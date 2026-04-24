---
name: standard-script-batch-update
description: Workflow command scaffold for standard-script-batch-update in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /standard-script-batch-update

Use this workflow when working on **standard-script-batch-update** in `CIPP-API`.

## Goal

Batch updating or adding comments, documentation, or required sections across all standards scripts.

## Common Files

- `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1`
- `Tools/Update-StandardsComments.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit many files under Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1
- Optionally update or add a helper script for batch updating (e.g., Tools/Update-StandardsComments.ps1)

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.