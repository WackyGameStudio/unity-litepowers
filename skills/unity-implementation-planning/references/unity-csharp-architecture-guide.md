# Unity C# Architecture Guide

Canonical decision reference for C# architecture-sensitive Unity work.

## Purpose

Use this guide when C# work changes contracts, responsibility ownership, state/event topology, Unity lifecycle, `ScriptableObject` ownership, composition/inheritance, asmdef/API direction, or serialized prefab/scene wiring.

Do not load this full guide for routine local edits with no architecture trigger. For routine work, record depth, one behavior invariant, no-pattern or local-structure decision, and targeted evidence.

## Conditional Depth

Depth controls documentation and evidence, not quality score.

| Depth | Use when | Required output |
| --- | --- | --- |
| `routine` | Private/local implementation change; no contract, lifecycle, event/state, data ownership, or serialized wiring change. | Architecture depth, behavior invariant, no-pattern/local decision, targeted evidence. |
| `focused` | Interface/capability/Strategy/State/event introduction; component split/merge; plain-C# policy extraction; `ScriptableObject` config; small prefab/scene migration; composition/inheritance change; subscription owner change. | Compact C# Architecture Profile with pressure, invariants, ownership, lifecycle, serialized wiring, selected/rejected approaches, evidence. |
| `migration` | Public API or asmdef direction; broad prefab/scene/variant migration; save/data compatibility; cross-system event topology; lifecycle/execution-order change; shared runtime state migration; deep inheritance replacement; substantial State migration; new DI/service/package architecture. | Focused profile plus slices, compatibility/coexistence, rollback, affected assets, stop/replan triggers, checkpoint evidence. |

Highest applicable trigger wins.

## Decision Order

1. Read actual docs, source, and Unity wiring.
2. State requested behavior change.
3. State behavior invariants.
4. Locate concrete change pressure and current blast radius.
5. Map responsibilities and owners.
6. Map dependency direction and concrete selection point.
7. Map Unity lifecycle and serialized wiring.
8. Choose simplest viable structure.
9. Name a pattern only when it clarifies and addresses pressure.
10. Record plausible rejected approaches.
11. Define migration order and rollback when needed.
12. Bind each failure mode to evidence.

## Behavior Invariants

Record observable behavior that must not change while structure changes.

Examples:

- Input sampling phase remains `Update`.
- Physics write remains `FixedUpdate`.
- Animation parameter changes happen after movement state changes.
- Death event fires exactly once.
- Disabled object does not receive callbacks.
- Prefab default values and scene overrides stay equivalent.
- Save/load data remains compatible.

## Change Pressure

Use concrete pressure, not vague quality language.

Good pressure:

- New player/AI/replay input variants must share movement rule.
- Several listeners duplicate `health <= 0` logic.
- Boolean locomotion flags can enter impossible combinations.
- Prefab variants need component migration without losing overrides.

Weak pressure:

- Class is long.
- Pattern would be cleaner.
- Interface may be useful someday.
- Composition is always better.

## Responsibility Map

Use this compact table for focused/migration work.

| Responsibility | Current owner | Proposed owner | Change reason | State/data moved | Evidence |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |

SRP means separate reasons to change. Do not use line count, class count, or method count as the reason.

## Dependency Direction And Selection

Consumer-owned minimal contracts are preferred when there is real substitution, boundary, or test-seam pressure.

| Consumer | Contract/capability | Implementations | Concrete selection point | Failure behavior | Evidence |
| --- | --- | --- | --- | --- | --- |
|  |  |  | prefab/composition root/factory/installer |  |  |

Rules:

- Do not create interface-per-class.
- Do not copy every concrete method into an interface.
- Verify LSP: subtype or implementation must honor caller expectations.
- Verify ISP: consumers see only capability they need.
- DIP/Strategy requires actual variation, boundary, runtime selection, or valuable deterministic test seam.
- Factory/composition root requires explicit concrete selection point and missing-selection failure behavior.

## MonoBehaviour And Plain C# Boundary

Keep `MonoBehaviour` for Unity lifecycle, serialization, Inspector wiring, scene/object identity, component lookup, coroutines, animation/physics bridges, and composition roots.

Move to plain C# when rule/policy/transition is deterministic and does not need Unity object identity or lifecycle.

Do not extract plain C# only because "testable" sounds good. Extraction must reduce concrete pressure and keep wiring inspectable.

## Unity Lifecycle Ownership

Record owners when lifecycle changes.

| Concern | Owner | Phase | Re-entry policy | Cleanup/cancel owner | Evidence |
| --- | --- | --- | --- | --- | --- |
| initialization |  | `Awake`/`Start`/composition root |  |  |  |
| tick/update |  | `Update`/`FixedUpdate`/`LateUpdate` |  |  |  |
| subscribe/unsubscribe |  | `OnEnable`/`OnDisable`/`OnDestroy` |  |  |  |
| coroutine/tween/async |  |  |  |  |  |

Watch for timing drift after component splits, missing unsubscribe, duplicated subscribe, stale coroutine, and scene unload leaks.

## Serialized Wiring Contract

Any component, field, prefab, variant, scene, or asset migration needs an explicit contract.

| Asset/path | Current component/field | New component/field | Compatibility path | Batch order | Rollback | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
|  |  |  | coexist/copy/adapter/none |  |  |  |

