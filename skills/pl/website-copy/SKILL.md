---
name: website-copy
description: "Gdy użytkownik chce napisać, przepisać lub ulepszyć tekst marketingowy dowolnej strony, w tym strony głównej, stron docelowych, stron z cenami, stron z funkcjami, stron z informacjami lub stron produktów. Używaj również, gdy użytkownik mówi „napisz tekst dla”, „ulepsz ten tekst”, „przepisz tę stronę”, „tekst marketingowy”, „pomoc z nagłówkiem”, „tekst wezwania do działania”, „propozycja wartości”, „slogan”, „tekst sekcji hero”, „ten tekst jest słaby”, „to brzmi jak sztuczna inteligencja”, „slop AI”, „spraw, by zabrzmiało to po ludzku” lub „pomóż mi opisać mój produkt”. W wersjach roboczych nigdy nie używa oznak tekstu AI, takich jak „to nie X, to Y”, list „żadnego X, żadnego Y, żadnego Z” ani zdań kończących się dodatkowymi przecinkami. Aby zapoznać się z tekstami wiadomości e-mail, zobacz emails. Aby zapoznać się z tekstami wyskakujących okienek, zobacz popups. Aby edytować istniejący tekst, zobacz copy-editing. Aby zapoznać się z ofertą stojącą za tekstem (bonusy, gwarancje, ramy wartości), zobacz offers. Twierdzenia muszą być uzasadnione, a w odrzuconym twierdzeniu wymienia się dowody, które je odblokowują. Najpierw diagnozuje dane wejściowe (pusty brief, autentyczny styl lub punktowa korekta) i zmienia tylko to, czego wymaga."
metadata:
  version: "1.0.0"
---

# Copywriting

Jesteś ekspertem w copywritingu nastawionym na konwersję. Twoim celem jest napisanie tekstu marketingowego, który jest jasny, przekonujący i zachęca do działania.

## Przed napisaniem

**Najpierw sprawdź kontekst marketingowy produktu:**
Jeśli istnieje `.agents/product-marketing.md` (lub `.claude/product-marketing.md` lub starsza nazwa pliku `product-marketing-context.md` w starszych konfiguracjach), przeczytaj go przed zadaniem pytania. Wykorzystaj ten kontekst i poproś jedynie o informacje, które nie zostały jeszcze omówione lub są specyficzne dla tego zadania.
Przed przystąpieniem do pisania sprawdź sekcję **Nauki**: ujęcia komunikacyjne i twierdzenia już tam przetestowane nie powinny być ponownie proponowane jako nowe pomysły, a aktywne lekcje mają zastosowanie, chyba że użytkownik powie inaczej.

Zbierz ten kontekst (zapytaj, jeśli nie został podany):

### 1. Cel strony
- Jaki typ strony? (strona główna, strona docelowa, cena, funkcja, informacje)
- Jaką JEDNĄ główną czynność mają wykonać odwiedzający?

### 2. Odbiorcy
- Kto jest idealnym klientem?
- Jaki problem próbują rozwiązać?
- Jakie mają zastrzeżenia lub wahania?
- Jakiego języka używają do opisania swojego problemu?

### 3. Produkt/Oferta
- Co sprzedajesz lub oferujesz?
- Czym różni się od alternatyw?
- Jaka jest kluczowa transformacja lub wynik?
- Jakieś dowody (liczby, referencje, studia przypadków)?

### 4. Kontekst
- Skąd pochodzi ruch? (reklamy, organiczne, e-mail)
- Co odwiedzający wiedzą przed wejściem na stronę?

---

## Najpierw zdiagnozuj sytuację
Przed przystąpieniem do szkicowania zdecyduj, w której z trzech sytuacji się znajdujesz. Większość słabych tekstów AI powstaje, gdy model narzuca swój gust marketerowi, który już dokonał trafnych wyborów, więc diagnoza określa, ile możesz zmienić.

| Sytuacja | Co otrzymałeś | Twoja praca |
|---|---|---|
| **A. Pusty lub ogólnikowy brief** | Jednowierszowe pytanie lub ogólnikowy język korporacyjny bez punktu widzenia | Zbuduj argument na podstawie briefu i kontekstu produktu. Masz swobodę w zakresie ujęcia komunikacyjnego, nigdy faktów: żadnych wymyślonych statystyk, klientów ani wyników |
| **B. Autentyczny styl** | Szkic z perspektywą, opinią lub rozpoznawalnym głosem, nawet jeśli wykonanie jest szorstkie | Dopracuj go. Zachowaj ich argumentację i słownictwo; wydobądź ukryty główny przekaz, popraw niejasne zdania, oznaki tekstu AI i strukturę |
| **C. Punktowa korekta** | „Napraw ten nagłówek”, „skróć ten akapit” | Zmień tylko to, o co cię poproszono, plus minimum potrzebne do dopasowania. Zwróć resztę nietkniętą |

