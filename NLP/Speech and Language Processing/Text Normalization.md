# Introduction
* It is a process of transforming text in order to reduce its randomness and bringing it closer to a predefined standard.
* Helps in reducing the amount of different information that the computer has to deal with.
* There are at least three tasks that are applied
    * Tokenizing (segmenting) words.
    * Normalizing word formats.
    * Segmenting sentences.

# Tokenization
* Unix tools like tr can be used to tokenize words.
* However, we need a strong and powerful regex to take into account various punctuations, special characters etc.
* Hence, a tokenizer can be used to expan clitic contractions which is a part of word that can't stand on its own and can only occur when attached with another word (like doesn't).
* **Penn Treebank**
    * Commonly used tokenization standard.
    * Spearates outs clitics but keeps hyphenated words together and separates out all punctuations.
    * It is a **deterministic method** based on regex.
* Most tokenization schemes have two parts
    * Token learner - takes a raw training corpus and induces a vocab, a set of tokens.
    * Token segmenter - takes a raw **test** sentence and segments it into the tokens in the vocab.
    * Three used algos are byte-pair encoding, unigram language modeling and wordpiece.
* **Byte-Pair Encoding**
    * There is a problem of unknown words. For eg. our corpus might contain the word low, lowest, new, newer but not the word lower.
    * This algorithm deals with such issues.
    * It automatically induce sets of tokens that include tokens smaller than words called subwords.
    * Furthermore, it denotes the end of sentence via a special character "_".

# Word normalization, Lemmatization and Stemming
* 