**Differentiation** is the process of finding the derivative of a function. **The derivative at point $x_0$** is interpreted as the slope of the tangent to a curve at point $x_0$ (instantaneous rate) or the slope of the secant $x_0$ at $P(x_0, f(x_0))$. Mathematically, it is defined as the limit of the instantaneous rate where $h$ approaches zero.
$f'(x_0) = \lim_{h \to 0} \dfrac{f(x_0 + h) - f(x_0)}{h}$, $x_0$ emphasizes that we are computing the derivative of a function at point $x_0$. If such a limit doesn't exist, that means that the derivative of the function doesn't exist at point $x_0$
Example of the derivative at point $x_0$, where the slope of the tangent is $f'(x_0)$
![[Pasted image 20260830114654.png|494]]

**The derivative of a function** has the same formula as the derivative of a function at a point; only $x_0$ is replaced with $x$ to emphasize that we can use an arbitrary x
$f'(x) =  \lim_{\Delta x \to 0} \dfrac{\Delta y}{\Delta x} \lim_{h \to 0} \dfrac{f(x + h) - f(x)}{h}$
or
$f'(x) = \lim_{z \to x} \dfrac{f(z) - f(x)}{z - x}$, where $z = x + h$ then $h = z - x$. When $z$ is equal to $x$ then $h$ is zero.

The derivative of a function can be denoted in multiple ways:
$f'(x) = \dfrac{d}{dx}f(x) = \dfrac{dy}{dx} = D^1(f)(x)$
$\dfrac{d}{dx}f(x)$ = derivative of f(x) with respect to x
$\dfrac{dy}{dx}$ = derivative of y with respect to x

The derivative of a function at point $a$ can be denoted as:
$f'(a) = \dfrac{d}{dx}\Bigg|_{x=a}$

If a function is differentiable for all $x$, it's called a differentiable function.
If a function is differentiable at point $x$, it's called a function that is differentiable at point $x$

Differentiation can be split into right and left differentiation, denoted as $\lim_{h \to 0+}$ and $\lim_{h \to 0-}$. 
**Existence rules**: 
* If both the left and right derivatives exist, they are equal, and the function is continuous at point $x$, then the function is differentiable at point $x$. 
* A function is differentiable on a closed interval $[a, b]$ if the function is differentiable from the right at $a$ and from the left at $b$
* A function is differentiable on an open interval $(a, b)$ if it's differentiable at all points inside the interval

Some cases where it's not possible to differentiate:
1. Oscillating $sin(1/x)$
    ![[Pasted image 20260823173731.png|328]]
2. Different behavior on the left and right sides (Point 0,0). $f(x) = |x|$
	$\lim_{h \to 0+} \dfrac{x + h - x}{h} = 1$
	$\lim_{h \to 0-} \dfrac{-x - h + x}{h} = -1$
	![[Pasted image 20260829175000.png|222]]
3. Discontinuity


We differentiate a function $n$ times (n-th order derivative) by differentiating the derivative. For example, the second order derivative is $f''(x)$, which is the derivative of the derivative; the third order derivative is the derivative of the derivative of the derivative

Differentiation can be applied even when $x$ is not time; for example, the area of a square is 
$A = a^2$, then how fast the area will change with respect to the side length, thus $x$ is the side length. The result is the derivative $\dfrac{dA}{da} = 2a$ $m^2/m$

When a small change in $x$ makes a big change in $f(x)$, then the function is sensitive. The measure of sensitivity is $|f'(x)|$; the steeper the slope, the more sensitive the function
#### Common derivative formulas
1. **Derivative of a constant**:
   $\dfrac{d}{dx}f(x) = 0$ for $f(x) = k$ since $\lim_{h \to 0+} \dfrac{k - k}{h} = 0$
