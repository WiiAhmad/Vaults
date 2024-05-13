Chapter 4      

#[Chapter 4 Geometric aspects of linear algebra](./Chapter 4_ Geometric aspects of linear algebra.md)

In this section, we’ll study geometric objects like lines, planes, and vector spaces. We’ll use what we learned about vectors and matrices in the previous chapters to perform geometric calculations such as projections and distance measurements.

Developing your intuition about the geometric problems of linear algebra is very important: of all the things you learn in this course, your geometric intuition will stay with you the longest. Years from now, you may not recall the details of the Gauss–Jordan elimination procedure, but you’ll still remember that the solution to three linear equations in three variables corresponds to the intersection of three planes in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png).

##[4.1 Lines and planes](./Chapter 4_ Geometric aspects of linear algebra.md)

_Points_, _lines_, and _planes_ are the basic building blocks of geometry. In this section, we’ll explore these geometric objects, the equations that describe them, and their visual representations.

###[Concepts](./Front matter.md)

-   ![p=(p_x,p_y,p_z)](./images/45ccf2f30d3256d7ab9bf269e08c41de61396494.png): a _point_ in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png)
-   ![\vec{v}=(v_x,v_y,v_z)](./images/87c95a73f484d93d31b33d580a161c30cea133fe.png): a _vector_ in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png)
-   ![\hat{v}=\frac{ \vec{v} }{ \|\vec{v}\| }](./images/f640b03cb278770eee56f4de8124c1fa96706340.png): the _unit vector_ in the same direction as the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png)
-   An infinite line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) is a one-dimensional space defined in one of several possible ways:
    -   ![\ell: \{ p_{\textrm{o}}+t\:\vec{v}, t \in \mathbb{R} \}](./images/63b9e1bcc93aac5c35dc40510509205c82041bae.png): a _parametric equation_ of a line with direction vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) passing through the point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png)
    -   ![\ell: \left\{ \frac{x - p_{\textrm{o}x}}{v_x}
        = \frac{y - p_{\textrm{o}y}}{v_y} = \frac{z - p_{\textrm{o}z}}{v_z} \right\}](./images/99ed8bf865b429d48f71179b95fb07cbe662dfc5.png): a _symmetric equation_
-   An infinite plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) is a two-dimensional space defined in one of several possible ways:
    -   ![P: \left\{ Ax+By+Cz=D \, \right\}](./images/9ddcaa092d77d6b1b6981d9f79e1d5d649269235.png): a _general equation_
    -   ![P: \{ 				    		p_{\textrm{o}}+s\,\vec{v} + t\,\vec{w}, \; s,t \in \mathbb{R} \}](./images/4717eb0dd2f9cf1e5ce2a177ecd1806639c83718.png): a _parametric equation_
    -   ![P: \left\{ 				    				\vec{n} \cdot[ (x,y,z) - p_{\textrm{o}} ] = 0 \,\right\}](../Images/152619953d7ca5bab185f313b14543a2d1aef8cb.png): a _geometric equation_ of the plane that contains point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png) and has normal vector ![\hat{n}](./images/d6198b5666fb3a4222e792b72a973ec953451382.png)
-   ![d(a,b)](./images/8f9da0843ab48eee768eb28bcb2d266ed57e13d1.png): the shortest _distance_ between geometric objects ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)

###[Points](./Front matter.md)

We can specify a point in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) by its coordinates ![p=(p_x,p_y,p_z)](./images/45ccf2f30d3256d7ab9bf269e08c41de61396494.png), which is similar to how we specify vectors. In fact, the two notions are equivalent: we can either talk about the destination point ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) or the vector ![\vec{p}](./images/4a51d8c8da47c0cee3671be5cad1c0bd4f2cada8.png) that takes us from the origin to the point ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png). This equivalence lets us add and subtract vectors and points. For example, ![\vec{d}=q-p](./images/6f75bda354ffd929155820ebd111fca8eba7e41d.png) denotes the displacement vector that takes the point ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) to the point ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png).

We can also specify a point as the intersection of two lines. As an example in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png), let’s define ![p=(p_x,p_y)](./images/344cd2d3542d0946303ebd673403b9d906a3fbdb.png) to be the intersection of the lines ![x -y = -1](./images/0a6d884653e6464a73181431080abd720751e2fe.png) and ![3x + y = 9](./images/298b309b0406940765edd26b8bfb1f41f7225486.png). We must solve the two equations simultaneously to find the coordinates of the point ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png). We can use the standard techniques for solving equations to find the answer. The intersection point is ![p=(2,3)](./images/bfd8208f881350fb61b65f57686d0bb22f6fec8d.png). Note that for two lines to intersect at a point, the lines must not be parallel.

![intersecting_lines](./images/intersecting_lines.png)

Figure 4.1: Two non-parallel lines in ![\mathbb{R}^2](./images/95400ab39ca45e382fe8897a6d187c7836ff8db6.png) intersect at a point.

#####[Example 1](./Front matter.md)

Find where the lines ![x + 2y = 5](./images/ba3501c6b0628631cab9f573a53506d29f0f5439.png) and ![3x + 9y = 21](./images/0b56d4475bbebdd63c973e2e5b1aa66395a08104.png) intersect. To find the point of intersection, we solve these equations simultaneously and obtain the point ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that is contained in both lines. The answer is the point ![p=(1,2)](./images/91542a3265335716313533df919382a5cedc7511.png).

In three dimensions, a point can also be specified as the intersection of three planes. This is precisely what happens when we solve equations of the form:

![\begin{align*}
A_1x +B_1y+C_1z 	&= D_1,	\\
A_2x +B_2y+C_2z 	&= D_2,	\\
A_3x +B_3y+C_3z 	&= D_3.
\end{align*}](./images/ec45d494a28bbb5f23d02e5cd9ee92ed5e6b4a13.png)

To solve this system of equations, we must find the point ![(x_o,y_o,z_o)](./images/6a14bdc048f82b97df9e28dd8bb2023faaec3307.png) that satisfies all three equations, which means this point is contained in all three planes.

![three-planes-intersect-at-a-point](./images/three-planes-intersect-at-a-point.png)

Figure 4.2: Three non-parallel planes in ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png) intersect at a point.

###[Lines](./Front matter.md)

A line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) is a one-dimensional space that is infinitely long. There are several equivalent ways to specify a line in space.

The _parametric equation_ of a line is obtained as follows. Given a direction vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and some point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png) on the line, we define the line as the following set:

![\ell: \; \{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)=p_{\textrm{o}}+t\:\vec{v}, t \in \mathbb{R} \}.](./images/09a7519b2d3edbc2c361824717bf078bdd822dbd.png)

The line consists of all the points ![(x,y,z)](./images/ab8147f25510506ccc5d4d1090c36e74e6becf81.png) that can be reached by starting from the point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png) and adding any multiple of the direction vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), as illustrated in[Figure 4.3](./Chapter 4_ Geometric aspects of linear algebra.md). We say the line is _parametrized_ by the variable ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png).

![lines_and_planes_line_p0_vecv](./images/lines_and_planes_line_p0_vecv.png)

Figure 4.3: All points on the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) can be reached by starting from the point ![p_{\textrm{o}}](./images/0c1edb1cdf43894876062d6769578fba42218fe4.png) and adding some multiple of the direction vector ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png).

The _symmetric equation_ is an equivalent way to describe a line that does not require an explicit parametrization. The equations that correspond to each coordinate in the parametric equation of a line are

![x = p_{\textrm{o}x} + t\,v_x, \quad
y = p_{\textrm{o}y} + t\,v_y, \quad
z = p_{\textrm{o}z} + t\,v_z.](./images/023ed5f59ce762d876a6404cf754c6c7f70ab475.png)

When we solve for ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) in these equations and equate the results, we obtain the _symmetric equation_ of a line:

![\ell: \; \left\{ \; 
\frac{x - p_{\textrm{o}x}}{v_x} =
\frac{y - p_{\textrm{o}y}}{v_y} =
\frac{z - p_{\textrm{o}z}}{v_z}
\right\}\!.](./images/996eb6287344920d244c44ec859b7f099d0f0158.png)

Note the parameter ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) does not appear. The symmetric equation specifies the line as the relationships between the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png) coordinates that hold for all points on the line.

You’re probably most familiar with the symmetric equation of lines in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png), which does not involve the variable ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png). For nonvertical lines in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png) (![v_x \neq 0](./images/905ccaf5a02812c3803f51ae866cfb5be87a7f54.png)), we can think of ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) as a function of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and write the equation of the line in the equivalent form:

![\frac{x - p_{\textrm{o}x}}{v_x} =
\frac{y - p_{\textrm{o}y}}{v_y}
\qquad  \Rightarrow
\qquad
y(x) = mx + b,](./images/1ec4e08ad3760ee73efd98c14eb39989a0e04b64.png)

where ![m=\frac{v_y}{v_x}](./images/a80721593c0e315494c615822cca4db334fcf1f0.png) and ![b=p_{\textrm{o}y}-\frac{v_y}{v_x}p_{\textrm{o}x}](./images/2646312c8d79a4650c0317a77cb9f3183406cabf.png). The equation ![m=\frac{v_y}{v_x}](./images/a80721593c0e315494c615822cca4db334fcf1f0.png) makes sense intuitively: the slope of a line ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) corresponds to how much the line “moves” in the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-direction divided by how much the line “moves” in the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-direction.

Another way to describe a line is to specify two points that are part of the line, as shown in[Figure 4.4](./Chapter 4_ Geometric aspects of linear algebra.md). The equation of a line that contains the points ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) can be obtained as follows:

![\ell: \; \{ \vec{x}=p+t \: (q-p), \; t \in \mathbb{R} \},](./images/af3dc4c93dbbd685b1c66cd7a69fae34e7f6329f.png)

where ![(q-p)](./images/bd15013fc2b99b83532bd670bb6f00f1298f4c46.png) plays the role of the direction vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) for this line. Any vector parallel to the line can be used as the direction vector for the line.

![lines_and_planes_line_p_q](./images/lines_and_planes_line_p_q.png)

Figure 4.4: The line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) is defined by the points ![p](./images/b11f2617243b9603c98df21c26f4fc4d87ffa1fb.png) and ![q](./images/8352363828e0228195580ba48c9cde386d9f6849.png).

#####[Example 2](./Front matter.md)

Find the parametric equation of the line that passes through the points ![p=(1,1,1)](./images/6f188a13b7235763c0524efc1c2af717395e35d2.png) and ![q=(2,3,4)](./images/2f9181dc5f2881fe780074955310ed2ded9f7186.png). What is the symmetric equation of this line?

Using the direction vector ![\vec{v}=q-p=(1,2,3)](./images/10e3f651906391d0a1d5766672ab263ad673542b.png) and the point ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) on the line, we can write a parametric equation for the line as ![\{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)=(1,1,1) +t(1,2,3), t \in \mathbb{R} \}](./images/9e8d22a2df50e2d373faf4e4fccf077fcac68b4b.png). Note that a parametric equation using the direction vector ![(-1,-2,-3)](./images/fd3844d49379bf7e289d0d46ad37cdbd8240a519.png) would be equally valid: ![\{ (1,1,1) +t(-1,-2,-3), t \in \mathbb{R} \}](./images/0ef20a529b4332c50e0b61b303e7f652eb0c40f4.png). The symmetric equation of the line is ![\frac{x - 1}{1} = \frac{y -1}{2} = \frac{z - 1}{3}](./images/4c4d41dae832f48a4c87546998747c62d523d90e.png).

####[Lines as intersections of planes](./Front matter.md)

In three dimensions, the intersection of two non-parallel planes forms a line. For example, the intersection of the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane ![P_{xy} : \{ (x,y,z) \in \mathbb{R}^3 \; | \; z=0 \}](./images/7b356f4a597f6ac4996c72299b41014e892703b0.png) and the ![xz](./images/3b2b802e0cb4f5f7ef1cf6e42fd614b66c2ea226.png)\-plane ![P_{xz} : \{ (x,y,z) \in \mathbb{R}^3 \; | \; y=0 \}](./images/e515d873201c5ec99be404e28a0cf266d4b30376.png) is the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis: ![\{ (x,y,z) \in \mathbb{R}^3 \; | \; (0,0,0) + (1,0,0)t, \; t \in \mathbb{R} \}](./images/9d6bb3249f479224a1d653dd3f28ddec91c13f00.png). For this simple case, we can imagine the two planes (use your hands) and visually establish that they intersect along the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis. Wouldn’t it be nice if there was a general procedure for finding the line of intersection of two planes?

![1000px-Intersecting_planes](./images/1000px-Intersecting_planes.png)

Figure 4.5: The ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-axis is the intersection of the ![xy](./images/e819445128c475992b46e256b3c37c0307f3d821.png)\-plane and the ![xz](./images/14f66ea3df0e0387c2dc0b38fdcf06401967ede1.png)\-plane.

You already know such a procedure! The line of intersection between the planes ![A_1x +B_1y+C_1z=D_1](./images/1698437e1757ec01b363159777603ede0636e07c.png) and ![A_2x +B_2y+C_2z=D_2](./images/c71683869acdbef6f1511a7125cd13558cc8a6d7.png) is the solution of the following set of linear equations:

![\begin{align*}
A_1x +B_1y+C_1z 	&= D_1,	\\
A_2x +B_2y+C_2z 	&= D_2.
\end{align*}](./images/a0abab4d4701bd11523c382d6a0d20562f9bb242.png)

#####[Example 3](./Front matter.md)

Find the intersection of the planes ![0x+0y+1z=0](./images/26a64ac94132e692e53a7c1c04cbc10244bfc3e3.png) and ![0x+1y+1z=0](./images/9c0af9ad17867225209cf844b9f3e89a188f5ad7.png). We follow the standard Gauss–Jordan elimination procedure we learned in[Chapter 3](./Chapter 3_ Computational linear algebra.md): construct an augmented matrix, perform row operations (denoted ![\sim](./images/a004754d720c0f43a5fa401c099053ae7fef796a.png)), obtain the RREF, and interpret the solution:

![\left[ \begin{array}{ccc|c}
0 & 0 & 1  \; \; & \;  0 \\
0 & 1 & 1  \; \;  &\;  0 
\end{array}\right]
\; \; 
\sim
\; \; 
\left[ \begin{array}{ccc|c}
0 & 1 & 1  \; \; & \;  0 \\
0 & 0 & 1  \; \;  &\;  0 
\end{array}\right]
\; \; 
\sim
\; \; 
\left[ \begin{array}{ccc|c}
0 & 1 & 0  \; \; & \;  0 \\
0 & 0 & 1  \; \;  &\;  0 
\end{array}\right]							    
\!\!.](../Images/d45ded6c557fcaa93feb9b4d3aa6c1cfebf5c1ed.png)

The first column is a free variable ![t \in \mathbb{R}](./images/27da8cc414f17278d49c7116607963991c3cd05f.png). The solution is the line

![\left\{ \!\!
\begin{array}{rl}
x \!\!\!\!\! &= t  \\
y \!\!\!\!\! &= 0 \\
z \!\!\!\!\! &= 0
\end{array}, \; \; 
\forall t \in \mathbb{R}
\right\}
\; 		    = 		     \; 
\left\{
\begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}
+ t \!
\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix},\; \; \; 
\forall t \in \mathbb{R}
\right\}\!,](./images/b78a87ca3dcdeac6f6b31a2be5a7234f12432887.png)

which corresponds to the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis.

###[Planes](./Front matter.md)

A plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) is a two-dimensional space with infinite extent. In general, we specify a plane through a constraint equation that must be satisfied by all points in the plane:

![P: \;  \{ (x,y,z) \in \mathbb{R}^3 \; | \;  Ax + By + Cz  = D\}.](./images/c4662207ef1eeca0819ac5895d702c2eda0e29da.png)

The plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) is the set of all points ![(x,y,z) \in \mathbb{R}^3](./images/877b62a173c53ca5831f3444d0937c7a03b93642.png) that satisfy the equation ![Ax + By + Cz  = D](./images/5f91c0ddbb6e860c1501e473f074222c873d0e08.png). The equation ![Ax + By + Cz  = D](./images/5f91c0ddbb6e860c1501e473f074222c873d0e08.png) is called the _general equation_ of the plane. This definition represents the _algebraic view_ of planes, which is useful for calculations.

There is an equally useful geometric view of planes. A plane can be specified by a _normal vector_ ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png) and some point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png) in the plane. The normal vector ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png) is perpendicular to the plane: it sticks out at right angles to the plane like the normal force between surfaces in physics problems. All points in the plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) can be obtained by starting from the point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png) and moving in a direction orthogonal to the normal vector ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png). The geometric formula of a plane is

![P: \; \;  \vec{n} \cdot[ (x,y,z) - p_{\textrm{o}} ] = 0.](../Images/a928708f5c8a2b15c6e2759821b7ffacfd451b01.png)

Recall that the dot product of two vectors is zero, if and only if these vectors are orthogonal. In the above equation, the expression ![[(x,y,z) - p_{\textrm{o}}]](../Images/93748512ffa1efc5a111f55811f84f8c6acd8d18.png) forms an arbitrary vector with one endpoint at ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png). From all these vectors, we select _only_ those that are perpendicular to ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png), and thus we obtain all the points in the plane.

![lines_and_planes_plane_p0_vecn](./images/lines_and_planes_plane_p0_vecn.png)

Figure 4.6: All points on the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) can be reached by starting from the point ![p_{\textrm{o}}](./images/0c1edb1cdf43894876062d6769578fba42218fe4.png) and moving perpendicularly to the normal vector ![\vec{n}](./images/7da6b307d5458666fc055f8a1f35f4dc2c7b11d7.png).

The geometric equation ![\vec{n} \cdot[ (x,y,z) - p_{\textrm{o}} ] = 0](../Images/c9b03b10a641578b860d1aaaadbfdef6fd999ff2.png) is equivalent to the general equation ![Ax + By + Cz  = D](./images/5f91c0ddbb6e860c1501e473f074222c873d0e08.png). We can find the parameters ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png), and ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png) by calculating the dot product: ![A = n_x, B=n_y, C=n_z](./images/e78e369b9bd531b2fbd737f814f1d6c2cedd10d6.png), and ![D = \vec{n} \cdot p_{\textrm{o}} = n_xp_{\textrm{o}x} + n_yp_{\textrm{o}y} + n_yp_{oz}](./images/8db188e6691cc31f3eea04eb676809d14858ce74.png).

Observe that scaling the general equation of a plane by a constant factor does not change the plane: the equations ![Ax + By + Cz  = D](./images/5f91c0ddbb6e860c1501e473f074222c873d0e08.png) and ![\alpha Ax + \alpha By + \alpha Cz  = \alpha D](./images/2e54e993dfe0286e96f1e64ef93bcfde97439fc4.png) define the same plane. Similarly, the geometric equations ![\vec{n} \cdot[ (x,y,z) - p_{\textrm{o}} ] = 0](../Images/c9b03b10a641578b860d1aaaadbfdef6fd999ff2.png) and ![\alpha\vec{n} \cdot[ (x,y,z) - p_{\textrm{o}} ] = 0](../Images/318cc98f12d2c57ff6f5dfa6d7625c33349b2894.png) define the same plane. In each case, the direction of the normal vector ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png) is important, but not its length.

We can also give a _parametric equation_ of a plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png). If we know a point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png) in the plane and two linearly independent vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) that lie in the plane, then a parametric equation for the plane can be obtained as follows:

![P: \; \{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)=p_{\textrm{o}}+s\,\vec{v} + t\,\vec{w}, \; s,t \in \mathbb{R} \}.](./images/2245957eb246a6347e7a47da72481b97921b2f20.png)

Since a plane is a two-dimensional space, we need two parameters (![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png) and ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png)) to describe the location of arbitrary points in the plane.

Suppose we’re given three points ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png), ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png), and ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png) that lie in the plane. How can we find the geometric equation for this plane ![\vec{n} \cdot[ (x,y,z) - p_{\textrm{o}} ] = 0](../Images/c9b03b10a641578b860d1aaaadbfdef6fd999ff2.png)? We can use the point ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) as the reference point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png), but how do we find the normal vector ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png) for the plane? The trick is to use the cross product. First we build two vectors that are parallel to the plane, ![\vec{v} = q-p](./images/35b6c4135c90d40cc5db2b8c4f095681dbb40ff6.png) and ![\vec{w} = r-p](./images/0174a691c2d1554bd6b536bcb42e97c9dcf62fd1.png). Then compute their cross product to find a vector that is perpendicular to both of them, and hence normal to the plane:

![\vec{n} = \vec{v} \times \vec{w} =  (q - p) \times (r - p).](./images/130bc014fada05674e28d07be997cbf54d1ddcbe.png)

We can use the vector ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png) to write the geometric equation of the plane ![\vec{n} \cdot[ (x,y,z) - p ] = 0](../Images/f6b351fcd421a87fd9134bd04f1133a2b9b061ec.png). Recall that the cross product of two vectors is perpendicular to both vectors. This property of the cross product makes it the perfect tool for finding normal vectors. This procedure is illustrated in[Figure 4.7](./Chapter 4_ Geometric aspects of linear algebra.md).

![lines_and_planes_plane_points_p_q_r](./images/lines_and_planes_plane_points_p_q_r.png)

Figure 4.7: We can obtain the normal vector ![\vec{n}](./images/7da6b307d5458666fc055f8a1f35f4dc2c7b11d7.png) for the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) by starting from the three points ![p](./images/b11f2617243b9603c98df21c26f4fc4d87ffa1fb.png), ![q](./images/8352363828e0228195580ba48c9cde386d9f6849.png), and ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) which lie in the plane.

#####[Example 4](./Front matter.md)

Consider the plane that contains the points ![p=(1,0,0)](./images/4d6dc58c059c4ad69c19fa3daea28de36ab3a371.png), ![q =(0,1,0)](./images/cbc920cd837646c8a8fc15b103aece434ed0e538.png), and ![r=(0,0,1)](./images/d6a1a7955fcf8080d90cf8096baa3e8f01b99293.png). Find a geometric equation, a general equation, and a parametric equation for this plane.

We need a normal vector for the geometric equation. We can obtain a normal vector from the cross product of the vectors ![\vec{v} = q-p=(-1,1,0)](./images/0224bf375e9f36b0697ea083f0ea41b4807a9df9.png) and ![\vec{w} = r-p =(-1,0,1)](./images/16a3660ae584f99c7e3a7656973a83a75f3f40a1.png), which both lie in the plane. We obtain the normal ![\vec{n} = \vec{v} \times \vec{w} = (1,1,1)](./images/c803ccb4b1c7e6a2d2cf1fba54f6535ddeeaa280.png) and write the geometric equation as ![(1,1,1) \cdot[ (x,y,z) - (1,0,0) ] = 0](../Images/2dafcf0614a4c87c07bbdeb300ff41d8ce4f87de.png), using ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) as the point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png) in the plane. To find the general equation for the plane, we compute the dot product in the geometric equation and obtain ![1x+1y+1z - 1 = 0](./images/4dbe85f51cfda95d2837cd1452fc45f21c63c3a6.png), which is the same as ![x + y + z = 1](./images/3b656d13f760fcf6a40f5693a37e7cbee5062e35.png). The vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) obtained above can also be used in the parametric equation of the plane: ![\{ (1,0,0) + s(-1,1,0) + t(-1,0,1), \; s,t \in \mathbb{R} \}](./images/92cc8c1e2399bafce200734fde7347d9173abdd2.png).

###[Distance formulas](./Front matter.md)

We’ll now discuss three formulas for calculating distances: the distance between two points, the closest distance between a line and the origin, and the closest distance between a plane and the origin.

####[Distance between points](./Front matter.md)

The distance between points ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) is equal to the length of the vector that goes from ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) to ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png):

![d(p,q)
= \| q - p \|
= \sqrt{ (q_x-p_x)^2 + (q_y-p_y)^2 + (q_z-p_z)^2}.](./images/edfbff9a817f186fad245f180e81bc242b3de6c0.png)

####[Distance between a line and the origin](./Front matter.md)

