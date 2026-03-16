# PowerCo Customer Churn Prediction

> **Real-world ML analysis predicting customer churn for a European energy provider using 50+ engineered features and XGBoost**

##  Table of Contents
- [Overview](#overview)
- [Key Findings](#key-findings)
- [Methodology](#methodology)
- [Model Performance](#model-performance)
- [Technical Stack](#technical-stack)
- [Getting Started](#getting-started)

---

##  Overview

Advanced data science analysis for **PowerCo** using real-world dataset of **10,000+ customers** with 12-month transaction history. Engineered 50+ predictive features across price dynamics, profitability, tenure, and contract signals. Trained and compared three ML algorithms (Random Forest, XGBoost, Gradient Boosting) to identify at-risk customers.

**Key Finding:** Customer profitability (5.1%) & segmentation (9.0%) are primary churn drivers—not price sensitivity (2.4%)

## 🎯 Business Problem

PowerCo initially hypothesized price sensitivity as the primary churn driver. This project validates that hypothesis using data:
- **Contract terms** (tenure, renewal timing)
- **Customer profitability** (margin per customer)
- **Pricing patterns** (volatility, rate changes)
- **Geographic segmentation** (origin, channel)

Result: Price hypothesis **partially rejected** in favor of profitability-driven insights.

##  Model Performance

![Executive Summary](imgs/executive_sumary.png)

**Best Model: XGBoost**
- **Test ROC-AUC:** 0.677 | **Precision:** 95.7% | **Recall:** 6.0%
- **Feature Importance Top 3:**
  1. Net margin on electricity (5.1%)
  2. Customer geographic origin (9.0%)
  3. Price volatility (2.4%)



---

##  Methodology

### Feature Engineering (50+ Features)
- **Price Dynamics (14):** Monthly deltas, volatility, trend slopes
- **Tenure Signals (5):** Months active, contract end date, modification history
- **Consumption Patterns (6):** Log-space ratios, forecast deviations, usage trends
- **Financial Metrics (5):** Profitability scores, customer lifetime value, cost per kWh
- **Contract Signals (6):** Stability scores, renewal indicators, change flags

*Technical Note:* All skewed variables transformed via log-space arithmetic to prevent extreme outliers.

![Log Transformation Process](imgs/log_trans.png)

### Model Comparison

| Model | CV ROC-AUC | Test ROC-AUC | Precision | Recall |
|-------|-----------|-------------|-----------|--------|
| Random Forest | 0.7006 | 0.6678 | 90.91% | 2.73% |
| **XGBoost** | **0.7133** | **0.6773** ✅ | **95.65%** | **6.01%** |
| Gradient Boosting | 0.7081 | 0.6760 | 100% | 1.91% |

---

## 🔍 Key Findings

1. **Profitability > Price:** Low-margin customers churn at higher rates
2. **Segmentation Matters:** Geographic origin + sales channel = 9% importance
3. **Price Not Primary:** Price volatility ranks #3, contradicting initial hypothesis

---

##  Technical Stack

**Languages & Libraries:**
- Python 3.12.3 | Pandas 3.0.1 | NumPy 2.4.3
- Scikit-learn 1.8.0 | XGBoost | GridSearchCV
- Matplotlib 3.10.8 | Seaborn 0.13.2

**Data Pipeline:**
Raw Data → Cleaning → Feature Engineering (50+) → Log Transformation → Train/Test Split → GridSearchCV Tuning → Model Evaluation


---

##  Getting Started

### Clone & Setup
```bash
git clone https://github.com/kpatc/PowerCo-Churn-Prediction-BCG.git
cd "PowerCo Churn Prediction "
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Run Analysis
```bash
# EDA
jupyter notebook eda/eda_analysis.ipynb

# Features
jupyter notebook feature_engineering/feature_engineering_v2.ipynb

# Models
jupyter notebook modeling/modeling.ipynb
```

---

##  Key Learnings

- **Log-space arithmetic:** Prevented extreme outliers in skewed data
- **Class imbalance:** 90% no-churn required ROC-AUC focus over accuracy
- **Feature importance:** Profitability > Segmentation >> Price

---
