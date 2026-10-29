# Dostarczalność cold maila

Najlepszy cold mail nic nie da, jeśli wyląduje w spamie. Dostarczalność jest konfigurowana przed pierwszą wysyłką i sprawdzana co tydzień później. W tym dokumencie opisano konfigurację wysyłania, zasady dostawców skrzynek pocztowych, limity wolumenu wysyłki, rozgrzewanie, monitorowanie i moment zatrzymania.

Liczby pochodzą głównie z własnych wytycznych dostawców infrastruktury wysyłającej i dostawców skrzynek pocztowych. Dostawcy skrzynek pocztowych zmieniają zasady egzekwowania zasad bez powiadomienia, dlatego należy traktować dane liczbowe jako punkt wyjścia i pozwolić zadecydować własnym testom rozmieszczenia.

## Reguły Google, Yahoo i Microsoft

| Dostawca | Czego wymaga | Egzekucja |
|---------|--------------------------------|------------|
| **Gmail** | SPF i DKIM dla każdego; w przypadku nadawców masowych (ponad 5000 wiadomości dziennie do osobistego Gmaila), także DMARC, wyrównanie, anulowanie subskrypcji poczty marketingowej jednym kliknięciem i skargi dotyczące spamu poniżej 0,3% | Od listopada 2025 r. poczta niezgodna z wymaganiami jest odrzucana na stałe, a nie tymczasowo. Gdy zostaniesz sklasyfikowany jako nadawca masowy, status będzie stały |
| **Yahoo** | Spełnia wymagania Google | Od 2024 |
| **Microsoft** (Outlook.com, Hotmail, Live) | SPF, DKIM i DMARC dla nadawców powyżej 5000 dziennie | Od 5 maja 2025 r. poczta niezgodna z wymogami jest odrzucana (`550 5.7.515`) |
Reguły Google dotyczące nadawców zbiorczych dotyczą poczty wysyłanej na osobiste konta Gmail, a nie na adresy firmowe w Google Workspace. Program cold mailingu poniżej 5000 wiadomości dziennie nie jest technicznie „nadawcą masowym”. I tak postępuj zgodnie z zasadami: opisują one, co nagradza każdy filtr, a próg reklamacji dotyczy każdego.

**Wskaźnik skarg:** utrzymuj skargi dotyczące spamu na poziomie poniżej 0,1% i nigdy nie osiągaj 0,3%. Praktycy zgłaszają spadek wysyłania w Workspace znacznie wcześniej niż 0,3%.

## Konfiguracja wysyłania

**Nigdy nie wysyłaj cold maili ze swojej domeny podstawowej.** Jedna zła kampania może uszkodzić domenę, od której zależą Twoi klienci, faktury i resetowanie haseł.

1. **Kup domeny dodatkowe**, które są oczywiście Twoje (`getacme.com`, `acmehq.com`, `tryacme.com`). Przekieruj każdego na swoją stronę główną.
2. **Uwierzytelnij każdą domenę:** SPF, DKIM i DMARC (zacznij od `p=none` z raportowaniem), dopasowane do domeny From. Dodaj niestandardową domenę śledzenia tylko wtedy, gdy śledzisz kliknięcia (patrz Śledzenie poniżej).
3. **Utwórz 2–3 skrzynki pocztowe na domenę**, każda z realistycznie wyglądającą osobą z imieniem, zdjęciem i podpisem. Nigdy nie używaj aliasów pojedynczej skrzynki pocztowej; zarówno Google, jak i Microsoft traktują to jako nadużycie swoich warunków.
4. **Kupuj skrzynki pocztowe wyłącznie od odpowiednio licencjonowanych dzierżawców.** Pod koniec 2025 r. Google według doniesień zawiesił dużą liczbę odsprzedawanych skrzynek pocztowych Workspace zbudowanych na kontach edukacyjnych, non-profit lub starszych kontach. Tanie skrzynki odbiorcze „sprzedawcy” są w najlepszym przypadku jednorazowe.
5. **Jeśli to możliwe, dopasuj dostawcę do potencjalnych klientów.** Skrzynki pocztowe hostowane przez Google dla odbiorców w Google Workspace (większość startupów i SaaS), hostowane przez firmę Microsoft dla odbiorców korporacyjnych na platformie Microsoft 365. Dostawcy zgłaszają lepsze rozmieszczenie skrzynek odbiorczych, gdy oba elementy są zgodne. Sprawdź host poczty potencjalnego klienta w jego rekordzie MX.

