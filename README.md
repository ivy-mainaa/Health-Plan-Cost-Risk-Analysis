# Health Plan Cost Risk Analysis
Predicting High-Cost Patients Using Demographic & Behavioral Data.

This project analyzes U.S. medical insurance records to understand the drivers of medical spending and predict high-cost patients, a critical use case for payer organizations and health plans.

The analysis is split into two notebooks:

**1. 01_Health_Plan_EDA.ipynb - Exploratory Data Analysis**

**2. 02_High_Cost_Risk_Model.ipynb - Predictive Modeling**

---

## Business Problem
Health plans must manage risk while maintaining care quality.
Identifying members likely to incur high medical costs helps with:
- Early outreach and care management
- Budget forecasting
- Fair pricing and risk adjustment
- Targeted member education

This project demonstrates how statistical analysis and machine learning can support those goals.

---

## Dataset
Source: Kaggle – Medical Cost Personal Dataset
https://www.kaggle.com/datasets/mirichoi0218/insurance

**Observations:** 1,337

**Target:** Annual medical charges

**Engineering Label:**

- high_cost = 1 if annual charges > 75th percentile
- high_cost = 0 otherwise

---

## Notebook 1 — Key EDA Insights
Factors associated with higher spending:
- Smokers spend roughly 3.7x more than non-smokers.
- Charges increase sharply with age (especially after 45).
- Higher BMI correlates with higher spending (obese group is the most expensive).
- Regional impact exists but is weaker (Southeast is highest).
- Cost distribution is heavily right-skewed (few very high spenders).

### Business Takeaways:
- Smoking cessation could reduce claims cost.
- Preventive care for obesity and chronic illness has strong ROI.
- Age bands help segment risk for pricing and outreach.
- Region differences may matter with additional contextual data.

  ---

## Notebook 2 — Predictive Modeling
Goal: Predict which members will be high-cost (top 25% of total charges).

Models Trained:
- Logistic Regression
- Random Forest Classifier

### Random Forest
Model Performance (Test Set):
- ROC-AUC: approximately 0.92
- Recall (high-cost): approximately 82%
- Accuracy: approximately 96%
  
Feature Importance (ranking):
1. Smoking status
2. BMI
3. Age
4. Number of children
5. Sex and region (smaller influence)

**Interpretation:**
High-cost risk is primarily driven by lifestyle and health behavior factors.

---

## Tech Stack
- Python
- pandas, numpy, matplotlib, seaborn
- scikit-learn
- Jupyter Notebook
- Git and GitHub
---  

## Repository Structure

```
Health-Plan-Cost-Risk-Analysis/
│
├── data/
│   └── insurance.csv
├── notebooks/
│   ├── 01_Health_Plan_EDA.ipynb
│   └── 02_High_Cost_Risk_Model.ipynb
├── README.md
└── .gitignore
```

---

## Next Steps (Future Enhancements)
- Add comorbidity features (hypertension, diabetes, etc.)
- Test Gradient Boosting / XGBoost models
- Build a Power BI dashboard for business users
- Deploy a lightweight scoring API
