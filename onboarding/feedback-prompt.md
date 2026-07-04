# Onboarding Feedback — Retro Prompt

Paste this into your agent session **after** completing the Level-1
onboarding. It makes the agent that just ran your onboarding produce a
structured retro, so the onboarding materials can be improved.

---

You just onboarded me using `onboarding/level-1-build.md`. Now produce a
process retro so the maintainers can refine the onboarding. Rules:

- **Zero personal data.** No amounts, balances, rates, debts, names of my
  accounts, or anything identifying. Process observations only. If an
  example needs a number, use a placeholder like `$X`.
- Be specific and critical. "It went fine" is useless. Every issue should
  point at a file and, where possible, propose the exact wording change.

Write the retro to `cartridges/private/feedback-YYYY-MM-DD.md` (today's
date; this directory is gitignored) AND print it in full. Use exactly this
structure:

```markdown
# Onboarding Retro — YYYY-MM-DD

agent/tool: <which agent and model ran this>
mode: <estimate | evidence — did you interview only, or read documents?>
duration: <approx minutes, number of questions asked>

## What worked
- <bullet per observation>

## Friction points
- <each: what happened, which question/step, why it slowed things down>

## Coverage gaps
- <user info that had no home in the snapshot/rules schema>
- <schema fields the user couldn't answer or that felt irrelevant>

## Protocol ambiguities (agent's own confusion)
- <places where level-1-build.md, SPEC.md, or AGENTS.md were unclear,
  contradictory, or forced a judgment call — quote the ambiguous line>

## Output verification
- SPEC compliance of generated files: pass/fail + notes
- git check-ignore on private files: pass/fail
- Calendar-reminder step delivered: yes/no

## Proposed changes (ranked, most valuable first)
1. <file: exact change or new wording>
2. ...

## Overall: GREEN / YELLOW / RED
<one line: would you recommend this onboarding to a non-technical user
as-is?>
```
