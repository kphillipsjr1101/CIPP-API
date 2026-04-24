```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill provides a comprehensive guide to the development patterns, coding conventions, and common workflows used in the **CIPP-API** repository. The codebase is primarily written in C#, but also includes extensive PowerShell scripting for module management, API endpoint handling, configuration, and automation. The repository emphasizes modularity, batch updates, and maintainable code organization, with frequent workflows for module refactoring, API endpoint management, configuration updates, and dependency upgrades.

## Coding Conventions

- **File Naming:**  
  Use **kebab-case** for file names.  
  _Example:_  
  ```
  invoke-cippstandard-update.ps1
  cipp-core-module.psd1
  ```

- **Import Style:**  
  Use **relative imports** when referencing scripts or modules.  
  _Example:_  
  ```powershell
  . "$PSScriptRoot\..\Helpers\common-helpers.ps1"
  ```

- **Export Style:**  
  Use **named exports** for functions and modules.  
  _Example:_  
  ```powershell
  Export-ModuleMember -Function Invoke-CIPPStandardUpdate
  ```

- **Commit Messages:**  
  - Prefix with `fix:` or `feat:` as appropriate.
  - Keep messages concise (~45 characters).
  _Example:_  
  ```
  feat: add new endpoint for user sync
  fix: correct permissions in config
  ```

## Workflows

### Module Breakout and Mass Script Addition
**Trigger:** When refactoring core modules for performance, maintainability, or feature expansion.  
**Command:** `/module-breakout`

1. Update or create multiple module manifest files (`*.psd1`, `*.psm1`).
2. Add or move scripts under new or existing module directories:
   - `Modules/CIPPCore/Public/`
   - `Modules/CIPPActivityTriggers/Public/Entrypoints/`
   - etc.
3. Update configuration files as needed (`Config/*.json`, `Config/*.csv`).
4. Update or add build files (e.g., `build.psd1`).
5. Update CI/CD workflow files if required (e.g., `.github/workflows/dev_api.yml`).

_Example:_  
```powershell
# Move script to new module
Move-Item Modules/CIPPCore/Public/Invoke-Old.ps1 Modules/CIPPActivityTriggers/Public/Entrypoints/Invoke-New.ps1
# Update module manifest
Update-ModuleManifest -Path Modules/CIPPActivityTriggers/CIPPActivityTriggers.psd1 -FunctionsToExport 'Invoke-New'
```

---

### Standard Script Batch Update
**Trigger:** When updating documentation, comments, or required metadata for all standards scripts.  
**Command:** `/update-standards-comments`

1. Edit files under `Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandard*.ps1`.
2. Optionally, use or update a helper script for batch updates (e.g., `Tools/Update-StandardsComments.ps1`).

_Example:_  
```powershell
# Batch update comment headers in all standards scripts
.\Tools\Update-StandardsComments.ps1
```

---

### API Endpoint Addition or Migration
**Trigger:** When adding a new HTTP API endpoint or consolidating endpoints under a generic handler.  
**Command:** `/new-api-endpoint`

1. Create or update script(s) under `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/[...]/Invoke-*.ps1`.
2. Optionally update related index or handler scripts.
3. Add or update test scripts if applicable.

_Example:_  
```powershell
# New endpoint script
function Invoke-UserSync {
    [CmdletBinding()]
    param(...)
    # Implementation
}
Export-ModuleMember -Function Invoke-UserSync
```

---

### Config or Permissions Batch Update
**Trigger:** When permissions, feature flags, or config tables need to be updated for new features or refactors.  
**Command:** `/update-config`

1. Edit multiple files in `Config/` (e.g., `*.json`, `*.csv`).
2. Optionally update related module scripts to consume new config.
3. Commit alongside module or endpoint changes.

_Example:_  
```json
// Config/permissions.json
{
  "NewFeature": true,
  "UserSync": ["admin", "superuser"]
}
```

---

### DLL or Binary Dependency Upgrade
**Trigger:** When upgrading a binary dependency or moving it to a shared location.  
**Command:** `/upgrade-dll`

1. Add, update, or delete DLL files in module lib directories (e.g., `Modules/CIPPCore/lib/*.dll`).
2. Optionally update references in scripts or module manifests.

_Example:_  
```powershell
# Reference new DLL in module manifest
Add-Type -Path "$PSScriptRoot\lib\NewDependency.dll"
```

---

## Testing Patterns

- **Framework:** Unknown (not detected in analysis).
- **File Pattern:** Test files follow the `*.test.ts` naming convention.
- **Typical Usage:**  
  - Place test files alongside or near the scripts they test.
  - Use descriptive test names and group related tests together.

_Example:_  
```typescript
// user-sync.test.ts
describe('UserSync API', () => {
  it('should return 200 on valid request', () => {
    // test implementation
  });
});
```

## Commands

| Command                   | Purpose                                                      |
|---------------------------|--------------------------------------------------------------|
| /module-breakout          | Refactor modules, add/move scripts, update manifests/configs |
| /update-standards-comments| Batch update comments/metadata in standards scripts          |
| /new-api-endpoint         | Add or migrate HTTP API endpoints                            |
| /update-config            | Batch update config or permissions files                     |
| /upgrade-dll              | Upgrade or centralize DLL/binary dependencies                |
```
