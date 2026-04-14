# Telconnect Customer Churn Analysis
---
<img width="1261" height="608" alt="Image" src="https://github.com/user-attachments/assets/54231281-3feb-42f0-8afb-7a0f12d2f05f" />

# TelConnect Customer Churn Prediction & Retention Optimization

## Executive Summary

TelConnect faces a **26.54% monthly churn rate**, meaning roughly 1 in 4 customers leaves each billing cycle. The current retention strategy is purely reactive — offering a $30 StreamFlix voucher only after a customer initiates cancellation — with no predictive capability to intervene earlier.

This project builds a **predictive churn model + profit-optimized retention strategy**, transforming retention from a reactive cost center into a **data-driven profit lever**.

### Key Results
- Net profit increased from **$304,052 → $359,508 (+23%)**
- Revenue recovered increased from **$326,486 → $424,515**
- XGBoost churn model achieves **AUC = 0.845, Recall = 77%**
- Proactive targeting of **2,604 high-risk customers monthly**
- Break-even proactive acceptance rate: **~4% (strategy highly robust)**

### Core Insight
> Moving from reactive vouchers → proactive + reactive tiered intervention unlocks significant incremental profit and prevents churn before cancellation intent is formed.

---

## Business Impact

This project delivers an actionable retention system for:

- **CMOs & Growth Teams** optimizing churn reduction strategy  
- **Data Science Teams** deploying predictive retention models  
- **Finance Teams** evaluating customer lifetime value efficiency  
- **Strategy Teams** allocating retention budget based on ROI  

The result is a **profit-aware churn prevention framework**, not just a classification model.

---

## Solution Overview

We developed an end-to-end churn intelligence pipeline:

- Predicts churn probability for all **7,043 customers monthly**
- Identifies drivers of churn using **SHAP explainability**
- Optimizes intervention strategy using **profit-based threshold selection**
- Simulates real-world retention economics (CLV, voucher cost, outreach cost)
- Segments customers into actionable **4-tier retention strategy**

---

## Business Problem

TelConnect currently operates reactively:

- Customers churn first → then retention offer is triggered
- No early warning system
- No prioritization of high-value customers

This project answers three core questions:

1. Who is likely to churn next month?
2. Why are they churning?
3. Which customers should we intervene on — and how?

---

## Data Overview

- **Customers**: 7,043  
- **Features**: 21 raw variables  
- **Churn rate**: 26.54%  
- **Update frequency**: Monthly snapshot  

### Feature Groups
- Demographics (gender, senior citizen, dependents)
- Account (contract type, tenure, billing method)
- Services (internet, security, support, streaming)
- Charges (monthly & total charges)

Key insight: **Contract type and tenure dominate churn behavior.**

---

## Methodology

<img width="1368" height="638" alt="Image" src="https://github.com/user-attachments/assets/e9f4bebd-ac24-4add-814a-9b0403119edd" />

### Core Stack
Python • Scikit-learn • XGBoost • SHAP • Pandas • Matplotlib • Seaborn

---

## Modeling Approach

We trained and compared multiple models:

| Model | ROC-AUC | Recall | Notes |
|------|--------|--------|------|
| Logistic Regression | 0.843 | 0.77 | Interpretable baseline |
| Random Forest | 0.838 | 0.80 | Strong ensemble model |
| **XGBoost (Selected)** | **0.845** | **0.80** | Best profit performance |

### Why XGBoost?
- Highest ROC-AUC (0.845)
- Strong recall for churn class (80%)
- Choose a 0.56 threshold for maximum net profit in simulation
- Robust handling of non-linear churn drivers

---

## Key Insights (EDA + SHAP)

- **Month-to-month contracts → strongest churn driver**
- **Early tenure (0–6 months) = highest risk period**
- **Fiber optic users churn disproportionately**
- **Lack of OnlineSecurity / TechSupport increases churn**
- **Electronic check payment = behavioral churn proxy**
- **Service depth strongly reduces churn risk**
- **High monthly charges increase churn probability**

SHAP analysis confirms:
> Contract type, tenure, and service engagement are the dominant drivers of churn behavior.

---

## Business Simulation

A profit-based simulation evaluates retention strategy using:

- CLV = MonthlyCharges × 6 months
- Proactive outreach cost = $18
- Reactive voucher cost = $30
- Acceptance rates:
  - Reactive: 40%
  - Proactive: 25%

### Outcome (Optimized Strategy)

| Metric | Current | Optimized |
|--------|--------|----------|
| Net Profit | $304,052 | $359,508 |
| Revenue | $326,486 | $424,515 |
| Total Cost | $22,434 | $65,007 |
| Customers Targeted | 0 | 2,604 |

### Key Insight
A **threshold of 0.56** maximizes profit — not accuracy or F1-score.

---

## Retention Strategy (4-Tier System)

Customers are segmented into actionable tiers:

- **Tier 1 (High risk + high value)** → proactive + voucher backup  
- **Tier 2 (High risk + lower value)** → proactive outreach only  
- **Tier 3 (Medium risk)** → monitoring + soft engagement  
- **Tier 4 (Low risk)** → no intervention  

This ensures **budget is allocated based on ROI, not uniform treatment.**

---

## Limitations

- Proactive acceptance rate is uncertain (key risk factor)
- CLV is simplified (6-month proxy)
- No causal uplift modeling (correlation ≠ causation)
- No longitudinal behavioral data (only snapshot dataset)
- No post-intervention retention tracking available

---

## Next Steps

<img width="986" height="379" alt="Image" src="https://github.com/user-attachments/assets/28fee167-e02a-4fad-ac1c-5942d4216360" />

---

## Final Takeaway

This project transforms churn analysis from:

> “Who will leave?”

to:

> “Who will leave, why, and what intervention maximizes profit?”

By combining **predictive modeling + SHAP explainability + profit simulation**, TelConnect can shift from reactive retention to **data-driven proactive customer retention strategy**.

## Full Presentation

Please find the complete project presentation below, including:
- End-to-end methodology walkthrough  
- Feature engineering & modeling pipeline  
- Business simulation & ROI analysis  
- SHAP interpretability insights  
- Final retention strategy & recommendations  

**[View Full Slide Deck](https://github.com/lin-jhe-yu/Telconnect-Customer-Churn-Analysis/blob/main/TelConnect_Customer_Churn_Analysis_Lawrence_Lin.pdf)**
