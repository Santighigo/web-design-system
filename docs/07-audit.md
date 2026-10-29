# 07 — Auditing a site

Audit against objective criteria, not "look for what's wrong". Every finding has evidence: a `file:line`, a live URL response, a screenshot, a measured contrast ratio. Report template: [`templates/AUDIT-REPORT.md`](../templates/AUDIT-REPORT.md).

## Phase 1 — Raw audit

### Critical: breaks sales or trust

- [ ] **Every contact path works in production.** Submit the form on the live site. Click the phone/WhatsApp link. Open the email link. Check that env vars made it into the deployed build (search the shipped JS for the webhook URL).
- [ ] Phone numbers and emails are real, not placeholders.
- [ ] Form submits can report failure (no `no-cors` fire-and-forget).
- [ ] Social proof is real. Any "example" metrics or sample testimonials are a critical finding.
- [ ] Social links aren't `href="#"`.

### SEO basics

- [ ] `sitemap.xml` returns XML with every public URL (and every locale).
- [ ] `robots.txt` is a real file (not an HTML 404 with status 200) and declares the sitemap.
- [ ] Structured data: `LocalBusiness` / `ProfessionalService` JSON-LD with name, area served, phone, `sameAs`.
- [ ] `metadataBase`, `og:image`, `twitter:card = summary_large_image`. Links get shared in messaging apps; a preview without an image looks like spam.
- [ ] Canonical URLs, consistent trailing-slash policy.
- [ ] `hreflang` for every locale.
- [ ] Title contains what customers search (task + industry + city for local businesses), not the abstract category.
- [ ] Own domain. A free hosting subdomain reads as a demo.

### Conversion / copy / UX

- [ ] The hero says who it's for and what they get, in their words. It doesn't use the phrase every competitor uses.
- [ ] The LCP element is visible without waiting for animation.
- [ ] If there are no prices, the CTA sells the first step: what you get, how long it takes, why it's worth it.
- [ ] There's a lighter action for visitors not ready to contact (a full case study, a short quiz).

### Accessibility (WCAG 2.1 AA)

- [ ] Text contrast ≥ 4.5:1, including accent-colored CTAs and labels on gradients.
- [ ] Form errors and success messages are in `aria-live` regions.
- [ ] Inputs have `type`, `autoComplete`, `inputmode`.
- [ ] One `h1`, `h2` per section, landmarks (`main`, `nav`, `header`, `footer`), `aria-label` on icon buttons, `aria-labelledby` on sections.
- [ ] Reduced motion respected.

### Nice to have

- [ ] `theme-color` meta.
- [ ] No dead assets shipped.
- [ ] Images compressed (static exports don't optimize them for you).

## Phase 2 — Benchmark

Compare against 5–10 real competitors on objective axes:

| Axis | Who wins today | Where we are | Gap |
|---|---|---|---|
| Craft / design | | | |
| Message in the customer's language | | | |
| SEO / discoverability | | | |
| Price transparency | | | |
| Real proof | | | |
| Local trust (domain, business profile, contact details) | | | |
| Vertical focus | | | |

Typical verdict: great design loses to worse sites that have a real phone number, published prices and a Google presence. The gap is rarely design; it's fundamentals.

## Phase 3 — Executable fixes

Turn each finding into an unambiguous instruction an agent can execute: file, change, acceptance check. Order by leverage: criticals first, then the hero message, then SEO fundamentals, then everything else.
