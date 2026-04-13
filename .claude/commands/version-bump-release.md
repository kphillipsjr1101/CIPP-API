---
name: version-bump-release
description: Workflow command scaffold for version-bump-release in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /version-bump-release

Use this workflow when working on **version-bump-release** in `CIPP-API`.

## Goal

Update version tracking files (host.json, version_latest.txt) to bump the project version, often after a set of changes or a release.

## Common Files

- `host.json`
- `version_latest.txt`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit host.json and version_latest.txt to reflect new version
- Commit both files together

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.