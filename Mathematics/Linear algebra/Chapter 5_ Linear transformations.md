Chapter 5      

#[Chapter 5 Linear transformations](./Chapter 5_ Linear transformations.md)

Linear transformations are a central idea of linear algebra—they form the cornerstone that connects all the seemingly unrelated concepts we’ve studied so far. We previously introduced linear transformations, informally describing them as “vector functions.” In this chapter, we’ll formally define linear transformations, describe their properties, and discuss their applications.

In[Section 5.2](./Chapter 5_ Linear transformations.md), we’ll learn how matrices can be used to _represent_ linear transformations. We’ll show the matrix representations of important types of linear transformations like projections, reflections, and rotations.[Section 5.3](./Chapter 5_ Linear transformations.md) discusses the relation between bases and matrix representations. We’ll learn how the bases chosen for the input and output spaces determine the entries of matrix representations. A single linear transformation can correspond to many different matrix representations, depending on the choice of bases for the input and output spaces.

[Section 5.4](./Chapter 5_ Linear transformations.md) discusses and characterizes the class of _invertible linear transformations_. This section serves to connect several topics we covered previously: linear transformations, matrix representations, and the fundamental subspaces of matrices.

##[5.1 Linear transformations](./Chapter 5_ Linear transformations.md)

Linear transformations take vectors as inputs and produce vectors as outputs. A transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) that takes ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vectors as inputs and produces ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-dimensional vectors as outputs is denoted ![T \colon \mathbb{R}^n \to \mathbb{R}^m](./images/47bf5e239d64ece2ecfc2fdba17ea92e01d7d91d.png).

The class of linear transformations includes most of the useful transformations of analytical geometry: stretchings, projections, reflections, rotations, and combinations of these. Since linear transformations describe and model many real-world phenomena in physics, chemistry, biology, and computer science, learning the theory behind them is worthwhile.

###[Concepts](./Front matter.md)

Linear transformations are mappings between _vector inputs_ and _vector outputs_. The following concepts describe the input and output spaces:

-   ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png): the input vector space of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png)
-   ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png): the output vector space of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png)
-   ![\dim(U)](./images/39429e204b5a7b77f2a7c92527c8a409cebed629.png): the dimension of the vector space ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png)
-   ![T:V \to W](./images/6f6abcb4c10a6a13779cdad441002ebe2bfb94ea.png): a linear transformation that takes vectors ![\vec{v} \in V](./images/3eefde8f9c5d92cf2322bd0bd81265b055ce130a.png) as inputs and produces vectors ![\vec{w} \in W](./images/39f41ad30bac5c215f204e76604507821089cd00.png) as outputs. The notation ![T(\vec{v}) = \vec{w}](./images/e071b653ade064d85ae1e5439e65f5fa064d43ed.png) describes ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) acting on ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) to produce the output ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png).
    
    ![linear_transformation_T_v1w1_v2w2](./images/linear_transformation_T_v1w1_v2w2.png)
    
    Figure 5.1: An illustration of the linear transformation ![T:V \to W](./images/c04aca1f064043fc34d9c907b2bab7d92e7dea2d.png).
    
-   ![\textrm{Im}(T)](./images/9dfea7d3645748cd98fffed4ab60cd977dd3df63.png): the _image space_ of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is the set of vectors that ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) can output for some input ![\vec{v}\in V](./images/3eefde8f9c5d92cf2322bd0bd81265b055ce130a.png). The mathematical definition of the image space is
    
    ![\textrm{Im}(T)
    \eqdef \{ \vec{w} \in W \; | \; \vec{w}=T(\vec{v}), \textrm{ for some } \vec{v}\in V \} \quad \subseteq  \; \; W.](./images/b198b9b1230b10a6f1110c7a322405d93b8775ed.png)
    
    The image space is the vector equivalent of the _image set_ of a single-variable function ![\textrm{Im}(f) \eqdef \{ y \in \mathbb{R} \, | \, y=f(x), \, \forall x \in \mathbb{R} \}](./images/cf0d93f4182be0618fc220f79503c944b0019a8e.png).
    
-   ![\textrm{Ker}(T)](./images/40f71975e168346fc3b18999947490b8ff1bd29a.png): the _kernel_ of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png); the set of vectors mapped to the zero vector by ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). The mathematical definition of the kernel is
    
    ![\textrm{Ker}(T) \eqdef \{\vec{v}\in V   \; | \;  T(\vec{v}) = \vec{0} \} \quad \subseteq \; \; V.](./images/b68fcc247afc05a6507d82669d766c150fdc3ddd.png)
    
    The kernel of a linear transformation is the vector equivalent of the roots of a function: ![\{ x \in \mathbb{R} \, | \, f(x) =0 \}](./images/17857d2f75b10ecc7ceca7d61fe1d6893af921bd.png).
    
    ![linear_transformation_T_Null_Im](./images/linear_transformation_T_Null_Im.png)
    
    Figure 5.2: Two key properties of a linear transformation ![T:V \to W](./images/c04aca1f064043fc34d9c907b2bab7d92e7dea2d.png); its kernel ![\textrm{Ker}(T) \subseteq V](./images/391aada1006cb01b8e745f214cf0e85bee587eeb.png), and its image space ![\textrm{Im}(T) \subseteq W](./images/90ec800de2ed91216c10385746175fdaca5d6a9f.png).
    

#####[Example](./Front matter.md)

The linear transformation ![T: \mathbb{R}^2 \to \mathbb{R}^3](./images/29b70a18e5bf953bfd1c59c4ac369eee6336d49d.png) is defined by the equation ![T(x,y) = (x, y, x+y)](./images/c307a1d44dab162c2743f5c88a9eef24d9c1d6c0.png). Applying ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) to the input vector ![(1,0)](./images/d8f32e7b923a10bccdaa68e7141d6158e48cdc1f.png) produces the output vector ![(1,0,1+0)=(1,0,1)](./images/aa679b172758779b79d85fc48ba04d13914ba67a.png). Applying ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) to the input vector ![(3,4)](./images/8b361078c31e9c395a74ffc219bee56006c8a7fa.png) produces the output vector ![(3,4,7)](./images/9e04752519c4906d99a6bafea27017bad1e30efa.png).

The kernel of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) contains only the zero vector ![\textrm{Ker}(T) = \{ \vec{0} \}](./images/fc46f15d47b28882b575aa2a4e7a79cbf031d0a0.png). The image space of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is a two-dimensional subspace of the output space ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png), namely ![\textrm{Im}(T)  = \textrm{span}( (1,0,1), (0,1,1) ) \subseteq \mathbb{R}^3](./images/5203e63b13dba79b611f324bbfa2a65f40029836.png).

###[Matrix representations](./Front matter.md)

Given bases for the input and output spaces of a linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png), the transformation’s action on vectors can be represented as a matrix-vector product:

-   ![B_V=\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n\}](./images/8b1288c813edf28f2310386beddc783812647d16.png): a basis for the input vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)
-   ![B_W=\{ \vec{b}_1, \vec{b}_2, \ldots, \vec{b}_m\}](./images/b7cdf8cb02caa442f12d71abcf9b156bdddb06bd.png): a basis for the output vector space ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png)
-   ![M_T \in \mathbb{R}^{m\times n}](./images/941601a4ecd9670b4e8d5963fcb6365be4ae7908.png): a matrix representation of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png):
    
    ![\vec{w} = T(\vec{v})  
    \; \;  \qquad \Leftrightarrow \qquad  \; \; 
    \vec{w} = M_T \vec{v}.](./images/23bf43b7abd85812c5486cd45cf227d699ba2fc4.png)
    
    To be precise, we denote the matrix representation as ![\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}](../Images/21e22525b5b5e7cd7c60f91b419268473d9a2290.png) to show it depends on the input and output bases.
    
-   ![\mathcal{C}(M_T)](./images/e2795335a8030ac14df41f32682aaccbee112470.png): the _column space_ of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png)
-   ![\mathcal{R}(M_T)](./images/11106dfb106281e8e717cf3e92de59f80c6c4c17.png): the _row space_ of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png)
-   ![\mathcal{N}(M_T)](./images/7249396c415b0166710fc189a95067b1b6ef3dc6.png): the _null space_ the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png)

###[Properties of linear transformations](./Front matter.md)

We’ll start with the feature of linear transformations that makes them suitable for modelling a wide range of phenomena in science, engineering, business, and computing.

####[Linearity](./Front matter.md)

The fundamental property of linear transformations is—you guessed it—their _linearity_. If ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png) are two input vectors and ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) are two constants, then

![T(\alpha\vec{v}_1+\beta\vec{v}_2)=
\alpha T(\vec{v}_1)+\beta T(\vec{v}_2) = \alpha \vec{w}_1 + \beta \vec{w}_2,](./images/58fcd93c91fac78213c2edfda63468a80461e450.png)

where ![\vec{w}_1=T(\vec{v}_1)](./images/89b20d06f0dfed9876831218948979cb2428d262.png) and ![\vec{w}_2=T(\vec{v}_2)](./images/f6a2d4b49c76efd8d8c0448e2682dbdddacccd03.png).

![linear_transformation__linearity_mix_1_to_3](./images/linear_transformation__linearity_mix_1_to_3.png)

Figure 5.3: A linear transformation ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) maps the linear combination of inputs ![\frac{1}{4}\vec{v}_1 + \frac{3}{4}\vec{v}_2](./images/051d79b7d1825c8229a6adb659e8bd979066ec49.png) to the linear combination of outputs ![\frac{1}{4}\vec{w}_1 + \frac{3}{4}\vec{w}_2](./images/8df0f4794ace724f8d2ea91180beeda59063276f.png).

Linear transformations map any linear combination of inputs to the same linear combination of outputs. If you know the outputs of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) for the inputs ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png), you can deduce the output ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) for any linear combination of the vectors ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png) by computing the appropriate linear combination of the outputs ![T(\vec{v}_1)](./images/c431214a5950d1a89923ec5c4e7905369166e317.png) and ![T(\vec{v}_2)](./images/7088405399a26336f55b44aa666360ac16efc65d.png). This is perhaps the most important idea in linear algebra: it’s the _linear_ that we refer to when we talk about _linear algebra_. Linear algebra is not about lines, but about mathematical transformations that map linear combinations of inputs to the same linear combinations of outputs.

In this chapter, we’ll study various aspects and properties of linear transformations, the abstract objects that map input vectors to output vectors. The fact that linear transformations map linear combinations of inputs to corresponding linear combinations of outputs will be of central importance in many calculations and proofs. Make a good note and store a mental image of the example shown in[Figure 5.3](./Chapter 5_ Linear transformations.md).

####[Linear transformations as black boxes](./Front matter.md)

Suppose someone gives you a black box that implements the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). While you can’t look inside the box to see how ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) acts, you can _probe_ the transformation by choosing various input vectors and observing what comes out.

Assume the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is of the form ![T \colon \mathbb{R}^n \to \mathbb{R}^m](./images/47bf5e239d64ece2ecfc2fdba17ea92e01d7d91d.png). By probing this transformation with ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors of a basis for the input space and observing the outputs, you can characterize the transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) completely.

To see why this is true, consider a basis ![\{ \vec{e}_1, \vec{e}_2, \ldots , \vec{e}_n \}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png) for the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional input space ![V = \mathbb{R}^n](./images/1fe565cae7d9a3fbff52350ba69bf4bd88750fd1.png). To characterize ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png), input each of the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) basis vectors ![\vec{e}_i](./images/8e3efa1e871aeea4f937dc13aa99a36dbde1386c.png) into the black box and record the ![T(\vec{e}_i)](./images/47c45b0917578dd0d8b50e5fa34c7f1d81682a8a.png) that comes out. Any input vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) can be written as a linear combination of the basis vectors:

![\vec{v} = v_1 \vec{e}_1 + v_2 \vec{e}_2 + \cdots + v_n \vec{e}_n.](./images/d0d4abf4f2d099251da98cf53ceb76ddd4d9e507.png)

Using these observations and the linearity of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png), we can predict the output of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) for this vector:

![T(\vec{v}) = v_1 T(\vec{e}_1) + v_2 T(\vec{e}_2) + \cdots + v_n T(\vec{e}_n).](./images/13e760165a80f149f1fddcd0518abaf9749a56de.png)

This black box model of probing is used in many areas of science and is one of the most important ideas in linear algebra. The transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) could be the description of a chemical process, an electrical circuit, or some phenomenon in biology. As long as we know that ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is (or can be approximated by) a linear transformation, we can describe it completely by probing it with a small number of inputs. This is in contrast to characterizing nonlinear transformations, which correspond to arbitrarily complex input-output relationships and require significantly more probing.

###[Input and output spaces](./Front matter.md)

Consider the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) from ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-vectors to ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-vectors:

![T \colon \mathbb{R}^n \to \mathbb{R}^m.](./images/70a9301dd7083b4fcea2215e2416be3b306f221d.png)

The _input space_ of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) and its _output space_ is ![\mathbb{R}^m](./images/4d4f5acbadc1b9a3febf3642dbe25d99a4704061.png). The output space is also called the _target space_ and it is similar to the notion of the _target set_ for functions. The input space is identical to the _domain_ of the linear transformation, since ![T(\vec{v})](./images/23f53bdb5049e614d60619289bc062cf19ba0c51.png) is defined for all inputs ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png).

The _image space_ ![\textrm{Im}(T)](./images/9dfea7d3645748cd98fffed4ab60cd977dd3df63.png) consists of all possible outputs of the transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). The image space of a linear transformation is a subset of its output space, ![\textrm{Im}(T) \subseteq \mathbb{R}^m](./images/3b3fb175c5fa81733d130be0b75bcf088494164a.png). A linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) whose image space is equal to its output space (![\textrm{Im}(T)=\mathbb{R}^m](./images/3e4d89f23e575648e842fcfce68032eb1081a837.png)) is called _surjective_ or _onto_.

The _kernel_ of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is the subspace of the domain ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) that is mapped to the zero vector by ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png): ![\textrm{Ker}(T) \eqdef \{\vec{v} \in \mathbb{R}^n \; | \; T(\vec{v}) = \vec{0} \}](./images/b8fa2e125fc702ba7d0952f77621474ad04a25bd.png). A linear transformation with an empty kernel ![\textrm{Ker}(T)=\{ \vec{0} \}](./images/fc46f15d47b28882b575aa2a4e7a79cbf031d0a0.png) is called _injective_. Injective transformations map different inputs to different outputs.

If a linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is both injective and surjective, it is called _bijective_. In this case, ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is a _one-to-one correspondence_ between the input vector space and the output vector space.

Note the terminology used to characterize linear transformations (injective, surjective, and bijective) is the same as the terminology used to characterize functions in[Section 1.8](./Chapter 1_ Math fundamentals.md). Indeed, we can use the same terminology since linear transformations are functions. The concepts of image space and kernel are illustrated in[Figure 5.4](./Chapter 5_ Linear transformations.md).

![linear_transformation_Rn_to_Im_subset_of_Rm](./images/linear_transformation_Rn_to_Im_subset_of_Rm.png)       ![linear_transformation_Null_subset_of_Rn](./images/linear_transformation_Null_subset_of_Rn.png)

Figure 5.4: Pictorial representations of the image space ![\textrm{Im}(T)](./images/618de22f89981fea204be3b3fca829f4ee31d3e2.png) and the kernel ![\textrm{Ker}(T)](./images/e8f24f4617cb62d6052153f0823f9018fd3bf85f.png) of a linear transformation ![T:\mathbb{R}^n \to \mathbb{R}^m](./images/a38045c9850f87df1852ab3ee343eb7ea20c415a.png). The image space is the set of all possible outputs of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png). The kernel of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is the set of inputs that ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) maps to the zero vector.

#####[Observation](./Front matter.md)

The dimensions of the input space and the output space of a bijective linear transformation must be the same. Indeed, if ![T:\mathbb{R}^n \to \mathbb{R}^m](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png) is bijective, then it is both injective and surjective. Since ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is surjective, the input space must be at least as large as the output space; ![n \geq m](./images/586ac6354c863cfd2bd013cbd85fffa29d645b3c.png). Since ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is injective, the output space must be larger or equal to the input space; ![m \geq n](./images/9e4b21effb61468ce6e22d954387de04abc9a9d0.png). Combining these observations, we find that if ![T:\mathbb{R}^n \to \mathbb{R}^m](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png) is bijective then ![m=n](./images/1df137326c35c8302d900b83b591cdba68e5804d.png).

#####[Example 2](./Front matter.md)

Consider the linear transformation ![T: \mathbb{R}^3 \to \mathbb{R}^2](./images/bfa9a6201ae9d63dab49af55f5484c585187e83e.png) defined by the equation ![T(x,y,z) = (x, z)](./images/d0a7fb4e4599e862096c6f2e08f98e36998a34f1.png). Find the kernel and the image space of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). Is ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) injective? Is ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) surjective?

The action of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is to delete the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-components of inputs. Any vector that has only a ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-component will be sent to the zero vector. We have ![\textrm{Ker}(T)=\textrm{span}( (0,1,0) )](./images/6e24fa839a4abfe9ef2515065bbd8927555b319b.png). The image space is ![\textrm{Im}(T)=\mathbb{R}^2](./images/282dadfbb1b5420908571dcf29150ea091018a47.png). The transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is not injective. As an explicit example proving ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is not injective, observe that ![T(0,1,0)=T(0,2,0)](./images/7d773f460daa8c0f5fae65857dd63b1f45525f6e.png) but ![(0,1,0)\neq (0,2,0)](./images/bbfb335b4ac75c00844fe7792cb36181a53ca2cc.png). Since ![\textrm{Im}(T)](./images/9dfea7d3645748cd98fffed4ab60cd977dd3df63.png) is equal to the output space ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png), ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is surjective.

###[Linear transformations as matrix multiplications](./Front matter.md)

An important relationship exists between linear transformations and matrices. If you fix a basis for the input vector space and a basis for the output vector space, a linear transformation ![T(\vec{v})=\vec{w}](./images/e071b653ade064d85ae1e5439e65f5fa064d43ed.png) can be represented as matrix multiplication ![M_T\vec{v}=\vec{w}](./images/f95fd21a98c7260034cc7f1da264f2b7e1944b8f.png) for some matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png):

![\vec{w} = T(\vec{v})
\quad \qquad \Leftrightarrow \qquad  \quad
\vec{w} = M_T \vec{v}.](./images/23207bad0f1b6ee2df95ee964cf83be7e6db4cbf.png)

