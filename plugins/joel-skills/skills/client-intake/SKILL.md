---
name: client-intake
description: Onboard a new client for Joel by interviewing him and building a client profile from the template. Use this skill whenever Joel says he has a new client, prospect, or lead — "I landed a client", "new client", "onboard this client", "set up a profile for [name]", "add [business] as a client" — or when he pastes client details (an email thread, a brief, discovery-call notes) and wants them turned into a profile. Also use it to update an existing profile after a discovery call or when client preferences change ("update the [client] profile"). Not for creating Joel's own profile or agent personas, and not for mock/sample clients in portfolio pieces — those get invented details, not an intake interview.
---

# Client Intake

Turns "I have a new client" into a filled profile at `clients/<client-slug>.md` in minutes. The profile is the single source of truth every future deliverable for that client reads from — English variant, tone, tools, do's and don'ts.

Template: `clients/client-profile-template.md` (same folder this skill's profiles go to). If the template is missing, recreate the sections listed there from this skill's checklist below.

## How to run intake

1. **Harvest first, ask second.** If Joel pasted anything (email thread, brief, call notes), extract every field you can from it before asking a single question. Never ask for what he already gave.
2. **Interview in small batches** — 3–4 questions at a time, not a 20-question dump. Order of priority:
   - Snapshot: business, location/timezone, contact, preferred channel, **English variant**
   - Working relationship: services in scope, tools + access, deadlines/cadence, approval flow
   - Business context: audience, what they sell, peak season
   - Do's/don'ts, comms style, voice notes
3. **Stop when it's usable, not complete.** Snapshot + services + English variant is enough to save a v1. Mark everything unknown as `[ASSUMPTION: ...]` or leave the placeholder — never invent client details.
4. **Save** to `clients/<client-slug>.md` (lowercase, hyphenated business name). Set Created/Updated dates and status.
5. **Offer the follow-ups**, don't auto-run them: add unanswered questions as a short "Ask the client" list at the bottom of the profile; suggest a kickoff message drafted in Joel's voice.

## Updating an existing profile

- Read the current profile first; change only what changed.
- Log every notable correction or preference in the profile's **Log** section with a date — that's how one-time feedback becomes a standing rule.
- Resolve `[ASSUMPTION]` markers as facts come in.

## Rules

- **English variant is a first-class field.** US by default; confirm early. Every deliverable for this client must match it.
- **Never guess client facts.** A blank field or flagged assumption is correct; an invented detail is a defect.
- Profiles may contain business-sensitive info — keep them in `clients/`, don't copy their contents into other deliverables beyond what's needed.
- Run the qc-gate skill on the finished profile before calling it done.
