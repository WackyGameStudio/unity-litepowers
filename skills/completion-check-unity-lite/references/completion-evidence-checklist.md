# Completion Evidence Checklist

## Required Report Fields

- Changed surfaces:
- Architecture depth: routine | focused | migration | N/A
- Planned architecture:
- Actual architecture:
- Plan deviations:
- Behavior invariants:
- Architecture failure modes:
- Evidence run:
- MCPForUnity identity evidence:
- Tests:
- Console/import:
- Manual observation:
- Pattern/SOLID fit:
- Pattern-specific evidence:
- Lifecycle evidence:
- Serialized wiring evidence:
- Config/runtime-state evidence:
- Compatibility/rollback status:
- Implementation log reviewed:
- Skill feedback updated:
- Docs updated:
- Evidence gaps:

Use `N/A` for routine work where a field does not apply.

## Architecture Blockers

- Missing serialized references.
- Unmigrated prefabs, scenes, variants, or runtime-created paths.
- Old and new compatibility paths both run unexpectedly.
- Event lifetime or subscription symmetry is uncertain.
- State transition ownership or re-entry policy is unclear.
- `ScriptableObject` runtime mutation can affect another instance or asset unexpectedly.
- API/asmdef compatibility is unverified.
- Evidence came from wrong or stale Unity target.
- Planned and actual architecture differ without updated docs and evidence.

## Project Map Update

Update `docs/litepowers/project-map.md` after implementation with:

- major folders and responsibilities
- important files and functions
- scene, prefab, data asset, UI, package/settings relationships
- feature entrypoints
- recent feature implementation area
- C# modules and assembly boundaries
- composition roots and concrete selection points
- MonoBehaviour orchestrators
- plain-C# policies
- capability interfaces and extension points
- State machines and transition owners
- event topology and subscription ownership
- ScriptableObject config and runtime-state ownership
- serialized component contracts
- prefab/scene wiring
- lifecycle/order assumptions
- known architecture debt
- Mermaid architecture diagram
- Mermaid scene flow diagram
- pattern map: system, pattern/SOLID reason, files, evidence
- DOTS/ECS map when used: systems, components, baking path, GameObject boundary, package versions, evidence
