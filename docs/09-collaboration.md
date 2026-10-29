# 09 — Collaboration

How to work on a site with an agent and with other people without breaking production or redoing work.

## Branches and PRs

- Never commit to `main` or push to production without explicit approval.
- One feature per branch, one PR per feature. Small and reviewable beats one giant PR.
- When features depend on each other, stack them: each branch is based on the previous one. Merge in order; the host retargets the next PR as each one lands.
- Squash reverted experiments out of the history before opening the PR.
- Conventional commits, in English.
- Auto-merge off. Someone reads every PR.
- Don't push to someone else's repo or open PRs there without asking the owner first.

## The PR review doc

Every PR gets a short, plain-language doc for a non-technical reviewer ([`templates/PR-REVIEW.md`](../templates/PR-REVIEW.md)):

- **What changed**, in terms of what you see on the page.
- **Why.**
- **Where numbers come from**, if any.
- **What was not touched.**
- **How to review it** (which page in the preview, which files).
- **Updates** appended per session, never rewriting history.
- **Verified**, tiered as in [08-quality-gates.md](08-quality-gates.md).

## Deploys

- Deploy only when the owner says "deploy". Iterate locally on the dev preview otherwise.
- Keep a separate preview site for proposals so production stays untouched.
- Say when the preview is stale relative to local work.

## Memory: the decisions log

The project `CLAUDE.md` is the source of truth that every new session reads first. It holds:

- Positioning (who buys, what they search, the one action).
- Stack and its gotchas (things that already broke once).
- Tokens summary (palette, fonts).
- **Decisions, numbered and dated**, including the reason. "Light mode locked: dark felt cold to small-business buyers."
- **Tried and rejected**, with the reason. "WebGL gradient hero: tried, owner reverted to the plain background. Don't reintroduce unless asked."
- Placeholders still pending (so they never ship by accident).
- Existing components to reuse, with their props.

Update it in the same session a decision is made, not "later".

## Session handoff

When a session gets long or you need to switch machines, write a handoff ([`templates/SESSION-HANDOFF.md`](../templates/SESSION-HANDOFF.md)): coordinates, branch stack with tips, what's committed vs not, what's deployed vs local, environment gotchas, open items, and what needs asking before doing.

## Working with a non-technical owner

- Explain changes as what they'll see, not as code.
- Ask before anything outward-facing (push, PR, deploy, sending anything).
- Don't add things they didn't ask for: extra guides, extra components, extra sections. Keep the system small enough that they understand every part of it.
- When they reject something, ask what they liked about the previous version before trying a third option.
