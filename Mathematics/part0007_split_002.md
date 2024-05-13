Chapter 7    

##[7.2 Vectors](part0007_split_002.md)

Vectors are extremely useful in all areas of life. In physics, for example, we use a vector to describe the velocity of an object. It is not sufficient to say that the speed of a tennis ball is 200 kilometres per hour: we must also specify the direction in which the ball is moving. Both of the two velocities

![\vec{v}_1 = (200,0)    \qquad \textrm{and}   \qquad \vec{v}_2=(0,200)](01541.jpeg)

describe motion at the speed of ![200](01542.jpeg) kilometres per hour; but since one velocity points along the ![x](00015.jpeg)\-axis, and the other points along the ![y](00018.jpeg)\-axis, they are _completely_ different velocities. The velocity vector contains information about the object’s speed _and_ its direction. The direction makes a big difference. If it turns out the tennis ball is hurtling toward you, you’d better get out of the way!

The main idea in this chapter is that **vectors are not the same as numbers**. We’ll start by defining what vectors are. Then we’ll describe all the mathematical operations we can perform with vectors, which include vector addition ![\vec{u}+\vec{v}](01543.jpeg), vector subtraction ![\vec{u}-\vec{v}](01544.jpeg), vector scaling ![\alpha\vec{v}](01545.jpeg), and other operations. In[Section 7.4](part0007_split_004.md) we’ll also talk about two different kinds of vector products.

###[Definitions](part0007_split_002.md)

A two-dimensional vector ![\vec{v}](01520.jpeg) corresponds to a _pair of numbers_:

![\vec{v} = (v_x, v_y),](01546.jpeg)

where ![v_x](01547.jpeg) is the _![x](00015.jpeg)\-component_ of the vector and ![v_y](01548.jpeg) is its _![y](00018.jpeg)\-component_. We denote the set of two-dimensional vectors as ![\mathbb{R}^2](01549.jpeg), since the components of a two-dimensional vector are specified by two real numbers. We’ll use the mathematical shorthand ![\vec{v} \in \mathbb{R}^2](01550.jpeg) to define a two-dimensional vector ![\vec{v}](01520.jpeg). Vectors in ![\mathbb{R}^2](01549.jpeg) can be represented as arrows in the Cartesian plane. See the vector ![\vec{v}=(3,2)](01551.jpeg) illustrated in[Figure 7.1](Vectors.md).

We can also define three-dimensional vectors like the vector ![\vec{v} = (v_x, v_y, v_z) \in \mathbb{R}^3](01552.jpeg), which has three components. Three-dimensional vectors can be represented as arrows in a coordinate system that has three axes, like the one shown in[Figure 7.10](part0007_split_002.md) on page 7.10. A three-dimensional coordinate system is similar to the Cartesian coordinate system you’re familiar with, and includes the additional ![z](00656.jpeg)\-axis that measures the height above the plane. In fact, there’s no limit to the number of dimensions for vectors. We can define vectors in an ![n](00054.jpeg)\-dimensional space: ![\vec{v} = (v_1, v_2, \ldots, v_n) \in \mathbb{R}^n](01553.jpeg). For the sake of simplicity, we’ll define all the vector operation formulas using two-dimensional vectors. Unless otherwise indicated in the text, all the formulas we give for two-dimensional vectors ![\vec{v} \in \mathbb{R}^2](01550.jpeg) also apply to ![n](00054.jpeg)\-dimensional vectors ![\vec{v} \in \mathbb{R}^n](01554.jpeg).

####[Vector operations](part0007_split_002.md)

Consider two vectors, ![\vec{u}=(u_x,u_y)](01555.jpeg) and ![\vec{v}=(v_x,v_y)](00645.jpeg), and assume that ![\alpha \in \mathbb{R}](01556.jpeg) is an arbitrary constant. The following operations are defined for these vectors:

-   **Addition:** ![\vec{u} + \vec{v} = (u_x+v_x,\, u_y+v_y)](01557.jpeg)
-   **Subtraction:** ![\vec{u} - \vec{v} = (u_x-v_x,\, u_y-v_y)](01558.jpeg)
-   **Scaling:** ![\alpha \vec{u} = (\alpha u_x,\, \alpha u_y)](01559.jpeg)
-   **Dot product:** ![\vec{u} \cdot \vec{v}  = u_xv_x+u_yv_y](01560.jpeg)
-   **Length:** ![\|\vec{u}\| = \sqrt{\vec{u}\cdot\vec{u}} = \sqrt{u_x^2+u_y^2}](01561.jpeg). The vector’s length is also called the _norm_ of the vector. We sometimes use the letter ![u](00272.jpeg) to denote the length of the vector ![\vec{u}](01562.jpeg).

Note there is no vector division operation.

