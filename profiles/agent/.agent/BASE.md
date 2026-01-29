# Base Engineering Rules (All Repos)

These rules are intentionally cross‑project. Project‑specific details belong in `.agent/PROJECT.md`.

## Architecture & boundaries
- Prefer explicit boundaries over convenience.
- Keep modules cohesive; avoid “god” modules.
- Dependency direction should be one‑way and explicit (e.g., Domain → Application → Adapters/IO).
- If a boundary is crossed, add a mapper or façade at the boundary.

## Model separation
- Domain models: business meaning, invariants, pure types, no IO.
- API models (DTOs): request/response payloads and validation.
- Persistence models: DB schema representations.
- Mapping is explicit, testable, and lives at boundaries.

## Error handling
- Add context as errors bubble up.
- No silent error drops.
- Prefer typed errors or error enums over stringly‑typed errors.

## Data & persistence
- Keep queries parameterized; avoid interpolation in SQL.
- Migrations are additive and reversible where feasible.
- Use repository interfaces in the domain/application layers; DB details live in adapters.

## Testing
- Unit tests for domain logic and mapping.
- Integration tests for adapters when behavior matters.
- Keep tests deterministic and isolated.

## Security
- Never commit secrets.
- Validate inputs at the boundary.
- Principle of least privilege for credentials and services.

## Observability
- Emit structured logs with stable fields.
- Add metrics or traces for critical paths.
- Correlate logs/traces per request/job.

## Documentation
- Non‑trivial decisions → add a short entry to `.agent/CONTEXT/DECISIONS.md`.
- Behavior changes → update docs/README/API docs as appropriate.

## Code hygiene
- Keep changes minimal and reviewable.
- Avoid “clever” code when a clear version is available.
- Prefer small, composable functions with explicit inputs/outputs.