Chapter 6    

##[6.4 Circles and polar coordinates](part0006_split_004.md)

In this section, we’ll review what we know about circles and define the _polar coordinate system_, a specialized coordinate system for describing circles and other circular shapes.

###[Formulas](part0006_split_004.md)

A _circle_ is a set of points located at a constant distance from a centre point. A circle with radius ![r](01135.jpeg) centred at the origin is described by the equation

![x^2 + y^2 = r^2.](01136.jpeg)

All points ![(x,y)](00630.jpeg) that satisfy this equation are part of the circle.

More generally, the circle’s centre can be located at any point ![(h,k)](01074.jpeg) in the plane, as illustrated in[Figure 6.14](part0006_split_004.md).

![circle-centered-at-h-k](01308.gif)

Figure 6.14: A circle of radius ![r](01161.jpeg) centred at the point ![(h,k)](01309.jpeg) is described by the equation ![(x-h)^2 + (y-k)^2 = r^2](01310.jpeg).

####[Describing circles using functions](part0006_split_004.md)

The circle equation ![x^2 + y^2 = r^2](01311.jpeg) is a _relation_ between the variables ![x](00015.jpeg) and ![y](00018.jpeg). If we want to describe the circle using a function ![y=f(x)](00654.jpeg), we can solve for ![y](00018.jpeg) in the equation ![x^2 + y^2 = r^2](01311.jpeg) to obtain

![y = f_{\textrm{t}}(x) = \sqrt{ r^2 - x^2}, \; \; \, \quad -r \leq x \leq r,](01312.jpeg)

and

![y = f_{\textrm{b}}(x) = -\sqrt{ r^2 - x^2}, \quad -r \leq x \leq r.](01313.jpeg)

Describing a circle requires two functions, ![f_{\textrm{t}}](01314.jpeg) and ![f_{\textrm{b}}](01315.jpeg), because there are two values of ![y](00018.jpeg) that satisfy the equation ![x^2 + y^2 = r^2](01311.jpeg) for each value of ![x](00015.jpeg). The function ![f_{\textrm{t}}](01314.jpeg) describes the top half of the circle, while the function ![f_{\textrm{b}}](01315.jpeg) describes the bottom half.

You might be wondering why a simple geometric shape like a circle requires such complicated-looking formulas like ![f_{\textrm{t}}(x)](01316.jpeg) and ![f_{\textrm{b}}(x)](01317.jpeg) to describe it. Surely there’s a better way to describe circles that doesn’t involve quadratic expressions and square roots? There is! If instead of using the Cartesian coordinates ![(x,y)](00630.jpeg) we use the polar coordinates ![r\angle\theta](01318.jpeg), then the equation of a circle becomes very simple. We’ll learn about that next.

###[The polar coordinate system](part0006_split_004.md)

[Figure 6.15](part0006_split_004.md) shows the _polar coordinate system_, which consists of concentric circles at different distances from the origin (also called the _pole_), and radial lines extending from the origin in all directions. We can specify the location of any point in the plane using the _polar coordinates_ ![r\angle\theta](01318.jpeg), where ![r](01135.jpeg) measures the point’s distance from the origin, and ![\theta](00944.jpeg) describes the angle measured in the counterclockwise direction starting from the ![r](01135.jpeg)\-axis. For example, the point ![Q=2\angle60^\circ](01319.jpeg) is located at the distance of ![r=2](01320.jpeg) units form the origin, in the direction ![\theta=60^\circ](01321.jpeg).

![empty_coordinate_system_polar](01322.gif)

Figure 6.15: We can use the polar coordinate system to describe points in the two-dimensional plane. The polar coordinates ![r\angle\theta](01323.jpeg) describe the point located at the distance ![r](01161.jpeg) from the origin in the direction ![\theta](01154.jpeg).

