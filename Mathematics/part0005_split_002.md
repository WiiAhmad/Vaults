Chapter 5    

##[5.2 Functions reference](part0005_split_002.md)

Your _function vocabulary_ determines how well you can express yourself mathematically in the same way your English vocabulary determines how well you can express yourself in English. The following pages aim to embiggen your function vocabulary, so you’ll know how to handle the situation when a teacher tries to pull some trick on you at the final. Here are the ten most important functions in math:

1.  Straight line ![f(x) = mx+b](00807.jpeg) (see pages 5.2.1 and 8.1.5)
2.  Quadratic function ![f(x)=x^2](00298.jpeg) (pages 5.2.2, 5.3.5, and 6.6)
3.  Square root ![f(x) = \sqrt{x}](00337.jpeg) (page 5.2.3)
4.  Absolute value ![f(x)=|x|](00808.jpeg) (page 5.2.4)
5.  Polynomials ![f(x)=a_0 + a_1x + a_2x^2 + \cdots + a_nx^n](00809.jpeg) (page 5.2.5)
6.  Sine ![f(x)=\sin(x)](00810.jpeg) (pages 5.2.6, 5.3.6, and 6.2)
7.  Cosine ![f(x)=\cos(x)](00811.jpeg) (pages 5.2.7 and 6.2)
8.  Tangent ![f(x)=\tan(x)](00812.jpeg) (page 5.2.8)
9.  Exponential ![f(x)=e^{x}](00813.jpeg) (pages 5.2.9 and 8.2.4)
10.  Logarithm ![f(x)=\ln(x)](00814.jpeg) (page 5.2.10)

If you’re seeing these functions for the first time, don’t worry about remembering all the facts and properties on the first reading. We’ll use these functions throughout the rest of the book, so you’ll have plenty of time to become familiar with them. Remember to return to this section if you ever get stuck on a function.

To build mathematical intuition, it’s essential you understand functions’ graphs. Memorizing the definitions and properties of functions gets a lot easier with visual accompaniment. Indeed, remembering what the function “looks like” is a great way to train yourself to recognize various types of functions.[Figure 5.9](part0005_split_002.md) shows the graphs of some of the functions we’ll use in this book.

![3x3_functions_miniplots](00815.jpeg)

Figure 5.9: We’ll see many types of function graphs in the next pages.

###[Line](part0005_split_002.md)

The equation of a line describes an input-output relationship where the change in the output is _proportional_ to the change in the input. The equation of a line is

![f(x) = mx+b.](00816.jpeg)

The constant ![m](00053.jpeg) describes the slope of the line. The constant ![b](00074.jpeg) is called the ![y](00018.jpeg)\-intercept and it is the value of the function when ![x=0](00776.jpeg).

Consider what relationship the equation of ![f(x)](00288.jpeg) describes for different values of ![m](00053.jpeg) and ![b](00074.jpeg). What happens when ![m](00053.jpeg) is positive? What happens when ![m](00053.jpeg) is negative?

####[Graph](part0005_split_002.md)

![graph_of_2x_plus_3](00817.jpeg)

Figure 5.10: The graph of the function ![f(x)=2x-3](00818.jpeg). The slope is ![m=2](00819.jpeg). The ![y](00674.jpeg)\-intercept of this line is ![b=-3](00820.jpeg). The ![x](00632.jpeg)\-intercept is at ![x=\frac{3}{2}](00821.jpeg).

####[Properties](part0005_split_002.md)

-   Domain: ![\mathbb{R}](00060.jpeg). The function ![f(x)=mx+b](00807.jpeg) is defined for all reals.
-   Image: ![\mathbb{R}](00060.jpeg) if ![m\neq 0](00822.jpeg). If ![m=0](00823.jpeg) the function is constant ![f(x)=b](00710.jpeg), so the image set contains only a single number ![\{ b\}](00824.jpeg).
-   ![x=-b/m](00825.jpeg): the ![x](00015.jpeg)\-intercept of ![f(x)=mx+b](00807.jpeg). The ![x](00015.jpeg)\-intercept is obtained by solving ![f(x)=0](00379.jpeg).
-   The inverse to the line ![f(x)=mx+b](00807.jpeg) is ![f^{-1}(x)=\frac{1}{m}(x-b)](00826.jpeg), which is also a line.

####[General equation](part0005_split_002.md)

A line can also be described in a more symmetric form as a relation:

![Ax + By = C.](00827.jpeg)

This is known as the _general_ equation of a line. The general equation for the line shown in[Figure 5.10](part0005_split_002.md) is ![2x-1y=3](00828.jpeg).

