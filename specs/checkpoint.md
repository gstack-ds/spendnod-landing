# Checkpoint — 2026-04-30

## What was done
Repositioned SpendNod landing page from paid SaaS to free open-source project.

**Main page (`spendnod-landing/index.html`):**
- Removed entire pricing section (Free/$29/$99 tiers + Enterprise card)
- Hero: new headline "Open-source authorization gateway for AI agents"
- Hero: added MIT License / Free forever / Self-host anywhere badge strip
- All CTAs now point to https://github.com/gstack-ds/spendnod
- Nav: removed Pricing link

**Enterprise pages (both `enterprise/index.html` and `spendnod-landing/enterprise/index.html`):**
- Repositioned as managed hosting / support lead gen — not a pricing page
- Pricing section ($799/$2499/Custom) replaced with single "contact us" card
- Hero rewritten: "Managed hosting and enterprise support for SpendNod"
- FAQ: self-hosting answer updated — "it's open source, that's the default"
- CTA: added GitHub secondary button

## Current state
All pages deployed to Vercel via push to main (commit 2945dd3). Site is live.

## Known issues / Next session
- Page `<title>` tags not updated yet (still old SaaS copy)
- Terms/Privacy pages reference plan tiers — hold for attorney review
- `enterprise/index.html` (root) is missing PostHog + hamburger nav vs nested version
