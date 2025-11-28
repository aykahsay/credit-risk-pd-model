# **Credit Risk PD Model 🏦**

## **Overview**

This repository contains a Python-based machine learning pipeline developed to estimate the **Probability of Default (PD)** for consumer loans. The workflow includes:

* Data Cleaning
* Exploratory Data Analysis (EDA)
* Feature Engineering
* Model Training & Evaluation

A **Logistic Regression** algorithm is used as the baseline model to classify borrowers as *default* or *non-default*.
This project was completed as part of the **Mathematical Finance (MTH3010B)** practical assignment.

---

## 📂 **Project Structure**

```text
credit-risk-pd-model/
├── data/
│   ├── loan_data.csv              # Raw dataset (input)
│   ├── loan_data_dictionary.csv   # Description of dataset fields
│
├── output/
│   ├── eda_visualizations.png     # Plots generated during EDA
│   ├── roc_curve.png              # ROC curve for PD model
│
├── scripts/
│   ├── pd_model.py
|   ├── EDA.ipynb            # Main model training & evaluation script
│
├── README.md                      # Project documentation
├── requirements.txt               # Dependencies for easy setup
```

---

## 📊 **Dataset Description**

The dataset contains **2,500 loan records** with the following categories:

### **Borrower Information**

* Income
* Age
* Employment Years
* Credit Score

### **Loan Information**

* Loan Amount
* Loan Term
* Loan Purpose
* Loan Status

### **Target Variable**

* **default** (derived from `loan_status`)

---

## 🛠️ **Data Preparation**

### **1. Data Cleaning**

* Missing values in `income` and `loan_amount` imputed using **median**
* Negative income values corrected (erroneous sign entries)
* Categorical variables reviewed for consistency

### **2. Feature Engineering**

Created new variables to improve model performance:

* `loan_to_income` → Loan Amount ÷ Annual Income
* `emp_to_age` → Employment Years ÷ Age
* One-hot encoding applied to:

  * `loan_purpose`
  * `loan_term`

---

## 📈 **Exploratory Data Analysis (EDA)**

EDA steps include:

* Distribution of borrower income, age, and credit score
* Loan amount and loan purpose trends
* Correlation matrix
* Default rate analysis
* Outlier checks

A summary of EDA outputs is saved under `/output/eda_visualizations.png`.

---

## 🤖 **Modeling Approach**

### **Model Used**

* **Logistic Regression** (Scikit-Learn)

### **Validation Strategy**

* **80/20 Train-Test Split**

### **Key Variables**

* `loan_to_income` emerged as the **strongest predictor** of default.
* Borrowers with high loan-to-income ratios show significantly higher PD.

---

## 📊 **Model Performance**

Evaluation on the test set:

| Metric           | Score  | Interpretation              |
| ---------------- | ------ | --------------------------- |
| **Accuracy**     | 78.80% | High due to class imbalance |
| **AUC Score**    | 0.52   | Weak separation power       |
| **KS Statistic** | 0.0755 | Low risk discrimination     |


---

## 🚀 **Getting Started**

### **Prerequisites**

Ensure Python **3.8+** is installed.

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

## ▶️ **How to Run the Model**

### **1. Clone the repository**

```bash
git clone https://github.com/your-username/credit-risk-pd-model.git
```

### **2. Navigate to project directory**

```bash
cd credit-risk-pd-model
```

### **3. Run the main script**

```bash
python scripts/pd_model.py
```

The script performs data loading, cleaning, feature engineering, model training, and evaluation automatically.

---

## 💡 **Key Insights**

* Borrowers with **high loan-to-income ratios** are significantly more likely to default.
* Logistic Regression struggled due to **class imbalance** and limited feature richness.
* Additional variables (e.g., debt history, employment type, savings) could improve predictive power.

---

## 📌 **Future Improvements**

Potential enhancements include:

* Testing alternative models (Random Forest, XGBoost)
* Applying SMOTE or Class Weight adjustment for imbalance
* Hyperparameter optimization
* Incorporating behavioral or transactional features
* Building a PD calibration curve

---

## 🤝 **Contributing**

Contributions are welcome!
Feel free to submit issues or pull requests to improve the model or documentation.

---

## 📜 **License**

This project is licensed under the **MIT License**.

---

