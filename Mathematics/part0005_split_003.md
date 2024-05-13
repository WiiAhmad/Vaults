Chapter 5    

##[5.3 Function transformations](part0005_split_003.md)

Often, we’re asked to adjust the shape of a function by scaling it or moving it, so that it passes through certain points. For example, if we wanted to make a function ![g](01017.jpeg) with the same shape as the absolute value function ![f(x)=|x|](00808.jpeg), but moved up by three units so that ![g(0)=3](01018.jpeg), we would use the function ![g(x)=|x|+3](01019.jpeg).

In this section, we’ll discuss the four basic transformations you can perform on _any_ function ![f](00287.jpeg) to obtain a transformed function ![g](01017.jpeg):

-   Vertical translation: ![g(x) = f(x)+k](01020.jpeg)
-   Horizontal translation: ![g(x) = f(x-h)](01021.jpeg)
-   Vertical scaling: ![g(x) = Af(x)](01022.jpeg)
-   Horizontal scaling: ![g(x) = f(ax)](01023.jpeg)

By applying these transformations, we can _move_ and _stretch_ a generic function to give it any desired shape.

The next couple of pages illustrate all of the above transformations on the function

![f(x) = 6.75(x^3 - 2x^2 +x).](01024.jpeg)

We’ll work with this function because it has distinctive features in both the horizontal and vertical directions. By observing this function’s graph [Figure 5.21](part0005_split_003.md)), we see its ![x](00015.jpeg)\-intercepts are at ![x=0](00776.jpeg) and ![x=1](00773.jpeg). We can confirm this mathematically by factoring the expression:

![f(x) = 6.75x(x^2 - 2x +1) = 6.75x(x-1)^2.](01025.jpeg)

The function ![f(x)](00288.jpeg) also has a local maximum at ![x=\frac{1}{3}](01026.jpeg), and the value of the function at that maximum is ![f(\frac{1}{3})=1](01027.jpeg).

![function_transformation_none](01028.gif)

Figure 5.21: Graph of the function ![f(x)=6.75(x^3 - 2x^2 +x)](01029.jpeg).

###[Vertical translations](part0005_split_003.md)

To move a function ![f(x)](00288.jpeg) _up_ by ![k](00017.jpeg) units, add ![k](00017.jpeg) to the function:

![g(x) = f(x) + k.](01030.jpeg)

The function ![g(x)](01031.jpeg) will have exactly the same shape as ![f(x)](00288.jpeg), but it will be _translated_ (the mathematical term for moved) upward by ![k](00017.jpeg) units.

![function_transformation_k2](01032.jpeg)

Figure 5.22: The graph of the function ![g(x) = f(x)+2](01033.jpeg) has the same shape as the graph of ![f(x)](00673.jpeg) translated upward by two units.

Recall the function ![f(x) = 6.75(x^3 - 2x^2 +x)](01034.jpeg). To move the function up by ![k=2](01035.jpeg) units, we can write

![g(x) = f(x)+2 = 6.75(x^3 - 2x^2 +x) + 2,](01036.jpeg)

and the graph of ![g(x)](01031.jpeg) will be as it is shown in[Figure 5.22](part0005_split_003.md). Recall the original function ![f(x)](00288.jpeg) crosses the ![x](00015.jpeg)\-axis at ![x=0](00776.jpeg). The transformed function ![g(x)](01031.jpeg) has the property ![g(0)=2](01037.jpeg). The maximum at ![x=\frac{1}{3}](01026.jpeg) has similarly shifted in value from ![f(\frac{1}{3})=1](01027.jpeg) to ![g(\frac{1}{3})=3](01038.jpeg).

###[Horizontal translation](part0005_split_003.md)

We can move a function ![f](00287.jpeg) to the right by ![h](01039.jpeg) units by _subtracting_ ![h](01039.jpeg) from ![x](00015.jpeg) and using ![(x-h)](01040.jpeg) as the function’s input argument:

![g(x) = f(x-h).](01041.jpeg)

The point ![(0,f(0))](01042.jpeg) on ![f(x)](00288.jpeg) now corresponds to the point ![(h,g(h))](01043.jpeg) on ![g(x)](01031.jpeg).

![function_transformation_h2](01044.jpeg)

Figure 5.23: The graph of the function ![g(x) = f(x-2)](01045.jpeg) has the same shape as the graph of ![f(x)](00673.jpeg) translated to the right by two units.

[Figure 5.23](part0005_split_003.md) shows the function ![f(x)= 6.75(x^3 - 2x^2 +x)](01034.jpeg), as well as the function ![g(x)](01031.jpeg), which is shifted to the right by ![h=2](01046.jpeg) units:

![g(x)     = f(x-2)    = 6.75\left[ (x-2)^3 - 2(x-2)^2 +(x-2) \right].](01047.jpeg)

The original function ![f](00287.jpeg) gives us ![f(0)=0](01048.jpeg) and ![f(1)=0](01049.jpeg), so the new function ![g(x)](01031.jpeg) must give ![g(2)=0](01050.jpeg) and ![g(3)=0](01051.jpeg). The maximum at ![x=\frac{1}{3}](01026.jpeg) has similarly shifted by two units to the right, ![g(2+\frac{1}{3})=1](01052.jpeg).

###[Vertical scaling](part0005_split_003.md)

To stretch or compress the shape of a function vertically, we can multiply it by some constant ![A](00667.jpeg) and obtain

![g(x) = Af(x).](01053.jpeg)

![function_transformation_avert2](01054.jpeg)

Figure 5.24: The graph of the function ![g(x)=2f(x)](01055.jpeg) looks like ![f(x)](00673.jpeg) vertically stretched by a factor of two.

If ![|A|>1](01056.jpeg), the function will be stretched. If ![|A|<1](01057.jpeg), the function will be compressed. If ![A](00667.jpeg) is negative, the function will flip upside down, which is a _reflection_ through the ![x](00015.jpeg)\-axis.

There is an important difference between vertical translation and vertical scaling. Translation moves all points of the function by the same amount, whereas scaling moves each point proportionally to that point’s distance from the ![x](00015.jpeg)\-axis.

The function ![f(x)= 6.75(x^3 - 2x^2 +x)](01034.jpeg), when stretched vertically by a factor of ![A=2](01058.jpeg), becomes the function

![g(x) = 2f(x) = 13.5(x^3 - 2x^2 +x).](01059.jpeg)

The ![x](00015.jpeg)\-intercepts ![f(0)=0](01048.jpeg) and ![f(1)=0](01049.jpeg) do not move, and remain at ![g(0)=0](01060.jpeg) and ![g(1)=0](01061.jpeg). All values of ![f(x)](00288.jpeg) have been stretched upward by a factor of 2, as we can verify using the point ![f(1.5)=2.5](01062.jpeg), which has become ![g(1.5)=5](01063.jpeg). The maximum at ![x=\frac{1}{3}](01026.jpeg) has doubled in value to become ![g(\frac{1}{3})=2](01064.jpeg).

###[Horizontal scaling](part0005_split_003.md)

To stretch or compress a function horizontally, we can multiply the input value by some constant ![a](00014.jpeg) to obtain:

![g(x) = f(ax).](01065.jpeg)

If ![|a|>1](01066.jpeg), the function will be compressed. If ![|a|<1](01067.jpeg), the function will be stretched. Note that the behaviour here is the opposite of vertical scaling. If ![a](00014.jpeg) is a negative number, the function will also flip horizontally, which is a reflection through the ![y](00018.jpeg)\-axis.

![function_transformation_a2](01068.jpeg)

Figure 5.25: The graph of the function ![g(x)=f(2x)](01069.jpeg) looks like ![f(x)](00673.jpeg) horizontally compressed by a factor of two.

