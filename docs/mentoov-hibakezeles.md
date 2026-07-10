# Mentőöv — hibakezelési protokoll (6. hét)

## A három pillér

- **Prevenció (default):** commit minden működő funkció után · kis lépésekben kérj ·
  kérd, hogy kérdezzen vissza · konkrét fájlokra hivatkozz
- **Reagálás (backup):** az error információ, nem ítélet — olvasd el, másold be
  TELJESEN az AI-nak, előbb értelmezést kérj, csak utána javítást
- **Mindset:** a javítás drágább, mint az újraindulás · az AI beragadhat rossz
  mentális modellbe — új chat segít · néha a kérdés rossz, nem a válasz

## A 3-iterációs szabály

**Ha 3 promptra sem javul — NE menj negyedikre. Lépj vissza.**

## Git-mentőöv

```
git status                          # mely fájlok változtak?
git diff                            # pontosan mi változott?
git checkout .                      # MINDEN nem commitolt változás eldobása
git checkout HEAD~1 -- file.ts      # egy fájl visszaállítása az előző commitból
git stash                           # félretesz (nem töröl) — később visszahozható
```

Vagy bízd az AI-ra: „Nézd meg a git statust és a diffet. Foglald össze, mit
változtattunk az utolsó commit óta. Utána lépj vissza Gittel a legutolsó működő
állapotra — de előtte mondd el, pontosan mi fog elveszni, és várd meg a jóváhagyásomat."

## Mikor nyiss új chatet

- Ha az AI 5+ iteráción át körözik és nem érti
- Ha a kontextusban több a kuszaság, mint a tisztaság

A `.cursor/rules` és a `CLAUDE.md` az új chatbe is betöltődik — a szabályok
maradnak, a zaj tűnik el.
