---
name: add-or-update-alert
description: Workflow command scaffold for add-or-update-alert in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-alert

Use this workflow when working on **add-or-update-alert** in `CIPP-API`.

## Goal

Adds a new alert detection script or updates an existing alert for tenant monitoring.

## Common Files

- `Modules/CIPPCore/Public/Alerts/Get-CIPPAlert*.ps1`
- `Modules/CIPPAlerts/Public/Alerts/Get-CIPPAlert*.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create or modify a script in Modules/CIPPCore/Public/Alerts/Get-CIPPAlert*.ps1 or Modules/CIPPAlerts/Public/Alerts/Get-CIPPAlert*.ps1
- Optionally update agent documentation in .github/agents/CIPP-Alert-Agent.md
- Commit the new or updated alert script

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.