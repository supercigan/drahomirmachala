# DNA — Drahomír Machala
**Typ projektu:** Jednostránkový web — autoservis / podvozkový specialista
**Datum:** 2026-03-26
**Repo:** https://github.com/supercigan/drahomirmachala

---

## Vizuální archetype
**Světlý profesionální specialista.** Čistý, důvěryhodný, osobní. Kontrastuje s tmavými minimalistickými weby ze portfolia (DH-servis, AUROPS, MANITECH). Evokuje řemeslnou přesnost a transparentnost — ne agresivní workshop, ale zkušený odborník.

---

## Barevná paleta

| Název | Hex | Použití |
|-------|-----|---------|
| Warm White | `#FAFAF8` | Hlavní pozadí |
| Warm Sand | `#F0E7D8` | Sekce: O mně, Ceník |
| Burnt Orange / Russet | `#B8410A` | Primární akcent — tlačítka, ikony, nadpisy, hero panel |
| Accent Dark | `#8C2F06` | Hover stav tlačítek |
| Accent Light | `#FDF0EA` | Pozadí ikonových boxů, notice strip |
| Dark | `#1A1A1A` | Nadpisy, footer, trust strip |
| Text | `#3D3D3D` | Tělo textu |
| Muted | `#7A7A7A` | Popisky, sekundární text |
| Border | `#E8E0D5` | Ohraničení karet, tabulek |

**Proč burnt orange:** Teplý, zemitý tón — evokuje kov, preciznost, ručnímu řemeslu blízký. Nepoužit v žádném z 10 předchozích DNA projektů. Odlišný od jasné AUROPS oranžové (#F05F2E).

---

## Typografie

| Role | Font | Váha |
|------|------|------|
| Nadpisy | Space Grotesk | 700, 800 |
| Tělo | Figtree | 400, 500, 600 |

**Proč tyto fonty:**
- **Space Grotesk** — geometrický, mírně technický charakter. Ostrý, moderní, nezaměnitelný. V celém portfoliu dosud nepoužit.
- **Figtree** — humanistický, lehce kulatý bezpatkový. Dobře čitelný v malých velikostech. V portfoliu nepoužit.

---

## Layout & Struktura sekcí

```
NAV (fixed, blur backdrop, scrolled border)
│
├── HERO (min-height: 100vh, flex split)
│   ├── Levý panel 62% — text, badge, nadpis, popis, CTA
│   └── Pravý panel 38% — accent background, velké "30+", rok 1994
│       └── clip-path: polygon(6% 0, 100% 0, 100% 100%, 0 100%) — šikmý přechod
│
├── TRUST STRIP (dark background, 5 items v řadě)
│
├── O MNĚ (sand background)
│   ├── Levý sloupec — text + notice banner (nová adresa)
│   └── Pravý sloupec — 4 stat karty s counter animací
│
├── SLUŽBY (white background)
│   ├── Header — tag + nadpis + subtitle pod ním
│   └── Grid 2×2 — 4 karty s top-border scaleX animací při hover
│
├── CENÍK (sand background)
│   └── max-width: 720px centered — notice box + 2 price items
│
├── KONTAKT (white background)
│   ├── Levý sloupec — telefon, email, adresa, hodiny
│   └── Pravý sloupec — Google Maps iframe
│
└── FOOTER (dark background) — IČ, sídlo, copyright
```

---

## Klíčové designové prvky

### Hero split panel
- **Nový pattern v portfoliu** — šikmý clip-path pravého panelu vytváří dynamický přechod
- Velké číslo "30+" jako okamžitý trust signal
- Opacity 0 → 1 transition s 0.25s delay na pravém panelu
- Staggered text reveal na levém panelu (každý řádek zvlášť)

### Stat karty s counter animací
- IntersectionObserver spouští counter při vstupu do viewportu
- `requestAnimationFrame` s ease-out cubic — plynulé odrolování
- Ikony: clock (roky), activity/EKG (Beissbarth diagnostika), truck (hmotnost), kalendář (rok praxe)

### Service cards
- Top-border scaleX animace (transform-origin: left) při hover
- Čísla 01–04 jako typografické záhlaví
- Bez ghost textu, bez spotlight efektu — odlišné od ostatních projektů

### Notice banner
- Levý oranžový border + warm background pro upozornění na změnu adresy
- Umístěn v sekci O mně — neintruzivní ale viditelný

### Trust strip
- Tmavý pruh pod hero — 5 bodů důvěry v jedné řadě
- `justify-content: space-between` — rovnoměrné rozložení

---

## Animace

| Prvek | Animace |
|-------|---------|
| Hero badge | fadeUp 0.55s, delay 80ms |
| Hero title lines | slideUp 0.7s cubic-bezier(.16,1,.3,1), stagger 170ms/řádek |
| Hero subtitle | fadeUp 0.6s, delay 660ms |
| Hero buttons | fadeUp 0.6s, delay 780ms |
| Hero right panel | fadeIn 0.9s, delay 260ms |
| Stat cards | IntersectionObserver, counter 1400ms ease-out cubic |
| Sekce | IntersectionObserver fadeUp + delay třídy d1–d5 |
| Hover karty | translateY(-5px) + box-shadow + border-color 0.3s |

---

## Responsivita

| Breakpoint | Změna |
|-----------|-------|
| 900px | Hero stacking (sloupce → řady), about/services/contact na 1 sloupec |
| 640px | Hamburger menu, menší sekce padding, hero-right min-height 320px |
| 400px | Tlačítka full-width column, price items stacked |

---

## Co fungovalo dobře
- Split hero s clip-path je vizuálně silné a neopakuje se v portfoliu
- Světlé téma s burnt orange — svěží kontrast k tmavým minimalistickým projektům
- Space Grotesk dává webu technický ale přátelský charakter
- Counter animace na stat kartách přidává interaktivitu bez zbytečné komplexity
- Notice banner pro adresu je elegantní řešení komunikace změny

## Co příště jinak
- Hero left padding: `clamp(2rem, calc((100vw - 1200px) / 2 + 2rem), 9rem)` — dobré zarovnání s nav, lze použít jako vzor pro budoucí light-theme split heroy
- Mobilní hero-right: při nízkém viewportu (< 700px) je content těsně nad hranou — zvážit menší font čísla nebo více padding-top na hero-left
- Google Maps embed bez API klíče funguje spolehlivě pro jednoduché zobrazení lokace
