# AGENTS.md

## Unity Litepowers Package Work

This package provides token-light Unity workflow skills for AI coding agents.

Keep skills concise. Put heavy checklists, templates, MCPForUnity routing, architecture pattern matrices, and verification matrices in `references/`.

`lite` means token-light, not rigor-light. Completion still needs evidence.

## Required Package Behavior

- Unity work starts by searching `docs/litepowers`.
- Feature expansion writes timestamped iteration snapshots under `docs/litepowers/features/YYYY-MM-DD-feature-name/` first, then updates canonical feature docs and main docs only when approved or completed.
- `docs/litepowers/project-map.md` is updated by completion checks after implementation, not during planning.
- MCPForUnity is the primary Unity Editor evidence path.
- TDD is automatic only when deterministic result, cheap automated setup, and high regression cost justify it.
- Implementation planning and completion checks verify SOLID and Unity design pattern fit.
