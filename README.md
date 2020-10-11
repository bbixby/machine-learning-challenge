# Machine Learning Exercise - Exoplanet Exploration

![exoplanets.jpg](Images/exoplanets.jpg)

## Background

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system.

To help process this data, I created three machine learning models capable of classifying candidate exoplanets from the raw dataset.

- - -

## Process

The raw Kepler data is a csv file with 41 columns and 6,992 rows.

The first column, koi_disposition, is the target to predict: 'CONFIRMED', 'FALSE POSITIVE', or 'CANDIDATE'.

The other 40 columns are all numerical data whose contribution to the target is to be determined with the model.
[Column descriptions available here.](https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html)

Each model followed this general process:
1. CSV import and data cleaning
2. Set target y with label encoding and remaining columns as X
3. Test train split X and y
4. Standard scaling of X
5. Train model
6. Tune model with GridSearchCV
7. Test accuracy of tuned model

## Models & Results
Models:
* RandomForest (RF)
* KNeighborsClassifier (KNN)
* Support Vector Machine (SVM)

Classification report test accuracy:
* RF = 89%
* KNN = 67%
* SVM = 60%

RF model saved as matthewDebnarRF.sav based on best accuracy.

## Suggested Improvements
1. Drop features down from full set of 40 to eliminate noise. Features may be cut in half by eliminating RF score < 2%
2. Try broader model assumptions. RF, KNN, and SVM models all have parameters that may be expanded, run, and tweaked based on results.
3. Additional tuning may be helpful to bring up all models' accuracies.
4. Graph the features to the targets to review their relevance.


