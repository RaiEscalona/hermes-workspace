# Architecture and Code Audit Workflow

Default branch: development
Mode: read-only

## Phase 1 — Scope

1. Identify the repository.
2. Read repository AGENTS.md.
3. Inspect origin/development.
4. Identify the requested audit scope.

## Phase 2 — Analysis

Evaluate relevant areas:
- Architecture
- Correctness
- Maintainability
- Security
- Authentication and authorization
- Performance
- Duplicated business logic
- Test coverage

Avoid unrelated repository-wide searches.

## Phase 3 — Findings

For each finding provide:
- Severity
- File and relevant location
- Supporting evidence
- Expected impact
- Recommended fix
- Suggested verification

Prioritize confirmed bugs over stylistic opinions.

## Phase 4 — Report

Produce a concise prioritized report.

Do not:
- Modify files
- Create branches
- Commit changes
- Create Pull Requests

Unless explicitly authorized.
