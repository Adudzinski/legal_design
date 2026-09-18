---
name: legal-design-pl
description: Przepisuje polskie teksty prawne na prostą polszczyznę (prosty język / legal design), nie zmieniając ich znaczenia prawnego. Używaj tej umiejętności zawsze, gdy użytkownik pracuje z polskim tekstem prawnym lub quasi-prawnym i chce, żeby był jaśniejszy, prostszy, bardziej przyjazny albo czytelny — regulamin, polityka prywatności, klauzula informacyjna RODO, zgody, cookies, OWU, umowa, warunki subskrypcji, ekrany zgód, mikroteksty w aplikacji, e-maile transakcyjne. Uruchamiaj ją także wtedy, gdy użytkownik nie mówi wprost "legal design" ani "prosty język" — sformułowania takie jak "uprość ten regulamin", "napisz to po ludzku", "to jest napisane prawniczym bełkotem", "zrób to czytelniejsze", "simplify our terms" albo wgrana polska umowa z prośbą o uproszczenie też oznaczają, że ta umiejętność ma zastosowanie. Używaj jej również do audytu istniejących dokumentów pod kątem prostego języka, do sprawdzania spójności terminologii w zestawie dokumentów oraz do nauczania tych technik.
---

# Legal Design PL — przepisywanie polskich tekstów prawnych na prostą polszczyznę

Przekształć **język** polskiego tekstu prawnego tak, żeby zwykła dorosła osoba mogła go przeczytać na telefonie — przy zachowaniu identycznego skutku prawnego.

## Zasada nadrzędna

**Zmienia się język. Znaczenie nie.**

Po redakcji tekst musi wywoływać dokładnie te same skutki prawne co przed nią — te same obowiązki, prawa, warunki, terminy, wyjątki i zakresy.

Jeśli fragmentu nie da się uprościć bez ryzyka zmiany znaczenia, **nie upraszczaj go**. Zostaw oryginał i oznacz `[FLAGA]` wraz z powodem. Trudne zdanie pozostawione bez zmian to mały koszt. Uproszczone zdanie, które po cichu przesuwa odpowiedzialność, to koszt poważny. Osoby korzystające z tej umiejętności zwykle wysyłają te dokumenty realnym klientom, więc wybór ostrożniejszy jest tu wyborem właściwym.

To ważniejsze, niż się wydaje. Naturalna pokusa przy upraszczaniu tekstu prawnego polega na **rozstrzyganiu wieloznaczności** — na uznaniu, co niejasny przepis "pewnie znaczy", i napisaniu tego. To już nie redakcja, tylko tworzenie treści, i jest poza zakresem tej umiejętności. Wieloznaczność się oznacza, nigdy nie rozstrzyga.

## Krok 1 — Ustal styl, zanim cokolwiek przepiszesz

Dwie decyzje wiążą każde kolejne zdanie. Zapytaj użytkownika, jeśli nie wynikają z kontekstu:

1. **Jak organizacja mówi o sobie?** Zalecane: `my` / `nas` / `nasz`. Działa to tylko wtedy, gdy słownik definicji zawiera odpowiedni wpis (`my / [Spółka] – [pełna nazwa, KRS…]`). Bez takiej definicji zostaw `Usługodawca` / `Administrator` i powiedz użytkownikowi, co zyskałby po jej dodaniu.
2. **Jak zwracamy się do odbiorcy?** Zalecane w aplikacjach i usługach konsumenckich: `Ty` / `Ciebie` / `Twój`. Alternatywa to `Państwo` z czasownikiem w 3. osobie — pasuje do B2B i kontekstów formalnych. Wybierz jedno i nigdy nie mieszaj.

Zdefiniowanie `my` i `Ty` usuwa więcej kancelaryzmów niż wszystkie pozostałe techniki razem wzięte, bo rozpuszcza konstrukcje bierne, które polszczyzna prawnicza buduje wokół abstrakcyjnych nazw stron.

Zbierz też przed startem listę **terminów zdefiniowanych** (z `§ definicje`). Trzeba je odtwarzać dosłownie i nigdy nie zamieniać na synonimy — nawet prostsze.

