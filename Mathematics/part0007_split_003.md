Chapter 7    

##[7.3 Basis](part0007_split_003.md)

One of the most important concepts in the study of vectors is the concept of a _basis_. Consider the three-dimensional vector space ![\mathbb{R}^3](01691.jpeg). A _basis_ for ![\mathbb{R}^3](01691.jpeg) is a set of vectors ![\{ \hat{e}_1, \hat{e}_2, \hat{e}_3 \}](01683.jpeg) that can be used as a coordinate system for ![\mathbb{R}^3](01691.jpeg). If the set of vectors ![\{ \hat{e}_1, \hat{e}_2, \hat{e}_3 \}](01683.jpeg) is a basis, then you can _represent_ any vector ![\vec{v} \in \mathbb{R}^3](01692.jpeg) as coordinates ![(v_1,v_2,v_3)](01682.jpeg) _with respect to_ that basis:

![\vec{v} =  v_1\hat{e}_1 + v_2\hat{e}_2 + v_3\hat{e}_3.](01693.jpeg)

The vector ![\vec{v}](01520.jpeg) is obtained by measuring out a distance ![v_1](01685.jpeg) in the ![\hat{e}_1](01686.jpeg) direction, a distance ![v_2](01687.jpeg) in the ![\hat{e}_2](01688.jpeg) direction, and a distance ![v_3](01689.jpeg) in the ![\hat{e}_3](01690.jpeg) direction.

You are already familiar with the _standard_ basis ![\{ \hat{\imath}, \hat{\jmath}, \hat{k} \}](01681.jpeg), which is associated with the ![xyz](01677.jpeg)\-coordinate system. You know that any vector ![\vec{v} \in \mathbb{R}^3](01692.jpeg) can be expressed as a triple ![(v_x,v_y,v_z)](01676.jpeg) with respect to the basis ![\{ \hat{\imath}, \hat{\jmath}, \hat{k} \}](01681.jpeg) through the formula ![\vec{v}=v_x\hat{\imath}+v_y\hat{\jmath}+v_z\hat{k}](01674.jpeg). The whole point of this section is to let you know that other bases (coordinate systems) exist, and to get you into the habit of asking, “With respect to which coordinate system?” every time you see a coordinate vector ![(a,b,c)](01694.jpeg).

###[An analogy](part0007_split_003.md)

Let’s start with a simple example of a basis. If you look at the HTML source code behind any web page, you’re sure to find at least one mention of the colour stylesheet directive such as `color:#336699;`. The numbers should be interpreted as a triple of values ![(33,66,99)](01695.jpeg), each value describing the amount of red, green, and blue needed to create a given colour. Let us call the colour described by the triple ![(33,66,99)](01695.jpeg) CoolBlue. This convention for colour representation is called the RGB colour model and we can think of it as the _RGB basis_. A basis is a set of elements that can be combined together to express something more complicated. In our case, the **R**, **G**, and **B** elements are pure colours that can create any colour when mixed appropriately. Schematically, we can write this mixing idea as

![{\rm CoolBlue} = (33,66,99)_{RGB}=33{\mathbf R}+66{\mathbf G}+99{\mathbf B},](01696.jpeg)

where the _components_ determine the strength of each colour. To create the colour, we combine its components as symbolized by the ![+](00453.jpeg) operation.

The cyan, magenta, and yellow (CMY) colour model is another basis for representing colours. To express the “cool blue” colour in the CMY basis, you will need the following components:

![(33,66,99)_{RGB} = {\rm CoolBlue}  = (222,189,156)_{CMY} = 222{\mathbf C}+189{\mathbf M}+156{\mathbf Y}.](01697.jpeg)

The _same_ colour CoolBlue is represented by a _different_ set of components when the CMY colour basis is used.

Note that a triple of components by itself doesn’t mean anything unless we know the basis being used. For example, if we were to interpret the triple of components ![(33,66,99)](01695.jpeg) with respect to the CMY basis, we would obtain a completely different colour, which would not be cool at all. A basis is required to convert mathematical objects like the triple ![(a,b,c)](01694.jpeg) into real-world ideas like colours. As exemplified above, to avoid any ambiguity we can use a subscript after the bracket to indicate the basis associated with each triple of components. Writing ![(222,189,156)_{CMY}](01698.jpeg) and ![(33,66,99)_{RGB}](01699.jpeg) clarifies which basis to use for each triple of components.

