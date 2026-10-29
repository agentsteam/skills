# Gotowość agenta — czy agent może dotrzeć do Twojej witryny, nawigować i analizować ją?

Praca nad widocznością AI dzieli się na dwie warstwy: to, co mówi Twoja treść (reszta tej umiejętności) i to, czy agent w ogóle może *dotrzeć do tego*. To odniesienie obejmuje drugą warstwę — audyt dostępu/wykrywania/analizowalności — oraz pojawiające się przejście od witryn *czytelnych* dla agentów do witryn *umożliwiających agentom działanie*.

Dwa bezpłatne narzędzia do punktacji zostały udostępnione w sierpniu 2026 r. i zamieniły to w mierzalną dyscyplinę:

| Narzędzie | Uruchom to | Metoda |
|---|---|---|
| **Is Agentic** (Vercel + Ora) | `npx is-agentic yourdomain.com` lub [is-agentic.com](https://is-agentic.com) | Ponad 100 kontroli; Niezbędne kontrole przynoszą większość wyniku; Zalecane kontrole aktywują się tylko wtedy, gdy dowody wskazują, że masz taką powierzchnię (API, serwer MCP, handel); kontrole niemające zastosowania są wykluczone, a nie zakończone niepowodzeniem; obejmuje obserwowaną podróż agenta, pokazującą, gdzie prawdziwy agent napotkał tarcie |
| **Frase Agent Readiness Checker** | [frase.io/tools/agent-readiness](https://www.frase.io/tools/agent-readiness) | Triada dostępu / odkrywania / analizowalności; 80+ = agenci mogą niezawodnie korzystać ze strony, 60–79 = solidnie z lukami, <60 = rzeczywiste problemy z dostępem |

Uruchom go przed i po wszelkich pracach związanych z przygotowaniem agenta — wynik jest artefaktem, który można udostępniać, a nieudane testy stanowią Twoją listę roboczą. (Oba są narzędziami dostawców, za którymi kryje się produkt; *kontrole* dotyczą wartości, a nie prezentacji.)

## Trzy pytania

### 1. Dostęp — czy agent może dostać się na stronę i zobaczyć prawdziwą treść?
- **Główna treść w początkowej odpowiedzi HTML.** Większość agentów nigdy nie wykonuje kodu JavaScript. Jeśli treść istnieje dopiero po wyrenderowaniu po stronie klienta, nie istnieje. Jest to najważniejsza kontrola w przypadku obu narzędzi.
- **Brak wyzwań dla botów i blokowania zapory sieciowej** na zamierzonej ścieżce wykrywania. Blokowanie `OAI-SearchBot`, `PerplexityBot` lub `Claude-SearchBot` może zmniejszyć widoczność wyszukiwania. Blokowanie robotów indeksujących służących do opracowywania modeli, takich jak `GPTBot` lub `ClaudeBot`, może stanowić celową rezygnację ze szkolenia i samo w sobie nie stanowi błędu w widoczności. Sprawdź, co Twój CDN/WAF faktycznie robi z każdym identyfikatorem user-agent — wiele witryn domyślnie je blokuje, nikt o tym nie decyduje.
- **Prawidłowe zachowanie HTTP**: rzeczywiste kody stanu (bez soft-404), stabilne kanoniczne adresy URL, możliwe do naprawienia błędy.

### 2. Odkrycie — czy Twoje pliki informują agentów, co się tutaj znajduje?

- **plik robots.txt z wyraźnym stanowiskiem dotyczącym robota AI** — nazwij odpowiednie identyfikatory user-agent i podaj zasady dotyczące określonego celu, zamiast pozostawiać je do założenia (zobacz wskazówki dotyczące dostępu do botów w SKILL.md).
- **Mapa witryny, która ładuje się i analizuje w sposób przejrzysty.**
- **llms.txt w katalogu głównym domeny** (patrz Pliki do odczytu maszynowego w SKILL.md).
- **`llms-full.txt`** — nowszy dodatek: cała zawartość witryny w jednym pliku, dzięki czemu agent otrzymuje wszystko w jednym żądaniu, zamiast przeszukiwać całą witrynę. Pojawiający się, tani w generowaniu wraz z plikiem llms.txt i oceniany jako sygnał bonusowy przez oba narzędzia.
- **Oświadczenia dotyczące wykorzystania treści w pliku robots.txt** — wyłaniająca się konwencja dotycząca deklarowania, co sztuczna inteligencja może zrobić z Twoją treścią (trenowanie/cytowanie/podsumowywanie), dzięki czemu odpowiedź pochodzi od Ciebie, a nie jest zakładana.

### 3. Możliwość analizy — czy agent może stwierdzić, co to jest za strona?

- **Adekwatne, merytoryczne dane strukturalne** (JSON-LD — patrz umiejętność `schema`).
- **Reprezentacja strony w Markdown.** To najnowsza technika na stosie, dwie implementacje:
  - **Negocjacja treści**: udostępniaj kompaktowy Markdown pod *tym samym kanonicznym adresem URL*, gdy żądanie pyta o `Accept: text/markdown`, z nagłówkiem `Vary` oddzielającym wpisy pamięci podręcznej HTML i Markdown. (W ten sposób Is Agentic udostępnia własne raporty — agenci otrzymują Markdown, przeglądarki otrzymują HTML i jeden adres URL.)
  - **Nagłówek łącza**: nagłówek HTTP `Link` na stronie HTML wskazujący na równoległą wersję Markdown — możliwy do wykrycia bez zgadywania adresów URL.
- Przejrzysta struktura dokumentu — jedno H1, nagłówki odpowiadające na pytania dodatkowe, wyodrębniane bloki odpowiedzi (odniesienie do wzorców treści).

## Pojawiające się: możliwe do podjęcia przez agenta, a nie tylko do odczytania przez agenta
Możliwość odczytu staje się podstawowym wymogiem. Następny wyścig polega na tym, czy agent może *działać* na Twojej stronie — wypełnij formularz, zarezerwuj spotkanie, rozpocznij okres próbny. **WebMCP** jest tutaj wyłaniającym się standardem: strona deklaruje swoje formularze i wezwania do działania jako wywoływalne narzędzia ze schematami wejściowymi, więc agent nie musi odtwarzać Twojego interfejsu użytkownika. Początki (etykieta: pojawia się, jeszcze nie jest sygnałem do rankingu/cytowania), ale kierunek jest jasny — jeśli agenci stają się kupującymi, witryna przedstawiająca „rozpoczęcie okresu próbnego” jako ustrukturyzowane działanie wygrywa konwersję za pośrednictwem agenta, którą przegrywa ładny przycisk.

Praktyczne kroki na dziś: upewnij się, że Twoje najważniejsze działania (rejestracja, wycena, rezerwacja wersji demonstracyjnej, kontakt) działają bez przepływów opartych wyłącznie na JavaScript, mają oznaczone semantyczne pola formularzy i zwracają potwierdzenie do odczytu maszynowego.

**Sposoby dodania WebMCP** (wszystko na początku; potwierdź obsługę przeglądarki i asystenta, zanim cokolwiek obiecasz):
- **Zaimplementuj to samodzielnie.** Postępuj zgodnie z wersją roboczą WebMCP, aby zadeklarować każdą akcję jako narzędzie ze schematem wejściowym, połączonym z formularzem lub interfejsem API, którego strona już używa. Zachowaj krótką listę narzędzi (2–4 działania o najwyższym celu) i ponownie wykorzystuj istniejącą weryfikację, ochronę przed spamem i uprawnienia, zamiast budować równoległą ścieżkę.
- **Skorzystaj ze wsparcia swojej platformy, jeśli ją posiada.** Niektóre platformy witryn i przepływy pracy agentów dodają za Ciebie protokół WebMCP. Na przykład Ploy ◆ ma Ploybook, który sprawdza witrynę, definiuje umowy dotyczące narzędzi, implementuje je w oparciu o istniejącą logikę formularzy i sprawdza je. Jest to przepływ pracy z przewodnikiem, a nie hostowany serwer MCP. ◆ oznacza [Zweryfikowanego partnera](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/REGISTRY.md#verified-partners) tego repozytorium (ujawnienie, a nie poparcie); podaj obok niego alternatywę, kiedy o niej wspominasz.
- **Poproś o to agenta kodującego** w repozytorium witryny, z tym samym zakresem: kilka działań, istniejąca logika, test dla każdego.

Niezależnie od ścieżki, sprawdź, czy każde narzędzie odrzuca nieprawidłowe dane wejściowe, czy zgłoszenia trafiają tam, gdzie trafia zwykły formularz (CRM, skrzynka odbiorcza, śledzenie konwersji) i czy nic nie omija wymogów zgody ani limitów żądań.

W przypadku produktów, które agent instaluje w trakcie zadania (narzędzia dla programistów, interfejsy API, infrastruktura), kolejnym krokiem poza działaniem w Twojej witrynie jest bycie dostawcą wybranym przez agenta. Zobacz [agent-defaults.md](agent-defaults.md).

## Zmienność źródła cytatów (dlaczego dywersyfikujesz)
Udziały zewnętrznych źródeł w cytowaniach nie są **stałe** — zmieniają się z dnia na dzień wraz z aktualizacjami modeli i pobierania, a w sierpniu 2026 r. przedstawiono studium przypadku: **Zmiany w zakresie rozgałęziania zapytań ChatGPT prawie wymazały Reddit jako źródło cytatów** w ciągu kilku dni (zgłoszone przez praktyków przez wiele zespołów AEO; przed zmianą jeden z nich uzyskał cytowania z Reddita w ciągu 24 godzin przy ponad milionie wyświetleń/miesiąc). Tymczasem ci sami praktycy podają, że **witryny należące do firm dominują w cytowaniach Gemini (~60%)**.

LinkedIn przeniósł się w tej samej aktualizacji: liczba cytowań LinkedIn w serwisie ChatGPT spadła o ~36% w połowie sierpnia 2026 r., a cytowania artykułów Pulse spadły o ~86% od maja do października, podczas gdy cytowania postów w kanałach wzrosły. Perplexity i Copilot przesunęli się w drugą stronę. Zobacz [linkedin-ai-citations.md](linkedin-ai-citations.md).

Co to oznacza dla strategii:

- **Nigdy nie skupiaj pracy nad widocznością sztucznej inteligencji na jednej powierzchni innej firmy.** Lista filarów obecności (Wikipedia, Reddit, YouTube, podcasty, witryny z recenzjami, Quora) to portfolio, a nie menu, z którego można wybrać jedno. Powierzchnia stanowiąca obecnie 2% cytowań może wynosić 0% po jednej aktualizacji pobierania — i odwrotnie.
- **Podstawy posiadanych witryn zabezpieczają zmienność.** Transakcje platformowe i zmiany w zakresie pobierania powodują przetasowanie źródeł zewnętrznych; Twoja własna witryna czytelna dla agenta to jedyna przestrzeń, z której żadna platforma nie może Cię wyrzucić, a w Gemini jest to już dominująca klasa cytowań.
- **Każdą statystykę dotyczącą udziału cytowań traktuj jako opatrzoną datą.** Statystyki klasy „Reddit = 1,8% cytowań ChatGPT” (w tym te dotyczące tej umiejętności) to migawki — sprawdź datę i zweryfikuj z własnym monitorowaniem cytowań (pętla monitorowania DIY w SKILL.md) przed obstawieniem budżetu na nie.
- **Prędkość jest prawdziwa**: świeżą treść na odzyskanych powierzchniach można cytować w ciągu ~24 godzin. Wyszukiwanie AI nagradza świeżość szybciej niż kiedykolwiek robiło to klasyczne SEO.

---

*Taksonomia kontroli gotowości agenta wywodząca się z publikacji Vercel/Ora Is Agentic (is-agentic.com) i Agent Readiness Checker firmy Frase (oba z sierpnia 2026 r., przypisane); zdarzenia związane ze zmiennością cytowań zgłoszone przez praktyków (Ashni z Hype Partners (@ashnichrist) i inni, sierpień 2026 r.) — odpowiednio oznaczone, sprawdź na podstawie własnego monitoringu.*