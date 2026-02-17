<div align="center">

# Lab 3: Exploratory Data Analysis (EDA)

**Applying EDA Techniques to the Heart Failure Clinical Records Dataset**

[![Dataset](https://img.shields.io/badge/Dataset-Heart%20Failure%20Clinical%20Records-red)](https://www.kaggle.com/datasets/andrewmvd/heart-failure-clinical-data)
[![Problem](https://img.shields.io/badge/Problem-Binary%20Classification-blue)](#)
[![Samples](https://img.shields.io/badge/Samples-299-green)](#)
[![Features](https://img.shields.io/badge/Features-13-orange)](#)

</div>

---

## Problem Statement

The goal of this lab is to perform **Exploratory Data Analysis (EDA)** on medical records of patients who experienced heart failure. By analyzing clinical features such as age, blood enzyme levels, and follow-up time, we aim to understand the factors that significantly influence patient mortality.

Before building a machine learning model, we visualize the relationships between health indicators (like Ejection Fraction and Serum Creatinine) and the survival outcome.

- **Target Variable:** `DEATH_EVENT` (0 = Survived, 1 = Deceased)
- **Problem Type:** Binary Classification
- **Dataset Size:** 299 entries

---

## Dataset Features

The dataset contains 13 clinical features. Below are the primary variables analyzed:

| # | Feature | Description | Type |
|:-:|---------|-------------|:----:|
| 1 | `age` | Age of the patient (years) | Numeric |
| 2 | `anaemia` | Decrease of red blood cells or hemoglobin | Boolean |
| 3 | `creatinine_phosphokinase` | Level of the CPK enzyme in the blood (mcg/L) | Numeric |
| 4 | `ejection_fraction` | Percentage of blood leaving the heart at each contraction | Numeric |
| 5 | `serum_creatinine` | Level of serum creatinine in the blood (mg/dL) | Numeric |
| 6 | `serum_sodium` | Level of serum sodium in the blood (mEq/L) | Numeric |
| 7 | `time` | Follow-up period in days | Numeric |
| 8 | `smoking` | If the patient is a smoker | Boolean |

---

## Steps Performed

### A. Data Integrity Check
We inspected the dataset to ensure quality before proceeding with analysis:
- **Missing Values:** Conducted a null value check; found **0** missing values across all columns.
- **Duplicates:** Verified there were **0** duplicate rows in the medical records.
- **Data Types:** Confirmed all columns are numerical (float64/int64), making the data ready for statistical computation.

### B. Exploratory Data Analysis (EDA)
Using **Matplotlib** and **Seaborn**, we performed several visualizations:
1.  **Summary Statistics:** Generated descriptive statistics (mean, std, min, max) for all clinical features.
2.  **Death Rate by Follow-up Time:** Binned the `time` variable into periods to observe how survival rates change over the duration of medical observation.
3.  **Categorical Impact:** Analyzed the death rate specifically for patients with conditions like **Anaemia**.
4.  **Relationship Analysis:** Investigated correlations between age and critical bio-markers like **Serum Creatinine**.

---

## Key Findings

| Finding | Detail |
|---------|--------|
| **Data Quality** | The dataset is extremely clean with **no missing values** or duplicates. |
| **Mortality Rate** | Approximately **32%** of patients in this dataset suffered a `DEATH_EVENT`. |
| **Follow-up Time** | There is a visible relationship between the `time` (follow-up period) and the likelihood of survival. |
| **Anaemia Factor** | Initial analysis shows patients with Anaemia have a slightly higher mortality rate (~35.6%) compared to those without (~29.4%). |

---

## Libraries Used

- **Pandas:** For data loading, binning, and manipulation.
- **Seaborn:** For statistical visualization and cleaner plot styling.
- **Matplotlib:** For creating bar charts and scatter plots.
- **NumPy:** For numerical operations.
