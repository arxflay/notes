If we have <u>a finite interval</u> $[a, b]$, then, using subintervals, we can approximate the area under a function by computing the sum of the areas of squares with height $y$ at some point in a subinterval, multiplied by the width of the interval. Such an area could be interpreted as the average value of a continuous function on a finite interval if it is divided by the interval length ($||b-a||$), or as the cumulative change in $y$ with respect to $x$ if $f$ is $\dfrac{dy}{dx}$.

**Riemann sums** are a generalization of such sum approximations on a finite interval, where the interval $[a,b]$ is subdivided by $n$ points (each point is an $x$ value), where all subsequent points are greater or less than the previous points (as if we were approaching from the other side, with the consequence that the sum becomes negative), forming a sequence of points $P = \{x_0, x_1...x_{n-1}, x_n\}$ where $x_0=a$ and $x_n= b$. Then each point is subdivided by intervals. Partition $P$  $\{[x_0, x_1]...[x_{k-1}, x_k]...x_n, x_n+1\}$, where $k$ is a value between $1$ and $n$, is called **partitioning**. Each interval has a width $\Delta x_k = x_k - x_{k-1}$, not necessarily an equal width, but if the widths are equal, then the width is denoted as $\Delta x = (b-a)/n$ for all subintervals.
![[OpenGL/images/calculus-riemann-partition-subintervals.png|525]]
By computing the sum of function values at arbitrarily selected points in a subinterval, multiplied by the width of the subinterval, we can approximate the function's area. This is mathematically denoted as $S_{p} = \sum{f(c_k)\Delta x_k}$, where $c_k$ is an arbitrarily selected point and $\Delta x_k$ is the width of the subinterval. There are an unlimited number of ways to select $c_k$, including the **upper sum**, **lower sum**, and **midpoint sum**, and there are an unlimited number of ways to partition. 

The largest width of a subinterval is denoted as the norm $||P||$ (the Chebyshev norm applied to a vector of widths).
* If each interval has an equal width ($||P|| = \Delta x$), then the smaller $\Delta x$ is, e.g., as $\Delta x$ approaches $0$ and the number of intervals $n$ approaches $\infty$, the more precise the approximation is. 
* If the lengths of the subintervals are not equal, then the precision is determined by the largest width of a subinterval, $||P||$. The smaller $||P||$ is, the more precise the approximation will be.
Example of arbitrarily selected points $c_k$ in the interval $[0,1]$ on $f(x) = \sqrt{1-x^2}$. The sum of the areas of the squares is an approximation of the area under the curve.
![[OpenGL/images/calculus-riemann-sum-arbitrary-sample-points.png|506]]

There are 4 common summation methods:
1. **Upper sum(Left rule)**: the $c_k$ value is picked at the beginning of a subinterval of length $\Delta x_k$. The upper sum is usually bigger than the area under $f$. 
   With equal widths, the upper sum can be expressed as $\sum_{k=1}^{n}f(a+(k-1)\Delta x)\Delta x$, where $k$ is the index of the first element, $n$ is the number of intervals, $a$ is the beginning of the interval, and $(k-1)$ is the beginning of the subinterval. 
   Example: having the interval $[0,1]$ and $n=2$, we have $\Delta x= (1-0) / 2 = 1/2$  and $\sum_{k=1}^{2}f(0+\Delta x(k-1))\Delta x =  f(0 + \Delta{x}(1-1))\Delta x + f(0 + \Delta{x}(2-1))\Delta x = f(0)\Delta x + f(1/2)\Delta x$
2. **Lower sum(Right rule)**: the $c_k$ value is picked at the end of a subinterval of length $\Delta x_k$. The lower sum is usually smaller than the area under $f$. 
   With equal widths, the lower sum can be expressed as $\sum_{k=1}^{n}f(a+k\Delta x)\Delta x$, where $k$ is the index of the first element, $n$ is the number of intervals, $a$ is the beginning of the interval, and $k$ is the end of the subinterval. 
   Example: having the interval $[0,1]$ and $n=2$, we have $\Delta x= (1-0) / 2 = 1/2$  and $\sum_{k=1}^{2}f(0+k\Delta x)\Delta x =  f(0 + \Delta{x})\Delta x + f(0 + 2\Delta{x})\Delta x = f(1/2) \Delta{x} + f(1)\Delta{x}$
