Customer Churn Prediction Using Machine Learning

Project Overview

Customer churn occurs when customers discontinue using a company's products or services. Predicting churn helps businesses identify customers who are likely to leave and take proactive retention measures.

This project develops an end-to-end machine learning solution to predict customer churn in the telecommunications industry using the IBM Telco Customer Churn dataset. Multiple classification algorithms were trained and evaluated, with particular emphasis on identifying as many potential churners as possible.

Objectives

- Analyse customer behaviour and identify patterns associated with churn.
- Perform data cleaning, preprocessing, and exploratory data analysis.
- Train and compare multiple machine learning classification models.
- Handle class imbalance and optimise the classification threshold.
- Prioritise recall to minimise missed churners.
- Interpret model predictions using feature importance and SHAP.
- Derive actionable business insights and recommendations.

Dataset

Dataset: IBM Telco Customer Churn

The dataset contains customer information, subscribed services, account details, and churn status.

Attribute| Description
Total records| 7,043
Original columns| 21
Target variable| "Churn"
Input features| 19 after removing "customerID"
Problem type| Binary classification

Target encoding:

- "0" – Customer stayed
- "1" – Customer churned

The "customerID" column was removed because it is an identifier and does not provide meaningful predictive information.

Technologies Used

- Programming: Python
- Data Manipulation: Pandas, NumPy
- Data Visualisation: Matplotlib, Seaborn
- Machine Learning: Scikit-learn
- Boosting Algorithm: XGBoost
- Model Explainability: SHAP
- Development Environment: Google Colab

Project Workflow

1. Dataset loading and initial understanding
2. Data cleaning and preprocessing
3. Exploratory Data Analysis (EDA)
4. Feature encoding and numerical scaling
5. Train-test splitting and model development
6. Training and comparison of multiple classification models
7. Handling class imbalance
8. Validation-based classification threshold selection
9. Final evaluation on an independent test set
10. Feature importance analysis
11. SHAP-based model explainability
12. Business insights and recommendations

Exploratory Data Analysis

EDA was performed to understand customer behaviour and identify patterns associated with churn.

Key observations:

- Month-to-month contract customers showed substantially higher churn rates than customers with longer-term contracts.
- Customers with shorter tenure were more likely to churn.
- Customers with higher monthly charges showed higher observed churn.
- Customers without online security or technical support had higher churn rates.
- Electronic check users showed higher observed churn compared with other payment methods.
- Fiber optic internet customers showed higher churn than DSL customers.

These observations represent associations in the dataset and do not establish causation.

Machine Learning Models

The following classification models were experimented with:

- Logistic Regression
- Balanced Logistic Regression
- Random Forest
- Balanced Random Forest
- Support Vector Machine (SVM)
- Balanced SVM
- XGBoost
- Class-weighted XGBoost

Model performance was evaluated using accuracy, precision, recall, F1-score, and confusion matrices.

Final Model

A class-weighted XGBoost classifier was selected for the final evaluation.

Since the primary business objective was to identify as many potential churners as possible, recall was prioritised.

A classification threshold of 0.28 was selected using validation data. Among the tested thresholds, it was the highest threshold that achieved at least 90% validation recall.

The final model was then evaluated on the independent test set.

Final Test Results

Evaluation Metric| Score
Accuracy| 64.44%
Precision| 42.19%
Recall| 91.71%
F1-Score| 57.79%

Confusion Matrix

Actual / Predicted| Stayed (0)| Churn (1)
Stayed (0)| 565| 470
Churn (1)| 31| 343

Key result: The model correctly identified 343 out of 374 actual churners, achieving 91.71% recall on the independent test set.

Although the model identified most actual churners, it also produced 470 false positives. This reflects the trade-off involved in prioritising recall over precision.

Model Explainability

Two techniques were used to understand the features influencing the model's predictions.

1. Feature Importance

XGBoost feature importance was extracted to identify the features the model relied on most.

Some of the most influential features included:

- Month-to-month contract
- Fiber optic internet service
- Technical support
- Online security
- Internet service type
- Payment method
- Customer tenure

Month-to-month contract emerged as the most influential feature in the model's feature importance analysis.

2. SHAP Analysis

SHAP (SHapley Additive exPlanations) was used to understand how individual features contribute to model predictions.

SHAP summary plots helped identify:

- Features pushing predictions towards churn.
- Features pushing predictions away from churn.
- The relative influence of features across customers.

This provided a deeper understanding of model behaviour beyond overall feature importance scores.

Business Insights

Based on the exploratory analysis and model results:

- Month-to-month customers represent a high-churn customer segment.
- Newer customers with shorter tenure may require additional engagement.
- Higher monthly charges are associated with increased churn.
- Customers without online security or technical support show higher observed churn.
- Electronic check users represent another customer segment worth investigating.

Business Recommendations

- Encourage longer-term contracts through suitable incentives.
- Improve onboarding and engagement strategies for new customers.
- Review pricing plans and provide suitable packages.
- Improve customer support and promote relevant additional services.
- Investigate customer concerns among high-risk customer groups.
- Use churn predictions to prioritise customer retention efforts.

Limitations

- The model produces a relatively high number of false positives, resulting in lower precision.
- The analysis is based on a single telecommunications dataset.
- Feature relationships do not necessarily imply causation.
- Model performance may differ when applied to real-world business data.

Future Improvements

- Perform hyperparameter tuning and model optimisation.
- Improve precision while maintaining high recall.
- Experiment with additional feature engineering techniques.
- Evaluate the model on other customer churn datasets.
- Deploy the model through a web application or interactive dashboard.
- Develop a system for monitoring model performance over time.

Conclusion

This project demonstrates an end-to-end application of machine learning to a real-world customer retention problem.

The final class-weighted XGBoost model achieved 91.71% recall on the independent test set, successfully identifying a large proportion of customers who actually churned.

Feature importance and SHAP analysis provided additional insights into the factors influencing customer churn predictions.

Overall, the project demonstrates the complete machine learning workflow, from data preprocessing and exploratory analysis to model development, evaluation, explainability, and business recommendations.

---

Project Type: Machine Learning | Supervised Learning | Binary Classification

Dataset: IBM Telco Customer Churn
