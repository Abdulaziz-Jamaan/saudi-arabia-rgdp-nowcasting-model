# Saudi Arabia Real GDP Nowcasting: ARIMAX Model

A quantitative nowcasting model designed to estimate the Real Gross Domestic Product (rGDP) of Saudi Arabia using an Autoregressive Integrated Moving Average with Exogenous Variables (ARIMAX) approach.

## 📌 Project Overview
This project bridges the reporting lag inherent in official quarterly GDP releases by providing a data-driven nowcast for Q1 2026. By tracking high-frequency macroeconomic and monetary indicators, the model accurately predicts the current quarter's economic trajectory[cite: 2]. 

## 📊 Data & Indicators
The model synthesizes multiple leading and coincident economic indicators to capture non-oil and oil sector dynamics[cite: 2]:
*   **Target Variable:** Real GDP[cite: 2]
*   **Exogenous Predictors:** 
    *   Purchasing Managers' Index (PMI)[cite: 2]
    *   Oil Price[cite: 2]
    *   Oil Production[cite: 2]
    *   Money Supply (M3)[cite: 2]
    *   Point of Sales (POS) transactions[cite: 2]
*   **Data Sources:** General Authority for Statistics (GASTAT), Saudi Central Bank (SAMA), Riyadh Bank, Investing.com, and OPEC[cite: 2].

## ⚙️ Methodology
The econometric modeling pipeline prioritizes strict stationarity and optimized lag selection:
1.  **Diagnostic Testing:** Augmented Dickey-Fuller (ADF) tests were conducted to check for unit roots across all series[cite: 2].
2.  **Data Transformation:** Non-stationary variables (GDP, PMI, Oil Price, M3, POS) were transformed using log-differencing to achieve stationarity, while Oil Production was maintained in levels[cite: 2].
3.  **Model Selection:** An algorithmic grid search was deployed to minimize the Akaike Information Criterion (AIC), identifying **ARIMAX(2, 0, 0)** as the optimal architectural fit for the data[cite: 2].
4.  **Estimation:** The model was estimated using maximum likelihood via `statsmodels.tsa.SARIMAX`[cite: 2].

## 🚀 Key Results (Q1 2026 Nowcast)
Applying the Q1 2026 exogenous data inputs to the trained ARIMAX model yields the following predictions[cite: 2]:
*   **Predicted Real GDP:** 1,242,146 Million SAR[cite: 2]
*   **Implied YoY Growth:** 2.91%[cite: 2]

## 🗂️ Tech Stack & Requirements
*   `pandas` & `numpy` (Data ingestion and transformation)[cite: 2]
*   `statsmodels` (ADF testing and ARIMAX/SARIMAX implementation)[cite: 2]
*   `matplotlib` & `seaborn` (Time-series visualization)[cite: 2]
*   `scipy`[cite: 2]

## 🛠️ How to Run
1. Ensure the `Model.xlsx` data file is located in the root directory[cite: 2].
2. Run the Jupyter Notebook sequentially to execute the data prep, transformation, ADF testing, grid search optimization, and final forecasting outputs[cite: 2].
