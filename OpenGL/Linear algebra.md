## Common principles 

### Linear combination 
Linear combinations is defined as sum of terms, where each term is multiplied by constant (some number). Term could be either variable, number or vector. Depending on context, linear combination is either the value or expression. Examples:

1. $2x + y$ is a linear combination $ax + by$ where constant $a$ and $b$ are constant, $x$ and $y$ are terms
2. $f(a) = 10a$, where $10$ is a term and $a$ is a constant
3. $f(x) = x * cos(\theta)$, where $x$ is a constant and $cos(\theta)$ is term
4. Vector space R^2, where i is (1, 0) and k (0, 1), thus any vector in R^2 space an be expressed as combination of two vectors (ai + bk), for example (1, 5) could be expressed as 1i + 5k
5. Combination of polynomials, p1: $x$, p2: $x^2 - 20$, p3: $x^3$, which can be expressed as $ax + b(x^2 - 20) + cx^3$

### Linear dependence 
Linear dependence means that at least one term in the set can be expressed as a linear combination of the other terms. Other way to define it is that exists constants (which are not all zero) that will make linear combination equal to 0.

Example of linear dependence:
	Having vectors $p = (0, 1)$, $q = (1, 0)$, $r = (1/\sqrt{2}, 1/\sqrt{2})$, there exists combination $p + q + r = 0$ such as $q * (1/\sqrt{2}) + p * (1/\sqrt{2}) + -1 * r = 0$ and there exists combination of p and q that is equal to r, $q * 1/\sqrt{2} + p * 1/\sqrt{2} = r$. Zero vector is always dependent 

Example of linear independence:
	Having vectors $p = (0, 1)$, $q = (1, 0)$ there are no constants, that will make linear combination equal to 0 or equal to other term. Other example is $(-1,1)$ and $(1,1)$ or $(1, -1)$ and $(1,1)$

### Span and basis

^fe779d

**Spanning set**: subset of vectors S in vector space V, by which we can express all elements in that space via linear combination, $span(S) = V$. Spanning set doesn't necessary have to be finite or linear independent

**Linear span (span)**: set formed by linear combination of spanning set. Span is subspace of vector space V when not all elements can be expressed by spanning set. For example, spanning set S $\{(1,0)\}$ and vector space $\mathbb{R}^2$, S is subspace of $\mathbb{R}^2$ because it's can't represent all elements in $\mathbb{R}^2$

**Basis**: <u>spanning set of linear independent elements</u> of vector space V. For example, vector space $\mathbb{R}^3$ with canonical basis is $i=(1,0,0)$, $j=(0,1,0)$, $k=(0,0,1)$. Poorly chosen basis will span only subset of vector space.  ^bd3fba

**Rank**: number of dimensions that can be described by basis. Rank is named full rank if it's possible to represent all elements in vector space by linear combination of basis

**Orthogonal basis**: each vector is perpendicular to each other or in other words, for each component of vector in vector space V we need only one vector from spanning set. Example is ($i=(1,0)$, $j=(0,1)$)

**Orthonormal basis**: all vectors in spanning set have unit length

## Matrices

Matrix is mathematical structure, where elements arranged in rows and columns. Matrix can be seen as compact way to describe linear combination with vector, where columns are vector components (or rows, if ve are using row vectors). Matrices start with capital later, like this - $M$. Selected element is denoted as index number for row ($i$) and column ($j$) under $M$ - $M_{ij}$. Index start from 1. Matrix size is denoted as $m \times n$
### Special types of matrices
- **Square matrix**: matrix has same count of rows as column, e.g $m = n$
- **Symmetric matrix**: square matrix, where each values in columns for row $x$ are same as values in rows for column $x$. Transpose doesn't affect matrix, $S = S^T = S$
  $\begin{bmatrix} 7 & -1 & 2 \\ -1 & 10 & 8  \\ 2 & 8 & 20 \end{bmatrix}$ $M{1j} = M{i1}$, $M{2j} = M{i2}$, $M{3j} = M{i3}$
