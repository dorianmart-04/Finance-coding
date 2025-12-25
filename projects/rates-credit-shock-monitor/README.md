# Rates / Credit Shock Monitor (Python)

## Objective
Build a simple desk-style monitoring tool to track stress regimes across:
- US rates proxy (10Y: ^TNX)
- Investment Grade credit (LQD)
- High Yield credit (HYG)

The tool computes daily returns, rolling volatility, correlations, and identifies **shock days** using empirical quantiles.

## Market intuition
- When rates rise sharply, long-duration assets (IG credit) typically underperform.
- HY credit is more sensitive to risk sentiment and credit spread widening.
- The goal is to distinguish **rate-driven** vs **credit-driven** stress episodes.

## Methodology (high level)
1. Download historical data using `yfinance`
2. Compute daily returns
3. Compute rolling volatility (annualized)
4. Compute correlation matrix
5. Define shocks as returns outside the [5%, 95%] quantile range
6. Flag “system shock days” when at least one proxy experiences a shock

## Outputs
- Price levels and normalized levels (base 100)
- Rolling volatility plots
- Correlation heatmap
- Shock-day highlights
- Summary table (avg return, vol, shock counts, worst/best day)

