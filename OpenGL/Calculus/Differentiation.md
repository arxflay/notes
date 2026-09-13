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
