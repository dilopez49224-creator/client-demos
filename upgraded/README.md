# Upgraded demos (Part 3)

Status of the nine Vercel demo projects targeted for the "upgraded" pass
(demo banner, noindex meta, missed-call text-back section, sample reviews).

Date: 2026-11-05

## Summary

All nine projects were **skipped**. None of their source could be obtained in
full from this environment, so nothing was reconstructed or guessed. No Vercel
project, deployment, domain or setting was changed (read-only access only).

| Project | Status | Source URL attempted | Deployment inspected |
|---|---|---|---|
| mackeys-demo | skipped | https://mackeys-demo.vercel.app/ | dpl_3doXR5jsanAvfMLQSbbMZ3bXyy2U (src/index.html) |
| carolina-lawn-demo | skipped | https://carolina-lawn-demo.vercel.app/ | dpl_5QcbXmB1x8JxthUwjH78BRySsouX (src/index.html) |
| mike-durham-demo | skipped | https://mike-durham-demo.vercel.app/ | dpl_DqzLbGSHUAUtuMCTh4fQmsjsnD2i (src/index.html) |
| dyars-diner-demo | skipped | https://dyars-diner-demo.vercel.app/ | dpl_9GjzqCdogJcvwift87uMSACZuaWp (src/index.html) |
| mac-smiths-demo | skipped | https://mac-smiths-demo.vercel.app/ | dpl_2A1VzcBhVdoMLMahY26jWz2rXniD (src/index.html) |
| bangkok-demo | skipped | https://bangkok-demo.vercel.app/ | dpl_LQ4Wwr9dzdcPJvEo5w3ZTLu1VWV9 (src/index.html) |
| fastbay-demo | skipped | https://fastbay-demo.vercel.app/ | dpl_AqRfrJ4wErn1a18JocVHBvyRPLtu (src/index.html) |
| michaels-property-demo | skipped | https://michaels-property-demo.vercel.app/ | dpl_8cYiFdg9CpsofHWiwXUJ6HgzEFhC (src/index.html) |
| ultimate-hair-demo | skipped | https://ultimate-hair-demo.vercel.app/ | dpl_5QbPytcUs3rBBRNWGvrwPkWkkD5V (src/index.html) |

## Why every project was skipped

Each project is a single static `src/index.html` (confirmed via the Vercel
deployment file listing) with no password/SSO protection, served at
`https://<project>.vercel.app/`. Four ways of reading that file were tried;
all failed for the same reason on all nine:

1. `curl -sSL https://<project>.vercel.app/` — the session's egress proxy
   answered **403 to CONNECT** for every `*.vercel.app` host (policy denial;
   the proxy README says not to retry or route around it).
2. Vercel MCP `web_fetch_vercel_url` — refused with **403 forbidden** at the
   `read_protection_bypass` stage (it needs to create a share link on the
   deployment, which the connector is not authorised to do).
3. Vercel MCP `get_deployment_file_contents` — returned the file but
   **truncated** (roughly 10–15 KB omitted per file); the tool has no
   range/offset parameter, so the remainder is unreachable.
4. First-party `WebFetch` — `getaddrinfo ENOTFOUND <project>.vercel.app`
   (host not in the session's allowed network domains; and it would return a
   converted rendering rather than the source anyway).

The truncated fragments that did come back are only the `<head>` and the start
of the `<style>` block; they were not saved or used.

## How to unblock

Allow `*.vercel.app` (or the nine hostnames above) in the cloud session's
network settings, or drop each project's `index.html` into
`upgraded/<project-name>/` by hand, then re-run this pass. The upgrade itself
(banner, robots meta, text-back section, sample reviews, each styled to the
site's own fonts/colours) is straightforward once the full HTML is available.
