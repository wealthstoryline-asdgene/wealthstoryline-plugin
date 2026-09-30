# WealthStoryLine MCP — household financial Monte Carlo simulation

Ask your AI assistant "Can I retire at 60?" or "Can we afford this apartment?" and get a probabilistic answer. WealthStoryLine simulates 3,000 possible futures of your household finances — random inflation, salary growth, interest rates, house prices and investment returns — and reports how likely you are to reach your goal.

Works with **Claude, ChatGPT, Cursor, VS Code** and any MCP client that supports remote (Streamable HTTP) servers. No account, no API key.

```
https://wealthstoryline.com/mcp
```

## What you get
- Probability of reaching a net-worth goal by a given year
- Years needed to reach a target
- Chance of running out of money
- Inflation-adjusted net worth over time for the top 10%, middle 50%, worst 10% and worst 1% of outcomes
- Storylines: futures grouped by life events, e.g. "in 12% of futures you would have to sell the house around year 8"
- Built-in macro assumptions for Taiwan, Japan, the US, China and Canada (2004–2024 history)

## Install

### Claude
- **Claude Code / Cowork plugin**: install `wealthstoryline` from the plugin directory (adds the server plus a skill that guides Claude through the inputs).
- **Claude Code (server only)**:
  ```bash
  claude mcp add --transport http wealthstoryline https://wealthstoryline.com/mcp
  ```
- **Claude.ai / Claude Desktop**: Settings → Connectors → Add custom connector → `https://wealthstoryline.com/mcp`

### ChatGPT
Enable developer mode in Settings → Apps & Connectors, then create a connector with the URL `https://wealthstoryline.com/mcp` (no authentication).

### Cursor
Add to `~/.cursor/mcp.json`:
```json
{
  "mcpServers": {
    "wealthstoryline": {
      "url": "https://wealthstoryline.com/mcp"
    }
  }
}
```

### VS Code
```bash
code --add-mcp '{"name":"wealthstoryline","type":"http","url":"https://wealthstoryline.com/mcp"}'
```
or add to `.vscode/mcp.json`:
```json
{
  "servers": {
    "wealthstoryline": {
      "type": "http",
      "url": "https://wealthstoryline.com/mcp"
    }
  }
}
```

### Smithery
[smithery.ai/server/@wealthstoryline/wealthstoryline](https://smithery.ai/server/@wealthstoryline/wealthstoryline)

### Other MCP clients
Use the Streamable HTTP URL `https://wealthstoryline.com/mcp`. No authentication is required.

## Example prompts
1. "I'm 35 in Taiwan, earn 900,000 a year, spend 600,000, have 1.5 million saved and want to retire at 65. What's the chance I have 15 million in 20 years?"
2. "We're a family of three in Japan. Household income 8 million yen, expenses 6 million yen, savings 20 million yen. Can we retire at 60?"
3. "I plan to buy a 30 million TWD apartment in 2028 with 20% down. How likely is a forced sale?"
4. "Compare my plan with investing 80% of savings in the S&P 500 instead of 60%."

## Tools
| Tool | What it does |
|---|---|
| `run_simulation` | Runs a 3,000-path simulation of income, expenses, investments, real estate, mortgages, loans and other assets; returns goal probability, bankruptcy rate, net-worth percentiles and storylines |
| `get_simulation_result` | Fetches a result that was still running |
| `get_country_defaults` | Shows a country's default macro assumptions (TW, JP, US, CN, CA) |
| `list_investment_options` | Searches about 3,900 ETFs, stocks, bonds, crypto and commodities usable in advanced investment |
| `explain_methodology` | Explains the model, available modules and limitations |

All tools are read-only.

## What is included (early access)
Family members, liquid assets, income and expense curves, extra income/expense streams, one-off income/expense events, basic and advanced investment, real estate, mortgages and other loans, other assets, and storylines. 3,000 paths per run. Insurance and income-tax modules are not offered yet. 10,000 paths, saved plans, PDF reports and advisor features are on [wealthstoryline.com](https://wealthstoryline.com). Early-access terms may change later.

## Usage limits
Up to 100 simulations per hour per network (IP address). If you hit the limit, wait and try again later. Heavy or commercial use: contact us.

## Privacy
Only the numbers needed for the simulation are stored; names and custom labels are discarded. Anonymous simulations are deleted after 30 days. See the [privacy policy](https://wealthstoryline.com/privacy.html) and [terms](https://wealthstoryline.com/terms.html).

## Disclaimer
Results are projections for planning discussions, not financial advice or guarantees.

## Support
info@wealthstoryline.com · [wealthstoryline.com](https://wealthstoryline.com)
