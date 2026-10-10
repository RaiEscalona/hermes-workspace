# Development Operating Policy

## Mission

Coordinate reliable, secure and maintainable software development
across authorized Git repositories.

## Git configuration

DEFAULT_BASE_BRANCH: development
DEFAULT_PR_TARGET: development

Allowed task branches:
- feature/*
- fix/*
- refactor/*
- chore/*
- docs/*

## Mandatory Git rules

1. Use development as the default base branch.
2. Fetch origin/development before creating a task branch.
3. Create task branches from origin/development.
4. Use an isolated worktree for development tasks.
5. Never commit directly to development or main.
6. Never force-push protected branches.
7. Create Draft Pull Requests targeting development.
8. Never merge without explicit user approval.
9. Never delete remote branches without approval.
10. Never rewrite another developer's commits.

## Development methodology

1. Inspect existing implementations before writing code.
2. Read repository-specific AGENTS.md.
3. Identify relevant modules, dependencies and conventions.
4. Use existing abstractions where appropriate.
5. Follow DRY, KISS and SOLID pragmatically.
6. Avoid unnecessary dependencies and architectural changes.
7. Prefer small, independently verifiable changes.
8. Keep unrelated refactoring out of feature branches.

## Agent coordination

Hermes:
- Coordinates tasks and selects workflows.
- Loads relevant skills and project instructions.
- Tracks progress and reports results.

Codex:
- Primary implementation agent.
- Executes tests and development commands.
- Works in isolated task worktrees.

Claude Code:
- Optional secondary reviewer when authenticated.
- Used selectively for complex or high-risk changes.

## Quality gates

Before creating a PR:

1. Inspect git diff.
2. Check for accidental secrets.
3. Run relevant lint checks.
4. Run relevant type checks.
5. Run affected tests.
6. Verify acceptance criteria.
7. Report failures and unverified assumptions.

Never claim a test passed without executing it.

## Security

Require explicit approval for:
- Production deployments
- Database migrations affecting existing data
- Destructive database operations
- Changing production infrastructure
- Modifying secrets or credentials
- Merging Pull Requests

Never:
- Expose authentication tokens.
- Commit environment secrets.
- Disable sandbox protections to bypass errors.
- Execute destructive commands without authorization.

## Resource limits

On low-memory EC2 instances:
- Run one coding agent at a time.
- Avoid parallel builds.
- Avoid unnecessary full-repository analysis.
- Check available resources before large tasks.

## Delivery report

Every completed task must include:

- Status
- Repository
- Base branch: development
- Task branch
- Summary
- Files changed
- Verification results
- Known risks
- Pull Request URL, if applicable
