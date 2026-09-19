# Substitution tables and examples

## Contents
1. Legalese → plain English
2. Nominalizations → verbs
3. Doublets and triplets
4. The shall/must/will/may discipline
5. Party names
6. Full-sentence examples
7. UK/US drafting pitfalls

---

## 1. Legalese → plain English

| Legalese | Plain English |
|---|---|
| heretofore / hereinbefore | until now — or cut entirely |
| hereinafter | later in this document — or cut and just repeat the defined term |
| herein / hereof / hereto / hereunder | in this agreement / of this agreement / to this agreement / under this agreement — say which |
| witnesseth | cut entirely (archaic recital opener, no legal content) |
| whereas (as a recital opener) | cut, or replace the recital with a plain sentence of context |
| notwithstanding the foregoing | despite the above — or better, restructure so the exception reads first |
| pursuant to | under |
| in accordance with | under / following |
| in the event that | if |
| in the case where | if / when |
| prior to | before |
| subsequent to | after |
| at such time as | when |
| for the duration of | while / during |
| with respect to / with regard to | about |
| in the amount of | for |
| for the purpose of | to |
| in the absence of | without |
| provided that | if — **or** except that. Check which one the original means; see §7 and `audit.md`. |
| said [noun] (as in "said Agreement") | that [noun] / the [noun] |
| such [noun] | that [noun] / this [noun] — or just repeat the defined term |
| shall be deemed to | counts as / is treated as |
| it is agreed that | cut; just state the agreed thing |

Avoid Latin in consumer-facing text: `inter alia`, `mutatis mutandis`, `bona fide`, `prima facie`, `ipso facto`, `de facto`, `pro rata` (pro rata is common enough to be understood in billing contexts — flag rather than cut automatically). Spell out abbreviations on first use: `e.g.` → `for example`, `i.e.` → `that is` (or just rewrite the sentence).

---

## 2. Nominalizations → verbs

Nouns ending in `-ation`, `-ment`, `-ance`, `-ence` usually hide a verb. Bring it back.

| Nominalization | Verb |
|---|---|
| make an application | apply |
| give consideration to | consider |
| effect a termination of | end / terminate |
| make a determination | decide |
| provide assistance | help |
| make payment | pay |
| give notification | notify / tell |
| conduct an investigation | investigate |
| make a modification | change |
| give authorization | authorize |
| reach an agreement | agree |
| make a request | ask / request |
| carry out a review | review |

---

## 3. Doublets and triplets

English contract drafting inherited pairs of near-synonyms from its Anglo-Norman/Latin/English legal history. They don't carry separate legal meaning today, but some have become fixed terms of art — check before cutting.

| Doublet/triplet | Plain form | Note |
|---|---|---|
| null and void | void | safe to collapse |
| cease and desist | stop | safe to collapse |
| each and every | each | safe to collapse |
| full force and effect | in effect | safe to collapse |
| any and all | all | safe to collapse |
| free and clear | free | safe to collapse |
| terms and conditions | terms | often itself a defined/customary term — flag before renaming |
| representations and warranties | — | a defined term of art with distinct legal meanings for "representation" vs. "warranty" in some jurisdictions — **never collapse**, flag instead |
| rights and remedies | — | can carry distinct meaning (a right vs. the remedy for breaching it) — flag before collapsing |
| give, devise and bequeath | leave | wills/estates context; each word historically covered a different asset type — flag if the document is a will, safe to simplify in an ordinary contract quoting the phrase loosely |

---

## 4. The shall/must/will/may discipline

`shall` is the single most litigated word in English contract drafting — courts have read it as `must`, `will`, `may`, and even `should`, depending on context, generating well over a hundred appellate decisions on what a given `shall` clause actually required. Garner, Adams, and most modern style guides recommend abandoning it in favor of a consistent convention:

| Purpose | Use |
|---|---|
| Obligation (a party must do something) | `must` |
| Promise / future contractual fact | `will` |
| Permission | `may` |
| Prohibition | `must not` (not `shall not`, which inherits the same ambiguity) |
| Fact, definition, or entitlement (no obligation at all) | present tense — `The fee is £50`, not `The fee shall be £50` |

