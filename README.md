Trader Behavior vs Market Sentiment Analysis
Candidate: Prince Kashav
Google Colab Notebook:https://colab.research.google.com/drive/1eFQPQ4MgHwB1xbm5ZQ4mXU3E2Ceuv0fj?usp=sharing
drive link https://1drv.ms/f/c/cad7999d5a776d23/Ek5OyWBYoU1LobN4QgZ1sMkBqhWvUvng-_FynUdUfWs0xQ?e=xwquoA
GitHub Repository:[https://github.com/PRIINCE141/MY-SQL](https://github.com/PRIINCE141/ds_prince_kashav)

Project Overview

This project explores how trader behavior (profitability, trading volume, and risk) correlates with overall
market sentiment (Fear vs Greed). The analysis uses trading data from the Hyperliquid exchange and sentiment 
data from the Bitcoin Fear & Greed Index to identify patterns of behavior under different market moods.

Objectives

Study trader performance metrics such as PnL, volume, and win rate.

Analyze how these performance metrics vary under different sentiment conditions.

Validate the relationship between market sentiment and trading activity using statistical tests.

Provide insights for smarter trading strategies by combining sentiment and trade‑level data.

Datasets Used
1. Trader Activity Data (Hyperliquid)

Rows: ~211,000

Key columns include: account, coin, execution_price, size_usd, side, timestamp_ist, closed_pnl, fee

Captures trade‑level details across accounts and assets.

2. Bitcoin Market Sentiment Data (Fear & Greed Index)

Rows: ~2,600

Columns: timestamp, value, classification, date

Sentiment values range from 0 (extreme fear) to 100 (extreme greed).

Data Cleaning & Preprocessing

Column names standardized to lowercase and snake_case for consistency.

Timestamps converted into datetime objects; date column extracted for daily aggregation.

Duplicate entries removed; rows missing timestamps or key fields were dropped.

Numeric conversion applied to execution price, size, PnL, fee, etc.

Trader data merged with sentiment data on date.

Missing sentiment days filled via forward/backward filling to create continuous daily coverage.

Feature Engineering & Metrics

Daily aggregated metrics include:

total_trades: number of trades per day

total_volume_usd: sum of trade volume in USD per day

avg_execution_price: mean execution price per day

median_fee: median fee per trade per day

unique_accounts: number of distinct trader accounts per day

avg_closed_pnl: average profit or loss per trade per day

win_rate: percentage of trades resulting in positive closed PnL

These metrics are then joined with sentiment classification (Fear vs Greed) and sentiment value for further analysis.

Exploratory Data Analysis (EDA)

Average Daily Volume by Sentiment: Trading volume is noticeably higher during Greed periods than Fear periods, indicating increased risk tolerance and participation when sentiment is positive.

Sentiment vs Volume Time Series: A clear pattern shows volume and profitability rising during sentiment‑increasing phases and declining during fear phases.

Profitability & Win Rate by Sentiment: Traders show higher average PnL and win rate during Greed phases compared to Fear.

Statistical Validation

Statistical tests (e.g., Mann–Whitney U test) were used to compare metrics between Fear and Greed periods. For example:

Total volume p‑value < 0.001 → significant difference between sentiment phases.

Win rate p‑value ~0.004 → traders perform significantly better in Greed phases.

These results support the hypothesis at the 95 % confidence level.

Insights

Trader activity and risk‑taking increases in Greed phases.

Profitability improves when sentiment is positive.

Sentiment drops often lead to smaller positions and more conservative behavior.

Market sentiment can serve as a leading indicator for trading volume and performance shifts.

Deliverables

notebook_1.ipynb – full Colab notebook

csv_files/

daily_trading_metrics.csv

merged_trading_sentiment.csv

outputs/ – charts and visualizations (.png files)

ds_report.pdf – final project report

README.md – this documentation file

Tools Used

Python (Pandas, NumPy, Matplotlib, Seaborn)

Google Colab

Scikit‑learn (for optional clustering)

GitHub for version control and submission

Conclusion

This project demonstrates a significant link between market sentiment and trading behavior. Greed‑driven periods are linked with higher trading volume, more risk‑taking, and improved profitability. Incorporating sentiment signals into trading frameworks could lead to more informed, data‑driven strategies.
