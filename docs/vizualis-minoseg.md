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

## 9. Reszponzivitás — négy méret, nem kettő

Nem „mobilbarát" a cél, hanem **négy szándékosan megtervezett méret**. Minden
projekt ezeken épül és ezeken ellenőrződik:

| Sáv | Szélesség | Elrendezés |
|---|---|---|
| **Mobil** | 320–767px | 1 hasáb; sticky elemek minimalizálva; a hero szövege nem lóghat ki a képből (`object-position` igazítva) |
| **Tablet** | 768–1023px | 2 hasáb ott, ahol értelme van; a 3-elemű sorok 2+1-re bomlanak, NEM zsugorodnak egyformán |
| **Desktop** | 1024–1439px | a teljes tervezett elrendezés |
| **Nagy képernyő** | ≥1440px (1920/2560 is!) | a tartalom **nem úszik el**: konténer `contentMax`, DE a full-bleed médiák a teljes szélességet használják, és a gutterek nőnek |

**Ellenőrizhető szabályok:**
- **Nincs vízszintes scroll** egyetlen szélességen sem — teszt: 320, 375, 768,
  1024, 1440, 1920.
- **Érintőfelület minimum 44×44px**, és két érinthető elem között legalább 8px.
- A szövegsor **soha nem hosszabb 70 karakternél**, akkor sem, ha 2560px-en
  nézik. Nagy képernyőn a felesleges hely gutterbe és médiába megy, nem a
  sorhosszba.
- 1920px-en a hero **nem lehet üres**: vagy full-bleed a média, vagy a
  tipográfia skálázódik vele (a `clamp()` felső határa elég nagy legyen).
- A képek `srcset`/`sizes` attribútummal mennek, hogy mobilon ne töltsön le
  2400px-es fájlt.
- Semmilyen funkció nem érhető el **kizárólag hoverrel** — érintőképernyőn
  nincs hover.
- A táblázatok és a kódblokkok saját `overflow-x: auto` konténerben
  görgethetők; az oldal törzse soha nem görög vízszintesen.
- **Full-bleed háttér ≠ full-bleed szöveg.** Ha egy szekciónak teljes
  szélességű képe vagy színsávja van, a *szöveg* akkor is a tartalmi
  konténert (`layout.contentMax` + gutter) követi. Nagy képernyőn ez a
  leggyakoribb hiba: a háttér kifut, a szöveg a viewport bal széléhez
  tapad, a fejléc viszont a konténerhez igazodik — és a kettő láthatóan
  elcsúszik. **Ellenőrzés 1920px-en:** a hero címsor bal széle ugyanott
  van, mint a fejléc logóé.

---

## 10. Mikrointerakciók — alapértelmezés, nem extra

**Minden projektben, minden dizájnnál.** Nem csak gombra: képre, kártyára,
listaelemre, linkre, űrlapmezőre — mindenre, aminek van értelme.

| Elem | Kötelező visszajelzés |
|---|---|
| Gomb | hover: háttér/árnyék + 1–2px emelés · active: 1px vissza · focus-visible: látható gyűrű |
| Kártya | hover: `translateY(-3px)` + `shadow.sm → shadow.lg` |
| Kép kártyában/galériában | hover: `scale(1.03)` a képen, a konténer `overflow: hidden` — a keret nem mozdul, csak a kép |
| Link | hover: aláhúzás-animáció (`text-underline-offset` vagy növekvő vonal), nem puszta színváltás |
| Nyilas CTA | hover: a nyíl 4px-t csúszik a haladás irányába |
| Űrlapmező | focus: gyűrű + halvány háttérváltás; hiba: szöveg + ikon, nem csak szín |
| Navigációs elem | aktív állapot jelölve, hover aláhúzás/háttér |

**Szabályok:**
- **A hover-görbe lassan fut ki, nem gyorsan indul.** A belépőkre való
  `cubic-bezier(0.2, 0.8, 0.2, 1)` hoveren **rántósnak** hat, mert azonnal
  nagyot ugrik. Hoverre: `cubic-bezier(0.33, 1, 0.68, 1)` (easeOutCubic),
  **240–300ms** — külön `motion.hover` token.
- **Kép-zoom lassabb, mint a többi:** 450–550ms (`motion.zoom`). Egy 200ms-os
  képnagyítás mindig olcsónak hat.
- Szín/határ-váltás gyorsabb (150–180ms), elmozdulás és árnyék lassabb —
  együtt ez adja a „smooth" érzetet.
- **A puszta `opacity: 0.9` nem visszajelzés.** Legyen elmozdulás, árnyék,
  méret vagy szín-váltás.
- `:focus-visible` mindenhol, ahol `:hover` van — billentyűzettel is látszik.
- `prefers-reduced-motion: reduce` esetén a transzformációk elmaradnak, de a
  szín/árnyék-visszajelzés **marad** (a visszajelzés akadálymentességi kérdés,
  nem dísz).
- Egy elemen legfeljebb két tulajdonság animálódjon egyszerre.

---

## 11. Kötelező oldal-elemek

**Back-to-top gomb** — kötelező minden oldalon, ami **kettőnél több
szekcióból** áll (vagy hosszabb 2× viewportnál):
- jobb alsó sarok, `position: fixed`, a `safe-area` figyelembevételével
- **csak görgetés után jelenik meg** (kb. 1,5 viewport), fade + kis elmozdulás
- minimum 44×44px, `aria-label="Vissza az oldal tetejére"`
- `scroll-behavior: smooth`, de `prefers-reduced-motion` esetén azonnali ugrás
- nem takarhat CTA-t vagy fontos tartalmat mobilon
- amikor rejtett, ne legyen fókuszálható (`inert` vagy `visibility: hidden`)

