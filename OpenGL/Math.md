
### Linear algebra

#### Linear combination 
Linear combinations is defined as sum of terms, where each term is multiplied by constant (some number). Term could be either variable, number or vector. Depending on context, linear combination is either the value or expression. Examples:

1. $2x + y$ is a linear combination $ax + by$ where constant $a$ and $b$ are constant, $x$ and $y$ are terms
2. $f(a) = 10a$, where $10$ is a term and $a$ is a constant
3. $f(x) = x * cos(\theta)$, where $x$ is a constant and $cos(\theta)$ is term
4. Vector space R^2, where i is (1, 0) and k (0, 1), thus any vector in R^2 space an be expressed as combination of two vectors (ai + bk), for example (1, 5) could be expressed as 1i + 5k
5. Combination of polynomials, p1: $x$, p2: $x^2 - 20$, p3: $x^3$, which can be expressed as $ax + b(x^2 - 20) + cx^3$

#### Linear dependence 
Linear dependence means that at least one term in the set can be expressed as a linear combination of the other terms. Other way to define it is that exists constants (which are not all zero) that will make linear combination equal to 0.

Example of linear dependence:
	Having vectors $p = (0, 1)$, $q = (1, 0)$, $r = (1/\sqrt{2}, 1/\sqrt{2})$, there exists combination $p + q + r = 0$ such as $q * (1/\sqrt{2}) + p * (1/\sqrt{2}) + -1 * r = 0$ and there exists combination of p and q that is equal to r, $q * 1/\sqrt{2} + p * 1/\sqrt{2} = r$ 

Example of linear independence:
	Having vectors $p = (0, 1)$, $q = (1, 0)$ there are no constants, that will make linear combination equal to 0 or equal to other term. Other example is $(-1,1)$ and $(1,1)$ or $(1, -1)$ and $(1,1)$

#### Span and basis

^fe779d

Spanning set - subset of vectors S in vector space V, by which we can express all elements in that space via linear combination, $span(S) = V$. Spanning set doesn't necessary have to be finite or linear independent

Linear span (span) - set formed by linear combination of spanning set. Span is subspace of vector space V when not all elements can be expressed by spanning set. For example, spanning set S $\{(1,0)\}$ and vector space $\mathbb{R}^2$, S is subspace of $\mathbb{R}^2$ because it's can't represent all elements in $\mathbb{R}^2$

Basis - **spanning set of linear independent elements** of vector space V. For example, vector space $\mathbb{R}^3$ with canonical basis is $i=(1,0,0)$, $j=(0,1,0)$, $k=(0,0,1)$. Poorly chosen basis will span only subset of vector space.  ^bd3fba

Rank - number of dimensions that can be described by basis. Rank is named full rank if it's possible to represent all elements in vector space by linear combination of basis

Orthogonal basis - each vector is perpendicular to each other or in other words, for each component of vector in vector space V we need only one vector from spanning set. Example is ($i=(1,0)$, $j=(0,1)$)

Orthonormal basis - all vectors in spanning set have unit length


### Matrices

for matrix multiplication to work, first matrix column count must equal to second matrix row count. Result of matrix multiplication has row count of first matrix and column count of second matrix ($m_1n_1*m_2n_2 = m_1n_2$, where m = rows, n = columns)
$m1 = 1 x 2$
$m2 = 2 x 3$
$m_{1,2} = 1x3$
$\begin{bmatrix} a_1 & a_2  \end{bmatrix} * \begin{bmatrix} b_1 & b_2 & b_3\\ b_4  & b_5 & b_6 \end{bmatrix} = \begin{bmatrix} a_1 * b_1 + a_2 * b_4 & a_1 * b_2 + a_2 * b_5 & a_1 * b_3 + a_2 * b_6   \end{bmatrix}$ 

### Interpolations
1. linear interpolation - interpolation between x0 and x1, mapping range of x0-x1 to value range (0.0-1.0), values smaller or bigger than this range are outside of interpolation. 
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

### Rotation matrix

#### Rotation matrix 2d

Formulae: $\begin{bmatrix} cos(\theta) & -sin(\theta) \\ sin(\theta) & cos(\theta)   \end{bmatrix}$

Rotation matrix is derived from sum of angle with hypotenuse of length 1
1. for x: $cos(\alpha + \beta) = cos(\alpha)cos(\beta) - sin(\alpha)sin(\beta)$, $sin(\alpha)$ = y (because $sin(\alpha) = opposite/hypotenuse$ and hypotenuse is 1, so $sin(\alpha) = opposite$) and $cos(\alpha) = x$, so $cos(\alpha + \beta) = x*cos(\beta) - y*sin(\beta)$
2. for y: $sin(\alpha + \beta) = sin(\alpha)cos(\beta) + sin(\beta)cos(\alpha)$, $sin(\alpha)$ = y (because $sin(\alpha) = opposite/hypotenuse$ and hypotenuse is 1, so $sin(\alpha) = opposite$) and $cos(\alpha) = x$, $sin(\alpha + \beta) = y*cos(\beta) + x*sin(\beta)$ 

#### Rotation matrix 3D

Similar to 2d matrix, but rotation is along axis. Value of point on this axis will not be changed. Matrix is slightly different z
