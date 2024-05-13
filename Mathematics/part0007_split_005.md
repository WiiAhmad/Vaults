Chapter 7    

##[7.5 Complex numbers](part0007_split_005.md)

By now, you’ve heard about complex numbers ![\mathbb{C}](00062.jpeg). The word “complex” is an intimidating word. Surely it must be a complex task to learn about the complex numbers. That may be true in general, but it helps if you know about vectors. Complex numbers are similar to two-dimensional vectors ![\vec{v} \in \mathbb{R}^2](01550.jpeg). We add and subtract complex numbers like vectors. Complex numbers also have components, length, and “direction.” If you understand vectors, you will understand complex numbers at almost no additional mental cost.

We’ll begin with a practical problem.

####[Example](part0007_split_005.md)

Suppose you’re asked to solve the following quadratic equation:

![x^2 + 1 = 0.](01764.jpeg)

You’re looking for a number ![x](00015.jpeg), such that ![x^2=-1](01765.jpeg). If you are only allowed to give real answers (the set of real numbers is denoted ![\mathbb{R}](00060.jpeg)), then there is no answer to this question. In other words, this equation has no solutions. Graphically speaking, this is because the quadratic function ![f(x)=x^2 + 1](01766.jpeg) does not cross the ![x](00015.jpeg)\-axis.

However, we’re not taking no for an answer! If we insist on solving for ![x](00015.jpeg) in the equation ![x^2 + 1 = 0](01767.jpeg), we can imagine a new number ![i](01768.jpeg) that satisfies ![i^2=-1](01769.jpeg). We call ![i](01768.jpeg) the unit imaginary number. The solutions to the equation are therefore ![x_1=i](01770.jpeg) and ![x_2=-i](01771.jpeg). There are two solutions because the equation is quadratic. We can check that ![i^2 + 1 = -1 +1 = 0](01772.jpeg) and also ![(-i)^2 +1 = (-1)^2i^2 + 1 = i^2 +1 = 0](01773.jpeg).

Thus, while the equation ![x^2 + 1=0](01767.jpeg) has no real solutions, it _does_ have solutions if we allow the answers to be imaginary numbers.

###[Definitions](part0007_split_005.md)

Complex numbers have a real part and an imaginary part:

-   ![i](01768.jpeg): the unit imaginary number ![i = \sqrt{-1}](01774.jpeg) or ![i^2 = -1](01769.jpeg)
-   ![bi](01775.jpeg): an imaginary number that is equal to ![b](00074.jpeg) times ![i](01768.jpeg)
-   ![\mathbb{R}](00060.jpeg): the set of real numbers
-   ![\mathbb{C}](00062.jpeg): the set of complex numbers ![\mathbb{C} = \{ a + bi \;  | \;  a,b \in \mathbb{R} \}](01776.jpeg)
-   ![z=a+bi](01777.jpeg): a complex number
    -   ![\textrm{Re}\{ z \}=a](01778.jpeg): the real part of ![z](00656.jpeg)
    -   ![\textrm{Im}\{ z \}=b](01779.jpeg): the imaginary part of ![z](00656.jpeg)
-   ![\overline{z}](01780.jpeg): the _complex conjugate_ of ![z](00656.jpeg). If ![z=a+bi](01777.jpeg), then ![\overline{z}=a-bi](01781.jpeg).

The polar representation of complex numbers:

-   ![z= |z|\angle \varphi_z= |z|\cos\varphi_z + i|z|\sin\varphi_z](01782.jpeg)
-   ![|z|=\sqrt{ \overline{z}z }=\sqrt{a^2+b^2}](01783.jpeg): the _magnitude_ of ![z=a+bi](01777.jpeg)
-   ![\varphi_z=\tan^{-1}(b/a)](01784.jpeg): the _phase_ or _argument_ of ![z=a+bi](01777.jpeg)
-   ![\textrm{Re}\{ z \} = |z|\cos \varphi_z](01785.jpeg)
-   ![\textrm{Im}\{ z \} = |z|\sin \varphi_z](01786.jpeg)