2. **Derivative of a power**:
   $\dfrac{d}{dx}f(x) = nx^{n-1}$ for $f(x) = x^n$ 
	Proof: 
	$z^n - x^n$ = $(z-x)*\sum_{k=0}^xx^ky^{n-k}$ 
	$\lim_{z \to x} \dfrac{z^n - x^n}{z - x} = \lim_{z \to x} \dfrac{(z-x)*\sum_{k=0}^xx^ky^{n-k}}{z-x} = lim_{z \to x}\sum_{k=0}^n{x^ky^{n-k}} = nx^{n-1}$ because we set $z = x$, thus $\sum_{k=0}^n{x^ky^{n-k}}$ is equal to $\sum_{k=0}^n{x^n}$
3. **Derivative of a scalar $u$ multiple**:
	$\dfrac{d}{dx}f(ux) = u \dfrac{d}{dx}f(x)$
	Proof:
	$lim_{h \to 0} \dfrac{u(x + h) - u(x)}{h} = u \dfrac{(x + h) - (x)}{h}=u \dfrac{d}{dx}f(x)$
4. **Derivative of a sum and difference**:
	$\dfrac{d}{dx}(u+v) = \dfrac{du}{dx} + \dfrac{dv}{dx}$
	$\dfrac{d}{dx}(u-v) = \dfrac{du}{dx} - \dfrac{dv}{dx}$
	Proof:
	$lim_{h \to 0} \dfrac{(u(x + h) + v(x + h)) - (u(x) + v(x))}{h}=lim_{h \to 0} \dfrac{u(x + h) - u(x)}{h} + \dfrac{v(x + h) - v(x)}{h}$ = $\dfrac{du}{dx} + \dfrac{dv}{dx}$
5. **Derivative of a product**:
	$\dfrac{d}{dx}(u*v) = u\dfrac{dv}{dx} + v\dfrac{du}{dx}$
6. **Derivative of a quotient**:
	$\dfrac{d}{dx}(\dfrac{u}{v}) = \dfrac{v\dfrac{du}{dx} - u\dfrac{dv}{dx}}{v^2}$
	if $v(x) \ne 0$
#### Derivatives of trigonometric functions
1. **Derivative of sine**
   $\dfrac{d}{dx}(sin(x)) = cos(x)$
   Proof:
	$\lim_{h \to 0} \dfrac{sin(x + h) - sin(x)}{h} = \lim_{h \to 0} \dfrac{sin(x)cos(h) + cos(x)sin(h) - sin(x)}{h}$
	$= \lim_{h \to 0} sin(x) \dfrac{cos(h) - 1}{h} + \lim_{h \to 0}cos(x)\dfrac{sin(h)}{h}$ since $sin(x)$ and $cos(x)$ are not part of the limit, $sin(x) \lim_{h \to 0} \dfrac{cos(h) - 1}{h} + cos(x)\lim_{h \to 0}\dfrac{sin(h)}{h}$; both are known limits, $sin(x)*0 + cos(x) * 1$
2. **Derivative of cosine**
   $\dfrac{d}{dx}(cos(x)) = -sin(x)$
    Proof:
	$\lim_{h \to 0} \dfrac{cos(x + h) - cos(x)}{h} = \lim_{h \to 0} \dfrac{cos(x)cos(h) - sin(x)sin(h) - cos(x)}{h}$
	$= \lim_{h \to 0} cos(x) \dfrac{cos(h) - 1}{h} - \lim_{h \to 0}sin(x)\dfrac{sin(h)}{h}$ since $sin(x)$ and $cos(x)$ are not part of the limit, $cos(x) \lim_{h \to 0} \dfrac{cos(h) - 1}{h} - sin(x)\lim_{h \to 0}{\dfrac{sin(h)}{h}} = cos(x)*0 - sin(x) * 1$
