# legal-design-en

**A Claude skill that rewrites English-language legal text into plain English — without changing its legal meaning.**

Terms of service, privacy policies, GDPR/UK GDPR notices, consent screens, cookie banners, insurance policies, loan agreements, subscription terms, employment contracts, in-app microcopy, transactional emails. Input is legalese; output is the same text, readable by an ordinary adult on a phone. Covers both **UK and US** drafting conventions and flags where they diverge.

> This skill is the English-language sibling of [`legal-design-pl`](../legal-design-pl/), which does the same job for Polish. See the [repository overview](../README.md) for how the two relate.

---

## Core rule

**The language changes. The meaning does not.**

After the rewrite, the text must produce exactly the same legal effect as before — the same obligations, rights, conditions, deadlines, exceptions and scope.

If a passage can't be simplified without risking a change in meaning, the skill **leaves it alone**, keeps the original, and marks it `[FLAG]` with a reason. A hard sentence left untouched is a small cost. A simplified sentence that quietly shifts liability is a serious one.

Ambiguity is **flagged**, never **resolved**. Deciding what an unclear clause "probably means" is drafting, not editing, and is out of scope.

---

## How it works

Four steps:

1. **Fix the voice.** How the organization refers to itself (`we` vs. `the Company`) and whether the document holds a consistent direct address (`you`) instead of drifting back to third-person entity-nouns (`the Customer`). Defined terms are collected up front and reproduced verbatim. The document's jurisdiction (UK or US — usually visible from the governing-law clause or spelling conventions) is identified before rewriting, since some techniques and citations differ.
2. **Rewrite.** Short sentences (under ~25 words), active voice, verbs instead of nominalizations (`make an application` → `apply`), archaic connectives cut (`heretofore`, `pursuant to`, `in the event that`), doublets collapsed (`null and void` → `void`). Nested conditions become bullet lists that state AND/OR explicitly, never separate sentences.
3. **Meaning audit.** A separate, adversarial pass: modality (the `shall`/`must`/`will`/`may` discipline — `shall` alone has generated well over a hundred appellate decisions on what it meant in a given clause), scope words (`solely`, `at least`, `including but not limited to`), the reach of provisos, AND/OR relationships in nested conditions, numbers and deadlines, statutory cross-references, new ambiguity. Anything rated HIGH risk reverts to the original wording.
4. **Readability estimate.** Flesch Reading Ease / Flesch-Kincaid Grade Level for a US audience (matching the metric written into state insurance-readability statutes); Automated Readability Index for a UK audience (matching UK insurance-industry guidance).

Default output is a before/after table — the diff is what makes a lawyer's review fast and cheap:

| No. | BEFORE | AFTER | What changed | Flag |
|---|---|---|---|---|
| Clause 4.2 | `Personal data relating to the Customer is processed by the Company for the purpose of performing the Agreement.` | `We process your personal data to perform this Agreement.` | passive → active; `we`/`you` | |

Flags grouped for a lawyer's attention, then the readability estimate, follow the table.

---

## What it deliberately does **not** do

The scope is narrow on purpose. The skill changes the **language layer** and does not redesign documents:

- no "in short" summary layers, icons, tables, timelines, or decision maps,
- no reordering of sections,
- no deleting provisions that look redundant,
- no resolving ambiguity.

Those are legitimate legal-design moves, but they add or move substance and need a separate, lawyer-reviewed decision. Mixing "make this readable" with "restructure this" is exactly how documents quietly lose provisions.

**This is not a substitute for a lawyer.** The output is review material, not a publishable document.

---

## Install

**Claude Code**

```bash
git clone https://github.com/Adudzinski/legal_design_pl.git ~/legal_design_pl
ln -s ~/legal_design_pl/legal-design-en ~/.claude/skills/legal-design-en
```

Or copy `SKILL.md` and `references/` into `.claude/skills/legal-design-en/` inside a project.

**Claude.ai / Cowork desktop app**

Download [`legal-design-en.skill`](legal-design-en.skill) and upload it under Settings → Capabilities → Skills. It's a packaged copy of the same files.

---

## Usage

The skill triggers on its own when a conversation involves English legal text and its clarity — "simplify this contract", "rewrite this in plain English", "this reads like legalese", or an uploaded English-language agreement with a request to make it readable.

It also handles document sets: one document at a time, with a visible progress table, followed by a **cross-document consistency audit** — mixed forms of address, one concept under several names, contradictions between documents (terms say 14 days, the consent screen says 30), and, specific to this skill's multi-jurisdiction scope, mixed UK/US spelling, terminology, or currency that signals an unlocalized template. Contradictions are reported as legal risk, not as a style issue.

---

## Repository layout

```
SKILL.md                  # main instructions: core rule, four steps, output format, scope
references/
  phrasebook.md           # legalese substitution tables, nominalization -> verb pairs,
                          # before/after examples, UK/US drafting pitfalls
  audit.md                # meaning-preservation checklist, nested-condition comparison
                          # method, cross-document audit, flag triage
  context.md              # legal basis in the UK and US, readability targets,
                          # exemplar documents, risk and criticism
legal-design-en.skill      # packaged version for the desktop app
```

---

## Readability targets

| Measure | Target | Where it applies |
|---|---|---|
| Flesch Reading Ease | 60–70 general consumer text; state insurance statutes set floors of 40 (most states), 45 (CT/FL/NY), or 50 (ME/MA/NC/VA/WI Medicare Supp) | US |
| Flesch-Kincaid Grade Level | roughly 8th–10th grade | US, secondary |
| Automated Readability Index (ARI) | grade 8 or below | UK insurance-industry guidance |
| Sentence length | under 25–29 words | both |

These formulas measure sentence and word length, not comprehension — treat a passing score as a floor to clear, not a substitute for the meaning audit in step 3.

---

## Why this is not just style

- **UK — Consumer Rights Act 2015, s.68** requires consumer-contract terms to be transparent (plain, intelligible, legible); **s.69** resolves any ambiguous term in the consumer's favour — ambiguity already works against the drafter, so precise plain drafting reduces exposure rather than creating it.
- **UK GDPR Art. 12(1)** requires clear and plain language in data-subject notices; the **FCA Consumer Duty**'s "consumer understanding" outcome requires firms to test communications for comprehension.
- **US — SEC Plain English Rule (17 CFR 230.421)** mandates short sentences, active voice, and no jargon in prospectuses. **NY General Obligations Law §5-702** requires clear, coherent, everyday language in consumer contracts, with a real per-violation penalty. **State insurance-readability statutes** are the most concrete US mandate — most require a Flesch Reading Ease score of at least 40.
- The federal **Plain Writing Act of 2010** is often cited but doesn't apply to private companies — it binds federal agencies only.
- **ISO 24495-2:2025**, "Plain language — Part 2: Legal communication," is the international standard behind this method.

Full discussion, exemplar documents, and criticism of the method: [`references/context.md`](references/context.md).

---

## License

Covered by the repository's [MIT license](../LICENSE).
