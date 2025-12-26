# Equity Greeks Monitor

## Overview

This project implements a simple **Equity Options Greeks Monitor** based on the Black–Scholes framework.  
The objective is to analyze how the price and risk sensitivities (Greeks) of a European option evolve as a function of the underlying spot price.

The project is designed as a **pedagogical but desk-oriented tool**, replicating the type of scenario analysis and risk monitoring used on equity derivatives trading desks.

---

## Financial Framework

The model relies on the **Black–Scholes assumptions**:
- Lognormal dynamics of the underlying asset
- Constant volatility
- Constant risk-free interest rate
- European-style options
- No arbitrage

The analytical formulas are used to compute:
- Option price
- Delta
- Gamma
- Vega
- Theta

All quantities are derived from the standard Black–Scholes variables \( d_1 \) and \( d_2 \).

---

## Methodology

### 1. Option Parameters

A reference European call option is defined by:
- Spot price \( S_0 \)
- Strike \( K \)
- Time to maturity \( T \)
- Risk-free rate \( r \)
- Volatility \( \sigma \)

These parameters remain fixed throughout the analysis.

---

### 2. Spot Scenario Grid

A grid of spot prices is created around the initial spot level to simulate different market scenarios:
- Downside stress
- At-the-money region
- Upside scenarios

For each spot level, the option price and Greeks are recomputed.

This approach mirrors how traders and risk managers assess option behavior under market moves.

---

### 3. Greeks Computation

For each spot level, the following quantities are calculated:

- **Price**: Option value as a function of spot  
- **Delta**: Exposure to spot movements  
- **Gamma**: Convexity of the delta  
- **Vega**: Sensitivity to volatility  
- **Theta**: Time decay  

This allows a full visualization of how risk evolves dynamically with the underlying price.

---

## Visual Analysis

The project generates the following plots:

- **Option Price vs Spot**
- **Delta vs Spot**
- **Gamma vs Spot**
- **Vega vs Spot**
- **Theta vs Spot**

Each plot provides an intuitive interpretation of the option’s risk profile:
- Delta transitions from 0 to 1 as the option moves from OTM to ITM
- Gamma peaks around the at-the-money region
- Vega is maximal when the option is near the strike
- Theta is most negative around ATM

---

## Interpretation (Trading Perspective)

This monitor highlights several key concepts used on equity derivatives desks:
- Convexity risk is concentrated near the strike
- Delta hedging becomes more challenging in high-gamma regions
- Volatility exposure is largest when uncertainty about exercise is highest
- Time decay accelerates as maturity approaches

The project emphasizes **risk intuition**, not only formula implementation.

---

## Extensions

Possible extensions include:
- Put option analysis and put–call parity verification
- Delta-hedging simulation
- Portfolio aggregation of multiple options
- Sensitivity analysis with respect to volatility and maturity
- Application to equity indices (e.g. S&P 500, Euro Stoxx 50)

---

## Technologies

- Python
- NumPy
- SciPy
- Matplotlib



