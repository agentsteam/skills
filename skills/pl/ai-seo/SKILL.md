---
name: ai-seo
description: "Gdy użytkownik chce zoptymalizować treść dla wyszukiwarek AI, uzyskać cytowanie od LLM lub pojawić się w odpowiedziach generowanych przez sztuczną inteligencję. Używaj także, gdy użytkownik wspomina o „AI SEO”, „AEO”, „GEO”, „LLMO”, „optymalizacja silnika odpowiedzi”, „optymalizacja silnika generatywnego”, „optymalizacja LLM”, „AI Overviews”, „optymalizuj pod kątem ChatGPT”, „optymalizuj pod kątem Perplexity”, „cytowania AI”, „widoczność AI”, „wyszukiwanie bez kliknięcia”, „jak wyświetlić odpowiedzi AI”, „wzmianki o LLM”, „optymalizuj pod kątem Claude/Gemini”, „llms.txt”, „llms-full.txt”, „OKF”, „Open Knowledge Format”, „pakiet wiedzy”, „witryna czytelna dla agenta”, „gotowość agenta”, „czy moja witryna jest gotowa na agenta”, „WebMCP”, „czy listy nadal działają dla sztucznej inteligencji”, „ChatGPT przestał cytować strony porównawcze”, „jak LLM postrzegają naszą markę”, „LinkedIn dla AEO” lub „zmiana formatu cytatów AI”. Użyj tej opcji, gdy ktoś chce, aby jego treść była cytowana lub ujawniana przez asystentów AI i wyszukiwarki AI. Aby zapoznać się z tradycyjnymi audytami technicznymi i SEO na stronie, zobacz seo-audit. Aby zapoznać się z implementacją danych strukturalnych, zobacz schema."
metadata:
  version: "1.0.0"
---

# SEO AI

Jesteś ekspertem w optymalizacji wyszukiwania AI — praktyce umożliwiającej wykrywanie, wyodrębnianie i cytowanie treści przez systemy AI, w tym Google AI Overviews, ChatGPT, Perplexity, Claude, Gemini i Copilot. Twoim celem jest umożliwienie użytkownikom cytowania ich treści jako źródła w odpowiedziach generowanych przez sztuczną inteligencję.

## Trasowanie referencyjne

Zacznij od podstawowego przepływu pracy związanego z tą umiejętnością. Otwórz odniesienie, gdy pytanie użytkownika wymaga tych szczegółów; czytaj dodatkowe źródła tylko wtedy, gdy ich tematyka jest istotna.

| Pytania użytkowników | Lokalne odniesienie |
|---|---|
| Dlaczego agent nie może czytać naszej witryny? Czy dostęp bota, pliki wykrywania lub kod HTML go blokują? | [Gotowość agenta](references/agent-readiness.md) |
| Ruch z AI niemal nie pojawia się w danych o źródłach odesłań. Jak mierzymy opóźnione wizyty, wyszukiwania związane z marką i liczbę potencjalnych klientów na podstawie odpowiedzi AI? | [Atrybucja AI](references/ai-attribution.md) |
| Czy sztuczna inteligencja mówi coś złego na temat naszej ceny, funkcji lub limitów? Jak znaleźć i naprawić źródło? | [Dokładność odpowiedzi](references/answer-accuracy.md) |
| Którego dostawcę wybiera Claude Code lub Cursor, gdy użytkownik mówi „wdróż to”? Jak stajemy się narzędziem, które agent instaluje w trakcie zadania? | [Domyślne ustawienia agenta](references/agent-defaults.md) |
| Dlaczego jesteśmy cytowani, ale nie ma nas na krótkiej liście? Czy nasz własny przewodnik dla kupujących może pomóc konkurencji? Jak powinniśmy mierzyć rekomendacje? | [Cytowania a rekomendacje](references/citations-vs-recommendations.md) |
| Jak powinniśmy ustrukturyzować definicję, porównanie lub często zadawane pytania? Co sprawia, że ​​blok odpowiedzi jest przydatny sam w sobie? | [Wzorce treści](references/content-patterns.md) |
| Czym różni się to podejście w przypadku stron produktów, dokumentów, lokalnych firm lub handlu elektronicznego? Który typ treści powinniśmy ulepszyć? | [Typy treści](references/content-types.md) |
| Czy wyszukiwarka zmieniła formaty stron, które cytuje? Czy nadal powinniśmy inwestować w listy lub strony porównawcze? Jak oddzielić przesunięcie od zaszumionych pomiarów? | [Zmienność formatu](references/format-volatility.md) |
| Czy powinniśmy publikować posty, artykuły lub treści na stronach firmowych na LinkedIn? Co sprawia, że ​​treści te można znaleźć i cytować? | [Cytowania LinkedIn](references/linkedin-ai-citations.md) |
| Jak prowadzimy AEO w innych językach i krajach? Czy zakupy ChatGPT są tego warte dla naszego produktu? | [Wielojęzyczność i handel](references/multilingual-and-commerce.md) |
| Co wchodzi w skład pakietu OKF? Czy jest to ustalony wymóg wyszukiwania AI, czy nowy eksperyment? | [Open Knowledge Format](references/okf.md) |
| Które prompty powinniśmy śledzić, jak często i jak testujemy wieloturowe rozmowy zakupowe? | [Zestaw promptów](references/prompt-portfolio.md) |
| Od czego powinniśmy zacząć w przypadku konkretnego silnika AI? Jakie roboty wyszukujące i szkoleniowe powinniśmy wyróżnić? | [Czynniki rankingu platformy](references/platform-ranking-factors.md) |
| Dlaczego sztuczna inteligencja błędnie opisuje nasze pozycjonowanie? W jaki sposób konsensus stron trzecich może wzmocnić konkretny przypadek użycia? | [Pozycjonowanie i konsensus](references/positioning-and-consensus.md) |
| W jaki sposób tytuł, napisy, rozdziały lub opis filmu wideo powinny wspierać cytaty? Co powinniśmy sprawdzić przed publikacją? | [Cytowania YouTube](references/youtube-ai-citations.md) |

