# Implementation Learning Log Format

Use this when execution or debugging produces reusable learning.

Do not log routine successful edits. Log only failed attempts, unexpected Unity/tool behavior, useful workaround, repeated friction, or a concrete skill update candidate.

## Feature Implementation Log

Append raw entries to:

```text
docs/litepowers/features/YYYY-MM-DD-feature-name/implementation-log.md
```

Entry format:

```markdown
## YYYY-MM-DD HH:mm - <short title>

- Task:
- Context:
- Attempt:
- Failed because:
- Working solution:
- Evidence:
- Skill update candidate:
- Tags:
```

Keep entries short. Link or summarize evidence instead of pasting large logs.

## Skill Feedback Ledger

During completion checks, distill reusable entries into:

```text
docs/litepowers/skill-feedback.md
```

Entry format:

```markdown
## YYYY-MM-DD - <short title>

- Source:
- Repeating pattern:
- Recommended skill update:
- Affected skill/reference:
- Evidence:
- Status: candidate | applied | rejected
```

Do not copy every raw implementation log entry. Promote only learnings likely to improve future skill behavior.

## Safety

- Do not include secrets, tokens, private keys, license keys, or personal data.
- Redact local absolute paths when they are not needed to understand the lesson.
- Preserve exact error text only when useful and safe.