3. **Derivative of tangents**
   $\dfrac{d}{dx}(tg(x)) = sec^2(x)$
   Proof:
   $\dfrac{d}{dx}(tg(x)) = \dfrac{d}{dx}(\dfrac{sin(x)}{cos(x)}) = \dfrac{cos(x)\dfrac{d}{dx}(sin(x)) - sin(x)\dfrac{d}{dx}(cos(x))}{cos^2(x)} = \dfrac{cos^2(x) + sin^2(x)}{cos^2(x)}$
   $= \dfrac{1}{cos^2(x)} = sec^2(x)$
4. **Derivative of cotangents**
   $\dfrac{d}{dx}(cot(x)) = -csc^2(x)$
   Proof:
   $\dfrac{d}{dx}(tg(x)) = \dfrac{d}{dx}(\dfrac{cos(x)}{sin(x)}) = \dfrac{sin(x)\dfrac{d}{dx}(cos(x)) - cos(x)\dfrac{d}{dx}(sin(x))}{sin^2(x)} = -\dfrac{sin^2(x) + cos^2(x)}{sin^2(x)}$
   $= -\dfrac{1}{sin^2(x)} = -csc^2(x)$
5. **Derivative of secants**
   $\dfrac{d}{dx}(sec(x)) = tg(x)sec(x)$
   Proof:
   $\dfrac{d}{dx}(sec(x)) = \dfrac{d}{dx}(\dfrac{1}{cos(x)}) = \dfrac{cos(x)\dfrac{d}{dx}(1) - \dfrac{d}{dx}(cos(x))}{cos^2(x)} = \dfrac{sin(x)}{cos^2(x)} = \dfrac{sin(x)}{cos(x)} * \dfrac{1}{cos(x)}$
   $= tg(x)sec(x)$
6. **Derivative of cosecants**
   $\dfrac{d}{dx}(csc(x)) = -cot(x)csc(x)$
   Proof:
    $\dfrac{d}{dx}(csc(x)) = \dfrac{d}{dx}(\dfrac{1}{sin(x)}) = \dfrac{sin(x)\dfrac{d}{dx}(1) - \dfrac{d}{dx}(sin(x))}{sin^2(x)} = -\dfrac{cos(x)}{sin^2(x)} = -\dfrac{cos(x)}{sin(x)} * \dfrac{1}{sin(x)}$
    $= -cot(x)csc(x)$

#### Chain rule 
The chain rule is a rule for the differentiation of composite functions. Having functions $u$ and $v$ composed as $u \circ v$, the derivative of such a composite function is defined as the derivative of $u$ with respect to $v$ multiplied by the derivative of $v$ with respect to $x$, because $v$ is affected by a change in $x$ and $u$ is affected by a change in $v$. It is mathematically defined as $\dfrac{du}{dv} * \dfrac{dv}{dx}$ or $u'(v(x))v'$, where $v$ is the inner function and $u$ is the outer function, for example $(x)^2$, where $^2$ is the outer function and $x$ is the inner function. The inner function is not changed when deriving $u'$
Example: $sin(x + 5) = cos(x+5) * (\dfrac{d}{y}(x) + \dfrac{d}{y}(5)) = (x+5)cos(x) * (1 + 0) = (x+5)cos(x)$

**The chain power rule** is an extension of the chain rule for a power function, which is mathematically defined as $\dfrac{d}{dx}(v)^n = nv^{n-1}\dfrac{dv}{dx}$. 
Example: $\dfrac{d}{dx}(cos^3(x)) = -3cos^2(x)sin(x)$

#### Implicit differentiation
**Explicit differentiation** is the differentiation of a formula on the right side of $y$, whereas **implicit differentiation** is a method of differentiating both sides (e.g., differentiating the whole equation) by treating $y$ as  $y = f(x)$. The result of the derivative of $y$ is $\dfrac{dy}{dx}$. This method is used when the result of a function produces several branches, e.g., it can be represented as a single function as a result of a nonlinear variable $y$ ($xy$, $y^2$, etc.). By implicit differentiation, we can compute the derivative of $f(x)$ at $c$ knowing the $y$ at $c$ 
Example: differentiate the function $f:y^2+xy=x^2$ 
$y=f(x)$ , by applying implicit differentiation: $2y\dfrac{dy}{dx} + y + x\dfrac{dy}{dx} = 2x$  the result is $\dfrac{dy}{dx} = \dfrac{2x-y}{2y+x}$

