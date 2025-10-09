# Credit Card Fraud Detection: A Methodological Study (work in progress)

## Objective

This project is a study of the Kaggle credit card fraud detection dataset. The primary goal is to develop a performing XGBoost model for this severely imbalanced dataset, while maintaining strict **methodological rigor**.

The approach focuses on **eliminating Data Leakage risk** during the preprocessing, scaling and hyperparameter optimization via Cross-Validation (CV) phases.

***

## Dataset and Source

The data is sourced from the public "Credit Card Fraud Detection" dataset:

* **Source:** https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

*(Note: The raw data file is not included in this repository due to its size.)*

***

## Methodology and Key Steps (In Progress)

1. **Splitting:** Split the data using timeseriesplit to ensure good parctice and avoid bias on our model
2. **Optimization:** Searching for optimal hyperparameters for **XGBoost** via **Optuna**.
    a. Timsplitting inside pipeline
    b. A scaling step is integrated directly into an **`imblearn` Pipeline** passed to the CV, guaranteeing that the scaling does not contaminate the validation folds.
3. **Param determination** obtention of the best hyperparameters  for our model using the ROC AUC as metric
4. **Data Preparation:** Applying the **RobustScaler** according to the `fit_transform` on the global *Train* and `transform` on the *Test* rule to prevent any leakage.
5. **Evaluation:** Final performance measurement (Recall, ROC AUC) on a pure hold-out test set.

***

## Current Status

* [✅] Exploratory Data Analysis (EDA) and Initial Preparation complete.
* [🛠] **In Progress:** Hyperparameter Optimization (XGBoost Pipeline) via Optuna.
* [⬜️] Final Training and Evaluation on the Test Set.