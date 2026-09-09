# ADR-009: Transactional outbox

**Status:** Accepted

## Decision

Write business state and outbox event in one transaction so critical events are not silently lost.

## Consequences

This decision is part of the StayFlow Phase 6/10 architecture baseline. Changes require a superseding ADR and migration plan where relevant.