###[Formulas](part0007_split_005.md)

####[Addition and subtraction](part0007_split_005.md)

Just as we performed the addition of vectors component by component, we perform addition on complex numbers by adding the real parts together and adding the imaginary parts together:

![(a+bi) + (c+di) = (a+c) + (b+d)i.](01787.jpeg)

####[Polar representation](part0007_split_005.md)

We can give a geometric interpretation of the complex numbers by extending the real number line into a two-dimensional plane called the _complex plane_. The horizontal axis in the complex plane measures the _real_ part of the number. The vertical axis measures the _imaginary_ part. Complex numbers are points in the complex plane.

![complex_number](01788.gif)

Figure 7.13: The complex number ![z=a+bi](01789.jpeg) corresponds to the point with coordinates ![(a,b)](01790.jpeg) in the complex plane.

It is possible to represent any complex number ![z=a+bi](01777.jpeg) in terms of its _magnitude_ and its _phase_:

![z= |z|\angle \varphi_z = \underbrace{|z|\cos\varphi_z}_a + \underbrace{|z|\sin\varphi_z}_bi.](01791.jpeg)

The _magnitude_ (or _absolute value_) of a complex number ![z=a+bi](01777.jpeg) is

![|z|=\sqrt{a^2+b^2}.](01792.jpeg)

This corresponds to the _length_ of the vector that represents the complex number in the complex plane. The formula is obtained by using Pythagoras’ theorem.

The _phase_, also known as the _argument_ of the complex number ![z=a+bi](01777.jpeg) is given by the formula

![\varphi_z = \arg z =  \texttt{atan2(}b\texttt{,}a\texttt{)} =       \left\{ \begin{array}{ll}      \!\!\tan^{-1}\!\big(\tfrac{b}{a}\big)    & \textrm{ if } a > 0,      \\      \!\! \pi + \tan^{-1}\!\!\big(\tfrac{b}{a}\big)   & \textrm{ if } a < 0,      \\      \!\! \frac{\pi}{2}        & \textrm{ if } a=0 \textrm{ and }  b > 0,  \\      \!\!-\frac{\pi}{2}        & \textrm{ if } a=0 \textrm{ and }  b < 0.     \end{array}\right.](01793.jpeg)

The phase corresponds to the angle that ![z](00656.jpeg) forms with the real axis.

We previously saw this complicated-looking formula with four cases when we talked about converting from Cartesian coordinates to polar coordinates for points [Section 6.4](part0006_split_004.md)) and vectors [Section 7.2](part0007_split_002.md)). When a certain formula comes up three times in a math book, this should tell you the author _really_ wants you to know it. Seriously, do me a favour and revisit the exercise [6.4.4](part0006_split_004.md) (page 6.4.4) and the exercise [7.3.4](part0007_split_003.md) (page 7.3.4).

Computer algebra systems provide the two-input inverse tangent function `atan2`, which is the easiest way to calculate the phase ![\varphi_z](01794.jpeg) for the complex number ![z=a+bi](01777.jpeg). The function `atan2` handles all four cases automatically and always computes the correct phase ![\varphi_z](01794.jpeg).

In addition to the vector-like operations we can perform on complex numbers, like computing their magnitude and phase, we can also perform other operations on complex numbers that are not defined for vectors. The set of complex numbers ![\mathbb{C}](00062.jpeg) is a _field_. This means, in addition to the addition and subtraction operations, we can also perform multiplication and division with complex numbers.

####[Multiplication](part0007_split_005.md)

The product of two complex numbers is computed using the usual rules of algebra:

![\begin{align*}     (a+bi)(c+di) &= a(c+di) + bi(c+di)   \\        &= ac+adi + bci + bdi^2  \\        &= (ac - bd) + (ad + bc)i.    \end{align*}](01795.jpeg)

