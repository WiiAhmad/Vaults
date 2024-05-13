Chapter 2    

##[2.1 Basic rules of algebra](part0002_split_001.md)

It’s important that you know the general rules for manipulating numbers and variables, a process otherwise known as—you guessed it—_algebra_. This little refresher will cover these concepts to make sure you’re comfortable on the algebra front. We’ll also review some important algebraic tricks, like _factoring_ and _completing the square_, which are useful when solving equations.

Let’s define some terminology for referring to different parts of math expressions. When an expression contains multiple things added together, we call those things _terms_. Furthermore, terms are usually composed of many things multiplied together. When a number ![x](00015.jpeg) is obtained as the product of other numbers like ![x=abc](00341.jpeg), we say “![x](00015.jpeg) factors into ![a](00014.jpeg), ![b](00074.jpeg), and ![c](00256.jpeg).” We call ![a](00014.jpeg), ![b](00074.jpeg), and ![c](00256.jpeg) the _factors_ of ![x](00015.jpeg).

![anatomy_of_an_eqn](00342.jpeg)

Figure 2.1: Diagram showing the names used to describe the different parts of the equation ![abc+de=0](00343.jpeg).

Given any three numbers ![a](00014.jpeg), ![b](00074.jpeg), and ![c](00256.jpeg), we can apply the following algebraic properties:

1.  Associative property: ![a+b+c=(a+b)+c=a+(b+c)](00344.jpeg) and ![abc=(ab)c=a(bc)](00088.jpeg)
2.  Commutative property: ![a+b=b+a](00065.jpeg) and ![ab=ba](00087.jpeg)
3.  Distributive property: ![a(b+c)=ab+ac](00345.jpeg)

We use the distributive property every time we _expand_ brackets. For example ![a(b+c+d)=ab + ac + ad](00346.jpeg). The brackets, also known as parentheses, indicate the expression ![(b+c+d)](00347.jpeg) must be treated as a whole; as a factor consisting of three terms. Multiplying this expression by ![a](00014.jpeg) is the same as multiplying each term by ![a](00014.jpeg).

The opposite operation of expanding is called _factoring_, which consists of rewriting the expression with the common parts taken out in front of a bracket: ![ab+ac = a(b+c)](00348.jpeg). In this section, we’ll discuss all algebra operations and illustrate what they’re capable of.

#####[Example](part0002_split_001.md)

Suppose we are asked to solve for ![t](00349.jpeg) in the equation

![7(3 + 4t) = 11(6t - 4).](00350.jpeg)

Since the unknown ![t](00349.jpeg) appears on both sides of the equation, it is not immediately obvious how to proceed.

To solve for ![t](00349.jpeg), we can bring all ![t](00349.jpeg) terms to one side and all constant terms to the other side. First, expand the two brackets to obtain

![21 + 28t = 66t - 44.](00351.jpeg)

Then move things around to relocate all ![t](00349.jpeg)s to the equation’s right-hand side and all constants to the left-hand side:

![21 + 44 = 66t - 28t.](00352.jpeg)

We see ![t](00349.jpeg) is contained in both terms on the right-hand side, so we can “factor it out” by rewriting the equation as

![21 + 44 = t(66 - 28).](00353.jpeg)

The answer is within close reach: ![t = \frac{21 + 44}{66 - 28} = \frac{65}{38}](00354.jpeg).

###[Expanding brackets](part0002_split_001.md)

To _expand_ a bracket is to multiply each term inside the bracket by the factor outside the bracket. The key thing to remember when expanding brackets is to apply the _distributive_ property: ![a(x+y) = ax + ay](00355.jpeg). For longer expressions, we may need to apply the distributive property several times, until there are no more brackets left:

![\begin{align*}    (a+b)(x+y+z) &= a(x+y+z) + b(x+y+z)    \\       &= ax + ay + az + bx + by + bz.   \end{align*}](00356.jpeg)

