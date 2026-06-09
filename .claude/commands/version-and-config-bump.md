---
name: version-and-config-bump
description: Workflow command scaffold for version-and-config-bump in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /version-and-config-bump

Use this workflow when working on **version-and-config-bump** in `CIPP-API`.

## Goal

Updates version numbers and/or configuration files as part of a release or hotfix process.

## Common Files

- `Config/version_latest.txt`
- `host.json`
- `version_latest.txt`
- `Config/CIPPTimers.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update version numbers in version_latest.txt and/or host.json.
- Update configuration files as needed (e.g., Config/CIPPTimers.json).
- Commit all version/config changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.