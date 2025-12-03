
## Introduction:
- This project focuses on applying data science and machine learning techniques to financial market analysis using stock data from Yahoo Finance. 
- It covers a wide range of topics including data preprocessing, exploratory data analysis, technical indicators, trading strategy design, backtesting, portfolio optimization, and predictive modeling.

- The project explores moving averages, technical indicators, and trading strategies such as Moving Average Crossover and Mean Reversion. 
- It incorporates machine learning models to forecast stock returns, evaluates their performance using multiple metrics, and visualizes the results. 
- Additionally, it introduces core financial models such as the Capital Asset Pricing Model (CAPM) and the Efficient Frontier

## Part 1: 
## AAPL Stock Analysis & Moving Average Crossover Strategy

### Project Overview

This project analyzes **Apple Inc. (AAPL)** stock price data from **January 1, 2010 to December 31, 2022** using exploratory data analysis (EDA) and technical trading strategies. The analysis includes:

- Historical price trends and volatility analysis
- Simple Moving Average (SMA) indicators (10-day and 50-day)
- Moving Average Crossover trading strategy implementation
- Backtesting and portfolio performance evaluation

### Dataset

- **Source:** Yahoo Finance (via `yfinance`)
- **Ticker:** AAPL
- **Period:** 2010-01-01 to 2022-12-31
- **Frequency:** Daily trading data
- **Records:** 3,272 trading days
- **Features:** Open, High, Low, Close, Adj Close, Volume

#### Data Characteristics

- **Price Range:** $5.76 (minimum, adjusted for splits) to $179.18 (maximum)
- **Mean Close:** ~$49.26 | **Median Close:** ~$27.19
- **Distribution:** Right-skewed (long-term uptrend dominates recent years)
- **Volume:** Mean ≈ 256M shares/day | Median ≈ 167M shares/day (high-volume outliers present)

## #Project Structure

```
Honors-Thesis/
├── README.md                 # This file
├── yfinancedata.ipynb        # Main analysis notebook
└── READ.ME                   # Project notes
```

### Methodology

#### 1. Exploratory Data Analysis (EDA)

#### Price Analysis
- **Linear & Log-scale plots:** Log scale reveals underlying growth patterns without recent-year visual dominance
- **Annual returns bar chart:** Green (positive) vs. red (negative) returns by year
- **Daily returns histogram:** Distribution of daily percentage changes

#### Technical Indicators
- **10-day SMA (MA10):** Responsive, tracks short-term price swings
- **50-day SMA (MA50):** Smooth, lags behind MA10; acts as trend filter

#### Key Findings
- Clear long-term uptrend from 2010 to 2022
- MA10 stays below MA50 during declines, above during rallies
- Crossovers signal momentum shifts: MA10 > MA50 = bullish, MA10 < MA50 = bearish

### 2. Trading Strategy: Moving Average Crossover

#### Signal Generation
```
Buy Signal:  data['Position'] = +1  when MA10 crosses above MA50
Sell Signal: data['Position'] = -1  when MA10 crosses below MA50
```

#### Strategy Characteristics
- **Frequent whipsaws:** Many quick alternating buy/sell signals (2010–2020)
- **Quiet periods:** Fewer signals during 2020–2021 (only 1 buy, 3 sells)
- **Signal bias:** More red (sell) arrows than green (buy) arrows overall
- **Implications:** Strategy is noisy; may require smoothing or MA gap filters to reduce false signals

### 3. Portfolio Backtesting

#### Initial Capital
- $100,000 USD

#### Performance Observations

| Period | Observation |
|--------|------------|
| 2010–2016 | Portfolio flat/stagnant; minimal growth |
| 2016–2020 | Increased volatility; modest downward bias |
| 2018–2021 | General downtrend with few strong up months |
| 2021–2022 | Extreme high/low swings; large drawdowns & spikes |



## Requirements

```
pandas           # Data manipulation
numpy            # Numerical computing
yfinance         # Stock data download
matplotlib       # Plotting
seaborn          # Statistical visualization
```


### Python Version

Python 3.7+

