# AGENTS.md — ai-finance-workshop

Context for AI coding agents (Claude Code, Codex, Pi, OpenCode, etc.)
working in this repo.

## What this repo is

A personal finance knowledge-base kit: a tool-agnostic **engine**
(`engine/project-instructions.md`) plus pluggable **cartridges**
(`cartridges/` — each is `snapshot.md` + `rules.md`, spec in
`cartridges/SPEC.md`). Includes workshop materials (`workshop/`), per-tool
setup guides (`adapters/`), a maturity ladder (`levels.md`), and AI-guided
onboarding prompts (`onboarding/`).

## Hard rules

1. **Never commit anything inside `cartridges/private/`** except its
   README. It is gitignored; it holds the user's real financial data.
   Never weaken the `.gitignore`, never `git add -f` files from there,
   never paste its contents into commits, issues, or PRs.
2. **Public cartridges contain mocked data only.** `alex/` and `sam/` are
   fictional personas. Any new committed cartridge must be fictional and
   labeled as such.
3. The engine must stay **generic** — no personal data, no
   currency/locale assumptions beyond what a cartridge provides.

## Agent tasks this repo supports

### "Onboard me" — build the user's cartridge

Run the interview in `onboarding/level-1-build.md` (one question at a
time). **Capability branch:** if you have document access (Drive, email,
files), offer evidence mode — populate figures from the latest statements
(≤1 month old), confirming each with the user — otherwise interview for
estimates. Write results to `cartridges/private/snapshot.md` and
`cartridges/private/rules.md`. Verify with `git check-ignore
cartridges/private/snapshot.md` before finishing.

Boundary note: creating the user's refresh calendar reminder (after
explicit confirmation) is permitted — the engine's draft-never-execute
rule governs copilot-mode financial actions, not onboarding setup.

### Act as the finance copilot

If `cartridges/private/` contains a filled cartridge and the user asks a
money question: read `engine/project-instructions.md` and adopt it as your
operating rules, read the private cartridge, then answer. All engine rules
apply — including fiduciary behavior, rule-enforcement against the user,
show-your-math, staleness check on `as_of`, and draft-never-execute.

### Refresh the snapshot (Level 2)

Read the existing private `snapshot.md`, ask the user only what changed,
update numbers, bump `as_of`. Suggest archiving the previous snapshot
(e.g., `cartridges/private/history/YYYY-MM-snapshot.md`) so trend
questions have data.

## Conventions

- Markdown everywhere; keep files small and single-purpose.
- Follow `cartridges/SPEC.md` exactly when generating cartridges.
- Conventional commits (feat/fix/docs/chore).
