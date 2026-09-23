### Interpolations
1. linear interpolation - interpolation between $x_0$ and $x_1$, mapping the range of $x_0$-$x_1$ to the value range (0.0-1.0); values smaller or bigger than this range are outside the interpolation. 
	$\dfrac{x - x_0}{x_1 - x_0}$

### Analytic geometry

circle: $(x-m)^2 + (y-n)^2 = r^2$ or if S = 0, $x^2 + y^2 = r^2$, technically it's two functions

line slope formula:  $tan(\theta) = \dfrac{y}{x}$, where y or x are either vector or line values 

bounding box: a box around an object in two variants:
1. two coordinates ($x_1, y_1$) $(x_2, y_2)$ (named xyxy) or a single coordinate + width and height 
   ![[Pasted image 20260724115028.png|265]]
2. $c$ center and $a$ positional vector (oriented bounding box)
### Set-builder notation
Set-builder notation is $\set{expression|condition}$, which can be read as the returned set created by $expression$ restricted by $condition$. If the set of numbers for a variable in $expression$ is not specified, it's assumed that the set of variables is the set of $\mathbb{R}$ numbers; otherwise, it must be specified in the expression block $\set{x \in \mathbb{R}}$ or as a condition $\set{x |x \in \mathbb{R}}$. The syntax is similar to Python list comprehension 

Examples:
1. $\set{x^2| x \in \mathbb{R}\ and\ x >= 1\ and\  x <= 9}$ returns the set of $x^2$ for each x in $\mathbb{R}$ which is less than or equal to 1 and bigger than or equal to 9
2. $\set{(x, y)| x > 0\ and\ y > 0}$ returns an infinite set of vectors, where x and y are $\mathbb{R}$ and bigger than 0
### Number theory

discrete - countable numbers, for example, 1, 2, 3, 4, or a set of points or a function like $floor(x)$ on an open interval 
continuous - uncountable numbers, a function with no abrupt changes in value ($sin$, $log$), or even $floor(x)$ if the interval is $(x, x+1)$. Technically, an endless number of values

Natural numbers ($\mathbb{N}$) - the set of whole, positive numbers excluding 0 (except if denoted as $\mathbb{N}_0$)
Integers ($\mathbb{Z}$) - the set of whole, positive and negative numbers including 0 (except if denoted as $\mathbb{Z}^+$)
Rational numbers ($\mathbb{Q}$) - the set of numbers represented by a fraction
Real numbers ($\mathbb{R}$) - the set of numbers that can't be represented by a fraction (an endless sequence like $\pi$)

Each set of numbers is a subset of the previous set (ex: natural numbers are a subset of integers)

### Group Theory

Additive identity - one element in a group that will not change the value of the summand, $y + x = y$; for example, 0 is the additive identity for $\mathbb{R}$, $10 + 0 = 10$

Multiplicative identity - one element in a group that will not change the value of the multiplicand, $y * x = y$; for example, 1 is the multiplicative identity for $\mathbb{R}$, $10 * 1 = 10$

Additive inverse - an element in a group that is the inverse of a number, which, when added, results in 0, $y + (-y) = 0$; for example, 10 + (-10) = 0

#### Binary operation properties
1. **Associativity**: rearranging parentheses doesn't change the result 
   $(a * b) * c = a * (b * c) = a*b*c$
2. **Commutativity**: order of operands doesn't matter $a + b = b + a$
3. **Anticommutativity**: the negated result of a performed binary operation having the reversed order of operands is the result of the binary operation performed in the original order $a \times b = -(b \times a)$
4. **Distributivity**: operation is distributed over binary operation $a * (b + c) = a*b + a*c$

### Functions


