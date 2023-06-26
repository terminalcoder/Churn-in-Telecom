![image](https://github.com/terminalcoder/Churn-in-Telecom/blob/main/images/pexels-troy-squillaci-2525871_4.jpg)
# Churn in Telecom
Elimelech Berlin  
June 2023
***
## Overview
This report examines data about phone usage to gain understanding of factors that can be used to predict churn, or customers closing acounts or canceling service subscrition, from a telecommunications company. This report aims to build a model that can accurately predict which customers will soon abandon a service provider, equiping the business with a key tool in strategizing to retain them/reduce further customer loss. From the resulting model, several insights into customer churn emerge, notably, in identifying the most important factors that influence a customer's decision to churn:
* number of usage minutes
* number of customer service calls
* international plan
***
## Business Problem
One of the greatest business challenges to providers of telecommunication services is customer churn. Although customers may abandon a service provider for a number of reasons, a carefully crafted and targeted effort to retain customers who may leave, may prove effective in retaining their patronage. As such, identifying those customers & gaining insight into the factors that may influence their decision to keep their accounts, is essential in reducing a company's customer churn rate. 
***
## Data
The dataset used for this project is the [Churn in Telecom's Dataset](https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset) available from Kaggle.  
This dataset includes details of 3k+ US telecom accounts, including:
* phone numbers
* location
* plan details
* usage minutes
* churn status
***
## Modeling
Prior to the actual modeling, the list of predictor features was reduced to include only those features that had the highest correlation with the target feature, `'churn'`. (The features were scaled to ensure that they could be modeled effectively with logistic regression.)  
Several different modeling techniques are used to identify a classification model which best predicts which customers will churn:
- Logistic Regression
- Random Forest
- XGBoost
For each method used, a number of model parameters are tried, in an iterative fashion, to pinpoint the best model.
Each model's performance is assesed by its f1-score on test predictions, in order to balance the need to maximize the percentage of customers 'caught' (based on recall), with concern not to waste resources on customers who aren't at risk of churning but mistakenly identified as such (precision).
A random forest classifier, with an f1-score of .71, is ultimately identified as the best performing model for the data.
***
## Features
The features used to predict customer churn, & their respective importance:
![image](https://github.com/terminalcoder/Churn-in-Telecom/blob/main/images/rf_model_feat_imp_hbar.png)
