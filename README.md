# 🚀 SAJU SRL — GUIDE DE MISE EN LIGNE COMPLET

## saju.be · GitHub Pages · Google Workspace · Analytics

-----

## 📦 CONTENU DE CE DOSSIER

|Fichier           |Rôle                                                |
|------------------|----------------------------------------------------|
|`index.html`      |Votre site complet (5 langues, Calendly, formulaire)|
|`sitemap.xml`     |Plan du site pour Google                            |
|`robots.txt`      |Instructions pour les moteurs de recherche          |
|`site.webmanifest`|Icône sur écran d’accueil mobile                    |
|`Logo.png`        |Votre logo                                          |
|`README.md`       |Ce guide                                            |

**À ajouter manuellement :**

- `og-image.jpg` — image 1200×630px pour LinkedIn/WhatsApp (optionnel mais conseillé)
- `favicon.ico`, `favicon-32x32.png`, `apple-touch-icon.png` — icônes navigateur

-----

## ÉTAPE 1 — PRÉPARER LES FICHIERS

### Favicon (icône dans l’onglet du navigateur)

1. Allez sur **https://favicon.io/favicon-generator/**
1. Tapez “S”, choisissez une police, fond bordeaux (#7a1f1a), lettre blanche
1. Téléchargez le pack ZIP et copiez dans ce dossier :
- `favicon.ico`
- `favicon-32x32.png`
- `apple-touch-icon.png`

### Image Open Graph (aperçu sur LinkedIn)

Créez une image 1200×630px avec votre logo + “Saju Srl – Formule de révision des prix”
et nommez-la `og-image.jpg`. Outil gratuit : **https://www.canva.com**

-----

## ÉTAPE 2 — GITHUB (hébergement gratuit)

### Créer le repository

1. Allez sur **https://github.com**
1. Connectez-vous avec votre compte (hanneusefrancois)
1. Allez sur **https://github.com/hanneusefrancois/sajusrl**

### Uploader vos fichiers

1. Cliquez **“Add file”** → **“Upload files”**
1. Glissez ces fichiers :
- `index.html`
- `Logo.png`
- `sitemap.xml`
- `robots.txt`
- `site.webmanifest`
- `favicon.ico` (quand vous l’aurez créé)
1. Cliquez **“Commit changes”**

### Activer GitHub Pages

1. Cliquez **“Settings”** → dans le menu gauche cliquez **“Pages”**
1. Sous **“Source”** → choisissez **“Deploy from a branch”**
1. Sous **“Branch”** → sélectionnez **“main”** et **”/ (root)”**
1. Cliquez **“Save”**
1. Dans **“Custom domain”** → tapez `www.saju.be` → cliquez **“Save”**
1. Cochez **“Enforce HTTPS”** dès que la case devient disponible

-----

## ÉTAPE 3 — BOOKMYNAME (pointer saju.be vers GitHub)

1. Connectez-vous sur **https://www.bookmyname.com**
1. Cliquez sur **saju.be** → **“Gestion DNS”**
1. Configurez exactement ces enregistrements :

```
Type    Nom    Valeur                TTL
────────────────────────────────────────────
A       @      185.199.108.153       28800
A       @      185.199.109.153       28800
A       @      185.199.110.153       28800
A       @      185.199.111.153       28800
AAAA    @      2606:50c0:8000::153   28800
AAAA    @      2606:50c0:8001::153   28800
AAAA    @      2606:50c0:8002::153   28800
AAAA    @      2606:50c0:8003::153   28800
CNAME   www    hanneusefrancois.github.io.  28800
MX      @      aspmx.l.google.com          28800  priorité 1
MX      @      alt1.aspmx.l.google.com     28800  priorité 5
MX      @      alt2.aspmx.l.google.com     28800  priorité 5
MX      @      alt3.aspmx.l.google.com     28800  priorité 10
MX      @      alt4.aspmx.l.google.com     28800  priorité 10
TXT     @      v=spf1 include:_spf.google.com ~all  28800
```

⚠️ **NE TOUCHEZ JAMAIS aux enregistrements MX** — c’est votre email fh@saju.be
⚠️ **NE TOUCHEZ JAMAIS au TXT SPF** — c’est la sécurité de votre email

### Vérification DNS

- Allez sur **https://dnschecker.org** → tapez `saju.be` → type **A**
- Vous devez voir `185.199.108.153` en vert partout
- Propagation : 15 minutes à 2 heures

-----

## ÉTAPE 4 — HTTPS (automatique via GitHub)

GitHub génère le certificat SSL automatiquement une fois le DNS propagé.

1. Allez dans GitHub → Settings → Pages
1. Attendez que le message **“DNS Check in Progress”** disparaisse
1. Vous verrez : **“Your site is published at https://www.saju.be”** ✅
1. Cochez **“Enforce HTTPS”**
1. Testez **https://www.saju.be** — le cadenas 🔒 doit apparaître

-----

## ÉTAPE 5 — ANALYTICS (statistiques visiteurs)

### Option A — Cloudflare Web Analytics (100% gratuit, recommandé)

1. Allez sur **https://dash.cloudflare.com** → créez un compte gratuit
1. Allez dans **“Web Analytics”** → **“Add a site”**
1. Tapez `saju.be`
1. Cloudflare vous donne un code à copier dans votre index.html
1. Dans index.html, remplacez la ligne Plausible par ce code

**Ce que vous verrez :**

- Visiteurs uniques par jour/semaine/mois
- Pays d’origine des visiteurs
- Sources de trafic (LinkedIn, Google, direct…)
- Appareils utilisés (mobile vs desktop)
- Pages les plus visitées
- Aucun cookie — conforme RGPD sans bandeau

### Option B — Plausible (9€/mois, plus complet)

1. Allez sur **https://plausible.io**
1. Créez un compte → tapez `saju.be`
1. Le script est déjà dans votre index.html — rien à modifier

-----

## ÉTAPE 6 — GOOGLE SEARCH CONSOLE (référencement gratuit)

1. Allez sur **https://search.google.com/search-console**
1. Connectez-vous avec fh@saju.be
1. Cliquez **“Ajouter une propriété”** → tapez `https://www.saju.be`
1. Choisissez **“Balise HTML”** comme méthode de vérification
1. Google vous donne un code type `<meta name="google-site-verification" content="XXXXX">`
1. Ajoutez ce code dans votre index.html dans la section `<head>`
1. Redéployez sur GitHub → cliquez **“Vérifier”** dans Google
1. Une fois vérifié → **“Sitemaps”** → entrez :
   
   ```
   https://www.saju.be/sitemap.xml
   ```
   
   → cliquez **“Envoyer”**

Google indexera votre site dans les 24 à 72h.

-----

## ÉTAPE 7 — CALENDLY (déjà configuré)

Le widget Calendly dans votre site est configuré sur :

```
https://calendly.com/fh-saju/30min
```

Si votre URL Calendly est différente, cherchez dans index.html :

```
data-url="https://calendly.com/fh-saju/30min"
```

Et remplacez par votre vraie URL Calendly.

-----

## MISE À JOUR DU SITE

Pour mettre à jour votre site après modification :

1. Claude modifie votre `index.html`
1. Allez sur **https://github.com/hanneusefrancois/sajusrl**
1. Cliquez sur le fichier `index.html`
1. Cliquez l’icône **crayon** ✏️ en haut à droite
1. Ou cliquez **“Add file”** → **“Upload files”** → glissez le nouveau fichier
1. Cliquez **“Commit changes”**
1. Votre site est mis à jour en **30 secondes** ✅

-----

## RÉCAPITULATIF DES COÛTS

|Service                   |Coût                                  |
|--------------------------|--------------------------------------|
|GitHub Pages (hébergement)|**GRATUIT**                           |
|saju.be (domaine)         |Déjà payé via Bookmyname (~15€/an)    |
|Certificat HTTPS          |**GRATUIT** (Let’s Encrypt via GitHub)|
|Cloudflare Analytics      |**GRATUIT**                           |
|Google Search Console     |**GRATUIT**                           |
|Plausible (si choisi)     |9€/mois (optionnel)                   |
|Google Workspace (email)  |Déjà en place                         |
|**TOTAL MENSUEL**         |**0€**                                |

-----

## EN CAS DE PROBLÈME

### Mon site ne s’affiche pas

1. Vérifiez sur **https://dnschecker.org** → `saju.be` → type A → doit afficher `185.199.108.153`
1. Vérifiez dans GitHub → Settings → Pages → votre site doit être “published”
1. Attendez 30 minutes et retestez

### Mon email ne fonctionne plus

Vérifiez sur **https://mxtoolbox.com** → tapez `saju.be` → MX Lookup
Vous devez voir les serveurs Google (aspmx.l.google.com)

### Le cadenas HTTPS ne s’affiche pas

Dans GitHub → Settings → Pages → cochez “Enforce HTTPS”
Si la case est grisée, attendez 30 minutes — GitHub génère le certificat automatiquement

### Mettre à jour le sitemap

Quand vous modifiez votre site, mettez à jour la date dans sitemap.xml :

```xml
<lastmod>2026-03-21</lastmod>
```

-----

## CONTACTS UTILES

|                          |                                           |
|--------------------------|-------------------------------------------|
|Votre email               |fh@saju.be                                 |
|Votre site                |https://www.saju.be                        |
|GitHub                    |https://github.com/hanneusefrancois/sajusrl|
|Bookmyname                |https://www.bookmyname.com                 |
|Google Search Console     |https://search.google.com/search-console   |
|Cloudflare Analytics      |https://dash.cloudflare.com                |
|Documentation GitHub Pages|https://docs.github.com/pages              |