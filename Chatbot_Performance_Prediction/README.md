# Chatbot Performance Prediction

A machine learning project that predicts two key performance metrics of an AI chatbot — **TARGET_Capacity** (conversation-length handling capacity) and **TARGET_CaseCount** (simultaneous task-processing capacity) — from a set of technological and operational system features.

## Overview

Data analysts often need to estimate chatbot performance based on measurable system characteristics (failure rates, latency, adoption metrics, infrastructure spend, etc.). This project builds and compares several regression approaches to make that prediction as accurate and generalizable as possible.

## Workflow

1. **Exploratory Data Analysis (EDA)**
   - Feature summary statistics, missing value checks, distribution analysis
   - Correlation analysis between features and both targets
   - Outlier detection via box plots
2. **Data Splitting & Pre-processing**
   - 60/20/20 train/validation/test split (holdout validation)
   - Target encoding for the high-cardinality `Country` feature (136 categories)
   - Power transform (Yeo-Johnson) to reduce skewness in heavily skewed features
   - Min-max scaling for uniform feature contribution
   - PCA explored for dimensionality reduction
3. **Baseline Models**
   - **Linear Regression** for `TARGET_Capacity`
   - **Poisson Regression** for `TARGET_CaseCount`
   - PCA component tuning and Ridge regularization tuning for both
4. **Polynomial Regression (degree 2)**
   - Applied to `TARGET_Capacity` only (300 engineered features)
   - Compared against PCA-reduced features
   - Tuned with Ridge and Lasso regularization to control overfitting
   - Best model: Polynomial regression + Lasso (≈73 features), achieving **R² = 0.84** on the test set with a low generalization gap
5. **Multi-output Prediction via RegressorChain**
   - Since `TARGET_Capacity` and `TARGET_CaseCount` are almost perfectly correlated (r ≈ 1), a `RegressorChain` uses the tuned Polynomial+Lasso model to predict `TARGET_Capacity`, then uses that prediction to derive `TARGET_CaseCount`
   - Achieves R² ≈ 0.84 on both targets on the held-out test set
6. **Final Predictions**
   - The trained pipeline (power transform → scaling → polynomial features → scaling → RegressorChain) is applied to `Eval.csv` to generate final predictions for both targets.

## Results Summary

| Model                         | Target           | Test MAE | Test RMSE | Test R²  |
| ----------------------------- | ---------------- | -------- | --------- | -------- |
| Linear Regression             | TARGET_Capacity  | 3.37     | 4.43      | 0.77     |
| Poisson Regression            | TARGET_CaseCount | —        | —         | ~0.7     |
| Polynomial Regression + Lasso | TARGET_Capacity  | ~2.85    | ~3.68     | **0.84** |
| RegressorChain (Poly+Lasso)   | Both targets     | <3       | <4        | **0.84** |

## Tech Stack

- Python, pandas, NumPy
- scikit-learn (LinearRegression, Ridge, Lasso, PoissonRegressor, PCA, PolynomialFeatures, RegressorChain)
- matplotlib, seaborn (visualization)

## Files

- `main.ipynb` — full analysis notebook (EDA, preprocessing, modeling, evaluation)
- `Data.csv` — training dataset
- `Eval.csv` — evaluation dataset for final predictions

## Author's Note

This project was completed as part of coursework (COSC2793, RMIT University), applying and extending lab exercises on regression modeling, regularization, and dimensionality reduction.
