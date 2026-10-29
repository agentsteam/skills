# Strona przeglądu kreacji

Udostępniana, samodzielna strona internetowa, która prezentuje wygenerowane koncepcje reklam, które klient lub interesariusz może **przejrzeć i wybrać** — aktualizacja wizualna do wersji `INDEX.md`. Tam, gdzie materiały Markdown są tworzone dla operatora, strona przeglądu jest tworzona dla osoby zatwierdzającej wydatki: przedstawia każdą koncepcję jako makietę platformy In-Feed, dzieli karuzele na oznaczony scenorys klatka po klatce, umożliwia przełączanie wariantów tekstu reklamy i ujawnia, co jest oparte na rzeczywistych zasobach.

Szablon jest dostarczany pod adresem [assets/creative-review-template.html](../assets/creative-review-template.html). To jeden plik — wbudowany CSS i JS, bez kompilacji, bez zależności i bez sieci. Otwórz go lokalnie, hostuj na dowolnym hoście statycznym (Vercel/Netlify/GitHub Pages) lub przekaż bezpośrednio plik `.html`.

## Kiedy go wyprodukować

- **Przedstawienie partii do zatwierdzenia** — po wygenerowaniu trybu 1 lub trybu 3 spakuj najważniejsze koncepcje na stronie recenzji zamiast (lub obok) `INDEX.md`. Wybór 5 z 50 to decyzja *wizualna*; klient nie powinien musieć czytać Markdown, aby to zrobić.
- **Proponowanie białej listy / partnerstwo pod wspólną marką** — format, dla którego utworzono wzorzec źródłowy: pokaż partnerowi dokładnie, jak wygląda reklama pod nazwą każdego konta, ​​z opisaną mechaniką wdrażania.
- **Miesięczny przegląd planu** (tryb 4) — renderuj koncepcje planu tak, aby ocena stanu konta i wybór koncepcji odbywały się pod jednym linkiem.
Nie twórz jej do pojedynczej zmiany nagłówka ani szybkiej oceny wewnętrznej — wynik w Markdown powstanie szybciej. Sięgnij po stronę recenzji, gdy człowiek, który nie jest Tobą, musi dokonać wyboru.

## Jak jest zbudowany

Szablon jest renderowany w całości z bloku JSON w górnej części pliku — `<script type="application/json" id="review-data">`. Wypełnij go wygenerowanymi koncepcjami, a reszta wyrenderuje się automatycznie — karty, podglądy, scenorys i panel tekstów. Nie edytujesz kodu renderowania poniżej bloku danych. Poniższy model z komentarzami jest pokazany z komentarzami `//` zapewniającymi czytelność; **sam plik ma ścisły format JSON** — bez komentarzy i końcowych przecinków (zobacz „Bezpieczne wypełnianie danych”).

### Model danych

```jsonc
{
  project: {
    brand: "Truvani",              // required
    agency: "Light Labs",          // optional — adds the co-brand line + the default handle fallback (partner label/initials)
    date: "2026-07-12",            // optional
    note: "one-line context"       // optional
  },
  platforms: ["instagram", "facebook"],   // previews to offer; first is the default. Supported: instagram, facebook
  concepts: [                              // each concept is one strategic ANGLE (see SKILL.md "Define Your Angles")
    {
      name: "Heavy-Metal Proof",           // required — the angle name
      tagline: "Lifestyle hero, then the lab results",   // one line, what makes this concept distinct
      handles: [                            // optional. 1 entry = normal post; 2 = whitelist handle toggle
        { name: "truvani", partner: "Paid partnership with lightlabs", initials: "TV" },
        { name: "Light Labs", partner: "Paid partnership with truvani", initials: "LL" }
      ],
      frames: [                             // 1 frame = single ad; multiple = carousel storyboard
        {
          label: "Hook",                    // the frame's job in the narrative arc
          prompt: "Product bag hero on soft pink, gold-lace overlay",  // image description (shown as placeholder if no image)
          image: "images/heavy-metal-01.png",   // optional — local path/file URL or data URI; omit for text-only concepts
          headline: "Finally, a plant-based protein that's third-party tested for heavy metals.",  // optional per-frame overlay
          headlineTheme: "dark"             // optional: "dark" (default, white text) or "light" (dark text on light imagery)
        }
        // … one object per frame
      ],
      headlines: [                          // selectable variations; the picked one overlays frame 1 in the preview
        "Finally, a plant-based protein that's third-party tested for heavy metals.",
        "We tested our protein for heavy metals. Here's what an independent lab found.",
        "Most protein powders are never tested for heavy metals. Ours is."
      ],
      primaryText: "The caption / body copy.",
      likes: "6,240",                       // optional — Instagram like count; omit and no count is shown
      destination: { url: "shop.truvani.com", cta: "Shop now", offer: "72% OFF Protein Starter Kit" },
      rollout: {                            // optional — the mechanics of how this runs (whitelist, launch plan)
        title: "How the whitelist runs",
        steps: ["step 1", "step 2", "…"]
      },
      grounding: "What in this concept is real — the required disclosure. See below."
    }
    // … 2–4 concepts is the sweet spot; more than that and the tabs stop being a decision
  ]
}
```

