[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)
n the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters µ = 178 cm and σ = 7.7 cm for men, and µ = 163 cm and σ = 7.3 cm for women.

In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see http://bluemancasting.com). What percentage of the U.S. male population is in this range? Hint: use `scipy.stats.norm.cdf`.

`scipy.stats` contains objects that represent analytic distributions

import scipy.stats

For example <tt>scipy.stats.norm</tt> represents a normal distribution.

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)
type(dist)

A "frozen random variable" can compute its mean and standard deviation.

dist.mean(), dist.std()

It can also evaluate its CDF.  How many people are more than one standard deviation below the mean?  About 16%

dist.cdf(mu-sigma)

How many people are between 5'10" and 6'1"?


>>tallest_blue = dist.cdf(185.42)
shortest_blue = dist.cdf(177.8)
tallest_blue -shortest_blue

>>'''About 34.27% of adult ment are between 5'10" and thus eligible to be
apart of the Blue Man Group.'''
'''I this is still a bit unclear to me; I only got the answer fast enough 
since there was an example right above where I submitted my answer.'''
