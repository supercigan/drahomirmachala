# Drahomír Machala — Diagnostika & Opravy Podvozků
**Datum zahájení:** 2026-03-26
**Poslední update:** 2026-03-26

---

## Co je hotovo
- [x] Analýza původního webu (drahomirmachala.cz) — extrahovány všechny sekce, služby, kontakt, ceník
- [x] Analýza DNA všech 10 předchozích projektů — identifikovány vzory k vyvarování
- [x] Návrh unikátní vizuální identity
- [x] Vytvořen index.html — kompletní jednostránkový web
- [x] Screenshot review + oprava všech vizuálních chyb:
  - Hero text zarovnán s navigací (clamp padding)
  - Ikony opraveny — crosshair pro geometrii, activity monitor pro Beissbarth, kalendář pro 1994
  - Services header layout — subtitle pod nadpis (ne vedle)
  - Mobilní hero-right min-height 320px, viditelná "V OBORU OD / 1994"
  - Services gap zmenšen
- [x] GitHub push — https://github.com/supercigan/drahomirmachala (2 commity)
- [x] DNA soubor vytvořen

---

## Reálné informace z původního webu
- **Majitel:** Drahomír Machala
- **Tagline:** Profesionální diagnostika & komplexní opravy podvozků
- **Telefon:** +420 606 468 733
- **Email:** info@drahomirmachala.cz (originál má překlep: drahormimachala)
- **Provozovna (od 1.7.2025):** Zerzavice 1706, 686 01 Staré Město (areál Povodí Moravy)
- **Sídlo:** Na Kopečku 483, 686 01 Uherské Hradiště
- **IČ:** 46202773
- **Zkušenosti:** 30+ let, přístroje Beissbarth
- **Otevírací doba:** Po–Pá, výhradně na telefonickou objednávku
- **Ceník:** Geometrie od 1 500 Kč, práce 700 Kč/hod, není plátce DPH
- **Vozidla:** osobní, SUV, off-road, užitková do 3,5 t

---

## Důležitá rozhodnutí
- Překlep v emailu opraven: drahormimachala → drahomirmachala
- Nová adresa od 1.7.2025 prominentně zobrazena jako notice banner v sekci O mně
- Hero: split layout 62%/38% s velkým "30+" v accent panelu — silný vizuální statement
- Světlé téma — kontrast k posledním 3 tmavým projektům portfolia
- Space Grotesk + Figtree — v portfoliu dosud nepoužité
- Burnt orange #B8410A — nepoužit v žádném z 10 předchozích DNA projektů
- Counter animace v stat kartách (IntersectionObserver + requestAnimationFrame)
- Nevyužity: canvas animace, ghost text, diagonální linky, radial glow

---

## Příští kroky
- [ ] Vercel deploy (auto přes GitHub push — zkontrolovat dashboard)
- [x] DNA soubor → C:/Users/karel/DNA-projekty/DNA-drahomirmachala.md
