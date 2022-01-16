# Simple Linear Regression
* Introduction
    * beta0 and beta1 are intercept and slope respectively in terms of linear model.
    * Can also be understood as expected value of Y when X=0 is beta0 and average increase in Y associeated with a one unit increase in X is beta1.
    * Together called as coefficients or paramters.
    * Interested in estimating yhat (predicted value).
* Estimating the coefficients
    * Most common approach involves minimizing the least squared criterion.
    * Residual e = y - yhat.
    * RSS = sum(e)
* Assessing the **accuracy of coefficient estimates**
    * Error term is generally generated from a normal distribution with mean zero.
    * Standard Error tells us the amount that this estimate "mean" differes from the actual value.
    * Estimate of **sigma = SD(Error term)** is known as **RSE** = sqrt(RSS / (n-2))
    * Std Error can be used to compute confidence intervals.
    * 95% confidence interval is defined as a range of values such that with 95% probability, the range will contain the true unkown value of the parameter.
    * Std Errors can be used to perform hypothesis tests on the coefficients.
    * Most common is null hypothesis.
    * To infer about null hypothesis, we compute t-statistics which measures the number of std dev that beta1 is away from 0.
    * Prob. of observing any number >= mod(t) assuming null hypothesis is true is called p-value.
    * It can be interpreted as follow, small p-value indicates that it is unlikely to observe such a substantial association between the predictor and response and hence there is an association between the predictor and response.
* Assessing the **accuracy of model**
    * Use RSE and R2.
    * RSE is estimate of sigma = SD(Error Term).
    * RSE is measure of lack of fit. If RSE is small, model fits the data well and vice versa.
    * R2 takes the form of proportion, the proportion of variance.
    * Ranges from [0, 1].
    * R2 = 1 - (RSS / TSS)
    * TSS = sum(yhat - mean(y)^2) = Total sum of squares. It measures total variance in Y.
    * RSS measures the amount of variability that is left unexplained after performing the regression.
    * R2 close to 1 indicates that a large proportion of variability in the response is explained by regression and hence is a good model and vice versa.
* Multiple Linear Regression
    * Y = beta0 + beta1*X1 + ...
    * betaj can be interpreted as the average effect on Y of a one unit increase in Xj, holding all other predictors fixed.
* Estimating the regression coefficients
    * F-statistics --> F = (TSS - RSS)/p/RSS/(n - p -1)
    * E{RSS / (n-p-1)} = sigma^2. Iff linear model assumption is correct.
    * When there is no relationship between the response and predictors, one would expect the F-statistic to take on the value close to 1 and if there is a relationship then value of F-statistic will be > 1.
    * If we use individual t-stats and associated p-values in order to decide whether or not there is an association between the variables and the reponse then there is a high chance that we will incorrectly conclude the relationship.
    * F-stat does not suffer from this because it adjusts for the number of predictors.
* The task of determining which predictors are associated with the response, in order to fit a single model involving only those predictors is referred to as variable selection.
* Various statistics that help in variable selection are Mallow's Cp, AIC, BIC and adjusted R2.
* But there may be 2^p models and there is no computational power.
* Forward Selection
    * Begin with a null model i.e a model with intercept but no predictors.
    * Then fit p simple linear regressions and all to the null model the variable that results in the lower RSS.
    * Then cont. with this until some stopping rule is satisfied.
* Backward Selection
    * Begin with all variables in the model and remove the variable with the largest p-value i.e variable with the least significance.
    * Again reiterate untill some stopping rule is satisfied.
    * Can't be used if p > n.
* Mixed Selection
    * Combination of forward and backward.
    * Start with no variables in the mode, and add variable that provides the best fit.
    * Now, as we increase the variables, p-value for variables is going to increase and if it exceeds certain threshold then we remove that variable from the model.
* R2 will always increase when more variables are added to the model even if those variables are only wekaly associated with the response.
* Prediction intervals are always wider than confidence intervals because they incorporate both the error in the estimate for f (the reducible and irreducible).
* Confidence interval is used to quantify the uncertainty surrouding the average whereas prediction interval is used to quantify the uncertainty surrouding a particular feature.
* We also need to incorporate a qualitative predictor (also known as a factor).
* If a qualitative predictor only has two lecels, or possible values, then incorporating it into a regression model is very simple. 
* We create an indicator or dummy variable that takes on two possible numerical values.
* The level with no dummy variable is known as the **baseline.**
* Two of the most **important assumptions made by linear model** states tha the relationship between predictors and response are additive and linear.
* **Synergy or interaction effect**
* Extending linear model to include interaction terms (these are the terms obtained from multipying two or more features)
* The hierarchial principle states that if we include an interaction in a model, we should also include the main effects, even if the p-values associated with their coefficients are not significant.
* Note that concept of interaction term applied to qualitative variables as well as to the combination of qualitative and quantitative variables.
* Residual Plots are residuals vs predictors plot and are used for identifying non-linearity.
* Residual plot will show no discernible pattern.
* An **important assumption of the linear regression** model is that the error terms are uncorrelated.
* However, if they are correlated, we may have an unwarranted sense of confidence in our model.
* Correlation between error terms may occur in the context of time series data, which consistes of observations for which measurements are obtained at discrete points in time.
* Another **important assumtion** is that the error terms have a constance variance.
* Once can identify non-constant variances in the errors or heteroscedasticity, from the presence of a funnel shape in the residual plot.
* Outlier
    * It is a point for which y is far from the value predicted by the model.
    * Residual Plots can be used to identify outliers.
    * But in practice, it is difficult to decide how large a residual needs to be before we consider the point to be an outlier.
    * This can be solved by plotting studentized residuals instead of residuals in residual plots.
    * Studentized residuals are computed by dividing each residual by its estimated SE.
    * Obs. whose abs(studentized residuals) are greater than 3 in absolute value are possible outliers.
* Leverage Points
    * Observations with high leverage points have an unusual value for xi.
    * Removing the high leverage observation has a much more substantial impact on the least squares line than removing the outlier.
    * Leverage points are important becuase it is possible that these points heavily affect least squares line becuase any problems with these points may invalidate the entire fit.
    * To identify leverage points, we can simply look for observations for which the predictor value is outside of the normal range of obs.
    * We can use levarage statistics a large value of which is called leverage statistics.
    * Range is [1/n, 1] and the average leverage for all observations alwasy equals (p+1)/n.
    * So if the leverage stat of observation is higher then this, consider it for high leverage point.
* Collinearity
    * The presence of collinearity can pose problems in the regression context, since it can be difficult to separate out the individual effects of collinear variables on the response.
    * Correlation can give an idea about collinearity between pair of features.
    * To asses multicollinearity (i.e collinearity between more than 2 features), use **variance inflation factor (VIF)**.
    * VIF is the ratio of the variance of betaj when fitting full model divided by the variance of betaj if fit on its own.
    * VIF = 1 implies complete absense of colliearity.
    * If VIF exeeds 5 or 10, then there is a problem in predictors.
    * Solutions
        * Drop one of the problematic variables.
        * Combine the collinear variables together into a single predictor.
* [Lab Kaggle Notebook](https://www.kaggle.com/sameepvani/chapter3-islr-linearregression)