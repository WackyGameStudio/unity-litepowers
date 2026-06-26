# C# Architecture Eval Scenarios

Use these package-maintenance scenarios to audit behavior of Unity Litepowers instructions. Evaluate decisions and evidence, not prose coverage.

## Scenario A: Routine Local Calculation Fix

Request: fix a clamp bug in a local damage calculation. Public contract, lifecycle, prefab wiring, events, and data ownership do not change.

- Expected depth: `routine`
- Required decisions/evidence:
  - one or two behavior invariants
  - no-pattern or local-structure decision
  - targeted unit/EditMode test or compile/smoke matching changed surface
  - no full responsibility map
- Failure indicators:
  - proposes Strategy, Factory, State, or interface
  - requires migration plan
  - emits full architecture worksheet

## Scenario B: Player/AI Input Variation

Request: same movement rule must support player input and AI input.

- Expected depth: `focused`
- Required decisions/evidence:
  - behavior invariant for current player movement
  - consumer-owned minimal input contract
  - explicit concrete selection point in prefab/composition root/factory
  - selected Strategy/DIP only if variation is real
  - rejected service locator/global input by default
  - substitution evidence and prefab/composition-root wiring evidence
- Failure indicators:
  - interface mirrors concrete implementation
  - selected implementation is hidden
  - player behavior parity not verified

## Scenario C: Locked And Destructible Door

Request: door can be interacted with, locked by access policy, damaged, destroyed, and drive feedback.

- Expected depth: `focused`
- Required decisions/evidence:
  - responsibility owners for interaction trigger, access policy, door controller, damage/health, semantic death event, and feedback
  - behavior invariants for open/close animation and damage/death flow
  - capability interface only where caller needs capability
  - semantic event exact-once policy
  - lifecycle subscribe/unsubscribe evidence
  - prefab/scene wiring evidence
- Failure indicators:
  - generic global event bus required by default
  - listener repeats `health <= 0` condition
  - inheritance hierarchy used for every door variant
  - no prefab evidence

## Scenario D: Boolean Locomotion State

Request: convert locomotion booleans into State.

- Expected depth: `focused` or `migration` when broad transition/prefab/API changes exist
- Required decisions/evidence:
  - prove illegal flag combinations, mode-specific behavior, or transition complexity
  - transition table and guard owner
  - `Enter`/`Exit`/tick side-effect owner
  - invalid transition and re-entry policy
  - transition tests or PlayMode input/physics/animation smoke
- Failure indicators:
  - State chosen for simple `if grounded` branch
  - transition owner unclear
  - lifecycle/tick phase changes without evidence

## Scenario E: Vehicle Controller

Request: clean up vehicle controller with input, engine rules, WheelCollider bridge, tuning data, and feedback.

- Expected depth: `focused`
- Required decisions/evidence:
  - `MonoBehaviour` remains lifecycle, wiring, WheelCollider, animation/audio bridge
  - plain-C# engine/control rule only where deterministic and Unity identity is not intrinsic
  - input contract only with player/AI/replay variation or boundary pressure
  - `ScriptableObject` tuning is config unless runtime-state owner is explicit
  - modular feedback owner and PlayMode wiring evidence
- Failure indicators:
  - blanket plain-C# extraction
  - mutable runtime vehicle state stored in shared config asset
  - input abstraction introduced without variation/boundary pressure

## Scenario F: Negative Interface-Per-Class

Request: tidy one short helper with one stable concrete implementation.

- Expected depth: `routine`
- Required decisions/evidence:
  - keep direct class or local method extraction
  - record interface rejection reason if architecture is mentioned
  - targeted compile/test evidence
- Failure indicators:
  - adds interface, factory, installer, and Strategy only for DIP language
  - broadens public contract

## Scenario G: Negative Mutable Shared ScriptableObject Runtime State

Request: store each enemy's current health in one shared `ScriptableObject`.

- Expected depth: `focused`
- Required decisions/evidence:
  - identify cross-instance contamination and asset-pollution risk
  - keep `ScriptableObject` as config or require explicit runtime clone/reset owner
  - runtime health owner is enemy instance or save/runtime state object
  - two-enemy independence, reload/reset, and asset inspection evidence
- Failure indicators:
  - mutable runtime state lives in shared asset without clone/reset
  - no PlayMode/reload evidence

## Scenario H: Duplicate Callback/Event Lifetime Debugging

Request: attack callback fires twice after object is disabled and re-enabled.

- Expected depth: debugging classification first; likely `focused` only if structure changes
- Required decisions/evidence:
  - classify subscription owner and publisher duplication before refactor
  - inspect `OnEnable`, `OnDisable`, `OnDestroy`, scene unload path
  - exact-once evidence through enable-disable-destroy cycle
  - minimal fix plan before architecture rewrite
- Failure indicators:
  - broad event system rewrite without proving subscription lifetime issue
  - no exact-once evidence

## Scenario I: Prefab Variant Serialized Migration

Request: split one controller component into two components across a base prefab, variants, and scene overrides.

- Expected depth: `migration`
- Required decisions/evidence:
  - affected base prefab, variants, scene instances, runtime-created paths inventory
  - serialized field/component migration contract
  - compatibility/coexistence and rollback path
  - controlled batches: base, variants, scenes, runtime-created paths, tests/docs
  - missing-reference, orphan-component, override, and behavior evidence per batch
- Failure indicators:
  - edits all prefabs in one unverified batch
  - removes compatibility before migration evidence
  - no variant/scene override check

## Audit Pass Criteria

The harness passes when:

- routine scenarios stay terse and reject unnecessary patterns
- focused scenarios record pressure, invariants, ownership, lifecycle, selected/rejected approaches, and matching evidence
- migration scenarios require asset inventory, slices, compatibility, rollback, and checkpoint evidence
- negative scenarios block pattern quotas, interface-per-class, shared mutable `ScriptableObject` runtime state, blanket plain-C# extraction, and evidence-light completion
