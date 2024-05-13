Chapter 6    

##[6.5 Ellipse](part0006_split_005.md)

The _ellipse_ is a fundamental shape that occurs in nature. The orbit of planet Earth around the Sun is an ellipse.

###[Parameters](part0006_split_005.md)

[Figure 6.20](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) shows an ellipse with all its parameters annotated:

-   ![F_1, F_2](01383.jpeg): the two _focal points_ of the ellipse
-   ![r_1](01384.jpeg): the distance from a point on the ellipse to ![F_1](01385.jpeg)
-   ![r_2](01386.jpeg): the distance from a point on the ellipse to ![F_2](01387.jpeg)
-   ![a](00014.jpeg): the semi-major axis of the ellipse is the half-length of the ellipse along the ![x](00015.jpeg)\-axis. The distance between ![V_1](01388.jpeg) and ![V_2](01389.jpeg) is ![2a](01390.jpeg).
-   ![b](00074.jpeg): the semi-minor axis of the ellipse is the half-width of the ellipse along the ![y](00018.jpeg)\-axis. The distance between ![V_3](01391.jpeg) and ![V_4](01392.jpeg) is ![2b](01393.jpeg).
-   ![c](00256.jpeg): the distance of the focal points from the centre of the ellipse. The distance between ![F_1](01385.jpeg) and ![F_2](01387.jpeg) is ![2c](01394.jpeg).
-   ![\varepsilon](01395.jpeg): the _eccentricity_ of the ellipse, ![\varepsilon = \sqrt{1- \frac{b^2}{a^2}} = \frac{c}{a}](01396.jpeg).

![conic-sections--ellipse](01397.jpeg)

Figure 6.20: An ellipse with semi-major axis ![a](00110.jpeg) and semi-minor axis ![b](01123.jpeg). The locations of the focal points ![F_1](01398.jpeg) and ![F_2](01399.jpeg) are indicated.

###[Definition](part0006_split_005.md)

An ellipse is the curve found by tracing along all the points for which the sum of the distances to the two focal points is a constant:

![r_1 + r_2 = \text{const}.](01400.jpeg)

There’s a neat way to draw a perfect ellipse using a piece of string and two tacks. Take a piece of string and tack it to a picnic table at two points, leaving some loose slack in the middle of the string. Now take a pencil, and without touching the table, use the pencil to pull the middle of the string until it is taut. Make a mark at that point. With the two parts of string completely straight, make a mark at every point possible where the two “legs” of string remain taut.

An ellipse is a set of points ![(x,y)](00630.jpeg) that satisfy the equation

![\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1.](01401.jpeg)

The parameters ![a](00014.jpeg) and ![b](00074.jpeg) determine the shape of the ellipse.

The focal points ![F_1](01385.jpeg) and ![F_2](01387.jpeg) correspond to the locations of the two tacks where the string is held in place. The coordinates of the two focal points are

![F_1 = (-c,0) \qquad \textrm{and} \qquad F_2 = (c,0),](01402.jpeg)

where ![c = \sqrt{a^2-b^2}](01403.jpeg) is the _focal distance_.

The _eccentricity_ of an ellipse is given by the equation

![\varepsilon = \sqrt{1- \frac{b^2}{a^2} } = \frac{c}{a}\,.](01404.jpeg)

The parameter ![\varepsilon](01395.jpeg) (the Greek letter _epsilon_) varies between ![0](00101.jpeg) and ![1](00211.jpeg) and describes how much the shape of the ellipse differs from the shape of a circle. When ![\varepsilon=0](01405.jpeg) the ellipse is a circle with radius ![a](00014.jpeg), and both focal points are located at the centre. As the eccentricity ![\varepsilon](01395.jpeg) increases, the ellipse becomes more elongated and the focal points spread farther apart.

###[Polar coordinates](part0006_split_005.md)

Consider a polar coordination system whose centre is located at the focus ![F_2](01387.jpeg). We can describe the ellipse by specifying the function ![r_2(\theta)](01406.jpeg), which describes the distance from the focus ![F_2](01387.jpeg) to the point ![E](01407.jpeg) on the ellipse as a function of the angle ![\theta](00944.jpeg) (see[Figure 6.21](part0006_split_005.md)). Recall that for functions in polar coordinates, the angle ![\theta](00944.jpeg) is the independent variable that varies from ![0](00101.jpeg) to ![2\pi](00928.jpeg) (![360^\circ](01145.jpeg)), and the dependent variable is the distance ![r_2(\theta)](01406.jpeg).

![ellipse_in_polar_coordinates](01408.jpeg)

Figure 6.21: The function ![r_2(\theta)](01409.jpeg) in polar coordinates specifies the distance between the point ![E](01410.jpeg) on the ellipse and the focal point ![F_2](01399.jpeg) for all angles.

The function that describes an ellipse in polar coordinates is

![r_2(\theta) = \frac{a(1-\varepsilon^2)}{1 + \varepsilon\cos(\theta)}\, ,](01411.jpeg)

where the angle ![\theta](00944.jpeg) is measured with respect to the semi-major axis. The distance is smallest when ![\theta=0](01215.jpeg) with ![r_2(0)= a- c = a(1-\varepsilon)](01412.jpeg) and largest when ![\theta=\pi](01413.jpeg) with ![r_2(\pi)=a+c = a(1+\varepsilon)](01414.jpeg).

