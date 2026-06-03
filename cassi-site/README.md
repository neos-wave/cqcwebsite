# Cassi — marketing site

The marketing site for **Cassi**, the CQC readiness platform by **Neos Wave**.
Pure static — HTML, one image, an SVG favicon, and Google Fonts from CDN. No build step, no dependencies.

## Files
| File | Purpose |
|---|---|
| `index.html` | Landing page (with the inline readiness taster) |
| `privacy.html` | Privacy policy (Neos Wave Ltd) |
| `taster.html` | Standalone taster — optional, for embedding in email or the deck |
| `neoswave-mark.png` | Neos Wave logo (footer + privacy page) |
| `favicon.svg` | Cassi brand mark |
| `netlify.toml` | Publish config, `/privacy` redirect, security headers |

## Before launch — checklist
1. **Pilot CTAs.** In `index.html`, the "Start your pilot" links are placeholders (`href="#"`). Point them at the app / sign-up URL (the `cqc-demo` site, e.g. an `app.` subdomain).
2. **Contact + parent links.** Replace `hello@neoswave.com`, `privacy@neoswave.com`, and `https://neoswave.com` with the real addresses/domain.
3. **Privacy policy.** Fill the `[bracketed]` items in `privacy.html` (company number, registered address, ICO number, dates) and have it reviewed by a solicitor/DPO before publishing.

## Deploy to Netlify (GitHub)
Create an empty repo `cassi-site` under the `neos-wave` org, then:

```bash
git init
git add .
git commit -m "Cassi marketing site"
git branch -M main
git remote add origin https://github.com/neos-wave/cassi-site.git
git push -u origin main
```

In Netlify → **Add new site → Import from Git** → pick `cassi-site`:
- **Build command:** _(leave blank)_
- **Publish directory:** `.`

Every push to `main` then redeploys automatically.

### Domains
- This site → apex / `www` (or your `cassi.` domain)
- The `cqc-demo` app → `app.` subdomain

---
© 2026 Neos Wave Ltd. All rights reserved. Proprietary — not for redistribution.