After expanding the brackets in this expression, we end up with six terms—one term for each of the six possible combinations of products between the terms in ![(a+b)](00357.jpeg) and the terms in ![(x+y+z)](00358.jpeg).

The distributive property is often used to manipulate expressions containing different powers of the variable ![x](00015.jpeg). For instance,

![(x+3)(x+2) = x(x+2) + 3(x+2)  =  x^2 +x2 +3x + 6.](00359.jpeg)

We can use the commutative property on the second term ![x2=2x](00360.jpeg), then combine the two ![x](00015.jpeg) terms into a single term to obtain

![(x+3)(x+2) = x^2 + 5x + 6.](00361.jpeg)

The bracket-expanding and simplification techniques demonstrated above are very common in math, and I recommend you solve some algebra practice problems to get the hang of them. Most math textbooks skip simplification steps and jump straight to the answer, since they assume readers are capable of doing simplifications on their own. It would be too long (and annoying) to show the simplifications for each expression. For example, the sentence “We can rewrite ![(x+3)(x+2)](00362.jpeg) as ![x^2 + 5x + 6](00363.jpeg),” is the short version of the longer sentence, “We can apply the distributive property twice on ![(x+3)(x+2)](00362.jpeg) then combine the terms with the same power of ![x](00015.jpeg) to get ![x^2 + 5x + 6](00363.jpeg).”

It’s not unusual for people to make math mistakes when expanding brackets and manipulating long algebra expressions. To avoid mistakes, use a step-by-step approach and apply only one operation in each step. Write legibly and keep the equations “organized” so it’s easy to check the calculations performed in each step. Consider this slightly-more-complicated algebraic expression and its expansion:

![\begin{align*}    (x+a)(bx^2+cx+d)        &= x(bx^2+cx+d) + a(bx^2+cx+d)   \\       &= bx^3+cx^2+dx \; + \; abx^2 +acx +ad   \\       &= bx^3+ (c+ab)x^2+(d+ac)x +ad.   \end{align*}](00364.jpeg)

Note how we sorted the terms in the final expression according to the different powers of ![x](00015.jpeg), with the terms containing ![x^2](00026.jpeg) grouped together, and the terms containing ![x](00015.jpeg) grouped together. This approach helps keep things organized when dealing with expressions containing many terms.

###[Factoring](part0002_split_001.md)

Factoring involves “taking out” the common parts of a complicated expression in order to make the expression more compact. Suppose we’re given the expression ![6x^2y + 15x](00365.jpeg). We can simplify this expression by taking out the common factors and moving them in front of a bracket. Let’s see how to do this, step by step.

The expression ![6x^2y + 15x](00365.jpeg) has two terms. Let’s split each term into its constituent factors:

![6x^2y + 15x =   (3)(2)(x)(x)y + (5)(3)x.](00366.jpeg)

Since factors ![x](00015.jpeg) and ![3](00106.jpeg) appear in both terms, we can _factor them out_ like this:

![6x^2y + 15x =  3x(2xy+5).](00367.jpeg)

The expression on the right shows ![3x](00368.jpeg) is common to both terms.

Here’s another example of factoring—notice the common factors are taken out and moved in front of the bracket:

![2x^2y + 2x + 4x = 2x(xy +1+2) =  2x(xy+3).](00369.jpeg)

###[Factoring quadratic expressions](part0002_split_001.md)

A _quadratic expression_ is an expression of the form ![ax^2 + bx + c](00370.jpeg). The expression contains a _quadratic term_ ![ax^2](00371.jpeg), a _linear term_ ![bx](00372.jpeg), and a constant term ![c](00256.jpeg). The numbers ![a](00014.jpeg), ![b](00074.jpeg), and ![c](00256.jpeg) are called _coefficients_: the quadratic coefficient is ![a](00014.jpeg), the linear coefficient is ![b](00074.jpeg), and the constant coefficient is ![c](00256.jpeg).

