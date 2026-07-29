# 4. hét — UI-gyorsító

A parancsok a repóban: `.cursor/commands/landing-design.md` és
`generate-image.md`, a 6 agent: `.cursor/skills/ui/`.
MCP-telepítés: `docs/mcp-setup.md`.

## Mielőtt elindítod a /landing-design-t

Két bemenete van, mindkettő kell:

1. **A brief** a projekt-mappájában (`knowledge-base/briefs/<projekt-slug>/`)
2. **A 3. heti UX-output** (`output/ux-research/<projekt-slug>/`) — ha még
   nincs meg, előbb futtasd a `/ux-research`-öt

Amit könnyű elfelejteni: a **`brand-analyzer` kihagyja magát, ha nincs
brand-anyag** a projekt-mappában. Ha a kliensednek van brandbookja, logója
vagy meglévő oldala, tedd be — ha nincs, írj róla egy rövid jegyzetet
(színek, hangvétel, fotó-stílus). Minta:
`knowledge-base/briefs/zold-sarok-kerteszet-brand.md`.

A `builder` a végén `npm install` + `npm run dev`-vel zár — legyen Node
telepítve és szabad port.

## MCP-kereső prompt — új eszközök felfedezéséhez

Keress nekem [Tailwind-kompatibilis, animált hátterekhez való]
UI komponens MCP-t, ami Cursorral működik.

Szempontok:
- Friss információból dolgozz — keress rá, ne a régi tudásodból.
- Írd meg: ingyenes-e, van-e limit, mi a telepítési parancs.
- Hasonlítsd össze a top 2-3 találatot: mikor melyiket érdemes.
- Jelezd, ha valamelyik átfed azzal, amim már van
  (shadcn/ui MCP, Magic UI MCP).

A végén adj egy konkrét ajánlást egy mondatban.

## Kulcsfrázisok, amik javítják az outcome-ot (2. hétről)

Minőségi keret: best practices · production grade quality code ·
scalable and future-proof · high level architecture

Frissesség: up to date data · latest documentation · security concerns ·
search the web for current best practices
