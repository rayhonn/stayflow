# API

Primary contract style: REST + OpenAPI 3.1 under `/api/v1`.

API errors use a consistent Problem Details-style shape including stable `code` and `correlationId`. Retry-sensitive mutations support idempotency.