#### Related rates
**Related rates** occur when two related quantities are changing. By knowing how the rate of change of $a$ with respect to $c$ affects the rate of change of $b$ with respect to $d$, we can compute the rate of change of $b$ with respect to $d$
For example, the area of a circle and its radius change over time $t$. Given the formula  $S = \pi r^2$, we can compute $\dfrac{dS}{t} = \dfrac{dS}{r}*\dfrac{dr}{dt} = 2\pi r*\dfrac{dr}{dt}$ Knowing $r$ and the rate $\dfrac{dr}{dt}$, we can compute the change in area over time $t$.
**Related rate problems** are usually solved by:
1. Drawing a picture 
2. Writing what we have and what we need to compute in numbers
3. Writing a related equation. You may have to combine multiple equations to get a single equation to get the rate of what you want by knowing the rate of what you know.
4. Differentiating with respect to $t$
5. Evaluate at $t$

#### Linearization and differentials 
**Linearization** is the approximation of a curve by a linear function at point $a$ with a slope that is equal to the derivative of $f(x)$ at $a$. It is mathematically defined as $L(x) = f(a) + f'(a)(x - a)$. The closer point $x$ is to $a$, the more precise the result. 
Example of the linearization of $cos(x)$ at point $a=\dfrac{\pi}{6}$. 
$f(a) = cos(\dfrac{\pi}{6}) = \dfrac{\sqrt{3}}{2}$, $f'(a) = -sin(x)\Bigg|_{x=\dfrac{\pi}{6}} = -1/2$, $L(x) = \dfrac{\sqrt{3}}{2} + \dfrac{1}{2}(x - 3)$
**A differential** is an infinitely small change (very small change) in a quantity; for example, an infinitely small change in $x$ is denoted as $dx$. We can relate multiple changes to each other (creating a differential change) using derivatives, where $dx$ is an independent variable and $dy$ is a dependent variable that depends on $x$ and $dx$ in the form $dy = f'(x) * dx$. This form is derived by assuming that if $dx$ is equal to $\Delta x$ and $x = a$, then $dy$ is a change in $y$ in the linear function at $a$ by the amount $\Delta L = L(a + dx) - L(a) = f'(a)*dx$; in other words, if $dx$ is some distance from $a$, then $dy$ is the distance of $y$ on linear function L between $a$ and $a + dx$. Sometimes the form $df = f'(x)dx,$ is used, where a function is in place of f, for example $d(sin(x)) = cos(x) dx$. <u>All formulas for derivatives can be applied to differentials</u>. 
Example: having the curve $x^2$ and $a = 3$, we have the linear function $L(x) = 6x(-3) + 9$ with point $(3,9)$. If $dx$ is equal to $0.5$, then $dy = \Delta L = f'(3)*0.5 = 6*0.5 = 3$
![[Pasted image 20260912120510.png|346]]

By dividing the whole $dy$ by $dx$, we will get $\dfrac{dy}{dx} = f'(x)$, which is used to denote derivatives.

**Approximation error** is an error created by linearization approximation, which is found by subtracting the differential change $df = f'(a)\Delta x$ from the true change $\Delta y = f(a + x) - f(a)$.
$\Delta y - df = f(a + x) - f(a) - f'(a)\Delta x = (\dfrac{f(a + x) - f(a)}{\Delta x} - f'(a))\Delta x$ where the part $\dfrac{f(a + x) - f(a)}{\Delta x} - f'(a)$ is called $\epsilon$ (a very small number); the final form is $\epsilon \Delta x$. The quotient of $\Delta y$ in $\epsilon$ approaches $f'(a)$ as $\Delta x \to 0$; thus, $\epsilon \to 0$ as $\Delta x \to 0$. $\epsilon \Delta x$ is smaller than $\Delta x$ if the change is small.
Using this notation, we can compute $\Delta y$ as $f'(a) + \epsilon \Delta x$, which can be used to prove chain rule. 

