Chapter 6    

##[6.2 Trigonometry](part0006_split_002.md)

If one of the angles in a triangle is equal to ![90^\circ](01178.jpeg), we call this triangle a _right-angle triangle_. In this section we’ll discuss right-angle triangles in great detail and get to know their properties. We’ll learn some fancy new terms like _hypotenuse_, _opposite_, and _adjacent_, which are used to refer to the different sides of a triangle. We’ll also use the functions _sine_, _cosine_, and _tangent_ to compute the _ratios of lengths_ in right triangles.

Understanding triangles and their associated trigonometric functions is of fundamental importance: you’ll need this knowledge for your future understanding of mathematical concepts like vectors and complex numbers.

![rightangletriangle](01179.jpeg)

Figure 6.8: A right-angle triangle. The angle at the base is denoted ![\theta](01154.jpeg) and the names of the sides of the triangle are indicated.

###[Concepts](part0006_split_002.md)

-   ![A,B,C](01180.jpeg): the three _vertices_ of the triangle
-   ![\theta](00944.jpeg): the angle at the vertex ![C](00266.jpeg). Angles can be measured in degrees or radians.
-   ![\text{opp} = AB](01181.jpeg): the length of the _opposite_ side to ![\theta](00944.jpeg)
-   ![\text{adj} = BC](01182.jpeg): the length of side _adjacent_ to ![\theta](00944.jpeg)
-   ![\text{hyp} = AC](01183.jpeg): the _hypotenuse_. This is the triangle’s longest side.
-   ![h](01039.jpeg): the “height” of the triangle (in this case ![h = \text{opp} = AB](01184.jpeg))
-   ![\sin\theta = \frac{\text{opp}}{\text{hyp}}](01185.jpeg): the _sine_ of theta is the ratio of the length of the opposite side and the length of the hypotenuse
-   ![\cos\theta = \frac{\text{adj}}{\text{hyp}}](01186.jpeg): the _cosine_ of theta is the ratio of the adjacent length and the hypotenuse length
-   ![\tan\theta = \frac{\sin\theta}{\cos\theta} = \frac{\text{opp}}{\text{adj}}](01187.jpeg): the _tangent_ is the ratio of the opposite length divided by the adjacent length

###[Pythagoras’ theorem](part0006_split_002.md)

In a right-angle triangle, the length of the hypotenuse squared is equal to the sum of the squares of the lengths of the other sides:

![\text{adj}^2 \; + \; \text{opp}^2  \; = \;   \text{hyp}^2.](01188.jpeg)

If we divide both sides of the above equation by ![\text{hyp}^2](01189.jpeg), we obtain

![\frac{\text{adj}^2}{ \text{hyp}^2 } \;  + \; \frac{\text{opp}^2}{ \text{hyp}^2 }  \; = \; 1.](01190.jpeg)

Since ![\frac{\text{adj}}{\text{hyp}}=\cos\theta](01191.jpeg) and ![\frac{\text{opp}}{\text{hyp}} = \sin\theta](01192.jpeg), this equation can be rewritten as

![\cos^2\theta \; + \; \sin^2\theta = 1.](01193.jpeg)

This is a powerful _trigonometric identity_ that describes an important relation between sine and cosine functions. In case you’ve never seen this notation before, the expression ![\cos^2\theta](01194.jpeg) is used to denote ![(\cos(\theta))^2](01195.jpeg).

###[Sin and cos](part0006_split_002.md)

Meet the trigonometric functions, or trigs for short. These are your new friends. Don’t be shy now, say hello to them.

“Hello.”

“Hi.”

“Soooooo, you are like functions right?”

“Yep,” sin and cos reply in chorus.

“Okay, so what do you do?”

“Who me?” asks cos. “Well I tell the ratio…hmm…Wait, are you asking what I do as a _function_ or specifically what _I_ do?”

“Both I guess?”

“Well, as a function, I take angles as inputs and I give ratios as answers. More specifically, I tell you how ‘wide’ a triangle with that angle will be,” says cos all in one breath.

“What do you mean wide?” you ask.

“Oh yeah, I forgot to say, the triangle must have a hypotenuse of length 1. What happens is there is a point ![P](00267.jpeg) that moves around on a circle of radius 1, and we _imagine_ a triangle formed by the point ![P](00267.jpeg), the origin, and the point on the ![x](00015.jpeg)\-axis located directly below the point ![P](00267.jpeg).”

“I am not sure I get it,” you confess.

“Let me try explaining,” says sin. “Look at[Figure 6.9](part0006_split_002.md) and you’ll see a circle. This is the unit circle because it has a radius of 1. You see it, yes?”

“Yes.”

