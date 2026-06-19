# Unity Litepowers

Unity Litepowers is a token-light Unity skill package for AI coding agents working on commercial-style Unity game projects.

`lite` means token-light, not rigor-light. The package avoids blanket TDD and heavy execution ceremony, but still requires fresh evidence before completion claims.

## Core Flow

1. `using-litepowers-unity`
2. `unity-bootstrap`
3. `unity-project-idea`
4. `unity-game-planning`
5. `unity-implementation-planning`
6. `risk-based-verification-unity`
7. `executing-unity-plan-lite`
8. `completion-check-unity-lite`

Bug work starts with `systematic-debugging-unity-lite`.

## Design Rules

- Read `docs/litepowers` before planning new Unity work.
- Keep main docs and feature docs consistent.
- Capture reusable failed attempts, workarounds, and skill update candidates in feature `implementation-log.md`; distill them into `skill-feedback.md` during completion checks.
- Use MCPForUnity as the primary Unity Editor evidence path.
- Use TDD only when `risk-based-verification-unity` marks it required.
- Verify Unity scene, prefab, UI, animation, physics, package, and settings surfaces with appropriate evidence.
- Verify implementation plans against SOLID and Unity design pattern fit.
- Consider DOTS/ECS through a suitability gate for scale, CPU, determinism, streaming, or multiplayer pressure.
- Ask decision questions with exactly two suitable options, a recommendation, and a reason.
- Match user-facing outputs and generated project docs to the user's language, while preserving exact English technical terms.