3. **Midpoint sum (Midpoint rule)**: the $c_k$ value is picked at the middle of a subinterval of length $\Delta x_k$. The midpoint sum could be bigger or smaller than the area under $f$. 
   With equal widths, the midpoint sum can be expressed as $\sum_{k=1}^{n}f(a + (k-1)\Delta x + \Delta x/2)\Delta x$, where $k$ is the index of the first element, $n$ is the number of intervals, $a$ is the beginning of the interval, and $(k-1)\Delta x + \Delta x/2$ is the midpoint of the subinterval. 
   Example: having the interval $[0,1]$ and $n=2$, we have $\Delta x=1/2$  and $\sum_{k=1}^{2}f(0 + (k-1)\Delta x + \Delta x/2)\Delta x$
   $= f(0 + (1-1) + 1/2\Delta{x})\Delta x + f(0 + (2-1) + 1/2\Delta{x})\Delta x = f(1/4) + f(3/4)$
4. **Trapezoid rule**: the sum is computed differently; instead of summing the areas of squares, we compute the sum of the areas of trapezoids. 
   $\sum_{k=1}^{n}\dfrac{\Delta x(f(a + (k-1)\Delta x)+f(a + k\Delta x))}{2}$
   ![[OpenGL/images/calculus-trapezoid-rule-subinterval.png|230]]
All Riemann summation methods are trapped between the upper and lower sums. The real value lies somewhere between the upper sum and the lower sum.

