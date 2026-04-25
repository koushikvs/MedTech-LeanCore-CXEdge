# Lean Core & Edge — Digital Health Transformation Showcase

A static, multi-page showcase built for SAP Sapphire. No build step, no dependencies — just HTML and CSS.

## File structure

```
index.html                    # Main showcase (loads first on the site)
demo-commerce.html            # Solution Demo 01 — Commerce Platform
demo-inventory.html           # Solution Demo 02 — Surgical Inventory Platform
demo-analytics.html           # Solution Demo 03 — Analytics & Decision Support
showcase-styles.css           # Shared stylesheet used by all four pages
lean-core-edge-showcase.html  # Legacy redirect → index.html (safe to delete)
README.md                     # This file
```

The site is fully static: open `index.html` in any browser and it works offline. No server, no build.

## Why the previous Netlify deploy failed

Netlify (and GitHub Pages, S3 static hosting, Vercel) automatically serve a file named `index.html` at the root of your site. Without that filename, you get a "page not found" error because the host doesn't know which page is the homepage. Renaming the main page to `index.html` fixes that.

## Deploy options

### Option 1 — Netlify drag-and-drop (fastest)

1. Open https://app.netlify.com/drop
2. Drag this entire folder onto the drop zone
3. Netlify gives you a live URL within seconds

### Option 2 — GitHub + Netlify continuous deploy

1. Push this folder to a GitHub repo
2. In Netlify: New site → Import from Git → pick the repo
3. **Build command:** leave blank
4. **Publish directory:** leave blank (or `.`)
5. Deploy

Every git push to the main branch will redeploy automatically.

### Option 3 — GitHub Pages

1. Push this folder to a GitHub repo
2. Repo Settings → Pages → Source: `main` branch, folder: `/ (root)`
3. Site goes live at `https://<your-username>.github.io/<repo-name>/`

### Option 4 — Any other static host

Works on Vercel, Cloudflare Pages, AWS S3 + CloudFront, Azure Static Web Apps, or even a plain web server. The site is just static files — no special configuration needed.

## Cross-page navigation

- `index.html` → links out to all three demo pages
- Each demo page → has top-nav links back to `index.html` and across to the other two demos, plus a "Back to main showcase" CTA at the bottom

## Customizing

- **Colors / typography / spacing:** edit `showcase-styles.css` — all design tokens are CSS variables at the top of the file
- **Content (numbers, descriptions, mockups):** edit the relevant HTML file directly
- **Adding more demo pages:** copy any of the existing `demo-*.html` files as a template; they all use the same layout primitives

## Notes

- All client identifiers are anonymized as "Medical Tech Business"
- Mockups are CSS-rendered and use illustrative numbers
- The site is responsive down to mobile widths