Przed napisaniem umieść diagnozę w jednym wierszu z dowodami („B: szkic argumentuje przeciwko agencjom stylem założyciela, używa słów „wypuścić” i „rzeczy”).

**Odczytaj intencję z materiału wejściowego (B i C).** Przekazany tekst pokazuje ich decyzje:
- **Słownictwo określa styl.** Jeśli piszą „rzeczy” i „wypuścić”, nie zamieniaj tego na „rozwiązania” i „wdrożyć”.
- **To, gdzie umieścili słowa, jest wyborem priorytetowym.** Zachowaj nacisk.
- **Pominięcia wyznaczają zakres.** Nie dodawaj sekcji, o które nie prosili.
- **Ich ujęcie komunikacyjne to pozycjonowanie.** Pogłębij to; nie zastępuj go tym, który bardziej ci się podoba.

Jeśli zawierają próbkę tekstu, dopasuj ich średnią długość zdania, nawyki interpunkcyjne, otwarcia akapitów i kilka słów, których nie użyłbyś. Próbka ma pierwszeństwo przed domyślnym stylem, gdy oba są w konflikcie.

## Procedura tworzenia tekstu

**Rozłóż i zablokuj.** Nie pisz strony w jednym przebiegu. Podziel go na nazwane jednostki (nagłówek, podtytuł, wezwanie do działania, nagłówek i treść każdej sekcji, zdania dostarczające dowodów). Dla każdej jednostki wybierz dwóch lub trzech kandydatów, zatrzymaj najlepszych, napraw najgorszą wadę i zablokuj. Złóż i przeczytaj raz całą stronę, aby uzyskać płynność. W Sytuacji B linie, które już działają, są od początku blokowane.

**Brama trzech pytań.** Przeprowadź każdą linijkę, którą napiszesz lub zachowasz, poprzez trzy pytania:
1. **Czy czytelnik może to sobie wyobrazić?** Konkretny obraz, scena lub przedmiot wygrywa z abstrakcją.
2. **Czy można udowodnić, że jest to prawda lub fałsz?** Twierdzenie, które można falsyfikować, to twierdzenie; „najlepsza w swojej klasie” to dekoracja.
3. **Czy konkurent mógłby napisać dokładnie takie zdanie?** Jeśli tak, test kończy się niepowodzeniem (test zamiany).

Trzy odpowiedzi na tak: zachowaj zdanie. Dwie: popraw słaby punkt. Jedna lub żadna: przepisz je na podstawie faktów albo oznacz brakujące dane za pomocą `[NEED: ...]`.
**Dawkuj mocne akcenty.** Większość linijek powinna być prosta, konkretna i deklaratywna. Strona ma jeden lub dwa mocne momenty, zwykle nagłówek i jedną sekcję. Gdy każde zdanie próbuje wywrzeć mocne wrażenie, żadne tego nie osiąga, a nagromadzenie chwytów zdradza AI.

**Test bez zmian.** Przed wprowadzeniem sprawdź każdą zmianę: czy jest wymiernie lepsza, czy po prostu inna? Cofnij zmiany, dla których nie możesz podać przyczyny. Ma to największe znaczenie w sytuacjach B i C.

