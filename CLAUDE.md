# CLAUDE.md — projekt-kontextus (SABLON)

> **CSERÉLD LE** a szögletes zárójeles részeket a saját projektedre, aztán töröld ezt a sort.

## A projekt

[1-2 mondat: mit építünk és miért — pl. „Microsite az ENCO Energy energetikai
tanácsadó cégnek: leadgyűjtés B2B ügyfelektől."]

## A kliens és a célcsoport

- Kliens: [név, iparág, mennyire technikai]
- Célcsoport: [kik használják, mi a fő flow-juk]
- A projekt üzleti célja: [lead / döntés / hatékonyság / bizalom — konkrétan]

## Tech stack és workflow

- Build: Cursor + Claude Code
- Frontend: [pl. Astro + Tailwind]
- Deploy: Cloudflare Pages (main = éles, dev = fejlesztés)
- Adat/email (ha van): Supabase / Resend — kulcsok a .env-ben, SOHA a kódban

## Működési szabályok

1. Kérdezz vissza, mielőtt módosítasz — ne találgass.
2. Kis lépésekben dolgozz: előbb terv, jóváhagyás után kód.
3. Konkrét fájlokra hivatkozz, és ne nyúlj máshoz, csak amit a feladat kér.
4. Best practices, production grade minőség — skálázható és időtálló.
5. Minden működő állapot után commit.
6. A briefek a knowledge-base/briefs/ inboxba érkeznek; minden projekt
   saját mappát kap (knowledge-base/briefs/<projekt-slug>/), az outputok
   pedig /output/<fázis>/<projekt-slug>/ alá. Onnan dolgozz.

## Amit kerülj

- [pl. ne találj ki tartalmat a kliens nevében; ne bővítsd a scope-ot kérés nélkül]
- [brand-szabályok: mit ne használjon — színek, hangnem]
