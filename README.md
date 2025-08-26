# Frad's `.claude` ![](https://img.shields.io/badge/A%20FRAD%20PRODUCT-WIP-yellow)

[![Twitter Follow](https://img.shields.io/twitter/follow/FradSer?style=social)](https://twitter.com/FradSer) [![Claude Code](https://img.shields.io/badge/Claude%20Code-Configuration-blue.svg)](https://docs.anthropic.com/en/docs/claude-code) [![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**English | [中文](README-zh.md)**

A Python-first multi-agent configuration for Claude Code. It unifies session bootstrap, project-wide context loading, and continuous progress tracking while focusing on Python development: FastAPI services, LLM agents, and workflow systems.

## Quick Start

New to the multi-agent system? Start here:

### 1. Sync Configuration
```bash
bash <(curl -fsSL https://raw.githubusercontent.com/FradSer/dotclaude/main/sync-to-github.sh)
```

### 2. Basic Agent Usage
In any Claude Code conversation:
- `@agent-python-orchestrator` - Session bootstrap, repository scan, `.claude/` docs management
- `@agent-project-state-manager` - Maintain 3-file state: `project_overview.md`, `changelog.md`, `current_focus.json`
- `@agent-python-reviewer` - Unified Python review (quality + security + architecture)
- `@agent-security-reviewer` - Python security audit
- `@agent-tech-lead-reviewer` - Architectural guidance

### 3. Best Practice Workflow in `claude`
Three-stage collaborative process for comprehensive code quality:

1. **Hierarchical Review** - Use `/review/hierarchical` for thorough multi-agent analysis
   - *Review and validate Claude's analysis before proceeding*

2. **Issue Creation** - Use `/gh/create-issues` to create GitHub issues for tracking improvements  
   - *Check and refine the issues Claude suggests before creating*

3. **Quality Implementation** - Use `/gh/resolve-issues` with intelligent branch detection, AI-generated names, and worktree management
   - *Automatically detects existing worktrees and offers continuation options*
   - *Uses AI to generate concise, descriptive branch names*
   - *Review Claude's code suggestions and adapt them to your context*

Each step requires engineer validation to ensure Claude's output aligns with project goals and constraints. See [Collaboration Philosophy](#collaboration-philosophy) for partnership principles.

### 4. Essential Commands
Open these templates as checklists in Claude Code:
- **Session init**: `commands/session-init.md` — Python-focused bootstrap and repo scan for new projects
- **Quick review**: `commands/review/quick.md` - Python-focused code review
- **Fix issues**: `commands/fix/code-quality.md` - Python code quality improvements  
- **Commit changes**: `commands/git/commit-and-push.md` - Git workflow with uv environment support

### 5. Next Steps
- Browse [Specialized Agents](#specialized-agents) for all available experts
- Explore [Command Templates](#command-templates) for structured workflows
- Set up [Multi-Agent Collaboration](#multi-agent-collaboration) pipelines

---

### Sync Details

<details>
<summary>What the sync script does (click to expand)</summary>

- Syncs `~/.claude/{agents,commands,CLAUDE.md}` with the same paths in this repo (two-way comparison)
- Automatically detects whether it runs inside this repo or clones into `/tmp/dotclaude-sync`
- Shows a diff for each item and lets you interactively choose: use local, use repo, or skip (supports color diff)
- At the end, you can choose to commit and push (generates a Conventional/Commitizen-style message or falls back to a built-in template)

**Prerequisites:**
- `git`, `curl`, `bash 3.2+` (macOS defaults are fine)
- Optional: `colordiff` (for colored diffs), `claude` CLI (for better commit message generation)

</details>

## Directory Structure

```text
dotclaude/
  - agents/
    - code-reviewer.md
    - code-simplifier.md
    - security-reviewer.md
    - tech-lead-reviewer.md
    - python-orchestrator.md
  - commands/
    - continue.md
    - fix/
      - code-quality.md
      - security.md
    - gh/
      - create-issues.md
      - resolve-issues.md
    - git/
      - commit-and-push.md
      - commit.md
      - push.md
      - release.md
    - refactor.md
    - review/
      - hierarchical.md
      - quick.md
  - CLAUDE.md
  - README.md
  - sync-to-github.sh
```

## Specialized Agents

Each agent provides domain-specific expertise for Python/LLM agent development:

| Agent | Purpose | Focus Areas |
|-------|---------|-------------|
| **agent-python-orchestrator** | Session bootstrap & docs | Repo scan, `.claude/` docs, Python-first context |
| **agent-code-reviewer** | Python code review | Correctness, error handling, maintainability, Python best practices |
| **agent-code-simplifier** | Python refactoring & optimization | Readability, complexity reduction, DRY principles, Pythonic patterns |
| **agent-security-reviewer** | Python security audit | Input validation, dependency scanning, secret management, Python-specific vulnerabilities |
| **agent-tech-lead-reviewer** | Python architectural guidance | System design, technical direction, risk assessment, scalability |
| **agent-project-state-manager** | Cross-session project tracking | Deep project analysis, comprehensive documentation, state continuity |

## Command Templates

Structured workflows for common development tasks:

### Review Workflows
- **`/review/quick`** - Two-stage rapid review process
- **`/review/hierarchical`** - Multi-layered parallel reviews with consolidated output

### Fix Operations
- **`/fix/code-quality`** - Python code quality improvements (naming, complexity, performance)
- **`/fix/security`** - Python security vulnerability identification and remediation

### Git Operations
- **`/git/commit.md`** - Structured commit workflow
- **`/git/commit-and-push`** - Combined commit and push operations
- **`/git/push`** - Push with validation checks
- **`/git/release`** - Git-flow release management

### GitHub Integration
- **`/gh/create-issues`** - Issue creation with templates
- **`/gh/resolve-issues`** - Smart issue resolution with branch detection, AI-generated names, and worktree continuation

### Development Utilities
- **`/session-init`** - Initialize sessions with complete project state awareness
- **`/continue`** - Resume interrupted work sessions
- **`/refactor`** - Systematic Python code refactoring checklist

## Usage Patterns

### Command-Driven Workflows
1. **Open command templates** - Use `commands/*.md` files as interactive checklists
2. **Follow structured processes** - Each template guides you through specific workflows
3. **Maintain consistency** - Standardized approaches across team members

### Multi-Agent Collaboration
```bash
# Example: Comprehensive review pipeline
@agent-python-reviewer → @agent-security-reviewer → @agent-tech-lead-reviewer
```

### Collaboration Philosophy

**Claude Code as Your Development Partner**

Treat Claude Code as an excellent colleague who collaborates asynchronously. This partnership provides specialized expertise and quality assurance while requiring your validation at each step to ensure alignment with project goals.

**GitHub as a Collaboration Platform**

GitHub with `gh` CLI creates seamless integration between Claude Code and project management. Issues, pull requests, and commits become structured documentation, transforming development into thoughtful technical writing where both human decisions and AI insights are captured and trackable.

### Sync Management
- Run Quick Sync periodically to maintain alignment with the repository
- Interactive diff resolution for local vs. remote changes
- Automatic commit message generation with Conventional style

---

## Development Guidelines (Python-first, minimal)

### Interactive Development
- Confirm in small steps; avoid one-shot changes
- Understand project structure before edits; search first when unsure
- Maintain cross-session context via `.claude/`

### Architecture Principles
- Prefer composition; follow SOLID; inject dependencies for testability
- Use repository/strategy patterns when appropriate

### Code Quality
- Descriptive names; avoid magic numbers; keep functions small
- Handle errors with meaningful messages; comment "why", not "what"

### Workflow
- TDD for core logic; update docs alongside code
- Atomic commits per logical change; Conventional style (≤50 chars)

### Cross-Session Tracking
- Keep `.claude/` in sync with reality:
  - `changelog.md`: after each meaningful change
  - `current_focus.json`: when WIP/next/known issues change
  - `project_overview.md`: only when architecture changes
- Start: `@python-orchestrator` loads/bootstraps context
- End: ensure `.claude/` consistent; list next 1–3 tasks with file paths

### Python Tooling
- Use `uv` for env and packages:
  - `uv venv` at project root
  - `uv add <package>` for deps
  - `uv run <command>` to run scripts/tests/tools
- Entry point at repo root; merge commits; avoid emojis and hardcoded secrets

### Requirements Protocol
- Don’t rush to code; follow: clarify → analyze → propose → discuss → decide
- Wait for approval before implementing

## FAQ

- Is the sync script non-interactive? It is interactive: choose local vs. repo per item and decide whether to commit and push at the end.
- No colored diffs? Optionally install `colordiff`; the script will auto-detect and use it.

## License

MIT License