“Now imagine a point ![P](00267.jpeg) that moves along the circle of radius 1, starting from the point ![P(0)=(1,0)](01196.jpeg). The ![x](00015.jpeg) and ![y](00018.jpeg) coordinates of the point ![P(\theta)=(P_x(\theta),\; P_y(\theta))](01197.jpeg) as a function of ![\theta](00944.jpeg) are

![P(\theta)=(P_x(\theta),\; P_y(\theta)) = (\cos\theta, \; \sin\theta ).](01198.jpeg)

So, _either_ you can think of us in the context of triangles, or in the context of the unit circle.”

“Cool. I kind of get it. Thanks so much,” you say, but in reality you are weirded out. Talking functions? “Well guys. It was nice to meet you, but I have to get going, to finish the rest of the book.”

“See you later,” says cos.

“Peace out,” says sin.

###[The unit circle](part0006_split_002.md)

The _unit circle_ is a circle of radius one centred at the origin. The unit circle consists of all points ![(x,y)](00630.jpeg) that satisfy the equation ![x^2 + y^2 = 1](01199.jpeg). A point ![P](00267.jpeg) on the unit circle has coordinates ![(P_x,P_y)=(\cos\theta,\sin\theta)](01200.jpeg), where ![\theta](00944.jpeg) is the angle ![P](00267.jpeg) makes with the ![x](00015.jpeg)\-axis.

![trigonometric_functions_as_point_or_as_triangle](01201.jpeg)

Figure 6.9: The unit circle corresponds to the equation ![x^2+y^2=1](01202.jpeg). The coordinates of the point ![P](01203.jpeg) on the unit circle are ![P_x= \cos\theta](01204.jpeg) and ![P_y=\sin\theta](01205.jpeg).

![the_graph_of_sin_theta_as_the_vertical_component_of_P_on_unit_circle](01206.jpeg)

Figure 6.10: The function ![f(\theta)=\sin\theta](01207.jpeg) describes the vertical position of a point ![P](01203.jpeg) that travels along the unit circle. The graph shows the values of the function ![f(\theta)=\sin\theta](01207.jpeg) for angles between ![\theta=0](01208.jpeg) and ![\theta=\pi](01209.jpeg).

[Figure 6.10](part0006_split_002.md) shows the graph of the function ![f(\theta)=\sin\theta](01210.jpeg). The values ![\sin\theta](01118.jpeg) for the angles ![0](00101.jpeg), ![\frac{\pi}{6}](01211.jpeg) (![30^\circ](01212.jpeg)), ![\frac{\pi}{3}](01213.jpeg) (![60^\circ](00749.jpeg)), and ![\frac{\pi}{2}](00129.jpeg) (![90^\circ](01178.jpeg)) are marked. There are three values to remember: ![\sin\theta = 0](01214.jpeg) when ![\theta = 0](01215.jpeg), ![\sin\theta = \frac{1}{2}](01216.jpeg) when ![\theta = \frac{\pi}{6}](01217.jpeg) (![30^\circ](01212.jpeg)), and ![\sin\theta = 1](01218.jpeg) when ![\theta=\frac{\pi}{2}](01219.jpeg) (![90^\circ](01178.jpeg)). See[Figure 5.14](part0005_split_002.md) (page 5.14) for a graph of ![\sin\theta](01118.jpeg) that shows a complete cycle around the circle. Also see[Figure 5.17](part0005_split_002.md) (page 5.17) for the graph of ![\cos\theta](01119.jpeg).

Instead of trying to memorize the values of the functions ![\cos\theta](01119.jpeg) and ![\sin\theta](01118.jpeg) separately, it’s easier to remember them as a combined “package” ![(\cos\theta, \sin\theta)](01220.jpeg), which describes the ![x](00015.jpeg)\- and ![y](00018.jpeg)\-coordinates of the point ![P](00267.jpeg) for the angle ![\theta](00944.jpeg).[Figure 6.11](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) shows the values of ![\cos\theta](01119.jpeg) and ![\sin\theta](01118.jpeg) for the angles ![0](00101.jpeg), ![\frac{\pi}{6}](01211.jpeg) (![30^\circ](01212.jpeg)), ![\frac{\pi}{4}](01221.jpeg) (![45^\circ](01222.jpeg)), ![\frac{\pi}{3}](01213.jpeg) (![60^\circ](00749.jpeg)), and ![\frac{\pi}{2}](00129.jpeg) (![90^\circ](01178.jpeg)). These are the most common angles that often show up on homework and exam questions. For each angle, the ![x](00015.jpeg)\-coordinate (the first number in the bracket) is ![\cos\theta](01119.jpeg), and the ![y](00018.jpeg)\-coordinate (the second number in the bracket) is ![\sin\theta](01118.jpeg).

![trigonometry--unit-circle-with-angles-and-cos-sin-first_quadrant](01223.jpeg)

