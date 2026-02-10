# Lab 2: Machine Learning Problem Definition

## Dataset Description
The dataset used for this lab is the **Heart Failure Clinical Records** dataset. It contains 299 patient records with 13 different columns:

* **Clinical Metrics**: Age, Anaemia, Creatinine Phosphokinase, Ejection Fraction, Platelets, Serum Creatinine, and Serum Sodium.
* **Health Indicators**: Diabetes, High Blood Pressure, Sex, and Smoking status.
* **Follow-up Data**: Time (follow-up period in days).

## Machine Learning Problem

* **Problem Type**: This is a **Classification** problem.
* **Target Variable**: The target variable is `DEATH_EVENT` (Categorical: 0 for survival, 1 for deceased).
* **Problem Statement**: The objective is to analyze clinical features to predict whether a patient will survive a heart failure event. This model aims to help medical professionals identify high-risk patients based on their clinical history to improve treatment outcomes.


## Files Included

- **`Lab2.ipynb`**: The Jupyter Notebook containing data loading, inspection (shape, head, info), and basic data type checks.
- **`waleed.csv`**: The raw clinical dataset used for the analysis.
- **`Methodology-LAB-2.png`**: A flowchart illustrating the proposed ML pipeline from data collection to evaluation.
