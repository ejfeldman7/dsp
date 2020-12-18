[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

We are asked to consider the distribution of men whose mean height is 178 cm and standard deviation is 7.7 cm. Using this distribution, we must determine what percentage of the population we would expect to be eligible for the Blue Man Group, between 5'10" and 6'1". First, as the distribution is described in cm, let's consider that the height requirements for Blue Man Group are between 177.8 and 185.42 cm, once converted to metric. 

Since we are given that heights should follow an approximately normal distribution, we can set up our distribution as follows:

>mu = 178  
>sigma = 7.7  
>dist = scipy.stats.norm(loc=mu, scale=sigma)

We wish to determine the area beneath our pmf between 177.8 and 185.42, so we will calculate the area to the left of 185.42 and subtract the area to the left of 177.8.

>dist.cdf(185.42)-dist.cdf(177.8)  

This gives us a value of .342, or 34.2% of the population. 

This result is unsuprising, when we consider that we are at an area that is approximately from the mean to one standard deviation above the mean. Following the empirical rule, we can expect this to be roughly 34% of the population, which our calculation confirms!
