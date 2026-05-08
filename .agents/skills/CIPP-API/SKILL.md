```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and common workflows for contributing to the CIPP-API codebase. CIPP-API is a TypeScript project (no framework detected) that orchestrates Microsoft 365/Intune/Teams automation via modular PowerShell scripts. You’ll learn how to add or update standards enforcement scripts, API endpoints, test suites, and core features, as well as how to follow the project’s code style and testing conventions.

## Coding Conventions

- **File Naming:**  
  Use `kebab-case` for all TypeScript and script files.
  - Example:  
    ```
    user-management.ts
    enforce-policy.ts
    ```

- **Import Style:**  
  Use **relative imports** for modules within the codebase.
  - Example:  
    ```typescript
    import { getUser } from './user-management';
    ```

- **Export Style:**  
  Use **named exports** for all modules.
  - Example:  
    ```typescript
    // user-management.ts
    export function getUser(id: string) { ... }
    export function setUser(user: User) { ... }
    ```

- **Commit Patterns:**  
  - Prefix commits with `fix:`, `feat:`, or `chore:`
  - Keep commit messages concise (average ~45 characters)
  - Example:  
    ```
    feat: add endpoint for device compliance
    fix: correct user role assignment bug
    chore: update dependencies
    ```

## Workflows

### Add or Update Standard Enforcement Script
**Trigger:** When you want to enforce a new standard or update an existing policy enforcement script.  
**Command:** `/new-standard`

1. Create or update a script in  
   `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1`
2. Optionally update related documentation or report/test files.

**Example:**
```powershell
# Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandardPasswordPolicy.ps1
function Invoke-CIPPStandardPasswordPolicy {
    # Implementation of password policy enforcement
}
```

---

### Add or Update API Endpoint
**Trigger:** When you want to expose a new API endpoint or modify an existing one.  
**Command:** `/new-endpoint`

1. Create or update a script in  
   `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/Invoke-*.ps1`
2. Optionally update related core logic or helper scripts.

**Example:**
```powershell
# Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/Users/Invoke-GetUser.ps1
function Invoke-GetUser {
    param($UserId)
    # Fetch and return user details
}
```

---

### Add or Update Test Suite
**Trigger:** When you want to add new tests or update existing ones for a standard or feature.  
**Command:** `/new-test-suite`

1. Create or update `.ps1` and `.md` files in  
   `Modules/CIPPTests/Public/Tests/**/`
2. Optionally update `report.json` in the same directory.

**Example:**
```powershell
# Modules/CIPPTests/Public/Tests/PasswordPolicy/PasswordPolicy.test.ps1
Describe "Password Policy Enforcement" {
    It "Should enforce minimum length" {
        # Test logic here
    }
}
```
```markdown
<!-- Modules/CIPPTests/Public/Tests/PasswordPolicy/README.md -->
# Password Policy Test Suite
This suite validates password policy enforcement...
```

---

### Feature Implementation with Core and API Integration
**Trigger:** When you want to add a new feature that requires both backend logic and an API surface.  
**Command:** `/new-feature`

1. Implement or update core logic in  
   `Modules/CIPPCore/Public/**/*.ps1`
2. Integrate or expose via  
   `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/*.ps1`
3. Optionally update related DB/cache/reporting scripts.

**Example:**
```powershell
# Modules/CIPPCore/Public/DeviceManagement/SetDeviceTag.ps1
function Set-DeviceTag { ... }

# Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/Devices/Invoke-SetDeviceTag.ps1
function Invoke-SetDeviceTag {
    param($DeviceId, $Tag)
    Set-DeviceTag -DeviceId $DeviceId -Tag $Tag
}
```

---

### Queue or Scheduler Feature Update
**Trigger:** When you want to improve, fix, or extend queue/scheduler features.  
**Command:** `/update-queue`

1. Update or add scripts in  
   `Modules/CIPPCore/Public/CippQueue/*.ps1`
2. Update orchestrator or scheduler scripts in  
   `Modules/CIPPCore/Public/Entrypoints/Orchestrator Functions/*.ps1`  
   or  
   `Modules/CIPPCore/Public/Tools/*.ps1`
3. Optionally update related triggers or helper scripts.

**Example:**
```powershell
# Modules/CIPPCore/Public/CippQueue/EnqueueTask.ps1
function Enqueue-Task { ... }

# Modules/CIPPCore/Public/Entrypoints/Orchestrator Functions/Invoke-QueueOrchestrator.ps1
function Invoke-QueueOrchestrator { ... }
```

## Testing Patterns

- **Test Framework:**  
  Unknown (likely custom or PowerShell-based)
- **Test File Pattern:**  
  All test files are named with the `.test.ts` extension for TypeScript, or `.ps1` for PowerShell test scripts.
- **Location:**  
  Tests are organized under  
  `Modules/CIPPTests/Public/Tests/**/`
- **Documentation:**  
  Each test suite may include a Markdown file (`.md`) and a `report.json` for results or metadata.

**Example:**
```typescript
// user-management.test.ts
import { getUser } from './user-management';

describe('getUser', () => {
  it('returns user by ID', () => {
    expect(getUser('123')).toEqual({ id: '123', ... });
  });
});
```

## Commands

| Command         | Purpose                                                      |
|-----------------|-------------------------------------------------------------|
| /new-standard   | Add or update a standard enforcement script                  |
| /new-endpoint   | Add or update an API endpoint                               |
| /new-test-suite | Add or update a suite of tests for standards or features     |
| /new-feature    | Implement a new feature with core and API integration        |
| /update-queue   | Update or extend queueing and scheduler-related functionality|
```
