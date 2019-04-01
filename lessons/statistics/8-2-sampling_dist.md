[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

>> Sample size, n = 10

```python
def SimulateSample(lam=2, n=10, iters=1000):
    
    estimates = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        lamhat = 1.0 / np.mean(xs)
        estimates.append(lamhat)

    stderr = RMSE(estimates, lam)
    print('standard error', stderr)

    cdf = thinkstats2.Cdf(estimates)
    ci = cdf.Percentile(5), cdf.Percentile(95)
    print('confidence interval', ci)

SimulateSample()
```



```
standard error 0.8992468292976267
confidence interval (1.2827691993726555, 3.8104295236798027)
```

sample size, n= 150

```python
def SimulateSample(lam=2, n=150, iters=1000):
    
    estimates = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        lamhat = 1.0 / np.mean(xs)
        estimates.append(lamhat)

    stderr = RMSE(estimates, lam)
    print('standard error', stderr)

    cdf = thinkstats2.Cdf(estimates)
    ci = cdf.Percentile(5), cdf.Percentile(95)
    print('confidence interval', ci)

SimulateSample()
```

```
standard error 0.16875765563465242
confidence interval (1.7671550493268935, 2.3151202907499204)
```



sample size, n= 900

```python
def SimulateSample(lam=2, n=900, iters=1000):
    
    estimates = []
    for _ in range(iters):
        xs = np.random.exponential(1.0/lam, n)
        lamhat = 1.0 / np.mean(xs)
        estimates.append(lamhat)

    stderr = RMSE(estimates, lam)
    print('standard error', stderr)

    cdf = thinkstats2.Cdf(estimates)
    ci = cdf.Percentile(5), cdf.Percentile(95)
    print('confidence interval', ci)

SimulateSample()
```

```
standard error 0.06636983240515502
confidence interval (1.8915185242466368, 2.111403703811913)
```



As sample size increases, standard error and the width of the confidence interval decreases (ci). 
