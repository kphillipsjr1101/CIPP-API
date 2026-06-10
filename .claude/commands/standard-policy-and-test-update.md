---
name: standard-policy-and-test-update
description: Workflow command scaffold for standard-policy-and-test-update in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /standard-policy-and-test-update

Use this workflow when working on **standard-policy-and-test-update** in `CIPP-API`.

## Goal

Updates a standard policy implementation and its corresponding ORCA test.

## Common Files

- `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1`
- `Modules/CIPPTests/Public/Tests/ORCA/Identity/Invoke-CippTestORCA*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit policy script in Modules/CIPPStandards/Public/Standards/
- Edit or update corresponding ORCA test in Modules/CIPPTests/Public/Tests/ORCA/Identity/

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.