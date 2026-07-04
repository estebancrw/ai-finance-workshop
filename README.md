# ai-finance-workshop

Build a **personal finance knowledge base** your AI actually reads — so it
answers with *your* numbers and enforces *your* rules, instead of giving
advice that would fit anyone.

Born as a hands-on workshop for friends; usable by anyone, self-serve, in
~30 minutes, with a free ChatGPT or Claude account.

## The idea

```
   ENGINE  (shared, generic, public)      CARTRIDGE  (yours, private)
   ──────────────────────────────         ─────────────────────────────
   project-instructions.md          +     snapshot.md  (your numbers)
   fiduciary rule · read-KB-first         rules.md     (your non-negotiables)
   staleness check · draft-only
                     │                                │
                     └───────────────┬────────────────┘
                                     ▼
                     A saved Project/Gem that answers:
                     "Where does my next peso go?"
                     "Am I protected?"
                     "Where can I cut?"
                     — grounded in YOUR data, every time.
```

Same engine, different cartridge, different (correct) advice. See it work:
the two demo personas in
[`workshop/demo-cartridges/`](workshop/demo-cartridges/) give **opposite
answers to the same question** — that's the point.

## Quickstart (30 minutes, no workshop needed)

1. **Easiest:** paste [`onboarding/level-1-build.md`](onboarding/level-1-build.md)
   into a fresh chat — the AI interviews you and writes your cartridge for
   you. (Manual alternative: copy
   [`cartridges/_template/`](cartridges/_template/) and fill it yourself.)
2. Follow the setup guide for your tool:
   [ChatGPT](adapters/chatgpt-project.md) ·
   [Claude](adapters/claude-project.md) ·
   power tier: [Claude Code](adapters/claude-code.md) ·
   [Codex CLI](adapters/codex.md)
3. Ask it a real money question you're facing this week.
4. Put a monthly 15-minute "refresh" event in your calendar. That habit is
   the actual system — see [`levels.md`](levels.md).

**Privacy:** your real cartridge goes in `cartridges/private/` — gitignored,
never committed. The repo stays generic; your data stays yours.

## Repo map

| Path | What it is |
|---|---|
| [`engine/`](engine/) | The tool-agnostic instructions (no personal data) |
| [`cartridges/`](cartridges/) | Spec, blank template, and your gitignored `private/` cartridge + statements |
| [`skills/`](skills/) | Agent procedures: statement-ingest (incl. password-protected PDFs), snapshot-refresh (weekly close), debt-plan, protection-check |
| [`adapters/`](adapters/) | Per-tool setup guides |
| [`onboarding/`](onboarding/) | AI-guided interviews that build your cartridge for you |
| [`levels.md`](levels.md) | The 5 levels of personal AI (0 stateless → 4 agentic) |
| [`workshop/`](workshop/) | Run this as a workshop: facilitator script, demo runbook, worksheets, handout |

## The levels, in one line each

0. **Stateless chat** — generic advice, from scratch, every time
1. **Snapshot KB** — AI that knows your numbers and rules *(quickstart gets you here)*
2. **Living KB** — AI that knows your history (the monthly refresh)
3. **Connected KB** — AI that stays current via integrations
4. **Agentic** — AI that acts, inside human approval gates

Full ladder with upgrade triggers and the guardrail story: [`levels.md`](levels.md).

## Using a coding agent?

Clone the repo, open Claude Code / Codex / any CLI agent in the root, and
say **"onboard me."** `AGENTS.md` instructs the agent to interview you,
write your real cartridge into the gitignored `cartridges/private/`, and
then act as your finance copilot on demand — the repo installs itself.

## Disclaimer

Educational material, not financial advice. The engine explicitly instructs
the AI to say the same and to defer to professionals where it matters.

## License

MIT
