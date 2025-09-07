# Customer Churn Prediction

This project focuses on predicting customer churn using a logistic regression model. By identifying customers likely to leave, businesses can take proactive steps to improve retention, enhance satisfaction, and reduce revenue loss.

## Table of Contents
* [Introduction](#introduction)
* [Dataset](#dataset)
* [Analysis](#analysis)
* [Data Cleaning & Preprocessing](#data-cleaning--preprocessing)
* [Feature Engineering](#feature-engineering)
* [Model Development](#model-development)
* [Model Evaluation](#model-evaluation)
* [Interpretation & Business Impact](#interpretation--business-impact)

---

## Introduction
Customer churn—the rate at which customers stop using a company's services—is one of the most significant drivers of revenue loss in subscription and service-based industries. Retaining existing customers is often more cost-effective than acquiring new ones, making churn prediction a critical component of customer relationship management.

This project builds a machine learning pipeline to predict churn based on customer demographics, service usage, payment behavior, and engagement history. Beyond prediction, the insights from this model can guide strategic interventions such as personalized offers, improved customer support, and better product bundling.

### Objectives
* Build a reliable machine learning model to predict customer churn
* Identify key factors that influence churn behavior
* Translate predictive insights into practical retention strategies

---

## Dataset
* **Source**: Teleco credit card transactions (2023)
* **Size**: 7,043 observations, 33 variables (\~550,000 anonymized records)
* **Features include**: customer demographics, contract type, payment method, internet and streaming services, tenure, and churn indicators

Key observations:
* Only the `Churn Reason` column contains missing values (5,174 missing)
* 9 numerical and 24 categorical features

---

## Analysis
The dataset revealed patterns that are highly relevant to retention strategies:
* **Contract Type**: Most customers are on month-to-month plans, indicating flexibility is important but also increases churn risk.
* **Payment Behavior**: Electronic checks are the most used payment method, highlighting a digitally-inclined customer base.
* **High Churn Regions**: Los Angeles and San Francisco showed higher churn concentrations, suggesting regional differences in service satisfaction or competition.
* **Low Adoption Services**: Tech support, device protection, and streaming add-ons were underutilized, indicating potential areas for upselling or improved awareness.

---

## Data Cleaning & Preprocessing
* Missing values in `Churn Reason` were handled appropriately to avoid bias.
* Categorical variables were encoded using standard techniques.
* Key numerical columns (`Monthly Charge`, `Total Charges`) were standardized to ensure consistency in model training.

---

## Feature Engineering
* Created `Num_Additional_Services` (sum of optional services subscribed)
* Standardized key variables for better model stability

---

## Model Development
* **Algorithm**: Logistic Regression
* **Purpose**: Chosen for interpretability and ability to provide clear insights into feature importance
* **Train-Test Split**: Ensured unbiased evaluation

---

## Model Evaluation
The model was evaluated using multiple metrics to capture different dimensions of performance:

* **Accuracy: 0.84**
  * Meaning: The model correctly predicts churn vs. non-churn 84% of the time.
  * Business relevance: Indicates strong overall reliability but can be misleading for imbalanced datasets (where non-churners dominate).

* **Precision: 0.76**
  * Meaning: Of all customers the model predicted as churners, 76% actually churned.
  * Business relevance: High precision reduces wasted retention efforts on customers who would not have left anyway, optimizing marketing costs.

* **Recall: 0.67**
  * Meaning: The model correctly identified 67% of actual churners.
  * Business relevance: Reflects how many at-risk customers the company can realistically save. Higher recall means fewer lost opportunities, but may come at the cost of precision.

* **F1 Score: 0.71**
  * Meaning: Harmonic mean of precision and recall, balancing the trade-off between catching more churners (recall) and avoiding false alarms (precision).
  * Business relevance: Useful when both missing churners and targeting the wrong customers have real costs.

* **ROC AUC: 0.93**
  * Meaning: Measures the model’s ability to distinguish between churners and non-churners across all thresholds. A score of 0.93 is considered excellent.
  * Business relevance: Indicates the model is highly capable of ranking customers by churn risk, making it ideal for prioritizing retention campaigns.

Confusion Matrix:

```
[[923  86]   → True Negatives & False Positives
 [134 266]] → False Negatives & True Positives
```

* True Negatives (923): Correctly identified non-churners
* False Positives (86): Customers incorrectly flagged as churners (may lead to unnecessary retention offers)
* False Negatives (134): Churners missed by the model (lost retention opportunity)
* True Positives (266): Correctly identified churners (ideal intervention targets)

---

## Interpretation & Business Impact
This model provides actionable intelligence rather than just predictions:
* **Targeted Retention Campaigns**: Focuses efforts on customers most likely to leave, rather than wasting resources on the entire base.
* **Customer Segmentation**: Identifies which regions, contract types, or payment preferences are most associated with churn.
* **Revenue Preservation**: Preventing churn among high-value customers has a disproportionate positive impact on long-term revenue.
* **Operational Strategy**: Insights on why customers churn (e.g., poor support, competitor offers) inform broader business improvements.

By deploying this model, the business can move from reactive to proactive retention—saving costs on unnecessary campaigns and maximizing the return on retention investments.
