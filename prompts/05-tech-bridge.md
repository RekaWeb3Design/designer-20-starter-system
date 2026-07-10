# 5. hét — Tech Bridge

A fő parancs: `.cursor/commands/build-project.md`, az 5 agent:
`.cursor/skills/tech-bridge/` (a qa SKILL.md tartalmazza a self-healing
protokollt és a max 3 iterációs limitet).
Wrangler-setup: `docs/wrangler-cloudflare.md`.

## Emlékeztető — a lánc

BRIEF + UX-output → tech-architect → UX-csapat → UI-csapat → builder
→ (párhuzamosan) visual-review + responsiveness-checker → qa
→ PASS: deployer → élő URL | FAIL: self-healing loop (max 3 kör)

## A qa-kritériumok testreszabása

Olvasd el a .cursor/skills/tech-bridge/qa/SKILL.md fájlt. A következőt
változtatnám a kapun: [pl. a Lighthouse-küszöb legyen 85, mert...].
Vezesd át best practices szerint, és mutasd meg a diffet.