### Scenorys ramowy = karuzelowy wątek narracyjny

`frames` koncepcji to jej scenorys. Oznacz każdą ramkę *zadaniem, które wykonuje*, a nie jej zawartością — `Hook`, `The problem`, `The results`, `The ask`. Jest to to samo myślenie oparte na narracji, co w przypadku ram karuzelowych: koncepcja oparta na dowodach to dosłownie Przyciągnięcie uwagi → Problem → Mechanizm → Wyniki → Kontekst → Wezwanie do działania. Aby zapoznać się z pięcioma łukami karuzelowymi wielokrotnego użytku (stos wartości, dowód problemów, lista hacków, objaśnienie narzekań, przewodnik demonstracyjny), zobacz `carousel-frameworks.md` w umiejętności **social** i wybierz łuk pasujący do ujęcia komunikacyjnego przed napisaniem ramek.

### Obrazy a obiekty zastępcze

Każda klatka jest renderowana na jeden z dwóch sposobów:
- **Dostarczono `image`** — prawdziwa kreacja (z folderu Mode 3 `images/` lub identyfikatora URI danych) wypełnia ramkę.
- **`image` pominięto** — stylizowany symbol zastępczy przedstawia ramkę `label` + `prompt`. Jest to zamierzony stan dla koncepcji obejmujących tekst reklamy i prompt obrazu, ale nie zostały jeszcze wyrenderowane na obraz — strona przeglądu jest użyteczna *zanim* pojawią się obrazy i pozostaje użyteczna po ich wypełnieniu.

Zdalne adresy URL obrazów i adresy względne wobec protokołu są blokowane, łącznie z pisownią adresów URL normalizowaną przez przeglądarkę. Pobierz autoryzowane zasoby kreatywne do lokalnego folderu `images/` i zachowaj względność ścieżek podczas hostowania lub udostępniania; hostowane zasoby względne nadal ładują się z tego hosta. To ograniczenie dotyczy dostarczonych źródeł obrazów, a nie piaskownicy do dowolnej edycji kodu HTML lub zapewnienia o serwerze hostingowym.

Swobodnie wysyłaj strony recenzji z symbolami zastępczymi; komunikują koncepcję. Wymieniaj obrazy w miarę ich generowania.

## Źródła i dowody — wymagany blok ujawniający

