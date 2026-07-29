# Knowledge base

Ide kerül minden, amiből az AI-csapat dolgozik:

- `briefs/` — a briefek **inboxa**. Ide dobd be az anyagot lazán, akármilyen
  fájlnévvel; a futás első lépése berendezi egy `<projekt-slug>/` mappába, és
  onnantól abból dolgozik. (Most egy dummy gyakorló-projekt van itt — cseréld
  a sajátodra!)
- `briefs/<projekt-slug>/` — egy projekt minden anyaga egy helyen:
  - a brief (a kliens megkeresése, ajánlatkérés)
  - **brand-anyag** — brandbook, logó, arculati kivonat, vagy akár csak egy
    jegyzet a meglévő oldalról. Ez a `brand-analyzer` bemenete a 4. héten:
    ha nincs brand-anyag, az az agent kihagyja magát.
  - kliens-levelezés kivonata (érzékeny adatok KITAKARVA)
  - `transcript-*.md` — interjú/meeting-átiratok, ha vannak

Szabály: **ami itt van, azt az AI ténynek tekinti.** Ezért ide csak átnézett,
csiszolt anyag kerüljön — a nyers AI-generálta vázlat előbb menjen review-ra.
