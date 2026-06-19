# Architecture Pattern Decision Matrix

Use this as fit check, not as checklist to apply every pattern.

| Problem pressure | First check | Good signal | Bad signal | Verification impact |
| --- | --- | --- | --- | --- |
| large MonoBehaviour | SRP, component split | separate reasons to change | split only by file count | scene/prefab refs compile |
| new type changes switch | OCP, Strategy, Factory | variants are expected | one-off branch | unit/EditMode or spawn smoke |
| subclass cannot honor parent | LSP, composition | all child types honor contract | empty/throwing overrides | API review and tests |
| interface keeps growing | ISP | optional capability | every consumer sees unrelated members | implementer review |
| logic depends on concrete source | DIP | player/AI/replay/network vary | one stable source | test double or PlayMode smoke |
| mode behavior | State | transitions matter | boolean branch is enough | transition tests or smoke |
| decoupled reaction | Observer/event | publisher should not know listener | direct call is clearer | subscribe/unsubscribe evidence |
| undo/replay/input buffer | Command | action history matters | no replay/undo need | command tests |
| complex UI data flow | MVP | UI and model logic mixed | tiny static UI | presenter tests or UI smoke |
| UI Toolkit binding | MVVM | binding reduces repeated updates | UGUI/simple UI | binding evidence |
| frequent spawn/despawn | Object Pool | allocation/GC/lifecycle risk | low volume | pool lifecycle smoke/profiler |
| shared static data | Flyweight/ScriptableObject | duplicated immutable data | per-instance mutable state | asset inspection |
| expensive repeated recalculation | Dirty Flag | recompute only when changed | stale state risk unmanaged | dirty/clean tests |
| large entity count / CPU hot path / deterministic simulation / streaming | DOTS/ECS or Jobs/Burst | same rules over large data, clear GameObject boundary | low volume, UI/animation/authored behavior dominates | DOTS suitability gate, profiler or entity runtime evidence |

Record selected patterns, rejected patterns, and overengineering risk.
