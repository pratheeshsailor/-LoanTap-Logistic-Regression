# LoanTap-Logistic-Regression

**Context:**

LoanTap is an online platform committed to delivering customized loan products to millennials. They innovate in an otherwise dull loan segment, to deliver instant, flexible loans on consumer friendly terms to salaried professionals and businessmen.

The data science team at LoanTap is building an underwriting layer to determine the creditworthiness of MSMEs as well as individuals.

LoanTap deploys formal credit to salaried individuals and businesses 4 main financial instruments:

Personal Loan
EMI Free Loan
Personal Overdraft
Advance Salary Loan
This case study will focus on the underwriting process behind Personal Loan only

**Problem Statement:**

Given a set of attributes for an Individual, determine if a credit line should be extended to them. If so, what should the repayment terms be in business recommendations?


**Data dictionary:**

loan_amnt : The listed amount of the loan applied for by the borrower. If at some point in time, the credit department 
            reduces the loan amount, then it will be reflected in this value.
term : The number of payments on the loan. Values are in months and can be either 36 or 60.
int_rate : Interest Rate on the loan
installment : The monthly payment owed by the borrower if the loan originates.
grade : LoanTap assigned loan grade
sub_grade : LoanTap assigned loan subgrade
emp_title :The job title supplied by the Borrower when applying for the loan.*
emp_length : Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means 
              ten or more years.
home_ownership : The home ownership status provided by the borrower during registration or obtained from the credit report.
annual_inc : The self-reported annual income provided by the borrower during registration.
verification_status : Indicates if income was verified by LoanTap, not verified, or if the income source was verified
issue_d : The month which the loan was funded
loan_status : Current status of the loan - Target Variable
purpose : A category provided by the borrower for the loan request.
title : The loan title provided by the borrower
dti : A ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage 
      and the requested LoanTap loan, divided by the borrower’s self-reported monthly income.
earliest_cr_line :The month the borrower's earliest reported credit line was opened
open_acc : The number of open credit lines in the borrower's credit file.
pub_rec : Number of derogatory public records
revol_bal : Total credit revolving balance
revol_util : Revolving line utilization rate, or the amount of credit the borrower is using relative to all available revolving credit.
total_acc : The total number of credit lines currently in the borrower's credit file
initial_list_status : The initial listing status of the loan. Possible values are – W, F
application_type : Indicates whether the loan is an individual application or a joint application with two co-borrowers
mort_acc : Number of mortgage accounts.
pub_rec_bankruptcies : Number of public record bankruptcies
Address: Address of the individual
**Concept Used:**

      Exploratory Data Analysis
      Feature Engineering
      Logistic Regression
      Precision Vs Recall Tradeoff

**What does ‘good’ look like?**

1)Import the dataset and do usual exploratory data analysis steps like checking the structure & characteristics of the dataset
2)Check how much target variable (Loan_Status) depends on different predictor variables (Use count plots, box plots, heat maps etc)
3)Check correlation among independent variables and how they interact with each other
4)Simple Feature Engineering steps:
E.g.: Creation of Flags- If value greater than 1.0 then 1 else 0. This can be done on:

1. Pub_rec
2. Mort_acc
3. Pub_rec_bankruptcies

5)Missing values and Outlier Treatment
6)Scaling - Using MinMaxScaler or StandardScaler
7)Use Logistic Regression Model from Sklearn/Statsmodel library and explain the results
8)Results Evaluation:
      * Classification Report
      * ROC AUC curve
      * Precision recall curve
9)Tradeoff Questions:
      * How can we make sure that our model can detect real defaulters and there are less false positives? This is important         as we can lose out on an opportunity to finance more individuals and earn interest on it.
      * Since NPA (non-performing asset) is a real problem in this industry, it’s important we play safe and shouldn’t               disburse loans to anyone
10)Provide actionable Insights & Recommendations
