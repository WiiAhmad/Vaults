Chapter 3    

##[3.2 Logarithms](part0003_split_002.md)

Some people think the word “logarithm” refers to some mythical, mathematical beast. Legend has it that logarithms are many-headed, breathe fire, and are extremely difficult to understand. Nonsense! Logarithms are simple. It will take you at most a couple of pages to get used to manipulating them, and that is a good thing because logarithms are used all over the place.

The strength of your sound system is measured in logarithmic units called decibels. This is because your ears are sensitive only to exponential differences in sound intensity. Logarithms allow us to compare very large numbers and very small numbers on the same scale. If sound were measured in linear units instead of logarithmic units, your sound system’s volume control would need to range from ![1](00211.jpeg) to ![1\,048\,576](00583.jpeg). That would be weird, no? This is why we use the logarithmic scale for volume notches. Using a logarithmic scale, we can go from sound intensity level ![1](00211.jpeg) to sound intensity level ![1\,048\,576](00583.jpeg) in 20 “progressive” steps. Assume each notch doubles the sound intensity, rather than increasing the intensity by a fixed amount. If the first notch corresponds to ![2](00103.jpeg), the second notch is ![4](00136.jpeg)—still probably inaudible, turn it up! By the time you get to the sixth notch you’re at ![2^6=64](00584.jpeg) sound intensity, which is the level of audible music. The tenth notch corresponds to sound intensity ![2^{10}=1024](00585.jpeg) (medium-strength sound), and finally the twentieth notch reaches a max power of ![2^{20}=1\,048\,576](00586.jpeg), at which point the neighbours come to complain.

###[Definitions](part0003_split_002.md)

You’re hopefully familiar with these following concepts from the previous section:

-   ![b^x](00500.jpeg): the exponential function base ![b](00074.jpeg)
-   ![\exp(x)=e^x](00502.jpeg): the exponential function base ![e](00236.jpeg), Euler’s number
-   ![2^x](00503.jpeg): exponential function base ![2](00103.jpeg)
-   ![f](00287.jpeg): the notion of a function
-   ![f^{-1}](00289.jpeg): the inverse function of ![f](00287.jpeg). The inverse function is defined in terms of ![f](00287.jpeg) such that ![f^{-1}(f(x))=x](00291.jpeg). In other words, if you apply ![f](00287.jpeg) to some number ![x](00015.jpeg) and get the output ![y](00018.jpeg), and then you pass ![y](00018.jpeg) through ![f^{-1}](00289.jpeg), the output will be ![x](00015.jpeg) again. The inverse function ![f^{-1}](00289.jpeg) undoes the effects of the function ![f](00287.jpeg).

In this section we’ll play with the following new concepts:

-   ![\log_b(x)](00587.jpeg): the logarithm of ![x](00015.jpeg) base ![b](00074.jpeg) is the inverse function of ![b^x](00500.jpeg).
-   ![\ln(x)](00588.jpeg): the “natural” logarithm base ![e](00236.jpeg). This is the inverse of ![e^x](00589.jpeg).
-   ![\log_2(x)](00590.jpeg): the logarithm base ![2](00103.jpeg) is the inverse of ![2^x](00503.jpeg).

I say _play_ because there is nothing much new to learn here: a logarithm is a clever way to talk about the size of a number; essentially, it tells us how many digits the number has.

###[Formulas](part0003_split_002.md)

The main thing to realize is that ![\log](00591.jpeg)s don’t really exist on their own. They are defined as the inverses of their corresponding exponential functions. The following statements are equivalent:

![\log_b(x)=m \; \; \; \; \;  \Leftrightarrow \; \; \; \; \; b^m=x.](00592.jpeg)

Logarithms with base ![e](00236.jpeg) are written ![\ln(x)](00588.jpeg) for “logarithme naturel” because ![e](00236.jpeg) is the “natural” base. Another special base is ![10](00246.jpeg) because our numbers are based on the decimal system. The logarithm base 10 ![\log_{10}(x)](00593.jpeg) tells us roughly the size of the number ![x](00015.jpeg)—how many digits the number has.

#####[Example](part0003_split_002.md)

When someone working for the System (say someone with a high-paying job in the financial sector) boasts about his or her “six-figure” salary, they are really talking about the ![\log](00591.jpeg) of how much money they make. The “number of figures” ![N_S](00594.jpeg) in their salary is calculated as 1 plus the logarithm base 10 of their salary ![S](00595.jpeg). The formula is

![N_S = 1 + \log_{10}(S).](00596.jpeg)

A salary of ![S=100\,000](00597.jpeg) corresponds to ![N_S=1+\log_{10}(100\,000)=1+5=6](00598.jpeg) figures.

