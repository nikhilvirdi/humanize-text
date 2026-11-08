---
name: humanize-text
description: Rewrite machine-sounding prose into natural human writing while keeping the author's meaning, claims, stance, and voice intact. Use this skill whenever the user asks to humanize text, remove AI tells, make writing sound less like a chatbot, fix robotic, generic, stiff, or formulaic prose, de-AI an email, essay, post, report, comment, or bio, or review a draft for AI-sounding patterns. Also use it when the user pastes text and says it sounds fake, too polished, or too generic, even if they never say "humanize". Always run the full workflow, including the drift audit and the mechanical audit, before delivering anything.
---

# Humanize Text

Rewrite machine-sounding prose so it reads like a careful person wrote it, without changing what the author said, believed, or sounded like.

This is a constrained edit, not a rewrite. Two things go wrong with this task, and the second is worse than the first:

1. **Tells survive.** The text still has the reflexes of machine prose: inflated significance, stock phrases, mechanical rhythm, decorative formatting.
2. **Drift.** The editing pass itself changes the text. Language models editing text tend to soften opinions toward neutral, make the tone more upbeat and emotional, swap plain words for formal ones, drop first-person voice and anecdotes, add adjectives, and quietly change conclusions, even when told to fix grammar only. A humanized version that reads smoothly but says something different has failed.

Work the way a good human copyeditor works: small, targeted edits, everything else left alone, the author's voice kept.

## Priorities, in order

1. **Fidelity.** Facts, claims, stance, certainty, and intent stay exactly as written. If humanizing and fidelity conflict, fidelity wins.
2. **No invention.** Machine prose often replaces a specific fact with generic praise. Do not reverse that by inventing specifics. Cut the padding or leave a plain neutral statement.
3. **Voice.** The author's register, person, humor, rough edges, and vocabulary stay.
4. **Fix the defect, not the word.** Each tell is a symptom of a writing problem (vagueness, puffery, filler, formula). Swapping one stock word for another leaves the problem in place and often creates a new tell. Remove or restructure.
5. **Minimal edits.** Change a sentence only when it contains a defect from the catalog below.
6. **Audit before delivery.** The drift audit and the mechanical audit are required steps, run against your actual output, not a formality.

## Fidelity rules

These apply to every edit.

- **Facts and fixed text.** Never alter numbers, dates, names, quotations, citations, URLs, code, equations, or proper nouns. Text inside quotation marks, code blocks, and math is untouchable, except for stripping pasted junk (see Artifacts).
- **Stance and certainty.** Same position, same strength. A hedge stays a hedge. A firm claim stays firm. Do not add hedges, and do not remove them.
- **Counterpoints and criticism stay.** If the author named drawbacks, risks, objections, or complaints, they remain at the same weight. Never smooth a one-sided piece into "both sides have merit" and never tilt a critical piece toward the positive.
- **Tone temperature.** Do not make the text more positive, more emotional, more enthusiastic, more formal, or more analytical than the original. Do not add intensifiers or adjectives.
- **Voice markers.** Keep first-person pronouns, direct address, anecdotes, examples, jokes, colloquialisms, idioms, questions, fragments the author chose, and regional spelling. Never convert personal experience into impersonal statement.
- **No new content.** No new examples, numbers, sources, transitions that assert a relationship the author did not state, or summary sentences.
- **Language and variety.** Reply in the language of the text. Keep its spelling variety (British, American, Indian, and so on). Do not translate.
- **Structure.** Keep section order, headings, and list structure unless the user asks to restructure.
- **When unsure, edit less.** Under-editing is safe. Semantic drift is not.

## Edit budget

Most of a humanized document should be the author's own sentences.

- Light (default): most sentences untouched, edits confined to flagged spans.
- Medium (user asks for "more natural" or "rework it"): flagged paragraphs may be restructured, but every claim, stance, and voice marker survives.
- Heavy (user explicitly asks for a full rewrite): still bound by every fidelity rule.

Practical limits unless the user says otherwise: output length within about 15 percent of the original, and no sentence changed unless it had a cataloged defect. If you find yourself changing sentences that were already clean and specific, revert them. Do not replace the author's own distinctive words with generic synonyms.

