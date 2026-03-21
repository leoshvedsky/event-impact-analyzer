# Event Impact Analyzer: Financial Sector

How do bank stocks react to earnings surprises and analyst rating changes?

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Data](https://img.shields.io/badge/Data-Yahoo%20Finance-purple)

## Overview

This project uses **event study methodology** to measure how 10 major financial stocks react to two types of market events:

1. **Earnings Surprises** — When a company reports EPS above or below analyst estimates, how does the stock move over the next 1, 3, 5, and 10 trading days?
2. **Analyst Rating Changes** — When an analyst upgrades or downgrades a stock, does the market follow? Which firms' calls carry the most weight?

The analysis also builds a simple predictive model to test whether the size of an earnings surprise can forecast the magnitude of the price reaction.

## Stocks Analyzed

| Ticker | Company |
|--------|---------|
| JPM | JPMorgan Chase |
| GS | Goldman Sachs |
| BAC | Bank of America |
| WFC | Wells Fargo |
| MS | Morgan Stanley |
| C | Citigroup |
| USB | U.S. Bancorp |
| PNC | PNC Financial |
| SCHW | Charles Schwab |
| BK | Bank of New York Mellon |

## Key Findings

*Run the notebook to generate findings from the latest data.*

The analysis answers:
- Do earnings beats reliably lead to positive returns?
- How large is the beat vs miss spread in the financial sector?
- Which analyst firms move bank stocks the most?
- Can a simple model predict post-earnings price moves?

## Quick Start

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/event-impact-analyzer.git
cd event-impact-analyzer

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook event_impact_analyzer.ipynb
```

## Project Structure

```
event-impact-analyzer/
├── event_impact_analyzer.ipynb   # Main analysis notebook
├── requirements.txt              # Python dependencies
├── README.md                     # This file
└── images/                       # Generated charts (after running)
    ├── earnings_reaction_curve.png
    ├── earnings_surprise_scatter.png
    ├── earnings_heatmap.png
    ├── analyst_reaction_curve.png
    ├── analyst_firm_impact.png
    └── model_comparison.png
```

## Methodology

**Event Study Framework:**
For each event (earnings announcement or analyst action), we:
1. Identify the event date
2. Capture the stock's closing price in a window of -5 to +10 trading days around the event
3. Calculate cumulative returns relative to the day before the event
4. Aggregate across events to find average patterns

**Data Source:** All data is pulled from Yahoo Finance via the `yfinance` library (free, no API key required).

## Roadmap

- [x] **Phase 1:** Static analysis notebook with earnings and analyst event studies
- [ ] **Phase 2:** Automated data refresh via GitHub Actions
- [ ] **Phase 3:** Interactive Streamlit dashboard

## Disclaimer

This project is for **educational and research purposes only**. It is not financial advice. Past patterns do not guarantee future results.

## License

MIT
