# LightGBM Multiclass Classification

## Project Overview

This project focuses on building, training, and evaluating a multiclass classification model using **LightGBM** in R.

The objective was to develop a high-performing classification model capable of predicting one of 26 classes. The project covers the complete machine learning workflow, from data preparation and model tuning to performance evaluation.

## Technologies & Libraries

- **R**
- **LightGBM** – gradient boosting framework
- **caret** – machine learning utilities
- **tidyverse** – data manipulation
- **data.table** – efficient data handling
- **MLmetrics** – model evaluation metrics
- **pROC** – ROC curves and AUC calculation

## Project Workflow

### 1. Data Preparation
- Loaded and inspected the dataset.
- Removed unnecessary columns.
- Split the data into training (80%) and test (20%) sets.
- Converted target labels into numerical values required by LightGBM.

### 2. Model Training & Hyperparameter Tuning
- Implemented a multiclass LightGBM classifier.
- Used 5-fold stratified cross-validation.
- Applied early stopping to determine the optimal number of boosting iterations.
- Tuned model hyperparameters, including:
  - Learning rate: 0.03
  - Number of leaves: 50
  - Minimum data in leaf: 25
  - Feature fraction: 0.6
  - L1 and L2 regularization

### 3. Model Evaluation

The model was evaluated using multiple classification metrics:

- Accuracy
- F1-score (F-beta score, β = 1)
- Matthews Correlation Coefficient (MCC)
- Area Under the ROC Curve (AUC), calculated using macro averaging
- Training vs. test accuracy comparison

A learning curve based on multi-class log loss was also used to assess model convergence and potential overfitting.

### 4. Model Comparison

LightGBM was compared against several alternative machine learning algorithms:

- XGBoost
- Random Forest
- AdaBoost

LightGBM achieved the best overall results while requiring less training time than the tested alternatives.

## Results

<escape>**Test accuracy: 96%**</escape>

The model achieved strong classification performance across the evaluated metrics. The comparison with other algorithms showed that LightGBM provided the best balance between predictive performance and training time.

## Key Learning Outcomes

- Practical application of gradient boosting for multiclass classification.
- Hyperparameter tuning and cross-validation.
- Model evaluation using multiple classification metrics.
- Understanding of overfitting and learning curves.
- Comparison of different machine learning algorithms.

## Dataset

The dataset was provided as part of a university assignment. It is not included in this repository.
