# Plugin Ownership

This repository is the canonical source for the Skill Issue plugin. Make every
plugin-content change here under `plugins/skill-issue/`.

The Skill Issue CLI consumes this repository as the
`dependencies/codex-skill-issue-plugin` submodule. Do not edit plugin files from
that checkout. A push to this repository's `main` branch updates the dependency
pointer on an automation branch in `ericwimp8/skill-issue` and opens a pull
request there.

Before pushing a plugin change:

1. Validate every changed skill with the active skill validator.
2. Validate the complete plugin with the active plugin validator.
3. Update the plugin cachebuster when Codex must load the changed bundle.
4. Confirm the commit contains only the intended plugin and repository-support
   changes.

Treat manual submodule-pointer updates in Skill Issue as recovery work. Normal
updates originate here and flow through `.github/workflows/update-skill-issue.yml`.

# Repository Secrets

`SKILL_ISSUE_DEPLOY_KEY` is the private half of a write-enabled deploy key
scoped only to `ericwimp8/skill-issue`. Keep it in GitHub Actions secrets. Never
write it to the repository, logs, fixtures, or documentation.
