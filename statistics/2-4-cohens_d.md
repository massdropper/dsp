[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> 
import nsfg
import math

df = nsfg.ReadFemPreg()
live = df[df.outcome == 1]
nsfg.CleanFemPreg(live)
live2 = live[live.totalwgt_lb.notnull()]
firstgroup = live2[live2.birthord ==1]
secondgroup = live2[live2.birthord != 1]

first = firstgroup.totalwgt_lb
second = secondgroup.totalwgt_lb

def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d

CohenEffectSize(first,second)
-0.08867236333202932

This effect is about 3 times stronger than the difference in pregnancy length, although still quite small
