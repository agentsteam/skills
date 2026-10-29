# Open Knowledge Format (OKF)

Specyfikacja Google oparta na Markdown w wersji 0.1 dotycząca przedstawiania zawartości witryny jako pakietu czytelnego dla agenta. Wprowadzono na [blogu Google Cloud](https://cloud.google.com/blog/products/data-analytics/how-the-open-knowledge-format-can-improve-data-sharing) 12.06.2026 i udostępniono w Knowledge Catalog.

## Co to jest

OKF to katalog połączonych plików Markdown. Każdy plik posiada:

- Blok YAML frontmatter (wymagany `type`; zalecany `title`, `description`, `resource`, `tags`, `timestamp`)
- Standardowy treść Markdown
- Standardowe linki do innych plików w pakiecie (które specyfikacja traktuje jako relacje koncepcyjne)

Opcjonalny `index.md` wyświetla listę plików w celu stopniowego ujawniania. Pakiet może być dystrybuowany jako repozytorium git (zalecane), plik tar/zip lub podkatalog większego repozytorium.

[Pełna specyfikacja](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/HEAD/okf/SPEC.md) mieści się na jednej stronie. Repozytorium podlega pod `GoogleCloudPlatform` (zastrzeżenie „nie jest to oficjalny produkt Google” to standardowy szablon Google dotyczący oprogramowania typu open source, a nie zaprzeczenie — pojawia się w większości repozytoriów Google typu open source, w tym w ich głównym repozytorium próbek AI).

### Minimalny plik koncepcyjny

```markdown
---
type: Article
title: How to Connect the Ahrefs MCP Server to Manus
description: The official MCP servers, why they did not connect, and the fix.
resource: https://yoursite.com/blog/ahrefs-mcp-manus/
tags: [mcp, ahrefs]
---

# How to Connect the Ahrefs MCP Server to Manus

The body of the post, as clean markdown.
```

Dodaj `index.md` zawierający listę wszystkich plików, aby agent mógł zobaczyć kształt pakietu przed otwarciem każdego pliku i to jest cały format.

## Uczciwe sposób przedstawienia
**Google stworzyło OKF dla zespołów zajmujących się danymi udostępniających metadane katalogu** — tabele BigQuery, punkty końcowe API, metryki, podręczniki. Większość przykładów specyfikacji to artefakty zespołu danych, a nie posty na blogu. Sposób przedstawienia na blogu Google: „ulepsz udostępnianie danych” i „ujednolicona dokumentacja” w celu współpracy między zespołami.

Wskazywanie OKF na stronę marketingową to **sprytne wykorzystanie** spopularyzowane przez [Suganthana Mohanadasana](https://suganthan.com/blog/open-knowledge-format/). Jest to uzasadniony przypadek użycia tego formatu, ale nie podstawowy przypadek Google. Sformułuj go dokładnie, wyjaśniając założycielom lub zespołom marketingowym.

## Co to daje dzisiaj w wyszukiwaniu AI

Nic natychmiastowego. Nic jeszcze nie przeszukuje sieci w poszukiwaniu pakietów OKF — specyfikacja ma już kilka tygodni, żaden silnik AI nie ogłosił integracji, a Knowledge Catalog pozyskuje pakiety tylko dla płacących zespołów zajmujących się danymi klientów korporacyjnych.

Traktuj OKF jako **rejestrację na poziomie protokołu** — taki sam kształt jak w przypadku wczesnego wdrożenia `schema.org` dziesięć lat temu. Schema zaczęła przynosić korzyści dopiero po wielu latach; ludzie, którzy wysłali go wcześniej, nadal są zadowoleni, że to zrobili.

Dodatkowa korzyść, która opłaca się dzisiaj, niezależnie od tego: **generowanie pakietu samo w sobie jest audytem linkowania wewnętrznego**. Narzędzie Suganthana rysuje każdą stronę jako węzeł, a każde łącze wewnętrzne jako krawędź, dzięki czemu wyspy i sieroty stają się widoczne na pierwszy rzut oka.

## Gdzie OKF mieści się w stosie czytelnym dla agenta

| Warstwa | Cel |
|---|---|
| `sitemap.xml` | Informuje robota, które adresy URL istnieją |
| `robots.txt` (z regułami bota AI) | Zezwala lub blokuje roboty AI |
| `llms.txt` | Wskazuje agentowi kilka stron, które najbardziej chcesz, by agent przeczytał |
| `/pricing.md` | Strukturalne ceny dla porównań agent-kupujący |
| **Pakiet `/okf/`** | Przekazuje samą treść jako powiązane koncepcje |
| Znacznik schematu | Dane strukturalne dotyczące poszczególnych stron (artykuł, strona z często zadawanymi pytaniami, produkt itp.) |

Te kumulują się, zamiast konkurować. `llms.txt` to drogowskaz, OKF to biblioteka.

## Jak opublikować pakiet

Trzy opcje, uporządkowane według wysiłku, jakiego wymagają:

### 1. Bezpłatne narzędzie internetowe Suganthana (zalecane w przypadku większości witryn)

[suganthan.com/okf-generator](https://suganthan.com/okf-generator/) — wklej adres URL lub mapę witryny, przeszuka do 100 stron, zwróci pakiet do pobrania. Rysuje również wynikowy wykres strony, dzięki czemu można wykryć odłączone strony przed publikacją.

### 2. Wtyczka WordPress (oczekuje na zatwierdzenie wp.org)

Wtyczka Suganthana (bezpłatna, GPL, oczekująca na zatwierdzenie wp.org w momencie pisania tego tekstu) instaluje się w ciągu minuty, udostępnia pakiet w `/okf/` i przebudowuje przy każdej publikacji lub edycji, dzięki czemu pozostaje zsynchronizowana. Bezpośredni link do pobrania znajduje się w [jego poście na blogu](https://suganthan.com/blog/open-knowledge-format/). Wymaga WordPressa 6.0+ i PHP 7.4+. Tylko do odczytu — nigdy nie edytuje postów ani ustawień.

### 3. Ręcznie

Praktyczne tylko dla kilku stron. Każdy post staje się plikiem Markdown z treścią, którą ręcznie łączysz. Uciążliwe dla całej witryny.

## Hosting i odkrywanie
Podaj pakiet w `yoursite.com/okf/`, zaczynając od `yoursite.com/okf/index.md`:

- **Hosty statyczne / Cloudflare**: przeciągnij i upuść
- **WordPress**: wtyczka Suganthan obsługuje serwowanie
- **Statyczne witryny z niestandardowymi ścieżkami**: prześlij katalog do `/okf/`
- **Zamknięte platformy (Wix, Squarespace, większość kreatorów stron)**: zazwyczaj nie można udostępniać plików w niestandardowych ścieżkach — całkowicie pomiń OKF

Po udostępnieniu dodaj linię do `llms.txt` wskazującą na pakiet, aby agenci czytający `llms.txt` (dziś) mogli odkryć pakiet (później).

## Kiedy pominąć

- Witryna ma mniej niż 10 stron — koszty ogólne przekraczają opłacalność
- Witryna znajduje się na zamkniętej platformie, która nie pozwala na niestandardowe ścieżki
- Nie utrzymujesz `llms.txt`, znaczników schematu ani innych plików do odczytu maszynowego (OKF łączy się z nimi; sam to nic nie robi)
- Nie możesz przeznaczyć 30 minut na kwartał na odświeżenie pakietu w miarę zmiany zawartości

## Co śledzić

OKF ma wersję 0.1 i ma kilka tygodni. Warto śledzić, nie warto mieć obsesji na punkcie:

- Czy Google ogłasza obsługę OKF w AI Overviews/Grafie wiedzy (obecnie brak sygnału)
- Czy wyszukiwarki inne niż Google (ChatGPT, Perplexity, Claude) ogłaszają odczyt OKF
- Czy specyfikacja zostanie przeniesiona do wersji 1.0 (istotne zmiany są możliwe w wersji <1.0)
- Czy Knowledge Catalog dodaje publiczne punkty końcowe pozyskiwania
- Sygnały przyjęcia — wyszukaj w GitHubie `okf/index.md`, aby zobaczyć, kto dostarcza pakiety