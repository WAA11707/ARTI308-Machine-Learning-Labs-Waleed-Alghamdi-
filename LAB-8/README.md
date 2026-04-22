# Lab 8: K-Nearest Neighbors (KNN)
**Binary Classification Using the KNN Project Dataset**
 
[![Problem](https://img.shields.io/badge/Problem-KNN%20Classification-blue)](#)
[![Samples](https://img.shields.io/badge/Samples-1000-green)](#)
[![Features](https://img.shields.io/badge/Features-10-orange)](#)
 
---
 
## Problem Statement
 
The objective of this lab is to utilize the **K-Nearest Neighbors** algorithm to classify anonymized data points into a specific `TARGET CLASS`. This project covers the end-to-end machine learning pipeline, emphasizing the importance of feature scaling for distance-based algorithms and the optimization of hyperparameters using the elbow method.
 
- **Target Variable:** `TARGET CLASS` (0 or 1)
- **Problem Type:** Binary Classification
- **Dataset Size:** 1000 entries (300 in test set)
---
 
## Dataset Features
 
The dataset contains 10 numerical features that have been anonymized for the project:
 
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
 
1. **Load the Data** — Imported the `KNN_Project_Data` file into a Pandas DataFrame.
2. **Exploratory Data Analysis (EDA)** — Created a Seaborn pairplot with hue set to the target class to observe feature distributions and class overlap.
3. **Standardize the Features** — Used `StandardScaler` to normalize the data, ensuring that features with larger scales do not disproportionately influence the KNN distance calculations.
4. **Prepare for Modeling** — Performed a train/test split (70% training, 30% testing) with a `random_state` of 101.
5. **Train Initial Model** — Established a baseline by fitting a `KNeighborsClassifier` with **K=1**.
6. **Evaluate Initial Model** — Analyzed performance via a confusion matrix and classification report.
7. **The Elbow Method** — Iterated through K values from 1 to 40 to calculate and plot the error rate, identifying the point where the error stabilizes.
8. **Retrain with Optimal K** — Based on the elbow plot, the model was retrained with **K=31**, resulting in a more generalized and accurate classifier.
---
 
## Key Findings
 
| Finding | Detail |
|---------|--------|
| **Standardization** | Crucial step; scaling the features significantly impacted the model's ability to calculate meaningful distances. |
| **Optimal K-Value** | **K=31** was identified as the optimal neighbor count to balance accuracy and complexity. |
| **Model Accuracy** | The final model achieved an overall accuracy of **84%** on the test dataset. |
| **Confusion Matrix** | The final model produced 123 True Negatives and 129 True Positives. |
 
---
 
## Libraries Used
 
- **Pandas:** Data manipulation and analysis.
- **NumPy:** Mathematical computations.
- **Seaborn & Matplotlib:** Data visualization and plotting error curves.
- **Scikit-learn:** Feature scaling (`StandardScaler`), model selection (`train_test_split`), and model evaluation metrics.