The closest distance between the line with equation ![\ell: \{ 			p_{\textrm{o}}+t\:\vec{v}, t \in \mathbb{R} \}](./images/63b9e1bcc93aac5c35dc40510509205c82041bae.png) and the origin ![O=(0,0,0)](./images/0d113a5deff61789e9e07e9fc440c73e53774270.png) is given by the formula

![d(\ell,O) = \left\| p_{\textrm{o}} - \frac{  p_{\textrm{o}} \cdot \vec{v}  }{ \| \vec{v} \|^2 } \vec{v} \right\|.](./images/0ce98dd3c9353054bbc339d288b732cc46056610.png)

![lines_and_planes_dist_line_o](./images/lines_and_planes_dist_line_o.png)

Figure 4.8: The closest distance between the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) and the origin.

#####[Example 5](./Front matter.md)

The closest distance between the line ![\ell: \{ (4,5,6)+t(1,0,1), \; t \in \mathbb{R} \}](./images/35f16ad25368c2f00496b661091d3528cc9e3611.png) and the origin ![O=(0,0,0)](./images/0d113a5deff61789e9e07e9fc440c73e53774270.png) is calculated as follows:

![\begin{align*}
d(\ell,O)
&= 	\left\| (4,5,6) - \frac{  (4,5,6) \cdot (1,0,1)  }{ 1^2+0^2+1^2 } (1,0,1) \right\|		\\
&= 	\left\| (4,5,6) - \frac{  4+0+6  }{ 2 } (1,0,1) \right\|							\\
&=	\left\| ( -1,5,1) \right\|  \; = \; 	3\sqrt{3}.
\end{align*}](./images/67ea4750da98bf636fb27614c8416c64a0878242.png)

####[Distance between a plane and the origin](./Front matter.md)

The closest distance between the plane with geometric equation ![P: \; \vec{n} \cdot[ (x,y,z) - p_{\textrm{o}} ] = 0](../Images/3b42b973a9a9df3c0649f9575efbf864bc145a14.png) and the origin ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is given by

![d(P,O)= \frac{| \vec{n}\cdot p_{\textrm{o}} |}{ \| \vec{n} \| }.](./images/5e3d92f28c16dd55488ea43ad5f21704f693cfb9.png)

For example, the distance between the plane ![P: \; (-3,0,-4) \cdot[ (x,y,z) - (1,2,3)] = 0](../Images/202f81a5499371914c5e14c836e43797f40a40c4.png) and the origin is computed as

![\begin{align*}
d(P,O) &= \frac{| (-3,0,-4)\cdot (1,2,3) |}{ \| (-3,0,-4) \| } = \frac{| -3-12|}{5} = \frac{15}{5}  \; = \; 3.	
\end{align*}](./images/16afc1d596489ea21c0f3bb39f53e480b8d85b9e.png)

![lines_and_planes_dist_plane_o](./images/lines_and_planes_dist_plane_o.png)

Figure 4.9: The closest distance between the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) and the origin.

###[Discussion](./Front matter.md)

The distance formulas ![d(\ell,O)](./images/b9935015ec934e6b3d48e39566fbf3204480f2ad.png) and ![d(P,O)](./images/76bbf24171a19236b6abc8504c0539e8039a002e.png) are complicated expressions that involve dot products and vector lengths. To understand the logic behind these distance formulas, we need to learn a bit about _projective geometry_. The techniques of projective geometry allow us to measure distances between arbitrary points, lines, and planes. No new math operations are required. Instead, we’ll learn how to use a combination of vector subtraction, vector length, and the dot product to compute distances. Each distance function ![d(\cdot,\cdot)](./images/4f5655ad3e0028a94b6ba3cb8edb46f829ab8f27.png) corresponds to an abstract procedure with one or two steps which can be described using a vector diagram. Projections play a key role in projective geometry, so we’ll learn about them in detail in the next section.

###[Exercises](./Front matter.md)

E4.1 Define the line ![\ell: \{ (0,3)+t(1,-1), \; t \in \mathbb{R} \}](./images/5084f4b74f33fa7a08cee5024485acc6a338b64a.png). Find the closest distance between the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) and the origin.

E4.2 Find the closest distance between the origin and the line defined by ![\ell: \{ (0,0,3)+t(1,1,0), \; t \in \mathbb{R} \}](./images/56b83bc3e49f2d8592ac5845b8fd62e56d394ea6.png).

E4.3 Find the distance between the plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) with geometric equation ![(1,1,1)\cdot[ (x,y,z)-(4,5,6) ]=0](../Images/1ff723d8c0b4cd1f8d4985a5bedd07337e5ef54d.png) and the origin.

E4.4 Find the general equation of the line that passes through the points ![(0,5)](./images/c01bf1450d4d39460c77627bb80a969b1a0d4232.png) and ![(6,-7)](./images/d3d53963cda371082ba1096989f4ea8b3c79c2aa.png) in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png).

E4.5 Given the point ![r\!=\!(1,3,0)](./images/06ef829993cccf412bacdc2b9ffb0a8e370bbac8.png), the line ![\ell\!:\!\{ (0,0,2) + t(1,-1,0), t\!\in~\!\!\mathbb{R} \}](./images/58efea4150eb877b7144aa7119c1b1e1870e4d32.png), the plane ![P: x+y+z=1](./images/d746e08730e8d30567291ad98012f8b78141cb08.png), and the origin ![O=(0,0,0)](./images/0d113a5deff61789e9e07e9fc440c73e53774270.png), compute the following closest distances:

1.  ![d(r,O)](./images/19a7c36b9a56aadc5fa1f0ee2b643a7a66976328.png)
2.  ![d(\ell,O)](./images/709deed432f37b4d3187c96585ebb71b8e8c1f33.png)
3.  ![d(P,O)](./images/a189345d7e48662c427c328fed0b93bca269291a.png)
4.  ![d(r,\ell)](./images/c99c4132ce9d2eea61821a5ac3265195cd266771.png)
5.  ![d(r,P)](./images/3de975685ddbef0509921e6a8314e66fa4c3f88c.png)
6.  ![d(\ell,P)](./images/23abb28217d4177f2a30cff23d1ab689d54b7b32.png)

Draw a diagram and find the closest distances visually. Label the point ![p_\ell = (0,0,2)](./images/e0b18c8fb652acd07a0f6d3d1cbe8dc656b241a3.png), which is an arbitrary point in the line, and the point ![p_P = (1,0,0)](./images/5fbb88f6288414307a8d1af54274061c8b5f2e79.png), which is an arbitrary point in the plane. Don’t look for a one-size-fits-all formula for the different cases; derive the appropriate formula for each case starting from the basic projection operations ![\Pi_{\ell}](./images/01d855befc1fcc71eb4f11a72bf8a75abbc386d7.png) and ![\Pi_{P}](./images/ced20ab32ffba6906845b9e2493cf9925a6c382a.png).

##[4.2 Projections](./Chapter 4_ Geometric aspects of linear algebra.md)

In this section we’ll learn to compute projections of vectors onto lines and planes. Given an arbitrary vector, we’ll find how much of this vector points in a given direction (projection onto a line). We’ll also find the part of the vector that lies in some plane (projection onto a plane). The dot product, ![\vec{u}\cdot \vec{v} = u_1v_1 + u_2v_2 + u_3v_3](./images/21ce043ab82562c8024226a589afc0087d1945a3.png), will play a central role in these calculations.

**Each projection formula corresponds to a vector diagram**. Vector diagrams, also known as “picture proofs,” are used to describe the precise sequence of operations for computing a projection. Focussing on vector diagrams makes it much easier to understand projection and distance formulas. Indeed, the pictures in this section are a heck of a lot more important than the formulas. Be sure you understand each vector diagram, and don’t worry about memorizing the corresponding formula. You can easily reproduce the formula by starting from the vector diagram.

###[Concepts](./Front matter.md)

-   ![S\subseteq \mathbb{R}^n](./images/041bf9efc49c2d62eccc3241fa030ca42e2d1163.png): ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) is a _vector subspace_ of ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png). In this section, we assume ![S \subseteq \mathbb{R}^3](./images/11a240a64686456f908af7b10fea4831aff236f7.png). The subspaces of ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) are lines ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) and planes ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) that pass through the origin.
-   ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png): the orthogonal complement to ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png), ![S^\perp\! \eqdef\! \{ \vec{w}\!\in\!\mathbb{R}^n \; | \; \vec{w} \cdot S = 0\}](./images/7631e4fc8b2ebcf1a40dd260e8a150a25084794a.png). The symbol ![^\perp](./images/bf3f26af68cd10841ca1f5a140736b3a4046bc32.png) stands for _perpendicular to_.
-   ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png): the _projection_ onto the subspace ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png).
-   ![\Pi_{S^\perp}](./images/11fcfc12e8198c56be561ee9aa01f7cd43367253.png): the projection onto the subspace ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png).

###[Definitions](./Front matter.md)

Let ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) be a _vector subspace_ of ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png), denoted ![S \subseteq \mathbb{R}^n](./images/041bf9efc49c2d62eccc3241fa030ca42e2d1163.png). In this section, we’ll focus on the subspaces of the vector space ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) because they are easy to visualize and understand intuitively. The vector subspaces of ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) are lines and planes that pass through the origin. We defer the general discussion of subspaces in ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) dimensions until[Section 4.4](./Chapter 4_ Geometric aspects of linear algebra.md).

The projection operation onto the subspace ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) is a linear transformation that takes as inputs vectors in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png), and produces outputs in the subspace ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png):

![\Pi_S : \mathbb{R}^3 \;  \to \; S.](./images/77acbe927b8dd0518b6540dcafc6c1b40e937351.png)

The transformation ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png), pronounced “projection onto ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png),” cuts off all parts of the input that do not lie within the subspace ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png). We can understand ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png) by analyzing its action for different inputs:

-   If ![\vec{v} \in S](./images/509bab64dc06f23e6f1eb603c0465659df0dc4e9.png), then ![\Pi_S(\vec{v}) = \vec{v}](./images/1dfdb39ae90f3f2d8f6f609aabca8a791af2f515.png).
-   If ![\vec{w} \in S^\perp](./images/4e13119522db316d7bccc42513f7a6450b62547b.png), then ![\Pi_S(\vec{w}) = \vec{0}](./images/11d0f7c7ea5ffee2d63438369d5b7c72feff2f51.png).
-   Linearity and the above two conditions imply that, for any vector ![\vec{u}=\alpha\vec{v}+ \beta \vec{w}](./images/2ef259be1adf729c894c2b9b513b759da920aac9.png) with ![\vec{v} \in S](./images/509bab64dc06f23e6f1eb603c0465659df0dc4e9.png) and ![\vec{w} \in S^\perp](./images/4e13119522db316d7bccc42513f7a6450b62547b.png), we have
    
    ![\Pi_S(\vec{u}) = \Pi_S(\alpha\vec{v}+ \beta \vec{w}) = \alpha\vec{v}.](./images/574a770cdab7f2ecd85d6ae91f88d88c37171bce.png)
    

The _orthogonal subspace_ to ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) is the set of vectors that are perpendicular to all vectors in ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png):

![S^\perp 
\; \eqdef \; 	\{ \, \vec{w} \in \mathbb{R}^3 \; | \; \vec{w}  \cdot \vec{s} = 0, \; \forall \vec{s} \in S \, \}.](./images/3117cf3a7ec1c63c798128c8886854282205d642.png)

The transformation ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png) “projects” to the space ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) in the sense that, no matter which vector ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) you start from, applying the projection ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png) results in a vector that is in ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png):

![\forall \vec{u} \in \mathbb{R}^3, \quad \Pi_S(\vec{u}) \in S.](./images/bbb3cc4760426aef8df509688586dc0ad40b5e28.png)

All parts of ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) in the _perp_\-space ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) were killed by ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png). Meet ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png)—the ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)\-_perp_ killer.

We can split the set of all vectors ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) into two disjoint sets: vectors entirely contained in ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) and vectors perpendicular to ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png). We say ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) decomposes into the _direct sum_ of the subspaces ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) and ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png):

![\mathbb{R}^3 = S \oplus S^\perp.](./images/c2fac4473649e4c3fa21253fd6583685f5dbb306.png)

Any vector ![\vec{u}\in \mathbb{R}^3](./images/0e8dbb310d1b010a998b7494aeb8abfb51001b01.png) can be split into an ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)\-part ![\vec{v}=\Pi_S(\vec{u})](./images/d76b6d292b83e005d896d2f2e99af958983b3816.png) and a ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png)\-part ![\vec{w}=\Pi_{S^\perp}(\vec{u})](./images/8ea4837016b697412f32a0071f4e32a7e33a63d3.png), such that

![\vec{u}=\vec{v} + \vec{w}.](./images/62d2b1ea3bc70bbfb48d4d303458862c15a7916e.png)

A defining property of projections is that they are _idempotent operations_, meaning it doesn’t matter if you project a vector once, twice, or a million times; the result will always be the same:

![\Pi_S( \vec{u} ) = \Pi_S( \Pi_S( \vec{u} )) = \Pi_S(\Pi_S(\Pi_S(\vec{u} ))) = \ldots.](./images/c36cbed1618f00986f9f6287e55ff96f78f1233d.png)

Once you project a vector onto the subspace ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png), any further projections to ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) have no effect.

In the remainder of this section, we’ll derive formulas for projections onto lines and planes that pass through the origin.

###[Projection onto a line](./Front matter.md)

Consider the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) passing through the origin with direction vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png):

![\ell: \; \{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)=\vec{0}+ t\,\vec{v},  \; t \in \mathbb{R} \}.](./images/d33b485b6e4b2fa40829ec8baf558ded7cac4655.png)

The projection onto ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) for an arbitrary vector ![\vec{u} \in \mathbb{R}^3](./images/0e8dbb310d1b010a998b7494aeb8abfb51001b01.png) is given by the formula

![\Pi_\ell( \vec{u} ) = \frac{  \vec{u} \cdot \vec{v}  }{ \| \vec{v} \|^2 } \vec{v}.](./images/6784d2698ca840d2b497d041af2f480c100b6c53.png)

![lines_and_planes_projection_onto_line](./images/lines_and_planes_projection_onto_line.png)

Figure 4.10: The vector ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png) can be decomposed into the sum of two projections defined with respect to the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png). The projection ![\Pi_\ell( \vec{u} )](./images/5ffc789966f3e28b3df45f8a6d66ef3c23949289.png) is parallel to the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png), while the projection ![\Pi_{\ell^\perp\!}(\vec{u})](./images/9f02644d8db28094f39f0fd59bce61d0e278b0d9.png) is perpendicular to the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png).

The orthogonal complement to the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) consists of all vectors perpendicular to the direction vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). Mathematically speaking,

![\ell^\perp: \; \; \{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)\cdot \vec{v} = 0 \}.](./images/48bf7e0ffdbd72b51e197a3cdbd6f4fd8bc79842.png)

Recognize that the equation ![(x,y,z)\cdot \vec{v} = 0](./images/80b61f852e847c382829c8c96f9b52a6a92546b6.png) defines a _plane_. The orthogonal complement for a line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) with direction vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is a plane with normal vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). Makes sense, yes?

We can easily find the projection operation onto ![\ell^\perp](./images/b2fc87ea8f3a3c14bfa6164d256e4a09b8c3d95b.png) as well. Any vector can be written as the sum of an ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) part and a ![\ell^\perp](./images/b2fc87ea8f3a3c14bfa6164d256e4a09b8c3d95b.png) part: ![\vec{u}=\vec{v} + \vec{w}](./images/45e47ed7c001a3ee6accee19ab129206cebc4a94.png), where ![\vec{v}=\Pi_\ell(\vec{u}) \in \ell](./images/abdeb33196a15bea60d74d35084d841f29e1a331.png) and ![\vec{w}=\Pi_{\ell^\perp}(\vec{u}) \in  \ell^\perp](./images/d99bb7f990f30c8333c4a0a799326db53465bd70.png). To obtain ![\Pi_{\ell^\perp}(\vec{u})](./images/527fb094ec848fa87c9bd60758237f3eedf9efbb.png), subtract the ![\Pi_\ell](./images/01d855befc1fcc71eb4f11a72bf8a75abbc386d7.png) part from the original vector ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png):

![\Pi_{\ell^\perp}(\vec{u}) = \vec{w} = \vec{u}-\vec{v}
= \vec{u} - \Pi_{\ell}(\vec{u})
= \vec{u} - \frac{ \vec{u} \cdot \vec{v} }{ \| \vec{v} \|^2 } \vec{v}.](./images/bf9003bcca0f6636ab8e417a0983fe38353cffd5.png)

We can think of ![\Pi_{\ell^\perp}(\vec{u}) = \vec{w}](./images/ea8d4b5719a02d58513ba38a57145067dded61f6.png) as the part of ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) that remains after we’ve removed the ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png)\-part.

#####[Example 1](./Front matter.md)

Consider the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) defined by the parametric equation ![\{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)=t(1,2,3), t \in \mathbb{R} \}](./images/ee9c6322443792acf817af9abe07a162b0b718e7.png). Find the projection of the vector ![\vec{u}=(4,5,6)](./images/e49d91d577d668b75e188c1d4d9cf6d3a90a991a.png) onto ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png). Find the projection of ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) onto ![\ell^\perp](./images/b2fc87ea8f3a3c14bfa6164d256e4a09b8c3d95b.png) and verify that ![\Pi_\ell(\vec{u}) + \Pi_{\ell^\perp}(\vec{u}) = \vec{u}](./images/06e22de578e211c4acce0ccfd9c89e8dab2108b2.png).

The direction vector of the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) is ![\vec{v}=(1,2,3)](./images/d11523070a2a18de48c687d12d5085f1b839ebe1.png), so ![\Pi_\ell(\vec{u}) = \frac{  \vec{u} \cdot \vec{v}  }{ \| \vec{v} \|^2 } \vec{v}
= \frac{16}{7}\vec{v} = (\frac{16}{7}, \frac{32}{7}, \frac{48}{7})](./images/600a55bce0ca03091ef53af94c818a207d0c2998.png). Next, using the formula ![\Pi_{\ell^\perp}(\vec{u}) =  \vec{u} - \frac{ \vec{u} \cdot \vec{v} }{ \| \vec{v} \|^2 } \vec{v}](./images/e69cc09dfc24ea1829ced48fe74720f98d93d3c6.png), we find ![\Pi_{\ell^\perp}(\vec{u}) = (\frac{12}{7}, \frac{3}{7}, \frac{-6}{7})](./images/8380cd00a3b0af71122d7c974e33a12534aca8c8.png). Observe that ![(\frac{12}{7}, \frac{3}{7}, \frac{-6}{7}) \cdot \vec{v}=0](./images/2fab9ffd508b94abb7b6a400272c3de4101fc870.png), which shows the vector ![\Pi_{\ell^\perp}(\vec{u})](./images/527fb094ec848fa87c9bd60758237f3eedf9efbb.png) is indeed perpendicular to ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png). Adding the results of the two projections, we obtain the whole ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png): ![(\frac{16}{7}, \frac{32}{7}, \frac{48}{7})+ (\frac{12}{7}, \frac{3}{7}, \frac{-6}{7})
= (\frac{28}{7}, \frac{35}{7}, \frac{42}{7})=(4,5,6)=\vec{u}](./images/daa961ef35af7395d7554cfff9c5aad87be27426.png).

###[Projection onto a plane](./Front matter.md)

Now consider the two-dimensional plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) passing through the origin with normal vector ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png):

![P: \; \; \{ (x,y,z) \in \mathbb{R}^3 \; | \; \vec{n} \cdot (x,y,z) = 0 \}.](./images/835f064dd2b0a6cba23441a3aec25c1152d8cd19.png)

The perpendicular space ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) is a line with direction vector ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png):

![P^\perp: \; \{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)=\vec{0} + t\,\vec{n}, \; t \in \mathbb{R} \}.](./images/5fbb919ffe584edbaefeb728c17e3d7181397fb3.png)

Again, the vector space ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) decomposes into the direct sum of ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and ![P^\perp](./images/b84ae344bc6b0a02b8daaf254a721e2ad9f820a6.png): ![\mathbb{R}^3= P \oplus P^\perp](./images/24825284f71d181cbafea0e1195e87c2b3b26523.png).

We want to find ![\Pi_P](./images/ced20ab32ffba6906845b9e2493cf9925a6c382a.png), but it will actually be easier to find ![\Pi_{P^\perp}](./images/48d7743d010ec3cf5126ff1b17f999c5ae46c648.png) first and then compute ![\Pi_P(\vec{u})](./images/13bada21159766be2649b130208f7d2c5c11308d.png) using ![\Pi_P(\vec{u}) = \vec{v} = \vec{u} - \vec{w}](./images/ada8ccb7fee0b891cd3d43d042519aa657f7abf5.png), where ![\vec{w}=\Pi_{P^\perp}(\vec{u})](./images/67965c71ebf0a745f2020c764fa51ab509b361df.png). See[Figure 4.11](./Chapter 4_ Geometric aspects of linear algebra.md) for an illustration.

![lines_and_planes_projection_onto_plane](./images/lines_and_planes_projection_onto_plane.png)

Figure 4.11: Any vector ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png) can be written as the sum of two projections defined with respect to the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png). The projection ![\Pi_P( \vec{u} )](./images/600885765d147b5c8613661529e2646f57b15155.png) is parallel to the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png), while the projection ![\Pi_{P^\perp\!}(\vec{u})](./images/fd27a21cc3a32753c307a238cfecb41d2af24337.png) is perpendicular to the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png).

Since ![P^\perp](./images/b84ae344bc6b0a02b8daaf254a721e2ad9f820a6.png) is a line, we know the formula for projecting onto it is

![\Pi_{P^\perp}( \vec{u} ) = \frac{ \vec{u} \cdot \vec{n} }{ \| \vec{n} \|^2 } \vec{n}.](./images/23c559220e5f6c844ea212a77d80af4ec9fd835a.png)

We can now obtain the formula for ![\Pi_P](./images/ced20ab32ffba6906845b9e2493cf9925a6c382a.png):

![\Pi_P(\vec{u}) = \vec{v} = \vec{u}-\vec{w} 
= \vec{u} - \Pi_{P^\perp}(\vec{u}) 
= \vec{u} - \frac{ \vec{u} \cdot \vec{n} }{ \| \vec{n} \|^2 } \vec{n}.](./images/278192c0fa24a307cb9d7f3c37bac1fbc702778a.png)

#####[Example 2](./Front matter.md)

Consider the plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) defined by the geometric equation ![(1,1,1) \cdot[ (x,y,z) - (0,0,0) ] = 0](../Images/831d0fb6bd5dae0e3cb3e02a0edeaa790a4e388a.png). Find the projection of the vector ![\vec{u}=(4,5,6)](./images/e49d91d577d668b75e188c1d4d9cf6d3a90a991a.png) onto ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and onto ![P^\perp](./images/b84ae344bc6b0a02b8daaf254a721e2ad9f820a6.png). Verify that ![\Pi_P(\vec{u}) + \Pi_{P^\perp}(\vec{u}) = \vec{u}](./images/e431592894d1da451c40c750d38477b2b64a9932.png).

Using the formula ![\Pi_P(\vec{u}) = \vec{u} - \frac{ \vec{u} \cdot \vec{n} }{ \| \vec{n} \|^2 } \vec{n}](./images/2979fc31a21784b690d3fae60026f004b67ea312.png), we find ![\Pi_P(\vec{u})= (-1,0,1)](./images/3d08efbf43cc7eec3281162eb0729dd2fa202aa1.png). We also find ![\Pi_{P^\perp}(\vec{u}) = \frac{ \vec{u} \cdot \vec{n} }{ \| \vec{n} \|^2 } \vec{n}
= (5,5,5)](./images/63b5578f69a3fed1408d80b71af2f6e48d889e72.png), which is a vector in the same direction as ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png). Observe that the vector ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) can be reconstructed by adding the two projections: ![\Pi_P(\vec{u}) + \Pi_{P^\perp}(\vec{u}) = (-1,0,1) + (5,5,5) = (4,5,6) = \vec{u}](./images/ab59d245e8fbf30067191d0ec4dbd056a2800a18.png).

