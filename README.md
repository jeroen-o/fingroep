# FINdossier.nl

**Actuele toolversie: 1.2.0 — augustus 2026** (zie versiegeschiedenis in de tool, tabblad Handleiding)

FINdossier is je persoonlijke financiële dossier dat je één keer opbouwt en daarna jaarlijks bijwerkt — zelf, of samen met je adviseur. Zo weet jij altijd hoe je ervoor staat, en weten je nabestaanden waar alles te vinden is als jou iets overkomt.

De tool is één standalone HTML-bestand: geen server, geen database, geen build-step, geen externe libraries. Alle gegevens blijven in de browser van de gebruiker; opslaan gebeurt via (optioneel AES-256-versleutelde) export naar een lokaal bestand.

## Inhoud van deze repository

| Bestand | Doel |
|---|---|
| `index.html` | Homepage / landingspagina met uitleg voor consument en adviseur, FAQ en de SEO/GEO structured data (WebApplication + FAQPage) |
| `tool.html` | De volledige FINdossier-tool (8 tabbladen incl. ingebouwde handleiding) |
| `handleiding.html` | Losse, printbare handleiding |
| `robots.txt` / `sitemap.xml` | SEO |
| `CNAME` | Custom domain voor GitHub Pages (findossier.nl) |
| `.nojekyll` | Schakelt Jekyll-verwerking uit op GitHub Pages |

## Live zetten via GitHub Pages

1. Maak een nieuwe (private of publieke) repository en push deze bestanden naar de `main`-branch.
2. Ga naar **Settings → Pages**, kies **Deploy from a branch**, branch `main`, map `/ (root)`.
3. Wacht tot de site live staat op `https://<gebruikersnaam>.github.io/<repo>/`.
4. **Custom domain**: bij je DNS-provider voor `findossier.nl`:
   - `A`-records naar GitHub Pages: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME`-record voor `www` naar `<gebruikersnaam>.github.io`
5. Vul in **Settings → Pages** het custom domain `findossier.nl` in en zet **Enforce HTTPS** aan (nodig voor de versleutelde export: Web Crypto vereist https).

## SEO en GEO (AI-vindbaarheid)

- `index.html` bevat meta description, Open Graph-tags, canonical en JSON-LD structured data: `WebApplication` (gratis, FinanceApplication, nl) en `FAQPage` met de belangrijkste vragen. Zoekmachines kunnen de FAQ als rich result tonen; AI-zoekmachines (GEO) halen de beschrijving en FAQ-antwoorden hieruit.
- De FAQ staat óók als leesbare content in de tool (tabblad Handleiding) en in `handleiding.html` — zichtbare content weegt voor AI-engines zwaarder dan alleen structured data.
- Na livegang: dien `https://findossier.nl/sitemap.xml` in via Google Search Console en Bing Webmaster Tools.

## Onderhoud (jaarlijks, na Prinsjesdag/jaarwisseling)

1. **AOW-tabel** — in `index.html`, functie `aowInfo()`: voeg de nieuw vastgestelde AOW-leeftijd toe zodra het kabinet het volgende jaar vaststelt (elk najaar, 5 jaar vooruit). Laatst verwerkte vaststelling: AOW-jaar 2031 (67 jaar en 3 maanden).
2. Controleer de teksten van de handleiding en disclaimers op actualiteit.
3. De tool zelf bevat bewust géén belastingtarieven of vrijstellingsbedragen — daar is dus geen jaarlijks parameteronderhoud voor nodig.

## Compliance-positionering

FINdossier is een registratie- en overzichtstool: geen financieel/fiscaal/juridisch advies, geen productaanbevelingen, geen belastingberekening, geen erfrechtelijke duiding. Projecties en scenario's (tabblad Kompas) zijn indicatieve rekenuitkomsten op basis van eigen aannames van de gebruiker, voorzien van disclaimers. **Laat vóór livegang het Kompas-tabblad en het adviseursrapport toetsen door compliance/juridisch** — zie ook de sectie "Wat FINdossier níet doet" in de handleiding.

## Privacy (AVG)

Er worden geen persoonsgegevens verwerkt door de site: geen server-side opslag, geen accounts, geen cookies, geen analytics (tenzij zelf toegevoegd — voeg dan een privacyverklaring en cookiebanner toe). Gegevens bestaan uitsluitend in de browser van de gebruiker en in diens eigen exportbestanden.
