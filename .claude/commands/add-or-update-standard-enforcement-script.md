---
name: add-or-update-standard-enforcement-script
description: Workflow command scaffold for add-or-update-standard-enforcement-script in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-standard-enforcement-script

Use this workflow when working on **add-or-update-standard-enforcement-script** in `CIPP-API`.

## Goal

Adds or updates a standard enforcement script (policy/standard enforcement) for Microsoft 365/Intune/Teams/etc.

## Common Files

- `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or update a script in Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1
- Optionally update related documentation or report/test files

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.