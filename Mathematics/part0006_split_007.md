Chapter 6    

##[6.7 Hyperbola](part0006_split_007.md)

The _hyperbola_ is another fundamental shape of nature.

###[Parameters](part0006_split_007.md)

-   ![F_1, F_2](01383.jpeg): the _focal points_ of the hyperbola
-   ![r_1](01384.jpeg): the distance from a point of the hyperbola to ![F_1](01385.jpeg)
-   ![r_2](01386.jpeg): the distance from a point of the hyperbola to ![F_2](01387.jpeg)
-   ![a](00014.jpeg): the semi-major axis of the hyperbola is the distance from the origin to the vertices ![V_1](01388.jpeg) and ![V_2](01389.jpeg)
-   ![b](00074.jpeg): the semi-minor axis of the hyperbola is the distance from a focus to the nearest asymptote
-   ![c](00256.jpeg): the distance of the focal points from the centre. The distance between ![F_1](01385.jpeg) and ![F_2](01387.jpeg) is ![2c](01394.jpeg).
-   ![\varepsilon](01395.jpeg): _eccentricity_ of the hyperbola, ![\varepsilon = \sqrt{1+ \frac{b^2}{a^2} } = \frac{c}{a}](01466.jpeg)

![unit-hyperbola](01467.jpeg)

Figure 6.26: The graph of the unit hyperbola ![x^2-y^2=1](01468.jpeg). The graph has two branches opening to the sides, and its eccentricity is ![\varepsilon=\sqrt{1+\frac{1}{1}}=\sqrt{2}](01469.jpeg).

The graph of a hyperbola consists of two separate _branches_, as illustrated in[Figure 6.26](part0006_split_007.md). The dashed lines are called the _asymptotes_ of the hyperbola. The graph of the hyperbola approaches these lines but never touches them. The equations that describe these asymptotes are ![y=\frac{b}{a}\, x](01470.jpeg) and ![y=-\frac{b}{a}\, x](01471.jpeg).

###[Definition](part0006_split_007.md)

A hyperbola is defined as the set of points such that the absolute value of the difference of the distances to the two focal points is constant:

![|r_1 - r_2| = \text{const}.](01472.jpeg)

Another way to define a hyperbola is as the set of points ![(x,y)](00630.jpeg) that satisfy the equation

![\frac{x^2}{a^2}   - \frac{y^2}{b^2} = 1.](01473.jpeg)

The coordinates of the two focal points of this hyperbola are

![F_1 = (-c,0) \qquad \textrm{and} \qquad F_2 = (c,0),](01402.jpeg)

where the _focal distance_ is ![c = \sqrt{a^2+b^2}](01474.jpeg). The coordinates of the _vertices_ ![V_1](01388.jpeg) and ![V_2](01389.jpeg) are ![(-a,0)](01475.jpeg) and ![(a,0)](01476.jpeg).

The hyperbola’s _eccentricity_ is defined by the equation

![\varepsilon = \sqrt{ 1 + \frac{b^2}{a^2} } = \frac{c}{a}\,.](01477.jpeg)

The eccentricity is a number greater than ![1](00211.jpeg) that determines the hyperbola’s shape. Recall that an ellipse is also defined by an eccentricity parameter, though the formula is slightly different. This could be a coincidence—or is there a connection? Read on to find out.

###[Hyperbolic trigonometry](part0006_split_007.md)

The study of the geometry of the points on the unit circle is called _circular trigonometry_. The geometry of the unit circle is described by the trigonometric functions ![\sin\theta](01118.jpeg) and ![\cos\theta](01119.jpeg). The function ![\cos\theta](01119.jpeg) defines the ![x](00015.jpeg)\-coordinates of the points on the unit circle, and ![\sin\theta](01118.jpeg) defines their ![y](00018.jpeg)\-coordinates. The point ![P=(\cos\theta, \sin\theta)](01478.jpeg) traces the unit circle as the angle ![\theta](00944.jpeg) goes from ![0](00101.jpeg) to ![2\pi](00928.jpeg).

