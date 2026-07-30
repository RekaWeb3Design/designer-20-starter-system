# Vizuális minőség-küszöb

Ez a dokumentum a `/landing-design` **kötelező** minőségi mércéje. A
`creative-director`, `designer` és `builder` skill mindegyike beolvassa és
betartja. Minden szám ellenőrizhető — nem ízlés-kérdés.

## Miért létezik ez a fájl

Az első futásunk technikailag hibátlan oldalt adott — és **lapos** volt:
0 px sarokkerekítés, semmi árnyék, semmi mozgás, kép nélküli képhelyek,
egyenlő szövegblokkok. A rendszer pontosan azt csinálta, amit kértünk:
„diszkrét", „nem kártya-stílusú", „minimum". A tanulság: **a visszafogottság
nem ugyanaz, mint a jó design.** Egy dizájner-szemű kliens az elsőt kinevet,
a másodikat kifizeti.

**Alapszabály:** ha egy szekció screenshotja megkülönböztethetetlen egy
Bootstrap-sablonétól, nem kész.

---

## 1. Tipográfia — a legnagyobb hatású réteg

| Szint | Méret (clamp) | Szabály |
|---|---|---|
| Hero H1 | `clamp(2.75rem, 7vw, 6.5rem)` | Display betű, `line-height: 0.95–1.02`, `letter-spacing: -0.03em` |
| H2 | `clamp(2rem, 4vw, 3.5rem)` | `line-height: 1.05`, `letter-spacing: -0.02em` |
| H3 | `clamp(1.25rem, 2vw, 1.75rem)` | |
| Lead | `clamp(1.125rem, 1.6vw, 1.5rem)` | `line-height: 1.5`, max 60 karakter/sor |
| Törzs | `1rem–1.125rem` | `line-height: 1.6`, max 70 karakter/sor |
| Eyebrow / kicker | `0.75rem` | `letter-spacing: 0.18em`, uppercase, 700 |

**Kötelező:**
- A hero H1 és a törzsszöveg között **legalább 4× méretugrás** legyen. Ha a
  legnagyobb címsor 2rem, az oldal brosúra-szerű lesz.
- Nagy méretben (>3rem) **negatív letter-spacing** kötelező.
- Két betűtípus, nem több. Display + UI. Változó (variable) font előny.
- Legalább **egy** szekcióban legyen tipográfia-vezérelt hangsúly: kiemelt
  szó eltérő stílusban (dőlt display, aláhúzás-jelölés, színes szó).

**Tilos:** minden címsor ugyanaz a méret; teljes oldal középre zárva;
`text-align: center` 2-nél több szekcióban.

---

## 2. Ritmus és elrendezés — az aszimmetria nem hiba

- Szekció-térköz: mobil `64–80px`, desktop `120–180px`. Kevesebb = tömör
  és unalmas.
- Konténer: `1200–1320px`. Szerkesztett szövegsáv: `620–720px`.
- **Legalább 2 szekció törje meg a rácsot:** teljes szélességű (full-bleed)
  kép- vagy színsáv, offset/átlapoló elem, vagy 60/40 aszimmetrikus split.
- **Tilos** három egyforma kártya ikonnal egymás mellett („Our Services"
  minta). Ha három elem kell, legyen bento-jellegű: eltérő méret, egy
  dominánssal.
- Legalább egy helyen **átlapolás** (`negative margin` / `translate`), hogy
  a szekciók ne csak egymás alatt sorakozzanak.
- Egy hosszú szekció végén ne legyen üres 200px — a következő szekció
  kezdődjön vizuális horgonnyal (kép széle, színváltás, vonal).

---

## 3. Szín — 60/30/10, és legalább egy sötét pont

- 60% alap (papír/háttér), 30% másodlagos (szekció-blokkok), 10% akcent.
- **Kötelező legalább egy sötét (near-black vagy deep brand) szekció**
  valahol az oldal középső harmadában. Kontraszt nélkül nincs ritmus.
- Az akcentszínt legalább 3 helyen használd: CTA, link-hover, egy kiemelt
  tipográfiai elem.
- Engedett és javasolt: finom **gradient** (2 közeli tónus, max 8% eltérés),
  szín-tint kép fölé, `noise`/grain overlay 3–6% opacitáson.
- Minden szöveg-háttér párnál WCAG AA (4.5:1 törzs, 3:1 nagy szöveg).

---

## 4. Mélység — árnyék, radius, textúra

Radius-skála (válassz egy karaktert és tartsd):

| Karakter | Kártya | Gomb | Kép |
|---|---|---|---|
| Modern-soft | `16–24px` | `999px` vagy `12px` | `16–24px` |
| Editorial | `4–8px` | `4px` | `0–4px`, de **nagy** képek |
| Organic | `24–40px` | `999px` | `24px+`, aszimmetrikus is |

- **Legalább 2 szintű árnyék-token** (`sm`, `lg`), és tényleg használva:
  `0 1px 2px rgba(0,0,0,.06)` és `0 24px 48px -12px rgba(0,0,0,.18)`.
- 0 px radius + 0 árnyék + 0 textúra kombináció **tilos** — az a „nyers
  HTML" benyomás.
- Egy helyen legyen finom `backdrop-blur` (ragadós nav vagy kép fölötti
  címke).

---

## 5. Képek — a legnagyobb megtérülés

- A hero **full-bleed vagy legalább 60vh** magas képet használ. Kis, keretes
  hero-kép azonnal amatőr.
