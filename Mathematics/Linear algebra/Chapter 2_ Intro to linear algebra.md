Chapter 2      

#[Chapter 2 Intro to linear algebra](./Chapter 2_ Intro to linear algebra.md)

The first chapter reviewed core ideas of mathematics. Now that we’re done with the prerequisites, we can begin the main discussion of linear algebra: the study of vectors and matrices.

##[2.1 Definitions](./Chapter 2_ Intro to linear algebra.md)

Vectors and matrices are the objects of study in linear algebra, and in this chapter we’ll define them and learn the basic operations we can perform on them.

We denote the set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vectors with real coefficients as ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png). A vector ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png) is an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-tuple of real numbers[1](./Front matter.md) For example, a three-dimensional vector is defined as a triple of numbers:

![\vec{v} \; \eqdef \; (v_1,v_2,v_3).](./images/ffea2e06561f139667a193ca3ce40fa160285c5d.png)

To specify the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), we must specify the values for its three components, ![v_1](./images/26bb4de90d49b42600706cf2e962fbcf50141c0c.png), ![v_2](./images/b8ca706d019569604aca5b0c8b702542f0fd8e6b.png), and ![v_3](./images/bfc4eadd653f02c4089f3359b55ced531eb69354.png). We’ll use the terms _components_ and _coordinates_ interchangeably throughout the book.

A matrix ![A \in \mathbb{R}^{m\times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) is a rectangular array of real numbers with ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) rows and ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) columns. For example, a ![3\times 2](./images/3247cd7695abad3cf4c4a69c536cd715d34202d1.png) matrix is defined like this:

![\; 
A
\; \eqdef  \; 
\left[\begin{array}{ccc}
a_{11} & a_{12} 	\\
a_{21} & a_{22}  	\\
a_{31} & a_{32} 
\end{array}\right]\!.](../Images/c3b4b3bc50ade70bc644e45b47543be8f5385517.png)

To specify the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), we need to specify the values of its six _entries_: ![a_{11}](./images/d0db9d50e4605b1bde6e4eb755078045c9a98583.png), ![a_{12}](./images/6a900889a0b7e32191a6331ff9b241d3cb748f17.png), ![a_{21}](./images/4361de7397aca15280c0d7c75e6e00ffd3527da8.png), ![a_{22}](./images/af0fe2a6e674b096b72652ca91583f6e5bdc5eb1.png), ![a_{31}](./images/76907e340f9f67cbdecc5f7a3fb5284ba6e45234.png), and ![a_{32}](./images/f65a984122f14652de55df6f1f15a261e7b469cc.png).

In the remainder of this chapter we’ll learn about the mathematical operations we can perform on vectors and matrices. Many problems in science, business, and technology can be described in terms of vectors and matrices, so it’s important you understand how to work with these math objects.

###[Context](./Front matter.md)

To illustrate what’s new about vectors and matrices, let’s begin by reviewing the properties of something more familiar: the set of real numbers ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). The basic operations for real numbers are:

-   Addition (denoted ![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png))
-   Subtraction, the inverse of addition (denoted ![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png))
-   Multiplication (denoted implicitly)
-   Division, the inverse of multiplication (denoted by fractions)

You’re familiar with these operations and know how to use them to evaluate math expressions and solve equations.

You should also be familiar with _functions_ that take real numbers as inputs and give real numbers as outputs, denoted ![f: \mathbb{R} \to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png). Recall that, by definition, the _inverse function_ ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) _undoes_ the effect of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png). If you are given ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) and want to find ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), you can use the inverse function as follows: ![f^{-1}\left( f(x) \right)=x](./images/bb6fb711c1a3876284d3499a107ff53fe1cb4d66.png). For example, the function ![f(x)=\ln(x)](./images/09638e2e7d7115cf6e5c0fe672bfbe1c54299bcd.png) has the inverse ![f^{-1}(x)=e^x](./images/8d8f795e3a2502e130389de30f1e5cfcdcba4225.png), and the inverse of ![g(x)=\sqrt{x}](./images/59dcae40ff87663758474befbc4873684131f5b8.png) is ![g^{-1}(x)=x^2](./images/cb9dce543e533aad64b691766ba643a6e5a3adf8.png).

Having reviewed the basic operations for real numbers ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png), let’s now introduce the basic operations for vectors ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) and matrices ![\mathbb{R}^{m\times n}](./images/e0107482dfd257822ffe0115cf94429a3196e6c5.png).

####[Vector operations](./Front matter.md)

The operations we can perform on vectors are:

-   Addition (denoted ![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png))
-   Subtraction, the inverse of addition (denoted ![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png))
-   Scaling (denoted implicitly)
-   Dot product (denoted ![\cdot\,](./images/4ec995749ae8ac4da25df2280a67757c0f5df1f2.png))
-   Cross product (denoted ![\times](./images/6c1ccbe8bb6958fb7f98fce646fdb82946c0ffa3.png))

We’ll discuss each of these vector operations in[Section 2.2](./Chapter 2_ Intro to linear algebra.md). Although you should already be familiar with vectors and vector operations from[Section 1.13](./Chapter 1_ Math fundamentals.md), it’s worth revisiting these concepts in greater depth, because vectors are the foundation of linear algebra.

####[Matrix operations](./Front matter.md)

The mathematical operations defined for matrices ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) are:

-   Addition (denoted ![A+B](./images/98dbfe515ef82fe730cf414fe5fb4c5aa4c8ad4e.png))
-   Subtraction, the inverse of addition (denoted ![A-B](./images/517b3bd0fb50424afa969b1bf242adabafaf4280.png))
-   Scaling by a constant ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) (denoted ![\alpha A](./images/96aaa16475ceb2a1a7ba99ada680745ac28abc61.png))
-   Matrix product (denoted ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png))
-   Matrix-vector product (denoted ![A\vec{v}](./images/7f9f917ef64cac1364cf488fd6017afa872a4ef3.png))
-   Matrix inverse (denoted ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png))
-   Trace (denoted ![\textrm{Tr}(A)](./images/5cac703e5885c95d0781a32376aa9d456b4dbeb2.png))
-   Determinant (denoted ![\textrm{det}(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png) or ![|A|](./images/f395085915c0b82f3f55aa5551b1676f28378881.png))

We’ll define each of these operations in[Section 2.3](./Chapter 2_ Intro to linear algebra.md), and we’ll learn about the various computational, geometric, and theoretical considerations associated with these matrix operations throughout the remainder of the book.

Let’s now examine one important matrix operation in closer detail: the matrix-vector product ![A\vec{x}](./images/1013646b0165a8b1f4e2bcaca5e29639cc92eae1.png).

####[Matrix-vector product](./Front matter.md)

Consider the matrix ![A \in \mathbb{R}^{m \times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) and the vector ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png). The matrix-vector product ![A\vec{x}](./images/1013646b0165a8b1f4e2bcaca5e29639cc92eae1.png) produces a linear combination of the columns of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) with coefficients ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png). For example, the product of a ![3 \times 2](./images/3247cd7695abad3cf4c4a69c536cd715d34202d1.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and a ![2 \times 1](./images/ff0d917829459a76eae0ac57cc13fac67fe68ba0.png) vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) results in a ![3 \times 1](./images/d64df9876c8c9a0d8d60681d95891dd8eaa05696.png) vector, which we’ll denote ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png):

![\begin{align*}
\vec{y} 
&= A \vec{x}, \\
\begin{bmatrix}
y_1 \\
y_2 \\
y_3
\end{bmatrix}
& = 
\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
a_{31} & a_{32} 
\end{bmatrix}
\!\!
\begin{bmatrix}
x_1 \\
x_2 
\end{bmatrix}
=
\!
\underbrace{
\begin{bmatrix}
x_1a_{11} + x_2a_{12} \\
x_1a_{21} + x_2a_{22} \\
x_1a_{31} + x_2a_{32} 
\end{bmatrix}
}_{\textrm{row picture}}
\!\!
=
\underbrace{
x_1\!
\begin{bmatrix}
a_{11} \\
a_{21} \\
a_{31} 
\end{bmatrix}
+
x_2\!
\begin{bmatrix}
a_{12} \\
a_{22} \\
a_{32} 
\end{bmatrix}
}_{\textrm{column picture}}\!\!.
\end{align*}](./images/f647f594c89aa5ff483ec631dec7e038a689bffc.png)

The key thing to observe in the above formula is the dual interpretation of the matrix-vector product ![A\vec{x}](./images/1013646b0165a8b1f4e2bcaca5e29639cc92eae1.png) in the “row picture” and in the “column picture.” In the row picture, we obtain the vector ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png) by computing the dot product of the vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) with each of the rows of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). In the column picture, we interpret the vector ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png) as ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) times the first column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) plus ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) times the second column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). In other words, ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png) is a linear combination of the columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). For example, if you want to obtain the linear combination consisting of three times the first column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and four times the second column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), you can multiply ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by the vector ![\vec{x}=\begin{bmatrix} 3 \\ 4 \end{bmatrix}](./images/128126d98452f23d72cc7a5b70b9857da52bd7ad.png).

####[Linear combinations as matrix products](./Front matter.md)

Consider some set of vectors ![\{ \vec{e}_1, \vec{e}_2 \}](./images/6e1323c539f5e800db738b0a9ebf8ab2ea19a7e1.png), and a third vector ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png) that is a _linear combination_ of the vectors ![\vec{e}_1](./images/bfb7cfed44bb7969a0f9b8df5e08e10a9a7a6c54.png) and ![\vec{e}_2](./images/dd508590ce90d8ecb415afab0c7d2f49f6eaea62.png):

![\vec{y} \; =  \; \alpha \vec{e}_1 \; + \; \beta \vec{e}_2.](./images/7adc8dae97163db614b2c9c5de39f103ed6dd94e.png)

The numbers ![\alpha, \beta \in \mathbb{R}](./images/d3db62d29b143a5aceb076e151fa6666f7ffaeaa.png) are the coefficients in this linear combination.

The matrix-vector product is defined expressly for the purpose of studying linear combinations. We can describe the linear combination ![\vec{y} =  \alpha \vec{e}_1 + \beta \vec{e}_2](./images/bd9c1adfc72bf0d2fb92707890f627f4bde225ed.png) as the following matrix-vector product:

![\vec{y} \; 
=  \; 
\begin{bmatrix}
| & | \\
\vec{e}_1 & \vec{e}_2 \\
| & | 
\end{bmatrix}\!
\begin{bmatrix}
\alpha \\
\beta
\end{bmatrix}\!.](./images/890b22b448ead548f5055221717ce5f921c609ef.png)

The matrix ![E](./images/80475983a19b0a9300f24e29f61de72089cf32a2.png) has ![\vec{e}_1](./images/bfb7cfed44bb7969a0f9b8df5e08e10a9a7a6c54.png) and ![\vec{e}_2](./images/dd508590ce90d8ecb415afab0c7d2f49f6eaea62.png) as columns. The dimensions of the matrix ![E](./images/80475983a19b0a9300f24e29f61de72089cf32a2.png) will be ![n \times 2](./images/2c81cdf00eedb0e1135b0928dd75aa30bf8a6262.png), where ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is the dimension of the vectors ![\vec{e}_1](./images/bfb7cfed44bb7969a0f9b8df5e08e10a9a7a6c54.png), ![\vec{e}_2](./images/dd508590ce90d8ecb415afab0c7d2f49f6eaea62.png), and ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png).

####[Linear transformations](./Front matter.md)

Dear readers, we’ve reached the key notion in the study of linear algebra. This is the crux. The essential fibre. The main idea. I know you’re ready to handle it because you’re familiar with functions of a real variable ![f:\mathbb{R} \to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png), and you just learned the definition of the matrix-vector product (in which the variables were chosen to subliminally remind you of the standard conventions for the function input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and the function output ![y=f(x)](./images/7b49e4a41f7dceef9f4e593fe8b4f6aa481e96cc.png)). Without further ado, I present to you the concept of a _linear transformation_.

The matrix-vector product corresponds to the abstract notion of a _linear transformation_, which is one of the key notions in the study of linear algebra. Multiplication by a matrix ![A \in \mathbb{R}^{m \times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) can be thought of as computing a linear transformation ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) that takes ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-vectors as inputs and produces ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-vectors as outputs:

![T_A:\mathbb{R}^n \to \mathbb{R}^m.](./images/9d2bfe26c3c1490c77f342d9e1942c5d5690a06d.png)

Instead of writing ![\vec{y} = T_A(\vec{x})](./images/7a9222cc87f50dad1aac3a48947c27d47b401edf.png) to denote the linear transformation ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) applied to the vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png), we can write ![\vec{y}=A\vec{x}](./images/06d912fc811b513e111fa6a0ea08753b468bd47a.png). Since the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) rows, the result of the matrix-vector product is an ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-vector. Applying the linear transformation ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) to the vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) corresponds to the product of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and the column vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png). We say ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) is _represented by_ the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

#####[Inverse](./Front matter.md)

When a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is square and invertible, there exists an inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) which _undoes_ the effect of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) to restore the original input vector:

![A^{-1}\!\left( A \vec{x} \right)=A^{-1}A\vec{x}=\vec{x}.](./images/e3f733da27f0abb664890447251c915199cdd01c.png)

Using the matrix inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) to undo the effects of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is analogous to using the inverse function ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) to undo the effects of the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png).

#####[Example 1](./Front matter.md)

Consider the linear transformation that multiplies the first components of input vectors by ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) and multiplies the second components by ![5](./images/0a99a11a8db1514f59b81b2211782467dd4a2e74.png), as described by the matrix

![A = 
\begin{bmatrix}
3 & 0 \\
0 & 5 
\end{bmatrix}\!, \; 
\qquad
A\vec{x}= 
\begin{bmatrix}
3 & 0 \\
0 & 5 
\end{bmatrix}
\!\!
\begin{bmatrix}
x_1 \\
x_2 
\end{bmatrix}
=
\begin{bmatrix}
3x_1 \\
5x_2 
\end{bmatrix} \!.](./images/4b07e2ef6ed0f667ae8edc484aaacc9dfea544f8.png)

The inverse of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is

![A^{-1} = 
\begin{bmatrix}
\frac{1}{3} & 0 \\
0 & \frac{1}{5}
\end{bmatrix}, \; 
\qquad
A^{-1}\!\left( A\vec{x} \right)=
\begin{bmatrix}
\frac{1}{3} & 0 \\
0 & \frac{1}{5}
\end{bmatrix}
\!\!
\begin{bmatrix}
3x_1 \\
5x_2 
\end{bmatrix}
=
\begin{bmatrix}
x_1 \\
x_2 
\end{bmatrix}
=\vec{x}.](./images/b6745de718de2ad2a139fc6b3195d8fa5bc845d8.png)

The inverse matrix multiplies the first component by ![\frac{1}{3}](./images/2e1382258077dc418e81971924dd9f4f09b9215a.png) and the second component by ![\frac{1}{5}](./images/48ce8fbb655ce90714638d4c3ceac1d9504db196.png), which effectively undoes what ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) did.

#####[Example 2](./Front matter.md)

