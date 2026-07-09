# Data Science with Python

A collection of data science projects completed in Python, covering the full workflow from data cleaning and exploratory analysis to machine learning model development and evaluation.

## Projects

### 1. Chatbot Performance Prediction

A regression project predicting two AI chatbot performance metrics — conversation-length handling capacity and simultaneous task-processing capacity — from technological and operational system features.

- **Techniques:** EDA, target encoding, Yeo-Johnson power transform, min-max scaling, PCA, Linear & Poisson regression, Polynomial regression with Ridge/Lasso regularization, multi-output prediction via `RegressorChain`
- **Best result:** Polynomial regression + Lasso achieving **R² = 0.84** on the test set
- **Tech stack:** pandas, NumPy, scikit-learn, matplotlib, seaborn

### 2. Rainfall Data Analysis

A data cleaning and exploratory analysis project examining daily rainfall records from 2013–2023 to uncover long-term trends and patterns.

- **Techniques:** Data cleaning (handling messy dates, invalid values, outliers), reshaping and aggregation, time-series trend analysis, visualization
- **Key finding:** 2020 was the wettest year on record (786.8 mm) while 2019 was the driest (374.4 mm)
- **Tech stack:** pandas, matplotlib

## Note

These projects were completed as part of coursework applying and extending core data science concepts — regression modeling, regularization, dimensionality reduction, data cleaning, and exploratory data analysis — using Python's data science stack.
