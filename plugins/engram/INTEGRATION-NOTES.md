# Engram — integration notes (Joel's setup)

Vendored from https://github.com/nagisanzenin/engram (MIT, © nagisanzenin / Quan Duong).
This file is Joel's own; it is not part of upstream. Everything else in this folder is upstream as-cloned.

## Why it's here
Engram is a full learning *plugin*, not three loose skills. The `learn`, `review`, and `coach`
skills are thin front-ends over `scripts/engram.py` (FSRS scheduling, learner model, receipts,
HTML dashboard) plus three subagents (`agents/`). Copying only the SKILL.md files would break them —
they all call `python3 "$ENGRAM" …`. So the whole plugin is vendored under `plugins/engram/`.

## When to use engram vs. the built-in `learn` skill
This is the "redundancy" to keep straight:

- **Built-in `learn` skill** — quick, one-off understanding. ELI5, "explain X", a fast quiz,
  "walk me through this." No persistence, no schedule. Use for a single sitting.
- **Engram `/learn`, `/review`, `/coach`** — durable study you want to *retain* over weeks.
  First-principles curriculum, verified free recall, FSRS-spaced reviews, retention telemetry.
  Use when the topic matters long-term (e.g. Project Management Specialist cert, Python, n8n).

Rule of thumb: **one sitting → built-in `learn`; keep it for months → engram.**

## Fits Joel's existing setup
- Engram's `skills/_shared/dialogue-grammar.md` (predict-before-reveal, no invented confidence,
  small steps, confirm before proceeding) matches the **teaching-style** memory — same discipline.
- Good home for the **Coursera learning plan** tracks (Python, Prompting, n8n) as engram topics.
- Independent of `joel-skills`; that plugin's "custom skills live only in joel-skills" rule is
  unaffected — engram is a separate vendored plugin, not a Joel-authored skill.

## Requirements
- Python 3 only (stdlib — no pip installs). Verified `engram.py` runs standalone.
- To activate the skills/subagents, install this plugin from the `joel-tools` marketplace, same as
  `joel-skills`. Until installed, the files are just vendored in the repo.

## Updating from upstream
Re-clone and copy over everything **except this file**:
`rsync -a --exclude='.git' --exclude='INTEGRATION-NOTES.md' engram/ plugins/engram/`
