[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

```
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
   
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

CohenEffectSize(firsts.totalwgt_lb,others.totalwgt_lb)
```

The Cohen's d value for `totalwgt_lb` is `-0.088672927072602`. (I believe the value is negative because the first mean is smaller than the second mean.)

The Cohen's d value for `prglngth` is `0.028879044654449883`.

The Cohen's d for the `totalwgt_lb` is greater (8%) than `prglngth` (2%) because there is more variability between the total lb weight for the first births compared to the other births.