[Figure 5.25](part0005_split_003.md) shows the function ![g(x)](01031.jpeg), which is ![f(x)](00288.jpeg) compressed horizontally by a factor of ![a=2](00457.jpeg):

![g(x)  = f(2x) =6.75\!\left[ (2x)^3 - 2(2x)^2 +(2x)\right].](01070.jpeg)

The ![x](00015.jpeg)\-intercept ![f(0)=0](01048.jpeg) does not move since it is on the ![y](00018.jpeg)\-axis. The ![x](00015.jpeg)\-intercept ![f(1)=0](01049.jpeg) does move, however, and we have ![g(0.5)=0](01071.jpeg). The maximum at ![x=\frac{1}{3}](01026.jpeg) moves to ![g(\frac{1}{6})=1](01072.jpeg). All points of ![f(x)](00288.jpeg) are compressed toward the ![y](00018.jpeg)\-axis by a factor of 2.

###[General quadratic function](part0005_split_003.md)

Any quadratic function can be written in the form:

![f(x) = a(x-h)^2 + k,](01073.jpeg)

where ![x](00015.jpeg) is the input, and ![a](00014.jpeg), ![h](01039.jpeg), and ![k](00017.jpeg) are parameters. This is called the _vertex form_ of the quadratic function, and the coordinate pair ![(h,k)](01074.jpeg) is called the _vertex_ of the parabola. This equation can be obtained by starting from the basic quadratic function ![x^2](00026.jpeg) (see[Figure 5.11](part0005_split_002.md)) and applying three transformations: a horizontal translation by ![h](01039.jpeg) units, a vertical scaling by ![a](00014.jpeg), and finally a vertical translation by ![k](00017.jpeg) units.

####[Parameters](part0005_split_003.md)

-   ![a](00014.jpeg): the slope multiplier
    -   The larger the absolute value of ![a](00014.jpeg), the steeper the slope.
    -   If ![a<0](01075.jpeg) (negative), the function opens downward.
-   ![h](01039.jpeg): the horizontal displacement of the function. Note that subtracting a number inside the bracket ![(\; \;  )^2](01076.jpeg) (positive ![h](01039.jpeg)) makes the function go to the right.
-   ![k](00017.jpeg): the vertical displacement of the function

The graph in[Figure 5.26](part0005_split_003.md) illustrates a quadratic function with parameters ![a=1](01077.jpeg), ![h=1](01078.jpeg) (one unit shifted to the right), and ![k=-2](01079.jpeg) (two units shifted down).

![quadratic_func_h1_k2](01080.jpeg)

Figure 5.26: The graph of the function ![f(x)=(x-1)^2-2](01081.jpeg) is the same as the function ![f(x)=x^2](00652.jpeg), but shifted one unit to the right and two units down.

We can also write a quadratic function as a second-degree polynomial ![f(x) = ax^2 + bx + c](00491.jpeg). This is called the _standard form_ of the quadratic function. Given a quadratic expression in standard form ![ax^2 + bx + c](00370.jpeg), we can find its equivalent expression in vertex form ![a(x-h)^2 + k](01082.jpeg) using the complete-the-square trick we learned in[Section 2.1.4](part0002_split_001.md).

If a quadratic function crosses the ![x](00015.jpeg)\-axis, it can be written in _factored form_:

![f(x) = a(x-x_1)(x-x_2),](01083.jpeg)

where ![x_1](00455.jpeg) and ![x_2](00456.jpeg) are the two roots of the quadratic. Given a quadratic function ![f(x)=ax^2 + bx + c](00491.jpeg), we can find its roots using the quadratic formula: ![x_{1}=\frac{-b + \sqrt{b^2 - 4ac}}{2a}](00888.jpeg) and ![x_{2}=\frac{-b - \sqrt{b^2 - 4ac}}{2a}](00889.jpeg) (see[Section 2.2](part0002_split_002.md)).

