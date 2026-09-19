**Differentiation** is process of searching derivate of function. **Derivation at point $x_0$** is interpreted as slope of tangent to a curve at point $x_0$ (instantenious rate) or slope of secant $x_0$ at $P(x_0, f(x_0))$. Mathematically is defined as limit of instantenious rate where $h$ approaches zero.
$f'(x_0) = \lim_{h \to 0} \dfrac{f(x_0 + h) - f(x_0)}{h}$, $x_0$ emphasise that we are computing derivation of function at point $x_0$. If such limit doesn't exists, that means, that derivation of function doesn't exists at point $x_0$
Example of derivation at point $x_0$, where slope of tangent is $f'(x_0)$
![[Pasted image 20260830114654.png|494]]

**Derivation of function** has same formula as derivation of function at point, just $x_0$ is replaced with $x$ to emphasise that we can use arbitrary x
$f'(x) =  \lim_{\Delta x \to 0} \dfrac{\Delta y}{\Delta x} \lim_{h \to 0} \dfrac{f(x + h) - f(x)}{h}$
or
$f'(x) = \lim_{z \to x} \dfrac{f(z) - f(x)}{z - x}$, where $z = x + h$ then $h = z - x$. When $z$ is equal to $x$ then $h$ is zero.

Derivation of a function can be denoted multiple ways:
$f'(x) = \dfrac{d}{dx}f(x) = \dfrac{dy}{dx} = D^1(f)(x)$
$\dfrac{d}{dx}f(x)$ = derivative of f(x) with respect to x
$\dfrac{dy}{dx}$ = derivative of y with respect to x

Derivation of function at point $a$ can be denoted as:
$f'(a) = \dfrac{d}{dx}\Bigg|_{x=a}$

If function is differentiable for all $x$, it's called differentiable function.
If function is differentiable at point $x$, it's called function, that is differentaible at point $x$

Differentation can be splited to right and left differentation, denoted as $\lim_{h \to 0+}$ and $\lim_{h \to 0-}$. 
**Existance rules**: 
* If both, left and right derivates exists and they are equal and function is continuous at point $x$, then function is differentiable at point $x$. 
* Function is differentiable on closed interval $[a, b]$ if then function is differentiable from right on $a$ and from left on $b$
* Function is differentiable on open interval $(a, b)$ if it's differentiable on all points inside interval

Some cases where it's not possible differentiate:
1. Oscilating $sin(1/x)$
    ![[Pasted image 20260823173731.png|328]]
2. Different behavior on left and right side (Point 0,0). $f(x) = |x|$
	$\lim_{h \to 0+} \dfrac{x + h - x}{h} = 1$
	$\lim_{h \to 0-} \dfrac{-x - h + x}{h} = -1$
	![[Pasted image 20260829175000.png|222]]
3. Discontinuity


We derivate function $n$ times (n-th order derivation) by performing derivation of derivation. For example, second order derivation is $f''(x)$ which is derivation of derivation, third order is derivation of derivation of derivation

derivation can be applied even when $x$ is not time, for example area of square is 
$A = a^2$, then how fast will be changed area in respect of length size, thus $x$ is size length. Result is derivation $\dfrac{dA}{da} = 2a$ $m^2/m$

When small change of $x$ makes big change of $f(x)$, then function is sensitive. Measure of sensitivity is $|f'(x)|$, the steeper is slope, the more sensitive is function
#### Derivation common formulas
1. **Derivation of constant**:
   $\dfrac{d}{dx}f(x) = 0$ for $f(x) = k$ since $\lim_{h \to 0+} \dfrac{k - k}{h} = 0$
2. **Derivation of power**:
   $\dfrac{d}{dx}f(x) = nx^{n-1}$ for $f(x) = x^n$ 
	Prove: 
	$z^n - x^n$ = $(z-x)*\sum_{k=0}^xx^ky^{n-k}$ 
	$\lim_{z \to x} \dfrac{z^n - x^n}{z - x} = \lim_{z \to x} \dfrac{(z-x)*\sum_{k=0}^xx^ky^{n-k}}{z-x} = lim_{z \to x}\sum_{k=0}^n{x^ky^{n-k}} = nx^{n-1}$ because we set $z = x$, thus $\sum_{k=0}^n{x^ky^{n-k}}$ is equal to $\sum_{k=0}^n{x^n}$
