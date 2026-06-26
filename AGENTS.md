# AGENTS.md

## Unity Litepowers Package Work

This package provides token-light Unity workflow skills for AI coding agents.

Keep skills concise. Put heavy checklists, templates, MCPForUnity routing, architecture pattern matrices, and verification matrices in `references/`.

`lite` means token-light, not rigor-light. Completion still needs evidence.

## Required Package Behavior

- Unity work starts by searching `docs/litepowers`.
- Feature expansion writes timestamped iteration snapshots under `docs/litepowers/features/YYYY-MM-DD-feature-name/` first, then updates canonical feature docs and main docs only when approved or completed.
- `docs/litepowers/project-map.md` is updated by completion checks after implementation, not during planning.
- Execution/debugging can append raw reusable learning to feature `implementation-log.md`; completion distills skill update candidates into `docs/litepowers/skill-feedback.md`.
- MCPForUnity is the primary Unity Editor evidence path.
- TDD is automatic only when deterministic result, cheap automated setup, and high regression cost justify it.
- Implementation planning and completion checks verify SOLID and Unity design pattern fit.
- Keep C# architecture pressure-first and evidence-bound: record behavior invariants before patterns, select `routine | focused | migration` depth, and tie lifecycle/serialized/event/data ownership to evidence.
- Keep routine C# work terse. Put detailed ownership, lifecycle, serialized migration, and pattern evidence rules in `references/` and require them only for focused/migration work.
- Do not enforce pattern quotas, class-size quotas, interface-per-class, composition-only, or blanket plain-C# extraction.
- Do not copy runtime code from external teaching repositories into this skill package; independently restate decision rules and preserve license boundaries.
- Implementation planning considers DOTS/ECS through a suitability gate, not as a default architecture.
- Decision questions present exactly two suitable options, recommend one, and explain the reason.
- User-facing outputs and generated project docs match the user's language; keep English technical terms when more exact.
