# Animowane reklamy wideo (bez prezentera, w pełni generowane)

> Format spopularyzowany przez Borję ([@borjafat](https://x.com/borjafat)) i otwarty przepis na kolaż ruchu `super-video-maker` autorstwa [Bomx](https://github.com/Bomx/super-video-maker-skill); ten przewodnik jest oryginalnym wyrazem tej metody, rozszerzonym o bibliotekę obejmującą wiele stylów i lekcje produkcyjne dotyczące tworzenia i dostarczania całego filmu.

Stwórz reklamę wideo lub film objaśniający o długości 15–45 s bez prezentera, wyłącznie na podstawie koncepcji: stylizowany
kadr plakatowy (model obrazu) → ożywienie subtelnym ruchem (model obraz–wideo)
→ narracja (TTS) → napisy zsynchronizowane ze słowami. Bez nagrań, prezentera i montażysty. Koszt
gotowego filmu to około 3–6 USD w wywołaniach API; czas wykonania około 15 minut.

Format działa, ponieważ *nieruchomy obraz* przekazuje ideę (jedna dosłowna, lekko surrealistyczna
wizualizacja na segment), a *ruch* jedynie ją ożywia. Oprzyj się pokusie, by to
wideo opowiadało historię — projektujesz animowany plakat, a nie film.

## Kiedy używać

- Reklamy z koncepcjami/objaśnieniami: jeden pomysł skonkretyzowany („Twój CRM to szuflada na śmieci”)
- Filmy społecznościowe na górę lejka (Reels/Shorts/TikTok 9:16, aktualności 4:5 i 1:1)
- Formaty łączące budowanie marki z reakcją odbiorcy, w których charakterystyczny, własny styl przewyższa standardowe treści UGC
- NIE dla: reklam demonstracyjnych i opartych na dowodach (wygrywają nagrania ekranu), formatów referencji/UGC,
  wszystko, co wymaga prawdziwego zdjęcia produktu jako dowodu

## Proces produkcji (niezależny od dostawcy)

1. **Scenariusz**: 3–6 segmentów, 20–45 s narracji. Jeden pomysł na segment. Spokój i konkret wygrywają
   z nadmiernym entuzjazmem. Zakończ jednym zdaniem CTA.
2. **Kadry plakatowe** — po jednym na segment, przy użyciu *formuły stylu* (poniżej). Wygeneruj segment 1,
   zatwierdź go, a następnie przekaż jako obraz referencyjny dla każdego późniejszego segmentu, aby zestaw został odczytany
   jako jedna seria. Napraw zniekształcony tekst etykiety, regenerując go z krótszą frazą.
3. **Animuj** każdy zatwierdzony kadr za pomocą modelu obrazu na wideo (5–8 s na segment).
   Ruch należy do obiektów w kadrze; kompozycja nie może się zmieniać.
4. **Narracja + napisy**: jedno ciągłe ujęcie TTS, transkrypcja ze znacznikami czasu słów
   (Whisper), podziel segmenty na granicach zdań i wtop w obraz grupy napisów po 2–3 słowa.
5. **Montaż**: połącz segmenty przycięte do długości ich narracji (przedłuż ostatnią klatkę, jeśli trzeba wypełnić czas),
   normalizacja głośności do `I=-16:TP=-1.5:LRA=11`, eksport aspektu według miejsca docelowego.

**Opcje dostawcy** (działa dowolna kombinacja; przepis jest niezależny od modelu):

| Etap | Gemini z jednym kluczem API | Alternatywy |
|---|---|---|
| Zdjęcia | Nano Banana Pro (`gemini-3-pro-image-preview`) — doskonała typografia etykiet | GPT-Image, Flux, Ideogram |
| Ruch | Veo 3.1 Fast obraz–wideo (uwaga: 1080p wymaga klipów trwających 8 s) | Seedance 2.0 przez fal.ai, Kling, Runway |
| VO | Gemini TTS (spokojne głosy: Charon/Kore) | ElevenLabs, OpenAI TTS |
| Napisy | znaczniki czasu słów z Whisper + wtapianie napisów PIL/ASS | CapCut, automatyczne napisy na platformie |

## Biblioteka stylów

Pięć sprawdzonych stylizacji. Każdy z nich to formuła podpowiedzi polegająca na wypełnieniu pól; zachowaj JEDEN styl na
kampanię tak, aby konto budowało rozpoznawalną identyfikację wizualną. Cała piątka dobrze się animuje.

### A. Kolaż wykonany metodą sitodruku (od redakcji, estetyka kanału In a Nutshell)
> Plakat kolażowy wykonany metodą sitodruku, pojedyncze nasycone tło `<COLOR>`, subtelne ziarno papieru gazetowego. Element centralny: czarno-biały półtonowy wycinek `<SUBJECT DOING THE LITERAL CONCEPT>`, traktowany jak papierowa naklejka z cienkim białym wyciętym konturem, lekko podartymi krawędziami i miękkim cieniem. Widoczna tekstura kropki półtonowej, wrażenie zdjęcia redakcyjnego w stylu vintage, obiekt w skali szarości. Wycięcia akcentujące: 2–4 płaskie kształty (kremowe kółko słońca, czarny zygzak, rozproszone kropki). U dołu podarta papierowa etykieta z napisem „`<LABEL>`” zapisanym pogrubioną, zagęszczoną czcionką, wielkimi literami. Estetyczny risograf z nadrukiem matowym, ograniczona paleta. Żadnych gradientów, żadnego blasku, żadnego 3D, żadnego fotorealizmu, żadnego dodatkowego tekstu.

### B. Płaska ilustracja wektorowa (czytelne, techniczne, z możliwością nieograniczonego brandingu)
> Płaska ilustracja wektorowa w stylu animowanego kanału naukowego premium: przyjazny uproszczony `<SUBJECT>`, odważne płaskie kształty z czystymi zaokrąglonymi krawędziami, jednolite tło `<BRAND COLOR>`, ograniczona paleta `<2-3 ACCENTS>`, płaskie akcenty geometryczne, miękkie, długie cienie, całkowicie płaski projekt 2D. Czysty prostokątny baner u dołu zawiera napis „`<LABEL>`” zapisany pogrubioną geometryczną czcionką bezszeryfową i wielkimi literami. Żadnych konturów, żadnego 3D, żadnego fotorealizmu, żadnej tekstury, żadnego dodatkowego tekstu.

### C. Diorama z papieru (ciepła, dotykowa, najwyższej jakości)
> Warstwowa diorama z papieru: `<SUBJECT>`, każdy element ręcznie wycięty z kolorowego papieru plastycznego z widoczną grubością papieru i prawdziwymi cieniami pomiędzy warstwami, papierowe tło `<COLOR>` z akcentami z wycinanego papieru, w dotyku wrażenie rękodzieła z nieco niedoskonałymi cięciami nożycowymi. Wycięty z papieru baner u dołu zawiera gruby, wycięty z papieru napis „`<LABEL>`”. Miękkie oświetlenie studyjne na warstwach papieru. Żadnych cyfrowych gradientów, żadnych fotorealistycznych ludzi, żadnego dodatkowego tekstu.

### D. Komiks pop-artowy (głośny, zatrzymujący przewijanie, przyjazny promocjom)
> Panel komiksowy w stylu vintage w stylu pop-art: `<SUBJECT>`, pogrubione kontury czarnym tuszem, cieniowanie kropek Ben-Day, płaskie kolory drukarskie (`<PALETTE>`), komiksowe akcenty w kształcie gwiazdy, grube obramowanie panelu, tekstura postarzanego papieru gazetowego. Pole z podpisem komiksowym u dołu zawiera pogrubiony komiksowy napis „`<LABEL>`”. Estetyka komiksu drukowanego w latach 60. XX wieku, niewielka niedokładność pasowania farb. Żadnego 3D, żadnego fotorealizmu, żadnych gradientów, żadnego dodatkowego tekstu.

### E. Claymation (uroczy, mocne przełamanie schematu)
> Scena animacji poklatkowej: urocza, ręcznie robiona plastelina `<SUBJECT>`, widoczne odciski palców i tekstura gliny, gliniane tło i podłoga `<COLOR>`, masywne gliniane rekwizyty, ciepłe, miękkie oświetlenie studyjne przypominające plan filmowy poklatkowy, płytka głębia ostrości. Mały gliniany znak u dołu zawiera ręcznie formowany gliniany napis „`<LABEL>`”. Ręcznie wykonane miniaturowe wrażenie. Żadnych ilustracji 2D, żadnych fotorealistycznych ludzi, żadnego dodatkowego tekstu.
## Style elastyczne pod kątem marki (oparte na tokenach)

Pięć powyższych stylizacji jest *charakterystycznych* — narzucają własną paletę. Ten drugi
poziom stawia *markę na pierwszym miejscu*: każdy styl określają *pola do wypełnienia*, więc można wstawić tokeny dowolnej firmy,
a wynik wygląda jak część jej własnego systemu projektowego.

**Pola marki do wypełnienia.** Przed generowaniem ustal ich wartości na podstawie
wytycznych marki (lub `.agents/product-marketing.md`):

- `FIELD` — neutralne tło (markowa biel/ecru lub markowa ciemna)
- `INK` — kolor rysunku i tekstu (markowy szary/węgiel, prawie czarny)
- `ACCENT` — JEDEN markowy kolor lub gradient, stosowany oszczędnie (linia, belka, kwadrat)
- `TYPE FEEL` — styl typografii marki („czyste nowoczesne groteskowe sans”, „geometryczne sans”, „mono napisy”)
- Wszelkie ograniczenia związane z marką (np. „gradienty tylko na obramowaniach/krawędziach, nigdy na wypełnieniach”)

Stosuj akcent bardzo oszczędnie — jeden element na klatkę. Dzięki temu
całość wygląda na świadomie zaprojektowaną, a nie wygenerowaną.

### F. Ilustracja redakcyjna monoline (najłatwiejsza do dostosowania do marki)
> Minimalistyczny plakat redakcyjny z monolinią: `<SUBJECT>`, narysowany w całości eleganckimi, cienkimi liniami `<INK>` o jednakowej grubości na czystym tle `<FIELD>`, w stylu ilustracji na blogu premium firmy technologicznej. Rzadka kompozycja z dużą ilością pustej przestrzeni, kilkoma drobnymi monoliniowymi akcentami i JEDNYM powściągliwym elementem `<ACCENT>`: `<a thin accent underline sweep / a small accent arc>`. Mały podpis u dołu brzmi „`<LABEL>`” zapisany czcionką `<TYPE FEEL>`, `<INK>`, wielkimi literami z odstępami i cienkim podkreśleniem `<ACCENT>`. Precyzyjny, techniczny, wyrafinowany. Żadnych wypełnień poza pojedynczym akcentem, żadnych gradientów, żadnego 3D, żadnego fotorealizmu, żadnej tekstury, żadnego dodatkowego tekstu.

### G. Typografia szwajcarska (typografia JEST warstwą wizualną — dowolna marka z czcionką i kolorem)
> Plakat w szwajcarskim międzynarodowym stylu typograficznym: słowa „`<LABEL>`” umieszczone są ogromne, pogrubioną czcionką `<TYPE FEEL>`, `<INK>` na tle `<FIELD>`, wypełniając górne dwie trzecie ciasną interlinią i przyciętymi krawędziami. Mały czarno-biały wycinek fotograficzny `<SUBJECT>` znajduje się na cienkiej siatce linii bazowej w dolnej jednej trzeciej, wyrównanej do asymetrycznej siatki z jedną cienką linią `<ACCENT>` i małym kwadratem `<ACCENT>` jako jedynym kolorem. Widoczne słabe linie siatki, precyzyjne marginesy, kompozycja matematyczna. Płaski, zadrukowany, matowy. Żadnych gradientów, żadnych 3D, żadnych dekoracji, żadnego dodatkowego tekstu poza etykietą i jednej małej linii podpisu z odstępami między literami.

### H. Wireglow (ciemny motyw przewodni — narzędzia deweloperskie / marki działające w trybie ciemnym)
> Ciemny, minimalistyczny plakat z motywem technicznym: `<SUBJECT>` renderowany jako elegancka, cienka, jasnoszara linia szkieletowa rysowana na prawie czarnym tle `<FIELD>` z subtelnym ziarnem filmu. Z `<the focal object>` emanuje miękka, wąska wiązka świecącego światła gradientowego `<ACCENT>`, jedynego koloru, o miękkich krawędziach, tworzącego atmosferę. Słabe, cienkie, koncentryczne geometryczne okręgi prowadzące. Podpis u dołu brzmi „`<LABEL>`” zapisany czcionką `<TYPE FEEL>`, jasnoszary, z wielkimi literami i odstępami między nimi, pod nim znajduje się bardzo cienka linia gradientowa. Powściągliwy, premium, techniczny. Żadnego fotorealizmu, żadnego renderowania 3D, żadnych przeładowanych elementów, żadnego dodatkowego tekstu.

### I. Sitodruk Duotone (foto marki — redakcyjny efekt druku w dwóch kolorach)
> Wyrazisty dwukolorowy plakat fotograficzny wykonany metodą sitodruku: dramatyczna fotografia `<SUBJECT>`, odtworzona jako dwukolorowy sitodruk — `<INK>` dla cieni i `<ACCENT>` dla świateł — na tle w złamanej bieli papieru `<FIELD>` z widocznym gruboziarnistym ziarnem półtonów i niewielkim błędnym pasowaniem atramentu. Mocna kompozycja diagonalna, postać duża i przycięta. Szeroki, solidny pasek `<INK>` u dołu zawiera słowa „`<LABEL>`” odwrócone pogrubioną, skróconą wielką literą `<TYPE FEEL>` i małym kwadratowym znacznikiem `<ACCENT>`. Energia plakatu redakcyjnego, matowy nadruk. Żadnych gradientów poza duotonem, żadnego 3D, żadnego dodatkowego tekstu.

**Notatki o ruchach dla tego poziomu**: F/G animuje się podczas rysowania (linie wydłużają się, akcent
przeciągnięcie rysuje się samoczynnie, tekst osiada, przesuwając się o kilka pikseli); H animuje się jako impuls wiązki + wolny
wrażenie rotacji szkieletu; I jak ziarno migocze + powolny najazd. Obowiązują te same twarde zasady — ruch
należy do istniejących elementów, kompozycja nigdy się nie zmienia.

## Formuła podpowiedzi ruchu

> Subtelny ruch ożywiający styl `<style>` ruch tylko istniejących elementów. `<ONE literal motion tied to the concept: the pile inflates / the arrow creeps higher / the megaphone trembles with each shout>`. `<Secondary ambient motion: accents drift, gentle push-in>`. Każdy element, który jest teraz widoczny, jest jedyną rzeczą, która kiedykolwiek się pojawia; kompozycja pozostaje dokładnie taka sama. Wszystko pozostaje `<style descriptor: a flat printed collage / flat 2D vector / cut paper / printed comic / handmade clay>`. Bez gwałtownych ruchów kamery, bez zmiany sceny, bez morfingu, bez dodanego tekstu.

## Błędy poznane w praktyce

- **Modele wideo uwielbiają dodawać fotorealistyczne „ręce twórcy”**, zwłaszcza sięgające do kadru
  przy naciskaniu/obsługiwaniu ruchów — i *negatywne podpowiedzi pogarszają sytuację* („bez rąk” to
  pułapka uwagi). Nigdy nie wspominaj o rękach; opisywać ruch jako należący do obiektów,
  i zawierać „kompozycja pozostaje dokładnie taka, jaka jest”.
- **Zawsze sprawdzaj ostatnie 2 sekundy każdego klipu** — to właśnie tam pojawiają się obiekty i styl
  pojawia się dryf. Przytnij przed nimi lub zregeneruj; nigdy nie dostarczaj klatki, która nagle stała się fotorealistyczna.
- **Jeden dominujący ruch na segment.** Dwa ruchy wyglądają chaotycznie przy szybkim przewijaniu aktualności.
- **TTS i Whisper różnie rozpoznają podobnie brzmiące słowa** („laws” → „loss”). Porównaj transkrypcję
  ze scenariuszem przed wtopieniem napisów; wybieraj jednoznacznie brzmiące sformułowania CTA.
- **Trzymaj napisy z dala od paska etykiety** (napisy ~60% wysokości, etykieta ~80%).
  Ogranicz przedziały grup napisów, aby nigdy na siebie nie zachodziły; dłuższe grupy zmniejszaj do dostępnego miejsca.
- **Dotyczy reklamy**: umieść markę/etykietę na samym plakacie (pozostanie widoczna podczas
  automatycznego odtwarzania bez dźwięku), przedstaw koncepcję już w segmencie 1 (3-sekundowym haczykiem jest plakat) i
  eksportuj 9:16 + 4:5 + 1:1 z tych samych segmentów, generując kadry ponownie dla każdej proporcji
  zamiast przycinać.

## Zgodność

W pełni syntetyczne postacie — bez problemów związanych z wizerunkiem i oznaczaniem UGC, ale sprawdź platformę
Wymagania dotyczące ujawniania treści związanych ze sztuczną inteligencją (media wygenerowane przez sztuczną inteligencję z etykietami Meta i TikTok).
Nie twórz statystyk ani referencji w VO; uzasadnij każde twierdzenie.