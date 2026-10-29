# Przewodnik po systemach headless CMS

Podręcznik do wyboru, modelowania i wdrażania systemu headless CMS dla treści marketingowych.

## Kiedy używać tego odniesienia

Użyj tej opcji podczas wybierania systemu CMS do nowego projektu, projektowania modeli treści dla witryn marketingowych, konfigurowania przepływów pracy redakcyjnej lub łączenia treści CMS ze stronami generowanymi programowo.

---

## Headless CMS a tradycyjny CMS

Headless CMS oddziela zarządzanie treścią od prezentacji. Treść jest przechowywana w ustrukturyzowanym backendie i dostarczana poprzez API do dowolnego frontendu.

### Kiedy headless CMS ma sens

- Wiele frontendów korzysta z tej samej treści (internet, telefon komórkowy, e-mail)
- Programiści chcą pełnej kontroli nad stosem frontendu
- Treść należy ponownie wykorzystać w różnych kanałach
- Budujesz w nowoczesnym frameworku (Next.js, Remix, Astro)
- Marketing potrzebuje uporządkowanych bloków treści, które można ponownie wykorzystać

### Kiedy tradycyjne działa lepiej

- Mały zespół bez dedykowanych programistów
- Prosty blog lub witryna wizytówkowa
- Edycja WYSIWYG jest bezwzględnym wymogiem
- Budżet jest napięty, a WordPress/Webflow spełnia swoje zadanie

### Lista kontrolna decyzji

| Czynnik | Headless | Tradycyjny |
|--------|----------|------------|
| Dostawa wielokanałowa | Tak | ograniczona |
| Kontrola programisty | Pełny | Ograniczone |
| Redakcja nietechniczna | Wymaga konfiguracji | Wbudowany |
| Czas do uruchomienia | Dłużej | Szybciej |
| Ponowne wykorzystanie treści | Natywne | Ręczne |
| Elastyczność hostingu | Dowolny frontend | Zależne od platformy |

---
## Modelowanie treści dla marketingu

### Podstawowe zasady

1. **Myśl typami, a nie stronami.** „Strona docelowa” to typ treści z polami, a nie plik HTML. Dzięki temu możesz ponownie używać komponentów na różnych stronach.
2. **Oddziel treść od prezentacji.** Przechowuj tekst nagłówka, a nie nagłówek ze stylem. Prezentacja należy do frontendu.
3. **Projektuj z myślą o ponownym użyciu.** Jeśli referencje pojawiają się na 5 stronach, utwórz typ Referencji i odwołuj się do niego – nie duplikuj.
4. **Trzymaj modele płaskie.** Głęboko zagnieżdżone struktury są trudne do sprawdzania i utrzymywania. Preferuj odniesienia zamiast zagnieżdżania.

### Typowe typy treści marketingowych

| Typ | Kluczowe pola | Notatki |
|------|-----------|-------|
| **Strona docelowa** | title, slug, hero, sections[], seo | Sekcje modułowe zapewniające elastyczność |
| **Post na blogu** | title, slug, body, author, category, tags, publishedAt, seo | Tekst sformatowany lub treść w formacie Portable Text |
| **Studium przypadku** | title, customer, challenge, solution, results, metrics[], logo | Link do powiązanych produktów/funkcji |
| **Referencja** | quote, author, role, company, avatar, rating | Odniesienia ze stron docelowych |
| **Często zadawane pytania** | question, answer, category | Grupuj według kategorii dla stron generowanych programowo |
| **Autor** | name, bio, avatar, social links | Odniesienia z wpisów na blogu |
| **Blok CTA** | heading, body, buttonText, buttonUrl, variant | Możliwość wielokrotnego użytku na stronach |

### Lista kontrolna pól SEO
Każdy typ zawartości na poziomie strony wymaga:

- `metaTitle` — 50-60 znaków
- `metaDescription` — 150-160 znaków
- `ogImage` — podgląd społecznościowy 1200x630px
- `slug` — segment ścieżki URL
- `canonicalUrl` — opcjonalne nadpisanie
- `noIndex` — wartość logiczna wykluczająca z wyszukiwania
- `structuredData` — opcjonalne nadpisanie JSON-LD

---

## Procesy redakcyjne

### Wersja robocza → Recenzja → Cykl publikowania

1. **Szkic** — Autor tworzy lub edytuje treść
2. **Recenzja** — Redaktor sprawdza poprawność, styl marki i SEO
3. **Zatwierdź** — Interesariusz się podpisuje
4. **Harmonogram** — Ustaw datę/godzinę publikacji
5. **Opublikuj** — Treść jest udostępniana za pośrednictwem interfejsu API

### Podgląd interfejsów API

Wszystkie główne platformy headless CMS obsługują podglądy wersji roboczej:

- **Sanity**: Podgląd w czasie rzeczywistym za pomocą `useLiveQuery` lub narzędzia Presentation
- **Contentful**: Podgląd API (`preview.contentful.com`) z oddzielnym tokenem dostępu
- **Strapi**: System tworzenia wersji roboczych i publikowania z parametrem zapytania `status=draft` (wersja 5; zastępuje `publicationState` wersji 4)

Skonfiguruj ścieżkę podglądu w swoim interfejsie (np. `/api/preview`), która uwierzytelnia i renderuje wersję roboczą treści.

### Role i uprawnienia

| Rola | Może tworzyć | Można edytować | Może publikować | Można usunąć |
|------|:--------------:|:------------:|:----------:|:----------:|
| Autor | Tak | Własny | Nie | Własne szkice |
| Redaktor | Tak | Wszystko | Tak | Szkice |
| Administrator | Tak | Wszystko | Tak | Wszystko |

Dokładne modele uprawnień różnią się w zależności od platformy. Sanity korzysta z dostępu opartego na rolach. Contentful ma role na poziomie przestrzeni. Strapi ma granulowany RBAC.

---
## Porównanie platform

| Funkcja | Sanity | Contentful | Strapi |
|--------|--------|------------|-------|
| Hosting | Chmura (zarządzana) | Chmura (zarządzana) | Samodzielnie lub w chmurze |
| Język zapytań | GROQ | REST / GraphQL | REST / GraphQL |
| Bezpłatny poziom | Hojny | ograniczona | Otwarte oprogramowanie (bezpłatne) |
| Współpraca w czasie rzeczywistym | Tak (wbudowany) | ograniczona | Nie |
| Najlepsze dla | Elastyczność programisty | Przedsiębiorstwo wielojęzyczne | Budżet / własny hosting |
| Modelowanie treści | Schemat jako kod | Interfejs sieciowy | Interfejs sieciowy lub kod |
| Obsługa multimediów | Wbudowany DAM | Wbudowany | Oparte na wtyczkach |

### Sanity

**Mocne strony**: Język zapytań GROQ jest potężny i elastyczny. Schemat zdefiniowany w kodzie (kontrolowany wersją). Wspólna edycja w czasie rzeczywistym. Portable Text do treści sformatowanych. Obfity darmowy poziom.

**Rozważania**: Bardziej stroma krzywa uczenia się dla osób niebędących programistami. Dostosowywanie studia wymaga znajomości React. Uzależnienie od dostawcy przy zapytaniach GROQ.

**Dopasowanie marketingowe**: Najlepiej, gdy programiści i marketerzy ściśle współpracują. Odpowiedni dla witryn o dużej zawartości treści i złożonych modelach.

### Contentful

**Mocne strony**: Dojrzała platforma dla przedsiębiorstw. Doskonała obsługa wielu wersji językowo-regionalnych. Silny ekosystem integracji. Możliwość komponowania treści w programie Studio. Dobrze udokumentowane interfejsy API.

