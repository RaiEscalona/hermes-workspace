# AGENTS.md — SintIA

## Project Context

SintIA is a Virtual Data Room and AI-assisted due diligence platform.

Expected stack:
- Frontend: Next.js, TypeScript, Tailwind CSS
- Backend: NestJS, PostgreSQL, Prisma
- Authentication: Firebase Authentication
- Authorization: Backend-managed roles and effective permissions

Inspect the repository before assuming that all these technologies or modules are implemented.

## Development Rules

1. Inspect existing code, modules, conventions and dependencies before implementing changes.
2. Reuse existing services, utilities and components whenever appropriate.
3. Follow DRY, KISS and SOLID principles without introducing unnecessary abstractions.
4. Keep changes focused on the requested task.
5. Never commit secrets, tokens, credentials or environment files.
6. Do not modify infrastructure, database schemas or authentication flows without explicit approval.
7. Prefer small, reviewable changes with clear tests.

## Git Workflow

- Use `dev` as the base branch unless explicitly instructed otherwise.
- Create task branches named `feature/*`, `fix/*` or `refactor/*`.
- Never commit directly to `dev` or `main`.
- Never force-push protected branches.
- Create Pull Requests targeting `dev`.
- Never merge a PR without explicit user approval.

## Quality Requirements

Before completing a task:
1. Review the diff.
2. Run relevant linting and type checks.
3. Run affected tests.
4. Check for authorization and security regressions.
5. Document failures or tests that could not be executed.

Do not claim a task is verified unless the corresponding checks actually ran.

## Security

- Firebase Authentication establishes identity, not application-level authorization.
- Effective permissions must be enforced by the backend.
- Frontend visibility must not be treated as an authorization boundary.
- Data Room, folder and document access must be checked at the appropriate resource scope.
- Follow least-privilege access principles.

## Delivery

For every completed task, provide:
- Summary of changes
- Modified files
- Tests executed and results
- Known limitations or risks
- Branch name and Pull Request URL, when applicable
