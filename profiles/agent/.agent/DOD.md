# Definition of Done

This checklist is intentionally language‑agnostic. Repos may add language‑specific sections in `.agent/PROJECT.md`.

## Must be true
- Scope matches the Issue; acceptance criteria are met.
- Implementation is covered by tests (unit/integration as appropriate).
- Lint/format/typecheck pass for the repo.
- CI is green (or explicitly justified).
- Docs/DECISIONS updated when behavior or architecture changes.
- PR includes clear “How to test” and links the Issue (e.g., `Fixes #<id>`).
- No secrets or sensitive data were introduced.

## Status hygiene
- Issue status label reflects current state.
- If blocked, the Issue notes the blocker and next step.

## Language‑specific checks (fill in per repo)
### Rust (if applicable)
- `cargo fmt --check`
- `cargo clippy --all-targets --all-features -- -D warnings`
- `cargo test --all-features`
- `cargo check --all-targets --all-features`

### Python (if applicable)
- `ruff check .`
- `ruff format --check .`
- `pytest -q`

### Node.js / TypeScript (if applicable)
- `npm run lint` or `pnpm lint`
- `npm run typecheck` (if TypeScript)
- `npm test` or `pnpm test`

### SQL / Migrations (if applicable)
- Migrations are reviewed and reversible where feasible.
- Queries are parameterized; no string interpolation.
- Schema changes documented and tested.

## Rollback note
- If runtime behavior changes, include a rollback note in the PR description or Issue.