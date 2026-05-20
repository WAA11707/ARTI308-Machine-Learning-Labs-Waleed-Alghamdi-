# 💳 LAB-11: Customer Segmentation Using K-Means
### *Behavioral Clustering of Credit Card Holders*

<div align="center">

![Task](https://img.shields.io/badge/Task-Clustering-DB7093?style=for-the-badge)
![Data](https://img.shields.io/badge/Dataset-Credit_Card_Usage-blueviolet?style=for-the-badge)
![Library](https://img.shields.io/badge/Tools-Scikit--Learn-orange?style=for-the-badge)

</div>

---

## 📝 Project Overview
This project applies unsupervised machine learning techniques—specifically **K-Means Clustering**—to segment credit card users based on their spending, payment patterns, and cash advance behavior. Since the dataset contains no pre-existing target profiles, clustering allows us to uncover naturally hidden customer archetypes. These distinct groups can enable financial institutions to design highly personalized marketing campaigns, adjust credit lines, or offer custom rewards programs.

### Core Objectives
* **Examine** customer behavioral variables including balances, purchase frequencies, and installment usage.
* **Preprocess** raw customer profiles by dealing with missing values and scaling variances.
* **Determine** the optimal number of operational customer segments using statistical metrics.
* **Formulate** actionable business and marketing recommendations derived from cluster traits.

---

## 📊 Dataset Breakdown
The dataset captures the historical behavior of **8,950 active credit card holders** across 18 distinct variables:

| Feature | Description | Importance |
| :--- | :--- | :---: |
| `BALANCE` | The account balance remaining at the end of cycles. | **High** |
| `PURCHASES` | Total dollar value of purchases made from the account. | **High** |
| `CASH_ADVANCE` | Cash withdrawn upfront by the customer. | **High** |
| `PURCHASES_FREQUENCY` | How frequently purchases are being made (0 to 1 score). | Medium |
| `CREDIT_LIMIT` | The maximum credit allowance configured for the cardholder. | Medium |
| `PAYMENTS` | Total financial amount paid off by the user. | Medium |

---

## ⚙️ Technical Pipeline

### 1. Exploratory Data Analysis & Preprocessing
* **Missing Value Imputation:** Handled structural null fields located within `MINIMUM_PAYMENTS` and `CREDIT_LIMIT` columns gracefully.
* **Feature Pruning:** Eliminated uninformative metadata such as `CUST_ID` to focus structural metrics entirely on pure behavior.
* **Feature Scaling:** Implemented standard Z-score normalization via `StandardScaler` to remove dominant magnitude biases across vastly mismatched financial distributions.

### 2. Model Architecture & Optimization
* **Algorithm:** K-Means Clustering.
* **Hyperparameter Tuning (The Elbow Method):** Plotted **Within-Cluster Sum of Squares (WCSS)** against a spectrum of cluster candidates to isolate the direct inflection zone.
* **Validation Score:** Tracked the mathematical `silhouette_score` across setups to formally lock in structural cluster configurations.

### 3. Cluster Profile Extraction
* Integrated labels back onto core frames to map multi-dimensional geometric centroids.
* Generated comprehensive distribution comparisons using `sns.countplot` and mean statistical aggregation to highlight distinctive cluster behaviors.

---

## 🚀 Key Insights & Marketing Strategies

The final model successfully grouped credit card holders into distinct, actionable behavior segments:

* **Cluster 1: The VIP Premium Spenders**
  * *Traits:* Exhibit the highest average purchase amounts, maximum credit limits, and most frequent card interactions.
  * *Strategy:* Offer high-tier reward points, exclusive concierge upgrades, luxury partnerships, and invitation-only credit line extensions.
* **Cluster 2: The Cash-Advance Reliant Group**
  * *Traits:* Uniquely characterized by significantly elevated cash withdrawal frequencies and amounts, accompanied by low shopping purchases.
  * *Strategy:* Promote structured low-interest cash withdrawal periods or financial management features to mitigate default risk.
* **Cluster 3: The Dormant / Low-Engagement Users**
  * *Traits:* Minimal overall activity, low balance maintenance, and sparse usage frequencies.
  * *Strategy:* Launch targeted "re-engagement" email sequences embedded with retail partner discount vouchers or activation incentives to make the card their daily choice.

---

## 🛠️ Stack & Dependencies
* **Data Handling:** `Pandas`, `NumPy`
* **Clustering & Metrics:** `Scikit-learn (KMeans, StandardScaler, silhouette_score)`
* **Visualization:** `Seaborn`, `Matplotlib`
