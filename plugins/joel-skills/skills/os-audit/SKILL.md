---
name: os-audit
description: Audit Joel's Claude OS — inventory the live system, score it against the five-layer rubric, and rank what to build next. Use when Joel asks to audit, grade, or health-check his setup/system/Claude OS, asks "what should I build next?" or "where are the gaps?", after a major addition (new skill, connector, or cadence) to measure the delta, or when a scheduled task invokes the monthly audit.
---

Audit Joel's whole agent setup ("Claude OS") and produce an evidence-cited scorecard with a build queue. This skill is **read-only**: it observes, scores, and recommends. It never fixes, edits, or deletes anything during the audit — fixes are follow-up work Joel approves separately.

The root discipline is **evidence**: every score and finding must cite something actually observed this run (a path, a tool result, a file's content). If a layer can't be observed, say so and score what was seen — never fill gaps from memory or previous audits.

## Process

### 1. Inventory

Sweep the live system. For each layer, collect evidence fresh — do not reuse a prior audit's inventory.

- **Context:** read `CLAUDE.md`, `aboutme-agent-brief.md`, memory index (`MEMORY.md`). Note age signals — do priorities/facts still match what Joel has said recently?
- **Connections:** list connected MCP servers/connectors visible this session; note which are authenticated vs dead/unauthenticated.
- **Capabilities:** list skills in `joel-plugins-marketplace/plugins/joel-skills/skills/` and compare against loose copies elsewhere (e.g. `skills/`); note the agent-library and prompt-library.
- **Cadence:** call the scheduled-tasks list tool. Note each task's schedule, enabled state, and last-run date. Check output folders (e.g. `Weekly Digests/`) for whether recent runs actually produced files.
- **Compounding:** check the Obsidian vault (Session Vault, Wiki, prompt-library), audit history in `claude-os/audits/`, and the Correction Log in CLAUDE.md for recent entries.

*Done when:* every one of the five layers has at least one piece of observed evidence, and anything unobservable is listed as such.

### 2. Hygiene sweep

While inventorying, hunt for these specific rots:

- **Secrets exposure** — credential-looking files (keys, passwords, recovery codes) anywhere agents read. Flag path and file name only; NEVER read, quote, or copy the contents.
- **Duplication drift** — the same skill/doc/config living in two+ places with no declared source of truth.
- **Dead cadence** — scheduled tasks disabled, failing silently (no recent output file), or producing output nobody reads.
- **Sediment** — stale plans, spent one-time tasks, docs describing a system that no longer matches reality.
- **Orphans** — skills, agents, or prompts nothing references and Joel hasn't used in months.

*Done when:* each of the five rot categories has been explicitly checked and marked clean or flagged.

### 3. Score

Score each layer 0–20 using `references/RUBRIC.md` — read it now, score strictly by its anchors. Total /100.

Guard against **grade inflation**: when torn between two scores, take the lower and say what would earn the higher one. A flattering audit is a useless audit; Joel is QC-minded and wants the real number.

*Done when:* five layer scores exist, each justified by cited evidence against specific rubric anchors — no score justified by vibes.

### 4. Report

Write the report to `claude-os/audits/YYYY-MM-DD-audit.md` (create the folder if missing):

1. **Scorecard** — table: layer, score/20, one-line justification. Total /100.
2. **Delta** — compare against the most recent previous file in `claude-os/audits/`; show per-layer change and call out what improved or regressed. First audit: state it's the baseline.
3. **Findings** — hygiene flags first (secrets always at the top), each with evidence path and why it matters.
4. **Build queue** — the 3 highest-payoff next builds, ranked by payoff vs effort, each with a one-line "what done looks like". Then ONE quick win (under 30 min). Do not list ten ideas; Joel works one priority at a time.

In chat, give the one-paragraph version: total score, delta, top finding, and the single recommended next build.

*Done when:* the report file exists with all four sections, and the chat summary names exactly one next build.

## Rules

- Read-only run; recommend, don't repair. If Joel says "fix it", that's a new task after the audit is delivered.
- Secrets: flag location only, never contents.
- Score with today's evidence, not memory of past sessions.
- Same rubric every run — if the rubric itself seems wrong, finish the audit under it, then propose the rubric change as a finding.
