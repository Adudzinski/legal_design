# legal-design-pl

**A Claude skill that rewrites Polish legal texts into plain Polish — without changing their legal meaning.**

Terms of service, privacy policies, GDPR notices, consent screens, cookie banners, insurance terms (OWU), contracts, in-app microcopy, transactional emails. Input is text written in legalese; output is the same text, readable by an ordinary adult on a phone.

The skill itself, and everything it produces, is **in Polish** — it encodes Polish-specific plain-language technique (kancelaryzmy, zombie nouns, `Ty` vs `Państwo` forms, Jasnopis/FOG targets, Polish statutory basis). This page exists so the repository can be found and understood in English.

> 🇵🇱 Polska wersja: [README.md](README.md)

---

## Core rule

**The language changes. The meaning does not.**

After the rewrite, the text must produce exactly the same legal effect as before — the same obligations, rights, conditions, deadlines, exceptions and scopes.

If a passage cannot be simplified without risking a change in meaning, the skill **leaves it alone**, keeps the original and marks it `[FLAGA]` with a reason. A hard sentence left untouched is a small cost. A simplified sentence that quietly shifts liability is a serious one.

Ambiguity is **flagged**, never **resolved**. Deciding what an unclear provision "probably means" is authoring, not editing, and is out of scope.

---

## How it works

Four steps:

1. **Fix the voice.** How the organization refers to itself (`my` vs `Usługodawca`) and how it addresses the reader (informal `Ty` vs formal `Państwo`). These two decisions bind every sentence that follows and remove more legalese than all other techniques combined. Defined terms are collected up front and must be reproduced verbatim — never swapped for a simpler synonym.
2. **Rewrite.** Short sentences (15–20 words), active voice, verbs instead of nominalizations (`dokonać zapłaty` → `zapłacić`), personal forms instead of impersonal `należy`, no adverbial participles, legalese substitutions. Nested conditions become bullet lists rather than separate sentences — splitting them into sentences is the most common way meaning is lost.
3. **Meaning audit.** A separate, adversarial pass: modality (`może` ≠ `musi`), scope words (`wyłącznie`, `co najmniej`, `w szczególności`), the reach of provisos, AND/OR relations in conditions, numbers and deadlines, statutory cross-references, newly introduced ambiguity. Anything rated HIGH risk reverts to the original wording.
4. **Readability estimate,** plus how to measure it properly with Polish-specific tools (jasnopis.pl, logios.pl).

The default output is a before/after table (`Nr | PRZED | PO | Co zmieniłem | Flaga`), because the diff is what makes lawyer review fast and cheap. Flags follow, grouped for a lawyer's attention.

---

## What it deliberately does **not** do

The scope is narrow on purpose. The skill changes the **language layer** and does not redesign documents:

- no "in short" summary layers, icons, tables, timelines or decision maps,
- no reordering of sections,
- no deleting provisions that look redundant,
- no resolving ambiguity.

Those are legitimate legal design moves, but they add or move substance and need a separate, lawyer-reviewed decision. Mixing "make this readable" with "restructure this" is exactly how documents quietly lose provisions.

**This is not a substitute for a lawyer.** The output is review material, not a publishable document.

---

## Install

**Claude Code**

```bash
git clone https://github.com/Adudzinski/legal_design_pl.git ~/.claude/skills/legal-design-pl
```

Or copy `SKILL.md` and `references/` into `.claude/skills/legal-design-pl/` inside a project.

**Claude.ai / Cowork desktop app**

Download [`legal-design-pl.skill`](legal-design-pl.skill) and upload it under Settings → Capabilities → Skills. It is a packaged copy of the same files.

---

## Usage

The skill triggers on its own whenever a conversation involves a Polish legal text and its clarity — "uprość ten regulamin", "napisz to po ludzku", "simplify our terms", or an uploaded Polish contract with a request to make it readable.

It also handles document sets: one document at a time, with a visible progress table, followed by a **cross-document consistency audit** that catches mixed address forms, one concept under several names, and contradictions between documents (terms say 14 days, the consent screen says 30). Contradictions are reported as legal risk, not as a style issue.

---

## Repository layout

```
SKILL.md                  # main instructions: core rule, four steps, output format, scope
references/
  phrasebook.md           # legalese substitution tables, zombie nouns, before/after
                          # examples, Polish-specific traps
  audit.md                # meaning-preservation checklist, nested-condition comparison
                          # method, cross-document audit, flag triage
  context.md              # legal basis for plain language in PL/EU, readability targets,
                          # exemplar documents, risks and criticism
legal-design-pl.skill     # packaged version for the app
```

Files in `references/` are loaded on demand rather than kept in context from the start.

---

## Readability targets

| Measure | Target for consumer text | Tool |
|---|---|---|
| Sentence length | ≤ 15–20 words | any |
| Jasnopis difficulty class | 3–4 (5 is the limit) | [jasnopis.pl](https://jasnopis.pl) |
| FOG index | 10–12 | [logios.pl](https://logios.pl) |
| CEFR | B2 | — |

English readability metrics do not transfer: Polish morphology changes how syllable-counting heuristics behave. Jasnopis and Logios are built for Polish.

---

## Why this is not just style

GDPR Art. 12(1) requires clear and plain language. Polish Civil Code Art. 385 § 2 construes ambiguous standard-form terms **against the drafter** — so ambiguity already works against you, and precise plain-language drafting usually *reduces* exposure. DSA Art. 14 requires clear, plain, user-friendly terms. The European Accessibility Act (in force in Poland since 28 June 2025) requires CEFR B2 Polish in retail banking documents. ISO 24495-2:2025 is the international standard for plain language in legal communication.

Full discussion, exemplar documents and criticism of the method: [`references/context.md`](references/context.md) (in Polish).

---

## License

[MIT](LICENSE)
