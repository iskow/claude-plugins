---
name: discovery-form
description: Produce a short client-facing discovery form that a prospect fills in themselves, then map their answers into a client profile. Use this skill whenever Joel wants to send a lead a questionnaire before a project — "make a discovery form", "send [prospect] a questionnaire", "I need a form for a new lead", "intake form for the client to fill", "what should I ask this prospect", or when a prospect's filled-in answers come back and need turning into a profile/scope. Complements client-intake: client-intake interviews Joel; this collects input directly from the client. Not for Joel's own profile, agent personas, or mock clients in portfolio pieces.
---

# Discovery Form

Gives a prospect a quick 5–15 minute form so we learn their business and the likely feature scope **before** quoting — then turns their answers into a client profile. Two parts: Part 1 (about the business) and Part 2 (what the site/app must do).

Question source of truth: `references/discovery-form-template.md`. Edit questions there, never in an export. If the template is missing, rebuild it from the two-part checklist in that file's structure.

## Two ways this skill runs

**A) Generate a form to send** (most common)
1. Ask Joel which format he wants and confirm the target project type:
   - **Fillable PDF** (default) — professional, self-contained, client types and emails back.
   - **Editable doc** — Word/Docs they type into and return.
   - **Google-Form-ready** — output the questions structured (question + type + options) so Joel pastes them into Google Forms.
2. Load `references/discovery-form-template.md` and render it to the chosen format. Keep every item short-answer, pick-one, or checkbox. Keep the two-part split.
3. If the project has an obvious type (e.g. a booking site), keep the conditional booking questions in Part 2; if clearly irrelevant, trim them and say what you trimmed.
4. Save the export to `prospects/` and hand it over. Don't invent client answers — the form goes out blank.

**B) Process a filled-in form**
1. Read the returned answers (pasted text, PDF, or doc).
2. Map them into a profile via the client-intake skill → `clients/<slug>.md`. Part 1 feeds Snapshot + Business context; Part 2 feeds Services/scope.
3. Flag every blank or ambiguous answer as `[ASSUMPTION: ...]` or an "Ask the client" line — never guess.
4. Summarise the likely feature scope for Joel (what they ticked → what that implies for the build and quote).

## Rules

- **Short answers only.** Every question must be answerable in a word, a tick, or one line. If a question needs a paragraph, cut or split it.
- **Client-ready means send-ready.** Zero typos; match the client's English variant once known (US default).
- **Never pre-fill client answers.** Blank form out; flagged assumptions in.
- **Keep the two files in sync.** The template drives the exports — regenerate exports after editing the template.
- Run the qc-gate skill on the finished form (or scope summary) before calling it done.
