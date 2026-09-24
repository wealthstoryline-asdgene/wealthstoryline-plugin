---
name: wealth-simulation
description: Use when the user asks whether their savings, income and spending plan will reach a financial goal, when they can retire, whether they can afford a house or mortgage, how likely they are to run out of money, or wants a Monte Carlo projection of household net worth. Guides gathering inputs, calling the WealthStoryLine run_simulation tool and explaining the result, including storylines.
---

# Household wealth simulation with WealthStoryLine

## When to use
The user wants a probabilistic answer about their household finances: "Can I retire at 60?", "Can we afford this apartment?", "Should I prepay the mortgage or invest?", "Will I have 10 million in 20 years?". Use the `run_simulation` tool rather than estimating by hand.

Early access: every stable module of the website's business plan is currently free and anonymous (real estate, mortgages, multiple income/expense streams, income/expense events, advanced investment, other assets, storylines). Call `explain_methodology` if you need the current list.

## Gather inputs (ask only for what is missing)
1. Age and country (TW, JP, US, CN or CA). Amounts are in that country's currency, full units.
2. Savings / liquid assets today.
3. Household income and planned retirement age; pension after retirement if any. Extra income streams (rent, side business) and one-off income events (bonus, inheritance) go in their own modules.
4. Living expenses; extra expense streams (children's education, care) and one-off expense events (car, wedding).
5. How savings are invested and the expected return if the user knows it.
6. Property owned or planned (price, purchase year, down payment) and its mortgage; other loans.
7. Other assets such as a business stake or collectibles.
8. The goal: a target net worth by a certain year.

Only fill what the user actually told you or clearly implied. If a value is unknown, leave it out; the tool uses defaults and reports them in `input_warnings`.

## Explain the result
- Lead with the probability of reaching the goal, then the median path, then the worst 10% case. Trajectory amounts are inflation-adjusted to today's money.
- Storylines: describe the two or three largest groups in plain words, e.g. "In about 12% of futures you would have to sell the house around year 8". Storyline amounts are nominal (not inflation-adjusted).
- Model limits to mention when relevant: a forced sale sells every property and adds no rent afterwards (optimistic); custom assets in advanced investment vary between runs, so quote a range.
- Always relay every item in `input_warnings` and say which assumptions were defaults (especially the investment return).
- Offer one or two what-if variations (lower return, later retirement, smaller house, lower spending) and rerun if the user agrees.
- Close with: this is a planning projection, not financial advice. For decisions, a qualified financial professional should review it.
