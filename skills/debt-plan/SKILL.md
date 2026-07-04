---
name: debt-plan
description: Build or update the user's debt payoff plan — ordering per
  their rules (default avalanche), payoff timeline with shown math, total
  interest cost, and extra-payment / lump-sum scenarios. Use when the user
  asks about paying off debt, loan priorities, "what if I pay X more", or
  windfall allocation while debts exist.
---

# Debt Plan

Read `cartridges/private/snapshot.md` (debts table) and `rules.md` (debt
priority, EF floor) before anything. If a balance or rate is missing, ask
— never assume.

## Procedure

1. **Order the debts** by the user's own priority rule. Default:
   avalanche (highest annual rate first). If their rules say otherwise
   (e.g., snowball for motivation), follow their rule and don't argue —
   note the cost difference once, neutrally.
2. **Compute the baseline**: minimum-payments-only — months to payoff and
   total interest paid.
3. **Compute the plan**: all available surplus (income − fixed −
   discretionary, per snapshot) to the top-priority debt, minimums on the
   rest; roll payments as each debt clears. Output per debt: payoff date,
   interest paid.
4. **Show the math** — non-negotiable. State the monthly-rate conversion
   (annual rate / 12), the surplus figure used and where it came from,
   and a compact month-by-month table for at least the first debt. LLM
   arithmetic drifts: compute step by step, and tell the user to
   spot-check one row.
5. **Scenarios on request**: "+$X/month" and "lump sum of $Y" → new
   payoff dates and interest saved vs. the plan.

## Guardrails

- **Never route the emergency fund below the user's floor** into debt
  payments — even if mathematically optimal. The floor is a rule.
- If their rules gate investing behind debt payoff, restate the gate
  whenever investment questions come up mid-plan.
- Interest saved is the headline number — people persist for "this saves
  me $X and ends N months sooner", not for schedules.
- End with: the single next payment (amount, target debt, date) — a plan
  is one action, repeated.
