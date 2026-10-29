# Strony lokalizacji i pomiary

Użyj tej opcji, jeśli żądanie obejmuje strony lokalne, schemat lub raporty dotyczące wydajności.

## Treść strony, która pomaga lokalnemu klientowi

W przypadku rzeczywistej lokalizacji skierowanej do klienta podaj dokładną lokalizację/dane kontaktowe, godziny otwarcia, dostępne tam usługi, linki do rezerwacji/połączenia, wskazówki dojazdu/parkowania, jeśli są znane, dowody dotyczące personelu lub lokalizacji oraz przydatne informacje o okolicy/usługach. Połącz go z indeksem lokalizacji i odpowiednimi stronami usług.

W przypadku usług bez biura wyjaśnij rzeczywistą dostępność, ograniczenia, zasady dotyczące podróży lub wezwań, odpowiednie przykłady pracy lokalnej, jeśli są dostępne, oraz jasną ścieżkę zapytania. Powiedz, że jest to obszar usług. Nie podawaj fałszywego adresu ani nie sugeruj oddziału, w którym pracuje personel.

Przykładowa decyzja: hydraulik ma jedną bazę operacyjną i obsługuje dwie pobliskie miejscowości. Jedna rzetelna strona opisująca zasięg może wystarczyć. Odrębne strony miast są uzasadnione jedynie dodatkowymi przydatnymi informacjami lub dowodami; żadne z miast nie zasługuje automatycznie na kolejny profil działalności.

Przed skalowaniem potwierdź stabilne źródło danych i znaczące różnice między stronami. Sprawdź aktualne [zasady dotyczące nadużywania stron przejściowych](https://developers.google.com/search/docs/essentials/spam-policies#doorway-abuse). Skieruj uzasadnione szablony do programmatic-seo i hierarchię do site-architecture; konsoliduj strony, gdy proponowane warianty nie wnoszą żadnej wartości.

## Lokalne dane strukturalne
Użyj najdokładniejszego podtypu LocalBusiness i stabilnego identyfikatora dla każdej rzeczywistej lokalizacji. Dopasuj widoczne fakty na stronie; w stosownych przypadkach połącz adres URL lokalizacji, numer telefonu publicznego, godziny otwarcia i współrzędne fizyczne. Nie oznaczaj miast usługowych jako wymyślonych oddziałów ani nie publikuj ukrytego adresu zamieszkania za pośrednictwem JSON-LD.

Ważna różnica: Schema.org może opisać firmę, nie spełniając wymagań Google dotyczących wyników z elementami rozszerzonymi. [Dokumentacja firmy Google](https://developers.google.com/search/docs/appearance/structured-data/local-business) wymaga adresu dla tej funkcji wyszukiwania. W przypadku firmy, która nie może tego opublikować, zachowaj prywatność i wyjaśnij, że wymóg dotyczący wyników z elementami rozszerzonymi nie został spełniony; nie twórz adresu ani nie obiecuj spełnienia wymagań na podstawie samego `areaServed`.

Znaczniki opinii o własnej firmie (self-serving reviews) dla LocalBusiness nie dają gwiazdek w recenzjach tylko dlatego, że firma wyświetla referencje. Nie importuj oceny profilu do znaczników jako skrótu do gwiazdek.

Użyj schema do wdrożenia. Sprawdź wyrenderowaną stronę i odpowiednie narzędzia testowe, a następnie sprawdź, czy wdrożone znaczniki odpowiadają treści publicznej. Pobranie strony w postaci samego tekstu nie jest wystarczającym dowodem na brak formatu JSON-LD z wstrzykniętym JavaScriptem. Walidacja nie gwarantuje wyświetlenia ani zmiany rankingu pakietu lokalnego.

## Mierz wyniki klientów

Zachowaj punkt odniesienia według lokalizacji i okresu:

| Wskaźnik | Dowód | Granice interpretacji |
|---|---|---|
| Kwalifikowane połączenia/rezerwacje/potencjalne kontakty | Wyniki CRM lub potwierdzone przez właściciela | Deduplikuj; przypisanie może być niekompletne |
| Interakcje profilowe | Dostępny eksport wydajności profilu firmy | Interakcja nie jest sfinalizowaną sprzedażą |
| Organiczne lokalne zapytania/strony | Raporty zapytań/stron w Search Console | Progi prywatności i agregacja ograniczają szczegółowość |
| Działania witryny z linków profilowych | Analityka ze spójnymi tagami kampanii | Zgoda, blokady i tagowanie mogą mieć wpływ na liczbę |
| Widoczność lokalna | Porównywalne obserwacje zapytań/lokalizacji | Dystans, personalizacja i zmienność mają znaczenie |

Stosuj spójną konwencję tagowania linków do witryn profilowych, zachowując jednocześnie stabilny adres URL lokalizacji kanonicznej. Sprawdź, czy przekierowania i ścieżki rezerwacji zachowują niezbędne dane atrybucji. Aby śledzić połączenia, zachowaj naprawdę osiągalny kontakt biznesowy i zweryfikuj aktualne zasady dotyczące rozmów telefonicznych na platformie; nie zastępuj na ślepo kanonicznych numerów wzmianek NAP.

Przejrzyj zmiany pod kątem porównywalnego okresu, sezonowości, zmian godzin otwarcia i przepustowości usług. Zapisz, co i kiedy się zmieniło. Traktuj wzrost widoczności jako obserwację, a nie dowód związku przyczynowego lub dodatkowy dochód. Ustal z użytkownikiem termin dalszych działań, zamiast obiecać uniwersalny termin naprawy.