# Task Name

## Purpose

## Background

## Scope

## Out Of Scope

## Related Docs

## Unity Surfaces

## C# Architecture Profile

### Routine Form

Use only when depth is `routine`.

- Depth: routine
- Behavior invariant:
- Local structure decision: no pattern | local method/object cleanup
- Architecture evidence:

### Focused / Migration Form

Use when depth is `focused` or `migration`.

- Depth: focused | migration
- Change pressure:
- Behavior invariants:
- Current blast radius:
- Responsibility map:
  - Responsibility:
  - Current owner:
  - Proposed owner:
  - Change reason:
  - State/data moved:
  - Evidence:
- Dependency / contract / implementations:
  - Consumer:
  - Contract or capability:
  - Implementations:
  - Concrete selection point:
  - Failure behavior:
- Lifecycle ownership:
  - Initialization owner:
  - Tick owner:
  - Subscribe/unsubscribe owner:
  - Cleanup/cancel owner:
  - Re-entry policy:
- Serialized wiring contract:
  - Affected prefabs/scenes/assets:
  - Component/field changes:
  - Compatibility path:
  - Missing-reference/orphan-component check:
- Config/runtime-state ownership:
  - Config owner:
  - Runtime-state owner:
  - Reset/clone/save policy:
- Selected patterns and pressure per pattern:
- Rejected approaches and overengineering guard:
- Architecture evidence:
- Migration / compatibility / rollback (migration depth; `N/A` for focused):
  - Slices:
  - Coexistence path:
  - Rollback:
  - Stop/replan triggers:

## DOTS / ECS Fit

- Candidate: none | Jobs/Burst only | hybrid ECS | ECS-first
- Trigger pressure:
- Selected approach:
- Rejected approach:
- GameObject boundary:
- Authoring/Baking impact:
- Structural changes / ECB need:
- Package impact:
- Verification evidence:

## Data / Prefab / UI

## Implementation Notes

## Verification Profile

## Decision Questions

- Current situation:
- Options considered:
- Recommendation:
- User answer:
- Evidence:

## Pattern / SOLID Verification

- Does the plan record behavior invariants before selecting patterns?
- Does the plan split responsibilities at Unity boundaries that change independently?
- Does the plan avoid inheritance/interface contracts that likely violate LSP, ISP, or serialized wiring?
- Does the plan apply State/Strategy/Factory/Observer/Command/MVP/MVVM/Object Pool/Flyweight/Dirty Flag only where change pressure justifies it?
- Does the plan apply DOTS/ECS or Jobs/Burst only where scale, CPU, determinism, streaming, or multiplayer pressure justifies it?
- Does the plan record why plausible patterns were rejected?
- Does the verification evidence cover architecture failure modes and pattern-specific failure modes?

## Done Criteria

## Risks