Figure 6.11: The combined ![(\cos\theta, \sin\theta)](01224.jpeg) coordinates for the points on the unit circle at the most common angles: ![0](00919.jpeg), ![\frac{\pi}{6}](01225.jpeg) (![30^\circ](01226.jpeg)), ![\frac{\pi}{4}](01227.jpeg) (![45^\circ](01228.jpeg)), ![\frac{\pi}{3}](01229.jpeg) (![60^\circ](01230.jpeg)), and ![\frac{\pi}{2}](01231.jpeg) (![90^\circ](01232.jpeg)).

Note the values of ![\cos\theta](01119.jpeg) and ![\sin\theta](01118.jpeg) for the angles shown in[Figure 6.11](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) are all combinations of the fractions ![\frac{1}{2}](00050.jpeg), ![\frac{\sqrt{2}}{2}](01233.jpeg), and ![\frac{\sqrt{3}}{2}](01234.jpeg). The square roots appear as a consequence of the trigonometric identity ![\cos^2\theta + \sin^2\theta = 1](01235.jpeg). This identity tells us that the sum of the squared coordinates of each point on the unit circle is equal to one. Let’s look at what this equation tells us for the angle ![\theta = \frac{\pi}{6}](01217.jpeg) (![30^\circ](01212.jpeg)). Remember that ![\sin(30^\circ) = \frac{1}{2}](01236.jpeg) (the length of the dashed line in[Figure 6.11](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md)). We can plug this value into the equation ![\cos^2(30^\circ) + \sin^2(30^\circ) = 1](01237.jpeg) to find the value: ![\cos(30^\circ) = \sqrt{ 1 - \sin^2(30^\circ)  } = \sqrt{ 1 - \frac{1}{4} } = \sqrt{ \frac{3}{4} } =  \tfrac{\sqrt{3}}{2}](01238.jpeg).

The coordinates ![\left(\frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2} \right)](01239.jpeg) for the angle ![\theta = \frac{\pi}{4}](01240.jpeg) (![45^\circ](01222.jpeg)) are obtained from a similar calculation. We know the values of ![\sin\theta](01118.jpeg) and ![\cos\theta](01119.jpeg) must be equal for that angle, so we’re looking for the number ![a](00014.jpeg) that satisfies the equation ![a^2 + a^2 = 1](01241.jpeg), which is ![a=\frac{1}{\sqrt{2}} = \frac{\sqrt{2}}{2}](01242.jpeg). The values of ![\cos(60^\circ)](00750.jpeg) and ![\sin(60^\circ)](01243.jpeg) can be obtained from a symmetry argument. Measuring ![60^\circ](00749.jpeg) from the ![x](00015.jpeg)\-axis is the same as measuring ![30^\circ](01212.jpeg) from the ![y](00018.jpeg)\-axis, so ![\cos(60^\circ)=\sin(30^\circ)=\frac{1}{2}](01244.jpeg) and ![\sin(60^\circ) = \cos(30^\circ) = \frac{\sqrt{3}}{2}](01245.jpeg).

We can extend the calculations described above for all other angles that are multiples of ![\frac{\pi}{6}](01211.jpeg) (![30^\circ](01212.jpeg)) and ![\frac{\pi}{4}](01221.jpeg) (![45^\circ](01222.jpeg)) to obtain the ![\cos\theta](01119.jpeg) and ![\sin\theta](01118.jpeg) values for the whole unit circle, as shown in[Figure 6.12](part0006_split_002.md).

![trigonometry--unit-circle-with-angles-and-cos-sin](01246.jpeg)

Figure 6.12: The coordinates of the point on the unit circle ![(\cos\theta, \sin\theta)](01224.jpeg) are indicated for all multiples of ![\frac{\pi}{6}](01225.jpeg) (![30^\circ](01226.jpeg)) and ![\frac{\pi}{4}](01227.jpeg) (![45^\circ](01228.jpeg)). Note the symmetries.

Don’t be intimidated by all the information shown in[Figure 6.12](part0006_split_002.md)! You’re not expected to memorize all these values. The primary reason for including this figure is so you can appreciate the symmetries of the sine and cosine values that we find as we go around the circle. The values of ![\sin\theta](01118.jpeg) and ![\cos\theta](01119.jpeg) for all angles are the same as the values for the angles between ![0^\circ](01247.jpeg) and ![90^\circ](01178.jpeg), but one or more of their coordinates has a negative sign. For example, ![150^\circ](01248.jpeg) is just like ![30^\circ](01212.jpeg), except its ![x](00015.jpeg)\-coordinate is negative since the point lies to the left of the ![y](00018.jpeg)\-axis. Another use for[Figure 6.12](part0006_split_002.md) is to convert between angles measured in degrees and radians, since both units for angles are indicated.

###[Non-unit circles](part0006_split_002.md)