Using this equivalence, we can re-interpret several properties of matrices as properties of linear transformations. The equivalence is useful in the other direction too, since it allows us to use the language of linear transformations to talk about the properties of matrices.

The idea of representing the action of a linear transformation as a matrix multiplication is extremely important since it transforms the abstract, mathematical description of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) into a concrete, computational one: “take the input vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and multiply it from the right by the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png).” Borrowing an idea from the field of software engineering, we can understand the relationship between a linear transformation and its matrix representation as analogous to the relationship between the abstract software specification of a computer program, and the program’s concrete implementation as code that runs on a computer.

#####[Example 3](./Front matter.md)

We’ll now illustrate the “linear transformation ![\Leftrightarrow](./images/4d453510cfb01bcef19996e2421ed9bfabb8333f.png) matrix-product” equivalence with an example. Define ![\Pi_{P_{xy}}](./images/6b4bdef27958a440c4e1349b694171975d195b74.png) to be the _orthogonal projection_ onto the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane ![P_{xy}](./images/fddbff4c3aae481d112f0c042fb10caa0d09acd1.png). In words, the action of this projection is to zero-out the ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-component of input vectors. The matrix that corresponds to this projection is

![T\!\left(
\begin{bmatrix}
v_x \\ v_y \\ v_z
\end{bmatrix} \right)
=
\begin{bmatrix}
v_x \\ v_y \\ 0
\end{bmatrix}
\qquad \Leftrightarrow \qquad
M_{T}\vec{v} = 
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 0 
\end{bmatrix}
\!\!\!
\begin{bmatrix}
v_x \\ v_y \\ v_z
\end{bmatrix}
=
\begin{bmatrix}
v_x \\ v_y \\ 0
\end{bmatrix}\!.](./images/ae05717ac6441bd5a820f4dd566cbbb16b76ea30.png)

####[Finding the matrix](./Front matter.md)

In order to find the matrix representation of any linear transformation ![T \colon \mathbb{R}^n \to \mathbb{R}^m](./images/47bf5e239d64ece2ecfc2fdba17ea92e01d7d91d.png), it is sufficient to probe ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors in the standard basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png):

![\hat{e}_1  =   \begin{bmatrix} 1 \\ 0 \\ \vdots \\ 0 \end{bmatrix} \!,  \; \; \; 
\hat{e}_2  =   \begin{bmatrix} 0 \\ 1 \\ \vdots \\ 0 \end{bmatrix}\!,  \; \; \; 
\; \ldots,  \; \; \; 
\hat{e}_n  = \begin{bmatrix} 0 \\  \vdots \\ 0  \\ 1 \end{bmatrix}\!.](./images/f2e5eb1c021e12cdb0ebc4508a8fabf9a1985397.png)

To obtain ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png), we combine the outputs ![T(\hat{e}_1)](./images/35befe18e88516bc4c9b366cc6323f0da982f42b.png), ![T(\hat{e}_2)](./images/426daef9c8aa6af38b0e9b5b11f040c2451e6d36.png), ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png), ![T(\hat{e}_n)](./images/c7400909d73e943d06476f7f20255d10651a5162.png) as the _columns_ of a matrix:

![M_T = 
\begin{bmatrix} 
\vert & \vert &  & \vert \\ 
T(\hat{e}_1) & T(\hat{e}_2) & \cdots & T(\hat{e}_n) \\
\vert & \vert &  & \vert 
\end{bmatrix}\!.](./images/dd418296f1dfd208e080c7e2eb6cba7fdb2bab04.png)

Observe that the matrix constructed in this way has the correct dimensions: ![m \times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png). We have ![M_T \in \mathbb{R}^{m \times n}](./images/941601a4ecd9670b4e8d5963fcb6365be4ae7908.png) since we used ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) “probe vectors,” and since the outputs of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) are ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-dimensional column vectors. To help visualize the column structure of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png), let’s analyze what happens when we compute the product ![M_T \hat{e}_2](./images/e89d8be932e8bc6a2540eee57228faf97d1537f9.png). The probe vector ![\hat{e}_2 = (0,1,0,\ldots,0)^\sfT](./images/d85d059d13c74d8e565ec32a360aa608b80e71a5.png) “selects” only the second column from ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png); thus we obtain the correct output: ![M_T \hat{e}_2 = T(\hat{e}_2)](./images/22f9f64d30a21120ee39f017b4ede6769f2090a9.png). Similarly, applying ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) to other basis vectors selects the other columns of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png).

Any input vector can be written as a linear combination of the standard basis vectors ![\vec{v} = v_1 \hat{e}_1 + v_2 \hat{e}_2 + \cdots + v_n\hat{e}_n](./images/0b351a2cabbd0150e980339bfb4020beac9234fd.png). Therefore, by linearity, we can compute the output ![T(\vec{v})](./images/23f53bdb5049e614d60619289bc062cf19ba0c51.png) as follows:

![\begin{align*}
T(\vec{v}) &= v_1 T(\hat{e}_1) + v_2 T(\hat{e}_2) + \cdots + v_n T(\hat{e}_n) \\
& = 	v_1\!\begin{bmatrix} \vert \\  T(\hat{e}_1) \\ \vert \end{bmatrix}
+
v_2\!\begin{bmatrix} \vert \\  T(\hat{e}_2) \\ \vert \end{bmatrix}
+ \cdots
+ v_n\!\begin{bmatrix} \vert \\  T(\hat{e}_n) \\ \vert \end{bmatrix} \\
& = 	\begin{bmatrix} 
\vert & \vert &  & \vert \\ 
T(\hat{e}_1) & T(\hat{e}_2) & \cdots & T(\hat{e}_n) \\
\vert & \vert &  & \vert 
\end{bmatrix}
\!\!
\begin{bmatrix} \vert \\  \vec{v} \\ \vert \end{bmatrix} \\
& = M_T [\vec{v}],
\end{align*}](../Images/2c0e48e41680f18b9c88d0af8a8b0861c6baa5e9.png)

where ![[\vec{v}] = (v_1,v_2,\ldots, v_n)^\sfT](../Images/9d9458d13220ecf07f53fc5e51d1ddfb3a743d44.png) is the coordinate vector of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), represented as a column vector.

####[Input and output spaces](./Front matter.md)

We can identify correspondences between the properties of a linear transformation ![T:V \to W](./images/6f6abcb4c10a6a13779cdad441002ebe2bfb94ea.png) and the properties of a ![\dim(W) \times \dim(V)](./images/5807a9ee70dc39ea5d8b8b510b8c62d0901ee368.png) matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) that implements ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png).

The outputs of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) consist of all possible linear combinations of the columns of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png). Thus, the _image space_ of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is equivalent to the _column space_ of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png):

![\textrm{Im}(T) 
= \{ \vec{w} \in W \; | \; \vec{w}=T(\vec{v}), \textrm{ for some } \vec{v}\in V \}
= \mathcal{C}(M_T).](./images/95bb4e733b4e316e76089f07b10cbc14470eaf5f.png)

There is also an equivalence between the kernel of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) and the null space of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png):

![\textrm{Ker}(T) = \{\vec{v}\in V \; | \; T(\vec{v}) = \vec{0} \}
= 
\{\vec{v}\in V \; | \; M_T\vec{v} = \vec{0} \} = \mathcal{N}(M_T).](./images/b3070329cd9167bc101de1b77247c4af67bdf051.png)

The null space of a matrix ![\mathcal{N}(M_T)](./images/7249396c415b0166710fc189a95067b1b6ef3dc6.png) consists of all vectors that are orthogonal to the rows of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png). The vectors in the null space of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) have a zero dot product with each of the rows of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png). This orthogonality can also be phrased in the opposite direction: any vector in the row space ![\mathcal{R}(M_T)](./images/11106dfb106281e8e717cf3e92de59f80c6c4c17.png) is orthogonal to the null space ![\mathcal{N}(M_T)](./images/7249396c415b0166710fc189a95067b1b6ef3dc6.png).

These observations allow us to decompose the domain of the transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) as the _orthogonal sum_ of the row space and the null space of a matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png):

![V \; = \; \mathcal{R}(M_T) \oplus \mathcal{N}(M_T).](./images/b63eba494b3f0507ceec56114e51b8f260ebb816.png)

This split implies the _conservation of dimensions_ formula:

![\dim(V) \; = \;  \dim({\cal R}(M_T)) + \dim({\cal N}(M_T)),](./images/5895612c51d6d230eccbdf3ed165dca990fd60d2.png)

which describes how the sum of the dimensions of the row space and the null space of a matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) is equal to the total dimensions of the input space.

We can summarize everything we know about the input-output relationship of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) as follows:

![T \colon \mathcal{R}(M_T) \to \mathcal{C}(M_T),
\qquad 
T \colon \mathcal{N}(M_T) \to \{ \vec{0} \}.](./images/8614bbe69fedc02a174777673f29842c85ea1193.png)

Input vectors ![\vec{v} \in \mathcal{R}(M_T)](./images/21f5b276f4f1551b975f9275fb376c1464f3c5ac.png) are mapped to output vectors ![\vec{w} \in \mathcal{C}(M_T)](./images/8518bfed3c5bb0a8e6d6cb08649aa21009774ebb.png) in a one-to-one correspondence. Input vectors ![\vec{v} \in \mathcal{N}(M_T)](./images/786817db275deb090a010a319c422a5211b60ecd.png) are mapped to the zero vector ![\vec{0} \in W](./images/7ff53499b79f7fbee8b994debeae702f64ee8789.png).

####[Composition of linear transformations](./Front matter.md)

The consecutive application of two linear transformations ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) and ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) on an input vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) corresponds to the following matrix product:

![S \circ T (\vec{v}) \; = \;  S(T(\vec{v})) \; = \; M_S M_T \vec{v}.](./images/5b3c64071a75fa7b8af999942ce599ee25def3f4.png)

The matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) acts on the vector first, followed by the matrix ![M_S](./images/47f74708f99cb23182fd7597b3f6f09a1b4478d8.png).

For this composition to be well-defined, the dimension of the output space of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) must be the same as the dimension of the input space of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png). This requirement corresponds to the condition that the rows of ![M_S](./images/47f74708f99cb23182fd7597b3f6f09a1b4478d8.png) and the columns of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) must have the same dimension for the product ![M_SM_T](./images/79462f6bcc3ac51bf448af4c8f5cc0a95f86dd99.png) to exist.

####[Importance of the choice of bases](./Front matter.md)

Above, we assumed the standard basis was used both for inputs and outputs of the linear transformation. Thus, we obtained the entries in the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) _with respect to_ the standard basis.

In particular, we assumed that the outputs of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) were given as column vectors in terms of the standard basis for ![W= \mathbb{R}^m](./images/e535c65a75a19da2d37be036080f5c7e280ce8c2.png). If the outputs were given in some other basis ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png), the entries of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) would have been _with respect to_ ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png).

Due to the dependence of matrix entries on the basis used, **a linear transformation does not correspond to a unique matrix**. Indeed, the same linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) will correspond to different matrices when different bases are used. We say the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) corresponds to a matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) for a _given_ choice of input and output bases. We write ![_{B_W}[M_T]_{B_V}](../Images/f77141e8752269c2a401514ac1c4324af8e681b6.png) to show the entries of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) depend on the choice of left and right bases. Recall we can also use the basis-in-a-subscript notation for vectors. For example, writing ![(v_x,v_y,v_z)_{B_s}](./images/e6f7876c7fd65568582d7af3014f701f0832c581.png) shows the components ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png), ![v_y](./images/6f1ce966448346cbc28c3277a48ccbc1483c0f8c.png), and ![v_z](./images/387cd73c8e889d0c77298fe1a209b9151289faae.png) are expressed in terms of the standard basis ![B_s = \{ \hat{\imath}, \hat{\jmath}, \hat{k} \}](./images/a8681773e0cf3f39fd77cb3920a6f11ab9a02936.png).

The choice of basis is an important technical detail: be aware of it, but don’t worry about it too much. Unless otherwise specified, assume the standard basis is used for specifying vectors and matrices. When you see the product ![A\vec{v}](./images/7f9f917ef64cac1364cf488fd6017afa872a4ef3.png), it means ![\!\tensor[_{B_s}]{\left[A\right]}{_{B_s}} [\vec{v}]_{B_s}](../Images/19197accab1e415389f53069c627c7e7c6c04bb6.png). The only time you really need to pay attention to the choice of bases is when performing _change-of-basis_ transformations, which we’ll discuss in[Section 5.3](./Chapter 5_ Linear transformations.md).

###[Invertible transformations](./Front matter.md)

We’ll now revisit the properties of invertible matrices and connect them to the notion of invertible transformations. Think of multiplication by a matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) as “doing” something to vectors, and multiplication by ![M^{-1}](./images/b61498c52b0456b52de77a7c920e458a63edab4f.png) as doing the opposite thing, restoring the original vector:

![M^{-1} M \vec{v} = \vec{v}.](./images/eca4f1261bd8e565d9a45f5329aabc4334acaf7a.png)

For example, the matrix

![M = \begin{bmatrix}2 & 0 \\  0 & 1 \end{bmatrix}\!](./images/43fd5ced24a66273022807fa3f154932824a1f8e.png)

corresponds to a stretching of space by a factor of 2 in the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-direction, while the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-direction remains unchanged. The inverse transformation corresponds to a shrinkage by a factor of 2 in the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-direction:

![M^{-1} = \begin{bmatrix}\frac{1}{2} & 0 \\  0 & 1 \end{bmatrix}\!.](./images/3aca6ad6aff470fadd6ef8a8c2dcfb37855edd0b.png)

In general, it’s hard to see exactly what the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) does, since it performs some arbitrary linear combination of the components of the input vector.

If ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is an invertible matrix, we can start from any output vector ![\vec{w} = M\vec{v}](./images/8b5f4d34f86009dd163ea545be03896d5d9bdff1.png), and go back to find the input ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) that produced the output ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png). We do this by multiplying ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) by the inverse: ![M^{-1}\vec{w} = M^{-1}M\vec{v} =  \vec{v}](./images/9ddbb3b473e26be27e3df6c571b8242b50d21afc.png).

A linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is _invertible_ if there exists an inverse transformation ![T^{-1}](./images/f0f6e7e1f0c6c860b2353e133905204b7892df1d.png) such that ![T^{-1}(T(\vec{v}))=\vec{v}](./images/1e7f68c87a157d7cf34e845faed1ea6fbc91b409.png). By the correspondence ![\vec{w} = T(\vec{v}) \; \Leftrightarrow \; \vec{w} = M_T\vec{v}](./images/2115682b444586bcce0f67d1b620678521c056ad.png), we can identify the class of invertible linear transformations with the class of invertible matrices. A linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is invertible if and only if its matrix representation ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) is an invertible matrix.

###[Affine transformations](./Front matter.md)

An _affine transformation_ is a function ![A:\mathbb{R}^n \to \mathbb{R}^m](./images/184ae2dc515bd8f770617a3b353d484b3f3c1172.png) that is the combination of a linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) followed by a _translation_ by a fixed vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png):

![\vec{y} = A(\vec{x}) = T(\vec{x}) + \vec{b}.](./images/6049f3b87fa90e249b585a63582170914cc6e5e6.png)

By the ![T \Leftrightarrow M_T](./images/3fcd7db1223c291ed0a4eb0e7a55e5d74d2ea8ad.png) equivalence, we can write the formula for an affine transformation as

![\vec{y} = A(\vec{x}) = M_T\vec{x} + \vec{b}.](./images/9fb67831c25fdd04b802646cd20a4da13ca85942.png)

To obtain the output ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png), apply the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) (the matrix-vector product ![M_T\vec{x}](./images/309608e7d18c45858106b3cf427866f89bd0f48b.png)), then add the vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png). This is the vector generalization of a single-variable _affine function_ ![y=f(x)=mx+b](./images/d8cf5080f5e5e6492b2ef723e5c4cb558ec9d537.png).

###[Discussion](./Front matter.md)

####[The most general linear transformation](./Front matter.md)

In this section we learned that a linear transformation _can_ be represented as matrix multiplication. Are there other ways to represent linear transformations? To study this question, let’s analyze the most general form a linear transformation ![T\colon V \to W](./images/91f4a257e50021f88d8b4a0cb235e39dedef0cde.png) can take. We’ll use ![V=\mathbb{R}^3](./images/65d88c05dafbe29a729ed5ca0e86a2fa633124f4.png) and ![W=\mathbb{R}^2](./images/16febe8078b1dbd0afde94cabf913b1603d6b607.png) to keep things simple.

First consider the component ![w_1](./images/ca60648c1d6fcb7ca582e6f1d3f26000537a98a0.png) of the output vector ![\vec{w} = T(\vec{v})](./images/6aa95b3a44d6864e1530428c8e2c4f63bd5023f4.png) when the input vector is ![\vec{v} \in \mathbb{R}^3](./images/7d4d76835dd377bbd6d7248bd9e3aa55aa35fdfa.png). The fact that ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is linear means that ![w_1](./images/ca60648c1d6fcb7ca582e6f1d3f26000537a98a0.png) can be an arbitrary mixture of the input vector components ![v_1,v_2,v_3](./images/e6a02336aca0f4efb9d34a60456fd4c3ae314436.png):

![w_1 		= 	\alpha_1 v_1  	+ \alpha_2 v_2 		+ \alpha_3 v_3.](./images/d6e27cfa8caafbadd864dac2db1990342a8285aa.png)

Similarly, the component ![w_2](./images/d075ab686799f0f52391bb93c47e53a7b43cdc62.png) must be some arbitrary linear combination of the input components ![w_2 = \beta_1 v_1  + \beta_2 v_2 + \beta_3 v_3](./images/8fe7462fedac322833f8673d3beedf0d8fcc6322.png). Thus, the most general linear transformation ![T \colon \mathbb{R}^3 \to \mathbb{R}^2](./images/d0663477a2b91435e875dba618f648e5fb1fd403.png) can be written as

![\begin{align*}
w_1 	&=	\alpha_1 v_1 	+ \alpha_2 v_2  	+ \alpha_3 v_3, \\
w_2 	&=	\beta_1 v_1 	+ \beta_2 v_2   		+ \beta_3 v_3.
\end{align*}](./images/4363c67675e9ccda53663a5953f79172bd3ea314.png)

This is precisely the kind of expression that can be obtained as a matrix product:

