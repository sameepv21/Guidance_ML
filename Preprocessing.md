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