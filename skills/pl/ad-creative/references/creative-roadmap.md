# Pętla strategii kreatywnej

Generacja (tryby 1–3) odpowiada „twórz reklamy”. To odniesienie odpowiada na pytanie, które pojawia się jako pierwsze: **które reklamy warto tworzyć, w jakiej kolejności i przy jakim koszcie produkcji** — oraz retro, które zamienia wyniki każdego miesiąca w plan na następny miesiąc. To stała pętla operacyjna kreatywnego stratega, prowadzona przez agenta, w którym decyzje podejmuje człowiek.

```
Signals → Concepts (evidence-ranked) → Roadmap (tiered, capacity-checked) → Briefs → [Modes 1–3 produce] → Monthly retro → back into the icebox
```

---

## Krok 1: Przeczytaj trzy sygnały

Kierunek kreatywny wynika z syntezy trzech niezależnych źródeł sygnału. Poleganie wyłącznie na jednym źródle wprowadza w błąd: konto informuje, co zadziałało *spośród rzeczy, które wypróbowałeś*, klienci mówią, dlaczego kupują *swoimi słowami*, a treści organiczne mówią, co odbiorcy *wybierają oglądać, gdy nikt nie płaci*.

| Sygnał | Jakie dane zebrać | Jak |
|---|---|---|
| **Wydajność konta** | Zwycięzcy/przegrani według ujęcia komunikacyjnego, haka, formatu; wskaźniki lejka według koncepcji (patrz [hook-system.md](hook-system.md) lejek diagnostyczny); stan zmęczenia | Interfejsy CLI `google-ads` / `meta-ads` / `linkedin-ads` / `tiktok-ads` (zobacz Integracje narzędzi w SKILL.md) |
| **Klient/marka** | Dosłowny język bólu/pożądania/sprzeciwu; nieoczekiwane przypadki użycia; kto *faktycznie* kupuje, a kto jest celem | Korpus materiałów źródłowych opartych na dowodach (`inputs/reviews/`, `inputs/comments/`), notatki z rozmów telefonicznych, tematy wsparcia — na podstawie **customer-research** |
| **Zewnętrzne organiczne** | Co nisza ogląda bezpłatnie: najlepsze treści organiczne, ich haczyki, formaty, słownictwo; reklamy konkurencji wyświetlane wystarczająco długo, aby można było założyć, że działają | **scraping**, narzędzia do słuchania w **social**, biblioteki reklam, **competitor-profiling** |

**Rytm pracy:** comiesięczna dogłębna analiza (60–90 min, wszystkie trzy źródła, zasila miesięczny plan działania) plus cotygodniowe ~20-minutowe odświeżanie (co się zmieniło: nowi zwycięzcy/przegrani, nowe tematy recenzji, wszystko, co zyskuje organicznie). Badania wykraczające poza potrzeby następnej decyzji są zbędną pracą — każda sesja syntezy powinna kończyć się koncepcjami, a nie notatkami.

**Zasada zaufania:** każde spostrzeżenie, które agent wykryje, musi mieć potwierdzenie – jaka recenzja, jakie dane reklamy, który bezpłatny post. Spostrzeżenie bez źródła nie trafia do backlogu koncepcji. (Te same zasady oparcia na dowodach, jak wszystko inne w tej umiejętności.)

---

## Krok 2: Zamień sygnały w koncepcje oparte na dowodach

**Koncepcja** to jedna sprawdzalna hipoteza twórcza: *segment × motywacja × ujęcie komunikacyjne × format* wraz z dołączonymi dowodami. „UGC dla mam” nie jest koncepcją; „świeżo upieczeni rodzice cierpiący na bezsenność (na ponad 40 recenzji wspominających o karmieniu o 3 nad ranem) × „wystarczająco cicho, aby nie obudzić dziecka” × przed/po demonstracji × nocny film POV” to.

Oceń każdą koncepcję według najsilniejszych dowodów ją potwierdzających:

