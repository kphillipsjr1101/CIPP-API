---
name: add-or-update-http-endpoint
description: Workflow command scaffold for add-or-update-http-endpoint in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-http-endpoint

Use this workflow when working on **add-or-update-http-endpoint** in `CIPP-API`.

## Goal

Adds a new HTTP API entrypoint or updates an existing one, typically for new features or bugfixes.

## Common Files

- `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or update a script in Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/...
- Optionally update related modules or core logic if needed.
- Commit the new or changed endpoint file.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.