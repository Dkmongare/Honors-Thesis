
## Introduction:
- This project focuses on applying data science and machine learning techniques to financial market analysis using stock data from Yahoo Finance. 
- It covers a wide range of topics including data preprocessing, exploratory data analysis, technical indicators, trading strategy design, backtesting, portfolio optimization, and predictive modeling.

- The project explores moving averages, technical indicators, and trading strategies such as Moving Average Crossovers.

## Part 1: 
## AAPL Stock Analysis & Moving Average Crossover Strategy

### Project Overview

This project analyzes **Apple Inc. (AAPL)** stock price data from **January 1, 2010 to December 31, 2022** using exploratory data analysis (EDA) and technical trading strategies. The analysis includes:

- Historical price trends and volatility analysis
- Simple Moving Average (SMA) indicators (10-day and 50-day)
- Moving Average Crossover trading strategy implementation

### Dataset

- **Source:** Yahoo Finance (via `yfinance`)
- **Ticker:** AAPL
- **Period:** 2010-01-01 to 2022-12-31
- **Frequency:** Daily trading data
- **Records:** 3,272 trading days
- **Features:** Open, High, Low, Close, Adj Close, Volume


### Methodology

#### 1. Exploratory Data Analysis (EDA)

#### Price Analysis
- **Linear & Log-scale plots:** Log scale reveals underlying growth patterns without recent-year visual dominance


#### Technical Indicators
- **10-day SMA (MA10):** 
- **50-day SMA (MA50):** 



### 2. Trading Strategy: Moving Average Crossover

#### Signal Generation
```
Buy Signal:  data['Position'] = +1  when MA10 crosses above MA50
Sell Signal: data['Position'] = -1  when MA10 crosses below MA50
```

#### Strategy Characteristics
- **Frequent whipsaws:** Many quick alternating buy/sell signals (2010–2020)
- **Quiet periods:** Fewer signals during 2020–2021 (only 1 buy, 3 sells)

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

