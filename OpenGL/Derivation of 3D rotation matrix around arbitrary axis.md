Rotation about arbitrary axis involves getting 2D plane from vector $j$ and axis $\hat n$, around which will be performed rotation. Remember, **plane is just a slice of 3D space**.

To determine vector $j'$, we need $j'_{perpendicular}$ and $j'_{parallel}$. 
1. If $j_{parallel}$ is parallel to vector $\hat n$, then rotation will not change that component (since it's rotation around $\hat n$). That mean's, that $j_{paralell}$ is equal to $j'_{paralell}$. $j'_{parallel}$ can be computed using dot product $(\hat n*j)\hat n$. 
2. We need to compute $j_{perpendicular}$ which can be computed as $j - j_{parallel}$. 
3. Using vector $j_{perpendicular}$, we compute vector $w$ which is vector $j_{perpendicular}$ rotated by $90\textdegree$ around $\hat n$ (perpendicular to both $\hat n$ and $j_{perpendicular}$) We can use cross product to compute $w$. 
4. Pair $j_{perpendicular}$ and $w$ will act like two axis (they are forming 2D plane), where $w$ is opposite and $j_{perpendicular}$ is adjacent. Now we can compute rotated vector $j'_{pependicular}$, via $cos(\theta)*j_{perpendicular} + sin(\theta) * w$
5. With this, we can compute $j' = j'_{parallel} + j'_{perpendicular}$

![[Pasted image 20260807175715.png|418]]

Now all of this must be converted to matrix, which can be applied to any vector
1. $j' = j'_{parallel} + j'_{perpendicular}$
2. $j'_{parallel} = j_{parallel} = (\hat n*j)\hat n$
3. $j_{perpendicular}$ = $j - j_{parallel} = j - (\hat n*j)\hat n$
4. $w = \hat n \times j_{perpendicular} = \hat n \times (j-j_{parallel}) = \hat n  \times j$ (since cross product of parallel vector is equal to 0)
5. $j_{perpendicular}' = cos(\theta)*j_{perpendicular} + sin(\theta) * w$
   $j'_{perpendicular} = cos(\theta) * (j - (\hat n * j)\hat n) + sin(\theta) * (\hat n \times j)$
6. $j' = j'_{parallel} + j'_{perpendicular} =  (\hat n * j)\hat n +cos(\theta) * (j - (\hat n * j)\hat n) + sin(\theta) *(\hat n \times j)$
7. compute $(\hat n * j)$
   $n_x * j_x + n_y * j_y + n_z * j_z$
8. compute $v_{parallel} = (\hat n*j)\hat n$ for each component
	$\hat n_x(\hat n * j) = n_x*(n_x * j_x + n_y * j_y + n_z * j_z) = n_x^2*j_x + n_y*n_x*j_y + n_z*n_x*j_z$
	$\hat n_y(\hat n * j) = n_y * (n_x * j_x + n_y * j_y + n_z * j_z) = n_x*n_y*j_x + n_y^2*j_y + n_z*n_y*j_z$
	$\hat n_z(\hat n * j) = n_z * (n_x * j_x + n_y * j_y + n_z * j_z) = n_x*n_z*j_x + n_y*n_z*j_y + n_z^2*j_z$
9. compute $j - (\hat n * j)\hat n$ for each component
   $j_x - \hat n_x(\hat n * j) = j_x - n_x^2*j_x - n_y*n_x*j_y - n_z*n_x*j_z$
   $j_y - \hat n_y(\hat n * j) = j_y - n_x*n_y*j_x - n_y^2*j_y - n_z*n_y*j_z$
   $j_z - \hat n_z(\hat n * j) = j_z - n_x*n_z*j_x - n_y*n_z*j_y - n_z^2*j_z$
10. compute $\hat n \times j$
    $(\hat n \times j)_x = n_y * j_z - n_z * j_y$
    $(\hat n \times j)_y = n_z * j_x - n_x * j_z$
    $(\hat n \times j)_z = n_x * j_y - n_y * j_x$
11. compute p,q,r (x,y,z) components
**basis p**
$p = ((\hat n * j)\hat n_x) +cos(\theta) * (j_x - (\hat n * j)\hat n_x) + sin(\theta) *(\hat n \times j)_x$
$p = n_x^2*j_x + n_y*n_x*j_y + n_z*n_x*j_z +cos(\theta) * (j_x - n_x^2*j_x - n_y*n_x*j_y - n_z*n_x*j_z) +$ $sin(\theta) *(n_y * j_z - n_z * j_y)$
$p = n_x^2*j_x + n_y*n_x*j_y + n_z*n_x*j_z +cos(\theta) * j_x - cos(\theta) * n_x^2*j_x - cos(\theta) * n_y*n_x*j_y$ $-cos(\theta) * n_z*n_x*j_z + sin(\theta) *n_y * j_z - sin(\theta) * n_z * j_y$
$p = j_x * (n^2_x + cos(\theta) - cos(\theta)n^2_x)$
$+\ j_y * (n_y*n_x - cos(\theta)*n_y*n_x - sin(\theta)*n_z)$
$+\ j_z * (n_z*n_x - cos(\theta) * n_z * n_x + sin(\theta) * n_y)$
$p = j_x * (n^2_x * (1 - cos(\theta))  + cos(\theta)))$
$+\ j_y * (n_yn_x * (1 - cos(\theta)) - n_z * sin(\theta))$
$+\ j_z * (n_zn_x * (1 - cos(\theta)) + n_y * sin(\theta))$

