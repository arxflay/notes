CDF - Cumulative distribution function - values that are less or equal to x. Distrubution are easily comparable compared to PMF

![[Pasted image 20260418135917.png]]

**percentile rank** - fraction of values of total values that are smaller than value or equal to observed value. Other definition is values between 0 to 100% offseted by mean. Expressed in percentages. typical formula:
$valuesBelowOrEqualToX/n * 100$

however there more ways to compute percentile rank, for example:
$((CF'+0.5*f)/n)*100$

where CF' are count of values below target value

**Percentile** = value that is pointed by percentile rank. Mapping is not exactly 1 to 1 values (when using classic method, where values equal to are not included) If percentile rank is between 2 values, then for discrete values it will yield to closest one

for example: 1 2 3 4
target value = 2
(2 / 4) * 100 = 25
2 has 50 percentile rank, 50th percentile is value 2.

50th percentile - median = center of distribution

IQR - interquartile range - difference between 75th and 25th percentile (Q3 - Q1)

q1 and q3 could be computed as median of lower half (q1) and median of upper part (q3)

Quantile - divide distribution into ranges (quartile - four groups, deciles - 10 groups, percentile - 100 groups)
