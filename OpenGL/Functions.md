**Mapping**: taking input and transforming it output, e.g mapping output to input by function. Single input can be mapped only to one output but multiple inputs can be mapped to same value output. Function mapping is denoted as $f:input \rightarrow output$ and as function input maps to output. 

**Domain** is input set, while **range** is set, that domain maps to. **Range** set can be bigger than subset that **domain** points, it's not required for mapping to point to all element of **range** set

Type of function mapping:
1. **Injection** (one-to-one): mapping, where each element of domain maps to unique element from range. If range set is bigger than domain set, some element from range are not mapped.
2. **Surjection** (onto): All from range are mapped to at least one element from domain elements (different elements from domain could ba mapped to same element from range)
3. **Bijection** (one-to-one and onto): combination of injection and surjection - only one mapping of element from domain to element from range exist and each element from range are mapped
4. **General mapping**: no restrictions
There is visualization using arrow mappings:
![[Pasted image 20260814150543.png|430]]

**Piecewise function**: function, that is partitioned into some intervals, e.g is different in some parts depending on some conditions. Example of absolute value $|a|$ function, **floor** function (which always rounds to smallest integer) or **ceil** (which always round to bigger integer) Piecewise function notation consists of opened curcly brace, which consists mapping function value (can be an expression or variable) for specific interval. Example: 
$sign(x) = \begin{cases}1 & x > 0 \\ 0 & x = 0 \\ -1 & x < 0\end{cases}$

**Increasing and decreasing function**: function increases as it moves to right or decreases as it moves to right

**Even and odd function**: Symmetrical functions, which are **even** if $f(-x) = f(x)$ for all values or *odd* if $f(-x) = -f(x)$ for all values.

Common types of functions:
- **Linear**: function is defined by variable and fixed constants slope $m$ and $b$ $y = mx + b$ If $m =1$ and $b=0$, then function is called identity function. Linear variables x and y are proportional to each, changing one changes another. Function is flat if $m$ is 0
- **Power**: function in form $y = x^a$, where $a$ is constant exponent. Even exponents produce symmetrical function by $y$ axis and function is always positive, odd exponents produce symmetrical function by origin. Power function are steeper in change than linear
- **Inversely proportional function**: Power function with exponent equal to -1. Function decreases (for negative side increases) further it gets from origin
- **Polynomial**: function in form $y = \sum{a_nx^n} ...$ that contains polynomial of degree equal to $n$. Linear functions are polynomial functions of degree 1
- **Rational**: polynomial function that is form of fraction $y = p/q$, where $p$ and $q$ are polynomials
- **Exponential**: Decreasing function, that defined by exponent $x$ of constant base $a$, $y = x^a$
- **Logarithmic**: Inverse of exponential function
- **Algebraic**: polynomial function with defined algebraic operations - division, multiplication, sum, subtraction and root.
- **Trigonometric**
- **Transcendental**: Functions that can't be expressed as algebraic function such as trigonometric functions

**Monotonic function** is function that is keep increasing or decreasing, for example $y=x$ or $y = -x$

**Combining function**: Function can be algebraically combined. Domain ($D$) is reduced to intersection of domains of both function.
Examples where $f(x) = x$ and $g(x) = 1/x$, $D(x)$ for is $f(x)$ is $(-\infty, \infty)$, $D(x)$ for is $g(x)$ is $(-\infty, 0)\ U\ (0, \infty)$
1. $f(x) + g(x)$ if $x$ is defined in $D(x)$ for $f(x)$ and $g(x)$
2. $f(x)- g(x)$ if $x$ is defined in $D(x)$ for $f(x)$ and $g(x)$
3. $f(x)*g(x)$ if $x$ is defined in $D(x)$ for $f(x)$ and $g(x)$
4. $\dfrac{f(x)}{g(x)}$ if $x$ is defined in $D(x)$ for $f(x)$ and $g(x)$ and output of $g(x)$ is not zero

**Composed function**: Output if one function is passed to another. Domain is restricted to function that accepts passed function. Denoted as $f \circ g = f(g(x))$

**Scaling and reflecting graph**:
* if function is multiplied by $k > 1$, graph becomes stretched by $y$. Multiplying by $k$ in $(0, 1)$ will shrink graph by y
* if function input is multiplied by $k > 1$, graph becomes compressed by $x$. Multiplying by $k$ in $(0, 1)$ will stretched graph by x
* if function is multiplied by minus one $-1 *f(x)$, graph is reflected by y. If the input of function is multiplied by one $f(-1*x)$, graph is reflected by x

**Shifting graph**: graph can be shifted in $y$ and $x$ direction. 
1. **Shift $y$ of graph**: adding constant such as $y = f(x) + k$ shift $y$ of graph by $k$, where positive $k$ shifts graph up and negative $k$ shifts graph down.
2. **Shift $x$ of graph**: adding constant to function input such as $f(x + k)$ shifts $x$ of graph by $k$, where positive $k$ shifts graph to right and negative $k$ shifts graph to left.

**Periodic function**: Function that repeats itself by adding period $p$. **Period** is the smallest possible number by adding which function repeats itself. Example is trigonometric function, where $p$ is $2\pi$, $sin(x + p) = sin(x + 2\pi) = sin(x)$

**Graph viewing windows**: window, where min, max y and x is limited. Decreasing x and y zooms graph, increasing unzooms. Some details of graphs can be visible in zoomed or unzoomed graph


**Norm**: any function that defines distance of vector from origin with properties:
* Is zero only in origin 
* Must obey triangle inequality $f(x + y) <= x + y$ 
* homogeneous - $f(s*x) = s * f(x)$, 
* (optionally) non negative
common types:
* P-norm - p norm is defined as ($\sum{x_i^p})^{1/p}$
* Euclidean norm (2-norm, geometric length) - length of vector defined by $\sqrt{\sum{x_i^2}}$. Euclidean norm is subset of p norm. Proof of homogeneity - s = 2, $\vec{v} = (5, 2)$, $\sqrt{(5*2)^2 + (2*2)^2} = 2 * \sqrt{5^2 + 2^2}$, $\sqrt{10^2 + 4^2} = 2 * \sqrt{25 + 4}$, $\sqrt{100 + 16} = 2 * \sqrt{29}$, $\sqrt{116} = \sqrt{4 * 29}$, $\sqrt{116} = \sqrt{116}$
* taxicab norm - $\sum{x_i}$, it measures distance like if we travel to x and then to y instead of shortest path via euclidean norm, for example $a = (1,1)$, length is $1 + 1$
* chebyshev norm (infinity norm) - largest absolute value in vector
