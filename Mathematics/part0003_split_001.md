Chapter 3    

##[3.1 Exponents](part0003_split_001.md)

In math we must often multiply together the same number many times, so we use the notation

![b^n  = \underbrace{bbb \cdots bb}_{n \text{ times} }](00497.jpeg)

to denote some number ![b](00074.jpeg) multiplied by itself ![n](00054.jpeg) times. In this section we’ll review the basic terminology associated with exponents and discuss their properties.

###[Definitions](part0003_split_001.md)

The fundamental ideas of exponents are:

-   ![b^n](00498.jpeg): the number ![b](00074.jpeg) raised to the power ![n](00054.jpeg)
    -   ![b](00074.jpeg): the _base_
    -   ![n](00054.jpeg): the _exponent_ or _power_ of ![b](00074.jpeg) in the expression ![b^n](00498.jpeg)

By definition, the zeroth power of any number is equal to one, expressed as ![b^0=1](00499.jpeg).

We’ll also discuss _exponential functions_. In particular, we define the following important exponential functions:

-   ![b^x](00500.jpeg): the exponential function base ![b](00074.jpeg)
-   ![10^x](00501.jpeg): the exponential function base ![10](00246.jpeg)
-   ![\exp(x)= e^x](00502.jpeg): the exponential function base ![e](00236.jpeg). The number ![e](00236.jpeg) is called _Euler’s number_.
-   ![2^x](00503.jpeg): the exponential function base ![2](00103.jpeg). This function is important in computer science.

The number ![e=2.7182818\ldots](00504.jpeg) is a special base with many applications. We call ![e](00236.jpeg) the _natural_ base. Another special base is ![10](00246.jpeg) because we use the decimal system for our numbers. We can write very large numbers and very small numbers as powers of ![10](00246.jpeg). For example, one thousand can be written as ![1\,000=10^3](00505.jpeg), one million is ![1\,000\,000=10^6](00506.jpeg), and one billion is ![1\,000\,000\,000=10^9](00507.jpeg).

###[Formulas](part0003_split_001.md)

The following properties follow from the definition of exponentiation as repeated multiplication.

#####[Property 1](part0003_split_001.md)

Multiplying together two exponential expressions that have the same base is the same as adding the exponents:

![b^m b^n       = \underbrace{bbb \cdots bb}_{m \text{ times} }        \underbrace{bbb \cdots bb}_{n \text{ times} }      = \underbrace{bbbbbbb \cdots bb}_{m + n \text{ times} }      = b^{m+n}.](00508.jpeg)

#####[Property 2](part0003_split_001.md)

Division by a number can be expressed as an exponent of minus one:

![b^{-1} = \frac{1}{b} \,.](00509.jpeg)

Any number times its reciprocal gives one: ![b b^{-1} = \frac{b}{b} = 1](00510.jpeg). A negative exponent corresponds to a division:

![b^{-n} = \frac{1}{b^n} \,.](00511.jpeg)

#####[Property 3](part0003_split_001.md)

By combining Property 1 and Property 2 we obtain the following rule:

![\frac{b^m}{b^n} = b^{m-n}.](00512.jpeg)

In particular we have ![b^{n}b^{-n}=b^{n-n}=b^0=1](00513.jpeg). Multiplication by the number ![b^{-n}](00514.jpeg) is the inverse operation of multiplication by the number ![b^{n}](00498.jpeg). The net effect of the combination of both operations is the same as multiplying by one.

#####[Property 4](part0003_split_001.md)

When an exponential expression is exponentiated, the inner exponent and the outer exponent multiply:

![({b^m})^n      = \underbrace{(\underbrace{bbb \cdots bb}_{m \text{ times} })       (\underbrace{bbb \cdots bb}_{m \text{ times} })       \cdots       (\underbrace{bbb \cdots bb}_{m \text{ times} })}_{n \text{ times} }     = b^{mn}.](00515.jpeg)

#####[Property 5.1](part0003_split_001.md)

![(ab)^n      =\underbrace{(ab)(ab)(ab) \cdots (ab)(ab)}_{n \text{ times} }      = \underbrace{aaa \cdots aa}_{n \text{ times} }        \underbrace{bbb \cdots bb}_{n \text{ times} }        = a^n b^n.](00516.jpeg)

#####[Property 5.2](part0003_split_001.md)

![\left(\frac{a}{b}\right)^n      = \underbrace{\left(\frac{a}{b}\right)\left(\frac{a}{b}\right)\left(\frac{a}{b}\right)       \cdots \left(\frac{a}{b}\right)\left(\frac{a}{b}\right)}_{n \text{ times} }     =  \frac{ \overbrace{aaa \cdots aa}^{n \text{ times} }        }{\underbrace{bbb \:\cdots\: bb}_{n \text{ times} } }     = \frac{a^n}{b^n}.](00517.jpeg)

