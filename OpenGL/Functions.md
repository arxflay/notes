**Mapping**: taking input and transforming it into output, e.g., mapping output to input by a function. A single input can be mapped to only one output, but multiple inputs can be mapped to the same output value. Function mapping is denoted as $f:input \rightarrow output$ and as a function input maps to output. 

**Domain** is the input set, while **range** is the set that the domain maps to. The **range** set can be bigger than the subset that the **domain** points to; it's not required for the mapping to point to all elements of the **range** set

Types of function mapping:
1. **Injection** (one-to-one): mapping where each element of the domain maps to a unique element from the range. If the range set is bigger than the domain set, some elements from the range are not mapped.
2. **Surjection** (onto): All elements from the range are mapped to at least one element from the domain (different elements from the domain could be mapped to the same element from the range)
3. **Bijection** (one-to-one and onto): combination of injection and surjection - only one mapping of an element from the domain to an element from the range exists, and each element from the range is mapped
4. **General mapping**: no restrictions
There is a visualization using arrow mappings:
![[Pasted image 20260814150543.png|430]]

**Piecewise function**: a function that is partitioned into some intervals, e.g., it is different in some parts depending on some conditions. Examples are the absolute value $|a|$ function, the **floor** function (which always rounds to the smallest integer), or **ceil** (which always rounds to the bigger integer). Piecewise function notation consists of an open curly brace, which contains the function value mapping (which can be an expression or variable) for a specific interval. Example: 
$sign(x) = \begin{cases}1 & x > 0 \\ 0 & x = 0 \\ -1 & x < 0\end{cases}$

**Increasing and decreasing function**: a function increases as it moves to the right or decreases as it moves to the right

**Even and odd function**: Symmetrical functions which are **even** if $f(-x) = f(x)$ for all values or *odd* if $f(-x) = -f(x)$ for all values.

Common types of functions:
- **Linear**: a function is defined by a variable and fixed constants slope $m$ and $b$ $y = mx + b$ If $m =1$ and $b=0$, then the function is called an identity function. Linear variables x and y are proportional to each other; changing one changes the other. The function is flat if $m$ is 0
- **Power**: a function in the form $y = x^a$, where $a$ is a constant exponent. Even exponents produce a function symmetrical about the $y$ axis, and the function is always positive; odd exponents produce a function symmetrical about the origin. Power functions are steeper in change than linear functions
- **Inversely proportional function**: A power function with an exponent equal to -1. The function decreases (and increases on the negative side) the further it gets from the origin
- **Polynomial**: a function in the form $y = \sum{a_nx^n} ...$ that contains a polynomial of degree equal to $n$. Linear functions are polynomial functions of degree 1
- **Rational**: a polynomial function that is in the form of a fraction $y = p/q$, where $p$ and $q$ are polynomials
- **Exponential**: A decreasing function that is defined by exponent $x$ of constant base $a$, $y = x^a$
- **Logarithmic**: Inverse of exponential function
- **Algebraic**: a polynomial function with defined algebraic operations - division, multiplication, sum, subtraction, and root.
- **Trigonometric**
- **Transcendental**: Functions that can't be expressed as algebraic functions, such as trigonometric functions

**A monotonic function** is a function that keeps increasing or decreasing, for example, $y=x$ or $y = -x$

**Combining functions**: Functions can be algebraically combined. The domain ($D$) is reduced to the intersection of the domains of both functions.
Examples where $f(x) = x$ and $g(x) = 1/x$: $D(x)$ for $f(x)$ is $(-\infty, \infty)$, and $D(x)$ for $g(x)$ is $(-\infty, 0)\ U\ (0, \infty)$
1. $f(x) + g(x)$ if $x$ is defined in $D(x)$ for $f(x)$ and $g(x)$
2. $f(x)- g(x)$ if $x$ is defined in $D(x)$ for $f(x)$ and $g(x)$
3. $f(x)*g(x)$ if $x$ is defined in $D(x)$ for $f(x)$ and $g(x)$
4. $\dfrac{f(x)}{g(x)}$ if $x$ is defined in $D(x)$ for $f(x)$ and $g(x)$ and the output of $g(x)$ is not zero

**Composed function**: The output if one function is passed to another. The domain is restricted to a function that accepts the passed function. Denoted as $f \circ g = f(g(x))$

**Scaling and reflecting graph**:
* if a function is multiplied by $k > 1$, the graph becomes stretched by $y$. Multiplying by $k$ in $(0, 1)$ will shrink the graph by y
* if a function input is multiplied by $k > 1$, the graph becomes compressed by $x$. Multiplying by $k$ in $(0, 1)$ will stretch the graph by x
* if a function is multiplied by minus one $-1 *f(x)$, the graph is reflected by y. If the input of the function is multiplied by one $f(-1*x)$, the graph is reflected by x

**Shifting a graph**: a graph can be shifted in the $y$ and $x$ directions. 
1. **Shift $y$ of graph**: adding a constant such as $y = f(x) + k$ shifts the $y$ of the graph by $k$, where positive $k$ shifts the graph up and negative $k$ shifts the graph down.
2. **Shift $x$ of graph**: adding a constant to the function input, such as $f(x + k)$, shifts the $x$ of the graph by $k$, where positive $k$ shifts the graph to the right and negative $k$ shifts the graph to the left.

**Periodic function**: A function that repeats itself by adding a period $p$. **A period** is the smallest possible number which, when added, causes the function to repeat itself. An example is a trigonometric function, where $p$ is $2\pi$, $sin(x + p) = sin(x + 2\pi) = sin(x)$

**Graph viewing windows**: a window where the minimum and maximum y and x are limited. Decreasing x and y zooms the graph; increasing them zooms out. Some details of graphs can be visible in a zoomed or unzoomed graph


**Norm**: any function that defines the distance of a vector from the origin with the properties:
* Is zero only at the origin 
* Must obey triangle inequality $f(x + y) <= x + y$ 
* homogeneous - $f(s*x) = s * f(x)$, 
* (optionally) nonnegative
common types:
* P-norm - the p-norm is defined as ($\sum{x_i^p})^{1/p}$
* Euclidean norm (2-norm, geometric length) - the length of a vector defined by $\sqrt{\sum{x_i^2}}$. The Euclidean norm is a subset of the p-norm. Proof of homogeneity - s = 2, $\vec{v} = (5, 2)$, $\sqrt{(5*2)^2 + (2*2)^2} = 2 * \sqrt{5^2 + 2^2}$, $\sqrt{10^2 + 4^2} = 2 * \sqrt{25 + 4}$, $\sqrt{100 + 16} = 2 * \sqrt{29}$, $\sqrt{116} = \sqrt{4 * 29}$, $\sqrt{116} = \sqrt{116}$
* taxicab norm - $\sum{x_i}$, it measures distance as if we travel to x and then to y instead of taking the shortest path via the Euclidean norm; for example, $a = (1,1)$, the length is $1 + 1$
* Chebyshev norm (infinity norm) - the largest absolute value in a vector
