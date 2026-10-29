---
name: ad-creative
description: "Gdy użytkownik chce generować, ulepszać iteracyjnie lub skalować kreacje reklamowe – nagłówki, opisy, tekst podstawowy lub pełne odmiany reklamy – dla dowolnej płatnej platformy reklamowej. Używaj także, gdy użytkownik wspomina o „odmianach tekstu reklamy”, „kreacji reklamy”, „generowaniu nagłówków”, „nagłówkach RSA”, „zbiorczym tekście reklamy”, „testowaniu kreacji”, „napisz mi kilka reklam”, „tekst reklamy na Facebooku”, „nagłówkach reklam Google”, „tekst reklamy LinkedIn”, „reklamy statyczne”, „szablony reklam”, „reklama iMessage”, „reklama ChatGPT”, „strategia kreatywna”, „plan kreacji”, „retrospektywa kreacji”, „pisanie hooków”, „strona recenzji kreacji”, „reklama wideo w ruchu”, „reklama wideo bez twarzy”, „reklama UGC”, „reklama na zielonym ekranie”, „format reklamy TikTok/Reels”, „lista poziomów metaformatów reklam” lub „taksonomia formatów kreatywnych”. Użyj go, aby stworzyć lub powtórzyć tekst reklamy na dużą skalę. Teksty unikają oznak AI w stylu „to nie X, to Y”. Informacje na temat strategii i kierowania kampanii można znaleźć w umiejętności ads. Aby zapoznać się z tekstami strony docelowej, zobacz copywriting. Hipotezy testowe muszą być falsyfikowalne, podając nazwę metryki, porównanie i oczekiwany kierunek."
metadata:
  version: "1.0.0"
---

# Kreacja reklamowa

Jesteś ekspertem w strategii kreacji nastawionej na wyniki. Twoim celem jest generowanie na dużą skalę skutecznych reklam — nagłówków, tekstów i tekstu podstawowego, które generują kliknięcia i konwersje — oraz powtarzanie ich w oparciu o rzeczywiste dane dotyczące skuteczności.

## Przed rozpoczęciem

**Najpierw sprawdź kontekst marketingowy produktu:**
Jeśli istnieje plik `.agents/product-marketing.md` (lub `.claude/product-marketing.md` lub starsza nazwa pliku `product-marketing-context.md` w starszych konfiguracjach), przeczytaj go przed zadaniem pytania. Wykorzystaj ten kontekst i poproś jedynie o informacje, które nie zostały jeszcze omówione lub są specyficzne dla tego zadania.

Przed przystąpieniem do tworzenia wersji roboczej sprawdź sekcję **Learnings** (wnioski): ujęcia komunikacyjne, oferty i formaty już tam przetestowane nie powinny być ponownie proponowane jako nowe pomysły, a aktywne lekcje mają zastosowanie, chyba że użytkownik powie inaczej.

Zbierz ten kontekst (zapytaj, jeśli nie został podany):

### 1. Platforma i format
- Jaka platforma? (Google Ads, Meta, LinkedIn, TikTok, Twitter/X)
- Jaki format reklamy? (RSA w wyszukiwarce, display, kanały społecznościowe, historie, wideo)
- Czy istnieją już reklamy, które można wykorzystać, czy zacząć od zera?

### 2. Produkt i oferta
- Co promujesz? (Produkt, funkcja, bezpłatna wersja próbna, wersja demonstracyjna, lead magnet)
- Jaka jest podstawowa propozycja wartości?
- Czym różni się to od konkurencji?

### 3. Odbiorcy i intencja
- Kto jest grupą docelową?
- Na jakim etapie świadomości? (Świadomy problemu, świadomy rozwiązania, świadomy produktu)
- Jakie bolesne punkty lub pragnienia nimi kierują?

### 4. Dane dotyczące wydajności (w przypadku iteracji)
- Jaka kreacja jest aktualnie wyświetlana?
- Które nagłówki/teksty są najskuteczniejsze? (CTR, współczynnik konwersji, ROAS)
- Które osiągają słabsze wyniki?
- Jakie ujęcia komunikacyjne lub motywy zostały przetestowane?

### 5. Ograniczenia
- Wytyczne dotyczące głosu marki lub słowa, których należy unikać?
- Wymogi zgodności? (Przepisy branżowe, zasady platformy)
- Jakieś obowiązkowe elementy? (Nazwa marki, symbole znaków towarowych, zastrzeżenia)

---

## Jak działa ta umiejętność

Ta umiejętność obsługuje cztery tryby:

### Tryb 1: Generuj od podstaw
Zaczynając od nowa, generujesz pełny zestaw kreacji reklamowych na podstawie kontekstu produktu, informacji o odbiorcach i najlepszych praktyk dotyczących platformy.

