 Feature-Engineering---Discretisation


Discretisation is the process of transforming continuous variables into discrete variables by creating a set of contiguous 
intervals that span the range of the variable's values. Discretisation is also called **binning**, where bin is an alternative 
name for interval.


### Discretisation helps handle outliers and may improve value spread in skewed variables

Discretisation helps handle outliers by placing these values into the lower or higher intervals, together with the remaining 
inlier values of the distribution. Thus, these outlier observations no longer differ from the rest of the values at the tails 
of the distribution, as they are now all together in the same interval / bucket. In addition, by creating appropriate bins or 
intervals, discretisation can help spread the values of a skewed variable across a set of bins with equal number of observations.


### Discretisation approaches

There are several approaches to transform continuous variables into discrete ones. Discretisation methods fall into 2 categories:
supervised and unsupervised**. Unsupervised methods do not use any information, other than the variable distribution, 
to create the contiguous bins in which the values will be placed. Supervised methods typically use target information in 
order to create the bins or intervals.


####  Unsupervised discretisation methods

- Equal width discretisation
- Equal frequency discretisation
- K-means discretisation

#### Supervised discretisation methods

- Discretisation using decision trees


In this lecture, I will describe **equal width discretisation**.


## Equal width discretisation

Equal width discretisation divides the scope of possible values into N bins of the same width.The width is determined by the range 
of values in the variable and the number of bins we wish to use to divide the variable:

width = (max value - min value) / N

where N is the number of bins or intervals.

For example if the values of the variable vary between 0 and 100, we create 5 bins like this: width = (100-0) / 5 = 20. 
The bins thus are 0-20, 20-40, 40-60, 80-100. The first and final bins (0-20 and 80-100) can be expanded to accommodate 
outliers (that is, values under 0 or greater than 100 would be placed in those bins as well).

There is no rule of thumb to define N, that is something to determine experimentally.

## In this demo

We will learn how to perform equal width binning using:

- pandas and NumPy
- Feature-engine
- Scikit-learn
