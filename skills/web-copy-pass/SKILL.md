---
name: web-copy-pass
description: Run a text-only pass over a website, page by page, in every locale - unify CTA labels, remove promises the business doesn't always keep, strip tech-stack jargon, replace invented or unsourced proof with scope, fix truncated text by shortening copy, drop stale counts and em-dashes, and remove duplicate content - without touching facts or structure. Use when the user asks to review, tighten, simplify, fix or rewrite the copy/text/wording of a site, or shares screenshots with text notes, even without naming the skill.
---

# Web copy pass

A copy pass changes words, not facts and not layout. Work page by page; show each page's changes before moving on.

## Rules

- **Facts stay identical.** Never add a metric, client, testimonial, feature or promise. If the user's wording is the source, reuse it verbatim.
- **Every locale in the same pass.** Keep message-key parity; run the parity test.
- **One title per item lives in one field**, so a change propagates to every place it appears. Say where it shows up.

## What to look for on each page

1. **CTA labels.** The primary action must say the exact same thing everywhere (header, hero, mobile bar, closing blocks, detail pages).
2. **Promises.** Any "we always", "we measure", "closed budget", "response in under X" that the business can't guarantee every time. Rewrite to what's always true, or cut.
3. **Jargon.** Framework, library and tool names in client copy. Replace with what the client gets.
4. **Proof.** Unsourced numbers become scope. Sample testimonials get removed.
5. **Truncation.** Any `line-clamp` or "..." hiding text. Remove the clamp and shorten the copy instead.
6. **Counts.** Headings with numbers ("Eight services") become count-agnostic.
7. **Duplicates.** The same idea said in two sections or two pages. Keep one.
8. **Subtitles that add nothing.** Remove them.
9. **Language slips.** Untranslated words, mixed registers, slang on a formal site.
10. **Em-dashes** in visible copy.
11. **Retired offers** still listed somewhere (sidebars, "other services", footers).
12. **FAQ.** Keep 3–5 questions that answer real objections (price, time, ownership). Drop the reassuring filler.

## Output

For each page, a short before → after list in plain language. Append it to the relevant PR review doc under "Update (copy pass)". Run typecheck, lint and unit tests after each page; say that build, budget and e2e still need a rerun if they haven't run.
