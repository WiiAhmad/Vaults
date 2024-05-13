Chapter 2    

##[2.2 Solving quadratic equations](part0002_split_002.md)

What would you do if asked to solve for ![x](00015.jpeg) in the quadratic equation ![2x^2 = 4x + 6](00446.jpeg)? This is called a _quadratic equation_ since it contains the unknown variable ![x](00015.jpeg) squared. The name comes from the Latin _quadratus_, which means square. Quadratic equations appear often, so mathematicians created a general formula for solving them. In this section, we’ll learn about this formula and use it to put some quadratic equations in their place.

Before we can apply the formula, we need to rewrite the equation we are trying to solve in the following form:

![ax^2 + bx + c = 0.](00331.jpeg)

This is called the _standard form_ of the quadratic equation. We obtain this form by moving all the numbers and ![x](00015.jpeg)s to one side and leaving only ![0](00101.jpeg) on the other side. For example, to transform the quadratic equation ![2x^2 = 4x + 6](00446.jpeg) into standard form, we subtract ![4x + 6](00447.jpeg) from both sides of the equation to obtain ![2x^2 - 4x - 6 = 0](00448.jpeg). What are the values of ![x](00015.jpeg) that satisfy this equation?

####[Quadratic formula](part0002_split_002.md)

The solutions to the equation ![ax^2 + bx + c = 0](00340.jpeg) for ![a\neq0](00449.jpeg) are

![x_1 = \frac{-b + \sqrt{b^2-4ac} }{2a}        \qquad \textrm{and} \qquad \; \;       x_2 = \frac{-b - \sqrt{b^2-4ac} }{2a} \, .](00450.jpeg)

The quadratic formula is usually abbreviated ![x=\frac{-b \pm \sqrt{b^2 - 4ac}}{2a}](00451.jpeg), where the sign “![\pm](00452.jpeg)” stands for both “![+](00453.jpeg)” and “![-](00454.jpeg).” The notation “![\pm](00452.jpeg)” allows us to express both solutions ![x_1](00455.jpeg) and ![x_2](00456.jpeg) in one equation, but you should keep in mind there are really two solutions.

Let’s see how the quadratic formula is used to solve the equation ![2x^2 - 4x - 6 = 0](00448.jpeg). Finding the two solutions requires the simple mechanical task of identifying ![a=2](00457.jpeg), ![b=-4](00458.jpeg), and ![c=-6](00459.jpeg), then plugging these values into the two parts of the formula:

![x_1 = \frac{4 + \sqrt{4^2-4(2)(-6)} }{4} = \frac{4 + \sqrt{16+48} }{4} = \frac{4 + \sqrt{64} }{4} = 3,](00460.jpeg)

![x_2 = \frac{4 - \sqrt{4^2-4(2)(-6)} }{4} = \frac{4 - \sqrt{16+48} }{4}  = \frac{4 - \sqrt{64} }{4} = -1.](00461.jpeg)

We can easily verify that value ![x_1=3](00462.jpeg) and ![x_2=-1](00463.jpeg) both satisfy the original equation ![2x^2 = 4x + 6](00446.jpeg).

####[Proof of the quadratic formula](part0002_split_002.md)

Every claim made by a mathematician comes with a _proof_, which is a step-by-step argument that shows why the claim is true. It’s easy to see where a proof starts and where a proof ends in mathematical texts. Each proof begins with the heading _Proof_ (usually in italics) and has the symbol “![\qedsymbol](00464.jpeg)” at its end. The purpose of these demarcations is to give readers the option to skip the proof. It’s not necessary to read and understand the proofs of all math statements, but reading proofs can often lead you to a more solid understanding of the material.

I want you to see the proof of the quadratic formula because it’s an important result that you’ll use very often to solve math problems. Reading the proof will help you understand where the quadratic formula comes from. The proof relies on the completing-the-square technique from the previous section, and some basic algebra operations. You can totally handle this!

We’re starting from the quadratic equation ![ax^2 + bx + c = 0](00340.jpeg), and we’re making the additional assumption that ![a\neq 0](00449.jpeg). We want to find the value or values of ![x](00015.jpeg) that satisfy this equation.

