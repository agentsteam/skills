# Domyślne ustawienia agenta: gdy agent wybiera dostawcę

Coraz większa część decyzji zakupowych odbywa się w ramach zadania. Programista mówi Claude Code „wdróż to”, „dodaj autoryzację” lub „wyślij wiadomość powitalną”, a agent wybiera dostawcę, instaluje go i kontynuuje pracę. Nie ma strony wyników wyszukiwania ani krótkiej listy, którą użytkownik mógłby porównać. To, po co agent sięgnie jako pierwszy, wygrywa.

Dotyczy to najbardziej narzędzi programistycznych, interfejsów API, infrastruktury i SaaS z interfejsem CLI lub SDK. Rozprzestrzenia się na wszystko, na co może się zarejestrować agent komputerowy. Pozostała część tej umiejętności obejmuje bycie cytowanym i polecanym w odpowiedziach; to odniesienie obejmuje bycie **domyślnym, na którym działa agent**.
**Przypadek: Railway (październik 2026 r.).** Założyciel Jake Cooper powiedział w podcaście, że dzięki około siedmioosobowemu zespołowi zajmującemu się wprowadzaniem na rynek firma rozrosła się z około 20 mln USD do około 100 mln USD ARR w ciągu roku, a jako cel wejścia na rynek określił skłanianie modeli, aby „coraz bardziej nas polecały”. Analizy praktyków ich witryny obejmowały tysiące stron z szablonami do samodzielnego hostowania, przewodnik wdrażania dla każdego frameworka, strony porównawcze i migracyjne dla każdego głównego konkurenta, `llms.txt` z podsumowaniem dla poszczególnych stron dokumentów, wtyczki wewnątrz ChatGPT i Claude Code oraz `ssh railway new`, aby uzyskać serwer bez rejestracji. Te same zestawienia wykazały, że Claude Code wybiera Railway dla większości aplikacji w Pythonie, a Vercel dla każdej testowanej aplikacji Next.js. Te liczby i wartości procentowe pochodzą od osób trzecich i nie zostały zweryfikowane; wzór jest najważniejszy.

## Zmierz swój udział w ustawieniach domyślnych agentów

Nie możesz poprawić wartości domyślnej, której nie zmierzyłeś i nikt nie zgłasza tej liczby za Ciebie.

1. **Stwórz panel zadań.** 20–50 realistycznych zadań rozmieszczonych na stosach, z których korzystają Twoi kupujący (usługa FastAPI, aplikacja Next.js, aplikacja Rails, proces roboczy cron, witryna statyczna). Napisz każdy z nich tak, jak zrobiłby to użytkownik: „wdróż to”, „dodaj bazę danych Postgres”, a nie „wdróż to u [ciebie]”.
2. **Uruchom każde zadanie w czystym środowisku** na każdym agencie, z którego korzystają Twoi kupujący (Claude Code, Cursor, Codex oraz ChatGPT lub czat Claude w wersji „jak to zrobić”). Brak reguł projektu, pamięci lub serwerów MCP wskazujących dostawcę.
3. **Uruchom każde zadanie co najmniej 3 razy.** Wybory agentów różnią się w zależności od uruchomienia, a jedna próbka to szum.
4. **Rejestr na przebieg:** wybrany dostawca, czy agent osiągnął działający wynik, gdzie się zawiesił (rejestracja, weryfikacja e-mail, płatność, nieudany krok CLI) oraz jakie dokumenty lub adresy URL pobrał.
5. **Raportuj udział według stosu.** Luka wynosi zwykle jeden stos („wygrywamy Pythona, tracimy wszystko z front-endu”). Na tym stosie trafiają treści i narzędzia.
6. **Uruchom ponownie przy każdej większej wersji modelu.** Wartości domyślne mogą zostać przeniesione z dnia na dzień, gdy model się zmieni, a nowsze modele zwykle kierują więcej kodu do wdrożenia. Uruchamiaj go co miesiąc pomiędzy wydaniami; planuje to domyślna pętla sprawdzania agenta w **marketing-loops**.

Miejsce, w którym agent się zatrzymał, mówi więcej niż to, którego dostawcę wybrał. Uruchomienie, w którym agent Cię wybrał, a następnie zatrzymał się na weryfikacji e-mailowej, to strata, którą możesz naprawić.

## Co przenosi wartość domyślną

