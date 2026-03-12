<div align="center">

# Lab 5: Feature Engineering (Classification)
**Order Status Prediction using a Talabat-style Orders Dataset**

</div>

## Student Tasks

### Task 1: New Engineered Feature
**Feature Created:** `price_ratio` 

**Justification:** The `price_ratio` feature captures the "economic value density" of an order. It measures the financial incentive relative to the delivery effort. A low-priced order requiring a long delivery distance may be more prone to driver cancellations or "In Transit" delays due to lower incentive. Conversely, high-value orders over short distances are often prioritized, leading to a higher likelihood of "Delivered" outcomes.

---

### Task 2: Alternative `is_peak_hour` Rule
**New Rule:** Created `is_peak_hour_v2` to include both lunch (12:00–14:00) and dinner (18:00–21:00) windows.

**Discussion:** By incorporating the lunch rush, the model accounts for a second major wave of high demand. Traffic congestion and driver shortages during lunch affect delivery times and cancellation rates in a similar way to the dinner rush, providing the model with a more complete picture of peak-hour pressures.

---

### Task 3: Adjusting `top_k` for `Item_Name_reduced`
**Values Tested:** `top_k` = 10, 30, and 50.

**Comparison & Results:** * **Accuracy:** Modifying the `top_k` items resulted in the exact same accuracy of **0.8519** across all three variations.
* **Discussion:** This indicates that the `Item_Name` feature has very low predictive power regarding `Order_Status`. The Random Forest classifier relies heavily on stronger predictors (such as distance or traffic) and effectively ignores the item name. Consequently, increasing the granularity of food categories does not provide new, useful patterns for the model to learn from.

---

### Task 4: Feature Selection using `SelectFromModel`
**Discussion:** Feature selection proved highly beneficial for model optimization. The `OneHotEncoder` generates numerous dummy columns for categories like `City` and `Payment_Method` that often have near-zero predictive power. Filtering out this noise with `SelectFromModel` forces the Random Forest to focus exclusively on strong signals (like distance and traffic). This results in a simpler, faster model that is less prone to overfitting without sacrificing overall accuracy.
