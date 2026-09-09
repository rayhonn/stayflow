# Tenant Isolation Testing

Every property-scoped feature must include negative tests proving that a user from Organisation/Property A cannot read, search, mutate or infer existence of restricted resources from B. Test direct IDs, list/search endpoints, nested resources and indirect references.