For vectors in a three-dimensional space ![\vec{u}=(u_x,u_y,u_z) \in \mathbb{R}^3](01563.jpeg) and ![\vec{v}=(v_x,v_y,v_z) \in \mathbb{R}^3](01552.jpeg), we can also define the **cross product** operation ![\vec{u} \times \vec{v} = (u_yv_z-u_zv_y,\; u_zv_x-u_xv_z,\; u_xv_y-u_yv_x)](01564.jpeg). The dot product and the cross product are new operations that you probably haven’t seen before. We’ll talk more about dot products and the cross products in[Section 7.4](part0007_split_004.md). For now let’s start with the basics.

####[Vector representations](part0007_split_002.md)

We’ll use three equivalent ways to denote vectors in two dimensions:

-   ![\vec{v} =(v_x, v_y)](00645.jpeg): component notation. The vector is written as a pair of numbers called the _components_ or _coordinates_ of the vector.
-   ![\vec{v} =v_x\hat{\imath}+ v_y\hat{\jmath}](01565.jpeg): unit vector notation. The vector is expressed as a combination of the unit vectors ![\hat{\imath} = (1,0)](01566.jpeg) and ![\hat{\jmath} = (0,1)](01567.jpeg).
-   ![\vec{v}=\|\vec{v}\|\angle \theta](01568.jpeg): length-and-direction notation (polar coordinates). The vector is expressed in terms of its _length_ ![\|\vec{v}\|](01569.jpeg) and the angle ![\theta](00944.jpeg) that the vector makes with the ![x](00015.jpeg)\-axis.

![vector_components_annotated](01570.jpeg)

Figure 7.3: The vector ![\vec{v}=(v_x,v_y) = v_x\hat{\imath}+ v_y\hat{\jmath} = \|\vec{v}\|\angle \theta](01571.jpeg).

We use the component notation for doing vector algebra calculations since it is most compact. The unit vector notation shows explicitly that the vector ![\vec{v}](01520.jpeg) corresponds to the sum of ![v_x\hat{\imath}](01572.jpeg) (a displacement of ![v_x](01547.jpeg) steps in the direction of the ![x](00015.jpeg)\-axis) and ![v_y\hat{\jmath}](01573.jpeg) (a displacement of ![v_y](01548.jpeg) steps in the direction of the ![y](00018.jpeg)\-axis). The length-and-direction notation describes the vector ![\vec{v}](01520.jpeg) as a displacement of ![\|\vec{v}\|](01569.jpeg) steps in the direction of the angle ![\theta](00944.jpeg). We’ll use all three ways of denoting vectors throughout the rest of the book, and we’ll learn how to convert between them.

###[Vector algebra](part0007_split_002.md)

#####[Addition and subtraction](part0007_split_002.md)

Just like numbers, you can add vectors

![\vec{v}+\vec{w} = (v_x, \, v_y) + (w_x, \, w_y) = (v_x+w_x, \, v_y+w_y),](01574.jpeg)

subtract them

![\vec{v}-\vec{w} = (v_x, \, v_y) - (w_x, \, w_y) = (v_x-w_x, \, v_y-w_y),](01575.jpeg)

and solve all kinds of equations where the unknown variable is a vector. This is not a formidably complicated new development in mathematics. Performing arithmetic calculations on vectors simply requires **carrying out arithmetic operations on their components**. Given two vectors, ![\vec{v}=(4,2)](01576.jpeg) and ![\vec{w}=(3,7)](01577.jpeg), their difference is computed as ![\vec{v}-\vec{w} = (4, 2) - (3, 7) = (1,  -5)](01578.jpeg).

#####[Scaling](part0007_split_002.md)

We can also _scale_ a vector by any number ![\alpha \in \mathbb{R}](01556.jpeg):

![\alpha \vec{v} = (\alpha v_x, \alpha v_y),](01579.jpeg)

where each component is multiplied by the scale factor ![\alpha](01112.jpeg). Scaling changes the length of a vector. If ![\alpha>1](01580.jpeg) the vector will get longer, and if ![0\leq \alpha <1](01581.jpeg) then the vector will become shorter. If ![\alpha](01112.jpeg) is a negative number, the scaled vector will point in the opposite direction.

#####[Length](part0007_split_002.md)

A vector’s length is obtained from Pythagoras’ theorem. Imagine a right-angle triangle with one side of length ![v_x](01547.jpeg) and the other side of length ![v_y](01548.jpeg); the length of the vector is equal to the length of the triangle’s hypotenuse:

![\|\vec{v}\|^2  = v_x^2 + v_y^2      \qquad\Rightarrow\qquad     \|\vec{v}\|  = \sqrt{ v_x^2 + v_y^2 }\,.](01582.jpeg)

A common technique is to scale a vector ![\vec{v}](01520.jpeg) by one over its length ![\frac{1}{ \|\vec{v}\|}](01583.jpeg) to obtain a unit vector that points in the same direction as ![\vec{v}](01520.jpeg):

![\hat{v} = \frac{\vec{v}}{ \|\vec{v}\| }=\left( \frac{v_x}{ \|\vec{v}\| }, \frac{v_y}{ \|\vec{v}\| } \right)\!.](01584.jpeg)