- **Asymmetric (skew symmetric) matrix:** Square matrix, transpose of this matrix is equal to matrix negation $A^T = -A$. Values on diagonal must be 0, because transpose doesn't affect diagonal
  $\begin{bmatrix} 0 & -1 & -9 \\ 1 & 0 & 4 \\ 9 & -4 & 0 \end{bmatrix}$ $A^T$ = $\begin{bmatrix} 0 & 1 & 9 \\ -1 & 0 & -4 \\ -9 & 4 & 0 \end{bmatrix}$
- **Diagonal matrix**: square matrix, that has numbers non zero numbers only on diagonal. Transpose doesn't affect matrix, $D = D^T = D$
  $D = \begin{bmatrix} 4 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 3 \end{bmatrix}$
- **Identity matrix**: special case of diagonal matrix, that has all 1 on diagonal. Matrix multiplied by this matrix is not changed. This matrix is like number 1 when multiplying scalars. Identity matrix is denoted as I with size under it, example: $I_3 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$
- **Vector**: technically vector is one dimensional a matrix. Vectors exists in two types - column $\begin{bmatrix} x \\ y \\ z \end{bmatrix}$ or row vectors $\begin{bmatrix} x & y & z \end{bmatrix}$, they are not same from matrix perspective
### Matrix basic operations

1. **Matrix multiplication with scalar**: similar to vector, all components are multiplied with scalar
   properties:
	   1. $k(A*B) = kA * B = A * kB$
2. **Matrix addition/subtraction with another matrix**: similar to vector 
3. **Matrix multiplication**: result of matrix multiplication is another matrix that has same **row count** as <u>matrix on left side</u> and same **column count** as <u>matrix on right</u> side. <u>Matrix on left side must have same column count as right matrix row count</u>, otherwise operation is undefined. Each element in final matrix is computed as vector dot product of row from matrix on left side with column from matrix on right side. Matrix multiplication with vector can be interpreted as linear combination
	Example:
	$\begin{bmatrix} \color{yellow} 1 & \color{yellow} 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix} * \begin{bmatrix} \color{yellow} 4 & 4 \\ \color{yellow} 5 & 5 \end{bmatrix} = \begin{bmatrix} 1 * 4 + 2 * 5 & .. \\ .. & .. \\ .. & .. \end{bmatrix} = \begin{bmatrix} 14 & .. \\ .. & .. \\ .. & .. \end{bmatrix}$ final matrix will have size 3x2
	next row example: 
	$\begin{bmatrix}  1 & 2 \\ \color{yellow} 3 & \color{yellow} 4 \\ 5 & 6 \end{bmatrix} * \begin{bmatrix} \color{yellow} 4 & 4 \\ \color{yellow} 5 & 5 \end{bmatrix} = \begin{bmatrix} 14 & .. \\ 3 *4 + 4 * 5 & .. \\ .. & .. \end{bmatrix} = \begin{bmatrix} 14 & .. \\ 32 & .. \\ .. & .. \end{bmatrix}$
	next column example:
	$\begin{bmatrix}  \color{yellow} 1 & \color{yellow} 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix} * \begin{bmatrix} 4 & \color{yellow} 4 \\ 5 &  \color{yellow} 5 \end{bmatrix} = \begin{bmatrix} 14 & 1 * 4 + 2 * 5 \\ 32 & .. \\ .. & .. \end{bmatrix} = \begin{bmatrix} 14 & 14 \\ 32 & .. \\ .. & .. \end{bmatrix}$
	Matrix multiplication with vector be interpreted as linear combination of vector. If we took canon basis for $V^n$ we can decompose matrix columns (or rows, we multiplying with row vector) as it was basis vectors.
	column vector ($\begin{bmatrix} p & q & r \end{bmatrix}$):
        $x$     $y$     $z$
	$i = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix},  \begin{bmatrix} m_{11} & m_{12} & m_{13} \\ m_{21} & m_{22} & m_{23} \\  m_{31} & m_{32} & m_{33} \end{bmatrix} * i = \begin{bmatrix} m_{11} \\ m_{21} \\ m_{31} \end{bmatrix}$ 
	$j = \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} m_{11} & m_{12} & m_{13} \\ m_{21} & m_{22} & m_{23} \\  m_{31} & m_{32} & m_{33} \end{bmatrix} * j = \begin{bmatrix} m_{12} \\ m_{22} \\ m_{23} \end{bmatrix}$ 
	$i = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} m_{11} & m_{12} & m_{13} \\ m_{21} & m_{22} & m_{23} \\  m_{31} & m_{32} & m_{33} \end{bmatrix} * i = \begin{bmatrix} m_{13} \\ m_{23} \\ m_{33} \end{bmatrix}$ 
	row vector($\begin{bmatrix} - p - \\ - q - \\ - r - \end{bmatrix}$):
	$i = \begin{bmatrix} 1 & 0 & 0 \end{bmatrix}, i *\  \begin{array}{c c c} x \\ y \\ z\end{array} \begin{bmatrix} m_{11} & m_{12} & m_{13} \\ m_{21} & m_{22} & m_{23} \\  m_{31} & m_{32} & m_{33} \end{bmatrix} = \begin{bmatrix} m_{11} \\ m_{12} \\ m_{13} \end{bmatrix}$ 
	$j = \begin{bmatrix} 0 & 1 & 0 \end{bmatrix}, j *\ \ \ \begin{bmatrix} m_{11} & m_{12} & m_{13} \\ m_{21} & m_{22} & m_{23} \\  m_{31} & m_{32} & m_{33} \end{bmatrix} = \begin{bmatrix} m_{21} \\ m_{22} \\ m_{23} \end{bmatrix}$ 
	$k = \begin{bmatrix} 0 & 0 & 1 \end{bmatrix}, k *\ \ \begin{bmatrix} m_{11} & m_{12} & m_{13} \\ m_{21} & m_{22} & m_{23} \\  m_{31} & m_{32} & m_{33} \end{bmatrix} = \begin{bmatrix} m_{31} \\ m_{32} \\ m_{33} \end{bmatrix}$
	Matrix multiplication properties:
	1. $A*B\ne B*A$ (non commutative)
	2. $A * (BC) = A*B*C$ (associativity)
