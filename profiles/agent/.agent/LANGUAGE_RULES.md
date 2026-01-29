# Language Rules (General)

These are cross-project language rules that apply when no language-specific section overrides them.

## General engineering rules
- Prefer explicit, readable code over cleverness.
- Keep functions small and composable with clear inputs/outputs.
- Separate domain, API/transport, and persistence models.
- Use explicit mapping at boundaries; no implicit conversions.
- Keep dependency direction one-way and explicit.
- Validate inputs at the boundary; preserve invariants in constructors.
- Errors should be explicit and contextual; avoid silent failures.
- Tests must be deterministic and isolated.

## Data & persistence
- Use parameterized queries (never string interpolation for SQL).
- Migrations should be additive and reversible where feasible.
- Keep persistence details in adapters, not in domain logic.

## Observability
- Use structured logs with stable fields.
- Correlate logs/traces per request or job.
- Emit metrics/traces for critical paths.

## Documentation
- Document non-trivial decisions.
- Update docs when behavior or architecture changes.

## Security
- Never commit secrets.
- Apply least-privilege access.
- Sanitize inputs to prevent injection risks.

## API & contracts
- Define API contracts explicitly and keep them versioned.
- Validation and error mapping must be explicit.

## Testing expectations
- Unit tests for domain logic and mapping.
- Integration tests for adapters and IO boundaries.
- Avoid flakiness; tests should be repeatable.