# DOTS / ECS Decision Matrix

Use this as a suitability gate. Do not make DOTS the default architecture.

## Output Decision

```markdown
## DOTS / ECS Suitability

- Candidate: none | Jobs/Burst only | hybrid ECS | ECS-first
- Trigger pressure:
- Rejected approach:
- GameObject boundary:
- Authoring/Baking path:
- Runtime data ownership:
- Structural changes / ECB need:
- Package impact:
- Debugging and inspection path:
- Verification evidence:
```

## Suitability Signals

| Pressure | First candidate | Good signal | Bad signal | Planning impact |
| --- | --- | --- | --- | --- |
| isolated CPU-heavy calculation | Jobs/Burst only | data can be copied to native containers or structs | needs many UnityEngine object calls | plan Burst/job safety evidence |
| many similar runtime units | hybrid ECS | projectiles, crowds, units, resources, sensors, path queries | under dozens of objects or mostly bespoke behavior | plan ECS data boundary |
| deterministic simulation | hybrid ECS or ECS-first | rollback, replay, lockstep, QA determinism matters | designer-driven timing or animation dominates | plan deterministic smoke/tests |
| large world streaming | hybrid ECS or ECS-first | SubScene/entity scene workflow fits content | small handcrafted scenes | plan baking and streaming evidence |
| heavy NPC/AI/resource sim | hybrid ECS | same rules over many agents | few hand-authored actors | plan systems and profiler evidence |
| large-scale multiplayer | ECS-first candidate | Netcode for Entities is likely central | small co-op or GameObject netcode is enough | plan package and authority model |
| UI, menus, narrative scripting | none | UI Toolkit/uGUI/GameObject workflow is clearer | data-oriented pressure absent | avoid DOTS |
| animation-heavy character controller | none or hybrid edge | simulation can separate from presentation | Animator/rig/control feel dominates | keep GameObject presentation boundary |

## Candidate Levels

- `none`: Use GameObject/MonoBehaviour architecture. Record why DOTS is overkill.
- `Jobs/Burst only`: Use C# Job System and Burst for a contained hot path without Entities.
- `hybrid ECS`: Keep authoring/presentation in GameObjects; use Entities for high-volume runtime data and systems.
- `ECS-first`: Use Entities as the core gameplay runtime. Require explicit package, baking, debugging, and verification plan.

## Planning Requirements

- Record package versions for `Entities`, `Burst`, `Collections`, `Mathematics`, and any `Entities.Graphics`, `Unity Physics`, `Havok Physics`, or `Netcode for Entities` dependency.
- Define GameObject-to-Entity boundary. Name what remains MonoBehaviour/UI/Animator/prefab driven.
- Define Authoring/Baking path: Baker, baking system, SubScene, entity prefab, or no baking.
- Prefer `IJobEntity`, `IJob`, `SystemAPI.Query`, and direct component/query APIs for new Entities 1.4+ plans.
- Avoid recommending new `IAspect`, `Entities.ForEach`, or `Job.WithCode` usage for new work unless maintaining existing code.
- Record structural changes and whether `EntityCommandBuffer` is needed.
- Plan inspection evidence: Entity Hierarchy/Inspector, Systems window, Query window, console/import evidence, PlayMode smoke.
- Plan profiler evidence for performance-motivated DOTS work.

## Rejection Reasons

Reject or defer DOTS when:

- entity count is low
- behavior is mostly one-off, visual, UI, or animation authored
- team/project has no Entities package installed and no clear scale pressure
- feature needs fast iteration more than data-oriented scale
- GameObject architecture with pooling, jobs, or simpler data structs solves the pressure
- verification cannot inspect baking, systems, or entity runtime state

## Source Notes

- Unity DOTS: data-oriented architecture for scalable processing, with ECS, Burst, and C# Job System. Source: https://unity.com/dots
- Unity Entities 1.4: prefer `IJobEntity`, `IJob`, `SystemAPI.Query`, and direct component/query APIs for new work; `IAspect`, `Entities.ForEach`, and `Job.WithCode` are obsolete. Source: https://docs.unity3d.com/Packages/com.unity.entities%401.4/manual/whats-new.html
- `EntityCommandBuffer` stores thread-safe commands for later playback and supports structural changes from jobs. Source: https://docs.unity3d.com/Packages/com.unity.entities%401.2/manual/systems-entity-command-buffers.html
- Baking converts GameObject authoring data into runtime entity data in the Editor. Source: https://docs.unity3d.com/Packages/com.unity.entities%401.4/manual/baking.html
