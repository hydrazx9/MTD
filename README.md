  18:16:20.068  hydrazx9 joined live editing session.  -  Studio
  18:16:29.046  cloud_105278801373290.Script:1: Expected identifier when parsing expression, got ``  -  Studio
  18:16:49.148  > local HttpService = game:GetService("HttpService")

local output = {}

local function add(text)
	table.insert(output, text)
end

local function indent(depth)
	return string.rep("    ", depth)
end

local function scan(instance, depth)
	local className = instance.ClassName
	local name = instance.Name

	add(indent(depth) .. name .. " [" .. className .. "]")

	-- Salva o código dos scripts
	if instance:IsA("Script")
		or instance:IsA("LocalScript")
		or instance:IsA("ModuleScript") then

		add(indent(depth + 1) .. "----- SOURCE -----")
		add(instance.Source)
		add(indent(depth + 1) .. "----- END SOURCE -----")
	end

	for _, child in ipairs(instance:GetChildren()) do
		scan(child, depth + 1)
	end
end

add("===== ROBLOX PROJECT MAP =====")
add("Gerado em: " .. os.date("%Y-%m-%d %H:%M:%S"))
add("")

scan(game, 0)

local result = table.concat(output, "\n")

-- Tenta copiar para o clipboard do Studio
pcall(function()
	setclipboard(result)
end)

print("========================================")
print("PROJETO EXPORTADO!")
print("Tamanho: " .. #result .. " caracteres")
print("========================================")
print(result)  -  Studio
  18:16:49.197  ========================================  -  Editar
  18:16:49.197  PROJETO EXPORTADO!  -  Editar
  18:16:49.197  Tamanho: 442723 caracteres  -  Editar
  18:16:49.198  ========================================  -  Editar
  18:16:49.200  ===== ROBLOX PROJECT MAP =====
Gerado em: 2026-10-02 18:16:49

Place1 [DataModel]
    Workspace [Workspace]
        SunRays [SunRaysEffect]
        ColorCorrection [ColorCorrectionEffect]
        Blur [BlurEffect]
        Bloom [BloomEffect]
            Atmosphere [Atmosphere]
            ArcHandles [ArcHandles]
        TowerDefenseMap [Folder]
            Waypoints [Folder]
            Path [Folder]
            TowerSpots [Folder]
            Decor [Folder]
        Terrain [Terrain]
        Camera [Camera]
    Run Service [RunService]
    GuiService [GuiService]
        ScreenshotHud [ScreenshotHud]
    Stats [Stats]
        PerformanceStats [StatsItem]
            Memory [StatsItem]
                CoreMemory [StatsItem]
                    default [StatsItem]
                    staticinit [StatsItem]
                    http/batch [StatsItem]
                    lua/web-cache [StatsItem]
                    contentProvider/asyncDecryption [StatsItem]
                    internal/DataModelPatch [StatsItem]
                    render/prepare/physics [StatsItem]
                    physics/step [StatsItem]
                    physics/buffers [StatsItem]
                    physics/mechanism [StatsItem]
                    physics/assembly [StatsItem]
                    experienceStateCaptureService [StatsItem]
                    gui/TextLayout [StatsItem]
                    render/fonts [StatsItem]
                    gui/HarfBuzz [StatsItem]
                    gui/FreeType [StatsItem]
                    fontProvider/loading [StatsItem]
                    gui/FontData [StatsItem]
                    internal/localizationTable [StatsItem]
                    internal/localization [StatsItem]
                    ads/AdGui [StatsItem]
                    internal/MarketplaceService [StatsItem]
                    geometry/EditableMesh/Geometry [StatsItem]
                    geometry/EditableMesh/SpatialCache [StatsItem]
                    geometry/EditableMesh/GpuAssigned [StatsItem]
                    physics/bullet [StatsItem]
                    network/netAssetSerialized [StatsItem]
                    network/netAssetRegistries [StatsItem]
                    network/netAssetProxy [StatsItem]
                    AppCore/GuidRegistry [StatsItem]
                    instance/fullname [StatsItem]
                    internal/TaskScheduler [StatsItem]
                    profiler [StatsItem]
                    internal/RbxThread [StatsItem]
                    localstorage [StatsItem]
                    telemetry/analytics [StatsItem]
                    telemetry [StatsItem]
                    http/client [StatsItem]
                    http/curl [StatsItem]
                    http/requestcallback [StatsItem]
                    openssl [StatsItem]
                    http/wslay [StatsItem]
                    SQLite [StatsItem]
                    telemetry/fields_container [StatsItem]
                    telemetry/counter [StatsItem]
                    telemetry/event [StatsItem]
                    telemetry/stat [StatsItem]
                    telemetry/v2_try_cut_and_send [StatsItem]
                    gui/FreeTypeDT [StatsItem]
                    AssetProvider/total [StatsItem]
                    sound/default [StatsItem]
                    render/copy [StatsItem]
                    render/vertexlayout [StatsItem]
                    render/shader [StatsItem]
                    render/swapchain [StatsItem]
                    raknet/raknet [StatsItem]
                    raknet/startup [StatsItem]
                    raknet/recv-buffer [StatsItem]
                    raknet/buffered-commands [StatsItem]
                    raknet/packet-return [StatsItem]
                    raknet/tx-outgoing [StatsItem]
                    raknet/tx-datagram [StatsItem]
                    raknet/rx-ordered-heap [StatsItem]
                    raknet/rx-split-reassembly [StatsItem]
                    raknet/rx-output [StatsItem]
                    raknet/rx-handling [StatsItem]
                    raknet/datagram-history [StatsItem]
                    raknet/ack-nak [StatsItem]
                    RbxTransport/Io/sys [StatsItem]
                    RbxTransport/Io/libuv [StatsItem]
                    video/encoding/hardware [StatsItem]
                    video/default [StatsItem]
                    video/packet [StatsItem]
                    video/codec [StatsItem]
                    video/texture [StatsItem]
                    internal/PerformanceControl [StatsItem]
                    RbxTransport/RtcIo/Local [StatsItem]
                    RbxTransport/RtcIo/Remote/Rx [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptConnection [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptWtSession [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptH3 [StatsItem]
                    RbxTransport/RtcIo/Remote/NewAppConnection [StatsItem]
                    RbxTransport/RtcIo/Remote/Handshake [StatsItem]
                    RbxTransport/RtcIo/Remote/StreamAccepted [StatsItem]
                    RbxTransport/RtcIo/Remote/StreamClose [StatsItem]
                    RbxTransport/RtcIo/Remote/Ack [StatsItem]
                    RbxTransport/RtcIo/Remote/FlowControl [StatsItem]
                    RbxTransport/RtcIo/Remote/Loss [StatsItem]
                    RbxTransport/RtcIo/Remote/ConnClose [StatsItem]
                    RbxTransport/RtcIo/Remote/AppControl [StatsItem]
                    RbxTransport/RtcIo/Remote/AppFin [StatsItem]
                    RbxTransport/RtcIo/Remote/OpenUnreliableChannel [StatsItem]
                    physics/broadphase [StatsItem]
                    physics/midphase [StatsItem]
                    internal/ixp [StatsItem]
                    video/realtime_media [StatsItem]
                    video/capture_engine [StatsItem]
                    physics/aerodynamics/mesh [StatsItem]
                    physics/aerodynamics/integrator [StatsItem]
                    physics/aerodynamics/linearintegrator [StatsItem]
                    physics/aerodynamics/cpintegrator [StatsItem]
                    physics/aerodynamics/shinterpolator [StatsItem]
                    physics/aerodynamics/reducedmesh [StatsItem]
                    internal/ScriptContext [StatsItem]
                    lua/bytecode [StatsItem]
                    lua/codegen [StatsItem]
                    lua/codegenpages [StatsItem]
                    internal/RuntimeScriptService [StatsItem]
                    CoreScriptTelemetry [StatsItem]
                    physics/solver/buffers [StatsItem]
                    physics/solver/sleep [StatsItem]
                    physics/solver/ldl [StatsItem]
                    physics/solver/misc [StatsItem]
                    internal/DataModelGenericJob [StatsItem]
                    studio/undo [StatsItem]
                    internal/InstanceStitchingHandler [StatsItem]
                    CollectionService [StatsItem]
                    internal/ChatService [StatsItem]
                    internal/GlobalSettings [StatsItem]
                    render/terrain/heightmapImporter [StatsItem]
                    geometry/EditableImage [StatsItem]
                    collections/collection [StatsItem]
                    collections/watcher [StatsItem]
                    performanceStats [StatsItem]
                    collections/proximity [StatsItem]
                    internal/AuroraService/InputFrame [StatsItem]
                    internal/AuroraService/HashBuffer [StatsItem]
                    internal/AuroraService/Prediction [StatsItem]
                    internal/Workspace [StatsItem]
                    internal/RemoteFunction [StatsItem]
                    internal/LogService [StatsItem]
                    render/lightgrid [StatsItem]
                    render/system [StatsItem]
                    render/bindworkspace [StatsItem]
                    render/adorn [StatsItem]
                    render/perform/statistics [StatsItem]
                    render/prepare [StatsItem]
                    render/prepare/adorn [StatsItem]
                    render/perform [StatsItem]
                    render/perform/adorn [StatsItem]
                    render/glyphaatlas/ugc [StatsItem]
                    render/glyphatlas/core [StatsItem]
                    render/terrain/grass/async [StatsItem]
                    render/terrain/grass [StatsItem]
                    render/prepare/terrain/grass [StatsItem]
                    render/target [StatsItem]
                    render/target/pooled [StatsItem]
                    render/perform/zpre [StatsItem]
                    render/clouds [StatsItem]
                    render/ssao [StatsItem]
                    render/glow [StatsItem]
                    render/sunrays [StatsItem]
                    render/dof [StatsItem]
                    render/blur [StatsItem]
                    render/colorCorrection [StatsItem]
                    render/highlight [StatsItem]
                    render/RtPool [StatsItem]
                    render/mainRts [StatsItem]
                    render/ui [StatsItem]
                    render/shadowmap [StatsItem]
                    render/perform/shadowmap [StatsItem]
                    render/shadowmap/depthcache [StatsItem]
                    render/perform/materialMisc [StatsItem]
                    render/perform/materialGc [StatsItem]
                    render/material/failsafe [StatsItem]
                    render/perform/terrain [StatsItem]
                    render/prepare/terrain [StatsItem]
                    render/instanceglob [StatsItem]
                    render/gpu_geom_mgr [StatsItem]
                    dynamic/mesh [StatsItem]
                    dynamic/texture [StatsItem]
                    render/envmap [StatsItem]
                    render/material/misc [StatsItem]
                    render/prepare/tc [StatsItem]
                    render/prepare/sceneUpdater [StatsItem]
                    render/prepare/parts [StatsItem]
                    render/prepare/megaCluster [StatsItem]
                    render/prepare/attachments [StatsItem]
                    render/swocc [StatsItem]
                    render/perform/textureAtlasInsert [StatsItem]
                    render/meshManager/async [StatsItem]
                    textureRef [StatsItem]
                    render/texture/local [StatsItem]
                    render/texture/fallback [StatsItem]
                    render/texture/loading [StatsItem]
                    render/perform/textureGc [StatsItem]
                    render/prepare/textureManager [StatsItem]
                    render/perform/textureManager [StatsItem]
                    render/sky [StatsItem]
                    render/advsky [StatsItem]
                    render/perform/cullableScene [StatsItem]
                    render/prepare/motionBuffer [StatsItem]
                    render/geometryGenerator [StatsItem]
                    render/perform/scratchFB [StatsItem]
                    render/prepare/lightObject [StatsItem]
                    render/terrain/async/chunkGen [StatsItem]
                    render/perform/terrain/occlusionGen [StatsItem]
                    render/viewportFrames [StatsItem]
                    render/prepare/lightGridChunk [StatsItem]
                    render/perform/lightGrid [StatsItem]
                    render/fastCluster/prepareSkinning [StatsItem]
                    render/fastCluster/skinningReserve [StatsItem]
                    render/prepare/beamNode [StatsItem]
                    render/prepare/customEmitter [StatsItem]
                    render/pipeline [StatsItem]
                    render/pipeline/updates [StatsItem]
                    render/meshFetcherDecomp [StatsItem]
                    network/compresspacket [StatsItem]
                    network/decompresspacket [StatsItem]
                    network/ISR/Property [StatsItem]
                    network/groupManager [StatsItem]
                    network/ISR/Replicator [StatsItem]
                    network/setManager [StatsItem]
                    internal/CSGDictionary [StatsItem]
                    network/HeatmapQueryService [StatsItem]
                    internal/HttpRbxApiService [StatsItem]
                    internal/StarterPlayer [StatsItem]
                    datastore/cache [StatsItem]
                    animation/skeleton_watcher [StatsItem]
                    wrap/layeredDeformer [StatsItem]
                    internal/Humanoid [StatsItem]
                    temporaryCageMeshProvider/save [StatsItem]
                    wrap/hsr [StatsItem]
                    animation/skeleton [StatsItem]
                    wrap/deformMeshProvider [StatsItem]
                    gui/Uncategorized [StatsItem]
                    gui/UIQuadTree [StatsItem]
                    languageServices/async [StatsItem]
                    languageServices/generic [StatsItem]
                    languageServices/shadow [StatsItem]
                    network/streamingReplication [StatsItem]
                    network/streamJob [StatsItem]
                    network/replicationCoalescing [StatsItem]
                    network/deserializestep [StatsItem]
                    network/onreceive [StatsItem]
                    network/sharedQueue [StatsItem]
                    network/megaReplicationData [StatsItem]
                    network/modelCompleteness [StatsItem]
                    network/refPropTracking [StatsItem]
                    network/replicator [StatsItem]
                    internal/InputReplicator [StatsItem]
                    network/gcJob [StatsItem]
                    network/instanceObjectManager [StatsItem]
                    network/server [StatsItem]
                    network/streamingSolver [StatsItem]
                    network/streamingObserver [StatsItem]
                    network/replicatedInstances [StatsItem]
                    network/deferredtrees [StatsItem]
                    network/newinstanceitem [StatsItem]
                    network/streamDataItem [StatsItem]
                    network/ISR [StatsItem]
                    network/ISR/Connection [StatsItem]
                    network/ISR/Prioritization [StatsItem]
                    network/touchReplication [StatsItem]
                    network/replicationDataCache [StatsItem]
                    network/replicationDataCachePendingList [StatsItem]
                    network/ISR/groupMan [StatsItem]
                    network/physicsSenderCache [StatsItem]
                    sound/voice [StatsItem]
                    voice/webrtc [StatsItem]
                    voice/operations [StatsItem]
                    voice/audio [StatsItem]
                    sound/async [StatsItem]
                    sound/acoustics [StatsItem]
                    AudioWiring [StatsItem]
                    instance/AttributesAndTags [StatsItem]
                    internal/BaseThreadPool [StatsItem]
                    AssetProvider/state [StatsItem]
                    AssetProvider/other [StatsItem]
                    render/vertexstreamer [StatsItem]
                    friendsCalling/bringUp [StatsItem]
                PlaceMemory [StatsItem]
                    HttpCache [StatsItem]
                    Instances [StatsItem]
                    Signals [StatsItem]
                    LuaHeap [StatsItem]
                    Script [StatsItem]
                    PhysicsCollision [StatsItem]
                    BaseParts [StatsItem]
                    GraphicsSolidModels [StatsItem]
                    GraphicsHSR [StatsItem]
                    GraphicsMeshParts [StatsItem]
                    GraphicsParticles [StatsItem]
                    GraphicsParts [StatsItem]
                    GraphicsSpatialHash [StatsItem]
                    GraphicsTerrain [StatsItem]
                    GraphicsTexture [StatsItem]
                    GraphicsTextureCharacter [StatsItem]
                    Sounds [StatsItem]
                    TerrainVoxels [StatsItem]
                    TerrainPhysics [StatsItem]
                    Gui [StatsItem]
                    Animation [StatsItem]
                    Navigation [StatsItem]
                    GeometryCSG [StatsItem]
                    GraphicsSlimModels [StatsItem]
                UntrackedMemory [StatsItem]
                PlaceScriptMemory [StatsItem]
                    MemoryCategory_0 [StatsItem]
                    MemoryCategory_1 [StatsItem]
                    MemoryCategory_2 [StatsItem]
                    MemoryCategory_3 [StatsItem]
                    MemoryCategory_4 [StatsItem]
                    MemoryCategory_5 [StatsItem]
                    MemoryCategory_6 [StatsItem]
                    MemoryCategory_7 [StatsItem]
                    MemoryCategory_8 [StatsItem]
                    MemoryCategory_9 [StatsItem]
                    MemoryCategory_10 [StatsItem]
                    MemoryCategory_11 [StatsItem]
                    MemoryCategory_12 [StatsItem]
                    MemoryCategory_13 [StatsItem]
                    MemoryCategory_14 [StatsItem]
                    MemoryCategory_15 [StatsItem]
                    MemoryCategory_16 [StatsItem]
                    MemoryCategory_17 [StatsItem]
                    MemoryCategory_18 [StatsItem]
                    MemoryCategory_19 [StatsItem]
                    MemoryCategory_20 [StatsItem]
                    MemoryCategory_21 [StatsItem]
                    MemoryCategory_22 [StatsItem]
                    MemoryCategory_23 [StatsItem]
                    MemoryCategory_24 [StatsItem]
                    MemoryCategory_25 [StatsItem]
                    MemoryCategory_26 [StatsItem]
                    MemoryCategory_27 [StatsItem]
                    MemoryCategory_28 [StatsItem]
                    MemoryCategory_29 [StatsItem]
                    MemoryCategory_30 [StatsItem]
                    MemoryCategory_31 [StatsItem]
                    MemoryCategory_32 [StatsItem]
                    MemoryCategory_33 [StatsItem]
                    MemoryCategory_34 [StatsItem]
                    MemoryCategory_35 [StatsItem]
                    MemoryCategory_36 [StatsItem]
                    MemoryCategory_37 [StatsItem]
                    MemoryCategory_38 [StatsItem]
                    MemoryCategory_39 [StatsItem]
                    MemoryCategory_40 [StatsItem]
                    MemoryCategory_41 [StatsItem]
                    MemoryCategory_42 [StatsItem]
                    MemoryCategory_43 [StatsItem]
                    MemoryCategory_44 [StatsItem]
                    MemoryCategory_45 [StatsItem]
                    MemoryCategory_46 [StatsItem]
                    MemoryCategory_47 [StatsItem]
                    MemoryCategory_48 [StatsItem]
                    MemoryCategory_49 [StatsItem]
                    MemoryCategory_50 [StatsItem]
                    MemoryCategory_51 [StatsItem]
                    MemoryCategory_52 [StatsItem]
                    MemoryCategory_53 [StatsItem]
                    MemoryCategory_54 [StatsItem]
                    MemoryCategory_55 [StatsItem]
                    MemoryCategory_56 [StatsItem]
                    MemoryCategory_57 [StatsItem]
                    MemoryCategory_58 [StatsItem]
                    MemoryCategory_59 [StatsItem]
                    MemoryCategory_60 [StatsItem]
                    MemoryCategory_61 [StatsItem]
                    MemoryCategory_62 [StatsItem]
                    MemoryCategory_63 [StatsItem]
                    MemoryCategory_64 [StatsItem]
                    MemoryCategory_65 [StatsItem]
                    MemoryCategory_66 [StatsItem]
                    MemoryCategory_67 [StatsItem]
                    MemoryCategory_68 [StatsItem]
                    MemoryCategory_69 [StatsItem]
                    MemoryCategory_70 [StatsItem]
                    MemoryCategory_71 [StatsItem]
                    MemoryCategory_72 [StatsItem]
                    MemoryCategory_73 [StatsItem]
                    MemoryCategory_74 [StatsItem]
                    MemoryCategory_75 [StatsItem]
                    MemoryCategory_76 [StatsItem]
                    MemoryCategory_77 [StatsItem]
                    MemoryCategory_78 [StatsItem]
                    MemoryCategory_79 [StatsItem]
                    MemoryCategory_80 [StatsItem]
                    MemoryCategory_81 [StatsItem]
                    MemoryCategory_82 [StatsItem]
                    MemoryCategory_83 [StatsItem]
                    MemoryCategory_84 [StatsItem]
                    MemoryCategory_85 [StatsItem]
                    MemoryCategory_86 [StatsItem]
                    MemoryCategory_87 [StatsItem]
                    MemoryCategory_88 [StatsItem]
                    MemoryCategory_89 [StatsItem]
                    MemoryCategory_90 [StatsItem]
                    MemoryCategory_91 [StatsItem]
                    MemoryCategory_92 [StatsItem]
                    MemoryCategory_93 [StatsItem]
                    MemoryCategory_94 [StatsItem]
                    MemoryCategory_95 [StatsItem]
                    MemoryCategory_96 [StatsItem]
                    MemoryCategory_97 [StatsItem]
                    MemoryCategory_98 [StatsItem]
                    MemoryCategory_99 [StatsItem]
                    MemoryCategory_100 [StatsItem]
                    MemoryCategory_101 [StatsItem]
                    MemoryCategory_102 [StatsItem]
                    MemoryCategory_103 [StatsItem]
                    MemoryCategory_104 [StatsItem]
                    MemoryCategory_105 [StatsItem]
                    MemoryCategory_106 [StatsItem]
                    MemoryCategory_107 [StatsItem]
                    MemoryCategory_108 [StatsItem]
                    MemoryCategory_109 [StatsItem]
                    MemoryCategory_110 [StatsItem]
                    MemoryCategory_111 [StatsItem]
                    MemoryCategory_112 [StatsItem]
                    MemoryCategory_113 [StatsItem]
                    MemoryCategory_114 [StatsItem]
                    MemoryCategory_115 [StatsItem]
                    MemoryCategory_116 [StatsItem]
                    MemoryCategory_117 [StatsItem]
                    MemoryCategory_118 [StatsItem]
                    MemoryCategory_119 [StatsItem]
                    MemoryCategory_120 [StatsItem]
                    MemoryCategory_121 [StatsItem]
                    MemoryCategory_122 [StatsItem]
                    MemoryCategory_123 [StatsItem]
                    MemoryCategory_124 [StatsItem]
                    MemoryCategory_125 [StatsItem]
                    MemoryCategory_126 [StatsItem]
                    MemoryCategory_127 [StatsItem]
                    MemoryCategory_128 [StatsItem]
                    MemoryCategory_129 [StatsItem]
                    MemoryCategory_130 [StatsItem]
                    MemoryCategory_131 [StatsItem]
                    MemoryCategory_132 [StatsItem]
                    MemoryCategory_133 [StatsItem]
                    MemoryCategory_134 [StatsItem]
                    MemoryCategory_135 [StatsItem]
                    MemoryCategory_136 [StatsItem]
                    MemoryCategory_137 [StatsItem]
                    MemoryCategory_138 [StatsItem]
                    MemoryCategory_139 [StatsItem]
                    MemoryCategory_140 [StatsItem]
                    MemoryCategory_141 [StatsItem]
                    MemoryCategory_142 [StatsItem]
                    MemoryCategory_143 [StatsItem]
                    MemoryCategory_144 [StatsItem]
                    MemoryCategory_145 [StatsItem]
                    MemoryCategory_146 [StatsItem]
                    MemoryCategory_147 [StatsItem]
                    MemoryCategory_148 [StatsItem]
                    MemoryCategory_149 [StatsItem]
                    MemoryCategory_150 [StatsItem]
                    MemoryCategory_151 [StatsItem]
                    MemoryCategory_152 [StatsItem]
                    MemoryCategory_153 [StatsItem]
                    MemoryCategory_154 [StatsItem]
                    MemoryCategory_155 [StatsItem]
                    MemoryCategory_156 [StatsItem]
                    MemoryCategory_157 [StatsItem]
                    MemoryCategory_158 [StatsItem]
                    MemoryCategory_159 [StatsItem]
                    MemoryCategory_160 [StatsItem]
                    MemoryCategory_161 [StatsItem]
                    MemoryCategory_162 [StatsItem]
                    MemoryCategory_163 [StatsItem]
                    MemoryCategory_164 [StatsItem]
                    MemoryCategory_165 [StatsItem]
                    MemoryCategory_166 [StatsItem]
                    MemoryCategory_167 [StatsItem]
                    MemoryCategory_168 [StatsItem]
                    MemoryCategory_169 [StatsItem]
                    MemoryCategory_170 [StatsItem]
                    MemoryCategory_171 [StatsItem]
                    MemoryCategory_172 [StatsItem]
                    MemoryCategory_173 [StatsItem]
                    MemoryCategory_174 [StatsItem]
                    MemoryCategory_175 [StatsItem]
                    MemoryCategory_176 [StatsItem]
                    MemoryCategory_177 [StatsItem]
                    MemoryCategory_178 [StatsItem]
                    MemoryCategory_179 [StatsItem]
                    MemoryCategory_180 [StatsItem]
                    MemoryCategory_181 [StatsItem]
                    MemoryCategory_182 [StatsItem]
                    MemoryCategory_183 [StatsItem]
                    MemoryCategory_184 [StatsItem]
                    MemoryCategory_185 [StatsItem]
                    MemoryCategory_186 [StatsItem]
                    MemoryCategory_187 [StatsItem]
                    MemoryCategory_188 [StatsItem]
                    MemoryCategory_189 [StatsItem]
                    MemoryCategory_190 [StatsItem]
                    MemoryCategory_191 [StatsItem]
                    MemoryCategory_192 [StatsItem]
                    MemoryCategory_193 [StatsItem]
                    MemoryCategory_194 [StatsItem]
                    MemoryCategory_195 [StatsItem]
                    MemoryCategory_196 [StatsItem]
                    MemoryCategory_197 [StatsItem]
                    MemoryCategory_198 [StatsItem]
                    MemoryCategory_199 [StatsItem]
                    MemoryCategory_200 [StatsItem]
                    MemoryCategory_201 [StatsItem]
                    MemoryCategory_202 [StatsItem]
                    MemoryCategory_203 [StatsItem]
                    MemoryCategory_204 [StatsItem]
                    MemoryCategory_205 [StatsItem]
                    MemoryCategory_206 [StatsItem]
                    MemoryCategory_207 [StatsItem]
                    MemoryCategory_208 [StatsItem]
                    MemoryCategory_209 [StatsItem]
                    MemoryCategory_210 [StatsItem]
                    MemoryCategory_211 [StatsItem]
                    MemoryCategory_212 [StatsItem]
                    MemoryCategory_213 [StatsItem]
                    MemoryCategory_214 [StatsItem]
                    MemoryCategory_215 [StatsItem]
                    MemoryCategory_216 [StatsItem]
                    MemoryCategory_217 [StatsItem]
                    MemoryCategory_218 [StatsItem]
                    MemoryCategory_219 [StatsItem]
                    MemoryCategory_220 [StatsItem]
                    MemoryCategory_221 [StatsItem]
                    MemoryCategory_222 [StatsItem]
                    MemoryCategory_223 [StatsItem]
                    MemoryCategory_224 [StatsItem]
                    MemoryCategory_225 [StatsItem]
                    MemoryCategory_226 [StatsItem]
                    MemoryCategory_227 [StatsItem]
                    MemoryCategory_228 [StatsItem]
                    MemoryCategory_229 [StatsItem]
                    MemoryCategory_230 [StatsItem]
                    MemoryCategory_231 [StatsItem]
                    MemoryCategory_232 [StatsItem]
                    MemoryCategory_233 [StatsItem]
                    MemoryCategory_234 [StatsItem]
                    MemoryCategory_235 [StatsItem]
                    MemoryCategory_236 [StatsItem]
                    MemoryCategory_237 [StatsItem]
                    MemoryCategory_238 [StatsItem]
                    MemoryCategory_239 [StatsItem]
                    MemoryCategory_240 [StatsItem]
                    MemoryCategory_241 [StatsItem]
                    MemoryCategory_242 [StatsItem]
                    MemoryCategory_243 [StatsItem]
                    MemoryCategory_244 [StatsItem]
                    MemoryCategory_245 [StatsItem]
                    MemoryCategory_246 [StatsItem]
                    MemoryCategory_247 [StatsItem]
                    MemoryCategory_248 [StatsItem]
                    MemoryCategory_249 [StatsItem]
                    MemoryCategory_250 [StatsItem]
                    MemoryCategory_251 [StatsItem]
                    MemoryCategory_252 [StatsItem]
                    MemoryCategory_253 [StatsItem]
                    MemoryCategory_254 [StatsItem]
                    MemoryCategory_255 [StatsItem]
                CoreScriptMemory [StatsItem]
                    MemoryCategory_0 [StatsItem]
                    MemoryCategory_1 [StatsItem]
                    MemoryCategory_2 [StatsItem]
                    MemoryCategory_3 [StatsItem]
                    MemoryCategory_4 [StatsItem]
                    MemoryCategory_5 [StatsItem]
                    MemoryCategory_6 [StatsItem]
                    MemoryCategory_7 [StatsItem]
                    MemoryCategory_8 [StatsItem]
                    MemoryCategory_9 [StatsItem]
                    MemoryCategory_10 [StatsItem]
                    MemoryCategory_11 [StatsItem]
                    MemoryCategory_12 [StatsItem]
                    MemoryCategory_13 [StatsItem]
                    MemoryCategory_14 [StatsItem]
                    MemoryCategory_15 [StatsItem]
                    MemoryCategory_16 [StatsItem]
                    MemoryCategory_17 [StatsItem]
                    MemoryCategory_18 [StatsItem]
                    MemoryCategory_19 [StatsItem]
                    MemoryCategory_20 [StatsItem]
                    MemoryCategory_21 [StatsItem]
                    MemoryCategory_22 [StatsItem]
                    MemoryCategory_23 [StatsItem]
                    MemoryCategory_24 [StatsItem]
                    MemoryCategory_25 [StatsItem]
                    MemoryCategory_26 [StatsItem]
                    MemoryCategory_27 [StatsItem]
                    MemoryCategory_28 [StatsItem]
                    MemoryCategory_29 [StatsItem]
                    MemoryCategory_30 [StatsItem]
                    MemoryCategory_31 [StatsItem]
                    MemoryCategory_32 [StatsItem]
                    MemoryCategory_33 [StatsItem]
                    MemoryCategory_34 [StatsItem]
                    MemoryCategory_35 [StatsItem]
                    MemoryCategory_36 [StatsItem]
                    MemoryCategory_37 [StatsItem]
                    MemoryCategory_38 [StatsItem]
                    MemoryCategory_39 [StatsItem]
                    MemoryCategory_40 [StatsItem]
                    MemoryCategory_41 [StatsItem]
                    MemoryCategory_42 [StatsItem]
                    MemoryCategory_43 [StatsItem]
                    MemoryCategory_44 [StatsItem]
                    MemoryCategory_45 [StatsItem]
                    MemoryCategory_46 [StatsItem]
                    MemoryCategory_47 [StatsItem]
                    MemoryCategory_48 [StatsItem]
                    MemoryCategory_49 [StatsItem]
                    MemoryCategory_50 [StatsItem]
                    MemoryCategory_51 [StatsItem]
                    MemoryCategory_52 [StatsItem]
                    MemoryCategory_53 [StatsItem]
                    MemoryCategory_54 [StatsItem]
                    MemoryCategory_55 [StatsItem]
                    MemoryCategory_56 [StatsItem]
                    MemoryCategory_57 [StatsItem]
                    MemoryCategory_58 [StatsItem]
                    MemoryCategory_59 [StatsItem]
                    MemoryCategory_60 [StatsItem]
                    MemoryCategory_61 [StatsItem]
                    MemoryCategory_62 [StatsItem]
                    MemoryCategory_63 [StatsItem]
                    MemoryCategory_64 [StatsItem]
                    MemoryCategory_65 [StatsItem]
                    MemoryCategory_66 [StatsItem]
                    MemoryCategory_67 [StatsItem]
                    MemoryCategory_68 [StatsItem]
                    MemoryCategory_69 [StatsItem]
                    MemoryCategory_70 [StatsItem]
                    MemoryCategory_71 [StatsItem]
                    MemoryCategory_72 [StatsItem]
                    MemoryCategory_73 [StatsItem]
                    MemoryCategory_74 [StatsItem]
                    MemoryCategory_75 [StatsItem]
                    MemoryCategory_76 [StatsItem]
                    MemoryCategory_77 [StatsItem]
                    MemoryCategory_78 [StatsItem]
                    MemoryCategory_79 [StatsItem]
                    MemoryCategory_80 [StatsItem]
                    MemoryCategory_81 [StatsItem]
                    MemoryCategory_82 [StatsItem]
                    MemoryCategory_83 [StatsItem]
                    MemoryCategory_84 [StatsItem]
                    MemoryCategory_85 [StatsItem]
                    MemoryCategory_86 [StatsItem]
                    MemoryCategory_87 [StatsItem]
                    MemoryCategory_88 [StatsItem]
                    MemoryCategory_89 [StatsItem]
                    MemoryCategory_90 [StatsItem]
                    MemoryCategory_91 [StatsItem]
                    MemoryCategory_92 [StatsItem]
                    MemoryCategory_93 [StatsItem]
                    MemoryCategory_94 [StatsItem]
                    MemoryCategory_95 [StatsItem]
                    MemoryCategory_96 [StatsItem]
                    MemoryCategory_97 [StatsItem]
                    MemoryCategory_98 [StatsItem]
                    MemoryCategory_99 [StatsItem]
                    MemoryCategory_100 [StatsItem]
                    MemoryCategory_101 [StatsItem]
                    MemoryCategory_102 [StatsItem]
                    MemoryCategory_103 [StatsItem]
                    MemoryCategory_104 [StatsItem]
                    MemoryCategory_105 [StatsItem]
                    MemoryCategory_106 [StatsItem]
                    MemoryCategory_107 [StatsItem]
                    MemoryCategory_108 [StatsItem]
                    MemoryCategory_109 [StatsItem]
                    MemoryCategory_110 [StatsItem]
                    MemoryCategory_111 [StatsItem]
                    MemoryCategory_112 [StatsItem]
                    MemoryCategory_113 [StatsItem]
                    MemoryCategory_114 [StatsItem]
                    MemoryCategory_115 [StatsItem]
                    MemoryCategory_116 [StatsItem]
                    MemoryCategory_117 [StatsItem]
                    MemoryCategory_118 [StatsItem]
                    MemoryCategory_119 [StatsItem]
                    MemoryCategory_120 [StatsItem]
                    MemoryCategory_121 [StatsItem]
                    MemoryCategory_122 [StatsItem]
                    MemoryCategory_123 [StatsItem]
                    MemoryCategory_124 [StatsItem]
                    MemoryCategory_125 [StatsItem]
                    MemoryCategory_126 [StatsItem]
                    MemoryCategory_127 [StatsItem]
                    MemoryCategory_128 [StatsItem]
                    MemoryCategory_129 [StatsItem]
                    MemoryCategory_130 [StatsItem]
                    MemoryCategory_131 [StatsItem]
                    MemoryCategory_132 [StatsItem]
                    MemoryCategory_133 [StatsItem]
                    MemoryCategory_134 [StatsItem]
                    MemoryCategory_135 [StatsItem]
                    MemoryCategory_136 [StatsItem]
                    MemoryCategory_137 [StatsItem]
                    MemoryCategory_138 [StatsItem]
                    MemoryCategory_139 [StatsItem]
                    MemoryCategory_140 [StatsItem]
                    MemoryCategory_141 [StatsItem]
                    MemoryCategory_142 [StatsItem]
                    MemoryCategory_143 [StatsItem]
                    MemoryCategory_144 [StatsItem]
                    MemoryCategory_145 [StatsItem]
                    MemoryCategory_146 [StatsItem]
                    MemoryCategory_147 [StatsItem]
                    MemoryCategory_148 [StatsItem]
                    MemoryCategory_149 [StatsItem]
                    MemoryCategory_150 [StatsItem]
                    MemoryCategory_151 [StatsItem]
                    MemoryCategory_152 [StatsItem]
                    MemoryCategory_153 [StatsItem]
                    MemoryCategory_154 [StatsItem]
                    MemoryCategory_155 [StatsItem]
                    MemoryCategory_156 [StatsItem]
                    MemoryCategory_157 [StatsItem]
                    MemoryCategory_158 [StatsItem]
                    MemoryCategory_159 [StatsItem]
                    MemoryCategory_160 [StatsItem]
                    MemoryCategory_161 [StatsItem]
                    MemoryCategory_162 [StatsItem]
                    MemoryCategory_163 [StatsItem]
                    MemoryCategory_164 [StatsItem]
                    MemoryCategory_165 [StatsItem]
                    MemoryCategory_166 [StatsItem]
                    MemoryCategory_167 [StatsItem]
                    MemoryCategory_168 [StatsItem]
                    MemoryCategory_169 [StatsItem]
                    MemoryCategory_170 [StatsItem]
                    MemoryCategory_171 [StatsItem]
                    MemoryCategory_172 [StatsItem]
                    MemoryCategory_173 [StatsItem]
                    MemoryCategory_174 [StatsItem]
                    MemoryCategory_175 [StatsItem]
                    MemoryCategory_176 [StatsItem]
                    MemoryCategory_177 [StatsItem]
                    MemoryCategory_178 [StatsItem]
                    MemoryCategory_179 [StatsItem]
                    MemoryCategory_180 [StatsItem]
                    MemoryCategory_181 [StatsItem]
                    MemoryCategory_182 [StatsItem]
                    MemoryCategory_183 [StatsItem]
                    MemoryCategory_184 [StatsItem]
                    MemoryCategory_185 [StatsItem]
                    MemoryCategory_186 [StatsItem]
                    MemoryCategory_187 [StatsItem]
                    MemoryCategory_188 [StatsItem]
                    MemoryCategory_189 [StatsItem]
                    MemoryCategory_190 [StatsItem]
                    MemoryCategory_191 [StatsItem]
                    MemoryCategory_192 [StatsItem]
                    MemoryCategory_193 [StatsItem]
                    MemoryCategory_194 [StatsItem]
                    MemoryCategory_195 [StatsItem]
                    MemoryCategory_196 [StatsItem]
                    MemoryCategory_197 [StatsItem]
                    MemoryCategory_198 [StatsItem]
                    MemoryCategory_199 [StatsItem]
                    MemoryCategory_200 [StatsItem]
                    MemoryCategory_201 [StatsItem]
                    MemoryCategory_202 [StatsItem]
                    MemoryCategory_203 [StatsItem]
                    MemoryCategory_204 [StatsItem]
                    MemoryCategory_205 [StatsItem]
                    MemoryCategory_206 [StatsItem]
                    MemoryCategory_207 [StatsItem]
                    MemoryCategory_208 [StatsItem]
                    MemoryCategory_209 [StatsItem]
                    MemoryCategory_210 [StatsItem]
                    MemoryCategory_211 [StatsItem]
                    MemoryCategory_212 [StatsItem]
                    MemoryCategory_213 [StatsItem]
                    MemoryCategory_214 [StatsItem]
                    MemoryCategory_215 [StatsItem]
                    MemoryCategory_216 [StatsItem]
                    MemoryCategory_217 [StatsItem]
                    MemoryCategory_218 [StatsItem]
                    MemoryCategory_219 [StatsItem]
                    MemoryCategory_220 [StatsItem]
                    MemoryCategory_221 [StatsItem]
                    MemoryCategory_222 [StatsItem]
                    MemoryCategory_223 [StatsItem]
                    MemoryCategory_224 [StatsItem]
                    MemoryCategory_225 [StatsItem]
                    MemoryCategory_226 [StatsItem]
                    MemoryCategory_227 [StatsItem]
                    MemoryCategory_228 [StatsItem]
                    MemoryCategory_229 [StatsItem]
                    MemoryCategory_230 [StatsItem]
                    MemoryCategory_231 [StatsItem]
                    MemoryCategory_232 [StatsItem]
                    MemoryCategory_233 [StatsItem]
                    MemoryCategory_234 [StatsItem]
                    MemoryCategory_235 [StatsItem]
                    MemoryCategory_236 [StatsItem]
                    MemoryCategory_237 [StatsItem]
                    MemoryCategory_238 [StatsItem]
                    MemoryCategory_239 [StatsItem]
                    MemoryCategory_240 [StatsItem]
                    MemoryCategory_241 [StatsItem]
                    MemoryCategory_242 [StatsItem]
                    MemoryCategory_243 [StatsItem]
                    MemoryCategory_244 [StatsItem]
                    MemoryCategory_245 [StatsItem]
                    MemoryCategory_246 [StatsItem]
                    MemoryCategory_247 [StatsItem]
                    MemoryCategory_248 [StatsItem]
                    MemoryCategory_249 [StatsItem]
                    MemoryCategory_250 [StatsItem]
                    MemoryCategory_251 [StatsItem]
                    MemoryCategory_252 [StatsItem]
                    MemoryCategory_253 [StatsItem]
                    MemoryCategory_254 [StatsItem]
                    MemoryCategory_255 [StatsItem]
            MaxMemory [StatsItem]
            CPU [StatsItem]
            MaxCPU [StatsItem]
            GPU [StatsItem]
            MaxGPU [StatsItem]
            Ping [StatsItem]
            MaxPing [StatsItem]
            NetworkReceived [StatsItem]
            MaxNetworkReceived [StatsItem]
            NetworkSent [StatsItem]
            MaxNetworkSent [StatsItem]
        RenderBreakdown [StatsItem]
            Undefined [StatsItem]
            Opaque [StatsItem]
            Transparent [StatsItem]
            Terrain [StatsItem]
            Grass [StatsItem]
            UI [StatsItem]
            Decal [StatsItem]
            Cloud [StatsItem]
            GenericPostProcess [StatsItem]
            SSAO [StatsItem]
            DOF [StatsItem]
            Particles [StatsItem]
            Sky [StatsItem]
        Workspace [StatsItem]
            FPS [StatsItem]
            Heartbeat [StatsItem]
            Environment Speed % [StatsItem]
            World [StatsItem]
                Primitives [StatsItem]
                Joints [StatsItem]
                Contacts [StatsItem]
                Non-Anchored Assemblies [StatsItem]
                Sleeping Assemblies [StatsItem]
                Sleep Checking Assemblies [StatsItem]
                Awake Assemblies [StatsItem]
            Contacts [StatsItem]
                CtctStageCtcts [StatsItem]
                SteppingCtcts [StatsItem]
            Kernel [StatsItem]
                Constraints [StatsItem]
            File Operations [StatsItem]
                Total Load Time [StatsItem]
                SyncHttpGet Time [StatsItem]
                XML Load Time [StatsItem]
                Join All Time [StatsItem]
        Sound [StatsItem]
            CPU [StatsItem]
                Dsp [StatsItem]
                Stream [StatsItem]
                Geometry [StatsItem]
                Update [StatsItem]
            ChannelsPlaying [StatsItem]
            Current [StatsItem]
            Max [StatsItem]
            # Sounds [StatsItem]
            # Unused [StatsItem]
        ChangeHistory [StatsItem]
            Data Size [StatsItem]
            Constrained Data Size [StatsItem]
            Stack Size [StatsItem]
        Network [StatsItem]
            Packets Thread [StatsItem]
                Rate [StatsItem]
                Activity [StatsItem]
                Physics Senders [StatsItem]
                Send Buffer Health [StatsItem]
            ServerStatsItem [StatsItem]
                Network Ping [StatsItem]
                Data Ping [RunningAverageItemInt]
                StreamingEnabled [StatsItem]
                Compression [StatsItem]
                Stats [StatsItem]
                    messageDataBytesSentPerSec [StatsItem]
                    messageTotalBytesSentPerSec [StatsItem]
                    messageDataBytesResentPerSec [StatsItem]
                    messagesBytesReceivedPerSec [StatsItem]
                    messagesBytesReceivedAndIgnoredPerSec [StatsItem]
                    bytesSentPerSec [StatsItem]
                    bytesReceivedPerSec [StatsItem]
                    totalMessageBytesPushed [StatsItem]
                    totalMessageBytesSent [StatsItem]
                    totalMessageBytesResent [StatsItem]
                    totalMessagesBytesReceived [StatsItem]
                    totalMessagesBytesReceivedAndIgnored [StatsItem]
                    totalBytesSent [StatsItem]
                    totalBytesReceived [StatsItem]
                    connectionStartTime [StatsItem]
                    outgoingBandwidthLimitBytesPerSecond [StatsItem]
                    isLimitedByOutgoingBandwidthLimit [StatsItem]
                    congestionControlLimitBytesPerSecond [StatsItem]
                    isLimitedByCongestionControl [StatsItem]
                    messageSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    bytesInSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    messagesInResendQueue [StatsItem]
                    bytesInResendQueue [StatsItem]
                    packetlossLastSecond [StatsItem]
                    packetlossTotal [StatsItem]
                    numberOfUnsplitMessages [StatsItem]
                    numberOfSplitMessages [StatsItem]
                    messageDataBytesSentPerSec [StatsItem]
                    messageTotalBytesSentPerSec [StatsItem]
                    messageDataBytesResentPerSec [StatsItem]
                    messagesBytesReceivedPerSec [StatsItem]
                    messagesBytesReceivedAndIgnoredPerSec [StatsItem]
                    bytesSentPerSec [StatsItem]
                    bytesReceivedPerSec [StatsItem]
                    totalMessageBytesPushed [StatsItem]
                    totalMessageBytesSent [StatsItem]
                    totalMessageBytesResent [StatsItem]
                    totalMessagesBytesReceived [StatsItem]
                    totalMessagesBytesReceivedAndIgnored [StatsItem]
                    totalBytesSent [StatsItem]
                    totalBytesReceived [StatsItem]
                    connectionStartTime [StatsItem]
                    outgoingBandwidthLimitBytesPerSecond [StatsItem]
                    isLimitedByOutgoingBandwidthLimit [StatsItem]
                    congestionControlLimitBytesPerSecond [StatsItem]
                    isLimitedByCongestionControl [StatsItem]
                    messageSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    bytesInSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    messagesInResendQueue [StatsItem]
                    bytesInResendQueue [StatsItem]
                    packetlossLastSecond [StatsItem]
                    packetlossTotal [StatsItem]
                    numberOfUnsplitMessages [StatsItem]
                    numberOfSplitMessages [StatsItem]
                Send kBps [StatsItem]
                    MtuSize [StatsItem]
                Send Buffer Health [StatsItem]
                BandwidthExceeded [StatsItem]
                CongestionControlExceeded [StatsItem]
                Receive kBps [StatsItem]
                Packet Queue [StatsItem]
                Sent Data Packets [StatsItem]
                    Size [RunningAverageItemInt]
                    Throttle [StatsItem]
                    Queue Size [StatsItem]
                    Time In Queue [StatsItem]
                    New Items Per Sec [TotalCountTimeIntervalItem]
                    Items Sent Per Sec [TotalCountTimeIntervalItem]
                OutPhysicsDetails [StatsItem]
                    CFrameOnly [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Mechanism [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Translation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Rotation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Velocity [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                InPhysicsDetails [StatsItem]
                    CFrameOnly [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Mechanism [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Translation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Rotation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Velocity [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                DataPingDetails [StatsItem]
                    LQToS [StatsItem]
                    LBcsQ [StatsItem]
                    RakPing [StatsItem]
                    RRakRecvToAppPop [StatsItem]
                    RAppPopToDeserialize [StatsItem]
                    RDeserializeToPBQ [StatsItem]
                    RQToS [StatsItem]
                    RBscQ [StatsItem]
                    LRakRecvToAppPop [StatsItem]
                    LAppPopToSerialize [StatsItem]
                    LDeserializeToProcess [StatsItem]
                    EstTotal [StatsItem]
                    MeasuredTotal [StatsItem]
                    unrelLQToS [StatsItem]
                    unrelLBcsQ [StatsItem]
                    unrelRakPing [StatsItem]
                    unrelRRakRecvToAppPop [StatsItem]
                    unrelRAppPopToDeserialize [StatsItem]
                    unrelRDeserializeToPBQ [StatsItem]
                    unrelRQToS [StatsItem]
                    unrelRBscQ [StatsItem]
                    unrelLRakRecvToAppPop [StatsItem]
                    unrelLAppPopToSerialize [StatsItem]
                    unrelLDeserializeToProcess [StatsItem]
                    unrelEstTotal [StatsItem]
                    unrelMeasuredTotal [StatsItem]
                Send Data Types [StatsItem]
                    InstanceNew [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDelete [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Ping [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Data [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Behavior [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    State [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Appearance [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Team [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Video [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Control [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Events [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDestroy [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                Received Data Types [StatsItem]
                    InstanceNew [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDelete [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Ping [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Data [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Behavior [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    State [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Appearance [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Team [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Video [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Control [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Events [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDestroy [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                Sent Physics Packets [StatsItem]
                    Size [RunningAverageItemInt]
                    Throttle [StatsItem]
                    Smoothed [StatsItem]
                    Items Per Packet [RunningAverageItemInt]
                SentTouchPackets [StatsItem]
                    Size [RunningAverageItemInt]
                    WaitingTouches [RunningAverageItemInt]
                Received Packets [StatsItem]
                Received Data Packets [StatsItem]
                    Queue Size [StatsItem]
                    Instance Size [StatsItem]
                    Waiting Refs [StatsItem]
                    Size [StatsItem]
                Received ISR Packets [StatsItem]
                    Size [StatsItem]
                Received LR Packets [StatsItem]
                    Size [StatsItem]
                Received Physics Packets [StatsItem]
                    Average Lag [StatsItem]
                    Average Buffer Seek [StatsItem]
                    Max Buffer Seek [StatsItem]
                    Wrong Order [StatsItem]
                    Size [StatsItem]
                Sent ISR Packets [StatsItem]
                    Size [StatsItem]
                In ISR Physics Details [StatsItem]
                    Mechanism [StatsItem]
                        Size [StatsItem]
                    CFrameOnly [StatsItem]
                        Size [StatsItem]
                    Translation [StatsItem]
                        Size [StatsItem]
                    Rotation [StatsItem]
                        Size [StatsItem]
                    Velocity [StatsItem]
                        Size [StatsItem]
                Out ISR Physics Details [StatsItem]
                    Mechanism [StatsItem]
                        Size [StatsItem]
                    CFrameOnly [StatsItem]
                        Size [StatsItem]
                    Translation [StatsItem]
                        Size [StatsItem]
                    Rotation [StatsItem]
                        Size [StatsItem]
                    Velocity [StatsItem]
                        Size [StatsItem]
                Sent Cluster Packets [StatsItem]
                    Size [RunningAverageItemInt]
                Received Cluster Packets [StatsItem]
                    Size [StatsItem]
                Received Touch Packets [StatsItem]
                    Size [StatsItem]
                ElapsedTime [StatsItem]
                MaxPacketLoss [StatsItem]
                TotalInDataBW [StatsItem]
                TotalOutDataBW [StatsItem]
                TotalRakIn [StatsItem]
                TotalRakOut [StatsItem]
                OutBufferHealth [StatsItem]
                PropSync [StatsItem]
                    ItemCount [StatsItem]
                    AckCount [StatsItem]
                Received Stream Data [StatsItem]
                    AvgReadTimePerItem [RunningAverageItemDouble]
                    AvgInstancesPerItem [RunningAverageItemDouble]
                    RequestedInstanceAvg [RunningAverageItemInt]
                    PendingRequestCount [StatsItem]
                    GCDistance [StatsItem]
                    NumRegions [StatsItem]
                    CurrentRadius [StatsItem]
                    NumReplicationFoci [StatsItem]
                    NumPrefetches [StatsItem]
                    PlayerPosition [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                    PlayerRegion [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                    LastKnownServerStreamCenter [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                Lr Data [StatsItem]
                    LrBytesRecv [StatsItem]
                    LrSegmentsRecv [StatsItem]
                    LrEstimatedRawRecv [StatsItem]
                    LrEstimatedOptimizedRecv [StatsItem]
                    LrActualPreCompressRecv [StatsItem]
                    LrActualPostCompressRecv [StatsItem]
                    LrAssetsRecv [StatsItem]
                    LrAssetsByDeltaRecv [StatsItem]
                    LrDeltasRecv [StatsItem]
                    LrCancelRecv [StatsItem]
                    LrRemoveRecv [StatsItem]
                    LrCompleteRecv [StatsItem]
                    LrInlineRecv [StatsItem]
                    LrIgnoreRecv [StatsItem]
                    LrHashFail [StatsItem]
                    LrHashCheck [StatsItem]
                    LrMemCountRecv [StatsItem]
                    LrMemEstBytesRecv [StatsItem]
        Luau [StatsItem]
            disabled [StatsItem]
            threads [StatsItem]
            AverageGcTime [StatsItem]
        FrameRateManager [StatsItem]
            DeviceFeatureLevel [StatsItem]
            DeviceShadingLanguage [StatsItem]
            AverageQualityLevel [StatsItem]
            AutoQuality [StatsItem]
            NumberOfSettles [StatsItem]
            AverageSwitches [StatsItem]
            FramebufferWidth [StatsItem]
            FramebufferHeight [StatsItem]
            Batches [StatsItem]
            Indices [StatsItem]
            MaterialChanges [StatsItem]
            VideoMemoryInMB [StatsItem]
            AverageFPS [StatsItem]
            FrameTimeVariance [StatsItem]
            FrameSpikeCount [StatsItem]
            RenderAverage [StatsItem]
            PrepareAverage [StatsItem]
            PerformAverage [StatsItem]
            AveragePresent [StatsItem]
            AverageGPU [StatsItem]
            RenderThreadAverage [StatsItem]
            TotalFrameWallAverage [StatsItem]
            PerformVariance [StatsItem]
            PresentVariance [StatsItem]
            GpuVariance [StatsItem]
            MsFrame0 [StatsItem]
            MsFrame1 [StatsItem]
            MsFrame2 [StatsItem]
            MsFrame3 [StatsItem]
            MsFrame4 [StatsItem]
            MsFrame5 [StatsItem]
            MsFrame6 [StatsItem]
            MsFrame7 [StatsItem]
            MsFrame8 [StatsItem]
            MsFrame9 [StatsItem]
            MsFrame10 [StatsItem]
            MsFrame11 [StatsItem]
        Render [StatsItem]
            Memory [StatsItem]
                Video [StatsItem]
    TimerService [TimerService]
    CollectionService [CollectionService]
    SoundService [SoundService]
    VideoCaptureService [VideoCaptureService]
    LogService [LogService]
    MicroProfilerService [MicroProfilerService]
    ContentProvider [ContentProvider]
    KeyframeSequenceProvider [KeyframeSequenceProvider]
    AnimationClipProvider [AnimationClipProvider]
    Chat [Chat]
    MarketplaceService [MarketplaceService]
    Players [Players]
        hydrazx9 [Player]
            PlayerScripts [PlayerScripts]
            Backpack [Backpack]
    PointsService [PointsService]
    NotificationService [NotificationService]
    ReplicatedFirst [ReplicatedFirst]
    HttpRbxApiService [HttpRbxApiService]
    TweenService [TweenService]
    MaterialService [MaterialService]
    TextChatService [TextChatService]
        BubbleChatConfiguration [BubbleChatConfiguration]
            ImageLabel [ImageLabel]
            UICorner [UICorner]
            UIGradient [UIGradient]
            UIPadding [UIPadding]
        ChannelTabsConfiguration [ChannelTabsConfiguration]
        ChatInputBarConfiguration [ChatInputBarConfiguration]
        ChatWindowConfiguration [ChatWindowConfiguration]
    TextService [TextService]
    PermissionsService [PermissionsService]
    SharedTableRegistry [SharedTableRegistry]
    StarterPlayer [StarterPlayer]
        StarterCharacterScripts [StarterCharacterScripts]
        StarterPlayerScripts [StarterPlayerScripts]
            ClientMain [LocalScript]
                ----- SOURCE -----
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)

Registry.AutoLoadConfigs(ReplicatedStorage:WaitForChild("Configs"))
Net.Init()

local Client = script.Parent:WaitForChild("Client")
local Render = require(Client.ClientRenderEngine)
local Placement = require(Client.PlacementController)
local ShopUI = require(Client.ShopUI)

Render.Init()
Placement.Init(Render)
ShopUI.Init(Placement, Render)

local okChat, errChat = pcall(function()
	require(Client.ChatCommands).Init()
end)
if not okChat then
	warn("[ChatCommands] " .. tostring(errChat))
end

Net.Request():InvokeServer("ClientReady")

                ----- END SOURCE -----
            LocalScript [LocalScript]
                ----- SOURCE -----
local StarterGui = game:GetService("StarterGui")

-- Desativa completamente a barra de inventário (Backpack) da tela do jogador
StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Backpack, false)
                ----- END SOURCE -----
            Client [Folder]
                Animators [ModuleScript]
                    ----- SOURCE -----
--[[
	Animators: escolhe o animador de cada unidade pelo config. O ClientRenderEngine só fala com esta fábrica.
	Animation = { Mode = "Procedural" }   -- padrão: poses por nome de junta (UnitAnimator)
	Animation = { Mode = "Rig", ... }     -- animações reais do Animation Editor (RigAnimator)
	Os dois têm o mesmo contrato: :SetPivot(cf) :SetSpeed(s) :Trigger(nome, aoSoltar) :Kill() :Step(dt) e .DeathTime
]]
local UnitAnimator = require(script.Parent.UnitAnimator)
local RigAnimator = require(script.Parent.RigAnimator)

local Animators = {}

function Animators.IsRig(cfg)
	return cfg.Animation ~= nil and cfg.Animation.Mode == "Rig"
end

function Animators.new(model, role, cfg)
	if not model:IsA("Model") then
		return nil
	end
	if Animators.IsRig(cfg) then
		return RigAnimator.new(model, role, cfg)
	end
	return UnitAnimator.new(model, role, cfg)
end

return Animators

                    ----- END SOURCE -----
                ClientRenderEngine [ModuleScript]
                    ----- SOURCE -----
--[[
	ClientRenderEngine: 100% do visual roda aqui. Nenhum inimigo existe como Instance no servidor.
	- Inimigo: posição = path:PositionAt(min(D + S * (agora - T), comprimento)), com agora = workspace:GetServerTimeNow().
	  O servidor só manda âncora (D,T) + velocidade (S) no spawn e quando a velocidade muda (slow/freeze).
	- Partes simples são movidas em lote com BulkMoveTo (1 chamada/frame).
	- Projétil: lerp de origem -> posição PREVISTA do inimigo em T1 (hora do impacto, vinda do servidor).
	Assets opcionais: ReplicatedStorage.Assets.Models.{Towers,Enemies,Projectiles}.<ModelName> (também vale Assets.<Pasta> direto).
	  Torres/inimigos = Models com PrimaryPart (torre: pivô na base; inimigo: pivô no centro da altura de Visual.Size).
	  Projétil = Model com PrimaryPart apontando p/ -Z; Visual.Projectile.ModelName escolhe o modelo (Attribute BaseSize = escala 1).
	  Modelos com juntas são animados pelo UnitAnimator (procedural, funciona com partes ancoradas).
]]
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local RunService = game:GetService("RunService")
local TweenService = game:GetService("TweenService")
local Debris = game:GetService("Debris")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local EventBus = require(Shared.EventBus)
local Net = require(Shared.Net)
local PathUtil = require(Shared.PathUtil)
local Animators = require(script.Parent.Animators)

local Render = {
	Enemies = {},
	Towers = {},
	Map = nil,
	State = nil,
	Data = { Coins = 0 },
	Loadout = {},
	Events = EventBus.new(), -- "TowerChanged"(id) · "TowerRemoved"(id) · "GameState"(state) · "PlayerData"(data)
	Folder = nil,
	TowersFolder = nil,
}

local enemiesFolder, fxFolder
local projectiles = {}
local dying = {} -- modelos animados tocando a animação de morte
local pendingSpawns = {}
local bulkParts, bulkCFrames = {}, {}

local function serverNow()
	return workspace:GetServerTimeNow()
end

local function findIn(root, kind, name)
	local folder = root and root:FindFirstChild(kind)
	return folder and folder:FindFirstChild(name)
end

local function cloneAsset(kind, name, canQuery, rig)
	if not name then
		return nil
	end
	local assets = ReplicatedStorage:FindFirstChild("Assets")
	local models = assets and assets:FindFirstChild("Models")
	local template = findIn(models, kind, name) or findIn(assets, kind, name)
	if not template then
		return nil
	end
	local clone = template:Clone()
	-- rig = animações reais: só a PrimaryPart fica ancorada; o resto segue pelas juntas (Motor6D/Weld).
	-- procedural: tudo ancorado (o UnitAnimator move as peças em lote).
	local root = rig and clone:IsA("Model") and clone.PrimaryPart or nil
	local parts = clone:GetDescendants()
	table.insert(parts, clone)
	for _, d in ipairs(parts) do
		if d:IsA("BasePart") then
			d.CanCollide = false
			d.CanQuery = canQuery
			if root then
				d.Anchored = d == root
				d.Massless = true
			else
				d.Anchored = true
			end
		end
	end
	return clone
end

local function makePart(size, color, canQuery)
	local part = Instance.new("Part")
	part.Anchored = true
	part.CanCollide = false
	part.CanTouch = false
	part.CanQuery = canQuery
	part.Size = size
	part.Color = color
	part.Material = Enum.Material.SmoothPlastic
	return part
end

-- ---------------------------------------------------------------- anel de alcance (usado por UI/placement)
function Render.MakeRing(color)
	local ring = Instance.new("Part")
	ring.Shape = Enum.PartType.Cylinder
	ring.Anchored = true
	ring.CanCollide = false
	ring.CanTouch = false
	ring.CanQuery = false
	ring.Material = Enum.Material.Neon
	ring.Transparency = 0.8
	ring.Color = color or Color3.fromRGB(255, 255, 255)
	return ring
end

function Render.PlaceRing(ring, pos, range)
	ring.Size = Vector3.new(0.2, range * 2, range * 2)
	ring.CFrame = CFrame.new(pos + Vector3.new(0, 0.15, 0)) * CFrame.Angles(0, 0, math.rad(90))
end

function Render.TowerCost(def)
	local m = Render.Map and Render.Map.Config.Multipliers
	return math.ceil(def.Cost * (m and m.TowerCost or 1))
end

function Render.PickTower(inst)
	local cur = inst
	while cur and cur ~= Render.TowersFolder do
		local id = cur:GetAttribute("TDTowerId")
		if id then
			return id
		end
		cur = cur.Parent
	end
	return nil
end

-- ---------------------------------------------------------------- inimigos
local function adornee(r)
	if r.IsPart then
		return r.Inst
	end
	return r.Inst.PrimaryPart or r.Inst:FindFirstChildWhichIsA("BasePart", true)
end

local function updateBar(r)
	if r.Hp >= r.MaxHp and not r.Bar then
		return
	end
	if not r.Bar then
		local gui = Instance.new("BillboardGui")
		gui.Size = UDim2.fromOffset(60, 8)
		gui.StudsOffset = Vector3.new(0, r.BarY, 0)
		gui.AlwaysOnTop = true
		gui.Adornee = adornee(r)
		local back = Instance.new("Frame")
		back.Size = UDim2.fromScale(1, 1)
		back.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
		back.BorderSizePixel = 0
		back.Parent = gui
		local fill = Instance.new("Frame")
		fill.Name = "Fill"
		fill.Size = UDim2.fromScale(1, 1)
		fill.BackgroundColor3 = Color3.fromRGB(90, 220, 90)
		fill.BorderSizePixel = 0
		fill.Parent = back
		gui.Parent = r.Inst
		r.Bar = gui
	end
	r.Bar.Frame.Fill.Size = UDim2.fromScale(math.clamp(r.Hp / r.MaxHp, 0, 1), 1)
end

local function applyTint(r)
	local color = r.BaseColor
	for _, c in pairs(r.Tints) do
		color = c
		break
	end
	if r.IsPart then
		r.Inst.Color = color
	elseif r.TintParts then
		local tinted = next(r.Tints) ~= nil
		for part, original in pairs(r.TintParts) do
			part.Color = tinted and color or original
		end
	end
end

local function newEnemy(p)
	if Render.Enemies[p.Id] then
		return
	end
	local cfg = Registry.Of("Enemies"):Get(p.Cfg)
	local path = Render.Map and Render.Map.Paths[p.Path]
	if not cfg or not path then
		return
	end
	local vis = cfg.Visual or {}
	local size = vis.Size or Vector3.new(2, 3, 2)
	local inst = cloneAsset("Enemies", cfg.ModelName, false, Animators.IsRig(cfg))
	if not inst then
		inst = makePart(size, vis.Color or Color3.fromRGB(200, 60, 60), false)
	end
	inst.Parent = enemiesFolder
	local isPart = inst:IsA("BasePart")
	local anim = not isPart and inst:IsA("Model") and Animators.new(inst, "Enemy", cfg) or nil
	local tintParts
	if not isPart then
		tintParts = {}
		for _, d in ipairs(inst:GetDescendants()) do
			if d:IsA("BasePart") and d.Transparency < 1 then
				tintParts[d] = d.Color
			end
		end
	end
	local r = {
		Id = p.Id,
		Cfg = cfg,
		Path = path,
		Inst = inst,
		IsPart = isPart,
		D = p.D,
		T = p.T,
		S = p.S,
		Hp = p.Hp,
		MaxHp = p.MaxHp,
		YOffset = size.Y / 2,
		BarY = (isPart and size.Y / 2 or inst:GetAttribute("BarHeight") or size.Y / 2) + 1.5,
		Anim = anim,
		TintParts = tintParts,
		Tints = {},
		BaseColor = isPart and inst.Color or Color3.new(1, 1, 1),
		LastPos = path:PositionAt(p.D),
	}
	Render.Enemies[p.Id] = r
	updateBar(r)
end

local function removeEnemy(id, reason)
	local r = Render.Enemies[id]
	if not r then
		return
	end
	Render.Enemies[id] = nil
	if r.Bar then
		r.Bar:Destroy()
	end
	if reason == "Killed" and r.IsPart then
		TweenService:Create(r.Inst, TweenInfo.new(0.25), { Transparency = 1, Size = r.Inst.Size * 0.3 }):Play()
		Debris:AddItem(r.Inst, 0.3)
	elseif reason == "Killed" and r.Anim then
		r.Anim:Kill()
		table.insert(dying, { Anim = r.Anim, Inst = r.Inst, Age = 0 })
	else
		r.Inst:Destroy()
	end
end

-- ---------------------------------------------------------------- torres
local function newTower(p)
	local cfg = Registry.Of("Towers"):Get(p.Cfg)
	if not cfg or Render.Towers[p.Id] then
		return
	end
	local vis = cfg.Visual or {}
	local size = vis.Size or Vector3.new(3, 4, 3)
	local inst = cloneAsset("Towers", cfg.ModelName, true, Animators.IsRig(cfg))
	local anim, muzzle
	if inst then
		inst:PivotTo(CFrame.new(p.Pos))
		if inst:IsA("Model") then
			anim = Animators.new(inst, "Tower", cfg)
			muzzle = inst:FindFirstChild("Muzzle", true)
			if muzzle and not muzzle:IsA("Attachment") then
				muzzle = nil
			end
		end
	else
		inst = makePart(size, vis.Color or Color3.fromRGB(200, 200, 200), true)
		inst.Position = p.Pos + Vector3.new(0, size.Y / 2, 0)
	end
	inst:SetAttribute("TDTowerId", p.Id)
	inst.Parent = Render.TowersFolder
	Render.Towers[p.Id] = {
		Id = p.Id,
		Cfg = cfg,
		Inst = inst,
		Position = p.Pos,
		Owner = p.Owner,
		Range = p.Range,
		Splash = p.Splash,
		Tiers = p.Tiers,
		Mode = p.Mode,
		Invested = p.Invested,
		Damage = p.Damage,
		Interval = p.Interval,
		Height = size.Y * 0.8,
		Anim = anim,
		Muzzle = muzzle,
	}
	Render.Events:Fire("TowerChanged", p.Id)
end

local function tierSum(tiers)
	local n = 0
	for _, v in pairs(tiers) do
		n += v
	end
	return n
end

local function updateTower(p)
	local t = Render.Towers[p.Id]
	if not t then
		return
	end
	local upgraded = tierSum(p.Tiers) > tierSum(t.Tiers)
	t.Range, t.Splash, t.Tiers, t.Mode, t.Invested = p.Range, p.Splash, p.Tiers, p.Mode, p.Invested
	t.Damage, t.Interval = p.Damage, p.Interval
	if upgraded and t.Anim then
		t.Anim:Trigger("Upgrade")
	end
	Render.Events:Fire("TowerChanged", p.Id)
end

local function removeTower(id)
	local t = Render.Towers[id]
	if not t then
		return
	end
	Render.Towers[id] = nil
	t.Inst:Destroy()
	Render.Events:Fire("TowerRemoved", id)
end

-- ---------------------------------------------------------------- projéteis / fx
local function impactFx(pos, radius, color)
	local fx = Instance.new("Part")
	fx.Shape = Enum.PartType.Ball
	fx.Anchored = true
	fx.CanCollide = false
	fx.CanQuery = false
	fx.CanTouch = false
	fx.Material = Enum.Material.Neon
	fx.Transparency = 0.4
	fx.Color = color
	fx.Size = Vector3.one
	fx.Position = pos
	fx.Parent = fxFolder
	TweenService
		:Create(fx, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {
			Size = Vector3.one * radius * 2,
			Transparency = 1,
		})
		:Play()
	Debris:AddItem(fx, 0.35)
end

local function placeProjectile(pr, pos)
	if pr.IsAsset then
		local d = pos - pr.LastPos
		if d.Magnitude > 1e-3 then
			pr.Dir = d.Unit
		end
		pr.LastPos = pos
		pr.Part:PivotTo(CFrame.lookAt(pos, pos + pr.Dir))
	else
		pr.Part.Position = pos
	end
end

-- impacto de projétil com modelo próprio: emissores com atributo EmitCount soltam uma rajada, rastros param,
-- o corpo some (exceto peças com atributo KeepOnImpact) e o modelo fica ImpactLifetime segundos para os efeitos terminarem
local function projectileImpact(pr)
	local inst = pr.Part
	if not pr.IsAsset then
		inst:Destroy()
		return
	end
	inst:PivotTo(CFrame.lookAt(pr.Target, pr.Target + pr.Dir))
	for _, d in ipairs(inst:GetDescendants()) do
		if d:IsA("ParticleEmitter") then
			d.Enabled = false
			local count = d:GetAttribute("EmitCount")
			if count then
				d:Emit(count)
			end
		elseif d:IsA("Trail") then
			d.Enabled = false
		elseif d:IsA("BasePart") and not d:GetAttribute("KeepOnImpact") then
			d.Transparency = 1
		end
	end
	Debris:AddItem(inst, pr.Cfg.ImpactLifetime or 1.5)
end

local function fireTower(f)
	local tw = Render.Towers[f.Tower]
	if not tw then
		return
	end
	local en = Render.Enemies[f.Enemy]
	local pv = tw.Cfg.Visual and tw.Cfg.Visual.Projectile or {}

	if en then
		local look = Vector3.new(en.LastPos.X, tw.Position.Y, en.LastPos.Z)
		if look ~= tw.Position then
			local rot = CFrame.lookAt(tw.Position, look)
			if tw.Anim then
				tw.Anim:SetPivot(rot)
			else
				tw.Inst:PivotTo(rot)
			end
		end
	end

	local fallback = en and en.LastPos or tw.Position
	local launched = false

	-- o projétil sai no instante de "soltar" da animação (procedural: ReleaseTime; rig: marcador "Release")
	local function launch()
		if launched or not Render.Towers[tw.Id] then
			return
		end
		launched = true
		if tw.Anim then
			tw.Anim:Step(0) -- aplica a pose atual: o Muzzle precisa estar no lugar certo
		end
		local now = serverNow()
		local cur = Render.Enemies[f.Enemy]
		local origin = tw.Muzzle and tw.Muzzle.WorldPosition or (tw.Position + Vector3.new(0, tw.Height, 0))
		local target = cur and cur.LastPos or fallback
		local flat = target - origin
		local dir = flat.Magnitude > 1e-3 and flat.Unit or Vector3.new(0, 0, -1)

		local part = pv.ModelName and cloneAsset("Projectiles", pv.ModelName, false)
		local isAsset = part ~= nil
		if isAsset then
			local base = part:GetAttribute("BaseSize")
			if base and pv.Size and part:IsA("Model") then
				part:ScaleTo(pv.Size / base)
			end
			part:PivotTo(CFrame.lookAt(origin, origin + dir))
			part.Parent = fxFolder
		else
			part = Instance.new("Part")
			part.Shape = Enum.PartType.Ball
			part.Anchored = true
			part.CanCollide = false
			part.CanQuery = false
			part.CanTouch = false
			part.Material = Enum.Material.Neon
			part.Color = pv.Color or Color3.fromRGB(255, 255, 255)
			part.Size = Vector3.one * (pv.Size or 0.7)
			part.Position = origin
			part.Parent = fxFolder
		end
		table.insert(projectiles, {
			Part = part,
			IsAsset = isAsset,
			Cfg = pv,
			LastPos = origin,
			Dir = dir,
			From = origin,
			EnemyId = f.Enemy,
			T0 = now,
			T1 = math.max(f.T1, now + 0.1), -- o acerto é decidido pelo servidor (T1); mínimo de 0.1s visível
			Arc = pv.Arc or 0,
			Splash = tw.Splash,
			Color = pv.Color or Color3.fromRGB(255, 255, 255),
			Target = target,
		})
	end

	if tw.Anim then
		tw.Anim:Trigger("Attack", launch)
	else
		launch()
	end
end

-- ---------------------------------------------------------------- loop de render
local function step(dt)
	local t = serverNow()

	local n = 0
	for _, r in pairs(Render.Enemies) do
		local d = r.D + r.S * (t - r.T)
		local len = r.Path.Length
		if d > len then
			d = len
		elseif d < 0 then
			d = 0
		end
		local pos = r.Path:PositionAt(d)
		r.LastPos = pos
		local center = pos + Vector3.new(0, r.YOffset, 0)
		local cf = CFrame.lookAt(center, center + r.Path:DirectionAt(d))
		if r.IsPart then
			n += 1
			bulkParts[n] = r.Inst
			bulkCFrames[n] = cf
		elseif r.Anim then
			r.Anim:SetPivot(cf)
			r.Anim:SetSpeed(r.S)
			r.Anim:Step(dt)
		else
			r.Inst:PivotTo(cf)
		end
	end
	for i = #bulkParts, n + 1, -1 do
		bulkParts[i] = nil
		bulkCFrames[i] = nil
	end
	if n > 0 then
		workspace:BulkMoveTo(bulkParts, bulkCFrames, Enum.BulkMoveMode.FireCFrameChanged)
	end

	for _, tw in pairs(Render.Towers) do
		if tw.Anim then
			tw.Anim:Step(dt)
		end
	end
	for i = #dying, 1, -1 do
		local d = dying[i]
		d.Age += dt
		d.Anim:Step(dt)
		if d.Age >= (d.Anim.DeathTime or 0.5) then
			d.Inst:Destroy()
			table.remove(dying, i)
		end
	end

	for i = #projectiles, 1, -1 do
		local pr = projectiles[i]
		local en = Render.Enemies[pr.EnemyId]
		if en then
			local d = math.min(en.D + en.S * (pr.T1 - en.T), en.Path.Length)
			pr.Target = en.Path:PositionAt(d) + Vector3.new(0, en.YOffset, 0)
		end
		local alpha = (t - pr.T0) / (pr.T1 - pr.T0)
		if alpha >= 1 then
			if pr.Splash > 0 then
				impactFx(pr.Target, pr.Splash, pr.Color)
			end
			projectileImpact(pr)
			table.remove(projectiles, i)
		else
			alpha = math.max(alpha, 0)
			local pos = pr.From:Lerp(pr.Target, alpha)
			if pr.Arc > 0 then
				pos += Vector3.new(0, math.sin(math.pi * alpha) * pr.Arc, 0)
			end
			placeProjectile(pr, pos)
		end
	end
end

-- ---------------------------------------------------------------- rede
local function setMap(mapId)
	for _, r in pairs(Render.Enemies) do
		r.Inst:Destroy()
	end
	for _, tw in pairs(Render.Towers) do
		tw.Inst:Destroy()
	end
	for _, pr in ipairs(projectiles) do
		pr.Part:Destroy()
	end
	for _, d in ipairs(dying) do
		d.Inst:Destroy()
	end
	table.clear(dying)
	table.clear(Render.Enemies)
	table.clear(Render.Towers)
	table.clear(projectiles)

	local cfg = Registry.Of("Maps"):Get(mapId)
	if not cfg then
		Render.Map = nil
		return
	end
	local paths = {}
	for id, points in pairs(cfg.Paths) do
		paths[id] = PathUtil.new(points)
	end
	Render.Map = { Id = mapId, Config = cfg, Paths = paths }
	for _, p in ipairs(pendingSpawns) do
		newEnemy(p)
	end
	table.clear(pendingSpawns)
end

local function onDelta(p)
	for _, e in ipairs(p.EnemySpawned) do
		if Render.Map then
			newEnemy(e)
		else
			table.insert(pendingSpawns, e) -- mapa ainda não chegou (entrada tardia)
		end
	end
	for _, m in ipairs(p.EnemyMotion) do
		local r = Render.Enemies[m.Id]
		if r then
			r.D, r.T, r.S = m.D, m.T, m.S
		end
	end
	for _, h in ipairs(p.EnemyHealth) do
		local r = Render.Enemies[h.Id]
		if r then
			r.Hp = h.Hp
			updateBar(r)
		end
	end
	for _, s in ipairs(p.Status) do
		local r = Render.Enemies[s.Enemy]
		if r then
			local def = Registry.Of("StatusEffects"):Get(s.Effect)
			r.Tints[s.Effect] = s.On and def and def.Visual and def.Visual.Color or nil
			applyTint(r)
		end
	end
	for _, tp in ipairs(p.TowerPlaced) do
		newTower(tp)
	end
	for _, tu in ipairs(p.TowerUpdated) do
		updateTower(tu)
	end
	for _, f in ipairs(p.TowerFired) do
		fireTower(f)
	end
	for _, id in ipairs(p.TowerRemoved) do
		removeTower(id.Id)
	end
	for _, e in ipairs(p.EnemyRemoved) do
		removeEnemy(e.Id, e.Reason)
	end
end

function Render.Init()
	Render.Folder = Instance.new("Folder")
	Render.Folder.Name = "TDClient"
	Render.Folder.Parent = workspace
	Render.TowersFolder = Instance.new("Folder")
	Render.TowersFolder.Name = "Towers"
	Render.TowersFolder.Parent = Render.Folder
	enemiesFolder = Instance.new("Folder")
	enemiesFolder.Name = "Enemies"
	enemiesFolder.Parent = Render.Folder
	fxFolder = Instance.new("Folder")
	fxFolder.Name = "FX"
	fxFolder.Parent = Render.Folder

	Net.Event("GameState").OnClientEvent:Connect(function(state)
		Render.State = state
		if not Render.Map or Render.Map.Id ~= state.MapId then
			setMap(state.MapId)
		end
		Render.Events:Fire("GameState", state)
	end)
	Net.Event("PlayerData").OnClientEvent:Connect(function(data)
		Render.Data = data
		Render.Events:Fire("PlayerData", data)
	end)
	Net.Event("Loadout").OnClientEvent:Connect(function(list)
		Render.Loadout = list
		Render.Events:Fire("Loadout", list)
	end)
	Net.Event("Delta").OnClientEvent:Connect(onDelta)
	RunService.RenderStepped:Connect(step)
end

return Render

                    ----- END SOURCE -----
                PlacementController [ModuleScript]
                    ----- SOURCE -----
--[[
	PlacementController: fantasma da torre (verde/vermelho), confirmação por clique/toque e seleção de torres.
	O cliente só PREVÊ com PlacementRules; quem decide é o servidor (Request "PlaceTower").
]]
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)
local PlacementRules = require(Shared.PlacementRules)

local GREEN, RED = Color3.fromRGB(90, 220, 110), Color3.fromRGB(230, 80, 80)

local Placement = { Active = nil, OnSelect = nil, OnResult = nil }
local Render
local ghost, ring, conn
local activeRange = 0
local pointer = nil -- só usado no toque
local currentPos, currentValid, currentReason = nil, false, nil

function Placement.Cancel()
	Placement.Active = nil
	currentPos = nil
	if conn then
		conn:Disconnect()
		conn = nil
	end
	if ghost then
		ghost:Destroy()
		ghost = nil
	end
	if ring then
		ring:Destroy()
		ring = nil
	end
end

local function update()
	if not Placement.Active or not Render.Map then
		return
	end
	local camera = workspace.CurrentCamera
	local loc = pointer or UserInputService:GetMouseLocation()
	local ray = camera:ViewportPointToRay(loc.X, loc.Y)
	local params = RaycastParams.new()
	params.FilterType = Enum.RaycastFilterType.Exclude
	params.FilterDescendantsInstances = { Render.Folder, Players.LocalPlayer.Character }
	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
	if not hit then
		currentPos = nil
		ghost.Transparency = 1
		return
	end
	local y = Render.Map.Config.GroundY or 0
	currentPos = Vector3.new(hit.Position.X, y, hit.Position.Z)
	currentValid, currentReason = PlacementRules.Check(Render.Map, currentPos, Render.Towers)
	ghost.Position = currentPos + Vector3.new(0, ghost.Size.Y / 2, 0)
	ghost.Transparency = 0.45
	local color = currentValid and GREEN or RED
	ghost.Color = color
	ring.Color = color
	if activeRange > 0 then
		ring.Transparency = 0.8
		Render.PlaceRing(ring, currentPos, activeRange)
	else
		ring.Transparency = 1
	end
end

function Placement.Begin(towerId)
	Placement.Cancel()
	local def = Registry.Of("Towers"):Get(towerId)
	if not def then
		return
	end
	Placement.Active = towerId
	if Placement.OnSelect then
		Placement.OnSelect(nil)
	end
	local vis = def.Visual or {}
	ghost = Instance.new("Part")
	ghost.Anchored = true
	ghost.CanCollide = false
	ghost.CanQuery = false
	ghost.CanTouch = false
	ghost.Size = vis.Size or Vector3.new(3, 4, 3)
	ghost.Transparency = 1
	ghost.Parent = Render.Folder
	ring = Render.MakeRing()
	ring.Parent = Render.Folder
	activeRange = def.Stats and def.Stats.Range or 0
	conn = RunService.RenderStepped:Connect(update)
end

function Placement.Toggle(towerId)
	if Placement.Active == towerId then
		Placement.Cancel()
	else
		Placement.Begin(towerId)
	end
end

local function confirm()
	if not Placement.Active or not currentPos then
		return
	end
	if not currentValid then
		if Placement.OnResult then
			Placement.OnResult({ Ok = false, Error = currentReason })
		end
		return
	end
	local id, pos = Placement.Active, currentPos
	if not UserInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
		Placement.Cancel() -- segure Shift para colocar várias
	end
	local res = Net.Request():InvokeServer("PlaceTower", { TowerId = id, Position = pos })
	if Placement.OnResult then
		Placement.OnResult(res)
	end
end

local function selectAt(loc)
	local ray = workspace.CurrentCamera:ViewportPointToRay(loc.X, loc.Y)
	local params = RaycastParams.new()
	params.FilterType = Enum.RaycastFilterType.Include
	params.FilterDescendantsInstances = { Render.TowersFolder }
	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
	local id = hit and Render.PickTower(hit.Instance) or nil
	if Placement.OnSelect then
		Placement.OnSelect(id)
	end
end

function Placement.Init(renderEngine)
	Render = renderEngine

	UserInputService.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.Touch then
			pointer = Vector2.new(input.Position.X, input.Position.Y)
		end
	end)

	UserInputService.InputBegan:Connect(function(input, processed)
		if processed then
			return
		end
		local t = input.UserInputType
		if t == Enum.UserInputType.MouseButton1 then
			pointer = nil
			if Placement.Active then
				confirm()
			else
				selectAt(UserInputService:GetMouseLocation())
			end
		elseif t == Enum.UserInputType.MouseButton2 or (t == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.Escape) then
			Placement.Cancel()
		elseif t == Enum.UserInputType.Touch then
			pointer = Vector2.new(input.Position.X, input.Position.Y)
			if not Placement.Active then
				selectAt(pointer)
			end
		end
	end)

	-- toque: arraste para posicionar, solte para confirmar
	UserInputService.InputEnded:Connect(function(input, processed)
		if not processed and input.UserInputType == Enum.UserInputType.Touch and Placement.Active then
			confirm()
		end
	end)
end

return Placement

                    ----- END SOURCE -----
                RigAnimator [ModuleScript]
                    ----- SOURCE -----
--[[
	RigAnimator: mesmo contrato do UnitAnimator, mas toca AnimationTracks reais (Animation Editor).
	O ClientRenderEngine ancora só a PrimaryPart quando Animation.Mode = "Rig"; o resto do modelo segue pelas juntas.
	AnimationController e Animator são criados se o modelo não tiver.

	Animation = {
		Mode = "Rig",
		Tracks = { Idle = "rbxassetid://...", Walk = "...", Attack = "...", Upgrade = "...", Death = "..." },  -- todos opcionais
		WalkSpeed = 9,        -- studs/s em que o Walk toca a 1x (padrão: Speed do config do inimigo)
		ReleaseMarker = true, -- KeyframeMarker "Release" no Attack = instante em que o projétil sai
		ReleaseTime = 0.3,    -- alternativa sem marcador: segundos após o início do Attack (0 = sai na hora)
	}
]]
local RigAnimator = {}
RigAnimator.__index = RigAnimator

local PRIORITY = {
	Idle = Enum.AnimationPriority.Idle,
	Walk = Enum.AnimationPriority.Movement,
	Attack = Enum.AnimationPriority.Action,
	Upgrade = Enum.AnimationPriority.Action2,
	Death = Enum.AnimationPriority.Action4,
}
local LOOPED = { Idle = true, Walk = true }

function RigAnimator.new(model, role, cfg)
	if not model.PrimaryPart then
		return nil
	end
	local a = cfg.Animation or {}
	return setmetatable({
		Model = model,
		Role = role,
		Config = a,
		Tracks = {},
		Loaded = false,
		Pivot = model:GetPivot(),
		Speed = 0,
		WalkRef = a.WalkSpeed or cfg.Speed or 8,
		ReleaseTime = a.ReleaseTime or 0,
		DeathTime = 0.15,
		PendingRelease = nil,
		ReleaseAt = 0,
		Time = 0,
		Dead = false,
	}, RigAnimator)
end

-- carrega as animações só quando o modelo já está no workspace (o Animator exige isso)
function RigAnimator:_load()
	if self.Loaded or not self.Model:IsDescendantOf(workspace) then
		return
	end
	self.Loaded = true
	local controller = self.Model:FindFirstChildWhichIsA("AnimationController", true)
		or self.Model:FindFirstChildWhichIsA("Humanoid", true)
	if not controller then
		controller = Instance.new("AnimationController")
		controller.Parent = self.Model
	end
	local animator = controller:FindFirstChildWhichIsA("Animator")
	if not animator then
		animator = Instance.new("Animator")
		animator.Parent = controller
	end
	for name, id in pairs(self.Config.Tracks or {}) do
		local anim = Instance.new("Animation")
		anim.AnimationId = id
		local ok, track = pcall(function()
			return animator:LoadAnimation(anim)
		end)
		if ok and track then
			track.Priority = PRIORITY[name] or Enum.AnimationPriority.Action
			track.Looped = LOOPED[name] == true
			self.Tracks[name] = track
		else
			warn(("[RigAnimator] %s: não carregou a animação '%s'"):format(self.Model.Name, name))
		end
	end
	if self.Tracks.Idle then
		self.Tracks.Idle:Play()
	end
	if self.Tracks.Walk then
		self.Tracks.Walk:Play(0.1, 1, 0) -- começa parado; SetSpeed liga o ciclo
	end
	if self.Tracks.Death then
		self.DeathTime = math.max(self.Tracks.Death.Length, 0.15)
	end
end

function RigAnimator:SetPivot(cf)
	self.Pivot = cf
end

function RigAnimator:SetSpeed(speed)
	self.Speed = speed
	local walk = self.Tracks.Walk
	if walk and not self.Dead then
		walk:AdjustSpeed(speed > 0.05 and speed / self.WalkRef or 0) -- 0 = pose congelada
	end
end

function RigAnimator:_release()
	local fn = self.PendingRelease
	if fn then
		self.PendingRelease = nil
		fn()
	end
end

function RigAnimator:Trigger(name, onRelease)
	self:_load()
	local track = self.Tracks[name]
	if track then
		track:Play(0.05, 1, 1)
	end
	if name ~= "Attack" or not onRelease then
		return
	end
	self:_release() -- solta o disparo anterior, se ainda estava pendente
	if not track then
		onRelease()
	elseif self.Config.ReleaseMarker then
		self.PendingRelease = onRelease
		self.ReleaseAt = self.Time + 1 -- segurança se o marcador não existir na animação
		local conn
		conn = track:GetMarkerReachedSignal("Release"):Connect(function()
			conn:Disconnect()
			self:_release()
		end)
	elseif self.ReleaseTime > 0 then
		self.PendingRelease = onRelease
		self.ReleaseAt = self.Time + self.ReleaseTime
	else
		onRelease()
	end
end

function RigAnimator:Kill()
	if self.Dead then
		return
	end
	self.Dead = true
	self:_load()
	self:_release()
	for name, track in pairs(self.Tracks) do
		if name ~= "Death" then
			track:Stop(0.05)
		end
	end
	if self.Tracks.Death then
		self.Tracks.Death:Play(0.05, 1, 1)
	end
end

function RigAnimator:Step(dt)
	self.Time += dt
	self:_load()
	self.Model:PivotTo(self.Pivot)
	if self.PendingRelease and self.Time >= self.ReleaseAt then
		self:_release()
	end
end

return RigAnimator

                    ----- END SOURCE -----
                ShopUI [ModuleScript]
                    ----- SOURCE -----
--[[
	ShopUI (Factory): NENHUM botão é desenhado à mão.
	- Loja: um clone do template (ReplicatedStorage.Template2) por entrada de TowersConfig, dentro de MainUI.Units.Background
	- Painel da torre selecionada: upgrades/targeting/venda gerados de cfg.Upgrades e cfg.Targeting
	- HUD: estado, onda, vidas, moedas e contagem regressiva
]]
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)
local UnitCard = require(script.Parent.UnitCard)
local UnitPanel = require(script.Parent.UnitPanel)

local ERRORS = {
	NotEnoughCoins = "Moedas insuficientes",
	NotEquipped = "Equipe essa unidade no inventário",
	LoadoutFull = "Slots cheios: desequipe uma unidade",
	CannotBuildNow = "Não é possível construir agora",
	OutOfBounds = "Fora da área do mapa",
	TooCloseToPath = "Muito perto do caminho",
	TooCloseToTower = "Muito perto de outra torre",
	LimitReached = "Limite dessa torre atingido",
	MaxTier = "Nível máximo",
	PathLocked = "Caminho bloqueado por outro upgrade",
	NotYourTower = "Essa torre não é sua",
	RateLimited = "Calma! Muitas ações",
}
local STATE_NAMES = {
	WaitingForPlayers = "Aguardando jogadores",
	Intermission = "Intervalo",
	WaveActive = "Onda em andamento",
	GameOver = "Fim de jogo",
	Victory = "Vitória!",
}

local TEMPLATE_NAME = "Template2" -- troque para "Template1" quando quiser cards com ícone

local ShopUI = {}

local function new(class, props, parent)
	local inst = Instance.new(class)
	for k, v in pairs(props) do
		inst[k] = v
	end
	inst.Parent = parent
	return inst
end

function ShopUI.Init(Placement, Render)
	local player = Players.LocalPlayer
	local playerGui = player:WaitForChild("PlayerGui")
	local gui = new("ScreenGui", { Name = "TDUI", ResetOnSpawn = false }, playerGui)

	-- ---------------------------------------------------------- HUD + toast
	local hud = new("TextLabel", {
		AnchorPoint = Vector2.new(0.5, 0),
		Position = UDim2.new(0.5, 0, 0, 8),
		Size = UDim2.fromOffset(520, 34),
		BackgroundColor3 = Color3.fromRGB(20, 22, 28),
		BackgroundTransparency = 0.2,
		TextColor3 = Color3.new(1, 1, 1),
		Font = Enum.Font.GothamMedium,
		TextSize = 16,
		Text = "Conectando...",
	}, gui)
	new("UICorner", { CornerRadius = UDim.new(0, 8) }, hud)

	local toastLabel = new("TextLabel", {
		AnchorPoint = Vector2.new(0.5, 0),
		Position = UDim2.new(0.5, 0, 0, 48),
		Size = UDim2.fromOffset(360, 30),
		BackgroundColor3 = Color3.fromRGB(150, 50, 50),
		TextColor3 = Color3.new(1, 1, 1),
		Font = Enum.Font.GothamMedium,
		TextSize = 15,
		Visible = false,
	}, gui)
	new("UICorner", { CornerRadius = UDim.new(0, 8) }, toastLabel)
	local toastToken = 0
	local function toast(text)
		toastToken += 1
		local mine = toastToken
		toastLabel.Text = text
		toastLabel.Visible = true
		task.delay(2.5, function()
			if toastToken == mine then
				toastLabel.Visible = false
			end
		end)
	end
	local function explain(res)
		if res and not res.Ok then
			toast(ERRORS[res.Error] or tostring(res.Error))
		end
	end
	Placement.OnResult = explain

	local function refreshHud()
		local s = Render.State
		if not s then
			return
		end
		local left = ""
		if s.EndsAt and s.EndsAt > 0 then
			left = (" | %ds"):format(math.max(0, math.ceil(s.EndsAt - workspace:GetServerTimeNow())))
		end
		local waveText = s.VictoryWave and s.VictoryWave > 0 and ("%d/%d"):format(s.Wave, s.VictoryWave) or tostring(s.Wave)
		hud.Text = ("%s | Onda %s | Vidas %d/%d | Moedas %d%s"):format(
			STATE_NAMES[s.State] or s.State,
			waveText,
			s.Lives,
			s.MaxLives,
			Render.Data.Coins or 0,
			left
		)
	end
	task.spawn(function()
		while gui.Parent do
			refreshHud()
			task.wait(0.25)
		end
	end)

	-- ---------------------------------------------------------- loja (equipadas) + inventário (todas)
	local template = ReplicatedStorage:WaitForChild(TEMPLATE_NAME)
	local mainUI = playerGui:WaitForChild("MainUI")
	local shopBackground = mainUI:WaitForChild("Units"):WaitForChild("Background") -- Frame Units: só as equipadas
	local invUnits = mainUI:WaitForChild("Inventory"):WaitForChild("Units") -- ScrollingFrame Units: todas

	if not shopBackground:FindFirstChildWhichIsA("UIListLayout") and not shopBackground:FindFirstChildWhichIsA("UIGridLayout") then
		new("UIListLayout", {
			FillDirection = Enum.FillDirection.Horizontal,
			Padding = UDim.new(0, 8),
			SortOrder = Enum.SortOrder.LayoutOrder,
		}, shopBackground)
	end

	local WHITE, RED, GREEN = Color3.new(1, 1, 1), Color3.fromRGB(255, 120, 120), Color3.fromRGB(120, 255, 140)
	local shopCards, invCards = {}, {}

	local function makeCard(def, parent, order)
		local button = template:Clone()
		button.Name = def.Id
		button.LayoutOrder = order
		button.Visible = true
		button.Parent = parent
		if button:IsA("ImageButton") and def.Icon and def.Icon ~= "" then
			button.Image = def.Icon
		end
		return button
	end

	local function refreshShop()
		local coins = Render.Data.Coins or 0
		for _, c in pairs(shopCards) do
			local cost = Render.TowerCost(c.Def)
			if c.Button:IsA("TextButton") then
				c.Button.Text = ("%s\n$%d"):format(c.Def.DisplayName or c.Def.Id, cost)
				c.Button.TextColor3 = coins >= cost and WHITE or RED
			end
		end
	end

	local function refreshInventory()
		for id, c in pairs(invCards) do
			local eq = table.find(Render.Loadout, id) ~= nil
			if c.Button:IsA("TextButton") then
				c.Button.Text = ("%s\n%s"):format(c.Def.DisplayName or id, eq and "[Equipado]" or "Equipar")
				c.Button.TextColor3 = eq and GREEN or WHITE
			end
		end
	end

	local function rebuildShop()
		for _, c in pairs(shopCards) do
			c.Button:Destroy()
		end
		table.clear(shopCards)
		local towers = Registry.Of("Towers")
		for i, id in ipairs(Render.Loadout) do
			local def = towers:Get(id)
			if def then
				local button = UnitCard.Make(def, shopBackground, i, Render) or makeCard(def, shopBackground, i)
				button.Activated:Connect(function()
					Placement.Toggle(id)
				end)
				shopCards[id] = { Button = button, Def = def }
			end
		end
		refreshShop()
	end

	-- inventário: um card por torre existente (torres novas em TowersConfig aparecem sozinhas)
	Registry.Of("Towers"):OnRegister(function(def)
		local button = makeCard(def, invUnits, def.Cost)
		button.Activated:Connect(function()
			explain(Net.Request():InvokeServer("ToggleEquip", { TowerId = def.Id }))
		end)
		invCards[def.Id] = { Button = button, Def = def }
		refreshInventory()
	end)

	Render.Events:Connect("Loadout", function(list)
		if Placement.Active and not table.find(list, Placement.Active) then
			Placement.Cancel()
		end
		rebuildShop()
		refreshInventory()
	end)
	Render.Events:Connect("PlayerData", refreshShop)
	Render.Events:Connect("GameState", refreshShop)
	rebuildShop()
	 [trimmed]  -  Editar
  18:17:13.021   ▶ > local HttpService = game:GetService("HttpService")

local output = {}

local function add(text)
	table.insert(output, text)
end

local function indent(depth)
	return string.rep("    ", depth)
end

local function scan(instance, depth)
	local className = instance.ClassName
	local name = instance.Name

	add(indent(depth) .. name .. " [" .. className .. "]")

	-- Salva o código dos scripts
	if instance:IsA("Script")
		or instance:IsA("LocalScript")
		or instance:IsA("ModuleScript") then

		add(indent(depth + 1) .. "----- SOURCE -----")
		add(instance.Source)
		add(indent(depth + 1) .. "----- END SOURCE -----")
	end

	for _, child in ipairs(instance:GetChildren()) do
		scan(child, depth + 1)
	end
end

add("===== ROBLOX PROJECT MAP =====")
add("Gerado em: " .. os.date("%Y-%m-%d %H:%M:%S"))
add("")

scan(game, 0)

local result = table.concat(output, "\n")

-- Tenta copiar para o clipboard do Studio
pcall(function()
	setclipboard(result)
end)

print("========================================")
print("PROJETO EXPORTADO!")
print("Tamanho: " .. #result .. " caracteres")
print("========================================")
print(result) (x2)  -  Studio
  18:17:13.069  ========================================  -  Editar
  18:17:13.069  PROJETO EXPORTADO!  -  Editar
  18:17:13.069  Tamanho: 442723 caracteres  -  Editar
  18:17:13.069  ========================================  -  Editar
  18:17:13.072  ===== ROBLOX PROJECT MAP =====
Gerado em: 2026-10-02 18:17:13

Place1 [DataModel]
    Workspace [Workspace]
        SunRays [SunRaysEffect]
        ColorCorrection [ColorCorrectionEffect]
        Blur [BlurEffect]
        Bloom [BloomEffect]
            Atmosphere [Atmosphere]
            ArcHandles [ArcHandles]
        TowerDefenseMap [Folder]
            Waypoints [Folder]
            Path [Folder]
            TowerSpots [Folder]
            Decor [Folder]
        Terrain [Terrain]
        Camera [Camera]
    Run Service [RunService]
    GuiService [GuiService]
        ScreenshotHud [ScreenshotHud]
    Stats [Stats]
        PerformanceStats [StatsItem]
            Memory [StatsItem]
                CoreMemory [StatsItem]
                    default [StatsItem]
                    staticinit [StatsItem]
                    http/batch [StatsItem]
                    lua/web-cache [StatsItem]
                    contentProvider/asyncDecryption [StatsItem]
                    internal/DataModelPatch [StatsItem]
                    render/prepare/physics [StatsItem]
                    physics/step [StatsItem]
                    physics/buffers [StatsItem]
                    physics/mechanism [StatsItem]
                    physics/assembly [StatsItem]
                    experienceStateCaptureService [StatsItem]
                    gui/TextLayout [StatsItem]
                    render/fonts [StatsItem]
                    gui/HarfBuzz [StatsItem]
                    gui/FreeType [StatsItem]
                    fontProvider/loading [StatsItem]
                    gui/FontData [StatsItem]
                    internal/localizationTable [StatsItem]
                    internal/localization [StatsItem]
                    ads/AdGui [StatsItem]
                    internal/MarketplaceService [StatsItem]
                    geometry/EditableMesh/Geometry [StatsItem]
                    geometry/EditableMesh/SpatialCache [StatsItem]
                    geometry/EditableMesh/GpuAssigned [StatsItem]
                    physics/bullet [StatsItem]
                    network/netAssetSerialized [StatsItem]
                    network/netAssetRegistries [StatsItem]
                    network/netAssetProxy [StatsItem]
                    AppCore/GuidRegistry [StatsItem]
                    instance/fullname [StatsItem]
                    internal/TaskScheduler [StatsItem]
                    profiler [StatsItem]
                    internal/RbxThread [StatsItem]
                    localstorage [StatsItem]
                    telemetry/analytics [StatsItem]
                    telemetry [StatsItem]
                    http/client [StatsItem]
                    http/curl [StatsItem]
                    http/requestcallback [StatsItem]
                    openssl [StatsItem]
                    http/wslay [StatsItem]
                    SQLite [StatsItem]
                    telemetry/fields_container [StatsItem]
                    telemetry/counter [StatsItem]
                    telemetry/event [StatsItem]
                    telemetry/stat [StatsItem]
                    telemetry/v2_try_cut_and_send [StatsItem]
                    gui/FreeTypeDT [StatsItem]
                    AssetProvider/total [StatsItem]
                    sound/default [StatsItem]
                    render/copy [StatsItem]
                    render/vertexlayout [StatsItem]
                    render/shader [StatsItem]
                    render/swapchain [StatsItem]
                    raknet/raknet [StatsItem]
                    raknet/startup [StatsItem]
                    raknet/recv-buffer [StatsItem]
                    raknet/buffered-commands [StatsItem]
                    raknet/packet-return [StatsItem]
                    raknet/tx-outgoing [StatsItem]
                    raknet/tx-datagram [StatsItem]
                    raknet/rx-ordered-heap [StatsItem]
                    raknet/rx-split-reassembly [StatsItem]
                    raknet/rx-output [StatsItem]
                    raknet/rx-handling [StatsItem]
                    raknet/datagram-history [StatsItem]
                    raknet/ack-nak [StatsItem]
                    RbxTransport/Io/sys [StatsItem]
                    RbxTransport/Io/libuv [StatsItem]
                    video/encoding/hardware [StatsItem]
                    video/default [StatsItem]
                    video/packet [StatsItem]
                    video/codec [StatsItem]
                    video/texture [StatsItem]
                    internal/PerformanceControl [StatsItem]
                    RbxTransport/RtcIo/Local [StatsItem]
                    RbxTransport/RtcIo/Remote/Rx [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptConnection [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptWtSession [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptH3 [StatsItem]
                    RbxTransport/RtcIo/Remote/NewAppConnection [StatsItem]
                    RbxTransport/RtcIo/Remote/Handshake [StatsItem]
                    RbxTransport/RtcIo/Remote/StreamAccepted [StatsItem]
                    RbxTransport/RtcIo/Remote/StreamClose [StatsItem]
                    RbxTransport/RtcIo/Remote/Ack [StatsItem]
                    RbxTransport/RtcIo/Remote/FlowControl [StatsItem]
                    RbxTransport/RtcIo/Remote/Loss [StatsItem]
                    RbxTransport/RtcIo/Remote/ConnClose [StatsItem]
                    RbxTransport/RtcIo/Remote/AppControl [StatsItem]
                    RbxTransport/RtcIo/Remote/AppFin [StatsItem]
                    RbxTransport/RtcIo/Remote/OpenUnreliableChannel [StatsItem]
                    physics/broadphase [StatsItem]
                    physics/midphase [StatsItem]
                    internal/ixp [StatsItem]
                    video/realtime_media [StatsItem]
                    video/capture_engine [StatsItem]
                    physics/aerodynamics/mesh [StatsItem]
                    physics/aerodynamics/integrator [StatsItem]
                    physics/aerodynamics/linearintegrator [StatsItem]
                    physics/aerodynamics/cpintegrator [StatsItem]
                    physics/aerodynamics/shinterpolator [StatsItem]
                    physics/aerodynamics/reducedmesh [StatsItem]
                    internal/ScriptContext [StatsItem]
                    lua/bytecode [StatsItem]
                    lua/codegen [StatsItem]
                    lua/codegenpages [StatsItem]
                    internal/RuntimeScriptService [StatsItem]
                    CoreScriptTelemetry [StatsItem]
                    physics/solver/buffers [StatsItem]
                    physics/solver/sleep [StatsItem]
                    physics/solver/ldl [StatsItem]
                    physics/solver/misc [StatsItem]
                    internal/DataModelGenericJob [StatsItem]
                    studio/undo [StatsItem]
                    internal/InstanceStitchingHandler [StatsItem]
                    CollectionService [StatsItem]
                    internal/ChatService [StatsItem]
                    internal/GlobalSettings [StatsItem]
                    render/terrain/heightmapImporter [StatsItem]
                    geometry/EditableImage [StatsItem]
                    collections/collection [StatsItem]
                    collections/watcher [StatsItem]
                    performanceStats [StatsItem]
                    collections/proximity [StatsItem]
                    internal/AuroraService/InputFrame [StatsItem]
                    internal/AuroraService/HashBuffer [StatsItem]
                    internal/AuroraService/Prediction [StatsItem]
                    internal/Workspace [StatsItem]
                    internal/RemoteFunction [StatsItem]
                    internal/LogService [StatsItem]
                    render/lightgrid [StatsItem]
                    render/system [StatsItem]
                    render/bindworkspace [StatsItem]
                    render/adorn [StatsItem]
                    render/perform/statistics [StatsItem]
                    render/prepare [StatsItem]
                    render/prepare/adorn [StatsItem]
                    render/perform [StatsItem]
                    render/perform/adorn [StatsItem]
                    render/glyphaatlas/ugc [StatsItem]
                    render/glyphatlas/core [StatsItem]
                    render/terrain/grass/async [StatsItem]
                    render/terrain/grass [StatsItem]
                    render/prepare/terrain/grass [StatsItem]
                    render/target [StatsItem]
                    render/target/pooled [StatsItem]
                    render/perform/zpre [StatsItem]
                    render/clouds [StatsItem]
                    render/ssao [StatsItem]
                    render/glow [StatsItem]
                    render/sunrays [StatsItem]
                    render/dof [StatsItem]
                    render/blur [StatsItem]
                    render/colorCorrection [StatsItem]
                    render/highlight [StatsItem]
                    render/RtPool [StatsItem]
                    render/mainRts [StatsItem]
                    render/ui [StatsItem]
                    render/shadowmap [StatsItem]
                    render/perform/shadowmap [StatsItem]
                    render/shadowmap/depthcache [StatsItem]
                    render/perform/materialMisc [StatsItem]
                    render/perform/materialGc [StatsItem]
                    render/material/failsafe [StatsItem]
                    render/perform/terrain [StatsItem]
                    render/prepare/terrain [StatsItem]
                    render/instanceglob [StatsItem]
                    render/gpu_geom_mgr [StatsItem]
                    dynamic/mesh [StatsItem]
                    dynamic/texture [StatsItem]
                    render/envmap [StatsItem]
                    render/material/misc [StatsItem]
                    render/prepare/tc [StatsItem]
                    render/prepare/sceneUpdater [StatsItem]
                    render/prepare/parts [StatsItem]
                    render/prepare/megaCluster [StatsItem]
                    render/prepare/attachments [StatsItem]
                    render/swocc [StatsItem]
                    render/perform/textureAtlasInsert [StatsItem]
                    render/meshManager/async [StatsItem]
                    textureRef [StatsItem]
                    render/texture/local [StatsItem]
                    render/texture/fallback [StatsItem]
                    render/texture/loading [StatsItem]
                    render/perform/textureGc [StatsItem]
                    render/prepare/textureManager [StatsItem]
                    render/perform/textureManager [StatsItem]
                    render/sky [StatsItem]
                    render/advsky [StatsItem]
                    render/perform/cullableScene [StatsItem]
                    render/prepare/motionBuffer [StatsItem]
                    render/geometryGenerator [StatsItem]
                    render/perform/scratchFB [StatsItem]
                    render/prepare/lightObject [StatsItem]
                    render/terrain/async/chunkGen [StatsItem]
                    render/perform/terrain/occlusionGen [StatsItem]
                    render/viewportFrames [StatsItem]
                    render/prepare/lightGridChunk [StatsItem]
                    render/perform/lightGrid [StatsItem]
                    render/fastCluster/prepareSkinning [StatsItem]
                    render/fastCluster/skinningReserve [StatsItem]
                    render/prepare/beamNode [StatsItem]
                    render/prepare/customEmitter [StatsItem]
                    render/pipeline [StatsItem]
                    render/pipeline/updates [StatsItem]
                    render/meshFetcherDecomp [StatsItem]
                    network/compresspacket [StatsItem]
                    network/decompresspacket [StatsItem]
                    network/ISR/Property [StatsItem]
                    network/groupManager [StatsItem]
                    network/ISR/Replicator [StatsItem]
                    network/setManager [StatsItem]
                    internal/CSGDictionary [StatsItem]
                    network/HeatmapQueryService [StatsItem]
                    internal/HttpRbxApiService [StatsItem]
                    internal/StarterPlayer [StatsItem]
                    datastore/cache [StatsItem]
                    animation/skeleton_watcher [StatsItem]
                    wrap/layeredDeformer [StatsItem]
                    internal/Humanoid [StatsItem]
                    temporaryCageMeshProvider/save [StatsItem]
                    wrap/hsr [StatsItem]
                    animation/skeleton [StatsItem]
                    wrap/deformMeshProvider [StatsItem]
                    gui/Uncategorized [StatsItem]
                    gui/UIQuadTree [StatsItem]
                    languageServices/async [StatsItem]
                    languageServices/generic [StatsItem]
                    languageServices/shadow [StatsItem]
                    network/streamingReplication [StatsItem]
                    network/streamJob [StatsItem]
                    network/replicationCoalescing [StatsItem]
                    network/deserializestep [StatsItem]
                    network/onreceive [StatsItem]
                    network/sharedQueue [StatsItem]
                    network/megaReplicationData [StatsItem]
                    network/modelCompleteness [StatsItem]
                    network/refPropTracking [StatsItem]
                    network/replicator [StatsItem]
                    internal/InputReplicator [StatsItem]
                    network/gcJob [StatsItem]
                    network/instanceObjectManager [StatsItem]
                    network/server [StatsItem]
                    network/streamingSolver [StatsItem]
                    network/streamingObserver [StatsItem]
                    network/replicatedInstances [StatsItem]
                    network/deferredtrees [StatsItem]
                    network/newinstanceitem [StatsItem]
                    network/streamDataItem [StatsItem]
                    network/ISR [StatsItem]
                    network/ISR/Connection [StatsItem]
                    network/ISR/Prioritization [StatsItem]
                    network/touchReplication [StatsItem]
                    network/replicationDataCache [StatsItem]
                    network/replicationDataCachePendingList [StatsItem]
                    network/ISR/groupMan [StatsItem]
                    network/physicsSenderCache [StatsItem]
                    sound/voice [StatsItem]
                    voice/webrtc [StatsItem]
                    voice/operations [StatsItem]
                    voice/audio [StatsItem]
                    sound/async [StatsItem]
                    sound/acoustics [StatsItem]
                    AudioWiring [StatsItem]
                    instance/AttributesAndTags [StatsItem]
                    internal/BaseThreadPool [StatsItem]
                    AssetProvider/state [StatsItem]
                    AssetProvider/other [StatsItem]
                    render/vertexstreamer [StatsItem]
                    friendsCalling/bringUp [StatsItem]
                PlaceMemory [StatsItem]
                    HttpCache [StatsItem]
                    Instances [StatsItem]
                    Signals [StatsItem]
                    LuaHeap [StatsItem]
                    Script [StatsItem]
                    PhysicsCollision [StatsItem]
                    BaseParts [StatsItem]
                    GraphicsSolidModels [StatsItem]
                    GraphicsHSR [StatsItem]
                    GraphicsMeshParts [StatsItem]
                    GraphicsParticles [StatsItem]
                    GraphicsParts [StatsItem]
                    GraphicsSpatialHash [StatsItem]
                    GraphicsTerrain [StatsItem]
                    GraphicsTexture [StatsItem]
                    GraphicsTextureCharacter [StatsItem]
                    Sounds [StatsItem]
                    TerrainVoxels [StatsItem]
                    TerrainPhysics [StatsItem]
                    Gui [StatsItem]
                    Animation [StatsItem]
                    Navigation [StatsItem]
                    GeometryCSG [StatsItem]
                    GraphicsSlimModels [StatsItem]
                UntrackedMemory [StatsItem]
                PlaceScriptMemory [StatsItem]
                    MemoryCategory_0 [StatsItem]
                    MemoryCategory_1 [StatsItem]
                    MemoryCategory_2 [StatsItem]
                    MemoryCategory_3 [StatsItem]
                    MemoryCategory_4 [StatsItem]
                    MemoryCategory_5 [StatsItem]
                    MemoryCategory_6 [StatsItem]
                    MemoryCategory_7 [StatsItem]
                    MemoryCategory_8 [StatsItem]
                    MemoryCategory_9 [StatsItem]
                    MemoryCategory_10 [StatsItem]
                    MemoryCategory_11 [StatsItem]
                    MemoryCategory_12 [StatsItem]
                    MemoryCategory_13 [StatsItem]
                    MemoryCategory_14 [StatsItem]
                    MemoryCategory_15 [StatsItem]
                    MemoryCategory_16 [StatsItem]
                    MemoryCategory_17 [StatsItem]
                    MemoryCategory_18 [StatsItem]
                    MemoryCategory_19 [StatsItem]
                    MemoryCategory_20 [StatsItem]
                    MemoryCategory_21 [StatsItem]
                    MemoryCategory_22 [StatsItem]
                    MemoryCategory_23 [StatsItem]
                    MemoryCategory_24 [StatsItem]
                    MemoryCategory_25 [StatsItem]
                    MemoryCategory_26 [StatsItem]
                    MemoryCategory_27 [StatsItem]
                    MemoryCategory_28 [StatsItem]
                    MemoryCategory_29 [StatsItem]
                    MemoryCategory_30 [StatsItem]
                    MemoryCategory_31 [StatsItem]
                    MemoryCategory_32 [StatsItem]
                    MemoryCategory_33 [StatsItem]
                    MemoryCategory_34 [StatsItem]
                    MemoryCategory_35 [StatsItem]
                    MemoryCategory_36 [StatsItem]
                    MemoryCategory_37 [StatsItem]
                    MemoryCategory_38 [StatsItem]
                    MemoryCategory_39 [StatsItem]
                    MemoryCategory_40 [StatsItem]
                    MemoryCategory_41 [StatsItem]
                    MemoryCategory_42 [StatsItem]
                    MemoryCategory_43 [StatsItem]
                    MemoryCategory_44 [StatsItem]
                    MemoryCategory_45 [StatsItem]
                    MemoryCategory_46 [StatsItem]
                    MemoryCategory_47 [StatsItem]
                    MemoryCategory_48 [StatsItem]
                    MemoryCategory_49 [StatsItem]
                    MemoryCategory_50 [StatsItem]
                    MemoryCategory_51 [StatsItem]
                    MemoryCategory_52 [StatsItem]
                    MemoryCategory_53 [StatsItem]
                    MemoryCategory_54 [StatsItem]
                    MemoryCategory_55 [StatsItem]
                    MemoryCategory_56 [StatsItem]
                    MemoryCategory_57 [StatsItem]
                    MemoryCategory_58 [StatsItem]
                    MemoryCategory_59 [StatsItem]
                    MemoryCategory_60 [StatsItem]
                    MemoryCategory_61 [StatsItem]
                    MemoryCategory_62 [StatsItem]
                    MemoryCategory_63 [StatsItem]
                    MemoryCategory_64 [StatsItem]
                    MemoryCategory_65 [StatsItem]
                    MemoryCategory_66 [StatsItem]
                    MemoryCategory_67 [StatsItem]
                    MemoryCategory_68 [StatsItem]
                    MemoryCategory_69 [StatsItem]
                    MemoryCategory_70 [StatsItem]
                    MemoryCategory_71 [StatsItem]
                    MemoryCategory_72 [StatsItem]
                    MemoryCategory_73 [StatsItem]
                    MemoryCategory_74 [StatsItem]
                    MemoryCategory_75 [StatsItem]
                    MemoryCategory_76 [StatsItem]
                    MemoryCategory_77 [StatsItem]
                    MemoryCategory_78 [StatsItem]
                    MemoryCategory_79 [StatsItem]
                    MemoryCategory_80 [StatsItem]
                    MemoryCategory_81 [StatsItem]
                    MemoryCategory_82 [StatsItem]
                    MemoryCategory_83 [StatsItem]
                    MemoryCategory_84 [StatsItem]
                    MemoryCategory_85 [StatsItem]
                    MemoryCategory_86 [StatsItem]
                    MemoryCategory_87 [StatsItem]
                    MemoryCategory_88 [StatsItem]
                    MemoryCategory_89 [StatsItem]
                    MemoryCategory_90 [StatsItem]
                    MemoryCategory_91 [StatsItem]
                    MemoryCategory_92 [StatsItem]
                    MemoryCategory_93 [StatsItem]
                    MemoryCategory_94 [StatsItem]
                    MemoryCategory_95 [StatsItem]
                    MemoryCategory_96 [StatsItem]
                    MemoryCategory_97 [StatsItem]
                    MemoryCategory_98 [StatsItem]
                    MemoryCategory_99 [StatsItem]
                    MemoryCategory_100 [StatsItem]
                    MemoryCategory_101 [StatsItem]
                    MemoryCategory_102 [StatsItem]
                    MemoryCategory_103 [StatsItem]
                    MemoryCategory_104 [StatsItem]
                    MemoryCategory_105 [StatsItem]
                    MemoryCategory_106 [StatsItem]
                    MemoryCategory_107 [StatsItem]
                    MemoryCategory_108 [StatsItem]
                    MemoryCategory_109 [StatsItem]
                    MemoryCategory_110 [StatsItem]
                    MemoryCategory_111 [StatsItem]
                    MemoryCategory_112 [StatsItem]
                    MemoryCategory_113 [StatsItem]
                    MemoryCategory_114 [StatsItem]
                    MemoryCategory_115 [StatsItem]
                    MemoryCategory_116 [StatsItem]
                    MemoryCategory_117 [StatsItem]
                    MemoryCategory_118 [StatsItem]
                    MemoryCategory_119 [StatsItem]
                    MemoryCategory_120 [StatsItem]
                    MemoryCategory_121 [StatsItem]
                    MemoryCategory_122 [StatsItem]
                    MemoryCategory_123 [StatsItem]
                    MemoryCategory_124 [StatsItem]
                    MemoryCategory_125 [StatsItem]
                    MemoryCategory_126 [StatsItem]
                    MemoryCategory_127 [StatsItem]
                    MemoryCategory_128 [StatsItem]
                    MemoryCategory_129 [StatsItem]
                    MemoryCategory_130 [StatsItem]
                    MemoryCategory_131 [StatsItem]
                    MemoryCategory_132 [StatsItem]
                    MemoryCategory_133 [StatsItem]
                    MemoryCategory_134 [StatsItem]
                    MemoryCategory_135 [StatsItem]
                    MemoryCategory_136 [StatsItem]
                    MemoryCategory_137 [StatsItem]
                    MemoryCategory_138 [StatsItem]
                    MemoryCategory_139 [StatsItem]
                    MemoryCategory_140 [StatsItem]
                    MemoryCategory_141 [StatsItem]
                    MemoryCategory_142 [StatsItem]
                    MemoryCategory_143 [StatsItem]
                    MemoryCategory_144 [StatsItem]
                    MemoryCategory_145 [StatsItem]
                    MemoryCategory_146 [StatsItem]
                    MemoryCategory_147 [StatsItem]
                    MemoryCategory_148 [StatsItem]
                    MemoryCategory_149 [StatsItem]
                    MemoryCategory_150 [StatsItem]
                    MemoryCategory_151 [StatsItem]
                    MemoryCategory_152 [StatsItem]
                    MemoryCategory_153 [StatsItem]
                    MemoryCategory_154 [StatsItem]
                    MemoryCategory_155 [StatsItem]
                    MemoryCategory_156 [StatsItem]
                    MemoryCategory_157 [StatsItem]
                    MemoryCategory_158 [StatsItem]
                    MemoryCategory_159 [StatsItem]
                    MemoryCategory_160 [StatsItem]
                    MemoryCategory_161 [StatsItem]
                    MemoryCategory_162 [StatsItem]
                    MemoryCategory_163 [StatsItem]
                    MemoryCategory_164 [StatsItem]
                    MemoryCategory_165 [StatsItem]
                    MemoryCategory_166 [StatsItem]
                    MemoryCategory_167 [StatsItem]
                    MemoryCategory_168 [StatsItem]
                    MemoryCategory_169 [StatsItem]
                    MemoryCategory_170 [StatsItem]
                    MemoryCategory_171 [StatsItem]
                    MemoryCategory_172 [StatsItem]
                    MemoryCategory_173 [StatsItem]
                    MemoryCategory_174 [StatsItem]
                    MemoryCategory_175 [StatsItem]
                    MemoryCategory_176 [StatsItem]
                    MemoryCategory_177 [StatsItem]
                    MemoryCategory_178 [StatsItem]
                    MemoryCategory_179 [StatsItem]
                    MemoryCategory_180 [StatsItem]
                    MemoryCategory_181 [StatsItem]
                    MemoryCategory_182 [StatsItem]
                    MemoryCategory_183 [StatsItem]
                    MemoryCategory_184 [StatsItem]
                    MemoryCategory_185 [StatsItem]
                    MemoryCategory_186 [StatsItem]
                    MemoryCategory_187 [StatsItem]
                    MemoryCategory_188 [StatsItem]
                    MemoryCategory_189 [StatsItem]
                    MemoryCategory_190 [StatsItem]
                    MemoryCategory_191 [StatsItem]
                    MemoryCategory_192 [StatsItem]
                    MemoryCategory_193 [StatsItem]
                    MemoryCategory_194 [StatsItem]
                    MemoryCategory_195 [StatsItem]
                    MemoryCategory_196 [StatsItem]
                    MemoryCategory_197 [StatsItem]
                    MemoryCategory_198 [StatsItem]
                    MemoryCategory_199 [StatsItem]
                    MemoryCategory_200 [StatsItem]
                    MemoryCategory_201 [StatsItem]
                    MemoryCategory_202 [StatsItem]
                    MemoryCategory_203 [StatsItem]
                    MemoryCategory_204 [StatsItem]
                    MemoryCategory_205 [StatsItem]
                    MemoryCategory_206 [StatsItem]
                    MemoryCategory_207 [StatsItem]
                    MemoryCategory_208 [StatsItem]
                    MemoryCategory_209 [StatsItem]
                    MemoryCategory_210 [StatsItem]
                    MemoryCategory_211 [StatsItem]
                    MemoryCategory_212 [StatsItem]
                    MemoryCategory_213 [StatsItem]
                    MemoryCategory_214 [StatsItem]
                    MemoryCategory_215 [StatsItem]
                    MemoryCategory_216 [StatsItem]
                    MemoryCategory_217 [StatsItem]
                    MemoryCategory_218 [StatsItem]
                    MemoryCategory_219 [StatsItem]
                    MemoryCategory_220 [StatsItem]
                    MemoryCategory_221 [StatsItem]
                    MemoryCategory_222 [StatsItem]
                    MemoryCategory_223 [StatsItem]
                    MemoryCategory_224 [StatsItem]
                    MemoryCategory_225 [StatsItem]
                    MemoryCategory_226 [StatsItem]
                    MemoryCategory_227 [StatsItem]
                    MemoryCategory_228 [StatsItem]
                    MemoryCategory_229 [StatsItem]
                    MemoryCategory_230 [StatsItem]
                    MemoryCategory_231 [StatsItem]
                    MemoryCategory_232 [StatsItem]
                    MemoryCategory_233 [StatsItem]
                    MemoryCategory_234 [StatsItem]
                    MemoryCategory_235 [StatsItem]
                    MemoryCategory_236 [StatsItem]
                    MemoryCategory_237 [StatsItem]
                    MemoryCategory_238 [StatsItem]
                    MemoryCategory_239 [StatsItem]
                    MemoryCategory_240 [StatsItem]
                    MemoryCategory_241 [StatsItem]
                    MemoryCategory_242 [StatsItem]
                    MemoryCategory_243 [StatsItem]
                    MemoryCategory_244 [StatsItem]
                    MemoryCategory_245 [StatsItem]
                    MemoryCategory_246 [StatsItem]
                    MemoryCategory_247 [StatsItem]
                    MemoryCategory_248 [StatsItem]
                    MemoryCategory_249 [StatsItem]
                    MemoryCategory_250 [StatsItem]
                    MemoryCategory_251 [StatsItem]
                    MemoryCategory_252 [StatsItem]
                    MemoryCategory_253 [StatsItem]
                    MemoryCategory_254 [StatsItem]
                    MemoryCategory_255 [StatsItem]
                CoreScriptMemory [StatsItem]
                    MemoryCategory_0 [StatsItem]
                    MemoryCategory_1 [StatsItem]
                    MemoryCategory_2 [StatsItem]
                    MemoryCategory_3 [StatsItem]
                    MemoryCategory_4 [StatsItem]
                    MemoryCategory_5 [StatsItem]
                    MemoryCategory_6 [StatsItem]
                    MemoryCategory_7 [StatsItem]
                    MemoryCategory_8 [StatsItem]
                    MemoryCategory_9 [StatsItem]
                    MemoryCategory_10 [StatsItem]
                    MemoryCategory_11 [StatsItem]
                    MemoryCategory_12 [StatsItem]
                    MemoryCategory_13 [StatsItem]
                    MemoryCategory_14 [StatsItem]
                    MemoryCategory_15 [StatsItem]
                    MemoryCategory_16 [StatsItem]
                    MemoryCategory_17 [StatsItem]
                    MemoryCategory_18 [StatsItem]
                    MemoryCategory_19 [StatsItem]
                    MemoryCategory_20 [StatsItem]
                    MemoryCategory_21 [StatsItem]
                    MemoryCategory_22 [StatsItem]
                    MemoryCategory_23 [StatsItem]
                    MemoryCategory_24 [StatsItem]
                    MemoryCategory_25 [StatsItem]
                    MemoryCategory_26 [StatsItem]
                    MemoryCategory_27 [StatsItem]
                    MemoryCategory_28 [StatsItem]
                    MemoryCategory_29 [StatsItem]
                    MemoryCategory_30 [StatsItem]
                    MemoryCategory_31 [StatsItem]
                    MemoryCategory_32 [StatsItem]
                    MemoryCategory_33 [StatsItem]
                    MemoryCategory_34 [StatsItem]
                    MemoryCategory_35 [StatsItem]
                    MemoryCategory_36 [StatsItem]
                    MemoryCategory_37 [StatsItem]
                    MemoryCategory_38 [StatsItem]
                    MemoryCategory_39 [StatsItem]
                    MemoryCategory_40 [StatsItem]
                    MemoryCategory_41 [StatsItem]
                    MemoryCategory_42 [StatsItem]
                    MemoryCategory_43 [StatsItem]
                    MemoryCategory_44 [StatsItem]
                    MemoryCategory_45 [StatsItem]
                    MemoryCategory_46 [StatsItem]
                    MemoryCategory_47 [StatsItem]
                    MemoryCategory_48 [StatsItem]
                    MemoryCategory_49 [StatsItem]
                    MemoryCategory_50 [StatsItem]
                    MemoryCategory_51 [StatsItem]
                    MemoryCategory_52 [StatsItem]
                    MemoryCategory_53 [StatsItem]
                    MemoryCategory_54 [StatsItem]
                    MemoryCategory_55 [StatsItem]
                    MemoryCategory_56 [StatsItem]
                    MemoryCategory_57 [StatsItem]
                    MemoryCategory_58 [StatsItem]
                    MemoryCategory_59 [StatsItem]
                    MemoryCategory_60 [StatsItem]
                    MemoryCategory_61 [StatsItem]
                    MemoryCategory_62 [StatsItem]
                    MemoryCategory_63 [StatsItem]
                    MemoryCategory_64 [StatsItem]
                    MemoryCategory_65 [StatsItem]
                    MemoryCategory_66 [StatsItem]
                    MemoryCategory_67 [StatsItem]
                    MemoryCategory_68 [StatsItem]
                    MemoryCategory_69 [StatsItem]
                    MemoryCategory_70 [StatsItem]
                    MemoryCategory_71 [StatsItem]
                    MemoryCategory_72 [StatsItem]
                    MemoryCategory_73 [StatsItem]
                    MemoryCategory_74 [StatsItem]
                    MemoryCategory_75 [StatsItem]
                    MemoryCategory_76 [StatsItem]
                    MemoryCategory_77 [StatsItem]
                    MemoryCategory_78 [StatsItem]
                    MemoryCategory_79 [StatsItem]
                    MemoryCategory_80 [StatsItem]
                    MemoryCategory_81 [StatsItem]
                    MemoryCategory_82 [StatsItem]
                    MemoryCategory_83 [StatsItem]
                    MemoryCategory_84 [StatsItem]
                    MemoryCategory_85 [StatsItem]
                    MemoryCategory_86 [StatsItem]
                    MemoryCategory_87 [StatsItem]
                    MemoryCategory_88 [StatsItem]
                    MemoryCategory_89 [StatsItem]
                    MemoryCategory_90 [StatsItem]
                    MemoryCategory_91 [StatsItem]
                    MemoryCategory_92 [StatsItem]
                    MemoryCategory_93 [StatsItem]
                    MemoryCategory_94 [StatsItem]
                    MemoryCategory_95 [StatsItem]
                    MemoryCategory_96 [StatsItem]
                    MemoryCategory_97 [StatsItem]
                    MemoryCategory_98 [StatsItem]
                    MemoryCategory_99 [StatsItem]
                    MemoryCategory_100 [StatsItem]
                    MemoryCategory_101 [StatsItem]
                    MemoryCategory_102 [StatsItem]
                    MemoryCategory_103 [StatsItem]
                    MemoryCategory_104 [StatsItem]
                    MemoryCategory_105 [StatsItem]
                    MemoryCategory_106 [StatsItem]
                    MemoryCategory_107 [StatsItem]
                    MemoryCategory_108 [StatsItem]
                    MemoryCategory_109 [StatsItem]
                    MemoryCategory_110 [StatsItem]
                    MemoryCategory_111 [StatsItem]
                    MemoryCategory_112 [StatsItem]
                    MemoryCategory_113 [StatsItem]
                    MemoryCategory_114 [StatsItem]
                    MemoryCategory_115 [StatsItem]
                    MemoryCategory_116 [StatsItem]
                    MemoryCategory_117 [StatsItem]
                    MemoryCategory_118 [StatsItem]
                    MemoryCategory_119 [StatsItem]
                    MemoryCategory_120 [StatsItem]
                    MemoryCategory_121 [StatsItem]
                    MemoryCategory_122 [StatsItem]
                    MemoryCategory_123 [StatsItem]
                    MemoryCategory_124 [StatsItem]
                    MemoryCategory_125 [StatsItem]
                    MemoryCategory_126 [StatsItem]
                    MemoryCategory_127 [StatsItem]
                    MemoryCategory_128 [StatsItem]
                    MemoryCategory_129 [StatsItem]
                    MemoryCategory_130 [StatsItem]
                    MemoryCategory_131 [StatsItem]
                    MemoryCategory_132 [StatsItem]
                    MemoryCategory_133 [StatsItem]
                    MemoryCategory_134 [StatsItem]
                    MemoryCategory_135 [StatsItem]
                    MemoryCategory_136 [StatsItem]
                    MemoryCategory_137 [StatsItem]
                    MemoryCategory_138 [StatsItem]
                    MemoryCategory_139 [StatsItem]
                    MemoryCategory_140 [StatsItem]
                    MemoryCategory_141 [StatsItem]
                    MemoryCategory_142 [StatsItem]
                    MemoryCategory_143 [StatsItem]
                    MemoryCategory_144 [StatsItem]
                    MemoryCategory_145 [StatsItem]
                    MemoryCategory_146 [StatsItem]
                    MemoryCategory_147 [StatsItem]
                    MemoryCategory_148 [StatsItem]
                    MemoryCategory_149 [StatsItem]
                    MemoryCategory_150 [StatsItem]
                    MemoryCategory_151 [StatsItem]
                    MemoryCategory_152 [StatsItem]
                    MemoryCategory_153 [StatsItem]
                    MemoryCategory_154 [StatsItem]
                    MemoryCategory_155 [StatsItem]
                    MemoryCategory_156 [StatsItem]
                    MemoryCategory_157 [StatsItem]
                    MemoryCategory_158 [StatsItem]
                    MemoryCategory_159 [StatsItem]
                    MemoryCategory_160 [StatsItem]
                    MemoryCategory_161 [StatsItem]
                    MemoryCategory_162 [StatsItem]
                    MemoryCategory_163 [StatsItem]
                    MemoryCategory_164 [StatsItem]
                    MemoryCategory_165 [StatsItem]
                    MemoryCategory_166 [StatsItem]
                    MemoryCategory_167 [StatsItem]
                    MemoryCategory_168 [StatsItem]
                    MemoryCategory_169 [StatsItem]
                    MemoryCategory_170 [StatsItem]
                    MemoryCategory_171 [StatsItem]
                    MemoryCategory_172 [StatsItem]
                    MemoryCategory_173 [StatsItem]
                    MemoryCategory_174 [StatsItem]
                    MemoryCategory_175 [StatsItem]
                    MemoryCategory_176 [StatsItem]
                    MemoryCategory_177 [StatsItem]
                    MemoryCategory_178 [StatsItem]
                    MemoryCategory_179 [StatsItem]
                    MemoryCategory_180 [StatsItem]
                    MemoryCategory_181 [StatsItem]
                    MemoryCategory_182 [StatsItem]
                    MemoryCategory_183 [StatsItem]
                    MemoryCategory_184 [StatsItem]
                    MemoryCategory_185 [StatsItem]
                    MemoryCategory_186 [StatsItem]
                    MemoryCategory_187 [StatsItem]
                    MemoryCategory_188 [StatsItem]
                    MemoryCategory_189 [StatsItem]
                    MemoryCategory_190 [StatsItem]
                    MemoryCategory_191 [StatsItem]
                    MemoryCategory_192 [StatsItem]
                    MemoryCategory_193 [StatsItem]
                    MemoryCategory_194 [StatsItem]
                    MemoryCategory_195 [StatsItem]
                    MemoryCategory_196 [StatsItem]
                    MemoryCategory_197 [StatsItem]
                    MemoryCategory_198 [StatsItem]
                    MemoryCategory_199 [StatsItem]
                    MemoryCategory_200 [StatsItem]
                    MemoryCategory_201 [StatsItem]
                    MemoryCategory_202 [StatsItem]
                    MemoryCategory_203 [StatsItem]
                    MemoryCategory_204 [StatsItem]
                    MemoryCategory_205 [StatsItem]
                    MemoryCategory_206 [StatsItem]
                    MemoryCategory_207 [StatsItem]
                    MemoryCategory_208 [StatsItem]
                    MemoryCategory_209 [StatsItem]
                    MemoryCategory_210 [StatsItem]
                    MemoryCategory_211 [StatsItem]
                    MemoryCategory_212 [StatsItem]
                    MemoryCategory_213 [StatsItem]
                    MemoryCategory_214 [StatsItem]
                    MemoryCategory_215 [StatsItem]
                    MemoryCategory_216 [StatsItem]
                    MemoryCategory_217 [StatsItem]
                    MemoryCategory_218 [StatsItem]
                    MemoryCategory_219 [StatsItem]
                    MemoryCategory_220 [StatsItem]
                    MemoryCategory_221 [StatsItem]
                    MemoryCategory_222 [StatsItem]
                    MemoryCategory_223 [StatsItem]
                    MemoryCategory_224 [StatsItem]
                    MemoryCategory_225 [StatsItem]
                    MemoryCategory_226 [StatsItem]
                    MemoryCategory_227 [StatsItem]
                    MemoryCategory_228 [StatsItem]
                    MemoryCategory_229 [StatsItem]
                    MemoryCategory_230 [StatsItem]
                    MemoryCategory_231 [StatsItem]
                    MemoryCategory_232 [StatsItem]
                    MemoryCategory_233 [StatsItem]
                    MemoryCategory_234 [StatsItem]
                    MemoryCategory_235 [StatsItem]
                    MemoryCategory_236 [StatsItem]
                    MemoryCategory_237 [StatsItem]
                    MemoryCategory_238 [StatsItem]
                    MemoryCategory_239 [StatsItem]
                    MemoryCategory_240 [StatsItem]
                    MemoryCategory_241 [StatsItem]
                    MemoryCategory_242 [StatsItem]
                    MemoryCategory_243 [StatsItem]
                    MemoryCategory_244 [StatsItem]
                    MemoryCategory_245 [StatsItem]
                    MemoryCategory_246 [StatsItem]
                    MemoryCategory_247 [StatsItem]
                    MemoryCategory_248 [StatsItem]
                    MemoryCategory_249 [StatsItem]
                    MemoryCategory_250 [StatsItem]
                    MemoryCategory_251 [StatsItem]
                    MemoryCategory_252 [StatsItem]
                    MemoryCategory_253 [StatsItem]
                    MemoryCategory_254 [StatsItem]
                    MemoryCategory_255 [StatsItem]
            MaxMemory [StatsItem]
            CPU [StatsItem]
            MaxCPU [StatsItem]
            GPU [StatsItem]
            MaxGPU [StatsItem]
            Ping [StatsItem]
            MaxPing [StatsItem]
            NetworkReceived [StatsItem]
            MaxNetworkReceived [StatsItem]
            NetworkSent [StatsItem]
            MaxNetworkSent [StatsItem]
        RenderBreakdown [StatsItem]
            Undefined [StatsItem]
            Opaque [StatsItem]
            Transparent [StatsItem]
            Terrain [StatsItem]
            Grass [StatsItem]
            UI [StatsItem]
            Decal [StatsItem]
            Cloud [StatsItem]
            GenericPostProcess [StatsItem]
            SSAO [StatsItem]
            DOF [StatsItem]
            Particles [StatsItem]
            Sky [StatsItem]
        Workspace [StatsItem]
            FPS [StatsItem]
            Heartbeat [StatsItem]
            Environment Speed % [StatsItem]
            World [StatsItem]
                Primitives [StatsItem]
                Joints [StatsItem]
                Contacts [StatsItem]
                Non-Anchored Assemblies [StatsItem]
                Sleeping Assemblies [StatsItem]
                Sleep Checking Assemblies [StatsItem]
                Awake Assemblies [StatsItem]
            Contacts [StatsItem]
                CtctStageCtcts [StatsItem]
                SteppingCtcts [StatsItem]
            Kernel [StatsItem]
                Constraints [StatsItem]
            File Operations [StatsItem]
                Total Load Time [StatsItem]
                SyncHttpGet Time [StatsItem]
                XML Load Time [StatsItem]
                Join All Time [StatsItem]
        Sound [StatsItem]
            CPU [StatsItem]
                Dsp [StatsItem]
                Stream [StatsItem]
                Geometry [StatsItem]
                Update [StatsItem]
            ChannelsPlaying [StatsItem]
            Current [StatsItem]
            Max [StatsItem]
            # Sounds [StatsItem]
            # Unused [StatsItem]
        ChangeHistory [StatsItem]
            Data Size [StatsItem]
            Constrained Data Size [StatsItem]
            Stack Size [StatsItem]
        Network [StatsItem]
            Packets Thread [StatsItem]
                Rate [StatsItem]
                Activity [StatsItem]
                Physics Senders [StatsItem]
                Send Buffer Health [StatsItem]
            ServerStatsItem [StatsItem]
                Network Ping [StatsItem]
                Data Ping [RunningAverageItemInt]
                StreamingEnabled [StatsItem]
                Compression [StatsItem]
                Stats [StatsItem]
                    messageDataBytesSentPerSec [StatsItem]
                    messageTotalBytesSentPerSec [StatsItem]
                    messageDataBytesResentPerSec [StatsItem]
                    messagesBytesReceivedPerSec [StatsItem]
                    messagesBytesReceivedAndIgnoredPerSec [StatsItem]
                    bytesSentPerSec [StatsItem]
                    bytesReceivedPerSec [StatsItem]
                    totalMessageBytesPushed [StatsItem]
                    totalMessageBytesSent [StatsItem]
                    totalMessageBytesResent [StatsItem]
                    totalMessagesBytesReceived [StatsItem]
                    totalMessagesBytesReceivedAndIgnored [StatsItem]
                    totalBytesSent [StatsItem]
                    totalBytesReceived [StatsItem]
                    connectionStartTime [StatsItem]
                    outgoingBandwidthLimitBytesPerSecond [StatsItem]
                    isLimitedByOutgoingBandwidthLimit [StatsItem]
                    congestionControlLimitBytesPerSecond [StatsItem]
                    isLimitedByCongestionControl [StatsItem]
                    messageSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    bytesInSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    messagesInResendQueue [StatsItem]
                    bytesInResendQueue [StatsItem]
                    packetlossLastSecond [StatsItem]
                    packetlossTotal [StatsItem]
                    numberOfUnsplitMessages [StatsItem]
                    numberOfSplitMessages [StatsItem]
                    messageDataBytesSentPerSec [StatsItem]
                    messageTotalBytesSentPerSec [StatsItem]
                    messageDataBytesResentPerSec [StatsItem]
                    messagesBytesReceivedPerSec [StatsItem]
                    messagesBytesReceivedAndIgnoredPerSec [StatsItem]
                    bytesSentPerSec [StatsItem]
                    bytesReceivedPerSec [StatsItem]
                    totalMessageBytesPushed [StatsItem]
                    totalMessageBytesSent [StatsItem]
                    totalMessageBytesResent [StatsItem]
                    totalMessagesBytesReceived [StatsItem]
                    totalMessagesBytesReceivedAndIgnored [StatsItem]
                    totalBytesSent [StatsItem]
                    totalBytesReceived [StatsItem]
                    connectionStartTime [StatsItem]
                    outgoingBandwidthLimitBytesPerSecond [StatsItem]
                    isLimitedByOutgoingBandwidthLimit [StatsItem]
                    congestionControlLimitBytesPerSecond [StatsItem]
                    isLimitedByCongestionControl [StatsItem]
                    messageSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    bytesInSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    messagesInResendQueue [StatsItem]
                    bytesInResendQueue [StatsItem]
                    packetlossLastSecond [StatsItem]
                    packetlossTotal [StatsItem]
                    numberOfUnsplitMessages [StatsItem]
                    numberOfSplitMessages [StatsItem]
                Send kBps [StatsItem]
                    MtuSize [StatsItem]
                Send Buffer Health [StatsItem]
                BandwidthExceeded [StatsItem]
                CongestionControlExceeded [StatsItem]
                Receive kBps [StatsItem]
                Packet Queue [StatsItem]
                Sent Data Packets [StatsItem]
                    Size [RunningAverageItemInt]
                    Throttle [StatsItem]
                    Queue Size [StatsItem]
                    Time In Queue [StatsItem]
                    New Items Per Sec [TotalCountTimeIntervalItem]
                    Items Sent Per Sec [TotalCountTimeIntervalItem]
                OutPhysicsDetails [StatsItem]
                    CFrameOnly [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Mechanism [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Translation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Rotation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Velocity [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                InPhysicsDetails [StatsItem]
                    CFrameOnly [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Mechanism [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Translation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Rotation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Velocity [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                DataPingDetails [StatsItem]
                    LQToS [StatsItem]
                    LBcsQ [StatsItem]
                    RakPing [StatsItem]
                    RRakRecvToAppPop [StatsItem]
                    RAppPopToDeserialize [StatsItem]
                    RDeserializeToPBQ [StatsItem]
                    RQToS [StatsItem]
                    RBscQ [StatsItem]
                    LRakRecvToAppPop [StatsItem]
                    LAppPopToSerialize [StatsItem]
                    LDeserializeToProcess [StatsItem]
                    EstTotal [StatsItem]
                    MeasuredTotal [StatsItem]
                    unrelLQToS [StatsItem]
                    unrelLBcsQ [StatsItem]
                    unrelRakPing [StatsItem]
                    unrelRRakRecvToAppPop [StatsItem]
                    unrelRAppPopToDeserialize [StatsItem]
                    unrelRDeserializeToPBQ [StatsItem]
                    unrelRQToS [StatsItem]
                    unrelRBscQ [StatsItem]
                    unrelLRakRecvToAppPop [StatsItem]
                    unrelLAppPopToSerialize [StatsItem]
                    unrelLDeserializeToProcess [StatsItem]
                    unrelEstTotal [StatsItem]
                    unrelMeasuredTotal [StatsItem]
                Send Data Types [StatsItem]
                    InstanceNew [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDelete [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Ping [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Data [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Behavior [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    State [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Appearance [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Team [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Video [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Control [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Events [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDestroy [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                Received Data Types [StatsItem]
                    InstanceNew [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDelete [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Ping [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Data [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Behavior [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    State [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Appearance [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Team [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Video [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Control [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Events [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDestroy [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                Sent Physics Packets [StatsItem]
                    Size [RunningAverageItemInt]
                    Throttle [StatsItem]
                    Smoothed [StatsItem]
                    Items Per Packet [RunningAverageItemInt]
                SentTouchPackets [StatsItem]
                    Size [RunningAverageItemInt]
                    WaitingTouches [RunningAverageItemInt]
                Received Packets [StatsItem]
                Received Data Packets [StatsItem]
                    Queue Size [StatsItem]
                    Instance Size [StatsItem]
                    Waiting Refs [StatsItem]
                    Size [StatsItem]
                Received ISR Packets [StatsItem]
                    Size [StatsItem]
                Received LR Packets [StatsItem]
                    Size [StatsItem]
                Received Physics Packets [StatsItem]
                    Average Lag [StatsItem]
                    Average Buffer Seek [StatsItem]
                    Max Buffer Seek [StatsItem]
                    Wrong Order [StatsItem]
                    Size [StatsItem]
                Sent ISR Packets [StatsItem]
                    Size [StatsItem]
                In ISR Physics Details [StatsItem]
                    Mechanism [StatsItem]
                        Size [StatsItem]
                    CFrameOnly [StatsItem]
                        Size [StatsItem]
                    Translation [StatsItem]
                        Size [StatsItem]
                    Rotation [StatsItem]
                        Size [StatsItem]
                    Velocity [StatsItem]
                        Size [StatsItem]
                Out ISR Physics Details [StatsItem]
                    Mechanism [StatsItem]
                        Size [StatsItem]
                    CFrameOnly [StatsItem]
                        Size [StatsItem]
                    Translation [StatsItem]
                        Size [StatsItem]
                    Rotation [StatsItem]
                        Size [StatsItem]
                    Velocity [StatsItem]
                        Size [StatsItem]
                Sent Cluster Packets [StatsItem]
                    Size [RunningAverageItemInt]
                Received Cluster Packets [StatsItem]
                    Size [StatsItem]
                Received Touch Packets [StatsItem]
                    Size [StatsItem]
                ElapsedTime [StatsItem]
                MaxPacketLoss [StatsItem]
                TotalInDataBW [StatsItem]
                TotalOutDataBW [StatsItem]
                TotalRakIn [StatsItem]
                TotalRakOut [StatsItem]
                OutBufferHealth [StatsItem]
                PropSync [StatsItem]
                    ItemCount [StatsItem]
                    AckCount [StatsItem]
                Received Stream Data [StatsItem]
                    AvgReadTimePerItem [RunningAverageItemDouble]
                    AvgInstancesPerItem [RunningAverageItemDouble]
                    RequestedInstanceAvg [RunningAverageItemInt]
                    PendingRequestCount [StatsItem]
                    GCDistance [StatsItem]
                    NumRegions [StatsItem]
                    CurrentRadius [StatsItem]
                    NumReplicationFoci [StatsItem]
                    NumPrefetches [StatsItem]
                    PlayerPosition [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                    PlayerRegion [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                    LastKnownServerStreamCenter [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                Lr Data [StatsItem]
                    LrBytesRecv [StatsItem]
                    LrSegmentsRecv [StatsItem]
                    LrEstimatedRawRecv [StatsItem]
                    LrEstimatedOptimizedRecv [StatsItem]
                    LrActualPreCompressRecv [StatsItem]
                    LrActualPostCompressRecv [StatsItem]
                    LrAssetsRecv [StatsItem]
                    LrAssetsByDeltaRecv [StatsItem]
                    LrDeltasRecv [StatsItem]
                    LrCancelRecv [StatsItem]
                    LrRemoveRecv [StatsItem]
                    LrCompleteRecv [StatsItem]
                    LrInlineRecv [StatsItem]
                    LrIgnoreRecv [StatsItem]
                    LrHashFail [StatsItem]
                    LrHashCheck [StatsItem]
                    LrMemCountRecv [StatsItem]
                    LrMemEstBytesRecv [StatsItem]
        Luau [StatsItem]
            disabled [StatsItem]
            threads [StatsItem]
            AverageGcTime [StatsItem]
        FrameRateManager [StatsItem]
            DeviceFeatureLevel [StatsItem]
            DeviceShadingLanguage [StatsItem]
            AverageQualityLevel [StatsItem]
            AutoQuality [StatsItem]
            NumberOfSettles [StatsItem]
            AverageSwitches [StatsItem]
            FramebufferWidth [StatsItem]
            FramebufferHeight [StatsItem]
            Batches [StatsItem]
            Indices [StatsItem]
            MaterialChanges [StatsItem]
            VideoMemoryInMB [StatsItem]
            AverageFPS [StatsItem]
            FrameTimeVariance [StatsItem]
            FrameSpikeCount [StatsItem]
            RenderAverage [StatsItem]
            PrepareAverage [StatsItem]
            PerformAverage [StatsItem]
            AveragePresent [StatsItem]
            AverageGPU [StatsItem]
            RenderThreadAverage [StatsItem]
            TotalFrameWallAverage [StatsItem]
            PerformVariance [StatsItem]
            PresentVariance [StatsItem]
            GpuVariance [StatsItem]
            MsFrame0 [StatsItem]
            MsFrame1 [StatsItem]
            MsFrame2 [StatsItem]
            MsFrame3 [StatsItem]
            MsFrame4 [StatsItem]
            MsFrame5 [StatsItem]
            MsFrame6 [StatsItem]
            MsFrame7 [StatsItem]
            MsFrame8 [StatsItem]
            MsFrame9 [StatsItem]
            MsFrame10 [StatsItem]
            MsFrame11 [StatsItem]
        Render [StatsItem]
            Memory [StatsItem]
                Video [StatsItem]
    TimerService [TimerService]
    CollectionService [CollectionService]
    SoundService [SoundService]
    VideoCaptureService [VideoCaptureService]
    LogService [LogService]
    MicroProfilerService [MicroProfilerService]
    ContentProvider [ContentProvider]
    KeyframeSequenceProvider [KeyframeSequenceProvider]
    AnimationClipProvider [AnimationClipProvider]
    Chat [Chat]
    MarketplaceService [MarketplaceService]
    Players [Players]
        hydrazx9 [Player]
            PlayerScripts [PlayerScripts]
            Backpack [Backpack]
    PointsService [PointsService]
    NotificationService [NotificationService]
    ReplicatedFirst [ReplicatedFirst]
    HttpRbxApiService [HttpRbxApiService]
    TweenService [TweenService]
    MaterialService [MaterialService]
    TextChatService [TextChatService]
        BubbleChatConfiguration [BubbleChatConfiguration]
            ImageLabel [ImageLabel]
            UICorner [UICorner]
            UIGradient [UIGradient]
            UIPadding [UIPadding]
        ChannelTabsConfiguration [ChannelTabsConfiguration]
        ChatInputBarConfiguration [ChatInputBarConfiguration]
        ChatWindowConfiguration [ChatWindowConfiguration]
    TextService [TextService]
    PermissionsService [PermissionsService]
    SharedTableRegistry [SharedTableRegistry]
    StarterPlayer [StarterPlayer]
        StarterCharacterScripts [StarterCharacterScripts]
        StarterPlayerScripts [StarterPlayerScripts]
            ClientMain [LocalScript]
                ----- SOURCE -----
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)

Registry.AutoLoadConfigs(ReplicatedStorage:WaitForChild("Configs"))
Net.Init()

local Client = script.Parent:WaitForChild("Client")
local Render = require(Client.ClientRenderEngine)
local Placement = require(Client.PlacementController)
local ShopUI = require(Client.ShopUI)

Render.Init()
Placement.Init(Render)
ShopUI.Init(Placement, Render)

local okChat, errChat = pcall(function()
	require(Client.ChatCommands).Init()
end)
if not okChat then
	warn("[ChatCommands] " .. tostring(errChat))
end

Net.Request():InvokeServer("ClientReady")

                ----- END SOURCE -----
            LocalScript [LocalScript]
                ----- SOURCE -----
local StarterGui = game:GetService("StarterGui")

-- Desativa completamente a barra de inventário (Backpack) da tela do jogador
StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Backpack, false)
                ----- END SOURCE -----
            Client [Folder]
                Animators [ModuleScript]
                    ----- SOURCE -----
--[[
	Animators: escolhe o animador de cada unidade pelo config. O ClientRenderEngine só fala com esta fábrica.
	Animation = { Mode = "Procedural" }   -- padrão: poses por nome de junta (UnitAnimator)
	Animation = { Mode = "Rig", ... }     -- animações reais do Animation Editor (RigAnimator)
	Os dois têm o mesmo contrato: :SetPivot(cf) :SetSpeed(s) :Trigger(nome, aoSoltar) :Kill() :Step(dt) e .DeathTime
]]
local UnitAnimator = require(script.Parent.UnitAnimator)
local RigAnimator = require(script.Parent.RigAnimator)

local Animators = {}

function Animators.IsRig(cfg)
	return cfg.Animation ~= nil and cfg.Animation.Mode == "Rig"
end

function Animators.new(model, role, cfg)
	if not model:IsA("Model") then
		return nil
	end
	if Animators.IsRig(cfg) then
		return RigAnimator.new(model, role, cfg)
	end
	return UnitAnimator.new(model, role, cfg)
end

return Animators

                    ----- END SOURCE -----
                ClientRenderEngine [ModuleScript]
                    ----- SOURCE -----
--[[
	ClientRenderEngine: 100% do visual roda aqui. Nenhum inimigo existe como Instance no servidor.
	- Inimigo: posição = path:PositionAt(min(D + S * (agora - T), comprimento)), com agora = workspace:GetServerTimeNow().
	  O servidor só manda âncora (D,T) + velocidade (S) no spawn e quando a velocidade muda (slow/freeze).
	- Partes simples são movidas em lote com BulkMoveTo (1 chamada/frame).
	- Projétil: lerp de origem -> posição PREVISTA do inimigo em T1 (hora do impacto, vinda do servidor).
	Assets opcionais: ReplicatedStorage.Assets.Models.{Towers,Enemies,Projectiles}.<ModelName> (também vale Assets.<Pasta> direto).
	  Torres/inimigos = Models com PrimaryPart (torre: pivô na base; inimigo: pivô no centro da altura de Visual.Size).
	  Projétil = Model com PrimaryPart apontando p/ -Z; Visual.Projectile.ModelName escolhe o modelo (Attribute BaseSize = escala 1).
	  Modelos com juntas são animados pelo UnitAnimator (procedural, funciona com partes ancoradas).
]]
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local RunService = game:GetService("RunService")
local TweenService = game:GetService("TweenService")
local Debris = game:GetService("Debris")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local EventBus = require(Shared.EventBus)
local Net = require(Shared.Net)
local PathUtil = require(Shared.PathUtil)
local Animators = require(script.Parent.Animators)

local Render = {
	Enemies = {},
	Towers = {},
	Map = nil,
	State = nil,
	Data = { Coins = 0 },
	Loadout = {},
	Events = EventBus.new(), -- "TowerChanged"(id) · "TowerRemoved"(id) · "GameState"(state) · "PlayerData"(data)
	Folder = nil,
	TowersFolder = nil,
}

local enemiesFolder, fxFolder
local projectiles = {}
local dying = {} -- modelos animados tocando a animação de morte
local pendingSpawns = {}
local bulkParts, bulkCFrames = {}, {}

local function serverNow()
	return workspace:GetServerTimeNow()
end

local function findIn(root, kind, name)
	local folder = root and root:FindFirstChild(kind)
	return folder and folder:FindFirstChild(name)
end

local function cloneAsset(kind, name, canQuery, rig)
	if not name then
		return nil
	end
	local assets = ReplicatedStorage:FindFirstChild("Assets")
	local models = assets and assets:FindFirstChild("Models")
	local template = findIn(models, kind, name) or findIn(assets, kind, name)
	if not template then
		return nil
	end
	local clone = template:Clone()
	-- rig = animações reais: só a PrimaryPart fica ancorada; o resto segue pelas juntas (Motor6D/Weld).
	-- procedural: tudo ancorado (o UnitAnimator move as peças em lote).
	local root = rig and clone:IsA("Model") and clone.PrimaryPart or nil
	local parts = clone:GetDescendants()
	table.insert(parts, clone)
	for _, d in ipairs(parts) do
		if d:IsA("BasePart") then
			d.CanCollide = false
			d.CanQuery = canQuery
			if root then
				d.Anchored = d == root
				d.Massless = true
			else
				d.Anchored = true
			end
		end
	end
	return clone
end

local function makePart(size, color, canQuery)
	local part = Instance.new("Part")
	part.Anchored = true
	part.CanCollide = false
	part.CanTouch = false
	part.CanQuery = canQuery
	part.Size = size
	part.Color = color
	part.Material = Enum.Material.SmoothPlastic
	return part
end

-- ---------------------------------------------------------------- anel de alcance (usado por UI/placement)
function Render.MakeRing(color)
	local ring = Instance.new("Part")
	ring.Shape = Enum.PartType.Cylinder
	ring.Anchored = true
	ring.CanCollide = false
	ring.CanTouch = false
	ring.CanQuery = false
	ring.Material = Enum.Material.Neon
	ring.Transparency = 0.8
	ring.Color = color or Color3.fromRGB(255, 255, 255)
	return ring
end

function Render.PlaceRing(ring, pos, range)
	ring.Size = Vector3.new(0.2, range * 2, range * 2)
	ring.CFrame = CFrame.new(pos + Vector3.new(0, 0.15, 0)) * CFrame.Angles(0, 0, math.rad(90))
end

function Render.TowerCost(def)
	local m = Render.Map and Render.Map.Config.Multipliers
	return math.ceil(def.Cost * (m and m.TowerCost or 1))
end

function Render.PickTower(inst)
	local cur = inst
	while cur and cur ~= Render.TowersFolder do
		local id = cur:GetAttribute("TDTowerId")
		if id then
			return id
		end
		cur = cur.Parent
	end
	return nil
end

-- ---------------------------------------------------------------- inimigos
local function adornee(r)
	if r.IsPart then
		return r.Inst
	end
	return r.Inst.PrimaryPart or r.Inst:FindFirstChildWhichIsA("BasePart", true)
end

local function updateBar(r)
	if r.Hp >= r.MaxHp and not r.Bar then
		return
	end
	if not r.Bar then
		local gui = Instance.new("BillboardGui")
		gui.Size = UDim2.fromOffset(60, 8)
		gui.StudsOffset = Vector3.new(0, r.BarY, 0)
		gui.AlwaysOnTop = true
		gui.Adornee = adornee(r)
		local back = Instance.new("Frame")
		back.Size = UDim2.fromScale(1, 1)
		back.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
		back.BorderSizePixel = 0
		back.Parent = gui
		local fill = Instance.new("Frame")
		fill.Name = "Fill"
		fill.Size = UDim2.fromScale(1, 1)
		fill.BackgroundColor3 = Color3.fromRGB(90, 220, 90)
		fill.BorderSizePixel = 0
		fill.Parent = back
		gui.Parent = r.Inst
		r.Bar = gui
	end
	r.Bar.Frame.Fill.Size = UDim2.fromScale(math.clamp(r.Hp / r.MaxHp, 0, 1), 1)
end

local function applyTint(r)
	local color = r.BaseColor
	for _, c in pairs(r.Tints) do
		color = c
		break
	end
	if r.IsPart then
		r.Inst.Color = color
	elseif r.TintParts then
		local tinted = next(r.Tints) ~= nil
		for part, original in pairs(r.TintParts) do
			part.Color = tinted and color or original
		end
	end
end

local function newEnemy(p)
	if Render.Enemies[p.Id] then
		return
	end
	local cfg = Registry.Of("Enemies"):Get(p.Cfg)
	local path = Render.Map and Render.Map.Paths[p.Path]
	if not cfg or not path then
		return
	end
	local vis = cfg.Visual or {}
	local size = vis.Size or Vector3.new(2, 3, 2)
	local inst = cloneAsset("Enemies", cfg.ModelName, false, Animators.IsRig(cfg))
	if not inst then
		inst = makePart(size, vis.Color or Color3.fromRGB(200, 60, 60), false)
	end
	inst.Parent = enemiesFolder
	local isPart = inst:IsA("BasePart")
	local anim = not isPart and inst:IsA("Model") and Animators.new(inst, "Enemy", cfg) or nil
	local tintParts
	if not isPart then
		tintParts = {}
		for _, d in ipairs(inst:GetDescendants()) do
			if d:IsA("BasePart") and d.Transparency < 1 then
				tintParts[d] = d.Color
			end
		end
	end
	local r = {
		Id = p.Id,
		Cfg = cfg,
		Path = path,
		Inst = inst,
		IsPart = isPart,
		D = p.D,
		T = p.T,
		S = p.S,
		Hp = p.Hp,
		MaxHp = p.MaxHp,
		YOffset = size.Y / 2,
		BarY = (isPart and size.Y / 2 or inst:GetAttribute("BarHeight") or size.Y / 2) + 1.5,
		Anim = anim,
		TintParts = tintParts,
		Tints = {},
		BaseColor = isPart and inst.Color or Color3.new(1, 1, 1),
		LastPos = path:PositionAt(p.D),
	}
	Render.Enemies[p.Id] = r
	updateBar(r)
end

local function removeEnemy(id, reason)
	local r = Render.Enemies[id]
	if not r then
		return
	end
	Render.Enemies[id] = nil
	if r.Bar then
		r.Bar:Destroy()
	end
	if reason == "Killed" and r.IsPart then
		TweenService:Create(r.Inst, TweenInfo.new(0.25), { Transparency = 1, Size = r.Inst.Size * 0.3 }):Play()
		Debris:AddItem(r.Inst, 0.3)
	elseif reason == "Killed" and r.Anim then
		r.Anim:Kill()
		table.insert(dying, { Anim = r.Anim, Inst = r.Inst, Age = 0 })
	else
		r.Inst:Destroy()
	end
end

-- ---------------------------------------------------------------- torres
local function newTower(p)
	local cfg = Registry.Of("Towers"):Get(p.Cfg)
	if not cfg or Render.Towers[p.Id] then
		return
	end
	local vis = cfg.Visual or {}
	local size = vis.Size or Vector3.new(3, 4, 3)
	local inst = cloneAsset("Towers", cfg.ModelName, true, Animators.IsRig(cfg))
	local anim, muzzle
	if inst then
		inst:PivotTo(CFrame.new(p.Pos))
		if inst:IsA("Model") then
			anim = Animators.new(inst, "Tower", cfg)
			muzzle = inst:FindFirstChild("Muzzle", true)
			if muzzle and not muzzle:IsA("Attachment") then
				muzzle = nil
			end
		end
	else
		inst = makePart(size, vis.Color or Color3.fromRGB(200, 200, 200), true)
		inst.Position = p.Pos + Vector3.new(0, size.Y / 2, 0)
	end
	inst:SetAttribute("TDTowerId", p.Id)
	inst.Parent = Render.TowersFolder
	Render.Towers[p.Id] = {
		Id = p.Id,
		Cfg = cfg,
		Inst = inst,
		Position = p.Pos,
		Owner = p.Owner,
		Range = p.Range,
		Splash = p.Splash,
		Tiers = p.Tiers,
		Mode = p.Mode,
		Invested = p.Invested,
		Damage = p.Damage,
		Interval = p.Interval,
		Height = size.Y * 0.8,
		Anim = anim,
		Muzzle = muzzle,
	}
	Render.Events:Fire("TowerChanged", p.Id)
end

local function tierSum(tiers)
	local n = 0
	for _, v in pairs(tiers) do
		n += v
	end
	return n
end

local function updateTower(p)
	local t = Render.Towers[p.Id]
	if not t then
		return
	end
	local upgraded = tierSum(p.Tiers) > tierSum(t.Tiers)
	t.Range, t.Splash, t.Tiers, t.Mode, t.Invested = p.Range, p.Splash, p.Tiers, p.Mode, p.Invested
	t.Damage, t.Interval = p.Damage, p.Interval
	if upgraded and t.Anim then
		t.Anim:Trigger("Upgrade")
	end
	Render.Events:Fire("TowerChanged", p.Id)
end

local function removeTower(id)
	local t = Render.Towers[id]
	if not t then
		return
	end
	Render.Towers[id] = nil
	t.Inst:Destroy()
	Render.Events:Fire("TowerRemoved", id)
end

-- ---------------------------------------------------------------- projéteis / fx
local function impactFx(pos, radius, color)
	local fx = Instance.new("Part")
	fx.Shape = Enum.PartType.Ball
	fx.Anchored = true
	fx.CanCollide = false
	fx.CanQuery = false
	fx.CanTouch = false
	fx.Material = Enum.Material.Neon
	fx.Transparency = 0.4
	fx.Color = color
	fx.Size = Vector3.one
	fx.Position = pos
	fx.Parent = fxFolder
	TweenService
		:Create(fx, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {
			Size = Vector3.one * radius * 2,
			Transparency = 1,
		})
		:Play()
	Debris:AddItem(fx, 0.35)
end

local function placeProjectile(pr, pos)
	if pr.IsAsset then
		local d = pos - pr.LastPos
		if d.Magnitude > 1e-3 then
			pr.Dir = d.Unit
		end
		pr.LastPos = pos
		pr.Part:PivotTo(CFrame.lookAt(pos, pos + pr.Dir))
	else
		pr.Part.Position = pos
	end
end

-- impacto de projétil com modelo próprio: emissores com atributo EmitCount soltam uma rajada, rastros param,
-- o corpo some (exceto peças com atributo KeepOnImpact) e o modelo fica ImpactLifetime segundos para os efeitos terminarem
local function projectileImpact(pr)
	local inst = pr.Part
	if not pr.IsAsset then
		inst:Destroy()
		return
	end
	inst:PivotTo(CFrame.lookAt(pr.Target, pr.Target + pr.Dir))
	for _, d in ipairs(inst:GetDescendants()) do
		if d:IsA("ParticleEmitter") then
			d.Enabled = false
			local count = d:GetAttribute("EmitCount")
			if count then
				d:Emit(count)
			end
		elseif d:IsA("Trail") then
			d.Enabled = false
		elseif d:IsA("BasePart") and not d:GetAttribute("KeepOnImpact") then
			d.Transparency = 1
		end
	end
	Debris:AddItem(inst, pr.Cfg.ImpactLifetime or 1.5)
end

local function fireTower(f)
	local tw = Render.Towers[f.Tower]
	if not tw then
		return
	end
	local en = Render.Enemies[f.Enemy]
	local pv = tw.Cfg.Visual and tw.Cfg.Visual.Projectile or {}

	if en then
		local look = Vector3.new(en.LastPos.X, tw.Position.Y, en.LastPos.Z)
		if look ~= tw.Position then
			local rot = CFrame.lookAt(tw.Position, look)
			if tw.Anim then
				tw.Anim:SetPivot(rot)
			else
				tw.Inst:PivotTo(rot)
			end
		end
	end

	local fallback = en and en.LastPos or tw.Position
	local launched = false

	-- o projétil sai no instante de "soltar" da animação (procedural: ReleaseTime; rig: marcador "Release")
	local function launch()
		if launched or not Render.Towers[tw.Id] then
			return
		end
		launched = true
		if tw.Anim then
			tw.Anim:Step(0) -- aplica a pose atual: o Muzzle precisa estar no lugar certo
		end
		local now = serverNow()
		local cur = Render.Enemies[f.Enemy]
		local origin = tw.Muzzle and tw.Muzzle.WorldPosition or (tw.Position + Vector3.new(0, tw.Height, 0))
		local target = cur and cur.LastPos or fallback
		local flat = target - origin
		local dir = flat.Magnitude > 1e-3 and flat.Unit or Vector3.new(0, 0, -1)

		local part = pv.ModelName and cloneAsset("Projectiles", pv.ModelName, false)
		local isAsset = part ~= nil
		if isAsset then
			local base = part:GetAttribute("BaseSize")
			if base and pv.Size and part:IsA("Model") then
				part:ScaleTo(pv.Size / base)
			end
			part:PivotTo(CFrame.lookAt(origin, origin + dir))
			part.Parent = fxFolder
		else
			part = Instance.new("Part")
			part.Shape = Enum.PartType.Ball
			part.Anchored = true
			part.CanCollide = false
			part.CanQuery = false
			part.CanTouch = false
			part.Material = Enum.Material.Neon
			part.Color = pv.Color or Color3.fromRGB(255, 255, 255)
			part.Size = Vector3.one * (pv.Size or 0.7)
			part.Position = origin
			part.Parent = fxFolder
		end
		table.insert(projectiles, {
			Part = part,
			IsAsset = isAsset,
			Cfg = pv,
			LastPos = origin,
			Dir = dir,
			From = origin,
			EnemyId = f.Enemy,
			T0 = now,
			T1 = math.max(f.T1, now + 0.1), -- o acerto é decidido pelo servidor (T1); mínimo de 0.1s visível
			Arc = pv.Arc or 0,
			Splash = tw.Splash,
			Color = pv.Color or Color3.fromRGB(255, 255, 255),
			Target = target,
		})
	end

	if tw.Anim then
		tw.Anim:Trigger("Attack", launch)
	else
		launch()
	end
end

-- ---------------------------------------------------------------- loop de render
local function step(dt)
	local t = serverNow()

	local n = 0
	for _, r in pairs(Render.Enemies) do
		local d = r.D + r.S * (t - r.T)
		local len = r.Path.Length
		if d > len then
			d = len
		elseif d < 0 then
			d = 0
		end
		local pos = r.Path:PositionAt(d)
		r.LastPos = pos
		local center = pos + Vector3.new(0, r.YOffset, 0)
		local cf = CFrame.lookAt(center, center + r.Path:DirectionAt(d))
		if r.IsPart then
			n += 1
			bulkParts[n] = r.Inst
			bulkCFrames[n] = cf
		elseif r.Anim then
			r.Anim:SetPivot(cf)
			r.Anim:SetSpeed(r.S)
			r.Anim:Step(dt)
		else
			r.Inst:PivotTo(cf)
		end
	end
	for i = #bulkParts, n + 1, -1 do
		bulkParts[i] = nil
		bulkCFrames[i] = nil
	end
	if n > 0 then
		workspace:BulkMoveTo(bulkParts, bulkCFrames, Enum.BulkMoveMode.FireCFrameChanged)
	end

	for _, tw in pairs(Render.Towers) do
		if tw.Anim then
			tw.Anim:Step(dt)
		end
	end
	for i = #dying, 1, -1 do
		local d = dying[i]
		d.Age += dt
		d.Anim:Step(dt)
		if d.Age >= (d.Anim.DeathTime or 0.5) then
			d.Inst:Destroy()
			table.remove(dying, i)
		end
	end

	for i = #projectiles, 1, -1 do
		local pr = projectiles[i]
		local en = Render.Enemies[pr.EnemyId]
		if en then
			local d = math.min(en.D + en.S * (pr.T1 - en.T), en.Path.Length)
			pr.Target = en.Path:PositionAt(d) + Vector3.new(0, en.YOffset, 0)
		end
		local alpha = (t - pr.T0) / (pr.T1 - pr.T0)
		if alpha >= 1 then
			if pr.Splash > 0 then
				impactFx(pr.Target, pr.Splash, pr.Color)
			end
			projectileImpact(pr)
			table.remove(projectiles, i)
		else
			alpha = math.max(alpha, 0)
			local pos = pr.From:Lerp(pr.Target, alpha)
			if pr.Arc > 0 then
				pos += Vector3.new(0, math.sin(math.pi * alpha) * pr.Arc, 0)
			end
			placeProjectile(pr, pos)
		end
	end
end

-- ---------------------------------------------------------------- rede
local function setMap(mapId)
	for _, r in pairs(Render.Enemies) do
		r.Inst:Destroy()
	end
	for _, tw in pairs(Render.Towers) do
		tw.Inst:Destroy()
	end
	for _, pr in ipairs(projectiles) do
		pr.Part:Destroy()
	end
	for _, d in ipairs(dying) do
		d.Inst:Destroy()
	end
	table.clear(dying)
	table.clear(Render.Enemies)
	table.clear(Render.Towers)
	table.clear(projectiles)

	local cfg = Registry.Of("Maps"):Get(mapId)
	if not cfg then
		Render.Map = nil
		return
	end
	local paths = {}
	for id, points in pairs(cfg.Paths) do
		paths[id] = PathUtil.new(points)
	end
	Render.Map = { Id = mapId, Config = cfg, Paths = paths }
	for _, p in ipairs(pendingSpawns) do
		newEnemy(p)
	end
	table.clear(pendingSpawns)
end

local function onDelta(p)
	for _, e in ipairs(p.EnemySpawned) do
		if Render.Map then
			newEnemy(e)
		else
			table.insert(pendingSpawns, e) -- mapa ainda não chegou (entrada tardia)
		end
	end
	for _, m in ipairs(p.EnemyMotion) do
		local r = Render.Enemies[m.Id]
		if r then
			r.D, r.T, r.S = m.D, m.T, m.S
		end
	end
	for _, h in ipairs(p.EnemyHealth) do
		local r = Render.Enemies[h.Id]
		if r then
			r.Hp = h.Hp
			updateBar(r)
		end
	end
	for _, s in ipairs(p.Status) do
		local r = Render.Enemies[s.Enemy]
		if r then
			local def = Registry.Of("StatusEffects"):Get(s.Effect)
			r.Tints[s.Effect] = s.On and def and def.Visual and def.Visual.Color or nil
			applyTint(r)
		end
	end
	for _, tp in ipairs(p.TowerPlaced) do
		newTower(tp)
	end
	for _, tu in ipairs(p.TowerUpdated) do
		updateTower(tu)
	end
	for _, f in ipairs(p.TowerFired) do
		fireTower(f)
	end
	for _, id in ipairs(p.TowerRemoved) do
		removeTower(id.Id)
	end
	for _, e in ipairs(p.EnemyRemoved) do
		removeEnemy(e.Id, e.Reason)
	end
end

function Render.Init()
	Render.Folder = Instance.new("Folder")
	Render.Folder.Name = "TDClient"
	Render.Folder.Parent = workspace
	Render.TowersFolder = Instance.new("Folder")
	Render.TowersFolder.Name = "Towers"
	Render.TowersFolder.Parent = Render.Folder
	enemiesFolder = Instance.new("Folder")
	enemiesFolder.Name = "Enemies"
	enemiesFolder.Parent = Render.Folder
	fxFolder = Instance.new("Folder")
	fxFolder.Name = "FX"
	fxFolder.Parent = Render.Folder

	Net.Event("GameState").OnClientEvent:Connect(function(state)
		Render.State = state
		if not Render.Map or Render.Map.Id ~= state.MapId then
			setMap(state.MapId)
		end
		Render.Events:Fire("GameState", state)
	end)
	Net.Event("PlayerData").OnClientEvent:Connect(function(data)
		Render.Data = data
		Render.Events:Fire("PlayerData", data)
	end)
	Net.Event("Loadout").OnClientEvent:Connect(function(list)
		Render.Loadout = list
		Render.Events:Fire("Loadout", list)
	end)
	Net.Event("Delta").OnClientEvent:Connect(onDelta)
	RunService.RenderStepped:Connect(step)
end

return Render

                    ----- END SOURCE -----
                PlacementController [ModuleScript]
                    ----- SOURCE -----
--[[
	PlacementController: fantasma da torre (verde/vermelho), confirmação por clique/toque e seleção de torres.
	O cliente só PREVÊ com PlacementRules; quem decide é o servidor (Request "PlaceTower").
]]
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)
local PlacementRules = require(Shared.PlacementRules)

local GREEN, RED = Color3.fromRGB(90, 220, 110), Color3.fromRGB(230, 80, 80)

local Placement = { Active = nil, OnSelect = nil, OnResult = nil }
local Render
local ghost, ring, conn
local activeRange = 0
local pointer = nil -- só usado no toque
local currentPos, currentValid, currentReason = nil, false, nil

function Placement.Cancel()
	Placement.Active = nil
	currentPos = nil
	if conn then
		conn:Disconnect()
		conn = nil
	end
	if ghost then
		ghost:Destroy()
		ghost = nil
	end
	if ring then
		ring:Destroy()
		ring = nil
	end
end

local function update()
	if not Placement.Active or not Render.Map then
		return
	end
	local camera = workspace.CurrentCamera
	local loc = pointer or UserInputService:GetMouseLocation()
	local ray = camera:ViewportPointToRay(loc.X, loc.Y)
	local params = RaycastParams.new()
	params.FilterType = Enum.RaycastFilterType.Exclude
	params.FilterDescendantsInstances = { Render.Folder, Players.LocalPlayer.Character }
	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
	if not hit then
		currentPos = nil
		ghost.Transparency = 1
		return
	end
	local y = Render.Map.Config.GroundY or 0
	currentPos = Vector3.new(hit.Position.X, y, hit.Position.Z)
	currentValid, currentReason = PlacementRules.Check(Render.Map, currentPos, Render.Towers)
	ghost.Position = currentPos + Vector3.new(0, ghost.Size.Y / 2, 0)
	ghost.Transparency = 0.45
	local color = currentValid and GREEN or RED
	ghost.Color = color
	ring.Color = color
	if activeRange > 0 then
		ring.Transparency = 0.8
		Render.PlaceRing(ring, currentPos, activeRange)
	else
		ring.Transparency = 1
	end
end

function Placement.Begin(towerId)
	Placement.Cancel()
	local def = Registry.Of("Towers"):Get(towerId)
	if not def then
		return
	end
	Placement.Active = towerId
	if Placement.OnSelect then
		Placement.OnSelect(nil)
	end
	local vis = def.Visual or {}
	ghost = Instance.new("Part")
	ghost.Anchored = true
	ghost.CanCollide = false
	ghost.CanQuery = false
	ghost.CanTouch = false
	ghost.Size = vis.Size or Vector3.new(3, 4, 3)
	ghost.Transparency = 1
	ghost.Parent = Render.Folder
	ring = Render.MakeRing()
	ring.Parent = Render.Folder
	activeRange = def.Stats and def.Stats.Range or 0
	conn = RunService.RenderStepped:Connect(update)
end

function Placement.Toggle(towerId)
	if Placement.Active == towerId then
		Placement.Cancel()
	else
		Placement.Begin(towerId)
	end
end

local function confirm()
	if not Placement.Active or not currentPos then
		return
	end
	if not currentValid then
		if Placement.OnResult then
			Placement.OnResult({ Ok = false, Error = currentReason })
		end
		return
	end
	local id, pos = Placement.Active, currentPos
	if not UserInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
		Placement.Cancel() -- segure Shift para colocar várias
	end
	local res = Net.Request():InvokeServer("PlaceTower", { TowerId = id, Position = pos })
	if Placement.OnResult then
		Placement.OnResult(res)
	end
end

local function selectAt(loc)
	local ray = workspace.CurrentCamera:ViewportPointToRay(loc.X, loc.Y)
	local params = RaycastParams.new()
	params.FilterType = Enum.RaycastFilterType.Include
	params.FilterDescendantsInstances = { Render.TowersFolder }
	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
	local id = hit and Render.PickTower(hit.Instance) or nil
	if Placement.OnSelect then
		Placement.OnSelect(id)
	end
end

function Placement.Init(renderEngine)
	Render = renderEngine

	UserInputService.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.Touch then
			pointer = Vector2.new(input.Position.X, input.Position.Y)
		end
	end)

	UserInputService.InputBegan:Connect(function(input, processed)
		if processed then
			return
		end
		local t = input.UserInputType
		if t == Enum.UserInputType.MouseButton1 then
			pointer = nil
			if Placement.Active then
				confirm()
			else
				selectAt(UserInputService:GetMouseLocation())
			end
		elseif t == Enum.UserInputType.MouseButton2 or (t == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.Escape) then
			Placement.Cancel()
		elseif t == Enum.UserInputType.Touch then
			pointer = Vector2.new(input.Position.X, input.Position.Y)
			if not Placement.Active then
				selectAt(pointer)
			end
		end
	end)

	-- toque: arraste para posicionar, solte para confirmar
	UserInputService.InputEnded:Connect(function(input, processed)
		if not processed and input.UserInputType == Enum.UserInputType.Touch and Placement.Active then
			confirm()
		end
	end)
end

return Placement

                    ----- END SOURCE -----
                RigAnimator [ModuleScript]
                    ----- SOURCE -----
--[[
	RigAnimator: mesmo contrato do UnitAnimator, mas toca AnimationTracks reais (Animation Editor).
	O ClientRenderEngine ancora só a PrimaryPart quando Animation.Mode = "Rig"; o resto do modelo segue pelas juntas.
	AnimationController e Animator são criados se o modelo não tiver.

	Animation = {
		Mode = "Rig",
		Tracks = { Idle = "rbxassetid://...", Walk = "...", Attack = "...", Upgrade = "...", Death = "..." },  -- todos opcionais
		WalkSpeed = 9,        -- studs/s em que o Walk toca a 1x (padrão: Speed do config do inimigo)
		ReleaseMarker = true, -- KeyframeMarker "Release" no Attack = instante em que o projétil sai
		ReleaseTime = 0.3,    -- alternativa sem marcador: segundos após o início do Attack (0 = sai na hora)
	}
]]
local RigAnimator = {}
RigAnimator.__index = RigAnimator

local PRIORITY = {
	Idle = Enum.AnimationPriority.Idle,
	Walk = Enum.AnimationPriority.Movement,
	Attack = Enum.AnimationPriority.Action,
	Upgrade = Enum.AnimationPriority.Action2,
	Death = Enum.AnimationPriority.Action4,
}
local LOOPED = { Idle = true, Walk = true }

function RigAnimator.new(model, role, cfg)
	if not model.PrimaryPart then
		return nil
	end
	local a = cfg.Animation or {}
	return setmetatable({
		Model = model,
		Role = role,
		Config = a,
		Tracks = {},
		Loaded = false,
		Pivot = model:GetPivot(),
		Speed = 0,
		WalkRef = a.WalkSpeed or cfg.Speed or 8,
		ReleaseTime = a.ReleaseTime or 0,
		DeathTime = 0.15,
		PendingRelease = nil,
		ReleaseAt = 0,
		Time = 0,
		Dead = false,
	}, RigAnimator)
end

-- carrega as animações só quando o modelo já está no workspace (o Animator exige isso)
function RigAnimator:_load()
	if self.Loaded or not self.Model:IsDescendantOf(workspace) then
		return
	end
	self.Loaded = true
	local controller = self.Model:FindFirstChildWhichIsA("AnimationController", true)
		or self.Model:FindFirstChildWhichIsA("Humanoid", true)
	if not controller then
		controller = Instance.new("AnimationController")
		controller.Parent = self.Model
	end
	local animator = controller:FindFirstChildWhichIsA("Animator")
	if not animator then
		animator = Instance.new("Animator")
		animator.Parent = controller
	end
	for name, id in pairs(self.Config.Tracks or {}) do
		local anim = Instance.new("Animation")
		anim.AnimationId = id
		local ok, track = pcall(function()
			return animator:LoadAnimation(anim)
		end)
		if ok and track then
			track.Priority = PRIORITY[name] or Enum.AnimationPriority.Action
			track.Looped = LOOPED[name] == true
			self.Tracks[name] = track
		else
			warn(("[RigAnimator] %s: não carregou a animação '%s'"):format(self.Model.Name, name))
		end
	end
	if self.Tracks.Idle then
		self.Tracks.Idle:Play()
	end
	if self.Tracks.Walk then
		self.Tracks.Walk:Play(0.1, 1, 0) -- começa parado; SetSpeed liga o ciclo
	end
	if self.Tracks.Death then
		self.DeathTime = math.max(self.Tracks.Death.Length, 0.15)
	end
end

function RigAnimator:SetPivot(cf)
	self.Pivot = cf
end

function RigAnimator:SetSpeed(speed)
	self.Speed = speed
	local walk = self.Tracks.Walk
	if walk and not self.Dead then
		walk:AdjustSpeed(speed > 0.05 and speed / self.WalkRef or 0) -- 0 = pose congelada
	end
end

function RigAnimator:_release()
	local fn = self.PendingRelease
	if fn then
		self.PendingRelease = nil
		fn()
	end
end

function RigAnimator:Trigger(name, onRelease)
	self:_load()
	local track = self.Tracks[name]
	if track then
		track:Play(0.05, 1, 1)
	end
	if name ~= "Attack" or not onRelease then
		return
	end
	self:_release() -- solta o disparo anterior, se ainda estava pendente
	if not track then
		onRelease()
	elseif self.Config.ReleaseMarker then
		self.PendingRelease = onRelease
		self.ReleaseAt = self.Time + 1 -- segurança se o marcador não existir na animação
		local conn
		conn = track:GetMarkerReachedSignal("Release"):Connect(function()
			conn:Disconnect()
			self:_release()
		end)
	elseif self.ReleaseTime > 0 then
		self.PendingRelease = onRelease
		self.ReleaseAt = self.Time + self.ReleaseTime
	else
		onRelease()
	end
end

function RigAnimator:Kill()
	if self.Dead then
		return
	end
	self.Dead = true
	self:_load()
	self:_release()
	for name, track in pairs(self.Tracks) do
		if name ~= "Death" then
			track:Stop(0.05)
		end
	end
	if self.Tracks.Death then
		self.Tracks.Death:Play(0.05, 1, 1)
	end
end

function RigAnimator:Step(dt)
	self.Time += dt
	self:_load()
	self.Model:PivotTo(self.Pivot)
	if self.PendingRelease and self.Time >= self.ReleaseAt then
		self:_release()
	end
end

return RigAnimator

                    ----- END SOURCE -----
                ShopUI [ModuleScript]
                    ----- SOURCE -----
--[[
	ShopUI (Factory): NENHUM botão é desenhado à mão.
	- Loja: um clone do template (ReplicatedStorage.Template2) por entrada de TowersConfig, dentro de MainUI.Units.Background
	- Painel da torre selecionada: upgrades/targeting/venda gerados de cfg.Upgrades e cfg.Targeting
	- HUD: estado, onda, vidas, moedas e contagem regressiva
]]
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)
local UnitCard = require(script.Parent.UnitCard)
local UnitPanel = require(script.Parent.UnitPanel)

local ERRORS = {
	NotEnoughCoins = "Moedas insuficientes",
	NotEquipped = "Equipe essa unidade no inventário",
	LoadoutFull = "Slots cheios: desequipe uma unidade",
	CannotBuildNow = "Não é possível construir agora",
	OutOfBounds = "Fora da área do mapa",
	TooCloseToPath = "Muito perto do caminho",
	TooCloseToTower = "Muito perto de outra torre",
	LimitReached = "Limite dessa torre atingido",
	MaxTier = "Nível máximo",
	PathLocked = "Caminho bloqueado por outro upgrade",
	NotYourTower = "Essa torre não é sua",
	RateLimited = "Calma! Muitas ações",
}
local STATE_NAMES = {
	WaitingForPlayers = "Aguardando jogadores",
	Intermission = "Intervalo",
	WaveActive = "Onda em andamento",
	GameOver = "Fim de jogo",
	Victory = "Vitória!",
}

local TEMPLATE_NAME = "Template2" -- troque para "Template1" quando quiser cards com ícone

local ShopUI = {}

local function new(class, props, parent)
	local inst = Instance.new(class)
	for k, v in pairs(props) do
		inst[k] = v
	end
	inst.Parent = parent
	return inst
end

function ShopUI.Init(Placement, Render)
	local player = Players.LocalPlayer
	local playerGui = player:WaitForChild("PlayerGui")
	local gui = new("ScreenGui", { Name = "TDUI", ResetOnSpawn = false }, playerGui)

	-- ---------------------------------------------------------- HUD + toast
	local hud = new("TextLabel", {
		AnchorPoint = Vector2.new(0.5, 0),
		Position = UDim2.new(0.5, 0, 0, 8),
		Size = UDim2.fromOffset(520, 34),
		BackgroundColor3 = Color3.fromRGB(20, 22, 28),
		BackgroundTransparency = 0.2,
		TextColor3 = Color3.new(1, 1, 1),
		Font = Enum.Font.GothamMedium,
		TextSize = 16,
		Text = "Conectando...",
	}, gui)
	new("UICorner", { CornerRadius = UDim.new(0, 8) }, hud)

	local toastLabel = new("TextLabel", {
		AnchorPoint = Vector2.new(0.5, 0),
		Position = UDim2.new(0.5, 0, 0, 48),
		Size = UDim2.fromOffset(360, 30),
		BackgroundColor3 = Color3.fromRGB(150, 50, 50),
		TextColor3 = Color3.new(1, 1, 1),
		Font = Enum.Font.GothamMedium,
		TextSize = 15,
		Visible = false,
	}, gui)
	new("UICorner", { CornerRadius = UDim.new(0, 8) }, toastLabel)
	local toastToken = 0
	local function toast(text)
		toastToken += 1
		local mine = toastToken
		toastLabel.Text = text
		toastLabel.Visible = true
		task.delay(2.5, function()
			if toastToken == mine then
				toastLabel.Visible = false
			end
		end)
	end
	local function explain(res)
		if res and not res.Ok then
			toast(ERRORS[res.Error] or tostring(res.Error))
		end
	end
	Placement.OnResult = explain

	local function refreshHud()
		local s = Render.State
		if not s then
			return
		end
		local left = ""
		if s.EndsAt and s.EndsAt > 0 then
			left = (" | %ds"):format(math.max(0, math.ceil(s.EndsAt - workspace:GetServerTimeNow())))
		end
		local waveText = s.VictoryWave and s.VictoryWave > 0 and ("%d/%d"):format(s.Wave, s.VictoryWave) or tostring(s.Wave)
		hud.Text = ("%s | Onda %s | Vidas %d/%d | Moedas %d%s"):format(
			STATE_NAMES[s.State] or s.State,
			waveText,
			s.Lives,
			s.MaxLives,
			Render.Data.Coins or 0,
			left
		)
	end
	task.spawn(function()
		while gui.Parent do
			refreshHud()
			task.wait(0.25)
		end
	end)

	-- ---------------------------------------------------------- loja (equipadas) + inventário (todas)
	local template = ReplicatedStorage:WaitForChild(TEMPLATE_NAME)
	local mainUI = playerGui:WaitForChild("MainUI")
	local shopBackground = mainUI:WaitForChild("Units"):WaitForChild("Background") -- Frame Units: só as equipadas
	local invUnits = mainUI:WaitForChild("Inventory"):WaitForChild("Units") -- ScrollingFrame Units: todas

	if not shopBackground:FindFirstChildWhichIsA("UIListLayout") and not shopBackground:FindFirstChildWhichIsA("UIGridLayout") then
		new("UIListLayout", {
			FillDirection = Enum.FillDirection.Horizontal,
			Padding = UDim.new(0, 8),
			SortOrder = Enum.SortOrder.LayoutOrder,
		}, shopBackground)
	end

	local WHITE, RED, GREEN = Color3.new(1, 1, 1), Color3.fromRGB(255, 120, 120), Color3.fromRGB(120, 255, 140)
	local shopCards, invCards = {}, {}

	local function makeCard(def, parent, order)
		local button = template:Clone()
		button.Name = def.Id
		button.LayoutOrder = order
		button.Visible = true
		button.Parent = parent
		if button:IsA("ImageButton") and def.Icon and def.Icon ~= "" then
			button.Image = def.Icon
		end
		return button
	end

	local function refreshShop()
		local coins = Render.Data.Coins or 0
		for _, c in pairs(shopCards) do
			local cost = Render.TowerCost(c.Def)
			if c.Button:IsA("TextButton") then
				c.Button.Text = ("%s\n$%d"):format(c.Def.DisplayName or c.Def.Id, cost)
				c.Button.TextColor3 = coins >= cost and WHITE or RED
			end
		end
	end

	local function refreshInventory()
		for id, c in pairs(invCards) do
			local eq = table.find(Render.Loadout, id) ~= nil
			if c.Button:IsA("TextButton") then
				c.Button.Text = ("%s\n%s"):format(c.Def.DisplayName or id, eq and "[Equipado]" or "Equipar")
				c.Button.TextColor3 = eq and GREEN or WHITE
			end
		end
	end

	local function rebuildShop()
		for _, c in pairs(shopCards) do
			c.Button:Destroy()
		end
		table.clear(shopCards)
		local towers = Registry.Of("Towers")
		for i, id in ipairs(Render.Loadout) do
			local def = towers:Get(id)
			if def then
				local button = UnitCard.Make(def, shopBackground, i, Render) or makeCard(def, shopBackground, i)
				button.Activated:Connect(function()
					Placement.Toggle(id)
				end)
				shopCards[id] = { Button = button, Def = def }
			end
		end
		refreshShop()
	end

	-- inventário: um card por torre existente (torres novas em TowersConfig aparecem sozinhas)
	Registry.Of("Towers"):OnRegister(function(def)
		local button = makeCard(def, invUnits, def.Cost)
		button.Activated:Connect(function()
			explain(Net.Request():InvokeServer("ToggleEquip", { TowerId = def.Id }))
		end)
		invCards[def.Id] = { Button = button, Def = def }
		refreshInventory()
	end)

	Render.Events:Connect("Loadout", function(list)
		if Placement.Active and not table.find(list, Placement.Active) then
			Placement.Cancel()
		end
		rebuildShop()
		refreshInventory()
	end)
	Render.Events:Connect("PlayerData", refreshShop)
	Render.Events:Connect("GameState", refreshShop)
	rebuildShop()
	 [trimmed]  -  Editar
  18:17:13.842  > local HttpService = game:GetService("HttpService")

local output = {}

local function add(text)
	table.insert(output, text)
end

local function indent(depth)
	return string.rep("    ", depth)
end

local function scan(instance, depth)
	local className = instance.ClassName
	local name = instance.Name

	add(indent(depth) .. name .. " [" .. className .. "]")

	-- Salva o código dos scripts
	if instance:IsA("Script")
		or instance:IsA("LocalScript")
		or instance:IsA("ModuleScript") then

		add(indent(depth + 1) .. "----- SOURCE -----")
		add(instance.Source)
		add(indent(depth + 1) .. "----- END SOURCE -----")
	end

	for _, child in ipairs(instance:GetChildren()) do
		scan(child, depth + 1)
	end
end

add("===== ROBLOX PROJECT MAP =====")
add("Gerado em: " .. os.date("%Y-%m-%d %H:%M:%S"))
add("")

scan(game, 0)

local result = table.concat(output, "\n")

-- Tenta copiar para o clipboard do Studio
pcall(function()
	setclipboard(result)
end)

print("========================================")
print("PROJETO EXPORTADO!")
print("Tamanho: " .. #result .. " caracteres")
print("========================================")
print(result)  -  Studio
  18:17:13.854  ========================================  -  Editar
  18:17:13.854  PROJETO EXPORTADO!  -  Editar
  18:17:13.854  Tamanho: 442723 caracteres  -  Editar
  18:17:13.854  ========================================  -  Editar
  18:17:13.855  ===== ROBLOX PROJECT MAP =====
Gerado em: 2026-10-02 18:17:13

Place1 [DataModel]
    Workspace [Workspace]
        SunRays [SunRaysEffect]
        ColorCorrection [ColorCorrectionEffect]
        Blur [BlurEffect]
        Bloom [BloomEffect]
            Atmosphere [Atmosphere]
            ArcHandles [ArcHandles]
        TowerDefenseMap [Folder]
            Waypoints [Folder]
            Path [Folder]
            TowerSpots [Folder]
            Decor [Folder]
        Terrain [Terrain]
        Camera [Camera]
    Run Service [RunService]
    GuiService [GuiService]
        ScreenshotHud [ScreenshotHud]
    Stats [Stats]
        PerformanceStats [StatsItem]
            Memory [StatsItem]
                CoreMemory [StatsItem]
                    default [StatsItem]
                    staticinit [StatsItem]
                    http/batch [StatsItem]
                    lua/web-cache [StatsItem]
                    contentProvider/asyncDecryption [StatsItem]
                    internal/DataModelPatch [StatsItem]
                    render/prepare/physics [StatsItem]
                    physics/step [StatsItem]
                    physics/buffers [StatsItem]
                    physics/mechanism [StatsItem]
                    physics/assembly [StatsItem]
                    experienceStateCaptureService [StatsItem]
                    gui/TextLayout [StatsItem]
                    render/fonts [StatsItem]
                    gui/HarfBuzz [StatsItem]
                    gui/FreeType [StatsItem]
                    fontProvider/loading [StatsItem]
                    gui/FontData [StatsItem]
                    internal/localizationTable [StatsItem]
                    internal/localization [StatsItem]
                    ads/AdGui [StatsItem]
                    internal/MarketplaceService [StatsItem]
                    geometry/EditableMesh/Geometry [StatsItem]
                    geometry/EditableMesh/SpatialCache [StatsItem]
                    geometry/EditableMesh/GpuAssigned [StatsItem]
                    physics/bullet [StatsItem]
                    network/netAssetSerialized [StatsItem]
                    network/netAssetRegistries [StatsItem]
                    network/netAssetProxy [StatsItem]
                    AppCore/GuidRegistry [StatsItem]
                    instance/fullname [StatsItem]
                    internal/TaskScheduler [StatsItem]
                    profiler [StatsItem]
                    internal/RbxThread [StatsItem]
                    localstorage [StatsItem]
                    telemetry/analytics [StatsItem]
                    telemetry [StatsItem]
                    http/client [StatsItem]
                    http/curl [StatsItem]
                    http/requestcallback [StatsItem]
                    openssl [StatsItem]
                    http/wslay [StatsItem]
                    SQLite [StatsItem]
                    telemetry/fields_container [StatsItem]
                    telemetry/counter [StatsItem]
                    telemetry/event [StatsItem]
                    telemetry/stat [StatsItem]
                    telemetry/v2_try_cut_and_send [StatsItem]
                    gui/FreeTypeDT [StatsItem]
                    AssetProvider/total [StatsItem]
                    sound/default [StatsItem]
                    render/copy [StatsItem]
                    render/vertexlayout [StatsItem]
                    render/shader [StatsItem]
                    render/swapchain [StatsItem]
                    raknet/raknet [StatsItem]
                    raknet/startup [StatsItem]
                    raknet/recv-buffer [StatsItem]
                    raknet/buffered-commands [StatsItem]
                    raknet/packet-return [StatsItem]
                    raknet/tx-outgoing [StatsItem]
                    raknet/tx-datagram [StatsItem]
                    raknet/rx-ordered-heap [StatsItem]
                    raknet/rx-split-reassembly [StatsItem]
                    raknet/rx-output [StatsItem]
                    raknet/rx-handling [StatsItem]
                    raknet/datagram-history [StatsItem]
                    raknet/ack-nak [StatsItem]
                    RbxTransport/Io/sys [StatsItem]
                    RbxTransport/Io/libuv [StatsItem]
                    video/encoding/hardware [StatsItem]
                    video/default [StatsItem]
                    video/packet [StatsItem]
                    video/codec [StatsItem]
                    video/texture [StatsItem]
                    internal/PerformanceControl [StatsItem]
                    RbxTransport/RtcIo/Local [StatsItem]
                    RbxTransport/RtcIo/Remote/Rx [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptConnection [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptWtSession [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptH3 [StatsItem]
                    RbxTransport/RtcIo/Remote/NewAppConnection [StatsItem]
                    RbxTransport/RtcIo/Remote/Handshake [StatsItem]
                    RbxTransport/RtcIo/Remote/StreamAccepted [StatsItem]
                    RbxTransport/RtcIo/Remote/StreamClose [StatsItem]
                    RbxTransport/RtcIo/Remote/Ack [StatsItem]
                    RbxTransport/RtcIo/Remote/FlowControl [StatsItem]
                    RbxTransport/RtcIo/Remote/Loss [StatsItem]
                    RbxTransport/RtcIo/Remote/ConnClose [StatsItem]
                    RbxTransport/RtcIo/Remote/AppControl [StatsItem]
                    RbxTransport/RtcIo/Remote/AppFin [StatsItem]
                    RbxTransport/RtcIo/Remote/OpenUnreliableChannel [StatsItem]
                    physics/broadphase [StatsItem]
                    physics/midphase [StatsItem]
                    internal/ixp [StatsItem]
                    video/realtime_media [StatsItem]
                    video/capture_engine [StatsItem]
                    physics/aerodynamics/mesh [StatsItem]
                    physics/aerodynamics/integrator [StatsItem]
                    physics/aerodynamics/linearintegrator [StatsItem]
                    physics/aerodynamics/cpintegrator [StatsItem]
                    physics/aerodynamics/shinterpolator [StatsItem]
                    physics/aerodynamics/reducedmesh [StatsItem]
                    internal/ScriptContext [StatsItem]
                    lua/bytecode [StatsItem]
                    lua/codegen [StatsItem]
                    lua/codegenpages [StatsItem]
                    internal/RuntimeScriptService [StatsItem]
                    CoreScriptTelemetry [StatsItem]
                    physics/solver/buffers [StatsItem]
                    physics/solver/sleep [StatsItem]
                    physics/solver/ldl [StatsItem]
                    physics/solver/misc [StatsItem]
                    internal/DataModelGenericJob [StatsItem]
                    studio/undo [StatsItem]
                    internal/InstanceStitchingHandler [StatsItem]
                    CollectionService [StatsItem]
                    internal/ChatService [StatsItem]
                    internal/GlobalSettings [StatsItem]
                    render/terrain/heightmapImporter [StatsItem]
                    geometry/EditableImage [StatsItem]
                    collections/collection [StatsItem]
                    collections/watcher [StatsItem]
                    performanceStats [StatsItem]
                    collections/proximity [StatsItem]
                    internal/AuroraService/InputFrame [StatsItem]
                    internal/AuroraService/HashBuffer [StatsItem]
                    internal/AuroraService/Prediction [StatsItem]
                    internal/Workspace [StatsItem]
                    internal/RemoteFunction [StatsItem]
                    internal/LogService [StatsItem]
                    render/lightgrid [StatsItem]
                    render/system [StatsItem]
                    render/bindworkspace [StatsItem]
                    render/adorn [StatsItem]
                    render/perform/statistics [StatsItem]
                    render/prepare [StatsItem]
                    render/prepare/adorn [StatsItem]
                    render/perform [StatsItem]
                    render/perform/adorn [StatsItem]
                    render/glyphaatlas/ugc [StatsItem]
                    render/glyphatlas/core [StatsItem]
                    render/terrain/grass/async [StatsItem]
                    render/terrain/grass [StatsItem]
                    render/prepare/terrain/grass [StatsItem]
                    render/target [StatsItem]
                    render/target/pooled [StatsItem]
                    render/perform/zpre [StatsItem]
                    render/clouds [StatsItem]
                    render/ssao [StatsItem]
                    render/glow [StatsItem]
                    render/sunrays [StatsItem]
                    render/dof [StatsItem]
                    render/blur [StatsItem]
                    render/colorCorrection [StatsItem]
                    render/highlight [StatsItem]
                    render/RtPool [StatsItem]
                    render/mainRts [StatsItem]
                    render/ui [StatsItem]
                    render/shadowmap [StatsItem]
                    render/perform/shadowmap [StatsItem]
                    render/shadowmap/depthcache [StatsItem]
                    render/perform/materialMisc [StatsItem]
                    render/perform/materialGc [StatsItem]
                    render/material/failsafe [StatsItem]
                    render/perform/terrain [StatsItem]
                    render/prepare/terrain [StatsItem]
                    render/instanceglob [StatsItem]
                    render/gpu_geom_mgr [StatsItem]
                    dynamic/mesh [StatsItem]
                    dynamic/texture [StatsItem]
                    render/envmap [StatsItem]
                    render/material/misc [StatsItem]
                    render/prepare/tc [StatsItem]
                    render/prepare/sceneUpdater [StatsItem]
                    render/prepare/parts [StatsItem]
                    render/prepare/megaCluster [StatsItem]
                    render/prepare/attachments [StatsItem]
                    render/swocc [StatsItem]
                    render/perform/textureAtlasInsert [StatsItem]
                    render/meshManager/async [StatsItem]
                    textureRef [StatsItem]
                    render/texture/local [StatsItem]
                    render/texture/fallback [StatsItem]
                    render/texture/loading [StatsItem]
                    render/perform/textureGc [StatsItem]
                    render/prepare/textureManager [StatsItem]
                    render/perform/textureManager [StatsItem]
                    render/sky [StatsItem]
                    render/advsky [StatsItem]
                    render/perform/cullableScene [StatsItem]
                    render/prepare/motionBuffer [StatsItem]
                    render/geometryGenerator [StatsItem]
                    render/perform/scratchFB [StatsItem]
                    render/prepare/lightObject [StatsItem]
                    render/terrain/async/chunkGen [StatsItem]
                    render/perform/terrain/occlusionGen [StatsItem]
                    render/viewportFrames [StatsItem]
                    render/prepare/lightGridChunk [StatsItem]
                    render/perform/lightGrid [StatsItem]
                    render/fastCluster/prepareSkinning [StatsItem]
                    render/fastCluster/skinningReserve [StatsItem]
                    render/prepare/beamNode [StatsItem]
                    render/prepare/customEmitter [StatsItem]
                    render/pipeline [StatsItem]
                    render/pipeline/updates [StatsItem]
                    render/meshFetcherDecomp [StatsItem]
                    network/compresspacket [StatsItem]
                    network/decompresspacket [StatsItem]
                    network/ISR/Property [StatsItem]
                    network/groupManager [StatsItem]
                    network/ISR/Replicator [StatsItem]
                    network/setManager [StatsItem]
                    internal/CSGDictionary [StatsItem]
                    network/HeatmapQueryService [StatsItem]
                    internal/HttpRbxApiService [StatsItem]
                    internal/StarterPlayer [StatsItem]
                    datastore/cache [StatsItem]
                    animation/skeleton_watcher [StatsItem]
                    wrap/layeredDeformer [StatsItem]
                    internal/Humanoid [StatsItem]
                    temporaryCageMeshProvider/save [StatsItem]
                    wrap/hsr [StatsItem]
                    animation/skeleton [StatsItem]
                    wrap/deformMeshProvider [StatsItem]
                    gui/Uncategorized [StatsItem]
                    gui/UIQuadTree [StatsItem]
                    languageServices/async [StatsItem]
                    languageServices/generic [StatsItem]
                    languageServices/shadow [StatsItem]
                    network/streamingReplication [StatsItem]
                    network/streamJob [StatsItem]
                    network/replicationCoalescing [StatsItem]
                    network/deserializestep [StatsItem]
                    network/onreceive [StatsItem]
                    network/sharedQueue [StatsItem]
                    network/megaReplicationData [StatsItem]
                    network/modelCompleteness [StatsItem]
                    network/refPropTracking [StatsItem]
                    network/replicator [StatsItem]
                    internal/InputReplicator [StatsItem]
                    network/gcJob [StatsItem]
                    network/instanceObjectManager [StatsItem]
                    network/server [StatsItem]
                    network/streamingSolver [StatsItem]
                    network/streamingObserver [StatsItem]
                    network/replicatedInstances [StatsItem]
                    network/deferredtrees [StatsItem]
                    network/newinstanceitem [StatsItem]
                    network/streamDataItem [StatsItem]
                    network/ISR [StatsItem]
                    network/ISR/Connection [StatsItem]
                    network/ISR/Prioritization [StatsItem]
                    network/touchReplication [StatsItem]
                    network/replicationDataCache [StatsItem]
                    network/replicationDataCachePendingList [StatsItem]
                    network/ISR/groupMan [StatsItem]
                    network/physicsSenderCache [StatsItem]
                    sound/voice [StatsItem]
                    voice/webrtc [StatsItem]
                    voice/operations [StatsItem]
                    voice/audio [StatsItem]
                    sound/async [StatsItem]
                    sound/acoustics [StatsItem]
                    AudioWiring [StatsItem]
                    instance/AttributesAndTags [StatsItem]
                    internal/BaseThreadPool [StatsItem]
                    AssetProvider/state [StatsItem]
                    AssetProvider/other [StatsItem]
                    render/vertexstreamer [StatsItem]
                    friendsCalling/bringUp [StatsItem]
                PlaceMemory [StatsItem]
                    HttpCache [StatsItem]
                    Instances [StatsItem]
                    Signals [StatsItem]
                    LuaHeap [StatsItem]
                    Script [StatsItem]
                    PhysicsCollision [StatsItem]
                    BaseParts [StatsItem]
                    GraphicsSolidModels [StatsItem]
                    GraphicsHSR [StatsItem]
                    GraphicsMeshParts [StatsItem]
                    GraphicsParticles [StatsItem]
                    GraphicsParts [StatsItem]
                    GraphicsSpatialHash [StatsItem]
                    GraphicsTerrain [StatsItem]
                    GraphicsTexture [StatsItem]
                    GraphicsTextureCharacter [StatsItem]
                    Sounds [StatsItem]
                    TerrainVoxels [StatsItem]
                    TerrainPhysics [StatsItem]
                    Gui [StatsItem]
                    Animation [StatsItem]
                    Navigation [StatsItem]
                    GeometryCSG [StatsItem]
                    GraphicsSlimModels [StatsItem]
                UntrackedMemory [StatsItem]
                PlaceScriptMemory [StatsItem]
                    MemoryCategory_0 [StatsItem]
                    MemoryCategory_1 [StatsItem]
                    MemoryCategory_2 [StatsItem]
                    MemoryCategory_3 [StatsItem]
                    MemoryCategory_4 [StatsItem]
                    MemoryCategory_5 [StatsItem]
                    MemoryCategory_6 [StatsItem]
                    MemoryCategory_7 [StatsItem]
                    MemoryCategory_8 [StatsItem]
                    MemoryCategory_9 [StatsItem]
                    MemoryCategory_10 [StatsItem]
                    MemoryCategory_11 [StatsItem]
                    MemoryCategory_12 [StatsItem]
                    MemoryCategory_13 [StatsItem]
                    MemoryCategory_14 [StatsItem]
                    MemoryCategory_15 [StatsItem]
                    MemoryCategory_16 [StatsItem]
                    MemoryCategory_17 [StatsItem]
                    MemoryCategory_18 [StatsItem]
                    MemoryCategory_19 [StatsItem]
                    MemoryCategory_20 [StatsItem]
                    MemoryCategory_21 [StatsItem]
                    MemoryCategory_22 [StatsItem]
                    MemoryCategory_23 [StatsItem]
                    MemoryCategory_24 [StatsItem]
                    MemoryCategory_25 [StatsItem]
                    MemoryCategory_26 [StatsItem]
                    MemoryCategory_27 [StatsItem]
                    MemoryCategory_28 [StatsItem]
                    MemoryCategory_29 [StatsItem]
                    MemoryCategory_30 [StatsItem]
                    MemoryCategory_31 [StatsItem]
                    MemoryCategory_32 [StatsItem]
                    MemoryCategory_33 [StatsItem]
                    MemoryCategory_34 [StatsItem]
                    MemoryCategory_35 [StatsItem]
                    MemoryCategory_36 [StatsItem]
                    MemoryCategory_37 [StatsItem]
                    MemoryCategory_38 [StatsItem]
                    MemoryCategory_39 [StatsItem]
                    MemoryCategory_40 [StatsItem]
                    MemoryCategory_41 [StatsItem]
                    MemoryCategory_42 [StatsItem]
                    MemoryCategory_43 [StatsItem]
                    MemoryCategory_44 [StatsItem]
                    MemoryCategory_45 [StatsItem]
                    MemoryCategory_46 [StatsItem]
                    MemoryCategory_47 [StatsItem]
                    MemoryCategory_48 [StatsItem]
                    MemoryCategory_49 [StatsItem]
                    MemoryCategory_50 [StatsItem]
                    MemoryCategory_51 [StatsItem]
                    MemoryCategory_52 [StatsItem]
                    MemoryCategory_53 [StatsItem]
                    MemoryCategory_54 [StatsItem]
                    MemoryCategory_55 [StatsItem]
                    MemoryCategory_56 [StatsItem]
                    MemoryCategory_57 [StatsItem]
                    MemoryCategory_58 [StatsItem]
                    MemoryCategory_59 [StatsItem]
                    MemoryCategory_60 [StatsItem]
                    MemoryCategory_61 [StatsItem]
                    MemoryCategory_62 [StatsItem]
                    MemoryCategory_63 [StatsItem]
                    MemoryCategory_64 [StatsItem]
                    MemoryCategory_65 [StatsItem]
                    MemoryCategory_66 [StatsItem]
                    MemoryCategory_67 [StatsItem]
                    MemoryCategory_68 [StatsItem]
                    MemoryCategory_69 [StatsItem]
                    MemoryCategory_70 [StatsItem]
                    MemoryCategory_71 [StatsItem]
                    MemoryCategory_72 [StatsItem]
                    MemoryCategory_73 [StatsItem]
                    MemoryCategory_74 [StatsItem]
                    MemoryCategory_75 [StatsItem]
                    MemoryCategory_76 [StatsItem]
                    MemoryCategory_77 [StatsItem]
                    MemoryCategory_78 [StatsItem]
                    MemoryCategory_79 [StatsItem]
                    MemoryCategory_80 [StatsItem]
                    MemoryCategory_81 [StatsItem]
                    MemoryCategory_82 [StatsItem]
                    MemoryCategory_83 [StatsItem]
                    MemoryCategory_84 [StatsItem]
                    MemoryCategory_85 [StatsItem]
                    MemoryCategory_86 [StatsItem]
                    MemoryCategory_87 [StatsItem]
                    MemoryCategory_88 [StatsItem]
                    MemoryCategory_89 [StatsItem]
                    MemoryCategory_90 [StatsItem]
                    MemoryCategory_91 [StatsItem]
                    MemoryCategory_92 [StatsItem]
                    MemoryCategory_93 [StatsItem]
                    MemoryCategory_94 [StatsItem]
                    MemoryCategory_95 [StatsItem]
                    MemoryCategory_96 [StatsItem]
                    MemoryCategory_97 [StatsItem]
                    MemoryCategory_98 [StatsItem]
                    MemoryCategory_99 [StatsItem]
                    MemoryCategory_100 [StatsItem]
                    MemoryCategory_101 [StatsItem]
                    MemoryCategory_102 [StatsItem]
                    MemoryCategory_103 [StatsItem]
                    MemoryCategory_104 [StatsItem]
                    MemoryCategory_105 [StatsItem]
                    MemoryCategory_106 [StatsItem]
                    MemoryCategory_107 [StatsItem]
                    MemoryCategory_108 [StatsItem]
                    MemoryCategory_109 [StatsItem]
                    MemoryCategory_110 [StatsItem]
                    MemoryCategory_111 [StatsItem]
                    MemoryCategory_112 [StatsItem]
                    MemoryCategory_113 [StatsItem]
                    MemoryCategory_114 [StatsItem]
                    MemoryCategory_115 [StatsItem]
                    MemoryCategory_116 [StatsItem]
                    MemoryCategory_117 [StatsItem]
                    MemoryCategory_118 [StatsItem]
                    MemoryCategory_119 [StatsItem]
                    MemoryCategory_120 [StatsItem]
                    MemoryCategory_121 [StatsItem]
                    MemoryCategory_122 [StatsItem]
                    MemoryCategory_123 [StatsItem]
                    MemoryCategory_124 [StatsItem]
                    MemoryCategory_125 [StatsItem]
                    MemoryCategory_126 [StatsItem]
                    MemoryCategory_127 [StatsItem]
                    MemoryCategory_128 [StatsItem]
                    MemoryCategory_129 [StatsItem]
                    MemoryCategory_130 [StatsItem]
                    MemoryCategory_131 [StatsItem]
                    MemoryCategory_132 [StatsItem]
                    MemoryCategory_133 [StatsItem]
                    MemoryCategory_134 [StatsItem]
                    MemoryCategory_135 [StatsItem]
                    MemoryCategory_136 [StatsItem]
                    MemoryCategory_137 [StatsItem]
                    MemoryCategory_138 [StatsItem]
                    MemoryCategory_139 [StatsItem]
                    MemoryCategory_140 [StatsItem]
                    MemoryCategory_141 [StatsItem]
                    MemoryCategory_142 [StatsItem]
                    MemoryCategory_143 [StatsItem]
                    MemoryCategory_144 [StatsItem]
                    MemoryCategory_145 [StatsItem]
                    MemoryCategory_146 [StatsItem]
                    MemoryCategory_147 [StatsItem]
                    MemoryCategory_148 [StatsItem]
                    MemoryCategory_149 [StatsItem]
                    MemoryCategory_150 [StatsItem]
                    MemoryCategory_151 [StatsItem]
                    MemoryCategory_152 [StatsItem]
                    MemoryCategory_153 [StatsItem]
                    MemoryCategory_154 [StatsItem]
                    MemoryCategory_155 [StatsItem]
                    MemoryCategory_156 [StatsItem]
                    MemoryCategory_157 [StatsItem]
                    MemoryCategory_158 [StatsItem]
                    MemoryCategory_159 [StatsItem]
                    MemoryCategory_160 [StatsItem]
                    MemoryCategory_161 [StatsItem]
                    MemoryCategory_162 [StatsItem]
                    MemoryCategory_163 [StatsItem]
                    MemoryCategory_164 [StatsItem]
                    MemoryCategory_165 [StatsItem]
                    MemoryCategory_166 [StatsItem]
                    MemoryCategory_167 [StatsItem]
                    MemoryCategory_168 [StatsItem]
                    MemoryCategory_169 [StatsItem]
                    MemoryCategory_170 [StatsItem]
                    MemoryCategory_171 [StatsItem]
                    MemoryCategory_172 [StatsItem]
                    MemoryCategory_173 [StatsItem]
                    MemoryCategory_174 [StatsItem]
                    MemoryCategory_175 [StatsItem]
                    MemoryCategory_176 [StatsItem]
                    MemoryCategory_177 [StatsItem]
                    MemoryCategory_178 [StatsItem]
                    MemoryCategory_179 [StatsItem]
                    MemoryCategory_180 [StatsItem]
                    MemoryCategory_181 [StatsItem]
                    MemoryCategory_182 [StatsItem]
                    MemoryCategory_183 [StatsItem]
                    MemoryCategory_184 [StatsItem]
                    MemoryCategory_185 [StatsItem]
                    MemoryCategory_186 [StatsItem]
                    MemoryCategory_187 [StatsItem]
                    MemoryCategory_188 [StatsItem]
                    MemoryCategory_189 [StatsItem]
                    MemoryCategory_190 [StatsItem]
                    MemoryCategory_191 [StatsItem]
                    MemoryCategory_192 [StatsItem]
                    MemoryCategory_193 [StatsItem]
                    MemoryCategory_194 [StatsItem]
                    MemoryCategory_195 [StatsItem]
                    MemoryCategory_196 [StatsItem]
                    MemoryCategory_197 [StatsItem]
                    MemoryCategory_198 [StatsItem]
                    MemoryCategory_199 [StatsItem]
                    MemoryCategory_200 [StatsItem]
                    MemoryCategory_201 [StatsItem]
                    MemoryCategory_202 [StatsItem]
                    MemoryCategory_203 [StatsItem]
                    MemoryCategory_204 [StatsItem]
                    MemoryCategory_205 [StatsItem]
                    MemoryCategory_206 [StatsItem]
                    MemoryCategory_207 [StatsItem]
                    MemoryCategory_208 [StatsItem]
                    MemoryCategory_209 [StatsItem]
                    MemoryCategory_210 [StatsItem]
                    MemoryCategory_211 [StatsItem]
                    MemoryCategory_212 [StatsItem]
                    MemoryCategory_213 [StatsItem]
                    MemoryCategory_214 [StatsItem]
                    MemoryCategory_215 [StatsItem]
                    MemoryCategory_216 [StatsItem]
                    MemoryCategory_217 [StatsItem]
                    MemoryCategory_218 [StatsItem]
                    MemoryCategory_219 [StatsItem]
                    MemoryCategory_220 [StatsItem]
                    MemoryCategory_221 [StatsItem]
                    MemoryCategory_222 [StatsItem]
                    MemoryCategory_223 [StatsItem]
                    MemoryCategory_224 [StatsItem]
                    MemoryCategory_225 [StatsItem]
                    MemoryCategory_226 [StatsItem]
                    MemoryCategory_227 [StatsItem]
                    MemoryCategory_228 [StatsItem]
                    MemoryCategory_229 [StatsItem]
                    MemoryCategory_230 [StatsItem]
                    MemoryCategory_231 [StatsItem]
                    MemoryCategory_232 [StatsItem]
                    MemoryCategory_233 [StatsItem]
                    MemoryCategory_234 [StatsItem]
                    MemoryCategory_235 [StatsItem]
                    MemoryCategory_236 [StatsItem]
                    MemoryCategory_237 [StatsItem]
                    MemoryCategory_238 [StatsItem]
                    MemoryCategory_239 [StatsItem]
                    MemoryCategory_240 [StatsItem]
                    MemoryCategory_241 [StatsItem]
                    MemoryCategory_242 [StatsItem]
                    MemoryCategory_243 [StatsItem]
                    MemoryCategory_244 [StatsItem]
                    MemoryCategory_245 [StatsItem]
                    MemoryCategory_246 [StatsItem]
                    MemoryCategory_247 [StatsItem]
                    MemoryCategory_248 [StatsItem]
                    MemoryCategory_249 [StatsItem]
                    MemoryCategory_250 [StatsItem]
                    MemoryCategory_251 [StatsItem]
                    MemoryCategory_252 [StatsItem]
                    MemoryCategory_253 [StatsItem]
                    MemoryCategory_254 [StatsItem]
                    MemoryCategory_255 [StatsItem]
                CoreScriptMemory [StatsItem]
                    MemoryCategory_0 [StatsItem]
                    MemoryCategory_1 [StatsItem]
                    MemoryCategory_2 [StatsItem]
                    MemoryCategory_3 [StatsItem]
                    MemoryCategory_4 [StatsItem]
                    MemoryCategory_5 [StatsItem]
                    MemoryCategory_6 [StatsItem]
                    MemoryCategory_7 [StatsItem]
                    MemoryCategory_8 [StatsItem]
                    MemoryCategory_9 [StatsItem]
                    MemoryCategory_10 [StatsItem]
                    MemoryCategory_11 [StatsItem]
                    MemoryCategory_12 [StatsItem]
                    MemoryCategory_13 [StatsItem]
                    MemoryCategory_14 [StatsItem]
                    MemoryCategory_15 [StatsItem]
                    MemoryCategory_16 [StatsItem]
                    MemoryCategory_17 [StatsItem]
                    MemoryCategory_18 [StatsItem]
                    MemoryCategory_19 [StatsItem]
                    MemoryCategory_20 [StatsItem]
                    MemoryCategory_21 [StatsItem]
                    MemoryCategory_22 [StatsItem]
                    MemoryCategory_23 [StatsItem]
                    MemoryCategory_24 [StatsItem]
                    MemoryCategory_25 [StatsItem]
                    MemoryCategory_26 [StatsItem]
                    MemoryCategory_27 [StatsItem]
                    MemoryCategory_28 [StatsItem]
                    MemoryCategory_29 [StatsItem]
                    MemoryCategory_30 [StatsItem]
                    MemoryCategory_31 [StatsItem]
                    MemoryCategory_32 [StatsItem]
                    MemoryCategory_33 [StatsItem]
                    MemoryCategory_34 [StatsItem]
                    MemoryCategory_35 [StatsItem]
                    MemoryCategory_36 [StatsItem]
                    MemoryCategory_37 [StatsItem]
                    MemoryCategory_38 [StatsItem]
                    MemoryCategory_39 [StatsItem]
                    MemoryCategory_40 [StatsItem]
                    MemoryCategory_41 [StatsItem]
                    MemoryCategory_42 [StatsItem]
                    MemoryCategory_43 [StatsItem]
                    MemoryCategory_44 [StatsItem]
                    MemoryCategory_45 [StatsItem]
                    MemoryCategory_46 [StatsItem]
                    MemoryCategory_47 [StatsItem]
                    MemoryCategory_48 [StatsItem]
                    MemoryCategory_49 [StatsItem]
                    MemoryCategory_50 [StatsItem]
                    MemoryCategory_51 [StatsItem]
                    MemoryCategory_52 [StatsItem]
                    MemoryCategory_53 [StatsItem]
                    MemoryCategory_54 [StatsItem]
                    MemoryCategory_55 [StatsItem]
                    MemoryCategory_56 [StatsItem]
                    MemoryCategory_57 [StatsItem]
                    MemoryCategory_58 [StatsItem]
                    MemoryCategory_59 [StatsItem]
                    MemoryCategory_60 [StatsItem]
                    MemoryCategory_61 [StatsItem]
                    MemoryCategory_62 [StatsItem]
                    MemoryCategory_63 [StatsItem]
                    MemoryCategory_64 [StatsItem]
                    MemoryCategory_65 [StatsItem]
                    MemoryCategory_66 [StatsItem]
                    MemoryCategory_67 [StatsItem]
                    MemoryCategory_68 [StatsItem]
                    MemoryCategory_69 [StatsItem]
                    MemoryCategory_70 [StatsItem]
                    MemoryCategory_71 [StatsItem]
                    MemoryCategory_72 [StatsItem]
                    MemoryCategory_73 [StatsItem]
                    MemoryCategory_74 [StatsItem]
                    MemoryCategory_75 [StatsItem]
                    MemoryCategory_76 [StatsItem]
                    MemoryCategory_77 [StatsItem]
                    MemoryCategory_78 [StatsItem]
                    MemoryCategory_79 [StatsItem]
                    MemoryCategory_80 [StatsItem]
                    MemoryCategory_81 [StatsItem]
                    MemoryCategory_82 [StatsItem]
                    MemoryCategory_83 [StatsItem]
                    MemoryCategory_84 [StatsItem]
                    MemoryCategory_85 [StatsItem]
                    MemoryCategory_86 [StatsItem]
                    MemoryCategory_87 [StatsItem]
                    MemoryCategory_88 [StatsItem]
                    MemoryCategory_89 [StatsItem]
                    MemoryCategory_90 [StatsItem]
                    MemoryCategory_91 [StatsItem]
                    MemoryCategory_92 [StatsItem]
                    MemoryCategory_93 [StatsItem]
                    MemoryCategory_94 [StatsItem]
                    MemoryCategory_95 [StatsItem]
                    MemoryCategory_96 [StatsItem]
                    MemoryCategory_97 [StatsItem]
                    MemoryCategory_98 [StatsItem]
                    MemoryCategory_99 [StatsItem]
                    MemoryCategory_100 [StatsItem]
                    MemoryCategory_101 [StatsItem]
                    MemoryCategory_102 [StatsItem]
                    MemoryCategory_103 [StatsItem]
                    MemoryCategory_104 [StatsItem]
                    MemoryCategory_105 [StatsItem]
                    MemoryCategory_106 [StatsItem]
                    MemoryCategory_107 [StatsItem]
                    MemoryCategory_108 [StatsItem]
                    MemoryCategory_109 [StatsItem]
                    MemoryCategory_110 [StatsItem]
                    MemoryCategory_111 [StatsItem]
                    MemoryCategory_112 [StatsItem]
                    MemoryCategory_113 [StatsItem]
                    MemoryCategory_114 [StatsItem]
                    MemoryCategory_115 [StatsItem]
                    MemoryCategory_116 [StatsItem]
                    MemoryCategory_117 [StatsItem]
                    MemoryCategory_118 [StatsItem]
                    MemoryCategory_119 [StatsItem]
                    MemoryCategory_120 [StatsItem]
                    MemoryCategory_121 [StatsItem]
                    MemoryCategory_122 [StatsItem]
                    MemoryCategory_123 [StatsItem]
                    MemoryCategory_124 [StatsItem]
                    MemoryCategory_125 [StatsItem]
                    MemoryCategory_126 [StatsItem]
                    MemoryCategory_127 [StatsItem]
                    MemoryCategory_128 [StatsItem]
                    MemoryCategory_129 [StatsItem]
                    MemoryCategory_130 [StatsItem]
                    MemoryCategory_131 [StatsItem]
                    MemoryCategory_132 [StatsItem]
                    MemoryCategory_133 [StatsItem]
                    MemoryCategory_134 [StatsItem]
                    MemoryCategory_135 [StatsItem]
                    MemoryCategory_136 [StatsItem]
                    MemoryCategory_137 [StatsItem]
                    MemoryCategory_138 [StatsItem]
                    MemoryCategory_139 [StatsItem]
                    MemoryCategory_140 [StatsItem]
                    MemoryCategory_141 [StatsItem]
                    MemoryCategory_142 [StatsItem]
                    MemoryCategory_143 [StatsItem]
                    MemoryCategory_144 [StatsItem]
                    MemoryCategory_145 [StatsItem]
                    MemoryCategory_146 [StatsItem]
                    MemoryCategory_147 [StatsItem]
                    MemoryCategory_148 [StatsItem]
                    MemoryCategory_149 [StatsItem]
                    MemoryCategory_150 [StatsItem]
                    MemoryCategory_151 [StatsItem]
                    MemoryCategory_152 [StatsItem]
                    MemoryCategory_153 [StatsItem]
                    MemoryCategory_154 [StatsItem]
                    MemoryCategory_155 [StatsItem]
                    MemoryCategory_156 [StatsItem]
                    MemoryCategory_157 [StatsItem]
                    MemoryCategory_158 [StatsItem]
                    MemoryCategory_159 [StatsItem]
                    MemoryCategory_160 [StatsItem]
                    MemoryCategory_161 [StatsItem]
                    MemoryCategory_162 [StatsItem]
                    MemoryCategory_163 [StatsItem]
                    MemoryCategory_164 [StatsItem]
                    MemoryCategory_165 [StatsItem]
                    MemoryCategory_166 [StatsItem]
                    MemoryCategory_167 [StatsItem]
                    MemoryCategory_168 [StatsItem]
                    MemoryCategory_169 [StatsItem]
                    MemoryCategory_170 [StatsItem]
                    MemoryCategory_171 [StatsItem]
                    MemoryCategory_172 [StatsItem]
                    MemoryCategory_173 [StatsItem]
                    MemoryCategory_174 [StatsItem]
                    MemoryCategory_175 [StatsItem]
                    MemoryCategory_176 [StatsItem]
                    MemoryCategory_177 [StatsItem]
                    MemoryCategory_178 [StatsItem]
                    MemoryCategory_179 [StatsItem]
                    MemoryCategory_180 [StatsItem]
                    MemoryCategory_181 [StatsItem]
                    MemoryCategory_182 [StatsItem]
                    MemoryCategory_183 [StatsItem]
                    MemoryCategory_184 [StatsItem]
                    MemoryCategory_185 [StatsItem]
                    MemoryCategory_186 [StatsItem]
                    MemoryCategory_187 [StatsItem]
                    MemoryCategory_188 [StatsItem]
                    MemoryCategory_189 [StatsItem]
                    MemoryCategory_190 [StatsItem]
                    MemoryCategory_191 [StatsItem]
                    MemoryCategory_192 [StatsItem]
                    MemoryCategory_193 [StatsItem]
                    MemoryCategory_194 [StatsItem]
                    MemoryCategory_195 [StatsItem]
                    MemoryCategory_196 [StatsItem]
                    MemoryCategory_197 [StatsItem]
                    MemoryCategory_198 [StatsItem]
                    MemoryCategory_199 [StatsItem]
                    MemoryCategory_200 [StatsItem]
                    MemoryCategory_201 [StatsItem]
                    MemoryCategory_202 [StatsItem]
                    MemoryCategory_203 [StatsItem]
                    MemoryCategory_204 [StatsItem]
                    MemoryCategory_205 [StatsItem]
                    MemoryCategory_206 [StatsItem]
                    MemoryCategory_207 [StatsItem]
                    MemoryCategory_208 [StatsItem]
                    MemoryCategory_209 [StatsItem]
                    MemoryCategory_210 [StatsItem]
                    MemoryCategory_211 [StatsItem]
                    MemoryCategory_212 [StatsItem]
                    MemoryCategory_213 [StatsItem]
                    MemoryCategory_214 [StatsItem]
                    MemoryCategory_215 [StatsItem]
                    MemoryCategory_216 [StatsItem]
                    MemoryCategory_217 [StatsItem]
                    MemoryCategory_218 [StatsItem]
                    MemoryCategory_219 [StatsItem]
                    MemoryCategory_220 [StatsItem]
                    MemoryCategory_221 [StatsItem]
                    MemoryCategory_222 [StatsItem]
                    MemoryCategory_223 [StatsItem]
                    MemoryCategory_224 [StatsItem]
                    MemoryCategory_225 [StatsItem]
                    MemoryCategory_226 [StatsItem]
                    MemoryCategory_227 [StatsItem]
                    MemoryCategory_228 [StatsItem]
                    MemoryCategory_229 [StatsItem]
                    MemoryCategory_230 [StatsItem]
                    MemoryCategory_231 [StatsItem]
                    MemoryCategory_232 [StatsItem]
                    MemoryCategory_233 [StatsItem]
                    MemoryCategory_234 [StatsItem]
                    MemoryCategory_235 [StatsItem]
                    MemoryCategory_236 [StatsItem]
                    MemoryCategory_237 [StatsItem]
                    MemoryCategory_238 [StatsItem]
                    MemoryCategory_239 [StatsItem]
                    MemoryCategory_240 [StatsItem]
                    MemoryCategory_241 [StatsItem]
                    MemoryCategory_242 [StatsItem]
                    MemoryCategory_243 [StatsItem]
                    MemoryCategory_244 [StatsItem]
                    MemoryCategory_245 [StatsItem]
                    MemoryCategory_246 [StatsItem]
                    MemoryCategory_247 [StatsItem]
                    MemoryCategory_248 [StatsItem]
                    MemoryCategory_249 [StatsItem]
                    MemoryCategory_250 [StatsItem]
                    MemoryCategory_251 [StatsItem]
                    MemoryCategory_252 [StatsItem]
                    MemoryCategory_253 [StatsItem]
                    MemoryCategory_254 [StatsItem]
                    MemoryCategory_255 [StatsItem]
            MaxMemory [StatsItem]
            CPU [StatsItem]
            MaxCPU [StatsItem]
            GPU [StatsItem]
            MaxGPU [StatsItem]
            Ping [StatsItem]
            MaxPing [StatsItem]
            NetworkReceived [StatsItem]
            MaxNetworkReceived [StatsItem]
            NetworkSent [StatsItem]
            MaxNetworkSent [StatsItem]
        RenderBreakdown [StatsItem]
            Undefined [StatsItem]
            Opaque [StatsItem]
            Transparent [StatsItem]
            Terrain [StatsItem]
            Grass [StatsItem]
            UI [StatsItem]
            Decal [StatsItem]
            Cloud [StatsItem]
            GenericPostProcess [StatsItem]
            SSAO [StatsItem]
            DOF [StatsItem]
            Particles [StatsItem]
            Sky [StatsItem]
        Workspace [StatsItem]
            FPS [StatsItem]
            Heartbeat [StatsItem]
            Environment Speed % [StatsItem]
            World [StatsItem]
                Primitives [StatsItem]
                Joints [StatsItem]
                Contacts [StatsItem]
                Non-Anchored Assemblies [StatsItem]
                Sleeping Assemblies [StatsItem]
                Sleep Checking Assemblies [StatsItem]
                Awake Assemblies [StatsItem]
            Contacts [StatsItem]
                CtctStageCtcts [StatsItem]
                SteppingCtcts [StatsItem]
            Kernel [StatsItem]
                Constraints [StatsItem]
            File Operations [StatsItem]
                Total Load Time [StatsItem]
                SyncHttpGet Time [StatsItem]
                XML Load Time [StatsItem]
                Join All Time [StatsItem]
        Sound [StatsItem]
            CPU [StatsItem]
                Dsp [StatsItem]
                Stream [StatsItem]
                Geometry [StatsItem]
                Update [StatsItem]
            ChannelsPlaying [StatsItem]
            Current [StatsItem]
            Max [StatsItem]
            # Sounds [StatsItem]
            # Unused [StatsItem]
        ChangeHistory [StatsItem]
            Data Size [StatsItem]
            Constrained Data Size [StatsItem]
            Stack Size [StatsItem]
        Network [StatsItem]
            Packets Thread [StatsItem]
                Rate [StatsItem]
                Activity [StatsItem]
                Physics Senders [StatsItem]
                Send Buffer Health [StatsItem]
            ServerStatsItem [StatsItem]
                Network Ping [StatsItem]
                Data Ping [RunningAverageItemInt]
                StreamingEnabled [StatsItem]
                Compression [StatsItem]
                Stats [StatsItem]
                    messageDataBytesSentPerSec [StatsItem]
                    messageTotalBytesSentPerSec [StatsItem]
                    messageDataBytesResentPerSec [StatsItem]
                    messagesBytesReceivedPerSec [StatsItem]
                    messagesBytesReceivedAndIgnoredPerSec [StatsItem]
                    bytesSentPerSec [StatsItem]
                    bytesReceivedPerSec [StatsItem]
                    totalMessageBytesPushed [StatsItem]
                    totalMessageBytesSent [StatsItem]
                    totalMessageBytesResent [StatsItem]
                    totalMessagesBytesReceived [StatsItem]
                    totalMessagesBytesReceivedAndIgnored [StatsItem]
                    totalBytesSent [StatsItem]
                    totalBytesReceived [StatsItem]
                    connectionStartTime [StatsItem]
                    outgoingBandwidthLimitBytesPerSecond [StatsItem]
                    isLimitedByOutgoingBandwidthLimit [StatsItem]
                    congestionControlLimitBytesPerSecond [StatsItem]
                    isLimitedByCongestionControl [StatsItem]
                    messageSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    bytesInSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    messagesInResendQueue [StatsItem]
                    bytesInResendQueue [StatsItem]
                    packetlossLastSecond [StatsItem]
                    packetlossTotal [StatsItem]
                    numberOfUnsplitMessages [StatsItem]
                    numberOfSplitMessages [StatsItem]
                    messageDataBytesSentPerSec [StatsItem]
                    messageTotalBytesSentPerSec [StatsItem]
                    messageDataBytesResentPerSec [StatsItem]
                    messagesBytesReceivedPerSec [StatsItem]
                    messagesBytesReceivedAndIgnoredPerSec [StatsItem]
                    bytesSentPerSec [StatsItem]
                    bytesReceivedPerSec [StatsItem]
                    totalMessageBytesPushed [StatsItem]
                    totalMessageBytesSent [StatsItem]
                    totalMessageBytesResent [StatsItem]
                    totalMessagesBytesReceived [StatsItem]
                    totalMessagesBytesReceivedAndIgnored [StatsItem]
                    totalBytesSent [StatsItem]
                    totalBytesReceived [StatsItem]
                    connectionStartTime [StatsItem]
                    outgoingBandwidthLimitBytesPerSecond [StatsItem]
                    isLimitedByOutgoingBandwidthLimit [StatsItem]
                    congestionControlLimitBytesPerSecond [StatsItem]
                    isLimitedByCongestionControl [StatsItem]
                    messageSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    bytesInSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    messagesInResendQueue [StatsItem]
                    bytesInResendQueue [StatsItem]
                    packetlossLastSecond [StatsItem]
                    packetlossTotal [StatsItem]
                    numberOfUnsplitMessages [StatsItem]
                    numberOfSplitMessages [StatsItem]
                Send kBps [StatsItem]
                    MtuSize [StatsItem]
                Send Buffer Health [StatsItem]
                BandwidthExceeded [StatsItem]
                CongestionControlExceeded [StatsItem]
                Receive kBps [StatsItem]
                Packet Queue [StatsItem]
                Sent Data Packets [StatsItem]
                    Size [RunningAverageItemInt]
                    Throttle [StatsItem]
                    Queue Size [StatsItem]
                    Time In Queue [StatsItem]
                    New Items Per Sec [TotalCountTimeIntervalItem]
                    Items Sent Per Sec [TotalCountTimeIntervalItem]
                OutPhysicsDetails [StatsItem]
                    CFrameOnly [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Mechanism [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Translation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Rotation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Velocity [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                InPhysicsDetails [StatsItem]
                    CFrameOnly [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Mechanism [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Translation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Rotation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Velocity [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                DataPingDetails [StatsItem]
                    LQToS [StatsItem]
                    LBcsQ [StatsItem]
                    RakPing [StatsItem]
                    RRakRecvToAppPop [StatsItem]
                    RAppPopToDeserialize [StatsItem]
                    RDeserializeToPBQ [StatsItem]
                    RQToS [StatsItem]
                    RBscQ [StatsItem]
                    LRakRecvToAppPop [StatsItem]
                    LAppPopToSerialize [StatsItem]
                    LDeserializeToProcess [StatsItem]
                    EstTotal [StatsItem]
                    MeasuredTotal [StatsItem]
                    unrelLQToS [StatsItem]
                    unrelLBcsQ [StatsItem]
                    unrelRakPing [StatsItem]
                    unrelRRakRecvToAppPop [StatsItem]
                    unrelRAppPopToDeserialize [StatsItem]
                    unrelRDeserializeToPBQ [StatsItem]
                    unrelRQToS [StatsItem]
                    unrelRBscQ [StatsItem]
                    unrelLRakRecvToAppPop [StatsItem]
                    unrelLAppPopToSerialize [StatsItem]
                    unrelLDeserializeToProcess [StatsItem]
                    unrelEstTotal [StatsItem]
                    unrelMeasuredTotal [StatsItem]
                Send Data Types [StatsItem]
                    InstanceNew [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDelete [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Ping [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Data [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Behavior [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    State [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Appearance [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Team [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Video [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Control [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Events [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDestroy [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                Received Data Types [StatsItem]
                    InstanceNew [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDelete [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Ping [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Data [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Behavior [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    State [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Appearance [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Team [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Video [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Control [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Events [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDestroy [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                Sent Physics Packets [StatsItem]
                    Size [RunningAverageItemInt]
                    Throttle [StatsItem]
                    Smoothed [StatsItem]
                    Items Per Packet [RunningAverageItemInt]
                SentTouchPackets [StatsItem]
                    Size [RunningAverageItemInt]
                    WaitingTouches [RunningAverageItemInt]
                Received Packets [StatsItem]
                Received Data Packets [StatsItem]
                    Queue Size [StatsItem]
                    Instance Size [StatsItem]
                    Waiting Refs [StatsItem]
                    Size [StatsItem]
                Received ISR Packets [StatsItem]
                    Size [StatsItem]
                Received LR Packets [StatsItem]
                    Size [StatsItem]
                Received Physics Packets [StatsItem]
                    Average Lag [StatsItem]
                    Average Buffer Seek [StatsItem]
                    Max Buffer Seek [StatsItem]
                    Wrong Order [StatsItem]
                    Size [StatsItem]
                Sent ISR Packets [StatsItem]
                    Size [StatsItem]
                In ISR Physics Details [StatsItem]
                    Mechanism [StatsItem]
                        Size [StatsItem]
                    CFrameOnly [StatsItem]
                        Size [StatsItem]
                    Translation [StatsItem]
                        Size [StatsItem]
                    Rotation [StatsItem]
                        Size [StatsItem]
                    Velocity [StatsItem]
                        Size [StatsItem]
                Out ISR Physics Details [StatsItem]
                    Mechanism [StatsItem]
                        Size [StatsItem]
                    CFrameOnly [StatsItem]
                        Size [StatsItem]
                    Translation [StatsItem]
                        Size [StatsItem]
                    Rotation [StatsItem]
                        Size [StatsItem]
                    Velocity [StatsItem]
                        Size [StatsItem]
                Sent Cluster Packets [StatsItem]
                    Size [RunningAverageItemInt]
                Received Cluster Packets [StatsItem]
                    Size [StatsItem]
                Received Touch Packets [StatsItem]
                    Size [StatsItem]
                ElapsedTime [StatsItem]
                MaxPacketLoss [StatsItem]
                TotalInDataBW [StatsItem]
                TotalOutDataBW [StatsItem]
                TotalRakIn [StatsItem]
                TotalRakOut [StatsItem]
                OutBufferHealth [StatsItem]
                PropSync [StatsItem]
                    ItemCount [StatsItem]
                    AckCount [StatsItem]
                Received Stream Data [StatsItem]
                    AvgReadTimePerItem [RunningAverageItemDouble]
                    AvgInstancesPerItem [RunningAverageItemDouble]
                    RequestedInstanceAvg [RunningAverageItemInt]
                    PendingRequestCount [StatsItem]
                    GCDistance [StatsItem]
                    NumRegions [StatsItem]
                    CurrentRadius [StatsItem]
                    NumReplicationFoci [StatsItem]
                    NumPrefetches [StatsItem]
                    PlayerPosition [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                    PlayerRegion [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                    LastKnownServerStreamCenter [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                Lr Data [StatsItem]
                    LrBytesRecv [StatsItem]
                    LrSegmentsRecv [StatsItem]
                    LrEstimatedRawRecv [StatsItem]
                    LrEstimatedOptimizedRecv [StatsItem]
                    LrActualPreCompressRecv [StatsItem]
                    LrActualPostCompressRecv [StatsItem]
                    LrAssetsRecv [StatsItem]
                    LrAssetsByDeltaRecv [StatsItem]
                    LrDeltasRecv [StatsItem]
                    LrCancelRecv [StatsItem]
                    LrRemoveRecv [StatsItem]
                    LrCompleteRecv [StatsItem]
                    LrInlineRecv [StatsItem]
                    LrIgnoreRecv [StatsItem]
                    LrHashFail [StatsItem]
                    LrHashCheck [StatsItem]
                    LrMemCountRecv [StatsItem]
                    LrMemEstBytesRecv [StatsItem]
        Luau [StatsItem]
            disabled [StatsItem]
            threads [StatsItem]
            AverageGcTime [StatsItem]
        FrameRateManager [StatsItem]
            DeviceFeatureLevel [StatsItem]
            DeviceShadingLanguage [StatsItem]
            AverageQualityLevel [StatsItem]
            AutoQuality [StatsItem]
            NumberOfSettles [StatsItem]
            AverageSwitches [StatsItem]
            FramebufferWidth [StatsItem]
            FramebufferHeight [StatsItem]
            Batches [StatsItem]
            Indices [StatsItem]
            MaterialChanges [StatsItem]
            VideoMemoryInMB [StatsItem]
            AverageFPS [StatsItem]
            FrameTimeVariance [StatsItem]
            FrameSpikeCount [StatsItem]
            RenderAverage [StatsItem]
            PrepareAverage [StatsItem]
            PerformAverage [StatsItem]
            AveragePresent [StatsItem]
            AverageGPU [StatsItem]
            RenderThreadAverage [StatsItem]
            TotalFrameWallAverage [StatsItem]
            PerformVariance [StatsItem]
            PresentVariance [StatsItem]
            GpuVariance [StatsItem]
            MsFrame0 [StatsItem]
            MsFrame1 [StatsItem]
            MsFrame2 [StatsItem]
            MsFrame3 [StatsItem]
            MsFrame4 [StatsItem]
            MsFrame5 [StatsItem]
            MsFrame6 [StatsItem]
            MsFrame7 [StatsItem]
            MsFrame8 [StatsItem]
            MsFrame9 [StatsItem]
            MsFrame10 [StatsItem]
            MsFrame11 [StatsItem]
        Render [StatsItem]
            Memory [StatsItem]
                Video [StatsItem]
    TimerService [TimerService]
    CollectionService [CollectionService]
    SoundService [SoundService]
    VideoCaptureService [VideoCaptureService]
    LogService [LogService]
    MicroProfilerService [MicroProfilerService]
    ContentProvider [ContentProvider]
    KeyframeSequenceProvider [KeyframeSequenceProvider]
    AnimationClipProvider [AnimationClipProvider]
    Chat [Chat]
    MarketplaceService [MarketplaceService]
    Players [Players]
        hydrazx9 [Player]
            PlayerScripts [PlayerScripts]
            Backpack [Backpack]
    PointsService [PointsService]
    NotificationService [NotificationService]
    ReplicatedFirst [ReplicatedFirst]
    HttpRbxApiService [HttpRbxApiService]
    TweenService [TweenService]
    MaterialService [MaterialService]
    TextChatService [TextChatService]
        BubbleChatConfiguration [BubbleChatConfiguration]
            ImageLabel [ImageLabel]
            UICorner [UICorner]
            UIGradient [UIGradient]
            UIPadding [UIPadding]
        ChannelTabsConfiguration [ChannelTabsConfiguration]
        ChatInputBarConfiguration [ChatInputBarConfiguration]
        ChatWindowConfiguration [ChatWindowConfiguration]
    TextService [TextService]
    PermissionsService [PermissionsService]
    SharedTableRegistry [SharedTableRegistry]
    StarterPlayer [StarterPlayer]
        StarterCharacterScripts [StarterCharacterScripts]
        StarterPlayerScripts [StarterPlayerScripts]
            ClientMain [LocalScript]
                ----- SOURCE -----
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)

Registry.AutoLoadConfigs(ReplicatedStorage:WaitForChild("Configs"))
Net.Init()

local Client = script.Parent:WaitForChild("Client")
local Render = require(Client.ClientRenderEngine)
local Placement = require(Client.PlacementController)
local ShopUI = require(Client.ShopUI)

Render.Init()
Placement.Init(Render)
ShopUI.Init(Placement, Render)

local okChat, errChat = pcall(function()
	require(Client.ChatCommands).Init()
end)
if not okChat then
	warn("[ChatCommands] " .. tostring(errChat))
end

Net.Request():InvokeServer("ClientReady")

                ----- END SOURCE -----
            LocalScript [LocalScript]
                ----- SOURCE -----
local StarterGui = game:GetService("StarterGui")

-- Desativa completamente a barra de inventário (Backpack) da tela do jogador
StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Backpack, false)
                ----- END SOURCE -----
            Client [Folder]
                Animators [ModuleScript]
                    ----- SOURCE -----
--[[
	Animators: escolhe o animador de cada unidade pelo config. O ClientRenderEngine só fala com esta fábrica.
	Animation = { Mode = "Procedural" }   -- padrão: poses por nome de junta (UnitAnimator)
	Animation = { Mode = "Rig", ... }     -- animações reais do Animation Editor (RigAnimator)
	Os dois têm o mesmo contrato: :SetPivot(cf) :SetSpeed(s) :Trigger(nome, aoSoltar) :Kill() :Step(dt) e .DeathTime
]]
local UnitAnimator = require(script.Parent.UnitAnimator)
local RigAnimator = require(script.Parent.RigAnimator)

local Animators = {}

function Animators.IsRig(cfg)
	return cfg.Animation ~= nil and cfg.Animation.Mode == "Rig"
end

function Animators.new(model, role, cfg)
	if not model:IsA("Model") then
		return nil
	end
	if Animators.IsRig(cfg) then
		return RigAnimator.new(model, role, cfg)
	end
	return UnitAnimator.new(model, role, cfg)
end

return Animators

                    ----- END SOURCE -----
                ClientRenderEngine [ModuleScript]
                    ----- SOURCE -----
--[[
	ClientRenderEngine: 100% do visual roda aqui. Nenhum inimigo existe como Instance no servidor.
	- Inimigo: posição = path:PositionAt(min(D + S * (agora - T), comprimento)), com agora = workspace:GetServerTimeNow().
	  O servidor só manda âncora (D,T) + velocidade (S) no spawn e quando a velocidade muda (slow/freeze).
	- Partes simples são movidas em lote com BulkMoveTo (1 chamada/frame).
	- Projétil: lerp de origem -> posição PREVISTA do inimigo em T1 (hora do impacto, vinda do servidor).
	Assets opcionais: ReplicatedStorage.Assets.Models.{Towers,Enemies,Projectiles}.<ModelName> (também vale Assets.<Pasta> direto).
	  Torres/inimigos = Models com PrimaryPart (torre: pivô na base; inimigo: pivô no centro da altura de Visual.Size).
	  Projétil = Model com PrimaryPart apontando p/ -Z; Visual.Projectile.ModelName escolhe o modelo (Attribute BaseSize = escala 1).
	  Modelos com juntas são animados pelo UnitAnimator (procedural, funciona com partes ancoradas).
]]
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local RunService = game:GetService("RunService")
local TweenService = game:GetService("TweenService")
local Debris = game:GetService("Debris")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local EventBus = require(Shared.EventBus)
local Net = require(Shared.Net)
local PathUtil = require(Shared.PathUtil)
local Animators = require(script.Parent.Animators)

local Render = {
	Enemies = {},
	Towers = {},
	Map = nil,
	State = nil,
	Data = { Coins = 0 },
	Loadout = {},
	Events = EventBus.new(), -- "TowerChanged"(id) · "TowerRemoved"(id) · "GameState"(state) · "PlayerData"(data)
	Folder = nil,
	TowersFolder = nil,
}

local enemiesFolder, fxFolder
local projectiles = {}
local dying = {} -- modelos animados tocando a animação de morte
local pendingSpawns = {}
local bulkParts, bulkCFrames = {}, {}

local function serverNow()
	return workspace:GetServerTimeNow()
end

local function findIn(root, kind, name)
	local folder = root and root:FindFirstChild(kind)
	return folder and folder:FindFirstChild(name)
end

local function cloneAsset(kind, name, canQuery, rig)
	if not name then
		return nil
	end
	local assets = ReplicatedStorage:FindFirstChild("Assets")
	local models = assets and assets:FindFirstChild("Models")
	local template = findIn(models, kind, name) or findIn(assets, kind, name)
	if not template then
		return nil
	end
	local clone = template:Clone()
	-- rig = animações reais: só a PrimaryPart fica ancorada; o resto segue pelas juntas (Motor6D/Weld).
	-- procedural: tudo ancorado (o UnitAnimator move as peças em lote).
	local root = rig and clone:IsA("Model") and clone.PrimaryPart or nil
	local parts = clone:GetDescendants()
	table.insert(parts, clone)
	for _, d in ipairs(parts) do
		if d:IsA("BasePart") then
			d.CanCollide = false
			d.CanQuery = canQuery
			if root then
				d.Anchored = d == root
				d.Massless = true
			else
				d.Anchored = true
			end
		end
	end
	return clone
end

local function makePart(size, color, canQuery)
	local part = Instance.new("Part")
	part.Anchored = true
	part.CanCollide = false
	part.CanTouch = false
	part.CanQuery = canQuery
	part.Size = size
	part.Color = color
	part.Material = Enum.Material.SmoothPlastic
	return part
end

-- ---------------------------------------------------------------- anel de alcance (usado por UI/placement)
function Render.MakeRing(color)
	local ring = Instance.new("Part")
	ring.Shape = Enum.PartType.Cylinder
	ring.Anchored = true
	ring.CanCollide = false
	ring.CanTouch = false
	ring.CanQuery = false
	ring.Material = Enum.Material.Neon
	ring.Transparency = 0.8
	ring.Color = color or Color3.fromRGB(255, 255, 255)
	return ring
end

function Render.PlaceRing(ring, pos, range)
	ring.Size = Vector3.new(0.2, range * 2, range * 2)
	ring.CFrame = CFrame.new(pos + Vector3.new(0, 0.15, 0)) * CFrame.Angles(0, 0, math.rad(90))
end

function Render.TowerCost(def)
	local m = Render.Map and Render.Map.Config.Multipliers
	return math.ceil(def.Cost * (m and m.TowerCost or 1))
end

function Render.PickTower(inst)
	local cur = inst
	while cur and cur ~= Render.TowersFolder do
		local id = cur:GetAttribute("TDTowerId")
		if id then
			return id
		end
		cur = cur.Parent
	end
	return nil
end

-- ---------------------------------------------------------------- inimigos
local function adornee(r)
	if r.IsPart then
		return r.Inst
	end
	return r.Inst.PrimaryPart or r.Inst:FindFirstChildWhichIsA("BasePart", true)
end

local function updateBar(r)
	if r.Hp >= r.MaxHp and not r.Bar then
		return
	end
	if not r.Bar then
		local gui = Instance.new("BillboardGui")
		gui.Size = UDim2.fromOffset(60, 8)
		gui.StudsOffset = Vector3.new(0, r.BarY, 0)
		gui.AlwaysOnTop = true
		gui.Adornee = adornee(r)
		local back = Instance.new("Frame")
		back.Size = UDim2.fromScale(1, 1)
		back.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
		back.BorderSizePixel = 0
		back.Parent = gui
		local fill = Instance.new("Frame")
		fill.Name = "Fill"
		fill.Size = UDim2.fromScale(1, 1)
		fill.BackgroundColor3 = Color3.fromRGB(90, 220, 90)
		fill.BorderSizePixel = 0
		fill.Parent = back
		gui.Parent = r.Inst
		r.Bar = gui
	end
	r.Bar.Frame.Fill.Size = UDim2.fromScale(math.clamp(r.Hp / r.MaxHp, 0, 1), 1)
end

local function applyTint(r)
	local color = r.BaseColor
	for _, c in pairs(r.Tints) do
		color = c
		break
	end
	if r.IsPart then
		r.Inst.Color = color
	elseif r.TintParts then
		local tinted = next(r.Tints) ~= nil
		for part, original in pairs(r.TintParts) do
			part.Color = tinted and color or original
		end
	end
end

local function newEnemy(p)
	if Render.Enemies[p.Id] then
		return
	end
	local cfg = Registry.Of("Enemies"):Get(p.Cfg)
	local path = Render.Map and Render.Map.Paths[p.Path]
	if not cfg or not path then
		return
	end
	local vis = cfg.Visual or {}
	local size = vis.Size or Vector3.new(2, 3, 2)
	local inst = cloneAsset("Enemies", cfg.ModelName, false, Animators.IsRig(cfg))
	if not inst then
		inst = makePart(size, vis.Color or Color3.fromRGB(200, 60, 60), false)
	end
	inst.Parent = enemiesFolder
	local isPart = inst:IsA("BasePart")
	local anim = not isPart and inst:IsA("Model") and Animators.new(inst, "Enemy", cfg) or nil
	local tintParts
	if not isPart then
		tintParts = {}
		for _, d in ipairs(inst:GetDescendants()) do
			if d:IsA("BasePart") and d.Transparency < 1 then
				tintParts[d] = d.Color
			end
		end
	end
	local r = {
		Id = p.Id,
		Cfg = cfg,
		Path = path,
		Inst = inst,
		IsPart = isPart,
		D = p.D,
		T = p.T,
		S = p.S,
		Hp = p.Hp,
		MaxHp = p.MaxHp,
		YOffset = size.Y / 2,
		BarY = (isPart and size.Y / 2 or inst:GetAttribute("BarHeight") or size.Y / 2) + 1.5,
		Anim = anim,
		TintParts = tintParts,
		Tints = {},
		BaseColor = isPart and inst.Color or Color3.new(1, 1, 1),
		LastPos = path:PositionAt(p.D),
	}
	Render.Enemies[p.Id] = r
	updateBar(r)
end

local function removeEnemy(id, reason)
	local r = Render.Enemies[id]
	if not r then
		return
	end
	Render.Enemies[id] = nil
	if r.Bar then
		r.Bar:Destroy()
	end
	if reason == "Killed" and r.IsPart then
		TweenService:Create(r.Inst, TweenInfo.new(0.25), { Transparency = 1, Size = r.Inst.Size * 0.3 }):Play()
		Debris:AddItem(r.Inst, 0.3)
	elseif reason == "Killed" and r.Anim then
		r.Anim:Kill()
		table.insert(dying, { Anim = r.Anim, Inst = r.Inst, Age = 0 })
	else
		r.Inst:Destroy()
	end
end

-- ---------------------------------------------------------------- torres
local function newTower(p)
	local cfg = Registry.Of("Towers"):Get(p.Cfg)
	if not cfg or Render.Towers[p.Id] then
		return
	end
	local vis = cfg.Visual or {}
	local size = vis.Size or Vector3.new(3, 4, 3)
	local inst = cloneAsset("Towers", cfg.ModelName, true, Animators.IsRig(cfg))
	local anim, muzzle
	if inst then
		inst:PivotTo(CFrame.new(p.Pos))
		if inst:IsA("Model") then
			anim = Animators.new(inst, "Tower", cfg)
			muzzle = inst:FindFirstChild("Muzzle", true)
			if muzzle and not muzzle:IsA("Attachment") then
				muzzle = nil
			end
		end
	else
		inst = makePart(size, vis.Color or Color3.fromRGB(200, 200, 200), true)
		inst.Position = p.Pos + Vector3.new(0, size.Y / 2, 0)
	end
	inst:SetAttribute("TDTowerId", p.Id)
	inst.Parent = Render.TowersFolder
	Render.Towers[p.Id] = {
		Id = p.Id,
		Cfg = cfg,
		Inst = inst,
		Position = p.Pos,
		Owner = p.Owner,
		Range = p.Range,
		Splash = p.Splash,
		Tiers = p.Tiers,
		Mode = p.Mode,
		Invested = p.Invested,
		Damage = p.Damage,
		Interval = p.Interval,
		Height = size.Y * 0.8,
		Anim = anim,
		Muzzle = muzzle,
	}
	Render.Events:Fire("TowerChanged", p.Id)
end

local function tierSum(tiers)
	local n = 0
	for _, v in pairs(tiers) do
		n += v
	end
	return n
end

local function updateTower(p)
	local t = Render.Towers[p.Id]
	if not t then
		return
	end
	local upgraded = tierSum(p.Tiers) > tierSum(t.Tiers)
	t.Range, t.Splash, t.Tiers, t.Mode, t.Invested = p.Range, p.Splash, p.Tiers, p.Mode, p.Invested
	t.Damage, t.Interval = p.Damage, p.Interval
	if upgraded and t.Anim then
		t.Anim:Trigger("Upgrade")
	end
	Render.Events:Fire("TowerChanged", p.Id)
end

local function removeTower(id)
	local t = Render.Towers[id]
	if not t then
		return
	end
	Render.Towers[id] = nil
	t.Inst:Destroy()
	Render.Events:Fire("TowerRemoved", id)
end

-- ---------------------------------------------------------------- projéteis / fx
local function impactFx(pos, radius, color)
	local fx = Instance.new("Part")
	fx.Shape = Enum.PartType.Ball
	fx.Anchored = true
	fx.CanCollide = false
	fx.CanQuery = false
	fx.CanTouch = false
	fx.Material = Enum.Material.Neon
	fx.Transparency = 0.4
	fx.Color = color
	fx.Size = Vector3.one
	fx.Position = pos
	fx.Parent = fxFolder
	TweenService
		:Create(fx, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {
			Size = Vector3.one * radius * 2,
			Transparency = 1,
		})
		:Play()
	Debris:AddItem(fx, 0.35)
end

local function placeProjectile(pr, pos)
	if pr.IsAsset then
		local d = pos - pr.LastPos
		if d.Magnitude > 1e-3 then
			pr.Dir = d.Unit
		end
		pr.LastPos = pos
		pr.Part:PivotTo(CFrame.lookAt(pos, pos + pr.Dir))
	else
		pr.Part.Position = pos
	end
end

-- impacto de projétil com modelo próprio: emissores com atributo EmitCount soltam uma rajada, rastros param,
-- o corpo some (exceto peças com atributo KeepOnImpact) e o modelo fica ImpactLifetime segundos para os efeitos terminarem
local function projectileImpact(pr)
	local inst = pr.Part
	if not pr.IsAsset then
		inst:Destroy()
		return
	end
	inst:PivotTo(CFrame.lookAt(pr.Target, pr.Target + pr.Dir))
	for _, d in ipairs(inst:GetDescendants()) do
		if d:IsA("ParticleEmitter") then
			d.Enabled = false
			local count = d:GetAttribute("EmitCount")
			if count then
				d:Emit(count)
			end
		elseif d:IsA("Trail") then
			d.Enabled = false
		elseif d:IsA("BasePart") and not d:GetAttribute("KeepOnImpact") then
			d.Transparency = 1
		end
	end
	Debris:AddItem(inst, pr.Cfg.ImpactLifetime or 1.5)
end

local function fireTower(f)
	local tw = Render.Towers[f.Tower]
	if not tw then
		return
	end
	local en = Render.Enemies[f.Enemy]
	local pv = tw.Cfg.Visual and tw.Cfg.Visual.Projectile or {}

	if en then
		local look = Vector3.new(en.LastPos.X, tw.Position.Y, en.LastPos.Z)
		if look ~= tw.Position then
			local rot = CFrame.lookAt(tw.Position, look)
			if tw.Anim then
				tw.Anim:SetPivot(rot)
			else
				tw.Inst:PivotTo(rot)
			end
		end
	end

	local fallback = en and en.LastPos or tw.Position
	local launched = false

	-- o projétil sai no instante de "soltar" da animação (procedural: ReleaseTime; rig: marcador "Release")
	local function launch()
		if launched or not Render.Towers[tw.Id] then
			return
		end
		launched = true
		if tw.Anim then
			tw.Anim:Step(0) -- aplica a pose atual: o Muzzle precisa estar no lugar certo
		end
		local now = serverNow()
		local cur = Render.Enemies[f.Enemy]
		local origin = tw.Muzzle and tw.Muzzle.WorldPosition or (tw.Position + Vector3.new(0, tw.Height, 0))
		local target = cur and cur.LastPos or fallback
		local flat = target - origin
		local dir = flat.Magnitude > 1e-3 and flat.Unit or Vector3.new(0, 0, -1)

		local part = pv.ModelName and cloneAsset("Projectiles", pv.ModelName, false)
		local isAsset = part ~= nil
		if isAsset then
			local base = part:GetAttribute("BaseSize")
			if base and pv.Size and part:IsA("Model") then
				part:ScaleTo(pv.Size / base)
			end
			part:PivotTo(CFrame.lookAt(origin, origin + dir))
			part.Parent = fxFolder
		else
			part = Instance.new("Part")
			part.Shape = Enum.PartType.Ball
			part.Anchored = true
			part.CanCollide = false
			part.CanQuery = false
			part.CanTouch = false
			part.Material = Enum.Material.Neon
			part.Color = pv.Color or Color3.fromRGB(255, 255, 255)
			part.Size = Vector3.one * (pv.Size or 0.7)
			part.Position = origin
			part.Parent = fxFolder
		end
		table.insert(projectiles, {
			Part = part,
			IsAsset = isAsset,
			Cfg = pv,
			LastPos = origin,
			Dir = dir,
			From = origin,
			EnemyId = f.Enemy,
			T0 = now,
			T1 = math.max(f.T1, now + 0.1), -- o acerto é decidido pelo servidor (T1); mínimo de 0.1s visível
			Arc = pv.Arc or 0,
			Splash = tw.Splash,
			Color = pv.Color or Color3.fromRGB(255, 255, 255),
			Target = target,
		})
	end

	if tw.Anim then
		tw.Anim:Trigger("Attack", launch)
	else
		launch()
	end
end

-- ---------------------------------------------------------------- loop de render
local function step(dt)
	local t = serverNow()

	local n = 0
	for _, r in pairs(Render.Enemies) do
		local d = r.D + r.S * (t - r.T)
		local len = r.Path.Length
		if d > len then
			d = len
		elseif d < 0 then
			d = 0
		end
		local pos = r.Path:PositionAt(d)
		r.LastPos = pos
		local center = pos + Vector3.new(0, r.YOffset, 0)
		local cf = CFrame.lookAt(center, center + r.Path:DirectionAt(d))
		if r.IsPart then
			n += 1
			bulkParts[n] = r.Inst
			bulkCFrames[n] = cf
		elseif r.Anim then
			r.Anim:SetPivot(cf)
			r.Anim:SetSpeed(r.S)
			r.Anim:Step(dt)
		else
			r.Inst:PivotTo(cf)
		end
	end
	for i = #bulkParts, n + 1, -1 do
		bulkParts[i] = nil
		bulkCFrames[i] = nil
	end
	if n > 0 then
		workspace:BulkMoveTo(bulkParts, bulkCFrames, Enum.BulkMoveMode.FireCFrameChanged)
	end

	for _, tw in pairs(Render.Towers) do
		if tw.Anim then
			tw.Anim:Step(dt)
		end
	end
	for i = #dying, 1, -1 do
		local d = dying[i]
		d.Age += dt
		d.Anim:Step(dt)
		if d.Age >= (d.Anim.DeathTime or 0.5) then
			d.Inst:Destroy()
			table.remove(dying, i)
		end
	end

	for i = #projectiles, 1, -1 do
		local pr = projectiles[i]
		local en = Render.Enemies[pr.EnemyId]
		if en then
			local d = math.min(en.D + en.S * (pr.T1 - en.T), en.Path.Length)
			pr.Target = en.Path:PositionAt(d) + Vector3.new(0, en.YOffset, 0)
		end
		local alpha = (t - pr.T0) / (pr.T1 - pr.T0)
		if alpha >= 1 then
			if pr.Splash > 0 then
				impactFx(pr.Target, pr.Splash, pr.Color)
			end
			projectileImpact(pr)
			table.remove(projectiles, i)
		else
			alpha = math.max(alpha, 0)
			local pos = pr.From:Lerp(pr.Target, alpha)
			if pr.Arc > 0 then
				pos += Vector3.new(0, math.sin(math.pi * alpha) * pr.Arc, 0)
			end
			placeProjectile(pr, pos)
		end
	end
end

-- ---------------------------------------------------------------- rede
local function setMap(mapId)
	for _, r in pairs(Render.Enemies) do
		r.Inst:Destroy()
	end
	for _, tw in pairs(Render.Towers) do
		tw.Inst:Destroy()
	end
	for _, pr in ipairs(projectiles) do
		pr.Part:Destroy()
	end
	for _, d in ipairs(dying) do
		d.Inst:Destroy()
	end
	table.clear(dying)
	table.clear(Render.Enemies)
	table.clear(Render.Towers)
	table.clear(projectiles)

	local cfg = Registry.Of("Maps"):Get(mapId)
	if not cfg then
		Render.Map = nil
		return
	end
	local paths = {}
	for id, points in pairs(cfg.Paths) do
		paths[id] = PathUtil.new(points)
	end
	Render.Map = { Id = mapId, Config = cfg, Paths = paths }
	for _, p in ipairs(pendingSpawns) do
		newEnemy(p)
	end
	table.clear(pendingSpawns)
end

local function onDelta(p)
	for _, e in ipairs(p.EnemySpawned) do
		if Render.Map then
			newEnemy(e)
		else
			table.insert(pendingSpawns, e) -- mapa ainda não chegou (entrada tardia)
		end
	end
	for _, m in ipairs(p.EnemyMotion) do
		local r = Render.Enemies[m.Id]
		if r then
			r.D, r.T, r.S = m.D, m.T, m.S
		end
	end
	for _, h in ipairs(p.EnemyHealth) do
		local r = Render.Enemies[h.Id]
		if r then
			r.Hp = h.Hp
			updateBar(r)
		end
	end
	for _, s in ipairs(p.Status) do
		local r = Render.Enemies[s.Enemy]
		if r then
			local def = Registry.Of("StatusEffects"):Get(s.Effect)
			r.Tints[s.Effect] = s.On and def and def.Visual and def.Visual.Color or nil
			applyTint(r)
		end
	end
	for _, tp in ipairs(p.TowerPlaced) do
		newTower(tp)
	end
	for _, tu in ipairs(p.TowerUpdated) do
		updateTower(tu)
	end
	for _, f in ipairs(p.TowerFired) do
		fireTower(f)
	end
	for _, id in ipairs(p.TowerRemoved) do
		removeTower(id.Id)
	end
	for _, e in ipairs(p.EnemyRemoved) do
		removeEnemy(e.Id, e.Reason)
	end
end

function Render.Init()
	Render.Folder = Instance.new("Folder")
	Render.Folder.Name = "TDClient"
	Render.Folder.Parent = workspace
	Render.TowersFolder = Instance.new("Folder")
	Render.TowersFolder.Name = "Towers"
	Render.TowersFolder.Parent = Render.Folder
	enemiesFolder = Instance.new("Folder")
	enemiesFolder.Name = "Enemies"
	enemiesFolder.Parent = Render.Folder
	fxFolder = Instance.new("Folder")
	fxFolder.Name = "FX"
	fxFolder.Parent = Render.Folder

	Net.Event("GameState").OnClientEvent:Connect(function(state)
		Render.State = state
		if not Render.Map or Render.Map.Id ~= state.MapId then
			setMap(state.MapId)
		end
		Render.Events:Fire("GameState", state)
	end)
	Net.Event("PlayerData").OnClientEvent:Connect(function(data)
		Render.Data = data
		Render.Events:Fire("PlayerData", data)
	end)
	Net.Event("Loadout").OnClientEvent:Connect(function(list)
		Render.Loadout = list
		Render.Events:Fire("Loadout", list)
	end)
	Net.Event("Delta").OnClientEvent:Connect(onDelta)
	RunService.RenderStepped:Connect(step)
end

return Render

                    ----- END SOURCE -----
                PlacementController [ModuleScript]
                    ----- SOURCE -----
--[[
	PlacementController: fantasma da torre (verde/vermelho), confirmação por clique/toque e seleção de torres.
	O cliente só PREVÊ com PlacementRules; quem decide é o servidor (Request "PlaceTower").
]]
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)
local PlacementRules = require(Shared.PlacementRules)

local GREEN, RED = Color3.fromRGB(90, 220, 110), Color3.fromRGB(230, 80, 80)

local Placement = { Active = nil, OnSelect = nil, OnResult = nil }
local Render
local ghost, ring, conn
local activeRange = 0
local pointer = nil -- só usado no toque
local currentPos, currentValid, currentReason = nil, false, nil

function Placement.Cancel()
	Placement.Active = nil
	currentPos = nil
	if conn then
		conn:Disconnect()
		conn = nil
	end
	if ghost then
		ghost:Destroy()
		ghost = nil
	end
	if ring then
		ring:Destroy()
		ring = nil
	end
end

local function update()
	if not Placement.Active or not Render.Map then
		return
	end
	local camera = workspace.CurrentCamera
	local loc = pointer or UserInputService:GetMouseLocation()
	local ray = camera:ViewportPointToRay(loc.X, loc.Y)
	local params = RaycastParams.new()
	params.FilterType = Enum.RaycastFilterType.Exclude
	params.FilterDescendantsInstances = { Render.Folder, Players.LocalPlayer.Character }
	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
	if not hit then
		currentPos = nil
		ghost.Transparency = 1
		return
	end
	local y = Render.Map.Config.GroundY or 0
	currentPos = Vector3.new(hit.Position.X, y, hit.Position.Z)
	currentValid, currentReason = PlacementRules.Check(Render.Map, currentPos, Render.Towers)
	ghost.Position = currentPos + Vector3.new(0, ghost.Size.Y / 2, 0)
	ghost.Transparency = 0.45
	local color = currentValid and GREEN or RED
	ghost.Color = color
	ring.Color = color
	if activeRange > 0 then
		ring.Transparency = 0.8
		Render.PlaceRing(ring, currentPos, activeRange)
	else
		ring.Transparency = 1
	end
end

function Placement.Begin(towerId)
	Placement.Cancel()
	local def = Registry.Of("Towers"):Get(towerId)
	if not def then
		return
	end
	Placement.Active = towerId
	if Placement.OnSelect then
		Placement.OnSelect(nil)
	end
	local vis = def.Visual or {}
	ghost = Instance.new("Part")
	ghost.Anchored = true
	ghost.CanCollide = false
	ghost.CanQuery = false
	ghost.CanTouch = false
	ghost.Size = vis.Size or Vector3.new(3, 4, 3)
	ghost.Transparency = 1
	ghost.Parent = Render.Folder
	ring = Render.MakeRing()
	ring.Parent = Render.Folder
	activeRange = def.Stats and def.Stats.Range or 0
	conn = RunService.RenderStepped:Connect(update)
end

function Placement.Toggle(towerId)
	if Placement.Active == towerId then
		Placement.Cancel()
	else
		Placement.Begin(towerId)
	end
end

local function confirm()
	if not Placement.Active or not currentPos then
		return
	end
	if not currentValid then
		if Placement.OnResult then
			Placement.OnResult({ Ok = false, Error = currentReason })
		end
		return
	end
	local id, pos = Placement.Active, currentPos
	if not UserInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
		Placement.Cancel() -- segure Shift para colocar várias
	end
	local res = Net.Request():InvokeServer("PlaceTower", { TowerId = id, Position = pos })
	if Placement.OnResult then
		Placement.OnResult(res)
	end
end

local function selectAt(loc)
	local ray = workspace.CurrentCamera:ViewportPointToRay(loc.X, loc.Y)
	local params = RaycastParams.new()
	params.FilterType = Enum.RaycastFilterType.Include
	params.FilterDescendantsInstances = { Render.TowersFolder }
	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
	local id = hit and Render.PickTower(hit.Instance) or nil
	if Placement.OnSelect then
		Placement.OnSelect(id)
	end
end

function Placement.Init(renderEngine)
	Render = renderEngine

	UserInputService.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.Touch then
			pointer = Vector2.new(input.Position.X, input.Position.Y)
		end
	end)

	UserInputService.InputBegan:Connect(function(input, processed)
		if processed then
			return
		end
		local t = input.UserInputType
		if t == Enum.UserInputType.MouseButton1 then
			pointer = nil
			if Placement.Active then
				confirm()
			else
				selectAt(UserInputService:GetMouseLocation())
			end
		elseif t == Enum.UserInputType.MouseButton2 or (t == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.Escape) then
			Placement.Cancel()
		elseif t == Enum.UserInputType.Touch then
			pointer = Vector2.new(input.Position.X, input.Position.Y)
			if not Placement.Active then
				selectAt(pointer)
			end
		end
	end)

	-- toque: arraste para posicionar, solte para confirmar
	UserInputService.InputEnded:Connect(function(input, processed)
		if not processed and input.UserInputType == Enum.UserInputType.Touch and Placement.Active then
			confirm()
		end
	end)
end

return Placement

                    ----- END SOURCE -----
                RigAnimator [ModuleScript]
                    ----- SOURCE -----
--[[
	RigAnimator: mesmo contrato do UnitAnimator, mas toca AnimationTracks reais (Animation Editor).
	O ClientRenderEngine ancora só a PrimaryPart quando Animation.Mode = "Rig"; o resto do modelo segue pelas juntas.
	AnimationController e Animator são criados se o modelo não tiver.

	Animation = {
		Mode = "Rig",
		Tracks = { Idle = "rbxassetid://...", Walk = "...", Attack = "...", Upgrade = "...", Death = "..." },  -- todos opcionais
		WalkSpeed = 9,        -- studs/s em que o Walk toca a 1x (padrão: Speed do config do inimigo)
		ReleaseMarker = true, -- KeyframeMarker "Release" no Attack = instante em que o projétil sai
		ReleaseTime = 0.3,    -- alternativa sem marcador: segundos após o início do Attack (0 = sai na hora)
	}
]]
local RigAnimator = {}
RigAnimator.__index = RigAnimator

local PRIORITY = {
	Idle = Enum.AnimationPriority.Idle,
	Walk = Enum.AnimationPriority.Movement,
	Attack = Enum.AnimationPriority.Action,
	Upgrade = Enum.AnimationPriority.Action2,
	Death = Enum.AnimationPriority.Action4,
}
local LOOPED = { Idle = true, Walk = true }

function RigAnimator.new(model, role, cfg)
	if not model.PrimaryPart then
		return nil
	end
	local a = cfg.Animation or {}
	return setmetatable({
		Model = model,
		Role = role,
		Config = a,
		Tracks = {},
		Loaded = false,
		Pivot = model:GetPivot(),
		Speed = 0,
		WalkRef = a.WalkSpeed or cfg.Speed or 8,
		ReleaseTime = a.ReleaseTime or 0,
		DeathTime = 0.15,
		PendingRelease = nil,
		ReleaseAt = 0,
		Time = 0,
		Dead = false,
	}, RigAnimator)
end

-- carrega as animações só quando o modelo já está no workspace (o Animator exige isso)
function RigAnimator:_load()
	if self.Loaded or not self.Model:IsDescendantOf(workspace) then
		return
	end
	self.Loaded = true
	local controller = self.Model:FindFirstChildWhichIsA("AnimationController", true)
		or self.Model:FindFirstChildWhichIsA("Humanoid", true)
	if not controller then
		controller = Instance.new("AnimationController")
		controller.Parent = self.Model
	end
	local animator = controller:FindFirstChildWhichIsA("Animator")
	if not animator then
		animator = Instance.new("Animator")
		animator.Parent = controller
	end
	for name, id in pairs(self.Config.Tracks or {}) do
		local anim = Instance.new("Animation")
		anim.AnimationId = id
		local ok, track = pcall(function()
			return animator:LoadAnimation(anim)
		end)
		if ok and track then
			track.Priority = PRIORITY[name] or Enum.AnimationPriority.Action
			track.Looped = LOOPED[name] == true
			self.Tracks[name] = track
		else
			warn(("[RigAnimator] %s: não carregou a animação '%s'"):format(self.Model.Name, name))
		end
	end
	if self.Tracks.Idle then
		self.Tracks.Idle:Play()
	end
	if self.Tracks.Walk then
		self.Tracks.Walk:Play(0.1, 1, 0) -- começa parado; SetSpeed liga o ciclo
	end
	if self.Tracks.Death then
		self.DeathTime = math.max(self.Tracks.Death.Length, 0.15)
	end
end

function RigAnimator:SetPivot(cf)
	self.Pivot = cf
end

function RigAnimator:SetSpeed(speed)
	self.Speed = speed
	local walk = self.Tracks.Walk
	if walk and not self.Dead then
		walk:AdjustSpeed(speed > 0.05 and speed / self.WalkRef or 0) -- 0 = pose congelada
	end
end

function RigAnimator:_release()
	local fn = self.PendingRelease
	if fn then
		self.PendingRelease = nil
		fn()
	end
end

function RigAnimator:Trigger(name, onRelease)
	self:_load()
	local track = self.Tracks[name]
	if track then
		track:Play(0.05, 1, 1)
	end
	if name ~= "Attack" or not onRelease then
		return
	end
	self:_release() -- solta o disparo anterior, se ainda estava pendente
	if not track then
		onRelease()
	elseif self.Config.ReleaseMarker then
		self.PendingRelease = onRelease
		self.ReleaseAt = self.Time + 1 -- segurança se o marcador não existir na animação
		local conn
		conn = track:GetMarkerReachedSignal("Release"):Connect(function()
			conn:Disconnect()
			self:_release()
		end)
	elseif self.ReleaseTime > 0 then
		self.PendingRelease = onRelease
		self.ReleaseAt = self.Time + self.ReleaseTime
	else
		onRelease()
	end
end

function RigAnimator:Kill()
	if self.Dead then
		return
	end
	self.Dead = true
	self:_load()
	self:_release()
	for name, track in pairs(self.Tracks) do
		if name ~= "Death" then
			track:Stop(0.05)
		end
	end
	if self.Tracks.Death then
		self.Tracks.Death:Play(0.05, 1, 1)
	end
end

function RigAnimator:Step(dt)
	self.Time += dt
	self:_load()
	self.Model:PivotTo(self.Pivot)
	if self.PendingRelease and self.Time >= self.ReleaseAt then
		self:_release()
	end
end

return RigAnimator

                    ----- END SOURCE -----
                ShopUI [ModuleScript]
                    ----- SOURCE -----
--[[
	ShopUI (Factory): NENHUM botão é desenhado à mão.
	- Loja: um clone do template (ReplicatedStorage.Template2) por entrada de TowersConfig, dentro de MainUI.Units.Background
	- Painel da torre selecionada: upgrades/targeting/venda gerados de cfg.Upgrades e cfg.Targeting
	- HUD: estado, onda, vidas, moedas e contagem regressiva
]]
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)
local UnitCard = require(script.Parent.UnitCard)
local UnitPanel = require(script.Parent.UnitPanel)

local ERRORS = {
	NotEnoughCoins = "Moedas insuficientes",
	NotEquipped = "Equipe essa unidade no inventário",
	LoadoutFull = "Slots cheios: desequipe uma unidade",
	CannotBuildNow = "Não é possível construir agora",
	OutOfBounds = "Fora da área do mapa",
	TooCloseToPath = "Muito perto do caminho",
	TooCloseToTower = "Muito perto de outra torre",
	LimitReached = "Limite dessa torre atingido",
	MaxTier = "Nível máximo",
	PathLocked = "Caminho bloqueado por outro upgrade",
	NotYourTower = "Essa torre não é sua",
	RateLimited = "Calma! Muitas ações",
}
local STATE_NAMES = {
	WaitingForPlayers = "Aguardando jogadores",
	Intermission = "Intervalo",
	WaveActive = "Onda em andamento",
	GameOver = "Fim de jogo",
	Victory = "Vitória!",
}

local TEMPLATE_NAME = "Template2" -- troque para "Template1" quando quiser cards com ícone

local ShopUI = {}

local function new(class, props, parent)
	local inst = Instance.new(class)
	for k, v in pairs(props) do
		inst[k] = v
	end
	inst.Parent = parent
	return inst
end

function ShopUI.Init(Placement, Render)
	local player = Players.LocalPlayer
	local playerGui = player:WaitForChild("PlayerGui")
	local gui = new("ScreenGui", { Name = "TDUI", ResetOnSpawn = false }, playerGui)

	-- ---------------------------------------------------------- HUD + toast
	local hud = new("TextLabel", {
		AnchorPoint = Vector2.new(0.5, 0),
		Position = UDim2.new(0.5, 0, 0, 8),
		Size = UDim2.fromOffset(520, 34),
		BackgroundColor3 = Color3.fromRGB(20, 22, 28),
		BackgroundTransparency = 0.2,
		TextColor3 = Color3.new(1, 1, 1),
		Font = Enum.Font.GothamMedium,
		TextSize = 16,
		Text = "Conectando...",
	}, gui)
	new("UICorner", { CornerRadius = UDim.new(0, 8) }, hud)

	local toastLabel = new("TextLabel", {
		AnchorPoint = Vector2.new(0.5, 0),
		Position = UDim2.new(0.5, 0, 0, 48),
		Size = UDim2.fromOffset(360, 30),
		BackgroundColor3 = Color3.fromRGB(150, 50, 50),
		TextColor3 = Color3.new(1, 1, 1),
		Font = Enum.Font.GothamMedium,
		TextSize = 15,
		Visible = false,
	}, gui)
	new("UICorner", { CornerRadius = UDim.new(0, 8) }, toastLabel)
	local toastToken = 0
	local function toast(text)
		toastToken += 1
		local mine = toastToken
		toastLabel.Text = text
		toastLabel.Visible = true
		task.delay(2.5, function()
			if toastToken == mine then
				toastLabel.Visible = false
			end
		end)
	end
	local function explain(res)
		if res and not res.Ok then
			toast(ERRORS[res.Error] or tostring(res.Error))
		end
	end
	Placement.OnResult = explain

	local function refreshHud()
		local s = Render.State
		if not s then
			return
		end
		local left = ""
		if s.EndsAt and s.EndsAt > 0 then
			left = (" | %ds"):format(math.max(0, math.ceil(s.EndsAt - workspace:GetServerTimeNow())))
		end
		local waveText = s.VictoryWave and s.VictoryWave > 0 and ("%d/%d"):format(s.Wave, s.VictoryWave) or tostring(s.Wave)
		hud.Text = ("%s | Onda %s | Vidas %d/%d | Moedas %d%s"):format(
			STATE_NAMES[s.State] or s.State,
			waveText,
			s.Lives,
			s.MaxLives,
			Render.Data.Coins or 0,
			left
		)
	end
	task.spawn(function()
		while gui.Parent do
			refreshHud()
			task.wait(0.25)
		end
	end)

	-- ---------------------------------------------------------- loja (equipadas) + inventário (todas)
	local template = ReplicatedStorage:WaitForChild(TEMPLATE_NAME)
	local mainUI = playerGui:WaitForChild("MainUI")
	local shopBackground = mainUI:WaitForChild("Units"):WaitForChild("Background") -- Frame Units: só as equipadas
	local invUnits = mainUI:WaitForChild("Inventory"):WaitForChild("Units") -- ScrollingFrame Units: todas

	if not shopBackground:FindFirstChildWhichIsA("UIListLayout") and not shopBackground:FindFirstChildWhichIsA("UIGridLayout") then
		new("UIListLayout", {
			FillDirection = Enum.FillDirection.Horizontal,
			Padding = UDim.new(0, 8),
			SortOrder = Enum.SortOrder.LayoutOrder,
		}, shopBackground)
	end

	local WHITE, RED, GREEN = Color3.new(1, 1, 1), Color3.fromRGB(255, 120, 120), Color3.fromRGB(120, 255, 140)
	local shopCards, invCards = {}, {}

	local function makeCard(def, parent, order)
		local button = template:Clone()
		button.Name = def.Id
		button.LayoutOrder = order
		button.Visible = true
		button.Parent = parent
		if button:IsA("ImageButton") and def.Icon and def.Icon ~= "" then
			button.Image = def.Icon
		end
		return button
	end

	local function refreshShop()
		local coins = Render.Data.Coins or 0
		for _, c in pairs(shopCards) do
			local cost = Render.TowerCost(c.Def)
			if c.Button:IsA("TextButton") then
				c.Button.Text = ("%s\n$%d"):format(c.Def.DisplayName or c.Def.Id, cost)
				c.Button.TextColor3 = coins >= cost and WHITE or RED
			end
		end
	end

	local function refreshInventory()
		for id, c in pairs(invCards) do
			local eq = table.find(Render.Loadout, id) ~= nil
			if c.Button:IsA("TextButton") then
				c.Button.Text = ("%s\n%s"):format(c.Def.DisplayName or id, eq and "[Equipado]" or "Equipar")
				c.Button.TextColor3 = eq and GREEN or WHITE
			end
		end
	end

	local function rebuildShop()
		for _, c in pairs(shopCards) do
			c.Button:Destroy()
		end
		table.clear(shopCards)
		local towers = Registry.Of("Towers")
		for i, id in ipairs(Render.Loadout) do
			local def = towers:Get(id)
			if def then
				local button = UnitCard.Make(def, shopBackground, i, Render) or makeCard(def, shopBackground, i)
				button.Activated:Connect(function()
					Placement.Toggle(id)
				end)
				shopCards[id] = { Button = button, Def = def }
			end
		end
		refreshShop()
	end

	-- inventário: um card por torre existente (torres novas em TowersConfig aparecem sozinhas)
	Registry.Of("Towers"):OnRegister(function(def)
		local button = makeCard(def, invUnits, def.Cost)
		button.Activated:Connect(function()
			explain(Net.Request():InvokeServer("ToggleEquip", { TowerId = def.Id }))
		end)
		invCards[def.Id] = { Button = button, Def = def }
		refreshInventory()
	end)

	Render.Events:Connect("Loadout", function(list)
		if Placement.Active and not table.find(list, Placement.Active) then
			Placement.Cancel()
		end
		rebuildShop()
		refreshInventory()
	end)
	Render.Events:Connect("PlayerData", refreshShop)
	Render.Events:Connect("GameState", refreshShop)
	rebuildShop()
	 [trimmed]  -  Editar
  18:17:15.881  ========================================  -  Editar
  18:17:15.885  PROJETO EXPORTADO!  -  Editar
  18:17:15.885  Tamanho: 442723 caracteres  -  Editar
  18:17:15.885  ========================================  -  Editar
  18:17:15.886  ===== ROBLOX PROJECT MAP =====
Gerado em: 2026-10-02 18:17:15

Place1 [DataModel]
    Workspace [Workspace]
        SunRays [SunRaysEffect]
        ColorCorrection [ColorCorrectionEffect]
        Blur [BlurEffect]
        Bloom [BloomEffect]
            Atmosphere [Atmosphere]
            ArcHandles [ArcHandles]
        TowerDefenseMap [Folder]
            Waypoints [Folder]
            Path [Folder]
            TowerSpots [Folder]
            Decor [Folder]
        Terrain [Terrain]
        Camera [Camera]
    Run Service [RunService]
    GuiService [GuiService]
        ScreenshotHud [ScreenshotHud]
    Stats [Stats]
        PerformanceStats [StatsItem]
            Memory [StatsItem]
                CoreMemory [StatsItem]
                    default [StatsItem]
                    staticinit [StatsItem]
                    http/batch [StatsItem]
                    lua/web-cache [StatsItem]
                    contentProvider/asyncDecryption [StatsItem]
                    internal/DataModelPatch [StatsItem]
                    render/prepare/physics [StatsItem]
                    physics/step [StatsItem]
                    physics/buffers [StatsItem]
                    physics/mechanism [StatsItem]
                    physics/assembly [StatsItem]
                    experienceStateCaptureService [StatsItem]
                    gui/TextLayout [StatsItem]
                    render/fonts [StatsItem]
                    gui/HarfBuzz [StatsItem]
                    gui/FreeType [StatsItem]
                    fontProvider/loading [StatsItem]
                    gui/FontData [StatsItem]
                    internal/localizationTable [StatsItem]
                    internal/localization [StatsItem]
                    ads/AdGui [StatsItem]
                    internal/MarketplaceService [StatsItem]
                    geometry/EditableMesh/Geometry [StatsItem]
                    geometry/EditableMesh/SpatialCache [StatsItem]
                    geometry/EditableMesh/GpuAssigned [StatsItem]
                    physics/bullet [StatsItem]
                    network/netAssetSerialized [StatsItem]
                    network/netAssetRegistries [StatsItem]
                    network/netAssetProxy [StatsItem]
                    AppCore/GuidRegistry [StatsItem]
                    instance/fullname [StatsItem]
                    internal/TaskScheduler [StatsItem]
                    profiler [StatsItem]
                    internal/RbxThread [StatsItem]
                    localstorage [StatsItem]
                    telemetry/analytics [StatsItem]
                    telemetry [StatsItem]
                    http/client [StatsItem]
                    http/curl [StatsItem]
                    http/requestcallback [StatsItem]
                    openssl [StatsItem]
                    http/wslay [StatsItem]
                    SQLite [StatsItem]
                    telemetry/fields_container [StatsItem]
                    telemetry/counter [StatsItem]
                    telemetry/event [StatsItem]
                    telemetry/stat [StatsItem]
                    telemetry/v2_try_cut_and_send [StatsItem]
                    gui/FreeTypeDT [StatsItem]
                    AssetProvider/total [StatsItem]
                    sound/default [StatsItem]
                    render/copy [StatsItem]
                    render/vertexlayout [StatsItem]
                    render/shader [StatsItem]
                    render/swapchain [StatsItem]
                    raknet/raknet [StatsItem]
                    raknet/startup [StatsItem]
                    raknet/recv-buffer [StatsItem]
                    raknet/buffered-commands [StatsItem]
                    raknet/packet-return [StatsItem]
                    raknet/tx-outgoing [StatsItem]
                    raknet/tx-datagram [StatsItem]
                    raknet/rx-ordered-heap [StatsItem]
                    raknet/rx-split-reassembly [StatsItem]
                    raknet/rx-output [StatsItem]
                    raknet/rx-handling [StatsItem]
                    raknet/datagram-history [StatsItem]
                    raknet/ack-nak [StatsItem]
                    RbxTransport/Io/sys [StatsItem]
                    RbxTransport/Io/libuv [StatsItem]
                    video/encoding/hardware [StatsItem]
                    video/default [StatsItem]
                    video/packet [StatsItem]
                    video/codec [StatsItem]
                    video/texture [StatsItem]
                    internal/PerformanceControl [StatsItem]
                    RbxTransport/RtcIo/Local [StatsItem]
                    RbxTransport/RtcIo/Remote/Rx [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptConnection [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptWtSession [StatsItem]
                    RbxTransport/RtcIo/Remote/AcceptH3 [StatsItem]
                    RbxTransport/RtcIo/Remote/NewAppConnection [StatsItem]
                    RbxTransport/RtcIo/Remote/Handshake [StatsItem]
                    RbxTransport/RtcIo/Remote/StreamAccepted [StatsItem]
                    RbxTransport/RtcIo/Remote/StreamClose [StatsItem]
                    RbxTransport/RtcIo/Remote/Ack [StatsItem]
                    RbxTransport/RtcIo/Remote/FlowControl [StatsItem]
                    RbxTransport/RtcIo/Remote/Loss [StatsItem]
                    RbxTransport/RtcIo/Remote/ConnClose [StatsItem]
                    RbxTransport/RtcIo/Remote/AppControl [StatsItem]
                    RbxTransport/RtcIo/Remote/AppFin [StatsItem]
                    RbxTransport/RtcIo/Remote/OpenUnreliableChannel [StatsItem]
                    physics/broadphase [StatsItem]
                    physics/midphase [StatsItem]
                    internal/ixp [StatsItem]
                    video/realtime_media [StatsItem]
                    video/capture_engine [StatsItem]
                    physics/aerodynamics/mesh [StatsItem]
                    physics/aerodynamics/integrator [StatsItem]
                    physics/aerodynamics/linearintegrator [StatsItem]
                    physics/aerodynamics/cpintegrator [StatsItem]
                    physics/aerodynamics/shinterpolator [StatsItem]
                    physics/aerodynamics/reducedmesh [StatsItem]
                    internal/ScriptContext [StatsItem]
                    lua/bytecode [StatsItem]
                    lua/codegen [StatsItem]
                    lua/codegenpages [StatsItem]
                    internal/RuntimeScriptService [StatsItem]
                    CoreScriptTelemetry [StatsItem]
                    physics/solver/buffers [StatsItem]
                    physics/solver/sleep [StatsItem]
                    physics/solver/ldl [StatsItem]
                    physics/solver/misc [StatsItem]
                    internal/DataModelGenericJob [StatsItem]
                    studio/undo [StatsItem]
                    internal/InstanceStitchingHandler [StatsItem]
                    CollectionService [StatsItem]
                    internal/ChatService [StatsItem]
                    internal/GlobalSettings [StatsItem]
                    render/terrain/heightmapImporter [StatsItem]
                    geometry/EditableImage [StatsItem]
                    collections/collection [StatsItem]
                    collections/watcher [StatsItem]
                    performanceStats [StatsItem]
                    collections/proximity [StatsItem]
                    internal/AuroraService/InputFrame [StatsItem]
                    internal/AuroraService/HashBuffer [StatsItem]
                    internal/AuroraService/Prediction [StatsItem]
                    internal/Workspace [StatsItem]
                    internal/RemoteFunction [StatsItem]
                    internal/LogService [StatsItem]
                    render/lightgrid [StatsItem]
                    render/system [StatsItem]
                    render/bindworkspace [StatsItem]
                    render/adorn [StatsItem]
                    render/perform/statistics [StatsItem]
                    render/prepare [StatsItem]
                    render/prepare/adorn [StatsItem]
                    render/perform [StatsItem]
                    render/perform/adorn [StatsItem]
                    render/glyphaatlas/ugc [StatsItem]
                    render/glyphatlas/core [StatsItem]
                    render/terrain/grass/async [StatsItem]
                    render/terrain/grass [StatsItem]
                    render/prepare/terrain/grass [StatsItem]
                    render/target [StatsItem]
                    render/target/pooled [StatsItem]
                    render/perform/zpre [StatsItem]
                    render/clouds [StatsItem]
                    render/ssao [StatsItem]
                    render/glow [StatsItem]
                    render/sunrays [StatsItem]
                    render/dof [StatsItem]
                    render/blur [StatsItem]
                    render/colorCorrection [StatsItem]
                    render/highlight [StatsItem]
                    render/RtPool [StatsItem]
                    render/mainRts [StatsItem]
                    render/ui [StatsItem]
                    render/shadowmap [StatsItem]
                    render/perform/shadowmap [StatsItem]
                    render/shadowmap/depthcache [StatsItem]
                    render/perform/materialMisc [StatsItem]
                    render/perform/materialGc [StatsItem]
                    render/material/failsafe [StatsItem]
                    render/perform/terrain [StatsItem]
                    render/prepare/terrain [StatsItem]
                    render/instanceglob [StatsItem]
                    render/gpu_geom_mgr [StatsItem]
                    dynamic/mesh [StatsItem]
                    dynamic/texture [StatsItem]
                    render/envmap [StatsItem]
                    render/material/misc [StatsItem]
                    render/prepare/tc [StatsItem]
                    render/prepare/sceneUpdater [StatsItem]
                    render/prepare/parts [StatsItem]
                    render/prepare/megaCluster [StatsItem]
                    render/prepare/attachments [StatsItem]
                    render/swocc [StatsItem]
                    render/perform/textureAtlasInsert [StatsItem]
                    render/meshManager/async [StatsItem]
                    textureRef [StatsItem]
                    render/texture/local [StatsItem]
                    render/texture/fallback [StatsItem]
                    render/texture/loading [StatsItem]
                    render/perform/textureGc [StatsItem]
                    render/prepare/textureManager [StatsItem]
                    render/perform/textureManager [StatsItem]
                    render/sky [StatsItem]
                    render/advsky [StatsItem]
                    render/perform/cullableScene [StatsItem]
                    render/prepare/motionBuffer [StatsItem]
                    render/geometryGenerator [StatsItem]
                    render/perform/scratchFB [StatsItem]
                    render/prepare/lightObject [StatsItem]
                    render/terrain/async/chunkGen [StatsItem]
                    render/perform/terrain/occlusionGen [StatsItem]
                    render/viewportFrames [StatsItem]
                    render/prepare/lightGridChunk [StatsItem]
                    render/perform/lightGrid [StatsItem]
                    render/fastCluster/prepareSkinning [StatsItem]
                    render/fastCluster/skinningReserve [StatsItem]
                    render/prepare/beamNode [StatsItem]
                    render/prepare/customEmitter [StatsItem]
                    render/pipeline [StatsItem]
                    render/pipeline/updates [StatsItem]
                    render/meshFetcherDecomp [StatsItem]
                    network/compresspacket [StatsItem]
                    network/decompresspacket [StatsItem]
                    network/ISR/Property [StatsItem]
                    network/groupManager [StatsItem]
                    network/ISR/Replicator [StatsItem]
                    network/setManager [StatsItem]
                    internal/CSGDictionary [StatsItem]
                    network/HeatmapQueryService [StatsItem]
                    internal/HttpRbxApiService [StatsItem]
                    internal/StarterPlayer [StatsItem]
                    datastore/cache [StatsItem]
                    animation/skeleton_watcher [StatsItem]
                    wrap/layeredDeformer [StatsItem]
                    internal/Humanoid [StatsItem]
                    temporaryCageMeshProvider/save [StatsItem]
                    wrap/hsr [StatsItem]
                    animation/skeleton [StatsItem]
                    wrap/deformMeshProvider [StatsItem]
                    gui/Uncategorized [StatsItem]
                    gui/UIQuadTree [StatsItem]
                    languageServices/async [StatsItem]
                    languageServices/generic [StatsItem]
                    languageServices/shadow [StatsItem]
                    network/streamingReplication [StatsItem]
                    network/streamJob [StatsItem]
                    network/replicationCoalescing [StatsItem]
                    network/deserializestep [StatsItem]
                    network/onreceive [StatsItem]
                    network/sharedQueue [StatsItem]
                    network/megaReplicationData [StatsItem]
                    network/modelCompleteness [StatsItem]
                    network/refPropTracking [StatsItem]
                    network/replicator [StatsItem]
                    internal/InputReplicator [StatsItem]
                    network/gcJob [StatsItem]
                    network/instanceObjectManager [StatsItem]
                    network/server [StatsItem]
                    network/streamingSolver [StatsItem]
                    network/streamingObserver [StatsItem]
                    network/replicatedInstances [StatsItem]
                    network/deferredtrees [StatsItem]
                    network/newinstanceitem [StatsItem]
                    network/streamDataItem [StatsItem]
                    network/ISR [StatsItem]
                    network/ISR/Connection [StatsItem]
                    network/ISR/Prioritization [StatsItem]
                    network/touchReplication [StatsItem]
                    network/replicationDataCache [StatsItem]
                    network/replicationDataCachePendingList [StatsItem]
                    network/ISR/groupMan [StatsItem]
                    network/physicsSenderCache [StatsItem]
                    sound/voice [StatsItem]
                    voice/webrtc [StatsItem]
                    voice/operations [StatsItem]
                    voice/audio [StatsItem]
                    sound/async [StatsItem]
                    sound/acoustics [StatsItem]
                    AudioWiring [StatsItem]
                    instance/AttributesAndTags [StatsItem]
                    internal/BaseThreadPool [StatsItem]
                    AssetProvider/state [StatsItem]
                    AssetProvider/other [StatsItem]
                    render/vertexstreamer [StatsItem]
                    friendsCalling/bringUp [StatsItem]
                PlaceMemory [StatsItem]
                    HttpCache [StatsItem]
                    Instances [StatsItem]
                    Signals [StatsItem]
                    LuaHeap [StatsItem]
                    Script [StatsItem]
                    PhysicsCollision [StatsItem]
                    BaseParts [StatsItem]
                    GraphicsSolidModels [StatsItem]
                    GraphicsHSR [StatsItem]
                    GraphicsMeshParts [StatsItem]
                    GraphicsParticles [StatsItem]
                    GraphicsParts [StatsItem]
                    GraphicsSpatialHash [StatsItem]
                    GraphicsTerrain [StatsItem]
                    GraphicsTexture [StatsItem]
                    GraphicsTextureCharacter [StatsItem]
                    Sounds [StatsItem]
                    TerrainVoxels [StatsItem]
                    TerrainPhysics [StatsItem]
                    Gui [StatsItem]
                    Animation [StatsItem]
                    Navigation [StatsItem]
                    GeometryCSG [StatsItem]
                    GraphicsSlimModels [StatsItem]
                UntrackedMemory [StatsItem]
                PlaceScriptMemory [StatsItem]
                    MemoryCategory_0 [StatsItem]
                    MemoryCategory_1 [StatsItem]
                    MemoryCategory_2 [StatsItem]
                    MemoryCategory_3 [StatsItem]
                    MemoryCategory_4 [StatsItem]
                    MemoryCategory_5 [StatsItem]
                    MemoryCategory_6 [StatsItem]
                    MemoryCategory_7 [StatsItem]
                    MemoryCategory_8 [StatsItem]
                    MemoryCategory_9 [StatsItem]
                    MemoryCategory_10 [StatsItem]
                    MemoryCategory_11 [StatsItem]
                    MemoryCategory_12 [StatsItem]
                    MemoryCategory_13 [StatsItem]
                    MemoryCategory_14 [StatsItem]
                    MemoryCategory_15 [StatsItem]
                    MemoryCategory_16 [StatsItem]
                    MemoryCategory_17 [StatsItem]
                    MemoryCategory_18 [StatsItem]
                    MemoryCategory_19 [StatsItem]
                    MemoryCategory_20 [StatsItem]
                    MemoryCategory_21 [StatsItem]
                    MemoryCategory_22 [StatsItem]
                    MemoryCategory_23 [StatsItem]
                    MemoryCategory_24 [StatsItem]
                    MemoryCategory_25 [StatsItem]
                    MemoryCategory_26 [StatsItem]
                    MemoryCategory_27 [StatsItem]
                    MemoryCategory_28 [StatsItem]
                    MemoryCategory_29 [StatsItem]
                    MemoryCategory_30 [StatsItem]
                    MemoryCategory_31 [StatsItem]
                    MemoryCategory_32 [StatsItem]
                    MemoryCategory_33 [StatsItem]
                    MemoryCategory_34 [StatsItem]
                    MemoryCategory_35 [StatsItem]
                    MemoryCategory_36 [StatsItem]
                    MemoryCategory_37 [StatsItem]
                    MemoryCategory_38 [StatsItem]
                    MemoryCategory_39 [StatsItem]
                    MemoryCategory_40 [StatsItem]
                    MemoryCategory_41 [StatsItem]
                    MemoryCategory_42 [StatsItem]
                    MemoryCategory_43 [StatsItem]
                    MemoryCategory_44 [StatsItem]
                    MemoryCategory_45 [StatsItem]
                    MemoryCategory_46 [StatsItem]
                    MemoryCategory_47 [StatsItem]
                    MemoryCategory_48 [StatsItem]
                    MemoryCategory_49 [StatsItem]
                    MemoryCategory_50 [StatsItem]
                    MemoryCategory_51 [StatsItem]
                    MemoryCategory_52 [StatsItem]
                    MemoryCategory_53 [StatsItem]
                    MemoryCategory_54 [StatsItem]
                    MemoryCategory_55 [StatsItem]
                    MemoryCategory_56 [StatsItem]
                    MemoryCategory_57 [StatsItem]
                    MemoryCategory_58 [StatsItem]
                    MemoryCategory_59 [StatsItem]
                    MemoryCategory_60 [StatsItem]
                    MemoryCategory_61 [StatsItem]
                    MemoryCategory_62 [StatsItem]
                    MemoryCategory_63 [StatsItem]
                    MemoryCategory_64 [StatsItem]
                    MemoryCategory_65 [StatsItem]
                    MemoryCategory_66 [StatsItem]
                    MemoryCategory_67 [StatsItem]
                    MemoryCategory_68 [StatsItem]
                    MemoryCategory_69 [StatsItem]
                    MemoryCategory_70 [StatsItem]
                    MemoryCategory_71 [StatsItem]
                    MemoryCategory_72 [StatsItem]
                    MemoryCategory_73 [StatsItem]
                    MemoryCategory_74 [StatsItem]
                    MemoryCategory_75 [StatsItem]
                    MemoryCategory_76 [StatsItem]
                    MemoryCategory_77 [StatsItem]
                    MemoryCategory_78 [StatsItem]
                    MemoryCategory_79 [StatsItem]
                    MemoryCategory_80 [StatsItem]
                    MemoryCategory_81 [StatsItem]
                    MemoryCategory_82 [StatsItem]
                    MemoryCategory_83 [StatsItem]
                    MemoryCategory_84 [StatsItem]
                    MemoryCategory_85 [StatsItem]
                    MemoryCategory_86 [StatsItem]
                    MemoryCategory_87 [StatsItem]
                    MemoryCategory_88 [StatsItem]
                    MemoryCategory_89 [StatsItem]
                    MemoryCategory_90 [StatsItem]
                    MemoryCategory_91 [StatsItem]
                    MemoryCategory_92 [StatsItem]
                    MemoryCategory_93 [StatsItem]
                    MemoryCategory_94 [StatsItem]
                    MemoryCategory_95 [StatsItem]
                    MemoryCategory_96 [StatsItem]
                    MemoryCategory_97 [StatsItem]
                    MemoryCategory_98 [StatsItem]
                    MemoryCategory_99 [StatsItem]
                    MemoryCategory_100 [StatsItem]
                    MemoryCategory_101 [StatsItem]
                    MemoryCategory_102 [StatsItem]
                    MemoryCategory_103 [StatsItem]
                    MemoryCategory_104 [StatsItem]
                    MemoryCategory_105 [StatsItem]
                    MemoryCategory_106 [StatsItem]
                    MemoryCategory_107 [StatsItem]
                    MemoryCategory_108 [StatsItem]
                    MemoryCategory_109 [StatsItem]
                    MemoryCategory_110 [StatsItem]
                    MemoryCategory_111 [StatsItem]
                    MemoryCategory_112 [StatsItem]
                    MemoryCategory_113 [StatsItem]
                    MemoryCategory_114 [StatsItem]
                    MemoryCategory_115 [StatsItem]
                    MemoryCategory_116 [StatsItem]
                    MemoryCategory_117 [StatsItem]
                    MemoryCategory_118 [StatsItem]
                    MemoryCategory_119 [StatsItem]
                    MemoryCategory_120 [StatsItem]
                    MemoryCategory_121 [StatsItem]
                    MemoryCategory_122 [StatsItem]
                    MemoryCategory_123 [StatsItem]
                    MemoryCategory_124 [StatsItem]
                    MemoryCategory_125 [StatsItem]
                    MemoryCategory_126 [StatsItem]
                    MemoryCategory_127 [StatsItem]
                    MemoryCategory_128 [StatsItem]
                    MemoryCategory_129 [StatsItem]
                    MemoryCategory_130 [StatsItem]
                    MemoryCategory_131 [StatsItem]
                    MemoryCategory_132 [StatsItem]
                    MemoryCategory_133 [StatsItem]
                    MemoryCategory_134 [StatsItem]
                    MemoryCategory_135 [StatsItem]
                    MemoryCategory_136 [StatsItem]
                    MemoryCategory_137 [StatsItem]
                    MemoryCategory_138 [StatsItem]
                    MemoryCategory_139 [StatsItem]
                    MemoryCategory_140 [StatsItem]
                    MemoryCategory_141 [StatsItem]
                    MemoryCategory_142 [StatsItem]
                    MemoryCategory_143 [StatsItem]
                    MemoryCategory_144 [StatsItem]
                    MemoryCategory_145 [StatsItem]
                    MemoryCategory_146 [StatsItem]
                    MemoryCategory_147 [StatsItem]
                    MemoryCategory_148 [StatsItem]
                    MemoryCategory_149 [StatsItem]
                    MemoryCategory_150 [StatsItem]
                    MemoryCategory_151 [StatsItem]
                    MemoryCategory_152 [StatsItem]
                    MemoryCategory_153 [StatsItem]
                    MemoryCategory_154 [StatsItem]
                    MemoryCategory_155 [StatsItem]
                    MemoryCategory_156 [StatsItem]
                    MemoryCategory_157 [StatsItem]
                    MemoryCategory_158 [StatsItem]
                    MemoryCategory_159 [StatsItem]
                    MemoryCategory_160 [StatsItem]
                    MemoryCategory_161 [StatsItem]
                    MemoryCategory_162 [StatsItem]
                    MemoryCategory_163 [StatsItem]
                    MemoryCategory_164 [StatsItem]
                    MemoryCategory_165 [StatsItem]
                    MemoryCategory_166 [StatsItem]
                    MemoryCategory_167 [StatsItem]
                    MemoryCategory_168 [StatsItem]
                    MemoryCategory_169 [StatsItem]
                    MemoryCategory_170 [StatsItem]
                    MemoryCategory_171 [StatsItem]
                    MemoryCategory_172 [StatsItem]
                    MemoryCategory_173 [StatsItem]
                    MemoryCategory_174 [StatsItem]
                    MemoryCategory_175 [StatsItem]
                    MemoryCategory_176 [StatsItem]
                    MemoryCategory_177 [StatsItem]
                    MemoryCategory_178 [StatsItem]
                    MemoryCategory_179 [StatsItem]
                    MemoryCategory_180 [StatsItem]
                    MemoryCategory_181 [StatsItem]
                    MemoryCategory_182 [StatsItem]
                    MemoryCategory_183 [StatsItem]
                    MemoryCategory_184 [StatsItem]
                    MemoryCategory_185 [StatsItem]
                    MemoryCategory_186 [StatsItem]
                    MemoryCategory_187 [StatsItem]
                    MemoryCategory_188 [StatsItem]
                    MemoryCategory_189 [StatsItem]
                    MemoryCategory_190 [StatsItem]
                    MemoryCategory_191 [StatsItem]
                    MemoryCategory_192 [StatsItem]
                    MemoryCategory_193 [StatsItem]
                    MemoryCategory_194 [StatsItem]
                    MemoryCategory_195 [StatsItem]
                    MemoryCategory_196 [StatsItem]
                    MemoryCategory_197 [StatsItem]
                    MemoryCategory_198 [StatsItem]
                    MemoryCategory_199 [StatsItem]
                    MemoryCategory_200 [StatsItem]
                    MemoryCategory_201 [StatsItem]
                    MemoryCategory_202 [StatsItem]
                    MemoryCategory_203 [StatsItem]
                    MemoryCategory_204 [StatsItem]
                    MemoryCategory_205 [StatsItem]
                    MemoryCategory_206 [StatsItem]
                    MemoryCategory_207 [StatsItem]
                    MemoryCategory_208 [StatsItem]
                    MemoryCategory_209 [StatsItem]
                    MemoryCategory_210 [StatsItem]
                    MemoryCategory_211 [StatsItem]
                    MemoryCategory_212 [StatsItem]
                    MemoryCategory_213 [StatsItem]
                    MemoryCategory_214 [StatsItem]
                    MemoryCategory_215 [StatsItem]
                    MemoryCategory_216 [StatsItem]
                    MemoryCategory_217 [StatsItem]
                    MemoryCategory_218 [StatsItem]
                    MemoryCategory_219 [StatsItem]
                    MemoryCategory_220 [StatsItem]
                    MemoryCategory_221 [StatsItem]
                    MemoryCategory_222 [StatsItem]
                    MemoryCategory_223 [StatsItem]
                    MemoryCategory_224 [StatsItem]
                    MemoryCategory_225 [StatsItem]
                    MemoryCategory_226 [StatsItem]
                    MemoryCategory_227 [StatsItem]
                    MemoryCategory_228 [StatsItem]
                    MemoryCategory_229 [StatsItem]
                    MemoryCategory_230 [StatsItem]
                    MemoryCategory_231 [StatsItem]
                    MemoryCategory_232 [StatsItem]
                    MemoryCategory_233 [StatsItem]
                    MemoryCategory_234 [StatsItem]
                    MemoryCategory_235 [StatsItem]
                    MemoryCategory_236 [StatsItem]
                    MemoryCategory_237 [StatsItem]
                    MemoryCategory_238 [StatsItem]
                    MemoryCategory_239 [StatsItem]
                    MemoryCategory_240 [StatsItem]
                    MemoryCategory_241 [StatsItem]
                    MemoryCategory_242 [StatsItem]
                    MemoryCategory_243 [StatsItem]
                    MemoryCategory_244 [StatsItem]
                    MemoryCategory_245 [StatsItem]
                    MemoryCategory_246 [StatsItem]
                    MemoryCategory_247 [StatsItem]
                    MemoryCategory_248 [StatsItem]
                    MemoryCategory_249 [StatsItem]
                    MemoryCategory_250 [StatsItem]
                    MemoryCategory_251 [StatsItem]
                    MemoryCategory_252 [StatsItem]
                    MemoryCategory_253 [StatsItem]
                    MemoryCategory_254 [StatsItem]
                    MemoryCategory_255 [StatsItem]
                CoreScriptMemory [StatsItem]
                    MemoryCategory_0 [StatsItem]
                    MemoryCategory_1 [StatsItem]
                    MemoryCategory_2 [StatsItem]
                    MemoryCategory_3 [StatsItem]
                    MemoryCategory_4 [StatsItem]
                    MemoryCategory_5 [StatsItem]
                    MemoryCategory_6 [StatsItem]
                    MemoryCategory_7 [StatsItem]
                    MemoryCategory_8 [StatsItem]
                    MemoryCategory_9 [StatsItem]
                    MemoryCategory_10 [StatsItem]
                    MemoryCategory_11 [StatsItem]
                    MemoryCategory_12 [StatsItem]
                    MemoryCategory_13 [StatsItem]
                    MemoryCategory_14 [StatsItem]
                    MemoryCategory_15 [StatsItem]
                    MemoryCategory_16 [StatsItem]
                    MemoryCategory_17 [StatsItem]
                    MemoryCategory_18 [StatsItem]
                    MemoryCategory_19 [StatsItem]
                    MemoryCategory_20 [StatsItem]
                    MemoryCategory_21 [StatsItem]
                    MemoryCategory_22 [StatsItem]
                    MemoryCategory_23 [StatsItem]
                    MemoryCategory_24 [StatsItem]
                    MemoryCategory_25 [StatsItem]
                    MemoryCategory_26 [StatsItem]
                    MemoryCategory_27 [StatsItem]
                    MemoryCategory_28 [StatsItem]
                    MemoryCategory_29 [StatsItem]
                    MemoryCategory_30 [StatsItem]
                    MemoryCategory_31 [StatsItem]
                    MemoryCategory_32 [StatsItem]
                    MemoryCategory_33 [StatsItem]
                    MemoryCategory_34 [StatsItem]
                    MemoryCategory_35 [StatsItem]
                    MemoryCategory_36 [StatsItem]
                    MemoryCategory_37 [StatsItem]
                    MemoryCategory_38 [StatsItem]
                    MemoryCategory_39 [StatsItem]
                    MemoryCategory_40 [StatsItem]
                    MemoryCategory_41 [StatsItem]
                    MemoryCategory_42 [StatsItem]
                    MemoryCategory_43 [StatsItem]
                    MemoryCategory_44 [StatsItem]
                    MemoryCategory_45 [StatsItem]
                    MemoryCategory_46 [StatsItem]
                    MemoryCategory_47 [StatsItem]
                    MemoryCategory_48 [StatsItem]
                    MemoryCategory_49 [StatsItem]
                    MemoryCategory_50 [StatsItem]
                    MemoryCategory_51 [StatsItem]
                    MemoryCategory_52 [StatsItem]
                    MemoryCategory_53 [StatsItem]
                    MemoryCategory_54 [StatsItem]
                    MemoryCategory_55 [StatsItem]
                    MemoryCategory_56 [StatsItem]
                    MemoryCategory_57 [StatsItem]
                    MemoryCategory_58 [StatsItem]
                    MemoryCategory_59 [StatsItem]
                    MemoryCategory_60 [StatsItem]
                    MemoryCategory_61 [StatsItem]
                    MemoryCategory_62 [StatsItem]
                    MemoryCategory_63 [StatsItem]
                    MemoryCategory_64 [StatsItem]
                    MemoryCategory_65 [StatsItem]
                    MemoryCategory_66 [StatsItem]
                    MemoryCategory_67 [StatsItem]
                    MemoryCategory_68 [StatsItem]
                    MemoryCategory_69 [StatsItem]
                    MemoryCategory_70 [StatsItem]
                    MemoryCategory_71 [StatsItem]
                    MemoryCategory_72 [StatsItem]
                    MemoryCategory_73 [StatsItem]
                    MemoryCategory_74 [StatsItem]
                    MemoryCategory_75 [StatsItem]
                    MemoryCategory_76 [StatsItem]
                    MemoryCategory_77 [StatsItem]
                    MemoryCategory_78 [StatsItem]
                    MemoryCategory_79 [StatsItem]
                    MemoryCategory_80 [StatsItem]
                    MemoryCategory_81 [StatsItem]
                    MemoryCategory_82 [StatsItem]
                    MemoryCategory_83 [StatsItem]
                    MemoryCategory_84 [StatsItem]
                    MemoryCategory_85 [StatsItem]
                    MemoryCategory_86 [StatsItem]
                    MemoryCategory_87 [StatsItem]
                    MemoryCategory_88 [StatsItem]
                    MemoryCategory_89 [StatsItem]
                    MemoryCategory_90 [StatsItem]
                    MemoryCategory_91 [StatsItem]
                    MemoryCategory_92 [StatsItem]
                    MemoryCategory_93 [StatsItem]
                    MemoryCategory_94 [StatsItem]
                    MemoryCategory_95 [StatsItem]
                    MemoryCategory_96 [StatsItem]
                    MemoryCategory_97 [StatsItem]
                    MemoryCategory_98 [StatsItem]
                    MemoryCategory_99 [StatsItem]
                    MemoryCategory_100 [StatsItem]
                    MemoryCategory_101 [StatsItem]
                    MemoryCategory_102 [StatsItem]
                    MemoryCategory_103 [StatsItem]
                    MemoryCategory_104 [StatsItem]
                    MemoryCategory_105 [StatsItem]
                    MemoryCategory_106 [StatsItem]
                    MemoryCategory_107 [StatsItem]
                    MemoryCategory_108 [StatsItem]
                    MemoryCategory_109 [StatsItem]
                    MemoryCategory_110 [StatsItem]
                    MemoryCategory_111 [StatsItem]
                    MemoryCategory_112 [StatsItem]
                    MemoryCategory_113 [StatsItem]
                    MemoryCategory_114 [StatsItem]
                    MemoryCategory_115 [StatsItem]
                    MemoryCategory_116 [StatsItem]
                    MemoryCategory_117 [StatsItem]
                    MemoryCategory_118 [StatsItem]
                    MemoryCategory_119 [StatsItem]
                    MemoryCategory_120 [StatsItem]
                    MemoryCategory_121 [StatsItem]
                    MemoryCategory_122 [StatsItem]
                    MemoryCategory_123 [StatsItem]
                    MemoryCategory_124 [StatsItem]
                    MemoryCategory_125 [StatsItem]
                    MemoryCategory_126 [StatsItem]
                    MemoryCategory_127 [StatsItem]
                    MemoryCategory_128 [StatsItem]
                    MemoryCategory_129 [StatsItem]
                    MemoryCategory_130 [StatsItem]
                    MemoryCategory_131 [StatsItem]
                    MemoryCategory_132 [StatsItem]
                    MemoryCategory_133 [StatsItem]
                    MemoryCategory_134 [StatsItem]
                    MemoryCategory_135 [StatsItem]
                    MemoryCategory_136 [StatsItem]
                    MemoryCategory_137 [StatsItem]
                    MemoryCategory_138 [StatsItem]
                    MemoryCategory_139 [StatsItem]
                    MemoryCategory_140 [StatsItem]
                    MemoryCategory_141 [StatsItem]
                    MemoryCategory_142 [StatsItem]
                    MemoryCategory_143 [StatsItem]
                    MemoryCategory_144 [StatsItem]
                    MemoryCategory_145 [StatsItem]
                    MemoryCategory_146 [StatsItem]
                    MemoryCategory_147 [StatsItem]
                    MemoryCategory_148 [StatsItem]
                    MemoryCategory_149 [StatsItem]
                    MemoryCategory_150 [StatsItem]
                    MemoryCategory_151 [StatsItem]
                    MemoryCategory_152 [StatsItem]
                    MemoryCategory_153 [StatsItem]
                    MemoryCategory_154 [StatsItem]
                    MemoryCategory_155 [StatsItem]
                    MemoryCategory_156 [StatsItem]
                    MemoryCategory_157 [StatsItem]
                    MemoryCategory_158 [StatsItem]
                    MemoryCategory_159 [StatsItem]
                    MemoryCategory_160 [StatsItem]
                    MemoryCategory_161 [StatsItem]
                    MemoryCategory_162 [StatsItem]
                    MemoryCategory_163 [StatsItem]
                    MemoryCategory_164 [StatsItem]
                    MemoryCategory_165 [StatsItem]
                    MemoryCategory_166 [StatsItem]
                    MemoryCategory_167 [StatsItem]
                    MemoryCategory_168 [StatsItem]
                    MemoryCategory_169 [StatsItem]
                    MemoryCategory_170 [StatsItem]
                    MemoryCategory_171 [StatsItem]
                    MemoryCategory_172 [StatsItem]
                    MemoryCategory_173 [StatsItem]
                    MemoryCategory_174 [StatsItem]
                    MemoryCategory_175 [StatsItem]
                    MemoryCategory_176 [StatsItem]
                    MemoryCategory_177 [StatsItem]
                    MemoryCategory_178 [StatsItem]
                    MemoryCategory_179 [StatsItem]
                    MemoryCategory_180 [StatsItem]
                    MemoryCategory_181 [StatsItem]
                    MemoryCategory_182 [StatsItem]
                    MemoryCategory_183 [StatsItem]
                    MemoryCategory_184 [StatsItem]
                    MemoryCategory_185 [StatsItem]
                    MemoryCategory_186 [StatsItem]
                    MemoryCategory_187 [StatsItem]
                    MemoryCategory_188 [StatsItem]
                    MemoryCategory_189 [StatsItem]
                    MemoryCategory_190 [StatsItem]
                    MemoryCategory_191 [StatsItem]
                    MemoryCategory_192 [StatsItem]
                    MemoryCategory_193 [StatsItem]
                    MemoryCategory_194 [StatsItem]
                    MemoryCategory_195 [StatsItem]
                    MemoryCategory_196 [StatsItem]
                    MemoryCategory_197 [StatsItem]
                    MemoryCategory_198 [StatsItem]
                    MemoryCategory_199 [StatsItem]
                    MemoryCategory_200 [StatsItem]
                    MemoryCategory_201 [StatsItem]
                    MemoryCategory_202 [StatsItem]
                    MemoryCategory_203 [StatsItem]
                    MemoryCategory_204 [StatsItem]
                    MemoryCategory_205 [StatsItem]
                    MemoryCategory_206 [StatsItem]
                    MemoryCategory_207 [StatsItem]
                    MemoryCategory_208 [StatsItem]
                    MemoryCategory_209 [StatsItem]
                    MemoryCategory_210 [StatsItem]
                    MemoryCategory_211 [StatsItem]
                    MemoryCategory_212 [StatsItem]
                    MemoryCategory_213 [StatsItem]
                    MemoryCategory_214 [StatsItem]
                    MemoryCategory_215 [StatsItem]
                    MemoryCategory_216 [StatsItem]
                    MemoryCategory_217 [StatsItem]
                    MemoryCategory_218 [StatsItem]
                    MemoryCategory_219 [StatsItem]
                    MemoryCategory_220 [StatsItem]
                    MemoryCategory_221 [StatsItem]
                    MemoryCategory_222 [StatsItem]
                    MemoryCategory_223 [StatsItem]
                    MemoryCategory_224 [StatsItem]
                    MemoryCategory_225 [StatsItem]
                    MemoryCategory_226 [StatsItem]
                    MemoryCategory_227 [StatsItem]
                    MemoryCategory_228 [StatsItem]
                    MemoryCategory_229 [StatsItem]
                    MemoryCategory_230 [StatsItem]
                    MemoryCategory_231 [StatsItem]
                    MemoryCategory_232 [StatsItem]
                    MemoryCategory_233 [StatsItem]
                    MemoryCategory_234 [StatsItem]
                    MemoryCategory_235 [StatsItem]
                    MemoryCategory_236 [StatsItem]
                    MemoryCategory_237 [StatsItem]
                    MemoryCategory_238 [StatsItem]
                    MemoryCategory_239 [StatsItem]
                    MemoryCategory_240 [StatsItem]
                    MemoryCategory_241 [StatsItem]
                    MemoryCategory_242 [StatsItem]
                    MemoryCategory_243 [StatsItem]
                    MemoryCategory_244 [StatsItem]
                    MemoryCategory_245 [StatsItem]
                    MemoryCategory_246 [StatsItem]
                    MemoryCategory_247 [StatsItem]
                    MemoryCategory_248 [StatsItem]
                    MemoryCategory_249 [StatsItem]
                    MemoryCategory_250 [StatsItem]
                    MemoryCategory_251 [StatsItem]
                    MemoryCategory_252 [StatsItem]
                    MemoryCategory_253 [StatsItem]
                    MemoryCategory_254 [StatsItem]
                    MemoryCategory_255 [StatsItem]
            MaxMemory [StatsItem]
            CPU [StatsItem]
            MaxCPU [StatsItem]
            GPU [StatsItem]
            MaxGPU [StatsItem]
            Ping [StatsItem]
            MaxPing [StatsItem]
            NetworkReceived [StatsItem]
            MaxNetworkReceived [StatsItem]
            NetworkSent [StatsItem]
            MaxNetworkSent [StatsItem]
        RenderBreakdown [StatsItem]
            Undefined [StatsItem]
            Opaque [StatsItem]
            Transparent [StatsItem]
            Terrain [StatsItem]
            Grass [StatsItem]
            UI [StatsItem]
            Decal [StatsItem]
            Cloud [StatsItem]
            GenericPostProcess [StatsItem]
            SSAO [StatsItem]
            DOF [StatsItem]
            Particles [StatsItem]
            Sky [StatsItem]
        Workspace [StatsItem]
            FPS [StatsItem]
            Heartbeat [StatsItem]
            Environment Speed % [StatsItem]
            World [StatsItem]
                Primitives [StatsItem]
                Joints [StatsItem]
                Contacts [StatsItem]
                Non-Anchored Assemblies [StatsItem]
                Sleeping Assemblies [StatsItem]
                Sleep Checking Assemblies [StatsItem]
                Awake Assemblies [StatsItem]
            Contacts [StatsItem]
                CtctStageCtcts [StatsItem]
                SteppingCtcts [StatsItem]
            Kernel [StatsItem]
                Constraints [StatsItem]
            File Operations [StatsItem]
                Total Load Time [StatsItem]
                SyncHttpGet Time [StatsItem]
                XML Load Time [StatsItem]
                Join All Time [StatsItem]
        Sound [StatsItem]
            CPU [StatsItem]
                Dsp [StatsItem]
                Stream [StatsItem]
                Geometry [StatsItem]
                Update [StatsItem]
            ChannelsPlaying [StatsItem]
            Current [StatsItem]
            Max [StatsItem]
            # Sounds [StatsItem]
            # Unused [StatsItem]
        ChangeHistory [StatsItem]
            Data Size [StatsItem]
            Constrained Data Size [StatsItem]
            Stack Size [StatsItem]
        Network [StatsItem]
            Packets Thread [StatsItem]
                Rate [StatsItem]
                Activity [StatsItem]
                Physics Senders [StatsItem]
                Send Buffer Health [StatsItem]
            ServerStatsItem [StatsItem]
                Network Ping [StatsItem]
                Data Ping [RunningAverageItemInt]
                StreamingEnabled [StatsItem]
                Compression [StatsItem]
                Stats [StatsItem]
                    messageDataBytesSentPerSec [StatsItem]
                    messageTotalBytesSentPerSec [StatsItem]
                    messageDataBytesResentPerSec [StatsItem]
                    messagesBytesReceivedPerSec [StatsItem]
                    messagesBytesReceivedAndIgnoredPerSec [StatsItem]
                    bytesSentPerSec [StatsItem]
                    bytesReceivedPerSec [StatsItem]
                    totalMessageBytesPushed [StatsItem]
                    totalMessageBytesSent [StatsItem]
                    totalMessageBytesResent [StatsItem]
                    totalMessagesBytesReceived [StatsItem]
                    totalMessagesBytesReceivedAndIgnored [StatsItem]
                    totalBytesSent [StatsItem]
                    totalBytesReceived [StatsItem]
                    connectionStartTime [StatsItem]
                    outgoingBandwidthLimitBytesPerSecond [StatsItem]
                    isLimitedByOutgoingBandwidthLimit [StatsItem]
                    congestionControlLimitBytesPerSecond [StatsItem]
                    isLimitedByCongestionControl [StatsItem]
                    messageSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    bytesInSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    messagesInResendQueue [StatsItem]
                    bytesInResendQueue [StatsItem]
                    packetlossLastSecond [StatsItem]
                    packetlossTotal [StatsItem]
                    numberOfUnsplitMessages [StatsItem]
                    numberOfSplitMessages [StatsItem]
                    messageDataBytesSentPerSec [StatsItem]
                    messageTotalBytesSentPerSec [StatsItem]
                    messageDataBytesResentPerSec [StatsItem]
                    messagesBytesReceivedPerSec [StatsItem]
                    messagesBytesReceivedAndIgnoredPerSec [StatsItem]
                    bytesSentPerSec [StatsItem]
                    bytesReceivedPerSec [StatsItem]
                    totalMessageBytesPushed [StatsItem]
                    totalMessageBytesSent [StatsItem]
                    totalMessageBytesResent [StatsItem]
                    totalMessagesBytesReceived [StatsItem]
                    totalMessagesBytesReceivedAndIgnored [StatsItem]
                    totalBytesSent [StatsItem]
                    totalBytesReceived [StatsItem]
                    connectionStartTime [StatsItem]
                    outgoingBandwidthLimitBytesPerSecond [StatsItem]
                    isLimitedByOutgoingBandwidthLimit [StatsItem]
                    congestionControlLimitBytesPerSecond [StatsItem]
                    isLimitedByCongestionControl [StatsItem]
                    messageSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    bytesInSendBuffer [StatsItem]
                        IMMEDIATE_PRIORITY [StatsItem]
                        HIGH_PRIORITY [StatsItem]
                        MEDIUM_PRIORITY [StatsItem]
                        LOW_PRIORITY [StatsItem]
                    messagesInResendQueue [StatsItem]
                    bytesInResendQueue [StatsItem]
                    packetlossLastSecond [StatsItem]
                    packetlossTotal [StatsItem]
                    numberOfUnsplitMessages [StatsItem]
                    numberOfSplitMessages [StatsItem]
                Send kBps [StatsItem]
                    MtuSize [StatsItem]
                Send Buffer Health [StatsItem]
                BandwidthExceeded [StatsItem]
                CongestionControlExceeded [StatsItem]
                Receive kBps [StatsItem]
                Packet Queue [StatsItem]
                Sent Data Packets [StatsItem]
                    Size [RunningAverageItemInt]
                    Throttle [StatsItem]
                    Queue Size [StatsItem]
                    Time In Queue [StatsItem]
                    New Items Per Sec [TotalCountTimeIntervalItem]
                    Items Sent Per Sec [TotalCountTimeIntervalItem]
                OutPhysicsDetails [StatsItem]
                    CFrameOnly [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Mechanism [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Translation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Rotation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Velocity [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                InPhysicsDetails [StatsItem]
                    CFrameOnly [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Mechanism [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Translation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Rotation [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Velocity [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                DataPingDetails [StatsItem]
                    LQToS [StatsItem]
                    LBcsQ [StatsItem]
                    RakPing [StatsItem]
                    RRakRecvToAppPop [StatsItem]
                    RAppPopToDeserialize [StatsItem]
                    RDeserializeToPBQ [StatsItem]
                    RQToS [StatsItem]
                    RBscQ [StatsItem]
                    LRakRecvToAppPop [StatsItem]
                    LAppPopToSerialize [StatsItem]
                    LDeserializeToProcess [StatsItem]
                    EstTotal [StatsItem]
                    MeasuredTotal [StatsItem]
                    unrelLQToS [StatsItem]
                    unrelLBcsQ [StatsItem]
                    unrelRakPing [StatsItem]
                    unrelRRakRecvToAppPop [StatsItem]
                    unrelRAppPopToDeserialize [StatsItem]
                    unrelRDeserializeToPBQ [StatsItem]
                    unrelRQToS [StatsItem]
                    unrelRBscQ [StatsItem]
                    unrelLRakRecvToAppPop [StatsItem]
                    unrelLAppPopToSerialize [StatsItem]
                    unrelLDeserializeToProcess [StatsItem]
                    unrelEstTotal [StatsItem]
                    unrelMeasuredTotal [StatsItem]
                Send Data Types [StatsItem]
                    InstanceNew [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDelete [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Ping [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Data [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Behavior [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    State [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Appearance [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Team [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Video [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Control [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Events [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDestroy [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                Received Data Types [StatsItem]
                    InstanceNew [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDelete [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Ping [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Data [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Behavior [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    State [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Appearance [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Team [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Video [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Control [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    Events [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                    InstanceDestroy [TotalCountTimeIntervalItem]
                        Size [RunningAverageItemInt]
                Sent Physics Packets [StatsItem]
                    Size [RunningAverageItemInt]
                    Throttle [StatsItem]
                    Smoothed [StatsItem]
                    Items Per Packet [RunningAverageItemInt]
                SentTouchPackets [StatsItem]
                    Size [RunningAverageItemInt]
                    WaitingTouches [RunningAverageItemInt]
                Received Packets [StatsItem]
                Received Data Packets [StatsItem]
                    Queue Size [StatsItem]
                    Instance Size [StatsItem]
                    Waiting Refs [StatsItem]
                    Size [StatsItem]
                Received ISR Packets [StatsItem]
                    Size [StatsItem]
                Received LR Packets [StatsItem]
                    Size [StatsItem]
                Received Physics Packets [StatsItem]
                    Average Lag [StatsItem]
                    Average Buffer Seek [StatsItem]
                    Max Buffer Seek [StatsItem]
                    Wrong Order [StatsItem]
                    Size [StatsItem]
                Sent ISR Packets [StatsItem]
                    Size [StatsItem]
                In ISR Physics Details [StatsItem]
                    Mechanism [StatsItem]
                        Size [StatsItem]
                    CFrameOnly [StatsItem]
                        Size [StatsItem]
                    Translation [StatsItem]
                        Size [StatsItem]
                    Rotation [StatsItem]
                        Size [StatsItem]
                    Velocity [StatsItem]
                        Size [StatsItem]
                Out ISR Physics Details [StatsItem]
                    Mechanism [StatsItem]
                        Size [StatsItem]
                    CFrameOnly [StatsItem]
                        Size [StatsItem]
                    Translation [StatsItem]
                        Size [StatsItem]
                    Rotation [StatsItem]
                        Size [StatsItem]
                    Velocity [StatsItem]
                        Size [StatsItem]
                Sent Cluster Packets [StatsItem]
                    Size [RunningAverageItemInt]
                Received Cluster Packets [StatsItem]
                    Size [StatsItem]
                Received Touch Packets [StatsItem]
                    Size [StatsItem]
                ElapsedTime [StatsItem]
                MaxPacketLoss [StatsItem]
                TotalInDataBW [StatsItem]
                TotalOutDataBW [StatsItem]
                TotalRakIn [StatsItem]
                TotalRakOut [StatsItem]
                OutBufferHealth [StatsItem]
                PropSync [StatsItem]
                    ItemCount [StatsItem]
                    AckCount [StatsItem]
                Received Stream Data [StatsItem]
                    AvgReadTimePerItem [RunningAverageItemDouble]
                    AvgInstancesPerItem [RunningAverageItemDouble]
                    RequestedInstanceAvg [RunningAverageItemInt]
                    PendingRequestCount [StatsItem]
                    GCDistance [StatsItem]
                    NumRegions [StatsItem]
                    CurrentRadius [StatsItem]
                    NumReplicationFoci [StatsItem]
                    NumPrefetches [StatsItem]
                    PlayerPosition [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                    PlayerRegion [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                    LastKnownServerStreamCenter [StatsItem]
                        X [StatsItem]
                        Y [StatsItem]
                        Z [StatsItem]
                Lr Data [StatsItem]
                    LrBytesRecv [StatsItem]
                    LrSegmentsRecv [StatsItem]
                    LrEstimatedRawRecv [StatsItem]
                    LrEstimatedOptimizedRecv [StatsItem]
                    LrActualPreCompressRecv [StatsItem]
                    LrActualPostCompressRecv [StatsItem]
                    LrAssetsRecv [StatsItem]
                    LrAssetsByDeltaRecv [StatsItem]
                    LrDeltasRecv [StatsItem]
                    LrCancelRecv [StatsItem]
                    LrRemoveRecv [StatsItem]
                    LrCompleteRecv [StatsItem]
                    LrInlineRecv [StatsItem]
                    LrIgnoreRecv [StatsItem]
                    LrHashFail [StatsItem]
                    LrHashCheck [StatsItem]
                    LrMemCountRecv [StatsItem]
                    LrMemEstBytesRecv [StatsItem]
        Luau [StatsItem]
            disabled [StatsItem]
            threads [StatsItem]
            AverageGcTime [StatsItem]
        FrameRateManager [StatsItem]
            DeviceFeatureLevel [StatsItem]
            DeviceShadingLanguage [StatsItem]
            AverageQualityLevel [StatsItem]
            AutoQuality [StatsItem]
            NumberOfSettles [StatsItem]
            AverageSwitches [StatsItem]
            FramebufferWidth [StatsItem]
            FramebufferHeight [StatsItem]
            Batches [StatsItem]
            Indices [StatsItem]
            MaterialChanges [StatsItem]
            VideoMemoryInMB [StatsItem]
            AverageFPS [StatsItem]
            FrameTimeVariance [StatsItem]
            FrameSpikeCount [StatsItem]
            RenderAverage [StatsItem]
            PrepareAverage [StatsItem]
            PerformAverage [StatsItem]
            AveragePresent [StatsItem]
            AverageGPU [StatsItem]
            RenderThreadAverage [StatsItem]
            TotalFrameWallAverage [StatsItem]
            PerformVariance [StatsItem]
            PresentVariance [StatsItem]
            GpuVariance [StatsItem]
            MsFrame0 [StatsItem]
            MsFrame1 [StatsItem]
            MsFrame2 [StatsItem]
            MsFrame3 [StatsItem]
            MsFrame4 [StatsItem]
            MsFrame5 [StatsItem]
            MsFrame6 [StatsItem]
            MsFrame7 [StatsItem]
            MsFrame8 [StatsItem]
            MsFrame9 [StatsItem]
            MsFrame10 [StatsItem]
            MsFrame11 [StatsItem]
        Render [StatsItem]
            Memory [StatsItem]
                Video [StatsItem]
    TimerService [TimerService]
    CollectionService [CollectionService]
    SoundService [SoundService]
    VideoCaptureService [VideoCaptureService]
    LogService [LogService]
    MicroProfilerService [MicroProfilerService]
    ContentProvider [ContentProvider]
    KeyframeSequenceProvider [KeyframeSequenceProvider]
    AnimationClipProvider [AnimationClipProvider]
    Chat [Chat]
    MarketplaceService [MarketplaceService]
    Players [Players]
        hydrazx9 [Player]
            PlayerScripts [PlayerScripts]
            Backpack [Backpack]
    PointsService [PointsService]
    NotificationService [NotificationService]
    ReplicatedFirst [ReplicatedFirst]
    HttpRbxApiService [HttpRbxApiService]
    TweenService [TweenService]
    MaterialService [MaterialService]
    TextChatService [TextChatService]
        BubbleChatConfiguration [BubbleChatConfiguration]
            ImageLabel [ImageLabel]
            UICorner [UICorner]
            UIGradient [UIGradient]
            UIPadding [UIPadding]
        ChannelTabsConfiguration [ChannelTabsConfiguration]
        ChatInputBarConfiguration [ChatInputBarConfiguration]
        ChatWindowConfiguration [ChatWindowConfiguration]
    TextService [TextService]
    PermissionsService [PermissionsService]
    SharedTableRegistry [SharedTableRegistry]
    StarterPlayer [StarterPlayer]
        StarterCharacterScripts [StarterCharacterScripts]
        StarterPlayerScripts [StarterPlayerScripts]
            ClientMain [LocalScript]
                ----- SOURCE -----
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)

Registry.AutoLoadConfigs(ReplicatedStorage:WaitForChild("Configs"))
Net.Init()

local Client = script.Parent:WaitForChild("Client")
local Render = require(Client.ClientRenderEngine)
local Placement = require(Client.PlacementController)
local ShopUI = require(Client.ShopUI)

Render.Init()
Placement.Init(Render)
ShopUI.Init(Placement, Render)

local okChat, errChat = pcall(function()
	require(Client.ChatCommands).Init()
end)
if not okChat then
	warn("[ChatCommands] " .. tostring(errChat))
end

Net.Request():InvokeServer("ClientReady")

                ----- END SOURCE -----
            LocalScript [LocalScript]
                ----- SOURCE -----
local StarterGui = game:GetService("StarterGui")

-- Desativa completamente a barra de inventário (Backpack) da tela do jogador
StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Backpack, false)
                ----- END SOURCE -----
            Client [Folder]
                Animators [ModuleScript]
                    ----- SOURCE -----
--[[
	Animators: escolhe o animador de cada unidade pelo config. O ClientRenderEngine só fala com esta fábrica.
	Animation = { Mode = "Procedural" }   -- padrão: poses por nome de junta (UnitAnimator)
	Animation = { Mode = "Rig", ... }     -- animações reais do Animation Editor (RigAnimator)
	Os dois têm o mesmo contrato: :SetPivot(cf) :SetSpeed(s) :Trigger(nome, aoSoltar) :Kill() :Step(dt) e .DeathTime
]]
local UnitAnimator = require(script.Parent.UnitAnimator)
local RigAnimator = require(script.Parent.RigAnimator)

local Animators = {}

function Animators.IsRig(cfg)
	return cfg.Animation ~= nil and cfg.Animation.Mode == "Rig"
end

function Animators.new(model, role, cfg)
	if not model:IsA("Model") then
		return nil
	end
	if Animators.IsRig(cfg) then
		return RigAnimator.new(model, role, cfg)
	end
	return UnitAnimator.new(model, role, cfg)
end

return Animators

                    ----- END SOURCE -----
                ClientRenderEngine [ModuleScript]
                    ----- SOURCE -----
--[[
	ClientRenderEngine: 100% do visual roda aqui. Nenhum inimigo existe como Instance no servidor.
	- Inimigo: posição = path:PositionAt(min(D + S * (agora - T), comprimento)), com agora = workspace:GetServerTimeNow().
	  O servidor só manda âncora (D,T) + velocidade (S) no spawn e quando a velocidade muda (slow/freeze).
	- Partes simples são movidas em lote com BulkMoveTo (1 chamada/frame).
	- Projétil: lerp de origem -> posição PREVISTA do inimigo em T1 (hora do impacto, vinda do servidor).
	Assets opcionais: ReplicatedStorage.Assets.Models.{Towers,Enemies,Projectiles}.<ModelName> (também vale Assets.<Pasta> direto).
	  Torres/inimigos = Models com PrimaryPart (torre: pivô na base; inimigo: pivô no centro da altura de Visual.Size).
	  Projétil = Model com PrimaryPart apontando p/ -Z; Visual.Projectile.ModelName escolhe o modelo (Attribute BaseSize = escala 1).
	  Modelos com juntas são animados pelo UnitAnimator (procedural, funciona com partes ancoradas).
]]
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local RunService = game:GetService("RunService")
local TweenService = game:GetService("TweenService")
local Debris = game:GetService("Debris")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local EventBus = require(Shared.EventBus)
local Net = require(Shared.Net)
local PathUtil = require(Shared.PathUtil)
local Animators = require(script.Parent.Animators)

local Render = {
	Enemies = {},
	Towers = {},
	Map = nil,
	State = nil,
	Data = { Coins = 0 },
	Loadout = {},
	Events = EventBus.new(), -- "TowerChanged"(id) · "TowerRemoved"(id) · "GameState"(state) · "PlayerData"(data)
	Folder = nil,
	TowersFolder = nil,
}

local enemiesFolder, fxFolder
local projectiles = {}
local dying = {} -- modelos animados tocando a animação de morte
local pendingSpawns = {}
local bulkParts, bulkCFrames = {}, {}

local function serverNow()
	return workspace:GetServerTimeNow()
end

local function findIn(root, kind, name)
	local folder = root and root:FindFirstChild(kind)
	return folder and folder:FindFirstChild(name)
end

local function cloneAsset(kind, name, canQuery, rig)
	if not name then
		return nil
	end
	local assets = ReplicatedStorage:FindFirstChild("Assets")
	local models = assets and assets:FindFirstChild("Models")
	local template = findIn(models, kind, name) or findIn(assets, kind, name)
	if not template then
		return nil
	end
	local clone = template:Clone()
	-- rig = animações reais: só a PrimaryPart fica ancorada; o resto segue pelas juntas (Motor6D/Weld).
	-- procedural: tudo ancorado (o UnitAnimator move as peças em lote).
	local root = rig and clone:IsA("Model") and clone.PrimaryPart or nil
	local parts = clone:GetDescendants()
	table.insert(parts, clone)
	for _, d in ipairs(parts) do
		if d:IsA("BasePart") then
			d.CanCollide = false
			d.CanQuery = canQuery
			if root then
				d.Anchored = d == root
				d.Massless = true
			else
				d.Anchored = true
			end
		end
	end
	return clone
end

local function makePart(size, color, canQuery)
	local part = Instance.new("Part")
	part.Anchored = true
	part.CanCollide = false
	part.CanTouch = false
	part.CanQuery = canQuery
	part.Size = size
	part.Color = color
	part.Material = Enum.Material.SmoothPlastic
	return part
end

-- ---------------------------------------------------------------- anel de alcance (usado por UI/placement)
function Render.MakeRing(color)
	local ring = Instance.new("Part")
	ring.Shape = Enum.PartType.Cylinder
	ring.Anchored = true
	ring.CanCollide = false
	ring.CanTouch = false
	ring.CanQuery = false
	ring.Material = Enum.Material.Neon
	ring.Transparency = 0.8
	ring.Color = color or Color3.fromRGB(255, 255, 255)
	return ring
end

function Render.PlaceRing(ring, pos, range)
	ring.Size = Vector3.new(0.2, range * 2, range * 2)
	ring.CFrame = CFrame.new(pos + Vector3.new(0, 0.15, 0)) * CFrame.Angles(0, 0, math.rad(90))
end

function Render.TowerCost(def)
	local m = Render.Map and Render.Map.Config.Multipliers
	return math.ceil(def.Cost * (m and m.TowerCost or 1))
end

function Render.PickTower(inst)
	local cur = inst
	while cur and cur ~= Render.TowersFolder do
		local id = cur:GetAttribute("TDTowerId")
		if id then
			return id
		end
		cur = cur.Parent
	end
	return nil
end

-- ---------------------------------------------------------------- inimigos
local function adornee(r)
	if r.IsPart then
		return r.Inst
	end
	return r.Inst.PrimaryPart or r.Inst:FindFirstChildWhichIsA("BasePart", true)
end

local function updateBar(r)
	if r.Hp >= r.MaxHp and not r.Bar then
		return
	end
	if not r.Bar then
		local gui = Instance.new("BillboardGui")
		gui.Size = UDim2.fromOffset(60, 8)
		gui.StudsOffset = Vector3.new(0, r.BarY, 0)
		gui.AlwaysOnTop = true
		gui.Adornee = adornee(r)
		local back = Instance.new("Frame")
		back.Size = UDim2.fromScale(1, 1)
		back.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
		back.BorderSizePixel = 0
		back.Parent = gui
		local fill = Instance.new("Frame")
		fill.Name = "Fill"
		fill.Size = UDim2.fromScale(1, 1)
		fill.BackgroundColor3 = Color3.fromRGB(90, 220, 90)
		fill.BorderSizePixel = 0
		fill.Parent = back
		gui.Parent = r.Inst
		r.Bar = gui
	end
	r.Bar.Frame.Fill.Size = UDim2.fromScale(math.clamp(r.Hp / r.MaxHp, 0, 1), 1)
end

local function applyTint(r)
	local color = r.BaseColor
	for _, c in pairs(r.Tints) do
		color = c
		break
	end
	if r.IsPart then
		r.Inst.Color = color
	elseif r.TintParts then
		local tinted = next(r.Tints) ~= nil
		for part, original in pairs(r.TintParts) do
			part.Color = tinted and color or original
		end
	end
end

local function newEnemy(p)
	if Render.Enemies[p.Id] then
		return
	end
	local cfg = Registry.Of("Enemies"):Get(p.Cfg)
	local path = Render.Map and Render.Map.Paths[p.Path]
	if not cfg or not path then
		return
	end
	local vis = cfg.Visual or {}
	local size = vis.Size or Vector3.new(2, 3, 2)
	local inst = cloneAsset("Enemies", cfg.ModelName, false, Animators.IsRig(cfg))
	if not inst then
		inst = makePart(size, vis.Color or Color3.fromRGB(200, 60, 60), false)
	end
	inst.Parent = enemiesFolder
	local isPart = inst:IsA("BasePart")
	local anim = not isPart and inst:IsA("Model") and Animators.new(inst, "Enemy", cfg) or nil
	local tintParts
	if not isPart then
		tintParts = {}
		for _, d in ipairs(inst:GetDescendants()) do
			if d:IsA("BasePart") and d.Transparency < 1 then
				tintParts[d] = d.Color
			end
		end
	end
	local r = {
		Id = p.Id,
		Cfg = cfg,
		Path = path,
		Inst = inst,
		IsPart = isPart,
		D = p.D,
		T = p.T,
		S = p.S,
		Hp = p.Hp,
		MaxHp = p.MaxHp,
		YOffset = size.Y / 2,
		BarY = (isPart and size.Y / 2 or inst:GetAttribute("BarHeight") or size.Y / 2) + 1.5,
		Anim = anim,
		TintParts = tintParts,
		Tints = {},
		BaseColor = isPart and inst.Color or Color3.new(1, 1, 1),
		LastPos = path:PositionAt(p.D),
	}
	Render.Enemies[p.Id] = r
	updateBar(r)
end

local function removeEnemy(id, reason)
	local r = Render.Enemies[id]
	if not r then
		return
	end
	Render.Enemies[id] = nil
	if r.Bar then
		r.Bar:Destroy()
	end
	if reason == "Killed" and r.IsPart then
		TweenService:Create(r.Inst, TweenInfo.new(0.25), { Transparency = 1, Size = r.Inst.Size * 0.3 }):Play()
		Debris:AddItem(r.Inst, 0.3)
	elseif reason == "Killed" and r.Anim then
		r.Anim:Kill()
		table.insert(dying, { Anim = r.Anim, Inst = r.Inst, Age = 0 })
	else
		r.Inst:Destroy()
	end
end

-- ---------------------------------------------------------------- torres
local function newTower(p)
	local cfg = Registry.Of("Towers"):Get(p.Cfg)
	if not cfg or Render.Towers[p.Id] then
		return
	end
	local vis = cfg.Visual or {}
	local size = vis.Size or Vector3.new(3, 4, 3)
	local inst = cloneAsset("Towers", cfg.ModelName, true, Animators.IsRig(cfg))
	local anim, muzzle
	if inst then
		inst:PivotTo(CFrame.new(p.Pos))
		if inst:IsA("Model") then
			anim = Animators.new(inst, "Tower", cfg)
			muzzle = inst:FindFirstChild("Muzzle", true)
			if muzzle and not muzzle:IsA("Attachment") then
				muzzle = nil
			end
		end
	else
		inst = makePart(size, vis.Color or Color3.fromRGB(200, 200, 200), true)
		inst.Position = p.Pos + Vector3.new(0, size.Y / 2, 0)
	end
	inst:SetAttribute("TDTowerId", p.Id)
	inst.Parent = Render.TowersFolder
	Render.Towers[p.Id] = {
		Id = p.Id,
		Cfg = cfg,
		Inst = inst,
		Position = p.Pos,
		Owner = p.Owner,
		Range = p.Range,
		Splash = p.Splash,
		Tiers = p.Tiers,
		Mode = p.Mode,
		Invested = p.Invested,
		Damage = p.Damage,
		Interval = p.Interval,
		Height = size.Y * 0.8,
		Anim = anim,
		Muzzle = muzzle,
	}
	Render.Events:Fire("TowerChanged", p.Id)
end

local function tierSum(tiers)
	local n = 0
	for _, v in pairs(tiers) do
		n += v
	end
	return n
end

local function updateTower(p)
	local t = Render.Towers[p.Id]
	if not t then
		return
	end
	local upgraded = tierSum(p.Tiers) > tierSum(t.Tiers)
	t.Range, t.Splash, t.Tiers, t.Mode, t.Invested = p.Range, p.Splash, p.Tiers, p.Mode, p.Invested
	t.Damage, t.Interval = p.Damage, p.Interval
	if upgraded and t.Anim then
		t.Anim:Trigger("Upgrade")
	end
	Render.Events:Fire("TowerChanged", p.Id)
end

local function removeTower(id)
	local t = Render.Towers[id]
	if not t then
		return
	end
	Render.Towers[id] = nil
	t.Inst:Destroy()
	Render.Events:Fire("TowerRemoved", id)
end

-- ---------------------------------------------------------------- projéteis / fx
local function impactFx(pos, radius, color)
	local fx = Instance.new("Part")
	fx.Shape = Enum.PartType.Ball
	fx.Anchored = true
	fx.CanCollide = false
	fx.CanQuery = false
	fx.CanTouch = false
	fx.Material = Enum.Material.Neon
	fx.Transparency = 0.4
	fx.Color = color
	fx.Size = Vector3.one
	fx.Position = pos
	fx.Parent = fxFolder
	TweenService
		:Create(fx, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {
			Size = Vector3.one * radius * 2,
			Transparency = 1,
		})
		:Play()
	Debris:AddItem(fx, 0.35)
end

local function placeProjectile(pr, pos)
	if pr.IsAsset then
		local d = pos - pr.LastPos
		if d.Magnitude > 1e-3 then
			pr.Dir = d.Unit
		end
		pr.LastPos = pos
		pr.Part:PivotTo(CFrame.lookAt(pos, pos + pr.Dir))
	else
		pr.Part.Position = pos
	end
end

-- impacto de projétil com modelo próprio: emissores com atributo EmitCount soltam uma rajada, rastros param,
-- o corpo some (exceto peças com atributo KeepOnImpact) e o modelo fica ImpactLifetime segundos para os efeitos terminarem
local function projectileImpact(pr)
	local inst = pr.Part
	if not pr.IsAsset then
		inst:Destroy()
		return
	end
	inst:PivotTo(CFrame.lookAt(pr.Target, pr.Target + pr.Dir))
	for _, d in ipairs(inst:GetDescendants()) do
		if d:IsA("ParticleEmitter") then
			d.Enabled = false
			local count = d:GetAttribute("EmitCount")
			if count then
				d:Emit(count)
			end
		elseif d:IsA("Trail") then
			d.Enabled = false
		elseif d:IsA("BasePart") and not d:GetAttribute("KeepOnImpact") then
			d.Transparency = 1
		end
	end
	Debris:AddItem(inst, pr.Cfg.ImpactLifetime or 1.5)
end

local function fireTower(f)
	local tw = Render.Towers[f.Tower]
	if not tw then
		return
	end
	local en = Render.Enemies[f.Enemy]
	local pv = tw.Cfg.Visual and tw.Cfg.Visual.Projectile or {}

	if en then
		local look = Vector3.new(en.LastPos.X, tw.Position.Y, en.LastPos.Z)
		if look ~= tw.Position then
			local rot = CFrame.lookAt(tw.Position, look)
			if tw.Anim then
				tw.Anim:SetPivot(rot)
			else
				tw.Inst:PivotTo(rot)
			end
		end
	end

	local fallback = en and en.LastPos or tw.Position
	local launched = false

	-- o projétil sai no instante de "soltar" da animação (procedural: ReleaseTime; rig: marcador "Release")
	local function launch()
		if launched or not Render.Towers[tw.Id] then
			return
		end
		launched = true
		if tw.Anim then
			tw.Anim:Step(0) -- aplica a pose atual: o Muzzle precisa estar no lugar certo
		end
		local now = serverNow()
		local cur = Render.Enemies[f.Enemy]
		local origin = tw.Muzzle and tw.Muzzle.WorldPosition or (tw.Position + Vector3.new(0, tw.Height, 0))
		local target = cur and cur.LastPos or fallback
		local flat = target - origin
		local dir = flat.Magnitude > 1e-3 and flat.Unit or Vector3.new(0, 0, -1)

		local part = pv.ModelName and cloneAsset("Projectiles", pv.ModelName, false)
		local isAsset = part ~= nil
		if isAsset then
			local base = part:GetAttribute("BaseSize")
			if base and pv.Size and part:IsA("Model") then
				part:ScaleTo(pv.Size / base)
			end
			part:PivotTo(CFrame.lookAt(origin, origin + dir))
			part.Parent = fxFolder
		else
			part = Instance.new("Part")
			part.Shape = Enum.PartType.Ball
			part.Anchored = true
			part.CanCollide = false
			part.CanQuery = false
			part.CanTouch = false
			part.Material = Enum.Material.Neon
			part.Color = pv.Color or Color3.fromRGB(255, 255, 255)
			part.Size = Vector3.one * (pv.Size or 0.7)
			part.Position = origin
			part.Parent = fxFolder
		end
		table.insert(projectiles, {
			Part = part,
			IsAsset = isAsset,
			Cfg = pv,
			LastPos = origin,
			Dir = dir,
			From = origin,
			EnemyId = f.Enemy,
			T0 = now,
			T1 = math.max(f.T1, now + 0.1), -- o acerto é decidido pelo servidor (T1); mínimo de 0.1s visível
			Arc = pv.Arc or 0,
			Splash = tw.Splash,
			Color = pv.Color or Color3.fromRGB(255, 255, 255),
			Target = target,
		})
	end

	if tw.Anim then
		tw.Anim:Trigger("Attack", launch)
	else
		launch()
	end
end

-- ---------------------------------------------------------------- loop de render
local function step(dt)
	local t = serverNow()

	local n = 0
	for _, r in pairs(Render.Enemies) do
		local d = r.D + r.S * (t - r.T)
		local len = r.Path.Length
		if d > len then
			d = len
		elseif d < 0 then
			d = 0
		end
		local pos = r.Path:PositionAt(d)
		r.LastPos = pos
		local center = pos + Vector3.new(0, r.YOffset, 0)
		local cf = CFrame.lookAt(center, center + r.Path:DirectionAt(d))
		if r.IsPart then
			n += 1
			bulkParts[n] = r.Inst
			bulkCFrames[n] = cf
		elseif r.Anim then
			r.Anim:SetPivot(cf)
			r.Anim:SetSpeed(r.S)
			r.Anim:Step(dt)
		else
			r.Inst:PivotTo(cf)
		end
	end
	for i = #bulkParts, n + 1, -1 do
		bulkParts[i] = nil
		bulkCFrames[i] = nil
	end
	if n > 0 then
		workspace:BulkMoveTo(bulkParts, bulkCFrames, Enum.BulkMoveMode.FireCFrameChanged)
	end

	for _, tw in pairs(Render.Towers) do
		if tw.Anim then
			tw.Anim:Step(dt)
		end
	end
	for i = #dying, 1, -1 do
		local d = dying[i]
		d.Age += dt
		d.Anim:Step(dt)
		if d.Age >= (d.Anim.DeathTime or 0.5) then
			d.Inst:Destroy()
			table.remove(dying, i)
		end
	end

	for i = #projectiles, 1, -1 do
		local pr = projectiles[i]
		local en = Render.Enemies[pr.EnemyId]
		if en then
			local d = math.min(en.D + en.S * (pr.T1 - en.T), en.Path.Length)
			pr.Target = en.Path:PositionAt(d) + Vector3.new(0, en.YOffset, 0)
		end
		local alpha = (t - pr.T0) / (pr.T1 - pr.T0)
		if alpha >= 1 then
			if pr.Splash > 0 then
				impactFx(pr.Target, pr.Splash, pr.Color)
			end
			projectileImpact(pr)
			table.remove(projectiles, i)
		else
			alpha = math.max(alpha, 0)
			local pos = pr.From:Lerp(pr.Target, alpha)
			if pr.Arc > 0 then
				pos += Vector3.new(0, math.sin(math.pi * alpha) * pr.Arc, 0)
			end
			placeProjectile(pr, pos)
		end
	end
end

-- ---------------------------------------------------------------- rede
local function setMap(mapId)
	for _, r in pairs(Render.Enemies) do
		r.Inst:Destroy()
	end
	for _, tw in pairs(Render.Towers) do
		tw.Inst:Destroy()
	end
	for _, pr in ipairs(projectiles) do
		pr.Part:Destroy()
	end
	for _, d in ipairs(dying) do
		d.Inst:Destroy()
	end
	table.clear(dying)
	table.clear(Render.Enemies)
	table.clear(Render.Towers)
	table.clear(projectiles)

	local cfg = Registry.Of("Maps"):Get(mapId)
	if not cfg then
		Render.Map = nil
		return
	end
	local paths = {}
	for id, points in pairs(cfg.Paths) do
		paths[id] = PathUtil.new(points)
	end
	Render.Map = { Id = mapId, Config = cfg, Paths = paths }
	for _, p in ipairs(pendingSpawns) do
		newEnemy(p)
	end
	table.clear(pendingSpawns)
end

local function onDelta(p)
	for _, e in ipairs(p.EnemySpawned) do
		if Render.Map then
			newEnemy(e)
		else
			table.insert(pendingSpawns, e) -- mapa ainda não chegou (entrada tardia)
		end
	end
	for _, m in ipairs(p.EnemyMotion) do
		local r = Render.Enemies[m.Id]
		if r then
			r.D, r.T, r.S = m.D, m.T, m.S
		end
	end
	for _, h in ipairs(p.EnemyHealth) do
		local r = Render.Enemies[h.Id]
		if r then
			r.Hp = h.Hp
			updateBar(r)
		end
	end
	for _, s in ipairs(p.Status) do
		local r = Render.Enemies[s.Enemy]
		if r then
			local def = Registry.Of("StatusEffects"):Get(s.Effect)
			r.Tints[s.Effect] = s.On and def and def.Visual and def.Visual.Color or nil
			applyTint(r)
		end
	end
	for _, tp in ipairs(p.TowerPlaced) do
		newTower(tp)
	end
	for _, tu in ipairs(p.TowerUpdated) do
		updateTower(tu)
	end
	for _, f in ipairs(p.TowerFired) do
		fireTower(f)
	end
	for _, id in ipairs(p.TowerRemoved) do
		removeTower(id.Id)
	end
	for _, e in ipairs(p.EnemyRemoved) do
		removeEnemy(e.Id, e.Reason)
	end
end

function Render.Init()
	Render.Folder = Instance.new("Folder")
	Render.Folder.Name = "TDClient"
	Render.Folder.Parent = workspace
	Render.TowersFolder = Instance.new("Folder")
	Render.TowersFolder.Name = "Towers"
	Render.TowersFolder.Parent = Render.Folder
	enemiesFolder = Instance.new("Folder")
	enemiesFolder.Name = "Enemies"
	enemiesFolder.Parent = Render.Folder
	fxFolder = Instance.new("Folder")
	fxFolder.Name = "FX"
	fxFolder.Parent = Render.Folder

	Net.Event("GameState").OnClientEvent:Connect(function(state)
		Render.State = state
		if not Render.Map or Render.Map.Id ~= state.MapId then
			setMap(state.MapId)
		end
		Render.Events:Fire("GameState", state)
	end)
	Net.Event("PlayerData").OnClientEvent:Connect(function(data)
		Render.Data = data
		Render.Events:Fire("PlayerData", data)
	end)
	Net.Event("Loadout").OnClientEvent:Connect(function(list)
		Render.Loadout = list
		Render.Events:Fire("Loadout", list)
	end)
	Net.Event("Delta").OnClientEvent:Connect(onDelta)
	RunService.RenderStepped:Connect(step)
end

return Render

                    ----- END SOURCE -----
                PlacementController [ModuleScript]
                    ----- SOURCE -----
--[[
	PlacementController: fantasma da torre (verde/vermelho), confirmação por clique/toque e seleção de torres.
	O cliente só PREVÊ com PlacementRules; quem decide é o servidor (Request "PlaceTower").
]]
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)
local PlacementRules = require(Shared.PlacementRules)

local GREEN, RED = Color3.fromRGB(90, 220, 110), Color3.fromRGB(230, 80, 80)

local Placement = { Active = nil, OnSelect = nil, OnResult = nil }
local Render
local ghost, ring, conn
local activeRange = 0
local pointer = nil -- só usado no toque
local currentPos, currentValid, currentReason = nil, false, nil

function Placement.Cancel()
	Placement.Active = nil
	currentPos = nil
	if conn then
		conn:Disconnect()
		conn = nil
	end
	if ghost then
		ghost:Destroy()
		ghost = nil
	end
	if ring then
		ring:Destroy()
		ring = nil
	end
end

local function update()
	if not Placement.Active or not Render.Map then
		return
	end
	local camera = workspace.CurrentCamera
	local loc = pointer or UserInputService:GetMouseLocation()
	local ray = camera:ViewportPointToRay(loc.X, loc.Y)
	local params = RaycastParams.new()
	params.FilterType = Enum.RaycastFilterType.Exclude
	params.FilterDescendantsInstances = { Render.Folder, Players.LocalPlayer.Character }
	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
	if not hit then
		currentPos = nil
		ghost.Transparency = 1
		return
	end
	local y = Render.Map.Config.GroundY or 0
	currentPos = Vector3.new(hit.Position.X, y, hit.Position.Z)
	currentValid, currentReason = PlacementRules.Check(Render.Map, currentPos, Render.Towers)
	ghost.Position = currentPos + Vector3.new(0, ghost.Size.Y / 2, 0)
	ghost.Transparency = 0.45
	local color = currentValid and GREEN or RED
	ghost.Color = color
	ring.Color = color
	if activeRange > 0 then
		ring.Transparency = 0.8
		Render.PlaceRing(ring, currentPos, activeRange)
	else
		ring.Transparency = 1
	end
end

function Placement.Begin(towerId)
	Placement.Cancel()
	local def = Registry.Of("Towers"):Get(towerId)
	if not def then
		return
	end
	Placement.Active = towerId
	if Placement.OnSelect then
		Placement.OnSelect(nil)
	end
	local vis = def.Visual or {}
	ghost = Instance.new("Part")
	ghost.Anchored = true
	ghost.CanCollide = false
	ghost.CanQuery = false
	ghost.CanTouch = false
	ghost.Size = vis.Size or Vector3.new(3, 4, 3)
	ghost.Transparency = 1
	ghost.Parent = Render.Folder
	ring = Render.MakeRing()
	ring.Parent = Render.Folder
	activeRange = def.Stats and def.Stats.Range or 0
	conn = RunService.RenderStepped:Connect(update)
end

function Placement.Toggle(towerId)
	if Placement.Active == towerId then
		Placement.Cancel()
	else
		Placement.Begin(towerId)
	end
end

local function confirm()
	if not Placement.Active or not currentPos then
		return
	end
	if not currentValid then
		if Placement.OnResult then
			Placement.OnResult({ Ok = false, Error = currentReason })
		end
		return
	end
	local id, pos = Placement.Active, currentPos
	if not UserInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
		Placement.Cancel() -- segure Shift para colocar várias
	end
	local res = Net.Request():InvokeServer("PlaceTower", { TowerId = id, Position = pos })
	if Placement.OnResult then
		Placement.OnResult(res)
	end
end

local function selectAt(loc)
	local ray = workspace.CurrentCamera:ViewportPointToRay(loc.X, loc.Y)
	local params = RaycastParams.new()
	params.FilterType = Enum.RaycastFilterType.Include
	params.FilterDescendantsInstances = { Render.TowersFolder }
	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
	local id = hit and Render.PickTower(hit.Instance) or nil
	if Placement.OnSelect then
		Placement.OnSelect(id)
	end
end

function Placement.Init(renderEngine)
	Render = renderEngine

	UserInputService.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.Touch then
			pointer = Vector2.new(input.Position.X, input.Position.Y)
		end
	end)

	UserInputService.InputBegan:Connect(function(input, processed)
		if processed then
			return
		end
		local t = input.UserInputType
		if t == Enum.UserInputType.MouseButton1 then
			pointer = nil
			if Placement.Active then
				confirm()
			else
				selectAt(UserInputService:GetMouseLocation())
			end
		elseif t == Enum.UserInputType.MouseButton2 or (t == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.Escape) then
			Placement.Cancel()
		elseif t == Enum.UserInputType.Touch then
			pointer = Vector2.new(input.Position.X, input.Position.Y)
			if not Placement.Active then
				selectAt(pointer)
			end
		end
	end)

	-- toque: arraste para posicionar, solte para confirmar
	UserInputService.InputEnded:Connect(function(input, processed)
		if not processed and input.UserInputType == Enum.UserInputType.Touch and Placement.Active then
			confirm()
		end
	end)
end

return Placement

                    ----- END SOURCE -----
                RigAnimator [ModuleScript]
                    ----- SOURCE -----
--[[
	RigAnimator: mesmo contrato do UnitAnimator, mas toca AnimationTracks reais (Animation Editor).
	O ClientRenderEngine ancora só a PrimaryPart quando Animation.Mode = "Rig"; o resto do modelo segue pelas juntas.
	AnimationController e Animator são criados se o modelo não tiver.

	Animation = {
		Mode = "Rig",
		Tracks = { Idle = "rbxassetid://...", Walk = "...", Attack = "...", Upgrade = "...", Death = "..." },  -- todos opcionais
		WalkSpeed = 9,        -- studs/s em que o Walk toca a 1x (padrão: Speed do config do inimigo)
		ReleaseMarker = true, -- KeyframeMarker "Release" no Attack = instante em que o projétil sai
		ReleaseTime = 0.3,    -- alternativa sem marcador: segundos após o início do Attack (0 = sai na hora)
	}
]]
local RigAnimator = {}
RigAnimator.__index = RigAnimator

local PRIORITY = {
	Idle = Enum.AnimationPriority.Idle,
	Walk = Enum.AnimationPriority.Movement,
	Attack = Enum.AnimationPriority.Action,
	Upgrade = Enum.AnimationPriority.Action2,
	Death = Enum.AnimationPriority.Action4,
}
local LOOPED = { Idle = true, Walk = true }

function RigAnimator.new(model, role, cfg)
	if not model.PrimaryPart then
		return nil
	end
	local a = cfg.Animation or {}
	return setmetatable({
		Model = model,
		Role = role,
		Config = a,
		Tracks = {},
		Loaded = false,
		Pivot = model:GetPivot(),
		Speed = 0,
		WalkRef = a.WalkSpeed or cfg.Speed or 8,
		ReleaseTime = a.ReleaseTime or 0,
		DeathTime = 0.15,
		PendingRelease = nil,
		ReleaseAt = 0,
		Time = 0,
		Dead = false,
	}, RigAnimator)
end

-- carrega as animações só quando o modelo já está no workspace (o Animator exige isso)
function RigAnimator:_load()
	if self.Loaded or not self.Model:IsDescendantOf(workspace) then
		return
	end
	self.Loaded = true
	local controller = self.Model:FindFirstChildWhichIsA("AnimationController", true)
		or self.Model:FindFirstChildWhichIsA("Humanoid", true)
	if not controller then
		controller = Instance.new("AnimationController")
		controller.Parent = self.Model
	end
	local animator = controller:FindFirstChildWhichIsA("Animator")
	if not animator then
		animator = Instance.new("Animator")
		animator.Parent = controller
	end
	for name, id in pairs(self.Config.Tracks or {}) do
		local anim = Instance.new("Animation")
		anim.AnimationId = id
		local ok, track = pcall(function()
			return animator:LoadAnimation(anim)
		end)
		if ok and track then
			track.Priority = PRIORITY[name] or Enum.AnimationPriority.Action
			track.Looped = LOOPED[name] == true
			self.Tracks[name] = track
		else
			warn(("[RigAnimator] %s: não carregou a animação '%s'"):format(self.Model.Name, name))
		end
	end
	if self.Tracks.Idle then
		self.Tracks.Idle:Play()
	end
	if self.Tracks.Walk then
		self.Tracks.Walk:Play(0.1, 1, 0) -- começa parado; SetSpeed liga o ciclo
	end
	if self.Tracks.Death then
		self.DeathTime = math.max(self.Tracks.Death.Length, 0.15)
	end
end

function RigAnimator:SetPivot(cf)
	self.Pivot = cf
end

function RigAnimator:SetSpeed(speed)
	self.Speed = speed
	local walk = self.Tracks.Walk
	if walk and not self.Dead then
		walk:AdjustSpeed(speed > 0.05 and speed / self.WalkRef or 0) -- 0 = pose congelada
	end
end

function RigAnimator:_release()
	local fn = self.PendingRelease
	if fn then
		self.PendingRelease = nil
		fn()
	end
end

function RigAnimator:Trigger(name, onRelease)
	self:_load()
	local track = self.Tracks[name]
	if track then
		track:Play(0.05, 1, 1)
	end
	if name ~= "Attack" or not onRelease then
		return
	end
	self:_release() -- solta o disparo anterior, se ainda estava pendente
	if not track then
		onRelease()
	elseif self.Config.ReleaseMarker then
		self.PendingRelease = onRelease
		self.ReleaseAt = self.Time + 1 -- segurança se o marcador não existir na animação
		local conn
		conn = track:GetMarkerReachedSignal("Release"):Connect(function()
			conn:Disconnect()
			self:_release()
		end)
	elseif self.ReleaseTime > 0 then
		self.PendingRelease = onRelease
		self.ReleaseAt = self.Time + self.ReleaseTime
	else
		onRelease()
	end
end

function RigAnimator:Kill()
	if self.Dead then
		return
	end
	self.Dead = true
	self:_load()
	self:_release()
	for name, track in pairs(self.Tracks) do
		if name ~= "Death" then
			track:Stop(0.05)
		end
	end
	if self.Tracks.Death then
		self.Tracks.Death:Play(0.05, 1, 1)
	end
end

function RigAnimator:Step(dt)
	self.Time += dt
	self:_load()
	self.Model:PivotTo(self.Pivot)
	if self.PendingRelease and self.Time >= self.ReleaseAt then
		self:_release()
	end
end

return RigAnimator

                    ----- END SOURCE -----
                ShopUI [ModuleScript]
                    ----- SOURCE -----
--[[
	ShopUI (Factory): NENHUM botão é desenhado à mão.
	- Loja: um clone do template (ReplicatedStorage.Template2) por entrada de TowersConfig, dentro de MainUI.Units.Background
	- Painel da torre selecionada: upgrades/targeting/venda gerados de cfg.Upgrades e cfg.Targeting
	- HUD: estado, onda, vidas, moedas e contagem regressiva
]]
local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local Shared = ReplicatedStorage:WaitForChild("Shared")
local Registry = require(Shared.Registry)
local Net = require(Shared.Net)
local UnitCard = require(script.Parent.UnitCard)
local UnitPanel = require(script.Parent.UnitPanel)

local ERRORS = {
	NotEnoughCoins = "Moedas insuficientes",
	NotEquipped = "Equipe essa unidade no inventário",
	LoadoutFull = "Slots cheios: desequipe uma unidade",
	CannotBuildNow = "Não é possível construir agora",
	OutOfBounds = "Fora da área do mapa",
	TooCloseToPath = "Muito perto do caminho",
	TooCloseToTower = "Muito perto de outra torre",
	LimitReached = "Limite dessa torre atingido",
	MaxTier = "Nível máximo",
	PathLocked = "Caminho bloqueado por outro upgrade",
	NotYourTower = "Essa torre não é sua",
	RateLimited = "Calma! Muitas ações",
}
local STATE_NAMES = {
	WaitingForPlayers = "Aguardando jogadores",
	Intermission = "Intervalo",
	WaveActive = "Onda em andamento",
	GameOver = "Fim de jogo",
	Victory = "Vitória!",
}

local TEMPLATE_NAME = "Template2" -- troque para "Template1" quando quiser cards com ícone

local ShopUI = {}

local function new(class, props, parent)
	local inst = Instance.new(class)
	for k, v in pairs(props) do
		inst[k] = v
	end
	inst.Parent = parent
	return inst
end

function ShopUI.Init(Placement, Render)
	local player = Players.LocalPlayer
	local playerGui = player:WaitForChild("PlayerGui")
	local gui = new("ScreenGui", { Name = "TDUI", ResetOnSpawn = false }, playerGui)

	-- ---------------------------------------------------------- HUD + toast
	local hud = new("TextLabel", {
		AnchorPoint = Vector2.new(0.5, 0),
		Position = UDim2.new(0.5, 0, 0, 8),
		Size = UDim2.fromOffset(520, 34),
		BackgroundColor3 = Color3.fromRGB(20, 22, 28),
		BackgroundTransparency = 0.2,
		TextColor3 = Color3.new(1, 1, 1),
		Font = Enum.Font.GothamMedium,
		TextSize = 16,
		Text = "Conectando...",
	}, gui)
	new("UICorner", { CornerRadius = UDim.new(0, 8) }, hud)

	local toastLabel = new("TextLabel", {
		AnchorPoint = Vector2.new(0.5, 0),
		Position = UDim2.new(0.5, 0, 0, 48),
		Size = UDim2.fromOffset(360, 30),
		BackgroundColor3 = Color3.fromRGB(150, 50, 50),
		TextColor3 = Color3.new(1, 1, 1),
		Font = Enum.Font.GothamMedium,
		TextSize = 15,
		Visible = false,
	}, gui)
	new("UICorner", { CornerRadius = UDim.new(0, 8) }, toastLabel)
	local toastToken = 0
	local function toast(text)
		toastToken += 1
		local mine = toastToken
		toastLabel.Text = text
		toastLabel.Visible = true
		task.delay(2.5, function()
			if toastToken == mine then
				toastLabel.Visible = false
			end
		end)
	end
	local function explain(res)
		if res and not res.Ok then
			toast(ERRORS[res.Error] or tostring(res.Error))
		end
	end
	Placement.OnResult = explain

	local function refreshHud()
		local s = Render.State
		if not s then
			return
		end
		local left = ""
		if s.EndsAt and s.EndsAt > 0 then
			left = (" | %ds"):format(math.max(0, math.ceil(s.EndsAt - workspace:GetServerTimeNow())))
		end
		local waveText = s.VictoryWave and s.VictoryWave > 0 and ("%d/%d"):format(s.Wave, s.VictoryWave) or tostring(s.Wave)
		hud.Text = ("%s | Onda %s | Vidas %d/%d | Moedas %d%s"):format(
			STATE_NAMES[s.State] or s.State,
			waveText,
			s.Lives,
			s.MaxLives,
			Render.Data.Coins or 0,
			left
		)
	end
	task.spawn(function()
		while gui.Parent do
			refreshHud()
			task.wait(0.25)
		end
	end)

	-- ---------------------------------------------------------- loja (equipadas) + inventário (todas)
	local template = ReplicatedStorage:WaitForChild(TEMPLATE_NAME)
	local mainUI = playerGui:WaitForChild("MainUI")
	local shopBackground = mainUI:WaitForChild("Units"):WaitForChild("Background") -- Frame Units: só as equipadas
	local invUnits = mainUI:WaitForChild("Inventory"):WaitForChild("Units") -- ScrollingFrame Units: todas

	if not shopBackground:FindFirstChildWhichIsA("UIListLayout") and not shopBackground:FindFirstChildWhichIsA("UIGridLayout") then
		new("UIListLayout", {
			FillDirection = Enum.FillDirection.Horizontal,
			Padding = UDim.new(0, 8),
			SortOrder = Enum.SortOrder.LayoutOrder,
		}, shopBackground)
	end

	local WHITE, RED, GREEN = Color3.new(1, 1, 1), Color3.fromRGB(255, 120, 120), Color3.fromRGB(120, 255, 140)
	local shopCards, invCards = {}, {}

	local function makeCard(def, parent, order)
		local button = template:Clone()
		button.Name = def.Id
		button.LayoutOrder = order
		button.Visible = true
		button.Parent = parent
		if button:IsA("ImageButton") and def.Icon and def.Icon ~= "" then
			button.Image = def.Icon
		end
		return button
	end

	local function refreshShop()
		local coins = Render.Data.Coins or 0
		for _, c in pairs(shopCards) do
			local cost = Render.TowerCost(c.Def)
			if c.Button:IsA("TextButton") then
				c.Button.Text = ("%s\n$%d"):format(c.Def.DisplayName or c.Def.Id, cost)
				c.Button.TextColor3 = coins >= cost and WHITE or RED
			end
		end
	end

	local function refreshInventory()
		for id, c in pairs(invCards) do
			local eq = table.find(Render.Loadout, id) ~= nil
			if c.Button:IsA("TextButton") then
				c.Button.Text = ("%s\n%s"):format(c.Def.DisplayName or id, eq and "[Equipado]" or "Equipar")
				c.Button.TextColor3 = eq and GREEN or WHITE
			end
		end
	end

	local function rebuildShop()
		for _, c in pairs(shopCards) do
			c.Button:Destroy()
		end
		table.clear(shopCards)
		local towers = Registry.Of("Towers")
		for i, id in ipairs(Render.Loadout) do
			local def = towers:Get(id)
			if def then
				local button = UnitCard.Make(def, shopBackground, i, Render) or makeCard(def, shopBackground, i)
				button.Activated:Connect(function()
					Placement.Toggle(id)
				end)
				shopCards[id] = { Button = button, Def = def }
			end
		end
		refreshShop()
	end

	-- inventário: um card por torre existente (torres novas em TowersConfig aparecem sozinhas)
	Registry.Of("Towers"):OnRegister(function(def)
		local button = makeCard(def, invUnits, def.Cost)
		button.Activated:Connect(function()
			explain(Net.Request():InvokeServer("ToggleEquip", { TowerId = def.Id }))
		end)
		invCards[def.Id] = { Button = button, Def = def }
		refreshInventory()
	end)

	Render.Events:Connect("Loadout", function(list)
		if Placement.Active and not table.find(list, Placement.Active) then
			Placement.Cancel()
		end
		rebuildShop()
		refreshInventory()
	end)
	Render.Events:Connect("PlayerData", refreshShop)
	Render.Events:Connect("GameState", refreshShop)
	rebuildShop()
	 [trimmed]  -  Editar
  18:17:54.307  [Roblox][Ribbon.Ribbon.Src.Hooks.useMenu] This plugin cannot create more than one PluginGui with id: "Menus/1"  -  Autônomo
  18:17:54.308  Stack Begin  -  Studio
  18:17:54.308  Script 'Ribbon.Ribbon.Src.Hooks.useMenu', Line 108 - function getMenu  -  Studio
  18:17:54.308  Script 'Ribbon.Ribbon.Src.Hooks.useMenu', Line 211 - function openMenu  -  Studio
  18:17:54.308  Script 'Ribbon.Ribbon.Src.Components.ControlsView', Line 86  -  Studio
  18:17:54.308  Script 'Ribbon.Ribbon.Src.Components.ControlsView.Renderers.SplitButtonControl', Line 137 - function OnSelectArrow  -  Studio
  18:17:54.308  Script 'Ribbon.Ribbon.Src.Components.SplitButton', Line 133  -  Studio
  18:17:54.308  Script 'Ribbon.Ribbon.Packages._Index.ReactRoblox.ReactRoblox.client.roblox.SingleEventManager', Line 112  -  Studio
  18:17:54.308  Stack End  -  Studio
  18:22:18.390  > -- ROBLOX PROJECT EXPORTER
-- Somente leitura: não modifica o projeto.

local MAX_CHARS_PER_PART = 12000

local lines = {}
local currentPart = {}
local currentSize = 0
local partNumber = 0

local function addLine(text)
	text = tostring(text)

	if currentSize + #text + 1 > MAX_CHARS_PER_PART and #currentPart > 0 then
		partNumber += 1

		print("")
		print("========== PROJECT EXPORT PART " .. partNumber .. " ==========")
		print(table.concat(currentPart, "\n"))
		print("========== END PART " .. partNumber .. " ==========")
		print("")

		currentPart = {}
		currentSize = 0
	end

	table.insert(currentPart, text)
	currentSize += #text + 1
end

local function getPath(instance)
	local path = instance.Name
	local parent = instance.Parent

	while parent and parent ~= game do
		path = parent.Name .. "." .. path
		parent = parent.Parent
	end

	return "game." .. path
end

local function scan(instance, depth)
	local prefix = string.rep("  ", depth)

	addLine(prefix .. "- " .. instance.Name .. " [" .. instance.ClassName .. "]")

	-- Scripts
	if instance:IsA("Script")
		or instance:IsA("LocalScript")
		or instance:IsA("ModuleScript") then

		addLine(prefix .. "  PATH: " .. getPath(instance))
		addLine(prefix .. "  SOURCE_START")

		local success, source = pcall(function()
			return instance.Source
		end)

		if success then
			for line in source:gmatch("[^\r\n]*") do
				addLine(prefix .. "    " .. line)
			end
		else
			addLine(prefix .. "    [SOURCE COULD NOT BE READ]")
		end

		addLine(prefix .. "  SOURCE_END")
	end

	-- RemoteEvents / RemoteFunctions
	if instance:IsA("RemoteEvent")
		or instance:IsA("RemoteFunction") then

		addLine(prefix .. "  REMOTE_PATH: " .. getPath(instance))
	end

	for _, child in ipairs(instance:GetChildren()) do
		scan(child, depth + 1)
	end
end

addLine("==================================================")
addLine("ROBLOX PROJECT EXPORT")
addLine("Generated: " .. os.date("%Y-%m-%d %H:%M:%S"))
addLine("==================================================")
addLine("")
addLine("This export contains the project hierarchy, scripts and remotes.")
addLine("")

scan(game, 0)

-- Finaliza última parte
if #currentPart > 0 then
	partNumber += 1

	print("")
	print("========== PROJECT EXPORT PART " .. partNumber .. " ==========")
	print(table.concat(currentPart, "\n"))
	print("========== END PART " .. partNumber .. " ==========")
	print("")
end

print("")
print("==========================================")
print("EXPORT COMPLETE")
print("TOTAL PARTS: " .. partNumber)
print("==========================================")  -  Studio
  18:22:18.425    -  Editar
  18:22:18.425  ========== PROJECT EXPORT PART 1 ==========  -  Editar
  18:22:18.425  ==================================================
ROBLOX PROJECT EXPORT
Generated: 2026-10-02 18:22:18
==================================================

This export contains the project hierarchy, scripts and remotes.

- Place1 [DataModel]
  - Workspace [Workspace]
    - SunRays [SunRaysEffect]
    - ColorCorrection [ColorCorrectionEffect]
    - Blur [BlurEffect]
    - Bloom [BloomEffect]
      - Atmosphere [Atmosphere]
      - ArcHandles [ArcHandles]
    - TowerDefenseMap [Folder]
      - Waypoints [Folder]
      - Path [Folder]
      - TowerSpots [Folder]
      - Decor [Folder]
    - Terrain [Terrain]
    - Camera [Camera]
  - Run Service [RunService]
  - GuiService [GuiService]
    - ScreenshotHud [ScreenshotHud]
  - Stats [Stats]
    - PerformanceStats [StatsItem]
      - Memory [StatsItem]
        - CoreMemory [StatsItem]
          - default [StatsItem]
          - staticinit [StatsItem]
          - http/batch [StatsItem]
          - lua/web-cache [StatsItem]
          - contentProvider/asyncDecryption [StatsItem]
          - internal/DataModelPatch [StatsItem]
          - render/prepare/physics [StatsItem]
          - physics/step [StatsItem]
          - physics/buffers [StatsItem]
          - physics/mechanism [StatsItem]
          - physics/assembly [StatsItem]
          - experienceStateCaptureService [StatsItem]
          - gui/TextLayout [StatsItem]
          - render/fonts [StatsItem]
          - gui/HarfBuzz [StatsItem]
          - gui/FreeType [StatsItem]
          - fontProvider/loading [StatsItem]
          - gui/FontData [StatsItem]
          - internal/localizationTable [StatsItem]
          - internal/localization [StatsItem]
          - ads/AdGui [StatsItem]
          - internal/MarketplaceService [StatsItem]
          - geometry/EditableMesh/Geometry [StatsItem]
          - geometry/EditableMesh/SpatialCache [StatsItem]
          - geometry/EditableMesh/GpuAssigned [StatsItem]
          - physics/bullet [StatsItem]
          - network/netAssetSerialized [StatsItem]
          - network/netAssetRegistries [StatsItem]
          - network/netAssetProxy [StatsItem]
          - AppCore/GuidRegistry [StatsItem]
          - instance/fullname [StatsItem]
          - internal/TaskScheduler [StatsItem]
          - profiler [StatsItem]
          - internal/RbxThread [StatsItem]
          - localstorage [StatsItem]
          - telemetry/analytics [StatsItem]
          - telemetry [StatsItem]
          - http/client [StatsItem]
          - http/curl [StatsItem]
          - http/requestcallback [StatsItem]
          - openssl [StatsItem]
          - http/wslay [StatsItem]
          - SQLite [StatsItem]
          - telemetry/fields_container [StatsItem]
          - telemetry/counter [StatsItem]
          - telemetry/event [StatsItem]
          - telemetry/stat [StatsItem]
          - telemetry/v2_try_cut_and_send [StatsItem]
          - gui/FreeTypeDT [StatsItem]
          - AssetProvider/total [StatsItem]
          - sound/default [StatsItem]
          - render/copy [StatsItem]
          - render/vertexlayout [StatsItem]
          - render/shader [StatsItem]
          - render/swapchain [StatsItem]
          - raknet/raknet [StatsItem]
          - raknet/startup [StatsItem]
          - raknet/recv-buffer [StatsItem]
          - raknet/buffered-commands [StatsItem]
          - raknet/packet-return [StatsItem]
          - raknet/tx-outgoing [StatsItem]
          - raknet/tx-datagram [StatsItem]
          - raknet/rx-ordered-heap [StatsItem]
          - raknet/rx-split-reassembly [StatsItem]
          - raknet/rx-output [StatsItem]
          - raknet/rx-handling [StatsItem]
          - raknet/datagram-history [StatsItem]
          - raknet/ack-nak [StatsItem]
          - RbxTransport/Io/sys [StatsItem]
          - RbxTransport/Io/libuv [StatsItem]
          - video/encoding/hardware [StatsItem]
          - video/default [StatsItem]
          - video/packet [StatsItem]
          - video/codec [StatsItem]
          - video/texture [StatsItem]
          - internal/PerformanceControl [StatsItem]
          - RbxTransport/RtcIo/Local [StatsItem]
          - RbxTransport/RtcIo/Remote/Rx [StatsItem]
          - RbxTransport/RtcIo/Remote/AcceptConnection [StatsItem]
          - RbxTransport/RtcIo/Remote/AcceptWtSession [StatsItem]
          - RbxTransport/RtcIo/Remote/AcceptH3 [StatsItem]
          - RbxTransport/RtcIo/Remote/NewAppConnection [StatsItem]
          - RbxTransport/RtcIo/Remote/Handshake [StatsItem]
          - RbxTransport/RtcIo/Remote/StreamAccepted [StatsItem]
          - RbxTransport/RtcIo/Remote/StreamClose [StatsItem]
          - RbxTransport/RtcIo/Remote/Ack [StatsItem]
          - RbxTransport/RtcIo/Remote/FlowControl [StatsItem]
          - RbxTransport/RtcIo/Remote/Loss [StatsItem]
          - RbxTransport/RtcIo/Remote/ConnClose [StatsItem]
          - RbxTransport/RtcIo/Remote/AppControl [StatsItem]
          - RbxTransport/RtcIo/Remote/AppFin [StatsItem]
          - RbxTransport/RtcIo/Remote/OpenUnreliableChannel [StatsItem]
          - physics/broadphase [StatsItem]
          - physics/midphase [StatsItem]
          - internal/ixp [StatsItem]
          - video/realtime_media [StatsItem]
          - video/capture_engine [StatsItem]
          - physics/aerodynamics/mesh [StatsItem]
          - physics/aerodynamics/integrator [StatsItem]
          - physics/aerodynamics/linearintegrator [StatsItem]
          - physics/aerodynamics/cpintegrator [StatsItem]
          - physics/aerodynamics/shinterpolator [StatsItem]
          - physics/aerodynamics/reducedmesh [StatsItem]
          - internal/ScriptContext [StatsItem]
          - lua/bytecode [StatsItem]
          - lua/codegen [StatsItem]
          - lua/codegenpages [StatsItem]
          - internal/RuntimeScriptService [StatsItem]
          - CoreScriptTelemetry [StatsItem]
          - physics/solver/buffers [StatsItem]
          - physics/solver/sleep [StatsItem]
          - physics/solver/ldl [StatsItem]
          - physics/solver/misc [StatsItem]
          - internal/DataModelGenericJob [StatsItem]
          - studio/undo [StatsItem]
          - internal/InstanceStitchingHandler [StatsItem]
          - CollectionService [StatsItem]
          - internal/ChatService [StatsItem]
          - internal/GlobalSettings [StatsItem]
          - render/terrain/heightmapImporter [StatsItem]
          - geometry/EditableImage [StatsItem]
          - collections/collection [StatsItem]
          - collections/watcher [StatsItem]
          - performanceStats [StatsItem]
          - collections/proximity [StatsItem]
          - internal/AuroraService/InputFrame [StatsItem]
          - internal/AuroraService/HashBuffer [StatsItem]
          - internal/AuroraService/Prediction [StatsItem]
          - internal/Workspace [StatsItem]
          - internal/RemoteFunction [StatsItem]
          - internal/LogService [StatsItem]
          - render/lightgrid [StatsItem]
          - render/system [StatsItem]
          - render/bindworkspace [StatsItem]
          - render/adorn [StatsItem]
          - render/perform/statistics [StatsItem]
          - render/prepare [StatsItem]
          - render/prepare/adorn [StatsItem]
          - render/perform [StatsItem]
          - render/perform/adorn [StatsItem]
          - render/glyphaatlas/ugc [StatsItem]
          - render/glyphatlas/core [StatsItem]
          - render/terrain/grass/async [StatsItem]
          - render/terrain/grass [StatsItem]
          - render/prepare/terrain/grass [StatsItem]
          - render/target [StatsItem]
          - render/target/pooled [StatsItem]
          - render/perform/zpre [StatsItem]
          - render/clouds [StatsItem]
          - render/ssao [StatsItem]
          - render/glow [StatsItem]
          - render/sunrays [StatsItem]
          - render/dof [StatsItem]
          - render/blur [StatsItem]
          - render/colorCorrection [StatsItem]
          - render/highlight [StatsItem]
          - render/RtPool [StatsItem]
          - render/mainRts [StatsItem]
          - render/ui [StatsItem]
          - render/shadowmap [StatsItem]
          - render/perform/shadowmap [StatsItem]
          - render/shadowmap/depthcache [StatsItem]
          - render/perform/materialMisc [StatsItem]
          - render/perform/materialGc [StatsItem]
          - render/material/failsafe [StatsItem]
          - render/perform/terrain [StatsItem]
          - render/prepare/terrain [StatsItem]
          - render/instanceglob [StatsItem]
          - render/gpu_geom_mgr [StatsItem]
          - dynamic/mesh [StatsItem]
          - dynamic/texture [StatsItem]
          - render/envmap [StatsItem]
          - render/material/misc [StatsItem]
          - render/prepare/tc [StatsItem]
          - render/prepare/sceneUpdater [StatsItem]
          - render/prepare/parts [StatsItem]
          - render/prepare/megaCluster [StatsItem]
          - render/prepare/attachments [StatsItem]
          - render/swocc [StatsItem]
          - render/perform/textureAtlasInsert [StatsItem]
          - render/meshManager/async [StatsItem]
          - textureRef [StatsItem]
          - render/texture/local [StatsItem]
          - render/texture/fallback [StatsItem]
          - render/texture/loading [StatsItem]
          - render/perform/textureGc [StatsItem]
          - render/prepare/textureManager [StatsItem]
          - render/perform/textureManager [StatsItem]
          - render/sky [StatsItem]
          - render/advsky [StatsItem]
          - render/perform/cullableScene [StatsItem]
          - render/prepare/motionBuffer [StatsItem]
          - render/geometryGenerator [StatsItem]
          - render/perform/scratchFB [StatsItem]
          - render/prepare/lightObject [StatsItem]
          - render/terrain/async/chunkGen [StatsItem]
          - render/perform/terrain/occlusionGen [StatsItem]
          - render/viewportFrames [StatsItem]
          - render/prepare/lightGridChunk [StatsItem]
          - render/perform/lightGrid [StatsItem]
          - render/fastCluster/prepareSkinning [StatsItem]
          - render/fastCluster/skinningReserve [StatsItem]
          - render/prepare/beamNode [StatsItem]
          - render/prepare/customEmitter [StatsItem]
          - render/pipeline [StatsItem]
          - render/pipeline/updates [StatsItem]
          - render/meshFetcherDecomp [StatsItem]
          - network/compresspacket [StatsItem]
          - network/decompresspacket [StatsItem]
          - network/ISR/Property [StatsItem]
          - network/groupManager [StatsItem]
          - network/ISR/Replicator [StatsItem]
          - network/setManager [StatsItem]
          - internal/CSGDictionary [StatsItem]
          - network/HeatmapQueryService [StatsItem]
          - internal/HttpRbxApiService [StatsItem]
          - internal/StarterPlayer [StatsItem]
          - datastore/cache [StatsItem]
          - animation/skeleton_watcher [StatsItem]
          - wrap/layeredDeformer [StatsItem]
          - internal/Humanoid [StatsItem]
          - temporaryCageMeshProvider/save [StatsItem]
          - wrap/hsr [StatsItem]
          - animation/skeleton [StatsItem]
          - wrap/deformMeshProvider [StatsItem]
          - gui/Uncategorized [StatsItem]
          - gui/UIQuadTree [StatsItem]
          - languageServices/async [StatsItem]
          - languageServices/generic [StatsItem]
          - languageServices/shadow [StatsItem]
          - network/streamingReplication [StatsItem]
          - network/streamJob [StatsItem]
          - network/replicationCoalescing [StatsItem]
          - network/deserializestep [StatsItem]
          - network/onreceive [StatsItem]
          - network/sharedQueue [StatsItem]
          - network/megaReplicationData [StatsItem]
          - network/modelCompleteness [StatsItem]
          - network/refPropTracking [StatsItem]
          - network/replicator [StatsItem]
          - internal/InputReplicator [StatsItem]
          - network/gcJob [StatsItem]  -  Editar
  18:22:18.425  ========== END PART 1 ==========  -  Editar
  18:22:18.425   ▶  (x2)  -  Editar
  18:22:18.428  ========== PROJECT EXPORT PART 2 ==========  -  Editar
  18:22:18.428            - network/instanceObjectManager [StatsItem]
          - network/server [StatsItem]
          - network/streamingSolver [StatsItem]
          - network/streamingObserver [StatsItem]
          - network/replicatedInstances [StatsItem]
          - network/deferredtrees [StatsItem]
          - network/newinstanceitem [StatsItem]
          - network/streamDataItem [StatsItem]
          - network/ISR [StatsItem]
          - network/ISR/Connection [StatsItem]
          - network/ISR/Prioritization [StatsItem]
          - network/touchReplication [StatsItem]
          - network/replicationDataCache [StatsItem]
          - network/replicationDataCachePendingList [StatsItem]
          - network/ISR/groupMan [StatsItem]
          - network/physicsSenderCache [StatsItem]
          - sound/voice [StatsItem]
          - voice/webrtc [StatsItem]
          - voice/operations [StatsItem]
          - voice/audio [StatsItem]
          - sound/async [StatsItem]
          - sound/acoustics [StatsItem]
          - AudioWiring [StatsItem]
          - instance/AttributesAndTags [StatsItem]
          - internal/BaseThreadPool [StatsItem]
          - AssetProvider/state [StatsItem]
          - AssetProvider/other [StatsItem]
          - render/vertexstreamer [StatsItem]
          - friendsCalling/bringUp [StatsItem]
        - PlaceMemory [StatsItem]
          - HttpCache [StatsItem]
          - Instances [StatsItem]
          - Signals [StatsItem]
          - LuaHeap [StatsItem]
          - Script [StatsItem]
          - PhysicsCollision [StatsItem]
          - BaseParts [StatsItem]
          - GraphicsSolidModels [StatsItem]
          - GraphicsHSR [StatsItem]
          - GraphicsMeshParts [StatsItem]
          - GraphicsParticles [StatsItem]
          - GraphicsParts [StatsItem]
          - GraphicsSpatialHash [StatsItem]
          - GraphicsTerrain [StatsItem]
          - GraphicsTexture [StatsItem]
          - GraphicsTextureCharacter [StatsItem]
          - Sounds [StatsItem]
          - TerrainVoxels [StatsItem]
          - TerrainPhysics [StatsItem]
          - Gui [StatsItem]
          - Animation [StatsItem]
          - Navigation [StatsItem]
          - GeometryCSG [StatsItem]
          - GraphicsSlimModels [StatsItem]
        - UntrackedMemory [StatsItem]
        - PlaceScriptMemory [StatsItem]
          - MemoryCategory_0 [StatsItem]
          - MemoryCategory_1 [StatsItem]
          - MemoryCategory_2 [StatsItem]
          - MemoryCategory_3 [StatsItem]
          - MemoryCategory_4 [StatsItem]
          - MemoryCategory_5 [StatsItem]
          - MemoryCategory_6 [StatsItem]
          - MemoryCategory_7 [StatsItem]
          - MemoryCategory_8 [StatsItem]
          - MemoryCategory_9 [StatsItem]
          - MemoryCategory_10 [StatsItem]
          - MemoryCategory_11 [StatsItem]
          - MemoryCategory_12 [StatsItem]
          - MemoryCategory_13 [StatsItem]
          - MemoryCategory_14 [StatsItem]
          - MemoryCategory_15 [StatsItem]
          - MemoryCategory_16 [StatsItem]
          - MemoryCategory_17 [StatsItem]
          - MemoryCategory_18 [StatsItem]
          - MemoryCategory_19 [StatsItem]
          - MemoryCategory_20 [StatsItem]
          - MemoryCategory_21 [StatsItem]
          - MemoryCategory_22 [StatsItem]
          - MemoryCategory_23 [StatsItem]
          - MemoryCategory_24 [StatsItem]
          - MemoryCategory_25 [StatsItem]
          - MemoryCategory_26 [StatsItem]
          - MemoryCategory_27 [StatsItem]
          - MemoryCategory_28 [StatsItem]
          - MemoryCategory_29 [StatsItem]
          - MemoryCategory_30 [StatsItem]
          - MemoryCategory_31 [StatsItem]
          - MemoryCategory_32 [StatsItem]
          - MemoryCategory_33 [StatsItem]
          - MemoryCategory_34 [StatsItem]
          - MemoryCategory_35 [StatsItem]
          - MemoryCategory_36 [StatsItem]
          - MemoryCategory_37 [StatsItem]
          - MemoryCategory_38 [StatsItem]
          - MemoryCategory_39 [StatsItem]
          - MemoryCategory_40 [StatsItem]
          - MemoryCategory_41 [StatsItem]
          - MemoryCategory_42 [StatsItem]
          - MemoryCategory_43 [StatsItem]
          - MemoryCategory_44 [StatsItem]
          - MemoryCategory_45 [StatsItem]
          - MemoryCategory_46 [StatsItem]
          - MemoryCategory_47 [StatsItem]
          - MemoryCategory_48 [StatsItem]
          - MemoryCategory_49 [StatsItem]
          - MemoryCategory_50 [StatsItem]
          - MemoryCategory_51 [StatsItem]
          - MemoryCategory_52 [StatsItem]
          - MemoryCategory_53 [StatsItem]
          - MemoryCategory_54 [StatsItem]
          - MemoryCategory_55 [StatsItem]
          - MemoryCategory_56 [StatsItem]
          - MemoryCategory_57 [StatsItem]
          - MemoryCategory_58 [StatsItem]
          - MemoryCategory_59 [StatsItem]
          - MemoryCategory_60 [StatsItem]
          - MemoryCategory_61 [StatsItem]
          - MemoryCategory_62 [StatsItem]
          - MemoryCategory_63 [StatsItem]
          - MemoryCategory_64 [StatsItem]
          - MemoryCategory_65 [StatsItem]
          - MemoryCategory_66 [StatsItem]
          - MemoryCategory_67 [StatsItem]
          - MemoryCategory_68 [StatsItem]
          - MemoryCategory_69 [StatsItem]
          - MemoryCategory_70 [StatsItem]
          - MemoryCategory_71 [StatsItem]
          - MemoryCategory_72 [StatsItem]
          - MemoryCategory_73 [StatsItem]
          - MemoryCategory_74 [StatsItem]
          - MemoryCategory_75 [StatsItem]
          - MemoryCategory_76 [StatsItem]
          - MemoryCategory_77 [StatsItem]
          - MemoryCategory_78 [StatsItem]
          - MemoryCategory_79 [StatsItem]
          - MemoryCategory_80 [StatsItem]
          - MemoryCategory_81 [StatsItem]
          - MemoryCategory_82 [StatsItem]
          - MemoryCategory_83 [StatsItem]
          - MemoryCategory_84 [StatsItem]
          - MemoryCategory_85 [StatsItem]
          - MemoryCategory_86 [StatsItem]
          - MemoryCategory_87 [StatsItem]
          - MemoryCategory_88 [StatsItem]
          - MemoryCategory_89 [StatsItem]
          - MemoryCategory_90 [StatsItem]
          - MemoryCategory_91 [StatsItem]
          - MemoryCategory_92 [StatsItem]
          - MemoryCategory_93 [StatsItem]
          - MemoryCategory_94 [StatsItem]
          - MemoryCategory_95 [StatsItem]
          - MemoryCategory_96 [StatsItem]
          - MemoryCategory_97 [StatsItem]
          - MemoryCategory_98 [StatsItem]
          - MemoryCategory_99 [StatsItem]
          - MemoryCategory_100 [StatsItem]
          - MemoryCategory_101 [StatsItem]
          - MemoryCategory_102 [StatsItem]
          - MemoryCategory_103 [StatsItem]
          - MemoryCategory_104 [StatsItem]
          - MemoryCategory_105 [StatsItem]
          - MemoryCategory_106 [StatsItem]
          - MemoryCategory_107 [StatsItem]
          - MemoryCategory_108 [StatsItem]
          - MemoryCategory_109 [StatsItem]
          - MemoryCategory_110 [StatsItem]
          - MemoryCategory_111 [StatsItem]
          - MemoryCategory_112 [StatsItem]
          - MemoryCategory_113 [StatsItem]
          - MemoryCategory_114 [StatsItem]
          - MemoryCategory_115 [StatsItem]
          - MemoryCategory_116 [StatsItem]
          - MemoryCategory_117 [StatsItem]
          - MemoryCategory_118 [StatsItem]
          - MemoryCategory_119 [StatsItem]
          - MemoryCategory_120 [StatsItem]
          - MemoryCategory_121 [StatsItem]
          - MemoryCategory_122 [StatsItem]
          - MemoryCategory_123 [StatsItem]
          - MemoryCategory_124 [StatsItem]
          - MemoryCategory_125 [StatsItem]
          - MemoryCategory_126 [StatsItem]
          - MemoryCategory_127 [StatsItem]
          - MemoryCategory_128 [StatsItem]
          - MemoryCategory_129 [StatsItem]
          - MemoryCategory_130 [StatsItem]
          - MemoryCategory_131 [StatsItem]
          - MemoryCategory_132 [StatsItem]
          - MemoryCategory_133 [StatsItem]
          - MemoryCategory_134 [StatsItem]
          - MemoryCategory_135 [StatsItem]
          - MemoryCategory_136 [StatsItem]
          - MemoryCategory_137 [StatsItem]
          - MemoryCategory_138 [StatsItem]
          - MemoryCategory_139 [StatsItem]
          - MemoryCategory_140 [StatsItem]
          - MemoryCategory_141 [StatsItem]
          - MemoryCategory_142 [StatsItem]
          - MemoryCategory_143 [StatsItem]
          - MemoryCategory_144 [StatsItem]
          - MemoryCategory_145 [StatsItem]
          - MemoryCategory_146 [StatsItem]
          - MemoryCategory_147 [StatsItem]
          - MemoryCategory_148 [StatsItem]
          - MemoryCategory_149 [StatsItem]
          - MemoryCategory_150 [StatsItem]
          - MemoryCategory_151 [StatsItem]
          - MemoryCategory_152 [StatsItem]
          - MemoryCategory_153 [StatsItem]
          - MemoryCategory_154 [StatsItem]
          - MemoryCategory_155 [StatsItem]
          - MemoryCategory_156 [StatsItem]
          - MemoryCategory_157 [StatsItem]
          - MemoryCategory_158 [StatsItem]
          - MemoryCategory_159 [StatsItem]
          - MemoryCategory_160 [StatsItem]
          - MemoryCategory_161 [StatsItem]
          - MemoryCategory_162 [StatsItem]
          - MemoryCategory_163 [StatsItem]
          - MemoryCategory_164 [StatsItem]
          - MemoryCategory_165 [StatsItem]
          - MemoryCategory_166 [StatsItem]
          - MemoryCategory_167 [StatsItem]
          - MemoryCategory_168 [StatsItem]
          - MemoryCategory_169 [StatsItem]
          - MemoryCategory_170 [StatsItem]
          - MemoryCategory_171 [StatsItem]
          - MemoryCategory_172 [StatsItem]
          - MemoryCategory_173 [StatsItem]
          - MemoryCategory_174 [StatsItem]
          - MemoryCategory_175 [StatsItem]
          - MemoryCategory_176 [StatsItem]
          - MemoryCategory_177 [StatsItem]
          - MemoryCategory_178 [StatsItem]
          - MemoryCategory_179 [StatsItem]
          - MemoryCategory_180 [StatsItem]
          - MemoryCategory_181 [StatsItem]
          - MemoryCategory_182 [StatsItem]
          - MemoryCategory_183 [StatsItem]
          - MemoryCategory_184 [StatsItem]
          - MemoryCategory_185 [StatsItem]
          - MemoryCategory_186 [StatsItem]
          - MemoryCategory_187 [StatsItem]
          - MemoryCategory_188 [StatsItem]
          - MemoryCategory_189 [StatsItem]
          - MemoryCategory_190 [StatsItem]
          - MemoryCategory_191 [StatsItem]
          - MemoryCategory_192 [StatsItem]
          - MemoryCategory_193 [StatsItem]
          - MemoryCategory_194 [StatsItem]
          - MemoryCategory_195 [StatsItem]
          - MemoryCategory_196 [StatsItem]
          - MemoryCategory_197 [StatsItem]
          - MemoryCategory_198 [StatsItem]
          - MemoryCategory_199 [StatsItem]
          - MemoryCategory_200 [StatsItem]
          - MemoryCategory_201 [StatsItem]
          - MemoryCategory_202 [StatsItem]
          - MemoryCategory_203 [StatsItem]
          - MemoryCategory_204 [StatsItem]
          - MemoryCategory_205 [StatsItem]
          - MemoryCategory_206 [StatsItem]
          - MemoryCategory_207 [StatsItem]
          - MemoryCategory_208 [StatsItem]
          - MemoryCategory_209 [StatsItem]
          - MemoryCategory_210 [StatsItem]
          - MemoryCategory_211 [StatsItem]
          - MemoryCategory_212 [StatsItem]
          - MemoryCategory_213 [StatsItem]
          - MemoryCategory_214 [StatsItem]
          - MemoryCategory_215 [StatsItem]
          - MemoryCategory_216 [StatsItem]
          - MemoryCategory_217 [StatsItem]
          - MemoryCategory_218 [StatsItem]
          - MemoryCategory_219 [StatsItem]
          - MemoryCategory_220 [StatsItem]
          - MemoryCategory_221 [StatsItem]
          - MemoryCategory_222 [StatsItem]
          - MemoryCategory_223 [StatsItem]
          - MemoryCategory_224 [StatsItem]
          - MemoryCategory_225 [StatsItem]
          - MemoryCategory_226 [StatsItem]  -  Editar
  18:22:18.428  ========== END PART 2 ==========  -  Editar
  18:22:18.428   ▶  (x2)  -  Editar
  18:22:18.432  ========== PROJECT EXPORT PART 3 ==========  -  Editar
  18:22:18.433            - MemoryCategory_227 [StatsItem]
          - MemoryCategory_228 [StatsItem]
          - MemoryCategory_229 [StatsItem]
          - MemoryCategory_230 [StatsItem]
          - MemoryCategory_231 [StatsItem]
          - MemoryCategory_232 [StatsItem]
          - MemoryCategory_233 [StatsItem]
          - MemoryCategory_234 [StatsItem]
          - MemoryCategory_235 [StatsItem]
          - MemoryCategory_236 [StatsItem]
          - MemoryCategory_237 [StatsItem]
          - MemoryCategory_238 [StatsItem]
          - MemoryCategory_239 [StatsItem]
          - MemoryCategory_240 [StatsItem]
          - MemoryCategory_241 [StatsItem]
          - MemoryCategory_242 [StatsItem]
          - MemoryCategory_243 [StatsItem]
          - MemoryCategory_244 [StatsItem]
          - MemoryCategory_245 [StatsItem]
          - MemoryCategory_246 [StatsItem]
          - MemoryCategory_247 [StatsItem]
          - MemoryCategory_248 [StatsItem]
          - MemoryCategory_249 [StatsItem]
          - MemoryCategory_250 [StatsItem]
          - MemoryCategory_251 [StatsItem]
          - MemoryCategory_252 [StatsItem]
          - MemoryCategory_253 [StatsItem]
          - MemoryCategory_254 [StatsItem]
          - MemoryCategory_255 [StatsItem]
        - CoreScriptMemory [StatsItem]
          - MemoryCategory_0 [StatsItem]
          - MemoryCategory_1 [StatsItem]
          - MemoryCategory_2 [StatsItem]
          - MemoryCategory_3 [StatsItem]
          - MemoryCategory_4 [StatsItem]
          - MemoryCategory_5 [StatsItem]
          - MemoryCategory_6 [StatsItem]
          - MemoryCategory_7 [StatsItem]
          - MemoryCategory_8 [StatsItem]
          - MemoryCategory_9 [StatsItem]
          - MemoryCategory_10 [StatsItem]
          - MemoryCategory_11 [StatsItem]
          - MemoryCategory_12 [StatsItem]
          - MemoryCategory_13 [StatsItem]
          - MemoryCategory_14 [StatsItem]
          - MemoryCategory_15 [StatsItem]
          - MemoryCategory_16 [StatsItem]
          - MemoryCategory_17 [StatsItem]
          - MemoryCategory_18 [StatsItem]
          - MemoryCategory_19 [StatsItem]
          - MemoryCategory_20 [StatsItem]
          - MemoryCategory_21 [StatsItem]
          - MemoryCategory_22 [StatsItem]
          - MemoryCategory_23 [StatsItem]
          - MemoryCategory_24 [StatsItem]
          - MemoryCategory_25 [StatsItem]
          - MemoryCategory_26 [StatsItem]
          - MemoryCategory_27 [StatsItem]
          - MemoryCategory_28 [StatsItem]
          - MemoryCategory_29 [StatsItem]
          - MemoryCategory_30 [StatsItem]
          - MemoryCategory_31 [StatsItem]
          - MemoryCategory_32 [StatsItem]
          - MemoryCategory_33 [StatsItem]
          - MemoryCategory_34 [StatsItem]
          - MemoryCategory_35 [StatsItem]
          - MemoryCategory_36 [StatsItem]
          - MemoryCategory_37 [StatsItem]
          - MemoryCategory_38 [StatsItem]
          - MemoryCategory_39 [StatsItem]
          - MemoryCategory_40 [StatsItem]
          - MemoryCategory_41 [StatsItem]
          - MemoryCategory_42 [StatsItem]
          - MemoryCategory_43 [StatsItem]
          - MemoryCategory_44 [StatsItem]
          - MemoryCategory_45 [StatsItem]
          - MemoryCategory_46 [StatsItem]
          - MemoryCategory_47 [StatsItem]
          - MemoryCategory_48 [StatsItem]
          - MemoryCategory_49 [StatsItem]
          - MemoryCategory_50 [StatsItem]
          - MemoryCategory_51 [StatsItem]
          - MemoryCategory_52 [StatsItem]
          - MemoryCategory_53 [StatsItem]
          - MemoryCategory_54 [StatsItem]
          - MemoryCategory_55 [StatsItem]
          - MemoryCategory_56 [StatsItem]
          - MemoryCategory_57 [StatsItem]
          - MemoryCategory_58 [StatsItem]
          - MemoryCategory_59 [StatsItem]
          - MemoryCategory_60 [StatsItem]
          - MemoryCategory_61 [StatsItem]
          - MemoryCategory_62 [StatsItem]
          - MemoryCategory_63 [StatsItem]
          - MemoryCategory_64 [StatsItem]
          - MemoryCategory_65 [StatsItem]
          - MemoryCategory_66 [StatsItem]
          - MemoryCategory_67 [StatsItem]
          - MemoryCategory_68 [StatsItem]
          - MemoryCategory_69 [StatsItem]
          - MemoryCategory_70 [StatsItem]
          - MemoryCategory_71 [StatsItem]
          - MemoryCategory_72 [StatsItem]
          - MemoryCategory_73 [StatsItem]
          - MemoryCategory_74 [StatsItem]
          - MemoryCategory_75 [StatsItem]
          - MemoryCategory_76 [StatsItem]
          - MemoryCategory_77 [StatsItem]
          - MemoryCategory_78 [StatsItem]
          - MemoryCategory_79 [StatsItem]
          - MemoryCategory_80 [StatsItem]
          - MemoryCategory_81 [StatsItem]
          - MemoryCategory_82 [StatsItem]
          - MemoryCategory_83 [StatsItem]
          - MemoryCategory_84 [StatsItem]
          - MemoryCategory_85 [StatsItem]
          - MemoryCategory_86 [StatsItem]
          - MemoryCategory_87 [StatsItem]
          - MemoryCategory_88 [StatsItem]
          - MemoryCategory_89 [StatsItem]
          - MemoryCategory_90 [StatsItem]
          - MemoryCategory_91 [StatsItem]
          - MemoryCategory_92 [StatsItem]
          - MemoryCategory_93 [StatsItem]
          - MemoryCategory_94 [StatsItem]
          - MemoryCategory_95 [StatsItem]
          - MemoryCategory_96 [StatsItem]
          - MemoryCategory_97 [StatsItem]
          - MemoryCategory_98 [StatsItem]
          - MemoryCategory_99 [StatsItem]
          - MemoryCategory_100 [StatsItem]
          - MemoryCategory_101 [StatsItem]
          - MemoryCategory_102 [StatsItem]
          - MemoryCategory_103 [StatsItem]
          - MemoryCategory_104 [StatsItem]
          - MemoryCategory_105 [StatsItem]
          - MemoryCategory_106 [StatsItem]
          - MemoryCategory_107 [StatsItem]
          - MemoryCategory_108 [StatsItem]
          - MemoryCategory_109 [StatsItem]
          - MemoryCategory_110 [StatsItem]
          - MemoryCategory_111 [StatsItem]
          - MemoryCategory_112 [StatsItem]
          - MemoryCategory_113 [StatsItem]
          - MemoryCategory_114 [StatsItem]
          - MemoryCategory_115 [StatsItem]
          - MemoryCategory_116 [StatsItem]
          - MemoryCategory_117 [StatsItem]
          - MemoryCategory_118 [StatsItem]
          - MemoryCategory_119 [StatsItem]
          - MemoryCategory_120 [StatsItem]
          - MemoryCategory_121 [StatsItem]
          - MemoryCategory_122 [StatsItem]
          - MemoryCategory_123 [StatsItem]
          - MemoryCategory_124 [StatsItem]
          - MemoryCategory_125 [StatsItem]
          - MemoryCategory_126 [StatsItem]
          - MemoryCategory_127 [StatsItem]
          - MemoryCategory_128 [StatsItem]
          - MemoryCategory_129 [StatsItem]
          - MemoryCategory_130 [StatsItem]
          - MemoryCategory_131 [StatsItem]
          - MemoryCategory_132 [StatsItem]
          - MemoryCategory_133 [StatsItem]
          - MemoryCategory_134 [StatsItem]
          - MemoryCategory_135 [StatsItem]
          - MemoryCategory_136 [StatsItem]
          - MemoryCategory_137 [StatsItem]
          - MemoryCategory_138 [StatsItem]
          - MemoryCategory_139 [StatsItem]
          - MemoryCategory_140 [StatsItem]
          - MemoryCategory_141 [StatsItem]
          - MemoryCategory_142 [StatsItem]
          - MemoryCategory_143 [StatsItem]
          - MemoryCategory_144 [StatsItem]
          - MemoryCategory_145 [StatsItem]
          - MemoryCategory_146 [StatsItem]
          - MemoryCategory_147 [StatsItem]
          - MemoryCategory_148 [StatsItem]
          - MemoryCategory_149 [StatsItem]
          - MemoryCategory_150 [StatsItem]
          - MemoryCategory_151 [StatsItem]
          - MemoryCategory_152 [StatsItem]
          - MemoryCategory_153 [StatsItem]
          - MemoryCategory_154 [StatsItem]
          - MemoryCategory_155 [StatsItem]
          - MemoryCategory_156 [StatsItem]
          - MemoryCategory_157 [StatsItem]
          - MemoryCategory_158 [StatsItem]
          - MemoryCategory_159 [StatsItem]
          - MemoryCategory_160 [StatsItem]
          - MemoryCategory_161 [StatsItem]
          - MemoryCategory_162 [StatsItem]
          - MemoryCategory_163 [StatsItem]
          - MemoryCategory_164 [StatsItem]
          - MemoryCategory_165 [StatsItem]
          - MemoryCategory_166 [StatsItem]
          - MemoryCategory_167 [StatsItem]
          - MemoryCategory_168 [StatsItem]
          - MemoryCategory_169 [StatsItem]
          - MemoryCategory_170 [StatsItem]
          - MemoryCategory_171 [StatsItem]
          - MemoryCategory_172 [StatsItem]
          - MemoryCategory_173 [StatsItem]
          - MemoryCategory_174 [StatsItem]
          - MemoryCategory_175 [StatsItem]
          - MemoryCategory_176 [StatsItem]
          - MemoryCategory_177 [StatsItem]
          - MemoryCategory_178 [StatsItem]
          - MemoryCategory_179 [StatsItem]
          - MemoryCategory_180 [StatsItem]
          - MemoryCategory_181 [StatsItem]
          - MemoryCategory_182 [StatsItem]
          - MemoryCategory_183 [StatsItem]
          - MemoryCategory_184 [StatsItem]
          - MemoryCategory_185 [StatsItem]
          - MemoryCategory_186 [StatsItem]
          - MemoryCategory_187 [StatsItem]
          - MemoryCategory_188 [StatsItem]
          - MemoryCategory_189 [StatsItem]
          - MemoryCategory_190 [StatsItem]
          - MemoryCategory_191 [StatsItem]
          - MemoryCategory_192 [StatsItem]
          - MemoryCategory_193 [StatsItem]
          - MemoryCategory_194 [StatsItem]
          - MemoryCategory_195 [StatsItem]
          - MemoryCategory_196 [StatsItem]
          - MemoryCategory_197 [StatsItem]
          - MemoryCategory_198 [StatsItem]
          - MemoryCategory_199 [StatsItem]
          - MemoryCategory_200 [StatsItem]
          - MemoryCategory_201 [StatsItem]
          - MemoryCategory_202 [StatsItem]
          - MemoryCategory_203 [StatsItem]
          - MemoryCategory_204 [StatsItem]
          - MemoryCategory_205 [StatsItem]
          - MemoryCategory_206 [StatsItem]
          - MemoryCategory_207 [StatsItem]
          - MemoryCategory_208 [StatsItem]
          - MemoryCategory_209 [StatsItem]
          - MemoryCategory_210 [StatsItem]
          - MemoryCategory_211 [StatsItem]
          - MemoryCategory_212 [StatsItem]
          - MemoryCategory_213 [StatsItem]
          - MemoryCategory_214 [StatsItem]
          - MemoryCategory_215 [StatsItem]
          - MemoryCategory_216 [StatsItem]
          - MemoryCategory_217 [StatsItem]
          - MemoryCategory_218 [StatsItem]
          - MemoryCategory_219 [StatsItem]
          - MemoryCategory_220 [StatsItem]
          - MemoryCategory_221 [StatsItem]
          - MemoryCategory_222 [StatsItem]
          - MemoryCategory_223 [StatsItem]
          - MemoryCategory_224 [StatsItem]
          - MemoryCategory_225 [StatsItem]
          - MemoryCategory_226 [StatsItem]
          - MemoryCategory_227 [StatsItem]
          - MemoryCategory_228 [StatsItem]
          - MemoryCategory_229 [StatsItem]
          - MemoryCategory_230 [StatsItem]
          - MemoryCategory_231 [StatsItem]
          - MemoryCategory_232 [StatsItem]
          - MemoryCategory_233 [StatsItem]
          - MemoryCategory_234 [StatsItem]
          - MemoryCategory_235 [StatsItem]
          - MemoryCategory_236 [StatsItem]
          - MemoryCategory_237 [StatsItem]
          - MemoryCategory_238 [StatsItem]
          - MemoryCategory_239 [StatsItem]
          - MemoryCategory_240 [StatsItem]
          - MemoryCategory_241 [StatsItem]
          - MemoryCategory_242 [StatsItem]
          - MemoryCategory_243 [StatsItem]
          - MemoryCategory_244 [StatsItem]
          - MemoryCategory_245 [StatsItem]
          - MemoryCategory_246 [StatsItem]
          - MemoryCategory_247 [StatsItem]
          - MemoryCategory_248 [StatsItem]
          - MemoryCategory_249 [StatsItem]
          - MemoryCategory_250 [StatsItem]  -  Editar
  18:22:18.433  ========== END PART 3 ==========  -  Editar
  18:22:18.433   ▶  (x2)  -  Editar
  18:22:18.434  ========== PROJECT EXPORT PART 4 ==========  -  Editar
  18:22:18.435            - MemoryCategory_251 [StatsItem]
          - MemoryCategory_252 [StatsItem]
          - MemoryCategory_253 [StatsItem]
          - MemoryCategory_254 [StatsItem]
          - MemoryCategory_255 [StatsItem]
      - MaxMemory [StatsItem]
      - CPU [StatsItem]
      - MaxCPU [StatsItem]
      - GPU [StatsItem]
      - MaxGPU [StatsItem]
      - Ping [StatsItem]
      - MaxPing [StatsItem]
      - NetworkReceived [StatsItem]
      - MaxNetworkReceived [StatsItem]
      - NetworkSent [StatsItem]
      - MaxNetworkSent [StatsItem]
    - RenderBreakdown [StatsItem]
      - Undefined [StatsItem]
      - Opaque [StatsItem]
      - Transparent [StatsItem]
      - Terrain [StatsItem]
      - Grass [StatsItem]
      - UI [StatsItem]
      - Decal [StatsItem]
      - Cloud [StatsItem]
      - GenericPostProcess [StatsItem]
      - SSAO [StatsItem]
      - DOF [StatsItem]
      - Particles [StatsItem]
      - Sky [StatsItem]
    - Workspace [StatsItem]
      - FPS [StatsItem]
      - Heartbeat [StatsItem]
      - Environment Speed % [StatsItem]
      - World [StatsItem]
        - Primitives [StatsItem]
        - Joints [StatsItem]
        - Contacts [StatsItem]
        - Non-Anchored Assemblies [StatsItem]
        - Sleeping Assemblies [StatsItem]
        - Sleep Checking Assemblies [StatsItem]
        - Awake Assemblies [StatsItem]
      - Contacts [StatsItem]
        - CtctStageCtcts [StatsItem]
        - SteppingCtcts [StatsItem]
      - Kernel [StatsItem]
        - Constraints [StatsItem]
      - File Operations [StatsItem]
        - Total Load Time [StatsItem]
        - SyncHttpGet Time [StatsItem]
        - XML Load Time [StatsItem]
        - Join All Time [StatsItem]
    - Sound [StatsItem]
      - CPU [StatsItem]
        - Dsp [StatsItem]
        - Stream [StatsItem]
        - Geometry [StatsItem]
        - Update [StatsItem]
      - ChannelsPlaying [StatsItem]
      - Current [StatsItem]
      - Max [StatsItem]
      - # Sounds [StatsItem]
      - # Unused [StatsItem]
    - ChangeHistory [StatsItem]
      - Data Size [StatsItem]
      - Constrained Data Size [StatsItem]
      - Stack Size [StatsItem]
    - Network [StatsItem]
      - Packets Thread [StatsItem]
        - Rate [StatsItem]
        - Activity [StatsItem]
        - Physics Senders [StatsItem]
        - Send Buffer Health [StatsItem]
      - ServerStatsItem [StatsItem]
        - Network Ping [StatsItem]
        - Data Ping [RunningAverageItemInt]
        - StreamingEnabled [StatsItem]
        - Compression [StatsItem]
        - Stats [StatsItem]
          - messageDataBytesSentPerSec [StatsItem]
          - messageTotalBytesSentPerSec [StatsItem]
          - messageDataBytesResentPerSec [StatsItem]
          - messagesBytesReceivedPerSec [StatsItem]
          - messagesBytesReceivedAndIgnoredPerSec [StatsItem]
          - bytesSentPerSec [StatsItem]
          - bytesReceivedPerSec [StatsItem]
          - totalMessageBytesPushed [StatsItem]
          - totalMessageBytesSent [StatsItem]
          - totalMessageBytesResent [StatsItem]
          - totalMessagesBytesReceived [StatsItem]
          - totalMessagesBytesReceivedAndIgnored [StatsItem]
          - totalBytesSent [StatsItem]
          - totalBytesReceived [StatsItem]
          - connectionStartTime [StatsItem]
          - outgoingBandwidthLimitBytesPerSecond [StatsItem]
          - isLimitedByOutgoingBandwidthLimit [StatsItem]
          - congestionControlLimitBytesPerSecond [StatsItem]
          - isLimitedByCongestionControl [StatsItem]
          - messageSendBuffer [StatsItem]
            - IMMEDIATE_PRIORITY [StatsItem]
            - HIGH_PRIORITY [StatsItem]
            - MEDIUM_PRIORITY [StatsItem]
            - LOW_PRIORITY [StatsItem]
          - bytesInSendBuffer [StatsItem]
            - IMMEDIATE_PRIORITY [StatsItem]
            - HIGH_PRIORITY [StatsItem]
            - MEDIUM_PRIORITY [StatsItem]
            - LOW_PRIORITY [StatsItem]
          - messagesInResendQueue [StatsItem]
          - bytesInResendQueue [StatsItem]
          - packetlossLastSecond [StatsItem]
          - packetlossTotal [StatsItem]
          - numberOfUnsplitMessages [StatsItem]
          - numberOfSplitMessages [StatsItem]
          - messageDataBytesSentPerSec [StatsItem]
          - messageTotalBytesSentPerSec [StatsItem]
          - messageDataBytesResentPerSec [StatsItem]
          - messagesBytesReceivedPerSec [StatsItem]
          - messagesBytesReceivedAndIgnoredPerSec [StatsItem]
          - bytesSentPerSec [StatsItem]
          - bytesReceivedPerSec [StatsItem]
          - totalMessageBytesPushed [StatsItem]
          - totalMessageBytesSent [StatsItem]
          - totalMessageBytesResent [StatsItem]
          - totalMessagesBytesReceived [StatsItem]
          - totalMessagesBytesReceivedAndIgnored [StatsItem]
          - totalBytesSent [StatsItem]
          - totalBytesReceived [StatsItem]
          - connectionStartTime [StatsItem]
          - outgoingBandwidthLimitBytesPerSecond [StatsItem]
          - isLimitedByOutgoingBandwidthLimit [StatsItem]
          - congestionControlLimitBytesPerSecond [StatsItem]
          - isLimitedByCongestionControl [StatsItem]
          - messageSendBuffer [StatsItem]
            - IMMEDIATE_PRIORITY [StatsItem]
            - HIGH_PRIORITY [StatsItem]
            - MEDIUM_PRIORITY [StatsItem]
            - LOW_PRIORITY [StatsItem]
          - bytesInSendBuffer [StatsItem]
            - IMMEDIATE_PRIORITY [StatsItem]
            - HIGH_PRIORITY [StatsItem]
            - MEDIUM_PRIORITY [StatsItem]
            - LOW_PRIORITY [StatsItem]
          - messagesInResendQueue [StatsItem]
          - bytesInResendQueue [StatsItem]
          - packetlossLastSecond [StatsItem]
          - packetlossTotal [StatsItem]
          - numberOfUnsplitMessages [StatsItem]
          - numberOfSplitMessages [StatsItem]
        - Send kBps [StatsItem]
          - MtuSize [StatsItem]
        - Send Buffer Health [StatsItem]
        - BandwidthExceeded [StatsItem]
        - CongestionControlExceeded [StatsItem]
        - Receive kBps [StatsItem]
        - Packet Queue [StatsItem]
        - Sent Data Packets [StatsItem]
          - Size [RunningAverageItemInt]
          - Throttle [StatsItem]
          - Queue Size [StatsItem]
          - Time In Queue [StatsItem]
          - New Items Per Sec [TotalCountTimeIntervalItem]
          - Items Sent Per Sec [TotalCountTimeIntervalItem]
        - OutPhysicsDetails [StatsItem]
          - CFrameOnly [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Mechanism [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Translation [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Rotation [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Velocity [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
        - InPhysicsDetails [StatsItem]
          - CFrameOnly [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Mechanism [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Translation [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Rotation [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Velocity [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
        - DataPingDetails [StatsItem]
          - LQToS [StatsItem]
          - LBcsQ [StatsItem]
          - RakPing [StatsItem]
          - RRakRecvToAppPop [StatsItem]
          - RAppPopToDeserialize [StatsItem]
          - RDeserializeToPBQ [StatsItem]
          - RQToS [StatsItem]
          - RBscQ [StatsItem]
          - LRakRecvToAppPop [StatsItem]
          - LAppPopToSerialize [StatsItem]
          - LDeserializeToProcess [StatsItem]
          - EstTotal [StatsItem]
          - MeasuredTotal [StatsItem]
          - unrelLQToS [StatsItem]
          - unrelLBcsQ [StatsItem]
          - unrelRakPing [StatsItem]
          - unrelRRakRecvToAppPop [StatsItem]
          - unrelRAppPopToDeserialize [StatsItem]
          - unrelRDeserializeToPBQ [StatsItem]
          - unrelRQToS [StatsItem]
          - unrelRBscQ [StatsItem]
          - unrelLRakRecvToAppPop [StatsItem]
          - unrelLAppPopToSerialize [StatsItem]
          - unrelLDeserializeToProcess [StatsItem]
          - unrelEstTotal [StatsItem]
          - unrelMeasuredTotal [StatsItem]
        - Send Data Types [StatsItem]
          - InstanceNew [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - InstanceDelete [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Ping [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Data [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Behavior [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - State [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Appearance [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Team [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Video [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Control [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Events [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - InstanceDestroy [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
        - Received Data Types [StatsItem]
          - InstanceNew [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - InstanceDelete [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Ping [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Data [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Behavior [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - State [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Appearance [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Team [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Video [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Control [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - Events [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
          - InstanceDestroy [TotalCountTimeIntervalItem]
            - Size [RunningAverageItemInt]
        - Sent Physics Packets [StatsItem]
          - Size [RunningAverageItemInt]
          - Throttle [StatsItem]
          - Smoothed [StatsItem]
          - Items Per Packet [RunningAverageItemInt]
        - SentTouchPackets [StatsItem]
          - Size [RunningAverageItemInt]
          - WaitingTouches [RunningAverageItemInt]
        - Received Packets [StatsItem]
        - Received Data Packets [StatsItem]
          - Queue Size [StatsItem]
          - Instance Size [StatsItem]
          - Waiting Refs [StatsItem]
          - Size [StatsItem]
        - Received ISR Packets [StatsItem]
          - Size [StatsItem]
        - Received LR Packets [StatsItem]
          - Size [StatsItem]
        - Received Physics Packets [StatsItem]
          - Average Lag [StatsItem]
          - Average Buffer Seek [StatsItem]
          - Max Buffer Seek [StatsItem]
          - Wrong Order [StatsItem]
          - Size [StatsItem]
        - Sent ISR Packets [StatsItem]
          - Size [StatsItem]
        - In ISR Physics Details [StatsItem]
          - Mechanism [StatsItem]
            - Size [StatsItem]
          - CFrameOnly [StatsItem]
            - Size [StatsItem]  -  Editar
  18:22:18.435  ========== END PART 4 ==========  -  Editar
  18:22:18.435   ▶  (x2)  -  Editar
  18:22:18.436  ========== PROJECT EXPORT PART 5 ==========  -  Editar
  18:22:18.436            - Translation [StatsItem]
            - Size [StatsItem]
          - Rotation [StatsItem]
            - Size [StatsItem]
          - Velocity [StatsItem]
            - Size [StatsItem]
        - Out ISR Physics Details [StatsItem]
          - Mechanism [StatsItem]
            - Size [StatsItem]
          - CFrameOnly [StatsItem]
            - Size [StatsItem]
          - Translation [StatsItem]
            - Size [StatsItem]
          - Rotation [StatsItem]
            - Size [StatsItem]
          - Velocity [StatsItem]
            - Size [StatsItem]
        - Sent Cluster Packets [StatsItem]
          - Size [RunningAverageItemInt]
        - Received Cluster Packets [StatsItem]
          - Size [StatsItem]
        - Received Touch Packets [StatsItem]
          - Size [StatsItem]
        - ElapsedTime [StatsItem]
        - MaxPacketLoss [StatsItem]
        - TotalInDataBW [StatsItem]
        - TotalOutDataBW [StatsItem]
        - TotalRakIn [StatsItem]
        - TotalRakOut [StatsItem]
        - OutBufferHealth [StatsItem]
        - PropSync [StatsItem]
          - ItemCount [StatsItem]
          - AckCount [StatsItem]
        - Received Stream Data [StatsItem]
          - AvgReadTimePerItem [RunningAverageItemDouble]
          - AvgInstancesPerItem [RunningAverageItemDouble]
          - RequestedInstanceAvg [RunningAverageItemInt]
          - PendingRequestCount [StatsItem]
          - GCDistance [StatsItem]
          - NumRegions [StatsItem]
          - CurrentRadius [StatsItem]
          - NumReplicationFoci [StatsItem]
          - NumPrefetches [StatsItem]
          - PlayerPosition [StatsItem]
            - X [StatsItem]
            - Y [StatsItem]
            - Z [StatsItem]
          - PlayerRegion [StatsItem]
            - X [StatsItem]
            - Y [StatsItem]
            - Z [StatsItem]
          - LastKnownServerStreamCenter [StatsItem]
            - X [StatsItem]
            - Y [StatsItem]
            - Z [StatsItem]
        - Lr Data [StatsItem]
          - LrBytesRecv [StatsItem]
          - LrSegmentsRecv [StatsItem]
          - LrEstimatedRawRecv [StatsItem]
          - LrEstimatedOptimizedRecv [StatsItem]
          - LrActualPreCompressRecv [StatsItem]
          - LrActualPostCompressRecv [StatsItem]
          - LrAssetsRecv [StatsItem]
          - LrAssetsByDeltaRecv [StatsItem]
          - LrDeltasRecv [StatsItem]
          - LrCancelRecv [StatsItem]
          - LrRemoveRecv [StatsItem]
          - LrCompleteRecv [StatsItem]
          - LrInlineRecv [StatsItem]
          - LrIgnoreRecv [StatsItem]
          - LrHashFail [StatsItem]
          - LrHashCheck [StatsItem]
          - LrMemCountRecv [StatsItem]
          - LrMemEstBytesRecv [StatsItem]
    - Luau [StatsItem]
      - disabled [StatsItem]
      - threads [StatsItem]
      - AverageGcTime [StatsItem]
    - FrameRateManager [StatsItem]
      - DeviceFeatureLevel [StatsItem]
      - DeviceShadingLanguage [StatsItem]
      - AverageQualityLevel [StatsItem]
      - AutoQuality [StatsItem]
      - NumberOfSettles [StatsItem]
      - AverageSwitches [StatsItem]
      - FramebufferWidth [StatsItem]
      - FramebufferHeight [StatsItem]
      - Batches [StatsItem]
      - Indices [StatsItem]
      - MaterialChanges [StatsItem]
      - VideoMemoryInMB [StatsItem]
      - AverageFPS [StatsItem]
      - FrameTimeVariance [StatsItem]
      - FrameSpikeCount [StatsItem]
      - RenderAverage [StatsItem]
      - PrepareAverage [StatsItem]
      - PerformAverage [StatsItem]
      - AveragePresent [StatsItem]
      - AverageGPU [StatsItem]
      - RenderThreadAverage [StatsItem]
      - TotalFrameWallAverage [StatsItem]
      - PerformVariance [StatsItem]
      - PresentVariance [StatsItem]
      - GpuVariance [StatsItem]
      - MsFrame0 [StatsItem]
      - MsFrame1 [StatsItem]
      - MsFrame2 [StatsItem]
      - MsFrame3 [StatsItem]
      - MsFrame4 [StatsItem]
      - MsFrame5 [StatsItem]
      - MsFrame6 [StatsItem]
      - MsFrame7 [StatsItem]
      - MsFrame8 [StatsItem]
      - MsFrame9 [StatsItem]
      - MsFrame10 [StatsItem]
      - MsFrame11 [StatsItem]
    - Render [StatsItem]
      - Memory [StatsItem]
        - Video [StatsItem]
  - TimerService [TimerService]
  - CollectionService [CollectionService]
  - SoundService [SoundService]
  - VideoCaptureService [VideoCaptureService]
  - LogService [LogService]
  - MicroProfilerService [MicroProfilerService]
  - ContentProvider [ContentProvider]
  - KeyframeSequenceProvider [KeyframeSequenceProvider]
  - AnimationClipProvider [AnimationClipProvider]
  - Chat [Chat]
  - MarketplaceService [MarketplaceService]
  - Players [Players]
    - hydrazx9 [Player]
      - PlayerScripts [PlayerScripts]
      - Backpack [Backpack]
  - PointsService [PointsService]
  - NotificationService [NotificationService]
  - ReplicatedFirst [ReplicatedFirst]
  - HttpRbxApiService [HttpRbxApiService]
  - TweenService [TweenService]
  - MaterialService [MaterialService]
  - TextChatService [TextChatService]
    - BubbleChatConfiguration [BubbleChatConfiguration]
      - ImageLabel [ImageLabel]
      - UICorner [UICorner]
      - UIGradient [UIGradient]
      - UIPadding [UIPadding]
    - ChannelTabsConfiguration [ChannelTabsConfiguration]
    - ChatInputBarConfiguration [ChatInputBarConfiguration]
    - ChatWindowConfiguration [ChatWindowConfiguration]
  - TextService [TextService]
  - PermissionsService [PermissionsService]
  - SharedTableRegistry [SharedTableRegistry]
  - StarterPlayer [StarterPlayer]
    - StarterCharacterScripts [StarterCharacterScripts]
    - StarterPlayerScripts [StarterPlayerScripts]
      - ClientMain [LocalScript]
        PATH: game.StarterPlayer.StarterPlayerScripts.ClientMain
        SOURCE_START
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          
          local Shared = ReplicatedStorage:WaitForChild("Shared")
          
          local Registry = require(Shared.Registry)
          
          local Net = require(Shared.Net)
          
          
          Registry.AutoLoadConfigs(ReplicatedStorage:WaitForChild("Configs"))
          
          Net.Init()
          
          
          local Client = script.Parent:WaitForChild("Client")
          
          local Render = require(Client.ClientRenderEngine)
          
          local Placement = require(Client.PlacementController)
          
          local ShopUI = require(Client.ShopUI)
          
          
          Render.Init()
          
          Placement.Init(Render)
          
          ShopUI.Init(Placement, Render)
          
          
          local okChat, errChat = pcall(function()
          
          	require(Client.ChatCommands).Init()
          
          end)
          
          if not okChat then
          
          	warn("[ChatCommands] " .. tostring(errChat))
          
          end
          
          
          Net.Request():InvokeServer("ClientReady")
          
          
        SOURCE_END
      - LocalScript [LocalScript]
        PATH: game.StarterPlayer.StarterPlayerScripts.LocalScript
        SOURCE_START
          local StarterGui = game:GetService("StarterGui")
          
          
          -- Desativa completamente a barra de inventário (Backpack) da tela do jogador
          
          StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Backpack, false)
          
        SOURCE_END
      - Client [Folder]
        - Animators [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.Animators
          SOURCE_START
            --[[
            
            	Animators: escolhe o animador de cada unidade pelo config. O ClientRenderEngine só fala com esta fábrica.
            
            	Animation = { Mode = "Procedural" }   -- padrão: poses por nome de junta (UnitAnimator)
            
            	Animation = { Mode = "Rig", ... }     -- animações reais do Animation Editor (RigAnimator)
            
            	Os dois têm o mesmo contrato: :SetPivot(cf) :SetSpeed(s) :Trigger(nome, aoSoltar) :Kill() :Step(dt) e .DeathTime
            
            ]]
            
            local UnitAnimator = require(script.Parent.UnitAnimator)
            
            local RigAnimator = require(script.Parent.RigAnimator)
            
            
            local Animators = {}
            
            
            function Animators.IsRig(cfg)
            
            	return cfg.Animation ~= nil and cfg.Animation.Mode == "Rig"
            
            end
            
            
            function Animators.new(model, role, cfg)
            
            	if not model:IsA("Model") then
            
            		return nil
            
            	end
            
            	if Animators.IsRig(cfg) then
            
            		return RigAnimator.new(model, role, cfg)
            
            	end
            
            	return UnitAnimator.new(model, role, cfg)
            
            end
            
            
            return Animators
            
            
          SOURCE_END
        - ClientRenderEngine [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.ClientRenderEngine
          SOURCE_START
            --[[
            
            	ClientRenderEngine: 100% do visual roda aqui. Nenhum inimigo existe como Instance no servidor.
            
            	- Inimigo: posição = path:PositionAt(min(D + S * (agora - T), comprimento)), com agora = workspace:GetServerTimeNow().
            
            	  O servidor só manda âncora (D,T) + velocidade (S) no spawn e quando a velocidade muda (slow/freeze).
            
            	- Partes simples são movidas em lote com BulkMoveTo (1 chamada/frame).
            
            	- Projétil: lerp de origem -> posição PREVISTA do inimigo em T1 (hora do impacto, vinda do servidor).
            
            	Assets opcionais: ReplicatedStorage.Assets.Models.{Towers,Enemies,Projectiles}.<ModelName> (também vale Assets.<Pasta> direto).
            
            	  Torres/inimigos = Models com PrimaryPart (torre: pivô na base; inimigo: pivô no centro da altura de Visual.Size).
            
            	  Projétil = Model com PrimaryPart apontando p/ -Z; Visual.Projectile.ModelName escolhe o modelo (Attribute BaseSize = escala 1).
            
            	  Modelos com juntas são animados pelo UnitAnimator (procedural, funciona com partes ancoradas).
            
            ]]
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            local RunService = game:GetService("RunService")
            
            local TweenService = game:GetService("TweenService")
            
            local Debris = game:GetService("Debris")
            
            
            local Shared = ReplicatedStorage:WaitForChild("Shared")
            
            local Registry = require(Shared.Registry)
            
            local EventBus = require(Shared.EventBus)
            
            local Net = require(Shared.Net)
            
            local PathUtil = require(Shared.PathUtil)
            
            local Animators = require(script.Parent.Animators)
            
            
            local Render = {
            
            	Enemies = {},
            
            	Towers = {},
            
            	Map = nil,
            
            	State = nil,
            
            	Data = { Coins = 0 },
            
            	Loadout = {},
            
            	Events = EventBus.new(), -- "TowerChanged"(id) · "TowerRemoved"(id) · "GameState"(state) · "PlayerData"(data)
            
            	Folder = nil,
            
            	TowersFolder = nil,
            
            }
            
            
            local enemiesFolder, fxFolder
            
            local projectiles = {}
            
            local dying = {} -- modelos animados tocando a animação de morte
            
            local pendingSpawns = {}  -  Editar
  18:22:18.436  ========== END PART 5 ==========  -  Editar
  18:22:18.436   ▶  (x2)  -  Editar
  18:22:18.437  ========== PROJECT EXPORT PART 6 ==========  -  Editar
  18:22:18.437              
            local bulkParts, bulkCFrames = {}, {}
            
            
            local function serverNow()
            
            	return workspace:GetServerTimeNow()
            
            end
            
            
            local function findIn(root, kind, name)
            
            	local folder = root and root:FindFirstChild(kind)
            
            	return folder and folder:FindFirstChild(name)
            
            end
            
            
            local function cloneAsset(kind, name, canQuery, rig)
            
            	if not name then
            
            		return nil
            
            	end
            
            	local assets = ReplicatedStorage:FindFirstChild("Assets")
            
            	local models = assets and assets:FindFirstChild("Models")
            
            	local template = findIn(models, kind, name) or findIn(assets, kind, name)
            
            	if not template then
            
            		return nil
            
            	end
            
            	local clone = template:Clone()
            
            	-- rig = animações reais: só a PrimaryPart fica ancorada; o resto segue pelas juntas (Motor6D/Weld).
            
            	-- procedural: tudo ancorado (o UnitAnimator move as peças em lote).
            
            	local root = rig and clone:IsA("Model") and clone.PrimaryPart or nil
            
            	local parts = clone:GetDescendants()
            
            	table.insert(parts, clone)
            
            	for _, d in ipairs(parts) do
            
            		if d:IsA("BasePart") then
            
            			d.CanCollide = false
            
            			d.CanQuery = canQuery
            
            			if root then
            
            				d.Anchored = d == root
            
            				d.Massless = true
            
            			else
            
            				d.Anchored = true
            
            			end
            
            		end
            
            	end
            
            	return clone
            
            end
            
            
            local function makePart(size, color, canQuery)
            
            	local part = Instance.new("Part")
            
            	part.Anchored = true
            
            	part.CanCollide = false
            
            	part.CanTouch = false
            
            	part.CanQuery = canQuery
            
            	part.Size = size
            
            	part.Color = color
            
            	part.Material = Enum.Material.SmoothPlastic
            
            	return part
            
            end
            
            
            -- ---------------------------------------------------------------- anel de alcance (usado por UI/placement)
            
            function Render.MakeRing(color)
            
            	local ring = Instance.new("Part")
            
            	ring.Shape = Enum.PartType.Cylinder
            
            	ring.Anchored = true
            
            	ring.CanCollide = false
            
            	ring.CanTouch = false
            
            	ring.CanQuery = false
            
            	ring.Material = Enum.Material.Neon
            
            	ring.Transparency = 0.8
            
            	ring.Color = color or Color3.fromRGB(255, 255, 255)
            
            	return ring
            
            end
            
            
            function Render.PlaceRing(ring, pos, range)
            
            	ring.Size = Vector3.new(0.2, range * 2, range * 2)
            
            	ring.CFrame = CFrame.new(pos + Vector3.new(0, 0.15, 0)) * CFrame.Angles(0, 0, math.rad(90))
            
            end
            
            
            function Render.TowerCost(def)
            
            	local m = Render.Map and Render.Map.Config.Multipliers
            
            	return math.ceil(def.Cost * (m and m.TowerCost or 1))
            
            end
            
            
            function Render.PickTower(inst)
            
            	local cur = inst
            
            	while cur and cur ~= Render.TowersFolder do
            
            		local id = cur:GetAttribute("TDTowerId")
            
            		if id then
            
            			return id
            
            		end
            
            		cur = cur.Parent
            
            	end
            
            	return nil
            
            end
            
            
            -- ---------------------------------------------------------------- inimigos
            
            local function adornee(r)
            
            	if r.IsPart then
            
            		return r.Inst
            
            	end
            
            	return r.Inst.PrimaryPart or r.Inst:FindFirstChildWhichIsA("BasePart", true)
            
            end
            
            
            local function updateBar(r)
            
            	if r.Hp >= r.MaxHp and not r.Bar then
            
            		return
            
            	end
            
            	if not r.Bar then
            
            		local gui = Instance.new("BillboardGui")
            
            		gui.Size = UDim2.fromOffset(60, 8)
            
            		gui.StudsOffset = Vector3.new(0, r.BarY, 0)
            
            		gui.AlwaysOnTop = true
            
            		gui.Adornee = adornee(r)
            
            		local back = Instance.new("Frame")
            
            		back.Size = UDim2.fromScale(1, 1)
            
            		back.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
            
            		back.BorderSizePixel = 0
            
            		back.Parent = gui
            
            		local fill = Instance.new("Frame")
            
            		fill.Name = "Fill"
            
            		fill.Size = UDim2.fromScale(1, 1)
            
            		fill.BackgroundColor3 = Color3.fromRGB(90, 220, 90)
            
            		fill.BorderSizePixel = 0
            
            		fill.Parent = back
            
            		gui.Parent = r.Inst
            
            		r.Bar = gui
            
            	end
            
            	r.Bar.Frame.Fill.Size = UDim2.fromScale(math.clamp(r.Hp / r.MaxHp, 0, 1), 1)
            
            end
            
            
            local function applyTint(r)
            
            	local color = r.BaseColor
            
            	for _, c in pairs(r.Tints) do
            
            		color = c
            
            		break
            
            	end
            
            	if r.IsPart then
            
            		r.Inst.Color = color
            
            	elseif r.TintParts then
            
            		local tinted = next(r.Tints) ~= nil
            
            		for part, original in pairs(r.TintParts) do
            
            			part.Color = tinted and color or original
            
            		end
            
            	end
            
            end
            
            
            local function newEnemy(p)
            
            	if Render.Enemies[p.Id] then
            
            		return
            
            	end
            
            	local cfg = Registry.Of("Enemies"):Get(p.Cfg)
            
            	local path = Render.Map and Render.Map.Paths[p.Path]
            
            	if not cfg or not path then
            
            		return
            
            	end
            
            	local vis = cfg.Visual or {}
            
            	local size = vis.Size or Vector3.new(2, 3, 2)
            
            	local inst = cloneAsset("Enemies", cfg.ModelName, false, Animators.IsRig(cfg))
            
            	if not inst then
            
            		inst = makePart(size, vis.Color or Color3.fromRGB(200, 60, 60), false)
            
            	end
            
            	inst.Parent = enemiesFolder
            
            	local isPart = inst:IsA("BasePart")
            
            	local anim = not isPart and inst:IsA("Model") and Animators.new(inst, "Enemy", cfg) or nil
            
            	local tintParts
            
            	if not isPart then
            
            		tintParts = {}
            
            		for _, d in ipairs(inst:GetDescendants()) do
            
            			if d:IsA("BasePart") and d.Transparency < 1 then
            
            				tintParts[d] = d.Color
            
            			end
            
            		end
            
            	end
            
            	local r = {
            
            		Id = p.Id,
            
            		Cfg = cfg,
            
            		Path = path,
            
            		Inst = inst,
            
            		IsPart = isPart,
            
            		D = p.D,
            
            		T = p.T,
            
            		S = p.S,
            
            		Hp = p.Hp,
            
            		MaxHp = p.MaxHp,
            
            		YOffset = size.Y / 2,
            
            		BarY = (isPart and size.Y / 2 or inst:GetAttribute("BarHeight") or size.Y / 2) + 1.5,
            
            		Anim = anim,
            
            		TintParts = tintParts,
            
            		Tints = {},
            
            		BaseColor = isPart and inst.Color or Color3.new(1, 1, 1),
            
            		LastPos = path:PositionAt(p.D),
            
            	}
            
            	Render.Enemies[p.Id] = r
            
            	updateBar(r)
            
            end
            
            
            local function removeEnemy(id, reason)
            
            	local r = Render.Enemies[id]
            
            	if not r then
            
            		return
            
            	end
            
            	Render.Enemies[id] = nil
            
            	if r.Bar then
            
            		r.Bar:Destroy()
            
            	end
            
            	if reason == "Killed" and r.IsPart then
            
            		TweenService:Create(r.Inst, TweenInfo.new(0.25), { Transparency = 1, Size = r.Inst.Size * 0.3 }):Play()
            
            		Debris:AddItem(r.Inst, 0.3)
            
            	elseif reason == "Killed" and r.Anim then
            
            		r.Anim:Kill()
            
            		table.insert(dying, { Anim = r.Anim, Inst = r.Inst, Age = 0 })
            
            	else
            
            		r.Inst:Destroy()
            
            	end
            
            end
            
            
            -- ---------------------------------------------------------------- torres
            
            local function newTower(p)
            
            	local cfg = Registry.Of("Towers"):Get(p.Cfg)
            
            	if not cfg or Render.Towers[p.Id] then
            
            		return
            
            	end
            
            	local vis = cfg.Visual or {}
            
            	local size = vis.Size or Vector3.new(3, 4, 3)
            
            	local inst = cloneAsset("Towers", cfg.ModelName, true, Animators.IsRig(cfg))
            
            	local anim, muzzle
            
            	if inst then
            
            		inst:PivotTo(CFrame.new(p.Pos))
            
            		if inst:IsA("Model") then
            
            			anim = Animators.new(inst, "Tower", cfg)
            
            			muzzle = inst:FindFirstChild("Muzzle", true)
            
            			if muzzle and not muzzle:IsA("Attachment") then
            
            				muzzle = nil
            
            			end
            
            		end
            
            	else
            
            		inst = makePart(size, vis.Color or Color3.fromRGB(200, 200, 200), true)
            
            		inst.Position = p.Pos + Vector3.new(0, size.Y / 2, 0)
            
            	end
              -  Editar
  18:22:18.437  ========== END PART 6 ==========  -  Editar
  18:22:18.437   ▶  (x2)  -  Editar
  18:22:18.438  ========== PROJECT EXPORT PART 7 ==========  -  Editar
  18:22:18.439              	inst:SetAttribute("TDTowerId", p.Id)
            
            	inst.Parent = Render.TowersFolder
            
            	Render.Towers[p.Id] = {
            
            		Id = p.Id,
            
            		Cfg = cfg,
            
            		Inst = inst,
            
            		Position = p.Pos,
            
            		Owner = p.Owner,
            
            		Range = p.Range,
            
            		Splash = p.Splash,
            
            		Tiers = p.Tiers,
            
            		Mode = p.Mode,
            
            		Invested = p.Invested,
            
            		Damage = p.Damage,
            
            		Interval = p.Interval,
            
            		Height = size.Y * 0.8,
            
            		Anim = anim,
            
            		Muzzle = muzzle,
            
            	}
            
            	Render.Events:Fire("TowerChanged", p.Id)
            
            end
            
            
            local function tierSum(tiers)
            
            	local n = 0
            
            	for _, v in pairs(tiers) do
            
            		n += v
            
            	end
            
            	return n
            
            end
            
            
            local function updateTower(p)
            
            	local t = Render.Towers[p.Id]
            
            	if not t then
            
            		return
            
            	end
            
            	local upgraded = tierSum(p.Tiers) > tierSum(t.Tiers)
            
            	t.Range, t.Splash, t.Tiers, t.Mode, t.Invested = p.Range, p.Splash, p.Tiers, p.Mode, p.Invested
            
            	t.Damage, t.Interval = p.Damage, p.Interval
            
            	if upgraded and t.Anim then
            
            		t.Anim:Trigger("Upgrade")
            
            	end
            
            	Render.Events:Fire("TowerChanged", p.Id)
            
            end
            
            
            local function removeTower(id)
            
            	local t = Render.Towers[id]
            
            	if not t then
            
            		return
            
            	end
            
            	Render.Towers[id] = nil
            
            	t.Inst:Destroy()
            
            	Render.Events:Fire("TowerRemoved", id)
            
            end
            
            
            -- ---------------------------------------------------------------- projéteis / fx
            
            local function impactFx(pos, radius, color)
            
            	local fx = Instance.new("Part")
            
            	fx.Shape = Enum.PartType.Ball
            
            	fx.Anchored = true
            
            	fx.CanCollide = false
            
            	fx.CanQuery = false
            
            	fx.CanTouch = false
            
            	fx.Material = Enum.Material.Neon
            
            	fx.Transparency = 0.4
            
            	fx.Color = color
            
            	fx.Size = Vector3.one
            
            	fx.Position = pos
            
            	fx.Parent = fxFolder
            
            	TweenService
            
            		:Create(fx, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {
            
            			Size = Vector3.one * radius * 2,
            
            			Transparency = 1,
            
            		})
            
            		:Play()
            
            	Debris:AddItem(fx, 0.35)
            
            end
            
            
            local function placeProjectile(pr, pos)
            
            	if pr.IsAsset then
            
            		local d = pos - pr.LastPos
            
            		if d.Magnitude > 1e-3 then
            
            			pr.Dir = d.Unit
            
            		end
            
            		pr.LastPos = pos
            
            		pr.Part:PivotTo(CFrame.lookAt(pos, pos + pr.Dir))
            
            	else
            
            		pr.Part.Position = pos
            
            	end
            
            end
            
            
            -- impacto de projétil com modelo próprio: emissores com atributo EmitCount soltam uma rajada, rastros param,
            
            -- o corpo some (exceto peças com atributo KeepOnImpact) e o modelo fica ImpactLifetime segundos para os efeitos terminarem
            
            local function projectileImpact(pr)
            
            	local inst = pr.Part
            
            	if not pr.IsAsset then
            
            		inst:Destroy()
            
            		return
            
            	end
            
            	inst:PivotTo(CFrame.lookAt(pr.Target, pr.Target + pr.Dir))
            
            	for _, d in ipairs(inst:GetDescendants()) do
            
            		if d:IsA("ParticleEmitter") then
            
            			d.Enabled = false
            
            			local count = d:GetAttribute("EmitCount")
            
            			if count then
            
            				d:Emit(count)
            
            			end
            
            		elseif d:IsA("Trail") then
            
            			d.Enabled = false
            
            		elseif d:IsA("BasePart") and not d:GetAttribute("KeepOnImpact") then
            
            			d.Transparency = 1
            
            		end
            
            	end
            
            	Debris:AddItem(inst, pr.Cfg.ImpactLifetime or 1.5)
            
            end
            
            
            local function fireTower(f)
            
            	local tw = Render.Towers[f.Tower]
            
            	if not tw then
            
            		return
            
            	end
            
            	local en = Render.Enemies[f.Enemy]
            
            	local pv = tw.Cfg.Visual and tw.Cfg.Visual.Projectile or {}
            
            
            	if en then
            
            		local look = Vector3.new(en.LastPos.X, tw.Position.Y, en.LastPos.Z)
            
            		if look ~= tw.Position then
            
            			local rot = CFrame.lookAt(tw.Position, look)
            
            			if tw.Anim then
            
            				tw.Anim:SetPivot(rot)
            
            			else
            
            				tw.Inst:PivotTo(rot)
            
            			end
            
            		end
            
            	end
            
            
            	local fallback = en and en.LastPos or tw.Position
            
            	local launched = false
            
            
            	-- o projétil sai no instante de "soltar" da animação (procedural: ReleaseTime; rig: marcador "Release")
            
            	local function launch()
            
            		if launched or not Render.Towers[tw.Id] then
            
            			return
            
            		end
            
            		launched = true
            
            		if tw.Anim then
            
            			tw.Anim:Step(0) -- aplica a pose atual: o Muzzle precisa estar no lugar certo
            
            		end
            
            		local now = serverNow()
            
            		local cur = Render.Enemies[f.Enemy]
            
            		local origin = tw.Muzzle and tw.Muzzle.WorldPosition or (tw.Position + Vector3.new(0, tw.Height, 0))
            
            		local target = cur and cur.LastPos or fallback
            
            		local flat = target - origin
            
            		local dir = flat.Magnitude > 1e-3 and flat.Unit or Vector3.new(0, 0, -1)
            
            
            		local part = pv.ModelName and cloneAsset("Projectiles", pv.ModelName, false)
            
            		local isAsset = part ~= nil
            
            		if isAsset then
            
            			local base = part:GetAttribute("BaseSize")
            
            			if base and pv.Size and part:IsA("Model") then
            
            				part:ScaleTo(pv.Size / base)
            
            			end
            
            			part:PivotTo(CFrame.lookAt(origin, origin + dir))
            
            			part.Parent = fxFolder
            
            		else
            
            			part = Instance.new("Part")
            
            			part.Shape = Enum.PartType.Ball
            
            			part.Anchored = true
            
            			part.CanCollide = false
            
            			part.CanQuery = false
            
            			part.CanTouch = false
            
            			part.Material = Enum.Material.Neon
            
            			part.Color = pv.Color or Color3.fromRGB(255, 255, 255)
            
            			part.Size = Vector3.one * (pv.Size or 0.7)
            
            			part.Position = origin
            
            			part.Parent = fxFolder
            
            		end
            
            		table.insert(projectiles, {
            
            			Part = part,
            
            			IsAsset = isAsset,
            
            			Cfg = pv,
            
            			LastPos = origin,
            
            			Dir = dir,
            
            			From = origin,
            
            			EnemyId = f.Enemy,
            
            			T0 = now,
            
            			T1 = math.max(f.T1, now + 0.1), -- o acerto é decidido pelo servidor (T1); mínimo de 0.1s visível
            
            			Arc = pv.Arc or 0,
            
            			Splash = tw.Splash,
            
            			Color = pv.Color or Color3.fromRGB(255, 255, 255),
            
            			Target = target,
            
            		})
            
            	end
            
            
            	if tw.Anim then
            
            		tw.Anim:Trigger("Attack", launch)
            
            	else
            
            		launch()
            
            	end
            
            end
            
            
            -- ---------------------------------------------------------------- loop de render
            
            local function step(dt)
            
            	local t = serverNow()
            
            
            	local n = 0
            
            	for _, r in pairs(Render.Enemies) do
            
            		local d = r.D + r.S * (t - r.T)
            
            		local len = r.Path.Length
            
            		if d > len then
            
            			d = len
            
            		elseif d < 0 then
            
            			d = 0
            
            		end
            
            		local pos = r.Path:PositionAt(d)
            
            		r.LastPos = pos
            
            		local center = pos + Vector3.new(0, r.YOffset, 0)
            
            		local cf = CFrame.lookAt(center, center + r.Path:DirectionAt(d))
            
            		if r.IsPart then
            
            			n += 1
            
            			bulkParts[n] = r.Inst
            
            			bulkCFrames[n] = cf
            
            		elseif r.Anim then
            
            			r.Anim:SetPivot(cf)
            
            			r.Anim:SetSpeed(r.S)
            
            			r.Anim:Step(dt)
            
            		else
            
            			r.Inst:PivotTo(cf)
            
            		end
            
            	end
            
            	for i = #bulkParts, n + 1, -1 do
            
            		bulkParts[i] = nil
            
            		bulkCFrames[i] = nil
            
            	end
            
            	if n > 0 then
            
            		workspace:BulkMoveTo(bulkParts, bulkCFrames, Enum.BulkMoveMode.FireCFrameChanged)
            
            	end
            
            
            	for _, tw in pairs(Render.Towers) do
            
            		if tw.Anim then
            
            			tw.Anim:Step(dt)
            
            		end
            
            	end
              -  Editar
  18:22:18.439  ========== END PART 7 ==========  -  Editar
  18:22:18.439   ▶  (x2)  -  Editar
  18:22:18.440  ========== PROJECT EXPORT PART 8 ==========  -  Editar
  18:22:18.440              	for i = #dying, 1, -1 do
            
            		local d = dying[i]
            
            		d.Age += dt
            
            		d.Anim:Step(dt)
            
            		if d.Age >= (d.Anim.DeathTime or 0.5) then
            
            			d.Inst:Destroy()
            
            			table.remove(dying, i)
            
            		end
            
            	end
            
            
            	for i = #projectiles, 1, -1 do
            
            		local pr = projectiles[i]
            
            		local en = Render.Enemies[pr.EnemyId]
            
            		if en then
            
            			local d = math.min(en.D + en.S * (pr.T1 - en.T), en.Path.Length)
            
            			pr.Target = en.Path:PositionAt(d) + Vector3.new(0, en.YOffset, 0)
            
            		end
            
            		local alpha = (t - pr.T0) / (pr.T1 - pr.T0)
            
            		if alpha >= 1 then
            
            			if pr.Splash > 0 then
            
            				impactFx(pr.Target, pr.Splash, pr.Color)
            
            			end
            
            			projectileImpact(pr)
            
            			table.remove(projectiles, i)
            
            		else
            
            			alpha = math.max(alpha, 0)
            
            			local pos = pr.From:Lerp(pr.Target, alpha)
            
            			if pr.Arc > 0 then
            
            				pos += Vector3.new(0, math.sin(math.pi * alpha) * pr.Arc, 0)
            
            			end
            
            			placeProjectile(pr, pos)
            
            		end
            
            	end
            
            end
            
            
            -- ---------------------------------------------------------------- rede
            
            local function setMap(mapId)
            
            	for _, r in pairs(Render.Enemies) do
            
            		r.Inst:Destroy()
            
            	end
            
            	for _, tw in pairs(Render.Towers) do
            
            		tw.Inst:Destroy()
            
            	end
            
            	for _, pr in ipairs(projectiles) do
            
            		pr.Part:Destroy()
            
            	end
            
            	for _, d in ipairs(dying) do
            
            		d.Inst:Destroy()
            
            	end
            
            	table.clear(dying)
            
            	table.clear(Render.Enemies)
            
            	table.clear(Render.Towers)
            
            	table.clear(projectiles)
            
            
            	local cfg = Registry.Of("Maps"):Get(mapId)
            
            	if not cfg then
            
            		Render.Map = nil
            
            		return
            
            	end
            
            	local paths = {}
            
            	for id, points in pairs(cfg.Paths) do
            
            		paths[id] = PathUtil.new(points)
            
            	end
            
            	Render.Map = { Id = mapId, Config = cfg, Paths = paths }
            
            	for _, p in ipairs(pendingSpawns) do
            
            		newEnemy(p)
            
            	end
            
            	table.clear(pendingSpawns)
            
            end
            
            
            local function onDelta(p)
            
            	for _, e in ipairs(p.EnemySpawned) do
            
            		if Render.Map then
            
            			newEnemy(e)
            
            		else
            
            			table.insert(pendingSpawns, e) -- mapa ainda não chegou (entrada tardia)
            
            		end
            
            	end
            
            	for _, m in ipairs(p.EnemyMotion) do
            
            		local r = Render.Enemies[m.Id]
            
            		if r then
            
            			r.D, r.T, r.S = m.D, m.T, m.S
            
            		end
            
            	end
            
            	for _, h in ipairs(p.EnemyHealth) do
            
            		local r = Render.Enemies[h.Id]
            
            		if r then
            
            			r.Hp = h.Hp
            
            			updateBar(r)
            
            		end
            
            	end
            
            	for _, s in ipairs(p.Status) do
            
            		local r = Render.Enemies[s.Enemy]
            
            		if r then
            
            			local def = Registry.Of("StatusEffects"):Get(s.Effect)
            
            			r.Tints[s.Effect] = s.On and def and def.Visual and def.Visual.Color or nil
            
            			applyTint(r)
            
            		end
            
            	end
            
            	for _, tp in ipairs(p.TowerPlaced) do
            
            		newTower(tp)
            
            	end
            
            	for _, tu in ipairs(p.TowerUpdated) do
            
            		updateTower(tu)
            
            	end
            
            	for _, f in ipairs(p.TowerFired) do
            
            		fireTower(f)
            
            	end
            
            	for _, id in ipairs(p.TowerRemoved) do
            
            		removeTower(id.Id)
            
            	end
            
            	for _, e in ipairs(p.EnemyRemoved) do
            
            		removeEnemy(e.Id, e.Reason)
            
            	end
            
            end
            
            
            function Render.Init()
            
            	Render.Folder = Instance.new("Folder")
            
            	Render.Folder.Name = "TDClient"
            
            	Render.Folder.Parent = workspace
            
            	Render.TowersFolder = Instance.new("Folder")
            
            	Render.TowersFolder.Name = "Towers"
            
            	Render.TowersFolder.Parent = Render.Folder
            
            	enemiesFolder = Instance.new("Folder")
            
            	enemiesFolder.Name = "Enemies"
            
            	enemiesFolder.Parent = Render.Folder
            
            	fxFolder = Instance.new("Folder")
            
            	fxFolder.Name = "FX"
            
            	fxFolder.Parent = Render.Folder
            
            
            	Net.Event("GameState").OnClientEvent:Connect(function(state)
            
            		Render.State = state
            
            		if not Render.Map or Render.Map.Id ~= state.MapId then
            
            			setMap(state.MapId)
            
            		end
            
            		Render.Events:Fire("GameState", state)
            
            	end)
            
            	Net.Event("PlayerData").OnClientEvent:Connect(function(data)
            
            		Render.Data = data
            
            		Render.Events:Fire("PlayerData", data)
            
            	end)
            
            	Net.Event("Loadout").OnClientEvent:Connect(function(list)
            
            		Render.Loadout = list
            
            		Render.Events:Fire("Loadout", list)
            
            	end)
            
            	Net.Event("Delta").OnClientEvent:Connect(onDelta)
            
            	RunService.RenderStepped:Connect(step)
            
            end
            
            
            return Render
            
            
          SOURCE_END
        - PlacementController [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.PlacementController
          SOURCE_START
            --[[
            
            	PlacementController: fantasma da torre (verde/vermelho), confirmação por clique/toque e seleção de torres.
            
            	O cliente só PREVÊ com PlacementRules; quem decide é o servidor (Request "PlaceTower").
            
            ]]
            
            local UserInputService = game:GetService("UserInputService")
            
            local RunService = game:GetService("RunService")
            
            local Players = game:GetService("Players")
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            
            local Shared = ReplicatedStorage:WaitForChild("Shared")
            
            local Registry = require(Shared.Registry)
            
            local Net = require(Shared.Net)
            
            local PlacementRules = require(Shared.PlacementRules)
            
            
            local GREEN, RED = Color3.fromRGB(90, 220, 110), Color3.fromRGB(230, 80, 80)
            
            
            local Placement = { Active = nil, OnSelect = nil, OnResult = nil }
            
            local Render
            
            local ghost, ring, conn
            
            local activeRange = 0
            
            local pointer = nil -- só usado no toque
            
            local currentPos, currentValid, currentReason = nil, false, nil
            
            
            function Placement.Cancel()
            
            	Placement.Active = nil
            
            	currentPos = nil
            
            	if conn then
            
            		conn:Disconnect()
            
            		conn = nil
            
            	end
            
            	if ghost then
            
            		ghost:Destroy()
            
            		ghost = nil
            
            	end
            
            	if ring then
            
            		ring:Destroy()
            
            		ring = nil
            
            	end
            
            end
            
            
            local function update()
            
            	if not Placement.Active or not Render.Map then
            
            		return
            
            	end
            
            	local camera = workspace.CurrentCamera
            
            	local loc = pointer or UserInputService:GetMouseLocation()
            
            	local ray = camera:ViewportPointToRay(loc.X, loc.Y)
            
            	local params = RaycastParams.new()
            
            	params.FilterType = Enum.RaycastFilterType.Exclude
            
            	params.FilterDescendantsInstances = { Render.Folder, Players.LocalPlayer.Character }
            
            	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
            
            	if not hit then
            
            		currentPos = nil
            
            		ghost.Transparency = 1
            
            		return
            
            	end
            
            	local y = Render.Map.Config.GroundY or 0
            
            	currentPos = Vector3.new(hit.Position.X, y, hit.Position.Z)
            
            	currentValid, currentReason = PlacementRules.Check(Render.Map, currentPos, Render.Towers)
            
            	ghost.Position = currentPos + Vector3.new(0, ghost.Size.Y / 2, 0)
            
            	ghost.Transparency = 0.45
            
            	local color = currentValid and GREEN or RED
            
            	ghost.Color = color
            
            	ring.Color = color
            
            	if activeRange > 0 then
            
            		ring.Transparency = 0.8
            
            		Render.PlaceRing(ring, currentPos, activeRange)
            
            	else
            
            		ring.Transparency = 1
            
            	end
            
            end
            
            
            function Placement.Begin(towerId)
            
            	Placement.Cancel()
            
            	local def = Registry.Of("Towers"):Get(towerId)
            
            	if not def then
            
            		return
            
            	end
            
            	Placement.Active = towerId
            
            	if Placement.OnSelect then
            
            		Placement.OnSelect(nil)
            
            	end
              -  Editar
  18:22:18.440  ========== END PART 8 ==========  -  Editar
  18:22:18.440   ▶  (x2)  -  Editar
  18:22:18.441  ========== PROJECT EXPORT PART 9 ==========  -  Editar
  18:22:18.441              	local vis = def.Visual or {}
            
            	ghost = Instance.new("Part")
            
            	ghost.Anchored = true
            
            	ghost.CanCollide = false
            
            	ghost.CanQuery = false
            
            	ghost.CanTouch = false
            
            	ghost.Size = vis.Size or Vector3.new(3, 4, 3)
            
            	ghost.Transparency = 1
            
            	ghost.Parent = Render.Folder
            
            	ring = Render.MakeRing()
            
            	ring.Parent = Render.Folder
            
            	activeRange = def.Stats and def.Stats.Range or 0
            
            	conn = RunService.RenderStepped:Connect(update)
            
            end
            
            
            function Placement.Toggle(towerId)
            
            	if Placement.Active == towerId then
            
            		Placement.Cancel()
            
            	else
            
            		Placement.Begin(towerId)
            
            	end
            
            end
            
            
            local function confirm()
            
            	if not Placement.Active or not currentPos then
            
            		return
            
            	end
            
            	if not currentValid then
            
            		if Placement.OnResult then
            
            			Placement.OnResult({ Ok = false, Error = currentReason })
            
            		end
            
            		return
            
            	end
            
            	local id, pos = Placement.Active, currentPos
            
            	if not UserInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
            
            		Placement.Cancel() -- segure Shift para colocar várias
            
            	end
            
            	local res = Net.Request():InvokeServer("PlaceTower", { TowerId = id, Position = pos })
            
            	if Placement.OnResult then
            
            		Placement.OnResult(res)
            
            	end
            
            end
            
            
            local function selectAt(loc)
            
            	local ray = workspace.CurrentCamera:ViewportPointToRay(loc.X, loc.Y)
            
            	local params = RaycastParams.new()
            
            	params.FilterType = Enum.RaycastFilterType.Include
            
            	params.FilterDescendantsInstances = { Render.TowersFolder }
            
            	local hit = workspace:Raycast(ray.Origin, ray.Direction * 1000, params)
            
            	local id = hit and Render.PickTower(hit.Instance) or nil
            
            	if Placement.OnSelect then
            
            		Placement.OnSelect(id)
            
            	end
            
            end
            
            
            function Placement.Init(renderEngine)
            
            	Render = renderEngine
            
            
            	UserInputService.InputChanged:Connect(function(input)
            
            		if input.UserInputType == Enum.UserInputType.Touch then
            
            			pointer = Vector2.new(input.Position.X, input.Position.Y)
            
            		end
            
            	end)
            
            
            	UserInputService.InputBegan:Connect(function(input, processed)
            
            		if processed then
            
            			return
            
            		end
            
            		local t = input.UserInputType
            
            		if t == Enum.UserInputType.MouseButton1 then
            
            			pointer = nil
            
            			if Placement.Active then
            
            				confirm()
            
            			else
            
            				selectAt(UserInputService:GetMouseLocation())
            
            			end
            
            		elseif t == Enum.UserInputType.MouseButton2 or (t == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.Escape) then
            
            			Placement.Cancel()
            
            		elseif t == Enum.UserInputType.Touch then
            
            			pointer = Vector2.new(input.Position.X, input.Position.Y)
            
            			if not Placement.Active then
            
            				selectAt(pointer)
            
            			end
            
            		end
            
            	end)
            
            
            	-- toque: arraste para posicionar, solte para confirmar
            
            	UserInputService.InputEnded:Connect(function(input, processed)
            
            		if not processed and input.UserInputType == Enum.UserInputType.Touch and Placement.Active then
            
            			confirm()
            
            		end
            
            	end)
            
            end
            
            
            return Placement
            
            
          SOURCE_END
        - RigAnimator [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.RigAnimator
          SOURCE_START
            --[[
            
            	RigAnimator: mesmo contrato do UnitAnimator, mas toca AnimationTracks reais (Animation Editor).
            
            	O ClientRenderEngine ancora só a PrimaryPart quando Animation.Mode = "Rig"; o resto do modelo segue pelas juntas.
            
            	AnimationController e Animator são criados se o modelo não tiver.
            
            
            	Animation = {
            
            		Mode = "Rig",
            
            		Tracks = { Idle = "rbxassetid://...", Walk = "...", Attack = "...", Upgrade = "...", Death = "..." },  -- todos opcionais
            
            		WalkSpeed = 9,        -- studs/s em que o Walk toca a 1x (padrão: Speed do config do inimigo)
            
            		ReleaseMarker = true, -- KeyframeMarker "Release" no Attack = instante em que o projétil sai
            
            		ReleaseTime = 0.3,    -- alternativa sem marcador: segundos após o início do Attack (0 = sai na hora)
            
            	}
            
            ]]
            
            local RigAnimator = {}
            
            RigAnimator.__index = RigAnimator
            
            
            local PRIORITY = {
            
            	Idle = Enum.AnimationPriority.Idle,
            
            	Walk = Enum.AnimationPriority.Movement,
            
            	Attack = Enum.AnimationPriority.Action,
            
            	Upgrade = Enum.AnimationPriority.Action2,
            
            	Death = Enum.AnimationPriority.Action4,
            
            }
            
            local LOOPED = { Idle = true, Walk = true }
            
            
            function RigAnimator.new(model, role, cfg)
            
            	if not model.PrimaryPart then
            
            		return nil
            
            	end
            
            	local a = cfg.Animation or {}
            
            	return setmetatable({
            
            		Model = model,
            
            		Role = role,
            
            		Config = a,
            
            		Tracks = {},
            
            		Loaded = false,
            
            		Pivot = model:GetPivot(),
            
            		Speed = 0,
            
            		WalkRef = a.WalkSpeed or cfg.Speed or 8,
            
            		ReleaseTime = a.ReleaseTime or 0,
            
            		DeathTime = 0.15,
            
            		PendingRelease = nil,
            
            		ReleaseAt = 0,
            
            		Time = 0,
            
            		Dead = false,
            
            	}, RigAnimator)
            
            end
            
            
            -- carrega as animações só quando o modelo já está no workspace (o Animator exige isso)
            
            function RigAnimator:_load()
            
            	if self.Loaded or not self.Model:IsDescendantOf(workspace) then
            
            		return
            
            	end
            
            	self.Loaded = true
            
            	local controller = self.Model:FindFirstChildWhichIsA("AnimationController", true)
            
            		or self.Model:FindFirstChildWhichIsA("Humanoid", true)
            
            	if not controller then
            
            		controller = Instance.new("AnimationController")
            
            		controller.Parent = self.Model
            
            	end
            
            	local animator = controller:FindFirstChildWhichIsA("Animator")
            
            	if not animator then
            
            		animator = Instance.new("Animator")
            
            		animator.Parent = controller
            
            	end
            
            	for name, id in pairs(self.Config.Tracks or {}) do
            
            		local anim = Instance.new("Animation")
            
            		anim.AnimationId = id
            
            		local ok, track = pcall(function()
            
            			return animator:LoadAnimation(anim)
            
            		end)
            
            		if ok and track then
            
            			track.Priority = PRIORITY[name] or Enum.AnimationPriority.Action
            
            			track.Looped = LOOPED[name] == true
            
            			self.Tracks[name] = track
            
            		else
            
            			warn(("[RigAnimator] %s: não carregou a animação '%s'"):format(self.Model.Name, name))
            
            		end
            
            	end
            
            	if self.Tracks.Idle then
            
            		self.Tracks.Idle:Play()
            
            	end
            
            	if self.Tracks.Walk then
            
            		self.Tracks.Walk:Play(0.1, 1, 0) -- começa parado; SetSpeed liga o ciclo
            
            	end
            
            	if self.Tracks.Death then
            
            		self.DeathTime = math.max(self.Tracks.Death.Length, 0.15)
            
            	end
            
            end
            
            
            function RigAnimator:SetPivot(cf)
            
            	self.Pivot = cf
            
            end
            
            
            function RigAnimator:SetSpeed(speed)
            
            	self.Speed = speed
            
            	local walk = self.Tracks.Walk
            
            	if walk and not self.Dead then
            
            		walk:AdjustSpeed(speed > 0.05 and speed / self.WalkRef or 0) -- 0 = pose congelada
            
            	end
            
            end
            
            
            function RigAnimator:_release()
            
            	local fn = self.PendingRelease
            
            	if fn then
            
            		self.PendingRelease = nil
            
            		fn()
            
            	end
            
            end
            
            
            function RigAnimator:Trigger(name, onRelease)
            
            	self:_load()
            
            	local track = self.Tracks[name]
            
            	if track then
            
            		track:Play(0.05, 1, 1)
            
            	end
            
            	if name ~= "Attack" or not onRelease then
            
            		return
            
            	end
            
            	self:_release() -- solta o disparo anterior, se ainda estava pendente
            
            	if not track then
            
            		onRelease()
            
            	elseif self.Config.ReleaseMarker then
            
            		self.PendingRelease = onRelease
            
            		self.ReleaseAt = self.Time + 1 -- segurança se o marcador não existir na animação
            
            		local conn
              -  Editar
  18:22:18.441  ========== END PART 9 ==========  -  Editar
  18:22:18.441   ▶  (x2)  -  Editar
  18:22:18.442  ========== PROJECT EXPORT PART 10 ==========  -  Editar
  18:22:18.442              		conn = track:GetMarkerReachedSignal("Release"):Connect(function()
            
            			conn:Disconnect()
            
            			self:_release()
            
            		end)
            
            	elseif self.ReleaseTime > 0 then
            
            		self.PendingRelease = onRelease
            
            		self.ReleaseAt = self.Time + self.ReleaseTime
            
            	else
            
            		onRelease()
            
            	end
            
            end
            
            
            function RigAnimator:Kill()
            
            	if self.Dead then
            
            		return
            
            	end
            
            	self.Dead = true
            
            	self:_load()
            
            	self:_release()
            
            	for name, track in pairs(self.Tracks) do
            
            		if name ~= "Death" then
            
            			track:Stop(0.05)
            
            		end
            
            	end
            
            	if self.Tracks.Death then
            
            		self.Tracks.Death:Play(0.05, 1, 1)
            
            	end
            
            end
            
            
            function RigAnimator:Step(dt)
            
            	self.Time += dt
            
            	self:_load()
            
            	self.Model:PivotTo(self.Pivot)
            
            	if self.PendingRelease and self.Time >= self.ReleaseAt then
            
            		self:_release()
            
            	end
            
            end
            
            
            return RigAnimator
            
            
          SOURCE_END
        - ShopUI [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.ShopUI
          SOURCE_START
            --[[
            
            	ShopUI (Factory): NENHUM botão é desenhado à mão.
            
            	- Loja: um clone do template (ReplicatedStorage.Template2) por entrada de TowersConfig, dentro de MainUI.Units.Background
            
            	- Painel da torre selecionada: upgrades/targeting/venda gerados de cfg.Upgrades e cfg.Targeting
            
            	- HUD: estado, onda, vidas, moedas e contagem regressiva
            
            ]]
            
            local Players = game:GetService("Players")
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            
            local Shared = ReplicatedStorage:WaitForChild("Shared")
            
            local Registry = require(Shared.Registry)
            
            local Net = require(Shared.Net)
            
            local UnitCard = require(script.Parent.UnitCard)
            
            local UnitPanel = require(script.Parent.UnitPanel)
            
            
            local ERRORS = {
            
            	NotEnoughCoins = "Moedas insuficientes",
            
            	NotEquipped = "Equipe essa unidade no inventário",
            
            	LoadoutFull = "Slots cheios: desequipe uma unidade",
            
            	CannotBuildNow = "Não é possível construir agora",
            
            	OutOfBounds = "Fora da área do mapa",
            
            	TooCloseToPath = "Muito perto do caminho",
            
            	TooCloseToTower = "Muito perto de outra torre",
            
            	LimitReached = "Limite dessa torre atingido",
            
            	MaxTier = "Nível máximo",
            
            	PathLocked = "Caminho bloqueado por outro upgrade",
            
            	NotYourTower = "Essa torre não é sua",
            
            	RateLimited = "Calma! Muitas ações",
            
            }
            
            local STATE_NAMES = {
            
            	WaitingForPlayers = "Aguardando jogadores",
            
            	Intermission = "Intervalo",
            
            	WaveActive = "Onda em andamento",
            
            	GameOver = "Fim de jogo",
            
            	Victory = "Vitória!",
            
            }
            
            
            local TEMPLATE_NAME = "Template2" -- troque para "Template1" quando quiser cards com ícone
            
            
            local ShopUI = {}
            
            
            local function new(class, props, parent)
            
            	local inst = Instance.new(class)
            
            	for k, v in pairs(props) do
            
            		inst[k] = v
            
            	end
            
            	inst.Parent = parent
            
            	return inst
            
            end
            
            
            function ShopUI.Init(Placement, Render)
            
            	local player = Players.LocalPlayer
            
            	local playerGui = player:WaitForChild("PlayerGui")
            
            	local gui = new("ScreenGui", { Name = "TDUI", ResetOnSpawn = false }, playerGui)
            
            
            	-- ---------------------------------------------------------- HUD + toast
            
            	local hud = new("TextLabel", {
            
            		AnchorPoint = Vector2.new(0.5, 0),
            
            		Position = UDim2.new(0.5, 0, 0, 8),
            
            		Size = UDim2.fromOffset(520, 34),
            
            		BackgroundColor3 = Color3.fromRGB(20, 22, 28),
            
            		BackgroundTransparency = 0.2,
            
            		TextColor3 = Color3.new(1, 1, 1),
            
            		Font = Enum.Font.GothamMedium,
            
            		TextSize = 16,
            
            		Text = "Conectando...",
            
            	}, gui)
            
            	new("UICorner", { CornerRadius = UDim.new(0, 8) }, hud)
            
            
            	local toastLabel = new("TextLabel", {
            
            		AnchorPoint = Vector2.new(0.5, 0),
            
            		Position = UDim2.new(0.5, 0, 0, 48),
            
            		Size = UDim2.fromOffset(360, 30),
            
            		BackgroundColor3 = Color3.fromRGB(150, 50, 50),
            
            		TextColor3 = Color3.new(1, 1, 1),
            
            		Font = Enum.Font.GothamMedium,
            
            		TextSize = 15,
            
            		Visible = false,
            
            	}, gui)
            
            	new("UICorner", { CornerRadius = UDim.new(0, 8) }, toastLabel)
            
            	local toastToken = 0
            
            	local function toast(text)
            
            		toastToken += 1
            
            		local mine = toastToken
            
            		toastLabel.Text = text
            
            		toastLabel.Visible = true
            
            		task.delay(2.5, function()
            
            			if toastToken == mine then
            
            				toastLabel.Visible = false
            
            			end
            
            		end)
            
            	end
            
            	local function explain(res)
            
            		if res and not res.Ok then
            
            			toast(ERRORS[res.Error] or tostring(res.Error))
            
            		end
            
            	end
            
            	Placement.OnResult = explain
            
            
            	local function refreshHud()
            
            		local s = Render.State
            
            		if not s then
            
            			return
            
            		end
            
            		local left = ""
            
            		if s.EndsAt and s.EndsAt > 0 then
            
            			left = (" | %ds"):format(math.max(0, math.ceil(s.EndsAt - workspace:GetServerTimeNow())))
            
            		end
            
            		local waveText = s.VictoryWave and s.VictoryWave > 0 and ("%d/%d"):format(s.Wave, s.VictoryWave) or tostring(s.Wave)
            
            		hud.Text = ("%s | Onda %s | Vidas %d/%d | Moedas %d%s"):format(
            
            			STATE_NAMES[s.State] or s.State,
            
            			waveText,
            
            			s.Lives,
            
            			s.MaxLives,
            
            			Render.Data.Coins or 0,
            
            			left
            
            		)
            
            	end
            
            	task.spawn(function()
            
            		while gui.Parent do
            
            			refreshHud()
            
            			task.wait(0.25)
            
            		end
            
            	end)
            
            
            	-- ---------------------------------------------------------- loja (equipadas) + inventário (todas)
            
            	local template = ReplicatedStorage:WaitForChild(TEMPLATE_NAME)
            
            	local mainUI = playerGui:WaitForChild("MainUI")
            
            	local shopBackground = mainUI:WaitForChild("Units"):WaitForChild("Background") -- Frame Units: só as equipadas
            
            	local invUnits = mainUI:WaitForChild("Inventory"):WaitForChild("Units") -- ScrollingFrame Units: todas
            
            
            	if not shopBackground:FindFirstChildWhichIsA("UIListLayout") and not shopBackground:FindFirstChildWhichIsA("UIGridLayout") then
            
            		new("UIListLayout", {
            
            			FillDirection = Enum.FillDirection.Horizontal,
            
            			Padding = UDim.new(0, 8),
            
            			SortOrder = Enum.SortOrder.LayoutOrder,
            
            		}, shopBackground)
            
            	end
            
            
            	local WHITE, RED, GREEN = Color3.new(1, 1, 1), Color3.fromRGB(255, 120, 120), Color3.fromRGB(120, 255, 140)
            
            	local shopCards, invCards = {}, {}
            
            
            	local function makeCard(def, parent, order)
            
            		local button = template:Clone()
            
            		button.Name = def.Id
            
            		button.LayoutOrder = order
            
            		button.Visible = true
            
            		button.Parent = parent
            
            		if button:IsA("ImageButton") and def.Icon and def.Icon ~= "" then
            
            			button.Image = def.Icon
            
            		end
            
            		return button
            
            	end
            
            
            	local function refreshShop()
            
            		local coins = Render.Data.Coins or 0
            
            		for _, c in pairs(shopCards) do
            
            			local cost = Render.TowerCost(c.Def)
            
            			if c.Button:IsA("TextButton") then
            
            				c.Button.Text = ("%s\n$%d"):format(c.Def.DisplayName or c.Def.Id, cost)
            
            				c.Button.TextColor3 = coins >= cost and WHITE or RED
            
            			end
            
            		end
            
            	end
            
            
            	local function refreshInventory()
            
            		for id, c in pairs(invCards) do
            
            			local eq = table.find(Render.Loadout, id) ~= nil
            
            			if c.Button:IsA("TextButton") then
            
            				c.Button.Text = ("%s\n%s"):format(c.Def.DisplayName or id, eq and "[Equipado]" or "Equipar")
            
            				c.Button.TextColor3 = eq and GREEN or WHITE
            
            			end
            
            		end
            
            	end
            
            
            	local function rebuildShop()
            
            		for _, c in pairs(shopCards) do
            
            			c.Button:Destroy()
            
            		end
            
            		table.clear(shopCards)
            
            		local towers = Registry.Of("Towers")
              -  Editar
  18:22:18.442  ========== END PART 10 ==========  -  Editar
  18:22:18.442   ▶  (x2)  -  Editar
  18:22:18.442  ========== PROJECT EXPORT PART 11 ==========  -  Editar
  18:22:18.443              		for i, id in ipairs(Render.Loadout) do
            
            			local def = towers:Get(id)
            
            			if def then
            
            				local button = UnitCard.Make(def, shopBackground, i, Render) or makeCard(def, shopBackground, i)
            
            				button.Activated:Connect(function()
            
            					Placement.Toggle(id)
            
            				end)
            
            				shopCards[id] = { Button = button, Def = def }
            
            			end
            
            		end
            
            		refreshShop()
            
            	end
            
            
            	-- inventário: um card por torre existente (torres novas em TowersConfig aparecem sozinhas)
            
            	Registry.Of("Towers"):OnRegister(function(def)
            
            		local button = makeCard(def, invUnits, def.Cost)
            
            		button.Activated:Connect(function()
            
            			explain(Net.Request():InvokeServer("ToggleEquip", { TowerId = def.Id }))
            
            		end)
            
            		invCards[def.Id] = { Button = button, Def = def }
            
            		refreshInventory()
            
            	end)
            
            
            	Render.Events:Connect("Loadout", function(list)
            
            		if Placement.Active and not table.find(list, Placement.Active) then
            
            			Placement.Cancel()
            
            		end
            
            		rebuildShop()
            
            		refreshInventory()
            
            	end)
            
            	Render.Events:Connect("PlayerData", refreshShop)
            
            	Render.Events:Connect("GameState", refreshShop)
            
            	rebuildShop()
            
            	refreshInventory()
            
            
            	-- ---------------------------------------------------------- painel da torre selecionada
            
            	local selectedId
            
            	local selectionRing
            
            	local panel = new("Frame", {
            
            		AnchorPoint = Vector2.new(1, 0.5),
            
            		Position = UDim2.new(1, -10, 0.5, 0),
            
            		Size = UDim2.fromOffset(260, 10),
            
            		AutomaticSize = Enum.AutomaticSize.Y,
            
            		BackgroundColor3 = Color3.fromRGB(20, 22, 28),
            
            		BackgroundTransparency = 0.1,
            
            		Visible = false,
            
            	}, gui)
            
            	new("UICorner", { CornerRadius = UDim.new(0, 10) }, panel)
            
            	new("UIListLayout", { Padding = UDim.new(0, 6), SortOrder = Enum.SortOrder.LayoutOrder }, panel)
            
            	new("UIPadding", {
            
            		PaddingTop = UDim.new(0, 8),
            
            		PaddingBottom = UDim.new(0, 8),
            
            		PaddingLeft = UDim.new(0, 8),
            
            		PaddingRight = UDim.new(0, 8),
            
            	}, panel)
            
            
            	local order = 0
            
            	local function addRow(class, props)
            
            		order += 1
            
            		props.LayoutOrder = order
            
            		props.Size = props.Size or UDim2.new(1, 0, 0, 30)
            
            		props.Font = Enum.Font.GothamMedium
            
            		props.TextSize = props.TextSize or 13
            
            		props.TextColor3 = props.TextColor3 or Color3.new(1, 1, 1)
            
            		props.TextWrapped = true
            
            		return new(class, props, panel)
            
            	end
            
            
            	local function request(action, payload)
            
            		local res = Net.Request():InvokeServer(action, payload)
            
            		explain(res)
            
            		return res
            
            	end
            
            
            	-- template UI3 (ReplicatedStorage): se existir, ele desenha o painel da torre; senão vale o painel abaixo
            
            	local unitPanel = UnitPanel.Init(gui, Render, request)
            
            
            	local function deselect()
            
            		selectedId = nil
            
            		panel.Visible = false
            
            		unitPanel.Hide()
            
            		if selectionRing then
            
            			selectionRing:Destroy()
            
            			selectionRing = nil
            
            		end
            
            	end
            
            
            	local function rebuild()
            
            		for _, c in ipairs(panel:GetChildren()) do
            
            			if c:IsA("GuiObject") then
            
            				c:Destroy()
            
            			end
            
            		end
            
            		order = 0
            
            		local t = selectedId and Render.Towers[selectedId]
            
            		if not t then
            
            			deselect()
            
            			return
            
            		end
            
            		panel.Visible = true
            
            		local cfg = t.Cfg
            
            		addRow("TextLabel", { Text = cfg.DisplayName or cfg.Id, BackgroundTransparency = 1, TextSize = 16 })
            
            
            		if selectionRing then
            
            			selectionRing:Destroy()
            
            			selectionRing = nil
            
            		end
            
            		if t.Range > 0 then
            
            			selectionRing = Render.MakeRing()
            
            			selectionRing.Parent = Render.Folder
            
            			Render.PlaceRing(selectionRing, t.Position, t.Range)
            
            		end
            
            
            		if unitPanel.Show(t) then
            
            			panel.Visible = false
            
            			return
            
            		end
            
            
            		if t.Owner ~= player.UserId then
            
            			addRow("TextLabel", { Text = "Torre de outro jogador", BackgroundTransparency = 1 })
            
            			return
            
            		end
            
            
            		for _, path in ipairs(cfg.Upgrades and cfg.Upgrades.Paths or {}) do
            
            			local tier = t.Tiers[path.Id] or 0
            
            			local nextDef = path.Tiers[tier + 1]
            
            			local text = nextDef
            
            				and ("%s [%d/%d]\n%s ($%d)\n%s"):format(
            
            					path.Name or path.Id,
            
            					tier,
            
            					#path.Tiers,
            
            					nextDef.Name or "Próximo",
            
            					math.ceil(nextDef.Cost * (Render.Map and Render.Map.Config.Multipliers.TowerCost or 1)),
            
            					nextDef.Description or ""
            
            				)
            
            				or ("%s [%d/%d] — MÁX"):format(path.Name or path.Id, tier, #path.Tiers)
            
            			local btn = addRow("TextButton", {
            
            				Text = text,
            
            				Size = UDim2.new(1, 0, 0, nextDef and 62 or 30),
            
            				BackgroundColor3 = nextDef and Color3.fromRGB(50, 90, 160) or Color3.fromRGB(60, 60, 60),
            
            				AutoButtonColor = nextDef ~= nil,
            
            				TextSize = 12,
            
            			})
            
            			new("UICorner", { CornerRadius = UDim.new(0, 6) }, btn)
            
            			if nextDef then
            
            				btn.Activated:Connect(function()
            
            					request("UpgradeTower", { TowerId = t.Id, PathId = path.Id })
            
            				end)
            
            			end
            
            		end
            
            
            		local modes = cfg.Targeting and cfg.Targeting.Modes
            
            		if modes and #modes > 1 then
            
            			local targeting = Registry.Of("Targeting")
            
            			local current = targeting:Get(t.Mode)
            
            			local btn = addRow("TextButton", {
            
            				Text = "Alvo: " .. (current and current.DisplayName or t.Mode),
            
            				BackgroundColor3 = Color3.fromRGB(70, 70, 90),
            
            			})
            
            			new("UICorner", { CornerRadius = UDim.new(0, 6) }, btn)
            
            			btn.Activated:Connect(function()
            
            				local idx = table.find(modes, t.Mode) or 0
            
            				request("SetTargeting", { TowerId = t.Id, Mode = modes[idx % #modes + 1] })
            
            			end)
            
            		end
            
            
            		local ratio = Render.Map and Render.Map.Config.Multipliers.SellRatio or 0.7
            
            		local sell = addRow("TextButton", {
            
            			Text = ("Vender (+$%d)"):format(math.floor(t.Invested * ratio)),
            
            			BackgroundColor3 = Color3.fromRGB(140, 50, 50),
            
            		})
            
            		new("UICorner", { CornerRadius = UDim.new(0, 6) }, sell)
            
            		sell.Activated:Connect(function()
            
            			request("SellTower", { TowerId = t.Id })
            
            		end)
            
            
            		local close = addRow("TextButton", { Text = "Fechar", BackgroundColor3 = Color3.fromRGB(50, 50, 50) })
            
            		new("UICorner", { CornerRadius = UDim.new(0, 6) }, close)
            
            		close.Activated:Connect(deselect)
            
            	end
            
            
            	Placement.OnSelect = function(id)
            
            		selectedId = id
            
            		rebuild()
            
            	end
            
            	Render.Events:Connect("TowerChanged", function(id)
            
            		if id == selectedId then
            
            			rebuild()
            
            		end
            
            	end)
            
            	Render.Events:Connect("TowerRemoved", function(id)
            
            		if id == selectedId then
            
            			deselect()
            
            		end
            
            	end)
            
            end
            
            
            return ShopUI
            
          SOURCE_END
        - UnitAnimator [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.UnitAnimator
          SOURCE_START
            --[[
            
            	UnitAnimator: animação PROCEDURAL para modelos com juntas (Motor6D/Weld).
            
            	O ClientRenderEngine ancora todas as partes, então Animator/AnimationTrack não movem nada: aqui as juntas são
            
            	resolvidas na mão (parte = pai * C0 * Transform * C1^-1, igual ao Motor6D) e aplicadas em lote com BulkMoveTo.
            
            	Quem manda no modelo é o animador: use :SetPivot(cf) em vez de Model:PivotTo.
            
            
            	API
            
            	  UnitAnimator.new(model, role)  -> animador (nil se o modelo não tiver PrimaryPart). role = "Enemy" | "Tower"
            
            	  :SetPivot(cf)   :SetSpeed(studsPorSegundo)   :Trigger("Attack")   :Kill()   :Step(dt)
            
            
            	Perfil de animação (Attribute "AnimProfile" no modelo; padrão: Walk p/ inimigo, Soldier p/ torre):
            
            	  Walk    ciclo de caminhada; a cadência acompanha a velocidade (congelado = pose parada)
            
            	  Soldier respiração em idle + braços para frente e coice quando atira (Trigger "Attack")
              -  Editar
  18:22:18.443  ========== END PART 11 ==========  -  Editar
  18:22:18.443   ▶  (x2)  -  Editar
  18:22:18.443  ========== PROJECT EXPORT PART 12 ==========  -  Editar
  18:22:18.444              	  Totem   juntas "OrbJoint" e "RingJoint" (orbe flutuando/girando)
            
            	Outros Attributes opcionais: CarryAngle (ângulo dos braços em idle no perfil Soldier).
            
            	As poses são indexadas pelo NOME da junta (Root Hip, Neck, Left/Right Shoulder, Left/Right Hip...).
            
            ]]
            
            local UnitAnimator = {}
            
            UnitAnimator.__index = UnitAnimator
            
            
            local IDENTITY = CFrame.new()
            
            -- segundos do Attack até o tiro sair (o Windup do servidor deve ser igual). Sobrescreva com Animation.ReleaseTime no config.
            
            local RELEASE_TIME = { Soldier = 0.08 }
            
            
            local function smooth(x)
            
            	x = math.clamp(x, 0, 1)
            
            	return x * x * (3 - 2 * x)
            
            end
            
            
            -- Rig R6: os quadros das juntas esquerda/direita são espelhados, então o MESMO ângulo nos dois lados alterna
            
            -- as pernas; nos ombros, +ângulo no direito e -ângulo no esquerdo levantam os dois braços para frente.
            
            local POSES = {}
            
            
            function POSES.Walk(self, dt, pose)
            
            	local moving = self.Speed > 0.05
            
            	self.Move += ((moving and 1 or 0) - self.Move) * math.min(dt * 10, 1)
            
            	self.Phase += dt * self.Speed * 0.75
            
            	local m, s, ph = self.Move, self.Scale, self.Phase
            
            	local swing = math.sin(ph) * 0.75 * m
            
            	pose["Right Hip"] = CFrame.Angles(0, 0, swing)
            
            	pose["Left Hip"] = CFrame.Angles(0, 0, swing)
            
            	pose["Right Shoulder"] = CFrame.Angles(0, 0, -swing * 0.8)
            
            	pose["Left Shoulder"] = CFrame.Angles(0, 0, -swing * 0.8)
            
            	pose["Root Hip"] = CFrame.new(0, math.abs(math.cos(ph)) * 0.18 * s * m, 0)
            
            		* CFrame.Angles(-0.06 * m, 0, math.sin(ph) * 0.04 * m)
            
            	pose["Neck"] = CFrame.Angles(0, math.sin(ph * 0.5) * 0.12 * m, 0)
            
            end
            
            
            function POSES.Soldier(self, dt, pose)
            
            	self.AttackT += dt
            
            	local at, t, s = self.AttackT, self.Time, self.Scale
            
            	-- braços sobem rápido, seguram e voltam; o corpo dá um coice logo no disparo
            
            	local raise = smooth(at / 0.08) * (1 - smooth((at - 0.35) / 0.6))
            
            	local recoil
            
            	if at < 0.1 then
            
            		recoil = at / 0.1
            
            	else
            
            		recoil = math.max(1 - (at - 0.1) / 0.35, 0)
            
            	end
            
            	local breathe = math.sin(t * 2.2)
            
            	local arm = self.Carry + (1.35 - self.Carry) * raise
            
            	pose["Right Shoulder"] = CFrame.Angles(0, 0, arm + breathe * 0.02)
            
            	pose["Left Shoulder"] = CFrame.Angles(0, 0, -arm - breathe * 0.02)
            
            	pose["Root Hip"] = CFrame.new(0, breathe * 0.04 * s, recoil * 0.5 * s) * CFrame.Angles(recoil * 0.12, 0, 0)
            
            	pose["Neck"] = CFrame.Angles(0, math.sin(t * 0.8) * 0.25 * (1 - raise), 0)
            
            end
            
            
            function POSES.Totem(self, dt, pose)
            
            	local t, s = self.Time, self.Scale
            
            	pose["OrbJoint"] = CFrame.new(0, math.sin(t * 2) * 0.3 * s, 0) * CFrame.Angles(0, t * 1.2, 0)
            
            	pose["RingJoint"] = CFrame.Angles(t * 1.5, 0, t * 0.5)
            
            end
            
            
            function UnitAnimator.new(model, role, cfg)
            
            	local root = model.PrimaryPart
            
            	if not root then
            
            		return nil
            
            	end
            
            
            	-- árvore de juntas a partir da raiz (Part0 = pai, Part1 = filho)
            
            	local kids = {}
            
            	for _, d in ipairs(model:GetDescendants()) do
            
            		if d:IsA("JointInstance") and d.Part0 and d.Part1 and d.Part1 ~= root then
            
            			local list = kids[d.Part0]
            
            			if not list then
            
            				list = {}
            
            				kids[d.Part0] = list
            
            			end
            
            			table.insert(list, { Part = d.Part1, C0 = d.C0, C1Inv = d.C1:Inverse(), Name = d.Name })
            
            		end
            
            	end
            
            
            	local order, seen = {}, { [root] = true }
            
            	local queue, qi = { root }, 1
            
            	while qi <= #queue do
            
            		local parent = queue[qi]
            
            		qi += 1
            
            		for _, j in ipairs(kids[parent] or {}) do
            
            			if not seen[j.Part] then
            
            				seen[j.Part] = true
            
            				j.Parent = parent
            
            				table.insert(order, j)
            
            				table.insert(queue, j.Part)
            
            			end
            
            		end
            
            	end
            
            	-- parte sem junta ligada à raiz: acompanha a raiz parada
            
            	for _, d in ipairs(model:GetDescendants()) do
            
            		if d:IsA("BasePart") and not seen[d] then
            
            			seen[d] = true
            
            			table.insert(order, {
            
            				Part = d,
            
            				Parent = root,
            
            				C0 = root.CFrame:ToObjectSpace(d.CFrame),
            
            				C1Inv = IDENTITY,
            
            				Name = "",
            
            			})
            
            		end
            
            	end
            
            
            	local parts = { root }
            
            	for i, j in ipairs(order) do
            
            		parts[i + 1] = j.Part
            
            	end
            
            
            	local role2 = role or "Tower"
            
            	local self = setmetatable({
            
            		Model = model,
            
            		Root = root,
            
            		Role = role2,
            
            		Profile = model:GetAttribute("AnimProfile") or (role2 == "Enemy" and "Walk" or "Soldier"),
            
            		Carry = model:GetAttribute("CarryAngle") or 0.2,
            
            		Order = order,
            
            		Parts = parts,
            
            		CFrames = {},
            
            		World = {},
            
            		Pose = {},
            
            		RootPivotInv = root.PivotOffset:Inverse(),
            
            		Pivot = model:GetPivot(),
            
            		Scale = model:GetScale(),
            
            		Time = math.random() * 6,
            
            		Speed = 0,
            
            		Move = 0,
            
            		Phase = 0,
            
            		AttackT = math.huge,
            
            		DeadT = nil,
            
            	}, UnitAnimator)
            
            	self.DeathTime = 0.5
            
            	self.ReleaseTime = cfg and cfg.Animation and cfg.Animation.ReleaseTime or RELEASE_TIME[self.Profile] or 0
            
            	self.PendingRelease = nil
            
            	return self
            
            end
            
            
            function UnitAnimator:SetPivot(cf)
            
            	self.Pivot = cf
            
            end
            
            
            function UnitAnimator:SetSpeed(speed)
            
            	self.Speed = speed
            
            end
            
            
            function UnitAnimator:_release()
            
            	local fn = self.PendingRelease
            
            	if fn then
            
            		self.PendingRelease = nil
            
            		fn()
            
            	end
            
            end
            
            
            -- onRelease (opcional): chamado no instante em que o projétil deve sair (no máximo uma vez)
            
            function UnitAnimator:Trigger(name, onRelease)
            
            	if name ~= "Attack" then
            
            		return
            
            	end
            
            	self:_release() -- solta o disparo anterior, se ainda estava pendente
            
            	self.AttackT = 0
            
            	if not onRelease then
            
            		return
            
            	end
            
            	if self.ReleaseTime > 0 then
            
            		self.PendingRelease = onRelease
            
            	else
            
            		onRelease()
            
            	end
            
            end
            
            
            function UnitAnimator:Kill()
            
            	if not self.DeadT then
            
            		self.DeadT = 0
            
            	end
            
            end
            
            
            function UnitAnimator:Step(dt)
            
            	self.Time += dt
            
            	local pose = self.Pose
            
            	table.clear(pose)
            
            
            	if self.DeadT then
            
            		self.DeadT += dt
            
            		local e = smooth(self.DeadT / 0.35)
            
            		pose["Right Shoulder"] = CFrame.Angles(0, 0, e * 2.6)
            
            		pose["Left Shoulder"] = CFrame.Angles(0, 0, -e * 2.6)
            
            	else
            
            		local fn = POSES[self.Profile] or POSES.Soldier
            
            		fn(self, dt, pose)
            
            	end
            
            
            	local pivot = self.Pivot
            
            	if self.DeadT then
            
            		local e = smooth(self.DeadT / 0.35)
            
            		pivot = pivot * CFrame.new(0, -0.4 * self.Scale * e, 0) * CFrame.Angles(-1.45 * e, 0, 0)
            
            	end
            
            
            	local world, cfs = self.World, self.CFrames
            
            	local rootCF = pivot * self.RootPivotInv
            
            	world[self.Root] = rootCF
            
            	cfs[1] = rootCF
            
            	for i, j in ipairs(self.Order) do
            
            		local cf = world[j.Parent] * j.C0 * (pose[j.Name] or IDENTITY) * j.C1Inv
            
            		world[j.Part] = cf
            
            		cfs[i + 1] = cf
            
            	end
            
            	workspace:BulkMoveTo(self.Parts, cfs, Enum.BulkMoveMode.FireCFrameChanged)
            
            
            	if self.PendingRelease and self.AttackT >= self.ReleaseTime then
            
            		self:_release()
            
            	end
            
            end
            
            
            return UnitAnimator
            
            
          SOURCE_END
        - UnitPanel [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.UnitPanel
          SOURCE_START
            --[[
            
            	UnitPanel: painel da torre selecionada, montado a partir do template UI3 (um Frame em ReplicatedStorage que
            
            	contém UpgradeTemplate, Upgrade1Box e Upgrade2Box). O mesmo template serve para TODAS as unidades:
            
            	  UnitIcon        ícone do config (cfg.Icon); sem ícone, mostra o modelo da unidade num ViewportFrame  -  Editar
  18:22:18.444  ========== END PART 12 ==========  -  Editar
  18:22:18.444   ▶  (x2)  -  Editar
  18:22:18.444  ========== PROJECT EXPORT PART 13 ==========  -  Editar
  18:22:18.444              
            	  Upgrade1/2      os dois primeiros caminhos de cfg.Upgrades.Paths: próximo nível + custo; clique = UpgradeTower
            
            	  Upgrade1Box/2Box  descrição do próximo nível (aparece ao passar o mouse; no toque: 1º toque mostra, 2º compra)
            
            	  Priority        modo de alvo atual; clique troca para o próximo (SetTargeting)
            
            	  Sell            mostra o valor de venda; clique = SellTower
            
            	  DMG / SPA / RNG dano, segundos por ataque e alcance atuais da torre
            
            	Sem o template no ReplicatedStorage, Show() devolve false e o ShopUI usa o painel antigo.
            
            
            	Opções (Attributes no Frame raiz do template):
            
            	  KeepPosition = true      não mexe na posição/âncora do Frame raiz (usa a que você desenhou)
            
            	  KeepBoxPositions = true  não mexe na posição de Upgrade1Box/Upgrade2Box
            
            ]]
            
            local Players = game:GetService("Players")
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            local UserInputService = game:GetService("UserInputService")
            
            
            local Shared = ReplicatedStorage:WaitForChild("Shared")
            
            local Registry = require(Shared.Registry)
            
            
            -- centro do painel principal (200x200) na tela; o grupo (com Stats/Priority/Sell à direita) fica no lado direito
            
            local PANEL_CENTER = UDim2.new(1, -228, 0.5, 0)
            
            
            local COLOR_POOR = Color3.fromRGB(200, 120, 0)
            
            local COLOR_OFF = Color3.fromRGB(110, 110, 110)
            
            
            local UnitPanel = {}
            
            
            local function findTemplate()
            
            	for _, c in ipairs(ReplicatedStorage:GetChildren()) do
            
            		if c:IsA("GuiObject") and c:FindFirstChild("UpgradeTemplate") and c:FindFirstChild("Upgrade1Box") then
            
            			return c
            
            		end
            
            	end
            
            	return nil
            
            end
            
            
            local function findModel(name)
            
            	if not name then
            
            		return nil
            
            	end
            
            	local assets = ReplicatedStorage:FindFirstChild("Assets")
            
            	local models = assets and assets:FindFirstChild("Models")
            
            	for _, root in ipairs({ models, assets }) do
            
            		local folder = root and root:FindFirstChild("Towers")
            
            		local m = folder and folder:FindFirstChild(name)
            
            		if m then
            
            			return m
            
            		end
            
            	end
            
            	return nil
            
            end
            
            
            local function fmt(n)
            
            	if not n or n <= 0 then
            
            		return "-"
            
            	end
            
            	if math.abs(n - math.round(n)) < 0.05 then
            
            		return tostring(math.round(n))
            
            	end
            
            	return ("%.1f"):format(n)
            
            end
            
            
            local function pathLocked(cfg, tiers, pathId, tier)
            
            	local rules = cfg.Upgrades and cfg.Upgrades.Rules
            
            	if rules and rules.SecondaryMaxTier and tier + 1 > rules.SecondaryMaxTier then
            
            		for _, other in ipairs(cfg.Upgrades.Paths) do
            
            			if other.Id ~= pathId and (tiers[other.Id] or 0) > rules.SecondaryMaxTier then
            
            				return true
            
            			end
            
            		end
            
            	end
            
            	return false
            
            end
            
            
            -- Init(gui, Render, request) -> { Show(t) -> bool, Hide() }
            
            -- request(action, payload) é o do ShopUI (chama o servidor e mostra o erro na tela)
            
            function UnitPanel.Init(gui, Render, request)
            
            	local touchMode = UserInputService.TouchEnabled and not UserInputService.MouseEnabled
            
            	local root, ui
            
            	local current -- entrada de Render.Towers mostrada agora
            
            	local armed -- toque: índice do upgrade "armado" (1º toque)
            
            	local iconFor -- cfg.Id do ícone atual (evita recriar o ViewportFrame a cada atualização)
            
            	local api = {}
            
            
            	local function showBox(i, on)
            
            		local slot = ui.Paths[i]
            
            		slot.Box.Visible = on and slot.HasInfo
            
            	end
            
            
            	local function hideBoxes()
            
            		for i = 1, #ui.Paths do
            
            			showBox(i, false)
            
            		end
            
            	end
            
            
            	local function setIcon(cfg)
            
            		if iconFor == cfg.Id then
            
            			return
            
            		end
            
            		iconFor = cfg.Id
            
            		if ui.Viewport then
            
            			ui.Viewport:Destroy()
            
            			ui.Viewport = nil
            
            		end
            
            		if cfg.Icon and cfg.Icon ~= "" then
            
            			ui.Icon.Image = cfg.Icon
            
            			return
            
            		end
            
            		local template = findModel(cfg.ModelName)
            
            		if not template then
            
            			ui.Icon.Image = ui.DefaultIcon
            
            			return
            
            		end
            
            		ui.Icon.Image = ""
            
            		local vp = Instance.new("ViewportFrame")
            
            		vp.Name = "ModelPreview"
            
            		vp.BackgroundTransparency = 1
            
            		vp.Size = UDim2.fromScale(1, 1)
            
            		vp.Ambient = Color3.fromRGB(190, 190, 190)
            
            		vp.LightColor = Color3.new(1, 1, 1)
            
            		vp.LightDirection = Vector3.new(-0.4, -1, -0.6)
            
            		local radius = 0
            
            		local m = template:Clone()
            
            		for _, d in ipairs(m:GetDescendants()) do
            
            			if d:IsA("BasePart") then
            
            				d.Anchored = true
            
            			end
            
            		end
            
            		m:PivotTo(CFrame.new())
            
            		local cf, size = m:GetBoundingBox()
            
            		radius = math.max(size.X, size.Y, size.Z)
            
            		local cam = Instance.new("Camera")
            
            		cam.FieldOfView = 40
            
            		local dist = radius * 0.5 / math.tan(math.rad(cam.FieldOfView / 2)) * 1.3
            
            		local center = cf.Position
            
            		-- o rig olha para -Z: a câmera fica na frente, um pouco à direita e acima
            
            		cam.CFrame = CFrame.lookAt(center + Vector3.new(dist * 0.35, size.Y * 0.1, -dist), center)
            
            		cam.Parent = vp
            
            		vp.CurrentCamera = cam
            
            		m.Parent = vp
            
            		vp.Parent = ui.Icon
            
            		ui.Viewport = vp
            
            	end
            
            
            	local function refresh()
            
            		local t = current
            
            		if not t or not root then
            
            			return
            
            		end
            
            		local cfg = t.Cfg
            
            		local mine = t.Owner == Players.LocalPlayer.UserId
            
            		setIcon(cfg)
            
            
            		ui.DMG.Text = fmt(t.Damage)
            
            		ui.SPA.Text = (t.Interval and t.Interval > 0) and (fmt(t.Interval) .. "s") or "-"
            
            		ui.RNG.Text = fmt(t.Range)
            
            
            		local paths = cfg.Upgrades and cfg.Upgrades.Paths or {}
            
            		local coins = Render.Data.Coins or 0
            
            		local costMult = Render.Map and Render.Map.Config.Multipliers.TowerCost or 1
            
            		for i, slot in ipairs(ui.Paths) do
            
            			local path = paths[i]
            
            			slot.Path = path
            
            			slot.Button.Visible = path ~= nil and mine
            
            			slot.HasInfo = false
            
            			if path then
            
            				local tier = t.Tiers[path.Id] or 0
            
            				local nextDef = path.Tiers[tier + 1]
            
            				local head = ("%s [%d/%d]"):format(path.Name or path.Id, tier, #path.Tiers)
            
            				if not nextDef then
            
            					slot.Name.Text = (path.Name or path.Id) .. "\nMÁX"
            
            					slot.Fill.BackgroundColor3 = COLOR_OFF
            
            					slot.Desc.Text = head .. "\nNível máximo"
            
            				else
            
            					local cost = math.ceil(nextDef.Cost * costMult)
            
            					local locked = pathLocked(cfg, t.Tiers, path.Id, tier)
            
            					slot.Name.Text = ("%s\n$%d"):format(nextDef.Name or "Próximo", cost)
            
            					slot.Fill.BackgroundColor3 = locked and COLOR_OFF or (coins >= cost and slot.ReadyColor or COLOR_POOR)
            
            					slot.Desc.Text = ("%s\n%s\n%s%s"):format(
            
            						head,
            
            						nextDef.Name or "",
            
            						nextDef.Description or "",
            
            						locked and "\n(bloqueado pelo outro caminho)" or ""
            
            					)
            
            				end
            
            				slot.HasInfo = true
            
            			end
            
            			slot.Box.Visible = false
            
            		end
            
            
            		local modes = cfg.Targeting and cfg.Targeting.Modes
            
            		local hasModes = mine and modes ~= nil and #modes > 1
            
            		ui.Priority.Visible = hasModes
            
            		if hasModes then
            
            			local def = Registry.Of("Targeting"):Get(t.Mode)
            
            			ui.PriorityText.Text = "Alvo: " .. (def and def.DisplayName or tostring(t.Mode))
            
            		end
            
            
            		ui.Sell.Visible = mine
            
            		local ratio = Render.Map and Render.Map.Config.Multipliers.SellRatio or 0.7
            
            		ui.SellText.Text = ("Vender $%d"):format(math.floor(t.Invested * ratio))
            
            	end
            
            
            	local function build()
            
            		if root then
            
            			return true
            
            		end
            
            		local template = findTemplate()
            
            		if not template then
            
            			return false
            
            		end
            
            		root = template:Clone()
            
            		root.Name = "UnitPanel"
            
            		root.Visible = false
            
            
            		local panel = root.UpgradeTemplate  -  Editar
  18:22:18.444  ========== END PART 13 ==========  -  Editar
  18:22:18.445   ▶  (x2)  -  Editar
  18:22:18.445  ========== PROJECT EXPORT PART 14 ==========  -  Editar
  18:22:18.446              
            		local box = { root.Upgrade1Box, root.Upgrade2Box }
            
            		ui = {
            
            			Icon = panel.UnitIcon,
            
            			DefaultIcon = panel.UnitIcon.Image,
            
            			Paths = {},
            
            			Priority = panel.PriorityAndSell.Priority,
            
            			PriorityText = panel.PriorityAndSell.Priority:FindFirstChildWhichIsA("TextLabel"),
            
            			Sell = panel.PriorityAndSell.Sell,
            
            			SellText = panel.PriorityAndSell.Sell:FindFirstChildWhichIsA("TextLabel"),
            
            			DMG = panel.Stats.DMG.DMGNUMBER,
            
            			SPA = panel.Stats.SPA.SPANUMBER,
            
            			RNG = panel.Stats.RNG.RNGNUMBER,
            
            		}
            
            		for i, name in ipairs({ "Upgrade1", "Upgrade2" }) do
            
            			local button = panel[name]
            
            			local fill = button.ImageLabel
            
            			ui.Paths[i] = {
            
            				Button = button,
            
            				Fill = fill,
            
            				Name = fill.UpgradeName,
            
            				ReadyColor = fill.BackgroundColor3,
            
            				Box = box[i],
            
            				Desc = box[i]:FindFirstChildWhichIsA("TextLabel"), -- "DescriçãoDoUpgrade"
            
            				HasInfo = false,
            
            			}
            
            			box[i].Visible = false
            
            		end
            
            
            		if not root:GetAttribute("KeepPosition") then
            
            			root.AnchorPoint = Vector2.new(0.5, 0.5)
            
            			root.Position = PANEL_CENTER
            
            		end
            
            		if not root:GetAttribute("KeepBoxPositions") then
            
            			-- acima do painel, alinhadas com o botão de cada upgrade (coordenadas relativas ao Frame raiz)
            
            			box[1].Position = UDim2.fromOffset(-50, -156)
            
            			box[2].Position = UDim2.fromOffset(50, -156)
            
            		end
            
            
            		for i, slot in ipairs(ui.Paths) do
            
            			slot.Button.MouseEnter:Connect(function()
            
            				showBox(i, true)
            
            			end)
            
            			slot.Button.MouseLeave:Connect(function()
            
            				if armed ~= i then
            
            					showBox(i, false)
            
            				end
            
            			end)
            
            			slot.Button.Activated:Connect(function()
            
            				local t = current
            
            				if not t or not slot.Path then
            
            					return
            
            				end
            
            				if touchMode and armed ~= i then
            
            					armed = i
            
            					hideBoxes()
            
            					showBox(i, true)
            
            					return
            
            				end
            
            				request("UpgradeTower", { TowerId = t.Id, PathId = slot.Path.Id })
            
            			end)
            
            		end
            
            
            		ui.Priority.Activated:Connect(function()
            
            			local t = current
            
            			local modes = t and t.Cfg.Targeting and t.Cfg.Targeting.Modes
            
            			if not modes or #modes < 2 then
            
            				return
            
            			end
            
            			local idx = table.find(modes, t.Mode) or 0
            
            			request("SetTargeting", { TowerId = t.Id, Mode = modes[idx % #modes + 1] })
            
            		end)
            
            
            		ui.Sell.Activated:Connect(function()
            
            			if current then
            
            				request("SellTower", { TowerId = current.Id })
            
            			end
            
            		end)
            
            
            		-- moedas mudaram: recolore os botões de upgrade (pode comprar / não pode)
            
            		Render.Events:Connect("PlayerData", function()
            
            			if current and root.Visible then
            
            				refresh()
            
            			end
            
            		end)
            
            
            		root.Parent = gui
            
            		return true
            
            	end
            
            
            	-- devolve true se o template existe e o painel foi mostrado (o ShopUI então não desenha o painel antigo)
            
            	function api.Show(t)
            
            		if not build() then
            
            			return false
            
            		end
            
            		current = t
            
            		armed = nil
            
            		root.Visible = true
            
            		refresh()
            
            		return true
            
            	end
            
            
            	function api.Hide()
            
            		current = nil
            
            		armed = nil
            
            		if root then
            
            			root.Visible = false
            
            			hideBoxes()
            
            		end
            
            	end
            
            
            	return api
            
            end
            
            
            return UnitPanel
            
            
          SOURCE_END
        - UnitIcon [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.UnitIcon
          SOURCE_START
            --[[
            
            	UnitIcon: põe a "imagem" de uma unidade num ImageLabel/ImageButton.
            
            	  cfg.Icon preenchido  -> usa a imagem do config
            
            	  senão, se existe o modelo (Assets.Models.Towers.<cfg.ModelName>) -> ViewportFrame com o modelo (o macaco)
            
            	  senão não mexe na imagem que já está no elemento
            
            	UnitIcon.Apply(target, cfg) -> ViewportFrame criado, ou nil
            
            ]]
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            
            local UnitIcon = {}
            
            
            local function findModel(name)
            
            	if not name then
            
            		return nil
            
            	end
            
            	local assets = ReplicatedStorage:FindFirstChild("Assets")
            
            	local models = assets and assets:FindFirstChild("Models")
            
            	for _, root in ipairs({ models, assets }) do
            
            		local folder = root and root:FindFirstChild("Towers")
            
            		local m = folder and folder:FindFirstChild(name)
            
            		if m then
            
            			return m
            
            		end
            
            	end
            
            	return nil
            
            end
            
            
            function UnitIcon.Apply(target, cfg)
            
            	local old = target:FindFirstChild("ModelPreview")
            
            	if old then
            
            		old:Destroy()
            
            	end
            
            	if cfg.Icon and cfg.Icon ~= "" then
            
            		target.Image = cfg.Icon
            
            		return nil
            
            	end
            
            	local template = findModel(cfg.ModelName)
            
            	if not template then
            
            		return nil
            
            	end
            
            	target.Image = ""
            
            
            	local vp = Instance.new("ViewportFrame")
            
            	vp.Name = "ModelPreview"
            
            	vp.BackgroundTransparency = 1
            
            	vp.Size = UDim2.fromScale(1, 1)
            
            	vp.ZIndex = target.ZIndex + 1
            
            	vp.Ambient = Color3.fromRGB(190, 190, 190)
            
            	vp.LightColor = Color3.new(1, 1, 1)
            
            	vp.LightDirection = Vector3.new(-0.4, -1, -0.6)
            
            	local corner = target:FindFirstChildOfClass("UICorner")
            
            	if corner then
            
            		local c = Instance.new("UICorner")
            
            		c.CornerRadius = corner.CornerRadius
            
            		c.Parent = vp
            
            	end
            
            
            	local m = template:Clone()
            
            	for _, d in ipairs(m:GetDescendants()) do
            
            		if d:IsA("BasePart") then
            
            			d.Anchored = true
            
            		end
            
            	end
            
            	m:PivotTo(CFrame.new())
            
            	local cf, size = m:GetBoundingBox()
            
            	local radius = math.max(size.X, size.Y, size.Z)
            
            	local cam = Instance.new("Camera")
            
            	cam.FieldOfView = 40
            
            	local dist = radius * 0.5 / math.tan(math.rad(cam.FieldOfView / 2)) * 1.3
            
            	local center = cf.Position
            
            	-- o rig olha para -Z: a câmera fica na frente, um pouco à direita e acima
            
            	cam.CFrame = CFrame.lookAt(center + Vector3.new(dist * 0.35, size.Y * 0.1, -dist), center)
            
            	cam.Parent = vp
            
            	vp.CurrentCamera = cam
            
            	m.Parent = vp
            
            	vp.Parent = target
            
            	return vp
            
            end
            
            
            return UnitIcon
            
            
          SOURCE_END
        - UnitCard [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.UnitCard
          SOURCE_START
            --[[
            
            	UnitCard: botão de COMPRAR/colocar unidade na loja (equipadas), montado a partir do template UIA
            
            	(um ImageButton em ReplicatedStorage com um TextLabel filho chamado PriceAndName). Serve para todas as unidades:
            
            	  imagem          cfg.Icon, ou o modelo da unidade (o macaco) num ViewportFrame
            
            	  PriceAndName    "Nome" e "$preço" (vermelho quando faltam moedas); o preço acompanha o multiplicador do mapa
            
            	O clique continua sendo ligado pelo ShopUI (Placement.Toggle). Sem o template, Make() devolve nil e o ShopUI
            
            	usa o card antigo.
            
            	UnitCard.Make(def, parent, order, Render) -> ImageButton ou nil
            
            ]]
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            
            local UnitIcon = require(script.Parent.UnitIcon)
            
            
            local COLOR_POOR = Color3.fromRGB(210, 40, 40)
            
            
            local UnitCard = {}
            
            
            local cards = {} -- [botão] = { Def, Label, ReadyColor }
            
            local renderRef
            
            local hooked = false
            
            
            local function findTemplate()
            
            	for _, c in ipairs(ReplicatedStorage:GetChildren()) do
            
            		if c:IsA("ImageButton") and c:FindFirstChild("PriceAndName") then
            
            			return c
            
            		end
            
            	end
            
            	return nil
            
            end
            
            
            local function update(entry)
              -  Editar
  18:22:18.446  ========== END PART 14 ==========  -  Editar
  18:22:18.446   ▶  (x2)  -  Editar
  18:22:18.447  ========== PROJECT EXPORT PART 15 ==========  -  Editar
  18:22:18.447              	local coins = renderRef.Data.Coins or 0
            
            	local cost = renderRef.TowerCost(entry.Def)
            
            	entry.Label.Text = ("%s\n$%d"):format(entry.Def.DisplayName or entry.Def.Id, cost)
            
            	entry.Label.TextColor3 = coins >= cost and entry.ReadyColor or COLOR_POOR
            
            end
            
            
            local function refreshAll()
            
            	for _, entry in pairs(cards) do
            
            		update(entry)
            
            	end
            
            end
            
            
            function UnitCard.Make(def, parent, order, Render)
            
            	local template = findTemplate()
            
            	if not template then
            
            		return nil
            
            	end
            
            	renderRef = Render
            
            	local button = template:Clone()
            
            	button.Name = def.Id
            
            	button.LayoutOrder = order
            
            	button.Visible = true
            
            
            	local label = button.PriceAndName
            
            	-- o layout da loja pode redimensionar o card: o rótulo acompanha em proporção (74x38 no template)
            
            	local h = template.Size.Y.Offset
            
            	if h > 0 then
            
            		label.Size = UDim2.fromScale(1, label.Size.Y.Offset / h)
            
            	end
            
            	label.ZIndex = button.ZIndex + 2 -- acima do ViewportFrame
            
            
            	UnitIcon.Apply(button, def)
            
            
            	local entry = { Def = def, Label = label, ReadyColor = label.TextColor3 }
            
            	cards[button] = entry
            
            	button.Destroying:Connect(function()
            
            		cards[button] = nil
            
            	end)
            
            	update(entry)
            
            
            	if not hooked then
            
            		hooked = true
            
            		Render.Events:Connect("PlayerData", refreshAll)
            
            		Render.Events:Connect("GameState", refreshAll)
            
            	end
            
            
            	button.Parent = parent
            
            	return button
            
            end
            
            
            return UnitCard
            
            
          SOURCE_END
        - ChatCommands [ModuleScript]
          PATH: game.StarterPlayer.StarterPlayerScripts.Client.ChatCommands
          SOURCE_START
            --[[
            
            	ChatCommands: comandos digitados no chat. O cliente só interpreta o texto e pede ao servidor (Requests);
            
            	a permissão é checada no servidor (Server/AdminCommands).
            
            	  /give <quantia> <jogador|me|all>   (também /dar). Sem jogador = você. Quantia aceita 1k, 2.5k, 1m.
            
            	Funciona com o chat novo (TextChatService) e, se o jogo estiver no chat antigo, via Player.Chatted.
            
            ]]
            
            local Players = game:GetService("Players")
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            local StarterGui = game:GetService("StarterGui")
            
            local TextChatService = game:GetService("TextChatService")
            
            
            local Net = require(ReplicatedStorage.Shared.Net)
            
            
            local ALIASES = { "/give", "/dar" }
            
            local USAGE = "Uso: /give <quantia> <jogador | me | all>   (ex.: /give 1000 NomeDoJogador)"
            
            local ERRORS = {
            
            	NotAuthorized = "Você não tem permissão para usar esse comando.",
            
            	BadAmount = "Quantia inválida: use um número inteiro de 1 a 1.000.000.000.",
            
            	BadRequest = USAGE,
            
            	PlayerNotFound = "Jogador não encontrado.",
            
            	AmbiguousPlayer = "Mais de um jogador combina; digite o nome completo.",
            
            	TargetNotReady = "Esse jogador ainda não tem moedas (não entrou na partida).",
            
            	RateLimited = "Calma! Muitas ações.",
            
            }
            
            
            local ChatCommands = {}
            
            
            local function say(text)
            
            	local ok = pcall(function()
            
            		local channels = TextChatService:FindFirstChild("TextChannels")
            
            		local system = channels and channels:FindFirstChild("RBXSystem")
            
            		assert(system, "sem canal de sistema")
            
            		system:DisplaySystemMessage(text)
            
            	end)
            
            	if not ok then
            
            		pcall(function()
            
            			StarterGui:SetCore("ChatMakeSystemMessage", { Text = text })
            
            		end)
            
            	end
            
            end
            
            
            -- "1000" -> 1000, "1k" -> 1000, "2.5k" -> 2500, "1m" -> 1000000
            
            local function parseAmount(token)
            
            	if not token then
            
            		return nil
            
            	end
            
            	local num, suffix = token:lower():match("^(%d+%.?%d*)([km]?)$")
            
            	if not num then
            
            		return nil
            
            	end
            
            	local n = tonumber(num)
            
            	if suffix == "k" then
            
            		n *= 1000
            
            	elseif suffix == "m" then
            
            		n *= 1000000
            
            	end
            
            	return math.floor(n + 0.5)
            
            end
            
            
            local function runGive(text)
            
            	local tokens = {}
            
            	for word in text:gmatch("%S+") do
            
            		table.insert(tokens, word)
            
            	end
            
            	local amount = parseAmount(tokens[2])
            
            	if not amount then
            
            		say(USAGE)
            
            		return
            
            	end
            
            	local ok, res = pcall(function()
            
            		return Net.Request():InvokeServer("AdminGive", { Amount = amount, Target = tokens[3] or "me" })
            
            	end)
            
            	if not ok or type(res) ~= "table" then
            
            		say("Falha ao falar com o servidor.")
            
            	elseif res.Ok then
            
            		say(("Você deu $%d para %s."):format(res.Amount, table.concat(res.Names, ", ")))
            
            	else
            
            		say(ERRORS[res.Error] or ("Erro: " .. tostring(res.Error)))
            
            	end
            
            end
            
            
            function ChatCommands.Init()
            
            	if TextChatService.ChatVersion == Enum.ChatVersion.TextChatService then
            
            		local cmd = Instance.new("TextChatCommand")
            
            		cmd.Name = "TDGiveCommand"
            
            		cmd.PrimaryAlias = ALIASES[1]
            
            		cmd.SecondaryAlias = ALIASES[2]
            
            		cmd.AutocompleteVisible = true
            
            		cmd.Triggered:Connect(function(_, text)
            
            			runGive(text)
            
            		end)
            
            		cmd.Parent = TextChatService
            
            	else
            
            		Players.LocalPlayer.Chatted:Connect(function(msg)
            
            			local first = msg:match("^(%S+)")
            
            			if first and table.find(ALIASES, first:lower()) then
            
            				runGive(msg)
            
            			end
            
            		end)
            
            	end
            
            end
            
            
            return ChatCommands
            
            
          SOURCE_END
  - StarterPack [StarterPack]
  - StarterGui [StarterGui]
    - MainUI [ScreenGui]
      - LocalScript [LocalScript]
        PATH: game.StarterGui.MainUI.LocalScript
        SOURCE_START
          -- Referências dos elementos da interface
          
          local mainUI = script.Parent
          
          
          local inventory = mainUI:WaitForChild("Inventory")
          
          local inventoryButton = mainUI:WaitForChild("InventoryButton")
          
          
          local itensFrame = inventory:WaitForChild("Itens")
          
          local unitsFrame = inventory:WaitForChild("Units")
          
          
          local itensButton = inventory:WaitForChild("ItensButton")
          
          local unitsButton = inventory:WaitForChild("UnitsButton")
          
          
          -- Configuração padrão inicial
          
          unitsFrame.Visible = true
          
          itensFrame.Visible = false
          
          
          -- 1. Botão do Inventário: Alterna (Toggle) a visibilidade do Inventory
          
          inventoryButton.MouseButton1Click:Connect(function()
          
          	inventory.Visible = not inventory.Visible
          
          end)
          
          
          -- 2. Botão 'Units': Deixa 'Units' visível e 'Itens' invisível
          
          unitsButton.MouseButton1Click:Connect(function()
          
          	unitsFrame.Visible = true
          
          	itensFrame.Visible = false
          
          end)
          
          
          -- 3. Botão 'Itens': Deixa 'Itens' visível e 'Units' invisível
          
          itensButton.MouseButton1Click:Connect(function()
          
          	itensFrame.Visible = true
          
          	unitsFrame.Visible = false
          
          end)
          
          
        SOURCE_END
      - Inventory [Frame]
        - Background [ImageLabel]
          - UICorner [UICorner]
          - UIGradient [UIGradient]
        - UICorner [UICorner]
        - UIStroke [UIStroke]
        - Units [ScrollingFrame]
          - UICorner [UICorner]
          - UIGridLayout [UIGridLayout]
        - Itens [ScrollingFrame]
          - UICorner [UICorner]
          - UIGridLayout [UIGridLayout]
        - ItensButton [ImageButton]
          - UIStroke [UIStroke]
          - UICorner [UICorner]
        - UnitsButton [ImageButton]
          - UIStroke [UIStroke]
          - UICorner [UICorner]
      - Units [Frame]
        - Background [ImageLabel]
          - UICorner [UICorner]
          - UIGridLayout [UIGridLayout]
      - InventoryButton [ImageButton]
        - UICorner [UICorner]
        - UIStroke [UIStroke]
  - CoreGui [CoreGui]
    - RobloxGui [ScreenGui]
      - ControlFrame [Frame]
        - BottomLeftControl [Frame]
        - BottomRightControl [Frame]
        - TopLeftControl [Frame]
    - TransformTempAdornments [Folder]
      - Rotation [Folder]
      - LineGrid [Folder]
    - ViewSelectorScreenGui [ScreenGui]
      - Panel [Frame]
        - Viewport [ViewportFrame]
          - EventReceiver [ImageButton]
          - Model [MeshPart]
            - pnp [MeshPart]
            - y [Part]
              - Mesh [FileMesh]
            - nnn [MeshPart]
            - npn [MeshPart]
            - pnn [MeshPart]
            - 0p0 [Decal]
            - z [Part]
              - Mesh [FileMesh]
            - 0n0 [Decal]
            - p00 [Decal]
            - 00n [Decal]
            - x [Part]
              - Mesh [FileMesh]
            - 00p [Decal]
            - nnp [MeshPart]
            - n00 [Decal]
            - npp [MeshPart]
            - ppp [MeshPart]
            - ppn [MeshPart]  -  Editar
  18:22:18.447  ========== END PART 15 ==========  -  Editar
  18:22:18.447   ▶  (x2)  -  Editar
  18:22:18.449  ========== PROJECT EXPORT PART 16 ==========  -  Editar
  18:22:18.449            - Camera [Camera]
        - ArrowButtons [Frame]
          - UpArrow [ImageButton]
          - RightArrow [ImageButton]
          - LeftArrow [ImageButton]
          - DownArrow [ImageButton]
        - X [TextLabel]
        - Y [TextLabel]
        - Z [TextLabel]
    - PlaceAnnotations [Folder]
      - PlaceAnnotationsGui [ScreenGui]
        - Wrapper [Frame]
          - StyleSheet [StyleLink]
          - Children [Frame]
            - Manager [Frame]
            - StyleLink [StyleLink]
          - FoundationCursorContainer [Frame]
        - StyleLink [StyleLink]
    - LightGuides [Folder]
    - DraggerUI [Folder]
    - PathEditFolder [Folder]
    - Gen3d [Folder]
      - Gen3dGui [ScreenGui]
        - Wrapper [Frame]
          - StyleSheet [StyleLink]
          - Children [Frame]
            - StyleLink [StyleLink]
          - FoundationCursorContainer [Frame]
        - StyleLink [StyleLink]
    - ImageLoader [ScreenGui]
    - RojoNotifications [ScreenGui]
      - Notifications [Frame]
        - Fullscreen [Frame]
        - Popups [Frame]
          - Layout [UIListLayout]
          - Padding [UIPadding]
    - RojoNotifications [ScreenGui]
      - Notifications [Frame]
        - Fullscreen [Frame]
        - Popups [Frame]
          - Layout [UIListLayout]
          - Padding [UIPadding]
  - LocalizationService [LocalizationService]
  - PolicyService [PolicyService]
  - Teleport Service [TeleportService]
  - JointsService [JointsService]
  - PhysicsService [PhysicsService]
  - BadgeService [BadgeService]
  - FriendService [FriendService]
  - InsertService [InsertService]
    - InsertionHash [StringValue]
  - GamePassService [GamePassService]
  - Debris [Debris]
  - CookiesService [CookiesService]
  - Selection [Selection]
  - UserInputService [UserInputService]
  - KeyboardService [KeyboardService]
  - MouseService [MouseService]
  - VRService [VRService]
  - ContextActionService [ContextActionService]
  - ScriptService [ScriptService]
  - AssetService [AssetService]
  - TouchInputService [TouchInputService]
  - BrowserService [BrowserService]
  - CaptureService [CaptureService]
  - AnalyticsService [AnalyticsService]
  - SlimContentProvider [SlimContentProvider]
  - Packages [Packages]
  - GuidRegistryService [GuidRegistryService]
  - PublishService [PublishService]
  - ChangeHistoryService [ChangeHistoryService]
  - LuaWebService [LuaWebService]
  - ProcessInstancePhysicsService [ProcessInstancePhysicsService]
  - ReplicatedStorage [ReplicatedStorage]
    - Frame [Frame]
      - UpgradeTemplate [ImageLabel]
        - UIStroke [UIStroke]
        - Upgrade1 [ImageButton]
          - ImageLabel [ImageLabel]
            - UIStroke [UIStroke]
            - UpgradeName [TextLabel]
        - Upgrade2 [ImageButton]
          - ImageLabel [ImageLabel]
            - UIStroke [UIStroke]
            - UpgradeName [TextLabel]
        - UnitIcon [ImageLabel]
          - UIStroke [UIStroke]
          - UICorner [UICorner]
        - PriorityAndSell [ImageLabel]
          - Priority [ImageButton]
            - Priority [TextLabel]
            - ImageLabel [ImageLabel]
            - UIStroke [UIStroke]
            - UICorner [UICorner]
          - Sell [ImageButton]
            - Sell [TextLabel]
            - ImageLabel [ImageLabel]
            - UIStroke [UIStroke]
            - UICorner [UICorner]
        - Stats [ImageLabel]
          - DMG [ImageLabel]
            - DMGNUMBER [TextLabel]
            - UIStroke [UIStroke]
          - SPA [ImageLabel]
            - SPANUMBER [TextLabel]
            - UIStroke [UIStroke]
          - RNG [ImageLabel]
            - RNGNUMBER [TextLabel]
            - UIStroke [UIStroke]
        - UICorner [UICorner]
      - Upgrade1Box [ImageLabel]
        - UIStroke [UIStroke]
        - UICorner [UICorner]
        - DescriçãoDoUpgrade [TextLabel]
      - Upgrade2Box [ImageLabel]
        - UIStroke [UIStroke]
        - UICorner [UICorner]
        - DescriçãoDoUpgrade [TextLabel]
    - MapSelection [Frame]
      - Main [ImageLabel]
        - UICorner [UICorner]
        - UIStroke [UIStroke]
        - Mapas [ScrollingFrame]
          - MapTemplate [ImageButton]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
            - MapIcon [ImageLabel]
              - UIStroke [UIStroke]
          - UIListLayout [UIListLayout]
          - MapTemplate [ImageButton]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
            - MapIcon [ImageLabel]
              - UIStroke [UIStroke]
          - MapTemplate [ImageButton]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
            - MapIcon [ImageLabel]
              - UIStroke [UIStroke]
        - Dificuldades [Frame]
          - UIListLayout [UIListLayout]
          - DificuldadeTemplate [ImageButton]
            - UIStroke [UIStroke]
            - UICorner [UICorner]
            - TextLabel [TextLabel]
          - DificuldadeTemplate [ImageButton]
            - UIStroke [UIStroke]
            - UICorner [UICorner]
            - TextLabel [TextLabel]
          - DificuldadeTemplate [ImageButton]
            - UIStroke [UIStroke]
            - UICorner [UICorner]
            - TextLabel [TextLabel]
          - DificuldadeTemplate [ImageButton]
            - UIStroke [UIStroke]
            - UICorner [UICorner]
            - TextLabel [TextLabel]
        - SelectedMapIcon [ImageLabel]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
        - Rewards [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - SelectedMapDifficultBanana [ImageLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
            - Coins [TextLabel]
            - CoinIcon [ImageLabel]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
          - UIListLayout [UIListLayout]
          - SelectedMapDifficultXP [ImageLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
            - XP [TextLabel]
            - XPIcon [ImageLabel]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
    - ImageButton [ImageButton]
      - UICorner [UICorner]
      - UIStroke [UIStroke]
      - PriceAndName [TextLabel]
        - UIStroke [UIStroke]
    - Assets [Folder]
      - Models [Folder]
        - Enemies [Folder]
          - Brute [Model]
            - MonkeyHat [Accessory]
              - Handle [Part]
                - HatAttachment [Attachment]
                - OriginalSize [Vector3Value]
                - Mesh [SpecialMesh]
                - TouchInterest [TouchTransmitter]
            - Monkey Tail [Accessory]
              - Handle [Part]
                - WaistFrontAttachment [Attachment]
                - Mesh [SpecialMesh]
                - OriginalSize [Vector3Value]
                - TouchInterest [TouchTransmitter]
            - Torso [Part]
              - Right Hip [Motor6D]
              - Right Shoulder [Motor6D]
              - Left Hip [Motor6D]
              - Left Shoulder [Motor6D]
              - Neck [Motor6D]
            - Right Leg [Part]
            - Right Arm [Part]
            - HumanoidRootPart [Part]
              - Root Hip [Motor6D]
            - Left Leg [Part]
            - Left Arm [Part]
            - Head [Part]
              - Mesh [SpecialMesh]
              - HeadWeld [Weld]
              - HeadWeld [Weld]
            - PadL [Part]
              - PadLJoint [Weld]
            - PadR [Part]
              - PadRJoint [Weld]
            - Belt [Part]
              - BeltJoint [Weld]
          - Grunt [Model]
            - MonkeyHat [Accessory]
              - Handle [Part]
                - HatAttachment [Attachment]
                - OriginalSize [Vector3Value]
                - Mesh [SpecialMesh]
                - TouchInterest [TouchTransmitter]
            - Monkey Tail [Accessory]
              - Handle [Part]
                - WaistFrontAttachment [Attachment]
                - Mesh [SpecialMesh]
                - OriginalSize [Vector3Value]
                - TouchInterest [TouchTransmitter]
            - Torso [Part]
              - Right Hip [Motor6D]
              - Right Shoulder [Motor6D]
              - Left Hip [Motor6D]
              - Left Shoulder [Motor6D]
              - Neck [Motor6D]
            - Right Leg [Part]
            - Right Arm [Part]
            - HumanoidRootPart [Part]
              - Root Hip [Motor6D]
            - Left Leg [Part]
            - Left Arm [Part]
            - Head [Part]
              - Mesh [SpecialMesh]
              - HeadWeld [Weld]
              - HeadWeld [Weld]
          - MiniGrunt [Model]
            - MonkeyHat [Accessory]
              - Handle [Part]
                - HatAttachment [Attachment]
                - OriginalSize [Vector3Value]
                - Mesh [SpecialMesh]
                - TouchInterest [TouchTransmitter]
            - Monkey Tail [Accessory]
              - Handle [Part]
                - WaistFrontAttachment [Attachment]
                - Mesh [SpecialMesh]
                - OriginalSize [Vector3Value]
                - TouchInterest [TouchTransmitter]
            - Torso [Part]
              - Right Hip [Motor6D]
              - Right Shoulder [Motor6D]
              - Left Hip [Motor6D]
              - Left Shoulder [Motor6D]
              - Neck [Motor6D]
            - Right Leg [Part]
            - Right Arm [Part]
            - HumanoidRootPart [Part]
              - Root Hip [Motor6D]
            - Left Leg [Part]
            - Left Arm [Part]
            - Head [Part]
              - Mesh [SpecialMesh]
              - HeadWeld [Weld]
              - HeadWeld [Weld]
          - Splitter [Model]
            - MonkeyHat [Accessory]
              - Handle [Part]
                - HatAttachment [Attachment]
                - OriginalSize [Vector3Value]
                - Mesh [SpecialMesh]
                - TouchInterest [TouchTransmitter]
            - Monkey Tail [Accessory]
              - Handle [Part]
                - WaistFrontAttachment [Attachment]
                - Mesh [SpecialMesh]
                - OriginalSize [Vector3Value]
                - TouchInterest [TouchTransmitter]
            - Torso [Part]
              - Right Hip [Motor6D]
              - Right Shoulder [Motor6D]
              - Left Hip [Motor6D]
              - Left Shoulder [Motor6D]
              - Neck [Motor6D]
            - Right Leg [Part]
            - Right Arm [Part]
            - HumanoidRootPart [Part]
              - Root Hip [Motor6D]
            - Left Leg [Part]
            - Left Arm [Part]
            - Head [Part]
              - Mesh [SpecialMesh]
              - HeadWeld [Weld]
              - HeadWeld [Weld]
            - Core [Part]
              - CoreJoint [Weld]
        - Projectiles [Folder]
          - CannonBall [Model]
            - Ball [Part]
            - Tracer [Part]
          - FrostShell [Model]
            - Core [Part]
            - SpikeX [Part]
            - SpikeY [Part]
            - SpikeZ [Part]
        - Towers [Folder]
          - Cannon [Model]
            - MonkeyHat [Accessory]
              - Handle [Part]
                - HatAttachment [Attachment]
                - OriginalSize [Vector3Value]
                - Mesh [SpecialMesh]
                - TouchInterest [TouchTransmitter]
            - Monkey Tail [Accessory]
              - Handle [Part]
                - WaistFrontAttachment [Attachment]
                - Mesh [SpecialMesh]
                - OriginalSize [Vector3Value]
                - TouchInterest [TouchTransmitter]
            - Torso [Part]
              - Right Hip [Motor6D]
              - Right Shoulder [Motor6D]
              - Left Hip [Motor6D]
              - Left Shoulder [Motor6D]
              - Neck [Motor6D]
            - Right Leg [Part]
            - Right Arm [Part]
            - HumanoidRootPart [Part]
              - Root Hip [Motor6D]
            - Left Leg [Part]  -  Editar
  18:22:18.450  ========== END PART 16 ==========  -  Editar
  18:22:18.450   ▶  (x2)  -  Editar
  18:22:18.451  ========== PROJECT EXPORT PART 17 ==========  -  Editar
  18:22:18.451              - Left Arm [Part]
            - Head [Part]
              - Mesh [SpecialMesh]
              - HeadWeld [Weld]
              - HeadWeld [Weld]
            - Barrel [Part]
              - BarrelJoint [Weld]
              - Muzzle [Attachment]
            - Band [Part]
              - BandJoint [Weld]
          - FrostMortar [Model]
            - MonkeyHat [Accessory]
              - Handle [Part]
                - HatAttachment [Attachment]
                - OriginalSize [Vector3Value]
                - Mesh [SpecialMesh]
                - TouchInterest [TouchTransmitter]
            - Monkey Tail [Accessory]
              - Handle [Part]
                - WaistFrontAttachment [Attachment]
                - Mesh [SpecialMesh]
                - OriginalSize [Vector3Value]
                - TouchInterest [TouchTransmitter]
            - Torso [Part]
              - Right Hip [Motor6D]
              - Right Shoulder [Motor6D]
              - Left Hip [Motor6D]
              - Left Shoulder [Motor6D]
              - Neck [Motor6D]
            - Right Leg [Part]
            - Right Arm [Part]
            - HumanoidRootPart [Part]
              - Root Hip [Motor6D]
            - Left Leg [Part]
            - Left Arm [Part]
            - Head [Part]
              - Mesh [SpecialMesh]
              - HeadWeld [Weld]
              - HeadWeld [Weld]
            - Tube [Part]
              - TubeJoint [Weld]
              - Muzzle [Attachment]
            - Rim [Part]
              - RimJoint [Weld]
            - Crystal1 [Part]
              - Crystal1Joint [Weld]
            - Crystal2 [Part]
              - Crystal2Joint [Weld]
          - SupportTotem [Model]
            - Base [Part]
            - Pillar [Part]
              - PillarJoint [Weld]
            - Cap [Part]
              - CapJoint [Weld]
            - Orb [Part]
              - OrbJoint [Weld]
            - Ring [Part]
              - RingJoint [Weld]
            - Rune1 [Part]
              - Rune1Joint [Weld]
            - Rune2 [Part]
              - Rune2Joint [Weld]
            - Rune3 [Part]
              - Rune3Joint [Weld]
      - Towers [Folder]
    - Configs [Folder]
      - EnemiesConfig [Folder]
        - Brute [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.EnemiesConfig.Brute
          SOURCE_START
            return {
            
            	Id = "Brute",
            
            	ModelName = "Brute",
            
            	DisplayName = "Bruto",
            
            	Health = 600,
            
            	Speed = 6,
            
            	Reward = 30,
            
            	LivesDamage = 3,
            
            	Tags = { "Ground" },
            
            	Immunities = { Status = { "Freeze" }, Damage = {} },
            
            	Visual = { Color = Color3.fromRGB(90, 90, 110), Size = Vector3.new(4, 5, 4) },
            
            	Spawn = { FromWave = 6, Weight = 3, Cost = 8 },
            
            	Passives = {
            
            		{ Id = "DamageReduction", Params = { Reduction = 0.30, DamageTypes = { "Physical" } } },
            
            	},
            
            }
            
            
          SOURCE_END
        - Grunt [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.EnemiesConfig.Grunt
          SOURCE_START
            return {
            
            	Id = "Grunt",
            
            	ModelName = "Grunt",
            
            	DisplayName = "Soldado",
            
            	Health = 50,
            
            	Speed = 9,
            
            	Reward = 8,
            
            	LivesDamage = 1,
            
            	Tags = { "Ground" },
            
            	Visual = { Color = Color3.fromRGB(200, 70, 70), Size = Vector3.new(2, 3, 2) },
            
            	-- O gerador de ondas procedural descobre inimigos sozinho lendo este bloco (sem Spawn = não sorteia).
            
            	Spawn = { FromWave = 1, Weight = 10, Cost = 1 },
            
            }
            
            
          SOURCE_END
        - MiniGrunt [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.EnemiesConfig.MiniGrunt
          SOURCE_START
            return {
            
            	Id = "MiniGrunt",
            
            	ModelName = "MiniGrunt",
            
            	DisplayName = "Soldadinho",
            
            	Health = 40,
            
            	Speed = 13,
            
            	Reward = 3,
            
            	LivesDamage = 1,
            
            	Tags = { "Ground" },
            
            	Visual = { Color = Color3.fromRGB(230, 130, 130), Size = Vector3.new(1.3, 2, 1.3) },
            
            	-- sem Spawn: só aparece como filhote do Splitter
            
            }
            
            
          SOURCE_END
        - Splitter [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.EnemiesConfig.Splitter
          SOURCE_START
            return {
            
            	Id = "Splitter",
            
            	ModelName = "Splitter",
            
            	DisplayName = "Divisor",
            
            	Health = 220,
            
            	Speed = 8,
            
            	Reward = 14,
            
            	LivesDamage = 2,
            
            	Tags = { "Ground" },
            
            	Visual = { Color = Color3.fromRGB(190, 90, 210), Size = Vector3.new(3, 3.5, 3) },
            
            	Spawn = { FromWave = 3, Weight = 5, Cost = 3 },
            
            	-- comportamento ao morrer = passiva com hook OnDeath
            
            	Passives = {
            
            		{ Id = "SplitOnDeath", Params = { EnemyId = "MiniGrunt", Count = 2, Spread = 2 } },
            
            	},
            
            }
            
            
          SOURCE_END
      - GameModesConfig [Folder]
        - Endless [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.GameModesConfig.Endless
          SOURCE_START
            return {
            
            	Id = "Endless",
            
            	DisplayName = "Infinito",
            
            	MapPool = nil, -- nil = qualquer mapa registrado em MapsConfig
            
            	MinPlayers = 1,
            
            	WaitingTime = 8,
            
            	IntermissionTime = 12,
            
            	VictoryWave = nil, -- nil = infinito; ex.: 40 para um modo com fim
            
            	Seed = 0,
            
            
            	-- Ondas manuais (opcional): [numeroDaOnda] = { grupos }. Se a onda não estiver aqui, usa o Generator.
            
            	Waves = {
            
            		Manual = {
            
            			[1] = { { EnemyId = "Grunt", Count = 8, Interval = 1.0 } },
            
            			[2] = { { EnemyId = "Grunt", Count = 12, Interval = 0.8 } },
            
            		},
            
            
            		-- Geração procedural por fórmula. Descobre sozinho todo inimigo com bloco `Spawn` em EnemiesConfig.
            
            		-- Spawn = { FromWave, Weight, Cost, BossEvery? }
            
            		Generator = function(wave, ctx)
            
            			local budget = 6 + (wave ^ 1.35) * 2.5
            
            			local pool = {}
            
            			local counts = {}
            
            			for _, id in ipairs(ctx.Enemies:Ids()) do
            
            				local def = ctx.Enemies:Get(id)
            
            				local s = def.Spawn
            
            				if s and wave >= (s.FromWave or 1) then
            
            					if s.BossEvery then
            
            						if wave % s.BossEvery == 0 then
            
            							counts[id] = math.max(1, wave // s.BossEvery)
            
            						end
            
            					else
            
            						table.insert(pool, { Id = id, Weight = s.Weight or 1, Cost = s.Cost or 1 })
            
            					end
            
            				end
            
            			end
            
            			while budget > 0 do
            
            				local affordable, total = {}, 0
            
            				for _, e in ipairs(pool) do
            
            					if e.Cost <= budget then
            
            						table.insert(affordable, e)
            
            						total += e.Weight
            
            					end
            
            				end
            
            				if #affordable == 0 then
            
            					break
            
            				end
            
            				local roll = ctx.Random:NextNumber() * total
            
            				local pick = affordable[#affordable]
            
            				for _, e in ipairs(affordable) do
            
            					roll -= e.Weight
            
            					if roll <= 0 then
            
            						pick = e
            
            						break
            
            					end
            
            				end
            
            				counts[pick.Id] = (counts[pick.Id] or 0) + 1
            
            				budget -= pick.Cost
            
            			end
            
            			local ids = {}
            
            			for id in pairs(counts) do
            
            				table.insert(ids, id)
            
            			end
            
            			table.sort(ids)
            
            			local groups = {}
            
            			local interval = math.clamp(1.1 - wave * 0.02, 0.25, 1.1)
            
            			for i, id in ipairs(ids) do
            
            				table.insert(groups, { EnemyId = id, Count = counts[id], Interval = interval, Delay = (i - 1) * 3 })
            
            			end
            
            			return groups
            
            		end,
            
            	},
            
            
            	HealthScale = function(wave)
            
            		return 1.07 ^ (wave - 1)
            
            	end,
            
            	WaveBonus = function(wave)
            
            		return 50 + wave * 10
            
            	end,
            
            }
            
            
          SOURCE_END
      - MapsConfig [Folder]
        - Meadow [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.MapsConfig.Meadow
          SOURCE_START
            return {
            
            	Id = "Meadow",
            
            	DisplayName = "Campina",
            
            	ModelName = nil, -- ServerStorage.Assets.Maps.<ModelName>; nil = terreno + estrada gerados automaticamente
            
            	GroundY = 0,
            
            	Paths = {
            
            		Main = {
            
            			Vector3.new(-70, 1, -60),
            
            			Vector3.new(-70, 1, 0),
            
            			Vector3.new(-10, 1, 0),
            
            			Vector3.new(-10, 1, 60),
            
            			Vector3.new(60, 1, 60),
            
            			Vector3.new(60, 1, -30),
            
            		},
            
            	},
            
            	DefaultPath = "Main",
            
            	Bounds = { Min = Vector3.new(-100, 0, -90), Max = Vector3.new(100, 0, 90) },
            
            	PathClearance = 6,
            
            	TowerSpacing = 4,
            
            	StartingCoins = 300,
            
            	StartingLives = 20,
            
            	Multipliers = { EnemyHealth = 1, EnemySpeed = 1, Reward = 1, TowerCost = 1, SellRatio = 0.7 },
            
            }
            
            
          SOURCE_END
      - StatusEffectsConfig [Folder]
        - Burn [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.StatusEffectsConfig.Burn
          SOURCE_START
            return {
            
            	Id = "Burn",
            
            	Tags = { "DoT", "Fire" },
              -  Editar
  18:22:18.451  ========== END PART 17 ==========  -  Editar
  18:22:18.451   ▶  (x2)  -  Editar
  18:22:18.451  ========== PROJECT EXPORT PART 18 ==========  -  Editar
  18:22:18.452              	Stacking = "Refresh", -- "Refresh" renova a duração | "Stack" soma stacks (até MaxStacks)
            
            	Defaults = { Duration = 4, TickInterval = 0.5, Potency = 4 }, -- Potency = dano por tick
            
            	Visual = { Color = Color3.fromRGB(255, 120, 30) },
            
            	OnApply = function(inst, enemy) end,
            
            	OnTick = function(inst, enemy)
            
            		enemy:TakeDamage(inst.Params.Potency * inst.Stacks, "Fire", inst.Source)
            
            	end,
            
            	OnRemove = function(inst, enemy, reason) end,
            
            }
            
            
          SOURCE_END
        - Freeze [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.StatusEffectsConfig.Freeze
          SOURCE_START
            return {
            
            	Id = "Freeze",
            
            	Tags = { "CC", "Ice" }, -- inimigos podem ser imunes ao id "Freeze" OU à tag "CC"
            
            	Stacking = "Refresh",
            
            	Defaults = { Duration = 1.5 },
            
            	ReapplyCooldown = 2.0, -- anti "freeze-lock": após terminar, não congela de novo por 2s
            
            	Visual = { Color = Color3.fromRGB(190, 235, 255) },
            
            	OnApply = function(inst, enemy)
            
            		enemy:SetSpeedModifier("Freeze", 0)
            
            	end,
            
            	OnRemove = function(inst, enemy)
            
            		enemy:SetSpeedModifier("Freeze", nil)
            
            	end,
            
            }
            
            
          SOURCE_END
        - Slow [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.StatusEffectsConfig.Slow
          SOURCE_START
            return {
            
            	Id = "Slow",
            
            	Tags = { "Debuff", "Ice" },
            
            	Stacking = "Refresh",
            
            	Defaults = { Duration = 3, Potency = 0.35 }, -- Potency = fração de velocidade removida
            
            	Visual = { Color = Color3.fromRGB(120, 190, 255) },
            
            	OnApply = function(inst, enemy)
            
            		enemy:SetSpeedModifier("Slow", 1 - inst.Params.Potency)
            
            	end,
            
            	OnRefresh = function(inst, enemy)
            
            		enemy:SetSpeedModifier("Slow", 1 - inst.Params.Potency)
            
            	end,
            
            	OnRemove = function(inst, enemy)
            
            		enemy:SetSpeedModifier("Slow", nil)
            
            	end,
            
            }
            
            
          SOURCE_END
      - TargetingConfig [Folder]
        - Closest [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.TargetingConfig.Closest
          SOURCE_START
            -- Score: quanto MAIOR, mais preferido. Novos modos = novo arquivo aqui; a UI e a Tower descobrem sozinhas.
            
            return {
            
            	Id = "Closest",
            
            	DisplayName = "Mais Próximo",
            
            	Score = function(enemy, tower, distSq)
            
            		return -distSq
            
            	end,
            
            }
            
            
          SOURCE_END
        - First [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.TargetingConfig.First
          SOURCE_START
            -- Score: quanto MAIOR, mais preferido. Novos modos = novo arquivo aqui; a UI e a Tower descobrem sozinhas.
            
            return {
            
            	Id = "First",
            
            	DisplayName = "Primeiro",
            
            	Score = function(enemy, tower, distSq)
            
            		return enemy.Distance
            
            	end,
            
            }
            
            
          SOURCE_END
        - Last [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.TargetingConfig.Last
          SOURCE_START
            -- Score: quanto MAIOR, mais preferido. Novos modos = novo arquivo aqui; a UI e a Tower descobrem sozinhas.
            
            return {
            
            	Id = "Last",
            
            	DisplayName = "Último",
            
            	Score = function(enemy, tower, distSq)
            
            		return -enemy.Distance
            
            	end,
            
            }
            
            
          SOURCE_END
        - Strongest [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.TargetingConfig.Strongest
          SOURCE_START
            -- Score: quanto MAIOR, mais preferido. Novos modos = novo arquivo aqui; a UI e a Tower descobrem sozinhas.
            
            return {
            
            	Id = "Strongest",
            
            	DisplayName = "Mais Forte",
            
            	Score = function(enemy, tower, distSq)
            
            		return enemy.Health
            
            	end,
            
            }
            
            
          SOURCE_END
        - Weakest [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.TargetingConfig.Weakest
          SOURCE_START
            -- Score: quanto MAIOR, mais preferido. Novos modos = novo arquivo aqui; a UI e a Tower descobrem sozinhas.
            
            return {
            
            	Id = "Weakest",
            
            	DisplayName = "Mais Fraco",
            
            	Score = function(enemy, tower, distSq)
            
            		return -enemy.Health
            
            	end,
            
            }
            
            
          SOURCE_END
      - TowersConfig [Folder]
        - Cannon [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.TowersConfig.Cannon
          SOURCE_START
            return {
            
            	Id = "Cannon",
            
            	ModelName = "Cannon",
            
            	DisplayName = "Canhão",
            
            	Description = "Dano físico consistente. Evolui para executor ou metralhadora.",
            
            	Icon = "",
            
            	Cost = 100,
            
            	Tags = { "Basic" },
            
            	TargetTags = { "Ground" },
            
            	Visual = {
            
            		Color = Color3.fromRGB(196, 140, 72),
            
            		Size = Vector3.new(3, 4, 3),
            
            		Projectile = { ModelName = "CannonBall", Color = Color3.fromRGB(60, 60, 60), Size = 0.7 },
            
            	},
            
            	Stats = { Damage = 24, DamageType = "Physical", Range = 24, Cooldown = 1.0, AttackSpeed = 1, ProjectileSpeed = 80, Windup = 0.08 },
            
            	Targeting = { Modes = { "First", "Last", "Strongest", "Weakest", "Closest" }, Default = "First" },
            
            	Effects = {},
            
            	Passives = {
            
            		{ Id = "RampingDamage", Params = { BonusPerStack = 0.08, MaxStacks = 8, ResetOnTargetChange = true } },
            
            	},
            
            	Upgrades = {
            
            		Rules = { SecondaryMaxTier = 2 },
            
            		Paths = {
            
            			{
            
            				Id = "Power",
            
            				Name = "Poder Bruto",
            
            				Tiers = {
            
            					{ Name = "Balas Pesadas", Cost = 90, Description = "+40% de dano", Modifiers = { Damage = { Mul = 1.4 } } },
            
            					{
            
            						Name = "Executor",
            
            						Cost = 220,
            
            						Description = "Triplica o dano em alvos abaixo de 15% de vida",
            
            						AddPassives = { { Id = "Executioner", Params = { HealthPercentage = 0.15, ExtraDamageMultiplier = 3.0 } } },
            
            					},
            
            					{ Name = "Artilharia", Cost = 650, Description = "Dano x2 e +4 de alcance", Modifiers = { Damage = { Mul = 2.0 }, Range = { Add = 4 } } },
            
            				},
            
            			},
            
            			{
            
            				Id = "Speed",
            
            				Name = "Cadência",
            
            				Tiers = {
            
            					{ Name = "Gatilho Leve", Cost = 80, Description = "+25% de velocidade de ataque", Modifiers = { AttackSpeed = { Mul = 1.25 } } },
            
            					{ Name = "Mira Longa", Cost = 160, Description = "+5 de alcance", Modifiers = { Range = { Add = 5 } } },
            
            					{
            
            						Name = "Munição Incendiária",
            
            						Cost = 500,
            
            						Description = "Os disparos causam queimadura",
            
            						AddEffects = { { Id = "Burn", Params = { Potency = 6, Duration = 4 } } },
            
            					},
            
            				},
            
            			},
            
            		},
            
            	},
            
            }
            
            
          SOURCE_END
        - FrostMortar [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.TowersConfig.FrostMortar
          SOURCE_START
            return {
            
            	Id = "FrostMortar",
            
            	ModelName = "FrostMortar",
            
            	DisplayName = "Morteiro Glacial",
            
            	Description = "Explosão de gelo em área: desacelera e às vezes congela.",
            
            	Icon = "",
            
            	Cost = 275,
            
            	Tags = { "Ice", "Splash" },
            
            	TargetTags = { "Ground" },
            
            	Visual = {
            
            		Color = Color3.fromRGB(110, 200, 255),
            
            		Size = Vector3.new(3.5, 3, 3.5),
            
            		Projectile = { ModelName = "FrostShell", Color = Color3.fromRGB(170, 235, 255), Size = 1.2, Arc = 8 },
            
            	},
            
            	Stats = {
            
            		Damage = 9,
            
            		DamageType = "Ice",
            
            		Range = 30,
            
            		Cooldown = 2.0,
            
            		AttackSpeed = 1,
            
            		ProjectileSpeed = 40,
            
            		SplashRadius = 9,
            
            		Windup = 0.08,
            
            	},
            
            	Targeting = { Modes = { "First", "Strongest", "Closest" }, Default = "First" },
            
            	Effects = {
            
            		{ Id = "Slow", Params = { Potency = 0.4, Duration = 3 } },
            
            		{ Id = "Freeze", Chance = 0.25, Params = { Duration = 1.5 } },
            
            	},
            
            	Passives = {},
            
            	Upgrades = {
            
            		Rules = { SecondaryMaxTier = 2 },
            
            		Paths = {
            
            			{
            
            				Id = "Area",
            
            				Name = "Explosão",
            
            				Tiers = {
            
            					{ Name = "Estilhaços", Cost = 150, Description = "+3 de raio", Modifiers = { SplashRadius = { Add = 3 } } },
            
            					{ Name = "Nevasca", Cost = 350, Description = "+6 de raio e +30% de dano", Modifiers = { SplashRadius = { Add = 6 }, Damage = { Mul = 1.3 } } },
            
            				},
            
            			},
            
            			{
            
            				Id = "Freeze",
            
            				Name = "Congelamento",
            
            				Tiers = {
            
            					{
            
            						Name = "Geada Profunda",
            
            						Cost = 200,
            
            						Description = "45% de chance de congelar por 2s",  -  Editar
  18:22:18.452  ========== END PART 18 ==========  -  Editar
  18:22:18.452   ▶  (x2)  -  Editar
  18:22:18.452  ========== PROJECT EXPORT PART 19 ==========  -  Editar
  18:22:18.452              
            						AddEffects = { { Id = "Freeze", Chance = 0.45, Params = { Duration = 2 } } },
            
            					},
            
            					{
            
            						Name = "Zero Absoluto",
            
            						Cost = 550,
            
            						Description = "70% de chance de congelar por 2.5s",
            
            						AddEffects = { { Id = "Freeze", Chance = 0.7, Params = { Duration = 2.5 } } },
            
            					},
            
            				},
            
            			},
            
            		},
            
            	},
            
            }
            
            
          SOURCE_END
        - SupportTotem [ModuleScript]
          PATH: game.ReplicatedStorage.Configs.TowersConfig.SupportTotem
          SOURCE_START
            return {
            
            	Id = "SupportTotem",
            
            	ModelName = "SupportTotem",
            
            	DisplayName = "Totem de Suporte",
            
            	Description = "Aumenta alcance e dano das torres aliadas próximas.",
            
            	Icon = "",
            
            	Cost = 250,
            
            	Tags = { "Support" },
            
            	Visual = { Color = Color3.fromRGB(120, 220, 120), Size = Vector3.new(2, 6, 2) },
            
            	Stats = {}, -- sem ataque próprio (sem Range/Cooldown => a Tower não tenta atacar)
            
            	Effects = {},
            
            	Passives = {
            
            		{ Id = "SupportAura", Params = { Radius = 18, RangeBonus = 0.20, DamageBonus = 0.15 } },
            
            	},
            
            	Upgrades = {
            
            		Paths = {
            
            			{
            
            				Id = "Reach",
            
            				Name = "Alcance da Aura",
            
            				Tiers = {
            
            					{ Name = "Aura Ampla", Cost = 200, Description = "Raio 26", PassiveParams = { SupportAura = { Radius = 26 } } },
            
            					{ Name = "Aura Vasta", Cost = 450, Description = "Raio 36 e +30% de alcance", PassiveParams = { SupportAura = { Radius = 36, RangeBonus = 0.30 } } },
            
            				},
            
            			},
            
            			{
            
            				Id = "Power",
            
            				Name = "Bênção",
            
            				Tiers = {
            
            					{ Name = "Bênção Menor", Cost = 250, Description = "+30% de dano às torres", PassiveParams = { SupportAura = { DamageBonus = 0.30 } } },
            
            					{ Name = "Bênção Maior", Cost = 600, Description = "+50% dano e +15% cadência", PassiveParams = { SupportAura = { DamageBonus = 0.50, AttackSpeedBonus = 0.15 } } },
            
            				},
            
            			},
            
            		},
            
            	},
            
            }
            
            
          SOURCE_END
    - Shared [Folder]
      - EventBus [ModuleScript]
        PATH: game.ReplicatedStorage.Shared.EventBus
        SOURCE_START
          --[[
          
          	EventBus (Observer). Cada entidade (Tower, Enemy) tem o seu próprio Bus; EventBus.Global liga os sistemas.
          
          	- Connect(evento, fn, prioridade)  menor prioridade roda primeiro (empate: ordem de conexão)
          
          	- Fire(evento, ...)                handlers são isolados com pcall (uma passiva quebrada não derruba o jogo)
          
          	- Has(evento)                      permite pular o Fire quando ninguém escuta (barato em hooks de frame)
          
          	Listas de handlers são copy-on-write: conectar/desconectar durante um Fire é seguro.
          
          	Os nomes de evento são livres: qualquer módulo pode disparar/assinar hooks novos.
          
          ]]
          
          
          local EventBus = {}
          
          EventBus.__index = EventBus
          
          
          local Connection = {}
          
          Connection.__index = Connection
          
          
          function Connection:Disconnect()
          
          	if not self.Connected then
          
          		return
          
          	end
          
          	self.Connected = false
          
          	self.Bus:_remove(self)
          
          end
          
          
          local function byPriority(a, b)
          
          	if a.Priority ~= b.Priority then
          
          		return a.Priority < b.Priority
          
          	end
          
          	return a.Seq < b.Seq
          
          end
          
          
          function EventBus.new()
          
          	return setmetatable({ _handlers = {}, _seq = 0 }, EventBus)
          
          end
          
          
          function EventBus:Connect(event, fn, priority)
          
          	self._seq += 1
          
          	local conn = setmetatable({
          
          		Fn = fn,
          
          		Priority = priority or 0,
          
          		Seq = self._seq,
          
          		Event = event,
          
          		Bus = self,
          
          		Connected = true,
          
          	}, Connection)
          
          	local old = self._handlers[event]
          
          	local list = old and table.clone(old) or {}
          
          	table.insert(list, conn)
          
          	table.sort(list, byPriority)
          
          	self._handlers[event] = list
          
          	return conn
          
          end
          
          
          function EventBus:_remove(conn)
          
          	local list = self._handlers[conn.Event]
          
          	if not list then
          
          		return
          
          	end
          
          	local new = {}
          
          	for _, c in ipairs(list) do
          
          		if c ~= conn then
          
          			table.insert(new, c)
          
          		end
          
          	end
          
          	self._handlers[conn.Event] = #new > 0 and new or nil
          
          end
          
          
          function EventBus:Has(event)
          
          	return self._handlers[event] ~= nil
          
          end
          
          
          function EventBus:Fire(event, ...)
          
          	local list = self._handlers[event]
          
          	if not list then
          
          		return
          
          	end
          
          	for i = 1, #list do
          
          		local conn = list[i]
          
          		if conn.Connected then
          
          			local ok, err = pcall(conn.Fn, ...)
          
          			if not ok then
          
          				warn(("[EventBus] erro no handler de '%s': %s"):format(event, tostring(err)))
          
          			end
          
          		end
          
          	end
          
          end
          
          
          function EventBus:Destroy()
          
          	for _, list in pairs(self._handlers) do
          
          		for _, c in ipairs(list) do
          
          			c.Connected = false
          
          		end
          
          	end
          
          	table.clear(self._handlers)
          
          end
          
          
          EventBus.Global = EventBus.new()
          
          
          return EventBus
          
          
        SOURCE_END
      - Net [ModuleScript]
        PATH: game.ReplicatedStorage.Shared.Net
        SOURCE_START
          --[[
          
          	Rede. O servidor cria os remotes; o cliente espera por eles.
          
          	  Delta       (S->C) pacote em lote a 20 Hz: spawns, mudanças de movimento, vida, status, torres, tiros
          
          	  GameState   (S->C) estado da partida
          
          	  PlayerData  (S->C) moedas do jogador
          
          	  Notify      (S->C) mensagens
          
          	  Request     (C->S) RemoteFunction única com roteador de ações (ver Server/Requests)
          
          	Eventos novos são criados sob demanda no servidor (Net.Event("Nome")).
          
          ]]
          
          local RunService = game:GetService("RunService")
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          
          local IS_SERVER = RunService:IsServer()
          
          local PRECREATE = { "Delta", "GameState", "PlayerData", "Notify", "Loadout" }
          
          
          local Net = {}
          
          local folder, request
          
          local events = {}
          
          
          function Net.Init()
          
          	if folder then
          
          		return
          
          	end
          
          	if IS_SERVER then
          
          		folder = Instance.new("Folder")
          
          		folder.Name = "Remotes"
          
          		request = Instance.new("RemoteFunction")
          
          		request.Name = "Request"
          
          		request.Parent = folder
          
          		folder.Parent = ReplicatedStorage
          
          		for _, name in ipairs(PRECREATE) do
          
          			Net.Event(name)
          
          		end
          
          	else
          
          		folder = ReplicatedStorage:WaitForChild("Remotes")
          
          		request = folder:WaitForChild("Request")
          
          	end
          
          end
          
          
          function Net.Event(name)
          
          	local e = events[name]
          
          	if e then
          
          		return e
          
          	end
          
          	if IS_SERVER then
          
          		e = Instance.new("RemoteEvent")
          
          		e.Name = name
          
          		e.Parent = folder
          
          	else
          
          		e = folder:WaitForChild(name)
          
          	end
          
          	events[name] = e
          
          	return e
          
          end
          
          
          function Net.Request()
          
          	return request
          
          end
          
          
          return Net
          
          
        SOURCE_END
      - PathUtil [ModuleScript]
        PATH: game.ReplicatedStorage.Shared.PathUtil
        SOURCE_START
          --[[ Caminho (polilinha) com comprimento acumulado. Servidor usa para lógica, cliente para render. ]]
          
          local PathUtil = {}
          
          PathUtil.__index = PathUtil
          
          
          function PathUtil.new(points)
          
          	assert(#points >= 2, "[PathUtil] um caminho precisa de pelo menos 2 waypoints")
          
          	local cum = { 0 }
          
          	for i = 2, #points do
          
          		cum[i] = cum[i - 1] + (points[i] - points[i - 1]).Magnitude
          
          	end
          
          	return setmetatable({ Points = points, Cum = cum, Length = cum[#points] }, PathUtil)
          
          end
          
          
          -- devolve (índiceA, índiceB, t) do segmento que contém a distância percorrida (busca binária)
          
          function PathUtil:_segment(dist)
          
          	local pts, cum = self.Points, self.Cum
          
          	if dist <= 0 then
          
          		return 1, 2, 0
          
          	end
          
          	if dist >= self.Length then
          
          		return #pts - 1, #pts, 1
          
          	end
          
          	local lo, hi = 1, #pts
          
          	while hi - lo > 1 do
          
          		local mid = (lo + hi) // 2
          
          		if cum[mid] <= dist then
          
          			lo = mid
          
          		else
          
          			hi = mid
          
          		end
          
          	end
          
          	local segLen = cum[hi] - cum[lo]
          
          	return lo, hi, segLen > 0 and (dist - cum[lo]) / segLen or 0  -  Editar
  18:22:18.453  ========== END PART 19 ==========  -  Editar
  18:22:18.453   ▶  (x2)  -  Editar
  18:22:18.453  ========== PROJECT EXPORT PART 20 ==========  -  Editar
  18:22:18.453            
          end
          
          
          function PathUtil:PositionAt(dist)
          
          	local lo, hi, t = self:_segment(dist)
          
          	return self.Points[lo]:Lerp(self.Points[hi], t)
          
          end
          
          
          function PathUtil:DirectionAt(dist)
          
          	local lo, hi = self:_segment(dist)
          
          	local d = self.Points[hi] - self.Points[lo]
          
          	if d.Magnitude < 1e-4 then
          
          		return Vector3.new(0, 0, 1)
          
          	end
          
          	return d.Unit
          
          end
          
          
          -- distância 2D (XZ) de um ponto até o caminho
          
          function PathUtil:DistanceTo(point)
          
          	local best = math.huge
          
          	local px, pz = point.X, point.Z
          
          	local pts = self.Points
          
          	for i = 1, #pts - 1 do
          
          		local a, b = pts[i], pts[i + 1]
          
          		local abx, abz = b.X - a.X, b.Z - a.Z
          
          		local len2 = abx * abx + abz * abz
          
          		local t = 0
          
          		if len2 > 0 then
          
          			t = math.clamp(((px - a.X) * abx + (pz - a.Z) * abz) / len2, 0, 1)
          
          		end
          
          		local dx, dz = px - (a.X + abx * t), pz - (a.Z + abz * t)
          
          		local d = math.sqrt(dx * dx + dz * dz)
          
          		if d < best then
          
          			best = d
          
          		end
          
          	end
          
          	return best
          
          end
          
          
          return PathUtil
          
          
        SOURCE_END
      - PlacementRules [ModuleScript]
        PATH: game.ReplicatedStorage.Shared.PlacementRules
        SOURCE_START
          --[[
          
          	Regras de posicionamento compartilhadas: o servidor decide (autoridade), o cliente só usa para o "fantasma" verde/vermelho.
          
          	map    = { Config = <MapsConfig entry>, Paths = { [id] = PathUtil } }
          
          	towers = tabela (dict ou array) de objetos com .Position
          
          ]]
          
          local PlacementRules = {}
          
          
          function PlacementRules.Check(map, pos, towers)
          
          	local cfg = map.Config
          
          	local b = cfg.Bounds
          
          	if b and (pos.X < b.Min.X or pos.X > b.Max.X or pos.Z < b.Min.Z or pos.Z > b.Max.Z) then
          
          		return false, "OutOfBounds"
          
          	end
          
          	local clearance = cfg.PathClearance or 6
          
          	for _, path in pairs(map.Paths) do
          
          		if path:DistanceTo(pos) < clearance then
          
          			return false, "TooCloseToPath"
          
          		end
          
          	end
          
          	local spacing = cfg.TowerSpacing or 4
          
          	local s2 = spacing * spacing
          
          	for _, t in pairs(towers) do
          
          		local dx, dz = t.Position.X - pos.X, t.Position.Z - pos.Z
          
          		if dx * dx + dz * dz < s2 then
          
          			return false, "TooCloseToTower"
          
          		end
          
          	end
          
          	return true
          
          end
          
          
          return PlacementRules
          
          
        SOURCE_END
      - Registry [ModuleScript]
        PATH: game.ReplicatedStorage.Shared.Registry
        SOURCE_START
          --[[
          
          	Registry + Auto-Loader
          
          	----------------------
          
          	Registry.Create("Towers") / Registry.Of("Towers")
          
          	registry:LoadFolder(folder)  -> registra todo ModuleScript da pasta (subpastas incluídas e os adicionados depois).
          
          	  Um módulo pode retornar UMA definição ({ Id = "X", ... }) ou UMA LISTA de definições ({ {Id=..}, {Id=..} }),
          
          	  então "adicionar um registro numa tabela" também funciona.
          
          	Registry.AutoLoadConfigs(root) -> cada subpasta "<Nome>Config" vira o registro "<Nome>" automaticamente.
          
          	  Ex.: TowersConfig -> Registry.Of("Towers"). Criar uma pasta "SkinsConfig" cria o registro "Skins" sem tocar em código.
          
          	registry:OnRegister(fn) -> chama fn para as definições existentes E para as futuras (usado pela UI generativa).
          
          ]]
          
          
          local Registry = {}
          
          Registry.__index = Registry
          
          
          local all = {}
          
          
          function Registry.Create(name)
          
          	local existing = all[name]
          
          	if existing then
          
          		return existing
          
          	end
          
          	local self = setmetatable({ Name = name, Entries = {}, Order = {}, _listeners = {}, _loaded = {} }, Registry)
          
          	all[name] = self
          
          	return self
          
          end
          
          
          function Registry.Of(name)
          
          	local r = all[name]
          
          	assert(r, ("[Registry] o registro '%s' não existe (falta a pasta %sConfig?)"):format(name, name))
          
          	return r
          
          end
          
          
          function Registry.Exists(name)
          
          	return all[name] ~= nil
          
          end
          
          
          function Registry:Register(id, def)
          
          	assert(type(def) == "table", ("[Registry:%s] '%s' precisa ser uma tabela"):format(self.Name, tostring(id)))
          
          	if self.Entries[id] == nil then
          
          		table.insert(self.Order, id)
          
          	else
          
          		warn(("[Registry:%s] id duplicado '%s' (sobrescrevendo)"):format(self.Name, id))
          
          	end
          
          	def.Id = def.Id or id
          
          	self.Entries[id] = def
          
          	for _, fn in ipairs(self._listeners) do
          
          		task.spawn(fn, def)
          
          	end
          
          	return def
          
          end
          
          
          function Registry:Get(id)
          
          	return self.Entries[id]
          
          end
          
          
          function Registry:Require(id)
          
          	local def = self.Entries[id]
          
          	assert(def, ("[Registry:%s] id '%s' não registrado"):format(self.Name, tostring(id)))
          
          	return def
          
          end
          
          
          function Registry:All()
          
          	return self.Entries
          
          end
          
          
          function Registry:Ids()
          
          	local ids = table.clone(self.Order)
          
          	table.sort(ids)
          
          	return ids
          
          end
          
          
          function Registry:OnRegister(fn)
          
          	table.insert(self._listeners, fn)
          
          	for _, id in ipairs(table.clone(self.Order)) do
          
          		task.spawn(fn, self.Entries[id])
          
          	end
          
          end
          
          
          function Registry:_loadModule(module)
          
          	if self._loaded[module] then
          
          		return
          
          	end
          
          	self._loaded[module] = true
          
          	local ok, result = pcall(require, module)
          
          	if not ok then
          
          		warn(("[Registry:%s] erro ao carregar %s: %s"):format(self.Name, module:GetFullName(), tostring(result)))
          
          		return
          
          	end
          
          	if type(result) ~= "table" then
          
          		warn(("[Registry:%s] %s deve retornar uma tabela"):format(self.Name, module:GetFullName()))
          
          		return
          
          	end
          
          	if result[1] ~= nil then
          
          		for _, def in ipairs(result) do
          
          			self:Register(def.Id or module.Name, def)
          
          		end
          
          	else
          
          		self:Register(result.Id or module.Name, result)
          
          	end
          
          end
          
          
          function Registry:LoadFolder(folder)
          
          	local function scan(inst)
          
          		for _, child in ipairs(inst:GetChildren()) do
          
          			if child:IsA("ModuleScript") then
          
          				self:_loadModule(child)
          
          			elseif child:IsA("Folder") then
          
          				scan(child)
          
          			end
          
          		end
          
          	end
          
          	scan(folder)
          
          	-- hot-add: módulos criados depois (Studio, plugins, streaming) entram sozinhos
          
          	folder.DescendantAdded:Connect(function(d)
          
          		if d:IsA("ModuleScript") then
          
          			task.defer(function()
          
          				self:_loadModule(d)
          
          			end)
          
          		end
          
          	end)
          
          	return self
          
          end
          
          
          function Registry.AutoLoadConfigs(root)
          
          	local function attach(folder)
          
          		if folder:IsA("Folder") and folder.Name:sub(-6) == "Config" and #folder.Name > 6 then
          
          			local name = folder.Name:sub(1, -7)
          
          			Registry.Create(name):LoadFolder(folder)
          
          		end
          
          	end
          
          	for _, child in ipairs(root:GetChildren()) do
          
          		attach(child)
          
          	end
          
          	root.ChildAdded:Connect(attach)
          
          end
          
          
          return Registry
          
          
        SOURCE_END
    - Template1 [ImageButton]
      - UIStroke [UIStroke]
      - UICorner [UICorner]
    - Template2 [TextButton]
      - UICorner [UICorner]
      - UIStroke [UIStroke]
    - TowerDefense [Folder]
      - TowerData [ModuleScript]
        PATH: game.ReplicatedStorage.TowerDefense.TowerData
        SOURCE_START
          -- Tower Defense - Dragon Ball Characters Data
          
          -- 10 characters with unique stats
          
          
          local TowerData = {}
          
          
          -- Each tower: name, cost, damage, range, cooldown, splashRadius, slowEffect, slowDuration, maxTargets, color, description
          
          TowerData.Towers = {
          
              ["Krillin"] = {
          
                  Name = "Krillin",
          
                  Cost = 50,
          
                  Damage = 8,
          
                  Range = 20,
          
                  Cooldown = 1.0,
          
                  SplashRadius = 0,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 1,
          
                  Color = Color3.fromRGB(255, 200, 100),
          
                  Description = "Cheap and basic. Good for early game.",
          
                  UpgradeCost = 40,
          
                  UpgradeMultiplier = 1.5,
          
                  MaxLevel = 3,
          
              },
          
              ["Goku"] = {
          
                  Name = "Goku",
          
                  Cost = 100,
          
                  Damage = 20,
          
                  Range = 30,
          
                  Cooldown = 0.8,
          
                  SplashRadius = 0,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 1,
            -  Editar
  18:22:18.453  ========== END PART 20 ==========  -  Editar
  18:22:18.453   ▶  (x2)  -  Editar
  18:22:18.454  ========== PROJECT EXPORT PART 21 ==========  -  Editar
  18:22:18.454                    Color = Color3.fromRGB(255, 100, 50),
          
                  Description = "Balanced fighter. Kamehameha!",
          
                  UpgradeCost = 75,
          
                  UpgradeMultiplier = 1.6,
          
                  MaxLevel = 3,
          
              },
          
              ["Vegeta"] = {
          
                  Name = "Vegeta",
          
                  Cost = 150,
          
                  Damage = 35,
          
                  Range = 18,
          
                  Cooldown = 1.2,
          
                  SplashRadius = 0,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 1,
          
                  Color = Color3.fromRGB(50, 50, 255),
          
                  Description = "High damage, short range. Prince of Saiyans!",
          
                  UpgradeCost = 100,
          
                  UpgradeMultiplier = 1.7,
          
                  MaxLevel = 3,
          
              },
          
              ["Piccolo"] = {
          
                  Name = "Piccolo",
          
                  Cost = 120,
          
                  Damage = 15,
          
                  Range = 45,
          
                  Cooldown = 1.5,
          
                  SplashRadius = 0,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 1,
          
                  Color = Color3.fromRGB(100, 200, 100),
          
                  Description = "Long range sniper. Special Beam Cannon!",
          
                  UpgradeCost = 80,
          
                  UpgradeMultiplier = 1.5,
          
                  MaxLevel = 3,
          
              },
          
              ["Gohan"] = {
          
                  Name = "Gohan",
          
                  Cost = 200,
          
                  Damage = 25,
          
                  Range = 28,
          
                  Cooldown = 1.5,
          
                  SplashRadius = 12,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 1,
          
                  Color = Color3.fromRGB(255, 150, 50),
          
                  Description = "Splash damage. Masenko!",
          
                  UpgradeCost = 120,
          
                  UpgradeMultiplier = 1.6,
          
                  MaxLevel = 3,
          
              },
          
              ["Trunks"] = {
          
                  Name = "Trunks",
          
                  Cost = 130,
          
                  Damage = 12,
          
                  Range = 25,
          
                  Cooldown = 0.3,
          
                  SplashRadius = 0,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 1,
          
                  Color = Color3.fromRGB(150, 150, 255),
          
                  Description = "Very fast attacks. Sword master!",
          
                  UpgradeCost = 90,
          
                  UpgradeMultiplier = 1.4,
          
                  MaxLevel = 3,
          
              },
          
              ["Tien"] = {
          
                  Name = "Tien",
          
                  Cost = 180,
          
                  Damage = 18,
          
                  Range = 35,
          
                  Cooldown = 1.0,
          
                  SplashRadius = 0,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 3,
          
                  Color = Color3.fromRGB(200, 200, 50),
          
                  Description = "Attacks multiple enemies. Tri-Beam!",
          
                  UpgradeCost = 110,
          
                  UpgradeMultiplier = 1.5,
          
                  MaxLevel = 3,
          
              },
          
              ["MajinBuu"] = {
          
                  Name = "Majin Buu",
          
                  Cost = 160,
          
                  Damage = 10,
          
                  Range = 25,
          
                  Cooldown = 1.0,
          
                  SplashRadius = 0,
          
                  SlowEffect = 0.5,
          
                  SlowDuration = 3,
          
                  MaxTargets = 1,
          
                  Color = Color3.fromRGB(255, 150, 200),
          
                  Description = "Slows enemies. Buu turn you into candy!",
          
                  UpgradeCost = 100,
          
                  UpgradeMultiplier = 1.4,
          
                  MaxLevel = 3,
          
              },
          
              ["Cell"] = {
          
                  Name = "Cell",
          
                  Cost = 250,
          
                  Damage = 30,
          
                  Range = 30,
          
                  Cooldown = 1.0,
          
                  SplashRadius = 0,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 1,
          
                  Color = Color3.fromRGB(100, 200, 50),
          
                  Description = "Tank tower. High HP absorber!",
          
                  UpgradeCost = 150,
          
                  UpgradeMultiplier = 1.7,
          
                  MaxLevel = 3,
          
              },
          
              ["Frieza"] = {
          
                  Name = "Frieza",
          
                  Cost = 400,
          
                  Damage = 60,
          
                  Range = 60,
          
                  Cooldown = 2.0,
          
                  SplashRadius = 8,
          
                  SlowEffect = 0,
          
                  SlowDuration = 0,
          
                  MaxTargets = 1,
          
                  Color = Color3.fromRGB(200, 100, 200),
          
                  Description = "Ultimate tower. Death Beam!",
          
                  UpgradeCost = 250,
          
                  UpgradeMultiplier = 1.8,
          
                  MaxLevel = 3,
          
              },
          
          }
          
          
          TowerData.Order = {"Krillin", "Goku", "Vegeta", "Piccolo", "Gohan", "Trunks", "Tien", "MajinBuu", "Cell", "Frieza"}
          
          
          function TowerData.GetTowerData(name)
          
              return TowerData.Towers[name]
          
          end
          
          
          function TowerData.GetUpgradedStats(name, level)
          
              local base = TowerData.Towers[name]
          
              if not base then return nil end
          
              local mult = base.UpgradeMultiplier ^ (level - 1)
          
              return {
          
                  Damage = math.floor(base.Damage * mult),
          
                  Range = math.floor(base.Range * (1 + (level - 1) * 0.15)),
          
                  Cooldown = math.max(0.1, base.Cooldown * (1 - (level - 1) * 0.1)),
          
                  SplashRadius = base.SplashRadius > 0 and math.floor(base.SplashRadius * mult) or 0,
          
                  SlowEffect = base.SlowEffect,
          
                  SlowDuration = base.SlowDuration + (level - 1) * 0.5,
          
                  MaxTargets = base.MaxTargets + (level - 1),
          
              }
          
          end
          
          
          return TowerData
          
        SOURCE_END
      - Remotes [Folder]
        - PlaceTower [RemoteEvent]
          REMOTE_PATH: game.ReplicatedStorage.TowerDefense.Remotes.PlaceTower
        - SellTower [RemoteEvent]
          REMOTE_PATH: game.ReplicatedStorage.TowerDefense.Remotes.SellTower
        - StartWave [RemoteEvent]
          REMOTE_PATH: game.ReplicatedStorage.TowerDefense.Remotes.StartWave
        - UpgradeTower [RemoteEvent]
          REMOTE_PATH: game.ReplicatedStorage.TowerDefense.Remotes.UpgradeTower
        - TowerSelected [RemoteEvent]
          REMOTE_PATH: game.ReplicatedStorage.TowerDefense.Remotes.TowerSelected
        - GameUpdate [RemoteEvent]
          REMOTE_PATH: game.ReplicatedStorage.TowerDefense.Remotes.GameUpdate
      - TowerModels [Folder]
  - ServerScriptService [ServerScriptService]
    - Main [Script]
      PATH: game.ServerScriptService.Main
      SOURCE_START
        -- Bootstrap do servidor. Você não precisa editar este arquivo para adicionar conteúdo.
        
        local ReplicatedStorage = game:GetService("ReplicatedStorage")
        
        local ServerStorage = game:GetService("ServerStorage")
        
        local ServerScriptService = game:GetService("ServerScriptService")
        
        
        local Shared = ReplicatedStorage:WaitForChild("Shared")
        
        local Registry = require(Shared.Registry)
        
        local Net = require(Shared.Net)
        
        
        -- 1) Auto-loader: cada pasta "<X>Config" vira o registro "<X>"; Passives fica só no servidor (ServerStorage)
        
        Registry.AutoLoadConfigs(ReplicatedStorage:WaitForChild("Configs"))
        
        Registry.Create("Passives"):LoadFolder(ServerStorage:WaitForChild("Passives"))
        
        
        -- 2) Rede
        
        Net.Init()
        
        
        -- 3) Serviços
        
        local Server = ServerScriptService:WaitForChild("Server")
        
        
        local function step(name, fn)
        
        	local ok, err = pcall(fn)
        
        	if ok then
        
        		print("[Boot] ok: " .. name)
        
        	else
        
        		warn("[Boot] FALHOU: " .. name .. " -> " .. tostring(err))
        
        	end
        
        end
        
        
        step("ConfigValidator", function() require(Server.ConfigValidator).Run() end)
        
        step("Requests", function() require(Server.Requests).Init() end)
        
        step("Replicator", function() require(Server.Replicator).Init() end)
        
        step("Economy", function() require(Server.Economy).Init() end)
        
        step("Loadout", function() require(Server.Loadout).Init() end)
        
        step("TowerService", function() require(Server.TowerService).Init() end)
        
        step("AdminCommands", function() require(Server.AdminCommands).Init() end)
        
        step("GameManager", function() require(Server.GameManager).Init() end)
        
        
      SOURCE_END
    - Server [Folder]
      - ConfigValidator [ModuleScript]
        PATH: game.ServerScriptService.Server.ConfigValidator
        SOURCE_START
          -- Valida referências cruzadas dos configs no boot (typos em Id de passiva/efeito/modo viram warn claro).
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Registry = require(ReplicatedStorage.Shared.Registry)
          
          
          local V = {}
          
          
          local function check(cond, msg, ...)
          
          	if not cond then
          
          		warn("[ConfigValidator] " .. msg:format(...))
          
          	end
          
          end
          
          
          local function checkPassives(owner, list)
          
          	local passives = Registry.Of("Passives")
          
          	for _, p in ipairs(list or {}) do
          
          		check(passives:Get(p.Id), "%s usa passiva inexistente '%s'", owner, tostring(p.Id))
          
          	end
          
          end
          
          
          local function checkEffects(owner, list)
          
          	local fx = Registry.Of("StatusEffects")
          
          	for _, e in ipairs(list or {}) do
          
          		local id = type(e) == "string" and e or e.Id
            -  Editar
  18:22:18.454  ========== END PART 21 ==========  -  Editar
  18:22:18.454   ▶  (x2)  -  Editar
  18:22:18.455  ========== PROJECT EXPORT PART 22 ==========  -  Editar
  18:22:18.455            		check(fx:Get(id), "%s usa efeito inexistente '%s'", owner, tostring(id))
          
          	end
          
          end
          
          
          function V.Run()
          
          	local targeting = Registry.Of("Targeting")
          
          	for id, t in pairs(Registry.Of("Towers"):All()) do
          
          		local name = "Torre " .. id
          
          		check(type(t.Cost) == "number", "%s sem Cost numérico", name)
          
          		check(type(t.Stats) == "table", "%s sem tabela Stats", name)
          
          		checkPassives(name, t.Passives)
          
          		checkEffects(name, t.Effects)
          
          		for _, mode in ipairs(t.Targeting and t.Targeting.Modes or {}) do
          
          			check(targeting:Get(mode), "%s usa modo de targeting inexistente '%s'", name, mode)
          
          		end
          
          		for _, path in ipairs(t.Upgrades and t.Upgrades.Paths or {}) do
          
          			for i, tier in ipairs(path.Tiers) do
          
          				local n = ("%s/%s/tier %d"):format(name, path.Id, i)
          
          				check(type(tier.Cost) == "number", "%s sem Cost", n)
          
          				checkPassives(n, tier.AddPassives)
          
          				checkEffects(n, tier.AddEffects)
          
          			end
          
          		end
          
          	end
          
          	for id, e in pairs(Registry.Of("Enemies"):All()) do
          
          		local name = "Inimigo " .. id
          
          		check(type(e.Health) == "number" and type(e.Speed) == "number", "%s precisa de Health e Speed", name)
          
          		checkPassives(name, e.Passives)
          
          	end
          
          	for id, m in pairs(Registry.Of("Maps"):All()) do
          
          		check(m.Paths and m.Paths[m.DefaultPath], "Mapa %s: DefaultPath inválido", id)
          
          	end
          
          end
          
          
          return V
          
          
        SOURCE_END
      - Economy [ModuleScript]
        PATH: game.ServerScriptService.Server.Economy
        SOURCE_START
          -- Moedas por jogador (servidor é a única fonte de verdade). Replica via evento global "PlayerData".
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local EventBus = require(ReplicatedStorage.Shared.EventBus)
          
          local G = EventBus.Global
          
          
          local Economy = {}
          
          local coins = {}
          
          
          local function push(player)
          
          	G:Fire("PlayerData", player, { Coins = coins[player] or 0 })
          
          end
          
          
          function Economy.SetCoins(player, amount)
          
          	coins[player] = amount
          
          	push(player)
          
          end
          
          
          function Economy.Get(player)
          
          	return coins[player] or 0
          
          end
          
          
          function Economy.CanAfford(player, amount)
          
          	return (coins[player] or 0) >= amount
          
          end
          
          
          function Economy.Add(player, amount)
          
          	if coins[player] == nil then
          
          		return
          
          	end
          
          	coins[player] += amount
          
          	push(player)
          
          end
          
          
          function Economy.Spend(player, amount)
          
          	if not Economy.CanAfford(player, amount) then
          
          		return false
          
          	end
          
          	coins[player] -= amount
          
          	push(player)
          
          	return true
          
          end
          
          
          function Economy.AddAll(amount)
          
          	for player in pairs(coins) do
          
          		Economy.Add(player, amount)
          
          	end
          
          end
          
          
          function Economy.Remove(player)
          
          	coins[player] = nil
          
          end
          
          
          function Economy.Init()
          
          	-- recompensa de abate vai para o dono da torre que deu o golpe final (inclui DoT atribuído à torre)
          
          	G:Connect("EnemyKilled", function(enemy, killer)
          
          		if killer and killer.Owner then
          
          			Economy.Add(killer.Owner, math.floor(enemy.Reward + 0.5))
          
          		end
          
          	end)
          
          end
          
          
          return Economy
          
          
        SOURCE_END
      - GameManager [ModuleScript]
        PATH: game.ServerScriptService.Server.GameManager
        SOURCE_START
          --[[
          
          	GameManager: máquina de estados da partida.
          
          	WaitingForPlayers -> Intermission -> WaveActive -> (Intermission ...) -> GameOver | Victory -> WaitingForPlayers
          
          	Tudo que varia vem do GameModesConfig (tempos, ondas manuais/procedurais, escala de vida, bônus, vitória).
          
          	Ondas procedurais: mode.Waves.Generator(wave, ctx) devolve grupos { EnemyId, Count, Interval, Delay }.
          
          ]]
          
          local RunService = game:GetService("RunService")
          
          local Players = game:GetService("Players")
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Registry = require(ReplicatedStorage.Shared.Registry)
          
          local EventBus = require(ReplicatedStorage.Shared.EventBus)
          
          local World = require(script.Parent.World)
          
          local Economy = require(script.Parent.Economy)
          
          
          local G = EventBus.Global
          
          
          local STATES = {
          
          	Waiting = "WaitingForPlayers",
          
          	Intermission = "Intermission",
          
          	Wave = "WaveActive",
          
          	GameOver = "GameOver",
          
          	Victory = "Victory",
          
          }
          
          local RESTART_DELAY = 12
          
          
          local run = {
          
          	State = "",
          
          	Wave = 0,
          
          	Lives = 0,
          
          	MaxLives = 0,
          
          	EndsAt = 0,
          
          	Mode = nil,
          
          	MapId = nil,
          
          	Queue = {},
          
          	QueueIndex = 1,
          
          	WaveStartedAt = 0,
          
          }
          
          local handlers = {}
          
          local GameManager = { States = STATES }
          
          
          local function now()
          
          	return workspace:GetServerTimeNow()
          
          end
          
          
          function GameManager.GetPublicState()
          
          	return {
          
          		State = run.State,
          
          		Wave = run.Wave,
          
          		EndsAt = run.EndsAt,
          
          		Lives = run.Lives,
          
          		MaxLives = run.MaxLives,
          
          		MapId = run.MapId,
          
          		ModeId = run.Mode and run.Mode.Id,
          
          		VictoryWave = run.Mode and run.Mode.VictoryWave or 0,
          
          	}
          
          end
          
          
          local function publish()
          
          	G:Fire("GameStateChanged", GameManager.GetPublicState())
          
          end
          
          
          local function setState(name)
          
          	run.State = name
          
          	local h = handlers[name]
          
          	if h and h.Enter then
          
          		h.Enter()
          
          	end
          
          	publish()
          
          end
          
          
          function GameManager.CanBuild()
          
          	return run.State == STATES.Intermission or run.State == STATES.Wave
          
          end
          
          
          local function pickMode()
          
          	local modes = Registry.Of("GameModes")
          
          	local id = workspace:GetAttribute("GameMode") or "Endless"
          
          	return modes:Get(id) or modes:Require(modes:Ids()[1])
          
          end
          
          
          local function pickMap(mode)
          
          	local maps = Registry.Of("Maps")
          
          	local forced = workspace:GetAttribute("MapId")
          
          	if forced and maps:Get(forced) then
          
          		return forced
          
          	end
          
          	local pool = mode.MapPool or maps:Ids()
          
          	return pool[math.random(#pool)]
          
          end
          
          
          local function buildQueue()
          
          	local mode, wave = run.Mode, run.Wave
          
          	local waves = mode.Waves or {}
          
          	local groups = waves.Manual and waves.Manual[wave]
          
          	if not groups and waves.Generator then
          
          		groups = waves.Generator(wave, {
          
          			Enemies = Registry.Of("Enemies"),
          
          			Random = Random.new(wave * 7919 + (mode.Seed or 0)),
          
          		})
          
          	end
          
          	local queue = {}
          
          	for _, g in ipairs(groups or {}) do
          
          		for i = 1, g.Count or 1 do
          
          			table.insert(queue, {
          
          				At = (g.Delay or 0) + (i - 1) * (g.Interval or 1),
          
          				EnemyId = g.EnemyId,
          
          				HealthMultiplier = g.HealthMultiplier,
          
          			})
          
          		end
          
          	end
          
          	table.sort(queue, function(a, b)
          
          		return a.At < b.At
          
          	end)
          
          	run.Queue, run.QueueIndex = queue, 1
          
          end
          
          
          handlers[STATES.Waiting] = {
          
          	Enter = function()
          
          		World.Clear()
          
          		run.Wave, run.EndsAt = 0, 0
          
          		run.Mode = pickMode()
          
          		run.MapId = pickMap(run.Mode)
          
          		local map = World.LoadMap(run.MapId)
          
          		run.MaxLives = map.Config.StartingLives or 20
          
          		run.Lives = run.MaxLives
          
          		for _, p in ipairs(Players:GetPlayers()) do
          
          			Economy.SetCoins(p, map.Config.StartingCoins or 0)
          
          		end
          
          	end,
          
          	Update = function(_, t)
          
          		if Players.NumPlayers >= run.Mode.MinPlayers then
          
          			if run.EndsAt == 0 then
          
          				run.EndsAt = t + run.Mode.WaitingTime
          
          				publish()
          
          			end
          
          			if t >= run.EndsAt then
          
          				setState(STATES.Intermission)
          
          			end
          
          		elseif run.EndsAt ~= 0 then
          
          			run.EndsAt = 0
          
          			publish()
          
          		end
          
          	end,
          
          }
          
          
          handlers[STATES.Intermission] = {
          
          	Enter = function()
          
          		run.Wave += 1
          
          		run.EndsAt = now() + run.Mode.IntermissionTime
          
          	end,
          
          	Update = function(dt, t)
          
          		World.Step(dt, t)
          
          		if t >= run.EndsAt then
          
          			setState(STATES.Wave)
          
          		end
          
          	end,
          
          }
          
          
          handlers[STATES.Wave] = {
          
          	Enter = function()
          
          		run.EndsAt = 0
            -  Editar
  18:22:18.455  ========== END PART 22 ==========  -  Editar
  18:22:18.455   ▶  (x2)  -  Editar
  18:22:18.456  ========== PROJECT EXPORT PART 23 ==========  -  Editar
  18:22:18.456            		run.WaveStartedAt = now()
          
          		buildQueue()
          
          	end,
          
          	Update = function(dt, t)
          
          		local elapsed = t - run.WaveStartedAt
          
          		local mode = run.Mode
          
          		while run.QueueIndex <= #run.Queue and run.Queue[run.QueueIndex].At <= elapsed do
          
          			local q = run.Queue[run.QueueIndex]
          
          			run.QueueIndex += 1
          
          			local scale = mode.HealthScale and mode.HealthScale(run.Wave) or 1
          
          			World.SpawnEnemy(q.EnemyId, { HealthMultiplier = scale * (q.HealthMultiplier or 1) })
          
          		end
          
          		World.Step(dt, t)
          
          
          		if run.State == STATES.Wave and run.QueueIndex > #run.Queue and World.EnemyCount == 0 then
          
          			if mode.WaveBonus then
          
          				Economy.AddAll(mode.WaveBonus(run.Wave))
          
          			end
          
          			if mode.VictoryWave and run.Wave >= mode.VictoryWave then
          
          				setState(STATES.Victory)
          
          			else
          
          				setState(STATES.Intermission)
          
          			end
          
          		end
          
          	end,
          
          }
          
          
          local function endHandlers()
          
          	return {
          
          		Enter = function()
          
          			World.ClearEnemies()
          
          			run.EndsAt = now() + RESTART_DELAY
          
          		end,
          
          		Update = function(_, t)
          
          			if t >= run.EndsAt then
          
          				setState(STATES.Waiting)
          
          			end
          
          		end,
          
          	}
          
          end
          
          handlers[STATES.GameOver] = endHandlers()
          
          handlers[STATES.Victory] = endHandlers()
          
          
          function GameManager.Init()
          
          	G:Connect("EnemyLeaked", function(enemy)
          
          		if run.State ~= STATES.Wave and run.State ~= STATES.Intermission then
          
          			return
          
          		end
          
          		run.Lives = math.max(0, run.Lives - enemy.LivesDamage)
          
          		if run.Lives <= 0 then
          
          			setState(STATES.GameOver)
          
          		else
          
          			publish()
          
          		end
          
          	end)
          
          
          	setState(STATES.Waiting)
          
          
          	Players.PlayerAdded:Connect(function(player)
          
          		if World.Map then
          
          			Economy.SetCoins(player, World.Map.Config.StartingCoins or 0)
          
          		end
          
          	end)
          
          	Players.PlayerRemoving:Connect(function(player)
          
          		local mine = {}
          
          		for _, t in pairs(World.Towers) do
          
          			if t.Owner == player then
          
          				table.insert(mine, t)
          
          			end
          
          		end
          
          		for _, t in ipairs(mine) do
          
          			t:Destroy()
          
          		end
          
          		Economy.Remove(player)
          
          	end)
          
          
          	RunService.Heartbeat:Connect(function(dt)
          
          		local h = handlers[run.State]
          
          		if h and h.Update then
          
          			h.Update(dt, now())
          
          		end
          
          	end)
          
          end
          
          
          return GameManager
          
          
        SOURCE_END
      - Loadout [ModuleScript]
        PATH: game.ServerScriptService.Server.Loadout
        SOURCE_START
          -- Loadout: quais torres cada jogador tem equipadas (servidor decide; o cliente só pede).
          
          local Players = game:GetService("Players")
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Registry = require(ReplicatedStorage.Shared.Registry)
          
          local EventBus = require(ReplicatedStorage.Shared.EventBus)
          
          local Requests = require(script.Parent.Requests)
          
          
          local G = EventBus.Global
          
          local Loadout = {}
          
          local equipped = {} -- [player] = { towerId, ... } (ordem = ordem dos slots)
          
          
          local function maxSlots()
          
          	return workspace:GetAttribute("MaxEquipped") or 5
          
          end
          
          
          local function push(player)
          
          	G:Fire("LoadoutChanged", player, table.clone(equipped[player] or {}))
          
          end
          
          
          local function defaultLoadout()
          
          	local towers = Registry.Of("Towers")
          
          	local ids = towers:Ids()
          
          	table.sort(ids, function(a, b)
          
          		return towers:Get(a).Cost < towers:Get(b).Cost
          
          	end)
          
          	local list = {}
          
          	for i = 1, math.min(#ids, maxSlots()) do
          
          		list[i] = ids[i]
          
          	end
          
          	return list
          
          end
          
          
          function Loadout.Get(player)
          
          	return table.clone(equipped[player] or {})
          
          end
          
          
          function Loadout.IsEquipped(player, towerId)
          
          	local list = equipped[player]
          
          	return list ~= nil and table.find(list, towerId) ~= nil
          
          end
          
          
          function Loadout.Init()
          
          	local function setup(player)
          
          		equipped[player] = defaultLoadout()
          
          		push(player)
          
          	end
          
          	Players.PlayerAdded:Connect(setup)
          
          	for _, p in ipairs(Players:GetPlayers()) do
          
          		setup(p)
          
          	end
          
          	Players.PlayerRemoving:Connect(function(p)
          
          		equipped[p] = nil
          
          	end)
          
          
          	Requests.Handle("ToggleEquip", function(player, p)
          
          		if type(p) ~= "table" or type(p.TowerId) ~= "string" then
          
          			return { Ok = false, Error = "BadRequest" }
          
          		end
          
          		if not Registry.Of("Towers"):Get(p.TowerId) then
          
          			return { Ok = false, Error = "UnknownTower" }
          
          		end
          
          		local list = equipped[player]
          
          		if not list then
          
          			return { Ok = false, Error = "BadRequest" }
          
          		end
          
          		local idx = table.find(list, p.TowerId)
          
          		if idx then
          
          			table.remove(list, idx)
          
          		else
          
          			if #list >= maxSlots() then
          
          				return { Ok = false, Error = "LoadoutFull" }
          
          			end
          
          			table.insert(list, p.TowerId)
          
          		end
          
          		push(player)
          
          		return { Ok = true }
          
          	end)
          
          end
          
          
          return Loadout
          
        SOURCE_END
      - PassiveEngine [ModuleScript]
        PATH: game.ServerScriptService.Server.PassiveEngine
        SOURCE_START
          --[[
          
          	PassiveEngine: liga módulos da pasta Passives a qualquer entidade que tenha `.Bus` (Tower, Enemy, ...).
          
          	A entidade só entrega uma lista { {Id=, Params=}, ... }; nenhuma regra de passiva vive nas classes.
          
          
          	Formato de um módulo de passiva:
          
          	return {
          
          		Id = "MinhaPassiva",
          
          		Priority = 0,                                -- menor roda primeiro
          
          		Defaults = { ... },                          -- params padrão (sobrescritos pelo Params do config)
          
          		OnAttach = function(passive, owner) end,     -- opcional
          
          		OnDetach = function(passive, owner) end,     -- opcional (limpe buffs aqui)
          
          		OnParamsChanged = function(passive) end,     -- opcional
          
          		Hooks = { OnPreAttack = function(passive, tower, enemy, damageData) end, ... }  -- qualquer evento do Bus
          
          	}
          
          	passive.Params = params finais · passive.State = tabela livre · passive.Owner = entidade
          
          ]]
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Registry = require(ReplicatedStorage.Shared.Registry)
          
          
          local PassiveEngine = {}
          
          
          local function safe(fn, ...)
          
          	local ok, err = pcall(fn, ...)
          
          	if not ok then
          
          		warn("[PassiveEngine] " .. tostring(err))
          
          	end
          
          end
          
          
          function PassiveEngine.Attach(owner, list)
          
          	if not list then
          
          		return
          
          	end
          
          	local registry = Registry.Of("Passives")
          
          	owner.Passives = owner.Passives or {}
          
          	for _, entry in ipairs(list) do
          
          		local def = registry:Get(entry.Id)
          
          		if not def then
          
          			warn(("[PassiveEngine] passiva '%s' não encontrada"):format(tostring(entry.Id)))
          
          		else
          
          			local params = table.clone(def.Defaults or {})
          
          			for k, v in pairs(entry.Params or {}) do
          
          				params[k] = v
          
          			end
          
          			local passive = { Id = entry.Id, Def = def, Owner = owner, Params = params, State = {}, Connections = {} }
          
          			if def.OnAttach then
          
          				safe(def.OnAttach, passive, owner)
          
          			end
          
          			for hook, fn in pairs(def.Hooks or {}) do
          
          				table.insert(
          
          					passive.Connections,
          
          					owner.Bus:Connect(hook, function(...)
          
          						fn(passive, ...)
          
          					end, def.Priority or 0)
          
          				)
          
          			end
          
          			table.insert(owner.Passives, passive)
          
          		end
          
          	end
          
          end
          
          
          function PassiveEngine.SetParams(owner, passiveId, overrides)
          
          	for _, p in ipairs(owner.Passives or {}) do
          
          		if p.Id == passiveId then
          
          			for k, v in pairs(overrides) do
          
          				p.Params[k] = v
          
          			end
          
          			if p.Def.OnParamsChanged then
          
          				safe(p.Def.OnParamsChanged, p)
          
          			end
          
          		end
          
          	end
          
          end
          
          
          function PassiveEngine.Detach(owner)
          
          	for _, p in ipairs(owner.Passives or {}) do
          
          		for _, c in ipairs(p.Connections) do
          
          			c:Disconnect()
          
          		end
          
          		if p.Def.OnDetach then
          
          			safe(p.Def.OnDetach, p, owner)
          
          		end
          
          	end
          
          	owner.Passives = {}
          
          end
          
          
          return PassiveEngine
          
            -  Editar
  18:22:18.456  ========== END PART 23 ==========  -  Editar
  18:22:18.456   ▶  (x2)  -  Editar
  18:22:18.456  ========== PROJECT EXPORT PART 24 ==========  -  Editar
  18:22:18.457          SOURCE_END
      - Replicator [ModuleScript]
        PATH: game.ServerScriptService.Server.Replicator
        SOURCE_START
          --[[
          
          	Replicator: ÚNICO ponto que fala com clientes sobre o mundo. A lógica (Tower/Enemy) só dispara eventos globais;
          
          	aqui eles viram um pacote "Delta" em lote a 20 Hz (ordem garantida: tudo num remote só).
          
          	Inimigos: spawn (1x) + mudança de movimento (âncora D/T + velocidade S). O cliente calcula a posição sozinho
          
          	com workspace:GetServerTimeNow(); o servidor NÃO envia posição por frame.
          
          ]]
          
          local RunService = game:GetService("RunService")
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Loadout = require(script.Parent.Loadout)
          
          local EventBus = require(ReplicatedStorage.Shared.EventBus)
          
          local Net = require(ReplicatedStorage.Shared.Net)
          
          local Requests = require(script.Parent.Requests)
          
          local World = require(script.Parent.World)
          
          local Economy = require(script.Parent.Economy)
          
          
          local G = EventBus.Global
          
          local SEND_INTERVAL = 0.05
          
          
          local Replicator = {}
          
          local delta, motionMap, healthMap, dirty
          
          local lastState
          
          
          local function emptyPacket()
          
          	return {
          
          		EnemySpawned = {},
          
          		EnemyMotion = {},
          
          		EnemyHealth = {},
          
          		EnemyRemoved = {},
          
          		Status = {},
          
          		TowerPlaced = {},
          
          		TowerUpdated = {},
          
          		TowerRemoved = {},
          
          		TowerFired = {},
          
          	}
          
          end
          
          
          local function reset()
          
          	delta = emptyPacket()
          
          	motionMap, healthMap = {}, {}
          
          	dirty = false
          
          end
          
          
          local function push(key, payload)
          
          	table.insert(delta[key], payload)
          
          	dirty = true
          
          end
          
          
          local function flatten(map)
          
          	local out = {}
          
          	for _, v in pairs(map) do
          
          		table.insert(out, v)
          
          	end
          
          	return out
          
          end
          
          
          local function enemySnapshot(e)
          
          	return {
          
          		Id = e.Id,
          
          		Cfg = e.ConfigId,
          
          		Path = e.PathId,
          
          		MaxHp = e.MaxHealth,
          
          		Hp = e.Health,
          
          		D = e.DistanceAnchor,
          
          		T = e.TimeAnchor,
          
          		S = e:GetSpeed(),
          
          	}
          
          end
          
          
          local function towerSnapshot(t)
          
          	return {
          
          		Id = t.Id,
          
          		Cfg = t.ConfigId,
          
          		Pos = t.Position,
          
          		Owner = t.Owner and t.Owner.UserId or 0,
          
          		Range = t.Stats.Range or 0,
          
          		Splash = t.Stats.SplashRadius or 0,
          
          		Tiers = t.Tiers,
          
          		Mode = t.TargetMode,
          
          		Invested = t.Invested,
          
          		Damage = t.Stats.Damage or 0,
          
          		Interval = t.CanAttack and (t.Stats.Cooldown or 1) / math.max(t.Stats.AttackSpeed or 1, 0.05) or 0,
          
          	}
          
          end
          
          
          local function flush()
          
          	if not dirty then
          
          		return
          
          	end
          
          	local packet = delta
          
          	packet.EnemyMotion = flatten(motionMap)
          
          	packet.EnemyHealth = flatten(healthMap)
          
          	reset()
          
          	Net.Event("Delta"):FireAllClients(packet)
          
          end
          
          
          function Replicator.Init()
          
          	reset()
          
          
          	G:Connect("EnemySpawned", function(e)
          
          		push("EnemySpawned", enemySnapshot(e))
          
          	end)
          
          	G:Connect("LoadoutChanged", function(player, list)
          
          		if player.Parent then
          
          			Net.Event("Loadout"):FireClient(player, list)
          
          		end
          
          	end)
          
          	G:Connect("EnemyMotionChanged", function(e)
          
          		motionMap[e.Id] = { Id = e.Id, D = e.DistanceAnchor, T = e.TimeAnchor, S = e:GetSpeed() }
          
          		dirty = true
          
          	end)
          
          	G:Connect("EnemyHealthChanged", function(e)
          
          		healthMap[e.Id] = { Id = e.Id, Hp = e.Health }
          
          		dirty = true
          
          	end)
          
          	G:Connect("EnemyRemoved", function(e, reason)
          
          		motionMap[e.Id] = nil
          
          		healthMap[e.Id] = nil
          
          		push("EnemyRemoved", { Id = e.Id, Reason = reason })
          
          	end)
          
          	G:Connect("StatusChanged", function(e, effectId, on, untilTime)
          
          		push("Status", { Enemy = e.Id, Effect = effectId, On = on, Until = untilTime })
          
          	end)
          
          	G:Connect("TowerPlaced", function(t)
          
          		push("TowerPlaced", towerSnapshot(t))
          
          	end)
          
          	G:Connect("TowerUpdated", function(t)
          
          		push("TowerUpdated", towerSnapshot(t))
          
          	end)
          
          	G:Connect("TowerRemoved", function(t)
          
          		push("TowerRemoved", { Id = t.Id })
          
          	end)
          
          	G:Connect("TowerFired", function(t, target, t0, t1)
          
          		push("TowerFired", { Tower = t.Id, Enemy = target.Id, T0 = t0, T1 = t1 })
          
          	end)
          
          
          	G:Connect("GameStateChanged", function(state)
          
          		lastState = state
          
          		Net.Event("GameState"):FireAllClients(state)
          
          	end)
          
          	G:Connect("PlayerData", function(player, data)
          
          		if player.Parent then
          
          			Net.Event("PlayerData"):FireClient(player, data)
          
          		end
          
          	end)
          
          	G:Connect("Notify", function(player, message)
          
          		if player then
          
          			Net.Event("Notify"):FireClient(player, message)
          
          		else
          
          			Net.Event("Notify"):FireAllClients(message)
          
          		end
          
          	end)
          
          
          	-- cliente conectado (inclusive quem entra no meio da partida) pede o retrato atual do mundo
          
          	Requests.Handle("ClientReady", function(player)
          
          		if lastState then
          
          			Net.Event("GameState"):FireClient(player, lastState)
          
          		end
          
          		local packet = emptyPacket()
          
          		for _, e in pairs(World.Enemies) do
          
          			table.insert(packet.EnemySpawned, enemySnapshot(e))
          
          		end
          
          		for _, t in pairs(World.Towers) do
          
          			table.insert(packet.TowerPlaced, towerSnapshot(t))
          
          		end
          
          		Net.Event("Delta"):FireClient(player, packet)
          
          		Net.Event("PlayerData"):FireClient(player, { Coins = Economy.Get(player) })
          
          		Net.Event("Loadout"):FireClient(player, Loadout.Get(player))
          
          		return { Ok = true }
          
          	end)
          
          
          	local acc = 0
          
          	RunService.Heartbeat:Connect(function(dt)
          
          		acc += dt
          
          		if acc >= SEND_INTERVAL then
          
          			acc = 0
          
          			flush()
          
          		end
          
          	end)
          
          end
          
          
          return Replicator
          
          
        SOURCE_END
      - Requests [ModuleScript]
        PATH: game.ServerScriptService.Server.Requests
        SOURCE_START
          --[[
          
          	Roteador de ações Cliente->Servidor (uma única RemoteFunction).
          
          	Requests.Handle("PlaceTower", function(player, payload) return { Ok = true } end)
          
          	Novas ações = novo Handle em qualquer módulo. Inclui rate limit por jogador.
          
          ]]
          
          local Players = game:GetService("Players")
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Net = require(ReplicatedStorage.Shared.Net)
          
          
          local Requests = {}
          
          local handlers = {}
          
          local buckets = {}
          
          local MAX_TOKENS, REFILL_PER_SEC = 20, 10
          
          
          function Requests.Handle(action, fn)
          
          	handlers[action] = fn
          
          end
          
          
          function Requests.Init()
          
          	Players.PlayerRemoving:Connect(function(p)
          
          		buckets[p] = nil
          
          	end)
          
          	Net.Request().OnServerInvoke = function(player, action, payload)
          
          		if type(action) ~= "string" then
          
          			return { Ok = false, Error = "BadRequest" }
          
          		end
          
          		local handler = handlers[action]
          
          		if not handler then
          
          			return { Ok = false, Error = "UnknownAction" }
          
          		end
          
          		local t = os.clock()
          
          		local b = buckets[player]
          
          		if not b then
          
          			b = { Tokens = MAX_TOKENS, Last = t }
          
          			buckets[player] = b
          
          		end
          
          		b.Tokens = math.min(MAX_TOKENS, b.Tokens + (t - b.Last) * REFILL_PER_SEC)
          
          		b.Last = t
          
          		if b.Tokens < 1 then
          
          			return { Ok = false, Error = "RateLimited" }
          
          		end
          
          		b.Tokens -= 1
          
          		local ok, result = pcall(handler, player, payload)
          
          		if not ok then
          
          			warn("[Requests] " .. action .. ": " .. tostring(result))
          
          			return { Ok = false, Error = "ServerError" }
          
          		end
          
          		return result
          
          	end
          
          end
          
          
          return Requests
          
          
        SOURCE_END
      - StatusEffectManager [ModuleScript]
        PATH: game.ServerScriptService.Server.StatusEffectManager
        SOURCE_START
          --[[
          
          	StatusEffectManager: acopla QUALQUER efeito de StatusEffectsConfig em QUALQUER inimigo, sem if/else no Enemy.
          
          	Hooks do efeito: OnApply(inst, enemy) · OnTick(inst, enemy, dt) · OnRemove(inst, enemy, reason) · OnRefresh(inst, enemy)
          
          	Campos opcionais do efeito: Tags, Stacking ("Refresh"|"Stack"), Defaults, ReapplyCooldown.
          
          	Imunidades: enemy.Config.Immunities.Status pode conter ids OU tags do efeito.
          
          	Um único loop de Heartbeat cobre todos os inimigos com status ativo.  -  Editar
  18:22:18.457  ========== END PART 24 ==========  -  Editar
  18:22:18.457   ▶  (x2)  -  Editar
  18:22:18.458  ========== PROJECT EXPORT PART 25 ==========  -  Editar
  18:22:18.458            
          ]]
          
          local RunService = game:GetService("RunService")
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Registry = require(ReplicatedStorage.Shared.Registry)
          
          local EventBus = require(ReplicatedStorage.Shared.EventBus)
          
          
          local G = EventBus.Global
          
          local Manager = {}
          
          local active = {} -- [enemy] = true
          
          
          local function now()
          
          	return workspace:GetServerTimeNow()
          
          end
          
          
          local function safe(fn, ...)
          
          	local ok, err = pcall(fn, ...)
          
          	if not ok then
          
          		warn("[StatusEffect] " .. tostring(err))
          
          	end
          
          end
          
          
          function Manager.Apply(enemy, effectId, opts)
          
          	if not enemy.Alive then
          
          		return nil
          
          	end
          
          	local def = Registry.Of("StatusEffects"):Get(effectId)
          
          	if not def then
          
          		warn(("[StatusEffect] efeito '%s' não existe"):format(tostring(effectId)))
          
          		return nil
          
          	end
          
          	if enemy:IsImmuneToStatus(def) then
          
          		return nil
          
          	end
          
          	local t = now()
          
          	local lock = enemy.StatusLock[effectId]
          
          	if lock and t < lock then
          
          		return nil
          
          	end
          
          
          	opts = opts or {}
          
          	local params = table.clone(def.Defaults or {})
          
          	for k, v in pairs(opts.Params or {}) do
          
          		params[k] = v
          
          	end
          
          	local duration = params.Duration or 1
          
          
          	local inst = enemy.Statuses[effectId]
          
          	if inst then
          
          		if def.Stacking == "Stack" then
          
          			inst.Stacks = math.min(inst.Stacks + 1, params.MaxStacks or 5)
          
          		end
          
          		if (params.Potency or 0) >= (inst.Params.Potency or 0) then
          
          			inst.Params = params
          
          		end
          
          		inst.ExpiresAt = math.max(inst.ExpiresAt, t + duration)
          
          		inst.Source = opts.Source or inst.Source
          
          		if def.OnRefresh then
          
          			safe(def.OnRefresh, inst, enemy)
          
          		end
          
          	else
          
          		inst = {
          
          			Id = effectId,
          
          			Def = def,
          
          			Enemy = enemy,
          
          			Source = opts.Source,
          
          			Params = params,
          
          			Stacks = 1,
          
          			AppliedAt = t,
          
          			ExpiresAt = t + duration,
          
          			NextTick = t + math.max(params.TickInterval or 1, 0.05),
          
          			Data = {},
          
          		}
          
          		enemy.Statuses[effectId] = inst
          
          		active[enemy] = true
          
          		if def.OnApply then
          
          			safe(def.OnApply, inst, enemy)
          
          		end
          
          	end
          
          	G:Fire("StatusChanged", enemy, effectId, true, inst.ExpiresAt)
          
          	return inst
          
          end
          
          
          function Manager.Remove(enemy, effectId, reason)
          
          	local inst = enemy.Statuses[effectId]
          
          	if not inst then
          
          		return
          
          	end
          
          	enemy.Statuses[effectId] = nil
          
          	if inst.Def.OnRemove then
          
          		safe(inst.Def.OnRemove, inst, enemy, reason or "Expired")
          
          	end
          
          	if inst.Def.ReapplyCooldown then
          
          		enemy.StatusLock[effectId] = now() + inst.Def.ReapplyCooldown
          
          	end
          
          	G:Fire("StatusChanged", enemy, effectId, false, 0)
          
          	if next(enemy.Statuses) == nil then
          
          		active[enemy] = nil
          
          	end
          
          end
          
          
          function Manager.ClearAll(enemy, reason)
          
          	local ids = {}
          
          	for id in pairs(enemy.Statuses) do
          
          		table.insert(ids, id)
          
          	end
          
          	for _, id in ipairs(ids) do
          
          		Manager.Remove(enemy, id, reason or "Cleared")
          
          	end
          
          end
          
          
          RunService.Heartbeat:Connect(function()
          
          	local t = now()
          
          	for enemy in pairs(active) do
          
          		if not enemy.Alive then
          
          			active[enemy] = nil
          
          		else
          
          			local ids = {}
          
          			for id in pairs(enemy.Statuses) do
          
          				table.insert(ids, id)
          
          			end
          
          			for _, id in ipairs(ids) do
          
          				local inst = enemy.Statuses[id]
          
          				if inst then
          
          					local def = inst.Def
          
          					if def.OnTick then
          
          						local interval = math.max(inst.Params.TickInterval or 1, 0.05)
          
          						while inst.NextTick <= t and inst.NextTick <= inst.ExpiresAt and enemy.Alive do
          
          							inst.NextTick += interval
          
          							safe(def.OnTick, inst, enemy, interval)
          
          						end
          
          					end
          
          					if not enemy.Alive then
          
          						break
          
          					end
          
          					if t >= inst.ExpiresAt then
          
          						Manager.Remove(enemy, id, "Expired")
          
          					end
          
          				end
          
          			end
          
          		end
          
          	end
          
          end)
          
          
          return Manager
          
          
        SOURCE_END
      - TowerService [ModuleScript]
        PATH: game.ServerScriptService.Server.TowerService
        SOURCE_START
          --[[
          
          	TowerService: valida e executa compra/upgrade/venda/targeting. O cliente só PEDE; o servidor decide.
          
          	Novas ações de jogador = novo Requests.Handle (nada nas classes).
          
          ]]
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Loadout = require(script.Parent.Loadout)
          
          local Registry = require(ReplicatedStorage.Shared.Registry)
          
          local PlacementRules = require(ReplicatedStorage.Shared.PlacementRules)
          
          local World = require(script.Parent.World)
          
          local Economy = require(script.Parent.Economy)
          
          local GameManager = require(script.Parent.GameManager)
          
          local Requests = require(script.Parent.Requests)
          
          local Tower = require(script.Parent.Classes.Tower)
          
          
          local TowerService = {}
          
          
          local function fail(code)
          
          	return { Ok = false, Error = code }
          
          end
          
          
          local function mult(name, default)
          
          	local m = World.Map and World.Map.Config.Multipliers
          
          	return m and m[name] or default or 1
          
          end
          
          
          local function validVector(v)
          
          	return typeof(v) == "Vector3" and v.X == v.X and v.Z == v.Z and math.abs(v.X) < 1e5 and math.abs(v.Z) < 1e5
          
          end
          
          
          local function ownedTower(player, id)
          
          	if type(id) ~= "number" then
          
          		return nil
          
          	end
          
          	local t = World.Towers[id]
          
          	if t and t.Alive and t.Owner == player then
          
          		return t
          
          	end
          
          	return nil
          
          end
          
          
          function TowerService.Init()
          
          	Requests.Handle("PlaceTower", function(player, p)
          
          		if type(p) ~= "table" or type(p.TowerId) ~= "string" or not validVector(p.Position) then
          
          			return fail("BadRequest")
          
          		end
          
          		if not World.Map or not GameManager.CanBuild() then
          
          			return fail("CannotBuildNow")
          
          		end
          
          		local def = Registry.Of("Towers"):Get(p.TowerId)
          
          		if not def then
          
          			return fail("UnknownTower")
          
          		end
          
          		if not Loadout.IsEquipped(player, p.TowerId) then
          
          			return fail("NotEquipped")
          
          		end
          
          		if def.MaxPerPlayer then
          
          			local count = 0
          
          			for _, t in pairs(World.Towers) do
          
          				if t.Owner == player and t.ConfigId == def.Id then
          
          					count += 1
          
          				end
          
          			end
          
          			if count >= def.MaxPerPlayer then
          
          				return fail("LimitReached")
          
          			end
          
          		end
          
          		local cost = math.ceil(def.Cost * mult("TowerCost"))
          
          		if not Economy.CanAfford(player, cost) then
          
          			return fail("NotEnoughCoins")
          
          		end
          
          		local map = World.Map
          
          		local pos = Vector3.new(p.Position.X, map.Config.GroundY or 0, p.Position.Z) -- Y sempre decidido pelo servidor
          
          		local ok, reason = PlacementRules.Check(map, pos, World.Towers)
          
          		if not ok then
          
          			return fail(reason)
          
          		end
          
          		Economy.Spend(player, cost)
          
          		local tower = Tower.new(def.Id, player, pos, cost)
          
          		World.Towers[tower.Id] = tower
          
          		tower:Activate()
          
          		return { Ok = true, TowerId = tower.Id }
          
          	end)
          
          
          	Requests.Handle("UpgradeTower", function(player, p)
          
          		if type(p) ~= "table" or type(p.PathId) ~= "string" then
          
          			return fail("BadRequest")
          
          		end
          
          		local tower = ownedTower(player, p.TowerId)
          
          		if not tower then
          
          			return fail("NotYourTower")
          
          		end
          
          		local tierDef, reason = tower:GetNextTier(p.PathId)
          
          		if not tierDef then
          
          			return fail(reason)
          
          		end
          
          		local cost = math.ceil(tierDef.Cost * mult("TowerCost"))
          
          		if not Economy.Spend(player, cost) then
          
          			return fail("NotEnoughCoins")
          
          		end
          
          		tower:Upgrade(p.PathId, cost)
          
          		return { Ok = true }
          
          	end)
          
          
          	Requests.Handle("SellTower", function(player, p)
          
          		local tower = ownedTower(player, type(p) == "table" and p.TowerId or nil)
          
          		if not tower then
          
          			return fail("NotYourTower")
          
          		end
            -  Editar
  18:22:18.458  ========== END PART 25 ==========  -  Editar
  18:22:18.458   ▶  (x2)  -  Editar
  18:22:18.459  ========== PROJECT EXPORT PART 26 ==========  -  Editar
  18:22:18.460            		Economy.Add(player, math.floor(tower.Invested * mult("SellRatio", 0.7)))
          
          		tower:Destroy()
          
          		return { Ok = true }
          
          	end)
          
          
          	Requests.Handle("SetTargeting", function(player, p)
          
          		if type(p) ~= "table" or type(p.Mode) ~= "string" then
          
          			return fail("BadRequest")
          
          		end
          
          		local tower = ownedTower(player, p.TowerId)
          
          		if not tower then
          
          			return fail("NotYourTower")
          
          		end
          
          		if not tower:SetTargetMode(p.Mode) then
          
          			return fail("InvalidMode")
          
          		end
          
          		return { Ok = true }
          
          	end)
          
          end
          
          
          return TowerService
          
          
        SOURCE_END
      - World [ModuleScript]
        PATH: game.ServerScriptService.Server.World
        SOURCE_START
          --[[
          
          	World: estado vivo da partida no servidor (mapa, inimigos, torres) + consultas espaciais.
          
          	Inimigos NÃO se movem por física: a posição é analítica (âncora de distância + velocidade * tempo do servidor),
          
          	calculada uma vez por frame em World.Update e reutilizada por todas as torres (sem raycasts, sem Instances).
          
          ]]
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local ServerStorage = game:GetService("ServerStorage")
          
          local Registry = require(ReplicatedStorage.Shared.Registry)
          
          local EventBus = require(ReplicatedStorage.Shared.EventBus)
          
          local PathUtil = require(ReplicatedStorage.Shared.PathUtil)
          
          
          local G = EventBus.Global
          
          
          local World = { Enemies = {}, Towers = {}, EnemyCount = 0, Map = nil }
          
          local snapshot = {}
          
          
          -- prioridade -100: o World atualiza o próprio estado antes de qualquer outro listener
          
          G:Connect("EnemyRemoved", function(enemy)
          
          	if World.Enemies[enemy.Id] then
          
          		World.Enemies[enemy.Id] = nil
          
          		World.EnemyCount -= 1
          
          	end
          
          end, -100)
          
          
          G:Connect("TowerRemoved", function(tower)
          
          	World.Towers[tower.Id] = nil
          
          end, -100)
          
          
          local function buildPlaceholderMap(cfg, paths, container)
          
          	local groundY = cfg.GroundY or 0
          
          	local b = cfg.Bounds or { Min = Vector3.new(-100, 0, -100), Max = Vector3.new(100, 0, 100) }
          
          	local size = b.Max - b.Min
          
          	local ground = Instance.new("Part")
          
          	ground.Name = "Ground"
          
          	ground.Anchored = true
          
          	ground.Size = Vector3.new(size.X, 1, size.Z)
          
          	ground.Position = Vector3.new((b.Min.X + b.Max.X) / 2, groundY - 0.5, (b.Min.Z + b.Max.Z) / 2)
          
          	ground.Color = Color3.fromRGB(96, 150, 84)
          
          	ground.Material = Enum.Material.Grass
          
          	ground.Parent = container
          
          
          	local width = cfg.PathClearance or 6
          
          	for _, path in pairs(paths) do
          
          		for i = 1, #path.Points - 1 do
          
          			local p1, p2 = path.Points[i], path.Points[i + 1]
          
          			local a = Vector3.new(p1.X, groundY + 0.05, p1.Z)
          
          			local c = Vector3.new(p2.X, groundY + 0.05, p2.Z)
          
          			local strip = Instance.new("Part")
          
          			strip.Name = "Road"
          
          			strip.Anchored = true
          
          			strip.CanCollide = false
          
          			strip.Size = Vector3.new(width, 0.2, (c - a).Magnitude + width)
          
          			strip.CFrame = CFrame.lookAt((a + c) / 2, c)
          
          			strip.Color = Color3.fromRGB(176, 150, 110)
          
          			strip.Material = Enum.Material.Sand
          
          			strip.Parent = container
          
          		end
          
          	end
          
          end
          
          
          function World.LoadMap(mapId)
          
          	World.Clear()
          
          	local cfg = Registry.Of("Maps"):Require(mapId)
          
          	local paths = {}
          
          	for id, points in pairs(cfg.Paths) do
          
          		paths[id] = PathUtil.new(points)
          
          	end
          
          	local container = Instance.new("Folder")
          
          	container.Name = "TDMap"
          
          	container.Parent = workspace
          
          
          	local assets = ServerStorage:FindFirstChild("Assets")
          
          	local maps = assets and assets:FindFirstChild("Maps")
          
          	local template = maps and cfg.ModelName and maps:FindFirstChild(cfg.ModelName)
          
          	if template then
          
          		template:Clone().Parent = container
          
          	else
          
          		buildPlaceholderMap(cfg, paths, container)
          
          	end
          
          
          	World.Map = { Id = mapId, Config = cfg, Paths = paths, Container = container }
          
          	return World.Map
          
          end
          
          
          function World.ClearEnemies()
          
          	local list = {}
          
          	for _, e in pairs(World.Enemies) do
          
          		table.insert(list, e)
          
          	end
          
          	for _, e in ipairs(list) do
          
          		e:Destroy("Cleared")
          
          	end
          
          end
          
          
          function World.Clear()
          
          	World.ClearEnemies()
          
          	local towers = {}
          
          	for _, t in pairs(World.Towers) do
          
          		table.insert(towers, t)
          
          	end
          
          	for _, t in ipairs(towers) do
          
          		t:Destroy()
          
          	end
          
          	if World.Map and World.Map.Container then
          
          		World.Map.Container:Destroy()
          
          	end
          
          	World.Map = nil
          
          end
          
          
          function World.AddEnemy(enemy)
          
          	World.Enemies[enemy.Id] = enemy
          
          	World.EnemyCount += 1
          
          	G:Fire("EnemySpawned", enemy)
          
          end
          
          
          function World.SpawnEnemy(enemyId, opts)
          
          	local Enemy = require(script.Parent.Classes.Enemy) -- require tardio evita ciclo World <-> Enemy
          
          	opts = opts or {}
          
          	opts.Map = World.Map
          
          	local enemy = Enemy.new(enemyId, opts)
          
          	World.AddEnemy(enemy)
          
          	enemy.Bus:Fire("OnSpawn", enemy)
          
          	return enemy
          
          end
          
          
          function World.Update(now, dt)
          
          	table.clear(snapshot)
          
          	for _, enemy in pairs(World.Enemies) do
          
          		table.insert(snapshot, enemy)
          
          	end
          
          	local leaked
          
          	for _, enemy in ipairs(snapshot) do
          
          		if enemy.Alive then
          
          			local d = enemy:GetDistance(now)
          
          			enemy.Distance = d
          
          			enemy.Pos = enemy.Path:PositionAt(d)
          
          			local bus = enemy.Bus
          
          			if bus:Has("OnTick") then
          
          				bus:Fire("OnTick", enemy, dt)
          
          			end
          
          			if enemy.Alive and d >= enemy.Path.Length then
          
          				leaked = leaked or {}
          
          				table.insert(leaked, enemy)
          
          			end
          
          		end
          
          	end
          
          	if leaked then
          
          		for _, enemy in ipairs(leaked) do
          
          			enemy:Leak()
          
          		end
          
          	end
          
          end
          
          
          function World.Step(dt, now)
          
          	World.Update(now, dt)
          
          	for _, tower in pairs(World.Towers) do
          
          		if tower.Alive then
          
          			tower:Step(dt, now)
          
          		end
          
          	end
          
          end
          
          
          function World.QueryEnemies(center, radius)
          
          	local r2, cx, cz = radius * radius, center.X, center.Z
          
          	local out = {}
          
          	for _, e in pairs(World.Enemies) do
          
          		if e.Alive then
          
          			local dx, dz = e.Pos.X - cx, e.Pos.Z - cz
          
          			if dx * dx + dz * dz <= r2 then
          
          				table.insert(out, e)
          
          			end
          
          		end
          
          	end
          
          	return out
          
          end
          
          
          function World.QueryTowers(center, radius)
          
          	local r2, cx, cz = radius * radius, center.X, center.Z
          
          	local out = {}
          
          	for _, t in pairs(World.Towers) do
          
          		if t.Alive then
          
          			local dx, dz = t.Position.X - cx, t.Position.Z - cz
          
          			if dx * dx + dz * dz <= r2 then
          
          				table.insert(out, t)
          
          			end
          
          		end
          
          	end
          
          	return out
          
          end
          
          
          return World
          
          
        SOURCE_END
      - AdminCommands [ModuleScript]
        PATH: game.ServerScriptService.Server.AdminCommands
        SOURCE_START
          --[[
          
          	AdminCommands: ações de administrador (servidor decide; o cliente só pede).
          
          	  AdminGive { Amount = n, Target = "nome" | "me" | "all" }  -> soma moedas (as da partida) ao jogador
          
          	Quem pode usar: qualquer um no Studio (teste), o dono do jogo (usuário ou dono do grupo) e os UserIds de ADMIN_USER_IDS.
          
          	Novos comandos = novo Requests.Handle aqui + uma entrada em Client/ChatCommands.
          
          ]]
          
          local Players = game:GetService("Players")
          
          local RunService = game:GetService("RunService")
          
          
          local Requests = require(script.Parent.Requests)
          
          local Economy = require(script.Parent.Economy)
          
          
          -- UserIds extras com permissão (ex.: { 7571418308, 7761350367 })
          
          local ADMIN_USER_IDS = {7571418308, 7761350367}
          
          
          local MAX_AMOUNT = 10000000000000000000000000000000000000000000000
          
          
          local AdminCommands = {}
          
          
          local function fail(code)
          
          	return { Ok = false, Error = code }
          
          end
          
          
          local function isAdmin(player)
          
          	if RunService:IsStudio() then
          
          		return true
          
          	end
          
          	if table.find(ADMIN_USER_IDS, player.UserId) then
          
          		return true
          
          	end
          
          	if game.CreatorType == Enum.CreatorType.User then
          
          		return player.UserId == game.CreatorId
          
          	end
            -  Editar
  18:22:18.460  ========== END PART 26 ==========  -  Editar
  18:22:18.460   ▶  (x2)  -  Editar
  18:22:18.461  ========== PROJECT EXPORT PART 27 ==========  -  Editar
  18:22:18.461            	if game.CreatorType == Enum.CreatorType.Group then
          
          		local ok, rank = pcall(function()
          
          			return player:GetRankInGroup(game.CreatorId)
          
          		end)
          
          		return ok and rank == 255
          
          	end
          
          	return false
          
          end
          
          
          -- "me"/"eu", "all"/"todos", nome ou nome de exibição (completo ou só o começo, se for único)
          
          local function resolveTargets(requester, token)
          
          	local t = token:lower()
          
          	if t == "me" or t == "eu" then
          
          		return { requester }
          
          	end
          
          	if t == "all" or t == "todos" then
          
          		return Players:GetPlayers()
          
          	end
          
          	local partial = {}
          
          	for _, p in ipairs(Players:GetPlayers()) do
          
          		local name, display = p.Name:lower(), p.DisplayName:lower()
          
          		if name == t or display == t then
          
          			return { p }
          
          		end
          
          		if name:sub(1, #t) == t or display:sub(1, #t) == t then
          
          			table.insert(partial, p)
          
          		end
          
          	end
          
          	if #partial == 1 then
          
          		return partial
          
          	end
          
          	if #partial > 1 then
          
          		return nil, "AmbiguousPlayer"
          
          	end
          
          	return nil, "PlayerNotFound"
          
          end
          
          
          function AdminCommands.Init()
          
          	Requests.Handle("AdminGive", function(player, p)
          
          		if type(p) ~= "table" or type(p.Amount) ~= "number" or type(p.Target) ~= "string" or #p.Target > 40 then
          
          			return fail("BadRequest")
          
          		end
          
          		if not isAdmin(player) then
          
          			return fail("NotAuthorized")
          
          		end
          
          		local amount = p.Amount
          
          		if amount ~= amount or amount < 1 or amount > MAX_AMOUNT or amount % 1 ~= 0 then
          
          			return fail("BadAmount")
          
          		end
          
          		local targets, err = resolveTargets(player, p.Target)
          
          		if not targets then
          
          			return fail(err)
          
          		end
          
          		local names = {}
          
          		for _, target in ipairs(targets) do
          
          			local before = Economy.Get(target)
          
          			Economy.Add(target, amount)
          
          			if Economy.Get(target) > before then
          
          				table.insert(names, target.Name)
          
          			end
          
          		end
          
          		if #names == 0 then
          
          			return fail("TargetNotReady") -- jogador ainda sem carteira (não entrou na partida)
          
          		end
          
          		print(("[Admin] %s deu %d moedas para %s"):format(player.Name, amount, table.concat(names, ", ")))
          
          		return { Ok = true, Amount = amount, Names = names }
          
          	end)
          
          end
          
          
          return AdminCommands
          
          
        SOURCE_END
      - Classes [Folder]
        - Enemy [ModuleScript]
          PATH: game.ServerScriptService.Server.Classes.Enemy
          SOURCE_START
            --[[
            
            	Enemy (OOP). Zero conhecimento de tipos de inimigo, de efeitos ou de passivas.
            
            	- movimento: âncora (DistanceAnchor, TimeAnchor) + velocidade; mudou a velocidade => rebase + replica
            
            	- efeitos: enemy.Statuses é gerido pelo StatusEffectManager
            
            	- passivas: PassiveEngine liga os módulos ao enemy.Bus
            
            	Hooks disparados no Bus do inimigo: OnSpawn, OnTick, OnEnemyTakeDamage(enemy, amount, type, source, hit),
            
            	OnDeath(enemy, killer), OnLeak(enemy). Em OnEnemyTakeDamage, passivas alteram `hit.Amount`.
            
            ]]
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            local Registry = require(ReplicatedStorage.Shared.Registry)
            
            local EventBus = require(ReplicatedStorage.Shared.EventBus)
            
            local PassiveEngine = require(script.Parent.Parent.PassiveEngine)
            
            local StatusEffectManager = require(script.Parent.Parent.StatusEffectManager)
            
            
            local G = EventBus.Global
            
            local Enemy = {}
            
            Enemy.__index = Enemy
            
            local nextId = 0
            
            
            local function now()
            
            	return workspace:GetServerTimeNow()
            
            end
            
            
            function Enemy.new(enemyId, opts)
            
            	local cfg = Registry.Of("Enemies"):Require(enemyId)
            
            	local map = assert(opts.Map, "[Enemy] sem mapa carregado")
            
            	local mult = map.Config.Multipliers or {}
            
            	local pathId = opts.PathId or cfg.PathId or map.Config.DefaultPath
            
            	local path = assert(map.Paths[pathId], "[Enemy] caminho inexistente: " .. tostring(pathId))
            
            	local t = now()
            
            
            	nextId += 1
            
            	local self = setmetatable({}, Enemy)
            
            	self.Id = nextId
            
            	self.ConfigId = enemyId
            
            	self.Config = cfg
            
            	self.Alive = true
            
            	self.Destroyed = false
            
            	self.PathId = pathId
            
            	self.Path = path
            
            	self.MaxHealth = cfg.Health * (mult.EnemyHealth or 1) * (opts.HealthMultiplier or 1)
            
            	self.Health = self.MaxHealth
            
            	self.BaseSpeed = cfg.Speed * (mult.EnemySpeed or 1)
            
            	self.Reward = cfg.Reward * (mult.Reward or 1)
            
            	self.LivesDamage = cfg.LivesDamage or 1
            
            	self.TagSet = {}
            
            	for _, tag in ipairs(cfg.Tags or {}) do
            
            		self.TagSet[tag] = true
            
            	end
            
            	self.SpeedModifiers = {}
            
            	self.SpeedMultiplier = 1
            
            	self.DistanceAnchor = opts.StartDistance or 0
            
            	self.TimeAnchor = t
            
            	self.Distance = self.DistanceAnchor
            
            	self.Pos = path:PositionAt(self.Distance)
            
            	self.Statuses = {}
            
            	self.StatusLock = {}
            
            	self.Bus = EventBus.new()
            
            	PassiveEngine.Attach(self, cfg.Passives)
            
            	return self
            
            end
            
            
            function Enemy:HasTag(tag)
            
            	return self.TagSet[tag] == true
            
            end
            
            
            function Enemy:GetSpeed()
            
            	return self.BaseSpeed * self.SpeedMultiplier
            
            end
            
            
            function Enemy:GetDistance(t)
            
            	local d = self.DistanceAnchor + self:GetSpeed() * (t - self.TimeAnchor)
            
            	return math.min(d, self.Path.Length)
            
            end
            
            
            -- key -> multiplicador (nil remove). Efeitos usam isto; o Enemy não sabe quais efeitos existem.
            
            function Enemy:SetSpeedModifier(key, mult)
            
            	if not self.Alive then
            
            		return
            
            	end
            
            	local t = now()
            
            	self.DistanceAnchor = self:GetDistance(t)
            
            	self.TimeAnchor = t
            
            	self.SpeedModifiers[key] = mult
            
            	local product = 1
            
            	for _, m in pairs(self.SpeedModifiers) do
            
            		product *= m
            
            	end
            
            	self.SpeedMultiplier = product
            
            	G:Fire("EnemyMotionChanged", self)
            
            end
            
            
            function Enemy:IsImmuneToDamage(damageType)
            
            	local imm = self.Config.Immunities
            
            	return imm ~= nil and imm.Damage ~= nil and table.find(imm.Damage, damageType) ~= nil
            
            end
            
            
            function Enemy:IsImmuneToStatus(def)
            
            	local imm = self.Config.Immunities
            
            	local list = imm and imm.Status
            
            	if not list then
            
            		return false
            
            	end
            
            	if table.find(list, def.Id) then
            
            		return true
            
            	end
            
            	for _, tag in ipairs(def.Tags or {}) do
            
            		if table.find(list, tag) then
            
            			return true
            
            		end
            
            	end
            
            	return false
            
            end
            
            
            function Enemy:TakeDamage(amount, damageType, sourceTower)
            
            	if not self.Alive or amount <= 0 then
            
            		return 0
            
            	end
            
            	if self:IsImmuneToDamage(damageType) then
            
            		return 0
            
            	end
            
            	local dm = self.Config.DamageMultipliers
            
            	if dm and dm[damageType] then
            
            		amount *= dm[damageType]
            
            	end
            
            	local hit = { Amount = amount, Type = damageType, Source = sourceTower }
            
            	self.Bus:Fire("OnEnemyTakeDamage", self, amount, damageType, sourceTower, hit)
            
            	local final = math.max(hit.Amount, 0)
            
            	if final <= 0 or not self.Alive then
            
            		return 0
            
            	end
            
            	local dealt = math.min(final, self.Health)
            
            	self.Health -= dealt
            
            	G:Fire("EnemyHealthChanged", self)
            
            	if self.Health <= 0 then
            
            		self:Die(sourceTower)
            
            	end
            
            	return dealt
            
            end
            
            
            function Enemy:Heal(amount)
            
            	if not self.Alive then
            
            		return
            
            	end
            
            	self.Health = math.min(self.MaxHealth, self.Health + amount)
            
            	G:Fire("EnemyHealthChanged", self)
            
            end
            
            
            function Enemy:Die(killer)
            
            	if not self.Alive then
            
            		return
            
            	end
            
            	self.Alive = false
            
            	self.KilledBy = killer
            
            	self.Bus:Fire("OnDeath", self, killer)
            
            	if killer and killer.Alive then
            
            		killer.Bus:Fire("OnEnemyKill", killer, self)
            
            	end
            
            	G:Fire("EnemyKilled", self, killer)
              -  Editar
  18:22:18.462  ========== END PART 27 ==========  -  Editar
  18:22:18.462   ▶  (x2)  -  Editar
  18:22:18.463  ========== PROJECT EXPORT PART 28 ==========  -  Editar
  18:22:18.463              	self:Destroy("Killed")
            
            end
            
            
            function Enemy:Leak()
            
            	if not self.Alive then
            
            		return
            
            	end
            
            	self.Bus:Fire("OnLeak", self)
            
            	self.Alive = false
            
            	G:Fire("EnemyLeaked", self)
            
            	self:Destroy("Leaked")
            
            end
            
            
            function Enemy:Destroy(reason)
            
            	if self.Destroyed then
            
            		return
            
            	end
            
            	self.Destroyed = true
            
            	self.Alive = false
            
            	StatusEffectManager.ClearAll(self, reason)
            
            	PassiveEngine.Detach(self)
            
            	G:Fire("EnemyRemoved", self, reason or "Removed")
            
            	self.Bus:Destroy()
            
            end
            
            
            return Enemy
            
            
          SOURCE_END
        - Tower [ModuleScript]
          PATH: game.ServerScriptService.Server.Classes.Tower
          SOURCE_START
            --[[
            
            	Tower (OOP). Agnóstica: só lê o config do seu ID. Não existe if/else sobre nomes de torre, de efeito ou de passiva.
            
            	- Stats finais = base do config + modificadores nomeados (upgrades, auras...) via SetModifier(key, {Stat={Add,Mul,Set}})
            
            	- Alvo: função Score do modo de targeting (TargetingConfig)
            
            	- Ataque: OnPreAttack (passivas mexem em damageData) -> projétil (tempo de voo) -> dano/efeitos -> OnPostAttack
            
            	Hooks no Bus da torre: OnTowerPlaced, OnTargetSelected, OnPreAttack, OnPostAttack, OnEnemyKill, OnTick,
            
            	OnUpgrade, OnTowerRemoved.
            
            ]]
            
            local ReplicatedStorage = game:GetService("ReplicatedStorage")
            
            local Registry = require(ReplicatedStorage.Shared.Registry)
            
            local EventBus = require(ReplicatedStorage.Shared.EventBus)
            
            local PassiveEngine = require(script.Parent.Parent.PassiveEngine)
            
            local StatusEffectManager = require(script.Parent.Parent.StatusEffectManager)
            
            local World = require(script.Parent.Parent.World)
            
            
            local G = EventBus.Global
            
            local SCAN_INTERVAL = 0.1
            
            local STAT_DEFAULTS = { AttackSpeed = 1 }
            
            
            local Tower = {}
            
            Tower.__index = Tower
            
            local nextId = 0
            
            
            local function toSet(list)
            
            	local s = {}
            
            	for _, v in ipairs(list or {}) do
            
            		s[v] = true
            
            	end
            
            	return s
            
            end
            
            
            function Tower.new(towerId, owner, position, paid)
            
            	local cfg = Registry.Of("Towers"):Require(towerId)
            
            	nextId += 1
            
            	local self = setmetatable({}, Tower)
            
            	self.Id = nextId
            
            	self.ConfigId = towerId
            
            	self.Config = cfg
            
            	self.Owner = owner
            
            	self.Position = position
            
            	self.Alive = true
            
            	self.Announced = false
            
            	self.Bus = EventBus.new()
            
            	self.Tiers = {}
            
            	self.Modifiers = {}
            
            	self.Stats = {}
            
            	self.Effects = {}
            
            	self.TagSet = toSet(cfg.Tags)
            
            	self.TargetTagSet = cfg.TargetTags and toSet(cfg.TargetTags) or nil
            
            	self.TargetMode = cfg.Targeting and cfg.Targeting.Default or "First"
            
            	self.Invested = paid or cfg.Cost
            
            	self.ReadyAt = 0
            
            	self.NextScan = 0
            
            	self.Pending = {}
            
            	self.Target = nil
            
            	for _, e in ipairs(cfg.Effects or {}) do
            
            		self:_mergeEffect(e)
            
            	end
            
            	self:Recompute()
            
            	PassiveEngine.Attach(self, cfg.Passives)
            
            	return self
            
            end
            
            
            function Tower:HasTag(tag)
            
            	return self.TagSet[tag] == true
            
            end
            
            
            function Tower:_mergeEffect(effect)
            
            	local e = type(effect) == "string" and { Id = effect } or table.clone(effect)
            
            	for i, existing in ipairs(self.Effects) do
            
            		if existing.Id == e.Id then
            
            			self.Effects[i] = e
            
            			return
            
            		end
            
            	end
            
            	table.insert(self.Effects, e)
            
            end
            
            
            function Tower:Recompute()
            
            	local base = self.Config.Stats or {}
            
            	local add, mul, set, keys = {}, {}, {}, {}
            
            	for stat in pairs(base) do
            
            		keys[stat] = true
            
            	end
            
            	for _, mods in pairs(self.Modifiers) do
            
            		for stat, m in pairs(mods) do
            
            			keys[stat] = true
            
            			if m.Add then
            
            				add[stat] = (add[stat] or 0) + m.Add
            
            			end
            
            			if m.Mul then
            
            				mul[stat] = (mul[stat] or 1) * m.Mul
            
            			end
            
            			if m.Set ~= nil then
            
            				set[stat] = m.Set
            
            			end
            
            		end
            
            	end
            
            	local stats = {}
            
            	for stat in pairs(keys) do
            
            		local b = base[stat]
            
            		if b == nil then
            
            			b = STAT_DEFAULTS[stat] or 0
            
            		end
            
            		local v = b
            
            		if type(b) == "number" then
            
            			v = (b + (add[stat] or 0)) * (mul[stat] or 1)
            
            		end
            
            		if set[stat] ~= nil then
            
            			v = set[stat]
            
            		end
            
            		stats[stat] = v
            
            	end
            
            	if stats.AttackSpeed == nil then
            
            		stats.AttackSpeed = 1
            
            	end
            
            	self.Stats = stats
            
            	self.CanAttack = (stats.Range or 0) > 0 and (stats.Cooldown or 0) > 0
            
            	if self.Announced then
            
            		G:Fire("TowerUpdated", self)
            
            	end
            
            end
            
            
            function Tower:SetModifier(key, mods)
            
            	self.Modifiers[key] = mods
            
            	self:Recompute()
            
            end
            
            
            function Tower:ClearModifier(key)
            
            	if self.Modifiers[key] then
            
            		self.Modifiers[key] = nil
            
            		self:Recompute()
            
            	end
            
            end
            
            
            function Tower:Activate()
            
            	self.Announced = true
            
            	G:Fire("TowerPlaced", self)
            
            	self.Bus:Fire("OnTowerPlaced", self)
            
            end
            
            
            function Tower:SetTargetMode(mode)
            
            	local modes = self.Config.Targeting and self.Config.Targeting.Modes
            
            	if not modes or not table.find(modes, mode) then
            
            		return false
            
            	end
            
            	self.TargetMode = mode
            
            	self.Target = nil
            
            	G:Fire("TowerUpdated", self)
            
            	return true
            
            end
            
            
            -- ---------------------------------------------------------------- upgrades
            
            function Tower:GetPath(pathId)
            
            	local up = self.Config.Upgrades
            
            	if not up then
            
            		return nil
            
            	end
            
            	for _, path in ipairs(up.Paths) do
            
            		if path.Id == pathId then
            
            			return path
            
            		end
            
            	end
            
            	return nil
            
            end
            
            
            -- devolve tierDef, ou nil + motivo
            
            function Tower:GetNextTier(pathId)
            
            	local path = self:GetPath(pathId)
            
            	if not path then
            
            		return nil, "UnknownPath"
            
            	end
            
            	local tier = self.Tiers[pathId] or 0
            
            	local nextDef = path.Tiers[tier + 1]
            
            	if not nextDef then
            
            		return nil, "MaxTier"
            
            	end
            
            	local rules = self.Config.Upgrades.Rules
            
            	if rules and rules.SecondaryMaxTier and tier + 1 > rules.SecondaryMaxTier then
            
            		for _, other in ipairs(self.Config.Upgrades.Paths) do
            
            			if other.Id ~= pathId and (self.Tiers[other.Id] or 0) > rules.SecondaryMaxTier then
            
            				return nil, "PathLocked"
            
            			end
            
            		end
            
            	end
            
            	return nextDef
            
            end
            
            
            function Tower:Upgrade(pathId, paid)
            
            	local def = self:GetNextTier(pathId)
            
            	if not def then
            
            		return false
            
            	end
            
            	local tier = (self.Tiers[pathId] or 0) + 1
            
            	self.Tiers[pathId] = tier
            
            	self.Invested += paid or def.Cost
            
            	if def.Modifiers then
            
            		self.Modifiers[("Upgrade:%s:%d"):format(pathId, tier)] = def.Modifiers
            
            	end
            
            	for _, e in ipairs(def.AddEffects or {}) do
            
            		self:_mergeEffect(e)
            
            	end
            
            	if def.AddPassives then
            
            		PassiveEngine.Attach(self, def.AddPassives)
            
            	end
            
            	for passiveId, overrides in pairs(def.PassiveParams or {}) do
            
            		PassiveEngine.SetParams(self, passiveId, overrides)
            
            	end
            
            	self:Recompute()
            
            	self.Bus:Fire("OnUpgrade", self, pathId, tier)
            
            	return true
            
            end
            
            
            -- ---------------------------------------------------------------- combate
              -  Editar
  18:22:18.463  ========== END PART 28 ==========  -  Editar
  18:22:18.463   ▶  (x2)  -  Editar
  18:22:18.464  ========== PROJECT EXPORT PART 29 ==========  -  Editar
  18:22:18.465              function Tower:AcquireTarget()
            
            	local targeting = Registry.Of("Targeting")
            
            	local mode = targeting:Get(self.TargetMode) or targeting:Get("First")
            
            	local range = self.Stats.Range
            
            	local r2 = range * range
            
            	local px, pz = self.Position.X, self.Position.Z
            
            	local allowed = self.TargetTagSet
            
            	local best, bestScore = nil, -math.huge
            
            
            	for _, enemy in pairs(World.Enemies) do
            
            		if enemy.Alive then
            
            			local dx, dz = enemy.Pos.X - px, enemy.Pos.Z - pz
            
            			local d2 = dx * dx + dz * dz
            
            			if d2 <= r2 then
            
            				local ok = allowed == nil
            
            				if not ok then
            
            					for tag in pairs(allowed) do
            
            						if enemy.TagSet[tag] then
            
            							ok = true
            
            							break
            
            						end
            
            					end
            
            				end
            
            				if ok then
            
            					local score = mode.Score(enemy, self, d2)
            
            					if score > bestScore then
            
            						best, bestScore = enemy, score
            
            					end
            
            				end
            
            			end
            
            		end
            
            	end
            
            
            	if best ~= self.Target then
            
            		self.Target = best
            
            		if best then
            
            			self.Bus:Fire("OnTargetSelected", self, best)
            
            		end
            
            	end
            
            	return best
            
            end
            
            
            function Tower:Attack(target, now)
            
            	local s = self.Stats
            
            	local data = {
            
            		Amount = s.Damage or 0,
            
            		DamageType = s.DamageType or "Physical",
            
            		Splash = s.SplashRadius or 0,
            
            		Effects = table.clone(self.Effects),
            
            		Tower = self,
            
            		Target = target,
            
            		ImpactPos = target.Pos,
            
            	}
            
            	-- passivas interceptam aqui (crítico, execução, stacks...) alterando damageData
            
            	self.Bus:Fire("OnPreAttack", self, target, data)
            
            
            	local interval = (s.Cooldown or 1) / math.max(s.AttackSpeed or 1, 0.05)
            
            	self.ReadyAt = now + interval
            
            
            	local speed = s.ProjectileSpeed or 0
            
            	local travel = s.Windup or 0 -- Windup = segundos até o tiro sair (igual ao ReleaseTime da animação)
            
            	if speed > 0 then
            
            		local dx, dz = target.Pos.X - self.Position.X, target.Pos.Z - self.Position.Z
            
            		travel += math.sqrt(dx * dx + dz * dz) / speed
            
            	end
            
            	G:Fire("TowerFired", self, target, now, now + travel)
            
            
            	local hit = { At = now + travel, Data = data, Target = target }
            
            	if travel <= 0 then
            
            		self:_resolveHit(hit)
            
            	else
            
            		table.insert(self.Pending, hit)
            
            	end
            
            end
            
            
            function Tower:_resolveHit(hit)
            
            	local data, target = hit.Data, hit.Target
            
            	local center = target.Alive and target.Pos or data.ImpactPos
            
            	local victims
            
            	if data.Splash > 0 then
            
            		victims = World.QueryEnemies(center, data.Splash)
            
            	elseif target.Alive then
            
            		victims = { target }
            
            	else
            
            		victims = {}
            
            	end
            
            
            	for _, enemy in ipairs(victims) do
            
            		if enemy.Alive then
            
            			local dealt = 0
            
            			if data.Amount > 0 then
            
            				dealt = enemy:TakeDamage(data.Amount, data.DamageType, self)
            
            			end
            
            			for _, eff in ipairs(data.Effects) do
            
            				if enemy.Alive and (eff.Chance == nil or math.random() <= eff.Chance) then
            
            					StatusEffectManager.Apply(enemy, eff.Id, { Source = self, Params = eff.Params })
            
            				end
            
            			end
            
            			self.Bus:Fire("OnPostAttack", self, enemy, dealt)
            
            		end
            
            	end
            
            end
            
            
            function Tower:Step(dt, now)
            
            	local bus = self.Bus
            
            	if bus:Has("OnTick") then
            
            		bus:Fire("OnTick", self, dt)
            
            	end
            
            
            	local pending = self.Pending
            
            	local i = 1
            
            	while i <= #pending do
            
            		local hit = pending[i]
            
            		if hit.At <= now then
            
            			table.remove(pending, i)
            
            			self:_resolveHit(hit)
            
            		else
            
            			i += 1
            
            		end
            
            	end
            
            
            	if not self.CanAttack or now < self.ReadyAt or now < self.NextScan then
            
            		return
            
            	end
            
            	local target = self:AcquireTarget()
            
            	if not target then
            
            		self.NextScan = now + SCAN_INTERVAL
            
            		return
            
            	end
            
            	self:Attack(target, now)
            
            end
            
            
            function Tower:Destroy()
            
            	if not self.Alive then
            
            		return
            
            	end
            
            	self.Bus:Fire("OnTowerRemoved", self)
            
            	self.Alive = false
            
            	PassiveEngine.Detach(self)
            
            	table.clear(self.Pending)
            
            	G:Fire("TowerRemoved", self)
            
            	self.Bus:Destroy()
            
            end
            
            
            return Tower
            
            
          SOURCE_END
    - TowerDefense [Folder]
      - GameManager [Script]
        PATH: game.ServerScriptService.TowerDefense.GameManager
        SOURCE_START
          -- GameManager - Handles waves, enemy spawning, economy, and base health
          
          local Players = game:GetService("Players")
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
          
          local Workspace = game:GetService("Workspace")
          
          
          local Remotes = ReplicatedStorage.TowerDefense.Remotes
          
          local GameUpdate = Remotes.GameUpdate
          
          local StartWaveRemote = Remotes.StartWave
          
          
          -- Game State
          
          local GameState = {
          
              Money = 250,
          
              BaseHealth = 100,
          
              Wave = 0,
          
              WaveActive = false,
          
              Enemies = {},
          
              EnemiesAlive = 0,
          
              GameOver = false,
          
          }
          
          
          local MAX_WAVES = 20
          
          
          -- Waypoints for enemy movement
          
          local Waypoints = {}
          
          local wpFolder = Workspace:FindFirstChild("TowerDefenseMap") and Workspace.TowerDefenseMap:FindFirstChild("Waypoints")
          
          if wpFolder then
          
              for i = 1, 100 do
          
                  local wp = wpFolder:FindFirstChild("WP" .. i)
          
                  if wp then
          
                      table.insert(Waypoints, wp.Position)
          
                  else
          
                      break
          
                  end
          
              end
          
          end
          
          
          -- Enemy types per wave
          
          local function getWaveEnemies(wave)
          
              local enemies = {}
          
              local count = 5 + wave * 2
          
              for i = 1, count do
          
                  local hp = 20 + wave * 15
          
                  local speed = 6 + wave * 0.3
          
                  if wave >= 5 and i % 5 == 0 then
          
                      hp = hp * 3
          
                      speed = speed * 0.7
          
                      enemies[i] = {HP = hp, Speed = speed, Type = "Tank", Color = Color3.fromRGB(80, 80, 80), Size = Vector3.new(4, 6, 4)}
          
                  elseif wave >= 10 and i % 7 == 0 then
          
                      hp = hp * 2
          
                      speed = speed * 1.5
          
                      enemies[i] = {HP = hp, Speed = speed, Type = "Fast", Color = Color3.fromRGB(255, 50, 50), Size = Vector3.new(2.5, 4, 2.5)}
          
                  else
          
                      enemies[i] = {HP = hp, Speed = speed, Type = "Normal", Color = Color3.fromRGB(150, 150, 150), Size = Vector3.new(3, 5, 3)}
          
                  end
          
              end
          
              -- Boss wave every 5 waves
          
              if wave % 5 == 0 then
          
                  local bossHp = 200 + wave * 50
          
                  table.insert(enemies, {HP = bossHp, Speed = 4, Type = "Boss", Color = Color3.fromRGB(255, 0, 0), Size = Vector3.new(6, 10, 6)})
          
              end
          
              return enemies
          
          end
          
          
          -- Create enemy
          
          local function createEnemy(data, index)
          
              local enemy = Instance.new("Part")
          
              enemy.Name = "Enemy_" .. index
          
              enemy.Size = data.Size
          
              enemy.Position = Waypoints[1] or Vector3.new(0, 5, 180)
          
              enemy.Anchored = true
          
              enemy.CanCollide = false
          
              enemy.Color = data.Color
          
              enemy.Material = Enum.Material.SmoothPlastic
          
              enemy.TopSurface = Enum.SurfaceType.Smooth
          
              
          
              -- Health bar
          
              local billboard = Instance.new("BillboardGui")
          
              billboard.Name = "HealthBar"
          
              billboard.Size = UDim2.new(0, 100, 0, 15)
          
              billboard.AlwaysOnTop = true
          
              billboard.StudsOffset = Vector3.new(0, data.Size.Y / 2 + 2, 0)
          
              billboard.Parent = enemy
          
              
          
              local bg = Instance.new("Frame")
          
              bg.Size = UDim2.new(1, 0, 1, 0)
          
              bg.BackgroundColor3 = Color3.fromRGB(50, 0, 0)
          
              bg.BorderSizePixel = 0
          
              bg.Parent = billboard
          
              
          
              local fill = Instance.new("Frame")
            -  Editar
  18:22:18.465  ========== END PART 29 ==========  -  Editar
  18:22:18.465   ▶  (x2)  -  Editar
  18:22:18.465  ========== PROJECT EXPORT PART 30 ==========  -  Editar
  18:22:18.466                fill.Name = "Fill"
          
              fill.Size = UDim2.new(1, 0, 1, 0)
          
              fill.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
          
              fill.BorderSizePixel = 0
          
              fill.Parent = bg
          
              
          
              -- Store enemy data
          
              enemy:SetAttribute("MaxHP", data.HP)
          
              enemy:SetAttribute("HP", data.HP)
          
              enemy:SetAttribute("Speed", data.Speed)
          
              enemy:SetAttribute("Type", data.Type)
          
              enemy:SetAttribute("WaypointIndex", 1)
          
              enemy:SetAttribute("SlowTimer", 0)
          
              enemy:SetAttribute("Alive", true)
          
              
          
              enemy.Parent = Workspace
          
              
          
              return enemy
          
          end
          
          
          -- Update health bar
          
          local function updateHealthBar(enemy)
          
              local hp = enemy:GetAttribute("HP")
          
              local maxHp = enemy:GetAttribute("MaxHP")
          
              if not hp or not maxHp then return end
          
              local billboard = enemy:FindFirstChild("HealthBar")
          
              if billboard then
          
                  local fill = billboard:FindFirstChild("Frame") and billboard.Frame:FindFirstChild("Fill")
          
                  if fill then
          
                      local ratio = math.clamp(hp / maxHp, 0, 1)
          
                      fill.Size = UDim2.new(ratio, 0, 1, 0)
          
                      if ratio > 0.5 then
          
                          fill.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
          
                      elseif ratio > 0.25 then
          
                          fill.BackgroundColor3 = Color3.fromRGB(255, 255, 0)
          
                      else
          
                          fill.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
          
                      end
          
                  end
          
              end
          
          end
          
          
          -- Move enemies along waypoints
          
          local function updateEnemies(dt)
          
              for _, enemy in ipairs(GameState.Enemies) do
          
                  if not enemy.Parent then continue end
          
                  if not enemy:GetAttribute("Alive") then continue end
          
                  
          
                  local wpIndex = enemy:GetAttribute("WaypointIndex")
          
                  if wpIndex >= #Waypoints then
          
                      -- Reached the base
          
                      local hp = enemy:GetAttribute("HP")
          
                      if hp and hp > 0 then
          
                          GameState.BaseHealth = GameState.BaseHealth - (enemy:GetAttribute("Type") == "Boss" and 10 or 5)
          
                          if GameState.BaseHealth <= 0 then
          
                              GameState.BaseHealth = 0
          
                              GameState.GameOver = true
          
                          end
          
                      end
          
                      enemy:SetAttribute("Alive", false)
          
                      enemy:Destroy()
          
                      GameState.EnemiesAlive = GameState.EnemiesAlive - 1
          
                      continue
          
                  end
          
                  
          
                  local target = Waypoints[wpIndex + 1]
          
                  if not target then continue end
          
                  
          
                  local speed = enemy:GetAttribute("Speed")
          
                  local slowTimer = enemy:GetAttribute("SlowTimer")
          
                  if slowTimer and slowTimer > 0 then
          
                      speed = speed * 0.5
          
                      enemy:SetAttribute("SlowTimer", slowTimer - dt)
          
                  end
          
                  
          
                  local pos = enemy.Position
          
                  local direction = (target - pos)
          
                  local distance = direction.Magnitude
          
                  local move = speed * dt
          
                  
          
                  if move >= distance then
          
                      enemy.Position = target
          
                      enemy:SetAttribute("WaypointIndex", wpIndex + 1)
          
                  else
          
                      enemy.Position = pos + direction.Unit * move
          
                  end
          
                  
          
                  updateHealthBar(enemy)
          
              end
          
          end
          
          
          -- Spawn a wave
          
          local function spawnWave(waveNum)
          
              local enemyData = getWaveEnemies(waveNum)
          
              GameState.EnemiesAlive = #enemyData
          
              
          
              for i, data in ipairs(enemyData) do
          
                  if GameState.GameOver then break end
          
                  task.spawn(function()
          
                      task.wait((i - 1) * 1.5)
          
                      if GameState.GameOver then return end
          
                      local enemy = createEnemy(data, i)
          
                      table.insert(GameState.Enemies, enemy)
          
                  end)
          
              end
          
          end
          
          
          -- Send game state to clients
          
          local function sendGameState()
          
              GameUpdate:FireAllClients({
          
                  Money = GameState.Money,
          
                  BaseHealth = GameState.BaseHealth,
          
                  Wave = GameState.Wave,
          
                  WaveActive = GameState.WaveActive,
          
                  EnemiesAlive = GameState.EnemiesAlive,
          
                  GameOver = GameState.GameOver,
          
                  MaxWaves = MAX_WAVES,
          
              })
          
          end
          
          
          -- Start wave handler
          
          StartWaveRemote.OnServerEvent:Connect(function(player)
          
              if GameState.WaveActive or GameState.GameOver then return end
          
              if GameState.Wave >= MAX_WAVES then return end
          
              
          
              GameState.Wave = GameState.Wave + 1
          
              GameState.WaveActive = true
          
              sendGameState()
          
              
          
              spawnWave(GameState.Wave)
          
          end
          
          
          -- Expose for TowerManager
          
          _G.TowerDefense = _G.TowerDefense or {}
          
          _G.TowerDefense.GetEnemies = function()
          
              local alive = {}
          
              for _, enemy in ipairs(GameState.Enemies) do
          
                  if enemy.Parent and enemy:GetAttribute("Alive") then
          
                      table.insert(alive, enemy)
          
                  end
          
              end
          
              return alive
          
          end
          
          
          _G.TowerDefense.DamageEnemy = function(enemy, damage)
          
              if not enemy or not enemy.Parent then return end
          
              if not enemy:GetAttribute("Alive") then return end
          
              local hp = enemy:GetAttribute("HP")
          
              if not hp then return end
          
              hp = hp - damage
          
              enemy:SetAttribute("HP", hp)
          
              if hp <= 0 then
          
                  enemy:SetAttribute("Alive", false)
          
                  GameState.Money = GameState.Money + (enemy:GetAttribute("Type") == "Boss" and 100 or 15)
          
                  GameState.EnemiesAlive = GameState.EnemiesAlive - 1
          
                  enemy:Destroy()
          
                  sendGameState()
          
              end
          
          end
          
          
          _G.TowerDefense.SlowEnemy = function(enemy, duration)
          
              if not enemy or not enemy.Parent then return end
          
              if not enemy:GetAttribute("Alive") then return end
          
              enemy:SetAttribute("SlowTimer", duration)
          
          end
          
          
          _G.TowerDefense.AddMoney = function(amount)
          
              GameState.Money = GameState.Money + amount
          
          end
          
          
          _G.TowerDefense.GetMoney = function()
          
              return GameState.Money
          
          end
          
          
          _G.TowerDefense.SpendMoney = function(amount)
          
              if GameState.Money >= amount then
          
                  GameState.Money = GameState.Money - amount
          
                  return true
          
              end
          
              return false
          
          end
          
          
          _G.TowerDefense.GetGameState = function()
          
              return GameState
          
          end
          
          
          _G.TowerDefense.SendGameState = sendGameState
          
          
          -- Main game loop
          
          local lastUpdate = 0
          
          local runService = game:GetService("RunService")
          
          
          runService.Heartbeat:Connect(function(dt)
          
              if GameState.GameOver then return end
          
              
          
              updateEnemies(dt)
          
              
          
              -- Check if wave is complete
          
              if GameState.WaveActive and GameState.EnemiesAlive <= 0 then
          
                  GameState.WaveActive = false
          
                  GameState.Money = GameState.Money + 50 + GameState.Wave * 10 -- Wave completion bonus
          
                  sendGameState()
          
                  
          
                  if GameState.Wave >= MAX_WAVES then
          
                      -- Victory!
          
                      GameUpdate:FireAllClients({
          
                          Money = GameState.Money,
          
                          BaseHealth = GameState.BaseHealth,
          
                          Wave = GameState.Wave,
          
                          WaveActive = false,
          
                          EnemiesAlive = 0,
          
                          GameOver = false,
          
                          Victory = true,
          
                          MaxWaves = MAX_WAVES,
          
                      })
          
                  end
          
              end
          
              
          
              -- Send state periodically
          
              lastUpdate = lastUpdate + dt
          
              if lastUpdate >= 0.5 then
          
                  lastUpdate = 0
          
                  sendGameState()
          
              end
          
          end)
          
          
          -- Initialize
          
          sendGameState()
          
          print("[TowerDefense] GameManager initialized with " .. #Waypoints .. " waypoints")
          
        SOURCE_END
      - TowerManager [Script]
        PATH: game.ServerScriptService.TowerDefense.TowerManager
        SOURCE_START
          -- TowerManager - Handles tower placement, attacking, upgrading, and selling
          
          local Players = game:GetService("Players")
          
          local ReplicatedStorage = game:GetService("ReplicatedStorage")
            -  Editar
  18:22:18.466  ========== END PART 30 ==========  -  Editar
  18:22:18.466   ▶  (x2)  -  Editar
  18:22:18.466  ========== PROJECT EXPORT PART 31 ==========  -  Editar
  18:22:18.466            local Workspace = game:GetService("Workspace")
          
          local RunService = game:GetService("RunService")
          
          
          local TowerData = require(ReplicatedStorage.TowerDefense.TowerData)
          
          local Remotes = ReplicatedStorage.TowerDefense.Remotes
          
          
          local PlaceTowerRemote = Remotes.PlaceTower
          
          local SellTowerRemote = Remotes.SellTower
          
          local UpgradeTowerRemote = Remotes.UpgradeTower
          
          
          local Towers = {} -- Active towers
          
          local TowerIdCounter = 0
          
          
          -- Create tower visual
          
          local function createTowerVisual(towerName, position, color)
          
              local model = Instance.new("Model")
          
              model.Name = towerName
          
              
          
              -- Base platform
          
              local base = Instance.new("Part")
          
              base.Name = "Base"
          
              base.Size = Vector3.new(5, 1, 5)
          
              base.Position = position - Vector3.new(0, 0.5, 0)
          
              base.Anchored = true
          
              base.CanCollide = false
          
              base.Color = Color3.fromRGB(100, 100, 100)
          
              base.Material = Enum.Material.SmoothPlastic
          
              base.TopSurface = Enum.SurfaceType.Smooth
          
              base.Parent = model
          
              
          
              -- Body (representing the character)
          
              local body = Instance.new("Part")
          
              body.Name = "Body"
          
              body.Size = Vector3.new(3, 5, 3)
          
              body.Position = position + Vector3.new(0, 3, 0)
          
              body.Anchored = true
          
              body.CanCollide = false
          
              body.Color = color
          
              body.Material = Enum.Material.SmoothPlastic
          
              body.TopSurface = Enum.SurfaceType.Smooth
          
              body.Parent = model
          
              
          
              -- Head
          
              local head = Instance.new("Part")
          
              head.Name = "Head"
          
              head.Shape = Enum.PartType.Ball
          
              head.Size = Vector3.new(2.5, 2.5, 2.5)
          
              head.Position = position + Vector3.new(0, 6.5, 0)
          
              head.Anchored = true
          
              head.CanCollide = false
          
              head.Color = Color3.fromRGB(255, 220, 180)
          
              head.Material = Enum.Material.SmoothPlastic
          
              head.Parent = model
          
              
          
              -- Name tag
          
              local billboard = Instance.new("BillboardGui")
          
              billboard.Name = "NameTag"
          
              billboard.Size = UDim2.new(0, 150, 0, 40)
          
              billboard.AlwaysOnTop = true
          
              billboard.StudsOffset = Vector3.new(0, 9, 0)
          
              billboard.Parent = model
          
              
          
              local nameLabel = Instance.new("TextLabel")
          
              nameLabel.Size = UDim2.new(1, 0, 0.6, 0)
          
              nameLabel.BackgroundTransparency = 0.3
          
              nameLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
          
              nameLabel.TextColor3 = color
          
              nameLabel.TextScaled = true
          
              nameLabel.Font = Enum.Font.FredokaOne
          
              nameLabel.Text = towerName
          
              nameLabel.Parent = billboard
          
              
          
              local levelLabel = Instance.new("TextLabel")
          
              levelLabel.Name = "LevelLabel"
          
              levelLabel.Size = UDim2.new(1, 0, 0.4, 0)
          
              levelLabel.Position = UDim2.new(0, 0, 0.6, 0)
          
              levelLabel.BackgroundTransparency = 0.3
          
              levelLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
          
              levelLabel.TextColor3 = Color3.fromRGB(255, 255, 0)
          
              levelLabel.TextScaled = true
          
              levelLabel.Font = Enum.Font.FredokaOne
          
              levelLabel.Text = "Lv.1"
          
              levelLabel.Parent = billboard
          
              
          
              model.PrimaryPart = base
          
              return model
          
          end
          
          
          -- Create range indicator
          
          local function createRangeIndicator(position, range)
          
              local indicator = Instance.new("Part")
          
              indicator.Name = "RangeIndicator"
          
              indicator.Shape = Enum.PartType.Cylinder
          
              indicator.Size = Vector3.new(0.1, range * 2, range * 2)
          
              indicator.Position = position
          
              indicator.CFrame = CFrame.new(position) * CFrame.Angles(0, 0, math.rad(90))
          
              indicator.Anchored = true
          
              indicator.CanCollide = false
          
              indicator.Color = Color3.fromRGB(100, 255, 100)
          
              indicator.Material = Enum.Material.Neon
          
              indicator.Transparency = 0.85
          
              indicator.Parent = nil -- Hidden by default
          
              return indicator
          
          end
          
          
          -- Place tower
          
          PlaceTowerRemote.OnServerEvent:Connect(function(player, towerName, spotName)
          
              local data = TowerData.GetTowerData(towerName)
          
              if not data then return end
          
              
          
              -- Find the spot
          
              local spotsFolder = Workspace:FindFirstChild("TowerDefenseMap") and Workspace.TowerDefenseMap:FindFirstChild("TowerSpots")
          
              if not spotsFolder then return end
          
              local spot = spotsFolder:FindFirstChild(spotName)
          
              if not spot then return end
          
              
          
              -- Check if spot is already occupied
          
              if spot:GetAttribute("Occupied") then return end
          
              
          
              -- Check money
          
              local td = _G.TowerDefense
          
              if not td then return end
          
              if not td.SpendMoney(data.Cost) then return end
          
              
          
              -- Mark spot as occupied
          
              spot:SetAttribute("Occupied", true)
          
              spot.Color = Color3.fromRGB(0, 255, 0)
          
              spot.Transparency = 0.8
          
              
          
              -- Create tower
          
              TowerIdCounter = TowerIdCounter + 1
          
              local towerModel = createTowerVisual(data.Name, spot.Position, data.Color)
          
              towerModel.Name = "Tower_" .. TowerIdCounter
          
              towerModel:SetAttribute("TowerName", towerName)
          
              towerModel:SetAttribute("Level", 1)
          
              towerModel:SetAttribute("SpotName", spotName)
          
              towerModel:SetAttribute("TowerId", TowerIdCounter)
          
              towerModel.Parent = Workspace
          
              
          
              local rangeIndicator = createRangeIndicator(spot.Position, data.Range)
          
              rangeIndicator.Parent = towerModel
          
              
          
              local tower = {
          
                  Id = TowerIdCounter,
          
                  Name = towerName,
          
                  Model = towerModel,
          
                  Spot = spot,
          
                  Position = spot.Position,
          
                  Level = 1,
          
                  LastAttack = 0,
          
                  RangeIndicator = rangeIndicator,
          
              }
          
              table.insert(Towers, tower)
          
              
          
              td.SendGameState()
          
          end)
          
          
          -- Sell tower
          
          SellTowerRemote.OnServerEvent:Connect(function(player, towerId)
          
              for i, tower in ipairs(Towers) do
          
                  if tower.Id == towerId then
          
                      local data = TowerData.GetTowerData(tower.Name)
          
                      if not data then return end
          
                      
          
                      -- Refund 50% of total investment
          
                      local totalCost = data.Cost
          
                      for lvl = 1, tower.Level - 1 do
          
                          totalCost = totalCost + math.floor(data.UpgradeCost * data.UpgradeMultiplier ^ (lvl - 1))
          
                      end
          
                      local refund = math.floor(totalCost * 0.5)
          
                      
          
                      local td = _G.TowerDefense
          
                      if td then td.AddMoney(refund) end
          
                      
          
                      -- Free the spot
          
                      tower.Spot:SetAttribute("Occupied", false)
          
                      tower.Spot.Color = Color3.fromRGB(255, 255, 0)
          
                      tower.Spot.Transparency = 0.5
          
                      
          
                      -- Remove tower
          
                      tower.Model:Destroy()
          
                      table.remove(Towers, i)
          
                      
          
                      if td then td.SendGameState() end
          
                      return
          
                  end
          
              end
          
          end)
          
          
          -- Upgrade tower
          
          UpgradeTowerRemote.OnServerEvent:Connect(function(player, towerId)
          
              for _, tower in ipairs(Towers) do
          
                  if tower.Id == towerId then
          
                      local data = TowerData.GetTowerData(tower.Name)
          
                      if not data then return end
          
                      if tower.Level >= data.MaxLevel then return end
          
                      
          
                      local upgradeCost = math.floor(data.UpgradeCost * data.UpgradeMultiplier ^ (tower.Level - 1))
          
                      local td = _G.TowerDefense
          
                      if not td then return end
          
                      if not td.SpendMoney(upgradeCost) then return end
          
                      
          
                      tower.Level = tower.Level + 1
          
                      tower.Model:SetAttribute("Level", tower.Level)
          
                      
          
                      -- Update visual
          
                      local billboard = tower.Model:FindFirstChild("NameTag")
          
                      if billboard then
          
                          local levelLabel = billboard:FindFirstChild("LevelLabel")
          
                          if levelLabel then
          
                              levelLabel.Text = "Lv." .. tower.Level
          
                          end
          
                      end
          
                      
          
                      -- Update body size slightly
          
                      local body = tower.Model:FindFirstChild("Body")
          
                      if body then
            -  Editar
  18:22:18.467  ========== END PART 31 ==========  -  Editar
  18:22:18.467   ▶  (x2)  -  Editar
  18:22:18.468  ========== PROJECT EXPORT PART 32 ==========  -  Editar
  18:22:18.468                            body.Size = body.Size * 1.1
          
                          body.Position = tower.Position + Vector3.new(0, 3 + (tower.Level - 1) * 0.5, 0)
          
                      end
          
                      local head = tower.Model:FindFirstChild("Head")
          
                      if head then
          
                          head.Size = head.Size * 1.05
          
                          head.Position = tower.Position + Vector3.new(0, 6.5 + (tower.Level - 1) * 0.5, 0)
          
                      end
          
                      
          
                      -- Update range indicator
          
                      local stats = TowerData.GetUpgradedStats(tower.Name, tower.Level)
          
                      if stats and tower.RangeIndicator then
          
                          tower.RangeIndicator.Size = Vector3.new(0.1, stats.Range * 2, stats.Range * 2)
          
                      end
          
                      
          
                      td.SendGameState()
          
                      return
          
                  end
          
              end
          
          end)
          
          
          -- Tower attacking logic
          
          local function findTargets(tower, maxTargets)
          
              local td = _G.TowerDefense
          
              if not td then return {} end
          
              local enemies = td.GetEnemies()
          
              local targets = {}
          
              
          
              -- Sort enemies by waypoint progress (furthest first)
          
              table.sort(enemies, function(a, b)
          
                  return (a:GetAttribute("WaypointIndex") or 0) > (b:GetAttribute("WaypointIndex") or 0)
          
              end)
          
              
          
              local stats = TowerData.GetUpgradedStats(tower.Name, tower.Level)
          
              local range = stats and stats.Range or TowerData.GetTowerData(tower.Name).Range
          
              
          
              for _, enemy in ipairs(enemies) do
          
                  if #targets >= maxTargets then break end
          
                  local dist = (enemy.Position - tower.Position).Magnitude
          
                  if dist <= range then
          
                      table.insert(targets, enemy)
          
                  end
          
              end
          
              
          
              return targets
          
          end
          
          
          -- Create attack effect
          
          local function createAttackEffect(origin, target, color)
          
              local effect = Instance.new("Part")
          
              effect.Name = "AttackEffect"
          
              effect.Anchored = true
          
              effect.CanCollide = false
          
              effect.Material = Enum.Material.Neon
          
              effect.Color = color
          
              effect.Size = Vector3.new(0.5, 0.5, 0.5)
          
              effect.Shape = Enum.PartType.Ball
          
              effect.Position = origin
          
              effect.Parent = Workspace
          
              
          
              -- Animate the effect
          
              task.spawn(function()
          
                  local duration = 0.2
          
                  local elapsed = 0
          
                  while elapsed < duration and effect.Parent and target.Parent do
          
                      elapsed = elapsed + 0.03
          
                      local alpha = elapsed / duration
          
                      effect.Position = origin:Lerp(target.Position, alpha)
          
                      effect.Transparency = alpha
          
                      task.wait(0.03)
          
                  end
          
                  effect:Destroy()
          
              end)
          
          end
          
          
          -- Tower attack loop
          
          RunService.Heartbeat:Connect(function()
          
              local td = _G.TowerDefense
          
              if not td then return end
          
              local gameState = td.GetGameState()
          
              if gameState.GameOver then return end
          
              
          
              local now = os.clock()
          
              
          
              for _, tower in ipairs(Towers) do
          
                  if not tower.Model or not tower.Model.Parent then continue end
          
                  
          
                  local data = TowerData.GetTowerData(tower.Name)
          
                  if not data then continue end
          
                  
          
                  local stats = TowerData.GetUpgradedStats(tower.Name, tower.Level)
          
                  if not stats then continue end
          
                  
          
                  if now - tower.LastAttack < stats.Cooldown then continue end
          
                  
          
                  local targets = findTargets(tower, stats.MaxTargets)
          
                  if #targets == 0 then continue end
          
                  
          
                  tower.LastAttack = now
          
                  
          
                  local origin = tower.Position + Vector3.new(0, 6, 0)
          
                  
          
                  for _, target in ipairs(targets) do
          
                      createAttackEffect(origin, target, data.Color)
          
                      td.DamageEnemy(target, stats.Damage)
          
                      
          
                      -- Splash damage
          
                      if stats.SplashRadius > 0 then
          
                          local allEnemies = td.GetEnemies()
          
                          for _, enemy in ipairs(allEnemies) do
          
                              if enemy ~= target then
          
                                  local dist = (enemy.Position - target.Position).Magnitude
          
                                  if dist <= stats.SplashRadius then
          
                                      td.DamageEnemy(enemy, math.floor(stats.Damage * 0.5))
          
                                  end
          
                              end
          
                          end
          
                      end
          
                      
          
                      -- Slow effect
          
                      if stats.SlowEffect > 0 then
          
                          td.SlowEnemy(target, stats.SlowDuration)
          
                      end
          
                  end
          
              end
          
          end)
          
          
          print("[TowerDefense] TowerManager initialized")
          
        SOURCE_END
  - ServerStorage [ServerStorage]
    - Passives [Folder]
      - DamageReduction [ModuleScript]
        PATH: game.ServerStorage.Passives.DamageReduction
        SOURCE_START
          -- Passiva de INIMIGO: reduz o dano recebido (opcionalmente só de certos tipos). Mesmo motor, outra entidade.
          
          return {
          
          	Id = "DamageReduction",
          
          	Defaults = { Reduction = 0.5, DamageTypes = nil },
          
          	Hooks = {
          
          		OnEnemyTakeDamage = function(p, enemy, amount, damageType, source, hit)
          
          			local types = p.Params.DamageTypes
          
          			if types and not table.find(types, damageType) then
          
          				return
          
          			end
          
          			hit.Amount *= 1 - p.Params.Reduction
          
          		end,
          
          	},
          
          }
          
          
        SOURCE_END
      - Executioner [ModuleScript]
        PATH: game.ServerStorage.Passives.Executioner
        SOURCE_START
          --[[
          
          	Executioner: se a vida do alvo estiver abaixo de HealthPercentage, o dano é multiplicado por ExtraDamageMultiplier.
          
          ]]
          
          return {
          
          	Id = "Executioner",
          
          	Priority = 20, -- roda depois de bônus aditivos/stacks
          
          	Defaults = { HealthPercentage = 0.15, ExtraDamageMultiplier = 3.0 },
          
          
          	Hooks = {
          
          		OnPreAttack = function(p, tower, enemy, damageData)
          
          			if enemy.Health / enemy.MaxHealth < p.Params.HealthPercentage then
          
          				damageData.Amount *= p.Params.ExtraDamageMultiplier
          
          				damageData.Executed = true
          
          			end
          
          		end,
          
          	},
          
          }
          
          
        SOURCE_END
      - RampingDamage [ModuleScript]
        PATH: game.ServerStorage.Passives.RampingDamage
        SOURCE_START
          --[[
          
          	RampingDamage: cada ataque no MESMO inimigo aumenta o dano do próximo em BonusPerStack (até MaxStacks).
          
          	Trocou de alvo => zera os acúmulos (OnTargetSelected). OnPreAttack aplica o bônus e soma o stack.
          
          ]]
          
          return {
          
          	Id = "RampingDamage",
          
          	Priority = 10,
          
          	Defaults = { BonusPerStack = 0.10, MaxStacks = 10, ResetOnTargetChange = true },
          
          
          	OnAttach = function(p)
          
          		p.State.Stacks = 0
          
          		p.State.TargetId = nil
          
          	end,
          
          
          	Hooks = {
          
          		OnTargetSelected = function(p, tower, enemy)
          
          			if p.Params.ResetOnTargetChange then
          
          				p.State.Stacks = 0
          
          			end
          
          			p.State.TargetId = enemy and enemy.Id
          
          		end,
          
          
          		OnPreAttack = function(p, tower, enemy, damageData)
          
          			local st, P = p.State, p.Params
          
          			-- segurança: se o alvo mudou sem passar por OnTargetSelected, trata aqui também
          
          			if enemy.Id ~= st.TargetId then
          
          				if P.ResetOnTargetChange then
          
          					st.Stacks = 0
          
          				end
          
          				st.TargetId = enemy.Id
          
          			end
          
          			damageData.Amount *= 1 + st.Stacks * P.BonusPerStack
          
          			st.Stacks = math.min(st.Stacks + 1, P.MaxStacks)
          
          		end,
          
          	},
          
          }
          
          
        SOURCE_END
      - SplitOnDeath [ModuleScript]
        PATH: game.ServerStorage.Passives.SplitOnDeath
        SOURCE_START
          -- Passiva de INIMIGO: ao morrer, divide em Count inimigos de EnemyId (hook extra: OnDeath).
          
          local ServerScriptService = game:GetService("ServerScriptService")
          
          local World = require(ServerScriptService.Server.World)
          
          
          return {
          
          	Id = "SplitOnDeath",
          
          	Defaults = { EnemyId = "Grunt", Count = 2, Spread = 2 },
          
          	Hooks = {
          
          		OnDeath = function(p, enemy, killer)
          
          			local P = p.Params
          
          			for i = 1, P.Count do
          
          				World.SpawnEnemy(P.EnemyId, {
          
          					PathId = enemy.PathId,
          
          					StartDistance = math.max(0, enemy.Distance - (i - 1) * P.Spread),
          
          				})
          
          			end
          
          		end,
          
          	},
          
          }
          
          
        SOURCE_END
      - SupportAura [ModuleScript]
        PATH: game.ServerStorage.Passives.SupportAura  -  Editar
  18:22:18.468  ========== END PART 32 ==========  -  Editar
  18:22:18.468   ▶  (x2)  -  Editar
  18:22:18.471  ========== PROJECT EXPORT PART 33 ==========  -  Editar
  18:22:18.471          SOURCE_START
          --[[
          
          	SupportAura: buffa torres aliadas dentro de Radius via OnTick (com throttle).
          
          	Nada é hardcoded na Tower: a aura só usa o API genérico tower:SetModifier / ClearModifier.
          
          	Params: Radius, RangeBonus, DamageBonus, AttackSpeedBonus, TargetTag (opcional), AffectSelf, Interval
          
          ]]
          
          local ServerScriptService = game:GetService("ServerScriptService")
          
          local World = require(ServerScriptService.Server.World)
          
          
          local function buildMods(P)
          
          	local mods = {}
          
          	if P.RangeBonus ~= 0 then
          
          		mods.Range = { Mul = 1 + P.RangeBonus }
          
          	end
          
          	if P.DamageBonus ~= 0 then
          
          		mods.Damage = { Mul = 1 + P.DamageBonus }
          
          	end
          
          	if P.AttackSpeedBonus ~= 0 then
          
          		mods.AttackSpeed = { Mul = 1 + P.AttackSpeedBonus }
          
          	end
          
          	return mods
          
          end
          
          
          local function clearAll(p)
          
          	local key = "SupportAura#" .. p.Owner.Id
          
          	for other in pairs(p.State.Buffed) do
          
          		other:ClearModifier(key)
          
          		p.State.Buffed[other] = nil
          
          	end
          
          end
          
          
          return {
          
          	Id = "SupportAura",
          
          	Defaults = {
          
          		Radius = 15,
          
          		RangeBonus = 0.15,
          
          		DamageBonus = 0,
          
          		AttackSpeedBonus = 0,
          
          		TargetTag = nil,
          
          		AffectSelf = false,
          
          		Interval = 0.25,
          
          	},
          
          
          	OnAttach = function(p)
          
          		p.State.Buffed = {}
          
          		p.State.Timer = 0
          
          	end,
          
          
          	OnDetach = clearAll,
          
          
          	-- parâmetros mudaram (upgrade): limpa e deixa o próximo scan reaplicar com os valores novos
          
          	OnParamsChanged = clearAll,
          
          
          	Hooks = {
          
          		OnTick = function(p, tower, dt)
          
          			local st, P = p.State, p.Params
          
          			st.Timer += dt
          
          			if st.Timer < P.Interval then
          
          				return
          
          			end
          
          			st.Timer = 0
          
          
          			local key = "SupportAura#" .. tower.Id
          
          			local inRange = {}
          
          			for _, other in ipairs(World.QueryTowers(tower.Position, P.Radius)) do
          
          				if (P.AffectSelf or other ~= tower) and (P.TargetTag == nil or other:HasTag(P.TargetTag)) then
          
          					inRange[other] = true
          
          				end
          
          			end
          
          
          			local mods = buildMods(P)
          
          			for other in pairs(inRange) do
          
          				if not st.Buffed[other] then
          
          					other:SetModifier(key, mods)
          
          					st.Buffed[other] = true
          
          				end
          
          			end
          
          			for other in pairs(st.Buffed) do
          
          				if not inRange[other] then
          
          					other:ClearModifier(key)
          
          					st.Buffed[other] = nil
          
          				end
          
          			end
          
          		end,
          
          	},
          
          }
          
          
        SOURCE_END
    - RBX_ANIMSAVES [Model]
      - Rig [ObjectValue]
        - Automatic Save [KeyframeSequence]
          - RigAnimationRigData [AnimationRigData]
      - Rig [ObjectValue]
      - Rig [ObjectValue]
        - Automatic Save [KeyframeSequence]
          - Keyframe [Keyframe]
            - HumanoidRootPart [Pose]
              - Torso [Pose]
                - Right Arm [Pose]
                - Left Arm [Pose]
          - Keyframe [Keyframe]
            - HumanoidRootPart [Pose]
              - Torso [Pose]
                - Right Arm [Pose]
                - Left Arm [Pose]
          - Keyframe [Keyframe]
            - HumanoidRootPart [Pose]
              - Torso [Pose]
                - Right Arm [Pose]
          - Keyframe [Keyframe]
            - HumanoidRootPart [Pose]
              - Torso [Pose]
                - Right Arm [Pose]
  - NetworkClient [NetworkClient]
    - ClientReplicator [ClientReplicator]
  - StudioService [StudioService]
  - PluginGuiService [PluginGuiService]
    - Rojo_soundPlayer [DockWidgetPluginGui]
    - PluginGui [DockWidgetPluginGui]
      - Frame [Frame]
      - Main [Frame]
        - Position [TextLabel]
          - Scale [TextButton]
            - TextButton_Roundify_5px [ImageLabel]
          - Offset [TextButton]
            - TextButton_Roundify_5px [ImageLabel]
        - Size [TextLabel]
          - Offset [TextButton]
            - TextButton_Roundify_5px [ImageLabel]
          - Scale [TextButton]
            - TextButton_Roundify_5px [ImageLabel]
    - PluginGui [DockWidgetPluginGui]
      - UI [Frame]
        - Top [Frame]
          - UX [Frame]
            - UIFlexItem [UIFlexItem]
            - UIListLayout [UIListLayout]
            - UIPadding [UIPadding]
            - Buttons [Frame]
              - UIFlexItem [UIFlexItem]
              - UIListLayout [UIListLayout]
              - Mode [TextButton]
                - UICorner [UICorner]
                - UIPadding [UIPadding]
                - UIStroke [UIStroke]
              - Settings [TextButton]
                - UIPadding [UIPadding]
                - UICorner [UICorner]
                - ImageLabel [ImageLabel]
                - UIListLayout [UIListLayout]
                - UIStroke [UIStroke]
            - TextLabel [TextLabel]
          - UIListLayout [UIListLayout]
          - Divider [Frame]
        - UIListLayout [UIListLayout]
        - Bottom [Frame]
          - Divider [Frame]
          - UIListLayout [UIListLayout]
          - UX [Frame]
            - UIPadding [UIPadding]
            - UIListLayout [UIListLayout]
            - Reclass [TextButton]
              - UICorner [UICorner]
              - UIPadding [UIPadding]
              - UIStroke [UIStroke]
            - InputHolder [Frame]
              - Frame [TextBox]
                - UIFlexItem [UIFlexItem]
                - UICorner [UICorner]
                - UIStroke [UIStroke]
              - Modal [Frame]
                - Group [Frame]
                  - UIListLayout [UIListLayout]
                  - ReclassObject [TextButton]
                    - UIPadding [UIPadding]
                    - UICorner [UICorner]
                    - UIStroke [UIStroke]
                  - ReclassObject [TextButton]
                    - UIPadding [UIPadding]
                    - UICorner [UICorner]
                    - UIStroke [UIStroke]
                - UIListLayout [UIListLayout]
                - UICorner [UICorner]
                - UIStroke [UIStroke]
                - UIPadding [UIPadding]
                - UIFlexItem [UIFlexItem]
            - UIFlexItem [UIFlexItem]
        - UX [Frame]
          - UIFlexItem [UIFlexItem]
          - ModalHolder [Frame]
            - Frame [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Sectiontitle [Frame]
                - Divider [Frame]
                - UIListLayout [UIListLayout]
                - UX [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - Title [TextLabel]
                    - UIPadding [UIPadding]
                    - UIFlexItem [UIFlexItem]
                  - Close [TextButton]
              - Info [ScrollingFrame]
                - Infoblock [TextLabel]
                - UIPadding [UIPadding]
                - UIListLayout [UIListLayout]
                - UIFlexItem [UIFlexItem]
          - Main [ScrollingFrame]
            - MiscTools [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - UIListLayout [UIListLayout]
                - UIListLayout [UIListLayout]
                - Divider [Frame]
                - OtherTools [Frame]
                  - UIListLayout [UIListLayout]
                  - TextLabel [TextLabel]
                  - UIPadding [UIPadding]
                  - ToggleBackground [TextButton]
                    - UIStroke [UIStroke]
                - FittingTools [Frame]
                  - UIListLayout [UIListLayout]
                  - TextLabel [TextLabel]
                  - UIPadding [UIPadding]
                  - Items [Frame]
                    - UIListLayout [UIListLayout]
                    - SetFITIMAGE [TextButton]
                      - UIStroke [UIStroke]
                    - Fit [Frame]
                      - FillX [TextButton]
                        - UIStroke [UIStroke]
                      - FilLY [TextButton]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                    - UIFlexItem [UIFlexItem]
                - Top-Divider [Frame]
                - Zindex [Frame]
                  - UIListLayout [UIListLayout]
                  - TextLabel [TextLabel]
                  - UIPadding [UIPadding]
                  - Buttons [Frame]
                    - UIListLayout [UIListLayout]
                    - Input [TextBox]
                      - UIStroke [UIStroke]
                    - Buttons [Frame]
                      - MoveUp [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                      - MoveDown [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                - Divider [Frame]
            - ImageEditing [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]  -  Editar
  18:22:18.471  ========== END PART 33 ==========  -  Editar
  18:22:18.471   ▶  (x2)  -  Editar
  18:22:18.474  ========== PROJECT EXPORT PART 34 ==========  -  Editar
  18:22:18.474                  - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - UIListLayout [UIListLayout]
                - ImageTitleEditing [Frame]
                  - UIListLayout [UIListLayout]
                  - TextLabel [TextLabel]
                  - UIPadding [UIPadding]
                  - Items [Frame]
                    - SizeOffset [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - UIFlexItem [UIFlexItem]
                    - PositionOffset [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - Group [Frame]
                      - OffsetImageTitle [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                      - ScaleImageTitle [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                - Top-Divider [Frame]
                - imagerescaling [Frame]
                  - UIListLayout [UIListLayout]
                  - TextLabel [TextLabel]
                  - UIPadding [UIPadding]
                  - Items [Frame]
                    - scale [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - InputImages [TextButton]
                      - UIStroke [UIStroke]
                      - UIFlexItem [UIFlexItem]
                - Divider [Frame]
            - LiveScaleEditor [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - UIListLayout [UIListLayout]
                - Top-Divider [Frame]
                - Inputs [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - UIFlexItem [UIFlexItem]
                  - SizeOffset [Frame]
                    - Input [TextBox]
                      - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                      - UIFlexItem [UIFlexItem]
                    - UIStroke [UIStroke]
                  - PositionOffset [Frame]
                    - Input [TextBox]
                      - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                      - UIFlexItem [UIFlexItem]
                    - UIStroke [UIStroke]
            - UILayoutTools [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - UIListLayout [UIListLayout]
                - TabButtons [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - UIList [TextButton]
                    - UIStroke [UIStroke]
                  - UIGrid [TextButton]
                    - UIStroke [UIStroke]
                - Top-Divider [Frame]
                - Inputs [Frame]
                  - UIGrid [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - UIFlexItem [UIFlexItem]
                    - Padding [Frame]
                      - PaddingTop [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - PaddingBottom [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - PaddingLeft [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - PaddingRight [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - UIListLayout [UIListLayout]
                    - MainCellTools [Frame]
                      - CellX [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - CellY [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - CellPaddingX [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - CellPaddingY [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - UIListLayout [UIListLayout]
                    - OtherTools [Frame]
                      - FillDirection [Frame]
                        - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                      - FillDirectionMax [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]  -  Editar
  18:22:18.474  ========== END PART 34 ==========  -  Editar
  18:22:18.474   ▶  (x2)  -  Editar
  18:22:18.477  ========== PROJECT EXPORT PART 35 ==========  -  Editar
  18:22:18.477                          - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - SortOrder [Frame]
                        - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                      - StartCorner [Frame]
                        - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                      - HorizontalAlignment [Frame]
                        - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                      - VerticalAlignment [Frame]
                        - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - SortTab [TextLabel]
                    - SortTab [TextLabel]
                    - SortTab [TextLabel]
                  - UIList [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - UIFlexItem [UIFlexItem]
                    - Padding [Frame]
                      - PaddingRight [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - PaddingLeft [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - PaddingBottom [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - PaddingTop [Frame]
                        - UIStroke [UIStroke]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                      - UIListLayout [UIListLayout]
                    - MainCellTools [Frame]
                      - CellPaddingX [Frame]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                    - OtherTools [Frame]
                      - FillDirection [Frame]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                        - UIStroke [UIStroke]
                      - SortOrder [Frame]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                        - UIStroke [UIStroke]
                      - HorizontalAlignment [Frame]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                        - UIStroke [UIStroke]
                      - VerticalAlignment [Frame]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - ItemLineAlignment [Frame]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                        - UIStroke [UIStroke]
                      - Wraps [Frame]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                        - UIStroke [UIStroke]
                      - HorizontalFlex [Frame]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                        - UIStroke [UIStroke]
                      - VerticalFlex [Frame]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                        - Button [TextButton]
                          - UIStroke [UIStroke]
                        - UIStroke [UIStroke]
                      - SortTab [TextLabel]
                    - SortTab [TextLabel]
                    - SortTab [TextLabel]
                - Buttons [Frame]
                  - Top [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Apply [TextButton]
                      - UIStroke [UIStroke]
                    - Scale [TextButton]
                      - UIStroke [UIStroke]
                  - Middle [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - GetChildrenSize [TextButton]
                      - UIStroke [UIStroke]
                  - UIListLayout [UIListLayout]
              - UXnew [Frame]
                - UIListLayout [UIListLayout]
                - Top-Divider [Frame]
                - selector [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - UIList [TextButton]
                    - UIStroke [UIStroke]
                  - UIGrid [TextButton]
                    - UIStroke [UIStroke]
                - UIListtoggled [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - Ites [Frame]
                    - Top [Frame]
                      - TL [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                      - T [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - TR [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                    - UIFlexItem [UIFlexItem]
                    - UIListLayout [UIListLayout]
                    - Middle [Frame]
                      - CL [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - C [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - CR [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                    - Bottom [Frame]
                      - BL [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - B [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - BR [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                  - Group [Frame]
                    - UIListLayout [UIListLayout]
                    - Direction [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - ButtonClick [TextButton]
                        - UIStroke [UIStroke]
                    - Wrap [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - ButtonClick [TextButton]
                        - UIStroke [UIStroke]
                    - Gap [TextLabel]
                      - UIStroke [UIStroke]
                      - UIPadding [UIPadding]
                      - TextBox [TextBox]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                    - Wrap [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - ButtonClick [TextButton]
                        - UIStroke [UIStroke]
                - UIPadding [UIPadding]
                - Padding [Frame]
                  - Bottom [Frame]
                    - LPadding [TextLabel]
                      - UIStroke [UIStroke]
                      - UIPadding [UIPadding]
                      - TextBox [TextBox]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                    - BPadding [TextLabel]
                      - UIStroke [UIStroke]
                      - UIPadding [UIPadding]
                      - TextBox [TextBox]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - UIListLayout [UIListLayout]
                  - UIListLayout [UIListLayout]
                  - Top [Frame]
                    - RPadding [TextLabel]
                      - UIStroke [UIStroke]
                      - UIPadding [UIPadding]
                      - TextBox [TextBox]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                    - TPadding [TextLabel]
                      - UIStroke [UIStroke]  -  Editar
  18:22:18.477  ========== END PART 35 ==========  -  Editar
  18:22:18.477   ▶  (x2)  -  Editar
  18:22:18.480  ========== PROJECT EXPORT PART 36 ==========  -  Editar
  18:22:18.480                        - UIPadding [UIPadding]
                      - TextBox [TextBox]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - UIListLayout [UIListLayout]
                - Divider [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UISizeConstraint [UISizeConstraint]
                - Dims [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - Height [Frame]
                    - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                    - ButtonClick [TextButton]
                      - UIStroke [UIStroke]
                  - Width [Frame]
                    - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                    - ButtonClick [TextButton]
                      - UIStroke [UIStroke]
                - uigridtoggled [Frame]
                  - UIListLayout [UIListLayout]
                  - Top [Frame]
                    - RPadding [TextLabel]
                      - UIStroke [UIStroke]
                      - UIPadding [UIPadding]
                      - TextBox [TextBox]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                    - TPadding [TextLabel]
                      - UIStroke [UIStroke]
                      - UIPadding [UIPadding]
                      - TextBox [TextBox]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
            - NudgeTool [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - Top-Divider [Frame]
                - Tools [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - Buttons [Frame]
                    - Mode [TextButton]
                      - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - Input [TextBox]
                      - UIStroke [UIStroke]
                      - UIFlexItem [UIFlexItem]
                  - Grid [Frame]
                    - UIListLayout [UIListLayout]
                    - Top [Frame]
                      - UIListLayout [UIListLayout]
                      - TL [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - T [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - TR [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                    - Middle [Frame]
                      - UIListLayout [UIListLayout]
                      - CL [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - CR [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - C [TextButton]
                        - UIPadding [UIPadding]
                        - UIListLayout [UIListLayout]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                    - Bottom [Frame]
                      - UIListLayout [UIListLayout]
                      - BL [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - B [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - BR [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                  - AffectChildren [TextButton]
                    - UIStroke [UIStroke]
                    - UIFlexItem [UIFlexItem]
                  - Property [TextButton]
                    - UIStroke [UIStroke]
                    - UIFlexItem [UIFlexItem]
                - UIListLayout [UIListLayout]
            - StickerTool [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - Top-Divider [Frame]
                - Tools [Frame]
                  - UIPadding [UIPadding]
                  - UIListLayout [UIListLayout]
                  - SetRoot [TextButton]
                    - UIStroke [UIStroke]
                    - UIFlexItem [UIFlexItem]
                  - Stick [TextButton]
                    - UIStroke [UIStroke]
                - UIListLayout [UIListLayout]
            - AlignmentTools [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - Tools [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - Buttons [Frame]
                    - PositionTool [TextButton]
                      - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - AnchorTool [TextButton]
                      - UIStroke [UIStroke]
                  - Grid [Frame]
                    - UIListLayout [UIListLayout]
                    - Top [Frame]
                      - UIListLayout [UIListLayout]
                      - TL [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]  -  Editar
  18:22:18.480  ========== END PART 36 ==========  -  Editar
  18:22:18.480   ▶  (x2)  -  Editar
  18:22:18.483  ========== PROJECT EXPORT PART 37 ==========  -  Editar
  18:22:18.484                          - UIPadding [UIPadding]
                      - T [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - TR [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                    - Middle [Frame]
                      - UIListLayout [UIListLayout]
                      - CL [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - C [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - CR [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                    - Bottom [Frame]
                      - UIListLayout [UIListLayout]
                      - BL [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - B [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                      - BR [TextButton]
                        - UIStroke [UIStroke]
                        - Item [ImageLabel]
                          - UIAspectRatioConstraint [UIAspectRatioConstraint]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                  - Compensate [TextButton]
                    - UIStroke [UIStroke]
                - UIListLayout [UIListLayout]
                - pOSITIONING [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - Buttons [Frame]
                    - UIListLayout [UIListLayout]
                    - Divider [Frame]
                    - 1 [Frame]
                      - Left [TextButton]
                        - UIStroke [UIStroke]
                        - ImageLabel [ImageLabel]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - UIFlexItem [UIFlexItem]
                      - Center [TextButton]
                        - UIStroke [UIStroke]
                        - ImageLabel [ImageLabel]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - UIFlexItem [UIFlexItem]
                      - Right [TextButton]
                        - UIStroke [UIStroke]
                        - ImageLabel [ImageLabel]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                      - UIFlexItem [UIFlexItem]
                      - UISizeConstraint [UISizeConstraint]
                    - 2 [Frame]
                      - Top [TextButton]
                        - UIStroke [UIStroke]
                        - ImageLabel [ImageLabel]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - UIFlexItem [UIFlexItem]
                      - Center [TextButton]
                        - UIStroke [UIStroke]
                        - ImageLabel [ImageLabel]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - UIFlexItem [UIFlexItem]
                      - Bottom [TextButton]
                        - UIStroke [UIStroke]
                        - ImageLabel [ImageLabel]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                      - UIFlexItem [UIFlexItem]
                      - UISizeConstraint [UISizeConstraint]
                  - TextLabel [TextLabel]
                  - Mirroring [Frame]
                    - UIListLayout [UIListLayout]
                    - Flipvertically [TextButton]
                      - UIStroke [UIStroke]
                    - Fliphorizontally [TextButton]
                      - UIStroke [UIStroke]
                  - Divider [Frame]
                  - AnchorpointSnap [Frame]
                    - Button [TextButton]
                      - UIStroke [UIStroke]
                - Top-Divider [Frame]
                - Divider [Frame]
            - MainTools [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - UIListLayout [UIListLayout]
                - ScalingTools [Frame]
                  - UIListLayout [UIListLayout]
                  - TextLabel [TextLabel]
                  - UIPadding [UIPadding]
                  - Buttons [Frame]
                    - UIListLayout [UIListLayout]
                    - Top [Frame]
                      - ScaletoOffset [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - UIListLayout [UIListLayout]
                      - OffsettoScale [TextButton]
                        - UIStroke [UIStroke]
                        - UIFlexItem [UIFlexItem]
                      - Settings [TextButton]
                        - UIPadding [UIPadding]
                        - ImageLabel [ImageLabel]
                        - UIListLayout [UIListLayout]
                        - UIStroke [UIStroke]
                    - UIFlexItem [UIFlexItem]
                    - AspectRatioadd [TextButton]
                      - UIStroke [UIStroke]
                    - AspectRatioremove [TextButton]
                      - UIStroke [UIStroke]
                    - Divider [Frame]
                - Divider [Frame]
                - Top-Divider [Frame]
                - OtherTools [Frame]
                  - UIListLayout [UIListLayout]
                  - TextLabel [TextLabel]
                  - UIPadding [UIPadding]
                  - Buttons [Frame]
                    - UIListLayout [UIListLayout]
                    - Top [Frame]
                      - RemoveAllTags [TextButton]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - RemoveAllAttributes [TextButton]
                        - UIStroke [UIStroke]
                    - UIFlexItem [UIFlexItem]
                    - SwapUIGridUIList [TextButton]
                      - UIStroke [UIStroke]
                    - Bottom [Frame]
                      - UIListLayout [UIListLayout]
                      - Ungroup [TextButton]
                        - UIStroke [UIStroke]
                      - GroupLayers [TextButton]
                        - UIStroke [UIStroke]
                    - Divider [Frame]
                    - Apply [Frame]
                      - applyflex [TextButton]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - applyautomaticsize [TextButton]
                        - UIStroke [UIStroke]
            - UIFlexItem [UIFlexItem]
            - UIListLayout [UIListLayout]
            - UIPadding [UIPadding]
            - DefaultProperties [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - UIListLayout [UIListLayout]
                - Top-Divider [Frame]
                - Inputs [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - UIFlexItem [UIFlexItem]
                  - SelectProperty [Frame]  -  Editar
  18:22:18.484  ========== END PART 37 ==========  -  Editar
  18:22:18.484   ▶  (x2)  -  Editar
  18:22:18.486  ========== PROJECT EXPORT PART 38 ==========  -  Editar
  18:22:18.486                      - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                      - UIFlexItem [UIFlexItem]
                    - Icon [ImageLabel]
                  - Properties [Frame]
                    - UIListLayout [UIListLayout]
                    - PositionOffset [Frame]
                      - UIStroke [UIStroke]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                  - FilLY [TextButton]
                    - UIStroke [UIStroke]
            - TopButtonss [Frame]
              - UIListLayout [UIListLayout]
              - ZoomToolActivation [TextButton]
                - UIStroke [UIStroke]
              - KeybindsActivation [TextButton]
                - UIStroke [UIStroke]
            - ZoomToolProps [Frame]
              - UIStroke [UIStroke]
              - UICorner [UICorner]
              - UIListLayout [UIListLayout]
              - Top [Frame]
                - TextLabel [TextLabel]
                - UIListLayout [UIListLayout]
                - UIPadding [UIPadding]
                - Right [Frame]
                  - UIFlexItem [UIFlexItem]
                  - UIListLayout [UIListLayout]
                  - SortUp [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - SortDown [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                  - ExpandCollapse [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - Iconholder [Frame]
                      - VerticalPart [Frame]
                      - HorizontalPart [Frame]
                  - Info [TextButton]
                    - UIStroke [UIStroke]
                    - UICorner [UICorner]
                    - UIListLayout [UIListLayout]
                    - Icon [ImageLabel]
                    - UIPadding [UIPadding]
                - UICorner [UICorner]
              - UX [Frame]
                - UIListLayout [UIListLayout]
                - Top-Divider [Frame]
                - Inputs [Frame]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - UIFlexItem [UIFlexItem]
                  - Size [Frame]
                    - UIListLayout [UIListLayout]
                    - TextLabel [TextLabel]
                    - SizeY [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - SizeX [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                  - Position [Frame]
                    - UIListLayout [UIListLayout]
                    - TextLabel [TextLabel]
                    - PositionX [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - PositionY [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                  - TextLabel [TextLabel]
                  - Grid [Frame]
                    - UIListLayout [UIListLayout]
                    - GridPaddingX [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - GridPaddingY [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - TextLabel [TextLabel]
                    - GridSize [Frame]
                      - UIListLayout [UIListLayout]
                      - GridY [Frame]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                          - UIFlexItem [UIFlexItem]
                        - UIStroke [UIStroke]
                      - GridX [Frame]
                        - Input [TextBox]
                          - UIStroke [UIStroke]
                        - UIListLayout [UIListLayout]
                        - UIPadding [UIPadding]
                        - TextLabel [TextLabel]
                          - UIFlexItem [UIFlexItem]
                        - UIStroke [UIStroke]
                  - List [Frame]
                    - UIListLayout [UIListLayout]
                    - TextLabel [TextLabel]
                    - UIlistpadding [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                  - Padding [Frame]
                    - UIListLayout [UIListLayout]
                    - TextLabel [TextLabel]
                    - TopPadd [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - RightPad [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - PadLeft [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
                    - PadBottom [Frame]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                        - UIFlexItem [UIFlexItem]
                      - UIStroke [UIStroke]
          - Settings [Frame]
            - Background [Frame]
              - UIFlexItem [UIFlexItem]
            - SettingsScroll [ScrollingFrame]
              - UIPadding [UIPadding]
              - UIListLayout [UIListLayout]
              - UIFlexItem [UIFlexItem]
              - Sections [Frame]
                - UIStroke [UIStroke]
                - UICorner [UICorner]
                - UIListLayout [UIListLayout]
                - Top [Frame]
                  - TextLabel [TextLabel]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - UICorner [UICorner]
                - UX [Frame]
                  - UIListLayout [UIListLayout]
                  - Toggles [Frame]
                    - MainToolsToggle [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - AlignmentToolsToggle [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - StickerToolToggle [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - MiscToolsToggle [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - NudgeToolToggle [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - UILayoutToolsToggle [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - LiveScaleEditorToggle [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - ImageEditingToggle [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                  - Top-Divider [Frame]  -  Editar
  18:22:18.486  ========== END PART 38 ==========  -  Editar
  18:22:18.486   ▶  (x2)  -  Editar
  18:22:18.488  ========== PROJECT EXPORT PART 39 ==========  -  Editar
  18:22:18.489                    - Divider [Frame]
                  - StudioUIEditor [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - SectionHandles [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - TextLabel [TextLabel]
                    - Distances [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - Alignments [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - Values [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                  - Other [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                    - LiveParenting [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - EasyUISelect [Frame]
                      - TextLabel [TextLabel]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - ZoomToolProperties [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
              - Keybinds [Frame]
                - UIStroke [UIStroke]
                - UICorner [UICorner]
                - UIListLayout [UIListLayout]
                - Top [Frame]
                  - TextLabel [TextLabel]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - UICorner [UICorner]
                - UX [Frame]
                  - UIListLayout [UIListLayout]
                  - Main [Frame]
                    - UIListLayout [UIListLayout]
                    - Ungroup [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - ScaleToOffset [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - OffsetToScale [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - GroupLayers [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - UIPadding [UIPadding]
                  - Top-Divider [Frame]
                  - Divider [Frame]
                  - AlignmentTools [Frame]
                    - AlignLeft [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - AlignHorizCenter [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - AlignRight [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                    - AlignVertCenter [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - AlignTop [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - AlignBottom [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - Divider [Frame]
                    - Divider [Frame]
                    - FlipHorizontal [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - FlipVertical [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                  - Divider [Frame]
                  - NudgeTool [Frame]
                    - Nudge [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                    - SmallNudgeAmount [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                    - BigNudgeAmount [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Input [TextBox]
                        - UIStroke [UIStroke]
                    - BigNudge [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - Button [TextButton]
                        - UIStroke [UIStroke]
                  - Top [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - ScaletoOffset [TextButton]
                      - UIStroke [UIStroke]
                      - UIFlexItem [UIFlexItem]
                    - Divider [Frame]
                  - Mirroring [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - TextLabel [TextLabel]
                  - Divider [Frame]
              - Themes [Frame]
                - UIStroke [UIStroke]
                - UICorner [UICorner]
                - UIListLayout [UIListLayout]
                - Top [Frame]
                  - TextLabel [TextLabel]
                  - UIListLayout [UIListLayout]
                  - UIPadding [UIPadding]
                  - UICorner [UICorner]
                - UX [Frame]
                  - UIListLayout [UIListLayout]
                  - Mode [Frame]
                    - UIListLayout [UIListLayout]
                    - UIPadding [UIPadding]
                    - ThemeDefaultSelector [Frame]
                      - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - UIPadding [UIPadding]
                      - TextLabel [TextLabel]
                      - ThemeSelector [TextButton]
                        - UIStroke [UIStroke]
                  - Divider [Frame]
                  - Top-Divider [Frame]
                  - CustomThemes [Frame]
                    - UIListLayout [UIListLayout]
                    - TextLabel [TextLabel]
                    - UIPadding [UIPadding]
                    - Buttons [Frame]
                      - Export [TextButton]
                        - UIStroke [UIStroke]
                      - UIListLayout [UIListLayout]
                      - Import [TextButton]
                        - UIStroke [UIStroke]
                    - Input [TextBox]
                      - UIStroke [UIStroke]
                      - UIPadding [UIPadding]
                    - Reset [TextButton]
                      - UIStroke [UIStroke]
    - PluginGui [DockWidgetPluginGui]
      - MainFrame [ScrollingFrame]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - UIPadding [UIPadding]
        - UIGridLayout [UIGridLayout]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]  -  Editar
  18:22:18.489  ========== END PART 39 ==========  -  Editar
  18:22:18.489   ▶  (x2)  -  Editar
  18:22:18.492  ========== PROJECT EXPORT PART 40 ==========  -  Editar
  18:22:18.492          - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
        - Frame [Frame]
          - UICorner [UICorner]
          - UIStroke [UIStroke]
          - TextButton [TextButton]
            - TextLabel [TextLabel]
            - UICorner [UICorner]
            - UIStroke [UIStroke]
          - Frame [Frame]
            - UICorner [UICorner]
            - UIGradient [UIGradient]
          - UIAspectRatioConstraint [UIAspectRatioConstraint]
          - UIGradient [UIGradient]
      - CheckFrame [Frame]
        - UIStroke [UIStroke]
        - UIGridLayout [UIGridLayout]
        - TextLabel [TextLabel]
        - Replace [TextButton]
          - UIStroke [UIStroke]
          - UICorner [UICorner]
        - RotationG [TextButton]
          - UIStroke [UIStroke]
          - UICorner [UICorner]
        - TextLabel [TextLabel]
    - Rojo_soundPlayer [DockWidgetPluginGui]
    - PluginGui [DockWidgetPluginGui]
      - ScrollingFrame [ScrollingFrame]
        - UIGridLayout [UIGridLayout]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
        - ImageButton [ImageButton]  -  Editar
  18:22:18.492  ========== END PART 40 ==========  -  Editar
  18:22:18.492   ▶  (x2)  -  Editar
  18:22:18.496  ========== PROJECT EXPORT PART 41 ==========  -  Editar
  18:22:18.497            - UIScale [UIScale]
        - ImageButton [ImageButton]
          - UIScale [UIScale]
      - Frame [Frame]
        - ImageLabel [ImageLabel]
        - TextLabel [TextLabel]
        - TextButton [TextButton]
          - UIScale [UIScale]
          - UICorner [UICorner]
    - Rojo 7.7.0 [DockWidgetPluginGui]
      - Background [Frame]
        - NotConnectedPage [Frame]
          - Header [Frame]
            - Layout [UIListLayout]
            - VersionIndicator [Frame]
              - VersionText [TextLabel]
                - Padding [UIPadding]
              - Tip [Frame]
              - Border [ImageLabel]
                - Indicator [ImageLabel]
            - Logo [ImageLabel]
          - Buttons [Frame]
            - Layout [UIListLayout]
            - Settings [ImageButton]
              - HoverOverlay [ImageLabel]
              - Tip [Frame]
              - TouchRipple [Frame]
                - Circle [ImageLabel]
              - Text [TextLabel]
              - Border [ImageLabel]
            - Connect [ImageButton]
              - HoverOverlay [ImageLabel]
              - Tip [Frame]
              - TouchRipple [Frame]
                - Circle [ImageLabel]
              - Text [TextLabel]
              - Background [ImageLabel]
          - AddressEntry [ImageLabel]
            - Content [Frame]
              - Host [TextBox]
              - Port [TextBox]
                - Divider [Frame]
            - Border [ImageLabel]
          - Padding [UIPadding]
          - Layout [UIListLayout]
        - Tooltips [Frame]
    - Rojo 7.7.0 [DockWidgetPluginGui]
      - Background [Frame]
        - NotConnectedPage [Frame]
          - Header [Frame]
            - Layout [UIListLayout]
            - VersionIndicator [Frame]
              - VersionText [TextLabel]
                - Padding [UIPadding]
              - Tip [Frame]
              - Border [ImageLabel]
                - Indicator [ImageLabel]
            - Logo [ImageLabel]
          - Buttons [Frame]
            - Layout [UIListLayout]
            - Settings [ImageButton]
              - HoverOverlay [ImageLabel]
              - Tip [Frame]
              - TouchRipple [Frame]
                - Circle [ImageLabel]
              - Text [TextLabel]
              - Border [ImageLabel]
            - Connect [ImageButton]
              - HoverOverlay [ImageLabel]
              - Tip [Frame]
              - TouchRipple [Frame]
                - Circle [ImageLabel]
              - Text [TextLabel]
              - Background [ImageLabel]
          - AddressEntry [ImageLabel]
            - Content [Frame]
              - Host [TextBox]
              - Port [TextBox]
                - Divider [Frame]
            - Border [ImageLabel]
          - Padding [UIPadding]
          - Layout [UIListLayout]
        - Tooltips [Frame]
  - Script Context [ScriptContext]
  - PlacesService [PlacesService]
  - StudioDeviceSimulatorService [StudioDeviceSimulatorService]
  - SelectionHighlightManager [SelectionHighlightManager]
  - PathfindingService [PathfindingService]
  - ScriptEditorService [ScriptEditorService]
    - CommandBar [ScriptDocument]
  - RemoteDebuggerServer [RemoteDebuggerServer]
  - DebuggerManager [DebuggerManager]
    - MainDebugger [ScriptDebugger]
    - LocalScriptDebugger [ScriptDebugger]
    - ClientMainDebugger [ScriptDebugger]
    - LocalScriptDebugger [ScriptDebugger]
    - AnimatorsDebugger [ScriptDebugger]
    - ClientRenderEngineDebugger [ScriptDebugger]
    - PlacementControllerDebugger [ScriptDebugger]
    - RigAnimatorDebugger [ScriptDebugger]
    - ShopUIDebugger [ScriptDebugger]
    - UnitAnimatorDebugger [ScriptDebugger]
    - UnitPanelDebugger [ScriptDebugger]
    - UnitIconDebugger [ScriptDebugger]
    - UnitCardDebugger [ScriptDebugger]
    - ChatCommandsDebugger [ScriptDebugger]
    - BruteDebugger [ScriptDebugger]
    - GruntDebugger [ScriptDebugger]
    - MiniGruntDebugger [ScriptDebugger]
    - SplitterDebugger [ScriptDebugger]
    - EndlessDebugger [ScriptDebugger]
    - MeadowDebugger [ScriptDebugger]
    - BurnDebugger [ScriptDebugger]
    - FreezeDebugger [ScriptDebugger]
    - SlowDebugger [ScriptDebugger]
    - ClosestDebugger [ScriptDebugger]
    - FirstDebugger [ScriptDebugger]
    - LastDebugger [ScriptDebugger]
    - StrongestDebugger [ScriptDebugger]
    - WeakestDebugger [ScriptDebugger]
    - CannonDebugger [ScriptDebugger]
    - FrostMortarDebugger [ScriptDebugger]
    - SupportTotemDebugger [ScriptDebugger]
    - EventBusDebugger [ScriptDebugger]
    - NetDebugger [ScriptDebugger]
    - PathUtilDebugger [ScriptDebugger]
    - PlacementRulesDebugger [ScriptDebugger]
    - RegistryDebugger [ScriptDebugger]
    - TowerDataDebugger [ScriptDebugger]
    - ConfigValidatorDebugger [ScriptDebugger]
    - EconomyDebugger [ScriptDebugger]
    - GameManagerDebugger [ScriptDebugger]
    - LoadoutDebugger [ScriptDebugger]
    - PassiveEngineDebugger [ScriptDebugger]
    - ReplicatorDebugger [ScriptDebugger]
    - RequestsDebugger [ScriptDebugger]
    - StatusEffectManagerDebugger [ScriptDebugger]
    - TowerServiceDebugger [ScriptDebugger]
    - WorldDebugger [ScriptDebugger]
    - AdminCommandsDebugger [ScriptDebugger]
    - EnemyDebugger [ScriptDebugger]
    - TowerDebugger [ScriptDebugger]
    - GameManagerDebugger [ScriptDebugger]
    - TowerManagerDebugger [ScriptDebugger]
    - DamageReductionDebugger [ScriptDebugger]
    - ExecutionerDebugger [ScriptDebugger]
    - RampingDamageDebugger [ScriptDebugger]
    - SplitOnDeathDebugger [ScriptDebugger]
    - SupportAuraDebugger [ScriptDebugger]
  - ScriptDebuggerService [ScriptDebuggerService]
  - PluginDebugService [PluginDebugService]
  - ServiceVisibilityService [ServiceVisibilityService]
  - HttpService [HttpService]
  - PackageService [PackageService]
  - StudioTestService [StudioTestService]
  - Visit [Visit]
  - TraceRouteService [TraceRouteService]
  - Lighting [Lighting]
    - Atmosphere [Atmosphere]
    - Bloom [BloomEffect]
    - DepthOfField [DepthOfFieldEffect]
    - SunRays [SunRaysEffect]
    - Atmosphere [Atmosphere]
    - Dune Sky  [Sky]
  - Teams [Teams]
  - FeatureRestrictionManager [FeatureRestrictionManager]
  - CommerceService [CommerceService]
  - RecommendationService [RecommendationService]
  - TestService [TestService]
  - AdService [AdService]
  - SocialService [SocialService]
  - ProximityPromptService [ProximityPromptService]
  - VoiceChatService [VoiceChatService]
  - AvatarCreationService [AvatarCreationService]
  - AvatarEditorService [AvatarEditorService]
  - GenerationService [GenerationService]
  - ScriptProfilerService [ScriptProfilerService]
  - HeapProfilerService [HeapProfilerService]
  - ModerationService [ModerationService]
  - VideoService [VideoService]
  - VersionControlService [VersionControlService]
  - RemoteCommandService [RemoteCommandService]
  - HapticService [HapticService]
  - MeshContentProvider [MeshContentProvider]
  - SolidModelContentProvider [SolidModelContentProvider]
  - HSRDataContentProvider [HSRDataContentProvider]
  - InstanceFileSyncService [InstanceFileSyncService]
  - UniqueIdLookupService [UniqueIdLookupService]
  - GamepadService [GamepadService]
  - FilteredSelection []
  - FilteredSelection []
  - FilteredSelection []
  - FilteredSelection []
  - TextBoxService [TextBoxService]
  - ControllerService [ControllerService]
    - Instance [HumanoidController]
  - MemStorageService [MemStorageService]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]  -  Editar
  18:22:18.498  ========== END PART 41 ==========  -  Editar
  18:22:18.498   ▶  (x2)  -  Editar
  18:22:18.500  ========== PROJECT EXPORT PART 42 ==========  -  Editar
  18:22:18.500      - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
    - MemStorageConnection [MemStorageConnection]
  - StylingService [StylingService]
    - StudioDesign-4 [Folder]
      - Themes [Folder]
        - Dark [StyleSheet]
          - Derive from Palette [StyleDerive]
        - Light [StyleSheet]
          - Derive from Palette [StyleDerive]
      - Design [StyleSheet]
        - Derive from Light [StyleDerive]
        - .Component-Image [StyleRule]
          - .Icon16 [StyleRule]
          - .Primary [StyleRule]
          - .ArrowIcon [StyleRule]
          - .ErrorIcon [StyleRule]
        - .Component-Pane [StyleRule]
          - .Default [StyleRule]
          - .Paper [StyleRule]
          - .Main [StyleRule]
          - .Muted [StyleRule]
          - .Contrast [StyleRule]
          - .PrimaryBrand [StyleRule]
            - :hover [StyleRule]
          - .Primary [StyleRule]
            - :hover [StyleRule]
          - .Secondary [StyleRule]
            - :hover [StyleRule]
          - .Row [StyleRule]
            - :hover [StyleRule]
          - .Selected [StyleRule]
          - .Input [StyleRule]
        - .Component-TextLabel [StyleRule]
          - .Disabled [StyleRule]
          - .Body [StyleRule]
          - .Bold [StyleRule]
          - .Semibold [StyleRule]
          - .SubText [StyleRule]
          - .Label [StyleRule]
          - .Selected [StyleRule]
          - .Subtitle [StyleRule]
          - .Title [StyleRule]
          - .Contrast [StyleRule]
          - .Success [StyleRule]
          - .Error [StyleRule]
          - .Warning [StyleRule]
          - .Monospace [StyleRule]
          - .Wrap [StyleRule]
          - .Truncate [StyleRule]
          - .Left [StyleRule]
          - .Right [StyleRule]
          - .Top [StyleRule]
          - .Bottom [StyleRule]
          - .BuilderSans [StyleRule]
            - .Bold [StyleRule]
            - .Semibold [StyleRule]
          - .Muted [StyleRule]
        - .Component-Checkbox [StyleRule]
          - >> ImageLabel [StyleRule]
          - .Checked >> ImageLabel [StyleRule]
          - .Indeterminate >> ImageLabel [StyleRule]
          - .Disabled >> ImageLabel [StyleRule]
        - .Component-DragBar [StyleRule]
          - :hover [StyleRule]
          - :press [StyleRule]
          - .Transparent [StyleRule]
        - .Component-ExpandablePane [StyleRule]
          - > .Header > .Arrow [StyleRule]
          - .Expanded > .Header > .Arrow [StyleRule]
          - .compact [StyleRule]
            - > .Header > .Arrow [StyleRule]
            - .Expanded > .Header > .Arrow [StyleRule]
        - .Component-IconButton [StyleRule]
        - .Component-Markdown [StyleRule]
          - >> .Header ::UIPadding [StyleRule]
          - >> .Paragraph ::UIPadding [StyleRule]
          - >> .List [StyleRule]
            - ::UIPadding [StyleRule]
            - >> .ListItem ::UIPadding [StyleRule]
          - >> .CodeBlock [StyleRule]
            - ::UIPadding [StyleRule]
            - >> .CopyButton [StyleRule]
              - >> .CopyIcon [StyleRule]
            - >> .LineNumbers [StyleRule]
            - >> .CodeScroller ::UIFlexItem [StyleRule]
          - >> .HorizontalRule ::UIPadding [StyleRule]
          - >> #1 > UIPadding [StyleRule]
        - .Component-ScrollingFrame [StyleRule]
          - > ScrollingFrame [StyleRule]
          - .modern > ScrollingFrame [StyleRule]
        - .Component-SearchBar [StyleRule]
          - > .Input > .Buttons [StyleRule]
            - > .ClearButton >> ImageLabel [StyleRule]
            - > .SearchButton >> ImageLabel [StyleRule]
            - > .FilterButton >> ImageLabel [StyleRule]
          - > .Input > .SearchIcon [StyleRule]
        - .Component-SelectInput [StyleRule]
          - > TextButton [StyleRule]
            - > #SelectedItemIcon [StyleRule]
            - > #SelectedItemText [StyleRule]
            - > #SelectArrow [StyleRule]
            - .Placeholder > #SelectedItemText [StyleRule]
            - .HasIcon > #SelectedItemText [StyleRule]
          - .HasError [StyleRule]
          - > ImageButton [StyleRule]
          - .modern [StyleRule]
            - >> #SelectedItemText [StyleRule]
            - >> .Component-SelectInput-Selection [StyleRule]
              - ::UICorner [StyleRule]
              - ::UIStroke [StyleRule]  -  Editar
  18:22:18.500  ========== END PART 42 ==========  -  Editar
  18:22:18.500   ▶  (x2)  -  Editar
  18:22:18.502  ========== PROJECT EXPORT PART 43 ==========  -  Editar
  18:22:18.502                - :hover [StyleRule]
        - .Component-SimpleTab [StyleRule]
          - :: UIPadding [StyleRule]
          - > .Contents [StyleRule]
            - .TabSelected [StyleRule]
            - ::UIPadding [StyleRule]
            - > ImageLabel [StyleRule]
          - > .TopLine [StyleRule]
          - > .BottomLine [StyleRule]
            - .TabSelected [StyleRule]
        - .Component-Table [StyleRule]
        - .Component-Tabs [StyleRule]
        - .Component-TextInput [StyleRule]
          - .Input [StyleRule]
          - >> TextBox [StyleRule]
          - .Compact >> TextBox [StyleRule]
          - .PropertyCellError >> TextBox [StyleRule]
        - .Component-Tooltip [StyleRule]
        - .Component-TreeTable [StyleRule]
          - >> .Component-TreeTableCell [StyleRule]
            - > .Left ::UIPadding [StyleRule]
            - >> .Arrow [StyleRule]
              - .Invisible [StyleRule]
          - .modern [StyleRule]
            - >> .Component-TableHeaderBorder [StyleRule]
            - >> .Component-TreeTableCell [StyleRule]
              - >> .Component-TreeTableCellText [StyleRule]
            - >> .Component-TreeTableCell.Secondary [StyleRule]
            - .enable-hover >> .Component-TableRow:hover >> .Component-TreeTableCell [StyleRule]
          - .compact [StyleRule]
            - >> .Component-TreeTableCell [StyleRule]
              - > .Left ::UIPadding [StyleRule]
              - >> .Arrow [StyleRule]
              - >> TextBox [StyleRule]
        - .Component-TreeViewRow [StyleRule]
          - ::UIPadding [StyleRule]
          - >> .Arrow [StyleRule]
          - > .Tail [StyleRule]
            - ::UIPadding [StyleRule]
        - .Component-UseDialogLayout [StyleRule]
          - > UIListLayout [StyleRule]
          - ::UIPadding [StyleRule]
          - > #Icon [StyleRule]
          - .Confirmation > #Icon [StyleRule]
          - .Destructive > #Icon, .Warning > #Icon [StyleRule]
          - .Error > #Icon [StyleRule]
          - .Information > #Icon [StyleRule]
          - .Question > #Icon [StyleRule]
          - > #Content [StyleRule]
            - > UIListLayout, > #Children > UIListLayout [StyleRule]
            - > #Text > UIListLayout [StyleRule]
            - > #Text, > #Children [StyleRule]
              - >> TextLabel [StyleRule]
                - ::UIPadding [StyleRule]
                - #Heading [StyleRule]
            - > #Buttons [StyleRule]
              - > #RightAnchoredButtons [StyleRule]
                - > UIListLayout [StyleRule]
              - > TextButton, > #RightAnchoredButtons > TextButton [StyleRule]
                - ::UIPadding [StyleRule]
                - .Primary [StyleRule]
                  - .Enabled :hover [StyleRule]
                - .Secondary, .Tertiary [StyleRule]
                  - ::UIStroke [StyleRule]
                  - .Enabled :hover [StyleRule]
                    - > UIStroke [StyleRule]
                - .Disabled [StyleRule]
          - .Destructive > #Content > #Buttons > #RightAnchoredButtons > .Primary [StyleRule]
        - .Component-ViewTypeButton [StyleRule]
          - > .ButtonContainer [StyleRule]
            - .Icon [StyleRule]
            - > .ImageContainer [StyleRule]
              - > ImageLabel .Grid [StyleRule]
              - > ImageLabel .List [StyleRule]
          - > .SliderContainer [StyleRule]
        - .Component-ViewTypeSelector [StyleRule]
          - .IconOnly [StyleRule]
          - .List > .Component-SelectInput [StyleRule]
            - > ImageButton [StyleRule]
            - > TextButton > #SelectedItemIcon [StyleRule]
          - .Grid > .Component-SelectInput [StyleRule]
            - > ImageButton [StyleRule]
            - > TextButton > #SelectedItemIcon [StyleRule]
        - .Component-useTooltip [StyleRule]
          - .Role-Tooltip [StyleRule]
          - >> .Role-Surface [StyleRule]
          - >> .Text-Label [StyleRule]
          - >> .Text-Title [StyleRule]
          - >> .TooltipTextBounds [StyleRule]
            - ::UISizeConstraint [StyleRule]
          - >> .X-PadTooltip ::UIPadding [StyleRule]
          - >> .X-RowSpace50 [StyleRule]
            - ::UIListLayout [StyleRule]
        - .X-Fill [StyleRule]
        - .X-Fit [StyleRule]
        - .X-FitX [StyleRule]
        - .X-FitY [StyleRule]
        - .X-PadXS ::UIPadding [StyleRule]
        - .X-PadS ::UIPadding [StyleRule]
        - .X-Pad ::UIPadding [StyleRule]
        - .X-PadL ::UIPadding [StyleRule]
        - .X-Row [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-RowS [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-RowM [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-Column [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-ColumnS [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-ColumnM [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-Top [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-Middle [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-Bottom [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-Left [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-Center [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-Right [StyleRule]
          - ::UIListLayout [StyleRule]
        - .X-AnchorCenter [StyleRule]
        - .X-Corner ::UICorner [StyleRule]
        - .X-Stroke ::UIStroke [StyleRule]
        - .X-Border [StyleRule]
        - .X-Clip [StyleRule]
        - .X-Input [StyleRule]
          - ::UICorner [StyleRule]
          - ::UIStroke [StyleRule]
          - &:hover::UIStroke [StyleRule]
        - .X-Focus ::UIStroke [StyleRule]
        - .X-Error ::UIStroke [StyleRule]
        - .X-Success ::UIStroke [StyleRule]
        - .X-Warning ::UIStroke [StyleRule]
        - .X-Transparent [StyleRule]
        - .X-DefaultSize [StyleRule]
        - .X-DefaultTransparency [StyleRule]
      - Stories [Folder]
      - Palette [StyleSheet]
    - AvatarSettings [Folder]
      - Design [StyleSheet]
        - .Component-CategoryList [StyleRule]
        - .Component-CategoryListItem [StyleRule]
          - >> TextButton [StyleRule]
            - :hover [StyleRule]
            - :press [StyleRule]
            - .Selected [StyleRule]
            - .Unselected [StyleRule]
        - .GeneralCategoryImage [StyleRule]
        - .BodyCategoryImage [StyleRule]
        - .MovementCategoryImage [StyleRule]
        - .AccessoriesCategoryImage [StyleRule]
        - .ClothingCategoryImage [StyleRule]
        - .ToggleSidebarExpandImage [StyleRule]
          - .Expanded [StyleRule]
          - .Collapsed [StyleRule]
        - .Component-NavigationBar [StyleRule]
          - ::UIPadding [StyleRule]
          - ::UISizeConstraint [StyleRule]
        - .AvatarTypeDropdownItem [StyleRule]
          - ::UIStroke [StyleRule]
          - :hover [StyleRule]
        - .AvatarTypeDropdownToggleButton [StyleRule]
          - .Enabled [StyleRule]
          - ::UICorner [StyleRule]
        - .DropdownItem [StyleRule]
          - :hover [StyleRule]
        - .AvatarSettings-LeftTextPrimary [StyleRule]
        - .AvatarSettings-SettingsPage [StyleRule]
          - ::UIListLayout [StyleRule]
        - .AvatarSettings-SettingsContent [StyleRule]
          - ::UIPadding [StyleRule]
        - .Component-ExpandableSection [StyleRule]
        - .Component-ExpandableSection-Header [StyleRule]
          - ::UIPadding [StyleRule]
          - ::UIListLayout [StyleRule]
        - .Component-ExpandableSection-Content [StyleRule]
          - ::UIPadding [StyleRule]
          - ::UIListLayout [StyleRule]
        - .Component-ExpandableSection-Arrow [StyleRule]
          - .Expanded [StyleRule]
          - .Invisible [StyleRule]
        - .Component-WarningIcon [StyleRule]
          - .AssetIdSelector [StyleRule]
        - .Component-HoverTextBox [StyleRule]
          - ::UICorner [StyleRule]
          - ::UIPadding [StyleRule]
        - .GenericModeSelector-Subtext [StyleRule]
        - .RadioButtonContainer >> TextLabel #DescriptionTextLabel [StyleRule]
        - .PresetHoverTooltipDivider [StyleRule]
        - .Separator [StyleRule]
        - .PresetHoverTooltip [StyleRule]
          - >> Frame #ContentPane [StyleRule]
          - >> ImageLabel #DropShadow [StyleRule]
        - .PresetHoverTooltipCheckImage [StyleRule]
        - .PresetHoverTooltipXImage [StyleRule]
        - .GeneralSettingsGameplayDescriptionImage [StyleRule]
        - .ColumnSpacing-Standard ::UIListLayout [StyleRule]
        - .VerticalFlex-Fill ::UIListLayout [StyleRule]
        - .AvatarSettings-BodyOnlyDialog >> TextLabel #Heading [StyleRule]
        - .PublishBar [StyleRule]
          - ::UIStroke [StyleRule]
          - ::UIPadding [StyleRule]
          - ::UIListLayout [StyleRule]
        - .TitledComponentLabel [StyleRule]
        - .PresetImage [StyleRule]
          - ::UIPadding [StyleRule]
          - .PlayerChoice [StyleRule]
          - .Consistent [StyleRule]
        - .HoverTooltipPresetImage [StyleRule]
          - .PlayerChoice [StyleRule]
          - .Consistent [StyleRule]
        - .SaveToRobloxButton [StyleRule]
          - >> TextLabel [StyleRule]
            - UIPadding [StyleRule]
        - TextLabel [StyleRule]
          - .Bold [StyleRule]
        - TextButton [StyleRule]
        - UIListLayout [StyleRule]
        - Derive from AvatarSettingsLightTheme [StyleDerive]
        - Derive from Design [StyleDerive]
      - AvatarSettingsDarkTheme [StyleSheet]
        - Derive from Design [StyleDerive]
      - AvatarSettingsLightTheme [StyleSheet]
        - Derive from Design [StyleDerive]
    - Explorer [StyleSheet]
      - .Explorer-BG-Surface0 [StyleRule]
      - .Explorer-BG-Surface100 [StyleRule]
      - .Explorer-BG-Shift300 [StyleRule]
      - .Explorer-BG-Action-Soft-Emphasis [StyleRule]
      - .Explorer-BG-SystemEmphasis [StyleRule]
      - .Explorer-BG-Input [StyleRule]
      - .Explorer-BG-Hover [StyleRule]
      - .Explorer-Border-SystemEmphasis [StyleRule]
      - .Explorer-Button [StyleRule]
      - .Explorer-GrowX [StyleRule]
        - ::UIFlexItem [StyleRule]
      - .Explorer-ShrinkX [StyleRule]
        - ::UIFlexItem [StyleRule]
      - .Explorer-FillX [StyleRule]
        - ::UIFlexItem [StyleRule]
      - .Explorer-SidePadS ::UIPadding [StyleRule]
      - .Explorer-Content-Default [StyleRule]
      - .Explorer-Content-Disabled [StyleRule]
      - .Explorer-Content-Emphasis [StyleRule]
      - .Explorer-Content-Muted [StyleRule]
      - .Explorer-BG-PrimaryBrandFill [StyleRule]
      - .Explorer-Content-PrimaryBrandFill [StyleRule]
      - .Explorer-Content-Standard [StyleRule]
      - .Explorer-Content-Surface-Outline [StyleRule]
      - .DEPRECATED_Explorer-Text-Size-14 [StyleRule]
      - .Explorer-View [StyleRule]
      - .Explorer-ScrollingFrame [StyleRule]
      - .Explorer-Square ::UIAspectRatioConstraint [StyleRule]
      - .Explorer-Icon [StyleRule]
      - .Explorer-Radius-Small ::UICorner [StyleRule]
      - >> .DEPRECATED_Explorer-StandardText [StyleRule]
      - .Explorer-Stroke-Standard [StyleRule]
        - ::UIStroke [StyleRule]
      - .Explorer-Stroke-Thick [StyleRule]
        - ::UIStroke [StyleRule]
      - .Explorer-Stroke-Emphasis ::UIStroke [StyleRule]
      - .Explorer-Stroke-System-Emphasis ::UIStroke [StyleRule]
      - TextLabel [StyleRule]
      - TextBox [StyleRule]
    - ExplorerDark [StyleSheet]
    - ExplorerLight [StyleSheet]
    - PlaceAnnotations [Folder]
      - Design [StyleSheet]
        - Frame [StyleRule]
        - GuiButton [StyleRule]
        - TextLabel [StyleRule]
          - .Disabled [StyleRule]
        - TextButton [StyleRule]
        - .Component-Avatar [StyleRule]
          - ::UICorner [StyleRule]
        - .Component-Dropdown [StyleRule]
          - ::UIStroke [StyleRule]
          - ::UIPadding [StyleRule]
          - ::UICorner [StyleRule]
        - .Component-DropdownItem [StyleRule]
          - ::UIPadding [StyleRule]  -  Editar
  18:22:18.502  ========== END PART 43 ==========  -  Editar
  18:22:18.502   ▶  (x2)  -  Editar
  18:22:18.503  ========== PROJECT EXPORT PART 44 ==========  -  Editar
  18:22:18.504            - :hover [StyleRule]
          - :press [StyleRule]
          - .Delete [StyleRule]
          - .SectionTitle [StyleRule]
            - ::UIPadding [StyleRule]
        - .Component-Divider [StyleRule]
        - .MoreIcon [StyleRule]
        - .CheckboxOnIcon [StyleRule]
        - .CheckboxOffIcon [StyleRule]
        - .ErrorIcon [StyleRule]
        - .CloseIcon [StyleRule]
        - .SettingsIcon [StyleRule]
        - .AddAnnotationIcon [StyleRule]
        - .Component-AnnotationContents [StyleRule]
          - ::UIPadding [StyleRule]
          - >> Frame [StyleRule]
          - > #TextColumn [StyleRule]
            - ::UIListLayout [StyleRule]
            - ::UIFlexItem [StyleRule]
            - >> #UsernameRow [StyleRule]
              - > Frame [StyleRule]
                - > TextLabel [StyleRule]
                - > #TaggedYou [StyleRule]
                  - ::UIPadding [StyleRule]
                  - ::UICorner [StyleRule]
              - > #MoreIcon [StyleRule]
                - :hover [StyleRule]
                - :press [StyleRule]
            - >> TextLabel #Contents [StyleRule]
            - >> TextBox [StyleRule]
        - .Component-AnnotationHeader [StyleRule]
          - ::UIPadding [StyleRule]
          - ::UIListLayout [StyleRule]
          - > #Navigation [StyleRule]
            - > #ErrorBanner [StyleRule]
            - > #LeftAligned [StyleRule]
              - ::UIListLayout [StyleRule]
              - > ImageLabel [StyleRule]
              - > TextLabel [StyleRule]
              - >> ImageButton [StyleRule]
            - > #RightAligned [StyleRule]
              - ::UIListLayout [StyleRule]
              - > .CloseButton [StyleRule]
                - ::UIPadding [StyleRule]
                - :hover [StyleRule]
                - :press [StyleRule]
                - ::UICorner [StyleRule]
        - .Component-AnnotationListCard [StyleRule]
          - ::UIPadding [StyleRule]
          - > #BackgroundFrame [StyleRule]
            - > TextButton [StyleRule]
              - ::UIPadding [StyleRule]
              - :press [StyleRule]
              - .Hovered [StyleRule]
              - .Selected [StyleRule]
              - > TextLabel [StyleRule]
                - ::UIPadding [StyleRule]
        - .Component-AnnotationListView [StyleRule]
          - ::UISizeConstraint [StyleRule]
          - > #Header [StyleRule]
            - ::UIPadding [StyleRule]
            - > #ButtonGroup [StyleRule]
              - > #AddButton [StyleRule]
                - ::UIPadding [StyleRule]
                - ::UICorner [StyleRule]
                - :hover [StyleRule]
                - :press [StyleRule]
              - > #SettingsWrapper [StyleRule]
                - ::UICorner [StyleRule]
                - > .Dropdown [StyleRule]
                - :hover [StyleRule]
                - :press [StyleRule]
          - > #AnnotationList [StyleRule]
            - ::UIFlexItem [StyleRule]
            - >> ScrollingFrame [StyleRule]
          - >> #EmptyState [StyleRule]
            - ::UIFlexItem [StyleRule]
            - > #AnnotationIcon [StyleRule]
            - > #NoCommentsYet [StyleRule]
            - > #ToAdd [StyleRule]
            - > TextButton [StyleRule]
              - ::UICorner [StyleRule]
              - :hover [StyleRule]
              - :press [StyleRule]
              - ::UIPadding [StyleRule]
          - > #ErrorWrapper >> #ErrorAlert [StyleRule]
            - >> TextButton [StyleRule]
              - ::UICorner [StyleRule]
              - ::UIPadding [StyleRule]
              - :hover [StyleRule]
              - :press [StyleRule]
        - .Component-CancelSubmitFooter [StyleRule]
          - ::UIPadding [StyleRule]
          - >> TextButton [StyleRule]
            - ::UICorner [StyleRule]
          - > #SubmitButton [StyleRule]
            - .Disabled [StyleRule]
            - :hover [StyleRule]
            - :press [StyleRule]
          - > #CancelButton [StyleRule]
            - :hover [StyleRule]
            - :press [StyleRule]
        - .Component-DropdownButton [StyleRule]
          - .AddPadding [StyleRule]
            - ::UIPadding [StyleRule]
          - ::UICorner [StyleRule]
          - :hover [StyleRule]
          - :press [StyleRule]
          - .Disabled [StyleRule]
        - .Component-ErrorAlert [StyleRule]
          - ::UIListLayout [StyleRule]
          - >> #Icon [StyleRule]
          - >> ImageButton [StyleRule]
          - >> #Text [StyleRule]
            - ::UIFlexItem [StyleRule]
          - .Popup [StyleRule]
            - ::UIPadding [StyleRule]
            - ::UICorner [StyleRule]
            - > TextLabel [StyleRule]
        - .Component-ResolveButton [StyleRule]
          - ::UIPadding [StyleRule]
          - :hover [StyleRule]
          - :press [StyleRule]
          - ::UICorner [StyleRule]
          - > ImageLabel [StyleRule]
          - .Resolved [StyleRule]
            - > ImageLabel [StyleRule]
          - .Disabled [StyleRule]
            - > ImageLabel [StyleRule]
        - .Component-SizedScrollingFrame [StyleRule]
          - PadScrollBar [StyleRule]
            - ::UIPadding [StyleRule]
        - .Component-TextInput [StyleRule]
          - ::UICorner [StyleRule]
          - ::UIFlexItem [StyleRule]
          - .Error [StyleRule]
            - ::UIStroke [StyleRule]
          - > ScrollingFrame [StyleRule]
            - > TextBox [StyleRule]
              - ::UIPadding [StyleRule]
              - .Disabled [StyleRule]
        - .Component-TaggingDropdown [StyleRule]
          - ::UIStroke [StyleRule]
          - ::UIPadding [StyleRule]
          - ::UICorner [StyleRule]
          - > .Component-DropdownItem [StyleRule]
            - ::UIListLayout [StyleRule]
            - > #TextLabel [StyleRule]
              - ::UIPadding [StyleRule]
          - > .Hover [StyleRule]
        - Derive from PlaceAnnotationsLightTheme [StyleDerive]
        - Derive from Design [StyleDerive]
        - Derive from Default-Light-Desktop-1 [StyleDerive]
      - PlaceAnnotationsDarkTheme [StyleSheet]
        - Derive from Design [StyleDerive]
      - PlaceAnnotationsLightTheme [StyleSheet]
        - Derive from Design [StyleDerive]
    - KnowledgeTutorials [Folder]
      - Design [StyleSheet]
        - Derive from Design [StyleDerive]
    - Gen3d [Folder]
      - Design [StyleSheet]
        - Derive from Design [StyleDerive]
        - Derive from Default-Light-Desktop-1 [StyleDerive]
    - ManageCollaborators [Folder]
      - Design [StyleSheet]
        - Derive from Design [StyleDerive]
        - Derive from Default-Light-Desktop-1 [StyleDerive]
    - TerrainEditor [Folder]
      - Design [StyleSheet]
        - Derive from Design [StyleDerive]
  - VisualizationModeService [VisualizationModeService]
    - PhysicsSimulation [VisualizationModeCategory]
      - WindDirection [VisualizationMode]
      - ContactPoints [VisualizationMode]
    - GUI [VisualizationModeCategory]
      - GUIOverlay [VisualizationMode]
      - DeviceEmulation [VisualizationMode]
    - View [VisualizationModeCategory]
      - ViewSelector [VisualizationMode]
      - CollaboratorHighlights [VisualizationMode]
      - GridMaterial [VisualizationMode]
      - Grid [VisualizationMode]
    - Animation [VisualizationModeCategory]
      - ShowAnimationSkeleton [VisualizationMode]
    - Lighting [VisualizationModeCategory]
      - Lights [VisualizationMode]
    - PhysicsConstraints [VisualizationModeCategory]
      - Welds [VisualizationMode]
      - Constraints [VisualizationMode]
    - PhysicsLabels [VisualizationModeCategory]
      - AwakeParts [VisualizationMode]
      - AnchoredParts [VisualizationMode]
      - NetworkOwner [VisualizationMode]
      - Assemblies [VisualizationMode]
      - Mechanisms [VisualizationMode]
    - Pathfinding [VisualizationModeCategory]
      - PathfindingModifiers [VisualizationMode]
      - PathfindingMesh [VisualizationMode]
      - PathfindingLinks [VisualizationMode]
  - EncodingService [EncodingService]
  - UserService [UserService]
  - ReflectionService [ReflectionService]
  - UIDragDetectorService [UIDragDetectorService]
  - SerializationService [SerializationService]
  - DraggerService [DraggerService]
  - UGCValidationService [UGCValidationService]
  - PluginManagementService [PluginManagementService]
  - InstanceExtensionsService [InstanceExtensionsService]
  - DraftsService [DraftsService]
  - HeightmapImporterService [HeightmapImporterService]  -  Editar
  18:22:18.504  ========== END PART 44 ==========  -  Editar
  18:22:18.504   ▶  (x2)  -  Editar
  18:22:18.504  ==========================================  -  Editar
  18:22:18.504  EXPORT COMPLETE  -  Editar
  18:22:18.504  TOTAL PARTS: 44  -  Editar
  18:22:18.504  ==========================================  -  Editar