### Obliczanie wolumenu wysyłki

| Ustawienie | Punkt wyjścia |
|------------|----------------|
| Wiadomości dziennie na skrzynkę | 20–30 (hostowane przez Google); test niższy dla hostowanych przez firmę Microsoft, gdzie raporty operatorów za rok 2026 wahają się od pojedynczych cyfr do dziesiątek |
| Skrzynki pocztowe na domenę | 2–3 |
| Dzienny wolumen | Liczba skrzynek × liczba wiadomości na skrzynkę |

Przykład: 500 przesyłek dziennie ≈ 20 skrzynek pocztowych po 25 każda ≈ 7–10 domen. Kontynuacje wliczają się do dziennego wolumenu.

Zaplanuj zapas. Utrzymuj 10–20% dodatkowych domen rozgrzanych i nieużywanych, aby spalona domena mogła zostać wymieniona bez zatrzymywania programu.

## Rozgrzewka

Nowe skrzynki pocztowe potrzebują 3–4 tygodni, zanim osiągną pełny wolumen cold mailingu:
- **Tygodnie 1–2:** tylko rozgrzewka i kilka prawdziwych e-maili do osób, które prawdopodobnie odpowiedzą.
- **Tygodnie 3–4:** rozpocznij cold mailing od 5–10 dziennie na skrzynkę pocztową i stopniowo je zwiększaj.
- **Następnie:** włącz w tle lekką rozgrzewkę.
Sieci rozgrzewające nadal pomagają nowym skrzynkom, ale skrzynka, której jedyne interakcje pochodzą z rozgrzewania, tworzy rozpoznawalny wzorzec. Prawdziwe odpowiedzi są najsilniejszym sygnałem reputacji, co jest kolejnym powodem, dla którego warto pisać e-maile, na które ludzie odpowiadają.

## Sam e-mail

- **Zwykły tekst.** Żadnych obrazów, żadnych szablonów HTML, żadnych załączników.
- **Brak linku w pierwszym e-mailu,** i maksymalnie jeden link w kolejnych. Nigdy nie używaj skracaczy linków.
- **Wyłącz śledzenie otwartych przesyłek.** Ochrona prywatności Apple Mail sprawia, że ​​otwarcia stają się bezsensowne, a sam piksel śledzący jest sygnałem spamu. W jednym z dużych zbiorów danych nadawców stwierdzono, że odsetek odpowiedzi wzrósł mniej więcej dwukrotnie, gdy wyłączone było śledzenie otwarte. Zamiast tego mierz odpowiedzi.
- **Wyłącz śledzenie kliknięć**, chyba że tego potrzebujesz i tylko w przypadku niestandardowej domeny śledzącej.
- **Poniżej około 80 słów** w przypadku pierwszego e-maila.
- **Różnicuj tekst.** Identyczne treści w tysiącach wysłań wyglądają jak przesyłki masowe. Tekst dopasowany do segmentu i prawdziwa personalizacja naprawiają to w naturalny sposób. Zachowaj Spintax jako ostateczność.
- **Wiersz rezygnacji.** Wiersz zwykłego tekstu („Jeśli to nie dotyczy, odpowiedz „nie”, a nie będę się kontaktować”) plus Twój adres pocztowy w podpisie. CAN-SPAM wymaga obu; zobacz odniesienia do zgodności umiejętności poszukiwania klientów.

## Sprawdź przed wysłaniem
Odbicia to najszybszy sposób na uszkodzenie domeny. Utrzymuj je poniżej 2% na kampanię; poniżej 1% jest najlepszy w swojej klasie. Jeden dzień z kilkuprocentowymi odbiciami może skutkować recenzją w Google.

