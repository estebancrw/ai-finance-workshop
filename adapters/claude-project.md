# Adapter — Claude (Projects)

## Setup (~5 minutes)

1. Go to claude.ai → **Projects** → **Create project** → name it
   `My Money KB`. (Projects require a paid plan.)
2. Open the project → **Set project instructions** → paste the full
   contents of `engine/project-instructions.md` (everything below the
   `---` line).
3. Add your cartridge under **Project knowledge**: upload (or paste as
   text content) your filled `snapshot.md` and `rules.md`.
4. Test with: `Where does my next peso go?` — the answer must cite *your*
   numbers and *your* rules. If it's generic, reply: `Check my KB first.`

## Free-tier fallback

No Projects on free tier: start a normal chat with one setup message —
`You are my finance copilot. Follow these instructions:` + engine text +
both cartridge files. Bookmark the conversation and keep using that same
chat. Less durable than a Project, same pattern.

## Refresh ritual (Level 2)

Monthly: update `snapshot.md` in Project knowledge, bump `as_of`. Keep old
snapshots — that's your history for trend questions.

## Power-user note

If you use Claude Code / Codex / a CLI agent: skip the web UI entirely —
keep your cartridge as local files in a private directory and point the
agent at them. Same engine text works as the system prompt / AGENTS.md.
