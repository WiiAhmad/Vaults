Chapter 6    

##[6.6 Parabola](part0006_split_006.md)

The _parabola_ is another important geometric shape. In this section, we’ll see how we can describe parabolas using their geometric properties, as well as in terms of algebraic equations.

###[Parameters](part0006_split_006.md)

[Figure 6.23](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) shows a parabola with all its parameters annotated:

-   ![f](00287.jpeg): the _focal length_ of the parabola
-   ![F=(0,f)](01430.jpeg): the _focal point_ of the parabola
-   ![\{ (x,y) \in\mathbb{R}^2 \; | \; y=-f\}](01431.jpeg): the _directrix_ line to the parabola
-   ![r](01135.jpeg): the distance from point ![P](00267.jpeg) on the parabola to the focal point ![F](01432.jpeg)
-   ![\ell](01143.jpeg): the closest distance from a point ![P](00267.jpeg) on the parabola to the parabola’s directrix line

![new-conic-sections--parabola](01433.jpeg)

Figure 6.23: The parabola is defined geometrically as the set of points whose distance form the focal point ![r](01161.jpeg) is equal to their distance from the directrix ![\ell](01149.jpeg). The figure shows the point ![P](01203.jpeg) on the parabola that has distance ![r=2](01434.jpeg) from ![F](01435.jpeg), and distance ![\ell=2](01436.jpeg) from the point ![D](01437.jpeg) on the directrix. This parabola can be described algebraically using the equation ![y=\frac{1}{4}x^2](01438.jpeg).

###[Geometric definition](part0006_split_006.md)

The shape of a parabola is determined by a single parameter ![f](00287.jpeg), called the _focal length_. For a parabola with focal length ![f](00287.jpeg), the focal point is at ![F=(0,f)](01430.jpeg) and the _directrix_ line has the equation ![y=-f](01439.jpeg). The parabola is defined as the set of points ![P](00267.jpeg) for which the distance from the focal point and the directrix are equal:

![r = \ell,](01440.jpeg)

where ![r =  d(P, F)](01441.jpeg) is the distance from the point ![P](00267.jpeg) to the focal point ![F](01432.jpeg), and ![\ell = d(P, D)](01442.jpeg) is the distance from ![P](00267.jpeg) to the point ![D](01443.jpeg) on the directrix that is closest to the point ![P](00267.jpeg).

[Figure 6.23](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) shows a parabola opening upward with focal length ![f=1](01444.jpeg) centred at the origin. The parabola is the set of points that are equidistant from the focal point ![F=(0,1)](01445.jpeg) and the directrix line located at ![y=-1](01446.jpeg).

###[Algebraic description](part0006_split_006.md)

The shape of a parabola with focal length ![f](00287.jpeg) opening upward corresponds to the graph of the quadratic functions ![f(x) = \frac{1}{4f} x^2](01447.jpeg). This is a special case of the general formula for quadratic functions ![f(x) = a(x-h)^2 + k](01448.jpeg), which you’re already familiar with from[Section 5.3](part0005_split_003.md) (see page 5.3.5). The parabola shown in[Figure 6.23](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) is centred at the origin, so the displacement parameters ![h](01039.jpeg) and ![k](00017.jpeg) are both zero. The coefficient ![a](00014.jpeg) in the general formula is related to the focal length ![f](00287.jpeg) through the relation ![a=\frac{1}{4f}](01449.jpeg), so in the case of focal length ![f=1](01444.jpeg) the coefficient is ![a=\frac{1}{4}](01450.jpeg). See[Figure 6.23](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md).

The formula ![y=\frac{1}{4f}x^2](01451.jpeg) is specific to the case of a parabola opening upward, but similar algebraic expressions exist for parabolas opening downward and sideways. The parabola with focal length ![f](00287.jpeg) opening downward is described by the equation ![y=-\frac{1}{4f}x^2](01452.jpeg). The parabola opening to the left and to the right are described by relations ![x=-\frac{1}{4f}y^2](01453.jpeg) and ![x=\frac{1}{4f}y^2](01454.jpeg). With your knowledge of the displacement parameters ![h](01039.jpeg) and ![k](00017.jpeg) used for general quadratic equations (see page 5.3.5), you can also obtain algebraic expressions for parabolas that are not centred at the origin.