To _factor_ the quadratic expression ![ax^2 + bx + c](00370.jpeg) is to rewrite it as the product of a constant and two factors like ![(x+p)](00373.jpeg) and ![(x+q)](00374.jpeg):

![ax^2 + bx + c = a(x+p)(x+q).](00375.jpeg)

Rewriting quadratic expressions in factored form helps us better understand and describe their properties.

#####[Example](part0002_split_001.md)

Suppose we’re asked to describe the properties of the function ![f(x)=x^2-5x+6](00376.jpeg). Specifically, we’re asked to find the function’s _roots_, which are the values of ![x](00015.jpeg) for which the function equals zero.

Factoring the expression ![x^2-5x+6](00377.jpeg) helps us see its properties more clearly, and makes our job of finding the roots of ![f(x)](00288.jpeg) easier. The factored form of this quadratic expression is

![f(x) = x^2-5x+6 = (x-2)(x-3).](00378.jpeg)

Now we can see at a glance that the values of ![x](00015.jpeg) for which ![f(x)=0](00379.jpeg) are ![x=2](00380.jpeg) and ![x=3](00381.jpeg). When ![x=2](00380.jpeg), the factor ![(x-2)](00382.jpeg) is zero and hence ![f(x)=0](00379.jpeg). Similarly, when ![x=3](00381.jpeg), the factor ![(x-3)](00383.jpeg) is zero so ![f(x)=0](00379.jpeg).

How did we know that the factors of ![x^2-5x+6](00377.jpeg) are ![(x-2)](00382.jpeg) and ![(x-3)](00383.jpeg) in the above example? For simple quadratics like the one above, we can simply _guess_ the values of ![p](00384.jpeg) and ![q](00385.jpeg) in the equation ![x^2-5x+6 = (x+p)(x+q)](00386.jpeg). Before we start guessing, let’s look at the expanded version of the product between ![(x+p)](00373.jpeg) and ![(x+q)](00374.jpeg):

![(x+p)(x+q) = x^2 + (p+q)x + pq.](00387.jpeg)

Note the linear term on the right-hand side contains the sum of the unknowns ![(p+q)](00388.jpeg), while the constant term contains their product ![pq](00389.jpeg). If we want the equation ![x^2-5x+6 = x^2 + (p+q)x + pq](00390.jpeg) to hold, we must find two numbers ![p](00384.jpeg) and ![q](00385.jpeg) whose sum equals ![-5](00391.jpeg) and whose product equals ![6](00328.jpeg). After a couple of attempts we find ![p=-2](00392.jpeg) and ![q=-3](00393.jpeg). This guessing approach is an effective strategy for many of the factoring problems we will likely be asked to solve, since math teachers often choose simple numbers like ![\pm 1](00394.jpeg), ![\pm 2](00395.jpeg), ![\pm 3](00396.jpeg), or ![\pm 4](00397.jpeg) for the constants ![p](00384.jpeg) and ![q](00385.jpeg). For more complicated quadratic expressions, we’ll need to use the quadratic formula, which we’ll talk about in[Section 2.2](part0002_split_002.md).

####[Common quadratic forms](part0002_split_001.md)

Let’s look at some common variations of quadratic expressions you might encounter when doing algebra calculations.

The quadratic expression ![x^2 - p^2](00398.jpeg) is called a _difference of squares_, and it can be obtained by multiplying the factors ![(x+p)](00373.jpeg) and ![(x-p)](00399.jpeg):

![(x+p)(x-p)           = x^2 \; \cancel{- xp} \; \cancel{+px}  \; - p^2     = x^2 - p^2.](00400.jpeg)

There’s no linear term because the ![-xp](00401.jpeg) term cancels the ![+px](00402.jpeg) term. Any time you see an expression like ![x^2-p^2](00398.jpeg), you can know it comes from a product of the form ![(x+p)(x-p)](00403.jpeg).

A _perfect square_ is a quadratic expression that can be written as the product of repeated factors ![(x+p)](00373.jpeg):