Compare the polar coordinate system shown in[Figure 6.15](part0006_split_004.md) with the Cartesian coordinate system in[Figure 4.3](part0004_split_001.md). In the Cartesian coordinate system, we interpret the coordinate pair ![(x,y)](00630.jpeg) as the instructions “Walk a distance of ![x](00015.jpeg) units in the direction of the ![x](00015.jpeg)\-axis, and a distance of ![y](00018.jpeg) units in the direction of the ![y](00018.jpeg)\-axis.” In a polar coordinate system, we interpret the coordinates ![r\angle \theta](01318.jpeg) as the instructions “Turn toward the direction ![\theta](00944.jpeg) and walk a distance of ![r](01135.jpeg) units in that direction.” Both types of coordinates give instructions for getting to a particular point in the plane, with Cartesian coordinates giving the instructions in the form of two distances, while polar coordinates give the instructions in the form of a distance and a direction.

A Cartesian coordinate pair ![(x,y)](00630.jpeg) is made of ![x](00015.jpeg) and ![y](00018.jpeg) coordinates, while a polar coordinate pair ![r\angle\theta](01318.jpeg) is made of ![r](01135.jpeg) and ![\theta](00944.jpeg) coordinates. In this book, we use the angle symbol ![\angle](01324.jpeg) (read “at an angle of”) to separate the polar coordinates ![r](01135.jpeg) and ![\theta](00944.jpeg), in order to emphasize the difference between Cartesian and polar coordinates. However, some other books use the notation ![(r,\theta)](01325.jpeg) for polar coordinates, so you have to watch out—the coordinate pair ![(20,30)](01326.jpeg) could be either a ![(x,y)](00630.jpeg) coordinate pair or a ![(r,\theta)](01325.jpeg) coordinate pair, depending on the context.

Note the polar coordinates that describe a given point are not unique, meaning the same point can be described in multiple ways. The point ![Q=2\angle60^\circ](01319.jpeg) is equally described by the polar coordinates ![2\angle-300^\circ](01327.jpeg), since a clockwise turn of ![300^\circ](01328.jpeg) is the same as a counterclockwise turn of ![60^\circ](00749.jpeg). We can also describe the same point ![Q](01329.jpeg) using the polar coordinates ![-2\angle240^\circ](01330.jpeg) and ![-2\angle-120^\circ](01331.jpeg), which tell us to turn in the direction opposite to ![60^\circ](00749.jpeg) and measure a negative distance ![r=-2](01332.jpeg). While all of these polar coordinates for ![Q](01329.jpeg) are equivalent, the preferred way to specify polar coordinates is with positive ![r](01135.jpeg) values and angles ![|\theta| \leq 180^\circ](01333.jpeg).

####[Converting between Cartesian and polar coordinates](part0006_split_004.md)

[Figure 6.16](part0006_split_004.md) shows a point whose location is described both in terms of Cartesian coordinates ![(x,y)](00630.jpeg) and polar coordinates ![r\angle\theta](01318.jpeg). The triangle formed by the coordinates ![(0,0)](00923.jpeg), ![(x,0)](01334.jpeg), and ![(x,y)](00630.jpeg) is a right-angle triangle. This means we can apply our knowledge of the trigonometric functions ![\sin](00935.jpeg), ![\cos](00751.jpeg), and ![\tan](00968.jpeg) to obtain formulas for converting between Cartesian coordinates ![(x,y)](00630.jpeg) and polar coordinates ![r\angle\theta](01318.jpeg).

![polar_coordinates_conversion](01335.jpeg)

Figure 6.16: Polar coordinates ![r\angle\theta](01323.jpeg) can describe any point ![(x,y)](00634.jpeg).

To convert from polar coordinates ![r\angle\theta](01318.jpeg) to ![(x,y)](00630.jpeg) coordinates, we use the definitions of the trigonometric functions ![\cos\theta=\frac{\text{adj}}{\text{hyp}}=\frac{x}{r}](01336.jpeg) and ![\sin\theta=\frac{\text{opp}}{\text{hyp}}=\frac{y}{r}](01337.jpeg) to obtain the formulas:

![x = r\cos \theta      \qquad \textrm{and} \qquad      y = r\sin \theta.](01338.jpeg)