## Workflow

1. **Read everything first.** Identify genre, audience, register, person (I/we/you/third), language variety, and what the author is trying to get done. Note user constraints (length, format, tone).
2. **Diagnose.** Mark each defect with its catalog category. Mark spans to protect (quotes, code, names, numbers, voice markers).
3. **Decide each edit with the ladder below.**
4. **Edit,** smallest change first.
5. **Drift audit** against the original (required).
6. **Rhythm pass.**
7. **Mechanical audit** on the final text (required).
8. **Deliver** in the output format below.

For long documents, work section by section but keep terminology and voice consistent across sections, and run both audits on the whole.

## Decision ladder for each edit

Stop at the first "no".

1. Does the edit keep meaning, stance, certainty, tone temperature, and voice exactly?
2. Is the target a real defect from the catalog, as opposed to legitimate human or technical usage?
3. Can cutting or a minimal reshape fix it, rather than a rewrite?
4. Does the fix avoid inventing content?
5. Would a careful human writer plausibly produce the result, and not merely a different machine pattern?

## Defect catalog

### A. Content defects

**A1. Inflated significance.** Statements that an ordinary subject "stands as a testament," "marks a pivotal moment," "plays a vital role," "reflects broader trends," "leaves an indelible mark," "is deeply rooted," or sits inside an "evolving landscape." Includes hedged preambles that admit the subject is minor and then praise its importance anyway, and forced links to broader ecosystems, debates, or "ongoing discussions."
Fix: delete the inflation and keep only what the text supports. "Marks a pivotal moment in regional statistics" becomes "was established in 1989" if the date is in the text, or is cut. Never swap one grand phrase for a subtler one.

**A2. Editorial tails.** A trailing participle phrase that comments instead of informing: ", highlighting its significance," ", reflecting broader trends," ", ensuring reliability," ", contributing to growth," ", showcasing its importance," ", fostering collaboration." Strongest signal: an inanimate subject doing the highlighting. A fact, event, or object cannot underscore, emphasize, reflect, symbolize, or showcase anything.
Fix: cut the tail. If it carries a real fact, promote it to its own plain sentence. If the tail is attributed to a named person or source, confirm the source actually said it. If you cannot confirm, drop the attribution and flag it.

**A3. Promotional tone.** "Boasts," "vibrant," "rich heritage," "nestled in the heart of," "renowned," "groundbreaking," "diverse array," "state-of-the-art," "seamlessly," "commitment to excellence," "stunning," "captivating."
Fix: neutral, specific description, or cut. "Boasts a population of 56,998" becomes "has a population of 56,998." Marketing copy that is meant to sell keeps its earned, specific selling points. Only the hollow superlatives go.

**A4. Notability and source name-dropping.** Listing outlets by type or name to prove importance ("featured in national media," "covered by trade publications," "independent coverage"), saying a subject "maintains an active social media presence," or describing what a source is rather than what it said.
Fix: state the fact the source supports, with a plain citation if the format uses them. Cut the outlet parade.

**A5. Phantom authorities.** "Experts argue," "observers note," "industry reports suggest," "some critics say," "several sources," "scholars agree," "widely regarded," backed by one source or none. Also a non-exhaustive "such as" in front of a list that is in fact complete.
Fix: attribute to the named source if the text has one. Otherwise state the claim plainly or flag it for sourcing. Never upgrade one source into "studies show."

**A6. Vague connection.** "Associated with," "connected to," "in connection with," "in association with," "linked to," used where a concrete relationship exists in the text. "Was connected with science education at the university" should be "taught science at the university" if that is what the text means.
Fix: use the specific verb the text supports. If the text does not say what the relationship is, leave it and flag it.

**A7. Identification framing.** "His website identifies him as," "records list her as," "is described by the database as." The sentence is about the source's existence instead of the fact.
Fix: state the fact, and keep the source only if the reader needs it for trust.

