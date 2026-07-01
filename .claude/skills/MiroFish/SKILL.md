```markdown
# MiroFish Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the MiroFish TypeScript codebase. It covers file organization, code style, commit conventions, and testing patterns, providing practical examples and step-by-step workflows to help you contribute effectively.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `miroFishEngine.ts`, `userSettings.ts`

### Import Style
- Use **relative imports** for all module references.
  - Example:
    ```typescript
    import { calculateScore } from './scoreUtils';
    ```

### Export Style
- Use **named exports** rather than default exports.
  - Example:
    ```typescript
    // In scoreUtils.ts
    export function calculateScore() { ... }
    ```

### Commit Messages
- Follow **conventional commit** style.
- Use the `chore` prefix for routine tasks.
  - Example:
    ```
    chore: update dependencies for security patches
    ```

## Workflows

### Creating a New Module
**Trigger:** When adding new functionality
**Command:** `/new-module`

1. Create a new file using camelCase naming (e.g., `fishLogic.ts`).
2. Write your code using named exports.
3. Import dependencies using relative paths.
4. Add or update tests in a corresponding `*.test.ts` file.
5. Commit with a conventional message (e.g., `chore: add fishLogic module`).

### Updating Dependencies
**Trigger:** When dependencies need to be updated
**Command:** `/update-deps`

1. Update the relevant dependency files (e.g., `package.json`).
2. Test the project to ensure compatibility.
3. Commit with a message like `chore: update dependencies`.

### Writing and Running Tests
**Trigger:** When adding or modifying code
**Command:** `/run-tests`

1. Create or update test files matching the `*.test.*` pattern (e.g., `fishLogic.test.ts`).
2. Use the project's test runner (framework unknown; refer to project docs or `package.json` scripts).
3. Run the tests and ensure all pass before committing.

## Testing Patterns

- Test files are named with the `*.test.*` pattern, such as `fishLogic.test.ts`.
- Each test file should correspond to a module and cover its exported functions.
- Testing framework is not specified; check project scripts or documentation for details.

  Example test file:
  ```typescript
  import { calculateScore } from './scoreUtils';

  describe('calculateScore', () => {
    it('returns 0 for empty input', () => {
      expect(calculateScore([])).toBe(0);
    });
  });
  ```

## Commands
| Command        | Purpose                                    |
|----------------|--------------------------------------------|
| /new-module    | Scaffold and add a new module              |
| /update-deps   | Update project dependencies                |
| /run-tests     | Run all test suites                        |
```