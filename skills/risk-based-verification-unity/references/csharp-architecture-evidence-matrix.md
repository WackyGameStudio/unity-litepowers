# C# Architecture Evidence Matrix

Use this matrix for medium/high C# architecture risk. Architecture evidence is independent from TDD.

| Change type | Primary failure modes | Automated evidence | Unity Editor/runtime evidence | Review evidence | Completion blockers |
| --- | --- | --- | --- | --- | --- |
| SRP/component split | timing drift, missing component, duplicated owner, broken prefab refs | tests for moved deterministic rule | affected prefab/scene components and refs; PlayMode smoke | responsibility owner map | missing affected asset inventory; invariant not checked |
| DIP/Strategy | wrong implementation selected, concrete dependency leaks back, missing wiring | contract/substitution tests where cheap | prefab/composition-root selected implementation smoke | concrete selection point review | no selection point; only one speculative implementation |
| capability interface | broad contract, optional method forced, LSP/ISP break | caller contract tests | detection/wiring smoke across implementations | minimal capability and failure semantics review | concrete type switch remains; implementer cannot honor contract |
| State | invalid transition, re-entry bug, stuck/oscillating mode, side-effect order drift | transition table tests | PlayMode mode/animation/physics smoke | guard/transition owner review | no transition owner; State used for trivial branch |
| Observer/event | duplicate callback, missed unsubscribe, destroyed listener receives event, wrong order | publisher/listener tests where deterministic | enable-disable-destroy/scene unload smoke and console | publisher/subscriber lifetime review | event lifetime uncertain; global bus introduced without pressure |
| Adapter/semantic event | meaning duplicated, low-level event exposed, event fires too often | semantic condition tests | exact-once runtime smoke | translation owner and event naming review | listeners still duplicate condition |
| Factory/composition root | wrong concrete, hidden service lookup, failed spawn path | factory selection tests | prefab/installer/composition-root inspection; spawn smoke | selection and failure behavior review | no owner for selection; missing implementation failure unhandled |
| inheritance change | subtype violates base invariant, hidden lifecycle dependency, empty overrides | base contract tests | representative subtype prefab/smoke | LSP and hook review | subtype cannot honor base contract |
| plain-C# extraction | Unity lifecycle dependency lost, stale state copy, extra bridge bug | deterministic rule tests | bridge smoke for MonoBehaviour caller | boundary review | extracted rule still depends on Unity object identity |
| `ScriptableObject` config/runtime ownership | shared mutable asset state, cross-instance contamination, reload/reset bug | config validation or save/reset tests | asset inspection; two-instance PlayMode/reload smoke | config vs runtime owner review | mutable runtime state stored in shared asset without clone/reset |
| serialized migration | missing refs, orphan components, lost overrides, old/new double run | migration utility tests if present | base prefab, variants, scenes, runtime-created paths inspected and smoked | affected asset and rollback review | unmigrated variants/scenes; compatibility removed early |
| asmdef/API boundary | compile break, circular dependency, downstream caller drift | compile and API tests | package/import console | dependency direction and public contract review | dependent callers unverified; asmdef direction unclear |

## Evidence Rules

- State expected and observed result.
- Automated tests do not prove prefab/scene/serialized wiring.
- Source review does not prove runtime behavior.
- Editor-backed claims need fresh MCPForUnity target identity.
- Manual evidence needs reproducible steps and observed result.
