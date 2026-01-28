# Definition of Done

## Must be true
- Behavior is covered by tests (unit/integration as appropriate).
- Lint/format/typecheck pass (per language in this repo).
- CI is green.
- Docs/DECISIONS updated when architecture/behavior changes.
- PR includes clear "How to test" and `Fixes #<id>`.

## Rust commands (when repo uses Rust)
- cargo fmt --check
- cargo clippy --all-targets --all-features -- -D warnings
- cargo test --all-features
- cargo check --all-targets --all-features

## Python commands (when repo uses Python)
- ruff check .
- ruff format --check .
- pytest -q
