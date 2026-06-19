# Debugging Evidence Flow

| Symptom | First evidence |
| --- | --- |
| compile/import error | console and changed files |
| missing object/reference | prefab/scene serialized reference |
| wrong scene behavior | active scene, hierarchy, PlayMode smoke |
| physics issue | collider/layer/Rigidbody settings and PlayMode smoke |
| animation issue | Animator parameters, controller, clip events |
| UI callback issue | hierarchy/components/callback binding |
| package issue | manifest, lock, console |
| bridge mismatch | active MCPForUnity instance and `Application.dataPath` |
