# Debugging Evidence Flow

| Symptom | First evidence | Likely surface | Follow-up evidence |
| --- | --- | --- | --- |
| compile/import error | console and changed files | code/API/package | compile after minimal fix |
| missing object/reference | prefab/scene serialized reference | serialized wiring | missing-reference/orphan-component check |
| wrong scene behavior | active scene, hierarchy, PlayMode smoke | scene/runtime | targeted PlayMode or manual smoke |
| physics issue | collider/layer/Rigidbody settings and PlayMode smoke | physics/lifecycle | physics-step smoke |
| animation issue | Animator parameters, controller, clip events | animation/timing | PlayMode animation smoke |
| UI callback issue | hierarchy/components/callback binding | UI/event | callback smoke |
| package issue | manifest, lock, console | package/settings | import/compile evidence |
| bridge mismatch | active MCPForUnity instance and `Application.dataPath` | evidence target | refreshed target identity |
| duplicate callback | subscription trace or logs | event lifetime | enable-disable-destroy exact-once smoke |
| missing callback after re-enable | `OnEnable`/`OnDisable` path and listener state | lifecycle/event | re-enable smoke and console |
| stuck or oscillating state | current state, transition log, guard result | State transition | transition/re-entry evidence |
| works only after domain reload/restart | static state, `ScriptableObject`, initialization order | lifecycle/shared state | reload/reset and two-instance evidence |
| prefab variant missing behavior | base prefab/variant component and override diff | serialized migration | variant smoke and missing-reference check |
| wrong strategy/input implementation selected | composition root, prefab refs, factory path | dependency selection | selected implementation inspection and behavior smoke |
| ScriptableObject/static cross-instance contamination | two-instance runtime values and asset values | config/runtime-state ownership | reload/reset and asset inspection |
| destroyed listener still receiving events | publisher listener list or callback log | event lifetime | destroy/scene-unload exact-once evidence |
| behavior timing drift after component split | before/after callback order and owner map | lifecycle/component split | phase-specific PlayMode smoke |
