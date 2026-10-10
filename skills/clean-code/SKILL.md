---
name: clean-code
description: Review and improve code quality, eliminate unnecessary duplication, and apply maintainable design principles.
metadata:
  version: 1.0.0
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

1. Read repository instructions, manifests, and the affected code before choosing a pattern.
2. Search for existing implementations and reusable code.
3. Identify affected modules, contracts, data boundaries, and dependencies.
4. Make the smallest maintainable change that satisfies the request.
5. Run the repository's relevant tests, lint, type checks, builds, and domain-specific checks.
6. Review the diff for duplication, unintended API changes, and regressions.
7. Summarize changes, verification evidence, and remaining risks.

Do not introduce a new abstraction merely to satisfy DRY. Duplication is often
cheaper than a shared abstraction when the concepts only look similar or are
likely to evolve independently.

## Verification

- No unnecessary duplicated logic.
- Existing interfaces remain compatible where required.
- Tests pass or failures are documented.
- Changes are scoped to the task.
- No secrets or credentials are exposed.
