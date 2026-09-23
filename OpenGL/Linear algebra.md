## Common principles 

### Linear combination 
Linear combination is defined as a sum of terms where each term is multiplied by a constant (some number). A term could be either a variable, number, or vector. Depending on the context, a linear combination is either the value or the expression. Examples:

1. $2x + y$ is a linear combination $ax + by$ where $a$ and $b$ are constants, and $x$ and $y$ are terms
2. $f(a) = 10a$, where $10$ is a term and $a$ is a constant
3. $f(x) = x * cos(\theta)$, where $x$ is a constant and $cos(\theta)$ is a term
4. Vector space R^2, where i is (1, 0) and k is (0, 1); thus, any vector in R^2 space can be expressed as a combination of two vectors (ai + bk), for example, (1, 5) could be expressed as 1i + 5k
5. Combination of polynomials, p1: $x$, p2: $x^2 - 20$, p3: $x^3$, which can be expressed as $ax + b(x^2 - 20) + cx^3$

### Linear dependence 
Linear dependence means that at least one term in the set can be expressed as a linear combination of the other terms. Another way to define it is that there exist constants (which are not all zero) that will make the linear combination equal to 0.

Example of linear dependence:
	Having vectors $p = (0, 1)$, $q = (1, 0)$, $r = (1/\sqrt{2}, 1/\sqrt{2})$, there exists a combination $p + q + r = 0$ such as $q * (1/\sqrt{2}) + p * (1/\sqrt{2}) + -1 * r = 0$, and there exists a combination of p and q that is equal to r, $q * 1/\sqrt{2} + p * 1/\sqrt{2} = r$. The zero vector is always dependent 

Example of linear independence:
	Having vectors $p = (0, 1)$, $q = (1, 0)$, there are no constants that will make the linear combination equal to 0 or equal to another term. Other examples are $(-1,1)$ and $(1,1)$ or $(1, -1)$ and $(1,1)$

### Span and basis

^fe779d

**Spanning set**: a subset of vectors S in vector space V, by which we can express all elements in that space via a linear combination, $span(S) = V$. A spanning set doesn't necessarily have to be finite or linearly independent

**Linear span (span)**: a set formed by a linear combination of a spanning set. A span is a subspace of vector space V when not all elements can be expressed by the spanning set. For example, for spanning set S $\{(1,0)\}$ and vector space $\mathbb{R}^2$, S is a subspace of $\mathbb{R}^2$ because it can't represent all elements in $\mathbb{R}^2$

**Basis**: <u>a spanning set of linearly independent elements</u> of vector space V. For example, vector space $\mathbb{R}^3$ with a canonical basis is $i=(1,0,0)$, $j=(0,1,0)$, $k=(0,0,1)$. A poorly chosen basis will span only a subset of the vector space.  ^bd3fba

**Rank**: the number of dimensions that can be described by a basis. A rank is called full rank if it's possible to represent all elements in the vector space by a linear combination of the basis

**Orthogonal basis**: each vector is perpendicular to every other vector, or in other words, for each component of a vector in vector space V, we need only one vector from the spanning set. An example is ($i=(1,0)$, $j=(0,1)$)

**Orthonormal basis**: all vectors in the spanning set have unit length

## Matrices

A matrix is a mathematical structure where elements are arranged in rows and columns. A matrix can be seen as a compact way to describe a linear combination with a vector, where columns are vector components (or rows, if we are using row vectors). Matrices start with a capital letter, like this - $M$. A selected element is denoted as an index number for the row ($i$) and column ($j$) under $M$ - $M_{ij}$. Indices start from 1. Matrix size is denoted as $m \times n$
### Special types of matrices
- **Square matrix**: a matrix that has the same number of rows as columns, e.g., $m = n$
- **Symmetric matrix**: a square matrix where each value in the columns for row $x$ is the same as the value in the rows for column $x$. Transposition doesn't affect the matrix, $S = S^T = S$
  $\begin{bmatrix} 7 & -1 & 2 \\ -1 & 10 & 8  \\ 2 & 8 & 20 \end{bmatrix}$ $M{1j} = M{i1}$, $M{2j} = M{i2}$, $M{3j} = M{i3}$
