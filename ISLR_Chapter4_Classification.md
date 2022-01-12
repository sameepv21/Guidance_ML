# Introduction
* Why not Linear Regression?
    * We can very well encode different classes and use it as a regression problem.
    * In general, there is no natural way to convert a qualitative response variable with more than two levels into a quantitative response that is ready for linear regression.
    * However, for binary classification, the classifications that we use linear regression to predict a binary response will be the same as for the LDA (Linear Discriminant Analysis).
    * Two reasons not to perform classification
        * Can't accomodate a qualitative response with more than two classes.
        * It will not provide meaningful estimates of Pr(Y | X), even with just two class.
* Logistic Regression
    * Instead of modelling response Y directly, it models the probability that Y belongs to a particular category.
    * Logistic Function is used ranges from [0, 1]
    * To fit the model we use a method called maximum likelihood.
    * The function function will always produce an S-shaped curve regardless of the value of X.
    * Logistic function is better able to capture the range of probabilities than is the linear regression model.
    * **Odds = p / (1-p)** where p is probability.
    * **Log odds or logit is calculated by taking log of odds XD.**
    * In a logistic regression model, increasing X by one unit changes the log odds by beta1.
    * Estimatig the coefficients
        * Maximum likelihood is preferred.
        * We seek estimates for beta0 and beta1 such that the predicted probability is as close to 1.
        * This in mathematical form is called likelihood function.
        *  We choose the estimates to maximize this likelihood function.
        * z - statistics play a similar role as t-statistics.
    * Multiple Logistic Regression
        * Only the likelihood function changes.
    * Confounding is a phenomenon that affects the relationship between input data and output variables.
    * Correlation can be one of the cofounders.
    * Multinomial Logistic Regression
        * Select a single class to serve as the baseline.
        * However, interpretation of coefficients must be done with care as they change with changing baseline.
        * Thus, likelihood function can't work because it depends on the choice of baseline.
        * Thus, we use softmax coding.
        * Rather than selecting a baseline case, it treats all K classes symmetrically.
* Generative Models for Classification
    * Note that Bayes classifier is the most optimum one.
    * It is a classifier against which all others are judged.
* Linear Discriminant Analysis (LDA)
    * **Here we assume that fk(x) is normal or gaussian.**
    * **Further assume that there is a shared covariance.**
    * delta(x) = taking log on both the sides of bayes classifier equation. These are also known as discriminant functions.
    * The bayes decision boundary is the point for which delta1(x) = delta2(x).
    * LDA provides the method to estimate the paramters that can be plugged in bayes classifier to get the probability.
    * Since these discriminant functions are linear functions of x, hence the name **Linear**
    * In general, a binary classifier like this one can make two types of mistakes.
        * One that it incorrectly assigns right to actually a wrong.
        * Second that it incorrectly assigns wrong to actually a right.
    * Confusion matrix can be used.
        * Which is a table of true and false positive with true and false negative.
        * That is it gives a table for misclassifications.
    * Bayes classifier and LDA uses a threshold of 50% for the posterior probability (by default) in order to assign an observation.
    * ROC Curve
        * Full form is receiver operating characteristics.
        * It is a curve between **True Positive Rate and False Positive Rate.**
        * The closer it is to 1, the better it is said to be i.e it hug the top-left corner
        * AUC (Area Under Curve) is actually the correct measure for performance.
        * Hence, it is said that more closer it is to 1, more area it will cover.
* Quadratic Discriminant Analysis (QDA)
    * QDA also **assumes** that the observations are drawn from a Gaussian distribution.
    * It also **assumes** that each class has its own covariance matrix unlike LDA where there is a shared covariance.
    * Now, the equation of discriminant changes and bayes classifier assigns the obs to the class for which this equation is the largest.
    * However, unlike LDA, the x is now a quadratic function.
    * Why prefer QDA to LDA and vice versa?
        * LDA is prefered because it assumes a shared covariance matrix which decreases the load on CPU.
        * However, it is less flexible because of this.
        * High, it might have low variance but high bias (under the condition that the assumption of shared covariance matrix is wrong).
        * However, QDA is flexible compared to LDA.
        * Thus, it is more flexible and can lead to improved performance.
        * In short, LDA is preferred when there are relatively few training observations and so reducing variance is crucial and vice versa.
* Naive Bayes
    * It **assumes** that within the kth class, the p predictors are independent.
    * However, it **does not assume** anything about the shape of distribution or covariance within each class.
    * Mathematically, the fk(x) is multiplication of individual functions.
    * Why is the assumption so powerful?
        * The problem with earlier approaches is that the marginal distribution along with join distribution plays a heavy role.
        * However, if assumed that they are independent, then we dont need to worry about the association between the predictors because we have simply assumed that there is no association.
    * However, in practice, we dont actually believe this assumption to be true. But still it gives a good result if n is not large enough relative to p.
    * This assumption does introduce some bias but reduces variance by a lot of extent.
    * If Xj is quantitative then we assume that probability follows a normal distribution.
    * KDE plot (Kernel Density Estimator) is a smoothened version of histogram.
* KNN
    * In orde rto make a prediction for an observation X = x, the training observations that are closest to x are identified.
    * Then X is assigned to the class to which the plurality of these observations belong.
    * Dominates LDA and logistic regression when the decision boundary is highly non-linear with n being very large and p being small.
    * In setting where decision boundary is not linear but n is only modest or p is not small, then QDA may be preferred to KNN.
    * It does not tell which predictors are important.
* Poisson Regression
    * It assumes that data follows poisson distribution.
    * This means that larger the mean of Y, the larger would be its variance.
    * It is typically used to model *counts*.
    * Poisson distribution always takes a non negative number.
* Link Function (eta) applies a transformation to E(Y | X1....Xn) so that the transformed mean is a linear function of the predictors.
* This means that eta(E(Y | X1 .... Xn)) = beta0 + beta1\*X1 + ... + betap\*Xp
* In general, we can perform a regression by modeling the response Y as coming from a particular member of the exponential family (Bernaulli, Gaussian and Poisson), and then transforming the mean of the response so that the transformed mean is a linear function of predictors.
* Any regression that follows this general approach is called generalized linear model (GLM).
* [Lab Kaggle Notebook]()