---
name: legal-design-en
description: Rewrites English-language legal and quasi-legal text into plain language, without changing its legal meaning. Use this skill whenever someone is working with English legal text and wants it clearer, simpler, friendlier, or more readable — terms of service, privacy policies, GDPR/UK GDPR notices, consent screens, cookie banners, insurance policies (UK) or insurance contracts (US), loan agreements, subscription terms, employment contracts, consent/onboarding microcopy, transactional emails. Trigger it even when the person doesn't say "plain language" or "legal design" — phrasing like "simplify this contract", "rewrite this in plain English", "this reads like legalese", "make this readable", "de-jargon this", or an uploaded English-language agreement with a request to simplify it all count. Also use it to audit existing documents for plain-language compliance, to check terminology consistency across a set of documents, and to teach these techniques. Covers both UK and US drafting conventions and flags where they diverge.
---

# Legal Design EN — rewriting English legal text into plain language

Rewrite the **language** of an English legal text so an ordinary adult can read it on a phone — while keeping the exact same legal effect.

## Core rule

**The language changes. The meaning does not.**

After the rewrite, the text must produce exactly the same legal effect as before: the same obligations, rights, conditions, deadlines, exceptions, and scope.

If a passage can't be simplified without risking a change in meaning, **don't simplify it**. Leave the original and mark it `[FLAG]` with a reason. A hard sentence left untouched is a small cost. A simplified sentence that quietly shifts liability is a serious one. People using this skill usually send these documents to real customers, so the cautious choice is the right one.

This matters more than it sounds like it should. The natural temptation when simplifying legal text is to **resolve ambiguity** — to decide what an unclear provision "probably means" and write that down. That's no longer editing; it's drafting, and it's out of scope. Ambiguity gets flagged, never resolved.

## Step 1 — Fix the voice before rewriting anything

Two decisions bind every sentence that follows. Ask the user if they don't follow from context.

1. **How does the organization refer to itself?** Recommended: `we` / `us` / `our`. This only works if the definitions section actually defines it (`we / [Company] means [full legal name, registration number...]`). Without that definition, keep `the Company` / `the Provider` / `the Insurer` and tell the user what they'd gain by adding one.
2. **How do you address the reader?** English already defaults to `you` in consumer contexts far more than Polish or German does — the real fight isn't `you` vs. a formal pronoun, it's `you` vs. drifting back into third-person entity-nouns mid-document (`the Customer shall notify the Company` creeping back in after a `you`/`we` opening). Pick direct address and hold it for the whole document.

Defining `we` and `you` removes more legalese than any other single technique, because it dissolves the passive constructions English legal drafting builds around abstract party-names (`the Data Subject's information is processed by the Controller`).

Collect the list of **defined terms** (from the Definitions/Interpretation clause) before starting. Reproduce them verbatim — capitalization and all — never swap in a simpler-sounding synonym.

**Jurisdiction check.** Because this skill covers both UK and US practice, identify which one applies before rewriting — usually visible from the governing-law clause, the currency, or spelling conventions (`programme`/`licence` vs. `program`/`license`). Some techniques and citations below are jurisdiction-specific; `references/context.md` and `references/phrasebook.md` flag where UK and US practice diverge. If a document mixes both (common in group-company templates), flag that as its own finding — see the cross-document audit in `references/audit.md`.

If the user gives several documents, the voice choice holds across all of them. A drift in terminology between the terms of service and the consent screen is a real defect, not a stylistic nitpick.

## Step 2 — Rewrite

Apply in order. Full substitution tables and examples: `references/phrasebook.md`.

**Sentences.** One sentence, one idea. Target 20–25 words; the UK insurance-industry clear-communication guide flags anything over 29 words as hard to read and recommends staying well under 30. Split long compound sentences — but only when the logic survives intact. When a sentence nests conditions (`if… unless… provided that…`), turn it into a bulleted list, not separate sentences. Splitting nested conditions into sentences is the single most common way meaning gets lost.

**Active voice.** `Your personal data is processed by us` → `We process your personal data.` Always make clear who does what to whom.

**Verbs instead of nominalizations.** `make an application` → `apply`. `give consideration to` → `consider`. `effect a termination of the Agreement` → `end the Agreement`. `make a determination` → `decide`.

**Direct forms instead of passive/impersonal constructions.** Cut `it is required that`, `there shall be provided`, and third-person entity-noun back-reference once `we`/`you` are defined.

**Cut archaic connective tissue.** `heretofore`, `hereinafter`, `witnesseth`, `whereas` (as a recital-opener), `notwithstanding the foregoing`, `pursuant to` → `under`, `in the event that` → `if`, `prior to` → `before`, `subsequent to` → `after`, `with respect to` → `about`. Full list in `references/phrasebook.md`. Avoid Latin (`inter alia`, `mutatis mutandis`, `bona fide`, `prima facie`) in consumer-facing text.

**Collapse doublets and triplets.** `null and void` → `void`. `cease and desist` → `stop`. `each and every` → `each`. `full force and effect` → `in effect`. These are historical hedges from when English contracts blended Latin, French, and English terms for the same concept — they carry no separate legal meaning today, but check `references/phrasebook.md` before cutting any specific one, since a few (`terms and conditions`, `representations and warranties`) are now themselves defined or customary terms of art.

**Headings can become questions.** `Termination` → `How can this agreement end?` This is the only structural change allowed by default.

## Step 3 — Check meaning before you hand back the result

Read every rewritten passage next to the original and check it point by point. Full checklist and cross-document mode: `references/audit.md`.

The checks that matter most, because this is where meaning actually slips:

