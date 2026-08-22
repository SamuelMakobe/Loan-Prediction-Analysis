# Loan Prediction Analysis

## Project overview

This repository contains an end-to-end data science project focused on analysing loan application data and preparing the dataset for predictive modelling.

The project was developed progressively across the data science internship assignments, beginning with data exploration and preprocessing in Week 2, followed by advanced exploratory and statistical analysis and dataset refinement in Week 3. The refined dataset will form the foundation for machine-learning modelling in Week 4.

The project aims to identify patterns and relationships associated with loan approval and prepare a reliable, machine-learning-ready dataset that can be used to support data-driven loan assessment.

---

## Business problem

Financial institutions need to assess loan applications efficiently and consistently while identifying characteristics associated with loan approval.

This project investigates historical loan application data to understand the factors associated with loan outcomes and to prepare the data for predictive modelling.

The analysis can provide insights into applicant characteristics, financial information, and application attributes that may be useful when developing a loan approval prediction model.

---

## Project objectives

The main objectives of this project are to:

* Understand the loan application dataset and its business context.
* Assess data quality and identify missing values.
* Perform exploratory data analysis.
* Conduct advanced exploratory and multivariate analysis.
* Investigate relationships between variables using statistical tests.
* Engineer meaningful features.
* Evaluate and refine the feature set.
* Remove redundant or non-informative variables.
* Encode categorical variables.
* Scale numerical variables where applicable.
* Produce a final machine-learning-ready dataset.
* Generate business insights and recommendations.
* Prepare the refined dataset for predictive modelling in Week 4.

---

# Project progress

## Week 2 — Data exploration and preprocessing

Week 2 focused on understanding and preparing the original loan prediction dataset.

The main activities included:

* Dataset inspection
* Data structure and variable identification
* Missing-value assessment
* Exploratory data analysis
* Data cleaning
* Data preprocessing
* Preparation of a cleaned dataset
* Preparation of an initial machine-learning-ready dataset

### Week 2 deliverables

* `Week_2_loan_prediction_preprocessing.ipynb`
* `cleaned_loan_prediction.csv`
* `machine_learning_ready_loan_prediction.csv`
* `Business understanding report-Loan prediction.pdf`
* `Data preprocessing report-Loan prediction.pdf`

---

# Week 3 — Advanced analysis and dataset refinement

Week 3 extended the Week 2 analysis rather than repeating the complete preprocessing process.

The analysis focused on:

* Advanced Exploratory Data Analysis
* Numerical variable analysis
* Categorical variable analysis
* Correlation analysis
* Multivariate analysis
* Group comparisons
* Statistical analysis
* Feature evaluation
* Feature engineering
* Dataset refinement
* Categorical encoding
* Feature scaling
* Final modelling dataset preparation
* Business insights and recommendations

---

## Dataset

The loan prediction dataset contains 614 observations.

The target variable is:

Loan_Status

where:

* 1 = Approved
* 0 = Rejected

The target distribution is:

| Loan status | Count | Percentage |
| ----------- | ----: | ---------: |
| Approved    |   422 |     68.73% |
| Rejected    |   192 |     31.27% |

---

# Exploratory data analysis

The exploratory analysis investigated numerical and categorical variables using descriptive statistics and visualisations.

### Numerical analysis

Numerical variables were investigated using:

* Descriptive statistics
* Histograms
* Distribution plots
* Boxplots
* Correlation analysis

Several financial variables showed right-skewed distributions, including ApplicantIncome, CoapplicantIncome and LoanAmount.

### Categorical analysis

Categorical variables were examined using:

* Frequency distributions
* Bar charts
* Cross-tabulations
* Group comparisons

These analyses helped identify patterns that required further investigation during the advanced analysis stage.

---

# Correlation analysis

Correlation analysis was conducted to investigate relationships between numerical variables.

Important relationships included:

| Variables                       | Correlation |
| ------------------------------- | ----------: |
| ApplicantIncome – TotalIncome   |      0.8930 |
| LoanAmount – TotalIncome        |      0.6246 |
| ApplicantIncome – LoanAmount    |      0.5709 |
| TotalIncome – DebtToIncomeRatio |     -0.3882 |

The strongest relationship was between ApplicantIncome and TotalIncome. This strong correlation is expected because TotalIncome incorporates applicant and coapplicant income.

LoanAmount also showed positive relationships with both ApplicantIncome and TotalIncome.

---

# Statistical analysis

Several statistical analyses were conducted to investigate relationships and differences within the dataset.

## Chi-Square analysis

Statistically significant relationships were identified between Loan_Status and:

* Married — p = 0.034394
* Education — p = 0.043100
* Property_Area — p = 0.002136

CreditRiskCategory also showed a strong statistical association with Loan_Status:

* χ² = 180.0665
* p < 0.001

However, CreditRiskCategory was subsequently removed because it was derived from Credit_History and therefore represented redundant information.

## Mann-Whitney U test

The Mann-Whitney U test produced:

* U statistic: 38,267.0
* p-value: 0.576442

Since the p-value was greater than 0.05, there was insufficient evidence of a statistically significant difference between the two groups examined.

---

# Feature engineering

Several additional features were created and evaluated during the analysis.

### TotalIncome

Combines applicant and coapplicant income to provide a broader measure of total income.

### IncomeBand

Groups income into categories:

* Low
* Lower-Middle
* Upper-Middle
* High

### DebtToIncomeRatio

Provides a measure of the relationship between the requested loan amount and income.

### FamilySizeGroup

Groups applicants according to family size:

* Small Family
* Medium Family
* Large Family
* Unknown

### CreditRiskCategory

