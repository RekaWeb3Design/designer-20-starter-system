# Handover-checklist (7. hét)

## A 4 lépés

```
# 1) KÓD A KLIENS REPÓBA — az output/ TARTALMÁT másold (ne magát a mappát):
git init
git remote add origin https://github.com/KLIENS/projekt.git
git add . && git commit -m "Initial handover"
git push -u origin main
git checkout -b dev && git push -u origin dev

# 2) CLOUDFLARE PAGES (a kliens accountján)
# Pages → Create a project → Connect to GitHub → repo kiválasztása
# Build settings: framework auto-detect + build command + output dir → Save and deploy

# 3) ENVIRONMENT VARIABLES (a leggyakoribb hibapont!)
# Settings → Environment variables — kézzel, egyenként:
#   SUPABASE_URL, SUPABASE_ANON_KEY, RESEND_API_KEY, ...
# A .env SOHA nem megy GitHubra.

# 4) DOMAIN + ÁTADÁS
# Pages projekt → Custom domains → kliens-domain (CNAME/A, SSL automatikus, 1-24h propagation)
# Resend domain-verifikáció KÜLÖN rekordok — ne keverd össze!
# Minden hozzáférés a klienshez; jelszóváltás az ő dolguk.
```

## Ellenőrzés a végén

- [ ] `git push origin main` → tényleg frissül az éles oldal?
- [ ] űrlap-beküldés működik élesben? (env-változók tesztje)
- [ ] visszaigazoló email megérkezik?
- [ ] a kliens be tud lépni minden accountjába?

A kliens-README generáló prompt és az 1 oldalas garanciális megállapodás-váz:
`prompts/07-handover.md`
