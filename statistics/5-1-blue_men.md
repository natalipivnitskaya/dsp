[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

Libraries
``` python
import scipy.stats
```

Parameters

``` python
mu = 178
sigma = 7.7
```

Distribution with givan parameters
``` python
dist = scipy.stats.norm(loc = mu, scale = sigma)
type(dist)
```

Solution

``` python
low = dist.cdf(177.8)    # 5'10"
high = dist.cdf(185.4)   # 6'1"
print('Percentage of people between 177.8 and 185.4 height is {}%.format(high-low))
```
