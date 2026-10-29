# Krótkie filmy w pionie — specyfikacja produkcji i formaty twórców

Warstwa platformy pod dowolnym filmem 9:16 dla TikTok, Reels lub Shorts – ograniczenia decydujące o tym, czy dobry pomysł przetrwa kontakt z kanałem – plus wielopoziomowa biblioteka formatów twórców/UGC i założycieli, które regularnie dają dobre wyniki organiczne i w płatnych kampaniach.

Część 1 (specyfikacja) dotyczy **każdego** pionowego filmu wideo, który wytworzy ta umiejętność — ujawnień w iMessage w [imessage-video-ads.md](imessage-video-ads.md), reklamy ruchome w [motion-video-ads.md](motion-video-ads.md) i formaty twórców poniżej. Część 2 to biblioteka formatów.

---

## Część 1 — Specyfikacja wideo w pionie

### Płótno
- **1080×1920 (9:16), 30 kl./s, MP4.** Materiał filmowy o dowolnej rozdzielczości/orientacji jest przycinany do środka w celu wypełnienia (`object-fit: cover`) — mieszane rozdzielczości źródłowe są w porządku.

### Bezpieczne strefy (najczęściej pomijane ograniczenie)
Interfejs platformy zakrywa krawędzie klatki — szyna akcji, stos napisów, przycisk muzyki i wiersz konta znajdują się *nad* Twoim filmem. Tekst i kluczowe elementy wizualne w tych pasach zostaną zasłonięte. Trzymaj wszystko w **bezpiecznym międzyplatformowym przedziale** — najgorszy przypadek marginesów TikTok i IG Reels na płótnie o rozdzielczości 1080 × 1920:

| Krawędź | Pozostaw wolne | Dlaczego |
|---|---|---|
| **Góra** | 220 pikseli | Zakładki TikTok + wiersz konta IG |
| **Na dole** | 500 pikseli | Napisy / muzyka / stos CTA (obie platformy) |
| **W lewo** | 180 pikseli | Symetria z prawą |
| **Prawo** | 180 pikseli | Szyna akcji (polub/skomentuj/udostępnij/muzykę) |

**Wynik: wyśrodkowany pasek tekstowy o wymiarach 720×1200, od y=220 do y=1420.** Umieść w nim wszystkie podpisy i nośne elementy wizualne. Przed dużą partią produkcyjną sprawdź podgląd z nałożoną bezpieczną strefą. (Te liczby zmieniają się wraz z aktualizacjami aplikacji — sprawdzaj je od czasu do czasu; są to najgorszy przypadek z dobrych źródeł, a nie stałe prawo).

### Styl napisów (klasyczny TikTok)
Białe wypełnienie, czarny kontur, **bez pigułki w tle** — natywny wygląd, który można odczytać jako organiczny, a nie jako reklamę:

```css
color: #fff;
font-family: "TikTok Sans", sans-serif;  /* or a close variable sans; embed it, don't assume it's installed */
font-weight: 700;
paint-order: stroke fill;                  /* stroke behind fill — keeps glyphs crisp */
-webkit-text-stroke: 8px #000;
text-shadow: 0 2px 10px rgba(0, 0, 0, 0.35);
```

- **Podpisy są statyczne** — brak przejść między wejściami i wyjściami. Napis jest w pełni widoczny w pierwszej klatce okna, a jego okno dokładnie pasuje do segmentu wideo (ten sam początek i ten sam koniec). Animowane napisy brzmią: „stworzone przez markę”.
- **Automatyczny rozmiar pasa.** Zacznij od ~58 pikseli i zmniejszaj w krokach ~2 piksele, aż tekst zmieści się w bezpiecznym pasmie (wysokość pola dopasowania ~1150 pikseli), minimum ~26 pikseli. Nigdy nie przekraczaj pasma, nigdy nie przycinaj części glifu. Długie haczyki typu ściana tekstu są *obsługiwanym* wejściem, a nie przypadkiem awarii — po prostu się kurczą. Dokonaj ponownego pomiaru po faktycznym załadowaniu czcionki (`document.fonts.ready`), aby przy ustalaniu rozmiaru uwzględniana była rzeczywisty krój pisma, a nie font zastępczy.