###[Distances formulas revisited](./Front matter.md)

Suppose you want to find the distance between the line ![\ell: \{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)=p_{\textrm{o}}+t\:\vec{v}, t \in \mathbb{R} \}](./images/61e128eae814f124d1286c693243dbc80223834e.png) and the origin ![O=(0,0,0)](./images/0d113a5deff61789e9e07e9fc440c73e53774270.png). This problem is equivalent to finding the distance between the line ![\ell^\prime: \{ (x,y,z) \in \mathbb{R}^3 \; | \; (x,y,z)=\vec{0}+t\:\vec{v}, t \in \mathbb{R} \}](./images/df944eaa6d6e5aadc3420418ab0f2efc2589c991.png) and the point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png), the answer to which is the length of the projection ![\Pi_{\ell^\perp}(p_{\textrm{o}})](./images/8d74776d1499599a5c6659a49ca8bc740a4620f6.png):

![d(\ell^\prime,p_{\textrm{o}}) 
= \left\| \Pi_{\ell^\perp}(p_{\textrm{o}}) \right\|
= \left\| p_{\textrm{o}} - \frac{  p_{\textrm{o}} \cdot \vec{v}  }{ \| \vec{v} \|^2 } \vec{v} \right\|.](./images/7aa9bb1c6c4c4820ee3ae6a8fb2508529bb94115.png)

The distance between a plane ![P: \; \vec{n} \cdot[ (x,y,z) - p_{\textrm{o}} ] = 0](../Images/3b42b973a9a9df3c0649f9575efbf864bc145a14.png) and the origin ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is the same as the distance between the plane ![P^\prime: \vec{n} \cdot (x,y,z) = 0](./images/516724b0a614c716261f719d7a0247f8b3e2e222.png) and the point ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png). We can obtain this distance by finding the length of the projection of ![p_{\textrm{o}}](./images/2bb497563adb0da3ba9ddc3885534bfc3eac40ea.png) onto ![P^{\prime\perp}](./images/25a569f20860883cea75c18202b188a42d505a6e.png) using the formula

![d(P^\prime,p_{\textrm{o}})= \frac{| \vec{n}\cdot p_{\textrm{o}} |}{ \| \vec{n} \| }.](./images/9e2115293f3530c8d5ded949a05efbe379e366eb.png)

On your own, try drawing the pictures for the above two scenarios. Make sure the formulas make sense to you.

###[Projections matrices](./Front matter.md)

Since projections are _linear transformations_, they can be expressed as matrix-vector products:

![\vec{v} = \Pi(\vec{u}) \qquad \Leftrightarrow \qquad  \vec{v} = M_{\Pi}\vec{u}.](./images/21f59fde925771fe27629afc73745e89463da421.png)

Multiplying the vector ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) by the matrix ![M_{\Pi}](./images/2123e7425d926fdec4bc9be5d5268694fe27d5a8.png) is the same as applying the projection ![\Pi](./images/a14d4f6918d49df98b5c0288d26a866e1907eef8.png).

We’ll learn more about projection matrices later. For now, I’ll show you a simple example of a projection matrix in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png). Let ![\Pi](./images/a14d4f6918d49df98b5c0288d26a866e1907eef8.png) be the projection onto the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane. This projection operation corresponds to the following matrix-vector product:

![\Pi(\vec{u}) = 
M_{\Pi}\vec{u} = 
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 0 
\end{bmatrix}
\!\!
\begin{bmatrix}
u_x \\ u_y \\ u_z
\end{bmatrix}
=
\begin{bmatrix}
u_x \\ u_y \\ 0
\end{bmatrix}\!\!.](./images/e89d3ec8366078cebeeb8d1ed9f8e470084e115c.png)

Note how multiplying a vector by ![M_{\Pi}](./images/2123e7425d926fdec4bc9be5d5268694fe27d5a8.png) results in selecting only the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-components of the vector while killing the ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-component, which is precisely what the projection onto the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane is supposed to do.

###[Discussion](./Front matter.md)

In the next section we’ll talk about a particular set of projections known as _coordinate projections_. We use coordinate projections to find the components of vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) with respect to a coordinate system:

![\begin{align*}
v_x\hat{\imath} 
&=  	\Pi_x(\vec{v}) 
= \frac{\vec{v} \cdot \hat{\imath}}{\|\hat{\imath}\|^2}\hat{\imath} 
= (\vec{v} \cdot \hat{\imath})\hat{\imath},  \\
v_y\hat{\jmath} 
&= \Pi_y(\vec{v}) 
= \frac{\vec{v} \cdot \hat{\jmath}}{\|\hat{\jmath}\|^2}\hat{\jmath} 
= (\vec{v} \cdot \hat{\jmath})\hat{\jmath},  \\
v_z\hat{k}
&= \Pi_z(\vec{v})
= \frac{\vec{v} \cdot \hat{k}}{\|\hat{k}\|^2}\hat{k} 			
= (\vec{v} \cdot \hat{k})\hat{k}.
\end{align*}](./images/99f58367439ea126d8181f088cc6b972b789d1ee.png)

The coordinate projection ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) projects onto the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis. Similarly, ![\Pi_y](./images/505d12683593ec170ac826c0a36f82e7f01bf7d8.png) and ![\Pi_z](./images/b1ede810caab387e3a432f0cd37d397c820e83d4.png) project onto the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\- and ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-axes.

###[Exercises](./Front matter.md)

E4.6 Consider the points ![r_1=(1,3,0)](./images/2c411d5ece65c4b62916eb7899bf63f8a137d020.png), ![r_2=(3,1,0)](./images/26aa5f699f5d186d9edb9ce88d7a721314037417.png), the vector ![\vec{u}=(0,0,5)](./images/678e718129c2f33f16ee5f384f5330b1c95d1a81.png), and the plane ![P: x+y+z=0](./images/b6a05e44ff50ab9d28e71bd4c8835d7d1bcadc9b.png) that passes through the origin and has normal vector ![\vec{n} = (1,1,1)](./images/3c645024f5ecaff25418e50509f832047a86298d.png). Compute the projections.

1.  ![\Pi_{\vec{n}}(r_1)](./images/17023c34299f8862231ead89d011fd3e28dcef99.png)
2.  ![\Pi_{P}(r_1)](./images/52be789e10a051d10c8fec8afa7ededa11550cfb.png)
3.  ![\Pi_{P}(r_2)](./images/d9d07e10b8e8da3de6c52d7a669b5ecb930d4541.png)
4.  ![\Pi_{\vec{n}}(\vec{u})](./images/0ece056556882f6d7c65f3cdaa519a4862fd0700.png)
5.  ![\Pi_{P}(\vec{u})](./images/13bada21159766be2649b130208f7d2c5c11308d.png)

Your answer should be a vector in each case.

E4.7 Consider the points ![p=(10,10,10)](./images/14b06c3bfc2bda8557fe0198a41098046f269bd7.png) and the two parallel lines ![\ell_1:\{ (3,0,5) + t(1,-2,0), t\!\in~\!\!\mathbb{R} \}](./images/3fc12cabebf1e5933f64e038e438b078ae323ec6.png) and ![\ell_2:\{ (6,0,0) + t(1,-2,0), t\!\in~\!\!\mathbb{R} \}](./images/dab8f564ce62fac4854fcd5a59b5c9d103945338.png). Compute the following quantities.

1.  ![\Pi_{\ell_1}(p)](./images/3a2e69aad6cc5bb3c41db1511ff0e30f769ffa30.png)
2.  ![d(p, \ell_1)](./images/d8d62f159b3ba5e57f07a817c0b0e54505057bbc.png)
3.  ![\Pi_{\ell_2}(p)](./images/65a7c91cbfbe97fe08c7522a62899b4de4176477.png)
4.  ![d(p, \ell_2)](./images/c7ba8614e8c457b7876cc2c62345d1734568ab62.png)
5.  ![d(\ell_1, \ell_2)](./images/d188660074a5fa87e169bbd32ae4e4ccde5292c3.png)

Is ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) closer to ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) or to ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png)?

E4.8 Find the orthogonal projection of the vector ![\vec{v}=(4,5,6)](./images/a9b0e66848a3564fc3169616b863fed70a36612d.png) onto the plane that passes through the origin and contains the vectors ![(2,-4,2)](./images/a8deda5f9aad456e48839f75722527294f4f616d.png) and ![(6,1,-4)](./images/cb421d36cb345a5fb4be61ce895d7ffe3d18f353.png).

##[4.3 Coordinate projections](./Chapter 4_ Geometric aspects of linear algebra.md)

In science, it’s common to express vectors as components: ![(v_x,v_y,v_z)](./images/89f872c82996b86c9b7ed306d9d98fea762b6865.png). Thinking of vectors as lists of components is fine for computational purposes, since vector operations require manipulating the components of vectors. However, focussing on a vector’s components overlooks an important concept—the _basis_ with respect to which the vector’s components are expressed.

It’s not uncommon for students to have misconceptions about linear algebra due to an incomplete understanding of the fundamental distinction between vectors and their components. Since I want you to have a _thorough_ understanding of linear algebra, we’ll review—in full detail—the notion of a basis and how to compute vector components with respect to different bases.

Before we begin, let’s quickly review what we know about vectors and vector components from previous sections of the book. In[Section 1.13](./Chapter 1_ Math fundamentals.md), we described vectors in terms of their ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-components. Given a standard ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-coordinate system, we can decompose a vector ![\vec{F}](./images/8c04d2fa93145d81b055be1dc21fc755d690670a.png) in terms of its components:

![F_x = \| \vec{F} \| \cos\theta,	\qquad 
F_y = \| \vec{F} \| \sin\theta,](./images/bfeccb63ced4d8a1854855665f4454e2415c7eaf.png)

where ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is the angle the vector ![\vec{F}](./images/8c04d2fa93145d81b055be1dc21fc755d690670a.png) makes with the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis. We can express the vector as _coordinates_ with respect to the basis ![\{ \hat{\imath}, \hat{\jmath} \}](./images/81e59913690964dec5056d8ba5bc8eac170f8c1f.png) as ![\vec{F} = F_x\hat{\imath} + F_y \hat{\jmath} = (F_x,F_y)_{\hat{\imath}\hat{\jmath}}](./images/f799c368bf52618c25771176d530f0bcbe5da1bc.png). The number ![F_x](./images/2476fc8c6b72c33ec61450e698b7c2b6adf9ee13.png) corresponds to the length of the _projection_ of the vector ![\vec{F}](./images/8c04d2fa93145d81b055be1dc21fc755d690670a.png) onto the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis.

In the last section, we discussed the projection operation and learned how to compute projections using the dot product or as a matrix-vector product:

![F_x\,\hat{\imath} 
\; = \; \frac{\vec{F} \cdot \hat{\imath}}{\|\hat{\imath}\|^2}\hat{\imath}
\; = \; \Pi_x(\vec{F}) 
\; = \; \underbrace{\!\begin{bmatrix}1 & 0 \\ 0 & 0 \end{bmatrix}\!}_{M_{\Pi_x}}
\;
\underbrace{\!\begin{bmatrix}F_x \\ F_y\end{bmatrix}}_{\vec{F}\!},](./images/7fca665876645dd2997f08bc8a1f1659e0b6cb10.png)

where ![\Pi_x:\mathbb{R}^2 \to \mathbb{R}^2](./images/b1c0f8f659670f893ffbd4b9212d596593ab6379.png) is the projection onto the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis (a linear transformation) and ![M_{\Pi_x}](./images/b52ab9ff4c3f64fd300661883097976ceaf7fe21.png) is the matrix representation of ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) with respect to the basis ![\{ \hat{\imath}, \hat{\jmath} \}](./images/81e59913690964dec5056d8ba5bc8eac170f8c1f.png).

In this section, we’ll extend what we know about basic vectors coordinates with respect to the basis ![\{ \hat{\imath}, \hat{\jmath} \}](./images/81e59913690964dec5056d8ba5bc8eac170f8c1f.png), and formally define vector coordinates with respect to any basis.

###[Concepts](./Front matter.md)

We can define three different types of bases for an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png):

-   A generic basis ![B_f=\{ \vec{f}_1, \vec{f}_2, \ldots, \vec{f}_n \}](./images/6ae078a11fc2d7dd8caa9a3a54bc48366cf38496.png) consists of any set of linearly independent vectors in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png).
-   An orthogonal basis ![B_{e}=\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/fe874cfac89808de8fe088ec62189e5115fb7031.png) consists of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) mutually orthogonal vectors in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) obeying ![\vec{e}_i \cdot \vec{e}_j = 0](./images/3023b3baa9491c19185f7885aa16aa93b8f8c221.png), ![\forall i\neq j](./images/c7d08c2631463599e72b1b0c0b69c549d69487a6.png).
-   An orthonormal basis ![B_{\hat{e}}=\{ \hat{e}_1, \hat{e}_2, \ldots, \hat{e}_n \}](./images/edd77475ee1480008d89a4b95667e94a4c02713a.png) is an orthogonal basis of unit vectors: ![\hat{e}_i \cdot \hat{e}_j = 0](./images/c21e5902a2fa81639475dd97e5ca3fe04725bb3e.png) and ![\| \hat{e}_i \| =1, \; \forall i \in \{ 1,2,\ldots,n\}](./images/1e986feda190ec3f89b6ee6ae2f2030268b3fcd4.png).

A vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is expressed as coordinates ![v_i](./images/abb23a5428dd91d81a0e764b6e1f2924c3cfae81.png) with respect to any basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![\vec{v} 	= v_1 \vec{e}_1 +  v_2\vec{e}_2 +  \cdots + v_n\vec{e}_n
= (v_1, v_2, \ldots, v_n)_{B}.](./images/198bec6ffeeea348a30fb42df52ecfc81762a528.png)

We can use two different bases, ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png), to express the same vector:

-   ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png): a vector
-   ![[\vec{v}]_{B}=(v_1, v_2, \ldots, v_n)_{B}](../Images/ae5fa7027263f23d2c0d77a80caa4f551e0f168e.png): the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) expressed in the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)
-   ![[\vec{v}]_{B^\prime}=(v^\prime_1, v^\prime_2, \ldots, v^\prime_n)_{B^\prime}](../Images/c933d43adc9042c63f65c64b1bf50b24808d6d3b.png): the same vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) expressed in a different basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png)
-   ![\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/029b9a61176cd5f29400e699e84a44a9f08e60cd.png): the change-of-basis matrix that converts from ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) coordinates to ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) coordinates: ![[\vec{v}]_{B^\prime} = \tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}\,[\vec{v}]_{B}](../Images/f1c32ab9c513e7c6ac32d1ad4a9b2d10b40416a0.png)

###[Components with respect to a basis](./Front matter.md)

A vector’s _components_ describe how much of the vector lies in a given direction. For example, a vector ![\vec{v} \in \mathbb{R}^3](./images/7d4d76835dd377bbd6d7248bd9e3aa55aa35fdfa.png) expressed as components _with respect to_ the standard orthonormal basis ![\{ \hat{\imath}, \hat{\jmath}, \hat{k} \}](./images/20a783ec4e2fb4e61cdda060b7be04e1c1bd2022.png) is denoted ![\vec{v}=(v_x,v_y,v_z)_{\hat{\imath}\hat{\jmath}\hat{k}}](./images/c43c5f88f3d1b630cb0d9065c82eb7c1d3e33187.png). The _components_ of a vector are also called _coordinates_ (in the context of a coordinate system) and _coefficients_ (in the context of a linear combination). Don’t be confused by this multitude of terms because it’s all the same idea: components, coordinates, and coefficients are all ways to describe vectors with respect to bases.

When the basis consists of a set of orthonormal vectors like the vectors ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png), ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png), and ![\hat{k}](./images/1427cff1bf4c402fb2a07d3b871082761b7c2102.png), we can compute vector components using the dot product:

![v_x = \vec{v}\cdot \hat{\imath},
\qquad
v_y = \vec{v}\cdot \hat{\jmath},
\qquad
v_z = \vec{v} \cdot \hat{k}.](./images/f7fcb41874d3add1014d0f21337c9c3e6f90992a.png)

In this section, we’ll discuss how to find coordinates with respect to three different types of bases: orthonormal bases, orthogonal bases, and generic bases. First, let’s precisely define what a _basis_ is.

###[Definition of a basis](./Front matter.md)

A basis ![B=\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/8633486a939e2d0b809894ed2c088015e70ef124.png) for the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) has the following two properties:

-   **Spanning property**: Any vector ![\vec{v} \in V](./images/3eefde8f9c5d92cf2322bd0bd81265b055ce130a.png) can be expressed as a linear combination of the basis vectors:
    
    ![\vec{v} = v_1\vec{e}_1 + v_2\vec{e}_2 + \cdots +  v_n\vec{e}_n.](./images/d0d4abf4f2d099251da98cf53ceb76ddd4d9e507.png)
    
    This property guarantees that the vectors in the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) are _sufficient_ to represent any vector in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png).
    
-   **Linear independence property**: The vectors that form the basis ![B = \{ \vec{e}_1,\vec{e}_2, \ldots, \vec{e}_n \}](./images/8633486a939e2d0b809894ed2c088015e70ef124.png) are linearly independent. The linear independence of the vectors in the basis guarantees that none of the vectors ![\vec{e}_i](./images/8e3efa1e871aeea4f937dc13aa99a36dbde1386c.png) are redundant.

If a set of vectors ![B=\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/8633486a939e2d0b809894ed2c088015e70ef124.png) satisfies both properties, we say ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is a basis for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). In other words, ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) can serve as a coordinate system for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png).

###[Coordinates with respect to an orthonormal basis](./Front matter.md)

An orthonormal basis ![B_{\hat{e}}=\{ \hat{e}_1, \hat{e}_2, \ldots, \hat{e}_n \}](./images/edd77475ee1480008d89a4b95667e94a4c02713a.png) consists of a set of mutually orthogonal, unit vectors:

![\hat{e}_i \cdot \hat{e}_j = 
\left\{ \begin{array}{ll} 1 & \textrm{if } i=j, \\  0 & \textrm{if } i \neq j. \end{array} \right.](./images/8487bea8eb84b340a3f4df027d06f4d71a11a30c.png)

The vectors are mutually orthogonal since ![\hat{e}_i \cdot \hat{e}_j = 0](./images/c21e5902a2fa81639475dd97e5ca3fe04725bb3e.png) for all ![i\neq j](./images/fe4bf09b19814755a6c9a589b2e1aad7707242e8.png), and the vectors have length one since ![\hat{e}_i \cdot \hat{e}_i = 1](./images/dfc722381b192fc037d52382da1edf82ff59d610.png) implies ![\| \hat{e}_i \| =1](./images/58e34ac921685f483631e4758426b57071b50001.png).

To compute the coordinates of the vector ![\vec{a}](./images/f0090c6a4c3d631f857e7e214dac1503513e48fc.png) with respect to an orthonormal basis ![B_{\hat{e}}](./images/1bde90ebddd0a0b9701dd85f9436e2158bf4adbb.png), we use the standard “prescription” similar to the one we used for the ![\{ \hat{\imath}, \hat{\jmath}, \hat{k} \}](./images/20a783ec4e2fb4e61cdda060b7be04e1c1bd2022.png) basis:

![(a_1,a_2,\ldots,a_n)_{B_{\hat{e}}}  \; \Leftrightarrow \; 
\underbrace{(\vec{a}\cdot \hat{e}_1)}_{a_1}\hat{e}_1 
\;  +  \; 
\underbrace{(\vec{a}\cdot \hat{e}_2)}_{a_2} \hat{e}_2 
\; + \; 
\cdots
\; + \; 
\underbrace{(\vec{a}\cdot \hat{e}_n)}_{a_n} \hat{e}_n.](./images/e1246e20c9ae52cc8a7a432c65e895e104ccb0ac.png)

###[Coordinates with respect to an orthogonal basis](./Front matter.md)

Consider a basis ![B_{e}=\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/fe874cfac89808de8fe088ec62189e5115fb7031.png) that is orthogonal, but not orthonormal. We can compute the coordinates of any vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png) with respect to the basis ![\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png) as follows:

![(b_1,b_2,\ldots,b_n)_{B_{e}}
\; \Leftrightarrow \; 
\left(\frac{\vec{b}\cdot\vec{e}_1}{\|\vec{e}_1\|^2}\right)\!\vec{e}_1
\; + \;   
\left(\frac{\vec{b}\cdot\vec{e}_2}{\|\vec{e}_2\|^2}\right)\!\vec{e}_2
\; + \;   
\cdots
\; + \; 
\left(\frac{\vec{b}\cdot\vec{e}_n}{\|\vec{e}_n\|^2}\right)\!\vec{e}_n.](./images/a909d77066ccb27d7b3d59a12e81d3240624f475.png)

To find the coordinates of the vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png) with respect to ![B_{e}](./images/514480ae54829b671c00296490abdbde7df625a7.png), we use the general projection formula,

![b_1 = \frac{  \vec{b} \cdot \vec{e}_1 }{ \|\vec{e}_1\|^2 },
\quad
b_2  = \frac{   \vec{b} \cdot \vec{e}_2 }{ \|\vec{e}_2\|^2 },
\quad
\cdots \:,
\quad
b_n  = \frac{  \vec{b}  \cdot \vec{e}_n }{ \|\vec{e}_n\|^2 }.](./images/7ea37aa63146a84bf9a87e57501ed25c31dba069.png)

Observe that each component of the vector can be computed independently of the other components: to compute ![b_1](./images/b910026bd71716fbed564967ba81e56942b1b6ad.png), all we need to know is ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png) and ![\vec{e}_1](./images/bfb7cfed44bb7969a0f9b8df5e08e10a9a7a6c54.png); we don’t need to know ![\vec{e}_2](./images/dd508590ce90d8ecb415afab0c7d2f49f6eaea62.png), ![\vec{e}_3](./images/623991b4ef748c04915bb0e8ddf404b5d62bcaad.png), ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png), ![\vec{e}_n](./images/39dc24b5930902266d26141c076d93d41e03a55b.png), because we know the other basis vectors are orthogonal to ![\vec{e}_1](./images/bfb7cfed44bb7969a0f9b8df5e08e10a9a7a6c54.png). The computation of the coordinates correspond to ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) independent _orthogonal projections_. The coordinate ![b_i](./images/13294bd22e12bd7ece755875322827e8e82562b2.png) tells us how much of the basis vector ![\vec{e}_i](./images/8e3efa1e871aeea4f937dc13aa99a36dbde1386c.png) we need in the linear combination to construct the vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png).

###[Coordinates with respect to a generic basis](./Front matter.md)

Suppose we’re given a generic basis ![\{ \vec{f}_1, \vec{f}_2, \ldots, \vec{f}_n \}](./images/f3e1f20fdf33b662b4fd01edcb06d1e26a51789b.png) for a vector space. To find the coordinates ![(c_1,c_2,\ldots,c_n)](./images/5660785fb807ca497c29e140065edce1c3c0481f.png) of a vector ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) with respect to this basis, we need to solve the equation

![c_1\vec{f}_1+ c_2\vec{f}_2 + \cdots + c_n\vec{f}_n  = \vec{c}](./images/bfc060d062a6c58e5507f861e257575640f1dbea.png)

for the unknowns ![c_1,c_2,\ldots,c_n](./images/ee2d713d39c7a00541a0b1fad17446bfd010f302.png). Because the vectors ![\{ \vec{f}_i \}](./images/c8f10f5e7498fdb0a0168468c2ba8929d24d6fe9.png) are not orthogonal, the calculation of the coefficients ![c_1,c_2,\ldots,c_n](./images/ee2d713d39c7a00541a0b1fad17446bfd010f302.png) must be done simultaneously.

#####[Example](./Front matter.md)

