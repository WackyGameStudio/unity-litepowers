---
name: unity-implementation-planning
description: Use when converting Unity Litepowers GDD Lite or feature game design into a technical plan, milestones, task tickets, Unity surfaces, MCPForUnity evidence paths, risk-based verification, and SOLID/design-pattern fit decisions.
---

# Unity Implementation Planning

Create implementation plans that Unity agents can execute with minimal ambiguity.

## Process

1. Read relevant idea and game-design docs.
2. Search existing `technical-plan.md`, `project-map.md`, and feature implementation plans.
3. Read package doc `docs/guided-questioning-protocol.md`.
4. Read `references/task-ticket-template.md`.
5. Read `references/architecture-pattern-decision-matrix.md` for architecture-heavy tasks.
6. Read `references/mcpforunity-evidence-matrix.md` for Unity surface evidence.
7. Ask only missing high-cost decisions.
8. For each architecture, SOLID, pattern, Unity surface, or verification decision, present exactly two context-suitable options, recommendation, reason, and evidence note.
9. Use source/project/web search before asking when option quality depends on facts not in docs.
10. Do not invent filler choices; if only one option is viable, ask for confirmation.
11. Write task tickets with surfaces, Architecture / Pattern Fit, verification profile, and docs update effects.
12. For feature work, save `iterations/YYYY-MM-DD-HHmmss-implementation-plan.md` before updating canonical `implementation-plan.md`.
13. Call `risk-based-verification-unity` for each task.
14. End with a Handoff block that names `executing-unity-plan-lite` when ready.

## Rules

- Do not use RED/GREEN-heavy task format by default.
- Do not apply patterns first. Record selected and rejected patterns.
- Include Pattern / SOLID Verification for medium or high architecture risk.
- Record feature-first draft path before main doc updates.
- Record feature identity, collision decision, iteration snapshot path, and handoff readiness.