Unit vectors (denoted with a hat instead of an arrow) are useful when you want to describe only a direction in space without any specific length in mind. Verify that ![\|\hat{v}\|=1](01585.jpeg).

###[Vector as arrows](part0007_split_002.md)

So far, we described how to perform algebraic operations on vectors in terms of their components. Vector operations can also be interpreted geometrically, as operations on arrows in the Cartesian plane.

#####[Vector addition](part0007_split_002.md)

The sum of two vectors corresponds to the combined displacement of the two vectors.[Figure 7.4](part0007_split_002.md) illustrates the addition of two vectors, ![\vec{v}_1=(3,0)](01586.jpeg) and ![\vec{v}_2=(2,2)](01587.jpeg). The sum of the two vectors is the vector ![\vec{v}_1+\vec{v}_2=(3,0)+(2,2)=(5,2)](01588.jpeg).

![vector_addition](01589.jpeg)

Figure 7.4: The addition of the vectors ![\vec{v}_1](01590.jpeg) and ![\vec{v}_2](01591.jpeg) produces the vector ![(5,2)](01592.jpeg).

#####[Vector subtraction](part0007_split_002.md)

Before we describe vector subtraction, note that multiplying a vector by a scale factor ![\alpha=-1](01593.jpeg) gives a vector of the same length as the original, but pointing in the opposite direction.

This fact is useful if you want to subtract two vectors using the graphical approach. Subtracting a vector is the same as adding the negative of the vector:

![\vec{w} - \vec{v}_1     = \vec{w} + (- \vec{v}_1)     =  \vec{v}_2.](01594.jpeg)

![vector_subtraction](01595.jpeg)

Figure 7.5: The vector subtraction ![\vec{w} - \vec{v}_1](01596.jpeg) is equivalent to the vector addition ![\vec{w} + (-\vec{v}_1)](01597.jpeg), where ![(-\vec{v}_1)](01598.jpeg) is like ![\vec{v}_1](01590.jpeg) but points in the opposite direction.

[Figure 7.5](part0007_split_002.md) illustrates the graphical procedure for subtracting the vector ![\vec{v}_1=(3,0)](01586.jpeg) from the vector ![\vec{w}=(5,2)](01599.jpeg). Subtraction of ![\vec{v}_1=(3,0)](01586.jpeg) is the same as addition of ![-\vec{v}_1=(-3,0)](01600.jpeg).

#####[Scaling](part0007_split_002.md)

The scaling operation acts to change the length of a vector. Suppose we want to obtain a vector in the same direction as the vector ![\vec{v}=(3,2)](01551.jpeg), but half as long. “Half as long” corresponds to a scale factor of ![\alpha = 0.5](01601.jpeg). The scaled-down vector is ![\vec{w}=0.5\vec{v}=(1.5,1)](01602.jpeg). Conversely, we can think of the vector ![\vec{v}](01520.jpeg) as being twice as long as the vector ![\vec{w}](01603.jpeg).

![vector_scaled_by_point_five](01604.jpeg)

Figure 7.6: Vectors ![\vec{v}](01523.jpeg) and ![\vec{w}](01605.jpeg) are related by the equation ![\vec{v}=2\vec{w}](01606.jpeg).

Multiplying a vector by a negative number reverses its direction.

###[Length-and-direction representation](part0007_split_002.md)

So far, we’ve seen how to represent a vector in terms of its components. There is another way of representing two-dimensional vectors: we can describe the vector ![\vec{v} \in \mathbb{R}^2](01550.jpeg) in terms of its length ![\|\vec{v}\|](01569.jpeg) and its direction ![\theta](00944.jpeg)—the angle it makes with the ![x](00015.jpeg)\-axis. For example, the vector ![(1,1)](01607.jpeg) can also be written as ![\sqrt{2}\angle45^{\circ}](01608.jpeg) in polar coordinates. This length-and-direction notation is useful because it makes it easy to see the “size” of vectors. On the other hand, vector arithmetic operations are much easier to carry out in the component notation. It’s therefore good to know the formulas for converting between the two vector representations.

![polar_coordinates_conversion_for_vector_v](01609.jpeg)

Figure 7.7: The ![x](00632.jpeg)\- and ![y](00674.jpeg)\-components of a vector with length ![\|\vec{v}\|](01610.jpeg) in the direction ![\theta](01154.jpeg) are given by ![v_x=\|\vec{v}\|\cos\theta](01611.jpeg) and ![v_y=\|\vec{v}\|\sin\theta](01612.jpeg).

To convert the length-and-direction vector ![\vec{v}=\|\vec{v}\|\angle\theta](01568.jpeg) into an ![x](00015.jpeg)\-component and a ![y](00018.jpeg)\-component ![(v_x,v_y)](01519.jpeg), use the formulas

