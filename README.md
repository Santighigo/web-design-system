# Web Design System

The rules, process and Claude Code skills behind a studio that ships websites clients actually like. This repo holds no brand: no palette, no logo, no copy. It's the system you run *any* brand through.

It started as a set of hard-won notes: dozens of rounds of annotated screenshots, reverted experiments, audits and copy passes on real client and studio sites. Every rule here exists because breaking it once produced something worse.

## What's inside

| Path | What it is |
|---|---|
| [`CLAUDE.md`](CLAUDE.md) | Drop-in agent rules. Copy it into a project root so Claude Code (or any coding agent) follows the system automatically. |
| [`docs/01-process.md`](docs/01-process.md) | The end-to-end workflow, from brief to deployed site. |
| [`docs/02-visual-rules.md`](docs/02-visual-rules.md) | Type, color, radius, shadow, background, theme. |
| [`docs/03-layout-and-components.md`](docs/03-layout-and-components.md) | Page structure, hero, nav, cards, tabs, CTAs, mobile. |
| [`docs/04-copy-rules.md`](docs/04-copy-rules.md) | Honest, plain, customer-language copy. No invented proof. |
| [`docs/05-motion.md`](docs/05-motion.md) | Animation rules that don't hurt performance or accessibility. |
| [`docs/06-visual-polish-checklist.md`](docs/06-visual-polish-checklist.md) | The checklist to run on every hand-built graphic. |
| [`docs/07-audit.md`](docs/07-audit.md) | How to audit a site: conversion, SEO, accessibility, benchmark. |
| [`docs/08-quality-gates.md`](docs/08-quality-gates.md) | What "done" means. |
| [`docs/09-collaboration.md`](docs/09-collaboration.md) | Branches, PRs, review docs, deploys, decision logs. |
| [`docs/10-references.md`](docs/10-references.md) | How to choose and use visual references. |
| [`templates/`](templates) | Project `CLAUDE.md`, design tokens, PR review doc, audit report, session handoff. |
| [`skills/`](skills) | Three Claude Code skills: build, audit, copy pass. |
| [`RECOMMENDED-SKILLS.md`](RECOMMENDED-SKILLS.md) | Third-party skills this system pairs well with, credited to their authors. |

## Quick start

### With Claude Code

1. Install the skills:
   ```bash
   cp -R skills/* ~/.claude/skills/
   ```
2. In your website project, copy the agent rules and the project template:
   ```bash
   cp CLAUDE.md /path/to/your-site/AGENTS.md
   cp templates/PROJECT-CLAUDE.md /path/to/your-site/CLAUDE.md
   ```
   Fill in the brand slots in `CLAUDE.md` (palette, fonts, references, decisions). Keep `AGENTS.md` as is; the project file imports it.
3. Ask Claude to build or review something. The `web-design-build`, `web-design-audit` and `web-copy-pass` skills trigger on their own.

### Without an agent

Read the docs in order. `01-process.md` is the spine; everything else is referenced from it.

## The ten rules, if you read nothing else

1. **Look at real references before you build.** Reading a description of a style is not the same as matching a rendered example.
2. **Two typefaces, maximum.** One sentence, one typeface. Never mix them mid-line.
3. **One primary color, one accent.** The accent is a single focal point per section, never a fill.
4. **Every corner the same radius.** Every hand-built card gets a soft ambient shadow.
5. **One primary CTA, same label everywhere.** Header, hero and every closing block say the exact same thing.
6. **Never invent proof.** No fake metrics, clients, testimonials or team members. Unverified numbers render as scope or not at all.
7. **Don't promise what you don't always do.** Cut the line before you ship a promise you might break.
8. **Speak the customer's words, not your stack.** Nobody hiring you cares which framework you used.
9. **Above-the-fold content never waits for an animation.** Every animation ends in a static, readable state and respects reduced motion.
10. **Decisions get written down so they aren't reopened.** Reverted experiments get logged too, with the reason.

## License

MIT. Use it, fork it, sell websites with it.