Jeśli użytkownik daje kilka dokumentów, styl obowiązuje we wszystkich. Rozjazd terminologii między regulaminem a ekranami zgód to realna wada, nie drobiazg stylistyczny.

## Krok 2 — Przepisz

Stosuj po kolei. Pełną listę zamian i przykłady znajdziesz w `references/phrasebook.md`.

**Zdania.** Jedno zdanie, jedna myśl. Cel: 15–20 wyrazów. Rozbijaj długie zdania złożone — ale tylko wtedy, gdy logika zostaje nietknięta. Gdy zdanie zawiera zagnieżdżone warunki (`jeżeli… chyba że… o ile…`), zamień je na listę wypunktowaną, a nie na osobne zdania. Rozbijanie zagnieżdżonych warunków na zdania to najczęstszy sposób, w jaki ginie znaczenie.

**Strona czynna.** `Dane są przetwarzane przez Administratora` → `Przetwarzamy Twoje dane`. Zawsze musi być jasne, kto co komu robi.

**Czasowniki zamiast rzeczowników odczasownikowych** (*rzeczowniki zombie* — rzeczowniki, które połknęły czasownik). `dokonać zapłaty` → `zapłacić`. `w celu dokonania weryfikacji` → `aby sprawdzić`. `następuje rozwiązanie umowy` → `umowa się kończy`.

**Formy osobowe zamiast bezosobowych.** Usuń `należy`, `trzeba`, `winno się` oraz formy na `-no` / `-to`. `Należy podać adres e-mail` → `Podaj swój adres e-mail`.

**Bez imiesłowów przysłówkowych** (`-ąc`, `-wszy`, `-łszy`). `Korzystając z aplikacji, akceptujesz…` → `Gdy korzystasz z aplikacji, akceptujesz…`

**Zamień kancelaryzmy.** `niniejszy` → `ten`; `w związku z powyższym` → `dlatego`; `z uwagi na fakt, iż` → `ponieważ`; `w przypadku gdy` → `jeśli`. Pełna lista w `references/phrasebook.md`. Unikaj łaciny. Rozwijaj skróty nieprawnicze (`m.in.`, `tj.`, `ww.`).

**Nagłówki mogą stać się pytaniami.** `Przetwarzanie danych` → `Jakie dane zbieramy?` To jedyna zmiana strukturalna dozwolona domyślnie.

## Krok 3 — Sprawdź znaczenie, zanim oddasz wynik

Przeczytaj każdy przepisany fragment obok oryginału i sprawdź punkt po punkcie. Pełna lista kontrolna i tryb pracy z zestawem dokumentów: `references/audit.md`.

Najważniejsze kontrole, bo to tam znaczenie realnie się wymyka:

- **Modalność.** `może` ≠ `musi` ≠ `powinien` ≠ `jest zobowiązany`. Zachowaj dokładnie ten sam stopień.
- **Wyrazy zakresu.** `wyłącznie`, `jedynie`, `co najmniej`, `nie później niż`, `w szczególności`, `m.in.` — każdy z nich zmienia to, co przepis obejmuje.
- **Zasięg zastrzeżeń.** `z zastrzeżeniem ust. 3` musi nadal ograniczać dokładnie to, co ograniczało.
- **Warunki zagnieżdżone.** Wypisz warunki z oryginału i z wersji nowej obok siebie i porównaj je jawnie. Nie oceniaj tego "na oko".
- **Liczby, daty, terminy, kwoty, okresy przechowywania** — identyczne.
- **Odesłania do przepisów** — znak w znak.
- **Terminy zdefiniowane** — bez parafrazy.
- **Nowa wieloznaczność** — czy wersja nowa dopuszcza odczytanie, którego oryginał nie dopuszczał?

## Krok 4 — Podaj poziom czytelności

Podaj szacunek i sposób weryfikacji. Cele dla tekstu konsumenckiego: **Jasnopis klasa 3–4**, **FOG 10–12**, **zdania ≤20 wyrazów**, **CEFR B2** jako poziom odniesienia, który da się obronić.

Odeślij użytkownika do jasnopis.pl i logios.pl, żeby zmierzył to porządnie — to narzędzia stworzone dla polszczyzny, a wyniki warto mieć zapisane. Jeśli fragment nie chce zejść niżej, przyczyną jest prawie zawsze jedno zdanie z trzema zagnieżdżonymi warunkami. Pomoże lista wypunktowana, a nie zmiana słownictwa.

