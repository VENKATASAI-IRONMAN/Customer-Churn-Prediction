# Bank Customer Churn Prediction

## 📊 Project Overview
This project focuses on predicting customer churn for a banking institution using machine learning techniques. Customer churn—when customers stop doing business with a company—represents a significant challenge for banks as acquiring new customers typically costs more than retaining existing ones. By identifying customers at risk of leaving and understanding the factors that drive churn, banks can implement targeted retention strategies to improve customer loyalty and maintain profitability.

The analysis employs logistic regression modeling to predict which customers are likely to leave the bank based on demographic information, banking relationship characteristics, and account activity patterns.

## 🚀 Installation & Requirements

### Prerequisites
- Python 3.x
- Jupyter Notebook

### Installation
Clone this repository:
```
git clone https://github.com/your-username/bank-customer-churn-prediction.git
cd bank-customer-churn-prediction
```

Install required dependencies:
```
pip install -r requirements.txt
```

## 📋 Dataset Details
The analysis uses a bank customer dataset containing information about 10,000 customers with the following attributes:

- **Demographics**: Age, gender, country of residence
- **Banking relationship**: Tenure, number of products, credit card ownership
- **Financial indicators**: Credit score, account balance, estimated salary
- **Activity metrics**: Active member status
- **Target variable**: Customer churn status (0=retained, 1=churned)

The dataset exhibits a class imbalance with approximately 20.37% of customers having churned. For detailed information about the dataset structure, statistics, and preprocessing recommendations, see the [data/README.md](data/README.md) file.

## 🔍 Key Findings (EDA Summary)

### Customer Segments with Higher Churn Risk

The exploratory data analysis revealed several critical insights:

German customers show a remarkably high churn rate of 47.62%, compared to around 19% for French and Spanish customers. This geographical disparity suggests market-specific issues that require attention. Female customers exhibit a churn rate of 33.25%, significantly higher than male customers at 19.53%, indicating potential gender-based differences in service preferences or expectations.

Age demonstrates a strong positive correlation with churn (correlation coefficient: 0.358), making it one of the most powerful predictors in the dataset. This finding suggests that older customers require special attention in retention efforts.

### Product and Service Usage Patterns

The relationship between product usage and churn follows a U-shaped pattern. Customers with only one product show a high churn rate (38.34%), while those with two products have the lowest churn rate (8.01%). However, customers with three or four products demonstrate extremely high churn rates, suggesting potential issues with product bundling or pricing strategies.

Account activity emerges as a critical factor, with inactive members showing a churn rate more than double that of active members (35.23% vs. 16.99%). This highlights the importance of regular engagement for customer retention.

For a comprehensive analysis of all factors and their relationships with churn, see the [reports/README.md](reports/README.md) file.

## 📓 How to Use the Notebook

The Jupyter notebook `JETTI_ZC11772_FINAL_PROJECT.ipynb` contains the complete analysis workflow:

1. **Data Loading and Preparation**: Loading the dataset, initial exploration, and preprocessing steps
2. **Exploratory Data Analysis**: Univariate, bivariate, and multivariate analyses with visualizations
3. **Feature Engineering**: Creating dummy variables for categorical features and scaling numeric features
4. **Model Building**: Implementing logistic regression with various feature combinations
5. **Model Evaluation**: Assessing performance using accuracy, precision, recall, and F1 score metrics

To run the notebook:
```
jupyter notebook JETTI_ZC11772_FINAL_PROJECT.ipynb
```

## 📊 Results & Visualizations

### Model Performance
The logistic regression model achieved the following performance metrics:
- Accuracy: 82.51%
- Precision: 64.39%
- Recall: 30.60%
- F1 Score: 41.48%

These results indicate that while the model can identify a significant portion of churners, there remains room for improvement, particularly in recall. The model is more precise than sensitive, meaning it misses many actual churners but has relatively few false positives.

### Feature Importance
The most influential factors for predicting churn are:
1. Age (older customers more likely to churn)
2. Active member status (inactive members more likely to churn)
3. Country of residence (particularly Germany)
4. Number of products (especially very few or many products)
5. Account balance (higher balances associated with increased churn)

## 🔮 Future Enhancements

Several opportunities exist to expand and improve this project:

1. **Advanced Modeling Techniques**: Implement ensemble methods (Random Forest, XGBoost), neural networks, or other algorithms that might capture more complex patterns in the data.

2. **Feature Engineering**: Create interaction terms and derived features that might better explain churn behavior, such as balance-to-salary ratio or product usage patterns over time.

3. **Addressing Class Imbalance**: Experiment with techniques like SMOTE, class weighting, or cost-sensitive learning to improve the model's ability to identify churners.

4. **Customer Segmentation**: Develop segment-specific models that might better capture the unique factors driving churn within different customer groups.

5. **Temporal Analysis**: If time-series data becomes available, implement models that can predict not just if but when a customer is likely to churn.

6. **Hyperparameter Optimization**: Conduct more extensive grid search or other optimization techniques to fine-tune model parameters.

7. **Cost-Benefit Analysis**: Develop a framework to quantify the financial impact of correctly identifying churners versus the cost of retention programs.

## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgements
- Dataset provided by Kaggle
- Analysis conducted using scikit-learn, pandas, numpy, matplotlib, and seaborn
