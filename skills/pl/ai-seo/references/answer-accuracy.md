# Dokładność odpowiedzi: sprawdzanie, co AI mówi o Tobie

Widoczność mierzy, czy się pojawiasz. Dokładność sprawdza, co powie odpowiedź, gdy już to zrobisz. Marka może pojawić się w każdej odpowiedzi, a mimo to być opisana cenami z zeszłego roku, brakującą integracją lub ograniczeniem, które naprawiono kilka miesięcy temu.

Duża część odpowiedzi to komentarz, o który użytkownik nigdy nie prosił. Analiza 50 000 odpowiedzi przeprowadzona przez firmę Profound (Profound, czerwiec 2026 r.) wykazała, że ​​około 47% treści odpowiedzi stanowiły niezamówione materiały redakcyjne: porównania, rankingi, zastrzeżenia i zalecenia. W tej warstwie redakcyjnej zwykle pojawiają się błędne twierdzenia na Twój temat.

Profound sprzedaje śledzenie widoczności AI, więc traktuj te liczby jako badania dostawców. Inne moduły śledzące przechwytujące tekst odpowiedzi na potrzeby tego rodzaju audytu to Ahrefs Brand Radar, zestaw narzędzi AI Semrush, Peec AI, Otterly i ZipTie.

## Kiedy go uruchomić

- Asystent podał nieprawidłową cenę, limit planu, funkcję lub kompatybilność
- Sprzedaż słyszy, że potencjalni klienci powtarzają coś fałszywego, co „powiedział ChatGPT”
- Po repozycjonowaniu, zmianie cen, rebrandingu lub wycofaniu produktu
- Kwartalnie dla dowolnej marki z produktem regulowanym, związanym z bezpieczeństwem lub wrażliwym na cenę

## Rejestr twierdzeń

Najpierw przechwyć odpowiedzi, a następnie zarejestruj po jednym wierszu na każde twierdzenie. Zapisz silnik, model lub powierzchnię, lokalizację, monit i datę wykonania każdej odpowiedzi, ponieważ twierdzenie, którego nie można odtworzyć, jest trudne do naprawienia.

| Pole | Co się w nim kryje |
|---|---|
| Silnik i data | ChatGPT (szukaj), Gemini, AI Overviews, Perplexity, Copilot, Claude; data przechwycenia |
| Prompt | Dokładne sformułowanie oraz do której rodziny promptów należy (zobacz [prompt-portfolio.md](prompt-portfolio.md)) |
| Twierdzenie | Zdanie w postaci wygenerowanej przez model |
| Rodzaj twierdzenia | Cena, dostępność, kompatybilność, funkcja, ograniczenia, porównanie, ranking, rekomendacja, zastrzeżenie, nastroje |
| Werdykt | Jeden z siedmiu poniżej |
| Dowód | Aktualne źródło, które to potwierdza lub zaprzecza |
| Prawdopodobne źródło | Strona, z której prawdopodobnie pochodzi twierdzenie: Twoja strona, dokumenty, kanał, profil, artykuł strony trzeciej, wątek na forum lub nieznany |
| Dotkliwość | Krytyczny, wysoki, średni lub niski |
| Właściciel | Kto naprawia źródło |

Wyodrębnij wszystkie twierdzenia, które mogą zmienić decyzję o zakupie, łącznie z tymi, o które użytkownik nie pytał. Pytanie dotyczące cen, które pojawia się bez monitu „ale brakuje mu logowania jednokrotnego”, to dwa twierdzenia.

### Siedem werdyktów

1. **Dokładne i aktualne**
2. **Dokładne, ale niekompletne**: prawdziwe, ale pomija fakt, który ma znaczenie (istnieje darmowy plan, ale odpowiedź pomija jego ograniczenia)
3. **Niejednoznaczne**: można odczytać jako prawdziwe lub fałszywe
4. **Nieaktualne**: było prawdą, teraz nie jest
5. **Fałsz**
6. **Subiektywne sformułowanie**: opinia stwierdzona jako fakt („najlepsze dla małych zespołów”, „trudne do ustalenia”)
7. **Nieweryfikowalne**: w obu przypadkach brak aktualnego źródła rozstrzygającego w którąkolwiek stronę
Sprawdź fakty z pierwszej ręki w porównaniu z aktualnymi materiałami dotyczącymi produktu oraz twierdzenia dotyczące świata zewnętrznego w oparciu o wiarygodne, niezależne źródła. Preferowane przez Ciebie sformułowania marketingowe nie są dowodem.