Things get a little more complicated when matrices _mix_ the different components of the input vector, as in this example:

![B = 
\begin{bmatrix}
1 & 2 \\
0 & 3 
\end{bmatrix}, \; \; 
\text{which acts as } \; 
B\vec{x}= 
\begin{bmatrix}
1 & 2 \\
0 & 3 
\end{bmatrix}
\!\!
\begin{bmatrix}
x_1 \\
x_2 
\end{bmatrix}
=
\begin{bmatrix}
x_1 +2x_2 \\
\; \; 3x_2 
\end{bmatrix}\!.](./images/f1aa3c4482eb4a0a4432bc14c09cce4f7360a103.png)

Make sure you understand how to compute ![B\vec{x}](./images/9ededb86445a58ff8cf9d46b7084020a9169ef93.png) using both the _row picture_ and the _column picture_ of the matrix-vector product.

The inverse of the matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is the matrix

![B^{-1} = 
\begin{bmatrix}
1 & \frac{-2}{3} \\
0 & \frac{1}{3} 
\end{bmatrix}\!.](./images/19c5a12d47c2f1679ab54c21274abf3a38c8b57d.png)

Multiplication by the matrix ![B^{-1}](./images/3ce81de543e8cf47a1570a7cb200d40a7c3786c1.png) is the “undo action” for multiplication by ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![B^{-1}\!\left( B\vec{x} \right)
\!=\!
\begin{bmatrix}
1 & \frac{-2}{3} \\
0 & \frac{1}{3} 
\end{bmatrix}
\!\!
\begin{bmatrix}
1 & 2 \\
0 & 3 
\end{bmatrix}
\!\!
\begin{bmatrix}
x_1 \\
x_2 
\end{bmatrix}
\!=\!
\begin{bmatrix}
1 & \frac{-2}{3} \\
0 & \frac{1}{3} 
\end{bmatrix}
\!\!
\begin{bmatrix}
x_1 +2x_2 \\
3x_2 
\end{bmatrix}
\!=\!
\begin{bmatrix}
x_1 \\
x_2 
\end{bmatrix}
\!=\!
\vec{x}.](./images/267602694f60334ef91c1387f92af5ba09d6914e.png)

By definition, the inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) _undoes_ the effects of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). The cumulative effect of applying ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) after ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is the _identity matrix_ ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png), which has 1s on the diagonal and 0s everywhere else:

![A^{-1}A\vec{x}
=\mathbbm{1}\vec{x}
=\vec{x}
\qquad \Rightarrow
\qquad
A^{-1}A = \begin{bmatrix}
1 & 0 \\
0 & 1 
\end{bmatrix}= \mathbbm{1}.](./images/698843ac85f4b5d034f88b9a2d301f90702faf95.png)

Note that ![\mathbbm{1} \vec{x} = \vec{x}](./images/e7e60346943f796602c01390948d270638495865.png) for any vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png).

We’ll discuss matrix inverses and how to compute them in more detail later [Section 3.5](./Chapter 3_ Computational linear algebra.md)). For now, it’s important you know they exist.

###[An overview of linear algebra](./Front matter.md)

In the remainder of the book, we’ll learn all about the properties of vectors and matrices. Matrix-vector products play an important role in linear algebra because of their relation to _linear transformations_.

Functions are transformations from an input space (the domain) to an output space (the image). A linear transformation ![T:\mathbb{R}^n \to \mathbb{R}^m](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png) is a function that takes ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-vectors as inputs and produces ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-vectors as outputs. If the function ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is linear, the output ![\vec{y} = T(\vec{x})](./images/63cc1345c565faf1c7325b1be2d2570561baeff3.png) of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) applied to ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) can be computed as the matrix-vector product ![A_T\vec{x}](./images/7d210f3c302bcf0458e3ac0962e7ebc5551ba3ac.png), for some matrix ![A_T \in \mathbb{R}^{m \times n}](./images/fa0be7a4e415694bc1ec1d09e5590013b397e406.png). We say ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is _represented by_ the matrix ![A_T](./images/81f26977f2fbdfae28b4e545d3db4507c37524b8.png). Equivalently, every matrix ![A \in \mathbb{R}^{m \times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) corresponds to some linear transformation ![T_A:\mathbb{R}^n \to \mathbb{R}^m](./images/06e4499271b782cac11319dfbee8171a51788c83.png). Given the equivalence between matrices and linear transformations, we can reinterpret the statement “linear algebra is about vectors and matrices” by saying “linear algebra is about vectors and linear transformations.”

You can adapt your existing knowledge about functions to the world of linear transformations. The action of a function on a number is similar to the action of a linear transformation on a vector. The table below summarizes several useful correspondences between functions and linear transformations.

![\begin{align*}
\textrm{function } 
f:\mathbb{R}\to \mathbb{R}
& \; \Leftrightarrow \!\!\:
\begin{array}{l}
\textrm{linear transformation } 
T_A:\mathbb{R}^{n}\! \to \mathbb{R}^{m}		 \\
\textrm{represented by the matrix } A \in \mathbb{R}^{m \times n}
\end{array} \\
\textrm{input }  x\in \mathbb{R} 	
& \; \Leftrightarrow \;  
\textrm{input }  \vec{x} \in \mathbb{R}^n           \\
\textrm{output } f(x) \in \mathbb{R}
& \; \Leftrightarrow \; 
\textrm{output }      T_A(\vec{x}) = A\vec{x} \in \mathbb{R}^m \\
g\circ\! f \: (x) =  g(f(x))
& \; \Leftrightarrow \; 
T_B(T_A(\vec{x})) = BA \vec{x} \\
\textrm{function inverse } f^{-1}
& \; \Leftrightarrow \; 
\textrm{matrix inverse } A^{-1}												 	\\
\textrm{roots of } f
& \; \Leftrightarrow \; 
\textrm{kernel of } T_A  =  \textrm{null space of } A = \mathcal{N}(A)  			  	\\
\textrm{image of } f
& \; \Leftrightarrow \!
\begin{array}{l}
\textrm{image of } T_A =  \textrm{column space of } A  = \mathcal{C}(A) 		  
\end{array}
\end{align*}](./images/e0747bb248a8a973a2d740cfd58b4f4e6fb3d19f.png)

Table 2.1: Correspondences between functions and linear transformations.

This table of correspondences serves as a roadmap for the rest of the material in this book. You’ll notice the table introduces several new linear algebra concepts like _kernel_, _null space_, and _column space_, but not too many. You can totally do this!

Remember to always connect the new concepts of linear algebra to concepts you’re already familiar with. For example, the roots of a function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) are the set of inputs for which the function’s output is zero. Similarly, the _kernel_ of a linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is the set of inputs that ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) sends to the zero vector. The roots of a function ![f:\mathbb{R}\to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png) and the kernel of a linear transformation ![T_A:\mathbb{R}^{n}\! \to \mathbb{R}^{m}](./images/6141864b5e41764ab37d2f0f1060f93907c4c4d6.png) are essentially the same concept; we’re just upgrading functions to vector inputs.

In[Chapter 1](./Chapter 1_ Math fundamentals.md), I explained why functions are useful tools for modelling the real world. Well, linear algebra is the “vector upgrade” to your real-world modelling skills. With linear algebra you’ll be able to model complex relationships between multivariable inputs and multivariable outputs. To build modelling skills, you must first develop your geometric intuition about lines, planes, vectors, bases, linear transformations, vector spaces, vector subspaces, etc. It’s a lot of work, but the effort you invest will pay dividends.

###[Links](./Front matter.md)

\[ Linear algebra lecture series by Prof. Strang from MIT \]

[`http://bit.ly/1ayRcrj`](./1ayRcrj.md) (row and column picture example)

\[ A system of equations in the row picture and column picture \]

[`https://www.youtube.com/watch?v=uNKDw46_Ev4`](./watch_v=uNKDw46_Ev4.md)

###[Exercises](./Front matter.md)

E2.1 Find the inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) for the matrix ![A=\begin{bmatrix}7 & 0 \\ 0 & 2\end{bmatrix}](./images/e9b8f60e18adbd8b12257d401d5bd46eb091aaf6.png). Verify that ![A^{-1}(A\vec{v})=\vec{v}](./images/336ada65399d8b6873ac31f67309ba9f80084914.png) for any vector ![\vec{v} = \begin{bmatrix} v_1 \\ v_2\end{bmatrix}](./images/7efb248b0cf7dcf8b2b745e8f29a1dfd5af0b003.png).

E2.2 Given the matrices ![A=\begin{bmatrix}1 & 3 \\ 4 & 5\end{bmatrix}](./images/77a83a6b2a4c87acf43ecd65b430ca628df01351.png) and ![B=\begin{bmatrix} -1 & 0 \\ 3 & 3 \end{bmatrix}](./images/c31371c8a7b1df6c6181cf4048d4e00ccb4eef5a.png), and the vectors ![\vec{v}=\begin{bmatrix}1 \\  2\end{bmatrix}](./images/d822270da21c034c48100161296e44ca9a231ba8.png) and ![\vec{w}=\begin{bmatrix}-3 \\ -4\end{bmatrix}](./images/9771b04b21b0e5673c47050df7c4f2deba4e11e2.png), compute the following expressions.

1.  ![A\vec{v}](./images/7f9f917ef64cac1364cf488fd6017afa872a4ef3.png)
2.  ![B\vec{v}](./images/a748ca6930f2d1874dad3ba9adcedf511190c38c.png)
3.  ![A(B\vec{v})](./images/cfc86c4e6da343c72ade0fc717926a98215b1bbc.png)
4.  ![B(A\vec{v})](./images/76714694ff3fa5dad2770de67655c45738a2feee.png)
5.  ![A\vec{w}](./images/991b97f8ac6e91fe9653ddd243cf52d7013bbcb4.png)
6.  ![B\vec{w}](./images/d2bf9b726567b41d239ebc8ee14f0e4256d86385.png)

E2.3 Find the components ![v_1](./images/26bb4de90d49b42600706cf2e962fbcf50141c0c.png) and ![v_2](./images/b8ca706d019569604aca5b0c8b702542f0fd8e6b.png) of the vector ![\vec{v} =\begin{bmatrix}v_1 \\ v_2\end{bmatrix}](./images/7efb248b0cf7dcf8b2b745e8f29a1dfd5af0b003.png) so that ![E\vec{v} = 3 \vec{e}_2 - 2\vec{e}_1](./images/85155c0c7692e8caaa0e3b0285eb3f9d294902f3.png), where ![E](./images/80475983a19b0a9300f24e29f61de72089cf32a2.png) is the following matrix:

![E
=  \;
\begin{bmatrix}
| & | \\
\vec{e}_1 & \vec{e}_2 \\
| & | 
\end{bmatrix}\!.](./images/3d28ea5b8868d6be8fe6f67ec428244e245bbb40.png)

###[What next?](./Front matter.md)

We won’t bring geometry, vector spaces, algorithms, and the applications of linear algebra into the mix all at once. Instead, let’s start with the basics. Since linear algebra is about vectors and matrices, let’s define vectors and matrices precisely, and describe the math operations we can perform on them.

##[2.2 Vector operations](./Chapter 2_ Intro to linear algebra.md)

[Section 1.13](./Chapter 1_ Math fundamentals.md) introduced some basic notions about vectors. Understanding vectors is so important for linear algebra that it’s worth going beyond the rudimentary understanding of vectors as “directional quantities,” and so we took the time to describe vectors more abstractly—as math objects. With vectors defined, our next step is to specify their properties and the operations we can perform on vectors. This is what this section is all about.

###[Definitions](./Front matter.md)

Consider the vectors ![\vec{u}=(u_1,u_2,u_3)](./images/e0deb694534bdbb091b1e1bd24e2d5e6ed336ba3.png) and ![\vec{v}=(v_1,v_2,v_3)](./images/b5dec8d3fc9b621a78642f27092aa0374f269070.png), and an arbitrary constant ![\alpha \in \mathbb{R}](./images/291a1b884bfe1bd3bdd9e4811c426bcf4da094c5.png). Vector algebra can be summarized as the following operations:

-   Addition: ![\vec{u} + \vec{v}			\,\eqdef\, 	(u_1+v_1,u_2+v_2,u_3+v_3)](./images/43b85614f1e56d698fb31ccba60654d7571770cf.png)
-   Subtraction: ![\vec{u} - \vec{v}			\,\eqdef\, 	(u_1-v_1,u_2-v_2,u_3-v_3)](./images/dd404503dab9714c621c0c6d1743cb49bb36029f.png)
-   Scaling: ![\alpha \vec{u}				\,\eqdef\, 	(\alpha u_1,\alpha u_2,\alpha u_3)](./images/a91b735c7f70dbccc931cb96e683afd0c1d9af98.png)
-   Dot product: ![\vec{u} \cdot \vec{v}		\,\eqdef\, 	u_1v_1+u_2v_2+u_3v_3](./images/8c7b55e3f2373e1bb74b490f7234e20740467055.png)
-   Cross product: ![\vec{u} \times \vec{v}	\eqdef 	(u_2v_3-u_3v_2,\, u_3v_1-u_1v_3,\, u_1v_2-u_2v_1)](./images/8cea5103bbcd004203c6dd6c181599f7bca34802.png)
-   Length: ![\|\vec{u}\|            			\,\eqdef\, 	\sqrt{u_1^2+u_2^2+u_3^2}](./images/5381962503f9e01a89c7c3efac70e52ce23d3cc7.png)

In the next few pages we’ll see what these operations can do for us.

###[Notation](./Front matter.md)

The set of real numbers is denoted ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). An ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional real vector consists of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) real numbers slapped together in a bracket. We denote the set of three-dimensional vectors as ![\mathbb{R}^3 \eqdef ( \mathbb{R},  \mathbb{R},  \mathbb{R} )](./images/c8407ec8ed8805a456a4646f448d8127b00a03bf.png). Similarly, the set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional real vectors is denoted ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png).

When learning about new math operations, it’s important to keep track of the types of inputs and the types of outputs of each operation. In computer science, this information is called the _type signature_. For example, the type signature “![\textrm{op}: \mathbb{R} \to \mathbb{R}](./images/38724ac9513e05d60cb70984ad95f65a39ac1852.png)” tells us the math operation ![\textrm{op}](./images/239c1eeeaced30b912b5fef8b2e60c0882f91632.png) takes real numbers as inputs and produces real numbers as outputs. Certain operations take pairs of numbers as inputs, like addition for example: ![\textrm{add}(a,b)](./images/7cdebaa9e638f5f3aad501c3515d81f574ec3626.png) (usually denoted ![a+b](./images/1f747de8510cd5c6b556549a7eb6b39fef3d16ed.png)). The type signature for addition is “![\textrm{add}: \mathbb{R} \times \mathbb{R}  \to \mathbb{R}](./images/9e9b5125e76068ea7bf64882f3484eda885e0f31.png),” which tells us addition takes two real numbers as inputs and produces real numbers as outputs. The symbol “![\times](./images/6c1ccbe8bb6958fb7f98fce646fdb82946c0ffa3.png)” denotes the _Cartesian product_ of two sets. The Cartesian product ![\mathbb{R} \times \mathbb{R}](./images/44e924ec2c1da7f18ce2a6119180c4bb0441cfbf.png) contains all possible pairs of real numbers ![(a,b)](./images/98a5efa74a3f363e0ebadc4f086212f0b4a1a3de.png), where ![a \in \mathbb{R}](./images/f9423689df3e4691b543043380fd7c414443d30a.png) and ![b \in \mathbb{R}](./images/cd2825dcc283d4cc4b72f6f21bea41640a62673c.png). Note the math symbol “![\times](./images/6c1ccbe8bb6958fb7f98fce646fdb82946c0ffa3.png)” has two different meanings depending on the objects that surround it. The expression ![\vec{u} \times \vec{v}](./images/463be6a293fa8d06d54e2b035e190791aabbaa4c.png) denotes the cross product of vectors ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), while the expression ![A \times B](./images/514b6ebdf6c0896650d31f5d9a7a0508ea404779.png) denotes the Cartesian product of sets ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

