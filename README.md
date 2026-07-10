# Designer 2.0 — Starter System

**A saját AI-csapatod alapjai** — a Gerilla Mentor Klub „Designer 2.0: amikor te vagy a stúdió"
képzés kísérő repója. Oktató: Víg Réka · The WOW Studio

Ez a repo egy **működő kiindulórendszer**: parancsok, skillek és sablonok, amikkel briefből
élő, deployolt weboldalig jutsz — AI-csapattal, kódolás nélkül. A kurzus 8 hete alatt
hétről hétre „nyílik ki": mindig azt a részét használd, ahol a képzésben tartasz.

## Indulás 5 percben

1. **Klónozd a repót**, és nyisd meg Cursorban:
   ```
   git clone https://github.com/RekaWeb3Design/designer-20-starter-system.git
   ```
2. **Írd át a kontextusfájlokat a saját projektedre**: `CLAUDE.md` és
   `.cursor/rules/projekt-context.mdc` (mindkettőben jelölve, mit cserélj).
3. **Dobd be a saját briefed** a `knowledge-base/briefs/` mappába — a fájlnév
   mindegy, az első futás projekt-mappába rendezi. (A bent lévő Zöld Sarok
   brief egy dummy, gyakorláshoz.)
4. A Cursor chatben írd be: `/` — és válaszd a parancsot, ahol a kurzusban tartasz.

## Több projekt? Csak dobd be a briefet

A `knowledge-base/briefs/` mappa egy **inbox**: ide dobsz be minden új
briefet, akármilyen fájlnévvel. A következő futás első lépése a
rendszerezés — az AI:

1. létrehoz egy projekt-mappát a kliens nevéből
   (pl. `knowledge-base/briefs/kispista-peksege/`),
2. behúzza a briefet (és a hozzá tartozó anyagokat) ebbe a mappába,
3. az outputokat is projektenként külön mappába írja
   (pl. `output/ux-research/kispista-peksege/`).

Így akárhány kliensed lehet egy rendszerben, semmi nem keveredik: minden
projektnek saját brief-mappája és saját output-mappái vannak. Ha több
projekt van bent és nem egyértelmű, melyikkel dolgozz, a parancs betűjeles
menüben rákérdez. Handovernél a projekt brief-mappáját és output-almappáit
másolod ki — kész.

## Mi van benne — a kurzus hetei szerint

| Hét | Amit használsz | Hol |
|---|---|---|
| 2. | Kontextusfájl-sablonok | `CLAUDE.md` + `.cursor/rules/` |
| 3. | `/ux-research` + a UX-csapat 5 skillje | `.cursor/commands/` + `.cursor/skills/ux/` |
| 4. | `/landing-design`, `/generate-image` + a UI-csapat 6 agentje | `.cursor/skills/ui/` |
| 5. | `/build-project` + a Tech Bridge 5 agentje (qa self-healinggel) | `.cursor/skills/tech-bridge/` |
| 6. | Mentőöv: hibakezelési protokoll + Supabase/Resend bekötés | `docs/` + `prompts/06-*.md` |
| 7. | Handover-checklist + garancia-sablon | `docs/` + `prompts/07-*.md` |
| 1–8. | Az összes heti prompt-minta | `prompts/` |

## A rendszer logikája

```
knowledge-base/briefs/<projekt>/  →  /parancs  →  skillek (szerepek)  →  output/<fázis>/<projekt>/
```

- **A parancs** (`.cursor/commands/*.md`) a belépési pont — elnevezett, újrafuttatható folyamat.
- **A skillek** (`.cursor/skills/**/SKILL.md`) a csapattagok — mindegyiknek egy felelőssége van.
- **Az output** mindig fájl: átnézhető, javítható, és a következő lépés bemenete.

## A kurzus szelleme: a visszatanítás

Ez a rendszer **kezdetben junior**. A te dolgod, hogy seniorrá tanítsd:
ha egy skill rendszeresen ugyanazt rontja el, **írd vissza a tanulságot a SKILL.md-be**
(a kész visszatanító prompt: `prompts/03-ux-gyorsito.md`). Projekt-specifikus tudás
a projekt chatjében marad — globális tanulság a fájlba kerül.

> Minden iteráció, amit globálisan visszaírsz a rendszerbe, egy lépés a senior szint felé.

## Licenc és használat

A repo a képzés résztvevőinek készült, de nyilvános: használd, alakítsd, építs belőle
sajátot. Ha megmutatod, mit építettél vele — jelölj meg, örülök neki. 🙌
