```markdown
# gstack Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `gstack` TypeScript codebase. You'll learn about file organization, import/export styles, commit message conventions, and how to write and run tests using Jest. These patterns ensure code consistency, maintainability, and effective collaboration.

## Coding Conventions

### File Naming
- Use **kebab-case** for all file names.
  - Example:  
    ```
    my-feature-file.ts
    another-module.test.ts
    ```

### Import Style
- Use **relative imports** for internal modules.
  - Example:
    ```typescript
    import { myFunction } from './utils';
    ```

### Export Style
- Use **named exports** (avoid default exports).
  - Example:
    ```typescript
    // utils.ts
    export function myFunction() { ... }
    export const MY_CONSTANT = 42;
    ```

    ```typescript
    // usage
    import { myFunction, MY_CONSTANT } from './utils';
    ```

### Commit Messages
- Use **conventional commit** style.
- Prefix with type, e.g., `fix:`.
- Example:
  ```
  fix: correct calculation in stack handler
  ```

## Workflows

### Code Fix Workflow
**Trigger:** When you need to fix a bug or correct existing functionality  
**Command:** `/fix`

1. Identify the bug or issue in the codebase.
2. Create a new branch for your fix.
3. Make code changes following the coding conventions.
4. Write or update tests as needed.
5. Commit your changes using a conventional commit message (e.g., `fix: ...`).
6. Push your branch and open a pull request.

## Testing Patterns

- **Framework:** Jest
- **Test file pattern:** Files end with `.test.ts`
  - Example: `stack-utils.test.ts`
- **Test Example:**
  ```typescript
  // stack-utils.test.ts
  import { myFunction } from './stack-utils';

  describe('myFunction', () => {
    it('should return expected value', () => {
      expect(myFunction()).toBe('expected');
    });
  });
  ```
- Run tests using Jest:
  ```
  npx jest
  ```

## Commands
| Command | Purpose |
|---------|---------|
| /fix    | Start the code fix workflow (bugfixes, corrections) |
```
