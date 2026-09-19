# Audit — meaning preservation and cross-document consistency

## Contents
1. Why this step exists
2. Single-passage checklist
3. Comparing nested conditions
4. Flag triage
5. Cross-document consistency audit
6. Independent review

---

## 1. Why this step exists

The risk in this work isn't clumsy English. It's a rewrite that reads beautifully and quietly changes what a clause does. Typical failure modes:

- a qualifier dropped because it made the sentence longer
- `may` swapped for `must` because the active voice sounded more decisive
- two conjunctive conditions presented as if they were alternatives
- an exception whose scope widened when it was pulled out into its own sentence
- ambiguity resolved by picking whichever reading was easier to write
- `shall` mechanically replaced with `must` without checking which of its five possible meanings (§4 of `phrasebook.md`) the original actually carried

Every one of these reads like an improvement. That's exactly why the audit has to be a separate, deliberate pass — not a feeling of confidence while writing.

Work adversarially: assume the rewrite **has** errors and look for them. "This looks fine" is not an audit.

## 2. Single-passage checklist

For every BEFORE/AFTER pair:

1. **Obligations and rights** — did any get added, dropped, or shift between parties?
2. **Who owes what to whom** — is the subject of every obligation still the same party?
3. **Modality** — `must` / `will` / `may` / `should` / a leftover `shall`. Same strength as the original?
4. **Scope words** — `solely`, `exclusively`, `at least`, `no later than`, `including but not limited to`, `in particular`, `respectively`. Present, dropped, or changed?
5. **Reach of provisos** — does every `subject to`, `unless`, `except that`, `without prejudice to` still limit exactly what it limited?
6. **`provided that`** — resolved as `if` or `except that`? Check against context, not habit.
7. **Nested conditions** — see the method below. Compare explicitly, never by impression.
8. **Numbers** — dates, deadlines, amounts, currencies, percentages, retention periods. Identical?
9. **Defined terms** — reproduced verbatim, capitalization intact, no synonym substituted?
10. **Statutory cross-references** — section numbers, named acts, regulator citations. Character for character?
11. **New ambiguity** — does the rewrite admit a reading the original didn't?
12. **Numbering** — same clause number, same content? Nothing merged, split, or reordered?

Record results as:

```
RISK [HIGH / MEDIUM / LOW] — Clause X.Y
What changed: [one sentence]
Legal effect: [one sentence]
Recommendation: [revert to original / fix as: "…"]
```

**Anything rated HIGH goes back to the original wording.** Readability never outranks fidelity.

## 3. Comparing nested conditions

Don't evaluate nested conditions by reading them. List them out.

For the original and the rewrite, separately write down:
- each condition
- whether the conditions are conjunctive (AND) or disjunctive (OR)
- what happens when they're satisfied
- what happens when they're not

Then compare the two lists point by point. A mismatch in the AND/OR relationship is the most common and most serious error in this work, and it's nearly invisible on a casual read.

Signal words worth checking: `and` and `together with` are conjunctive; `or`, `either…or` are disjunctive; `unless` and `except that` introduce an exception to the main rule, not a further condition; `provided that` is ambiguous on its own (§7 of `phrasebook.md`) — resolve it from context, then make the resolution explicit in the rewrite. A bulleted list with no connector is ambiguous by default — always write `all of the following` or `any of the following`.

## 4. Flag triage

Group flags by what the reader needs, because a lawyer needs them sorted by what requires a decision:

**For the lawyer — needs a decision.** Liability, indemnity, intellectual property, jurisdiction, governing law. Anything where a rewrite was attempted but the legal effect isn't certain. Any `shall` whose intended meaning (§4 of `phrasebook.md`) couldn't be resolved from context.

**Defects in the original.** Problems found in the source text: capitalized terms that are never defined, cross-references that lead nowhere, internally contradictory provisions, definitions that are never used. These predate the rewrite and are worth reporting separately — often the most valuable output of the whole exercise.

**Left unchanged.** Passages skipped, with the reason, so nothing reads as an oversight.

## 5. Cross-document consistency audit

Run this after every document in the set has been rewritten. It catches defects invisible when working on one document at a time.

Report:

1. **Mixed forms of address** — `you` / `the Customer` / `the User` / impersonal constructions, within one document or across documents. Quote the location.
2. **Mixed organization names** — `we` / `the Company` / `the Provider` / a trading name.
3. **One concept, several names** — `Account` vs. `profile` vs. `user account`; `Subscription` vs. `plan` vs. `membership`; `Content` vs. `materials`. List every variant and flag which one is the defined term.
4. **One name, several concepts** — the same word used with two different meanings. More serious than #3, because it creates real ambiguity, not just inconsistency.
5. **Terms used but never defined** — a capitalized term with no entry in the Definitions clause.
6. **Terms defined but never used** — candidates for removal. Report, don't remove.
7. **Contradictions between documents** — terms of service say 14 days, the consent screen says 30; the privacy notice lists different data categories than the onboarding screen; the app-store privacy label doesn't match the privacy policy. **Report as a LEGAL RISK, not a style issue.** These are compliance defects and the most valuable output of this audit.
8. **Register drift** — formal legal documents sitting next to casually written microcopy.
9. **Jurisdiction drift** (specific to English-language sets) — mixed UK/US spelling or terminology (§7 of `phrasebook.md`), inconsistent currency symbols, a governing-law clause that doesn't match the spelling convention used elsewhere in the same document. Usually signals an unlocalized template.

Format:

```
| Issue | Type (1–9) | Variants | Where (file + quote) | Recommendation |
```

Report only. Don't fix items in category 7 or 9 yourself — they need a decision about which version is correct, and that decision belongs to the user and their lawyer.

## 6. Independent review

If the workflow allows it, run the audit in a fresh context that hasn't seen the rewrite — a new session, or a different reviewer. A model checking its own edits tends to defend them; someone with no attachment to the phrasing catches the dropped qualifier.

When that's not possible, compensate by working the checklist mechanically, point by point, rather than re-reading for a general impression. The checklist exists precisely because impressions are unreliable here.

Auditing the whole set at once has one advantage worth keeping: some inconsistencies only show up at scale — the same clause simplified two different ways in two different documents.
