# What is it?
* Field of AI that gives the machines the ability to read, understand and derive meaning from human languages.
* Not necessarily, English

# Use Cases
* Voice assistants
* Sentiment analysis
* Prediction of diseases
* Chatbots

# Bag of words
* Commonly used model that allows you to count all words in a piece of text.
* Creates an occurence matrix for the sentence or document.
* Disregards grammar and word order
* Then those frequencies are supplied to a classifier.
* Problem
    * Absense of semantic meaning and context
    * Stop words bring noise to the data.
* Solved by using TFIDF (Term Frequency - Inverse Document Frequency)

# TFIDF
* Improves BOW
* Through TFIDF, frequent terms in the text are "rewarded" but they are also "punished" if those terms are frequent in other texts we include in the algorithm.
* Considers all texts and then hights and rewards unique or rare terms.
* Problem is that there is still no context and sematics

# Tokenization
* Process of segmenting running text into sentences and words (or in more general - called tokens).
* Also, they throw away some characters such as punctuations making it very easy.
* Problems
    * English separates words by blank space, which is not quite possible in other languages.
    * It also splits certain group of words that, together should be considered as a token like San Fransisco.
    * Since it removes punctuations, certain useful meanings like (Dr.) gets removed too.
    * Problematic when dealing with biomedical texts containing lots of hyphens, paranthese etc.

# Stop Words Removal
* Includes getting rid of common language articles, pronouns and prepositions suchs as "and", "the", or "or".
* Very common words that appear to provide little or no value to NLP objective are filtered and excluded from the text to be processed.
* Can be implemented by a lookup in a pre-defined list of keywords, freeing up database space and improving processing time.
* Problems
    * Might wipe out relevant information and modify the context in a given sentence.
    * Example --> Sentiment analysis --> "Not" removed --> Causing problem

# Stemming
* Process of slicing the end or beginning of words with the intention of removing affixes.
* Why needed?
    * Affixed can create or expand new forms of the same word, or even create new words themselves.
    * Same meaning words can get differentiated if affix are not taken care of.
    * Simple to use and run very fast.
* How to select which letters to discard?
    * Common approach is to consider a list of common affixes and rules and then perform stemming based on them.
    * Has obvious limitations such as result of stemmming a word may not remain an actual word or even change the meaning of the words.

# Lemmatization
* Objective of this process is to reduce a word to its base form and grouping together different forms of the same word.
* Example --> Words changed to present and sysnonyms being unified.
* Basically, we are standardizing words with similar meaning to their root.
* Different than stemming in terms of approach to reach root word.
* Resolved words to their dictionary form for which it required detailed dictionaries in which the algorithm can look into and link words to their corresponding lemmas.
* Also takes into consideration, the context of the words.
* By using a part-of-speech parameter to a word (whether it is a noun or a verb), its possible to define a role for that word in the sentecne and remove disambiguation.
* Problems
    * Resource Intensive Task compared to stemming.
    * Demands more computational power than stemming.

# Topic Modeling
* Method for uncovering hidden structures in sets of texts or documents.
* Clusters texts to discover latent topics based on their contents, processing individual words and assigning them values based on their distribution.
* **Assumption is that each document consists of a mixture that if we can spot these hidden topics we can unlock the meaning of our texts.**
* Most commonly used is Latent Dirichlet Allocation (LDA)
    * Unsupervised learning methods
    * Discovers different topics underlying a collection of documents.
    * How Does it find groups of related words?
        * See some youtube links

# Extras
* **Must look at hashing, locality sensitive hashing and how is it useful in case of NLP.**
* Approximate Nearest neighbours.