- Sprawdź każdą listę przed przesłaniem i ponownie zweryfikuj wszystkie listy starsze niż około tygodnia.
- Obsługuj domeny typu catch-all zgodnie z polityką. Zobacz informacje dotyczące pozyskiwania i wzbogacania umiejętności poszukiwania klientów.
- Wstrzymaj automatycznie dowolną kampanię, gdy jej współczynnik odrzuceń przekroczy 2%.

## Monitorowanie

| Sprawdź | Jak | Kiedy |
|-------|-----|------|
| Odsetek wiadomości trafiających do skrzynki odbiorczej | Testy na kontrolnych adresach (MailReach, GlockApps lub wbudowany test Twojego narzędzia do wysyłania) | Przed każdą nową kampanią i co tydzień |
| Reputacja domeny | Narzędzia Google Postmaster; Microsoft SNDS | Co tydzień |
| Współczynnik odrzuceń | Narzędzie do wysyłania na kampanię i na skrzynkę pocztową | Codziennie |
| Skargi na spam | Narzędzia pocztowe; odpowiedzi zawierające „spam” lub „stop” | Co tydzień |
| Listy zablokowanych | Narzędzie do sprawdzania listy zablokowanych dla każdej domeny wysyłającej | Co tydzień |
| Uwierzytelnianie | Raporty zbiorcze DMARC | Miesięczne |

## Zasady stop-loss

Zdecyduj o nich przed uruchomieniem i egzekwuj je automatycznie, jeśli pozwala na to Twoje narzędzie:

| Wyzwalacz | Akcja |
|--------|--------|
| Współczynnik odrzuceń w kampanii powyżej 2% | Wstrzymaj kampanię i ponownie zweryfikuj listę |
| Odsetek wiadomości trafiających do skrzynki odbiorczej poniżej ~70% w skrzynce pocztowej lub domenie | Wyciągnij go z obrotu, wróć do rozgrzewki, zbadaj |
| Liczba skarg dotyczących spamu zbliża się do 0,1% | Wstrzymaj, zmniejsz liczbę, sprawdź targetowanie i treść |
| Domena pojawia się na głównej liście zablokowanych | Przestań z niego wysyłać; doprowadź do usunięcia domeny z listy blokad albo wycofaj domenę |
| Współczynnik odpowiedzi poniżej ~1% po ponad 300 wysyłkach | Zatrzymaj kampanię; kierowanie lub oferta jest błędna, a większy wolumen pogarsza sytuację |

## Typowe błędy

- Wysyłanie z domeny podstawowej
- Kupowanie najtańszych skrzynek pocztowych sprzedawcy i utrata ich wszystkich na raz
- Pominięcie weryfikacji „ponieważ dostawca danych to zweryfikował”
- Pozostawienie włączonego śledzenia i optymalizacja pod kątem liczby, która nie jest prawdziwa
- Zwiększanie wolumenu wysyłki w celu naprawienia niskiego współczynnika odpowiedzi
- Jednoczesna rozgrzewka i cold mailing z pełnym wolumenem od pierwszego dnia

## Narzędzia

| Praca | Opcje |
|-----|--------|
| Wysyłanie i rotacja skrzynek pocztowych | Instantly, Smartlead, lemlist, EmailBison, Salesforge |
| Udostępnianie domeny i skrzynki pocztowej | Inframail, Maildoso, Mailforge, Truelist Outbound (domeny zarządzane, skrzynki pocztowe i dedykowany adres IP z wymuszoną rampą), Zapmail lub Google Workspace i bezpośrednio Microsoft 365 |
| Testy trafiania do skrzynki odbiorczej | GlockApps, MailReach lub wbudowany test Twojego narzędzia do wysyłania (Instantly go oferuje) |
| Reputacja | Narzędzia Google Postmaster, Microsoft SNDS |
| Monitorowanie DMARC | EasyDMARC, dmarcian, Valimail |
| Weryfikacja listy | Bouncer, MillionVerifier, NeverBounce, Truelist, ZeroBounce i inne |

Przewodniki konfiguracji: [rejestr narzędzi](https://github.com/coreyhaines31/marketingskills/blob/e85f3cbc2e4a79bf33b2a12e9bdd9087d414735b/tools/REGISTRY.md).