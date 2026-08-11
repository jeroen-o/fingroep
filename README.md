# FINgroep.nl — website

Statische website van FINgroep.nl (onafhankelijk financieel advieskantoor, Amersfoort), gebouwd op de principes van FINdossier.nl.

## Publiceren via GitHub Pages
1. Maak een repository (bijv. `fingroep-site`) en upload alle bestanden uit deze map naar de root.
2. Ga naar **Settings → Pages**, kies **Deploy from a branch**, branch `main`, map `/ (root)`.
3. Eigen domein? Laat het bestand `CNAME` staan (fingroep.nl) en zet bij je DNS-provider een CNAME/A-record naar GitHub Pages; anders verwijder je `CNAME`.

## Structuur
- `index.html` — home · `diensten.html` · `werkwijze.html` · `tarieven.html` · `team.html` · `kennis.html` · `contact.html` · `privacy.html`
- `dossier.html` — de FINdossier-tool in FINgroep-uitvoering (draait volledig in de browser)
- `support.js` / `image-slot.js` — runtime; niet verwijderen
- `sitemap.xml`, `robots.txt`, `404.html`, `CNAME`

## SEO & geo
Elke pagina heeft een eigen title, meta description, canonical en Open Graph-tags. De homepage bevat schema.org **FinancialService**-structured data (adres, geo-coördinaten Amersfoort, openingstijden, werkgebied) en alle pagina's dragen geo-tags (NL-UT / Amersfoort).

**Nog doen voor livegang:** AFM-, Kifid- en KvK-nummers invullen (staan als “nr. volgt”), echte tarieven en klantreviews plaatsen, en de geo-coördinaten exact op het pand zetten.
