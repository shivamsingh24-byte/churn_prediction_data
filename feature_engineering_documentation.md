# Customer Churn Prediction - Feature Engineering Documentation

## 1. Introduction

Feature engineering is the process of creating new features from existing data to improve machine learning model performance. In this project, several new features 
were created to better capture customer behavior and patterns related to churn.


## 2. Objectives of Feature Engineering

* Improve model accuracy
* Capture hidden relationships in data
* Transform raw data into meaningful inputs
* Enhance predictive power of features


## 3. List of Engineered Features

### 3.1 TotalCharges

**Formula:**

```
TotalCharges = MonthlyCharges × Tenure
```

**Description:**
Represents the total amount spent by a customer over time.

**Reason:**
Customers who spend more over time are less likely to churn.


### 3.2 AverageCharges

**Formula:**

```
AverageCharges = TotalCharges / (Tenure + 1)
```

**Description:**
Represents the average monthly spending of a customer.

**Reason:**
Helps normalize spending across customers with different tenures.


### 3.3 IsLongTerm Customer

**Formula:**

```
IsLongTerm = 1 if Tenure > threshold else 0
```

**Description:**
Binary feature indicating whether a customer is long-term.

**Reason:**
Long-term customers are usually more loyal and less likely to churn.


### 3.4 ChargeRatio

**Formula:**

```
ChargeRatio = MonthlyCharges / (Tenure + 1)
```

**Description:**
Measures how much a customer pays relative to their duration.

**Reason:**
High ratio may indicate dissatisfaction or high cost → possible churn.


### 3.5 TenureGroup

**Formula:**

```
Tenure grouped into categories (short, medium, long)
```

**Description:**
Categorizes customers based on their duration with the company.

**Reason:**
Helps model identify patterns across different customer segments.


### 3.6 ChargePerService (Optional)

**Formula:**

```
ChargePerService = MonthlyCharges / NumberOfServices
```

**Description:**
Represents cost per service used by the customer.

**Reason:**
Customers paying more per service may be more likely to churn.


## 4. Feature Transformation Techniques

* Log transformation (if needed)
* Binning (used in TenureGroup)
* Ratio creation (ChargeRatio)
* Aggregation (TotalCharges)
  

## 5. Benefits of Feature Engineering

* Improves model performance
* Reduces complexity of raw data
* Helps in better pattern recognition
* Makes data more meaningful


## 6. Challenges Faced

* Handling division by zero (solved using +1 in formulas)
* Selecting meaningful thresholds
* Avoiding redundant features


## 7. Conclusion

Feature engineering significantly improved the dataset by introducing meaningful and informative variables. These features helped the machine learning model better
understand customer behavior and improved churn prediction accuracy.
