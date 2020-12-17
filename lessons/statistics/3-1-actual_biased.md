[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

First, we create PMF and histogram for the responses from those surveyed using the following code:

>pmf_kids = thinkstats2.Pmf(resp.numkdhh, label='unbiased_kids')  
>thinkplot.Pmf(pmf_kids)  
>thinkplot.Config(xlabel='Number of Kids', ylabel='Frequency'

![pmf_kids](https://user-images.githubusercontent.com/68957343/102549263-70103000-4081-11eb-9ee9-95afb6235064.png)


We then want to create the biased PMF that would represent data collected from children, rather than households. We expect that households with more children would response proportionally to the number of children in the household, so our distribution should change from being skew right to more symmetric or maybe even skew left. Certainly, we expect the mean to increase significantly in the new PMF. We call on a function to bias our PMF:

>bias_kids_pmf = BiasPmf(pmf_kids, label='biased_kids')

And then plot our new PMF:

>thinkplot.Pmf(bias_kids_pmf)  
>thinkplot.Config(xlabel='Number of Kids', ylabel='Frequency')

![bias_pmf_kids](https://user-images.githubusercontent.com/68957343/102549389-a057ce80-4081-11eb-8c02-07740e27006a.png)

We can overlay the two PMF for comparison if desired:

>thinkplot.PrePlot(2)  
>thinkplot.Pmfs([pmf_kids, bias_kids_pmf])  
>thinkplot.Config(xlabel='Number of Kids', ylabel='Frequency')

![kids_pmf_overlay](https://user-images.githubusercontent.com/68957343/102549415-abaafa00-4081-11eb-9f87-893659bc7bbd.png)

Ultimately, we calculate the mean of each distribution and find that once biased the mean increases from 1.02 to 2.40 children.