The use of such formal math notation may seem complicated at first, but it’s very helpful when defining new math operations.

###[Addition and subtraction](./Front matter.md)

Addition and subtraction take pairs of vectors as inputs and produce vectors as outputs:

![+: \mathbb{R}^{n} \times \mathbb{R}^{n} \to \mathbb{R}^{n}
\qquad \textrm{and} \qquad
-: \mathbb{R}^{n} \times \mathbb{R}^{n} \to \mathbb{R}^{n}.](./images/1750670fdf1df79ba4cbe380f1ae4c3c5d4a0129.png)

Addition and subtraction are performed component-wise:

![\vec{w}=\vec{u} \pm \vec{v} \qquad  \; \; \Leftrightarrow \qquad \; \;  w_{i} = u_i \pm  v_i, 
\; \;  \forall i \in[1,\ldots,n].](../Images/831567c9b5e802295da876513f877a4a0a9ef293.png)

###[Scaling by a constant](./Front matter.md)

Scaling is an operation that takes a number and a vector as inputs and produces a vector output:

![\textrm{scalar-mult}: \mathbb{R} \times \mathbb{R}^{n} \; \to \; \mathbb{R}^{n}.](./images/f9876683f3fb764eaff8a51f8e0c943a89fa09d3.png)

There is no symbol to denote scalar multiplication—we just write the scale factor in front of the vector and the multiplication is implicit.

Multiplying the vector ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) by the scale factor ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) is equivalent to multiplying each component of the vector by ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png):

![\vec{w}=\alpha\vec{u} \qquad   \Leftrightarrow \qquad  w_{i} = \alpha u_i.](./images/ad0e0690d894e88dd3346ec306d8da1114bb0389.png)

For example, choosing ![\alpha=2](./images/7dd638894d72694f0f68a3abb6bc5fc06e3307f6.png), we obtain the vector ![\vec{w}=2\vec{u}](./images/9bbdd16131dc19a331dbc9b996f57fef0a660975.png), which is two times longer than the vector ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png):

![\vec{w}=(w_1,w_2,w_3) = (2u_1,2u_2,2u_3) = 2(u_1,u_2,u_3) = 2\vec{u}.](./images/9128b938afc90bbd3721ade6555846bb65d7e501.png)

![vector_scaled_by_2](./images/vector_scaled_by_2.png)

Figure 2.1: Vectors ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png) and ![\vec{w}](./images/8605b88df3c2d74846ee2ea09257899f3d121a33.png) are related by the equation ![\vec{w}=2\vec{u}](./images/bcc4e08aa246526497ffa142b056ca3a89a1889d.png).

###[Vector products](./Front matter.md)

We’ll now define the _dot product_ and the _cross product_: two geometric operations useful for working with three-dimensional vectors.

####[Dot product](./Front matter.md)

The _dot product_ takes two vectors as inputs and produces a single, real number as an output:

![\cdot : \mathbb{R}^3 \times \mathbb{R}^3 \quad \to \quad \mathbb{R}.](./images/b6c6c766e426e61bf2798535af4afbd5f9581227.png)

The dot product between the vector ![\vec{v}=(v_x, v_y, v_z)](./images/87c95a73f484d93d31b33d580a161c30cea133fe.png) and the vector ![\vec{w}=(w_x, w_y, w_z)](./images/2a1c8219f3450d817dd8664b8e83f7228ff37de6.png) can be computed using either the algebraic formula,

![\vec{v}\cdot\vec{w}		\; = \; 		v_xw_x+v_yw_y+v_zw_z,](./images/cf870b9f468f84fa6108869e1aa51e4cb20e066c.png)

or the geometric formula,

![\vec{v}\cdot\vec{w} 		\; = \; 		\|\vec{v}\|\|\vec{w}\|\cos(\varphi),	\qquad \; \;](./images/06d2b6dc5f9cd275c2a654eb4a4e56183fe70533.png)

where ![\varphi](./images/849d84e8f75f3e71cd63fca138605f13f8a7f94a.png) is the angle between the two vectors. Note the value of the dot product depends on the vectors’ lengths and the cosine of the angle between them.

The dot product is the key tool for calculating vector projections, vector decompositions, and determining orthogonality. The name _dot product_ comes from the symbol used to denote it. It is also known as the _scalar product_, since the result of the dot product is a scalar number—a number that does not change when the basis changes. The dot product is also sometimes called the _inner product_.

We can combine the algebraic and the geometric formulas for the dot product to obtain the formula,

![\begin{align*}
\cos(\varphi)
= \frac{ \vec{v}\cdot\vec{w} }{  \|\vec{v}\|\|\vec{w}\| } 
= \frac{ v_xw_x+v_yw_y+v_zw_z }{  \|\vec{v}\|\|\vec{w}\| }
\quad
\textrm{and}
\quad
\varphi  = \cos^{-1}\!\left( \cos(\varphi) \right)\!.
\end{align*}](./images/39f8f54631f1c12cf2d129516cd2f9dd6f84c73f.png)

This formula makes it possible to find the angle between two vectors if we know their components.

The geometric factor ![\cos(\varphi)](./images/b7ac3fb7e090bd3075854fb5fb0e80a257e612cd.png) depends on the relative orientation of the two vectors as follows:

-   If the vectors point in the same direction, then ![\cos(\varphi)=\cos(0^\circ) = 1](./images/6c066feaf328f10609952514b2151b4e505b1c04.png), so ![\vec{v}\cdot\vec{w}=\|\vec{v}\|\|\vec{w}\|](./images/ee0ae2c2b46c215cc5ddbc5ad61644427550c1be.png).
-   If the vectors are perpendicular to each other, then ![\cos(\varphi)=\cos(90^\circ) = 0](./images/c100bf6065c25700e5363ab0a14a7d67736aed1c.png), so ![\vec{v}\cdot\vec{w}=0](./images/903092627363cf2a56160060b0d0ca857d39ca79.png).
-   If the vectors point in exactly opposite directions, then ![\cos(\varphi)=\cos(180^\circ) = -1](./images/fdbdda2de8abd104989bf5ffa3883cb802ef1b13.png), so ![\vec{v}\cdot\vec{w}=-\|\vec{v}\|\|\vec{w}\|](./images/dd036ff36d157e7119c7523832a92eb94733d4a3.png).

The dot product is defined for vectors of any dimension; as long as two vectors are defined with respect to the same basis, we can compute the dot product between them.

###[Cross product](./Front matter.md)

The _cross product_ takes two vectors as inputs and produces another vector as the output:

![\times : \mathbb{R}^3 \times \mathbb{R}^3 \quad \to \quad \mathbb{R}^3.](./images/b0054e335f81525a84107a9bc7b888d023369f3a.png)

The cross product of two vectors is perpendicular to both vectors:

![\vec{v}\times\vec{w} = \{ \text{ a vector perpendicular to both } \vec{v} \text{ and } \vec{w} \; \}  \quad \in \mathbb{R}^3.](./images/84b85411be5f6e09742c29464e677268e96446c8.png)

If you take the cross product of one vector pointing in the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-direction with another vector pointing in the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-direction, the result will be a vector in the ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-direction: ![\hat{\imath} \times \hat{\jmath} = \hat{k}](./images/7dba8d9c3333cf1eec3364bfdd935bb739e5988a.png). The name _cross product_ comes from the symbol used to denote it. It is also sometimes called the _vector product_, since the output of this operation is a vector.

The cross products of individual basis elements are defined as

![\hat{\imath}\times\hat{\jmath} =\hat{k}, \qquad
\hat{\jmath}\times\hat{k} =\hat{\imath},  \qquad
\hat{k}\times \hat{\imath}= \hat{\jmath}.](./images/ef73f8ac80b206258c2d55049ceafabc8c8271ed.png)

Look at[Figure 1.55](./Chapter 1_ Math fundamentals.md) on page 1.55 and imagine the vectors ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png), ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png), and ![\hat{k}](./images/1427cff1bf4c402fb2a07d3b871082761b7c2102.png) pointing along each axis. Try to visualize the three equations above.

The cross product is _anticommutative_, which means swapping the order of the inputs introduces a negative sign in the output:

![\hat{\jmath}\times  \hat{\imath} =-\hat{k}, \qquad
\hat{k}\times\hat{\jmath} =-\hat{\imath}, \qquad
\hat{\imath}\times \hat{k} = -\hat{\jmath}.](./images/ce84d6a25731c8b7f4f2713a8a76f78e25a42179.png)

It’s likely that, until now, the products you’ve seen in math have been _commutative_, which means the order of the inputs doesn’t matter. The product of two numbers is commutative ![ab=ba](./images/f3536b76e86db67948a746785d54445f12d5b163.png), and the dot product of two vectors is commutative ![\vec{u}\cdot\vec{v}=\vec{v}\cdot\vec{u}](./images/0ed1ae8625838f68ba8c790ea56977b3726058b7.png), but the cross product of two vectors is _anti_commutative ![\vec{v}\times \vec{w} = - \vec{w}\times \vec{v}](./images/d58a458c8117cdbd6e5b3ad281b14288a93490f1.png).

Given two vectors ![\vec{a}=a_x\hat{\imath} + a_y\hat{\jmath} +  a_z\hat{k}](./images/1e72a67ad1e61caddb689ad212d48188687376a1.png) and ![\vec{b}=b_x\hat{\imath} + b_y\hat{\jmath} +  b_z\hat{k}](./images/49a495733fd4462f7243937388ed33c0bb49e043.png), their cross product is calculated as

![\vec{a}\times\vec{b}
\; \; = \; \; (a_yb_z - a_zb_y)\hat{\imath} + (a_zb_x - a_xb_z)\hat{\jmath} + (a_xb_y - a_yb_x)\hat{k}.](./images/51499daea658d7c807529f216ca4ed3ab8dd41ce.png)

Computing the cross product requires a specific combination of multiplications and subtractions of the input vectors’ components. The result of this combination is the vector ![\vec{a}\times\vec{b}](./images/6fe2ec6465ae5fcf17a8b308121e2e5f2aae1c17.png) which is perpendicular to both ![\vec{a}](./images/f0090c6a4c3d631f857e7e214dac1503513e48fc.png) and ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png).

The length of the cross product of two vectors is proportional to the sine of the angle between the two vectors:

![\|\vec{a}\times\vec{b}\|=\|\vec{a}\|\|\vec{b}\|\sin(\varphi).](./images/9f34825eda4a8ac9793fb1da61d523a099ebd4a4.png)

####[The right-hand rule](./Front matter.md)

Consider the plane formed by the vectors ![\vec{a}](./images/f0090c6a4c3d631f857e7e214dac1503513e48fc.png) and ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png). There are actually _two_ vectors perpendicular to this plane: one above the plane and one below the plane. We use the _right-hand rule_ to figure out which of these vectors corresponds to the cross product ![\vec{a} \times \vec{b}](./images/6fe2ec6465ae5fcf17a8b308121e2e5f2aae1c17.png).

Make a fist with your right hand and then extend your thumb, first finger, and middle finger. When your index finger points in the same direction as the vector ![\vec{a}](./images/f0090c6a4c3d631f857e7e214dac1503513e48fc.png) and your middle finger points in the direction of ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png), your thumb will point in the direction of ![\vec{a} \times \vec{b}](./images/6fe2ec6465ae5fcf17a8b308121e2e5f2aae1c17.png). The relationship encoded in the right-hand rule matches the relationship between the standard basis vectors: ![\hat{\imath} \times \hat{\jmath} = \hat{k}](./images/7dba8d9c3333cf1eec3364bfdd935bb739e5988a.png).

![Right_hand_rule_cross_product](./images/Right_hand_rule_cross_product.png)

Figure 2.2: Using the right-hand rule to determine the direction of the cross product ![\vec{a}\times\vec{b}](./images/7fcb7dee1c355ef23266886162cb26e6b5191cc3.png) based on directions of ![\vec{a}](./images/abd226c6ebc9e4ce0859eae53c463d456351f166.png) and ![\vec{b}](./images/9de6fd92ad217df8b49690b95fe00acb5956bf59.png).

###[Links](./Front matter.md)

\[ Nice illustrations of the cross product \]

[`http://1ucasvb.tumblr.com/post/76812811092/`](./76812811092.md)

[https://www.youtube.com/watch?v=eu6i7WJeinw](./watch_v=eu6i7WJeinw.md)

###[Length of a vector](./Front matter.md)

The length of a vector is a nonnegative number that describes the extent of the vector in space, and is sometimes referred to as the vector’s _magnitude_ or the _norm_. We express the notion of length as an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional extension of Pythagoras’ formula: it is the length of the hypotenuse in a right-angle triangle, given the lengths of its two sides, just applied to ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) dimensions. The length of a vector ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) is denoted ![\|\vec{u}\|](./images/2a30f67a4db4e2dd1329502a49c113cc19154c63.png) or ![\|\vec{u}\|_2](./images/3713af2e691851cc550703a4ba0720002be37e5c.png) or sometimes simply ![u](./images/82a971ebc8ceb9b9a22bd63d00ce51c1323a931d.png).

The _length_ of the vector ![\vec{u} \in \mathbb{R}^n](./images/c16f7b55ead66844393160cdd9dfe4a24b3b44ee.png) is computed as follows:

![\|\vec{u}\|  = \sqrt{u_1^2+u_2^2+ \cdots + u_n^2 } = \sqrt{ \vec{u} \cdot \vec{u} }.](./images/a3333c9c7d808e8c45be9d04898ec1503ce3ffd5.png)

There are many mathematical concepts that correspond to the intuitive notion of length. The formula above computes the _Euclidian length_ (or _Euclidian norm_) of the vector. Another name for the Euclidian length is the ![\ell^2](./images/7fad99f1385aea13b4db8c4cfa93bef46e3eb4e0.png)\-norm (pronounced _ell-two norm[2](./Front matter.md)).

Note a vector’s length can also be computed as the square root of the dot product of the vector with itself: ![\|\vec{v}\| = \sqrt{  \vec{v} \cdot \vec{v} }](./images/0d134125afc497e97a27eba5d9c67c6208984818.png). Indeed, there is a deep mathematical connection between norms and inner products.

###[Unit vectors](./Front matter.md)