Każda koncepcja musi nieść za sobą linię `grounding` i musi być prawdziwa. Jest to ta sama zasada, co w korpusie materiałów źródłowych opartych na dowodach, który ukazał się klientowi: określ dokładnie, co jest prawdziwe (który panel laboratoryjny, jaka recenzja, jakie zdjęcia produktu), a przez pominięcie wskaż, co ma charakter ilustracyjny. Linią wzoru źródłowego jest model — * „Wyniki pochodzą z rzeczywistego panelu Light Labs firmy Truvani (Vanilla, testowano 13 listopada 2025 r.). Zdjęcia to własna fotografia produktów i stylu życia firmy Truvani”.*
Nigdy nie przedstawiaj wymyślonych statystyk, sfabrykowanych wyników testów ani obrazów stockowych jako własnych. Jeśli dowód koncepcji nie jest jeszcze rzeczywisty, wiersz informacji o źródłach i dowodach tak mówi („Pokazane wyniki mają charakter ilustracyjny w oczekiwaniu na panel laboratoryjny”) – strona przeglądu, która przedstawia fikcję jako fakt, jest gorsza niż brak strony z recenzjami.

## Bezpieczne wypełnianie danych

`DATA` znajduje się w bloku `<script type="application/json" id="review-data">` — są to dane obojętne (przeanalizowane za pomocą `JSON.parse`), a nie kod wykonywalny, więc wartość nigdy nie może zostać uruchomiona jako skrypt. Dwie zasady podczas pisania:

- **Tylko prawidłowy format JSON** — klucze i ciągi znaków w cudzysłowie, bez komentarzy i końcowych przecinków. (Na stronie widoczny jest wyraźny baner błędu, jeśli kod JSON jest zniekształcony, więc literówka powoduje widoczny błąd zamiast cichej awarii.)
- **Zapisuj `<` jako sekwencję `\u003c` w każdej wartości tekstowej.** Wartość zawierająca dosłownie `</script>` spowodowałaby w przeciwnym razie wcześniejsze zamknięcie bloku danych. Ponieważ agenci piszą kod JSON, zastosuj tę zmianę mechanicznie do wszystkich wartości ciągów. Wszystkie wartości są ponownie kodowane przy użyciu encji HTML podczas renderowania, więc jest to ochrona dogłębna, ale kluczowe jest kodowanie znaków na poziomie źródła — zrób to.

## Produkcja i dostarczanie

1. Skopiuj `assets/creative-review-template.html` do folderu wyjściowego partii jako `review.html` (np. `outputs/YYYY-MM-DD/review.html`).
2. Zamień obiekt `DATA` na rzeczywisty projekt — koncepcje, klatki, teksty, źródła i dowody. Wypełnij ścieżki `image` dla wszystkich wyrenderowanych klatek (zachowaj je względem pliku HTML, aby folder pozostał przenośny).
3. Sprawdź, czy renderuje się: otwórz go w przeglądarce, kliknij każdą kartę koncepcji, przełączniki platformy i konta oraz każdą klatkę w scenorysie.
4. Dostarcz: przekaż folder (html + `images/`) lub udostępnij go. W przypadku łącza klienta działa `vercel deploy` lub dowolny statyczny host — jest to pojedyncza strona z lokalnymi zasobami.

Trzymaj stronę przeglądu obok wyników w Markdown, a nie zamiast nich: `INDEX.md` i pliki poszczególnych koncepcji pozostają dokumentacją operatora i ścieżką audytu materiałów źródłowych i dowodów; `review.html` to warstwa zatwierdzania zbudowana na ich podstawie.

## Typowe błędy

- **Zbyt wiele koncepcji** — 2–4 karty to decyzja; 10 to menu, którego nikt nie kończy. Dokonaj selekcji przed prezentacją.
- **Ramki bez etykiety lub z etykietą treści** — etykietuj według zadania narracyjnego (`The proof`), a nie tego, co jest na zdjęciu (`Table screenshot`).
- **Brakujące lub nieuczciwe informacje o źródłach i dowodach** — każda koncepcja ujawnia to, co jest prawdziwe; dowód ilustracyjny jest oznaczony jako ilustracyjny.
- **Edycja kodu renderującego** – wszystko opiera się na danych; jeśli coś się nie pojawi, jest to pole `DATA`, a nie JS.
- **Bezwzględne ścieżki obrazów** — zachowaj względne ścieżki obrazów, aby folder wyjściowy mógł zostać spakowany, przeniesiony lub hostowany w nienaruszonym stanie.