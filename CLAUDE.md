# SpendNod Landing Page — CLAUDE.md

## Project Overview
Static HTML landing page for SpendNod — a free, open-source, self-hosted, human-in-the-loop authorization gateway for AI agents.

- **Repo:** https://github.com/gstack-ds/spendnod-landing
- **GitHub (product):** https://github.com/gstack-ds/spendnod
- **Deployed:** Vercel
- **Stack:** Static HTML/CSS/JS — no build step, no package.json

## File Structure
```
spendnod-landing/                  — Vercel Root Directory: the ONLY folder served at www.spendnod.com
spendnod-landing/index.html        — Main landing page
spendnod-landing/enterprise/       — RETIRED: unlinked, /enterprise 308-redirects to / (file kept for reuse)
spendnod-landing/terms/            — Terms of Service (legal wording locked, attorney review pending; chrome may change)
spendnod-landing/privacy/          — Privacy Policy (legal wording locked, attorney review pending; chrome may change)
spendnod-landing/vercel.json       — Served Vercel config: cleanUrls, trailingSlash, /enterprise redirect
enterprise/                        — Root-level enterprise copy, NOT served
vercel.json                        — Root copy, NOT used by the deploy
favicons/                          — Root-level favicon assets, NOT served (live copies sit in spendnod-landing/)
```

## Current State (as of 2026-10-22)
SpendNod is a free, open-source project. No pricing tiers. Primary CTAs point to https://app.spendnod.com (hosted version); GitHub links are secondary. The enterprise page is retired. EU AI Act copy carries no dates or fine figures.

## Design Decisions Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-04-30 | Remove all pricing tiers | Pivoting to open-source; pricing removed from main and enterprise pages |
| 2026-04-30 | Retain existing CSS (including pricing styles) | Unused CSS is harmless; avoids risk of breaking layout |
| 2026-04-30 | Add hosted CTA alongside self-host | Dual path: "Start free" → app.spendnod.com (primary), "View/Self-host on GitHub" (secondary) |
| 2026-10-22 | Dated compliance claims and fine figures removed from marketing copy | EU AI Act mentions only state that human oversight and record keeping are core requirements for high-risk AI systems |
| 2026-10-22 | Enterprise page retired, unlinked, and redirected to the homepage | It sold offerings SpendNod doesn't provide. Files kept in the repo for possible reuse. Supersedes the 2026-04-30 lead-gen and keep-in-sync decisions |
| 2026-10-22 | Keep unserved root copies (`enterprise/`, `vercel.json`, `favicons/`) as they are | No changes, no deletion |
| 2026-10-22 | Keep the `/enterprise/` redirect rule | Redundant with trailingSlash but harmless; review warning closed |
| 2026-10-22 | Terms/Privacy lock covers legal wording only | Site chrome (nav, footer links, styles) may change |
| 2026-10-22 | Homepage title mirrors the hero headline | Open-source positioning, keeps the "SpendNod - Page" title pattern |
| 2026-10-22 | Hero credit is a "Built by Stack Industries" link badge to stackindustries.io, not a GitHub star count | Reuses the hero badge style with no new CSS and no status dot; beside the open-source badge on desktop, wraps under it on phone |

## Current TODOs

- [x] **DONE** — Primary CTAs updated: nav + hero + bottom CTA all point to app.spendnod.com
- [x] **DONE** - Homepage `<title>` updated to open-source positioning (2026-10-22)
- [ ] **HIGH** — Terms and Privacy pages still reference plan tiers ($0, Starter, Pro) — update once attorney review complete
- [x] **DONE** - "Built by Stack Industries" hero badge added (2026-10-22)
- [ ] **LOW** - Review warning 2026-10-22: the hero "Built by Stack Industries" link opens a new tab with no screen-reader cue. Consider an aria-label ending "(opens in new tab)".
- [ ] **LOW** — Remove unused pricing CSS classes from stylesheets after content stabilizes (homepage `.compliance-banner` / `.compliance-date` are now unused too)

**Next session starts with:** the HIGH Terms/Privacy plan-tier update if attorney review is back; otherwise the LOW unused-CSS cleanup.

## Common Mistakes / Active Rules

- **Terms and Privacy legal wording is locked** - attorney review pending as of 2026-04-30. The lock covers legal wording only; site chrome (nav, footer links, styles) may change.
- **Do not edit vercel.json or favicon files** — treat as locked. Only `spendnod-landing/vercel.json` is live; it holds the /enterprise redirect.
- **Enterprise page is retired** - don't re-link it or edit the enterprise files without a new decision
- **No build step** — changes to HTML files are deployed directly by Vercel on push to main
- **CTA target** — primary CTA is app.spendnod.com (hosted), not GitHub; GitHub is always secondary

## Gotchas Log

**Date:** 2026-10-22 | **What happened:** Headless Edge screenshot with a 390px window came out clipped on the right; the page laid out wider than 390px | **Root cause:** headless Edge enforces a minimum window width, so phone media queries never fired | **Fix:** screenshot a scratch wrapper page holding a 390px-wide iframe of the page (to open the mobile menu, click `#hamburger` from the wrapper, with `--allow-file-access-from-files`) | **Rule going forward:** phone-width checks need a 390px iframe wrapper, never a direct 390px window
