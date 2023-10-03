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

## Data Preprocessing 
### Variables: 
- Model target variable(s): IS_SUCCESSFUL (was the money used effectively)
- Non-target/feature variables: EIN and NAME (identification columns)
- Model feature variable(s): remaining 9 columns 

### Actions: 
- Dropped EIN and NAME columns as they are not beneficial
- Determined the number of unique values for each column
  - For columns with more than 10 unique values, determined the number of data points for each unique value 
  - APPLICATION_TYPE and CLASSIFICATION columns have more than 10 unique values; chose cutoffs of 500 and 1500 respectively to bin "rare" categorical values together in a new `Other` value
- Used `pd.get_dummies()` to endcode categorical values
- Split the preprocessed data into a features array, `x`, and a target array, `y` (IS_SUCCESSFUL)
  - Used `train_test_split` function to split the data into traning and testing datasets 
- Used `StandardScaler` to scale the training and testing features datasets 
  - Fit to training data
  - Used `transform` function 

## Compiling, Training, and Evaluating the Model
### Attempt #1
- APPLICATION_TYPE cutoff = 500
- CLASSIFICATION cutoff = 1500
- Layer1 = 5 hidden nodes; activation = ReLU
- Layer2 = 10 hidden nodes; activation = ReLU
- Accuracy = 0.7383

### Attempt #2
- APPLICATION_TYPE cutoff = 500
- CLASSIFICATION cutoff = 1500
- Layer1 = 10 hidden nodes; activation = ReLU
- Layer2 = 5 hidden nodes; activation = ReLU
- Accuracy = 0.7394

### Attempt #3
- APPLICATION_TYPE cutoff = 500
- CLASSIFICATION cutoff = 1500
- Layer1 = 10 hidden nodes; activation = Tanh
- Layer2 = 5 hidden nodes; activation = Tanh
- Accuracy = 0.7387

## Summary
The overall goal was to optimize the model to achieve higher than 75% accuracy in prediciting if a loan from Alphabet Soup would be successful. I made three attempts, keeping the APPLICATION_TYPE and CLASSIFICATION cutoffs constant and adjusting the hidden nodes in layers 1 & 2 and trying both ReLU and Tanh activations.

I changed the number of hidden nodes between the first and second attemtps while keeping the activation the same. This resulted in a slight increase in accuracy, so for the third attempt I kept the number of hidden nodes from the second attempt the same but changed the activation from ReLU to Tanh. This resulted in a slightly lower accuracy score, but still higher than the first attempt. 

 The highest accuracy achieved in the three attempts was 73.9%, which does not meet the requirement to be able to recommend this model without further analysis. Additional attempts could be made with changing the number of hidden nodes in the layers as this did result in improving the accuracy score. 