### Domyślne ustawienia dźwięku (i decyzja „dźwięk w aplikacji” czy „dźwięk wbudowany”)
- **Domyślnie wycisz dźwięk klipu; pozwól, aby dźwięk był przenoszony przez jeden utwór muzyczny.** Dźwięk w każdym klipie jest opcjonalny (np. utrzymuj pełny głos twórcy, wycisz B-roll).
- **Wyciszanie muzyki przez ostatnie ~0,8 s** – nagłe urwanie dźwięku wygląda jak błąd.
- **Publikacje organiczne:** w przypadku organicznych TikTok/Reels często publikuj **bez wbudowanej muzyki** i dołączaj zyskujący popularność dźwięk *w aplikacji* — algorytm platformy nagradza natywny/popularny dźwięk, a dźwięk w aplikacji może zostać wykryty/dołączony przez innych. **Wbuduj muzykę w plik** dla płatnych reklam i wszędzie tam, gdzie nie można dołączyć natywnego dźwięku (niektóre cross-posty, niektóre platformy). Ta jedna decyzja znacząco wpływa na zasięg organiczny.

### Determinizm (jeśli generujesz programowo)
Rendery muszą być odtwarzalne: bez zegarów (`Date.now()`), bez `Math.random()`, bez pobierania sieci w czasie renderowania. Te same wejścia → ten sam MP4 za każdym razem. (Ma zastosowanie niezależnie od tego, czy korzystasz z Remotion, HyperFrames, czy potoku ffmpeg — zobacz umiejętność `video`, aby wybrać platformę.)

---

## Część 2 — Biblioteka formatów twórców

Krótkie formaty tworzone przez użytkowników i twórców, które niezawodnie dają wyniki organiczne i w reklamach. Każdy z nich to *struktura*, a nie scenariusz — wprowadź do niego własny materiał filmowy i haczyk. Wszyscy przestrzegają części 1.
**Poziomy** oceniają format na jednej osi: czy *skaluje reklamy do całkowicie nowych odbiorców* (format „skalowania jednorożca”), czy po prostu *konwertuje osoby znajdujące się już na środkowej/dolnej ścieżce* (format „obsady drugoplanowej”)? **S** = rzadkie formaty, które docierają do nowych odbiorców i jednocześnie przekazują rozbudowaną wiedzę. **A** = dobrze się skaluje. **B** = solidny format wspierający w odpowiednich warunkach. **C** = złożone sytuacyjnie lub operacyjnie (prawa, konkretny talent lub lepiej udawać niż uchwycić). Zbuduj *portfolio* na różnych poziomach — nie oczekuj, że każdy format będzie się skalował. Dzięki temu, że Meta dostarcza treści oparte na osobach, formaty skupiające się na twórcach (Yapper, Investigation, Authority, VSL) zajmują tak wysoką pozycję: docierają do osób natywnie za pośrednictwem twórców, których te osoby już obserwują. Aby zapoznać się z pełną taksonomią 51 formatów i umiejscowieniem każdego z nich, zobacz [meta-creative-formats.md](meta-creative-formats.md) (odnośnik towarzyszący) oraz logikę warstw/portfolio w [ads/references/meta-decision-system.md](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/skills/ads/references/meta-decision-system.md).

### Format 1 — Reakcja + Demo (twarde cięcie) · A
**Kształt:** klip z reakcją twórcy z podpisem → **twarde cięcie** do nagrania ekranu demonstracyjnego aplikacji/produktu. Łącznie ~9–12 s.

```
[ reaction · ~3s · hook caption ] → [ demo · full length · optional payoff caption ]
```

- **Kiedy:** masz (lub możesz uzyskać) autentyczną reakcję twórcy i wyraźną wersję demonstracyjną. Podstawowy format UGC dla aplikacji/narzędzi.
- **Napis przyciągający uwagę** pojawia się w segmencie reakcji i napędza sprzedaż – to reklama. Zapisz to jako wewnętrzny monolog reakcji („Miałem już to zrobić, ale ta aplikacja mnie od tego odwiodła”), a nie jako oświadczenie dotyczące produktu.
- **Twarde cięcie to mechanizm** — brak przejścia. Reakcja przyciąga uwagę, cięcie przynosi korzyści. Opcjonalny drugi podpis w wersji demonstracyjnej daje wynik („Oparto się 12 z 12 zachcianek”).
- Pozyskiwanie: rzeczywiste reakcje UGC stanowią wąskie gardło wejściowe; format jest tak dobry, jak autentyczność reakcji.

### Format 2 — samouczek dotyczący podzielonego ekranu „Bez gadania” · B
**Kształt:** cichy, szybki samouczek. Wprowadzenie na pełnym ekranie → **Podział 50/50** (pisanie/akcja na jednej połowie, wynik na żywo na drugiej), podpisy kroków na szwie. Obietnica „…ale bez gadania” = czysta wartość, bez gadania.

