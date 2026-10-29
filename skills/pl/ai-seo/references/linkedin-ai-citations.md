# Treść LinkedIn cytowana przez sztuczną inteligencję

LinkedIn to jedna z najczęściej cytowanych domen w przypadku zapytań profesjonalnych i B2B. Jednak to, która platforma LinkedIn zostanie cytowana, zależy w dużej mierze od silnika, a w 2026 r. zestawienie uległo gwałtownym zmianom. Traktuj każdą liczbę tutaj jako migawkę opatrzoną datą i sprawdzaj własne prompty.

## Spis treści
- Który rodzaj treści, który silnik
- Kto może co indeksować
- Co sprawia, że treści LinkedIn są cytowane
- Trwałość
- Ryzyko
- Lista kontrolna
- Źródła

---

## Która powierzchnia, który silnik

| Silnik | Co cytuje z LinkedIn (2026) |
|---|---|
| **ChatGPT** | Przeniesiono z artykułów Pulse do postów na kanale. Dane Ahrefs pokazują, że cytowania `/pulse/` w ChatGPT spadły o ~86%, a `/posts/` wzrosły o ~74% w okresie od maja do października 2026 r., przy ogólnym spadku o ~36% na LinkedIn w wyniku zmiany pobierania z połowy sierpnia, która również uderzyła w Reddit |
| **Perplexity** | Największa nieprzetworzona liczba cytatów z LinkedIn w próbie OtterlyAI i w naszym zestawie Ahrefs, przy czym strony firmowe mają największy udział w Ahrefs. (Semrush, mierząc udział odpowiedzi, które w ogóle cytują LinkedIn, stwierdził, że jest on niższy w przypadku Perplexity niż w przypadku ChatGPT lub AI Mode, więc ranking zależy od miary) |
| **Copilot** | Często i coraz częściej cytuje LinkedIn (liczba cytowań wzrosła ponad dwukrotnie w maju → październiku 2026 r., ~6,5 razy więcej niż w przypadku cytowań z Reddita). Pojawiają się zarówno artykuły Pulse, jak i posty |
| **Google AI Overviews / Tryb AI** | Cytowane posty i artykuły Pulse, a także strony firmowe |
| **Gemini** | Prawie nigdy nie cytuje LinkedIn (~0 w trzech oddzielnych zbiorach danych). Nie licz na LinkedIn, jeśli chodzi o widoczność w Gemini |
| **Claude** | Jego robot wyszukiwania jest dozwolony w artykułach, postach, profilach i stronach firmowych; mało opublikowanych danych o cytowaniach |

**Co to oznacza:**
- Publikuj posty w aktualnościach z myślą o ChatGPT oraz dłuższe artykuły z myślą o Perplexity, Copilot i funkcjach AI Google.
- Utrzymuj stronę firmy i profile ludzi. Perplexity najczęściej cytuje strony firmowe; ChatGPT i AI Mode cytują głównie poszczególnych członków.
- Pomiń wspólne artykuły (`/advice/`). Obecnie są praktycznie niecytowane.

**Nasza migawka Ahrefs** (cytowania adresów URL w linkedin.com w danych odpowiedzi AI Ahrefs, pobrane 2026-10-02; pula promptów zmienia się z biegiem czasu, więc traktuj ją jako kierunkową):

| Ścieżka | ChatGPT, 1 maja | ChatGPT, teraz | Perplexity | AI Overviews | Tryb AI | Copilot | Gemini |
|---|---|---|---|---|---|---|---|
| Wszystko na linkedin.com | 239 tys. | 185 tys. | 787 tys. | 352 tys. | 292 tys. | 154 tys. (w maju 65 tys.) | ~0,7 tys. |
| Artykuły `/pulse/` | 22,7 tys. | 3,3 tys. | 84 tys. | 43 tys. | 51 tys. | 23 tys. | ~0 |
| `/posts/` | 17,7 tys. | 30,8 tys. | 133 tys. | 62 tys. | 55 tys. | 18 tys. | 0 |
| `/company/` | — | — | 474 tys. | 51 tys. | 41 tys. | 15 tys. | — |
| Profile `/in/` | — | — | 103 tys. | 12 tys. | 13 tys. | 15 tys. | — |

---

## Kto może indeksować co

Plik robots.txt LinkedIn (sprawdzony 2026-10-02):

