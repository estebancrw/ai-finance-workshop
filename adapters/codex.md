# Adapter — Codex CLI (power tier)

Same power tier as Claude Code, for people with a ChatGPT subscription:
cartridge as real files, statement ingestion, skills, weekly refresh.

## Install (~5 min)

1. You need a ChatGPT subscription (Plus or higher) — you log in with
   your existing ChatGPT account.
2. Install: `npm install -g @openai/codex`
   (no Node? macOS: `brew install node` first)
3. Clone this repo and enter it:
   ```
   git clone https://github.com/estebancrw/ai-finance-workshop.git
   cd ai-finance-workshop
   ```
4. Run `codex`, log in when prompted.

## Use

Codex reads `AGENTS.md` automatically — it knows the repo rules and where
the skills live (`skills/`).

- First time: say **"onboard me"** — interview or statement-based, writes
  your private cartridge.
- Weekly: say **"weekly close"** — 3 questions, 5 minutes, one report.
- Monthly: say **"full refresh"** with last month's statements handy.
- Anytime: money questions, answered from your KB.

## Privacy notes

- Your data lives in `cartridges/private/` on YOUR machine — gitignored,
  never uploaded to GitHub.
- Conversation content goes to OpenAI like any ChatGPT chat. Same
  trade-off as the web app, no worse.
- Codex runs sandboxed and asks before touching things outside the repo —
  read what it asks.