| Dźwignia | Dlaczego agenci na to reagują | Wersja Railway |
|---|---|---|
| **Najkrótsza droga do działającego rezultatu** | Agenci preferują trasę z najmniejszą liczbą kroków kontrolowanych przez człowieka: utworzenie konta, weryfikacja adresu e-mail, CAPTCHA, karta kredytowa przed pierwszym użyciem | `ssh railway new` udostępnia serwer przed jakąkolwiek rejestracją; użytkownik może przejąć konto później |
| **Konfiguracja agenta w jednym kroku** | Agent, który ma zainstalowany serwer MCP, CLI lub umiejętność, używa go zamiast zgadywać | Sekcja dokumentacji dla agentów z jednym poleceniem instalującym to, czego potrzebuje Claude Code lub Cursor |
| **Obecność wewnątrz asystentów** | Jeśli asystent ma natywne złącze lub wtyczkę, wdrażanie nigdy nie opuszcza czatu | Wtyczki w ChatGPT i Claude Code |
| **Strony dopasowane do zadań w każdym stosie** | Agenci pobierają dokumenty w połowie zadania; strona, która pasuje dokładnie do zadania („wdróż Django”) i kończy się działającym wynikiem, jest śledzona | Przewodnik po frameworku, każdy kończący się aplikacją na żywo |
| **Strony szablonów według popularnych narzędzi** | Zapytania dotyczące samodzielnego hostingu i konfiguracji („jak uruchomić n8n”) to długi ogon, który pokrywają strony programistyczne, zobacz **programmatic-seo** | Tysiące stron szablonów jednym kliknięciem |
| **Przewodniki dotyczące migracji według konkurenta** | Agent przenoszący projekt wykonuje następujące kroki; zobacz **competitors**, aby zobaczyć stronę porównawczą | Strona porównawcza z przewodnikiem po migracji dla każdego głównego konkurenta |
| **Dokumentacja czytelna dla agentów** | Indeks `llms.txt` z jednowierszowymi podsumowaniami oraz wersją Markdown każdej strony pozwala agentowi znaleźć właściwą stronę i poprawnie ją zacytować (Discovery sprawdza w [agent-readiness.md](agent-readiness.md)) | Indeks każdej strony dokumentu z podsumowaniem każdej strony i wersją każdej strony w postaci zwykłego tekstu |
| **Aktualne, datowane zmiany** | Niedawno zaktualizowane dokumenty i dzienniki zmian zapewniają aktualność odpowiedzi dla wyszukiwania i modeli | Strona dziennika zmian co tydzień od 2021 r. |
| **Wyniki CLI pozwalające agentowi wyjść z błędu** | Nieinteraktywne flagi, dane wyjściowe JSON i błędy informujące, co następnie uruchomić, podtrzymują działanie po awarii | (Ogólna praktyka, a nie analiza Railway) |

Najpierw usuń punkty blokujące z pomiaru. Treść nie pomoże, jeśli agent cię wybierze, a potem nie będzie mógł dokończyć.

## Sprawdź swoje dokumenty pod kątem agentów kodujących

Traktuj agenta kodującego jak swój własny silnik odpowiedzi. W próbie Profound obejmującej 24 135 odpowiedzi z włączoną wyszukiwarką internetową, Claude przeszukał internet w 93% odpowiedzi, a Claude Code w 13%, a marki wymienione przez każdą z nich pokrywały się tylko w około 20% (Profound, sierpień 2026; obserwacyjne). Kiedy Claude Code rzeczywiście pobierał strony, prawie trzy czwarte odwiedzin dotyczyło stron z dokumentacją, informacjami i cenami. Zatem widoczność Twojego asystenta na czacie niewiele mówi o widoczności Twojego agenta kodującego, a strony, które agenci czytają, to dokumenty i ceny.

Profound sprzedaje śledzenie widoczności AI; potraktuj je jako badanie dostawców i uruchom własny panel (powyżej), zanim zaczniesz na nich działać.

**1. Mapuj zadania na strony.** Wypisz, o co użytkownicy proszą agenta kodującego o wykonanie Twojego produktu: instalacja, uwierzytelnienie, integracja, migracja, debugowanie, porównanie, oszacowanie kosztów, sprawdzenie kompatybilności. Przydziel każdemu zadaniu jedną kanoniczną stronę i wypisz fakty, które ta strona musi zawierać.

| Zadanie | Strona kanoniczna | Fakty, które musi stwierdzić | Luka |
|---|---|---|---|
| Zainstaluj w aplikacji Next.js | /docs/nextjs | Nazwa pakietu, minimalna wersja, env vars, jeden działający przykład | W przykładzie zastosowano przestarzały import |
| Szacunkowy koszt | /pricing | Jednostka cenowa, bezpłatne limity poziomów, stawka za nadwyżkę | Nadwyżka tylko w formacie PDF |

