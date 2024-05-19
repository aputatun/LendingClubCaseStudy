# Lending Club
> Lending Club is a case study of a company which is the largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. The main aim of this case study is to identify the risky loan applicants so that the loans can be reduced thereby cutting the amount of credit loss

## Table of Contents
* [Introduction](#introduction)
* [Problem Statement](#problem-statement)
* [Dataset](#dataset)
* [Preliminary Wrangling](#preliminary-wrangling)
* [Gathering](#gathering)
* [Assessing](#assessing)
* [Cleaning](#cleaning)
* [Exploratory Data Analysis](#exploratory-data-analysis)
    * [Univariate Exploration](#univariate-exploration)
    * [Segmented Univariate Exploration](#segmented-univariate-exploration)
    * [Bivariate Exploration](#bivariate-exploration)
    * [Multivariate Analysis](#multivariate-analysis)
* [Recommendations](#recommendations)

<!-- You can include any other section that is pertinent to your problem -->

## Introduction
As an employee of a consumer finance company specializing in lending various types of loans to urban clients, part of my responsibility involves facilitating loan approval decision-making. This entails evaluating application profiles and identifying potential risks associated with loan repayment. To accomplish this task, I need to analyze the data provided in "loan.csv", which contains historical information about past loan applicants along with their default status. The goal is to identify patterns that indicate the likelihood of an applicant defaulting, enabling us to take appropriate actions such as denying a loan, adjusting loan terms, or applying higher interest rates to risky applicants.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Problem Statement
The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.


## Dataset
The dataset is provided in a CSV file named "loan.csv", and the corresponding data dictionary is available in "Data_Dictionary.xlsx".

## Preliminary Wrangling
This section contains the libraries used in the case study.
* Numpy (version 1.26)
* Pandas (version 2.2)
* Matplotlib (version 3.9)
* Seaborn (13.2)
* Regex (2024.5.15)

## Gathering
This section involves gathering the data. Read the dataset and data dictionary and store into a dataframe for further steps. The dataset is of the shape (39717, 111) and the data dictionary contains data for 115 fields.

## Assessing

This section contains analysing the columns of the dataset based on the categories below 
* Uniqueness
* Null Values
* Categorical Values

## Cleaning

This section involves cleansing the dataset. As part of this section some of the examples of cleansing are given as below.
* Dropping columns which have null values
* Dropping rows which have loan status as current since they have just applied for a loan
* Dropping additional columns that do not aid in analysis
* Dropping the columns that have same values in all rows of the dataset.
* Removing Outliers
* Removing columns that are being used post loan approval.


## Exploratory Data Analysis

This section involves the analysis of the data post cleansing. This section is further divided into three categories below.
    * Univariate Analysis (Basic,Segmented)
    * Bivariate Analysis
    * Multivariate Analysis

## Univariate Exploration

This section involves the analysis of single columns in the dataset at a time. The following observations were made as part of this section.

1. **debt_to_income_b**: It is a normally distributed graph with peak between 12 and 14 which indicates that the most of customers had a debt-to-income ratio within this range.
   
2. **loan_amount_b**: The graph indicates a right-skewed distribution with the peak indicating that most of loans are for amounts between 5,000 and 10,000.
3. 
4. **issue_b_month**: The distribution is left-skewed, which indicates that most loan applications were issued in December,and the lowest in February.
   
5. **loan_status**: There are around 32,026 customers who have their loan status as fully paid while around 5,459 customers have loan status as charged-off.
   
6. **verification_status**: Around 16,528 customers who have been issued loans arent verified.
   
7. **home_ownership**: The majority of customers (around 18,240) have a home ownership status of "RENT," followed by 16,241 with "MORTGAGE," and only 2,906 who own their home.
   
8. **emp_length**: Customers with over 10 years of employment have applied for the most loans and that is around 9,131 applications.
   
9. **sub_grade**: Loans issued under subgrade 4 are the most common, while subgrade 1 has the least.
   
10. **grade**: The highest number of loans are issued under grade B (around 11,394), while the lowest is for grade G.
   
11. **term**: The majority of loans have a term of 36 months.

## Segmented Univariate Exploration

This section involves the analyis of loan amount columns values  against other columns and the  below observations were seen as part of this analysis.
Below observations were made as part of this analysis.

1. **Interest Rate (int_rate)**: Loans which have interest rates between 10%-12% have a higher chance of loan status being fully paid off. However, loans having interest rates between 12%-14% show a higher likelihood of charge-off.
   
2. **Annual Income (annual_inc)**: Loans Status fully paid when the customer's annual income is between 45K-60K. In contrast, the customers having an annual income between 30K-45K tend to have more charged-off loans.
   
3. **Grade**: Borrowers with 10 or more years of employment have the highest count of  loans and also is the highest in fully paid and charged-off segments. This indicates that they take more loans and are also prone to default more.
   
4. **Employment Length (emp_length)**: Borrowers having 10 or more years of employment have the highest loan counts in fully paid and default segments. This indicates they take more loans and also default more.
   
5. **Verification Status**: Loans to borrowers who are not verified show higher peaks in being paid off compared to those who are verified. This indicates that unverified borrowers tend to repay their loans more frequently.
   
6. **Home Ownership**: Renters have a higher default rate, which might be explained by their higher expenses towards rent.

## Bivariate analysis

This section involves the analysis of one or more columns against the values of other columns to find whether there is a pattern of dependency.
This analysis is subdivided into two parts. Numerical columns vs numerical columns and categorical columns vs numerical columns and categorical columns vs categorical columns.

Below observations were made as part of this analysis.

    ## Numerical vs Numerical
          1. **Loan Amount vs. Interest Rate**:
            - Slight positive correlation: Higher loan amounts correlate with slightly lower interest rates.

          2. **Loan Amount vs. Installment**:
            - Positive correlation: Larger loans entail higher installment payments.

          3. **Loan Amount vs. Annual Income**:
            - Weak positive correlation: As annual income increases, loan amount tends to rise, albeit weakly.

          4. **Loan Amount vs. Public Record Bankruptcies**:
            - Negative correlation: Public record bankruptcies minimally affect the loan amount qualification.

          5. **Annual Income vs. Interest Rate**:
            - Weak negative correlation: Drawing conclusions from this scatter plot alone is challenging due to the weak correlation.

          6. **Annual Income vs. Debt-to-Income Ratio**:
            - Negative correlation: As annual income increases, the debt-to-income ratio tends to decrease.
	  7. **Margin vs. Debt-to-Income Ratio**:
            - As the margin increases, the debt-to-income ratios vary more widely.

          8. **Margin vs. Int_Rate Ratio**:
             - The margin doesn't seem to affect the interest rate..

     ## Categorical vs Numerical
	    1. **Term vs Loan Amount**:

   		Loans with a 60-month term have higher average amounts  as compared to those with a 36-month term.

	    2. **Grade vs Loan Amount**:

               Median of the loan amounts increases with higher grades (A to G), that indicates a very strong positive correlation.
               Grades C, D, and E exhibit wider variety in loan amounts when compared to other grades.

            4. **Employment Length vs. Loan Amount**:

               There is no clear correlation between employment length and the loan amount. Variety in loan amounts differs across employment
               lengths.

            5. **Loan Status vs. Loan Amount**:

               Median of the loan amounts is almost same for charged-off and fully paid loans, but charged-off loans exhibit greater variety.

            6. **Loan Status vs. Interest Rate**:

               Charged-off loans have higher median interest rates than the fully paid loans, thereby suggesting a  potential correlation
               between interest rate and loan default.

            7. **Grade vs. Interest Rate**:

               Median of the interest rate increases with lower loan grades (A to G), indicating that riskier loans carry higher rates.
               Some grades (e.g., B, C, D, and E) show wider variety in interest rates.

            8. **Verification Status vs. Loan Amount**:

              There is no much difference in median income of verified and unverified customers. Unverified applicants show wider variety in
              income.

            9. **Home Ownership vs. Loan Amount**:
    
              Median of the loan amounts is high for customers with mortgages as compared to renters and others, suggesting a correlation
              between homeownership and the loan amount.
            10. **Margin vs. Loan Status**:

              People who fully repaid their loans had a bigger gap between their income and loan amount than those who didn't repay.
    ## Categorical vs Categorical
        1. **Comparison between Loan Status and Term**:

            Risk Levels (Charged Off Rates):
    
            -  Less Risky: 36 months (11.11%)
            -  More Risky: 60 months (25.05%)

            Distribution of Loan Terms:
    
            -  More Common: 36-month loans
            -  Less Common: 60-month loans

        2. **Comparison between Loan Status and Loan Amount**:

           Risk Levels (Charged Off Rates):

           -  Less Risky: 5000-10000 (12.83%), 0-5000 (13.87%), 10000-15000 (13.73%)
           -  More Risky: 15000-20000 (17.27%), 20000-25000 (19.11%), 25000-30000 (20.46%)

           Distribution of Loan Amounts:

           -  More Common: Loans in the 5000-10000 and 0-5000 ranges
           -  Less Common: Loans in the 25000-30000 and 20000-25000 ranges, indicating fewer larger loans.

        3. **Comparison between Loan Status and Interest Rate**:

           Risk Levels (Charged Off Rates):

           -  Less Risky: 4-6% (4.09%), 6-8% (5.6%), 8-10% (9.61%)
           -  More Risky: 16-18% (26.14%), 18-20% (30.34%), 20-22% (36.92%), 22-24% (46.08%)

           Distribution of Interest Rates:

           -  More Common: Loans with 10-12% and 6-8% interest rates
           -  Less Common: Loans with 22-24% and 20-22% interest rates, indicating fewer high-risk, high-interest loans.

        4. **Comparison between Loan Status and Grade**:

          Risk Levels (Charged Off Rates):

          -  Less Risky: Grade A (6.01%), B (12.15%), and C (17.13%)
          -  More Risky: Grade D (21.87%), E (26.89%), F (31.8%), and G (34.26%)

          Distribution of Loan Grades:

          -  More Common: Grades B and A
          -  Less Common: Grades F and G, indicating fewer high-risk loans.

        5. **Comparison between Loan Status and Home Ownership**:

          Risk Levels (Charged Off Rates):

          -  More Risky: OTHER (18.37%), RENT (15.18%), OWN (14.67%)
          -  Less Risky: MORTGAGE (13.31%), NONE (0.0%)

          Distribution of Home Ownership:

          -  High Common: RENT and MORTGAGE are most common.

        6. **Comparison between Loan Status and Purpose**:

          Risk:

          -  High Risk: Small business, renewable energy, educational loans.
          -  Low Risk: Wedding, car, credit card, major purchase loans.

          Demand:

          -  High Demand: Debt consolidation, credit card loans.
          -  Low Demand: Renewable energy, educational loans.

## Multivariate Analysis

This section covers the analysis of one or two columns against the values of one or two columns to find whether they are correlated to each oher.Below is the analysis for the same


1. **Loan Amounts**:
   - Strong positive correlations with funded amount and funded amount invested, moderate correlation with installment, and weak correlation with borrower characteristics and interest rates.

2. **Funded Amount**:
   - Strong positive correlations with loan amount and funded amount invested, moderate correlation with installment, and weak correlation with borrower characteristics and interest rates.

3. **Funded Amount Invested**:
   - Strong positive correlations with loan amount and funded amount, moderate correlation with installment, and weak correlation with borrower characteristics and interest rates.

4. **Interest Rate**:
   - Weak correlations with loan attributes, indicating some association but not particularly strong.

5. **Installment**:
   - Strong positive correlations with loan amount, funded amount, and funded amount invested, weak correlation with borrower characteristics and interest rates.

6. **Annual Income**:
   - Weak correlations with loan attributes, indicating a slight association with loan amounts but not particularly strong.

7. **Debt-to-Income Ratio**:
   - Weak correlations with loan attributes, suggesting some association but not particularly strong.

8. **Public Record Bankruptcies**:
   - Almost negligible correlation with loan attributes, indicating minimal association with borrower characteristics and loan terms.

9. **Issue Date Year**:
   - Negligible correlation with loan attributes except for a somewhat stronger correlation with funded amount invested.

## Recommendations

This section covers the factors that influence loan defaults

- **Loan Term**: Loans with longer terms (60 months) have higher default rates compared to shorter-term loans (36 months), indicating higher risk or borrower instability.

- **Loan Amount**: For loan amounts exceeding $15,000, there is a trend of higher default rates. Borrowers may find it difficult to make repayments for larger loans, leading to increased charge-offs.

- **Interest Rate**: Loans with higher interest rates, such as 16%, are associated with higher charge-off rates. High-interest loans may attract riskier customers.

- **Loan Grade**: Lower-grade loans (D, E, F, G) have higher charge-off rates compared to higher-grade loans (A, B, C).

- **Home Ownership**: Non-traditional home ownership, such as renting or other categories, is linked with higher charge-off rates compared to mortgage holders.

- **Loan Purpose**: Loans for small businesses, renewable energy, and education exhibit higher charge-off rates, while loans for weddings, cars, credit cards, and major purchases have lower charge-off rates.

These factors provide insights into customer behavior that can help lenders understand and mitigate loan charge-off risks.