A _unit vector_ is a vector that has length one. Given a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) of any length, we can build a unit vector in the same direction by dividing ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) by its own length:

![\hat{v} = \frac{\vec{v}}{ \|\vec{v}\| }\,.](./images/16749bdd4094e5b72e4c46462924d0923dd5b15c.png)

Unit vectors are useful in many contexts. For instance, when we want to specify a direction in space, we use a unit vector in that direction.

###[Projection](./Front matter.md)

Pop-quiz time! Can you remember some essentials from[Section 1.13](./Chapter 1_ Math fundamentals.md)? Suppose I give you a direction ![\hat{d}](./images/3585af26e87e5f04540c12eeeae6a021a6063ad1.png) and some vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), and ask you how much of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is in the direction ![\hat{d}](./images/3585af26e87e5f04540c12eeeae6a021a6063ad1.png)? To find the answer, you must compute the dot product:

![v_d	= \hat{d} \cdot \vec{v}
=  \| \hat{d} \| \|\vec{v} \| \cos\theta
= 1\|\vec{v} \| \cos\theta,](./images/f2bf102728dd71e9334ab0bc241d2a21fda6dd0e.png)

where ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is the angle between ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\hat{d}](./images/3585af26e87e5f04540c12eeeae6a021a6063ad1.png). This formula is used in physics to compute ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-components of forces: ![F_x = \vec{F}\cdot \hat{\imath} = \|\vec{F}\|\cos\theta](./images/1dfe16f84df09149165bda26b8d518b7213de5a1.png).

Define the _projection_ of a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in the ![\hat{d}](./images/3585af26e87e5f04540c12eeeae6a021a6063ad1.png) direction as follows:

![\Pi_{\hat{d}}(\vec{v}) = v_d \hat{d} = (\hat{d} \cdot \vec{v})\hat{d}.](./images/f58d9a9c8d3acb67f983529a121c800e5ab29c69.png)

If the direction is specified by a vector ![\vec{d}](./images/7905c6edce4836df7858602b11fd751a55b4b8f0.png) that doesn’t have length one, then the projection formula becomes

![\Pi_{\vec{d}}(\vec{v}) = \left(\frac{ \vec{d} \cdot \vec{v} }{ \|\vec{d}\|^2 } \right) \vec{d}.](./images/14e4ee92ebc713e72fef08a2d5cb909f8fe4c743.png)

Division by the length squared transforms the two appearances of the vector ![\vec{d}](./images/7905c6edce4836df7858602b11fd751a55b4b8f0.png) into the unit vectors ![\hat{d}](./images/3585af26e87e5f04540c12eeeae6a021a6063ad1.png) needed for the projection formula:

![\Pi_{\hat{d}}(\vec{v}) 
\; = \; \underbrace{ (\vec{v}\cdot\hat{d})}_{\|\vec{v}\|\cos\theta} \hat{d}
\; = \; \left(\vec{v}\cdot \frac{\vec{d}}{\|\vec{d}\|}\right) \frac{\vec{d}}{\|\vec{d}\|}
\; = \; \left(\frac{\vec{v}\cdot\vec{d}}{\|\vec{d}\|^2}\right)\vec{d}
\; = \;  \Pi_{\vec{d}}(\vec{v}).](./images/ff7479da85f8a1746dd9daf0fc1348de810af73f.png)

Remember these projection formulas well because we’ll need them later: when computing projections onto planes [Section 4.2.4](./Chapter 4_ Geometric aspects of linear algebra.md)), when computing vector coordinates [Section 4.3](./Chapter 4_ Geometric aspects of linear algebra.md)), and when describing the change-of-basis operation [Section 5.3](./Chapter 5_ Linear transformations.md)).

###[Discussion](./Front matter.md)

This section elaborated on the properties of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vectors, which are ordered tuples (lists) of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) components. It’s important to think of vectors as whole mathematical objects, rather than as components. Although vector operations boil down to manipulations of their components, vectors are most useful (and best understood) when you think of them as whole objects that have components, rather than focussing on their components.

###[Links](./Front matter.md)

\[ Nice illustration of the cross product \]

[`http://1ucasvb.tumblr.com/post/76812811092/`](./76812811092.md)

\[ Vectors explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=fNk_zzaMoSs`](./watch_v=fNk_zzaMoSs.md)

\[ Cross products explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=eu6i7WJeinw`](./watch_v=eu6i7WJeinw.md)

###[Exercises](./Front matter.md)

E2.4 Given the vectors ![\vec{u}=(1,1,0)](./images/62ee1cec3a3a03e4c6507b24c6e2cb08e31a3336.png) and ![\vec{v}=(0,0,3)](./images/a7bbec31a45d031ae63fffa04f3cc9a8b3779e40.png), compute the following vector expressions:

**a)** ![\vec{u}+\vec{v}](./images/3c2311f5d52e6932259fd54b71fc2017a077c2ba.png) **b)** ![\vec{u}-\vec{v}](./images/564b261b672e79034ab1b4003fc6e6b57eb808ac.png) **c)** ![3\vec{u}+\vec{v}](./images/17dcc3b8f31cc626048fd4b5bfc3e66bbbfac14e.png) **d)** ![\| \vec{u} \|](./images/2a30f67a4db4e2dd1329502a49c113cc19154c63.png)

E2.5 Given ![\vec{v}= (1, 2, 3)](./images/d11523070a2a18de48c687d12d5085f1b839ebe1.png) and ![\vec{w}=(0, 1, 1)](./images/097def6278517eb33a70d540ebec4f428867ae14.png), compute the following vector products: **a)** ![\vec{v} \cdot \vec{w}](./images/1a667961b87b806eb8f08f5f147739a16b1a979b.png); **b)** ![\vec{v} \times \vec{w}](./images/fe985097320b472712aa551f17c8816b69fb6c4f.png); **c)** ![\vec{w} \times \vec{v}](./images/541079f87914b3f91873f585d38868257ac9a469.png); **d)** ![\vec{w} \times \vec{w}](./images/e717caf0ecb3fefab26a458aa8c305ac0bf8fab7.png).

E2.6 For each of the following vectors, ![\vec{v}_1 = 10\angle 10^{\circ}](./images/da10ab1234294513937d72416d95797b9dc85d34.png), ![\vec{v}_2 = 10\angle 30^{\circ}](./images/645421ca6cebd80c6a6dea778461a8da81cf583f.png), ![\vec{v}_3 = 10\angle 60^{\circ}](./images/71ee6c3a8fdda64efdb7198d9f8e31784a941d29.png), ![\vec{v}_4 = 10\angle 120^{\circ}](./images/80dd18397e8a2a1a9a1d35e610480d6a459c3f2d.png), complete the following tasks:

1.  Draw the vector in a Cartesian plane.
2.  Compute the vector’s ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinates.
3.  Compute the projection of the vector in the direction ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png). Your answer should be a vector quantity.
4.  Compute the projection of the vector in the direction ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png).
5.  Compute the projection of the vector in the direction ![\vec{d}=(1,1)](./images/8e4dea27f630d1509b3cc57f7132565b9b3bbe10.png), and find the length of the projection.

Recall the formula for the projection of the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in the direction ![\vec{d}](./images/7905c6edce4836df7858602b11fd751a55b4b8f0.png) is defined as ![\Pi_{\vec{d}}(\vec{v}) = \Big(\frac{ \vec{d}\,\cdot \, \vec{v} }{ \|\vec{d}\|^2 } \Big) \vec{d}](./images/dc3922d685ce291aff38862469d24b499e5358f7.png).

##[2.3 Matrix operations](./Chapter 2_ Intro to linear algebra.md)

A matrix is a two-dimensional array (a table) of numbers. Consider the ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) by ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) matrix ![A \in \mathbb{R}^{m\times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png). We denote the matrix as a whole ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and refer to its individual entries as ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png), where ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png) is the number in the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th row and the ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). What are the mathematical operations we can perform on this matrix?

###[Addition and subtraction](./Front matter.md)

The matrix addition and subtraction operations take pairs of matrices as inputs and produce matrices as outputs:

![+: \mathbb{R}^{m \times n} \times \mathbb{R}^{m \times n} \to \mathbb{R}^{m \times n} \quad \textrm{and} \quad 
-: \mathbb{R}^{m \times n} \times \mathbb{R}^{m \times n} \to \mathbb{R}^{m \times n}.](./images/1adb8cf436d98d9527d195ff4f460267a39f754a.png)

Addition and subtraction are performed as follows:

![C = A \pm B
\quad \Leftrightarrow \quad
c_{ij} = a_{ij} \pm b_{ij}, \; \forall i \in[1,\ldots,m], j\in[1,\ldots,n].](../Images/66d32033b19b4a6ac81d8a14457690b863117aad.png)

For example, addition for two ![3\times2](./images/3247cd7695abad3cf4c4a69c536cd715d34202d1.png) matrices is expressed as

![\begin{bmatrix}
a_{11} 		& a_{12}	 \\
a_{21} 		& a_{22}	 \\
a_{31} 		& a_{32}	
\end{bmatrix}
+
\begin{bmatrix}
b_{11} 		& b_{12}	 \\
b_{21} 		& b_{22}	 \\
b_{31} 		& b_{32}	
\end{bmatrix}
=
\begin{bmatrix}
a_{11}+b_{11} 		& a_{12}+b_{12}	 \\
a_{21}+b_{21} 		& a_{22}+b_{22}	 \\
a_{31}+b_{31} 		& a_{32}+b_{32}	
\end{bmatrix}\!\!.](./images/2c636c09c08d28bc48fce242e2d144dda5870fd2.png)

Matrices must have the same dimensions to be added or subtracted.

###[Multiplication by a constant](./Front matter.md)

Recall that _scaling_ is another word for multiplication by a constant. Given a number ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), we can _scale_ ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) as follows:

![\alpha A
=
\alpha
\begin{bmatrix}
a_{11} 		& a_{12}	 \\
a_{21} 		& a_{22}	 \\
a_{31} 		& a_{32}
\end{bmatrix}
=
\begin{bmatrix}
\alpha a_{11} 		& \alpha a_{12}	 \\
\alpha a_{21} 		& \alpha a_{22}	 \\
\alpha a_{31} 		& \alpha a_{32}	
\end{bmatrix}\!\!.](./images/40b9eb9c8b2e94eaf15ac5036ce410f346071b76.png)

###[Matrix-vector multiplication](./Front matter.md)

The result of the matrix-vector product between a matrix ![A \in \mathbb{R}^{m\times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) and a vector ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png) is an ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-dimensional vector:

![\textrm{matrix-vector product} : \mathbb{R}^{m \times n}  \times \mathbb{R}^{n}  \to \mathbb{R}^{m}.](./images/be098b0e4f6324ef7b0929cdbb398e3ad1e72539.png)

The formula for the matrix-vector product is

![\vec{w} = A\vec{v}
\qquad \Leftrightarrow  \qquad
w_{i} = \sum_{j=1}^n a_{ij}v_{j}, \quad \forall i \in[1,\ldots,m].](../Images/e283e255ff4f8d6c4d8fef4ef8b9ba8025635ad7.png)

For example, the product of a ![3 \times 2](./images/3247cd7695abad3cf4c4a69c536cd715d34202d1.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and the ![2 \times 1](./images/ff0d917829459a76eae0ac57cc13fac67fe68ba0.png) column vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) results in a ![3 \times 1](./images/d64df9876c8c9a0d8d60681d95891dd8eaa05696.png) vector:

![\begin{align*}
A\vec{v} =
\begin{bmatrix}
a_{11} 		& a_{12}	 \\
a_{21} 		& a_{22}	 \\
a_{31} 		& a_{32}	
\end{bmatrix}\!\!
\begin{bmatrix}
v_{1} 	\\
v_{2} 
\end{bmatrix}
& = 	
\underbrace{		
v_1\!\!
\begin{bmatrix}
a_{11} \\
a_{21} \\
a_{31} 
\end{bmatrix}
+
v_2\!\!
\begin{bmatrix}
a_{12} \\
a_{22} \\
a_{32} 
\end{bmatrix} 							 
}_{\textrm{column picture}}  						 \\
&=
\left.
\begin{bmatrix}
(a_{11}, a_{12}) \cdot \vec{v} \\
(a_{21}, a_{22}) \cdot \vec{v} \\
(a_{31}, a_{32}) \cdot \vec{v}  
\end{bmatrix} 
\;  \; \right\} \textrm{\scriptsize row picture} 			\\
&=
\begin{bmatrix}
a_{11}v_{1} 		+ a_{12}v_{2}		\\
a_{21}v_1 		+ a_{22}v_2		 \\
a_{31}v_1 		+ a_{32}v_2	
\end{bmatrix}
\quad \in \mathbb{R}^{3 \times 1}.
\end{align*}](./images/d9b061527732c29a23e7aeac5bd925082095288e.png)

Note the two equivalent ways to understand the matrix-vector product: the _column picture_ and the _row picture_. In the column picture, the multiplication of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) produces a **linear combination of the columns of the matrix**. In the row picture, multiplication of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) produces a column vector with components equal to the **dot products of the rows of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) with the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png).**

###[Matrix-matrix multiplication](./Front matter.md)

The matrix product ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png) of matrices ![A \in \mathbb{R}^{m\times \ell}](./images/b0ede296919e4c3a24753989c4314f3fb0de0a48.png) and ![B \in \mathbb{R}^{\ell \times n}](./images/d742164890dd4391e9b9a7e0b490e133edb87633.png) results in an ![m\times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrix:

![\textrm{matrix-product} : \mathbb{R}^{m \times \ell}  \times\mathbb{R}^{\ell \times n}  \to \mathbb{R}^{m \times n}.](./images/ffd842976961563592dc8c8c3ba1489fe3993deb.png)

The formula for matrix multiplication computes the dot product between each row of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and each column of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![C = AB
\qquad \Leftrightarrow  \qquad
c_{ij} = \sum_{k=1}^\ell a_{ik}b_{kj}, \forall i \in[1,\ldots,m],j \in[1,\ldots,n].](../Images/d0e6619f25e929299db9cc7d409a3eff6af97f8e.png)

![\begin{bmatrix}
a_{11} 		&  a_{12}	 \\
a_{21} 		&  a_{22}	 \\
a_{31} 		&  a_{32}	 
\end{bmatrix}
\!\!
\begin{bmatrix}
b_{11} 		&  b_{12}	 \\
b_{21} 		&  b_{22}	 \\
\end{bmatrix}
=
\begin{bmatrix}
a_{11}b_{11} + a_{12}b_{21} 	&  a_{11}b_{12} + a_{12}b_{22} 	 \\
a_{21}b_{11} + a_{22}b_{21} 	&  a_{21}b_{12} + a_{22}b_{22} 	 \\
a_{31}b_{11} + a_{32}b_{21} 	&  a_{31}b_{12} + a_{32}b_{22} 	 
\end{bmatrix} \;  \in \mathbb{R}^{3 \times 2}.](./images/871b5838f9be0d3465311e16033289556394e025.png)

###[Transpose](./Front matter.md)

The transpose matrix ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png) is defined by the formula ![a_{ij}^\sfT=a_{ji}](./images/09f6eec02de68bfd7396c76945c7d4a78b5fb918.png). We obtain the transpose by “flipping” the matrix through its diagonal:

