# Output Language Policy

Use this for every user-facing response and generated project document.

## Rule

- Match the user's primary language for explanations, questions, planning docs, design docs, task tickets, verification notes, handoff blocks, and completion summaries.
- Preserve English when it is more natural or exact: Unity API names, C# symbols, file paths, package names, design pattern names, SOLID terms, tool names, error text, log output, Git refs, code identifiers, commands, and asset names.
- If the user mixes languages, use the language that carries the intent. Keep technical terms in their conventional form.
- If existing docs use a different language, prefer the current user's language for new content and avoid rewriting old docs only for translation.
- If multiple human audiences are explicit, ask which language to use before writing long-form docs.

## Examples

- Korean user: write rationale and decisions in Korean; keep `ScriptableObject`, `Object Pool`, `MCPForUnity`, `Application.dataPath`, and class names in English.
- English user: write outputs in English.
- Mixed request: follow the user's sentence language; keep established Unity terms unchanged.
