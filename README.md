# legal-design-pl

**Umiejętność (skill) dla Claude, która przepisuje polskie teksty prawne na prostą polszczyznę — nie zmieniając ich znaczenia prawnego.**

Regulamin, polityka prywatności, klauzula informacyjna RODO, zgody, cookies, OWU, umowa, ekrany zgód, mikroteksty w aplikacji, e-maile transakcyjne. Wejściem jest tekst napisany prawniczą polszczyzną, wyjściem — ten sam tekst, który zwykła dorosła osoba przeczyta na telefonie.

> 🇬🇧 English version: [README.en.md](README.en.md)

---

## Zasada nadrzędna

**Zmienia się język. Znaczenie nie.**

Po redakcji tekst musi wywoływać dokładnie te same skutki prawne co przed nią — te same obowiązki, prawa, warunki, terminy, wyjątki i zakresy.

Jeśli fragmentu nie da się uprościć bez ryzyka zmiany znaczenia, umiejętność **go nie upraszcza**. Zostawia oryginał i oznacza go `[FLAGA]` wraz z powodem. Trudne zdanie pozostawione bez zmian to mały koszt. Uproszczone zdanie, które po cichu przesuwa odpowiedzialność, to koszt poważny.

Wieloznaczność się **oznacza**, nigdy nie **rozstrzyga**. Zgadywanie, co niejasny przepis „pewnie znaczy", to już nie redakcja, tylko tworzenie treści.

---

## Jak to działa

Umiejętność prowadzi model przez cztery kroki:

1. **Ustalenie stylu.** Jak organizacja mówi o sobie (`my` vs `Usługodawca`) i jak zwraca się do odbiorcy (`Ty` vs `Państwo`). Te dwie decyzje wiążą każde kolejne zdanie i usuwają więcej kancelaryzmów niż wszystkie pozostałe techniki razem wzięte. Zbierana jest też lista terminów zdefiniowanych, których nie wolno parafrazować.
2. **Przepisanie.** Krótkie zdania (15–20 wyrazów), strona czynna, czasowniki zamiast rzeczowników zombie (`dokonać zapłaty` → `zapłacić`), formy osobowe zamiast `należy`, bez imiesłowów na `-ąc`, wymiana kancelaryzmów. Warunki zagnieżdżone trafiają na listę wypunktowaną, nie do osobnych zdań.
3. **Audyt znaczenia.** Osobny, kontradyktoryjny etap: modalność (`może` ≠ `musi`), wyrazy zakresu (`wyłącznie`, `co najmniej`, `w szczególności`), zasięg zastrzeżeń, relacje I/LUB w warunkach, liczby i terminy, odesłania do przepisów, nowa wieloznaczność. Wszystko ocenione jako ryzyko WYSOKIE wraca do brzmienia oryginalnego.
4. **Poziom czytelności.** Szacunek plus wskazanie, jak zmierzyć go porządnie (jasnopis.pl, logios.pl).

Domyślny format odpowiedzi to tabela porównawcza — to różnica między wersjami sprawia, że przegląd prawnika jest szybki i tani:

| Nr | PRZED | PO | Co zmieniłem | Flaga |
|---|---|---|---|---|
| § 4 ust. 2 | `Dane osobowe Użytkownika są przetwarzane przez Administratora w celu realizacji Umowy.` | `Przetwarzamy Twoje dane osobowe, aby wykonać Umowę.` | strona bierna → czynna; `my`/`Ty` | |

Po tabeli — flagi pogrupowane pod kątem prawnika i szacunek czytelności.

---

## Czego umiejętność **nie** robi

To jest świadomie wąski zakres. Umiejętność zmienia **warstwę językową** i nie przebudowuje dokumentów:

- nie dodaje warstw „w skrócie", ikon, tabel, osi czasu ani map decyzji,
- nie zmienia kolejności sekcji,
- nie usuwa przepisów, które wyglądają na zbędne,
- nie rozstrzyga wieloznaczności.

To są uprawnione zabiegi legal design, ale dodają albo przenoszą treść i wymagają osobnej decyzji przejrzanej przez prawnika. Mieszanie „zrób to czytelnym" z „przebuduj to" jest właśnie tym mechanizmem, przez który dokumenty po cichu tracą przepisy.

**To narzędzie nie zastępuje prawnika.** Wynik jest materiałem do przeglądu, nie dokumentem gotowym do publikacji.

---

## Instalacja

### Claude Code

```bash
git clone https://github.com/Adudzinski/legal_design_pl.git ~/.claude/skills/legal-design-pl
```

