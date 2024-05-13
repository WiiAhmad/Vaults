Chapter 7    

##[7.4 Vector products](part0007_split_004.md)

We’ll now define the _dot product_ and the _cross product_: two geometric operations useful for working with three-dimensional vectors.

###[Dot product](part0007_split_004.md)

The _dot product_ takes two vectors as inputs and produces a single, real number as an output:

![\cdot : \mathbb{R}^3 \times \mathbb{R}^3 \quad \to \quad \mathbb{R}.](01723.jpeg)

The dot product between the vector ![\vec{v}=(v_x, v_y, v_z)](01673.jpeg) and the vector ![\vec{w}=(w_x, w_y, w_z)](01724.jpeg) can be computed using either the algebraic formula,

![\vec{v}\cdot\vec{w}  \; = \;   v_xw_x+v_yw_y+v_zw_z,](01725.jpeg)

or the geometric formula,

![\vec{v}\cdot\vec{w}   \; = \;   \|\vec{v}\|\|\vec{w}\|\cos(\varphi), \qquad \; \;](01726.jpeg)

where ![\varphi](01727.jpeg) is the angle between the two vectors. Note the value of the dot product depends on the vectors’ lengths and the cosine of the angle between them.

The name _dot product_ comes from the symbol used to denote it. It is also known as the _scalar product_, since the result of the dot product is a scalar number—a number that does not change when the basis changes. The dot product is also sometimes called the _inner product_.

We can combine the algebraic and the geometric formulas for the dot product to obtain the formula,

![\begin{align*}    \cos(\varphi)     = \frac{ \vec{v}\cdot\vec{w} }{  \|\vec{v}\|\|\vec{w}\| }      = \frac{ v_xw_x+v_yw_y+v_zw_z }{  \|\vec{v}\|\|\vec{w}\| }    \quad    \textrm{and}    \quad    \varphi  = \cos^{-1}\!\left( \cos(\varphi) \right)\!.   \end{align*}](01728.jpeg)

This formula makes it possible to find the angle between two vectors if we know their components.

The geometric factor ![\cos(\varphi)](01729.jpeg) depends on the relative orientation of the two vectors as follows:

-   If the vectors point in the same direction, then ![\cos(\varphi)=\cos(0^\circ) = 1](01730.jpeg), so ![\vec{v}\cdot\vec{w}=\|\vec{v}\|\|\vec{w}\|](01731.jpeg).
-   If the vectors are perpendicular to each other, then ![\cos(\varphi)=\cos(90^\circ) = 0](01732.jpeg), so ![\vec{v}\cdot\vec{w}=0](01733.jpeg).
-   If the vectors point in exactly opposite directions, then ![\cos(\varphi)=\cos(180^\circ) = -1](01734.jpeg), so ![\vec{v}\cdot\vec{w}=-\|\vec{v}\|\|\vec{w}\|](01735.jpeg).

The dot product is defined for vectors of any dimension; as long as two vectors are defined with respect to the same basis, we can compute the dot product between them.

###[Cross product](part0007_split_004.md)

The _cross product_ takes two vectors as inputs and produces another vector as the output:

![\times : \mathbb{R}^3 \times \mathbb{R}^3 \quad \to \quad \mathbb{R}^3.](01736.jpeg)

The cross product of two vectors is perpendicular to both vectors:

![\vec{v}\times\vec{w} = \{ \text{ a vector perpendicular to both } \vec{v} \text{ and } \vec{w} \; \}  \quad \in \mathbb{R}^3.](01737.jpeg)

If you take the cross product of one vector pointing in the ![x](00015.jpeg)\-direction with another vector pointing in the ![y](00018.jpeg)\-direction, the result will be a vector in the ![z](00656.jpeg)\-direction: ![\hat{\imath} \times \hat{\jmath} = \hat{k}](01738.jpeg). The name _cross product_ comes from the symbol used to denote it. It is also sometimes called the _vector product_, since the output of this operation is a vector.

The cross products of individual basis elements are defined as

![\hat{\imath}\times\hat{\jmath} =\hat{k}, \qquad     \hat{\jmath}\times\hat{k} =\hat{\imath},  \qquad     \hat{k}\times \hat{\imath}= \hat{\jmath}.](01739.jpeg)

Look at[Figure 7.10](part0007_split_002.md) on page 7.10 and imagine the vectors ![\hat{\imath}](01616.jpeg), ![\hat{\jmath}](01617.jpeg), and ![\hat{k}](01680.jpeg) pointing along each axis. Try to visualize the three equations above.