- **Asymmetric (skew symmetric) matrix:** A square matrix whose transpose is equal to the matrix's negation $A^T = -A$. Values on the diagonal must be 0 because transposition doesn't affect the diagonal
  $\begin{bmatrix} 0 & -1 & -9 \\ 1 & 0 & 4 \\ 9 & -4 & 0 \end{bmatrix}$ $A^T$ = $\begin{bmatrix} 0 & 1 & 9 \\ -1 & 0 & -4 \\ -9 & 4 & 0 \end{bmatrix}$
- **Diagonal matrix**: a square matrix that has nonzero numbers only on the diagonal. Transposition doesn't affect the matrix, $D = D^T = D$
  $D = \begin{bmatrix} 4 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 3 \end{bmatrix}$
- **Identity matrix**: a special case of a diagonal matrix that has all 1s on the diagonal. A matrix multiplied by this matrix is not changed. This matrix is like the number 1 when multiplying scalars. The identity matrix is denoted as I with its size under it, example: $I_3 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$
- **Triangular matrix**: a square matrix where all numbers under the diagonal are zero (**upper triangular**) or all numbers above the diagonal are zero (**lower triangular**)
- **Vector**: technically, a vector is a one-dimensional matrix. Vectors exist in two types - column $\begin{bmatrix} x \\ y \\ z \end{bmatrix}$ or row vectors $\begin{bmatrix} x & y & z \end{bmatrix}$; they are not the same from a matrix perspective
### Matrix basic operations

1. **Matrix multiplication with a scalar**: similar to a vector, all components are multiplied by a scalar
   properties:
	   1. $k(A*B) = kA * B = A * kB$
2. **Matrix addition/subtraction with another matrix**: similar to a vector 
3. **Matrix multiplication**: the result of matrix multiplication is another matrix that has the same **row count** as the <u>matrix on the left side</u> and the same **column count** as the <u>matrix on the right</u> side. <u>The matrix on the left side must have the same column count as the right matrix's row count</u>; otherwise, the operation is undefined. Each element in the final matrix is computed as the vector dot product of a row from the matrix on the left side with a column from the matrix on the right side. Matrix multiplication with a vector can be interpreted as a linear combination
	Example:
	$\begin{bmatrix} \color{yellow} 1 & \color{yellow} 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix} * \begin{bmatrix} \color{yellow} 4 & 4 \\ \color{yellow} 5 & 5 \end{bmatrix} = \begin{bmatrix} 1 * 4 + 2 * 5 & .. \\ .. & .. \\ .. & .. \end{bmatrix} = \begin{bmatrix} 14 & .. \\ .. & .. \\ .. & .. \end{bmatrix}$; the final matrix will have size 3x2
	next row example: 
	$\begin{bmatrix}  1 & 2 \\ \color{yellow} 3 & \color{yellow} 4 \\ 5 & 6 \end{bmatrix} * \begin{bmatrix} \color{yellow} 4 & 4 \\ \color{yellow} 5 & 5 \end{bmatrix} = \begin{bmatrix} 14 & .. \\ 3 *4 + 4 * 5 & .. \\ .. & .. \end{bmatrix} = \begin{bmatrix} 14 & .. \\ 32 & .. \\ .. & .. \end{bmatrix}$
	next column example:
	$\begin{bmatrix}  \color{yellow} 1 & \color{yellow} 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix} * \begin{bmatrix} 4 & \color{yellow} 4 \\ 5 &  \color{yellow} 5 \end{bmatrix} = \begin{bmatrix} 14 & 1 * 4 + 2 * 5 \\ 32 & .. \\ .. & .. \end{bmatrix} = \begin{bmatrix} 14 & 14 \\ 32 & .. \\ .. & .. \end{bmatrix}$
	Basically, we are computing the dot product for each combination of a row vector and a column vector.
	Matrix multiplication with a vector can be interpreted as a linear combination of vectors. If we take the canonical basis for $V^n$, we can decompose matrix columns (or rows, if we are multiplying by a row vector) as if they were basis vectors.
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
> Most fields use column-based vectors; thus, the order of operations is read from right to left ($CBAv$), whereas other APIs may use row-based vectors, where operations are read from left to right ($vABC$). The order of operations is reversed for a row-based vector (since $(AB)^T = B^T*A^T$). 
4. **Matrix transpose**: swaps rows with columns. The transpose operation is written on top of the matrix, like this - $M^T$. $M{ij}$ becomes $M{ji}$
	$M = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}, M^T = \begin{bmatrix} 1 & 4 & 7 \\ 2 & 5 & 8 \\ 3 & 6 & 7 \end{bmatrix}$
	properties:
	   1. $(AB)^T = B^TA^T$, $(M_1*M_2...M_n)^T = M_n^T ... M_2^T * M_1^T$