**Uwagi**: Ceny różnią się w zależności od typów treści i wersji językowo-regionalnych. Dwa oddzielne interfejsy API (dostawa i zarządzanie). Limity zapytań mogą być rygorystyczne w przypadku niższych planów.
**Dopasowanie marketingowe**: najlepsze dla przedsiębiorstw mających potrzeby w zakresie treści obejmujących wiele rynków. Dobre, gdy potrzebujesz sprawdzonej niezawodności dostawcy.

### Strapi

**Mocne strony**: Open source, opcja samodzielnego hostowania. Pełna kontrola nad danymi. Brak opłat za stanowisko. Konfigurowalny panel administracyjny. Ekosystem wtyczek. Domyślnie REST, GraphQL poprzez wtyczkę.

**Uwagi**: Samodzielny hosting oznacza, że ​​zajmujesz się infrastrukturą. Mniejszy ekosystem niż Sanity/Contentful. Migracja V5 może być znacząca z V4.

**Dopasowanie marketingowe**: najlepsze dla zespołów z możliwością DevOps, które chcą pełnej kontroli i braku uzależnienia od dostawcy. Dobry do projektów uwzględniających budżet.

### Inne warte poznania

- **Hygraph** — natywny dla GraphQL, odpowiedni do federacji i treści z wielu źródeł
- **Keystatic** — Oparty na Git, dobry do hybrydowych przepływów pracy z treścią programisty
- **Payload** — oparty na TypeScript, hostowany samodzielnie i konfigurowany kodem jak Sanity
- **Builder.io** — Edytor wizualny z bezgłowym backendem, dobry dla nietechnicznych marketerów
- **Prismic** — modelowanie treści w oparciu o moduły Slice, silna integracja z Next.js

---

## Integracja z umiejętnościami marketingowymi

### Programmatic SEO

Użyj CMS jako źródła danych dla stron generowanych programowo. Przechowuj uporządkowane dane (FAQ, porównania, strony miast) jako typy treści i generuj strony na podstawie zapytań. Zobacz umiejętność **programmatic-seo**.

### Copywriting
Modele treści CMS wymuszają spójną strukturę. Zdefiniuj pola pasujące do ram tekstu (nagłówek, podnagłówek, społeczny dowód słuszności, CTA). Zobacz umiejętność **copywriting**.

### Architektura witryny

Struktura adresu URL, hierarchia nawigacji i linki wewnętrzne zależą od tego, jak treść jest zorganizowana w systemie CMS. Zaplanuj wspólnie model treści i architekturę witryny. Zobacz umiejętność **site-architecture**.

### Sekwencje e-maili

Przeciągnij treść CMS do szablonów wiadomości e-mail, aby zapewnić spójną komunikację w Internecie i e-mailu. Studia przypadków, referencje i wpisy na blogach mogą stanowić źródło inspiracji w wiadomościach e-mail. Zobacz umiejętność **emails**.

---

## Lista kontrolna wdrożenia

- [ ] Zdefiniuj typy treści w oparciu o typy stron i bloki wielokrotnego użytku
- [ ] Dodaj pola SEO do każdego typu treści na poziomie strony
- [ ] Skonfiguruj tryb podglądu/roboczy w swoim interfejsie użytkownika
- [ ] Skonfiguruj role i uprawnienia dla swojego zespołu
- [ ] Utwórz przykładową treść dla każdego typu przed zbudowaniem frontendu
- [ ] Skonfiguruj powiadomienia webhooka o zmianach treści (wyzwalacze przebudowy)
- [ ] Udokumentuj wytyczne dotyczące treści dla redaktorów (opisy pól, limity znaków)
- [ ] Testuj wydajność dostarczania treści (CDN, buforowanie, ISR)
- [ ] Zaplanuj strategię migracji w przypadku przejścia z istniejącego CMS

---

## Odpowiednie przewodniki dotyczące integracji

- [Sanity](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/integrations/sanity.md) — zapytania GROQ, mutacje, CLI
- [Contentful](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/integrations/contentful.md) — Interfejsy API dostarczania/zarządzania, publikowanie
- [Strapi](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/integrations/strapi.md) — REST CRUD, filtry, API dokumentów