###[General sine function](part0005_split_003.md)

Introducing all possible parameters into the sine function gives us:

![f(x) = A\sin\!\left( \tfrac{2\pi}{\lambda}x - \phi\right)\!,](01084.jpeg)

where ![A](00667.jpeg), ![\lambda](01085.jpeg), and ![\phi](01086.jpeg) are the function’s parameters.

![sin_of_x_A2_and_shifted](01087.jpeg)

Figure 5.27: The graph of the function ![f(x)=2\sin\big(\frac{2\pi}{4}x-\frac{\pi}{2}\big)](01088.jpeg), which has amplitude ![A=2](01089.jpeg), wavelength ![\lambda=4](01090.jpeg), and phase shift ![\phi = \frac{\pi}{2}](01091.jpeg).

####[Parameters](part0005_split_003.md)

-   ![A](00667.jpeg): the amplitude describes the distance above and below the ![x](00015.jpeg)\-axis that the function reaches as it oscillates.
-   ![\lambda](01085.jpeg): the _wavelength_ of the function:
    
    ![\lambda =  \{ \text{ the horizontal distance from one peak to the next } \}.](01092.jpeg)
    
-   ![\phi](01086.jpeg): is a phase shift, analogous to the horizontal shift ![h](01039.jpeg), which we have seen. This number dictates where the oscillation starts. The default sine function has zero phase shift (![\phi=0](01093.jpeg)), so it passes through the origin with an increasing slope.

The “bare” sine function ![f(x)=\sin(x)](00810.jpeg) has wavelength ![2\pi](00928.jpeg) and produces outputs that oscillate between ![-1](00308.jpeg) and ![+1](01094.jpeg). When we multiply the bare function by the constant ![A](00667.jpeg), the oscillations will range between ![-A](01095.jpeg) and ![A](00667.jpeg). When the input ![x](00015.jpeg) is scaled by the factor ![\frac{2\pi}{\lambda}](01096.jpeg), the wavelength of the function becomes ![\lambda](01085.jpeg).

###[Exercises](part0005_split_003.md)

E5.4 Given the functions ![f(x)=x+5](01097.jpeg), ![g(x)=x-6](01098.jpeg), ![h(x)=7x](01099.jpeg), and ![q(x)=x^2](01100.jpeg), find the formulas for the following composite functions:

**a)** ![q \circ f](01101.jpeg) **b)** ![f \circ q](01102.jpeg) **c)** ![q \circ g](01103.jpeg) **d)** ![q \circ h](01104.jpeg)

In each case, describe how the graph of the composite function is related to the graph of ![q(x)](01105.jpeg).

Recall, “![\circ](00734.jpeg)” denotes function composition: ![(f\circ g)(x) = f(g(x))](01106.jpeg).

E5.5 Find the amplitude ![A](00667.jpeg), the wavelength ![\lambda](01085.jpeg), and the phase shift ![\phi](01086.jpeg) for the function ![f(x)=5\sin(62.83x-\frac{\pi}{8})](01107.jpeg).

E5.6 Choose the coefficients ![a](00014.jpeg), ![b](00074.jpeg), and ![c](00256.jpeg) for the quadratic function ![f(x)=ax^2+bx+c](00491.jpeg) so that it passes through the points ![(0,5)](01108.jpeg), ![(1,4)](01109.jpeg), and ![(2,5)](01110.jpeg).

Find the equation ![f(x)=A(x-h)^2+k](01111.jpeg) first.

E5.7 Find the values ![\alpha](01112.jpeg) and ![\beta](01113.jpeg) that will make the function ![g(x)= 2\sqrt{x -\alpha} + \beta](01114.jpeg) pass through the points ![(3,-2)](01115.jpeg), ![(4,0)](01116.jpeg), and ![(7,2)](01117.jpeg).