![v_x=\|\vec{v}\|\cos\theta       \quad \textrm{and} \quad      v_y=\|\vec{v}\|\sin\theta.](01613.jpeg)

To convert from component notation ![\vec{v}=(v_x,v_y)](00645.jpeg) to length-and-direction ![\|\vec{v}\|\angle\theta](01614.jpeg), use

![\|\vec{v}\|=\sqrt{v_x^2+v_y^2}\,,    \quad    \theta\! =\!\left\{ \begin{array}{ll}       \!\!\tan^{-1}\!\big(\tfrac{v_y}{v_x}\big)     & \textrm{ if } v_x > 0,      \\       \!\!180^\circ + \tan^{-1}\!\!\big(\tfrac{v_y}{v_x}\big)   & \textrm{ if } v_x < 0,      \\       \!\!90^\circ           & \textrm{ if } v_x=0 \textrm{ and }  v_y > 0,   \\       \!\!-90^\circ           & \textrm{ if } v_x=0 \textrm{ and }  v_y < 0.      \end{array}\right.](01615.jpeg)

We’ve already seen these formulas in[Section 6.4](part0006_split_004.md) (page 6.4.2.1), when we learned about the transformations between Cartesian and polar coordinates for points. The conversion procedure for vectors is exactly the same, including the trickiness around calculating ![\theta](00944.jpeg) when ![v_x](01547.jpeg) is negative or zero. I invite you to revisit exercise [6.4.4](part0006_split_004.md) on page 6.4.4 to review the conversion operations between Cartesian coordinates and polar coordinates.

###[Unit vector notation](part0007_split_002.md)

In two dimensions, we can think of a vector ![\vec{v}=(v_x, v_y)](00645.jpeg) as a command to “Go a distance ![v_x](01547.jpeg) in the ![x](00015.jpeg)\-direction and a distance ![v_y](01548.jpeg) in the ![y](00018.jpeg)\-direction.” To write this set of commands more explicitly, we can use multiples of the vectors ![\hat{\imath}](01616.jpeg) and ![\hat{\jmath}](01617.jpeg). These are the unit vectors pointing in the ![x](00015.jpeg) and ![y](00018.jpeg) directions:

![\hat{\imath} = (1,0) \qquad \textrm{and} \qquad \hat{\jmath} = (0,1).](01618.jpeg)

Any number multiplied by ![\hat{\imath}](01616.jpeg) corresponds to a vector with that number in the first coordinate. For example, ![3\hat{\imath}=(3,0)](01619.jpeg) and ![4\hat{\jmath}=(0,4)](01620.jpeg).

In physics, we tend to perform a lot of numerical calculations with vectors; to make things easier, we often use unit vector notation:

![v_x \hat{\imath} + v_y\hat{\jmath}    \qquad \Leftrightarrow \qquad    (v_x, v_y).](01621.jpeg)

The addition rule remains the same for the new notation:

![\underbrace{2\hat{\imath}+ 3\hat{\jmath}}_{\vec{v}} \; \; + \; \;  \underbrace{ 5\hat{\imath} - 2\hat{\jmath}}_{\vec{w}}     \; = \;     \underbrace{  7\hat{\imath} + 1\hat{\jmath} }_{\vec{v}+\vec{w}}.](01622.jpeg)

It’s the same story repeating all over again: we need to add ![\hat{\imath}](01616.jpeg)s with ![\hat{\imath}](01616.jpeg)s, and ![\hat{\jmath}](01617.jpeg)s with ![\hat{\jmath}](01617.jpeg)s.

###[Examples](part0007_split_002.md)

####[Simple example](part0007_split_002.md)

Compute the sum ![\vec{s}=4\hat{\imath}+5\angle 30^\circ](01623.jpeg). Express your answer in the length-and-direction notation.

Since we want to carry out an addition, and since addition is performed in terms of components, our first step is to convert ![5\angle 30^\circ](01624.jpeg) into component notation: ![5\angle 30^\circ      = 5\cos 30^\circ\hat{\imath} + 5\sin 30^\circ\hat{\jmath}     = \tfrac{5\sqrt{3}}{2}\hat{\imath}+ \tfrac{5}{2}\hat{\jmath}](01625.jpeg). We can now compute the sum:

![\vec{s} \; \; = \; \;      4\hat{\imath}  \; +  \; \tfrac{5\sqrt{3}}{2}\hat{\imath} + \tfrac{5}{2}\hat{\jmath}      \; \; = \; \;       (4+ \tfrac{5\sqrt{3}}{2})\hat{\imath} + (\tfrac{5}{2})\hat{\jmath}\,.](01626.jpeg)

The ![x](00015.jpeg)\-component of the sum is ![s_x = (4+ \frac{5\sqrt{3}}{2})](01627.jpeg) and the ![y](00018.jpeg)\-component of the sum is ![s_y = (\frac{5}{2})](01628.jpeg). To express the answer as a length and a direction, we compute the length ![\|\vec{s}\|= \sqrt{s_x^2 + s_y^2} = 8.697](01629.jpeg) and the direction ![\tan^{-1}(s_y/s_x)=16.7^\circ](01630.jpeg). The answer is ![\vec{s}= 8.697\angle 16.7^\circ](01631.jpeg).

####[Vector addition example](part0007_split_002.md)

You’re heading to physics class after a “safety meeting” with a friend, and are looking forward to two hours of finding absolute amazement and awe in the laws of Mother Nature. As it turns out, there is no enlightenment to be had that day because there is going to be an in-class midterm. The first question involves a block sliding down an incline. You look at it, draw a little diagram, and then wonder how the hell you are going to find the net force acting on the block. The three forces acting on the block are ![\vec{W} = 300 \angle -90^{\circ}](01632.jpeg), ![\vec{N} = 260 \angle 120^{\circ}](01633.jpeg), and ![\vec{F}_f = 50 \angle 30^{\circ}](01634.jpeg).

You happen to remember the net force formula:

![\sum \vec{F} = \vec{F}_{\textrm{net}} = m\vec{a} \qquad  \text{[ Newton's 2\textsuperscript{nd} law ]}.](01635.jpeg)

You get the feeling Newton’s 2nd law is the answer to all your troubles. You sense this formula is certainly the key because you saw the keyword “net force” when reading the question, and notice “net force” also appears in this very equation.

The net force is the sum of all forces acting on the block:

![\vec{F}_{\textrm{net}} = \sum \vec{F}  = \vec{W} + \vec{N}  + \vec{F}_f.](01636.jpeg)

All that separates you from the answer is the addition of these vectors. Vectors have components, and there is the whole sin/cos procedure for decomposing length-and-direction vectors into their components. If you have the vectors as components you’ll be able to add them and find the net force.

Okay, chill! Let’s do this one step at a time. The net force must have an ![x](00015.jpeg)\-component, which, according to the equation, must equal the sum of the ![x](00015.jpeg)\-components of all the forces:

![\begin{align*}     F_{\textrm{net},x}      & = W_x + N_x + F_{f,x}  \\     & = 300\cos(-90^{\circ}) + 260\cos(120^{\circ})+ 50\cos(30^{\circ}) \\     & = -86.7.    \end{align*}](01637.jpeg)

Now find the ![y](00018.jpeg)\-component of the net force using the ![\sin](00935.jpeg) of the angles:

![\begin{align*}     F_{\textrm{net},y}      & = W_y + N_y + F_{f,y} \\     & = 300\sin(-90^{\circ}) + 260\sin(120^{\circ})+ 50\sin(30^{\circ}) \\     & = -49.8.    \end{align*}](01638.jpeg)

Combining the two components of the vector, you get the final answer:

![\begin{align*}     \vec{F}_{\textrm{net}}      & = (F_{\textrm{net},x},\, F_{\textrm{net},y})   \\     & = (-86.7,-49.8)     =-86.7 \hat{\imath} \; - 49.8 \hat{\jmath}    \\     & = 100\angle 209.9^\circ,    \end{align*}](01639.jpeg)

where you found the angle ![209.9^\circ](01640.jpeg) by computing ![\tan^{-1}(49.8/86.7)](01641.jpeg) and adding ![180^\circ](01127.jpeg) since the ![x](00015.jpeg)\-component is negative. Bam! Just like that you’re done, because you overstand them vectors!

####[Relative motion example](part0007_split_002.md)

A boat can reach a top speed of 12 knots in calm seas. Instead of cruising through a calm sea, however, the boat’s crew is trying to sail up the St-Laurence river. The speed of the current is 5 knots.

If the boat travels directly upstream at full throttle 12![\hat{\imath}](01616.jpeg), then the speed of the boat relative to the shore will be

![12\hat{\imath} - 5 \hat{\imath} = 7\hat{\imath},](01642.jpeg)

since we must “deduct” the speed of the current from the speed of the boat relative to the water. See the vector diagram in[Figure 7.8](part0007_split_002.md).

![vectors-boat-in-current-upstream](01643.jpeg)

Figure 7.8: A boat travels with speed ![12](01644.jpeg) knots against a current of ![5](01645.jpeg) knots.

If the crew wants to cross the river perpendicular to the current flow, they can use some of the boat’s thrust to counterbalance the current, and the remaining thrust to push across. The situation is illustrated in[Figure 7.9](part0007_split_002.md). In what direction should the boat sail to cross the river? We are looking for the direction of ![\vec{v}](01520.jpeg) the boat should take such that, after adding in the velocity of the current, the boat moves in a straight line between the two banks (in the ![\hat{\jmath}](01617.jpeg) direction).

![vectors-boat-in-current](01646.jpeg)

Figure 7.9: Part of the boat’s thrust cancels the current.

Let’s analyze the vector diagram. The opposite side of the triangle is parallel to the current flow and has length ![5](00117.jpeg). We take the up-the-river component of the velocity ![\vec{v}](01520.jpeg) to be equal to ![5\hat{\imath}](01647.jpeg), so that it cancels exactly the ![-5\hat{\imath}](01648.jpeg) flow of the river. The hypotenuse has length ![12](00482.jpeg) since this is the speed of the boat relative to the surface of the water.

From all of this we can answer the question like professionals. You want the angle? Well, we have that ![\frac{\text{opp}}{\text{hyp}} = \frac{5}{12}=\sin(\theta)](01649.jpeg), where ![\theta](00944.jpeg) is the angle of the boat’s course relative to the straight line between the two banks. We can use the inverse-sin function to solve for the angle:

![\theta = \sin^{-1}\!\left(\tfrac{5}{12} \right) = 24.62^\circ.](01650.jpeg)

The across-the-river component of the velocity can be calculated using ![v_y = 12\cos(\theta)=10.91](01651.jpeg), or from Pythagoras’ theorem if you prefer ![v_y = \sqrt{ \|\vec{v}\|^2 - v_x^2 } = \sqrt{ 12^2 - 5^2 }=10.91](01652.jpeg).

###[Discussion](part0007_split_002.md)

We did a lot of hands-on activities with vectors in this section and skipped over some of the theoretical details. Now that you’ve been exposed to the practical side of vector calculations, it’s worth clarifying certain points that we glossed over.

####[Vectors vs. points](part0007_split_002.md)

We used the notation ![\mathbb{R}^2](01549.jpeg) to describe two kinds of math objects: the set of points in the Cartesian plane and the set of vectors in a two-dimensional space. The point ![P=(P_x,P_y)](00638.jpeg) and the vector ![\vec{v}=(v_x,v_y)](00645.jpeg) are both represented by pairs of real numbers, so we use the notation ![P \in \mathbb{R}^2](01653.jpeg) and ![\vec{v} \in \mathbb{R}^2](01550.jpeg) to describe them. This means that a pair of numbers ![(3,2) \in \mathbb{R}^2](01654.jpeg) could represent the _coordinates_ of a point, or the _components_ of a vector, depending on the context.

Let’s take a moment to review the definitions of points and vectors and clarify the types of operations we can perform on them:

-   **Space of points ![\mathbb{R}^2](01549.jpeg)** : the set of points ![P=(P_x,P_y)](00638.jpeg) corresponds to locations in the Cartesian plane. The point ![P=(P_x,P_y)](00638.jpeg) corresponds to the geometric instructions: “Starting at the origin ![(0,0)](00923.jpeg), move ![P_x](00639.jpeg) units along the ![x](00015.jpeg)\-axis and ![P_y](00640.jpeg) units along the ![y](00018.jpeg)\-axis.” The distance between points ![P](00267.jpeg) and ![Q](01329.jpeg) is denoted ![d(P,Q)](01655.jpeg).
-   **Vector space ![\mathbb{R}^2](01549.jpeg)** : the set of vectors ![\vec{v}=(v_x, v_y)](00645.jpeg) describes displacements in the Cartesian plane. The vector ![\vec{v}=(v_x, v_y)](00645.jpeg) corresponds to the instructions: “Starting anywhere, move ![v_x](01547.jpeg) units along the ![x](00015.jpeg)\-axis and ![v_y](01548.jpeg) units along the ![y](00018.jpeg)\-axis.” Vectors can be combined and manipulated using the vector algebra operations ![\vec{u}+\vec{v}](01543.jpeg), ![\vec{u}-\vec{v}](01544.jpeg), ![\alpha\vec{u}](01656.jpeg), ![\vec{u}\cdot\vec{v}](01657.jpeg), and ![\|\vec{v}\|](01569.jpeg).

Note the geometric instructions for points and vectors are very similar; the only difference is the starting point. The coordinates of a point ![(P_x,P_y)](01658.jpeg) specify a _fixed position_ relative to the origin ![(0,0)](00923.jpeg), while the components of a vector ![(v_x, v_y)](01519.jpeg) describe a _relative displacement_ that can have any starting point.

Let’s look at some examples of calculations that combine points and vectors. Consider the points ![P](00267.jpeg) and ![Q](01329.jpeg) in the Cartesian plane, and the displacement vector ![\vec{v}_{\tiny PQ}](01659.jpeg) between them. The displacement vector ![\vec{v}_{\tiny PQ}](01659.jpeg) gives the “move instructions” for getting from point ![P](00267.jpeg) to point ![Q](01329.jpeg) and is defined by the equation:

![\vec{v}_{\tiny PQ} \; =  \;  Q - P.](01660.jpeg)

This equation says that subtracting two points produces a vector, which make sense if you think about it—the “difference” between two points is a displacement vector.

We can use the displacement vector ![\vec{v}_{\tiny PQ}](01659.jpeg) in calculations like this:

![P + \vec{v}_{\tiny PQ} \; = \; P +  (Q - P) \; =  \; Q.](01661.jpeg)

In words, this calculation shows that “Starting at the point ![P](00267.jpeg) and moving by ![\vec{v}_{\tiny PQ}](01659.jpeg) brings us to the point ![Q](01329.jpeg).”

The above equations use addition and subtraction operations between a mix of points and vectors. This is rather unusual: normally we only use operations like “+” and “-” between math objects of the same kind. In this case, we’re allowed to mix points and vectors because they both describe “move instructions” of the same kind.

Let’s keep going. What other useful calculations can we do by combining points and vectors? Suppose we wanted to find the midpoint ![M](01424.jpeg) that lies exactly in the middle between points ![P](00267.jpeg) and ![Q](01329.jpeg). We can find the midpoint ![M](01424.jpeg) using the displacement vector ![\vec{v}_{\tiny PQ}](01659.jpeg) and some basic vector algebra. If starting from ![P](00267.jpeg) and moving by ![\vec{v}_{\tiny PQ}](01659.jpeg) brings us all the way to the point ![Q](01329.jpeg), then starting from ![P](00267.jpeg) and moving by ![\frac{1}{2}\vec{v}_{\tiny PQ}](01662.jpeg) will bring us to the midpoint: ![M =  P + \tfrac{1}{2}\vec{v}_{\tiny PQ}](01663.jpeg).

The mathematical bridge between points and vectors allows us to use vector techniques to solve geometry problems. By learning to describe geometric objects like points, lines, and circles using vectors, we can do complicated geometry calculations using simple algebraic manipulations like vector operations. This exemplifies a general pattern in mathematics: applying techniques developed in one domain to solve problems in another domain.

#####[Example](part0007_split_002.md)

You come to class one day and there’s a surprise quiz that asks you to write the formula for the distance ![d(P,Q)](01655.jpeg) between two points ![P=(P_x,P_y)](00638.jpeg) and ![Q=(Q_x,Q_y)](01664.jpeg). You don’t remember ever learning about such a formula and feel caught off guard. How can the teacher ask for a formula they haven’t covered in class yet? This seems totally unfair!

After a minute of stressing out, you take a deep breath, come back to your senses, and resolve to give this problem a shot. You start by sketching a coordinate system, placing points ![P](00267.jpeg) and ![Q](01329.jpeg) in it, and drawing the line that connects the two points. What is the formula that describes the length of this line?

The line from ![P](00267.jpeg) to ![Q](01329.jpeg) looks like the hypotenuse of a triangle, which makes you think that trigonometry could somehow be used to find the answer. Unfortunately, trying to remember the trigonometry formulas has only the effect of increasing your math anxiety. You take this as a sign that you should look for other options. In math, it’s important to trust your gut instincts.

By a fortunate coincidence, you were recently reading about the connection between points and vectors, and specifically about the displacement vector ![\vec{v}_{\tiny PQ} = Q - P](01665.jpeg). The line in your sketch represents the vector ![\vec{v}_{\tiny PQ}](01659.jpeg). You realize that the distance between the points ![P](00267.jpeg) and ![Q](01329.jpeg) is the same as the length of the vector ![\vec{v}_{\tiny PQ}](01659.jpeg). You remember the formula for the length of a vector ![\vec{v}](01520.jpeg) is ![\|\vec{v}\| = \sqrt{ v_x^2 + v_y^2}](01666.jpeg) and you know the formula for the displacement vector is ![\vec{v}_{\tiny PQ} = (Q_x-P_x, Q_y-P_y)](01667.jpeg), so you combine these formulas to obtain the answer: ![d(P,Q) = \left\|\vec{v}_{\tiny PQ}\right\| = \sqrt{ (Q_x-P_x)^2 + (Q_y-P_y)^2 }](01668.jpeg). One more win for the “don’t worry and try it” strategy for solving math problems!

####[Vectors in three dimensions](part0007_split_002.md)

A three-dimensional coordinate system consists of three axes: the ![x](00015.jpeg)\-axis, the ![y](00018.jpeg)\-axis, and the ![z](00656.jpeg)\-axis. The three axes point in perpendicular directions to each other, as illustrated in[Figure 7.10](part0007_split_002.md). Look around you and find a corner of the room you’re in where two walls and the floor meet. The ![x](00015.jpeg)\-axis and the ![y](00018.jpeg)\-axis are the edges where the floor meets the walls. The vertical edge where the two walls meet represents the ![z](00656.jpeg)\-axis.

![empty_coordinate_system_3D](01669.gif)

Figure 7.10: A three-dimensional coordinate system with ![x](00632.jpeg), ![y](00674.jpeg), and ![z](01670.jpeg) axes.

The vector ![\vec{v} = (v_x, v_y, v_z) \in \mathbb{R}^3](01552.jpeg) describes the following displacement instructions: “Move ![v_x](01547.jpeg) units in the direction of the ![x](00015.jpeg)\-axis, then move ![v_y](01548.jpeg) along the ![y](00018.jpeg)\-axis, and finally move ![v_z](01671.jpeg) in the direction of the ![z](00656.jpeg)\-axis.” In three dimensions, there are three unit vectors that describe unit steps in the direction of each of the axes:

![\hat{\imath} = (1, 0, 0), \qquad     \hat{\jmath} = (0, 1, 0) \quad \textrm{and} \quad \;     \hat{k} = (0, 0, 1).](01672.jpeg)

We can therefore describe the vector ![\vec{v} = (v_x, v_y, v_z)](01673.jpeg) in terms of unit vectors as ![\vec{v} = v_x \hat{\imath} + v_y \hat{\jmath} + v_z \hat{k}](01674.jpeg).

####[High-dimensional vectors](part0007_split_002.md)

The most common types of vectors you’ll encounter in math and physics are two-dimensional and three-dimensional vectors. In other fields of science like genetics and machine learning, it’s common to see vectors with many more dimensions. For example, in machine learning we often represent “rich data” like images, videos, and text as vectors with thousands of dimensions.

An example of an ![n](00054.jpeg)\-dimensional vector is

![\vec{v} = (v_1, v_2, \ldots, v_n) \in \mathbb{R}^n.](01675.jpeg)

The vector algebra operations you learned in this section also apply to these high-dimensional vectors.

####[Vectors and vector coordinates](part0007_split_002.md)

One final point we need to clarify is the difference between real-world vector quantities like the velocity of a tennis ball ![\vec{v}](01520.jpeg) and its mathematical representation as a coordinate vector ![(v_x,v_y,v_z)](01676.jpeg). If you know the coordinate vector ![(v_x,v_y,v_z)](01676.jpeg) then you know what the real-world velocity is, right? Not quite.

Let’s say you’re doing a physics research project on tennis serves. You define an ![xyz](01677.jpeg)\-coordinate system for the tennis court, which allows you to represent the ball’s velocity ![\vec{v}](01520.jpeg) as a triple of components ![(v_x,v_y,v_z)](01676.jpeg) interpreted as: “The ball is moving with velocity ![v_x](01547.jpeg) units in the ![x](00015.jpeg)\-direction, ![v_y](01548.jpeg) units in the ![y](00018.jpeg)\-direction, and ![v_z](01671.jpeg) units in the ![z](00656.jpeg)\-direction.”

Suppose you want to describe the velocity vector ![\vec{v}](01520.jpeg) to a fellow physicist via text message. Referring to your sheet of calculations, you find the values ![\vec{v}=(60,3,-2)](01678.jpeg), which you know were measured in metres per second. You send this message:

    The velocity is (60,3,-2) measured in metres per second. 

A few minutes later the following reply comes back:

    Wait whaaat? What coordinate system are you using? 

Indeed the information you sent is incomplete. Vector components depend on the coordinate system in which the vectors are represented. The triple of numbers ![(60,3,-2)](01679.jpeg) only makes sense once you know the directions of the axes in the ![xyz](01677.jpeg)\-coordinate system. Realizing your mistake, you send a text with all the required information:

    Using the coordinate system centred at the south post of
    the net, with the x-axis pointing east along the court,
    the y-axis pointing north along the net, and the z-axis
    pointing up, the velocity is (60,3,-2) in metres per second. 

A few seconds later, you get the reply:

    OK got it now. Thx! 

This hypothetical situation illustrates the importance of the coordinate systems for describing vectors. If you don’t know what the coordinate system is, knowing the coordinates ![(v_x,v_y,v_z)](01676.jpeg) doesn’t tell you much. Only when you know the directions of the unit vectors ![\hat{\imath}](01616.jpeg), ![\hat{\jmath}](01617.jpeg), and ![\hat{k}](01680.jpeg) can you interpret the instructions ![\vec{v} = v_x\hat{\imath}+v_y\hat{\jmath}+v_z\hat{k}](01674.jpeg).

It turns out, using the ![xyz](01677.jpeg)\-coordinate system with the three vectors ![\{\hat{\imath},\hat{\jmath},\hat{k}\}](01681.jpeg) is just one of many possible ways we can represent vectors. We can represent a vector ![\vec{v}](01520.jpeg) as coordinates ![(v_1,v_2,v_3)](01682.jpeg) with respect to any _basis_ ![\{ \hat{e}_1, \hat{e}_2, \hat{e}_3 \}](01683.jpeg) using the expression ![\vec{v} = v_1\hat{e}_1 + v_2\hat{e}_2 +  v_3\hat{e}_3](01684.jpeg), which corresponds to the instructions: “Move ![v_1](01685.jpeg) units in the direction of ![\hat{e}_1](01686.jpeg), move ![v_2](01687.jpeg) units in the direction of ![\hat{e}_2](01688.jpeg), and move ![v_3](01689.jpeg) units in the direction of ![\hat{e}_3](01690.jpeg).”

What’s a basis, you ask? I’m glad you asked, because this is the subject of the next section.
