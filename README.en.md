# legal_design_pl

**Claude skills that rewrite legal text into plain language — without changing its legal meaning.**

This repository holds two sibling skills:

| Skill | Text language | Legal basis |
|---|---|---|
| [`legal-design-pl`](legal-design-pl/) | Polish | GDPR Art. 12, Polish Civil Code art. 385 §2, DSA, EAA |
| [`legal-design-en`](legal-design-en/) | English (UK + US) | Consumer Rights Act 2015, UK GDPR, SEC Plain English Rule, US state insurance-readability statutes, NY GOL §5-702 |

Both follow the same method: **the language changes, the meaning does not**. Four steps — fix the voice, rewrite, run an adversarial meaning audit, give a readability estimate — with a default before/after table output so a lawyer's review stays fast. The full method, including what each skill deliberately does **not** do (no document restructuring, no resolving ambiguity), is documented in each skill's own README — the language-specific technique doesn't duplicate across the two.

> 🇵🇱 Polski: [README.md](README.md)

---

## Install

```bash
git clone https://github.com/Adudzinski/legal_design_pl.git ~/legal_design_pl
ln -s ~/legal_design_pl/legal-design-pl ~/.claude/skills/legal-design-pl
ln -s ~/legal_design_pl/legal-design-en ~/.claude/skills/legal-design-en
```

Install one or both — the symlinks are independent. For the Claude.ai / Cowork desktop app, download the `.skill` file from the relevant subfolder (`legal-design-pl/legal-design-pl.skill` or `legal-design-en/legal-design-en.skill`) and upload it under Settings → Capabilities → Skills.

Install details, usage examples, and the full method: each skill's own README — [Polish](legal-design-pl/README.md) / [English](legal-design-en/README.md).

## License

[MIT](LICENSE) — covers the whole repository, both skills.
