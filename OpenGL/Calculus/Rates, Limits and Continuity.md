## Rates

**Average rate of change**: defined as the change in $y$ with respect to $x$, or in other words, the change in $y$ (which is defined by a function) is bound to the change in $x$  
The formula is $\dfrac{\Delta y}{\Delta x} = \dfrac{f(x_1) - f(x_0)}{x_1 - x_0}$

**Instantaneous rate of change**: Sometimes we want to compute the instantaneous rate of change at a given moment instead of the average rate of change. We can do it by using a constant $h$, which is equal to the distance from $x_0$. The smaller $h$ is (the point approaching from the right or left), the closer we are to the limit. 
1. Replacing $x_1$ with $x_0 + h$, where $h$ is a constant that is equal to the distance from $x_0$.  $\Delta x$ is then defined as $\Delta x = x_0 + h - x_0 = h$. The formula is $\dfrac{\Delta y}{\Delta x} = \dfrac{f(x_0 + h) - f(x_0)}{h}$. <u>It's still a formula for the average rate of change</u>
2. Computing by setting the value to $x_0$ with a value and expanding $f$ with a function, and for the final result setting $h$ to 0 (to cancel it, since we want the instantaneous rate of change).  
   Example $f(x) = x^2$, $x = 2$, $\dfrac{(2 + h)^2 - 2^2}{h} = \dfrac{2^2 + 4h + h^2 - 2^2}{h} = \dfrac{4h + h^2}{h} = 4 + h^2$, instant rate of change is equal to 4

Geometrically, the average rate of change is equal to the slope of the secant between points. The formula is $\dfrac{y_1 - y_0}{x_1 - x_0} = m$, where $m$ is the slope
 ![[Pasted image 20260816225752.png|214]]

**Point-Slope equation**: derived from the geometrical representation of the average rate of change by replacing y_1 and x_0 with y and x, and multiplying both sides by $x - x_0$, $y - y_0 = m(x - x_0)$

**Tangent of a curve**: A tangent is a line that is the best representation of a curve at a given point. The formula for the tangent of a curve at a given point is related to the **instantaneous rate of change**. By computing the instantaneous rate of change (which is the slope) and using the Point-Slope equation, we can compute the tangent of a curve. Example (based on the instantaneous rate of change example):
$y_0 = x^2 = 2^2 = 4$
Point-Slope: 
$y - 4 = 4 * (x - 2)$ 
$y = 4x - 8 + 4$ 
$y=4x - 4$
![[Pasted image 20260816233227.png|211]]
If multiple points lie on the same tangent line, we can compute the slope (*instantaneous rate*)


## Limits
A limit is defined as the value of a function when approaching a selected point $c$ as closely as possible to $c$, *possibly at $c$*. It doesn't matter if point $c$ is defined on the function or point $c$ has a different value than points close to $c$ (piecewise function), since we are computing the limit by approaching $c$ from either side (one-sided limits are possible too). 
A limit is denoted as $\lim_{x \to c} = L$; the limit of $x$ approaching $c$ is equal to the value $L$

<u>The limit of a function can be computed by decomposing the function into smaller functions</u> and then computing limits for them. Then we can combine the limits. 
Defined operations: 
1. **Sum**: $lim_{x \to c}(f(x) + g(x)) = lim_{x\to c}f + \lim_{x\to c}g = L + M$
2. **Difference**: $lim_{x \to c}(f(x) - g(x)) = lim_{x\to c}f -\lim_{x\to c}g = L - M$
3. **Division**: $lim_{x \to c}\dfrac{f(x)}{g(x)} = \dfrac{lim_{x\to c}f}{\lim_{x\to c}g} = \dfrac{L}{M}$ if $g(c) \ne 0$
4. **Multiplication with constant**: $lim_{x \to c}(kf(x)) = K * lim_{x \to c}(f(x)) = k * L$
5. **Multiplication**: $lim_{x \to c}(f(x)*g(x)) = lim_{x\to c}f(x) * \lim_{x\to c}g = L * M$ 
6. **Power**: $lim_{x \to c}f(x)^n = (lim_{x \to c}{f(x)})^n$ if $n > 0$
7. **Root**: $lim_{x \to c}f(x)^\dfrac{1}{n} = (lim_{x \to c}{f(x)})^\dfrac{1}{n}$ if $n > 0$

**Polynomial theorem**: if a function is polynomial, then we can substitute x for $c$, $F(x) = F(c) = \sum{A_n(c^n) + A_{n-1}(c^{n-1}) ...}$, where $A_n$ is a constant and $n$ is a power. Example: $f: 3x^3 + 4x^2 + 2x$, $c = 2$, $lim_{x \to c} = lim_{x \to 2} = 3 * c^3 + 4 * c^2 + 2 * c^1 = 3 * 2^3 + 4  * 2^2 + 2 * 2^1 = 44$
![[Pasted image 20260820170354.png|185]]

