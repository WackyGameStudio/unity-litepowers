---
name: executing-unity-plan-lite
description: Use when executing an approved Unity Litepowers implementation plan or task ticket, especially when code, scene, prefab, UI, asset, package, settings, docs, MCPForUnity evidence, feature verification updates, or feature implementation-log capture are involved.
---

# Executing Unity Plan Lite

Execute approved plans task by task.

## Output Language Rule

Before user-facing output or generated docs, read package doc `docs/output-language-policy.md`.

## Question Rule

Before asking scope, implementation, or evidence-choice questions, read package doc `docs/guided-questioning-protocol.md`.

## Rules

1. Read current implementation plan or task ticket.
2. Check Git status.
3. If Editor-backed work is needed, verify MCPForUnity target identity.
4. For focused/migration C# architecture work, read `references/unity-csharp-refactor-playbook.md`.
5. Stop and update plan/docs if required work falls outside the ticket.
6. Implement one task at a time.
7. Preserve behavior invariants and execute compilable, evidence-checked slices.
8. Run the evidence plan selected by `risk-based-verification-unity`.
9. Append reusable failed attempts, unexpected Unity/tool behavior, workarounds, or skill update candidates to feature `implementation-log.md`.
10. Update feature `verification.md`.

Do not edit shared serialized Unity surfaces in parallel.
Stop and return to planning if contract, lifecycle, serialized migration, affected asset scope, save/data compatibility, package scope, or architecture selection exceeds the approved ticket.

## Reference

For UI/scene/prefab evidence, read `references/mcpforunity-ui-scene-playbook.md`.
For focused/migration C# architecture execution, read `references/unity-csharp-refactor-playbook.md`.
For implementation learning log format, read package doc `docs/implementation-learning-log-format.md`.