In the polar representation, the product formula is

![(p\angle \phi)(q\angle \psi) = pq \angle (\phi + \psi).](01796.jpeg)

To multiply two complex numbers, multiply their magnitudes and add their phases.

#####[Example](part0007_split_005.md)

Verify that ![z \,\overline{z} = a^2+b^2 = |z|^2](01797.jpeg).

####[Division](part0007_split_005.md)

Let’s look at the procedure for dividing complex numbers:

![\frac{(a+bi)}{(c+di)}      = \frac{(a+bi)}{(c+di)}\frac{(c-di)}{(c-di)}      = (a+bi)\frac{(c-di)}{(c^2+d^2)}      = (a+bi)\frac{\overline{c+di}}{|c+di|^2}.](01798.jpeg)

In other words, to divide the number ![z](00656.jpeg) by the complex number ![s](01799.jpeg), compute ![\overline{s}](01800.jpeg) and ![|s|^2=s\overline{s}](01801.jpeg) and then use

![z/s = z\frac{ \overline{s} }{ |s|^2 }.](01802.jpeg)

You can think of ![\displaystyle \frac{ \overline{s} }{ |s|^2 }](01803.jpeg) as being equivalent to ![s^{-1}](01804.jpeg).

#####[Cardano’s example](part0007_split_005.md)

One of the earliest examples of reasoning involving complex numbers was given by Gerolamo Cardano in his 1545 book _Ars Magna_. Cardano wrote, “If someone says to you, divide 10 into two parts, one of which multiplied into the other shall produce 40, it is evident that this case or question is impossible.” We want to find numbers ![x_1](00455.jpeg) and ![x_2](00456.jpeg) such that ![x_1+x_2=10](01805.jpeg) and ![x_1x_2=40](01806.jpeg). This sounds kind of impossible. Or is it?

“Nevertheless,” Cardano said, “we shall solve it in this fashion:

![x_1 = 5 + \sqrt{15}i \; \; \text{and} \; \; x_2 = 5 - \sqrt{15}i.\textrm{''}](01807.jpeg)

When you add ![x_1 + x_2](01808.jpeg) you obtain 10. When you multiply the two numbers the answer is

![\begin{align*}     x_1x_2   &= \left(5 + \sqrt{15}i\right)\!\left(5 - \sqrt{15}i\right)       \\       &=  25 -5\sqrt{15}i + 5\sqrt{15}i -  \sqrt{15}^2i^2 = 25 + 15 =  40.    \end{align*}](01809.jpeg)

Hence ![5 + \sqrt{15}i](01810.jpeg) and ![5 - \sqrt{15}i](01811.jpeg) are two numbers whose sum is ![10](00246.jpeg) and whose product is 40.

#####[Example 2](part0007_split_005.md)

Let’s compute the product of ![-1](00308.jpeg) and ![i](01768.jpeg). The answer is obviously ![-i](01812.jpeg), but let’s look at this simple calculation geometrically. The polar representation of the number ![i](01768.jpeg) is ![1\angle\frac{\pi}{2}](01813.jpeg). Multiplication of any complex number ![z=|z|\angle \varphi_z](01814.jpeg) by ![i](01768.jpeg) corresponds to adding ![\frac{\pi}{2}](00129.jpeg) to the phase of the number:

![zi = (|z|\angle \varphi_z)(1\angle\tfrac{\pi}{2})       =  (|z| \cdot 1)\angle(\varphi_z+\tfrac{\pi}{2})     = |z|\angle(\varphi_z+\tfrac{\pi}{2}).](01815.jpeg)