#####[Property 6](part0003_split_001.md)

Raising a number to the power ![\frac{1}{n}](00518.jpeg) is equivalent to finding the ![n](00054.jpeg)th root of the number:

![b^{\frac{1}{n}} = \sqrt[n]{b}.](00519.jpeg)

In particular, the square root corresponds to the exponent of one half: ![\sqrt{b}=b^{\frac{1}{2}}](00520.jpeg). The cube root (the inverse of ![x^3](00521.jpeg)) corresponds to ![\sqrt[3]{b}= b^{\frac{1}{3}}](00522.jpeg). We can verify the inverse relationship between ![\sqrt[3]{x}](00523.jpeg) and ![x^3](00521.jpeg) by using either Property 1: ![(\sqrt[3]{x})^3=(x^{\frac{1}{3}})(x^{\frac{1}{3}})(x^{\frac{1}{3}})    =x^{\frac{1}{3}+\frac{1}{3}+\frac{1}{3}}=x^1=x](00524.jpeg), or by using Property 4: ![(\sqrt[3]{x})^3=(x^{\frac{1}{3}})^3=x^{\frac{3}{3}}=x^1=x](00525.jpeg).

Properties 5.1 and 5.2 also apply for fractional exponents:

![\sqrt[n]{ab}         = (ab)^{\frac{1}{n}}        = a^{\frac{1}{n}}b^{\frac{1}{n}}         = \sqrt[n]{a}\sqrt[n]{b}, \quad         \sqrt[n]{\left(\frac{a}{b}\right)}         = \left(\frac{a}{b}\right)^{\!\frac{1}{n}}         = \frac{  a^{\frac{1}{n}} }{ b^{\frac{1}{n}} }         =  \frac{\sqrt[n]{a} }{ \sqrt[n]{b} }.](00526.jpeg)

###[Discussion](part0003_split_001.md)

####[Negative exponents](part0003_split_001.md)

A negative sign in the exponent does not mean “subtract,” but rather “divide by”:

![a^{-n} = \frac{1}{a^n}=\frac{1}{\underbrace{aaa\cdots a}_{n\; \text{times}}} \, .](00527.jpeg)

To understand why negative exponents correspond to division, consider the following calculation:

![a^ma^n      =      \underbrace{aaa\cdots a}_{m\; \text{times}}      \,      \underbrace{aaa\cdots a}_{n\; \text{times}}      =      \underbrace{aaaaaa\cdots \cdots aa}_{m+n\; \text{times}}      =a^{m+n}.](00528.jpeg)

This calculation illustrates a general rule for multiplying exponential expressions: ![a^ma^n=a^{m+n}](00529.jpeg), or, if you prefer words, “add the exponents together when multiplying exponential expressions.” Defining ![a^{-n} = \frac{1}{a^n}](00530.jpeg) ensures the rule ![a^ma^n=a^{m+n}](00529.jpeg) is also valid for negative exponents:

![a^m a^{-n}       =      \underbrace{aaaaa\cdots aa}_{m\; \text{times}}      \,      \frac{1}{       \underbrace{a\cdots a}_{n\; \text{times}}      }      =      \frac{       \overbrace{aaaaa\cdots aa}^{m\; \text{times}}      }{       \underbrace{a\cdots a}_{n\; \text{times}}      }      =      \underbrace{aa\cdots a}_{m-n\; \text{times}}      =a^{m-n}.](00531.jpeg)

For example, the expression ![2^{-3}](00532.jpeg) corresponds to ![\frac{1}{2^3}=\frac{1}{8}](00533.jpeg). If we multiply together ![2^5](00534.jpeg) and ![2^{-3}](00532.jpeg), we obtain ![2^5\cdot 2^{-3} = 2^{5-3} = 2^2=4](00535.jpeg).

####[Fractional exponents](part0003_split_001.md)

We discussed positive and negative exponents, but what about exponents that are fractions? Fractional exponents describe square-root-like operations:

![\begin{align*}       a^{\frac{1}{2}} = \sqrt{a} = \sqrt[2]{a},        \qquad          a^{\frac{1}{3}} = \sqrt[3]{a},        \qquad       a^{\frac{1}{4}} = \sqrt[4]{a}.    \end{align*}](00536.jpeg)

Recall the square-root operation ![\sqrt{\phantom{a}}\,](00537.jpeg), which is used it to undo the effect of the ![x^2](00026.jpeg) operation. More generally, the “![n](00054.jpeg)th root” function ![\sqrt[n]{x}](00538.jpeg) is the inverse of the function ![x^n](00539.jpeg).

