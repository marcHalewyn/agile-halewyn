# Agile Halewyn — Portfolio Website

Persoonlijke portfoliosite gebouwd met [Astro](https://astro.build/), gehost op [Netlify](https://www.netlify.com/).

## Lokaal draaien

```bash
npm install
npm run dev        # Start dev server op localhost:4321
npm run build      # Bouw statische site naar /dist
npm run preview    # Preview de gebouwde site
```

## Deployen naar Netlify

### Optie A: Via GitHub (aanbevolen)

1. Push dit project naar een GitHub-repository
2. Ga naar [app.netlify.com](https://app.netlify.com/) en maak een gratis account aan
3. Klik op "Add new site" → "Import an existing project" → kies je GitHub-repo
4. Netlify detecteert automatisch de `netlify.toml` — klik op "Deploy"
5. Je site staat live op een `*.netlify.app`-URL

### Optie B: Handmatig deployen (drag & drop)

1. Run `npm run build`
2. Ga naar [app.netlify.com](https://app.netlify.com/)
3. Sleep de `/dist`-map naar het upload-vlak
4. Je site staat direct live

### Eigen domein koppelen (agilehalewyn.com)

1. In Netlify: ga naar "Domain management" → "Add custom domain"
2. Voer `agilehalewyn.com` in
3. Pas bij Bluehost (of je domeinregistrar) de DNS-instellingen aan:
   - Verwijder bestaande A-records
   - Voeg een CNAME-record toe: `www` → `je-site-naam.netlify.app`
   - Of stel Netlify DNS in (zij geven je de nameservers)
4. Netlify regelt automatisch een SSL-certificaat (HTTPS)

## Structuur

```
src/
  layouts/Base.astro    — Globale layout (head, fonts, CSS reset)
  pages/index.astro     — Alle content en styling
public/
  favicon.svg           — Favicon
netlify.toml            — Netlify build configuratie
```

## Content aanpassen

Alle tekst staat in `src/pages/index.astro`. Open het bestand, zoek de tekst die je wilt
wijzigen, pas het aan, en push naar GitHub (Netlify herdeployt automatisch).

## Toekomstige uitbreidingen

- CV als PDF-download toevoegen (plaats in `/public/cv.pdf`)
- Blog-sectie (met Astro Content Collections)
- Tweetaligheid (NL/EN) via Astro i18n