In other words, multiplication by ![i](01768.jpeg) is equivalent to applying a ![\frac{\pi}{2}](00129.jpeg) (![90^\circ](01178.jpeg)) counterclockwise rotation in the complex plane. We can therefore interpret the answer ![(-1)(i)=-i](01816.jpeg) as the complex number ![-1=1 \angle \pi](01817.jpeg) experiencing a ![\frac{\pi}{2}](00129.jpeg) rotation to arrive at ![1 \angle(\pi + \tfrac{\pi}{2})=1 \angle \tfrac{3\pi}{2}=-i](01818.jpeg).

#####[Example 3](part0007_split_005.md)

Find the polar representation of ![z=-3-i](01819.jpeg) and compute ![z^{6}](01820.jpeg). Let’s denote the polar representation of ![z](00656.jpeg) by ![z = r \angle \varphi](01821.jpeg) as shown in[Figure 7.14](part0007_split_005.md). We find ![r=\sqrt{3^2 +1^2}=\sqrt{10}](01822.jpeg) and ![\varphi=\tan^{-1}(\frac{1}{3})+\pi=0.322+\pi](01823.jpeg). Using the polar representation, we can easily compute ![z^{6}](01820.jpeg):

![z^{6}         = r^{6} \angle (6\varphi)        = (\sqrt{10})^{6} \angle \, 6(0.322+\pi)        = 10^{3} \angle 1.932 + 6\pi        = 10^{3} \angle 1.932.](01824.jpeg)

Note we can ignore multiples of ![2\pi](00928.jpeg) in the phase. We thus find the value of ![z^6](01820.jpeg) is ![1000\cos(1.932) + 1000\sin(1.932)i=-353.4 +935.5i](01825.jpeg).

![complex_number_example1](01826.gif)

Figure 7.14: The complex number ![z=3-i](01827.jpeg) has magnitude ![r=\sqrt{10}](01828.jpeg) and phase ![\varphi=0.322+\pi=3.463](01829.jpeg).

####[Fundamental theorem of algebra](part0007_split_005.md)

The fundamental theorem of algebra states that any polynomial of degree ![n](00054.jpeg), ![P(x) = a_nx^n + \cdots + a_2x^2 + a_1x + a_0](01830.jpeg), can be written as

![P(x) = a_n (x - z_1)(x - z_2) \cdots (x-z_n),](01831.jpeg)

where ![z_i \in \mathbb{C}](01832.jpeg) are the polynomial’s roots. In other words, the equation ![P(x)=0](00884.jpeg) has ![n](00054.jpeg) solutions: the complex numbers ![z_1](01833.jpeg), ![z_2](01834.jpeg), …, ![z_n](01835.jpeg). Before today, you might have said the equation ![x^2+1=0](01767.jpeg) has no solutions. Now you know its solutions are the complex numbers ![z_1=i](01836.jpeg) and ![z_2=-i](01837.jpeg).

The theorem is “fundamental” because it tells us we’ll never need to invent numbers “fancier” than the complex numbers to solve polynomial equations. To understand why this is important, recall that each set of numbers is associated with a different class of equations.[Figure 1.1](part0001_split_002.md) on page 1.1 shows the nested containment structure of the number sets ![\mathbb{N}](00048.jpeg), ![\mathbb{Z}](00225.jpeg), ![\mathbb{Q}](00051.jpeg), ![\mathbb{R}](00060.jpeg), and ![\mathbb{C}](00062.jpeg). The natural numbers ![\mathbb{N}](00048.jpeg) appear as solutions of the equation ![m+n=x](01838.jpeg), where ![m](00053.jpeg) and ![n](00054.jpeg) are natural numbers (denoted ![m,n \in \mathbb{N}](01839.jpeg)). The integers ![\mathbb{Z}](00225.jpeg) are the solutions to equations of the form ![x+m=n](01840.jpeg), where ![m,n \in \mathbb{N}](01839.jpeg). The rational numbers ![\mathbb{Q}](00051.jpeg) are necessary to solve for ![x](00015.jpeg) in ![mx=n](01841.jpeg), with ![m,n \in \mathbb{Z}](01842.jpeg). To find the solutions of ![x^2=2](01843.jpeg), we need the real numbers ![\mathbb{R}](00060.jpeg). And in this section, we learned that the solutions to the equation ![x^2 = -1](01765.jpeg) are complex numbers ![\mathbb{C}](00062.jpeg). At this point you might be wondering if you’re attending some sort of math party, where mathematicians write down complicated equations and—just for the fun of it—invent new sets of numbers to describe the solutions to these equations. Can this process continue indefinitely?

