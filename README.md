# 👊 Newton Competition 1401 - Quera

This repository contains complete solutions for **two questions** from the [Newton-0401 Data Science Competition](https://quera.org/events/newton-0401) hosted by **Quera**.

---

## 🔍 Overview

The competition presents two challenges based on real-world datasets:

1. **Online Store Discounts** (Question 1)
2. **Electricity Consumption Forecasting** (Question 2)
3. **Diabetes Prediction** (Question 3)

Each part includes a dataset, a notebook with data exploration and modeling, and final predictions suitable for submission to the competition platform.

---

## 🅰 Question 1: Online Store Discounts

### 📂 Files:
- Online Store Discounts.ipynb: Jupyter notebook for discount analysis.
- tarikhche_kharid.csv: Purchase history of online store customers.

### 🎯 Objectives:
- Analyze customer behavior with respect to discount usage.
- Understand patterns in purchasing with/without discounts.
- Recommend effective discounting strategies.

### ⚙️ Methodology:
- Data cleaning (handling missing values, date formatting).
- Feature extraction (e.g., month, weekday, discount percent).
- Aggregation by customer and period.
- Visualization of:
  - Monthly purchase trends
  - Distribution of discount usage
  - Customer activity patterns

### 📈 Insights:
- Discounts tend to increase purchase frequency during promotional windows.
- Certain customers are highly responsive to even small discounts.
- Weekdays and holidays show notable variations in purchase volume.

---

## 🅱 Question 2: Electricity Consumption Forecasting

### 📂 Files:
- electricity_consumption.ipynb: Forecasting electricity usage with ML models.
- train.csv: Weekly electricity usage for training.
- test.csv: Unlabeled data for prediction and submission.

### 🎯 Objectives:
- Forecast weekly electricity consumption.
- Optimize model performance using r2_score as the main metric (required to be > 0.6).

### ⚙️ Methodology:
- **Feature Engineering**:
  - Time-based features (month, week, day of week)
  - Lag features (previous weeks' consumption)
  - Rolling statistics (moving averages)
- **Modeling**:
  - Models evaluated: LinearRegression, DecisionTree, RandomForest, XGBoost
  - Parameter tuning with GridSearchCV
  - Metrics: MSE and R² Score

### 🏁 Final Results:

| Model           | MSE         | R² Score   |
|----------------|-------------|------------|
| LinearRegression | 288.33     | 0.8931     |
| DecisionTree     | 159.47     | 0.9409     |
| RandomForest     | 38.45      | 0.9858     |
| XGBoost          | 4.36       | 0.9984     |

✅ **Selected Model**: XGBoost with tuned hyperparameters  
📌 **Final R² Score**: **0.998**  
📌 **Test Predictions Format**:

## 🆎 Question 3: Diabetes Prediction

### 📂 Files:
- `diabet.ipynb`: Complete modeling notebook for diabetes classification.
- `diabetes.csv`: Patient-level medical dataset with diagnosis labels.
- `submission.csv`: Final test predictions formatted for competition submission.

### 🎯 Objectives:
- Predict whether a person has:
  - **Type 1 Diabetes** → label `1`
  - **Type 2 Diabetes** → label `2`
- Maximize **F1-Score (Macro)** as the main evaluation metric  
- F1-Score is rounded to **three decimal digits ×100** for competition grading

---

### ⚙️ Methodology:

#### 🔹 Data Cleaning & Preprocessing:
- **Dropped Redundant Columns**: e.g., `Health_region_grouped`, `Total_physical_act_time`
- **Handled Dirty/Missing Values**:
  - Replaced abnormal placeholders like `9996`, `9999.6`, `96`, `99` with `NaN`
  - Imputed missing values using **normal distribution sampling** (mean ± std, clipped)
- **Class Label Adjustment**:  
  - For compatibility with some models (like XGBoost), mapped labels from `{1, 2}` → `{0, 1}`

#### 🔹 Feature Engineering:
- Correlation analysis to identify most predictive features
- Removed low-correlation or redundant features
- Detected and clipped extreme values

---

### 🧪 Modeling Strategy:

#### Baseline:
- **Logistic Regression**:
  - With and without class weighting
  - Best tuned F1 Macro Score: **0.7387**

#### Advanced Modeling & Grid Search:
Tested using **StratifiedKFold (5-fold)** CV and `f1_macro` scoring:

| Model          | F1 Macro (Validation) | Best Parameters |
|----------------|------------------------|------------------|
| RandomForest   | **0.7403** ✅           | `max_depth=20`, `n_estimators=300`, `class_weight=balanced` |
| CatBoost       | 0.7382                 | `depth=6`, `iterations=100`, `learning_rate=0.1`, `scale_pos_weight=1` |
| XGBoost        | 0.7374                 | `max_depth=3`, `n_estimators=100`, `learning_rate=0.1`, `scale_pos_weight=1` |

---

### ✅ Final Model:

- **Selected Model**: `RandomForestClassifier` with tuned hyperparameters  
- **Final Macro F1-Score**: **0.7403** → **Score: 74.0** for competition  

---


# 👽 Notes
- All data is synthetic and provided by Quera for educational competition purposes.
- Evaluation metric for Q2 is r2_score with a passing threshold of 0.6.
---
👤 Author
Prepared by [OMID Moradi]

📅 Newton Data Science Challenge – Spring 1401

🏁 Hosted on: Quera 