Hosszú oldalnál (5+ szekció) **javasolt**: olvasás-jelző (`scroll-progress`)
és/vagy ragadós szekció-navigáció.

---

## 12. Önellenőrzés — a builder ezt lefuttatja, mielőtt kész

Készíts screenshotot **320, 768, 1440 és 1920px** szélességen (a 375 és 1024
opcionális, de ajánlott), és írd meg a `VIZUALIS-ONELLENORZES.md`-t: minden
pontnál `IGEN`/`NEM` + egy soros indoklás. Ha bármelyik `NEM`, javítsd, és
futtasd újra.

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
13. **Mind a négy méret rendben** (320 / 768 / 1440 / 1920): sehol nincs
    vízszintes scroll, tableten nem zsugorodnak egyformára a 3-as sorok, és
    1920-on nem úszik el a tartalom?
14. **Mikrointerakció mindenen, aminek van értelme** — nem csak gombon:
    kártya emelkedik, kép nagyít a kereten belül, link aláhúzása animált,
    űrlapmezőnek van fókusz-állapota? (§10 táblázata)
15. **Back-to-top gomb** — ha az oldal 2 szekciónál hosszabb, ott van,
    görgetés után jelenik meg, 44px+, `aria-label`-lel? (§11)

---

## 13. Konkrét tiltások — ezeket már megfizettük

Az alábbi tíz hiba mind egy valódi futásból jött, és mind **átment** a
korábbi szabályrendszeren. Ezek nem stílus-kérdések: ha bármelyik előfordul,
a build hibás.

**1. Szöveg képen: egy gradiens NEM elég.**
Az alsó `to top` scrim a szövegblokk *alján* sötét, de az eyebrow/kicker
magasságában már átlátszó — ott a szöveg olvashatatlan lesz egy világos
fotón. Kötelező **kétrétegű scrim**: alsó (`0.85→0` felfelé) **és** oldalsó
(`to right`, a szöveg-hasáb alatt), vagy dedikált scrim a szövegblokk alatt.
Ellenőrzés: a *legfelső* szövegelem alatt is legyen legalább 0.45 alfa.

**2. Átlapolás csak kártyát vagy médiát emelhet — szöveget soha.**
A negatív margót (`space.overlap`) sose a szöveget tartalmazó rácsra tedd,
csak arra az elemre, ami átlapol (pl. az űrlap-kártya). Egy `-5rem` a teljes
rácson a címet a fotó alá húzza, ahol nincs alatta scrim.

**3. Full-bleed elem grid-gyerekként kinyújtást igényel.**
Ha egy sáv/kép `aspect-ratio`-val van méretezve és a szülő `grid`/`flex`,
a böngésző NEM nyújtja ki: az arány fogja megszabni a szélességét (nálunk
1885px helyett 653px lett, és véletlen levágásnak látszott). Full-bleed
elemre mindig: `inline-size: 100%` + `justify-self: stretch`.

**4. Egy szekcióban legfeljebb két tartalmi hasáb (+ egy média).**
És **soha ne szűkíts kétszer**: ha a rács mellé `padding-inline-end`-del is
helyet foglalsz a képnek, a hasábok összeérnek. Vagy a kép valódi
rács-oszlop, vagy absolute + padding — a kettő együtt tilos.

**5. Két display-méretű szövegblokk nem követheti egymást.**
H2 + nagy idézet közvetlenül egymás alatt versenyez és tömör hatást ad.
Az egyik legyen alárendelt (`type.h3` méret, csökkentett kontraszt).

**6. Nyers, levágott képszél tilos.**
Minden képnek legyen kezelése: radius vagy maszk, plusz tint/blend a
háttér felé. Egy fotó, ami csak „odaáll" a szekció szélére, random-nak
látszik — akkor is, ha technikailag ott van a helye.

**7. Hiányzó kliensadat sosem badge a felületen.** (Lásd a builder skillt:
demo-érték az adat-rétegben + `HIANYZO-ADATOK.md`.)

**8. A reveal-animáció nem hagyhat tartósan láthatatlan tartalmat.**
`IntersectionObserver` + `once: true` esetén, ha a hidratálás késik vagy a
JS elhasal, a tartalom `opacity: 0`-n ragad. Kötelező: a kezdőállapot
CSS-ben csak akkor legyen rejtett, ha a JS már fut (`.js-ready` osztály a
`<html>`-en), vagy `@media (prefers-reduced-motion)` és no-JS esetén
`opacity: 1`. **A tartalom láthatósága nem függhet animációtól.**

**9. Full-bleed háttér mellett a szöveg NEM tapadhat a viewport széléhez.**
A háttér fut ki teljes szélességben, a szövegkonténer a `contentMax`-ot
követi. Ha a szekció szövege a fejléc logójánál balrébb kezdődik 1920px-en,
az hiba. (Konkrétan: egy `margin-inline: 0` + `max-width: 55%` felülírta a
konténer-centrálást, és a hero szövege 300px-rel elcsúszott a fejléctől.)

**10. „12/12 IGEN" böngésző nélkül nem írható ki.**
Ha nincs eszköz screenshotra, a self-review nem IGEN, hanem
`NEM ELLENŐRIZVE` — és a builder ezt kimondja a záró összefoglalóban,
hogy a designer tudja: rá van bízva a vizuális átvétel.

## 14. A mérce egy mondatban

> Ha a kész oldal screenshotját fel lehetne tenni egy Webflow-showcase-be
> vagy egy Land-book-listába, és nem lógna ki lefelé — akkor kész.
> Ha „korrekt, de láttam már ezerszer" — akkor nem.
