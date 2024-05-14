# credit-risk-classification
Using supervised machine learning to classify customers' credit risk (Columbia boot camp project)

# Module 12 Report

## Overview of the Analysis

The purpose of this analysis is to classify bank customers as having good or bad credit risk. Doing so will help the bank decide whether it should make loans to certain customers based on certain criteria. 

This analysis looked at historical loan data. Data included the loan size and interest rate on the loan. It also included the customers' income, debt-to-income ratio, number of financial accounts they hold, and total debt. There is also a metric of "derogatory marks", which presumably accounts for customers' financial history and any loan defaults or other negative issues they have had.

The model uses continuous data to predict the probability that a future customers' loan status will be good or bad; that is, whether the customer will be a good candidate for a loan (e.g., the customer will be able to pay back the loan on time) or if they will be a high-risk canddiate (e.g., there is a risk of defaulting on the loan).

To make these predictions, I used a supervised machine learning model. To begin, I split the existing data into features to use as inputs and data to be the output. I then split these into training and testing groups. The model would use the training groups to understand the relationship between the features to see if and how they affected the output. Put another way, the model would analyze the financial data to see if and how customers' were labeled as low- or high-risk. After that analysis, the model would then use its predictions on the test data, then compare its results to the actual output results. The results of the comparison would tell me if the model was accurate.

For this particular model, I used scikit-learn's LogisticRegression algorithm, using the lbfgs solver and a random state of 1. To evaluate the model, I used scikit-learn's confusion_matrix and classification_report functions from the metrics sub-module.

## Results
* Machine Learning Model:
    * feature       precision   recall  f1-score    support
        0           100%        99%     100%        18765
        1           85%         91%     88%         619
    * accuracy:                         99%         19384
    * macro avg:    92%        95%      94%         19384
    * weighted avg: 99%        99%      99%         19384
    

## Summary
The results of the machine learning model show that the model is successful at predicting 0 labels, or customers' positive credit-worthiness (that is, customers who are likely to pay back the loan). With an accuracy of 100% accruacy for 0 labels and 99% accuracy overall, I would recommend using this model to evaluate customers, but only to confirm giving a loan. I would not recommend using this model to deny customers a loan, as the accuracy for 1 labels is only 88%. Even if the accuracy were higher, I would still recommend that the bank not blindly rely on a model to deny customers. 

Because this is a binary choice--either a customer is loan-worthy or not--we can assume that if a customer does not score highly on being loan-worthy, they must therefore have a high credit risk. However, it is important for the bank to take the customers' full history and context into account if denying a loan. There could be additional factors not in the data that may make a a customer a higher or lower credit risk. Given that there is a history of bias in lending, it is imperative for the bank to ensure it has a holistic view of a customer before making a decision. The bank could use this model as a primary assessment tool to gague how much to ask a potential customer, or it could save the bank time by making positive assessments only; more work would be necessary to make any negative assessments. 