# Yield Curve Monitor (US Rates)

## Objective
This project builds a simple **rates desk monitoring tool** to track:
- US Treasury yield levels
- Yield curve slope dynamics
- Daily rate shocks
- Yield curve regimes (steepening / flattening, bull / bear)

The goal is to translate **daily rate movements** into an interpretable macro and trading framework.

---

## Market intuition

Rates desks typically analyze the yield curve along two dimensions:

1. **Level**  
   → Are rates moving up or down overall?

2. **Slope**  
   → Is the curve steepening or flattening?

Combining both allows identification of key regimes such as:
- Bull Steepening
- Bull Flattening
- Bear Steepening
- Bear Flattening

These regimes are closely linked to:
- Monetary policy expectations
- Growth and inflation outlook
- Risk sentiment

---

## Data

US Treasury yield proxies downloaded via Yahoo Finance (`yfinance`):

- **5Y**  : `^FVX`
- **10Y** : `^TNX`
- **30Y** : `^TYX`

Yields are expressed in percentage terms and converted into **basis points** when computing spreads and daily changes.

---

## Methodology

### 1. Yield levels
Daily yield levels for 5Y, 10Y and 30Y maturities.

### 2. Curve slopes (basis points)
- **10s5s** = (10Y − 5Y)
- **30s10s** = (30Y − 10Y)

These spreads capture the shape of the yield curve.

### 3. Daily changes (basis points)
- **Level change**: daily change in the 10Y yield (proxy for overall rate moves)
- **Slope change**: daily change in the 10s5s spread

### 4. Regime classification
Each day is classified using the sign of:
- level change
- slope change

| Level | Slope | Regime |
|------|------|--------|
| ↓ | ↑ | Bull Steepening |
| ↓ | ↓ | Bull Flattening |
| ↑ | ↑ | Bear Steepening |
| ↑ | ↓ | Bear Flattening |

---

## Outputs

The script / notebook produces:
- Yield level plots (5Y / 10Y / 30Y)
- Yield curve slope plots (10s5s, 30s10s)
- Daily level and slope changes (bps)
- Distribution of yield curve regimes
- Tabular view of recent rate moves and regimes

