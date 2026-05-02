```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill provides a comprehensive guide to contributing to the CIPP-API codebase, a C# project focused on tenant management, compliance, alerting, and automation. It covers established coding conventions, file organization, and step-by-step workflows for adding new standards, alerts, HTTP endpoints, activity triggers, database cache writers, tests, and Microsoft Graph helpers. The guide also suggests commands to streamline common development tasks.

## Coding Conventions

- **File Naming:**  
  Use **kebab-case** for all file names.  
  _Example:_  
  ```
  get-cippalert-tenanthealth.ps1
  set-cippdbcache-users.ps1
  ```

- **Import Style:**  
  Use **relative imports** when referencing modules or scripts.  
  _Example:_  
  ```powershell
  . ../GraphHelper/get-cippgraphuser.ps1
  ```

- **Export Style:**  
  Use **named exports** for functions and scripts.  
  _Example:_  
  ```powershell
  function Get-CIPPAlert-TenantHealth { ... }
  Export-ModuleMember -Function Get-CIPPAlert-TenantHealth
  ```

- **Commit Messages:**  
  - Use prefixes like `feat` or `fix`.
  - Keep messages concise (~46 characters on average).
  _Example:_  
  ```
  feat: add new alert for mailbox forwarding detection
  fix: correct dbcache writer for device compliance
  ```

## Workflows

### Add or Update Standard
**Trigger:** When you want to add a new compliance standard or update an existing one for tenant management.  
**Command:** `/new-standard`

1. Create or modify a script in `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1`.
2. Optionally update documentation in `.github/instructions/standards.instructions.md`.
3. Commit the new or updated standard script.

_Example:_  
```powershell
function Invoke-CIPPStandard-PasswordPolicy { ... }
Export-ModuleMember -Function Invoke-CIPPStandard-PasswordPolicy
```

---

### Add or Update Alert
**Trigger:** When introducing a new alert type or enhancing alert logic for tenant health/security.  
**Command:** `/new-alert`

1. Create or modify a script in:
   - `Modules/CIPPCore/Public/Alerts/Get-CIPPAlert*.ps1`
   - or `Modules/CIPPAlerts/Public/Alerts/Get-CIPPAlert*.ps1`
2. Optionally update agent documentation in `.github/agents/CIPP-Alert-Agent.md`.
3. Commit the new or updated alert script.

_Example:_  
```powershell
function Get-CIPPAlert-MailboxForwarding { ... }
Export-ModuleMember -Function Get-CIPPAlert-MailboxForwarding
```

---

### Add or Update Activity Trigger
**Trigger:** When automating a new activity or updating an automation trigger.  
**Command:** `/new-activity-trigger`

1. Create or modify a script in:
   - `Modules/CIPPCore/Public/Entrypoints/Activity Triggers/*/Push-*.ps1`
   - or `Modules/CIPPActivityTriggers/Public/Entrypoints/Activity Triggers/*/Push-*.ps1`
2. Commit the new or updated trigger script.

_Example:_  
```powershell
function Push-UserLicenseAssignment { ... }
Export-ModuleMember -Function Push-UserLicenseAssignment
```

---

### Add or Update HTTP Endpoint
**Trigger:** When exposing a new API endpoint or updating an existing one for CIPP.  
**Command:** `/new-http-endpoint`

1. Create or modify a script in:
   - `Modules/CIPPCore/Public/Entrypoints/HTTP Functions/**/*.ps1`
   - or `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/*.ps1`
2. Optionally update related documentation or tests.
3. Commit the new or updated endpoint script.

_Example:_  
```powershell
function Invoke-List-UserDevices { ... }
Export-ModuleMember -Function Invoke-List-UserDevices
```

---

### Add or Update DB Cache Writer
**Trigger:** When caching new data from Graph or updating the caching logic for reporting.  
**Command:** `/new-dbcache-writer`

1. Create or modify a script in `Modules/CIPPDB/Public/DBCache/Set-CIPPDBCache*.ps1`.
2. Optionally update related HTTP endpoint in `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/Invoke-List*.ps1`.
3. Commit the new or updated DB cache writer.

_Example:_  
```powershell
function Set-CIPPDBCache-Users { ... }
Export-ModuleMember -Function Set-CIPPDBCache-Users
```

---

### Add or Update Test Script
**Trigger:** When adding a new test or improving test coverage for standards or features.  
**Command:** `/new-test`

1. Create or modify a script in:
   - `Modules/CIPPCore/Public/Tests/**/*.ps1`
   - or `Modules/CIPPTests/Public/Tests/**/*.ps1`
2. Optionally add or update corresponding `.md` documentation.
3. Commit the new or updated test script.

_Example:_  
```powershell
function Test-PasswordPolicyCompliance { ... }
Export-ModuleMember -Function Test-PasswordPolicyCompliance
```

---

### Add or Update Graph Helper or Request
**Trigger:** When supporting new Graph API calls or changing request logic.  
**Command:** `/new-graph-helper`

1. Create or modify a script in:
   - `Modules/CIPPCore/Public/GraphHelper/*.ps1`
   - or `Modules/CIPPCore/Public/GraphRequests/*.ps1`
2. Commit the new or updated helper/request.

_Example:_  
```powershell
function Get-CIPPGraphUser { ... }
Export-ModuleMember -Function Get-CIPPGraphUser
```

---

## Testing Patterns

- **Test Framework:** Unknown (PowerShell-based scripts detected).
- **File Pattern:** Test scripts are named with `.test.ts` (TypeScript) or as PowerShell scripts in `Modules/*/Public/Tests/**/*.ps1`.
- **Approach:**  
  - Tests are organized by feature or standard.
  - Each test is a script/function exported for use in test runners or manual execution.

_Example:_  
```powershell
function Test-UserLicenseAssignment { ... }
Export-ModuleMember -Function Test-UserLicenseAssignment
```

## Commands

| Command               | Purpose                                                      |
|-----------------------|--------------------------------------------------------------|
| /new-standard         | Add or update a compliance/configuration standard            |
| /new-alert            | Add or update an alert detection script                      |
| /new-activity-trigger | Add or update an activity trigger PowerShell script          |
| /new-http-endpoint    | Add or update an HTTP Function endpoint                      |
| /new-dbcache-writer   | Add or update a DB cache writer script                       |
| /new-test             | Add or update a test script                                  |
| /new-graph-helper     | Add or update a Microsoft Graph helper or request script     |
```
