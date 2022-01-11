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
* For classification problem, use different colors for different classes.
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

# Preprocessing the data
* The formal definition of pipeline is that it is a sequence of data processing components.
* This is one of the most important step in to prepare the data to be fit by a model.
* This step includes deadling with missing values, standardizing, scaling/encoding, feature extraction and model fitting.
* Check for missing values using df.isna().sum() function.
* Then to handle the missing values you can use one of the following.
    * Filling the missing value with statistical variables (eg mean for numerical data and mode for categorical data)
    * Drop the column.
    * Drop the missing records.
* Scikit-learn's pipelines allow us to perform the preprocessing steps in one step.
* Some usefull scikit learn's classes for preprocessing.
    * Handling numerical Inputs
        * SimpleImputer from sklearn.impute
        * Imputer from sklearn.preprocessing
        * This handles the missing values for numeriacal data.
        * Make sure that you feed only those columns that have numerical data type.
        * One thing to make sure is that imputer returns a numpy array instead of pandas dataframe and hence we need to convert it back into the dataframe.
    * To handle categorical attributes
        * Use LabelEncoder class.
        * Maps a number to each class.
        * Classes can be viewed with classes_ attribute.
        * Issue is that ML algo. will assume that two nearby values are more similar than two distant values.
        * Use OneHotEncoder class.
        * Creates one binary attribute per category.
        * Returns sparse matrix of Scipy instead of numpy array.
        * convert using toarray() function.
        * LabelBinarizer
        * Apply both the above in one shot.
        * Returns a dense numpy array.
    * Can create your own transforms also.
    * Use Base classes like BaseEstimator, TransforemerMixin class for sklearn.base.
    * Feature Scaling
        * All the features must be of the same scale otherwise ML algorithms will not work efficiently.
        * Min-max scaling
        * Values are shifted and rescaled so that they end up ranging from 0 to 1.
        * (xi - min(x))/(max(x) - min(x))
        * Use scikitlearn's MinMaxScaler class.
        * feature_range hyperparameter lets you change the range if you dont want 0-1.
        * Standardization using StandardScaler class
        * (xi - mean(x))/var(x).
        * This makes the data std normal distribution i.e mean is 0 and std dev = 1.
    * scikitlearn's FeatureUnion class.
    * Join multiple transformations into a single pipeline.


