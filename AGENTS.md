# Plugin Ownership

This repository is the canonical source for the Skill Issue plugin. Make every
plugin-content change here under `plugins/skill-issue/`.

The Skill Issue CLI consumes this repository as the
`dependencies/codex-skill-issue-plugin` submodule. Do not edit plugin files from
that checkout.

Before pushing a plugin change:

1. Validate every changed skill with the active skill validator.
2. Validate the complete plugin with the active plugin validator.
3. Update the plugin cachebuster when Codex must load the changed bundle.
4. Confirm the commit contains only the intended plugin and repository-support
   changes.
5. After pushing `main`, trigger the Skill Issue dependency sync:

   ```sh
   gh workflow run sync-skill-issue-plugin.yml --repo ericwimp8/skill-issue
   ```

6. After the workflow succeeds, open and merge the Skill Issue pull request from
   `automation/skill-issue-plugin-<first-12-commit-characters>`.

The workflow writes only the commit-specific automation branch. Treat direct
manual submodule-pointer updates as recovery work.