| Poziom | Dowód | Waga |
|---|---|---|
| 1 | Twoje własne konto: reklama konwertująca o tym samym kącie/segmencie | Najsilniejszy — iteruj i rozszerzaj |
| 2 | Twoi klienci dosłownie: powtarzająca się recenzja/język rozmowy | Mocny — zbuduj na nim nową kreację |
| 3 | Twórczość konkurencji działająca ponad 60 dni (przypuszczalnie działająca) | Dobrze — dostosuj kąt, nigdy reklamę |
| 4 | Organiczne zaangażowanie w niszę (niepłatne wyświetlenia i zapisania treści o danym temacie) | Umiarkowany — najpierw sprawdź tanio |
| 5 | Wzorzec z innej niszy (sprawdził się w pokrewnej kategorii) | Słabe — backlog koncepcji do czasu potwierdzenia |
| 6 | Przeczucie zespołu, brak sygnału zewnętrznego | Najsłabszy — tani test o niskim stopniu dopracowania albo odrzucenie |

Silniejsze dowody dają koncepcji *pierwszeństwo* w planie — wcześniejszy termin realizacji. Poziom produkcyjny to osobna kwestia, ustalana na podstawie siły walidacji, istniejących zasobów, wydajności i ryzyka: nawet koncepcja języka klienta poziomu 2 zaczyna się od niskiej wierności, dopóki nie pojawi się sygnał ścieżki. Przeczucia nie są zakazane — dostają tanie testy i trafiają na koniec kolejki.

---

## Krok 3: Wybierz wariant według stanu konta

Właściwy zestaw kreacji zależy od tego, w którym z dwóch stanów znajduje się konto. Diagnozuj przed opracowaniem planu działania — plan stworzony dla niewłaściwego stanu marnuje miesiąc.

**Stan eksploracji** — nic (lub nic nowego) nie działa:
- Idź **szeroko, nie głęboko**: głównie nowe koncepcje w różnych segmentach i z różnymi ujęciami komunikacyjnymi; ograniczaj liczbę powtórzeń do niewielkiej mniejszości — powtarzanie przegranych mnoży przegranych
- **Zdefiniuj na nowo „wygraną” według danych**: w przypadku braku zwycięzców na całej ścieżce, poprawa pojedynczego wskaźnika (wzrost współczynnika utrzymania, spadek CPC, wzrost CVR) w dowolnym teście jest sukcesem, na który warto zwrócić uwagę — zobacz ścieżkę diagnostyczną
- Iteruj **tylko przy trafieniach**; wszystko inne pozostaje odkrywcze
- Najczęstsze przyczyny, które należy sprawdzić podczas testowania: kreacja jest nudna (bezpieczna, widziana wcześniej), przekaz jest nadmiernie skomplikowany, oferta/UVP jest niejasna lub CPM karze zbyt wąską grupę odbiorców

**Stan skalowania** — jedna lub więcej koncepcji konwertuje z zyskiem:
- **Rozwijaj zwycięską koncepcję**, dopóki trwa okno jej skuteczności: prowadzona przez zwycięzcę lista wizualnie odrębnych odmian zwycięskiej koncepcji (ten sam przekaz, nowe wykonanie — prawie duplikaty w większości kanibalizują zasięg oryginału i nie uczą Cię niczego nowego, więc wariacje muszą wyglądać znacząco inaczej), a także ścieżkę remiksów (ponowne wykonanie tonalne/emocjonalne) i testy węższych ujęć komunikacyjnych skierowanych *do* zwycięskiego segmentu; dostosuj podział do budżetu, szybkości zmęczenia i szybkości produkcji
- Utrzymuj niewielki przydział eksploracji nawet w trakcie skalowania - zwycięzcy są zmęczeni, a następny zwycięzca rzadko jest powtórzeniem bieżącego
- W tym stanie prędkość ma większe znaczenie: okno skalowania jest skończone

---

## Krok 4: Artefakt mapy drogowej

Utrzymuj jeden żywy dokument (sugerowane: `roadmap.md` obok korpusu materiałów źródłowych opartych na dowodach) z trzema horyzontami:

```
## Icebox        — every concept, evidence tier + source attached, nothing scheduled
## This quarter  — 2-4 themes chosen from the icebox (the bets), with why-now
## This month    — the slate: concept | evidence tier | production tier | owner | status
```

