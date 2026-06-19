---
name: systematic-debugging-unity-lite
description: Use when investigating Unity bugs, regressions, unexpected behavior, console/import errors, scene or prefab wiring failures, PlayMode issues, package problems, MCPForUnity target mismatch, or serialized reference issues.
---

# Systematic Debugging Unity Lite

Find root surface before fixing.

## Process

1. Reproduce or define the symptom.
2. Collect console/import/package/scene/prefab/runtime evidence.
3. Confirm MCPForUnity target identity for Editor-backed evidence.
4. Classify root surface.
5. If deterministic, cheap, and high regression cost, add regression test.
6. Otherwise record minimal repro and evidence-only gate.
7. Write fix plan before changing code or assets.

## Reference

Read `references/debugging-evidence-flow.md` when evidence path is unclear.
