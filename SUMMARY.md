# Summary

## Part 1: Lead research
- **Qualified leads:** 17 (`leads/leads.json`, sorted by score). Tier A: 6, Tier B: 11, Tier C: 0.
- **Extra leads:** 30 (`leads/extra-leads.md`). Not fully qualified; verify before contacting.
- All 17 leads were also added to the Lead Tracker artifact as l15-l31, status "Demo built".

### Top 10 by score
| # | Business | Niche | Town | Score | Tier | Phone | Demo |
|---|---|---|---|---|---|---|---|
| 1 | Cole's Southern BBQ | Catering | Seneca | 9 | A | 864-710-0284 | `demos/coles-southern-bbq/` |
| 2 | Carolina Catering | Catering | Anderson | 9 | A | 864-617-0806 | `demos/carolina-catering/` |
| 3 | One Shot Exterior Cleaning LLC | Pressure Washing | Easley | 9 | A | 864-293-9426 | `demos/one-shot-exterior/` |
| 4 | All J's Catering | Catering | Seneca | 8 | A | 864-985-8020 | `demos/all-js-catering/` |
| 5 | Noble Electric LLC | Electrical | Seneca | 8 | A | 864-280-7023 | `demos/noble-electric/` |
| 6 | Almaroad Pressure Washing | Pressure Washing | Anderson | 8 | A | 864-883-0126 | `demos/almaroad-pressure-washing/` |
| 7 | Tyndal Tree Service | Tree Service | Anderson | 7 | B | 864-906-5272 | `demos/tyndal-tree-service/` |
| 8 | Manna From Heaven | Catering | Seneca | 7 | B | 864-882-5632 (landline?) | `demos/manna-from-heaven/` |
| 9 | Special Touch Catering by Sardi's | Catering | Clemson | 7 | B | 864-654-7427 (landline?) | `demos/special-touch-catering/` |
| 10 | TrueLine Hauling & Services | Junk Removal | Anderson | 7 | B | 864-318-0231 | `demos/trueline-hauling/` |

## Part 2: Demo sites (17 built)
Each is one self-contained `index.html` with a different look. Each has noindex, the fixed "Demo preview built by David" banner, hero, services, why-us, a missed-call text-back phone mock, clearly labelled "Sample reviews", a quote form (non-functional), a service area and a tap-to-call link with the real number. No real photos.
All 17 use the design skill: 14 got a separate polish pass and 3 (one-shot-exterior, manna-from-heaven, prps-junk-removal) were built with it from the start. The polished sites were checked at 375/768/1280/1600px (no sideways scroll, 44px tap targets). During the polish, unsupported claims such as "free estimates" and invented star ratings were removed.

- `demos/coles-southern-bbq/`
- `demos/carolina-catering/`
- `demos/one-shot-exterior/`
- `demos/all-js-catering/`
- `demos/noble-electric/`
- `demos/almaroad-pressure-washing/`
- `demos/tyndal-tree-service/`
- `demos/manna-from-heaven/`
- `demos/special-touch-catering/`
- `demos/trueline-hauling/`
- `demos/doitall-handyman/`
- `demos/mo-flavorz/`
- `demos/jrs-junk-removal/`
- `demos/prps-junk-removal/`
- `demos/violas-catering/`
- `demos/primor-painting/`
- `demos/jl-stone-painting/`

**Added later (5 more, for pipeline leads l10-l14):** `demos/charles-als-barber/`, `demos/ferkalo-handyman/`, `demos/pressley-auto/`, `demos/one-stop-shop-auto/`, `demos/towne-pendleton/`. That makes 22 demo sites in total.

Root `index.html` is blank except for noindex, and `robots.txt` disallows all crawlers.

## Part 3: Vercel upgrades: done (9/9)
Each live page was fetched read-only and copied into `upgraded/<project>/index.html`. The additions are the demo banner, noindex meta, a text-back section and a "Sample reviews" section, each styled to match the site. The rest of each page is unchanged. **Nothing was deployed or changed on Vercel.** See `upgraded/README.md`.
Projects: mackeys-demo, carolina-lawn-demo, mike-durham-demo, dyars-diner-demo, mac-smiths-demo, bangkok-demo, fastbay-demo, michaels-property-demo, ultimate-hair-demo.

## Live
- **Hosting:** Cloudflare Worker `david-demos`, served from this repo (auto-deploys on push to `main`).
  - New demos: `https://david-demos.dilopez49224.workers.dev/demos/<slug>/`
  - Upgraded sites: `https://david-demos.dilopez49224.workers.dev/upgraded/<project>/`
- **Not published:** `.assetsignore` keeps `leads/` and all `.md` files off the site.
- **Old Vercel links:** all 9 `*.vercel.app` demos forward (307) to their upgraded Cloudflare copies. Keep those Vercel projects as long as the old links are in use.
- **Lead Tracker:** has all 31 leads with live demo links and, for each lead, a tailored text, phone script and email/Facebook message.

## Before contacting anyone
- Check whether Carolina Catering's own website loads; if it doesn't, that's your opener.
- Call or visit landlines (Manna From Heaven, Special Touch, Mike Durham) instead of texting them.