3. **Derivation of scalar $u$ multiple**:
	$\dfrac{d}{dx}f(ux) = u \dfrac{d}{dx}f(x)$
	Prove:
	$lim_{h \to 0} \dfrac{u(x + h) - u(x)}{h} = u \dfrac{(x + h) - (x)}{h}=u \dfrac{d}{dx}f(x)$
4. **Derivation of sum and difference**:
	$\dfrac{d}{dx}(u+v) = \dfrac{du}{dx} + \dfrac{dv}{dx}$
	$\dfrac{d}{dx}(u-v) = \dfrac{du}{dx} - \dfrac{dv}{dx}$
	Prove:
	$lim_{h \to 0} \dfrac{(u(x + h) + v(x + h)) - (u(x) + v(x))}{h}=lim_{h \to 0} \dfrac{u(x + h) - u(x)}{h} + \dfrac{v(x + h) - v(x)}{h}$ = $\dfrac{du}{dx} + \dfrac{dv}{dx}$
5. **Derivation of product**:
	$\dfrac{d}{dx}(u*v) = u\dfrac{dv}{dx} + v\dfrac{du}{dx}$
6. **Derivation of division**:
	$\dfrac{d}{dx}(\dfrac{u}{v}) = \dfrac{v\dfrac{du}{dx} - u\dfrac{dv}{dx}}{v^2}$
	if $v(x) \ne 0$
#### Derivation of trigonometric functions
1. **Derivation of sine**
   $\dfrac{d}{dx}(sin(x)) = cos(x)$
   Proved:
	$\lim_{h \to 0} \dfrac{sin(x + h) - sin(x)}{h} = \lim_{h \to 0} \dfrac{sin(x)cos(h) + cos(x)sin(h) - sin(x)}{h}$
	$= \lim_{h \to 0} sin(x) \dfrac{cos(h) - 1}{h} + \lim_{h \to 0}cos(x)\dfrac{sin(h)}{h}$ since $sin(x)$ and $cos(x)$ are not part of limit, $sin(x) \lim_{h \to 0} \dfrac{cos(h) - 1}{h} + cos(x)\lim_{h \to 0}\dfrac{sin(h)}{h}$ both are known limits, $sin(x)*0 + cos(x) * 1$
2. **Derivation of cosine**
   $\dfrac{d}{dx}(cos(x)) = -sin(x)$
    Proved:
	$\lim_{h \to 0} \dfrac{cos(x + h) - cos(x)}{h} = \lim_{h \to 0} \dfrac{cos(x)cos(h) - sin(x)sin(h) - cos(x)}{h}$
	$= \lim_{h \to 0} cos(x) \dfrac{cos(h) - 1}{h} - \lim_{h \to 0}sin(x)\dfrac{sin(h)}{h}$ since $sin(x)$ and $cos(x)$ are not part of limit, $cos(x) \lim_{h \to 0} \dfrac{cos(h) - 1}{h} - sin(x)\lim_{h \to 0}{\dfrac{sin(h)}{h}} = cos(x)*0 - sin(x) * 1$
3. **Derivation of tangents**
   $\dfrac{d}{dx}(tg(x)) = sec^2(x)$
   Proved:
   $\dfrac{d}{dx}(tg(x)) = \dfrac{d}{dx}(\dfrac{sin(x)}{cos(x)}) = \dfrac{cos(x)\dfrac{d}{dx}(sin(x)) - sin(x)\dfrac{d}{dx}(cos(x))}{cos^2(x)} = \dfrac{cos^2(x) + sin^2(x)}{cos^2(x)}$
   $= \dfrac{1}{cos^2(x)} = sec^2(x)$
4. **Derivation of cotangents**
   $\dfrac{d}{dx}(cot(x)) = -csc^2(x)$
   Proved:
   $\dfrac{d}{dx}(tg(x)) = \dfrac{d}{dx}(\dfrac{cos(x)}{sin(x)}) = \dfrac{sin(x)\dfrac{d}{dx}(cos(x)) - cos(x)\dfrac{d}{dx}(sin(x))}{sin^2(x)} = -\dfrac{sin^2(x) + cos^2(x)}{sin^2(x)}$
   $= -\dfrac{1}{sin^2(x)} = -csc^2(x)$