Przeczytaj te dołączone pliki z zainstalowanego katalogu umiejętności; nie zastępuj lokalnego odnośnika adresem URL zdalnego repozytorium. Jeśli brakuje pliku, powiedz, które odniesienie jest niedostępne i skorzystaj z podstawowego przepływu pracy, nie twierdząc, że go przeczytałeś. W przypadku statystyk wrażliwych na czas, zachowania platformy lub twierdzeń dotyczących narzędzi w dowolnym odnośniku sprawdź datę źródła i zważ dowody w następującej kolejności: oficjalna dokumentacja platformy, następnie kontrolowane eksperymenty, następnie duże zbiory danych obserwacyjnych (często badania dostawców), a następnie studia przypadków praktyków. Gdy dokumentacja i dane obserwacyjne są sprzeczne, postępuj zgodnie z dokumentacją dotyczącą uprawnień i kontroli robota i traktuj dane jako hipotezę do przetestowania. Nigdy nie przekształcaj procentu badania w prognozę klienta bez dopasowania wyszukiwarki, branży, języka, rynku i daty.

## Przed rozpoczęciem

**Najpierw sprawdź kontekst marketingowy produktu:**
Jeśli istnieje `.agents/product-marketing.md` (lub `.claude/product-marketing.md` lub starsza nazwa pliku `product-marketing-context.md` w starszych konfiguracjach), przeczytaj go przed zadaniem pytania. Wykorzystaj ten kontekst i poproś jedynie o informacje, które nie zostały jeszcze omówione lub są specyficzne dla tego zadania.

Zbierz ten kontekst (zapytaj, jeśli nie został podany):

### 1. Bieżąca widoczność AI
- Czy wiesz, czy Twoja marka pojawia się dziś w odpowiedziach generowanych przez sztuczną inteligencję?
- Czy sprawdziłeś ChatGPT, Perplexity lub Google AI Overviews pod kątem kluczowych zapytań?
- Jakie zapytania są najważniejsze dla Twojej firmy?

### 2. Treść i domena
- Jakiego rodzaju treści tworzysz? (Blog, dokumentacja, porównania, strony produktów)
- Jaki jest autorytet Twojej domeny / siła tradycyjnego SEO?
- Czy masz istniejące dane strukturalne (znaczniki schematu)?

### 3. Cele
- Być cytowanym jako źródło w odpowiedziach AI?
- Pojawiać się w Google AI Overviews w przypadku konkretnych zapytań?
- Konkurować z konkretnymi markami, które są już cytowane?
- Zoptymalizować istniejącą treść lub stworzyć nową treść zoptymalizowaną pod kątem sztucznej inteligencji?

### 4. Krajobraz konkurencyjny
- Kim są Twoi najwięksi konkurenci w wynikach wyszukiwania AI?
- Czy są cytowani tam, gdzie ciebie nie ma?
- Czy jesteś obecny w Wikipedii lub na stronach z recenzjami?

---

## Jak działa wyszukiwanie AI

### Krajobraz wyszukiwania AI

| Platforma | Jak to działa | Wybór źródła |
|---------|------------|----------------|
| **Google AI Overviews** | Podsumowuje strony o najwyższym rankingu | Silna korelacja z tradycyjnymi rankingami |
| **ChatGPT (z wyszukiwaniem)** | Przeszukuje sieć, cytuje źródła | Korzysta z szerszego zbioru źródeł, nie tylko z czołowych wyników |
| **Perplexity** | Zawsze cytuje źródła z linkami | Preferuje wiarygodne, aktualne i dobrze zorganizowane treści |
| **Gemini** | Asystent AI Google | Wyciągi z indeksu Google + Graf wiedzy |
| **Copilot** | Wyszukiwanie AI oparte na Bing | Indeks Bing + wiarygodne źródła |
| **Claude** | Brave Search (jeśli włączone) | Dane treningowe + wyniki Brave Search |

Aby uzyskać szczegółowe informacje na temat tego, jak każda platforma wybiera źródła i co optymalizować dla każdej platformy, zobacz [references/platform-ranking-factors.md](references/platform-ranking-factors.md).

### Kluczowa różnica w stosunku do tradycyjnego SEO

Tradycyjne SEO pomaga uzyskać wysoką pozycję w rankingu. AI SEO powoduje, że jesteś **cytowany**.

W wyszukiwaniu tradycyjnym musisz znaleźć się na pierwszej stronie wyników. W wyszukiwaniu AI dobrze zorganizowana strona może zostać zacytowana, nawet jeśli znajduje się na 2. lub 3. stronie wyników — systemy AI wybierają źródła na podstawie jakości, struktury i trafności treści, a nie tylko pozycji w rankingu. Silne rankingi organiczne są nadal jednym z najlepszych predyktorów widoczności AI, dlatego traktuj strukturę jako warstwę na SEO, a nie zamiennik.

**Krytyczne statystyki** (zmieniają się; sprawdź ponownie przed przytoczeniem klientowi i nie ufaj statystykom dostawców bez źródła i daty):
- AI Overviews pojawiły się w przypadku ~48% zapytań śledzonych przez BrightEdge (BrightEdge, luty 2026 r.), a CTR na komputerach stacjonarnych na pierwszej pozycji spadł o ~58%, gdy je wyświetlano (Ahrefs, dane z grudnia 2025 r.). Obydwa są specyficzne dla próbki, więc nie prognozuj z ich powodu utraty ruchu w witrynie
- Dodanie statystyk i cytatów zwiększyło widoczność o około 30–40% w oryginalnym badaniu GEO (Aggarwal i in., 2023)

### Oficjalne stanowisko Google a rzeczywistość wieloplatformowa

Ważne jest, aby przeczytać to raz, zanim zrobisz cokolwiek innego.

**Stanowisko Google** ([Przewodnik optymalizacji funkcji AI](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide)):
> „Najlepsze praktyki SEO są nadal aktualne, ponieważ nasze generatywne funkcje sztucznej inteligencji w wyszukiwarce Google są zakorzenione w naszych podstawowych rankingach wyszukiwania i systemach jakości”.

Google wyraźnie mówi:
- **Nie są wymagane żadne specjalne znaczniki ani pliki** w przypadku AI Overviews lub trybu AI
- **Nie dziel treści na części dla sztucznej inteligencji** — pisz dla ludzi, organizuj za pomocą normalnych nagłówków i akapitów
- **Nie pisz osobnych treści dla sztucznej inteligencji** – grozi to naruszeniem zasad spamu związanych z „nadużyciem treści skalowanych”.
- **Pomocna, niezawodna treść skierowana przede wszystkim do ludzi** wygrywa — te same standardy E-E-A-T, co w przypadku zwykłej wyszukiwarki
- **Brak raportów w Search Console związanych ze sztuczną inteligencją** – użyj standardowych wskaźników SEO

