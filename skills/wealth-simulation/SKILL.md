---
name: wealth-simulation
description: Use when the user asks whether their savings, income and spending plan will reach a financial goal, when they can retire, how likely they are to run out of money, or wants a Monte Carlo projection of household net worth. Guides gathering inputs, calling the WealthStoryLine run_simulation tool and explaining the result.
---

# Household wealth simulation with WealthStoryLine

## When to use
The user wants a probabilistic answer about their household finances: "Can I retire at 60?", "Will I have 10 million in 20 years?", "What happens if I keep spending like this?". Use the `run_simulation` tool rather than estimating by hand.

## Gather inputs (ask only for what is missing)
1. Age and country (TW, JP, US, CN or CA). Amounts are in that country's currency, full units.
2. Savings / liquid assets today.
3. Annual household income, and planned retirement age. Pension or annuity after retirement if any.
4. Annual living expenses.
5. Share of savings that is invested, and the expected return if the user knows it.
6. One general loan if relevant (remaining balance, total and paid monthly payments, interest rate). Mortgages and real estate are not in the free plan.
7. The goal: a target net worth by a certain year.

If the user does not know a value, leave it out; the tool uses sensible defaults and reports them in `input_warnings`.

## Explain the result
- Lead with the probability of reaching the goal, then the median path, then the worst 10% case.
- All amounts are inflation-adjusted to today's money.
- Always relay every item in `input_warnings` and state which assumptions were defaults (especially the investment return).
- Offer one or two what-if variations (lower return, later retirement, lower spending) and rerun if the user agrees.
- Close with: this is a planning projection, not financial advice. For decisions, a qualified financial professional should review it.