![\phantom{|}^\sfT : \mathbb{R}^{m \times n}  \to \mathbb{R}^{n \times m}](./images/378f2c97427327afb19705bd408813a6ff7e1997.png)

![\begin{bmatrix}
\alpha_1 &  \alpha_2 &  \alpha_3 \\
\beta_1  &  \beta_2  &  \beta_3 
\end{bmatrix}^\sfT
=
\begin{bmatrix}
\alpha_1  & \beta_1 \\
\alpha_2  &  \beta_2 \\
\alpha_3  &  \beta_3 
\end{bmatrix}\!.](./images/33eb3bef81eb8deb066f3ea04be01d82f04cc93e.png)

Note that entries on the diagonal of the matrix do not change when we apply the transpose operation.

####[Properties of the transpose operation](./Front matter.md)

-   ![(A+B)^\sfT 	= A^\sfT + B^\sfT](./images/ad493543bbcaa6d4f58de3486d1ac70001a3d623.png)
-   ![(AB)^\sfT 	= B^\sfT A^\sfT](./images/c898f120bdbcebcebf1f51640d922b0861c7191e.png)
-   ![(ABC)^\sfT    	= C^\sfT B^\sfT A^\sfT](./images/0dfdc43f7badcdff117edf8020bce3a74e1bc72c.png)
-   ![(A^\sfT)^{-1} 	= (A^{-1})^\sfT](./images/41402ce909520d7bb0f8d177b780c20cfa161b92.png)

###[Vectors as matrices](./Front matter.md)

A vector is a special type of matrix. You can treat a vector ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png) either as a _column vector_ (![n\times 1](./images/3090ba3f3c80de1e80bc520aaec116200eb116f6.png) matrix) or as a _row vector_ (![1 \times n](./images/d470d6249220dd5f738c22ef1592c3a0bc5bd50e.png) matrix).

####[Inner product](./Front matter.md)

Recall the definition of the _dot product_ or _inner product_ for vectors:

![\cdot : \mathbb{R}^{n} \times \mathbb{R}^{n} \to \mathbb{R}
\qquad
\Leftrightarrow
\qquad
\vec{u}\cdot\vec{v} =  \sum_{i=1}^n \!u_iv_i.](./images/9dedda4ab0abc0de181ddc496b606809571873b1.png)

If we think of vectors as _column_ vectors, we can write the dot product in terms of the matrix transpose operation ![^\sfT](./images/a462348fa44a14519bb7f3a98207adcc6cb061da.png) and the standard rules of matrix multiplication:

![\vec{u}\cdot \vec{v} 
=
\vec{u}^\sfT\vec{v}
=
\begin{bmatrix}
u_{1} 		& 	u_{2}	&  u_{3}
\end{bmatrix}
\!\!
\begin{bmatrix}
v_1 \\
v_2 \\
v_3 
\end{bmatrix}
=
u_1v_1 + u_2v_2 + u_3v_3.](./images/4588a46fab19a041826f6873156b6d509798c0db.png)

The dot product for vectors is thus a special case of matrix multiplication. Alternatively, we could say that matrix multiplication is defined in terms of the dot product.

####[Outer product](./Front matter.md)

Consider again two _column_ vectors ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) (![n\times 1](./images/3090ba3f3c80de1e80bc520aaec116200eb116f6.png) matrices). We obtain the inner product by applying the transpose to the _first_ vector in the product: ![\vec{u}^\sfT\vec{v} = \vec{u}\cdot \vec{v}](./images/e6116e836c533d8aeca9cc7c4ab0f1990059418a.png). Instead, if we apply the transpose to the _second_ vector, we’ll obtain the _outer product_ of ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). The outer product operation takes pairs of vectors as inputs and produces matrices as outputs:

![\textrm{outer-product} : \mathbb{R}^{n} \times \mathbb{R}^{n} \to \mathbb{R}^{n \times n}.](./images/4359b18321b4429f0357a6b938e716480f0cfbe6.png)

For example, the outer product of two vectors in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) is

![\vec{u}\vec{v}^\sfT
=
\begin{bmatrix}
u_1 \\
u_2 \\
u_3 
\end{bmatrix}
\!\!
\begin{bmatrix}
v_{1} 		& 	v_{2}	&  v_{3}
\end{bmatrix}
=
\begin{bmatrix}
u_1v_1 & u_1v_2 & u_1v_3 \\
u_2v_1 & u_2v_2 & u_2v_3 \\
u_3v_1 & u_3v_2 & u_3v_3
\end{bmatrix} \qquad \in \mathbb{R}^{3 \times 3}.](./images/939694f5ba93892ac63fd2785587f3e966ac8566.png)

Observe that the matrix-matrix product of a ![3\times1](./images/d64df9876c8c9a0d8d60681d95891dd8eaa05696.png) matrix and a ![1 \times 3](./images/53d0cbca6d38ed37808b17f771e6ce957700303f.png) matrix results in a ![3\times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix.

In[Section 4.2.6](./Chapter 4_ Geometric aspects of linear algebra.md) we’ll see how the outer product is used to build _projection matrices_. For example, the matrix that corresponds to the projection onto the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis is ![M_x = \hat{\imath}\hat{\imath}^\sfT \in \mathbb{R}^{3 \times 3}](./images/114ed344a8bf2ef68562702dbd338b4432936793.png). The ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-projection of any vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is computed as the matrix-vector product, ![M_x\vec{v} = \hat{\imath}\hat{\imath}^\sfT\vec{v} = \hat{\imath}(\hat{\imath}\cdot\vec{v}) = v_x \hat{\imath}](./images/d0153c77fe00cd5f9cc6789a5b648795ab9a0446.png). More on that later.

###[Matrix inverses](./Front matter.md)

Multiplying an invertible matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by its inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) produces the identity matrix: ![A A^{-1}= \mathbbm{1} = A^{-1}A](./images/2a23839bad5a19f0287f41ee87418eead22edd87.png). The _identity matrix_ obeys ![\mathbbm{1}\vec{v} = \vec{v}](./images/51c805cb90f920dcdb1371614e5b3eb0770dfdec.png) for all vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). The inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) _undoes_ whatever ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) did. The cumulative effect of multiplying by ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) is equivalent to the identity transformation,

![A^{-1}(A(\vec{v})) = (A^{-1}A)\vec{v} =  \mathbbm{1}\vec{v} = \vec{v}.](./images/ba087c35a13c508a4cf2104b2b94354d1369fd74.png)

We can think of “finding the inverse” (![\textrm{inv}(A)=A^{-1}](./images/fee498c87ae18cedccb7d1b8b828ef5fc34c0deb.png)) as an operation of the form

![\textrm{inv} : \mathbb{R}^{n \times n} \to \mathbb{R}^{n \times n}.](./images/26dd352912dd583e51a6d79fe2cb9c223310287e.png)

Note that only _invertible_ matrices have an inverse. Some matrices are not invertible—there is no “undo” operation for them. We’ll postpone the detailed discussion of invertibility until[Section 5.4](./Chapter 5_ Linear transformations.md).

####[Properties of matrix inverse operation](./Front matter.md)

-   ![(AB)^{-1} 	= B^{-1}A^{-1}](./images/6e0cb61bbb839109003ace30f8a8b6c5b37e9002.png)
-   ![(ABC)^{-1}    	= C^{-1}B^{-1}A^{-1}](./images/3e38af8d4d459748f0ac032b432794c2079019f2.png)
-   ![(A^\sfT)^{-1} 	= (A^{-1})^\sfT](./images/41402ce909520d7bb0f8d177b780c20cfa161b92.png)
-   ![(A^{-1})^{-1} 	= A](./images/8693f3d680e7e2298ba2602be27c319cc25356ba.png)

The matrix inverse plays the role of “division by the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)” in matrix equations. We’ll discuss matrix equations in[Section 3.2](./Chapter 3_ Computational linear algebra.md).

###[Trace](./Front matter.md)

The _trace_ of an ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix is the sum of the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) values on its diagonal:

![\textrm{Tr} : \mathbb{R}^{n \times n} \to \mathbb{R}, \qquad \quad
\textrm{Tr}\!\left[ A \right] 
\; \eqdef \; 
\sum_{i=1}^n a_{ii}.](../Images/4f7cd34025fcfd96f0639597bc683106e9500f76.png)

####[Properties of the trace operation](./Front matter.md)

-   ![\textrm{Tr}\!\left[ \alpha A + \beta B\right]  
    =  \alpha\textrm{Tr}\!\left[ A \right]   +  \beta \textrm{Tr}\!\left[ B\right]](../Images/cdd59c073cdf1fe41cea8952df8fffc30f8838af.png)              (linear property)
-   ![\textrm{Tr}\!\left[ AB \right]  	=  \textrm{Tr}\!\left[ BA \right]](../Images/3f059047e6e135b6b1fe22bb7fa7875b41e6d0bc.png)
-   ![\textrm{Tr}\!\left[ ABC \right]    	=  \textrm{Tr}\!\left[ CAB \right] =  \textrm{Tr}\!\left[ BCA \right]](../Images/c76355ed458bf3c7ddc636a0727bf073b01d42ad.png)             (cyclic property)
-   ![\textrm{Tr}\!\left[ A^\sfT \right]  =  \textrm{Tr}\!\left[ A \right]](../Images/c2b5797e810f13049a83838059f7649f49174555.png)
-   ![\textrm{Tr}\!\left[ A \right]  	=  \sum_{i=1}^{n} \lambda_i](../Images/899e08f08319403c2d2e2d02f313a9dfdc8be08b.png),    where ![\{ \lambda_i\}](./images/40512ae09a3b561b78b6b48308724922b9d9947c.png) are the eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

###[Determinant](./Front matter.md)

The _determinant_ of a matrix is a calculation that involves all the entries of the matrix, and whose output is a single number:

![\textrm{det} : \mathbb{R}^{n \times n} \to \mathbb{R}.](./images/6d65229e81525580b5b55f3303224675789b4685.png)

The determinant describes the relative geometry of the vectors that make up the rows of the matrix. More specifically, the determinant of a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) tells you the _volume_ of a box with sides given by rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

For example, the determinant of a ![2\times2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix is

![\det(A) 	= \det\!\left(	\begin{bmatrix}a&b\\ c&d \end{bmatrix} 	\right)
= \begin{vmatrix}a&b\\ c&d \end{vmatrix}
= ad-bc.](./images/863b000ee121b8bf4174d3c8451021b421954391.png)

The quantity ![ad-bc](./images/76fedc1d23f073afd3704aeda43e7601bba96651.png) corresponds to the area of the parallelogram formed by the vectors ![(a,b)](./images/98a5efa74a3f363e0ebadc4f086212f0b4a1a3de.png) and ![(c,d)](./images/8a84aa139a2fe07e6c7e61c9b24d3ca5d1e2b585.png). Observe that if the rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) point in the same direction, ![(a,b) = \alpha(c,d)](./images/f1612630cc82b3ce2bbfe095a90a3aebad6b7950.png) for some ![\alpha \in \mathbb{R}](./images/291a1b884bfe1bd3bdd9e4811c426bcf4da094c5.png), then the area of the parallelogram will be zero. If the determinant of a matrix is nonzero, then the rows of that matrix are linearly independent.

####[Properties of determinants](./Front matter.md)

-   ![\textrm{det}\!\left( AB\right) 	=  \textrm{det}\!\left( A \right)\textrm{det}\!\left( B\right)](./images/8dd2e1c41482b5cbdef1006d68ce959b3beca859.png)
-   ![\textrm{det}\!\left( A \right)   	=  \prod_{i=1}^{n} \lambda_i](./images/051ab4a08ad5831b53aec4d68f296e6e5a8b5ac5.png),    where ![\{\lambda_i\}](./images/40512ae09a3b561b78b6b48308724922b9d9947c.png) are the eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)
-   ![\textrm{det}\!\left( A^\sfT \right)	=  \textrm{det}\!\left( A \right)](./images/69549d7d0ff673286a07580b398ee8ce0890ac1f.png)
-   ![\textrm{det}\!\left( A^{-1}\right)	=  \frac{1}{\textrm{det}\!\left( A \right) }](./images/1bde1e177d68096a7808ce80c71c042ddc0c0f44.png)

###[Discussion](./Front matter.md)

Understanding vector and matrix operations is essential for understanding more advanced theoretical topics and the applications of linear algebra. In the remainder of this book, you’ll learn about various algebraic and geometric interpretations of the matrix operations defined in this section. Seeing all these definitions at the same time can be overwhelming, I know; but the good news is that we’ve defined all the math operations and notation we’ll need for the rest of the book. It could be worse, right?

So far, we’ve defined two of the main actors in linear algebra: vectors and matrices. But our introduction to linear algebra won’t be complete until we introduce _linearity_, the main thread that runs through all the topics in this book.

###[Exercises](./Front matter.md)

E2.7 Given the matrices ![A = \begin{bmatrix} 3 & 4 \\ 2 & 1 \end{bmatrix}](./images/9fac9bb0d8c289f1b6792ae28ec2d8dbf1038f95.png), ![B = \begin{bmatrix} -1 & 0 & 1 & 2 \\ 4 & 3 & 2 & 1 \end{bmatrix}](./images/d48e267acbaa71afb5bbb2f5cd798bccc7bd85fa.png), and ![C = \begin{bmatrix}  -2 & 3 & \,0 \\ 2 & \!-2 & \,1\end{bmatrix}](./images/098d027558da113a15ce56c6d94e3d35cb5a7b39.png), compute the expressions.

