# Template Repository Guide

This repository is the template source consumed by [`repokit-cli`](https://github.com/nimbusforge/repokit-cli).

Use this guide if you need to understand how the template repository is organized, what each profile owns, or how changes here affect target repositories.

## Relationship to `repokit-cli`

`repokit-cli` applies selected profiles from this repository into a target repository, records template metadata in `.kit.toml`, and later updates the target repo using the same template source.

In practice, that means this repository owns:

- the files that should appear in target repositories
- merge behavior for files that should be updated rather than overwritten blindly
- optional GitHub label definitions that can be synced into target repositories

`repokit-cli` owns:

- fetching the template source
- applying selected profiles in order
- tracking template state in `.kit.toml`
- performing update, status, and config operations in target repositories

## Profile structure

`repokit-cli` expects a template repository shaped like this:

```text
profiles/
  base/
    .repokit/
  <profile>/
    .repokit/
```

Rules for this repository:

- `profiles/base/` is required and is always applied first.
- Additional profiles are optional overlays.
- If two selected profiles provide the same path, the later profile wins unless a merge rule applies.

Current profiles in this repository:

- `base`
  Provides shared repository defaults such as issue templates, pull request template, base `.gitignore`, label definitions, and merge rules.
- `agent`
  Provides reusable `.agent/` guidance plus `AGENTS.md` for agent-driven repositories.
- `python`
  Adds Python-specific ignore patterns and `.agent/LANGUAGE_RULES.md` content.
- `rust`
  Adds Rust-specific ignore patterns and `.agent/LANGUAGE_RULES.md` content.

## `repokit` configuration inside profiles

The `.repokit/` directory is template metadata for `repokit-cli`. It is not copied into target repositories.

This repository currently uses:

- `profiles/base/.repokit/merge.toml`
  Merges `.gitignore` using the `gitignore` strategy.
- `profiles/base/.repokit/github/labels.toml`
  Defines the GitHub labels that can be added to target repositories.
- `profiles/agent/.repokit/merge.toml`
  Merges `.agent/LANGUAGE_RULES.md` as a Markdown block so language-specific overlays can extend it cleanly.

## Authoring and maintenance guidance

When changing this repository:

- keep profiles focused on a single concern
- put shared defaults in `base`
- add language or workflow-specific behavior in overlays
- update docs when profile responsibilities or public usage expectations change
- verify that the documented structure still matches the actual files under `profiles/`

For repository-local contributor workflow, see [AGENTS.md](../AGENTS.md).
