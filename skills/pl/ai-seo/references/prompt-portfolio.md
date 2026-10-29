# Projektowanie zestawu promptów

To, które monity śledzisz, decyduje o tym, co oznaczają Twoje liczby widoczności AI. Portfolio wypełnione pytaniami ze słownika zapewni dobrą widoczność, podczas gdy stracisz każdą krótką listę. W tym podręczniku opisano, jak wybierać prompty, grupować je, wersjonować i jak często je uruchamiać, łącznie z wieloetapowymi rozmowami zakupowymi, które pomijane są w przypadku pojedynczych promptów.

## Zacznij od pytania dotyczącego pomiaru

Zanim wybierzesz pojedynczy monit, zapisz decyzję, którą mają wesprzeć wyniki. „Czy znajdujemy się na krótkiej liście nabywców średniej wielkości w [kategorii] w USA?” potrzebuje innego portfolio niż „Czy przepisanie naszych dokumentów naprawiło sposób, w jaki Claude opisuje nasze limity API?”

## Buduj na podstawie rzeczywistego popytu

Używaj słów faktycznie wpisywanych przez kupujących. W kolejności preferencji:

1. Prompty zgłaszane bezpośrednio przez kupujących (kontynuacja „O co pytałeś sztuczną inteligencję?” w polu „Jak-słyszałeś”, notatki z rozmów telefonicznych)
2. Dane o popycie na prompty z narzędzia śledzącego, jeśli je masz
3. Badania klientów, zgłoszenia do pomocy technicznej, wątki społecznościowe i zastrzeżenia dotyczące sprzedaży
4. Twoje wyszukiwane hasła przepisane tak, jak ktoś by je sformułował asystentowi

Nie przekształcaj mechanicznie listy słów kluczowych w pytania. „crm small business” i „Z jakiego CRM powinna korzystać 5-osobowa agencja, jeśli mieszkamy w Gmailu?” poszukaj różnych źródeł.

## Uwzględnij rodziny intencji

| Rodzina | Przykładowy kształt |
|---|---|
| Odkrycie kategorii | „Z jakich narzędzi korzystają zespoły w przypadku [pracy]?” |
| Badania problemów i rozwiązań | „Jak zatrzymać [problem]?” |
| Porównania i alternatywy | „[Ty] kontra [konkurent]”, „alternatywy dla [konkurenta]” |
| Rekomendacje i „najlepsze dla” | „Najlepsza [kategoria] dla [segmentu lub ograniczenia]” |
| Zaufanie, ryzyko i walidacja | „Czy [ty] jesteś wiarygodny?” „Czy [ty] masz SOC 2?” |
| Cena, dostępność, kompatybilność, limity | „[Ty] wycena”, „Czy [ty] pracujesz z [narzędziem]?” |
| Wdrożenie i rozwiązywanie problemów | „Jak skonfigurować [ciebie] z [stosem]?” |
| Lokalne, handlowe lub regulowane | Tylko wtedy, gdy dotyczą one działalności |

Zważ rodziny według wartości biznesowej. Cytat z pytaniem dotyczącym definicji rzadko coś sprzedaje; zobacz filtr przychodów na etapie audytu SKILL.md.

## Trzy kohorty

| Kohorta | Cel | Zasady |
|---|---|---|
| **Stabilny rdzeń** | Pomiar trendu | Zmiany są rzadkie i tylko poprzez wersjonowanie. To jest zestaw, o którym piszesz. |
| **Odkrywcze** | Pojawiający się popyt, nowe segmenty, nowi konkurenci | Obraca się swobodnie. Przenoś prompty do rdzenia, gdy okażą się wartościowe. |
| **Kontrola diagnostyczna** | Znane wyniki, które mówią, czy pomiar dryfował | Dołącz prompty, w których powinieneś się zawsze pojawiać (nazwa Twojej marki) i w których nigdy się nie pojawiać (kategoria niepowiązana). Jeśli się poruszą, oznacza to zmianę narzędzia lub silnika i Twoja praca nie ma z tym nic wspólnego. |

Zachowaj wyszukiwarki, rynki, języki i osoby jako osobne konfiguracje. Uruchomienie ChatGPT w języku angielskim w USA i uruchomienie Gemini w Niemczech to różne pomiary; zobacz [multilingual-and-commerce.md](multilingual-and-commerce.md).

Dodawaj warianty parafraz tylko tam, gdzie chcesz zmierzyć wrażliwość sformułowań. W przeciwnym razie zwiń warianty tego samego zamiaru w jeden podstawowy monit.

## Jak często uruchamiać

Dwa reżimy, w zależności od wielkości portfela:

- **Szerokie portfolio (setki promptów):** zazwyczaj wystarczy raz dziennie. Porównując przez Profound 753 prompty na siedmiu platformach w ciągu dwóch tygodni, szacunki widoczności wyświetlanej raz dziennie mieściły się w granicach około dwóch punktów procentowych w przypadku wyświetlania każdego promptu dziesięć razy dziennie (Profound, lipiec 2026 r.). Dodatkowe uruchomienia poprawiały dokładność pomiaru udziału w cytowaniach bardziej niż samej widoczności, ale nie mogły wyeliminować codziennego dryfowania platformy. Skład był ważniejszy niż częstotliwość.
- **Mały zestaw (10–20 promptów w ramach audytu typu „zrób to sam”), krótkie eksperymenty lub precyzyjny pomiar udziału w cytowaniach:** uruchom każdy monit kilka razy (3–5 na platformę) i zgłoś częstotliwość wraz z wielkością próbki, jak opisano w sekcji monitorowania w SKILL.md. Przy niewielkiej liczbie promptów jedno uruchomienie na monit powoduje głównie hałas.

Profound sprzedaje narzędzia do śledzenia widoczności AI, dlatego traktuj te liczby jako badanie dostawcy przeprowadzone w jednym układzie pomiarowym. Inne trackery to Ahrefs Brand Radar, Semrush, Peec AI, Otterly i ZipTie; sprawdź, co każdy z nich obejmuje próbą, zanim porównasz ich liczby.
## Wersjonuj portfolio

- Nadaj portfelowi numer wersji i rejestruj każde dodanie, usunięcie i zmianę wagi, podając datę i przyczynę.
- Nigdy nie porównuj dwóch okresów, w których korzystano z zasadniczo różnych portfeli. Przelicz ponownie, korzystając z promptów wspólnych dla obu okresów.
- Zamroź rdzeń podczas eksperymentu.

## Wieloturowe podróże zakupowe

Kupujący nie poprzestają na jednym prompcie. Rozmowy komercyjne w ChatGPT rzadziej kończyły się po jednej turze niż rozmowy informacyjne, a intencje komercyjne wzrosły z 13,9% do 19,2% próbowanych rozmów w ciągu roku (Profound, sierpień 2026; szacunki próbkowane i modelowane). Wcześniejsze badanie Profound wykazało, że cytaty z Internetu koncentrują się na pierwszych etapach rozmowy badawczej (Profound, dane z IV kwartału 2025 r.). Zatem prompt otwierający decyduje, które źródła zostaną pobrane, a późniejsze tury decydują, kto pozostanie na krótkiej liście.

Zaplanuj podróż według etapów, a następnie napisz dla każdego z nich jedną prompt otwierający i dwa lub trzy realistyczne kontynuacje:

| Etap | Typowa kontynuacja |
|---|---|
| Zdefiniuj potrzebę | „Na co powinienem zwrócić uwagę w [kategorii]?” |
| Stwórz krótką listę | „Które z nich działają w przypadku [ograniczenia]?” |
| Porównaj | „Jak wypada [A] w porównaniu z [B] według [kryterium]?” |
| Sprawdź | „Na co użytkownicy narzekają w przypadku [A]?” |
| Wyjaśnij ryzyko | „Czy mogę przeprowadzić migrację z [obecnego dostawcy] bez utraty [danych]?” |
| Wybierz | „Co byś wybrał dla zespołu takiego jak mój?” |

Przeprowadź rozmowę w jednej sesji i zapisuj co turę, czy ktoś o Tobie wspomniał, polecił, zacytował czy odrzucił, a także otoczenie wzmianki. Turą, w której wypadasz z krótkiej listy, jest luka w treści lub dowodach, którą należy naprawić. Śledź osobno wzmianki, umieszczanie na krótkiej liście, sposób przedstawienia i cytaty; zobacz drabinę widoczności w [citations-vs-recommendations.md](citations-vs-recommendations.md).

Najpierw zdecyduj, czy rozmowy dotyczące zakupu AI w ogóle mają znaczenie dla tej kategorii. W tym samym badaniu stwierdzono, że udział osób o zamiarach komercyjnych różnił się około dziesięciokrotnie w zależności od branży.

---

*Pochodzenie frameworka: projektowanie kohort, reżimy rytmu i mapa podróży zaadaptowana (przekształcona i zrestrukturyzowana) na podstawie umiejętności ai-prompt-portfolio-builder i commercial-ai-journey-mapper firmy Profound na licencji MIT oraz badań, które cytują (lipiec i sierpień 2026 r.), przypisane.*