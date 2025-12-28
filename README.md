# Twitter Stock Price Analysis using Arbitrage Pricing Theory (APT)

This project implements a complete, end-to-end **financial time-series analysis pipeline** that analyzes and forecasts **Twitter stock price behavior** using a combination of:

- **Exploratory Data Analysis (EDA)** to understand the dataset structure and quality
- **Technical Analysis** (daily returns + 30-day moving average) to observe trend behavior
- **Time-Series Decomposition** (trend/seasonality/residual) to interpret components of price movement
- **ARIMA Forecasting (Auto-ARIMA)** to build a baseline prediction model for future prices
- **Arbitrage Pricing Theory (APT)** to explain stock returns using **market and macroeconomic risk factors**
- **Extreme Return Event Detection** to find the days where Twitter behaves very differently than expected
- **Event Interpretation (Simulated News)** to link abnormal return dates to real-world style explanations (placeholder)

The notebook and outputs are organized so that anyone reading the repository can follow the story section-by-section, from data loading all the way to factor-based return analysis.


## Why this project?
Stock prices are not driven only by past prices. In real financial analysis, returns often change due to:
- Broader market movement (index behavior)
- Macroeconomic conditions (inflation, unemployment, interest rates, etc.)
- Sudden external shocks (company news, policy updates, economic changes)

This project was created to show both:
1) **Prediction**: “What might happen next?” (ARIMA)  
2) **Explanation**: “Why did this happen?” (APT + macro factors + abnormal return detection)

This makes the project useful for:
- academic evaluation
- learning time-series + factor modeling
- portfolio demonstration (data science + finance reasoning)


## What the project does (High-level)
At a high level, the system behaves like a pipeline:

1. Load Twitter stock dataset  
2. Clean and format dates  
3. Compute returns and technical indicators  
4. Perform decomposition analysis  
5. Train forecasting model (ARIMA)  
6. Load market dataset (financials / index proxy)  
7. Build APT logic to calculate expected returns  
8. Compare expected vs actual returns  
9. Identify abnormal return dates  
10. Print significant macroeconomic factors  
11. Generate simulated news output for extreme dates  


## Technologies and Libraries Used
This project uses Python and standard data science tools:

- `pandas`, `numpy` for data processing
- `matplotlib`, `seaborn` for visualization
- `statsmodels` for time-series decomposition and statistical modeling
- `pmdarima` for auto-arima model selection
- `scikit-learn` (if used in parts) for supporting operations
- `tqdm` for progress bars (where needed)


## Features

### 1) Stock Dataset Cleaning + Basic EDA
- Displays `info()`, shape, missing values
- Ensures the dataset is usable for time-series analysis
- Confirms columns needed for downstream tasks exist

### 2) Daily Return Computation
- Calculates daily returns from closing price
- This is the main variable used for APT and abnormal return analysis

### 3) Moving Average Trend Analysis
- Computes 30-day moving average
- Visualizes smoothed trend behavior to reduce noise

### 4) Seasonal Decomposition
- Decomposes closing price into:
  - trend
  - seasonal
  - residual noise
- Helps explain long-term movement vs short-term repeating behavior

### 5) ARIMA Forecasting
- Uses Auto-ARIMA to search best parameters using AIC
- Trains an ARIMA model and generates forecasts
- Produces forecasting summary and performance plots

### 6) APT-based Expected Return Calculation
- Loads market proxy dataset (financials)
- Compares Twitter daily return against expected return logic
- Calculates **Return Difference = Actual − Expected**

### 7) Significant Factor Output
- Identifies significant macro factors using a factor-loading threshold approach:
  - abs(loading) > 0.5
- Produces a list of macro factors driving return behavior

### 8) Extreme Return Difference Dates
- Detects top 5 highest positive and negative return differences
- These dates represent “Twitter behaved unusually compared to expectation”

### 9) Simulated News Headlines
- For each extreme date, prints a placeholder news sentence
- This step demonstrates how abnormal return dates can be interpreted using real-world events


## Datasets Used

### 1) Twitter Stock Dataset
File: `twitter-stocks.csv` (or equivalent)
Contains:
- Date, Open, High, Low, Close, Volume

### 2) Market / Financial Dataset
File: `financials.csv`
Used as:
- index proxy / benchmark daily returns

### 3) Macroeconomic Dataset
File: `US_macroeconomics.csv`
Contains:
- CPI, unemployment, mortgage rate, NASDAQ, income/consumption/savings, etc.

Note:
- The project is designed so datasets can be stored in a `/data` folder or loaded from Google Drive (Colab usage).

