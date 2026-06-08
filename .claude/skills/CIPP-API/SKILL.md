```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute to the CIPP-API codebase, a TypeScript project focused on Microsoft 365 compliance, security standards, and automation. You'll learn the project's coding conventions, how to add or update standards, API endpoints, cache writers, reporting functions, custom scripts, license checks, and advanced matching helpers. Each workflow is documented with step-by-step instructions and command suggestions for efficient collaboration.

## Coding Conventions

- **File Naming:** Use `kebab-case` for all file names.
  - Example: `get-user-data.ts`
- **Import Style:** Use relative imports.
  - Example:
    ```typescript
    import { fetchData } from '../utils/fetch-data';
    ```
- **Export Style:** Use named exports.
  - Example:
    ```typescript
    export function getUserData() { ... }
    ```
- **Commit Messages:**
  - Prefix with `feat` for new features, `fix` for bug fixes.
  - Example: `feat: add Intune compliance standard`
  - Keep messages concise (~45 characters).

## Workflows

### Add or Update Standard
**Trigger:** When a new Microsoft 365 standard needs to be enforced or an existing standard updated  
**Command:** `/new-standard`

1. Create or update a file in `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1`.
2. If adding a new standard, add an entry to `Config/standards.json`.
3. If new, update documentation in `.github/instructions/standards.instructions.md`.
4. Optionally, update cache or reporting functions in `Modules/CIPPDB/Public/DBCache/Set-CIPPDBCache*.ps1`.
5. Optionally, add or update tests in `Modules/CIPPTests/Public/Tests/`.

**Example:**
```powershell
# Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandardTeams.ps1
function Invoke-CIPPStandardTeams { ... }
```

---

### Add or Update API Endpoint
**Trigger:** When a new frontend feature needs a backend endpoint or an existing endpoint is enhanced  
**Command:** `/new-endpoint`

1. Create or update a function in `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/Invoke-*.ps1`.
2. If new, add to the relevant index/module file.
3. Optionally, update related cache/DB functions in `Modules/CIPPDB/Public/DBCache/Set-CIPPDBCache*.ps1`.
4. Optionally, update related reporting/logic in `Modules/CIPPCore/Public/Get-*.ps1`.

**Example:**
```powershell
# Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/Teams/Invoke-GetTeamsReport.ps1
function Invoke-GetTeamsReport { ... }
```

---

### Add or Update Cache Writer
**Trigger:** When a new data type needs to be cached for reporting or standards, or cache logic needs improvement  
**Command:** `/new-cache`

1. Create or update a function in `Modules/CIPPDB/Public/DBCache/Set-CIPPDBCache*.ps1`.
2. Optionally, update the corresponding HTTP endpoint to call the cache writer.
3. Optionally, update reporting functions in `Modules/CIPPCore/Public/Get-*.ps1`.

---

### Add or Update Reporting Function
**Trigger:** When a new report is needed or an existing report needs enhancement  
**Command:** `/new-report`

1. Create or update a function in `Modules/CIPPCore/Public/Get-*.ps1`.
2. Optionally, update or add corresponding HTTP endpoint in `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/Invoke-*.ps1`.
3. Optionally, update or add cache writer in `Modules/CIPPDB/Public/DBCache/Set-CIPPDBCache*.ps1`.

---

### Add or Update Custom Script or Test
**Trigger:** When a new custom health check, compliance test, or alert logic is needed  
**Command:** `/new-custom-test`

1. Create or update a script in `Modules/CIPPTests/Public/Tests/Custom/Invoke-CippTestCustomScripts.ps1` or similar location.
2. Update or add HTTP endpoint in `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/Tools/Custom-Scripts/Invoke-*.ps1`.
3. Optionally, update scheduler or reporting logic.

---

### Add or Update License or Capability Check
**Trigger:** When a standard or feature requires a new license check or an existing check needs to be updated  
**Command:** `/update-license-check`

1. Update or add logic in `Modules/CIPPCore/Public/Functions/Test-CIPPStandardLicense.ps1`.
2. Update affected standard(s) in `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1` to use the new/updated check.
3. Optionally, update documentation or comment blocks.

---

### Add or Update Fuzzy Matching or Advanced Matching Helper
**Trigger:** When more robust or flexible matching is needed for policy/template deployment  
**Command:** `/new-matching-helper`

1. Add or update helper in `Modules/CIPPCore/Public/Tools/Find-CIPPFuzzyPolicyMatch.ps1` or similar.
2. Add or update test in `Tests/Private/Find-CIPPFuzzyPolicyMatch.Tests.ps1`.
3. Integrate helper into relevant standard or policy deployment logic (e.g., `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandardIntuneTemplate.ps1`).

**Example:**
```powershell
# Modules/CIPPCore/Public/Tools/Find-CIPPFuzzyPolicyMatch.ps1
function Find-CIPPFuzzyPolicyMatch { ... }
```

## Testing Patterns

- **Test Files:** Use the pattern `*.test.ts` for TypeScript tests.
- **Testing Framework:** Not explicitly detected; use standard TypeScript/Jest/Mocha patterns.
- **Location:** Place tests in a `tests` directory or alongside the code under test.
- **Example:**
  ```typescript
  // get-user-data.test.ts
  import { getUserData } from './get-user-data';

  test('should fetch user data', () => {
    expect(getUserData()).toBeDefined();
  });
  ```

## Commands

| Command               | Purpose                                                        |
|-----------------------|----------------------------------------------------------------|
| /new-standard         | Add or update a compliance/security standard                   |
| /new-endpoint         | Add or update an HTTP API endpoint                            |
| /new-cache            | Add or update a cache writer function                         |
| /new-report           | Add or update a reporting function                            |
| /new-custom-test      | Add or update a custom script or test                         |
| /update-license-check | Add or update license/capability checks                       |
| /new-matching-helper  | Add or update fuzzy/advanced matching helpers                 |
```