- **Modality.** `shall` / `must` / `will` / `may` / `should` are not interchangeable. `shall` is the most dangerous word in English legal drafting — it has been read by courts as `must`, `will`, `may`, and `should`, and has generated well over a hundred appellate decisions purely on what it meant in a given clause. Converge each occurrence on `must` (obligation), `will` (promise/future fact), `may` (permission), or present tense (fact/entitlement) — but preserve exactly the modal strength the original clause carried; don't let a rewrite quietly turn a `may` into a `must`.
- **Scope words.** `solely`, `exclusively`, `at least`, `no later than`, `including but not limited to`, `in particular` — each of these controls what a provision covers.
- **Reach of provisos.** `subject to clause 5`, `without prejudice to`, `notwithstanding clause 3` must still limit exactly what they limited.
- **`provided that`.** This phrase is itself a classic English drafting ambiguity — it can mean `if` (a condition) or `except that` (an exception). Read the original carefully before choosing which one to write.
- **Nested conditions.** List the conditions from the original and the rewrite side by side and compare them explicitly — don't eyeball it.
- **Numbers, dates, deadlines, amounts, retention periods** — identical.
- **Statutory cross-references** — verbatim.
- **Defined terms** — no paraphrasing.
- **New ambiguity** — does the rewrite admit a reading the original didn't?

## Step 4 — Give a readability estimate

Which metric is defensible depends on jurisdiction — say which one you're using and why:

- **US:** Flesch Reading Ease is the standard, because it's the metric written into state insurance-readability statutes. Most states set a floor of 40; Connecticut, Florida, and New York require 45; Maine, Massachusetts, North Carolina, Virginia, and Wisconsin (Medicare Supplement) require 50. For general consumer contracts, aim for 60–70 ("plain English, easily understood by 13–15-year-olds" on the standard interpretation scale). Flesch-Kincaid Grade Level as a secondary figure.
- **UK:** the general insurance-industry guidance (ABI/Fairer Finance) targets an Automated Readability Index (ARI) grade of 8 or below — roughly UK Year 8 / age 11 — against a baseline where the average policy document currently reads at a 16–18 grade level.
- Tools: Hemingway Editor, Readable.com, Microsoft Word's built-in readability statistics (Flesch Reading Ease and Flesch-Kincaid Grade Level are both built in).

Note the limitation either way: these formulas measure surface features (sentence length, syllable count), not comprehension. A sentence can score well and still be confusing if it hides a nested condition — that's what Step 3's audit is for, not the readability score.

## Response format

Default to a before/after table — the diff is what makes a lawyer's review fast and cheap:

```
| No. | BEFORE | AFTER | What changed | Flag |
```

- `No.` — the clause number (`Clause 4.2(c)`) or string key (`consent_marketing_title`)
- `BEFORE` — the original, verbatim
- `AFTER` — the rewrite, or `— unchanged —`
- `What changed` — 10 words max (`passive → active; shortened sentence`)
- `Flag` — blank, or `[FLAG]` with a reason

Cover every clause. Don't skip any and don't shortcut the work with "the rest follows the same pattern."

After the table, list the flags grouped for a lawyer's attention, then the readability estimate.

If the user only wants the clean rewritten text, give them that — but list the flags anyway. They won't reconstruct themselves.

## Always flag instead of fixing

- Ambiguous passages where simplifying would force a choice between readings
- Unclear references — what `subject to the foregoing`, `the above`, or `such` actually points to
- Anything touching liability, indemnity, intellectual property, jurisdiction, or governing law
- Text that looks like a quotation from a statute or a regulator-mandated form of words (GDPR/UK GDPR Art. 13/14 content, SEC-mandated risk-factor language, FCA-mandated risk warnings, US state-mandated insurance notices)
- Any simplification that would narrow or widen an exception
- `shall` where the obligor isn't clear from context

## Out of scope

This skill changes language. It doesn't redesign documents. Don't add "in short" summary layers, icons, tables, timelines, or decision maps; don't reorder sections; don't delete provisions that look redundant. Those are legitimate legal-design moves, but they add or move substance and need a separate, lawyer-reviewed decision. Mixing "make this readable" with "restructure this" is exactly the mechanism by which documents quietly lose provisions.

Mention to the user that a two-layer pattern (a plain-language summary sitting above the binding text — the model behind the CFPB's "Know Before You Owe" mortgage forms and the EU's layered privacy notices) is the standard next step, and that the summary must be marked as informational, with the full text clearly identified as what binds.

## Working across a document set

With several documents, work through them one at a time but finish all of them. Keep a visible progress table (`PENDING` / `IN PROGRESS` / `DONE` / `BLOCKED`) and update it after each document. Don't end early with "the remaining documents are similar" — short text like consent screens and button labels is usually the worst-written and most-read part of the set.

Once every document is done, run the cross-document consistency audit from `references/audit.md`. Contradictions between documents (terms say 14 days, the consent screen says 30; the privacy notice lists different data categories than the onboarding screen) are legal risks and get reported separately from style inconsistencies — and for a multi-jurisdiction set, so does mixed UK/US spelling, terminology, or currency, which signals a template that was never actually localized.

## Reference files

- `references/phrasebook.md` — full legalese substitution tables, nominalization → verb pairs, before/after examples, UK/US drafting pitfalls
- `references/audit.md` — meaning-preservation checklist, nested-condition comparison method, cross-document audit, flag triage
- `references/context.md` — legal basis for plain language in the UK and US (Consumer Rights Act 2015, GDPR/UK GDPR Art. 12, FCA Consumer Duty, SEC Plain English Rule, state insurance-readability statutes, NY GOL §5-702), readability targets, exemplar documents, risk and criticism. Read this when the user asks *why* to do this work, needs to justify it to a client or colleague, or is learning the method.
