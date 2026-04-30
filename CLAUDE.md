# SpendNod Landing Page — CLAUDE.md

## Project Overview
Static HTML landing page for SpendNod — a free, open-source, self-hosted, human-in-the-loop authorization gateway for AI agents.

- **Repo:** https://github.com/gstack-ds/spendnod-landing
- **GitHub (product):** https://github.com/gstack-ds/spendnod
- **Deployed:** Vercel
- **Stack:** Static HTML/CSS/JS — no build step, no package.json

## File Structure
```
spendnod-landing/index.html        — Main landing page
spendnod-landing/enterprise/       — Enterprise/managed hosting page (with PostHog + hamburger)
enterprise/                        — Root-level enterprise page (older, no PostHog/hamburger)
spendnod-landing/terms/            — Terms of Service (attorney review pending — do not edit)
spendnod-landing/privacy/          — Privacy Policy (attorney review pending — do not edit)
vercel.json                        — Vercel routing config (do not edit)
favicons/                          — Favicon assets (do not edit)
```

## Current State (as of 2026-04-30)
SpendNod was repositioned from a paid SaaS to a free, open-source project. All pricing tiers removed. Primary CTAs now point to GitHub.

## Design Decisions Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-04-30 | Remove all pricing tiers | Pivoting to open-source; pricing removed from main and enterprise pages |
| 2026-04-30 | Keep enterprise page as managed hosting lead gen | Contact-us funnel for teams that don't want to self-host |
| 2026-04-30 | Retain existing CSS (including pricing styles) | Unused CSS is harmless; avoids risk of breaking layout |
| 2026-04-30 | Both enterprise pages kept in sync | `enterprise/` (root) and `spendnod-landing/enterprise/` serve same content |

## Current TODOs

- [ ] **HIGH** — Update page `<title>` tags to reflect open-source positioning (currently still says "Human Authorization for AI Agent Transactions")
- [ ] **HIGH** — Terms and Privacy pages still reference plan tiers ($0, Starter, Pro) — update once attorney review complete
- [ ] **MED** — `enterprise/index.html` (root) lacks PostHog analytics and hamburger mobile nav; consider syncing with nested version
- [ ] **MED** — Add GitHub star count or "Built by Stack Industries" badge to hero
- [ ] **LOW** — Remove unused pricing CSS classes from stylesheets after content stabilizes

## Common Mistakes / Active Rules

- **Do not edit terms or privacy pages** — attorney review pending as of 2026-04-30
- **Do not edit vercel.json or favicon files** — treat as locked
- **Both enterprise pages must stay in sync** — apply changes to both `enterprise/index.html` and `spendnod-landing/enterprise/index.html`
- **No build step** — changes to HTML files are deployed directly by Vercel on push to main

## Gotchas Log

*(none yet)*