###[Polar coordinates](part0006_split_006.md)

In the previous section we connected the geometric definition of parabolas with quadratic algebraic expressions. When learning math, it’s important to note connections of this sort because they are the bridges between different mathematical domains. If one day you have to solve a geometry problem involving parabolas, you could use algebraic equations to describe the parabolas and solve the problem using algebra. If on another day you encounter an algebra problem involving a quadratic equation, you could visualize the quadratic equation as a parabolic shape and solve the problem using geometric reasoning. Being able to travel between math domains like this is a mark of true math fluency.

In the spirit of further bridge-building, I want to show you the equation of a parabola in polar coordinates. We choose a coordinate system centred at the focal point ![F](01432.jpeg). The polar-coordinates equation for the parabola with focal length ![f](00287.jpeg) opening to the left is

![r(\theta) = \frac{2f}{1+\cos\theta}\,.](01455.jpeg)

[Figure 6.24](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) shows a particular instance of this formula when the parabola has focal length ![f=1](01444.jpeg). Try substituting the values ![\theta=0](01215.jpeg) and ![\theta = 90^\circ](01363.jpeg) (![\frac{\pi}{2}](00129.jpeg) radians) in the polar equation to verify that it correctly describes the points on the parabola.

![conic-sections--parabola_in_polar_coords](01456.jpeg)

Figure 6.24: The parabola described by ![r(\theta)=\frac{2}{1+\cos\theta}](01457.jpeg) in polar coordinates.

The key point I want you to take away from this section is that algebraic formulas can be very useful for describing geometric shapes. The parabola illustrated in[Figure 6.24](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) can be described in three equivalent ways: geometrically through its focal length ![f=1](01444.jpeg) and directrix line ![x=2](00380.jpeg); algebraically as the relation ![x=1-\frac{1}{4}y^2](01458.jpeg) in Cartesian coordinates; or as the function ![r(\theta) = \frac{2}{1+\cos\theta}](01459.jpeg) in polar coordinates.

###[Parabola applications](part0006_split_006.md)

Parabolic shapes are of special importance in optics and communications. Using parabolic lenses, mirrors, and antennas, it’s possible to focus the energy emitted from a distant object into a single point. This is due to the _reflective property_ of parabolas, which states that all light rays coming from far away are redirected toward the focal point of the parabolic shape. The reflective property makes parabolas useful for many practical communication applications.

![conic-sections--parabolic-antenna](01460.jpeg)

Figure 6.25: The reflective property of parabolas tells us all radio waves coming from infinity are reflected toward the focal point of the parabola.

[Figure 6.25](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) illustrates the setup for a radio communication scenario in which a ground station is trying to detect a signal coming from a satellite in orbit. The satellite is very far away so the signal received on Earth is very weak. A parabolic satellite dish antenna collects the signal from a large surface area and focuses all of it on the focal point of the parabola. A radio receiver placed at the focal point of the parabola receives a much stronger signal, since the focal point is where the power from the whole dish surface is concentrated. This is thanks to the reflective property of the parabolic shape: all radio waves coming from the far-away satellite get reflected toward the focal point of the parabola.

###[Exercises](part0006_split_006.md)

E6.11 Consider some arbitrary point ![P=(x,y)](01461.jpeg) that lies on the parabola with focal length ![f](00287.jpeg) centred at the origin as illustrated in[Figure 6.23](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md). Use the geometric definition of the parabola ![r = \ell](01462.jpeg) to obtain a relation between the ![x](00015.jpeg)\- and ![y](00018.jpeg)\-coordinates of the point ![P](00267.jpeg).

The distance between points ![A=(A_x, A_y)](01463.jpeg) and ![B=(B_x,B_y)](01464.jpeg) is given by ![d(A, B) = \sqrt{ (A_x-B_x)^2 + (A_y-B_y)^2 }](01465.jpeg).

Recall the definitions of ![r = d(P, F)](01441.jpeg) and ![\ell = d(P, D)](01442.jpeg).

###[Links](part0006_split_006.md)

\[ Interactive graph of a parabola \]

[https://www.desmos.com/calculator/4ddfrv7wvx](./4ddfrv7wvx.md)

\[ Further reading about parabolas on Wikipedia \]

[`https://en.wikipedia.org/wiki/Parabola`](./Parabola.md)
