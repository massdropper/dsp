[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

from __future__ import print_function, division


import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot

list1 = np.random.random(1000)
pmf = thinkstats2.Pmf(list1)
thinkplot.Pmf(pmf)
thinkplot.Show(xlabel='number',ylabel='pmf',axis=[0,1,0,.01])
cdf = thinkstats2.Cdf(list1)
thinkplot.Cdf(cdf)
thinkplot.Show(xlabel='number', ylabel='cdf')

Yes, the distribution is uniform.  The PMF showed that each number had an equal probability.  The CDF showed a straight line, which also signifies a uniform distribution
