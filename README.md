# credit-risk-classification
Train and evaluate a model that predicts loan risk.


# Credit Risk Analysis Report

## Overview of the Analysis
Purpose: This model was built to help lenders receive the most accurate predictions of the creditworthiness of borrows using machine learning. 

Data:
The financial information was based on historical lending activity. Here is what each of the columns of data represented:
  * loan_size: amount requested by borrower
  * interest_rate: interest rate associated with loan
  * borrow_income: borrows income
  * debt_to_income: ratio of borrows total debt to their income
  * num_of_accounts: number of accounts borrower currently has
  * derogatory_marks: number of derogatory marks (i.e. late payments, bankruptcies, etc.) on the borrowers credit report
  * total_debt: amount of debt owed by borrower
  * loan_status: status of loan (0 = healthy, 1 = high-risk)

The debt, income, ratio of debt to income, and derogatory marks were important pieces of financial information for the model to predict on. In order for the model to make predictions and be evaluated, the data had to be separated into to labels and features. The X variable would include everything from the original dataframe (features) except for the loan status (labels), that way the predictions can be made without the answers, for comparison. The y variable included just the labels, meaning it was a dataframe of just the loan statuses.

Using the train_test_split function from sklearn, the data was split into training and testing data. The training data will be used to train the model, then the testing data evaluates the accuracy of said model. First a Logitic Regression Model is created with the original data. An lr model is fit to the training data, then predictions are made using the X_test data and the fitted model. 

After fitting the model using the training data and making predictions using the testing data, the model's performance is evaluated. This evaluation is done by generating a confusion matrix and a classification report. The confusion matrix allows you to visualize the counts of true positives, true negatives, false positives, and false negatives. The classification report provides a more detailed summary of the performance metrics. It will include precision, recall, F1-score, support, and accuracy. We will discuss the importance of these metrics in the summary. 

* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).

## Results
Machine Learning Model:
  * Healthy Loan:
      * Precision: 100%
      * Recall: 99%
      * F1-score: 100%
      * Support: 18765
  * High-Risk Loan:
      * Precision: 85%
      * Recall: 91%
      * F1-score: 88%
      * Support: 619
  * Overall Accuracy: 99% 

## Summary

Our results show that overall this model performs quite well with an accuracy of 99%. The model has a stronger ability to predict healthy loans vs risky loans with a 100% precision for healthy vs. 85% precision for risky. The precision measures the proportion of true positive predictions out of all the positive predictions made. The healthy loans also had a higher recall than the risky. Recall measures the proportion of true postive predictions out of all the actual positive instances. That means that this model has a higher ability to correctly identify healthy loans vs risky. 

For this model, I would say that both measures are important, as you want to continue your business and give out loans whenever possible. However, because high-risk loans can cause more signifcant monetary damage, I would say that it is more important to accurately predict high-risk loans. The precision and recall are still fairly high, and therefore I would trust this model.
