
similar triangles - triangles are similar when they have same side ratio and same angles but different size

## Trigonometry

Pythagoras theorem - sum of squares of sides in right side triangle is equal to hypotenuse. $c^2 = a^2 + b^2$
### Basics
hypotenuse - longest side in right angled triangle formed by two complementary angles

Formulas:
1. $sin(\theta) = \dfrac{o}{h}$ 
   ratio between opposite side and hypotenuse
2. $cos(\theta) = \dfrac{a}{h}$ 
   ratio between adjacent side and hypotenuse
3. $tan(\theta) = \dfrac{o}{a}$ 
   ratio between opposite and adjacent side
4. $cot(\theta) = \dfrac{a}{o}$ 
   ratio between adjacent and opposite side (inverse of tan)
5. $csc(\theta) = \dfrac{h}{o}$ 
   ratio between hypotenuse and opposite side (inverse of sin)
6. $sec(\theta) = \dfrac{h}{a}$ 
   ratio between hypotenuse and adjacent side (inverse of tan)

reverse formulas:
1. $\arcsin(o/h) = \theta$
2. $\arccos(a/h) = \theta$
3. $\arctan(o/a) = \theta$
4. $arccot(a/o) = \theta$

example task:
![[Pasted image 20260610210400.png|417]]

table of known trigonometric values

|    **fn**    | **$\pi/6 = 30\textdegree$** | **$\pi/4 = 45\textdegree$** | **$\pi/3 = 60\textdegree$** | **$\pi/2 = 90\textdegree$** |
| :----------: | :-------------------------: | :-------------------------: | :-------------------------: | :-------------------------: |
| ***$\sin$*** |             1/2             |        $\sqrt{2}/2$         |        $\sqrt{3}/2$         |              1              |
| ***$\cos$*** |        $\sqrt{3}/2$         |        $\sqrt{2}/2$         |             1/2             |              0              |
| ***$\tan$*** |        $\sqrt{3}/3$         |              1              |         $\sqrt{3}$          |            undef            |
| ***$\cot$*** |         $\sqrt{3}$          |              1              |        $\sqrt{3}/3$         |              0              |


$x\ trignometric\_fn^p(z * \theta)$
* increasing/decreasing $x$ will increase/decrease max/min value
* increasing/decreasing $z$ will shorten/extend trigonometric function
* positive power $p$ is applied to final result and determines how fast function will go up/down without shortening/extending function. Also if $p$ is divisible by 2, then result is positive
* if p is equal to -1, then result is inverse function.
* if p is negative and not equal -1, then parabola is formed

### Unit circle
Unit circle - circle with radius 1, which is used to describe trigonometric functions past $90$ degrees (because length of hypotenuse is always 1). This works with smaller or bigger triangles (which have hypotenuse bigger than 1) because this triangles are similar. 

basic trigonometric functions graphs (y is $\cos$ and x is $\sin$): 
![[Pasted image 20260620123440.png|520]]
Angles for each quadrant (can be proved by angle of intersecting lines):
1. $\theta$
2. $\pi - \theta$
3. $\theta - \pi$
4. $2\pi - \theta$
![[Pasted image 20260627132320.png|324]]

reverse functions graphs:
![[Pasted image 20260620154550.png|504]]
### Trigonometric identities (right triangle axioms)
#### Uncategorized identities
1. $tan(\theta) = \dfrac{sin(\theta)}{cos(\theta)}$
   this works, because $tan(\theta) = opposite/adjacent$ and if we divide both terms by hypotenuse $tan(\theta) = \dfrac{opposite / hypotenuse}{adjacent / hypotenuse}$, ratio will be the same, but from trigonometry we know, that $sin(\theta) = \dfrac{opposite}{hypotenuse}$ $cos(\theta) = \dfrac{adjacent}{hypotenuse}$, so we can substitute ratio with $tan(\theta) = \dfrac{sin(\theta)}{cos(\theta)}$
2. $cot(\theta) = \dfrac{cos(\theta)}{sin(\theta)}$ 
   same as for tan, but reversed
3. $csc(\theta) = \dfrac{1}{sin(\theta)}$
   derived from basic formula by division of dividend and divisor by hypotenuse, $csc(\theta) = \dfrac{h / h}{o / h}= \dfrac{1}{o / h} = \dfrac{1}{sin(\theta)}$

#### Identities derived from Pythagoras theorem
1. $sin^2(\theta) + cos^2(\theta) = 1$ 
   derived from Pythagoras theorem. $a^2 + b^2 = c^2$ divide both sides by $c^2$ $\dfrac{a^2}{c^2} \dfrac{b^2}{c^2} = \dfrac{c^2}{c^2}$ simplify $(\dfrac{a}{c})^2 + (\dfrac{b}{c})^2 = 1$ replace ratios with trigonometric functions $sin^2(\theta) + cos^2(\theta) = 1$