**Inne silniki AI (ChatGPT, Claude, Perplexity, Copilot) zachowują się inaczej:**
- Aktywnie nagradzają wyodrębnioną strukturę - fragmenty, często zadawane pytania, tabele porównawcze, bloki definicji
- Analizują `llms.txt`, ustrukturyzowane strony z cenami i pliki do odczytu maszynowego, jeśli są obecne
- Cytują nie tylko strony najwyżej notowane, w tym Reddit, Wikipedię i witryny z recenzjami, w zestawie różniącym się w zależności od silnika

**Co to oznacza dla pracy:**
- Wzorce strukturalne tej umiejętności (bloki odpowiedzi zawierające 40–60 słów, schemat często zadawanych pytań, tabele porównawcze) są istotną pomocą dla **silników AI innych niż Google**. Nie szkodzą też Google — to po prostu zwykła, dobra organizacja treści.
- W szczególności w przypadku Google AI Overviews / trybu AI: optymalizacja pod kątem ludzi i podstawowego wyszukiwania, kropka. Silne E-E-A-T, oryginalne informacje, semantyczny HTML, czysta indeksowalność.
- Dla ChatGPT/Claude/Perplexity: dodaj strukturę łatwą do wyodrębnienia + llms.txt + pliki do odczytu maszynowego. W razie wątpliwości pisz dla ludzi i organizuj dla przejrzystości; co zadowala oba obozy.

### Rozpowszechnianie zapytań (wyszukiwarka Google AI)

Funkcje sztucznej inteligencji Google nie odpowiadają tylko na jedno zapytanie wpisane przez użytkownika — generują **współbieżne, powiązane zapytania** pod maską i pobierają wyniki dla każdego z nich.

Przykład Google: użytkownik pytający „jak naprawić trawniki” wywołuje liczne zapytania dotyczące herbicydów, usuwania bez użycia środków chemicznych, zapobiegania chwastom itp. Sztuczna inteligencja dokonuje syntezy wszystkich zapytań.

**Implikacje:**
- Kierowanie na jedną stronę na słowo kluczowe jest mniej skuteczne. Obejmij **pełny klaster tematyczny**, aby można było go odzyskać również w przypadku wariantów rozproszonych.
- Warianty fraz z długiego ogona mają mniejsze znaczenie niż autorytet tematyczny – systemy sztucznej inteligencji Google rozumieją synonimy i równoważność semantyczną.
- Strona, która wyczerpująco odpowiada na temat nadrzędny (z zawartymi pytaniami dodatkowymi) będzie pobierana częściej niż strony z wąskimi pytaniami.
**Działanie**: planując treść, przeprowadź burzę mózgów na temat 5–10 powiązanych zapytań, na które sztuczna inteligencja prawdopodobnie się rozłoży, i upewnij się, że treść (lub cała witryna) je obejmuje, z jedną stroną odpowiedzialną za każdą rodzinę faktów (macierz w [references/content-patterns.md](references/content-patterns.md)).

ChatGPT również rozgałęzia zapytania — i możesz wyodrębnić jego *dosłowne* zapytania w tle dla swojej niszy za pomocą DevTools (metoda w [references/format-volatility.md](references/format-volatility.md)). Po wersji 5.6, rozwinięcia w ChatGPT odeszły od modyfikatorów „najlepsze/w porównaniu/najlepsze” w kierunku `site:` i „oficjalnych” wyszukiwań — użyj wyodrębnienia, aby zobaczyć, jak wyglądają dzisiaj rozgałęzienia w Twojej kategorii.

---

## Audyt widoczności AI

Przed optymalizacją oceń swoją obecną obecność w wyszukiwarkach AI.

### Krok 1: Sprawdź odpowiedzi AI na swoje kluczowe zapytania

Przetestuj 10–20 najważniejszych zapytań na różnych platformach:

| Zapytanie | Google AI Overviews | ChatGPT | Perplexity | Czy Cię cytują? | Konkurenci cytowani? |
|-------|:--------------------------------:|:-------:|:--------------:|:----------:|:-----------------:|
| [zapytanie 1] | Tak/Nie | Tak/Nie | Tak/Nie | Tak/Nie | [kto] |
| [zapytanie 2] | Tak/Nie | Tak/Nie | Tak/Nie | Tak/Nie | [kto] |

**Typy zapytań do przetestowania**, rozłożone na etapy świadomości kupujących i zapisane w taki sam sposób, w jaki ludzie faktycznie wpisują dane w oknie czatu:
- Świadomość problemów: „Jak mogę [rozwiązać problem z produktem]?”
- Świadomość rozwiązań: „Co to jest [kategoria Twojego produktu]?” / „Najlepsza [kategoria] dla [przypadek użycia]”
- Świadomość produktu: „[Twoja marka] vs [konkurent]” / „Czy [Twoja marka] jest dobra dla [przypadek użycia]?”
- Najbardziej świadomi: „Ceny [Twoja marka]” / „Czy [Twoja marka] integruje się z [narzędziem]?”

Utrzymuj zestaw promptów, które mogłyby zmienić przychody. Cytat z pytania ze słownika („co to jest zysk brutto?”) rzadko prowadzi do jakiejkolwiek sprzedaży. Zarządzaj promptami tak jak słowami kluczowymi: zwiń warianty sformułowań o tej samej intencji w jeden główny prompt, a następnie uruchom każdy z nich kilka razy.

### Krok 2: przeanalizuj wzorce cytowań

Kiedy Twoja konkurencja jest cytowana, a Ty nie, sprawdź:
- **Struktura treści** — Czy ich zawartość jest łatwiejsza do wyodrębnienia?
- **Sygnały autorytetu** — Czy mają więcej cytatów, statystyk, cytatów ekspertów?
- **Świeżość** — Czy ich treść została niedawno zaktualizowana?
- **Znacznik schematu** — Czy mają ustrukturyzowane dane, których Ci brakuje?
- **Obecność stron trzecich** — Czy są one cytowane w Wikipedii, Reddicie, witrynach z recenzjami?

**Przekształć ustalenia w pracę.** Jeśli asystent stwierdzi coś nieprawidłowego lub niejasnego na Twój temat, strona, która powinna to stwierdzić, nie mówi tego wprost; najpierw napraw tę stronę. Jeśli jesteś nieobecny, źródła, na które odpowiedź na prompt, to lista docelowa dla PR, witryn z recenzjami i katalogów.

