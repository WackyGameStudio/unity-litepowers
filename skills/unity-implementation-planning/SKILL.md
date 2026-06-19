---
name: unity-implementation-planning
description: Use when converting Unity Litepowers GDD Lite or feature game design into a technical plan, milestones, task tickets, Unity surfaces, MCPForUnity evidence paths, risk-based verification, and SOLID/design-pattern fit decisions.
---

# Unity Implementation Planning

Create implementation plans that Unity agents can execute with minimal ambiguity.

## Process

1. Read relevant idea and game-design docs.
2. Search existing `technical-plan.md`, `project-map.md`, and feature implementation plans.
3. Read package doc `docs/output-language-policy.md`.
4. Read package doc `docs/guided-questioning-protocol.md`.
5. Read `references/task-ticket-template.md`.
6. Read `references/architecture-pattern-decision-matrix.md` for architecture-heavy tasks.
7. Read `references/dots-ecs-decision-matrix.md` when large entity counts, CPU hot paths, deterministic simulation, streaming, heavy AI/resource simulation, or large multiplayer are plausible.
8. Read `references/mcpforunity-evidence-matrix.md` for Unity surface evidence.
9. Ask only missing high-cost decisions.
10. For each architecture, SOLID, pattern, DOTS/ECS, Unity surface, or verification decision, present exactly two context-suitable options, recommendation, reason, and evidence note.
11. Use source/project/web search before asking when option quality depends on facts not in docs.
12. Do not invent filler choices; if only one option is viable, ask for confirmation.
13. Write task tickets with surfaces, Architecture / Pattern Fit, DOTS / ECS Suitability when relevant, verification profile, and docs update effects.
14. For feature work, save `iterations/YYYY-MM-DD-HHmmss-implementation-plan.md` before updating canonical `implementation-plan.md`.
15. Call `risk-based-verification-unity` for each task.
16. End with a Handoff block that names `executing-unity-plan-lite` when ready.

## Rules

- Do not use RED/GREEN-heavy task format by default.
- Do not apply patterns first. Record selected and rejected patterns.
- Do not apply DOTS first. Record DOTS/ECS candidate level and rejection reason when scale or CPU pressure makes it plausible.
- Include Pattern / SOLID Verification for medium or high architecture risk.
- Record feature-first draft path before main doc updates.
- Record feature identity, collision decision, iteration snapshot path, and handoff readiness.