2. $tan^2(\theta) = sec^2(\theta) - 1$
   This formula is derived from previous formula by division by $cos^2(\theta)$ $\dfrac{sin^2(\theta)}{cos^2(\theta)} + 1 = \dfrac{1}{cos^2(\theta)}$ simplify $tan^2(\theta) + 1 = sec^2(\theta)$
3. $cot^2(\theta) = csc^2(\theta) - 1$ 
   similar to previous formula, but derived by division by $sin^2(\theta)$

#### Angle manipulations
1. $cos(-\theta) = cos(\theta)$ 
   because cosine function is same if angle is negative
   proved by reflection (adjacent is always -3)
   ![[Pasted image 20260627122621.png|209]]
2. $sin(-\theta) = -sin(\theta)$
   sine function is reversed.
   proved by reflection ($opposite$ points to positive y but $opposite_{reflected}$ points to negative y)
   ![[Pasted image 20260627123107.png|244]]
   
3. $tan(-\theta) = -tan(\theta)$ and $cot(-\theta) = -cot(\theta)$
   similar to sine
4. $sin(\dfrac{\pi}{2} + \theta) = cos(\theta)$
   proof (y = 3 on right, x = 3 on left), when extending angle by $90\textdegree$, y will be -3 on bottom triangle and x = -3 on top
   ![[Pasted image 20260627132753.png|266]]
5. $cos(\dfrac{\pi}{2} + \theta) = -sin(\theta)$
   same proof as in previous image
There other derivatives but they are can be simply derived from function graph or by reflection

