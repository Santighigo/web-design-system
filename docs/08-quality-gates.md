# 08 — Quality gates

Nothing is "done" until all of these pass. Report which ones ran and which didn't.

## Automated

```bash
npm run typecheck
npm run lint
npm test          # unit tests, including locale key parity
npm run test:e2e  # e2e, including a crawl of every sitemap URL in every locale
npm run build
npm run budget    # gzip JS budget, e.g. ≤ 240 KB
```

Useful tests to have from day one:

- **Message parity:** every locale has the same keys.
- **Sitemap crawl:** every URL in the sitemap renders, in every locale, with no broken internal links.
- **Content schema:** metrics without `verified` + `source` can't render as results.
- **Nav counts:** the number of nav items / listed services matches the content.

Add generated folders (deploy caches, build output) to the linter's ignore list, or you'll get thousands of false errors.

Also useful: Lighthouse CI with thresholds for performance, accessibility, SEO.

## Manual

- [ ] Open the dev preview. Console is clean: no hydration warnings, no component-library warnings.
- [ ] Every changed section checked at desktop width and at ~375px.
- [ ] Screenshot compared against the annotation or reference.
- [ ] Contrast measured for any new color pairing.
- [ ] Reduced motion toggled on and checked.
- [ ] Every interactive change clicked through (tabs, drawers, forms, nav anchors).

## Reporting

Write what you verified in the PR doc, in three tiers:

- Original change: all gates.
- Follow-up adjustments: which gates ran since.
- What still needs to run before merge.

Never write "all good" when e2e and build haven't run since the last edit.