###[Calculating the orbit of the Earth](part0006_split_005.md)

The motion of the Earth around the Sun is an ellipse with the Sun positioned at the focus ![F_2](01387.jpeg). We can therefore use the polar coordinates formula ![r_2(\theta)](01406.jpeg) to describe the distance of the Earth from the Sun. The eccentricity of Earth’s orbit around the Sun is ![\varepsilon = 0.01671123](01415.jpeg), and the half-length of the major axis is ![a=149\,598\,261](01416.jpeg) km. We substitute these values into the general formula for ![r_2(\theta)](01406.jpeg) and obtain the following equation:

![r_{2}(\theta) = \frac{149\,556\,484}{1 + 0.01671123\cos(\theta)} \; \;  \text{km}.](01417.jpeg)

The point where the Earth is closest to the Sun is called the _perihelion_. It occurs when ![\theta=0](01215.jpeg), which happens around the 3rd of January. The moment where the Earth is most distant from the Sun is called the _aphelion_ and corresponds to the angle ![\theta=\pi](01413.jpeg). Earth’s _aphelion_ happens around the 3rd of July.

Let’s use the formula for ![r_2(\theta)](01406.jpeg) to predict the _perihelion_ and _aphelion_ distances of Earth’s orbit:

![\begin{align*}    r_{2,\textrm{peri}} = r_2(0)   &= \frac{149556483}{1 + 0.01671123\cos(0)} = 147\,098\,290 \text{ km}, \\    r_{2,\textrm{aphe}} = r_2(\pi)  &= \frac{149556483}{1 + 0.01671123\cos(\pi)} = 152\,098\,232 \text{ km}.   \end{align*}](01418.jpeg)

Google “perihelion” and “aphelion” to verify that the above predictions are accurate. It’s kind of cool that a mathematical formula can describe the motion of our planet, don’t you think?

![diagram-sun-earth](01419.jpeg)

Figure 6.22: The orbit of the Earth around the Sun. Key points of the orbit are labelled. The seasons in the Northern hemisphere are also indicated.

The angle ![\theta](00944.jpeg) of the Earth relative to the Sun can be described as a function of time ![\theta(t)](01420.jpeg). The exact formula of the function ![\theta(t)](01420.jpeg) that describes the angle as a function of time is[fairly complicated](./Kepler's_laws_of_planetary_motion.md), so we won’t go into the details. Let’s simply look at the values of ![\theta(t)](01420.jpeg) with ![t](00349.jpeg) measured in days shown in[Table 6.1](part0006_split_005.md). We’ll begin on Jan 3rd.

![t](00349.jpeg) in days

1

2

![\cdots](01421.jpeg)

182

![\cdots](01421.jpeg)

365

365.2422

date

Jan 3

Jan 4

![\cdots](01421.jpeg)

July 3

![\cdots](01421.jpeg)

Jan 2

?

![\theta(t)](01420.jpeg) in ![^\circ](01422.jpeg)

0

![\cdots](01421.jpeg)

180

![\cdots](01421.jpeg)

359.7614

360

![\theta(t)](01420.jpeg) in rad

0

![\cdots](01421.jpeg)

![\pi](00057.jpeg)

![\cdots](01421.jpeg)

6.2790

![2\pi](00928.jpeg)

Table 6.1: The angular position of the Earth as a function of time. Note the extra amount of “day” that is roughly equal to ![\frac{1}{4}=0.25](01423.jpeg). We account for this discrepancy by adding an extra day to the calendar once every four years.

###[Newton’s insight](part0006_split_005.md)

Contrary to common belief, Newton did not discover his theory of gravitation because an apple fell on his head while sitting under a tree. What actually happened is that he started from Kepler’s laws of motion, which describe the exact elliptical orbit of the Earth as a function of time. Newton asked, “What kind of force would cause two bodies to spin around each other in an elliptical orbit?” He determined that the gravitational force between the Sun of mass ![M](01424.jpeg) and the Earth of mass ![m](00053.jpeg) must be of the form ![F_g=\frac{GMm}{r^2}](01425.jpeg).

For now, let’s give props to Newton for connecting the dots, and props to Johannes Kepler for studying the orbital periods, and Tycho Brahe for doing all the astronomical measurements. Above all, we owe some props to the ellipse for being such an awesome shape!

###[Exercises](part0006_split_005.md)

E6.10 The focal points of the ellipse with equation ![\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1](01426.jpeg) are ![F_1=(-c,0)](01427.jpeg) and ![F_2=(c,0)](01428.jpeg), as illustrated in[Figure 6.20](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md). Use the definition of the ellipse ![r_1 + r_2 = \textrm{const.}](01429.jpeg) to compute the value of the parameter ![c](00256.jpeg) in terms of the parameters ![a](00014.jpeg) and ![b](00074.jpeg).

###[Links](part0006_split_005.md)

\[ Interactive graph of an ellipse \]

[https://www.desmos.com/calculator/kgmh67lroj](./kgmh67lroj.md)

\[ Further reading about Earth-Sun geometry \]

[`http://www.physicalgeography.net/fundamentals/6h.html`](./6h.md)
