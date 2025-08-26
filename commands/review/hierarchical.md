# Hierarchical Code Review

Multi-stage comprehensive review using multiple subagents: strategic assessment, parallel specialized reviews, then consolidated recommendations.

**Stage 1**: Use @python-lead to think hard and assess architectural impact, technical debt, and identify risk areas (security, performance, complexity). Guide specialized review focus.

**Stage 2**: Parallel reviews using applicable subagents:

* @python-quality: business logic, error handling, test coverage, security, and architecture

**Stage 3**: Use @python-implementer to think hard and consolidate all findings into prioritized improvement roadmap, resolving conflicts and integrating recommendations.

For major features, architectural refactoring, critical business logic, cross-team projects, and technology upgrades.