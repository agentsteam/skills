# AI SEO według typu treści

Wskazówki taktyczne dotyczące optymalizacji określonych typów treści pod kątem cytowań w wyszukiwarce AI. Te taktyki działają w przypadku silników AI innych niż Google (ChatGPT, Claude, Perplexity, Copilot) i nie szkodzą Google AI Overviews ani trybowi AI.

Informacje na temat strategii przekrojowej można znaleźć w [SKILL.md](../SKILL.md).

---

## Strony produktów SaaS

**Cel:** być cytowanym w „Co to jest [kategoria]?” i „Najlepsza [kategoria]”. (Cytowanie jest tutaj realistycznym celem; bycie *poleconym* w odpowiedzi zależy od konsensusu poza witryną — patrz [citations-vs-recommendations.md](citations-vs-recommendations.md).)

**Optymalizuj:**
- Przejrzysty opis produktu w pierwszym akapicie (co robi, dla kogo jest przeznaczony)
- Tabele porównawcze funkcji (ty kontra kategoria, nie tylko konkurenci)
- Konkretne wskaźniki („przetwarza 10 000 transakcji na sekundę”, a nie „niesamowicie szybko”)
- Liczba klientów lub dowód społeczny z liczbami
- Przejrzystość cen (AI cytuje strony z widocznymi cenami) - dodaj plik `/pricing.md`, aby agenci AI mogli analizować Twoje plany bez renderowania strony (patrz „Pliki do odczytu maszynowego” w głównej umiejętności)
- Sekcja FAQ zawierająca najczęściej zadawane pytania kupujących

---

## Treść bloga

**Cel:** być cytowanym jako wiarygodne źródło tematów poruszanych w Twojej przestrzeni.

**Optymalizuj:**
- Jedno jasne zapytanie docelowe na post (dopasuj nagłówek do zapytania)
- Definicja w pierwszym akapicie dla zapytań „Co to jest”.
- Oryginalne dane, badania lub cytaty ekspertów
- Widoczna data „ostatniej aktualizacji”.
- Biografia autora z odpowiednimi kwalifikacjami
- Wewnętrzne linki do powiązanych stron produktów/funkcji

---

## Strony porównawcze/alternatywne

**Cel:** Uzyskanie cytowań w zapytaniach „[X] kontra [Y]” i „Najlepsze [X] alternatywy”.

**Optymalizuj:**
- Ustrukturyzowane tabele porównawcze (nie tylko proza)
- Uczciwe i zrównoważone (AI karze oczywiście stronnicze porównania)
- Określone kryteria z ocenami lub wynikami
- Zaktualizowano dane dotyczące cen i funkcji
- Wskaż umiejętność `competitors` niezbędną do tworzenia tych stron

---

## Strony branżowe/segmentowe

**Cel:** Uzyskaj rekomendację, gdy w prompcie zostanie podana branża lub wielkość firmy („oprogramowanie do marketingu e-mailowego dla handlu elektronicznego”, „oprogramowanie do zapytań ofertowych dla instytucji rządowych”, „przedsiębiorstwo [kategoria]”). Modele coraz częściej dzielą marki na segmenty i personalizują odpowiedzi, więc ogólna strona może przegrać ze stroną segmentową konkurencji.

**Optymalizuj:**
- Jedna strona na każdą podstawową branżę lub segment, który faktycznie obsługujesz, z przepływami pracy specyficznymi dla branży, integracjami, zgodnością i weryfikacją klienta
- Zacznij od podstawowych segmentów. Wiele stron jest w porządku, jeśli każda dodaje rzeczywistą wartość specyficzną dla segmentu; strony z szablonami, które zmieniają tylko nazwę branży, są celem polityki skalowanej treści (patrz umiejętność `programmatic-seo`)
- Dopasuj język segmentów używany w profilach stron trzecich (zobacz [positioning-and-consensus.md](positioning-and-consensus.md))

---

## Dokumentacja/treść pomocy

**Cel:** Uzyskanie cytowań w zapytaniach „Jak [X] z [Twoim produktem]”.
**Optymalizuj:**
- Format krok po kroku z listami numerowanymi
- Przykłady kodu, jeśli ma to zastosowanie
- Znacznik schematu HowTo
- Zrzuty ekranu z opisowym tekstem alternatywnym
- Jasne warunki wstępne i oczekiwane rezultaty

---

## Firma lokalna / e-commerce (podkreślenie Google)

Funkcje sztucznej inteligencji Google pobierają dane z kanałów produktów i profili biznesowych w przypadku zapytań lokalnych i e-commerce. Optymalizuj:

- **Kanały Merchant Center** są na bieżąco aktualizowane i zawierają dokładne informacje o asortymencie, cenach i atrybutach
- **Profil Firmy w Google** wraz z godzinami pracy, usługami, zdjęciami, postami i odpowiedziami na pytania i odpowiedzi
- **Recenzje** — najnowsze + wystarczająca ilość; odpowiadaj na recenzje, aby zasygnalizować aktywne zarządzanie
- **Schemat obszaru usług** dla usług lokalnych
- **Agent biznesowy** (jeśli jest dostępny) do rozmów z klientami