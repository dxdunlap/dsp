[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

>> For upper bound equal to log_upper=6.0 or 1 million dollars: 

Mean : 74278.70753118733

Median: 51226.45447894046

Skewness: 4.949920244429583

PearsonMedianSkewness: 0.7361258019141782

CDF: 0.660005879566872, which means 66% of the population make less than the mean. 



For upper bound equal to log_upper=7.0 or 10 million dollars:



```python
log_sample = InterpolateSample(income_df, log_upper=7.0)
sample = np.power(10, log_sample)
cdf = thinkstats2.Cdf(sample)

```



```python
Mean(sample), Median(sample)
```

(124267.39722164685, 51226.45447894046)



```python
Skewness(sample), PearsonMedianSkewness(sample)
```

(11.603690267537793, 0.39156450927742087)



```python 
cdf.Prob(Mean(sample))
```

0.8565630665207663 or 86% of the population make less than the mean. 

Focusing on the more robust statistic -Pearson's median skewness- we see that the median skewness gets smaller as the upper bound gets larger. 
