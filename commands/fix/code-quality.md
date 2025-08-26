# Code Quality Fix

Use @python-reviewer to identify issues, then @code-simplifier to implement fixes for code quality, performance, and testing coverage focusing on naming conventions, algorithm efficiency, test completeness, and error handling patterns.

## Step 1: Analysis (Confirm before proceeding)
- [ ] **@python-reviewer** - Analyze code quality, security, and architecture issues
- [ ] Review findings and confirm scope of fixes needed
- [ ] **Continue to implementation?** [y/N]

## Step 2: Security & Implementation (Confirm before proceeding) 
- [ ] **Implement security fixes** - Address identified vulnerabilities (uv run bandit for Python)
- [ ] **@code-simplifier** - Implement fixes and refactoring
- [ ] Review changes for correctness
- [ ] **Continue to testing?** [y/N]

## Step 3: Validation & Commit
- [ ] **Run quality checks** - Python: `uv run ruff check && uv run mypy` / Node.js: `pnpm lint`
- [ ] **Run tests** - Python: `uv run pytest` / Node.js: `pnpm test`
- [ ] **Commit and push** - Create descriptive commit message
- [ ] **@project-state-manager** - Update project state with quality improvements and changes

For performance optimization changes, core algorithms, shared utilities, and test suite updates.