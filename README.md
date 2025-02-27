# Insurance Price Prediction - Machine Learning Project

## Problem Statement
Accurately predicting health insurance costs is critical for fair pricing and financial planning. Traditional methods often fail to capture complex interactions between demographic factors (age, BMI, smoking status) and medical expenses. This project addresses the challenge of building a robust predictive model using machine learning to estimate individual insurance charges.

## Objectives
1. **Analyze Drivers**: Identify key factors influencing medical costs (e.g., smoking status, BMI)
2. **Model Comparison**: Evaluate 8+ regression algorithms for predictive accuracy
3. **Optimize Performance**: Achieve R² > 0.8 through feature engineering and model tuning
4. **Actionable Insights**: Provide data-driven recommendations for insurance pricing

## Dataset Overview
**Source:** [Insurance Dataset](https://www.kaggle.com/datasets/mirichoi0218/insurance)  
**Records:** 1,337 (after cleaning)  
**Features:**

| Column      | Type    | Description                     | Key Stats            |
|-------------|---------|---------------------------------|----------------------|
| age         | int64   | Policyholder age               | Range: 18-64 years   |
| sex         | object  | Gender                         | Male: 50.4%, Female: 49.6% |
| bmi         | float64 | Body Mass Index                | Mean: 30.66 kg/m²    |
| children    | int64   | Number of dependents           | 0-5 (73% have ≤2)    |
| smoker      | object  | Tobacco usage                  | Smokers: 20.5%       |
| region      | object  | US geographic region           | 4 regions (balanced) |
| charges     | float64 | **Target** - Medical expenses  | Max: $63,770         |

## Key Technical Steps
1. **Data Preparation**
   - Removed 1 duplicate entry
   - One-Hot Encoded categorical features (sex, smoker, region)
   - Standardized numerical features (age, bmi, children)

2. **Model Development**
   - Split data: 70% training / 30% testing
   - Evaluated 8 algorithms:
     - Linear Regression (Baseline)
     - Tree-Based: Decision Tree, Random Forest, XGBoost, Gradient Boosting
     - Other: KNN, SVM, AdaBoost
   - Metrics: RMSE & R²

## Results Summary
| Model                  | RMSE   | R²    | Inference Time (ms) |
|------------------------|--------|-------|---------------------|
| Gradient Boosting      | 4,736  | 0.84  | 12                  |
| XGBoost                | 5,266  | 0.82  | 18                  |
| Random Forest          | 5,435  | 0.78  | 22                  |
| Linear Regression      | 6,240  | 0.63  | 3                   |

**Critical Insights:**
- Smokers pay **3.8x higher** premiums on average
- BMI >35 correlates with **52% cost increase**
- Regional differences account for <5% of variance


