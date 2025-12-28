# Twitter Stock Price Analysis using Arbitrage Pricing Theory (APT)

## Overview
This project presents a comprehensive analysis of **Twitter stock prices** using **time series techniques** and the **Arbitrage Pricing Theory (APT)** framework.  
The workflow and outputs strictly follow the structure and methodology demonstrated in the reference PPT used for this study.

The analysis combines:
- Historical stock price behavior
- Technical indicators
- Time series decomposition
- ARIMA forecasting
- Macroeconomic factor analysis
- Event-based interpretation of abnormal returns

---

## Objectives
- Analyze long-term trends in Twitter stock prices
- Compute and visualize moving averages
- Decompose the time series into trend, seasonality, and residuals
- Forecast stock prices using ARIMA
- Apply Arbitrage Pricing Theory (APT) to estimate expected returns
- Identify significant macroeconomic factors
- Detect dates with extreme return differences
- Simulate news events associated with abnormal returns

---

## Methodology (Aligned with PPT)

### 1. Data Loading
- Twitter historical stock price data
- Market index / financial indicators
- U.S. macroeconomic indicators

### 2. Exploratory Data Analysis (EDA)
- Dataset structure and summary
- Missing value analysis
- Initial visualizations

### 3. Technical Indicators
- Daily returns calculation
- 30-day moving average computation and visualization

### 4. Time Series Decomposition
- Trend component
- Seasonal component
- Residual component

### 5. Forecasting
- Auto-ARIMA model selection
- Train vs test comparison
- Forecast visualization

### 6. Arbitrage Pricing Theory (APT)
- Expected returns estimation
- Return difference calculation
- Identification of abnormal returns

### 7. Significant Factors
- Factor loading matrix
- Threshold-based identification of significant macroeconomic factors
- Output matches PPT-defined significant factors

### 8. Event Analysis
- Dates with the most significant return differences
- Simulated news headlines for those dates (placeholder, as per PPT)

---

## Datasets Used

| File Name | Description |
|---------|------------|
| `twitter-stocks.csv` | Historical Twitter stock prices |
| `financials.csv` | Market index and financial indicators |
| `US_macroeconomics.csv` | U.S. macroeconomic variables |

> Some datasets are sourced from public financial repositories and Kaggle.

---

## Technologies and Libraries
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels
- pmdarima
- Scikit-learn
- tqdm

---

## Key Results
- Twitter stock shows clear long-term trend behavior
- ARIMA provides a reasonable baseline forecast
- Multiple macroeconomic indicators are identified as significant factors
- Extreme return dates align with major market movements
- APT framework effectively highlights abnormal returns

---

## How to Run

Clone the repository:
```bash
git clone https://github.com/your-username/Twitter-Stock-Price-Analysis-APT.git
cd Twitter-Stock-Price-Analysis-APT