- Arányok: hero `21:9`/`16:9`, portré-blokk `4:5`, galéria `1:1` vagy `3:4`.
- Szöveg képen: **kötelező** gradient overlay
  (`linear-gradient(to top, rgba(0,0,0,.55), transparent 60%)`) vagy
  szín-tint — soha nem csupasz szöveg fotón.
- A képek `loading="lazy"` (a hero `eager` + `fetchpriority="high"`),
  `width`/`height` megadva, hogy ne ugráljon a layout.
- Legalább egy képnél legyen kezelés: duotone tint, `mix-blend-mode`,
  maszk vagy lekerekített aszimmetrikus forma.
- **Ha nincs kliens-fotó:** a képhely nem maradhat üres szürke kocka. A
  projekt `site/public/images/` mappájából dolgozz (lásd az ottani
  `KEPEK.md` slot-listát), és a demó/preview állapotot jelöld a
  dokumentációban — de a felület legyen kész.

---

## 6. Mozgás — visszafogott, de van

Kötelező minimum:
1. **Belépő reveal** görgetésre: `opacity 0→1` + `translateY 16–24px`,
   `500–700ms`, `cubic-bezier(0.16, 1, 0.3, 1)`, listáknál `60–80ms`
   staggerrel.
2. **Hover-állapot minden interaktív elemen**: `150–250ms`, és látható
   elmozdulás vagy szín/árnyék-változás (nem csak `opacity: .9`).
3. **Egy** nagyobb effekt a heroban vagy egy kiemelt szekcióban (lásd 7.).
4. `@media (prefers-reduced-motion: reduce)` — minden animáció kikapcsol.

Tilos: automatikus carousel, 1s-nál hosszabb belépő, egyszerre 3-nál több
párhuzamos effekt, végtelen villogás.

---

## 7. MCP-komponensek — kötelező minimum 4

A `builder` **legalább 4** komponenst a telepített UI library MCP-k
katalógusából emel be (nem emlékezetből újraír!). Ajánlott párosítások:

**Magic UI** (`list magicui components`):
- `aurora-text` / `animated-gradient-text` — hero kiemelt szó
- `text-animate` / `blur-fade` — szekció-belépők
- `marquee` — szezonális kínálat vagy logó-sáv
- `magic-card` — kiemelt kártya spotlight-tal
- `noise-texture` — grain overlay a teljes oldalra
- `progressive-blur` — kép- vagy galéria-szél lágyítása
- `scroll-progress` — olvasás-jelző
- `bento-grid` — a „három egyforma kártya" helyett

**React Bits** (`npx reactbits-dev-mcp-server`):
- `aurora`, `silk`, `beams`, `waves` — hero-háttér (WebGL, visszafogott
  paraméterekkel)
- `scroll-reveal`, `split-text`, `blur-text` — tipográfiai belépők
- `circular-gallery`, `bounce-cards` — galéria alternatívák

**shadcn/ui** — a funkcionális alap: `button`, `input`, `label`, `textarea`,
`accordion`, `dialog`. Ezek nem számítanak bele a 4-be: azok a
*primitívek*, nem a vizuális karakter.

A választást a brand-irány dönti el, nem a divat: kertészetnél `waves`/
`aurora` finom zöld tónussal igen, `hyperspeed`/`letter-glitch` nem.

---

## 8. Anti-slop lista — ezek azonnali elutasítás

- Minden szekció ugyanaz: cím középen, alatta 2 sor, alatta 3 kártya
- Ikon-körök generikus SVG-vel („check", „star", „leaf") minden blokkban
- Emoji ikon helyett
- `Lorem ipsum` vagy angol maradvány magyar oldalon
- Üres szürke `div` képhely helyett
- „PENDING" / „TODO" badge éles vagy prezentált felületen
- Gomb, aminek nincs hover-állapota
- 1440px-en 60%-nál kevesebb kitöltött képernyő a heroban
- Ugyanaz a `border: 1px solid #ddd` mindenen

---

## 9. Önellenőrzés — a builder ezt lefuttatja, mielőtt kész

Készíts screenshotot `1440px` és `375px` szélességen, és írd meg a
`VIZUALIS-ONELLENORZES.md`-t: minden pontnál `IGEN`/`NEM` + egy soros
indoklás. Ha bármelyik `NEM`, javítsd, és futtasd újra.

1. A hero legalább 60vh, és van benne valódi kép vagy nagy effekt?
2. A H1 és a törzs között legalább 4× méretugrás?
3. Van legalább 2 rács-törő szekció (full-bleed / aszimmetrikus / átlapoló)?
4. Van legalább egy sötét szekció?
5. Minden képhely ki van töltve valódi fotóval?
6. Van legalább 2 szintű árnyék, és radius-karakter következetes?
7. Legalább 4 MCP-komponens beépítve, felsorolva a fájlban?
8. Görgetés-reveal + hover minden interaktív elemen?
9. `prefers-reduced-motion` kezelve?
10. 375px-en nincs vízszintes scroll, és a hero H1 nem tör 4-nél több sorba?
11. Nincs „PENDING"/placeholder badge a látható felületen?
12. `npm run build` hibátlan, `npm run dev` fut?

---

## 10. A mérce egy mondatban

> Ha a kész oldal screenshotját fel lehetne tenni egy Webflow-showcase-be
> vagy egy Land-book-listába, és nem lógna ki lefelé — akkor kész.
> Ha „korrekt, de láttam már ezerszer" — akkor nem.
