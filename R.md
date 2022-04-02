# Introduction
* Language of Data Science
* 50% more popular than Python
* Free and Open source
* Can perform vector operations
* Has great community
* 9000+ third party packages.

# Links
* [Downloading R](https://cloud.r-project.org/)
* [R for Data Science (**Must Read Book**)](https://r4ds.had.co.nz/)
* [Handson Book for R](https://rstudio-education.github.io/hopr/)

# Packages Download
* CRAN (Comprehensive R Archive Network)
* Crantastic
* Trending GitHub Repos

# Some important packages
* tidyverse --> A combined package for almost all libraries
* dplyr --> Deep Lyer --> Manipulating Dataframes
* tidyr --> Tydier --> Cleaning up information
* stringr --> Stringer --> For working with strings
* lubridate --> For working with date type
* httr --> For working with website related data
* ggvis --> Grammar for Graphics --> For interactive visualization tool
* ggplot2 --> Most Common for creating graphics and data visualization
* shiny --> Mostly used for visualizations on websites
* rio --> R Input and output --> For importing and exporting data
* rmarkdown --> Interactive and rich notebooks for sharing information.
* pacman --> Package Manager --> One package to load them all
* psych --> Contains describe function

# Some important functions
* library() --> Load a package into R environment
* curve() and dnorm() --> Density Normal Distribution
* plot() --> Automatically detects the type of inputs and plots the graphs accordingly
* barplot() --> For plotting bar graphs.
* table() --> Converting the dataset into a table (rows and columns)
* hist() --> For plotting a histogram
* par() --> Change parameters --> Basically for Subplots
* lines() --> Plotting line chart
* density() --> plotting KDE
* rug() --> Plotting rug plot
* summary() --> Analogous to X_train.describe() in pandas
* head() --> Shows 6 records
* describe() --> Only for quantitative variable --> Requires psych library --> Gives more details than summary()
* c() --> Combine/concat
* is.vector() --> Self explanatory
* matrix() --> Create matirc
* cbind() --> Column wise join two or more dataframes or arrays or matrices.
    * Result is a matrix in general case
* rbind() --> Forma a matrix by combinding rows.
* as.data.frame() --> Create a dataframe
* list() --> Create a list
* seq() --> More control over entering data.
* scan() --> Takes input from console or user.
    * Note that it does not take one input. It keeps on taking input unless enter is pressed twice.
* rep() --> Repeat certain task and store the output
* browseURL() --> Opens the passed in URL in the webpage.
* import() --> Reads the file passed in as the parameter
    * Can read csv, text and xlsx.
    * Uses rio package.
* View() --> Spreadsheet like thing that helps to view the dataset.
* read.table() --> Another method to read the files.
* rect.hclust() --> Differentiate and create rectanular boxes around a dendrogram based on the passes parameters.
* prcomp() --> Compute Principal Components
* predict() --> Make predictions
* biplot() --> 2D graphs with names and not numbers.
    * Used after PCA.
    * Not very inferential
* lm() --> Linear Model
* anova() --> Analysis of variance table
* coef() --> Coefficients
* confint() --> Confidence internval for our lm.
* resid() --> Get the residuals of our lm.
* lars() --> Least angle regression
* caret --> classification and regression training
* source(<FILE_NAME_IN_QUOTES>) --> Run .r script
* objects()/ls() --> Displays the names of the objects which are currently stored within R.
* rm() --> Remove objects currently stored in workspace
* seq() --> Generate sequence of numbers
* is.na() --> Gives true and false for x where na is there.
* attributes(<OBJECT>) --> Returns a list of all the non-intrinsic attributes.
* unclass() --> Remove class of an object for temporary purposes.
* factor() --> Creates a factor.
* tapply() --> Gives output of a function (say mean()) of the vector passed with the components labelled by the levels in a factor.
* ordered() --> custom order for factors instead of alphabetical.
* array() --> Creates an array
* outer() --> Perform outer product on 2 **vectors**.
* t(<MATRIX>) --> Transpose of the matrix
* eigen() --> Calculated eigenvalues and eigenvectors os symmatric matrix.
* svd() --> Calculate SVD of the provided matrix
* lsfit() --> Least squared fit
* qr() --> Gives qr decomposition of the provided matrix.
* attach() and detach() --> Attach/Detach database (list or dataframe) to the R session 

# Coersion or Casting
* Changing one datatype into another
* typeof() --> States the type of variable passed in it.
* Basically coerce means that taking multiple data types and combining with c() function but the result is that the datatype is changed to generic which is character.
* Hence, one should be careful and use as.data.frame() method to convert it into a dataframe while maintaining the datatypes.
* Other functions include as.integer(), as.numeric() etc.

# Data types
* numeric (interger, single and double)
* character
    * Note that there is no explicit datatype as string
    * However, one can store a string in variable but one thing that needs to be remembered is that it does not mean it is a string
    * The datatype still remains a character
* logical --> Boolean
* complex
* raw

# Data Structures
* Vector --> Array 
* Matrix --> 2D array
* Array --> More than 2 dimensions
* Dataframe --> Can hold vectors of multiple data types
* List --> Ordered collection of elements --> Can put anything into it

# Extras
* Putting a parenthesis around a variable, R will not only store that variable in the environment but also display it in the console.
* cbind.data.frame() --> Combine and Cast into dataframe in one line.
* **Factors in R is a v araible used to categorize and store the data, having a limited number of different values.**
* **It is also known as categorical variable that stores both string and integer data values as levels.**
* '<-' is the assignment operator in R.
* Pipeline in R --> %>%
* Shapes are auto handled in R (most of the times).
* Factors are data structures in R that store categorical data.
* Inverse of a matrix is done with the help of solve function.
* Look at global variables in R