# GPUs
* A GPU (Graphics Processing Unit) is a specialized processor with dedicated memory that conventionally perform floating point operations required for rendering graphics.
* It is a single-chip processor used for extensive graphical and mathematical computations which frees up CPU cycles for other jobs.
* The main difference between GPUs and CPUs is that GPUs devote proportionally more transistors to ALU and fewer to caches and flow control as compared to CPUs.
* Another difference is in the way of working. CPUs process the task sequencially whereas GPUs perform the task parallelly.
* [See this](https://www.youtube.com/watch?v=-P28LKWTzrI)
> Why to use GPUs?
* They have larger number of cores, which alllows for better computation of multiple parallel processes.
> When to use GPUs?
* Memory Bandwidth (Large)
* Dataset Size (Large)
* Optimization (No)
> Which libraries in python support GPUs?
* [CuPy](https://cupy.dev/) --> Numpy on the GPU
* Jax --> Numpy on the GPU
* [RAPIDS cuDF](https://docs.rapids.ai/api/cudf/nightly/) --> Pandas on the GPU
* [RAPIDS cuML](https://docs.rapids.ai/api/cuml/nightly/) --> Scikit learn on the GPU
* [RAPIDS cuGraph](https://docs.rapids.ai/api/cugraph/stable/) --> Graphs on the GPU
* [PyTorch](https://pytorch.org/docs/stable/index.html) --> Tensors on the GPU
* [Keras](https://keras.io/) and [TensorFlow](https://www.tensorflow.org/api_docs)
> A good [kaggle notebook](https://www.kaggle.com/harishvutukuri/introduction-to-rapids) for learning GPU accelarated RAPIDS library.

> Look for these terms, [Apache Arrow](https://arrow.apache.org/) and GoAi.

> **[Seaboarn Docs/Tutorial](https://seaborn.pydata.org/tutorial/distributions.html)**


# Good Tutorials on Kaggle
* [Seaborn](https://www.kaggle.com/learn/data-visualization)
* [Feature Engineering](https://www.kaggle.com/learn/feature-engineering)

# Some important Kaggle Notebooks
* [GPU Accelarated RAPIDS Library](https://www.kaggle.com/harishvutukuri/introduction-to-rapids)
* [XGBoost](https://www.kaggle.com/prashant111/xgboost-k-fold-cv-feature-importance)
* [Tuning hyperparameter XGBoost](https://www.kaggle.com/prashant111/a-guide-on-xgboost-hyperparameters-tuning)
* [Guidance (House Price Prediction)](https://www.kaggle.com/pmarcelino/comprehensive-data-exploration-with-python/notebook)
* [Full Guide on Data Science]()

# Feature Engineering
* It is the process of selecting, manipulating and transforming raw data into features that can be used in supervised learning.
* It is the act of converting raw observations into desired features using statistical or machine learning approaches.
* It is a technique that levrages data to create new variables that aren't in the training set.
* Visualize this new feature that has been created to gain some useful insights.
* Processes of Feature Engineering
    * Feature Creation
        * Creating features involves creating new variables which will be most helpful for our model.
        * This can be either adding to removing some features.
    * Transformations
        * It is simply a function that transforms features from one representation to another.
        * Goal is to plot and visualize the data and if something is not adding up, reduce the number of features used.
    * Feature Extraction
        * Process of extracting features from a dataset to identify information.
        * Without distorting the original relationships or significant information, this compresses the amount of data into manageable quantities.
    * EDA (Exploratory Data Analysis)
        * It is a powerful and simple tool that can be used to improve your understanding of your data by exploring its properties.
        * Often applied when the goal is to create new hypothesis or find patterns in the data.
    * Benchmark
        * Helps in measuring and comparing the performance between different machine learning models and same model with different methods etc.
* Techinques in Feature Engineering
    * Imputation
        * It is a technique to handle missing values.
        * Numerical and Categorical Imputation.
    * Handling Outliers
        * Technique that removes outliers from the dataset.
        * Methods
            * Removal
            * Replacing Values
            * Capping --> Using an arbitary value of a value from a variable distribution to replace the maximum and minimum values.
            * Discretization --> Process of converting continuous variables, models and functions to discrete ones.
                * Accomplished by constructing a series of continuous intervals (or bins) that span the range of our desired variable/model/function.
    * Log Tansform
        * Used to turn skewed distribution into a normal or less-skewed distribution.
        * Take the log of the values in a column and utilise those values as the volumn in this transform.
    * One-hot encoding
    * Scaling or **Feature Scaling**
        * **This is one of the most important steps and must always be performed.**
    * Normalization and Standardization
* Tools for feature engineering
    * FeatureTools
        * Open source framework to perform automated feature engineering.
        * Automatically construct significant features.
    * AutoFeat
        * Perform Linear Prediction Models with automated feature engineering and selection.
        * Allows to select the units of the input variables in order to avaoid the construction of physically nonsensical features.
    * TsFresh
        * Includes methods for assessing the explanatory power and significance of such traits in regression and classification tasks.
    * OneBM
        * Interacts directly with a database's raw tables.
        * Slowly joins the tables, taking different paths on the relational tree.
        * Recognises simple and complicated data types in the join results and applied pre-defined feature engineering approaches to the supplied types.
    * ExploreKit
        * Identifies common operators to alter each feature independently or combine multiple of them.
* > [**A must Read Feature Engineering Blog**](https://towardsdatascience.com/feature-engineering-for-machine-learning-3a5e293a5114#3abe)


# How to approach to use feature engineering?
* Use feature utility metric which is any function measuring associations between a feature and the target.
* These include mutual information and correlation.
* Advantage of mutual information is that it can detect any kind of relationship while correlation only detects linear relationships.
* Mutual Information
    * Describles relationships in terms of uncertainty.
    * It is a measure of the extent to which knowledge of one quantity reduces uncertainity about the other.
    * This uncertainty is measured from "entropy".
    * Mutual Information can be understood by how many questions you expect the feature to answer about the target.
    * If a feature reduces the uncertainty, it is fairly useful.
    * When MI is 0, the quantities are independent.
    * MI is a logarithmic quantity.
    * **It is a univariate metric.** This means that it can't detect interations between features.
        * This means that if a feature is very infomration when interacting with other features, but not so information all alone, then MI score will be less but the feature is still important.
    * The actual usefulness of the feature depends on the model you use it with. A feature is only useful to the extent that its relationship with the target is one your model can learn.

# Seaborn
* Useful functions
    * lineplot(data=*DATA*, label=*LABEL*)
    * barplot(x=*INDEX*, y=*DATA ON Y-AXIS*)
    * heatmap(data=*DATA*, annot=True)
        * annot=True displays the number also
    * scatterplot(x=*DATA*, y=*DATA*, (op) hue=*DATA*)
    * regplot(**Same as scatter plot except hue parameter**)
        * Also plots the regression line and hue is to add color coding based on that parameter
    * lmplot(**Same as scatter plot with hue parameter**)
        * Plot regression line along with color codes
    * swarmplot(x=*DATA*, y=*DATA*)
        * Used specifically for plotting categorical features on one of the axis
    * distplot/histplot/displot(a=*DATA*, kde=False, label=*LABEL*)
        * kde means another curve that follows histogram (smoothened histogram)
        * Label is used to ensure color coding if multiple histograms are plotted and hence is optional
    * kdeplot(data=*DATA*, shade=True, label=*LABEL*)
        * Label has same functionality as above.
    * jointplot(x=*DATA*, y=*DATA*, kind="kde) 
        * Plots joint kde or 2D kde
* Styling
    * sns.set_style(*STYLING_METHOD*)
        * 5 Different methods include darkgrid, whitegrid, dark, white, ticks

# ISLR Notes

## Statistical Learning
* Trade off between flexibility and interpretability.
    * Less flexible models have higher interpretability and vice versa.
* Parametric Vs Non Parametric
    * In parametric approach, we assume the same of the function that we need to estimate and then use the performance measurement to evaluate the function.
    * Non-parametric approach does not assume anything about the shape of the function.
* Supervised Vs Unsupervised
    * Supervised means that for each observation of the predictor measurement there is an associated response and vice versa.
    * Cluster analysis is one of the techniques used in unsupervised learning
        * Goal is to ascertain on the baseis of X (vector) whether the obs. will fall into relatively distinct groups.
    * Regression Vs Classification
        * Those problems in which we response variable is **quantitative** is called **regression** problem and vice versa.
        