![T(\vec{v}) =
\begin{bmatrix}
w_1 \\
w_2 \\
\end{bmatrix}
=
\begin{bmatrix}
\alpha_1 &  \alpha_2 &  \alpha_3 \\
\beta_1  &  \beta_2  &  \beta_3 
\end{bmatrix}
\!\!
\begin{bmatrix}
v_1 \\
v_2 \\
v_3 \\
\end{bmatrix}
= M_T \vec{v}.](./images/d5ffba04946f56d52dbf24d29415b87d494af30d.png)

Indeed, matrix multiplication is defined as rows-times-columns because it allows us to easily describe linear transformations.

###[Links](./Front matter.md)

\[ Examples of linear transformations from Wikibooks \]

[`http://wikibooks.org/wiki/Linear_Algebra/Linear_Transformations`](./Linear_Transformations.md)

\[ Linear transformations and matrices explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=kYB8IZa5AuE`](./watch_v=kYB8IZa5AuE.md)

\[ Three-dimensional transformations explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=rHLEWRxRGiM`](./watch_v=rHLEWRxRGiM.md)

\[ Nonsquare matrices explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=v8VSDg_WQlA`](./watch_v=v8VSDg_WQlA.md)

###[Exercises](./Front matter.md)

E5.1 Determine whether the following transformations are linear.

1.  ![T_1(x,y,z)=(x+2y+3z)](./images/5a9c8d64a521469f84abb6dc1be811021063fb25.png)       
2.  ![T_2(x,y)=(1, x, y)](./images/ee6bcf0b7d11b8ecfb789c3849581084d176ae5b.png)
3.  ![T_3(x,y)=(x+2y, y+x^2)](./images/ee09b2fa4237fa11550accc66dce9518c1b6f854.png)       
4.  ![T_4(x,y,z)=(z, y, x)](./images/62f9dacb54f3dbcec994f0de60dd5cd8eaae67e0.png)

If the transformation is linear, find its matrix representation. If the transformation is nonlinear, show an example where linearity fails.

E5.2 Consider the transformation ![T(x,y,z) = (y+z,x+z,x+y)](./images/39697c6ee1ac31ba8cdc3c3a5e4bc40369af7ffd.png). Find the input space, the output space, the kernel, and the image of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). Is ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) injective, surjective, or bijective?

E5.3 Consider the matrix ![M= \begin{bmatrix} 1 & 0  & 0 \\ 0 & 0 & 1\end{bmatrix}](./images/28e2a80226474d707a5de5a232f4abe1e2010b62.png) and the linear transformations ![T_M](./images/8f887452f4fa8d12625c92f275791e13cea1e14b.png) and ![T_{M^\sfT}](./images/38a86ff8e1ca962f1857d3a9c220ad2e6b1ec68f.png) defined through left and right multiplication by ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png): ![T_M(\vec{v}) = M\vec{v}](./images/2e4e05f1a1a5ab7205c3156fe02f6fd23e4ca1f0.png) and ![T_{M^\sfT}(\vec{u}) = \vec{u}^\sfT M](./images/6df674bccc30c71e6b039a6e74a72f0eef5d4285.png). Find the input, output, kernel, and image spaces of the linear transformations ![T_M](./images/8f887452f4fa8d12625c92f275791e13cea1e14b.png) and ![T_{M^\sfT}](./images/38a86ff8e1ca962f1857d3a9c220ad2e6b1ec68f.png).

E5.4 What linear transformation ![T:\mathbb{R}^2 \to \mathbb{R}^3](./images/29b70a18e5bf953bfd1c59c4ac369eee6336d49d.png) takes the vector ![(1,0)](./images/d8f32e7b923a10bccdaa68e7141d6158e48cdc1f.png) to the vector ![(1,2,3)](./images/219e4b815234428579879f5977795ee492157f2f.png), and the vector ![(0,1)](./images/51dc53e490143c62313d23af4c20f5a4e63d4d20.png) to the vector ![(4,5,6)](./images/a73c516734e769a2ae783b9d9414685145ac2342.png)? Express your answer as a function ![T(x,y) = \, \ldots](./images/2a66592d2dc9f906eba064fede65212f29a42389.png) and as a matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png).

##[5.2 Finding matrix representations](./Chapter 5_ Linear transformations.md)

Every linear transformation ![T:\mathbb{R}^n \to \mathbb{R}^m](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png) can be represented as a matrix ![M_T \in \mathbb{R}^{m \times n}](./images/941601a4ecd9670b4e8d5963fcb6365be4ae7908.png). Suppose you’re given the following description of a linear transformation: “![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is the counterclockwise rotation of all points in the ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-plane by ![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png),” and you want to find the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) that corresponds to this transformation.

Do you know how to find the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png)? This section describes a simple and intuitive probing procedure for finding matrix representations. Don’t worry; no alien technology is involved, and we won’t be probing any humans—only linear transformations! As you read, try to bridge your understanding between the abstract, mathematical specification of a transformation ![T(\vec{v})](./images/23f53bdb5049e614d60619289bc062cf19ba0c51.png) and its concrete implementation as a matrix-vector product ![M_T\vec{v}](./images/0c4c14d8bad3947c9b28cade7f27898d43780eb6.png). We’ll use the probing procedure to study various linear transformations and derive their matrix representations.

Once we find the matrix representation of a given transformation, we can efficiently apply that transformation to many vectors. This is exactly how computers carry out linear transformations. For example, a black-and-white image file can be represented as a long list that contains the coordinates of the image’s black pixels: ![\{ \vec{x}_1, \vec{x}_2, \ldots, \vec{x}_\ell\}](./images/079b258156db293872b7d4c54a8f862190dbe0bd.png). The image is obtained by starting with a white background and drawing a black pixel in each of the locations ![\vec{x}_i](./images/bc3acdc5b7336eb352b49cea75260879bfc271e1.png) on the screen[1](./Front matter.md) To rotate the image, we can process the list of pixels using the matrix-vector product ![\vec{y}_i = M_T\vec{x}_i](./images/1520d53adeb5400192ada44b61555fb9ac9e36ae.png), where ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) is the matrix representation of the desired rotation. The transformed list of pixels ![\{ \vec{y}_1, \vec{y}_2, \ldots, \vec{y}_\ell\}](./images/03e67d9516ee5c621383355c2fb6135b4ec968cf.png) corresponds to a rotated version of the image. This is essentially the effect of using the “rotate tool” in an image editing program—the computer multiplies the image by a rotation matrix.

###[Concepts](./Front matter.md)

The previous section covered linear transformations and their matrix representations:

-   ![T:\mathbb{R}^{n} \to \mathbb{R}^{m}](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png): a linear transformation that takes inputs in ![\mathbb{R}^{n}](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) and produces outputs in ![\mathbb{R}^{m}](./images/4d4f5acbadc1b9a3febf3642dbe25d99a4704061.png)
    
-   ![M_T \in \mathbb{R}^{m\times n}](./images/941601a4ecd9670b4e8d5963fcb6365be4ae7908.png): the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png)

The action of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is equivalent to multiplication by the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png):

![\vec{w} = T(\vec{v})  \qquad \Leftrightarrow \qquad \vec{w} = M_T \vec{v}.](./images/0d15c3a3cd0a0ffa6a9045800eb7ef469301c1f3.png)

###[Theory](./Front matter.md)

To find the matrix representation of the transformation ![T \colon \mathbb{R}^n \to \mathbb{R}^m](./images/47bf5e239d64ece2ecfc2fdba17ea92e01d7d91d.png), it is sufficient to probe ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors of the standard basis for the input space ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png):

![\hat{e}_1  =   \begin{bmatrix} 1 \\ 0 \\ \vdots \\ 0 \end{bmatrix} \!,  \; \; \; 
\hat{e}_2  =   \begin{bmatrix} 0 \\ 1 \\ \vdots \\ 0 \end{bmatrix}\!,  \; \; \; 
\; \ldots,  \; \; \; 
\hat{e}_n  = \begin{bmatrix} 0 \\  \vdots \\ 0  \\ 1 \end{bmatrix}\!.](./images/f2e5eb1c021e12cdb0ebc4508a8fabf9a1985397.png)

The matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) that corresponds to the action of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) on the standard basis is

![M_T = 
\begin{bmatrix} 
\vert & \vert &  & \vert \\ 
T(\vec{e}_1) & T(\vec{e}_2) & \cdots & T(\vec{e}_n) \\
\vert & \vert &  & \vert 
\end{bmatrix}\!.](./images/a54eedbdd255e66a69904febd5d1c75bf7b5b7dc.png)

This is an ![m\times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrix whose columns are the outputs of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) for the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) probe inputs.

The remainder of this section illustrates the probing procedure for finding matrix representations of linear transformations.

###[Projections](./Front matter.md)

We’ll start with a class of linear transformations you’re already familiar with: _projections_. I hope you still remember what you learned in[Section 4.2](./Chapter 4_ Geometric aspects of linear algebra.md) (page 4.2).

####[X projection](./Front matter.md)

The projection onto the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis is denoted ![\Pi_{x}](./images/8c98addaed815f9db525ba864c820de1ff891c37.png). The projection ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) acts on any vector or point by leaving the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-component unchanged and setting the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-component to zero. The action of ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) on two sample points is illustrated in[Figure 5.5](./Chapter 5_ Linear transformations.md).

![projection_tox_t](./images/projection_tox_t.png)

Figure 5.5: The projection ![\Pi_x](./images/4eb38e56a7ba7ffe8b4186a253cafa88d93efcc9.png) takes all points to the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-axis.

Let’s analyze how the projection ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) transforms the two vectors of the standard basis:

![\Pi_x\!\!\left(    \begin{bmatrix} 1 \\ 0 \end{bmatrix} \right)\!
=
\begin{bmatrix} 1 \\ 0 \end{bmatrix}\!,
\quad
\Pi_x\!\!\left(    \begin{bmatrix} 0 \\ 1 \end{bmatrix} \right)\!
=
\begin{bmatrix} 0 \\ 0 \end{bmatrix}\!.](./images/ab4517b8df223ad605ea4bbe6a0ea265dd81a657.png)

The action of ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) on the basis ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png) is to leave it unchanged. The action of ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) on the basis ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png) is to send it to the zero vector.

The matrix representation of ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) is therefore given by:

![M_{\Pi_{x}}=
\begin{bmatrix}
\Pi_x\!\!\left(    \begin{bmatrix} 1 \\ 0 \end{bmatrix} \right)  & \!\!
\Pi_x\!\!\left(    \begin{bmatrix} 0 \\ 1 \end{bmatrix} \right)
\end{bmatrix} \!
=
\begin{bmatrix}
1  &  0 \\
0  &  0 
\end{bmatrix}\!.](./images/de2890a9b491949179389554a0ca39beb1e81c09.png)

####[Y projection](./Front matter.md)

Similar to ![\Pi_{x}](./images/8c98addaed815f9db525ba864c820de1ff891c37.png), ![\Pi_{y}](./images/505d12683593ec170ac826c0a36f82e7f01bf7d8.png) is defined as the projection onto the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis. The action of ![\Pi_y](./images/505d12683593ec170ac826c0a36f82e7f01bf7d8.png) on two sample points is illustrated in[Figure 5.6](./Chapter 5_ Linear transformations.md). Can you guess what the matrix for the projection onto the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis will look like?

![projection_toy_t](./images/projection_toy_t.png)

Figure 5.6: The projection ![\Pi_y](./images/f27d35067cec2b61f037e4e3ec1c2e8a241ee04c.png) takes all points to the ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png)\-axis.

Use the standard approach to find the matrix representation of ![\Pi_y](./images/505d12683593ec170ac826c0a36f82e7f01bf7d8.png):

![M_{\Pi_{y}} \!\! = \!
\begin{bmatrix}
\Pi_y\!\!\left(    \begin{bmatrix} 1 \\ 0 \end{bmatrix} \right)  & \!\!\!\!
\Pi_y\!\!\left(    \begin{bmatrix} 0 \\ 1 \end{bmatrix} \right)
\end{bmatrix}
\! = \!
\begin{bmatrix}
0  &  0 \\
0  &  1
\end{bmatrix}\!.](./images/6713472fb1dd013228ac35cdce99f5ec23e8e6b0.png)

The first column of the matrix representation ![M_{\Pi_{y}}](./images/643fb9f49fcef253a981300789228adf36c6ed69.png) contains the zero vector since ![\Pi_y(\hat{\imath})=\vec{0}](./images/cb705edfb0e6934020bf979f1b77e0120c4aaf5b.png). The second column of ![M_{\Pi_{y}}](./images/643fb9f49fcef253a981300789228adf36c6ed69.png) contains ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png) since ![\Pi_y(\hat{\jmath})=\hat{\jmath}](./images/d59a1b6d493a07081c97b2e5c0b4cd4d94c14ccf.png).

We can verify that the matrices ![M_{\Pi_{x}}](./images/b52ab9ff4c3f64fd300661883097976ceaf7fe21.png) and ![M_{\Pi_{y}}](./images/643fb9f49fcef253a981300789228adf36c6ed69.png) do indeed select the appropriate components from a general input vector ![\vec{v} = (v_x,v_y)^\sfT](./images/e41f81f3bafa3873e227d21ac7c9342a109557e2.png):

![\begin{bmatrix}
1  &  0 \\
0  &  0 
\end{bmatrix}
\!\!
\begin{bmatrix} v_x \\ v_y \end{bmatrix}
=
\begin{bmatrix} v_x \\ 0 \end{bmatrix},
\qquad
\begin{bmatrix}
0  &  0 \\
0  &  1 
\end{bmatrix}
\!\!
\begin{bmatrix} v_x \\ v_y \end{bmatrix}
=
\begin{bmatrix} 0 \\ v_y \end{bmatrix}\!.](./images/7ca231798844f43e94ec07058f059d81b674abc1.png)

####[Projection onto a vector](./Front matter.md)

Recall that the general formula for the projection of a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) onto another vector ![\vec{a}](./images/f0090c6a4c3d631f857e7e214dac1503513e48fc.png) is obtained as:

![\Pi_{\vec{a}}(\vec{v})=\left(\frac{\vec{a} \cdot \vec{v} }{ \| \vec{a} \|^2  }\right)\vec{a}.](./images/de764c8ee1f374c7e283b3e44a43584c6de3a942.png)

To find the matrix representation of a projection onto an arbitrary direction ![\vec{a}](./images/f0090c6a4c3d631f857e7e214dac1503513e48fc.png), we compute

![M_{\Pi_{\vec{a}}}=
\begin{bmatrix}
\Pi_{\vec{a}}\!\!\left(    \begin{bmatrix} 1 \\ 0 \end{bmatrix} \right)  & 
\Pi_{\vec{a}}\!\!\left(    \begin{bmatrix} 0 \\ 1 \end{bmatrix} \right)
\end{bmatrix}.](./images/0134119433f55b1789456ebacd7f49216fa40d65.png)

####[Projection onto a plane](./Front matter.md)

We can also compute the projection of the vector ![\vec{v} \in \mathbb{R}^3](./images/7d4d76835dd377bbd6d7248bd9e3aa55aa35fdfa.png) onto the plane ![P: \; \vec{n}\cdot\vec{x}=n_xx+n_yy+n_zz=0](./images/0d85424f7e2e6e48907125b9eca391ab263afd5e.png) as follows:

![\Pi_{P}(\vec{v}) = \vec{v} - \Pi_{\vec{n}}(\vec{v}).](./images/b285df6ce36570948ef2dbab22f1600d99c59b27.png)

How should we interpret the above formula? First compute the part of the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) that is perpendicular to the plane (in the ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png) direction); then subtract this part from ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) to obtain the part that lies in the plane.

To obtain the matrix representation of ![\Pi_{P}](./images/ced20ab32ffba6906845b9e2493cf9925a6c382a.png), calculate what ![\Pi_{P}](./images/ced20ab32ffba6906845b9e2493cf9925a6c382a.png) does to the vectors in the standard basis ![\hat{\imath} = \hat{e}_1 = (1,0,0)^\sfT](./images/9e03ac732a3cc1744f1e6dab62d378f0e081bfdb.png), ![\hat{\jmath} = \hat{e}_2 = (0,1,0)^\sfT](./images/2a300f0ec34f11afa22b951b4b8e359aaa6cd49c.png), and ![\hat{k} = \hat{e}_3 = (0,0,1)^\sfT](./images/0419d59f9502b39c277c2598742d35df4f172332.png).

####[Projections as outer products](./Front matter.md)

We can obtain the projection matrix onto any unit vector by computing the _outer product_ of the vector with itself. As an example, we’ll find the matrix for the projection onto the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis ![\Pi_x(\vec{v}) = (\vec{v} \cdot \hat{\imath}) \hat{\imath}](./images/176fd64da2923ad8c3645be8adf0444ca31fe00c.png). Recall the _inner product_ (dot product) between two column vectors ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is equivalent to the matrix product ![\vec{u}^\sfT \vec{v}](./images/0cfaf5fbb1d4a8d2b1bb699e9173374ec99a85ce.png), while the _outer product_ is given by the matrix product ![\vec{u}\vec{v}^\sfT](./images/e9e2698be3fbcd275db30173393a484b3894974e.png). The inner product is a product between a ![1\times n](./images/d470d6249220dd5f738c22ef1592c3a0bc5bd50e.png) matrix and an ![n \times 1](./images/3090ba3f3c80de1e80bc520aaec116200eb116f6.png) matrix, whose result is a ![1 \times 1](./images/f0c3d747f547beb566ee37904af637e54f75fa08.png) matrix—a single number. The outer product corresponds to an ![n\times 1](./images/3090ba3f3c80de1e80bc520aaec116200eb116f6.png) matrix times a ![1 \times n](./images/d470d6249220dd5f738c22ef1592c3a0bc5bd50e.png) matrix, making the answer an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix. The projection matrix corresponding to ![\Pi_x](./images/8c98addaed815f9db525ba864c820de1ff891c37.png) is ![M_{\Pi_x} = \hat{\imath}\hat{\imath}^\sfT \in \mathbb{R}^{n \times n}](./images/c910e5b9ea8507796a42cb019f2d4919bee69b29.png).

Where did that equation come from? To derive the equation, we use the commutative law of scalar multiplication ![\alpha \vec{v} = \vec{v}\alpha](./images/7dd60e4cff5852cd88c8bd06d9d90637c56da0f9.png), rewrite the dot product as a matrix product ![\vec{u}\cdot\vec{v} = \vec{u}^\sfT \vec{v}](./images/0706e38fb1eecc10212ced24a34cf3862121f82c.png), and use the _associative_ law of matrix multiplication ![A(BC)=(AB)C](./images/f88b7f047fa6d75b15f7dcbcf9f5324d3ce83fd1.png). Check it out:

![\begin{align*}
\Pi_x(\vec{v}) =
(\hat{\imath}\cdot\vec{v})\:\hat{\imath}
=
\hat{\imath} (\hat{\imath}\cdot\vec{v})
& =
\hat{\imath} (\hat{\imath}^\sfT \vec{v} )
=
\begin{bmatrix}
1 \\
0 
\end{bmatrix}
\!
\left(
\begin{bmatrix}
1 & 	0	
\end{bmatrix}
\!\!
\begin{bmatrix}
v_x \\
v_y 
\end{bmatrix}
\right) \\
& =
\left(\hat{\imath} \hat{\imath}^\sfT\right)  \vec{v} 
=
\left(
\begin{bmatrix}
1 \\
0 
\end{bmatrix}
\!\!
\begin{bmatrix}
1 & 	0	
\end{bmatrix}
\right)
\begin{bmatrix}
v_x \\
v_y 
\end{bmatrix} \\
& =
\left(M \right)  \vec{v} 
=
\begin{bmatrix}
1 & 0  \\
0 & 0 
\end{bmatrix}
\!\!
\begin{bmatrix}
v_x \\
v_y 
\end{bmatrix}
=
\begin{bmatrix}
v_x \\
0 
\end{bmatrix}\!.
\end{align*}](./images/f9a1cc5e92ccaf29a3ac65734f812558f913c265.png)

The outer product ![M \eqdef \hat{\imath}\hat{\imath}^\sfT](./images/85e0b780a220a2d75e8172aff1be6801fb32a087.png) corresponds to the projection matrix ![M_{\Pi_x}](./images/b52ab9ff4c3f64fd300661883097976ceaf7fe21.png) we’re looking for.

More generally, we obtain the projection matrix onto a line with direction vector ![\vec{a}](./images/f0090c6a4c3d631f857e7e214dac1503513e48fc.png) by constructing the unit vector ![\hat{a}](./images/0fb2a22a7052a151cb3fbfc5b473e61e8ccfeb10.png), and then calculating the outer product of ![\hat{a}](./images/0fb2a22a7052a151cb3fbfc5b473e61e8ccfeb10.png) with itself:

![\hat{a} = \frac{ \vec{a} }{ \| \vec{a} \| },
\qquad
M_{\Pi_{\vec{a}}}=\hat{a}\hat{a}^\sfT.](./images/fd298a3b7cae7c813d665ce5205c7011ab232d8b.png)

#####[Example](./Front matter.md)

Find the matrix representation ![M_d \in \mathbb{R}^{2 \times 2 }](./images/49b2670fa3be6a31a709d7ac14056d79db6ea947.png) for the projection ![\Pi_d](./images/b1001f7faf9061648c2ac4fd7538658598c30468.png) onto the ![45^\circ](./images/bd3d3974358aa0059bc92afb15aa60914b97d2d5.png)\-diagonal line with equation ![y=x](./images/f11b12456873127040f5e21fe0be791e0421166c.png).

The line with equation ![y=x](./images/f11b12456873127040f5e21fe0be791e0421166c.png) corresponds to the parametric equation ![\{ (x,y) \in \mathbb{R}^2 \; |\; (x,y)=(0,0) + t(1,1), \; t\in \mathbb{R}\}](./images/7b6e22f34f5c1d92465dc4561be19a695936aa02.png), so the direction vector for this line is ![\vec{a}=(1,1)^\sfT](./images/ac8c3c26bd84422efd5c833710ca2c4f9fdbcce3.png). We want to find the matrix that corresponds to the linear transformation ![\Pi_d(\vec{v})=\left(  \frac{\vec{v} \cdot(1,1)}{2}\right)\!(1,1)^\sfT](./images/d4100436d5b0c71460abb5917f1106c363929418.png).

The projection matrix onto ![\vec{a}=(1,1)^\sfT](./images/ac8c3c26bd84422efd5c833710ca2c4f9fdbcce3.png) is computed using the outer product approach. First, compute a normalized direction vector ![\hat{a}=(\tfrac{1}{\sqrt{2}},\tfrac{1}{\sqrt{2}})^\sfT](./images/a45e5014fcf3cc5a5f5c194bd16612bb6d42dd50.png); then compute ![M_d](./images/6d34c5b3c2b5e69315f9d4d4fdbfa0519648ea8c.png) using the outer product:

![M_d
=
\hat{a}\hat{a}^\sfT
=
\begin{bmatrix}
\tfrac{1}{\sqrt{2}} \\
\tfrac{1}{\sqrt{2}}  
\end{bmatrix}
\begin{bmatrix}
\tfrac{1}{\sqrt{2}}  &  \tfrac{1}{\sqrt{2}} 
\end{bmatrix}
=
\begin{bmatrix}
\frac{1}{2}  &  \frac{1}{2} \\
\frac{1}{2}  &  \frac{1}{2} 
\end{bmatrix}.](./images/e9f42d0b8ddcde24a8a4ed18cc63c4dccb006a7e.png)

Usually, the idea of representing projections as outer products is not covered in a first linear algebra course, so don’t worry about outer products appearing on the exam. The purpose of introducing you to the equivalence between projections onto ![\hat{a}](./images/0fb2a22a7052a151cb3fbfc5b473e61e8ccfeb10.png) and the outer product ![\hat{a}\hat{a}^\sfT](./images/5af6ff7572ff1844b3e07c336e9e4eef7d7edbd8.png) is to illuminate this interesting connection between vectors and matrices. This connection plays a fundamental role in quantum mechanics, where projections in different directions are frequently used.

If you’re asked a matrix representation question on an exam, keep things simple and stick to the “probing with the standard basis” approach, which gives the same answer as the one computed using the outer product:

![M_{d}=
\begin{bmatrix}
\Pi_d\!\!\left(    \begin{bmatrix} 1 \\ 0 \end{bmatrix} \right)  & \!\!
\Pi_d\!\!\left(    \begin{bmatrix} 0 \\ 1 \end{bmatrix} \right)
\end{bmatrix}
=
\begin{bmatrix}
\left(\frac{\hat{\imath}\cdot\vec{a}  }{ \| \vec{a} \|^2  }\right)\!\vec{a} 
&
\left(\frac{\hat{\jmath}\cdot\vec{a} }{ \| \vec{a} \|^2  }\right)\!\vec{a}
\end{bmatrix}
=
\begin{bmatrix}
\frac{1}{2}  &  \frac{1}{2} \\
\frac{1}{2}  &  \frac{1}{2} 
\end{bmatrix}\!.](./images/319d37f3222b6fe15ebe68e64ae1ddb22d43cfbb.png)

####[Projections are idempotent](./Front matter.md)

A projection matrix ![M_{\Pi}](./images/2123e7425d926fdec4bc9be5d5268694fe27d5a8.png) satisfies ![M_{\Pi}M_{\Pi}=M_{\Pi}](./images/b7e93b2e02adec816cfc3a3dcca0bceafdfd05f0.png). This is one of the defining properties of projections. The technical term for this is _idempotence_, meaning the operation can be applied multiple times without changing the result beyond the initial application.

####[Subspaces](./Front matter.md)

A projection acts differently on different sets of input vectors. While some input vectors remain unchanged, other input vectors are “killed.” This is murder! Well, murder in a mathematical sense, which means multiplication by zero.

Let ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png) be the projection onto the space ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png), and ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) be the _orthogonal complement_ to ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) defined by ![S^\perp  \eqdef  \{ \, \vec{w} \in \mathbb{R}^n \; | \; \vec{w} \cdot \vec{s} = 0, \, \forall \vec{s} \in S \, \}](./images/9fa48fac7824e959d417c17fbcc15aacf71c6236.png). The action of ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png) is completely different for the vectors from ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) and ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png). All vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) remain unchanged,

![\Pi_S(\vec{v}) = \vec{v},](./images/23e71d2d1740e21b2c6e7e326b27b12e5439ec86.png)

whereas vectors ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) in ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) are killed,

![\Pi_S(\vec{w}) = 0\vec{w} = \vec{0}.](./images/b116f0617d825c6742dbb47ba155594725a5d4a2.png)

The action of ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png) on any vector from ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) is equivalent to multiplication by zero. This is why ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) is called the _null space_ of ![M_{\Pi_S}](./images/dad23b61f6ec79dd3c733d48cfe6b23a34c07501.png).

###[Reflections](./Front matter.md)

We’ll now compute matrix representations for simple _reflection_ transformations.

####[X reflection](./Front matter.md)

Reflection through the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis leaves the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-component unchanged and flips the sign of the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-component.[Figure 5.7](./Chapter 5_ Linear transformations.md) illustrates the effect of reflecting two points through the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis.

![reflection_throughx_t](./images/reflection_throughx_t.png)

Figure 5.7: The reflection through the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-axis sends every point ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png) in the plane to its mirror point ![(x,-y)](./images/ca80ffea6443217f4432fcd5a32cb05c249adc1c.png) on the other side of the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-axis.

Using the usual probing procedure, we obtain the matrix that corresponds to this linear transformation:

![M_{R_x} \!= \!
\begin{bmatrix}
R_x\!\!\left(    \begin{bmatrix} 1 \\ 0 \end{bmatrix} \right)  & \!\!\!
R_x\!\!\left(    \begin{bmatrix} 0 \\ 1 \end{bmatrix} \right)
\end{bmatrix}\!
=
\!
\begin{bmatrix}
1  &  0 \\
0  & \!\!-1 
\end{bmatrix}\!.](./images/7d56606716507eb55668bda7705e6d55f489c1a5.png)

This matrix sends ![(x,y)^\sfT](./images/914c41cdbc3f70ded5dc134fd638060d36b2223f.png) to ![(x,-y)^\sfT](./images/a03399eadb349532636dec6a8bec4656b7b9ee6e.png) as expected for a reflection through the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis.

####[Y reflection](./Front matter.md)

The matrix associated with ![R_y](./images/b05e94ce3f8666716bfd30fead86df9b9ba8505c.png), the reflection through the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis, is given by:

![M_{R_y}=
\begin{bmatrix}
-1  & 0 \\
0  & 1 
\end{bmatrix}\!.](./images/deba19e7b41c06e4d4824c42a065665464c66093.png)

The numbers in the above matrix tell us to change the sign of the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-component of the input and leave its ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-component unchanged. In other words, every point that starts to the left of the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis moves to the right of the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis, and every point that starts to the right of the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis moves to the left.

![reflection_throughy_t](./images/reflection_throughy_t.png)

Figure 5.8: The reflection through the ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png)\-axis flips the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-component of every point in the plane.

Do you see the power and simplicity of the probing procedure for finding matrix representations? In the first column, enter what you want to happen to the ![\hat{e}_1](./images/6918c3bc61ee2edc463842c5b586359c71047541.png) vector; in the second column, enter what you want to happen to the ![\hat{e}_2](./images/4a63957434b4c53e36baba2d6b8fe95b725bd6e2.png) vector, and voila!

####[Diagonal reflection](./Front matter.md)

Suppose we want to find the formula for the reflection through the line ![y=x](./images/f11b12456873127040f5e21fe0be791e0421166c.png). We’ll call this reflection ![R_{d}](./images/97c5e6d01f880785059a08a25038cab0a71ac88b.png). This time, dear readers, it’s up to you to draw the diagram. In words, ![R_d](./images/97c5e6d01f880785059a08a25038cab0a71ac88b.png) is the transformation that makes ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) “swap places.”

Based on this notion of swapping places, the matrix for ![R_d](./images/97c5e6d01f880785059a08a25038cab0a71ac88b.png) is

![M_{R_d}=
\begin{bmatrix}
0  & 1 \\
1  & 0 
\end{bmatrix}\!.](./images/f4de9cd4025de625eb4799d5d14758690b2bbd14.png)

Alternatively, the usual probing procedure leads us to the same result.

Now I must point out an important property common to all reflections. The effect of a reflection is described by one of two possible actions: some points remain unchanged by the reflection, while other points flip into their exact negatives. For example, the _invariant_ points under ![R_{y}](./images/b05e94ce3f8666716bfd30fead86df9b9ba8505c.png) are the points that lie on the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis—that is, the multiples of ![(0,1)^\sfT](./images/60bc79b1eaf757f84538b00ed706e5f70c30bb8e.png). The points that become their _exact negatives_ are those with only an ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-component—the multiples of ![(1,0)^\sfT](./images/739d3ab405159af8f10bf884a0fc5b87f1ac69a1.png). The action of ![R_y](./images/b05e94ce3f8666716bfd30fead86df9b9ba8505c.png) on all other points can be obtained as a linear combination of the actions “do not change” and “multiply by ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png).” We’ll continue this line of reasoning further at the end of this section, and again in[Section 6.1](./Chapter 6_ Theoretical linear algebra.md).

####[Reflections through lines and planes](./Front matter.md)

What about finding reflections through arbitrary lines and planes? We can leverage the formulas for projections onto lines and planes we saw earlier to obtain formulas for reflections through any line or plane that passes through the origin.

Consider the line with parametric equation ![\ell:  \{ \vec{0} + t\vec{a}, t\in\mathbb{R}\}](./images/ad55ea75adc138a99d67d0cea143d87b5d0b4b4f.png). The formula for the reflection of any vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) through the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) is

![R_{\vec{a}}(\vec{v})=2\Pi_{\vec{a}}(\vec{v})-\vec{v},](./images/65ea4892bfc1a30d083e5f16ffa3e64a82c507a4.png)

where ![\Pi_{\vec{a}}(\vec{v}) =\frac{\vec{a} \cdot \vec{v} }{ \| \vec{a} \|^2 }\vec{a}](./images/c9e7f7701a5d85658948c5629546e58572696a51.png) is the projection of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) onto the vector ![\vec{a}](./images/f0090c6a4c3d631f857e7e214dac1503513e48fc.png).

The vector diagram in[Figure 5.9](./Chapter 5_ Linear transformations.md) illustrates the reflection formula. Annotating the figure with a pencil can help you visualize how the formula works. Draw the vector ![2\Pi_{\vec{a}}(\vec{v})](./images/0d747843f157d1183a39c0501542a5baf3653741.png) followed by the vector ![-\vec{v}](./images/94247fe06a9c49f57f122551105114b04ce56e08.png) and confirm that ![2\Pi_{\vec{a}}(\vec{v})-\vec{v}](./images/75ad1ea467d9bfe0a3173e45685d98e4d7cce3cb.png) results in the vector ![R_{\vec{a}}(\vec{v})](./images/6558f408d2374681093711d634e1b01116185dc9.png).

![lines_and_planes_reflection_through_a_line](./images/lines_and_planes_reflection_through_a_line.png)

Figure 5.9: The reflection of the vector ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) through the line ![\ell:  \{ \vec{0} + t\vec{a}, t\in\mathbb{R}\}](./images/7a3776fa6524b71631e3f3387248474435216d27.png) is computed using the formula ![R_{\vec{a}}(\vec{v})=2\Pi_{\vec{a}}(\vec{v})-\vec{v}](./images/9421159d30ba1c6c8cb8092a7bc728568e74ef63.png).

We can derive two equivalent formulas for computing the reflection of the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) through the plane ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) defined by the equation ![\vec{n}\cdot\vec{x}=0](./images/c54fd48560bd87241cb779e51221014b658e9a65.png):

![R_{P}(\vec{v})=2\Pi_{P}(\vec{v})-\vec{v}
\qquad\textrm{or}\qquad
R_{P}(\vec{v})=\vec{v}-2\Pi_{\vec{n}}(\vec{v}).](./images/8c0976cb0c90f80a6eae3a61c292d4f06be7dd12.png)

The first formula uses a reasoning similar to the formula for the reflection through a line. The second formula can be understood as computing the projection of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in the direction of the normal vector, ![\Pi_{\vec{n}}(\vec{v})](./images/8b014999be0530234ca380977f1d13905459f709.png), subtracting that vector once from ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) to reach a point in the plane, and subtracting it a second time to move to the point ![R_{P}(\vec{v})](./images/f5a0d296d0f1a3f67d2b84e4c3504735e1579fc4.png) on the other side of the plane. See[Figure 5.10](./Chapter 5_ Linear transformations.md) for the illustration.

![lines_and_planes_reflection_through_a_plane](./images/lines_and_planes_reflection_through_a_plane.png)

Figure 5.10: The reflection of the vector ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) through the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) with normal vector ![\vec{n}](./images/7da6b307d5458666fc055f8a1f35f4dc2c7b11d7.png) is computed by starting with ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) and subtracting twice the projection of ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) in the direction of the normal: ![R_{P}(\vec{v})=\vec{v}-2\Pi_{\vec{n}}(\vec{v})](./images/50c31b2ceb60d11b072ba06b8ac53592c77a03ca.png).

###[Rotations](./Front matter.md)

We’ll now find the matrix representations for _rotation_ transformations. The counterclockwise rotation by the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is denoted ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png).[Figure 5.11](./Chapter 5_ Linear transformations.md) illustrates the action of the rotation ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png): the point ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is rotated around the origin to become the point ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

![rotation_t](./images/rotation_t.png) ![rotation-by-theta-tmp](./images/rotation-by-theta-tmp.png)

Figure 5.11: The linear transformation ![R_\theta](./images/d690dfc5e22f6fd3c9b29df0d1d802357081e275.png) rotates every point in the plane by the angle ![\theta](./images/962d17a7e21d58659675e6e02789c85029447dd5.png) in the counterclockwise direction. Note the effect of ![R_\theta](./images/d690dfc5e22f6fd3c9b29df0d1d802357081e275.png) on the basis vectors ![(1,0)](./images/17fa76d96a4d6efa1a8a1bab1ccb6699ef7b2e34.png) and ![(0,1)](./images/e69b48bc6687ee74a843dea90543682e53e069e3.png).

To find the matrix representation of ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png), probe it with the standard basis as usual:

![M_{R_\theta}=
\begin{bmatrix}
R_\theta\!\!\left(    \begin{bmatrix} 1 \\ 0 \end{bmatrix} \right)  & \!\!\!
R_\theta\!\!\left(    \begin{bmatrix} 0 \\ 1 \end{bmatrix} \right)
\end{bmatrix}\!.](./images/f1f336e7441ae6d5fd11ae75167f92be85e1a71b.png)

To compute the values in the first column, observe that ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) rotates the vector ![(1,0)^\sfT=1\angle 0](./images/ebc7d3d7654b37905837ad18294504b03aa07000.png) to the vector ![1\angle \theta=(\cos \theta, \sin\theta)^\sfT](./images/320d96fe780a1e76fa162a17298e6056fe99038d.png). The second input ![\hat{e}_2=(0,1)^\sfT=1\angle \tfrac{\pi}{2}](./images/12a032e51051219ddc483c3d102d2881ff3a9296.png) is rotated to ![1\angle (\tfrac{\pi}{2}+\theta) =(-\sin\theta,\cos \theta)^\sfT](./images/87c03ae843e5a3df8005e2854ca334a5faab9045.png). Therefore, the matrix for ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) is

![M_{R_\theta} 
\; = \; 
\begin{bmatrix} 
\vert & \vert \\
{\scriptstyle 1\angle \theta} & \, {\scriptstyle 1\angle (\!\tfrac{\pi}{2}\!+\!\theta) } \\
\vert & \vert 
\end{bmatrix}
\; = \; 
\begin{bmatrix}
\cos\theta	&-\sin\theta \\
\sin\theta	&\cos\theta
\end{bmatrix}\!.](./images/47c6147cb46abec6acb2a0d3cb793331a8e824f3.png)

Finding the matrix representation of a linear transformation is like a colouring-book activity for mathematicians. Filling in the columns is just like colouring inside the lines—nothing too complicated.

###[Inverses](./Front matter.md)

Can you determine the inverse matrix of ![M_{R_\theta}](./images/60dc1481c43df67b678450528f649658a2ec45a6.png)? You could use the formula for finding the inverse of a ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix, _or_ you could use the ![[ \: A \: |\; I \;]](../Images/85c2d240f85887a06fb4a22d6b859577f7c63c49.png)\-and-RREF algorithm for finding the inverse; but using either of these approaches would be _waaaaay_ too much work. Try to guess the matrix representation of the inverse without doing any calculations. If ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) rotates points by ![+\theta](./images/c057ac77df8b0cfd7d474edc97b6afd33230f81c.png), can you tell me what the inverse operation does? I’ll leave a blank line here to give you some time to think….

Think you have it? The inverse operation of ![R_{\theta}](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) is ![R_{-\theta}](./images/3f8b3b47ab0a0631ff60a366d2369038d97fea1e.png), a rotation by ![-\theta](./images/cb6e2eba55544b3197fa16e9dbbe033ba55a9a13.png), which corresponds to the matrix

![M_{R_{-\theta}} =
\begin{bmatrix}
\cos\theta	&\sin\theta \\
-\sin\theta	&\cos\theta
\end{bmatrix}\!.](./images/4d0f7c2950ef1f8cb19460953104f39aedf46fc5.png)

Recall that ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png) is an even function, so ![\cos(-\theta) = \cos(\theta)](./images/ecdbb22f24507f5ef54e38c9606a6840893e84bc.png), while ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png) is an odd function, so ![\sin(-\theta) = -\sin(\theta)](./images/4ca785efbeb031f980a3f1dc86910977fd97b578.png).

For any vector ![\vec{v}\in \mathbb{R}^2](./images/e3178de0f13474a865bbadb33a26cc93ba2230b3.png) we have ![R_{-\theta}\left(R_{\theta}(\vec{v})\right)=\vec{v}=R_{\theta}\left(R_{-\theta}(\vec{v})\right)](./images/91bf4469f0e69a3eee0fe6841aee2d8d7723d973.png); or in terms of matrices,

![M_{R_{-\theta}}M_{R_{\theta}} \; = \;  \mathbbm{1} \;  = \; M_{R_{\theta}}M_{R_{-\theta}}.](./images/320b6eecfbbfe0e41739c0bb2e6557ae31c4b8d6.png)

Cool, right? This is what _representation_ really means: the abstract notion of composition of linear transformations is _represented_ as a matrix product.

Here’s another quiz question: what is the inverse operation of the reflection through the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis ![R_x](./images/d303d20c9e866d40a6cd9742d42929a34f3acec3.png)? The “undo” action for ![R_x](./images/d303d20c9e866d40a6cd9742d42929a34f3acec3.png) is to apply ![R_x](./images/d303d20c9e866d40a6cd9742d42929a34f3acec3.png) again. We say ![R_x](./images/d303d20c9e866d40a6cd9742d42929a34f3acec3.png) is a self-inverse operation.

What is the inverse matrix of a projection ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png)? Good luck finding that one—it’s a trick question. The projection ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png) sends all input vectors from the subspace ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) to the zero vector. Projections are inherently many-to-one transformations and therefore not invertible.

###[Nonstandard-basis probing](./Front matter.md)

At this point, you should feel confident facing any linear transformation ![T:\mathbb{R}^2\to\mathbb{R}^2](./images/5983a52066d18e5338bbb02e92cb094cfbdd0957.png) and probing it with the standard basis to find its matrix representation ![M_T \in \mathbb{R}^{2\times 2}](./images/ede70b4e19ec97f08dc8f0b456a69e7719fc7361.png). But what if you’re not allowed to probe ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with the standard basis? Instead, let’s say you must find the matrix of the transformation given the outputs of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) for some other basis ![\{ \vec{v}_1 = (v_{1x},v_{1y})^\sfT, \vec{v}_2 = (v_{2x},v_{2y})^\sfT \}](./images/d24a7e5307dbf0d833b6d81578fb027a78241dad.png):

![T\!\!\left(    \begin{bmatrix} v_{1x} \\ v_{1y} \end{bmatrix} \right)
=
\begin{bmatrix} t_{1x} \\ t_{1y} \end{bmatrix},
\qquad
T\!\!\left(    \begin{bmatrix} v_{2x} \\ v_{2y} \end{bmatrix} \right)
=
\begin{bmatrix} t_{2x} \\ t_{2y} \end{bmatrix}.](./images/9e3adbbdb00b2d76245b7baf15478c9ff495d7cd.png)

Let’s test this idea. We’re given the information ![v_{1x}, v_{1y}, t_{1x}, t_{1y}](./images/4817bd2d2e792ad8702bba33826540b4769e4261.png), and ![v_{2x}, v_{2y}, t_{2x}, t_{2y}](./images/e6d782e8ec69e110c8fde898499e4339bd23ed11.png), and must find the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to the standard basis.

Because the vectors ![\vec{v}_1](./images/c54fb33fabbbfe15a0faf1385a358827912b5473.png) and ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png) form a basis, we can reconstruct the information about the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) from the input-output information given. We’re looking for four unknowns—![m_{11}](./images/0c84607de5d2f41c11b43fbd7cee39ab6fc199a9.png), ![m_{12}](./images/0a638f543ed55da18abde1e33ab9da664c31ec1b.png), ![m_{21}](./images/ff2d614e545a4645e603865be4c6f598c25e7193.png), and ![m_{22}](./images/3c1daf8e494db761fc95c40427bfca11d2d72ea7.png)— that form the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png):

![M_T = 
\begin{bmatrix}
m_{11} &  m_{12} \\
m_{21} &  m_{22}
\end{bmatrix}\!.](./images/0d52838c367e80eddc8c125eb6e0ecad82170ed2.png)

We can write four equations with the input-output information provided:

![\begin{align*}
m_{11}v_{1x} + m_{12} v_{1y} & = t_{1x}, \\
m_{21}v_{1x} + m_{22} v_{1y} & = t_{1y}, \\
m_{11}v_{2x} + m_{12} v_{2y} & = t_{2x}, \\
m_{21}v_{2x} + m_{22} v_{2y} & = t_{2y}.
\end{align*}](./images/80a9dfb7331694fbc3d43978a35bbb1450f3e65b.png)

Since there are four equations and four unknowns, we can solve for the coefficients ![m_{11}](./images/0c84607de5d2f41c11b43fbd7cee39ab6fc199a9.png), ![m_{12}](./images/0a638f543ed55da18abde1e33ab9da664c31ec1b.png), ![m_{21}](./images/ff2d614e545a4645e603865be4c6f598c25e7193.png), and ![m_{22}](./images/3c1daf8e494db761fc95c40427bfca11d2d72ea7.png).

This system of equations differs from ones we’ve seen before, so we’ll examine it in detail. Think of the entries of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) as a ![4\times 1](./images/fd45adbbd05816fd37852cf5511e175ce85294bb.png) vector of unknowns ![\vec{m}=(m_{11}, m_{12}, m_{21}, m_{22})^\sfT](./images/5bebc2ae86b2bf3f0125814d44d03916d2930d10.png). We can rewrite the four equations as a matrix equation:

![A\vec{m}
= \vec{t}
\qquad 
\Leftrightarrow
\qquad
\begin{bmatrix}
v_{1x}  & v_{1y} & 0 	   & 0 		\\      
0 	& 0 	 & v_{1x}  & v_{1y}  	\\
v_{2x}  & v_{2y} & 0 	   & 0 		\\      
0 	& 0 	 & v_{2x}  & v_{2y}  	
\end{bmatrix}
\!\!
\begin{bmatrix}
m_{11} \\ m_{12} \\ m_{21} \\ m_{22} 
\end{bmatrix}
=
\begin{bmatrix}
t_{1x} \\ t_{1y} \\ t_{2x} \\ t_{2y}
\end{bmatrix}\!.](./images/23651d559644ed2c6eea66892ee5f9849657ee6d.png)

Next, solve for ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) by computing ![\vec{m}=A^{-1}\vec{t}](./images/312dc90e4c657dd7bbb763e7a6e62c24afe782c3.png).

Finding the matrix representation by probing with a nonstandard basis is more work than probing with the standard basis, but it’s totally doable.

###[Eigenspaces](./Front matter.md)

Probing the transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with _any_ basis for the input space gives sufficient information to determine its matrix representation. We’re free to choose the “probing basis,” so how do we decide which basis to use? The standard basis is good for computing the matrix representation, but perhaps there’s a basis that allows us to simplify the abstract description of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png); a so-called _natural_ basis for probing each transformation.

Indeed, such a basis exists. Many linear transformations have a basis ![\{ \vec{e}_{\lambda_1}, \vec{e}_{\lambda_2}, \ldots \}](./images/08de2c699bce3b6c023ea6253325b365a588ea8d.png) such that the action of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) on the basis vector ![\vec{e}_{\lambda_i}](./images/93c5fcf398fb33ead2faff86020d9fefdfdcb678.png) is equivalent to the scaling of ![\vec{e}_{\lambda_i}](./images/93c5fcf398fb33ead2faff86020d9fefdfdcb678.png) by the constant ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png):

![T(\vec{e}_{\lambda_i}) = \lambda_i \vec{e}_{\lambda_i}.](./images/4d03312538f9d0861bbb1900b1c2daec0c611cd6.png)

Recall how projections leave some vectors unchanged (multiply by ![\lambda=1](./images/80fc8bed47c96f557f144e0985441a990951940c.png)) and send other vectors to the zero vector (multiply by ![\lambda=0](./images/10934b7194187c81748d1850a1ebd06584c5a07b.png)). These subspaces of the input space are specific to each transformation, and are called the _eigenspaces_ (from the German “own spaces”) of the transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png).

Consider the reflection ![R_x](./images/d303d20c9e866d40a6cd9742d42929a34f3acec3.png) and its two eigenspaces:

-   The space of vectors that remain unchanged (the eigenspace corresponding to ![\lambda_1=1](./images/059d866c639cc9ccb539a1be16c52dc3413a9956.png)) is spanned by the vector ![(1,0)](./images/d8f32e7b923a10bccdaa68e7141d6158e48cdc1f.png):
    
    ![R_x\!\!\left(    \begin{bmatrix} 1 \\ 0 \end{bmatrix} \right)
    = 1 \begin{bmatrix} 1 \\ 0 \end{bmatrix}.](./images/fea23ef1a7f5197137ff52fb945f2e77747c07ad.png)
    
-   The space of vectors that become the exact negatives of themselves (corresponding to ![\lambda_2=-1](./images/415435ee62fe1a60391f67c278fa6b2350ad062b.png)) is spanned by ![(0,1)](./images/51dc53e490143c62313d23af4c20f5a4e63d4d20.png):
    
    ![R_x\!\!\left(    \begin{bmatrix} 0 \\ 1 \end{bmatrix} \right)
    = -1 \begin{bmatrix} 0 \\ 1 \end{bmatrix}.](./images/6f9ef1ae81d23413a5423de34044565df7d06785.png)
    

From a theoretical point of view, describing the action of a liner transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) in its natural basis is the best way to understand it. For each of the _eigenvectors_ in the various eigenspaces of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png), the action of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is a simple scalar multiplication. We defer the detailed discussion on _eigenvalues_ and _eigenvectors_ until the next chapter.

###[Links](./Front matter.md)

\[ Rotation operation as the composition of three shear operations \]

[`http://datagenetics.com/blog/august32013/index.html`](./index.md)

###[Exercises](./Front matter.md)

E5.5 Find the matrix representation of the linear transformations: the rotation by ![\frac{\pi}{4}](./images/83eb36bebaea14b26caf7467fcb663a1882deb23.png) radians ![R_{\frac{\pi}{4}}](./images/b60a8d6d122d072463f9f26a70c7b2b5765c8128.png), and the rotation by ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png) radians ![R_{\frac{\pi}{2}}](./images/f0a16edffd8b13c4a1f3e4600d2abaa345c92430.png). Verify the equation ![R_{\frac{\pi}{4}} \circ R_{\frac{\pi}{4}} = R_{\frac{\pi}{2}}](./images/01e1636334bd93f17af183e5333c3ceb630cb35d.png) by computing the product of the matrix representations.

