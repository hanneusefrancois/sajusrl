# 🚀 SAJU SRL — GUIDE DE MISE EN LIGNE COMPLET
## saju.be · Netlify · Google Workspace · Plausible Analytics

---

## 📦 CONTENU DE CE DOSSIER

| Fichier | Rôle |
|---------|------|
| `index.html` | Votre site complet (5 langues, Calendly, formulaire) |
| `netlify.toml` | Configuration Netlify (sécurité, cache, redirections) |
| `sitemap.xml` | Plan du site pour Google |
| `robots.txt` | Instructions pour les moteurs de recherche |
| `site.webmanifest` | Icône sur écran d'accueil mobile |
| `README.md` | Ce guide |

**À ajouter manuellement :**
- `logo.jpg` — votre logo (ex : IMG_3329.jpeg renommé)
- `og-image.jpg` — image 1200×630px pour LinkedIn/WhatsApp (optionnel mais conseillé)
- `favicon.ico`, `favicon-32x32.png`, `apple-touch-icon.png` — icônes navigateur

---

## ÉTAPE 1 — PRÉPARER LES FICHIERS

### Favicon (icône dans l'onglet du navigateur)
1. Allez sur **https://favicon.io/favicon-generator/**
2. Tapez "S", choisissez une police, fond bordeaux (#7a1f1a), lettre blanche
3. Téléchargez le pack ZIP et copiez dans ce dossier :
   - `favicon.ico`
   - `favicon-32x32.png`
   - `apple-touch-icon.png`

### Image Open Graph (aperçu sur LinkedIn)
Créez une image 1200×630px avec votre logo + "Saju Srl – Formule de révision des prix"
et nommez-la `og-image.jpg`. Outils gratuits : Canva.com

### Logo
Renommez votre logo `IMG_3329.jpeg` en `logo.jpg` et copiez-le dans ce dossier.

---

## ÉTAPE 2 — CRÉER UN COMPTE NETLIFY

1. Allez sur **https://netlify.com**
2. Cliquez **"Sign up"** → connectez-vous avec votre Google (fh@saju.be)
3. Une fois connecté, vous êtes sur le dashboard

---

## ÉTAPE 3 — DÉPLOYER LE SITE (2 minutes)

1. Sur le dashboard Netlify → cliquez **"Add new site"** → **"Deploy manually"**
2. Glissez-déposez **tout le contenu de ce dossier** (pas le dossier lui-même, son contenu)
3. Netlify génère une URL temporaire type `https://jolly-phoenix-123.netlify.app`
4. Testez votre site sur cette URL — si ça marche, on passe à l'étape suivante

---

## ÉTAPE 4 — CONNECTER saju.be (votre domaine)

### Sur Netlify
1. **Site overview** → **"Domain settings"** → **"Add custom domain"**
2. Tapez : `saju.be` → cliquez **"Add domain"**
3. Tapez aussi : `www.saju.be` → cliquez **"Add domain"**
4. Netlify vous affiche des valeurs DNS. Notez-les.

### Sur Bookmyname (https://www.bookmyname.com)
1. Connectez-vous → **Mes domaines** → cliquez sur `saju.be`
2. Allez dans **Gestion DNS** ou **Zone DNS**
3. Modifiez/ajoutez ces enregistrements :

```
Type    Nom     Valeur                      TTL
────────────────────────────────────────────────
A       @       75.2.60.5                   3600
A       @       99.83.190.102               3600
CNAME   www     jolly-phoenix-123.netlify.app  3600
```

⚠️  NE TOUCHEZ PAS aux enregistrements MX (pour votre email Google Workspace)
⚠️  NE TOUCHEZ PAS au TXT "google-site-verification" (si présent)

4. Sauvegardez — propagation : 15 min à 24h

### Vérification
- https://dnschecker.org → tapez saju.be → vérifiez que le A pointe vers 75.2.60.5
- Une fois propagé, Netlify active le HTTPS automatiquement (certificat gratuit)

---

## ÉTAPE 5 — ACTIVER PLAUSIBLE ANALYTICS (statistiques)

Plausible est déjà intégré dans votre index.html. Il faut maintenant créer le compte :

1. Allez sur **https://plausible.io**
2. Cliquez **"Start free trial"** (30 jours gratuits, puis 9€/mois — ou auto-hébergé gratuit)
   
   **Alternative 100% gratuite** : utilisez **Umami** ou remplacez la ligne Plausible par :
   ```html
   <!-- Cloudflare Web Analytics — GRATUIT, RGPD -->
   <script defer src='https://static.cloudflare.com/beacon.min.js'
     data-cf-beacon='{"token": "VOTRE_TOKEN"}'></script>
   ```
   → Créez un compte gratuit sur **https://dash.cloudflare.com** → Analytics → Web Analytics → Add site

3. Une fois le compte créé, tapez `saju.be` comme domaine
4. Le script est déjà dans votre HTML — rien à modifier

**Ce que vous verrez dans vos stats :**
- Nombre de visiteurs uniques par jour/semaine/mois
- Pages les plus visitées
- Pays d'origine
- Sources de trafic (LinkedIn, Google, direct…)
- Appareils (mobile vs desktop)
- Taux de rebond
- Durée moyenne des visites
- Aucun cookie, conforme RGPD — pas besoin de bandeau cookie

---

## ÉTAPE 6 — GOOGLE SEARCH CONSOLE (référencement gratuit)

1. Allez sur **https://search.google.com/search-console**
2. Connectez-vous avec fh@saju.be
3. Cliquez **"Ajouter une propriété"** → tapez `https://www.saju.be`
4. Choisissez **"Méthode DNS"** → Bookmyname → ajoutez l'enregistrement TXT fourni
5. Cliquez **"Vérifier"**
6. Une fois vérifié → **"Sitemaps"** → entrez : `https://www.saju.be/sitemap.xml` → **"Envoyer"**

Google indexera votre site dans les 24 à 72h.

---

## ÉTAPE 7 — CALENDLY (déjà configuré)

Le widget Calendly dans votre site est configuré sur :
`https://calendly.com/fh-saju/30min`

Si votre URL Calendly est différente, cherchez dans index.html :
```
data-url="https://calendly.com/fh-saju/30min
```
Et remplacez par votre vraie URL Calendly.

---

## RÉCAPITULATIF DES COÛTS

| Service | Coût |
|---------|------|
| Netlify (hébergement) | **GRATUIT** (plan Starter) |
| saju.be (domaine) | Déjà payé via Bookmyname (~15€/an) |
| Certificat HTTPS | **GRATUIT** (Let's Encrypt via Netlify) |
| Cloudflare Analytics | **GRATUIT** |
| Google Search Console | **GRATUIT** |
| Plausible (si choisi) | 9€/mois (optionnel) |
| Google Workspace (email) | Déjà en place |
| **TOTAL MENSUEL** | **0€** (ou 9€ avec Plausible) |

---

## MISE À JOUR DU SITE

Pour mettre à jour votre site après modification :
1. Modifiez `index.html`
2. Allez sur **app.netlify.com** → votre site → **"Deploys"** → **"Drag and drop"**
3. Glissez à nouveau tous les fichiers → en ligne en 30 secondes

---

## SUPPORT

Questions : fh@saju.be
Documentation Netlify : https://docs.netlify.com
Plausible docs : https://plausible.io/docs
Google Search Console : https://support.google.com/webmasters
