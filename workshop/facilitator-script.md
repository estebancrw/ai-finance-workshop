# Facilitator Script — 12:00–13:45

Audience: 3–4 friends, daily AI users, non-engineers. Hands-on. One goal:
**everyone leaves with a working Level-1 Money KB in their own account,
tested on a real question.**

Pre-session checklist (do before 12:00):

- [ ] Two Projects created in your demo tool: `Alex — Money KB`,
      `Sam — Money KB` (engine + respective cartridge loaded)
- [ ] Both demos rehearsed at least once (see `demo-runbook.md`)
- [ ] Everyone told to bring a laptop + a ChatGPT or Claude login
- [ ] Worksheets open/printed (`worksheets/`)

---

## 12:00–12:15 — Framing + live demos

Open with the plateau, not the tech:

> "You all use AI daily. And I'd bet every session starts from zero — you
> re-explain your situation, get advice that would fit anyone, close the
> tab. Today we fix that permanently, using your money as the subject."

**Demo A — the misc reveal** (plain chat, no KB): paste Alex-style spending,
ask what's eating the money, then pull the thread on "misc". Landing line:

> "Everyone here can tell me their rent. Nobody can tell me what's in their
> 'misc' — until they look."

**Demo B — the bonus verdict** (Alex project): `I just got a $15,000 bonus.
What should I do with it?` → concrete split citing Alex's card rate and EF
gap. Landing line:

> "Same model as before. The difference is it knows Alex's numbers and
> Alex's rules. That's the entire trick — and OpenAI just built their whole
> personal-finance product on this exact idea. US-only, $200/month. We're
> building it ourselves, today, free."

**Demo C — the contrast** (Sam project): identical bonus question →
opposite answer (no debt, over-parked cash, invest per Sam's rules).
Landing line:

> "Same engine, same question, opposite advice. The value isn't in the AI —
> it's in the cartridge. Now let's build yours."

## 12:15–12:25 — Name the pattern

Whiteboard/paper: **ENGINE (shared, generic) + CARTRIDGE (yours, private)**.
Cartridge = two files: `snapshot.md` (your numbers, changes monthly) +
`rules.md` (your non-negotiables, changes rarely). Show the levels ladder
(`levels.md`) for 2 minutes: "you're at 0, you leave at 1, the ritual takes
you to 2, I live around 3 — I'll show you at the end."

## 12:25–12:35 — Build their cartridge (AI-guided interview)

Primary path: everyone pastes `onboarding/level-1-build.md` into a fresh
chat — the AI interviews them one question at a time and emits their two
cartridge files. (Fallback if someone's tool misbehaves: the manual
worksheets in `worksheets/`.) Say explicitly:

> "Estimates are fine — this is a snapshot, not bookkeeping. And round or
> abstract any number you don't want to share out loud; the pattern works
> identically. Nobody has to show anyone their sheet."

Walk the Alex example first so they calibrate. While they answer the
interview, circulate: the most common failure is thin `rules` — prompt
them: "what money rule do you already enforce on yourself that no app
knows about?" Note the interview may run past 12:35 into the build block
— fine, it produces the files they need for step 3 anyway.

## 12:35–13:05 — Build (the core block)

Each person, in their own account (route by tool — `adapters/`):

1. Create Project/Gem named `My Money KB`
2. Paste the engine into instructions
3. Add their two cartridge files (upload or paste)
4. **Test on a real question they're actually facing this week** — a
   purchase they're weighing, a bonus, "should I pay X faster or save"

You float. Unblock fast; tune rules files live when answers come back
generic ("Check my KB first" usually fixes it).

## 13:05–13:20 — Share-out (voluntary detail)

Each person shows one before/after: the same real question in plain chat
vs. their KB project. Ask each: "what did it catch that generic advice
missed?" — that answer, in their own words, is the workshop's proof.

## 13:20–13:30 — Level 3 teaser (demo only, not hands-on)

Show your own setup for 60–90 seconds — **structure only, redacted, never
real balances**: the file tree, the rules file shape, the monthly cadence.
Landing line:

> "This is the same two files you just made, plus 18 months of habit.
> Nothing here is smarter than what you built — it's just older."

## 13:30–13:45 — Guardrails + the close

Tell the Air Canada story (bot invented a refund policy; tribunal made the
airline honor it). Land the rule:

> "AI drafts, you execute. Anything irreversible — money moved, message
> sent, commitment made — a human approves. Keep approving everything until
> it's wrong less than 1 time in 5, then loosen one action type at a time."

**The close — do not skip:** everyone takes out their phone and creates a
calendar event *now*, before leaving the table: **"Money KB refresh — 15
min"**, next month, recurring monthly. Say why:

> "The build was today. The value is the refresh. This event is the
> difference between a cool afternoon and a system you'll still be using
> next year."

Send them the repo link as they leave.
