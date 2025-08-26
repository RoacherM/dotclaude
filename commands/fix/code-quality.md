# Code Quality Fix

Use @python-quality to identify issues, then @python-implementer to implement fixes for code quality, performance, and testing coverage focusing on naming conventions, algorithm efficiency, test completeness, and error handling patterns.

## Step 1: Analysis (Confirm before proceeding)
- [ ] **@python-quality** - Analyze code quality, security, and architecture issues
- [ ] Review findings and confirm scope of fixes needed
- [ ] **Continue to implementation?** [y/N]

## Step 2: Security & Implementation (Confirm before proceeding) 
- [ ] **Implement security fixes** - Address identified vulnerabilities (uv run bandit for Python)
- [ ] **@python-implementer** - Implement fixes and refactoring
- [ ] Review changes for correctness
- [ ] **Continue to testing?** [y/N]

## Step 3: Validation & Commit
- [ ] **Run quality checks** - Python: `uv run ruff check && uv run mypy` / Node.js: `pnpm lint`
- [ ] **Run tests** - Python: `uv run pytest` / Node.js: `pnpm test`
- [ ] **Commit and push** - Create descriptive commit message
- [ ] **@python-lead** - Update project state with quality improvements and changes

For performance optimization changes, core algorithms, shared utilities, and test suite updates.