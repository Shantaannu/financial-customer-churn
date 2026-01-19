# Financial Customer Churn Analysis

## 📌 Problem Statement
Subscription-based financial services face significant revenue loss due to customer churn. Retaining existing customers is often more cost-effective than acquiring new ones, making early churn identification critical.

## 🎯 Objective
The objective of this project is to:
- Predict customers who are likely to churn **in advance**
- Use historical usage and account-level data to build predictive models
- Identify key churn-driving factors
- Propose **data-driven, actionable retention strategies**
- Reduce customer attrition and associated revenue loss

## 📊 Dataset Overview
The dataset includes:
- Customer demographic and account information  
- Subscription tenure and plan details  
- Transaction and service usage behavior  
- Engagement and inactivity indicators  

(Target variable: `Churn`)

## 🧠 Approach
1. **Business Understanding**
   - Defined churn and business impact
   - Identified cost of false positives vs false negatives

2. **Exploratory Data Analysis (EDA)**
   - Churn distribution analysis
   - Feature relationships with churn
   - Behavioral pattern identification

3. **Feature Engineering**
   - Tenure-based features
   - Usage trend metrics
   - Activity frequency and inactivity gaps

4. **Modeling**
   - Baseline model: Logistic Regression
   - Tree-based models: Random Forest / Gradient Boosting
   - Model comparison using business-relevant metrics

5. **Evaluation**
   - Precision, Recall, F1-score
   - ROC-AUC
   - Focus on **Recall for churners**

6. **Interpretation & Insights**
   - Feature importance analysis
   - Risk segmentation of customers

7. **Retention Strategy Design**
   - Strategy recommendations tied directly to churn drivers

## 🤖 Models Used
- Logistic Regression
- Random Forest
- XGBoost (if applicable)

## 📈 Key Insights
- Customers with declining usage over recent periods show significantly higher churn probability
- Short-tenure customers are more sensitive to poor early engagement
- Inactivity duration is a stronger churn indicator than total usage volume

## 🛠️ Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook

## 🚀 Business Impact
This project demonstrates how predictive analytics can be used to proactively identify high-risk customers and support targeted retention efforts, ultimately reducing revenue loss.


│
├── data/
│ ├── raw/ # original dataset (unchanged)
│ └── processed/ # model-ready datasets
│
├── notebooks/
│ ├── 01_business_understanding.ipynb
│ ├── 02_data_understanding.ipynb
│ ├── 03_eda.ipynb
│ ├── 04_feature_engineering.ipynb
│ ├── 05_modeling.ipynb
│ └── 06_evaluation_and_insights.ipynb
│
├── src/ # reusable preprocessing and modeling logic
├── outputs/ # trained models and artifacts
└── README.md
