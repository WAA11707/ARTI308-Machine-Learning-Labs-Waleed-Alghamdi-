# 📈 Lab 6: Linear Regression.
### *Predicting Customer Lifetime Spending via Linear Regression*

<div align="center">

![Type](https://img.shields.io/badge/Task-Regression-DB7093?style=for-the-badge)
![Data](https://img.shields.io/badge/Dataset-Ecommerce_Customers-blueviolet?style=for-the-badge)
![Library](https://img.shields.io/badge/Tools-Scikit--Learn-orange?style=for-the-badge)

</div>

---

## 📝 Project Overview
This project focuses on identifying the key behavioral drivers that influence how much money customers spend on an e-commerce platform. By utilizing a **Linear Regression** model, we analyze the correlation between session length, app usage, and membership duration to predict the `Yearly Amount Spent`.

### Core Objectives
* **Analyze** the impact of mobile app vs. website usage on total revenue.
* **Build** a predictive model to estimate yearly expenditure for new customers.
* **Evaluate** model accuracy using standard regression metrics (MAE, MSE, RMSE).

---

## 📊 Dataset Breakdown
The model is trained on a dataset of **500 customers** with the following numerical attributes:

| Feature | Description | Importance |
| :--- | :--- | :---: |
| `Avg. Session Length` | In-store style advice session duration. | Low/Mid |
| `Time on App` | Minutes spent browsing the mobile application. | **High** |
| `Time on Website` | Minutes spent browsing the desktop site. | Low |
| `Length of Membership` | Number of years as a registered member. | **Primary Driver** |
| **`Yearly Amount Spent`** | **Target Variable (USD)** | - |

> **Note:** Categorical data (Email, Address, Avatar) was pruned during the preprocessing phase to ensure a focus on quantitative correlation.

---

## ⚙️ Technical Pipeline

### 1. Data Processing
* **Inspection:** Initial audit using `.info()` and descriptive statistics.
* **Cleaning:** Verified a clean dataset with **zero missing values**.
* **Selection:** Dropped non-numeric identifiers to isolate predictive features.

### 2. Model Architecture
* **Validation Strategy:** 70/30 Train-Test split (Random State: 101).
* **Algorithm:** Ordinary Least Squares (OLS) Linear Regression.
* **Metric Suite:** Mean Absolute Error, Mean Squared Error, and Root Mean Squared Error.

### 3. Visual Diagnostics
* **Residual Analysis:** Generated a distribution plot of residuals to confirm normality and model validity.
* **Prediction Mapping:** Comparison plots of actual vs. predicted values.

---

## 🚀 Key Insights
* **The Power of Membership:** The strongest correlation to spending is the length of time a customer has been a member. 
* **App vs. Web:** The data suggests that time spent on the **Mobile App** has a significantly higher impact on spending compared to the Website.
* **Model Accuracy:** The residual histogram follows a normal distribution, suggesting that the Linear Regression model is an appropriate fit for this specific dataset.

---

## 🛠️ Stack & Dependencies
* **Data Handling:** `Pandas`, `NumPy`
* **Modeling:** `Scikit-learn`
* **Visualization:** `Seaborn`, `Matplotlib`

---

## 📂 How to Use
1. Clone the repository.
2. Ensure you have the `Ecommerce Customers.csv` file in the root directory.
3. Run the notebook/script to view the coefficients and error metrics.
