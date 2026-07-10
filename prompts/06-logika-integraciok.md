# 6. hét — Mentőöv + integrációk

A hibakezelési protokoll: `docs/mentoov-hibakezeles.md`.

## 1) Biztonságos módosítás — a prevenciós prompt-szerkezet

Olvasd el a [src/lib/auth.ts] fájlt, és foglald össze
1-2 mondatban, mit csinál most.

Kérdezz vissza, MIELŐTT bármit módosítasz — ha valami
nem egyértelmű a kérésemben, ne találgass.

A feladat: [az új funkció leírása — pl. a user kapjon
visszaigazoló emailt beküldés után].

Szabályok:
- Ne nyúlj máshoz, csak amit kifejezetten kérek.
- Kis lépésekben dolgozz: előbb mutasd meg a tervet,
  csak jóváhagyás után írj kódot.
- A végén sorold fel, pontosan mely fájlokat változtattad.

## 2) Űrlap-beküldés mentése Supabase-be

A CLAUDE.md-ben megtalálod a Supabase connection URL-t.
Csináld meg, hogy a kapcsolatfelvételi űrlap beküldései
egy 'submissions' táblába mentődjenek.

Szabályok:
- Az API-kulcsok környezeti változóba kerüljenek (.env),
  SOHA ne a kódba égetve.
- Kapcsold be a Row Level Securityt: beküldeni bárki tud,
  olvasni csak autentikált user.
- A végén adj teszt-instrukciót: hogyan ellenőrzöm a
  Supabase felületén, hogy megjött-e a beküldés.

## 3) Visszaigazoló email Resenddel

A Resend API key a .env-ben van (RESEND_API_KEY).
Minden új űrlap-beküldés után menjen automatikus
visszaigazoló email a beküldőnek.

Szabályok:
- A feladó a hitelesített domainünk legyen.
- Az email-sablon legyen külön fájlban, hogy a szövegét
  én is tudjam szerkeszteni.
- Kezeld az esetet, ha az email-küldés hibázik: a beküldés
  attól még mentődjön el, és logold a hibát.
