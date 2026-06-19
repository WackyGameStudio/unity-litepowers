# Guided Questioning Protocol

Use this before asking planning, design, architecture, verification, or handoff questions.

## Grounding

Start from current context:

- user request
- existing `docs/litepowers` main docs
- related feature docs and latest iteration draft
- project-map and Unity project profile when relevant
- source files, Unity evidence, or web search when local context is insufficient

Use web search only when the decision depends on current Unity/package/tooling facts or external references. Cite or name the evidence briefly in the question.

## Question Rules

- Ask one blocking question at a time.
- Explain the current situation before options.
- Present exactly two options for decision questions.
- Make both options suitable for the current context. Do not add filler.
- Make the options meaningfully different in cost, risk, scope, architecture, player experience, or evidence path.
- Recommend one option and explain why.
- If only one option is viable, say so and ask for confirmation. Do not invent a second option.
- If no recommendation is defensible yet, read/search first or ask for missing context.
- Keep the question short enough to answer in one reply.

## Format

```markdown
Current situation:
Decision needed:

Option A - <name>:
- Best when:
- Tradeoff:

Option B - <name>:
- Best when:
- Tradeoff:

Recommendation:
Reason:
Evidence:
Question:
```

Omit `Evidence` only when the choice comes entirely from already-read project docs or user-provided context.