Given the general equation of a line ![Ax + By = C](00829.jpeg) with ![B\neq 0](00830.jpeg), you can convert to the function form ![y=f(x)=mx+b](00831.jpeg) by computing the slope ![m=\frac{-A}{B}](00832.jpeg) and the ![y](00018.jpeg)\-intercept ![b=\frac{C}{B}](00833.jpeg).

###[Square](part0005_split_002.md)

The function ![x](00015.jpeg) _squared_, is also called the _quadratic_ function, or _parabola_. The formula for the quadratic function is

![f(x)=x^2.](00834.jpeg)

The name “quadratic” comes from the Latin _quadratus_ for square, since the expression for the area of a square with side length ![x](00015.jpeg) is ![x^2](00026.jpeg).

![quadratic_func](00835.jpeg)

Figure 5.11: Plot of the quadratic function ![f(x)=x^2](00652.jpeg). The graph of the function passes through the following ![(x,y)](00634.jpeg) coordinates: ![(-2,4)](00836.jpeg), ![(-1,1)](00837.jpeg), ![(0,0)](00838.jpeg), ![(1,1)](00839.jpeg), ![(2,4)](00840.jpeg), ![(3,9)](00841.jpeg), etc.

####[Properties](part0005_split_002.md)

-   Domain: ![\mathbb{R}](00060.jpeg). The function ![f(x)=x^2](00298.jpeg) is defined for all numbers.
-   Image: ![\mathbb{R}_+ = \{y \in \mathbb{R} \; | \; y \geq 0 \}](00688.jpeg). The outputs are nonnegative numbers since ![x^2 \geq 0](00842.jpeg), for all real numbers ![x](00015.jpeg).
-   The function ![x^2](00026.jpeg) is the inverse of the square root function ![\sqrt{x}](00681.jpeg).
-   ![f(x)=x^2](00298.jpeg) is _two-to-one_: it sends both ![x](00015.jpeg) and ![-x](00299.jpeg) to the same output value ![x^2=(-x)^2](00843.jpeg).
-   The quadratic function is _convex_, meaning it curves upward.

The set expression ![\{y \in \mathbb{R} \; | \; y \geq 0 \}](00844.jpeg) that we use to define the nonnegative real numbers (![\mathbb{R}_+](00683.jpeg)) is read “the set of real numbers that are greater than or equal to zero.”

###[Square root](part0005_split_002.md)

The square root function is denoted

![f(x) = \sqrt{x} = x^{\frac{1}{2}} .](00845.jpeg)

The square root ![\sqrt{x}](00681.jpeg) is the inverse function of the square function ![x^2](00026.jpeg) when the two functions are defined as ![f : \mathbb{R}_+ \to \mathbb{R}_+](00720.jpeg). The symbol ![\sqrt{c}](00846.jpeg) refers to the _positive_ solution of ![x^2=c](00304.jpeg). Note that ![-\sqrt{c}](00847.jpeg) is also a solution of ![x^2=c](00304.jpeg).

####[Graph](part0005_split_002.md)

![sqrt_of_x](00848.jpeg)

Figure 5.12: The graph of the function ![f(x)=\sqrt{x}](00686.jpeg). The domain of the function is ![\mathbb{R}_+](00687.jpeg) because we can’t take the square root of a negative number.

####[Properties](part0005_split_002.md)

-   Domain: ![\mathbb{R}_+ = \{x \in \mathbb{R} \; | \; x \geq 0 \}](00684.jpeg). The function ![f(x)=\sqrt{x}](00337.jpeg) is only defined for nonnegative inputs. There is no real number ![y](00018.jpeg) such that ![y^2](00849.jpeg) is negative, hence the function ![f(x)=\sqrt{x}](00337.jpeg) is not defined for negative inputs ![x](00015.jpeg).
-   Image: ![\mathbb{R}_+ = \{y \in \mathbb{R} \; | \; y \geq 0 \}](00688.jpeg). The outputs of the function ![f(x)=\sqrt{x}](00337.jpeg) are nonnegative numbers since ![\sqrt{x} \geq 0](00850.jpeg).

In addition to _square_ root, there is also _cube_ root ![f(x) = \sqrt[3]{x}  = x^{\frac{1}{3}}](00851.jpeg), which is the inverse function for the cubic function ![f(x)=x^3](00700.jpeg). We have ![\sqrt[3]{8}=2](00852.jpeg) since ![2\times2\times2=8](00853.jpeg). More generally, we can define the ![n](00054.jpeg)th\-root function ![\sqrt[n]{x}](00538.jpeg) as the inverse function of ![x^n](00539.jpeg).

