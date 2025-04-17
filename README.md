# 📈 Modeling and Forecasting Volatility in Financial Time Series  
**A Comparative Study of GARCH Models**

This project investigates two financial time series — **U.S. retail sales data** and **Apple Inc. stock closing prices** — to model and forecast volatility using **ARIMA** and **GARCH-based models**. Our objective is to identify the best-fitting model for each dataset and provide meaningful forecasts that account for trends, seasonality, and volatility clustering.

---

## 🧭 Summary of Key Findings

- 📊 **Retail Sales**: Seasonal volatility (e.g., 2008 recession, COVID-19) required seasonal ARIMA modeling followed by GARCH residual fitting.  
  → Best model: **ARIMA(3, 0, 3)(0, 0, 3)[12] + GARCH(1,1)** with Student-t distribution.

- 🍎 **Apple Stock**: Captured upward trend and volatility in monthly closing prices.  
  → Best model: **ARFIMA(0,2)-GARCH(1,1)** model, outperforming all ARIMA-only approaches.

- 🧪 **Model Selection**: AIC, BIC, and residual diagnostics were used to compare models. Ljung-Box p-values guided the selection of models with uncorrelated residuals.

---

## 🛠️ Technologies Used

| Component               | Tools / Libraries                                  |
|------------------------|----------------------------------------------------|
| Language               | R                                                  |
| Time Series Modeling   | `forecast`, `TSA`, `tseries`, `rugarch`, `ugarch` |
| Visualization          | `ggplot2`, `zoo`, `base R`, `acf/pacf` plotting    |
| Data Sources           | FRED (Retail Sales), Yahoo Finance (AAPL stock)    |

---

## 🔍 Methodology

### 1. **Retail Sales Time Series**
- Source: [FRED RSXFSN – Advance Monthly Retail Trade Survey](https://fred.stlouisfed.org/series/RSXFSN)
- Span: Jan 1992 to July 2024 (monthly)
- Techniques:
  - Seasonal decomposition + differencing
  - ARIMA order selection via EACF, AIC, and residual diagnostics
  - GARCH modeling of residuals with both normal and t-distributions
  - Final model: **ARIMA(3,0,3)(0,0,3)[12] + GARCH(1,1)**

### 2. **Apple Inc. (AAPL) Stock Time Series**
- Source: [Yahoo Finance](https://finance.yahoo.com/quote/AAPL/history)
- Span: Jan 2016 to May 2024 (monthly)
- Techniques:
  - ARIMA models fit to differenced log returns
  - Residual normality check using Shapiro-Wilk
  - Volatility modeled using ARFIMA-GARCH models
  - Final model: **ARFIMA(0,2)-GARCH(1,1)**

---

## 📈 Visual Outputs
- ACF/PACF plots to assess serial dependence
- QQ plots and histograms for residual diagnostics
- Ljung-Box tests for checking model adequacy
- Forecast plots with confidence intervals

---

## 📊 Real-World Relevance

- **Economics & Policy**: Forecasting retail sales assists in planning during crises like COVID-19 or economic recessions.
- **Finance & Investing**: Understanding stock volatility improves risk modeling and portfolio construction.
- **Forecasting**: Combining ARIMA and GARCH provides robust insight into both trend and variance dynamics.

---

## 👥 Authors

Brianna Cirillo • Brendan Kenny • Kimberley Maldonado • Emily Su  
MA 641: Time Series Analysis I | August 2024

---