The trigonometric identities from[Section 1.12](./Chapter 1_ Math fundamentals.md) might be helpful.

E5.6 Find the matrix representation of the projection ![\Pi_{\vec{d}}](./images/8098f35f07c75138b4abbdd01366e59739274761.png)  that projects vectors onto the subspace spanned by the direction vector ![\vec{d} = (1,3)^\sfT](./images/3221623b708f6ddaa5e4ec8742b78dfe1c88e156.png).

Compute the unit vector ![\hat{d}](./images/3585af26e87e5f04540c12eeeae6a021a6063ad1.png), then use the outer product formula.

##[5.3 Change of basis for matrices](./Chapter 5_ Linear transformations.md)

Every linear transformation ![T : \mathbb{R}^n \to \mathbb{R}^m](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png) can be represented as a matrix ![M_T \in \mathbb{R}^{m \times n}](./images/941601a4ecd9670b4e8d5963fcb6365be4ae7908.png). The entries of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) depend on the basis used to describe the input and output spaces. Note, this dependence of matrix entries on the basis is directly analogous to the dependence of vector coordinates on the basis.

In this section, we’ll learn how the choice of basis affects the entries of matrix representations, and discuss how to carry out the change-of-basis operation for matrices.

###[Concepts](./Front matter.md)

You should already be familiar with the concepts of vector spaces, bases, vector coordinates with respect to different bases, and the change-of-basis transformation:

-   ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png): an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space
-   ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png): a vector in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)
-   ![B=\{ \hat{e}_1, \hat{e}_2, \ldots, \hat{e}_n \}](./images/5f09ec874b543c3bd540d193ec13851044a04c46.png): an orthonormal basis for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)
-   ![\left[\vec{v} \right]_{B}=(v_1, v_2, \ldots, v_n)_{B}](../Images/1d2d4efed865758c4439a744272106d7293ae64b.png): the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) expressed in the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)
-   ![B^\prime=\{ \hat{e}^\prime_1, \hat{e}^\prime_2, \ldots, \hat{e}^\prime_n \}](./images/3489aa5fd19eaf68d1cd6f71106b56fee42562df.png): another orthonormal basis for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)
-   ![[\vec{v}]_{B^\prime}=(v^\prime_1, v^\prime_2, \ldots, v^\prime_n)_{B^\prime}](../Images/c933d43adc9042c63f65c64b1bf50b24808d6d3b.png): the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) expressed in the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png)
-   ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/b3068d47a22daef194cb14735750ffa22f484a70.png): the change-of-basis matrix that converts from ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) coordinates to ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) coordinates, ![[\vec{v}]_{B^\prime} = \tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}\,[\vec{v}]_{B}](../Images/f1c32ab9c513e7c6ac32d1ad4a9b2d10b40416a0.png)
-   ![\!\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/17cc63d61cf74f9d91e01962ea51c62dc63ad57f.png): the inverse change-of-basis matrix ![[\vec{v}]_{B} = \tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}\,[\vec{v}]_{B^\prime}](../Images/22bf3a6dca137eefd52b975862c1e64e1cf54cf0.png) (note that ![\!\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}} = \left(\!	\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}} \!\,\right)^{-1}](../Images/29fdc1749faeac53388f1e40c5ca71940959a6e9.png))

We’ll use the following concepts when describing a linear transformation ![T: V \to W](./images/6f6abcb4c10a6a13779cdad441002ebe2bfb94ea.png):

-   ![B_V=\{ \vec{e}_1, \vec{e}_2, \ldots, \vec{e}_n\}](./images/8b1288c813edf28f2310386beddc783812647d16.png): a basis for the input vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)
-   ![B_W=\{ \vec{b}_1, \vec{b}_2, \ldots, \vec{b}_m\}](./images/b7cdf8cb02caa442f12d71abcf9b156bdddb06bd.png): a basis for the output vector space ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png)
-   ![\!\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}} \in \mathbb{R}^{m\times n}](../Images/2e63f8bcee5de1be1728f10858cf7438a09374de.png): a matrix representation of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to the bases ![B_V](./images/b34e40af7663e726b4e1eb9cd5ef93b05e45a47e.png) and ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png),
    
    ![\vec{w} = T(\vec{v})  
    \; \;  \qquad \Leftrightarrow \qquad  \; \; 
    \tensor{[\vec{w}]}{_{B_W}} = \tensor[_{B_W}]{\left[M_T\right]}{_{B_V}} \tensor{[\vec{v}]}{_{B_V}}](../Images/fb0aaa72d5f733307a61ebdee6faa0f1120ba3fb.png)
    

By far, the most commonly used basis in linear algebra is the standard basis ![\hat{e}_1=(1,0,0, \ldots)^\sfT](./images/b4b643d186cbfee81a3190640c33a82b58d0b660.png), ![\hat{e}_2=(0,1,0, \ldots)^\sfT](./images/7d4d809b4ce4dbdd93d78579d9f341d11ec1c369.png), etc. It is therefore customary to denote the matrix representation of a linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) simply as ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png), without an explicit reference to the input and output bases. This simplified notation causes much confusion when students later try to learn about change-of-basis operations.

