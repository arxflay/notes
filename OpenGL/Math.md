### Interpolations
1. linear interpolation - interpolation between $x_0$ and $x_1$, mapping range of $x_0$-$x_1$ to value range (0.0-1.0), values smaller or bigger than this range are outside of interpolation. 
	$\dfrac{x - x_0}{x_1 - x_0}$

### Analytic geometry

circle: $(x-m)^2 + (y-n)^2 = r^2$ or if S = 0, $x^2 + y^2 = r^2$, technically it's two functions

line slope formula:  $tan(\theta) = \dfrac{y}{x}$, where y or x are either vector or line values 

bounding box: box around object in two variants:
1. two coordinates ($x_1, y_1$) $(x_2, y_2)$ (named xyxy) or single coordinate + width and height 
   ![[Pasted image 20260724115028.png|265]]
2. $c$ center and $a$ positional vector (oriented bounding box)
### Set-builder notation
Set-builder notation is $\set{expression|condition}$, which can be read as return set created by $expression$ restricted by $condition$. If set of number for variable in $expression$ is not specified, it's assumed that set of variable set of $\mathbb{R}$ numbers, otherwise it must be specified in expression block $\set{x \in \mathbb{R}}$ or as condition $\set{x |x \in \mathbb{R}}$. Syntax is similar to python list comprehension 

Examples:
1. $\set{x^2| x \in \mathbb{R}\ and\ x >= 1\ and\  x <= 9}$ returns set of $x^2$ for each x in $\mathbb{R}$ which is less or equal to 1 and bigger or equal to 9
2. $\set{(x, y)| x > 0\ and\ y > 0}$ returns infinite set of vectors, where x and y are $\mathbb{R}$ and bigger than 0
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

#### Binary operation properties
1. **Associativity**: rearranging parenthesis doesn't change result 
   $(a * b) * c = a * (b * c) = a*b*c$
2. **Commutativity**: order of operands doesn't matter $a + b = b + a$
3. **Anti commutativity**: negated result of performed binary operation having reversed order of operands is result of binary operation performed in original order $a \times b = -(b \times a)$
4. **Distributivity**: operation is distributed over binary operation $a * (b + c) = a*b + a*c$

### Functions


### Inqualities:
1. Sum, subtaction, positive division, multiplication, power to both sides doesn't change sign of inequality
2. Multiplication or division by negative value change sign of inquality
3. Solving absolute value depends on value of $a$ and sign
	- Solution doesn't exists if $a < 0$ and inequality is $|expression| < a$ 
	- if $a > 0$ and $expression > a$, then solution is $R$
	- Two inequalities are created if $a > 0$ and inequality is $|expression| < a$  
	  $-a < expression < a$
	- Solve for one if $a > 0$ and inequality is $|expression| > a$  
	  $expression < -a$ or $expression > a$
4. For square root solution is combination of intervals (we have to compute valid intervals for each expression under square root)

## Polynomials

**Conjugate**: expression, where is changed of sign between two terms. Conjugates are useful when we want to remove square root from numerator (top part) or denumerator (bottom part) or simplify equation. Example $\dfrac{5 + \sqrt{x}}{\sqrt{x}} = \dfrac{5 + \sqrt{x}}{\sqrt{x}} * \dfrac{5 - \sqrt{x}}{5-\sqrt{x}} = \dfrac{25 - x^2}{5\sqrt{x} - x^2}$`

**Polynomial division**: similar to long division, where original polynomial is replaced with euclidian division representation. Used where divident is polynomial of equal or lower rank.
How it works:
0. First polynomial must rewritten in form which contains all term of lower ranks, for example $x^3 + 2 = x^2 + x^3 + 0x^2 + 0x + 2$
1. Divide highiest term with lower term
2. Write result of division top
3. Subtract from polynomial result of product of division from step $1.$ and divident polynomial
4. Repeat step 1
5. If divident term is highier then remaining term, then remaining polynomial is remainder. Result is written as

Example $\dfrac{x^3 + x^2 - 5}{x^2 - 2x + 3}$
![[Pasted image 20260829000544.png|383]]
## Unordered

**Euclidian division** is division with remainder. Using euclidian division, we can represent each divisior as quatient multiplied with divident and summed with remainder: $a = nq + r$, where n is divident, q is quotient and r is remainder.

**GCD**: since common divisor of $A$ is equal to common divisor of $A -B$, then we can subtract B until B is equal to A. If $B$ is bigger than $A$, then we swap $A$ with $B$. Subtracting B from A is slow, we can use another method using division with remainer. Principle is similar, check if remainder until $A\ mod\ B$ is zero, otherwise set A as B and B as remainder. It works, because it essentialy same as algorithm with $A - B$

**Pascal triangle**: Triangle that forms rows, where each entry as sum of two immediately above. Triangle starts with $1$. Entries from pascal triangle form combination $\begin{pmatrix} n \\ k \end{pmatrix}$, where $n$ is number of row from 1 and $k$ is entry.
![[Pasted image 20260830132931.png|411]]

**Monomial**: Polynomial, that contains only single term, e.g $x^2$, $-ax$ and etc
**Binomial**: Polynomial, that is sum of two terms, where each term is monomial 
**Binomial theorem**: Expansion of powers of binomials $(x + y)^n$ is equal to $\sum_{k=0}^n{ax^{n - k}y^k}$ where $a$ is coefficient (called bionomial coefficient) from pascal triangle also defined as combination $\begin{pmatrix} n \\ k \end{pmatrix}$
**Binominal difference factorization**: $x^{n+1} - y^{n+1} = (x-y) * (\sum_{k=0}^nx^ky^{n-k})$, for example $x^3 - y^3 = x^{2 + 1} - y^{2 + 1} = (x - y)*(x^0*y^2 + x^1*y^1 + y^0*x^2) = (x - y)*(y^2 + xy + x^2)$

**Cusp**: curve, that separates into two branches having tangent on the same point for both branches. Example: $\sqrt{|{x}|}$
![[Pasted image 20260830111628.png]]