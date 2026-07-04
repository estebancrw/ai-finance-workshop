# Cartridge Spec

A **cartridge** is your personal financial data, kept fully separate from the
engine. The engine is generic and public; the cartridge is yours and private.
Swap the cartridge and the same engine serves a different person — that
separation is the whole design.

## Format

A cartridge is a directory with exactly two files:

| File | What it holds | How often it changes |
|---|---|---|
| `snapshot.md` | Your **state**: income, spending, savings, debts, investments, insurance — with an `as_of` date | Monthly by default (engine flags it stale past 1 month); tighter cadence is your choice |
| `rules.md` | Your **knowledge**: targets, priorities, non-negotiables | Rarely (when you learn something about yourself) |

Why two files, not one: your balances change every month; your principles
don't. Separating them means the refresh ritual only touches `snapshot.md`,
and your rules accumulate slowly and deliberately.

## Required fields

### snapshot.md

- `as_of` date (the engine refuses stale data past 1 month)
- Monthly take-home income
- Fixed monthly costs (rent/mortgage, debt payments, insurance, subscriptions)
- Discretionary spend last month (a rough estimate is fine)
- Current savings (and where they sit)
- Active debts: name / balance / interest rate / minimum payment
- Investments: type / rough value (or "none")
- Insurance: what you have, what you don't

Optional (include when they apply — they change the answers):

- **Non-cash benefits**: employer-paid insurance, meal/grocery vouchers —
  they change your protection level and your effective spend
- **Equity-building payments**: mortgage / pre-construction installments —
  payments that build an asset; list separately from consumer debt and
  from consumption

### rules.md

- Emergency fund target (in months of expenses)
- Save / Spend / Invest split target (percentages)
- Debt priority rule (e.g., highest rate first)
- Insurance stance (what must be covered, especially if you have dependents)
- Personal non-negotiables (the rules generic advice always misses —
  e.g., "never carry a card balance past 60 days", "48-hour wait on any
  purchase over 5,000")

## Included cartridges

- `_template/` — blank cartridge. Copy it, fill it, plug it in.
- `private/` — **gitignored.** Put your real cartridge here; it never gets
  committed or published. This is where "pluggable" becomes real: the
  public repo carries the engine and mocked demo data, your machine
  carries your data. Statement files (PDFs/CSVs) go in
  `private/statements/YYYY-MM/` — same protection.

Demo personas (Alex: debt-heavy; Sam: debt-free, cash over-parked — both
fully mocked) live in `../workshop/demo-cartridges/`; they exist for the
workshop demos, not as part of anyone's setup.

## Precision note

Estimates are enough to start. The point of v1 is a good-enough snapshot to
run the pattern on — not reconciled bookkeeping. Precision improves at your
first monthly refresh, once you trust the tool.
