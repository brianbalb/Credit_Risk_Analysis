# Credit_Risk_Analysis

# Project OVerview

In this project, we use Python to build and evaluate several machine learning models to predict credit risk.

We adopted the following procedure:

!. Oversample the data using the RandomOverSampler and SMOTE algorithms.
2. Undersample the data using the ClusterCentroids algorithm.
3. Use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm.
4. Compare two machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier.
5. Evaluate the performance of these models and make a recommendation on whether they should be used to predict credit risk.

## Resources
* Data Set: LoanStats_2019Q1.csv
* Python 3.7
* SciPy 1.6.2
* Scikit-learn 0.24.1
* imbalanced-learn 0.80

## Results

### Oversampling: Native Random OVersampling 

* Balanced Accurracy Score: 0.674
* High-Risk Precision: 0.01
* High-Risk Recall: 0.74

The balanced accuracy score is 65%.
The high_risk precision is about 1% only with 62% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 68%.

### Oversampling: SMOTE (Synthetic Minority Oversampling Technique)
 *Used to deal with unbalanced datasets*
 
* Balanced Accurracy Score: 0.662
* High-Risk Precision: 0.01
* High-Risk Recall: 0.63
 
The balanced accuracy score is 64%.
The high_risk precision is about 1% only with 63% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 66%.

### Combination Sampling: SMOTEENN

Balanced Accurracy Score: 0.644
High-Risk Precision: 0.01
High-Risk Recall: 0.72

The balanced accuracy score is about 62%.
The high_risk precision is still 1% only with 68% sensitivity which makes a F1 of only 2%.
Due to the high number of false positives, the low_risk sensitivity is 57%.

### Balanced Random Forest Classifers Model

* Balanced Accurracy Score: 0.788
* High-Risk Precision: 0.03
* High-Risk Recall: 0.70

The balanced accuracy score improved to about 79%.
The high_risk precision is still low at 4% only with 67% sensitivity which makes a F1 of only 7%.
Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion.

### Easy Ensemble AdaBoost Classifier

* Balanced Accurracy Score: 0.931
* High-Risk Precision: 0.09
* High-Risk Recall: 0.92
* 
The balanced accuracy score is high to about 93%.
The high_risk precision is still low at 7% only with 91% sensitivity which makes a F1 of only 14%.
Due to a lower number of false positives, the low_risk sensitivity is now 94% with 100% presicion.

## Summary 

All the models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.

The Ensemble models brought a lot more improvment specially on the sensitivity of the high risk credits.

The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. However, with a low precision, a lot of low risk credits are still falsely detected as high risk which would penalize the bank's credit strategy and infer on its revenue by missing those business opportunities.

If one of the models in this project must be used to predict credit risk, it is recommended to use Easy Ensemble AdaBoost Classifier.

1. EasyEnsemble AdaBoost Classifier has the highest Balanced Accuracy Score out of all of the techniques employed in this project. 

2. EasyEnsemble also has the highest precision, recall, and F1 scores as proven by the imbalanced classification reports printed for each model.

*CATION: If given the option, it is not suggested to use any of these models. Although the EasyEnsemble model performed the best in this group, its precision for high-risk data points is still only 0.09. This indicates that very few of positive predictions are true (False Positives).*

## Suggestions
For the reasons stated above I would not recommend the bank to use any of these models to predict credit risk.

Further research and development are required to create a more robust model that can predict credit risk.
