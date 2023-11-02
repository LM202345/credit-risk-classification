# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis I completed for the machine learning models used in this Challenge.

####  Explain the purpose of the analysis.

The purpose of the analysis is evaluate how the loan risk model change using resampled training data. 

#### Explain what financial information the data was on, and what you needed to predict.

The dataset contains historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

#### Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

The variable trying to predict is the loan risk

There are an equal number of instances for both healthy (0) and high-risk (1) loans, indicating a balanced dataset after resampling

0    75036
1    75036



#### Describe the stages of the machine learning process you went through as part of this analysis.


* Data Collection

* Data Preprocessing 

* Data Splitting

* Data Resampling 

* Model Selection: select the logistic regression model for this analysis due to its suitability for binary classification problems and interpretability. The model was then trained on the oversampled training data.

* Model Evaluation: Using the testing set, assess the model's performance by calculating various metrics such as precision, recall, and F1-score. This evaluation allowed to understand how well the model could classify healthy and high-risk loans.

* Model Interpretation


#### Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).


In this analysis, employed two primary methods:
First, the Logistic Regression algorithm as classification method. Logistic Regression is a powerful tool for binary classification tasks, making it well-suited for predicting loan classifications as healthy or high-risk.

Second, to tackle the challenge of class imbalance in the dataset, applied a resampling method known as Random OverSampling. This technique involves oversampling the minority class (high-risk loans) to balance the dataset, ensuring that the model receives adequate exposure to both healthy and high-risk loan examples. This approach allowed to mitigate the class imbalance issue and build a more robust model for loan classification.

## Results



* Machine Learning Model 1:Logistic Regression Model with the Original Data

* Description of Model 1 Accuracy, Precision, and Recall scores.
           precision    recall  f1-score   support

           0       1.00      0.99      1.00     18775
           1       0.86      0.90      0.88       609

    accuracy                           0.99     19384
   macro avg       0.93      0.95      0.94     19384
weighted avg       0.99      0.99      0.99     19384

The model achieves an overall accuracy of 99%, meaning that 99% of the predictions are correct. In summary, the logistic regression model demonstrates good performance in classifying both healthy and high-risk loans, with a high degree of precision and recall.


* Machine Learning Model 2:Logistic Regression Model with Resampled Training Data

* Description of Model 2 Accuracy, Precision, and Recall scores.

  
           precision    recall  f1-score   support

           0       0.99      0.99      0.99     75036
           1       0.99      0.99      0.99     75036

    accuracy                           0.99    150072
   macro avg       0.99      0.99      0.99    150072
weighted avg       0.99      0.99      0.99    150072

In summary, the logistic regression model, trained with oversampled data, excels in its ability to predict both healthy and high-risk loans with a high degree of accuracy, precision, recall, and F1-score

## Summary

#### Which one seems to perform best? How do you know it performs best?


Model 2, which was trained with resampled training data, with an accuracy of 99% and balanced precision and recall for both label 0 and label 1.
The performance of Model 2 is notably better, with higher precision and recall scores for both healthy (0) and high-risk (1) loans, compared to Model 1.
Model 2, trained with resampled data, is recommended for scenarios where balanced precision and recall for both healthy and high-risk loans are essential. This model provides an optimal trade-off between accurately predicting both label 0 and label 1 instances.

In summary, Model 2, trained with resampled data, is recommended as it delivers a well-balanced performance for both healthy and high-risk loan predictions, which is often a critical requirement in risk assessment and lending decisions.


#### Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
Yes, if the focus is primarily on healthy loans (label 0) and the goal is to achieve a high level of precision in predicting them, Model 1 with the original data may be considered, as it has higher precision for label 0 compared to Model 2.


