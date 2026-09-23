## Motion

**Displacement** is a <u>vector</u> of the difference in position between the origin and final destination, denoted as $s$. Displacement is equal to $\Delta s = s_{final} - s_{origin}$, where $s_{origin}$ is the starting position and $s_{final}$ is the final position. Distance, denoted as $d$, is the magnitude of a vector (scalar).
Example: $s_{origin} = (1,1)$ $s_{final}=(0, 3)$ $\Delta s = (0,3) - (1,1) = (-1, 2)$, $d = \sqrt{(-1)^2 + 2^2} = \sqrt{5}$

**Velocity** is a <u>vector</u> of the rate of position $s$ change with respect to time $t$ of the position with respect to time, denoted as $v$. <u>Nonuniform (average)</u> velocity is equal to $\bar v$ = $\dfrac{\Delta s}{\Delta t}$. <u>Uniform velocity</u> is a constant speed over a distance, which is equal to $v = \dfrac{s}{t}$. Speed, also denoted as $v$, is the absolute value of the magnitude of a vector (scalar). Multiplying velocity by time, we get displacement. <u>Instantaneous velocity</u> is the rate of displacement at a particular $t$, computed as $\lim_{\Delta t \to 0} \dfrac{\Delta s}{\Delta t} = \dfrac{ds}{dt}$
Example: Having the function $f(x) = x^2$ and assuming the units of measure are meters and the units of time are seconds, what is the instantaneous velocity at 4 seconds?
$\dfrac{ds}{dt} = nt^n = 2t^{2-1} = 2t$, $2t = 2*4 = 8m/s$

**Acceleration** is a vector (the magnitude can also be computed) of the rate of change of velocity with respect to time $t$, denoted as $a$. Acceleration can be positive (forward) or negative (backward). <u>Nonuniform (average)</u> acceleration is equal to $\bar a$ = $\dfrac{\Delta v}{\Delta t}$. <u>Uniform acceleration</u> is constant acceleration for any period of time, for example, gravitational acceleration. The units are distance over time squared, since velocity also depends on time, $v = \dfrac{s}{t}$, $a = \dfrac{\dfrac{s}{t}}{t} = \dfrac{s}{t^2} = s/t^2$. Multiplying acceleration by time, we get velocity. Instantaneous acceleration is the rate of velocity at a particular $t$, computed as $\lim_{\Delta t \to 0} \dfrac{\Delta v}{\Delta t} = \dfrac{dv}{dt}$, or since velocity is defined as the second derivative of $s$, then $\dfrac{dv}{dt} = \dfrac{d^2s}{dt}$
Several formulas can be derived from average acceleration:
1. $v_{final} = at + v_{original}$ assuming $t_{original}$ is zero or $v_{final} = at$ if initial speed was zero
2. $\bar v = 1/2at$ assuming $v_{original}$ is zero, the computed average of two velocities $\dfrac{v_{final} + v_{original}}{2}$
3. $s = \bar vt = 1/2(v_{original} + v_{final})t$ and if $v_{original}$ is zero $s= 1/2at^2$ assuming $a$ is constant acceleration

**Jerk** is a vector (the magnitude can also be computed) of the rate of change of acceleration over time, defined as the third derivative of $s$, $\dfrac{d^3s}{dt}$

**Snap**, **crackle**, and **pop**, which are also vectors, are defined as the fourth, fifth, and sixth derivatives of $s$, $\dfrac{d^4s}{dt}$, $\dfrac{d^5s}{dt}$, $\dfrac{d^6s}{dt}$

**Free fall** is a motion where a body is affected only by the force of gravity. Travel is calculated via $s = 1/2gt^2$, derived from the acceleration formula, where $a$ is gravitational acceleration $g$, which is equal to $9.8m/sec^2$

**Simple harmonic motion** is the motion with no force of an object that is bobbing up and down, defined by a trigonometric function from its position in an unrest state.
