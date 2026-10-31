# Audyt — zachowanie znaczenia i spójność między dokumentami

## Spis treści
1. Po co ten etap
2. Lista kontrolna dla pojedynczego fragmentu
3. Metoda porównania warunków zagnieżdżonych
4. Segregacja flag
5. Audyt spójności między dokumentami
6. Niezależny przegląd

---

## 1. Po co ten etap

Zagrożeniem w tej pracy nie jest niezgrabna polszczyzna. Jest nim wersja, która czyta się świetnie i po cichu zmienia to, co przepis robi. Typowe przypadki:

- pominięty kwalifikator, bo wydłużał zdanie
- `może` zamienione na `musi`, bo strona czynna brzmiała stanowczo
- dwa warunki łączne przedstawione jako alternatywne
- wyjątek, którego zasięg się poszerzył, gdy wyciągnięto go do osobnego zdania
- wieloznaczność rozstrzygnięta przez wybór odczytania, które łatwiej się formułowało
- obowiązek zamieniony w prośbę (`jest obowiązany` → `prosimy`), bo brzmiało cieplej
- pozycja wypadła z katalogu ustawowego albo krąg osób się przesunął (`inny pracownik` → `kolega z zespołu`)
- dopisane wzmocnienie lub ocena (`zawsze`, `z empatią`), których oryginał nie miał

Wszystkie trzy ostatnie wystąpiły w przeglądzie regulaminu pracy — przykłady w `wzorzec-redakcji.md`, sekcja 4.

Każdy z tych błędów czyta się jak ulepszenie. Właśnie dlatego audyt musi być osobnym, świadomym etapem, a nie poczuciem pewności w trakcie pisania.

Podejdź do tego kontradyktoryjnie: załóż, że w wersji nowej **są** błędy, i szukaj ich. Potwierdzenie, że "wygląda dobrze", nie jest audytem.

---

## 2. Lista kontrolna dla pojedynczego fragmentu

Dla każdej pary PRZED/PO:

1. **Obowiązki i prawa** — czy któreś przybyło, ubyło albo przeszło między stronami?
2. **Kto komu co jest winien** — czy podmiot każdego obowiązku jest ten sam?
3. **Modalność** — `może` / `musi` / `powinien` / `jest zobowiązany` / `ma prawo`. Ten sam stopień?
4. **Wyrazy zakresu** — `wyłącznie`, `jedynie`, `co najmniej`, `nie później niż`, `w szczególności`, `m.in.`, `odpowiednio`. Obecne, usunięte czy zmienione?
5. **Zasięg zastrzeżeń** — czy każde `z zastrzeżeniem` / `chyba że` / `o ile` ogranicza dokładnie to, co ograniczało?
6. **Warunki zagnieżdżone** — patrz metoda niżej. Porównuj jawnie, nigdy wrażeniowo.
7. **Liczby** — daty, terminy, kwoty, waluty, procenty, okresy przechowywania. Identyczne?
8. **Terminy zdefiniowane** — odtworzone dosłownie, z wielkimi literami, bez synonimów?
9. **Odesłania do przepisów** — `art.`, `ust.`, `pkt`, RODO, k.c., nazwane ustawy. Znak w znak?
10. **Nowa wieloznaczność** — czy wersja nowa dopuszcza odczytanie, którego oryginał nie dopuszczał?
11. **Numeracja** — ten sam numer, ta sama treść? Nic nie scalone, nie podzielone, nie przestawione?
12. **Katalogi i kręgi osób** — wypisz pozycje przed i po obok siebie. Każda przetrwała, z tym samym zakresem?
13. **Pola szablonu `{{…}}`** — każde nadal jest, raz, i wstawiona wartość pasuje gramatycznie w nowym zdaniu?
14. **Nazwy stron i forma zwracania się** — w obrębie ustępu jedna (`my`/`Ty` albo trzecia osoba w sankcjach), bez nowych nazw strony?

Wyniki zapisuj tak:

```
RYZYKO [WYSOKIE / ŚREDNIE / NISKIE] — § X ust. Y
Na czym polega zmiana: [jedno zdanie]
Skutek prawny: [jedno zdanie]
Rekomendacja: [przywrócić oryginał / poprawić tak: "…"]
```

**Wszystko oznaczone jako WYSOKIE wraca do brzmienia oryginalnego.** Czytelność nigdy nie wygrywa z wiernością.

---

## 3. Metoda porównania warunków zagnieżdżonych

Warunków zagnieżdżonych nie oceniaj przez przeczytanie. Wypisz je.

Osobno dla oryginału i dla wersji nowej wypisz:
- każdy warunek
- czy warunki są łączne (I) czy alternatywne (LUB)
- co następuje, gdy są spełnione
- co następuje, gdy nie są

Potem porównaj obie listy punkt po punkcie. Rozjazd w relacji I/LUB to najczęstszy i najpoważniejszy błąd w tej pracy, a przy pobieżnym czytaniu jest praktycznie niewidoczny.

