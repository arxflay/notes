## Rates

**Average rate of change**: defined as change of $y$ in respect to $x$ or in other words change of $y$ (which is defined by function) is bound to change of $x$  
Formula is $\dfrac{\Delta y}{\Delta x} = \dfrac{f(x_1) - f(x_0)}{x_1 - x_0}$

**Instanteneous rate of change**: Sometimes we want to compute instant rate of change at given moment instead of average rate of change. We can do it by using constant $h$, which is equal to distance from $x_0$. The smaller $h$ is (Point approaching from right or left), the closer we are to limit. 
1. Replacing $x_1$ with $x_0 + h$, where $h$ constant that is equal to distance from $x_0$.  $\Delta x$ is then defined as $\Delta x = x_0 + h - x_0 = h$. Formula is $\dfrac{\Delta y}{\Delta x} = \dfrac{f(x_0 + h) - f(x_0)}{h}$. <u>It's a still formula for average rate of change</u>
2. Compute by setting value to $x_0$ with value and expand $f$ with a function and for final result set $h$ as 0 (to cancel it. since we want instant rate of change).  
   Example $f(x) = x^2$, $x = 2$, $\dfrac{(2 + h)^2 - 2^2}{h} = \dfrac{2^2 + 4h + h^2 - 2^2}{h} = \dfrac{4h + h^2}{h} = 4 + h^2$, instant rate of change is equal to 4

Geometrically average rate of change is equal to slope of secant between points. Formula is $\dfrac{y_1 - y_0}{x_1 - x_0} = m$, where $m$ is a slope
 ![[Pasted image 20260816225752.png|214]]

**Point-Slope equation**: derived of geometrical representation of average rate of change, replacing y_1 and x_0 with y and x, and multiplying both sides with $x - x_0$, $y - y_0 = m(x - x_0)$

**Tangent of curve**: Tanget is line that is the best representation of curve at given point. Formula for tangent of curve at given point is related to **Instanteneous rate of change**. By computing Instanteneous rate of change (which is slope) and using Point-Slope equation, we can compute tangent of curve. Example (based of instant rate of change example):
$y_0 = x^2 = 2^2 = 4$
Point-Slope: 
$y - 4 = 4 * (x - 2)$ 
$y = 4x - 8 + 4$ 
$y=4x - 4$
![[Pasted image 20260816233227.png|211]]
If multiple points lies on same tangent line, we can compute slope (*Instanteneous rate*)


## Limits
Limit is defined as value of function when approaching selected point $c$ as close it possible close to $c$, *possible at $c$*. It doesn't matter if point $c$ is defined on function or point $c$ have different value then points close to $c$ (piecewise function), since we are computing limit by approching $c$ from either sides (one side limits are possible too). 
Limit is denoted as $\lim_{x \to c} = L$, limit of $x$ approaching $c$ is equal to value $L$

<u>Limit of function can be computed by decomposing function into smaller functions</u> and then computing limits for them. Then we can combine limits. 
Defined operations: 
1. **Sum**: $lim_{x \to c}(f(x) + g(x)) = lim_{x\to c}f + \lim_{x\to c}g = L + M$
2. **Difference**: $lim_{x \to c}(f(x) - g(x)) = lim_{x\to c}f -\lim_{x\to c}g = L - M$
3. **Division**: $lim_{x \to c}\dfrac{f(x)}{g(x)} = \dfrac{lim_{x\to c}f}{\lim_{x\to c}g} = \dfrac{L}{M}$ if $g(c) \ne 0$
4. **Multiplication with constant**: $lim_{x \to c}(kf(x)) = K * lim_{x \to c}(f(x)) = k * L$
5. **Multiplication**: $lim_{x \to c}(f(x)*g(x)) = lim_{x\to c}f(x) * \lim_{x\to c}g = L * M$ 
6. **Power**: $lim_{x \to c}f(x)^n = (lim_{x \to c}{f(x)})^n$ if $n > 0$
7. **Root**: $lim_{x \to c}f(x)^\dfrac{1}{n} = (lim_{x \to c}{f(x)})^\dfrac{1}{n}$ if $n > 0$

**Polynomial theorem** if function is polymonial, then we can substitute x for $c$, $F(x) = F(c) = \sum{A_n(c^n) + A_{n-1}(c^{n-1}) ...}$, where $A_n$ is a constant and $n$ is a power. Example $f: 3x^3 + 4x^2 + 2x$, $c = 2$, $lim_{x \to c} = lim_{x \to 2} = 3 * c^3 + 4 * c^2 + 2 * c^1 = 3 * 2^3 + 4  * 2^2 + 2 * 2^1 = 44$
![[Pasted image 20260820170354.png|185]]

