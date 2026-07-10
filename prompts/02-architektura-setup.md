# 2. hét — Brief, scope, knowledge base

## 1) Architekturális kérdéscsomag — az AI interjúztat végig a 8 tengelyen

Új kliens-projektet indítok. Kérdezz végig az architekturális
kérdéscsomagon, egyesével, ezen a nyolc tengelyen:

1) Projekt és üzleti kontextus   2) Scope és terjedelem
3) Technikai választások         4) Időzítés és átadás
5) Tartalom és adat              6) Brand és vizuális
7) Visszamérés                   8) Külső függőségek

Tengelyenként maximum 2-3 kérdés. Ha egy válaszom homályos vagy
ellentmondásos, kérdezz vissza — ne menj tovább udvariasságból.

A végén készíts összefoglalót: mely tengelyek tiszták, hol vannak
kockázatok, és mit kell a klienssel tisztáznom, MIELŐTT építeni kezdek.

## 2) Brief-generálás — nyers kliens-anyagból strukturált brief

Bemásolom, amit a klienstől kaptam: emailek, meetingjegyzet, átirat,
brand-infó. Az érzékeny adatokat kitakartam.

Készíts belőle strukturált projekt-briefet ezekkel a szekciókkal:

1) A projekt üzleti célja (1-2 mondat)
2) Célcsoport és fő felhasználói flow
3) Elvárt kimenet: oldalak / képernyők / funkciók
4) Ismert korlátok: határidő, budget, technikai adottságok
5) Nyitott kérdések — amit a kliens anyagából NEM lehet tudni

Fontos: ne találj ki semmit. Ha egy információ hiányzik, a nyitott
kérdésekhez kerüljön, ne pótold feltételezéssel.

Kliens-anyag:
[ide jön minden, amid van]

## 3) Scope-rögzítés — MVP + later szétválasztással

A brief alapján készíts scope-dokumentumot két listával:

MVP — ami az induláshoz kell:
csak az, ami nélkül a projekt nem tudja betölteni az üzleti célját.
Minden tételhez írd oda: miért az indulás feltétele.

Later — jó ötlet, de nem most:
minden, ami elhalasztható anélkül, hogy az MVP sérülne.
Minden tételhez írd oda: mi a feltétele annak, hogy később bekerüljön.

Kontextus: solo szállítom, AI-first workflow-val — a scope-nál jelezd
azt is, mely részek sablonozhatók vagy automatizálhatók.

A végén mondd meg: hol látod ebben a projektben a scope creep
legnagyobb kockázatát, és milyen mondattal védeném ki a kliensnél.

## 4) Knowledge base instructions — a projekt-instrukció mezőbe

A briefet és a scope-ot feltöltöttem ebbe a projektbe. Írj
projekt-instrukciót (a project instructions mezőbe), ami tartalmazza:

1) Mi ez a projekt és mi az üzleti célja — a briefből, tömören
2) A te szereped: solo designer-builder partnere vagy a buildben.
   Kérdezz vissza, ha hiányos az input, jelezd a kockázatokat,
   és ne dönts helyettem.
3) Tech stack és workflow: [pl. Cursor + Claude Code, GitHub,
   Cloudflare Pages — írd át a sajátodra]
4) Stílus- és minőségszabályok: [brand, hangnem, mit kerüljön]
5) Amit soha: ne találj ki tartalmat a kliens nevében, és ne
   bővítsd a scope-ot kérés nélkül.

Maximum 300 szó. Instrukció legyen, ne regény — minden mondata
minden jövőbeli beszélgetésre rárakódik.
