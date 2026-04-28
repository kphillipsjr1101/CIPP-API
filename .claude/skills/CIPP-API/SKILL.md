```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute effectively to the CIPP-API codebase, a C# project focused on providing modular API endpoints and standards enforcement scripts. You'll learn the project's coding conventions, how to add or update HTTP endpoints, enforce standards, fix core logic, manage documentation links, handle GDAP tenant functions, and reorganize configuration files. The guide also covers testing patterns and provides handy commands for common workflows.

## Coding Conventions

- **File Naming:**  
  Use **kebab-case** for all file names.  
  _Example:_  
  ```
  invoke-listgdap-tenants.ps1
  fix-core-logic.ps1
  ```

- **Import Style:**  
  Use **relative imports** within scripts.  
  _Example:_  
  ```powershell
  . "../Helpers/utilities.ps1"
  ```

- **Export Style:**  
  Use **named exports** for functions and modules.  
  _Example:_  
  ```powershell
  function Invoke-ListGDAPTenants {
      [CmdletBinding()]
      param(...)
      ...
  }
  Export-ModuleMember -Function Invoke-ListGDAPTenants
  ```

- **Commit Message Patterns:**  
  - Prefixes: `fix`, `chore`, `refactor`
  - Average length: ~41 characters  
  _Example:_  
  ```
  fix: correct null reference in tenant listing
  chore: update documentation links for standards
  refactor: move config files to Config/
  ```

## Workflows

### Add or Update HTTP Endpoint
**Trigger:** When you need to expose new functionality or fix a bug via an HTTP API endpoint.  
**Command:** `/new-endpoint`

1. Create or update a script in `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/`.
2. Optionally update related modules or core logic if needed.
3. Commit the new or changed endpoint file.

_Example:_  
```powershell
# Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/invoke-gettenant.ps1
function Invoke-GetTenant {
    [CmdletBinding()]
    param([string]$TenantId)
    ...
}
Export-ModuleMember -Function Invoke-GetTenant
```

---

### Add or Update Standard
**Trigger:** When you want to enforce a new standard or update compliance logic.  
**Command:** `/new-standard`

1. Create or update a script in `Modules/CIPPStandards/Public/Standards/`.
2. Optionally update related core logic or helper modules.
3. Commit the new or changed standard file.

_Example:_  
```powershell
# Modules/CIPPStandards/Public/Standards/Invoke-CIPPStandardPasswordPolicy.ps1
function Invoke-CIPPStandardPasswordPolicy {
    ...
}
Export-ModuleMember -Function Invoke-CIPPStandardPasswordPolicy
```

---

### Fix or Enhance Core Logic
**Trigger:** When you need to fix a bug or enhance a core function.  
**Command:** `/fix-core`

1. Update one or more scripts in `Modules/CIPPCore/Public/`.
2. Commit the changes with a `fix` or `refactor` message.

_Example:_  
```powershell
# Modules/CIPPCore/Public/fix-user-permissions.ps1
function Fix-UserPermissions {
    ...
}
Export-ModuleMember -Function Fix-UserPermissions
```

---

### Update or Fix Documentation Links
**Trigger:** When you find broken or outdated documentation links in code.  
**Command:** `/fix-docs`

1. Search for and update documentation links in code files.
2. Commit the changes with a message referencing documentation updates.

_Example:_  
```powershell
# Update outdated link in script comment
# Old: https://docs.oldsite.com/standard
# New: https://docs.newsite.com/standard
```

---

### Add or Update GDAP Tenant Functions
**Trigger:** When you want to support new GDAP operations or fix GDAP-related bugs.  
**Command:** `/new-gdap-function`

1. Create or update scripts in `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/Tenant/GDAP/`.
2. Commit the changes.

_Example:_  
```powershell
# Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/Tenant/GDAP/invoke-listgdaptenants.ps1
function Invoke-ListGDAPTenants {
    ...
}
Export-ModuleMember -Function Invoke-ListGDAPTenants
```

---

### Move or Rename Config and Root Files
**Trigger:** When you want to clean up the root directory or reorganize configuration files.  
**Command:** `/move-config`

1. Move or rename files in `Config/` or at the repo root.
2. Update references in scripts or workflows as needed.
3. Commit the changes.

_Example:_  
```
mv version_latest.txt Config/version_latest.txt
# Update any scripts referencing version_latest.txt
```

## Testing Patterns

- **Test File Pattern:**  
  Test files follow the `*.test.*` pattern.
- **Testing Framework:**  
  The specific framework is unknown, but tests are likely written as scripts with descriptive names.
- **Example:**  
  ```
  Modules/CIPPCore/Public/test-user-permissions.ps1
  ```

## Commands

| Command             | Purpose                                                        |
|---------------------|----------------------------------------------------------------|
| /new-endpoint       | Add or update an HTTP API entrypoint                          |
| /new-standard       | Add or update a standard enforcement script                   |
| /fix-core           | Fix or enhance core logic in core modules                     |
| /fix-docs           | Update or fix documentation links in code                     |
| /new-gdap-function  | Add or update GDAP-related HTTP functions for tenants         |
| /move-config        | Move, rename, or reorganize config and root-level files       |
```
