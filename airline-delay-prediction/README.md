# Airline Delay Prediction
**A Machine Learning Approach to Minimizing Airline Losses & Improving Customer Satisfaction**
`UC Berkeley · May 2025`

---

## Overview

Built and evaluated machine learning models to predict flight delays using a multi-year 
dataset combining airline, weather, station, and airport data — processed on Databricks 
for distributed computing. The team's final XGBoost model achieved **85.3% F1-score**.

---

## Contents

| File | Description |
|------|-------------|
| `phase1-report.html` | EDA phase — exploratory analysis across all data sources |
| `phase2-report.html` | Modeling phase — data merging, imputation, and initial model training |
| `phase3-report.html` | Final phase — model comparison, feature importance, and results |
| `presentation.pdf` | Project presentation slides |

---

## My Contributions

**Phase 1 — EDA**
- Performed exploratory data analysis on station data

**Phase 2 — Data Preparation & Modeling**
- Applied imputation techniques to address missing values in station dataset
- Built, fine-tuned, and evaluated Logistic Regression classifiers

**Phase 3 — Final Modeling**
- Built and fine-tuned Logistic Regression and Random Forest classifiers
- Conducted hyperparameter optimization
- Evaluated model performance using precision, recall, F1-score, and ROC-AUC

---

## Key Results

- **Final model:** XGBoost — **85.3% F1-score**
- 4 ML algorithms evaluated: Logistic Regression, Random Forest, MLP, XGBoost
- Hyperparameter tuning via time-series cross-validation with Optuna
- Collaborated on Databricks for distributed data processing and model training

---
