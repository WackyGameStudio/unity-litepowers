# Litepowers Docs Schema

Target Unity projects use:

```text
docs/litepowers/
  project-idea.md
  game-design.md
  technical-plan.md
  project-map.md
  context/
    unity-project-profile.md
  features/
    YYYY-MM-DD-feature-name/
      feature.md
      idea.md
      game-design.md
      implementation-plan.md
      verification.md
      iterations/
        YYYY-MM-DD-HHmmss-idea.md
        YYYY-MM-DD-HHmmss-game-design.md
        YYYY-MM-DD-HHmmss-implementation-plan.md
```

## Main Docs

- `project-idea.md`: game direction and MVP idea.
- `game-design.md`: GDD Lite and gameplay system design.
- `technical-plan.md`: Unity implementation architecture, milestones, task template, risk plan.
- `project-map.md`: current implemented structure after completion checks.
- `context/unity-project-profile.md`: Unity version, pipeline, platform, bridge, package, test readiness.

## Feature Docs

Feature docs are drafts and implementation history for one feature or expansion.

Repeated planning must write feature docs first:

```text
docs/litepowers/features/YYYY-MM-DD-feature-name/
```

Main docs are updated after approval or completion when the feature changes project-wide direction, GDD, technical architecture, or implemented structure.

## Question Log Rule

Planning docs should include a `## Question Log` section when user decisions shape scope, design, architecture, verification, or handoff.

Each entry records:

- current situation summary
- two options considered
- recommendation and reason
- user answer
- evidence source when docs, source, Unity Editor, or web search informed the options

## Feature Collision Rule

- `feature.md` stores title, slug, created, status, latest canonical docs, and main docs merge status.
- If `YYYY-MM-DD-feature-name/` does not exist, create it.
- If it exists and `feature.md` matches the same feature, reuse it.
- If it exists but identity differs or is unclear, create `YYYY-MM-DD-feature-name-02/`, then `-03/`.
- Every planning run writes `iterations/YYYY-MM-DD-HHmmss-<phase>.md` first.
- Update canonical `idea.md`, `game-design.md`, `implementation-plan.md`, or `verification.md` only after approval or explicit update condition.

## Handoff Rule

Every planning phase ends with:

```markdown
## Handoff

- Stage status: draft | approved | blocked
- Written docs:
- Canonical docs updated:
- Main docs update needed:
- Open decisions:
- Recommended next skill:
- Ready to continue: yes/no
```

Continue to the recommended next skill only when `Ready to continue: yes` and the user approved the phase.

## Project Map Rule

Planning does not pre-edit `project-map.md`. Completion checks update it from actual implementation evidence.
