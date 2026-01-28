# Base Engineering Rules (All repos)

## Architecture
- Prefer explicit boundaries over convenience.
- Keep modules cohesive; avoid "god" modules.
- Dependency direction: Domain -> Application -> Adapters (API/Persistence/External).

## Model separation
- Domain models: business meaning, invariants, pure types.
- API models (DTOs): request/response payloads, versioned if needed.
- Persistence models: DB schema representations.
- Mapping: explicit, testable, located at boundaries.

## Error handling
- Add context as errors bubble up.
- No silent error drops.
- Rust: avoid `unwrap()`/`expect()` in production paths (tests ok).

## Testing
- Unit tests for domain logic and mapping.
- Integration tests for adapters when behavior matters.
- Keep tests deterministic.

## Documentation
- Non-trivial decision -> add a short entry to `.agent/CONTEXT/DECISIONS.md`.
- Behavior changes -> update docs / README / API docs as appropriate.
