# Upgraded demos (Part 3)

Status of the nine Vercel demo projects given the "upgraded" pass. Each copy
lives in `upgraded/<project-name>/index.html` and is the live production page
with four additions, styled with that site's own fonts, colours and card/button
styles. Nothing else on the page was changed, and no Vercel project,
deployment, domain or setting was touched (read-only access only).

Date: 2026-11-05

## The four additions

1. Fixed top banner: "Demo preview built by David — not the official site."
   (`body` and `scroll-padding-top` are offset by the banner's measured
   height, so nothing is covered; none of the sites had fixed headers).
2. `<meta name="robots" content="noindex, nofollow">` replacing the existing
   `noindex,nofollow` meta.
3. "Never miss a call — we text you back in seconds" section with a CSS/SVG
   phone mock: a missed-call notification followed by an instant SMS reply in
   the business's name. No phone numbers are shown or invented.
4. "Sample reviews" section with three placeholder reviews (generic first
   names only, each card tagged "Sample review", plus a disclaimer). Each
   site's existing single review quote was left untouched; the new section
   sits directly after it.

## Per-project status

| Project | Status | Source URL used | Deployment |
|---|---|---|---|
| mackeys-demo | upgraded | https://mackeys-demo.vercel.app/ | dpl_3doXR5jsanAvfMLQSbbMZ3bXyy2U |
| carolina-lawn-demo | upgraded | https://carolina-lawn-demo.vercel.app/ | dpl_5QcbXmB1x8JxthUwjH78BRySsouX |
| mike-durham-demo | upgraded | https://mike-durham-demo.vercel.app/ | dpl_DqzLbGSHUAUtuMCTh4fQmsjsnD2i |
| dyars-diner-demo | upgraded | https://dyars-diner-demo.vercel.app/ | dpl_9GjzqCdogJcvwift87uMSACZuaWp |
| mac-smiths-demo | upgraded | https://mac-smiths-demo.vercel.app/ | dpl_2A1VzcBhVdoMLMahY26jWz2rXniD |
| bangkok-demo | upgraded | https://bangkok-demo.vercel.app/ | dpl_LQ4Wwr9dzdcPJvEo5w3ZTLu1VWV9 |
| fastbay-demo | upgraded | https://fastbay-demo.vercel.app/ | dpl_AqRfrJ4wErn1a18JocVHBvyRPLtu |
| michaels-property-demo | upgraded | https://michaels-property-demo.vercel.app/ | dpl_8cYiFdg9CpsofHWiwXUJ6HgzEFhC |
| ultimate-hair-demo | upgraded | https://ultimate-hair-demo.vercel.app/ | dpl_5QbPytcUs3rBBRNWGvrwPkWkkD5V |

## How the source was obtained

Each project is a single static `src/index.html` (confirmed via the Vercel
deployment file listing) with no password/SSO protection. The full page was
fetched with `curl -sSL https://<project>.vercel.app/` once `*.vercel.app`
was allowed in the session's network settings (an earlier attempt was blocked:
the proxy denied the hosts, the Vercel MCP share-link fetch was forbidden, and
the deployment-files API truncates at a few KB). Every fetch returned HTTP 200
and a complete document ending in `</html>`. None of the pages reference local
CSS/JS/image files (only Google Fonts), so the single HTML file is the whole
site. Fetched content was treated as untrusted data and never executed.