By computing the limit as $lim_ {n \to \infty}$ (if such a limit exists), we can get the exact value of the area.
Example of approximating the area using equal-width intervals whose width approaches $0$:
Approximate the area of $f(x) = 1-x^2$ on the interval $<0,1>$ as precisely as possible. 
1. First, we divide $[0,1]$ into $n$ equal-width subintervals $\{[0, 1/n], [1/n, 2/n]....[(n-1)/n, n]\}$ with length $\Delta x = 1/n$. 
2. Construct and simplify the lower-sum approximation. 
   $\sum_{k=1}^{n}f(a+k\Delta x)\Delta x = \sum_{k=1}^{n} f(k\dfrac{1}{n})\dfrac{1}{n} = \dfrac{1}{n}\sum_{k=1}^{n} 1 - \dfrac{k^2}{n^2} = \dfrac{1}{n}(\sum_{k=1}^{n} 1 - (\dfrac{1}{n^2}*\sum_{k=1}^{n}k^2))$ The sum of $k^2$ can be expressed as a sum of squares. 
   $\sum_{k=1}^{n}f(a+k\Delta x)\Delta x = \dfrac{1}{n}(n - (\dfrac{1}{n^2}*\dfrac{n*(n+1)(2n+1)}{6}) = 1 - \dfrac{2n^3+3n^2 + n}{6n^3}$
3. Compute the limit as $n$ approaches infinity: $\lim_{n \to \infty} 1 - \dfrac{2n^3+3n^2 + n}{6n^3}=1 - 1/3 = \dfrac{2}{3}$.
The area of $f(x) = 1-x^2$ on the interval $<0,1>$ is $\dfrac{2}{3}$.
### Definite integral 
**A definite integral** is a number $J$ to which the limit of Riemann sums converges as $n$ approaches $\infty$. 
If there is a value $\epsilon > 0$ representing an acceptable error from $J$ and a value $\delta$ such that any norm $||P|| < \delta$ is a solution for $|(\sum_{k=1}^n{f(c_k)\Delta{x_k}}) - J| < \epsilon$, regardless of which partition method or method of selecting $c_k$ we use, then the definite integral could exist and is equal to the limit of Riemann sums as $n$ approaches $\infty$. 
The definite integral is denoted as $\int_a^b{f(x)dx}$.
1. $\int$ is a symbol of integration that replaces $\sum$. 
2. $a$ is the lower limit. 
3. $b$ is the upper limit.
4. $f(x)$ is the **integrand**, where $c_k$ is replaced with $x$ to emphasize that the integral is a sum of continuous values.
5. $x$ is a **variable of integration**, and $dx$ is a differential that emphasizes that the norm $||P||$ is approaching $0$. $dx$ is a dummy variable.
Since we can use any method of partitioning and selecting $c_k$, we can define the definite integral as a Riemann sum partitioned into equal widths $\Delta x = \dfrac{b-a}{n}$, where each $c_k$ is selected by the **right rule**.
$\int_a^b{f(x)dx} =  \sum_{k=1}^n{f(a+k\Delta x)\Delta x} = \sum_{k=1}^n{f(a+k\dfrac{b-a}{n})\dfrac{b-a}{n}}$
If we know how to compute the area under a function using some formula, then $\int_a^b{f(x)dx} = formula$.

A definite integral always exists if the function $f$ is continuous over the interval $[a,b]$ or if the function has a finite removable discontinuity. It fails if $f$ does not have a sufficiently finite removable discontinuity because different methods of selecting $c_k$ could produce different values.

Common formulas:
1. $\int_b^a{f(x)dx} = -\int_a^b{f(x)dx}$ - as if we were approaching the function from right to left; thus, $\Delta{x}$ becomes negative.
2. $\int_a^a{f(x)dx} = 0$ - since the length of $\Delta x$ is $0$. 
3. $\int_a^b{hf(x)dx} = h\int_a^b{f(x)dx}$ - since the definite integral is $\sum_{k=1}^n{f(k\Delta x)\Delta x}$, then $\sum_{k=1}^n{hf(k\Delta x)\Delta x} = h\sum_{k=1}^n{f(k\Delta x)\Delta x}=h\int_a^b{f(x)dx}$. Graphically, the function becomes scaled by $h$, as does the area under the function.
4. $\int_a^b({f(x) \pm g(x))dx} = \int_a^b{f(x)}dx \pm \int_a^b{g(x)dx}$ - using sum notation, we can separate the two expressions. Graphically, it is the sum/difference of the areas under $f(x)$ and $g(x)$.
5. $\int_a^b{f(x)}dx + \int_b^c{f(x)}dx = \int_a^c{f(x)}dx$. Graphically, the area under $f$ on $[a,b]$ becomes expanded by the area under $f$ on $[b,c]$.
6. (**Min-max inequality**) If $f$ has maximum and minimum values on $[a,b]$, then $f_{min} * (b-a) \le \int_a^b{f(x)}dx  \le f_{max} * (b-a)$ because the values are trapped between the maximum and minimum values.
7. (**Domination**) If $f(x)$ is bigger everywhere on $[a,b]$ than $g(x)$, then $\int_a^b{f(x)}dx > \int_a^b{f(x)}dx$.

**The value of a definite integral** is the area under a function <u>only if the function is positive</u> on the interval $[a,b]$. Assuming the function $f(x)=x$ on the positive interval $[0,b]$, we have two ways to compute the area:
1. Using the Riemann sum limit as $n$ approaches $\infty$ by partitioning the interval $[0,b]$ into $n$ intervals of width $\Delta x = \dfrac{(b-0)}{n} = \dfrac{b}{n}$ and using the **right rule**.
   $\int_0^b{f(x)dx} =  \sum_{k=1}^n{f(k\dfrac{b}{n})\dfrac{b}{n}} = \sum_{k=1}^n{k\dfrac{b}{n}\dfrac{b}{n}} = \dfrac{b^2}{n^2}\sum_{k=1}^n{k} = \dfrac{b^2}{n^2}*\dfrac{n(n+1)}{2} = \dfrac{b^2}{2}*(1+\dfrac{1}{n})$
   $= \lim_{n \to \infty} \dfrac{b^2}{2}*(1+\dfrac{1}{n}) = \dfrac{b^2}{2}$
2. By computing the area of a triangle, which is equal to $\dfrac{b*b}{2} = \dfrac{b^2}{2}$ = $\int_0^b{f(x)dx}$.
This proves the definition of a definite integral.

A generalized variant of the definite integral of $f(x) = x$ on $[a,b]$ if $a > 0$ and $b > a$ is:
$\int_a^b{f(x)dx} = \int_a^0{f(x)dx} + \int_0^b{f(x)dx} = -\int_0^a{f(x)dx} + \int_0^b{f(x)dx} = - \dfrac{a^2}{2} + \dfrac{b^2}{2} = \dfrac{b^2}{2} - \dfrac{a^2}{2}$
If $a < b < 0$, then the formula still works, but the definite integral is a negative area. If $b > 0$ but $a < 0$, then the definite integral is the difference between the areas.

**The average value of a function on $[a,b]$** can be computed using a definite integral via  $\dfrac{1}{b-a}\int_a^b{f(x)dx}$, as if the values $f(x)$ were sampled across the intervals $b-a$.

**The mean value theorem for definite integrals** states that if a definite integral exists on the closed interval $[a,b]$ for a continuous function $f$, then there is a value $c$ in the interval $[a,b]$ where the height $f(c)$   multiplied by the width of the interval $(b-a)$ is equal to the value of the definite integral (the area under the function $f$ on the interval $(b,a)$).
$f(c)*(b-a) = \int_a^b{f(x)dx}$ 
As a consequence of this theorem, there is a point $f(c)$ whose value is equal to the average value of the definite integral.
$f(c) = \dfrac{1}{(b-a)}\int_a^b{f(x)dx}$
This is proved using the **Min-max inequality** by dividing both sides by $(b-a)$.
$f_{min} \le \dfrac{1}{(b-a)}\int_a^b{f(x)}dx  \le f_{max}$; by the intermediate value theorem, there must be an $f(c)$ between $f_{min}$ and $f_{max}$.
![[OpenGL/images/calculus-integral-mean-value-theorem.png|334]]

**The fundamental theorem of calculus** is a theorem that connects differentiation with integration to simplify the calculation of integrals, since computing an integral using Riemann sums is harder and is sometimes impossible. Instead, we can compute integrals using antiderivatives.

**Fundamental theorem part 1** states that there is a function $F(x)$ whose value at the upper limit $x$ is equal to the definite integral for $f(t)$ from $a$ to $x$ if $f(t)$ is integrable over the interval $I$, where $a\in I$ and $x \in I$.
$F(x) = \int_a^x{f(t)dt}$, 
and, as a consequence, $f(x)$ is equal to $F'(x)$, 
$F'(x) = f(x)$
Since $F'(x) = F(x + h) - F(x)$, $F(x)$ is the area from $a$ to $x$, and $F(x + h)$ is the area from $a$ to $x + h$. The difference gives the area between $x$ and $x+h$. We can approximate this difference using $f$ at $x$ by the area of a square, which is equal to $hf(x)$: $F(x + h) - F(x) \approx hf(x)$. Dividing both sides by $h$, we get $\dfrac{F(x + h) - F(x)}{h} \approx f(x)$, and computing the limit as $h \to 0$, we get $F'(x) = f(x)$.

Since $F'(x) = f(x)$ and $F(x) = \int_a^x{f(t)dt}$, then 
$F'(x) = \dfrac{d}{dx}\int_a^x{f(t)dt} = f(x)$ 
where $dt$ is a dummy variable because $y$ depends on $x$.
*Proof*: $F'(x) = \dfrac{F(x + h) - F(x)}{h}$. By fundamental theorem part 1, we can write $F(x)$ as $\int_a^x{f(t)dt}$, so $F'(x) = \lim_{h \to 0}\dfrac{1}{h}(\int_a^{x+h}{f(t)dt} - \int_a^x{f(t)dt}) = \lim_{h \to 0}\dfrac{1}{h}(\int_a^{x}{f(t)dt} + \int_x^{x+h}{f(t)dt} - \int_a^x{f(t)dt})$
$= \lim_{h \to 0}\dfrac{1}{h}\int_x^{x+h}{f(t)dt}$
By the mean value theorem, there is an $f(c)$ that is equal to $\dfrac{1}{(b-a)}\int_a^b{f(x)dx}$, where $(b-a)$ is $h$, so $F'(x)=\lim_{h \to 0}\dfrac{1}{h}\int_x^{x+h}{f(t)dt}=\lim_{h \to 0}f(c)$. Since $h$ approaches $x$ and $c$ is between $x$ and $x+h$, then $lim_{h \to 0}f(c) = f(x)$.

Examples:
1. $\dfrac{d}{dx}\int_a^x{t}\ dt = x$ since $f(x) = x$ 
2.  $\dfrac{d}{dx}\int_x^a{2}\ dt = \dfrac{d}{dx}-\int_a^x{2}\ dt = -\dfrac{d}{dx}\int_a^x{2}\ dt = -2$ since $f(x) = 2$ 
If the upper limit is not equal to a single variable $x$, we can use the chain rule $\dfrac{dy}{dx} = \dfrac{dv}{du}*\dfrac{du}{dx}$, where the upper limit $f(x)$ is an inner function substituted with $u$,  forming $\dfrac{d}{dx}(\int_a^{f(x)}{f(t)}\ dt) = \dfrac{dv}{du}(\int_a^u{f(t)}\ dt)*\dfrac{du}{dx}$.
3. $\dfrac{d}{dx}\int_a^{x^2}{\sqrt{t}}\ dt, u=x^2$
   $\dfrac{d}{dx}\int_a^{x^2}{\sqrt{t}}\ dt = \dfrac{d}{du}(\int_a^{u}{\sqrt{t}})\ dt*\dfrac{du}{dx} = \sqrt{u}*\dfrac{du}{dx}=\sqrt{t^2}*\dfrac{d}{dx}(\sqrt{t})=\sqrt{t^2}*\dfrac{1}{2}{t^{(-1/2)}}=\dfrac{\sqrt{t^2}}{2\sqrt{t}}$

**Fundamental theorem part 2 (The Evaluation Theorem)**
This theorem tells us that the value of a definite integral is equal to the difference of the **antiderivative** of $f$ on $[a,b]$ that is continuous on $[a,b]$: $\int_a^b{f(x)dx}=F(b) - F(a)$. 
Using this theorem to compute integrals is easier than computing a Riemann sum.
The notation for the difference $F(b) - F(a)$ is $F(x)\Bigr]_a^b$.
Example:
$\int_{\pi/6}^{\pi/4}{cos(x)dt} = sin(x)\Bigr]_{\pi/6}^{\pi/4} - sin(a) = sin(\pi/4) - sin(\pi/6) = \dfrac{\sqrt{2} - 1}{2}$
This theorem can also be interpreted as an **integral of rate**, where the integral of the rate of change is equal to $F'(x)$, interpreted as the net change of $F$ as $x$ changes from $a$ to $b$.
For example, the difference between distances $s$ is represented as the integral of velocity $\int_a^b{v(x)dx}$.
*Proof of theorem*: We can rewrite $F(b) - F(a)$ as $\int_a^b{f(x)dx} - \int_a^a{f(x)dx} = \int_a^b{f(t)dx} - 0 = \int_a^b{f(t)dx}$.

