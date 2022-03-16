# Types of features
* Time-step features
    * Features that we can derive from the time index.
    * Most basic is time dummy which counts off time steps in the series from beginning to end.
    * Lets you model time dependence.
    * Lets you plot **time plot**, in which time is in the x-axis.
* Lag Features
    * Shift the observations of the target series so that they appear to have occured later in time.
    * Lets you plot **lag plots** where each observation in a series is plotted against the previous observations.
    * Can measure or see that sales on one day are correlated to sales on previous days (if there is a correlation).
    * Lets you model serial dependence.
    * Pandas provides shift method for this purpose.
    * While doing this, need to make sure about the missing values that might be produced.
        * One option is to fill them with 0 or backfilling them.
        * Other is to drop these values and make sure to drop them from target variables from corresponding dates.
* Best time series models will use some combinations of lag features and time series features.

# Trend
* Trend component of a time series represents a persistent, long-term change in the mean of series.
* Slowest moving part of the series.
* We use moving average plot to see what kind of trend a time series might have.
* Idea is to smooth out any short-term fluctuations in the series so that only long-term changes remain.
* For a change to be a part of the trend, it shoild occur over a longer period than any seasonal changes.
* If trend discovered by our LR model is almost identical to the moving average plot, which suggests that a linear trend was the right decision in this case.

# Seasonality
* Time series exhibites seasonality whenever there is a regular, periodic change in th mean of the series.
* Often driven by the cycles of the natural world over days and years or by conventions of social behaviour surrounding dates and times.
* 2 features that model seasonality
    * Indicators
        * Weekly season of daily observations.
    * Fourier
        * Many observations like annual season of daily observations.
* Seasonal Plots
    * Used to discover seasons.
    * Shows segments of the time series plotted against some common period, the period being the "season" you want to observe.
* Seasonal Indicators
    * Binary features that represent seasonal differences in the level of a time series.
    * Result of treating seasonal period as a categorical feature and apply one-hot-encoding.
* Fourier Features
    * Instead of creating a feature for each date, it tries to capture the overall shape of the seasonal curve with just a few features.
    * Idea is to include, in our training data , periodic curves having the same frequencies as the season we are trying to model.
    * Thus, we use trigonometric functions.
    * Fourier Features are pairs of sine and cosine curves, one pair for each potential frequency in the season starting with the longest.
* Periodogram
    * Calculates the number of fourier pairs required to actually include in feature set.
    * Tells you the strength of the frequencies in a time series.

# Serial Dependence
* Returns evolve nonrandomly, that is they are correlated with their prior values.
* One special way is cycles.
* Cycles are patterns of growth and decay on values at pervious times, but not necessarily on the time step itself.
* Cyclic behaviours are not time dependent as seasons are.
* Less about particular date of occurence but more about what has happened in the recent past.
* Use lag plots to model serrial dependence (like cycles).
* Lagging a time series means to shift its values forward one or more steps.
* In layman terms, simply create new features with one delay/row below it.
* We make past values appear to be exisiting or occuring in same period of time.
 
# Extras
* Series is time dependent if its values can be predicted from the time they occured.
* Series is serial dependent when an observation can be predicted from pervious observations.
* Time series is majorly about feature engineering with time column and lag.
* Deterministic process is a technical term for a time series that is non-random or completely determined.
* Look at something called out of samples features.
    * Referas to times outside of the observation perioud of the training data.