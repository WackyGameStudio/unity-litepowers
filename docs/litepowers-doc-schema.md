# Litepowers Docs Schema

Target Unity projects use:

```text
docs/litepowers/
  project-idea.md
  game-design.md
  technical-plan.md
  project-map.md
  skill-feedback.md
  context/
    unity-project-profile.md
  features/
    YYYY-MM-DD-feature-name/
      feature.md
      idea.md
      game-design.md
      implementation-plan.md
      verification.md
      implementation-log.md
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
- `skill-feedback.md`: distilled reusable lessons from implementation logs for future skill updates.
- `context/unity-project-profile.md`: Unity version, pipeline, platform, bridge, package, test readiness.

## Feature Docs

Feature docs are drafts and implementation history for one feature or expansion.

Repeated planning must write feature docs first:

```text
docs/litepowers/features/YYYY-MM-DD-feature-name/
```

Main docs are updated after approval or completion when the feature changes project-wide direction, GDD, technical architecture, or implemented structure.

## Implementation Learning Log Rule

Execution and debugging can append raw reusable learning to feature-local `implementation-log.md`.

Log only failed attempts, unexpected Unity/tool behavior, useful workaround, repeated friction, or concrete skill update candidates. Do not log routine successful edits.

Completion checks read feature `implementation-log.md` and append only distilled reusable lessons to root `skill-feedback.md`.

If work has no feature folder and produces log-worthy learning, select or create an appropriate feature folder before logging so raw notes stay near the work that produced them.

## Output Language Rule

User-facing outputs and generated project docs match the user's primary language. Keep English terms when they are technical identifiers, Unity/API names, code symbols, file paths, package/tool names, logs, errors, Git refs, or standard pattern/SOLID names.

## C# Architecture Track Rule

C# architecture guidance is conditional.

- `technical-plan.md` records stable project policy: depth triggers, dependency direction, lifecycle conventions, serialized wiring policy, and evidence policy.
- Feature `implementation-plan.md` and task tickets record intended change: depth, behavior invariants, change pressure, ownership, lifecycle, serialized wiring, selected/rejected approaches, and migration/rollback when needed.
- `verification.md` records evidence for behavior invariants, architecture failure modes, lifecycle, event, data ownership, and serialized wiring.
- `project-map.md` is updated only after actual completion evidence.
- `implementation-log.md` stores reusable architecture failures/learnings, not routine successful refactors.

Do not create a mandatory separate target-project architecture document for this track.

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

Routers must inspect the latest Handoff in relevant main docs, feature canonical docs, and newest feature iteration before choosing the next skill. If the latest Handoff is `blocked`, `draft`, `Ready to continue: no`, or not user-approved, resume the phase that owns the open decision instead of advancing.

## Project Map Rule

Planning does not pre-edit `project-map.md`. Completion checks update it from actual implementation evidence.