5. **Derivation of secans**
   $\dfrac{d}{dx}(sec(x)) = tg(x)sec(x)$
   Proved:
   $\dfrac{d}{dx}(sec(x)) = \dfrac{d}{dx}(\dfrac{1}{cos(x)}) = \dfrac{cos(x)\dfrac{d}{dx}(1) - \dfrac{d}{dx}(cos(x))}{cos^2(x)} = \dfrac{sin(x)}{cos^2(x)} = \dfrac{sin(x)}{cos(x)} * \dfrac{1}{cos(x)}$
   $= tg(x)sec(x)$
6. **Derivation of cosecans**
   $\dfrac{d}{dx}(csc(x)) = -cot(x)csc(x)$
   Proved:
    $\dfrac{d}{dx}(csc(x)) = \dfrac{d}{dx}(\dfrac{1}{sin(x)}) = \dfrac{sin(x)\dfrac{d}{dx}(1) - \dfrac{d}{dx}(sin(x))}{sin^2(x)} = -\dfrac{cos(x)}{sin^2(x)} = -\dfrac{cos(x)}{sin(x)} * \dfrac{1}{sin(x)}$
    $= -cot(x)csc(x)$

#### Chain rule 
Chain rule is rule for differentation of composed functions. Having function $u$ and $v$ composed as $u \circ v$, derivation of such composed function is defined as derivation of $u$ in respect $v$ multiplied by derivation of $v$ in respect of $x$, because $v$ is affected by change of $x$ and $u$ is affected by change of $v$. Mathematically defined as $\dfrac{du}{dv} * \dfrac{dv}{dx}$ or $u'(v(x))v'$, where $v$ is inner function and $u$ is outside function, for example $(x)^2$, where $^2$ is outside function and $x$ is inner function. Inner function is not changed when deriving $u'$
Example: $sin(x + 5) = cos(x+5) * (\dfrac{d}{y}(x) + \dfrac{d}{y}(5)) = (x+5)cos(x) * (1 + 0) = (x+5)cos(x)$

**Chain power rule** is extension of chain rule for power function, which is mathematically defined as $\dfrac{d}{dx}(v)^n = nv^{n-1}\dfrac{dv}{dx}$. 
Example: $\dfrac{d}{dx}(cos^3(x)) = -3cos^2(x)sin(x)$

#### Implicit differentiation
**Expliciting differentiation** is differentation of a formula on right side of $y$, whereas **implicit differentiation** is method of differentation of both sides (e.g differentation of the whole equation) by threating $y$ as  $y = f(x)$. Result of derivation of $y$ is $\dfrac{dy}{dx}$. This method is used when result of function produces several branches, e.g can be represented as single function as result of non linear variable $y$ ($xy$, $y^2$ and etc). By implicit derivation we can compute derivation of $f(x)$ at $c$ knowing the $y$ at $c$ 
Example: differentatiate function $f:y^2+xy=x^2$ 
$y=f(x)$ , by applying implicit derivation: $2y\dfrac{dy}{dx} + y + x\dfrac{dy}{dx} = 2x$  result is $\dfrac{dy}{dx} = \dfrac{2x-y}{2y+x}$

#### Related rates
**Related rates** is when two related quantites are changing. By knowing how rate of change $a$ in respect of $c$ affects rate of change $b$ in respect of $d$, we can compute rate of change of $b$ in respect of $d$
For example, area of circle and radius changes by time $t$. Given formula  $S = \pi r^2$ we can compute $\dfrac{dS}{t} = \dfrac{dS}{r}*\dfrac{dr}{dt} = 2\pi r*\dfrac{dr}{dt}$ Knowing $r$ and rate $\dfrac{dr}{dt}$ we can compute change of area in time $t$.
**Related rate problems** are usually solved by:
1. Drawing a picture 
2. Writing what we have and we need to compute in numbers
3. Write relating equation. You may have to combine multiple equations to get single equation to get rate of what you want by knowing rate of you know.
4. Differentatiate in respect of $t$
5. Evaluate at $t$

