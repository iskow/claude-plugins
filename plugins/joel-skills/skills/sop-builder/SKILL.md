---
name: sop-builder
description: Turn a process into a well-written SOP — interview Joel grill-style or digest his notes/transcript, pick the right SOP format, add a Mermaid flowchart when the process branches, and deliver as HTML, PDF, or Word. Use whenever Joel wants a process documented, even without the word "SOP" — "write an SOP", "document this process", "turn this into a procedure / runbook / checklist / how-to", "standardize how we do X", or when he pastes process notes, a call transcript, or a tool walkthrough to formalize. Works for client deliverables and Joel's own internal ops. Not for stress-testing a plan (use grilling), portfolio write-ups (case-study), or one-off task lists.
---

# SOP Builder

Extract a process from Joel's head (or his notes), then write it up so someone who has never done the task can follow it without asking questions. That's the bar: **a competent stranger could execute this SOP unsupervised.**

## Step 0 — Frame it (always first)

Ask these up front, in one batch (they're setup, not the interview):

1. **Who executes this SOP?** (new VA, client's staff, Joel-in-6-months, technician…) — sets reading level and how much context to include.
2. **Client deliverable or internal?** If client: read `clients/<client-slug>.md` first, match their English variant and any branding. If internal: US English, no frills.
3. **Input mode** — does Joel want to be interviewed from scratch, or does he have raw material (notes, transcript, screenshots, existing doc) to dump first?
4. **Output format** — HTML, PDF, Word doc, or just Markdown. Default: Markdown master + whichever one polished format fits the audience (client → PDF or Word; internal/shareable link → HTML).

## Mode A — Interview (from scratch)

Grill-style rules apply: **one question at a time**, wait for the answer, offer a recommended answer with each question when you can infer one. Never fire a wall of questions.

Walk the process in this order — it mirrors how SOPs are structured, so nothing gets missed:

1. **Trigger & outcome** — what starts this process, and what does "done" look like? How do you verify it's done correctly?
2. **Scope** — when does this SOP apply, and when does it explicitly *not* apply?
3. **Roles** — who does each part? One person or handoffs?
4. **Prerequisites** — access, tools, accounts, files, prior steps that must exist before step 1.
5. **The happy path** — walk the steps in order. For each step, probe for the *how*: exact clicks, commands, field values, naming conventions. "Process the data" is not a step; "In Relativity, go to Processing > New Job and select the workspace" is.
6. **Decision points** — at each step: can anything branch here? What decides which way to go? (These become the flowchart.)
7. **Exceptions & failure** — what goes wrong most often? How do you recover? When do you stop and escalate, and to whom?
8. **Warnings** — any step where a mistake is expensive or irreversible? (These get embedded at that step, never in a blob at the end.)
9. **Cadence & ownership** — how often is this run? Who owns keeping the SOP current, and when should it be reviewed?

Stop interviewing when you can pass the stranger test, not when the list is exhausted. If Joel says "I don't know" — mark it `[TO CONFIRM: …]` and move on; never guess.

## Mode B — Draft-first (from a dump)

1. Read everything Joel provided.
2. Draft the full SOP immediately, marking every gap inline as `[NEEDS INPUT: what's missing]`.
3. Show the draft, then interview **only the gaps**, one at a time, Mode A style.

This is faster and respects the material he already has — don't re-ask what the dump answers.

## Pick the right format (don't default to one)

| Process | Format |
|---|---|
| Short, linear, ≤10 steps, few decisions | Simple numbered steps |
| Long or multi-phase (>10 steps) | Hierarchical — phase headings, numbered sub-steps |
| Order doesn't matter; completeness does (inspections, closings, handoffs) | Checklist |
| Branches on conditions (troubleshooting, escalations, intake) | Flowchart + supporting steps |

Formats combine: a hierarchical SOP with a flowchart overview and a final QC checklist is common and good. Say which format you picked and why — one line.

## Writing rules (non-negotiable)

- **One action per step.** If a step has "and", split it.
- **Active voice, action verb first.** "Verify the totals", not "The totals should be verified."
- **Banned vagueness:** "periodically", "as needed", "typically", "appropriate", "etc." Give numbers, names, and criteria instead.
- **Modal discipline:** *must* = mandatory. *may* = executor's choice. Avoid *should* — it's ambiguous; decide whether it's must or may.
- **Warnings sit at the step** where the hazard occurs, formatted to be seen: `> ⚠️ **Warning:** …`. A caution ignored at step 12 doesn't belong on page 1.
- **Name the roles**, not people: "Data Ops Specialist", not "Joel". People change; roles don't.
- Plain words. Define jargon and acronyms in Definitions on first use.
- Every SOP carries a **document control block** (version, owner, effective date, next review date) — an SOP without a review date is already rotting.

Full section-by-section template: `references/sop-template.md`.

## Flowchart

Include a Mermaid flowchart when the process has decision points; skip it for purely linear processes (say so). Patterns, syntax constraints, and rendering commands: `references/flowchart-and-output.md`.

## Deliver

1. Write the Markdown master first — it's the source of truth.
2. Produce the requested format(s) per `references/flowchart-and-output.md` (HTML self-contained; PDF via the pdf skill; Word via the docx skill — read those SKILL.md files before building).
3. Save to `sops/` — client SOPs under `sops/<client-slug>/`, internal under `sops/internal/`. Filename: `sop-<process-slug>.md` (+ same-name .html/.pdf/.docx).
4. **Run the qc-gate skill on the finished SOP before handing it over.** Extra SOP-specific check: pick a random step and ask "could a stranger execute this line?" If not, it fails.
5. Offer a **walkthrough test**: the real QC of an SOP is someone executing it. Suggest Joel (or the client's person) run the process following only the document and log where they stall — then fold fixes into v1.1.
