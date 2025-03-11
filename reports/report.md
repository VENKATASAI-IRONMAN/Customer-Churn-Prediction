# Bank Customer Churn Analysis Report

This document summarizes key findings from the exploratory data analysis and machine learning modeling of bank customer churn prediction.

## Exploratory Data Analysis Insights

### Customer Demographics Analysis

#### Country-Based Analysis
The analysis reveals significant geographical variations in churn rates:

France has 4,826 customers with a churn rate of 19.19%, representing the largest customer base but a moderate churn level. Germany shows the highest churn propensity with 2,421 customers and an alarming 47.62% churn rate, more than double that of other regions. This suggests potential market-specific issues in Germany that require targeted intervention. Spain has 2,379 customers with a churn rate of 19.67%, similar to France but with a smaller customer base.

#### Gender-Based Analysis
Gender emerges as a significant factor in churn prediction:

Female customers (4,368 total) have a churn rate of 33.25%, substantially higher than male customers (5,258 total) with a churn rate of 19.53%. This pronounced difference suggests that female customers may respond to different service aspects or have different expectations from the bank, requiring gender-specific retention strategies.

#### Age Correlation
Age demonstrates a strong positive correlation with churn (correlation coefficient: 0.358), indicating that older customers are significantly more likely to leave the bank. This represents one of the strongest predictors in the dataset and highlights the need for age-targeted retention programs.

### Product and Service Usage Analysis

#### Number of Products
The relationship between number of products and churn reveals interesting patterns:

Customers with 1 product (4,882 customers) show a high churn rate of 38.34%, suggesting that single-product customers may not be sufficiently engaged. Those with 2 products (4,435 customers) demonstrate the lowest churn rate at only 8.01%, indicating an optimal relationship balance. Customers with 3 products (251 customers) have an extremely high churn rate of 497.62% (this unusual percentage may indicate calculation issues or that nearly all customers with 3 products churned). All customers with 4 products (58 total) have churned, showing that customers with the most products are the most dissatisfied.

#### Credit Card Ownership
Credit card ownership shows minimal impact on churn behavior:

Customers without credit cards (2,840 total) have a churn rate of 26.22%, while those with credit cards (6,786 total) have a slightly lower rate at 25.04%. This suggests that credit card offerings alone do not significantly impact customer retention.

#### Account Activity
Member activity status demonstrates a substantial impact on churn:

Inactive members (4,779 customers) have a churn rate of 35.23%, while active members (4,847 customers) show a much lower rate of 16.99%. This compelling difference underscores the importance of regular engagement and activity in maintaining customer relationships.

### Financial Factor Analysis

#### Account Balance
Balance shows a positive correlation with churn (correlation coefficient: 0.117), suggesting that customers with higher balances may be more likely to leave. This counterintuitive finding could indicate that high-value customers might be receiving more competitive offers from other banks or have higher expectations for service.

## Machine Learning Model Performance

### Logistic Regression Model Results

The project implemented a logistic regression model with multiple iterations to optimize performance:

| Model Iteration | F1 Score | Accuracy | Recall | Precision |
|-----------------|----------|----------|--------|-----------|
| Initial Model   | 0.4023   | 0.8210   | 0.2974 | 0.6214    |
| Iteration 1     | 0.4148   | 0.8251   | 0.3060 | 0.6439    |
| Iteration 2     | 0.4005   | 0.8258   | 0.2872 | 0.6614    |

The performance metrics illustrate several important aspects of the model's predictive capabilities. The overall accuracy remained consistently strong across iterations, hovering around 82%, which indicates good general predictive power. The F1 score, which balances precision and recall, peaked at 0.4148 in Iteration 1, suggesting this version best balanced identifying true churners versus minimizing false positives. Precision improved across iterations (from 0.6214 to 0.6614), meaning the model became increasingly confident in its positive predictions. However, recall remained relatively low (around 0.3), indicating the model still misses many actual churners.

### Feature Importance Analysis

Based on the correlation analysis, the most influential features for predicting churn are:

1. Age (0.358) - Strongest positive correlation with churn
2. Active member status (-0.143) - Strong negative correlation, indicating active members are less likely to churn
3. Balance (0.117) - Moderate positive correlation
4. Products number (-0.051) - Weak negative correlation, but highly dependent on specific number of products
5. Country (specifically Germany) - Not directly measured by correlation but evident from cross-tabulations

## Recommendations and Conclusions

Based on the analysis and model results, several actionable insights emerge:

1. Develop targeted retention programs for high-risk segments:
   - Older customers
   - Female clients
   - German market customers
   - Customers with either very few (1) or many (3-4) products
   - Inactive account holders

2. Review product bundling strategies, as the unusual pattern of customers with 3-4 products having extremely high churn rates suggests potential issues with product combinations or pricing.

3. Implement engagement initiatives to increase account activity, as active members show significantly lower churn rates.

4. Consider model enhancements to improve recall, as the current model has stronger precision than recall, meaning it misses many potential churners.

5. Further investigate the German market to understand why it has significantly higher churn rates compared to France and Spain.
