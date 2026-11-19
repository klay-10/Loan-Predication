# Loan Prediction Analysis: Exploratory Data Analysis, Feature Engineering & Model Evaluation
###tutorial project


1. Project Overview

Loan approval is an important decision-making process for financial institutions. Banks and lending organizations need to assess applicants' financial information and credit history to determine whether they qualify for loans.

This project explores a loan prediction dataset to understand the factors associated with loan approval and rejection. It applies data analysis and machine learning techniques to investigate the dataset, prepare features, identify potentially useful predictors, and evaluate a baseline classification model.

Beyond predicting loan approval, the project pays particular attention to the model's ability to identify rejected loan applications, as the initial evaluation revealed a significant difference in performance between the two target classes.

2. Project Objectives

The main objectives are to:

Understand the structure and characteristics of the loan prediction dataset.

Perform exploratory data analysis (EDA) to identify patterns, distributions, and potential outliers.

Investigate missing values and apply appropriate preprocessing techniques.

Transform categorical variables into numerical representations suitable for machine learning.

Examine relationships between features and the target variable.

Apply feature selection techniques, including Mutual Information.

Establish a baseline classification model.

Evaluate model performance and investigate misclassified loan applications.

Explore approaches to improve classification performance across both target classes.

3. Dataset Description

The project uses a loan prediction dataset containing 614 observations and applicant-related information.

The dataset includes the following variables:

Feature

Description

Gender

Applicant's gender

Married

Marital status

Dependents

Number of dependents

Education

Applicant's education level

Self_Employed

Whether the applicant is self-employed

ApplicantIncome

Applicant's income

CoapplicantIncome

Co-applicant's income

LoanAmount

Requested loan amount

Loan_Amount_Term

Loan repayment period

Credit_History

Applicant's credit history indicator

Property_Area

Location category of the property

Loan_Status

Target variable indicating loan approval or rejection

Loan_ID is an identifier and is excluded from the predictive features.

Target Variable

The target variable is Loan_Status:

1 – Loan Approved (Y)

0 – Loan Rejected (N)

4. Exploratory Data Analysis (EDA)

EDA was conducted to understand the distribution of numerical and categorical variables and identify potential data quality issues.

4.1 Descriptive Statistics

The describe() method was used to examine the mean, standard deviation, minimum, maximum, median-related quartiles, and other descriptive statistics.

Some observations included:

ApplicantIncome and CoapplicantIncome exhibited right-skewed distributions.

Both income variables contained unusually high values that warranted further investigation.

LoanAmount also showed right-skewness, suggesting that the median could be more appropriate than the mean for imputation.

Loan_Amount_Term was concentrated around 360 months.

Credit_History was a binary variable, with approximately 84.2% of its non-missing observations having a value of 1.

4.2 Distribution and Outlier Analysis

Histograms and boxplots were used to investigate numerical feature distributions.

The analysis helped identify:

Skewness in income and loan amount variables.

Potential outliers in applicant and co-applicant incomes.

Concentration of loan repayment periods around 360 months.

Differences in numerical feature distributions across loan approval categories.

Boxplots were also used to examine the relationship between numerical features and Loan_Status.

4.3 Missing Value Analysis

Missing values were identified using isna().sum().

Feature

Missing Values

Gender

13

Married

3

Dependents

15

Self_Employed

32

LoanAmount

22

Loan_Amount_Term

14

Credit_History

50

Credit_History had the highest number of missing observations among the listed features.

Missing values were investigated according to feature type:

Numerical features: median or mean imputation, depending on the distribution.

Categorical features: mode imputation.

For leakage-safe modelling, imputation values should be calculated using the training set and then applied consistently to validation and test sets.
