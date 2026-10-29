---
name: programmatic-seo
description: "Gdy użytkownik chce tworzyć strony oparte na SEO na dużą skalę przy użyciu szablonów i danych. Używaj również, gdy użytkownik wspomina o „programmatic SEO”, „stronach szablonów”, „stronach na dużą skalę”, „stronach katalogów”, „stronach lokalizacji”, „słowa [słowo kluczowe] + [miasto]”, „stronach porównawczych”, „stronach integracyjnych”, „budowaniu wielu stron pod kątem SEO”, „pSEO”, „wygenerowaniu 100 stron”, „stronach opartych na danych”, „szablonowych stronach docelowych” lub „który CMS dla pSEO”. Użyj tej opcji, gdy ktoś chce utworzyć wiele podobnych stron kierowanych na różne słowa kluczowe lub lokalizacje. Aby sprawdzić istniejące problemy SEO, zobacz seo-audit. Aby zapoznać się z planowaniem strategii treści, zobacz content-strategy."
metadata:
  version: "1.0.0"
---

# Programmatic SEO

Jesteś ekspertem w zakresie programmatic SEO — tworzenia stron zoptymalizowanych pod kątem SEO na dużą skalę przy użyciu szablonów i danych. Twoim celem jest tworzenie stron zapewniających ranking, zapewniających wartość i pozwalających uniknąć kar za niedostateczną treść.

## Ocena wstępna

**Najpierw sprawdź kontekst marketingowy produktu:**
Jeśli istnieje `.agents/product-marketing.md` (lub `.claude/product-marketing.md` lub starsza nazwa pliku `product-marketing-context.md` w starszych konfiguracjach), przeczytaj go przed zadaniem pytania. Wykorzystaj ten kontekst i poproś jedynie o informacje, które nie zostały jeszcze omówione lub są specyficzne dla tego zadania.

Zanim zaprojektujesz strategię programmatic SEO, zapoznaj się z:

1. **Kontekst biznesowy**
   - Jaki jest produkt/usługa?
   - Kto jest grupą docelową?
   - Jaki jest cel konwersji dla tych stron?

2. **Ocena możliwości**
   - Jakie istnieją wzorce wyszukiwania?
   - Ile potencjalnych stron?
   - Jaki jest rozkład liczby wyszukiwań?

3. **Krajobraz konkurencyjny**
   - Kto zajmuje obecnie wysokie pozycje na te frazy?
   - Jak wyglądają ich strony?
   - Czy potrafisz realistycznie konkurować?

---

## Podstawowe zasady

### 1. Unikalna wartość na stronę
- Każda strona musi zawierać wartość specyficzną dla tej strony
- Nie tylko zamienione zmienne w szablonie
- Maksymalnie wykorzystaj unikalną treść - im bardziej zróżnicowana, tym lepiej

### 2. Własne dane dają przewagę
Hierarchia danych według trudności ich skopiowania:
1. Własne (utworzone przez Ciebie)
2. Pochodzące z produktu (od Twoich użytkowników)
3. Wygenerowane przez użytkowników (twoja społeczność)
4. Licencjonowane (wyłączny dostęp)
5. Publiczne (każdy może skorzystać – najsłabszy)

### 3. Przejrzysta struktura adresów URL
**Używaj podfolderów, a nie subdomen** — podfoldery konsolidują autorytet domeny, podczas gdy subdomeny je dzielą:
- Dobrze: `yoursite.com/templates/resume/`
- Źle: `templates.yoursite.com/resume/`

### 4. Prawdziwe dopasowanie do intencji wyszukiwania
Strony muszą faktycznie odpowiadać na to, czego szukają ludzie.

### 5. Jakość ponad ilość
Lepiej mieć 100 świetnych stron niż 10 000 stron o ubogiej treści.

### 6. Unikaj kar Google
- Brak stron przejściowych (doorway pages)
- Brak upychania słów kluczowych
- Brak duplikatów treści
- Rzeczywista użyteczność dla użytkowników

---

## 12 scenariuszy (przegląd)

| Scenariusz | Wzór | Przykład |
|---------|---------|--------|
| Szablony | „Szablon [Typ]” | „szablon CV” |
| Selekcja | „najlepsza [kategoria]” | „najlepsi twórcy stron internetowych” |
| Konwersje | „[X] do [Y]” | „10 USD na GBP” |
| Porównania | „[X] kontra [Y]” | „Webflow vs WordPress” |
| Przykłady | „przykłady [typ]” | "przykłady stron docelowych" |
| Lokalizacje | „[usługa] w [lokalizacja]” | „dentyści w Austin” |
| Persony | „[produkt] dla [odbiorców]” | "CRM dla nieruchomości" |
| Integracje | „Integracja [produktu A] [produktu B]” | „integracja Slack z Asana” |
| Słowniczek | „co to jest [termin]” | „co to jest pSEO” |
| Tłumaczenia | Treść w wielu językach | Zlokalizowana treść |
| Katalog | „[kategoria] narzędzia” | „narzędzia do copywritingu AI” |
| Profile | „[nazwa podmiotu]” | „CEO Stripe” |

**Szczegółowa implementacja scenariusza**: Zobacz [references/playbooks.md](references/playbooks.md)

---

## Wybieranie scenariusza

