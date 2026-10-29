# Narzędzia generatywne AI do kreacji reklam

Dokumentacja dotycząca korzystania z generatorów obrazów AI, generatorów wideo i narzędzi wideo opartych na kodzie do tworzenia materiałów wizualnych reklam na dużą skalę.

---

## Kiedy używać narzędzi generatywnych

| Potrzebuję | Kategoria narzędzia | Najlepsze dopasowanie |
|------|-------------------|--------------|
| Statyczne obrazy reklamowe (banery, społecznościowe) | Generowanie obrazu | ChatGPT Images 2.0, Nano Banana Pro, Flux, Ideogram |
| Obrazy reklamowe z nakładkami tekstowymi | Generowanie obrazu (z możliwością tekstu) | Ideogram, Nano Banana Pro |
| Krótkie reklamy wideo (6-30 s) | Generowanie wideo | Veo, Kling, Runway, Seedance |
| Reklamy wideo z lektorem | Generowanie wideo + głos | Veo (natywny) lub Runway + ElevenLabs |
| Ścieżki lektorskie do reklam | Generowanie głosu | ElevenLabs, OpenAI TTS, Cartesia |
| Wersje reklam w wielu językach | Generowanie głosu | ElevenLabs, PlayHT |
| Klonowanie głosu marki | Generowanie głosu | ElevenLabs, Resemble AI |
| Makiety i wariacje produktów | Generowanie wizerunku + referencje | Flux (wiele obrazów referencyjnych) |
| Szablonowe reklamy wideo na dużą skalę | Wideo oparte na kodzie | Remotion |
| Spersonalizowany film (imię, dane) | Wideo oparte na kodzie | Remotion |
| Odmiany spójne z marką | Generowanie obrazu + referencje stylu | Flux, ideogram, Nano Banana Pro |

---

## Generowanie obrazu

### Nano Banana Pro (Gemini)

Model generowania obrazów Google DeepMind, dostępny poprzez API Gemini.

**Najlepsze dla:** Wysokiej jakości obrazy reklam, wizualizacje produktów, renderowanie tekstu
**API:** Gemini API (Google AI Studio, Vertex AI)
**Cena:** ~0,04 USD/obraz (Gemini 2.5 Flash Image), ~0,24 USD/obraz 4K (Nano Banana Pro)

**Mocne strony:**
- Silne renderowanie tekstu na obrazach (logo, nagłówki)
- Natywna edycja obrazów (modyfikuj istniejące obrazy za pomocą podpowiedzi)
- Dostępne za pośrednictwem tego samego interfejsu API Gemini, który jest używany do generowania tekstu
- Obsługuje zarówno generowanie, jak i edycję w jednym modelu

**Przypadki użycia kreacji reklamowych:**
- Generuj obrazy reklam w mediach społecznościowych na podstawie opisów tekstowych
- Twórz warianty makiet produktu
- Edytuj istniejące obrazy reklam (zamień tła, zmień kolory)
- Generuj obrazy z wtopionym tekstem nagłówka

**Przykład API:**
```bash
# Using the Gemini API for image generation
curl -X POST "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-image:generateContent" \
  -H "Content-Type: application/json" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -d '{
    "contents": [{"parts": [{"text": "Create a clean, modern social media ad image for a project management tool. Show a laptop with a kanban board interface. Bright, professional, 16:9 ratio."}]}],
    "generationConfig": {"responseModalities": ["TEXT", "IMAGE"]}
  }'
```

