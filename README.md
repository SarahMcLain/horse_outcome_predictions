# horse_outcome_predictions

## Repository for machine learning from kaggle competition

### Predict whether a horse lived or died

The first step of the competition was to clean the data.  Two methods were employed. The first one took the original data and concatenated it with the training data.  The second method only used the training data.  


# Method One

Read in the original data, training data, test data. 

Concatenate original data and training data and name it horse_data; look at the columns in the horse_data.

Horse_data has three unique values for "outcome": lived, died, euthenized.  Since euthenized means the horse died I chose to combine these two values to make the outcome simpler. 

Next check to make sure the concatenated data has the same columns as the test data and find if there are any missing columns; check the length of the columns.  

Original data is missing id column therefore is missing values. Fill all na id values with 0. 

Check the data types of the concatenated data. Since this dataset has a lot of "object" data types.  Model picked will be a classifier. 

Find the null values in the dataset.  For numeric values fill in the column median and for categorical features fill in none. 

Find categorical features that have different unique values.  Fix values so that they match. Check to make sure values are matching now. 

# Make X and y for target variable for outcome

Encode X and y using LabelEncoder

Apply smote to X and y 

# Split the dataset into X_train, X_test, y_train, y_test

Model: gradientBoosting Classifier

Run a gridsearch for the best parameters 

Run the best_model on X_train, y_train and then read in X_test to make predictions. 

# Evaluations 

Evaluate the model's accuracy using the F-1 score.

I also chose to look at precision, recall score, confusion matrix, and a classification report.

# Results

F-1 Score: 0.7980
Precision: 0.80
Recall: 0.80

      precision    recall  f1-score   support

           0       0.81      0.85      0.83       176
           1       0.79      0.73      0.75       131

    accuracy                           0.80       307
   macro avg       0.80      0.79      0.79       307
weighted avg       0.80      0.80      0.80       307


# Save the model

# Use the model on given kaggle Test Data

Load the saved model.

Encode the test data in the same way as X.

Check to make test_data has the same number of columns as X_train

Make test predictions using the loaded model.

Create a dataframe to hold the predicted outcome with the id from the test data.

Undo the encoding for y.

Save the uncoded dataframe to a csv file.

# Visulizations

Feature importance