###[Discussion](part0007_split_003.md)

It would be hard to over-emphasize the importance of the basis—the coordinate system you use to describe vectors. The choice of coordinate system is the bridge between real-world vector quantities and their mathematical representation in terms of components. Every time you start a new problem that involves vector calculations, the first thing you should do is choose the coordinate system you want to use, and indicate it clearly in the diagram.

Using a non-standard coordinate system can sometimes simplify the equations you have to solve. For example, let’s say we want to study the motion of a block sliding down an incline with velocity ![\vec{v}](01520.jpeg), as illustrated in[Figure 7.11](part0007_split_003.md). Using the standard ![xy](01700.jpeg)\-basis, the velocity vector is represented as ![(v\cos\theta,-v\sin\theta)_{xy}](01701.jpeg), which has components in both the ![x](00015.jpeg)\- and ![y](00018.jpeg)\-directions and requires using trigonometric functions. If instead you use the non-standard ![x'y'](01702.jpeg)\-basis, the components of the velocity will be ![(v,0)_{x'y'}](01703.jpeg). Note the velocity only has a component along the ![x'](00698.jpeg)\-direction, which will simplify all subsequent calculations.

![rotated_coordinate_system](01704.gif)

Figure 7.11: The vector ![\vec{v}](01523.jpeg) is described by the coordinates ![(v\cos\theta,-v\sin\theta)_{xy}](01705.jpeg) with respect to the standard basis ![xy](01706.jpeg). The same vector ![\vec{v}](01523.jpeg) is described by the coordinates ![(v,0)_{x'y'}](01707.jpeg) with respect to the “tilted” basis ![x'y'](01708.jpeg).

Recall the polar coordinates representation we used to describe points ![r\angle\theta](01318.jpeg) and vectors ![\|\vec{v}\|\angle\theta](01614.jpeg) in two dimensions (see page 7.2.4). This is another example of an alternative coordinate system that’s useful for describing rotations and circular motion. Note certain textbooks will write the polar coordinates of the vector ![\vec{v}=\|\vec{v}\|\angle\theta](01568.jpeg) using the bracket notation ![(\|\vec{v}\|,\theta)](01709.jpeg), which can easily be confused with the Cartesian coordinates of the vector ![(v_x,v_y)](01519.jpeg). Indicating the coordinate system as a subscript after the bracket can avoid any confusion: ![\vec{v}=(\|\vec{v}\|,\theta)_{r\theta} = (v_x,v_y)_{xy}](01710.jpeg).

###[Links](part0007_split_003.md)

\[ Vectors and vector operations explained by 3Blue1Brown \]

[https://www.youtube.com/watch?v=fNkzzaMoSs](./watch_v=fNk_zzaMoSs.md)

\[ More vector illustrations and definitions from Wikipedia \]

[https://en.wikipedia.org/wiki/Euclideanvector](./Euclidean_vector.md)

###[Exercises](part0007_split_003.md)

E7.1 Given the vectors ![\vec{v}_1=(2,1)](01711.jpeg), ![\vec{v}_2=(2,-1)](01712.jpeg), and ![\vec{v}_3=(3,3)](01713.jpeg), calculate the following expressions:

**a)** ![\vec{v}_1 + \vec{v}_2](01714.jpeg) **b)** ![\vec{v}_2 - 2\vec{v}_1](01715.jpeg) **c)** ![\vec{v}_1 + \vec{v}_2 + \vec{v}_3](01716.jpeg)

E7.2 Express the following vectors as components:

**a)** ![\vec{v}_1 =10\angle30^\circ](01717.jpeg) **b)** ![\vec{v}_2 = 12\angle\!-\!90^\circ](01718.jpeg) **c)** ![\vec{v}_3 = 3\angle170^\circ](01719.jpeg)

E7.3 Express the following vectors in length-and-direction notation:

**a)** ![\vec{u}_1 = (4,0)](01720.jpeg) **b)** ![\vec{u}_2 = (1,1)](01721.jpeg) **c)** ![\vec{u}_3 = (-1,3)](01722.jpeg)