**Dokumenty:** [Generowanie obrazów Gemini](https://ai.google.dev/gemini-api/docs/image-generation)

---

### Flux (Black Forest Labs)

Modele generowania obrazów z otwartymi wagami z dostępem API poprzez Replicate i natywny interfejs API BFL.

**Najlepsze do:** Fotorealistycznych obrazów, wariacji zgodnych z marką, generowania wielu odniesień
**API:** Replicate, BFL API, fal.ai
**Cena:** ~0,01–0,06 USD/obraz w zależności od modelu i rozdzielczości

**Warianty modelu:**
| Model | Prędkość | Jakość | Koszt | Najlepsze dla |
|-------|-------|---------|------|----------|
| Flux 2 Pro | ~6 sekund | Najwyższy | 0,015 USD/MP | Końcowe aktywa produkcyjne |
| Flux 2 Flex | ~22 sek | Wysoka + edycja | 0,06 USD/MP | Edycja iteracyjna |
| Flux 2 Dev | ~2,5 sek | Dobrze | 0,012 USD/MP | Szybkie prototypowanie |
| Flux 2 Klein | Najszybszy | Dobrze | Najniższy | Generowanie partii o dużej objętości |

**Mocne strony:**
- Odniesienie do wielu obrazów (do 8 obrazów) zapewniające spójną tożsamość we wszystkich reklamach
- Spójność produktu — ten sam produkt w różnych kontekstach
- Transfer stylu z obrazów referencyjnych
- Model Dev z otwartymi wagami do samodzielnego hostowania

**Przypadki użycia kreacji reklamowych:**
- Wygeneruj ponad 50 odmian reklam ze spójną tożsamością produktu/osoby
- Twórz obrazy produktu w kontekście (Twój SaaS na różnych urządzeniach)
- Dopasowanie stylu do istniejących zasobów marki przy użyciu obrazów referencyjnych
- Szybkie testy A/B wariantów obrazu

**Dokumenty:** [Replicate Flux](https://replicate.com/black-forest-labs/flux-2-pro), [BFL API](https://docs.bfl.ml/)

---

### Ideogram

Specjalizuje się w typografii i renderowaniu tekstu w obrazach.

**Najlepsze dla:** banerów reklamowych z tekstem, grafiką marki, obrazów reklam społecznościowych z nagłówkami
**API:** Ideogram API, Runware
**Cena:** ~0,06 USD/obraz (API), ~0,009 USD/obraz (subskrypcja)

**Mocne strony:**
- Najlepsze w swojej klasie renderowanie tekstu (dokładność ~90% vs ~30% w przypadku większości narzędzi)
- System referencyjny stylu (prześlij maksymalnie 3 obrazy referencyjne)
- 4,3 miliarda gotowych ustawień stylów zapewniających spójną estetykę marki
- Mocny w logo i typografii marki

**Przypadki użycia kreacji reklamowych:**
- Generuj banery reklamowe z tekstem nagłówka bezpośrednio na obrazie
- Twórz grafiki do mediów społecznościowych za pomocą nakładek tekstowych z marką
- Twórz wiele odmian projektu ze spójną typografią
- Generuj materiały promocyjne bez angażowania projektanta przy każdej iteracji

**Dokumenty:** [Ideogram API](https://developer.ideogram.ai/), [Ideogram](https://ideogram.ai/)

---

### Inne narzędzia obrazu

| Narzędzie | Najlepsze dla | Stan interfejsu API | Notatki |
|------|----------|------------|-------|
| **DALL-E 3** (OpenAI) | Ogólne generowanie obrazu | Oficjalne API | Zintegrowany z ChatGPT, dobre renderowanie tekstu |
| **Midjourney** | Artystyczne, bardzo estetyczne obrazy | Brak oficjalnego publicznego API | Oparty na Discordzie; istnieją nieoficjalne interfejsy API, ale istnieje ryzyko zakazów |
| **Stable Diffusion** | Własny hosting, konfigurowalny | Otwarte źródło | Najlepsze dla zespołów z infrastrukturą GPU |

---

## Generowanie wideo

### Google Veo

Model generowania wideo Google DeepMind, dostępny poprzez Gemini API i Vertex AI.

**Najlepsze dla:** Wysokiej jakości reklamy wideo z natywnym dźwiękiem, pionowe wideo do mediów społecznościowych
**API:** Gemini API, Vertex AI
**Cena:** ~0,15 USD/s (Veo 3.1 Fast), ~0,40 USD/s (Veo 3.1 Standard)

**Możliwości:**
- Do 60 sekund w rozdzielczości 1080p
- Natywna generacja dźwięku (dialogi, efekty dźwiękowe, ambient)
- Pionowy format 9:16 dla Stories/Reels/Shorts
- Skalowanie do 4K
- Tekst na wideo i obraz na wideo

**Przypadki użycia kreacji reklamowych:**
- Generuj krótkie reklamy wideo (15-30 sekund) z opisów tekstowych
- Twórz pionowe reklamy wideo dla TikTok, Reels, Short
- Twórz prezentacje produktów z lektorem
- Generuj wiele odmian wideo z tego samego monitu w różnych stylach
**Dokumenty:** [Veo na Vertex AI](https://cloud.google.com/vertex-ai/generative-ai/docs/video/overview)

---

### Kling (Kuaishou)

Generowanie wideo z jednoczesną generacją audiowizualną i sterowaniem kamerą.

**Najlepsze dla:** kinowych reklam wideo, dłuższych treści i wideo zsynchronizowanych z dźwiękiem
**API:** Kling API, PiAPI, fal.ai
**Ceny:** ~0,09 USD/s (za pośrednictwem strony trzeciej fal.ai)

**Możliwości:**
- Do 3 minut przy 1080p/30-48fps
- Jednoczesna generacja audiowizualna (Kling 2.6)
- Tekst na wideo i obraz na wideo
- Sterowanie ruchem i kamerą

**Przypadki użycia kreacji reklamowych:**
- Dłuższe filmy objaśniające produkt
- Filmowe filmy marki ze zsynchronizowanym dźwiękiem
- Animuj obrazy produktów w reklamach wideo

**Dokumenty:** [Programista Kling AI](https://klingai.com/global/dev/model/video)

---

### Runway

Platforma do generowania i edycji wideo z dużą możliwością sterowania.

**Najlepsze do:** Kontrolowanego generowania wideo, treści o spójnym stylu, edycji istniejącego materiału
**API:** Runway Developer Portal

**Możliwości:**
- Gen-4: Spójność postaci/scen we wszystkich ujęciach
- Pędzel ruchu i sterowanie kamerą
- Obraz na wideo z obrazami referencyjnymi
- Transfer stylu wideo na wideo

**Przypadki użycia kreacji reklamowych:**
- Generuj reklamy wideo ze spójnymi postaciami/produktami w różnych scenach
- Przenoszenie stylu istniejącego materiału filmowego w celu dopasowania go do estetyki marki
- Rozszerz lub zremiksuj istniejącą zawartość wideo

**Dokumenty:** [Runway API](https://docs.dev.runwayml.com/)

---

### Seedance 2.0 (ByteDance)
Model generowania wideo ByteDance z jednoczesną generacją audiowizualną i wejściami multimodalnymi.

**Najlepsze dla:** Szybkie i niedrogie reklamy wideo z natywnym dźwiękiem i multimodalnymi wejściami referencyjnymi
**API:** BytePlus (oficjalny), Replicate, WaveSpeedAI, fal.ai (strona trzecia); Format API zgodny z OpenAI
**Cena:** ~0,10–0,80 USD/min w zależności od rozdzielczości

**Możliwości:**
- Do 20 sekund w rozdzielczości do 2K
- Jednoczesna generacja audiowizualna (dwugałęziowy transformer dyfuzyjny)
- Tekst na wideo i obraz na wideo
- Do 12 plików referencyjnych dla wejścia multimodalnego
- Struktura API kompatybilna z OpenAI

**Przypadki użycia kreacji reklamowych:**
- Produkcja krótkich reklam wideo na dużą skalę przy niskich kosztach
- Reklamy wideo ze zsynchronizowanym lektorem i efektami dźwiękowymi w jednym przebiegu
- Generowanie wielu odniesień (zdjęcia produktów, zasoby marki, odniesienia do stylu)
- Szybka iteracja koncepcji reklam wideo

**Dokumenty:** [Seedance](https://seed.bytedance.com/en/seedance2_0)

---

### Higgsfield

Platforma do tworzenia wideo z pełnym stosem i sterowaniem kamerą kinową.

**Najlepsze dla:** Społecznościowe reklamy wideo, styl kinowy, treści przeznaczone przede wszystkim na urządzenia mobilne
**Platforma:** [higgsfield.ai](https://higgsfield.ai/)

**Możliwości:**
- Ponad 50 profesjonalnych ruchów kamerą (zoom, panorama, ujęcia z drona FPV)
- Animacja obrazu do wideo
- Wbudowana edycja, przejścia i klatki kluczowe
- Kompleksowy przepływ pracy: generowanie obrazu, animacja, edycja

**Przypadki użycia kreacji reklamowych:**
- Reklamy wideo w mediach społecznościowych o kinowym charakterze
- Animuj obrazy produktów do dynamicznego wideo
- Twórz wiele odmian wideo z różnymi stylami kamer
- Szybkie treści wideo do kampanii społecznościowych

---

### Porównanie narzędzi wideo

| Narzędzie | Maksymalna długość | Dźwięk | Rozdzielczość | API | Najlepsze dla |
|------|------|-------|------------|---------|----------|
| **Veo 3.1** | 60 sekund | Natywny | 1080p/4K | Gemini | Pionowe wideo społecznościowe |
| **Kling 2.6** | 3 minuty | Natywny | 1080p | Strona trzecia | Dłuższy film |
| **Runway Gen-4** | 10 sekund | Nie | 1080p | Oficjalne | Kontrolowany, konsekwentny |
| **Seedance 2.0** | 20 sekund | Natywny | 2K | Oficjalne + strona trzecia | Niedrogie duże ilości |
| **Higgsfield** | Różnie | Tak | 1080p | Internetowe | Społecznościowe, przede wszystkim mobilne |

---

## Generowanie głosu i dźwięku

Do nakładania realistycznych narracji na reklamy wideo, dodawania narracji do prezentacji produktów lub generowania dźwięku dla filmów renderowanych w technologii Remotion. Narzędzia te przekształcają skrypty reklamowe w naturalnie brzmiące ścieżki głosowe.

### Kiedy używać narzędzi głosowych

Wiele generatorów wideo (Veo, Kling, Seedance) zawiera teraz natywny dźwięk. Korzystaj z samodzielnych narzędzi głosowych, gdy potrzebujesz:

- **Głos w niemym wideo** — Runway Gen-4 i Remotion generują wideo bez dźwięku
- ** Spójność głosu marki** — Klonuj określony głos dla wszystkich reklam
- **Wersje wielojęzyczne** — Ten sam skrypt reklamowy w ponad 20 językach
- **Iteracja skryptu** — Nagraj ponownie narrację bez ponownego nagrywania wideo
- **Precyzyjna kontrola** — Dokładne wyczucie czasu, emocji i tempa

---

### ElevenLabs

Lider na rynku generowania realistycznego głosu i klonowania głosu.

**Najlepsze dla:** Większość naturalnie brzmiących podkładów głosowych, klonowanie głosu marki, wielojęzyczność
**API:** API REST z obsługą przesyłania strumieniowego
**Cena:** ~0,12-0,30 USD za 1000 znaków w zależności od planu; zaczyna się od 5 USD miesięcznie

**Możliwości:**
- Ponad 29 języków z naturalnym akcentem i intonacją
- Klonowanie głosu z krótkich klipów audio (natychmiastowe) lub dłuższych nagrań (profesjonalne)
- Kontrola emocji i stylu
- Przesyłanie strumieniowe do generowania w czasie rzeczywistym
- Biblioteka głosowa z setkami gotowych głosów

**Przypadki użycia kreacji reklamowych:**
- Generuj ścieżki lektorskie dla reklam wideo
- Sklonuj głos rzecznika marki dla wszystkich odmian reklamy
- Wyprodukuj tę samą reklamę w ponad 10 językach za pomocą jednego skryptu
- Test A/B różnych stylów głosu (autorytatywny, przyjacielski, pilny)

**Przykład API:**
```bash
curl -X POST "https://api.elevenlabs.io/v1/text-to-speech/{voice_id}" \
  -H "xi-api-key: $ELEVENLABS_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "text": "Stop wasting hours on manual reporting. Try DataFlow free for 14 days.",
    "model_id": "eleven_multilingual_v2",
    "voice_settings": {"stability": 0.5, "similarity_boost": 0.75}
  }' --output voiceover.mp3
```

**Dokumenty:** [ElevenLabs API](https://elevenlabs.io/docs/api-reference/text-to-speech)

---

### OpenAI TTS

Prosta i niedroga funkcja zamiany tekstu na mowę wbudowana w interfejs API OpenAI.

**Najlepsze dla:** Szybkie lektorstwo, opłacalność na dużą skalę, prosta integracja
**API:** OpenAI API (ten sam SDK co GPT/DALL-E)
**Ceny:** 15 USD za milion znaków (standard), 30 USD za milion znaków (HD); ~0,015 USD/min z gpt-4o-mini-tts

**Możliwości:**
- 13 wbudowanych głosów (bez klonowania niestandardowego)
- Wiele języków
- Przesyłanie strumieniowe w czasie rzeczywistym
- Opcja jakości HD
- Proste API — ten sam SDK, którego już używasz dla GPT

**Przypadki użycia kreacji reklamowych:**
- Szybki i tani lektor dla wersji roboczych/testowych reklam
- Obszerna narracja przy niskich kosztach
- Prototyp dźwięku reklamy przed inwestycją w głos premium

**Dokumenty:** [OpenAI TTS](https://platform.openai.com/docs/guides/text-to-speech)

---

### Cartesia Sonic

Generowanie głosu o bardzo niskim opóźnieniu, stworzone do zastosowań w czasie rzeczywistym.

**Najlepsze dla:** Głosu w czasie rzeczywistym, najniższego opóźnienia, ekspresji emocjonalnej
**API:** REST + przesyłanie strumieniowe WebSocket
**Ceny:** zaczynają się od 5 USD/miesiąc; płatność zgodnie z rzeczywistym użyciem od 0,03 USD/min

**Możliwości:**
- Czas do pierwszego dźwięku 40 ms (najszybszy w swojej klasie)
- Ponad 15 języków
- Ekspresja niewerbalna: śmiech, oddychanie, zmiany emocjonalne
- Sonic Turbo dla jeszcze mniejszych opóźnień
- Streaming API do generowania w czasie rzeczywistym

**Przypadki użycia kreacji reklamowych:**
- Podgląd reklamy w czasie rzeczywistym podczas iteracji twórczej
- Interaktywne filmy demonstracyjne z dynamiczną narracją
- Reklamy wymagające naturalnego śmiechu, westchnień lub reakcji emocjonalnych

**Dokumenty:** [Cartesia Sonic](https://docs.cartesia.ai/build-with-cartesia/tts-models/latest)

---

### Voicebox (otwarte oprogramowanie)

Bezpłatne studio syntezy głosu działające przede wszystkim lokalnie obsługiwane przez Qwen3-TTS. Alternatywa typu open source dla ElevenLabs.

**Najlepsze dla:** Bezpłatne klonowanie głosu, generowanie lokalne/prywatne, produkcja seryjna o zerowych kosztach
**API:** Lokalny interfejs API REST w `http://localhost:8000`
**Ceny:** Bezpłatnie (licencja MIT). Działa całkowicie na Twojej maszynie.
**Stos:** Tauri (Rust) + React + FastAPI (Python)

**Możliwości:**
- Klonowanie głosu z krótkich próbek audio za pośrednictwem Qwen3-TTS
- Obsługa wielu języków (angielski, chiński, więcej planowanych)
- Wielościeżkowy edytor osi czasu do tworzenia rozmów
- 4-5x szybsze wnioskowanie na Apple Silicon poprzez akcelerację MLX Metal
- Lokalny interfejs API REST do generowania programowego
- Brak zależności od chmury — całe przetwarzanie odbywa się na urządzeniu

**Przypadki użycia kreacji reklamowych:**
- Bezpłatne klonowanie głosu rzecznika marki we wszystkich odmianach reklam
- Wsadowe generowanie narracji bez kosztów za znak
- Generowanie prywatne/lokalne, gdy treść reklamy jest poufna lub jest przed publikacją
- Prototypowe odmiany głosu przed zaangażowaniem się w płatną usługę

**Przykład API:**
```bash
curl -X POST http://localhost:8000/generate \
  -H "Content-Type: application/json" \
  -d '{"text": "Stop wasting hours on manual reporting.", "profile_id": "abc123", "language": "en"}'
```

**Zainstaluj:** aplikacje komputerowe dla systemów macOS i Windows pod adresem [voicebox.sh](https://voicebox.sh) lub skompiluj ze źródła:
```bash
git clone https://github.com/jamiepine/voicebox.git
cd voicebox && make setup && make dev
```

**Dokumenty:** [GitHub](https://github.com/jamiepine/voicebox)

---

### Inne narzędzia głosowe

| Narzędzie | Najlepsze dla | Wyróżnik | API |
|------|----------|-------------------|---------|
| **PlayHT** | Duża biblioteka głosowa, niskie opóźnienia | Ponad 900 głosów, opóźnienie <300 ms, ultrarealistyczne | [play.ht](https://play.ht/) |
| **Resemble AI** | Klonowanie głosu w przedsiębiorstwie | Wdrożenie lokalne, zamiana mowy na mowę w czasie rzeczywistym | [resemble.ai](https://www.resemble.ai/) |
| **WellSaid Labs** | Głosy etyczne i bezpieczne pod względem komercyjnym | Głosy aktorów wynagradzanych, bezpieczne do użytku komercyjnego | [wellsaid.io](https://www.wellsaid.io/) |
| **Fish Audio** | Przyjazny dla budżetu, kontrola emocji | ~50-70% tańsze niż ElevenLabs, znaczniki emocji | [fish.audio](https://fish.audio/) |
| **Murf AI** | Zespoły nietechniczne | Studio oparte na przeglądarce, ponad 200 głosów | [murf.ai](https://murf.ai/) |
| **Google Cloud TTS** | Ekosystem Google, skala | Ponad 220 głosów, ponad 40 języków, umowy SLA dla przedsiębiorstw | [Google TTS](https://cloud.google.com/text-to-speech) |
| **Amazon Polly** | Ekosystem AWS, koszt | Głosy neuronowe, kontrola SSML, niski koszt przy dużej skali | [Amazon Polly](https://aws.amazon.com/polly/) |

---

### Porównanie narzędzi głosowych

| Narzędzie | Jakość | Klonowanie | Języki | Opóźnienie | Cena/1 tys. znaków |
|------|---------|---------|----------|---------|----------------|
| **ElevenLabs** | Najlepszy | Tak (natychmiastowy + profesjonalny) | 29+ | ~200 ms | 0,12–0,30 USD |
| **OpenAI TTS** | Dobrze | Nie | 13+ | ~300 ms | 0,015-0,030 USD |
| **Cartesia Sonic** | Bardzo dobrze | Nie | 15+ | ~40 ms | ~0,03 USD/min |
| **PlayHT** | Bardzo dobrze | Tak | 140+ | <300 ms | ~0,10-0,20 USD |
| **Fish Audio** | Dobrze | Tak | 13+ | ~200 ms | ~0,05-0,10 USD |
| **WellSaid** | Bardzo dobrze | Nie (głosy aktorów) | Angielski | ~300 ms | Ceny niestandardowe |
| **Voicebox** | Dobrze | Tak (lokalnie) | 2+ | Lokalne | Bezpłatny (otwarte oprogramowanie) |

### Wybieranie narzędzia głosowego

```
Need voiceover for ads?
├── Need to clone a specific brand voice?
│   ├── Best quality → ElevenLabs
│   ├── Enterprise/on-premise → Resemble AI
│   └── Budget-friendly → Fish Audio, PlayHT
├── Need multilingual (same ad, many languages)?
│   ├── Most languages → PlayHT (140+)
│   └── Best quality → ElevenLabs (29+)
├── Need free / open source / local?
│   └── Voicebox (MIT, runs on your machine)
├── Need cheap, fast, good-enough?
│   └── OpenAI TTS ($0.015/min)
├── Need commercially-safe licensing?
│   └── WellSaid Labs (actor-compensated voices)
└── Need real-time/interactive?
    └── Cartesia Sonic (40ms TTFA)
```

### Przebieg pracy: głos + wideo

```
1. Write ad script (use ad-creative skill for copy)
2. Generate voiceover with ElevenLabs/OpenAI TTS
3. Generate or render video:
   a. Silent video from Runway/Remotion → layer voice track
   b. Or use Veo/Seedance with native audio (skip separate VO)
4. Combine with ffmpeg if layering separately:
   ffmpeg -i video.mp4 -i voiceover.mp3 -c:v copy -c:a aac output.mp4
5. Generate variations (different scripts, voices, or languages)
```

---

## Film oparty na kodzie: Remotion
W przypadku dużych reklam wideo opartych na szablonach najlepszym rozwiązaniem jest Remotion. W przeciwieństwie do generatorów wideo AI, które tworzą unikalne wideo na podstawie podpowiedzi, Remotion wykorzystuje kod React do renderowania deterministycznego, idealnego dla marki wideo na podstawie szablonów i danych.

**Najlepsze dla:** odmian reklam opartych na szablonach, spersonalizowanych filmów, produkcji spójnej z marką
**Stos:** React + TypeScript
**Ceny:** Bezpłatnie dla osób indywidualnych/małych zespołów; licencja komercyjna wymagana dla 4+ pracowników
**Dokumenty:** [remotion.dev](https://www.remotion.dev/)

### Dlaczego Remotion dla reklam

| Generatory wideo AI | Remotion |
|----------------------------------|---------|
| Unikalne wyjście za każdym razem | Deterministyczny, doskonały w pikselach |
| Oparta na podpowiedziach, mniejsza kontrola | Pełna kontrola kodu nad każdą klatką |
| Trudno dokładnie dopasować markę | Dokładne kolory marki, czcionki, odstępy |
| Generowanie pojedynczo | Renderuj wsadowo setki z danych |
| Brak dynamicznego wstawiania danych | Personalizuj za pomocą nazw, cen i statystyk |

### Przypadki użycia kreacji reklamowych

**1. Dynamiczne reklamy produktów**
Podaj tablicę produktów JSON i wyrenderuj dla każdego unikalną reklamę wideo:
```tsx
// Simplified Remotion component for product ads
export const ProductAd: React.FC<{
  productName: string;
  price: string;
  imageUrl: string;
  tagline: string;
}> = ({productName, price, imageUrl, tagline}) => {
  return (
    <AbsoluteFill style={{backgroundColor: '#fff'}}>
      <Img src={imageUrl} style={{width: 400, height: 400}} />
      <h1>{productName}</h1>
      <p>{tagline}</p>
      <div className="price">{price}</div>
      <div className="cta">Shop Now</div>
    </AbsoluteFill>
  );
};
```

**2. Wersje wideo testu A/B**
Renderuj ten sam szablon z różnymi nagłówkami, wezwaniami do działania lub schematami kolorów:
```tsx
const variations = [
  {headline: "Save 50% Today", cta: "Get the Deal", theme: "urgent"},
  {headline: "Join 10K+ Teams", cta: "Start Free", theme: "social-proof"},
  {headline: "Built for Speed", cta: "Try It Now", theme: "benefit"},
];
// Render all variations programmatically
```

**3. Spersonalizowane filmy informacyjne**
Generuj filmy, w których zwracasz się do potencjalnych klientów po imieniu w celu dotarcia do klienta lub sprzedaży.

**4. Produkcja partii reklam społecznościowych**
Renderuj tę samą treść w różnych proporcjach:
- 1:1 do aktualności
- 9:16 dla Stories/Reels
- 16:9 dla YouTube

### Przepływ pracy z Remotion przy tworzeniu kreacji reklamowych

```
1. Design template in React (or use AI to generate the component)
2. Define data schema (products, headlines, CTAs, images)
3. Feed data array into template
4. Batch render all variations
5. Upload to ad platform
```

### Pierwsze kroki

```bash
# Create a new Remotion project
npx create-video@latest

# Render a single video
npx remotion render src/index.ts MyComposition out/video.mp4

# Batch render from data
npx remotion render src/index.ts MyComposition --props='{"data": [...]}'
```

---

## Wybór odpowiedniego narzędzia

### Drzewo decyzyjne

```
Need video ads?
├── Templated, data-driven (same structure, different data)
│   └── Use Remotion
├── Unique creative from prompts (exploratory)
│   ├── Need dialogue/voiceover? → Veo 3.1, Kling 2.6, Seedance 2.0
│   ├── Need consistency across scenes? → Runway Gen-4
│   ├── Need vertical social video? → Veo 3.1 (native 9:16)
│   ├── Need high volume at low cost? → Seedance 2.0
│   └── Need cinematic camera work? → Higgsfield, Kling
└── Both → Use AI gen for hero creative, Remotion for variations

Need image ads?
├── Need text/headlines in image? → Ideogram
├── Need product consistency across variations? → Flux (multi-ref)
├── Need quick iterations on existing images? → Nano Banana Pro
├── Need highest visual quality? → Flux Pro, Midjourney
└── Need high volume at low cost? → Flux Klein, Nano Banana
```

### Porównanie kosztów dla 100 odmian reklamy

| Podejście | Narzędzie | Przybliżony koszt |
|---------|------|--------------------------------|
| 100 statycznych obrazów | Nano Banana Pro | ~4-24 $ |
| 100 statycznych obrazów | Flux Dev | ~1-2 $ |
| 100 statycznych obrazów | Ideogram API | ~6 dolarów |
| Filmy 100 × 15 sekund | Veo 3.1 Fast | ~225 dolarów |
| Filmy 100 × 15 sekund | Remotion (szablon) | ~0 $ (renderowanie na własnym serwerze) |
| 10 głównych filmów + 90 filmów z szablonu | Veo + Remotion | ~22 $ + czas renderowania |

### Zalecany przepływ pracy przy produkcji reklam skalowanych

1. **Twórz główną kreację** za pomocą sztucznej inteligencji (Nano Banana, Flux, Veo) — wysokiej jakości, eksploracyjna
2. **Buduj szablony** w Remotion w oparciu o zwycięskie wzorce kreatywne
3. **Tworzenie wersji wsadowych** za pomocą Remotion przy użyciu danych (produkty, nagłówki, wezwania do działania)
4. **Iteruj** — użyj narzędzi AI dla nowych ujęć komunikacyjnych, Remotion dla skali

To hybrydowe podejście umożliwia twórczą eksplorację generatorów AI oraz spójność i skalę renderowania opartego na kodzie.

---

## Specyfikacje obrazu specyficzne dla platformy

Generując obrazy do reklam, poproś o podanie prawidłowych wymiarów:

| Platforma | Umieszczenie | Proporcje | Zalecany rozmiar |
|---------|-----------|------------|--------------------------------|
| Meta Feed | Pojedynczy obraz | 1:1 | 1080x1080 |
| Meta Stories/Reels | Pionowe | 9:16 | 1080x1920 |
| Meta-karuzela | Kwadrat | 1:1 | 1080x1080 |
| Google Display | Poziomy | 1,91:1 | 1200x628 |
| Google Display | Kwadrat | 1:1 | 1200x1200 |
| Kanał LinkedIn | Poziomy | 1,91:1 | 1200x627 |
| Kanał LinkedIn | Kwadrat | 1:1 | 1200x1200 |
| Kanał TikTok | Pionowe | 9:16 | 1080x1920 |
| Kanał Twittera/X | Poziomy | 16:9 | 1200x675 |
| Karta Twittera/X | Poziomy | 1,91:1 | 800x418 |

Uwzględnij te wymiary w monitach generowania, aby uniknąć konieczności przycinania lub zmiany rozmiaru.