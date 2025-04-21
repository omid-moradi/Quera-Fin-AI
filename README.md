# 👊 Newton Competition 1401 - Quera

This repository contains complete solutions for **two questions** from the [Newton-0401 Data Science Competition](https://quera.org/events/newton-0401) hosted by **Quera**.

---

## 🔍 Overview

The competition presents two challenges based on real-world datasets:

1. **Online Store Discounts** (Question 1)
2. **Electricity Consumption Forecasting** (Question 2)

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


# 👽 Notes
- All data is synthetic and provided by Quera for educational competition purposes.
- Evaluation metric for Q2 is r2_score with a passing threshold of 0.6.
---
👤 Author
Prepared by [OMID Moradi]

📅 Newton Data Science Challenge – Spring 1401

🏁 Hosted on: Quera 