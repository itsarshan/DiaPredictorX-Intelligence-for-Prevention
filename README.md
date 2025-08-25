# DiaPredictorX-Intelligence-for-Prevention
DiaPredictorX is a robust machine learning pipeline built to assess diabetes risk from routine clinical and demographic data. Designed for early detection, it equips users—whether individuals or healthcare professionals—with accurate risk assessments and actionable advice

## Dataset
The dataset contains 768 samples and 9 features including:
- Pregnancies
- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI
- DiabetesPedigreeFunction
- Age
- Outcome (target label: diabetes presence)

## Steps & Pipeline

### 1. Import Libraries
Essential libraries include pandas, numpy, matplotlib, seaborn for data handling and visualization, along with scikit-learn for ML modeling, preprocessing, hyperparameter tuning, and calibration.

### 2. Load and Clean Data
The dataset is loaded from `diabetes.csv`. Invalid zero values in some medical features are replaced with NaNs for imputation later.

### 3. Split Data
A stratified train-test split is performed preserving the outcome distribution (80% train, 20% test).

### 4. Preprocessing Pipelines
Two numeric transformers are built:
- For Logistic Regression: median imputation + standard scaling
- For Tree-based models: median imputation only (no scaling)

### 5. Model Pipelines
- Logistic Regression with class-weight balancing
- Random Forest and Gradient Boosting with hyperparameter tuning grids

### 6. Hyperparameter Search
Fast grid/randomized search using StratifiedKFold cross-validation on a subsample of training data to find best parameters.

### 7. Model Evaluation
For each model, metrics reported are accuracy, ROC-AUC, precision-recall AUC, alongside confusion matrix, ROC curve, and precision-recall curve plots.

### 8. Probability Calibration
Platt scaling calibration applied to best model for reliable probability outputs, evaluated by Brier score and ROC-AUC.

### 9. Risk Tier Advisory
Probabilities are mapped into risk tiers (High, Moderate, Low) with corresponding personalized health advice.

### 10. Inference Helper
A helper function to predict label, calibrated probability, risk tier, and advice based on input features.

### 11. Batch Scoring
Function for scoring entire datasets with risk flagging and advice.

### 12. Feature Importance
Feature importance plots using native and permutation importance specifically for Random Forest.

# Diabetes Prediction Machine Learning Project

## Overview
This project uses machine learning to predict the likelihood of diabetes based on health data. It leverages the Pima Indians Diabetes dataset to train models such as Logistic Regression, Random Forest, and Gradient Boosting. The models include probability calibration for better risk prediction.

## Dataset
The dataset contains 768 samples and 9 features including:
- Pregnancies
- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI
- DiabetesPedigreeFunction
- Age
- Outcome (target label: diabetes presence)

## Steps & Pipeline

### 1. Import Libraries
Essential libraries include pandas, numpy, matplotlib, seaborn for data handling and visualization, along with scikit-learn for ML modeling, preprocessing, hyperparameter tuning, and calibration.

### 2. Load and Clean Data
The dataset is loaded from `diabetes.csv`. Invalid zero values in some medical features are replaced with NaNs for imputation later.

### 3. Split Data
A stratified train-test split is performed preserving the outcome distribution (80% train, 20% test).

### 4. Preprocessing Pipelines
Two numeric transformers are built:
- For Logistic Regression: median imputation + standard scaling
- For Tree-based models: median imputation only (no scaling)

### 5. Model Pipelines
- Logistic Regression with class-weight balancing
- Random Forest and Gradient Boosting with hyperparameter tuning grids

### 6. Hyperparameter Search
Fast grid/randomized search using StratifiedKFold cross-validation on a subsample of training data to find best parameters.

### 7. Model Evaluation
For each model, metrics reported are accuracy, ROC-AUC, precision-recall AUC, alongside confusion matrix, ROC curve, and precision-recall curve plots.

### 8. Probability Calibration
Platt scaling calibration applied to best model for reliable probability outputs, evaluated by Brier score and ROC-AUC.

### 9. Risk Tier Advisory
Probabilities are mapped into risk tiers (High, Moderate, Low) with corresponding personalized health advice.

### 10. Inference Helper
A helper function to predict label, calibrated probability, risk tier, and advice based on input features.

### 11. Batch Scoring
Function for scoring entire datasets with risk flagging and advice.

### 12. Feature Importance
Feature importance plots using native and permutation importance specifically for Random Forest.

## Usage

1. Ensure `diabetes.csv` is in the working directory.
2. Install dependencies:
