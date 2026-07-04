# Adapter — Claude Code (CLI, power tier)

The CLI path unlocks what the web app can't: your cartridge as real files,
statement ingestion (including password-protected PDFs), skills, and a
weekly refresh that reads your actual documents. ~10 minutes to set up.

## Install (~5 min)

1. You need a Claude subscription (Pro or higher) — you log in with the
   same account you already use at claude.ai.
2. Install: `npm install -g @anthropic-ai/claude-code`
   (no Node? macOS: `brew install node` first. Or use the native
   installer: `curl -fsSL https://claude.ai/install.sh | bash`)
3. Clone this repo and enter it:
   ```
   git clone https://github.com/estebancrw/ai-finance-workshop.git
   cd ai-finance-workshop
   ```
4. Run `claude`, log in when prompted.

## Use

- First time: say **"onboard me"** — it interviews you (or reads your
  statements if you provide them) and writes your private cartridge.
- Weekly: say **"weekly close"** — 3 questions, 5 minutes, one report.
- Monthly: say **"full refresh"** and have last month's statements
  downloaded (drop them anywhere; it will store them correctly).
- Anytime: ask money questions — "am I protected?", "what's my debt
  plan?", "can I afford X?" It reads your KB before answering.

Skills auto-load from `.claude/skills/`; repo rules from `CLAUDE.md`.

## Privacy notes

- Your data lives in `cartridges/private/` on YOUR machine — gitignored,
  never uploaded to GitHub.
- Conversation content (including numbers you discuss) goes to Anthropic
  like any Claude chat. Same trade-off as the web app, no worse.
- The agent asks permission before running commands — read what it asks.
