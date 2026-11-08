# Assignment 1 — Working Report Notes

## 1. Objective
- A customer churn is when a customer does not want to continue with their contract and does not want to stay with the company.
- in this project we want to explore a publlically availabe dataset to explore first and analyse the corelattions and customer charachteristic and then try to compare two binary classifiers that distinguish customer who churned and those who stayed. 
- it is very important to find the pattern and identifying the customers who are at risk that help us to focus on customer retention. 

## 2. Dataset Source and Selection

## 3. Initial Data Inspection

- 7043 customers, 21 columns
- 19 potential predictors, one identifier(customerID), and one target (churn).
- TotalCharges is stored as text

- With isna() I checked the missing in every column and reported zero missing values
- and also whitespace check found 11 blank TotalCharges
- All 11 customers with blank TotalCharges have tenure = 0 and churn = No
- no rows or values have been changed (Before Cleaning)

### Churn Class Balance After Cleaning
- our cleaned dataset is imbalanced 
- stayed (NO) 5163  --> 73.42%
- Churned (yes) 1869 --> 26.58 %

### Churn by Contract Type
- churn rates 
- month-to-month 42.71%
- one-year 11.28%
- two-year 2.85%
- the month-to-month has the highest rate of churn and it means that the longer the contract the lower the churn rate
- Figure: `figures/churn_by_contract.png` 

### Tenure and Monthly Charges by Churn
- customer who churned generally had shorter tenure and higher monthly charges.
- the median tenure of 10 months means at least half the churned customers had tenure of 10 months or less.

 Measure            Stayed (No) | Churned (Yes)

 Mean tenure (months) | 37.65 | 17.98 |
 Median tenure (months) | 38 | 10 |
 Mean monthly charges | 61.31 | 74.44 |
 Median monthly charges | 64.45 | 79.65 |

 - these comparisions show associations not proof that shorter tenure or higher charges cause churn.
- Figure: `figures/tenure_by_churn.png`
 - Figure: `figures/monthly_charges_by_churn.png`


## 4. Cleaning Decisions

- Converted TotalCharges from text to numeric.
- Verified that conversion produced missing values only for the 11 known blank entries.
- Removed those 11 rows because their total charges were unknown; filling with zero would require an unverified assumption.
- Removed approximately 0.16% of the original records.
- Cleaned dataset: 7,032 rows and 21 columns.
- TotalCharges now has type float64, with zero missing values.
- Limitation: this excludes the 11 customers with zero tenure.
- kept the original data in df and the unchanged CSV; cleaning was applied to df_clean.

- zero duplicate customer Ids and zero duplicate full rows.
- Inspection of distinct category values found no obvious inconsistent labels.
- no internet service and no phone service were kept as meaningful categories.

## 5. Models and Evaluation
- predicting "No" for everyone would achieve 73.42% accuracy while identifying no customers who churned.

### Task 2 — Inputs and Target
- X: 19 input features excloding customerID and Churn
- y: churn encoded as No = 0, Yes = 1
- 7032 customers before spliting

### Evaluation Split
- 80% training / 20% testing.
- 5,625 training customers; 1,407 test customers.
- Stratification preserves approximately 73.42% stayed / 26.- 58% churned in both sets.
- random_state=42 makes the split repeatable.
- Both models will use the same split.
- The full dataset was explored before splitting; test data will now be excluded from fitting and tuning.


## 6. Findings and Limitations

## 7. AI Assistance
