# Volatility Forecasting of NVDA using GARCH Family Models

## 🔹 Introduction
This project analyzes the **volatility of NVIDIA (NVDA) stock** using **GARCH family models**.  
Financial time series often exhibit **volatility clustering**, **fat tails**, and sometimes **leverage effects**, making GARCH-type models a natural choice for volatility forecasting.  

The project compares multiple GARCH variants:
- **GARCH(1,1)**
- **EGARCH(1,1)**
- **TGARCH(1,1)**
- **IGARCH(1,1)**  

with two distributions:
- **Student-t**
- **Generalized Error Distribution (GED)**  

---

## 🔹 Dataset
- **Source**: Yahoo Finance (`yfinance` API)  
- **Asset**: NVIDIA (NVDA) daily adjusted close prices  
- **Period**:  
  - **In-sample (training)**: 2015-01-01 → 2024-12-31  
  - **Out-of-sample (testing)**: 2025-01-01 → 2025-10-02

---

## 🔹 Methodology
1. **Exploratory Data Analysis**
   - Checked for autocorrelation and ARCH effects (ADF, Ljung-Box, ARCH-LM test).
   - Confirmed volatility clustering and fat tails in NVDA returns.

2. **Model Estimation**
   - Fitted GARCH, EGARCH, TGARCH, IGARCH under both **t** and **GED** distributions.

3. **Model Evaluation**
   - Generated **out-of-sample volatility forecasts** (2025).
   - Compared models using **RMSE** (variance & volatility).

---

## 🔹 Results
| Model              | RMSE Variance | RMSE Volatility |
|--------------------|---------------|-----------------|
| EGARCH(1,1)-GED    | 34.66         | **2.49** |
| EGARCH(1,1)-t      | 34.69         | 2.53 |
| GARCH(1,1)-GED     | 34.90         | 2.54 |
| TGARCH(1,1)-GED    | 34.99         | 2.58 |
| GARCH(1,1)-t       | 34.98         | 2.59 |
| IGARCH(1,1)-GED    | 34.86         | 2.60 |
| IGARCH(1,1)-t      | 34.86         | 2.60 |
| TGARCH(1,1)-t      | 35.09         | 2.63 |

✅ **Best model**: **EGARCH(1,1)-GED** → lowest RMSE (volatility ~2.49% per day).  

---

## 🔹 Conclusion
- NVDA returns exhibit **volatility clustering, fat tails, and some leverage effect**.  
- **EGARCH-GED** outperformed other models in volatility forecasting.  
- The framework can be applied to **portfolio risk management, Value-at-Risk (VaR), option pricing, and trading strategies**.  

---

## 🔹 Executive Summary
This project analyzes the volatility of **NVIDIA (NVDA)** stock using **GARCH family models** (GARCH, EGARCH, TGARCH, IGARCH) with **Student-t** and **GED** distributions.  
We found strong evidence of **volatility clustering, fat tails, and leverage effects** in NVDA returns.  
Among all models, **EGARCH(1,1)-GED** provided the best out-of-sample forecast performance (lowest RMSE).  
The forecasting framework developed here can be directly applied to **portfolio risk management, VaR, and option pricing** in practice.  

---
