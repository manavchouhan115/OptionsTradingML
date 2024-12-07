
# Exploring Options Market using Machine Learning

## Overview

This project focuses on **Options Price Prediction** and **Market Direction Analysis** using historical data and machine learning techniques. By leveraging feature engineering and predictive modeling, we aim to:

- Predict accurate prices for call and put options.
- Analyze market direction (bullish, bearish, or neutral) to assist in trading decisions.
- Enhance model explainability by identifying key features influencing predictions.

---

## Objectives

1. **Options Price Prediction**  
   Accurately predict call and put options prices using historical data and engineered features.
   
2. **Market Direction Analysis**  
   Predict weekly market trends to help traders make informed decisions.
   
3. **Explainability**  
   Provide feature importance insights to enhance model interpretability using SHAP values.

---

## Dataset

- **Source**: [Tesla Options Chains (2019-2022)](https://www.kaggle.com/datasets/kylegraupe/tsla-daily-eod-options-quotes-2019-2022)
- **Key Features**:  
  - Current call and put prices  
  - Expiration dates  
  - Implied volatility  
  - Greeks (e.g., delta, gamma)  
- **Size**: 2.64M rows (~1GB)

---

## Approach

### **Feature Engineering**
- **Moneyness**: Measures the profitability of options.  
- **Days to Expiration (DTE)**: Converted to seconds for precise time decay analysis.  
- **Vega-Theta Ratio**: Captures the balance between volatility sensitivity and time decay.  
- **Delta-Gamma Interaction**: Accounts for nonlinear price changes.  
- **Historical Volatility**: Reflects asset risk using 30-day rolling standard deviation.  
- **Moving Averages**: Includes 5-day and 20-day trends.

### **Data Filtering**
- Options with maturity <1 year and moneyness <1.7.  
- Premium >1 to ensure significant market demand.  
- Applied theoretical pricing bounds for validation.

### **Models**
- **Price Prediction**: Gradient Boosting achieved the best RMSE (16.90).  
- **Market Direction**: Random Forest Classifier and XGBoost Classifier with ~89% accuracy.

---

## Results

### **Options Price Prediction**
- Gradient Boosting showed superior accuracy in predicting call and put premiums.  

### **Market Direction Analysis**
- High recall for bullish trends and consistent accuracy for bearish trends.  
- SHAP values highlighted key contributors to predictions.

---

## Lessons Learned

- **Challenges**:  
  - Processing large datasets  
  - Managing missing data  
  - Selecting impactful features  
- **Insights**:  
  - Domain-specific features like moneyness significantly improved model accuracy.  
  - SHAP analysis clarified the influence of features, aiding interpretability.

---

## Authors

- **Manav Chouhan**  
- **Amey Shimpi**  
