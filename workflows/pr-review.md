# Pull Request Review Workflow

Default target branch: development

## Phase 1 — Context

1. Identify repository and PR number.
2. Read repository AGENTS.md.
3. Retrieve PR description and diff.
4. Verify the PR base branch.
5. Review relevant acceptance criteria.

## Phase 2 — Technical Review

Check:
- Functional correctness
- Regression risks
- Security vulnerabilities
- Authorization checks
- Duplicated logic
- Architecture consistency
- Missing validation
- Error handling
- Test coverage

## Phase 3 — Verification

1. Inspect GitHub Actions results.
2. Run additional tests when practical.
3. Identify missing verification.
4. Distinguish confirmed failures from possible risks.

## Phase 4 — Findings

Report:
- Critical issues
- High-priority issues
- Medium/low-priority improvements
- Files and lines
- Recommended corrections

## Phase 5 — Decision

Recommend one of:
- Ready for human review
- Changes requested
- More investigation required

Do not approve on behalf of the user.
Do not merge automatically.
Do not modify the PR unless authorized.