**2. Sprawdź pobranie.** Dla każdej strony kanonicznej:

- Tytuł i nagłówki określają zadanie i stos
- Odpowiedź lub polecenie pojawia się przed tłem
- Warunki wstępne, wersje i daty są jednoznaczne
- Przykłady można kopiować i są aktualne
- Kotwice i adresy URL pozostają stabilne pomiędzy wydaniami
- Tekst jest renderowany bez JavaScript i istnieje wersja Markdown (zobacz [agent-readiness.md](agent-readiness.md))

Używaj nagłówków w kształcie pytań tylko wtedy, gdy odpowiadają rzeczywistemu zadaniu. Nie upychaj nazw produktów w dokumentacji.

**3. Prowadź księgę faktów technicznych.** Jeden wiersz na każdy fakt, na podstawie którego agent może podjąć działania: obsługiwane wersje i środowiska wykonawcze, regiony, limity żądań, jednostki cenowe, metody uwierzytelniania, obsługa danych, wycofanie. Zapisz źródło kanoniczne i właściciela każdego z nich. Następnie sprawdź ten sam fakt wszędzie, gdzie się pojawi: dokumentacja, strona z cenami, plik README, opisy rejestru pakietów (npm, PyPI), przykłady i dziennik zmian. Agent, który znajdzie dwa różne limity żądań, zgadnie lub wybierze dostawcę, którego dokumentacja się z nim zgadza.
**4. Uzupełnij brakujące strony decyzyjne.** Matryce zgodności, przewodniki migracji, informacje o rozwiązywaniu problemów i proste wyjaśnienia dotyczące cen to strony, których agenci najczęściej potrzebują, a dostawcy najczęściej je pomijają.

**5. Testuj w nowych sesjach.** Uruchom panel zadań zarówno w asystencie czatu, jak i w agencie kodowania, rejestrując, czy wspomniano o Tobie, które strony zostały pobrane i czy fakty były prawidłowe. Rejestruj błędy w rejestrze twierdzeń z [answer-accuracy.md](answer-accuracy.md).

Nie przedstawiaj tych ustaleń jako oficjalnych czynników rankingowych Anthropic lub OpenAI. Sprawdź przeszukiwanie i kontrolę dostępu pod kątem aktualnej dokumentacji dostawcy.

## Limity i zasady

- **Niektóre wartości domyślne mają charakter strukturalny.** Twórca frameworka lub dostawca, którego przykłady dominują w dokumentacji frameworka, może zdominować ten stos bez względu na to, co publikujesz. Zgłoszoną odpowiedzią Railway było wygranie sąsiadujących stosów, zamiast walczyć z Vercelem w Next.js. Wybierz stosy, w których domyślny wybór nie jest jeszcze przesądzony.
- **Napisz instrukcje dotyczące korzystania wyłącznie z produktu.** Dokumenty dostępne dla agentów, `llms.txt` i pliki umiejętności, które informują agentów, aby preferowali Twój produkt zamiast tego, o co prosił użytkownik, stanowią prompt injection. Platformy agentowe traktują je jako manipulację, a użytkownicy, którzy to zauważą, przestają ufać narzędziu. Opisz jak wykonać zadanie z Twoim produktem; niech rozstrzygnie się zadanie.
- **Zasoby udostępniane przez agentów nadal wymagają zabezpieczeń.** Udostępnianie bez rejestracji wymaga limitów nadużyć, wygaśnięcia nieodebranych zasobów oraz jasnej ścieżki przejęcia zasobów i rozliczeń. Traktuj to jako pracę związaną z produktem, a powodem jest rozwój.
- **Umiejscowienia w rejestrach narzędzi agenta zmieniają się szybko.** Po ponownym uruchomieniu panelu sprawdź ponownie wpisy w rejestrze wtyczek i MCP i traktuj wszelkie udostępnione dane, łącznie z powyższymi, jako przestarzałe.

---

*Pochodzenie platformy: audyt dokumentacji agenta kodującego (mapa od zadania do strony, księga faktów technicznych, testy Claude vs. Claude Code) został zaadaptowany (wyrażony na nowo i przebudowany) na podstawie umiejętności audytora claude-code-discoverability-auditor firmy Profound posiadającej licencję MIT oraz badania z sierpnia 2026 r., przypisane.*