**Division theorem**: if $F(x)$ and $Q(x)$ are polynomial functions and $Q(c) \ne 0$, then we can substitute $x$ for $c$ then $\dfrac{F(x)}{Q(x)} = \dfrac{F(c)}{Q(c)}$ 

**Sandwich theorem**: if function $f$ is in between two functions $g$ and $h$, and both functions $g$ and $h$ have same limit at point $c$, denoted as $\lim_{x \to  c}g = \lim_{x \to  c}h = L$, then any $f$ that is between two functions also have same limit at point $c$.
![[Pasted image 20260820121628.png|448]]

More price defition of limited involves defining some acceptable error from $L$ at point $c$ as epsilon $\epsilon$ and solution delta $\delta$ (offset from $c$) for that $\epsilon$. If such $\delta$ exist for every $\epsilon$, then limit exists.
Mathematically defined as:
$|f(x) - L|< \epsilon$ for every $0 < |x - c| < \delta$, read as for every $\epsilon < 0$ exists solution $\delta$ that is bigger than $0$. 

Example: 
	Find $\delta$ for $\epsilon$ in $\lim_{x \to 2} x^2 = 4$.
	*Solution*: $|x^2 - 4| < \epsilon$, $-\epsilon< x^2 - 4 < \epsilon$, $-\epsilon + 4 < x^2 < \epsilon + 4$, $\sqrt{-\epsilon + 4} < x < \sqrt{\epsilon + 4}$, that implies that for every $\epsilon < 4$ exists $\delta$ that equals to $\sqrt{\epsilon + 4}$
	By picking any $\epsilon$ we can show it. For example $\epsilon = 2$
	$\sqrt{(2 + 4)} = \sqrt(6)$, $\sqrt{(-2 + 4)} = \sqrt(2)$ 
	![[Pasted image 20260823121149.png|389]]

There is also one sided limits at point $c$, denoted as $\lim_{x \to c+} = L$ for limit coming from right and and as $lim_{x \to c-} = L$ for limit coming from left. Limit from right if for every exists acceptable error $\epsilon$ exists solution $\delta$ from right. Limit from left if for every exists acceptable error $\epsilon$ exists solution $\delta$ from left.
Mathematically defined as:
$|f(x) - L| < \epsilon$ for $c < x < c + \delta$ for right limit, read as for each epsilon exists delta that forms interval between $(c, c + \delta)$
$|f(x) - L| < \epsilon$ for $c - \delta  < x < c$ for right limit, read as for each epsilon exists delta that forms interval between $(c - \delta, c)$

If exists limit at point $c$ from left and right, then at point $c$ exists limit

**Theorem limit of the ratio $sin(\theta) / \theta$ as $\theta \to 0$**:
$lim_{x \to 0} {\dfrac{sin(\theta)}{\theta}} = 1$. Proved by sandwich theorem by constructing triangle on unit circle with angle equals to 1 rad and computing Area $\triangle ABC$ <  Area of sector $ABC$ < Area $\triangle ABD$
![[Pasted image 20260823160412.png|226]]
$S_{\triangle ABC} = \dfrac{1}{2} * sin(\theta) * 1 = \dfrac{\sin{\theta}}{2}$
$S_{sector\ ABC} = \dfrac{\theta * r^2}{2} = \dfrac{\theta}{2}$
$S_{\triangle ABC} = \dfrac{1}{2} * tan(\theta) * 1 = \dfrac{\tan{\theta}}{2}$
$\dfrac{\sin{\theta}}{2} < \dfrac{\theta}{2} < \dfrac{\tan{\theta}}{2}\ |*2, |:\sin\theta$
$1 < \dfrac{\theta}{sin(\theta)} < \dfrac{1}{cos(\theta)} | ^-1$
$1 > \dfrac{sin{\theta}}{\theta} > cos(\theta)$ , $lim_{x \to 0} cos(\theta) = 1$, thus proving limit
![[Pasted image 20260823161657.png|583]]

### Continuity 

**Continuity rules**:
1. Function is continuous from left at point $c$ if exists left limit
2. Function is continuous from right at point $c$ if exists right limit
3. Function is continuous at $c$ if function is defined at point c, is continuous from left and from right, and both limits are equal value at point $c$
	1. $c \in x$
	2. $f(c) = L$
	3. $lim_{x \to c+}=lim_{x \to c-}=f(c) =L$
