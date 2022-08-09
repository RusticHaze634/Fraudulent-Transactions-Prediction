# Fraudulent-Transactions-Prediction
Prediction of Fraudulent Transactions for a  Financial Company


## Context:

_This case requires to develop a model for predicting fraudulent transactions for a financial company and use insights from the model to develop an actionable plan. Following usual model development procedures, the model would be estimated on the calibration data and tested on the validation data. This case requires both statistical analysis and creativity._

## Dataset

Data for the case is available in CSV format having 6362620 rows and 10 columns.  
**Data Link :** https://www.kaggle.com/datasets/chitwanmanchanda/fraudulent-transactions-data

## Data Dictionary:

- step - maps a unit of time in the real world. In this case 1 step is 1 hour of time. Total steps 744 (30 days simulation).
- type - CASH-IN, CASH-OUT, DEBIT, PAYMENT and TRANSFER.
- amount - amount of the transaction in local currency.
- nameOrig - customer who started the transaction
- oldbalanceOrg - initial balance before the transaction
- newbalanceOrig - new balance after the transaction
- nameDest - customer who is the recipient of the transaction
- oldbalanceDest - initial balance recipient before the transaction. Note that there is not information for customers that start with M (Merchants).
- newbalanceDest - new balance recipient after the transaction. Note that there is not information for customers that start with M (Merchants).
- isFraud - This is the transactions made by the fraudulent agents inside the simulation. In this specific dataset the fraudulent behavior of the agents aims to profit by taking control or customers accounts and try to empty the funds by transferring to another account and then cashing out of the system.
- isFlaggedFraud - The business model aims to control massive transfers from one account to another and flags illegal attempts. An illegal attempt in this dataset is an attempt to transfer more than 200.000 in a single transaction.

## Task:

- Data cleaning including missing values, outliers and multi-collinearity.  
- Describe fraud detection model.  
- Variables selection method.  
- Demonstrate the performance of the model by using best set of tools.  
- Key factors that predict fraudulent customer.  
- Preventive methods should be adopted while company update its infrastructure.  
- Determine if they work (_assuming these actions have been implemented_).  


# Solution


## Libraries Used:

numpy, pandas, matplotlib, seaborn,  
warnings, scikit-learn, scipy

## EDA & Data Pre-Processing:

- Load and read the data
- Check info, shape of data
- Check null values
- Value count of the Target column (**Highly Imbalanced Column**)
- **Detecting Multicollinearity with VIF**
- ![image](https://user-images.githubusercontent.com/38161827/183543698-b07314ba-96d5-4a6e-9d2f-cce89e9716f0.png)
- **LABEL ENCODING of Categorical Data**
- **Normalizing** _'amount'_ data using **StandardScaler**


## Data Visualization:

**Distribution of Genuine and fraud Trandactions**

![image](https://user-images.githubusercontent.com/38161827/183542311-4bac9a00-b234-41be-8ef9-3c7297d3ac40.png)

**Distribution of Fraud Transaction**

![image](https://user-images.githubusercontent.com/38161827/183542535-3d139a02-1b08-499d-9813-3a132be02ab7.png)

**Feature Correlation HEATMAP before Data-Preprocessing**

![image](https://user-images.githubusercontent.com/38161827/183542632-c7106ad4-ee7f-4d81-960b-1ed713b43ef3.png)

**Feature Correlation HEATMAP for after Data-Preprocessing**

![image](https://user-images.githubusercontent.com/38161827/183543238-c7522f3a-70f8-410e-a9ed-b5db8218229f.png)


## Models Used:

**Trial 1:** 
- DECISION TREE
- RANDOM FOREST

**Trial 2:** 
- Ensemble of 
  - XGboost, 
  - CatBoost, 
  - LGBMClassifier

## Results:

### Classification Reports
- ![image](https://user-images.githubusercontent.com/38161827/183544266-2af706c8-377a-4df9-ab93-e0c6c83b92cc.png)
- ![image](https://user-images.githubusercontent.com/38161827/183544289-cca73b9f-162d-4e84-96f6-e1eb5ff0a5df.png)
- Classification Report of Ensemble model
- ![image](https://user-images.githubusercontent.com/38161827/183544349-c3fee527-9324-47fc-aedb-095cf71fa89c.png)


## CONCLUSION

From above test, it was found that

Accuracy of both Random Forest and Decision Tree is almost equal;
The precision of Random Forest is more than that of DT.
Boosting models like XGboost, CatBoost, LGBMClassifier gives higher accuracy but lesser precision if tested individually. But if they are tested as an ensemble, it gives far better precision score.
In a fraud detection model, Precision is highly important because we want Fraud transactions to be predicted correctly and Genuine transactions to be left out.
If either of the 2 reasons are not fulfiiled we may catch the innocent and leave the culprit.
