# pairs-trading-shiny
A Shiny app for pairs trading using cointegration and z-score strategies
# 📈 Pairs Trading Strategy Dashboard

A **Shiny app** to track and backtest a market-neutral **pairs trading strategy**, leveraging **cointegration** and **z-score analysis** to identify and act on statistically driven trading signals.

---

## 🚀 Overview

Pairs trading is a quantitative trading strategy that profits from the mean-reverting behavior of historically correlated stocks. This app:

- Identifies **highly correlated** and **cointegrated** S&P 500 stock pairs
- Computes **price ratio**, **rolling mean**, **standard deviation**, and **z-score**
- Generates **entry/exit signals** based on statistical thresholds (±2 std dev)
- Simulates trades and tracks performance: **profit**, **Sharpe ratio**, and **profit factor**
- Plots trading signals, price ratios, and PnL

---

## 🧠 Strategy Logic

1. **Pair Selection**
   - Find pairs with correlation > 0.75
   - Check for **cointegration**

2. **Z-Score Calculation**
   - Compute the ratio of prices
   - Calculate rolling 40-day mean and std deviation of the ratio
   - Compute z-score

3. **Trading Rules**
   - **Z > +2**: Short spread (short expensive, long cheap)
   - **Z < -2**: Long spread (long cheap, short expensive)
   - **Z ≈ 0**: Close position

---

## 🛠️ Running the App Locally

### Requirements
- R and RStudio installed
- Required libraries: `quantmod`, `shiny`, `dplyr`, `ggplot2`, `tseries`, `urca`, etc.

### Run
```R
http://127.0.0.1:7104