If this is the first time you’re seeing square roots, you might assume you’ll need to learn lots of new rules for manipulating square-root expressions. Or maybe you have experience with the rules of “squiggle math” already. What kind of emotions do expressions like ![\sqrt[3]{27}\sqrt[3]{8}](00540.jpeg) stir up in you? Chill! There’s no new math to learn and no rules to memorize. All the “squiggle math” rules are consequences of the general rule ![a^ba^c=a^{b+c}](00541.jpeg) applied to expressions where the exponents are fractions. For example, a cube root satisfies the equation

![\sqrt[3]{a}       \sqrt[3]{a}       \sqrt[3]{a}       =       a^{\frac{1}{3}}       a^{\frac{1}{3}}       a^{\frac{1}{3}}       =       a^{ \frac{1}{3} + \frac{1}{3} + \frac{1}{3} }       =       a^{ 1 }            =       a.](00542.jpeg)

Do you see why ![\sqrt[3]{x}](00523.jpeg) and ![x^3](00521.jpeg) are inverse operations? The number ![\sqrt[3]{a}](00543.jpeg) is one third of the number ![a](00014.jpeg) with respect to multiplication (since multiplying ![\sqrt[3]{a}](00543.jpeg) by itself three times produces ![a](00014.jpeg)). We say “one third _with respect to multiplication_,” because the usual meaning of “one third of ![a](00014.jpeg)” is with respect to the addition operation (adding together three copies of ![\frac{a}{3}](00544.jpeg) produces ![a](00014.jpeg)).

The ![n](00054.jpeg)th root of ![a](00014.jpeg) is a number which, when multiplied together ![n](00054.jpeg) times, will give ![a](00014.jpeg). The “![n](00054.jpeg)th root of ![a](00014.jpeg)” can be denoted in two equivalent ways:

![\sqrt[n]{a} = a^{\frac{1}{n}}.](00545.jpeg)

Using this definition and the general rule ![a^ba^c=a^{b+c}](00541.jpeg) allows us to simplify all kinds expressions. For example, we can simplify ![\sqrt[4]{a}\sqrt[4]{a}](00546.jpeg) by rewriting it as ![\sqrt[4]{a}\sqrt[4]{a}     = a^{\frac{1}{4}} a^{\frac{1}{4}}     = a^{ \frac{1}{4} + \frac{1}{4} }     =  a^{ \frac{1}{2} }     = \sqrt{a}](00547.jpeg). We can also simplify the expression ![\sqrt[3]{27}\sqrt[3]{8}](00540.jpeg) by rewriting it as ![27^{\frac{1}{3}} 8^{\frac{1}{3}}](00548.jpeg), then simplifying it as ![27^{\frac{1}{3}} 8^{\frac{1}{3}}     =     \left(3 \cdot 3 \cdot 3\right)^{\frac{1}{3}}  \left(2 \cdot 2 \cdot 2\right)^{\frac{1}{3}}     =     3\cdot2     =     6](00549.jpeg).

Let’s verify the claim that ![\sqrt[n]{a}](00550.jpeg) equals “one ![n](00054.jpeg)th of ![a](00014.jpeg) with respect to multiplication.” To obtain the whole number, we must multiply the number ![\sqrt[n]{a}](00550.jpeg) times itself ![n](00054.jpeg) times:

![\big(\sqrt[n]{a}\big)^n     =     \left(a^{\frac{1}{n}}\right)^n      =     \underbrace{      a^{\frac{1}{n}}a^{\frac{1}{n}}a^{\frac{1}{n}}a^{\frac{1}{n}} \cdots a^{\frac{1}{n}}a^{\frac{1}{n}}     }_{n\; \textrm{times}}       = a^{\frac{n}{n}}      = a^1 = a.](00551.jpeg)

The ![n](00054.jpeg)\-fold product of ![\frac{1}{n}](00518.jpeg)\-fractional exponents of any number produces that number raised to exponent one, and therefore the inverse operation of ![\sqrt[n]{x}](00538.jpeg) is ![x^n](00539.jpeg).

The commutative law of multiplication ![ab=ba](00087.jpeg) implies that we can write any fraction ![\frac{a}{b}](00206.jpeg) in two other equivalent ways: ![\frac{a}{b}=a\frac{1}{b}=\frac{1}{b}a](00552.jpeg). We multiply by ![a](00014.jpeg), then divide the result by ![b](00074.jpeg); or first we divide by ![b](00074.jpeg) and then multiply the result by ![a](00014.jpeg). Similarly, when we have a fraction in the exponent, we can write the answer in two equivalent ways:

