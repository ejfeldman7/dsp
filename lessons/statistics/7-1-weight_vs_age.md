[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

We are tasked with doing some exploratory analysis of the relationship between a mother's age and her baby's weight at birth. To begin, we organize and clean our data.

>import first  
>live, firsts, others = first.MakeFrames()  
>live = live.dropna(subset=['agepreg', 'totalwgt_lb'])  
>age_preg , baby_weight  = live.agepreg, live.totalwgt_lb

Then, we take our data and create a scatterplot:

>thinkplot.Scatter(age_preg, baby_weight, alpha=.5, s=1) 
>thinkplot.Config(xlabel="Mother's Age",  
                 >ylabel="Baby's Weight (lb)",  
                 >axis=[0, 60, 0, 15],  
                 >legend=False)
                 
![mothersage_babyweight_scatter](https://user-images.githubusercontent.com/68957343/102666671-23922680-414d-11eb-962c-acbf6fff981e.png)

We see no obvious relationship, linear or otherwise between our two variables in this scatterplot. 

Next, we create bins and organize our data into percentile groups and plot the percentiles for baby weight again the mean ages in those percentiles:

>bins = np.arange(10, 50, 2)  
>indices = np.digitize(age_preg, bins)  
>groups = live.groupby(indices)  

>mean_age = [group.agepreg.mean() for i, group in groups]  
>cdfs = [thinkstats2.Cdf(group.totalwgt_lb) for i, group in groups]

>for percent in [75, 50, 25]:  
    >weight_percentiles = [cdf.Percentile(percent) for cdf in cdfs]  
    >label = '%dth' % percent  
    >thinkplot.Plot(mean_age, weight_percentiles, label=label)  
    
>thinkplot.Config(xlabel='Age',  
                 >ylabel='Weight (lb)',  
                 >axis=[0, 50, 0, 20],  
                 >legend=False)

![mothersage_babyweight_percentileplot](https://user-images.githubusercontent.com/68957343/102666897-a7e4a980-414d-11eb-83ee-11a7d3591c3c.png)

Again, we don't see a strong trend in this data. It appears as though baby weight's are, on average, fairly consistent against mother's age and the differences between percentile's means stay somewhat the same as well. The variability for younger and older mothers may be a result of smaller populations within those bins, rather than any evidence of correlation.

Finally, we can compute both our Correlation Coefficient and Spearman's coefficient:

>np.corrcoef(age_preg,baby_weight)  
>SpearmanCorr(age_preg,baby_weight)

We get values of .0688 and .0946 respectively, indicating that there does not appear to be a strong relationship present, linear or otherwise. 