#### Angle difference identities
1. $sin(A \pm B) = sin(A) * cos(B) \pm cos(A) * sin(B)$
2. $cos(A \pm B) = cos(A) * cos(B) \mp sin(A) * sin(B)$
visual proofs for sine and cosine ([using wikipedia article](https://en.wikipedia.org/wiki/Proofs_of_trigonometric_identities#Angle_sum_identities)) 
   ![[Pasted image 20260703171224.png]]
3. $tan(A \pm B) = \dfrac{tan(A) \pm tan(B)}{1 \mp tan(A)*tan(B)}$
4. $cot(A \pm B) = \dfrac{cot(A)*cot(B) \mp 1 }{cot(B) \pm cot(A)}$

#### Multiple of angle identities
1. $sin(z*\theta) = 2sin(\dfrac{z}{2}\theta)* cos(\dfrac{z}{2}\theta)$
    can be derived from $sin(A + B)$ $sin(z*\theta) = sin(\dfrac{z}{2}\theta + \dfrac{z}{2}\theta) = sin(\dfrac{z}{2}\theta) * cos(\dfrac{z}{2}\theta) + sin(\dfrac{z}{2}\theta) * cos(\dfrac{z}{2}\theta) = 2sin(\dfrac{z}{2}\theta) * cos(\dfrac{z}{2}\theta)$
    visual proof with same isosceles triangles with two different orientations
    ![[Pasted image 20260703153827.png|314]]
2. $cos(z*\theta) = cos^2(\dfrac{z}{2}\theta) - sin^2(\dfrac{z}{2}\theta)$
    can be derived from $cos(A + B)$
    $cos(z*\theta) = cos(\dfrac{z}{2}\theta + \dfrac{z}{2}\theta) = cos(\dfrac{z}{2}\theta) * cos(\dfrac{z}{2}\theta) - sin(\dfrac{z}{2}\theta) * sin(\dfrac{z}{2}\theta) = cos^2(\dfrac{z}{2}\theta) - sin^2(\dfrac{z}{2}\theta)$
    alternatives forms are:
    * $2cos^2(\dfrac{z}{2}\theta) - 1$ derived using substitution $sin^2(\theta)$ = 1 - $cos^2(\theta)$,  
    * $1 - 2sin^2(\dfrac{z}{2}\theta)$ derived using substitution $cos^2(\theta)$ = 1 - $sin^2(\theta)$, 
3. $tan(z * \theta) = \dfrac{2tan(\dfrac{z}{2}\theta)}{1 - tan^2(\dfrac{z}{2}\theta)}$
    can be derived from $tan(A + B)$
    $tan(z*\theta) = tan(\dfrac{z}{2}\theta + \dfrac{z}{2}\theta) = \dfrac{tan(\dfrac{z}{2}\theta) + tan(\dfrac{z}{2}\theta)}{1-tan(\dfrac{z}{2}\theta) * tan(\dfrac{z}{2}\theta)} =\dfrac{2tan(\dfrac{z}{2}\theta)}{1 - tan^2(\dfrac{z}{2}\theta)}$

#### Half angle identities
1. $sin(\dfrac{a}{2}) = \pm \sqrt{\dfrac{1 - cos(\alpha)}{2}}$
   derived from multiple angle identity for cosine
	$cos(2\theta) = 1 - 2sin^2(\theta)$ substitute $\theta = \dfrac{\alpha}{2}$ then $cos(\alpha) = 1 - 2sin^2(\dfrac{\alpha}{2})$ solve for $sin(\dfrac{\alpha}{2})$, $2sin^2(\dfrac{a}{2}) = 1 - cos(\alpha)$ divide by 2 $sin^2(\dfrac{a}{2}) = \dfrac{1 - cos(\alpha)}{2}$ and then sqrt both sides $sin(\dfrac{a}{2}) = \pm \sqrt{\dfrac{1 - cos(\alpha)}{2}}$
2. $cos(\dfrac{\alpha}{2}) = \pm \sqrt{\dfrac{1 + cos(\alpha)}{2}}$
   derived from multiple angle identity for cosine
   $cos(2\theta) = 2cos^2(\theta) - 1$ substitute $\theta = \dfrac{\alpha}{2}$ then $cos(\alpha) = 2cos^2(\dfrac{\alpha}{2}) - 1$ solve for $cos(\dfrac{\alpha}{2})$, $2cos^2(\dfrac{a}{2}) = 1 + cos(\alpha)$ divide by 2 $cos^2(\dfrac{a}{2}) = \dfrac{1 + cos(\alpha)}{2}$ and then sqrt both sides $cos(\dfrac{a}{2}) = \pm \sqrt{\dfrac{1 + cos(\alpha)}{2}}$
3. $\tan(\dfrac{a}{2}) = \pm \sqrt{\dfrac{1 - cos(\alpha)}{1 + cos(\alpha)}}$
   is derived from two previous formulas and relation $tan(\theta) = \dfrac{sin(\theta)}{\cos(\theta)}$. Solve for $\tan(\dfrac{a}{2})$, $\tan(\dfrac{a}{2}) = \pm \dfrac{sin(\dfrac{\theta}{2})}{\cos(\dfrac{\theta}{2})}$ substitute with two previous formulas
   $\tan(\dfrac{a}{2}) = \pm \sqrt{\dfrac{\dfrac{1 - cos(\alpha)}{2}}{\dfrac{1 + cos(\alpha)}{2}}}$ simplify $\tan(\dfrac{a}{2}) = \pm \sqrt{{\dfrac{1 - cos(\alpha)}{\cancel{2}}} * \dfrac{\cancel{2}}{1 + cos(\alpha)}}$ result $\tan(\dfrac{a}{2}) = \pm \sqrt{\dfrac{1 - cos(\alpha)}{1 + cos(\alpha)}}$





### Triangle identities
1. figure is not a triangle if one of the three sides is bigger than sum of two other sides
2. sum of angle of triangles must be always 180
3. Law of sine
   $\dfrac{a}{sin(A)} = \dfrac{b}{sin(B)} = \dfrac{c}{sin(C)}$
   proved by division of triangle 
   ![[Pasted image 20260614210709.png|332]]
   To apply law of sine we must know at least 2 sides and angle between one this sides or two angles and one side that is clos
4. Law of cosine
   $c^2 = a^2 + b^2 - 2ab * cos(C)$
   $a^2 = b^2 + c^2 - 2bc * cos(A)$
   $b^2 = a^2 + c^2 - 2ac * cos(B)$
   How to prove: construct triangle (colored in blue), from this triangle construct circle of radius a. Extended length by a. Extended side c to top and bottom. Extended side on top is equal to $(a - c)$ because $a$ is length from center and $c$ is length of triangle. Extended side b. Connect new formed point to two points (points form chord of length of diameter). Newly connected points form right angled triangle by [[Angles#^33e87c |Thales theorem]]. Using trigonometry, we can use formula to determine  
   $cos(\theta)  = adjacent\_side/hypotenuse$ 
   rearranged
   $cos(\theta) * hypotenuse = adjacent\_side$
   hypotenuse is 2a, so $adjacent\_side = 2a * cos(\theta)$
   but we need only size on opposite of chord, which is $2a - cos(\theta) - b$
   now we can use [[Math#^00d4f6|chord intersection theorem]] $ab = cd$
	$(2a * cos(\theta) - b) * b = (a-c) * (c + a)$
	$2ab*cos(\theta) - b^2 = a^2 - c^2$
	$c^2 = a^2 + b^2 - 2ab *cos(\theta)$
	![[Pasted image 20260615202502.png|437]]
