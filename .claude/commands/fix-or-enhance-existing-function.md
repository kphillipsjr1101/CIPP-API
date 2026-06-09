---
name: fix-or-enhance-existing-function
description: Workflow command scaffold for fix-or-enhance-existing-function in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /fix-or-enhance-existing-function

Use this workflow when working on **fix-or-enhance-existing-function** in `CIPP-API`.

## Goal

Fixes or improves an existing PowerShell function, often standardizing variables, fixing bugs, or improving logic.

## Common Files

- `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandardSPOVersionControl.ps1`
- `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/Email-Exchange/Tools/Invoke-ListMessageTrace.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify the function needing a fix or enhancement.
- Edit the corresponding .ps1 file to update logic, variable casing, or permissions.
- Commit the changes with a descriptive message.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.