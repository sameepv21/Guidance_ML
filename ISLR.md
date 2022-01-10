# Statistical Learning
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
    * Those problems in which we **response** variable is **quantitative** is called **regression** problem and vice versa.
* Measuring the quality of fit (Regression)
    * MSE
        * Computed on the training data.
        * However, we are interested in predictions that we obtain when we apply out method to unseen test data.
        * Lowering the training MSE does not garuntee a decrease in test MSE a phenomenon generally refered to as **overfitting**.
        * **Degrees of freedom** is a quantity that summarizes the flexibility of a curve.
        * The training MSE decline monotonically as flexibility increases.
        * However, the test MSE declines initially as flexibility increases but at some point the test MSE levels off and then starts to increase again (Giving the test MSE a U-shape curve).
        *  Overfitting happens because, our model is trying too hard to find pattterns in the trainin data and may be picking up some patterns that are just caused by random chance rather by true properties of the unknown function f.
* Bias-Variance Trade Off
    * E[test MSE] for a given x, can be decomposed into 2 sums --> The variance of yhat, the squared bias of yhat and the variance of error term.
    * Variance of irreducible error is not in our control.
    * Thus, we want a model that has low bias and low varaince of yhat.
    * **Variance** refers to the amount by which fhat would change if we estimated it using a different training data set.
        * High variance means that small change in training data can result in large changes in f.
        * More flexible statistical methods have higher variance and vice versa.
    * **Bias** refers to the error that is introduced by approximating a real-life problem, which may be extremely complicated, by a much simpler model.
* Measuring the quality of fit (Classification)
    * Error Rate
        * Proportion of mistake that are made if we apply our estimate fhat to the training observations
        * Uses indicator random variable.
        * Can be used for both training and test (but we are more interested in test)
* The Bayes Classifier
    * Assigns each observation to the most likely class, given its predictor values.
    * Assign the class for which Pr(Y = j | X = x0) is largest.
    * Bayes Error Rate = 1 - E(max(Pr(Y = j | X)))
* KNN (Classifier)
    * Given a positive integer K and a test observation x0, the KNN classififer first identifies the K points in the training data that are closet to x0 and then estimates the conditional probability for class j as a fraction of points.
    * Classifies the test obs to the class with the largest probability.
    * Choice of 'K' is crucial.
    * K = 1 --> Overly flexible and overfits the data, low bias and high variance.
    * As K increases, high bias and low variance.
* [Lab (Kaggle Notebook)](https://www.kaggle.com/sameepvani/chapter2-islr-statisticallearning) 