---
name: add-or-update-api-endpoint
description: Workflow command scaffold for add-or-update-api-endpoint in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-api-endpoint

Use this workflow when working on **add-or-update-api-endpoint** in `CIPP-API`.

## Goal

Adds or updates an API endpoint (HTTP function) for a specific feature or resource.

## Common Files

- `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or update a script in Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/Invoke-*.ps1
- Optionally update related core logic or helper scripts

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.