[Think Stats Chapter 8 Exercise 3](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77)

---

In this exercise we create two functions, the first takes in a value, lambda, which stands for the average goals scored in a hockey or soccer game, and simulates a game to estimate how many goals were scored. We then create a second function which runs this simulation many times and logs the values of lambda. We can then use our estimates in comparison to the seed value of lamda to compute our RMSE and check for bias in our estimate. 

When first run for lambda set to 3 goals over 100 games, we generated the following estimates and errors:  
>Average number of goals scored was: 2.972116276132484  
>rmse lambda 0.29246146622168606  
>mean error lambda -0.027883723867516322  
>Our 90% confidence interval is (2.5836176577246146, 3.462944304944023)  

The above simulation yielded the following PDF and CDF:

![goals_scored_dfs](https://user-images.githubusercontent.com/68957343/103230348-d48d8380-48fa-11eb-8f1e-4c6c720c22e3.png)

When we repeat this simulation for increasing number of games, we can see that our RMSE approaches zero, which tell us that our simulation is producing an unbiased estimator for lambda. When we repeat this simulation for increasing values of lambda, but holding the number of games constant, we can see our RMSE increase and our confidence interval widen. This makes sense in the context of a soccer/hockey game. If the average number of goals scored was one, there is not an expectation for much variability in number of goals scored from game to game. If the average number of goals scored was 15, then the wait time between goals would be considerably shorter and we would expect more variability in the number of goals scored from game to game. 

---
