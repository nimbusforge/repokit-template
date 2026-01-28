# Agent Operating Guide

## Read order (mandatory)
1) .agent/BASE.md
2) .agent/PROJECT.md
3) .agent/WORKFLOW.md
4) .agent/DOD.md
5) .agent/CONTEXT/* (as needed)

## Scope and focus
- Work on exactly ONE GitHub Issue at a time.
- Keep changes minimal and reviewable.
- If scope expands, update the Issue plan and explain in PR.

## Non-negotiables
- Separate Domain vs API (DTO) vs Persistence models.
- Domain must not depend on transport (HTTP), DB drivers, vendor SDKs, or IO.
- Mapping is explicit and lives at boundaries (no scattered implicit conversions).
- Avoid hidden coupling; dependencies must be explicit across module boundaries.

## Safety
- Never commit secrets.
- Do not silently change CI or formatting rules; if needed, explain in PR.

## Completion rule
Do not claim completion unless `.agent/DOD.md` is satisfied and you can describe:
- what changed
- how it was tested
- trade-offs / risks
