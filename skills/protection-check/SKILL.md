---
name: protection-check
description: Deep audit of "am I protected?" — emergency fund vs. target,
  insurance gaps including non-cash employer benefits, income-variability
  stress test, and a ranked gap list with costs. Use when the user asks
  about protection, safety net, emergency fund, insurance, or "what
  happens if I lose my income".
---

# Protection Check

Read `cartridges/private/snapshot.md` and `rules.md` first. This is the
deep-dive behind the weekly close's one-line verdict.

## Procedure

1. **Emergency fund, honestly counted.** Liquid savings only (cash,
   instant-access accounts; not investments, not equity-building
   payments). Months = liquid savings ÷ monthly obligations (fixed +
   realistic discretionary floor, not zero-spending fantasy). Show the
   division. Compare against the user's target from `rules.md`.
2. **Income stress test.** If income is variable (per snapshot): recompute
   runway at −20% income. If single-source salary: state the runway if it
   stops entirely — that's what the EF is for.
3. **Insurance audit.** Health, life (only matters with dependents —
   don't upsell it otherwise), disability/income protection (critical for
   freelancers; most forget it), car/home. **Count non-cash employer
   benefits** from the snapshot — employer-paid insurance changes this
   answer materially, and its loss is part of the job-loss scenario.
4. **Single-point-of-failure scan.** All savings in one institution? One
   card for everything? Income and employer benefits from the same
   employer (correlated loss)? Name what a single bad event takes out.

## Output

```
PROTECTION CHECK — <date>
Emergency fund:   X.X months vs target Y → verdict (show the math)
Income stress:    runway at −20% / at zero
Insurance:        covered | gap — per line: health / life / disability / other
Failure points:   <1-3 bullets>
VERDICT:          PROTECTED / PARTIAL / EXPOSED
Top gap:          <the one thing> — costs roughly $Z/month to close
```

## Guardrails

- Fiduciary rule applies hard here: name gap *types*, never insurance
  brands or products, unless explicitly asked to compare.
- No fear-selling: if the user is well protected, say so and stop —
  "you're fine" is a complete answer.
- Recommend a licensed professional for policy specifics; sizing the gap
  is our job, contracts are not.
