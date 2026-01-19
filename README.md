# Telecom Customer Churn Prediction — End-to-End ML Project

## Overview

Customer churn is one of the most expensive problems in the telecom industry.  
This project focuses on **predicting customer churn early** and, more importantly, **translating model outputs into actionable business decisions**.

The emphasis is not just on building a machine learning model, but on:
- framing the problem correctly,
- making defensible modeling choices,
- and aligning predictions with real retention strategies.

---

## Business Problem

Telecom companies rely on recurring subscription revenue.  
When a customer churns:
- future revenue is lost,
- acquisition costs are wasted,
- and intervention opportunities disappear.

The challenge is that churn is typically identified **after it happens**.

**Objective:**  
Predict customers who are likely to churn *before* they leave and enable proactive retention actions.

---

## Dataset

- **Source:** Telco Customer Churn dataset (public)
- **Size:** ~7,000 customers
- **Target:** `Churn` (Yes / No)

The dataset includes:
- customer demographics,
- contract and tenure information,
- service usage patterns,
- billing and payment behavior.

Although the dataset is public, it is treated as a **real-world telecom scenario** with explicit assumptions and documented limitations.

---
## Project Structure

TELECOM-CUSTOMER-CHURN/
│
├── data/
│   ├── raw/
│   │   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│   │
│   └── processed/
│       ├── X_train_scaled.csv
│       ├── X_test_scaled.csv
│       ├── y_train.csv
│       └── y_test.csv
│
├── notebooks/
│   ├── 01_business_understanding.ipynb
│   ├── 02_data_understanding.ipynb
│   ├── 03_eda.ipynb
│   ├── 04_feature_engineering.ipynb
│   ├── 05_modeling.ipynb
│   └── 06_evaluation_and_insights.ipynb
│
├── src/
│   ├── __init__.py
│   ├── config.py
│   ├── data_loader.py
│   ├── preprocessing.py
│   ├── feature_engineering.py
│   ├── modeling.py
│   ├── evaluation.py
│   └── utils.py
│
├── outputs/
│   ├── models/
│   │   └── churn_model.pkl
│   │
│   ├── figures/
│   │   ├── eda/
│   │   │   └── churn_distribution.png
│   │   └── evaluation/
│   │       ├── confusion_matrix.png
│   │       └── roc_curve.png
│   │
│   └── reports/
│       └── final_insights.md
│
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt



Each notebook has a **single responsibility** to avoid mixing business logic, data exploration, and modeling.

---

## Approach

### 1. Business-First Framing
- Defined churn as a **cost-sensitive business problem**
- Prioritized recall for churners over raw accuracy
- Explicitly documented assumptions before analysis

---

### 2. Data Understanding & Quality
- Identified and fixed data quality issues (e.g. `TotalCharges` stored as strings)
- Avoided premature imputation
- Separated data validation from exploration

---

### 3. Exploratory Data Analysis (EDA)
EDA was driven by **business questions**, not random plots:
- How does tenure affect churn?
- Do contract types influence retention?
- Are high charges associated with churn?
- Does service adoption reduce churn risk?

---

### 4. Feature Engineering
Key decisions:
- Removed non-informative identifiers
- Handled missing values using business logic
- Addressed multicollinearity between `tenure` and `TotalCharges`
- One-hot encoded categorical features
- Scaled numerical features for linear models

---

### 5. Modeling Strategy
- **Logistic Regression** used as a transparent baseline
- **Random Forest** selected as the final model due to:
  - higher recall for churners,
  - ability to capture non-linear behavior,
  - better alignment with business priorities.

Models were evaluated using:
- Recall (churn class)
- ROC-AUC
- Confusion matrix analysis

---

### 6. Threshold Optimization
The default probability threshold (0.5) was **not accepted blindly**.

- Threshold was lowered to improve churn recall
- Higher false positives were accepted intentionally
- Decision justified by retention cost considerations

This step bridges ML predictions with business reality.

---

## Key Insights

- Customers with **low tenure** are significantly more likely to churn
- **Month-to-month contracts** show the highest churn risk
- Higher **monthly charges** increase churn probability
- Customers using **fewer services** churn more often

These insights were consistent across EDA and model outputs.

---

## Business Output

Instead of raw predictions, customers are segmented into **risk tiers**:

- **High Risk:** Immediate retention action
- **Medium Risk:** Engagement and incentive campaigns
- **Low Risk:** Monitoring only

This enables targeted, cost-effective retention strategies.

---

## What This Project Does NOT Claim

- ❌ Perfect prediction
- ❌ Real-time deployment
- ❌ Causal inference

The goal is **practical, decision-oriented analytics**, not overclaiming.

---

## Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn

No unnecessary frameworks or buzzwords.
---

## Possible Next Steps

- Cost-based evaluation using retention vs churn cost
- Model deployment as a scoring service
- CRM integration for automated retention triggers
- Model monitoring and drift detection


