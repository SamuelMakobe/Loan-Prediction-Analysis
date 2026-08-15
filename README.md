# Loan Prediction Analysis

## Project Overview

This project focuses on analysing loan application data and preparing it for machine-learning-based loan approval prediction. The aim is to understand the factors associated with loan approval and transform the original dataset into a clean, structured, and machine-learning ready dataset.

The project follows a complete data preparation workflow, including data quality checks, missing-value treatment, categorical encoding, outlier detection, feature scaling, correlation analysis, and feature selection.

## Business Problem

Financial institutions need to assess loan applications accurately to manage financial risk while identifying applicants who are suitable for lending. Traditional assessment can involve evaluating several applicant and loan characteristics, making a data-driven approach useful for identifying patterns in historical applications.

This project investigates whether applicant and loan information can be used to support the prediction of loan approval outcomes.

## Project Objectives

The main objectives are to:

* Understand the structure and quality of the loan application dataset.
* Identify and address data-quality issues.
* Transform categorical variables into suitable numerical features.
* Detect and assess potential outliers.
* Apply appropriate feature scaling.
* Identify important and potentially correlated features.
* Produce a final dataset suitable for machine-learning modelling.

## Dataset

The project uses the Loan Prediction dataset containing **614 loan applications**.

The target variable is:

* `Loan_Status` — loan approval outcome.

The dataset contains applicant, financial, and loan-related information, including:

* Gender
* Married
* Dependents
* Education
* Self_Employed
* ApplicantIncome
* CoapplicantIncome
* LoanAmount
* Loan_Amount_Term
* Credit_History
* Property_Area

## Tools and Technologies

The project was developed using:

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

## Data Preprocessing

The following preprocessing steps were performed:

1. **Missing-value treatment**
   Missing values were identified and treated to ensure that the final modelling dataset contained complete feature information.

2. **Duplicate check**
   Duplicate records were investigated to maintain data quality.

3. **Data type inspection**
   Variable data types were checked to ensure that the data was appropriately structured.

4. **Removal of ****`Loan_ID`**
   `Loan_ID` was removed because it is an identifier and does not provide meaningful predictive information.

5. **Categorical encoding**
   Categorical variables were converted into numerical features using one-hot encoding.

6. **Target encoding**
   `Loan_Status` was converted into a binary target, where `1` represents an approved loan and `0` represents a rejected loan.

7. **Outlier detection**
   Potential outliers were investigated using boxplots and the IQR method. Potentially valid observations were retained rather than automatically removed.

8. **Train-test split**
   The dataset was divided into training and testing sets for future machine-learning modelling.

9. **Feature scaling**
   StandardScaler was applied to the relevant numerical features to place them on a comparable scale.

## Feature Selection

Feature selection was supported by correlation analysis and Random Forest feature importance.

The correlation analysis showed that `ApplicantIncome` and `LoanAmount` had the strongest observed numerical relationship, with a correlation of approximately **0.57**.

Random Forest feature importance identified the following as the most influential features:

1. `Credit_History`
2. `ApplicantIncome`
3. `LoanAmount`
4. `CoapplicantIncome`
5. `Loan_Amount_Term`

These findings indicate that credit history and financial characteristics contain useful information for predicting loan approval.

## Key Observations

The analysis produced several important observations:

* The dataset contains both approved and rejected loan applications.
* `Credit_History` was the most important feature in the Random Forest analysis.
* `ApplicantIncome` and `LoanAmount` were also among the strongest predictors.
* Potential outliers were present in several numerical variables.
* Potentially legitimate extreme observations were retained rather than removed without sufficient evidence.
* The final feature dataset contains no missing values.

## Final Machine-Learning Dataset

The final machine-learning-ready dataset contains:

* **614 observations**
* **14 predictor features**
* **1 target variable**
* **0 missing values**

The final dataset contains the encoded predictor variables and the binary `Loan_Status` target.

## Repository Structure

```text
Loan-Prediction-Analysis/
│
├── README.md
├── Loan_Prediction_Analysis.ipynb
├── cleaned_loan_prediction.csv
├── machine_learning_ready_loan_prediction.csv
├── Business_Understanding_Report.docx
└── Data_Preprocessing_Report.docx
```

## Project Reports

The repository includes:

* **Business Understanding Report** — explains the business problem, objectives, key questions, and business value.
* **Data Preprocessing Report** — explains the preprocessing decisions, feature engineering, outlier detection, feature scaling, feature selection, key observations, and final dataset.

## Conclusion

The project successfully transformed the original loan application data into a structured machine-learning ready dataset. The preprocessing and feature-selection stages provided useful insights into the characteristics associated with loan approval, particularly the importance of credit history and financial variables.The resulting dataset provides a suitable foundation for the next stage of the project: developing and evaluating machine-learning models for loan approval prediction.
