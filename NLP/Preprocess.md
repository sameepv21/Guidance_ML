# Introduction
* Eliminate handles and URLs
* Tokenize the strings into wrods
* Two most common methods include stemming and stop words.
* Convert all your words to lower case.

# Stemming
* Convert each word to its base word.
* This means that running is converted to run for example.

# Stop words
* These include words or puntuations that add no meaning to the overall sentiment of the text.
* These are already availble arrays and just need to perform lookups in them.

# Finalizing
* Once preprocessed the tweets, then you extract the features (a dimensional vector) which contain bias, pos freq and neg freq.
* You repeat this for each and every piece of text and gather an mx3 dimensional matrix where m = number of tweets.
* Finally, you can pass this matrix into one of the ML models.