In order to _really_ understand the connection between linear transformations and their matrix representations, we need to have a little talk about bases and matrix entries. It’s a little complicated, but the mental effort you invest is worth the overall understanding you’ll gain. As the old Samurai saying goes, “Cry during training, laugh on the battlefield.”

By the end of this section, you’ll be able to handle any basis question your teacher may throw at you.

###[Matrix entries](./Front matter.md)

Every linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) can be represented as a matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png). Consider the linear transformation ![T:V \to W](./images/6f6abcb4c10a6a13779cdad441002ebe2bfb94ea.png). Assume the input vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional and let ![B_V=\{ \hat{e}_1, \hat{e}_2, \ldots, \hat{e}_n \}](./images/8dd76021f7e4ad6a9f5f487996617fb7a60638f1.png) be a basis for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). Assume the output space ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) is ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)\-dimensional and let ![B_W=\{ \vec{b}_1, \vec{b}_2, \ldots, \vec{b}_m\}](./images/b7cdf8cb02caa442f12d71abcf9b156bdddb06bd.png) be a basis for output space of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). The entries of the matrix ![M_T \in \mathbb{R}^{m \times n}](./images/941601a4ecd9670b4e8d5963fcb6365be4ae7908.png) depend on the bases ![B_V](./images/b34e40af7663e726b4e1eb9cd5ef93b05e45a47e.png) and ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png). We’ll now analyze this dependence in detail.

To compute the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to the input basis ![B_V=\{ \hat{e}_1, \hat{e}_2, \ldots, \hat{e}_n \}](./images/8dd76021f7e4ad6a9f5f487996617fb7a60638f1.png), we probe ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with each of the vectors in the basis and record the outputs as the columns of a matrix:

![\tensor{\left[M_T\right]}{_{B_V}}
=
\begin{bmatrix}
\vert & \vert &  & \vert \\
T(\hat{e}_1) & T(\hat{e}_2) & \cdots & T(\hat{e}_n) \\
\vert & \vert &  & \vert 
\end{bmatrix}_{\!B_V}.](../Images/8348848e2f67ca686edfe175de759daa5327fadc.png)

The subscript ![B_V](./images/b34e40af7663e726b4e1eb9cd5ef93b05e45a47e.png) indicates the columns are built from outputs of the basis ![B_V](./images/b34e40af7663e726b4e1eb9cd5ef93b05e45a47e.png). We can use the matrix ![\tensor{\left[M_T\right]}{_{B_V}}](../Images/a794d511390dc656a4019b80d9e72d0597cf7a49.png) to compute ![T(\vec{v})](./images/23f53bdb5049e614d60619289bc062cf19ba0c51.png) for a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) expressed in the basis ![B_V](./images/b34e40af7663e726b4e1eb9cd5ef93b05e45a47e.png): ![\vec{v} = (v_1,v_2,\ldots,v_n)^\sfT_{B_V}](./images/700ef7ebfb953b21afd23d467cbd39f5e1e396fa.png). The matrix-vector product produces the correct linear combination of outputs:

![\begin{align*} 
\tensor{\left[M_T\right]}{_{B_V}} \tensor{\left[\vec{v}\right]}{_{B_V}} 
&=    \begin{bmatrix}
\vert & \vert &  & \vert \\
T(\hat{e}_1) & T(\hat{e}_2) & \cdots & T(\hat{e}_n) \\
\vert & \vert &  & \vert
\end{bmatrix}_{\!B_V}
\!\!
\begin{bmatrix}
v_1 \\ v_2 \\ \vdots \\ v_n 
\end{bmatrix}_{\!B_V} 								\\
& = v_1T(\hat{e}_1) + v_2T(\hat{e}_2) + \cdots + v_nT(\hat{e}_n) 	\\
&=  T(v_1\hat{e}_1 + v_2\hat{e}_2 + \cdots + v_n\hat{e}_n)		\\
& = T(\vec{v}).
\end{align*}](../Images/bdfe9c2e788d3220296bcfa625bbf018ee0c506c.png)

So far we’ve treated the outputs of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) as abstract vectors ![T(\hat{e}_j) \in W](./images/3994d022c7a5e4ea4b4d947b9f6b47adba38ce20.png). Like all vectors in the space ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png), each output of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) can be expressed as a vector of components with respect to the basis ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png). For example, the output ![T(\hat{e}_1)](./images/35befe18e88516bc4c9b366cc6323f0da982f42b.png) can be expressed as

![T(\hat{e}_1) 
= \begin{bmatrix} c_{11}  \\ c_{21} \\  \vdots \\ c_{m1} \end{bmatrix}_{\!B_W} \!\!
= c_{11}\vec{b}_1 + c_{21}\vec{b}_2 + \cdots + c_{m1}\vec{b}_m](./images/92ad61c6da9bd08cc09100e2ad9d5a1fd41f823c.png)

for some coefficients ![c_{11}, c_{21}, \ldots, c_{m1}](./images/61972630ae579062a1af3fdbcdaaf5fe91b0a95e.png). Similarly, the other output vectors ![T(\hat{e}_j)](./images/a504bb6f4801515599287ddf656242e818f38a8b.png) can be expressed as components with respect to the basis ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png), ![T(\hat{e}_j)=(c_{1j}, c_{2j}, \ldots, c_{mj})^\sfT_{B_W}](./images/1e3fb83337bbb012461bf06e1b25fec848fe2452.png).

We’re now in a position to find the matrix representation ![\!\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}](../Images/3401dfce825d454c6a48a24f481b72575d31d13a.png) of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png), with respect to the input basis ![B_V](./images/b34e40af7663e726b4e1eb9cd5ef93b05e45a47e.png) and the output basis ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png):

![\; \tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}
=
\tensor[_{B_W}]{
\begin{bmatrix}
c_{11} & c_{12} & \cdots 	& c_{1n}	\\
c_{21} & c_{22} & \cdots 	& c_{2n}	\\
\vdots &		 & 		& \vdots 	\\
c_{m1} & c_{m2} & \cdots 	& c_{mn}	\\
\end{bmatrix}
}{_{B_V}}
\; 
\in \mathbb{R}^{m \times n}.](../Images/16234553160b3ee6dcf5d56b6e2dff9a67029b30.png)

The action of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) on a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is the same as the product of ![\!\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}](../Images/3401dfce825d454c6a48a24f481b72575d31d13a.png) and the vector of components ![\tensor{\left[\vec{v}\right]}{_{B_V}}=(v_1,v_2,\ldots,v_n)^\sfT_{B_V}](../Images/84a0b8b4f0571b192b3b694614cec5baebf036cc.png):

![\left[ T(\vec{v})\right]_{B_W} 
= \tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}
\tensor{\left[\vec{v}\right]}{_{B_V}}.](../Images/7b86678811a56cdb2d662aa6a468278cfc24ec52.png)

You may feel this example has stretched the limits of your attention span, but bear in mind, these nitty-gritty details hold the meaning of matrix entries. If you can see how the _positions_ of the entries in the matrix encode the information about ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) and the choice of bases ![B_V](./images/b34e40af7663e726b4e1eb9cd5ef93b05e45a47e.png) and ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png), you’re well on your way to getting it. The entry ![c_{ij}](./images/7ea84843068c73cace02ad6f2a02e61951a9026e.png) in the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th row and ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th column in the matrix ![\!\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}](../Images/3401dfce825d454c6a48a24f481b72575d31d13a.png) is the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th component (with respect to ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png)) of the output of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) when the input is ![\hat{e}_j](./images/6b4e0a6c86897c9536ab6ed7efc33062b7164b32.png).

Let’s verify that the matrix representation ![\!\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}](../Images/3401dfce825d454c6a48a24f481b72575d31d13a.png) correctly predicts the output of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) for the input ![\vec{v} = 5\hat{e}_1 + 6\hat{e}_2=(5,6,0,\ldots)^\sfT_{B_V}](./images/dfe75bdce19e317827c00b05f3bf8929ae0df519.png). Using the linearity of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png), we know the correct output is ![T(\vec{v}) = T(5\hat{e}_1 + 6 \hat{e}_2) = 5T(\hat{e}_1) + 6 T(\hat{e}_2)](./images/8f5a0cc1f4cc08bfe9811e2cc7f669b207980d50.png). We can verify that the matrix-vector product ![\!\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}} \tensor{\left[\vec{v}\right]}{_{B_V}}](../Images/d42f370ffe9567b3580cb9a4d0b35777698786c2.png) leads to the same answer:

![\begin{align*}
\begin{bmatrix}
c_{11} & c_{12} & \cdots 	& c_{1n}	\\
c_{21} & c_{22} & \cdots 	& c_{2n}	\\
\vdots &		 & 		& \vdots 	\\
c_{m1} & c_{m2} & \cdots 	& c_{mn}	\\
\end{bmatrix}
\!\!
\begin{bmatrix}
5 \\ 6 \\ 0 \\ \vdots
\end{bmatrix} \!
=
5\!\begin{bmatrix} c_{11} \\ c_{21} \\ \vdots \\ c_{m1} \end{bmatrix}
+
6\!\begin{bmatrix} c_{12} \\ c_{22} \\ \vdots \\ c_{m1} \end{bmatrix} \!
= 5T(\hat{e}_1) + 6 T(\hat{e}_2).
\end{align*}](./images/4f44d085edfc20db305009d35dc1d5df4ebedcfc.png)

###[Change of basis for matrices](./Front matter.md)

Given the matrix representation ![\!\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}](../Images/3401dfce825d454c6a48a24f481b72575d31d13a.png) of the linear transformation ![T:V \to W](./images/6f6abcb4c10a6a13779cdad441002ebe2bfb94ea.png), you’re asked to find the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to different bases ![B^\prime_V](./images/1517e0085a471e6969189ff9db58761277c31392.png) and ![B^\prime_W](./images/3e6bbdae9d229e065fbc683488c01049fcca7ecc.png). This is the _change-of-basis_ task for matrices.

We’ll discuss the important special case where the input space and the output space of the linear transformation are the same. Let ![T:V \to V](./images/f17409b3d23d5cc5812f5d4ec80af6a8f0b27cbe.png) be a linear transformation, and let ![B=\{ \hat{e}_1, \hat{e}_2, \ldots, \hat{e}_n \}](./images/5f09ec874b543c3bd540d193ec13851044a04c46.png) and ![B^\prime=\{ \hat{e}^\prime_1, \hat{e}^\prime_2, \ldots, \hat{e}^\prime_n \}](./images/3489aa5fd19eaf68d1cd6f71106b56fee42562df.png) be two bases for the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png).

Recall the change-of-basis matrix ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/b3068d47a22daef194cb14735750ffa22f484a70.png) that converts vectors from ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) coordinates to ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) coordinates, and its inverse ![\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/1a734635c91bfad2c510fd7637a4502e2ac1ea24.png), which converts vectors from ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) coordinates to ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) coordinates:

![\tensor{\left[\vec{v}\right]}{_{B^\prime}} 
= 	\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}} \!
\tensor{\left[\vec{v}\right]}{_{B}}
\qquad \; \textrm{and} \qquad \; 
\tensor{\left[\vec{v}\right]}{_{B}} 
= 	\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}} \!
\tensor{\left[\vec{v}\right]}{_{B^\prime}}.](../Images/267982d0d627415f56d720deed4e034f2ec596f0.png)

A clarification of notation is in order. The change-of-basis matrix ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/b3068d47a22daef194cb14735750ffa22f484a70.png) is not equal to the identity matrix ![\mathbbm{1}_n](./images/75629c9993d58a0c3a38b8cb4bcecca2310baf62.png). However, the change-of-basis operation is _logically_ equivalent to an identity transformation: the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) doesn’t change—only its coordinates change. If you don’t remember the change-of-basis operation for vectors, now’s the time to flip back to[Section 4.3.7](./Chapter 4_ Geometric aspects of linear algebra.md) (page 4.3.7) and review before continuing.

Given the matrix representation ![\tensor[_{B}]{\left[M_T\right]}{_{B}}](../Images/d08ccfc9e7da7d58678ca11fb56ad98e9a123121.png) of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), we want to find the matrix ![\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}](../Images/719ea1111f36bb97d59e253e5debcc3eba220a9d.png), which is the representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png). The computation is straightforward. Perform the change-of-basis operation on the input and output vectors:

![\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}  \;  
=  \;	\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}} \!
\tensor[_{B}]{\left[M_T\right]}{_{B}}  \!
\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}.](../Images/d3666b95505d29cab8f80e45cc62c0c18f421307.png)

This group of three matrices is interpreted as follows. Imagine an input vector ![[\vec{v}]_{B^\prime}](../Images/b64d5488c31ca6787f2c25d5a6133d547784e921.png) multiplying the three matrices ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}} \!
\tensor[_{B}]{\left[M_T\right]}{_{B}}  \!
\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/a8caaf7bfbaff9c009e51628b004bc57010f5f6f.png) from the right. In the first step, ![\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/1a734635c91bfad2c510fd7637a4502e2ac1ea24.png) converts the vector from the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) to the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) so the matrix ![\!\tensor[_{B}]{\left[M_T\right]}{_{B}}](../Images/329ad4eabeb8473cdcee59b31d00979c34052824.png) can be applied. In the last step, the matrix ![_{B^\prime}[\mathbbm{1}]_{B}](../Images/22118f361c19dc13119fb50488d1ef14c2a13bed.png) converts the output of ![\!\tensor[_{B}]{\left[M_T\right]}{_{B}}](../Images/329ad4eabeb8473cdcee59b31d00979c34052824.png) to the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png). The combined effect of multiplying by this specific arrangement of three matrices is the same as applying ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) to the input vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png):

![\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}} \!
\tensor[_{B}]{\left[M_T\right]}{_{B}}  \!
\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}
\! \tensor{\left[\vec{v}\right]}{_{B^\prime}}		
=  \tensor{\left[T(\vec{v})\right]}{_{B^\prime}},](../Images/3d42b1b9a1176b4ac1ad80f13b31ce59c74ef791.png)

which means

![\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}
=
\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}} \!
\tensor[_{B}]{\left[M_T\right]}{_{B}}  \!
\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}.](../Images/b4b0e4fafba1f0775f45aac5746f8d9958d983ab.png)

This formula makes sense intuitively: to obtain a matrix with respect to a different basis, we must surround it by appropriate change-of-basis matrices.

Note the touching dimensions of the matrices are expressed with respect to the same basis. Indeed, we can think of the change-of-basis matrices as adaptors we use to express vectors in different bases. The change-of-basis operation for matrices requires two adaptors; one for the input space and one for the output space.

###[Similarity transformation](./Front matter.md)

It’s interesting to note the abstract mathematical properties of the operation used above. Consider any matrix ![N \in \mathbb{R}^{n\times n}](./images/1c8e476620e6468487ef487725ba70b810a21ca0.png) and an invertible matrix ![P \in \mathbb{R}^{n\times n}](./images/1c8dec7a187408a4d3c91ae46a70e337c083f406.png). Define ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) to be the result when ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) is multiplied by ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) on the left and by the inverse ![P^{-1}](./images/673110cb74e9c6dd7ef57248c5d46cbb35f61993.png) on the right:

![M = P N P^{-1}.](./images/ae7d9fc6e4b916bebbb4ea27cdce134999f6a57d.png)

We say matrices ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) and ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) are related by a _similarity transformation_.

Since the matrix ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) is invertible, its columns form a basis for the vector space ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png). Thus, we can interpret ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) as a _change-of-basis_ matrix that converts the standard basis to the basis of the columns of ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png). The matrix ![P^{-1}](./images/673110cb74e9c6dd7ef57248c5d46cbb35f61993.png) corresponds to the inverse change-of-basis matrix. Using this interpretation, the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) corresponds to the _same_ linear transformation as the matrix ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png), but is expressed with respect to the basis ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png).

Similarity transformations preserve certain properties of matrices:

-   Trace: ![\textrm{Tr}\!\left( M \right)  = \textrm{Tr}\!\left( N \right)](./images/246c09678932a7070e0c77876b8d974525b1052c.png)
-   Determinant: ![\textrm{det}\!\left( M \right)  = \textrm{det}\!\left( N \right)](./images/4341d815bdca5decbeca9ec55dbab3239a38dbbe.png)
-   Rank: ![\textrm{rank}\!\left( M \right)  = \textrm{rank}\!\left( N \right)](./images/3af30b2053253c3615d460a10beeaf447059b2cc.png)
-   Eigenvalues: ![\textrm{eig}\!\left( M \right)  = \textrm{eig}\!\left( N \right)](./images/b334f9064176b3daad29618bc9df903bfa2faa78.png)

Together, the trace, the determinant, the rank, and the eigenvalues of a matrix are known as the invariant properties of the matrix because they don’t depend on the choice of basis.

###[Exercises](./Front matter.md)

E5.7 Suppose you’re given the matrix representation of a linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png): ![\!\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}](../Images/f461417616d8a82b56141ceb0376ca0af92e32dd.png). What formula describes the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)?

E5.8 Consider the linear transformation ![T(x,y) = (3x,y)](./images/6083f1d9bc23c82c1dac1641ab1cffdaa9636622.png), which represents a stretching by a factor of three along the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis. Find the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to the following bases.

1.  The standard basis ![B_s = \{ (1,0), (0,1) \}](./images/7ed3895543be801cd2110c68ecb0ae599ec8326a.png)
2.  The flipped basis ![B_{\!f} = \{ (0,1), (1,0) \}](./images/e3db33ec5773f18176c3fb8d753cda013104e549.png)
3.  The diagonal basis ![B_d = \{ (\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}}), (\frac{1}{\sqrt{2}},-\frac{1}{\sqrt{2}}) \}](./images/4d204f9a444bab9ed2bb9e19e35cc7ec512627db.png)

E5.9 You asked your lab assistant to compute the outputs of a list of vectors ![\vec{x}_i](./images/bc3acdc5b7336eb352b49cea75260879bfc271e1.png) when passed through the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). You specified the vectors in the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). Unfortunately, your lab assistant made a mistake and used a different basis ![B'](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png), applying the matrix ![\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}](../Images/719ea1111f36bb97d59e253e5debcc3eba220a9d.png) to the vectors, and obtaining the wrong outputs ![\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}} = \!
\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}
\tensor{\left[\vec{x}_i\right]}{_{B}}](../Images/6c413dd89297edd22e4af7ed9a2cbff22daa97fa.png). To make things worse, your assistant deleted the original data ![\vec{x}_i](./images/bc3acdc5b7336eb352b49cea75260879bfc271e1.png)! “No worries,” you say. “Since the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is invertible, we can recover the data.” What sequence of operations will recover ![\vec{x}_i](./images/bc3acdc5b7336eb352b49cea75260879bfc271e1.png) from ![\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}}](../Images/4bf7656e9b1a8b5404ac13d866fa1bbd767490d6.png)? What sequence of operations will convert ![\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}}](../Images/4bf7656e9b1a8b5404ac13d866fa1bbd767490d6.png) into the correct output ![\tensor{\left[ \vec{y}_i \right]}{_{B}}](../Images/3b58aa2d31215bbae4fdeab5927a35fc5875cdcb.png)?

