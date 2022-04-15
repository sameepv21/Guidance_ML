# What is it?
* Regular Expression is a tool for performing operations like grep.
* Used in many functionalities offered by ubuntu.
* Helps in recognizing patterns.

# Basic Patterns
* /WORD/ --> Matches that word or character in the input document.
    * Is case sensitive and that might pose a problem sometimes.
* [STRING] --> Searches for each charater in string
    * "OR" operation
* [A-Z] --> Example on how to specify range.
* ^ --> Specify what a single character cannot be.
    * Caret only works if it is the first symbol after opening the square bracket
    * Another use case is to match at the start of the line.
    * For that don't write carent inside square brackets.
* ? --> Preceding cahater or nothing
* \* --> Kleene Star means zero or more occurrences
* \+ --> Keene plus means one or more occurrences of the immediately preceding charater or regex.
    * /[0-9]+/ --> Specify sequence of digits
* /./ --> Wildcard char which means any string
* Wrapping in \b matchs a word boundary and not a substring.

# Disjunction, Grouping and Precedence
* 