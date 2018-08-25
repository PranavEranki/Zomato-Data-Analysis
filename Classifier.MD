Here, in the classifier notebook, we create a classifier for predicting the aggregate rating based on the other columns from the cleaned data. 

We also create two mini classifiers just for some fun binary classification.

# Classifiers?
1. Classifier meant for predicting 'Has Table booking' based on the other features
2. Classifier meant for predicting 'Has Online delivery' based on the other features
3. MAIN - Classifier meant for predicting rating based on other features

# 1 (Table Booking)

1. Used a Gradient Boosting Classifier
2. Split X and Y w/ train test split
3. Fit and predicted on X and Y
4. Used a cm and accuracy matrix to get accuracy of classifier : 92.2 %


# 2 (Online Delivery)

1. Used a Gradient Boosting Classifier
2. Split X and Y w/ train test split
3. Fit and predicted on X and Y
4. Used a cm and accuracy matrix to get accuracy of classifier : 69.7 %


# 3 (MAIN)

1. First, we imported the modules and classifiers necessary
2. Then, we split the data into the X and Y
3. Next, to append all the classifiers to a big list
4. To test all these classifiers, we built a basic pipeline.
5. Then, we cross validated every classifier in our list through the pipeline
6. We found the best classifier, which was a GradientBoostingClassifier
7. Now, to improve my GBC classifier, I performed a course-to-fine GridSearch
    *  *'clf__loss' : ['deviance', 'exponential'],
    'clf__learning_rate': np.linspace(0.5, 1.5, 11),
    'clf__n_estimators' : [80,100,120,140,160,180,200]*
    * Then, *'clf__loss' : ['exponential'],
    'clf__learning_rate': np.linspace(0.1, 0.6, 11),
    'clf__n_estimators' : [80,100,120,140,160,180,200]*
    * Then, *'clf__loss' : ['exponential'],
    'clf__learning_rate': (np.linspace(0.01, 0.15, 15)),
    'clf__n_estimators' : [80,100,120,140,160,180,200, 220, 250, 300, 350]*
    * Finally, the fourth grid search: *'clf__loss' : ['exponential'],
    'clf__learning_rate': (np.linspace(0.05, 0.10, 15)),
    'clf__n_estimators' : [160,165, 170, 175, 180, 185, 190, 195, 200]*
8. This fourth search yielded a GBC classifier with an accuracy of ~70.7 % (not good, I know, but the best I could do with the data without using a neural network).
9. Then, I used an accuracy score on the final classifier to get a test accuracy of ~69.5%
10. Finally, I ran a classification report on the final classifier:
    * Precision : 68%
    * Recall : 70%
    * F1-Score : 68%

__Possible Improvements__ : 
* Use more grid searches(quite time-consuming)
* Use k cross validation, and not just a cross val score, for determining grid search and best classifiers (again, quite time-consuming)
* Use a neural network(might do)

