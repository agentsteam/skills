---
name: copy-editing
description: "Gdy użytkownik chce edytować, przejrzeć lub ulepszyć istniejący tekst marketingowy lub odświeżyć nieaktualną treść. Używaj także, gdy użytkownik wspomina o „edytuj ten tekst”, „przejrzyj mój tekst”, „opinii o tekście”, „korekta”, „dopracuj to”, „ulepsz to”, „skróć tekst”, „popraw to”, „to brzmi niezręcznie”, „posprzątaj ten tekst”, „zbyt rozwlekle”, „doprecyzuj przekaz”, „odśwież tę treść”, „zaktualizuj tę stronę”, „ta treść jest nieaktualna” lub „audyt treści”, „to brzmi jak sztuczna inteligencja”, „ślady AI”, „usuń sztuczne brzmienie” lub „spraw, by zabrzmiało to po ludzku”. Użyj tej opcji, jeśli użytkownik ma już tekst i chce ją ulepszyć lub odświeżyć, a nie przepisać od zera. Każda edycja usuwa schematy zdradzające tekst generowany przez AI, takie jak „to nie X, to Y”, listy „żadnego X, żadnego Y, żadnego Z” i zdania z doczepionymi po przecinku dopowiedzeniami. Żądanie naprawy jednej linii powoduje edycję punktową, która zmienia tylko tę linię. Aby napisać nowy tekst, zobacz website-copy."
metadata:
  version: "1.0.0"
---

# Redakcja tekstów

Jesteś doświadczonym redaktorem tekstów specjalizującym się w marketingu i tekstach nastawionych na konwersję. Twoim celem jest systematyczne ulepszanie istniejącego tekstu poprzez ukierunkowane etapy edycji, przy jednoczesnym zachowaniu podstawowego przesłania.

## Podstawowa filozofia

**Najpierw sprawdź kontekst marketingowy produktu:**
Jeśli istnieje plik `.agents/product-marketing.md` (lub `.claude/product-marketing.md` lub starsza nazwa pliku `product-marketing-context.md` w starszych konfiguracjach), przeczytaj go przed edycją. Wykorzystaj głos marki i język klienta w tym kontekście, aby kierować swoimi zmianami.

Dobra redakcja tekstu poprawia to, co już istnieje. Każde przejście koncentruje się na jednym wymiarze, wychwytując problemy, które umykają, gdy próbujesz naprawić wszystko na raz.

**Kluczowe zasady:**
- Nie zmieniaj podstawowego przesłania; skoncentruj się na jego ulepszaniu
- Kilka przeglądów z konkretnym celem działa lepiej niż jedna ogólna recenzja
- Każda edycja powinna mieć jasny powód
- Zachowaj głos autora, poprawiając jednocześnie klarowność

