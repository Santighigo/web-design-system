---
name: web-design-build
description: Build or redesign a website section or page following a strict, brand-agnostic design system (positioning first, references, tokens, one typeface per sentence, one accent focal point, unified radius, ambient shadows, one CTA label everywhere, no invented proof, reduced-motion-safe animation, full quality gates). Use whenever the user asks to design, build, redesign, polish or restyle a landing page, website, hero, section, card, nav, pricing, FAQ or contact block, or applies annotated-screenshot feedback to a site, even without naming the skill.
---

# Web design build

You build websites that look considered, read honestly and convert. Follow this sequence every time.

## 0. Load context

1. Read the project `CLAUDE.md` / `AGENTS.md`. Note the decisions log and the "tried and rejected" list. Do not reopen either unless the user asks.
2. Read the tokens file. List the tokens you'll use.
3. If there's no positioning section (who buys, what they search, the one action), ask for it in one message before designing a hero or a page. A section tweak doesn't need it.
4. Search the codebase for an existing component or graphic that does what's asked. If it exists, reuse it 1:1.

## 1. Look at references

Open the reference screenshots or sites the project lists. Look at the actual rendered example of the pattern you're building. If there are none, ask for 1–3 or propose them, naming the one idea each contributes.

## 2. Build

Apply these rules without exception:

**Type** — max two typefaces; never mix them inside a sentence; emphasis = color; no mono; eyebrows 11px uppercase 0.16em muted; headlines in 1–2 lines.

**Color** — primary for CTAs/links/active; accent once per section as a focal point, never on headlines or the primary CTA; AA contrast; set explicit text colors on colored surfaces; dark = near-black.

**Shape** — one radius token everywhere; ambient shadow on every hand-built card/chip; plain backgrounds; smooth curves for charts; no CSS triangles.

**Layout** — hero fills the viewport, one message, one primary CTA; identical CTA label everywhere; no duplicated sections; same-kind cards identical site-wide; no line-clamp; no counts in headings; tabs-to-panel pattern per `docs/03`; every page has its own `#contact`.

**Copy** — never invent metrics, clients, testimonials, labels or eyebrows; unsourced numbers become scope; no stack names; customer's words; no em-dashes; every locale in the same pass.

**Motion** — LCP visible without animation; `fromTo` on transform/opacity; static final state; reduced-motion gated; SVG rotations with `transform-box: fill-box`.

**Code** — tokens only, no ad-hoc values; server components by default; named constants; no comments.

## 3. Mobile

Check at ~375px: h2 in two lines, cramped diagrams hidden or re-cropped, horizontal rows with a peek and `touch-action: pan-x`, drawers scrollable, step panels stable in height.

## 4. Polish checklist

Run `docs/06-visual-polish-checklist.md` line by line on anything hand-built. Screenshot your output next to the reference and compare.

## 5. Verify

Start the dev preview. Clean console. Desktop + mobile screenshots. Run the project's gates (typecheck, lint, tests, e2e, build, budget). Report exactly which ran.

## 6. Record

Add any new decision or reverted experiment to the project `CLAUDE.md` with date and reason. Don't commit, push or deploy unless asked.

## When applying annotated screenshots

Change only what's marked. If a mark conflicts with the current graphic or background, keep the graphic and solve it another way (move the text, fade the graphic), or ask. On "revert", revert fully and log it.
