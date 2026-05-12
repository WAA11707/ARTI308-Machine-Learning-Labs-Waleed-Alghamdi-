# 🌸 LAB-10: Support Vector Machines
### *Species Classification of the Iris Flower Dataset*

<div align="center">

![Type](https://img.shields.io/badge/Task-Classification-DB7093?style=for-the-badge)
![Data](https://img.shields.io/badge/Dataset-Iris_Flower-blueviolet?style=for-the-badge)
![Library](https://img.shields.io/badge/Tools-Scikit--Learn-orange?style=for-the-badge)

</div>

---

## 📝 Project Overview
This project applies **Support Vector Machines (SVM)** to the classic Iris dataset to classify flowers into one of three species: *Setosa*, *Versicolor*, or *Virginica*. By analyzing morphological measurements, we build a robust classifier and optimize its performance using hyperparameter tuning via Grid Search.

### Core Objectives
* **Visualize** feature relationships to identify cluster separability (notably the distinct Setosa group).
* **Train** a Support Vector Classifier (SVC) to distinguish between species.
* **Optimize** the model using **GridSearch** to find the ideal values for `C` and `gamma`.
* **Evaluate** performance using precision, recall, and confusion matrices.

---

## 📊 Dataset Breakdown
The dataset consists of **150 samples** across three species, with four quantitative features:

| Feature | Description | Importance |
| :--- | :--- | :---: |
| `Sepal Length` | Length of the sepal (cm). | Medium |
| `Sepal Width` | Width of the sepal (cm). | Medium |
| `Petal Length` | Length of the petal (cm). | **High** |
| `Petal Width` | Width of the petal (cm). | **High** |
| **`Species`** | **Target: Setosa, Versicolor, Virginica** | - |

> **Note:** Exploratory Data Analysis (EDA) confirms that *Iris-Setosa* is linearly separable from the other two species, while *Versicolor* and *Virginica* require a non-linear boundary (RBF Kernel).

---

## ⚙️ Technical Pipeline

### 1. Exploratory Data Analysis (EDA)
* **Pairplots:** Visualized feature interactions using `sns.pairplot` to identify clustering patterns.
* **KDE Plots:** Generated kernel density estimation plots (e.g., Sepal Length vs. Width) to observe species overlap.

### 2. Model Architecture
* **Algorithm:** Support Vector Classifier (SVC).
* **Validation Strategy:** Train-Test split with a focus on balanced classification.
* **Optimization:** Implemented `GridSearchCV` to tune `C` (penalty parameter) and `gamma` (kernel coefficient), moving from default guesses to an optimized model.

### 3. Performance Evaluation
* **Metrics:** Detailed Classification Report showing Precision, Recall, and F1-Score.
* **Visualization:** Confusion Matrix heatmap (using `sns.heatmap`) to visualize correct vs. incorrect predictions across species.

---

## 🚀 Key Insights
* **The Setosa Gap:** Setosa remains the most separable species, consistently achieving 100% precision and recall across all tests.
* **Grid Search Impact:** Fine-tuning hyperparameters significantly improved the model's ability to distinguish between the slightly overlapping Versicolor and Virginica classes.
* **High Accuracy:** The final optimized model achieved an overall accuracy of **98%**, proving SVM is an excellent fit for small, high-dimensional biological datasets.

---

## 🛠️ Stack & Dependencies
* **Data Handling:** `Pandas`, `NumPy`
* **Modeling:** `Scikit-learn`
* **Visualization:** `Seaborn`, `Matplotlib`
