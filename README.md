# GiftGauge site

Static marketing, guide, privacy, and support pages for the GiftGauge iOS app.
Deployed on Vercel, no build step.

## Pages

| File | Route | Purpose |
|------|-------|---------|
| `index.html` | `/` | Landing page |
| `christmas-gift-tracker.html` | `/christmas-gift-tracker` | Guide hub: how to keep track of Christmas gifts |
| `christmas-gift-budget-spreadsheet.html` | `/christmas-gift-budget-spreadsheet` | Free spreadsheet template with the formulas |
| `how-to-budget-for-christmas-gifts.html` | `/how-to-budget-for-christmas-gifts` | Budgeting method |
| `support.html` | `/support` | Support |
| `privacy.html` | `/privacy` | Privacy Policy |

`vercel.json` enables clean URLs, so routes work without the `.html`.

## Guide pages

The three guide pages exist because GiftGauge has almost no App Store search
demand (checked September 2026: "gift budget" returns a single result at the
lowest popularity tier), while Google demand for the same intent is real.
Autocomplete confirms people search "app to keep track of christmas gifts",
"christmas gift budget spreadsheet template", and "how to budget for christmas
gifts". These pages target that, and each links to the App Store listing.

Conventions to keep if you add more:

- Answer the query in the first hundred words, inside a `.lead` block. Nobody
  scrolls past a long intro to find the answer.
- A download call to action after each substantial answer, not only at the end.
- Give away the useful thing. The spreadsheet page contains a working template,
  not a teaser for one.
- Plain human copy. No em-dashes, no marketing voice, and no claims the app
  cannot back (it has no ratings yet, so never imply otherwise).
- Cross-link the guides to each other.

## App Store badge

`app-store-badge.svg` is Apple's supplied badge artwork, used unaltered at 54px
tall. Apple's marketing guidelines set a 40px web minimum and require clear
space of at least a quarter of the badge height, which `.cta` provides. Do not
restyle it.

## SEO plumbing

`sitemap.xml` and `robots.txt` are maintained by hand. Add new routes to the
sitemap and bump `lastmod`.

Worth doing and not yet done: connect Google Search Console. The queries that
show impressions with zero clicks are the cheapest wins, and the fix is usually
rewriting the page title to match what people actually typed.

## Deploy

Push to `main`; Vercel auto-deploys the connected project.
