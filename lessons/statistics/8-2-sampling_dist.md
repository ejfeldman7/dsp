[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

When we run our code to generate an approximation for a sampling distribution of wait times (lamba as our parameter, L as our statistic) with lambda set to 2, sample size 5, and our simulation set to run 1000 times, we find the following approximations:  

>90% Confidence Interval for L: (1.2704657734500975, 3.892964817911828)
>Root mean square error of L = 0.8709363447062992
>Mean error of L = 0.28241450425424464

Additionally, we can plot our approximate sampling distribution (CDF or PDF), as seen below:

![sampling_dist_appx](https://user-images.githubusercontent.com/68957343/103156191-daa12a00-476b-11eb-9dda-a3aacf500be3.png)

To explore how the sample size impacts the error on L, we can create a plot such as the one shown below. In the plot, it is very clear that our sample size and RMSE have an inverse relationship, and as sample size increases RMSE approaches zero. 

![exp_dist_rmse_chart](https://user-images.githubusercontent.com/68957343/103156240-3bc8fd80-476c-11eb-8338-138d0da95684.png)

