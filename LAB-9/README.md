# Lab 9: Random Forest Classification
**Loan Repayment Prediction Using LendingClub Data**

---

## Problem Statement
The goal of this project is to explore publicly available data from **LendingClub.com** (2007-2010) to create a model that predicts the probability of a borrower paying back their loan in full. This is a binary classification problem where we aim to identify reliable borrowers for potential investors.

*   **Target Variable:** `not.fully.paid` (1 if the loan was not paid back, 0 if it was)
*   **Problem Type:** Binary Classification
*   **Dataset Size:** 9,578 entries

---

## Dataset Features
The dataset includes 13 features describing the financial profile and credit history of the borrowers:

| # | Feature | Description |
|---|---------|-------------|
| 1 | `credit.policy` | 1 if customer meets underwriting criteria, 0 otherwise |
| 2 | `purpose` | Categorical: credit_card, debt_consolidation, etc. |
| 3 | `int.rate` | Interest rate of the loan (as a proportion) |
| 4 | `installment` | Monthly installments owed |
| 5 | `log.annual.inc` | Natural log of the self-reported annual income |
| 6 | `dti` | Debt-to-income ratio |
| 7 | `fico` | FICO credit score |
| 8 | `days.with.cr.line` | Number of days the borrower has had a credit line |
| 9 | `revol.bal` | Revolving balance |
| 10 | `revol.util` | Revolving line utilization rate |
| 11 | `inq.last.6mths` | Number of inquiries by creditors in the last 6 months |
| 12 | `delinq.2yrs` | Times 30+ days past due in the past 2 years |
| 13 | `pub.rec` | Number of derogatory public records |
| 14 | `not.fully.paid` | **Target Variable** (0 = Paid in full, 1 = Not paid) |

---

## Steps Performed
1.  **Data Loading** — Imported `loan_data.csv` using Pandas.
2.  **Exploratory Data Analysis (EDA)** — Visualized FICO distributions based on `credit.policy` and `not.fully.paid` using Seaborn histograms.
3.  **Categorical Variable Handling** — Transformed the `purpose` column into dummy variables using `pd.get_dummies()` to make it compatible with Scikit-Learn.
4.  **Train-Test Split** — Divided data into training and testing sets (standard 70/30 split).
5.  **Decision Tree Model** — Trained a single `DecisionTreeClassifier` as a baseline model.
6.  **Random Forest Model** — Trained a `RandomForestClassifier` to compare performance against the single tree.
7.  **Evaluation** — Generated Confusion Matrices and Classification Reports for both models to analyze precision, recall, and f1-score.

---

## Key Findings

| Finding | Detail |
|---------|--------|
| **EDA Insight** | Borrowers with higher FICO scores are more likely to meet the credit policy criteria. |
| **Data Prep** | Converting categorical "Purpose" into numerical dummy variables was necessary for model training. |
| **Model Comparison** | The Random Forest model generally outperformed the single Decision Tree in overall accuracy and stability. |
| **Class Imbalance** | The model's performance on the "not paid" class (1) is influenced by the fact that most loans in the dataset were paid in full. |

---

## Libraries Used
*   **Pandas**: For data manipulation and reading CSV files.
*   **NumPy**: For numerical computing.
*   **Matplotlib / Seaborn**: For data visualization (histograms, countplots, and jointplots).
*   **Scikit-learn**: For data splitting, Decision Tree/Random Forest modeling, and performance metrics.
