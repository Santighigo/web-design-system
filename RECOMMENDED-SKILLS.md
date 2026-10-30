# Recommended third-party skills

This system was used alongside these community Claude Code skills. They aren't bundled here; get them from their authors so you have the latest version and the right license.

| Skill | What it adds | Author / where to find it |
|---|---|---|
| `design-taste-frontend` (and siblings: `high-end-visual-design`, `minimalist-ui`, `redesign-existing-projects`, `industrial-brutalist-ui`, `gpt-taste`, `stitch-design-taste`, `image-to-code`, `full-output-enforcement`) | Anti-"AI slop" frontend rules: brief inference, design dials, layout discipline, pre-flight checks. Use before redesigning large sections. | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) |
| `impeccable` | UI polish: spacing, hierarchy, micro-details, critique and audit commands. | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) |
| `ui-ux-pro-max` | Searchable database of styles, palettes, font pairings and UX guidelines. | Search GitHub for "ui-ux-pro-max-skill" |
| `stop-slop` | Removes AI writing patterns from prose. Good final pass on copy. | Hardik Pandya (hvpandya.com) |
| `design-system`, `ui-styling` | Token architecture and shadcn/Tailwind styling references. | ClaudeKit (MIT) |

How they fit with this repo:

- The **taste** skills and **impeccable** decide *how good* a section looks. This repo decides *what is allowed* (fonts, accent use, honesty of proof, CTA consistency) and *how the work flows* (references, tokens, review loop, gates, PRs).
- When a third-party skill and this system disagree, the project `CLAUDE.md` wins, then this repo's `CLAUDE.md`, then the third-party skill.
