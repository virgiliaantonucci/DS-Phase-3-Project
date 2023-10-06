# Data Science Phase 3 Project
Virgilia Antonucci

# Overview/Business Data and Understanding
I have been tasked with evaluating students based on their academic performance and background to predict whether or not they will drop out of the university. I have been provided a dataset of approx. 4500 rows and 40 features. Each row is a student. The information provided for each student includes marital status, nationality, curriculum units for each semester, the amount of education achieved by each student’s parents, etc.

# Modeling
Here I trained a logistic regression model on the data. The evaluation metric we will be using as our primary evaluation method is the area under the curve. Here we see that the area is 0.95. I chose the auc because now that it's balanced, I wanted to look at the balance between false positive and true positive.
![logreg](https://github.com/virgiliaantonucci/DS-Phase-3-Project/blob/main/Phase%203%20Images/logreg1.png)

We can potentially expect a gain in performance because we are going from a linear model of logistic regression to the non-linear model of decision trees, therefore allowing for the model to incorporate interactions between different features. Once we plot the AUC, we see that the decision tree did not perform as well as the logistic regression.
![dectree](https://github.com/virgiliaantonucci/DS-Phase-3-Project/blob/main/Phase%203%20Images/dectree1.png)

Here, we are figuring out the best possible parameters for our decision tree. We can see using the AUC that this one performed better than the original decision tree, but not as good as the logistic regression.
![hyper](https://github.com/virgiliaantonucci/DS-Phase-3-Project/blob/main/Phase%203%20Images/hyper1.png)

Each decision tree in the forest is built on a random subset of the training data and considers a random subset of features for each split, providing a built-in form of regularization which helps mitigate the overfitting issue common in single decision trees. The AUC is highest here.
![random](https://github.com/virgiliaantonucci/DS-Phase-3-Project/blob/main/Phase%203%20Images/random1.png)

# Features
We are looking at the features from the Random Forest because it performed the best.
![features](https://github.com/virgiliaantonucci/DS-Phase-3-Project/blob/main/Phase%203%20Images/features.png)

# Evaluation
After exploring different models including Logistic Regression, Decision Tree, and Random Forest to predict student dropout, the Tuned Random Forest model performed the best on the test set. This is not too surprising considering that a random forest is an ensemble of decision trees. Furthermore, hyperparameter tuning was performed on the Random Forest model to find the optimal parameters that yield the best predictive performance. Grid Search was employed to exhaustively search through a specified parameter grid, evaluating all possible parameter combinations to find the optimal values for parameters like n_estimators, max_depth, min_samples_split, and min_samples_leaf. The performance of the model improved post-tuning. Finally, the model's feature importance revealed key features that influence student dropout, providing valuable insights that could be leveraged to develop interventions to improve student retention.

# Recommendations and Next Steps
If certain variables are not affectable, then the university should make sure to be aware of them and help the variables that are within their control. The feature importances show us that curriculum units, tuition, and mother’s occupation are the biggest predictors for whether or not someone will drop out. Going forward, the school should closely monitor these values and make sure these values are reported for each student.

Here is a histogram of the number of credits of students who dropped out and students who graduated. We want the plot to resemble those on the right. If they resemble the first image, call a tutor.
![dropout](https://github.com/virgiliaantonucci/DS-Phase-3-Project/blob/main/Phase%203%20Images/dropout.png)
![enrolled](https://github.com/virgiliaantonucci/DS-Phase-3-Project/blob/main/Phase%203%20Images/enrolled.png)

