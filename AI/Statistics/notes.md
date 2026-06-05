Empirical distribution - distribution created from values from dataset, not continuous 
Analytical distribution - distribution expressed as mathematical function, could be continuous  

Logarithmic scale:
scale of power of base (base can be different). Amount of segments is equal to base example and value is not linear:

b = 10

log(0.1) is -1 (10^-1)

0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1

log(1) is 0 (10^0)

then after 1
1 2 3 4 5 6 7 8 9 10

log(10) is 1 (10^1)

then after 10
10 20 30 40 50 60 70 80 90 100

log(100) is 2

space between them is always the same, for example, log(2) will is ~0.3 and log(20) is equal to 1.3


b 2

2 3 4 = 1, ~1.58, 2
4 6 8 = 2, ~2.58, 3
8 12 16

semi log plot 
- only one axis is log scaled
![[semi_log_1.png|420]]

proof = $y = 2^x$ = $log_{2}y = x$
for $f(x) = 2^x$

$log_2(4) = x = 2$
$y = f(2) = 2^2 = 4$


log-log plot
* all axis are log scaled
![[log-log.png|437]]

(e) euler number = endless sequence of  $\displaystyle\sum_{n=1} ^{\infty}\frac{1}{n!} = 1 + \frac{1}{1 * 2}\ ...$
defined as 2.71


Exponential distribution (CDF)

exponential CDF is defined as $e^{\lambda x}$, where $\lambda$ determines shape
![[Pasted image 20260419212624.png|391]]
CCDF (Complementary CDF) computed as $1 - CDF(x)$ with log scale on Y is used to test if exponential distibution fits to dataset. If distribution is a straight line, then distribution is exponential. It works, because 
$y = e^{\lambda x};\ \ log({y}) = \lambda x$, so exponential function become is straight line with slope $\lambda$ on y log scale

mean of exponential distribution is $1/\lambda$

Normal distribution (CDF)

Normal doesn't mean normal, it mean typical distribution (many things tend to look like a normal distribution)

normal distribution CDF is a sigmoid function (looks like S) and it actually resembles bell shape progression. Normal distribution CDF represented by parameters mean (mu) and std deviation (sigma). Normal distribution CDF with mu = 0 and s = 1 is called standard normal distribution. Normal distribution CDF is defined as integral (because it doesn't have closed form) 


![[Pasted image 20260419212805.png|453]]

Normal probability plot

Transformations like in exponential distribution can't be used to test if normal distribution fits to dataset. Instead normal probability plot is used with these steps

1. Select sample from dataset and sort it
2. Select same amount of values from standard normal distribution function
3. Plot both and compare