Express the vector ![\vec{v}=(5,6)_{\hat{\imath}\hat{\jmath}}](./images/0c4f40f6fa1c6a6f7b4b51fca6f42bdbeac4ddcd.png) in terms of the basis ![B_f = \{ \vec{f}_1, \vec{f}_2 \}](./images/4d26e72f311236cf53e9d86b00a313166fd13c70.png) where ![\vec{f}_1 = (1,1)_{\hat{\imath}\hat{\jmath}}](./images/4e2ef58b34aa30328d50269ab1f43191d35d0247.png) and ![\vec{f}_2 = (3,0)_{\hat{\imath}\hat{\jmath}}](./images/4d84850f9025711fd33604209656d8dad099ddfb.png).

We are looking for the coefficients ![v_1](./images/26bb4de90d49b42600706cf2e962fbcf50141c0c.png) and ![v_2](./images/b8ca706d019569604aca5b0c8b702542f0fd8e6b.png) such that

![(v_1,v_2)_{\!B_f}
= v_1 \vec{f}_1 + v_2\vec{f}_2
= \vec{v} = (5,6)_{\hat{\imath}\hat{\jmath}}.](./images/df1045e5b2cbe60ceeb6c7e67c1861cbdeb4e0fd.png)

To find the coefficients we need to solve the following system of equations _simultaneously_:

![\begin{align*}
1v_1 + 3v_2  	& = 5 \\
1v_1 + 0 \;   	& = 6. 
\end{align*}](./images/fc2cddc1fd8920dc0c2787d09716e5ea782030c8.png)

From the second equation we find ![v_1=6](./images/4fb9d4bec0924942e16bd9f888a9168f9bb8392e.png). We substitute this answer into the first equation and find ![v_2 = \frac{-1}{3}](./images/10924b0572b4244b860f04006e434e4d41bdec9e.png). Thus, the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) written with respect to the basis ![\{ \vec{f}_1, \vec{f}_2 \}](./images/6e589f9a5109dea43a32d95883031d63bfc5f3e8.png) is ![\vec{v} = 6\vec{f}_1 - \frac{1}{3}\vec{f}_2 = \left(6,\tfrac{-1}{3}\right)_{\!B_f}](./images/0a9d2bef380d80f730aa0c544eb3a29933fb3a76.png).

The general case of computing a vector’s coordinates with respect to a generic basis ![\{ \vec{f}_1, \vec{f}_2, \ldots, \vec{f}_n \}](./images/f3e1f20fdf33b662b4fd01edcb06d1e26a51789b.png) requires solving a system of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) equations in ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) unknowns. You know how to do this, but it will take some work. The take-away message is that computing vector coordinates with respect to generic bases is more difficult than computing vector coordinates with respect to orthogonal and orthonormal bases.

###[Change of basis](./Front matter.md)

We often identify a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) with its components ![(v_x,v_y,v_z)](./images/89f872c82996b86c9b7ed306d9d98fea762b6865.png). It’s important to always keep in mind the basis with respect to which the components are taken, and if necessary specify the basis as a subscript ![\vec{v}=(v_x,v_y,v_z)_{\hat{\imath}\hat{\jmath}\hat{k}}](./images/c43c5f88f3d1b630cb0d9065c82eb7c1d3e33187.png). When performing vector arithmetic operations like ![\vec{u}+\vec{v}](./images/3c2311f5d52e6932259fd54b71fc2017a077c2ba.png), we don’t really care what basis the vectors are expressed in so long as the _same_ basis is used for both ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png).

We sometimes need to use multiple bases, however. Consider the basis ![B=\{ \hat{e}_1, \hat{e}_2, \hat{e}_3 \}](./images/085e29361ca11de1ae1bb3f1912df98da41a610e.png) and another basis ![B^\prime=\{ \hat{e}^\prime_1, \hat{e}^\prime_2, \hat{e}^\prime_3 \}](./images/5fb8f867d1fb32eb70d533f6e96ec771e3b416ea.png). Suppose we’re given the coordinates ![v_1,v_2,v_3](./images/e6a02336aca0f4efb9d34a60456fd4c3ae314436.png) of some vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in terms of the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![\vec{v}
= \left( v_1 , v_2 , v_3  \right)_{ B }
= v_1  \hat{e}_1  + v_2  \hat{e}_2  + v_3  \hat{e}_3.](./images/9f20204e8ee3043a43bdd05bc8994687eb0b6213.png)

How can we find the coordinates of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in terms of the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png)?

This is called a _change-of-basis_ transformation, and it’s performed as a matrix multiplication with a _change-of-basis matrix_:

![\left[
\begin{array}{c}
v_1^\prime  \\
v_2^\prime  \\
v_3^\prime  
\end{array}
\right]_{\!B^\prime }
=
\underbrace{\!\!
\left[
\begin{array}{ccc}
\hat{e}^\prime_1 \cdot \hat{e}_1		& \hat{e}^\prime_1 \cdot \hat{e}_2	& \hat{e}^\prime_1 \cdot \hat{e}_3 \\
\hat{e}^\prime_2 \cdot \hat{e}_1		& \hat{e}^\prime_2 \cdot \hat{e}_2	& \hat{e}^\prime_2 \cdot \hat{e}_3 \\
\hat{e}^\prime_3 \cdot \hat{e}_1		& \hat{e}^\prime_3 \cdot \hat{e}_2	& \hat{e}^\prime_3 \cdot \hat{e}_3 
\end{array}
\right]\!\!
}_{  \tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}  } 
\!
\begin{bmatrix}
v_1  \\
v_2  \\
v_3  
\end{bmatrix}_{\!B }.](../Images/610f47a287e0100b0075f5ea9706de561963a937.png)

The columns of the change-of-basis matrix describe the vectors of the basis ![\{\hat{e}_i\}](./images/eef194e84589e60d53ce9919410e93eb3417c776.png) in terms of the basis ![\{ \hat{e}^\prime_i\}](./images/0cd057939a14c4b343ccff94fe4e62513641d166.png).

Note that multiplying a vector by the matrix ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/b3068d47a22daef194cb14735750ffa22f484a70.png) doesn’t actually _do_ anything since it doesn’t change the vector. The change-of-basis operation acts like the identity transformation, which is why we use the notation ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/b3068d47a22daef194cb14735750ffa22f484a70.png) to describe it. The vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) stays the same—it is simply expressed in terms of a different basis:

![\!\left( v_1^\prime , v_2^\prime , v_3^\prime  \right)_{\!B^\prime}\!\!
= v_1^\prime \hat{e}^\prime_1  + v_2^\prime \hat{e}^\prime_2  + v_3^\prime \hat{e}^\prime_3 
= \vec{v}
= v_1  \hat{e}_1  + v_2  \hat{e}_2  + v_3 \hat{e}_3
= \!\left( v_1 , v_2 , v_3  \!\right)_{\!B}\!.](./images/41705b9a7b271f53fe58a6384fd1dce0b7a9e885.png)

We say the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) has two _representations_. The vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) corresponds to the coordinates triple ![(v_1 , v_2 , v_3)](./images/d6f9bedeb9a54107047374f785c25741614d6b4c.png) with respect to the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), and to the triple ![(v_1^\prime , v_2^\prime , v_3^\prime)](./images/e0fecca58cfec5b0e84c10ce00a94c46dfc45096.png) with respect to the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png).

The matrix ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/b3068d47a22daef194cb14735750ffa22f484a70.png) contains the information about how each vector of the old basis (![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)) is expressed in terms of the new basis (![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png)). For example, the first column of the change-of-basis matrix describes how the vector ![\hat{e}_1](./images/6918c3bc61ee2edc463842c5b586359c71047541.png) is expressed in terms of the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png):

![\hat{e}_1 
= 
(\hat{e}^\prime_1 \cdot \hat{e}_1)\:\hat{e}^\prime_1 
+ 
(\hat{e}^\prime_2 \cdot \hat{e}_1)\:\hat{e}^\prime_2 
+ 
(\hat{e}^\prime_3 \cdot \hat{e}_1)\:\hat{e}^\prime_3
=
\left(\hat{e}^\prime_1 \cdot \hat{e}_1, \, \hat{e}^\prime_2 \cdot \hat{e}_1, \,  \hat{e}^\prime_3 \cdot \hat{e}_1\right)_{B^\prime}\,.](./images/32cc4e10312278358d1a4078dc4dd1adb3840b52.png)

Note this is the generic formula for expressing vectors in the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png).

To find the entries of the change-of-basis matrix ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/b3068d47a22daef194cb14735750ffa22f484a70.png) between orthonormal bases ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png), it’s sufficient to compute all the dot products ![\hat{e}^\prime_i \cdot \hat{e}_j](./images/e48ae2cbe7a5f67fba1151defe9b56e1204a83ee.png). To compute the entries of a change-of-basis matrix between bases ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) (which are orthogonal but not necessarily orthonormal), we use ![\left(\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}\right)_{ij}
=\frac{ \vec{e}^\prime_i \cdot \vec{e}_j }{ \| \vec{e}^\prime_i \| \, \|\vec{e}_j\|}](../Images/dd44d79ee20bd0512605128dfba17e45f7b009b3.png). Computing the change-of-basis matrix between nonorthogonal bases is more complicated.

###[Change of basis to the standard basis](./Front matter.md)

We’ll now discuss an important special case of the change-of-basis operation, where we change from a generic basis ![B_f = \{ \vec{f}_1, \vec{f}_2, \vec{f}_3 \}](./images/ea524ef979f81b786e02a5b7c774737b50d9d713.png) to the standard basis ![B_s = \{(1,0,0), (0,1,0), (0,0,1) \}](./images/76b4c84e43a197f86e6b76a1fb0bf4055adb372a.png). In three dimensions, the vectors of the standard basis are denoted ![\hat{\imath} \eqdef (1,0,0)](./images/4fb9f306181754b408b8ca1a0db552ee074a2444.png), ![\hat{\jmath} \eqdef (0,1,0)](./images/e17bfe67a9415d2d016f8fdb971cdf75c5867554.png), and ![\hat{k} \eqdef (0,0,1)](./images/419718bd112f22444cd0e7ee134fb6660e117157.png). Assume the vectors of the generic basis are given to us as coordinate vectors with respect to the standard basis ![\vec{f}_1 = (f_{1x},f_{1y},f_{1z})_{B_s}](./images/43da3ff50e2998d6b7f7fe0554479d52f530e11b.png), ![\vec{f}_2 = (f_{2x},f_{2y},f_{2z})_{B_s}](./images/f77f0d42127547fd9c8217acabab962d9c47e385.png), and ![\vec{f}_3 = (f_{3x},f_{3y},f_{3z})_{B_s}](./images/bdbc6bb733b3d4508580e7d0d8cca46f4595d4dd.png). The change-of-basis matrix needed to convert vectors from the generic basis ![B_f](./images/2b68aa77f3885b0b7cf37397fa2f6116b8241f7b.png) to the standard basis ![B_s](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png) is

![\!\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_{\!f}}}
=
\left[\begin{array}{ccc}
\hat{\imath} \cdot \vec{f}_1   & \hat{\imath} \cdot \vec{f}_2     & \hat{\imath} \cdot \vec{f}_3 \\
\hat{\jmath} \cdot \vec{f}_1   & \hat{\jmath} \cdot \vec{f}_2     & \hat{\jmath} \cdot \vec{f}_3 \\
\hat{k} \cdot \vec{f}_1   & \hat{k} \cdot \vec{f}_2 & \hat{k} \cdot \vec{f}_3 
\end{array}\right]
=
\begin{bmatrix}
f_{1x}	&	f_{2x}	&	f_{3x}	\\
f_{1y}	&	f_{2y}	&	f_{3y}	\\
f_{1z}	&	f_{2z}	&	f_{3z}
\end{bmatrix}\!.](../Images/61ba57c0ee606923ef2ec37d0a46bd6962b3bc13.png)

Observe the matrix ![\!\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_{\!f}}}](../Images/9cfbb8a0ef04b98727cd55a015b525ce95ff958e.png) contains the components of the vectors ![\vec{f}_1](./images/bd1df8ef44b6cf6c9141f55d09b6b3c79851bd34.png), ![\vec{f}_2](./images/cb792e5d1aadfbd6cb66d7f693b32db23c021f1d.png), and ![\vec{f}_3](./images/980ffd4b9f35bb6d5fcf175b2f91b34426ace3ef.png) as its columns. This makes sense, since we’re computing dot products with the vectors ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png), ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png), and ![\hat{k}](./images/1427cff1bf4c402fb2a07d3b871082761b7c2102.png).

To obtain the change-of-basis matrix for the opposite direction—from ![B_s](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png) to ![B_f](./images/2b68aa77f3885b0b7cf37397fa2f6116b8241f7b.png)—compute the inverse of the change-of-basis matrix:

![\tensor[_{B_{\!f}}]{\left[\mathbbm{1}\right]}{_{B_s}}
=
\left( \!\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_{\!f}}}	\right)^{\!-1}\!.](../Images/3f5fc37ad9e26f7b222843beb116be7b56bcbecc.png)

We can find the inverse using one of the computational techniques we learned in[Chapter 3](./Chapter 3_ Computational linear algebra.md).

#####[Example](./Front matter.md)

Consider the basis ![B_f = \{ \vec{f}_1, \vec{f}_2 \}](./images/4d26e72f311236cf53e9d86b00a313166fd13c70.png), where ![\vec{f}_1=(1,2)^\sfT_{B_s}](./images/ea56cbbd61253d81285148b22b2c227caf869f15.png) and ![\vec{f}_2=(1,1)^\sfT_{B_s}](./images/e00d8295c0764d7642fcf02e151d42ce98d356d3.png). Find the coordinates of the vector ![\vec{v} = (5,6)_{B_f}^\sfT](./images/d9639a21c96c290490912202a67735886fb3bce0.png) with respect to the standard basis. Also, find the coordinates of the vector ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png) with respect to the basis ![B_f](./images/2b68aa77f3885b0b7cf37397fa2f6116b8241f7b.png).

To answer the first part of the question, we need to find the change-of-basis matrix from ![B_f](./images/2b68aa77f3885b0b7cf37397fa2f6116b8241f7b.png) to the standard basis:

![\!\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_{\!f}}}
=
\left[\begin{array}{cc}
\hat{\imath} \cdot \vec{f}_1   & \hat{\imath} \cdot \vec{f}_2 \\
\hat{\jmath} \cdot \vec{f}_1   & \hat{\jmath} \cdot \vec{f}_2
\end{array}\right]
=
\begin{bmatrix}
\; 1 & 1 \; \\
\; 2 & 1 \; 
\end{bmatrix}\!.](../Images/27c354ee98ba178cee022012321870753af062cb.png)

We then compute ![\begin{bmatrix}1 & 1\\2 & 1\end{bmatrix}
\begin{bmatrix}5 \\ 6 \end{bmatrix}
= \begin{bmatrix}11 \\ 16\end{bmatrix}](./images/a63fd565636baaffe1864e249845ead4315f786c.png). Thus we’ve shown that ![\vec{v} = (11,16)_{B_s}](./images/659fd59d8eaef1cd8495a737a3fe05a8b97bfa0c.png).

To answer the second part of the question, we compute ![(\!\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_{\!f}}})^{-1}](../Images/3894b04c04da8e8bf09dd33a8f2664c3555bd8a2.png):

![\left[\!\!\begin{array}{cc|cc}
1 & 1		&	1  &  \!0		\\ 
2 & 1		&	0  &  \!1
\end{array}\!\!\right]\!
\sim
\!\left[\!\!\begin{array}{cc|cc}
1 & 1 	& 1 	& \! 0	\\
0 & \!-1 	& -2 	& \! 1
\end{array}\!\!\right]\!
\sim
\!\left[\!\!\begin{array}{cc|cc}
1 & 1 	& 1 & 0\\
0 & 1 	& 2 & \!\!-1
\end{array}\!\!\right]\!
\sim
\!\left[\!\!\begin{array}{cc|cc}
1 & 0 	& -1 & 1\\
0 & 1 	& 2 & \!\!-1
\end{array}\!\!\right]\!.](../Images/720b634e45bcff8e7fdeba37a317161fcb64d0e6.png)

Having obtained ![\!\tensor[_{B_{\!f}}]{\left[\mathbbm{1}\right]}{_{B_s}}
=
(\!\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_{\!f}}})^{-1} = 
\begin{bmatrix}
-1 & 1\\2 & \!-1
\end{bmatrix}](../Images/007c59965d93750bf9a31f7a1a3f07dda9519072.png), we can now compute the coordinates of ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png) in the basis ![B_f](./images/2b68aa77f3885b0b7cf37397fa2f6116b8241f7b.png) using ![\begin{bmatrix}-1 & 1\\2 & \!-1\end{bmatrix}
\begin{bmatrix}1 \\ 0 \end{bmatrix}
= \begin{bmatrix} -1 \\ 2 \end{bmatrix}](./images/85ad202ad495565e858f87d4e75ce9935554ec34.png). Thus we’ve shown that ![\hat{\imath} = (-1,2)_{B_f}](./images/85ce2dae3ab8ee655f2a3a163c8ddfd8e99ad749.png).

###[Links](./Front matter.md)

\[ Khan Academy video on the change-of-basis operation \]

[`https://youtube.com/watch?v=meibWcbGqt4`](./watch_v=meibWcbGqt4.md)

