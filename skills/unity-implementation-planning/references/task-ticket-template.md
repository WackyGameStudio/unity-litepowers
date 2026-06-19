# Task Name

## Purpose

## Background

## Scope

## Out Of Scope

## Related Docs

## Unity Surfaces

## Architecture / Pattern Fit

- Problem pressure:
- SOLID check:
- Selected patterns:
- Rejected patterns:
- Unity lifecycle risks:
- Overengineering risk:

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

- Does the plan split responsibilities at the right Unity boundary?
- Does the plan avoid inheritance/interface contracts that likely violate LSP or ISP?
- Does the plan apply State/Strategy/Factory/Observer/Command/MVP/MVVM/Object Pool/Flyweight/Dirty Flag only where the problem pressure justifies it?
- Does the plan apply DOTS/ECS or Jobs/Burst only where scale, CPU, determinism, streaming, or multiplayer pressure justifies it?
- Does the plan record why plausible patterns were rejected?
- Does the verification evidence cover pattern-specific failure modes?

## Done Criteria

## Risks
