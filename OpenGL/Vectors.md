A vector is an array of values that can be represented in a column or row.
unit vector - a vector with length 1.
vector normalization - dividing a vector by its length to get a unit vector. The direction will not change.
vector magnitude - vector length 
vector direction - the way a vector points
scalar - explicitly mentioned ordinary value (not a vector)
A vector is not bound to an absolute position; instead, it represents a relative direction

Vector vs magnitude example:
* Velocity is the change in the x and y directions by a unit of measurement per unit of time, for example, $\begin{bmatrix} 10 & 5 \end{bmatrix}$ km per hour. Velocity is a vector
* Speed is the total speed; speed is a magnitude (and scalar or a point). For example, $\sqrt{10^2 + 5^2} = 5\sqrt{5}$ km/h

Zero vector - a vector which has all elements equal to zero. Its magnitude is 0. This vector is the additive identity

Difference of vectors - can be imagined as a vector coming from the end of another vector. For example, having vectors $a$ and $b$, then $a$ - $b$ is a vector coming from $b$ to $a$
![[Pasted image 20260615222419.png|208]]
vector distance is useful for determining the vector between two points or the distance between points. 
The formula for the distance between two points is derived from the magnitude formula and can have an unlimited number of components. It doesn't matter from which vector we calculate the difference
$||\vec{b} - \vec{a}|| = \sqrt{\sum^n_{i=0}{(b_i - a_i)}^2}$
example for $\vec{a} = (2, 3)\ \vec{b} = (6,2)$:
$\sqrt{(6 - 2)^2 + (2 - 3)^2} = \sqrt{4^2 + 1^2} = \sqrt{16 + 1} = \sqrt{17}$  

A vector from points is computed by the difference between the points (again, a vector from $a$ to $b$ must be computed as the difference between $b$ and $a$)
$a = (5, 10)$
$b=(10,15)$
$(10 - 5, 15 - 10) = (5, 5)$

radius vector: a positional vector

## Dot product
Dot product (vector multiplication) has two related definitions. 
1. The coordinate definition defines vector multiplication as the sum of the multiplication of vector components (imagine it as matrix multiplication where the result is a 1x1 matrix).
   $a*b = \sum_i a_i*b_i$ (vector components are not limited to 2). Coordinate definition is basically matrix multiplication 
	$\begin{bmatrix} a_1 & a_2 \end{bmatrix} * \begin{bmatrix} b_1 \\ b_2 \end{bmatrix} = [a_1 * b_1 + a_2 * b_2]$. Geometrically, this definition is defined as the projection of vector $\vec{a}$ into another vector $\vec{b}$ by extending $\vec{a}$ by the scalar result of vector multiplication. The result is a signed length that is scaled by the length of $\vec{a}$. Graphically, it's vector $\vec{a}$ extended by the scalar result of vector multiplication.  The further from the vector direction, the lower the value of the vector is
	* the dot product is zero when a vector is perpendicular - angle $90\textdegree$
	* the dot product is negative when a vector points in the opposite direction - angle $(90\textdegree, 270\textdegree)$
	* the dot product is positive when a vector points in the same direction - angle $(-90\textdegree, 90\textdegree)$
	![[Pasted image 20260719152621.png|413]]
	The dot product can be scaled by length $k$ of vector $a$ and the length of vector $b$. $(ka) * b = k(a*b) = a * (kb)$. Dividing the dot product by the lengths will result in a value between (-1, 1)
	![[Pasted image 20260719214328.png|405]]
	using this definition of the dot product (which measures only parallel displacement), it's also possible to compute the perpendicular vector and its distance
	$b = b_{parallel} + b_{perpendicular}$
	$b_{parallel} = \dfrac{(a * b)}{||a||}a$ (projected vector)
	$b_{perpendicular} = b_{parallel} - b$
	![[Pasted image 20260719180019.png|366]]
	the dot product of a vector itself is the length squared $a*a = |a|^2$, e.g., the projected vector is multiplied by its length
	![[Pasted image 20260719220018.png|379]]
	the dot product is defined even in 3D
	![[Pasted image 20260721164231.png|337]]
