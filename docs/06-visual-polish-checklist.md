# 06 — Visual polish checklist

Run this on every hand-built graphic (chart, card, chat bubble, badge, diagram, icon tile) before showing it. The failure mode it prevents: applying the right hex codes and font and assuming that makes it on-brand.

## Before building

- [ ] I opened the real reference images and looked at them, not just read about them.
- [ ] I checked whether this graphic already exists in the codebase. If it does, I'm reusing it 1:1.
- [ ] I checked whether a ready asset fits. If it carries fake data (a dashboard template with invented numbers), I'm not using it whole.

## Shape

- [ ] Lines through data are smooth curves, not straight segments with round joins.
- [ ] No CSS border-triangle tails. Real SVG paths, or no tail.
- [ ] Radius matches the token.
- [ ] Proportions match the reference (padding, icon size relative to text, stroke weight).

## Surface

- [ ] Soft ambient shadow on every floating card/chip/bubble.
- [ ] Background is plain (no dot grid) unless the brand says otherwise.
- [ ] Accent color used once, as a focal point.
- [ ] Text inside colored surfaces has explicit colors and passes contrast.

## Type

- [ ] Only the brand's typefaces. No new font sneaked in.
- [ ] No sentence mixes two typefaces.
- [ ] No invented labels, eyebrows or numbers.

## Final check

- [ ] Screenshot of my output side by side with the reference. I compared them, not just one.
- [ ] Desktop and mobile.
- [ ] Reduced-motion version still looks complete.
