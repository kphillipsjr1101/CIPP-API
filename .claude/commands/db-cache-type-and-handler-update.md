---
name: db-cache-type-and-handler-update
description: Workflow command scaffold for db-cache-type-and-handler-update in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /db-cache-type-and-handler-update

Use this workflow when working on **db-cache-type-and-handler-update** in `CIPP-API`.

## Goal

Adds or updates a DB cache type and its handler, often with a corresponding ORCA test.

## Common Files

- `Config/CIPPDBCacheTypes.json`
- `Modules/CIPPDB/Public/DBCache/Set-CIPPDBCache*.ps1`
- `Modules/CIPPCore/Public/Invoke-CIPPDBCacheCollection.ps1`
- `Modules/CIPPTests/Public/Tests/ORCA/Identity/Invoke-CippTestORCA*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit Config/CIPPDBCacheTypes.json to add or update cache type
- Edit or create handler script in Modules/CIPPDB/Public/DBCache/Set-CIPPDBCache*.ps1
- Optionally, update Modules/CIPPCore/Public/Invoke-CIPPDBCacheCollection.ps1
- Optionally, add or update related ORCA test

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.