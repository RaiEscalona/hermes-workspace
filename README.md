# Hermes Workspace

Reusable agent skills for software discovery, implementation, debugging,
review, and delivery. Skills are intentionally project-aware: repository-local
instructions and manifests override examples in this workspace.

## Skill catalog

| Skill | Purpose | Sintia fit |
| --- | --- | --- |
| `brainstorming` | Clarifies ambiguous product and design work before implementation. | Useful for new workflows and UI concepts; skips already-specified changes. |
| `clean-code` | Keeps changes scoped, readable, and free of premature abstractions. | Applies to both frontend and backend. |
| `vercel-composition-patterns` | Vercel's scalable React component-composition patterns. | Frontend only; especially compound admin UI, with React 19 guidance. |
| `finishing-a-development-branch` | Verifies and offers safe branch-integration choices. | Uses each Sintia repository's full verification matrix. |
| `vercel-react-best-practices` | Vercel's React/Next.js performance guidance. | Frontend only; dependencies are examples, not automatic additions. |
| `requesting-code-review` | Structured independent review or disclosed self-review fallback. | Emphasize auth, tenant isolation, migrations, and cross-repo contracts. |
| `sintia-development` | Sintia-specific frontend/backend architecture and security overlay. | Primary project overlay for both repositories. |
| `systematic-debugging` | Evidence-led root-cause analysis and focused fixes. | Applies across browser, API, Firebase, Prisma, and PostgreSQL boundaries. |
| `test-driven-development` | Red-green-refactor for testable behavior and regressions. | Vitest/Testing Library in frontend; Jest and integration boundaries in backend. |
| `using-git-worktrees` | Creates isolated workspaces without fighting the host harness. | Useful because frontend and backend are separate Git repositories. |
| `verification-before-completion` | Requires fresh evidence for completion claims. | Includes tests, lint, types/build, capability checks, and safe schema checks. |
| `writing-plans` | Produces implementation-ready plans without transcribing code. | Useful for cross-repository and migration-heavy work. |

## Layout

Every skill has a `SKILL.md` entrypoint. Larger imported skills keep detailed
rules beside it:

- `react-best-practices/rules/` and `composition-patterns/rules/` contain
  focused Vercel rules; their compiled `AGENTS.md` files are reference copies.
- `systematic-debugging/` and `test-driven-development/` include optional
  techniques and examples loaded only when relevant.
- `brainstorming/scripts/` powers its optional visual companion.

There are no placeholder or empty directories under `skills/`. Do not add
empty `scripts/`, `references/`, or `assets/` folders; create them only when a
skill has a concrete resource to store.

## Maintenance

The Vercel and Superpowers source revisions are recorded in `config/`. When
refreshing imported material, preserve Hermes' project-first guardrails and
rerun the skill validator for every skill. Also check local Markdown links and
search for stale references to skills that are not shipped in this workspace.
