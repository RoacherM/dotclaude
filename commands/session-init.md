# Session Initialization (Python-focused)

Kick off each session with complete, actionable context and Python-first workflows.

## Step 1: Smart Bootstrap
- [ ] **@python-lead** — Load `.claude/` context if present; otherwise bootstrap
- [ ] If new project: Scan repository to generate `.claude/{project_context.md,session_state.json}`
- [ ] Validate `session_state.json.timestamp` freshness; if stale, refresh context

## Step 2: Environment Verification (Python)
- [ ] Check Python tooling: `uv --version` | optional: `ruff --version`, `pytest --version` | `mypy --version`
- [ ] Verify setup: dependencies installed; tests and lint run clean
- [ ] Git status: clean or intentional changes understood

## Step 3: Work Planning
- [ ] Read `session_state.json` → `next_steps`
- [ ] Prioritize 1-2 tasks; specify exact file paths to touch
- [ ] Start with the smallest viable change

## Python Project Bootstrap Details
- python-lead scanning hints: FastAPI (`FastAPI(`, `APIRouter`), agents (`anthropic`, `openai`, `langchain`), workflows (`prefect`, `celery`, `temporal`), data (`sqlalchemy`, `alembic`), quality (`pytest`, `ruff`, `mypy`, `bandit`).
- Output should create:
  - `.claude/project_context.md` — identity, architecture, components, operations
  - `.claude/session_state.json` — current tasks, active work, next steps

## Integration with Other Commands
- Use `/review/hierarchical` after major changes
- Use `/fix/code-quality` with architecture awareness
- Use `/gh/resolve-issues` when syncing with GitHub issues

Session initialization ensures Python development begins with clear context and zero cold start.