##[5.4 Invertible matrix theorem](./Chapter 5_ Linear transformations.md)

So far, we discussed systems of linear equations, matrices, vector spaces, and linear transformations. It’s time to tie it all together! We’ll now explore connections between these different contexts where matrices are used. Originally, we saw how matrices can be used to solve systems of linear equations. Later, we studied geometric properties of matrices, including their row spaces, column spaces, and null spaces. We also learned about the connection between matrices and linear transformations. In each of these domains, _invertible_ matrices play a particularly important role. Lucky for us, there’s a theorem that summarizes 10 important facts about invertible matrices. One theorem; 10 facts. Now that’s a good deal!

\[Invertible matrix theorem\]

For an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), the following statements are equivalent:

1.  ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible
2.  The equation ![A\vec{x} = \vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) has exactly one solution for each ![\vec{b} \in \mathbb{R}^n](./images/c82ba4c9cd4dcf777248fec63f56d2f2e7e37766.png)
3.  The null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) contains only the zero vector ![\mathcal{N}(A)=\{\vec{0}\}](./images/4a0f833076b6035d08158e9dc8d1c755007e1973.png)
4.  The equation ![A\vec{x} = \vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png) has only the trivial solution ![\vec{x}=\vec{0}](./images/e2ac4820c2d5a479c68437ed56af13dcb5e7e17d.png)
5.  The columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png):
    -   The columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are linearly independent
    -   The columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) span ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png); ![\mathcal{C}(A)=\mathbb{R}^n](./images/a318c2f0ee0d4c6a5aada79495f4450734481e28.png)
6.  The rank of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)
7.  The RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is the ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) identity matrix ![\mathbbm{1}_n](./images/75629c9993d58a0c3a38b8cb4bcecca2310baf62.png)
8.  The transpose matrix ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png) is invertible
9.  The rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png):
    -   The rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are linearly independent
    -   The rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) span ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png); ![\mathcal{R}(A)=\mathbb{R}^n](./images/b64bce6f49c683b0c72732ed3e6099502c15744a.png)
10.  The determinant of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is nonzero ![\mathrm{det}(A) \neq 0](./images/49d38fd4671f94fd104ae1a28a0a81ff4ed4f623.png)

thm-invertible\_matrix\_thm

These 10 statements are either all true or all false for any given matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). We can split the set of ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrices into two disjoint subsets: invertible matrices, for which all 10 statements are true, and non-invertible matrices, for which all statements are false.

###[Proving the invertible matrix theorem](./Front matter.md)

It’s essential that you understand the details of this theorem, including its proof. The reasoning that connects these 10 statements unites all the chunks of linear algebra we’ve discussed. Not being a “proof person” is not a valid excuse! Be sure to read the proof, as it will help to solidify your understanding of the material covered thus far.

####[Proofs by contradiction](./Front matter.md)

Since our arrival at the invertible matrix theorem marks an important step, we’ll first quickly review some handy proof techniques, just to make sure everyone’s ready. A _proof by contradiction_ starts by assuming the opposite of the fact we want to prove, and after several derivation steps arrives at a contradiction—a mathematical inconsistency. Arriving at a contradiction implies our original premise is false, which means the fact we want to prove is true. Thus, to show that (A) implies (B)—denoted (A)![\Rightarrow](./images/0951fb700bed96c1c96903f848d5e8c404bd8408.png)(B)—we can show that not-(B) implies not-(A).

####[Review of definitions](./Front matter.md)

To really make sure we’re all on board before the train leaves the station, it’s wise to review some definitions from previous chapters. The matrix ![A\in \mathbb{R}^{n\times n}](./images/2f056442410016d3a541715471950849562de0c4.png) is _invertible_ if there exists a matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) such that ![AA^{-1} = \mathbbm{1}_n= A^{-1}A](./images/aa82bb551b53d6854b2b54a6225a742b9c28832f.png). The _null space_ of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is the set of vectors that become the zero vector when multiplying ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) from the right: ![\{ \vec{v} \in \mathbb{R}^n \, | \, A\vec{v} = \vec{0} \}](./images/1e84e2718d2f10aa2a6693865a66aa7d814e93c3.png). The _column space_ ![\mathcal{C}(A)\subseteq \mathbb{R}^n](./images/cbc8e8b8281304062931a0793290ba799fdaafa3.png) consists of all possible linear combinations of the columns of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Similarly, the _row space_ ![\mathcal{R}(A)\subseteq \mathbb{R}^n](./images/e73395da1c28e3ea0b970505447575e448acf20c.png) consists of all possible linear combinations of the rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). The _rank_ of a matrix, denoted ![\textrm{rank}(A)](./images/ed9af0029991b2f3fe54ea738272a568e5f5880a.png), is equal to the dimension of the row space and the column space ![\textrm{rank}(A) = \dim(\mathcal{C}(A)) = \dim(\mathcal{R}(A))](./images/4b8953db50ece86bafec04e5012b2becaf2c0488.png). The rank of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is also equal to the number of pivots (leading ones) in the reduced row echelon form of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). The _determinant_ of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) corresponds to the _scale factor_ by which the linear transformation ![T_A(\vec{x}) = A\vec{x}](./images/2f3847c88f1c8b24c3600fb2438ca44b880e5269.png) transforms the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional volume of the hyper-cube in the input space when it maps it to the output space. If any of the columns of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are linearly dependent, the determinant ![|A|](./images/f395085915c0b82f3f55aa5551b1676f28378881.png) will be zero.

Now tell me, do you feel ready to board the train? Don’t worry too much if some of the above definitions about matrices and vector spaces are still unclear for you. The whole point of this theorem is to solidify your understanding by demonstrating how the concepts you understand less are connected to the concepts you understand well.

\[Proof of the invertible matrix theorem\] The moment has arrived: we’ll prove the equivalence of the 10 statements in the theorem by showing a closed chain of implications between statements ![(\mathbf{1})](./images/6e0f8348c84e7c46b5216c4fa8989269492f3207.png) through ![(\mathbf{7})](./images/02fd5cdc53c29894770f6df83889d5877f67356f.png). We’ll separately show the equivalences ![(\mathbf{1}) \Leftrightarrow (\mathbf{8}) \Leftrightarrow (\mathbf{9})](./images/d8ab44a0c0043f943b5244267a3e9fcea1b339eb.png) and ![(\mathbf{5})  \Leftrightarrow (\mathbf{10})](./images/ae226e3ef28a9487f029b1157f6137a2e714831d.png).[Figure 5.12](./Chapter 5_ Linear transformations.md) shows an outline of the proof.

![inv_mat_thm_proof_implications_graph](./images/inv_mat_thm_proof_implications_graph.png)

Figure 5.12: The chain of implications used to prove the invertible matrix theorem.

**(1)**![\Rightarrow](./images/0951fb700bed96c1c96903f848d5e8c404bd8408.png)**(2)**: Assume ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible so there exists an inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) such that ![A^{-1}A=\mathbbm{1}_n](./images/8c0d7aebb2037804ffb8a90743783ccc19a9f8be.png). Therefore, for all ![\vec{b} \in \mathbb{R}^n](./images/c82ba4c9cd4dcf777248fec63f56d2f2e7e37766.png), the expression ![\vec{x}=A^{-1}\vec{b}](./images/0d62d34451b4b14be91c26e3a018d61ca1d9b6c0.png) is a solution to the equation ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png). We must show the solution ![\vec{x}=A^{-1}\vec{b}](./images/0d62d34451b4b14be91c26e3a018d61ca1d9b6c0.png) is the unique solution to this equation. Suppose that another solution ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png) exists such that ![A\vec{y}=\vec{b}](./images/0a6a75e2b9d978a71ce720125a5cf5c9927620ae.png). Multiplying both sides of the equation ![A\vec{y}=\vec{b}](./images/0a6a75e2b9d978a71ce720125a5cf5c9927620ae.png) by ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png), we obtain ![A^{-1}A\vec{y}=\vec{y}=A^{-1}\vec{b}](./images/9bae392819b49a06dd97044fb6170873356916c0.png), which shows that ![\vec{y} = \vec{x}=A^{-1}\vec{b}](./images/e6f5cfe0671f1a98d042a2e66dbfa10ddf964098.png), and so ![\vec{x}=A^{-1}\vec{b}](./images/0d62d34451b4b14be91c26e3a018d61ca1d9b6c0.png) is the unique solution to ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png).

**(2)**![\Rightarrow](./images/0951fb700bed96c1c96903f848d5e8c404bd8408.png)**(3)**: We want to show that a unique solution to ![A\vec{x} =\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) implies the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has a trivial null space ![\mathcal{N}(A)=\{\vec{0}\}](./images/4a0f833076b6035d08158e9dc8d1c755007e1973.png). We start by assuming the opposite is true: that ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png) contains at least one nonzero vector ![\vec{y} \neq 0](./images/b5f726031fd471af3f21a7315024b27898851633.png). If this were true, then ![\vec{x}^\prime = \vec{x}+\vec{y}](./images/4f5b090a7bc4f2d62492410c7ea4108ccb920115.png) would also be a solution to ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png), since ![A\vec{x}^\prime = A(\vec{x}+\vec{y})=A\vec{x}+ A\vec{y} 				=A\vec{x}+\vec{0}=\vec{b}](./images/1b1f437469928a97c77bb9ddf4e7505993852c5a.png), since ![A\vec{y}=\vec{0}](./images/0b67e0c1876e174bf5257194f48d107fe87681b7.png). The fact that two solutions (![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) and ![\vec{x}^\prime \neq \vec{x}](./images/be95dab507bd010e76274e6589ce5c8db7a8d590.png)) exist contradicts the statement that ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) has a unique solution. Thus, for ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) to have a unique solution, ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) must have a trivial null space ![\mathcal{N}(A)=\{\vec{0}\}](./images/4a0f833076b6035d08158e9dc8d1c755007e1973.png).

**(3)**![\Rightarrow](./images/0951fb700bed96c1c96903f848d5e8c404bd8408.png)**(4)** Statements ![(\mathbf{3})](./images/32204c7c461c321ab668871635144daeba7bb705.png) and ![(\mathbf{4})](./images/191132ec832966f0ccd7225c617928b093ac3488.png) are equivalent by definition: the condition that ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)’s null space contains only the zero vector, ![\mathcal{N}(A)=\{\vec{0}\}](./images/4a0f833076b6035d08158e9dc8d1c755007e1973.png), is equivalent to the condition that the only solution to the equation ![A\vec{v}=\vec{0}](./images/dd0654eddf8afc1a3d57a47b36dc528c6fea569a.png) is ![\vec{v}=\vec{0}](./images/3a2b014779b24212b450f004534ba2509246caef.png).

**(4)**![\Rightarrow](./images/0951fb700bed96c1c96903f848d5e8c404bd8408.png)**(5)**: Analyze the equation ![A\vec{v}=\vec{0}](./images/dd0654eddf8afc1a3d57a47b36dc528c6fea569a.png) in the column picture of matrix multiplication, denoting the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as ![\vec{c}_1, \vec{c}_2, \ldots, \vec{c}_n](./images/3ca02b5b186112d6a126ee5f01529dda8ade3601.png). We obtain ![A\vec{v} = v_1\vec{c}_1 + v_2\vec{c}_2 + \cdots + v_n\vec{c}_n = \vec{0}](./images/d33407a552cd28ab75b9063c117e2547ca8fdb04.png). Since ![\vec{v} = (v_1,v_2,\ldots,v_n)=\vec{0}](./images/58a2d035668831c83d3b4cf505ffa9d873da5256.png) is the only solution to this equation, we obtain the statement in the definition of linear independence for a set of vectors. The fact that ![A\vec{v}=\vec{0}](./images/dd0654eddf8afc1a3d57a47b36dc528c6fea569a.png) has only ![\vec{v}=\vec{0}](./images/3a2b014779b24212b450f004534ba2509246caef.png) as a solution implies the columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a linearly independent set. Furthermore, the columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) because they are a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors in an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space.

**(5)**![\Rightarrow](./images/0951fb700bed96c1c96903f848d5e8c404bd8408.png)**(6)**: We know ![\textrm{rank}(A)](./images/ed9af0029991b2f3fe54ea738272a568e5f5880a.png) equals the number of linearly independent columns in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Since the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are linearly independent, it follows that ![\textrm{rank}(A)=n](./images/c4ab2a5b53976f6fedc430a946537b609088d0a4.png).

**(6)**![\Rightarrow](./images/0951fb700bed96c1c96903f848d5e8c404bd8408.png)**(7)**: The rank is equal to the number of leading ones (pivots) in the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Since ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has rank ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png), its reduced row echelon form must contain ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) pivots. The reduced row echelon form of an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix with ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) pivots is the identity matrix ![\mathbbm{1}_n](./images/75629c9993d58a0c3a38b8cb4bcecca2310baf62.png).

**(7)**![\Rightarrow](./images/0951fb700bed96c1c96903f848d5e8c404bd8408.png)**(1)**: We start from the assumption ![\textrm{rref}(A)=\mathbbm{1}_n](./images/517237fa451d76e0729cd4919130ebb65fd21702.png). This means it’s possible to use a set of row operations ![\mathcal{R}_1, \mathcal{R}_2, \ldots, \mathcal{R}_k](./images/5090f932d13d1a13a32ba8b3ed3b0730909f86d3.png) to transform ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) to the identity matrix: ![\mathcal{R}_k(\cdots \mathcal{R}_2(\mathcal{R}_1(A))\cdots)=\mathbbm{1}_n](./images/77483799eb9a436677b07b630c1534a12a2eb6b4.png). Consider the elementary matrices ![E_1, E_2, \ldots, E_k](./images/330ccbff0f53debb3e5c4c2ff0041ce89958f601.png) that correspond to the row operations ![\mathcal{R}_1, \mathcal{R}_2, \ldots, \mathcal{R}_k](./images/5090f932d13d1a13a32ba8b3ed3b0730909f86d3.png). Rewriting the equation ![\mathcal{R}_k(\cdots \mathcal{R}_2(\mathcal{R}_1(A))\cdots)=\mathbbm{1}_n](./images/77483799eb9a436677b07b630c1534a12a2eb6b4.png) in terms of these elementary matrices gives us ![E_k\cdots E_2E_1A=\mathbbm{1}_n](./images/824e7c2bd4d148182114d146a8b9c749f1db4c41.png). This equation implies the inverse of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) exists and is equal to the product of elementary matrices ![A^{-1} = E_k\cdots E_2E_1](./images/9e0b34fe241fd87c2cfa6db93f75ddb06be6e908.png).

**(1)**![\Leftrightarrow](./images/4d453510cfb01bcef19996e2421ed9bfabb8333f.png)**(8)**: If ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible, there exists ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) such that ![AA^{-1}=\mathbbm{1}_n](./images/75514a5b6cd38696543208ae58b4867ee6e9d87e.png). If we apply the transpose operation to this equation, we obtain

![(AA^{-1})^\sfT=(\mathbbm{1}_n)^\sfT 
\qquad
\Rightarrow
\qquad
(A^{-1})^\sfT A^\sfT = \mathbbm{1}_n,](./images/89196a1a903a90aa948953c1cc769cda20b9b2ff.png)

which shows the matrix ![(A^{-1})^\sfT = (A^\sfT)^{-1}](./images/b2308b2b755741cf2d0629cd07de7e866b7b2d65.png) exists and is the inverse of ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png). Therefore, ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible if and only if ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png) is invertible.

**(8)**![\Leftrightarrow](./images/4d453510cfb01bcef19996e2421ed9bfabb8333f.png)**(9)**: Statement ![(\mathbf{9})](./images/06c3ce54f1ddb4e31899d88aced4c55e527dc078.png) follows by a combination of statements ![(\mathbf{8})](./images/8c5a3e8a484fb1c6f93a962eca07525a0bd93409.png) and ![(\mathbf{5})](./images/da27ce068f3c3280611f4163ba86b70cf5fe7f0f.png): if ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png) is invertible, its columns form a basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png). Since the columns of ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png) are the rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), it follows that the rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png).

**(5)**![\Leftrightarrow](./images/4d453510cfb01bcef19996e2421ed9bfabb8333f.png)**(10)**: The determinant of an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix is nonzero if and only if the columns of the matrix are linearly independent. Thus, the columns of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) form a basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) if and only if ![\det(A) \neq 0](./images/69633a1b936d0299a2d93cf1e2aada740f28d697.png).

Nice work! By proving the chain of implications ![(\mathbf{1})\Rightarrow(\mathbf{2})\Rightarrow\cdots \Rightarrow(\mathbf{7})\Rightarrow(\mathbf{1})](./images/fea4a0f3a1080168ada7bb073277f8a07a36a426.png), we’ve shown that the first seven statements are equivalent. If one of these statements is true, then all others are true—just follow the arrows of implication. Alternatively, if one statement is false, all statements are false, as we see by following the arrows of implication in the backward direction.

We also “attached” statements ![(\mathbf{8})](./images/8c5a3e8a484fb1c6f93a962eca07525a0bd93409.png), ![(\mathbf{9})](./images/06c3ce54f1ddb4e31899d88aced4c55e527dc078.png), and ![(\mathbf{10})](./images/3732cb3a8dc027d485bff3eb03bf1376082fded6.png) to the main loop of implications using “if and only if” statements. Thus, we’ve shown the equivalence of all 10 statements, which completes the proof.

The steps of the proof shown above cover only a small selection of all possible implications between the 10 statements. In a few pages, you’ll reach the exercises and you’ll be asked to prove several other implications. It’s important to try these exercises on your own! By checking whether you can obtain the proofs, you’ll force your brain to truly grasp the definitions and properties of linear algebra concepts. Note the crucial difference between _one-way_ implications of the form ![(\mathbf{A})\Rightarrow(\mathbf{B})](./images/2045539f36254a13934e9853ca805554c92f9688.png) and _if and only if_ statements ![(\mathbf{A})\Leftrightarrow(\mathbf{B})](./images/d763ba358080a041042819efbdff4e4a4150a09c.png). The latter require you to prove both directions of the implication: ![(\mathbf{A})\Rightarrow(\mathbf{B})](./images/2045539f36254a13934e9853ca805554c92f9688.png) and ![(\mathbf{A})\Leftarrow(\mathbf{B})](./images/9afdc34600adb614c866cb10dfb10d8dbe9bda45.png).

