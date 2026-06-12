# Project Rules (Repo‑specific)

Use this file to tailor the agent to the repo. Keep it short and actionable. This is the *only* place for repo‑specific rules; everything else should remain general.

---

## Overview
- **Purpose:**
- **Primary constraints:**
- **Explicit non‑goals:**

## Architecture summary
- **High‑level modules/layers:**
  - `<module>`: purpose, boundary
- **Dependency direction:**
  - `<example: domain → app → adapters>`
- **Forbidden dependencies (if any):**
  - `<module A> must not import <module B>`

## Technology stack
- **Languages:** (e.g., Rust, Python, TS)
- **Frameworks/libraries:** (short list)
- **Database/storage:** (e.g., Postgres, Redis, S3)
- **Observability:** (logging/metrics/tracing tools)

## Model boundaries & mapping
- **Domain models live in:**
- **API DTOs live in:**
- **Persistence models live in:**
- **Mapping code lives in:**
- **Mapping tests live in:**

## Data & persistence rules
- **Migration tool + policy:**
- **Query safety:** (e.g., parameterized only)
- **Schema evolution expectations:**

## Error handling conventions
- **Error types:**
- **Where to add context:**
- **User‑facing error mapping:**

## Testing & quality gates
- **Required test types:** (unit/integration/e2e)
- **Determinism constraints:**
- **Mandatory commands:** (list repo‑specific checks)

## Security & compliance
- **Secrets management:**
- **Input validation expectations:**
- **PII/PHI handling constraints:**

## Observability requirements
- **Correlation IDs:** (format + where to attach)
- **Log fields to include:**
- **Metrics/tracing requirements:**

## API / contract rules (if applicable)
- **OpenAPI / schema location:**
- **Versioning rules:**
- **Backward compatibility expectations:**

## Performance & concurrency
- **SLAs / SLOs:**
- **Hot paths:**
- **Concurrency constraints:**

## Workflow specifics
- **Default branch:**
- **Branch naming exceptions:**
- **Review rules:**
- **Merge strategy:**

## Documentation expectations
- **Docs that must be updated for changes:**
- **ADR/decision log location:**
- **What belongs in the decision log:** stable layer ownership, domain/API/persistence boundary rules, contract versioning rules, and cross-cutting runtime policies.
- **What does not belong in the decision log:** issue-slice refactors, extracted services, renamed files, file splits, test-module reorganizations, or cleanup passes unless they create a reusable repo-wide rule.
- **Where implementation history goes:** issue and PR updates by default; use an archive only if the note is worth keeping but not part of the active architectural working set.

## Language‑specific conventions
### Rust
- **Crate/module placement rules:**
- **Lint configuration:**
- **SQLx usage rules:**

### Python
- **Formatting/linting:**
- **Type checking:**
- **Dependency management:**

### Node.js / TypeScript
- **Formatting/linting:**
- **Type checking:**
- **Package manager:**

---

## Repo quickstart (optional)
- **Setup:**
- **Run:**
- **Test:**
- **Common pitfalls:**
