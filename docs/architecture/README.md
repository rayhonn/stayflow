# Architecture

Architecture baseline: Modular Monolith First, Distributed Platform Ready.

Core invariants:
1. Tenant boundaries cannot be crossed.
2. Reservation inventory is concurrency-safe.
3. Stay preserves room assignment history.
4. Financial entries are immutable in normal operation.
5. Sensitive actions use RBAC/approval.
6. Critical actions are audited.
7. AI cannot bypass application services.
8. Integrations are idempotent.
9. Critical events use reliable delivery.
10. Modules do not secretly mutate another module's private persistence.
