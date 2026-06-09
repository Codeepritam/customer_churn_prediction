# 📉 Customer Churn Prediction

An end-to-end machine learning pipeline to predict customer churn using the IBM Telco dataset.

---

## 🔍 Overview

| Detail | Info |
|--------|------|
| **Dataset** | IBM Telco Customer Churn |
| **Records** | 7,043 customers, 21 features |
| **Target** | Churn (Yes / No) |
| **Churn Rate** | 26.5% |

---

## 🚀 Pipeline

```
EDA → Preprocessing → SMOTE → Model Training → Hyperparameter Tuning → Calibration → SHAP → Business Impact
```

---

## ⚙️ Tech Stack

- **Language:** Python
- **Models:** Logistic Regression, Random Forest, XGBoost
- **Libraries:** scikit-learn, XGBoost, Optuna, SHAP, imbalanced-learn, pandas, matplotlib, seaborn

---

## 📊 Results

| Model | ROC-AUC (5-Fold CV) |
|-------|----------------------|
| Logistic Regression | 0.8490 ± 0.0048 |
| Random Forest | 0.8317 ± 0.0078 |
| XGBoost | 0.8259 ± 0.0059 |
| **XGBoost (Optuna Tuned)** | **0.8495** |

- **Optimal Decision Threshold:** 0.69
- **Max Expected Retention Value:** $642 / month

---

## 🧠 Key Findings (SHAP)

Top features driving churn:
1. `tenure` — longer tenure = lower churn
2. `Contract_Two year` — strong retention signal
3. `InternetService_Fiber optic` — high churn risk
4. `MonthlyCharges` — higher bills → more churn

Month-to-month contracts had a **30.6% churn rate** vs **11.3%** for two-year contracts.

---

## 📁 Project Structure

```
├── customer_churn_prediction.ipynb   # Main notebook
├── WA_Fn-UseC_-Telco-Customer-Churn.csv  # Dataset
└── README.md
```

---

## ▶️ How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost optuna imbalanced-learn shap
jupyter notebook customer_churn_prediction.ipynb
```

Or open directly in [Google Colab](https://colab.research.google.com/).

---

## 📌 Business Assumptions

| Parameter | Value |
|-----------|-------|
| Avg Monthly Revenue per customer | $65 |
| Retention Offer Cost | $20 |
| Retention Success Rate | 50% |
