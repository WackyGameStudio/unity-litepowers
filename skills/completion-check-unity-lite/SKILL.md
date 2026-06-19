---
name: completion-check-unity-lite
description: Use when about to claim Unity Litepowers work is complete, fixed, passing, ready, or verified, including code, scene, prefab, UI, package, settings, docs, MCPForUnity evidence, TDD-required tasks, and Pattern/SOLID verification.
---

# Completion Check Unity Lite

Fresh evidence before completion claims.

## Output Language Rule

Before user-facing output or generated docs, read package doc `docs/output-language-policy.md`.

## Question Rule

Before asking completion, exception, or follow-up choice questions, read package doc `docs/guided-questioning-protocol.md`.

## Checklist

1. List changed surfaces.
2. Confirm each surface received required evidence.
3. Confirm `tdd_required` tasks have RED/GREEN evidence.
4. Confirm implementation still matches Architecture / Pattern Fit and Pattern / SOLID Verification.
5. Confirm DOTS/ECS evidence when Entities packages, baking, ECS systems, structural changes, Jobs/Burst hot paths, or entity runtime state changed.
6. Confirm MCPForUnity target identity is fresh enough for Editor-backed claims.
7. Record console/import/test/smoke/manual observation evidence.
8. Update feature `verification.md`.
9. Update `docs/litepowers/project-map.md` from actual implementation.

Do not require unrelated verification. Evidence must match changed surfaces and risk profile.

## Reference

Read `references/completion-evidence-checklist.md`.
