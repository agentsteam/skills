# Agentsteam Skills

Polskie umiejętności AI dla firm usługowych. Te same pakiety są dostępne w katalogu Hyperapp jako ZIP.

## Instalacja

```sh
npx skills add https://github.com/agentsteam/skills --skill pomysly-marketingowe
```

Wyświetl wszystkie umiejętności: `npx skills add agentsteam/skills --list`.

## Użycie bez instalacji

```sh
npx skills use https://github.com/agentsteam/skills --skill pomysly-marketingowe
```

## Pakiety

- [Pomysły marketingowe](skills/pomysly-marketingowe/SKILL.md) — `pomysly-marketingowe`
- [Strategia treści](skills/strategia-tresci/SKILL.md) — `strategia-tresci`
- [Treści strony](skills/tresci-strony/SKILL.md) — `tresci-strony`
- [Redakcja treści](skills/redakcja-tresci/SKILL.md) — `redakcja-tresci`
- [Audyt SEO strony](skills/audyt-seo/SKILL.md) — `audyt-seo`
- [Widoczność w odpowiedziach AI](skills/widocznosc-w-ai/SKILL.md) — `widocznosc-w-ai`
- [Strony SEO z szablonu](skills/strony-seo-z-szablonu/SKILL.md) — `strony-seo-z-szablonu`
- [Psychologia marketingu](skills/psychologia-marketingu/SKILL.md) — `psychologia-marketingu`
- [Kreacje reklamowe](skills/kreacje-reklamowe/SKILL.md) — `kreacje-reklamowe`
- [Wiadomość B2B](skills/wiadomosc-b2b/SKILL.md) — `wiadomosc-b2b`

## Licencje i źródła

Każdy pakiet zawiera plik LICENSE.txt z licencją MIT oraz skill-manifest.json z informacjami o źródłach i adaptacji.

## Aktualizacja

Pakiety eksportowane z katalogu w repozytorium Hyperapp:

```sh
vp exec tsx scripts/export-customer-skills.ts <ścieżka-do-tego-repozytorium>
```
