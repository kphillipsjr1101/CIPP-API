---
name: bulk-alert-module-refactor
description: Workflow command scaffold for bulk-alert-module-refactor in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /bulk-alert-module-refactor

Use this workflow when working on **bulk-alert-module-refactor** in `CIPP-API`.

## Goal

Refactor or migrate multiple alert PowerShell scripts to use a new shared function or error handling pattern.

## Common Files

- `Modules/CIPPCore/Public/Alerts/*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify all alert scripts in Modules/CIPPCore/Public/Alerts/
- Update each script to use the new function or pattern (e.g., Get-CippException)
- Commit all updated alert scripts together

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.