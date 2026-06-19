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
4. Stop and update plan/docs if required work falls outside the ticket.
5. Implement one task at a time.
6. Run the evidence plan selected by `risk-based-verification-unity`.
7. Append reusable failed attempts, unexpected Unity/tool behavior, workarounds, or skill update candidates to feature `implementation-log.md`.
8. Update feature `verification.md`.

Do not edit shared serialized Unity surfaces in parallel.

## Reference

For UI/scene/prefab evidence, read `references/mcpforunity-ui-scene-playbook.md`.
For implementation learning log format, read package doc `docs/implementation-learning-log-format.md`.
