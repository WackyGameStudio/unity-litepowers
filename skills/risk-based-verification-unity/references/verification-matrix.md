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