## Format odpowiedzi

Domyślnie tabela porównawcza — to różnica między wersjami sprawia, że przegląd prawnika jest szybki i tani:

```
| Nr | PRZED | PO | Co zmieniłem | Flaga |
```

- `Nr` — jednostka redakcyjna (`§ 4 ust. 2 pkt 3`) albo klucz stringa (`consent_marketing_title`)
- `PRZED` — oryginał, dosłownie
- `PO` — wersja nowa albo `— bez zmian —`
- `Co zmieniłem` — maksymalnie 10 słów (`strona bierna → czynna; skrócono zdanie`)
- `Flaga` — puste albo `[FLAGA]` z powodem

Ujmij każdą jednostkę redakcyjną. Nie pomijaj żadnej i nie skracaj pracy zwrotem "reszta analogicznie".

Po tabeli wypisz flagi pogrupowane pod kątem prawnika, a potem szacunek czytelności.

Jeśli użytkownik prosi wyłącznie o czysty przepisany tekst, daj mu to — ale flagi wypisz i tak. Flag nie odtworzy samodzielnie.

## Zawsze oznacz zamiast poprawiać

- Fragmenty wieloznaczne, gdzie uproszczenie wymusiłoby wybór jednej interpretacji
- Niejasne odniesienia — do czego faktycznie odsyła `z zastrzeżeniem`, `powyższy`, `ten`
- Wszystko, co dotyczy odpowiedzialności, kar, własności intelektualnej, jurysdykcji i prawa właściwego
- Tekst, który wygląda na cytat z ustawy albo formułę wymaganą przepisami
- Każde uproszczenie, które zawęziłoby lub poszerzyło wyjątek

## Poza zakresem

Ta umiejętność zmienia język. Nie przebudowuje dokumentów. Nie dodawaj warstw `w skrócie`, ikon, tabel, osi czasu ani map decyzji; nie zmieniaj kolejności sekcji; nie usuwaj przepisów, które wyglądają na zbędne. To są uprawnione zabiegi legal design, ale dodają albo przenoszą treść i wymagają osobnej decyzji przejrzanej przez prawnika. Mieszanie "zrób to czytelnym" z "przebuduj to" jest właśnie tym mechanizmem, przez który dokumenty po cichu tracą przepisy.

Wspomnij użytkownikowi, że wzorzec dwuwarstwowy (proste streszczenie nad wiążącym tekstem) to standardowy następny krok — i że streszczenie musi być oznaczone jako informacyjne, z wyraźnym wskazaniem, że wiąże pełna treść.

## Praca na zestawie dokumentów

Przy kilku dokumentach pracuj po jednym, ale skończ wszystkie. Prowadź widoczną tabelę postępu (`OCZEKUJE` / `W TOKU` / `GOTOWE` / `ZABLOKOWANE`) i aktualizuj ją po każdym dokumencie. Nie kończ przedwcześnie zwrotem "pozostałe dokumenty są podobne" — krótkie teksty, jak zgody i etykiety przycisków, są zwykle najgorzej napisane i najczęściej czytane.

Gdy wszystkie dokumenty są gotowe, wykonaj audyt spójności międzydokumentowej z `references/audit.md`. Sprzeczności między dokumentami (regulamin mówi o 14 dniach, a ekran zgody o 30; opis prywatności w sklepie nie zgadza się z polityką prywatności) to ryzyka prawne i trzeba je raportować osobno od niespójności stylistycznych.

## Pliki pomocnicze

- `references/phrasebook.md` — pełna lista zamian kancelaryzmów, przykłady przed/po, pułapki właściwe dla polszczyzny
- `references/audit.md` — lista kontrolna zachowania znaczenia, audyt spójności między dokumentami, segregacja flag
- `references/context.md` — podstawa prawna prostego języka w Polsce (RODO art. 12, art. 385 §2 k.c., DSA, EAA/B2), cele czytelności, dokumenty wzorcowe. Czytaj, gdy użytkownik pyta, *po co* to robić, musi uzasadnić pracę albo uczy tej metody.
