# client-demos: rules for building demo sites

Free one-page demo sites for local businesses near Clemson, SC. Outreach is signed "David".
Every `.md` file and `leads/` stay off the live site via `.assetsignore`.

## Scope
- Work only in this repo. Never use, copy or resemble PC Atlas styles, components or branding (no dark navy, no cyan glow, no Space Grotesk/Inter/JetBrains Mono).

## Every demo needs
- `<meta name="robots" content="noindex, nofollow">` and a fixed banner reading "Demo preview built by David — not the official site."
- Sections: hero, services, why-us, a "Never miss a call — we text you back in seconds" phone/SMS mock, "Sample reviews" (clearly placeholder), a quote form, the service area, and a tap-to-call link with the real phone number.
- One self-contained `demos/<slug>/index.html`, mobile-first, with no real photos of the business.
- Use only facts from the lead record. Never invent ratings, owners, years, hours, prices, menu items, "free estimates" or licenses.

## Theme from the real business first
- If the business has real photos (Google, Facebook, storefront, trucks, uniforms), a menu, a logo or a current website, take the palette and mood from those: their actual colors, signage style and vibe. The demo should feel like an upgraded version of *them*.
- Only when there's nothing to go on, choose a direction from the niche and the business's personality.
- Every site must still look distinct from the other demos (different fonts, palette and layout).

## When David sends screenshots of a lead (Facebook, Google, menus, trucks)
- Pull out every useful fact: correct phone (screenshots beat our research, so fix it everywhere: tracker, `leads/leads.json`, the demo's tel: links and the text-back mock), email, real business name, hours, address, services and events, tagline, follower and review counts, and whether their website works.
- A dead or broken website is a pitch angle: put it in the text, phone script and email.
- Related businesses that appear in their posts (sister restaurants, partners) are separate leads. Note them in the tracker; never mix their info into this demo.
- If David says something in a screenshot is unrelated (e.g. a random website), ignore it everywhere.
- Then re-theme the demo from their real colors, logo style and photos (don't copy their logo or photos), and rewrite that lead's text, phone script and email in the Lead Tracker to use the new details.

## Illustrations must be accurate
- Any map, state shape, or town layout must match real geography. Use `tools/geo/sc-outline.json` (all of SC) or `tools/geo/upstate-outline.json` (Oconee, Pickens, Anderson and Greenville counties). Each has an SVG path plus town x,y positions in its viewBox. Never hand-draw a blob and call it SC.
- If an accurate version isn't practical, use an abstract town list or pin row rather than a fake map.
- Real objects (tools, vehicles, food, equipment) should be recognizable and correct for the trade, and text inside SVGs must be readable (12px or more on screen).
- Check every illustration in a 375px screenshot before committing.

## Fonts: readability rules (learned the hard way)
- Decorative, stencil, art-deco, hairline/high-contrast (e.g. Bodoni, Didot styles) and very wide or condensed display fonts are for **24px and up only**.
- Buttons, labels, chips, kickers, nav, small headings, review text and form labels use the **body font** (weight 500-700 for emphasis).
- Avoid hairline display serifs for headings; prefer sturdier ones (e.g. DM Serif Display over Bodoni Moda).
- No text under 12px, and no font weight of 300 or lighter on text under 18px.
- Check at 375px width before committing.

## Models (token efficiency)
- Design and build work: Opus, matching the style and quality of the existing demos (a separate polish pass isn't needed if these rules are followed).
- Routine edits, data updates and scripts: Sonnet.
- Keep parallel agents to what's needed, and avoid second passes.
