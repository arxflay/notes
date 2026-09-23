A coordinate system (space) is a system for representing points in some space. Each coordinate system has a defined graph origin and graph axes. **The graph origin** is the center of the graph, which could be (0,0), but it's up to us where the center of the graph will be. **Graph axes** are coordinate lines which are perpendicular to each other. We can orient them however we want (even flip them or rotate them by some degree). Coordinates measure displacement from the origin if [[Math#^bd3fba | basis]] vectors are orthogonal, and if they are not, coordinates are just coefficients of a linear combination
## Cartesian 3D
The naming of axes and their directions is not standardized in 3D. There are exactly two coordinate systems, left-handed and right-handed. They are named this way because they can be represented by the fingers of the hand. 

Left handed: 
* x+ - right
* y+ - top
* z+ - forward

Right handed: 
* x+ - left
* y+ - right
* z+ - forward

For consistency with 2D, x+ and z+ are usually inverted in a right-handed system, so x+ points to the right and z+ points backward. Swapping (negating) two axes will not change handedness (it's like rotating the original coordinate system by $180\textdegree$), but swapping the direction of a single axis will change handedness. 

![[Pasted image 20260624184944.png]]

The rotation direction is different for each hand. To determine the direction, point your thumb along the axis you want to rotate from. The curled fingers will show the direction. For left-handed, positive rotation is clockwise, and for right-handed, it is counterclockwise to the positive end  ^81e292

![[Pasted image 20260725143457.png|420]]
There are 24 positions for each hand, for a total of 48 possible combinations (imagine the coordinates as a cube; the cube has 6 sides in total, and we can spin each side 4 times, so $6*4=24$)

A 3D object can be represented as multiple planes. A plane is a 2D surface, but in the context of 3D, a plane is a slice of 3D space. Typical planes are XY, XZ, and YZ
![[Pasted image 20260624184915.png|418]]
but a slice of 3D space (a plane) is not required to be flat
![[Pasted image 20260807164358.png|398]]
Typical plane orientations for rotation (because they are used in transformations)
* xy - x adjacent and y is opposite 
* xz - z is adjacent and x is opposite 
* yz - y is adjacent and z is opposite
reason: 
1. rotation should remain clockwise or counterclockwise depending on handedness and angle (positive/negative rotation)
2. rotation should come from the horizontal axis

Example for xz (left handed):
![[Pasted image 20260804194134.png|321]] 
 but if we swap
 ![[Pasted image 20260804195245.png|182]]
then the rotation comes from the vertical axis, and its rotation is not from 0 but from $1/2\pi$
## Different coordinate spaces
Different coordinate spaces can be seen as different uses in different contexts. For example, we have a table with a phone on it and could ask the question, "Where exactly is the phone?" In world space, the answer will be GPS coordinates, but in space relative to the table, the answer could be in the center of the table. 

Important coordinate spaces:
1. World (global, universal) space - Abstract top-level global space - in simple words, it's a space where all objects are placed (translated), but the meaning of world space depends on the context (usually, though, it is defined just as that). World space can also be described as parent space; for example, a phone is on the table and the table is in the room, thus the parent space of the phone is relative to the table and the parent space of the table is relative to the room, so **spaces can be nested.** In world space, we use directions **north, south, east, and west** relative to the world, and we can answer questions that ask for these directions.
2. Object (model, body) space - Space unique to an object. Having an object that is composed of multiple objects, each object from which the object is composed has its own object space. In object space, we use directions **left, right, top, bottom, forward, back** and we can answer questions that ask for these directions.
3. Upright space - nonstandard intermediate space between object space and world space, where the object is rotated, but the origin is the same as in object space and the axes are parallel to the world space axes. It can be imagined as if the object axes were rotated (if linear rotation is applied) and we are converting points to the standard basis ![[Pasted image 20260730194203.png|392]]
4. Camera space - object space that defines the viewpoint from which the world is seen. In left coordinate space, the camera at the origin usually points to Z+ forward, X+ to the right, and Y+ to the top; in right-handed, Z- points forward, X+ to the right, and Y+ to the top.
   Blender (right coordinate system). The whole world space is translated and rotated to the camera origin. Camera space, however, is 3D, and to visualize content on the screen, the viewpoint must be transformed to 2D screen space by projection
   ![[Pasted image 20260728190918.png|251]]

When an object is in the home position (not affected by transformations), **then world space, upright space, and object space are the same**.

Transformations can be performed on an object or on the object space axes.
1. Active transformation - The object is rotated (upright space) and then translated (world space)
2. Passive transformation - The object space axes are rotated (upright space) and then the origin is translated (world space)
Performing a certain active/passive transformation is equivalent to performing the opposite passive/active transformation

### Conversion between spaces

We can convert **object space** to **upright** by **rotation** and **upright** space to world space by **translation**. World space can be converted to camera space by negative **translation** to the camera origin and opposite **rotation** 

> [!note] 
> Rotation must be from the origin; otherwise, it will be an affine transformation, which will perform translation to the origin, rotation, and translation back
##### Conversion from object space to upright
$u = \sum{a_i\ \vec{b_i}}$ , where $a_i$ is an object coordinate component and $\vec{b_i}$ is a basis vector, example
$u = a_x * p + a_y * q$, or $u_x = a_x*p_x + a_y * q_x$ and $u_y = a_x*p_y + a_y * q_y$ (because it's a linear combination). 
##### Conversion from upright space to world space:
$w = o + u$, where $o$ is the origin of world space and $u$ is the coordinates in upright space
##### Conversion from world space to upright space:
$u = w - o$
##### Conversion from upright space to object space (using dot product):
$a_n = u\cdot \vec{b_n}$, where u is upright space, where $a_n$ is an object coordinate component and $\vec{b_n}$ is a unit basis vector (otherwise, we have to divide by the length of $b_n$), but this works only if the axes are orthogonal; otherwise, the component. example: $a_x = u\cdot p$, $a_y = u \cdot q$, 
