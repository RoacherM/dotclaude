# Project Context

## Identity
- **Name**: dotclaude - Multi-Agent Configuration for Claude Code
- **Type**: Configuration Repository / Documentation System  
- **Purpose**: Python-first multi-agent system for Claude Code development workflows
- **Tech Stack**: Markdown documentation, Bash scripting, Git workflows

## Architecture
- **Directory Structure**:
  - `agents/` - 3 specialized agents (python-lead, python-implementer, python-quality)
  - `commands/` - Structured workflow templates for common development tasks
  - `CLAUDE.md` - Project-wide development guidelines and tooling preferences
  - `sync-to-github.sh` - Interactive sync script for distribution
- **Design Patterns**: Template-driven workflows, 3-stage development pipeline (Plan → Implement → Quality)
- **Entry Points**: `sync-to-github.sh` for setup, `/session-init` command for bootstrapping

## Components
- **3-Agent System**:
  - `python-lead` - Session bootstrap, architecture design, technical planning
  - `python-implementer` - Code implementation, refactoring, performance optimization
  - `python-quality` - Comprehensive review (quality + security + testing)
- **Command Templates**: Structured workflows (review/, fix/, gh/, git/)
- **Context System**: 2-file state management (project_context.md + session_state.json)

## Operations
- **Setup**: Run `bash <(curl -fsSL https://raw.githubusercontent.com/RoacherM/dotclaude/main/sync-to-github.sh)`
- **Usage**: Use command templates as checklists, invoke agents for specialized tasks
- **Key Dependencies**: git, curl, bash 3.2+, optional: colordiff, claude CLI
- **Python Focus**: uv for package management, emphasis on FastAPI/async/LLM patterns