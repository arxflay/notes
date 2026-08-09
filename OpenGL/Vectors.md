Vector is array of values that can be represented in column or row.
unit vector - vector with length 1.
vector normalization - dividing vector by it's length to get unit vector. Direction will not change.
vector magnitude - vector length 
vector direction - which way is vector points
scalar - explicitly mentioned ordinary value (not a vector)
Vector is not bound to absolute position, instead it represents relative direction

Vector vs magnitude example:
* Velocity is change of x and y direction by unit of measurement per unit of time, for example $\begin{bmatrix} 10 & 5 \end{bmatrix}$ km per hour. Velocity is a vector
* Speed is total speed, speed is magnitude (and scalar or a point). For example $\sqrt{10^2 + 5^2} = 5\sqrt{5}$ km/h

Zero vector - vector which has all element equal to zero. It's magnitude is 0. This vector is additive identity

Difference of vectors - can be imagined as vector coming the end of another vector. For example Having vector $a$ and $b$, then $a$ - $b$ is vector coming from $b$ to $a$
![[Pasted image 20260615222419.png|208]]
vector distance is useful to determine vector between two points or distance between points. 
Formulae for distance between two points is derived from magnitude formulae and can have unlimited amount of components. it doesn't matter from which vector we calculate difference
$||\vec{b} - \vec{a}|| = \sqrt{\sum^n_{i=0}{(b_i - a_i)}^2}$
example for $\vec{a} = (2, 3)\ \vec{b} = (6,2)$:
$\sqrt{(6 - 2)^2 + (2 - 3)^2} = \sqrt{4^2 + 1^2} = \sqrt{16 + 1} = \sqrt{17}$  

Vector from points is computed by difference between points (again, vector from $a$ to $b$ must be computed as difference from $b$ and $a$)
$a = (5, 10)$
$b=(10,15)$
$(10 - 5, 15 - 10) = (5, 5)$

radius vector: positional vector

## Dot product
Dot product (vector multiplication) has two related definitions. 
1. Coordinate definition defines vector multiplication as sum of multiplication of vector components (imagine as matrix multiplication where result is 1x1 matrix).
   $a*b = \sum_i a_i*b_i$ (vector components are not limited to 2). Coordinate definition is basically matrix multiplication 
	$\begin{bmatrix} a_1 & a_2 \end{bmatrix} * \begin{bmatrix} b_1 \\ b_2 \end{bmatrix} = [a_1 * b_1 + a_2 * b_2]$. Geometrically this definition is defined as projection of vector $\vec{a}$ into another vector $\vec{b}$ by extending $\vec{a}$ by scalar result of vector multiplication. Result is signed length that is scaled by length of $\vec{a}$. Graphically it's vector $\vec{a}$ extended by scalar result of vector multiplication.  the further from vector direction, the less value of vector is
	* dot product is zero when vector is perpendicular - angle $90\textdegree$
	* dot product is negative when vector points to opposite direction - angle $(90\textdegree, 270\textdegree)$
	* dot product is positive when vector points in the same direction - angle $(-90\textdegree, 90\textdegree)$
	![[Pasted image 20260719152621.png|413]]
	Dot product can be scaled by length $k$ of vector $a$ and length of vector $b$. $(ka) * b = k(a*b) = a * (kb)$. Dividing dot product by lengths will result in in value between (-1, 1)
	![[Pasted image 20260719214328.png|405]]
	using this definition of dot product (which measures only parallel displacement) it's also possible to compute perpendicular vector and it's distance
	$b = b_{parallel} + b_{perpendicular}$
	$b_{parallel} = \dfrac{(a * b)}{||a||}a$ (projected vector)
	$b_{perpendicular} = b_{parallel} - b$
	![[Pasted image 20260719180019.png|366]]
	dot product of vector itself is length squared $a*a = |a|^2$, e.g projected vector is multiplied by it's length
	![[Pasted image 20260719220018.png|379]]
	dot product is defined even in 3D
	![[Pasted image 20260721164231.png|337]]
