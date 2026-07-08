# SOP Template

Section-by-section skeleton for the Markdown master. Sections marked *(optional)* are dropped when they don't apply — never leave an empty heading. Order is fixed; readers learn where to look.

---

```markdown
# SOP: <Process Name>

| Document control | |
|---|---|
| Version | 1.0 |
| Owner | <role, not a person's name> |
| Effective date | <YYYY-MM-DD> |
| Next review | <YYYY-MM-DD — default: effective date + 6 months> |
| Status | Draft / Active / Retired |

## 1. Purpose

One or two sentences: why this procedure exists and the outcome it guarantees.
Not a description of the steps — the *reason* the steps matter.

## 2. Scope

- **Applies to:** <situations, systems, data types, clients this covers>
- **Does not apply to:** <explicit exclusions — the #1 source of misuse is
  someone running an SOP outside its scope>

## 3. Roles & responsibilities

| Role | Responsibility in this SOP |
|---|---|
| <Role> | <what they do / approve / verify> |

Single-person processes still name the role ("Executor") — SOPs outlive staffing.

## 4. Definitions *(optional)*

Only terms a first-time executor wouldn't know. Acronyms spelled out once here.

## 5. Prerequisites

Everything that must be true BEFORE step 1: access/accounts, tools installed,
files received, prior SOPs completed. Written as a checklist:

- [ ] <prerequisite>

## 6. Process overview *(include when there's a flowchart)*

<Mermaid flowchart here — see references/flowchart-and-output.md>

One-paragraph plain-text summary under the chart for anyone reading a
format where the chart didn't render.

## 7. Procedure

<The chosen format: simple steps / hierarchical / checklist — see SKILL.md table.>

Hierarchical example:

### Phase 1 — <Phase name>

1. <One action, verb first. Exact clicks, commands, field values, naming
   conventions.>
2. <Next action.>
   > ⚠️ **Warning:** <embedded at the hazardous step, not collected at the end>
3. <Action with a verification:> Confirm <observable result>. If not, see
   §8 <exception name>.

**Checkpoint:** <what must be true before starting Phase 2>

## 8. Exceptions & escalation

| If this happens | Do this | Escalate to |
|---|---|---|
| <common failure> | <recovery steps or pointer> | <role, when> |

Rule of thumb: anything the executor can't resolve inside <X minutes/attempts>
gets escalated — give the number.

## 9. Quality check

Final verification checklist — how the executor proves "done" is done right:

- [ ] <observable pass/fail criterion>

## 10. References *(optional)*

Related SOPs, tool docs, client profile, source recordings/transcripts.

## 11. Revision history

| Version | Date | Author (role) | Change |
|---|---|---|---|
| 1.0 | <date> | <role> | Initial release |
```

---

## Notes for the writer

- **Stranger test per section:** Purpose tells them *why they should care*, Scope stops wrong use, Prerequisites prevent mid-process dead ends, Quality check makes "done" objective.
- **Verification beats instruction.** The strongest steps pair an action with its observable result ("Click Export. A green 'Job queued' banner appears."). Add these wherever the interview surfaced a way to go wrong silently.
- **Time estimates** *(optional but valuable)*: add expected duration per phase when Joel knows it — helps executors spot when something is off ("this normally takes 10 minutes, it's been an hour").
- **Screenshots:** if Joel supplied them, reference by filename at the exact step (`![Step 3 — Processing job screen](img/step-3.png)`) and keep them in an `img/` folder beside the SOP.
