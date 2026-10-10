# Feature Development Workflow

Base branch: development
Pull Request target: development

## Phase 1 — Discovery (Architect)

1. Read repository AGENTS.md.
2. Fetch the latest development branch.
3. Inspect existing architecture.
4. Identify relevant modules and dependencies.
5. Search for reusable services, components and utilities.
6. Identify security and data-model implications.

Deliverable:
- Scope
- Acceptance criteria
- Affected modules
- Technical risks

## Phase 2 — Planning (Architect)

1. Produce a concrete implementation plan.
2. Break large changes into verifiable tasks.
3. Identify required unit and integration tests.
4. Estimate architectural impact.
5. Request approval for high-risk changes.

## Phase 3 — Isolation (PR Manager)

1. Confirm origin/development exists.
2. Verify the base repository has no uncommitted changes.
3. Create a unique branch named feature/<task>.
4. Create a dedicated Git worktree from origin/development.
5. Verify the current branch and working directory.

Never modify development directly.

## Phase 4 — Implementation (Developer)

1. Delegate implementation to Codex CLI where appropriate.
2. Follow repository-specific instructions.
3. Implement acceptance criteria.
4. Reuse existing abstractions where practical.
5. Keep changes focused.
6. Add relevant automated tests.

## Phase 5 — Verification (QA)

1. Run relevant lint checks.
2. Run type checks.
3. Run unit and integration tests.
4. Inspect changes with git diff.
5. Verify acceptance criteria.
6. Record actual command outcomes.

## Phase 6 — Review (Reviewer)

Review:
- Functional correctness
- Regressions
- Architecture consistency
- Security
- Authorization
- Code duplication
- Test coverage

Resolve blocking findings before delivery.

## Phase 7 — Delivery (PR Manager)

1. Commit only intended files.
2. Push the feature branch.
3. Open a Draft PR targeting development.
4. Include implementation summary.
5. Include test evidence and risks.
6. Report PR URL to the user.

Never merge automatically.
