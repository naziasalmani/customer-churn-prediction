Customer Churn Prediction Using Machine Learning

Project Overview

Customer churn occurs when customers discontinue using a company's products or services. Predicting customer churn helps businesses identify customers who may leave and take proactive retention measures.

This project uses machine learning to predict customer churn in the telecommunications industry using the IBM Telco Customer Churn dataset.

Objectives

- Analyse customer behaviour and identify churn patterns.
- Perform data cleaning and exploratory data analysis.
- Train and compare multiple machine learning classification models.
- Prioritise recall to identify potential churners.
- Interpret predictions using feature importance and SHAP.
- Provide actionable business recommendations.

Dataset

IBM Telco Customer Churn Dataset

- Total records: 7,043
- Original features: 20
- Target variable: "Churn"
- Classification type: Binary classification

Target encoding:

- "0" – Customer stayed
- "1" – Customer churned

Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- XGBoost
- SHAP
- Google Colab

Project Workflow

1. Dataset loading and understanding
2. Data cleaning and preprocessing
3. Exploratory Data Analysis (EDA)
4. Feature encoding and scaling
5. Model training and comparison
6. Class imbalance handling
7. Validation-based threshold selection
8. Final model evaluation
9. Feature importance analysis
10. SHAP explainability
11. Business insights and recommendations

Machine Learning Models

The following models were experimented with:

- Logistic Regression
- Balanced Logistic Regression
- Random Forest
- Balanced Random Forest
- Support Vector Machine (SVM)
- Balanced SVM
- XGBoost
- Class-weighted XGBoost

Final Model

A class-weighted XGBoost classifier was selected for the final evaluation.

A classification threshold of "0.28" was selected using validation data to prioritise recall.

Final Test Results

Metric| Score
Accuracy| 64.44%
Precision| 42.19%
Recall| 91.71%
F1 Score| 57.79%

Confusion Matrix

| Predicted Stayed| Predicted Churn
Actual Stayed| 565| 470
Actual Churn| 31| 343

The model identified 343 out of 374 actual churners in the test set.

Model Explainability

Feature importance and SHAP were used to understand the features influencing model predictions.

Important features included:

- Month-to-month contract
- Customer tenure
- Monthly charges
- Fiber optic internet service
- Online security
- Technical support
- Payment method

SHAP summary plots were used to understand how individual features push predictions towards or away from churn.

Business Insights

- Month-to-month customers show higher churn rates.
- Customers with shorter tenure are more likely to churn.
- Higher monthly charges are associated with increased churn.
- Customers without online security or technical support show higher churn rates.
- Electronic check users show higher observed churn rates.

Business Recommendations

- Encourage longer-term contracts through suitable incentives.
- Improve onboarding and engagement for new customers.
- Review pricing plans and offer suitable packages.
- Improve customer support and promote additional services.
- Investigate customer concerns among high-risk customer groups.

Limitations

- The model produces false positives, resulting in relatively low precision.
- Results are based on a single telecommunications dataset.
- The model does not establish causal relationships.
- Performance may differ when applied to real-world business data.

Future Improvements

- Hyperparameter tuning and model optimisation.
- Improve precision while maintaining high recall.
- Test on additional customer datasets.
- Deploy the model through a web application or interactive dashboard.

Conclusion

This project demonstrates the application of machine learning to a real-world customer retention problem.

The final XGBoost model achieved 91.71% recall on the independent test set, helping identify a large proportion of customers who actually churned.

Feature importance and SHAP analysis provided additional insight into the factors influencing predictions.

The project demonstrates an end-to-end machine learning workflow, from data preprocessing and model development to explainability and business recommendations.

---

Project Type: Machine Learning | Supervised Learning | Binary Classification