Consider a point ![Q(\theta)](01249.jpeg) at an angle of ![\theta](00944.jpeg) on a circle with radius ![r\neq1](01250.jpeg). How can we find the ![x](00015.jpeg)\- and ![y](00018.jpeg)\-coordinates of the point ![Q(\theta)](01249.jpeg)?

We saw that the coefficients ![\cos\theta](01119.jpeg) and ![\sin\theta](01118.jpeg) correspond to the ![x](00015.jpeg)\- and ![y](00018.jpeg)\-coordinates of a point on the _unit_ circle (![r=1)](01251.jpeg). To obtain the coordinates for a point on a circle of radius ![r](01135.jpeg), we must _scale_ the coordinates by a factor of ![r](01135.jpeg):

![Q(\theta) =  (Q_x(\theta), Q_y(\theta) ) =  ( r\cos\theta, r\sin\theta ).](01252.jpeg)

![decomposing_vector_r_into_two_parts](01253.jpeg)

Figure 6.13: The ![x](00632.jpeg)\- and ![y](00674.jpeg)\-coordinates of a point at the angle ![\theta](01154.jpeg) and distance of ![r](01161.jpeg) from the origin are given by ![x=r\cos\theta](01254.jpeg) and ![y=r\sin\theta](01255.jpeg).

The take-away message is that you can use the functions ![\cos\theta](01119.jpeg) and ![\sin\theta](01118.jpeg) to find the “horizontal” and “vertical” components of any length ![r](01135.jpeg). From this point on in the book, we’ll always talk about the length of the _adjacent_ side as ![x=r\cos\theta](01256.jpeg), and the length of the _opposite_ side as ![y = r\sin\theta](01257.jpeg). It is extremely important you get comfortable with this notation.

The reasoning behind the above calculations is as follows:

![\cos\theta     =     \frac{\text{adj}}{\text{hyp}} = \frac{x}{r}     \quad \Rightarrow \quad       x = r \cos\theta,  \\](01258.jpeg)

and

![\sin\theta    =    \frac{\text{opp}}{\text{hyp}}=\frac{y}{r}    \quad \Rightarrow \quad    y = r\sin\theta.](01259.jpeg)

###[Calculators](part0006_split_002.md)

Watch out for the units of angle measures when using calculators and computers. Make sure you know what kind of angle units the functions ![\sin](00935.jpeg), ![\cos](00751.jpeg), and ![\tan](00968.jpeg) expect as inputs, and what kind of outputs the functions ![\sin^{-1}](01260.jpeg), ![\cos^{-1}](01261.jpeg), and ![\tan^{-1}](01262.jpeg) return.

For example, let’s see what we should type into the calculator to compute the sine of 30 degrees. If the calculator is set to degrees, we simply type: ![\button{\texttt{3}}](01263.jpeg), ![\button{\texttt{0}}](01264.jpeg), ![\button{\texttt{sin}}](01265.jpeg), ![\button{\texttt{=}}](01266.jpeg), and obtain the answer ![0.5](00171.jpeg).

If the calculator is set to radians, we have two options:

1.  Change the `mode` of the calculator so it works in degrees.
2.  Convert ![30^\circ](01212.jpeg) to radians
    
    ![30^\circ \times \frac{ 2\pi \; \text{rad} }{ 360^\circ } = \frac{\pi}{6} \; \text{rad},](01267.jpeg)
    
    and type: ![\button{\pi}](01268.jpeg), ![\button{\small\texttt{/}}](01269.jpeg), ![\button{\texttt{6}}](01270.jpeg), ![\button{\texttt{sin}}](01265.jpeg), ![\button{\texttt{=}}](01266.jpeg) on the calculator.
    

Try computing ![\cos(60^\circ)](00750.jpeg), ![\cos\!\big(\frac{\pi}{3}\; \text{rad}\big)](01271.jpeg), and ![\cos^{-1}(\frac{1}{2})](01272.jpeg) using your calculator to make sure you know how it works.

###[Exercises](part0006_split_002.md)

E6.4 Given a circle with radius ![r=5](01273.jpeg), find the ![x](00015.jpeg)\- and ![y](00018.jpeg)\-coordinates of the point at ![\theta=45^{\circ}](01274.jpeg). What is the circumference of the circle?

E6.5 Convert the following angles from degrees to radians.

**a)** ![30^\circ](01212.jpeg) **b)** ![45^\circ](01222.jpeg) **c)** ![60^\circ](00749.jpeg) **d)** ![270^\circ](01275.jpeg)

###[Links](part0006_split_002.md)

\[ Unit-circle walkthrough and tricks by patrickJMT on YouTube \]

[`http://bit.ly/1mQg9Cj`](./1mQg9Cj.md) and[`http://bit.ly/1hvA702`](./1hvA702.md)
