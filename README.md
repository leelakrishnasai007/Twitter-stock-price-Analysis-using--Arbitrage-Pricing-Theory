# Twitter Stock Price Analysis using Arbitrage Pricing Theory (APT)

## Project Overview
This project presents a complete analysis of **Twitter stock prices** using **time series analysis** and the **Arbitrage Pricing Theory (APT)** framework.  
The entire workflow, logic, and outputs strictly follow the structure and explanation shown in the reference **PPT**, and this README is written as if the presenter is explaining each slide step-by-step.

The project focuses not only on forecasting stock prices, but also on **understanding why returns change** by linking them to macroeconomic factors.


## Motivation
Stock prices are influenced by multiple forces beyond historical prices, including:
- Market-wide movements
- Economic conditions
- External shocks and events

This project demonstrates:
- How Twitter stock behaves over time
- How future prices can be forecasted using ARIMA
- How APT explains abnormal returns using economic factors

## Datasets Used

### 1. Twitter Stock Price Dataset
Historical daily stock price data for Twitter.

**Key columns:**
- Date
- Open
- High
- Low
- Close
- Volume

Used for:
- Time series analysis
- Return calculation
- Forecasting
- Event detection


### 2. Financial Market Dataset (`financials.csv`)
Acts as a **market index proxy** for the APT model.

Used for:
- Expected return calculation
- Comparison with actual returns
- Identifying abnormal performance


### 3. Macroeconomic Dataset (`US_macroeconomics.csv`)
Contains U.S. macroeconomic indicators used as **APT risk factors**.

**Examples:**
- CPI
- Unemployment Rate
- Interest Rates
- Consumption and savings indicators

These variables form the **factor loading matrix**.


## Project Workflow (PPT-Aligned Explanation)

## 1. Data Loading and Preprocessing
All datasets are loaded and cleaned:
- Date columns converted to datetime
- Missing values inspected
- Time series consistency ensured

This prepares the data for analysis.


## 2. Exploratory Data Analysis (EDA)
Initial inspection includes:
- Dataset structure
- Missing values
- Shape and data types

This matches the early slides of the PPT.


## 3. Daily Return Calculation
Daily returns are computed using:

Daily Return = (Close_t − Close_{t−1}) / Close_{t−1}

Returns are essential because:
- APT models returns, not prices
- Returns normalize scale across time


## 4. Moving Average Analysis
A **30-day moving average** is calculated and plotted.

Purpose:
- Smooth short-term noise
- Highlight long-term trends
- Match the technical analysis shown in the PPT


## 5. Time Series Decomposition
The closing price series is decomposed into:
- Trend
- Seasonality
- Residuals

This explains long-term movement, repeating patterns, and random noise.

## 6. ARIMA Forecasting
Auto-ARIMA is used to:
- Select optimal (p, d, q) parameters
- Minimize AIC
- Forecast future prices

Outputs include:
- Model summary
- Forecast visualization
- Diagnostic statistics


## 7. Arbitrage Pricing Theory (APT)
APT assumes stock returns depend on multiple risk factors.

APT Equation:
Expected Return = Risk-Free Rate + Σ(Factor Loading × Factor Return)

In this project:
- Market returns are used as a proxy
- Macroeconomic variables act as risk factors


## 8. Factor Loading Matrix
A factor loading matrix is created to quantify:
- The influence of each macroeconomic variable on Twitter returns

This step prepares the data for identifying significant factors.


## 9. Identifying Significant Factors
A factor is considered **significant** if:

|Factor Loading| > 0.5

This threshold is used exactly as shown in the PPT.

**Output:**
- A list of significant macroeconomic factors affecting Twitter stock


## 10. Expected vs Actual Returns
Using the APT model:
- Expected returns are calculated
- Actual returns are compared
- Return differences are computed

Return Difference = Actual Return − Expected Return

Large differences indicate abnormal behavior.


## 11. Extreme Return Dates
The project identifies:
- Top 5 highest positive return differences
- Top 5 most negative return differences

These dates represent major market reactions.


## 12. Event Interpretation (Simulated News)
For each extreme return date:
- A simulated news headline is generated
- This mirrors the PPT explanation

Note: No live news APIs are used; placeholders are intentional.


## Project Structure

Twitter-Stock-Price-Analysis-APT/
- Twitter_Stock_Price_Analysis_using_APT.ipynb
- README.md
- requirements.txt
- data/
  - twitter-stocks.csv
  - financials.csv
  - US_macroeconomics.csv


## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels
- pmdarima
- Scikit-learn
- Jupyter Notebook


## Key Insights
- Twitter stock shows strong trend behavior
- ARIMA provides a reasonable forecast baseline
- Multiple macroeconomic indicators significantly influence returns
- APT effectively identifies abnormal return periods
- Extreme return dates align with major market movements



