# Lab 8: K-Nearest Neighbors (KNN)
**Binary Classification Using the KNN Project Dataset**
 
[![Problem](https://img.shields.io/badge/Problem-KNN%20Classification-blue)](#)
[![Samples](https://img.shields.io/badge/Samples-1000-green)](#)
[![Features](https://img.shields.io/badge/Features-10-orange)](#)
 
---
 
## Problem Statement
 
The objective of this lab is to utilize the **K-Nearest Neighbors** algorithm to classify anonymized data points into a specific `TARGET CLASS`. [cite_start]This project covers the end-to-end machine learning pipeline, emphasizing the importance of feature scaling for distance-based algorithms and the optimization of hyperparameters using the elbow method. [cite: 2]
 
- [cite_start]**Target Variable:** `TARGET CLASS` (0 or 1) [cite: 1, 2]
- [cite_start]**Problem Type:** Binary Classification [cite: 2]
- [cite_start]**Dataset Size:** 1000 entries (300 in test set) [cite: 2]
---
 
## Dataset Features
 
[cite_start]The dataset contains 10 numerical features that have been anonymized for the project: [cite: 1, 2]
 
| # | Feature | Type |
|:-:|---------|:----:|
| 1 | `XVPM` | Numeric |
| 2 | `GWYH` | Numeric |
| 3 | `TRAT` | Numeric |
| 4 | `TLLZ` | Numeric |
| 5 | `IGGA` | Numeric |
| 6 | `HYKR` | Numeric |
| 7 | `EDFS` | Numeric |
| 8 | `GUUB` | Numeric |
| 9 | `MGJM` | Numeric |
| 10 | `JHZC` | Numeric |
| 11 | `TARGET CLASS` | **Target Variable** |
 
---
 
## Steps Performed
 
1. [cite_start]**Load the Data** — Imported the `KNN_Project_Data` file into a Pandas DataFrame. [cite: 2]
2. [cite_start]**Exploratory Data Analysis (EDA)** — Created a Seaborn pairplot with hue set to the target class to observe feature distributions and class overlap. [cite: 2]
3. [cite_start]**Standardize the Features** — Used `StandardScaler` to normalize the data, ensuring that features with larger scales do not disproportionately influence the KNN distance calculations. [cite: 2]
4. [cite_start]**Prepare for Modeling** — Performed a train/test split (70% training, 30% testing) with a `random_state` of 101. [cite: 2]
5. [cite_start]**Train Initial Model** — Established a baseline by fitting a `KNeighborsClassifier` with **K=1**. [cite: 2]
6. [cite_start]**Evaluate Initial Model** — Analyzed performance via a confusion matrix and classification report. [cite: 2]
7. [cite_start]**The Elbow Method** — Iterated through K values from 1 to 40 to calculate and plot the error rate, identifying the point where the error stabilizes. [cite: 2]
8. [cite_start]**Retrain with Optimal K** — Based on the elbow plot, the model was retrained with **K=31**, resulting in a more generalized and accurate classifier. [cite: 2]
---
 
## Key Findings
 
| Finding | Detail |
|---------|--------|
| **Standardization** | [cite_start]Crucial step; scaling the features significantly impacted the model's ability to calculate meaningful distances. [cite: 2] |
| **Optimal K-Value** | [cite_start]**K=31** was identified as the optimal neighbor count to balance accuracy and complexity. [cite: 2] |
| **Model Accuracy** | [cite_start]The final model achieved an overall accuracy of **84%** on the test dataset. [cite: 2] |
| **Confusion Matrix** | [cite_start]The final model produced 123 True Negatives and 129 True Positives. [cite: 2] |
 
---
 
## Libraries Used
 
- [cite_start]**Pandas:** Data manipulation and analysis. [cite: 2]
- [cite_start]**NumPy:** Mathematical computations. [cite: 2]
- [cite_start]**Seaborn & Matplotlib:** Data visualization and plotting error curves. [cite: 2]
- [cite_start]**Scikit-learn:** Feature scaling (`StandardScaler`), model selection (`train_test_split`), and model evaluation metrics. [cite: 2]
