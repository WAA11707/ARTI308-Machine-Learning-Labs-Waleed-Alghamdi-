# Lab 7: Logistic Regression
**Predicting Ad Clicks Using the Advertising Dataset**

[![Problem](https://img.shields.io/badge/Problem-Logistic%20Regression-blue)](#)
[![Samples](https://img.shields.io/badge/Samples-1000-green)](#)
[![Features](https://img.shields.io/badge/Features-5-orange)](#)

---

## Problem Statement

The goal of this lab is to apply **Logistic Regression** to predict whether an internet user will click on an advertisement based on their browsing behavior and demographics.

- **Target Variable:** `Clicked on Ad` (0 = Did Not Click, 1 = Clicked)
- **Problem Type:** Binary Classification
- **Dataset Size:** 1000 entries

---

## 📊 Feature Breakdown

The model utilizes the following variables to identify patterns in user behavior:

| Feature | Description | Data Type |
| :--- | :--- | :--- |
| **Daily Time Spent on Site** | Consumer session duration in minutes | Numerical |
| **Age** | User age in years | Numerical |
| **Area Income** | Average income of the user's geographic region | Numerical |
| **Daily Internet Usage** | Average minutes spent online per day | Numerical |
| **Male** | Gender indicator (1: Male, 0: Female) | Categorical/Binary |

---

## ⚙️ Methodology

### 1. Data Exploration & Analysis
Initial exploration was conducted using `pandas` and `seaborn` to assess data quality and feature correlations.
- **Demographic Analysis:** Visualized age distributions via histograms.
- **Behavioral Correlation:** Utilized Jointplots to analyze the relationship between `Area Income`, `Daily Time Spent`, and `Age`.
- **Class Separation:** Generated Pairplots with hue-mapping to observe how distinct the "Clicked" vs. "Not Clicked" clusters appear across features.

### 2. Model Pipeline
- **Data Partitioning:** The dataset was split into training and testing sets (67/33 ratio) using `random_state=42`.
- **Implementation:** A `LogisticRegression` algorithm was trained on the processed features.
- **Performance Metrics:** The model was evaluated using a Classification Report to measure precision, recall, and the F1-score.

---

## 📈 Key Insights & Results

- **Predictive Power:** Exploratory analysis revealed strong class separation, particularly between "Daily Internet Usage" and "Daily Time Spent on Site," making them high-impact predictors.
- **Model Accuracy:** The Logistic Regression model achieved an **accuracy of 97%**, demonstrating high reliability for this classification task.
- **Efficiency:** The dataset was clean, requiring minimal preprocessing, which allowed for a direct and efficient modeling phase.

---

## 🛠 Tech Stack

- **Data Handling:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn (Model Selection, Linear Models, Metrics)
