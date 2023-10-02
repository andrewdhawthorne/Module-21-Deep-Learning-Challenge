# Alphabet Soup Applicant Success Analysis 

## Overview 

Deep neural network (DNN) is applied to data from nonprofit foundation Alphabet Soup to help it select the applicants for funding with the best chance of success in their business ventures. 

The csv dataset consists of 34,000+ organizations that have received funding from Alphabet Soup in the past. It includes the following factors: 
- EIN and NAME (identification columns)
- APPLICATION_TYPE (Alphabet Soup application type)
- AFFILIATION (affiliated sector of industry)
- CLASSIFICATION (government organization classification)
- USE_CASE (use case for funding)
- ORGANIZATION (organization type)
- STATUS (active status)
- INCOME_AMT (income classification)
- SPECIAL_CONSIDERATIONS (special considerations for application)
- ASK_AMT (funding amount requested)
- IS_SUCCESSFUL (was the money used effectively)

### Data Preprocessing 
- Model target variable(s): IS_SUCCESSFUL (was the money used effectively)
- Non-target/feature variables: EIN and NAME (identification columns)
- Model feature variable(s): remaining 9 columns 
- EIN and NAME columns were dropped as they are not beneficial
- Determined the number of unique values for each column, and determined the number of data points for each unique value of columns with more than 10 unique values 
- APPLICATION_TYPE and CLASSIFICATION columns have more than 10 unique values; chose cutoffs of 500 and 1500 respectively 




In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