![a^{\frac{2}{3} }=\sqrt[3]{a^2} = (\sqrt[3]{a})^2, \quad \;      a^{-\frac{1}{2}}=\frac{1}{a^{\frac{1}{2}}} = \frac{1}{\sqrt{a}}, \quad \;      a^{\frac{m}{n}} = \left(\sqrt[n]{a}\right)^m = \sqrt[n]{a^m}.](00553.jpeg)

Make sure the above notation makes sense to you. As an exercise, try computing ![5^{\frac{4}{3}}](00554.jpeg) on your calculator and check that you obtain ![8.54987973\ldots](00555.jpeg) as the answer.

####[Even and odd exponents](part0003_split_001.md)

The function ![f(x)=x^{n}](00556.jpeg) behaves differently depending on whether the exponent ![n](00054.jpeg) is even or odd. If ![n](00054.jpeg) is odd we have

![\left( \sqrt[n]{b} \, \right)^n = \sqrt[n]{ b^n } = b,      \qquad       \textrm{when } n \textrm{ is odd}.](00557.jpeg)

However, if ![n](00054.jpeg) is even, the function ![x^n](00539.jpeg) destroys the sign of the number (see ![x^2](00026.jpeg), which maps both ![-x](00299.jpeg) and ![x](00015.jpeg) to ![x^2](00026.jpeg)). The successive application of exponentiation by ![n](00054.jpeg) and the ![n](00054.jpeg)th root has the same effect as the absolute value function:

![\sqrt[n]{ b^n } = |b|,     \qquad      \textrm{when } n \textrm{ is even}.](00558.jpeg)

Recall that the absolute value function ![|x|](00031.jpeg) discards the information about the sign of ![x](00015.jpeg). The expression ![(\sqrt[n]{b})^n](00559.jpeg) cannot be computed whenever ![b](00074.jpeg) is a negative number. The reason is that we can’t evaluate ![\sqrt[n]{b}](00560.jpeg) for ![b<0](00561.jpeg) in terms of real numbers, since there is no real number which, multiplied by itself an even number of times, gives a negative number.

###[Links](part0003_split_001.md)

\[ Further reading on exponentiation \][`http://en.wikipedia.org/wiki/Exponentiation`](./Exponentiation.md)

###[Exercises](part0003_split_001.md)

E3.1 Simplify the following exponential expressions.

**a)** ![2^3ef\frac{\sqrt{ef}}{(\sqrt{ef})^3}](00562.jpeg) **b)** ![\frac{abc}{a^2b^3c^4}](00563.jpeg) **c)** ![\frac{(2\alpha)^3}{\alpha}](00564.jpeg) **d)** ![(a^3)^2(\frac{1}{b})^2](00565.jpeg)

E3.2 Simplify the following expressions as much as possible:

**a)** ![\sqrt{3}\sqrt{3}](00566.jpeg) **b)** ![\sqrt{9}\sqrt{16}](00567.jpeg) **c)** ![\frac{\sqrt[3]{8}\sqrt{3}}{\sqrt{4}}](00568.jpeg) **d)** ![\frac{ \sqrt{aba} }{ \sqrt{b} }](00569.jpeg)

E3.3 Calculate the values of the following exponential expressions:

**a)** ![\sqrt{2}(\pi)2^{\frac{1}{2}}](00570.jpeg) **b)** ![8^{\frac{2}{3}}+8^{-\frac{2}{3}}](00571.jpeg) **c)** ![\left( \frac{ (\sqrt[3]{c})^3 }{ c } \right)^{\!77}](00572.jpeg) **d)** ![\!\left(\!   \frac{x^2 \sqrt{x^4} }{x^3}  \!\right)^{\!2}](00573.jpeg)

E3.4 Find all the values of ![x](00015.jpeg) that satisfy these equations:

**a)** ![x^2=a](00574.jpeg) **b)** ![x^3=b](00575.jpeg) **c)** ![x^4=c](00576.jpeg) **d)** ![x^5=d](00577.jpeg)

E3.5 Coulomb’s constant ![k_e](00578.jpeg) is defined by the formula ![k_e=\frac{1}{4\pi \varepsilon_0}](00579.jpeg), where ![\varepsilon_0](00580.jpeg) is the permittivity of free space. Use a calculator to compute the value of ![k_e](00578.jpeg) starting from ![\varepsilon_0 = 8.854 \times 10^{-12}](00581.jpeg) and ![\pi=3.14159265](00582.jpeg). Report your answer with an appropriate number of digits, even if the calculator gives you a number with more digits.