**Sensitivity to change** of $df = f'(x)dx$ tells how sensitive the function is to the effect of an error for large $x$. The bigger the change in $df$ for the same $dx$, the more the estimate is affected by an error.

#### Extremes
**Extremes** are the absolute (global) maxima and minima of a function $f$ with domain $D$.  Extremes are defined as the value at point $c$ for all $x$ in domain $D$, including $c$, where the maximum is  $f(x) \le f(c)$ and the minimum is  $f(x) \ge f(c)$. If the domain of the function is unbounded or the function is not continuous for all $x$ in domain $D$, it could fail to have an extreme. Extremes are very useful when we want to solve an optimization problem, for example, finding the smallest area of a 1 liter tin can to reduce production costs.

**Theorem of closed interval extremes**: A continuous function in a closed interval $[a, b]$ always has a maximum $M$ where $f(x) \le M$ and a minimum $m$ where$f(x) \ge m$ for all $x$ in the closed interval $[a,b]$

**Local extremes** are local maxima or minima at an interior point $c$ where, for all $x$ in $D$, including $c$, either $f(c) \ge f(x)$ (maximum) or $f(c) \le f(x)$ (minimum) in some interval. Global extremes are also local extremes.
Examples of local extremes of the function $cos(x)$ with domain $(-\infty, \infty)$ in the interval $<-\pi/2, \pi/2>$ are the local minimum $0$ and the local maximum $1$
![[Pasted image 20260914224149.png|371]]

**Theorem of the first derivative for local extremes**: if there is an interior point $c$ which is a local maximum or minimum, then its derivative $f'(c)$ is equal to $0$

Extremes could exist at:
1. interior points where $f'(x)$ is equal to zero, 
2. end points of domain
3. points where the derivative is not defined.
Interior points where $f'(x)$ is zero or the derivative is not defined are called **critical points**; however, not all critical points are local extremes. For example, the function $x^3$ with derivative $3x^2$ has $f'(x) =0$ at $x=0$, but it's not an extreme. The function $x^{1/3}$ with derivative $\dfrac{1}{3x^{2/3}}$ is not defined at $0$, but it's also not an extreme. 
![[Pasted image 20260915161352.png|257]] ![[Pasted image 20260915161500.png|261]]

**Rolle's theorem**: if there are two points, $a$ and $b$, for which $f(a) = f(b)$, e.g., there is a horizontal line between them, then in $(a,b)$ there is at least one point $c$ at which the derivative is equal to $0$

**Mean value theorem**: if we have a function f and two points, $a$ and $b$, which form a secant, and it is differentiable on the interval $(a, b)$, then there is at least one point $c$ which has the same slope as the secant, e.g., $\dfrac{f(b) - f(a)}{b - a} = f'(c)$
This could be proved by Rolle's theorem. Having the secant function $g(x) = f(a) + \dfrac{f(b) - f(a)}{b - a}(x - a)$, the vertical difference between $f$ and $g$ at $x$ is $h(x) = f(x) - g(x) = f(x) - f(a) - \dfrac{f(b) - f(a)}{b - a}(x - a)$.  If we create a diagram of $h(x)$, it will form a function with two points, $a$ and $b$, which have the same $y$ value. Rolle's theorem tells us that there is some point where $h'(c)$ is equal to $0$. By differentiating both sides of the function $h'(x)$, we will get $h'(x) = f'(x) - \dfrac{f(b) - f(a)}{b - a}$ (note: we are differentiating with respect to $x$, so $a$, $f(a)$ and $f(b)$ are constants). Then we set $x$ to $c$, $0 = f'(c) - \dfrac{f(b) - f(a)}{b - a}$, and so $f'(c) = \dfrac{f(b) - f(a)}{b - a}$
![[Pasted image 20260915170200.png|409]]