Każda koncepcja miesięcznego pakietu otrzymuje **poziom produkcyjny**:
| Poziom | Koszt | Co to jest | Użyj dla |
|---|---|---|---|
| **T1 — Iteracja** | Godziny | Nowy hak/podpis/przycięcie istniejącego zasobu | Rozszerzanie sprawdzonych zwycięzców |
| **T2 — Remiks** | Dni | Nowa kreacja z istniejącego materiału filmowego/zasobów/generacji sztucznej inteligencji | Koncepcje z przyzwoitymi dowodami lub pierwszym sygnałem low-fi |
| **T3 — Produkcja** | Tygodnie | Całkowicie nowa sesja zdjęciowa lub nagraniowa, twórcy i pełna produkcja | Tylko ujęcia komunikacyjne potwierdzone wynikami z własnego konta lub wcześniejszym sygnałem ścieżki low-fi (drabina wierności w [hook-system.md](hook-system.md)) |

**Kontrola wydajności — zasada, dzięki której plany działania są uczciwe:** policz, co zespół (lub rurociąg AI) może wyprodukować *w jakości* w tym miesiącu i zaplanuj realizację tej liczby. Zestawienie 20 koncepcji w porównaniu z 8 koncepcjami rzeczywistej wydajności nie daje 20 reklam; daje 20 reklam o obniżonej jakości i wypalony zespół. Ograniczaj listę według siły dowodów, aż zmieści się w możliwościach produkcyjnych.

Na podstawie planu wygeneruj **po jednym briefie na koncepcję** (segment, motywacja + dokładne źródło, kąt, format, wiersze macierzy haków, poziom produkcji, miernik sukcesu) i przekaż każdy z nich do trybów 1–3 w celu produkcji.

---

## Krok 5: Comiesięczne kreatywne retro

Ostatni krok pętli, pierwsze wejście następnego. Jeden artefakt na miesiąc (sugerowane: `retros/YYYY-MM.md`):

```
## Winners     — concept, the funnel numbers, and the WHY (which element earned it)
## Losers      — concept, where in the funnel it died, hypothesis for why
## Metric wins — full-funnel losers with one strong metric (these are leads, not losses)
## Learnings   — pattern-level notes → written back into the icebox as new/revised concepts
## Kills       — concepts retired from the icebox, with reason
## Next slate  — first draft of next month, updated evidence ranks
```

Zasady retro:

- **Oceniaj koncepcje, a nie reklamy.** Niepowodzenie trzech różnych realizacji jednej koncepcji oznacza, że koncepcja jest błędna; jedno niepowodzenie mówi, że wykonanie było.
- **Przeczytaj ścieżkę, a nie kolumnę ROAS.** Lejek diagnostyczny mówi, *co* naprawić; Sam ROAS mówi tylko, *że* coś jest zepsute.
- **Wystarczająca ilość danych przed wydaniem werdyktu** – przestrzegaj progów wyświetleń/wydatków w typowych błędach i systemach decyzyjnych dotyczących umiejętności **ads**; dwudniowa lektura to rzut monetą.
- **Każda nauka gdzieś ląduje**: aktualizacja backlogu koncepcji, zmiana rangi dowodów lub zabicie. Retro, które nic nie zmienia w planie działania, było spotkaniem, a nie retro.

Aby uruchomić tę pętlę zgodnie z harmonogramem (retro pierwszego dnia, cotygodniowe odświeżanie w poniedziałki, codzienne partie w trybie 3), zobacz pętle kreatywne w **marketing-loops**.

---

## Tryby awarii

- **Roadmap bez diagnozy** – plansza zbudowana przed odczytaniem trzech sygnałów to lista życzeń; badanie bez diagnozy to nie strategia
- **Plany zdominowane przez iteracje w stanie eksploracji** — dopracowywanie przegranych, podczas gdy prawdziwy problem (kąt, oferta, odbiorcy) pozostaje niesprawdzony
- **Ignorowanie wydajności** — plan, którego zespół nie jest w stanie wyprodukować z zachowaniem odpowiedniej jakości, jest planem produkowania treści niskiej jakości
- **Koncepcje niepoparte dowodami wyskakujące w kolejce** — najgłośniejsze przeczucie interesariuszy pojawia się w sesji T3, podczas gdy język klienta poziomu 2 leży w backlogu koncepcji
- **Retro jak teatr** — zwycięzcy świętowali, nic nie zostało przeniesione do rankingu, backlog koncepcji nietknięta
- **Samozadowolenie ze stanu skalowania** — 100% planu przeznaczone na warianty zwycięskiej koncepcji; kiedy zwycięzca jest zmęczony, rurociąg jest pusty