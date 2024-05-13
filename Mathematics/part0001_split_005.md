Chapter 1    

##[1.5 Functions and their inverses](part0001_split_005.md)

As we saw in the section on solving equations, the ability to “undo” functions is a key skill for solving equations.

#####[Example](part0001_split_005.md)

Suppose we’re solving for ![x](00015.jpeg) in the equation

![f(x) = c,](00286.jpeg)

where ![f](00287.jpeg) is some function and ![c](00256.jpeg) is some constant. We’re looking for the unknown ![x](00015.jpeg) such that ![f(x)](00288.jpeg) equals ![c](00256.jpeg). Our goal is to isolate ![x](00015.jpeg) on one side of the equation, but the function ![f](00287.jpeg) stands in our way.

By using the _inverse function_ (denoted ![f^{-1}](00289.jpeg)) we “undo” the effects of ![f](00287.jpeg). We apply the inverse function ![f^{-1}](00289.jpeg) to both sides of the equation to obtain

![f^{-1}\!\left( f(x) \right)  = f^{-1}\left( c \right).](00290.jpeg)

By definition, the inverse function ![f^{-1}](00289.jpeg) performs the opposite action of the function ![f](00287.jpeg), so together the two functions cancel each other out. We have ![f^{-1}(f(x))=x](00291.jpeg) for any number ![x](00015.jpeg).

Provided everything is kosher (the function ![f^{-1}](00289.jpeg) must be defined for the input ![c](00256.jpeg)), the manipulation we made above is valid and we have obtained the answer ![x=f^{-1}(c)](00292.jpeg).

The above example introduces the notation ![f^{-1}](00289.jpeg) for denoting the inverse function. This notation is inspired by the notation for reciprocals. Recall that multiplication by the reciprocal number ![a^{-1}](00293.jpeg) is the inverse operation of multiplication by the number ![a](00014.jpeg): ![a^{-1}ax=1x=x](00294.jpeg). In the case of functions, however, the negative-one exponent does not refer to “one over-![f(x)](00288.jpeg)” as in ![\frac{1}{f(x)}=(f(x))^{-1}](00295.jpeg); rather, it refers to the inverse function. In other words, the number ![f^{-1}(y)](00296.jpeg) is equal to the number ![x](00015.jpeg) such that ![f(x)=y](00297.jpeg). Be careful: sometimes an equation can have multiple solutions. For example, the function ![f(x)=x^2](00298.jpeg) maps two input values (![x](00015.jpeg) and ![-x](00299.jpeg)) to the same output value ![x^2=f(x)=f(-x)](00300.jpeg). The inverse function of ![f(x)=x^2](00298.jpeg) is ![f^{-1}(y)=\sqrt{y}](00301.jpeg), but both ![x=+\sqrt{c}](00302.jpeg) and ![x=-\sqrt{c}](00303.jpeg) are solutions to the equation ![x^2=c](00304.jpeg). In this case, this equation’s solutions can be indicated in shorthand notation as ![x=\pm \sqrt{c}](00305.jpeg).

###[Formulas](part0001_split_005.md)

Here is a list of common functions and their inverses:

![\begin{align*}   \textrm{function } f(x)            & \; \; \Leftrightarrow \; \;      \textrm{inverse } f^{-1}(x)           \\   x+2  & \; \; \Leftrightarrow \; \;      x-2   \\   2x  & \; \; \Leftrightarrow \; \;      \tfrac{1}{2}x  \\   -1x  & \; \; \Leftrightarrow \; \;      -1x   \\   x^2  & \; \; \Leftrightarrow \; \;      \pm\sqrt{x}  \\   2^x  & \; \; \Leftrightarrow \; \;      \log_{2}(x)  \\   3x+5  & \; \; \Leftrightarrow \; \;      \tfrac{1}{3}(x-5) \\    a^x  & \; \; \Leftrightarrow \; \;      \log_a(x)  \\   \exp(x)= e^x & \; \; \Leftrightarrow \; \;      \ln(x)=\log_e(x) \\   \sin(x)  & \; \; \Leftrightarrow \; \;      \sin^{-1}(x)=\arcsin(x) \\   \cos(x)  & \; \; \Leftrightarrow \; \;      \cos^{-1}(x)=\arccos(x)   \end{align*}](00306.jpeg)

The function-inverse relationship is _symmetric_—if you see a function on one side of the above table (pick a side, any side), you’ll find its inverse on the opposite side.

Don’t be surprised to see ![-1x \; \Leftrightarrow -1x](00307.jpeg) in the list of function inverses. Indeed, the opposite operation of multiplying by ![-1](00308.jpeg) is to multiply by ![-1](00308.jpeg) once more: (![-(-x) = x](00309.jpeg)).

####[Example 1](part0001_split_005.md)

If you want to solve the equation ![x-4 = 5](00310.jpeg), you can apply the inverse function of ![x-4](00311.jpeg), which is ![x + 4](00312.jpeg). After adding four to both sides of the equation, ![x-4+4  = 5 +4](00313.jpeg), we obtain the answer ![x = 9](00314.jpeg).

####[Example 2](part0001_split_005.md)

Let’s say your teacher doesn’t like you and right away, on the first day of class, he gives you a serious equation and tells you to find ![x](00015.jpeg):

