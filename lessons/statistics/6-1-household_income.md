[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

When we compute the mean, median, skewness, and Pearson's skewness for the interpolated sample of housing data using our upper bound of 10<sup>6,</sup>, we find the following values:   

The mean of our sample is: 74278.70753118733  
The median of our sample is: 51226.45447894046  
The skewness of our sample is: 4.949920244429583  
The Pearson's skewness for our sample is: 0.7361258019141782  
In our sample 66.00% of households fall below the mean   

When we repeat the above calculations with an increased upper bound of 10<sup>7,</sup>, we find the following:  

The mean of our sample is: 124267.39722164685    
The median of our sample is: 51226.45447894046    
The skewness of our sample is: 11.603690267537793    
The Pearson's skewness for our sample is: 0.39156450927742087    
In our sample 85.66% of households fall below the mean    

Comparing these two, we can see that by increasing the upper bound on our data, our mean is increased but our median stays the same. That makes sense, as we haven't added more points above the median, we've only allowed them to take on higher values. This then makes our distribution skew further right, as we see in the increased value of skewness. Interestingly, Pearson's skewness drops. This shows us that the calculation for that value for Pearson's skewness is impacted by both the increase in the mean and the increase in the standard deviation, with the standard deviation ultimately having a greater impact. 