#### Linearization and differentials 
**Linearization** is approximation of curve by linear function at point $a$ with slope that is equal to derivation of $f(x)$ at $a$. Mathematically defined as $L(x) = f(a) + f'(a)(x - a)$. The closer is point $x$ to $a$, the more precise is the result. 
Example linearization of $cos(x)$ at point $a=\dfrac{\pi}{6}$. 
$f(a) = cos(\dfrac{\pi}{6}) = \dfrac{\sqrt{3}}{2}$, $f'(a) = -sin(x)\Bigg|_{x=\dfrac{\pi}{6}} = -1/2$, $L(x) = \dfrac{\sqrt{3}}{2} + \dfrac{1}{2}(x - 3)$
**Differential** is infinitely small change (very small change) of quantity, for example inifinetely small change of $x$ is denoted as $dx$. We can relate multiple changes to each other (creating differentiatial change) using derivates, where $dx$ is independant variable and $dy$ is dependant variable that depends on $x$ and $dx$ in form of $dy = f'(x) * dx$. This form is derived asumming that if $dx$ is equal to $\Delta x$ and $x = a$, then $dy$ is a change of $y$ in linear function at $a$ by amount $\Delta L = L(a + dx) - L(a) = f'(a)*dx$, in other words, if $dx$ is some distance from $a$, then $dy$ distance of $y$ on linear function L between $a$ and $a + dx$. Sometimes is used form $df = f'(x)dx,$ where in place of f is a function, for example $d(sin(x)) = cos(x) dx$. <u>All formulas for derivation can be applied for differentials</u>. 
Example: having curve $x^2$ and $a = 3$ we have linear function $L(x) = 6x(-3) + 9$ with point $(3,9)$. If $dx$ is equal to $0.5$, then $dy = \Delta L = f'(3)*0.5 = 6*0.5 = 3$
![[Pasted image 20260912120510.png|346]]

By dividing whole $dy$ with $dx$, we will get $\dfrac{dy}{dx} = f'(x)$ which is used to denote derivatives.

**Approximation error** is an error created by linearization appromixation which is by subtracting differentiatial change $df = f'(a)\Delta x$ from true change $\Delta y = f(a + x) - f(a)$.
$\Delta y - df = f(a + x) - f(a) - f'(a)\Delta x = (\dfrac{f(a + x) - f(a)}{\Delta x} - f'(a))\Delta x$ where part $\dfrac{f(a + x) - f(a)}{\Delta x} - f'(a)$ is called $\epsilon$ (very small number), final form is $\epsilon \Delta x$. The quatient of $\Delta y$ in $\epsilon$ approaches $f'(a)$ as $\Delta x \to 0$ thus $\epsilon \to 0$ as $\Delta x \to 0$. $\epsilon \Delta x$ is smaller than $\Delta x$ if change is small.
Using this notation, we can compute $\Delta y$ as $f'(a) + \epsilon \Delta x$, which can be used to prove chain rule. 

**Sensitivity to change** of $df = f'(x)dx$ tells how much is function sensitive to effect of an error for large $x$. The bigger change of $df$ for same $dx$, the more estimate is affected by an error.

#### Extremes
**Extremes** are absolute (global) maxima and minima of function $f$ with domain $D$.  Extremes are defined as value at point $c$ for all $x$ in domain $D$ including $c$, where maximum is  $f(x) \le f(c)$ and minimum is  $f(x) \ge f(c)$. If domain of function is unbound or function is not contineous for all $x$ in domain $D$, it could fail to have a extreme. Extremes are very useful when we want to solve optimization problem, for example finding smallest area of 1 liter tin can to reduce production cost.

**Theorem of closed interval extremes**: Contineous function in closed interval $[a, b]$ always have maximum $M$ where $f(x) \le M$ and minimum $m$ where$f(x) \ge m$ for all $x$ in closed interval $[a,b]$

**Local extremes** are local maxima or minima at point interior point $c$ that for all $x$ in $D$ including $c$ are either $f(c) \ge f(x)$ (maxima) or $f(c) \le f(x)$ (minima) in some interval. Global extremes are also a local extremes.
Example of local extremes of function $cos(x)$ with domain $(-\infty, \infty)$ in interval $<-\pi/2, \pi/2>$ are local minimum $0$ and  local maximum $1$
![[Pasted image 20260914224149.png|371]]

**Theorem of first derivate for local extremes**: if there is interior point $c$ which is local maximum or minimum, then it's derivation $f'(c)$ is equal $0$

Extremes could existing in:
1. interior points where $f'(x)$ is equal to zero, 
2. end points of domain
3. point, where derivation is not defined.
Interior points, where $f'(x)$ is zero or derivation is not defined are called **critical points**, however not all critical points are are local extremes. For example, function $x^3$ with derivation $3x^2$ has $f'(x) =0$ at $x=0$, but it's not an extreme. function $x^{1/3}$ with derivation $\dfrac{1}{3x^{2/3}}$ is not defined at $0$ but it's also not an extreme. 
![[Pasted image 20260915161352.png|257]] ![[Pasted image 20260915161500.png|261]]

