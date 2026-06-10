---
name: orca-test-fix-or-addition
description: Workflow command scaffold for orca-test-fix-or-addition in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /orca-test-fix-or-addition

Use this workflow when working on **orca-test-fix-or-addition** in `CIPP-API`.

## Goal

Fixes or adds an ORCA test case, often in response to a bug or feature request.

## Common Files

- `Modules/CIPPTests/Public/Tests/ORCA/Identity/Invoke-CippTestORCA*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify ORCA test needing fix or addition
- Edit or create the corresponding test file in Modules/CIPPTests/Public/Tests/ORCA/Identity/
- Commit with message referencing ORCA test number

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.