Function is continuous if function is continuous at every point $c$ in it's domain.

Examples:
1. $\sqrt{1 - x^2}$, function is left continuous at $1$ and right continuous at $- 1$, but function is continuous only in points between $(-1, 1)$
   ![[Pasted image 20260823172928.png|323]]
2. $x^2$ function is continuous for every point 


**Removable discontinuity**: function is discontinues in point by defining new point or is not defined in such point, but limits for either left or right side are equal, e.g function is continuous from either sides (example $sin(\theta) / \theta$
![[Pasted image 20260823172232.png|319]]
**Jump discontinuity**: function makes "jump" and continues from new point. Neither left or right limits are equal (example floor function)
![[Pasted image 20260823171216.png|359]]
**Oscillating discontinuity**: function oscillates to much that it's impossible to define limit, thus function is not contentious either from left or right
![[Pasted image 20260823173731.png|328]]
**Infinity discontinuity**: function goes to infinity on either sides, it's impossible to define limit (example $1/sin(x)$)
![[Pasted image 20260823173952.png|255]]

**Theorem properties of continuous functions**: If $f(c)$ and $g(c)$ are continuous at c, then algebraic combinations of such function are also continuous. List of algebraic combinations is same as for limits (because continuity is tightly connected with limits)

**Theorem composition of functions**: composition of function if $f$ is continuous at $c$ and $g$ is continuous at $g(f(c))$, then composition $g \circ f$ is also continuous at $c$ (example $f(x) = x$, $g(x) = x^2$, $c = 2$). $lim_{x \to c} g(f(c)) = g(lim_{x \to c} f(c))$
![[Pasted image 20260906115751.png|386]]

**Intermediate value theorem**: if function is continuous at $a$ and $b$ and $f(x)$ is a value between $f(a)$ and $f(b)$, then for $f(x)$ exists such point $c$ that lies in interval $[a, b]$

If function is continuous at $a$ and $b$ and $f(a)$ and $f(b)$ has different sign, then there point exists $x$ point that is equal to zero

**Contineous extensions point**: If function is not defined at one point, we can create create another piecewise function, where for $x$ that undefined point will exists definition
Example:
$f(x) = \begin{cases}\dfrac{sin{\theta}}{\theta} & x \ne 0 \\ 1 & x = 0\end{cases}$
![[Pasted image 20260823172025.png|448]]

### Asymptotes and infinity limits

**Limit at infinity** is value to which curve tends to come as x approaches positive or negative infinity. Denoted as $lim_{x \to \infty+} = L$ as x approaches positive infinity or $lim_{x \to \infty-} = L$ as x approaches negative infinity. For limits at infinity are applied same artihmetic rules and decomposition as for usual limits.

Rational polynomial limits are computed by division of all elements with highiest term of divident if divident rank is bigger or equal to divisor polynomial.
For example: $lim_{x \to \infty}\dfrac{x}{x^2 + 1} = \dfrac{x / x^2}{1 + 1/x^2} = \dfrac{lim_{x \to \infty}x / x^2}{1 + lim_{x \to \infty}1/x^2} = \dfrac{0}{1 - 0} = 0$

**Asymtote** is a line to some function, which become closer to curve as x approaches infinity or in other words distance between curve and line becomes zero as x approaches infinity. Function can have zero, one or two asymptotes (inf)

**Horizontal asymptote** is horizontal line that is defined by some value $a$, e.g $y = a$, to which curve become close as $x$ approaches infinity.



**Infinity limit** is not actually a limit but is a way to denote that function doesn't have limit at point $c$, because it tends to infinity. For example $log(x)$
![[Pasted image 20260828234147.png|312]]
**Vertical asymtote** is vertical line to positive or negative infinity at some point $c$ which function approaches but never reaches (previous image). 

**Oblique asymptote** is formed by skewed line for both positive and negitive limits, usually when divident of polynomial has lower rank divisor, e.g formed by polynomial divivision, where quatient is a asymtote and remainder is used to compute vertical distance between function. Limit for function that has oblique asymptote doesn't exists since function goes to infinity.
Example $\dfrac{x^3 + x^2 - 5}{x^2 - 2x + 3}$ with quatient x + 3
![[Pasted image 20260829000728.png|265]] ![[Pasted image 20260829000814.png|253]]

