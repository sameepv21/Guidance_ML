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

# Feature Engineering for multimodal distributions
* Note that tree based models are able to handle multimodal distributions without transforming.
* Thus, to set a baseline model, use LGBM.
* We can use a [mixture model](https://en.wikipedia.org/wiki/Mixture_model) for this. 
* It is a probabilistic model for representing the presence of subpopulations within an overall population, without requiring that an observed data set should identify the sub population to which an individual observation belongs.
* Gaussian Mixture Modelling (GMM)
    * Unsupervised Learning Algorithm
    ```python
    from sklearn.mixture import GaussianMixture
    gmm = GaussianMixture(n_components=2, random_state=42)
    gmm.fit(train_df.target.values.reshape(-1, 1))
    train_df['target_class'] = gmm.predict(train_df.target.values.reshape(-1, 1))
    ```
* Deep Feature Synthesis

# Handling Multimodal Distributions
* Gaussian Mixture Model
    * 