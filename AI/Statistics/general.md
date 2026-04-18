
Statistic - study that gives the meaning to data and is interconnected with probability

Selection bias - result are affected by specific group that is selected. For example which parts of plane are more likely to be hit by bullets? Collected data will contain planes that are hit by someone but not the planes that are destroyed, that are thus biased to planes that survived hits

Confirmation bias - people that believe in claim are more likely to provide confirming examples and people who don't believe in claim are more likely to provide counter examples

Cross-sectional study - taking snapshot of a group
Longitudinal study - repeatedly observation of same group over time

People who are part ot

Codebook - Description of all fields (encoding) and count
Code - field (Part of raw data)
Recode - field (Based on code)

Transformation - prepare data for processing. Data cleaning is a transformation.
Data cleaning - remove unnecessary parts and errors, for example remove rows with NaN value

defaultdict - dict with factory, for example dict that by default create list of items


Statistical distribution - function that shows values and how often values appear

Summary statistics asks this questions: do values have tendency to shift to center of cluster? Are there more than one cluster (data subset) ? Are there more modes? How much values are scattered (spread)? How quickly probability drops (tails) 

Variance (rozptyl) - spread of distribution (squared deviation), the lower value, the less spread

Variance formula:
S^2 = 1/n * sum((x_i - mean)^2)

x_i - mean = deviation from mean
(x_i - mean)^2 = magnitude of mean (like vector magnitude but with square root)

Square root of variance is standard deviation (směrodatna odchylka)

std dev is square root of variance = sqrt(variance)

Effect size - difference between groups
bigger than 0.5 - large effect
0 to 0.20 - small effect
0.20 to 0.50 - medium effect

Ways to calculate difference:
1. difference of means
2. cohen's d (difference of variability), result in std deviations

Cohen's d:
$d = (x_1mean - x_2mean) / s$
where s is pooled standard deviation
$s^2 = (x_1n * x_1var + x_2n * x_2var) / (n_1n + n_2n)$

alternatively cohen's d can be computed this way:
$d = (x_1mean - x_2mean) / s$
where
$s = (x_1std + x_2std) / 2$

- [ ] What is pooled standard deviation ?

