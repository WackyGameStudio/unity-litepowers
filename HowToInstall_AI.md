# How To Install Unity Litepowers

Install into a Unity project as project-local skills.

## Codex Shape

Copy skill folders into:

```text
<UnityProject>/
  AGENTS.md
  .agents/
    skills/
      using-litepowers-unity/
      unity-bootstrap/
      unity-project-idea/
      unity-game-planning/
      unity-implementation-planning/
      risk-based-verification-unity/
      executing-unity-plan-lite/
      systematic-debugging-unity-lite/
      completion-check-unity-lite/
```

Add the AGENTS rules from this package to the target project's `AGENTS.md`.

Restart or refresh the coding agent if project-local skills are not discovered.

This package is currently shaped for project-local skills. Plugin or marketplace distribution would also need package metadata such as a plugin manifest and optional skill UI metadata.

## Target Project Docs

Create or preserve:

```text
<UnityProject>/docs/litepowers/
```

The installed skills create main docs only when missing or approved.
