---
name: module-breakout-and-mass-script-addition
description: Workflow command scaffold for module-breakout-and-mass-script-addition in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /module-breakout-and-mass-script-addition

Use this workflow when working on **module-breakout-and-mass-script-addition** in `CIPP-API`.

## Goal

Splitting a large module into smaller modules and/or adding many new scripts or endpoints in bulk, often for performance or organizational improvements.

## Common Files

- `Modules/CIPPCore/*.psd1`
- `Modules/CIPPCore/*.psm1`
- `Modules/CIPPCore/Public/**/*.ps1`
- `Modules/CIPPActivityTriggers/**/*.ps1`
- `Modules/CIPPAlerts/**/*.ps1`
- `Modules/CIPPDB/**/*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update or create multiple module manifest files (*.psd1, *.psm1)
- Add or move many scripts under new or existing module directories (e.g., Modules/CIPPCore/Public, Modules/CIPPActivityTriggers/Public/Entrypoints/...)
- Update configuration files (e.g., Config/*.json, Config/*.csv)
- Update or add build files (e.g., build.psd1)
- Update CI/CD workflow files if needed (e.g., .github/workflows/dev_api.yml)

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.