```
[ intro · fullscreen · hook ] → [ split: input | output · ordered step captions at the seam ]
```

- **Kiedy:** poradnik, w którym *pokazywanie* przewyższa *opowiadanie* — przebieg konfiguracji, instrukcje obsługi, samouczki dotyczące narzędzi. Zaletą jest cisza (ludzie oglądają wyciszony dźwięk, hasło „bez gadania” przyciąga osoby o silnej intencji).
- **Podpisy przedstawiają kroki** — uporządkowane, statyczne, po jednym na takt, umieszczone na rozciętym szwie, tak aby obie połówki pozostały widoczne. Automatyczny rozmiar na część 1.
- Brak lektora; tylko muzyka (patrz uwaga dotycząca dźwięków organicznych). Utrzymuj szybkie tempo — puste przerwy zabijają retencję.

### Format 3 — Reakcja na zielony ekran · A
**Kształt:** jeden film odtwarzany jest na pełnym ekranie; twórca jest **wycięty z tła** (zielony ekran/segmentacja) i skomponowany na górze — reaguje na podstawową treść lub opowiada o niej. Opcjonalnie zacznij od środka, a następnie zmniejsz/przeciągnij do rogu, aby wideo przejęło kontrolę.

```
[ fullscreen video (e.g. a screen recording / another post) + creator cutout overlay · optional hook text ]
```

- **Kiedy:** reagujesz na post konkurencji, trend, nagranie ekranu lub własny produkt — natywny format TikTok „pozwól mi zareagować na to”. Czyta się jako komentarz, który algorytm i publiczność traktują jako organiczny.
- **Obie ścieżki dźwiękowe mogą współistnieć** (podstawowy film + twórca), w przeciwieństwie do domyślnej zasady wyciszenia — tutaj chodzi o głos reakcji.
- Ruch przeciągania za róg (twórca zaczyna od dużego, aby zaistnieć, a następnie kurczy się, aby pozwolić treści oddychać) jest charakterystycznym rytmem.

### Format 4 — Yapper · A
**Kształt:** jeden twórca przemawia bezpośrednio do kamery, opowiadając osobistą historię, która trafia do Twojego produktu. Nie są wymagane żadne cięcia — historia *jest* reklamą. ~20–60 s.

```
[ creator talking to camera · hook line first · personal story → product as the resolution ]
```

- **Kiedy:** masz *właściwego* twórcę (osobę odbieraną jako o krok dalej od widza, podekscytowaną i konkretną) oraz *scenariuszową* historię z prawdziwym wątkiem narracyjnym. Trudny do uchwycenia — wymaga twórcy, scenariusza i ustawień, aby wszystko działało — ale po wylądowaniu skaluje się do zimnej publiczności.
- **Mechanika:** otwarta na mocne ujęcie lub nawiązanie do historii („Trzy razy prawie anulowałem tę aplikację”), a nie na twierdzeniu dotyczącym produktu. Struktura jako haczyk → historia → produkt wprowadzany jako zwrot w historii, nigdy jako lista funkcji. Napisy na (styl części 1); ustawienie low-fi (samochód, spacer, jedno miejsce) czyta natywnie. Płaska energia to zabija – sposób opowiadania stanowi o formacie.
- Wąskim gardłem jest casting: format zawodzi w przypadku niewłaściwego twórcy znacznie częściej niż w przypadku złego scenariusza.

### Format 5 — śledztwo amatorskie · A
**Kształt:** twórca „bada” Twój produkt, niszę lub pytanie w imieniu widza – odwiedza miejsca, porównuje opcje, testuje twierdzenia. Łuk odkrywania to silnik retencji.

```
[ creator sets up the question · goes and investigates (real footage) · lands on your product as the finding ]
```

- **Kiedy:** Twój produkt wygrywa w porównaniu lub wytrzymuje weryfikację – dochodzenie pozwala uzyskać rekomendację, zamiast ją potwierdzać. Skaluje się na zimno, ponieważ odtwarza treść, a nie reklamę.
- **Mechanika:** zadaj prawdziwe pytanie („czy gwarancje dealera rzeczywiście są tego warte?”), pozwól twórcy wykonać całą pracę przed kamerą i pozwól, aby Twój produkt wypłynął na światło dzienne jako *wniosek, do którego doszło dochodzenie* — a nie miejsce dla sponsora. Uchwycenie świata rzeczywistego (lokalizacje, porównania) to wiarygodność.

