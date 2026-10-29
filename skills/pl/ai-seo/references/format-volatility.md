# Zmienność formatu — które formaty treści cytuje AI (i jak szybko to się zmienia)

Zmienność *źródeł cytowań* (Reddit usunięty z dnia na dzień, Gemini faworyzuje własne witryny) jest opisana w [agent-readiness.md](agent-readiness.md). To odniesienie obejmuje drugą oś zmienności: *formaty cytowanych treści* — typy stron pobierane i cytowane przez silniki AI oraz dowody z sierpnia 2026 r., że często wykorzystywane formaty są degradowane.

Przeczytaj to, zanim polecisz strony porównawcze, listy lub „najlepszą treść X” pod kątem widoczności AI. Porada uległa istotnej zmianie wraz z wersją ChatGPT 5.6.

## Zmiana formatu ChatGPT 5.6 (sierpień 2026 r.)

Dane z Peec AI (udostępnione przez Tomka Rudzkiego za pośrednictwem Lily Ray, sierpień 2026), porównujące zachowanie pobierania ChatGPT przed i po uruchomieniu wersji 5.6:

**Zapytania typu fan-out** — modyfikatory, które odnotowały największy spadek udziału w wyszukiwaniach w tle przez ChatGPT:

- „vs”
- „porównanie”
- „top”
- „najlepszy”
- "recenzje"

Jednocześnie: wzrost wyszukiwań `site:` i modyfikatorów takich jak **„oficjalne”**.

**Cytowania według typu strony** — udział w całkowitej liczbie cytowań ChatGPT:

| Typ strony | Przed 5.6 | Po 5.6 | Zmiana |
|---|---:|---:|---:|
| Listy („Top 10 X”, „8 najlepszych Y”) | 15,77% | 7,80% | **−50,5%** |
| Strony porównawcze („X kontra Y”, alternatywy) | 9,08% | 6,17% | **−32,1%** |

Interpretacja (Lily Ray i pasuje do danych rozproszonych): są to dokładnie dwa formaty, które firmy skalowały pod kątem GEO w ciągu ostatnich 18 miesięcy, a pobieranie skorygowane przez ChatGPT w celu ograniczenia spamu. Wzrost `site:`/„oficjalny” wskazuje ten sam kierunek — **w stronę głównych źródeł i posiadanych domen, z dala od formatów agregatorów**.

## Co to zmienia (a czego nie)

**NIE oznacza to „zaprzestania tworzenia stron porównawczych”.** Porównanie i najlepsze treści nadal:

- Konwertuje ludzkich nabywców (jego pierwotna praca)
- Jest cytowany przez Google AI Overviews (które śledzą podstawowe rankingi, a nie wyszukiwanie ChatGPT)
- Karmi Gemini i Perplexity, które nie wykazały tej samej degradacji
- Odpowiada na prawdziwe zapytania w połowie ścieżki w Twojej witrynie

**To znaczy:**

1. **Przestań usprawiedliwiać tworzenie skalowanych list/porównań stwierdzeniem, że „zdobywa cytowania AI”.** Na ChatGPT — największej powierzchni odpowiedzi na sztuczną inteligencję — to uzasadnienie straciło połowę swojej mocy w jednym wydaniu.
2. **Zmiana „oficjalnego”/głównego źródła faworyzuje strony, które posiadasz.** Strony produktów, dokumenty, strony z cenami i oryginalne badania — strony, które tylko Ty możesz publikować — zyskują na popularności jako klasa, którą można cytować. To pogłębia wniosek Gemini (strony należące do firm ≈ 60% cytowań).
3. **Strategia formatu jest teraz dostosowana do poszczególnych platform.** Zanim wybierzesz formaty, sprawdź, które wyszukiwarki mają znaczenie dla Twojej kategorii:

| Format | ChatGPT (po wersji 5.6) | Google AIO | Gemini | Perplexity |
|---|---|---|---|---|
| Listy / best-of | Zdegradowany | Zależne od rankingów | OK | OK |
| Porównanie / vs strony | Zdegradowany | Zależne od rankingów | OK | OK |
| Badania oryginalne + dane | Silny | Silny | Silny | Silny |
| Produkt/dokumentacja/pricing (własne, „oficjalne”) | **Wzrost** | Silny | **Dominujący** | Silny |
| Poradniki / poradniki | Stały | Silny | OK | Silny |

*(Zastrzeżenie do tabeli: degradację zmierzono tylko na ChatGPT. „OK” dla Gemini/Perplexity oznacza, że nie zgłoszono tam żadnej degradacji — nie, że zmierzono stabilność. Każdy silnik może dostarczać własną zmianę biegów w stylu 5.6.)*

4. **Każdą powyższą liczbę traktuj jako opatrzoną datą migawkę.** Ta sama doktryna, co zmienność źródła: są to pomiary poruszającego się układu z sierpnia 2026 r. Przed obstawianiem budżetu sprawdź swój własny monitoring cytowań.

## LinkedIn jako powierzchnia cytatów

