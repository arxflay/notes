Coordinate system (space) is a system how to represent points in some space. Each coordinate system has defined graph origin and graph axis. **Graph origin** is a center of the graph, which could be (0,0) but it's up to us where will be center of the graph. **Graph axis** are coordinate lines which are perpendicular to each other. We can orient them however we want (even flip them or rotate them by some degree). Coordinates  measures displacement from origin if[[Math#^bd3fba | basis]] vectors are orthogonal and if they are not, coordinates are just coefficients of linear combination
## Cartesian 3D
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

Rotation direction is different for each hand. To determine direction, point thumb axis you want to rotate from. Curled fingers will be the direction. For left handed, positive rotation is clockwise and for right is counterclockwise to positive end  ^81e292

![[Pasted image 20260725143457.png|420]]
There are 24 positions for each hand, in total 48 possible combinations (imagine coordinates as cube, cube has in total 6 sides, we can spin each side 4 times, so $6*4=24$)

3D object can be represented as multiple planes. Plane is 2D surface, but in context of 3D, plane is a slice of 3D space. Typical planes are XY, XZ and YZ
![[Pasted image 20260624184915.png|418]]
but slice of 3D space (plane) is not required to be flat
![[Pasted image 20260807164358.png|398]]
Typical plane orientations for rotation (because they are used in transformations)
* xy - x adjacent and y is opposite 
* xz - z is adjacent and x is opposite 
* yz - y is adjacent and z is opposite
reason: 
1. rotation should remain clockwise or counter-counter clockwise depending on handiness and angle (positive/negative rotation)
2. rotation should come from horizontal axis

Example for xz (left handed):
![[Pasted image 20260804194134.png|321]] 
 but if we swap
 ![[Pasted image 20260804195245.png|182]]
then rotation comes from vertical axis and it's rotation not from 0 but from $1/2\pi$
## Different coordinate spaces
Different coordinate spaces can be seen as different uses in different contexts. For example we have a table with phone on it and could ask a question "where exactly is the phone?". In world space, the answer will be GPS coordinates, but in space relative to table, the answer could be in the center of table. 

Important coordinate spaces:
1. World (global, universal) space - Abstract top level global space - in simple words, it's a space where all objects are placed (translated), but meaning of world space depends on context (usually tho is defined just as that). World space can be also described as parent space, for example phone is on the table and table is in the room, thus parent space of phone is relative to table and parent space of table is relative to room, thus **spaces can be nested.** In world space, we use directions **north, south, east and west** relative to world and we can answer to questions that asks for this directions.
2. Object (model, body) space - Space, unique for object. Having object that is composed from multiple objects, each object from which object is composed has it's own object space. In object space, we use directions **left, right, top, bottom, forward, back** and we can answer to questions that asks for this directions.
3. Upright space - non-standard intermediate space between object space and world space, where object is rotated, but origin is same as in object space and axis are parallel to world space axis. Can be imagined as if object axis were rotated (if linear rotation is applied) and we are converting points to standard basis ![[Pasted image 20260730194203.png|392]]
4. Camera space - object space, that defines viewpoint from which world is seen. In left coordinate space, camera at origin usually points to Z+ forward, X+ to right and Y+ to top, in right handed Z- points forward, X+ to right and Y+ to top.
   blender (right coordinate system). The whole world space is translated and rotated to camera origin. Camera space however is 3D and to visualize content on screen, viewpoint must be transformed to 2D screen space by projection
   ![[Pasted image 20260728190918.png|251]]

When object is home position (not affected by transformations), **then world space, upright space and object is same**.

Transformations can be performed on object or on object space axis.
1. Active transformation - Object is rotated (upright space) and then translated (world space space)
2. Passive transformation - Object space axis are rotated (upright space) and then origin is translated (world space)
Performing certain active/passive transformation is equivalent to performing opposite transformation passive/active transformation

### Conversion between spaces

We can convert **object space** to **upright** by **rotation** and **upright** space to world space by **translation**. World space can be converted to camera space by negative **translation** to  camera origin and opposite **rotation** 

> [!note] 
> Rotation must be from origin otherwise it will be affine transformation, which will perform translation to origin, rotation and translation back
##### Conversion from object space to upright
$u = \sum{a_i\ \vec{b_i}}$ , where $a_i$ is object coordinate component and $\vec{b_i}$ is basis vector, example
$u = a_x * p + a_y * q$, or $u_x = a_x*p_x + a_y * q_x$ and $u_y = a_x*p_y + a_y * q_y$ (because it's a linear combination). 
##### Conversion from upright space to world space:
$w = o + u$, where $o$ is origin of world space and $u$ is coordinates in upright space
##### Conversion from world space to upright space:
$u = w - o$
##### Conversion from upright space to object space (using dot product):
$a_n = u\cdot \vec{b_n}$, where u is upright space, where $a_n$ is object coordinate component and $\vec{b_n}$ is unit basis vector (otherwise we have divide by length of $b_n$), but these works only if axis are orthogonal, otherwise component. example $a_x = u\cdot p$, $a_y = u \cdot q$, 