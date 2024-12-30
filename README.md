# Weather Prediction Using Machine Learning

This repository contains a machine learning project aimed at predicting daily temperatures (in degrees Celsius) using a large weather dataset. The dataset contains a mix of numerical and categorical variables describing various weather characteristics for given days.

## Overview

The goal of this project was to build an accurate regression model for predicting temperature. The process involved extensive data cleaning, feature engineering, and modeling using multiple machine learning techniques. The Random Forest Regression model was ultimately selected as the best-performing model.

---

## Project Workflow

### 1. **Data Exploration and Cleaning**
- **Dataset Size**: 96,453 samples, 108 features.
- **Initial Issues**:
  - Numerical features were stored as strings.
  - Null values were present in multiple features.
  - Duplicate samples were identified and removed.
- **Steps Taken**:
  - Converted numerical inputs to appropriate formats.
  - Filled null values with the median for their respective features.
  - Removed 241 duplicate rows, reducing the dataset size to 96,212 samples.
  - Standardized numerical features to ensure equal weighting in modeling.
  - Converted categorical features:
    - Extracted time-based features (Year, Month, Day, Hour, Minute) from the `Formatted Date`.
    - Encoded `Daily Summary` using label encoding.

---

### 2. **Feature Selection**
- Used ANOVA scoring to evaluate feature importance.
- Retained the top 10 features with the highest scores, including both encoded categorical variables and numerical variables.

---

### 3. **Modeling**
- **Regression Models Tested**:
  - Linear Regression, Lasso Regression, Ridge Regression
  - KNN Regression
  - Decision Tree Regression, Bagging Regression, Random Forest Regression
  - Adaboost Regression, Gradient Boosting Regression
- **Evaluation Metrics**:
  - Root Mean Squared Error (RMSE)
  - R² score
  - Cross-validated RMSE (with standard deviation)

---

### 4. **Results**
- Tree-based models significantly outperformed linear regression models.
- Random Forest Regression emerged as the best model with the following metrics:
  - **Average Cross-Validated RMSE**: 2.57
  - **Average Cross-Validation Standard Deviation**: 0.023
  - **R² (Train)**: 0.991
  - **R² (Test)**: 0.934
- Interpretation: The model predicts temperatures within an average error of ±2.5°C with low variance and high explanatory power for the variability in temperature.

---

## Key Learnings
- Data cleaning and preprocessing are critical and time-intensive for successful machine learning projects.
- Working with large datasets requires optimization to minimize computational costs.
- Hyperparameter tuning can significantly enhance model performance but is constrained by computational resources.
- Random Forest Regression proved robust for this dataset, providing accurate predictions with low variance.

---

## Future Improvements
- Implement more advanced hyperparameter tuning methods.
- Explore additional models such as Support Vector Regression (excluded due to computational constraints).
- Optimize code to reduce run times for large datasets.

---
