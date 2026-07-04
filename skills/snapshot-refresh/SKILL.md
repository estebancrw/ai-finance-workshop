---
name: snapshot-refresh
description: Keep the user's money KB alive — a 5-minute weekly close
  (three questions, no documents) or a monthly full refresh (statements
  via statement-ingest). Diffs, updates snapshot.md, bumps as_of, archives
  history, and ends with a one-screen report. Use when the user says
  "refresh", "weekly close", "update my numbers", or their snapshot is
  stale.
---

# Snapshot Refresh

The KB's value is the refresh habit, not the build. Two modes — pick by
asking one question: **"Quick weekly close, or full refresh with
statements?"** (If `as_of` is >1 month old, recommend the full refresh.)

## Mode A — Weekly close (~5 minutes, no documents)

Three questions, nothing more:

1. What's your main account balance right now? (roughly)
2. Any payment due in the next 14 days you haven't confirmed?
3. Did you spend anything this week you regret — or that breaks one of
   your rules?

Then update only what changed in `cartridges/private/snapshot.md` (do NOT
bump `as_of` for rough weekly numbers — `as_of` reflects evidence-grade
data only; add a `last_weekly_close:` date line instead).

## Mode B — Full refresh (monthly, evidence-grade)

1. Archive the current snapshot to
   `cartridges/private/statements/history/YYYY-MM-snapshot.md` first.
2. Run `skills/statement-ingest/SKILL.md` for the new month's statements.
3. Diff old vs. new: balances, debt levels, category drift. Ask the user
   only about what changed or looks anomalous — never re-interview from
   scratch.
4. Update `snapshot.md`, set `as_of` to the newest statement cut date.

## The close report (both modes, always)

End with one screen, no more:

```
MONEY CLOSE — <date>
Changed since last time:  <2-3 bullets, or "nothing material">
Protected:                <EF months vs target> → on track / needs attention / at risk
Debt:                     <balance vs last close, vs payoff plan> (skip if debt-free)
Rule check:               <any rule violated or nearly violated this period>
One thing to do:          <single highest-leverage action before next close>
```

For trend lines ("better off than last month?"), read the archives in
`statements/history/`.

## Hard rules

- Never fabricate a number the user didn't give or a statement didn't
  show — leave stale values in place and flag them instead.
- Everything stays in `cartridges/private/`.
- If the user has skipped 2+ scheduled closes, say so plainly and ask if
  the cadence should change — a dying habit is a finding, not a failure.