### Format 6 — Dawid i Goliat · A
**Kształt:** pozycjonuj markę jako słabszą (Dawid) w obliczu dużej branży, istniejącej lub złamanej status quo (Goliat). Historia, która sprawia, że widz kibicuje słabszemu.

```
[ name the Goliath (the villain / broken norm) · the brand's fight against it · why you win / how you're different ]
```
- **Kiedy:** masz prawdziwego antagonistę — rozrośniętego, zasiedziałego gracza, praktykę branżową, która oszukuje ludzi, domyślną kategorię gorszą od twojej. Ta historia sprawia, że ​​widz *chce*, żebyś wygrał.
- **Mechanika:** sprawia, że ​​Goliat jest konkretny, a stawki emocjonalne; Pochodzenie marki („zbudowaliśmy to, ponieważ X się zepsuło”) napędza ją. Naturalnie łączy się z narracją założyciela. Nie twórz złoczyńcy, który nie jest prawdziwy – format żyje lub umiera w obliczu prawdziwego antagonisty.

### Format 7 — Autorytet · A
**Kształt:** certyfikowany ekspert — lekarz, dermatolog, inżynier, praktyk — prezentuje lub popiera produkt na podstawie swojej wiedzy specjalistycznej.

```
[ expert on camera (credentials clear) · the problem in their domain · why this product is the right answer ]
```

- **Kiedy:** hiperkonkurencyjne, oparte na zaufaniu nisze (suplementy, pielęgnacja skóry, zdrowie, wszystko regulowane), w których kwalifikacje eksperta przekonują skuteczniej niż UGC. Dodaje walidację i twórczą różnorodność wykraczającą poza UGC twórcy.
- **Mechanika:** ekspert musi być prawdziwy, a twierdzenia muszą być prawdziwe i uzasadnione – ten format jest najbliższy ryzyku regulacyjnemu. Kieruj twierdzenia zdrowotne/medyczne/finansowe do kontroli prawnej; nigdy nie fałszuj kwalifikacji ani nie wkładaj słów w usta eksperta. Ściśle przestrzega zasad umiejętności dotyczących materiałów źródłowych opartych na dowodach.

### Format 8 — VSL (list sprzedaży wideo) · S
**Kształt:** długi (od 60 s do kilku minut) film nastawiony na bezpośrednią reakcję, który edukuje, zanim sprzeda — problem → mechanizm → dowód → oferta.

```
[ hook + problem · why it happens (the mechanism) · the solution + proof · the offer + CTA ]
```
- **Kiedy:** sprzedaż wymaga *wstępnej edukacji* — zdrowia, dobrego samopoczucia, kondycji, finansów i wszystkiego, co wymaga zrozumienia mechanizmu przez kupującego przed dokonaniem konwersji. Jeden z niewielu formatów, który zarówno skaluje się na zimno, jak i niesie ze sobą ciężkie nauczanie, stąd poziom S.
- **Mechanika:** rzemiosło jest zapisane w scenariuszu — trudny problem, wiarygodny mechanizm, skumulowany dowód i jasna oferta. Retencja jest projektowana krok po kroku (otwarte pętle, zwroty w środku skryptu, które dodają nowy fakt). Podpisy w całym tekście; zarówno prawdziwa osoba, jak i głos lektora działają. Jest to przede wszystkim dyscyplina pisarska – zainwestuj w scenariusz.

### Format 9 — komentarz na zielonym ekranie · A
**Kształt:** twórca omawia *nad* obrazami pełnoklatkowymi — zrzutami ekranu, zdjęciami produktów, wykresami, stroną konkurencji — łącząc podejście edukacyjne z elementami wizualnymi, do których się odwołuje. (Różni się od reakcji Format 3: jest to nakładka *nauczająca*, a nie reakcja na post.)

```
[ creator cutout + full-frame reference imagery behind them · educational narration keyed to what's on screen ]
```

- **Kiedy:** odzież i wszystko, co ma charakter edukacyjny, gdzie *pokazanie rzeczy podczas jej wyjaśniania* jest lepsze niż rozmowa w samotności. Czyta się jako komentarz/naukę, którą przekaz traktuje jako organiczny.
- **Mechanika:** zamień obrazy tła, aby dopasować je do każdego rytmu narracji (wizualizacja powinna zawsze ilustrować bieżący punkt). Narrację prowadzi głos twórcy; staraj się, aby ujęcie było naprawdę przydatne, a nie ukrytą prezentacją sprzedażową.