Mean value theorem consequences:
1. Only constant functions have zero derivatives over an interval, since $\dfrac{f(b) - f(a)}{b - a}$ will always be zero, so $f'(c) = 0$
2. If a function has the same nonzero derivatives over its interval as another function, $g'(x) = f'(x)$, then there is a $C$ such that $f(x) = g(x) + C$, e.g., $h(x) = f(x) - g(x) = C$, which aligns with the first consequence, since the derivative of a constant function is $0$, then $h'(x) = f'(x) - g'(x) = f'(x) - f'(x) = 0$.
3. If the derivative $f'(x)$ of a continuous function $f$  doesn't change signs over the interval $(a,b)$, then the function is either increasing if the derivative is positive ($f'(x) > 0$ for all points in $(a,b)$) or negative ($f'(x) < 0$ for all points in $(a,b)$). Such a function $f$ over the interval $(a,b)$ is called **monotonic** over the interval.

<u>A critical point has a local extreme</u> if the derivative of the function $f$ at any point in the interval before the critical point changes signs at any point in the interval after the critical point; otherwise, the critical point is not a local extreme. By checking a point before the critical point and after the critical point, we are performing the **first derivative test** to determine if the critical point is a local extreme.
1. If the derivative of the function $f$ at a point before the critical point is negative and after it is positive, then it's a **local minimum**. For example, the function $f(x) = x^2$ with derivative $f'(x) = 2x$ has a critical point at $x=0$, forming two intervals,  $(-\infty, 0)\cup(0,\infty)$. The function's derivative is negative for any point in $(-\infty, 0)$ and positive for any point in $(0,\infty)$; thus, it's a local minimum
2. If the derivative of the function $f$ at a point before the critical point is positive and after it is negative, then it's a **local maximum**. For example, the function $f(x) = -x^2$ with derivative $f'(x) = -2x$ has a critical point at $x=0$, forming two intervals,  $(-\infty, 0)\cup(0,\infty)$. The function's derivative is positive for any point in $(-\infty, 0)$ and negative for any point in $(0,\infty)$; thus, it's a local minimum

#### Concavity
**Concavity** is a turning or bending of the tangent's slope over some interval. 
1. A function is **concave down** if the slope of the tangent decreases as we move from left to right over some interval $I$ or if the secant between points $a$ and $b$ in interval $I$ is below the curve. Mathematically, if $f'(x)$ <u>is decreasing</u> over an open interval $I$, then the function is concave. Having the curve $x^3$, $f'(x)$ is decreasing from $(-\infty, 0)$ when going from left to right
2. A function is **concave up (convex)** if the slope of the tangent increases as we move from left to right over some interval $I$ or if the secant between points $a$ and $b$ in interval $I$ is above the curve. Mathematically, if $f'(x)$ <u>is increasing</u> over an open interval $I$, then the function is convex. Having the curve $x^2$, $f'(x)$ is increasing either from $(-\infty, 0]$ or $[0, \infty)$ when going from left to right
![[Pasted image 20260917114529.png|434]]

To determine concavity, we apply the mean value theorem to the first derivative $f'(x)$, similarly to how we determined if the function $f(x)$ is increasing or decreasing. 
1. if $f''(x) > 0$, then the function is **convex** over the interval $I$
2. if $f''(x) < 0$, then the function is **concave down** over the interval $I$

**An inflection point** is a point where a function changes concavity. Such a point has either a second derivative $f''(c)$ equal to 0 or a second derivative that is not defined at $f''(c)$.
1. If the second derivative changes from positive at a point before the inflection point to negative at a point after the inflection point, then the function is changing from convex to concave
2. If the second derivative changes from negative at a point before the inflection point to positive at a point after the inflection point, then the function is changing from concave to convex
3. If the signs of the points before and after the inflection point do not change, then it's not an inflection point
An example of an inflection point is $f(x) = x^3$, $f''(x) = 6x$, $c = 0$, $f''(x)$ at $(-\infty , 0)<0$ and  $f''(x)$ at $(0 ,\infty)>0$; the function is changing from concave to convex.

