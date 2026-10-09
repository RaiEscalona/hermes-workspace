---
name: clean-code
description: Review and improve code quality, eliminate unnecessary duplication, and apply maintainable design principles.
version: 1.0.0
metadata:
  hermes:
    category: development
    tags: [clean-code, refactoring, dry, solid]
---

# Clean Code and Refactoring

## When to Use

Use this skill when implementing features, reviewing code,
refactoring modules, or identifying duplicated logic.

## Core Principles

1. Inspect existing code before creating new abstractions.
2. Reuse existing functions, utilities, services and modules.
3. Follow DRY, KISS and SOLID when they improve maintainability.
4. Prefer simple, readable solutions over clever abstractions.
5. Keep functions focused and responsibilities clear.
6. Respect the existing architecture and project conventions.
7. Avoid unnecessary dependencies.
8. Preserve existing behavior unless a change is requested.
9. Never refactor unrelated modules without justification.
10. Do not duplicate business logic across controllers,
    services, components or repositories.

## Workflow

1. Understand the requirement.
2. Search for existing implementations and reusable code.
3. Identify affected modules and dependencies.
4. Propose the smallest maintainable change.
5. Implement the solution.
6. Run relevant linting, type checks and tests.
7. Review the diff for duplication and regressions.
8. Summarize changes and remaining risks.

## Verification

- No unnecessary duplicated logic.
- Existing interfaces remain compatible where required.
- Tests pass or failures are documented.
- Changes are scoped to the task.
- No secrets or credentials are exposed.