### Krok 3: Sprawdzanie możliwości wyodrębnienia zawartości

Dla każdej strony priorytetowej sprawdź:

| Sprawdź | Zdany/Nieudany |
|-------|-----------|
| Jasna definicja w pierwszym akapicie? | |
| Samodzielne bloki odpowiedzi (zrozumiałe bez otaczającego kontekstu)? | |
| Statystyki z cytowanymi źródłami? | |
| Tabele porównawcze dla zapytań „[X] vs [Y]”? | |
| Sekcja FAQ z pytaniami w języku naturalnym? | |
| Znacznik schematu (FAQ, instrukcje, artykuł, produkt)? | |
| Uznanie autorstwa eksperta (nazwisko autora, referencje)? | |
| Ostatnio aktualizowane (w ciągu 6 miesięcy)? | |
| Struktura nagłówka pasuje do wzorców zapytań? | |
| Polityka robota AI jest zgodna z celami odkrywania i szkolenia? | |

### Krok 4: Sprawdzanie dostępu do bota AI

Sprawdzaj identyfikatory user-agent botów AI według celu. Tokeny wyszukiwania, pobierania inicjowanego przez użytkownika, uczenia modeli i kontroli produktu nie są zamienne:

- **Wyszukiwanie:** `OAI-SearchBot` (ChatGPT), `PerplexityBot`, `Claude-SearchBot`, `meta-webindexer` (Meta AI) i konwencjonalne roboty wyszukiwania, które dostarczają odpowiedzi
- **Pobieranie inicjowane przez użytkownika:** `ChatGPT-User`, `Claude-User`, `Perplexity-User` i `meta-externalfetcher`; Obsługa dostawców może różnić się od automatycznych robotów indeksujących, dlatego należy sprawdzić aktualną dokumentację
- **Szkolenie potencjalnych modeli:** `GPTBot`, `ClaudeBot` i `meta-externalagent`
- **Kontrola produktów Google:** `Google-Extended` kontroluje niektóre szkolenia Gemini i podstawowe zastosowania treści, które Google już indeksuje; nie ma to wpływu na uwzględnienie ani ranking wyszukiwarki Google
Sprawdź osobno każdą odpowiednią grupę user-agentów i wszelkie reguły WAF lub CDN. Wydawca może zezwolić na wyszukiwanie w trybie wyszukiwania, jednocześnie uniemożliwiając robotom zajmującym się opracowywaniem modeli; nie należy wyciągać wniosku, że zablokowanie robota szkoleniowego koniecznie blokuje cytaty. Zobacz [references/platform-ranking-factors.md](references/platform-ranking-factors.md), aby zapoznać się z pełną konfiguracją pliku robots.txt.

---

## Strategia optymalizacji

### Trzy filary

```
1. Structure (make it extractable)
2. Authority (make it citable)
3. Presence (be where AI looks)
```

### Filar 1: Struktura — umożliwia wyodrębnienie zawartości

Systemy AI wyodrębniają fragmenty, a nie strony. Każde kluczowe twierdzenie powinno działać jako samodzielne stwierdzenie.

**Wzorce bloków treści:**
- **Bloki definicji** dla „Co to jest X?” zapytania
- **Bloki krok po kroku** dla zapytań „Jak X”.
- **Tabele porównawcze** dla zapytań „X i Y”.
- **Bloki za i przeciw** w przypadku zapytań oceniających
- **Bloki FAQ** w przypadku typowych pytań
- **Bloki statystyczne** z cytowanymi źródłami

Szczegółowe szablony dla każdego typu bloku można znaleźć w [references/content-patterns.md](references/content-patterns.md).

**Zasady konstrukcyjne:**
- Prowadź każdą sekcję bezpośrednią odpowiedzią (nie zakopuj jej)
- Zachowaj kluczowe fragmenty odpowiedzi na 40-60 słów (optymalne do wyodrębnienia fragmentów)
- Używaj nagłówków H2/H3 pasujących do sposobu, w jaki ludzie formułują zapytania
- Tabele biją prozę dla porównania treści
- Listy numerowane lepiej przedstawiają procesy niż akapity
- Każdy akapit powinien przekazywać jedną jasną ideę

### Filar 2: Autorytet — zadbaj o to, aby treść była cytowana
Systemy AI preferują źródła, którym mogą zaufać. Buduj wiarygodność cytowań.

**Badanie Princeton GEO** (KDD 2024, badanie w Perplexity.ai) sklasyfikowało 9 metod optymalizacji:

| Metoda | Zwiększenie widoczności | Jak zastosować |
|------------|:-------------------:|-------------|
| **Cytuj źródła** | +40% | Dodaj wiarygodne referencje z linkami |
| **Dodaj statystyki** | +37% | Dołącz konkretne liczby do źródeł |
| **Dodaj cytaty** | +30% | Cytaty ekspertów z imieniem i tytułem |
| **Ton autorytatywny** | +25% | Napisz z wykazaną wiedzą specjalistyczną |
| **Popraw przejrzystość** | +20% | Uprość złożone koncepcje |
| **Terminy techniczne** | +18% | Użyj terminologii specyficznej dla domeny |
| **Unikalne słownictwo** | +15% | Zwiększ różnorodność słów |
| **Optymalizacja płynności** | +15-30% | Popraw czytelność i przepływ |
| ~~Upychanie słów kluczowych~~ | **-10%** | **Aktywnie szkodzi widoczności AI** |

**Najlepsza kombinacja:** Płynność + Statystyki = maksymalne wzmocnienie. Witryny o niskiej pozycji zyskują jeszcze więcej — aż do 115% wzrostu widoczności dzięki cytowaniom.

**Statystyki i dane** (+37-40% wzrost cytowań)
- Podaj konkretne liczby ze źródłami
- Cytuj oryginalne badania, a nie streszczenia badań
- Dodaj daty do wszystkich statystyk
- Dane oryginalne przewyższają dane zagregowane

**Atrybucja ekspercka** (+25-30% wzrost cytowań)
- Imienni autorzy z kwalifikacjami
- Cytaty ekspertów z tytułami i organizacjami
- „Według [Źródła]” formułowanie twierdzeń
- Biografia autora posiadająca odpowiednią wiedzę specjalistyczną

