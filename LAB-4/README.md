# Lab 4: Data Quality Assessment & Preprocessing

## Project Overview
This lab focuses on the critical second step of the Machine Learning pipeline: **Preprocessing**. In real-world scenarios, data is often incomplete, noisy, or inconsistent. Using a clinical heart failure dataset (`waleed.csv`), we apply various cleaning and transformation techniques to prepare the data for predictive modeling.

---

## Preprocessing Workflow

### 1. Data Quality Assessment
An initial audit of the 299 records was performed to identify structural or logical errors:
* **Data Types**: Verified that all 13 features were correctly identified as numeric (int64 or float64).
* **Logical Consistency**: Checked for unusual values; for instance, verified that the `age` column contained no zero or negative values.

### 2. Handling Missing Values
To demonstrate imputation techniques, we artificially introduced gaps in the dataset:
* **Simulation**: 20 random values were removed from the `platelets` column.
* **Strategy**: **Median Imputation** was used to fill these gaps.
* **Justification**: The median is robust to the extreme high values often found in medical data, ensuring that the central tendency is not skewed by outliers.

### 3. Outlier Detection
Extreme values can significantly distort machine learning models by adding noise.
* **Method**: Used the **Interquartile Range (IQR)** method on the `creatinine_phosphokinase` feature.
* **Result**: **29 extreme outliers** were identified and removed. 
* **Final Shape**: The dataset was reduced from 299 to 270 samples following outlier removal.

### 4. Data Transformation (Normalization)
To ensure all numerical features contribute equally to the model, we applied two scaling methods:
* **Min-Max Scaling**: Rescaled features (such as `age`, `platelets`, and `time`) to a fixed range of $[0, 1]$.
* **Z-Score Normalization**: Transformed features to have a **Mean of 0** and a **Standard Deviation of 1**.

### 5. Data Reduction (PCA)
We utilized **Principal Component Analysis** (PCA) to reduce dimensionality while retaining maximum information:
* **Explained Variance**: The first two Principal Components together captured **43.88%** of the total variance in the clinical records.
* **PC1 Contribution**: The first component (PC1) alone explained **24.12%** of the variance.
* **Impact**: These uncorrelated components help simplify future training and reduce computational costs.

---

## Key Results
| Metric | Value |
| :--- | :--- |
| **Total Samples** | 299 |
| **Outliers Removed** | 29 |
| **Imputation Method** | Median |
| **PC1 Variance** | 24.12% |

---

## Files Included
* `Lab4.ipynb`: The complete Python implementation of the preprocessing steps.
* `waleed.csv`: The heart failure clinical records dataset.
* `README.md`: Documentation of the lab workflow.