> [!note]
> Most fields use column based vectors, thus order of operations read from right to left ($CBAv$), whereas other APIs may use row based vectors, where operations are read from left to right ($vABC$). Order of operations is inversed for row based vector (since $(AB)^T = B^T*A^T$). 
4. **Matrix transpose**: swaps rows with columns. Transpose operation is written on top of matrix, like this - $M^T$. $M{ij}$ becomes $M{ji}$
	$M = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}, M^T = \begin{bmatrix} 1 & 4 & 7 \\ 2 & 5 & 8 \\ 3 & 6 & 7 \end{bmatrix}$
	properties:
	   1. $(AB)^T = B^TA^T$, $(M_1*M_2...M_n)^T = M_n^T ... M_2^T * M_1^T$

## Linear transformations
Liner transformations are transformations that transform vector using matrices. Linear transformations are based on linear combination (since vector can be represented as linear combination)
### Basic transformations
This section describes basic transformations from origin
#### Rotation 2D
Rotation in 2D is rotation around point
Matrices for rotation are below:

**counter-clockwise (standard 2D) rotation:**
					   $x$        $y$
for column vectors $(M)$ $\begin{bmatrix} cos(\theta) & -sin(\theta) \\ sin(\theta) & cos(\theta)   \end{bmatrix}$, for row vectors ($M^T$) $\begin{array}{c c} x \\ y \end{array} \begin{bmatrix} cos(\theta) & sin(\theta) \\ -sin(\theta) & cos(\theta)   \end{bmatrix}$ 
**clockwise rotation**:
					    $x$      $y$
for column vectors $(M)$ $\begin{bmatrix} cos(\theta) & sin(\theta) \\ -sin(\theta) & cos(\theta)   \end{bmatrix}$, for row vectors ($M^T$) $\begin{array}{c c} x \\ y \end{array} \begin{bmatrix} cos(\theta) & -sin(\theta) \\ sin(\theta) & cos(\theta)   \end{bmatrix}$ 