**Rolles theorem**: if there is a two points, $a$ and $b$, which $f(a) = f(b)$, e.g there is horizontal line between them, then there in $(a,b)$ is at least one point $c$ which derivation is equal to $0$

**Mean value theorem**: if we have function f and two points, $a$ and $b$, which form secant, and is differentiaable on interval $(a, b)$ then there is at least one point $c$, which has same slope as secant, e.g $\dfrac{f(b) - f(a)}{b - a} = f'(c)$
This could be proved by rolles theorem. Having secant function $g(x) = f(a) + \dfrac{f(b) - f(a)}{b - a}(x - a)$, vertical difference between $f$ and $g$ at $x$ are $h(x) = f(x) - g(x) = f(x) - f(a) - \dfrac{f(b) - f(a)}{b - a}(x - a)$.  If create diagram of $h(x)$, it will form a function with two points, $a$ and $b$, which have same $y$ value. Rolles theorem tells us, that there is some point, where $h'(c)$ is equal $0$. By derivation of both sides of function $h'(x)$, we will get $h'(x) = f'(x) - \dfrac{f(b) - f(a)}{b - a}$ (notes: we are deriving in respect of $x$, so $a$, $f(a)$ and $f(b)$ are constants). Then we set $x$ to $c$, $0 = f'(c) - \dfrac{f(b) - f(a)}{b - a}$ and so $f'(c) = \dfrac{f(b) - f(a)}{b - a}$
![[Pasted image 20260915170200.png|409]]

Mean value theorem consequences:
1. Only constant function have zero derivatives over interval, since $\dfrac{f(b) - f(a)}{b - a}$ will be always zero, so $f'(c) = 0$
2. If function have same non zero derivatives over it's interval as other function, $g'(x) = f'(x)$, then there is $C$ such that $f(x) = g(x) + C$, e.g $h(x) = f(x) - g(x) = C$, which aligns with first consequence, since derivation of constant function is $0$, then $h'(x) = f'(x) - g'(x) = f'(x) - f'(x) = 0$.
3. If derivation $f'(x)$ of contineous function $f$  doesn't change signess over interval $(a,b)$, then function is either increasing if derivation is positive ($f'(x) > 0$ for all points in $(a,b)$) or negative ($f'(x) < 0$ for all points in $(a,b)$). Such function $f$  over interval $(a,b)$ is called **monotonic** over interval.

<u>Critical point has an local extreme</u> if derivation of function $f$ at any point of interval before critical point changes signess at any point of interval after critical point, otherwise critical point is not an local extreme. By checking point before critical point and after critical points, we are performing **first derivate test** to determine if critical point is an local extreme.
1. If derivation of function $f$ at point before critical point negative and after is positive, then it's **local minimum**. For example function $f(x) = x^2$ with derivation $f'(x) = 2x$ has critical point at $x=0$ and forming two intervals,  $(-\infty, 0)\cup(0,\infty)$. The function derivation is negative for any point at $(-\infty, 0)$ and positive for any point at $(0,\infty)$, thus it's local minimum
2. If derivation of function $f$ at point before critical point positive and after is negative, then it's **local maximum**. For example function $f(x) = -x^2$ with derivation $f'(x) = -2x$ has critical point at $x=0$ and forming two intervals,  $(-\infty, 0)\cup(0,\infty)$. The function derivation is positive for any point at $(-\infty, 0)$ and negative for any point at $(0,\infty)$, thus it's local minimum

#### Concativity
**Concavity** is a turning or bending of tangets slope over some interval. 
1. Function is **concave down** if slope of tangent decreases as we move from left to right over some interval $I$ or if secant between points $a$ and $b$ in interval $I$ is below curve. Mathematicaly, if $f'(x)$ <u>is decreasing</u> over open interval $I$, then function is concave. Having curve $x^3$, $f'(x)$ is decreasing from $(-\infty, 0)$ when coming from left to right
2. Function is **concave up (convex)** if slope of tangent increases as we move from left to right over some interval $I$ or if secant between points $a$ and $b$ in interval $I$ is above curve. Mathematicaly, if $f'(x)$ <u>is increasing</u> over open interval $I$, then function is convex. Having curve $x^2$, $f'(x)$ is increasing either from $(-\infty, 0]$ or $[0, \infty)$ when coming from left to right
![[Pasted image 20260917114529.png|434]]

