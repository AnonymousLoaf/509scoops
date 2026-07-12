# 509 Scoops — Dog Waste Removal, Tri-Cities WA

Static marketing site with Jobber lead capture. No build step, no dependencies —
just HTML, CSS, and a few lines of JS.

Domain: **509scoops.com** — purchased July 2026 via Squarespace Domains (DNS is
managed in the Squarespace Domains dashboard).

Hosted on **GitHub Pages** from this repository's `main` branch — every push to
`main` redeploys the live site automatically (~1 minute). The `CNAME` file
tells Pages the custom domain; don't delete it.

## Pages

| File | Purpose |
|------|---------|
| `index.html` | Home: hero, how it works, plans overview, commercial, service area |
| `pricing.html` | Full pricing cards + policies (billing, cancellation, referrals) |
| `quote.html` | Quote/signup request page — **Jobber form embeds here** |
| `book.html` | Currently a "coming soon" page for online booking; Jobber booking form embed (form_id 4968383) is saved commented-out in the file, ready to restore |

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
- Jobber quote form is embedded and working on `quote.html`
- Online booking (`book.html`) is a placeholder until the Jobber booking form
  (services, availability, questions) is fully configured and tested

## Remaining checklist

1. **Register the business** — LLC filing with WA Secretary of State recommended
   before hiring or taking on liability-heavy work; check "509 Scoops LLC" is
   still available
2. **Liability insurance** — needed before commercial (HOA/apartment) work
3. **Logo/colors** — all colors are CSS variables at the top of
   `css/styles.css`; swap them once you have a logo
4. **Restore online booking** — once Jobber's booking form is confirmed
   working end-to-end (real availability, not a free-text date field), swap
   the embed back into `book.html`

## Deploy

Push to `main` — GitHub Pages redeploys automatically. DNS at Squarespace
points the apex at GitHub Pages' A records (185.199.108/109/110/111.153) with
`www` CNAME'd to the github.io address.

## Later (only if needed)

- Move to AWS (S3 + CloudFront, or Amplify) — the site is static, so this is a
  copy-paste migration
- Deeper Jobber integration via their GraphQL API (developer.getjobber.com) —
  requires a small backend; not needed while the embedded form does the job
