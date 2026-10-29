# DACUM landing page

Static landing page for the DACUM tools. No build step, no outside libraries or fonts.

```
public/index.html        the page (English / French / Arabic, three colour themes)
public/fonts/            Cairo + Manrope, self-hosted
wrangler.jsonc           tells Cloudflare to publish the public/ folder
```

## Turning a button on

Open `public/index.html`, find `SITE_LINKS` near the bottom, and change one line:

```js
lite: { enabled: true, url: 'https://lite.your-domain.com/' },
```

Commit — Cloudflare redeploys within a minute. While `enabled` is `false` the
button is greyed out and shows "Coming soon" (EN / FR / AR).

## Cloudflare

Workers & Pages → Create → Import a repository → this repo.
Build command: none. Deploy command: `npx wrangler deploy`.
Custom domain: project → Settings → Domains & Routes → Add Domain.
