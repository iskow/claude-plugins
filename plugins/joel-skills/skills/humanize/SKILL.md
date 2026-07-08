---
name: humanize
description: Strip AI-sounding patterns from text so it reads like a person wrote it. Use this skill whenever text is meant to be read by a client or the public and might smell like AI — customer service / client emails, website copy, landing pages, captions, proposals, portfolio pages, chat replies sent on a client's behalf — even if Joel doesn't say "humanize". Triggers include "this sounds like AI", "make it sound human/natural", "de-AI this", "too robotic", "clean up this draft", or Joel pasting AI-generated text he plans to send. Also run it proactively as a voice pass on any outward-facing deliverable before qc-gate. Not a fact-checker (that's qc-gate — run humanize first, then qc-gate) and not for code or internal scratch notes.
---

# Humanize

AI text has specific, named tells. This skill finds them and rewrites them. It is a voice pass, not a fact pass: qc-gate checks that the work is *right*; humanize checks that it *sounds like a person*. On client-facing work, run humanize first, then qc-gate.

Adapted from the MIT-licensed [blader/humanizer](https://github.com/blader/humanizer) skill, which is built on Wikipedia's "Signs of AI writing" guide, and merged with Joel's own writing rules so the two never conflict. Where they differ, Joel's rules win.

## Process

1. Read the input and mark every pattern below that appears.
2. Rewrite. Don't just delete — replace the AI-ism with a natural alternative and keep everything the original says. Same meaning, same coverage, same register.
3. Second pass: ask "what still makes this read as AI-generated?" and fix that too.
4. Return the final text plus a short list of what changed (pattern names, not a lecture).

If Joel provides a writing sample or the text is for a specific client, match that voice — sentence length, formality, quirks. A client profile in `clients/` may specify the English variant; check it.

## Joel's baseline (always on)

These come from CLAUDE.md and apply before any pattern below:

- Lead with the point or the ask in the first line.
- Banned words: "genuinely", "honestly", "straightforward", "utilize" (use "use").
- Banned phrases: "I hope this email finds you well", "Please do not hesitate to reach out", "As per my last email".
- No padding. Concise is correct, not lazy.
- US English by default; UK/AU/NZ only when the client profile says so.
- Emails: subject line, under ~150 words, one clear next step.

## Words to kill

Swap these for plain words whenever they appear. They spike in post-2023 text and cluster together:

**Verbs:** delve, leverage, foster, harness, underscore, showcase, highlight (as verb), enhance, streamline, elevate, empower, unlock, garner, navigate (figurative), embark
**Nouns:** tapestry, landscape (abstract), realm, ecosystem (non-biology), testament, journey (figurative), synergy, interplay, intricacies, game-changer
**Adjectives:** pivotal, crucial, vital, robust, seamless, vibrant, dynamic, cutting-edge, groundbreaking, transformative, comprehensive, innovative, stunning, breathtaking, renowned, key (as adjective)
**Connectors when piled up:** additionally, furthermore, moreover, consequently

One of these alone is not a crime. Three in a paragraph is a confession.

## Structures to break

**1. "It's not just X, it's Y" / "Not only... but also".** Say the actual claim once.
> Before: It's not just a website, it's a growth engine.
> After: The site is built to bring in bookings, not just look good.

**2. Rule of three.** AI forces everything into triplets ("innovation, inspiration, and insights"). Use two items, or four, or one — whatever is true.

**3. Tacked-on "-ing" analysis.** Phrases like "...highlighting the importance of", "...ensuring a seamless experience", "...reflecting our commitment to" glued to the end of sentences. Cut the clause or make it a real sentence with a real fact.

**4. Copula avoidance.** "serves as", "stands as", "boasts", "features", "offers" instead of "is" and "has". Use is/are/has.

**5. False ranges.** "From X to Y" where X and Y aren't on a scale ("from bold flavors to unforgettable moments"). List the actual things.

**6. Inflated significance.** "marks a pivotal moment", "a testament to", "setting the stage for", "reflects a broader trend". State the fact; drop the ceremony.

**7. Vague authority.** "Experts agree", "studies show", "industry reports suggest" with no source. Name the source or cut the claim. (This overlaps qc-gate's traceability rule — flag it in both passes.)

**8. Fake-profound framing.** "The real question is...", "At its core...", "What really matters is...", "Here's the thing:". The sentence after these is always just a normal point. Say the normal point.

**9. Signposting.** "Let's dive in", "Here's what you need to know", "Without further ado". Do the thing instead of announcing it.

**10. Synonym cycling.** The protagonist / the main character / the central figure / the hero — all one person. Repeat the noun or use a pronoun; repetition is human.

**11. Manufactured punchlines.** Runs of short dramatic fragments ("No fluff. No filler. Just results.") One short sentence lands a point. Three in a row is a template.

**12. Aphorism formulas.** "X is the language of Y", "X becomes a trap", "the currency of trust". Replace with the concrete claim underneath.

**13. Generic upbeat endings.** "The future looks bright", "Exciting times ahead", "your journey starts here". End with a fact or a next step.

## Formatting tells

- **Em and en dashes: none in the final text.** Most reliable single tell. Replace with a period, comma, colon, or parentheses — in that order of preference.
- **Bolded-header bullet lists** ("**Speed:** Our platform is fast...") — rewrite as prose or plain bullets.
- **Mechanical boldface** on random key phrases — cut it.
- **Emojis** decorating bullets or headings — cut unless the channel calls for them (casual chat, sometimes social captions).
- **Title Case Headings** — sentence case.
- **Curly quotes** — straight quotes, when other tells are also present.
- **Heading + one-line restatement of the heading** before the real content — delete the warm-up line.

## Email-specific tells

Everything above, plus:

- Chatbot residue: "Certainly!", "Great question!", "I hope this helps", "Let me know if you'd like me to expand". If it reads like a reply *to* an AI prompt, it's residue — cut it.
- Sycophancy: "You're absolutely right", "That's an excellent point". State the substance without the applause.
- Over-hedging: "could potentially possibly". One qualifier max, and only if the uncertainty is real.
- Filler: "In order to" → "To". "Due to the fact that" → "Because". "At this point in time" → "Now". "has the ability to" → "can".
- The perfect five-paragraph reply to a two-line question. Match the sender's length and energy.

## Website-copy-specific tells

- Promotional autopilot: "nestled in the heart of", "boasts a rich heritage", "commitment to excellence", "must-visit". Replace with specifics — what it costs, where it is, what you get, since when.
- Every section ending in a benefits triplet.
- "Whether you're a [persona A], [persona B], or [persona C]..." — pick the real audience and speak to them.
- Headline formulas: "Unlock/Elevate/Transform your X". Say what the product does in plain words.
- Specifics are the fix: numbers, names, dates, prices. AI rounds off details; humans hoard them.

## What NOT to flag

Don't gut legitimately good writing. These are fine on their own:

- Polish and correct grammar. Professional ≠ AI.
- Formal vocabulary that isn't on the kill list.
- A single em dash in someone's existing copy, one "however", one short punchy sentence.
- Specific, odd, hard-to-fabricate detail — that's evidence of a human. Keep it.
- Mixed feelings, asides, self-corrections, dated slang. Keep them.

Look for clusters. One tell means nothing; five tells in two paragraphs means rewrite.

## Output

Return:

1. The rewritten text, ready to send (channel-formatted: subject line if email, headings if doc).
2. "Changed:" — one line per pattern fixed, e.g. "Changed: killed 4 vocab words, broke 2 rule-of-threes, removed em dashes, cut chatbot sign-off."
3. If anything was ambiguous (voice, audience, English variant), one flag line — never a silent guess.

Then hand off to qc-gate if the piece is a deliverable.