Albo dla pojedynczego projektu — skopiuj `SKILL.md` i katalog `references/` do `.claude/skills/legal-design-pl/` w repozytorium projektu.

### Claude.ai / Cowork (aplikacja desktopowa)

Pobierz plik [`legal-design-pl.skill`](legal-design-pl.skill) i wgraj go w ustawieniach umiejętności (Settings → Capabilities → Skills). To spakowana kopia tych samych plików.

---

## Jak używać

Umiejętność uruchamia się sama, gdy rozmowa dotyczy polskiego tekstu prawnego i jego zrozumiałości. Nie trzeba mówić „legal design" ani „prosty język" — wystarczy:

- „Uprość ten regulamin."
- „Napisz tę politykę prywatności po ludzku."
- „To jest napisane prawniczym bełkotem, popraw to."
- „Sprawdź, czy terminologia w tych czterech dokumentach się zgadza."
- „Zrób audyt tego regulaminu pod kątem prostego języka."

Działa też na zestawach dokumentów: przepisuje po jednym, prowadzi widoczną tabelę postępu i na koniec wykonuje **audyt spójności międzydokumentowej** — wyłapuje mieszane formy zwracania się, jedno pojęcie pod kilkoma nazwami i sprzeczności między dokumentami (regulamin mówi o 14 dniach, ekran zgody o 30). Sprzeczności są raportowane jako ryzyko prawne, nie jako kwestia stylu.

---

## Struktura repozytorium

```
SKILL.md                  # główne instrukcje: zasada, cztery kroki, format odpowiedzi, zakres
references/
  phrasebook.md           # pełna lista zamian kancelaryzmów, rzeczowniki zombie,
                          # przykłady przed/po, pułapki właściwe dla polszczyzny
  audit.md                # lista kontrolna zachowania znaczenia, metoda porównania
                          # warunków zagnieżdżonych, audyt spójności, segregacja flag
  context.md              # podstawa prawna prostego języka w PL i UE, cele czytelności,
                          # dokumenty wzorcowe, ryzyko i krytyka
legal-design-pl.skill     # spakowana wersja do wgrania w aplikacji
```

Pliki z `references/` są wczytywane w miarę potrzeby — model sięga po nie wtedy, gdy są potrzebne, zamiast trzymać wszystko w kontekście na starcie.

---

## Cele czytelności

| Miara | Cel dla tekstu konsumenckiego | Narzędzie |
|---|---|---|
| Długość zdania | ≤ 15–20 wyrazów | dowolne |
| Klasa trudności Jasnopisu | 3–4 (5 to granica) | [jasnopis.pl](https://jasnopis.pl) |
| Indeks FOG | 10–12 | [logios.pl](https://logios.pl) |
| CEFR | B2 | — |

Dla kontekstu: polskie ustawy i rozporządzenia UE przekraczają FOG 20 (poziom doktorski), prasa ogólna to około 12. Typowy skopiowany regulamin plasuje się znacznie powyżej tego, co konsument jest w stanie przeczytać.

Angielskie wskaźniki czytelności się tu nie przenoszą — polska morfologia zmienia zachowanie heurystyk liczących sylaby. Jasnopis i Logios są stworzone dla polszczyzny.

---

## Dlaczego to nie jest tylko kwestia stylu

- **RODO art. 12 ust. 1** wymaga informacji sformułowanych jasnym i prostym językiem. To obowiązek, nie zalecenie.
- **Art. 385 § 2 k.c.** nakazuje tłumaczyć niejednoznaczne postanowienia wzorca **na korzyść konsumenta**. Wieloznaczność już teraz działa przeciwko autorowi wzorca — jasność zmniejsza ryzyko, a nie je tworzy.
- **Art. 385¹ k.c.** stosuje wyłączenie dla świadczenia głównego tylko przy jednoznacznym sformułowaniu.
- **DSA art. 14** wymaga warunków sformułowanych językiem jasnym, prostym i przyjaznym.
- **Europejski akt o dostępności** (w Polsce od 28 czerwca 2025 r.) nakłada m.in. na banki obowiązek polszczyzny na poziomie **CEFR B2** w dokumentach detalicznych.
- **ISO 24495-2:2025** — „Plain language — Part 2: Legal communication" — to międzynarodowa norma dla tej pracy.

Szersze omówienie, wraz z dokumentami wzorcowymi (certyfikowane OWU PZU, Projekt.Prawny, Pracownia Prostej Polszczyzny UWr) i krytyką metody, znajduje się w [`references/context.md`](references/context.md).

---

## Licencja

[MIT](LICENSE) — używaj, zmieniaj i rozpowszechniaj, zachowując informację o autorstwie.
