[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

### analysis
The number of men between 5'10 inches and 6'1 inches tall is `34%`.
### code
```
import scipy.stats
import brfss

df = brfss.ReadBrfss()
heights= df.htm3.dropna()
m_heights = heights[df.sex == 1]

m_height_mu = 178 
m_height_sigma = 7.7

f_height_mu = 163
f_height_sigma = 7.3

dist = scipy.stats.norm(loc=m_height_mu, scale=m_height_sigma)
min_cm = 177.8
max_cm = 185.4
low = dist.cdf(177.8)   
high = dist.cdf(185.4)   
print ((high-low)*100)
```