**Division theorem**: if $F(x)$ and $Q(x)$ are polynomial functions and $Q(c) \ne 0$, then we can substitute $x$ for $c$; then $\dfrac{F(x)}{Q(x)} = \dfrac{F(c)}{Q(c)}$ 

**Sandwich theorem**: if a function $f$ is between two functions $g$ and $h$, and both functions $g$ and $h$ have the same limit at point $c$, denoted as $\lim_{x \to  c}g = \lim_{x \to  c}h = L$, then any $f$ that is between the two functions also has the same limit at point $c$.
![[Pasted image 20260820121628.png|448]]

The more precise definition of a limit involves defining some acceptable error from $L$ at point $c$ as epsilon $\epsilon$ and a solution delta $\delta$ (offset from $c$) for that $\epsilon$. If such a $\delta$ exists for every $\epsilon$, then the limit exists.
Mathematically defined as:
$|f(x) - L|< \epsilon$ for every $0 < |x - c| < \delta$, read as: for every $\epsilon < 0$, there exists a solution $\delta$ that is bigger than $0$. 

Example: 
	Find $\delta$ for $\epsilon$ in $\lim_{x \to 2} x^2 = 4$.
	*Solution*: $|x^2 - 4| < \epsilon$, $-\epsilon< x^2 - 4 < \epsilon$, $-\epsilon + 4 < x^2 < \epsilon + 4$, $\sqrt{-\epsilon + 4} < x < \sqrt{\epsilon + 4}$, which implies that for every $\epsilon < 4$, there exists a $\delta$ that is equal to $\sqrt{\epsilon + 4}$
	By picking any $\epsilon$, we can show it. For example, $\epsilon = 2$
	$\sqrt{(2 + 4)} = \sqrt(6)$, $\sqrt{(-2 + 4)} = \sqrt(2)$ 
	![[Pasted image 20260823121149.png|389]]

There are also one-sided limits at point $c$, denoted as $\lim_{x \to c+} = L$ for a limit coming from the right and as $lim_{x \to c-} = L$ for a limit coming from the left. A limit from the right exists if, for every acceptable error $\epsilon$, there exists a solution $\delta$ from the right. A limit from the left exists if, for every acceptable error $\epsilon$, there exists a solution $\delta$ from the left.
Mathematically defined as:
$|f(x) - L| < \epsilon$ for $c < x < c + \delta$ for the right limit, read as: for each epsilon, there exists a delta that forms the interval between $(c, c + \delta)$
$|f(x) - L| < \epsilon$ for $c - \delta  < x < c$ for the right limit, read as: for each epsilon, there exists a delta that forms the interval between $(c - \delta, c)$

If a limit exists at point $c$ from the left and right, then a limit exists at point $c$

**Theorem limit of the ratio $sin(\theta) / \theta$ as $\theta \to 0$**:
$lim_{\theta  \to 0} {\dfrac{sin(\theta)}{\theta}} = 1$. Proved by the sandwich theorem by constructing a triangle on the unit circle with an angle equal to 1 rad and computing the area $\triangle ABC$ <  area of sector $ABC$ < area $\triangle ABD$
![[Pasted image 20260823160412.png|226]]
$S_{\triangle ABC} = \dfrac{1}{2} * sin(\theta) * 1 = \dfrac{\sin{\theta}}{2}$
$S_{sector\ ABC} = \dfrac{\theta * r^2}{2} = \dfrac{\theta}{2}$
$S_{\triangle ABC} = \dfrac{1}{2} * tan(\theta) * 1 = \dfrac{\tan{\theta}}{2}$
$\dfrac{\sin{\theta}}{2} < \dfrac{\theta}{2} < \dfrac{\tan{\theta}}{2}\ |*2, |:\sin\theta$
$1 < \dfrac{\theta}{sin(\theta)} < \dfrac{1}{cos(\theta)} | ^-1$
$1 > \dfrac{sin{\theta}}{\theta} > cos(\theta)$ , $lim_{x \to 0} cos(\theta) = 1$, thus proving the limit
![[Pasted image 20260823161657.png|583]]

### Continuity 

**Continuity rules**:
1. A function is continuous from the left at point $c$ if a left limit exists
2. A function is continuous from the right at point $c$ if a right limit exists
3. A function is continuous at $c$ if the function is defined at point c, is continuous from the left and from the right, and both limits are equal to the value at point $c$
	1. $c \in x$
	2. $f(c) = L$
	3. $lim_{x \to c+}=lim_{x \to c-}=f(c) =L$