###[Invertible linear transformations](./Front matter.md)

We can reinterpret the statements in the invertible matrix theorem as a statement about _invertible linear transformations_:

![T\colon \mathbb{R}^n \to \mathbb{R}^n \textrm{ is invertible}		
\quad \Leftrightarrow \quad
M_T \in \mathbb{R}^{n \times n} \textrm{ is invertible.}](./images/b919c25a4172e513f7da482228c22767480a81c9.png)

The set of linear transformations splits into two disjoint subsets; invertible linear transformations and non-invertible linear transformations.

####[Kernel and null space](./Front matter.md)

The _kernel_ of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is the same as the null space of its matrix representation ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png). Recall statement ![(\mathbf{3})](./images/32204c7c461c321ab668871635144daeba7bb705.png) of the invertible matrix theorem: a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible if and only if its null space contains only the zero vector ![\mathcal{N}(A) = \{ \vec{0} \}](./images/4a0f833076b6035d08158e9dc8d1c755007e1973.png). The equivalent condition for linear transformations is the zero kernel condition. A linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is invertible if and only if its kernel contains only the zero vector:

![T   \textrm{ is invertible}
\quad \Leftrightarrow \quad
\textrm{Ker}(T) =\{ \vec{0} \}.](./images/b948a66f498aff8a0d659437b2af480106a41a3f.png)

Invertible linear transformations ![T:\mathbb{R}^n \to \mathbb{R}^n](./images/fe26a7013168d5d82fcf565264d7b0cbeda5aca9.png) map different input vectors ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) to different output vectors ![\vec{y} = T(\vec{v})](./images/bbf1c798ef8edb6ec26f0e419fa93c5eeb219529.png); therefore it’s possible to build an inverse linear transformation ![T^{-1}:\mathbb{R}^n \to \mathbb{R}^n](./images/b9e6c795f4c60103d462ed29124cd50fcc923d84.png) that restores every ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png) back to the ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) it came from.

In contrast, a non-invertible linear transformation ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) sends all vectors ![\vec{x} \in \textrm{Ker}(S) \neq \{\vec{0}\}](./images/5f978c9d054d7db70c35254191a067bb8fef9870.png) to the zero vector ![S(\vec{x})=\vec{0}](./images/71e8589ece0863385a37c7f5d9033fadfe058f5b.png). When this happens, there is no way to undo the action of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png), since we can’t determine the input ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) that ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) sent to ![\vec{0}](./images/65166afafe3ddf1f84ea3e171c71602a0cc52b15.png).

####[Linear transformations as functions](./Front matter.md)

In[Section 1.8](./Chapter 1_ Math fundamentals.md), we discussed the notion of _invertibility_ for functions of a real variable, ![f:\mathbb{R} \to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png). In particular, we used the terms _injective_, _surjective_, and _bijective_ to describe how a function maps different inputs from its domain to outputs in its target set (see page 1.8.1). Since linear transformations are functions, we can apply the general terminology for functions to describe how linear transformations map different inputs to outputs.

A linear transformation is _injective_ if it maps different inputs to different outputs:

![T(\vec{v}_1) \neq T(\vec{v}_2)  \textrm{ for all } \vec{v}_1 \neq \vec{v}_2
\quad \Leftrightarrow \quad
T   \textrm{ is \emph{injective}}.](./images/eba02e80b24ff9f198e8e7be65fdc4b55cd5a6d2.png)

A linear transformation ![T:\mathbb{R}^n \to \mathbb{R}^m](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png) is _surjective_ if its image space equals its output space:

![\textrm{Im}(T) = \mathbb{R}^m
\quad \Leftrightarrow \quad				
T  \textrm{ is \emph{surjective}}.](./images/0fa3e1ec274d3320bc810d73543b52d4da935761.png)

The surjective condition for linear transformations is equivalent to the condition that the column space of the matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) spans the outputs space: ![\textrm{Im}(T) = \mathcal{C}(M_T) = \mathbb{R}^m](./images/76c0c5ecee2b4bc146dc26a9a85a560ab2708777.png).

If a function is both injective and surjective then it is _bijective_. Bijective functions are _one-to-one correspondences_ between elements in their input space and elements in their output space.

![T(\vec{x}) = \vec{y} \textrm{ has exactly one solution for each } \vec{y}
\quad \Leftrightarrow \quad
T \textrm{ is \emph{bijective}}.](./images/7c04ab1a7099ebf0b9fa59d4b7672d838767911f.png)

All bijective functions are invertible since each output ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png) in the output space corresponds to exactly one ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) in the input space.

Interestingly, for a linear transformation ![T:\mathbb{R}^n \to \mathbb{R}^n](./images/fe26a7013168d5d82fcf565264d7b0cbeda5aca9.png) to be invertible, the presence of either the injective or surjective property is sufficient. If ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is injective, it must have a ![\textrm{Ker}(T) =\{ \vec{0} \}](./images/fc46f15d47b28882b575aa2a4e7a79cbf031d0a0.png) so it is invertible. If ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is surjective, its matrix representation ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) has rank ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png). The rank–nullity theorem (![\textrm{rank}(M_T) + \textrm{nullity}(M_T) = n](./images/20a18e8ad5124e1fa80ba4e34782fad981128899.png)) tells us ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png) has an empty null space ![\mathcal{N}(M_T) = \textrm{Ker}(T) =\{ \vec{0} \}](./images/bbba680ca415767bd198338bf73cf7ead7cab402.png), making ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) invertible.

###[Links](./Front matter.md)

\[ Nice writeup about the invertible matrix theorem with proofs \]

[`http://bit.ly/InvMatThmProofs2`](./InvMatThmProofs2.md)

\[ Visualization of two-dimensional linear transformations \]

[`http://ncase.me/matrix/`](./matrix.md)

###[Exercises](./Front matter.md)

E5.10 Prove that statement ![(\mathbf{5})](./images/da27ce068f3c3280611f4163ba86b70cf5fe7f0f.png) of the invertible matrix theorem implies statement ![(\mathbf{2})](./images/dbd8127a85c3e116b74cbefee922e8e66880b3ed.png).

E5.11 Prove statement ![(\mathbf{3})](./images/32204c7c461c321ab668871635144daeba7bb705.png) implies statement ![(\mathbf{6})](./images/874875afcd0b167e3bdff3868e2be8309941f76c.png) in the invertible matrix theorem.

Use the rank–nullity theorem from[Chapter 4](./Chapter 4_ Geometric aspects of linear algebra.md) (page 4.4.15).

###[Discussion](./Front matter.md)

In this chapter, we learned about linear transformations and their matrix representations. The equivalence ![T(\vec{x}) = M_T\vec{x}](./images/6eeb05552c087f93a9ea27609a4d94c60e5af6c9.png) is important because it forms a bridge between the abstract notion of a linear transformation and its concrete implementation as a matrix-vector product. Everything you know about matrices can be applied to linear transformations, and everything you know about linear transformations can be applied to matrices. Which is mind-blowing, if you think about it.

We say ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is _represented_ by the matrix ![\tensor[_{B_W}]{\left[M_T\right]}{_{B_V}}](../Images/21e22525b5b5e7cd7c60f91b419268473d9a2290.png) with respect to the basis ![B_V](./images/b34e40af7663e726b4e1eb9cd5ef93b05e45a47e.png) for the input space, and the basis ![B_W](./images/8dca65106aff3b7f14f0f4dc15b79b60893165af.png) for the output space. In[Section 5.2](./Chapter 5_ Linear transformations.md), we learned about the probing procedure for finding matrix representations with respect to the standard basis, while[Section 5.3](./Chapter 5_ Linear transformations.md) discussed the notion of change of basis for matrices. Hold tight, because in the next chapter we’ll learn about the eigenvalues and eigenvectors of matrices and discuss the _eigendecomposition_ of matrices, which is a type of change of basis.

[Section 5.4](./Chapter 5_ Linear transformations.md) gave us the invertible matrix theorem along with a taste of what it takes to prove formal math statements. It’s extra important that you attempt some of the proofs in the exercise section on page 5.4.4. Although proofs can be complicated, they’re so worth your time because they force you to clarify the definitions and properties of all the math concepts you’ve encountered thus far. Attempt the proofs in the problems section to find out if you’re a linear algebra amateur, or a linear algebra expert.

##[5.5 Linear transformations problems](./Chapter 5_ Linear transformations.md)

Understanding linear transformations is extremely important for your overall understanding of linear algebra. This is why it’s crucial for you to solve all the problems in this section. By working on these problems, you’ll discover whether you really understand all the new material covered in this chapter. Remember in the book’s introduction, when I mentioned that linear algebra is all about vectors and linear transformations? Well, if you can solve all the problems in this section, you’re 80% of the way to understanding all of linear algebra.

P5.1 Determine whether each of the following transformations are linear.

1.  ![T_1(x,y)=(y, x+y)](./images/26d06515220f61b91b0b31f6b927988b58449434.png)
2.  ![T_2(x,y)=(x+3, y-3)](./images/3f9bb71039fc89ce38edada54e13e9b1771dc364.png)
3.  ![T_3(x,y)=(|x|, |y|)](./images/41c2b029a697ab5c922cfc9cd1c967cce43970dd.png)
4.  ![T_4(x,y,z)=(3x-2y+z, 2x+y-4z)](./images/8bbf1c71be3585a6d9d42781040e455deb2bcccf.png)
5.  ![T_5(x)=(x,2x,3x)](./images/da1b4c1e3a82148270724b220311832edc2e9211.png)
6.  ![T_6(x,y,z,w)=(5x,4y,3z,2w,1)](./images/ca7ced9f9119b4a759f782c014aaf87e0b91e412.png)

If the transformation is linear, find its matrix representation. If the transformation is nonlinear, show a calculation where the linear property fails.

P5.2 Find image space ![\textrm{Im}(T)](./images/618de22f89981fea204be3b3fca829f4ee31d3e2.png) for the linear transformation ![T: \mathbb{R}^2\to\mathbb{R}^3](./images/6696d8a1bca8035a83a194bee0f43169f7c66d4d.png) defined by ![T(x,y)=(x, x-y, 2y)](./images/1dd2296407a7d9e2105f71663c900f85e126a4bb.png).

P5.3 Consider the transformation defined by ![T(\vec{v}) = \vec{a} \times \vec{v}](./images/9d15d093bd4f29a5cfaeb1ecc69c2048c7ce58fe.png), where ![\vec{a} = (a_x,a_y,a_z)](./images/7232d2f9638325274beefe019d837a7494833b69.png). Find the matrix representation of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png). What is the kernel of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png)?

P5.4 Find the matrix representation of the linear transformation ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) that maps the input vector ![\vec{x}_1=(1,1)^\sfT](./images/2a512430e84ddf29e6eed04637893c0ce29a74ac.png) to the output vector ![\vec{y}_1=(2,-3)^\sfT](./images/b16d56edc6b634c05e5a93a45e8c9ade41d8ba4c.png) and the input vector ![\vec{x}_2=(1,2)^\sfT](./images/eaa0cee0fc5e5cc0574a85ecbc9c22241a8659bc.png) to the output vector ![\vec{y}_2=(5,1)^\sfT](./images/4a13003e1b083eb89d27e5c1c2e43fb53cf5ad7c.png).

This is a nonstandard basis probing question. See page 5.2.7.

P5.5 Given the linear transformation ![T(x,y,z)=(x,x+y,x+y+z)](./images/8ffe1d4e6e40fe7c4797602525c7fe55828d08fa.png), the standard basis for ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png) ![B = \{ (1,0,0), (0,1,0), (0,0,1) \}](./images/47e4d604c00e331cb18b53bcf925df6abc094764.png), and the alternative basis ![B^\prime = \{(1,0,0), (0,1,1), (0,1,-1) \}](./images/b7f23618d33249a303dec96413b5df2ec283aaf5.png), find the following matrix representations of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png):

1.  ![\!\!\tensor[_{B}]{\left[M_T\right]}{_{B}}](../Images/7a3345be78f2ebc1dbef139b04ac049b814bb2a8.png): the representation of ![T](./images/c4c1f26c0069eaa246339e6e021fa11c7dfea81a.png) with respect to the standard basis
2.  ![\!\!\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}](../Images/6b54b8cfc29ff9d0185819274d14f0f99fb55ba6.png): the representation of ![T](./images/c4c1f26c0069eaa246339e6e021fa11c7dfea81a.png) with respect to the basis ![B^\prime](./images/f4cb809b77f306051c36d5a8e887166c5e3c9bda.png) 
3.  ![\!\!\tensor[_{B}]{\left[M_T\right]}{_{B^\prime}}](../Images/005a6f56f02cdcefaabb152460eaa1c64519f8c5.png): the mixed representation of ![T](./images/c4c1f26c0069eaa246339e6e021fa11c7dfea81a.png) with respect to input vectors expressed in the basis ![B^\prime](./images/f4cb809b77f306051c36d5a8e887166c5e3c9bda.png) and output vectors in the standard basis ![B](./images/2d2a619bf252e3464ded96fab589d418adcd3f59.png) 

P5.6 Consider the linear transformation ![T(x,y,z)=(2x-5z,2y,-3z)](./images/02ee0d7a5c18ad9c410b6bb207ed3b9dd162fb84.png). Find the matrix of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) with respect to the basis ![B^\prime\!=\!\{ (1,0,0), (0,1,0), (1,0,1) \}](./images/54588deadbabea455b2af2d058883b0c75aaca4e.png).

P5.7 Find the matrix representations of each of the transformations shown in[Figure 5.13](./Front matter.md). The input to each transformation is the triangle with vertices ![(0,0)](./images/88f092814c075b14ae3942f62ed4da42f8321ec0.png), ![(2,0)](./images/40b6f6b8547473b2b37962617c356013005335ce.png), ![(0,1)](./images/e69b48bc6687ee74a843dea90543682e53e069e3.png) that is shown in[Figure 5.13](./Front matter.md) image (a).

Your answers should be ![2\times 2](./images/8d9f69fe9ab543dc19bd60e8ea565644efbcebb4.png) matrices. Recall that ![\sin(\frac{\pi}{6})=\frac{1}{2}](./images/a46e9aad99287dfa646e0c3e59a931d5d27c691e.png).

![linear_transformations_graphical_question](./images/linear_transformations_graphical_question.png)

Figure 5.13

P5.8 Prove that statement ![(\mathbf{2})](./images/d509fad8ec1697af936f259099b85641a0ad3cb5.png) implies statement ![(\mathbf{1})](./images/9835274db96b32b0d46092df247a317a83f9f606.png) in the invertible matrix theorem.

P5.9 Prove that statements ![(\mathbf{2})](./images/d509fad8ec1697af936f259099b85641a0ad3cb5.png) and ![(\mathbf{4})](./images/1aba5273f622923dff306880cdbad6d219e4c13f.png) of the invertible matrix theorem are equivalent.

P5.10 Prove statement ![(\mathbf{4})](./images/1aba5273f622923dff306880cdbad6d219e4c13f.png) implies statement ![(\mathbf{6})](./images/22c6edda11ba7b29f1d1ae63fa1d37c185e2024d.png) in the invertible matrix theorem.

P5.11 Prove statement ![(\mathbf{4})](./images/1aba5273f622923dff306880cdbad6d219e4c13f.png) implies statement ![(\mathbf{7})](./images/9afb4344a60b87f21755928c7aca3761704a6b75.png) in the invertible matrix theorem.

P5.12 Prove the chain of implications **(1)![\Rightarrow](./images/62dfd3e3def8ef769ca47450ffcb8132b2105a51.png)(7)![\Rightarrow](./images/62dfd3e3def8ef769ca47450ffcb8132b2105a51.png)(10)** in the invertible matrix theorem.

P5.13 Suppose ![T: V \to W](./images/c04aca1f064043fc34d9c907b2bab7d92e7dea2d.png) is an injective linear transformation, and ![\{\vec{v}_1, \ldots, \vec{v}_n\}](./images/74bb0f6d123899dd1a1696a3a856fd92d4694ec6.png) is a linearly independent set in ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png). Prove that ![\{T(\vec{v}_1), \ldots, T(\vec{v}_n)\}](./images/97b7563321663b43fbe1e63311cd428174c56a0f.png) is a linearly independent set in ![W](./images/cf83ddf97823b88ae25eb70438f249f159f02fbf.png).

P5.14 Suppose ![T: V \to W](./images/c04aca1f064043fc34d9c907b2bab7d92e7dea2d.png) is a surjective linear transformation, and the set ![\{\vec{v}_1, \ldots, \vec{v}_n\}](./images/74bb0f6d123899dd1a1696a3a856fd92d4694ec6.png) spans ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png). Prove that the set ![\{T(\vec{v}_1),  \ldots, T(\vec{v}_n)\}](./images/97b7563321663b43fbe1e63311cd428174c56a0f.png) spans ![W](./images/cf83ddf97823b88ae25eb70438f249f159f02fbf.png).

Consider an arbitrary ![\vec{w} \in W](./images/5d599cdfde3efa0f028f483572a70206d5a15c3c.png).

P5.15 Let ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) and ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) be ![n\times n](./images/08e2c13b8fef8a136e869818aa0544678444207a.png) matrices such that ![AB= \mathbbm{1}](./images/c5106705d43e103f4d2d94bedca4c03370087085.png). Show that ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) has rank ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) (full rank) and prove that ![BA= \mathbbm{1}](./images/043298d6b292f59cd4f0270a30f06b54b4e7f966.png).

Use a proof by contradiction to show ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) has full rank, then apply the associative law of matrix multiplication.

[1.](./Front matter.md) Location on a computer screen is denoted using pixel coordinates ![\vec{x}_i=(h_i,v_i)](./images/8d52f055965494b5223738981002b9b60b19338d.png). The number ![h_i](./images/d6ebc99223e8caa9cfd934072f9591557795d97d.png) describes a horizontal distance measured in pixels from the left edge of the image, and ![v_i](./images/abb23a5428dd91d81a0e764b6e1f2924c3cfae81.png) measures the vertical distance from the top of the image.
