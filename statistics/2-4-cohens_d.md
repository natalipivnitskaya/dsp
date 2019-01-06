[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

```python
import numpy as np
import scipy.stats
%matplotlib inline
%config IPCompleter.greedy=True
```


```python
def CohenEffectSize(group1, group2):
     """Computes Cohen's effect size for two groups.
     
     group1: Series or DataFrame
     group2: Series or DataFrame
     
     returns: float if the arguments are Series;
              Series if the arguments are DataFrames
     """
     diff = group1.mean() - group2.mean()
 
     var1 = group1.var()
     var2 = group2.var()
     n1, n2 = len(group1), len(group2)
 
     pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
     d = diff / np.sqrt(pooled_var)
     return d
 ```

 calculation of Cohen Effect Size for two groups (first babies, other babies) on their birth weight.

 ```python
 preg = nsfg.ReadFemPreg()
 live = preg[preg.outcome == 1]
 
 firsts = live[live.birthord == 1]
 others = live[live.birthord != 1]
 c_effect_weight = CohenEffectSize(firsts['totalwgt_lb'],others['totalwgt_lb'])
 c_effect_weight
 ```

Conclution: There is no significant difference between determined groups in tjei birth weight
