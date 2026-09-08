# Eventagrate Holding

Website for Eventagrate Holding, live at https://eventagrate.holdings.

Static HTML/CSS with relative asset paths. Entry point: `index.html` at the repository root. No build, dependencies, server code or install step. Assets: `styles.css`, `favicon.svg`, `eventagrate-holding-horizontal.png` (horizontal colour logo).

## People

- **Site content and design:** Ruslan (pushes via a GitHub deploy key with write access).
- **Hosting, DNS, merges:** Miguel.

## Hosting

- **Vercel** project `eventagrate-holdings`, team EventagrateHoldings (Hobby). Git integration on this repo.
  - `main` = production. Any other branch = preview deployment with its own URL.
  - Framework preset "Other", no build step. Files at the repo root are served as-is.
  - Hobby plan caps at 100 deployments/day. Push squashed work, not every edit.
- **Cloudflare** zone `eventagrate.holdings`: CNAME `@` and CNAME `www` → `ae0e7dba293feabd.vercel-dns-017.com`, both **DNS only** (grey cloud). Do not proxy them; Vercel cert issuance and redirects break.
- `www` → apex is a 308 configured in Vercel, not in Cloudflare.
- Mail for `@eventagrate.holdings` is Zoho (MX, SPF, DKIM, DMARC in the same zone). Leave those records alone. The site's contact address is hello@eventagrate.holdings.

## Workflow

1. Work on the `new-site` branch (or any branch), never directly on `main`. Vercel posts a preview URL on the commit.
2. Miguel reviews the preview and merges into `main`.
3. Keep `vercel.json` as is (cleanUrls, trailingSlash:false, security headers).
4. No DNS, domain or Vercel changes beyond `vercel.json`. No secrets, `.env`, or `node_modules`.
5. Keep the repo small; optimise images (WebP/AVIF, max 1600 px).

## Company links

| Company | URL |
|---|---|
| Streamworks | https://streamworks.ae |
| Branch | https://www.branchdev.io |
| Eventagrate Studio | https://www.eventagrate.com |
| Fearless Robots | https://fearlessrobots.com |
| FanHouse | in development, no link yet |

## Brand

Accent red `#FF664A`. No magenta. Fonts and layout as shipped in `styles.css`.
