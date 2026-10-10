---
name: sintia-development
description: Work safely across Sintia's frontend and backend repositories. Use for Sintia features, fixes, reviews, authorization, Firebase, Prisma, API contracts, and end-to-end verification.
metadata:
  hermes:
    category: development
    tags: [sintia, nextjs, nestjs, firebase, prisma]
---

# Sintia Development

Use this as a project overlay together with the relevant general skill. Local
repository instructions and current manifests remain authoritative; verify them
before acting because versions and scripts can change.

## Locate the Change

- `frontend`: Next.js App Router, React, strict TypeScript, Tailwind, Firebase
  web authentication, Vitest, and Testing Library.
- `backend`: NestJS modular monolith, TypeScript, Prisma/PostgreSQL, Firebase
  Admin, Jest, and explicit authorization guards.
- Cross-repository feature: inspect both sides of the HTTP contract before
  editing either. Keep identifiers, status values, optional fields, errors, and
  permission names aligned.

Do not copy business rules into the frontend. Shared-looking types in separate
repositories are a contract to verify, not evidence that either copy is
authoritative.

## Security Invariants

- The browser sends a Firebase ID token. It never sends trusted user IDs,
  organization IDs, roles, or permissions as proof of authority.
- Only public Firebase web configuration belongs in `NEXT_PUBLIC_*`. Firebase
  Admin credentials and service-account material never enter the frontend.
- Capability-gated controls are user experience only. The backend must enforce
  every protected action and deny by default.
- Scope every backend lookup and mutation to the organization and Data Room;
  fetching by resource ID alone risks cross-tenant access.
- Effective permissions combine role grants and direct overrides; an explicit
  `DENY` wins. Preserve system-role and last-active-owner protections.
- Sensitive mutations that require an audit event should update domain state
  and append the audit event in the same database transaction. Never audit
  invitation tokens, credentials, or raw bearer tokens.

When a requested change conflicts with one of these invariants, stop and call
out the conflict instead of weakening the invariant silently.

## Frontend Guidance

- Respect Server/Client Component boundaries. Add `"use client"` only where
  browser APIs, state, effects, or Firebase client behavior require it.
- Keep API calls in the existing authenticated client path so Firebase tokens,
  error handling, and base URLs stay consistent.
- Render explicit loading, empty, forbidden, and API-error states for data-room
  administration flows.
- Prefer the existing component and styling language: compact tables, clear
  labels, restrained badges, confirmation for destructive access changes, and
  no raw permission codes in ordinary user-facing copy.
- Use `vercel-react-best-practices` and `vercel-composition-patterns`
  selectively. Do not add SWR, `better-all`, a cache package, or another state
  layer merely because an example uses it.

Frontend verification from the repository root:

```bash
npm test
npm run lint
npm run typecheck
npm run check:capabilities
npm run build
```

## Backend Guidance

- Keep the modular-monolith boundaries. Do not introduce a gateway,
  microservice, Redis, OpenFGA, SSO, or a new authorization layer without an
  explicit architectural request.
- Controllers validate transport input and declare permissions; services own
  business rules and transaction boundaries; Prisma access must preserve tenant
  scope.
- For schema changes, modify `prisma/schema.prisma`, create a migration, inspect
  the SQL, regenerate the client, and update seeds/tests as applicable. Never
  rewrite an applied migration or run a destructive reset against shared data.
- Test authorization changes with allowed and denied cases, tenant mismatch,
  suspended membership, override precedence, and privilege-escalation attempts
  when relevant.

Backend verification from the repository root:

```bash
npm run prisma:generate
npm run lint
npm run build
npm test
```

Run migration deployment and seed checks only against an explicitly safe,
configured database:

```bash
npm run prisma:migrate:deploy
npm run prisma:seed
```

## Cross-Repository Completion

For contract changes, verify both repositories. Add or update tests at the
backend authorization/business boundary and at the frontend user-visible
boundary. Report checks that could not run because Firebase, PostgreSQL, or
other external services were unavailable.
