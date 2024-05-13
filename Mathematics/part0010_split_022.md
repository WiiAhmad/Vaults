Chapter 10    

##[Complex numbers](part0010_split_022.md)

\>>> from sympy import I, re, im, Abs, arg, conjugate

Consider the quadratic equation ![x^2=-1](01765.jpeg). There are no real solutions to this equation, but we can define an imaginary number ![i =\sqrt{-1}](01774.jpeg) (denoted `I` in `SymPy`) that satisfies this equation:

\>>> I\*I
-1
>>> solve( x\*\*2 + 1 , x)
\[I, -I\]

The solutions are ![x=i](02892.jpeg) and ![x=-i](02893.jpeg), and indeed we can verify that ![i^2+1=0](02894.jpeg) and ![(-i)^2+1=0](02895.jpeg) since ![i^2=-1](01769.jpeg).

The complex numbers ![\mathbb{C}](00062.jpeg) are defined as ![\{ a+bi \,|\, a,b \in \mathbb{R} \}](02896.jpeg). Complex numbers contain a real part and an imaginary part:

\>>> z = 4 + 3\*I
>>> z 
4 + 3\*I
>>> re(z)
4
>>> im(z)
3 

The _polar_ representation of a complex number is ![z\!=\!|z|\angle\theta\!= \!|z|e^{i\theta}](02897.jpeg). For a complex number ![z=a+bi](01777.jpeg), the quantity ![|z|=\sqrt{a^2+b^2}](02860.jpeg) is known as the _absolute value_ of ![z](00656.jpeg), and ![\theta](00944.jpeg) is its _phase_ or its _argument_:

\>>> Abs(z)
5
>>> arg(z)
atan(3/4)

The complex conjugate of ![z=a+bi](01777.jpeg) is the number ![\overline{z} = a-bi](01781.jpeg), which has the same absolute value as ![z](00656.jpeg) but opposite phase:

\>>> conjugate( z )
4 - 3\*I

Complex conjugation is important for computing the absolute value of ![z](00656.jpeg) (![|z|=\sqrt{ z\overline{z} }](02898.jpeg)) and for division by ![z](00656.jpeg) (![\frac{1}{z} = \frac{\overline{z}}{|z|^2}](02899.jpeg)).

###[Euler’s formula](part0010_split_022.md)

\>>> from sympy import expand, rewrite

[Euler’s formula](./Euler's_formula.md) shows an important relation between the exponential function ![e^x](00589.jpeg) and the trigonometric functions ![\sin(x)](00905.jpeg) and ![\cos(x)](00906.jpeg):

![e^{ix} = \cos x + i \sin x.](02900.jpeg)

To obtain this result in `SymPy`, you must specify that the number ![x](00015.jpeg) is real and also tell `expand` that you’re interested in complex expansions:

\>>> x = symbols('x', real=True)
>>> expand(exp(I\*x), complex=True)
cos(x) + I\*sin(x) 
>>> re( exp(I\*x) ) 
cos(x)
>>> im( exp(I\*x) ) 
sin(x)

Basically, ![\cos(x)](00906.jpeg) is the real part of ![e^{ix}](02901.jpeg), and ![\sin(x)](00905.jpeg) is the imaginary part of ![e^{ix}](02901.jpeg). Whaaat? I know it’s weird, but weird things are bound to happen when you input imaginary numbers to functions.