2. The trigonometrical definition is based on the previous definition. If we take both unit vectors and create a projection, via trigonometry we can compute the angle between them $cos(\phi) = a/h$, and since $h$ is 1 and $a$ is $\hat a * \hat b$, then $cos(\phi) = \hat a * \hat b$ (projection).
	    ![[Pasted image 20260720205545.png|162]] 
   This formula can be applied to nonunit vectors using the property of scaling by dividing the dot product by the lengths of vectors $||a||$ and $||b||$, thus retrieving the dot product as if both vectors were unit vectors. The angle between vectors is equal to the dot product divided by their length $a*b = ||a|| * ||b|| * cos(\phi)$. If one or both vectors are zero, then the resulting angle will be the same as if both vectors were perpendicular
   
   This definition also works in 3D, and the computation is the same, but the angle will be relative to 3 axes. For example, having vector $a$ (2, 3, 4) and vector $b$ (-2, -3, -4), the angle between them will be $180\textdegree$ (scaling doesn't affect the result). 

   
   This definition can also be derived from the law of cosines
	![[Pasted image 20260615225209.png]]
	[source](https://www.youtube.com/watch?v=afHTz7jrmGo)

dot product properties:
1. commutative 
2. distributive
3. dot product is $\le |a| * |b|$


### Direction cosines 
Direction cosines can be applied only in 3D and are derived from the dot product. They are used to determine how closely a vector points to an axis using a unit vector with 1 component as a base in the degree range $<0, 180>$, where $0\textdegree$ is a vector parallel to the axis having all components equal to $0$, $90\textdegree$ is a vector with the axis component equal to $0$, and $180\textdegree$. The angle can't be less than $90\textdegree$ if the vector points in the opposite direction relative to the axis and can't be less than $0\textdegree$ if it points in the positive direction. Moving unrelated components further in any direction will decrease the angle relative to the axis. 
* $cos (\alpha) = \dfrac{a * i}{||a||}$ ; $i = (1, 0, 0)$ angle relative to x axis 
* $cos (\beta) = \dfrac{a * j}{||a||}$ ; $j = (0, 1, 0)$ angle relative to y axis 
* $cos (\gamma) = \dfrac{a * k}{||a||}$ ; $k = (0, 0, 1)$ angle relative to z axis
 
example: vec(-1, 1, 1) and the angle relative to the x axis
 ![[Pasted image 20260721201524.png|318]]
direction cosines can be used to compute the dot product between two vectors
$cos(\alpha) * cos(\alpha') + cos(\beta) * cos(\beta') + cos(\gamma) * cos(\gamma')$ (it's actually the dot product formula from another perspective; it's like normalizing all components and then computing the dot product) $\dfrac{a_{x}}{||a||} * \dfrac{b_{x}}{||b||} + \dfrac{a_{y}}{||a||} * \dfrac{b_{y}}{||b||} + \dfrac{a_{z}}{||a||} * \dfrac{b_{z}}{||b||} = cos\theta$

Direction cosines identities:
1. $cos^2(\alpha) + cos^2(\beta) + cos^2(\gamma) = 1$ 
   derived from the magnitude formula, $|a|^2 = a_0^2 + a_1^2 + a_2^2$ divide by the length $\dfrac{a^2_0}{|a|^2} + \dfrac{a^2_1}{|a|^2} + \dfrac{a^2_2}{|a|^2} = 1$, simplify $(\dfrac{a_0}{|a|})^2 + (\dfrac{a_1}{|a|})^2 + (\dfrac{a_2}{|a|})^2 = 1$ replace with direction cosines $cos^2(\alpha) + cos^2(\beta) + cos^2(\gamma) = 1$. Using this identity, we can prove if we can form a vector with such angles in 3D; for example, having all angles $60\textdegree$, $cos^2(60\textdegree) + cos^2(60\textdegree) + cos^2(60\textdegree) = 1$, $1/4 + 1/4 + 1/4 \ne 1$. Only if $cos(\theta)$ is equal to $1/\sqrt{3}$ is it possible to form a vector with equal angles
	![[Pasted image 20260723105833.png|281]]

## Cross product
The cross product is a vector that is perpendicular to both vectors. It can be applied only in 3D. It is extensively used to determine a normal vector, the sign of the angle between two vectors, or the direction of rotation.

Cross product properties:
1. anticommutative 
2. distributive

the formula, which is derived using the determinant
$\begin{bmatrix} y_1*z_2 - z_1 * y_2 \\ z_1*x_2 - x_1*z_2 \\ x_1*y_2 - y_1*x_2  \end{bmatrix}$

The length of the perpendicular vector is equal to $||a \times b|| = ||a||\ ||b||sin(\theta)$, which is also equal to the area of the parallelogram $(b * h)$
so we can modify the formula $b = ||a||$, $h = ||b||  sin(\theta)$ and get $||a||\ ||b||sin(\theta)$
![[Pasted image 20260723191058.png|325]]
It can also be computed via the absolute value of the determinant of a matrix, since vectors $a$ and $b$ can be interpreted as a basis 

There are two directions in which $a \times b$ can be perpendicular. Whether we make a clockwise or counterclockwise turn can be determined by placing vector $b$ at the end. The axis from which we are looking matters (which axis looks backward) because it defines which way is clockwise and counterclockwise. The sign of the cross product can determine if the rotation is clockwise or counterclockwise

Looking from positive axis in **right handed** coordinate system:
* counter clockwise rotation (CCW): ($> 0$) vector points toward you
  ![[Pasted image 20260723120146.png|257]] 
* clockwise rotation (CW): $(< 0)$ vector points away from you
  ![[Pasted image 20260723120240.png|360]]
  ![[Pasted image 20260726171050.png|396]]
Looking from positive axis in **left handed** system:
* counterclockwise rotation (CCW): $(<0)$ vector points away from you
  ![[Pasted image 20260726164452.png|355]]
* clockwise rotation (CW): (> 0) vector points towards you
  ![[Pasted image 20260726164056.png|404]]
the rules become inverted if we look from the negative side; for example, if we are looking from negative -y, then clockwise becomes counterclockwise
![[Pasted image 20260726171318.png|377]]
the cross product of a parallel vector is equal to 0

cross products of each axis:
$x = (1, 0, 0), y = (0, 1, 0), z = (0, 0, 1)$
$x \times y = z+$ (0, 0, $x_1*y_2 - y_1*x_2$) = (0, 0, $1*1 - 0*0$) = (0, 0, 1)
$z \times x = y+$ ($z_1*x_2 - x_1*z_2, 0, 0$) = (0, $1*1 - 0*0$, 0) = (0, 1, 0)
$y \times z = x+$ ($y_1*z_2 - z_1*y_2, 0, 0$) = ($1*1 - 0*0$, 0, 0) = (1, 0, 0)
$y \times x = z-$ (0, 0, $x_1*y_2 - y_1*x_2$) = (0, 0, $0*0 - 1*1$) = (0, 0, -1)
$x \times z = y-$ ($z_1*x_2 - x_1*z_2, 0, 0$) = (0, $0*0 - 1*1$, 0) = (0, -1, 0)
$z \times y = x-$ ($y_1*z_2 - z_1*y_2, 0, 0$) = ($0*0 - 1*1$, 0, 0) = (-1, 0, 0)
the direction can also be determined by hand, placing the thumb in the direction of $a$ and the index finger in the direction of $b$, so the direction perpendicular to both axes will be where the cross product points
