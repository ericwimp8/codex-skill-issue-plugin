# Skill Issue Plugin

The standalone Codex plugin for creating, generating, evaluating, and
semantically refining agent skills.

## Install

Clone this repository, add it as a local Codex marketplace, and install the
plugin:

```sh
codex plugin marketplace add /path/to/codex-skill-issue-plugin
codex plugin add skill-issue@skill-issue
```

Start a new Codex thread after installation so the refreshed skills are loaded.

## Included Skills

- `skill-intake`: creates a build-ready A-to-B skill plan.
- `skill-generation`: produces the planned skill and hands it to evaluation.
- `skill-evaluation-and-refinement`: validates skill selection and behavior,
  then applies evidence-backed semantic refinements.

## Repository Relationship

This repository owns the plugin content. The
[Skill Issue](https://github.com/ericwimp8/skill-issue) CLI includes the same
skills through a Git submodule pinned to an exact commit of this repository.

After publishing `main`, the publishing agent triggers Skill Issue's
`sync-skill-issue-plugin.yml` workflow through GitHub CLI. The workflow updates
the pinned dependency to this repository's latest `main` commit, validates the
CLI, and pushes a commit-specific automation branch. The agent then opens and
merges the Skill Issue pull request through its authenticated GitHub CLI
session.

Do not edit plugin files from the Skill Issue submodule checkout. Make the
change here, validate it, push it, and trigger the dependency sync.

## License

MIT