**Computation method for total area**: Since area is a positive value, but integration can be negative (when the function is negative) and the sum of positive and negative areas can cancel each other out ($sin(x)$ on $<0, 2\pi>$), we need to use a special method to compute the area.
1. Find the points where the function becomes zero to separate the function into multiple subintervals.
2. Integrate over multiple intervals.
3. Compute the absolute value of each integral.
Example: Compute the total area for $sin(x)$ on $<0,2\pi>$. $sin(x)$ is $0$ at $\pi$ and $2\pi$. 
$|\int_0^\pi sin(x)dx| + |\int_0^\pi sin(x)dx| = \Bigl|-cos(x)\Bigr]_{0}^{\pi}\Bigl|+\Bigl|-cos(x)\Bigr]_{\pi}^{2\pi}\Bigl|$
$= \Bigl|-\Bigl[cos(\pi) - cos(0)\Bigr]\Bigl| + \Bigl|-\Bigl[cos(2\pi) - cos(\pi)\Bigr]\Bigl| = |-(-1-1)| + (|-(1 - (-1))|) =|2| + |-2| = 4$

**An indefinite integral** is a collection of all <u>general solutions</u> for a differential equation or, in other words, is an antiderivative of $y$ with an arbitrary constant $C$. The result of an indefinite integral is an antiderivative $F$ with an added arbitrary constant $C$. The indefinite integral is denoted as $\int{f(x)dx} = F(x) + C$.