Check base prefabs, prefab variants, scene instances, runtime-created objects, missing references, orphan components, overrides, and save/data compatibility.

## Config And Runtime-State Ownership

`ScriptableObject` is strong for design-time config and shared immutable data. Mutable per-instance runtime state belongs to an instance owner unless a clone/reset/save policy is explicit.

Record:

- config asset owner
- mutable runtime-state owner
- reset/reload policy
- save/load relationship
- clone policy if asset-derived runtime state is used
- cross-instance contamination evidence

## Composition And Inheritance

Prefer composition when behavior combinations differ per prefab, optional capabilities vary, runtime substitution is needed, or inheritance axes cross.

Inheritance is allowed when shared invariants and lifecycle are real, subtype substitutability holds, hooks are explicit, and hierarchy depth remains understandable.

Reject:

- empty or throwing overrides
- repeated subtype casts/checks
- base class with optional dependencies every subtype does not need
- prefab variation expressed only through type hierarchy
- hidden dependency on base lifecycle order

## Capability Interfaces

Use capability interfaces when different concrete types provide the same behavior and consumers should not type-switch.

Record:

- capability semantics
- pre/post conditions
- failure semantics
- implementations
- detection/wiring path
- ISP/LSP evidence

Reject broad interfaces, one-off interfaces, and contracts that leak concrete implementation details.

## Pattern Pressure Matrix

| Pressure | Simplest first option | Pattern/principle if justified | Bad signal | Minimum evidence |
| --- | --- | --- | --- | --- |
| Separate change reasons | Local method/component split | SRP/component split | Split by size only | compile plus affected prefab/scene refs |
| Concrete source varies | Direct dependency kept local | DIP/Strategy | one stable implementation | substitution and selection evidence |
| Type switch repeats | Local polymorphic call | capability interface/OCP | broad interface | implementer review plus detection/wiring smoke |
| Mode rules and transitions grow | named branch/table | State | trivial branch | transition/re-entry evidence |
| Listeners duplicate condition | direct call or local event | Observer/semantic event/Adapter | global bus by default | exact-once subscribe/unsubscribe evidence |
| Object creation varies | prefab reference/direct `Instantiate` | Factory/composition root | hides simple prefab link | selected implementation and failure evidence |
| Runtime data shared accidentally | instance field | ScriptableObject config plus instance state | mutable shared asset | cross-instance/reload evidence |

Pattern name is a label after the pressure is proven.

## Event Topology And Semantic Events

Record:

- publisher owner
- subscriber owner
- subscribe/unsubscribe phase
- exact-once guarantee
- event order and re-entry policy
- disabled/destroyed/scene-unload behavior
- debug trace or inspector path

Use semantic events when multiple listeners duplicate low-level interpretation. Avoid global event bus by default.

## State And Transition Design

Use State when mode-specific behavior and transition rules justify extra structure.

Record:

- state list
- transition table
- guard owner
- `Enter`/`Exit`/tick side effects
- invalid transition behavior
- re-entry policy
- transition evidence

Reject State for simple branches without illegal combinations or mode-specific lifecycle.

## Behavior-Preserving Migration

For migration depth:

1. Characterize current behavior.
2. Add one seam without behavior change.
3. Move one responsibility.
4. Compile/import and read console.
5. Migrate serialized wiring in controlled batches.
6. Verify invariants and representative failure modes.
7. Keep rollback path until affected assets and runtime paths are verified.
8. Remove compatibility only after coexistence evidence is no longer needed.

## Architecture Risk Triggers

Use existing `low | medium | high` values.

| Risk | Triggers |
| --- | --- |
| low | private/local implementation change; no contract, lifecycle, event/state, data ownership, or serialized wiring change |
| medium | interface/capability/Strategy/State/event introduction; component split/merge; plain-C# policy extraction; `ScriptableObject` config introduction; small prefab/scene migration; composition/inheritance change; subscription-owner change |
| high | public API or asmdef direction; broad prefab/scene/variant migration; save/data compatibility; cross-system event topology; lifecycle/execution-order change; shared static/runtime-state migration; deep inheritance replacement; substantial State migration; new DI/service/package architecture |

Do not lower risk because code compiles, a pattern is used, or unrelated tests pass.

## Required Evidence

Evidence must state expected and observed result.

- Automated tests prove deterministic rules, contracts, transitions, serialization, and data migration when setup is cheap enough.
- Unity Editor/runtime evidence proves scene, prefab, serialized reference, lifecycle, animation, physics, UI, and asset behavior.
- Source review proves dependency direction, ownership, contract width, and migration code path only when runtime state is not the claim.
- Manual observation needs reproducible steps and result.
- MCPForUnity-backed claims need fresh target identity.

Architecture evidence is independent from TDD.

## Overengineering Rejection Rules

Explicitly reject when applicable:

- pattern quota or score
- class-size quota
- interface-per-class
- Strategy/Factory for one concrete case without clear next variant
- State for trivial branch
- global event bus by default
- mutable shared `ScriptableObject` runtime state
- composition-only dogma
- blanket plain-C# extraction
- full architecture worksheet for routine work

## Source And License Boundary

This package may restate independent decision rules learned from architecture practice and Unity constraints. Do not copy C# source, class implementations, scenes, prefabs, assets, or runtime code from external teaching repositories into this skill package. If a reference repository has unclear or inconsistent license labels, keep examples original and generic.