1.  ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png)
2.  ![C^\sfT](./images/a51a010fe4f60d87127d354d3b147e44ac0cf91b.png)
3.  ![A^2](./images/a0d61abbc27f436fbb804c112345805d7ce3a569.png)
4.  ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png)
5.  ![AC](./images/aa7d723b084d934250963427b8540e10d4c7e0e9.png)
6.  ![BA](./images/58910eb14ca75c4168a6f7410c0420693ae4e4f0.png)
7.  ![C^\sfT \!A](./images/bc659e28937d30b051cb6e2629a799aa820e3aa7.png)
8.  ![\det(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png)
9.  ![\det(B)](./images/7eb0c5ab860de15da120bcc947c628a356949def.png)
10.  ![\det(C)](./images/c94aa2b5849ba423c67828f8b801a6e14c6b281f.png)
11.  ![\det(A^\sfT)](./images/26012f789322d968fcf9c10b25bfddef109768da.png)
12.  ![\det(AA^{-1})](./images/7fc50c971121784d16738c43da629a1b4d7e7c92.png)
13.  ![\Tr(A)](./images/5cac703e5885c95d0781a32376aa9d456b4dbeb2.png)
14.  ![\Tr(A^\sfT)](./images/3b9bea4c04a0cf16ccd51184e7c61320724407bc.png)

Some of these expressions may not exist.

E2.8 Given the ![1\times 3](./images/53d0cbca6d38ed37808b17f771e6ce957700303f.png) matrices (row vectors) ![\vec{u} = (1,2,3)](./images/ab56c7987603c79fb83187ed7e9fa5c347d5b44c.png) and ![\vec{v} = (2,-1,0)](./images/17bc2f54f1e0a6a313c392d47c773f2b0ee75b0a.png), compute the following products:

1.  ![\vec{u}\,\vec{u}^\sfT](./images/c9ef3350fd62585fcd392767a932fab0a72a7142.png)
2.  ![\vec{v}\,\vec{v}^\sfT](./images/02efd01c74558c77e0722f26254d6259918c79ea.png)
3.  ![\vec{u}\,\vec{v}^\sfT](./images/37e671de9f2e4809735cee03399216b7b31f682e.png)
4.  ![\vec{u}^\sfT \vec{u}](./images/0891c7b0425bdeb2044ddcda8962765393f17f79.png)
5.  ![\vec{v}^\sfT \vec{v}](./images/033880e85c724fbe6bd5d108f085547ebc2aa89c.png)
6.  ![\vec{u}^\sfT \vec{v}](./images/0cfaf5fbb1d4a8d2b1bb699e9173374ec99a85ce.png)

The transpose of a ![1 \times 3](./images/53d0cbca6d38ed37808b17f771e6ce957700303f.png) row vector is a ![3\times 1](./images/d64df9876c8c9a0d8d60681d95891dd8eaa05696.png) column vector.

E2.9 Find the unknowns ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) in the equation ![\begin{bmatrix}2 & \alpha \\ \beta & -3\end{bmatrix}
\begin{bmatrix}1 \\ 4\end{bmatrix}=\begin{bmatrix}0 \\ 0\end{bmatrix}](./images/ad04f1eb9bc2fbf08b759bfc137ed0793ed3817e.png).

##[2.4 Linearity](./Chapter 2_ Intro to linear algebra.md)

What is linearity and why is this entire book dedicated to learning about it? Consider an arbitrary function that contains terms with different powers of the input variable ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png):

![f(x) \; =  \; 
\underbrace{
a/x
}_{\textrm{one-over-}x}
\; + \;	
\underbrace{
b 
}_{\textrm{constant}}
\; + \;
\underbrace{mx}_{\textrm{linear term}} 
\; + \; 
\underbrace{
q x^2 
}_{\textrm{quadratic}}
\; + \;
\underbrace{
cx^3
}_{\textrm{cubic}}.](./images/ccb8af238615816783076aa89bac0822f3517a93.png)

The term ![mx](./images/02c45c1743ab3c821cb5b5b822cf56536399157e.png) is the _linear_ term in this expression—it contains ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) raised to the first power. All the other terms are _nonlinear_. The linear term is special because changes in the value of the input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) lead to proportional changes in the value of ![mx](./images/02c45c1743ab3c821cb5b5b822cf56536399157e.png). If the input is ![2x](./images/a7b59e2b5d6108cb3e2b951758e65620c41d42ad.png), the linear term will have value ![2mx](./images/dbaf9009d94f359c3c005a80de1df763db75a7fc.png). If the input is ![100x](./images/5a5a5c912ec5e1c89d290042b5257ffc535c8db6.png), the linear term will have value ![100mx](./images/3bd7a6b67ae4fb1ba3ce013b40d107f18081bee8.png). This input-output proportionality does not hold for nonlinear terms.

In this section we’ll discuss the special properties of expressions and equations containing only linear terms.

###[Introduction](./Front matter.md)

A single-variable function takes as its input a real number ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and outputs a real number ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png). The type signature of this function is

![f \colon \mathbb{R}  \to \mathbb{R}.](./images/e78310939ec4d33ab1ed81231f63f86895cdd386.png)

The most general linear function from ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) to ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) looks like this:

![f(x) = mx,](./images/f5767e6458a0c9792e370d12625d880a73282238.png)

where ![m \in \mathbb{R}](./images/d739c22f19543c696a4d21ae9897c7a9d332346b.png) is called the _coefficient_ of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). The action of a linear function is to multiply the input by the constant ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png). So far, so good.

#####[Example of composition of linear functions](./Front matter.md)

Given the linear functions ![f(x)=2x](./images/209b4acd670aa339057fda89c8fe17c6ccc789d4.png) and ![g(x)=3x](./images/f2eede0b73b831343da4a60600d5a58c2e850cb8.png), what is the equation of the function ![h(x) \eqdef g\circ f \:(x) = g(f(x))](./images/219460ed1b9531d3d71d6fcb7e79fd2c4493c711.png)? The composition of ![f(x)=2x](./images/209b4acd670aa339057fda89c8fe17c6ccc789d4.png) and ![g(x)=3x](./images/f2eede0b73b831343da4a60600d5a58c2e850cb8.png) is the function ![h(x) =g(f(x))= 3(2x)=6x](./images/bd530b2d64546931631553c1490426c21e46e306.png). Note the composition of two linear functions is also a linear function. The coefficient of ![h](./images/f1ca3cd6c70e90cc02066e90b194d6633838fd36.png) is equal to the product of the coefficients of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) and ![g](./images/1946b9850ac13de564c7e979735a85b5419ff434.png).

###[Definition](./Front matter.md)

Linear functions map any linear combination of inputs to the same linear combination of outputs. A function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is _linear_ if it satisfies the equation

![f(\alpha x_1 + \beta x_2) =   \alpha f(x_1) +   \beta f(x_2),](./images/ae8107fa7660c133ba12544b918a5748742ff619.png)

for any two inputs ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), and for all constants ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png).

###[Lines are not linear functions!](./Front matter.md)

Consider the equation of a line:

![l(x) = mx+b,](./images/4f89aae6236f045346bd7b72d28d2408e72241b2.png)

where the constant ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) corresponds to the slope of the line, and the constant ![b = f(0)](./images/718b1fd44c4a7394b819233d77f06cb88b671995.png) is its initial value. A _line_ ![l(x)=mx+b](./images/2798bc29c944f03244c8618be07d211eb026a3ea.png) with ![b\neq 0](./images/9bb9a41350d9dcd9868c81af13c2244751bf3111.png) is _not_ a linear function. This logic may seem a bit weird, but if you don’t trust me, you can check for yourself:

![l(\alpha x_1) = m(\alpha x_1)+b
\quad \neq \quad
\alpha( mx_1 + b ) = \alpha l(x_1).](./images/3ee687be0ef1980c3feabdcbe90a1143c29b556e.png)

A function with a linear part added to a constant term is called an _affine transformation_. Affine transformations are cool but a bit off-topic, since this book focuses on _linear_ transformations.

###[Multivariable functions](./Front matter.md)

The study of linear algebra is the study of _all_ things linear. In particular, we’ll learn how to work with functions that take multiple variables as inputs. Consider the set of functions that take pairs of real numbers as inputs and produce real numbers as outputs:

![f \colon \mathbb{R}\times\mathbb{R}   \to \mathbb{R}.](./images/2ddf59a48d7d787effaca2380a3bbcb92d05d022.png)

The most general linear function of two variables is

![f(x,y) = m_xx + m_yy.](./images/405573d3f29c682ebb3b17b0d57d5ba4ccad740c.png)

You can think of ![m_x](./images/f2e3441d557cf0495e062e109e1957667497c737.png) as the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-slope and ![m_y](./images/3319509dece2bc3e3855024ffa447e5306ee2adb.png) as the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-slope of the function. We say ![m_x](./images/f2e3441d557cf0495e062e109e1957667497c737.png) is the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-coefficient and ![m_y](./images/3319509dece2bc3e3855024ffa447e5306ee2adb.png) the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coefficient in the linear expression ![m_xx + m_yy](./images/18c5c32ae7040e1cf2c5b7963de7356041e528e8.png).

###[Linear expressions](./Front matter.md)

A _linear expression_ in the variables ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png), ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), and ![x_3](./images/db23e43963a7727df3e8966c1e818afe37b229d7.png) has the form,

![a_1 x_1 + a_2 x_2 + a_3 x_3,](./images/98eb6dd033ef5992052457ebbf4fa6f414e32566.png)

where ![a_1](./images/687e2b6e809c59ef21e9cab2e018a3b291d0bd3e.png), ![a_2](./images/15e6e46159abbf02dbc681c4e96a0803670acafc.png), and ![a_3](./images/2f35f026afd31384bb62a7e3e27f7e142fef5528.png) are arbitrary constants. Note the new terminology “linear in ![v](./images/9dbc12809617badc127996f71d4593b4959c51e7.png),” which refers to an expression in which the variable ![v](./images/9dbc12809617badc127996f71d4593b4959c51e7.png) is raised to the first power. The expression ![\frac{1}{a} x_1 + b^6 x_2 + \sqrt{c}\,x_3](./images/a5768a4a2648cd37611daf6dd37e41c9fc7ac099.png) contains nonlinear factors (![\frac{1}{a}](./images/ed55b9c1e7ba73e05cb1b4081f4390cc63b24525.png), ![b^6](./images/ef0b84570a20a365c61a29d5be9446c04af1f345.png), and ![\sqrt{c}](./images/e385df4fc333344625a17193859ba82c465bfe93.png)) but is a linear expression in the variables ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png), ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), and ![x_3](./images/db23e43963a7727df3e8966c1e818afe37b229d7.png).

###[Linear equations](./Front matter.md)

A _linear equation_ in the variables ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png), ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), and ![x_3](./images/db23e43963a7727df3e8966c1e818afe37b229d7.png) has the form

![a_1 x_1 + a_2 x_2 + a_3 x_3 = c.](./images/7d81dccae2ae70c91a4cd4fa5f511afd16d94926.png)

This equation is linear because it contains only linear terms in the variables ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png), ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), and ![x_3](./images/db23e43963a7727df3e8966c1e818afe37b229d7.png).

#####[Example](./Front matter.md)

Linear equations are very versatile. Suppose you know that the following equation describes some real-world phenomenon:

![4k -2m + 8p = 10,](./images/3bb4228811ebce4ee514dbd7cc8d516a505bd035.png)

where ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png), ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png), and ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) correspond to three variables of interest. You can interpret this equation as describing the variable ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) as a function of the variables ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png) and ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png), and rewrite the equation as

![m(k,p)  = 2k + 4p - 5.](./images/c6da1d303119c31bb956483138372078354a13ec.png)

Using this function, you can predict the value of ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) given the knowledge of the quantities ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png) and ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png).

Another option would be to interpret ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png) as a function of ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) and ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png): ![k(m,p) = \frac{10}{4} +\frac{m}{2} - 2p](./images/c58717c41374fabff78e078c34c0a02df893527c.png). This model would be useful if you know the quantities ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) and ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and want to predict the value of the variable ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png).

###[Applications](./Front matter.md)

####[Geometric interpretation of linear equations](./Front matter.md)

The linear equation in ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png),

![ax + by = c,      \qquad b \neq 0,](./images/18955778a13759f1ed2540c1c20956121529eabd.png)

corresponds to a line with the equation ![y(x)=mx+y_0](./images/888eef119fc62a9df56d7128ac9a796d33e6dca1.png) in the Cartesian plane. The slope of the line is ![m=-a/b](./images/8a9b1cd97378d09a26fc6e6ff458e24b562c7cf7.png) and its ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-intercept is ![y_0=c/b](./images/236c9ac3827947920b73f39bf9b0d467ed8082df.png). The special case when ![b=0](./images/492aab63c461473534001b03487f9f9d16fa5298.png) corresponds to a vertical line with equation ![x=\frac{c}{a}](./images/28bcf4a0e6b87dfa5b580de69e679e088e96385b.png).

The most general linear equation in ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png),

![ax + by + cz = d,](./images/d9d00f8f98fd202d61a946656a6f9454084d9276.png)

corresponds to the equation of a plane in a three-dimensional space. Assuming ![c\neq 0](./images/257c8f72e5b414ad6792d327eaa0a4ec36f83642.png), we can rewrite this equation so ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png) (the “height”) is a function of the coordinates ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png): ![z(x,y) = z_0 + m_x x  + m_y y](./images/5244d770d4a08beaa40349405d210ee2b84c7a88.png). The slope of the plane in the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-direction is ![m_x= - \frac{a}{c}](./images/45c863e69b874ba326d80c1d20b7cede2011056b.png) while the slope in the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-direction is ![m_y = - \frac{b}{c}](./images/82c02ef89d2ec61a437c5e3a86d041509ae05084.png). The ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-intercept of this plane is ![z_0=\frac{d}{c}](./images/1977e3a8f266ccd49e73bfbc0f0921a4fb875f0e.png).

####[First-order approximations](./Front matter.md)

When we use a linear function as a mathematical model for a nonlinear, real-world input-output process, we say the function represents a _linear model_ or a _first-order approximation_ for the process. Let’s analyze what this means in more detail, and see why linear models are so popular in science.

In calculus, we learn that functions can be represented as infinite Taylor series:

![f(x) = \textrm{taylor}(f(x)) =  a_0 + a_1t + a_2t^2 + a_3t^3 + \cdots = \sum_{n=0}^\infty a_n x^n,](./images/b02da78e8f9282d8f5b218cd3397f7d2bbefb470.png)

where the coefficient ![a_n](./images/1506cdb80ad5652d9a410c8547f1a72cbd19ce34.png) depends on the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)th derivative of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png). The Taylor series is only equal to the function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) if infinitely many terms in the series are calculated. If we sum together only a finite number of terms in the series, we obtain a _Taylor series approximation_. The first-order Taylor series approximation to ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) is

![f(x) \approx \textrm{taylor}_1(f(x)) =  a_0 + a_1x = f(0) + f'(0)x.](./images/88da3424e39c090585101e8c1403872b2d15e1fa.png)

The above equation describes the best approximation to ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) near ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png), by a line of the form ![l(x)=mx+b](./images/2798bc29c944f03244c8618be07d211eb026a3ea.png). To build a linear model ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) of a real-world process, it is sufficient to measure two parameters: the initial value ![b=f(0)](./images/718b1fd44c4a7394b819233d77f06cb88b671995.png) and the rate of change ![m=f'(0)](./images/2bdcf4c3da83251563901e5c79880c82d538224f.png).

Scientists routinely use linear models because this kind of model allows for easy _parametrization_. To build a linear model, the first step is to establish the initial value ![f(0)](./images/a417baca9baeb61459f71fafa5101378a2a2272b.png) by inputting ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png) to the process and seeing what comes out. Next, we vary the input by some amount ![\Delta x](./images/46759c9ab67e1785c9f3a4fbf60ee7b482e98c4e.png), and observe the resulting change in the output ![\Delta f](./images/17db05eab871d2b5237772549a569eeedd097eea.png). The rate of change parameter is equal to the change in the output divided by the change in the input ![m = \frac{\Delta f}{\Delta x}](./images/599f046a9eec7e2d86f0336a0343c54eb903e5b8.png). Thus, we can obtain the parameters of a linear model in two simple steps. In contrast, finding the parametrization of nonlinear models is a more complicated task.

For a function ![F(x,y,z)](./images/a28a085b355c58819585aad32c5c6af695984a9c.png) that takes three variables as inputs, the first-order Taylor series approximation is

