# Module 12 Report Template

## Overview of the Analysis

The purpose of this analysis was to see if we can train a model that can predict whether a loan made to an indiviudal was healthy or more importantly was high risk, and to see if we can improve the model by oversampling the high-risk loans in the training data set. The inputs or features fed into the model included loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks and total debt. The output or the target was the loan status which was represented by either a `0` "healthy loan" or a `1` a "risky-loan". The data set was clearly imbalanced as the there were 75k instances of healthy loans vs 2500 instances of risky loans. 

Since the goal was to identify a model that would identify whehter a loan goes into a healthy or risky class we used a classification machine learning model, logistic regression. Before feeding the data set into the model we first divided it into training and testing data points. Training points to train the model and testing points to test its efficiency. After fitting the model to the training data set we created predictions of our target (whether risky or healthy) using the features of the testing data set and we evaluated how those predicitons compared to the targets of the same testing data set. We used three evaluation techniques within the scikit-learn and imbalanced-learn libraries (balanced_accuracy_score, confusion_matrix, classification_matrix_imbalanced).

We also did the same process but with a logistic regression model that was trained on resampled data. As mentioned previously, the healthy class was significanlty larger than the risky class. So I used the random over sampling technique from the imbalanced learn library to create a resampled training dataset with radomly overgenerated instances of the risky loan. However, to test the model with the resampled training data set we still used the original testing data.


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Accuracy - .952
  * Precision - .85
  * Recall - .91



* Machine Learning Model 2:
  * Accuracy - .994
  * Precision - .84
  * Recall - .99

## Summary


The model with the original training data has high accuracy but that is skewed by the fact that most of the data points are for a healthy loan. To see if the model does well at finding the high-risk loans we have to look at the precision and recall scores. Both of these are performing well with 85% and 91% respectively. Meaning that of the model's predictions of high-risk loan 85% of them correct, and of all the truly high-risk loans the model was able to catch 91% of them. Since the harm of not catching a high-risk loan is higher than falsely flagging a healthy loan as high-risk we are willing to sacrifice precision for recall and it would be appropriate to rebalance the classes. The model with the oversampled data loses a little bit of precision since it is built with a significantly higher instances of high-risk loans, but in turn significantly increases recall from .91 to .98. So the model trained with oversampled instances of high-risk loans is better at identifying the high-risk loans it is also more accurate (99% vs 95%). 
