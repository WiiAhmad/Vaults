Chapter 6    

##[6.3 Trigonometric identities](part0006_split_003.md)

There are a number of important relationships between the values of the functions ![\sin](00935.jpeg) and ![\cos](00751.jpeg). Here are three of these relationships, known as _trigonometric identities_. There about a dozen other identities that are less important, but you should memorize these three.

The three identities to remember are:

####[1. Unit hypotenuse](part0006_split_003.md)

![\sin^2 \theta + \cos^2 \theta = 1.](01276.jpeg)

The unit hypotenuse identity is true by the Pythagoras theorem and the definitions of sin and cos. The sum of the squares of the sides of a triangle is equal to the square of the hypotenuse.

####[2. Sine angle sum](part0006_split_003.md)

![\sin(a + b)=\sin(a)\cos(b) + \sin(b)\cos(a).](01277.jpeg)

The mnemonic for this identity is “sico + sico.”

####[3. Cosine angle sum](part0006_split_003.md)

![\cos(a + b)=\cos(a)\cos(b) - \sin(a)\sin(b).](01278.jpeg)

The mnemonic for this identity is “coco ![-](00454.jpeg) sisi.” The negative sign is there because it’s not good to be a sissy.

###[Derived formulas](part0006_split_003.md)

If you remember the above three formulas, you can derive pretty much all the other trigonometric identities.

####[Double angle formulas](part0006_split_003.md)

Starting from the sico + sico identity and setting ![a=b=x](01279.jpeg), we can derive the following identity:

![\sin(2x) = 2\sin(x)\cos(x).](01280.jpeg)

Starting from the coco-sisi identity, we obtain

![\begin{align*}      \cos(2x)      &\;  = \cos^2(x) - \sin^2(x) \\            &\; =\; 2\cos^2(x) - 1      \; = 2\left(1 - \sin^2(x)\right) - 1      \; = 1 - 2\sin^2(x).    \end{align*}](01281.jpeg)

The formulas for expressing ![\sin(2x)](01282.jpeg) and ![\cos(2x)](01283.jpeg) in terms of ![\sin(x)](00905.jpeg) and ![\cos(x)](00906.jpeg) are called _double angle formulas_.

If we rewrite the double-angle formula for ![\cos(2x)](01283.jpeg) to isolate the ![\sin^2](01284.jpeg) or the ![\cos^2](01285.jpeg) term, we obtain the _power-reduction formulas_:

![\cos^2(x) = \frac{1}{2}\left(1+\cos(2x)\right), \qquad      \sin^2(x) = \frac{1}{2}\left(1-\cos(2x)\right).](01286.jpeg)

####[Self-similarity](part0006_split_003.md)

Sin and cos are periodic functions with period ![2\pi](00928.jpeg). Adding a multiple of ![2\pi](00928.jpeg) to the function’s input does not change the function:

![\sin(x + 2\pi)= \sin(x), \qquad  \cos(x+2\pi)=\cos(x).](01287.jpeg)

This follows because adding a multiple of ![2\pi](00928.jpeg) brings us back to the same point on the unit circle.

Furthermore, sin and cos have symmetries with respect to zero,

![\sin(-x)=-\sin(x), \qquad   \cos(-x)=\cos(x),](01288.jpeg)

within each ![\pi](00057.jpeg) half-cycle,

![\sin(\pi-x)=\sin(x), \qquad   \cos(\pi-x)=-\cos(x),](01289.jpeg)

and within each full ![2\pi](00928.jpeg) cycle,

![\sin(2\pi-x)=-\sin(x), \qquad   \cos(2\pi-x)=\cos(x).](01290.jpeg)

Take the time to revisit[Figure 5.14](part0005_split_002.md) (page 5.14),[Figure 5.17](part0005_split_002.md) (page 5.17), and[Figure 6.12](part0006_split_002.md) (page 6.12) to visually confirm that all the equations shown above are true. Knowing the points where the functions take on the same values (symmetries) or take on opposite values (anti-symmetries) is very useful in calculations.

####[Sin is cos, cos is sin](part0006_split_003.md)

It shouldn’t be surprising if I tell you that sin and cos are actually ![\frac{\pi}{2}](00129.jpeg)\-shifted versions of each other:

![\cos(x)=\sin\!\left(x\!+\!\tfrac{\pi}{2}\right)\!,       \qquad      \sin(x) = \cos\!\left(x\!-\!\tfrac{\pi}{2}\right)\!.](01291.jpeg)

####[Formulas for sums and products](part0006_split_003.md)

Here are some formulas for transforming sums into products:

![\sin\!\left(a\right)+\sin\!\left(b\right)=2\sin\!\left(\tfrac{1}{2}(a+b)\right)\cos\!\left(\tfrac{1}{2}(a-b)\right),](01292.jpeg)

![\sin\!\left(a\right)-\sin\!\left(b\right)=2\sin\!\left(\tfrac{1}{2}(a-b)\right)\cos\!\left(\tfrac{1}{2}(a+b)\right),](01293.jpeg)

![\cos\!\left(a\right)+\cos\!\left(b\right)=2\cos\!\left(\tfrac{1}{2}(a+b)\right)\cos\!\left(\tfrac{1}{2}(a-b)\right),](01294.jpeg)

![\cos\!\left(a\right)-\cos\!\left(b\right)=-2\sin\!\left(\tfrac{1}{2}(a+b)\right)\sin\!\left(\tfrac{1}{2}(a-b)\right).](01295.jpeg)

And here are some formulas for transforming products into sums:

![\sin(a)\cos(b) = \tfrac{1}{2}\Big(\sin(a+b)+\sin(a-b)\Big),](01296.jpeg)

![\sin(a)\sin(b) = \tfrac{1}{2}\Big(\cos(a-b)-\cos(a+b)\Big),](01297.jpeg)

![\cos(a)\cos(b) = \tfrac{1}{2}\Big(\cos(a-b)+\cos(a+b)\Big).](01298.jpeg)

###[Discussion](part0006_split_003.md)

The above formulas will come in handy when you need to find some unknown in an equation, or when you are trying to simplify

###[Exercises](part0006_split_003.md)

E6.6 Given ![a=\pi](01299.jpeg) and ![b=\frac{\pi}{2}](01300.jpeg), find

**a)** ![\sin(a+b)](01301.jpeg) **b)** ![\cos(2a)](01302.jpeg) **c)** ![\cos(a+b)](01303.jpeg)

E6.7 Simplify the following expressions and compute their value without using a calculator.

**a)** ![\cos(x)+\cos(\pi-x)](01304.jpeg) **b)** ![2\sin^2(x)+\cos(2x)](01305.jpeg)

**c)** ![\sin(\frac{5\pi}{4}) \sin(-\frac{\pi}{4})](01306.jpeg) **d)** ![2\cos(\frac{5\pi}{4}) \cos(-\frac{\pi}{4}) \cos(\pi)](01307.jpeg)
