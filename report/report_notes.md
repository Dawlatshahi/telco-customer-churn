# Assignment 1 — Working Report Notes

## 1. Objective

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

## 6. Findings and Limitations

## 7. AI Assistance
