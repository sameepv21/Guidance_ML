* Logistic Regression is a classficiation algorithm which can be used either for binary or for multiclass classification
* Right now lets consider a binary classification
* Every Machine Learning algorithm will require a loss function which in turn will get averaged over entire dataset to create a cost function.
* Further we need a cost function that is like MSE (Has a global minima, is continuous and differentiable)
* Currently if we use miss classification rate as the loss function then the value would be either 0 or 1 which does not have a global minima (Varying too much with ups and downs).
    * In other words, we need a cost function that is convex in nature
    * Thus, we use log loss which is then averaged to get cost function.
    * Loss Function = -( y\*log(yhat) - (1-y)\*log(1 - yhat) )
    * Consider two cases, 
        * y = 1 --> Loss function = -log(yhat)
        * y = 0 --> Loss function = -log(1-yhat)
* Then, once we have decided the cost function, we can easily perform backpropagation and gradient descent.
* Computation graphs are used to understand what happens at each step of forward propagation and back propagation.
* As a result of backpropagation, the weights will get adjusted and we will optimize the solution.
* Now, to achieve this for every dataset and for many epochs, there must be two nested for loops in our code.
* Already the neural networks are quite inefficient and adding extra n^2 complexity doesnt make any sense.
* To get rid of extra loops, vectorization is used which is discussed in detail in other md files.

# Derivatives
* Always think of derivatives as that amount by which a point gets scaled up or down if provided a small nudge.