![\log_5\left(3 + \sqrt{6\sqrt{x}-7}   \right) = 34+\sin(8)-\Psi(1).](00315.jpeg)

See what I mean when I say the teacher doesn’t like you?

First, note that it doesn’t matter what ![\Psi](00316.jpeg) (the Greek letter _psi_) is, since ![x](00015.jpeg) is on the other side of the equation. You can keep copying ![\Psi(1)](00317.jpeg) from line to line, until the end, when you throw the ball back to the teacher. “My answer is in terms of _your_ variables, dude. _You_ go figure out what the hell ![\Psi](00316.jpeg) is since you brought it up in the first place!” By the way, it’s not actually recommended to quote me verbatim should a situation like this arise. The same goes with ![\sin(8)](00318.jpeg). If you don’t have a calculator handy, don’t worry about it. Keep the expression ![\sin(8)](00318.jpeg) instead of trying to find its numerical value. In general, try to work with variables as much as possible and leave the numerical computations for the last step.

Okay, enough beating about the bush. Let’s just find ![x](00015.jpeg) and get it over with! On the right-hand side of the equation, we have the sum of a bunch of terms with no ![x](00015.jpeg) in them, so we’ll leave them as they are. On the left-hand side, the outermost function is a logarithm base ![5](00117.jpeg). Cool. Looking at the table of inverse functions, we find the exponential function is the inverse of the logarithm: ![a^x \Leftrightarrow \log_a(x)](00319.jpeg). To get rid of ![\log_5](00320.jpeg), we must apply the exponential function base 5 to both sides:

![5^{ \log_5\left(3 + \sqrt{6\sqrt{x}-7}   \right) }  = 5^{ 34+\sin(8)-\Psi(1) },](00321.jpeg)

which simplifies to

![3 + \sqrt{6\sqrt{x}-7} = 5^{ 34+\sin(8)-\Psi(1) },](00322.jpeg)

since ![5^x](00323.jpeg) cancels ![\log_5 x](00324.jpeg).

From here on, it is going to be as if Bruce Lee walked into a place with lots of bad guys. Addition of ![3](00106.jpeg) is undone by subtracting ![3](00106.jpeg) on both sides:

![\sqrt{6\sqrt{x}-7} = 5^{ 34+\sin(8)-\Psi(1) } - 3.](00325.jpeg)

To undo a square root we take the square:

![6\sqrt{x}-7 = \left(5^{ 34+\sin(8)-\Psi(1) } - 3\right)^2.](00326.jpeg)

Add ![7](00157.jpeg) to both sides,

![6\sqrt{x} = \left(5^{ 34+\sin(8)-\Psi(1) } - 3\right)^2+7,](00327.jpeg)

divide by ![6](00328.jpeg)

![\sqrt{x} = \frac{1}{6}\left(\left(5^{ 34+\sin(8)-\Psi(1) } - 3\right)^2+7\right),](00329.jpeg)

and square again to find the final answer:

![\begin{align*}      x      &= \left[\frac{1}{6}\left(\left(5^{ 34+\sin(8)-\Psi(1) } - 3\right)^2+7\right) \right]^2.    \end{align*}](00330.jpeg)

Did you see what I was doing in each step? Next time a function stands in your way, hit it with its inverse so it knows not to challenge you ever again.

###[Discussion](part0001_split_005.md)

The recipe I have outlined above is not universally applicable. Sometimes ![x](00015.jpeg) isn’t alone on one side. Sometimes ![x](00015.jpeg) appears in several places in the same equation. In these cases, you can’t effortlessly work your way, Bruce Lee-style, clearing bad guys and digging toward ![x](00015.jpeg)—you need other techniques.

The bad news is there’s no general formula for solving complicated equations. The good news is the above technique of “digging toward the ![x](00015.jpeg)” is sufficient for 80% of what you are going to be doing. You can get another 15% if you learn how to solve the quadratic equation:

![ax^2 +bx + c = 0.](00331.jpeg)

We’ll show a formula for solving quadratic equations in[Section 2.2](part0002_split_002.md). Solving cubic equations like ![ax^3+bx^2+cx+d=0](00332.jpeg) using a formula is also possible, but at this point you might as well start using a computer to solve for the unknowns. See page 9.3.23 in Appendix[1](./XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.md).

There are all kinds of other equations you can learn how to solve: equations with multiple variables, equations with logarithms, equations with exponentials, and equations with trigonometric functions. The principle of “digging” toward the unknown by applying inverse functions is the key for solving all these types of equations, so be sure to practice using it.

###[Exercises](part0001_split_005.md)

E1.5 Solve for ![x](00015.jpeg) in the following equations:

**a)** ![3x=6](00333.jpeg) **b)** ![\log_5(x)=2](00334.jpeg) **c)** ![\log_{10}(\sqrt{x})=1](00335.jpeg)

E1.6 Find the function inverse and use it to solve the problems.

**a)**-    Solve the equation ![f(x)=4](00336.jpeg), where ![f(x)= \sqrt{x}](00337.jpeg).
**b)**-    Solve for ![x](00015.jpeg) in the equation ![g(x)=1](00338.jpeg), given ![g(x)= e^{-2x}](00339.jpeg).
