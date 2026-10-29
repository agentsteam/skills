# Poprawa pozycji w wynikach

Audyty wykrywają, co jest zepsute. To odniesienie obejmuje następny krok: przeniesienie stron, które już mają pozycje w rankingu, na pierwszą stronę wyników oraz publikowanie nowych stron z dobrym startem. Jedno i drugie jest tańsze niż wygranie zapytania z niczego, ponieważ Google już zdecydował, że dana witryna jest istotna.

## Znajdź kandydatów

W Search Console pobierz pary zapytania i strony z ostatnich 28 dni (porównaj z poprzednim okresem, aby odfiltrować skoki):

| Kategoria | Filtr | Typ poprawki |
|--------|--------|---------|
| **Blisko pierwszej strony** | Średnia pozycja 8–20, wyświetlenia powyżej progu dopasowanego do witryny (często ponad 100/miesiąc) | Treść i linki |
| **Słaba klikalność** | Pozycja 1–5, CTR znacznie poniżej innych stron na podobnych pozycjach | Tytuł i metaopis |
| **U góry** | Pozycja 4–7 w zapytaniu o przychody | Treść, linki i format fragmentu wyróżnionego |

Ustal priorytety według wartości biznesowej: zapytanie na 11. pozycji, które prowadzi do demonstracji produktu, ma większą wartość niż termin słownikowy na 9. pozycji z trzykrotnie większą liczbą wyświetleń.

Zanim dotkniesz strony, sprawdź, czy nie występuje **kanibalizacja**: jeśli dwie z Twoich stron zajmują pozycję w wynikach tego samego zapytania, pozycje często zmieniają się między nimi i żadna z nich nie rośnie. Wybierz jednego właściciela, połącz z nim przydatne części drugiego i przekieruj.

## Diagnozuj na podstawie trzech najlepszych

Otwórz trzy wyniki nad sobą i dla każdego z nich zapisz konkretny powód, dla którego wygrywa. Zwykle jeden z nich:
- **Dopasowanie intencji.** Odpowiadają na pytanie zadane przez osobę wyszukującą; Twoja strona odpowiada na sąsiednią. Zapytanie o cenę, na które odpowiedź zawiera stronę z funkcjami, przegrywa.
- **Brakująca sekcja.** Obejmują one pytanie dodatkowe, które pominąłeś. Pole „Ludzie też pytają” i podtytuły w najwyższych wynikach pokazują, czego oczekują wyszukujący.
- **Świeżość.** Ich fakty, zrzuty ekranu lub rok są aktualne, a Twoje nie.
- **Format.** Zawierają tabelę, kroki lub narzędzie, których wymaga zapytanie.
- **Linki.** Linki do nich znajdują się na większej liczbie silniejszych stron, wewnątrz i na zewnątrz witryny.

Jeśli nie możesz podać powodu, nie zgaduj, przepisując. Luka dotyczy raczej autorytetu niż treści na stronie, a rozwiązaniem są linki (**umiejętność link-building**, uruchamiana co tydzień jako pętla `backlink-prospecting` w `marketing-loops`), a nie treść.

## Wprowadź najmniejszą zmianę, która wypełni lukę

- **Odpowiedz na pytanie w pierwszych dwóch zdaniach**, a następnie rozwiń. Jest to również fragment, który często cytują AI Overviews i asystenci.
- **Dodaj brakującą sekcję**, a nie przepisywanie całej strony. Strony, które już uzyskały ranking, niosą ze sobą sygnały, które warto zachować.
- **Wpisz zapytanie w tytule i H1**, jeśli brzmi naturalnie. Jeśli tytuł jest już wyrównany, zostaw go.
- **Dodaj linki wewnętrzne do strony** z najsilniejszych powiązanych stron, z tekstem zakotwiczenia opisującym cel. Jest to często największa pojedyncza dźwignia i najbardziej zaniedbywana.
- **Odśwież to, co nieaktualne**: fakty, zrzuty ekranu, rok, niedziałające linki.
- **Tylko w przypadku słabej klikalności** zmień tytuł i metaopis i nic więcej, aby można było przypisać wynik. Wzorce w [title-tags.md](title-tags.md).

Zapisz pozycję początkową, wyświetlenia i CTR, a następnie odczekaj 3–4 tygodnie, zanim ponownie ocenisz lub zmienisz stronę. Rankingi wymagają czasu po edycji, a nałożone na siebie zmiany sprawiają, że nie wiadomo, co zadziałało.

Jeśli dwie rundy nic nie zmienią, przestań edytować. Strona jest prawdopodobnie ograniczona przez niezgodność intencji (Google chce innego rodzaju strony) lub niewystarczający autorytet, a dalsze prace na stronie również nie rozwiążą problemu.

## Publikacja nowej strony

Nowa strona powinna zostać uruchomiona ze wszystkim, co trzeba znaleźć, aby nie pozostawała miesiącami jako sierota:

- [ ] Linki wewnętrzne z co najmniej trzech odpowiednich istniejących stron, z opisowymi kotwicami
- [ ] Unikalny tytuł i metaopis pasujący do docelowego zapytania
- [ ] Jeden H1, zgodny z tytułem
- [ ] Adres kanoniczny wskazujący na samą stronę
- [ ] Dodano do mapy witryny XML
- [ ] Dane strukturalne, jeśli obsługuje je typ strony (patrz `schema`)
- [ ] Główna treść obecna w renderowanym przez serwer HTML, nie tylko po uruchomieniu JavaScript
- [ ] Indeksowalne: brak przypadkowych `noindex`, niezablokowane w pliku robots.txt
- [ ] Powiązany z właściwą ścieżką konwersji (patrz `cro`)
Po publikacji poproś o jednokrotne zindeksowanie w Search Console. Ponowne żądanie niczego nie przyspiesza. Jeśli strona nie zostanie zaindeksowana po kilku tygodniach, zamiast przesyłać ją ponownie, sprawdź przyczyny w sekcji Indeksacja w ramach audytu.

## Uruchom go zgodnie z harmonogramem

Pętla striking-distance push w `marketing-loops` działa co tydzień ze stanem, okresami przerwy i regułą zatrzymania. Przepis operatora SEO w tej samej umiejętności łączy go z innymi pętlami SEO.