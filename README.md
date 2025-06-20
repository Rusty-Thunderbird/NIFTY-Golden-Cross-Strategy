# NIFTY-Golden-Cross-Strategy
A volatility-aware trading strategy for NIFTY futures, implemented in Pine Script and optimized using Python.
Overview
This project implements and evaluates a Golden Cross Strategy on NIFTY 50 Futures, integrating real-time volatility signals, adaptive slippage, and trailing stop-loss logic using:
Pine Script v6 for live simulation on TradingView
Python for data-driven SMA optimization and backtesting using historical Bhavcopy + India VIX data
Features
Pine Script (Live Strategy on TradingView)
SMA crossover signals using 21/22 period MAs
Adaptive slippage model based on India VIX, expiry days, and pre/post-market risk
Volatility-scaled trailing stop-loss and take-profit logic
Real-time strategy table with metrics: Net PnL, Win Rate, Slippage %, VIX exposure, etc.
Filters out positions during high VIX regimes

Python Backtester (Batch SMA Optimization)
Combines NIFTY Futures data across multiple expiries
Integrates India VIX and ATR filters for trade entry validation
Simulates long/short entries, stop-losses, and take-profits
Optimizes over 1000+ SMA pairs using:
VIX-filtered version
VIX-agnostic (vanilla Golden Cross) version
Returns top-performing SMA pairs based on PnL, Win Rate, and Final Capital

Sample Results:
*Filtered: PnL > ₹30,000 and Win Rate > 40% (Daily Candleframe)*

| Short SMA | Long SMA | Total PnL (₹) | Win Rate (%) | Final Capital (₹) |
|-----------|----------|----------------|---------------|-------------------|
| 23        | 25       | 34,822.74      | 68.18         | 1,34,822.74       |
| 1         | 8        | 33,956.15      | 42.55         | 1,33,956.15       |
| 25        | 26       | 33,463.25      | 57.69         | 1,33,463.25       |
| 4         | 5        | 32,617.98      | 58.57         | 1,32,617.98       |
| 3         | 5        | 31,917.26      | 57.41         | 1,31,917.26       |
| 23        | 24       | 31,807.49      | 55.56         | 1,31,807.49       |
| 21        | 22       | 30,363.51      | 58.62         | 1,30,363.51       |
