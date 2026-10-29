---
name: web-design-audit
description: Audit a website with objective, evidence-backed criteria in three phases (raw audit of conversion paths, SEO basics, copy/UX and WCAG AA accessibility; benchmark against real competitors; executable fixes ordered by leverage). Use when the user asks to audit, review, critique, check or "find what's wrong with" a site, landing page or preview, before a launch, or asks why a site doesn't convert or rank, even without naming the skill.
---

# Web design audit

Audit against criteria, not impressions. Every finding needs evidence: `file:line`, a live HTTP response, a screenshot, a measured contrast ratio. No evidence, no finding.

## Inputs

- Live or preview URL, and the codebase if available.
- The positioning (who buys, what they search, the one action). Ask if missing.
- 5–10 competitor URLs. Ask, or find them and confirm with the user.

## Phase 1 — Raw audit

Go through every item in `docs/07-audit.md`. The ones that are found broken most often, check first:

1. **Contact paths in production.** Actually submit the form on the live site; click phone/WhatsApp/email links; grep the shipped JS bundle for the webhook URL to confirm env vars reached the build. Flag `mode: "no-cors"`.
2. **Placeholder data**: dummy phone numbers, placeholder emails, `href="#"` socials, "example" metrics, sample testimonials.
3. **SEO files**: fetch `/sitemap.xml` and `/robots.txt` and check status *and* content type. Look for JSON-LD, `og:image`, `metadataBase`, canonical, hreflang.
4. **LCP gated by animation**: load the page fresh, screenshot at first paint; check whether the hero headline starts at `opacity: 0`.
5. **Hero message**: does it say who it's for in their words, or the same abstract phrase competitors use?
6. **Contrast**: measure accent-colored text and text on gradients.

Classify as 🔴 critical (breaks sales/trust), 🟡 important (SEO, conversion, a11y), 🟢 nice to have. Also list what's already good so nobody "fixes" it.

## Phase 2 — Benchmark

Fill the axis table from `docs/07-audit.md` with evidence for each competitor. Write a one-paragraph verdict: where the site wins, where it throws its advantage away.

## Phase 3 — Fixes

Turn each finding into an executable instruction: file, exact change, acceptance check. Order by leverage: criticals, hero message, SEO fundamentals, the rest.

## Output

Write the report with `templates/AUDIT-REPORT.md` into the project's `docs/` folder. Don't change code during an audit unless the user asks.
