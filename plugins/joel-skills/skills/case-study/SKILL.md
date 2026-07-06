---
name: case-study
description: Turn one of Joel's finished builds into a portfolio case study using the template. Use this skill whenever Joel wants a build written up as a portfolio piece — "write a case study", "turn [project] into a portfolio piece", "add this to my portfolio", "portfolio write-up for [build]" — or when he says a project is finished and asks what to do with it. Also use it to update an existing case study when a project gets new results or proof. Not for client deliverables about the client's own business, not for resumes or LinkedIn profile text, and not for the Weekly Digest — those have their own formats.
---

# Case Study

Turns a finished build into a one-page portfolio piece at `portfolio/<project-slug>.md`. Case studies are sales assets: they exist so a prospective client reads one and thinks "I want that outcome."

Template: `portfolio/case-study-template.md`. If it's missing, recreate the sections from the checklist below.

## How to run it

1. **Harvest first, ask second.** Read the project's own docs before asking anything — build plans and notes in `projects/`, the code or output itself, chat context if the build just finished. Extract: what it does, tools, key decisions, anything measurable. Never ask for what the workspace already says.
2. **Interview in small batches** — 3–4 questions max at a time. Priority order:
   - The problem: whose pain, in their words, and what it cost them
   - Results: real numbers (time saved, error rate, volume) — or what's honestly demonstrable
   - Proof: screenshots, demo video, link — what exists, what needs capturing
   - The service bridge: which of Joel's offers this sells
3. **Draft in Joel's voice.** Concise, plain words, lead with the outcome. Write for a non-technical business owner, not a developer.
4. **Save** to `portfolio/<project-slug>.md` (lowercase, hyphenated). Set dates and status.
5. **Flag the gaps**, don't fill them: missing proof or metrics become a short "To capture" list at the bottom of the draft, not invented content.

## Rules

- **Never invent metrics or client quotes.** A case study with one real number beats one with five fake ones. Unverified claims get `[ASSUMPTION: ...]` or go in "To capture".
- **Sample vs client work is a first-class distinction.** Self-initiated builds are labeled "Sample project" in the Snapshot — no implying a paying client existed. Mock-client details (names, scenarios) are fine if clearly framed as the scenario the sample solves.
- **Client confidentiality.** For real client work: no confidential data, and note whether Joel has permission to publish before status moves past draft.
- **One page.** If it runs long, cut the build log details — keep problem, decisions, results, proof.
- Delete the "Reuse notes" section from any version that leaves the workspace.
- Run the qc-gate skill on the finished case study before calling it done.
