# 509 Scoops — Dog Waste Removal, Tri-Cities WA

Static marketing site with Jobber lead capture. No build step, no dependencies —
just HTML, CSS, and a few lines of JS.

Domain: **509scoops.com** — purchased July 2026 via Squarespace Domains (DNS is
managed in the Squarespace Domains dashboard).

Hosted on **GitHub Pages** from this repository's `main` branch — every push to
`main` redeploys the live site automatically (~1 minute). The `CNAME` file
tells Pages the custom domain; don't delete it.

## Pages

Clean URLs via the directory + `index.html` pattern (works out of the box on
GitHub Pages, Netlify, or any static host — no config needed).

| URL | File | Purpose |
|-----|------|---------|
| `/` | `index.html` | Home: hero, how it works, plans overview, commercial, service area |
| `/pricing/` | `pricing/index.html` | Full pricing cards + policies (billing, cancellation, referrals) |
| `/quote/` | `quote/index.html` | Quote/signup request page — **Jobber form embeds here** |
| `/book/` | `book/index.html` | Online booking — Jobber booking form embed (form_id 4968383) |

All asset/CSS/JS references use root-absolute paths (`/css/styles.css`,
`/assets/...`) so pages work identically regardless of folder depth. Keep new
pages consistent with this pattern (a folder + `index.html`, absolute paths)
rather than mixing in bare `.html` files.

## Preview locally

Open `index.html` in a browser, or for a proper local server:

```
python -m http.server 8000
```

then visit http://localhost:8000.

## Pricing (set July 2026 from Tri-Cities market sweep)

Twice-weekly $20 / weekly $25 / bi-weekly $30 / monthly $49 per visit (1 dog,
small per-dog add-on), free initial cleanup with any recurring plan, one-time
cleanups $120/hr. Positioned against: Your Local Scoop ($25/wk, free first
cleanup), Doody Pros ($15/wk but 8-week contract + surcharges), Scoop Hero
("from $19/wk", unpublished). Differentiators to keep loud: no contracts,
transparent pricing, photo + text after every visit.

## Status

- Phone (509) 416-6473 and email 509scoops@gmail.com are live on all pages
- Jobber quote form is embedded and working on `/quote/`
- Jobber online booking is embedded and working on `/book/` (real calendar
  availability, tested end-to-end)
- Logo is the user-provided badge (dog + shovel + smiling poop pile),
  cropped to a transparent circle at `assets/logo-badge-300.png`; source
  files are `assets/logo-badge.png` (full res) and `assets/favicon-32.png` /
  `favicon-64.png`. Theme is a yard palette (green/sky-blue/yellow/brown) —
  no ice-cream references, by design (rejected as too confusing).

## Remaining checklist

1. **Register the business** — LLC filing with WA Secretary of State recommended
   before hiring or taking on liability-heavy work; check "509 Scoops LLC" is
   still available
2. **Liability insurance** — needed before commercial (HOA/apartment) work

## Deploy

Push to `main` — GitHub Pages redeploys automatically. DNS at Squarespace
points the apex at GitHub Pages' A records (185.199.108/109/110/111.153) with
`www` CNAME'd to the github.io address.

## Later (only if needed)

- Move to AWS (S3 + CloudFront, or Amplify) — the site is static, so this is a
  copy-paste migration
- Deeper Jobber integration via their GraphQL API (developer.getjobber.com) —
  requires a small backend; not needed while the embedded form does the job