For example, the Cartesian coordinates of the point ![Q=2\angle 60^\circ](01319.jpeg) are given by ![Q=(x,y)=(2\cos60^\circ,\, 2\sin60^\circ) = (1, \sqrt{3})](01339.jpeg).

To convert from ![(x,y)](00630.jpeg) coordinates to ![r\angle\theta](01318.jpeg) coordinates, we can use the circle equation ![x^2 + y^2 = r^2](01311.jpeg) and the definition of the tangent function ![\tan\theta = \frac{\text{opp}}{\text{adj}} = \frac{y}{x}](01340.jpeg), then solve for ![r](01135.jpeg) and ![\theta](00944.jpeg) to obtain the formulas:

![r = \sqrt{x^2+y^2}      \quad \textrm{and} \quad      \theta = \left\{ \begin{array}{ll}       \tan^{-1}\!\big(\tfrac{y}{x}\big)     & \textrm{ if } x > 0,      \\       180^\circ + \tan^{-1}\!\big(\tfrac{y}{x}\big)   & \textrm{ if } x < 0,      \\       90^\circ          & \textrm{ if } x=0 \textrm{ and }  y > 0,   \\       -90^\circ          & \textrm{ if } x=0 \textrm{ and }  y < 0.      \end{array}\right.](01341.jpeg)

Finding the angle ![\theta](00944.jpeg) is a little tricky. We must use a different formula for computing ![\theta](00944.jpeg) depending on where the point is located, and there are four different cases to consider. The basic idea is to use the inverse tangent function ![\tan^{-1}](01262.jpeg), which is also called ![\arctan](01342.jpeg), or `atan` on computer systems. By convention, the function ![\tan^{-1}](01262.jpeg) returns values between ![-90^\circ](01343.jpeg) (![-\frac{\pi}{2}](01344.jpeg) rad) and ![90^\circ](01178.jpeg) (![\frac{\pi}{2}](00129.jpeg) rad), which correspond to points with positive ![x](00015.jpeg)\-coordinates. If the ![x](00015.jpeg)\-coordinate of the point is negative, we must add ![180^\circ](01127.jpeg) (![\pi](00057.jpeg) rad) to the output of the inverse-tangent calculation to obtain the correct angle. When ![x=0](00776.jpeg) we can’t compute the fraction ![\frac{y}{x}](01345.jpeg) because we cannot divide by zero, so we must handle the cases with ![x=0](00776.jpeg) separately as described in the above equation.

If you have access to a computer algebra system, the easiest way to calculate the angle ![\theta](00944.jpeg) for the point ![(x,y)](00630.jpeg) is to use the two-input inverse tangent function `atan2(y,x)`. The function `atan2` is the best way to compute the angle since it handles all four cases of converting Cartesian coordinates to polar coordinates automatically and always gives the correct angle. You can try some calculations with `atan2` using the computer algebra system at  [https://live.sympy.org](./live.sympy.org.md).

For example, consider the point ![P](00267.jpeg) with Cartesian coordinates ![(-3,2)](01346.jpeg) shown in[Figure 4.3](part0004_split_001.md) (page 4.3). To find the polar coordinates of this point we first calculate the distance from the centre, ![r=\sqrt{(-3)^2+2^2}=\sqrt{13} \approx 3.61](01347.jpeg). To find the angle ![\theta](00944.jpeg) we note that the ![x](00015.jpeg)\-coordinate of ![P](00267.jpeg) is negative, so the angle ![\theta](00944.jpeg) we’re looking for is given by the formula ![\theta = 180^\circ + \tan^{-1}\!\big(\tfrac{2}{-3}\big) = 146.31^\circ](01348.jpeg). The angle of the point ![P=(-3,2)](01349.jpeg) can also be obtained from `atan2(2,-3)`. The polar coordinates of the point ![P](00267.jpeg) are ![3.61\angle146.31^\circ](01350.jpeg) (see[Figure 6.15](part0006_split_004.md)).

####[Equations in polar coordinates](part0006_split_004.md)

Equations in polar coordinates serve to describe relations between the variables ![r](01135.jpeg) and ![\theta](00944.jpeg). For example, the equation of a circle with radius ![2](00103.jpeg) in polar coordinates is simply ![r=2](01320.jpeg). If we substitute ![r=\sqrt{x^2+y^2}](01351.jpeg) and square both sides of the equation, we obtain the equation ![x^2 + y^2 = 2^2](01352.jpeg) that we saw in the beginning of this section.

We can use the substitutions ![x=r\cos\theta](01256.jpeg) and ![y=r\sin\theta](01257.jpeg) to convert equations from Cartesian coordinates ![x](00015.jpeg) and ![y](00018.jpeg) to polar coordinates ![r](01135.jpeg) and ![\theta](00944.jpeg). Consider the equation ![2x-y=3](01353.jpeg), which describes the line shown in[Figure 5.10](part0005_split_002.md) on page 5.10. We can rewrite this equation in polar coordinates as ![2r\cos\theta - r\sin\theta = 3](01354.jpeg), which is a relation between the polar coordinates ![r](01135.jpeg) and ![\theta](00944.jpeg).

As you can tell from these examples, polar coordinates are very convenient when dealing with circles, and less so when working with lines. Indeed, describing a circle in polar coordinates is as simple as ![r=2](01320.jpeg), while in Cartesian coordinates we had to use the complicated-looking functions ![f_{\textrm{t}}](01314.jpeg) and ![f_{\textrm{b}}](01315.jpeg) (see page 6.4.1.1). The situation is the opposite for lines: the equation of a line in Cartesian coordinates is simple, ![2x-y=3](01353.jpeg), while in polar coordinates the same line is described by a tangled mess involving ![\sin](00935.jpeg) and ![\cos](00751.jpeg) functions.

####[Functions in polar coordinates](part0006_split_004.md)

A function in polar coordinates is denoted ![r(\theta)](01355.jpeg) and describes how the distance ![r](01135.jpeg) varies as a function of the angle ![\theta](00944.jpeg).

For example, a circle with radius ![2](00103.jpeg) is described by the function ![r(\theta)=2](01356.jpeg) in polar coordinates, as illustrated in[Figure 6.17](part0006_split_004.md) (a). The circle is described by a constant function in polar coordinates, since the points in all directions have the same distance from the centre.

As another example, we can transform the equation of the line ![2x-y=3](01353.jpeg) to polar coordinates to obtain ![2r\cos\theta - r\sin\theta = 3](01354.jpeg), then isolate ![r](01135.jpeg) to obtain the function

![r(\theta) = \frac{3}{2\cos\theta - \sin\theta}\,,](01357.jpeg)

which describes the distance from the origin for different angles ![\theta](00944.jpeg). For example, when ![\theta=0](01215.jpeg), we find ![r(0) = \frac{3}{2\cos0 - \sin0}=1.5](01358.jpeg), so we can plot the polar coordinates ![1.5\angle 0^\circ](01359.jpeg) on the function’s graph.

The polar coordinates graph of the function ![r(\theta)](01355.jpeg) corresponds to all points with polar coordinates ![r(\theta)\angle\theta](01360.jpeg), for all possible values of ![\theta](00944.jpeg). This is analogous to how we obtain the graph of the function ![f(x)](00288.jpeg) in Cartesian coordinates by plotting the points ![(x, f(x))](00648.jpeg), for all possible values of the input variable ![x](00015.jpeg).[Figure 6.17](part0006_split_004.md) shows the graphs of the two functions discussed here.

If you ever need to graph a function ![r(\theta)](01355.jpeg) by hand, you can compute the value of the function for several angles like ![\theta=-90^\circ](01361.jpeg), ![\theta=0^\circ](01362.jpeg), ![\theta=90^\circ](01363.jpeg), then plot these points in the polar coordinate system. For example, to graph the function ![r(\theta)=\frac{3}{2\cos\theta - \sin\theta}](01364.jpeg), we can compute ![r(-90^\circ) = \frac{3}{2\cos(-90^\circ) - \sin(-90^\circ)}=3](01365.jpeg), which gives us the point ![3\angle\!-\!90^\circ](01366.jpeg) on the graph. We can similarly compute ![r(0^\circ) = 1.5](01367.jpeg) and ![r(30^\circ)=2.43](01368.jpeg), which gives us the points ![1.5\angle0^\circ](01359.jpeg) and ![2.43\angle 30^\circ](01369.jpeg).

![polar_coordinates_circle_and_line_plots](01370.gif)

Figure 6.17: The graphs of functions in polar coordinates are obtained by computing the distance ![r(\theta)](01371.jpeg) in all directions ![\theta](01154.jpeg) varying from ![0^\circ](01372.jpeg) to ![360^\circ](01373.jpeg).

[Figure 6.18](part0006_split_004.md) shows the polar coordinates graphs of three other interesting functions. Look at the points ![r\angle\theta](01318.jpeg) indicated in each graph and check that they satisfy the corresponding function ![r(\theta)](01355.jpeg).

![polar_coordinates_plots_examples](01374.gif)

Figure 6.18: The graphs of three functions in polar coordinates: (a) a circle, (b) a three-petalled rose, and (c) an Archimedean spiral.

###[Discussion](part0006_split_004.md)

The polar coordinate system is an alternative way of describing points in space using polar coordinates ![r\angle\theta](01318.jpeg) instead of the usual Cartesian coordinates ![(x,y)](00630.jpeg). See the concept map in[Figure 6.19](part0006_split_004.md). Your knowledge and experience with the trigonometric functions ![\sin](00935.jpeg), ![\cos](00751.jpeg), and ![\tan](00968.jpeg) is what allows you to convert between Cartesian and polar coordinates.

![polar_coordinates_parallels](01375.jpeg)

Figure 6.19: Cartesian coordinates ![(x,y)](00634.jpeg) and polar coordinates ![r\angle\theta](01323.jpeg) are two equivalent systems for representing points, equations, and functions.

The formulas for converting between Cartesian coordinates ![(x,y)](00630.jpeg) and polar coordinates ![r\angle \theta](01318.jpeg) covered in this section are important, and you should consider them “required material.” I expect you to become totally fluent with these formulas now, because we’ll need them later in the book when we learn about vectors [Section 7.2](part0007_split_002.md)) and complex numbers [Section 7.5](part0007_split_005.md)).

