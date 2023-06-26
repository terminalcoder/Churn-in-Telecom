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
## Business Understanding
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
***
## Conclusions/ Recommendations
### Usage Minutes (Day)
![image](https://github.com/terminalcoder/Churn-in-Telecom/blob/main/images/day_min_churn_bar.png)
* As the number of usage minutes increases (day or evening (not shown above)), so does the churn rate. This may be explainable by high minutes usage rates/plans that are not competitive with what other providers offer.
> By offering customers who are predicted to churn, discounts on high usage plans (over 250 minutes day/ 300 minutes evening), they will be discouraged from abandoning the provider.
___

### Customer Service Calls
![image](https://github.com/terminalcoder/Churn-in-Telecom/blob/main/images/cscalls_churn_bar.png)
* From the pattern of rising churn rates associated with an increasing number of customer service calls, it may be inferred that customers will close their accounts after some number of attempts at resolving their issues.  
> As the churn rate jumps dramatically at four service calls, the provider must implement a policy in the customer service department that focuses on ensuring a satisfactory resolution at no point further than at the time of a customer's third call.
___

### International Plan
![images](https://github.com/terminalcoder/Churn-in-Telecom/blob/main/images/intl_churn_pie.png)
* Customers with a plan that includes international service, churn at a much greater rate than those without. This may be sign that the price of that service isn't competitive with what other providers offer.
> The provider should offer customers identified as likely to churn, a discount on international plans.

## Limitations/Next Steps
Several points must be taken into account when considering this report:

* The highest scoring model identified above doesn't score all that high, further exploration of possible models with other hyperparameters may yield a better result.

* Depending on costs to implement recommendations, & loss associated with each customer churning, it may be determined that a different scoring method than the one used above is better suited to the business application. (e.g. If the cost to target individual customers is low & the loss from each customer churning is high, a model with high recall would be better even if it came at the expense of low precision.) *Further investigation is necessary to determine the best metric.*

* The recommendations arrived at above make certain assumptions about the underlying reasons for the patterns found in the data. Other perspectives on those patterns may indicate a need for different business strategies. (e.g. From the elevated churn rate of customers with international service included in their plan it was inferred that this provider charges too much for this service. However, there could be an entirely different reason for this phenomenon: Customers with international service may be foreigners who are only temporarily living in the US & after some period of time, return to their home countries & close their US service accounts when doing so.) *More research should be conducted to better understand the churn rates associated with the features identified above. (e.g. Determine if other providers are charging lower rates for such service, & facing equal churn rates.)*
***
### For More Information
Please review the full analysis in the [Jupyter Notebook](https://github.com/terminalcoder/Churn-in-Telecom/blob/main/notebook.ipynb) or the presentation.  
For any additional questions, please contact Elimelech Berlin, melech.berlin@gmail.com.

***
Repository Structure