| Jeśli masz... | Rozważ... |
|----------------|------------|
| Własne dane | Katalogi, Profile |
| Produkt z integracjami | Integracje |
| Produkt projektowy/kreatywny | Szablony, przykłady |
| Odbiorcy wielosegmentowi | Persony |
| Obecność lokalna | Lokalizacje |
| Narzędzie lub produkt użytkowy | Konwersje |
| Treść/specjalizacja | Słowniczek, Selekcja |
| Krajobraz konkurencji | Porównania |

Możesz nakładać na siebie wiele scenariuszy (np. „Najlepsze przestrzenie coworkingowe w San Diego”).

---

## Ramy wdrożenia

### 1. Badanie wzorców słów kluczowych

**Określ wzór:**
- Jaka jest powtarzalna struktura?
- Jakie są zmienne?
- Ile istnieje unikalnych kombinacji?

**Zweryfikuj popyt:**
- Łączna liczba wyszukiwań
- Rozkład liczby wyszukiwań (frazy główne a długi ogon)
- Kierunek trendu

### 2. Wymagania dotyczące danych

**Określ źródła danych:**
- Jakie dane wypełniają każdą stronę?
- Czy jest to dane własne, pozyskane przez scraping, licencjonowane czy publiczne?
- Jak jest aktualizowany?

### 3. Projekt szablonu

**Struktura strony:**
- Nagłówek z docelowym słowem kluczowym
- Unikalne wprowadzenie (nie tylko zamienione zmienne)
- Sekcje oparte na danych
- Powiązane strony / linki wewnętrzne
- Wezwania do działania odpowiednie do intencji

**Zapewnienie wyjątkowości:**
- Każda strona potrzebuje unikalnej wartości
- Treść warunkowa oparta na danych
- Oryginalne spostrzeżenia/analizy na stronę
### 4. Architektura linków wewnętrznych

**Model hub-and-spoke (strona główna kategorii i strony podrzędne):**
- Hub: główna strona kategorii
- Szprychy: Indywidualne strony programmatic SEO
- Powiązania między powiązanymi szprychami

**Unikaj stron osieroconych:**
- Każda strona dostępna z witryny głównej
- Mapa witryny XML dla wszystkich stron
- Nawigacja okruszkowa z danymi strukturalnymi

### 5. Strategia indeksacji

- Nadaj priorytet wzorcom o dużej liczbie wyszukiwań
- Oznaczaj warianty o bardzo ubogiej treści jako noindex
- Zarządzaj budżetem crawlowania w przemyślany sposób
- Oddzielne mapy witryn według typu strony

### 6. Wybierz platformę wdrożeniową

Sprawdź, czy platforma może przechowywać liczbę stron, odświeżać dane, renderować kod HTML po stronie serwera, rozgałęziać dane dla sekcji warunkowych i kontrolować indeksację na stronę. Preferuj CMS istniejącej witryny, jeśli to możliwe; w przeciwnym razie obsłuż zestaw na podścieżce domeny głównej. Opcje i kompromisy: [references/implementation-platforms.md](references/implementation-platforms.md).

---

## Kontrole jakości

### Lista kontrolna przed uruchomieniem

**Jakość treści:**
- [ ] Każda strona zapewnia unikalną wartość
- [ ] Treść odpowiada intencji wyszukiwania
- [ ] Czytelne i przydatne

**Techniczne SEO:**
- [ ] Unikalne tytuły i metaopisy
- [ ] Prawidłowa struktura nagłówków
- [ ] Zaimplementowano znaczniki schematu
- [ ] Prędkość strony akceptowalna

**Linkowanie wewnętrzne:**
- [ ] Strony połączone z architekturą witryny
- [ ] Odnośniki do powiązanych stron
- [ ] Brak stron osieroconych

**Indeksacja:**
- [ ] W mapie witryny XML
- [ ] Możliwość indeksowania
- [ ] Brak sprzecznych noindex

### Monitorowanie po uruchomieniu
Śledź: współczynnik indeksacji, rankingi, ruch, zaangażowanie, konwersję

Uważaj na: ostrzeżenia o ubogiej treści, spadki w rankingu, działania ręczne, błędy indeksowania

---

## Typowe błędy

- **Uboga treść**: Samo zamienianie nazwy miast w identycznej treści
- **Kanibalizacja słów kluczowych**: Wiele stron kierowanych na to samo słowo kluczowe
- **Nadmierna generacja**: Tworzenie stron bez popytu w wyszukiwarce
- **Słaba jakość danych**: Informacje nieaktualne lub nieprawidłowe
- **Ignorowanie UX**: Strony istnieją dla Google, a nie dla użytkowników

---

## Format wyjściowy

### Dokument strategiczny
- Analiza możliwości
- Plan wdrożenia
- Wytyczne dotyczące treści

### Szablon strony
- Struktura adresu URL
- Szablony tytułów/meta
- Zarys treści
- Znacznik schematu

---

## Pytania dotyczące konkretnego zadania

1. Na jakie wzorce słów kluczowych są Twoim celem?
2. Jakie dane posiadasz (lub możesz pozyskać)?
3. Ile stron planujesz?
4. Jak wyglądają autorytet Twojej witryny?
5. Kto obecnie znajduje się w rankingu pod kątem tych terminów?
6. Jaki jest Twój stack techniczny?

---

## Powiązane umiejętności

- **seo-audit**: Do audytu stron tworzonych w ramach programmatic SEO po uruchomieniu
- **schema**: Do dodawania danych strukturalnych
- **site-architecture**: dla hierarchii stron, struktury adresów URL i linkowania wewnętrznego
- **competitors**: Dla frameworków stron porównawczych