# Pomiar wpływu wyszukiwania AI poza kliknięciem w link odsyłający

Odpowiedzi AI wpływają na kupujących, którzy nigdy nie klikają linku. Czytają rekomendację, a kilka dni później wyszukują Twoją markę lub wpisują adres URL. W raportach poleceń brakuje większości tego, więc stwierdzenie „AI nie wysyła nam prawie żadnego ruchu” jest zwykle luką w pomiarze, a wpływ wywierany jest na inne kanały.

Firma Profound powiązała ponad dwa miliony rozmów AI z późniejszym zachowaniem podczas przeglądania (Profound, lipiec 2026 r.; obserwacyjne, tylko w USA, mierzone wizyty w witrynie, a nie zakupy). Dwa ustalenia kształtują poniższą konfigurację:

- Tylko **42%** dalszych wizyt po wprowadzeniu marki przez asystenta AI miało miejsce w ciągu 24 godzin. W oknie tej samej sesji brakuje większości efektów.
- Ponad **97%** tych wizyt nie zawierało informacji o źródle odesłania AI, nawet po tym, jak ChatGPT ułatwił klikanie linków.

Dane dotyczące podróży z serwisu SimilarWeb wskazują na to samo: około 9% wizyt po rekomendacji to widoczne polecenia AI (zobacz [citations-vs-recommendations.md](citations-vs-recommendations.md)). Firma Profound śledzi widoczność AI, więc traktuj jej liczby jako badania dostawców i nie przedstawiaj wyników żadnego z badań jako prognozy dla jednej marki.

## Cztery warstwy

Zgłaszaj każdą warstwę osobno. Rosnąca widoczność nie oznacza rosnących przychodów.

| Warstwa | Co rejestruje | Skąd pochodzi |
|---|---|---|
| **Ekspozycja** | Wzmianki, rekomendacje, znaczenie, sposób przedstawienia, cytowania | Śledzenie promptów (patrz [prompt-portfolio.md](prompt-portfolio.md)) |
| **Natychmiastowe zachowanie** | Sesje polecające AI, strony docelowe, sesje z zaangażowaniem | Analityka z pogrupowanymi stronami odsyłającymi AI (zobacz umiejętność **analytics**) |
| **Opóźnione zachowanie** | Wyszukiwanie marki, wizyty bezpośrednie, wizyty ponowne, konwersje między sesjami | Zapytania dotyczące marki w Search Console, analityka, CRM |
| **Wynik biznesowy** | Rejestracje, potencjalni klienci, kwalifikowane szanse sprzedaży, zakupy, przychody, utrzymanie | CRM i rozliczenia |

## Konfiguracja

1. **Nazwij decyzję.** „Czy powinniśmy nadal finansować treści AEO?” potrzebuje innego projektu niż „Czy naprawa naszej strony z cenami coś zmieniła?”
2. **Określ ekspozycję** według wyszukiwarki, kohorty zapytań, rynku, języka i daty, aby wiedzieć, co i kiedy się zmieniło.
3. **Napraw przechwytywanie poleceń.** Zgrupuj znane domeny odsyłające z AI (chatgpt.com, perplexity.ai, gemini.google.com, copilot.microsoft.com, claude.ai itd.) w jeden kanał. Zachowaj parametry strony docelowej, strony odsyłającej i zapytania. Spodziewaj się, że będzie zaniżone.
4. **Dodaj opóźnione okna.** Mierz wyszukiwania związane z marką i bezpośrednie wizyty na stronach objętych ekspozycją w ciągu 1 godziny, 24 godzin i 7 dni po znanej zmianie ekspozycji.
5. **Zapytaj ludzi.** Pole „Skąd się o nas dowiedziałeś?” z opcją AI i dodatkowym pytaniem „O co pytałeś?” oraz oznaczone notatki z rozmów wychwytują ścieżki klientów, których analityka nie widzi.
6. **Powiąż z wynikami** w CRM bez liczenia tej samej konwersji dwukrotnie w różnych warstwach.

## Projekty ewaluacyjne

Wybierz najmocniejszy projekt, na jaki Cię stać, i powiedz, którego użyłeś.

| Projekt | Użyj, gdy | Pewność |
|---|---|---|
| **Grupa kontrolna** | Możesz pozostawić porównywalne strony, produkty lub rynki nietknięte | Najwyższy |
| **Dopasowane porównanie** | Istnieją podobne strony lub rynki, ale nie można losować | Średni |
| **Przerywany szereg czasowy** | Jedna jasna data interwencji i długi, stabilny poziom wyjściowy | Średni |
| **Przed/po w stabilnej kohorcie** | Nic lepszego nie jest możliwe | Niski; zakłócacze łatwo to zalewają |
| **Panel ekspozycji lub badanie efektu przyrostowego** | Budżet panelu dostawcy | Różni się w zależności od metody panelu |

Wymień czynniki zakłócające przed przeczytaniem wyników: kampanie, premiery, prasa, sezonowość, zmiany cen oraz aktualizacje modeli lub pobierania.

## Język raportowania

Powiedz, którą z trzech rzeczy masz: **obserwację** („wyszukiwanie związane z marką wzrosło o 18% po zmianie”), **powiązanie** („strony z większą liczbą wzmianek o sztucznej inteligencji odnotowały więcej bezpośrednich odwiedzin”) lub **wynik przyczynowy** („strony kontrolne nie wykazały zmiany; strony objęte działaniem tak”). Większość raportów AEO uzasadnia tylko pierwsze dwa. Tak właśnie powiedz.

Przestrzegaj zasad prywatności w danych panelowych i samodzielnie zgłaszanych: agreguj małe grupy i postępuj zgodnie ze swoimi zasadami dotyczącymi zgody i przechowywania.

---
*Pochodzenie frameworka: czterowarstwowy model, okna atrybucji i projekty oceny zaadaptowane (ponownie wyrażone i zrestrukturyzowane) na podstawie firmy Profound umiejętności planowania ai-search-attribution-planner na licencji MIT oraz badania „efekt wzmianki o sztucznej inteligencji” (lipiec 2026 r.), przypisane.*