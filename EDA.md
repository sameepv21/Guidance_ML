# Definition
* EDA refers to critical process of performing initial investigations on data so as to discover patterns, to spot anomalies, to test hypothesis and to check assumtions with the help of summary statistics and graphical representations.

# Techniques and Tools
* **Box Plots**
* **Histograms**
* **Bar Charts**
* Mutli-Vari Chart
* Run Chart
* Pareto Chart
* **Scatter Plot**
* Stem and Leaf plot
* **Violin Plots**
* **Dimension Reduction Techniques**
    * PCA (Principal Component Analysis)
    * PLS (Partial Least squares)
* **Heatmaps**
    * Correlation
* KDE (Kernel Density Estimates)

# Links
* [Introduction](https://towardsdatascience.com/exploratory-data-analysis-8fc1cb20fd15)

# Notes
* .describe() is used to gather statistics.
* Used to find whether there are outliers or not with the help of 75th percentile and max. If the difference is huge, this means that there are outliers.
* Boxplots shows distribution of quantitative data in a way that facilitates comparisions between variables.
    * These can give pretty good understanding about outliers.
    * Any observation that is 3*IQR (Inter Quartile Range) above the third quartile or below the first quatile can be considered as outliers.
* Then one can check for distributions. Either normal, right or left skewed.

# Visualization
* Use sns.heatmap() to see the NaN Values.
* Use sns.countplot() for categorical count.
* **Interpretations based on these graphs are important.**
* sns.distplot() to see the distribution.
* sns.boxplot() to check for outliers and help in filling null values based on mean.
* sns.pairplot() to plot scatter plots for each pair of qunatitative variable.