### Matrix determinant

The determinant of a matrix is a special scalar (number) that characterizes properties of the matrix. A determinant can be computed only for a square matrix and is denoted as $|M|$ or $det\ M$.

**Minor of a matrix**: the determinant of a submatrix that has been formed by removing one row and one column from the original matrix. Denoted as $M^{\{ij\}}$, where $i$ is the number of the removed row and $j$ is the number of the removed column

**Matrix cofactor**: a cofactor is a minor of a matrix multiplied by $-1^{ij}$, where $i$ is the row number and $j$ is the column number. The formula is $-1^{ij} * M^{\{ij\}}$, for example, $M^{\{12\}} * -1^{1*2} = -M^{\{12\}}$

There are multiple ways to compute the determinant of a matrix depending on the size of the matrix. When computing the matrix, brackets are replaced with vertical lines
1. *For a $1 \times 1$ matrix*: the determinant is equal to the matrix itself (scalar)
2. **For a $2 \times 2$ matrix**: the product of scalars on the left diagonal subtracted by the product of scalars on the right diagonal
3. **For a $3 \times 3$ matrix**: the computation is similar to $2 \times 2$ by using Sarrus' rule, which is a special mnemonic where the matrix is extended by two rows. Compute 3 products of the left diagonal by moving one row down after each computation. In the same way, compute 3 products of the right diagonal. Subtract the 3 products of the left diagonal from the 3 products of the right diagonal.
4. *For any matrix $(n\times n)$*: Computed as the sum of matrix cofactors (Laplace expansion), where the number of cofactors is equal to $n$. Cofactors are computed for either minors, where $j$ is always 1 and i ranges from 1 to $n$, or the other way around.

![[Pasted image 20260812210945.png|449]]

The determinant of 2 vectors (2D matrix) is equal to the area of a parallelogram, and the determinant of 3 vectors (3D matrix) is equal to the volume of a parallelepiped   

Matrix determinant properties:
1. Associativity  $|AB| = |A| * |B|$
2. Determinant of identity matrix is always 1
   $\begin{vmatrix} 1 & 0 \\ 0 & 1 \end{vmatrix} = 1 * 1 - 0 * 0 = 1$
3. If any row or column has only 0, then the matrix determinant is equal to 0
   $\begin{vmatrix} 1 & 0 \\ 2 & 0 \end{vmatrix} = \begin{vmatrix} 1 & 2 \\ 0 & 0 \end{vmatrix} = 1 * 0 - 2 * 0 = 0$
4. Transpose doesn't affect matrix determinant
   $\begin{vmatrix} 1 & 2 \\ 3 & 4 \end{vmatrix} = \begin{vmatrix} 1 & 3 \\ 2 & 4 \end{vmatrix}^T = 4 - 6 = -2$
5. Multiplying any whole row or column multiplies the determinant
   $k = 5$, $\begin{vmatrix} 1k & 2k \\ 3 & 4 \end{vmatrix} = \begin{vmatrix} 1 & 2 \\ 3k & 4k \end{vmatrix} = 20 - 30 = -10 = -2k$
