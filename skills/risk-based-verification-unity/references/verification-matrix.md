# Verification Matrix

| Surface | Evidence |
| --- | --- |
| pure C# logic | unit test |
| combat/state/data | unit or EditMode test |
| ScriptableObject | EditMode validation and asset inspection |
| save/load | serialization test |
| editor tool | EditMode or dry-run test plus asset diff |
| prefab | prefab smoke and serialized refs |
| scene | scene smoke and hierarchy evidence |
| UI Toolkit | manage_ui/render/callback evidence |
| uGUI | hierarchy/components/screenshot/callback evidence |
| physics | PlayMode smoke |
| animation | Animator param/clip wiring and PlayMode/manual smoke |
| performance | profiler or device build evidence |
| package/settings | import/compile/console evidence |
| component split / serialized migration | compile/import, affected prefab/scene refs, missing-reference/orphan-component check, behavior smoke |
| event topology | publisher/subscriber review, enable-disable-destroy exact-once smoke, console evidence |
| state machine | transition tests or PlayMode transition/re-entry smoke |
| ScriptableObject config/runtime ownership | asset inspection, two-instance runtime smoke, reload/reset evidence |
| composition root / factory | selected implementation inspection, spawn/selection smoke, missing-selection failure review |
| asmdef/API boundary | compile, dependent caller evidence, dependency direction review |
| Jobs/Burst hot path | Burst compile/import evidence, deterministic result check, profiler or timing evidence |
| Entities/DOTS package | package manifest/import/compile evidence, console evidence |
| ECS authoring/baking | Baker/SubScene/entity prefab evidence, baking output or Entity Hierarchy/Inspector evidence |
| ECS runtime systems | Entity Hierarchy/Inspector, Systems/Query window evidence, PlayMode smoke |
| ECS structural changes | EntityCommandBuffer path review, PlayMode smoke, console evidence |
| ECS performance motivation | profiler/job evidence before/after or target-load smoke |
