# legal_design_pl

**Umiejętności (skills) dla Claude, które przepisują teksty prawne na prosty język — nie zmieniając ich znaczenia prawnego.**

To repozytorium zawiera dwie siostrzane umiejętności:

| Umiejętność | Język tekstu | Podstawa prawna |
|---|---|---|
| [`legal-design-pl`](legal-design-pl/) | polski | RODO art. 12, art. 385 §2 k.c., DSA, EAA |
| [`legal-design-en`](legal-design-en/) | angielski (UK + US) | Consumer Rights Act 2015, UK GDPR, SEC Plain English Rule, stanowe ustawy o czytelności OWU, NY GOL §5-702 |

Obie działają według tej samej metody: **zmienia się język, znaczenie nie**. Cztery kroki — ustalenie stylu, przepisanie, kontradyktoryjny audyt znaczenia, szacunek czytelności — i domyślny format odpowiedzi w postaci tabeli PRZED/PO, żeby przegląd prawnika był szybki. Szczegóły metody, w tym to, czego umiejętności świadomie **nie** robią (nie przebudowują dokumentów, nie rozstrzygają wieloznaczności), są opisane w README każdej z nich — techniki językowe są specyficzne dla każdego języka, więc nie są tu duplikowane.

> 🇬🇧 English: [README.en.md](README.en.md)

---

## Instalacja

```bash
git clone https://github.com/Adudzinski/legal_design_pl.git ~/legal_design_pl
ln -s ~/legal_design_pl/legal-design-pl ~/.claude/skills/legal-design-pl
ln -s ~/legal_design_pl/legal-design-en ~/.claude/skills/legal-design-en
```

Zainstaluj jedną albo obie — dowiązania symboliczne są niezależne. Dla aplikacji desktopowej Claude.ai / Cowork pobierz plik `.skill` z odpowiedniego podkatalogu (`legal-design-pl/legal-design-pl.skill` albo `legal-design-en/legal-design-en.skill`) i wgraj go w Settings → Capabilities → Skills.

Szczegóły instalacji, przykłady użycia i pełen opis metody: README każdej umiejętności — [polski](legal-design-pl/README.md) / [angielski](legal-design-en/README.md).

## Licencja

[MIT](LICENSE) — obejmuje całe repozytorium, obie umiejętności.