**The substitution method for solving integrals of composed functions** runs the chain rule backward; by the power rule, $\dfrac{dy}{dx}(\dfrac{u^{n+1}}{n+1}) =((n+1)\dfrac{u^{n}}{n+1})\dfrac{du}{dx}=u^{n}\dfrac{du}{dx}$, and using an integral, we get back the function $f$: $\int{u^n\dfrac{du}{dx}} = \dfrac{u^{n+1}}{n+1} + C$. We can solve such an integral as a simpler integral of $du$, $\int{u^n\ du} = \dfrac{u^{n+1}}{n+1} + C$, where $du=\dfrac{du}{dx}dx$.
Generalizing this rule: if $g(x)$ is a composed function of $f(x)$ and $u = g(x)$, then $\int{f'(g(x))*g'(x)}\ dx = \int{f(x)du}$.
General computation method:
1. Substitute $u = g(x)$ and $du = \dfrac{du}{dx}dx$. Sometimes we must manipulate the function to get the desired result (using trigonometric identities or some compensation).
2. Integrate with respect to $u$.
3. Replace $u$ with $g(x)$.
*Proof*: $\int{f'(g(x))*g'(x)}\ dx = F(g(x)) = F(u) = \int{f(u)\ du}$, where $du = g'(x) dx$.

