# Onboarding — Level 1: Build Your Cartridge

An AI-guided interview that builds your cartridge for you. Instead of
filling worksheets, you answer questions one at a time and the AI emits
your two files, ready to use.

## Two ways to run it

**A — Consumer (ChatGPT / Claude / Gemini, no coding):** copy everything
below the line into a fresh chat. Answer the questions. At the end, copy
the two files it produces into your Project (see `../adapters/`).

**B — Coding agent (Claude Code / Codex / any CLI agent, from this repo):**
open your agent in the repo root and say: *"Onboard me — run
`onboarding/level-1-build.md`."* The agent runs the same interview and
writes the results into `cartridges/private/` directly (gitignored — your
data never leaves your machine via git).

---

You are onboarding me onto my personal finance knowledge base. Your job is
to interview me, then produce my two cartridge files. Follow this protocol
exactly:

## Interview protocol

- **Evidence first — before any estimate questions, ask me for
  statements.** Bank and card statements answer the hard questions (loan
  balances, interest rates, per-account balances) far better than my
  memory. Two ways I can provide them:
  - **Upload**: if we're in a chat app, ask me to upload my latest
    statements (PDF/image/CSV) right now.
  - **Document access**: if you are an agent with tools (Drive, email,
    local files), offer to fetch them yourself, confirming each figure
    with me.
  Only if I have no statements available, fall back to **estimate mode**:
  interview only. If you are an agent working inside this repo, follow
  `skills/statement-ingest/SKILL.md` for acquisition, password-protected
  PDFs, storage location, and extraction.
- **Freshness window:** use the running month or the month before —
  that's the ideal. Hard cap: nothing older than 3 months; refuse older
  documents. If the freshest statement is 2–3 months old, use it but say
  so, and set `as_of` to the statement cut date — not today — so the
  staleness check stays honest.
- **Evidence beats estimates — always.** Humans estimate; statements
  record. If my stated number and a statement disagree, show me the
  discrepancy, then **use the statement figure**. Only override a
  statement if I give a concrete reason (e.g., a payment made after the
  cut date), and record that override as a note in the snapshot.
- Ask **one question at a time**. Wait for my answer before the next.
- Estimates are fine — say so when I hesitate. This is a snapshot, not
  bookkeeping.
- **Privacy first — state this before question 1:** I should never give
  you account numbers, card numbers, or credentials. Balances, rates, and
  dates only. I may round any number I'm not comfortable sharing.
- If an answer seems inconsistent (e.g., spending exceeds income with no
  debt growth), point it out gently and ask once.

## Questions to cover (adapt wording, keep coverage)

Part 1 — Snapshot (my state):
1. Monthly take-home income — the amount that actually lands in my
   account after tax and any payroll deductions. If I only know my gross,
   record both. (And: is it stable or variable?)
2. Fixed monthly costs — walk me through rent/mortgage, debt payments,
   insurance, utilities, subscriptions (prompt me for subscriptions I
   forgot: streaming, gym, apps, cloud storage). Two separations to make
   explicitly: (a) if I run a business or side venture, ask which
   recurring charges are business expenses and **exclude them** from the
   personal snapshot; (b) if a recurring payment builds an asset
   (mortgage, pre-construction/preventa installments), record it under
   **Equity-building payments**, not consumer debt or expense
3. Discretionary spend last month — groceries, restaurants/delivery,
   transport, and a rough "misc" figure. Then ask: "what's actually
   *inside* your misc?" and itemize what I can recall
4. Current savings, and where they sit (earning what, roughly?)
5. Debts — for each: name, balance, annual rate, minimum payment
6. Investments — type and rough value, or none
7. Insurance — health, life, car/home; do I have dependents? Also ask
   about **non-cash employer benefits** (employer-paid insurance,
   meal/grocery vouchers) — they change both protection and effective
   spend

Part 2 — Rules (my knowledge):
8. Emergency fund target in months (suggest 3–6; 6+ if my income is
   variable — but it's my call)
9. My save/spend/invest split target, as percentages
10. My debt priority (suggest highest-rate-first as default; my call)
11. My non-negotiables — offer this menu and ask which are true for me,
    plus any of my own:
    - Never carry a credit card balance past N days
    - Never invest before the emergency fund hits target
    - Purchases over $X wait 48 hours
    - Never invest in anything I can't explain in two sentences
    - No lifestyle inflation on a good month
    - Life insurance non-negotiable while I have dependents

## Output

When the interview is complete, produce **two complete markdown files** in
exactly this structure — `snapshot.md` first, then `rules.md`:

- `snapshot.md`: title with my name, `as_of:` today's date, `currency:`,
  then sections: Income, Fixed monthly costs (itemized, with total),
  Discretionary spend (itemized, with total), Savings, Debts (table:
  name/balance/rate/minimum), Investments, Insurance — plus, when
  relevant: Non-cash benefits and Equity-building payments.
- `rules.md`: title with my name, then sections: Targets (emergency fund,
  split), Priorities (numbered, in order), Non-negotiables (bulleted).

Then tell me my next step:
- If we're in a chat app: "Copy these into your Project as two files —
  setup guide: adapters/ in the repo."
- If you're a coding agent in this repo: write the files to
  `cartridges/private/snapshot.md` and `cartridges/private/rules.md`,
  confirm they are gitignored (`git check-ignore`), and tell me to load
  the engine + my cartridge into my AI tool of choice.

Finally, remind me to put a recurring 15-minute "Money KB refresh" event
in my calendar. **Monthly is the default** (the engine treats numbers
older than a month as stale); weekly is fine if my balances move a lot —
my call. If you are an agent with calendar access, you may create the
event after my explicit confirmation — onboarding setup is exempt from
the engine's draft-never-execute rule, which governs copilot-mode
financial actions.
