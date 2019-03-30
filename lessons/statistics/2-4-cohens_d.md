Using the variable `totalwgt_lb`, investigate whether first babies are lighter or heavier than others. 

Compute Cohen’s effect size to quantify the difference between the groups.  How does it compare to the difference in pregnancy length?

# Solution goes here
>>CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)

# Solution goes here

'''The first pregnancy length tends to be fractionally shorter.
Based on the dataset provided, it would be very hard to conclude that first
pregnancies are longer.'''

For the next few exercises, we'll load the respondent file:

>>resp = nsfg.ReadFemResp()