To determine concavity, we apply mean value theorem on first derivation $f'(x)$, similarly as we did for determining if function $f(x)$ is increasing or decreasing. 
1. if $f''(x) > 0$, then function is **convex** over interval $I$
2. if $f''(x) < 0$, then function is **concave down** over interval $I$

**Inflection point** is point where function changes concavity. Such point has either second derivation $f''(c)$ equal to 0 or second derivation is not defined at $f''(c)$.
1. If second derivation is changes from positive at point before inflection point to negative at point after inflection point, then it's function is changing from convex to concave
2. If second derivation is changes from negative at point before inflection point to positive at point after inflection point, then it's function is changing from concave to convex
3. If signess of points before and inflection point is not changing, then it's not an inflection point
Example of inflection point is $f(x) = x^3$, $f''(x) = 6x$, $c = 0$, $f''(x)$ at $(-\infty , 0)<0$ and  $f''(x)$ at $(0 ,\infty)>0$, function is changing from concave to convex.

**Second derivation local extreme test** is method to determine if critical point is an extreme
1. if $f'(c) = 0$ and $f''(x) < 0$, then it's a local maximum, because $f'(x)$ is decreasing towards $f'(c)$, forming $\cap$ shape
2. if $f'(c) = 0$ and $f''(x) > 0$, then it's a local minimum, because $f'(x)$ is increasing towards $f'(c)$, forming $\cup$ shape
3. if $f'(c) = 0$ and $f''(x) = 0$, then test fails, it's either an local minimum, maximum or non of that

Using critical points, inflection points and asymptotes, we can accurately sketch a graph

#### Newton appromixation 
Newton approximation is a method of finding roots of equation by approximation, assuming that function is contineous and have solution.  Process consists of
1. Picking random point on function $f$ where we think root could be
2. Compute tanget at point
3. Find intersection $x_n$ of tangent with $x$ axis
4. If $x_n$ on function $f$ doesn't have value acceptably close to 0, repeat step 2 with $x_n$
> [!info]
> Netwton approximation will find only single solution. Which solution is found does depend on initial point $x_0$
   
> [!warning]
> Process could fail, for example if point $x_0$ has distance between tanget $f(x_0) - h$ and $x_1$ has distance between tanget $f(x_1) + h$ that is same as $|f(x_0) - h|$, thus new points will cycle between $x_0$ and $x_1$.

For example, having function $f(x)=x^2-2$ we assume, that root is on $x_0=2$, which is not $f(2) = 2$. Intersection $x_1$ of tanget on $(x_0, f(x_0))$ which approximation of $y=0$ is close to root, but not Intersection $x_2$ of tanget on $(x_1, f(x_1))$ which approximation of $y=0$ is really close to root (geogebra thinks that it's 0), So we can accept $x=1.42$ as solution for equation $x^2 -2 = 0$
![[Pasted image 20260918133826.png|409]]
#### Antiderivatives
Antiderivative is function, that is inverse derivative, e.g function, recovered from it's derivative. Such function is denoted as capital $F(x)$. Since constant is removed during derivation, then we have infinity amount of solution in form $y = F(x) + C$, where C is a constant and $F(x)$ is antiderivative. Some antiderivative formulas can derived from derivates.

Antiderivative formulas:
1. $x^n = \dfrac{1}{n+1}x^{n+1}$
2. $sin(kx) = -\dfrac{1}{k}cos(kx)$
3. $cos(kx) = -\dfrac{1}{k}cos(kx)$
4. $kf(x) = kF(x)$
5. $f(x) + g(x) = F(x) + G(x)$

**Differential equation** is equation in form $\dfrac{dy}{dx} = f(x)$, since by derivation of uknown function $y$ (this is the reason why it's called equation) we will get $f(x)$ (it's derivation). Since during differentation there could be arbitrary constant, we also have to know **initial value** in form $y(x_0) = y$ to restore removed constant. Differential equation and initial value forms **initial value problem**, which we can solve knowing both. **General solution** for differential equation is function in form $y = F(x) + C$,

**Indefinite integral** is a collection all <u>general solutions</u> for differential equation. Integral is denoted with $\int{f(x)dx}$, where $\int$ is a symbol of integration, $f(x)$ is **integrand** and $x$ is a **variable of integration**. 