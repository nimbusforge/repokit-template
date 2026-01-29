# Coding Principles (Cross‑Project)

This guide is intentionally general. It applies across languages (Rust, Python, Node.js/TypeScript) and storage (Postgres/sqlx). Use `.agent/PROJECT.md` for repo‑specific rules.

## 1) Clarity over cleverness
- Prefer explicit, readable code.
- Avoid hidden control flow, surprising side effects, or “magic” abstractions.

## 2) Small, composable units
- Functions should do one thing and have clear inputs/outputs.
- Favor pure functions where possible.
- Keep modules cohesive; split when responsibilities diverge.

## 3) Explicit boundaries and mapping
- Separate domain, API (DTO), and persistence models.
- Use explicit mappers at boundaries; no implicit conversions.
- Keep dependency direction one‑way and explicit.

## 4) Defensive correctness
- Validate inputs at boundaries.
- Preserve invariants in constructors/factories.
- Handle error cases explicitly; no silent failures.

## 5) Errors with context
- Propagate errors with context meaningful to the caller.
- Prefer typed errors/enums to stringly‑typed errors.
- Log where it helps diagnosis, not as a substitute for error handling.

## 6) Deterministic tests
- Tests should be reliable, isolated, and repeatable.
- Avoid reliance on global state, time, or external services unless explicitly mocked/controlled.
- Use unit tests for logic and integration tests for boundaries.

## 7) Performance as a feature
- Measure before optimizing.
- Make hot paths explicit and documented.
- Avoid hidden N+1 IO or unbounded memory usage.

## 8) Security by default
- Never commit secrets.
- Least‑privilege access for services/credentials.
- Sanitize inputs and avoid injection risks (SQL, shell, template).

## 9) Observability built‑in
- Structured logs with stable fields.
- Correlate requests/jobs via IDs.
- Emit metrics/traces for critical paths.

## 10) Change discipline
- Keep changes minimal and reviewable.
- Link work to a single Issue.
- Update docs/decisions when behavior or architecture changes.

## 11) Consistent style
- Follow repo formatting and lint rules.
- Avoid mixing styles in the same module.
- Prefer conventions over personal preference.

## 12) Safe data handling
- Use parameterized queries; avoid string interpolation.
- Migrations should be additive and reversible where feasible.
- Document schema changes and backfills.

## 13) API contracts are explicit
- API surface is versioned and documented.
- Backward‑compatibility rules are honored.
- Validation and error mapping are explicit.

## 14) Concurrency is deliberate
- Avoid shared mutable state without clear ownership.
- Prefer message‑passing or immutable data.
- Document thread safety and synchronization strategy.

## 15) Reviewability
- Write code as if a teammate will maintain it.
- Prefer straightforward implementations over “clever” shortcuts.
- Include tests and rationale for non‑obvious decisions.