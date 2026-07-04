# Demo Runbook

Rehearse all three before the session. LLM outputs vary — the fallback
lines below recover every known failure mode.

## Prep

- Project 1: `Alex — Money KB` → engine instructions + `cartridges/alex/`
- Project 2: `Sam — Money KB` → engine instructions + `cartridges/sam/`
- Plain chat (no project) open in a separate tab for Demo A

## Demo A — the misc reveal (plain chat, ~3 min)

Prompt 1:

> Here's roughly what I spent last month: rent 12,000, groceries 4,200,
> restaurants 3,100, subscriptions 1,600, gas 1,800, misc 3,600. What's
> actually eating my money?

Expect: generic ranking ("rent is your biggest expense").

Prompt 2:

> Actually, let me break down "misc": Uber Eats 1,400, two impulse Amazon
> orders 1,100, a subscription renewal I forgot about 600, ATM fees 500.
> Now what do you see?

Expect: delivery + impulse reframing. The point on screen: *the category
you don't itemize is where the truth hides.*

## Demo B — the bonus verdict (Alex project, ~3 min)

Prompt:

> I just got a $15,000 bonus. What should I do with it?

Expected shape: cites the 45% card ($18,000) and the EF gap (1.4 vs 3
months); concrete split (e.g., most/all toward the card per Alex's
highest-rate-first rule); one-line verdict.

Failure modes:

- Generic answer → reply `Check my KB first — apply my rules.`
- Suggests investing → reply `Does that comply with my priority order in
  rules.md?` (the model self-corrects; this failure is actually a good
  live moment — the rules catch the model)

## Demo C — the contrast (Sam project, ~2 min)

Identical prompt:

> I just got a $15,000 bonus. What should I do with it?

Expected shape: no debt; EF already ~12 months vs 6-month target →
over-parked cash; direct surplus toward investing per Sam's split, likely
flags the disability-insurance gap.

The line that lands the whole workshop:

> "Same engine. Same question. Opposite advice. The value is in the
> cartridge."

## If a demo collapses live

Worst case, all three demos have a scripted expected-output above — narrate
from the runbook ("here's what it said in rehearsal") and move on. Never
debug live for more than 60 seconds; the build block matters more.
