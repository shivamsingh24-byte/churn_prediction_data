# Customer Churn Prediction - Preprocessing Report

## 1. Project Overview

This project aims to predict customer churn using machine learning techniques. Data preprocessing is a critical step to ensure the dataset is clean, consistent, and 
suitable for model training.


## 2. Dataset Description

* Dataset Name: Customer Churn Dataset
* Number of Rows: 500
* Number of Columns: 4
* Target Variable: Churn


## 3. Data Cleaning

### 3.1 Handling Missing Values

* Missing values were checked using:

  ```python
  df.isnull().sum()
  ```
* Missing values were handled by replacing them with "Unknown" or removing rows where necessary.

**Reason:**
Missing values can negatively affect model performance and lead to incorrect predictions.


## 4. Handling Categorical Data

Categorical variables were converted into numerical format using the following encoding techniques:

### 4.1 One-Hot Encoding

* Applied using:

  ```python
  pd.get_dummies(df)
  ```
* Converts categorical values into multiple binary columns.

### 4.2 Label Encoding

* Converts categories into numeric labels.

### 4.3 Ordinal Encoding

* Used where category order is meaningful.

**Reason:**
Machine learning models require numerical input, so categorical data must be transformed.


## 5. Feature Scaling

To normalize the range of features, two scaling techniques were used:

### 5.1 Min-Max Scaling

* Scales values between 0 and 1.

### 5.2 Standardization (Z-score Scaling)

* Transforms data to have mean = 0 and standard deviation = 1.

**Reason:**
Scaling ensures that all features contribute equally to the model.


## 6. Outlier Detection and Handling

Outliers were detected using:

### 6.1 Interquartile Range (IQR) Method

* Identifies extreme values outside normal range.

### 6.2 Z-Score Method

* Detects values far from mean.

Outliers were removed to improve model accuracy.


## 7. Feature Engineering

New features were created to improve model performance:

* TotalCharges = MonthlyCharges × Tenure
* AverageCharges
* Long-term customer indicator
* Charge ratio
* Tenure group

**Reason:**
Feature engineering helps capture hidden patterns in the data.


## 8. Feature Selection

* Correlation analysis was used to identify important features.
* Redundant or less important features were removed.

**Reason:**
Reducing irrelevant features improves model efficiency and accuracy.


## 9. Data Splitting

* Dataset was split into:

  * Training Set (80%)
  * Testing Set (20%)

**Reason:**
To evaluate model performance on unseen data.


## 10. Pipeline Creation

A preprocessing pipeline was created to automate:

* Scaling
* Model training

**Reason:**
Pipelines ensure reproducibility and cleaner workflow.


## 11. Conclusion

The preprocessing steps ensured that:

* Data is clean and consistent
* Features are meaningful
* Model performance is improved

This structured preprocessing pipeline helps in building an accurate and reliable churn prediction model.
