# Telecom Customer Churn Prediction Using Data-Driven Machine Learning Models
This project aims to address customer churn prediction for a telecom company, specifically focusing on high-value customers in the Indian and Southeast Asian markets, where prepaid models dominate. Churn prediction is critical in this context due to the competitive nature of the telecom industry and the significant revenue contributions made by high-value customers. Here's a summary of the key steps and insights:

## Problem Definition
- **Churn in the Telecom Industry**: High customer churn rates (15-25%) pose a major challenge, and customer retention is more cost-effective than acquisition. The focus is on high-value customers, who make up 20% of the customer base but contribute 80% of revenue.
- **Business Goal**: Predict churn for high-value customers based on customer behavior over the first three months, enabling telecom companies to take corrective actions during the "action phase" before churn occurs.
## Data Preparation
- **Feature Engineering**: New features were derived based on customer activity (e.g., total calls, internet usage). Customers' recharge activity over months 6, 7, and 8 was analyzed to filter high-value customers.
- **High-Value Customer Definition**: High-value customers are those whose average recharge value in the first two months is greater than or equal to the 70th percentile (INR 478). This leaves around 29,900 rows.
- **Churn Labeling**: Churners are identified as those with no outgoing or incoming calls and no data usage during the churn phase (month 9). After tagging, the data corresponding to the churn phase is removed.
## Modeling Approach
- **Preprocessing**: Missing values were imputed, and unnecessary columns (like date columns) were dropped. After preprocessing, outliers were treated.
- **PCA for Dimensionality Reduction**: To reduce the dataset's complexity, PCA was applied. The model retained 60 components that explained 94% of the variance.
- **Handling Class Imbalance**: As the dataset is imbalanced (about 8% churners), SMOTE was used to upsample the minority class during training.
## Modeling and Evaluation
- **Logistic Regression with PCA**: Achieved an accuracy of 84.1% on the test set with 100% sensitivity, meaning it captured all churners but had a specificity of 83%, leading to some false positives.
- **Decision Tree with PCA**: Post-tuning, the decision tree achieved a test accuracy of 82.17%, with a sensitivity of 94.48% and specificity of 80.99%.
- **Random Forest with PCA**: After hyperparameter tuning, the random forest model yielded an accuracy of 88.51% on the test set with a well-balanced performance between sensitivity and specificity.
## Key Predictors
From the models (especially tree-based models), important predictors of churn include:
- Total recharge amounts in earlier months.
- Data usage patterns (e.g., 2G/3G data volume).
- Call activity (incoming and outgoing).
## Recommendations for Churn Management
- **Proactive Engagement**: Target high-value customers during the "action phase" with personalized offers, discounts, or service improvements to reduce churn likelihood.
- **Feature Monitoring**: Keep track of key indicators such as a sharp decline in recharge amounts or data usage, which signal a customer moving towards the churn phase.
- **Data-Driven Strategies**: Use the churn prediction model to design data-driven retention strategies, focusing marketing efforts on high-risk, high-value customers.

This approach provides a comprehensive framework for identifying and reducing churn in the telecom industry, with a strong emphasis on predictive modeling and business impact.
