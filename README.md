# LightGBM Multiclass Classification

## Overview

This project focuses on developing and evaluating a multiclass classification model using **LightGBM** in R.

The objective was to build a high-performing model capable of classifying observations into **26 different classes**. The project covers data preparation, model configuration, cross-validation, hyperparameter tuning, and model evaluation.

## Technologies & Libraries

- **R**
- **LightGBM** – gradient boosting framework
- **caret** – machine learning utilities
- **tidyverse** – data manipulation
- **data.table** – efficient data handling
- **MLmetrics** – classification metrics
- **pROC** – ROC curves and AUC calculation

## Dataset

- 6,238 observations
- 617 input features
- 26 target classes

The dataset was provided as part of a university assignment and is not included in this repository.

## Methodology

### 1. Data Preparation
- Loaded and prepared the dataset.
- Removed an unnecessary index column.
- Split the data into training (80%) and test (20%) sets.
- Converted target labels into numerical values starting from 0, as required by LightGBM.

### 2. Model Configuration & Training

Implemented a multiclass classification model using LightGBM.

Selected hyperparameters:

| Parameter | Value |
|---|---:|
| Objective | multiclass |
| Learning rate | 0.03 |
| Number of leaves | 50 |
| Minimum data in leaf | 25 |
| Maximum depth | -1 |
| L1 regularization | 0.2 |
| L2 regularization | 2 |
| Feature fraction | 0.6 |
| Bagging fraction | 0.8 |

### 3. Cross-Validation & Hyperparameter Tuning

Used **5-fold stratified cross-validation** on the training set to evaluate model performance and determine the optimal number of boosting iterations.

- Maximum number of iterations: 2,000
- Early stopping: 10 rounds without improvement
- Evaluation metric: Multi-class Log Loss

The final model was trained using **1,110 boosting iterations**.

### 4. Model Evaluation

Evaluated model performance using the following metrics:

- Accuracy
- F1-score (F-beta, β = 1)
- Matthews Correlation Coefficient (MCC)
- Macro-averaged Area Under the ROC Curve (AUC)

A learning curve based on multi-class log loss was also generated to examine model convergence and potential overfitting.

## Results

<escape>**Test Accuracy: 96.07%**</escape>

| Metric | Training Set | Test Set |
|---|---:|---:|
| Accuracy | 100% | 96.07% |
| F1-score | – | 97.64% |
| MCC | – | 0.9592 |
| Macro AUC | – | 0.9995 |

The model achieved strong classification performance across all evaluated test metrics.

## Model Comparison

LightGBM was also compared with other machine learning algorithms:

- XGBoost
- Random Forest
- AdaBoost

LightGBM achieved the best overall results among the tested algorithms while also requiring less training time.

## Key Learning Outcomes

- Practical application of gradient boosting for multiclass classification.
- Model configuration and hyperparameter tuning.
- Stratified cross-validation and early stopping.
- Evaluation using multiple classification metrics.
- ROC and AUC analysis for multiclass classification.
- Learning curve analysis and model comparison.