2. Trigonometrical definition is based on previous definition. If we took both unit vectors, create projection, via trigonometry we can compute angle between them $cos(\phi) = a/h$ and since $h$ is 1 and $a$ is $\hat a * \hat b$, then $cos(\phi) = \hat a * \hat b$ (projection).
	    ![[Pasted image 20260720205545.png|162]] 
   This formula can applied on non unit vectors using property of scaling by dividing dot product by lengths vectors $||a||$ and $||b||$ and thus retrieving dot product as if both vector vectors were unit vectors. Angle between vector is equal to dot product divided by their length $a*b = ||a|| * ||b|| * cos(\phi)$. If one or both vectors are zero, then result angle will be same as if both vectors were perpendicular
   
   This definition also works in 3D and computation is same, but angle will be relative to 3 axis. For example having vector $a$ (2, 3, 4) and vector $b$ (-2, -3, -4) angle between them will be $180\textdegree$ (scaling doesn't affect result). 

   
   This definition can be also derived from cosine law
	![[Pasted image 20260615225209.png]]
	[source](https://www.youtube.com/watch?v=afHTz7jrmGo)
	
dot product is commutative and distributes over addition and subtraction ($a * (b + c) = a * b + a * c$)
### Direction cosines 
Direction cosines can applied only in 3D and are derived from Dot product. They are used to determine how close vector points to axis using unit vector with 1 component as base in degree range $<0, 180>$, where $0\textdegree$ is vector parallel to axis having all components equal to $0$, $90\textdegree$ is vector with axis component equal to $0$ and $180\textdegree$. Angle can't be less than $90\textdegree$ if vector points to opposite direction relative to axis and can't be less than $0\textdegree$ if it points to positive direction. Moving unrelated components further in any direction will decrease angle relative to axis. 
* $cos (\alpha) = \dfrac{a * i}{||a||}$ ; $i = (1, 0, 0)$ angle relative to x axis 
* $cos (\beta) = \dfrac{a * j}{||a||}$ ; $j = (0, 1, 0)$ angle relative to y axis 
* $cos (\gamma) = \dfrac{a * k}{||a||}$ ; $k = (0, 0, 1)$ angle relative to z axis
 
example: vec(-1, 1, 1) and angle relative to x axis
 ![[Pasted image 20260721201524.png|318]]
direction cosines can be used to compute dot product between two vectors
$cos(\alpha) * cos(\alpha') + cos(\beta) * cos(\beta') + cos(\gamma) * cos(\gamma')$ (it's actually dot product formulae from another perspective, it's like normalizing all components and then computing dot product) $\dfrac{a_{x}}{||a||} * \dfrac{b_{x}}{||b||} + \dfrac{a_{y}}{||a||} * \dfrac{b_{y}}{||b||} + \dfrac{a_{z}}{||a||} * \dfrac{b_{z}}{||b||} = cos\theta$

Direction cosines identities:
1. $cos^2(\alpha) + cos^2(\beta) + cos^2(\gamma) = 1$ 
   derived from magnitude formulae, $|a|^2 = a_0^2 + a_1^2 + a_2^2$ divide by length $\dfrac{a^2_0}{|a|^2} + \dfrac{a^2_1}{|a|^2} + \dfrac{a^2_2}{|a|^2} = 1$, simplify $(\dfrac{a_0}{|a|})^2 + (\dfrac{a_1}{|a|})^2 + (\dfrac{a_2}{|a|})^2 = 1$ replace with direction cosines $cos^2(\alpha) + cos^2(\beta) + cos^2(\gamma) = 1$. Using this identity we can prove if we can form vector with such angles in 3d, for example having having all angles $60\textdegree$, $cos^2(60\textdegree) + cos^2(60\textdegree) + cos^2(60\textdegree) = 1$, $1/4 + 1/4 + 1/4 \ne 1$. Only if $cos(\theta)$ is equal to $1/\sqrt{3}$ is possible to form vector with equal angles
	![[Pasted image 20260723105833.png|281]]

## Cross product
Cross product is a vector that is perpendicular to both vectors. Can be applied only in 3D. Extensively used to determine normal vector, sign of angle between two vectors or direction of rotation.
cross product is not commutative $a \times b = -(b \times a)$

formulae which is derived using determinant
$\begin{bmatrix} y_1*z_2 - z_1 * y_2 \\ z_1*x_2 - x_1*z_2 \\ x_1*y_2 - y_1*x_2  \end{bmatrix}$

Length of perpendicular vector is equal to $||a \times b|| = ||a||\ ||b||sin(\theta)$, which is also equal to area of parallelogram $(b * h)$
so we can modify formulae $b = ||a||$, $h = ||b||  sin(\theta)$ and get $||a||\ ||b||sin(\theta)$

![[Pasted image 20260723191058.png|325]]


There are two directions which $a \times b$ can be perpendicular, whatever we make clockwise or counterclockwise turn can be determined by placing vector $b$ at the end. Axis from what we are looking matters (what axis looks backwards), because it defines which way is clockwise and counterclockwise. Sign of cross product can determine if rotation is clockwise or counterclockwise

Looking from positive axis in **right handed** coordinate system:
* counter clockwise rotation (CCW): ($> 0$) vector points toward you
  ![[Pasted image 20260723120146.png|257]] 
* clockwise rotation (CW): $(< 0)$ vector points in away from you
  ![[Pasted image 20260723120240.png|360]]
  ![[Pasted image 20260726171050.png|396]]
Looking from positive axis in **left handed** system:
* counter clockwise rotation (CCW): $(<0)$ vector points in away from you
  ![[Pasted image 20260726164452.png|355]]
* clockwise rotation (CW): (> 0) vector points towards you
  ![[Pasted image 20260726164056.png|404]]
rules become inverted if we will look from negative side, for if we are looking from negative -y, then clockwise became counterclockwise
![[Pasted image 20260726171318.png|377]]
cross product of parallel vector is equal to 0

cross products of each axis:
$x = (1, 0, 0), y = (0, 1, 0), z = (0, 0, 1)$
$x \times y = z+$ (0, 0, $x_1*y_2 - y_1*x_2$) = (0, 0, $1*1 - 0*0$) = (0, 0, 1)
$z \times x = y+$ ($z_1*x_2 - x_1*z_2, 0, 0$) = (0, $1*1 - 0*0$, 0) = (0, 1, 0)
$y \times z = x+$ ($y_1*z_2 - z_1*y_2, 0, 0$) = ($1*1 - 0*0$, 0, 0) = (1, 0, 0)
$y \times x = z-$ (0, 0, $x_1*y_2 - y_1*x_2$) = (0, 0, $0*0 - 1*1$) = (0, 0, -1)
$x \times z = y-$ ($z_1*x_2 - x_1*z_2, 0, 0$) = (0, $0*0 - 1*1$, 0) = (0, -1, 0)
$z \times y = x-$ ($y_1*z_2 - z_1*y_2, 0, 0$) = ($0*0 - 1*1$, 0, 0) = (-1, 0, 0)
direction can be also determined by hand, placing thumb in direction of $a$ and index finger in direction of $b$, so direction perpendicular to both axis will be where cross product points