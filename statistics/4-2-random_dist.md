[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

#Ex 1

###analysis  
My birth weight was in the `89.48` percentile.
![](https://raw.githubusercontent.com/jblinder/dsp/master/statistics/figs/rnd2.png)
###code
```
import numpy as np
import thinkstats2
import thinkplot
import nsfg

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

cdf = thinkstats2.Cdf(others.totalwgt_lb,label='preg weight')
percentile_rank = cdf.PercentileRank(8.9)
print(percentile_rank)
thinkplot.Cdf(cdf)
thinkplot.Vlines(8.9,0,1,linestyles='dotted',label='me')
thinkplot.Show(xlabel='lbs',ylabel='CDF')
```


#Ex 2
### analysis
The PMF shows lines for a random value and gaps for a value that was not generated. This option isn't great because every number has an equal probability of being selected.

The CDF shows a roughly linear line, indicating the the distribution is uniform.

![](https://raw.githubusercontent.com/jblinder/dsp/master/statistics/figs/rnd1.png)

![](https://raw.githubusercontent.com/jblinder/dsp/master/statistics/figs/rnd3.png)


### code
```
import numpy as np
import thinkstats2
import thinkplot
import nsfg

n = np.random.random(1000)

pmf = thinkstats2.Pmf(n)
thinkplot.Pmf(pmf,linewidth=.5)
thinkplot.Config(xlabel='random num', ylabel='PMF')

cdf = thinkstats2.Cdf(n)
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel='random num', ylabel='CDF')
```