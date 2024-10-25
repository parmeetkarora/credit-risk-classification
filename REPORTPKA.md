## Overview of the Analysis

Purpose of the Analysis

The purpose of this analysis was to develop a machine learning model that predicts whether a loan will be classified as 0 (healthy loan) or 1 (high-risk loan). The data used in this analysis contains financial information regarding loans, including details such as loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, and total debt. These variables help assess the risk of loans, and the goal was to create a model that can accurately predict loan statuses based on these features.
The target variable was loan_status, where:

•	0 represents a healthy loan.
•	1 represents a high-risk loan.

To get a sense of the distribution, the target variable (loan_status) had the following value counts:
•	0 (healthy loans): 18,765
•	1 (high-risk loans): 619

This shows a significant class imbalance, with far more healthy loans than high-risk loans.


Machine Learning Process


The process followed in this analysis included the following stages:

1.	Data Preprocessing: The dataset was cleaned, and any missing or inconsistent data was handled. The features were standardized where necessary, and the target variable (loan_status) was encoded as a binary label.

2.	Train-Test Split: The data was split into training and testing sets to ensure that the model was evaluated on unseen data.

3.	Model Selection: A logistic regression model (LogisticRegression) was selected due to its effectiveness in binary classification problems.

4.	Model Training: The model was trained on the training dataset.

5.	Model Evaluation: The model's performance was evaluated using accuracy, precision, recall, and F1-scores.

Methods Used


•	Logistic Regression: This was chosen for its simplicity and interpretability in binary classification tasks, particularly when predicting a binary outcome like loan status.

Results

Machine Learning Model 1: Logistic Regression

•	Accuracy: 0.99 — The model performed extremely well in predicting loan status overall.
•	Precision:
o	Healthy loans (0): 1.00 — All loans predicted as healthy were indeed healthy.
o	High-risk loans (1): 0.85 — 85% of loans predicted as high-risk were actually high-risk, indicating some false positives.

•	Recall:
o	Healthy loans (0): 0.99 — The model correctly identified 99% of the actual healthy loans.
o	High-risk loans (1): 0.91 — The model identified 91% of the actual high-risk loans, missing 9%.
•	F1-Score:
o	Healthy loans (0): 1.00 — Perfect balance between precision and recall.
o	High-risk loans (1): 0.88 — A reasonably good balance, but lower than the healthy loan class.

Confusion Matrix:

[[18663   102]  # True Negatives (correctly predicted healthy) and False Positives
 [   56   563]] # False Negatives and True Positives (correctly predicted high-risk)


Summary

•	Best Performing Model: Logistic regression performed exceptionally well, especially for predicting healthy loans (0), with near-perfect precision and recall. The model also performed well in identifying high-risk loans (1), with a recall of 91% and precision of 85%.
•	Performance Evaluation: Given that the majority of loans are healthy, the model's high accuracy (99%) is largely due to correctly predicting healthy loans. However, for business use, it may be more important to focus on improving the precision for high-risk loans, to reduce false positives (where a healthy loan is misclassified as high-risk).

•	Recommendation: If the objective is to minimize risk and ensure that high-risk loans are correctly identified, this model is appropriate but could be further improved by tuning its decision threshold or using more advanced techniques like oversampling the minority class.

Overall, the logistic regression model performs very well but could be optimized for better high-risk loan prediction.