$p = \begin{bmatrix}n^2_x (1 - cos(\theta))  + cos(\theta) & n_yn_x (1 - cos(\theta)) - n_z sin(\theta) & n_zn_x (1 + cos(\theta)) + n_y sin(\theta)\end{bmatrix}$

**basis q**
$q = ((\hat n * j)\hat n_y) +cos(\theta) * (j_y - (\hat n * j)\hat n_y) + sin(\theta) *(\hat n \times j)_y$
$q = n_x*n_y*j_x + n_y^2*j_y + n_z*n_y*j_z +cos(\theta) * (j_y - n_x*n_y*j_x + n_y^2*j_y + n_z*n_y*j_z) +$ $sin(\theta) *(n_z * j_x - n_x * j_z)$
$q = n_x*n_y*j_x + n_y^2*j_y + n_z*n_y*j_z +cos(\theta) * j_y - cos(\theta) * n_x*n_y*j_x - cos(\theta) * n_y^2j_y$ 
 $-cos(\theta) * n_z*n_y*j_z + sin(\theta) *n_z * j_x - sin(\theta) * n_x * j_z$
$q = j_x * (n_xn_y -cos(\theta) * n_xn_y + sin(\theta) * n_z)$
 $+\ j_y * (n_y^2+cos(\theta)-cos(\theta)*n^2_y)$
 $+\ j_z * (n_z*n_y - cos(\theta) * n_z * n_y - sin(\theta) * n_x)$
$q = j_x * (n_xn_y*(1 - cos(\theta)) + sin(\theta)* n_z)$
 $+\ j_y * (n^2_y*(1-cos(\theta) + cos(\theta)))$
 $+\ j_z * (n_yn_z*(1 - cos(\theta)) - sin(\theta)*n_x)$
 
$q = \begin{bmatrix} n_xn_y(1 - cos(\theta)) + sin(\theta)n_z & n^2_y(1-cos(\theta)) + cos(\theta) & n_yn_z(1 - cos(\theta)) - sin(\theta)n_x \end{bmatrix}$

**basis r**
$r = ((\hat n * j)\hat n_z) +cos(\theta) * (j_z - (\hat n * j)\hat n_z) + sin(\theta) *(\hat n \times j)_z$
$r = n_x*n_z*j_x + n_y*n_z*j_y + n_z^2*j_z +cos(\theta) * (j_z - n_x*n_z*j_x - n_y*n_z*j_y - n_z^2*j_z) +$ $sin(\theta) *(n_x * j_y - n_y * j_x)$
$r = n_x*n_z*j_x + n_y*n_z*j_y + n_z^2*j_z +cos(\theta) * j_z$
$- cos(\theta)*n_x*n_z*j_x - cos(\theta) * n_y*n_z*j_y - cos(\theta) *n^2_z*j_z) + sin(\theta) * n_x*j_y - sin(\theta)*n_y*j_x$
$r = j_x * (n_x*n_z - cos(\theta)*n_x*n_z - sin(\theta)*n_y)$
 $+\ j_y * (n_y*n_z - cos(\theta)*n_y*n_z + sin(\theta)*n_x)$
 $+\ j_z * (n^2_z + cos(\theta) - cos(\theta)*n_z^2)$
$r = j_x * (n_xn_z(1 - cos(\theta)) - sin(\theta)n_y)$
 $+\ j_y * (n_yn_z*(1-cos(\theta)) + sin(\theta)n_x)$
 $+\ j_z * (n_z^2*(1 - cos(\theta)) + cos(\theta))$
$r = \begin{bmatrix} n_xn_z(1 - cos(\theta)) - sin(\theta)n_y & n_yn_z(1-cos(\theta)) + sin(\theta)n_x & n_z^2(1 - cos(\theta)) + cos(\theta) \end{bmatrix}$

12. combine
$\begin{bmatrix}n^2_x (1 - cos(\theta))  + cos(\theta) & n_yn_x (1 - cos(\theta)) - n_z sin(\theta) & n_zn_x (1 + cos(\theta)) + n_y sin(\theta) \\ n_xn_y(1 - cos(\theta)) + sin(\theta)n_z & n^2_y(1-cos(\theta)) + cos(\theta) & n_yn_z(1 - cos(\theta)) - sin(\theta)n_x \\ n_xn_z(1 - cos(\theta)) - sin(\theta)n_y & n_yn_z(1-cos(\theta)) + sin(\theta)n_x & n_z^2(1 - cos(\theta)) + cos(\theta) \end{bmatrix}$