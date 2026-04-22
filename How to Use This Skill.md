**Skill Created: write-jest-unit-test**

**Location:** .cursor/skills/write-jest-unit-test/

**Files Created:**

1. SKILL.md - Main skill instructions containing:
    - Step-by-step workflow for analyzing branch changes
    - Test patterns for components, services, pipes, directives
    - Mocking guidelines (HTTP, Router, Store, Observables)
    - Test coverage requirements
    - Commands to run tests
2. project-examples.md - Reference file with real examples from your codebase

**How to Use This Skill**

**Method 1: Natural Language Trigger**

**Simply ask Cursor something like:**

- "Write unit tests for my branch changes"
- "Generate specs for the files I modified"
- "Create tests for my bug fix"
- "Add unit tests for my new feature"

**Method 2: Explicit Invocation**

**You can also say:**

- "Use the write-jest-unit-test skill"
- "Run the unit test generator on my changes"

**What the Agent Will Do:**

1. Analyze your branch - Identifies all changed .ts files (excluding existing specs)
2. Categorize files - Determines if they're components, services, pipes, etc.
3. Read source code - Understands methods, dependencies, inputs/outputs
4. Generate tests - Creates or updates .spec.ts files following project patterns
5. Verify - Provides commands to run the new tests

**Example Workflow:**

You: "Write unit tests for my current branch changes"

Agent:

1. Runs: git diff --name-only $(git merge-base HEAD origin/develop)..HEAD

2. Finds: src/app/features/user/user.component.ts (modified)

3. Reads the component, identifies public methods

4. Creates/updates: user.component.spec.ts

5. Returns: "Created tests for UserComponent covering 3 methods. Run with: npx nx test demo-app --test-file=src/app/features/user/user.component.spec.ts"

**Key Features**

| Feature | Description |
| --- | --- |
| Auto-detection | Automatically finds changed files from your branch |
| Pattern matching | Uses your project's existing test patterns |
| Smart mocking | Creates proper mocks for Angular dependencies |
| Coverage focus | Generates happy path + edge case + error tests |
| Nx compatible | Uses npx nx test commands for this monorepo |
