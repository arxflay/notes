
### Interpolations
1. linear interpolation - interpolation between $x_0$ and $x_1$, mapping range of $x_0$-$x_1$ to value range (0.0-1.0), values smaller or bigger than this range are outside of interpolation. 
	$\dfrac{x - x_0}{x_1 - x_0}$

### Analytic geometry

circle: $(x-m)^2 + (y-n)^2 = r^2$ or if S = 0, $x^2 + y^2 = r^2$

line slope formula:  $tan(\theta) = \dfrac{y}{x}$, where y or x are either vector or line values 

bounding box: box around object in two variants:
1. two coordinates ($x_1, y_1$) $(x_2, y_2)$ (named xyxy) or single coordinate + width and height 
   ![[Pasted image 20260724115028.png|265]]
2. $c$ center and $a$ positional vector (oriented bounding box)

### Number theory

discrete - countable numbers, for example 1, 2, 3, 4 or set of points or function like $floor(x)$ on open interval 
continuous - uncountable numbers, function with no abrupt changes of value ($sin$, $log$) or even $floor(x)$ if interval is $(x, x+1)$. Technically endless amount of values

Natural number ($\mathbb{N}$) - set of whole, positive numbers excluding 0 (except if denoted as $\mathbb{N}_0$)
Integers ($\mathbb{Z}$) - set of whole, positive and negative numbers including 0 (except if denoted as $\mathbb{Z}^+$)
Rational numbers ($\mathbb{Q}$) - set of numbers represented by fraction
Real numbers ($\mathbb{R}$) - set of numbers that can't be represented by fraction (endless sequence like $\pi$)

Each set of numbers is subset of previous set (ex: natural numbers is subset of integers)

### Group Theory

Additive identity - one element in group that will not change value of summand, $y + x = y$, for example 0 is additive identity for $\mathbb{R}$, $10 + 0 = 10$

Multiplicative identity - one element in group that will not change value of multiplicand, $y * x = y$, for example 1 is multiplicative identity for $\mathbb{R}$, $10 * 1 = 10$

Additive inverse - element in group that is inverse to number, which when added results to 0, $y + (-y) = 0$, for example 10 + (-10) = 0

### Functions
Norm - any function that defines distance of vector from origin with properties:
* Is zero only in origin 
* Must obey triangle inequality $f(x + y) <= x + y$ 
* homogeneous - $f(s*x) = s * f(x)$, 
* (optionally) non negative

common types:
* P-norm - p norm is defined as ($\sum{x_i^p})^{1/p}$
* Euclidean norm (2-norm, geometric length) - length of vector defined by $\sqrt{\sum{x_i^2}}$. Euclidean norm is subset of p norm. Proof of homogeneity - s = 2, $\vec{v} = (5, 2)$, $\sqrt{(5*2)^2 + (2*2)^2} = 2 * \sqrt{5^2 + 2^2}$, $\sqrt{10^2 + 4^2} = 2 * \sqrt{25 + 4}$, $\sqrt{100 + 16} = 2 * \sqrt{29}$, $\sqrt{116} = \sqrt{4 * 29}$, $\sqrt{116} = \sqrt{116}$
* taxicab norm - $\sum{x_i}$, it measures distance like if we travel to x and then to y instead of shortest path via euclidean norm, for example $a = (1,1)$, length is $1 + 1$
* chebyshev norm (infinity norm) - largest absolute value in vector