### Inequalities:
1. A sum, subtraction, positive division, multiplication, or power applied to both sides doesn't change the sign of the inequality
2. Multiplication or division by a negative value changes the sign of the inequality
3. Solving absolute value depends on value of $a$ and sign
	- A solution doesn't exist if $a < 0$ and the inequality is $|expression| < a$ 
	- if $a > 0$ and $expression > a$, then the solution is $R$
	- Two inequalities are created if $a > 0$ and the inequality is $|expression| < a$  
	  $-a < expression < a$
	- Solve for one if $a > 0$ and the inequality is $|expression| > a$  
	  $expression < -a$ or $expression > a$
4. For a square root, the solution is a combination of intervals (we have to compute valid intervals for each expression under the square root)

## Polynomials

**Conjugate**: an expression where the sign between two terms is changed. Conjugates are useful when we want to remove a square root from the numerator (top part) or denominator (bottom part) or simplify an equation. Example: $\dfrac{5 + \sqrt{x}}{\sqrt{x}} = \dfrac{5 + \sqrt{x}}{\sqrt{x}} * \dfrac{5 - \sqrt{x}}{5-\sqrt{x}} = \dfrac{25 - x^2}{5\sqrt{x} - x^2}$`

**Polynomial division**: similar to long division, where the original polynomial is replaced with a Euclidean division representation. Used where the dividend is a polynomial of equal or lower rank.
How it works:
0. The first polynomial must be rewritten in a form which contains all terms of lower ranks, for example, $x^3 + 2 = x^2 + x^3 + 0x^2 + 0x + 2$
1. Divide the highest term by the lower term
2. Write the result of the division on top
3. Subtract from the polynomial the result of the product of the division from step $1.$ and the dividend polynomial
4. Repeat step 1
5. If the dividend term is higher than the remaining term, then the remaining polynomial is the remainder. The result is written as

Example $\dfrac{x^3 + x^2 - 5}{x^2 - 2x + 3}$
![[Pasted image 20260829000544.png|383]]
## Unordered

**Euclidean division** is division with a remainder. Using Euclidean division, we can represent each divisor as the quotient multiplied by the dividend and summed with the remainder: $a = nq + r$, where n is the dividend, q is the quotient, and r is the remainder.

**GCD**: since the common divisor of $A$ is equal to the common divisor of $A -B$, we can subtract B until B is equal to A. If $B$ is bigger than $A$, then we swap $A$ with $B$. Subtracting B from A is slow, so we can use another method using division with a remainder. The principle is similar: check the remainder until $A\ mod\ B$ is zero; otherwise, set A as B and B as the remainder. It works because it is essentially the same as the algorithm with $A - B$

**Pascal's triangle**: A triangle that forms rows, where each entry is the sum of the two immediately above it. The triangle starts with $1$. Entries from Pascal's triangle form the combination $\begin{pmatrix} n \\ k \end{pmatrix}$, where $n$ is the number of the row from 1 and $k$ is the entry.
![[Pasted image 20260830132931.png|411]]

**Monomial**: A polynomial that contains only a single term, e.g., $x^2$, $-ax$, etc.
**Binomial**: A polynomial that is the sum of two terms, where each term is a monomial 
**Binomial theorem**: The expansion of powers of binomials $(x + y)^n$ is equal to $\sum_{k=0}^n{ax^{n - k}y^k}$ where $a$ is a coefficient (called a binomial coefficient) from Pascal's triangle, also defined as the combination $\begin{pmatrix} n \\ k \end{pmatrix}$
**Binomial difference factorization**: $x^{n+1} - y^{n+1} = (x-y) * (\sum_{k=0}^nx^ky^{n-k})$, for example $x^3 - y^3 = x^{2 + 1} - y^{2 + 1} = (x - y)*(x^0*y^2 + x^1*y^1 + y^0*x^2) = (x - y)*(y^2 + xy + x^2)$

**Cusp**: a curve that separates into two branches having a tangent at the same point for both branches. Example: $\sqrt{|{x}|}$
![[Pasted image 20260830111628.png]]


**Odd form**: any odd number in $\mathbb{N}$ can be written as $2p+1$, since $p \in \mathbb{N}$ is even and adding 1 will make it odd