### Format 10 — Rozmowa · B
**Kształt:** dwie osoby biorące udział w prawdziwej wymianie zdań — wywiad, dialog, wymiana zdań — podczas której produkt naturalnie pojawia się w rozmowie.

```
[ two people talking · a real question/answer exchange · product enters as part of the dialogue ]
```

- **Kiedy:** możesz stworzyć autentyczną, dwuosobową dynamikę, a produkt pasuje do naturalnego momentu rozmowy. Solidna obsada drugoplanowa; więcej konwertuje niż skaluje na zimno.
- **Mechanika:** trudna do wykonania – chemia i naturalność to całość; dialogi brzmiące według scenariusza to zabijają. Najlepiej, gdy wymiana napotka realny sprzeciw i odpowie na nią naturalnie w toku rozmowy.

### Format 11 — Duet / Reakcja · C (wymagane uprawnienia)
**Kształt:** reaguj, twórz duety lub połącz film innego twórcy — Twój komentarz obok jego klipu lub po nim.

```
[ original creator's clip · your reaction / duet / stitch responding to it ]
```

- **Kiedy:** istnieje konkretny post, na który warto odpowiedzieć i dzięki któremu zyskujesz nowe grupy odbiorców. Sytuacyjne.
- **Mechanika:** **potrzebujesz praw** oryginalnego twórcy, aby wykorzystać jego materiał w płatnej reklamie — to jest brama operacyjna, a nie kreacja. Bez zatwierdzonych praw nie wyświetlaj tego jako reklamy.

### Format 12 — ASMR · C
**Kształt:** wideo kierowane dźwiękiem, skierowane do zmysłów — stukanie, rozpakowywanie, aplikacja, tekstura — z produktem jako obiektem zmysłowym.

```
[ close-up sensory action · product-forward · ASMR audio carries (no VO) ]
```

- **Kiedy:** produkty dla zwierząt domowych, kosmetyczne, spożywcze lub dotykowe, w przypadku których wrażenia zmysłowe *jest* atrakcyjne. Sytuacyjne i wymaga odpowiedniego twórcy natywnego ASMR.
- **Mechanika:** łamie domyślną zasadę wyciszenia — najważniejszy jest dźwięk; uchwyć to czysto. Wymaga twórcy, który rzeczywiście nagrywa ASMR; twórca bez specjalizacji nie odtworzy tego zmysłowego warsztatu.

### Format 13 — Wywiad uliczny · C („często lepiej udawać”)
**Kształt:** pytania zwykłych ludzi – prawdziwe lub odtworzone – rejestrujące szczere reakcje na pytanie dotyczące produktu lub kategorii.

```
[ on-the-street setup · question to passersby · candid answers → your angle ]
```

- **Kiedy:** chcesz wiarygodności nieskryptowanej reakcji publicznej. Sytuacyjne i operacyjne trudne do uchwycenia uczciwie.
- **Mechanika:** uczciwe uchwycenie jest bolesne (zgody na wykorzystanie wizerunku, nieudane ujęcia, pogoda, szczęście), więc ten format jest **często lepiej inscenizowany/odtworzony** przy użyciu tego samego języka wizualnego – odtworzona wersja jest szybsza, łatwiejsza do kontrolowania i czyta się tak samo. Jeśli to zrobisz, staraj się, aby twierdzenia były prawdziwe (nadal obowiązują materiały źródłowe oparte na dowodach).

### Założyciel / Organiczne struktury vlogów

W przypadku **reklam wideo prowadzonych przez założycieli** i organicznych treści marki cztery struktury narracyjne (Oren John) dają założycielowi coś do *powiedzenia*, a system nagrywania i edycji przyspiesza produkcję. To nie jest osobny poziom – to wątek fabularny *wewnątrz* Yappera, Investigation lub vloga. Treści założyciela to zazwyczaj *pierwsze* najskuteczniejsze materiały marki: opowiadanie historii o tym, *dlaczego* zbudowałeś markę, automatycznie nawiązuje kontakt z kupującymi mającymi ten sam problem.