Similarly, the study of the geometry of the unit hyperbola is called _hyperbolic trigonometry_. Doesn’t that sound awesome? Next time your friends ask what you have been up to, tell them you are learning about hyperbolic trigonometry. Whereas we trace the path of the point ![P](00267.jpeg) on the unit circle ![x^2+y^2=1](01199.jpeg), we’ll instead trace the path of a point ![Q](01329.jpeg) on the unit hyperbola ![x^2-y^2=1](01479.jpeg). We’ll now define _hyperbolic_ variants of the ![\sin](00935.jpeg) and ![\cos](00751.jpeg) functions to describe the coordinates of the point ![Q](01329.jpeg).

The coordinates of a point ![Q](01329.jpeg) on the right branch of the unit hyperbola are ![Q=(\cosh\mu,\sinh\mu)](01480.jpeg), where ![\mu](01481.jpeg) is the _hyperbolic angle_. The ![x](00015.jpeg)\-coordinate of the point ![Q](01329.jpeg) is ![x=\cosh \mu](01482.jpeg), and its ![y](00018.jpeg)\-coordinate is ![y=\sinh \mu](01483.jpeg). The name hyperbolic angle is a bit of a misnomer, since ![\mu](01481.jpeg) actually measures an area. The area of the highlighted region in[Figure 6.27](part0006_split_007.md) corresponds to ![\frac{1}{2}\mu](01484.jpeg).

![unit-hyperbola-coshmu-sinhmu](01485.jpeg)

Figure 6.27: The functions ![\cosh\mu](01486.jpeg) and ![\sinh\mu](01487.jpeg) are defined as the ![x](00632.jpeg)\- and ![y](00674.jpeg)\-coordinates of a point moving on the unit hyperbola ![x^2-y^2=1](01468.jpeg).

Recall the circular-trigonometric identity ![\cos^2 \theta + \sin^2 \theta = 1](01235.jpeg), which follows from the fact that all the points ![(x,y)](00630.jpeg) on the unit circle obey ![x^2+y^2=1](01199.jpeg). There is an analogous hyperbolic trigonometric identity:

![\cosh^2 \mu - \sinh^2 \mu = 1.](01488.jpeg)

This identity follows because we defined ![x=\cosh \mu](01482.jpeg) and ![y=\sinh \mu](01483.jpeg) to be the coordinates of a point ![Q](01329.jpeg) which traces out the unit hyperbola ![x^2-y^2=1](01479.jpeg).

The hyperbolic functions are related to the exponential function through the following formulas:

![\cosh \mu = \frac{e^{\mu}  + e^{-\mu}}{2} \,,  \qquad    \sinh \mu = \frac{e^{\mu} - e^{-\mu}}{2} \,,](01489.jpeg)

and

![e^\mu = \cosh \mu + \sinh \mu.](01490.jpeg)

Recall that even functions satisfy ![f(-x)=f(x)](01491.jpeg) and odd functions satisfy ![g(-x)=-g(x)](01492.jpeg). The ![\cosh](01493.jpeg) function is even, while ![\sinh](01494.jpeg) is odd. You can think of ![\cosh x](01495.jpeg) as the “even part” of ![e^x](00589.jpeg), and ![\sinh x](01496.jpeg) as the “odd part” of ![e^x](00589.jpeg).

![hyperbolic-sin-and-cos](01497.jpeg)

Figure 6.28: The graphs of the functions ![\cosh \mu](01486.jpeg) and ![\sinh \mu](01487.jpeg).

Don’t worry about ![\cosh \mu](01498.jpeg) and ![\sinh \mu](01499.jpeg) too much. The hyperbolic trig functions are used much less often than the circular trigonometric functions ![\cos \theta](01119.jpeg) and ![\sin \theta](01118.jpeg). The main thing to remember is the general pattern: cosine functions are used to denote horizontal coordinates and sine functions are used to denote vertical coordinates.

###[The conic sections](part0006_split_007.md)

There is a deep connection between the geometric shapes of the circle, the ellipse, the parabola, and the hyperbola. These seemingly different shapes can be obtained, geometrically speaking, from a single object: the cone. We can obtain the four curves by slicing the cone at different angles, as illustrated in[Figure 6.29](part0006_split_007.md).

![conic_sections_four-shapes](01500.jpeg)

Figure 6.29: Taking slices through a cone at different angles produces different geometric shapes: a circle, an ellipse, a parabola, or a hyperbola.

###[Conic sections in polar coordinates](part0006_split_007.md)

All four conic sections can be described by the same function in polar coordinates:

![r(\theta) = \frac{q(1+\varepsilon)}{1 + \varepsilon\cos(\theta)}\,,](01501.jpeg)

