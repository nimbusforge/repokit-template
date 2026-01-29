# Language Rules (Python - Minimal)

This profile targets scripting and small projects. Keep setup lightweight and favor clarity.

## General guidance
- Prefer explicit, readable code.
- Keep functions small and focused.
- Validate inputs at boundaries.
- Use exceptions with clear messages; avoid silent failures.

## Tooling (minimal)
- Testing: `pytest` when tests are needed, otherwise optional.
- Linting/formatting: optional; use only if already configured.

## Dependencies
- Keep dependencies minimal.
- Pin versions only when stability is required.

## Data & IO
- Parameterize any SQL.
- Handle IO errors at the boundary and return user-friendly messages.