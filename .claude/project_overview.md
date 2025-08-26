# Project Overview

## Project Identity
- **Name**: dotclaude - Multi-Agent Configuration for Claude Code
- **Type**: Configuration Repository / Documentation System
- **Tech Stack**: Markdown documentation, Bash scripting, Git workflows
- **Entry Point**: `sync-to-github.sh` for configuration sync

## Architecture Deep Dive
- **Directory Structure**:
  - `agents/` - Agent definitions (.md files with frontmatter)
  - `commands/` - Structured workflow templates (.md files)
  - `CLAUDE.md` - Project-wide development guidelines
  - `sync-to-github.sh` - Interactive sync script
- **Module Organization**: Documentation-based with clear separation between agents and commands
- **Design Patterns**: Template-driven workflows, multi-agent collaboration patterns
- **Data Flow**: User → Command Templates → Agent Invocations → Development Actions

## Core Components Analysis
- **Agents**: 6 specialized agents for Python-first development
  - `python-orchestrator.md` - Session bootstrap, repo scanning, `.claude/` state management
  - `project-state-manager.md` - Cross-session state tracking (3-file system)
  - `python-reviewer.md` - Unified Python code review (quality + security + architecture)
  - `security-reviewer.md` - Python security auditing
  - `tech-lead-reviewer.md` - Architectural guidance
  - `code-simplifier.md` - Python refactoring and optimization
- **Commands**: Structured workflow templates
  - Review workflows (`/review/quick`, `/review/hierarchical`)
  - Fix operations (`/fix/code-quality`, `/fix/security`)
  - Git operations (`/git/commit`, `/git/push`, `/git/release`)
  - GitHub integration (`/gh/create-issues`, `/gh/resolve-issues`)
  - Development utilities (`/session-init`, `/continue`, `/refactor`)
- **Configuration**: `CLAUDE.md` contains development guidelines and Python tooling preferences

## Development Environment
- **Setup**: Standard Git repository, no additional dependencies beyond `git`, `curl`, `bash 3.2+`
- **Testing**: No formal test suite (documentation-based project)
- **Build/Deploy**: `sync-to-github.sh` handles distribution to user's `~/.claude/` directory
- **Code Quality**: Markdown formatting, clear documentation structure

## Current Development State
- **Active Work Areas**: Agent refinement, command template optimization
- **Recent Implementations**: 
  - Python-first restructuring with `python-orchestrator` and `python-reviewer`
  - Simplified state management to 3-file system (project_overview, changelog, current_focus)
  - Enhanced GitHub integration with intelligent branch detection
- **Next Priorities**: 
  - Continue refining agent prompts based on usage feedback
  - Expand command template coverage for common Python workflows
- **Technical Debt**: None significant - clean documentation structure