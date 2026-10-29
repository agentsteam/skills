# Międzynarodowe SEO: dowody i źródła

Szczegółowe dowody potwierdzające sekcję Międzynarodowego SEO i lokalizacji w umiejętności Audyt SEO. Uporządkowane tematycznie ze źródłowymi adresami URL i kluczowymi cytatami.

---

## Hreflang

### Metody umieszczania adnotacji

Google obsługuje trzy równoważne metody: HTML `<link>` w `<head>`, nagłówki HTTP `Link` i elementy mapy witryny XML `<xhtml:link>`. Google potwierdziło, że żadna metoda nie ma pierwszeństwa przed inną.

Google łączy sygnały z HTML i map witryn. Jeśli ta sama para język-region wskazuje na różne adresy URL w różnych metodach, Google zamiast zgadywać, usuwa tę parę.

- [Centrum wyszukiwarki Google: wersje zlokalizowane](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [SEJ: Google łączy sygnały Hreflang](https://www.searchenginejournal.com/google-combines-hreflang-signals-from-html-sitemaps/389219/)

### Wymaganie wzajemne

Dokumenty Google: „Jeśli strona X zawiera link do strony Y, strona Y musi zawierać link z powrotem do strony X. W przeciwnym razie te adnotacje mogą zostać zignorowane lub niepoprawnie zinterpretowane”.

Każda strona musi zawierać samą siebie (odnoszącą się do siebie) w zestawie hreflang. Brak odniesienia do samego siebie to błąd nr 1 wykryty przez audyty Semrush. Badanie 374 756 domen wykazało, że 67% wdrożeń hreflang miało problemy.

- [Centrum wyszukiwarki Google: wersje zlokalizowane](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Semrush: 9 typowych błędów Hreflang](https://www.semrush.com/blog/hreflang-errors/)
- [Search Engine Land: 31% międzynarodowych stron internetowych zawiera błędy Hreflang](https://searchengineland.com/study-31-of-international-websites-contain-hreflang-errors-395161)

### x-default
Jest to zalecane rozwiązanie zastępcze dla użytkowników niedopasowanego języka/regionu, a nie warunek obowiązkowy w przypadku prawidłowych adnotacji językowych. Zgłoś jego brak jako zalecenie projektowe, gdy przydatne jest rozwiązanie awaryjne, zamiast deklarować nieważność całej implementacji hreflang.

Wprowadzono w kwietniu 2013 r. Wyznacza stronę rezerwową dla użytkowników, których język/region nie pasuje do żadnego zadeklarowanego wariantu. Może wskazywać ten sam adres URL, co jeden z alternatywnych adresów językowych. Jeśli jest używany, uwzględnij go konsekwentnie w pełnym zestawie adnotacji na każdej stronie wariantu.

- [Blog Google: x-default hreflang](https://developers.google.com/search/blog/2013/04/x-default-hreflang-for-international-pages)
- [Blog Google: Jak x-default może Ci pomóc (2023)](https://developers.google.com/search/blog/2023/05/x-default)

### Kody języków i regionów

Język: ISO 639-1 (2-literowy). Region: ISO 3166-1 Alpha 2 (2-literowy). Format: `language[-script][-region]`.

Nie można określić samego kodu regionu. Typowe błędy: `en-UK` (powinno być `en-GB`), `es-419` (nie ISO 3166-1). Badanie wykazało, że 8,9% witryn korzystających z hreflang zawiera nieprawidłowe kody językowe.

- [Centrum wyszukiwarki Google: wersje zlokalizowane](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Search Engine Land: badanie 31%](https://searchengineland.com/study-31-of-international-websites-contain-hreflang-errors-395161)

### Hreflang w skali (ponad 20 wersji językowych lub regionalnych)

Przy 20 wersjach językowych lub regionalnych adnotacje hreflang w HTML `<head>` dodają ~1,5 KB na stronę, co daje zerową korzyść dla użytkownika. hreflang oparty na mapie witryny ma zerowy wpływ na wydajność środowiska wykonawczego. Elementy podrzędne `<xhtml:link>` NIE wliczają się do limitu 50 000 adresów URL mapy witryny (liczą się tylko elementy `<loc>`).
John Mueller zaleca skupienie hreflang na stronach generujących ruch w niewłaściwym języku, a nie na każdej stronie: „Nie robiłbym tego w przypadku żadnej innej strony w witrynie, ponieważ jest ona tak złożona i trudna w zarządzaniu”.

- [SERoundtable: Elementy podrzędne się nie liczą](https://www.seroundtable.com/google-child-elements-dont-count-towards-sitemap-url-limit-34377.html)
- [SERoundtable: Gdzie skupić się na Hreflang](https://www.seroundtable.com/using-hreflang-34127.html)
- [Yoast: Przewodnik po hreflangu](https://yoast.com/hreflang-ultimate-guide/)

### Google kontra Bing

Bing traktuje hreflang jako „słaby sygnał”. Bing opiera się na metatagu `content-language`, atrybucie HTML `lang`, ccTLD i lokalizacji serwera. Yandex obsługuje hreflang tak jak Google.

Dla obu silników: zaimplementuj hreflang (Google/Yandex) + `<html lang="...">` + `<meta http-equiv="content-language">` (Bing).

- [Digital Ready Marketing: Bing nie używa języka Hreflang](https://digitalreadymarketing.com/bing-doesnt-use-hreflang-annotation-what-does-it-use/)
- [Yoast: Przewodnik po hreflangu](https://yoast.com/hreflang-ultimate-guide/)

---

## Kanonizacja i i18n

### Wybierz elementy kanoniczne według treści i języka

Używaj adresów kanonicznych wskazujących na samą stronę dla różnych stron regionalnych, w tym autentycznie przetłumaczonych treści. Nie konsoliduj tłumaczeń w różnych językach tylko dlatego, że opisują ten sam produkt.

W przypadku podobnych lub zduplikowanych stron regionalnych w **tym samym języku** Google zaleca wybranie preferowanej strony kanonicznej i użycie spójnych adnotacji `hreflang`. Na przykład równoważna treść w języku niemieckim w `example.de/` i `example.com/de/` może mieć wspólny preferowany kanon; każdy regionalny adres URL nie musi być kanonizowany do samego siebie.
- [Google: Obsługa zduplikowanych stron wielojęzycznych/wieloregionalnych](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites#handling-duplicate-pages-with-multilingualmulti-regional-sites)
- [Google: Konsoliduj zduplikowane adresy URL](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)

### Dopasuj sygnały kanoniczne i Hreflang

Zachowaj spójność celów kanonicznych i klastrów `hreflang` z wybraną strategią dotyczącą treści/języka. `hreflang` identyfikuje zlokalizowane alternatywy; nie zmusza Google do niezależnego indeksowania każdego adresu URL. Elementy kanoniczne są sygnałami dla procesu selekcji Google, a nie gwarancją indeksowania.

Preferowanym adresem kanonicznym musi być adres URL wewnątrz klastra `hreflang`. Google ignoruje `hreflang` w adresie URL, który jest kanonizowany do innego.

- [Google: Konsoliduj zduplikowane adresy URL](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)

### Prawie zduplikowane warianty regionalne

Mueller (Office Hours, 2023): „Jeśli treść jest całkowicie taka sama i nie możemy dostrzec żadnej różnicy, dla uproszczenia i wygody użytkownika możemy pokazać tylko jedną wersję – nawet jeśli obecny jest hreflang”.

Mimo `hreflang` Google może konsolidować identyczne lub prawie zduplikowane treści regionalne. W stosownych przypadkach użyj powyższej strategii preferowanego języka kanonicznego w tym samym języku; nie obiecuj, że różnice kanoniczne lub kosmetyczne sprawią, że każdy regionalny adres URL będzie indeksowany.

- [International Webmastery: zduplikowane strony w tym samym języku](https://internationalwebmastery.com/blog/how-google-handles-canonicalization-of-same-language-duplicate-near-duplicate-pages/)
- [Google: Zarządzanie witrynami wieloregionalnymi](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites)

### Paginacja w różnych wersjach językowych lub regionalnych
Google: „Nie używaj pierwszej strony sekwencji podzielonej na strony jako strony kanonicznej. Zamiast tego nadaj każdej stronie własny kanoniczny adres URL”. Każda stronicowana strona w każdym języku staje się kanoniczna, odnosząca się do siebie. `rel="next/prev"` wycofany z marca 2019 r.

- [Google: sprawdzone metody dotyczące paginacji](https://developers.google.com/search/docs/specialty/ecommerce/pagination-and-incremental-page-loading)

---

## Międzynarodowe mapy witryn

### Struktura

Każdy wpis `<url>` zawiera alternatywy `<xhtml:link>` dla każdej lokalizacji. Wymaga przestrzeni nazw `xmlns:xhtml="http://www.w3.org/1999/xhtml"`.

Podziel mapy witryn według typu zawartości, a nie według ustawień regionalnych. Dzielenie według ustawień regionalnych stwarza problemy w utrzymaniu, ponieważ każda mapa witryny z ustawieniami regionalnymi musi odwoływać się do wszystkich innych ustawień regionalnych (wymóg wzajemny).

- [Centrum wyszukiwarki Google: wersje zlokalizowane](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Lumar: Jak Google obsługuje Hreflang](https://www.lumar.io/office-hours/hreflang/)

### Limity rozmiaru

50 000 adresów URL / 50 MB nieskompresowanych na mapę witryny. Tylko elementy `<loc>` wliczają się do limitu 50 tys. Jednak przy 20 alternatywnych wersjach hreflang na wpis ograniczenie rozmiaru pliku wynoszącego 50 MB staje się wąskim gardłem. Zaplanuj 2000–5000 adresów URL na mapę witryny, jeśli używasz pełnego hreflangu.

- [Google: Utwórz i prześlij mapę witryny](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)
- [SERoundtable: Mapa witryny Limit 50 000](https://www.seroundtable.com/google-sitemap-50-000-limit-based-on-location-urls-not-alternative-urls-33843.html)

### Zgłoszenie

Prześlij indeks mapy witryny w Search Console ORAZ odwołaj się do niego w pliku robots.txt. Poszczególne mapy witryn podrzędnych można przesyłać oddzielnie w celu raportowania dotyczącego poszczególnych map witryn.

- [Google: utwórz i prześlij mapę witryny](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)

### Ostrzeżenie dotyczące Next.js
Next.js `alternates.languages` NIE zawiera automatycznie odniesienia `<xhtml:link>` do adresu URL `<loc>`. Musisz jawnie uwzględnić własny język adresu URL `<loc>` w obiekcie `languages`.

- [Dokumenty Next.js: mapa witryny.xml](https://nextjs.org/docs/app/api-reference/file-conventions/metadata/sitemap)

---

## Struktura adresu URL

### Porównanie strategii

Google traktuje podkatalogi i subdomeny jednakowo. Mueller: „Z naszego punktu widzenia... mówią, że subdomeny i podkatalogi są zasadniczo równoważne.”

Parametry adresu URL (`?lang=en`) są wyraźnie „Niezalecane” w dokumentach Google.

- [Google: Zarządzanie witrynami wieloregionalnymi](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites)

### Język domyślny

Mueller zaleca: ustaw `/` jako x-default, umieść każdy język z własnym przedrostkiem. Bez oznaczania `/` jako wersji x-default „dla Google może to wyglądać tak, jakby„/” było stroną odrębną od pozostałych”.

- [Blog Google: x-default](https://developers.google.com/search/blog/2023/05/x-default)
- [Blog Google: Tworzenie właściwej strony głównej](https://developers.google.com/search/blog/2014/05/creating-right-homepage-for-your)

### Negocjowanie treści / Przekierowania IP

Google zdecydowanie odradza stron dostosowanych do ustawień regionalnych. Googlebot crawluje z adresów IP w USA i nie wysyła nagłówków Accept-Language. Wymagane są osobne adresy URL i hreflang.

- [Google: Strony dostosowujące się do ustawień regionalnych](https://developers.google.com/search/docs/specialty/international/locale-adaptive-pages)

### Spójność ukośnika końcowego

Mueller: końcowy ukośnik stanowi „znaczną część adresu URL i zmieni adres URL, niezależnie od tego, czy tam jest, czy nie”. Wybierz jeden format dla wszystkich ścieżek ustawień regionalnych, linków wewnętrznych, plików kanonicznych, hreflang i map witryn.
Mueller (2025): „Spójność jest najważniejszym technicznym czynnikiem SEO”.

- [SERoundtable: Spójność to największy techniczny czynnik SEO](https://www.seroundtable.com/google-consistency-seo-40427.html)

### Kierowanie geograficzne w Search Console

Raport Kierowanie międzynarodowe jest przestarzały. Google polega teraz całkowicie na hreflangu, analizie języka treści i wzorcach linkowania. Możesz dodać właściwości podkatalogu na potrzeby raportowania według ustawień regionalnych.

- [Pomoc Google: kierowanie międzynarodowe wycofane](https://support.google.com/webmasters/answer/12474899?hl=en)

### Tryby regionalne platformy

Użyj `localePrefix: 'always'` (next-intl) lub odpowiednika. Nigdy nie ukrywaj ustawień regionalnych przed adresami URL – Google potrzebuje unikalnych adresów URL dla każdego języka. Korzystanie z trybu `'never'` całkowicie wyłącza łącza alternatywne.

- [next-intl: Konfiguracja routingu](https://next-intl.dev/docs/routing/configuration)
- [Dyskusja Next.js #18419](https://github.com/vercel/next.js/discussions/18419)

---

## Jakość treści w różnych wersjach językowych lub regionalnych

### Treść przetłumaczona automatycznie (stanowisko 2025)

W połowie 2025 r. Google usunęło wieloletnie wytyczne zalecające unikanie automatycznie tłumaczonych treści. Obecne stanowisko: „Nasze zasady nie definiują ściśle treści przetłumaczonych przez sztuczną inteligencję jako spam”. Polityka dotycząca nadużyć w treści skalowanej wymienia tłumaczenie jako możliwy wektor, ale go nie zakazuje.

Reddit skalował tłumaczenia AI na ponad 35 języków za wiedzą Google. Kluczowym rozróżnieniem jest zamiar i jakość, a nie metoda.

- [Zasady Google dotyczące spamu](https://developers.google.com/search/docs/essentials/spam-policies)
- [Glenn Gabe: Automatyczne tłumaczenie treści](https://www.gsqi.com/marketing-blog/auto-translating-content-google-scaled-content-abuse/)
- [SE Land: Tłumaczenia AI Reddit](https://searchengineland.com/google-comments-on-reddits-use-of-ai-to-translate-its-pages-456908)

### Strony regionalne o ubogiej treści
Google: „Zlokalizowane wersje strony są uważane za duplikaty tylko wtedy, gdy główna treść strony pozostaje nieprzetłumaczona”. Strony zawierające wyłącznie przetłumaczony szablon są grupowane jako duplikaty.

NIE używaj noindex do niechcianych stron regionalnych (marnuje budżet crawlowania). Nie kanonizuj oddzielnych tłumaczeń na inny język tylko po to, aby ukryć ubogą treść. Najlepsze podejście: nie twórz stron regionalnych, których nie możesz uczynić naprawdę pomocnymi.

- [Google: wersje zlokalizowane](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Google: Zarządzanie budżetem crawlowania](https://developers.google.com/search/docs/crawling-indexing/large-site-managing-crawl-budget)

### Wpływ systemu przydatnych treści

Połączone z rankingiem podstawowym w marcu 2024 r. Sygnał dla całej witryny: „wszelka treść – nie tylko nieprzydatna – w witrynach, w których stwierdzono, że ogółem zawiera stosunkowo dużo nieprzydatnej treści, ma mniejsze szanse na dobre wyniki w wyszukiwarce”.

Przetłumaczone strony niskiej jakości mogą obniżać wyniki całej witryny. Jest to najsilniejszy argument przeciwko tworzeniu stron regionalnych, które nie są naprawdę pomocne.

- [Blog Google: aktualizacja przydatnej zawartości](https://developers.google.com/search/blog/2022/08/helpful-content-update)
- [Amsive: Co zmieniło się w 2024 r.](https://www.amsive.com/insights/seo/googles-helpful-content-update-ranking-system-what-happened-and-what-changed-in-2024/)

### Częściowe tłumaczenie

Google: „Tłumaczenie tylko standardowego tekstu na stronach przy jednoczesnym zachowaniu większości treści w jednym języku… może pogorszyć komfort użytkownika”. Google używa widocznej treści (nie atrybutu lang), aby określić język strony.
Przetłumacz CAŁĄ zawartość strony, jeśli utworzysz wersję regionalną. Nieprzetłumaczone metadane (tytuł, opis) w złym języku obniżają CTR.

- [Google: Zarządzanie witrynami wieloregionalnymi](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites)

### Budżet crawlowania

Dotyczy to tylko ponad 1 mln stron lub ponad 10 tys. stron zmienianych codziennie. Jednak alternatywne adresy URL (cele hreflang) zużywają budżet crawlowania. Zepsute linki hreflang marnują budżet ORAZ unieważniają sygnały.

- [Google: Zarządzanie budżetem crawlowania](https://developers.google.com/search/docs/crawling-indexing/large-site-managing-crawl-budget)
- [Blog Google: Budżet indeksowania](https://developers.google.com/search/blog/2017/01/what-crawl-budget-means-for-googlebot)

### Sygnały specyficzne dla ustawień regionalnych

Google identyfikuje odbiorców na podstawie: „lokalnych adresów i numerów telefonów na stronach, użycia lokalnego języka i waluty, linków z innych witryn lokalnych lub sygnałów z profilu Twojej firmy”.

- [Google: Zarządzanie witrynami wieloregionalnymi](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites)