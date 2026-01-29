# Language Rules (Rust)

These rules extend the general language rules and apply to Rust repositories.

## SQLx & Postgres
- All SQL queries must use `sqlx` compile-time checked macros (`query!`, `query_as!`, etc.).
- Prefer `sqlx::test` for database-backed tests.
- Avoid dynamic SQL string building; keep queries parameterized and explicit.
- Do not use SQL stored procedures or SQL enums.
- Store complex fields as `JSONB` and serialize/deserialize in the persistence adapter when converting to/from `*TableRow` models.

## Persistence & repositories
- Persistence adapters (SQL, etc.) must follow the repository pattern with a repository trait and separate read/write traits.
- Repositories always return domain models; internally they must use private `*TableRow` models for persistence conversions. `*TableRow` models represent the data as it is saved.
- Each repository defines its own custom error type.
- Use custom types for `Error` and `BoxFut` for readability.

## Error handling
- Prefer custom error types with `thiserror`.
- Avoid `anyhow` in library code; reserve for binaries where appropriate.
- IO boundaries must map domain/business errors into standardized user-facing errors.

## Enums & string representations
- Prefer using enums instead of strings where possible.
- If a string representation is needed, enums may implement `FromStr` and `AsRef<str>`.

## Architecture & patterns
- Prefer Service and Manager patterns with traits to improve testability.
- No direct mutable repository calls in HTTP handlers; use `*Service` implementations instead.
- Avoid the `async_trait` polyfill; prefer native async in traits or alternative patterns.
- Use pure functions in private modules, but avoid across domain boundaries.
- Keep domain logic independent of transport and persistence concerns.
- `mod.rs` is for documentation and `mod` declarations/visibility only; do not place code, traits, or structs in `mod.rs`.

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