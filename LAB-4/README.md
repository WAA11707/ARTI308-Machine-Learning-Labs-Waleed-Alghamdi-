# Lab 4: Data Quality Assessment & Preprocessing

## Project Summary
This lab explores the essential second phase of the Machine Learning lifecycle: **Data Preprocessing**. Since raw clinical data is frequently riddled with inconsistencies, noise, or missing entries, this project utilizes the `waleed.csv` heart failure dataset to practice robust cleaning and preparation methods before any predictive modeling begins.

---

## The Preprocessing Pipeline

### 1. Data Integrity Audit
We began with a comprehensive scan of the 299 patient records to catch any structural flaws:
* **Schema Check**: Confirmed that all 13 clinical attributes were correctly formatted as numeric types (`int64` or `float64`).
* **Validity Testing**: Performed a sanity check on features like `age` to ensure no logically impossible values (e.g., negative numbers or zeros) were present.

### 2. Missing Data Imputation
To test our ability to handle incomplete data, we simulated a real-world "messy" scenario:
* **Artificial Gaps**: 20 entries were randomly deleted from the `platelets` column.
* **Correction Strategy**: We applied **Median Imputation** to restore the missing data.
* **Rational**: Unlike the mean, the median is less sensitive to extreme medical readings (outliers), preserving the overall distribution of the dataset without skewing the central tendency.

### 3. Outlier Management
Anomalous data points can introduce significant bias into a model. 
* **Detection Technique**: We applied the **Interquartile Range (IQR)** method specifically to the `creatinine_phosphokinase` column.
* **Outcome**: A total of **29 outliers** were flagged and pruned from the set.
* **Refined Dataset**: The record count moved from 299 down to a cleaner **270 samples**.

### 4. Feature Scaling (Normalization)
To prevent features with larger scales from dominating the model, we implemented two standardization techniques:
* **Min-Max Scaling**: Squashed values for variables like `age` and `time` into a uniform range between $0$ and $1$.
* **Z-Score Normalization**: Adjusted the features so they center at a **Mean of 0** with a **Standard Deviation of 1**.

### 5. Dimensionality Reduction (PCA)
To streamline the dataset without losing its "essence," we utilized **Principal Component Analysis** (PCA):
* **Variance Captured**: The first two Principal Components together accounted for **43.88%** of the total information.
* **PC1 Strength**: The primary component alone represented **24.12%** of the data's variance.
* **Benefit**: This transformation creates uncorrelated variables, which can speed up training and prevent overfitting in future models.

---

## Core Statistics
| Attribute | Result |
| :--- | :--- |
| **Initial Records** | 299 |
| **Outliers Excised** | 29 |
| **Handling Missing Data** | Median Replacement |
| **PC1 Explained Variance** | 24.12% |

---

## Repository Contents
* `Lab4.ipynb`: The Jupyter Notebook containing all Python preprocessing logic.
* `waleed.csv`: The source clinical dataset.
* `README.md`: A summary of the project methodology.
