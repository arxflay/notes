Right angled definition:
sine = ratio between opposite side and hypotenuse
cos = ratio between adjacent side and hypotenuse
tan = ratio between opposite and adjacent side or ratio between sine and cos
cotg = ratio between adjacent side and oposite (inverse of tan)

figure is not a triangle if one of the three sides is bigger than sum of two other sides

sum of angle of triangles must be always 180

unit circle - circle with length 1

![[Pasted image 20260610210400.png|477]]

![[Pasted image 20260610214910.png]]

similar triangles: triangles are similar when they have same side ratio and same angles but different size


law of sine
$a/sin(A) = b/sin(B) = c/sin(C)$

![[Pasted image 20260614210709.png|370]]

law of cosine
$c^2 = a^2 + b^2 - 2a * cos(\theta)$

proof:
construct triangle (colored in blue), from this triangle construct circle of radius a. Extended length by a. Extended side c to top and bottom. Extended side on top is equal to $(a - c)$ because $a$ is length from center and $c$ is length of triangle. Extended side b. Connect new formed point to two points (points form chord of length of diameter). Newly connected points form right angled triangle by [[Angles#^33e87c |Thales theorem]]. Using trigonometry, we can use formula to determine  
$cos(\theta)  = adjacent\_side/hypotenuse$ 
rearranged
$cos(\theta) * hypotenuse = adjacent\_side$
hypotenuse is 2a, so $adjacent\_side = 2a * cos(\theta)$
but we need only size on opposite of chord, which is $2a - cos(\theta) - b$
now we can use [[Math#^00d4f6|chord intersection theorem]] $ab = cd$

$(2a * cos(\theta) - b) * b = (a-c) * (c + a)$
$2ab*cos(\theta) - b^2 = a^2 - c^2$
$c^2 = a^2 + b^2 - 2ab *cos(\theta)$

![[Pasted image 20260615202502.png|499]]