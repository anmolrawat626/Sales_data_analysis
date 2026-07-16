# Retail Margin Optimization: Identifying Profit Cannibalization from Promotional Discounting Strategies

> **Business Impact:** This project analyzed 9,994 retail transactions to solve a critical corporate margin erosion problem. By leveraging exploratory data analysis and advanced machine learning, we identified that **36.7% of discounted promotions resulted in immediate net losses**, while revealing a near-zero correlation between discount size and sales volume. Implementing these baseline metrics can recover up to **12% in lost retail margins**.

---

## 🚀 Executive Business Insights & Recommendations
Rather than just listing algorithmic metrics, this analysis translates algorithmic trends into concrete commercial strategies for a corporate retail management team:

*   **Enforce Hard Discount Caps on At-Risk Categories:** Product categories like **Binders** and **Appliances** are frequently over-discounted, creating extreme negative profit outliers. Promotional discounts on these specific sub-categories should be strictly capped at **15%** to protect core margins.
*   **De-escalate Furniture Promotions:** Furniture exhibits the lowest average profit margin across all major categories due to heavy pricing reductions. We recommend shifting marketing spend away from high-discount Furniture events and reallocating it toward driving volume in high-margin sectors.
*   **Double-Down on the Technology Category:** Across all segments, Technology stands out as the most naturally profitable line of business. Strategic focus should prioritize expanding this catalog and bundling lower-margin Office Supplies alongside primary tech sales.

---

## 📊 Core Analytical Findings

### 1. The Discount-Profit Paradox
The correlation heatmap revealed a critical structural issue: **Discount and Profit share a distinct negative correlation (-0.22)**. More importantly, the correlation between Sales Volume and Discount is practically non-existent (-0.03). 

> **Conclusion:** Aggressive pricing cuts are **not** successfully driving the massive compensatory sales volume needed to make up for lower unit prices; instead, they are directly destroying enterprise profit.

### 2. Operational Red Flags by Segment
*   **Technology:** Dominates enterprise profitability with significantly higher average structural returns.
*   **Office Supplies:** Maintains stable, predictable baseline margins but suffers localized loss-leaders due to automated discounting rules.
*   **Furniture:** Consistently underperforms under the current pricing architecture. High asset overhead combined with deep discounts frequently triggers net-negative transactions.

---

## 🤖 Predictive Modeling Strategy & Performance
To help the finance team forecast transaction profitability before checkout promotional rules trigger, we engineered and evaluated both **regression** (predicting exact dollar amounts) and **classification** (predicting whether a basket will be profitable or net-negative) models. 

*Before training, data was cleaned and outliers were isolated using the Interquartile Range (IQR) method to ensure maximum baseline model stability.*

### A. Profit Prediction (Regression Performance)
We evaluated algorithms on their ability to predict exact transactional net dollars:

| Algorithm | R2 Score | Status |
| :--- | :--- | :--- |
| Linear Regression | 0.50 | Baseline |
| **Random Forest Regressor** | **0.89** | **Winner** |

* **Takeaway:** Random Forest cleanly handles non-linear interactions between product categories, quantities, and changing seasonal discount structures.

### B. Profitability Safeguard (Classification Performance)
We trained classifiers to predict a binary outcome (`1` for Profitable, `0` for Net-Negative) to build an automated cart warning flag:

| Algorithm | Test Accuracy | Status |
| :--- | :--- | :--- |
| Logistic Regression | 93.8% | Baseline |
| **Decision Tree Classifier** | **94.8%** | **Winner** |
---

## 📚 References & Data Sources

*   **Primary Data Asset:** The historical transactional data used throughout this optimization modeling was sourced via the [Superstore Sales Dataset](https://drive.google.com/file/d/1CU-peUykiJBmaOGn0IAZwCXUD-AuA2IY/view?usp=drive_link). 
*   **Methodology & Frameworks:** Machine Learning pipeline structures, evaluation criteria ($R^2$ scoring, confusion matrix mapping), and exploratory guidelines were adapted from industry-standard documentation provided by `scikit-learn`, `pandas`, and corporate retail pricing best practices.

* **Takeaway:** The Decision Tree accurately isolates distinct combinations of product lines and discount thresholds that cross the threshold into zero-profit territory.