Counter clockwise Rotation matrix is derived from sum of angle with hypotenuse of length 1 (and similarly with angle difference for clockwise matrix)
1. basis $p$: $cos(\alpha + \beta) = cos(\alpha)cos(\beta) - sin(\alpha)sin(\beta)$, $sin(\alpha)$ = y (because $sin(\alpha) = opposite/hypotenuse$ and hypotenuse is 1, so $sin(\alpha) = opposite$) and $cos(\alpha) = x$, so $cos(\alpha + \beta) = x*cos(\beta) - y*sin(\beta) = \begin{bmatrix}cos(\theta) & -sin(\theta)\end{bmatrix}$
2. basis $q$: $sin(\alpha + \beta) = sin(\alpha)cos(\beta) + sin(\beta)cos(\alpha)$, $sin(\alpha)$ = y (because $sin(\alpha) = opposite/hypotenuse$ and hypotenuse is 1, so $sin(\alpha) = opposite$) and $cos(\alpha) = x$, $sin(\alpha + \beta) = y*cos(\beta) + x*sin(\beta) =\begin{bmatrix}sin(\theta) & cos(\theta)\end{bmatrix}$
#### Rotation 3D
Rotation in 3D is not around point but is [[Coordinate spaces#^81e292|around cardinal axis]] 
1. **Around Y axis**: 
   					   $x$     $y$    $z$
	for column vectors $\begin{bmatrix} cos(\theta) & 0 & sin(\theta) \\ 0 & 1 & 0 \\ -sin(\theta) & 0 & cos(\theta)   \end{bmatrix}$ for row vectors $\begin{array}{c c c} x \\ y \\ z \end{array}\begin{bmatrix} cos(\theta) & 0 & -sin(\theta) \\ 0 & 1 & 0 \\ sin(\theta) & 0 & cos(\theta)   \end{bmatrix}$
2. **Around Z axis**:
   					   $x$     $y$    $z$
	for column vectors $\begin{bmatrix} cos(\theta) & -sin(\theta) & 0 \\ sin(\theta) & cos(\theta) & 0 \\ 0 & 0 & 1  \end{bmatrix}$ for row vectors $\begin{array}{c c c} x \\ y \\ z \end{array}\begin{bmatrix} cos(\theta) & sin(\theta) & 0 \\ -sin(\theta) & cos(\theta) & 0 \\ 0 & 0 & 1  \end{bmatrix}$ 
3. **Around X axis**:
   					   $x$     $y$    $z$
   for column vectors $\begin{bmatrix} 1 & 0 & 0 \\ 0 & cos(\theta) & -sin(\theta)  \\ 0 & sin(\theta) & cos(\theta)  \end{bmatrix}$ for row vectors $\begin{array}{c c c} x \\ y \\ z \end{array}\begin{bmatrix} 1 & 0 & 0 \\ 0 & cos(\theta) & sin(\theta)  \\ 0 & -sin(\theta) & cos(\theta)  \end{bmatrix}$
Same matrices work for right handed and left handed system
This matrices are derived the same way as 2D (each rotation is performed on 2D plane)

##### Rotation around arbitrary axis 
It's also possible to rotate around arbitrary (that comes through origin) axis provided by vector $\hat n$, but is less common and harder to derive. Principle is to determine 2D plane and rotate vector in this 2D plane. Derivation can be found[[Derivation of 3D rotation matrix around arbitrary axis | here]]. 

For column vectors:
$S = \begin{bmatrix}n^2_x (1 - cos(\theta))  + cos(\theta) & n_yn_x (1 - cos(\theta)) - n_z sin(\theta) & n_zn_x (1 + cos(\theta)) + n_y sin(\theta) \\ n_xn_y(1 - cos(\theta)) + sin(\theta)n_z & n^2_y(1-cos(\theta)) + cos(\theta) & n_yn_z(1 - cos(\theta)) - sin(\theta)n_x \\ n_xn_z(1 - cos(\theta)) - sin(\theta)n_y & n_yn_z(1-cos(\theta)) + sin(\theta)n_x & n_z^2(1 - cos(\theta)) + cos(\theta) \end{bmatrix}$

For row vectors:
$S^T = \begin{bmatrix}n^2_x (1 - cos(\theta))  + cos(\theta) & n_xn_y(1 - cos(\theta)) + sin(\theta)n_z & n_xn_z(1 - cos(\theta)) - sin(\theta)n_y \\ n_yn_x (1 - cos(\theta)) - n_z sin(\theta) & n^2_y(1-cos(\theta)) + cos(\theta) & n_yn_z(1-cos(\theta)) + sin(\theta)n_x \\ n_zn_x (1 + cos(\theta)) + n_y sin(\theta) & n_yn_z(1 - cos(\theta)) - sin(\theta)n_x & n_z^2(1 - cos(\theta)) + cos(\theta) \end{bmatrix}$

### Scale 

**Uniform scale**: all vector components are multiplied by single value. Angles and ratios remain same. Uniform scale matrix is equivalent for multiplying vector by scalar $k$. Area will be increased by $k^2$ and area by $k^3$
$S_u = \begin{bmatrix} k & 0 & 0 \\ 0 & k & 0 \\ 0 & 0 & k \end{bmatrix}$, for 2D $S_u = \begin{bmatrix} k & 0 \\ 0 & k \\\end{bmatrix}$
**Nonuniform scale**: vector components are multiplied by different coefficients. Angle are not preserved. $S_{nu} = \begin{bmatrix} k_x & 0 & 0 \\ 0 & k_y & 0 \\ 0 & 0 & k_z \end{bmatrix}$, for 2D $S_{nu} = \begin{bmatrix} k_x & 0 \\ 0 & k_y \end{bmatrix}$
if $|k|$ is > 1, then component is extended
if $|k|$ < 1, then component is shrinked
if k is zero, then it is[[Linear algebra#^ca4f5b | orthographic projection]]
if k < 0, then zero, then it's[[Linear algebra#^cd089e | reflection]]

##### Scaling along arbitrary axis

Scaling along arbitrary axis $\hat n$ (that comes through origin) with scale factor $k$ is similar rotation around arbitrary axis $\hat n$. Matrix can be applied for row and column vectors, for 2D and 3D

**3D scale matrix** (Can be applied for row and column vectors):
	$S_{\hat n} = \begin{bmatrix} 1 + n_x^2 (k - 1) & n_xn_y (k - 1) & n_xn_z (k - 1) \\ n_xn_y (k - 1) & 1+ n_y^2 (k - 1) & n_yn_z (k - 1) \\ n_xn_z (k - 1) & n_yn_z * (k - 1) & 1 + n_z^2 * (k - 1)\end{bmatrix}$
	
**2D scale matrix** (Can be applied for row and column vectors):
	$S_{\hat n} = \begin{bmatrix} 1 + n_x^2 (k - 1) & n_xn_y (k - 1) \\ n_xn_y (k - 1) & 1+ n_y^2 (k - 1)\end{bmatrix}$

Computation is below
![[Pasted image 20260808122450.png|610]]	
We have to find vector $v'$, which scaled along axis
1. $v' = v'_{perpendicular} + v'_{parallel}$, we just have to compute $v'_{perpendicular}$ and $v'_{parallel}$
2. $v_{parallel}$ is on same axis as $\hat n$, we can compute it by dot product. 
3. We can easily compute $v'_{paralell}$, because we are just changing size of $v_{parallel}$ by $k$ based on previous relationship with $\hat n$
4. Since we are scaling <u>along</u> arbitrary axis, $v_{perpendicular}$ will be not scaled because it's not on same axis, thus $v_{perpendicular} = v'_{perpendicular}$, and $v_{perpendicular} = v - v_{parallel}$ (we need this transformation because we have to somehow compute $v_{perpendicular}$)
5. Final formulae is $v' = v - v_{parallel} + v'_{parallel} = v - (\hat n * v)\hat n + k(\hat n * v)\hat n$
   $= v + (\hat n * v)\hat n  * (k - 1)$

We can transform it to matrix (3D example):
1. compute $(\hat n * v)$
$(\hat n * v) = (n_xv_x + n_yv_y + n_zv_z)$
$(\hat n * v)n_x = n_x^2v_x + n_xn_yv_y + n_xn_zv_z$
$(\hat n * v)n_y = n_xn_yv_x + n_y^2v_y + n_yn_zv_z$
$(\hat n * v)n_z = n_xn_zv_x + n_yn_zv_y + n_z^2v_z$
2. compute $p$, $q$, $r$
$p = v_x + (\hat n * v)\hat n_x  * (k - 1) = v_x * (1 + n_x^2 * (k - 1)) + v_y*(n_xn_y * (k - 1)) + v_z * (n_xn_z * (k - 1))$
$q = v_y + (\hat n * v)\hat n_y  * (k - 1) = v_x * (n_xn_y * (k - 1)) + v_y*(1+ n_y^2 * (k - 1)) + v_z * (n_yn_z * (k - 1))$
$r = v_z + (\hat n * v)\hat n_z  * (k - 1) = v_x * (n_xn_z * (k - 1)) + v_y*(n_yn_z * (k - 1)) + v_z * (1 + n_z^2 * (k - 1))$

### Orthographic projection ^ca4f5b

Projection is dimension reducing operation.
Orthographic projection is one of the type of projection, which is also called parallel projection, because line from point are parallel to projected counterparts (plane)
#### Projection along axis (2D) or plane (3D)
Simple case of orthographic projection, where one of $k$ for nonuniform scaling is 0 (discarded), thus projection is performed to perpendicular plane (3D) or perpendicular axis (2D).
3D:
	$P_{xy} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0  \end{bmatrix}$ $P_{xz} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1  \end{bmatrix}$ $P_{yz} = \begin{bmatrix} 0 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1  \end{bmatrix}$
2D:
	$P_{x} = \begin{bmatrix} 1 & 0  \\ 0 & 0  \end{bmatrix}$ $P_{y} = \begin{bmatrix} 0 & 0  \\ 0 & 1  \end{bmatrix}$

Projection of Z+ (Z+ is top in blender) to XY plane 
![[Pasted image 20260808125017.png|290]]
How it really looks
![[Pasted image 20260808125040.png|258]]
#### Projection along arbitrary line (2D) or plane (3D)

Derived from matrix for scaling along arbitrary axis, where k is replaced with 0 $P_{\hat n} = S(0, \hat n)$. However, plane/line defined by vector $\hat n$ is perpendicular to $\hat n$ ($\hat n$ can be imagine axis from what we are looking to object). Resulting plane comes through origin

**3D orthographic projection matrix** (Can be applied for row and column vectors):
	$P_{\hat n} = \begin{bmatrix} 1 - n_x^2 & -n_xn_y & -n_xn_z \\ -n_xn_y & 1- n_y^2 & -n_yn_z \\ -n_xn_z & -n_yn_z & 1 - n_z^2 \end{bmatrix}$
	
**2D orthographic projection matrix** (Can be applied for row and column vectors):
	$P_{\hat n} = \begin{bmatrix} 1 - n_x^2 & -n_xn_y \\ -n_xn_y & 1- n_y^2\end{bmatrix}$
	
![[Pasted image 20260808172406.png|502]]

### Reflection ^cd089e

Reflection is mirroring (flipping) about line (2D) or plane (3D)

#### Reflection around perpendicular axis
Reflection around axis is replacing one of the $k$ of scaling matrix (that scales around cardinal axis) with $-1$. Reflection will be performed about perpendicular axis/axes to what we are going negate

**3D reflection matrices:
	$R_{yz} = \begin{bmatrix} -1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$ $R_{xz} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$ $R_{xy} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & -1 \end{bmatrix}$
2D reflection matrices:
	$R_{y} = \begin{bmatrix} -1 & 0 \\ 0 & 1  \end{bmatrix}$ $R_{x} = \begin{bmatrix} 1 & 0  \\ 0 & -1 \end{bmatrix}$

Reflection around arbitrary axis can be also derived from scaling matrix $R_{\hat n} = S(-1, \hat n)$

**3D reflection matrix:
	$R_{\hat n} = \begin{bmatrix} 1 - 2n_x^2 & -2n_xn_y & -2n_xn_z \\ -2n_xn_y & 1 - 2n_y^2 & -2n_yn_z \\ -2n_xn_z & -2n_yn_z & 1 -2n_z^2  \end{bmatrix}$
	
**2D reflection matrix:
	$R_{\hat n} = \begin{bmatrix} 1 - 2n_x^2 & -2n_xn_y \\ -2n_xn_y & 1 - 2n_y^2 \end{bmatrix}$
	
![[Pasted image 20260809141518.png|387]]
#### Reflection around parallel axis
To rotate around parallel axis, we have to negate reflection matrix

**3D reflection matrix:
	$R_{\hat n} = \begin{bmatrix} 2n_x^2 - 1 & 2n_xn_y & 2n_xn_z \\ 2n_xn_y & 2n_y^2 - 1 & 2n_yn_z \\ 2n_xn_z & 2n_yn_z & 2n_z^2 -1  \end{bmatrix}$

**2D reflection matrix**:
$R_{\hat n} = \begin{bmatrix} 2n_x^2 - 1 & 2n_xn_y \\ 2n_xn_y & 2n_y^2 - 1 \end{bmatrix}$

![[Pasted image 20260809141959.png|389]]

### Shearing
Shearing is rarely used transformation, also known as **skew transform**, that skews (creates asymmetry) object, stretching it non uniformly, preserving area and volume. It work by adding another vector component with skew coefficient $s$ ($v_i = v_i + sv_j + ...$). For example, $x' = x + sy$, $x$ is sheared by $sy$. 

$x' = x + 1y$
![[Pasted image 20260809152715.png|283]]

Matrices for shearing is derived from $v_i = v_i + sv_j+...$, letter below $H$ denote what coordinate/s is being sheared. In 3D, it's possible to skew multiple coordinates by single coordinate, having coefficient for each coordinate

**3D shearing matrix**:
	multiple coefficients (for column vectors):
	$H_{xy} = \begin{bmatrix} 1 & 0 & t \\ 0 & 1 & s \\ 0 & 0 & 1  \end{bmatrix}$  $H_{xz} = \begin{bmatrix} 1 & 0 & 0 \\ s & 1 & 0 \\ t & 0 & 1  \end{bmatrix}$ $H_{yz} = \begin{bmatrix} 1 & s & 0 \\ 0 & 1 & 0 \\ 0 & t & 1  \end{bmatrix}$
	multiple coefficients (for row vectors):
	$H_{xy}^T = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ s & t & 1  \end{bmatrix}$  $H_{xz}^T = \begin{bmatrix} 1 & 0 & 0 \\ s & 1 & t \\ 0 & 0 & 1  \end{bmatrix}$ $H_{yz}^T = \begin{bmatrix} 1 & s & t \\ 0 & 1 & 0 \\ 0 & 0 & 1  \end{bmatrix}$
	single coefficient (for column vectors) 
	$H_{x} = \begin{bmatrix} 1 & s & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1  \end{bmatrix}$ or $H_{x} = \begin{bmatrix} 1 & 0 & s \\ 0 & 1 & 0 \\ 0 & 0 & 1  \end{bmatrix}$ and etc..

**2D shearing matrix**:
	for column vectors: 
	$H_x = \begin{bmatrix} 1 & s \\ 0 & 1 \end{bmatrix}$ $H_y = \begin{bmatrix} 1 & 0 \\ s & 1 \end{bmatrix}$
	for row vectors: 
	$H_x^T = \begin{bmatrix} 1 & 0 \\ s & 1 \end{bmatrix}$ $H_y^T = \begin{bmatrix} 1 & 0 \\ s & 1 \end{bmatrix}$
 
## Affine Transformations