**A8. Formula sections.** "Despite its success, X faces several challenges, including... Despite these challenges, X continues to thrive." Speculative "Future Outlook" closers. Generic "Legacy and Impact," "Awards and Recognition," "Key Takeaways," "Final Thoughts," "Questions to Consider" sections.
Fix: delete the formulaic sentences. Keep concrete challenges and plans the text actually names. Keep a heading only if real content remains. If a section empties out, flag it and propose removal instead of silently deleting.

**A9. Summaries and echoes.** "In summary," "In conclusion," "Overall," a final sentence that restates the paragraph, a conclusion section that repeats the body.
Fix: delete. A conclusion should state something new or stop.

**A10. Disclaimers and corrective framing.** "It's important to note," "it's worth remembering," "may vary by region," "should be treated as X rather than Y," "does not by itself establish," "should not be confused with," "details are limited," "not widely documented," "maintains a low profile," "as of my last update," "based on available information." Includes speculation about what missing information "likely" is.
Fix: delete. State the point directly. Never speculate about unknown information. If the author genuinely needs a caveat, keep it in one plain sentence.

**A11. Hollow reassurance (first-person and persuasive writing).** Promises, goodwill, and procedure in stock form: "I am committed to," "I assure you," "I have taken the time to," "I understand the importance of," "going forward, I will ensure," "this aligns with the guidelines," "to ensure compliance," "I'm happy to address any concerns," "if there are any specific issues, please point them out," "I welcome feedback," "I respectfully request," "I apologize for any inconvenience this may have caused," "Thank you for your time and consideration." Also: citing rules as an abstract whole, listing the names of standard policies, "my intention was not X but Y," "let's focus on the substance rather than...," asking a neutral third party to review, and "these changes would make the article more balanced and clear."
Fix: cut the boilerplate. Keep the specific commitments, facts, and requests the author actually makes, stated plainly. This register is the densest source of tells, so scrutinize it hardest.

**A12. Drama scaffolding.** Hot-take framing and fake suspense: "Here's the thing:", "Here's why that matters," "Here's the deal," "The result?", "And honestly?", "Hot take:", "Then I realized:", "But here's what nobody is saying," "That's the real unlock," "Let that sink in," a rhetorical question followed immediately by its own answer.
Fix: state the point. Most of these collapse to "But" or nothing.

**A13. Cliche frames.** "In today's fast-paced digital landscape," "In the dynamic world of," "As the world continues to evolve," "Whether you're a beginner or an expert," "Let's dive in," "No fluff," "shouting into the void," "take it to the next level," "looming challenges," "advantages and disadvantages."
Fix: start with the actual subject. Cut the frame.

**A14. Buzz verbs and false ranges.** "Unlock," "empower," "elevate," "harness," "embark," "navigate" (figurative), "master X in N days," and "from X to Y" where X and Y are not ends of a real scale ("from problem-solving to artistic expression to technological innovation").
Fix: say the concrete thing, or list the items plainly if they are all needed.

**A15. Chat residue.** "Certainly!", "Of course!", "Great question!", "I hope this helps," "Let me know if you'd like," "Would you like me to," "Here is a...", "In this section, we will discuss," "As an AI," offers to reformat, subject-line headers ("Subject: ..."), and pasted transcript prefixes ("You said:", "Assistant said:").
Fix: delete entirely. The finished text must not address its reader as a user.

**A16. Placeholders and leftovers.** "[Your Name]," "[Describe the issue]," "(Add URL here)," "INSERT_SOURCE," "2026-xx-xx," instruction comments such as `<!-- add if available -->`, "Evidence to be supplied."
Fix: if the author's content is missing, flag it. Do not fill it in.

### B. Language defects