LinkedIn jest jedną z najczęściej cytowanych domen w przypadku zapytań zawodowych, ale skład powierzchni zmienił się w 2026 r. i różni się w zależności od silnika: ChatGPT przeniósł się z artykułów Pulse do postów, Perplexity i Copilot nadal cytują artykuły i strony firmowe, a Gemini prawie w ogóle nie cytuje LinkedIn. Pierwsze słowa posta nadal tworzą slug adresu URL, więc umieść docelową frazę na początku.
Korekta: przewodnik LinkedIn nie mówi, że artykuły uzyskują ~60% cytowań w porównaniu z ~40% w przypadku postów. Mówi, że artykuły, biuletyny i posty *łącznie* stanowią 60%. Podziały stron trzecich dają ogólnie przewagę artykułom (około 60–70% w porównaniu z 25–35%), ale nie w ChatGPT.

Pełny podział według silnika, dostępu dla robotów indeksujących, samokontroli `noindex` i tego, co sprawia, że ​​posty można cytować: [linkedin-ai-citations.md](linkedin-ai-citations.md).

## Diagnostyka DIY: wyodrębnij prawdziwe zapytania ChatGPT

Nie potrzebujesz narzędzia, aby zobaczyć, czego faktycznie szuka ChatGPT w Twojej niszy (metoda rozpowszechniona publicznie, sierpień 2026 r.):

1. Uruchom ważne zapytanie dotyczące swojej kategorii w ChatGPT (z wyszukiwaniem).
2. Otwórz DevTools → zakładkę Sieć, odśwież rozmowę (identyfikator URL po `/c/`).
3. Znajdź ładunek odpowiedzi konwersacji i wyszukaj w nim `queries`.
4. Zobaczysz dosłowne wyszukiwania w tle, które ChatGPT rozszerzyło.

**Użyj go do:** budowania listy testów zapytań na podstawie *prawdziwego* zachowania fan-out zamiast domysłów; sprawdzenie, czy rozwinięcia Twojej kategorii nadal korzystają z modyfikatorów „najlepsze/vs”, czy też przeszły na wzorce `site:`/„oficjalne”; znajdowanie podtematów, których nie obejmuje Twoja treść.
**Następnie przejdź wstecz, zaczynając od domen.** Jeśli rozwinięcie `site:` przeprowadzi wyszukiwanie w zewnętrznych źródłach (Gartner, G2, Capterra) dla Twojej kategorii, te profile będą Twoją listą priorytetów, często przed nowymi stronami w Twojej witrynie. Zobacz [positioning-and-consensus.md](positioning-and-consensus.md).

**Nie używaj go do:** automatycznego generowania i masowego publikowania artykułu na zapytanie typu fan-out. To jest dokładnie zdegradowany wzorzec treści skalowanych w wersji 5.6 (oraz nazwy zasad Google dotyczących nadużyć w zakresie skalowanych treści). Diagnostyka służy do planowania zasięgu, a nie do spamowania treści.

## Rygor pomiaru: odpowiedzi AI są niedeterministyczne

Pojedyncza odpowiedź ChatGPT to anegdota, a nie pomiar — ten sam monit zwraca różne źródła na bieżąco. (Zastosowane tu ramy rygoru statystycznego zostały spopularyzowane przez Josha Pigforda, specjalistę ds. audytu AEO z firmy Final Commit, sierpień 2026 r.; praktyka ta jest samodzielna.)

Podczas audytu lub monitorowania:

- **Zarządzaj promptami tak jak słowami kluczowymi.** „Szukam najlepszego X”, „Jaki jest najlepszy X” i „znajdź mi najlepszy X” zwykle zwracają te same marki. Zwiń warianty sformułowań w jeden podstawowy monit dla każdej intencji i zamiast tego wydawaj budżet na powtarzalne uruchomienia.
- **Uruchom każde zapytanie 3–5 razy na platformę**, za każdym razem nowa sesja.
- **Śledź *odsetek* wzmianek lub cytowań** („cytowano w 3 z 5 uruchomień”), nigdy pojedynczą odpowiedź tak/nie.
- **Podaj wielkość próby** z każdą liczbą („40% współczynnika wzmianek, n=5”), aby w przyszłości wiedzieć, jak bardzo jej ufać.
- **Porównuj odsetki w czasie, a nie pojedyncze uruchomienia.** Spadek z 4/5 do 3/5 oznacza hałas; sygnałem jest spadek z 4/5 do 0/5 utrzymujący się w ciągu miesiąca.
- Przed zdiagnozowaniem *dlaczego* nie jesteś cytowany, podział powoduje, jak powinien wyglądać audyt: **techniczny** (nie można przeszukać/przeanalizować — zobacz agent-readiness.md), **zrozumienie** (sztuczna inteligencja opisuje Cię niedokładnie lub niejasno) lub **zaufanie** (zrozumienie, ale nie wybrane — zobacz citations-vs-recommendations.md).

---

*Źródła, wszystkie oznaczone i datowane: dane Peec AI sprzed i po wersji 5.6 za pośrednictwem Tomka Rudzkiego i Lily Ray (sierpień 2026 r.); Numery orientacyjne AEO LinkedIn za pośrednictwem Chrisa Longa (wrzesień 2026 r., zgłoszenie platformy); metoda ekstrakcji fan-out zgodnie z publikacją (sierpień 2026 r.); określenie ram rygorystycznych pomiarów przypisywanych umiejętności audytu AEO firmy Final Commit (Josh Pigford, sierpień 2026 r.). Wszystkie migawki niestabilnego systemu — sprawdź na podstawie własnego monitoringu.*