# HR-Employee-Attrition-Modeling

A data-driven project designed to understand the key drivers of employee turnover, build a predictive model for attrition, quantify causal effects of different HR interventions, and generate actionable, cost-saving recommendations for HR leadership.

---

## 1. Project Overview

Employee attrition represents a significant financial and operational risk to organizations. This project provides:

* A full exploratory data analysis of HR characteristics and turnover patterns
* Hypothesis-driven statistical investigation
* Machine learning models that predict attrition with interpretability
* SHAP-based driver analysis
* Causal inference (Propensity Score Matching) to estimate the impact of potential HR interventions
* A cost-impact framework for HR policy decision-making

---

## 2. Repository Structure

```
├── data/
|   └── WA_Fn-UseC_-HR-Employee-Attrition.csv                     # Raw or processed dataset(s)
├── notebooks/
│   └── hr_attrition_analysis.ipynb  # Main analysis notebook
├── README.md                 # Project documentation
```

---

## 3. Key Questions Addressed

1. **Which factors contribute most to employee turnover?**
2. **Can we accurately predict which employees are at high risk of leaving?**
3. **How do specific HR interventions (training, workload adjustments, income changes) influence attrition?**
4. **What is the estimated financial impact of reducing attrition?**

---

## 4. Exploratory Data Analysis (EDA)

The notebook includes an in-depth EDA covering:

* Attrition distribution
* Patterns by age, gender, department, education, and seniority
* Workload indicators (overtime, working hours)
* Compensation patterns
* Training and development metrics
* Tenure and internal mobility

---

## 5. Hypotheses Tested

```
H1: Employees who work overtime are more likely to leave.
H2: Employees with fewer years at the company have higher attrition risk.
H3: Monthly income significantly influences attrition probability.
H4: Employees who receive more training are less likely to leave.
```

Each hypothesis is tested using statistical tests, cross-tabulations, and visual diagnostics.

---

## 6. Machine Learning Model

A prediction pipeline was built using:

* Feature preprocessing (scaling, encoding)
* Train/validation/test split
* Stratified K-Fold cross-validation
* Model: RandomForestClassifier (tuned via Optuna)

**Model outputs include:**

* ROC-AUC and Accuracy metrics
* Feature importance
* Classification report

---

## 7. Model Interpretability: SHAP

SHAP values are used to understand:

* **Global feature importance**: which variables drive attrition across the dataset
* **Local explanations**: why the model predicts each individual employee’s attrition risk
* **Dependence plots**: interaction effects (e.g., income × overtime)

This section allows HR teams to interpret the model transparently.

---

## 8. Causal Inference and Impact Estimation

Machine learning alone does not determine "what would happen if an intervention was applied".
To estimate intervention impact, we apply:

### Step 1: Propensity Score Matching (PSM)

PSM is used to create treatment and control groups with similar characteristics.
Interventions assessed include:

* Additional training
* Salary adjustments
* Reduced overtime
* Internal mobility opportunities

### Step 2: Intervention Recommendation Engine

For each employee, the engine estimates:

* Expected change in attrition probability after intervention
* Probability uplift
* Cost-effectiveness of the intervention

**Business impact formula:**

```
Total Savings = (Attritions Prevented) × (Replacement Cost per Employee)
```

---

## 9. Technologies Used

* Python 3.x
* pandas, numpy
* scikit-learn
* optuna
* shap
* matplotlib, seaborn
* statsmodels (for inference)

---


## 10. Results Summary

* Identified key attrition drivers (overtime, tenure, income, job role).
* Built a robust predictive model with strong classification performance.
* Demonstrated which HR interventions are most cost-effective.
* Provided a framework for proactive employee retention strategy.

---

## 11. Future Work

* Extend to survival analysis (time-to-attrition modeling)
* Build interactive dashboards for HR teams (Streamlit/Power BI)
* Evaluate additional interventions using causal forests
* Integrate with internal HRIS systems for real-time risk scoring

---

If you would like, I can also:

* Format this as a **GitHub-ready Markdown file** with badges and table of contents
* Add **visuals** or an ASCII architecture diagram
* Build a **requirements.txt** or **conda environment file**
* Generate a **project logo or banner**

Let me know what you want to enhance next.