![x^2 + 2px + p^2 = (x+p)(x+p) = (x+p)^2.](00404.jpeg)

Note ![x^2 - 2qx + q^2 = (x-q)^2](00405.jpeg) is also a perfect square.

###[Completing the square](part0002_split_001.md)

In this section we’ll learn about an ancient algebra technique called _completing the square_, which allows us to rewrite _any_ quadratic expression of the form ![x^2+Bx+C](00406.jpeg) as a perfect square plus some constant correction factor ![(x+p)^2+k](00407.jpeg). This algebra technique was described in one of the first books on _al-jabr_ (algebra), written by Al-Khwarizmi around the year 800 CE. The name “completing the square” comes from the ingenious geometric construction used by this procedure. Yes, we can use geometry to solve algebra problems!

We assume the starting point for the procedure is a quadratic expression whose quadratic coefficient is one, ![1x^2 + Bx + C](00408.jpeg), and use capital letters ![B](00409.jpeg) and ![C](00266.jpeg) to denote the linear and constant coefficients. The capital letters are to avoid any confusion with the quadratic expression ![ax^2 + bx + c](00370.jpeg), for which ![a\neq 1](00410.jpeg). Note we can always write ![ax^2 + bx + c](00370.jpeg) as ![a(x^2+\frac{b}{a}x + \frac{c}{a})](00411.jpeg) and apply the procedure to the expression inside the brackets, identifying ![\frac{b}{a}](00412.jpeg) with ![B](00409.jpeg) and ![\frac{c}{a}](00413.jpeg) with ![C](00266.jpeg).

First let’s rewrite the quadratic expression ![x^2 + Bx + C](00406.jpeg) by splitting the linear term into two equal parts:

![x^2 + \tfrac{B}{2}x + \tfrac{B}{2}x + C.](00414.jpeg)

We can interpret the first three terms geometrically as follows: the ![x^2](00026.jpeg) term corresponds to a square with side length ![x](00015.jpeg), while the two ![\frac{B}{2}x](00415.jpeg) terms correspond to rectangles with sides ![\frac{B}{2}](00416.jpeg) and ![x](00015.jpeg). See the left side of[Figure 2.2](part0002_split_001.md) for an illustration.

![algebra__completing_the_square](00417.jpeg)

Figure 2.2: To complete the square in the expression ![x^2 +Bx + C](00418.jpeg), we need to add the quantity ![(\frac{B}{2})^2](00419.jpeg), which corresponds to a square (shown in darker colour) with sides equal to half the coefficient of the linear term. We also subtract ![(\frac{B}{2})^2](00419.jpeg) so the overall value of the expression remains unchanged.

The square with area ![x^2](00026.jpeg) and the two rectangles can be positioned to form a larger square with side length ![\big(x + \frac{B}{2}\big)](00420.jpeg). Note there’s a small piece of sides ![\frac{B}{2}](00416.jpeg) by ![\frac{B}{2}](00416.jpeg) missing from the corner. To _complete the square_, we can add a term ![\big(\tfrac{B}{2}\big)^2](00421.jpeg) to this expression. To preserve the equality, we also subtract ![\big(\tfrac{B}{2}\big)^2](00421.jpeg) from the expression to obtain:

![\begin{align*}    x^2 + \tfrac{B}{2}x + \tfrac{B}{2}x \; + C    &\; = \;  \underbrace{x^2 + \tfrac{B}{2}x + \tfrac{B}{2}x + \big(\tfrac{B}{2}\big)^2}_{ }  \; \; - \; \big(\tfrac{B}{2}\big)^2 \; \; + \; C    \\    &\; = \;  \qquad \quad \big(x+ \tfrac{B}{2}\big)^{\!2}  \qquad \; \; \; - \; \big(\tfrac{B}{2}\big)^2 \; \, + \; C.   \end{align*}](00422.jpeg)

