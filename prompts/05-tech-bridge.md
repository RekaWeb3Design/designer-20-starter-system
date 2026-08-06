# 5. hét — Tech Bridge

A fő parancs: `.cursor/commands/build-project.md`, az 5 agent:
`.cursor/skills/tech-bridge/` (a qa SKILL.md tartalmazza a self-healing
protokollt és a max 3 iterációs limitet).
Wrangler-setup: `docs/wrangler-cloudflare.md`.

## Emlékeztető — a lánc

BRIEF + UX-output → tech-architect → UX-csapat → UI-csapat → builder
→ (párhuzamosan) visual-review + responsiveness-checker → qa
→ PASS: deployer → élő URL | FAIL: self-healing loop (max 3 kör)

## 0. Repo frissítése (git pull)

Ha a repót a pre-training óta klónoztad, elég egy frissítés — terminálban
`git pull`, vagy Cursorban: Source Control panel → ⋯ → Pull. Prompttal:

Frissítsd a helyi kurzus-repómat GitHubról. Futtasd le a git pull-t,
és magyarázd el, mi történik. Ha hibába ütközünk (pl. lokális
módosítások vagy konfliktus), oldd meg úgy, hogy a saját
változtatásaim — például a qa SKILL.md módosításaim — megmaradjanak.

## 1. Wrangler + Cloudflare beüzemelése

Kézzel: `docs/wrangler-cloudflare.md`. Prompttal:

Segíts beüzemelni a Cloudflare-deployt ezen a gépen. Lépésről lépésre:
1) ellenőrizd a Node.js/npm meglétét, 2) telepítsd a Wrangler CLI-t
globálisan, 3) futtasd a wrangler login-t — mondd el, mit kell tennem
a böngészőben, 4) ellenőrizd a wrangler whoami paranccsal. Ha hibát
kapunk, itt a hibaüzenet: [ide másold] — diagnosztizáld, és javítsuk.

## 2. Futtatás a saját anyagodon

A brief + kliens-inputok a `knowledge-base/briefs/` inboxban (a
rendezést a rendszer elvégzi), aztán: `/build-project`

Számíts rá: az elején a UX-csapat megállhat célcsoport-kérdéssel —
válaszolj a betűjeles menüből. Kész UX-outputtal a futás ~30–40 perc,
üres projekten hosszabb.

## 3. Ha megáll a futás — hibakeresés

A /build-project futásom megállt. Az utolsó kimenet / hibaüzenet:
[ide másold]. Diagnosztizáld: 1) melyik fázisban álltunk meg
(tech-architect / UX / UI / builder / validáció / qa / deploy),
2) mi a hiba valószínű oka, 3) mi a legkisebb lépés, amivel onnan
folytatni tudjuk? Ne indítsd újra az egész láncot, ha nem szükséges.

## 4. A qa-kritériumok testreszabása (a hét lényege)

Olvasd el a .cursor/skills/tech-bridge/qa/SKILL.md fájlt. A következőt
változtatnám a kapun: [pl. a Lighthouse-küszöb legyen 85, mert...].
Vezesd át best practices szerint, és mutasd meg a diffet.

## 5. Iteráció kliens-visszajelzés alapján

A kliens az élő preview-ra ezt a visszajelzést adta: [ide másold].
Vezesd át a módosításokat, majd futtasd újra a Tech Bridge
ellenőrzéseit: visual-review, responsiveness-checker, qa. Csak qa PASS
után deployolj a meglévő Cloudflare-projektbe (ugyanarra az URL-re),
és foglald össze egy sorban, mi változott.
