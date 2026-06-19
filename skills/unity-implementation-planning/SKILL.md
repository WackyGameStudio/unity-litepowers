---
name: unity-implementation-planning
description: Use when converting Unity Litepowers GDD Lite or feature game design into a technical plan, milestones, task tickets, Unity surfaces, MCPForUnity evidence paths, risk-based verification, and SOLID/design-pattern fit decisions.
---

# Unity Implementation Planning

Create implementation plans that Unity agents can execute with minimal ambiguity.

## Process

1. Read relevant idea and game-design docs.
2. Search existing `technical-plan.md`, `project-map.md`, and feature implementation plans.
3. Read `references/task-ticket-template.md`.
4. Read `references/architecture-pattern-decision-matrix.md` for architecture-heavy tasks.
5. Read `references/mcpforunity-evidence-matrix.md` for Unity surface evidence.
6. Ask only missing high-cost decisions.
7. Write task tickets with surfaces, Architecture / Pattern Fit, verification profile, and docs update effects.
8. For feature work, save `iterations/YYYY-MM-DD-HHmmss-implementation-plan.md` before updating canonical `implementation-plan.md`.
9. Call `risk-based-verification-unity` for each task.
10. End with a Handoff block that names `executing-unity-plan-lite` when ready.

## Rules

- Do not use RED/GREEN-heavy task format by default.
- Do not apply patterns first. Record selected and rejected patterns.
- Include Pattern / SOLID Verification for medium or high architecture risk.
- Record feature-first draft path before main doc updates.
- Record feature identity, collision decision, iteration snapshot path, and handoff readiness.
