# credit-risk-classification

An overview of the analysis:

The Purpose of this analysis was to use various techniques to train and evaluate a model based on loan risk. The dataset used is of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers based on loan size, interest rate, borrower’s income, debt to income ratio, number of accounts, derogatory remarks, total debt and loan status. The goal is to predict the healthy loans and the high-risk loans.

To gain the goal, firstly I created the labels for which I set “y” from the “loan_status” column and then created the features with the remaining columns from the lending dataset. A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.
Then I split the data into Training datasets and Testing datasets by using the train_test_split.

Then I Created a Logistic Regression Model with the Original Data and Fitted a logistic regression model by using the training data (X_train and y_train).
The next step was to Save the predictions for the testing data labels by using the testing feature data (X_test) and the fitted model. After that I evaluated the model’s performance by doing the following:
o Calculating the balanced accuracy score.
o Generating a confusion matrix.
o Printing the classification report.
The model was good at predicting the healthy loans with a f1 score at 1.00 but it did not do very well with the high-risk loan with a f1 score at 0.88. This likely happened due to the unbalanced dataset used in the training model. So, I resampled the dataset using RandomOverSampler model which balanced the sample data for healthy as well as high-risk loans. I repeated the same steps again to see that the prediction was better this time with an increased f1 score at 0.93 for high-risk loans while it remained the same for the healthy loans that is 1.00.

Results-

Model 1:

Balanced Accuracy Score: 0.94


Precision:	1.00 for healthy loans,

       	0.87 for high-risk loans
       
       
Recall: 	1.00 for healthy loans, 

       	0.89 for high-risk loans

Re- sampled Model 2:

Balanced Accuracy Score: 1.00

Precision: 1.00 for healthy loans,

       	0.87 for high-risk loans.
       
       
Recall:	1.00 for healthy loans,

       	1.00 for high-risk loans.



Summary:  

In short, the second model did a good job at predicting the high-risk loans when we compare the f1 score for both the models. The accuracy score is 1 on the second one whereas it is .94 in the initial logistic regression model. I would prefer the second model because the first model had an imbalanced data meaning the healthy loans were more in numbers in comparision to high-risk loans  whereas the second model was resampled using RandomOverSampler which took the imbalance into consideration making the prediction more accurate.
