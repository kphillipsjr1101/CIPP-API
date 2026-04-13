```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches the core development patterns, coding conventions, and common workflows used in the CIPP-API codebase. The repository is primarily written in TypeScript, with a focus on modular scripting, consistent file organization, and collaborative workflows for refactoring, documentation, versioning, and releases. This guide will help you quickly get up to speed with the project's standards and automation commands.

## Coding Conventions

- **File Naming:**  
  Use kebab-case for all file names.  
  _Example:_  
  ```
  user-management.ts
  alert-handler.ts
  ```

- **Import Style:**  
  Use relative imports for referencing modules within the project.  
  _Example:_  
  ```typescript
  import { getUser } from './user-management';
  ```

- **Export Style:**  
  Use named exports for all modules.  
  _Example:_  
  ```typescript
  // In user-management.ts
  export function getUser(id: string) { ... }
  export function createUser(data: User) { ... }
  ```

- **Commit Messages:**  
  - Use prefixes like `fix`, `chore` to categorize commits.
  - Keep commit messages concise (average ~58 characters).

## Workflows

### Bulk Alert Module Refactor
**Trigger:** When migrating or updating the implementation details for all alert modules (e.g., to use a new exception handler).  
**Command:** `/refactor-alerts`

1. Identify all alert scripts in `Modules/CIPPCore/Public/Alerts/`.
2. Update each script to use the new function or pattern (e.g., `Get-CippException`).
3. Commit all updated alert scripts together.

_Example:_  
```powershell
# Before
try {
    # alert logic
} catch {
    Write-Error $_
}

# After
try {
    # alert logic
} catch {
    Get-CippException $_
}
```

---

### Documentation Instructions Update
**Trigger:** When improving developer/AI agent instructions or updating documentation for new features or conventions.  
**Command:** `/update-docs`

1. Edit or add markdown files in `.github/instructions/` and `.github/agents/`.
2. Optionally update `.gitignore` or related meta files.
3. Commit all documentation changes together.

_Example:_  
- Update `.github/instructions/alert-guidelines.md` with new alert patterns.

---

### Version Bump Release
**Trigger:** When preparing a new release or after merging significant changes.  
**Command:** `/bump-version`

1. Edit `host.json` and `version_latest.txt` to reflect the new version.
2. Commit both files together.

_Example:_  
```json
// host.json
{
  "version": "1.2.3"
}
```
```text
# version_latest.txt
1.2.3
```

---

### Hotfix or Merge from Dev
**Trigger:** When synchronizing branches or deploying hotfixes that require multiple updates.  
**Command:** `/merge-dev`

1. Merge the `dev` branch into `hotfix` or `main`.
2. Resolve conflicts and aggregate all changed files.
3. Commit the merged changes.

_Example:_  
```bash
git checkout hotfix
git merge dev
# Resolve conflicts
git commit -am "Merge dev into hotfix"
```

---

## Testing Patterns

- **Test File Naming:**  
  Test files follow the pattern `*.test.*` (e.g., `user-management.test.ts`).

- **Framework:**  
  The specific testing framework is unknown, but tests are colocated with source files or in dedicated test directories.

- **Example Test File:**  
  ```typescript
  // user-management.test.ts
  import { getUser } from './user-management';

  test('getUser returns correct user', () => {
      expect(getUser('123')).toEqual({ id: '123', name: 'Alice' });
  });
  ```

## Commands

| Command           | Purpose                                                         |
|-------------------|-----------------------------------------------------------------|
| /refactor-alerts  | Refactor or migrate all alert modules to use a new shared pattern|
| /update-docs      | Update or add documentation and AI agent instructions           |
| /bump-version     | Bump project version in version tracking files                  |
| /merge-dev        | Merge changes from dev branch into hotfix or main               |
```
