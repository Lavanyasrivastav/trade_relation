Trader Performance vs Market Sentiment
Overview
This project explores how Bitcoin market sentiment (Fear–Greed Index) influences trader behavior and performance using real trading data from Hyperliquid.
The idea is simple:
Do traders behave differently when the market is fearful vs greedy? And does that actually affect how much they earn?
What I Tried to Answer
1.Do traders make more money during Fear or Greed phases?
2.Does win rate change depending on sentiment?
3.Do traders take more risk (larger positions) in certain market conditions?
4.Are successful traders behaving differently from others?

Data Used
1. Market Sentiment Dataset
Daily classification: Extreme Fear → Extreme Greed
2. Trader Dataset (Hyperliquid)
Trade-level data including:
  Account
  Trade size (USD & tokens)
  Buy/Sell side
  Execution price
  Closed PnL
  Timestamp

How I Approached It:
    Data Preparation
    Cleaned column names and formats
    Converted timestamps into a consistent datetime format
    Mapped each trade to a daily sentiment label
    Merged both datasets on date
    Feature Engineering
    Created a flag for profitable trades (is_profit)
    Used trade size (USD) as a proxy for risk-taking
    Calculated:
      Average PnL
      Win rate
      Trade frequency

Key Findings
1. Profitability is highest during Extreme Greed
    Traders earn the most on average when the market is strongly bullish
    Win rate is also highest in this phase (~46%)
👉 Suggests that trend-following works better in bullish conditions

2. Fear phases drive activity, not efficiency
    Highest number of trades and total volume occur during Fear
    But:
    Lower win rate
    Lower average PnL
👉 Looks like panic or reactive trading, not strategic trading

3. Traders take bigger risks during Fear
   Average trade size is highest during Fear (~$7.8k)
👉 But this doesn’t improve performance →
   more risk, worse outcomes

4. Good traders behave differently
   Top traders remain profitable across all conditions
   They perform especially well during Extreme Greed
   Poor performers:
      Lose money in volatile phases
      Likely overtrade or mismanage risk


Strategy Takeaways
Based on the analysis:
1. Lean into strong trends (Greed phases)
Increase exposure when sentiment is strongly positive—this is where both win rate and PnL peak.
2. Be cautious during Fear
Even though activity increases, results worsen. Reducing position size helps avoid unnecessary losses.
3. Avoid overtrading in volatile markets
Higher frequency during Fear doesn’t translate into better outcomes.

Tools Used
Python
Pandas
NumPy
Matplotlib / Seaborn
Google Colab


How to Run This::
   Clone the repo
   Open the notebook (Jupyter or Colab)
   Install required libraries if needed
   Run all cells in order

Final Thoughts
This analysis shows a clear pattern:
Greed → better performance, more stable outcomes
Fear → more activity, but worse decisions
The key difference between good and bad traders seems to come down to how they manage risk under different market conditions.

Author
Lavanya Srivastav
