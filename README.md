# repokit-template

This repo contains repo templates applied by `repokit`.

## Structure
- `profiles/base/` is always applied first.
- Additional profiles can be applied in order (later profiles win on file collisions).

## Conventions
- Managed `.gitignore` is assembled from `gitignore.block` files per profile.
- Repo-local templates live under `.github/` (Issue/PR templates, workflows).
- Agent rules live under `.agent/`.
