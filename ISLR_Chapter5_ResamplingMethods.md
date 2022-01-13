# Resampling Methods
* They involve repeatedly rawing samples from a training set and refitting a model of interest on each sample in order to obtain additional information about the fitted model.
* Cross Validation
    * The test error is the average error that results from using a statistical learning method to predict the response on a new observation.
    * The training error can be easily calculated by applying the statistical learning method to the observations used in its training.
    * However, instead of validating on training set, we can validate it on other set using number of techniques.
* Validation Set Approach
    * It involves randomly dividing the available set of observations into two parts, a training set and a validation set or hold-out set.
    * The model is then fit on the training set and the fitted model is used to predict the responses for the observations in the validation set.
    * The resulting validation set error rate then provides an estimate of the test error rate.
    * However, if we repeat the process of randomly splitting the sample set into two parts, we will get a somewhat different estimate for the test MSE.
    * This may result into a high;y variable test MSE.
    * Since statistical methods tend to perform worse when trained on fewer observtions, thjis suggests that the validation set error rate may tend to overestimate the test error rate for the model fit on the entire data set.
* Leave-One-Out Cross-Validation (LOOCV)
    * Here, instead of creating two subsets, we just leave one sample out of the training set and train over model on the rest n-1 observations.
    * Then, we predict for that left out obs. and calculate the MSE.
    * Then, we leave another out and do the same thing untll we have n MSEs.
    * Then, we take the average of all of them to get the final test MSE.
    * Advantage of this method is that it tends not to overestimate the test error rate as much as the validation set appraoch does.
    * Secondly, performing LOOCV multiple times will always yield the same results as there is no randomness in the traning/validation set splits.
    * We define h(i) as the levarage. Hence according to the LOOCV equation, the residuals for the high leverage points are inflated.
* k-fold Cross Validation
    * This approach ivolved randomly dividing the set of observations into k groups, or folds, of approximately equal size.
    * The first fold is treated as the validation set and the model is fit on remaining k-1 folds.
    * Then, the fitted model is evaluated on the first set and MSE is calculated.
    * This is repeated k times for each set is considered as validation for exactly one time.
    * Then resulant MSE is calculated by computing average MSE.
    * LOOCV is a special case with k = n.
    * Advantage is computational.
    * Usually 5-fold or 10-fold is prefered due to bias-variance trade off.
* However, performing different cross validation is not the goal. The goal is to find the minimum point in the estimated test MSE.
* **Note that correlation increases variance.**
* Cross Validation on classification problem
    * Here only one thing changes that is the loss function.
    * Instead of MSE, it would be number of misclassified observations. 
* **Bootstrap**
    * Statistical tool that can be used to quantify the uncertainty associated with a given estimator or statistical learning method.
    * Applied to wide range of statistical methods.
    * Also used to assess the variability associated with the regression coefficients in a linear model fit.
    * The problem in any dataset is that we can't generate new samples from the original population.
    * Bootstrap allows us to overcome this.
    * It allows us to use a computer to emulate the process of obtaining new samples so that we can estimate the variability without generating additional samples.
    * So now instead of repeatedly obtaining independent datasets from the population, we instead obtain distinct datasets by repeatedly sampling observations from the original dataset.