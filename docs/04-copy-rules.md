# 04 — Copy rules

Design gets people to read. Copy decides if they act. Most of the trust a site earns or loses is here.

## Proof

- **Never invent** metrics, clients, testimonials, team members or logos. Not as placeholders either. Sample testimonials labeled "sample" still destroy credibility; remove the section until real ones exist.
- A number appears only with a source. Keep sources in the repo (content front-matter or the PR doc) even if the page only says "Industry average".
- Unverified metrics render as **scope** ("3 automated flows + dashboard") or don't render. Enforce it in the content schema: a metric needs `verified: true` and a `source`.
- Real cases beat everything. If the business has real projects, they go on the site before any illustrative example.
- A case with a live site gets a "Visit project" link.

## Promises

- Don't promise what the business doesn't do every time. "We measure hours before and after" gets cut if it's not always true. Replace it with honest, general phrasing.
- No "closed budget per stage" if prices actually depend on the project. Say what *is* clear.

## Language

- Write in the customer's words: the task and the industry ("online orders for your catering business"), not your category ("bespoke digital systems").
- Lead with the outcome for them, not your process.
- No stack names in client copy (frameworks, libraries, tools). The client doesn't care.
- Pick one register (formal-simple or casual) per site and keep it. Avoid slang on a business site.
- Short. If a card description needs to be clamped to fit, it's too long.
- No em-dashes (—) in visible copy.
- No hardcoded counts in headings ("Our eight services"). They go stale the day you add one.
- Fix stray untranslated words (an English term left in a Spanish title).

## Consistency

- One CTA label everywhere.
- One title per item stored in one field, so it updates everywhere at once (home, index, detail page).
- Services you no longer offer disappear from *every* list, including sidebars and "other services" menus. Keep a single constant of hidden items and reuse it.
- Every locale changes in the same pass. Keep a test that asserts message-key parity across locales. Mark machine-translated locales as needing native review.

## When the agent writes copy

- In client deliverables (decks, PDFs, posts built from the site), reuse the site's copy verbatim. Don't add eyebrows, labels, section intros or CTAs that aren't in the source.
- If a slot has no copy, leave it empty and say so. Don't fill it.
- When rewriting, keep the facts identical. Only the wording changes.
