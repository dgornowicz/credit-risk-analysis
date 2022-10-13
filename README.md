# Credit Risk Analysis

## Analysis Overview
In this project, we use Python to build and evaluate several machine learning models to predict credit risk.\
We adopted the following procedure:
- oversample the data using the **RandomOverSampler** and **SMOTE** algorithms.
- Undersample the data using the **ClusterCentroids** algorithm.
- Use a combinatorial approach of over- and undersampling using the **SMOTEENN** algorithm.
- Compare two machine learning models that reduce bias, **BalancedRandomForestClassifier** and **EasyEnsembleClassifier**.

## Resources
- Data Source: LoanStats_2019Q1.csv
- Software: Python, Conda, Jupyter Notebook

## Results (Balanced Accuracy Scores, Confusion Matrixes and Imbalanced Classification Reports)

### RandomOverSampler Model
<img width="371" alt="randomoversamp" src="https://user-images.githubusercontent.com/102050273/195712193-73edc928-94ec-4d13-93d7-b924ad9dc642.png">
</p>
The balanced accuracy score is 65.0%.<br>The high_risk precision is about 1% only with 62% sensitivity which makes a F1 of 2% only.<br>Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 68% and a f1 score 81%.
<br><br>

### SMOTE Model
<img width="365" alt="smote" src="https://user-images.githubusercontent.com/102050273/195712841-cd405ab6-8d29-4a9d-a88e-6dc3444c7bce.png">
</p>
The results are pretty similar to the previous model.<br>The balanced accuracy score is 64.4%.<br>The high_risk precision is about 1% only with 63% sensitivity which makes a F1 of 2% only.<br>Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 66% and a f1 score 79%.
<br><br>

### ClusterCentroids Model
<img width="367" alt="centerclust" src="https://user-images.githubusercontent.com/102050273/195713364-5ac2755d-56ef-4e9b-a05c-9749e984b3fe.png">
</p>
Here the balanced accuracy score is down to about 51.6%.<br>The high_risk precision is still 1% only with 63% sensitivity which makes a F1 of 1%.<br>Due to the high number of false positives, the low_risk sensitivity is only 40% and the f1 score is 57%.
<br><br>

### SMOTEENN Model
<img width="367" alt="smoteenn" src="https://user-images.githubusercontent.com/102050273/195713725-8f6d2f45-3b12-41bb-b815-e91a39fb5bb2.png">
</p>
The balanced accuracy score is about 62.4%.<br>The high_risk precision is still 1% only with 68% sensitivity which makes a F1 of only 2%.<br>Due to the high number of false positives, the low_risk sensitivity is 57% and the f1 score is 73%.
<br><br>

### BalancedRandomForestClassifier Model
<img width="375" alt="balrandomforest" src="https://user-images.githubusercontent.com/102050273/195714010-05fbeb1a-9070-43c5-aad7-388c2f25f5d9.png">
</p>
The balanced accuracy score improved to about 78.8%.<br>The high_risk precision is still low at 4% only with 67% sensitivity which makes a F1 of only 7%.<br>Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion and a f1 score of 95%.
<br><br>

### EasyEnsembleClassifier Model
<img width="365" alt="easyensembleadaboost" src="https://user-images.githubusercontent.com/102050273/195714217-625987a8-eba2-44c5-8b11-72d49186d432.png">
</p>
Now, the balanced accuracy score is high to about 92.5%.<br>The high_risk precision is still low at 7% only with 91% sensitivity which makes a F1 of only 14%.<br>Due to a lower number of false positives, the low_risk sensitivity is now 94% with 100% presicion and a f1 score of 97%.
<br><br>

## Summary
All the models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.\
The Ensemble models brought a lot more improvment specially on the sensitivity of the high risk credits.\
The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. On another hand, with a low precision, a lot of low risk credits are still falsely detected as high risk which would penalize the bank's credit strategy and infer on its revenue by missing those business opportunities.\
For those reasons I would not recommend the bank to use any of these models to predict credit risk.
