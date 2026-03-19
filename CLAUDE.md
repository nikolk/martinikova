# Martiníková.cz — projektová dokumentace

Osobní web Nikol Martiníkové. Jediný soubor: `index.html` (veškerý HTML, CSS i JS inline).

## Stack

- Čistý HTML/CSS/JS — žádný framework, žádný build step
- Fonty: **Bricolage Grotesque** (nadpisy, 700/800) + **DM Sans** (text, 400/500) — Google Fonts
- Deploy: GitHub → Vercel (auto-deploy z `main`)
- Repo: https://github.com/nikolk/martinikova

## Barevná paleta

| Proměnná | Hex | Použití |
|---|---|---|
| `--cream` | `#fdf5f0` | Pozadí stránky |
| `--ink` | `#1e0d10` | Tmavé sekce (O mně, Kontakt), základní text |
| `--ember` | `#660033` | Akcent — tlačítko, hover efekty, rámeček fotky |
| `--grove` | `#daa520` | Zlatá — zvýrazněné texty (`.about-accent`), šipky v kartách |
| `--sun` | `#2e6f40` | Zelená — definovaná, zatím nevyužitá |
| `--ink-soft` | `#f5e8e4` | Text na tmavém pozadí |

## Struktura sekcí

### `#uvod` — Hero
- Flex layout, foto vlevo (kruh s ember rámečkem, `clamp(180px, 22vw, 280px)`), text vpravo
- Fotka: `nikolm.png`, `object-position: center top`
- Na mobilu (`≤768px`): sloupcové, text centrovane

### `#o-mne` — O mně
- Tmavé pozadí (`--ink`), dvousloupcový grid
- Levý sloupec: nadpis h2 + `.about-accent` odstavce (žlutě, Bricolage Grotesque 700) + body text
- Pravý sloupec: tagy `.tag-past` (šedé) a `.tag-now` (zlaté)

### `#nabidka` — Nabídka
- Světlé pozadí (`--cream`), dvě karty vedle sebe
- Karty mají hover efekt (translateY + ember pruh nahoře)
- Ikony: inline SVG (Lucide styl, stroke 1.8), ne emoji
  - Karta 1 (Posila projektu): users ikona, `--grove` barva
  - Karta 2 (AI onboarding): sparkles ikona, `--ember` barva

### `#kontakt` — Kontakt
- Tmavé pozadí, centrovaný layout
- Dva kontaktní linky: email + LinkedIn

## CSS konvence

- Responzivní hodnoty přes `clamp()` — vždy min/viewport/max
- Scroll animace: třída `.reveal` (opacity 0 + translateY 32px), JS IntersectionObserver přidá `.visible`
- Zpoždění: `.reveal-delay-1/2/3` (0.1/0.2/0.3s)
- Breakpointy: `768px` (tablet/mobil), `480px` (malý mobil)

## Soubory

```
index.html     — celý web
nikolm.png     — profilová fotka (portrét, podzimní příroda)
.gitignore     — ignoruje .DS_Store, brainstorming*
CLAUDE.md      — tento soubor
```
