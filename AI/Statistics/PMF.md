PMF (probability mass function) - function that maps probability to each discrete value. For example \[2, 2, 4, 5, 6], 2 will have probability 0.4, 4 = 0.2, 5=0.2, 6=0.2

Normalization = converting frequencies to probability by dividing values by total count

Biased result = result affected (overshadowed) by value
Unbiasing data - divide by 1/value

![[Pasted image 20260411161817.png|533]]

piecewise function - function that is separated to multiple intervals, e.g  changes depending on interval value

![[Pasted image 20260411144107.png]]

step function - part of piecewise functions, but changes look like steps

![[step_fn_example.png]]




mean of pmf = $\sum p_i x_i$ where p is probability and x is value
example with 10, 20, 30, 10:
	count = 4
	counted = 10:2, 20:1, 30:1
	mean = $\overline x = 1/n * \sum x_i = (10 + 20 + 30 + 10) / 4 = 70 / 4 = 17,5$
	pmf = $10:(2/4), 20:(1/4), 30:(1/4) = 10:0.5, 20:0.25, 30:0.25$
	pmf_mean = $0.5 * 10 + 20 * 0.25 + 30 * 0.25 = 5 + 7.5 + 5 = 17,5$
	$s^2 = \sum p_i * (x_i - \overline x)^2$
	$s^2 = 0.5 * (10 - 17.5)^2 + 0.25 * (20 - 17.5)^2 + 0.25 * (30 - 17.5)^2$ = 68.75
	s = 8.29

PMF (Pravděpodobnostní funkce) is good for small variety of values, otherwise data will hard to interpret