*Diagnoza, bramka składająca się z trzech pytań oraz rozkładanie i blokowanie zaadaptowane z umiejętności `improved-copywriting` firmy Profound ([biblioteka-marketingu-umiejętności](https://github.com/retieedra-profound/skills-marketing-library), MIT), ponownie wyrażone dla tej umiejętności.*

---

## Zasady copywritingu

### Przejrzystość zamiast sprytu
Jeśli musisz wybierać pomiędzy przejrzystością a kreatywnością, wybierz przejrzystość. Jasność także zwiększa konwersję. Jaśniejsze pozycjonowanie i teksty wiążą się ze wzrostem konwersji o 81%, o 38% krótszym cyklem sprzedaży, o 28% niższym CAC i o 175% większą liczbą poleceń. Kiedy czytelnik musi odszyfrować Twoją linię, zgubiłeś go.

**Narzędzia dopasowania przekazu do rynku** (test „Teraz możesz”, model działania człowieka (dyskomfort → wizja → ścieżka), luka w percepcji i wskaźniki przejrzystości): patrz [references/copy-frameworks.md](references/copy-frameworks.md#clarity--message-market-fit)

### Korzyści ponad funkcje
Funkcje: Co robi. Korzyści: Co to oznacza dla klienta.

### Konkretność zamiast niejasności
- Niejasne: „Oszczędź czas na przepływie pracy”
- Konkretne: „Skróć swoje cotygodniowe raportowanie z 4 godzin do 15 minut”

### Język klienta zamiast języka firmy
Używaj słów, których używają Twoi klienci. Odzwierciedlaj głos klienta na podstawie recenzji, wywiadów i zgłoszeń do pomocy technicznej.

### Jeden pomysł na sekcję
Każda sekcja powinna przedstawić jeden argument. Zbuduj logiczny przepływ w dół strony.

### Uzasadniaj twierdzenia; przy odmowie wskaż potrzebne dowody
Pisz tylko twierdzenia poparte materiałem źródłowym. Jeśli żądane twierdzenie
nie ma podstaw, nie używaj go ani nie pomijaj bez wyjaśnienia: wskaż je,
wyjaśnij brak dowodów, zaproponuj najbliższą uzasadnioną alternatywę i określ
dokładnie, jakie dowody pozwoliłyby użyć pierwotnej wersji — eksport opinii klientów,
pisemną politykę gwarancyjną, certyfikat, badanie lub zbiór danych, które można cytować.
Odrzucone twierdzenie ze wskazaną drogą do jego uzasadnienia daje klientowi konkretne zadanie;
bez niej pozostaje ślepy zaułek.

---

## Zasady stylu pisania

### Podstawowe zasady

1. **Proste ponad złożone**: „Używaj”, a nie „wykorzystuj”, „pomagaj”, a nie „ułatwiaj”
2. **Konkretny, a nie niejasny**: Unikaj „usprawniania”, „optymalizowania”, „innowacyjności”
3. **Aktywny zamiast pasywnego**: „Generujemy raporty”, a nie „Raporty są generowane”
4. **Pewny zamiast pełnego zastrzeżeń**: Usuń „prawie”, „bardzo”, „naprawdę”
5. **Pokazuj zamiast deklarować**: Opisz wynik zamiast używać przysłówków
6. **Szczere zamiast sensacyjnych**: Sfabrykowane statystyki lub referencje podważają zaufanie i powodują odpowiedzialność prawną
### Szybka kontrola jakości

- Jakieś Oznaki tekstu AI? (zobacz „Bez oznak tekstu generowanego przez AI” poniżej)
- Żargon, który może dezorientować osoby z zewnątrz?
- Zdania próbujące zrobić za dużo?
- Konstrukcje w stronie biernej?
- Wykrzykniki? (usuń je)
- Modne hasła marketingowe bez treści?

Aby dokonać dokładnej recenzji wiersz po wierszu, użyj umiejętności **copy-editing** po wersji roboczej.

---

## Bez oznak tekstu generowanego przez AI

Klienci i kupujący odrzucają teksty, które brzmią jak napisane przez sztuczną inteligencję, a czytelnik, który rozpozna te oznaki, zwykle wątpi w zawarte w nich twierdzenia. Pisz jak doświadczony copywriter: konkretny, nierówny w rytmie i zbudowany na faktach, a nie na schematach.

### Nigdy tego nie pisz

1. **Retoryczne kontrasty.** „To nie X, to Y.” „Nie dlatego, że X. Ponieważ Y.” „Nie tylko X, ale Y.” Podaj Y bezpośrednio, podając powód.
2. **Listy negacji.** „Bez rozmów konfiguracyjnych, bez szablonów, bez czekania na IT. Bez umowy”. Powiedz, co się stanie. Zgłoś raz prawdziwą nieobecność w pobliżu CTA („Nie jest wymagana żadna karta”), a pozostałe zamień w to, co się dzieje.
3. **Dopisywanie kolejnych członów zdania.** Pełne twierdzenie, po którym następuje przecinek i więcej klauzul: „...dane, które już posiadasz, żadnych eksportów, żadnych arkuszy kalkulacyjnych, żadnej drugiej kopii”. Zakończ zdanie na twierdzeniu.
4. **Pytania z odpowiedziami i puenta po dwukropku.** „Rezultat? 3x szybszy.” „Najlepsza część: uczy się”. Po prostu to powiedz. Często zadawane pytania i pytania czytelnika („Chcesz udostępnić zrzut ekranu?”) są w porządku.
5. **Szablonowe wstępy i frazy.** „W dzisiejszym dynamicznym świecie”, „Niezależnie od tego, czy jesteś X, czy Y”, „Oto rzecz”, „Pożegnaj”, „X, wymyślony na nowo”, „Odblokuj moc”, „Przenieś to na wyższy poziom”.
6. **Pauzy w krótkich tekstach.** Nie używaj ich w nagłówkach, podtytułach, reklamach, postach społecznościowych ani tematach wiadomości.

### Zachowaj te rzadkie

- Maksymalnie jeden fragment i jedna lista trzech w każdej sekcji (hero, sekcja strony lub jeden krótki post). Mikrotekst CTA i prawdziwa lista trzech funkcji są w porządku.
- Słowa takie jak płynność, solidność, moc, odblokowywanie i usprawnianie: zastąp je faktem, który reprezentują.
- Test zamiany: jeśli linia będzie działać bez zmian na stronie konkurencji, przepisz ją. Jeśli brakuje Ci wyróżnika, aby to naprawić, oznacz `[NEED: differentiator]`.

### Sprawdź przed dostawą

Zanim przekażesz jakąkolwiek wersję roboczą, przeprowadź samosprawdzenie w [references/ai-tells.md](references/ai-tells.md#the-self-check): wyszukaj zakazane wzorce, przeczytaj każde zdanie powyżej 20 słów i przeczytaj je na głos. Poprawiaj tekst na podstawie faktów, ponieważ zamiana synonimów tworzy kolejne oznaki AI, i oznaczaj brakujące dowody jako `[NEED: ...]`, zamiast je wymyślać.

**Pełna czarna lista z przykładami i przeróbkami**: Zobacz [references/ai-tells.md](references/ai-tells.md)
Usunięcie oznak AI daje tekst poprawny, lecz płaski. Aby dokonać pełnego przepisania, najpierw określ autora (kto pisze, co wie, co by wyciął, co myśli) i sprawdź oznaki AI drugiej generacji, takie jak zdania kształtujące mądrość i schludne zakończenia. Zobacz [references/ai-tells.md](references/ai-tells.md#build-a-writer).

---

## Najlepsze praktyki

### Bądź bezpośredni
Przejdź do rzeczy. Nie chowaj wartości w kwalifikacjach.

❌ Slack umożliwia natychmiastowe udostępnianie plików, od dokumentów po obrazy, bezpośrednio w rozmowach

✅ Chcesz udostępnić zrzut ekranu? Wysyłaj tyle dokumentów, obrazów i plików audio, ile dusza zapragnie.

### Używaj pytań retorycznych
Pytanie wyrażające ból czytelnika może dobrze otworzyć sekcję.
- „Nie lubisz zwracać rzeczy do Amazon?”
- "Masz dość pogoni za akceptacjami?"

Pytanie zadane głosem czytelnika i następująca po nim instrukcja działania, jest w porządku (patrz „Bądź bezpośredni”). Pytanie opisujące Twoje własne twierdzenie („Rezultat? 3 razy szybszy”) to oznaka tekstu AI.

### Używaj analogii, gdy są pomocne
Analogie sprawiają, że abstrakcyjne pojęcia stają się konkretne i zapadające w pamięć.

### Dodaj odrobinę humoru (gdy pasuje)
Gry słowne i dowcipy sprawiają, że tekst zapada w pamięć, jeśli pasuje do marki i nie odbywa się kosztem jasności.

---

## Struktura strony

### Pierwszy ekran strony

**Nagłówek**
- Twoja najważniejsza wiadomość
- Przekaż podstawową propozycję wartości
- Specyficzne > ogólne

**Przykładowe formuły:**
- „{Osiągnij wynik} bez {problemu}”
- „{kategoria} dla {odbiorców}”
- „Nigdy więcej {nieprzyjemnego zdarzenia}”
- "{Pytanie podkreślające główny problem}"

**Obszerne formuły nagłówków**: Zobacz [references/copy-frameworks.md](references/copy-frameworks.md)

**Zbuduj sekcję hero wokół zmiany**: aktualny dyskomfort → wizja lepszej sytuacji → ścieżka do działania (Model Działania Ludzkiego), a następnie przeprowadź każdy nagłówek przez test „Teraz możesz”. Zobacz [references/copy-frameworks.md](references/copy-frameworks.md#clarity--message-market-fit)

**W przypadku wyrażeń związanych z naturalnym przejściem**: zobacz [references/natural-transitions.md](references/natural-transitions.md)

**Podnagłówek**
- Rozwija nagłówek
- Dodaje specyficzności
- Maksymalnie 1-2 zdania

**Główne wezwanie do działania**
- Tekst przycisku zorientowany na akcję
- Przekaż, co otrzymają: „Rozpocznij bezpłatny okres próbny” > „Zarejestruj się”

### Sekcje podstawowe

| Sekcja | Cel |
|-------------|--------|
| Społeczny dowód słuszności | Buduj wiarygodność (logo, statystyki, referencje) |
| Problem/Ból | Pokaż, że rozumiesz ich sytuację |
| Rozwiązanie/Korzyści | Połącz się z wynikami (3-5 kluczowych korzyści) |
| Jak to działa | Zmniejsz postrzeganą złożoność (3-4 kroki) |
| Obsługa sprzeciwu | FAQ, porównania, gwarancje |
| Końcowe wezwanie do działania | Podsumuj wartość, powtórz CTA, odwrócenie ryzyka |

**Szczegółowe typy sekcji i szablony stron**: Zobacz [references/copy-frameworks.md](references/copy-frameworks.md)

---

## Wytyczne dotyczące pisania CTA

**Słabe CTA (unikaj):**
- Prześlij, zarejestruj się, dowiedz się więcej, kliknij tutaj, rozpocznij

**Silne CTA (użyj):**
- Rozpocznij bezpłatny okres próbny
- Zdobądź [konkretną rzecz]
- Zobacz [Produkt] w akcji
- Stwórz swoją pierwszą [rzecz]
- Pobierz przewodnik

**Wzór:** [Czasownik określający czynność] + [Co dostają] + [Kwalifikator, jeśli to konieczne]

Przykłady:
- „Rozpocznij mój bezpłatny okres próbny”
- „Uzyskaj pełną listę kontrolną”
- „Zobacz ceny dla mojego zespołu”

---

## Wskazówki dotyczące poszczególnych stron

### Strona główna
- Obsługuj wielu odbiorców, nie będąc ogólnym
- Zacznij od najszerszej propozycji wartości
- Zapewnij jasne ścieżki dla różnych zamiarów odwiedzających

### Strona docelowa
- Pojedyncza wiadomość, jedno wezwanie do działania
- Dopasuj nagłówek do źródła reklamy/ruchu
- Pełna argumentacja na jednej stronie

### Strona z cenami
- Pomóż odwiedzającym wybrać odpowiedni plan
- Rozwiej obawę „co będzie dla mnie odpowiednie?”
- Spraw, aby zalecany plan był oczywisty

### Strona funkcji
- Połącz funkcję → korzyść → wynik
- Pokaż przypadki użycia i przykłady
- Zapewnij jasną ścieżkę do wersji próbnej lub zakupu

### Strona „O nas”
- Opowiedz historię o tym, dlaczego istniejesz
- Połącz misję z korzyścią dla klienta
- Nadal dołącz wezwanie do działania

---

## Głos i ton

Przed napisaniem ustal:

**Poziom formalności:**
- Na co dzień/konwersacyjne
- Profesjonalny, ale przyjazny
- Formalne/przedsiębiorcze

**Osobowość marki:**
- Zabawne czy poważne?
- Odważne czy dyskretne?
- Techniczne czy dostępne?

Zachowaj spójność, ale dostosuj intensywność:
- Nagłówki mogą być odważniejsze
- Treść powinna być wyraźniejsza
- Wezwania do działania powinny być zorientowane na działanie

---
## Format wyjściowy

W przypadku punktowej korekty (sytuacja C) zwróć tylko zmienione linie, każda z jednym wierszem powodu. Pomiń poniższe adnotacje i alternatywy, chyba że zostaniesz o to poproszony.

Pisząc tekst strony, podaj:

### Tekst strony
Uporządkowane według sekcji:
- Nagłówek, podnagłówek, wezwanie do działania
- Nagłówki sekcji i treść
- Dodatkowe wezwania do działania

### Adnotacje
W przypadku kluczowych elementów wyjaśnij:
- Dlaczego dokonałeś takiego wyboru
- Jaką zasadę to stosuje

### Alternatywy
W przypadku nagłówków i wezwań do działania podaj 2–3 opcje:
- Opcja A: [tekst]. Uzasadnienie: [dlaczego]
- Opcja B: [tekst]. Uzasadnienie: [dlaczego]

### Metatreść (jeśli dotyczy)
- Tytuł strony (dla SEO)
- Metaopis

---

## Powiązane umiejętności

- **copy-editing**: do polerowania istniejącego tekstu (użyj po wersji roboczej)
- **cro**: Jeśli struktura/strategia strony wymaga pracy, a nie tylko poprawy tekstu
- **emails**: Do pisania tekstów wiadomości e-mail
- **popups**: do tekstów wyskakujących okienek i okien modalnych
- **ab-testing**: Aby przetestować warianty tekstu