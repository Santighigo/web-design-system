# 02 — Visual rules

## Typography

- **Two typefaces, maximum.** A sans that does everything (headlines, body, buttons, labels) and, optionally, a serif or display face as an editorial accent.
- **One sentence, one typeface.** Never write a headline half in the sans and half in the serif ("Sites that convert. *Processes that run themselves.*" in two faces). The accent face is for whole standalone lines: a quote, a big step number, a closing line.
- **Emphasis is color.** To highlight words in a headline, change their color, not their font.
- **No monospace** unless the brand includes one. "Tech" doesn't need mono to look technical.
- **Micro-labels / eyebrows:** `11px`, uppercase, `letter-spacing: 0.16em`, muted color. Same sans, no mono.
- Don't add a font, even for a single effect (ASCII art, a counter), without asking.
- Headlines wrap in 1–2 lines on desktop. If a headline breaks into 3 narrow lines, widen its container.
- Subtitles: `font-weight: 400`, around 75–80% foreground opacity. Bold subtitles compete with the headline.

## Color

- **One primary** for CTAs, links, active states and key lines.
- **Supporting tones** of the primary (a deeper and a mid version) can be mixed in freely.
- **One accent** (usually warm against a cool primary). Use it as *one* focal point per section: a check icon, the lead node in a diagram, the top layer of a stack, a hover state. Never fill a headline or the primary CTA with it.
- **Contrast:** body text and secondary text pass WCAG AA (4.5:1). Accent-colored text is the usual failure; darken it or make it large text.
- **Dark grounds are near-black** (e.g. `#0C0F12`), not saturated navy.
- **Neutral background** is barely tinted off-white, not pure gray. Cards are white on it.
- **Hairlines** for borders: foreground at ~9% opacity.
- **On-color text:** when a panel is filled with a dark or brand color, set every text color inside it explicitly (title white, labels `white/50`, body `white/70–85`). Global heading colors will otherwise override inherited color.

## Theme

- Lock one theme for the whole site. Light usually fits small-business buyers better; dark can feel cold or "for developers".
- Keep the other theme's tokens defined but unused, so switching later is one class.

## Radius

- **One radius token** (8px is a good default) for buttons, cards, tabs, inputs, panels, the header.
- One step smaller for badges and small icon tiles.
- Fully round only for decorative blobs.
- Sweep the codebase for stray `rounded-full`, `rounded-2xl`, `rounded-xl` when you change it.

## Shadow and material

- Every hand-built card, bubble or chip gets a soft ambient shadow, roughly `0 2px 14px rgb(0 0 0 / 0.10)`. A flat shape with no shadow reads as unfinished.
- Glass effects (blurred translucent backgrounds) go on floating elements only, like a pill nav.

## Backgrounds

- Plain by default. No dot grids, hairline grids, or noise unless the brand calls for it.
- If you use a gradient hero, keep the area behind the copy lightest (maximum contrast) and let the color deepen away from it. A very light grain overlay (SVG `feTurbulence`, opacity ~0.06, `mix-blend-mode: overlay`) is fine.
- When text has to sit on top of a busy graphic, fade the whole graphic (e.g. opacity 0.3) before trying to cut holes in it. Don't swap the graphic.

## Graphics

- Prefer one signature graphic (a diagram of how the service works) reused across the site, in compact and full variants, over many unrelated illustrations.
- Diagrams over card grids when explaining a system.
- Give graphics room. Don't shrink a graphic to make space for chrome.
- Line charts: smooth curves through the data points (Catmull-Rom converted to cubic Bézier).
- No CSS border triangles for tails or arrows. Use an SVG path or remove it.
- Brand logos come from an icon set (e.g. simple-icons); check that an icon exists before importing it.
