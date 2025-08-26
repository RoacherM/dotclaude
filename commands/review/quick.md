# Quick Code Review

Simple two-stage review for rapid assessment and focused feedback.

**Stage 1**: Use @python-lead to assess whether the change needs deeper review, has architectural concerns, or security implications.

**Stage 2**: Based on findings, choose one or multiple agents for parallel review:
* @python-quality: unified Python review (quality, security, architecture)

For small bug fixes, simple features, formatting, documentation, tests, and configuration changes. Escalate to hierarchical review for core business logic, architectural impact, security operations, API changes, or performance-critical paths.