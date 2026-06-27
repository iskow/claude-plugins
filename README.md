# joel-tools — personal plugin marketplace

A tiny Claude plugin marketplace. It doesn't contain plugins itself — it points
at other people's public plugin repos so I can install them in Cowork.

Currently lists:
- **mattpocock-skills** — Matt Pocock's engineering skills (fetched from
  `github.com/mattpocock/skills`). Updates flow automatically from his repo.

## How to add a new plugin later
Edit `.claude-plugin/marketplace.json`, add another entry to the `plugins`
array (give it a `name` and a `source`), commit, and push. Then refresh the
marketplace in Cowork.
