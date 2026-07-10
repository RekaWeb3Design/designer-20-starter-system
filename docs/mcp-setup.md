# UI library MCP-k telepítése (4. hét)

A kurzus-minimum két INGYENES MCP — ennyi kell a `/landing-design`-hoz.

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

## Opcionális

- React Bits (animált komponensek): `npx reactbits-dev-mcp-server`
- Fizetős réteg: 21st.dev Magic (~5–20 USD/hó), Aceternity Pro, shadcn-studio Pro

Telepítés után: **Cursor Settings → MCP** — zöld pötty = él a kapcsolat.

Friss MCP-k felfedezéséhez: agentskills.io · mcpservers.org — a kereső-prompt:
`prompts/04-ui-gyorsito.md`
