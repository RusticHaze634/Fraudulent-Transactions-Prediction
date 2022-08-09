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


## Data Visualization:

**Distribution of Genuine and fraud Trandactions**
![image](https://user-images.githubusercontent.com/38161827/183542311-4bac9a00-b234-41be-8ef9-3c7297d3ac40.png)
