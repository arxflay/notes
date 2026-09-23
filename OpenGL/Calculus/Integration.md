Using subintervals, we can approximate the area under a function by computing squares of height $y$ and the width of the subinterval $\Delta x$, expressed as $f(k_0)\Delta x + f(k_1)\Delta x... f(k_n)\Delta x$ . This area can be interpreted as the average value $f$ of a nonnegative function or the sum of the positive change in $y$ (for example, the sum of the absolute values of $s$). The length of the subinterval $\Delta x$ is computed as $(b-a)/n$, where $n$ is the number of intervals and $a$ and $b$ are the values of the closed interval $[a,b]$. 

There are 3 ways in which we can divide subintervals:
1. **Upper sum**: the $y$ value is picked at the beginning of a subinterval of length $\Delta x$, e.g., $f(x_n)$.  The upper sum is usually bigger than the area under $f$. 
   The upper sum can be expressed as $\sum_{k=1}^{n}f(a+\Delta x(k-1))\Delta x$, where $k$ is the index of the first element, $n$ is the number of intervals, $a$ is the beginning of the interval, and $(k-1)$ is the beginning of the subinterval. 
   Example: having the interval $[0,1]$ and $n=2$, we have $\Delta x= (1-0) / 2 = 1/2$  and $\sum_{k=1}^{2}f(0+\Delta x(k-1))\Delta x =  f(0 + \Delta{x}(1-1))\Delta x + f(0 + \Delta{x}(2-1))\Delta x = f(0)\Delta x + f(1/2)\Delta x$
2. **Lower sum**: the $y$ value is picked at the end of a subinterval of length $\Delta x$, e.g., $f(x_n+\Delta x)$. The lower sum is usually smaller than the area under $f$. 
   The lower sum can be expressed as $\sum_{k=1}^{n}f(a+k\Delta x)\Delta x$, where $k$ is the index of the first element, $n$ is the number of intervals, $a$ is the beginning of the interval, and $k$ is the end of the subinterval. 
   Example: having the interval $[0,1]$ and $n=2$, we have $\Delta x= (1-0) / 2 = 1/2$  and $\sum_{k=1}^{2}f(0+k\Delta x)\Delta x =  f(0 + \Delta{x})\Delta x + f(0 + 2\Delta{x})\Delta x = f(1/2) \Delta{x} + f(1)\Delta{x}$
3. **Midpoint sum**: the $y$ value is picked at the middle of a subinterval of length $\Delta x$. The midpoint sum could be bigger or smaller than the area under $f$. 
   The midpoint sum can be expressed as $\sum_{k=1}^{n}f(a + (k-1)\Delta x + \Delta x/2)\Delta x$, where $k$ is the index of the first element, $n$ is the number of intervals, $a$ is the beginning of the interval, and $(k-1)\Delta x + \Delta x/2$ is the midpoint of the subinterval. 
   Example: having the interval $[0,1]$ and $n=2$, we have $\Delta x=1/2$  and $\sum_{k=1}^{2}f(0 + (k-1)\Delta x + \Delta x/2)\Delta x$
   $= f(0 + (1-1) + 1/2\Delta{x})\Delta x + f(0 + (2-1) + 1/2\Delta{x})\Delta x = f(1/4) + f(3/4)$

The real value lies between the upper sum and the lower sum; the error cannot be greater than $\Delta sum = sum_{upper} - sum_{lower}$