In contrast, the three next sections are not “required material.” We’ll now switch gears to “entertainment mode” and learn about three bonus geometry topics: ellipses, parabolas, and hyperbolas. I want you to know about these shapes, but I don’t expect you to be fluent with all the definitions and equations. You can take it easy for the next three sections because none of the material will be “on the exam.” You deserve a break after all the polar coordinates formulas!

###[Exercises](part0006_split_004.md)

E6.8 Convert the given points from Cartesian to polar coordinates:

**a)** ![(3,1)](01376.jpeg) **b)** ![(-1,-2)](01377.jpeg) **c)** ![(0,-6)](01378.jpeg)

Convert the points from polar to Cartesian coordinates:

**d)** ![10\angle30^\circ](01379.jpeg) **e)** ![10\angle\!-\!345^\circ](01380.jpeg) **f)** ![10\angle120^\circ](01381.jpeg)

E6.9 Draw the graph of the function ![r(\theta)=\frac{2}{\sin\theta}](01382.jpeg) in polar coordinates for ![\theta](00944.jpeg) varying from ![0](00101.jpeg) to ![180^\circ](01127.jpeg). What is the equivalent description of this function in Cartesian coordinates?

###[Links](part0006_split_004.md)

\[ Visual introduction to polar coordinates \]

[`https://www.youtube.com/watch?v=stU63ST6ung`](./watch_v=stU63ST6ung.md)

\[ Professor Dave explains equations in polar coordinates \]

[`https://www.youtube.com/watch?v=jwLUapqnwkk`](./watch_v=jwLUapqnwkk.md)
