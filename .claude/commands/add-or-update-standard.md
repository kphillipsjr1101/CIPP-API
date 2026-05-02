---
name: add-or-update-standard
description: Workflow command scaffold for add-or-update-standard in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-standard

Use this workflow when working on **add-or-update-standard** in `CIPP-API`.

## Goal

Adds a new CIPP Standard or updates an existing one, which defines a compliance or configuration policy.

## Common Files

- `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or modify a script in Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1
- Optionally update related documentation or instructions in .github/instructions/standards.instructions.md
- Commit the new or updated standard script

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.