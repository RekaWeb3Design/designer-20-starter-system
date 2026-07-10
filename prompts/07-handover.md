# 7. hét — Production és handover

A teljes flow: `docs/handover-checklist.md`.

## 1) Kliens-README generálás — a belső doksidból

Készíts kliensbarát README.md-t ehhez a projekthez, a meglévő
belső dokumentációm alapján — de annál sokkal rövidebben.

Tartalma pontosan ez legyen, ebben a sorrendben:
1) Mi ez a projekt — 1 bekezdés, nem-technikai nyelven
2) Futtatás helyi gépen — npm install, npm run dev, röviden
3) Deploy — hogyan működik az automata Cloudflare-deploy
   (push a main branchre → 1-2 perc múlva élesben)
4) Kapcsolat — [a neved és elérhetőséged]

Szabályok:
- NE kerüljön bele: belső promptok, agent-rendszer, scratch-
  jegyzetek, ügyfélkommunikáció, API-kulcsok.
- A hangnem: segítőkész, de tömör. A kliens nem fejlesztő.
- Maximum 1 oldal.

## 2) Garanciális megállapodás — 1 oldalas váz

ÁTADÁSI ÉS GARANCIÁLIS FELTÉTELEK — [projekt neve]
Átadás dátuma: [dátum] · Szállító: [neved] · Megrendelő: [kliens]

A HANDOVER-CSOMAG TARTALMA
1. Bugfix-garancia az átadástól számított 2 hétig:
   a leszállított funkcionalitásból eredő hibák javítása
   díjmentesen, bejelentéstől számított [3] munkanapon belül.
2. Egy átadási hívás (30 perc): a rendszer kezelésének
   bemutatása, kérdések megválaszolása.
3. Dokumentáció: README + setup-leírás a repositoryban.
4. Hozzáférés-átadás: minden fiók a Megrendelő tulajdonában;
   a jelszavak megváltoztatása az átadás után a Megrendelő
   feladata és felelőssége.

A GARANCIA NEM TERJED KI
- új funkciók fejlesztésére (külön megállapodás vagy óradíj),
- az átadás utáni design-módosításokra,
- harmadik fél szolgáltatásainak hibáira (pl. Stripe, Cal.com,
  tárhely- vagy domain-szolgáltató),
- a Megrendelő beavatkozása által okozott hibákra.

A GARANCIA UTÁNI IDŐSZAK
További támogatás, fejlesztés: [óradíj / támogatási csomag]
alapján, előzetes egyeztetéssel.

Kelt: __________  Szállító: __________  Megrendelő: __________
