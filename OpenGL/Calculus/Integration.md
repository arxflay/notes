Using subintervals, we can approximate area under function by computing squares of height $y$ and width of subinterval $\Delta x$, expressed as $f(k_0)\Delta x + f(k_1)\Delta x... f(k_n)\Delta x$ . This area can be interpreted as average value $f$ of non negative function or sum of change positive $y$ (for example sum of absolute values of $s$). Length of subinterval $\Delta x$ is computed as $(b-a)/n$, where $n$ is amount of intervals and $a$ and $b$ are values of closed interval $[a,b]$. 

There are 3 types how we can divide subintervals:
1. **Upper sum**: as $y$ value is picked beginning of subinterval of length $\Delta x$, e.g $f(x_n)$.  Upper sum is usually bigger than area under $f$. 
   Upper sum can be expressed as $\sum_{k=1}^{n}f(a+\Delta x(k-1))\Delta x$, where $k$ is index of first element, $n$ is amount of intervals, $a$ is beginning of interval, $(k-1)$ is beginning of subinterval. 
   Example: having interval $[0,1]$ and and $n=2$ we have $\Delta x= (1-0) / 2 = 1/2$  and $\sum_{k=1}^{2}f(0+\Delta x(k-1))\Delta x =  f(0 + \Delta{x}(1-1))\Delta x + f(0 + \Delta{x}(2-1))\Delta x = f(0)\Delta x + f(1/2)\Delta x$
2. **Lower sum**: as $y$ value is picked end of subinterval of length $\Delta x$, e.g $f(x_n+\Delta x)$. Lower sum is usually smaller than area under $f$. 
   Lower sum can be expressed as $\sum_{k=1}^{n}f(a+k\Delta x)\Delta x$, where $k$ is index of first element, $n$ is amount of intervals, $a$ is beginning of interval, $k$ is end of subinterval. 
   Example: having interval $[0,1]$ and $n=2$ we have $\Delta x= (1-0) / 2 = 1/2$  and $\sum_{k=1}^{2}f(0+k\Delta x)\Delta x =  f(0 + \Delta{x})\Delta x + f(0 + 2\Delta{x})\Delta x = f(1/2) \Delta{x} + f(1)\Delta{x}$
3. **Midpoint sum**: as $y$ value is picked middle of subinterval of length $\Delta x$. Midpoint sum could be bigger or smaller than are under $f$. 
   Midpoint sum can be expressed as $\sum_{k=1}^{n}f(a + (k-1)\Delta x + \Delta x/2)\Delta x$, where $k$ is index of first element, $n$ is amount of intervals, $a$ is beginning of interval, $(k-1)\Delta x + \Delta x/2$ is middle point of subinterval. 
   Example: having interval $[0,1]$ and $n=2$  we have $\Delta x=1/2$  and $\sum_{k=1}^{2}f(0 + (k-1)\Delta x + \Delta x/2)\Delta x$
   $= f(0 + (1-1) + 1/2\Delta{x})\Delta x + f(0 + (2-1) + 1/2\Delta{x})\Delta x = f(1/4) + f(3/4)$

Real value lies within upper sum and lower sum, error cannot be greater than $\Delta sum = sum_{upper} - sum_{lower}$

