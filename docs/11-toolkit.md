# 11 — Toolkit

The libraries this system has shipped real sites with, what each is for, and the gotchas already paid for. Pick one stack per project; don't mix animation libraries.

## Two proven stacks

| | Component stack | Motion-heavy stack | Static stack |
|---|---|---|---|
| Framework | Next.js (App Router) + React | Next.js (App Router) + React | Plain HTML/CSS/JS |
| Styling | Tailwind CSS v4 | Tailwind CSS v4 | Hand-written CSS with tokens |
| Components | shadcn/ui | Own components | Own markup |
| Animation | Motion (motion.dev) | GSAP + Lenis + lottie-web | CSS transitions |
| Icons | lucide + simple-icons | Inline SVG | Iconify |
| Content | Constants in `lib/` | Velite (MDX) + next-intl | JSON + a Git-based CMS |
| Tests | — | Vitest + Playwright + axe | — |

Use the component stack when you want to build fast from solid primitives. Use the motion-heavy stack for a multi-language site with lots of content and scroll-driven animation. Use the static stack for a small client landing page the client edits through a CMS.

## Components

**[shadcn/ui](https://ui.shadcn.com)**: copy-in components you own and restyle with your tokens.

- Check which primitives your shadcn style is built on. The `base-nova` style uses **Base UI**, not Radix: composition is the `render` prop, not `asChild`:
  ```tsx
  <Button nativeButton={false} render={<a href="/contact" />}>Contact</Button>
  ```
  Same for `SheetTrigger`, `DialogTrigger`: `render={<Button />}`. Add `nativeButton={false}` when it renders a non-button.
- shadcn registries extend it. **[bklit](https://ui.bklit.com)** adds charts built on visx + d3 (not Recharts).
- When installing a registry component asks to overwrite `lib/utils.ts`, answer **no**.
- Re-check imports after installing registry components; paths sometimes arrive broken.

## Animation

Pick **one** of these per project.

**[Motion](https://motion.dev)** (`motion/react`, formerly Framer Motion): declarative React animation.

- Wrap below-the-fold reveals in one `Reveal` component that uses `whileInView` and respects reduced motion.
- Never wrap the hero headline in `whileInView`; it hides the LCP element until hydration (see [05-motion.md](05-motion.md)).

**[GSAP](https://gsap.com)** + **[Lenis](https://lenis.darkroom.engineering)**: timeline and scroll-driven animation, smooth scroll.

- Register plugins once in a single module; import GSAP from there.
- `fromTo` on `transform`/`opacity`, static final state, reduced motion respected.
- When capturing frames by seeking, use `.seek(t, false)` so callbacks fire.

**[lottie-web](https://github.com/airbnb/lottie-web)**: plays Lottie JSON animations.

- Use the light build with the SVG renderer, lazy-loaded near the viewport.
- Keep each file small (e.g. under 80 KB) and always have an SVG/CSS fallback.
- Lottie files can come from a script in the repo or from a motion tool like **[Jitter](https://jitter.video)**. Before shipping a Jitter export, strip the watermark, recolor it to the tokens and remove baked-in backgrounds.

**[NumberFlow](https://number-flow.barvian.me)** (`@number-flow/react`): animated number counters. Only for real, sourced numbers.

## Icons

- **[lucide](https://lucide.dev)**: interface icons.
- **[simple-icons](https://simpleicons.org)**: brand logos. Not every brand exists in it (LinkedIn was removed); check before importing.
- **[Iconify](https://iconify.design)**: one web component for any icon set, good for static sites.

## Content, i18n, CMS

- **[Velite](https://velite.js.org)**: typed MDX content with a schema. Put honesty rules in the schema (a metric needs `verified` and `source`).
- **[next-intl](https://next-intl.dev)**: localized routes and messages. Add a test that every locale has the same message keys.
- **[Decap CMS](https://decapcms.org)**: Git-based CMS for static sites, so clients can edit copy. It needs the hosting provider's identity and Git gateway, and the site must be linked to the repo. If the HTML has a static fallback for JSON content, keep both in sync.

## Quality

- **[Vitest](https://vitest.dev)** + Testing Library: unit tests.
- **[Playwright](https://playwright.dev)** + **[axe](https://github.com/dequelabs/axe-core-npm)**: e2e, sitemap crawl and accessibility checks.
- **Lighthouse CI**: performance/accessibility/SEO thresholds.
- A bundle budget script (gzip JS ≤ a fixed limit) run as a gate.

## Other pieces

- **Fonts**: self-host (`next/font` or local woff2 with `display: swap`) or Google Fonts. Two families maximum.
- **Maps**: [Leaflet](https://leafletjs.com) for a lightweight embedded map.
- **Forms**: send to a webhook or an email API like [Resend](https://resend.com). Validate with [zod](https://zod.dev). Never fire-and-forget with `no-cors`.
- **Hosting**: any static or Next.js host. Connect it to the Git repo for automatic deploys, keep a separate preview site for proposals, and use your own domain before launch.

## Tried and not recommended by default

- **WebGL shader gradients** for hero backgrounds: heavy, and a stacked CSS `radial-gradient` gets most of the look. Use one only when explicitly asked.
- **Two animation libraries in one project**: pick Motion *or* GSAP.
- **A monospace font** added just to look "technical".