CreditRiskCategory was evaluated during the analysis but was removed from the final dataset because it duplicated information contained in Credit_History.

---

# Dataset refinement

The advanced analysis and feature evaluation were used to refine the Week 2 dataset.

### Removed features

Loan_ID

Removed because it is an identifier and does not provide meaningful predictive information.

**CreditRiskCategory**

Removed because it was derived from Credit_History and therefore contained redundant information.

### Missing values

Missing values were identified in several variables, including:

* Gender
* Married
* Dependents
* Self_Employed
* LoanAmount
* Loan_Amount_Term
* Credit_History
* DebtToIncomeRatio

After the refinement and preprocessing process, the final validation confirmed:

Total missing values: 0

---

# Machine-Learning preparation

Categorical variables were converted into numerical representations using one-hot encoding.

Examples include:

* Gender_Male
* Married_Yes
* Dependents_1
* Dependents_2
* Dependents_3+
* Education_Not Graduate
* Self_Employed_Yes
* Property_Area_Semiurban
* Property_Area_Urban

The engineered categorical features were also encoded.

Numerical variables were standardised using feature scaling.

The target variable was encoded as:

* 1 = Approved
* 0 = Rejected

---

# Final modelling dataset

The refined dataset contains:

* 614 observations
* 23 variables
* 22 predictor variables
* 1 target variable
* 0 missing values

The final modelling dataset includes financial, categorical and engineered features such as:

* ApplicantIncome
* CoapplicantIncome
* LoanAmount
* Loan_Amount_Term
* Credit_History
* TotalIncome
* DebtToIncomeRatio
* Gender_Male
* Married_Yes
* Dependents categories
* Education_Not Graduate
* Self_Employed_Yes
* Property_Area categories
* IncomeBand categories
* FamilySizeGroup categories

The final dataset is stored as:

final_modelling_dataset.csv

---

# Key findings

The main findings from the analysis include:

1. Loan approvals represented 68.73% of the dataset.
2. Married status showed a statistically significant relationship with Loan_Status.
3. Education showed a statistically significant relationship with Loan_Status.
4. Property_Area showed a statistically significant relationship with Loan_Status.
5. ApplicantIncome and TotalIncome had a strong positive correlation of 0.8930.
6. LoanAmount was positively associated with ApplicantIncome and TotalIncome.
7. CreditRiskCategory showed a strong statistical relationship with Loan_Status but was removed because it duplicated Credit_History.
8. The final modelling dataset contains 614 observations and 23 variables.
9. The final dataset contains zero missing values.

---

# Business recommendations

Based on the analysis, the following recommendations were identified:

* Prioritise Credit_History during predictive modelling.
* Evaluate Property_Area, Education and Married status as candidate predictors.
* Retain meaningful financial variables such as ApplicantIncome, TotalIncome, LoanAmount and DebtToIncomeRatio.
* Exclude Loan_ID from predictive modelling.
* Avoid using CreditRiskCategory together with Credit_History.
* Evaluate model performance using multiple metrics rather than accuracy alone.
* Monitor the effect of missing information, particularly Credit_History.
* Maintain a reproducible preprocessing workflow for future modelling.

---

# Dataset limitations

The analysis has several limitations:

* The dataset contains only 614 observations.
* Several variables originally contained missing values.
* Approved applications outnumber rejected applications.
* The dataset may not represent all loan applicants or lending environments.
* Some potentially important lending variables are not included.
* Statistical associations do not establish causation.
* The findings should therefore be validated using additional data before being applied to real-world lending decisions.

---

# Week 4 — Machine Learning

The refined dataset will be used as the foundation for predictive modelling in Week 4.

The planned machine-learning workflow includes:

1. Separating predictors and target variable.
2. Creating training and testing datasets.
3. Training classification algorithms.
4. Comparing model performance.
5. Evaluating accuracy, precision, recall and F1-score.
6. Examining confusion matrices.
7. Evaluating ROC-AUC where appropriate.
8. Investigating feature importance.
9. Selecting an appropriate predictive model.
10. Interpreting the model from a business perspective.

The goal is to determine whether machine-learning algorithms can reliably predict loan approval outcomes using the refined dataset.

---

# Repository structure

```text
Loan-Prediction-Analysis/
│
├── README.md
│
├── notebooks/
│   ├── Week_2_loan_prediction_preprocessing.ipynb
│   └── Week_3_loan_prediction_analysis.ipynb
│
├── datasets/
│   ├── cleaned_loan_prediction.csv
│   ├── machine_learning_ready_loan_prediction.csv
│   └── final_modelling_dataset.csv
│
├── reports/
│   ├── week_2/
│   │   ├── Business_understanding_report-Loan_prediction.pdf
│   │   └── Data_preprocessing_report-Loan_prediction.pdf
│   │
│   └── week_3/
│       ├── Project_Continuity_Summary.pdf
│       ├── Statistical_Analysis_Summary.pdf
│       ├── Feature_Engineering_Documentation.pdf
│       ├── Feature_Evaluation_and_Selection_Summary.pdf
│       ├── Business_Insights_and_Recommendations_Report.docx
│       └── Updated_Data_Dictionary.pdf
│
└── submission/
    └── Week_3_Submission_Form.pdf
```

---

# Tools and technologies

The project uses:

* Python
* Jupyter Notebook
* pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* scikit-learn
* Anaconda
* GitHub

---

# Author

Samuel Makobe

Data Science Intern

Project: Loan Prediction Analysis

Focus Areas: Data Analysis, Exploratory Data Analysis, Statistical Analysis, Feature Engineering, Machine Learning Preparation and Predictive Modelling.
