# 01 — The process

The order matters. Most bad sites skip step 1 or step 6.

## 1. Positioning before pixels

Before any design, write down in one page:

- **Who buys.** The typical customer, how digitally mature they are, who decides.
- **What they search for.** The exact words they type: the task and the industry ("booking site for a dental clinic"), not your category ("custom digital solutions").
- **What competitors say.** Collect the hero lines of 5–10 competitors. Whatever they all say is what you must *not* lead with.
- **The one action.** What the visitor should do (book a call, start a quiz, message on WhatsApp). There is exactly one.
- **Real proof you have.** Cases, numbers with a source, client permission to use names. Write down what you *don't* have too.

This page goes into the project `CLAUDE.md` so every session starts from it.

## 2. References

Pick 3–5 real sites. For each, name the single idea you're taking from it (the floating glass nav, the centered hero, the tabs-connected-to-panel pattern). See [10-references.md](10-references.md).

Open them and look. Screenshot the parts you're borrowing and keep them in the project.

## 3. Tokens first

Define the design tokens before any component: colors, type scale, spacing, radius, shadow, easing. Use [`templates/tokens.css`](../templates/tokens.css). Components only ever reference tokens.

## 4. Build section by section

Typical page order for a service business:

```
Hero → Services → Industries / use cases → Cases → Process → FAQ → Contact
```

Build one section, show it, get feedback, move on. Don't build the whole page and then ask.

For each section ask: does it say something no other section says? If not, cut it. Sections that repeat another (a services × industries matrix when both already have their own sections) get deleted.

## 5. The annotated-screenshot loop

The fastest feedback loop we've found:

1. Owner screenshots the live preview and marks it up (circles, arrows, short notes).
2. Agent applies every mark, desktop and mobile.
3. Agent screenshots the result and compares it side by side with the annotation.
4. Repeat.

Rules for the loop:

- Change only what was marked. If a change seems to need a different background or graphic, keep the original and solve it another way, or ask.
- When the owner says "revert", revert completely and log the experiment in the decisions log so it doesn't come back.

## 6. The copy pass

A separate session, only text, page by page. See [04-copy-rules.md](04-copy-rules.md) and the `web-copy-pass` skill. Typical findings:

- The same CTA labeled three different ways.
- Promises the business doesn't keep every time.
- Stack names nobody cares about.
- Truncated card text.
- Headings with stale counts.

## 7. Audit

Run [07-audit.md](07-audit.md) on the preview before launch: conversion paths actually work, SEO basics exist, accessibility passes, and the site beats competitors on the axes that matter.

The most common finding: a beautiful site whose contact form and phone number are placeholders in production.

## 8. Gates, PR, deploy

Run [08-quality-gates.md](08-quality-gates.md). Open one PR per feature with a review doc ([09-collaboration.md](09-collaboration.md)). Deploy when the owner asks.

## 9. Keep the log

Every decision and every reverted experiment goes into the project `CLAUDE.md` with a date and a reason. This is what stops a new session from "improving" something the owner already rejected.
