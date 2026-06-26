# MCPForUnity Routing

MCPForUnity is the primary Unity Editor evidence path for Unity Litepowers.

## Preflight

- Confirm active MCPForUnity instance.
- Confirm Unity project path.
- Confirm `Application.dataPath` or equivalent Unity-observed identity.
- Confirm required tool groups.
- Read console/import status before trusting Editor-backed claims.

## Skill Ownership

| Skill | MCPForUnity role |
| --- | --- |
| `unity-bootstrap` | setup, active target identity, profile |
| `unity-implementation-planning` | record evidence path per task |
| `risk-based-verification-unity` | choose surface-specific evidence |
| `executing-unity-plan-lite` | run Editor-backed evidence steps |
| `systematic-debugging-unity-lite` | inspect console, scene, prefab, runtime state |
| `completion-check-unity-lite` | confirm fresh evidence before completion |

## Surface Evidence

| Surface | Evidence |
| --- | --- |
| code compile | refresh/import and console |
| EditMode/PlayMode | test job evidence |
| scene | hierarchy/load/save evidence |
| prefab | serialized references and prefab smoke |
| asset/data | asset inspection |
| component split | affected GameObjects/prefabs have required components and refs |
| prefab/base/variant/scene migration | base prefab, variants, scene overrides, missing refs, orphan components |
| lifecycle/event | PlayMode enable-disable-destroy/reload smoke and console |
| ScriptableObject config/runtime | asset values, runtime instance behavior, reload/reset evidence |
| composition root selection | selected implementation/component/asset inspection |
| UI Toolkit | UI document/render/callback evidence |
| uGUI | hierarchy, components, screenshot, callback evidence |
| build settings | build settings inspection |
| package/settings | manifest/settings diff, import, console |
