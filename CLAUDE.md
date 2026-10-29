# Web design agent rules

Brand-agnostic rules for any agent building or editing a website. Brand specifics (palette, fonts, references, decisions) live in the project's own `CLAUDE.md`; this file defines how to work.

Full rationale for each rule: `docs/` in the web-design-system repo.

## Before writing code

- Read the project `CLAUDE.md` decisions log. Never reopen a decision listed there unless the user asks.
- Read the design tokens file (usually `globals.css`). Every new surface reuses its colors, spacing, radius, easing and type scale. No ad-hoc hex, px or easing values in components.
- Open the visual references and look at them. Do not work from a remembered description of them.
- If a graphic or component already exists in the codebase, reuse it 1:1 (same geometry, transforms, colors, animation params). Do not rebuild or "approximate" it.
- If the brief is ambiguous, ask one question. Don't guess and don't add things nobody asked for.

## Visual rules

- Two typefaces maximum: a sans for everything, an optional serif or display face for whole standalone lines (a quote, a big number). Never mix two typefaces inside one sentence. Emphasis inside a headline is color, not a font swap.
- No monospace font unless the brand explicitly includes one.
- One primary color for CTAs and links. One accent color, used as a single focal point per section. Headlines and the primary CTA are never in the accent.
- Accent text must pass WCAG AA (4.5:1) against its background. Darken it for text if needed.
- Dark surfaces are near-black, not saturated navy, unless the brand says otherwise.
- One radius token for all UI (buttons, cards, tabs, inputs, header). Small chips may use one step smaller. Decorative blobs are the only exception.
- Every hand-built card, bubble or chip gets a soft ambient shadow (around `0 2px 14px rgb(0 0 0 / 0.10)`).
- Backgrounds are plain. No dot grids, hairline patterns or noise unless the brand asks for them.
- Lock the page to one theme (light or dark). Don't mix themed sections at random.
- Line charts are smooth curves (Catmull-Rom to cubic Bézier), never straight segments with rounded joins.
- No CSS border-triangle hacks. Build shapes as real SVG paths or drop them.

## Layout rules

- One message and one primary CTA per hero. The hero fills the first viewport (`min-h-[100svh]`).
- The primary CTA has the same label everywhere it appears.
- Never show the same information in two sections or two pages. Merge or delete the duplicate.
- Cards of the same kind look the same everywhere on the site.
- Never truncate content with `line-clamp` to make a layout fit. Shorten the copy.
- Headings don't hardcode counts ("Eight services"). They go stale.
- On mobile, hide diagrams that get cramped rather than shrinking them to illegibility.
- Horizontally scrollable rows on mobile show a peek of the next item and use `touch-action: pan-x` with scroll snap.
- Every page has its own contact block; the nav "Contact" link scrolls to the current page's block.

## Copy rules

- Never invent metrics, clients, testimonials, team members, eyebrows, labels or CTAs. If a slot has no real copy, leave it empty and say so.
- Metrics without a verified source render as scope ("3 automated flows + dashboard"), never as results.
- Don't promise things the business doesn't always do.
- No tech-stack names in client-facing copy.
- Write in the customer's words: the task, the industry, the outcome.
- No em-dashes in visible copy.
- When copy changes, change it in every locale in the same pass.

## Motion rules

- Above-the-fold content (the LCP element) never starts at `opacity: 0` behind a scroll trigger.
- Entrances animate `transform` and `opacity` only, with explicit from and to states. Every animation ends in a static final state.
- Respect `prefers-reduced-motion` everywhere, including ambient loops.
- Register animation plugins once, in one module.
- SVG rotations use `transform-box: fill-box; transform-origin: center`. Never an inline origin in SVG coordinates.

## Working rules

- Work on a branch. Never push to `main` or production without explicit approval.
- Deploy only when the user says "deploy".
- One feature per PR. Each PR gets a plain-language review doc (template: `templates/PR-REVIEW.md`).
- Run every quality gate before calling something done: typecheck, lint, unit tests, e2e, build, bundle budget, and a visual check on desktop and mobile with a clean console.
- Report honestly what was and wasn't verified.
- When a decision is made or an experiment is reverted, record it in the project `CLAUDE.md` decisions log with the reason.
- Code: no comments, named constants for magic numbers, immutable updates, server components by default with client code only at the leaf.
