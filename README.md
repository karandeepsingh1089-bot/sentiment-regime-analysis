# Sentiment Regime Analysis: Impact on Trader Behavior & Profitability

## Objective

This project analyzes how Bitcoin market sentiment regimes (Fear/Greed) influence trader behavior and performance on Hyperliquid.

The goal is to understand whether sentiment affects:
- Profitability
- Trading intensity
- Position sizing
- Directional bias
- Risk-adjusted returns

The analysis is conducted at daily granularity after merging trade-level data with sentiment classifications.

---

## Dataset Overview

Two datasets were used:

1. **Bitcoin Sentiment Data**
   - Columns: `date`, `classification` (Fear / Greed / Extreme Fear / Extreme Greed / Neutral)

2. **Trader Execution Data**
   - Trade-level data including:
     - `account`
     - `execution_price`
     - `size_usd`
     - `direction`
     - `closed_pnl`
     - timestamps

Due to GitHub file size limitations, full datasets are not included.

Sample datasets are provided:
- `data/trades_sample.csv`
- `data/sentiment_sample.csv`

These allow full execution of the notebook.

---

## Methodology

### 1. Data Preparation
- Converted timestamps to daily granularity
- Merged sentiment classification with trade data on date
- Validated merge integrity and missing values

### 2. Feature Engineering
Constructed daily-level metrics:
- `daily_pnl` (sum of closed PnL)
- `total_opens`
- `avg_trade_size_usd`
- `long_ratio`
- `win_day` (daily profitability indicator)

### 3. Regime-Level Analysis
Compared across sentiment regimes:
- Mean / Median / Std of daily PnL
- Win rate
- Activity intensity
- Position sizing behavior
- Risk-adjusted return (mean / std)

---

## Key Findings

- **Fear regimes generate higher average returns but significantly higher volatility.**
- **Extreme Greed exhibits the highest win rate (greater consistency).**
- Trading intensity increases sharply during Fear, driven by a subset of highly active traders.
- Position sizes expand during Fear regimes, indicating amplified risk-taking behavior.
- Traders display stronger long bias during Extreme Fear, suggesting dip-buying behavior.
- No sentiment regime clearly dominates on a risk-adjusted basis.

---

## Strategy Implications

1. **Volatility-Responsive Risk Scaling**
   - Reduce leverage and cap position sizes during Fear regimes.
   - Control tail-risk exposure despite higher opportunity.

2. **Consistency-Focused Participation During Extreme Greed**
   - Favor systematic strategies during high win-rate environments.
   - Avoid over-amplifying exposure in low-volatility regimes.

