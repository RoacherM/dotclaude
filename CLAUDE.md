# Development Guidelines (Python-first, minimal)

## Interactive Development
- Confirm in small steps; avoid one-shot changes
- Understand project structure before edits; search first when unsure
- Maintain cross-session context via `.claude/`

## Architecture Principles
- Prefer composition; follow SOLID; inject dependencies for testability
- Use repository/strategy patterns when appropriate

## Code Quality
- Descriptive names; avoid magic numbers; keep functions small
- Handle errors with meaningful messages; comment "why", not "what"

## Workflow
- TDD for core logic; update docs alongside code
- Atomic commits per logical change

## Cross-Session Tracking
- Keep `.claude/` in sync with reality
- Update:
  - `changelog.md`: after each meaningful change
  - `current_focus.json`: when WIP/next/known issues change
  - `project_overview.md`: only when architecture changes
- Start: `@python-lead` loads/bootstraps context
- End: ensure `.claude/` consistent; list next 1–3 tasks with file paths

## Python Tooling Preferences
- Use `uv` for env and packages
  - `uv venv` at project root
  - `uv add <package>` for deps
  - `uv run <command>` to run scripts/tests/tools
- Entry point at repo root; lowercase commit titles (≤50 chars)
- Use merge commits; avoid emojis and hardcoded secrets

## Requirements Protocol
- Don’t rush to code; follow: clarify → analyze → propose → discuss → decide
- Wait for approval before implementing

## Quality Gates
- Python: `uv run ruff check && uv run mypy && uv run pytest && uv run bandit -r .`