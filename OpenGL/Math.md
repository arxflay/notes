Square units (surface) - size of each size of square, for example square 5x5cm contains 25 squares (each have side length 1cm) or in another words, it's surface is $25cm^2$

area of triangle = $\dfrac{b * h}{2}$ where b is base and h is shortest height to base

![[Pasted image 20260703153750.png|161]]

### Chord intersection theorem

^00d4f6

If two chord intersect and divide chord in two length: a and b for first chord and c and d for second chord, then $ab = cd$, e.g are of two rectangle that formed by divided chords are identical. The reason is that intersected chords form 2 triangles in point of intersection. Each triangle is similar triangle, because both angles are on same arc [[Angles#^8de587 |Subtended angle theorem]]. If we construct two triangles and compare them side by side, then it will form parallelogram


### Vectors

difference of vectors can be imagined as vector coming the end of another vector. For example Having vector A and B, then A - B is vector coming from B to A

![[Pasted image 20260615222419.png|208]]


unit vector - vector with length 1.
vector normalization - dividing vector by it's length to get unit vector. Direction will not change.

Dot product (vector multiplication) has two related definitions. 
1. Coordinate definition defines vector multiplication as sum of multiplication of vector components (imagine as matrix multiplication where result is 1x1 matrix).
   $a*b = \sum_i a_i*b_i$ (vector components are not limited to 2). Coordinate definition is basically matrix multiplication 
	$\begin{bmatrix} a_1 & a_2 \end{bmatrix} * \begin{bmatrix} b_1 \\ b_2 \end{bmatrix} = [a_1 * b_1 + a_2 * b_2]$ 
2. Geometrical definition extends previous definition. sum of multiplication of vector components is equal to multiplication of vector lengths and angle between them. $a*b = ||a|| * ||b|| * cos(\phi)$, where $\phi$ is angle, $||a||$ and $||b||$ are lengths. If both vectors are unit vector, then $a*b$ = $cos(\phi)$, which is why unit vectors are useful
Geometrical definition is used for finding angle between vectors
dot product of vector itself is length squared $a*a = |a|^2$
proof of geometrical definition (length of vector because we substitute vectors as sides but sides have length not direction):
![[Pasted image 20260615225209.png]]
[source](https://www.youtube.com/watch?v=afHTz7jrmGo)

for matrix multiplication to work, first matrix column count must equal to second matrix row count. Result of matrix multiplication has row count of first matrix and column count of second matrix ($m_1n_1*m_2n_2 = m_1n_2$, where m = rows, n = columns)
$m1 = 1 x 2$
$m2 = 2 x 3$
$m3 = 1x3$
$\begin{bmatrix} a_1 & a_2  \end{bmatrix} * \begin{bmatrix} b_1 & b_2 & b_3\\ b_4  & b_5 & b_6 \end{bmatrix} = \begin{bmatrix} a_1 * b_1 + a_2 * b_4 & a_1 * b_2 + a_2 * b_5 & a_1 * b_3 + a_2 * b_6   \end{bmatrix}$ 

### Interpolations
1. linear interpolation - interpolation between x0 and x1, mapping range of x0-x1 to value range (0.0-1.0), values smaller or bigger than this range are outside of interpolation. 
	$\dfrac{x - x_0}{x_1 - x_0}$

### Analytic geometry

circle: $(x-m)^2 + (y-n)^2 = r^2$ or if S = 0, $x^2 + y^2 = r^2$



### Number theory

discrete - countable numbers, for example 1, 2, 3, 4 or set of points or function like $floor(x)$ on open interval 
continuous - uncountable numbers, function with no abrupt changes of value ($sin$, $log$) or even $floor(x)$ if interval is $(x, x+1)$. Technically endless amount of values

Natural number ($\mathbb{N}$) - set of whole, positive numbers excluding 0 (except if denoted as $\mathbb{N}_0$)
Integers ($\mathbb{Z}$) - set of whole, positive and negative numbers including 0 (except if denoted as $\mathbb{Z}^+$)
Rational numbers ($\mathbb{Q}$) - set of numbers represented by fraction
Real numbers ($\mathbb{R}$) - set of numbers that can't be represented by fraction (endless sequence like $\pi$)

Each set of numbers is subset of previous set (ex: natural numbers is subset of integers)
### Cartesian coordinate system

Cartesian coordinate system is named after latin version of surname of Rene Decrates
Graph origin - center of graph, usually (0,0) for 2D or (0,0,0) for 3D, but it's up to us where will be center of graph, for example (1,1) will be also valid origin
Graph axis - coordinate line that can be oriented whatever we want. By rotation or changing faces we can return to original coordinate system
Plane - 2D surface. Analogue to point (0D), line (1D), or 3D.
#### Cartesian 3D
Naming of axis and direction of axis is not standardized in 3D. There are exactly two coordinate systems, left handed and right handed. They are named this way because they they can be represented by fingers of the hand. 

Left handed: 
* x+ - right
* y+ - top
* z+ - forward

Right handed: 
* x+ - left
* y+ - right
* z+ - forward

For consistency with 2D, x+ and z+ are usually inverted in right handed system, so x+ points to right and z+ points to backwards. Swapping (Negating) two axis will not change handiness (it's like rotation of original coordinate system by $180\textdegree$), but swapping direction of single axis will change handiness. 

![[Pasted image 20260624184944.png]]

Rotation direction is different for each hand. To determine direction, point thumb axis you want to rotate from. Curled fingers will be the direction.

![[Pasted image 20260624185222.png|442]]
There are 24 positions for each hand, in total 48 possible combinations (imagine coordinates as cube, cube has in total 6 sides, we can spin each side 4 times, so $6*4=24$)

3D object can be represented as multiple 2d planes
![[Pasted image 20260624184915.png|418]]

