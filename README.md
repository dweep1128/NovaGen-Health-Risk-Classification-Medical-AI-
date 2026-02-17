# 🏥 NovaGen Health Risk Classification

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-XGBoost-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Metric](https://img.shields.io/badge/Recall-91%25-red)

## 📌 Project Overview
**NovaGen Research Labs** requires a predictive model to identify individuals at high health risk to optimize clinical trial selection.

This project builds a **Binary Classification Model** to predict whether a patient is **"Healthy"** or **"At Risk"**.
Unlike standard datasets, this project involved a unique challenge: **Synthetic Data Anomalies**, where biological intuition clashed with statistical reality, requiring a rigorous data-centric approach.

---

## ⚠️ The "Synthetic Data" Anomaly (Key Insight)
In real-world medical scenarios, factors like **Smoking**, **Alcohol**, and **Sleep** are strong predictors of health. However, during Exploratory Data Analysis (EDA), I discovered a critical discrepancy:

* **Expectation:** Lifestyle choices correlates with Health Risk.
* **Reality:** 15 out of 22 features (including Smoking/Alcohol) had a **near 0.0 correlation** with the target.

**Decision:** Instead of forcing "domain knowledge" onto the model, I trusted the **Correlation Matrix** and mathematical feature importance. I removed the low-signal "noise" features to prevent overfitting, proving that in synthetic environments, **Data > Intuition**.

---

## 🛠️ Tech Stack & Workflow

* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, XGBoost, Seaborn, Matplotlib
* **Techniques:** SMOTE (imbalance handling), GridSearchCV, Feature Engineering

### Workflow:
1.  **EDA & Cleaning:** Analyzed distributions and dropped zero-variance features.
2.  **Feature Engineering:** Focused on high-impact physiological markers.
3.  **Model Selection:** Chose **XGBoost** over Random Forest for its superior handling of non-linear relationships.
4.  **Hyperparameter Tuning:** Used `GridSearchCV` to optimize `learning_rate`, `max_depth`, and `n_estimators`.

---

## 📊 Model Performance

The primary goal was to maximize **Recall** for the "At Risk" class (Class 1), because in healthcare, **False Negatives (missing a sick patient) are dangerous**.

| Metric | Base Model | **Final Tuned Model** |
| :--- | :--- | :--- |
| **Accuracy** | 88.0% | **89.1%** |
| **Recall (Class 1)** | 0.87 | **0.91** 🚀 |
| **Precision** | 0.88 | **0.89** |
| **F1-Score** | 0.88 | **0.90** |

> **Business Impact:** The model successfully identifies **91% of high-risk patients**, ensuring NovaGen captures the vast majority of the target population for their studies.

---

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/yourusername/novagen-classification.git](https://github.com/yourusername/novagen-classification.git)

