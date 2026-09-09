# StayFlow Hotel OS

Malaysia-first enterprise Hotel Operating System.

**Current status:** engineering bootstrap / implementation readiness. Hotel business modules begin with Organisation and Property after this foundation is installed and verified.

## Architecture

- TypeScript-first monorepo
- Nx + pnpm
- NestJS modular monolith backend
- Next.js Hotel Portal and Guest PWA
- React Native + Expo Staff Mobile
- PostgreSQL transactional source of truth
- Redis + BullMQ for cache/background work
- Transactional Outbox for reliable domain events
- REST + OpenAPI 3.1
- AWS Malaysia commercial deployment target

## Repository map

```text
apps/
  api/
  hotel-web/
  guest-web/
  staff-mobile/
  worker/
  scheduler/
packages/
  ui/
  contracts/
  api-client/
  domain-shared/
  observability/
  config/
infrastructure/
  docker/
  terraform/
docs/
  architecture/
  adr/
  api/
  security/
  integrations/
  runbooks/
tests/
  e2e/
  integration/
  fixtures/
tools/
```

## Prerequisites

- Node.js 24 LTS
- pnpm 10.x
- Docker Desktop / Docker Engine
- Git

## Initial local setup

1. Copy `.env.example` to `.env` and keep `.env` uncommitted.
2. Start local infrastructure:
   `pnpm infra:up`
3. Install dependencies once app generators/packages are added:
   `pnpm install`
4. Commit the generated `pnpm-lock.yaml` before enabling frozen-lockfile CI.

## Engineering rules

- `main` is deployable.
- Feature branches are short-lived.
- Business logic does not live in controllers.
- ORM entities are not API contracts.
- Cross-module mutations do not directly update another module's private tables.
- Tenant isolation is server-side and tested negatively.
- Financial records use reversal/adjustment, never silent deletion.
- Critical events use the transactional outbox pattern.
- AI never bypasses RBAC, approval or business APIs.

## First production branch

`feat/E02-property-foundation`

First production domain:

`Organisation → Property → Business Date → Tenant Context → RBAC foundation`

See `docs/architecture/implementation-sequence.md` and `docs/adr/`.
