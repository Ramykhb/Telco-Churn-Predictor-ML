# 📊 Telco-Churn-Predictor-ML

An end-to-end Machine Learning project designed to predict customer attrition. This repository features a **dual-lens approach**: a complete mathematical implementation of the ML lifecycle and a Scikit-Learn pipeline for industry-standard validation.

---

## 📌 Project Overview
The core of this project is a **Logistic Regression** engine built entirely in **NumPy**. Unlike most projects that rely on libraries for evaluation, this repository implements the **Confusion Matrix**, **Precision**, **Recall**, and **F1-Score** using raw matrix logic.

### The Dual-Approach Strategy
1.  **Mathematical Engine (NumPy):** Hand-coded Gradient Descent, L2 Regularization, and a custom Validation Suite.
2.  **Scikit-Learn Pipeline:** A production-ready implementation used to benchmark the accuracy of the manual approach.

---

## 🛠️ Technical Implementation

### 1. The "Pure Math" Approach (NumPy)
To demonstrate deep technical proficiency, the following were built without high-level ML libraries:
* **Optimization:** Vectorized Gradient Descent with **L2 Regularization (Ridge)** to penalize extreme weights and prevent overfitting.
* **Custom Validation Suite:** Built a manual evaluation framework to calculate:
    * **Confusion Matrix:** Manually identifying TP, TN, FP, FN counts.
    * **Metrics:** Hand-coded formulas for **Precision**, **Recall**, and **F1-Score**.
    * **Threshold Sweep:** A custom loop to test decision boundaries from 0.05 to 0.95.
* **Standardization:** Manual Z-score normalization using training-set statistics to prevent data leakage.



### 2. The Benchmark Approach (Scikit-Learn)
* Used `StandardScaler` and `LogisticRegression` to validate the custom engine.
* Results matched the custom engine within a **<1% margin**, proving the mathematical integrity of the NumPy implementation.

---

## 📈 Performance & Optimization

### Threshold Sweep
A standard 0.5 threshold is not always optimal for business. I performed a sweep of thresholds from **0.05 to 0.95** to find the "Sweet Spot" for the **F1-Score**.

| Metric | Peak Value | Optimal Threshold |
| :--- | :--- | :--- |
| **Accuracy** | 80.98% | 0.55 |
| **F1-Score** | 0.6026 | 0.40 |



### Feature Importance (The "Why")
The model identified the following top 3 predictors of churn:
1.  **Fiber Optic Internet:** Strongest positive correlation with churn.
2.  **Monthly Charges:** Higher costs significantly increase churn risk.
3.  **Electronic Check Payment:** Correlated with higher attrition compared to automated methods.