where ![q](00385.jpeg) is the curve’s closest distance to a focal point and ![\varepsilon](01395.jpeg) is the curve’s eccentricity. For a circle, ![q=R](01502.jpeg) (the radius) and the eccentricity parameter is ![\varepsilon=0](01405.jpeg). For an ellipse, ![q=a(1-\varepsilon)](01503.jpeg) and the eccentricity parameter varies between ![0](00101.jpeg) and ![1](00211.jpeg) (![0\leq \varepsilon < 1](01504.jpeg)). Note we include the case ![\varepsilon=0](01405.jpeg) since a circle is a special case of an ellipse. For a parabola, ![q=f](01505.jpeg) (the focal length) and the eccentricity is ![\varepsilon=1](01506.jpeg). For a hyperbola, ![q = a(\varepsilon-1)](01507.jpeg) and the eccentricity is ![\varepsilon>1](01508.jpeg).

We can use the eccentricity parameter ![\varepsilon](01395.jpeg) to classify all four curves. Depending on the value of ![\varepsilon](01395.jpeg), the equation ![r(\theta)](01355.jpeg) defines either a circle, an ellipse, a parabola, or a hyperbola.[Table 6.2](part0006_split_007.md) summarizes all our observations regarding conic sections.

Conic section

Equation

Polar function

Eccentricity

Circle

![x^2+y^2=R^2](01509.jpeg)

![r(\theta)=R](01510.jpeg)

![\varepsilon = 0](01405.jpeg)

Ellipse

![\frac{x^2}{a^2}+\frac{y^2}{b^2}=1](01426.jpeg)

![r(\theta)=\frac{a(1-\varepsilon^2)}{1 + \varepsilon\cos(\theta)}](01511.jpeg)

![\varepsilon\!=\!\sqrt{1\!-\!\frac{b^2}{a^2}}\,, \; 0\!\leq\!\varepsilon\!<\!1](01512.jpeg)

Parabola

![y^2=4fx](01513.jpeg)

![r(\theta)=\frac{2f}{1 + \cos(\theta)}](01514.jpeg)

![\varepsilon=1](01506.jpeg)

Hyperbola

![\frac{x^2}{a^2}-\frac{y^2}{b^2}=1](01515.jpeg)

![r(\theta)=\frac{a(\varepsilon^2-1)}{1 + \varepsilon\cos(\theta)}](01516.jpeg)

![\varepsilon\!=\!\sqrt{1\!+\!\frac{b^2}{a^2}}\,, \; 1\!<\!\varepsilon\!<\!\infty](01517.jpeg)

Table 6.2: The four conic sections and their eccentricity parameters.

The motion of the planets is explained by Newton’s law of gravitation. The gravitational interaction between two bodies always leads one of the two bodies to follow a trajectory described by one of the conic sections for which the other body is the focal point.[Figure 6.30](part0006_split_007.md) illustrates four different trajectories for a satellite near planet ![F](01432.jpeg). The circle (![\varepsilon=0](01405.jpeg)) and the ellipse (![0 \leq \varepsilon < 1](01504.jpeg)) describe _closed orbits_, in which the satellite is captured in the gravitational field of the planet ![F](01432.jpeg) and remains in orbit forever. The parabola (![\varepsilon =1](01506.jpeg)) and the hyperbola (![\varepsilon>1](01508.jpeg)) describe _open orbits_, in which the satellite swings by the planet ![F](01432.jpeg) and then continues.

![eccentricity_four_conics](01518.jpeg)

Figure 6.30: Four different trajectories for a satellite moving near a planet.

###[Links](part0006_split_007.md)

\[ Interactive graph of a hyperbola \]

[https://www.desmos.com/calculator/2mnsk5o8vn](./2mnsk5o8vn.md)

\[ Lots of information about conic sections on Wikipedia \]

[https://en.wikipedia.org/wiki/Conicsection](./Conic_section.md)

[http://en.wikipedia.org/wiki/Eccentricity(mathematics)](./Eccentricity_(mathematics.md))

\[ An in-depth discussion on the conic sections \]

[http://astrowww.phys.uvic.ca/ tatum/celmechs/celm2.pdf](./celm2.pdf.md)

I’d love to continue this geometric digression and tell you more about the properties and applications of conic sections, but there are more pressing math topics to discuss! It’s time to learn about vectors.
