@AGENTS.md

# <Project name> — project rules

Everything a new session needs to keep building without reopening decisions. Read before writing code. Update in the same session a decision is made.

## 1. Positioning

- **Who buys:** <typical customer, digital maturity, who decides>
- **What they search for:** <exact task + industry phrases>
- **What every competitor says (don't lead with it):** <phrases>
- **The one action:** <book a call / start the quiz / message us>
- **Register:** <formal-simple | casual>, <we | I>
- **Real proof available:** <cases with permission, sourced numbers>
- **Proof we don't have yet:** <so nobody invents it>

## 2. Stack

<framework, styling, components, motion, content, tests, hosting>

Gotchas already hit (don't repeat):

- <e.g. component library uses `render` prop, not `asChild`>

## 3. Tokens

Source of truth: `<path to globals.css>`. No ad-hoc values in components.

| Token | Value | Use |
|---|---|---|
| primary | | CTAs, links, active states |
| primary-deep / primary-mid | | supporting tones |
| accent | | one focal point per section |
| ink (dark ground) | | dark surfaces |
| foreground | | text |
| background | | page |
| muted-foreground | | secondary text (must pass AA) |
| hairline | | borders |
| radius | | everything |

## 4. Typography

- Sans: <font> — everything.
- Accent: <font or none> — whole standalone lines only.
- No other fonts. No mono.

## 5. References

| Site | The one idea we take |
|---|---|
| | |

## 6. Decisions (don't reopen)

1. <YYYY-MM-DD> <decision>. **Why:** <reason>.

## 7. Tried and rejected

1. <YYYY-MM-DD> <experiment>. **Why reverted:** <reason>. Don't reintroduce unless asked.

## 8. Components to reuse

- `<Component>` (`path`) — props: <…>

## 9. Placeholders pending (must not ship)

- [ ] <real phone number>
- [ ] <real email>
- [ ] <form webhook env var in production>

## 10. Working rules for this project

- Deploy only on request.
- Never push to `main`/production without approval.
- Quality gates: <commands>.