![F(x,y,z) 	\approx 	  b           + m_x x + m_y y  + m_z z.](./images/158057e4fcd0eb3ca72ee0ac965ff4345741f7fe.png)

Except for the constant term, the function has the form of a linear expression. The “first-order approximation” to a function of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) variables ![F(x_1,x_2,\ldots, x_n)](./images/d35dab74e4fc5d8449436d4f4e343386078e63b1.png) has the form ![b + m_1x_1 + m_2x_2 + \cdots + m_nx_n](./images/312d208e969e3eb865ca668d2f96159aa33a1a34.png).

As in the single-variable case, finding the parametrization of a multivariable linear model is a straightforward task. Suppose we want to model some complicated real-world phenomenon that has ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) input variables. First, we input only zeros to obtain the initial value ![F(0,\ldots,0) = b](./images/6c9aea252bb7831b62d159a83e7675c53d3955d8.png). Next, we go through each of the input variables one-by-one and measure how a small change in each input ![\Delta x_i](./images/a2a8467e85baa4e2ab32acd996fe10c2cbf7fad9.png) affects the output ![\Delta f](./images/17db05eab871d2b5237772549a569eeedd097eea.png). The rate of change with respect to the input ![x_i](./images/95d233a0d2bf3ac8b54cc52b4da9bcc248fb5855.png) is ![m_i = \frac{ \Delta f}{\Delta x_i}](./images/4e47f828319f3fce04a8ac934d5dad249cb6c10d.png). By combining the knowledge of the initial value ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) and the “slopes” with respect to each input parameter, we’ll obtain a complete linear model of the phenomenon.

###[Discussion](./Front matter.md)

In the next three chapters, we’ll learn about more mathematical objects and mathematical operations. Linear algebra is the study of vectors, matrices, linear transformations, vector spaces, and other abstract, vector-like objects. The mathematical operations we’ll perform on these objects will be linear: ![f(\alpha \mathbf{obj}_1 + \beta \mathbf{obj}_2) =   \alpha f(\mathbf{obj}_1) + \beta f(\mathbf{obj}_2)](./images/dc7ca6fdd290e944c3e5f21e4a7ca0224517a860.png). Linearity is the core assumption of linear algebra.

###[Exercises](./Front matter.md)

E2.10 Are these expressions linear in the variables ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)?

1.  ![2x+5y + \sqrt{m}z](./images/858ccabe0ca8a7e91b083c0769b55c0886690bcb.png)
2.  ![10\sqrt{x} + 2(y+z)](./images/9ad086b91f888db4011bf9b1d314da84540ccf0c.png)
3.  ![42x + \alpha^2\sin(\frac{\pi}{3})y + z\cos(\frac{\pi}{3})](./images/62365c5b5e14ba4a7a94899eed21d5b819d4f12f.png)

##[2.5 Overview of linear algebra](./Chapter 2_ Intro to linear algebra.md)

In linear algebra, you’ll learn new computational techniques and develop new ways of thinking about math. With these new tools, you’ll be able to use linear algebra techniques for many applications. Let’s look at what lies ahead in this book.

###[Computational linear algebra](./Front matter.md)

The first steps toward understanding linear algebra will seem a little tedious. In[Chapter 3](./Chapter 3_ Computational linear algebra.md) you’ll develop basic skills for manipulating vectors and matrices. Matrices and vectors have many components and performing operations on them involves many arithmetic steps—there is no way to circumvent this complexity. Make sure you understand the basic algebra rules (how to add, subtract, and multiply vectors and matrices) because they are a prerequisite for learning more advanced material. You should be able to perform all the matrix algebra operations with pen and paper for small and medium-sized matrices.

The good news is, with the exception of your homework assignments and final exam, you won’t have to carry out matrix algebra by hand. It is much more convenient to use a computer for large matrix calculations. The more you develop your matrix algebra skills, the deeper you’ll be able to delve into the advanced topics.

###[Geometric linear algebra](./Front matter.md)

So far, we’ve described vectors and matrices as arrays of numbers. This is fine for the purpose of doing _algebra_ on vectors and matrices, but this description is not sufficient for understanding their geometric properties. The components of a vector ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png) can be thought of as distances measured along a coordinate system with ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) axes. The vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) can therefore be said to “point” in a particular direction with respect to the coordinate system. The fun part of linear algebra starts when you learn about the geometric interpretation of the algebraic operations on vectors and matrices.

Consider some unit vector that specifies a direction of interest ![\hat{r}](./images/2bdf466e7e7803ff2dc292dd12c924f37722108c.png). Suppose we’re given some other vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), and we’re asked to find _how much of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is in the ![\hat{r}](./images/2bdf466e7e7803ff2dc292dd12c924f37722108c.png) direction_. The answer is computed using the dot product: ![v_r = \vec{v} \cdot \hat{r} = \|\vec{v}\|\cos\theta](./images/a6e4bd054934205d55fac56c7f0724c2b57e04fa.png), where ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is the angle between ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\hat{r}](./images/2bdf466e7e7803ff2dc292dd12c924f37722108c.png). The technical term for the quantity ![v_r](./images/d0ed53c0724f1f2e843b3e6fda4950e98ee9bb24.png) is “the length of the projection of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in the ![\hat{r}](./images/2bdf466e7e7803ff2dc292dd12c924f37722108c.png) direction.” By “projection,” I mean we ignore all parts of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) that are not in the ![\hat{r}](./images/2bdf466e7e7803ff2dc292dd12c924f37722108c.png) direction. Projections are used in mechanics to calculate the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-components of forces in force diagrams. In[Section 4.2](./Chapter 4_ Geometric aspects of linear algebra.md) we’ll learn how to calculate all kinds of projections using the dot product.

To further consider the geometric aspects of vector operations, imagine the following situation. Suppose I gave you two vectors ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), and asked you to find a third vector ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) that is perpendicular to both ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). A priori this sounds like a complicated question to answer, but in fact the required vector ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) can easily be obtained by computing the cross product ![\vec{w}=\vec{u}\times\vec{v}](./images/210dc48414d991d29c72dcf3bcaa3535f9a23c93.png).

In[Section 4.1](./Chapter 4_ Geometric aspects of linear algebra.md) we’ll learn how to describe lines and planes in terms of points, direction vectors, and normal vectors. Consider the following geometric problem: given the equations of two planes in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png), find the equation of the line where the two planes intersect. There is an algebraic procedure called _Gauss–Jordan elimination_ we can use to find the solution.

The determinant of a matrix has a geometric interpretation [Section 3.4](./Chapter 3_ Computational linear algebra.md)). The determinant tells us something about the relative orientation of the vectors that make up the rows of the matrix. If the determinant of a matrix is zero, it means the rows are not _linearly independent_, in other words, at least one of the rows can be written in terms of the other rows. Linear independence, as we’ll see shortly, is an important property for vectors to have. The determinant is a convenient way to test whether vectors are linearly independent.

As you learn about geometric linear algebra, practice _visualizing_ each new concept you learn about. Always keep a picture in your head of what is going on. The relationships between two-dimensional vectors can be represented in vector diagrams. Three-dimensional vectors can be visualized by pointing pens and pencils in different directions. Most of the intuition you build about vectors in two and three dimensions are applicable to vectors with more dimensions.

###[Theoretical linear algebra](./Front matter.md)

Linear algebra will teach you how to reason about vectors and matrices in an abstract way. By thinking abstractly, you’ll be able to extend your geometric intuition of two and three-dimensional problems to problems in higher dimensions. Much _knowledge buzz_ awaits as you learn about new mathematical ideas and develop new ways of thinking.

You’re no doubt familiar with the normal coordinate system made of two orthogonal axes: the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis and the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis. A vector ![\vec{v}\in \mathbb{R}^2](./images/e3178de0f13474a865bbadb33a26cc93ba2230b3.png) is specified in terms of its coordinates ![(v_x,v_y)](./images/bf08d8f270c5ace12ee18ba92752c926e1cd6f5b.png) with respect to these axes. When we say ![\vec{v}=(v_x,v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png), what we really mean is ![\vec{v} = v_x \hat{\imath} + v_y \hat{\jmath}](./images/cd33df884edcfbe9d040c4d295f459405759d0fb.png), where ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png) and ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png) are unit vectors that point along the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axes. As it turns out, we can use many other kinds of coordinate systems to represent vectors. A _basis_ for ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png) is any set of two vectors ![\{ \hat{e}_1, \hat{e}_2 \}](./images/bea59ac9351166e8c268eeac36fe324f3ce001ea.png) that allows us to express all vectors ![\vec{v} \in \mathbb{R}^2](./images/e3178de0f13474a865bbadb33a26cc93ba2230b3.png) as linear combinations of the basis vectors: ![\vec{v} = v_1 \hat{e}_1 + v_2 \hat{e}_2](./images/1b3d7833932be7157dc58b4963416b2c87f0e6c6.png). The same vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) corresponds to two different coordinate pairs, depending on which basis is used for the description: ![\vec{v}=(v_x,v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png) in the basis ![\{ \hat{\imath}, \hat{\jmath}\}](./images/81e59913690964dec5056d8ba5bc8eac170f8c1f.png) and ![\vec{v}=(v_1,v_2)](./images/6a397785cb41b9155e6c8bcaa271e1a634a1ea50.png) in the basis ![\{ \hat{e}_1, \hat{e}_2 \}](./images/bea59ac9351166e8c268eeac36fe324f3ce001ea.png). We’ll learn about bases and their properties in great detail in the coming chapters. The choice of basis plays a fundamental role in all aspects of linear algebra. Bases relate the real-world to its mathematical representation in terms of vector and matrix components.

In the text above, I explained that computing the product between a matrix and a vector ![A\vec{x}=\vec{y}](./images/de8346fe5aacf3c52a967a9e544ee1114f08ce26.png) can be thought of as a linear transformation, with input ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) and output ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png). Any linear transformation [Section 5.1](./Chapter 5_ Linear transformations.md)) can be represented [Section 5.2](./Chapter 5_ Linear transformations.md)) as a multiplication by a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Conversely, every ![m\times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrix ![A \in \mathbb{R}^{m\times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) can be thought of as performing a linear transformation ![T_A \colon \mathbb{R}^n \to \mathbb{R}^m](./images/b22201663d5c28e3ac0381dbe2312a057f12a9e3.png). The equivalence between matrices and linear transformations allows us to identify certain matrix properties with properties of linear transformations. For example, the _column space_ ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png) of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) (the set of vectors that can be written as a combination of the columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)) corresponds to the image space of the linear transformation ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) (the set of possible outputs of ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png)).

The eigenvalues and eigenvectors of matrices [Section 6.1](./Chapter 6_ Theoretical linear algebra.md)) allow us to describe the actions of matrices in a natural way. The set of eigenvectors of a matrix are special input vectors for which the action of the matrix is described as a _scaling_. When a matrix acts on one of its eigenvectors, the output is a vector in the same direction as the input vector scaled by a constant. The scaling constant is the _eigenvalue_ (own value) associated with this eigenvector. By specifying all the eigenvectors and eigenvalues of a matrix, it is possible to obtain a complete description of what the matrix does. Thinking of matrices in terms of their eigenvalues and eigenvectors is a powerful technique for describing their properties and has many applications.

Linear algebra is useful because linear algebra techniques can be applied to all kinds of “vector-like” objects. The abstract concept of a vector space [Section 6.3](./Chapter 6_ Theoretical linear algebra.md)) captures precisely what it means for some class of mathematical objects to be “vector-like.” For example, the set of polynomials of degree at most two, denoted ![P_2(x)](./images/470e4e253d68b222e3f3b163490bc01e944484f7.png), consists of all functions of the form ![f(x)=a_0 + a_1x + a_2x^2](./images/3bf4de43735f9b6855fac226af593cc12ce95a54.png). Polynomials are vector-like because it’s possible to describe each polynomial in terms of its coefficients ![(a_0,a_1,a_2)](./images/d5ed087ed3f9a40c5d39b4f5cca53106f77515f9.png). Furthermore, the sum of two polynomials and the multiplication of a polynomial by a constant both correspond to vector-like calculations of coefficients. Once you realize polynomials are vector-like, you’ll be able to use notions like _linear independence_, _dimension_, and _basis_ when working with polynomials.

###[Useful linear algebra](./Front matter.md)

One of the most useful skills you’ll learn in linear algebra is the ability to solve systems of linear equations. Many real-world problems are expressed as linear equations in multiple unknown quantities. You can solve for ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) unknowns simultaneously if you have a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linear equations that relate the unknowns. To solve this system of equations, eliminate the variables one by one using basic techniques such as substitution and subtraction (see[Section 1.15](./Chapter 1_ Math fundamentals.md)); however, the procedure will be slow and tedious for many unknowns. If the system of equations is linear, it can be expressed as an _augmented matrix_ built from the coefficients in the equations. You can then use the Gauss–Jordan elimination algorithm to solve for the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) unknowns [Section 3.1](./Chapter 3_ Computational linear algebra.md)). The key benefit of the augmented matrix approach is that it allows you to focus on the coefficients without worrying about the variable names. This saves time when you must solve for many unknowns. Another approach for solving ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linear equations in ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) unknowns is to express the system of equations as a matrix equation [Section 3.2](./Chapter 3_ Computational linear algebra.md)) and then solve the matrix equation by computing the matrix inverse [Section 3.5](./Chapter 3_ Computational linear algebra.md)).

In[Section 6.6](./Chapter 6_ Theoretical linear algebra.md) you’ll learn how to _decompose_ a matrix into a product of simpler matrices. Matrix decompositions are often performed for computational reasons: certain problems are easier to solve on a computer when the matrix is expressed in terms of its simpler constituents. Other decompositions, like the decomposition of a matrix into its eigenvalues and eigenvectors, give you valuable information about the properties of the matrix. Google’s original PageRank algorithm for ranking webpages by “importance” can be explained as the search for an eigenvector of a matrix. The matrix in question contains information about all hyperlinks that exist between webpages. The eigenvector we’re looking for corresponds to a vector that describes the relative importance of each page. So when I tell you eigenvectors are _valuable information_, I’m not kidding: a little 350-billion-dollar company called Google started as an eigenvector idea.

The techniques of linear algebra find applications in many areas of science and technology. We’ll discuss applications such as _modelling_ multidimensional real-world problems, finding _approximate solutions_ to equations (curve fitting), solving constrained optimization problems using _linear programming_, and many other in[Chapter 7](./Chapter 7_ Applications.md). As a special bonus for readers interested in physics, a short introduction to quantum mechanics can be found in[Chapter 9](./Chapter 9_ Quantum mechanics.md); if you have a good grasp of linear algebra, you can understand matrix quantum mechanics at no additional mental cost.

Our journey into the land of linear algebra will continue in the next chapter with the study of computational aspects of linear algebra. We’ll learn how to solve large systems of linear equations, practice computing matrix products, discuss matrix determinants, and compute matrix inverses.

##[2.6 Introductory problems](./Chapter 2_ Intro to linear algebra.md)

