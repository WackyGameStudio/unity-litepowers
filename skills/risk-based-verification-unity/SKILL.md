---
name: risk-based-verification-unity
description: Use when deciding verification strength for Unity Litepowers tasks, including whether TDD is required, which Unity surface evidence is enough, and whether Pattern/SOLID verification is required for implementation plans or completion checks.
---

# Risk-Based Verification Unity

Choose evidence. Do not force one verification style.

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
- Architecture/pattern fit risk: low/medium/high
- Pattern/SOLID verification required: yes/no
- TDD decision: tdd_required | test_recommended | evidence_only | manual_observation
- Evidence plan:
- Completion gate:
```

## Rules

- `tdd_required`: deterministic, cheap, high-cost rule work.
- `test_recommended`: useful automated seam but setup or risk is lower.
- `evidence_only`: scene, prefab, UI, animation, package, settings, or wiring evidence dominates.
- `manual_observation`: camera feel, combat feel, VFX/SFX timing, UI visual quality, device performance.
- Pattern/SOLID verification is independent from TDD.

## References

- Verification matrix: `references/verification-matrix.md`
- TDD suitability: `references/tdd-suitability-check.md`
- Pattern/SOLID verification: `references/pattern-solid-verification-check.md`
