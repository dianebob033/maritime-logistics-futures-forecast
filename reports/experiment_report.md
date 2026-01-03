# Experiment Report  
**Project**: Maritime Logistics–Driven Forecasting of Iron Ore Futures  
**Author**: [Your Name]  
**Date**: [YYYY-MM-DD]

---

## 1. Introduction

Global commodity markets are deeply intertwined with maritime transportation systems.  
For bulk commodities such as iron ore, maritime logistics constraints—including vessel availability, freight rates, and trade flow disruptions—play a critical role in shaping market expectations and price dynamics.

This project explores whether **maritime logistics indicators** can improve the prediction of **iron ore futures volatility**, compared to models that rely exclusively on historical financial data.

The study is framed as a **predictive modeling problem**, focusing on incremental forecasting performance rather than causal inference or trading strategy design.

---

## 2. Research Question and Hypothesis

### 2.1 Research Question

Can global maritime logistics indicators provide additional predictive power for iron ore futures volatility beyond traditional financial features?

### 2.2 Hypothesis

Models augmented with maritime logistics signals (e.g., freight rate indices and trade flow proxies) will outperform financial-only baseline models in forecasting short-horizon realized volatility of iron ore futures.

---

## 3. Prediction Task Definition

### 3.1 Target Variable

- **Target**: 5-day realized volatility of iron ore futures
- **Definition**:  
  Realized volatility is computed as the rolling standard deviation of daily log returns over the next 5 trading days.

### 3.2 Forecasting Setup

- **Task type**: Regression
- **Forecast horizon**: 5 trading days ahead
- **Evaluation scheme**: Rolling-window out-of-sample evaluation

---

## 4. Data Description

### 4.1 Financial Market Data

- Daily iron ore futures prices
- Derived features include:
  - Log returns
  - Rolling historical volatility
  - Momentum indicators

These features constitute the **financial-only baseline**.

---

### 4.2 Maritime Logistics Indicators

Logistics-related features are grouped into two categories:

#### 4.2.1 Freight Rate Indicators

- Baltic Dry Index (BDI)
- (Optional) Sub-indices by vessel class

These indices reflect real-time supply–demand conditions in the dry bulk shipping market.

#### 4.2.2 Trade Flow Proxies

- Aggregate iron ore import/export statistics
- Low-frequency trade data is aligned to the forecasting timeline using conservative availability assumptions.

---

### 4.3 Data Availability and Look-Ahead Bias

To avoid information leakage:
- Each feature is associated with an explicit **availability date**
- Only information observable at the forecast date is used during training and evaluation

---

## 5. Feature Engineering

### 5.1 Financial Features

- Lagged returns
- Rolling volatility measures
- Trend and momentum indicators

### 5.2 Logistics Features

- Level and change of freight indices
- Lagged logistics indicators
- Interaction terms between logistics and financial variables (optional)

All features are standardized within the training window to preserve temporal integrity.

---

## 6. Models

### 6.1 Baseline Model

- Financial-only regression model
- Purpose: establish a reference performance benchmark

### 6.2 Logistics-Augmented Model

- Identical model architecture
- Includes maritime logistics features
- Enables controlled comparison of incremental information value

### 6.3 Model Choice Rationale

Initial experiments prioritize:
- Interpretability
- Robustness under limited data
- Ease of reproducibility

More complex architectures are deferred to future work.

---

## 7. Evaluation Methodology

### 7.1 Metrics

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

### 7.2 Validation Strategy

- Rolling-window evaluation
- Fixed training window length
- Non-overlapping test periods

This setup mimics real-world forecasting constraints.

---

## 8. Experimental Results

### 8.1 Overall Performance

| Model | Features Used | MAE | RMSE |
|------|--------------|-----|------|
| Baseline | Financial only | TBD | TBD |
| Enhanced | Financial + Logistics | TBD | TBD |

---

### 8.2 Relative Performance Gain

- Percentage improvement over baseline
- Performance stability across time periods

---

## 9. Error Analysis

Qualitative and quantitative error analysis includes:
- Periods of large forecast errors
- Market regimes with degraded model performance
- Sensitivity to logistics feature availability

Representative examples are discussed to highlight model limitations.

---

## 10. Discussion

### 10.1 Key Findings

- Summary of predictive gains (or lack thereof)
- Contribution of logistics indicators to performance

### 10.2 Interpretation

Results are interpreted in terms of **predictive usefulness**, not causal claims or trading profitability.

---

## 11. Limitations

- Potential noise and delays in logistics indicators
- Limited availability of high-frequency trade data
- Simplified volatility definition

---

## 12. Future Work

- Incorporation of vessel-level AIS data
- Multi-horizon forecasting
- Extension to additional bulk commodities
- Regime-aware or hybrid modeling approaches

---

## 13. Conclusion

This study demonstrates a structured approach to integrating maritime logistics information into commodity futures forecasting models, highlighting both the potential benefits and practical challenges of logistics-aware financial prediction.

---

## 14. Disclaimer

This work is for research and educational purposes only and does not constitute investment advice.
