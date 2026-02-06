# Workflow 

GitHub Repository: {{REPOSITORY_NAME}}
This workflow is intentionally general so it can be reused across repositories.

## Source of truth
- Every change maps to exactly one GitHub Issue.
- The Issue contains current status via labels and/or the Issue form status field.
- If scope changes, update the Issue (plan + acceptance criteria).

## Issue types
Use the repo’s issue templates:
- Story: user-facing change or feature.
- Task: internal work or a unit of delivery.
- Bug: defect or regression.
- Docs: documentation updates.
- Spike: time-boxed research to reduce uncertainty.

## Status tracking (labels)
Exactly one status label should be active at a time:
- `status:triage` → `status:in-progress` → `status:review` → `status:done`
- When you start work, immediately move the Issue to `status:in-progress` (or update the Issue status field).
- If blocked, use `status:blocked` and comment with the blocker + next step.

## Branching (GitHub Flow)
- Always run `git fetch origin` before creating any branch.
- Always create a local branch from the primary branch (`main` or `master`, whichever exists).
- Create the branch as `feat/<id>-<slug>`, `fix/<id>-<slug>`, or `chore/<id>-<slug>`.
- Check out the new branch locally and set the upstream to the remote (push it once so both local and remote branches exist).
- If you can’t create a local branch (detached HEAD, missing permissions, or no remote access), stop and fix before starting work.
- Keep branches small and focused on one Issue.

## Coding Flow
1. Load issue/ticket.
2. Check if the ticket is self-explanatory. If not, ask clarification questions and update the ticket (plan + acceptance criteria).
3. Run `git fetch origin`, then create a local branch from `main`/`master` (whichever exists).
4. Work in small units; keep working notes, decisions, TODOs, and risks.
5. Run diagnostics.
6. Document progress in the ticket (what’s done, what’s next).
7. Ask to continue if needed due to token limits.
8. If continuing and not done, go back to step 4.
9. Check Definition of Done (diagnostics, required tests/linters).
10. Ask to commit, push, and open a PR (title includes issue ID; body has `Fixes #<id>`).

## Commits
Format: `type(scope): summary (#<id>)`
Examples:
- `feat(api): add order endpoint (#123)`
- `fix(core): handle null price (#123)`
- `docs(readme): clarify setup steps (#123)`

## Pull requests
- Title includes `(#<id>)`.
- Body includes `Fixes #<id>`.
- Include: Context, Approach, Trade-offs/Risks, How to test.
- Keep PRs reviewable; split if needed.

## Review & merge
- Request review when ready; update status to `status:review`.
- Address feedback; keep commits clean.
- Merge using the repo’s preferred strategy.

## Completion
- Ensure Definition of Done is satisfied.
- Update Issue plan/checklist.
- Set status to `status:done` and close the Issue.
- Link the PR in the Issue.

## Escalation
- If blocked or confidence is low, add `status:blocked` and comment with:
  - blocker
  - what’s needed
  - next action
