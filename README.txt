This is the README file supporting the assignment submission for Practical Application 3 (Module 17) for the Professional Certificate in ML and AI by UC Berkeley. 
Author: Akshat Kharaya 

Takeaways 
(A) Data
-- The data is imbalanced. Count of 'yes' is >35,000 while 'no' is approx. 5,000.
-- Decisions made: (1) Delete column default since all values are 'no' (so it is not useful); (2) Treat 'Unknown' itself as a class label. 
-- ColumnTransformer is used to treat the features. Categorical columns are One Hot Encoded.

(B) Modeling Results
-- The most important metric in this application is recall, i.e., what % of targets that subscribed to the bank term deposit the model predicted correctly. 
This is because it can help maximize the productivity of telephone marketers team employed by the organization by focusing their efforts on the customers that are likely to subscribe. 
-- While overall accuracy results are comparable across the 4 algorithms (see detailed results of GridSearchCV pasted below), the recall is highest for the decision tree model at 54%. 
Best parameters for Decision Tree are: {'classifier__criterion': 'gini', 'classifier__max_depth': 5, 'classifier__min_samples_leaf': 1, 'classifier__min_samples_split': 5}
-- Note that overall accuracy is a biased metric due to imbalanced nature of the dataset. 
-- Note: had to restrict the grid search parameters for SVM due to training time constraints.

(C) Findings
-- Use decision tree to classify the customers into yes/no for future campaigns. 
-- While using the model, it is critical to evaluate the similarity between the sample on which model was developed and the target population for future campaings. 


Link to Jupyter notebook: https://github.com/akshatkharaya/UCB_MLAI_Module17/blob/main/Module17_AkshatKharaya.ipynb

Detailed results (pasted from Jupyter notebook)
Tuning Logistic Regression...
Fitting 5 folds for each of 5 candidates, totalling 25 fits
Best parameters for Logistic Regression: {'classifier__C': 1}
Best cross-validation score for Logistic Regression: 0.9104
Test accuracy for Logistic Regression: 91.10%
Classification Report:
              precision    recall  f1-score   support

           0       0.93      0.97      0.95      7303
           1       0.67      0.42      0.52       935

    accuracy                           0.91      8238
   macro avg       0.80      0.70      0.74      8238
weighted avg       0.90      0.91      0.90      8238


Tuning K-Nearest Neighbors...
Fitting 5 folds for each of 10 candidates, totalling 50 fits
Best parameters for K-Nearest Neighbors: {'classifier__n_neighbors': 11, 'classifier__p': 1}
Best cross-validation score for K-Nearest Neighbors: 0.9090
Test accuracy for K-Nearest Neighbors: 90.76%
Classification Report:
              precision    recall  f1-score   support

           0       0.94      0.96      0.95      7303
           1       0.62      0.49      0.55       935

    accuracy                           0.91      8238
   macro avg       0.78      0.73      0.75      8238
weighted avg       0.90      0.91      0.90      8238


Tuning Decision Tree...
Fitting 5 folds for each of 90 candidates, totalling 450 fits
Best parameters for Decision Tree: {'classifier__criterion': 'gini', 'classifier__max_depth': 5, 'classifier__min_samples_leaf': 1, 'classifier__min_samples_split': 5}
Best cross-validation score for Decision Tree: 0.9135
Test accuracy for Decision Tree: 91.51%
Classification Report:
              precision    recall  f1-score   support

           0       0.94      0.96      0.95      7303
           1       0.65      0.54      0.59       935

    accuracy                           0.92      8238
   macro avg       0.80      0.75      0.77      8238
weighted avg       0.91      0.92      0.91      8238


Tuning SVM...
Fitting 5 folds for each of 3 candidates, totalling 15 fits
Best parameters for SVM: {'classifier__C': 0.1, 'classifier__kernel': 'linear'}
Best cross-validation score for SVM: 0.9007
Test accuracy for SVM: 89.49%
Classification Report:
              precision    recall  f1-score   support

           0       0.93      0.95      0.94      7303
           1       0.54      0.45      0.49       935

    accuracy                           0.89      8238
   macro avg       0.74      0.70      0.72      8238
weighted avg       0.89      0.89      0.89      8238



CITATION
Moro, S., Rita, P., & Cortez, P. (2014). Bank Marketing [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5K306.