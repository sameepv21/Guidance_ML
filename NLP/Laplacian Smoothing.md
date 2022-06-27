# Introduction
* In naive bayes, we calculate conditional probability like p(wi | positive)(pp) or p(wi | negative) (pn)
* Then, we would notice that there are certain neutral words for which both these probabilities are nearly the same and dont add any meaning to the overall sentiment.
* Finally, you calculate probabilitiy product of the ratio pp/pn.
* If that value is greater than 1, high change that the chosen tweet is positive and vice versa.
* The problem with this approach is that if some word did not appear in a tweet, then the probability results into 0.
* So to solve this issue, we use laplacian smoothing.

# What is it?
* ![](/assets/images/2022-06-27-07-54-24.png)
* Here, VClass means number of unique words in class and Nclass means frequency of all words in class.
* This is similar to hallucinating terms and exponential smoothing.

# Log Likelihood
* Ratio = P(wi | Pos)/P(wi | Neg)
* Positive words have ratio greater than 1.
* Larger the number, more positive it is.
* Negative number has a ratio of of less than 1.
* Smaller the number, more negative it is.
* ![](/assets/images/2022-06-27-07-59-13.png)
    * The above image is full naive bayes formula.
    * The first term is prior knowledge which is useful when the dataset is unbalanced and second term is product of ratios which is used to actually classify the tweet based on the results.
    * Naive bayes is a probabilistic model used for classification.
* Basically, use log of the score.
* It is helpful as it turns product into summation and also removes the risk of numerical underflow where the value is so small to be stored on computer.
* Now, for log ratio, the threashold shifts from 1 to 0.
    * This means that if a number (after calculating log likelihood) is greater than 0, then higher chance of positive tweet and vice versa.