**The second derivative local extreme test** is a method to determine if a critical point is an extreme
1. if $f'(c) = 0$ and $f''(x) < 0$, then it's a local maximum, because $f'(x)$ is decreasing towards $f'(c)$, forming $\cap$ shape
2. if $f'(c) = 0$ and $f''(x) > 0$, then it's a local minimum, because $f'(x)$ is increasing towards $f'(c)$, forming $\cup$ shape
3. if $f'(c) = 0$ and $f''(x) = 0$, then the test fails; it's either a local minimum, maximum, or none of those

Using critical points, inflection points and asymptotes, we can accurately sketch a graph

#### Newton approximation 
Newton approximation is a method of finding the roots of an equation by approximation, assuming that the function is continuous and has a solution.  The process consists of
1. Picking a random point on the function $f$ where we think the root could be
2. Computing the tangent at the point
3. Finding the intersection $x_n$ of the tangent with the $x$ axis
4. If $x_n$ on the function $f$ doesn't have a value acceptably close to 0, repeating step 2 with $x_n$
> [!info]
> Newton approximation will find only a single solution. Which solution is found depends on the initial point $x_0$
   
> [!warning]
> The process could fail, for example, if point $x_0$ has a distance between the tangent $f(x_0) - h$ and $x_1$ has a distance between the tangent $f(x_1) + h$ that is the same as $|f(x_0) - h|$; thus, new points will cycle between $x_0$ and $x_1$.

For example, having the function $f(x)=x^2-2$, we assume that the root is at $x_0=2$, which is not $f(2) = 2$. The intersection $x_1$ of the tangent at $(x_0, f(x_0))$, whose approximation of $y=0$ is close to the root, but not the intersection $x_2$ of the tangent at $(x_1, f(x_1))$, whose approximation of $y=0$ is really close to the root (GeoGebra thinks that it's 0). So we can accept $x=1.42$ as a solution to the equation $x^2 -2 = 0$
![[Pasted image 20260918133826.png|409]]
#### Antiderivatives
An antiderivative is a function that is an inverse derivative, e.g., a function recovered from its derivative. Such a function is denoted as capital $F(x)$. Since a constant is removed during differentiation, we have an infinite number of solutions in the form $y = F(x) + C$, where C is a constant and $F(x)$ is an antiderivative. Some antiderivative formulas can be derived from derivatives.

Antiderivative formulas:
1. $x^n = \dfrac{1}{n+1}x^{n+1}$
2. $sin(kx) = -\dfrac{1}{k}cos(kx)$
3. $cos(kx) = -\dfrac{1}{k}cos(kx)$
4. $sec^2(kx) = \dfrac{1}{k}tan(kx)$
5. $csc^2(kx) = -\dfrac{1}{k}cot(kx)$
6. $kf(x) = kF(x)$
7. $f(x) + g(x) = F(x) + G(x)$

**A differential equation** is an equation in the form $\dfrac{dy}{dx} = f(x)$, since by differentiating the unknown function $y$ (this is the reason why it's called an equation), we will get $f(x)$ (its derivative). Since there could be an arbitrary constant during differentiation, we also have to know the **initial value** in the form $y(x_0) = y$ to restore the removed constant. A differential equation and an initial value form an **initial value problem**, which we can solve by knowing both. **The general solution** for a differential equation is a function in the form $y = F(x) + C$,

**An indefinite integral** is a collection of all <u>general solutions</u> for a differential equation. The integral is denoted by $\int{f(x)dx}$, where $\int$ is a symbol of integration, $f(x)$ is the **integrand**, and $x$ is a **variable of integration**.  