### Dotkliwość

| Poziom | Przykłady |
|---|---|
| **Krytyczny** | Błędy dotyczące bezpieczeństwa, kwestii prawnych, kwalifikowalności, ceny, dostępności lub zgodności, które mogą spowodować zły zakup lub realną szkodę |
| **Wysoki** | Fałszywe porównania, wymyślone ograniczenia, nieaktualne fakty dotyczące produktów w rodzinach promptów o wysokiej wartości |
| **Średni** | Niekompletne lub stronnicze przedstawienie, które w przekonujący sposób mogłoby zmienić decyzję |
| **Niski** | Ton i sformułowania, które nie zmieniają decyzji |

Wagę błędu oceniaj również według ekspozycji: średni błąd pojawiający się w każdym wydaniu najpopularniejszego komercyjnego monitu przewyższa wysoki błąd w jednym mało znanym monicie.

## Najpierw napraw źródło

Odpowiedź leży poniżej tego, co model odzyskał lub czego się nauczył. Przepisanie kopii strony głównej rzadko rozwiązuje twierdzenie wynikające z nieaktualnej recenzji strony trzeciej.

1. **Śledź to.** Przeszukaj treść twierdzenia, sprawdź, jakie źródła cytowała wyszukiwarka w celu uzyskania tej odpowiedzi, i poszukaj strony, na której znajduje się błędny fakt.
2. **Popraw własne źródła.** Wyraźnie podaj poprawny fakt na stronie, która powinna go zawierać, podając datę: strona z cenami, dokumentacja, dziennik zmian, strona porównawcza, centrum pomocy. Usuń lub przekieruj nieaktualną stronę. Aktualizuj kanały i dane strukturalne, które zawierają ten sam fakt.
3. **Napraw swoje profile.** G2, Capterra, rynki aplikacji, Crunchbase, LinkedIn i katalogi partnerów często zawierają nieaktualne wersje.
4. **Proś osoby trzecie wyłącznie o sprostowanie faktów.** Prześlij wydawcy prawidłowy fakt i źródło. Nie proś ich o usunięcie uzasadnionej krytyki.
5. **Przetestuj ponownie** te same prompty po ustalonym oknie obserwacyjnym (rozsądny punkt wyjścia to 4–8 tygodni), z kilkoma kontrolowanymi wariantami. Raportuj zmiany w czasie; jeden czysty przebieg niczego nie dowodzi.

Nigdy nie obiecuj, że poprawka źródła zmieni odpowiedź. Modele przekwalifikowują się i odzyskują wiedzę według własnych harmonogramów.

**Niedozwolone:** sfabrykowane poprawki, edytowanie Wikipedii o sobie, posty na forach pozorujące oddolne opinie (astroturfing) i wywieranie presji na wydawców, aby usuwali uzasadnioną krytykę. Łamią one zasady platformy, a modele coraz lepiej je dyskontują.

## Zgłoś

1. Współczynnik dokładności w całej kohorcie, najbardziej ryzykowna narracja i główny problem źródłowy
2. Rejestr twierdzeń
3. Poprawki z własnego źródła, każda z dokładnym faktem i stroną, która powinna to podać
4. Prośby osób trzecich o sprostowanie, oparte na faktach i źródłach
5. Plan i data ponownego testu
6. Niewiadome

Ten audyt łączy się z pracą związaną z pozycjonowaniem w [positioning-and-consensus.md](positioning-and-consensus.md): dokładność naprawia błędne fakty, pozycjonowanie naprawia złą historię. Pętla audytu dokładności AI w **marketing-loops** może to zaplanować.

---
*Pochodzenie ramowe: księga twierdzeń, zestaw werdyktów i skala dotkliwości zaadaptowane (wyrażone ponownie i zrestrukturyzowane) na podstawie umiejętności audytora ai-answer-accuracy-auditor na licencji MIT oraz badań „Parrot Problem” (czerwiec 2026 r.), przypisane.*