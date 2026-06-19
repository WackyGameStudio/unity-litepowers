---
name: using-litepowers-unity
description: Use when starting any Unity game development request in a project that uses Unity Litepowers, including new game ideas, feature planning, implementation, debugging, verification, docs updates, scene/prefab/UI work, or MCPForUnity-backed Unity Editor work.
---

# Using Unity Litepowers

Route Unity work through the smallest needed Litepowers skill.

## Start

1. Search `docs/litepowers` and related `features/**`.
2. Check `docs/litepowers/context/unity-project-profile.md`.
3. Read package doc `docs/output-language-policy.md` before user-facing output or generated docs.
4. Read package doc `docs/guided-questioning-protocol.md` before asking planning or choice questions.
5. If Unity project identity or MCPForUnity state is unknown, use `unity-bootstrap`.
6. Choose next skill:

| Request | Next skill |
| --- | --- |
| new game or feature idea | `unity-project-idea` |
| GDD or system design | `unity-game-planning` |
| task plan | `unity-implementation-planning` |
| implementation | `executing-unity-plan-lite` |
| bug or regression | `systematic-debugging-unity-lite` |
| completion claim | `completion-check-unity-lite` |

## Rules

- Do not overwrite main docs with repeated planning drafts. Write timestamped iteration snapshots under `docs/litepowers/features/YYYY-MM-DD-feature-name/iterations/` first.
- Use `feature.md` and numeric suffixes to avoid same-day same-slug collisions.
- Do not trust Editor-backed claims until MCPForUnity target identity is confirmed.
- Do not force TDD. Use `risk-based-verification-unity` to decide.
- Do verify SOLID and Unity design pattern fit for implementation plans and completion checks.
- For decision questions, present exactly two context-suitable options, recommend one, and state why.
- Match output language to the user; keep exact English technical terms where clearer.