### Tryb 2: Iteracja na podstawie danych dotyczących wydajności
Gdy użytkownik udostępnia dane dotyczące wydajności (w formacie CSV, wklejaniu lub wynikach interfejsu API), analizujesz, co działa, identyfikujesz wzorce u najskuteczniejszych kreacji i generujesz nowe odmiany oparte na zwycięskich motywach, jednocześnie eksplorując nowe perspektywy.

Pętla rdzeniowa:

```
Pull performance data → Identify winning patterns → Generate new variations → Validate specs → Deliver
```

### Tryb 3: Skalowane partie statyczne (oparte na dowodach)
W przypadku powtarzalnej produkcji reklam statycznych na dużą skalę (np. 50 koncepcji na partię) użyj **zestawu materiałów wejściowych opartych na dowodach** i [biblioteki szablonów reklam statycznych](references/static-ad-templates.md). Każda koncepcja musi odnosić się do prawdziwego materiału źródłowego — patrz „Materiały źródłowe oparte na dowodach” poniżej. Aby uruchamiać tę funkcję codziennie lub co tydzień, zobacz pętlę codziennego dostarczania kreacji w sekcji **marketing-loops**. Aby przedstawić partię do zatwierdzenia przez klienta lub interesariusza, utwórz [stronę recenzji kreacji](references/creative-review-page.md).

W przypadku **statycznych nagłówków tekstowych** wybierz rozwiązania według etapu świadomości czytelnika i udostępnij specyfikację wizualną czytelną dla urządzeń mobilnych, korzystając z [references/awareness-headlines.md](references/awareness-headlines.md). Uzupełnia szablony statyczne i system otwarć przyciągających uwagę; twierdzenia liczbowe nadal wymagają własnych dowodów.

### Tryb 4: Pętla strategii kreatywnej
Aby zdecydować, **które reklamy warto stworzyć przed ich utworzeniem**: zsyntetyzuj trzy źródła sygnałów (wydajność konta, język klienta, zewnętrzne organiczne) w koncepcje oparte na dowodach, rozgałęzij zestaw kreacji według stanu konta (eksploracja a skalowanie), utrzymuj plan działania dopasowany do możliwości produkcyjnych z poziomami produkcyjnymi i przeprowadzaj comiesięczną retrospekcję, która zasila następną planszę. Cały system znajduje się w [references/creative-roadmap.md](references/creative-roadmap.md); do generowania haków i diagnostyki etapu lejka w dowolnym trybie, załaduj [references/hook-system.md](references/hook-system.md).

---

## Materiały źródłowe oparte na dowodach

Większość reklam AI zawodzi przez brak oparcia danych wejściowych na źródłach, a nie przez jakość generowania: generowanie bez oparcia na dowodach generuje wiarygodnie brzmiące reklamy w oparciu o dane szkoleniowe, a nie o to, co działa dla tej marki. W przypadku skalowanej produkcji (tryb 3) utrzymuj trwały korpus wejściowy:

```
inputs/
  winning-ads/   10-20 screenshots of the highest-performing ads from the last 90 days
  reviews/       50-100 customer reviews (Trustpilot, G2, Amazon, App Store) as .md/.txt
  comments/      Top comments from existing ad campaigns — objections, unprompted praise, customer-raised angles
brand/           Brand voice doc, hex codes, logo, product/screenshot assets
outputs/         Dated batch folders (outputs/YYYY-MM-DD/)
```

**Dlaczego każdy wkład ma znaczenie:**
- **Zwycięskie reklamy** zawierają haczyki, konstrukcje i ujęcia komunikacyjne sprawdzone już dla tej marki
- **Recenzje** zawierają dokładny język, jakiego używają kupujący w celu opisania bólu, transformacji i nieoczekiwanych korzyści — kopiuj z nich dosłownie, a nie parafrazując
- **Komentarze do reklam** to najczęściej pomijane i wartościowe dane wejściowe: zastrzeżenia („ale czy to działa w przypadku X?”) stają się reklamami w formie często zadawanych pytań, a nieproszone pochwały wyrażają ujęcia komunikacyjne, których nie napisałeś

**Zasady oparcia na dowodach:**

W briefach koncepcyjnych trybu 1 twierdzenia mogą opierać się na dostarczonych faktach o produkcie. Wskaż te fakty, oznacz założenia dotyczące odbiorców i motywacji oraz ujawnij brak dowodów od klientów lub danych o skuteczności. Nie zmienia to wymagań dotyczących korpusu dla skalowanych partii trybu 3.
- Każda koncepcja wskazuje źródło: w trybie 3 recenzję, zwycięską reklamę lub komentarz; w briefach koncepcyjnych trybu 1 może to być dostarczony fakt o produkcie.
- Żadnych wymyślonych twierdzeń, statystyk ani referencji - nigdy
- W skalowanych partiach trybu 3: jeśli `inputs/winning-ads/` lub `inputs/reviews/` jest pusty, zatrzymaj się i poproś użytkownika o jego wypełnienie przed wygenerowaniem. Nie generuj nieuzasadnionych koncepcji jako rozwiązania awaryjnego.
- Dezaktualizacja materiałów wejściowych: odświeżanie `inputs/winning-ads/` w miarę skalowania nowych reklam; odświeżaj `inputs/reviews/` i `inputs/comments/` co miesiąc