The cross product is _anticommutative_, which means swapping the order of the inputs introduces a negative sign in the output:

![\hat{\jmath}\times  \hat{\imath} =-\hat{k}, \qquad    \hat{k}\times\hat{\jmath} =-\hat{\imath}, \qquad    \hat{\imath}\times \hat{k} = -\hat{\jmath}.](01740.jpeg)

It’s likely that, until now, the products you’ve seen in math have been _commutative_, which means the order of the inputs doesn’t matter. The product of two numbers is commutative ![ab=ba](00087.jpeg), and the dot product of two vectors is commutative ![\vec{u}\cdot\vec{v}=\vec{v}\cdot\vec{u}](01741.jpeg), but the cross product of two vectors is _anti_commutative ![\vec{v}\times \vec{w} = - \vec{w}\times \vec{v}](01742.jpeg).

Given two vectors ![\vec{a}=a_x\hat{\imath} + a_y\hat{\jmath} +  a_z\hat{k}](01743.jpeg) and ![\vec{b}=b_x\hat{\imath} + b_y\hat{\jmath} +  b_z\hat{k}](01744.jpeg), their cross product is calculated as

![\vec{a}\times\vec{b}       \; \; = \; \; (a_yb_z - a_zb_y)\hat{\imath} + (a_zb_x - a_xb_z)\hat{\jmath} + (a_xb_y - a_yb_x)\hat{k}.](01745.jpeg)

Computing the cross product requires a specific combination of multiplications and subtractions of the input vectors’ components. The result of this combination is the vector ![\vec{a}\times\vec{b}](01746.jpeg) which is perpendicular to both ![\vec{a}](01747.jpeg) and ![\vec{b}](01748.jpeg).

The length of the cross product of two vectors is proportional to the sine of the angle between the two vectors:

![\|\vec{a}\times\vec{b}\|=\|\vec{a}\|\|\vec{b}\|\sin(\varphi).](01749.jpeg)

####[The right-hand rule](part0007_split_004.md)

Consider the plane formed by the vectors ![\vec{a}](01747.jpeg) and ![\vec{b}](01748.jpeg). There are actually _two_ vectors perpendicular to this plane: one above the plane and one below the plane. We use the _right-hand rule_ to figure out which of these vectors corresponds to the cross product ![\vec{a} \times \vec{b}](01746.jpeg).

Make a fist with your right hand and then extend your thumb, first finger, and middle finger. When your index finger points in the same direction as the vector ![\vec{a}](01747.jpeg) and your middle finger points in the direction of ![\vec{b}](01748.jpeg), your thumb will point in the direction of ![\vec{a} \times \vec{b}](01746.jpeg). The relationship encoded in the right-hand rule matches the relationship between the standard basis vectors: ![\hat{\imath} \times \hat{\jmath} = \hat{k}](01738.jpeg).

![Right_hand_rule_cross_product](01750.jpeg)

Figure 7.12: Using the right-hand rule to determine the direction of the cross product ![\vec{a}\times\vec{b}](01751.jpeg) based on directions of ![\vec{a}](01752.jpeg) and ![\vec{b}](01753.jpeg).

###[Links](part0007_split_004.md)

\[ Nice illustrations of the cross product \]

[`http://1ucasvb.tumblr.com/post/76812811092/`](./76812811092.md)

[https://www.youtube.com/watch?v=eu6i7WJeinw](./watch_v=eu6i7WJeinw.md)

###[Exercises](part0007_split_004.md)

E7.4 Given the vectors ![\vec{u}=(1,1,0)](01754.jpeg) and ![\vec{v}=(0,0,3)](01755.jpeg), compute the following vector expressions:

**a)** ![\vec{u}+\vec{v}](01543.jpeg) **b)** ![\vec{u}-\vec{v}](01544.jpeg) **c)** ![3\vec{u}+\vec{v}](01756.jpeg) **d)** ![\| \vec{u} \|](01757.jpeg)

E7.5 Given ![\vec{v}= (1, 2, 3)](01758.jpeg) and ![\vec{w}=(0, 1, 1)](01759.jpeg), compute the following vector products: **a)** ![\vec{v} \cdot \vec{w}](01760.jpeg); textbfb) ![\vec{v} \times \vec{w}](01761.jpeg); textbfc) ![\vec{w} \times \vec{v}](01762.jpeg); textbfd) ![\vec{w} \times \vec{w}](01763.jpeg).
