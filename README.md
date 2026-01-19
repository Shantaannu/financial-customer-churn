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

