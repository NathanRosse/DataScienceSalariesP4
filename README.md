# Data Science Salaries
Collabrative work between Sean Bell, Nathan Rosenberg, Ben Belczak, Molly Dlehant, and Cynthia Saving

## Project Intro/Objective
What Data Science Role would you want to apply for based on salary information? 

### Methods Used
* Machine Learning
* Data Visualization

### Technologies 
* Python
* Pandas, jupyter, plotly
* Tableau


## Exploring the Data
* There were 111 unique job titles held within the original data we found but this didn’t separate between a Data Scientist or Data Scientist Lead.
* Highest paying roles all seemed keyed towards guiding or managing a team of Data Scientists or Engineers.
* Top 3 countries worldwide for Data Science related jobs are the United States, United kingdom, and Canada.
* Most popular and highest paying are Data Engineer, Data Scientist, and Data Analyst before a variety of other engineers, scientists, and analysts of specific fields
* Sample size of 2442 based on experience level for full time employees in the United States: 
    - Entry level: 151
    - Senior level: 1734
    - Mid level:  440
    - Executive level: 117

## Data Cleaning 
- Filtered to only full-time employees living in United States
- Dropped irrelevant fields: 
    - ‘Expertise level' does not add any value beyond what is in 'Experience Level'.
    - Since we filtered to only US, the 'Salary Currency' and 'Salary in USD' fields don't add info.
- Changed experience level values to numerical values: 0-Entry, 1-Mid, 2-Senior, 3-Executive
- Changed company size values to numerical values: 0-Small, 1-Medium, 2-Large
- Replaced job titles with less than 50 instances with 'Other'
- Created column where 0 is salary under 100K and 1 is salary over 100K
- Created column where 0 is salary under 150K and 1 is salary over 150K
- Created dummy columns for categorical columns ('job_title', 'company_location')

## Logistic Regression
- First classification we tried was to predict if salary would be over 150K. This gave poor results with many false positives.
- The next classification tried was if entry level job has salary over 100K.  This produced better results. However, it is small sample size when filtered to only entry level jobs.

## Linear Regression
- Using training and testing data, we fit a model using multiple linear regression 
- The model yielded a low R-squared value
- The residuals vs. fitted plot shows heteroscedasticity
- Using AIC and BIC for model selection
- Using backwards stepwise variable selection, we determined the best model uses only ‘Job Title’ and ‘Experience Level’ as predictors of salary

## Resources
Our Data Set: https://www.kaggle.com/code/lusfernandotorres/data-science-salaries-2023-eda-prediction/input

Chicago Area Economic Summary: Chicago Area Economic Summary (bls.gov)

Tableau:https://prod-useast-b.online.tableau.com/t/northwesternsbba1347479a1/authoring/DataScienceSalariesP4/Top10DataScienceJobsSalaries2/Dashboard%202#1






