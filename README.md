# Beta Bank: Customer Churn Prediction

![Project Status](https://img.shields.io/badge/Status-Completed-success)
![F1 Score](https://img.shields.io/badge/F1--Score-0.62-blue)
![AUC-ROC](https://img.shields.io/badge/AUC--ROC-0.85-orange)

## 📌 Project Overview
Beta Bank is experiencing a gradual loss of customers every month. Bank marketers have concluded that retaining existing customers is significantly cheaper than acquiring new ones. 

This project aims to predict whether a customer will leave the bank soon. By identifying these high-risk individuals, Beta Bank can proactively offer incentives to improve retention rates.

## 🎯 Objectives
* Build a classification model with the **maximum possible F1 score**.
* Reach a minimum **F1 score threshold of 0.59**.
* Evaluate model performance using **AUC-ROC** and compare it with the F1 score.
* Address and resolve the inherent **class imbalance** (80/20) in the dataset.

## 📊 Dataset Description
The dataset contains 10,000 records of bank customers with the following key features:
* **Features:** Credit Score, Geography, Gender, Age, Tenure, Balance, Number of Products, Credit Card status, Active Membership, and Estimated Salary.
* **Target:** `Exited` (1 if the customer left, 0 if they stayed).

## 🛠️ Technical Workflow

### 1. Data Preprocessing
* **Cleaning:** Handled missing values in the `Tenure` column by analyzing distributions to ensure data integrity.
* **Encoding:** Utilized **One-Hot Encoding (OHE)** for categorical variables.
* **Scaling:** Applied **StandardScaler** to numerical features to ensure all variables contribute equally to the model's distance calculations.
* **Feature Selection:** Dropped non-informative columns (`RowNumber`, `CustomerId`, `Surname`) to prevent overfitting.

### 2. Handling Class Imbalance
The dataset was highly imbalanced (~80% stayed vs. ~20% exited). To resolve this, I implemented:
* **Upsampling:** Increasing the representation of the minority class.
* **Class Weight Adjustment:** Utilizing the `class_weight='balanced'` parameter.



### 3. Model Development & Tuning
I compared several algorithms, focusing primarily on:
1.  **Logistic Regression:** Baseline for performance.
2.  **Random Forest Classifier:** Performed hyperparameter tuning (Depth and Estimators) to achieve peak F1 scores.



## 🏆 Key Results

| Model | Imbalance Strategy | F1-Score | AUC-ROC |
| :--- | :--- | :--- | :--- |
| Logistic Regression | Baseline | 0.33 | 0.76 |
| **Random Forest** | **Upsampling** | **0.62** | **0.85** |

* **Final F1 Score:** 0.62 (Surpassed the 0.59 requirement).
* **Final AUC-ROC:** 0.85 (Indicates strong predictive power).

## 🚀 Business Impact
* **Targeted Retention:** The marketing team can now target the top 20% of customers most likely to churn with specialized rewards.
* **Operational Efficiency:** By predicting churn before it happens, the bank can allocate resources toward "at-risk" customers rather than broad, expensive marketing campaigns.

## 📂 Project Structure
* `Beta_Bank.ipynb`: The complete Jupyter Notebook containing all analysis, code, and visualizations.
* `Churn.csv`: The raw dataset used for the project.
* `README.md`: Project documentation.

## 🧰 Tools Used
* **Python** (Pandas, NumPy, Matplotlib, Seaborn)
* **Scikit-Learn** (RandomForestClassifier, LogisticRegression, StandardScaler, f1_score, roc_auc_score)
