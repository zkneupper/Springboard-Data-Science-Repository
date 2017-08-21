

# README - Capstone Project1 - Data Wrangling

In this folder, I wrangle/clean data for my first capstone project.

<p></p>

## Files: 

### 'default of credit card clients.csv'

'default of credit card clients.csv' contains the original data to be wrangled.

### 'Data_Wrangling.ipynb'

In this Jupyter Notebook, I check for missing values, mis-categorized values, and outliers.  Where necessary I make corrections to the data.  I export the corrected data to a new csv file called 'default of credit card clients - wrangled.csv'.

### 'data_cleaning-default_of_credit_card_clients.py'

This Python script will read the original data from 'default of credit card clients.csv', make the necessary corrections (as identified in the aforementioned Jupyter Notebook) to the data, and export the corrected data to 'default of credit card clients - wrangled.csv'.


### 'default of credit card clients - wrangled.csv'

'default of credit card clients - wrangled.csv' contains the wrangled/cleaned data.


<p></p>

# Data Wrangling Steps:

### 1. Check for null values

I verified that the data did not contain any null values.

### 2. Identify discrete (categorical) and continuous variables.

I categorized all variables as either discrete (categorical) or continuous variables.

### 3. Wrangle the discrete (categorical) variables

I checked that categorical variables only took on values that they were supposed to take (per the descriptions on https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients and https://www.kaggle.com/uciml/default-of-credit-card-clients-dataset/discussion/34608).  

Some of the data was mis-categorized.  For instance, education should have only taken on 4 values:

1. 1 = graduate school; 
2. 2 = university; 
3. 3 = high school; and 
4 = others).

However, in the original data, 'EDUCATION' took on values of 0, 1, 2, 3, 4, 5, and 6.
I re-categorized observations with values of 0, 5, and 6 as 4 ("others").

I checked each of the discrete (categorical) variables and re-categorized observations where necessary.




<p></p>

The dependent variable ('default payment next month') is a categorical variable that takes only two values (Yes = 1, No = 0).  The dependent variable ('default payment next month') is imbalanced.

+ 77.9% of the observations do not default in the next month ('default payment next month' = 0).

+ 22.1% of the observations do default in the next month ('default payment next month' = 1).

The data set may need to be rebalanced / resampled. 



<p></p>

### 3. Wrangle the continuous variables

I checked continuous variables for outliers (high kurtosis).  Other than the Age variable, all of the other continuous variables had high kurtosis and were highly skewed.  The outliers may need to be trimmed for linear models.