The first thing we want to do is divide by ![a](00014.jpeg) to obtain the equivalent equation

![x^2 + \frac{b}{a}x  + \frac{c}{a} = 0.](00465.jpeg)

We are allowed to divide by ![a](00014.jpeg) since we assumed that ![a \neq 0](00449.jpeg).

Next we apply the _complete the square_ trick to the quadratic expression, to obtain an equivalent expression of the form ![(x+?)^2 + ?](00466.jpeg). Recall that the trick for completing the square is to choose the number inside the bracket to be half the coefficient of the linear term of the quadratic expression, which is ![\frac{b}{2a}](00467.jpeg) in this case. We must also subtract the square of this term outside the bracket in order to maintain the equality. After completing the square, we’re left with the following equation:

![\left(x + \frac{b}{2a} \right)^{\!2} + \frac{c}{a} - \frac{b^2}{4a^2} = 0.](00468.jpeg)

From here, we use the standard digging-toward-the-![x](00015.jpeg) procedure. Move all constants to the right-hand side,

![\left(x + \frac{b}{2a}\right)^{\!2} \;  = \;  \frac{b^2}{4a^2} -\frac{c}{a}\,,](00469.jpeg)

and take the square root of both sides to undo the square function:

![\; \; \quad \qquad x + \frac{b}{2a}  \; = \; \pm \sqrt{ \frac{b^2}{4a^2} -\frac{c}{a} }\,.](00470.jpeg)

Since any number and its opposite have the same square, taking the square root gives us two possible solutions, which we denote using the “![\pm](00452.jpeg)” symbol.

Next we subtract ![\frac{b}{2a}](00467.jpeg) from both sides of the equation to isolate ![x](00015.jpeg) and obtain ![x  = - \frac{b}{2a}  \pm \sqrt{ \frac{b^2}{4a^2} -\frac{c}{a} }](00471.jpeg). We tidy up the mess under the square root, ![\sqrt{ \frac{b^2}{4a^2}  -\frac{c}{a} }     = \sqrt{ \frac{b^2}{4a^2} -\frac{4a\,\cdot\, c}{4a\,\cdot\, a} }     = \sqrt{ \frac{b^2 - 4ac}{4a^2}  }     = \frac{\sqrt{b^2 -4ac}  }{ 2a   }](00472.jpeg), and add the fractions on the right-hand side to obtain ![x = \frac{-b \pm \sqrt{b^2-4ac} }{2a}](00451.jpeg). The solutions to the quadratic equation ![ax^2 + bx + c = 0](00340.jpeg) are

![x_1 = \frac{-b + \sqrt{b^2-4ac} }{2a}     \qquad \textrm{and} \qquad     x_2  = \frac{-b - \sqrt{b^2-4ac} }{2a}\,.](00473.jpeg)

This completes the proof of the quadratic formula.

The expression ![b^2-4ac](00474.jpeg) is called the _discriminant_ of the equation. The discriminant tells us important information about the solutions of the equation ![ax^2 + bx + c = 0](00340.jpeg). The solutions ![x_1](00455.jpeg) and ![x_2](00456.jpeg) correspond to real numbers if the discriminant is positive or zero: ![b^2-4ac \geq 0](00475.jpeg). When the discriminant is zero (![b^2-4ac = 0](00476.jpeg)), the equation has only one solution since ![x_1= x_2 = \frac{-b}{2a}](00477.jpeg). If the discriminant is negative, ![b^2-4ac < 0](00478.jpeg), the quadratic formula requires computing the square root of a negative number, which is not allowed for real numbers.

####[Alternative proof](part0002_split_002.md)

To prove the quadratic formula, we don’t necessarily need to show the algebra steps we followed to obtain the formula as outlined above. The quadratic formula states that ![x_1](00455.jpeg) and ![x_2](00456.jpeg) are solutions. To prove the formula is correct we can simply plug ![x_1](00455.jpeg) and ![x_2](00456.jpeg) into the equation ![ax^2 + bx + c = 0](00340.jpeg) to verify that ![x_1](00455.jpeg) and ![x_2](00456.jpeg) are solutions. Verify this on your own.

###[Applications](part0002_split_002.md)

