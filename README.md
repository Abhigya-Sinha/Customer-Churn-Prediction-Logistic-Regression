#  Customer Churn Prediction using Logistic Regression

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)

An end-to-end Machine Learning assignment project building a **Logistic Regression** model to predict telecom customer churn based on customer demographics, accounts, and service usage.

---

##  Objective

The primary objective of this project is to analyze customer attributes from the **Telco Customer Churn** dataset and build a binary classification model using **Logistic Regression** to identify customers at risk of leaving the service provider.

---

##  Dataset Information

* **Dataset Name:** Telco Customer Churn Dataset
* **Source:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

> ⚠️ **Note:** In compliance with dataset distribution policies, the raw dataset file (`WA_Fn-UseC_-Telco-Customer-Churn.csv`) is not tracked in this GitHub repository. Download it directly from Kaggle.

### Feature Summary
* **Numerical Features:** `MonthlyCharges`, `TotalCharges`, `tenure`
* **Categorical Features:** `gender`, `SeniorCitizen`, `Partner`, `Dependents`, `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`, `Contract`, `PaperlessBilling`, `PaymentMethod`
* **Target Variable:** `Churn` (`Yes` / `No`)

---

## 🛠️ Libraries Used

* **Data Handling:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib`, `seaborn`
* **Machine Learning & Preprocessing:** `scikit-learn` (`LabelEncoder`, `train_test_split`, `LogisticRegression`, `BernoulliNB`, `SVC`, `DecisionTreeClassifier`, `accuracy_score`, `confusion_matrix`, `classification_report`, `roc_curve`, `auc`)

---

## 🔄 Methodology

1. **Data Understanding & Exploratory Analysis:**
   * Loaded raw dataset (`7043` rows, `21` columns) and validated non-duplicate records.
   * Generated distribution plots for demographic variables (`gender`, `SeniorCitizen`, `Partner`, `Dependents`) and account metrics.
2. **Data Cleaning & Feature Engineering:**
   * Handled blank space values in `TotalCharges` by dropping `11` empty string rows and converting the column to numeric `float32`.
   * Encoded categorical attributes using `LabelEncoder`.
   * Removed non-predictive identifiers (`customerID`).
3. **Data Splitting:**
   * Split dataset into **80% Training Set** and **20% Testing Set** as specified by assignment guidelines.
4. **Model Development & Benchmarking:**
   * Primary model trained: **Logistic Regression** (`solver='liblinear'`).
   * Secondary comparison baseline models trained: **Bernoulli Naive Bayes**, **Support Vector Classifier (SVC)**, and **Decision Tree Classifier**.

---

## 📈 Results & Evaluation

### Logistic Regression Model Metrics

| Metric | Score |
| :--- | :--- |
| **Accuracy** | **~79.9%** |
| **Precision (Class 1 - Churn)** | **0.65** |
| **Recall (Class 1 - Churn)** | **0.50** |
| **F1-Score (Class 1 - Churn)** | **0.56** |

### Confusion Matrix (Logistic Regression)
* **True Negatives (Retained correctly):** `1551`
* **False Positives (Predicted churn, actually retained):** `160`
* **False Negatives (Predicted retain, actually churned):** `307`
* **True Positives (Churned correctly):** `303`

### Model Comparisons
* **Logistic Regression:** Accuracy = `79.88%`, AUC = `0.702` *(Best Performing Model)*
* **Bernoulli Naive Bayes:** Accuracy = `73.46%`, AUC = `0.703`
* **Support Vector Classifier (SVC):** Accuracy = `73.72%`, AUC = `0.500`
* **Decision Tree Classifier:** Accuracy = `71.69%`, AUC = `0.636`

---

## 📝 Task 5: Conclusion

> In this project, a Logistic Regression classification model was successfully trained to predict telecom customer churn. Exploratory data analysis revealed that payment method, paperless billing, monthly charges, and service add-ons heavily influence customer retention, with roughly 26% of customers churning overall. Logistic Regression proved to be the most balanced model among those evaluated, achieving the highest classification accuracy (~80%) and strong ROC-AUC performance. However, a major limitation of Logistic Regression for this task is its linear decision boundary assumption. It struggles to capture non-linear relationships and multi-way feature interactions (such as the combined effect of high monthly charges and short tenure length) without explicit polynomial transformation or manual interaction features.

---

## 🚀 How to Run

1. **Clone repository:**
   ```bash
   git clone [https://github.com/DigitalDetectiv/Customer-Churn-Prediction-Logistic-Regression.git](https://github.com/DigitalDetectiv/Customer-Churn-Prediction-Logistic-Regression-MPONLINE)
   cd Customer-Churn-Prediction-Logistic-Regression