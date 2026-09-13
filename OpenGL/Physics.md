## Motion

**Displacement** is a <u>vector</u> of difference of position between origin and final destination, denoted as $s$. Displacement is equal to $\Delta s = s_{final} - s_{origin}$, where $s_{origin}$ is starting position and $s_{final}$ is final position. Distance, denoted as $d$, is a magnitude of vector (scalar).
Example: $s_{origin} = (1,1)$ $s_{final}=(0, 3)$ $\Delta s = (0,3) - (1,1) = (-1, 2)$, $d = \sqrt{(-1)^2 + 2^2} = \sqrt{5}$

**Velocity** is a <u>vector</u> of rate of position $s$ change in respect of time $t$ of position in respect of time, denoted as $v$. <u>Non uniform (average)</u> velocity is equal to $\bar v$ = $\dfrac{\Delta s}{\Delta t}$. <u>Uniform velocity</u> is a constant speed over a distance, which is equal to $v = \dfrac{s}{t}$. Speed, also denoted as $v$, is a absolute value of magnitude of vector(scalar). Multiplying velocity with time, we get displacement. <u>Instantenous velocity</u> is a rate of displacement at particular $t$ computed as $\lim_{\Delta t \to 0} \dfrac{\Delta s}{\Delta t} = \dfrac{ds}{dt}$
Example: Having function $f(x) = x^2$ and assuming units of measure are meters and units of time are seconds, what is instantenous velocity at 4 seconds?
$\dfrac{ds}{dt} = nt^n = 2t^{2-1} = 2t$, $2t = 2*4 = 8m/s$

**Acceleration** is a vector (magnitude can be also computed) of rate of change of velocity in respect of time $t$, denoted as $a$. Acceleration can be positive (forward) or negative (backwards). <u>Non uniform (average)</u> acceleration is equal to $\bar a$ = $\dfrac{\Delta v}{\Delta t}$. <u>Uniform acceleration</u> is constant acceleration for any period of time, for example gravitational acceleration. Units are distance over time squared, since velocity also depends on time, $v = \dfrac{s}{t}$, $a = \dfrac{\dfrac{s}{t}}{t} = \dfrac{s}{t^2} = s/t^2$. Multiplying accelartion by time, we get velocity. Instantenous acceleration is a rate of velocity at particular $t$ computed as $\lim_{\Delta t \to 0} \dfrac{\Delta v}{\Delta t} = \dfrac{dv}{dt}$ or since velocity defined as second derivative of $s$, then $\dfrac{dv}{dt} = \dfrac{d^2s}{dt}$
Several formulas can be derived from average acceleration:
1. $v_{final} = at + v_{original}$ assuming $t_{original}$ is zero or $v_{final} = at$ if initial speed was zero
2. $\bar v = 1/2at$ assuming $v_{original}$ is zero, computed average of two velocities $\dfrac{v_{final} + v_{original}}{2}$
3. $s = \bar vt = 1/2(v_{original} + v_{final})t$ and if $v_{original}$ is zero $s= 1/2at^2$ assuming $a$ is constant acceleration

**Jerk** is a vector (magnitude can be also computed) of rate of change of acceleration over time, defined as third derivative of $s$, $\dfrac{d^3s}{dt}$

**Snap**, **crackle** and **pop**, which are also vectors, are defined as fourth, fifth and sixth derivative of $s$, $\dfrac{d^4s}{dt}$, $\dfrac{d^5s}{dt}$, $\dfrac{d^6s}{dt}$

**Free fall** is a motion, where body is affected only by gravity force. Travel is calculated via $s = 1/2gt^2$ derived from acceleration formula, where $a$ is gravity acceleration $g$, which is equal to $9.8m/sec^2$

**Simple harmonic motion** is motion with no force of object that is bobbing up and down, defined by trigonometric function from position in unrest state.