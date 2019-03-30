[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Using the variable `totalwgt_lb`, investigate whether first babies are lighter or heavier than others. 

Compute Cohen’s effect size to quantify the difference between the groups.  How does it compare to the difference in pregnancy length?

# Solution goes here
CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)

# Solution goes here

'''The first pregnancy length tends to be fractionally shorter.
Based on the dataset provided, it would be very hard to conclude that first
pregnancies are longer.'''

For the next few exercises, we'll load the respondent file:

resp = nsfg.ReadFemResp()

'''For this following histograms, I used the three lines used in the lesson
with the proper modifications.'''

Make a histogram of <tt>totincr</tt> the total income for the respondent's family.  To interpret the codes see the [codebook](http://www.icpsr.umich.edu/nsfg6/Controller?displayPage=labelDetails&fileCode=FEM&section=R&subSec=7876&srtLabel=607543).

# Solution goes here
hist = thinkstats2.Hist(resp.totincr)
thinkplot.Hist(hist, label='totincr')
thinkplot.Config(xlabel='income (category)', ylabel='Count')

Make a histogram of <tt>age_r</tt>, the respondent's age at the time of interview.

# Solution goes here
hist = thinkstats2.Hist(resp.age_r)
thinkplot.Hist(hist, label='age')
thinkplot.Config(xlabel='age(years)', ylabel='count')

Make a histogram of <tt>numfmhh</tt>, the number of people in the respondent's household.

# Solution goes here
hist = thinkstats2.Hist(resp.numfmhh,)
thinkplot.Hist(hist, label='numfmhh')
thinkplot.Config(xlabel='household members', ylabel='count')

Make a histogram of <tt>parity</tt>, the number of children borne by the respondent.  How would you describe this distribution?

# Solution goes here
hist = thinkstats2.Hist(resp.parity)
thinkplot.Hist(hist, label='parity')
thinkplot.Config(xlabel='# of children borne', ylabel='count')

Use Hist.Largest to find the largest values of <tt>parity</tt>.

# Solution goes here
hist.Largest()

Let's investigate whether people with higher income have higher parity.  Keep in mind that in this study, we are observing different people at different times during their lives, so this data is not the best choice for answering this question.  But for now let's take it at face value.

Use <tt>totincr</tt> to select the respondents with the highest income (level 14).  Plot the histogram of <tt>parity</tt> for just the high income respondents.

# Solution goes here
highest_income = resp[resp.totincr == 14]
hist = thinkstats2.Hist(highest_income.parity)
thinkplot.Hist(hist, label='Highest Income Parity')
thinkplot.Config(xlabel='parity', ylabel='count')

Find the largest parities for high income respondents.

# Solution goes here
hist.Largest()

Compare the mean <tt>parity</tt> for high income respondents and others.

# Solution goes here
other = resp[resp.totincr < 14]
highest_income.parity.mean(), other.parity.mean()

Compute the Cohen effect size for this difference.  How does it compare with the difference in pregnancy length for first babies and others?

# Solution goes here
CohenEffectSize(highest_income.parity, other.parity)
