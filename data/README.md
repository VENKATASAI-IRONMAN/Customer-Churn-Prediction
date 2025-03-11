# Bank Customer Churn Dataset

## Dataset Overview
This dataset contains information about bank customers and whether they have churned (left the bank). It serves as the foundation for building predictive models to identify customers at risk of leaving the bank's services.

## Source
The dataset is sourced from Kaggle: [Bank Customer Churn Prediction Dataset](https://www.kaggle.com/datasets/gauravtopre/bank-customer-churn-dataset/)

## Data Description
The dataset consists of 10,000 records with 12 columns (11 features and 1 target variable). Each row represents a bank customer with various attributes.

### Column Details

| Column Name | Description | Data Type | Example Values |
|-------------|-------------|-----------|---------------|
| customer_id | Unique identifier for each customer | Integer | 15634602, 15647311 |
| credit_score | Credit score of the customer | Integer | 350-850 |
| country | Customer's country of residence | Categorical | France, Germany, Spain |
| gender | Customer's gender | Categorical | Female, Male |
| age | Customer's age in years | Integer | 18-92 |
| tenure | Number of years the customer has been with the bank | Integer | 0-10 |
| balance | Account balance of the customer | Float | 0.00-250898.09 |
| products_number | Number of bank products the customer uses | Integer | 1-4 |
| credit_card | Whether the customer has a credit card | Binary | 0 (No), 1 (Yes) |
| active_member | Whether the customer is an active member | Binary | 0 (No), 1 (Yes) |
| estimated_salary | Estimated salary of the customer | Float | 11.58-199992.48 |
| churn | Whether the customer left the bank (target variable) | Binary | 0 (No), 1 (Yes) |

## Statistical Summary
- **Records**: 10,000 customers
- **Target distribution**:
  - Not churned (0): 79.63% (7,963 customers)
  - Churned (1): 20.37% (2,037 customers)
- **Numerical features range**:
  - credit_score: 350-850 (mean: 650.53)
  - age: 18-92 (mean: 38.92)
  - tenure: 0-10 (mean: 5.01)
  - balance: 0.00-250898.09 (mean: 76485.89)
  - estimated_salary: 11.58-199992.48 (mean: 100090.24)

## Using The Dataset
To work with this dataset:

1. Load the data using pandas:
   ```
   import pandas as pd
   data = pd.read_csv("Bank Customer Churn Prediction.csv")
   ```

2. Perform basic exploration:
   ```
   # View data structure
   data.head()
   data.info()
   
   # Get statistical summary
   data.describe()
   
   # Check for missing values
   data.isnull().sum()
   ```

3. Prepare for modeling:
   ```
   # Convert categorical variables
   data_encoded = pd.get_dummies(data, drop_first=True)
   
   # Split features and target
   X = data_encoded.drop(['churn', 'customer_id'], axis=1)
   y = data_encoded['churn']
   ```

## Data Preprocessing Recommendations
For optimal modeling results:

1. Remove the 'customer_id' column as it's just an identifier with no predictive value
2. Convert categorical features (country, gender) to numerical using one-hot encoding
3. Consider scaling numerical features, especially those with wide ranges
4. Evaluate class imbalance effects on model performance (20.37% churn rate)