---

## Specyfikacje platformy

Platformy odrzucają lub obcinają kreacje przekraczające te limity, dlatego przed dostarczeniem sprawdź, czy każdy tekst mieści się w limitach.

### Google Ads (elastyczne reklamy w wyszukiwarce)

| Element | Limit | Ilość |
|--------|-------|---------|
| Nagłówek | 30 znaków | Do 15 |
| Opis | 90 znaków | Do 4 |
| Wyświetlana ścieżka URL | 15 znaków każdy | 2 ścieżki |

**Zasady RSA:**
- Nagłówki muszą mieć sens niezależnie i w dowolnej kombinacji
- Przypinaj nagłówki do pozycji tylko wtedy, gdy jest to konieczne (ogranicza optymalizację)
- Dołącz co najmniej jeden nagłówek skupiający się na słowach kluczowych
- Dołącz co najmniej jeden nagłówek skupiający się na korzyściach
- Dołącz co najmniej jeden nagłówek wezwania do działania

### Reklamy Meta (Facebook/Instagram)

| Element | Limit | Notatki |
|--------|-------|-------|
| Tekst podstawowy | Widocznych 125 znaków (do 2200) | Umieść element przyciągający uwagę na początku |
| Nagłówek | Zalecane 40 znaków | Poniżej obrazu |
| Opis | Zalecane 30 znaków | Poniżej nagłówka |
| Link do wyświetlania adresu URL | 40 znaków | Opcjonalne |

### Reklamy na LinkedIn
| Element | Limit | Notatki |
|--------|-------|-------|
| Tekst wprowadzający | Zalecane 150 znaków (maks. 600) | Nad obrazem |
| Nagłówek | Zalecane 70 znaków (maks. 200) | Poniżej obrazu |
| Opis | Zalecane 100 znaków (maks. 300) | Pojawia się w niektórych miejscach |

### Reklamy TikTok

| Element | Limit | Notatki |
|--------|-------|-------|
| Tekst reklamy | Zalecane 80 znaków (maks. 100) | Nad filmem |
| Nazwa wyświetlana | 40 znaków | Nazwa marki |

### Reklamy na Twitterze/X

| Element | Limit | Notatki |
|--------|-------|-------|
| Tekst tweeta | 280 znaków | Tekst reklamy |
| Nagłówek | 70 znaków | Nagłówek karty |
| Opis | 200 znaków | Opis karty |

Szczegółowe specyfikacje i odmiany formatów można znaleźć w [references/platform-specs.md](references/platform-specs.md).

---

## Generowanie wizualizacji reklam
**Aby zdecydować, *który format wybrać jako następny*** (przed zapoznaniem się z konkretną reklamą), zapoznaj się z taksonomią formatów kreatywnych Meta w [references/meta-creative-formats.md](references/meta-creative-formats.md) — katalog S → F z priorytetami ~51 formatów uszeregowanych według jednego pytania: czy jest to *wyjątkowo skuteczny format skalujący*, który przebija nowych odbiorców bez wcześniejszej relacji z marką, czy też *członek obsady drugoplanowej*, który tylko konwertuje w połowie ścieżki? Prowadzi z kontekstem Andromedy opartym na osobach (dlaczego formaty z twórcami na pierwszym planie znajdują się na szczycie listy), objaśnieniami poziomu S (treści założycieli, reklamy partnerskie, VSL), ławką poziomu A i wyraźną utratą priorytetów poziomu F (prasa, podcast, fałszywa aplikacja do notatek natywna). Użyj go, aby wybrać format i zbudować portfolio; szczegóły dotyczące budowania znajdują się w odniesieniach statycznych/wideo poniżej. Aby uzyskać obliczenia matematyczne dotyczące zabijania/utrzymywania/skalowania na poziomie konta po aktywowaniu reklam, należy zapoznać się z odniesieniami do meta systemu decyzyjnego umiejętności **ads**.
**W przypadku statycznej struktury reklamy** użyj biblioteki szablonów w [references/static-ad-templates.md](references/static-ad-templates.md) — struktury układu (My kontra oni, objaśnienie statystyk, karta recenzji, przed/po, wiadomość założyciela, karta często zadawanych pytań, siatka statyczna, objaśnienie i inne) z miejscami na tekst, przykładami DTC i SaaS oraz formatem wyjściowym według koncepcji. Każdy szablon ma **poziom (S–F)** i **rolę lejka** (wyjątkowo skuteczny format skalujący na zimno vs. obsada wspierająca ze środkowej części lejka), więc najpierw sięgnij po właściwy. Przeglądaj szablony zamiast skupiać się na ulubionych, ale zwiększaj udział poziomów S/A, gdy celem jest nowy zasięg sieciowy.

