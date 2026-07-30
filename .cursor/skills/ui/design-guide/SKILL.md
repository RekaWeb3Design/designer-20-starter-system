---
name: design-guide
description: Turn the tokens + brand direction into a presentable one-page
  design guide, and STOP for the designer's approval before any site is
  built. Runs after designer, before builder.
---

# Design Guide

Ez a lépés két dolgot csinál, és a második a fontosabb:
1. **előállít egy bemutatható, szépen megtervezett design guide-ot**, és
2. **megáll, és jóváhagyást kér** — a builder addig el sem indul.

**KÖTELEZŐ OLVASMÁNY:** `docs/vizualis-minoseg.md`.

## Miért kell
Ha a kliens nem adott brandbookot (a legtöbb kisebb projektnél nem ad), a
vizuális irány eddig csak a `design-tokens.json`-ban létezett — egy JSON-t
viszont sem a kliensnek nem lehet megmutatni, sem a designer nem lát rajta
azonnal, hogy jó irányba megyünk-e. **Olcsóbb itt megállni, mint egy kész
weboldalt újraépíteni.**

## Process
1. Bemenetek: `design-tokens.json`, `brand.md` (ha van), `consistency.md`,
   `intelligence.md` — benne a **„Megadott inspiráció"** szakasszal.
2. Készítsd el a `design-guide.html`-t: **egyetlen, önmagában megnyíló HTML
   fájl**, külső függőség nélkül (a `/ux-research` `report.html`-je a minta).
   Tartalma:
   - **Irány egy mondatban** + honnan jön (brand-anyag és/vagy inspiráció,
     névvel és URL-lel)
   - **Színpaletta**: minden szín kártyaként, hex-kóddal, szereppel
     (60/30/10 megjelölve), és a kiszámolt kontraszt-arányokkal
   - **Tipográfia**: a valódi betűkkel kirenderelt skála (H1→eyebrow),
     méret-értékekkel, és egy élő mintabekezdés
   - **Térköz és rács**: az alapegység és a szekció-térközök vizuálisan
     ábrázolva, nem csak felsorolva
   - **Formanyelv**: radius-karakter, a két árnyék-szint élő dobozokon
   - **Komponens-előnézetek**: gomb (alap/hover/fókusz), kártya, űrlapmező,
     link — valódi, működő állapotokkal
   - **Mozgás**: időzítések és görbék, egy kattintható példával
   - **Képi irány**: 3-4 kép a projekt `public/images/`-éből, a fotónyelv
     szabályaival
   - **Amit NEM tudunk**: a `brand.md` hézagai (NO GUIDANCE ON…)
3. A guide **maga is felel meg a mércének**: nem lehet egy szedetlen
   felsorolás. Ez az első dolog, amit a kliens lát a munkádból.

## HARD GATE — jóváhagyás
A guide elkészülte után **ÁLLJ MEG. Ne írj egyetlen site-fájlt sem.**
Írd ki az elérési utat, és tedd fel pontosan ezt:

```
Elkészült a design guide: output/landing-design/<projekt>/design-guide.html
Nyisd meg, és mondd meg, mehetünk-e tovább:

A) Rendben, építsd meg az oldalt ezzel
B) Módosítást kérek — leírom, mit
C) Mutass egy másik irányt (más paletta / más tipó / más formanyelv)
```

- **A)** → indul a builder, a jóváhagyott guide a szerződés.
- **B)** → vezesd át a kért módosítást a `design-tokens.json`-ba ÉS a
  guide-ba, majd **kérdezz újra**. Ez a ciklus addig ismétlődik, amíg
  A) nem érkezik. Egy körben mindent javíts, ne szálanként.
- **C)** → készíts egy második irányt ugyanezen a guide-formátumon, és a
  kettőt egymás mellett mutasd meg.

A jóváhagyás tényét (és a kért módosításokat) írd a guide aljára, dátummal —
így később visszakereshető, mihez adott a designer zöld utat.

## Quality bar
- A guide önmagában megnyílik, internet nélkül is (inline CSS, semmi CDN).
- Minden szín mellett ott a hex és a kontraszt-arány.
- A tipó-skálát a VALÓDI betűtípussal rendereld, ne leírd.
- Ha volt megadott inspiráció, a guide első blokkja hivatkozik rá.

## Output
/output/landing-design/<projekt-slug>/design-guide.html