**B1. Vocabulary clusters.** These words cluster in machine prose: delve, underscore (verb), showcase, testament, tapestry, landscape (abstract), pivotal, crucial, vital, key (as filler), robust, foster, cultivate, garner, boast, intricate, intricacies, interplay, meticulous, seamless, enhance, leverage, navigate (figurative), realm, embark, illuminate, align with, bolster, enduring, multifaceted, nuanced, vibrant, streamline, underpin, shed light on, deep dive, valuable (as filler), resonate, encompass, empower, elevate, harness, comprehensive, holistic, transformative, profound, indelible. A newer cluster adds: quietly, steady, dependable, practical, prioritize, challenge (as filler), clearer, echoed, universally, and "what matters is."
Rule: one such word alone is not a tell. Density is. Strip rhetorical uses and keep technical ones (a cryptographic key, a literal underscore, a physical landscape, statistical robustness, a technical use of "interplay").
Fix: restructure so the word is not needed. Do not swap in another word from this list. Plain replacements: utilize to use, leverage to use, foster to encourage or build, garner to get, showcase to show, delve into to examine.

**B2. Dressed-up copulas.** "Serves as," "stands as," "functions as," "operates as," "represents," "marks," "features," "offers," "boasts," "maintains," and lead sentences that begin "X refers to..." when the text is about the thing itself. Also "began his career as" for "was," and "ventured into politics as a candidate" for "was a candidate."
Fix: restore "is," "are," "has." "The gallery serves as the exhibition space and features four rooms" becomes "The gallery is the exhibition space and has four rooms." Keep the dressed-up form only when it adds information.

**B3. Contrast frames.** "Not just X, but Y," "not only... but also...," "it's not X, it's Y," "X isn't about A; it's about B," "no X, no Y, just Z," "not A, not B, not C," "X rather than Y" used for rhetorical lift, and the multi-sentence version ("He came from a famed family. His life, however, took a different path.").
Fix: assert the positive claim directly. Keep a contrast only when the author is genuinely correcting a stated misunderstanding or the contrast carries information. Aim for none, with at most one earned instance in a long piece.

**B4. Triads.** Three parallel adjectives, clauses, or bullets where one or two would carry the meaning ("clear, concise, and compelling"; "workshops, panels, and networking opportunities").
Fix: keep the items that say something distinct, cut the rest. Vary list lengths. Keep a real triad when all three items are needed.

**B5. Elegant variation.** Rotating synonyms to avoid repeating a word ("the film... the picture... the cinematic work").
Fix: use the plain, consistent term. Repetition is fine. Do not force repetition where separately written chunks never had it.

**B6. Noun-heavy construction.** Verbs turned into nouns and stacked: "the implementation of the optimization of the pipeline." Participle modifiers placed after nouns ("the data collected by the process"). Clause subjects that begin with "that" ("That the results held suggests..."). Sentence relatives that add commentary (", which underscores..."). Chains of coordinated nouns ("design, implementation, and evaluation").
Fix: turn nominalizations back into verbs and give sentences human subjects and active verbs where the text already supports it. "The implementation of the optimization improved throughput" becomes "Optimizing the pipeline improved throughput." Technical and legal writing legitimately uses some of this. Edit only when the density makes the prose heavy.

**B7. Transition density.** Sentence-initial "Additionally," "Moreover," "Furthermore," "Notably," "Importantly," "Consequently," "In addition," several per page.
Fix: cut where the order already implies the relation. Where the relation matters, fold it into the sentence ("and," "but," "so," "because"). Fold mild contrast ("However, X.", "That said, X.") into the previous sentence with "though," "although," or "but."

**B8. Hollow hedging.** Vague softeners that commit to nothing: "can play a role," "may contribute to," "can vary," "a range of factors," "various aspects," "key considerations."
Fix: if the text supplies the specific, use it. If not, cut the filler. Do not invent the specific. Keep a hedge that reflects the author's real uncertainty.

**B9. Sentiment and intensity inflation.** Stacked adjectives and adverbs that add heat without information: "truly," "incredibly," "powerful," "remarkable," "profound," "deeply," "unwavering."
Fix: cut those the author did not earn with a fact. Never add any.

**B10. Uniform rhythm.** Sentences clustered in the same length band, the same opening word or structure three times running, every paragraph the same shape (claim, three supports, wrap-up), every sentence closing on a tidy abstract noun phrase.
Fix: see the rhythm pass.

### C. Formatting defects

