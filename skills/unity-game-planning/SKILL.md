---
name: unity-game-planning
description: Use when expanding a Unity Litepowers project idea or feature idea into a GDD Lite, gameplay systems, UI flow, content/data rules, and Unity-facing design decisions through guided questions.
---

# Unity Game Planning

Turn project idea output into a GDD Lite or feature game-design draft.

## Process

1. Read relevant idea document.
2. Search existing `docs/litepowers/game-design.md` and related feature docs.
3. Read package doc `docs/output-language-policy.md`.
4. Read package doc `docs/guided-questioning-protocol.md`.
5. Read relevant templates in `references/`.
6. Fill every required system field.
7. Skip questions already answered by docs.
8. Ask only missing player-facing, system, content, UI, or Unity design decisions.
9. For each decision question, present exactly two context-suitable options, recommendation, reason, and evidence note.
10. Use source/project/web search before asking when option quality depends on facts not in docs.
11. Do not invent filler choices; if only one option is viable, ask for confirmation.
12. For feature work, save `iterations/YYYY-MM-DD-HHmmss-game-design.md` before updating canonical `game-design.md`.
13. Save to main `game-design.md` only for first creation or approved main update.
14. End with a Handoff block that names `unity-implementation-planning` when ready.

## Scope Rule

- For narrow features, keep unchanged or irrelevant required fields short: `unchanged`, `N/A`, or one sentence.
- Expand only fields affected by the current idea, feature, or open decision.
- Do not create broad GDD prose when the user asked for a small feature extension.

## Required Coverage

- game overview
- design value
- core loop details
- MVP scope
- systems list
- controls
- camera
- combat/interaction
- character/AI
- progression/reward/economy
- content data
- UI/UX flow
- level/stage
- animation
- art/audio production criteria
- save/load
- localization/accessibility
- analytics/operation events
- Unity technical assumptions
- performance criteria
- testing criteria
- change control