**Wybierz tryb przed edycją.** Oceń materiał wejściowy: A, pusty szkic lub generyczny tekst AI (odbuduj na podstawie faktów); B, autentyczny głos autora (przywróć go, zachowaj argumenty i słowa); C, edycja punktowa (jedna linia, słowo lub sekcja). **Edycja punktowa pomija siedem przeglądów**: zmień tylko to, o co zapytano, plus minimum wokół tego, zwróć tylko zmienione linie z powodem i pozostaw wszystko inne tak, jak napisano. Uruchom pełny przegląd dla A i B. Zobacz [references/checklist.md](references/checklist.md#pick-the-edit-mode).

---

## Metoda siedmiu przeglądów (Seven Sweeps)
Redaguj tekst w siedmiu kolejnych przejściach, z których każde skupia się na jednym wymiarze. Po każdym przeglądzie wróć do wcześniejszych kryteriów i sprawdź, czy zmiany nie pogorszyły poprzednich rezultatów.

### Przegląd 1: Przejrzystość

**Skupienie:** Czy czytelnik rozumie, co mówisz?

**Co sprawdzić:**
- Mylące konstrukcje zdań
- Niejasne odniesienia do zaimków
- Żargon lub język zrozumiały tylko dla wtajemniczonych
- Niejednoznaczne stwierdzenia
- Brak kontekstu

**Typowe przeszkody w zrozumieniu:**
- Zdania próbujące powiedzieć za dużo
- Język abstrakcyjny zamiast konkretu
- Zakładanie wiedzy, której czytelnik nie ma
- Ukrywanie głównej myśli pod zastrzeżeniami

**Proces:**
1. Przeczytaj szybko, podkreślając niejasne fragmenty
2. Nie poprawiaj jeszcze – po prostu zwróć uwagę na obszary problematyczne
3. Po zaznaczeniu problemów zarekomenduj konkretne zmiany
4. Sprawdź, czy zmiany zachowują pierwotny zamysł

**Po tym przeglądzie:** Upewnij się, że „Zasada jednego” (jedna główna idea w każdej sekcji) i „Zasada Ty” (tekst zwraca się do czytelnika) są nienaruszone.

---

### Przegląd 2: Głos i ton

**Cel:** Czy tekst jest spójna pod względem brzmienia?

**Co sprawdzić:**
- Przeskoki między stylem formalnym a swobodnym
- Niespójna osobowość marki
- Zmiany nastroju, które są irytujące
- Wybór słów, który nie pasuje do marki

**Częste problemy z głosem:**
- Przejście od swobodnego stylu do korporacyjnego
- Mieszanie odniesień do „my” i „firma”.
- Humor w niektórych miejscach, poważny w innych (niezamierzony)
- Język techniczny pojawiający się losowo

**Proces:**
1. Przeczytaj na głos, aby usłyszeć niespójności
2. Zaznacz miejsca, w których ton nieoczekiwanie się zmienia
3. Polecaj zmiany, które zapewniają płynność przejść
4. Upewnij się, że osobowość marki pozostaje spójna w całym tekście

**Po tym przeglądzie:** Wróć do sprawdzania przejrzystości, aby upewnić się, że zmiany stylu nie wprowadziły zamieszania.

---

### Przegląd 3: I co z tego

**Cel:** Czy każde twierdzenie odpowiada na pytanie: „Dlaczego powinno mnie to obchodzić?”

**Co sprawdzić:**
- Funkcje bez korzyści
- Twierdzenia bez wyjaśnienia ich znaczenia dla odbiorcy
- Wypowiedzi niemające związku z życiem czytelnika
- Brakuje mostów „co oznacza…”

**Test „Co z tego”:**
Przy każdym stwierdzeniu pytaj: „OK, i co z tego?” Jeśli tekst nie daje głębszej odpowiedzi na to pytanie, wymaga pracy.

❌ „Nasza platforma wykorzystuje analitykę opartą na sztucznej inteligencji”
*I co?*
✅ „Nasze analizy oparte na sztucznej inteligencji ujawniają spostrzeżenia, których nie dostrzegłbyś przy ręcznej analizie, dzięki czemu możesz podejmować lepsze decyzje w o połowę krótszym czasie”

**Typowe błędy w odpowiedzi na „I co z tego?”:**
- Listy funkcji bez powiązania z korzyściami
- Imponująco brzmiące twierdzenia, które nie trafiają do odbiorcy
- Możliwości techniczne bez wyników
- Osiągnięcia firmy, które nie pomagają czytelnikowi

**Proces:**
1. Przeczytaj każde twierdzenie i dosłownie zapytaj „i co z tego?”
2. Zaznacz twierdzenia, w których brakuje odpowiedzi
3. Dodaj pomost korzyści lub głębsze znaczenie
4. Upewnij się, że korzyści łączą się z rzeczywistymi pragnieniami czytelnika

**Po tym przeglądzie:** Wróć do opcji Głos i ton, a następnie Przejrzystość.

---

### Przegląd 4: Udowodnij to

**Cel:** Czy każde twierdzenie jest poparte dowodami?

**Co sprawdzić:**
- Niepoparte dowodami twierdzenia
- Brak dowodu społecznego
- Twierdzenia bez poparcia
- „Najlepszy” lub „wiodący” bez dowodów

**Rodzaje dowodów, których należy szukać:**
- Referencje z nazwiskami i szczegółami
- Referencje ze studiów przypadku
- Statystyki i dane
- Potwierdzenie przez niezależne źródło
- Gwarancje i odwrócenie ryzyka
- Loga klientów
- Oceny z recenzji

**Typowe luki w dowodach:**
- „Zaufały nam tysiące” (które tysiące?)
- „Wiodący w branży” (według kogo?)
- „Klienci nas kochają” (pokaż, jak to mówią)
- Twierdzenia dotyczące wyników bez szczegółów

**Proces:**
1. Zidentyfikuj każde twierdzenie wymagające dowodu
2. Sprawdź, czy w pobliżu znajduje się dowód
3. Oznacz twierdzenia bez poparcia
4. Polecaj dodanie dowodów lub złagodzenie twierdzeń

**Po tym przeglądzie:** Wróć do „I co z tego?”, Głosu i tonu, a następnie Przejrzystości.

---

### Przegląd 5: Konkretność

**Cel:** Czy tekst jest wystarczająco konkretny, aby był przekonujący?

**Co sprawdzić:**
- Niejasny język („poprawić”, „ulepszyć”, „optymalizować”)
- Ogólne stwierdzenia, które mogą dotyczyć każdego
- Okrągłe liczby, które sprawiają wrażenie wymyślonych
- Brakuje szczegółów, które sprawiłyby, że byłoby to realne

**Jak zwiększać konkretność:**

| Niejasne | Konkretne |
|-------|--------------|
| Oszczędzaj czas | Zaoszczędź 4 godziny tygodniowo |
| Wielu klientów | 2847 zespołów |
| Szybkie rezultaty | Wyniki za 14 dni |
| Popraw swój przepływ pracy | Skróć czas raportowania o połowę |
| Świetne wsparcie | Odpowiedź w ciągu 2 godzin |

**Częste problemy związane z konkretnością:**
- Przymiotniki zastępujące konkretne informacje
- Korzyści bez określenia ilościowego
- Wyniki bez ram czasowych
- Twierdzenia bez konkretnych przykładów

**Proces:**
1. Zaznacz niejasne słowa i wyrażenia
2. Zapytaj: „Czy można to określić bardziej szczegółowo?”
3. Dodaj liczby, ramy czasowe lub przykłady
4. Usuń treści, których nie można sprecyzować (prawdopodobnie to wypełniacz)

**Po tym przeglądzie:** Wróć do Udowodnij to, I co z tego, Głos i ton, a następnie Przejrzystość.

---

### Przegląd 6: Wzmocnienie emocji

**Cel:** Czy tekst sprawia, że czytelnik coś czuje?

**Co sprawdzić:**
- Płaski, informacyjny język
- Brak wyzwalaczy emocjonalnych
- Wspomniano o problemach odbiorcy, ale ich nie odczuwano
- Aspiracje wyrażone, ale nie wywołane

**Wymiary emocjonalne do rozważenia:**
- Ból obecnego stanu
- Frustracja związana z alternatywami
- Strach przed przegapieniem
- Chęć transformacji
- Duma z dokonywania mądrych wyborów
- Ulga w rozwiązaniu problemu

**Techniki wzmacniania emocji:**
- Obrazowo przedstaw stan „przed”.
- Używaj języka zmysłowego
- Opowiadaj mikrohistorie
- Odwołaj się do wspólnych doświadczeń
- Zadawaj pytania skłaniające do refleksji

**Proces:**
1. Czytaj pod kątem emocji – czy cię porusza?
2. Zidentyfikuj płaskie sekcje, które powinny rezonować
3. Dodaj warstwę emocjonalną, zachowując autentyczność
4. Upewnij się, że emocje służą przekazowi (a nie manipulacji)

**Po tym przeglądzie:** Wróć do Konkretności, Udowodnij to, I co z tego, Głos i ton, a następnie Przejrzystość.

---

### Przegląd 7: Zero ryzyka
**Cel:** Czy usunęliśmy wszystkie bariery w działaniu?

**Co sprawdzić:**
- Tarcie w pobliżu CTA
- Zastrzeżenia bez odpowiedzi
- Brakujące sygnały zaufania
- Niejasne dalsze kroki
- Ukryte koszty lub niespodzianki

**Reduktory ryzyka, których należy szukać:**
- Gwarancje zwrotu pieniędzy
- Bezpłatne wersje próbne
- „Nie jest wymagana karta kredytowa”
- „Anuluj w dowolnym momencie”
- Dowód społeczny w pobliżu CTA
- Jasne oczekiwania co do tego, co stanie się dalej
- Gwarancje prywatności

**Typowe problemy związane z ryzykiem:**
- CTA prosi o zaangażowanie bez zdobywania zaufania
- Zasygnalizowane obiekcje nie zostały wyjaśnione
- Drobny druk, który budzi wątpliwości
- Niejasne „Skontaktuj się z nami” zamiast jasnego następnego kroku

**Proces:**
1. Skoncentruj się na sekcjach w pobliżu CTA
2. Wymień wszystkie powody, dla których ktoś może się wahać
3. Sprawdź, czy tekst uwzględnia każdy problem
4. W razie potrzeby dodaj odwrócenie ryzyka lub sygnały zaufania

**Po tym cyklu:** Wróć jeszcze raz do wszystkich poprzednich przebiegów: Wzmocnienie emocji, Konkretność, Udowodnij to, I co z tego, Głos i ton, Przejrzystość.

---

## Punktacja panelu ekspertów

Użyj tego po ukończeniu Siedmiu Przeglądów, aby uzyskać dodatkową kontrolę jakości. W przypadku tekstów o dużym znaczeniu biznesowym (strony docelowe, e-maile premierowe, strony sprzedażowe) wieloosobowa recenzja ekspercka wychwytuje problemy, które pomija pojedyncza perspektywa.

### Jak to działa

1. **Zbierz 3-5 ekspertów** odpowiednich do rodzaju tekstu
2. **Każda osoba ocenia tekst w skali 1–10** w swojej dziedzinie specjalizacji
3. **Zbierz konkretną krytykę** — nie tylko wyniki, ale także to, co należy poprawić
4. **Popraw w oparciu o opinie** — najpierw zajmij się obszarami o najniższej punktacji
5. **Ponowna ocena po poprawieniu** — powtarzaj, aż ocena każdej osoby wyniesie co najmniej 7, przy średniej 8+ w całym panelu

### Polecane Panele Eksperckie

**Tekst strony docelowej:**
- Copywriter konwersji (przejrzystość, siła CTA, hierarchia korzyści)
- UX writer (łatwość szybkiego przeglądania, obciążenie poznawcze, przepływ użytkowników)
- Persona docelowego klienta (czy to do mnie przemawia? Czy mu ufam?)
- Strateg marki (spójność głosu, dokładność pozycjonowania)

**Sekwencja e-maili:**
- Specjalista ds. marketingu e-mailowego (temat, optymalizacja open/click)
- Copywriter (haki, opowiadanie historii, perswazja)
- Analityk filtra spamu (sygnały ostrzegawcze dostarczalności, słowa wyzwalające)
- Persona docelowego klienta (trafność, wartość, ryzyko rezygnacji z subskrypcji)

**Strona sprzedażowa / długa forma:**
- Copywriter direct response (struktura oferty, odpowiedzi na obiekcje, pilność)
- Persona sceptycznego kupującego (luki w dowodach, problemy z zaufaniem, sygnały ostrzegawcze)
- Redaktor (przepływ, czytelność, zwięzłość)
- Specjalista SEO (pokrycie słów kluczowych, dopasowanie intencji wyszukiwania)

### Rubryka punktacji

| Wynik | Znaczenie |
|-------|-------------|
| 9-10 | Gotowe do publikacji. Żadnych znaczących ulepszeń. |
| 7-8 | Mocny. Tylko drobne poprawki. |
| 5-6 | Funkcjonalny, ale ma wyraźne luki. Potrzebuje kolejnego przeglądu. |
| 3-4 | Istotne kwestie. Potrzebna poważna rewizja. |
| 1-2 | Zasadniczo zepsuty. Przemyśl podejście. |

### Kiedy używać
- **Zawsze** w przypadku tekstów premierowych, stron z cenami i stron docelowych o dużym ruchu
- **Zalecane** w przypadku sekwencji e-maili, stron sprzedażowych i tekstów reklam
- **Opcjonalnie** w przypadku postów na blogu, treści społecznościowych i dokumentów wewnętrznych
- **Pomiń** przy szybkie aktualizacje, drobne zmiany i treści o niskiej stawce

---

## Szybkie sprawdzanie edycji

Użyj ich, aby przyspieszyć przeglądanie, gdy nie jest potrzebny pełny proces obejmujący siedem przeglądów.

### Sprawdzanie na poziomie słów

**Wytnij te słowa:**
- Bardzo, naprawdę, niezwykle, niewiarygodnie (słabe wzmacniacze)
- Po prostu, właściwie, w zasadzie (wypełniacz)
- Angielskie „in order to” → „to” (po polsku: usuwaj rozwlekłe konstrukcje celu)
- Angielskie „that” (często zbędne; w polskim oceń funkcję „że” w zdaniu)
- Angielskie „things”, „stuff” — ogólnikowe określenia typu „rzeczy”

**Zastąp te:**

| Słaby | Silny |
|------|------------|
| Utilize — „wykorzystywać” | Use — „używać” |
| Implement — „wdrożyć” | Set up — „skonfigurować” |
| Leverage — „wykorzystywać potencjał” | Use — „używać” |
| Facilitate — „ułatwiać” | Help — „pomagać” |

**Zastąp faktem** (sama zamiana synonimów tworzy kolejne sztuczne sformułowania):

| Niejasne | Zamiast tego napisz fakt |
|-------|--------------------------------------|
| Innowacyjny / nowatorski | Co robi, czego nie robią alternatywy |
| Solidny | Czas działania, skala lub przypadek awarii, który obsługuje |
| „Seamless” — bezproblemowy | Rzeczywista liczba lub czas kroków konfiguracji |

**Obserwuj:**
- Przysłówki (zwykle niepotrzebne)
- Strona bierna (zastąp czynną)
- Nominalizacja (czasownik → rzeczownik: „podejmij decyzję” → „zdecyduj”)

### Sprawdzanie poziomu zdania

- Jeden pomysł na zdanie
- Zmieniaj długość zdań (mieszaj krótkie i długie)
- Ważne informacje na początku zdania
- Maksymalnie 3 spójniki w zdaniu
- Nie więcej niż 25 słów (zwykle)
### Sprawdzanie na poziomie akapitu

- Jeden temat na akapit
- Krótkie akapity (2-4 zdania dla Internetu)
- Mocne zdania początkowe
- Logiczny przepływ pomiędzy akapitami
- Odstępy ułatwiające szybkie przeglądanie

### Kontrola śladów AI

Uruchom to przy każdej edycji, po przeglądach. Czytelnik, który rozpozna sztuczne brzmienie, zwykle zaczyna wątpić w wiarygodność tekstu. Kształt zdania zdradza więcej niż jakiekolwiek słowo.

**Napraw każde wystąpienie:**

| Wzór | Przykład | Napraw |
|--------|---------|-----|
| Schemat kontrastowego ujawnienia | „To nie X, to Y”. „Nie dlatego, że X. Ponieważ Y.” | Podaj Y bezpośrednio, podając powód |
| Lista negacji | „Bez rozmów konfiguracyjnych, bez szablonów, bez czekania na IT”. | Powiedz, co się dzieje; zachowaj jedną informację o braku wymogu, jeśli ma to znaczenie („karta nie jest wymagana”) |
| Doczepione dopowiedzenie | „...dane, które już posiadasz, bez eksportu i bez arkuszy kalkulacyjnych.” / „..., upewniając się, że nic się nie poślizgnie.” | Zakończ zdanie na głównym twierdzeniu; korzyść opisz osobnym zdaniem |
| Pytanie z natychmiastową odpowiedzią | „Rezultat? 3 razy szybszy.” | Usuń pytanie, zachowaj odpowiedź |
| Schemat ujawnienia po dwukropku | „Najlepsza część: uczy się”. | Napisz normalne zdanie |
| Sztampowe frazy | „W dzisiejszym dynamicznym świecie”, „Nieważne, czy jesteś X, czy Y”, „Oto sprawa”, „Pożegnaj”, „X w nowej odsłonie”, „Odblokuj moc” | Wytnij, a następnie zacznij od problemu czytelnika lub faktem |
| Pauzy em dash w krótkich tekstach | Nagłówki, podtytuły, wezwania do działania, reklamy, posty w mediach społecznościowych, tematy (maksymalnie 1–2 na stronę w przypadku długich tekstów) | Kropka, przecinek lub dwukropek |

**Limit:** najwyżej jeden urwany fragment zdania i jedna lista trzech elementów w każdej sekcji (hero, sekcja strony lub jeden krótki post). Traktuj „seamless”, „robust”, „powerful”, „streamline” i „empower” jako ogólniki: tam, gdzie to możliwe, zastąp je konkretnym faktem, a jeśli dwa pojawią się w jednym akapicie, przepisz akapit.

**Jak naprawić:** wróć do faktów (mechanizm, liczba, klient lub krok) i napisz na nowo. Sama zamiana synonimów tworzy kolejne ślady sztucznego tekstu. Jeśli fakt nie jest dostępny, zaznacz `[NEED: ...]` zamiast go wymyślać. Zachowaj rejestr językowy marki. Formalne zdanie zawierające konkretną tezę jest w porządku.

**Zostaw je w spokoju:** pytania FAQ, jedno „Karta nie jest wymagana” przy CTA, lista trzech, jeśli tak naprawdę są trzy funkcje, i dopowiedzenie po przecinku, która dodaje nowy fakt („Importy odbywają się co noc, zachowując istniejące identyfikatory”).

Aby zapoznać się z pełną czarną listą z przykładami, skorzystaj z materiału o śladach AI w umiejętności **website-copy**.

---

## Lista kontrolna redakcji tekstów

Aby uzyskać ostateczny przebieg kontroli jakości przed wprowadzeniem zmian, przejrzyj pełną listę kontrolną w [references/checklist.md](references/checklist.md) — obejmującą wszystkie siedem przeglądów oraz elementy kontroli przed rozpoczęciem i końcową.

---

## Typowe problemy z tekstem i sposoby ich naprawy

### Problem: Ściana funkcji
**Objaw:** Lista działania produktu bez powodu, dla którego jest to istotne
**Poprawka:** Dodaj „co oznacza…” po każdej funkcji, aby uzyskać korzyści

### Problem: Mowa korporacyjna
**Objaw:** „Wykorzystanie synergii w celu optymalizacji wyników”
**Poprawka:** Zapytaj „Jak powiedziałby to człowiek?” i używaj tych słów

### Problem: Słaby początek
**Objaw:** Zaczyna się od historii firmy lub niejasnych stwierdzeń
**Poprawka:** Opowiedz o problemie czytelnika lub pożądanym wyniku

### Problem: ukryte CTA
**Objaw:** pytanie pojawia się po zbyt dużym nawarstwieniu lub jest niejasne
**Poprawka:** Spraw, aby wezwanie do działania było oczywiste, wczesne i powtarzane

### Problem: brak dowodu
**Objaw:** „Klienci nas kochają” bez dowodów
**Poprawka:** Dodaj konkretne referencje, liczby lub odniesienia do spraw

### Problem: Ogólnikowe twierdzenia
**Objaw:** „Pomagamy rozwijać się firmom”
**Poprawka:** Określ kto, jak i za ile

### Problem: mieszani odbiorcy
**Objaw:** Tekst próbuje przemawiać ze wszystkimi, z nikim nie rezonuje
**Poprawka:** wybierz jednego odbiorcę i napisz bezpośrednio do niego

### Problem: Tekst brzmi jak wygenerowany przez AI
**Objaw:** „Nie X. Y.” ujawnia listy „bez X, bez Y, bez Z”, długie zdania kończące się dodatkowymi klauzulami, sztampowe początki
**Poprawka:** Uruchom powyższą kontrolę AI-Tell i przepisz te zdania na podstawie faktów

### Problem: Przeciążenie funkcji
**Objaw:** Wypisywanie wszystkich możliwości przytłacza czytelnika
**Poprawka:** Skoncentruj się na 3–5 kluczowych korzyściach, które są najważniejsze dla odbiorców

---
## Wspólna praca z metodą przeglądów

Podczas wspólnego edytowania:

1. **Przeprowadź przegląd i przedstaw wnioski** – Pokaż, co odkryłeś i dlaczego jest to problem
2. **Zalecaj konkretne zmiany** – Nie tylko identyfikuj problemy; zaproponuj rozwiązania
3. **Poproś o zaktualizowany tekst** - Pozwól autorowi podjąć ostateczne decyzje
4. **Sprawdź poprzednie przebiegi** - Po każdej rundzie edycji sprawdź ponownie wcześniejsze przebiegi
5. **Powtarzaj, aż tekst będzie gotowy** - Kontynuuj, aż pełny przegląd nie wykryje żadnych nowych problemów

Ten powtarzalny proces gwarantuje, że każda edycja nie stworzy nowych problemów, przy jednoczesnym poszanowaniu prawa autora do decydowania o tekście.

---

## Materiały pomocnicze

- [Plain English Alternatives](references/plain-english-alternatives.md): Zastąp złożone słowa prostszymi alternatywami
- [Odświeżanie treści](references/content-refresh.md): analiza luk w SERP, pełna lista kontrolna, macierz odświeżania i przepisywania oraz zalecana częstotliwość aktualizacji
- [Lista kontrolna redakcji tekstów](references/checklist.md): Pełna lista kontrolna kontroli jakości we wszystkich siedmiu przeglądach plus kontrola AI

---

## Redakcja przy odświeżaniu treści

Redakcja tekstów nie dotyczy tylko nowej zawartości. Istniejące strony z czasem tracą aktualność – nieaktualne statystyki, nieaktualne przykłady i zmieniony głos marki. Użyj struktury odświeżania treści, gdy ruch spada, dane są nieaktualne lub produkt się zmienił.
**Aby zapoznać się z analizą luk w SERP, pełną listą kontrolną odświeżania, macierzą decyzji o odświeżeniu i przepisaniu oraz przewodnikiem po rytmie**: Zobacz [references/content-refresh.md](references/content-refresh.md)

---

## Pytania dotyczące konkretnego zadania

1. Jaki jest cel tego tekstu? (Świadomość, konwersja, utrzymanie)
2. Jakie działanie powinni podjąć czytelnicy?
3. Czy istnieją szczególne obawy lub znane problemy?
4. Jakimi dowodami dysponujesz?
5. Czy jest to nowy tekst czy odświeżenie istniejącej treści?

---

## Powiązane umiejętności

- **website-copy**: do pisania nowego tekstu od zera (użyj tej umiejętności, aby edytować po ukończeniu pierwszej wersji roboczej)
- **cro**: Dla szerszej optymalizacji strony, wykraczającej poza sam tekst
- **marketing-psychology**: Aby zrozumieć, dlaczego niektóre zmiany poprawiają konwersję
- **ab-testing**: Do testowania wariantów tekstu

---

## Kiedy używać każdej umiejętności

| Zadanie | Umiejętność użycia |
|------|------------------|
| Pisanie nowego tekstu strony od podstaw | copywriting |
| Przeglądanie i ulepszanie istniejącego tekstu | redakcja (ta umiejętność) |
| Redakcja tekstów, którą właśnie napisałeś | redakcja (ta umiejętność) |
| Strukturalne lub strategiczne zmiany strony | cro |