| Robot indeksujący | Artykuły, posty, profile, strony firmowe |
|---|---|
| Googlebot, Bingbot | Dozwolone |
| OAI-SearchBot (wyszukiwanie ChatGPT), Claude-SearchBot | Dozwolone |
| GPTBot, ChatGPT-User, ClaudeBot, Claude-User, PerplexityBot, Perplexity-User, Google-Extended, CCBot | Zablokowany |

Zatem ChatGPT i Claude mogą cytować LinkedIn ze swoich indeksów wyszukiwania, ale ich agenci „przeczytaj tę stronę” na żywo nie mogą go pobrać. Perplexity najczęściej cytuje LinkedIn, mimo że oba jego boty zostały zablokowane, prawdopodobnie za pośrednictwem innego indeksu.

**Sprawdź własne artykuły pod kątem `noindex`.** LinkedIn najwyraźniej oznacza niektóre artykuły Pulse jako noindex, podobno z kont o małej liczbie obserwujących lub o niskim zaangażowaniu i tylko dla robotów indeksujących, więc zalogowany autor nigdy ich nie widzi (jeden mały test, n=3). Sprawdź zarówno metatag robots, jak i nagłówek `X-Robots-Tag` w końcowej odpowiedzi dla każdego robota, na którym Ci zależy:

```bash
URL=https://www.linkedin.com/pulse/your-article-slug
for UA in Googlebot bingbot OAI-SearchBot; do
  echo "== $UA"
  curl -sIL -A "$UA" "$URL" | grep -iE '^(HTTP/|x-robots-tag)'
  curl -sL -A "$UA" "$URL" | grep -ioE '<meta[^>]+name="(robots|googlebot|bingbot)"[^>]*>'
done
```

Symbol `noindex` w dowolnym miejscu dla robota oznacza, że indeks wyszukiwarki prawdopodobnie nie będzie zawierać artykułu. Brak tagu nie jest dowodem na jego zaindeksowanie; potwierdź za pomocą wyszukiwania `site:`.

---

## Co sprawia, że treści LinkedIn są cytowane

**Potwierdzone niezależnymi danymi:**
- **Zaangażowanie nie ma większego znaczenia.** Polubienia i komentarze nie wykazują prawie żadnej korelacji z cytowaniem. Mediana cytowanego postu zawiera 15–25 reakcji; post ze 100 reakcjami ma podobną szansę na cytowanie jak post z 10 000.
- **Liczba obserwujących ma niewielkie znaczenie.** Cytowani są autorzy poniżej 500 obserwujących, a około połowa cytowań pochodzi od autorów poniżej 10 tys.
- **Oryginały wygrywają z ponownymi udostępnieniami.** Około 95% cytowanych postów to oryginały.
- **Naucz czegoś.** Najczęściej cytowane posty dzielą się wiedzą lub radami.
- **Spójność.** Około 75% autorów cytowanych postów opublikowało posty ponad 5 razy w ciągu ostatnich czterech tygodni.
- **Długość.** Cytowane artykuły mają przeważnie 500–2 000 słów; cytowane posty miały przeważnie 50–300 słów.
- **Najnowsze.** Około połowa cytowanych treści ma mniej niż trzy miesiące.

**Model przyczynowy dostawcy (Scrunch, ~4 tys. postów, traktuj jako kierunkowy):** szczegóły techniczne (+77%), nazwane podmioty, takie jak narzędzia, firmy i ludzie (+33%) oraz temat niszowy (+18%), który wzbudził cytowanie. Tekst pogrubiony lub pochylony w Unicode (-58%) i „link w komentarzach” (-31%) obniżyły liczbę cytowań postu. Badanie dotyczy ChatGPT i wykazało również, że linki w komentarzach mogą pomóc w cytowaniu połączonej strony, więc jest to kompromis, jeśli Twoim celem są cytaty z własnej witryny.

**Zgłoszone przez platformę (przewodnik LinkedIn, marzec 2026 r.):** artykuły zawierające 800–1200 słów, posty zawierające 200–300 słów, publikowane 2–3 razy w tygodniu. Przewodnik sugeruje również, że ponad 3000 obserwujących i ponad 10 komentarzy pomaga, czego nie potwierdzają powyższe niezależne dane.

**Mechanika:**
- Pierwsze słowa posta stają się jego adresem URL, więc umieść docelową frazę na początku.
- Strukturuj artykuły, takie jak treść bloga: jasne nagłówki, bezpośrednia odpowiedź na początku, konkretne liczby i nazwy.

---

