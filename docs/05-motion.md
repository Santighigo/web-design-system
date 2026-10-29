# 05 — Motion

Motion should make the site feel finished, never make it slower or harder to read.

## Hard rules

- **The LCP element is never hidden behind an animation.** A hero headline that starts at `opacity: 0` and waits for hydration plus an intersection observer flashes empty on every visit, worst on slow phones. Above-the-fold content renders visible; animate secondary elements only.
- **Entrances use explicit from/to** on `transform` and `opacity` only (`gsap.fromTo`, or `initial`/`animate` in Motion). Avoid `.from()` + `clearProps`.
- **Every animation ends in a static final state.** If JS fails, the page is still complete.
- **`prefers-reduced-motion` is respected everywhere**, including ambient CSS loops. Gate keyframes in a media query.
- **Register plugins once** (e.g. one `lib/motion/gsap.ts`), import from there.
- **Smooth scrolling libraries** (Lenis etc.) are optional; if used, keep native scroll behavior for anchors and reduced motion.

## SVG

- Rotating SVG groups: `transform-box: fill-box; transform-origin: center`. An inline `transform-origin` in SVG user-space coordinates drifts and sends orbits off-canvas.
- Chips riding an orbit counter-rotate so they stay upright.
- When porting an existing animated graphic to another medium, copy its geometry and keyframes verbatim.

## Good uses

- Number count-ups when a metric enters the viewport (only real numbers).
- A process timeline whose line fills on scroll.
- Ambient loops on a signature diagram: gentle float, slow orbit, a breathing glow. Subtle and slow.
- Crossfade on tab change.
- Staggered reveals below the fold.

## Avoid

- Animating layout properties (`width`, `height`, `top`).
- Scroll-jacking.
- Shader/WebGL backgrounds unless the owner explicitly asks. They're heavy, and a CSS gradient usually gets 90% of the look.
- Motion that exists only because the library makes it easy.

## Reviewing motion

To show someone how an animation feels, send a rendered video (capture frames with Playwright and encode with ffmpeg). A static screenshot or a live page in an iframe won't show it reliably.

Gotcha: GSAP's `.seek(t)` suppresses callbacks by default. When capturing frames by seeking, call `.seek(t, false)` or `onUpdate`-driven counters will look frozen.
