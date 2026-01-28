# Workflow (GitHub Issues + Conventional Commits)

GitHub Repository used for issues, labels and projects: {{REPOSITORY_NAME}}

## Source of truth
- Each change maps to exactly one GitHub Issue.

## Branch naming
- feat/<id>-<slug>
- fix/<id>-<slug>
- chore/<id>-<slug>

## Commit messages
Format: `type(scope): summary (#<id>)`
Examples:
- feat(api): add order endpoint (#123)
- refactor(domain): split pricing rules (#123)
- test(core): add unit tests for fee calc (#123)

## Pull requests
- Title should also include `(#<id>)`
- Body MUST include `Fixes #<id>`
- Include:
  - Context
  - Approach
  - Trade-offs / risks
  - How to test
