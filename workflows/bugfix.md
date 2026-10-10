# Bug Fix Workflow

Base branch: development
Pull Request target: development

## Phase 1 — Reproduce

1. Inspect the reported problem.
2. Read relevant AGENTS.md instructions.
3. Identify reproduction steps.
4. Inspect logs and affected code.
5. Confirm the failure when possible.

Do not assume a root cause without evidence.

## Phase 2 — Diagnose

Use systematic-debugging.

1. Trace the failing execution path.
2. Identify the root cause.
3. Identify affected modules.
4. Determine possible adjacent regressions.
5. Explain the proposed correction.

## Phase 3 — Isolate

1. Fetch origin/development.
2. Create a fix/<task> branch.
3. Use a dedicated Git worktree.
4. Never edit development directly.

## Phase 4 — Regression test

1. Create a test reproducing the bug where practical.
2. Confirm that the test fails for the expected reason.
3. Document cases where reproduction is unavailable.

## Phase 5 — Fix

1. Delegate implementation to Codex when appropriate.
2. Apply the smallest correct change.
3. Avoid unrelated refactoring.
4. Preserve existing interfaces unless changes are required.

## Phase 6 — Verify

1. Run regression tests.
2. Run relevant existing tests.
3. Run lint and type checks.
4. Review the diff.
5. Check security impacts.

## Phase 7 — Deliver

1. Push the fix branch.
2. Create a Draft PR targeting development.
3. Explain the root cause.
4. Explain the correction.
5. Include verification evidence.
6. Never merge automatically.
