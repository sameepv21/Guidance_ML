# Introduction
* Captures the meaning of sentence irrespective of the words.
* Captures relationships like cause and effect.
* Applications
    * Information Extraction
    * Machine Translation
    * Chatbots
* Allows you to represent words and documents as vectors.

# Constructing vectors
* Co-Occurrence matrix transforms sentences into vectors
* Word by Word Design
    * Number of times they occur together within a certain distance k.
* Word by Document Design
    * Number of times a word occurs within a certain category inside a corpus.
    * Example, word data occuring in entertainment, economy and machine learning.
* ![](/assets/images/2022-06-27-19-33-38.png)
    * An example showing word by document co-occurence matrix
* Then, once we have the co-occurence matrix, the similarity metrics is used in order to quantify the similarity between two vectors.
* One of the similarity metric is euclidean distance between two vecors.
* One of its advantages is that it does not drastically increase computational power required with number of vectors.
* Euclidean distance also can be understood as length of the straight line between two points or **norm of difference of two vectors**.
* Problems with euclidean distance
    * It is biased by the sized representation of the vectors.
    * Thus, we can not properly judge based on the distance which two vectors are more similar.
    * Thus, we need another metric which is called cosine similarity function.
* This is one of the most popular similarity metric and solves problem of euclidean distance as angle between vectors remain the same irrespective of the length of the vector.
* Calculated using dot product of two vectors.
    * ![](/assets/images/2022-06-27-20-00-10.png)
* Interpretation of cosine similarity
    * Larger the angle, greater the dissimilarity and vice versa.