The right-hand side of this equation describes the area of the square with side length ![\big(x + \frac{B}{2}\big)](00420.jpeg), minus the area of the small square ![\big(\tfrac{B}{2}\big)^2](00421.jpeg), plus the constant ![C](00266.jpeg), as illustrated on the right side of[Figure 2.2](part0002_split_001.md).

We can summarize the entire procedure in one equation:

![x^2 + Bx + C    =    \big(x \, \, \underbrace{\!+ \; \tfrac{B}{2} \!}_{(1)}\big)^2 \;  + \;  C \; \;   \underbrace{- \; \big(\tfrac{B}{2}\big)^2}_{(2)}.](00423.jpeg)

There are two things to remember when you want to apply the complete-the-square trick: (1) choose the constant inside the bracket to be ![\frac{B}{2}](00416.jpeg) (half of the linear coefficient), and (2) subtract ![\big(\frac{B}{2}\big)^2](00421.jpeg) outside the bracket in order to keep the equation balanced.

####[Solving quadratic equations](part0002_split_001.md)

Suppose we want to solve the quadratic equation ![x^2  + Bx  + C = 0](00424.jpeg). It’s not possible to solve this equation with the digging-toward-the-![x](00015.jpeg) approach from[Section 1.1](part0001_split_001.md) (since ![x](00015.jpeg) appears in both the quadratic term ![x^2](00026.jpeg) and the linear term ![Bx](00425.jpeg)). Enter the completing-the-square trick!

#####[Example](part0002_split_001.md)

Let’s find the solutions of the equation ![x^2+5x+6=0](00426.jpeg). The coefficient of the linear term is ![B=5](00427.jpeg), so we choose ![\frac{B}{2}=\frac{5}{2}](00428.jpeg) for the constant inside the bracket, and subtract ![\big(\tfrac{B}{2}\big)^2 = \big(\tfrac{5}{2}\big)^2](00429.jpeg) outside the bracket to keep the equation balanced. Completing the square gives

![x^2+5x+6  = \left(x+\tfrac{5}{2}\right)^2 + 6 - \big(\tfrac{5}{2}\big)^2 = 0.](00430.jpeg)

Next we use fraction arithmetic to simplify the constant terms in the expression: ![6 - \left(\tfrac{5}{2}\right)^{2} = 6\cdot\tfrac{4}{4} - \tfrac{25}{4} = \tfrac{24 - 25}{4} = \tfrac{-1}{4} = -0.25](00431.jpeg).

We’re left with the equation

![\left(x+2.5\right)^2 - 0.25 = 0,](00432.jpeg)

which we can now solve by digging toward ![x](00015.jpeg). First move ![0.25](00172.jpeg) to the right-hand side to get ![\left(x+2.5\right)^2 = 0.25](00433.jpeg). Then take the square root on both sides to obtain ![(x+2.5) = \pm 0.5](00434.jpeg), which simplifies to ![x = -2.5 \pm 0.5](00435.jpeg). The two solutions are ![x=-2.5+0.5=-2](00436.jpeg) and ![x=-2.5-0.5=-3](00437.jpeg). You can verify these solutions by substituting the values in the original equation ![(-2)^2+5(-2)+6=0](00438.jpeg) and similarly ![(-3)^2+5(-3)+6=0](00439.jpeg). Congratulations, you just solved a quadratic equation using a 1200-year-old algebra technique!

In the next section, we’ll learn how to leverage the complete-the-square trick to obtain a general-purpose formula for quickly solving quadratic equations.

###[Exercises](part0002_split_001.md)

E2.1 Factor the following quadratic expressions:

**a)** ![x^2-8x+7](00440.jpeg) **b)** ![x^2+4x+4](00441.jpeg) **c)** ![x^2-9](00442.jpeg)

Guess the values ![p](00384.jpeg) and ![q](00385.jpeg) in the expression ![(x+p)(x+q)](00443.jpeg).

E2.2 Solve the equations by completing the square.

**a)** ![x^2 + 2x - 15=0](00444.jpeg) **b)** ![x^2 + 4x + 1=0](00445.jpeg)