\[ Change of basis explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=P2LTAUO1TdA`](./watch_v=P2LTAUO1TdA.md)

###[Exercises](./Front matter.md)

E4.9 Find the coordinates of the vector ![\vec{v} = 2\hat{\imath} + 3\hat{\jmath} + 4\hat{k}](./images/0fb162e2aebdcee54b609db5aa72fd677b5fd0c8.png) with respect to the basis ![W = \{ \hat{w}_1 = (0,0,1), \hat{w}_2 = (0,1,0), \hat{w}_3 = (1,0,0)](./images/93f348fc79483a210034789cd7033a1dcc415c00.png).

E4.10 Find the change-of-basis matrix ![\tensor[_{B_m}]{\left[\mathbbm{1}\right]}{_{B_s}}](../Images/5d85dae919c04439ee32425615ebc808f1513ad6.png) that transforms vectors expressed in the standard basis ![B_s = \{(1,0,0), (0,1,0), (0,0,1) \}](./images/76b4c84e43a197f86e6b76a1fb0bf4055adb372a.png) to vectors in the modified basis ![B_m = \{ (1,1,0), (1,-1,0), (0,0,2) \}](./images/22b72e4cd78ebc79d1f6ccb2c39cdfb8f4e0fad4.png).

Find the change-of-basis matrix ![\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_m}}](../Images/ad4fa74f52191f97b5de69d468880e054975bfed.png) first.

E4.11 How many vectors exist in a basis for a four-dimensional vector space? Besides the number of vectors it contains, what other condition must a set of vectors satisfy to be a basis?

##[4.4 Vector spaces](./Chapter 4_ Geometric aspects of linear algebra.md)

We’re about to shift our attention from individual vectors to entire sets of vectors. We’re entering the territory of _vector spaces_. For instance, the set of all possible three-dimensional vectors is denoted ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png), and is a type of _vector space_. A vector space consists of a set of vectors and all linear combinations of these vectors. This means if the vectors ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png) are part of some vector space, then so is the vector ![\alpha\vec{v}_1  + \beta \vec{v}_2](./images/6b2b6d520587848ddacd4388b754c0750c519e3e.png) for any ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png). A _vector subspace_ consists of a subset of all possible vectors. The vector subspaces of ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) are lines and planes that pass through the origin.

Since vector spaces and subspaces play a central role in many areas of linear algebra, you’ll want to learn about the properties of vector spaces and develop your vocabulary for describing them.

By using the language of vector spaces, you’ll be able to describe certain key properties of matrices. The four _fundamental subspaces_ associated with a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are its _column space_ ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png), its _row space_ ![\mathcal{R}(A)](./images/3dbad2f997035cd04ed87a50d8ef6864087f6e44.png), its _null space_ ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png), and its _left null space_ ![\mathcal{N}(A^\sfT)](./images/c000bec6891375191f8d0e221f13c6ae42ca6c7e.png). Let’s now define these vector spaces and discuss how they help us understand the solutions to the matrix equation ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png), and the properties of the linear transformation ![T_A(\vec{x}) = A\vec{x}](./images/2f3847c88f1c8b24c3600fb2438ca44b880e5269.png).

###[Definitions](./Front matter.md)

-   ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png): a _vector space_
-   ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png): a _vector_. We use the notation ![\vec{v} \in V](./images/3eefde8f9c5d92cf2322bd0bd81265b055ce130a.png) to indicate the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is part of the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png).
-   ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png): a _vector subspace_. We use the notation ![W \subseteq V](./images/fe3c4c0997eb9a8f0f62a9774b91a1b0a2e5aaf2.png) to indicate the vector space ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) is a subspace of the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png).
-   _span_: the span of a set of vectors is the set of vectors that can be constructed as linear combinations of these vectors:
    
    ![\textrm{span}\!\left( \vec{v}_1, \ldots, \vec{v}_n \right)
    \; \eqdef \; 
    \{   \vec{v} \in V \; | \; 
    \vec{v} = \alpha_1\vec{v}_1 + \cdots + \alpha_n\vec{v}_n,\;  \alpha_i \in \mathbb{R} 
    \}.](./images/7058d3cd4c3d20b5e7de6b77a1bbb04cbb63a6be.png)
    

For every matrix ![M \in \mathbb{R}^{m\times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png), we define the following _fundamental subspaces_ associated with the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png):

-   ![\mathcal{R}(M) \subseteq \mathbb{R}^n](./images/e0e51fbcc74b2b05175c2fb4f95f52c3e7b2d5c2.png): the _row space_ of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) consists of all possible linear combinations of the rows of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png).
-   ![\mathcal{C}(M)\subseteq \mathbb{R}^m](./images/df1d79911cc6634f1a684370b8ec3150498f8e03.png): the _column space_ of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) consists of all possible linear combinations of the columns of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png).
-   ![\mathcal{N}(M) \subseteq \mathbb{R}^n](./images/69b9ca1e3c783d3cfb8ea05ded1c81b09339eeab.png): the _null space_ of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is the set of vectors that go to the zero vector when multiplying ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) from the right: ![\mathcal{N}(M) \eqdef \{ \vec{v} \in \mathbb{R}^n \;|\;M\vec{v} = \vec{0} \,\}](./images/551d23fd5a2dceb35724921aee435262da67fe10.png).
-   ![\mathcal{N}(M^\sfT)](./images/0363059816fea5757210b13c001a730e237cbead.png): the _left null space_ of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is the set of vectors that go to the zero vector when multiplying ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) from the left: ![\mathcal{N}(M^\sfT) \eqdef \{ \vec{w} \in \mathbb{R}^m \;|\; \vec{w}^\sfT M = \vec{0}^\sfT \}](./images/231152bbf0b344374e72f11074bbb8d28d130eb0.png).

The dimensions of the column space and the row space of a matrix are equal. We call this dimension the _rank_ of the matrix: ![\textrm{rank}(M) \eqdef \dim(\mathcal{C}(M)) = \dim(\mathcal{R}(M))](./images/353c3a10349542fce02359db90586d64a6237d37.png).

###[Vector space](./Front matter.md)

A vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) consists of a set of vectors and all possible linear combinations of these vectors. The notion of _all possible linear combinations_ is very powerful. In particular, it implies two useful properties. First, vector spaces are _closed under addition_: for all vectors in that space, the sum of two vectors is also a vector in that vector space. Mathematically, we write this as

![\forall \, \vec{v}_1, \vec{v}_2 \,\in V, \qquad \vec{v}_1+\vec{v}_2 \; \in \; V.](./images/6dea8eaffa95189b34d24805196fe7088d672e0b.png)

Recall the symbol ![\forall](./images/2454ab24706a8b1ba8fad496a7e8193bf39d07e1.png) is math shorthand for the phrase “for all.”

Second, vector spaces are _closed under scalar multiplication_:

![\forall \alpha \in \mathbb{R} \; \textrm{and} \; \vec{v} \in V, \qquad  \alpha \vec{v} \in V. \qquad \qquad](./images/231a67842f508a3761f10d3d4fa5b4823495399a.png)

Starting from any vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) and scaling the vector by any constant ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) results in a vector in the same vector space.

These two properties codify the essential nature of what a vector space is: a space of vectors that can be added together and scaled by constants.

###[Span](./Front matter.md)

The _span_ operator is a useful shorthand for denoting “the set of all linear combinations” of some set of vectors. This may seem like a weird notion at first, but it will prove very useful for describing vector spaces.

Let’s now illustrate how to define vector spaces using the span operator through some examples. Given a vector ![\vec{v}_1 \in V](./images/d31163f982c35a739d09c2c15dc9fd0fdbfed88d.png), define the following vector space:

![V_1 \eqdef \textrm{span}( \vec{v}_1 )
= \{ \vec{v} \in V \; |  \; \vec{v} = \alpha \vec{v}_1 \textrm{ for some } \alpha \in \mathbb{R} \}.](./images/cbcf412e7cbce3209f21e89336c1ab236b730cb9.png)

We say ![V_1](./images/d5c2ea480bc621ea9e17c050369ce2500b7dbac0.png) is _spanned_ by ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png), which means any vector in ![V_1](./images/d5c2ea480bc621ea9e17c050369ce2500b7dbac0.png) can be written as a multiple of ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png). The shape of ![V_1](./images/d5c2ea480bc621ea9e17c050369ce2500b7dbac0.png) is an infinite line.

Given two vectors ![\vec{v}_1, \vec{v}_2\in V](./images/01eb70af206277ca3a1912a27b00b41622080b1e.png), we define the vector space spanned by these vectors as

![V_{2} 
\eqdef \textrm{span}( \vec{v}_1, \vec{v}_2 )
= \{ \vec{v} \in V \; |  \; \vec{v} = \alpha \vec{v}_1 + \beta\vec{v}_2 \textrm{ for some } \alpha,\beta \in \mathbb{R} \}.](./images/6559fdce7b6ebf4470768d42d8e2280bbfdc8378.png)

The vector space ![V_{2}](./images/2afb7677b53adc5b4a76fcb7be639aed65b1bc2a.png) contains all vectors that can be written as a linear combination of ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png). This is a two-dimensional vector space. Geometrically speaking, the shape of ![V_{2}](./images/2afb7677b53adc5b4a76fcb7be639aed65b1bc2a.png) is an infinite plane that passes through the origin.

Now suppose we’re given three vectors ![\vec{v}_1, \vec{v}_2, \vec{v}_3 \in V](./images/4e33b30a46cd1ef2eadc419ce4b3e91c5054c24f.png), such that ![\vec{v}_3=\vec{v}_1+\vec{v}_2](./images/674a11149df04d59e5d2cff8a21ff62a8f6a3f31.png), and we define the vector space ![V_{3} \eqdef \textrm{span}( \vec{v}_1, \vec{v}_2, \vec{v}_3 )](./images/73a4faa15e1abc975cea106ef869a3fff0cb9737.png). The vector space ![V_{3}](./images/71b4b1d6417ceb14a8fd30a4eed3a60f9bc06fa0.png) is actually the same as ![V_{2}](./images/2afb7677b53adc5b4a76fcb7be639aed65b1bc2a.png); adding the vector ![\vec{v}_3](./images/d63fd9bb74319ed4e2f1dfb7240598e43ac4d302.png) to the span of ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png) does not enlarge the vector space because the vector ![\vec{v}_3](./images/d63fd9bb74319ed4e2f1dfb7240598e43ac4d302.png) is a linear combination of ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png). Geometrically speaking, the vector ![\vec{v}_3](./images/d63fd9bb74319ed4e2f1dfb7240598e43ac4d302.png) lies in the same plane as ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png).

Consider the vector space ![V_{2}^\prime =\textrm{span}( \vec{v}_1, \vec{v}^\prime_2 )](./images/4e94b832077af38784734ce83917e8f42d9ad097.png), where ![\vec{v}^\prime_2 = \gamma\vec{v}_1](./images/526f671a8e5965e6c84f98daff675653b70bc501.png), for some ![\gamma \in \mathbb{R}](./images/ce86285f623eadac17211f3989ef1e8077b6ee58.png). Since ![\vec{v}^\prime_2](./images/eaf50894270b7072f56bfe40b2c130e6dbbcb8cb.png) is a linear combination of the vector ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png), the vector space ![V_{2}^\prime](./images/213292317dd51488e98d7f1ea81e4846a52e218a.png) is one-dimensional. In fact, ![V_{2}^\prime](./images/213292317dd51488e98d7f1ea81e4846a52e218a.png) is the same as the vector space ![V_1](./images/d5c2ea480bc621ea9e17c050369ce2500b7dbac0.png) defined above: ![V_2^\prime = \textrm{span}( \vec{v}_1, \vec{v}^\prime_2 ) = \textrm{span}( \vec{v}_1 ) = V_1](./images/412628b8b60ebd63f9f9261d843256c8b3052b83.png).

Note that the word “span” can be used as a verb or a noun. The statement “The vectors ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png) span the vector space ![V_2](./images/2afb7677b53adc5b4a76fcb7be639aed65b1bc2a.png)” is equivalent to the statement “The span of ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png) is ![V_2](./images/2afb7677b53adc5b4a76fcb7be639aed65b1bc2a.png).” Both uses of the word communicate the same idea.

###[Vector subspaces](./Front matter.md)

We use the notation ![W \subseteq V](./images/fe3c4c0997eb9a8f0f62a9774b91a1b0a2e5aaf2.png) to indicate that ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) is a _subspace_ of ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). A _subspace_ is a subset of the vectors in the larger space that has a vector space structure. In other words, ![W \subseteq V](./images/fe3c4c0997eb9a8f0f62a9774b91a1b0a2e5aaf2.png) if the following conditions are satisfied:

-   ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) is contained in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png): for all ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png), if ![\vec{w} \in W](./images/39f41ad30bac5c215f204e76604507821089cd00.png), then ![\vec{w} \in V](./images/ee2986b7b87f9a27e85029b0982bcb9d315bbd8c.png).
-   ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) is closed under addition: for all ![\vec{w}_1,\vec{w}_2 \in W](./images/f0632fcaea7e7f73b216b9dbdecc488a6457fa02.png), ![\vec{w}_1 + \vec{w}_2  \in W](./images/e4514d857fdef30a517112ef09dd236d1502f968.png).
-   ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) is closed under scalar multiplication: for all ![\vec{w} \in W](./images/39f41ad30bac5c215f204e76604507821089cd00.png), ![\alpha \vec{w} \in W](./images/6ed09bbaa01d7a012f122586f0350c06f03a0fd8.png).

Subspaces always contain the zero vector ![\vec{0}](./images/65166afafe3ddf1f84ea3e171c71602a0cc52b15.png). This is implied by the third condition: _any_ vector becomes the zero vector when multiplied by the scalar ![\alpha=0](./images/9e8044e38db946eaa5abcc50bf8b667b562475e9.png): ![\alpha \vec{w} = 0\vec{w}= \vec{0}](./images/e4f2184e7538b7a1dd22b213080ec837e865439e.png).

###[Subspaces specified by constraints](./Front matter.md)

One way to define a vector subspace ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) is to start with a larger space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) and describe a _constraint_ that is satisfied by all vectors in the subspace ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png). For example, the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane is defined as the set of vectors ![(x,y,z) \in \mathbb{R}^3](./images/877b62a173c53ca5831f3444d0937c7a03b93642.png) that satisfy the constraint

![(0,0,1) \cdot (x,y,z) = 0.](./images/0a090bb8036909481ca72b10fd68141223f7d18d.png)

More formally, we define the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane as

![P_{xy} = \{ (x,y,z) \in \mathbb{R}^3 \; | \;  (0,0,1) \cdot (x,y,z) = 0 \}.](./images/720835d4624d677b188b6fc94ad6b0c7b4ad291a.png)

Since the vector ![\hat{k} = (0,0,1)](./images/d16e559f75f48c3b2ab6c4cb96495aa3027548d4.png) is perpendicular to all vectors in the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane, we can describe the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane as “the set of all vectors perpendicular to the vector ![\hat{k}](./images/1427cff1bf4c402fb2a07d3b871082761b7c2102.png).”

###[Subspaces specified as a span](./Front matter.md)

Another way to represent the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane is to describe it as the span of two linearly independent vectors in the plane:

![P_{xy} = \textrm{span}( \, (1,0,0), (0,1,0) \, ),](./images/ddd5dd893ce298506fee7214e43babc6d0553c18.png)

which is equivalent to saying,

![P_{xy} = \{ \vec{v} \in \mathbb{R}^3 \; | \;  \vec{v} = \alpha (1,0,0) + \beta(0,1,0), \; \forall \alpha,\beta \in \mathbb{R} \}.](./images/9d1bba2457093d2955555c7322d870fd8694cf35.png)

This expression is a _parametrization_ of the space ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png) with ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) as the two parameters. Each point in the plane is described by a unique pair of parameters ![(\alpha,\beta)](./images/697be2bf6cba96e4a3f75cad0787fcd4e6cf2ebe.png). The parametrization of an ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-dimensional vector space requires ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) parameters.

###[Subsets vs. subspaces](./Front matter.md)

In linear algebra, the terms _subset_ and _subspace_ are used somewhat interchangeably, and the same symbol is used to denote both subset (![S\subseteq V](./images/08dbf4e769974b498e1a3dc349427c6a1a499e8c.png)) and subspace (![W\subseteq V](./images/fe3c4c0997eb9a8f0f62a9774b91a1b0a2e5aaf2.png)) relationships. Every subspace is also a subset, but not every subset is a subspace.

Let’s clarify the distinction between the terms _subset_ and _subspace_. Assume we’re working in a vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). A subset of ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) can be described in the form ![S = \{ \vec{v} \in V \, | \, \langle\textrm{conditions}\rangle\,\}](./images/48b8652da8a8f8581abba17ec3c5391df72fd951.png) and consists of all vectors in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) that satisfy the ![\langle\textrm{conditions}\rangle](./images/7f44f36c602ac56f54c6b6ce7bf42d4b827aaa8f.png). A subspace ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) is a type of subset with a _vector space structure_, meaning it is closed under addition (for all ![\vec{w}_1,\vec{w}_2 \in W](./images/f0632fcaea7e7f73b216b9dbdecc488a6457fa02.png), ![\vec{w}_1 + \vec{w}_2  \in W](./images/e4514d857fdef30a517112ef09dd236d1502f968.png)), and closed under scalar multiplication (for all ![\vec{w} \in W](./images/39f41ad30bac5c215f204e76604507821089cd00.png), ![\alpha \vec{w} \in W](./images/6ed09bbaa01d7a012f122586f0350c06f03a0fd8.png)). When mathematicians refer to some subset as a _subspace_, they’re letting you know that you can take arbitrary vectors in the set, scale or add them together, and obtain a vector in the same set.

To further illustrate the difference between _subsets_ and _subspaces_, let’s compare the solution sets of two systems of equations: ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) and ![A\vec{x}=\vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png). The solution set of ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) is ![\{\vec{c} + \vec{v}_n\}](./images/eb94bb729b17fd445e3c405ba1e405523662d1cf.png), for all ![\vec{v}_n \in \mathcal{N}(A)](./images/46c80ecce5bffb1ec69aaab854df0e8fd5ce052e.png), which is not a subspace of ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) unless ![\vec{c}=\vec{0}](./images/508a32bf6802bef3711479b4f49831a992253918.png). Observe that if ![\vec{x}_1=\vec{c}+\vec{v}_1](./images/a597465729655e5c61a90fa99cc5d3ea44eba065.png) and ![\vec{x}_2=\vec{c}+\vec{v}_2](./images/b51881908172f33c6e62cf6843d38e2b030ae7c0.png) are two solutions to ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png), their sum is not a solution: ![\vec{x}_1 + \vec{x}_2 = 2\vec{c} + \vec{v}_1 + \vec{v}_2  \; \notin \; \{\vec{c} + \vec{v}_n\}](./images/a257f1a6ffd0800bcea74b126076ad6d14df57f6.png). The solution set to the equation ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) is not a subspace. In contrast, the solution set of ![A\vec{x}=\vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png) is a _vector space_ that is called _null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)_ and denoted ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png). If ![\vec{x}_1](./images/a144b7d5b5354457f21d08250875c9a95f1d6554.png) and ![\vec{x}_2](./images/701880e3ac7897437c7159afef5e7c4fa36ac287.png) are two solutions to ![A\vec{x}=\vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png), then ![\alpha \vec{x}_1+\beta \vec{x}_2](./images/fe3582c04b6ed4994c6fae3c0bf680db617ec890.png) is also a solution to ![A\vec{x}=\vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png).

####[A real-life situation](./Front matter.md)

You walk into class one day and are caught completely off guard by a surprise quiz—wait, let’s make it a mini-exam for emotional effect. Although you’ve read a chapter or two in the book, you’ve been “busy” and are totally unprepared for this exam. The first question asks you to “find the solution of the _homogeneous_ system of equations and the _non-homogeneous_ system of equations.” You rack your brain, but the only association with homogeny that comes to mind is the homogenized milk you had for breakfast. Oh, there’s more: the question also asks you to “state whether each of the solutions obtained is a _vector space_.” As you stare at the page, the words and equations begin to blur and panic sets in.

Don’t fear! Look at the problem again. You don’t know what the heck a homogeneous system of equations is, but you sure as heck know how to solve systems of equations. You solve the given system of equations ![A\vec{x} = \vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) by building the augmented matrix ![[ \, A\, | \, \vec{b} \,]](../Images/cc915725ad874062d2459af26791e32439eefc58.png) and computing its reduced row echelon form using row operations. You obtain the solution set ![\vec{x} = \{ \vec{v} \in V \, | \, \vec{v} = \vec{c} + t \vec{v}_n, \, \forall t \in \mathbb{R} \}](./images/076a038ee7b59a3ba61aa9b8d44ab54597703c33.png), where ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) is the particular solution and ![\vec{v}_n](./images/f4fabcdafdd663efccc2dc73cd64a68ae070ec63.png) is a vector that spans the null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

Next, you ponder the “vector space” part of the question. You notice the solution set to the _system_ of equations ![A\vec{x} = \vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) isn’t a vector space since it doesn’t pass through the origin. However, the solution set to the equation ![A\vec{x} = \vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png) _is_ a vector space ![\{ \vec{v} \in V \, | \, \vec{v} = t\vec{v}_n, \, \forall t \in \mathbb{R} \} = \textrm{span}( \vec{v}_n )](./images/b9859a0328e60501f2f1c005e74007b66a25527d.png). Suddenly it clicks: a _homogeneous_ system of equations must be the system of equations ![A\vec{x}=\vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png), in which the constants on the right side of the equation are all zero. The term _homogeneous_ kind of makes sense; all the constants of the right side have the same value ![b_1=b_2=\cdots=0](./images/cff783d285464a3cbda1a02f1933cfc0b257e161.png). The solution to the non-homogeneous system of equations ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) is the set ![\{ \vec{c} + s \vec{v}_n, \, \forall s \in \mathbb{R} \}](./images/19ac28ed12c259d6b7a88f92f32279e8bf6df0b8.png), which is not a vector space. The solution to the homogeneous system of equations ![A\vec{x}=\vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png) is ![\{ \vec{v} \in V \, | \, \vec{v} = t \vec{v}_n, \, \forall t \in \mathbb{R} \}](./images/66a2d26b376a1e9ee076b9ae700941cfb1b8cae1.png), which is a vector space. Well done!

###[Matrix fundamental subspaces](./Front matter.md)

We now define four _fundamental subspaces_ associated with a matrix ![M \in \mathbb{R}^{m\times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png).

-   The column space ![\mathcal{C}(M)](./images/041f2eb567ff07b61707a135e5034908da7356fb.png) is the span of the columns of the matrix. The column space consists of all possible output vectors the matrix can produce when multiplied by a vector from the right:
    
    ![\mathcal{C}(M) \eqdef \{ \vec{w} \in \mathbb{R}^m
    \; | \; 
    \vec{w} = M\vec{v} \textrm{ for some } \vec{v} \in \mathbb{R}^{n} \}.](./images/c49009015317d774b738bf012a94a6f44a16e185.png)
    
-   The null space ![\mathcal{N}(M)](./images/b2b278a718926bbd8fe6fd73a60a504f938642b4.png) of a matrix ![M \in \mathbb{R}^{m\times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png) consists of all vectors the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) sends to the zero vector:
    
    ![\mathcal{N}(M) \eqdef \{ \vec{v} \in \mathbb{R}^n \; | \; M\vec{v} = \vec{0} \}.](./images/9d563b9b62e701c9c294d2d94fbfc86ac336e69e.png)
    
    The null space is sometimes called the _kernel_ of the matrix.
    
-   The row space ![\mathcal{R}(M)](./images/61a4071689dae6b91184f94760c9ed7e9c6d88d1.png) is the span of the rows of the matrix. We obtain linear combinations of the rows by multiplying the matrix with an ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-dimensional vector from the left:
    
    ![\mathcal{R}(M) \eqdef \{ \vec{v} \in \mathbb{R}^n \; | \; \vec{v} 
    = \vec{w}^\sfT\!M \textrm{ for some } \vec{w} \in \mathbb{R}^{m} \}.](./images/56a16e7636e98d5ba55590d15e4e76bfa18fa519.png)
    
    Note, we used the transpose ![^\sfT](./images/a462348fa44a14519bb7f3a98207adcc6cb061da.png) to transform ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) to a row vector.
    
-   The left null space ![\mathcal{N}(M^\sfT)](./images/0363059816fea5757210b13c001a730e237cbead.png) of a matrix ![M \in \mathbb{R}^{m\times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png) consists of all vectors the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) sends to the zero vector when multiplied from the left:
    
    ![\mathcal{N}(M^\sfT) \eqdef \{ \vec{w} \in \mathbb{R}^m \; | \; \vec{w}^\sfT \! M = \vec{0}^\sfT \}.](./images/41944e94aede04ac022cad9cdbb835a06023ef42.png)
    

These vector spaces are called _fundamental_ because they describe important properties of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). Recall that matrix equations can be used to represent systems of linear equations, as well as linear transformations. A solid understanding of the fundamental subspaces leads to a solid understanding of linear equations and linear transformations.

###[Matrices and systems of linear equations](./Front matter.md)

The null space ![\mathcal{N}(M)](./images/b2b278a718926bbd8fe6fd73a60a504f938642b4.png) corresponds to the solution set of the matrix equation ![M\vec{x} = \vec{0}](./images/3a8341083cd74c2a0970b3263aaf41468d1b87cb.png). If a matrix has a nonempty null space, the system of equations corresponding to ![M\vec{x}=\vec{b}](./images/23acf556acd07509922df019602ebafb01da4bb7.png) has an infinite solution set. Indeed, we can write the solution of ![M\vec{x}=\vec{b}](./images/23acf556acd07509922df019602ebafb01da4bb7.png) as a _particular solution_ ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) plus all possible vectors in the null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png):

![\vec{x} = \vec{c} +  \textrm{span}( \vec{v}_1, \ldots, \vec{v}_k ),
\quad \textrm{where} \quad 
\textrm{span}( \vec{v}_1, \ldots, \vec{v}_k ) = \mathcal{N}(M).](./images/f4688a6ef9998ae66ca41d2cf0f01422ff165156.png)

We can verify this claim as follows. Suppose ![\vec{x}=\vec{c}](./images/da1591c1a03fd52e27b37ca969f410b30b38040b.png) is a solution to the equation ![M\vec{x}=\vec{b}](./images/23acf556acd07509922df019602ebafb01da4bb7.png). Consider the vector ![\vec{x} = \vec{c} + \alpha_1 \vec{v}_1 + \cdots + \alpha_k \vec{v}_k](./images/3387aa8fd74234127a68c8bf2136de39b0cf9319.png), which contains ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) and some arbitrary linear combination of vectors from the null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). Observe that ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) is also a solution to the equation ![M\vec{x}=\vec{b}](./images/23acf556acd07509922df019602ebafb01da4bb7.png):

![M\vec{x} 
= M(\vec{c} + \alpha_1 \vec{v}_1  + \cdots + \alpha_k \vec{v}_k)
= M\vec{c} + \alpha_1 \cancelto{0}{M\vec{v}_1}  + \cdots + \alpha_k \cancelto{0}{M\vec{v}_k}
= M\vec{c} = \vec{b}.](./images/e8282b536a686c750d7f328f70da7ee1e2811bd6.png)

If the null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) contains only the zero vector ![\{ \vec{0} \}](./images/44a75f16c14be3faf1008f18e1d0076952c967b6.png), then the system of equations ![M\vec{x}=\vec{b}](./images/23acf556acd07509922df019602ebafb01da4bb7.png) has a unique solution. It’s worth connecting the above observations with what we learned about the Gauss–Jordan elimination procedure in[Chapter 3](./Chapter 3_ Computational linear algebra.md). Suppose we want to solve the matrix equation ![M\vec{x}=\vec{b}](./images/23acf556acd07509922df019602ebafb01da4bb7.png), where ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is an ![(m\times n)](./images/86d74e01b6a99f43386b8cbf5d78c67c279e899e.png)\-dimensional matrix, ![\vec{x}=(x_1,x_2,\ldots,x_n)^\sfT](./images/d3239035f0703068c160aa5e716e58e7b69f12b7.png) is an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector of unknowns, and ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) is an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector of constants. We can construct the augmented matrix ![[\:M\; | \; \vec{b}\:]](../Images/36ac424d36667b368bb79b250bf051d1fd933e3f.png) and perform row operations until we bring the augmented matrix to its reduced row echelon form ![[\:\textrm{rref}(M)\; | \; \vec{c}\:]](../Images/945e02529ff542821508fe2881c9b0831cbf4c66.png). In the case where the null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png)\-dimensional, the reduced row echelon form of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) will have ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png) free variables and ![n-k](./images/86075e0aeeedcb0bffbee81606c464c216c508c0.png) pivots. The solution the system of equations is ![\vec{x} = \vec{c} + \alpha_1 \vec{v}_1  + \cdots + \alpha_k \vec{v}_k](./images/3387aa8fd74234127a68c8bf2136de39b0cf9319.png), where ![\{\vec{v}_1, \ldots, \vec{v}_k\}](./images/0166013743dcdeb80cba52bffa7d2f627052806a.png) are the vectors in the null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png).

###[Matrices and linear transformations](./Front matter.md)

Matrices can be used to _represent_ linear transformations. We postpone the detailed discussion about linear transformations and their representation as matrices until[Chapter 5](./Chapter 5_ Linear transformations.md), but we’ll discuss the subject here briefly—mainly to introduce an important connection between the column space and the row space of a matrix, and to explain why each matrix has _two_ null spaces (what’s up with that?).

####[Matrix-vector and vector-matrix products](./Front matter.md)

A matrix ![M \in \mathbb{R}^{m \times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png) corresponds to not one but _two_ linear transformations. Up until now we’ve focused on the matrix-vector product ![M\vec{x}=\vec{y}](./images/5eecbaaddaa68eb1ccd2e90747a570659b32f2b9.png), which corresponds to a linear transformation of the form ![T_M:\mathbb{R}^{n} \to \mathbb{R}^{m}](./images/d614512014c4b2224d731e9951a540c501bead6e.png). In addition to the linear transformation we obtain by multiplication from the right, there is also the option of multiplying ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) by a vector from the left: ![\vec{a}^\sfT M=\vec{b}^\sfT](./images/705022f1cc5e25c0130237aaff554d4eb96b00e5.png), where ![\vec{a}^\sfT](./images/bca6c2d4866ea8ae39c641df95dc051e41b5c8ac.png) (the input) is an ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-dimensional row vector, and ![\vec{b}^\sfT](./images/2c3576ee6b12c95a4ee4a7df161ab6041e03b732.png) (the output) is an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional row vector[1](./Front matter.md)

The vector-matrix product ![\vec{a}^\sfT M=\vec{b}^\sfT](./images/705022f1cc5e25c0130237aaff554d4eb96b00e5.png) corresponds to a linear transformation of the form ![T_{M^\sfT}:\mathbb{R}^{m} \to \mathbb{R}^{n}](./images/f509e202c6732b5058f67e19e88c6ccd0518e300.png). We identify the output of this linear transformation, ![\vec{b}=T_{M^\sfT}(\vec{a})](./images/5ba9459ed1cfc8c51af7101f5fbbef429c4e014c.png), with the result of the vector-matrix product ![\vec{b}^\sfT = \vec{a}^\sfT M](./images/aa11c0630e65ce4adb270a2136b4d02d607e18a5.png). The linear transformation ![T_{M^\sfT}:\mathbb{R}^{m} \to \mathbb{R}^{n}](./images/f509e202c6732b5058f67e19e88c6ccd0518e300.png) is called the _adjoint_ of the linear transformation ![T_M:\mathbb{R}^{n} \to \mathbb{R}^{m}](./images/d614512014c4b2224d731e9951a540c501bead6e.png). Adjoint linear transformations are represented by the same matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). ![T_M](./images/8f887452f4fa8d12625c92f275791e13cea1e14b.png) is defined as the multiplication of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) from the right, while ![T_{M^\sfT}](./images/38a86ff8e1ca962f1857d3a9c220ad2e6b1ec68f.png) is defined as multiplication of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) from the left.

Let’s clarify why we used the notation ![T_{M^\sfT}](./images/38a86ff8e1ca962f1857d3a9c220ad2e6b1ec68f.png) to denote the adjoint operation of ![T_M](./images/8f887452f4fa8d12625c92f275791e13cea1e14b.png). We previously used the notation ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) to describe the linear transformation obtained by right multiplication by ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) (![T_A(\vec{x}) = A\vec{x}](./images/2f3847c88f1c8b24c3600fb2438ca44b880e5269.png)). Instead of creating a new notation for left multiplication, we can transform left multiplication into right multiplication by using the transpose operation:

![\vec{a}^\sfT \!A  = \vec{b}^\sfT
\qquad
\Rightarrow
\qquad
\left( \, \vec{a}^\sfT \!A  \, \right)^{\!\!\sfT} = \left( \vec{b}^\sfT \right)^{\!\!\sfT}
\qquad
\Rightarrow
\qquad
A^\sfT \vec{a} = \vec{b}.](./images/49f5cebd585e1a90971aff03373cc55b8b4b8900.png)

**We can think of left multiplication by ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as right multiplication by ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png).** This correspondence also explains why we use the notation ![\mathcal{N}(M^\sfT)](./images/0363059816fea5757210b13c001a730e237cbead.png) for the left null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png); we can rewrite the condition ![\vec{w}^\sfT M = \vec{0}^\sfT](./images/f3c654d2c72cc3a7bf60df3ca36900fbfecf013f.png) as ![M^\sfT\vec{w} = \vec{0}](./images/965e7093e5b277246090b735f78823cd34fa0b92.png), so the left null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is equivalent to the right null space of ![M^\sfT](./images/351e3c059c9c1ab7f9c3644694084f639f6fd2eb.png).

####[Left and right input spaces](./Front matter.md)

Let’s call the _left space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png)_ the set of vectors suitable for multiplying ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) from the left. Similarly, we’ll call _right space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png)_ the set of vectors suitable for multiplying ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) from the right. If ![M \in \mathbb{R}^{m \times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png), the left space is ![\mathbb{R}^{m}](./images/4d4f5acbadc1b9a3febf3642dbe25d99a4704061.png) and the right space is ![\mathbb{R}^{n}](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png).

By combining all the vectors in the row space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) and all the vectors in its null space, we obtain the full right space:

![\mathcal{R}(M) \oplus \mathcal{N}(M) \;  = \; \mathbb{R}^n. \quad](./images/533ab3c99209a3fa4622d2122ccd2fd40f61ccc3.png)

This means any vector ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png) can be written as a sum, ![\vec{v} = \vec{v}_r + \vec{v}_n](./images/6b79e3d2cbab862c15a13ecd9364afeea70e3b70.png), such that ![\vec{v}_r \in \mathcal{R}(M)](./images/8fa170b87f7a3346bb8c9d24c865c1e0aff6c10a.png) and ![\vec{v}_n \in \mathcal{N}(M)](./images/51be56c54e4e51b3b32df36b0a83c019e06d66d4.png). The symbol ![\oplus](./images/6a61dca4d2971f0ac55df48a1ea4eefb5483aeb0.png) stands for _orthogonal sum_, which means we can pick ![\vec{v}_r](./images/86d1ae18e7acb6f9a84c7463c32241d9d9395d07.png) and ![\vec{v}_n](./images/f4fabcdafdd663efccc2dc73cd64a68ae070ec63.png) to be orthogonal vectors, ![\vec{v}_r \cdot \vec{v}_n=0](./images/d3a646fe75df0ec4d1912a44e5930744ddbee648.png).

If we consider the dimensions involved the above equation, we obtain the following important relation between the dimension of the row space and the null space of a matrix:

![\dim(\mathcal{R}(M))  + \dim( \mathcal{N}(M)) = n  =  \dim(\mathbb{R}^n).](./images/996edb2bdc49d8cc7bea5d44e015b4cc2dea9394.png)

The ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional right space splits into row-space dimensions and null-space dimensions.

Similar to the split in the right space, the left-space ![\mathbb{R}^m](./images/4d4f5acbadc1b9a3febf3642dbe25d99a4704061.png) decomposes into an orthogonal sum of the column space and the left null space of the matrix:

![\mathcal{C}(M) \oplus \mathcal{N}(M^\sfT) \; = \; \mathbb{R}^m.](./images/bdf003cfce49072c88c814c8e2c492d2f1cdfc86.png)

If we count the dimensions in this equation, we obtain a relation between the dimension of the column space and the left null space of the matrix: ![\dim(\mathcal{C}(M))  + \dim( \mathcal{N}(M^\sfT)) = m](./images/7014df6e667b8b0905a76d08e527fcc6c228ed2b.png).

###[Matrix rank](./Front matter.md)

The column space and the row space of a matrix have the same dimension. We call this dimension the _rank_ of the matrix:

![\textrm{rank}(M) \eqdef  \dim\left(\mathcal{R}(M) \right) = \dim\left(\mathcal{C}(M) \right).](./images/1f34dfb7eff6f90a8dd465cf4f08e3e57cf5d383.png)

The _rank_ of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is the number of linearly independent rows in ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png), which is equal to the number of linearly independent columns in ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). The dimension of the null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is called the _nullity_ of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png): ![\textrm{nullity}(M) \eqdef \dim( \mathcal{N}(M))](./images/3a52b8e4fc9d2906954d44c6f415093402b1ca7e.png).

Applying this new terminology, we can update our earlier observation about the dimensions of the right fundamental subspaces of a matrix:

![\textrm{rank}(M) + \textrm{nullity}(M) = n  = \dim(\mathbb{R}^n).](./images/f73961f030f07c8676b0f72a81ef5bfd12a80df9.png)

This formula is called the _rank–nullity theorem_, and can be used to deduce the rank of a matrix given its nullity, or vice versa.

###[Summary](./Front matter.md)

Together, ![\mathcal{R}(M)](./images/61a4071689dae6b91184f94760c9ed7e9c6d88d1.png), ![\mathcal{N}(M)](./images/b2b278a718926bbd8fe6fd73a60a504f938642b4.png), ![\mathcal{C}(M)](./images/041f2eb567ff07b61707a135e5034908da7356fb.png), and ![\mathcal{N}(M^\sfT)](./images/0363059816fea5757210b13c001a730e237cbead.png) describe all aspects of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) when multiplied by vectors from the left or the right. Everything we’ve learned so far about how the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) maps vectors between its left and right spaces can be summarized by the following observations:

![\begin{align*}
\mathcal{C}(M) 		\quad &\overset{M}{\longleftrightarrow}	\quad 		\mathcal{R}(M),				\\
\vec{0}				\quad &\overset{M}{\longleftarrow}	 \quad 			\mathcal{N}(M),				\\
\mathcal{N}(M^\sfT)	\quad &\overset{M}{\longrightarrow}	\quad 			\vec{0}.
\end{align*}](./images/26b2bd64d43cab906a4e6b16c938e7f2f0850758.png)

Note the zero vector in the second row is ![\vec{0} \in \mathbb{R}^m](./images/745354ed2a405633ae8260e09e94c6068a08b249.png), while the zero vector in the third row is ![\vec{0} \in \mathbb{R}^n](./images/62064dd08bfef964d45efb8361274d3317430bf8.png). In[Section 5.1.5](./Chapter 5_ Linear transformations.md), we’ll learn how to interpret the fundamental subspaces of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) as the input and output spaces of the linear transformations ![T_M:\mathbb{R}^n \to \mathbb{R}^m](./images/d614512014c4b2224d731e9951a540c501bead6e.png) and ![T_{M^\sfT}:\mathbb{R}^{m} \to \mathbb{R}^{n}](./images/f509e202c6732b5058f67e19e88c6ccd0518e300.png).

###[Linear independence](./Front matter.md)

One of the most important ideas in linear algebra is the notion of linear independence. Given a set of vectors ![\{ \vec{v}_1, \vec{v}_2, \vec{v}_3 \}](./images/42aaea8f12f0b2fe73ff3c5430ae5a7676459c6a.png), we’re often interested in knowing whether one of the vectors in the set can be written as a linear combination of the other vectors. For example, if ![\vec{v}_3 = \vec{v}_1 + \vec{v}_2](./images/674a11149df04d59e5d2cff8a21ff62a8f6a3f31.png), then the set ![\{ \vec{v}_1, \vec{v}_2, \vec{v}_3 \}](./images/42aaea8f12f0b2fe73ff3c5430ae5a7676459c6a.png) is _linearly dependent_. On the other hand, if none of the vectors in the set can be written as a linear combination of the other vectors, then the set is _linearly independent_.

Understanding the concept of linear independence of a set of vectors is a prerequisite for understanding the concept of a basis for a vector space, so it is important to give a clear definition.

**Definition:** The set of vectors ![\{\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n \}](./images/abdaeb0dbcba5c098940107f852a5b9fc0c2de80.png) is _linearly independent_ if the only solution to the equation

![\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \cdots + \alpha_n\vec{v}_n 
\; = \; 
\vec{0}](./images/a50564dce19b1abe0bc5ab4f4ddbc9eaffea98af.png)

is the zero vector ![(\alpha_1,\alpha_2, \ldots, \alpha_n) =(0,0,\ldots,0)](./images/d88af75e829cb262a3b3d9d491577df69619d22f.png).

When ![\vec{\alpha}=\vec{0}](./images/eb00ae0cde72fc2245a7b065e5ca949a9d9cb888.png) is the only solution to the equation, then none of the vectors ![\vec{v}_i](./images/11553a8d864ca512231bf7ef8cb860c8ad8271ac.png) can be written as a linear combination of the other vectors.

To understand the importance of the all zeros solution, let’s consider an example where a nonzero solution ![\vec{\alpha}](./images/a8c62df1c959768995d74d3973f1b13ca59751f6.png) exists. Suppose the set of vectors ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3 \}](./images/42aaea8f12f0b2fe73ff3c5430ae5a7676459c6a.png) satisfy ![\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \alpha_3\vec{v}_3 = 0](./images/44c3f014b92b6440f0eced8c23c2136d929f0ef7.png), with ![\alpha_1=1](./images/6ae5b014185eeec2f924cc0f06cb497ef14b0a7c.png), ![\alpha_2=1](./images/d7773d4650bc1df7e0a52bd28680122b8b3cbe41.png), and ![\alpha_3=-1](./images/63e0ba8523ca819e7300451e6cb3149da7a434d0.png). Then we can write ![\vec{v}_3=\vec{v}_1 + \vec{v}_2](./images/674a11149df04d59e5d2cff8a21ff62a8f6a3f31.png), which shows that ![\vec{v}_3](./images/d63fd9bb74319ed4e2f1dfb7240598e43ac4d302.png) is a linear combination of ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png), hence the vectors are linearly dependent. The strange wording of the definition in terms of an all zeros solution is required to make the definition of linear independence symmetric. An all zero alphas solution implies that _no_ vector can be written as a linear combination of the other vectors.

###[Basis](./Front matter.md)

To carry out calculations with vectors in a vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), we need to know a basis ![B=\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/8633486a939e2d0b809894ed2c088015e70ef124.png) for that space. Intuitively, a basis for a vector space is any set of vectors that can serve as a coordinate system for that vector space. A _basis_ for an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). Throughout this section, we’ve referred to the _dimension_ of a vector space, which is essentially the number of vectors in a basis for that vector space. A basis for an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space contains exactly ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors. Any set of fewer than ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors would not satisfy the spanning property. Any set of more than ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors from ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) cannot be linearly independent (see page 4.3.3). To form a basis for a vector space, a set of vectors must be “just right”: it must contain a sufficient number of vectors (but not too many) so that the coordinates of each vector are uniquely determined.

###[The rank–nullity theorem](./Front matter.md)

The relationship between the _rank_ and the _nullity_ of a matrix is so important that it’s worth formally stating the rank–nullity theorem.

\[Rank–nullity theorem\]

For any matrix ![M \in \mathbb{R}^{m \times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png), the following statement holds:

![\mathrm{rank}(M) + \mathrm{nullity}(M) = n,](./images/1601ed7662b9a062559cb19e4eca7e9e85d5ed98.png)

where the rank of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is ![\mathrm{rank}(M) =  \dim\!\left(\mathcal{R}(M) \right) = \dim\!\left(\mathcal{C}(M) \right)](./images/3849e4696715f09584a658d0fcdb94acfa7b6dee.png) and its nullity is defined as ![\mathrm{nullity}(M) = \dim( \mathcal{N}(M))](./images/63ba6840dd95448800241b081d33c71e5abea607.png).

The rank–nullity theorem is important because it “splits” the vectors in the right space of the matrix into two categories: those that lie in its row space and those that lie in its null space. We can use the rank–nullity theorem to infer the dimension of the row space of a matrix given the dimension of the null space. Vice versa, given the dimension of a null space, we can infer the dimension of the matrix’s row space.

#####[Example 1](./Front matter.md)

Suppose the null space of the matrix ![M \in \mathbb{R}^{m \times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png) consists only of the zero vector, ![\mathcal{N}(M)=\{\vec{0}\}](./images/14780fa2320bb46742c97d47feafbb0c20b44512.png); then the nullity of the matrix is ![\textrm{nullity}(M)=\dim( \mathcal{N}(M))=0](./images/51b1584fb3c256edb75dd07266edbf3057c03856.png). Using the rank–nullity theorem we can conclude that ![\textrm{rank}(M) = \dim(\mathcal{R}(M)) = \dim\!\left(\mathcal{C}(M) \right) =n](./images/f560a4266d66587afd8e92d5ca782ce668e7c339.png).

#####[Example 2](./Front matter.md)

Consider a matrix ![A \in \mathbb{R}^{3 \times 6}](./images/712fbb3d828f25e5f8ad59cc742bd11d04fda2be.png). After performing some calculations (which we’ll discuss in the next section) we find that one of the rows of the matrix is a linear combination of the other two. Therefore, the row space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is two-dimensional and ![\textrm{rank}(A)=2](./images/89954b1d87364f712590135f4c093dd540fa711b.png). From this, we can infer ![\textrm{nullity}(A)=6-2=4](./images/99d198f2a7d091d48f88e4ec14c91a3295522069.png), meaning the null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is four-dimensional.

###[Distilling bases](./Front matter.md)

A basis for an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) consists of _exactly_ ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors. Any set of vectors ![\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png) can serve as a basis for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), as long as the vectors are linearly independent and there are exactly ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) of them.

Sometimes an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is specified as the span of more than ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors:

![V = \textrm{span}( \vec{v}_1, \vec{v}_2, \ldots, \vec{v}_m ), \quad m > n.](./images/3fac25bb6253b97080a893a2a6ddc1933473e628.png)

Since there are ![m>n](./images/9a407a665f2355894a84a0a1932522814dbaff32.png) of the ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png)\-vectors, there are _too many_ to form a basis. We say this set of vectors is _overcomplete_. They cannot all be linearly independent since there can be at most ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors in an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space.

If we want to find a basis for the space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), we must reject some of the vectors. Given the set of vectors ![\{ \vec{v}_1, \vec{v}_2, \ldots, \vec{v}_m \}](./images/ee9257fc53e8c1624b28bfb24e3538d3ef96b59e.png), our task is to _distill_ a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors ![\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png) from them. We’ll learn how to do this in the next section.

###[Links](./Front matter.md)

\[ Linear combinations, span, and bases explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=k7RM-ot2NWY`](./watch_v=k7RM-ot2NWY.md)