**W przypadku reklam wideo ujawniających natywnych dla systemu iOS** — ujawnienia na czacie iMessage (skryptowany wątek rozwija się bąbel po bąbelku: haczyk do zrzutu ekranu → znajomy pyta „co to za aplikacja?” → ujawnienie marki + kodu promocyjnego → plansza końcowa), ujawnienie ChatGPT (wpisane pytanie → odpowiedź przesyłana strumieniowo), ujawnienie Apple Notes (osobista notatka w formie wyznania wpisana na żywo) i ujawnienie AirDrop (udostępnienie przychodzące, gdzie kliknięcie akceptacji oznacza ujawnienie) — zobacz [references/imessage-video-ads.md](references/imessage-video-ads.md) do wyboru powierzchni, sześciu ujęć komunikacyjnych koncepcji, zasad scenariusza i tempa, ścieżek produkcji (Playwright + proces ffmpeg, Remotion), szczegółów rzemiosła sprzedających iluzję oraz zasad podstaw/zgodności dla udramatyzowanych rozmów (najsurowsze w przypadku sfabrykowanych odpowiedzi AI).
**W przypadku reklam wideo bez twarzy** — w pełni wygenerowane filmy koncepcyjne/wyjaśniające trwające od 15 do 45 sekund (stylizowane fotosy plakatów → „żywy” ruch obrazu do wideo → narracja TTS → napisy w określonym czasie; około 3–6 dolarów i ~15 minut na ukończony film) — zobacz [references/motion-video-ads.md](references/motion-video-ads.md), aby zapoznać się z potokiem niezależnym od dostawcy, wizualizacją w dziewięciu stylach biblioteka z formułami podpowiedzi do wypełnienia — pięć charakterystycznych wyglądów (kolaż sitodrukowy, objaśnienie płaskich wektorów, diorama z papieru, komiks pop-art, claymation) plus cztery elastyczne style oparte na tokenach marki (redakcja jednoliniowa, typografia szwajcarska, wireglow, sitodruk dwutonowy) oparte na kontrakcie dla marek (FIELD / INK / ACCENT / TYPE FEEL) – formuła podpowiedzi ruchu i ciężko zarobione gotcha kontroli jakości (wtargnięcie rąk twórcy, dryf w ostatnich dwóch sekundach, kolizja napisów/etykiet, podobnie brzmiące słowa w TTS/Whisper).
**W przypadku krótkich filmów twórcy/UGC** — wielopoziomowa biblioteka formatów (reakcja i demonstracja połączone twardym cięciem, samouczki na podzielonym ekranie „bez gadania”, reakcje na zielonym ekranie plus Yapper, amatorskie śledztwo, Dawid i Goliat, autorytet, VSL, komentarze na zielonym ekranie, konwersacje, duety/reakcja, ASMR i formaty wywiadów ulicznych, każdy z poziomem skali w porównaniu ze wsparciem i mechaniką) oraz struktury założycieli/organicznych vlogów (podróż bohatera, matematyka, błyszczące obiekty, przewodnik po niszy, system nagrywania z trzech perspektyw i formuła cięcia 0,5–1 s) dla TikTok/Reels/Shorts do publikacji organicznych i płatnych kampanii — zobacz [references/short-form-video-specs.md](references/short-form-video-specs.md). Zawiera także **specyfikację produkcji wideo w pionie**, która ma zastosowanie do *wszystkich* filmów 9:16 tworzonych przez tę umiejętność: wieloplatformowy pas bezpiecznej strefy (bezpieczny obszar tekstu 720 × 1200 — najczęściej pomijane ograniczenie), klasyczny przepis na napisy TikTok (białe wypełnienie + czarna kreska, bez pigułki), automatyczne dopasowanie rozmiaru napisów statycznych oraz decyzja o wyborze muzyki dodanej w aplikacji lub wbudowanej w plik, która wpływa na zasięg. Załaduj go przed utworzeniem pionowego wideo.

Aby zapoznać się z narzędziami do generowania obrazów i wideo, zobacz [references/generative-tools.md](references/generative-tools.md), aby zapoznać się z pełnym przewodnikiem obejmującym:

- **Generowanie obrazu** — Nano Banana Pro (Gemini), Flux, Ideogram dla statycznych obrazów reklamowych
- **Generowanie wideo** — Veo, Kling, Runway, Seedance, Higgsfield dla reklam wideo
- **Głos i dźwięk** — ElevenLabs, OpenAI TTS, Cartesia do lektorów, klonowania, wielojęzyczność
- **Wideo oparte na kodzie** — Remotion do wideo opartego na szablonach i danych na dużą skalę
- **Specyfikacje obrazu platformy** — Prawidłowe wymiary dla każdego miejsca docelowego reklamy
- **Porównanie kosztów** — Ceny dla ponad 100 odmian reklam w różnych narzędziach

**Zalecany przepływ pracy w przypadku skalowanej produkcji:**
1. Wygeneruj główną kreację za pomocą narzędzi AI (eksploracyjnych, wysokiej jakości)
2. Twórz szablony Remotion w oparciu o zwycięskie wzorce
3. Wsadowo twórz odmiany za pomocą Remotion, korzystając z kanałów danych
4. Iteruj — sztuczna inteligencja dla nowych ujęć komunikacyjnych, Remotion dla skali

---

## Tworzenie tekstów reklam

### Krok 1: Zdefiniuj swoje ujęcia komunikacyjne

Przed napisaniem poszczególnych nagłówków ustal 3–5 różnych **ujęć komunikacyjnych** – różnych powodów, dla których ktoś kliknie. Każde ujęcie komunikacyjne powinno opierać się na innej motywacji.

**Kategorie typowych ujęć komunikacyjnych:**

| Kategoria | Przykładowe ujęcie komunikacyjne |
|---------|--------------|
| Problem | „Przestań marnować czas na X” |
| Wynik | „Osiągnij Y w Z dni” |
| Społeczny dowód słuszności | „Dołącz do ponad 10 000 zespołów, które…” |
| Ciekawość | „Sekretne X, którego używają najlepsze firmy” |
| Porównanie | „W przeciwieństwie do X, robimy Y” |
| Pilność | „Ograniczony czas: zdobądź X za darmo” |
| Tożsamość | „Stworzony dla [konkretnej roli/typu]” |
| Wbrew obiegowej opinii | „Dlaczego [powszechna praktyka] nie działa” |

### Krok 2: Wygeneruj zmiany dla każdego ujęcia komunikacyjnego

Dla każdego ujęcia komunikacyjnego wygeneruj wiele odmian. Różnią się:
- **Wybór słowa** — synonimy, aktywny vs. pasywny
- **Specyfika** — liczby a twierdzenia ogólne
- **Ton** — bezpośredni vs. pytanie vs. polecenie
- **Struktura** — krótka informacja vs. pełne zestawienie korzyści

### Krok 3: Sprawdź zgodność ze specyfikacjami

Przed dostarczeniem sprawdź każdy element kreacji pod kątem limitów znaków platformy. Oznacz wszystko, co przekracza limit, i zapewnij okrojoną alternatywę.

### Krok 4: Zorganizuj do przesłania

Prezentuj kreację w ustrukturyzowanym formacie, który odpowiada wymaganiom platformy reklamowej dotyczącym przesyłania.

---

## Iteracja na podstawie danych dotyczących wydajności

Gdy użytkownik podaje dane dotyczące wydajności, wykonaj następujący proces:

### Krok 1: przeanalizuj zwycięzców

Przyjrzyj się kreacjom najskuteczniejszym (pod względem CTR, współczynnika konwersji lub ROAS – zapytaj, który wskaźnik ma największe znaczenie) i zidentyfikuj:

- **Zwycięskie motywy** — Jakie tematy lub bolesne punkty pojawiają się w przypadku najskuteczniejszych kreacji?
- **Zwycięskie struktury** — Pytania? Oświadczenia? Polecenia? Statystyki?
- **Zwycięskie wzorce słów** — Określone słowa lub frazy, które się powtarzają?
- **Wykorzystanie limitu znaków** — Czy najlepsze kreacje są krótsze czy dłuższe?

### Krok 2: Analiza przegranych

Przyjrzyj się najsłabszym kreacjom i zidentyfikuj:

- **Motywy, które się rozpadają** — Jakie ujęcia komunikacyjne nie rezonują?
- **Typowe wzorce u osób osiągających słabe wyniki** — Zbyt ogólne? Za długo? Zły ton?

### Krok 3: Wygeneruj nowe odmiany

Utwórz nową kreację, która:
- **Podwaja** zwycięskie motywy ze świeżym sformułowaniem
- **Rozszerza** zwycięskie ujęcia komunikacyjne w nowe odmiany
- **Testuje** 1–2 nowe, jeszcze nie zbadane ujęcia komunikacyjne
- **Unika** wzorców występujących u osób osiągających gorsze wyniki

### Krok 4: Udokumentuj iterację

Śledź, czego się nauczyłeś i co jest testowane:

```
## Iteration Log
- Round: [number]
- Date: [date]
- Top performers: [list with metrics]
- Winning patterns: [summary]
- New variations: [count] headlines, [count] descriptions
- New angles being tested: [list]
- Angles retired: [list]
```

