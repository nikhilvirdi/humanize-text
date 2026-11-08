---
name: humanize-text
description: "Rewrite machine-sounding prose into natural, human-written text while preserving meaning, facts, and voice. Use whenever the user asks to \"humanize\" text, remove \"AI writing\" tells, make something \"sound less like ChatGPT,\" fix robotic/formulaic prose, or edit a draft so it doesn't read as AI-generated. This is an editing task under a strict fidelity constraint, not a free rewrite — and it ends with a mandatory mechanical self-audit, not just a stylistic pass."
---

# Humanize Text

Rewrite machine-sounding prose into natural, skilled human writing while
preserving everything that matters: meaning, facts, intent, tone, voice,
technical precision, and logical structure. This is an editing task under a
fidelity constraint, not a free rewrite. Prefer the smallest set of precise
edits that removes the machine signature.

This skill is built from an empirical field guide to how AI writing is
detected (Wikipedia's "Signs of AI writing" and "Signs of AI-generated
comments" projects, cross-referencing peer-reviewed studies). The guiding
insight: the well-known "AI tells" are symptoms of underlying writing
defects — vagueness, puffery, hedged nothing, formulaic scaffolding,
mechanical rhythm. Removing a tell by swapping one word for another, while
leaving the defect intact, accomplishes nothing and can make the text worse.
Fix the defect; the tell disappears on its own.

**This version is stricter than a normal editing pass.** A prior version of
this skill still let mechanical tells like spaced em dashes leak through
because it treated the catalog below as things to "keep in mind" rather than
things to actively hunt down and eliminate. That doesn't work — a model
editing under stylistic guidance defaults back to its own habits unless it is
forced to check its own output against a literal list. Step 6 (Mandatory
mechanical self-audit) is not optional and is not a formality. Do not skip it,
do not summarize it, actually run it against the actual text you produced.

## Core objectives (in priority order)

1. **Fidelity first.** Never alter facts, claims, numbers, names, citations,
   quotes, code, or the author's intended meaning and stance. If humanizing
   and fidelity conflict, fidelity wins and you leave the phrasing alone.
2. **No fabrication.** AI padding often replaces a specific fact with generic
   praise. Do not reverse this by inventing specifics to sound human. Cut the
   padding or leave a neutral statement; never manufacture detail.
3. **Remove genuine machine signatures** — the patterns catalogued below —
   because each corresponds to a real quality defect.
4. **Improve rhythm and readability** through sentence-length variation,
   natural cadence, and plain diction — without sterilizing the prose.
5. **Preserve voice, register, and precision.** Keep domain terminology,
   required formatting, and the author's tone. Match, don't flatten.
6. **Prefer subtle, high-precision edits** over aggressive rewriting. Change
   what carries the machine signal; leave clean sentences untouched.
7. **Pass your own output through the mechanical self-audit (Step 6) before
   delivering it.** A humanize pass that reintroduces em dashes, curly
   quotes, or "not just X but Y" while removing them elsewhere has failed,
   regardless of how good the prose reads.

## The prime directive: fidelity constraints (never violate)

- Do not add, remove, or change any factual claim, statistic, date, name,
  attribution, or logical relationship.
- Do not invent examples, specifics, sources, or transitions that assert
  content not present in the original.
- Do not change the author's position, certainty level, or emphasis. If the
  original hedges, keep it hedged; if it commits, keep it committed.
- Never touch text inside direct quotations, code blocks, math, citations,
  proper nouns, or user-specified required formatting — except to fix an
  obvious mechanical artifact (see Edge cases).
- Preserve the document's structure and section order unless the user
  explicitly asks to restructure.
- When unsure whether an edit preserves meaning, make the smaller edit or
  make none. Under-editing is safe; semantic drift is not.

## Decision hierarchy (apply to every candidate edit)

For each thing you're tempted to change, walk this ladder and stop at the
first "no":

1. Does the edit preserve meaning, facts, intent, and tone exactly?
   No → don't edit.
2. Is the target an actual machine signature or defect (per the catalog),
   rather than legitimate human/technical usage? No → leave it (see
   "Preserve" section — over-correction is itself a tell).
3. Can the defect be fixed by cutting or minimally reshaping, rather than
   rephrasing wholesale? If yes, prefer the minimal fix.
4. Does the fix require inventing content to fill a gap? Yes → don't invent;
   cut instead, or leave a shorter neutral statement.
5. After the edit, is the sentence something a careful human writer would
   actually produce (not just "differently AI")? No → revise or revert.

## Catalog of machine signatures → what to do

Each entry: the pattern, why it's a defect, and the transformation.

### 1. Puffery about significance, legacy, and broader trends
Pattern: unearned statements that the subject "stands as / serves as a
testament to / marks a pivotal moment / reflects a broader shift / leaves an
indelible mark / plays a vital role in the evolving landscape," or that
situate a mundane subject inside grand "debates" and "discussions." Includes
hedging preambles that admit the subject is minor and then talk about its
importance anyway.
Fix: delete the inflation. Keep only claims the text actually supports.
"marks a pivotal moment in the evolution of regional statistics" → (cut, or)
"was established in 1989." Do not replace one grand phrase with a subtler
one.

### 2. Superficial "-ing" analysis tails
Pattern: a trailing present-participle clause that editorializes: "…,
highlighting its significance," "…, reflecting broader trends," "…, ensuring
reliability," "…, contributing to the region's development," "…, showcasing
its importance." Newer models attach these to named sources ("Ebert
highlighted the lasting influence") regardless of whether the source says
anything of the kind — treat that as worse, not better, since it's a
fabricated attribution riding on a real name.
Fix: cut the tail. If it contains a real, sourced fact, promote it to a
plain independent clause instead of an editorial flourish.

### 3. Promotional / advertisement tone (peacock terms)
Pattern: "boasts," "vibrant," "rich cultural heritage," "nestled in the
heart of," "renowned," "groundbreaking," "a diverse array of," "state-of-
the-art," "seamlessly," "commitment to excellence."
Fix: replace with neutral, specific description or cut. "boasts a
population of 56,998" → "has a population of 56,998." Marketing copy that is
supposed to be promotional keeps its earned, specific selling points — only
the generic, hollow puffery goes.

### 4. Canned emphasis on notability, attribution, and media coverage
Pattern: listing outlets by type ("trade publications," "regional media
outlets") to prove notability rather than to support a specific claim;
"maintains an active [social media] presence"; attributing trivial or
uncontroversial facts to a named outlet mid-sentence when a human writer
would just cite it, if at all.
Fix: cut the notability-signaling; keep a plain citation only where a claim
actually needs it.

### 5. Vague attribution / overgeneralized opinion (weasel wording)
Pattern: "experts argue," "observers have noted," "industry reports,"
"it is widely regarded," "several sources," "critics say" — with one or zero
citations backing it; "such as" fronting a list implied to be non-exhaustive
when the source lists exactly those items; inflating one or two sources into
"scholars" or "researchers" broadly.
Fix: if the text names a real source, attribute to that source specifically.
If it doesn't, remove the false attribution and state the claim plainly, or
flag it for the user to source. Never upgrade "one study" into "studies
show."

### 6. "Challenges / Future prospects" outline endings
Pattern: "Despite its success, X faces several challenges, including…" and
speculative "Future Outlook" closers with vaguely upbeat forecasts. This is
about the rigid template, not the mere mention of a real, specific
challenge.
Fix: remove speculative filler. Keep only concrete, sourced challenges or
plans actually present in the text.

### 7. Section-summary and disclaimer scaffolding
Pattern: "In summary," "In conclusion," "Overall," "It is important to note
that," "It's worth noting," "As of my last update," "based on the available
information," "while specific details are limited/scarce…," speculative
filler about what something "likely" is when the source doesn't say.
Fix: delete. A conclusion can simply state its point; a note can simply be
stated. Never speculate about what unknown information "probably" is.

### 8. "AI-vocabulary" density (context-gated)
Pattern: heavy co-occurrence of: delve, underscore, showcase, testament,
tapestry, landscape (abstract), pivotal, crucial, vital, robust, foster,
garner, boast, intricate, interplay, meticulous, seamless, enhance,
leverage, navigate (figurative), realm, embark, illuminate, align with,
bolstered, and sentence-initial Additionally / Moreover / Furthermore /
Notably.
Fix: substitute the plainest accurate synonym or restructure. utilize→use,
foster→encourage/build, garner→get/earn, showcase→show, underscore→
stress/show, delve into→examine/look at, leverage→use, robust→
strong/reliable.
Gate: only strip the rhetorical use. Keep legitimate senses — a
cryptographic key, a literal underscore character, a physical landscape,
statistical robustness, an interplay that is genuinely the technical term.
Don't vandalize domain language to hit a word list. One or two of these
words in isolation is not a tell; density and co-occurrence is.

### 9. Copula avoidance
Pattern: AI dodges "is/are/has" in favor of "serves as / stands as /
represents / functions as / features / offers / maintains / operates as,"
and opens leads with "X refers to…" as if defining a term rather than
describing the thing — especially for article titles that aren't proper
nouns.
Fix: restore plain "is/are/has" where it reads naturally. "The gallery
serves as the exhibition arm" → "The gallery is the exhibition arm."
"Kestrel refers to a small falcon that…" → "The kestrel is a small falcon
that…"

### 10. Negative parallelism
Pattern: "not just X, but Y," "it's not X — it's Y," "not only… but
also…," "X isn't about A; it's about B," "no gimmicks, no filler, just
results," and the reversed form "X rather than Y" used as a rhetorical
contrast rather than a real distinction.
Fix: state the positive claim directly. Keep a genuine contrast only where
it carries real information; convert the rest to plain assertion. Aim to
leave at most rare, purposeful uses. This pattern is especially common —
and especially conspicuous — in argumentative or persuasive writing (talk
pages, comments, appeals); scrutinize those contexts hardest.

### 11. Rule of three
Pattern: reflexive triads — "clear, concise, and compelling"; "identity,
authenticity, and meaning"; three parallel clauses per sentence; three
bullet points where two would do.
Fix: cut to the one or two items that carry distinct meaning. Vary list
lengths across the passage. Humans use triads occasionally — keep the ones
that are real and earned; break the mechanical ones.

### 12. Elegant variation
Pattern: needless synonym-swapping to avoid repeating a word ("the film…
the picture… the cinematic work…"), driven by a repetition-penalty reflex.
Fix: use the plain, consistent term. Repeating "the film" is fine and more
human than three synonyms. Note: if you are humanizing multiple separately-
generated chunks of text, this pattern may not apply within each chunk —
don't force artificial repetition where the original had none.

### 13. Mechanical boldface and inline-header lists
Pattern: every list item is "Bold header: description"; key phrases bolded
throughout in a slide-deck "key takeaways" way; unnecessary small tables
that could be one or two prose sentences.
Fix: convert decorative lists to prose where the items read naturally as a
sentence; keep genuine enumerations as clean lists without the bold-colon
template. Remove emphasis bolding that isn't marking a defined term. Keep
bold only where it does real work.

### 14. Em-dash overuse and punctuation monotony
Pattern: frequent " — " (spaced em dash) or " -- " (double hyphen used as a
dash) where commas, parentheses, or periods belong; the same punch-clause
rhythm repeated sentence after sentence.
Fix: vary punctuation — some commas, some parentheses, some full stops.
This is a hard-ban pattern, not a matter of degree: see Step 6, item 1. Do
not eliminate em dashes entirely — humans use them, tight with no spaces
(—), occasionally. The problem is the spaced variant, the double-hyphen
substitute, and overuse, not the character itself.

### 15. Title Case headings, heading-level skips, decorative rules
Pattern: "Impact And Legacy" title-case headers; jumping from H1 to H3;
horizontal rules inserted before every heading; emoji-decorated headers.
Fix: use sentence case unless the document's established style is title
case; keep heading levels sequential; remove ornamental rules and heading
emoji. Match the surrounding document's real convention.

### 16. Curly-quote/apostrophe inconsistency and stray markup
Pattern: mixed straight/curly quotes; curly apostrophes in contractions;
markdown artifacts (asterisks for bold, `#` headers) pasted into a
non-markdown target; citation-artifact junk (stray `contentReference`,
`oai_citation`, `utm_source=chatgpt.com`, `citeturn0search0`,
`【85†L261-269】`, bracketed index tokens, `[cite: 1]`).
Fix: normalize quote/apostrophe style consistently to the target's
convention (straight unless the target explicitly uses curly, e.g. Chicago-
style typesetting); strip pasted markup artifacts and tracking junk
entirely — these are not stylistic, they're broken output and must go
regardless of fidelity concerns, since they were never part of any human
meaning to begin with.

### 17. Canned conversational scaffolding (chat residue)
Pattern: "Certainly!", "Of course!", "Great question!", "I hope this
helps", "Let me know if you'd like…", "Would you like me to…", "Here's a…",
"In this section, we will discuss…", subject-line headers ("Subject: …"),
placeholder templates ("[Your Name]", "INSERT_URL_HERE").
Fix: delete entirely. The finished text should not address a reader as an
assistant or contain prompt/response residue.

### 18. Canned assurance, hedging, and wikilawyering in first-person or persuasive text
Pattern (comments, appeals, emails, talk-page-style writing): "I am
committed to…", "I assure you…", "this aligns with the guidelines", "I'm
happy to address any concerns", "I welcome any feedback", "let's focus on
the substance instead of…", "without concrete evidence…", invoking rules or
policies as an abstract formal whole rather than a specific point.
Fix: cut the boilerplate; keep only concrete, specific points the author is
actually making. This register is one of the densest sources of AI tells in
non-encyclopedic text — apply extra scrutiny to persuasive or defensive
first-person writing.

## What to PRESERVE — do not "correct" these (over-correction is a tell)

Many features are not reliable AI markers, and human writing has signatures
AI lacks. Restoring or keeping these makes text more human, not less:

- Plain copulas and plain verbs: "there is," "it has," "she wrote," "he
  moved," "they used," "it died." Keep them.
- Superlatives and definite claims that are supported: "the first," "the
  only," "one of the largest." AI avoids these; humans use them. Don't
  hedge them into mush.
- Mild hedges and intensifiers: "very," "perhaps," "roughly," "tends to,"
  "a bit." A little is human. Don't scrub every one.
- Mild wordiness / natural connective tissue: "as a result of," "in order
  to," "the fact that," "a part of." Don't compress every sentence to
  telegram concision; that sterility is its own machine tell.
- Occasional em dashes (tight, unspaced), occasional triads, occasional
  transitions. The tic is the reflex and density, not any single instance.
- Formal, academic, or "fancy" register when the context calls for it.
  Formal ≠ AI.
- Correct grammar, correct formatting, and consistent style. Don't
  introduce errors to "seem human." Never inject typos, slang, or fake
  casualness as a humanizing device.
- Technical terminology and required structure. Keep every domain term and
  any format the user asked for (tables, headings, code) intact.
- Perfect grammar and formal/mixed registers on their own are not tells —
  don't flatten skilled or precise writing just because it's clean.

**Golden rule of restraint:** if a sentence is already clean, specific, and
natural, leave it exactly as is. A humanized document usually keeps most of
its sentences.

## Workflow

1. **Read the whole text first.** Identify genre (encyclopedic, technical
   doc, marketing, email, comment, narrative), register, and the author's
   voice. Note any user-specified constraints (format, length, tone).
2. **Diagnose, don't reflex-edit.** Scan for the signatures above and mark
   them. Distinguish real defects from legitimate usage using the context
   gate.
3. **Edit by the decision hierarchy**, smallest change first. Cut padding,
   restore plain verbs, break mechanical parallelism/triads, de-inflate
   puffery, strip scaffolding, vary rhythm. Preserve everything in the
   Preserve list.
4. **Re-read for fidelity.** Confirm no fact, claim, number, attribution,
   stance, or nuance changed. Confirm nothing was invented.
5. **Re-read for naturalness.** Confirm the result reads as genuine human
   prose with varied sentence length and plain diction — not merely
   "differently AI," and not over-corrected into sterile choppiness.
6. **Run the mandatory mechanical self-audit below.** This is a distinct,
   final pass over your own draft output — not a repeat of step 5. Do it
   even if you're confident the draft is clean. Fix any hits, then re-scan
   until it comes back clean.
7. Run the QA checklist. Fix any failures. Then deliver.

For long documents, work section by section but keep the whole-document
voice consistent (don't let elegant variation creep back in across
sections).

## Step 6 in detail: Mandatory mechanical self-audit

Before delivering, literally search your own draft for each of the
following. Treat every hit as a required fix, not a judgment call — these
are the patterns that leak through even when the prose otherwise "sounds"
human, and they are the fastest way for a reader to peg text as AI-written.
Go down the list in order.

1. **Spaced em dash or double-hyphen-as-dash.** Search for " — " and " -- "
   (dash or double hyphen with a space on either side). Every hit: replace
   with a comma, parenthesis, colon, period, or a tight unspaced em dash,
   whichever a human editor would actually reach for in that spot. This is
   the single most common failure mode of this skill — check it first,
   check it last, and don't rationalize a hit as "fine because it's just
   one."
2. **Curly quotes and curly apostrophes** ( " " ' ' ) in a plain-text or
   non-Word/non-Chicago target. Normalize to straight (" ') unless the
   target format is established as curly.
3. **Negative-parallelism constructions**: "not just X, but Y," "not
   only… but also," "it's not X — it's Y," "X rather than Y" used
   rhetorically. Every hit gets converted to a direct positive statement
   unless the contrast is genuinely load-bearing.
4. **Rule-of-three padding**: any sentence with three parallel adjectives,
   clauses, or list items where one or two would say the same thing.
   Cut to what's earned.
5. **"-ing" analysis tails** on the ends of factual sentences
   ("…, highlighting its importance," "…, ensuring reliability," "…,
   reflecting broader trends"). Cut the tail or promote real content to its
   own sentence.
6. **AI-vocabulary density check**: reread your draft's verbs and
   adjectives specifically for delve, underscore, showcase, testament,
   tapestry, pivotal, crucial, vital, robust, foster, garner, intricate,
   interplay, meticulous, seamless, leverage, realm, align with, bolstered.
   If more than one appears in the piece (outside a clearly technical
   sense), replace at least all but the most natural one.
7. **Copula avoidance**: scan for "serves as," "stands as," "functions as,"
   "represents," "offers," "features," "maintains," "operates as" used
   where a plain "is/are/has" would be more natural. Restore the plain verb.
8. **Scaffolding and disclaimers**: "In summary," "In conclusion,"
   "Overall," "It's important to note," "It's worth noting." Delete on
   sight unless the user's required format explicitly calls for a summary
   section.
9. **Chat residue**: anything addressed to a reader as if they were the
   person who typed the prompt ("I hope this helps," "Let me know,"
   "Here's a..."), subject-line headers, unfilled placeholders. Delete.
10. **Stray markup/citation artifacts**: markdown syntax in a non-markdown
    target, `contentReference`, `oai_citation`, `utm_source=`, bracketed
    citation tokens, leftover `【…†…】` or `[cite: N]` fragments. Strip.
11. **Title Case headers** in a document that otherwise uses sentence case,
    or vice versa — normalize to match the surrounding document.
12. **Sentence-initial "Additionally," "Moreover," "Furthermore,"
    "Notably"** repeated more than once in the piece. Vary or cut.

If any of items 1–12 produces a hit, fix it and re-run the full list once
more before delivering — a fix to one pattern can sometimes introduce
another (e.g., replacing a spaced em dash with "however" placed at a
sentence start repeatedly creates a new transition-word tell).

## Output format

- Default: return only the rewritten text, in the same format as the
  input (same headings, lists, code, language), ready to use. No preamble,
  no "here's your humanized version," no meta-commentary — that would
  itself be scaffolding.
- If the user asks what changed, or if edits touch meaning-adjacent
  choices, add a short, plain change summary after the text, grouped by
  type (e.g. "removed puffery in ¶2; restored plain verbs; cut three
  spaced em dashes; removed one negative-parallelism construction").
- If a passage cannot be humanized without inventing content or risking
  meaning (e.g. a vague claim with no specifics to recover), leave it
  as-is or minimally trimmed and flag it briefly so the user can supply
  the missing detail. Do not paper over it with fabricated specificity.
- Match the input language. Humanize in the language the text is written
  in.

## Edge cases

- **Already-human / clean text**: make minimal or zero edits. Say so
  plainly rather than manufacturing changes.
- **Quotes, code, math, citations, data, proper nouns**: never rewrite.
  Fix only unambiguous mechanical artifacts (a broken pasted token, a
  stray tracking parameter), never wording.
- **User-required AI-ish features**: if the user explicitly wants
  title-case headers, a bolded-header list, or a summary section, keep it.
  User instruction overrides the catalog.
- **Very short inputs** (a sentence or two): be especially conservative;
  there's little rhythm to fix and high risk of drift.
- **Legitimate technical uses of flagged words**: keep them (see gate in
  #8).
- **Marketing/persuasive copy that is supposed to be promotional**: don't
  neutralize its purpose. Remove only the generic, hollow puffery; keep
  earned, specific selling points and the persuasive intent.
- **Mixed-authorship or partly-human text**: preserve the human passages;
  concentrate edits on the machine-signature passages.
- **Requests to defeat a specific AI detector, or to disguise authorship
  for deception** (e.g. passing off AI work as human where honesty is
  required, such as an academic integrity context): focus on genuine
  writing-quality improvement, which is what this skill does. Do not add
  errors, obfuscation, adversarial paraphrasing tools/techniques, or
  watermark-stripping tricks whose only purpose is to fool a detector
  rather than to improve the writing — that degrades the text and serves
  no legitimate editing goal. If the person's stated purpose is explicitly
  about evading academic-integrity detection, say so plainly and offer the
  legitimate version of the service (making genuinely better, clearer
  prose) instead.

## Quality assurance checklist (run before every delivery)

**Fidelity**
- [ ] Every fact, number, date, name, and citation is unchanged.
- [ ] No new claim, example, source, or specific was invented.
- [ ] The author's stance, certainty, and emphasis are unchanged.
- [ ] Quotes, code, math, and required formatting are intact.
- [ ] Structure and section order are preserved (unless restructure was
      asked).

**Mechanical self-audit (Step 6) — confirm you actually ran it**
- [ ] Searched for " — " and " -- " specifically; zero remain unspaced or
      converted.
- [ ] Searched for curly quotes/apostrophes; normalized unless target
      format requires them.
- [ ] Zero unearned "not just X but Y" / "X rather than Y" constructions
      remain.
- [ ] AI-vocabulary words appear at most once each, and only where
      natural.
- [ ] No stray markup or citation-artifact fragments remain.

**Signature removal**
- [ ] No unearned significance/legacy puffery remains.
- [ ] No trailing "-ing" editorial analysis tails remain.
- [ ] No peacock/promotional filler remains (unless purposeful marketing).
- [ ] No fake or inflated attribution ("experts say" with no source).
- [ ] No "In summary / important to note / as of my last update"
      scaffolding.
- [ ] Plain is/are/has restored where copula-avoidance occurred.
- [ ] Mechanical triads broken; decorative bold-colon lists de-templated.
- [ ] Chat residue, subject lines, placeholders removed.

**Naturalness without over-correction**
- [ ] Sentence lengths vary; rhythm reads human, not metronomic.
- [ ] Plain verbs and diction throughout; no thesaurus inflation.
- [ ] No sterile over-compression; natural connective tissue retained.
- [ ] No injected typos, slang, or fake casualness.
- [ ] Voice, register, and technical precision match the original.
- [ ] Clean original sentences were left untouched.

If any box fails, revise and re-check. When in doubt between two edits,
ship the one closer to the original.

## Self-verification prompt (final gate)

Before returning, ask yourself, in order:

1. Could the original author read this and say "yes, that's what I meant,
   just better"? If not, you drifted — pull back.
2. Did I add any specific that wasn't in the source? If yes, remove it.
3. Would a skilled human editor have made roughly these edits — or did I
   just trade one set of tics for another? If the latter, simplify
   further.
4. Did I change anything that was already fine? If yes, revert it.
5. **If I search this exact output for a spaced em dash or a curly quote
   right now, will I find one?** If you're not sure, go check — don't
   guess.

Only deliver when all five pass.