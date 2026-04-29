```markdown
# CIPP-API Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns and workflows used in the CIPP-API TypeScript codebase. It covers file organization, code style conventions, commit habits, and the main feature development and release workflow. By following these guidelines, contributors can maintain consistency and efficiency across the project.

## Coding Conventions

### File Naming
- **Style:** kebab-case
- **Example:**  
  ```
  user-management.ts
  http-functions.ts
  ```

### Import Style
- **Style:** Relative imports
- **Example:**
  ```typescript
  import { getUser } from './user-management';
  import { handleRequest } from '../utils/http-functions';
  ```

### Export Style
- **Style:** Named exports
- **Example:**
  ```typescript
  // In user-management.ts
  export function getUser(id: string) { ... }
  export function createUser(data: UserData) { ... }
  ```

### Commit Patterns
- **Type:** Freeform messages, no strict prefix
- **Average Length:** ~37 characters
- **Example:**
  ```
  Add endpoint for user authentication
  Fix bug in HTTP request handler
  Update config for new scheduler
  ```

## Workflows

### Feature Development and Release Merge
**Trigger:** When multiple related changes (features, bugfixes, tweaks) are developed and then merged into a release branch.  
**Command:** `/merge-release`

**Step-by-step:**
1. **Develop or tweak features**  
   Work on individual module files, such as:
   - `Modules/CIPPCore/Public/Functions/*.ps1`
   - `Modules/CIPPCore/Public/Authentication/*.ps1`
   - `Modules/CIPPHTTP/Public/Entrypoints/HTTP Functions/**/*.ps1`
   - `Modules/CippExtensions/Public/NinjaOne/*.ps1`
2. **Update configuration or scheduler files as needed**  
   For example:  
   - `Config/CIPPTimers.json`
3. **Update version tracking**  
   - Edit `version_latest.txt` to reflect the new version.
4. **Merge all related changes into a single commit**  
   - Often use a message like `Dev to hf`.
5. **Push to the release branch**  
   - Ensures all updates are included in the release.

**Example Commit Message:**
```
Dev to hf: merge new features and bugfixes
```

## Testing Patterns

- **Framework:** Not explicitly detected; testing framework is unknown.
- **File Pattern:** Test files follow the `*.test.*` naming convention.
- **Example:**
  ```
  user-management.test.ts
  http-functions.test.ts
  ```
- **Typical Test Structure:**  
  (Assuming standard TypeScript testing)
  ```typescript
  import { getUser } from './user-management';

  describe('getUser', () => {
    it('should return user data for valid id', () => {
      // test implementation
    });
  });
  ```

## Commands

| Command         | Purpose                                           |
|-----------------|--------------------------------------------------|
| /merge-release  | Merge related feature and bugfix changes for release |
```
