# Language Rules (Rust)

These rules extend the general language rules and apply to Rust repositories.

## SQLx & Postgres
- All SQL queries must use `sqlx` compile-time checked macros (`query!`, `query_as!`, etc.).
- Prefer `sqlx::test` for database-backed tests.
- Avoid dynamic SQL string building; keep queries parameterized and explicit.

## Error handling
- Prefer custom error types with `thiserror`.
- Avoid `anyhow` in library code; reserve for binaries where appropriate.
- IO boundaries must map domain/business errors into standardized user-facing errors.

## Architecture & patterns
- Prefer Service and Manager patterns with traits to improve testability.
- Use pure functions in private modules, but avoid across domain boundaries.
- Keep domain logic independent of transport and persistence concerns.

## Runtime & composition
- Use the `processmanager` crate for runnable services.
- Use `instancebuilder` to construct service instances cleanly.

## API contracts
- REST APIs must have an OpenAPI spec.
- API validation and error mapping must be explicit.

## Testing
- Include unit tests for domain logic and mappers.
- Add integration tests for IO boundaries and adapters.
- Keep tests deterministic (no reliance on global state or timing).