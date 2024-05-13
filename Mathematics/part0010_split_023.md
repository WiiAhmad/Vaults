Chapter 10    

##[Vectors](part0010_split_023.md)

A vector ![\vec{v} \in \mathbb{R}^n](01554.jpeg) is an ![n](00054.jpeg)\-tuple of real numbers. For example, consider a vector that has three components:

![\vec{v} = (v_1,v_2,v_3) \; \in \; \mathbb{R}^3.](02902.jpeg)

To specify the vector ![\vec{v}](01520.jpeg), we specify the values for its three components ![v_1](01685.jpeg), ![v_2](01687.jpeg), and ![v_3](01689.jpeg).

A matrix ![A \in \mathbb{R}^{m\times n}](02903.jpeg) is a rectangular array of real numbers with ![m](00053.jpeg) rows and ![n](00054.jpeg) columns. A vector is a special type of matrix; you can think of the vector ![\vec{v} \in \mathbb{R}^n](01554.jpeg) as a ![1\times n](02904.jpeg) matrix. Because of this equivalence between vectors and matrices, in `SymPy` we use `Matrix` objects to represent vectors.

This is how we define vectors and compute their properties:

\>>> u = Matrix(\[4,5,6\])
>>> u
\[4, 5, 6\]                 # 3-vector
>>> u\[0\]                  # 0-based indexing for entries 
4
>>> u.norm()              # length of u 
sqrt(77)
>>> uhat = u/u.norm()     # unit vector in same dir as u
>>> uhat
\[4/sqrt(77), 5/sqrt(77), 6/sqrt(77)\]
>>> uhat.norm()
1

###[Dot product](part0010_split_023.md)

The dot product of the ![3](00106.jpeg)\-vectors ![\vec{u}](01562.jpeg) and ![\vec{v}](01520.jpeg) can be defined two ways:

![\vec{u}\cdot\vec{v}    =   \underbrace{u_xv_x+u_yv_y+u_zv_z}_{\textrm{algebraic def.}}   =   \underbrace{\|\vec{u}\|\|\vec{v}\|\cos(\varphi)}_{\textrm{geometric def.}}   \quad \in \mathbb{R},](02905.jpeg)

where ![\varphi](01727.jpeg) is the angle between the vectors ![\vec{u}](01562.jpeg) and ![\vec{v}](01520.jpeg). In `SymPy`,

\>>> u = Matrix(\[ 4,5,6\])
>>> v = Matrix(\[-1,1,2\])
>>> u.dot(v)
13

We can combine the algebraic and geometric formulas for the dot product to obtain the cosine of the angle between the vectors

![\cos(\varphi)         = \frac{ \vec{u}\cdot\vec{v} }{  \|\vec{u}\|\|\vec{v}\| }         = \frac{ u_xv_x+u_yv_y+u_zv_z  }{  \|\vec{u}\|\|\vec{v}\| },](02906.jpeg)

and use the `acos` function to find the angle measure:

\>>> acos(u.dot(v)/(u.norm()\*v.norm())).evalf()
0.921263115666387      # in radians  =  52.76 degrees

Just by looking at the coordinates of the vectors ![\vec{u}](01562.jpeg) and ![\vec{v}](01520.jpeg), it’s difficult to determine their relative direction. Thanks to the dot product, however, we know the angle between the vectors is ![52.76^\circ](02907.jpeg), which means they _kind of_ point in the same direction. Vectors that are at an angle ![\varphi=90^\circ](02908.jpeg) are called _orthogonal_, meaning at right angles with each other. The dot product between two vectors is negative when the angle between them is ![\varphi > 90^\circ](02909.jpeg).

The notion of the “angle between vectors” applies more generally to vectors with any number of dimensions. The dot product for ![n](00054.jpeg)\-dimensional vectors is ![\vec{u}\cdot\vec{v}=\sum_{i=1}^n u_iv_i](02910.jpeg). This means we can talk about “the angle between” 1000-dimensional vectors. That’s pretty crazy if you think about it—there is no way we could possibly “visualize” 1000-dimensional vectors, yet given two such vectors we can tell if they point mostly in the same direction, in perpendicular directions, or mostly in opposite directions.

The dot product is a commutative operation ![\vec{u}\cdot\vec{v} = \vec{v}\cdot\vec{u}](01741.jpeg):

\>>> u.dot(v) == v.dot(u)
True

###[Cross product](part0010_split_023.md)

The _cross product_, denoted ![\times](00746.jpeg), takes two vectors as inputs and produces a vector as output. The cross products of individual basis elements are defined as follows:

![\hat{\imath}\times\hat{\jmath} =\hat{k}, \qquad  \hat{\jmath}\times\hat{k} =\hat{\imath}, \qquad  \hat{k}\times \hat{\imath}= \hat{\jmath}.](01739.jpeg)

The cross product is defined by the following equation:

![\vec{u}\times\vec{v}=    \left(       u_yv_z-u_zv_y, \; u_zv_x-u_xv_z, \; u_xv_y-u_yv_x      \right).](02911.jpeg)

Here’s how to compute the cross product of two vectors:

\>>> u = Matrix(\[ 4,5,6\])
>>> v = Matrix(\[-1,1,2\])
>>> u.cross(v)
\[4, -14, 9\]

The vector ![\vec{u}\times \vec{v}](02864.jpeg) is orthogonal to both ![\vec{u}](01562.jpeg) and ![\vec{v}](01520.jpeg). The norm of the cross product ![\|\vec{u}\times \vec{v}\|](02912.jpeg) is proportional to the lengths of the vectors and the sine of the angle between them:

(u.cross(v).norm()/(u.norm()\*v.norm())).n()
0.796366206088088    # = sin(0.921..) 

The cross product is anticommutative, ![\vec{u}\times\vec{v} = -\vec{v}\times\vec{u}](02913.jpeg):

\>>> u.cross(v)
\[4, -14, 9\]
>>> v.cross(u)
\[-4, 14,-9\]

Watch out for this, because it’s a new thing. The product of two numbers ![a](00014.jpeg) and ![b](00074.jpeg) is commutative: ![ab = ba](00087.jpeg). The dot product of two vectors ![\vec{u}](01562.jpeg) and ![\vec{v}](01520.jpeg) is commutative: ![\vec{u}\cdot\vec{v} = \vec{v}\cdot\vec{u}](01741.jpeg). However the cross product is not commutative: ![\vec{u}\times\vec{v} \neq \vec{v}\times\vec{u}](02914.jpeg), it is anticommutative: ![\vec{u}\times\vec{v} = -\vec{v}\times\vec{u}](02913.jpeg).
