[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

from __future__ import print_function, division


import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot

resp = nsfg.ReadFemResp()
pmf = thinkstats2.Pmf(resp.numkdhh, label = 'actual')

def biaspmf(pmf, label):
    new_pmf = pmf.Copy(label = label)
    
    for x,p in pmf.Items():
        new_pmf.Mult(x,x)
    new_pmf.Normalize()
    return new_pmf

biased_pmf = biaspmf(pmf, label = 'biased')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Show(xlabel='number of children', ylabel = 'PMF')
print(pmf.Mean())
print(biased_pmf.Mean())