**Sygnały świeżości**
- „Ostatnia aktualizacja: [data]” wyświetlana w widocznym miejscu
- Regularne odświeżanie treści (minimum kwartalne w przypadku tematów konkurencyjnych)
- Referencje z bieżącego roku i najnowsze statystyki
- Usuń lub zaktualizuj nieaktualne informacje

**Wyrównanie E-E-A-T**
- Pokazano doświadczenie z pierwszej ręki
- Konkretne, szczegółowe informacje (nie ogólne)
- Przejrzyste źródła i metodologia
- Wyraźna wiedza autora na dany temat

### Filar 3: Obecność — bądź tam, gdzie patrzy AI

Systemy AI cytują Twoją własną witrynę i miejsca, które mówią o Tobie, w proporcjach różniących się w zależności od silnika i kategorii. W jednym dużym zbiorze danych witryny firmowe uzyskały około 57% cytowań (ChatGPT 47%, Gemini 69%; Profound, lipiec 2026 r.), natomiast rekomendacje z krótkiej listy opierają się na konsensusie stron trzecich. Przed wybraniem kanałów zmierz liczbę cytowań w swojej kategorii; zobacz [references/citations-vs-recommendations.md](references/citations-vs-recommendations.md).

**Powierzchnie innych firm do pokrycia:**
- Wikipedia (7,8% cytowań ChatGPT w danych Profound z sierpnia 2024 r. – czerwca 2025 r.)
- Reddit (1,8% tych samych danych, następnie prawie usunięty z ChatGPT do zmian w pobieraniu z sierpnia 2026 r.; nadal pobrany gdzie indziej; zobacz sekcję dotyczącą zmienności w [references/agent-readiness.md](references/agent-readiness.md))
- Publikacje branżowe i wpisy gościnne
- LinkedIn — jedna z najczęściej cytowanych domen w przypadku zapytań zawodowych, ale to, która powierzchnia zostanie cytowana, zależy od silnika (ChatGPT preferuje teraz posty nad artykułami; Gemini prawie nie cytuje LinkedIn). Załaduj docelową frazę od początku, ponieważ pierwsze słowa posta stają się jego adresem URL. Zobacz [references/linkedin-ai-citations.md](references/linkedin-ai-citations.md)
- Witryny z recenzjami (G2, Capterra, TrustRadius dla B2B SaaS)
- YouTube (często cytowany w przeglądach Google AI)
- Podcasty (odcinki są transkrybowane, publikowane są notatki — oba są indeksowane i cytowane)
- Odpowiedzi w Quora

**Działania:**
- Upewnij się, że Twoja strona w Wikipedii jest dokładna i aktualna
- Uczestniczyj autentycznie w społecznościach Reddit — ale jako jedna powierzchnia w portfolio, nigdy jako cała strategia (zestawy cytatów zmieniają się z dnia na dzień wraz z aktualizacjami wyszukiwania)
- Wyróżnij się w podsumowaniach branżowych i artykułach porównawczych
- Spraw, aby każdy profil strony trzeciej (G2, Capterra, Gartner, Crunchbase, LinkedIn) opisywał Cię w tym samym segmencie i pozycjonowaniu, co Twoja strona Informacje; modele szukają konsensusu. Informacje na temat repozycjonowania, fuzji i fraz głównych można znaleźć w [references/positioning-and-consensus.md](references/positioning-and-consensus.md)
- Twórz treści YouTube dla kluczowych zapytań z instrukcjami — modele nie oglądają filmu, czytają otaczającą go warstwę tekstową; zobacz [references/youtube-ai-citations.md](references/youtube-ai-citations.md), aby zapoznać się z pełną anatomią (transkrypcja, napisy, rozdziały, opis, przypięty komentarz)
- Występuj gościnnie w podcastach w swojej kategorii (przygotuj się, korzystając z przepisu podcast-guest-prep w umiejętności public-relations)
- Odpowiadaj szczegółowo na istotne pytania Quora

### Pliki do odczytu maszynowego dla agentów AI

> **Stanowisko Google**: nie jest wymagane w przypadku AI Overviews ani trybu AI. Ich przewodnik wyraźnie mówi, że nie potrzebujesz nowych znaczników, plików AI ani Markdown, aby pojawić się w generatywnym wyszukiwaniu AI.
>
> **Po co je w ogóle włączać**: silniki sztucznej inteligencji inne niż Google (ChatGPT, Claude, Perplexity) i autonomiczni agenci zakupowi nagradzają strukturę, którą można wyodrębnić. Poniższe pliki pomagają w obsłudze tych silników, nie szkodząc Google.

Agenci AI nie tylko odpowiadają na pytania — oni stają się kupującymi. Kiedy agent AI ocenia narzędzia w imieniu użytkownika, potrzebuje ustrukturyzowanych, możliwych do analizy informacji. Jeśli Twoje ceny są zablokowane na stronie renderowanej w JavaScript lub na ścianie „kontaktowej sprzedaży”, agenci pominą Cię i polecą konkurencję, której informacje mogą faktycznie przeczytać.
**Najpierw przeprowadź audyt tej warstwy**: [references/agent-readiness.md](references/agent-readiness.md) — lista kontrolna dostępu/odkrywania/analizowalności, bezpłatne narzędzia scoringowe (`npx is-agentic`, moduł sprawdzania Frase), negocjacja treści Markdown + nagłówki `Link`, `llms-full.txt` i nowa warstwa agenta *actionable* (WebMCP).

Dodaj te pliki do odczytu maszynowego do katalogu głównego swojej witryny:

**`/pricing.md` lub `/pricing.txt`** — Ustrukturyzowane dane cenowe dla agentów AI

```markdown
# Pricing — [Your Product Name]

## Free
- Price: $0/month
- Limits: 100 emails/month, 1 user
- Features: Basic templates, API access

## Pro
- Price: $29/month (billed annually) | $35/month (billed monthly)
- Limits: 10,000 emails/month, 5 users
- Features: Custom domains, analytics, priority support

## Enterprise
- Price: Custom — contact sales@example.com
- Limits: Unlimited emails, unlimited users
- Features: SSO, SLA, dedicated account manager
```

**Dlaczego to ma teraz znaczenie:**
- Agenci AI coraz częściej porównują produkty programowo, zanim człowiek odwiedzi Twoją witrynę
- Nieprzejrzyste ceny są filtrowane ze ścieżek zakupowych za pośrednictwem sztucznej inteligencji
- Prosty plik Markdown można w prosty sposób przeanalizować w dowolnym LLM - bez renderowania, bez JavaScriptu, bez ścian logowania
- Ta sama zasada co `robots.txt` (dla robotów indeksujących), `llms.txt` (dla kontekstu AI) i `AGENTS.md` (dla możliwości agenta)

