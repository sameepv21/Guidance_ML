# Introduction
* Errors include a misclassified sentence.
* Possible reasons
    * Sementic meaning lost in preprocessing step.
        * For example, My beloved grandmother :(
        * Here, the sad puntuation shows that it is sad. Hence, removing it might loose the semantic meaning it carries.
    * Word order
        * I am happy because i did not go.
        * I am not happy becuase I did go. (Order of word is important)
    * Adversarial attacks
        * Machines are not able to detect sarcasm, irony or euphemisms.
        * For eg. This is a ridiculously powerful movie. The plot was gripping and I cried right through until the ending.
        * This is positive but machine will tell you negative.