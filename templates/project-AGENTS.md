# Project Development Instructions

## Project

Read README.md, package.json and existing documentation
to understand this repository.

Do not assume technology or architecture without inspection.

## Git

Default base branch: development
Pull Request target: development

Task branches:
- feature/*
- fix/*
- refactor/*
- chore/*

Never commit directly to development or main.

## Implementation rules

1. Inspect existing architecture before changing code.
2. Reuse existing utilities, components and services.
3. Follow existing conventions.
4. Avoid duplicated business logic.
5. Implement the smallest correct change.
6. Preserve compatibility when required.
7. Add tests for meaningful behavior changes.

## Quality

Before creating a PR:
- Run available lint checks.
- Run available type checks.
- Run relevant tests.
- Review the final diff.
- Check for accidental secrets.
- Report failed or unavailable checks.

Use commands discovered from the actual repository,
not assumed commands.

## Security

Respect existing authentication and authorization boundaries.

Do not change production credentials or infrastructure.

Do not execute destructive database migrations
without explicit authorization.

## Pull Requests

Create Draft PRs targeting development.

Include:
- Summary
- Files changed
- Tests executed
- Risks
- Known limitations

Never merge automatically.
