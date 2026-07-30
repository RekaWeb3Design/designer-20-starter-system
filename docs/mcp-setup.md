# UI library MCP-k telepítése (4. hét)

A kurzus-minimum két INGYENES MCP — ennyi kell a `/landing-design`-hoz.

> **A repo már tartalmaz egy kész `.cursor/mcp.json`-t** (shadcn + Magic UI +
> React Bits). Ha `git pull` után újraindítod a Cursort, elvileg nincs is
> teendőd — **Cursor Settings → MCP**, és mindháromnál zöld pötty. Az alábbi
> lépések akkor kellenek, ha saját projektben állítod be a nulláról.

## 1) shadcn/ui MCP — a projekt mappájában:

```
npx shadcn@latest mcp init
```

Válaszd a Cursort; a `.cursor/mcp.json` létrejön.
**Teszt** a Cursor chatben: `show me available components in the shadcn registry`

## 2) Magic UI MCP — add hozzá a `.cursor/mcp.json`-hoz:

```json
{
  "mcpServers": {
    "magicui": {
      "command": "npx",
      "args": ["-y", "@magicuidesign/mcp@latest"]
    }
  }
}
```

**Teszt:** `list magicui components`

A kész `.cursor/mcp.json` így néz ki a kurzus-minimummal — ha akarod, az
`init` kihagyásával **ezt is bemásolhatod kézzel**, ugyanaz az eredmény:

```json
{
  "mcpServers": {
    "shadcn": {
      "command": "npx",
      "args": ["shadcn@latest", "mcp"]
    },
    "magicui": {
      "command": "npx",
      "args": ["-y", "@magicuidesign/mcp@latest"]
    }
  }
}
```

## Ha az `npx shadcn@latest mcp init` hibával áll le

Az `init` két dolgot csinál: **(1)** beírja a szervert a `.cursor/mcp.json`-ba,
**(2)** telepíti a shadcn csomagot dev-dependencyként. A (2) **nem kötelező** —
az MCP `npx`-szel indul, futáskor húzza le magát.

Tehát ha `npm error code ERESOLVE`-ot (vagy bármilyen install-hibát) látsz:
**nézd meg, létrejött-e a `.cursor/mcp.json`.** Ha igen és benne van a shadcn
szerver, kész vagy — lépj tovább, az install-hibát hagyd figyelmen kívül.

Miért fordul elő: az `npm install` felmászik a mappafán az első `package.json`-ig.
Ha a projekted egy olyan mappa alatt van, ahol feljebb létezik egy régi
`package.json` (pl. a home mappádban), az npm ANNAK a projektnek a
dependency-fáját próbálja megoldani — és annak a konfliktusaira hasal el.
Ilyenkor a kézi mcp.json a legrövidebb út.

## Firecrawl MCP — a valódi web

Ez nem UI-library, mégis ez hozza a legnagyobb különbséget: ezzel tudja az AI
**megnyitni a megadott inspirációs oldalt** és kiolvasni a szerkezetét, és
ezzel kutat friss adatból az `intelligence` agent — a betanított emlékezete
helyett.

```json
"firecrawl": {
  "command": "npx",
  "args": ["-y", "firecrawl-mcp"],
  "env": { "FIRECRAWL_API_KEY": "fc-IDE_A_SAJAT_KULCSOD" }
}
```

Kulcs: **firecrawl.dev** — van ingyenes szint. Nélküle a `/landing-design`
inspiráció-kapuja csak a szóban megadott irányt tudja feldolgozni.

## AI-vezérelt telepítés — ha nem akarsz configot szerkeszteni

Másold be ezt Cursorba, és végigvezet:

```
Segíts bekötni a UI-gyorsítóhoz szükséges MCP szervereket ebben a
projektben, és vezess végig lépésről lépésre.

Amire szükségem van: shadcn/ui, Magic UI, React Bits és Firecrawl.

Így haladj:
1. Nézd meg, létezik-e már .cursor/mcp.json, és mi van benne. Mondd meg,
   melyik hiányzik — ne írd felül, amit már beállítottam.
2. Írd bele a hiányzókat egyesével, és minden lépés után mondd meg, mit
   csináltál, és nekem mit kell tennem (pl. Cursor újraindítás).
3. A Firecrawlhoz API-kulcs kell: mondd el, hol szerzem be, és hova írjam —
   a kulcsot NE te találd ki.
4. A végén adj ellenőrző listát: melyik szervert milyen teszt-paranccsal
   nézzem meg.
5. Ha valami hibára fut, előbb magyarázd el, MI az oka, és csak utána
   javasolj megoldást.

Egyszerre egy lépést csinálj, és várd meg a visszajelzésemet.
```

## Opcionális

- React Bits (animált komponensek): `npx reactbits-dev-mcp-server`
- Fizetős réteg: 21st.dev Magic (~5–20 USD/hó), Aceternity Pro, shadcn-studio Pro

Telepítés után: **Cursor Settings → MCP** — zöld pötty = él a kapcsolat.

Friss MCP-k felfedezéséhez: agentskills.io · mcpservers.org — a kereső-prompt:
`prompts/04-ui-gyorsito.md`