Sygnały w polszczyźnie, które warto sprawdzić: `oraz` i `i` są łączne; `lub`, `albo`, `bądź` są alternatywne; `chyba że` wprowadza wyjątek od zasady głównej, a nie kolejny warunek; `o ile` wprowadza warunek uprzedni. Lista wypunktowana bez spójnika jest domyślnie wieloznaczna — zawsze napisz `wszystkie warunki` albo `którykolwiek z warunków`.

---

## 4. Segregacja flag

Pogrupuj flagi pod kątem czytającego, bo prawnik potrzebuje ich ułożonych według tego, co wymaga uwagi:

**Do prawnika — wymaga decyzji.** Odpowiedzialność, kary, własność intelektualna, jurysdykcja, prawo właściwe. Wszystko, gdzie podjęto próbę redakcji, a skutek prawny nie jest pewny.

**Wady oryginału.** Usterki znalezione w tekście źródłowym: terminy pisane wielką literą, ale niezdefiniowane; odesłania prowadzące donikąd; przepisy wzajemnie sprzeczne; definicje nigdy nieużyte. Istniały przed redakcją i warto je raportować osobno — często są najcenniejszym efektem całej pracy.

**Zostawione bez zmian.** Fragmenty pominięte i powód, żeby nikt nie uznał, że je przeoczono.

---

## 5. Audyt spójności między dokumentami

Wykonaj go po przepisaniu wszystkich dokumentów w zestawie. Wychwytuje wady niewidoczne przy pracy nad pojedynczym tekstem.

Raportuj:

1. **Mieszane formy zwracania się** — `Ty` / `Państwo` / `Użytkownik` / formy bezosobowe, w jednym dokumencie albo między dokumentami. Cytuj z lokalizacją.
2. **Mieszane nazwy organizacji** — `my` / `Usługodawca` / `Administrator` / `Spółka` / nazwa handlowa.
3. **Jedno pojęcie, kilka nazw** — `Konto` vs `profil` vs `konto użytkownika`; `Subskrypcja` vs `abonament` vs `plan`; `Treści` vs `materiały`. Wypisz wszystkie warianty i wskaż, który jest terminem zdefiniowanym.
4. **Jedna nazwa, kilka pojęć** — jedno słowo użyte w dwóch znaczeniach. Poważniejsze niż punkt 3, bo tworzy realną wieloznaczność, a nie tylko nieporządek.
5. **Terminy używane, ale niezdefiniowane** — wielka litera sugeruje definicję, której nie ma w `§ definicje`.
6. **Terminy zdefiniowane, ale nieużywane** — kandydaci do usunięcia. Zgłoś, nie usuwaj.
7. **Sprzeczności między dokumentami** — regulamin mówi o 14 dniach, ekran zgody o 30; polityka prywatności wymienia inne kategorie danych niż ekran onboardingu; opis prywatności w sklepie nie zgadza się z polityką. **Raportuj jako RYZYKO PRAWNE, nie jako kwestię stylu.** To wady zgodności i najcenniejszy efekt tego audytu.
8. **Rozjazd rejestru** — formalne dokumenty obok potocznie napisanych mikrotekstów.

Format:

```
| Problem | Typ (1–8) | Warianty | Gdzie (plik + cytat) | Rekomendacja |
```

Tylko raportuj. Nie poprawiaj pozycji z kategorii 7 — wymagają decyzji, która wersja jest prawidłowa, a ta należy do użytkownika i jego prawnika.

---

### Kontrole z przeglądu prawnego umów

Zgłaszaj flagą, nie przebudowuj sam (szczegóły: `wzorzec-umowy.md`):

- Nazwa roli albo trzecia osoba w treści umowy, która w § 1 definiuje `my` / `Wy` / `Ty` — także w klauzulach płatności, kar, odpowiedzialności i we frazach z formularza.
- Kara, zapłata albo odpowiedzialność wobec osoby, która nie jest stroną umowy.
- Prawo właściwe albo sąd w osobnym paragrafie zamiast w postanowieniach końcowych.
- Paragraf albo wariant, który nie zmienia praw ani obowiązków.
- Brak zakończenia umowy albo zakończenie niepasujące do jej typu.
- Luka tam, gdzie strony mogą niczego nie ustalić — bez odesłania do przepisów.
- Ta sama klauzula wyraźnie uboższa w jednym dokumencie zestawu niż w innym (tabela „element × dokument”).
- Regulamin bez zastrzeżenia o pierwszeństwie ustaleń indywidualnych tam, gdzie mogą wystąpić.

## 6. Niezależny przegląd

Jeśli sposób pracy na to pozwala, przeprowadź audyt w świeżym kontekście, który nie widział redakcji — nowa sesja albo inny model. Model sprawdzający własne zmiany ma skłonność do ich obrony; osoba bez emocjonalnego związku ze sformułowaniem znajduje pominięty kwalifikator.

Gdy to niemożliwe, zrekompensuj to pracą ściśle według listy kontrolnej, punkt po punkcie, zamiast ponownego czytania "na wrażenie". Lista istnieje właśnie dlatego, że wrażenia są tu zawodne.

Audyt całego zestawu naraz ma jedną zaletę, którą warto zachować: część rozjazdów widać dopiero w skali — na przykład ten sam przepis uproszczony w dwóch dokumentach na dwa różne sposoby.