**C1. Dashes.** Spaced em dashes (" — "), spaced en dashes used as dashes, " -- ", and a lone hyphen with spaces around it used as a dash. Also unspaced em dashes at high density, used for punch.
Fix: zero spaced dashes. Unspaced em dashes: at most one per roughly 200 words, kept only where a real aside needs it. Replace the rest using a mix of full stops, commas, colons, parentheses, or a restructured sentence. Do not default every dash to a comma, which creates uniform comma-only prose and its own tell.

**C2. Quotation marks.** Curly quotes and apostrophes in plain-text targets, or mixed straight and curly.
Fix: normalize to straight quotes and apostrophes unless the target format clearly uses typographic quotes, in which case make them consistent.

**C3. Decorative emphasis.** Bold scattered through prose, "key takeaway" bolding, bold lead-ins on every bullet.
Fix: remove emphasis that is not marking a defined term or a real warning.

**C4. Inline-header lists.** Every item shaped "**Header:** description," often with emoji.
Fix: turn into prose when the items read naturally as a sentence or two. Keep real enumerations as plain lists without the bold-colon template.

**C5. Headings.** Title Case headings in a sentence-case document (or the reverse), skipped heading levels, a top-level heading inside a short piece, horizontal rules before every section, emoji headings, headings and sections inside an email, reply, comment, or message.
Fix: match the document's convention (sentence case by default), keep levels sequential, drop ornaments, and remove sections from short conversational text.

**C6. Over-structured content.** Bullets or small tables where two sentences would do.
Fix: prose, unless the user's format requires structure.

**C7. Emoji** as bullets or headings in non-casual text. Remove unless the genre is casual social writing and the author used them.

### D. Artifacts and unverifiable material

**Strip pasted junk, always.** These are broken output, not style: citation placeholder tokens (`oai_citation`, `contentReference`, `oaicite`, `turn0search0`, `citeturn`, `attributableIndex`, `[web:1]`, `[attached_file:1]`, `grok_card`, `[cite: N]`, `【...†...】`), tracking parameters in URLs (`utm_source=`, `referrer=` pointing at a chatbot domain), footnote return arrows, stray markdown syntax in non-markdown targets, fenced code blocks wrapped around plain prose, and leftover instruction comments.

**Flag, never fix:** references that look invented (DOIs or ISBNs that may not resolve, book citations with no page, links that look fabricated, a source cited for a claim it likely does not contain), numbers that contradict each other, claims with no support. Tell the user these need checking. Do not repair, replace, or invent a reference.

## What to preserve

Over-correction is its own tell. Leave these alone:

- Plain copulas and verbs: "is," "has," "wrote," "moved," "used," "died."
- Supported superlatives and definite claims: "the first," "the only," "one of the largest."
- Mild hedges and intensifiers the author chose: "very," "perhaps," "roughly," "tends to."
- Ordinary connective wording: "in order to," "as a result of," "the fact that."
- Occasional tight em dashes, occasional triads, an occasional transition word.
- Formal, academic, or elaborate register when the genre calls for it.
- Contractions and their absence: match the original's rate. Do not add or strip contractions to sound more human.
- Correct grammar, consistent style, technical terms, required structure.
- Letter and email conventions (greeting, sign-off) when the genre is a letter or email.

None of these alone indicates machine writing: clean grammar, formal vocabulary, unusual words, a salutation, a single transition word, missing citations, or prose that is merely bland. Do not edit for them. Never inject typos, slang, filler words, or fake casualness. That is a different kind of fake.

If a sentence is already clean, specific, and natural, leave it exactly as it is.

## Genre notes

- **Academic and technical:** protect terminology and precision. Concentrate on A1, A2, A5, B6, B7. Keep legitimate nominalizations.
- **Marketing and persuasion:** keep the persuasive purpose and earned specifics. Remove hollow superlatives, triads, contrast frames, and drama scaffolding.
- **Email, messages, comments, appeals:** scrutinize A10, A11, A12, A15 and C5 first. Short and direct beats polished and padded. Keep the greeting and sign-off if the genre needs them, but drop the formula inside.
- **Profiles, bios, and reference text:** A1 to A8 dominate. Cut puffery and source-listing, keep dates and facts.
- **Narrative and creative:** be conservative. Voice is the product. Fix residue, cliche frames, and rhythm, and leave style choices alone.
- **Social posts:** A12 and A13 dominate. Keep the author's energy, drop the formula.

