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