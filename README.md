# Credit_Risk_Analysis

## Overview
The purpose of this analysis is to utilize Machine Learning and analyze a credit card dataset to determine high risk and low risk loans. In order to see what model would work best with this dataset, below are four different sampling methods of data sampling for low risk to high risk loans. Totalling in six tests, I ran a logical regression test on each sampling method. Then, I ran a RandomForest classifier and EasyEnsemble classifier tests.

### Results
Oversampling Methods
Each of these methods tried to add towards the minority class, high-risk, in order to make the test fairer.

#### Naive Random Oversampling
![](oversample_longregress.PNG)

Accuracy score: 66%
True Positives: 78
True Negatives: 9,283
False Positives: 7,821
False Negatives: 23

This test performed average with low precision on high-risk loans and perfect precision on low-risk loans. Recall on both classes were middling with 0.77 low-risk and 0.54 high-risk. Its true positives meaning it predicted high-risk on actual high-risk loans ranked about second out of the tests however the amount of false positives (Predicting high-risk, actually low-risk) is pretty high.

#### Synthetic Minority Oversampling Technique (SMOTE)
![](smote_logregress.PNG)

Accuracy score: 66%
True Positives: 64
True Negatives: 11,684
False Positives: 5,420
False Negatives: 37

This test performed similarly to Random Oversampling with low precision on high-risk loans and perfect precision on low-risk loans. Recall on both classes were closer with 0.68 low-risk and 0.63 high-risk. This test didn't really excell at any particular result and actually performed worse than Random Oversampling with less true positives and more false negatives (predicting low, actually high).

#### Undersampling Methods
This test attempted to take away from the majority class, low-risk, instead.

#### Cluster Centroid Undersampling
![](cluster.PNG)

Accuracy score: 54%
True Positives: 68
True Negatives: 7,105
False Positives: 9,999
False Negatives: 33

This test has the lowest level of performance. Low precision on high-risk loans and perfect precision on low-risk loans is average amongst each test. The recall on both classes are closer to each other with 0.42 low-risk and 0.67 high-risk. This test performed lowest at determining low risk loans and had many false positives. It would be hard to recommend this sampling method over the others evaluated.

### Combination Method
This test utilized both oversampling and undersampling.

#### Synthetic Minority Oversampling Technique Edited Nearest Neighbors (SMOTEENN)
smoteenn_logregress.PNG

Accuracy score: 65%
True Positives: 73
True Negatives: 9,789
False Positives: 7,315
False Negatives: 28

This test performed average with low precision on high-risk loans and perfect precision on low-risk loans. The recall on both classes were similar to random oversampling with 0.57 low-risk and 0.72 high-risk. This test did not perform as well as Random Oversampling.

#### Random Forest Classifier
randomforest.PNG

Accuracy score: 68%
True Positives: 36
True Negatives: 17,099
False Positives: 5
False Negatives: 65

This test performed above average with high precision (0.88) on high-risk loans and complete precision on low-risk loans. It also had complete recall on low-risk but significantly lower recall on high-risk 0.36. If we wanted to focus on reducing False Positives and increasing predictions on low-risk loans, this test would be a good recommendation. It is the worst at determining high risk loans however.

top5_features.PNG

Another benefit of the random forest classifier is seeing how much weight each feature of our dataset contributes to its predictions. This snapshot showcases the top 5 most considered features.

#### Easy Ensemble Classifier
eec.PNG

Accuracy score: 93%
True Positives: 93
True Negatives: 16,166
False Positives:938
False Negatives: 8

This test performed the best overall with 93% accuracy and the typical low precision on high-risk loans and complete precision on low-risk loans. It had near-perfect recall on low-risk 0.95 and on high-risk 0.92. This model performed the most effectively in each category of its confusion matrix. Even though false positives were ones of its weaker points, it still beat out most of the other methods.

### Summary
all_tests.PNG

In the image above shows the key statistics for each test and color coded them accordingly. The worse performing statistics would highlight closer to red while the ones closer to green would be the best. I recommend the Easy Ensemble Classifier model, which best predicts high-risk loans.

Although the EEC performed the best at predicting high-risk loans and second best at predicting low-risk loans. It displayed low false negatives which is great for the low-risk business. The higher recall or sensitivity does lead to higher false positives, however this consequence is easier to overlook than having higher false negatives. I personally think there should be more considered in high-risk loan assesments. This reasoning is why I would recommend Random Forest to the business as a more flexible on loaners overall. 
