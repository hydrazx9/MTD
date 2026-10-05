[README (1).md](https://github.com/user-attachments/files/33066665/README.1.md)
# MTD — Tower Defense (Roblox)

Tower Defense cooperativo em Luau. **Servidor-autoritativo**, **100% dirigido por configs** (adicionar torre, inimigo, mapa, dificuldade, efeito ou passiva é criar um `ModuleScript` numa pasta, sem editar código central), com **lobby + votação** e partida em **servidor reservado**.

Este documento explica como o projeto funciona de ponta a ponta. A ordem é: visão geral → mapa de pastas → como um jogo acontece → dados/configs → rede → simulação → cliente → modelos → manutenção.

---

## 1. Visão geral em 60 segundos

- O **mesmo place** roda em dois modos, decididos pelo `Session` ao iniciar o servidor:
  - **Lobby** — servidor público. Os jogadores equipam torres, escolhem mapa/dificuldade e **votam**.
  - **Match (partida)** — servidor *reservado* criado pelo lobby. Roda o `GameManager` (ondas, inimigos, torres).
- O atributo `workspace.SessionMode` (`"Lobby"` | `"Match"`) é replicado e o cliente o usa para mostrar/esconder a UI certa.
- Inimigos **não são Instances no servidor**: a posição é analítica (`âncora de distância + velocidade × tempo`), calculada uma vez por frame e reaproveitada por todas as torres. O cliente desenha tudo sozinho a partir de uma âncora enviada no spawn.
- O cliente **só pede** ações (comprar, melhorar, vender, mudar prioridade, votar). O servidor valida e decide.

```
                 ┌──────────── LOBBY (servidor público) ────────────┐
 jogadores  ──►  │ equipam torres · escolhem mapa/dificuldade       │
                 │ 1º "Jogar" inicia a votação (15 s)               │
                 │ todos votam · maioria vence (empates tratados)   │
                 └──────────────┬───────────────────────────────────┘
                                │ ReserveServer + TeleportAsync (leva MapId, Difficulty, ModeId, Loadouts)
                                ▼
                 ┌──────────── MATCH (servidor reservado) ──────────┐
                 │ Session lê o TeleportData → atributos MapId /    │
                 │ GameMode / Difficulty → restaura loadouts →      │
                 │ GameManager: Waiting → Intermission → WaveActive │
                 │ … → GameOver | Victory                           │
                 └──────────────┬───────────────────────────────────┘
                                │ 8 s depois do fim: TeleportAsync(PlaceId) sem código reservado
                                ▼
                         de volta ao LOBBY
```

> **No Studio** o `TeleportService` não funciona. Lá o "teleporte" é **simulado no mesmo servidor**: o lobby some, a partida começa e os personagens renascem. O teleporte real só existe no jogo publicado.

---

## 2. Mapa de pastas

```
ServerScriptService
├─ Main                         bootstrap: carrega registros, Net e inicia os serviços (ver §3)
└─ Server
   ├─ ConfigValidator           valida referências entre configs no boot
   ├─ Requests                  roteador Cliente→Servidor (uma RemoteFunction) + rate limit por jogador
   ├─ Replicator                ÚNICO ponto que fala com clientes sobre o mundo (pacote "Delta" a 20 Hz)
   ├─ Economy                   moedas por jogador (autoridade)
   ├─ Loadout                   torres equipadas por jogador (Get / Set / IsEquipped; trata a ação ToggleEquip)
   ├─ TowerService              compra / upgrade / venda / targeting (validação)
   ├─ AdminCommands             AdminGive { Amount, Target }
   ├─ Session                   Lobby × Match, votação, teleporte, dificuldade, volta ao lobby
   ├─ GameManager               máquina de estados da partida
   ├─ World                     estado vivo (mapa, inimigos, torres) + consultas espaciais
   ├─ PassiveEngine             liga módulos de ServerStorage.Passives a qualquer entidade com .Bus
   ├─ StatusEffectManager       aplica efeitos de StatusEffectsConfig em inimigos
   └─ Classes
      ├─ Tower                  OOP genérica (sem if/else por nome de torre)
      └─ Enemy                  OOP genérica (movimento por âncora, hooks no Bus)

ServerStorage
├─ Passives                     módulos de passiva (só servidor)
├─ Assets/Maps/<ModelName>      (opcional) modelo de mapa; sem ele o mapa é gerado (terreno + estrada)
└─ Referencias                  modelos guardados para uso futuro (fora do mundo do jogo)

ReplicatedStorage
├─ Shared
│  ├─ Registry                  registros + AutoLoadConfigs
│  ├─ Net                       eventos e request compartilhados
│  ├─ EventBus                  eventos internos (Global)
│  ├─ PathUtil                  caminhos (polilinha) com comprimento acumulado
│  └─ PlacementRules            regras de posicionamento (servidor decide; cliente só prevê)
├─ Configs                      cada pasta "<X>Config" vira o registro "<X>"
│  ├─ TowersConfig  EnemiesConfig  MapsConfig  GameModesConfig
│  ├─ StatusEffectsConfig  TargetingConfig  DifficultiesConfig
├─ Assets/Models/{Towers,Enemies,Projectiles}/<ModelName>   modelos (ver §8)
└─ Frame · ImageButton · ManagerTemplate                    templates de UI usados por UnitPanel / UnitCard / UnitManager

StarterPlayer/StarterPlayerScripts
├─ ClientMain                   inicia Net, registros e módulos do cliente
├─ LocalScript                  desliga o Backpack do CoreGui
└─ Client
   ├─ ClientRenderEngine        TODO o visual (inimigos, torres, projéteis, barras de vida)
   ├─ UnitAnimator · Animators  animação procedural por juntas (ou Rig do Animation Editor)
   ├─ PlacementController       fantasma verde/vermelho, clique para colocar, seleção
   ├─ ShopUI                    HUD, barra de equipadas, inventário, painel da torre, atalhos de teclado
   ├─ UnitCard · UnitIcon       cartão de unidade (foto do modelo num ViewportFrame)
   ├─ UnitPanel                 painel da torre selecionada (upgrades, prioridade, venda)
   ├─ UnitManager               gerenciador de todas as unidades (aba Manager)
   └─ ChatCommands              /give · /dar (chama AdminGive)

StarterGui
├─ MainUI                       botões Inventário/Manager, painéis; Fechador alterna botões por SessionMode
└─ LobbyUI                      MapSelection (mapas, dificuldades, recompensas, Jogar), botão de abrir, LobbyController

Workspace
├─ Lobby                        lobby feito à mão (com SpawnLocation); o Session o usa se existir
└─ (chão da partida, etc.)      o mapa da partida é montado em Workspace.TDMap pelo World.LoadMap
```

---

## 3. Boot do servidor (`Main`)

1. `Registry.AutoLoadConfigs(ReplicatedStorage.Configs)` — cada pasta `<X>Config` vira `Registry.Of("<X>")`.
2. `Registry.Create("Passives"):LoadFolder(ServerStorage.Passives)` — passivas ficam só no servidor.
3. `Net.Init()` — cria `ReplicatedStorage.Remotes` (Request + eventos).
4. Passos (cada um protegido por `pcall`, falha não derruba os outros):
   `ConfigValidator` → `Requests` → `Replicator` → `Economy` → `Loadout` → `TowerService` → `AdminCommands` → **`Session`**.
5. O `Session.Init(startMatch)` decide o modo. O `GameManager.Init()` **só roda dentro do callback** `startMatch`: na partida (depois de ler o `TeleportData`) ou, no Studio, quando a votação termina.

---

## 4. Lobby e votação (`Session` + `LobbyController`)

### Regras
1. O 1º jogador que clica **Jogar** envia seu voto (`SubmitVote`) e **inicia** a contagem (`VoteDuration`, 15 s). Os outros jogadores recebem a tela aberta automaticamente.
2. Durante a contagem, clicar em outro mapa/dificuldade **troca o voto**. O botão vira **Votar (n)** e confirma a seleção atual.
3. Cada cartão mostra `xN` com os votos. Quem sai do lobby deixa de contar.
4. A votação termina quando o tempo acaba **ou** quando todos votaram (`EarlyFinishDelay`, 3 s).
5. **Mapa:** o mais votado; empate → sorteio entre os empatados; ninguém votou → qualquer mapa.
6. **Dificuldade:** a mais votada; empate → a de **maior `Order`**; ninguém votou → `DefaultDifficulty` (`"Normal"`).
7. O servidor reserva um servidor e teleporta **todo o lobby** levando `MapId`, `Difficulty`, `ModeId` e o **loadout** de cada jogador. Se falhar, o lobby é liberado e todos recebem o aviso para votar de novo.

### Protocolo (tudo por `Net`)
| Direção | Nome | Conteúdo |
|---|---|---|
| Cliente → Servidor | `Request "SubmitVote"` | `{ MapId, Difficulty }` → `{ Ok, Started, EndsAt, Duration }` |
| Cliente → Servidor | `Request "GetVoteState"` | foto do estado (inclui `Mine`, o voto do próprio jogador) |
| Servidor → Cliente | `Event "LobbyVote"` | `{ Active, Locked, EndsAt, Duration, Voters, Players, Maps = {[id]=n}, Difficulties = {[id]=n}, Result?, Failed? }` |

`EndsAt` usa `workspace:GetServerTimeNow()`: o cliente calcula a contagem sozinho (sem enviar um evento por segundo).

### Ajustes (topo de `Server/Session`)
`ForceMode` (`nil`/`"Lobby"`/`"Match"`), `DefaultMode`, `VoteDuration`, `EarlyFinishDelay`, `DefaultDifficulty`, `ReturnToLobby`, `ReturnDelay`, `JoinDataTimeout`, `LobbyOrigin` (só se não existir `Workspace.Lobby`).

### Partida (Match)
`Session` espera o 1º jogador, lê `player:GetJoinData().TeleportData`, aplica os atributos que o `GameManager` já lê (`workspace.MapId`, `workspace.GameMode`) + `Difficulty`, restaura o loadout (`Loadout.Set`) e chama o `GameManager.Init()`. No `GameOver`/`Victory`, depois de `ReturnDelay` segundos, devolve todos ao lobby.

### Dificuldade
`DifficultiesConfig/<Id>` define `Multipliers` (`EnemyHealth`, `EnemySpeed`, `Reward`, `TowerCost`, `SellRatio`). Ao entrar em `WaitingForPlayers`, o `Session` **clona** `World.Map.Config` e multiplica `Multipliers` (o registro original do mapa nunca é alterado). Campos `Order` (ordena a UI e decide empates) e `Rewards = { Coins, XP }` (**só exibição**: ainda não existe pagamento/XP persistente).

---

## 5. Dados: Registry e Configs

`Registry.AutoLoadConfigs` transforma **cada pasta `<Nome>Config`** em `Registry.Of("<Nome>")`. Um módulo retorna **uma definição** `{ Id = "X", ... }` (ou uma lista delas). `registry:OnRegister(fn)` chama `fn` para o que já existe **e** para o que for registrado depois — é assim que as UIs geram botões sozinhas.

> **Regra do projeto:** o `Id` é a identidade; o *nome do módulo deve ser igual ao `Id`*. Para conteúdo novo, **crie um módulo na pasta certa em vez de editar um sistema central**.

| Pasta | Registro | Campos principais |
|---|---|---|
| `TowersConfig` | `Towers` | `Id, ModelName, DisplayName, Description, Icon, Cost, MaxPerPlayer, Tags, TargetTags, Visual, Stats{Damage,DamageType,Range,Cooldown,AttackSpeed,ProjectileSpeed,SplashRadius,Windup}, Targeting{Modes,Default}, Effects, Passives, Upgrades{Rules,Paths}` |
| `EnemiesConfig` | `Enemies` | `Id, ModelName, DisplayName, Health, Speed, Reward, LivesDamage, Tags, Visual, Spawn{FromWave,Weight,Cost,BossEvery}, Passives, Immunities` |
| `MapsConfig` | `Maps` | `Id, DisplayName, ModelName?, GroundY, Paths, DefaultPath, Bounds, PathClearance, TowerSpacing, StartingCoins, StartingLives, Multipliers`, opcionais `Icon`, `Rewards`, `RewardMultiplier` |
| `GameModesConfig` | `GameModes` | `Id, MinPlayers, WaitingTime, IntermissionTime, VictoryWave, Waves{Manual,Generator}, HealthScale, WaveBonus` |
| `DifficultiesConfig` | `Difficulties` | `Id, DisplayName, Order, Multipliers, Rewards` |
| `StatusEffectsConfig` | `StatusEffects` | `Id, Tags, Stacking("Refresh"\|"Stack"), Defaults, ReapplyCooldown, OnApply/OnTick/OnRemove/OnRefresh` |
| `TargetingConfig` | `Targeting` | modos: `Closest, First, Last, Strongest, Weakest` (função `Score`) |
| `ServerStorage.Passives` | `Passives` | `Id, Priority, Defaults, OnAttach, OnDetach, OnParamsChanged, Hooks{...}` |

### Upgrades de uma torre
`Upgrades = { Rules = { SecondaryMaxTier = 2 }, Paths = { { Id, Name, Tiers = { { Name, Cost, Description, Modifiers, PassiveParams, AddPassives, AddEffects } } } } }`
- `Modifiers = { Stat = { Add | Mul | Set } }` altera `Stats`.
- `PassiveParams = { PassiveId = { Param = valor } }` ajusta passivas já ligadas.
- `AddPassives` / `AddEffects` ligam novas passivas/efeitos ao subir de nível.
- O caminho secundário é limitado por `SecondaryMaxTier`; o servidor devolve `PathLocked` / `MaxTier` quando aplicável.
- Custo cobrado = `ceil(Cost × Multipliers.TowerCost)`.

### Passivas e efeitos existentes
- **Passivas:** `DamageReduction, Executioner, RampingDamage, SplitOnDeath, SupportAura` + `CriticalStrike, DistanceBonus, Chain, Pierce, Knockback, PulseNova, GoldGenerator, BountyHunter, Reaper, KillStack, Spoolup, Gambler, Overcharge`.
- **Efeitos de status:** `Burn, Freeze, Slow, Poison, Stun, Vulnerable`.
- **Hooks no Bus da torre:** `OnTowerPlaced, OnTargetSelected, OnPreAttack, OnPostAttack, OnEnemyKill, OnTick, OnUpgrade, OnTowerRemoved`.
- **Hooks no Bus do inimigo:** `OnSpawn, OnTick, OnEnemyTakeDamage(enemy, amount, type, source, hit), OnDeath(enemy, killer), OnLeak(enemy)` (em `OnEnemyTakeDamage` as passivas mudam `hit.Amount`).

### As 23 torres
| Original | Novas (20) |
|---|---|
| `Cannon`, `FrostMortar`, `SupportTotem` | `Archer` crítico · `Sniper` mais dano à distância · `Poisoner` veneno em stacks · `Tesla` raio em cadeia · `Hammer` atordoa/empurra em área · `Flamethrower` fogo contínuo · `Miner` gera moedas · `BountyHunter` bônus por abate · `Reaper` ceifa inimigos leves + maldição · `Berserker` cresce a cada abate · `MachineGun` cadência crescente · `Bomber` bomba carregada a cada 3º tiro · `WindMage` empurra e desacelera · `Cryomancer` aura gélida · `Reactor` pulso em área · `Gambler` dano sorteado · `Marker` marca alvos (+dano de todas as torres) · `WarBanner` aura de cadência · `Railgun` tiro que atravessa · `Alchemist` frasco com efeito aleatório |

---

## 6. Rede

Tudo passa por `ReplicatedStorage.Shared.Net`. **Não crie RemoteEvent/RemoteFunction soltos.**

- **Requests** (Cliente → Servidor, uma `RemoteFunction`): `Net.Request():InvokeServer(acao, payload)` → tabela `{ Ok = true, ... }` ou `{ Ok = false, Error = "Codigo" }`. Rate limit por jogador (balde de 20 fichas, 10/s).
  Ações: `ClientReady, PlaceTower, UpgradeTower, SellTower, SetTargeting, ToggleEquip, SubmitVote, GetVoteState, AdminGive`.
  Nova ação de jogador = novo `Requests.Handle("Nome", fn)` em qualquer módulo de servidor.
- **Eventos** (Servidor → Cliente): `Net.Event("Nome")`. Pré-criados: `Delta, GameState, PlayerData, Notify, Loadout`; `LobbyVote` é criado pelo `Session`.
- **`Delta`:** o `Replicator` agrupa spawns/mudanças de movimento/torres num pacote a 20 Hz. O servidor **não** envia posição de inimigo por frame.
- **Segurança:** o servidor valida dinheiro, dono da torre, posição, caminho de upgrade e **todos** os valores recebidos. Nunca confie no cliente.

---

## 7. Simulação da partida

- **`GameManager`** — estados: `WaitingForPlayers → Intermission → WaveActive → Intermission → … → GameOver | Victory → WaitingForPlayers` (reinicia 12 s depois do fim). Tudo que varia vem do `GameModesConfig`. Não crie um segundo sistema de partidas/ondas.
- **`World`** — `LoadMap`, `SpawnEnemy`, `AddEnemy`, `QueryEnemies(centro, raio)`, `QueryTowers`, `Update/Step`, `Clear`. O mapa é montado em `Workspace.TDMap`.
- **`Enemy`** — âncora `(DistanceAnchor, TimeAnchor)` + velocidade. Mudou a velocidade → rebase + replica.
- **`Tower`** — stats finais = base do config + modificadores nomeados (`SetModifier`); alvo = `Score` do modo de targeting; ataque: `OnPreAttack` → projétil (tempo de voo) → dano/efeitos → `OnPostAttack`.
- **`Economy`** — `Get, SetCoins, CanAfford, Add, AddAll, Spend, Remove`. É a única fonte de moedas.
- **`PlacementRules.Check(map, pos, torres)`** — limites do mapa, distância dos caminhos (`PathClearance`) e entre torres (`TowerSpacing`). O cliente usa só para o fantasma; o servidor decide.

---

## 8. Cliente, modelos e ícones

### UI gerada por configs
Nenhum botão de torre/mapa/dificuldade é desenhado à mão: o código **clona templates** e preenche com os dados do config.
- Cartão de unidade (`UnitCard`): `ImageButton` em `ReplicatedStorage` com um `TextLabel` filho `PriceAndName`.
- Painel da torre (`UnitPanel`): `Frame` em `ReplicatedStorage` com `UpgradeTemplate`, `Upgrade1Box`, `Upgrade2Box`.
- Lobby (`LobbyController`): clona o 1º `MapTemplate` / `DificuldadeTemplate` do `MapSelection`. **Para mudar o visual, edite esses templates.**

### Atalhos de teclado (só na partida)
`1…9` seleciona a unidade do slot para colocar · `X` vende a torre selecionada · `E` melhora o upgrade **mais barato** que você consegue pagar (empate = sorteio; na torre selecionada ou, sem seleção, entre todas as suas) · `Q` troca a prioridade da torre selecionada · `Esc` ou clique direito cancela a colocação.

### Modelos de torre (`ReplicatedStorage.Assets.Models.Towers.<ModelName>`)
`ModelName` do config = nome do Model. Sem modelo, o jogo usa um bloco colorido (`Visual.Color` / `Visual.Size`).

**Humanoide "macaco" R6** (perfil `Soldier`): `HumanoidRootPart` é o `PrimaryPart` com `PivotOffset = (0, −3 × escala, 0)` (pés no chão); juntas `Root Hip, Neck, Left/Right Shoulder, Left/Right Hip` (os nomes que o `UnitAnimator` pose); `MonkeyHat` e `Monkey Tail`; arma/acessório soldado ao `Torso` por `Weld` e um `Attachment` **`Muzzle`** onde sai o projétil (a frente do modelo é −Z).
**Torre simples** (perfil `Totem`): `Base` como `PrimaryPart` com `PivotOffset` na base, peças soldadas em cadeia, juntas `OrbJoint` / `RingJoint` (o animador flutua/gira).
Atributo `AnimProfile` no Model: `Soldier` (padrão de torre), `Totem`, `Walk` (padrão de inimigo). Todas as peças ficam `Anchored`: o `UnitAnimator` resolve as juntas na mão e move em lote.

### Ícones
O `UnitIcon` gera a "foto" de cada card a partir do **próprio modelo** (ViewportFrame) quando `Icon` está vazio. Para usar uma imagem sua, preencha `Icon = "rbxassetid://..."` no módulo da torre. Sem ícone **e** sem modelo, o card é tingido com `Visual.Color`.

---

## 9. Scripts de manutenção (Command Bar do Studio, modo edição)

Todos são **idempotentes** (podem rodar de novo), registram cada passo no Output e criam um ponto no histórico (Ctrl+Z desfaz). **Desconecte o Rojo antes**: ele pode apagar o que for criado só no Studio. Faça um *Save As* antes da limpeza.

| Ordem | Arquivo | O que faz |
|---|---|---|
| 1 | `1_limpeza` | Apaga o Tower Defense legado (`ServerScriptService.TowerDefense`, `ReplicatedStorage.TowerDefense`, `Workspace.TowerDefenseMap`) — só se nenhum script ainda o referenciar; apaga `TESTE111`, a `ClassicSword` e a cópia antiga de `ReplicatedStorage.MapSelection`; **move** modelos soltos para `ServerStorage.Referencias`; corrige nomes de módulos cortados. `DRY_RUN = true` só mostra o que faria. |
| 2 | `2_lobby_votos` | Instala o `Session` com votação e o `LobbyController` corrigido. |
| 3 | `3_modelos` | Cria os 20 modelos das novas torres em `Assets/Models/Towers`. |
| — | `install_personagens` | (Só para recomeçar do zero) cria as 13 passivas, os 3 efeitos e as 20 torres. |

---

## 10. Receitas

- **Nova torre:** copie uma torre parecida em `TowersConfig`, mude `Id`/stats/`Passives`/`Upgrades`. O Registry a descobre sozinho (loja, inventário e loadout já a mostram). Para o visual, crie um Model com o mesmo nome em `Assets/Models/Towers`.
- **Nova mecânica de torre/inimigo:** crie uma passiva em `ServerStorage.Passives` (ou um efeito em `StatusEffectsConfig`). **Não** coloque `if tower.Id == ...` no código.
- **Novo inimigo:** módulo em `EnemiesConfig`. Com bloco `Spawn`, o gerador de ondas o sorteia sozinho.
- **Novo mapa:** módulo em `MapsConfig` (`Paths`, `Bounds`, moedas/vidas). Opcionalmente `Icon` e `Rewards`. Ele aparece na votação sozinho.
- **Nova dificuldade:** módulo em `DifficultiesConfig` com `Order` e `Multipliers`. Se a UI tiver menos cartões que dificuldades, ajuste o layout dos templates.
- **Nova ação de jogador:** `Requests.Handle("Acao", function(player, payload) ... end)`. Valide tudo no servidor.
- **Novo modo de alvo:** módulo em `TargetingConfig` com `Score`.

---

## 11. Testando e depurando

- **Studio (Play):** nasce no lobby → *Selecionar Mapa* → escolha → *Jogar* (sozinho a partida começa em ~3 s). Para ir direto à partida como antes: `SETTINGS.ForceMode = "Match"` no `Session`.
- **Jogo publicado / Team Test:** o teleporte e o servidor reservado só funcionam aqui. O servidor da partida tem `game.PrivateServerId ~= ""` e `PrivateServerOwnerId == 0`.
- **Logs úteis:** `[Boot] ok/ERRO: <passo>` (Main), `[Session] modo: ...`, `[Session] votação encerrada: mapa=... dificuldade=...`.
- **Atributos de `workspace`:** `SessionMode`, `MapId`, `GameMode`, `Difficulty`, `MaxEquipped` (slots de loadout; padrão 5).
- **Nada aparece no lobby?** Confirme `Workspace.Lobby` com `SpawnLocation`, e que `ReplicatedStorage.Configs` tem `MapsConfig` e `DifficultiesConfig`.
- **Votação não inicia?** O `LobbyController` mostra o erro no `Status`; confira o Output do servidor por `[Session]`.

---

## 12. Regras de ouro

1. **O projeto já existe:** altere o mínimo necessário; não reescreva sistemas nem "modernize" sem pedido.
2. **Um sistema por função:** não crie versões paralelas de `Registry`, `Net`, `EventBus`, `PlacementRules`, `GameManager`, `Economy`.
3. **Config antes de código:** conteúdo novo vai numa pasta `*Config` ou em `Passives`.
4. **Servidor decide:** o cliente pede, o servidor valida (dinheiro, dono, posição, caminho, valores).
5. **Comunicação interna por `EventBus`**, rede por `Net`.
6. **Sem arquitetura legada:** o antigo `TowerDefense/TowerManager` foi removido; não reintroduza.

## 13. Limites conhecidos

- **Recompensas** (Coins/XP no painel) são só exibição; não há pagamento nem progressão persistente (DataStore).
- O **teleporte real** e o **servidor reservado** só podem ser validados no jogo publicado.
- O `GameManager` reinicia a partida sozinho 12 s depois do fim; com `ReturnToLobby` ligado, os jogadores voltam ao lobby antes (8 s).
