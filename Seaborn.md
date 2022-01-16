# Links
* [Official Documentation](https://seaborn.pydata.org/tutorial/distributions.html)

# Seaborn
* Useful functions
    * lineplot(data=*DATA*, label=*LABEL*)
    * barplot(x=*INDEX*, y=*DATA ON Y-AXIS*)
    * heatmap(data=*DATA*, annot=True)
        * annot=True displays the number also
    * scatterplot(x=*DATA*, y=*DATA*, (op) hue=*DATA*)
    * regplot(**Same as scatter plot except hue parameter**)
        * Also plots the regression line and hue is to add color coding based on that parameter
    * lmplot(**Same as scatter plot with hue parameter**)
        * Plot regression line along with color codes
    * swarmplot(x=*DATA*, y=*DATA*)
        * Used specifically for plotting categorical features on one of the axis
    * distplot/histplot/displot(a=*DATA*, kde=False, label=*LABEL*)
        * kde means another curve that follows histogram (smoothened histogram)
        * Label is used to ensure color coding if multiple histograms are plotted and hence is optional
    * kdeplot(data=*DATA*, shade=True, label=*LABEL*)
        * Label has same functionality as above.
    * jointplot(x=*DATA*, y=*DATA*, kind="kde) 
        * Plots joint kde or 2D kde
* Styling
    * sns.set_style(*STYLING_METHOD*)
        * 5 Different methods include darkgrid, whitegrid, dark, white, ticks