We’ve been having fun learning about vector and matrix operations, and we’ve also touched upon linear transformations. I’ve summarized what linear algebra is about; now it’s time for you to put in the effort and check whether you understand the definitions of the operations.

Don’t cheat yourself by thinking my summaries are enough; you can’t magically understand everything about linear algebra merely by reading about it. Learning doesn’t work that way! The only way to truly “get” math—especially advanced math—is to solve problems using the new concepts you’ve learned. Indeed, the only math I remember from my university days is math that I practiced by solving lots of problems. There’s no better way to test whether you understand than testing yourself. Of course, it’s your choice whether you’ll dedicate the next hour of your life to working through the problems in this section. All I’ll say is that you’ll have something to show for your efforts; and it’s totally worth it.

P2.1 Which of the following functions are linear?

1.  ![q(x)\!=\!x^2](./images/e11832b89f22683ec77017da86097184fd4c2e02.png)
2.  ![f(x)\!=\!g(h(x))](./images/cab7bd890d3d383e33835172eb0b66823eb809c3.png), where   ![g(x)\!=\!\sqrt{3}x](./images/7ee8fe57d7000253251e59d4fa00f319a4dc5ef2.png)  and   ![h(x)\!=\!-4x](./images/3129ce1bb6e86d3739fcd7ef659c6e02342ebbc7.png)   
3.  ![i(x)=\frac{1}{mx}](./images/a9ca0a2e31bbc965c8a624fac3ea37c73793b5b6.png)
4.  ![j(x)=\frac{x-a}{x-b}](./images/11cc92fd89bb08c4ea7a33ca279887753e4389ab.png)

P2.2 Find the sum of the vector ![(1,0,1)](./images/4a53a5d07f9d306c303d9df94820edb6d68dbcdc.png) and the vector ![(0,2,2)](./images/272b7274c03765ffb45ea74af67b6ee15c7f2cdf.png).

P2.3 Your friend is taking a quantum physics class and needs your help answering the following vectors question. “Let ![\ket{a} = 1\ket{0} +3\ket{1}](./images/a45085d544a1d18530ec700e5c1398b183ccb6cc.png) and ![\ket{b} = 4\ket{0} -1\ket{1}](./images/e7bdc3d9f63bf0ebea3b4ef45505c1b35cfe5258.png). Find ![\ket{a} + \ket{b}](./images/44dcf084bbea93fb8afc8bf90708a446bd0af7b2.png).”

The angle-bracket notation describes vectors: ![\ket{0}=\hat{\imath}](./images/50c18752dfa6e6f10be1efee6dd465139d0f5af4.png) and ![\ket{1}=\hat{\jmath}](./images/02c650a0029b3619ca1461c6af399112f2291b82.png).

P2.4 Given unit vectors ![\hat{\imath}=(1,0,0)](./images/8497756d3d95be1c98cabefb26fddbdc627a4e1c.png), ![\hat{\jmath}=(0,1,0)](./images/d5e790cd4c09d275224afeed0091f75950a6fc04.png), and ![\hat{k}=(0,0,1)](./images/878a16622ade000c9e114d27ce0779f614e2566f.png), find the following cross products: **a)** ![\hat{\imath}\times\hat{\imath}](./images/91819151b83a5ca9e5d750e40a4f772229abfe3e.png), **b)** ![\hat{\imath}\times\hat{\jmath}](./images/237bc90aff3ec76ce182088d141a4a8a9d2250c9.png), **c)** ![(-\hat{\imath})\times\hat{k}+\hat{\jmath}\times\hat{\imath}](./images/13f613ae5b571374c2ca7f1094f280ce32098b53.png), **d)** ![\hat{k}\times\hat{\jmath}+\hat{\imath}\times\hat{\imath}+\hat{\jmath}\times\hat{k}+\hat{\jmath}\times\hat{\imath}](./images/0d23cb86ce069b456f0c06085ea8d71e50aec8de.png).

P2.5 Given ![\vec{v}= (2, -1, 3)](./images/5641e68aee7f18e2d6fccb13117fbd01c80c7507.png) and ![\vec{w}=(1, 0, 1)](./images/644e05227d1e6077d1d0b87b52103ba86492f8fc.png), compute the following vector products: **a)** ![\vec{v} \cdot \vec{w}](./images/42c8e5c8bfb1263b264be2e70c17538f958332c3.png), **b)** ![\vec{v} \times \vec{w}](./images/afa0ecb1db69dfaf95877c591a3ec7392df05f0d.png), **c)** ![\vec{v} \times \vec{v}](./images/29eee132e8838618bc1870f6d7959da6a4635d0e.png), and **d)** ![\vec{w} \times \vec{w}](./images/e9d7bc35b5e9c3c834f036518473c459d9a3a99d.png).

P2.6 Given the vectors ![\vec{u}=(1,1,1)](./images/bb51f56a83e9b4246de9b7c7aeb384997f8221cc.png), ![\vec{v} = (2,3,1)](./images/83ab9d2f8d9b57fee50df48087047e521c80fa45.png), and ![\vec{w}=(-1,-1,2)](./images/32c9cee4128751dadaae2b9d52260658d79ab868.png), compute the following products:

**a)**  ![\vec{u} \cdot \vec{v}](./images/a7c4c8dad984b4767dd1e26c561bd763f42621b8.png)**b)**  ![\vec{u} \cdot \vec{w}](./images/6a0805ad7dc1393bdb3f7c9165b0eb2d9eaf153a.png)**c)** ![\vec{v} \cdot \vec{w}](./images/42c8e5c8bfb1263b264be2e70c17538f958332c3.png)

**d)**  ![\vec{u} \times \vec{v}](./images/d3b3eb97fd613f167bb48ef2c60dd87ac613a5c1.png)**e)**  ![\vec{u} \times \vec{w}](./images/f3f36a6a9c7e92c602a70157129fb6ba7ac3bb8f.png)**f)** ![\vec{v} \times \vec{w}](./images/afa0ecb1db69dfaf95877c591a3ec7392df05f0d.png)

P2.7 Given the vectors ![\vec{p} =(1,1,0,3,3)](./images/027ac30f23ffe38e8526f631424b6bf7c734d709.png) and ![\vec{q}=(1,2,3,4,5)](./images/a529a7270ce75ba40e525eb8b259c7736f383a83.png), calculate the following expressions:

**a)**  ![\vec{p}+\vec{q}](./images/3f4be7b79f102a9a89a014778868c7318a175f69.png)**b)**  ![\vec{p}-\vec{q}](./images/3e041e22ee5f4be3c5eb0d5fc825df65acdc268f.png)**c)** ![\vec{p} \cdot \vec{q}](./images/582aa72aad491dafb0715b57dad137ec7f63967f.png)

P2.8 Find a unit vector that is perpendicular to both ![\vec{u}=(1, 0, 1)](./images/a45d1ecb4e43d27c29455b64a7fff8dd2d0c8e83.png) and ![\vec{v} =(1, 2, 0)](./images/8db833cb1ffb77a49921ded9205ed7388edf5b97.png).

Use the cross product.

P2.9 Find a vector that is orthogonal to both ![\vec{u}_1 = (1, 0, 1)](./images/11c4de583c7bf37fd5f59c09ad6ee13864af23bb.png) and ![\vec{u}_2 =(1, 3, 0)](./images/7236e154ec4e6b8b106f988388342dbbfbcca114.png), and whose dot product with the vector ![\vec{v}= (1, 1, 0)](./images/400e353356a559caf8fc96a8cceed4bcec0e46b7.png) is equal to ![8](./images/50c8b4df6905af6190f7d236bc17391db40df469.png).

P2.10 A farmer with a passion for robotics has built a prototype of a robotic tractor. The tractor is programmed to move with a speed of ![0.524](./images/eee7bee87bf366f989528fdc27e54742abcb72e3.png) km/h and follow the direction of the hour-hand on a conventional watch. Assume the tractor starts at 12:00 p.m. (noon) and is left to roam about in a field until 6:00 p.m. What is the shape of the trajectory that the tractor will follow? What is the total distance travelled by the tractor after six hours?

P2.11 Prove the geometric formula for the dot product ![\vec{u}\cdot\vec{v} =  \|\vec{u}\|\|\vec{v}\|\cos(\varphi)](./images/914275285a54e40b56ea085084d054b4f6c4a829.png), where ![\varphi](./images/6f14e9ed0b9ebc16fdc9b26b6156e6d595813474.png) is the angle between vectors ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png) and ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png).

Consider the triangle with sides ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png), ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png), and ![\vec{u}-\vec{v}](./images/2f8f955e14d3e949e6c9158e7bd1d34601aa67ea.png). Connect the algebraic calculation of the length ![\| \vec{u}-\vec{v} \|^2 = (\vec{u}-\vec{v}) \cdot (\vec{u}-\vec{v})](./images/9881c3aa6acbd2638df07383911c18fbcd534655.png) with the geometric calculation based on the cosine rule from[Section 1.10](./Chapter 1_ Math fundamentals.md).

P2.12 Compute the product ![M\vec{v}](./images/1838f01d28ea99a9c09d72373f23e5bcda68d904.png) where ![M = \begin{bmatrix}\alpha & \beta \\ \gamma & \delta\end{bmatrix}](./images/d72c4041efdad80d4169899bca92c519be64d875.png) and ![\vec{v}=\begin{bmatrix} z_1 \\ z_2 \end{bmatrix}](./images/72d9faf13b7714b5328fd7b5424d233aa4dab115.png).

P2.13 Consider the following three linear transformations that take two-dimensional vectors as inputs and produce two-dimensional vectors as outputs:

![T_A\!\!\left(\begin{bmatrix}
x \\
y 
\end{bmatrix}\right)
=
\begin{bmatrix}
3x \\
y
\end{bmatrix},
\quad
T_B\!\!\left(\begin{bmatrix}
x \\
y 
\end{bmatrix}\right)
=
\begin{bmatrix}
x + y \\
y
\end{bmatrix},
\quad
T_C\!\!\left(\begin{bmatrix}
x \\
y 
\end{bmatrix}\right)
=
\begin{bmatrix}
3x + y\\
y
\end{bmatrix}.](./images/2925095d2fb5dda269fc29c6c8847e9d9fda1511.png)

Find the ![2 \times 2](./images/8d9f69fe9ab543dc19bd60e8ea565644efbcebb4.png) matrices ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png), ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png), and ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) such that

![T_A(\vec{v}) = A\vec{v},
\quad
T_B(\vec{v}) = B\vec{v},
\quad
T_C(\vec{v}) = C\vec{v},
\quad
\textrm{for all } \vec{v}.](./images/24cd1af86635e1af29ce47270f509c18e1bbb24d.png)

Use your answers to compute the matrix products ![AB](./images/ba90019888e8cb9ef51160a7cd7cb8ec3c63edda.png) and ![BA](./images/963b816e55c8e1a8ee9f5511d1fc2f015eb274b3.png).

P2.14 Consider the following matrices of different dimensions:

![A =
\begin{bmatrix}
2	& 	3	\\
5 	&	6
\end{bmatrix}	\!,
\; 
B = 
\begin{bmatrix}
7	& 	8	\\
1 	&	4
\end{bmatrix}	\!,
\; 
C = 
\begin{bmatrix}
-1	& 	4	\\
2 	&	1	\\
-1	&	2
\end{bmatrix}	\!,
\; 
U =
\begin{bmatrix}
2 & 1
\end{bmatrix}	\!,
\; 
\textrm{and}
\; 
V =
\begin{bmatrix}
1		\\
-2
\end{bmatrix}	\!.](./images/855c1279199872739c2b6b0d3a6e0b1bcb533b55.png)

Compute the following matrix expressions:

1.  ![A\!-\!B](./images/2c38d27405220d2aacee36f962a0bc1e82f3e86d.png)
2.  ![5C^\sfT](./images/9e4352ffceb3d0490a420db2bb43f01978253222.png)
3.  ![AB](./images/8a07ac9281e4ab08a6c913813d2381639a19055f.png)
4.  ![AC](./images/80bc8e4101320d70f032379b00614fee03c25385.png)
5.  ![CA](./images/cb5420131650b986b50f9c674f058401e54dfa9d.png)
6.  ![UA](./images/c998b7fa347e2e4b28094fdc11917a28c7dac481.png)
7.  ![AV](./images/265db4fe3a7085afa68b2c136c97ec218d41d3b4.png)
8.  ![UV](./images/d576a100c3676cf23512a4efbb30e54b9b14946a.png)
9.  ![VU](./images/cc5329df0dd6f5d9320e30848d8fa92b425de3d2.png)
10.  ![\Tr(A)](./images/3eb67292d9e08a6a807a8bba5b8f336590b636e2.png)
11.  ![\Tr(B)](./images/8cd5fe71daa0d7b12e300075941303d4ddd73e4a.png)
12.  ![\det(A)](./images/98d6e4278588714babf73aaf6e2183d5b78e6ecb.png)
13.  ![\det(B)](./images/479bbb1c988eda07d3c73d3be7fd20bf811aa57f.png)

P2.15 Use the determinant properties to simplify these expressions:

1.      ![\det(ABA^{-1})](./images/b127e8bf73bfb7be5f3af99cf28483fc05c597d0.png)
2.      ![\frac{\det(AB)}{\det(B)}](./images/b781d3e0e265407578d07ad90f3754ebb8053d6d.png)
3.  ![\det(AB) - \det(BA)](./images/df6342c72371ab4debead38aaa96293b59c9dddc.png)

P2.16 Suppose ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png), ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png), and ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) are unknown matrices such that ![|A|=2](./images/1bf40f3d0285901230ecd42bf38bb30e0ea77fb9.png), ![|B|=3](./images/96466e4b19cc808e1c7677328a6ff6efd4b70cd6.png), and ![|C|=5](./images/1c4c08d594769de86bfdf5cde7112f91195411b7.png). Determine the values of the following expressions:

1.            ![|AB|](./images/a7eb311af3fc62091582bb648f4caf63de2126a5.png)
2.            ![|A^{-1}B|](./images/64c93a8624e333fab77a87dba55cee09150feac7.png)
3.            ![|BC|](./images/804025d0cfac046318fdc5e88f6b675bc83e8b04.png)
4.  ![|ABC|](./images/e2b5d2add8a6cd243e9e024f91fea8091cec76a6.png)

Use the properties of the determinant operation.

[1.](./Front matter.md) The notation “![s \in \!S](./images/59b98f53e4e8fbf985a8f7826acac2e5ae4a9e81.png)” is read “![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png) is an element of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)” or “![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png) in ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png).”

[2.](./Front matter.md) The name _![\ell^2](./images/7fad99f1385aea13b4db8c4cfa93bef46e3eb4e0.png)\-norm_ refers to the process of squaring each of the vector’s components, and then taking the square root. Another norm is the ![\ell^4](./images/798a87696ee06e21cfbcaa267a7e8d7cf3832c50.png)\-norm, defined as the fourth root of the sum of the vector’s components raised to the fourth power: ![\|\vec{u}\|_4 \eqdef \sqrt[4]{u_1^4+u_2^4+u_3^4}](../Images/c937a356c743ab00fc0df4d7667728c153faaab3.png).
