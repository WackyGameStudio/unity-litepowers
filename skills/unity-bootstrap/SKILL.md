---
name: unity-bootstrap
description: Use when a Unity project needs Litepowers readiness checks, Unity version/profile discovery, Git/project marker inspection, docs/litepowers setup, MCPForUnity setup or active target identity verification, console/import evidence, or test readiness checks.
---

# Unity Bootstrap

Prepare or verify the Unity work surface. Ask approval before project mutation.

## Question Rule

Before asking mutation or setup-choice questions, read package doc `docs/guided-questioning-protocol.md`.

## Checklist

1. Confirm Unity project markers: `Assets/`, `Packages/manifest.json`, `ProjectSettings/ProjectVersion.txt`.
2. Inspect Unity version, render pipeline, target platform, and packages.
3. Inspect Git status.
4. Ensure `docs/litepowers` exists or report missing docs.
5. Read or create `docs/litepowers/context/unity-project-profile.md`.
6. Verify MCPForUnity install/config/state.
7. Verify active Unity target with `Application.dataPath` or equivalent Unity-observed evidence.
8. Read console/import evidence.
9. Check Unity Test Framework readiness.

## Mutation Rule

Ask approval before creating Unity projects, changing Git, installing packages, editing MCP config, adding Git LFS, or writing project settings.

## References

- For MCPForUnity setup details, read `references/mcpforunity-setup.md`.
- For profile template, read `references/unity-project-profile.md`.
