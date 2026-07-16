# Churn_Study

## 📖 Overview
This repository contains a comprehensive data science case study focused on predicting customer churn. By analyzing customer behavior, product engagement, and support interactions, this project identifies at-risk customers and provides actionable business strategies to improve retention.

## 📂 Project Structure
The repository is organized into the following directories:

* **`Code/`**: Contains all Jupyter Notebooks (`.ipynb`) and Python scripts used for Exploratory Data Analysis (EDA), feature engineering, and machine learning model training.
* **`Artifacts/`**: Stores exported models, preprocessed datasets, and saved visualizations/plots.
* **`Reports/`**: Contains the final exported case study summaries, presentations, and HTML versions of the notebooks.

## 🔍 Key Insights from Exploratory Data Analysis (EDA)
1. **Product Engagement**: At-risk customers are distinctly characterized by lower `avg_monthly_product_usage` and a significantly higher number of `last_login_days_ago`.
2. **Product Adoption**: Customers flagged as at-risk consistently have a lower `num_analyzers_installed`, indicating poor product integration into their daily workflows.
3. **The Support Ticket Anomaly**: Counterintuitively, at-risk customers raise *fewer* support tickets. In this context, a higher `support_ticket_count` indicates that the customer is more deeply engaged with the product, making them highly valuable and less likely to churn.

## ⚙️ Modeling Approach & Results
Given the inherent class imbalance in churn datasets, **SMOTE (Synthetic Minority Over-sampling Technique)** was applied to balance the training data.

Models evaluated included Logistic Regression, Random Forest, and Gradient Boosting.

### **🏆 Recommended Production Model: Gradient Boosting (with SMOTE)**
* **Mean CV AUC:** 0.889
* **Test ROC-AUC:** 0.794
* **Recall (Churn Class):** 0.73
* **F1-Score:** 0.71
* **Overall Accuracy:** 80%

**Why this model?** Gradient Boosting provides a strong balance of high recall and a robust ROC-AUC. In churn prediction, minimizing false negatives (failing to flag a customer who *does* churn) is critical to preventing lost revenue. This model maximizes our ability to detect true churn risks while remaining robust to noise in the data.

## 🚀 Business Recommendations
1. **Incentivize Deep Adoption:** Target at-risk customers with specialized deals or onboarding campaigns designed to encourage them to install more analyzers.
2. **Shift the Support Paradigm:** Embrace the finding that higher support needs equate to higher product engagement. Do not artificially minimize support tickets; instead, encourage product expansion.
3. **Continuous Monitoring:** Deploy automated drift detection tracking `avg_monthly_product_usage`, `last_login_days_ago`, and `num_analyzers_installed`. If distributions shift, the model requires retraining.

## 🛠️ Getting Started
To clone this repository and explore the code:
```bash
git clone [https://github.com/DD199427/Churn_Study.git](https://github.com/DD199427/Churn_Study.git)
cd Churn_Study
