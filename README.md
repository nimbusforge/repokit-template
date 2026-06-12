# repokit-template

Reusable repository templates for bootstrapping and updating repositories with [`repokit-cli`](https://github.com/nimbusforge/repokit-cli).

This repository defines composable template profiles for common repository concerns such as base GitHub workflow files, agent operating rules, and language-specific overlays. It is designed to be consumed by `repokit-cli`, which applies the selected profiles to target repositories and updates them later with merge-aware behavior.

## What this repository contains

- `profiles/base/`: required baseline files for repository hygiene, including issue templates, pull request template, merge rules, and GitHub label definitions.
- `profiles/agent/`: reusable agent workflow and repository operating guidance.
- `profiles/python/`: Python-specific ignore rules and agent language guidance.
- `profiles/rust/`: Rust-specific ignore rules and agent language guidance.

`repokit-cli` always applies `profiles/base/` first, then overlays any additional profiles in the order you select.

## How it is used

Use [`repokit-cli`](https://github.com/nimbusforge/repokit-cli) to initialize a target repository from this template repo or update an existing initialized repository.

```bash
repokit init \
  --template https://github.com/nimbusforge/repokit-template.git \
  --ref main \
  --profiles base,agent
```

After initialization, the target repository can be updated with:

```bash
repokit update
```

For the full command set and behavior details, see the `repokit-cli` repository.

## Repository layout

The template source is organized by profile:

```text
profiles/
  base/
  agent/
  python/
  rust/
```

Within each profile:

- normal files are copied or merged into the target repository
- `.repokit/` contains `repokit-cli` configuration for merge rules and optional GitHub label sync
- later profiles override earlier ones when the same path exists in more than one profile

## Documentation

- [Template repository guide](docs/template-repository.md)
- [Repo coding flow](AGENTS.md)

## License

This repository is licensed under the MIT License. See [LICENSE](LICENSE).