## Trwałość
- Cytaty mogą być trwałe w przypadku konkretnych promptów o niskiej konkurencji. Sześć artykułów jednego z autorów B2B w Pulse zostało zacytowanych w 54–86% z 28 śledzonych serii trwających około 20 tygodni w związku z niszowymi promptami (Kaleigh Moore, wrzesień 2026, anegdota).
- Na poziomie platformy są one zmienne. W jednym badaniu o ustalonym terminie zmierzono spadek udziału LinkedIn w odpowiedziach AI o ~65% od lutego do lipca 2026 r., podczas gdy inne zmierzyły jego wzrost w serwisie Perplexity w tych samych miesiącach. Śledź według wyszukiwarki i nie angażuj wszystkich swoich działań w LinkedIn (zobacz sekcję dotyczącą zmienności w [agent-readiness.md](agent-readiness.md)).

---

## Ryzyko

- **Brak kontroli kanonicznej.** LinkedIn ustala swój własny kanoniczny artykuł, więc pełna ponowna publikacja Twojego wpisu na blogu stanowi konkurencję dla Twojej własnej strony. Najpierw opublikuj na swojej stronie, a następnie opublikuj dostosowaną wersję (przepisz jej znaczącą część) lub podsumowanie zawierające link zwrotny.
- **Nie jesteś jego właścicielem.** LinkedIn kontroluje indeksowanie, może oznaczać artykuły jako noindex i zmienia formaty. Domyślnie zawartość członków z USA może być używana do szkolenia modeli LinkedIn i Microsoft.
- **Gemini jako martwy punkt.** Widoczność zbudowana na LinkedIn nie zostanie przeniesiona do Gemini.

---

## Lista kontrolna

- [ ] Feed posty i długie artykuły, oba w zestawie, dopasowane do silników, na których Ci zależy
- [ ] Strona firmowa kompletna i zgodna ze stroną Informacje (patrz [positioning-and-consensus.md](positioning-and-consensus.md))
- [ ] Docelowa fraza w pierwszych słowach postu
- [ ] Oryginalna, konkretna treść techniczna z nazwami podmiotów; brak pogrubienia Unicode; świadomie decyduj, dokąd prowadzi link (w poście pomaga postowi, komentarze w komentarzach mogą pomóc w miejscu docelowym)
- [ ] Artykuły sprawdzone pod kątem robota `noindex`
- [ ] Posty na blogu opublikowane najpierw na Twojej stronie; Wersja LinkedIn dostosowana, nie powielana
- [ ] Cytaty śledzone według wyszukiwarki, ponownie sprawdzane co miesiąc

---

## Źródła

Wszystko opatrzone datą; większość z nich to badania dostawców wykorzystujące własne moduły śledzące, więc żaden nie jest w pełni neutralny.

- Profound, LinkedIn jako najczęściej cytowana domena w przypadku zapytań zawodowych (marzec 2026 r.): https://www.tryprofound.com/blog/linkedin-is-the-most-cited-domain-for-professional-queries-in-ai-search
- Semrush, badanie widoczności LinkedIn AI, 325 tys. promptów (marzec 2026 r.): https://www.semrush.com/blog/linkedin-ai-visibility-study/
- OtterlyAI, badanie cytowań w wyszukiwarce LinkedIn AI, 1,31 mln cytowań (czerwiec 2026 r.): https://otterly.ai/blog/linkedin-ai-search-citations-study/
- Cloro, artykuły na LinkedIn a posty (sierpień – wrzesień 2026): https://cloro.dev/blog/linkedin-articles-vs-posts/
- Goodie, badanie cytowań AI w mediach społecznościowych (wrzesień 2026 r.): https://higoodie.com/blog/social-media-ai-citations-study-2026/
- Scrunch, posty na LinkedIn i cytaty ChatGPT (maj 2026): https://scrunch.com/blog/linkedin-posts-robots-cant-resist-what-data-says-about-chatgpt-citations
- Zmiana źródła ChatGPT z połowy sierpnia 2026 r. (Promptwatch, Petra Labs): https://somethinginc.com/blog/chatgpt-citation-sources-docs-replaced-reddit/
- Ahrefs AI odpowiada na dane według ścieżki URL, pobrane 2026-10-02 (kierunkowe; pula promptów zmienia się w czasie)
- LinkedIn robots.txt, pobrany 2026-10-02; Przewodnik AEO LinkedIn (marzec 2026 r.)