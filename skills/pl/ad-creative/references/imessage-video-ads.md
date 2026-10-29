# Reklamy wideo odsłaniające markę w interfejsie iOS (iMessage, ChatGPT, Apple Notes, AirDrop)

Rodzina natywnych społecznościowych formatów wideo 9:16, które odtwarzają w czasie rzeczywistym znajomą powierzchnię iOS i pozwalają marce zaistnieć w jej wnętrzu. Flagowcem jest **odsłonięcie marki w czacie iMessage** — ktoś wysyła zrzut ekranu wyniku lub produktu, znajomy reaguje i pyta, co to jest, a rozmowa ujawnia markę, zwykle za pomocą kodu promocyjnego. Bąbelki wiadomości pojawiają się w ciągu ~15–22 sekund z autentycznymi dźwiękami wysyłania/odbioru, a następnie statyczna karta końcowa marki powoduje wezwanie do działania. Ta sama architektura obsługuje **odsłonięcia marki w ChatGPT**, **Apple Notes** i **AirDrop** – omówiono w [Inne powierzchnie ujawniane natywnie dla systemu iOS](#other-ios-native-reveal-surfaces) poniżej.

Format działa, ponieważ zapożycza najczęściej czytany interfejs użytkownika na świecie. Wątek na czacie to znajoma dramatyzacja wzbudzająca duże zainteresowanie — odzwierciedla sposób, w jaki wydarzają się prawdziwe rekomendacje, więc widz pochyla się, zamiast przewijać dalej. Wezwanie do działania pojawia się w formie konwersacyjnej („użyj kodu FREEPACK”), a nie w formie twardej sprzedaży, co opóźnia odruch pominięcia reklamy, aż widz otrzyma już przekaz sprzedażowy. Uruchamiaj je tylko jako wyraźnie oznaczone płatną emisję (tag Meta „Sponsorowane” służy do ujawniania informacji); nigdy nie rozpowszechniaj tego organicznie, tak jakby to była prawdziwa rozmowa, która wyciekła.
Źródło: to odniesienie odzwierciedla format spopularyzowany przez Shiva Sakhuja i zespół Gooseworks ([@shivsakhuja](https://x.com/shivsakhuja), [gooseworks-ai/gooseworks-ads-skills](https://github.com/gooseworks-ai/gooseworks-ads-skills)), którzy zgłaszają dobre wyniki tego formatu w Meta.

---

## Kiedy używać tego formatu

**Dobre dopasowanie:**
- Reklamy reagujące/odkrywcze, których puentą jest ciekawość odbiorcy („czekaj, co to za aplikacja?”)
- Oferty z kodami promocyjnymi — przekaz konwersacyjny przypomina znacznie mniej reklamy niż kod na tabliczce
- Produkty z wynikiem umożliwiającym zrzut ekranu: liczba, pulpit nawigacyjny, paragon, informacja przed/po
- Ujęcia komunikacyjne w stylu UGC, gdy nie masz pod ręką twórców UGC

**Słabe dopasowanie:**
- Rozważane zakupy B2B, w przypadku których zwykła wymiana SMS-ów podważa wiarygodność
- Produkty, które nie zawierają żadnych elementów wizualnych ani numerycznych do zrzutu ekranu (najpierw napraw haczyk, a nie format)
- Marki, których kontrola zgodności nie może zatwierdzić udramatyzowanych rozmów (branże regulowane — najpierw sprawdź)

**Dopasowanie do platformy:** Stworzone do umieszczania w Meta Reels/Stories (9:16, 1080×1920) z wariantem 1:1 wykadrowanym centralnie do aktualności. Działa w TikTok i YouTube Shorts z tym samym plikiem głównym.

---

## Zgodność i oparcie na źródłach

To jest **dramatyzacja** – rozmowa oparta na scenariuszu, a nie prawdziwa. To standardowy, uzasadniony zabieg reklamowy, ale dwie zasady sprawiają, że jest ono uczciwe i zgodne z wytycznymi FTC:
1. **Każde twierdzenie w rozmowie musi być prawdziwe w odniesieniu do produktu.** Czas wyścigu, obliczenia oszczędności, „5 minut dziennie” – oprzyj każde z nich na rzeczywistym wyniku klienta, opinii lub możliwym do zweryfikowania fakcie dotyczącym produktu, dokładnie tak, jak wymagają tego zasady uziemionych danych wejściowych w SKILL.md. Rozmowa jest fikcyjna; zawarte w niej fakty nie mogą być fikcyjne.
2. **Nie przedstawiaj wątku jako prawdziwego świadectwa.** Żadnych prawdziwych nazwisk klientów, żadnych ramek w stylu „to jest prawdziwy tekst od klienta”, żadnych sfabrykowanych potwierdzeń. Format przekonuje rozpoznawalnością, a nie udawaniem found footage.

Jeśli twierdzenie wymaga zamieszczenia zastrzeżenia na stronie docelowej, będzie ono potrzebne także w tej reklamie.

---

## Ujęcia komunikacyjne koncepcyjne

Większość reklam iMessage pasuje do jednego z sześciu ujęć komunikacyjnych. Wybierz kąt przed napisaniem tekstu reklamy — najczęstszą przyczyną awarii („skrypt jest w porządku, ale reklama wydaje się nieodpowiednia”) jest niedopasowanie ujęcia komunikacyjnego, a nie złe linie. Najsilniejsze haczyki mają jedną z trzech cech: określoną liczbę, niewielki akt zaufania lub fizycznie nowatorską mechanikę produktu.

| Ujęcie komunikacyjne | Załącznik otwierający | Odsłonięcie marki |
|---|---|---|
| **Wynik jako zrzut ekranu** | Liczba, która sama w sobie jest przechwalająca — czas wyścigu, podsumowanie aplikacji, statystyki na desce rozdzielczej | „X minut dziennie. To wszystko.” |
| **Pochwalenie się konfiguracją** | Zdjęcie Twojej przestrzeni — mała siłownia w mieszkaniu, kącik ze sprzętem wyścigowym, konfiguracja biurka | „to jest cała konfiguracja” |
| **Moment anulowania** | Potwierdzenie — e-mail dotyczący anulowania siłowni, strona „subskrypcja anulowana” | „X/mies. → $ Y/mies. wykonaj obliczenia” |
| **Funkcja jako puenta** | Krótki klip przedstawiający mechanikę produktu w ruchu | Mechanizm produktu *jest* marką |
| **Przyjaciel-pyta-znajomego (odwrotnie)** | *Znajomy* zaczyna od zachwytu — „jak ty to robisz 😭” | *Ty* odpowiadasz, podając markę |
| **Paragon jako hook** | Zwykły dokument finansowy — wyciąg, paragon z App Store | Mały akt zaufania do siebie |

---

## Anatomia reklamy

```
0:00  Hook attachment lands (the screenshot the whole chat is about)
      ↓ short reactions, 250–450ms apart ("bro no way" / "wait is that real")
0:06  The question — "what app is that??"
      ↓ typing indicator … then the brand-name reply
0:12  The pitch, in texting voice — one or two bubbles max
0:15  The code — "use FREEPACK, first pack's free" (code renders link-underlined)
0:17  Beat of silence, then the closer — "bet" / "ok downloading"
0:18  300ms crossfade → static brand end card: logo, code, tagline (~3s)
```

**Zasady skryptu:**

- **Łącznie 8–14 dymków.** Krótsza rozmowa wydaje się uboga; dłuższa traci uwagę przewijającego widza.
- **Pisz prawdziwym głosem SMS-a.** Małe litery, fragmenty, maksymalnie jeden emoji na wiadomość, bez przymiotników marketingowych. Przeczytaj to na głos jako dwoje przyjaciół — każda bańka, która brzmi jak tekst reklamy, zostanie obcięta.
- **Marka pojawia się raz, z opóźnieniem.** Wątek dotyczy *wyniku*, dopóki ktoś nie zapyta. Nazywanie marki w bańce drugiej zabija ujawnienie.
- **Tempo ma rytm, a nie metronom.** Reakcje na jedno słowo uruchamiają się w odstępie 250–450 ms; odpowiedzi na zdania otrzymują po 600–900 ms powietrza; pozostaw około 600 ms ciszy przed końcową reakcją, aby wylądowała.
- **Wskaźniki pisania pojawiają się przed odpowiedziami innych osób składającymi się z całego zdania**, opcjonalnie przed krótkimi reakcjami. Pojawiający się wskaźnik jest cichy (patrz zasady efektów dźwiękowych poniżej).
- **Kod promocyjny znajduje się w dymku**, z podkreśleniem umożliwiającym wykrywanie linków w systemie iOS oraz *oraz* na karcie końcowej. Najpierw rozmowa, potem wzmocnienie.

---

## Trasy produkcyjne

Dwa sposoby jego produkcji, w kolejności kontroli:

### Trasa 1: potok oparty na kodzie (pełna kontrola)

Architektura, która daje przekonujący wynik: renderuj czat jako HTML/CSS naśladujący interfejs użytkownika iMessage, steruj animacją za pomocą skryptu osi czasu, nagrywaj ją w trybie headless za pomocą Playwright i składaj dźwięk + kartę końcową za pomocą ffmpeg.

1. **Skrypt jako dane.** Przechowuj wątek jako JSON: uczestnicy (imię rozmówcy, inicjały, kolor awatara), uporządkowane wiadomości (`from`, `text`, ścieżki załączników, flagi wskazujące wpisywanie), motyw, nagłówek. Skrypt można przeglądać i ponownie renderować bez dotykania kodu.
2. **Wyrenderuj interfejs czatu w formacie HTML/CSS.** Ciemny motyw jest najbardziej natywny. Dwa warianty: czat z pełnym ekranem lub czat w ramce iPhone'a (pasek stanu + Dynamic Island) na zdjęciu w tle istotnym dla marki — wariant w ramce wygląda bardziej naturalnie w aktualnościach i jest lepszym rozwiązaniem domyślnym.
3. **Animacja na osi czasu, nagrywanie w JEDNEJ ciągłej sesji.** Wszystkie bąbelki istnieją w DOM, ale są ukryte (`display: none` — nie `opacity: 0`, lub wątek wstępnie przydziela miejsce i nigdy „nie rośnie”). Skrypt sterownika porusza się po tablicy osi czasu, odsłaniając każdy bąbelek, sterując polem wpisywania wiadomości i automatycznie przewijając. Nigdy nie nagrywaj scena po scenie i konkat — każde przeładowanie strony powoduje widoczne mikromigotanie.
4. **Animuj wpisywanie w polu wiadomości dla każdego wysłanego dymku.** Wpisany tekst musi dokładnie odpowiadać wysłanemu tekstowi (rozbieżność wygląda sztucznie przy ponownym oglądaniu). Tempo ~12–15 znaków/sek. z wahaniami ±30% na znak, dzięki czemu można odnieść wrażenie, że są to kciuki, a nie skrypt.
5. **Nagrywaj w natywnej rozdzielczości wyjściowej.** Ustaw Playwright `viewport` *i* `recordVideo.size` na 1080×1920 — jeśli pominiesz `recordVideo.size`, Playwright domyślnie nagrywa pomniejszone wideo. Nagrywanie w małej rozdzielczości i późniejsze skalowanie daje nieostry, rozmyty tekst w dymkach.
6. **Warstwowe audio za pomocą ffmpeg.** Sygnały SFX obliczone deterministycznie na podstawie tej samej osi czasu, która napędzała nagranie, więc dźwięki trafiają dokładnie w trzaski bąbelków.
7. **Połączenie: czat → Przenikanie 300 ms → statyczna karta końcowa.** `xfade` ffmpeg wymaga, aby oba wejścia były zgodne pod względem rozdzielczości, formatu pikseli i liczby klatek na sekundę — renderuj kartę końcową do pliku MP4 ze statycznym obrazem z tymi samymi specyfikacjami, co nagranie czatu przed zanikaniem. Wyeksportuj wzorzec 9:16 plus kadrowanie 1:1 pośrodku.

### Trasa 2: Remotion (skalowanie przy użyciu szablonów)
Gdy pojawi się zwycięska struktura skryptu, przebuduj ją jako kompozycję Remotion (zobacz [generative-tools.md](generative-tools.md)) z JSON-em rozmowy przekazanym przez propsy. Zatem odmiany – nowe haczyki, nowe kody, nowe osoby – to zmiany danych, a nie reprodukcje. Właściwy ruch na etapie „testujemy 10 wariantów scenariusza tygodniowo”, a nie w przypadku pierwszej reklamy.

---

## Zasady rzemiosła (szczegóły, które sprzedają iluzję)

Oto różnica między „wydaje się, że jest to prawdziwy czat” a „wydaje się, że jest to makieta”:

- **Prawdziwe dźwięki wysyłania/odbioru, nigdy ogólne dźwięki powiadomień.** Wrażenie iMessage to głównie dźwięk. BigSoundBank przechowuje nagrania dźwięków wiadomości Apple pod CC0: wyślij whoosh (`bigsoundbank.com/UPLOAD/mp3/1313.mp3`, ~0,5 s) i odbierz tritone (`bigsoundbank.com/UPLOAD/mp3/1111.mp3` — przytnij do ~1,4 s z wyciszeniem 400 ms). Normalizuj głośno (≈ -9 LUFS), aby przebijały się przez muzykę. Należy pamiętać, że nagrania mają oznaczenie CC0 nie oznacza, że ​​Apple udzieliło licencji na swoje dźwiękowe znaki towarowe lub charakterystyczną szatę graficzną interfejsu — jest to standardowa praktyka w tym formacie, ale marki podlegające regulacjom i zespoły prawne niechętne ryzyku powinny ogólnie zapoznać się z mimiką iMessage; ogólna skórka aplikacji do czatowania (neutralne bąbelki, dźwięki inne niż Apple) to rozwiązanie awaryjne, które utrzymuje mechanikę.
- **Brak dźwięku na wskaźniku pisania.** iOS milczy, gdy ktoś zaczyna pisać. Odtwórz dźwięk odbioru tylko wtedy, gdy rzeczywista bańka zastąpi kropki. To najczęstszy szczegół zdradzający sztuczność.
- **Muzyka: cicha muzyka lofi/hip-hop.** ~30% głośności, górnoprzepustowy około 60 Hz, aby zwolnić miejsce na efekty dźwiękowe, wyciszenie ~1,5 s przed ujawnieniem kodu, dzięki czemu CTA zapada względna cisza.
- **Statyczna karta końcowa — bez zoomu, bez dryfu Kena Burnsa.** Karta marki musi mocno wylądować; dryfująca karta końcowa brzmi jako wypełniacz.
- **Prawdziwe logo marki SVG na karcie końcowej, nigdy tekst w stylu CSS.** Znaki słowne wykonane czcionką wyglądają amatorsko nawet z bliska. Pobierz oficjalny SVG z materiałów prasowych marki, Wikimedia lub brandfetch.com.
- **Zrzuty ekranu z hakami: naśladuj interfejs użytkownika prawdziwej aplikacji, nie generuj go przez sztuczną inteligencję.** Interfejsy użytkownika aplikacji generowane przez sztuczną inteligencję zawierają zniekształcone elementy interfejsu, który można odczytać jako niechlujstwo. Utwórz małą stronę HTML, kopiując rzeczywiste kolory marki aplikacji, typografię i konwencje układu (pomarańczowy pasek Strava, sygnatura czasowa „Publiczne · 2 godz. temu”) i wykonaj zrzut ekranu. Zarezerwuj generowanie obrazu AI dla haczyków *fotograficznych* — zdjęcia z plaży, zdjęcia lifestylowego, tła wykadrowanego wariantu.
- **Pułapka przy miksowaniu dźwięku:** `amix` firmy ffmpeg domyślnie dzieli głośność przez liczbę wejść — przekaż `normalize=0`, inaczej cały miks wyjdzie tajemniczo cicho. Następnie przepuść miks przez ogranicznik, ustawiając sufit tuż pod pełną skalą (np. `alimiter=limit=0.95`, ≈ -0,4 dB), aby było głośno i bez przesterowań.

---

## Lista kontrolna jakości

Przed wysyłką:

- [ ] Każde twierdzenie oparte na faktach w wątku prowadzi do prawdziwej recenzji, wyniku lub faktu o produkcie (uziemione dane wejściowe)
- [ ] Skrypt czytany na głos brzmi jak prawdziwy głos SMS-a — bez przymiotników marketingowych w dymkach
- [ ] Nazwa marki pojawia się dopiero po zapytaniu partnera
- [ ] Brak dźwięku na żadnym wskaźniku pisania; odbieraj efekty dźwiękowe, gdy wyląduje dymek z tekstem
- [ ] Efekty dźwiękowe pojawiają się dokładnie w przypadku wyskakujących bąbelków (sprawdzanie punktowe najpierw i na końcu)
- [ ] Każdy wysłany dymek był poprzedzony pełną animacją wpisywania w polu wiadomości; wpisany tekst jest równy wysłanemu tekstowi
- [ ] Brak mikromigotania w dowolnym miejscu czatu — jedyne cięcie to czat → karta końcowa (przenikanie 300 ms)
- [ ] Kod promocyjny jest podkreślony linkiem w dymku i powtórzony na karcie końcowej
- [ ] Karta końcowa jest statyczna z prawdziwym logo SVG
- [ ] Master jest natywny 1080×1920; Wariant 1:1 powstaje przez kadrowanie, a nie zniekształcenie proporcji
- [ ] Ostatnia bańka dostaje ~600–800 ms powietrza przed przejściem
- [ ] Dźwięk jest ograniczony tuż przy pełnej skali (bez przesterowania); muzyka nigdy nie walczy z efektami dźwiękowymi

---

## Iteracja formatu

Traktuj wątek jako zmienną, a potok jako stały. Testuj w tej kolejności — najpierw zaczep, potem cała reszta:

1. **Załącznik haka** — zrzut ekranu to miniaturka i pierwsze 2 sekundy; decyduje o zatrzymaniu przewijania
2. **Ujęcie komunikacyjne** — chwalenie się wynikiem, anulowanie lub odwrócenie ról zmieniają to, z kim utożsamia się widz
3. **Sformułowanie kodu ujawniające** — „pierwsza paczka jest bezpłatna w przypadku FREEPACK” vs. „FREEPACK daje ci jedną gratis”
4. **Persona rozmówcy** — imię i nazwisko, awatar i styl wysyłania SMS-ów zmieniają postrzeganą publiczność
5. **Długość** — wypróbuj wersję tego samego scenariusza z 12 i 8 dymkami

Ta sama architektura obejmuje także dalsze powierzchnie — WhatsApp, Slack, pole wyszukiwania — to samo nagrywanie oparte na osi czasu, inna powłoka interfejsu użytkownika.

---

## Inne powierzchnie natywne dla iOS

Wszystko powyżej na temat produkcji (makieta interfejsu użytkownika → ciągłe nagrywanie oparte na osi czasu → deterministyczne wskazówki SFX → statyczna karta końcowa), uziemienie i ujawnianie pozostaje niezmienione. To, co zmienia się w zależności od powierzchni, to *mechanika perswazji* i kilka szczegółów rzemiosła.

| Powierzchnia | Mechanika perswazji | Sięgnij po to, gdy |
|---|---|---|
| **iMessage** | Polecenie znajomego — społeczny dowód słuszności poprzez dialog | Produkt jest odkrywany na podstawie wyników udostępnianych przez użytkowników („co to za aplikacja?”). |
| **ChatGPT** | Autorytatywna odpowiedź na pytanie widza | Problem ma kształt pytania — coś, co ludzie dosłownie wpisują w ChatGPT |
| **Apple Notes** | Prywatne wyznanie ujawnione publicznie — pierwszoosobowa, bez dialogu | Kąt to transformacja lub uświadomienie sobie czegoś („rzeczy, których nikt mi nie powiedział o wieku 45 lat”) |
| **AirDrop** | Spontaniczne udostępnianie innym — „ktoś w pobliżu pomyślał, że warto Ci to wysłać *w tej chwili*” z wbudowaną decyzją o akceptacji/odrzuceniu | Produkt to coś, co ludzie przekazują sobie nawzajem (oferta, link, znalezisko, plik), a kliknięcie i zaakceptowanie może *być* ujawnieniem |
Najsilniejszy sygnał do wyboru: która z tych powierzchni już wypełnia dzień Twojej publiczności. Produkty rekomendacyjne wymagają iMessage; problemy związane z poszukiwaniem porad chcą ChatGPT; historie tożsamości/transformacji wymagają Notatek; a wszystko, co ludzie spontanicznie przekazują sobie nawzajem, wymaga AirDrop.

### Ujawnienie ChatGPT

Widz identyfikuje się z *pytającym*. Wpisywane pytanie jest haczykiem i musi być dosłownym pytaniem docelowego klienta – z niezręcznym sformułowaniem i w ogóle („dlaczego mój brzuch nagle jest taki wzdęty w wieku 47 lat?”). Odpowiedź przesyłana strumieniowo podaje prawdziwy mechanizm problemu, a następnie kategorię rozwiązania; marka ląduje w rekomendacji odpowiedzi lub w kolejnym wpisie („który jest najlepszy?”).

**Szczegóły rzemiosła:**
- **Wyświetlaj odpowiedź strumieniowo w grupach słów**, a nie znak po znaku (to jest pisanie, a nie generowanie) i nie całe akapity na raz. Subtelny dźwięk tykania pod strumieniowo wyświetlaną odpowiedzią i wyraźne zatrzymanie po zakończeniu odpowiedzi; nigdzie nie ma tritonów iMessage.
- **Animuj wpisywanie pytania jak na telefonie, a odpowiedź wyświetlaj strumieniowo jak model.** Dwa różne rytmy — kontrast oznacza „prawdziwy ChatGPT”.
- **Zachowuj możliwość zeskanowania odpowiedzi:** krótkie akapity, pogrubione wyrażenie lub krótka lista, dokładnie tak, jak faktycznie formatuje ChatGPT. Ściana tekstu przełamuje iluzję i gubi widza.
- Interfejs OpenAI jest ich charakterystyczną szatą graficzną — taka sama postawa po ocenie prawnej, jak powyższa notatka dotycząca mimiki interfejsu użytkownika Apple, z ogólną skórką „asystenta AI” jako rozwiązaniem zastępczym.

**Zgodność — tutaj bardziej rygorystyczna niż gdziekolwiek indziej w tej rodzinie.** „Odpowiedź” to tekst reklamy ubrany w fartuch laboratoryjny: kostium autorytetu. Każde zawarte w nim twierdzenie wymaga takiego samego uzasadnienia, jak twierdzenie wyrażone w twoim własnym głosie, a autorytet zapożyczony z formatu podnosi poprzeczkę, a nie ją obniża. Nie umieszczaj porad zdrowotnych, medycznych ani finansowych w sfabrykowanej odpowiedzi AI bez kontroli prawnej – to wersja tego formatu obarczona najwyższym ryzykiem. I nigdy nie przedstawiaj tej wymiany jako prawdziwej, spontanicznej odpowiedzi ChatGPT polecającej Twój produkt; to dramatyzacja, taka sama jak wątek iMessage.

### Ujawnienie notatek Apple

Gatunek inny niż formaty czatu: **spowiedź, nie rozmowa.** Widz obserwuje, jak ktoś pisze prywatną notatkę – listę osobistych odkryć, wpis „rzeczy, które chciałbym wiedzieć” – przy widocznej klawiaturze. Tytuł notatki to haczyk i spełnia rolę slajdu 1 w karuzeli („Rzeczy, których nikt mi nie powiedział o wieku 45 lat.”). Produkt pojawia się jako jedna pozycja na liście, nazwana w sposób, w jaki ktoś napisałby to do siebie, a nie tak, jak zrobiłaby to marka.

**Szczegóły rzemiosła:**
- **Dźwięk dotyczy tylko naciśnięć klawiatury.** Brak efektów czatu, brak odbieranych dźwięków — notatka nie ma innej strony. Pod spodem nadal działa cichy podkład muzyczny.
- **Animuj pisanie w naturalnym tempie kciuków, z niewielką zmiennością**, tak samo jak w przypadku reguły kompozytora iMessage. Jedna literówka i poprawka brzmi jak ludzki; kilka odczytano jako wyreżyserowane.
- **Zadbaj o właściwy wygląd interfejsu Notes:** styl tytułu większy niż treść, pasek formatowania nad klawiaturą, żółte akcenty w systemie iOS. To samo podejście do naśladowania HTML — i ta sama uwaga o ocenie prawnej szaty graficznej Apple i możliwość zastosowania neutralnego interfejsu notatnika — jak wszystko inne tutaj.
- **Dopasuj notatkę do ramki.** Napisz na tyle krótko, aby cała notatka zmieściła się bez przewijania, lub przewiń raz, celowo, z opóźnieniem.
- **Pierwsza osoba albo to nie działa.** W momencie, gdy notatka brzmi jak tekst reklamy („[Marka] wszystko zmieniła!”), intymność, która powoduje konwersję formatu, znika. Wzmianka o produkcie powinna być *najmniej* entuzjastycznym wersem w notatce.

Podstawowa zasada działa tutaj inaczej: wyznanie jest dramatyzacją *złożonej, prawdziwej* historii klienta — wnioski wyciągaj z prawdziwych recenzji i wywiadów (korpus ugruntowanych danych wejściowych), a wszelkie liczby i wyniki zachowaj w formie udokumentowanej.

### Ujawnienie AirDropu
Jedyny w rodzinie format natywny dla interakcji: hakiem jest **przychodzące żądanie AirDrop**, a **Dotknięcie Zaakceptuj to ujawnienie**. Widz ogląda z punktu widzenia *odbiorcy* — wysuwa się przezroczysta karta AirDrop z napisem „[Nadawca] chciałby udostępnić [podgląd]” z szarym komunikatem „Odrzuć” i niebieskim „Zaakceptuj”. Ciekawość ma charakter strukturalny („co to jest i kto to wysyła?”), a wybór akceptacji/odrzucenia to wbudowany rytm mikrokonwersji wbudowany w sam iOS. Kliknięcie przycisku Akceptuj powoduje przeniesienie elementu — i *to* miejsce, w którym wyląduje produkt, oferta lub wynik.

**Szczegóły rzemiosła:**
- **Miniatura podglądu to haczyk.** To jedyny obraz na karcie AirDrop przed zaakceptowaniem, więc musi zasłużyć na kliknięcie — to samo zadanie, co załącznik zrzutu ekranu iMessage. Niech będzie to rezultat, kluczowe ujęcie produktu lub oferta.
- **Nadaj nazwę nadawcy jak prawdziwe udostępnienie.** „IPhone Sarah”, „Mama”, „Macbook Jordana” brzmi natywnie; nazwa marki w slocie nadawcy brzmi jak reklama — zapisz markę jako nadawcę do ujawnienia, a nie przychodzącą kartę.
- **Pierścień postępu transferu to charakterystyczny ruch — nie pomijaj go.** Przychodząca karta → chwila wahania („zaakceptować?”) → dotknięcie Akceptuj → okrągłe wypełnienie postępu → ląduje przedmiot + karta końcowa. Ten rytm pierścienia postępu sprawia, że ​​czyta się go jak prawdziwy AirDrop, a nie cięcie.
- **Dźwięk to szum/odebrany ton AirDrop**, a nie trytony iMessage. To samo źródło CC0-Apple-sounds i ta sama uwaga o ocenie prawnej charakterystycznej szaty graficznej Apple, co reszta rodziny, z ogólną skórką „w pobliżu” jako rozwiązaniem zastępczym.
- **Zachowaj krótki czas i właściwie oddaj materiał interfejsu.** Rozmycie/przezroczystość karty i para szarych przycisków Odrzuć / niebieski Akceptuj to rozpoznawalne wskazówki; płaska, nieprzezroczysta tafla przełamuje iluzję. Cały rytm jest szybszy niż formaty czatu — interakcja *jest* reklamą.
- **Domyślnie POV odbiorcy; nadawca POV jako flex.** Odbiór jest odczytywany jako odkrycie („ktoś mi to przysłał”); wysyłanie odczytów jako rekomendacji („musiałem to przesłać AirDrop do grupy”) — użyj punktu widzenia nadawcy, gdy ujęcie opiera się na polecaniu produktu, a nie jego odkrywaniu.

Uziemienie to ta sama rodzinna zasada: to dramatyzacja udostępnienia, a nie twierdzenie, że prawdziwa osoba faktycznie przesłała Twój produkt przez AirDrop. Każde twierdzenie dotyczące przekazanego przedmiotu jest uzasadnione zgodnie z zasadami Uziemionych danych wejściowych, a wymiana nigdy nie jest przedstawiana jako prawdziwe, spontaniczne polecenie.