# Landing Design

Run the full UI accelerator flow: from brief + UX output to design tokens,
copy and a working local preview.

## Context
- PROJECT FOLDERS: the convention in .cursor/rules/projekt-context.mdc
  applies — inputs come from knowledge-base/briefs/<projekt-slug>/, and
  every /output/... path below gets a <projekt-slug>/ subfolder.
- Inputs: the project brief AND /output/ux-research/<projekt-slug>/ (run /ux-research
  first if it does not exist yet).
- If /output/tech-stack.md exists (from /build-project), treat it as a
  constraint; otherwise default to Astro + Tailwind, static-first.
- LANGUAGE: write all outputs (copy included!) in the language of the
  brief — Hungarian brief -> Hungarian deliverables, proper accents.
- The team playbooks live in .cursor/skills/ui/ — follow them in order.
- QUALITY FLOOR: docs/vizualis-minoseg.md is binding for creative-director,
  designer and builder. The deliverable is a page a design-literate client
  would pay for — "correct but ordinary" is a failed run.
- IMAGES: every image slot ships with a real file. If the client has no
  photos, use site/public/images/ (see its KEPEK.md) and log the gap — an
  empty grey placeholder box is never acceptable output.
- Every stage writes its artifact to /output/landing-design/ BEFORE the
  next stage starts, so the designer can review at any point.

## Step 0 — INSPIRÁCIÓ-KAPU (mindig ez az első)

Mielőtt BÁRMIT csinálnál, állj meg, és tedd fel EZT az egy kérdést a
designernek, betűjeles menüként. Ne írj addig egyetlen fájlt sem:

```
Szeretnél vizuális inspirációt megadni, mielőtt nekiállok?
Ez a leggyorsabb módja annak, hogy elsőre jó irányba induljunk.

A) Igen, URL(ek) — bemásolom a linkeket
B) Igen, screenshot(ok) — betettem őket a projekt inspiracio/ mappájába
C) Nem — dolgozz a saját kategória-kutatásodból (intelligence)
D) Nem konkrét oldal, de van stílus-irányom — leírom szóban
```

- **A)** Nyisd meg a megadott oldalakat (Firecrawl MCP vagy web-eszköz), és
  nyerd ki belőlük a KONKRÉTUMOKAT: hero-minta, típusskála-arányok, hol van
  a sötét sáv, mennyi a szekció-térköz, milyen a mozgás, mitől hat drágának.
- **B)** Olvasd be a képeket ugyanezekre a szempontokra.
- **C)** Az intelligence a `docs/vizualis-minoseg.md` szerint két poolt kutat
  (in-category + award-szint).
- **D)** A leírást fordítsd le konkrét paraméterekre, és írd be az
  intelligence.md-be, hogy honnan jött.

A választ és a kinyert megfigyeléseket az `intelligence.md` **„Megadott
inspiráció"** szakaszába rögzítsd — a creative-director ebből dolgozik.
A megadott inspiráció **felülírja** a kategória-átlagot: az a mérce, nem a
versenytársak.

FONTOS: ez nem stílusmásolás. A szerkezetet, arányokat és energiát vesszük
át, a tartalmat és a brandet nem.

## Steps (in this order)
1. intelligence — visual competitor & category research → intelligence.md
2. creative-director — section architecture, tone, non-negotiable design
   language → plan.md + consistency.md
3. IN PARALLEL (their outputs are independent):
   - copywriter — conversion copy per section → copy.md
   - brand-analyzer — machine-readable brand summary from any brand
     material in knowledge-base/ → brand.md (skip if no brand material;
     note the gap in plan.md)
4. designer — implementable design tokens from the brand direction
   → design-tokens.json
5. design-guide — a bemutatható, egy oldalas design guide a tokenekből és a
   brand-irányból → design-guide.html, majd **HARD GATE: állj meg és kérj
   jóváhagyást** (A: mehet · B: módosítást kérek · C: mutass másik irányt).
   A builder csak A) után indul. Ha nincs kliens-brandbook, EZ a lépés
   pótolja: itt születik meg a vizuális szerződés, amit a designer lát és
   jóváhagy — nem egy JSON-ban, hanem megnézhető formában.
6. builder — assemble the site using copy.md + design-tokens.json +
   the installed UI library MCPs (shadcn/ui, Magic UI, React Bits).
   At least 4 components come from the MCP catalogs — do NOT rebuild them
   from memory. Closes with the 15-point visual self-review (4 viewport widths).
   → /output/landing-design/site/ with npm run dev working locally.

## Output
/output/landing-design/: intelligence.md, plan.md, consistency.md, copy.md,
brand.md, design-tokens.json, design-guide.html (jóváhagyva), site/ (runnable),
VIZUALIS-ONELLENORZES.md, HIANYZO-ADATOK.md.
Finish with a short summary: what to review first, and any [ASSUMPTION]s.
