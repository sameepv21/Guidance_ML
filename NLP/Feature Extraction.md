# Introduction
* Given some text, you can represent it as a vecor of dimention V where V corresponds to your vocabulary size.
* Here, you change the word appearing in tweet to 1 and other words to 0.
* This is called sparse representation because it would contain large number of 0s and small number of 1s.
* Problem with this approach
    * As V gets larger, the vector becomes more sparse.
    * Training more parameters means larger training and prediction time.
* Thus a solution to this is to use frequency based approach

# Frequency Based Approach
* Here, the number of dimensions are significantly reduced from V to only 3.
* First is Bias, second is summation of positive frequencies and last is summation of negative frequencies.
* Positive frequencies mean that we count the number of times a word appears given that the text is taken from positive class and vice versa for negative frequencies.
* Based on that we contruct a table with 3 columns viz vocab, pos freq and neg freq.
* Now, given a new text, we find the sum of positive and negative frequencies.
* For more details, read [this](https://www.coursera.org/learn/classification-vector-spaces-in-nlp/supplement/sfhGt/feature-extraction-with-frequencies)