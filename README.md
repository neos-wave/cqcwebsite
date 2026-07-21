# Cassi — marketing site

The marketing site for **Cassi**, the CQC co-pilot for multi-site care groups, by **Neos Wave**.
Pure static — HTML, one logo image, an SVG favicon, an OG share image, and Google Fonts from CDN.
No build step, no dependencies.

## Files
| File | Purpose |
|---|---|
| `index.html` | Landing page (with the inline readiness taster + animated group-intelligence chat) |
| `privacy.html` | Privacy policy (Neos Wave Ltd) |
| `taster.html` | Standalone taster — optional, for embedding in email or the deck |
| `neoswave-mark.png` | Neos Wave logo (footer + privacy page) |
| `favicon.svg` | Cassi brand mark |
| `og-image.png` | 1200×630 social-share image (Open Graph / Twitter) |
| `robots.txt` / `sitemap.xml` | SEO |
| `netlify.toml` | Publish config, `/privacy` + `/taster` redirects, security headers, asset caching |

## The three products this site fronts
- **cqcwebsite** → this marketing site (`cassi-site`).
- **cqc-demo** → the single-home co-pilot app (PIN gate + Anthropic chat). Destined for an `app.` subdomain.
- **cqcreporting** → the Group Intelligence reporting layer (Brackenford demo estate). Keep on a separate demo URL.

## Before launch — checklist
1. **Wire the CTAs to real URLs.** At the bottom of `index.html` there's a `CTA CONFIG` block:
   - `DEMO_URL` — the single-home app (`cqc-demo`), e.g. `https://app.neoswave.works`. Powers "Start a pilot".
   - `BOOK_URL` — your scheduler (e.g. Calendly). Powers every "Book a walkthrough".
   - Until these are set, both CTAs open a **pre-filled email** to `hello@neoswave.works` — so nothing is a dead link.
   - In `taster.html`, set `FULL_REVIEW_URL` to the same live app URL.
2. **Contact + domain.** The site now uses **`neoswave.works`** throughout (matching the live domain).
   Confirm `hello@neoswave.works` and `privacy@neoswave.works` are monitored inboxes.
3. **Privacy policy.** Fill the `[bracketed]` items in `privacy.html` (company number, registered address,
   ICO number, dates) and have it reviewed by a solicitor/DPO before publishing.
4. **OG/canonical URLs.** Meta tags assume `https://cassi.neoswave.works/`. Update if the final domain differs.

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
- The `cqcreporting` demo → a separate, gated URL (not apex, not `app.`)

---
© 2026 Neos Wave Ltd. All rights reserved. Proprietary — not for redistribution.
