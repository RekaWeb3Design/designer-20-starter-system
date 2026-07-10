# Wrangler + Cloudflare setup (5. hét)

A `deployer` agent előfeltétele.

```
# 1) Wrangler CLI telepítése (globálisan):
npm install -g wrangler

# 2) Bejelentkezés — böngészőt nyit, a Cloudflare-fiókodat kéri:
wrangler login

# 3) Teszt — ha ez lefut, minden rendben:
wrangler whoami

# 4) Kézi deploy (amit a deployer agent is futtat majd):
wrangler pages deploy ./dist --project-name sajat-projekt-neve
```

Tipp: ha elakadsz, másold a hibaüzenetet az AI-nak — a Wrangler-hibák 90%-a
login vagy projektnév-elgépelés.

**FONTOS:** a `wrangler pages deploy` a MUNKAKÖNYVTÁRBAN keresi a `functions/`
mappát — ha Pages Functions-t is használsz, a projekt gyökeréből futtasd.
