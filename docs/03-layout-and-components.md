# 03 — Layout and components

## Page structure

- Every section has to earn its place. If it repeats another section or another page, delete it or merge it.
- One good page beats two similar pages competing in search. Fold near-duplicates together and 301-redirect the old URL.
- When you remove a page, decide explicitly: redirect, or let it 404. Write the decision down.
- When you hide a page from navigation to rebuild it later, keep the URL alive, drop it from the sitemap and mark it `noindex`.

## Header / nav

- A floating pill nav works well: detached from the edges (~24px), ~56px tall, translucent glass.
- Logo pinned left, primary CTA and language switcher pinned right, links centered. Don't crowd everything toward the middle.
- The current page's nav item is highlighted, using the same color as hover.
- Mobile: a sheet/drawer menu with the same items, plus a sticky bottom bar with the primary CTA if the action matters a lot.

## Hero

- One message, one primary CTA, one secondary CTA at most.
- Fill the first viewport (`min-h-[100svh]`) so the fold doesn't cut it.
- Centered single column is a safe, strong default: headline, subtitle, CTAs, a compact graphic or a small proof card below.
- Lead with the customer's benefit (hours saved, orders received), not your internal process.
- If the graphic doesn't work on mobile, show a different, simpler one or none at all.
- A small proof card in the hero (2–3 animated numbers) only with sourced numbers, labeled as what they are ("Industry average").

## CTAs

- Exactly one primary action, with **the same label** in the header, hero, mobile bar and every closing block.
- If the action has state (a quiz started and not finished), the label says what continues: "Continue quiz (2/5)", not "Continue (2/5)".
- Primary: filled in the primary color, ~44–48px tall, visible hover (slight lift + darker fill).
- Secondary: outline or text, lower weight.
- Don't put the primary CTA in every section. Header, hero, and the closing block are enough.

## Cards

- Cards of one kind look identical everywhere they appear (a case card on the home, the cases index and "related cases" at the bottom of a service page).
- Image-backed case cards: client name on top, title + scope at the bottom, no category tag noise.
- Clients without permission show as "Confidential client". Never invent a name.
- Card text is shown in full. If it doesn't fit, rewrite it shorter; never `line-clamp`.
- An odd number of cards in a grid: center the last row.
- Merge repeated blocks inside a card. A three-bullet "What we deliver" list next to a separate "Scope" stat becomes one line: "Site + admin panel + integrations".

## Tabs connected to a panel

The pattern where tabs sit on top and the selected tab merges into the panel below:

- Active tab has the same background as the panel, `border-bottom: 0` and `margin-bottom: -1px`. Inactive tabs are flat.
- Tabs carry the top radius; the panel has a **square top** and rounded bottom, so the active tab connects without a notch.
- Mobile: tabs in a horizontally scrolling row with hidden scrollbar, `touch-action: pan-x`, `overscroll-behavior-x: contain`, scroll snap, and sizes small enough that the next tab peeks (~25px).
- Desktop: a grid, no `overflow-x: auto` (it can create a phantom vertical scrollbar with the `-1px` margin).
- Use ARIA tab roles; crossfade the panel on change.

## Process / "How we work"

- 3–4 steps, short. Big step numbers are a good place for the accent typeface.
- A connected timeline (vertical line + dot per step, filling on scroll) reads better than loose cards, on mobile too.
- No subtitle unless it says something the steps don't.

## FAQ

- 3–5 questions that remove real objections: price ("depends on the project", and why), timeline (an example framed as a reference), ownership ("domains, servers and credentials in your name from day one").
- Drop questions that only exist to sound reassuring.

## Contact

- Usually no separate contact page: every page ends with the same contact block (primary action + direct channels).
- The nav "Contact" link scrolls to the current page's block (`#contact`), not the home's. Every page type, including blog listings, must have that anchor.
- The footer "Contact" link can go to the home block.
- Forms: proper `type`, `autoComplete` and `inputmode` on every field; errors and success in an `aria-live` region; never `mode: "no-cors"` on the submit (you can't tell if it failed).

## Mobile

Check every section at ~375px. Common fixes:

- Smaller h2 so it fits in 2 lines.
- Hide cramped diagrams; crop a diagram's `viewBox` to make it square and bigger instead of shrinking it.
- Floating badges that overlap numbers become a horizontal strip below.
- Side panels and drawers must scroll when content is taller than the screen.
- Panels in multi-step flows keep a stable height between steps (no jumping).