####[The golden ratio](part0002_split_002.md)

The _golden ratio_ is an essential proportion in geometry, art, aesthetics, biology, and mysticism, and is usually denoted as ![\varphi=\frac{1+\sqrt{5}}{2}=1.6180339\ldots](00479.jpeg). This ratio is determined as the positive solution to the quadratic equation

![x^2 -x -1 = 0.](00480.jpeg)

Applying the quadratic formula to this equation yields two solutions,

![x_1 = \frac{1+\sqrt{5}}{2} = \varphi      \qquad      \textrm{and}      \qquad      x_2 = \frac{1-\sqrt{5}}{2} = - \frac{1}{\varphi} \, .](00481.jpeg)

You can learn more about the various contexts in which the golden ratio appears from the[Wikipedia article](./Golden_ratio.md) on the subject.

###[Explanations](part0002_split_002.md)

####[Multiple solutions](part0002_split_002.md)

Often, we are interested in only one of the two solutions to the quadratic equation. It will usually be obvious from the context of the problem which of the two solutions should be kept and which should be discarded. For example, the _time of flight_ of a ball thrown in the air from a height of ![3](00106.jpeg) metres with an initial velocity of ![12](00482.jpeg) metres per second is obtained by solving the equation ![(-4.9)t^2+12t+3=0](00483.jpeg). The two solutions of the quadratic equation are ![t_1=-0.229](00484.jpeg) and ![t_2=2.678](00485.jpeg). The first answer ![t_1](00486.jpeg) corresponds to a time in the past so we reject it as invalid. The correct answer is ![t_2](00487.jpeg). The ball will hit the ground after ![t=2.678](00488.jpeg) seconds.

####[Relation to factoring](part0002_split_002.md)

In the previous section we discussed the _quadratic factoring_ operation by which we could rewrite a quadratic function as the product of a constant and two factors:

![f(x)=ax^2+bx+c=a(x-x_1)(x-x_2).](00489.jpeg)

The two numbers ![x_1](00455.jpeg) and ![x_2](00456.jpeg) are called the _roots_ of the function: these points are where the function ![f(x)](00288.jpeg) touches the ![x](00015.jpeg)\-axis.

You now have the ability to factor any quadratic equation: use the quadratic formula to find the two solutions, ![x_1](00455.jpeg) and ![x_2](00456.jpeg), then rewrite the expression as ![a(x-x_1)(x-x_2)](00490.jpeg).

Some quadratic expressions cannot be factored, however. These “unfactorable” expressions correspond to quadratic functions whose graphs do not touch the ![x](00015.jpeg)\-axis. They have no real solutions (no roots). There is a quick test you can use to check if a quadratic function ![f(x)=ax^2+bx+c](00491.jpeg) has roots (touches or crosses the ![x](00015.jpeg)\-axis) or doesn’t have roots (never touches the ![x](00015.jpeg)\-axis). If ![b^2-4ac>0](00492.jpeg) then the function ![f](00287.jpeg) has two roots. If ![b^2-4ac=0](00476.jpeg), the function has only one root, indicating the special case when the function touches the ![x](00015.jpeg)\-axis at only one point. If ![b^2-4ac<0](00478.jpeg), the function has no roots. In this case, the quadratic formula fails because it requires taking the square root of a negative number, which is not allowed (for now). We’ll come back to the idea of taking square roots of negative numbers in[Section 7.5](part0007_split_005.md) (see page 7.5).

###[Links](part0002_split_002.md)

\[ Algebra explanation of the quadratic formula \][`https://www.youtube.com/watch?v=r3SEkdtpobo`](./watch_v=r3SEkdtpobo.md)

\[ Visual explanation of the quadratic formula derivation \][`https://www.youtube.com/watch?v=EBbtoFMJvFc`](./watch_v=EBbtoFMJvFc.md)

###[Exercises](part0002_split_002.md)

E2.3 Solve for ![x](00015.jpeg) in the quadratic equation ![2x^2-x=3](00493.jpeg).

E2.4 Solve for ![x](00015.jpeg) in the equation ![x^4-4x^2+4=0](00494.jpeg).

Use the substitution ![y=x^2](00495.jpeg).