A function is continuous if the function is continuous at every point $c$ in its domain.

Examples:
1. $\sqrt{1 - x^2}$, the function is left-continuous at $1$ and right-continuous at $- 1$, but the function is continuous only at points between $(-1, 1)$
   ![[Pasted image 20260823172928.png|323]]
2. The $x^2$ function is continuous at every point 


**Removable discontinuity**: a function is discontinuous at a point by defining a new point or is not defined at such a point, but the limits for both the left and right sides are equal, e.g., the function is continuous from both sides (example $sin(\theta) / \theta$
![[Pasted image 20260823172232.png|319]]
**Jump discontinuity**: a function makes a "jump" and continues from a new point. The left and right limits are not equal (example: floor function)
![[Pasted image 20260823171216.png|359]]
**Oscillating discontinuity**: a function oscillates so much that it's impossible to define a limit; thus, the function is not continuous from either the left or right
![[Pasted image 20260823173731.png|328]]
**Infinity discontinuity**: a function goes to infinity on either side; it's impossible to define a limit (example: $1/sin(x)$)
![[Pasted image 20260823173952.png|255]]

**Theorem properties of continuous functions**: If $f(c)$ and $g(c)$ are continuous at c, then algebraic combinations of such functions are also continuous. The list of algebraic combinations is the same as for limits (because continuity is tightly connected with limits)

**Theorem composition of functions**: for the composition of functions, if $f$ is continuous at $c$ and $g$ is continuous at $g(f(c))$, then the composition $g \circ f$ is also continuous at $c$ (example: $f(x) = x$, $g(x) = x^2$, $c = 2$). $lim_{x \to c} g(f(c)) = g(lim_{x \to c} f(c))$
![[Pasted image 20260906115751.png|386]]

**Intermediate value theorem**: if a function is continuous at $a$ and $b$ and $f(x)$ is a value between $f(a)$ and $f(b)$, then for $f(x)$ there exists such a point $c$ that lies in the interval $[a, b]$

If a function is continuous at $a$ and $b$ and $f(a)$ and $f(b)$ have different signs, then there exists an $x$ point that is equal to zero

**Continuous extension point**: If a function is not defined at one point, we can create another piecewise function where a definition will exist for $x$ at that undefined point
Example:
$f(x) = \begin{cases}\dfrac{sin{\theta}}{\theta} & x \ne 0 \\ 1 & x = 0\end{cases}$
![[Pasted image 20260823172025.png|448]]

### Asymptotes and infinity limits

**A limit at infinity** is the value which a curve tends to approach as x approaches positive or negative infinity. It is denoted as $lim_{x \to \infty+} = L$ as x approaches positive infinity or $lim_{x \to \infty-} = L$ as x approaches negative infinity. The same arithmetic rules and decomposition as for usual limits are applied to limits at infinity.

Rational polynomial limits are computed by dividing all elements by the highest term of the dividend if the dividend rank is bigger than or equal to the divisor polynomial.
For example: $lim_{x \to \infty}\dfrac{x}{x^2 + 1} = \dfrac{x / x^2}{1 + 1/x^2} = \dfrac{lim_{x \to \infty}x / x^2}{1 + lim_{x \to \infty}1/x^2} = \dfrac{0}{1 - 0} = 0$

**An asymptote** is a line to some function which becomes closer to the curve as x approaches infinity, or in other words, the distance between the curve and the line becomes zero as x approaches infinity. A function can have zero, one, or two asymptotes (inf)

**A horizontal asymptote** is a horizontal line that is defined by some value $a$, e.g., $y = a$, which the curve approaches as $x$ approaches infinity.



**An infinity limit** is not actually a limit but is a way to denote that a function doesn't have a limit at point $c$ because it tends to infinity. For example, $log(x)$
![[Pasted image 20260828234147.png|312]]
**A vertical asymptote** is a vertical line to positive or negative infinity at some point $c$ which a function approaches but never reaches (previous image). 

**An oblique asymptote** is formed by a skewed line for both positive and negative limits, usually when the dividend of a polynomial has a lower-rank divisor, e.g., formed by polynomial division, where the quotient is an asymptote and the remainder is used to compute the vertical distance between the function. The limit for a function that has an oblique asymptote doesn't exist since the function goes to infinity.
Example: $\dfrac{x^3 + x^2 - 5}{x^2 - 2x + 3}$ with quotient x + 3
![[Pasted image 20260829000728.png|265]] ![[Pasted image 20260829000814.png|253]]
