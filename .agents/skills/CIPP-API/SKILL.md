```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and common workflows used in the CIPP-API repository. The codebase is written in TypeScript (no framework detected) and is organized for clarity and maintainability. You'll learn how to follow the project's file naming, import/export styles, commit practices, and how to contribute using established workflows for tests, DB cache types, policies, and releases.

## Coding Conventions

- **File Naming:**  
  Use kebab-case for all file names.  
  _Example:_  
  ```
  user-service.ts
  db-cache-handler.ts
  ```

- **Import Style:**  
  Use relative imports for modules.  
  _Example:_  
  ```typescript
  import { getUser } from './user-service';
  ```

- **Export Style:**  
  Use named exports.  
  _Example:_  
  ```typescript
  export function getUser(id: string) { ... }
  export const USER_ROLE = 'admin';
  ```

- **Commit Messages:**  
  - Freeform style, often prefixed with `fix` or `chore`.
  - Keep messages concise (average ~30 characters).
  - _Examples:_  
    ```
    fix: correct user role assignment
    chore: update dependencies
    ```

## Workflows

### ORCA Test Fix or Addition
**Trigger:** When you need to fix a bug or add coverage for an ORCA scenario  
**Command:** `/fix-orca-test`

1. Identify the ORCA test that needs a fix or addition.
2. Edit or create the corresponding test file in:  
   `Modules/CIPPTests/Public/Tests/ORCA/Identity/`
3. Commit your changes with a message referencing the ORCA test number.

_Example:_  
```
fix: update ORCA test 123 for new scenario
```

### DB Cache Type and Handler Update
**Trigger:** When you want to add or modify a DB cache type and its processing logic  
**Command:** `/update-db-cache-type`

1. Edit `Config/CIPPDBCacheTypes.json` to add or update a cache type.
2. Edit or create the handler script in:  
   `Modules/CIPPDB/Public/DBCache/Set-CIPPDBCache*.ps1`
3. Optionally, update:  
   `Modules/CIPPCore/Public/Invoke-CIPPDBCacheCollection.ps1`
4. Optionally, add or update a related ORCA test in:  
   `Modules/CIPPTests/Public/Tests/ORCA/Identity/`

_Example handler addition:_  
```json
// Config/CIPPDBCacheTypes.json
{
  "NewCacheType": {
    "description": "Handles new cache logic"
  }
}
```

### Standard Policy and Test Update
**Trigger:** When you want to change a standard policy and ensure it is tested  
**Command:** `/update-standard-policy`

1. Edit the policy script in:  
   `Modules/CIPPStandards/Public/Standards/`
2. Edit or update the corresponding ORCA test in:  
   `Modules/CIPPTests/Public/Tests/ORCA/Identity/`

_Example:_  
```
fix: update password policy and test
```

### Version Bump Release
**Trigger:** When you want to release a new version  
**Command:** `/bump-version`

1. Edit `host.json` and/or `version_latest.txt` to reflect the new version.
2. Commit with a version bump message.

_Example:_  
```
chore: bump version to 2.3.0
```

## Testing Patterns

- **Testing Framework:** Unknown (TypeScript tests detected)
- **Test File Pattern:**  
  All test files are named with the `.test.ts` suffix.
  _Example:_  
  ```
  user-service.test.ts
  db-cache-handler.test.ts
  ```

- **Test Example:**  
  ```typescript
  import { getUser } from './user-service';

  describe('getUser', () => {
    it('returns user by ID', () => {
      expect(getUser('123')).toEqual({ id: '123', name: 'Alice' });
    });
  });
  ```

## Commands

| Command                | Purpose                                                |
|------------------------|--------------------------------------------------------|
| /fix-orca-test         | Fix or add an ORCA test case                           |
| /update-db-cache-type  | Add or update a DB cache type and its handler          |
| /update-standard-policy| Update a standard policy and its corresponding test    |
| /bump-version          | Bump the version number for a new release              |
```