# Linear Model Selection And Regularization
* Alternatives to least squares method
    * Subset Selection --> Identifying a subset of the p predictors that we believe to be related to the response.
    * Shrinkage --> Fitting a model involving all p predictors but the estimated coefficients are shrunken towards zero relative to the least squares method.
    * Dimentionality Reduction --> Projectivg the p predictors into an M-dimensional subspace where M < p.
* Subset Selection
    * Best Subset selection
        * Fit a separate least squares regression for each possible combination of the p predictors.
        * Then select the model that gives the best performance.
        * This means we fit 2^p linear models.
        * Algorithm
            * ![Algorithm_Best_Subset_Selection](../assets/images/Algorithm_Best_Subset_Selection.png)
        * According to this algorithm, the RSS decreases monotonically when number of features are increased and hence we need to select the features carefully otherwise we may end up involving all the features.
        * Hence, in step3 we use cross validation so that it gives RSS or R2 on **test** set.
        * In case of logistic regression, we use deviance instead of RSS.
        * The deviance is negative two times the maximized log-likelihood. This means that smaller the deviance, the better the fit.
    * Forward Stepwise Selection
        * Begin with a model containing no predictors.
        * Then, add predictors to the model, one at a time until all predictors are in the model.
        * In each step, the feature that gives the greatest additional improvement to the fit is added to the model.
        * This greatly reduces the number of models to be fitted instead of 2^p.
        * Algorithm
            * ![Algorithm_Forward_Stepwise_Selection](../assets/images/Algorithm_Forward_Stepwise_Selection.png)
        * Computational advantage over best subset selection.
        * Does not take into account the interaction between the two features.
        * Can be applied when n < p.
    * Backward Stepwise Selection
        * Begins with the full least squares model containing all p predictors and then iteratively removes the least useful predictor.
        * Algorithm
            * ![Algorithm_Backward_Stepwise_Selection](../assets/images/Algorithm_Backward_Stepwise_Selection.png)
        * Requires n >> p.
    * **Choosing the optimal model**
        * We are trying to minimize the training set RSS and R2. However, we want to minimize the test set RSS and R2.
        * Thus, we need to estimate test set scores.
        * Some of these are Cp, Akaike Information Criterion (AIC), Bayesian Information Criterion (BIC) and adjusted R2.
        * Cp statistic adds a penalty to the training RSS in order to adjust for the fact that training error underestimates test error.
        * Penalty increases as number of predictors increases.
        * Choose the model with lowest Cp value.
        * AIC is defined for a large class of models fit by maximum likelihood.
        * Cp and AIC are proportional to each others.
        * BIC is similar to Cp but with Bayesian POV.
        * It used logarithm and hence it places much more heavier penalty on models with many variables and hence results in the selection of smaller models than Cp.
        * Adjusted R2 is another popular approach for selecting among a set of models.
        * Adjusted R2 is high means good model.
        * It means that once all of the correct vairbales have been included in the model, adding noise variables will lead to only a very small increase.
        * Cross validation methods are really better than these methods because it directly estimates the test error rate.
        * However, if we repeat the validation set approach using a different set, then test error rate might change.
        * Thus, select a model using **one standard error rule**.
            * We first calculate the standard error of the estimated test mse for each model size and then select the smallest model for which the estimated test error is within one standard error of the lowest point on the curve.
* Shrinkage Methods
    * Ridge Regression
        * Here, the coefficients are estimated by minimizing RSS + lambda*(sum(coefs^2)).
        * Lambda is called the tuning parameter and is always >= 0.
        * Thus, it adds a shrinkage penalty which is small when coefs are close to zero and so it essentially has an effect of shrinking the estimates of coefs towards zero.
        * When lambda is 0, no effect of penalty terms and coefs be same as that of Linear Regression.
        * When, lambda is infinity, coefs will shrink to 0.
        * One thing to note here is that the standard least squares coefficient estimates are scale equivariant.
        * This means that multipyling Xj by a constant c simply leads to a scaling of the least squared coeff estimates by a factor of 1/c.
        * However, in ridge regression coeff estimates can change substantially when multiplying a given predictor by a constant.
        * Therefore, it would be better to standardize the parameters before applying ridge regression.
        * Ridge Regression is an improvement over Least squared because of bias variance trade off.
        * **Follows l2 norm.**
    * Lasso Regression
        * Ridge Regression may make the coeffs very small but unless lamda is infinity, it will not make it completely zero.
        * This means that ridge regression will consider every feature which might not be desired.
        * Lasso Regression overcomes this problem and the difference here is that it follows **l1 norm.**
        * RSS + lambda(sum(coefs))
        * lambda >= 0 is a tuning parameter.
        * Similar to best subset selection, the lasso performs variable selection.
* Dimension Reduction
    * Dimension reduction techniques transform the predictors and then fit a least squared model using the transformed variables.
    * This approach reduces the problem of estimating the p + 1 coefficients to the simpler M + 1 coefficients where M < p.
    * It constrains the estimated betaj coefficients.
    * Two steps in DR
        * Transformed predictors are obtained.
        * Model is fit on these transformed prefictors.
    * PCA (Principal Component Analysis)
        * Technique for DR with unsupervised.
        * The first principal component (PC) direction fot he data is that along withch the observations vary the most.
        * This is used to ensure that the maximum data is restored and minimum is lost.
        * Thus, we project the data points on the pricipal component which simply means finding a location on the line which is closest to the point.
        * Thus, the first PC defines the line that is as close as possible to the data.
        * Values of the principal component means single number summaries of the joint predictors.
        * In general, we can construct upto "p" principal components.
        * Second PC is a linear combination of the variables that is uncorrelated with first PC and has largest variance sibject to this constraint.
        * This condition equals the line orthogonal to the first PC.
    * PCR (Principal Component Regression)
        * This approach involves constructing the first M PC and then using these as predictors in a linear regression model that is fit using least squared.
        * Key is that small number of PC can cover most variability in data.
        * We **assume** that the directions in which features show the most variantions are the directions that are associated with Y.
        * Note that as more PCs are used in the model, the bias decreases but the variance increases.
        * **It is not a feature selection method.**
        * The number of PCs is generally chose by cross validation.
        * **Note that while performing PCR, standardize each predictors prior to generating PCs.**
        * PCR has a drawback that there is no garuntee that the directions that best explain the predictors will also be the best directions to use for predicting the response.
    * PLS (Partial Least Squares)
        * Technique of DR in supervised manner.
        * PLS identifies new features in a supervised way.
        * PLS approach attempts to find directions that help explain both the response and the predictors.
        * PLS computes the firstion direction by setting each PC equal to coeff from the simple LR.
        * This coeff is proportional to the correlation betweeb Y and Xj.
        * Hence highest weight is put on the variables that are most stringly related to the response.
        * To identify the second PLS direction, we first adjust each of the variables for Z1 by regressing each variables on Z1 and taking residuals.
        * These residuals can be interpreted as the remaining information that has not been explained by the first PLS direction.
        * Compute 2nd direction using this orthogonalized data exactly like in first direction.
* In high dimensional data the bias-variance trade off and danger of overfitting play a very important role.
* Regression in high dimensional data
    * Regularization or shrinkage plays a key role.
    * Appropriate tuning parameter selection is crucial for good predictive performance.
    * Test error tends to increase as dimensionality of the problem increases unless additional features are truly associated with the response.
        * This is known as curse of dimensionality.
* [Kaggle Notebook](https://www.kaggle.com/sameepvani/chapter5-islr-linearmodelandregularizationmethods)