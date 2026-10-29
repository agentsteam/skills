# Wielojęzyczne powierzchnie handlowe AEO i AI

Dwa rozszerzenia podstawowego przepływu pracy, które zawodzą w przewidywalny sposób: tłumaczenie angielskiego planu AEO na inne rynki i inwestowanie w powierzchnie zakupowe AI w przypadku produktów, które te powierzchnie rzadko pokazują.

## Wielojęzyczny i wielorynkowy AEO

Język zapytania zmienia to, które źródła są cytowane. Analiza Profound obejmująca 3,25 miliarda cytowań w siedmiu modelach i 14 krajach, z wykorzystaniem promptów w języku ojczystym, wykazała, że ​​zróżnicowanie cytowań i wskaźniki źródeł społecznościowych zmieniły się znacząco w zależności od języka zapytań (Profound, kwiecień 2026). Rynki hiszpańskojęzyczne wyglądały podobnie w różnych krajach, więc język czasami miał większe znaczenie niż położenie geograficzne. Platformy również się różniły: Google AI Overviews opierały się na różnorodnym zestawie lokalnych źródeł społecznościowych, podczas gdy cytaty społecznościowe ChatGPT skupiały się na Reddicie. Profound sprzedaje śledzenie widoczności AI; traktuj je jako badania dostawców i sprawdzaj w swojej własnej kategorii.

### Lista kontrolna

1. **Traktuj język i kraj jako osobne wymiary.** Hiszpański w Meksyku, hiszpański w Hiszpanii i angielski w Meksyku to trzy konfiguracje.
2. **Twórz prompty na podstawie lokalnego popytu w danym języku.** Korzystaj z badań lokalnych klientów, lokalnych wyszukiwanych haseł i rodzimych użytkowników języka. Nie tłumacz słowo w słowo angielskiej listy promptów; nazwy kategorii, jednostki i kryteria decyzyjne różnią się.
3. **Uruchom każdy monit w każdym silniku docelowym** i sklasyfikuj cytowane źródła: własne, konkurencyjne, zarobione artykuły redakcyjne, instytucjonalne, społecznościowe, rynek lub katalog (taksonomia w [citations-vs-recommendations.md](citations-vs-recommendations.md)).
4. **Znajdź lokalny rynek źródłowy.** Zwróć uwagę, którzy lokalni wydawcy, katalogi, witryny z recenzjami, społeczności i autorytatywne źródła pojawiają się w poszczególnych wyszukiwarkach. Nie zakładaj, że Reddit, YouTube, LinkedIn czy globalny wydawca mają wszędzie jednakowe znaczenie.
5. **Sprawdź lokalne fakty.** Ceny i waluta, dostępność, zasady, twierdzenia prawne, godziny wsparcia i podmioty lokalne. Błędna cena lokalna jest błędem krytycznym (patrz [answer-accuracy.md](answer-accuracy.md)).
6. **Rozróżnij trzy typy luk.** Luka w tłumaczeniu oznacza, że ​​strona istnieje, ale nie jest w tym języku. Luka informacyjna oznacza, że ​​ta informacja nie istnieje nigdzie lokalnie. Luka w encji oznacza, że ​​profile lokalne opisują Cię niespójnie.
7. **Polecaj kanały lokalne tylko wtedy, gdy obsługuje je lokalny zestaw cytowań.**
8. **Przypisz osobę do weryfikacji językowej i osobę odpowiedzialną za aktualność** dla każdej zlokalizowanej strony.
9. **Raportuj osobno dla każdego języka, kraju i silnika** przed agregacją wyników.

## Powierzchnie handlowe AI
Funkcje zakupowe AI (zakupy ChatGPT, wyniki produktów w trybie Google AI, agent Meta's Muse i podobne) warto inwestować tylko w kategorie, które faktycznie wyświetlają. W testach Profound kategoria produktu była silniejszym czynnikiem wyzwalającym zakupy ChatGPT niż sformułowania dotyczące zamiaru zakupu: fizyczne produkty konsumenckie aktywowały ją znacznie częściej niż oprogramowanie, usługi, podróże lub produkty finansowe (Profound, marzec 2026; obserwacyjne, a OpenAI nie opublikowało reguł wyzwalających). Sprawdź aktualne wymagania dotyczące sprzedawców i plików danych w dokumentacji każdej platformy.

### Najpierw sprawdź dopasowanie

Klasyfikuj ofertę przed przystąpieniem do audytu czegokolwiek:

| Oferta | Typowe dopasowanie |
|---|---|
| Produkt konsumencki nadający się do wysyłki, materiały eksploatacyjne | Mocny; audyt w całości |
| Duży sprzęt lub pojazdy | Testuj wąsko |
| Oprogramowanie, produkty cyfrowe, usługi, podróże, produkty finansowe | Zwykle słaby; zamiast tego włóż wysiłek w zwykłe zalecenia AI |
| Oferty wyłącznie lokalne | Skoncentruj się na lokalnych powierzchniach i profilu działalności |

Następnie przetestuj, korzystając z powtarzających się reprezentatywnych promptów. Karty i oferty różnią się w zależności od serii, więc jedna karuzela nie stanowi rankingu.

### Audyt danych (gdy dopasowanie jest rzeczywiste)

- Kanoniczny tytuł i opis, marka i identyfikatory (GTIN, MPN)
- Kategoria, atrybuty, warianty, rozmiary, kolory i kompatybilność
- Obrazy
- Cena, waluta, status sprzedaży i dostępność wraz z szybkością rozprzestrzeniania się zmian
- Zasady dotyczące wysyłki, zwrotów i sprzedawców
- Recenzje i oceny od prawdziwych klientów

Agenci dokonujący zakupów mogą również bezpośrednio korzystać z katalogów handlowych. Muse na przykład przeszukuje katalog produktów Shopify, więc dane katalogu sprzedawcy Shopify są częścią audytu.

Porównaj plik danych, stronę produktu, dane strukturalne, rejestry sprzedawców i wykazy na rynku pod kątem konfliktów. Napraw błędne dane przed rozpoczęciem jakichkolwiek prac redakcyjnych. Śledź oddzielnie trzy wyniki: czy produkt jest uwzględniony, czy jesteś głównym sprzedawcą lub ofertą i czy pojawiasz się wśród wszystkich ofert.

Nigdy nie twórz recenzji, ocen, dostępności ani rabatów. Informacje o protokołach po stronie agenta (Merchant Center, UCP) znajdziesz w sekcji Doświadczenia agenta w SKILL.md.

---

*Pochodzenie Ram: rynkowa lista kontrolna i kontrola dopasowania handlowego zaadaptowane (ponownie wyrażone i zrestrukturyzowane) na podstawie umiejętności international-aeo-strategist i ai-commerce-readiness-auditor firmy Profound, posiadającego licencję MIT, oraz ich badań (marzec i kwiecień 2026 r.), przypisane.*