###[Absolute value](part0005_split_002.md)

The _absolute value_ function tells us the size of numbers without paying attention to whether the number is positive or negative. We can compute a number’s absolute value by _ignoring the sign_ of the number. A number’s absolute value corresponds to its distance from the origin of the number line.

Another way of thinking about the absolute value function is to say it multiplies negative numbers by ![-1](00308.jpeg) to “cancel” their negative sign:

![f(x)=|x|=  \left\{  \begin{array}{rl}  x &\text{ if } x\geq 0, \\  -x &\text{ if } x<0. \end{array} \right.](00854.jpeg)

####[Graph](part0005_split_002.md)

![absolute_value_of_x](00855.jpeg)

Figure 5.13: The graph of the absolute value function ![f(x)=|x|](00856.jpeg).

####[Properties](part0005_split_002.md)

-   Domain: ![\mathbb{R}](00060.jpeg). The function ![f(x)=|x|](00808.jpeg) is defined for all inputs.
-   Image: ![\mathbb{R}_+ = \{y \in \mathbb{R} \; | \; y \geq 0 \}](00688.jpeg)
-   The combination of squaring followed by square-root is equivalent to the absolute value function:
    
    ![\sqrt{ x^2 }  = |x|,](00857.jpeg)
    
    since squaring destroys the sign.
    

###[Polynomials](part0005_split_002.md)

The polynomials are a very useful family of functions. For example, quadratic polynomials of the form ![f(x) = ax^2 + bx +c](00491.jpeg) often arise when describing physics phenomena.

The general equation for a polynomial function of degree ![n](00054.jpeg) is

![f(x)=a_0 + a_1x + a_2x^2 + a_3x^3 + \cdots + a_nx^n.](00858.jpeg)

The constants ![a_i](00859.jpeg) are known as the _coefficients_ of the polynomial.

####[Parameters](part0005_split_002.md)

-   ![x](00015.jpeg): the variable
-   ![a_0](00150.jpeg): the constant term
-   ![a_1](00149.jpeg): the _linear_ coefficient, or _first-order_ coefficient
-   ![a_2](00148.jpeg): the _quadratic_ coefficient
-   ![a_3](00147.jpeg): the _cubic_ coefficient
-   ![a_n](00860.jpeg): the ![n](00054.jpeg)th order coefficient
-   ![n](00054.jpeg): the _degree_ of the polynomial. The degree of ![f(x)](00288.jpeg) is the largest power of ![x](00015.jpeg) that appears in the polynomial.

A polynomial of degree ![n](00054.jpeg) has ![n+1](00861.jpeg) coefficients: ![a_0,a_1,a_2,\ldots, a_n](00862.jpeg).

####[Properties](part0005_split_002.md)

-   Domain: ![\mathbb{R}](00060.jpeg). Polynomials are defined for all inputs.
-   The roots of ![f(x)](00288.jpeg) are the values of ![x](00015.jpeg) for which ![f(x)=0](00379.jpeg).
-   The image of a polynomial function depends on the coefficients.
-   The sum of two polynomials is also a polynomial.

The most general first-degree polynomial is a line ![f(x) = mx + b](00807.jpeg), where ![m](00053.jpeg) and ![b](00074.jpeg) are arbitrary constants. The most general second-degree polynomial is ![f(x) = a_2 x^2 + a_1 x + a_0](00863.jpeg), where again ![a_0](00150.jpeg), ![a_1](00149.jpeg), and ![a_2](00148.jpeg) are arbitrary constants. We call ![a_k](00864.jpeg) the _coefficient_ of ![x^k](00865.jpeg), since this is the number that appears in front of ![x^k](00865.jpeg). Following the pattern, a third-degree polynomial will look like ![f(x) = a_3 x^3 + a_2 x^2 + a_1 x + a_0](00866.jpeg).

In general, a polynomial of degree ![n](00054.jpeg) has the equation

![f(x) = a_n x^n + a_{n-1}x^{n-1} + \cdots + a_2 x^2 + a_1 x + a_0.](00867.jpeg)

You can add two polynomials by adding together their coefficients:

![\begin{align*}      f(x) + g(x)    &= (a_n x^n + \cdots + a_1 x + a_0)       \; + \;        (b_n x^n + \cdots + b_1 x + b_0)\\    &= (a_n+b_n) x^n + \cdots + (a_1+b_1) x + (a_0+b_0).   \end{align*}](00868.jpeg)

The subtraction of two polynomials works similarly. We can also multiply polynomials together using the general algebra rules for expanding brackets.

### Solving polynomial equations

Very often in math, you will have to _solve_ polynomial equations of the form

![A(x) = B(x),](00869.jpeg)

where ![A(x)](00870.jpeg) and ![B(x)](00871.jpeg) are both polynomials. Recall from earlier that to _solve_, we must find the values of ![x](00015.jpeg) that make the equality true.

Say the revenue of your company is a function of the number of products sold ![x](00015.jpeg), and can be expressed as ![R(x)=2x^2 + 2x](00872.jpeg). Say also the cost you incur to produce ![x](00015.jpeg) objects is ![C(x)=x^2+5x+10](00873.jpeg). You want to determine the amount of product you need to produce to break even, that is, so that revenue equals cost: ![R(x)=C(x)](00874.jpeg). To find the break-even value ![x](00015.jpeg), solve the equation

![2x^2 + 2x = x^2+5x+10.](00875.jpeg)

This may seem complicated since there are ![x](00015.jpeg)s all over the place. No worries! We can turn the equation into its “standard form,” and then use the quadratic formula. First, move all the terms to one side until only zero remains on the other side:

![\begin{align*}    2x^2 + 2x \; \; \; -x^2   &= \cancel{x^2}+5x+10  \; \; \;  - \cancel{x^2}  \\    x^2 + 2x \; \; \; -5x    &= \cancel{5x}+10  \; \; \; -\cancel{5x} \\    x^2 - 3x \; \; \; -10    &= \cancel{10}  \; \; \; -\cancel{10}  \\    x^2 - 3x -10          &= 0.     \end{align*}](00876.jpeg)

Remember, if we perform the same operations on both sides of the equation, the resulting equation has the same solutions. Therefore, the values of ![x](00015.jpeg) that satisfy ![x^2 - 3x -10  = 0](00877.jpeg), namely ![x=-2](00878.jpeg) and ![x=5](00803.jpeg), also satisfy ![2x^2 + 2x = x^2+5x+10](00879.jpeg), which is the original problem we’re trying to solve.

This “shuffling of terms” approach will work for any polynomial equation ![A(x)=B(x)](00880.jpeg). We can always rewrite it as ![C(x)=0](00881.jpeg), where ![C(x)](00882.jpeg) is a new polynomial with coefficients equal to the difference of the coefficients of ![A](00667.jpeg) and ![B](00409.jpeg). Don’t worry about which side you move all the coefficients to because ![C(x)=0](00881.jpeg) and ![0=-C(x)](00883.jpeg) have exactly the same solutions. Furthermore, the degree of the polynomial ![C](00266.jpeg) can be no greater than that of ![A](00667.jpeg) or ![B](00409.jpeg).

The form ![C(x)=0](00881.jpeg) is the _standard form_ of a polynomial, and we’ll explore several formulas you can use to find its solution(s).

####[Formulas](part0005_split_002.md)

The formula for solving the polynomial equation ![P(x)=0](00884.jpeg) depends on the _degree_ of the polynomial in question.

For a first-degree polynomial equation, ![P_1(x) = mx + b = 0](00885.jpeg), the solution is ![x=\frac{-b}{m}](00886.jpeg): just move ![b](00074.jpeg) to the other side and divide by ![m](00053.jpeg).

For a second-degree polynomial,

![P_2(x) = ax^2 + bx + c = 0,](00887.jpeg)

the solutions are ![x_1=\frac{-b + \sqrt{ b^2 -4ac}}{2a}](00888.jpeg) and ![x_2=\frac{-b - \sqrt{b^2-4ac}}{2a}](00889.jpeg).

If ![b^2-4ac < 0](00478.jpeg), the solutions will involve taking the square root of a negative number. In those cases, we say no real solutions exist.

There is also a formula for polynomials of degree ![3](00106.jpeg) and ![4](00136.jpeg), but they are complicated. For polynomials with order ![\geq 5](00890.jpeg), there does not exist a general analytical solution.

####[Using a computer](part0005_split_002.md)

When solving real-world problems, you’ll often run into much more complicated equations. To find the solutions of anything more complicated than the quadratic equation, I recommend using a computer algebra system like `SymPy`: [http://live.sympy.org](./live.sympy.org.md)`.

To make `SymPy` solve the standard-form equation ![C(x)=0](00881.jpeg), call the function `solve(expr,var)`, where the expression `expr` corresponds to ![C(x)](00882.jpeg), and `var` is the variable you want to solve for. For example, to solve ![x^2-3x+2=0](00891.jpeg), type in the following:

 >>> solve(x\*\*2 - 3\*x + 2, x)          # usage: solve(expr, var)
 \[1, 2\]		

The function `solve` will find the solutions to any equation of the form `expr = 0`. In this case, we see the solutions are ![x=1](00773.jpeg) and ![x=2](00380.jpeg).

Another way to solve the equation is to factor the polynomial ![C(x)](00882.jpeg) using the function `factor` like this:

 >>> factor(x\*\*2 - 3\*x + 2)            # usage: factor(expr)
 (x - 1)\*(x - 2)	

We see that ![x^2-3x+2 = (x-1)(x-2)](00892.jpeg), which confirms the two roots are indeed ![x=1](00773.jpeg) and ![x=2](00380.jpeg).

To learn more about `SymPy`, check out Appendix[1](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md) on page 1, which talks about all the `SymPy` functions that are available to you.

####[Substitution trick](part0005_split_002.md)

Sometimes you can solve fourth-degree polynomials by using the quadratic formula. Say you’re asked to solve for ![x](00015.jpeg) in

![x^4 - 7x^2 + 10  = 0.](00893.jpeg)

Imagine this problem is on your exam, where you are not allowed to use a computer. How does the teacher expect you to solve for ![x](00015.jpeg)? The trick is to substitute ![y=x^2](00495.jpeg) and rewrite the same equation as

![y^2 - 7y + 10  = 0,](00894.jpeg)

which you can solve by applying the quadratic formula. If you obtain the solutions ![y=\alpha](00895.jpeg) and ![y=\beta](00896.jpeg), then the solutions to the original fourth-degree polynomial are ![x=\pm\sqrt{\alpha}](00897.jpeg) and ![x=\pm\sqrt{\beta}](00898.jpeg), since ![y=x^2](00495.jpeg).

Since we’re not taking an exam right now, we are allowed to use the computer to find the roots:

 >>> solve(y\*\*2 - 7\*y + 10, y)
 \[2, 5\]
 >>> solve(x\*\*4 - 7\*x\*\*2 + 10, x)
 \[sqrt(2), -sqrt(2), sqrt(5), -sqrt(5)\]

Note how the second-degree polynomial has two roots, while the fourth-degree polynomial has four roots.

####[Even and odd functions](part0005_split_002.md)

The polynomials form an entire family of functions. Depending on the choice of degree ![n](00054.jpeg) and coefficients ![a_0](00150.jpeg), ![a_1](00149.jpeg), ![\ldots](00899.jpeg), ![a_n](00860.jpeg), a polynomial function can take on many different shapes. Consider the following observations about the symmetries of polynomials:

-   If a polynomial contains only even powers of ![x](00015.jpeg), like ![f(x)=1+x^2-x^4](00900.jpeg) for example, we call this polynomial _even_. Even polynomials have the property ![f(x)=f(-x)](00901.jpeg). The sign of the input doesn’t matter.
-   If a polynomial contains only odd powers of ![x](00015.jpeg), for example ![g(x)=x+x^3-x^9](00902.jpeg), we call this polynomial _odd_. Odd polynomials have the property ![g(x)=-g(-x)](00903.jpeg).
-   If a polynomial has both even and odd terms then it is neither even nor odd.

The terminology of _odd_ and _even_ applies to functions in general and not just to polynomials. All functions that satisfy ![f(x)=f(-x)](00901.jpeg) are called _even functions_, and all functions that satisfy ![f(x)=-f(-x)](00904.jpeg) are called _odd functions_.

###[Sine](part0005_split_002.md)

The sine function represents a fundamental unit of vibration. The graph of ![\sin(x)](00905.jpeg) _oscillates_ up and down and crosses the ![x](00015.jpeg)\-axis multiple times. The shape of the graph of ![\sin(x)](00905.jpeg) corresponds to the shape of a vibrating string. See[Figure 5.14](part0005_split_002.md).

In the remainder of this book, we’ll meet the function ![\sin(x)](00905.jpeg) many times. We’ll define the function ![\sin(x)](00905.jpeg) more formally as a trigonometric ratio in[Section 6.2](part0006_split_002.md). In[Chapter 7](Vectors.md) we’ll use ![\sin(x)](00905.jpeg) and ![\cos(x)](00906.jpeg) (another trigonometric ratio) to work out the _components_ of vectors. The sine function also describes waves and periodic motion.

At this point in the book, however, we don’t want to go into too much detail about all these applications. Let’s hold off on the discussion about vectors, triangles, angles, and ratios of lengths of sides and instead just focus on the graph of the function ![f(x) = \sin(x)](00810.jpeg).

####[Graph](part0005_split_002.md)

![sin_of_x](00907.jpeg)

Figure 5.14: The graph of the function ![y=\sin(x)](00908.jpeg) passes through the following ![(x,y)](00634.jpeg) coordinates: ![(0,0)](00838.jpeg), ![(\frac{\pi}{6},\frac{1}{2})](00909.jpeg), ![(\frac{\pi}{4},\frac{\sqrt{2}}{2})](00910.jpeg), ![(\frac{\pi}{3},\frac{\sqrt{3}}{2})](00911.jpeg), ![(\frac{\pi}{2},1)](00912.jpeg), ![(\frac{2\pi}{3},\frac{\sqrt{3}}{2})](00913.jpeg), ![(\frac{3\pi}{4},\frac{\sqrt{2}}{2})](00914.jpeg), ![(\frac{5\pi}{6},\frac{1}{2})](00915.jpeg), and ![(\pi,0)](00916.jpeg). For ![x](00632.jpeg) between ![\pi](00917.jpeg) and ![2\pi](00918.jpeg), the function’s graph has the same shape it has for ![x](00632.jpeg) between ![0](00919.jpeg) and ![\pi](00917.jpeg), but with negative values.

![the_numer_pi](00920.jpeg)

Figure 5.15: The function ![f(x)=\sin(x)](00921.jpeg) crosses the ![x](00632.jpeg)\-axis at ![x=\pi](00922.jpeg).

Let’s start at ![x=0](00776.jpeg) and follow the graph of the function ![\sin(x)](00905.jpeg) as it goes up and down. The graph starts from ![(0,0)](00923.jpeg) and smoothly increases until it reaches the maximum value at ![x=\frac{\pi}{2}](00924.jpeg). Afterward, the function comes back down to cross the ![x](00015.jpeg)\-axis at ![x=\pi](00925.jpeg). After ![\pi](00057.jpeg), the function drops below the ![x](00015.jpeg)\-axis and reaches its minimum value of ![-1](00308.jpeg) at ![x=\frac{3\pi}{2}](00926.jpeg). It then travels up again to cross the ![x](00015.jpeg)\-axis at ![x=2\pi](00927.jpeg). This ![2\pi](00928.jpeg)\-long cycle repeats after ![x=2\pi](00927.jpeg). This is why we call the function _periodic_—the shape of the graph repeats.

![sin_of_x_many_cycles](00929.jpeg)

Figure 5.16: The graph of ![\sin(x)](00930.jpeg) from ![x=0](00763.jpeg) to ![x=2\pi](00931.jpeg) repeats periodically everywhere else on the number line.

####[Properties](part0005_split_002.md)

-   Domain: ![\mathbb{R}](00060.jpeg). The function ![f(x)=\sin(x)](00810.jpeg) is defined for all input values.
-   Image: ![\{ y \in \mathbb{R} \; | \;  -1 \leq y \leq 1 \}](00932.jpeg). The outputs of the sine function are always between ![-1](00308.jpeg) and ![1](00211.jpeg).
-   Roots: ![\{\,\ldots, -3\pi, -2\pi,-\pi,0,\pi,2\pi,3\pi, \ldots\,\}](00933.jpeg). The function ![\sin(x)](00905.jpeg) has roots at all multiples of ![\pi](00057.jpeg).
-   The function is periodic, with period ![2\pi](00928.jpeg): ![\sin(x) = \sin(x+2\pi)](00934.jpeg).
-   The ![\sin](00935.jpeg) function is _odd_: ![\sin(x)=-\sin(-x)](00936.jpeg)
-   Relation to ![\cos](00751.jpeg): ![\sin^2 x + \cos^2 x = 1](00937.jpeg)
-   Relation to ![\csc](00938.jpeg): ![\csc(x) = \frac{1}{\sin x}](00939.jpeg) (![\csc](00938.jpeg) is read _cosecant_)
-   The inverse function of ![\sin(x)](00905.jpeg) is denoted as ![\sin^{-1}(x)](00940.jpeg) or ![\arcsin(x)](00941.jpeg), not to be confused with ![(\sin(x))^{-1}=\frac{1}{\sin(x)} = \csc(x)](00942.jpeg).
-   The number ![\sin(\theta)](00943.jpeg) is the length-ratio of the vertical side and the hypotenuse in a right-angle triangle with angle ![\theta](00944.jpeg) at the base.

####[Links](part0005_split_002.md)

\[ See the Wikipedia page for nice illustrations \]

[`http://en.wikipedia.org/wiki/Sine`](./Sine.md)

###[Cosine](part0005_split_002.md)

The cosine function is the same as the sine function _shifted_ by ![\frac{\pi}{2}](00129.jpeg) to the left: ![\cos(x) = \sin(x+\frac{\pi}{2})](00945.jpeg). Thus everything you know about the sine function also applies to the cosine function.

####[Graph](part0005_split_002.md)

![cos_of_x](00946.jpeg)

Figure 5.17: The graph of the function ![y=\cos(x)](00947.jpeg) passes through the following ![(x,y)](00634.jpeg) coordinates: ![(0,1)](00948.jpeg), ![(\frac{\pi}{6},\frac{\sqrt{3}}{2})](00949.jpeg), ![(\frac{\pi}{4},\frac{\sqrt{2}}{2})](00910.jpeg), ![(\frac{\pi}{3},\frac{1}{2})](00950.jpeg), ![(\frac{\pi}{2},0)](00951.jpeg), ![(\frac{2\pi}{3},-\frac{1}{2})](00952.jpeg), ![(\frac{3\pi}{4}, -\frac{\sqrt{2}}{2})](00953.jpeg), ![(\frac{5\pi}{6}, -\frac{\sqrt{3}}{2})](00954.jpeg), and ![(\pi,-1)](00955.jpeg).

The cos function starts at ![\cos(0)=1](00956.jpeg), then drops down to cross the ![x](00015.jpeg)\-axis at ![x=\frac{\pi}{2}](00924.jpeg). Cos continues until it reaches its minimum value at ![x=\pi](00925.jpeg). The function then moves upward, crossing the ![x](00015.jpeg)\-axis again at ![x=\frac{3\pi}{2}](00926.jpeg), and reaching its maximum value again at ![x=2\pi](00927.jpeg).

####[Properties](part0005_split_002.md)

-   Domain: ![\mathbb{R}](00060.jpeg)
-   Image: ![\{ y \in \mathbb{R} \; | \;  -1 \leq y \leq 1 \}](00932.jpeg)
-   Roots: ![\{\, \ldots, \, -\frac{3\pi}{2}, \, -\frac{\pi}{2}, \frac{\pi}{2}, \frac{3\pi}{2},  \frac{5\pi}{2}, \, \ldots\,\}](00957.jpeg)
-   Relation to ![\sin](00935.jpeg): ![\sin^2 x + \cos^2 x = 1](00937.jpeg)
-   Relation to ![\sec](00958.jpeg): ![\sec(x) = \frac{1}{\cos x}](00959.jpeg) (![\sec](00958.jpeg) is read _secant_)
-   The inverse function of ![\cos(x)](00906.jpeg) is denoted ![\cos^{-1}(x)](00960.jpeg) or ![\arccos(x)](00961.jpeg).
-   The ![\cos](00751.jpeg) function is _even_: ![\cos(x) = \cos(-x)](00962.jpeg)
-   The number ![\cos(\theta)](00963.jpeg) is the length-ratio of the horizontal side and the hypotenuse in a right-angle triangle with angle ![\theta](00944.jpeg) at the base

###[Tangent](part0005_split_002.md)

The tangent function is the ratio of the sine and cosine functions:

![f(x)=\tan(x)= \frac{ \sin(x) }{ \cos(x) }.](00964.jpeg)

####[Graph](part0005_split_002.md)

![tan_of_x](00965.jpeg)

Figure 5.18: The graph of the function ![f(x)=\tan(x)](00966.jpeg).

####[Properties](part0005_split_002.md)

-   Domain: ![\{ x\in \mathbb{R} \;|\; x\neq \frac{(2n+1)\pi}{2} \textrm{ for any } n \in \mathbb{Z} \}](00967.jpeg)
-   Image: ![\mathbb{R}](00060.jpeg)
-   The function ![\tan](00968.jpeg) is periodic with period ![\pi](00057.jpeg).
-   The ![\tan](00968.jpeg) function “blows up” at values of ![x](00015.jpeg) where ![\cos x=0](00969.jpeg). These are called _asymptotes_ of the function and their locations are ![x=\ldots, \frac{-3\pi}{2},\frac{-\pi}{2},\frac{\pi}{2},\frac{3\pi}{2},\ldots](00970.jpeg).
-   Value at ![x=0](00776.jpeg): ![\tan(0)=\frac{0}{1}=0](00971.jpeg), because ![\sin(0)=0](00972.jpeg).
-   Value at ![x=\frac{\pi}{4}](00973.jpeg): ![\tan\left(\frac{\pi}{4} \right)              = \frac{ \sin(\frac{\pi}{4}) }{ \cos(\frac{\pi}{4}) }             = \frac{ \frac{\sqrt{2}}{2}  }{ \frac{\sqrt{2}}{2}  }             = 1](00974.jpeg).
-   The number ![\tan(\theta)](00975.jpeg) is the length-ratio of the vertical and the horizontal sides in a right-angle triangle with angle ![\theta](00944.jpeg).
-   The inverse function of ![\tan(x)](00976.jpeg) is denoted ![\tan^{-1}(x)](00977.jpeg) or ![\arctan(x)](00978.jpeg).
-   The inverse tangent function is used to compute the angle at the base in a right-angle triangle with horizontal side length ![\ell_h](00979.jpeg) and vertical side length ![\ell_v](00980.jpeg): ![\theta=\tan^{-1}\!\left(\frac{\ell_v}{\ell_h}\right)](00981.jpeg).

###[Exponential](part0005_split_002.md)

The exponential function base ![e=2.7182818\ldots](00504.jpeg) is denoted

![f(x)=e^{x} = \exp(x).](00982.jpeg)

####[Graph](part0005_split_002.md)

![exp_x](00983.jpeg)

Figure 5.19: The graph of the exponential function ![f(x)=e^x](00984.jpeg) passes through the following points: ![(-2,\frac{1}{e^2})](00985.jpeg), ![(-1,\frac{1}{e})](00986.jpeg), ![(0,1)](00948.jpeg), ![(1,e)](00987.jpeg), ![(2,e^2)](00988.jpeg), ![(3,e^3)](00989.jpeg), ![(4,e^4)](00990.jpeg), etc.

####[Properties](part0005_split_002.md)

-   Domain: ![\mathbb{R}](00060.jpeg)
-   Image: ![\{ y \in \mathbb{R} \; | \;  y > 0 \}](00991.jpeg)
-   ![f(a)f(b)=f(a+b)](00992.jpeg) since ![e^ae^b=e^{a+b}](00993.jpeg)

A more general exponential function would be ![f(x)=Ae^{\gamma x}](00994.jpeg), where ![A](00667.jpeg) is the initial value, and ![\gamma](00995.jpeg) (the Greek letter _gamma_) is the _rate_ of the exponential. For ![\gamma > 0](00996.jpeg), the function ![f(x)](00288.jpeg) is increasing, as in[Figure 5.19](part0005_split_002.md). For ![\gamma < 0](00997.jpeg), the function is decreasing and tends to zero for large values of ![x](00015.jpeg). The case ![\gamma=0](00998.jpeg) is special since ![e^{0}=1](00999.jpeg), so ![f(x)](00288.jpeg) is a constant of ![f(x)=A1^x=A](01000.jpeg).

####[Links](part0005_split_002.md)

[ The exponential function ![2^x](./00503.jpeg.md) evaluated \]

[`http://www.youtube.com/watch?v=e4MSN6IImpI`](./watch_v=e4MSN6IImpI.md)

###[Natural logarithm](part0005_split_002.md)

The natural logarithm function is denoted

![f(x)=\ln(x) = \log_e(x).](01001.jpeg)

The function ![\ln(x)](00588.jpeg) is the inverse function of the exponential ![e^x](00589.jpeg).

####[Graph](part0005_split_002.md)

![ln_of_x](01002.jpeg)

Figure 5.20: The graph of the function ![\ln(x)](01003.jpeg) passes through the following coordinates: ![(\frac{1}{e^2},-2)](01004.jpeg), ![(\frac{1}{e},-1)](01005.jpeg), ![(1,0)](01006.jpeg), ![(e, 1)](01007.jpeg), ![(e^2, 2)](01008.jpeg), ![(e^3, 3)](01009.jpeg), ![(e^4, 4)](01010.jpeg), etc.

####[Properties](part0005_split_002.md)

-   Domain: ![\{ x \in \mathbb{R} \; | \;  x > 0 \}](01011.jpeg)
-   Image: ![\mathbb{R}](00060.jpeg)

###[Exercises](part0005_split_002.md)

E5.1 Find the domain, the image, and the roots of ![f(x)=2\cos(x)](01012.jpeg).

E5.2 What are the degrees of the following polynomials? Are they even, odd, or neither?

**a)** ![p(x)=x^2-5x^4+1](01013.jpeg) **b)** ![q(x)=x-x^3+x^5-x^7](01014.jpeg)

E5.3 Solve for ![x](00015.jpeg) in the following polynomial equations.

**a)** ![3x+x^2=x-15+2x^2](01015.jpeg) **b)** ![3x^2-4x-4+x^3=x^3+2x+2](01016.jpeg)
