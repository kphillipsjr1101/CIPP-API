---
name: feature-or-bugfix-touching-multiple-related-files
description: Workflow command scaffold for feature-or-bugfix-touching-multiple-related-files in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-or-bugfix-touching-multiple-related-files

Use this workflow when working on **feature-or-bugfix-touching-multiple-related-files** in `CIPP-API`.

## Goal

Implements a new feature or bugfix that requires coordinated changes across several related files, typically within a module or feature area.

## Common Files

- `Modules/CIPPCore/Public/Authentication/Add-CIPPSSOAppSecret.ps1`
- `Modules/CIPPCore/Public/Authentication/New-CIPPSSOApp.ps1`
- `Modules/CIPPCore/Public/Authentication/Set-CIPPSSOStoredCredentials.ps1`
- `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/CIPP/Setup/Invoke-ExecSSOSetup.ps1`
- `Modules/CIPPActivityTriggers/Public/Entrypoints/Activity Triggers/Push-IntuneReportExportSubmit.ps1`
- `Modules/CIPPCore/Public/Entrypoints/Orchestrator Functions/Start-IntuneReportExportOrchestrator.ps1`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or create several related .ps1 files within a module or feature area.
- Update configuration files if needed (e.g., Config/CIPPTimers.json, Config/version_latest.txt).
- Commit all related changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.