## Rhythm pass

Do this after the content edits, before the mechanical audit.

- Read the paragraph aloud in your head. If sentences land at about the same length, break the pattern: one short sentence where the thought is short, one longer sentence where the thought needs its clauses. In any passage of eight or more sentences, the longest sentence should clearly outrun the shortest.
- No three consecutive sentences should open with the same word or follow the same skeleton.
- Vary paragraph size to match content. Not every paragraph needs a topic sentence, three supports, and a wrap-up.
- Do not end every paragraph on a tidy summarizing line. Stop where the content stops.
- Mix punctuation: full stops, commas, colons, parentheses, the occasional semicolon. Do not let one mark carry everything.
- Never create rhythm by adding words. If the text is short, keep it short.

## Drift audit (required)

Compare the rewrite to the original, paragraph by paragraph. Fix every failure by reverting the offending edit.

1. **Claim ledger.** List every claim in the original, including minor ones. Confirm each appears in the output at the same strength. Anything missing: restore. Anything new: delete.
2. **Stance and polarity.** For each issue the author took a side on, the output takes the same side with the same force. Look specifically for drift toward neutral ("there are valid points on both sides"), toward positive, and toward optimistic. Drawbacks, objections, and complaints still carry the same weight.
3. **Voice markers.** Count first-person pronouns, direct address, questions, exclamations, idioms, jokes, and anecdotes. The output has them at about the original's rate, never lower.
4. **Intensity.** Count adjectives, adverbs, intensifiers, and emotive words. The output has no more than the original.
5. **Register.** Formality is unchanged. "Got" did not become "obtained." Plain nouns did not become abstract ones.
6. **Vocabulary retention.** The author's own distinctive words survived. No sentence was rewritten in a generic voice that could belong to anyone.
7. **Length.** Within about 15 percent of the original, with every cut traceable to a cataloged defect.
8. **Added generalizations.** No new sentence that the author did not write, including transitions that assert a relationship and summary lines.

## Mechanical audit (required)

Literally scan the final text, not your memory of it. Every hit is a required fix. After fixing, re-run the entire list, because a fix can create a new tell (a dash swapped for a sentence-initial "However," or a flagged word swapped for another flagged word).

1. **Dashes.** Search for " — ", " – ", " -- ", and " - " used as a dash. Zero allowed. Unspaced em dashes: no more than one per roughly 200 words.
2. **Quote characters.** Curly quotes and apostrophes normalized per C2.
3. **Contrast frames.** "Not just," "not only," "it's not... it's," "rather than" for lift, "no X, no Y, just Z." Zero, or one earned instance in a long piece.
4. **Triads.** Any sentence with three parallel items: confirm all three carry distinct meaning.
5. **Editorial tails.** Participle phrases at sentence ends that comment ("highlighting," "reflecting," "ensuring," "contributing to," "showcasing," "underscoring"). Zero.
6. **Vocabulary.** Scan against B1. No flagged word more than once, and no more than two distinct flagged words per 300 words outside technical use.
7. **Dressed-up verbs.** "Serves as," "stands as," "functions as," "represents," "features," "offers," "maintains," "refers to." Each one justified or restored to a plain verb.
8. **Scaffolding.** "In summary," "In conclusion," "Overall," "It's important to note," "It's worth noting," "As of my last update." Zero.
9. **Drama frames.** "Here's the thing," "The result?", "And honestly?", "That's the real," rhetorical question plus answer. Zero.
10. **Reassurance boilerplate.** "I am committed to," "I assure you," "I understand the importance of," "I'm happy to," "I respectfully," "going forward," "thank you for your time and consideration," "if there are any concerns." Zero unless the author's content is specific and the genre requires it.
11. **Chat residue and placeholders.** Nothing that addresses a user, no leftover brackets, no empty template fields.
12. **Artifacts.** No citation tokens, tracking parameters, stray markdown, or fenced prose.
13. **Formatting.** Heading case consistent, levels sequential, no decorative bold, no emoji bullets, no bold-colon list template, no sections in short messages.
14. **Transitions.** Sentence-initial Additionally, Moreover, Furthermore, Notably, Importantly, Consequently: at most one in the whole piece.
15. **Rhythm.** Sentence lengths vary per the rhythm pass. No three consecutive openers alike.
16. **Over-edit check.** Did you change any sentence that had no cataloged defect? Revert it.