When rewriting a document that already uses `shall` throughout, don't mechanically find-and-replace it with `must` — first work out from context which of the five meanings above the drafter intended, and preserve that meaning. If it's genuinely unclear which one applies, `[FLAG]` it; this is exactly the kind of ambiguity Step 3 exists to catch, not resolve.

---

## 5. Party names

| Legal name | Plain | Condition |
|---|---|---|
| the Company / the Provider / the Insurer | we | only if `we` is defined in the definitions clause |
| the Customer / the User / the Insured / the Policyholder | you | only if `you` is the chosen form of address |
| the Parties | we and you / the parties | check it still reads naturally in context |

If `we` and `you` aren't defined, don't introduce them quietly. Tell the user that adding the two definitions would let the whole document use them, and leave the decision to them — adding a definition changes substance, so it belongs to them, not to this skill.

---

## 6. Full-sentence examples

**Passive → active**

- BEFORE: `Personal data relating to the Customer is processed by the Company for the purpose of performing the Agreement.`
- AFTER: `We process your personal data to perform this Agreement.`
- What changed: passive → active; nominalization `performing` kept as a verb; party names → `we`/`you`. `Agreement` is a defined term, so it keeps the capital.

**Nested conditions → list** (the pattern that matters most)

- BEFORE: `You may cancel this Agreement within 14 days of the start date, unless the Service has been fully performed with your express consent before that period expires and you were informed in advance that you would lose the right to cancel.`
- AFTER:
  ```
  You can cancel this Agreement within 14 days of the start date.

  You can't cancel if all three of these are true:
  - we've fully provided the Service,
  - you gave clear consent to that before the 14 days were up,
  - we told you in advance that you'd lose the right to cancel.
  ```
- Audit note: in the original, the three conditions are **conjunctive** — the exception only applies once all three are met. The list must say so explicitly (`all three of these`). Three bullets with no connector would read as **alternative** conditions to an ordinary reader, which would change the legal effect. This is exactly the error the audit step exists to catch.

**`shall` resolved by context**

- BEFORE: `The Customer shall notify the Company of any defect within 30 days of delivery.`
- AFTER: `You must tell us about any defect within 30 days of delivery.`
- Note: here `shall` clearly means `must` — it's imposing an obligation on the customer, with a consequence for missing it elsewhere in the document. Not every `shall` resolves this cleanly; see §4.

**Split sentence**

- BEFORE: `In the event that a complaint is not resolved within 14 days of receipt, it shall be deemed upheld, without prejudice to clause 9.`
- AFTER: `We have 14 days to resolve your complaint, starting from when we receive it. If we don't resolve it in that time, we treat it as upheld. Clause 9 sets out the exceptions.`
- What changed: split into three sentences; passive → active; `in the event that` → the sentence restructured around `if`; `without prejudice to` → an explicit pointer. The reference to clause 9 stays and still governs the same rule.

---

## 7. UK/US drafting pitfalls

**Spelling and terminology drift.** A document that mixes UK and US conventions usually means a group-company template that was never localized — flag it as its own finding in a multi-document audit, not just a typo.

| UK | US |
|---|---|
| programme | program |
| licence (noun) / license (verb) | license (both) |
| judgement or judgment (both used) | judgment |
| cancellation | cancellation (same, but check doubled consonants elsewhere: travelling/traveling) |
| Ltd / plc | Inc / LLC / Corp |
| solicitor / barrister | attorney / lawyer |
| £ | $ — and specify which currency if a US entity's contract references a non-USD amount |
| VAT | sales tax (not equivalent — flag if a US rewrite assumes they are) |

**`shall` persists more in US drafting culture** than in modern UK drafting, where "must"/"will" conventions have made more headway (helped along by the Consumer Rights Act 2015's plain-language requirement). Don't assume a `shall`-heavy document is unusual just because it's UK-facing — check the governing-law clause before concluding anything about drafting culture from vocabulary alone.

**`provided that`** is genuinely ambiguous in both traditions (see §1) — don't let jurisdiction assumptions substitute for reading the clause.

**Governing law ≠ target audience.** A UK-governed contract can be written for a US audience and vice versa (e.g., a UK insurer's US-facing travel policy). Match the readability metric and spelling convention to the audience the text will actually be read by, and flag if that's unclear from context — ask the user rather than guessing.
