# WealthStoryLine plugin for Claude

Run household Monte Carlo simulations from Claude. Describe your situation in plain language and Claude calls the WealthStoryLine engine, which simulates 3,000 futures with random inflation, salary growth, interest rates and investment returns.

## What you get
- Probability of reaching a net-worth goal by a given year
- Years needed to reach a target
- Chance of running out of money
- Inflation-adjusted net worth over time for the top 10%, middle 50%, worst 10% and worst 1% of outcomes
- Built-in macro assumptions for Taiwan, Japan, the US, China and Canada (2004–2024 history)

## Install
- **Claude Code / Cowork**: install `wealthstoryline` from the plugin directory.
- **Any Claude app**: Settings → Connectors → Add custom connector → `https://wealthstoryline.com/mcp`

No account is needed for the free plan.

## Example prompts
1. "I'm 35 in Taiwan, earn 900,000 a year, spend 600,000, have 1.5 million saved and want to retire at 65. What's the chance I have 15 million in 20 years?"
2. "We're a family of three in Japan. Household income 8 million yen, expenses 6 million yen, savings 20 million yen. Can we retire at 60?"
3. "Compare my plan with investing 80% of savings instead of 60%."

## Tools
| Tool | What it does |
|---|---|
| `run_simulation` | Runs the free 3,000-path simulation |
| `get_simulation_result` | Fetches a result that was still running |
| `get_country_defaults` | Shows a country's default macro assumptions |
| `explain_methodology` | Explains the model, free vs paid modules and limitations |

All tools are read-only.

## Free plan limits
One card per module (one income, one expense, one loan…), 3,000 paths, no mortgage or real-estate modelling. More modules and 10,000 paths are available on [wealthstoryline.com](https://wealthstoryline.com).

## Privacy
Only the numbers needed for the simulation are stored; names and custom labels are discarded. Anonymous simulations are deleted after 30 days. See the [privacy policy](https://wealthstoryline.com/privacy.html).

## Disclaimer
Results are projections for planning discussions, not financial advice or guarantees.

## Support
info@wealthstoryline.com
