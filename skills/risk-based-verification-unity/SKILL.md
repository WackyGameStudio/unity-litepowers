---
name: risk-based-verification-unity
description: Use when deciding verification strength for Unity Litepowers tasks, including whether TDD is required, which Unity surface evidence is enough, and whether Pattern/SOLID verification is required for implementation plans or completion checks.
---

# Risk-Based Verification Unity

Choose evidence. Do not force one verification style.

## Output Language Rule

Before user-facing output or generated docs, read package doc `docs/output-language-policy.md`.

## Question Rule

Before asking verification-choice questions, read package doc `docs/guided-questioning-protocol.md`.

## Decision

```text
TDD required = deterministic result + cheap automated setup + high regression cost
```

## Output

```markdown
## Verification Profile

- Task:
- Changed surfaces:
- Deterministic result: yes/no
- Cheap automated setup: yes/no
- High regression cost: yes/no
- Existing test seam: yes/no
- Editor/runtime wiring risk: low/medium/high
- Architecture depth: routine/focused/migration
- Architecture/pattern fit risk: low/medium/high
- DOTS/ECS surface risk: none/low/medium/high
- Behavior invariants:
- Architecture failure modes:
- Pattern/SOLID verification required: yes/no
- DOTS/ECS verification required: yes/no
- TDD decision: tdd_required | test_recommended | evidence_only | manual_observation
- Architecture evidence:
- Evidence plan:
- Completion gate:
```

## Rules

- `tdd_required`: deterministic, cheap, high-cost rule work.
- `test_recommended`: useful automated seam but setup or risk is lower.
- `evidence_only`: scene, prefab, UI, animation, package, settings, or wiring evidence dominates.
- `manual_observation`: camera feel, combat feel, VFX/SFX timing, UI visual quality, device performance.
- Pattern/SOLID verification is independent from TDD.
- Architecture risk is driven by contracts, lifecycle, state/event topology, data ownership, asmdef/API direction, and serialized wiring, not pattern count.
- Medium/high architecture risk reads `references/csharp-architecture-evidence-matrix.md` and binds failure modes to evidence.
- DOTS/ECS verification is independent from TDD and required when Entities packages, baking, ECS systems, structural changes, Jobs/Burst hot paths, or entity runtime state are changed.

## References

- Verification matrix: `references/verification-matrix.md`
- TDD suitability: `references/tdd-suitability-check.md`
- Pattern/SOLID verification: `references/pattern-solid-verification-check.md`
- C# architecture evidence: `references/csharp-architecture-evidence-matrix.md`
