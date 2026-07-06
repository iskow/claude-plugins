# joel-tools — personal plugin marketplace

A tiny Claude plugin marketplace. It hosts my own plugin and points at other
people's public plugin repos so I can install everything from one place in Cowork.

Currently lists:
- **joel-skills** — my own skill bundle, hosted in this repo at
  `plugins/joel-skills/`: focus-toolkit, joel-brand, qc-gate. New skills get
  added here as they're built.
- **mattpocock-skills** — Matt Pocock's engineering skills (fetched from
  `github.com/mattpocock/skills`). Updates flow automatically from his repo.

## How to add a new skill to joel-skills
Copy the skill folder (with its `SKILL.md`) into `plugins/joel-skills/skills/`,
bump the `version` in `plugins/joel-skills/.claude-plugin/plugin.json`, commit,
and refresh the marketplace in Cowork.

## How to add a new plugin later
Edit `.claude-plugin/marketplace.json`, add another entry to the `plugins`
array (give it a `name` and a `source` — a relative path for plugins in this
repo, or a URL for external ones), commit, and push. Then refresh the
marketplace in Cowork.
