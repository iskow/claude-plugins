---
name: qc-gate
description: Run Joel's QC gate on any deliverable before handing it over. Use this skill whenever a piece of work is about to be returned as finished — a document, report, email draft, brief, summary, spreadsheet, data output, proposal, caption, or any client-facing or portfolio material — even if Joel doesn't say "QC" or "check this". Also use it when Joel asks to review, proofread, QC, sanity-check, or "make this client-ready", and when building agent files that need the canonical QC block. Not for code testing (use tdd/diagnosing-bugs) or deep dataset QC (use data-ops-qc) — but run this gate on those outputs' written summaries too.
---

# QC Gate

The final check before any deliverable leaves the building. Joel's standard is "client-ready means I'd send it as-is" — this gate is how that standard gets enforced instead of assumed.

Run it on the finished draft, not on the plan. Work is not done until every line passes. Failing a line means fix it or flag it — never return silently.

## The gate

1. **Contract** — output matches what was asked for: right sections, right format, right length. If the request implied a format (email, doc, table), the output is in that format.
2. **Traceability** — every factual claim traces to a source (file, URL, command output, client input). Anything untraceable is marked `[ASSUMPTION: ...]`. No invented names, numbers, quotes, or citations — ever.
3. **Numbers** — every figure is recomputed or checked against source, not eyeballed. Totals sum. Dates are real dates.
4. **Zero typos** — proofread the full output. Client-ready means Joel would send it as-is.
5. **English variant** — matches the client's region (US default; UK/AU/NZ when the client profile says so).
6. **Channel format** — chat is casual, email has a subject line and is under ~150 words, docs have headings.
7. **Uncertainty** — if confidence in any part is low, say so in one line at the top: what's uncertain and what would resolve it. Confidence theater fails this gate.
8. **Completeness honesty** — anything skipped, unavailable, or out of scope is listed, not omitted. A gap disclosed is fine; a gap hidden is a defect.

## How to run it

- Check each line against the actual output, not from memory of writing it. Re-read the deliverable top to bottom for line 4; re-derive at least the key figures for line 3.
- When a line fails: fix it if the fix is certain, flag it if it isn't. Joel's rule is "when unsure, flag it — never guess."
- Report the result in one short line, e.g. "QC gate: passed" or "QC gate: 7/8 — flagged one assumption in the pricing section." Don't pad the report; the gate exists to catch problems, not to perform thoroughness.
- The gate is a **floor**, not the whole QC story. Domain-specific checks (data QC, legal review) run *in addition* to it.
- Self-checking isn't certification. For high-stakes deliverables, suggest a second pass in a fresh context or by a checker agent.
- If the same line keeps failing across outputs, the fix belongs upstream — in the prompt, agent file, or template that produced them — not just in each output.

## Canonical block for agent files

This skill is the single source of truth for the gate. When building or updating an agent whose output could reach a client, paste the block below **verbatim** as its last section before any output contract. Don't paraphrase it per agent — one canonical version means one place to improve it.

```markdown
## QC Gate (run before returning any output)

Work is not done until every line passes. Failing any line means fix it or flag it — never return silently.

1. **Contract** — output matches this agent's declared output contract exactly: right sections, right format, right length.
2. **Traceability** — every factual claim traces to a source (file, URL, command output, client input). Anything untraceable is marked `[ASSUMPTION: ...]`. No invented names, numbers, quotes, or citations — ever.
3. **Numbers** — every figure is recomputed or checked against source, not eyeballed. Totals sum. Dates are real dates.
4. **Zero typos** — proofread the full output. Client-ready means Joel would send it as-is.
5. **English variant** — matches the client's region (US default; UK/AU/NZ when the client profile says so).
6. **Channel format** — chat is casual, email has a subject line and is under ~150 words, docs have headings.
7. **Uncertainty** — if confidence in any part is low, say so in one line at the top: what's uncertain and what would resolve it. Confidence theater fails this gate.
8. **Completeness honesty** — anything skipped, unavailable, or out of scope is listed, not omitted. A gap disclosed is fine; a gap hidden is a defect.
```