## Output format

- Default: return only the rewritten text, in the same format and language as the input, ready to use. No preamble, no "here is your version," no closing offer.
- If the user asks what changed, or if you made a meaning-adjacent call, add a short plain change summary after the text, grouped by type (for example: "cut inflated significance in paragraph 2; restored plain verbs; removed three spaced dashes; folded two contrast frames into direct statements").
- If something needs the author, say so briefly after the text: a vague claim with no specifics to recover, a reference that may be invented, numbers that disagree, a section that emptied out. Never cover the gap with invented detail.
- Do not claim the result will pass any detector. Say only what you changed.

## Edge cases

- **Already natural text:** make minimal or no edits and say so plainly. Do not manufacture changes.
- **Very short input** (a sentence or two): be especially conservative. There is little rhythm to fix and a lot of room to drift.
- **User-required features:** if the user explicitly wants title-case headings, a bold-header list, or a summary section, keep them. The user's instruction overrides the catalog, but not the fidelity rules.
- **Mixed authorship:** preserve the human passages. Concentrate edits on the machine-sounding ones.
- **Text with errors:** do not silently fix factual mistakes or change claims. Flag them.
- **Non-English text:** apply the same principles (inflated significance, filler, formula, rhythm, drift) to the language at hand. Do not apply English word lists, and do not translate.
- **Requests to evade detectors or disguise authorship** where honesty is required, such as coursework or any setting with an authorship rule: do not use adversarial tricks, injected errors, obfuscation, or paraphrase-to-fool methods. They degrade the text and serve no editing purpose. Say plainly that you will improve clarity and naturalness, and offer that. Make clear you cannot promise any detector result.

## Examples

**Reference text**

Before: Nestled in the heart of the valley, the town boasts a vibrant arts scene, serving as a testament to the region's rich cultural heritage. The annual festival, which draws about 4,000 visitors, highlights the community's commitment to creativity, fostering connection and showcasing local talent.

After: The town sits in the valley and has an arts scene. Its annual festival draws about 4,000 visitors.

Why: the only facts were location, an arts scene, the festival, and the 4,000 figure. Everything else was significance with no content, and nothing was invented to replace it.

**First-person appeal**

Before: I understand the importance of following the guidelines, and moving forward, I am committed to ensuring that my contributions remain constructive. My intention was not to promote the company but to share information. If there are any specific concerns, I would be happy to address them. Thank you for your time and consideration.

After: I'll follow the guidelines from now on. I wasn't trying to promote the company. I was sharing information about it.

Why: the commitment and the denial are the author's real claims, so they stay in plain form. The boilerplate around them went.

**Drift to avoid**

Original: The rollout was a mess. Support tickets doubled and I wouldn't call it a success.

Bad rewrite: The rollout presented some challenges, but valuable lessons were learned that will inform future success.

Why it fails: the stance flipped from negative to upbeat, the first person disappeared, a vague claim replaced a specific one, and a claim the author never made was added. The right edit here is none, or nothing beyond fixing a typo.

## Final gate

Before delivering, answer these in order.

1. Could the author read this and say "yes, that's what I meant, just better"? If not, you drifted. Pull back.
2. Did I add any detail, claim, or sentence that was not in the source? If yes, remove it.
3. Is anything the author wrote, including an opinion, a drawback, a joke, or an "I," missing or weakened? If yes, restore it.
4. Would a skilled human editor have made roughly these edits, or did I trade one set of tics for another? If the latter, simplify.
5. Did I change anything that was already fine? If yes, revert it.
6. If I scan this exact text for a spaced dash, a curly quote, a contrast frame, and a flagged word cluster right now, will I find any? If unsure, scan again.

Deliver only when all six pass.
