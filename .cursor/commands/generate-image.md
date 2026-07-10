# /generate-image

Brand-irány alapján generálj image-promptokat.
Olvasd be előbb a brand.md-t (ha van) a knowledge-base-ből vagy az
/output/landing-design/ mappából.

## Kérdések, amiket felteszel, mielőtt bármit generálsz
- Melyik platformon dolgozunk? (ChatGPT / Higgsfield / Freepik)
- Milyen modell? (vagy ajánlj a felhasználás alapján)
- Mi a felhasználás? (hero / product / lifestyle / makró)
- Milyen aspect ratio? (16:9 / 4:5 / square / portrait)

## Output
- 5 prompt-variáció a brand-iránynak megfelelően,
  angolul, platform-specifikus szintaxissal
- Minden prompthoz 1 soros magyar összefoglaló
- Mentsd a promptokat az assets/prompts/ mappába,
  a felhasználás neve szerint (pl. hero-01.md)

## Szabály
A generált kép fájlneve és a hozzá tartozó prompt mindig együtt legyen
archiválva a projektben — visszakereshetőnek kell lennie, melyik kép
miből készült.