**Cztery konstrukcje (wybierz wątek narracyjny, a następnie go nagraj):**
- **Podróż bohatera** — przeprowadź wszystko, co dzieje się w biznesie, poprzez: problem → historię → próbę → porażkę → objawienie → przełom → cliffhanger. Zmiana perspektywy ma większe znaczenie niż wydarzenia. Umożliwia publikowanie *mniej* — jeden świetny vlog z historią tygodniowo może pokonać codzienną treść, ponieważ ludzie śledzą podróż. (Szczególnie w przypadku tego wątku dobrze jest przeprowadzić surową sytuację przez LLM *tylko dla zarysu* — podaj kontekst marki/osoby, poproś o zarys 60–90-sekundowej podróży bohatera — a następnie sam napisz słowa).
- **Matematyka** — pieniądze jako dźwignia: zestawienie kosztów lub wyzwanie związane ze stałym budżetem („Wydałem 200 USD na reklamy Meta. Oto zestawienie.”). *Nieoczekiwanie tani* przewyższa kosztowny; kwestia przystępności cenowej budzi wewnętrzną ciekawość. Nie używaj luksusu jako haczyka – nie skaluje się i można go odczytać jako flex.
- **Błyszczący obiekt** — zakotwicz w czymś nowatorskim wizualnie, czego widz nie widział i do czego masz *dostęp* (twoja fabryka, maszyna, proces rzemieślniczy, targi). Nigdy pieniądze/luksus jako błyszczący przedmiot.
- **Przewodnik niszowy z doświadczeniem** — opowiedz o prawdziwym świecie z perspektywy swojego zawodu („Czego unikałbym jako projektant wnętrz”, nakręcony w sklepie). Punkt widzenia *ucznia* też działa — po prostu bądź szczery, kim jesteś. Wyjście w teren daje przewagę, gdy wszyscy inni gadają w samochodzie.

**System trzech ujęć** (sprawia, że ​​dowolne z powyższych jest szybkie):
- Filmuj każdą chwilę **na trzy sposoby — blisko / średnio / szeroko (0,5x)** — aby zmaksymalizować użyteczność materiału z dowolnego momentu.
- **Tylko klipy 2–3 sekundowe** — wiele małych klipów, nigdy długie przemieszczanie się (łatwy montaż osi czasu).
- **Zasada ruchu:** jeśli obiekt się porusza, trzymaj telefon nieruchomo; jeśli nic się nie porusza, dodaj powolny najazd lub przesunięcie w bok.
- Najpierw wykonaj czynność, a na koniec wróć na około 5 minut i nagraj 10–12 rzeczy z trzech perspektyw — mniej przerywania.
- Jeden folder telefonu na podróż; **oznacz najlepszy „hook” jako ulubiony**, aby otwieracz był wstępnie wybrany. Zrób sobie **≥5 zdjęć** — przydadzą się przy końcowej planszy.

**Wzór skrócenia o 0,5–1 s** (edycja): każde ujęcie to **0,5–1 sekunda** — 45-sekundowy lektor to ~45 jednosekundowych ujęć. Najpierw nagraj ścieżkę lektora/przemówienia, umieść pod nią klipy, zmień kolejność i przytnij. Wytnij w aplikacji CapCut lub Edits na Instagramie — nie sięgaj po Premiere/DaVinci. Ta przycięta kadencja jest kuzynem twardej wersji Format 1, przypominającej prędkość vloga, i to właśnie sprawia, że ​​materiał filmowy czyta się raczej energicznie niż wolno.

---
*Specyfikacja pionowego wideo (pasmo bezpiecznej strefy, przepis na napisy, automatyczne dopasowywanie rozmiaru, dźwięk organiczny a wypalony) i pierwsze trzy formaty kreatorów pochodzą z modelu `reelclaw-templates` Daniela Hangana (zbudowanego na platformie HyperFrames firmy HeyGen; TikTok Sans redystrybuowany pod SIL OFL 1.1) — wzorce zostały przypisane, bez przejmowania kodu dostawcy. Warstwowa biblioteka formatów (Yapper, Investigation, David & Goliath, Authority, VSL i logika warstw) została zaadaptowana z listy poziomów kreatywnych Meta Dary Denney; struktura założyciela/organicznego vloga, system nagrywania z trzech perspektyw i formuła cięcia 0,5–1 s zostały zaadaptowane z vloga Orena Johna + yaping playbooks — źródła przypisane, wyrażone oryginalnie. Numery bezpiecznych stref to najgorszy przypadek dla wielu platform; ponownie sprawdź w oparciu o bieżący interfejs aplikacji. Aby zapoznać się z wyborem frameworka/narzędzia do ich renderowania, zobacz umiejętność `video`.*