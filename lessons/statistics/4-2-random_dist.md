[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

To test if Numpy's random number generator come from a uniform distribution, we want to first pull a random sample of sufficient size and save it.

>random_sample = np.random.random(1000)

We then want to plot the distribution to visualize it's shape. The code below produces the chart as shown.
>pmf = thinkstats2.Pmf(random_sample, label='random sample')
>thinkplot.Pmf(pmf)
>thinkplot.Config(xlabel='Value', ylabel='Relative Frequency')

![random_variable_pmf1](https://user-images.githubusercontent.com/68957343/102638104-9d5dec00-411c-11eb-8e1b-02c1e62015dc.png)

This looks uniform! Great news, but we can take a closer look to examine if the distribution is impacted by the visualization tool, so we alter the default setting on the width of the lines that are generating our chart.

>pmf = thinkstats2.Pmf(random_sample, label='random sample')
>thinkplot.Pmf(pmf, linewidth=0.1)
>thinkplot.Config(xlabel='Value', ylabel='Relative Frequency')

![random_variable_pmf0 1](https://user-images.githubusercontent.com/68957343/102638115-9fc04600-411c-11eb-9441-fadd4c110e0b.png)

Interesting, it appears as though our sample is distributed at a near even frequency, but there are large gaps between values. Of course, we should expect to see this for a continuous variable and a finite sample. Regardless of sample size, there will always be a sufficiently small line width to produce such a visual, assuming for issues with screen resolution and specificity.

Finally, we create a cumulative distribution and we can see a nearly linear trend, as we would expect from a uniformly distributed sample. 

>cdf = thinkstats2.Cdf(random_sample, label='random sample')
>thinkplot.Cdf(cdf)
>thinkplot.Config(xlabel='Value', ylabel='Cumulative Frequency')

![random_variable_cdf](https://user-images.githubusercontent.com/68957343/102638116-a18a0980-411c-11eb-8005-7f021f87914c.png)