Nope. The party ends with ![\mathbb{C}](00062.jpeg). The fundamental theorem of algebra guarantees that any polynomial equation you could come up with—no matter how complicated it is—has solutions that are complex numbers ![\mathbb{C}](00062.jpeg).

####[Euler’s formula](part0007_split_005.md)

It turns out the exponential function is related to the functions sine and cosine. Lo and behold, we have _Euler’s formula_:

![e^{i\theta} = \cos \theta + i\sin \theta \,.](01844.jpeg)

Inputting an imaginary number to the exponential function outputs a complex number that contains both ![\cos](00751.jpeg) and ![\sin](00935.jpeg). Euler’s formula gives us an alternate notation for the polar representation of complex numbers: ![z=|z|\angle\varphi_z = |z|e^{i\varphi_z}](01845.jpeg).

If you want to impress your friends with your math knowledge, plug ![\theta=\pi](01413.jpeg) into the above equation to find

![e^{i\pi} = \cos(\pi) + i\sin(\pi)= -1,](01846.jpeg)

which can be rearranged to obtain the equation ![e^{i\pi} + 1 = 0](01847.jpeg). The equation ![e^{i\pi} + 1 = 0](01847.jpeg) is called _Euler’s identity_, and it shows a relationship between the five most important numbers in all of mathematics: Euler’s number ![e=2.71828\ldots{}](01848.jpeg), ![\pi=3.14159\ldots](01849.jpeg), the imaginary number ![i](01768.jpeg), 1, and zero. It’s kind of cool to see all these important numbers reunited in one equation, don’t you agree?

One way to understand the equation ![e^{i\pi} + 1 = 0](01847.jpeg), is to think of ![e^{i\pi}](01850.jpeg) as the polar representation of the complex number ![z=1e^{i\pi}=1\angle\pi](01851.jpeg), which is the same as ![1](00211.jpeg) rotated counterclockwise by ![\pi](00057.jpeg) radians (![180^\circ](01127.jpeg)) in the complex plane. We know ![e^{i\pi} = 1\angle\pi = -1](01852.jpeg) and so ![e^{i\pi} + 1 = 0](01847.jpeg).

####[De Moivre’s formula](part0007_split_005.md)

By replacing ![\theta](00944.jpeg) in Euler’s formula with ![n\theta](01853.jpeg), we obtain de Moivre’s formula:

![\left( \cos \theta + i \sin \theta \right)^n = \cos n\theta + i \sin n\theta.](01854.jpeg)

De Moivre’s formula makes sense if you think of the complex number ![z=e^{i\theta}=\cos\theta+i\sin\theta](01855.jpeg), raised to the ![n](00054.jpeg)th power:

![(\cos \theta + i \sin \theta)^n=z^n = (e^{i\theta})^n = e^{in\theta}=\cos n\theta + i \sin n\theta.](01856.jpeg)

Setting ![n=2](01857.jpeg) in de Moivre’s formula, we can derive the double angle formulas (page 6.3.1.1) as the real and imaginary parts of the following equation:

![(\cos^2 \theta - \sin^2 \theta) + (2\sin \theta \cos \theta )i = \cos(2\theta) + \sin(2\theta)i.](01858.jpeg)

###[Links](part0007_split_005.md)

\[ Intuitive proof of the fundamental theorem of algebra \]

[`https://www.youtube.com/watch?v=shEk8sz1oOw`](./watch_v=shEk8sz1oOw.md)