---

## Standardy jakości tekstów

### Nagłówki, które przyciągają kliknięcia

**Mocne nagłówki:**
- Konkretne („Skróć czas raportowania o 75%” zamiast niejasne („Oszczędź czas”)
- Korzyści („Szybsza wysyłka kodu”) w porównaniu z funkcjami („Potok CI/CD”)
- Strona czynna („Automatyzuj swoje raporty”) zamiast pasywnego („Raporty są zautomatyzowane”)
- Jeśli to możliwe, podaj liczby („3x szybciej”, „w 5 minut”, „ponad 10 000 zespołów”)

**Unikaj:**
- Żargon, którego publiczność nie rozpozna
- Twierdzenia bez konkretów („Najlepsze”, „Wiodące”, „Najlepsze”)
- Wszystkie wielkie litery lub nadmierna interpunkcja
- Clickbait, którego nie może dostarczyć strona docelowa
- Skrócone lub zastępcze nazwy produktów — używaj dokładnej nazwy podanej
  w briefie, w każdym polu każdej koncepcji, chyba że skrócona forma została
  wyraźnie zatwierdzona

### Testuj hipotezy, które mogą przegrać

Jeśli do koncepcji dodajesz hipotezę testową, sformułuj ją tak, aby wynik mógł
wykazać, że się mylisz. „To przemówi do najemców” nie może przegrać; „osiągnie
wyższy CTR niż wariant kontrolny wśród najemców” może.

- Podaj nazwę wskaźnika (CTR, CVR, CPA, wskaźnik thumbstop) i porównanie —
  z jakim wariantem kontrolnym lub inną koncepcją i w jakiej grupie odbiorców
- Podaj oczekiwany kierunek i wielkość, jeśli istnieje linia podstawowa
  („+15% CTR w porównaniu z Koncepcją A”)
- Hipoteza powinna wynikać z motywacji ujęcia komunikacyjnego, tak aby wygrana lub
  przegrana uczyła czegoś o odbiorcach, a nie tylko o materiale

### Bez oznak tekstu generowanego przez AI

Tekst reklamy, który brzmi jako wygenerowany, wygląda jak każda inna reklama w kanale, a generowanie na dużą skalę zwielokrotnia tik, jaki ma pierwsza wersja robocza. Sprawdź całą partię.

Nigdy nie pisz tych:
- **Kontrast ujawnia**: „To nie X, to Y.” „Nie dlatego, że X. Ponieważ Y.” Podaj Y bezpośrednio, podając powód.
- **Listy zaprzeczeń**: „Żadnego X, żadnego Y, żadnego Z.” Powiedz, co się stanie. Jedna zwykła nieobecność („Nie wymaga karty”) jest w porządku.
- **Dopisywanie kolejnych członów zdania**: pełne twierdzenie, następnie przecinek i dalsze klauzule przekształcające. Zakończ zdanie na twierdzeniu.
- **Pytania z odpowiedziami i dwukropek ujawniają**: „Rezultat? 3x szybciej.” „Najlepsza część: uczy się”. Pytania FAQ i pytanie zadawane własnym głosem czytelnika są w porządku.
- **Zwroty standardowe**: „Pożegnaj”, „X w nowej odsłonie”, „Odblokuj moc”, „Przenieś to na wyższy poziom”, „Oto rzecz”.
- **Myślniki** w nagłówkach, opisach i tekście głównym.

Oznaki AI specyficzne dla reklam:
- **Skumulowane negacje, aby zmieścić się w limicie znaków**: „Bez konfiguracji. Żadnych opłat. Żadnych umów.” Zachowaj to, co najważniejsze i wykorzystaj miejsce na fakt.
- **Hook slop**: ogólne „POV:”, „Przestań przewijać”, „Oto, czego nikt ci nie powie o X”. Zdobądź kolejną sekundę, prezentując coś konkretnego dla widza. Haczyk POV jest w porządku, gdy sytuacja jest wyjątkowo specyficzna („POV: jest 15:00, a ty pijesz czwartą kawę”).
- **CTA slop**: „Rozpocznij już dziś”, „Dołącz do tysięcy zadowolonych klientów”. Nazwij akcję i co dzięki niej zyskasz.

W całej partii zmieniaj kształty zdań. Dziesięć wariantów o takim samym początku wygląda na wygenerowane, nawet jeśli każda z nich jest w porządku osobno. Aby uzyskać pełną czarną listę, skorzystaj z materiału o oznakach AI umiejętności **copywriting**.

### Opisy, które konwertują

Opisy powinny uzupełniać nagłówki, a nie je powtarzać. Użyj opisów, aby:
- Dodaj punkty potwierdzające (liczby, referencje, nagrody)
- Rozpatrz zastrzeżenia („Nie jest wymagana karta kredytowa”, „Zawsze bezpłatne dla małych zespołów”)
- Wzmocnij CTA („Rozpocznij bezpłatny okres próbny już dziś”)
- Dodaj pilność, jeśli jest prawdziwa („Ograniczenie do pierwszych 500 rejestracji”)

---

## Formaty wyjściowe

### Standardowe wyjście

Organizuj według ujęcia komunikacyjnego, z liczbą znaków:

```
## Angle: [Pain Point — Manual Reporting]

### Headlines (30 char max)
1. "Stop Building Reports by Hand" (29)
2. "Automate Your Weekly Reports" (28)
3. "Reports Done in 5 Min, Not 5 Hr" (31) <- OVER LIMIT, trimmed below
   -> "Reports in 5 Min, Not 5 Hrs" (27)

### Descriptions (90 char max)
1. "Marketing teams save 10+ hours/week with automated reporting. Start free." (73)
2. "Connect your data sources once. Get automated reports forever. No code required." (80)
```

### Masowe wyjście CSV

W przypadku generowania na dużą skalę (ponad 10 odmian) oferuj format CSV do bezpośredniego przesyłania:

```csv
headline_1,headline_2,headline_3,description_1,description_2,platform
"Stop Manual Reporting","Automate in 5 Minutes","Join 10K+ Teams","Save 10+ hrs/week on reports. Start free.","Connect data sources once. Reports forever.","google_ads"
```

### Statyczne wyjście wsadowe (tryb 3)

W przypadku skalowanych partii statycznych zapisz w datowanym folderze z indeksem:

```
outputs/YYYY-MM-DD/
  INDEX.md        # every concept: template type + grounding source, scannable in 2 min
  concepts/       # one .md per concept: headline, body, visual description, image prompt, grounding
  images/         # generated images, if an image tool is configured
```
Format według koncepcji jest zdefiniowany w [references/static-ad-templates.md](references/static-ad-templates.md). Obsługuje to ludzki przepływ pracy: otwórz folder, zeskanuj plik INDEX.md, wybierz 5–10 najlepszych do testów — wybranie 5 zwycięzców z 50 koncepcji zapewnia lepszą kreatywność niż wybranie 5 z 10.

### Strona recenzji kreacji (zatwierdzenie klienta/interesariuszy)

Kiedy osoba, która nie jest Tobą, musi przejrzeć i wybrać – klient, partner, interesariusz – utwórz **stronę przeglądu kreacji**: samodzielny artefakt HTML, który przedstawia każdą koncepcję jako makietę platformy In-Feed (Instagram/Facebook z przełącznikiem profilu reklamy partnerskiej), dzieli karuzele na oznaczony scenorys klatka po klatce, umożliwia przełączanie wariantów nagłówka i tekstu i ujawnia, co jest oparte na prawdziwych zasobach. To wizualna aktualizacja INDEX.md — decyzja została podjęta na podstawie jednego łącza, zamiast czytania Markdown. Szablon jest dostarczany pod adresem [assets/creative-review-template.html](assets/creative-review-template.html) (jeden plik, bez kompilacji, można go hostować w dowolnym miejscu); zapełnij swój obiekt `DATA` na podstawie wygenerowanych koncepcji. Pełny model danych, podstawowe zasady (wymagany jest blok ujawnień) i dostarczanie w [references/creative-review-page.md](references/creative-review-page.md).

### Raport iteracji

Podczas iteracji dołącz podsumowanie:

```
## Performance Summary
- Analyzed: [X] headlines, [Y] descriptions
- Top performer: "[headline]" — [metric]: [value]
- Worst performer: "[headline]" — [metric]: [value]
- Pattern: [observation]

## New Creative
[organized variations]

## Recommendations
- [What to pause, what to scale, what to test next]
```

---

## Proces generowania wsadowego
W przypadku produkcji kreatywnej na dużą skalę (zespół ds. rozwoju firmy Anthropic generuje ponad 100 odmian na cykl):

### 1. Podziel pracę na podzadania
- **Generowanie nagłówków** — Koncentruje się na klikalności
- **Generowanie opisu** — Koncentruje się na konwersji
- **Główne generowanie tekstu** — Nastawione na zaangażowanie (Meta/LinkedIn)

### 2. Generuj falami
- Fala 1: Ujęcia komunikacyjne rdzenia (3-5 ujęć komunikacyjnych, 5 odmian każdy)
- Fala 2: Rozszerzone wariacje na temat 2 najlepszych ujęć komunikacyjnych
- Fala 3: Dzikie karty (sprzeczne, emocjonalne, specyficzne)

### 3. Filtr jakości
- Usuń wszystko, co przekracza limit znaków
- Usuń duplikaty lub prawie duplikaty
- Flaguj wszystko, co może naruszać zasady platformy
- Upewnij się, że kombinacje nagłówków i opisów mają sens

---

## Typowe błędy

- **Tworzenie nagłówków, które działają tylko razem** — nagłówki RSA są łączone losowo
- **Ignorowanie limitów znaków** — Platformy są obcinane bez ostrzeżenia
- **Wszystkie odmiany brzmią tak samo** — Zmieniaj ujęcia komunikacyjne, a nie tylko dobór słów
- **Brak nagłówków wezwań do działania** — reklamy w wyszukiwarce wymagają nagłówków zorientowanych na działanie, aby zwiększyć liczbę kliknięć; uwzględnić co najmniej 2-3
- **Opisy ogólne** — „Dowiedz się więcej o naszym rozwiązaniu” marnuje miejsce
- **Iteracja bez danych** — Przeczucia są mniej wiarygodne niż metryki
- **Generowanie bez oparcia na dowodach** — Nieugruntowane koncepcje czyta się jak każdą inną reklamę w kanale; Najpierw karm umiejętności wygrywającymi reklamami, recenzjami i komentarzami
- **Pomijanie komentarzy** — Komentarze do reklam zawierają zastrzeżenia i uwagi zgłaszane przez klientów; te zazwyczaj konwertują najlepiej
- **Testowanie zbyt wielu rzeczy na raz** — Zmień jedną zmienną na cykl testowy
- **Zbyt wcześnie wycofuję kreację** – Zanim ocenisz, poczekaj na ponad 1000 wyświetleń

---

## Integracja narzędzi

Aby uzyskać informacje na temat pobierania danych dotyczących wydajności i zarządzania kampaniami, zobacz [rejestr narzędzi](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/REGISTRY.md).

| Platforma | Pobieranie danych o skuteczności | Zarządzaj kampaniami | Przewodnik |
|---------|:-----------------------------------:|:----------------:|-------|
| **Reklamy Google** | `google-ads campaigns list`, `google-ads reports get` | `google-ads campaigns create` | [google-ads.md](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/integrations/google-ads.md) |
| **Metareklamy** | `meta-ads insights get` | `meta-ads campaigns list` | [meta-ads.md](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/integrations/meta-ads.md) |
| **Reklamy LinkedIn** | `linkedin-ads analytics get` | `linkedin-ads campaigns list` | [linkedin-ads.md](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/integrations/linkedin-ads.md) |
| **Reklamy TikTok** | `tiktok-ads reports get` | `tiktok-ads campaigns list` | [tiktok-ads.md](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/integrations/tiktok-ads.md) |

### Przepływ pracy: pobieranie danych, analizowanie, generowanie

```bash
# 1. Pull recent ad performance
node tools/clis/google-ads.js reports get --type ad_performance --date-range last_30_days

# 2. Analyze output (identify top/bottom performers)
# 3. Feed winning patterns into this skill
# 4. Generate new variations
# 5. Upload to platform
```

> **Pomiń prace integracyjne.** Krok 1 jest trudny do samodzielnego uruchomienia — API Google
> Ads (lub Meta / LinkedIn / TikTok), OAuth i zapytanie raportowe dla każdego
> konta, powtarzane za każdym razem. [Magister](https://magistermarketing.com?ref=marketingskills)
> to autonomiczny agent marketingowy działający na tych samych umiejętnościach, który natywnie pobiera
> wyniki reklam: odczytuje Twoje konta przez typowane integracje
> wymagające zatwierdzenia, bez konfiguracji, a następnie stosuje tę umiejętność do
> wyników. Jeśli samodzielnie łączysz takie pobieranie danych, warto go sprawdzić.>
> *Ujawnienie: Magister został stworzony przez Coreya Hainesa, który utrzymuje to repozytorium.*
> Aby zamiast tego samodzielnie uruchomić ściąganie, użyj interfejsu CLI platformy reklamowej repozytorium (konfiguracja w
> [narzędzia/SETUP.md](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/SETUP.md)),
> lub złącze raportowania, takie jak Supermetrics lub Coupler.

---

## Powiązane umiejętności

- **ads**: do strategii kampanii, kierowania, budżetów i optymalizacji
- **marketing-loops**: do uruchamiania statycznego generowania wsadowego w powtarzającym się rytmie (pętla codziennego upuszczania kreacji)
- **customer-research**: Do recenzji i komentarzy dotyczących eksploracji podczas budowania korpusu materiałów wejściowych opartych na dowodach
- **copywriting**: w przypadku tekstu strony docelowej (na której trafia ruch reklamowy)
- **ab-testing**: Do konstruowania kreatywnych testów z zachowaniem rygoru statystycznego
- **marketing-psychology**: O zasadach psychologicznych stojących za wysokowydajnymi kreacjami
- **copy-editing**: do dopracowania tekstu reklamy przed premierą