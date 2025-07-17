#  🧠 IBM Employee Attrition Prediction

This repository presents a complete machine learning workflow to predict **employee attrition** using the **IBM HR Analytics Employee Attrition & Performance dataset**. The goal is to help HR professionals identify employees at risk of leaving, using predictive analytics and classification models.

---

## 📄 Dataset Overview

The dataset consists of **1,470 employee records** with **35 features** related to demographics, job roles, performance, satisfaction, and compensation. The target variable is:

* `Attrition`: Whether an employee left the company (`Yes`) or not (`No`).

📌 Source: [Kaggle - IBM HR Analytics Employee Attrition](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

---

## 🎯 Objectives

* Perform data cleaning, preprocessing, and EDA
* Apply and compare multiple classification models
* Evaluate each model using relevant metrics
* Identify the most effective model for attrition prediction

---

## 🧲 Data Preprocessing

To ensure robust model performance, the dataset was preprocessed with the following steps:

* Handled missing values and inconsistent categories
* Performed **label encoding** and **one-hot encoding** for categorical variables
* Applied **feature scaling** using StandardScaler
* Addressed **class imbalance** using **SMOTE (Synthetic Minority Over-sampling Technique)** to generate synthetic examples of the minority class (`Attrition = Yes`)

---

## 🤖 Models Used

We trained and evaluated the following classification models:

| Model                        | Notes                                |
| ---------------------------- | ------------------------------------ |
| Decision Tree Classifier     | Simple, interpretable model          |
| Support Vector Machine (SVM) | Effective with high-dimensional data |
| K-Nearest Neighbors (KNN)    | Distance-based classifier            |
| Random Forest                | Ensemble of decision trees           |
| Voting Classifier            | Combines multiple models' outputs    |
| Bagging Classifier           | Bootstrapped aggregation             |
| AdaBoost Classifier          | Boosted weak learners                |
| Gradient Boosting Classifier | Powerful boosting algorithm          |
| XGBoost Classifier           | High-performance ensemble            |

---

## 🏆 Best Performing Model

✅ **XGBoost Classifier** achieved the best overall performance:

* **Accuracy on test data**: **87%**
* **Cross-validation score**: **90%**

It demonstrated strong generalization and robustness, making it highly suitable for real-world deployment in HR attrition prediction.

---

## 📈 Classification Report (Best Model – XGBoost)

```
              precision    recall  f1-score   support

           0       0.88      0.97      0.92       247
           1       0.68      0.32      0.43        47

    accuracy                           0.87       294
   macro avg       0.78      0.65      0.68       294
weighted avg       0.85      0.87      0.85       294
```

### 🔍 Interpretation:

* Class **0 (No Attrition)** is predicted very well with high precision and recall.
* Class **1 (Attrition)** has lower recall, indicating some attrition cases were missed.
* **SMOTE** helped improve model balance, though further tuning could boost recall.

---

## 📊 Evaluation Metrics

All models were evaluated using:

* Accuracy
* Confusion Matrix

## 🔍 Key Insights

* XGBoost achieved the highest **accuracy of 87%** with a **cross-validation score of 90%**
* SMOTE was essential to handle **class imbalance**
* OverTime, JobSatisfaction, and YearsAtCompany were key predictors
* Ensemble models consistently outperformed single classifiers

---