Examples:
1. $\int{x^2*2x\ dx}$, where the substitution $u=x^2$ succeeds: $\dfrac{d}{dx}(x^2)dx = 2x\ dx$. $\int{u\ du} = \dfrac{u^2}{2} + C = \dfrac{x^4}{2} + C$
2. $\int{\sqrt{2x + 1}\ dx}$, where the substitution  $u=2x+1$, with $g(x) = 2x+1$ and $g'(x) = 2$, fails because $\dfrac{d}{dx}(2x+1)dx = 2dx$, but the original term is only $dx$, so we have to compensate with $1/2\int{\sqrt{2x + 1}\ 2dx}$ (note that $g'(x)$ is now 2). Now we can solve for $u$:  $\dfrac{1}{2}\int{u^{1/2}\ du} = \dfrac{1}{2}\dfrac{u^{3/2}}{3/2} + C =\dfrac{(2x+1)^{3/2}}{3} + C = \dfrac{2(2x+1)^{3/2}}{6} + C$

Using this substitution method, we can compute definite integrals by:
1. Converting definite integrals to indefinite integrals, then evaluating the expression for $b$ and $a$.
   $\int_a^b{f'(g(x))*g'(x)}\ dx = \int{f(u)}\ du = F(u) + C = F(g(x))\Bigr]_a^b$
   Example: $\int_1^2{x^2*2x\ dx} = \int{u\ du} = \dfrac{u^2}{2} + C = \dfrac{x^4}{2}\Bigr]_1^2=\dfrac{2^4}{2} - \dfrac{1^4}{2} = 7.5$
2. Converting the upper and lower limits to $g(x)$.
   $\int_a^b{f'(g(x))*g'(x)}\ dx = \int_{g(a)}^{g(b)}{f(u)\ du} = F(u)\Bigr]_a^b$
   Example: $\int_1^2{x^2*2x\ dx} = \int_{1^2}^{2^2}{u\ du}=\int_{1}^{4}{u\ du} = \dfrac{u^2}{2}\Bigl]_1^4 = \dfrac{16}{2}-\dfrac{1}{2} = 7.5$
Both methods are valid and can be used interchangeably.

Formulas for computing **integrals of functions over symmetric intervals** $[-a,a]$ for **symmetric functions**:
1. If the function is even, $f(-x)=f(x)$, then $\int_{-a}^{a}f(x)dx=2\int_0^af(x)dx$.
2. If the function is odd, $f(-x)=-f(x)$, then $\int_{-a}^{a}f(x)dx=0$.

**Areas between curves**: If we have functions $f(x)$ and $g(x)$ on the closed interval $<a,b>$ and $f(x)$ is bigger than $g(x)$ on the interval $<a,b>$, then we compute the area between the curves. Using a Riemann sum, such an area is computed by approximation as $A_k = \sum_{k=1}^n={(f(c_k)-g(c_k))\Delta x_k}$, and the real value of the area as $|P| \to 0$ is $lim_{|P| \to 0}\sum_{k=1}^n={(f(c_k)-g(c_k))\Delta x_k}$, forming the definite integral $\int_{a}^{b}[f(x)-g(x)]dx$. To determine the limit $<a,b>$, we can compute $f(x)-g(x)=0$.
![[OpenGL/images/calculus-area-between-curves-vertical-slice.png|345]]
If we want to compute a horizontal area, then we have to integrate in terms of $y$, $\int_{a}^{b}[f(y)-g(y)]dy$, where the function $y = f(x)$ is transformed into the function $x = g(y)$; for example, if $y = x^2$, then $x = \pm \sqrt{y}$.
