# Credit Risk PD Model 🏦

## Overview
This repository contains a Python-based machine learning pipeline designed to estimate the **Probability of Default (PD)** for consumer loans. The project involves data cleaning, exploratory data analysis (EDA), feature engineering, and the development of a Logistic Regression model to predict borrower default risk.

This project was developed as part of the **Mathematical Finance (MTH3010B)** practical assignment.

## 📂 Project Structure
```text
credit-risk-pd-model/
├── data/
│   ├── loan_data.csv              # Raw dataset (Input)
│   ├── loan_data_dictionary.csv   # Data dictionary
├── output/
│   ├── eda_visualizations.png     # Generated EDA plots
│   ├── roc_curve.png              # ROC Curve of the model
├── scripts/
│   ├── pd_model.py                # Main Python script
├── README.md                      # Project documentation
├── requirements.txt               # List of dependencies
📊 DatasetThe dataset consists of 2,500 loan records with the following key attributes:Borrower Details: Income, Age, Employment Years, Credit Score.Loan Details: Loan Amount, Term, Purpose, Loan Status.Target Variable: default (Derived from loan_status).🛠️ Key FeaturesData Cleaning:Imputed missing values in income and loan_amount using the median.Corrected negative income values (sign error correction).Feature Engineering:loan_to_income: Ratio of Loan Amount to Annual Income (Proxy for DTI).emp_to_age: Ratio of Employment Years to Age (Stability indicator).One-Hot Encoding for categorical variables (loan_purpose, loan_term).Modeling:Algorithm: Logistic Regression (Scikit-Learn).Validation: 80/20 Train-Test Split.🚀 Getting StartedPrerequisitesEnsure you have Python 3.8+ installed. You can install the required libraries using:Bashpip install pandas numpy matplotlib seaborn scikit-learn
UsageClone the repository:Bashgit clone [https://github.com/your-username/credit-risk-pd-model.git](https://github.com/your-username/credit-risk-pd-model.git)
Navigate to the project directory:Bashcd credit-risk-pd-model
Run the analysis script:Bashpython scripts/pd_model.py
📈 Results & EvaluationThe model was evaluated on a held-out test set (20% of data).MetricScoreNoteAccuracy78.80%High due to class imbalance (mostly non-defaults).AUC Score0.52Indicates weak separation power in the current dataset.KS Statistic0.0755Low discrimination between defaults and non-defaults.Key Insight: The loan_to_income ratio was identified as the strongest predictor of default risk.🤝 ContributingContributions are welcome! Please feel free to submit a Pull Request.📜 LicenseThis project is licensed under the MIT License.
