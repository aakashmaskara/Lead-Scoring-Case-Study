# Lead Scoring Case Study (Logistic Regression)

End-to-end **Exploratory Data Analysis (EDA)** and **logistic-regression** model to assign a lead-conversion score (0–100) for an EdTech sales funnel, helping the business prioritize high-intent leads and improve conversion efficiency.

## Introduction

This project applies EDA and lightweight modeling to a real-world **lead-scoring** problem.  
We analyze historical lead data to uncover behavior and source patterns that distinguish **converting** vs **non-converting** leads, then build a transparent model that outputs a probability/score for sales prioritization.

When a sales team evaluates leads, two risks exist:
1. Ignoring a high-intent lead → **lost revenue**
2. Spending time on low-intent leads → **wasted effort / high CAC**

Data-driven scoring helps strike the right balance.

## Business Understanding

The company (EdTech) acquires leads from multiple channels (website, chat, ads, partner sites).  
Using EDA, we examine how attributes such as **lead origin/source, web activity, communication preferences, and occupation** affect conversion likelihood.

The dataset includes binary target `Converted` indicating whether a lead became a paying customer.

## Business Objectives

Identify **drivers of conversion** and build a simple, auditable model that:
- Produces a **lead score (0–100)** for every incoming lead
- Supports a practical **cutoff** (e.g., ≥80 = “hot”) for sales prioritization
- Balances **precision/recall** to fit business capacity

## Analytical Approach

1. **Data Understanding**
   - Inspect schema, types, missingness; align with the data dictionary.

2. **Data Cleaning**
   - Drop high-null columns; impute selective missing values (e.g., “Not Provided” for categorical).
   - Consolidate sparse categories and standardize label values.

3. **Outlier & Imbalance Checks**
   - Review numeric distributions (e.g., visits/time on site) and the class balance of `Converted`.

4. **Exploratory Data Analysis**
   - Univariate, segmented univariate (by `Converted`), and bivariate comparisons.
   - Visualize behavior by **lead origin/source**, **web engagement**, **communication preferences**, **occupation**, etc.

5. **Feature Engineering**
   - One-hot encoding of key categoricals; scaling of numeric features as needed.

6. **Modeling (Logistic Regression)**
   - Variable shortlist via RFE / business logic.
   - Iterative pruning with p-values & VIF to control multicollinearity.
   - Score calibration and **cutoff selection** using ROC/PR trade-offs.

7. **Validation**
   - Report **Accuracy**, **Precision**, **Recall**, **Specificity**, **ROC AUC** on train/test.
   - Sanity-check for overfitting and business interpretability.

## Tools & Libraries

- **Python** (Jupyter Notebook)  
- **pandas**, **numpy**, **scikit-learn**, **matplotlib**, **seaborn**  
- EDA: univariate / segmented univariate / bivariate analysis

## Key Insights

From this dataset, the following signals were among the strongest (directionally):
- **Higher web engagement** → more conversions (e.g., **Total Time Spent on Website**, **Total Visits**)
- **Lead Origin: Lead Add Form** and **sources** like **Olark Chat / Welingkar** → higher propensity
- **“Do Not Email = Yes”** → negative signal
- **Occupation** buckets (e.g., Working Professional vs Student/Unemployed) show distinct conversion propensities

(Exact magnitudes/metrics are documented in the notebook and slides.)

## Conclusion & Business Impact

A transparent logistic-regression model can:
- Surface a **rank-ordered lead list** for the sales team
- Support an operational **hot-lead threshold** (e.g., score ≥80)
- Improve **conversion rate** and **rep productivity** while keeping the system auditable and easy to maintain

## Files in this Repository

| File Name | Description |
|------------|-------------|
| `Lead Scoring Case Study.ipynb` | Full workflow (EDA → feature engineering → model → validation) |
| `Leads.csv` | Raw lead-level dataset |
| `Leads Data Dictionary.xlsx` | Variable descriptions |
| `Lead Scoring Case Study Summary.pdf` | Written summary of approach & findings |
| `Lead Scoring Case Study_Business Presentation.pdf` | Business slides for stakeholders |

---

## Author

**Aakash Maskara**  
*M.S. Robotics & Autonomy, Drexel University*  
Data Science | Machine Learning | Quantitative Finance  

[LinkedIn](https://linkedin.com/in/aakashmaskara) • [GitHub](https://github.com/AakashMaskara)
