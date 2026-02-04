# Trader Performance vs Market Sentiment Analysis

## Project Overview
This project analyzes how **market sentiment (Fear vs Greed)** impacts trader performance and behavior.  
We use **historical trade-level data** combined with the **Fear & Greed Index** to explore:

- Trader profitability (daily PnL, win rate)
- Trading behavior (trade frequency, position size, long/short bias)
- Risk exposure using leverage proxies
- Trader segmentation (high vs low leverage, frequent vs infrequent, consistent vs inconsistent traders)

---

## Datasets

1. **Historical Trading Data**
   - Each row represents a single trade.
   - Key columns: 
     - `Account` – trader ID  
     - `Order ID` – unique trade ID  
     - `Timestamp IST` – trade execution time  
     - `Side` – BUY/SELL  
     - `Size USD` – position size  
     - `Closed PnL` – realized profit/loss

2. **Fear & Greed Index Data**
   - Daily market sentiment indicator.
   - Key columns:
     - `date` – date of observation  
     - `classification` – Fear / Greed

**Note:** Leverage was not explicitly available; trade size (`Size USD`) was used as a proxy for risk exposure.

---

## Part A: Data Preparation
- Converted timestamps to daily level and aligned both datasets by date.
- Checked for missing values and duplicates.
- Created daily metrics per trader:
  - `daily_pnl` – total profit/loss
  - `trades_per_day` – number of trades
  - `win_rate` – percentage of profitable trades
  - `avg_trade_size` – average position size
  - `long_ratio` – % of BUY trades

---

## Part B: Analysis & Insights

### Insight 1: Performance differs between Fear and Greed
- Traders perform better on Greed days (higher daily PnL and win rate)
- Volatility increases during Greed, indicating higher risk-reward exposure

### Insight 2: Behavior changes with sentiment
- More trades and higher position sizes during Greed
- Long bias stronger on Greed days
- Fear leads to conservative and fewer trades

### Insight 3: High-risk segments
- High-leverage traders have lower performance during Fear
- Frequent traders benefit more on Greed days
- Consistent traders maintain stability across both sentiments

**Charts & Tables:** See notebook for visualizations of sentiment vs performance and behavioral metrics.

---

## Part C: Actionable Strategies
1. **Fear days:** Reduce leverage and position sizes for high-risk traders to limit drawdowns.
2. **Greed days:** Increase trade frequency and long positions for consistent traders to maximize returns.

---

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/shivamjais25/Data-Science-project.git

## Setup

### Requirements
- Python 3.8 or higher

### Python Libraries
- pandas
- numpy
- matplotlib
- seaborn

Install dependencies using pip:

```bash
pip install pandas numpy matplotlib seaborn
