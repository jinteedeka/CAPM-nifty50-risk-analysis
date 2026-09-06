# CAPM-Based Risk-Return Analysis of Nifty50 Stocks

## Overview
This project applies the Capital Asset Pricing Model (CAPM) to analyze the risk and return characteristics of five major Nifty50-listed stocks — Reliance Industries, TCS, HDFC Bank, Infosys, and ITC — relative to the Nifty50 index, using daily price data from January 2021 to September 2026.

The goal is to understand how each stock's returns relate to overall market movements, and whether individual stock selection outperforms a simple diversified index on a risk-adjusted basis.

## Methodology
1. **Data Collection**: Daily closing prices for five Nifty50 stocks and the Nifty50 index were retrieved using the `yfinance` Python library.
2. **Returns Calculation**: Daily percentage returns were computed for each stock and the index.
3. **Risk-Return Summary**: Annualized return, annualized volatility (standard deviation), and Sharpe ratio were calculated for each stock and the index.
4. **CAPM Regression**: For each stock, an OLS regression of daily stock returns against daily market (index) returns was run to estimate:
   - **Beta** — sensitivity of the stock's returns to market returns
   - **Alpha** — average return unexplained by market movement
   - **R-squared** — proportion of the stock's return variance explained by the market
5. **Visualization**: A risk-return scatter plot was produced to visually compare each stock's position relative to the index.

## Tools Used
- Python (Google Colab)
- `yfinance` — market data retrieval
- `pandas`, `numpy` — data processing
- `statsmodels` — CAPM regression (OLS)
- `matplotlib` — visualization

## Key Findings
- The Nifty50 index achieved the best risk-adjusted return (Sharpe ratio ≈ 0.76) of any asset in the sample, outperforming all five individual stocks.
- ITC had the lowest beta (0.66) among the stocks studied, indicating lower sensitivity to market movements, and the best Sharpe ratio (≈ 0.52) among individual stocks.
- HDFC Bank and Reliance had betas above 1 (1.09 each), indicating higher-than-market volatility.
- All estimated alphas were close to zero, consistent with CAPM's prediction that few stocks persistently generate excess risk-adjusted returns.

See `report.md` for a full discussion of these findings and their implications.

## How to Run
1. Open the notebook in Google Colab.
2. Run each cell in order (data collection → returns → risk-return summary → CAPM regression → visualization).
3. No local installation is required; all dependencies are installed via `pip install yfinance` in the first cell.

## Author
Jintee Deka
