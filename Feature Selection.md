# Techniques
* Univariate Selection
    * SelectKBest from sklearn
    * Uses a **univariate** statistical test for features to select **k** best features.
    * Takes in the scoring function and k-value and returns score and p-values. 
    * One such function is chi-squared. Note that it is only valied for **non-negative** features.
    * Scoring function list
        * For regression --> f_regression, mutual_info_regression.
        * For classification --> chi2, f_classif, mutual_info_classif
        * The methods based on F-test estimate the degreee of linear dependency between two random variables.
        * On the other hand, mutual information methods can capture any kind of statistical dependency, but being nonparametric, they require more samples for accurate estimation.