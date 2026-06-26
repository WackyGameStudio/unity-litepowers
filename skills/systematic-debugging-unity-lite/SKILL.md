---
name: systematic-debugging-unity-lite
description: Use when investigating Unity bugs, regressions, unexpected behavior, console/import errors, scene or prefab wiring failures, PlayMode issues, package problems, MCPForUnity target mismatch, serialized reference issues, or debugging lessons that should be captured in implementation-log.
---

# Systematic Debugging Unity Lite

Find root surface before fixing.

## Output Language Rule

Before user-facing output or generated docs, read package doc `docs/output-language-policy.md`.

## Question Rule

Before asking repro, scope, or fix-choice questions, read package doc `docs/guided-questioning-protocol.md`.

## Process

1. Reproduce or define the symptom.
2. Collect console/import/package/scene/prefab/runtime evidence.
3. Confirm MCPForUnity target identity for Editor-backed evidence.
4. Classify root surface.
5. For architecture-shaped symptoms, classify event lifetime, State transition, lifecycle order, shared mutable data, composition-root selection, or serialized migration surface before changing structure.
6. If deterministic, cheap, and high regression cost, add regression test.
7. Otherwise record minimal repro and evidence-only gate.
8. Write fix plan before changing code or assets.
9. Append reusable failed hypotheses, root cause, working fix, or skill update candidates to feature `implementation-log.md`.

Do not turn a minimal bug fix into an unapproved architecture rewrite.

## Reference

Read `references/debugging-evidence-flow.md` when evidence path is unclear.
For implementation learning log format, read package doc `docs/implementation-learning-log-format.md`.