What is the smallest “seven-figure” salary? We must solve for ![S](00595.jpeg) given ![N_S=7](00599.jpeg) in the formula. We find ![7 = 1+\log_{10}(S)](00600.jpeg), which means ![6=\log_{10}(S)](00601.jpeg), and—using the inverse relationship between logarithm base 10 and exponentiation base 10—we discover ![S=10^6 = 1\,000\,000](00602.jpeg). One million dollars per year! Yes, for this kind of money I see how someone might want to work for the System. But most system pawns never make it to the seven-figure level; I believe the average high-ranking salary is more in the ![1+\log_{10}(250\,000) =  1+5.397=6.397](00603.jpeg) digits range. Wait, a lousy ![0.397](00604.jpeg) extra digits is all it takes to convince some of the smartest people out there to sell their brains to the finance sector? What wankers! Who needs a six-digit salary anyway? Why not make ![1+\log_{10}(55\,000)=5.74](00605.jpeg) digits as a teacher and do something with your life that _actually_ matters?

###[Properties](part0003_split_002.md)

Moving on, let’s discuss two important properties you’ll need when dealing with logarithms. Pay attention because the arithmetic rules for logarithms are very different from the usual rules for numbers. Intuitively, you can think of logarithms as a convenient way to refer to the exponents of numbers. The following properties are the logarithmic analogues of the properties of exponents.

####[Property 1](part0003_split_002.md)

The first property states that the sum of the logarithms of two numbers is equal to the logarithm of the product of the numbers:

![\log(x)+\log(y)=\log(xy).](00606.jpeg)

We need to show that the expression on the left is equal to the expression on the right. We met logarithms very recently, so we don’t know each other too well yet. In fact, the only thing we know about ![\log](00591.jpeg)s is the inverse relationship with the exponential function. The only way to prove this property is to use this relationship.

The following statement is true for any base ![b](00074.jpeg):

![b^m b^n = b^{m+n}.](00607.jpeg)

This follows from first principles. Recall that exponentiation is nothing more than repeated multiplication. If you count the total number of ![b](00074.jpeg)s multiplied on the left side, you’ll find a total of ![m+n](00608.jpeg) of them, which is what we have on the right.

If we define some new variables ![x](00015.jpeg) and ![y](00018.jpeg) such that ![b^m=x](00609.jpeg) and ![b^n=y](00610.jpeg), then we can rewrite the equation ![b^m b^n = b^{m+n}](00611.jpeg) as

![xy = b^{m+n}.](00612.jpeg)

Taking the logarithm of both sides gives us

![\log_b(xy) = \log_b\!\left(  b^{m+n} \right) = m + n = \log_b(x) + \log_b(y).](00613.jpeg)

The last step above uses the definition of the ![\log](00591.jpeg) function again, which states that

![b^m=x \; \; \Leftrightarrow \; \; m=\log_b(x)       \qquad \textrm{and}  \qquad      b^n=y \; \; \Leftrightarrow \; \; n=\log_b(y).](00614.jpeg)

We have thus shown that ![\,\log(x)+\log(y)=\log(xy)](00615.jpeg).

Using this property, we can derive two other useful formulas:

![\log(x^k)=k\log(x),](00616.jpeg)

and

![\log(x)-\log(y)=\log\left(\frac{x}{y}\right)\!.](00617.jpeg)

####[Property 2](part0003_split_002.md)

This property helps us change from one base to another. We can express the logarithm in any base ![B](00409.jpeg) in terms of a ratio of logarithms in another base ![b](00074.jpeg). The general formula is

![\log_{B}(x) =  \frac{\log_b(x)}{\log_b(B)}.](00618.jpeg)

For example, the logarithm base ![10](00246.jpeg) of a number ![S](00595.jpeg) can be expressed as a logarithm base ![2](00103.jpeg) or base ![e](00236.jpeg) as follows:

![\log_{10}(S)      =\frac{\log_{10}(S)}{1}     =\frac{\log_{10}(S)}{\log_{10}(10)}      = \frac{\log_{2}(S)}{\log_{2}(10)}=\frac{\ln(S)}{\ln(10)}.](00619.jpeg)

This property is helpful when you need to compute a logarithm in a base that is not available on your calculator. Suppose you’re asked to compute ![\log_{7}(S)](00620.jpeg), but your calculator only has a ![\button{\log_{10}}](00621.jpeg) button. You can simulate ![\log_7(S)](00620.jpeg) by computing ![\log_{10}(S)](00622.jpeg) and dividing by ![\log_{10}(7)](00623.jpeg).

###[Exercises](part0003_split_002.md)

E3.6 Use the properties of logarithms to simplify the expressions**a)**  ![\log(x)+\log(2y)](00624.jpeg)**b)**  ![\log(z)-\log(z^2)](00625.jpeg)**c)** ![\log(x)+\log(y/x)](00626.jpeg) 

**d)**  ![\log_2(8)](00627.jpeg)**e)**  ![\log_{3}(\frac{1}{27})](00628.jpeg)**f)** ![\log_{10}(10000)](00629.jpeg)
