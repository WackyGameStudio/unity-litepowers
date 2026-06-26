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
5. Read `references/technical-plan-template.md` when creating or updating a technical plan.
6. Read `references/milestone-template.md` when grouping work into milestones.
7. Read `references/task-ticket-template.md` for executable tasks.
8. Read `references/unity-csharp-architecture-guide.md` when C# work changes contracts, responsibility ownership, state/event topology, lifecycle, `ScriptableObject` ownership, composition/inheritance, asmdef/API direction, or serialized prefab/scene wiring.
9. Read `references/architecture-pattern-decision-matrix.md` for architecture-heavy tasks.
10. Read `references/dots-ecs-decision-matrix.md` when large entity counts, CPU hot paths, deterministic simulation, streaming, heavy AI/resource simulation, or large multiplayer are plausible.
11. Read `references/mcpforunity-evidence-matrix.md` for Unity surface evidence.
12. Ask only missing high-cost decisions.
13. For each architecture, SOLID, pattern, DOTS/ECS, Unity surface, or verification decision, present exactly two context-suitable options, recommendation, reason, and evidence note.
14. Use source/project/web search before asking when option quality depends on facts not in docs.
15. Do not invent filler choices; if only one option is viable, ask for confirmation.
16. Write technical plan, milestones, and task tickets with surfaces, C# Architecture Profile when relevant, DOTS / ECS Suitability when relevant, verification profile, and docs update effects.
17. For feature work, save `iterations/YYYY-MM-DD-HHmmss-implementation-plan.md` before updating canonical `implementation-plan.md`.
18. Call `risk-based-verification-unity` for each task.
19. End with a Handoff block that names `executing-unity-plan-lite` when ready.

## Rules

- Do not use RED/GREEN-heavy task format by default.
- Select `routine | focused | migration` depth from concrete triggers; depth controls documentation and evidence.
- Record behavior invariants before selecting patterns.
- Do not apply patterns first. Record selected and rejected patterns and pressure per pattern.
- Bind selected patterns, architecture failure modes, migration risks, and serialized/lifecycle risks to evidence.
- Do not apply DOTS first. Record DOTS/ECS candidate level and rejection reason when scale or CPU pressure makes it plausible.
- Include Pattern / SOLID Verification for medium or high architecture risk.
- Record feature-first draft path before main doc updates.
- Record feature identity, collision decision, iteration snapshot path, and handoff readiness.