6. A single unique exchange of any whole row or column negates the determinant
   $\begin{vmatrix} 1 & 2 \\ 3 & 4 \end{vmatrix}$, $\begin{vmatrix} 2 & 1 \\ 4 & 3 \end{vmatrix} = 6 - 4 = 2$, but another exchange changes value $\begin{vmatrix} 4 & 1 \\ 2 & 3 \end{vmatrix} = 12 - 2 = 10$
7. Adding a multiple of one row or column doesn't change the value of the determinant
   $\begin{vmatrix} 1 & 2 \\ 3 & 4 \end{vmatrix} = \begin{vmatrix} 1 + 3 & 2 + 4 \\ 3 & 4 \end{vmatrix} = 4 * 4 - (6 * 3) = 16 - 18 = -2$

### Matrix inverse

The matrix inverse of a matrix is a matrix that undoes the linear transformation performed by the matrix. Not all matrices have an inverse; those that do have a <u>nonzero determinant</u> and are called **nonsingular**, whereas matrices without an inverse are called **singular**.

There are multiple ways to compute a matrix inverse; the simplest is via the **classical adjoint** matrix
**Classical adjoint (adjugate) matrix**: a transposed matrix formed from cofactors. Denoted as $adj\ M$
Example: $adj\ M=\begin{vmatrix} 1 & 2 \\ 3 & 4 \end{vmatrix} = \begin{vmatrix} C^{11} & C^{12} \\ C^{21} & C^{22} \end{vmatrix}^T = \begin{vmatrix} 3 & 2 \\ 4 & 1 \end{vmatrix}^T = \begin{vmatrix} 3 & 4 \\ 2 & 1 \end{vmatrix}$

The adjoint matrix is then divided by the determinant of the original matrix, giving us the inverse of the matrix. The formula is $M^{-1} = \dfrac{adj\ M}{|M|}$, by which we can conclude that matrices with a zero determinant don't have an inverse since division by zero is undefined.
Example: $|M| = 1 * 4 - 2 * 3 = -2$, $\begin{vmatrix} 3 & 4 \\ 2 & 1 \end{vmatrix} / -2 = \begin{vmatrix} -3/2 & -2 \\ -1 & -1/2 \end{vmatrix}$

Matrix inverse properties:
1. The inverse of a matrix product is equal to the product of the matrix inverses in reverse order $(AB)^{-1} = B^{-1}A^{-1}$
2. The inverse of an identity matrix is the identity matrix itself $I^-1 = I$ (there are other matrices that are inverses of themselves)


## Classes of transformations:

1. **Linear transformations**:  Transformations where
	1. $F(a+b)=F(a) + F(b)$
	2. $kF(a) = F(ka)$
	3. $F (0) = a$ and $a$ = 0
	4. Is a transformation accomplished with matrix multiplication $F(a + b) = (a+b)M = aM + bM$, where $M$ is a square matrix
	if some conditions are not met, then it's not a linear transformation.
2. **Affine transformations**: a linear transformation that is followed by translation. Every transformation that has the form $v' = vM + b$ is an affine transformation. All linear transformations are affine transformations because $b$ could be equal to zero, but if $b$ is a nonzero vector, then it's an affine transformation and not linear
3. **Invertible transformation**: a transformation for which there exists a matrix that undoes the transformation (matrix inverse) $F^{-1}(F(a)) = a$. All transformations except projection are invertible 
4. **Angle preserving transformations**: transformations where the angles between two vectors (points) are preserved. *Translation*, *uniform scale*, and *rotation* are angle preserving. <u>Reflection is not angle preserving</u>, since the sign could be inverted
5. **Orthogonal transformations**: transformations whose rows form an orthogonal basis. Each row is a basis vector, which is perpendicular to every other vector and has unit length. This transformation preserves area and volume and preserves the magnitude of the angle (but not strictly the sign). *Reflection*, *translation*, and *rotation* are orthogonal transformations.  
6. **Rigid body transformations**: transformations that preserve angles and change orientation, but not shape (the most restrictive class). *Translation* and *rotation* are the only transformations that are rigid body transformations. Rigid body transformations are also known as proper transformations. 
## Linear transformations
Linear transformations are transformations that transform a vector using matrices. Linear transformations are based on linear combinations (since a vector can be represented as a linear combination)
### Basic transformations
This section describes basic transformations from the origin
#### Rotation 2D
Rotation in 2D is rotation around a point
Matrices for rotation are below:

**counter-clockwise (standard 2D) rotation:**
					   $x$        $y$
for column vectors $(M)$ $\begin{bmatrix} cos(\theta) & -sin(\theta) \\ sin(\theta) & cos(\theta)   \end{bmatrix}$, for row vectors ($M^T$) $\begin{array}{c c} x \\ y \end{array} \begin{bmatrix} cos(\theta) & sin(\theta) \\ -sin(\theta) & cos(\theta)   \end{bmatrix}$ 
**clockwise rotation**:
					    $x$      $y$
for column vectors $(M)$ $\begin{bmatrix} cos(\theta) & sin(\theta) \\ -sin(\theta) & cos(\theta)   \end{bmatrix}$, for row vectors ($M^T$) $\begin{array}{c c} x \\ y \end{array} \begin{bmatrix} cos(\theta) & -sin(\theta) \\ sin(\theta) & cos(\theta)   \end{bmatrix}$ 

The counterclockwise rotation matrix is derived from the sum of an angle with a hypotenuse of length 1 (and similarly with the angle difference for the clockwise matrix)
1. basis $p$: $cos(\alpha + \beta) = cos(\alpha)cos(\beta) - sin(\alpha)sin(\beta)$, $sin(\alpha)$ = y (because $sin(\alpha) = opposite/hypotenuse$ and hypotenuse is 1, so $sin(\alpha) = opposite$) and $cos(\alpha) = x$, so $cos(\alpha + \beta) = x*cos(\beta) - y*sin(\beta) = \begin{bmatrix}cos(\theta) & -sin(\theta)\end{bmatrix}$
2. basis $q$: $sin(\alpha + \beta) = sin(\alpha)cos(\beta) + sin(\beta)cos(\alpha)$, $sin(\alpha)$ = y (because $sin(\alpha) = opposite/hypotenuse$ and hypotenuse is 1, so $sin(\alpha) = opposite$) and $cos(\alpha) = x$, $sin(\alpha + \beta) = y*cos(\beta) + x*sin(\beta) =\begin{bmatrix}sin(\theta) & cos(\theta)\end{bmatrix}$
#### Rotation 3D
Rotation in 3D is not around a point but is [[Coordinate spaces#^81e292|around a cardinal axis]] 
1. **Around Y axis**: 
   					   $x$     $y$    $z$
	for column vectors $\begin{bmatrix} cos(\theta) & 0 & sin(\theta) \\ 0 & 1 & 0 \\ -sin(\theta) & 0 & cos(\theta)   \end{bmatrix}$ for row vectors $\begin{array}{c c c} x \\ y \\ z \end{array}\begin{bmatrix} cos(\theta) & 0 & -sin(\theta) \\ 0 & 1 & 0 \\ sin(\theta) & 0 & cos(\theta)   \end{bmatrix}$
2. **Around Z axis**:
   					   $x$     $y$    $z$
	for column vectors $\begin{bmatrix} cos(\theta) & -sin(\theta) & 0 \\ sin(\theta) & cos(\theta) & 0 \\ 0 & 0 & 1  \end{bmatrix}$ for row vectors $\begin{array}{c c c} x \\ y \\ z \end{array}\begin{bmatrix} cos(\theta) & sin(\theta) & 0 \\ -sin(\theta) & cos(\theta) & 0 \\ 0 & 0 & 1  \end{bmatrix}$ 
3. **Around X axis**:
   					   $x$     $y$    $z$
   for column vectors $\begin{bmatrix} 1 & 0 & 0 \\ 0 & cos(\theta) & -sin(\theta)  \\ 0 & sin(\theta) & cos(\theta)  \end{bmatrix}$ for row vectors $\begin{array}{c c c} x \\ y \\ z \end{array}\begin{bmatrix} 1 & 0 & 0 \\ 0 & cos(\theta) & sin(\theta)  \\ 0 & -sin(\theta) & cos(\theta)  \end{bmatrix}$
The same matrices work for right-handed and left-handed systems
These matrices are derived in the same way as in 2D (each rotation is performed on a 2D plane)

##### Rotation around arbitrary axis 
It's also possible to rotate around an arbitrary axis (that passes through the origin) provided by vector $\hat n$, but it is less common and harder to derive. The principle is to determine a 2D plane and rotate the vector in this 2D plane. The derivation can be found [[Derivation of 3D rotation matrix around arbitrary axis | here]]. 

For column vectors:
$S = \begin{bmatrix}n^2_x (1 - cos(\theta))  + cos(\theta) & n_yn_x (1 - cos(\theta)) - n_z sin(\theta) & n_zn_x (1 + cos(\theta)) + n_y sin(\theta) \\ n_xn_y(1 - cos(\theta)) + sin(\theta)n_z & n^2_y(1-cos(\theta)) + cos(\theta) & n_yn_z(1 - cos(\theta)) - sin(\theta)n_x \\ n_xn_z(1 - cos(\theta)) - sin(\theta)n_y & n_yn_z(1-cos(\theta)) + sin(\theta)n_x & n_z^2(1 - cos(\theta)) + cos(\theta) \end{bmatrix}$

For row vectors:
$S^T = \begin{bmatrix}n^2_x (1 - cos(\theta))  + cos(\theta) & n_xn_y(1 - cos(\theta)) + sin(\theta)n_z & n_xn_z(1 - cos(\theta)) - sin(\theta)n_y \\ n_yn_x (1 - cos(\theta)) - n_z sin(\theta) & n^2_y(1-cos(\theta)) + cos(\theta) & n_yn_z(1-cos(\theta)) + sin(\theta)n_x \\ n_zn_x (1 + cos(\theta)) + n_y sin(\theta) & n_yn_z(1 - cos(\theta)) - sin(\theta)n_x & n_z^2(1 - cos(\theta)) + cos(\theta) \end{bmatrix}$

### Scale 

**Uniform scale**: all vector components are multiplied by a single value. Angles and ratios remain the same. A uniform scale matrix is equivalent to multiplying a vector by a scalar $k$. The area will be increased by $k^2$ and the area by $k^3$
$S_u = \begin{bmatrix} k & 0 & 0 \\ 0 & k & 0 \\ 0 & 0 & k \end{bmatrix}$, for 2D $S_u = \begin{bmatrix} k & 0 \\ 0 & k \\\end{bmatrix}$
**Nonuniform scale**: vector components are multiplied by different coefficients. Angles are not preserved. $S_{nu} = \begin{bmatrix} k_x & 0 & 0 \\ 0 & k_y & 0 \\ 0 & 0 & k_z \end{bmatrix}$, for 2D $S_{nu} = \begin{bmatrix} k_x & 0 \\ 0 & k_y \end{bmatrix}$
if $|k|$ is > 1, then the component is extended
if $|k|$ < 1, then the component is shrunk
if k is zero, then it is[[Linear algebra#^ca4f5b | orthographic projection]]
if k < 0, then zero, then it's [[Linear algebra#^cd089e | reflection]]

##### Scaling along arbitrary axis

Scaling along an arbitrary axis $\hat n$ (that passes through the origin) with scale factor $k$ is similar to rotation around an arbitrary axis $\hat n$. The matrix can be applied to row and column vectors, for 2D and 3D

**3D scale matrix** (Can be applied for row and column vectors):
	$S_{\hat n} = \begin{bmatrix} 1 + n_x^2 (k - 1) & n_xn_y (k - 1) & n_xn_z (k - 1) \\ n_xn_y (k - 1) & 1+ n_y^2 (k - 1) & n_yn_z (k - 1) \\ n_xn_z (k - 1) & n_yn_z * (k - 1) & 1 + n_z^2 * (k - 1)\end{bmatrix}$
	
**2D scale matrix** (Can be applied for row and column vectors):
	$S_{\hat n} = \begin{bmatrix} 1 + n_x^2 (k - 1) & n_xn_y (k - 1) \\ n_xn_y (k - 1) & 1+ n_y^2 (k - 1)\end{bmatrix}$

Computation is below
![[Pasted image 20260808122450.png|610]]	
We have to find vector $v'$, which is scaled along the axis
1. $v' = v'_{perpendicular} + v'_{parallel}$, we just have to compute $v'_{perpendicular}$ and $v'_{parallel}$
2. $v_{parallel}$ is on the same axis as $\hat n$; we can compute it by the dot product. 
3. We can easily compute $v'_{parallel}$ because we are just changing the size of $v_{parallel}$ by $k$ based on the previous relationship with $\hat n$
4. Since we are scaling <u>along</u> an arbitrary axis, $v_{perpendicular}$ will not be scaled because it's not on the same axis; thus, $v_{perpendicular} = v'_{perpendicular}$, and $v_{perpendicular} = v - v_{parallel}$ (we need this transformation because we have to somehow compute $v_{perpendicular}$)
5. The final formula is $v' = v - v_{parallel} + v'_{parallel} = v - (\hat n * v)\hat n + k(\hat n * v)\hat n$
   $= v + (\hat n * v)\hat n  * (k - 1)$

We can transform it to matrix (3D example):
1. Compute $(\hat n * v)$
$(\hat n * v) = (n_xv_x + n_yv_y + n_zv_z)$
$(\hat n * v)n_x = n_x^2v_x + n_xn_yv_y + n_xn_zv_z$
$(\hat n * v)n_y = n_xn_yv_x + n_y^2v_y + n_yn_zv_z$
$(\hat n * v)n_z = n_xn_zv_x + n_yn_zv_y + n_z^2v_z$
2. Compute $p$, $q$, $r$
$p = v_x + (\hat n * v)\hat n_x  * (k - 1) = v_x * (1 + n_x^2 * (k - 1)) + v_y*(n_xn_y * (k - 1)) + v_z * (n_xn_z * (k - 1))$
$q = v_y + (\hat n * v)\hat n_y  * (k - 1) = v_x * (n_xn_y * (k - 1)) + v_y*(1+ n_y^2 * (k - 1)) + v_z * (n_yn_z * (k - 1))$
$r = v_z + (\hat n * v)\hat n_z  * (k - 1) = v_x * (n_xn_z * (k - 1)) + v_y*(n_yn_z * (k - 1)) + v_z * (1 + n_z^2 * (k - 1))$

### Orthographic projection ^ca4f5b

Projection is a dimension-reducing operation.
Orthographic projection is one of the types of projection, which is also called parallel projection because lines from points are parallel to their projected counterparts (plane)
#### Projection along axis (2D) or plane (3D)
A simple case of orthographic projection where one of the $k$ values for nonuniform scaling is 0 (discarded); thus, projection is performed to a perpendicular plane (3D) or perpendicular axis (2D).
3D:
	$P_{xy} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0  \end{bmatrix}$ $P_{xz} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1  \end{bmatrix}$ $P_{yz} = \begin{bmatrix} 0 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1  \end{bmatrix}$
2D:
	$P_{x} = \begin{bmatrix} 1 & 0  \\ 0 & 0  \end{bmatrix}$ $P_{y} = \begin{bmatrix} 0 & 0  \\ 0 & 1  \end{bmatrix}$

Projection of Z+ (Z+ is the top in Blender) to the XY plane 
![[Pasted image 20260808125017.png|290]]
How it really looks
![[Pasted image 20260808125040.png|258]]
#### Projection along arbitrary line (2D) or plane (3D)

Derived from the matrix for scaling along an arbitrary axis, where k is replaced with 0 $P_{\hat n} = S(0, \hat n)$. However, the plane/line defined by vector $\hat n$ is perpendicular to $\hat n$ ($\hat n$ can be imagined as the axis from which we are looking at the object). The resulting plane passes through the origin

**3D orthographic projection matrix** (Can be applied for row and column vectors):
	$P_{\hat n} = \begin{bmatrix} 1 - n_x^2 & -n_xn_y & -n_xn_z \\ -n_xn_y & 1- n_y^2 & -n_yn_z \\ -n_xn_z & -n_yn_z & 1 - n_z^2 \end{bmatrix}$
	
**2D orthographic projection matrix** (Can be applied for row and column vectors):
	$P_{\hat n} = \begin{bmatrix} 1 - n_x^2 & -n_xn_y \\ -n_xn_y & 1- n_y^2\end{bmatrix}$
	
![[Pasted image 20260808172406.png|502]]

### Reflection ^cd089e

Reflection is mirroring (flipping) about a line (2D) or plane (3D)

#### Reflection around perpendicular axis
Reflection around an axis is replacing one of the $k$ values of the scaling matrix (that scales around a cardinal axis) with $-1$. Reflection will be performed about the perpendicular axis/axes to what we are going to negate

**3D reflection matrices:
	$R_{yz} = \begin{bmatrix} -1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$ $R_{xz} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$ $R_{xy} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & -1 \end{bmatrix}$
2D reflection matrices:
	$R_{y} = \begin{bmatrix} -1 & 0 \\ 0 & 1  \end{bmatrix}$ $R_{x} = \begin{bmatrix} 1 & 0  \\ 0 & -1 \end{bmatrix}$

Reflection around an arbitrary axis can also be derived from the scaling matrix $R_{\hat n} = S(-1, \hat n)$

**3D reflection matrix:
	$R_{\hat n} = \begin{bmatrix} 1 - 2n_x^2 & -2n_xn_y & -2n_xn_z \\ -2n_xn_y & 1 - 2n_y^2 & -2n_yn_z \\ -2n_xn_z & -2n_yn_z & 1 -2n_z^2  \end{bmatrix}$
	
**2D reflection matrix:
	$R_{\hat n} = \begin{bmatrix} 1 - 2n_x^2 & -2n_xn_y \\ -2n_xn_y & 1 - 2n_y^2 \end{bmatrix}$
	
![[Pasted image 20260809141518.png|387]]
#### Reflection around parallel axis
To rotate around a parallel axis, we have to negate the reflection matrix

**3D reflection matrix:
	$R_{\hat n} = \begin{bmatrix} 2n_x^2 - 1 & 2n_xn_y & 2n_xn_z \\ 2n_xn_y & 2n_y^2 - 1 & 2n_yn_z \\ 2n_xn_z & 2n_yn_z & 2n_z^2 -1  \end{bmatrix}$

**2D reflection matrix**:
$R_{\hat n} = \begin{bmatrix} 2n_x^2 - 1 & 2n_xn_y \\ 2n_xn_y & 2n_y^2 - 1 \end{bmatrix}$

![[Pasted image 20260809141959.png|389]]

### Shearing
Shearing is a rarely used transformation, also known as a **skew transform**, that skews (creates asymmetry in) an object, stretching it nonuniformly while preserving area and volume. It works by adding another vector component with a skew coefficient $s$ ($v_i = v_i + sv_j + ...$). For example, $x' = x + sy$, and $x$ is sheared by $sy$. 

$x' = x + 1y$
![[Pasted image 20260809152715.png|283]]

Matrices for shearing are derived from $v_i = v_i + sv_j+...$; the letter below $H$ denotes which coordinate/s are being sheared. In 3D, it's possible to skew multiple coordinates by a single coordinate, having a coefficient for each coordinate

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
