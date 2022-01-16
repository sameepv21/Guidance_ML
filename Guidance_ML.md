# Pipeline for ML
* Data Collection
* Feature Engineering
* EDA (Exploratory Data Analysis)
* Model Creation
* Hyperparameter Tuning
* Model Deployment

# How to approach an ML Problem?
* Start with understanding the problem statement.
    * This includes having knowledge about the type of problem.
    * This includes supervised or unsupervised, regression or classification etc.
    * How was the training data collected? (Was it produced and if so how? or is it real world based)
* Once done that, get the data.
* Next explore the data
    * use descibe() function to find some useful statistics of the data.
    * Plot the data on a graph and get an intuitive idea about the model that definitely can't fit.
    * Plot the histogram (or distplot() in sns) so that you know what the particular feature looks like.
    * Then plot a heatmap (sns) for identifying the null values if any
* Then check whether the assumptions of each model are satisfied by the data or not? If not satisfied, reject the model completely.
* List of different regression models
    * Linear Regression
    * Logistic Regression
    * Polynomial Regression
    * Ridge Regression
    * Lasso Regression
    * Elastic Net Regression
    * Bayesian Linear Regression
    * Poisson Regression
    * Pricipal Component Regression
    * Partial Least Regression
    * Support Vector Regression
    * Decision Tree Regression
    * Random Forest Regression
    * KNN Regression
    * SGD Regression (Stochastic Gradient Descent)
    * LGBM (Light Gradient Boosting Machine)
    * AdaBoost Regression
    * XGB (Extreme Gradient Boost)
* List of different classification model
    * Logistic Regression
    * LDA (Linear Discrminant Analysis)
    * QDA (Quadratic Discriminant Analysis)
    * Naive Bayes Classifier
    * Poisson Classifier
    * KNN Classifier
    * Decision Tree Classifier
    * Random Forest Classifier
    * SGD Classifier (Stochastic Gradient Descent)
    * Principal Component Classifier
* Then select models
    * There will always be some models which you can reject if the assumptions are properly checked.
    * Based on that, you have certain models that might be the one that makes the final predictions on the test dataset.
* Then Split the training set into training and validation set.
* Fit the chosen model(s) using the splitted training set.
* Then calculate the actual test error rate using the validation set.
* Various cross-validation approaches are as follows
    * Validation Set Approach
    * Leave One Out CV (LOOCV)
    * k-fold cross validation
    * Bootstrap

> How to select a model?
* Firstly examine the data very closely.
* For example, use correlation to identify whether linear regression model will be suited or not. If correlation between the predictors is high and between features and target is low, then most likely linear regression model will not be a good fit.
* Another approach is to use cross validation.
* In cross validation we split the training set into training and test set.
* Then we fit the model on training set and calculate the effectiveness of the model using predictions on test data.
* Various Cross validation approaches listed above.
* **Note that the cross validation method is used for model selection and not for making actual predictions.**
* Once the model has been chosen, use the best model and train it on the whole training dataset.
* Then use it to predict the output on really unseen test data.

> Which are the graphs that you can plot to get some insights?
* Scatter plot between response variable and each individual feature.
* Linear regression line along with the training dataset that is used to make predictions on the test dataset.
* Fitted values vs residuals
* **Residual Plots** --> Residuals vs predictors (xi)
* For classification problem, use different colors for different classes.
* Box plot of performance (Test error rates) of different models that we create.
* Plot a heatmap from seaborn library.
    * Could be for plotting correlation matrix.
    * Could be for identifying null values in the given training dataset.
    * Could be for plotting the confusion matrix.
* Line plot between each individual predictor and response variable.
* 'n' Nomral Density functions for classification problems on same graph where n is the number of classes.
* Along with it, if possible then draw different decision boundaries like Bayes, LDA etc.
* Plot error rate vs threshold for classification problem.
* Plot ROC Curves
* Box plot which compares test error rates for each of the linear scenarios (KNN, LDA. QDA, Logistic, Bayes etc)
* For classification problem plot density estimates for each class.
* If polynomial regression is used, then run the code for multiple degrees of the polynomial and note each mean squared test error rate and plot the MSE vs Degree of polynomial graph.
* If different random splits for validation are used, plot all the graphs (Ref: Pg 209 ISLR PDF)
* Plot MSE vs flexibility graph if possible.
* Same for classification problems
* If using boostrap method, plot a histogram of the estimates of alpha.
* Can plot number of predictors vs RSS, R2, Cp, BIC, Adjusted R2, Validation set Error and CV-Set Error for both training and validation/test dataset.
* If using ridge or lasso regression, plot Standard Coef vs alpha/lambda (basically tuning parameter).
* Plot MSE vs tuning parameter if using ridge or lasso regression.
* CV Error vs tuning parameter for ridge or lasso regression.
* MSE vs number of components (in PCA).
* MSE vs shrinkage factor from ridge or lasso regression.
* Standardized Coef vs Number of components (in PCA/PCR).
* CV - MSE vs Number of components (in PCA/PCR).
* Plot splines (can be of any degree)
* MSE vs Degree of freedom for natural and cubic spline.