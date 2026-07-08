# os-audit Scoring Rubric

Five layers, 0–20 each, total /100. Score by the anchors below — pick the band the evidence supports, then the exact number within it. When torn, take the lower band.

Interpretation of totals: <50 = foundation incomplete; 50–69 = working but leaky; 70–84 = solid OS, compounding; 85+ = exceptional (be suspicious of your own scoring above 85).

## 1. Context (0–20) — what the system knows about Joel

- **0–5:** No profile, or generic/stale CLAUDE.md an agent couldn't act from.
- **6–10:** Profile exists but incomplete or aging — key facts (availability, goals, active projects) missing or contradicted by recent conversations.
- **11–15:** CLAUDE.md + about-me current and specific; memory index maintained; a fresh agent could answer "what should Joel focus on this week?" with specifics.
- **16–20:** All of the above PLUS active upkeep observed: Correction Log growing, memories updated within the last month, no contradiction between any context file and observed reality.

## 2. Connections (0–20) — what the system can reach

- **0–5:** No live connectors; everything manual copy-paste.
- **6–10:** A few connectors work, but daily-driver tools (tasks, email, calendar) not reachable, or half the connected list is dead/unauthenticated.
- **11–15:** The tools Joel checks daily are connected and working; dead connectors are the exception.
- **16–20:** All of the above PLUS no zombie connectors (everything connected is used by some skill or cadence), and no data Joel routinely needs is out of reach.

Score what's *used*, not what's *installed* — twenty connected-but-unused MCPs is a 6, not an 18.

## 3. Capabilities (0–20) — what the system can do repeatably

- **0–5:** No custom skills; every task is a from-scratch prompt.
- **6–10:** A few skills exist but are stale, duplicated across locations, or rarely trigger correctly.
- **11–15:** Core repeated workflows (client intake, QC, research, case studies) are skills; a single declared source of truth; skills actually fire when they should.
- **16–20:** All of the above PLUS evidence of the done-twice rule operating (new skills appearing as work patterns repeat), eval/trigger-testing on at least some skills, and no orphan skills.

## 4. Cadence (0–20) — what runs without Joel

- **0–5:** Nothing scheduled; the system only works when Joel is typing.
- **6–10:** Some scheduled tasks exist but several are dead, failing silently, or ignored.
- **11–15:** Daily + weekly rhythms live and producing output files on schedule; spent one-time tasks cleaned up.
- **16–20:** All of the above PLUS closed loops — scheduled output feeds action (a planning brief Joel acts on, an audit that queues builds), not just reports that pile up unread.

Check output folders, not just the task list — a task that "runs" but produced no file in three scheduled cycles is dead.

## 5. Compounding (0–20) — does the system get smarter over time

- **0–5:** No knowledge base, no memory hygiene, no audit history; each session starts cold.
- **6–10:** Knowledge base exists but is a dumping ground — no index, stale notes, secrets or clutter mixed in.
- **11–15:** Vault organized and growing (session notes, wiki, prompt library with index); memory index pruned; audit history accumulating.
- **16–20:** All of the above PLUS visible flywheel: past sessions' outputs being reused (prompts re-run, wiki cited, corrections sticking), and quarterly pruning evidenced.

## Hygiene overrides

These cap scores regardless of anchors:

- **Plaintext secrets in an agent-readable location:** Compounding capped at 8 until resolved. Always the top finding.
- **No declared source of truth for skills (duplication drift):** Capabilities capped at 12.
- **Any scheduled task failing silently for 2+ cycles:** Cadence capped at 12.