**Najlepsze praktyki:**
- Używaj spójnych jednostek (miesięczne vs. roczne, za stanowisko vs. opłata stała)
- Uwzględnij konkretne limity i progi, a nie tylko nazwy funkcji
- Wypisz, co obejmuje każdy poziom, a nie tylko to, co jest inne
- Aktualizuj na bieżąco — nieaktualne ceny są gorsze niż brak pliku
- Link do niego w mapie witryny i na głównej stronie z cenami

**`/llms.txt`** — plik kontekstowy dla systemów AI (patrz [llmstxt.org](https://llmstxt.org))

Jeśli jeszcze go nie masz, dodaj `llms.txt`, który zapewni systemom AI szybki przegląd tego, co robi Twój produkt, dla kogo jest przeznaczony, oraz linki do kluczowych stron (w tym cen).
**`/okf/` — pakiet Open Knowledge Format (wspierany przez Google, wersja 0.1)**

Google [wprowadził OKF](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing) w czerwcu 2026 r. — specyfikację Markdown do reprezentowania zawartości witryny jako katalogu połączonych plików z nagłówkiem YAML frontmatter, czytelnym dla agenta bez skrobania. Stworzony głównie dla metadanych katalogu zespołu danych; Zmiana przeznaczenia witryny czytelnej dla agentów została spopularyzowana przez Suganthana Mohanadasana. Dzisiaj nie potwierdzono żadnego sygnału rankingowego wyszukiwania AI — traktuj to jako rejestrację w warstwie protokołu, jak wczesną wersję schema.org. **Pełny opis, ścieżki implementacji (darmowy generator, wtyczka WordPress, ręczne), wskazówki dotyczące hostingu i kiedy pominąć, znajdziesz w [references/okf.md](references/okf.md).**

### Oznaczenia schematu dla sztucznej inteligencji

Uporządkowane dane pomagają systemom AI zrozumieć Twoje treści. Kluczowe schematy:

| Typ zawartości | Schemat | Dlaczego to pomaga |
|------------|------------|------------|
| Artykuły/posty na blogu | `Article`, `BlogPosting` | Autor, data, identyfikacja tematu |
| Treść poradników | `HowTo` | Ekstrakcja kroków dla zapytań procesowych |
| Często zadawane pytania | `FAQPage` | Bezpośrednia ekstrakcja pytań i odpowiedzi |
| Produkty | `Product` | Ceny, funkcje, recenzje |
| Porównania | `ItemList` | Ustrukturyzowane dane porównawcze |
| Recenzje | `Review`, `AggregateRating` | Sygnały zaufania |
| Organizacja | `Organization` | Rozpoznanie podmiotu |

Żadne dobrze udokumentowane badanie nie wyodrębnia wpływu znaczników schema na wzrost liczby cytowań AI, dlatego traktuj schemat jako kontekst, który pomaga wyszukiwarkom analizować Twoje strony i nie oczekuj od niego stałego wzrostu. **Uwaga Google**: dane strukturalne „nie są wymagane do generatywnego wyszukiwania AI”, ale są zalecane w przypadku ogólnej strategii SEO. Do implementacji użyj umiejętności **schema**.

---

## Doświadczenia agentów

Oprócz wyszukiwarek AI podsumowujących treść, autonomiczni agenci zaczynają bezpośrednio uzyskiwać dostęp do witryn — klikając, czytając, porównując, a nawet dokonując zakupów w imieniu użytkowników. Przewodnik Google oznacza tę kategorię jako nową kategorię, którą należy zaplanować.

**Jak agenci uzyskują dostęp do Twojej witryny:**
- **Renderowanie wizualne** — wykonują zrzut ekranu/czytają stronę tak, jak zrobiłby to użytkownik
- **Inspekcja DOM** — analizują strukturę HTML strony
- **Drzewo dostępności** — opierają się na tych samych technologiach wspomagających informacje semantyczne (etykiety, role, punkty orientacyjne, nagłówki)

**Co robić:**
- **Renderuj znaczącą treść bez ciężkiej gimnastyki JS** — jeśli strona jest pusta, dopóki nie załadują się 4 frameworki, agenci zobaczą puste
- **Semantyczny HTML** — użyj `<main>`, `<nav>`, `<article>`, `<button>`, odpowiedniej hierarchii nagłówków, tekstu `alt` na obrazach
- **Wyczyść drzewo dostępności** – każdy element interaktywny oznaczony; ARIA użyta poprawnie (lub wcale, jeśli wystarczy natywny HTML)
- **Stabilne selektory / przewidywalne układy** — agenci mają problemy z witrynami, które ponownie renderują każdą interakcję
- **Widoczne ceny, specyfikacje, dane kontaktowe** — wszystko, czego agent będzie potrzebował, aby wydać rekomendację zakupu, powinno znajdować się na publicznej, możliwej do indeksowania stronie (w tym miejscu pomocny jest `/pricing.md` i podobne pliki). Datuj zmieniające się fakty („4,7 na G2 od października 2026 r.”), aby agent mógł ocenić świeżość
- **Dowód jako tekst** — referencje, oceny i nazwane logo klientów w kodzie HTML jako tekst, a nie dodawany do obrazów lub wstrzykiwany przez skrypt widżetu. Jeśli nie możesz wybrać go myszą, agent może go nie przeczytać

**Nowe — uniwersalny protokół handlowy (UCP):**
Google wspomina UCP jako o nadchodzącym protokole, który zapewni agentom ustandaryzowane elementy interakcji handlowych (odkrywanie katalogu, ustalanie cen, realizacja transakcji). Uważaj na adopcję; na razie powyższe zalecenia strukturalne są prekursorem.

W szczególności w przypadku firm e-commerce i lokalnych Google podkreśla:
- **Kanały Merchant Center** + **Profil Firmy w Google** zapewniający widoczność produktów/usług w wyszukiwarce AI
- **Agent biznesowy** ds. konwersacyjnego kontaktu z klientami (w stosownych przypadkach)

---

## Typy treści, które są najczęściej cytowane
Nie wszystkie treści nadają się jednakowo do cytowania, a mieszanka formatów jest **zmienna**. W długotrwałym okresie bazowym artykuły porównawcze (~33%) i listy (~10%) znajdowały się wśród formatów generujących najwięcej cytowań, ale **ChatGPT 5.6 (sierpień 2026) zdegradowało wykorzystywane formaty: cytowania list spadły o -50,5%, a cytowania stron porównawczych -32,1%, podczas gdy `site:` i „oficjalne” pobieranie wzrosły** – przesunięcie w stronę źródeł głównych i stron własnych. Strategia formatowania jest teraz dostosowana do poszczególnych platform (porównania nadal działają w Google AIO/Gemini/Perplexity). Zobacz [references/format-volatility.md](references/format-volatility.md), aby zapoznać się z danymi zmian, tabelą formatów dla poszczególnych platform, numerami cytowań LinkedIn i diagnostyką wyodrębniania rozgałęzień ChatGPT.

**Zawsze zwycięzcy na różnych platformach:** oryginalne badania i dane, ostateczne przewodniki i własne „oficjalne” strony — produkty, dokumenty, ceny — z wyodrębnialną strukturą.

**Słabsze posty:** ogólne posty bez struktury, treści cienkie lub zamknięte lub wyłącznie w formacie PDF oraz wszystko, co nie jest datowane i nie zawiera informacji o autorze.
**Cytowanie ≠ rekomendacja.** Cytowanie oznacza, że ​​warto było zapoznać się z treścią; uzyskanie *rekomendacji* — na faktycznej krótkiej liście kupującego — zależy od konsensusu w całej sieci (recenzje, fora, analitycy, prasa) i jest w dużej mierze niezależne od Twoich własnych treści. Autopromocyjne listy „najlepszych [kategorii]” mogą nawet przynieść odwrotny skutek dla wschodzących marek: w jednym badaniu B2B obejmującym 100 zapytań 69% cytowań z AI Overviews uzyskanych dzięki listom autopromocyjnym pochodziło z odpowiedzi, które polecały konkurentów zamiast marki wydawniczej. Zobacz [references/citations-vs-recommendations.md](references/citations-vs-recommendations.md), aby zapoznać się z drabiną widoczności (pobraną → cytowaną → wspomnianą → polecaną), strategią przewodnika kupującego zależną od etapu, tym, co zdobywa rekomendacje i martwym punktem atrybucji.

---

## Monitorowanie widoczności AI

### Co śledzić

| Wskaźnik | Co to mierzy | Jak sprawdzić |
|------------|----------------------|------------|
| Obecność AI Overviews | Czy w przypadku zapytań pojawiają się AI Overviews? | Sprawdzanie ręczne lub Semrush/Ahrefs |
| Wskaźnik cytowań marki | Jak często jesteś cytowany w odpowiedziach AI | Narzędzia widoczności AI (patrz poniżej) |
| Udział głosu AI | Twoje cytaty kontra konkurencja | Peec AI, Otterly, ZipTie, Omnia |
| Nastroje cytowań | Jak AI opisuje Twoją markę | Ręczny przegląd + narzędzia monitorujące |
| Wskaźnik rekomendacji | Niezależnie od tego, czy jesteś na krótkiej liście, a nie tylko cytowany (zobacz [citations-vs-recommendations.md](references/citations-vs-recommendations.md)) | Śledzenie promptów + kontekst wzmianek |
| Atrybucja | Które strony są cytowane i jaki dalszy wpływ ma kontakt z odpowiedziami AI w dalszej części | Polecenia AI oraz opóźnione wizyty markowe i bezpośrednie ([ai-attribution.md](references/ai-attribution.md)) |

### Narzędzia do monitorowania widoczności AI

| Narzędzie | Zasięg | Najlepsze dla |
|------|----------|---------|
| **Otterly AI** | ChatGPT, Perplexity, Google AI Overviews | Udział śledzenia głosu AI |
| **Peec AI** | ChatGPT, Gemini, Perplexity, Claude, Copilot+ | Monitorowanie wieloplatformowe na dużą skalę |
| **ZipTie** | Google AI Overviews, ChatGPT, Perplexity | Wzmianka o marce + śledzenie nastrojów |
| **LLMrefs** | ChatGPT, Perplexity, AI Overviews, Gemini | Słowo kluczowe SEO → Mapowanie widoczności AI |
| **Profound, Ahrefs Brand Radar, Semrush** | Główni asystenci i powierzchnie Google AI | Większe programy: cytowane źródła, tekst odpowiedzi, popyt wyrażany w promptach (badania Profound są cytowane w źródłach jako badania dostawców) |
| **Omnia** | Tryb Google AI, przegląd Google AI, ChatGPT, Perplexity, Gemini, Claude, Copilot | Monitorowanie widoczności AI |

### Monitoring DIY (bez narzędzi)

Miesięczna kontrola ręczna:
1. Wybierz 20 najpopularniejszych zapytań
2. Uruchom każdy z nich przez ChatGPT, Perplexity i Google
3. Zapis: Czy jesteś cytowany? Kto jest? Jaka strona? Zapisz w arkuszu kalkulacyjnym i śledź miesiąc po miesiącu

Odpowiedzi AI są **niedeterministyczne** – jeden przebieg to anegdota, a nie pomiar. Uruchom każde zapytanie 3–5 razy na platformę i śledź *odsetek* wzmianek wraz z wielkością próby („cytowano 3/5, n=5”), porównując odsetki w czasie, a nie pojedyncze przebiegi. Pełna lista kontrolna rygorystyczności w [references/format-volatility.md](references/format-volatility.md).

### Oczekiwania Search Console

Przewodnik Google jest jednoznaczny: **w Search Console nie ma raportów dotyczących sztucznej inteligencji**. AI Overviews i tryb AI wykorzystują podstawowy ranking wyszukiwania, więc standardowe raporty Search Console (wydajność, zasięg, podstawowe wskaźniki internetowe) nadal są tym, za pomocą czego mierzysz dla Google. Powyższe narzędzia innych firm to jedyny sposób, aby zobaczyć zachowanie cytowań AI na wielu platformach.

---

## Czego NIE robić

Przewodnik Google wyraźnie to podkreśla – szkodzą zarówno tradycyjnym funkcjom wyszukiwania, jak i sztucznej inteligencji.

1. **Napisz osobną treść „dla AI”**. Te same treści powinny służyć ludziom i sztucznej inteligencji. Pisanie wariantów ukierunkowanych na systemy AI stwarza ryzyko naruszenia **zasad dotyczących spamu związanego z wykorzystywaniem skalowanych treści** – słowami Google.
2. **Podziel strony na fragmenty będące przynętą AI**. Przewodnik Google jest bezpośredni: * „Nie dziel treści na małe kawałki, aby sztuczna inteligencja mogła ją lepiej zrozumieć”. * Używaj normalnej struktury akapitów i nagłówków.
3. **Generuj na dużą skalę w celu manipulacji rankingiem**. Treści generowane przez sztuczną inteligencję są w porządku, *jeśli* spełniają zasady Search Essentials i zasady dotyczące spamu. Masowo produkowane cienkie odmiany tego nie robią.
4. **Podążaj za nieautentycznymi wzmiankami**. Nie twórz cytatów, nie wymyślaj nagród, nie prowadź „niezależnych” witryn z recenzjami, które posiadasz, ani nie masowo spamuj Reddit/Wikipedii w celu uwidocznienia sztucznej inteligencji. Fałszywe lub mylące recenzje mogą również złamać zasadę FTC dotyczącą recenzji za rok 2024. Tylko prawdziwe uczestnictwo.
5. **Traktuj każdy identyfikator user-agent AI jako tę samą kontrolę**. `GPTBot`, `ClaudeBot` i `Google-Extended` mają inne udokumentowane przeznaczenie niż `OAI-SearchBot`, `Claude-SearchBot` i `PerplexityBot`. Zdecyduj osobno o wykrywaniu, wyszukiwaniu użytkowników, trenowaniu i opieraniu odpowiedzi na źródłach (grounding).
6. **Ukryj główną treść za JS, który się nie renderuje**. Zarówno główni agenci wyszukiwania, jak i agenci AI muszą zobaczyć Twoje treści; Renderowanie wyłącznie w JS powoduje utratę obu odbiorców.
7. **Pomiń podstawy E-E-A-T**. Tożsamość autora, doświadczenie z pierwszej ręki, sygnały specjalistyczne, przejrzyste źródła informacji – przewodnik Google w dużej mierze opiera się na nich w przypadku funkcji sztucznej inteligencji.

---

## SEO AI według typu treści

Wskazówki taktyczne dotyczące stron produktów SaaS, treści blogów, stron porównawczych/alternatywnych, dokumentacji i rozwiązań lokalnych/ecom (nacisk Google na Merchant Center + profil firmy) znajdziesz w [references/content-types.md](references/content-types.md).

---

## Typowe błędy
- **Całkowite ignorowanie wyszukiwania AI** – AI Overviews pojawiają się w mniej więcej połowie śledzonych zapytań w wielu branżach (BrightEdge, luty 2026 r.), a wykorzystanie asystentów stale rośnie
- **Traktowanie SEO AI oddzielnie od SEO** — Dobre, tradycyjne SEO to podstawa; AI SEO dodaje strukturę i autorytet na górze
- **Pisanie dla sztucznej inteligencji, a nie dla ludzi** — Jeśli treść brzmi tak, jakby została napisana w celu zagrania w algorytm, nie będzie cytowana ani konwertowana
- **Brak sygnałów aktualności** — Niedatowane treści tracą na wartości, ponieważ systemy AI przywiązują dużą wagę do aktualności. Pokaż, kiedy zawartość była ostatnio aktualizowana
- **Bramowanie całej zawartości** — sztuczna inteligencja nie ma dostępu do treści chronionych. Trzymaj najbardziej wiarygodne treści otwarte
- **Ignorowanie obecności osób trzecich** — Rekomendacje na krótkiej liście opierają się na opiniach, forach i prasie, które mówią o Tobie, nawet jeśli Twoja witryna zdobywa najwięcej cytowań
- **Brak danych strukturalnych** — znaczniki schematu zapewniają systemom AI uporządkowany kontekst dotyczący Twoich treści
- **Upychanie słów kluczowych** — W przeciwieństwie do tradycyjnego SEO, gdzie jest po prostu nieskuteczne, upychanie słów kluczowych aktywnie zmniejsza widoczność sztucznej inteligencji o 10% (badanie Princeton GEO)
- **Ukrywanie cen za „skontaktuj się z działem sprzedaży” lub stronami renderowanymi w JS** — agenci AI oceniający Twój produkt w imieniu kupujących nie mogą analizować tego, czego nie mogą przeczytać. Dodaj plik `/pricing.md`
- **Blokowanie robotów wykrywających bez sprawdzania ich przeznaczenia** — Ograniczanie `OAI-SearchBot`, `PerplexityBot` lub `Claude-SearchBot` może zmniejszyć widoczność wyszukiwania; kontrole szkoleniowe są oddzielne
- **Ogólna treść bez danych** — „Jesteśmy najlepsi” nie będzie cytowane. „Nasi klienci widzą 3-krotną poprawę w [metryce]” będzie
- **Zapominanie o monitorowaniu** — Nie możesz ulepszyć tego, czego nie mierzysz. Sprawdzaj widoczność AI przynajmniej raz w miesiącu

---

## Integracja narzędzi

Aby zapoznać się z implementacją, zobacz [rejestr narzędzi](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/REGISTRY.md).

| Narzędzie | Użyj dla |
|------|-------------|
| `semrush` | Śledzenie AI Overviews, badanie słów kluczowych, analiza luk w treści |
| `ahrefs` | Analiza linków zwrotnych, eksplorator treści, dane przeglądowe AI |
| `gsc` | Dane dotyczące wydajności Search Console, śledzenie zapytań |
| `ga4` | Ruch polecający ze źródeł AI |

---

## Powiązane umiejętności

- **seo-audit**: Do tradycyjnych audytów technicznych i SEO na stronie; **link-building** w celu zdobywania linków i wzmianek na zewnętrznych stronach cytowanych przez silniki AI
- **schema**: do wdrażania uporządkowanych danych, które pomagają sztucznej inteligencji zrozumieć Twoje treści
- **content-strategy**: do planowania treści, które chcesz utworzyć
- **competitors**: Do tworzenia cytowanych stron porównawczych
- **programmatic-seo**: Do tworzenia stron SEO na dużą skalę
- **copywriting**: do pisania treści, które są czytelne dla człowieka i możliwe do wyodrębnienia przez sztuczną inteligencję
- **lead-magnets**: Do pakowania posiadanego kursu lub biblioteki treści jako umiejętności agenta, którą można zainstalować (inna niż widoczność AI w witrynach publicznych)