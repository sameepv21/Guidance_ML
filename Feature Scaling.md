# Feature Scaling
* It is a method to normalize the rande of independent variables or features of data.
* It brings the range of features to comparable values.
* Otherwise, there is a high possibility that the larger features or records will influence the model more than the smaller values.
* Thus, in a way, it reduces the skewness of the distribution of particular feature.

# Techniques of Scaling
* Min Max Scaler - Normailzation
    * It brings the value of each and every record in the feature to range between 0 and 1.
    * xnew = (x - min(x)) / (max(x) - min(x))
    * Should be preferred when data is neither distorted (i.e skewed) nor normally distributed.
* Standard Scaler - Standardization
    * It standardizes the feature.
    * This means that after transformation, the feature will be following Standard Normal Distribution i.e its mean will be 0 and variance will be 1.
    * xnew = (x - mean)/stddev(x)
    * Note that for standardization, the feature must obey at least normal distribution.
* Robust Scaler
    * More suitable for dataset with skewed distributions and outliers as it used median and IQR to transform the data.
    * xnew = (x - median)/IQR.