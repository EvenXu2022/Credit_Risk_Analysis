 Credit_Risk_Analysis

## Overview
This project analyzes the credit risk dataset by implementing Multiple Machine Learning algorithms and evaluates the best performance based on multiple prediction results of High-Low risk loans.

## Resources
- Data Source: LoadStats_2019Q1.csv
- Tools: Python, jupyter notebook
- Features: imbalanced-learn, skikit-learn

## Results
### Oversampling Models
- Random Oversampling Model: 
Involves randomly selecting examples from the minority class, with replacement, and adding them to the training dataset. The classified records are equal to 51366 records to both low risk and high risk.
Accurate Score: 66%
High Risk Precision: 1%
Recall: 71%
<img src="images/Random Oversampling.PNG">

- SMOTE Oversampling Model:
Increases the size of the minority class by creating new values based on the value of the closest neighbors to the minority class instead of random selection. The classified records are finally equal with 51366 records to both low risk and high risk.
Accurate Score: 66%
High Risk Precision: 1%
Recall: 63%
<img src="images/SMOTE Oversampling.PNG">

### Undersampling Model
- ClusterCentroids Model:
Identifies clusters of the majority class to generate synthetic data points that are representative of the clusters. The model classified 246 records on each High Risk and Low Risk.
Accurate Score: 54%
High Risk Precision: 1%
Recall: 69%
<img src="images/Undersampling.PNG">

### Combination Sampling Model
Combines oversampling and undersampling. The model classified 51,359 records as High Risk and 46,660 records as Low Risk.
Accurate Score: 62%
High Risk Precision: 1%
Recall: 65%
<img src="images/Combination Sampling.PNG">

### Ensemble Classifiers
- Balanced Random Forest Classifier
Two trees of the same size and equal size to the minority class are constructed to represent one for the majority class and one for the minority class.
Accurate Score: 79%
Precision: 3%
Recall: 70%
<img src="images/Ensemble BRFC.PNG">

- Easy Ensemble Classifier Model
A set of classifiers where individual decisions are combined to classify new examples.
Accurate Score: 93%
Precision: 9%
Recall: 92%
<img src="images/Ensemble EEAC.PNG">

## Summary

In this analysis, since false negative (predicted high risk however actual is low risk) is less concern, the recall metric is more important than the precision metric. Comparing the resampling vs. ensemble classifier models, resampling models don't produce enough accurate results, the recall rates are all around 60-70%. Thus we will not recommend using resampling models.
Conversely, the Ensemble model, especially Easy Ensemble Classifier Model, generates the highest accurate score with the highest recall rate of 92%. The easy Ensemble Classifier Model would be the best fit model for this credit risk dataset.