\[ Inverse, column space, and null space explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=uQhTuRlWMxw`](./watch_v=uQhTuRlWMxw.md)

###[Exercises](./Front matter.md)

E4.12 Determine whether the following subsets are subspaces of ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png).

1.  The single vector ![(0,0,0)](./images/6504b17477eb02040594d433af4d4485562e2960.png)
2.  The line ![\ell: \{ (3,3,3) + t(1,1,1), \forall t \in \mathbb{R} \}](./images/5b7dbcda18ec8107c751b1cc00907623d2b3b2ae.png)
3.  The plane defined by the equation ![z=0](./images/5c95e6d91f3f8cef7dce19da420bb299f4f2c24e.png)
4.  The plane defined by the equation ![2x+y+z=3](./images/5739f843ce12705f4148329fa4d6c40b81665e3c.png)
5.  ![\textrm{span}( (1,1,0), (0,1,1) )](./images/d72336b48821606ed90152ffd2f9c71e5c592631.png)

E4.13 Find the rank and the dimensions of the row space, the column space, the null space, and the left null space of each of these matrices.

![A = 	\begin{bmatrix}
1 & 0 &  0 & 0 \\
0 & 1 &  0 & 0 \\
0 & 0 &  0 & 1
\end{bmatrix}
\qquad
B = 	\begin{bmatrix}
1 & 0 &  0 & 0 & 1\\
0 & 0 &  1 & 0 & 0\\
0 & 0 &  0 & 1 & 0\\
0 & 0 &  0 & 0 & 0
\end{bmatrix}
\quad
C = 	\begin{bmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0
\end{bmatrix}
\vspace{-1mm}](./images/ba43a4350912447ad7af626042da434d74ba9c1c.png)

Make sure your answers are consistent with the rank–nullity theorem.

E4.14 Consider the matrix ![A=
\begin{bmatrix}
1 & 0 &  0 & 0 \\
0 & 1 & -1 & 0 \\
0 & 0 &  0 & 0
\end{bmatrix} \in \mathbb{R}^{3\times 4}](./images/964606436d0b22f7ec47912fbb6593bc2c51341d.png). Specify bases for its row space ![\mathcal{R}(A)](./images/3dbad2f997035cd04ed87a50d8ef6864087f6e44.png), its column space ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png), and its null space ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png).

E4.15 Do the matrices ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![-A](./images/19580fb64130a20e1ad78a360f76607f63123b5a.png) have the same fundamental subspaces?

##[4.5 Vector space techniques](./Chapter 4_ Geometric aspects of linear algebra.md)

In this section, we’ll learn how to “distill” a basis for any vector space, which is an important procedure for characterizing vector spaces. Actually, the procedure is not new—it’s really an application of the Gauss–Jordan elimination procedure we saw in[Section 3.1](./Chapter 3_ Computational linear algebra.md).

Starting from a set of vectors that are not linearly independent, we can write them as the rows of a matrix, and then perform _row operations_ on this matrix until we find the reduced row echelon form of the matrix. Since row operations do not change the row space of a matrix, the nonzero rows in the final RREF of the matrix will span the same space as the original set of vectors. The rows in the RREF of the matrix will be linearly independent and thus will form a basis.

The ability to distill a basis is important when characterizing any vector space. The basis serves as the coordinate system for that vector space, and the number of vectors in a basis tells us the dimension of the vector space. For this reason, we’ll spend an entire section learning how to distill bases for various vector spaces.

###[Finding a basis](./Front matter.md)

Suppose the vector subspace ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is defined as the span of ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) vectors ![\{ \vec{u}_1, \vec{u}_2, \ldots, \vec{u}_m \}](./images/0d37090866da62873e15ea44caa55b6235546d0b.png), which are not necessarily linearly independent:

![V  \eqdef  \textrm{span}( \vec{u}_1, \vec{u}_2, \ldots, \vec{u}_m ).](./images/77f3b7bafea1a48433fba0ea9f4523a88edbb3ed.png)

Our task is to find a basis for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). We’re looking for an alternate description of the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) as

![V = \textrm{span}( \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n ),](./images/c0122b1cc8a02bd9b9ab861061e0362fbff3cbd1.png)

such that the vectors ![\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png) will be linearly independent.

One way to accomplish this task is to write the vectors ![\vec{u}_i](./images/6bab6bec1fed9b6fe08b826863602a20207bb02f.png) as the rows of a matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). By this construction, the space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) corresponds to the _row space_ of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png), denoted ![\mathcal{R}(M)](./images/61a4071689dae6b91184f94760c9ed7e9c6d88d1.png). We can then use standard _row operations_ to bring the matrix into its reduced row echelon form. Applying row operations to a matrix does not change its row space: ![\mathcal{R}(M) = \mathcal{R}(\textrm{rref}(M))](./images/05c4b935b6d91b39767c7dbd0a1e333ddb218ae3.png). Transforming the matrix into its RREF allows us to see which of the rows are linearly independent, and thus can serve as basis vectors:

![\begin{bmatrix}
\textrm{ ---} & \vec{u}_1 & \textrm{--- } \\
\textrm{ ---} & \vec{u}_2 & \textrm{--- } \\
\textrm{ ---} & \vec{u}_3 & \textrm{--- } \\
&   \vdots  &     \\
\textrm{ ---} & \vec{u}_m & \textrm{--- }
\end{bmatrix}
\; 
\xrightarrow{  \; \textrm{Gauss--Jordan elimination} \; }
\; 
\begin{bmatrix}
\textrm{ ---} & \vec{e}_1 & \textrm{--- } \\
&   \vdots  &     \\
\textrm{ ---} & \vec{e}_n & \textrm{--- } \\
0 &\;\;  0 \;\; & 0 \\
0 & \;\;  0 \;\;  & 0
\end{bmatrix}\!.](./images/a438cf949e59fed0782b7f3ad291ffc4f9ce424e.png)

The nonzero rows in the RREF of the matrix form a set of linearly independent vectors ![\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png) that span the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). The linearly dependent vectors have been reduced to rows of zeros.

The above process is called “finding a basis” or “distilling a basis” and it’s important you understand how to carry out this procedure. Even more important is that you understand _why_ we’d want to distill a basis in the first place! By the end of the Gauss–Jordan procedure, we obtain a description of the same vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) in terms of a new set of vectors. Why is it better to describe the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) in terms of the vectors ![\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png), rather than in terms of ![\{ \vec{u}_1, \vec{u}_2, \ldots, \vec{u}_m \}](./images/0d37090866da62873e15ea44caa55b6235546d0b.png)?

I’ll tell you exactly why. We prefer to use the basis ![\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png) to characterize the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) because there exists a one-to-one correspondence between each vector ![\vec{v} \in V](./images/3eefde8f9c5d92cf2322bd0bd81265b055ce130a.png) and the coefficients ![v_1,v_2,\ldots,v_n](./images/bef77889247e926b62dc927c4893d7e4987437f6.png) in the linear combination

![\vec{v} \; = \; v_1\vec{e}_1 + v_2\vec{e}_2 +  \cdots +v_n\vec{e}_n.](./images/dc8049dc726f2fbde8532bc0266e527c525097b2.png)

Using the basis ![B = \{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/8633486a939e2d0b809894ed2c088015e70ef124.png) allows us to represent each vector ![\vec{v} \in V](./images/3eefde8f9c5d92cf2322bd0bd81265b055ce130a.png) as a unique list of coordinates ![(v_1,v_2,\ldots, v_n)_B](./images/5f2c37920ff0642aa88735507ae76fafbdf501fe.png).

Expressing every vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) as a unique list of coordinates would not be possible if we used the vectors ![\{ \vec{u}_1, \vec{u}_2, \ldots, \vec{u}_m \}](./images/0d37090866da62873e15ea44caa55b6235546d0b.png) to describe the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). Since the vectors ![\{ \vec{u}_1, \vec{u}_2, \ldots, \vec{u}_m \}](./images/0d37090866da62873e15ea44caa55b6235546d0b.png) are not linearly independent, the same vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) can be represented by many different linear combinations of the form

![\vec{v} \; = \; v^\prime_1\vec{u}_1 + v^\prime_2\vec{u}_2 +  \cdots +v^\prime_m\vec{u}_m.](./images/307fc46660cb517e1d09fe441e5a7d7e9b0d8190.png)

We cannot identify ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) with a _unique_ set of coefficients ![v^\prime_1, v^\prime_2, \ldots, v^\prime_m](./images/afd275516fc3fb09b7dfc00f8314b414187e5c8d.png), therefore vectors are not represented faithfully by the coefficients in the linear combination.

Another reason we prefer to describe ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) in terms of a basis is because we can immediately see the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional, since there are ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors in the basis for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png).

###[Definitions](./Front matter.md)

-   ![B = \{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n \}](./images/8633486a939e2d0b809894ed2c088015e70ef124.png). A _basis_ for an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) is a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors that span ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png). Any vector ![\vec{v} \in S](./images/509bab64dc06f23e6f1eb603c0465659df0dc4e9.png) can be written as a linear combination of the basis vectors:
    
    ![\vec{v} = v_1 \vec{e}_1 + v_2 \vec{e}_2 + \cdots + v_n \vec{e}_n.](./images/d0d4abf4f2d099251da98cf53ceb76ddd4d9e507.png)
    
    A basis for an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space contains exactly ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors.
    
-   ![\textrm{dim}(S)](./images/4e4bf34cba2131deea72f348dd4f50f8c0a55076.png): the dimension of the vector space ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) is equal to the number of vectors in a basis for ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png).

Recall the four _fundamental subspaces_ of a matrix ![M \in \mathbb{R}^{m \times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png) we defined in the previous section:

-   ![\mathcal{R}(M)\subseteq \mathbb{R}^n](./images/e0e51fbcc74b2b05175c2fb4f95f52c3e7b2d5c2.png): the _row space_ of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) that consists of all possible linear combinations of the rows of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png).
-   ![\mathcal{N}(M)\subseteq \mathbb{R}^n](./images/69b9ca1e3c783d3cfb8ea05ded1c81b09339eeab.png): the _null space_ of the matrix contains all the vectors that become the zero vector when multiplied by ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png):
    
    ![\mathcal{N}(M) \eqdef \{ \, \vec{v} \in \mathbb{R}^n \;\;| \;\;M\vec{v} = \vec{0} \; \}.](./images/1e8f87c869a1eeab7db007792facde1dc42db9ff.png)
    
-   ![\mathcal{C}(M)\subseteq \mathbb{R}^m](./images/df1d79911cc6634f1a684370b8ec3150498f8e03.png): the _column space_ of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) that consists of all possible linear combinations of the columns of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png).
-   ![\mathcal{N}(M^\sfT) \subseteq \mathbb{R}^m](./images/6bf7f406cf85f9f012361d5caeeb201d94919e88.png): the _left null space_ of the matrix contains all the vectors that become the zero vector when multiplying ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) from the left:
    
    ![\mathcal{N}(M^\sfT) \eqdef \{ \vec{w} \in \mathbb{R}^m \; | \; \vec{w}^\sfT M = \vec{0}^\sfT \}.](./images/12078a650e05442faa8f712b071d9398d467f57d.png)
    

###[Bases for the fundamental subspaces of matrices](./Front matter.md)

Performing the Gauss–Jordan elimination procedure on a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has the effect of distilling a basis for its row space ![\mathcal{R}(A)](./images/3dbad2f997035cd04ed87a50d8ef6864087f6e44.png). How do we find bases for the other fundamental subspaces of a matrix? In this section, we’ll learn about a useful shortcut for computing bases for the column space ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png) and the null space ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png) of a matrix, starting from the reduced row echelon form of the matrix. Sorry, there is no shortcut for finding the left null space—we’ll have to use the transpose operation to obtain ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png) and then find its null space ![\mathcal{N}(A^\sfT)](./images/c000bec6891375191f8d0e221f13c6ae42ca6c7e.png).

Pay careful attention to the locations of the pivots (leading ones) in the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), because they play an important role in the procedures described below.

####[Basis for the row space](./Front matter.md)

The row space ![\mathcal{R}(A)](./images/3dbad2f997035cd04ed87a50d8ef6864087f6e44.png) of a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is defined as the space of all vectors that can be written as linear combinations of the rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). To find a basis for ![\mathcal{R}(A)](./images/3dbad2f997035cd04ed87a50d8ef6864087f6e44.png), we use the Gauss–Jordan elimination procedure:

1.  Perform row operations to find the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).
2.  The nonzero rows in the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a basis for ![\mathcal{R}(A)](./images/3dbad2f997035cd04ed87a50d8ef6864087f6e44.png).

####[Basis for the column space](./Front matter.md)

To find a basis for the column space ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png) of a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), we need to determine which columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are linearly independent. To find the linearly independent columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), follow these steps:

1.  Perform row operations to find the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).
2.  Identify the columns that contain pivots (leading ones).
3.  The corresponding columns in the original matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a basis for the column space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

This procedure works because elementary row operations do not change the independence relations between the columns of the matrix. If two columns are linearly independent in the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), then these columns are also linearly independent in the original matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

Note that the column space of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) corresponds to the row space of the matrix transposed ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png). From this fact, we derive another procedure for finding a basis for the column space of a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png): we can use the find-a-basis-for-the-row-space procedure on ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png).

####[Basis for the null space](./Front matter.md)

The null space ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png) of a matrix ![A \in \mathbb{R}^{m \times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) is

![\mathcal{N}(A) = \{ \vec{x}\in \mathbb{R}^n \; | \; A\vec{x} = \vec{0} \: \}.](./images/ec37d753d05917121b4f8961c18db5d830960a0d.png)

The vectors in the null space are orthogonal to the row space of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

The null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is the _solution_ of the equation ![A\vec{x}=\vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png). You should already be familiar with the procedure for finding the solution of systems of equations from[Section 3.1](./Chapter 3_ Computational linear algebra.md). The steps of the procedure are:

1.  Perform row operations to find the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).
2.  Identify the columns that _do not_ contain a leading one. These columns correspond to _free variables_ of the solution. For example, consider a matrix whose reduced row echelon form is
    
    ![\textrm{rref}(A) = 
    \begin{bmatrix} 
    \mathbf{1} & 2 & 0 & 0 \\  
    0 & 0 & \mathbf{1} & -3 \\  
    0 & 0 & 0 & 0
    \end{bmatrix}.](./images/579a9e216acf5de2169f243f75ac0aab0d9c371e.png)
    
    The second column and the fourth column do not contain leading ones (pivots), so these columns correspond to free variables, which are customarily called ![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png), ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png), ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png), etc. We’re looking for a vector with two free variables: ![(x_1,s,x_3,t)^\sfT](./images/43bfdd0daac4ab751c855ef15c78d288183962e5.png).
    
3.  Rewrite the null space problem as a system of equations:
    
    ![\begin{bmatrix}
    1 & 2 & 0 & 0 \\ 
    0 & 0 & 1 & -3 \\
    0 & 0 & 0 & 0
    \end{bmatrix}
    \begin{bmatrix}
    x_1 \\ s \\ x_3 \\ t
    \end{bmatrix}
    =
    \begin{bmatrix}
    0 \\ 0 \\ 0
    \end{bmatrix}
    \qquad
    \Rightarrow
    \qquad
    \begin{array}{rcl}
    1x_1 + 2s			&=&0 \\
    1x_3 - 3t			&=&0 \\
    0				&=&0\,.
    \end{array}](./images/7b6d856a2fb9ff7dd8a02c1bccc6200cf328df82.png)
    
    We can express the unknowns ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_3](./images/db23e43963a7727df3e8966c1e818afe37b229d7.png) in terms of the free variables ![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png) and ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png): ![x_1 = -2s](./images/11f29aff682fae9e8582f7f10335b3848b84df28.png) and ![x_3=3t](./images/d2c5bac2f23949f234e8d10525143bff5f25d880.png). The vectors in the null space are of the form ![(-2s,s,3t,t)^\sfT](./images/e5f81f162d461c6e69fc15aaecbe01069662297c.png), for all ![s,t \in \mathbb{R}](./images/d347dd10db2b5c96e25d8067b0560d00f86f0685.png). We can rewrite this expression by splitting it into an ![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png)\-part and a ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png)\-part:
    
    ![\begin{bmatrix}
    -2s \\ s \\ 3t \\ t
    \end{bmatrix}
    \; = \; 
    \begin{bmatrix}
    -2 \\ 1 \\ 0 \\ 0
    \end{bmatrix}\!\!s
    +
    \begin{bmatrix}
    0 \\ 0 \\ 3 \\ 1
    \end{bmatrix}\!t.](./images/63587059313e382d683b5851c704cca0054131b6.png)
    
4.  The direction vectors associated with each free variable form a basis for the null space of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):
    
    ![\mathcal{N}(A) \; = \; 
    \left\{ \begin{bmatrix}-2s \\ s \\  3t \\ t \end{bmatrix}\!\!, \forall s,t \in \mathbb{R} \right\}
    \; =  \; \textrm{span}\!\left( \begin{bmatrix}-2\\ 1\\0\\0\end{bmatrix}\!\!, 
    \begin{bmatrix}0\\0\\ 3\\1\end{bmatrix} \right).](./images/dc28d75402a3f9045834ea8bca2ead5b1027d42c.png)
    

Verify that the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) multiplied by any vector from its null space produces a zero vector.

###[Examples](./Front matter.md)

Let’s check out some examples that illustrate the procedures for finding bases for ![\mathcal{R}(A)](./images/3dbad2f997035cd04ed87a50d8ef6864087f6e44.png), ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png), and ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png). It’s important you become proficient at these “find a basis” tasks because they often appear on homework assignments and exams.

#####[Example 1](./Front matter.md)

Find a basis for the row space, the column space, and the null space of the matrix:

![A = 	\left[\begin{array}{ccc}
4 & -4 & 0\\
1 & 1 & -2\\
2 & -6 & 4
\end{array}\right]\!.](../Images/93e5795831caedd837011b4abdff04956862b6e6.png)

The first steps toward finding the row space, column space, and the null space of a matrix all require calculating the RREF of the matrix, so this is what we’ll do first.

1.  Let’s focus on the first column. To create a pivot in the top left corner, we divide the first row by ![4](./images/d642a42f2cf4e1514233d611b91e5d4646202fc8.png), denoted ![R_1 \gets \frac{1}{4}R_1](./images/2aac60391610aecd3027a38ae8f93f4d7c45846f.png):
    
    ![\left[\begin{array}{ccc}1 & -1 & 0\\1 & 1 & -2\\2 & -6 & 4\end{array}\right]\!.](../Images/a834c5e5785281d1ff4392299729f29320fe2aeb.png)
    
2.  We use this pivot to clear the numbers on the second and third rows by performing ![R_2 \gets R_2 -R_1](./images/b3860ff15a77a2195e7a12dfd9d74f51f25ca860.png) and ![R_3 \gets R_3 -2R_1](./images/03492030e752367be2da07fdb8aa55a54b018908.png):
    
    ![\left[\begin{array}{ccc}1 & -1 & 0\\0 & 2 & -2\\0 & -4 & 4\end{array}\right]\!.](../Images/04ae4bb27d606036b4cf03e1defd1eede36a85d4.png)
    
3.  We can create a pivot in the second row if we divide it by ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png), denoted ![R_2 \gets \frac{1}{2}R_2](./images/4de0d8e7f1c7bf88bdee7c4a3a49137fbb73bb43.png):
    
    ![\left[\begin{array}{ccc}1 & -1 & 0\\0 & 1 & -1\\0 & -4 & 4\end{array}\right]\!.](../Images/94d907fba79608b6c6d110eeda73ca09cb9ddba6.png)
    
4.  We now clear the entry below the pivot using ![R_3 \gets R_3 +4R_2](./images/5c914f3092dc859587843222a4c66e9acc80cbd4.png):
    
    ![\left[\begin{array}{ccc}1 & -1 & 0\\0 & 1 & -1\\0 & 0 & 0\end{array}\right]\!.](../Images/163806c1596dd38272b2c16eaf3217f149a362c0.png)
    
5.  The final simplification step is to clear the ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png) in the first row using ![R_1 \gets R_1 + R_2](./images/5176ec2cc46c0bba342eb4aa38b167c07dc6518a.png):
    
    ![\left[\begin{array}{ccc}1 & 0 & -1\\0 & 1 & -1\\0 & 0 & 0\end{array}\right]\!.](../Images/07dd82dd6d402cd8221f6c1c216e127f2dcd25de.png)
    

Now that we have the RREF of the matrix, we can answer the questions like professionals.

Before we find bases for the fundamental subspaces of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), let’s first do some basic dimension counting. Observe that the matrix has just two pivots. We say ![\textrm{rank}(A)=2](./images/89954b1d87364f712590135f4c093dd540fa711b.png). This means both the row space and the column spaces are two-dimensional.

Recall the equation ![n = \textrm{rank}( A )+ \textrm{nullity}(A)](./images/71185365d4f022308d360c6f03e544df1ba3c47b.png), which we saw in the previous section. The right space ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) splits into two types of vectors: those in the row space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and those in the null space. Since we know the row space is two-dimensional, we can deduce the dimension of the null space: ![\textrm{nullity}(A) = \textrm{dim}( \mathcal{N}(A) ) = n - \textrm{rank}(A) = 3 - 2 = 1](./images/171efd3f22df42f4045905912c4e9272a218d1c0.png).

Now let’s answer the questions posed in the problem. The row space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) consists of the two nonzero vectors in the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):

![\mathcal{R}(A) = \textrm{span}( (1,0,-1), (0,1,-1) ).](./images/df4f730ed1b510477c0768bb7bd814e29ce2a090.png)

To find the column space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), observe that the first and second columns contain the pivots in the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). If they do, then the first two columns of the original matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a basis for the column space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):

![\mathcal{C}(A)
= \textrm{span}\!\left(
\begin{bmatrix}4 \\ 1 \\ 2 \end{bmatrix}\!,
\begin{bmatrix}-4\\ 1\\ -6 \end{bmatrix}
\right).](./images/3c6d05e7934b3c1f62a542c59bee072415430b1f.png)

Let’s now find an expression for the null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). First, observe that the third column does not contain a pivot. No pivot indicates that the third column corresponds to a free variable; it can take on any value, which we write ![x_3= t, \; t \in \mathbb{R}](./images/48ff8ba473da5a86977b5a5c053e827886e1ac5a.png). We want to give a description of all vectors ![(x_1,x_2,t)^\sfT](./images/754cdf0ad1e527c5844f1803042b33d16e934e9c.png) that satisfy the system of equations:

![\left[\begin{array}{ccc}1 & 0 & -1\\ 0 & 1 & -1\\ 0 & 0 & 0\end{array}\right]
\!\!\!
\left[\begin{array}{c}x_1\\ x_2\\ t \end{array}\right]=
\left[\begin{array}{c}0\\ 0\\ 0 \end{array}\right]
\qquad 
\Rightarrow
\qquad 
\begin{array}{rcl}
1x_1  - 1t			&=&0 \\
1x_2  - 1t			&=&0 \\
0				&=&0 \,.
\end{array}](../Images/25778817f7dd4f899ff55a3a8d68577e5ca4e18d.png)

Solving the system equations for ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), we find ![x_1=t](./images/f53243712c92da46670d72306ff54c7bc9e3bf24.png) and ![x_2=t](./images/f059e9426f2f92fe508bf689c8a420d6841b8af2.png), and thus obtain the following final expression for the null space:

![\mathcal{N}(A)
= \left\{ \begin{bmatrix} t \\ t \\ t \end{bmatrix}\!, \;\;t \in \mathbb{R}\right\}
= \textrm{span}\!\left( \begin{bmatrix}1\\ 1\\ 1\end{bmatrix} \right)\!.](./images/227259f938efca7f58a5043c94380c2cd0a68f78.png)

The null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is one-dimensional and consists of all multiples of the vector ![(1,1,1)^\sfT](./images/5e58cc0f3e505a0f3cc2f45594aa61cfbdbe4f50.png).

#####[Example 2](./Front matter.md)

Find a basis for the row space, column space, and null space of the matrix:

![B = \begin{bmatrix} 1 & 3 & 1 & 4 \\  2 & 7 & 3 & 9 \\  1 & 5 & 3 & 1 \\  1 & 2 & 0 & 8 \end{bmatrix}\!.](./images/e55b8c2cd0476d90ddf61370dd422f9472bbdd29.png)

First, we find the reduced row echelon form of the matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![\quad \; 
\sim  \begin{bmatrix} 1 & 3 & 1 & 4 \\  0 & 1 & 1 & 1 \\  0 & 2 & 2 & -3 \\  0 & -1 & -1 & 4 \end{bmatrix}
\sim  \begin{bmatrix} 1 & 0 & -2 & 1 \\  0 & 1 & 1 & 1 \\  0 & 0 & 0 & -5 \\  0 & 0 & 0 & 5 \end{bmatrix}
\sim  \begin{bmatrix} 1 & 0 & -2 & 0 \\  0 & 1 & 1 & 0 \\  0 & 0 & 0 & 1 \\  0 & 0 & 0 & 0 \end{bmatrix}\!.](./images/6db86d75733dbde5a6ca32c4e9eb94b829235906.png)

As in the previous example, we begin by calculating the dimensions of the subspaces. The rank of this matrix is three, so the column space and the row space will be three-dimensional. Since the right space is ![\mathbb{R}^4](./images/63147fde7ca40efcdbf48e4b0a82e082577ebd3b.png), this leaves one dimension for the null space. Next, let’s find the fundamental subspaces for the matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

The row space of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) consists of the three nonzero vectors in the RREF of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![\mathcal{R}(B) = \textrm{span}(\; (1,0,-2,0), (0,1,1,0), (0,0,0,1) ).](./images/639f34cf9658be649f91106cb27640fd28fb4754.png)

The column space of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is spanned by the first, second and fourth columns of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) since these columns contain the leading ones in the RREF of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![\mathcal{C}(B)
= \textrm{span}\!\left( 
\begin{bmatrix} 1 \\  2 \\  1 \\  1\end{bmatrix}\!,\;\;
\begin{bmatrix} 3 \\  7 \\  5 \\  2\end{bmatrix}\!,\;\;
\begin{bmatrix} 4 \\  9 \\  1 \\  8\end{bmatrix}
\right).](./images/1c86295ce221a922e78a1bfa758f9dd9db23a094.png)

The third column lacks a leading one, so it corresponds to a free variable ![x_3= t,\;t \in \mathbb{R}](./images/48ff8ba473da5a86977b5a5c053e827886e1ac5a.png). The null space of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is the set of vectors ![(x_1,x_2,t,x_4)^\sfT](./images/cc4e6cc810dc499e9956c61892f7a8debe22ebe9.png) such that:

![\begin{bmatrix} 1 & 0 & -2 & 0 \\  0 & 1 & 1 & 0 \\  0 & 0 & 0 & 1 \\  0 & 0 & 0 & 0 \end{bmatrix}
\!\!
\left[\begin{array}{c}x_1\\x_2\\t \\x_4 \end{array}\right]=
\left[\begin{array}{c}0\\0\\0\\0 \end{array}\right]
\qquad 
\Rightarrow
\qquad 
\begin{array}{rcl}
1x_1  - 2t			&=&0 \\
1x_2  + 1t			&=&0 \\
x_4 				&=&0 \\
0				&=&0\,.
\end{array}](../Images/c882fcb48ad84daddc64e002042ba27a121b900c.png)

We find the values of ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png), ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), and ![x_4](./images/9d9899d0d905bf325ca6e7be0e5a74002e282586.png) in terms of ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) and obtain

![\mathcal{N}(B) = \left\{ \begin{bmatrix} 2t \\ -t \\ t \\ 0 \end{bmatrix}\!,
\;\;t \in \mathbb{R}\right\}
= 
\textrm{span}\!\left( \begin{bmatrix}2\\-1\\1\\0 \end{bmatrix} \right)\!.](./images/3e1b55db1c45e5b1cf3f74776c7478316aeae53e.png)

###[Discussion](./Front matter.md)

####[Dimensions](./Front matter.md)

For an ![m \times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrix ![M \in \mathbb{R}^{m \times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png) the row space and the null space consist of vectors with ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) components, while the column space and the left null space consist of vectors with ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) components.

Don’t confuse the number of components of vectors in a vector space with the _dimension_ of the space. Suppose we’re given a matrix ![M \in \mathbb{R}^{5 \times 10}](./images/be6ffa6a6e65a2a336d330a9479703184e19cad8.png) with five rows and 10 columns, and the RREF of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) contains three pivots. We say the _rank_ of the matrix is ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png), which means the row space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is three-dimensional. A basis for the row space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) contains three vectors, each vector having ![10](./images/fd39ea446d2046417cbd0fc131073609dd557e3d.png) components. The null space of the matrix is seven-dimensional ![(10-3=7)](./images/16bb51af8c0d1d3c20b2fc8aacdbe90e9bd9b2a6.png) and consist of vectors with ![10](./images/fd39ea446d2046417cbd0fc131073609dd557e3d.png) components. The column space of the matrix is also three-dimensional (![\dim(\mathcal{R}(M))=\dim(\mathcal{C}(M))](./images/9ac5d86c874db1175b6b05cd9b19cfcb3c215d38.png)). A basis for the column space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) consists of three vectors with five components. The left null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is two-dimensional ![(5-3=2)](./images/afec41eed125333284e14a46da3b57f21a207364.png) and is spanned by vectors with five components.

####[Importance of bases](./Front matter.md)

The procedures for identifying bases are somewhat technical and potentially boring, but they are of great practical importance. To illustrate the importance of a basis, consider a scenario in which you’re given a description of the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png) as the span of _three_ vectors:

![P_{xy}= \textrm{span}( (1,0,0), (0,1,0), (1,1,0) ).](./images/468816e50c94fa20a8bd4d3afa3aa1bfe76cbae4.png)

The above definition of ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png) says that any point ![p \in P_{xy}](./images/7abfee822b4c10d65e0792c4dd4ddc060df8aac7.png) can be written as a linear combination of the form

![p = a (1,0,0) + b(0,1,0) + c(1,1,0),](./images/94faef56d6782855c0aebfe770926f5f84915804.png)

for some coefficients ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png). This representation of ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png) is misleading. It might make us think (erroneously) that ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png) is three-dimensional, since it takes three coefficients to describe points in ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png).

Do we really need linear combinations of three vectors and three coefficients to describe any point in ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png)? No, we don’t. Linear combinations using two vectors are sufficient: ![(1,0,0)](./images/9e1166baa708e742a15d8042b9584b63a07fe1d9.png) and ![(0,1,0)](./images/d05a16c6005e544de2169f2566f4052601793d09.png), for example. The same point ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) described above can be written as:

![p 	= \underbrace{(a+c)}_\alpha (1,0,0) +  \underbrace{(b+c)}_\beta (0,1,0) 
= \alpha (1,0,0) + \beta (0,1,0).](./images/dc7419c47c1e2f556383423c249fe953a10aa891.png)

Note the point is described in terms of _two_ coefficients ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png). The vector ![(1,1,0)](./images/e9cd34c7b10472f82c53946d3ce3711f360498c9.png) is not _necessary_ for the description of points in ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png). The vector ![(1,1,0)](./images/e9cd34c7b10472f82c53946d3ce3711f360498c9.png) is redundant because it can be expressed in terms of the vectors ![(1,0,0)](./images/9e1166baa708e742a15d8042b9584b63a07fe1d9.png) and ![(0,1,0)](./images/d05a16c6005e544de2169f2566f4052601793d09.png). By getting rid of the redundant vector, we obtain a description of ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png) in terms of a basis:

![P_{xy}= \textrm{span}( (1,0,0), (0,1,0) ).](./images/a67b6655d68dda6480048541f095fe10001e29da.png)

Recall that a basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) for a space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) must be made of linearly independent vectors and must span the space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). The set ![\{ (1,0,0), (0,1,0) \}](./images/b6e35dad965ba8a5c7bcb7b153183ddc74f9ca47.png) is sufficient to represent any point in ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png), and the vectors in this set are linearly independent. We can correctly conclude that the space ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png) is two-dimensional. If someone asks you, “How do you know that ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png) is two-dimensional?” you can say, “Because its basis contains two vectors.”

###[Exercises](./Front matter.md)

E4.16 Find the null spaces ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png) and ![\mathcal{N}(B)](./images/24b4421f069998d607daef0fcba399de254cf639.png) of the following matrices:

![A = 
\begin{bmatrix}
1 & 0 & -1 & 0  \\
4 & 0 &  0 & -2 \\
0 & 2 & -2  & -1 
\end{bmatrix}
\quad
\textrm{and}
\quad
B = 
\begin{bmatrix}
1 & -1 & -2\\
-2 & 2 & 4\\
3 & -3 & -6 
\end{bmatrix}\!.](./images/ac4ee6e6f44364e8f29a7efda2671089d42ee097.png)

E4.17 Consider the matrix

![A=
\begin{bmatrix}
1 & 3 & 3 & 3 \\
2 & 6 & 7 & 6 \\
3 & 9 & 9 & 10
\end{bmatrix}\!.](./images/5f4458c2abd91dfdd873806b506535a487b79683.png)

Find the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), and bases for ![\mathcal{R}(A)](./images/3dbad2f997035cd04ed87a50d8ef6864087f6e44.png), ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png), and ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png).

##[4.6 Geometric problems](./Chapter 4_ Geometric aspects of linear algebra.md)

So far, we’ve defined all the important linear algebra concepts like vectors and matrices, and we’ve learned some useful computational techniques like the Gauss–Jordan elimination procedure. It’s now time to apply what you’ve learned to solve geometric problems.

Points, lines, and planes can be difficult to understand and conceptualize. But now that you’re armed with the tools of vectors, projections, and geometric intuition, you can solve all kinds of complicated geometric analysis problems—such as those waiting for you at the end of this paragraph. Remember to always sketch a diagram before you begin to write equations. Diagrams are great for visualizing and determining the steps you’ll need to solve each problem.

P4.1 Find the intersections of the these pairs of lines: **a)** ![\ell_1](./images/85ab1f44c88e495336ffa93afcb0641bb2ea908f.png): ![2x+y=4](./images/f61b2b92ca3440f1c7be9caf6b73b28a9c69b2cd.png) and ![\ell_2](./images/9ea9f5f1869d0e3d59478a6ad474b18224d59728.png): ![3x-2y=-1](./images/f84b7f9e3c8190d02e60d8c0a73576b5f92dd716.png), **b)** ![\ell_1](./images/85ab1f44c88e495336ffa93afcb0641bb2ea908f.png): ![y+x=2](./images/4959b2d82092aa30797bcd87a67a19ef9f636241.png) and ![\ell_2](./images/9ea9f5f1869d0e3d59478a6ad474b18224d59728.png): ![2x+2y=4](./images/59a61109f97eb6e2e20fadcaba24cbdb5c10df79.png), **c)** ![\ell_1](./images/85ab1f44c88e495336ffa93afcb0641bb2ea908f.png): ![y+x=2](./images/4959b2d82092aa30797bcd87a67a19ef9f636241.png) and ![\ell_2](./images/9ea9f5f1869d0e3d59478a6ad474b18224d59728.png): ![y-x=0](./images/24650659095648c6ff632c3309fc2355daded6bd.png).

P4.2 Find the lines of intersection between these pairs of planes: **a)** ![P_1](./images/f6424c2dbb8ebbfc0f54924e133c2f298c6160ea.png): ![3x-2y-z=2](./images/35343f17d08fc0a9568791519906a95958111bec.png) and ![P_2](./images/1401190f07de22e9b4824da0d5aefa528aa65a6d.png): ![x+2y+z=0](./images/c6365cd390eefaf998b8e32b2bc918da12e6753e.png), **b)** ![P_3](./images/604c032b1faef3581a34b9057e1029ac902f01c3.png): ![2x+y-z=0](./images/eae560a2a53dda132d3104048e163848fc43891d.png) and ![P_4](./images/71c53973d2582f328ade50cc32f0442bb9424e64.png): ![x+2y+z=3](./images/5ebe0113b2e6dd6ad2c3e5d65d076853f4e1ce84.png).

P4.3 Find whether the planes are parallel, perpendicular, or neither: **a)** ![P_1](./images/f6424c2dbb8ebbfc0f54924e133c2f298c6160ea.png): ![x-y-z=0](./images/7e7563207a4f3bb418e9148ce572e66a13303a51.png) and ![P_2](./images/1401190f07de22e9b4824da0d5aefa528aa65a6d.png): ![2x-2y-2z=4](./images/4504ad7d29989e46a9d3471b62856fe8d6bd201f.png), **b)** ![P_3](./images/604c032b1faef3581a34b9057e1029ac902f01c3.png): ![3x+2y=1](./images/068da81a2c6ee0f7879b592ae5ebf8e3639f9c54.png) and ![P_4](./images/71c53973d2582f328ade50cc32f0442bb9424e64.png): ![y-z=0](./images/d6dc5ee14e8e05248850fb2c7cb173e330730e70.png), **c)** ![P_5](./images/6a2b44eecbc13da006932900b1f3949e38ec45f8.png): ![x-2y+z=5](./images/4aa25df110422b94b39a800bbbe1a566c9c27115.png) and ![P_6](./images/3cfee06545643a47edc4d1eebe8fcf2a3e83ea87.png): ![x+y+z=3](./images/f17a4645dae10bda826de57d15450b22a5a52ba2.png).

P4.4 Find the distance from the point ![r=(2,3,5)](./images/25da06ad6bec728c4d51b2436fb0e05da52c49db.png) to the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) defined by the equation ![2x+y-2z=0](./images/f48889206e3a6fc2a96b61d6a0c58e922f8f5bc0.png).

P4.5 Find the closest distance between ![p=(5,3,5)](./images/42b31f714d025dee20531db905c097f0f36a9a9e.png) and ![Q: 2x+y-2z=1](./images/78b53319fb2516b80f4875a70dde22ce95848462.png).

Consider an arbitrary point in the plane ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png), such as ![q = (0,1,0)](./images/78a161bbecca56a47d2de074e0163b09d970eed9.png).

P4.6 Find the distance between the points **a)**  ![p=(4,7,3)](./images/8ba85684611a9f9d30002e527f59956444a8cd7e.png) and ![q=(1,1,1)](./images/b5374d56a3e9357ff01773ba746df99afd437e83.png), **b)**  ![m=(4,-2,0)](./images/ffb44c9c68570a94b7c2d7fc66924581bc4ed124.png) and ![n=(0,1,0)](./images/ae8269a7da091787a32d338cf1c1c3dad55f992d.png), **c)**  ![r=(1,0,1)](./images/c9b611c5050d79dd4d8fa1b379cb3e2cf4b201c9.png) and ![s=(-1,1,-1)](./images/d9bcf9ae947d34b9f76afc25cce1ed3bc1b3533a.png), **d)**  ![i=(2,1,2)](./images/8520cc2fd09c0ac8779f09535b78f757330413e9.png) and ![j=(1,-2,-1)](./images/997faae2196dca4643fec26dce8ce89ce60460fe.png).

P4.7 Find the general equation of the plane that passes through the points ![q=(1,3,0)](./images/f323b2ad2d03c463efdb1be8174a0cb5a8e4af2e.png), ![r=(0,2,1)](./images/435e15a65dd8a0c25f5b7c5e329e7767ee709b9c.png), and ![s=(1,1,1)](./images/ca9b26e3f88809ec17582d435c63a7ce262f7cd2.png).

P4.8 Find the symmetric equation of the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) described by the equations

![x=2t-3, 
\quad
y=-4t+1,
\quad
z= -t.](./images/d2abd4470fe6f6a72bd099ed2fb7b24eb76cdeda.png)

P4.9 Define the line ![\ell_1](./images/2700171b346ab6b4bda6d406dd791123fee92c26.png) to be the intersection of the planes ![x+2y+z=1](./images/985fa6f3d9c357fe0b07859b692ff878faf4018f.png) and ![2x-y-z=2](./images/4a46adb842e9adb86e9ccab4955c98b1a6674522.png). Define ![\ell_2](./images/d044fe34b7d41f4916ccf967c6bb2bc7e088c762.png) to be the line with parametric equation ![x=1+2t](./images/2738078a5bb6e052454651ff555ef29ec0457b38.png), ![y=-2+t](./images/9cffed24fbc0429cbecf20b51e4426745a25a3ac.png), ![z=-1-t](./images/5f7ebbfbf48f83937374d5f28dcf16472f4a89dc.png). Find the equation of the plane that contains the line ![\ell_1](./images/2700171b346ab6b4bda6d406dd791123fee92c26.png) and is parallel to the line ![\ell_2](./images/d044fe34b7d41f4916ccf967c6bb2bc7e088c762.png). See[Figure 4.12](./Front matter.md).

![plane_lines_3D-0](./images/plane_lines_3D-0.png)

Figure 4.12

P4.10 Given two vectors ![\vec{u}=(2,1,-1)](./images/180bfdeddeb935020e794d257d9aa83b9592b523.png) and ![\vec{v}=(1,1,1)](./images/a5326bea9dd8057b416ed081787731d358f3e51f.png), find the projection of ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) onto ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png), and the projection of ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png) onto ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png).

P4.11 Find a projection of ![\vec{v}=(3,4,1)](./images/d3e18da5fdaf6ad250c4a6f44027c5524b2a1c80.png) onto the plane ![P: 2x-y+4z=0](./images/06c9e473bf28915326861635ad40ca44cb2402fc.png).

P4.12 Find the component of the vector ![\vec{u}=(-2,1,1)](./images/d7ac73dbc8c385f6b1400b0f9296d6f0ad53f200.png) that is perpendicular to the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png), and that contains the points ![m=(2,4,1)](./images/5f14241b074f35634e70e59275de77c4a313ef90.png), ![s=(6,4,-2)](./images/fe995c2faaf4daf9c213e20b1e3d5046bd814adc.png), and ![r=(6,5,-2)](./images/8395a30c514ebac378149638a168db63c8c54ad1.png).

P4.13 Find the distance between the line ![\ell: \{x=1+2t, y=-3+t, z=2\}](./images/cbd8d70af6694fcf98c32d8697164c7918188647.png) and the plane ![P: -x+2y+2z=4](./images/c685207f1fb391720a28ec8edd480e74b37d573d.png).

P4.14 Find the coordinates of the vector ![\vec{v} = 9\hat{\imath} + 5\hat{\jmath} + 4\hat{k} = (9,5,4)_{B_s}](./images/e0f307000579e1ade0ebf065952c76d95f7a0829.png) with respect to the basis ![W = \{ \vec{w}_1, \vec{w}_2, \vec{w}_3 \}](./images/fa6e7a9c10292d2bd9c7d2ea78ad6020b491db23.png), which consists of the vectors ![\vec{w}_1 = (0,0,2)_{B_s}](./images/e7b683995d32a2236ec574c41688bc44a1b846fe.png), ![\vec{w}_2 = (0,5,0)_{B_s}](./images/33c6c39fc4f94b630ac1a30c66b768a53a1dfada.png), and ![\vec{w}_3 = (3,0,0)_{B_s}](./images/9bee4c27c505bddbdc6eae5abbc5ae0dd2c88ec2.png).

P4.15 Find the change-of-basis matrix ![\tensor[_{V}]{\left[\mathbbm{1}\right]}{_{U}}](../Images/0167271e0ceefd6d3f846eeffbe5c2caf23b8c2a.png) that transforms vectors expressed in the basis ![U = \{\vec{u}_1=(1,0,0), \vec{u}_2=(0,1,1), \vec{u}_3=(0,1,-1) \}](./images/86159c5ed8c61eca69261c3448bb2830a87591f2.png) to vectors in the basis ![V = \{ \vec{v}_1=(1,1,1), \vec{v}_2=(1,1,0), \vec{v}_3=(1,0,1) \}](./images/425a42eb45c6cb18126dbd2d6b3015d72e5d40a2.png).

Start by computing the change-of-basis matrices to the standard basis: ![\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{U}}](../Images/86ee681b22fd6b9c5b09013fc4d8b37a1160597c.png) and ![\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{V}}](../Images/e0b11f74317587fc4a3b237cb3672a91d032f14e.png). Then combine the matrices to obtain ![\tensor[_{V}]{\left[\mathbbm{1}\right]}{_{U}}](../Images/0167271e0ceefd6d3f846eeffbe5c2caf23b8c2a.png).

P4.16 An ![m\times n](./images/db64f3a4b45f481733f89912bcb47c0179ce9042.png) matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is upper triangular if all entries lying below the main diagonal are zero; that is, if ![A_{ij} = 0](./images/da19b0e5f4cba6dd69463e07d0877a81351ee716.png) whenever ![i > j](./images/c2fe2b7516ddfa7c04aedc89002a81e3f1cebc99.png). Prove that upper triangular matrices form a subspace of ![\mathbb{R}^{m\times n}](./images/ccd6e1a2a81105d50b3e7cf78aa5cd58f0869ae9.png).

Is the set closed under addition and scaling? Does it contains zero?

P4.17 Consider the vector space of three-dimensional vectors ![V = \mathbb{R}^3](./images/2829a58a3d6df0c50c4408bfb7a31bd31f447699.png). Which of the following sets are subspaces of ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png)?

1.  ![W_1 = \{ (v_x,v_y,v_z) \in V \; | \; v_x + v_y = 0 \; \}](./images/4064114348dfe70385aab10ae84e409ee128b2d7.png)
2.  ![W_2 = \{ (v_x,v_y,v_z) \in V \; | \; v_yv_z = 0 \; \}](./images/e1b5cc4cbdcd272549211414b7ee3714aaa33225.png)
3.  ![W_3 = \{ (v_x,v_y,v_z) \in V \; | \; v_x = v_y = v_z \; \}](./images/4950beee286113aa7cc64ed36f2d94f755f493ff.png)
4.  ![W_4 = \{ (v_x,v_y,v_z) \in V \; | \; v_x \geq 0 \; \}](./images/66d02f0975ab16ba5603c31d0176cf8b089f031a.png)
5.  ![W_5 = \{ (v_x,v_y,v_z) \in V \; | \; v_x + v_z = 3 \; \}](./images/a3bc07649fb3c90a9bd737800e7c57d217d2a8b1.png)

To form a subspace, a set must be closed under addition, closed under scalar multiplication, and contain the zero element.

P4.18 Find ![2\times 3](./images/644e34b738a35afc43e409a532e5b2a7981c54f5.png) matrices ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png), ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png), and ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) that satisfy the conditions.

1.   ![\mathcal{R}(A) = \textrm{span}( (1,2,3) )](./images/5d277e27ef0ee02151ce3d4872692dbab4616f4b.png) and ![\mathcal{C}(A) = \textrm{span}( (1,2)^\sfT )](./images/e6c12ba6ae8c917e06d94ef8411bc89a4c7c4a78.png) 
2.  ![\mathcal{N}(B) = \textrm{span}( (1,1,1)^\sfT )](./images/8a9cfff6fe90f69db7072249a3c899d21952d672.png)
3.  ![\mathcal{N}(C^\sfT) = \textrm{span}( (1,3) )](./images/f9be578353aa46495c96d467e6ec841b5b061d63.png)

P4.19 Consider the matrix ![A = \begin{bmatrix}a & b \\ c & d \end{bmatrix}](./images/c7aa3b5024c8452b2e0b3ad7c63dc71d5146961b.png) where ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png), ![b](./images/ae769ce22c6289af843e3e66bd3145003e72ccf6.png), and ![c](./images/0da715a1d62623ace880d9c3dde79450f829f124.png) are fixed constants and ![a \neq 0](./images/96f2b70d98bfbbb7dee1f0bd4e5cce83178276ae.png). Find the value of ![d](./images/dd565b0bdaf16b09052be14b28af85a1bdefb913.png) so that ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) will have rank one.

In this chapter we studied geometric objects like points, lines, and planes, and we derived various distance and projection formulas. We also introduced the notion of a vector and studied the vector spaces associated with matrices. With so much new material, it’s easy to miss the important new definitions found throughout this chapter. Here’s a little reminder:

-   The _span_ of a set of vectors is the vector space that can be constructed from linear combinations of the vectors:
    
    ![\textrm{span}\!\left( \vec{v}_1, \ldots, \vec{v}_n \right)
    \; = \;
    \{  
    \alpha_1\vec{v}_1 + \cdots + \alpha_n\vec{v}_n,\;  
    \forall \alpha_i \in \mathbb{R} 
    \}.
    \vspace{-2mm}](./images/12993461895547d21df2a5d4568469e029ab6234.png)
    
-   A set of ![n](./images/e4b68e8c3ac79ddb60832042f0e1d46dc15ad35e.png) vectors ![\{\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n \}](./images/41163bc6ab2d5ba2cbd23bce0a52c41adba98ef8.png) is _linearly independent_ if the equation ![\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \cdots + \alpha_n\vec{v}_n \; = \; \vec{0}](./images/2e97ac9fb7f424bd1c46c04f2b52743ca0c0db59.png) has only trivial solution ![\alpha_i=0](./images/1e6ce04920baae50ffe7cf1c91bb6c5dcb983801.png).
-   A _basis_ for a ![d](./images/408497c6508ab8b74a9cdef4c341262b816d98cc.png)\-dimensional vector space consists of any set of ![d](./images/408497c6508ab8b74a9cdef4c341262b816d98cc.png) linearly independent vectors.

The problems below will ensure that you’ve internalized these important concepts, and that you feel comfortable using the above definitions in proofs.

P4.20 Describe geometrically the subspaces of ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png) spanned by the following sets of vectors.

1.   ![\{(1,0,0), (2,0,0) \}](./images/01a811a7a381aa9d414112d73a83460f2ae6f246.png)
2.   ![\{(1,0,0), (0,1,0) \}](./images/0a4c89086743658aa9e136f8dca9e1a707f9cb41.png)
3.   ![\{(1,0,0), (0,1,0), (1,1,0) \}](./images/daad983f81bc34d1a063980abd687a6c9598a7fb.png)
4.  ![\{(1,0,0), (0,1,0), (1,1,1) \}](./images/58a8bfa1f3b22c0247133bcebf38b345300d3846.png)
5.  ![\{(0,1,1), (0,1,2), (0,1,3) \}](./images/1ff57e1b0d4efc435f478f7a4464eb7c489f0da7.png)

P4.21 Suppose the set of vectors ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/09e5ed76d3621c6d585d8c4b3b884ae4c93434fc.png) spans the vector space ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png). Prove that ![\{\vec{v}_1, \vec{v}_2-\vec{v}_1, \vec{v}_3-\vec{v}_2, \vec{v}_4-\vec{v}_3\}](./images/98fff543039ecf6fbcba59397a9a2399fc321a82.png) also spans ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png).

P4.22 A given set of ![m](./images/89bd9dbe770020ab4a4b963d537e5e619b5ee2ef.png) vectors is known to span the vector space ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png). Can you conclude that ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png) is ![m](./images/89bd9dbe770020ab4a4b963d537e5e619b5ee2ef.png)\-dimensional? Explain why or why not.

P4.23 Consider the vector space ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png) and the vectors ![\vec{w}_1 \in V](./images/7d51090ba7cd5e36ee7da6261cbf2e55fd00415b.png) and ![\vec{w}_2 \in V](./images/77ed2dca362af48de21df07491fc57e97ffd3b17.png). Prove that ![\textrm{span}(\vec{w}_1, \vec{w}_2 )](./images/c3300427635cce987076a984222a5ec52426c682.png) is a subspace of ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png).

P4.24 Suppose the set of vectors ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/09e5ed76d3621c6d585d8c4b3b884ae4c93434fc.png) is linearly independent. Prove that ![\{\vec{v}_1, \vec{v}_2-\vec{v}_1, \vec{v}_3-\vec{v}_2, \vec{v}_4-\vec{v}_3\}](./images/98fff543039ecf6fbcba59397a9a2399fc321a82.png) is also a linearly independent set.

P4.25 Suppose the set ![\{ \vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/09e5ed76d3621c6d585d8c4b3b884ae4c93434fc.png) forms a linearly independent set. Show that ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3\}](./images/3ab621063eeab3da100e803cd5b1524a970e87eb.png) is also a linearly independent set.

Use a proof by contradiction.

P4.26 Suppose ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3\}](./images/3ab621063eeab3da100e803cd5b1524a970e87eb.png) is a linearly independent set, and the vector ![\vec{v}_4 \notin \textrm{span}(\vec{v}_1, \vec{v}_2, \vec{v}_3)](./images/2e95a35edc4751501f35495b9f6859c67035a4d9.png). Show that ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/09e5ed76d3621c6d585d8c4b3b884ae4c93434fc.png) is linearly independent.

Use a proof by contradiction.

P4.27 Suppose that ![\{\vec{v}_1,\vec{v}_2,\vec{v}_3\}](./images/3ab621063eeab3da100e803cd5b1524a970e87eb.png) is a linearly independent set. Define the vectors ![\vec{w}_1 =\vec{v}_3](./images/64ed5009412b0996c4d6be25cddca1144183286b.png), ![\vec{w}_2 =\vec{v}_2 +\vec{v}_3](./images/50ced148d039b86c65859b7ed682d95ce7cab4f5.png), and ![\vec{w}_3 =\vec{v}_1 +\vec{v}_2 +\vec{v}_3](./images/1a7bf51820a05ddcffc7512000130160a0198767.png). Prove ![\{\vec{w}_1,\vec{w}_2,\vec{w}_3\}](./images/66c7339f0174187591abb4223a01cc462e73500e.png) is a linearly independent set.

P4.28 Let ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png) and ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) be distinct vectors from the vector space ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png), and assume that ![\{\vec{u}, \vec{v}\}](./images/330eafccc48633cc20ba2911e630ca55de8a71df.png) is a basis for ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png). Show that ![\{\vec{u}+\vec{v}, a\vec{u}\}](./images/151a37f62f9c24c6ecdd82ff27ab415932ffce49.png) and ![\{a\vec{u}, b\vec{v}\}](./images/f06a3fbabd6dafe4de22fb3e300c3fbdf86a9e7d.png) are also bases for ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png), for any choice of nonzero constants ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png) and ![b](./images/ae769ce22c6289af843e3e66bd3145003e72ccf6.png).

P4.29 Consider the vectors ![\vec{v}_1 = (1,2,3)](./images/96f6ac1bf79cc55e668ab6a28768f72003a4e764.png) and ![\vec{v}_2 = (1,2,4)](./images/05e0313b02bb494cb8d00f83c01d7cbdf0395e81.png). Find a vector ![\vec{v}_3](./images/6fb023e89213b68ba9ff281a50c3bf2d42b8e701.png) such that ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3\}](./images/3ab621063eeab3da100e803cd5b1524a970e87eb.png) is a basis for ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png). Also, find another vector ![\vec{v}_4](./images/497b24787340775ee919702626cee362c519cef7.png) such that ![\{\vec{v}_1,\vec{v}_2,\vec{v}_4\}](./images/664860e09a5d18e6d8addf624f5d1fe3470edcb5.png) is not a basis for ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png).

P4.30 Find a vector that is perpendicular to the vectors ![\vec{v}_1 = (1,2,3,0)](./images/9bfa6a43d294d6c49ede4d7d789efc65f8c03b2f.png), ![\vec{v}_2 = (0,1,1,1)](./images/263b5ea4ddca4bb584d6fc66956a7c7b0276a185.png), and ![\vec{v}_3 = (1,0,2,1)](./images/d7f86caf322aced2738fbbd371e770ae38df736a.png).

[1.](./Front matter.md) Our convention is to assume vectors are column vectors by default. The transpose operation is required to obtain row vectors.
