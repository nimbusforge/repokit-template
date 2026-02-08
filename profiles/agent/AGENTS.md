# Agent Operating Guide

## General agent rules:
- Apply the base engineering rules in `.agent/BASE.md` for all repos.
- Apply repo-specific rules only from `.agent/PROJECT.md`.
- Follow the GitHub Issues + GitHub Flow process in `.agent/WORKFLOW.md`.
- Treat `.agent/DOD.md` as the Definition of Done and check it before completion.
- Keep changes minimal, explicit, and reviewable.
- Maintain clear separation of domain, API (DTO), and persistence models with explicit mapping at boundaries.
- Avoid hidden coupling; dependencies must be explicit across module boundaries.
- Do not commit secrets or sensitive data.
- If blocked or uncertain, update issue status and document the blocker + next step.

## Read order (mandatory)
1) `.agent/BASE.md`
2) `.agent/PROJECT.md`
3) `.agent/WORKFLOW.md`
4) `.agent/DOD.md`
5) `.agent/CODING_PRINCIPLES.md`
6) `.agent/LANGUAGE_RULES.md`
7) `.agent/CONTEXT/*` (as needed)

## Scope and focus
- Work on exactly ONE GitHub Issue at a time.
- Keep changes minimal and reviewable.
- If scope expands, update the Issue plan and explain in the PR.

## Non-negotiables
- Separate Domain vs API (DTO) vs Persistence models.
- Domain must not depend on transport (HTTP), DB drivers, vendor SDKs, or IO.
- Mapping is explicit and lives at boundaries (no scattered implicit conversions).
- Avoid hidden coupling; dependencies must be explicit across module boundaries.

## Coding principles
- Follow `.agent/CODING_PRINCIPLES.md` for cross-project guidance.
- Use `.agent/PROJECT.md` for repo-specific exceptions or additions.

## Safety
- Never commit secrets.
- Do not silently change CI or formatting rules; if needed, explain in the PR.
- Work on exactly one Issue at a time.
- Update Issue plan/acceptance criteria if scope changes.
- When done, summarize what changed, how it was tested, and any trade-offs/risks.

## Completion rule
Do not claim completion unless `.agent/DOD.md` is satisfied and you can describe:
- what changed
- how it was tested
- trade-offs / risks
