# 🩺 Diabetes Prediction using Machine Learning

![Project Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Machine Learning](https://img.shields.io/badge/Technique-SVM-orange)

## Overview
This project focuses on predicting whether a person has **diabetes** based on several medical attributes using **Support Vector Machine (SVM)**.  
It is an important healthcare application aimed at early detection and intervention.

---

## 📅 Dataset Information

The dataset used is a standard diabetes dataset, often referred to as the **Pima Indians Diabetes Dataset**.

| Feature                    | Description                              |
| --------------------------- | ---------------------------------------- |
| Pregnancies                 | Number of times pregnant                |
| Glucose                     | Plasma glucose concentration            |
| BloodPressure               | Diastolic blood pressure (mm Hg)         |
| SkinThickness               | Triceps skin fold thickness (mm)         |
| Insulin                     | 2-Hour serum insulin (mu U/ml)           |
| BMI                         | Body mass index (weight in kg/(height in m)^2) |
| DiabetesPedigreeFunction    | Diabetes pedigree function (genetic history) |
| Age                         | Age in years                            |
| Outcome                     | Class variable (0: No diabetes, 1: Diabetes) |

### Dataset Shape
- **Rows:** 768
- **Columns:** 9

### 🧹 Data Cleaning
- No missing values ✅
- No duplicate entries ✅

---

## 🔍 Exploratory Data Analysis (EDA)

- **Imbalanced Dataset:** The `Outcome` variable is imbalanced, more 0s (non-diabetic) than 1s (diabetic).
- **Outliers:** Present in features like Pregnancies, Glucose, Blood Pressure, Skin Thickness, BMI, Age, DiabetesPedigreeFunction, and Insulin.
- **Feature Skewness:** Several features (e.g., Insulin, DiabetesPedigreeFunction) showed high skewness.
- **Feature Importance:** 
  - **Glucose** has the highest influence on prediction.
  - Followed by **BMI**, **Diabetes Pedigree Function**, and **Pregnancies**.

### 💡 Important Observations
- The data is **non-linear** and **non-normal**.
- Logistic Regression and Naive Bayes were **ruled out** due to:
  - Non-linear relationships
  - Presence of outliers
  - Dataset imbalance
- **SVM** was selected as the final model choice because it handles non-linear, high-dimensional data well.

---

## 🧠 Model Building

| Model Tried        | Decision                                     |
| ------------------ | -------------------------------------------- |
| Logistic Regression | Not suitable (non-linear, non-normal data) |
| Naive Bayes         | Not suitable (imbalanced dataset)           |
| SVM                 | **Final Model Chosen**                     |

###  Model Performance

- **SVM Accuracy:** ~80.6% (on test set)
- **Issues Identified:**  
  Some model instability observed, suspected due to:
  - Influence of irrelevant features
  - Outliers affecting SVM boundary

### 🔥 Feature Interpretation

Using **Permutation Importance**, the most influential features were identified:

| Feature                   | Importance Rank |
| --------------------------- | ---------------- |
| Glucose                     | 1️⃣ Most Important |
| BMI                         | 2️⃣ |
| Diabetes Pedigree Function  | 3️⃣ |
| Pregnancies                 | 4️⃣ |
| SkinThickness, Insulin      | Minor contribution |
| BloodPressure, Age          | Very little impact |

---

## 🛠 Technologies Used

- Python 🐍
- Pandas
- Numpy
- Scikit-Learn
- SHAP / Permutation Importance
- Jupyter Notebook

---
