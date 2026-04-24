# SMA Backtest

Systematic trend-following strategy backtested across five ETF asset classes (2015–2024).
Combines dual SMA crossover signals with ATR-based position sizing and a VIX regime filter.

## Overview

- **Signal**: long when SMA(short) > SMA(long), flat otherwise
- **Position sizing**: ATR-based, targeting 1% capital risk per trade
- **Regime filter**: moves to cash when VIX ≥ 30
- **Optimisation**: grid search over 9 SMA pairs on 2015–2020 training data
- **Evaluation**: honest out-of-sample test on 2020–2024

## Assets

| Ticker | Asset |
|--------|---------------------------|
| SPY | S&P 500 (US large caps) |
| QQQ | Nasdaq 100 (technology) |
| IWM | Russell 2000 (small caps) |
| GLD | Gold |
| TLT | 20+ Year Treasury Bonds |

## Metrics reported

Each asset is evaluated on both training and test periods:

- Annualised return
- Sharpe ratio
- Sortino ratio
- Calmar ratio
- Maximum drawdown
- Win rate

## Limitations

- Long/flat only — no short selling
- Assets optimised independently, no portfolio-level risk control
- Transaction cost fixed at 10 bps — no slippage or market impact modelling
