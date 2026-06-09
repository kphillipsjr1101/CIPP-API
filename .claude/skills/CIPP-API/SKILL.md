```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and workflows used in the CIPP-API repository. The project is written in TypeScript (no framework detected) and follows a modular, maintainable approach with clear conventions for file naming, imports/exports, and commit messaging. You'll learn how to contribute fixes, enhancements, features, and version bumps in a way that matches the team's established practices.

---

## Coding Conventions

### File Naming

- **Style:** kebab-case
- **Example:**  
  ```
  user-management.ts
  http-functions.ts
  ```

### Import Style

- **Relative imports are used.**
- **Example:**
  ```typescript
  import { getUser } from './user-management';
  ```

### Export Style

- **Named exports are preferred.**
- **Example:**
  ```typescript
  export function getUser(id: string) { ... }
  export const API_VERSION = '1.0.0';
  ```

### Commit Messages

- **Prefixes:** `fix`, `chore`
- **Average Length:** ~43 characters
- **Example:**
  ```
  fix: correct casing in variable names
  chore: update version and timers config
  ```

---

## Workflows

### Fix or Enhance Existing Function

**Trigger:** When you need to fix a bug or enhance the logic of an existing PowerShell function.  
**Command:** `/fix-function`

1. Identify the function that requires a fix or enhancement.
2. Edit the corresponding `.ps1` file to update logic, variable casing, or permissions.
3. Commit the changes with a descriptive message.

**Example:**
```powershell
# Before
$UserName = $username

# After (standardized casing)
$UserName = $UserName
```
**Typical Files:**
- `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandardSPOVersionControl.ps1`
- `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/Email-Exchange/Tools/Invoke-ListMessageTrace.ps1`

---

### Feature or Bugfix Touching Multiple Related Files

**Trigger:** When adding a new feature or fixing a bug that requires coordinated changes across several related files (e.g., new SSO app, export job, or scheduled task).  
**Command:** `/feature-multifile`

1. Edit or create several related `.ps1` files within a module or feature area.
2. Update configuration files if needed (e.g., `Config/CIPPTimers.json`, `Config/version_latest.txt`).
3. Commit all related changes together.

**Example:**
```powershell
# Add new SSO app function
function New-CIPPSSOApp { ... }

# Update orchestrator
function Start-IntuneReportExportOrchestrator { ... }
```
**Typical Files:**
- `Modules/CIPPCore/Public/Authentication/Add-CIPPSSOAppSecret.ps1`
- `Modules/CIPPCore/Public/Authentication/New-CIPPSSOApp.ps1`
- `Modules/CIPPCore/Public/Authentication/Set-CIPPSSOStoredCredentials.ps1`
- `Config/CIPPTimers.json`
- `Config/version_latest.txt`

---

### Version and Config Bump

**Trigger:** When preparing a release, hotfix, or updating version/configuration metadata.  
**Command:** `/bump-version`

1. Update version numbers in `version_latest.txt` and/or `host.json`.
2. Update configuration files as needed (e.g., `Config/CIPPTimers.json`).
3. Commit all version/config changes together.

**Example:**
```diff
- 1.2.3
+ 1.2.4
```
**Typical Files:**
- `Config/version_latest.txt`
- `host.json`
- `Config/CIPPTimers.json`

---

## Testing Patterns

- **Testing Framework:** Unknown (not detected)
- **Test File Pattern:** `*.test.*`
- **Example:**
  ```
  user-management.test.ts
  http-functions.test.ts
  ```
- **Note:** Place test files alongside or near the code they test, following the same kebab-case naming convention.

---

## Commands

| Command            | Purpose                                                          |
|--------------------|------------------------------------------------------------------|
| /fix-function      | Fix or enhance an existing PowerShell function                   |
| /feature-multifile | Implement a feature or bugfix that touches multiple related files|
| /bump-version      | Update version numbers and configuration files                   |
```