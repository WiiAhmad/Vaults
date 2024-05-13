Chapter 1      

# [Chapter 1 Math fundamentals](./Chapter 1_ Math fundamentals.md)

In this chapter we’ll review the fundamental ideas of mathematics—the prerequisites for learning linear algebra. We’ll define the different types of numbers and the concept of a function, which is a transformation that takes numbers as inputs and produces numbers as outputs. Linear algebra is the extension of these ideas to many dimensions: instead of doing math with numbers and functions, in linear algebra we’ll be doing math with vectors and linear transformations.

![precalculus_for_LA](./images/precalculus_for_LA.jpg)

Figure 1.1

## [1.1 Solving equations](./Chapter 1_ Math fundamentals.md)

Most math skills boil down to being able to manipulate and solve equations. Solving an equation means finding the value of the unknown in the equation.

Check this out:

![x^2-4=45.](./images/d385454e7d7f490e4a40642170947bba7e44abae.png)

To solve the above equation is to answer the question “What is ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)?” More precisely, we want to find the number that can take the place of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the equation so that the equality holds. In other words, we’re asking,

![\text{``Which number times itself minus four gives 45?''}](./images/473b5ca271cd50d025dbdbe17e018b4dbfd15f35.png)

That is quite a mouthful, don’t you think? To remedy this verbosity, mathematicians often use specialized symbols to describe math operations. The problem is that these specialized symbols can be very confusing. Sometimes even the simplest math concepts are inaccessible if you don’t know what the symbols mean.

What are your feelings about math, dear reader? Are you afraid of it? Do you have anxiety attacks because you think it will be too difficult for you? Chill! Relax, my brothers and sisters. There’s nothing to it. Nobody can magically guess the solution to an equation immediately. To find the solution, you must break the problem into simpler steps. Let’s walk through this one together.

To find ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), we can manipulate the original equation, transforming it into a different equation (as true as the first) that looks like this:

![x \; = \textrm{ only numbers.}](./images/34da0a788ee5151e75333159b25f0b58191a8d38.png)

That’s what it means to _solve_ an equation: the equation is solved because the unknown is isolated on one side, while the constants are grouped on the other side. You can type the numbers on the right-hand side into a calculator and obtain the numerical value of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).

By the way, before we continue our discussion, let it be noted: the equality symbol (![=](./images/b8ca3693499b05d77b159c39cca4f9b6fd74d54e.png)) means that all that is to the left of ![=](./images/b8ca3693499b05d77b159c39cca4f9b6fd74d54e.png) is equal to all that is to the right of ![=](./images/b8ca3693499b05d77b159c39cca4f9b6fd74d54e.png). To keep this equality statement true, **for every change you apply to the left side of the equation, you must apply the same change to the right side of the equation**.

To find ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), we need to manipulate the original equation into its final form, simplifying it step by step until it can’t be simplified any further. The only requirement is that the manipulations we make transform one true equation into another true equation. In this example, the first simplifying step is to add the number four to both sides of the equation:

![x^2-4  \; + 4  	=	45    \; + 4, 	    \\](./images/6cd86dd8e5caa88d5911955a8622154415b3a5bc.png)

which simplifies to

![x^2 	 		=	49.](./images/40fbf6666b7a472762161a0f514203aab8b706ec.png)

Now the expression looks simpler, yes? How did I know to perform this operation? I wanted to “undo” the effects of the operation ![-4](./images/655027e17cc709b6c6f4a44c99d6a60a88eecf3c.png). We undo an operation by applying its _inverse_. In the case where the operation is the subtraction of some amount, the inverse operation is the addition of the same amount. We’ll learn more about function inverses in[Section 1.4](./Chapter 1_ Math fundamentals.md).

We’re getting closer to our goal of _isolating_ ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) on one side of the equation, leaving only numbers on the other side. The next step is to undo the square ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) operation. The inverse operation of squaring a number ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) is to take its square root ![\sqrt{\phantom{a}\; }](./images/df5d1795f87aeeab7dd7dcd034f5d4bba7b24b37.png), so that’s what we’ll do next. We obtain

![\sqrt{x^2} 		= 	\sqrt{49}.](./images/2399bccd723954832773adbc80a4acb787a45a95.png)

Notice how we applied the square root to both sides of the equation? If we don’t apply the same operation to both sides, we’ll break the equality!

The equation ![\sqrt{x^2}= \sqrt{49}](./images/e57019f3e5cdefcf861648eb33e73e02e76fb6f3.png) simplifies to

![|x|	= 	7.](./images/60621d825f03ad19c2874ab7c528ed868efc5e87.png)

What’s up with the vertical bars around ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)? The notation ![|x|](./images/6a0c58538d2e0dc0054c5f510b8593ca34f65859.png) stands for the _absolute value_ of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), which is the same as ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) except we ignore the sign that indicates whether ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is positive or negative. For example ![|5|=5](./images/fea4badc8335a66bf8f495d3e903ade7679a54d2.png) and ![|-5|=5](./images/2796ab1fd95faa950ec6a9d83d887292746f678f.png), too. The equation ![|x|=7](./images/76070975c5800724396e4256df19924567265265.png) indicates that both ![x=7](./images/08e228f2877476bf9d50a28783d361bd07229dff.png) and ![x=-7](./images/f3b7a321efc7765b4051f1b313e29eb314ba6823.png) satisfy the equation ![x^2 = 49](./images/1aa43d451c1cb0f0c891d620a2e6701b2dd915af.png). Seven squared is 49, ![7^2=49](./images/718ac034ec4324f819c5c49e3cbf66ff281c3155.png), and negative seven squared is also 49, ![(-7)^2 = 49](./images/24fc4b8d97bc59ae7295c5a7fbd81713d29a98ee.png), because the two negative signs cancel each other out.

The final solutions to the equation ![x^2-4=45](./images/45925760a90dc6b17303068785036f62471ffbae.png) are

![x  = 7 \qquad \textrm{and} \qquad   x=  - 7.](./images/d6b9a2201bf297800c13c4d8345fc45103da9282.png)

Yes, there are _two_ possible answers. You can check that both of the above values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) satisfy the initial equation ![x^2-4=45](./images/45925760a90dc6b17303068785036f62471ffbae.png).

If you are comfortable with all the notions of high school math and you feel you could have solved the equation ![x^2-4=45](./images/45925760a90dc6b17303068785036f62471ffbae.png) on your own, then you can skim through this chapter quickly. If on the other hand you are wondering how the squiggle killed the power two, then this chapter is for you! In the following sections we will review all the essential concepts from high school math that you will need to power through the rest of this book. First, let me tell you about the different kinds of numbers.

##[1.2 Numbers](./Chapter 1_ Math fundamentals.md)

In the beginning, we must define the main players in the world of math: numbers.

###[Definitions](./Front matter.md)

Numbers are the basic objects we use to count, measure, quantify, and calculate things. Mathematicians like to classify the different kinds of number-like objects into categories called _sets_:

-   The natural numbers: ![\mathbb{N} = \{0,1,2,3,4,5,6,7, \ldots \, \}](./images/d015a68915a5966891b8c1baa4419dda789c2ab1.png)
-   The integers: ![\mathbb{Z} = \{\ldots, -3,-2,-1,0,1,2,3 , \ldots  \, \}](./images/a62de94ba72bb8596d6d777d19cc68bf6f902560.png)
-   The rational numbers: ![\mathbb{Q} = \{\frac{5}{3}, \frac{22}{7}, 1.5, 0.125,  -7, \, \ldots \, \}](./images/bcf75c2c4c5f5fbc9c640f97e5843afa804ec479.png)
-   The real numbers: ![\mathbb{R} = \{-1,0,1, \sqrt{2}, e,\pi, \;  4.94\ldots, \; \ldots \, \}](./images/86d04f6fdd0ccc7a7c055b0605308c9d277b7df3.png)
-   The complex numbers: ![\mathbb{C} = \{ -1, 0, 1, i,  1+i, 2+3i,  \ldots \, \}](./images/8a87bf74e87262368febfd69fb18254f1af3ac5b.png)

These categories of numbers should be somewhat familiar to you. Think of them as neat classification labels for everything that you would normally call a number. Each group in the above list is a _set_. A set is a collection of items of the same kind. Each collection has a name and a precise definition for which items belong in that collection. Note also that each of the sets in the list contains all the sets above it, as illustrated in[Figure 1.2](./Chapter 1_ Math fundamentals.md). For now, we don’t need to go into the details of[sets and set notation](./Chapter 1_ Math fundamentals.md), but we do need to be aware of the different sets of numbers.

![nested_sets](./images/nested_sets.png)

Figure 1.2: An illustration of the nested containment structure of the different number sets. The set of natural numbers is contained in the set of integers, which in turn is contained in the set of rational numbers. The set of rational numbers is contained in the set of real numbers, which is contained in the set of complex numbers.

Why do we need so many different sets of numbers? Each set of numbers is associated with more and more advanced mathematical problems.

The simplest numbers are the natural numbers ![\mathbb{N}](./images/bafa4736281babd323c41d9dbdcbc6784e7e82e1.png), which are sufficient for all your math needs if all you’re going to do is _count_ things. How many goats? Five goats here and six goats there so the total is 11 goats. The sum of any two natural numbers is also a natural number.

As soon as you start using _subtraction_ (the inverse operation of addition), you start running into negative numbers, which are numbers outside the set of natural numbers. If the only mathematical operations you will ever use are _addition_ and _subtraction_, then the set of integers ![\mathbb{Z} = \{ \ldots, -2, -1, 0, 1, 2, \ldots \}](./images/51c1669c133f3bf1b6a6880e73eb45603bf303f3.png) will be sufficient. Think about it. Any integer plus or minus any other integer is still an integer.

You can do a lot of interesting math with integers. There is an entire field in math called _number theory_ that deals with integers. However, to restrict yourself solely to integers is somewhat limiting—a rotisserie menu that offers ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png) of a chicken would be totally confusing.

If you want to use division in your mathematical calculations, you’ll need the rationals ![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png). The set of rational numbers corresponds to all numbers that can be expressed as _fractions_ of the form ![\frac{m}{n}](./images/a63eac226ced841a66c7c3ca10b635f7bd6243c3.png) where ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) and ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) are integers, and ![n \neq 0](./images/e1a6a6e69e6581feb55026ff32eaa248cd62d56b.png). You can add, subtract, multiply, and divide rational numbers, and the result will always be a rational number. However, even the rationals are not enough for all of math!

In geometry, we can obtain _irrational_ quantities like ![\sqrt{2}](./images/6715b8265ad0d01e2040fdb8d7b64f78ff347978.png) (the diagonal of a square with side 1) and ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) (the ratio between a circle’s circumference and its diameter). There are no integers ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) such that ![\sqrt{2}=\frac{x}{y}](./images/ead9b7c3c7752a64c894214a86f547fc3bb4b1d5.png), therefore we say that ![\sqrt{2}](./images/6715b8265ad0d01e2040fdb8d7b64f78ff347978.png) is _irrational_ (not in the set ![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png)). An irrational number has an infinitely long decimal expansion that doesn’t repeat. For example, ![\pi = 3.141592653589793\ldots](./images/e3f1c19482ec80ba05a835ad13526df1203e39c5.png) where the dots indicate that the decimal expansion of ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) continues all the way to infinity.

Combining the irrational numbers with the rationals gives us all the useful numbers, which we call the set of real numbers ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). The set ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) contains the integers, the rational numbers ![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png), as well as irrational numbers like ![\sqrt{2}=1.4142135\ldots](./images/a55cbea4bcba940fc708cea35d933da888eb6c7e.png). By using the reals you can compute pretty much anything you want. From here on in the text, when I say _number_, I mean an element of the set of real numbers ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png).

The only thing you can’t do with the reals is to take the square root of a negative number—you need the complex numbers ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png) for that. We defer the discussion on complex numbers until[Section 1.14](./Chapter 1_ Math fundamentals.md).

### [Operations on numbers](./Front matter.md)

#### [Addition](./Front matter.md)

You can add numbers. I’ll assume you’re familiar with this stuff:

![2 + 3 = 5,\; \; \; 45+56=101,\; \; \; 9\,999 + 1 = 10\,000.](./images/454744dbf958215fc4cd5956d0f4a8d962fac76a.png)

You can visualize numbers as sticks of different length. Adding numbers is like adding sticks together: the resulting stick has a length equal to the sum of the lengths of the constituent sticks, as illustrated in[Figure 1.3](./Chapter 1_ Math fundamentals.md).

![number_line_addition](./images/number_line_addition.png)

Figure 1.3: The addition of numbers corresponds to adding lengths.

Addition is _commutative_, which means that ![a+b=b+a](./images/a6fd95d4de5838f19e5619f0bcac997b1465436f.png). In other words, the order of the numbers in a summation doesn’t matter. It is also _associative_, which means that if you have a long summation like ![a+b+c](./images/0a89723f9c7dcad0df1ccc96ffeef2974f062ee1.png) you can compute it in any order ![(a+b)+c](./images/9b007222c629f85a320dd6866122c810bcef3adb.png) or ![a+(b+c)](./images/43f1f9a6cec7f9e89265ce279961aa95f0b9b431.png), and you’ll get the same answer.

#### [Subtraction](./Front matter.md)

Subtraction is the inverse operation of addition:

![2 - 3 = -1, \quad 45-56 = -11, \quad 999 - 1 = 998.](./images/3e381b3a6af4167159b5f66f3a224a0816572a4b.png)

Unlike addition, subtraction is not a commutative operation. The expression ![a-b](./images/e9396bae98fa3009be2d2e8fd76ee7defaa7a68f.png) is not equal to the expression ![b-a](./images/7dae325000372a2aa945443aab5d0a5f15918587.png), or written mathematically:

![a-b \neq b-a.](./images/b4a73776ab55fd976b4109005102d83c8245b120.png)

Instead we have ![b-a=-(a-b)](./images/d86845d442d5fe0fab9db437deafa8a21a417db8.png), which shows that changing the order of ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) in the expression changes its sign.

Subtraction is not associative either:

![(a-b) - c \neq  a - (b-c).](./images/a7869ed7aec68433dd1a472f64114bfbd8393113.png)

For example ![(7- 2) -3 = 2](./images/e49a9082f3d34c1691c29aa6b9bdee8d544badbd.png) while ![7- (2-3) = 8](./images/dd67031e9f113dd6e75b9c26735c3c70c8ce5089.png).

####[Multiplication](./Front matter.md)

You can also multiply numbers together:

![ab = \underbrace{a+a+\cdots+a}_{b \; \textrm{times}}=\underbrace{b+b+\cdots+b}_{a \; \textrm{times}}.](./images/966e781963731dfd777256532447cf05a8a9bef8.png)

Note that multiplication can be defined in terms of repeated addition.

The visual way to think about multiplication is as an area calculation. The area of a rectangle of width ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and height ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) is equal to ![ab](./images/ed94260877c56e3c6cf641e1fcadb5a64e18693f.png). A rectangle with a height equal to its width is a square, and this is why we call ![aa=a^2](./images/4370e95e4480ddd5aa9baa6302cfe8f397f84065.png) “![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) squared.”

![number_line_multiplication](./images/number_line_multiplication.png)

Figure 1.4: The area of a rectangle with width ![3](./images/b6031d121f1b4a4b138ae89b9919d5b4c8ebf35b.png) m and height ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png) m is equal to ![6](./images/160a910df642692dd50f0862138b3bc151d89988.png)m![^2](./images/ead5a636923c99f390e27454435456dae3fc32cc.png), which is equivalent to six squares with area ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png)m![^2](./images/ead5a636923c99f390e27454435456dae3fc32cc.png) each.

Multiplication of numbers is also commutative, ![ab=ba](./images/f3536b76e86db67948a746785d54445f12d5b163.png), and associative, ![abc=(ab)c=a(bc)](./images/a0319968f1b83acfbf5fa43c0543a5cfbcef4836.png). In modern math notation, no special symbol is required to denote multiplication; we simply put the two factors next to each other and say the multiplication is _implicit_. Some other ways to denote multiplication are ![a\cdot b](./images/b27950e4b3165565085f5fcc7056bc080c4fe89b.png), ![a\times b](./images/965868dfd4802fa09e413bb61034e0ec265c23af.png), and, on computer systems, ![a*b](./images/2469d77aadcc072d4539f010a31d25fc85b12947.png).

####[Division](./Front matter.md)

Division is the inverse operation of multiplication.

![a/b \; = \;  \frac{a}{b}  \; = a\div b = \text{ one } b^{\scriptsize \text{th}} \text{ of } a.](./images/81de7a68f34626a04abba7112793b7a5f97655e7.png)

Whatever ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) is, you need to divide it into ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) equal parts and take one such part.

Division is not a commutative operation since ![a/b](./images/a200368cf6fe25862bac6d5676e6c8c2ff0f3b20.png) is not equal to ![b/a](./images/a406a376b93274927f861bac5b33cf2209eb8279.png). Division is not associative either: ![(a \div b) \div c   \neq   a \div (b \div c)](./images/b46373e37fb07e5afdb48ed9e58a03198f4d2843.png). For example, when ![a=6](./images/57eed903693c65add8ac7608aedcaf5b51dc9ff2.png), ![b=3](./images/9f59d104ab82ae7e1bd5b9c34df833072a3203e2.png), and ![c=2](./images/45e75023a05fa399c815cfcfc1ddf5913544af25.png), we get ![(6/3)/2=1](./images/8c2f3264a3553f21cece99457c4c7ad7da64549a.png) while ![6/(3/2)=4](./images/07dbadd4d19d41897362819ef1a4a231a66b559e.png).

Note that you cannot divide by ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png). Try it on your calculator or computer. It will say “`error divide by zero`” because this action simply doesn’t make sense. After all, what would it mean to divide something into zero equal parts?

####[Exponentiation](./Front matter.md)

The act of multiplying a number by itself many times is called _exponentiation_. We denote “![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) exponent ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)” using a superscript, where ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is the number of times the base ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) is multiplied by itself:

![a^n = \underbrace{aaa\cdots a}_{n\; \text{times}}.](./images/81035c029ff5958c130c753cccb229fa0483ab3c.png)

In words, we say “![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) raised to the power of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png).”

To visualize how exponents work, we can draw a connection between the value of exponents and the dimensions of geometric objects.[Figure 1.5](./Chapter 1_ Math fundamentals.md) illustrates how the same length ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) corresponds to different geometric objects when raised to different exponents. The number ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) corresponds to a line segment of length two, which is a geometric object in a one-dimensional space. If we add a line segment of length two in a second dimension, we obtain a square with area ![2^2](./images/4d17021cdc8043b37f721818171a5f7ef44b63f9.png) in a two-dimensional space. Adding a third dimension, we obtain a cube with volume ![2^3](./images/26d9dc38bb4bc68736bb85dc6d3dd294a7c237b2.png) in a three-dimensional space. Indeed, raising a base ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) to the exponent ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) is commonly called “![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) squared,” and raising ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) to the power of ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) is called “![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) cubed.”

The geometrical analogy about one-dimensional quantities as lengths, two-dimensional quantities as areas, and three-dimensional quantities as volumes is good to keep in mind.

![number_line_exponentiation](./images/number_line_exponentiation.png)

Figure 1.5: Geometric interpretation for exponents ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png), ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png), and ![3](./images/b6031d121f1b4a4b138ae89b9919d5b4c8ebf35b.png). A length raised to exponent ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png) corresponds to the area of a square. The same length raised to exponent ![3](./images/b6031d121f1b4a4b138ae89b9919d5b4c8ebf35b.png) corresponds to the volume of a cube.

Our visual intuition works very well up to three dimensions, but we can use other means of visualizing higher exponents, as demonstrated in[Figure 1.6](./Chapter 1_ Math fundamentals.md).

![exponents_prime_factorizations](./images/exponents_prime_factorizations.png)

Figure 1.6: Visualization of numbers raised to different exponents. Each box in this grid contains ![a^n](./images/ebb53e71a4c1ec9dbf7cd0170a2c556821dfcbce.png) dots, where the base ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png) varies from one through five, and the exponent ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) varies from one through five. In the first row we see that the number ![a=1](./images/940407a8f7e47931d3ccf0b999e29806b439e164.png) raised to any exponent is equal to itself. The second row corresponds to the base ![a=2](./images/b847c237d4db31c11a5a30e271616eaab958e61a.png) so the number of dots doubles each time we increase the exponent by one. Starting from ![2^1=2](./images/a724e577a3b6d9fdcdf6c25f2131e1657d14a2d9.png) in the first column, we end up with ![2^5=32](./images/9f1b3e36761cc469212d088dff3517e72cff1df5.png) in the last column. The rest of the rows show how exponentiation works for different bases.

###[Operator precedence](./Front matter.md)

There is a standard convention for the order in which mathematical operations must be performed. The basic algebra operations have the following precedence:

1.  Parentheses
2.  Exponents
3.  Multiplication and Division
4.  Addition and Subtraction

If you’re seeing this list for the first time, the acronym PEMDAS and the associated mnemonic “Please Excuse My Dear Aunt Sally,” might help you remember the order of operations.

For instance, the expression ![5\cdot 3^2+13](./images/b288535296a204ff7d2822f12743b57f55c657dc.png) is interpreted as “First find the square of ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png), then multiply it by ![5](./images/0a99a11a8db1514f59b81b2211782467dd4a2e74.png), and then add ![13](./images/efda37b94eec4caab90a0dfd1dbbba749c4a3a52.png).” Parentheses are needed to carry out the operations in a different order: to multiply ![5](./images/0a99a11a8db1514f59b81b2211782467dd4a2e74.png) times ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) first and _then_ take the square, the equation should read ![(5\cdot 3)^2 + 13](./images/8b97014cb2e15451cb74ae7c494c3ee5074edc8c.png), where parentheses indicate that the square acts on ![(5 \cdot 3)](./images/19c2c923d80ec6f27d771642e7d3ecf0f6ebf67f.png) as a whole and not on ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) alone.

###[Exercises](./Front matter.md)

E1.1 Solve for the unknown ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the following equations:

**a)** ![3x+2-5=4+2](./images/e8d6af1487ef077edd3e2dc2e99685eb51e4c8c3.png) **b)** ![\frac{1}{2}x-3=\sqrt{3}+12-\sqrt{3}](./images/6c72ec27513ba7b08b49b154d928ed6a0e6b41b4.png)

**c)** ![\frac{7x-4}{2} +1 = 8-2](./images/6ea7d14c996ddf5491f71fd0f80477b3a0f21896.png) **d)** ![5x-2+3=3x-5](./images/a59d9b097f4a524b50c95438d34619993cf95984.png)

E1.2 Indicate all the number sets the following numbers belong to.

**a)** ![-2](./images/fad909888effb4a36881235a6f079a1489f6af7f.png) **b)** ![\sqrt{-3}](./images/c49159928419574e6784554b3a7496e0e6381342.png) **c)** ![8 \div 4](./images/3c1358614f39e09363c9bcb64bf6622bdf89a327.png) **d)** ![\frac{5}{3}](./images/6a593dff2d2f9dc94459a988f58e35f8e4e29a39.png) **e)** ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png)

E1.3 Calculate the values of the following expressions:

**a)** ![2^33-3](./images/dca30d7c8bb2a02300ea3cd18b508bc7ae01d2d7.png) **b)** ![2^3(3-3)](./images/4d932ac0437c5652d432b69922c537c97beb1681.png) **c)** ![\frac{4-2}{3^3}(6\cdot 7- 41)](./images/3c97a761e67fbf7783dffad217bf6ffd84507814.png)

##[1.3 Variables](./Chapter 1_ Math fundamentals.md)

In math we use a lot of _variables_ and _constants_, which are placeholder names for _any_ number or unknown. Variables allow us to perform calculations without knowing all the details.

#####[Example](./Front matter.md)

You’re having tacos for lunch today and wondering how many you can eat without going over your caloric budget. Your goal is to eat 800 calories for lunch and you want to do the calculation before getting to the restaurant because you fear your math abilities might be affected in the presence of tacos. You’re not sure how many calories each taco contains, so you invent the variable ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) to denote this unknown. You also define the variable ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) to represent the number of tacos you will eat, and come up with the equation ![800=cx](./images/b8af29fc53687520836e15877d606733673d3421.png) to represent the total number of calories of your lunch. Solving for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), you find the total number of tacos you should order is ![x = \frac{800}{c}](./images/90cb6be68c260f8b13795e822c02e50c03a00364.png). If the restaurant serves tacos that contain ![c=200](./images/af7f8abb11af18ff5e94708d2f2dd6a39971dd59.png) calories each, then you should order ![x = \frac{800}{200} = 4](./images/996aa7390b04b8553c0fdae06fe5c1042e84cff5.png) of them. If the restaurant serves only giant tacos worth ![c=400](./images/5f19c33601abad275993163131592f859477c859.png) calories each, then you can only eat ![x = \frac{800}{400} = 2](./images/d0d27c214501dc996a15b0d37defdef0105e0a73.png) of them. Observe we were able to solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) even before knowing the value of ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png).

###[Variable names](./Front matter.md)

There are common naming patterns for variables:

-   ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png): name used for the unknown in equations. We also use ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) to denote function inputs and the position of objects in physics.
-   ![i,j,k,m,n](./images/99f4c0b13b3755e7f17da9c8a4d3b9a196f4757c.png): common names for integer variables
-   ![a,b,c,d](./images/70a3913b689188e48b34db78693d88aa1482ccfa.png): letters near the beginning of the alphabet are often used to denote constants (fixed quantities that do not change).
-   ![\theta,\phi](./images/11a0ea3dddaa709a62c5fdc36900073f3b874ebf.png): the Greek letters _theta_ and _phi_ are used to denote angles
-   ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png): costs in business, along with ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) for profit, and ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) for revenue
-   ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png): capital letters are used to denote random variables in probability theory

###[Variable substitution](./Front matter.md)

We can often _change variables_ and replace one unknown variable with another to simplify an equation. For example, say you don’t feel comfortable around square roots. Every time you see a square root, you freak out until one day you find yourself taking an exam trying to solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the following equation:

![\frac{6}{5 - \sqrt{x}} = \sqrt{x}.](./images/941238b2ed1345cd681704efd1f056a84014a2f5.png)

Don’t freak out! In crucial moments like this, substitution can help with your root phobia. Just write, “Let ![u=\sqrt{x}](./images/bce3f247218ddb53b3d539044a4280e72d874324.png)” on your exam, and voila, you can rewrite the equation in terms of the variable ![u](./images/82a971ebc8ceb9b9a22bd63d00ce51c1323a931d.png):

![\frac{6}{5 - u} = u,](./images/30de8eb9121e5ffff019653e2b01bca70fad29a9.png)

which contains no square roots.

The next step to solve for ![u](./images/82a971ebc8ceb9b9a22bd63d00ce51c1323a931d.png) is to undo the division operation. Multiply both sides of the equation by ![(5-u)](./images/9327cc0ae5ec7388cd5d522b0a4256ee552d6290.png) to obtain

![\frac{6}{5-u}(5-u)	=	u(5-u),](./images/b63f3789bb64ca03d9bdf43eff7e0dc8aee94282.png)

which simplifies to

![\quad \qquad \qquad 6	= 	5u - u^2.](./images/cbdcdb77e5b76b4fdbc56b3368803e54d665676c.png)

This can be rewritten as the equation ![u^2-5u+6=0](./images/9eb5ea2e00873a524e829fa86886d55cf2ac15c8.png), which in turn can be rewritten as ![(u-2)(u-3)=0](./images/cc7612f652443eeb5b423e2d3e27c5babab9ae13.png) using the techniques we’ll learn in[Section 1.6](./Chapter 1_ Math fundamentals.md).

We now see that the solutions are ![u_1=2](./images/97c762a625400284b0d2f99677e41d5a503d9762.png) and ![u_2=3](./images/2d0fbeee83fd049ed1a0e9b121311528a58e6415.png). The last step is to convert our ![u](./images/82a971ebc8ceb9b9a22bd63d00ce51c1323a931d.png)\-answers into ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-answers by using ![u=\sqrt{x}](./images/bce3f247218ddb53b3d539044a4280e72d874324.png), which is equivalent to ![x = u^2](./images/e1369cb81f33411778dc2c0cd3e6c3eec6e80c96.png). The final answers are ![x_1=2^2=4](./images/cff315d32cefbe505f601b22ff3741c83547fc47.png) and ![x_2=3^2=9](./images/95bd9d94a491dbc2c64734ec7c99c6f1477d5dfb.png). Try plugging these ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) values into the original square root equation to verify that they satisfy it.

###[Compact notation](./Front matter.md)

Symbolic manipulation is a powerful tool because it allows us to manage complexity. Say you’re solving a physics problem in which you’re told the mass of an object is ![m=140](./images/878a02b31f717ae4b4649dfb2a27005dc83f5d8b.png) kg. If there are many steps in the calculation, would you rather use the number ![140](./images/f41036c56df1c78983cfe194d807f8d591b5f56b.png) kg in each step, or the shorter symbol ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)? It’s much easier to use ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) throughout your calculation, and wait until the last step to substitute the value ![140](./images/f41036c56df1c78983cfe194d807f8d591b5f56b.png) kg when computing the final numerical answer.

##[1.4 Functions and their inverses](./Chapter 1_ Math fundamentals.md)

As we saw in the section on solving equations, the ability to “undo” functions is a key skill for solving equations.

#####[Example](./Front matter.md)

Suppose we’re solving for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the equation

![f(x) = c,](./images/47b07e27059afc06251ca03a670042aa9e1585a4.png)

where ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is some function and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) is some constant. We’re looking for the unknown ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) such that ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) equals ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png). Our goal is to isolate ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) on one side of the equation, but the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) stands in our way.

By using the _inverse function_ (denoted ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png)) we “undo” the effects of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png). We apply the inverse function ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) to both sides of the equation to obtain

![f^{-1}\!\left( f(x) \right)  = f^{-1}\left( c \right).](./images/61ddd64305b815038991d638df3f96ca0ca16a08.png)

By definition, the inverse function ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) performs the opposite action of the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png), so together the two functions cancel each other out. We have ![f^{-1}(f(x))=x](./images/5548468b59d3c92190942bc4171657344e2aee93.png) for any number ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).

Provided everything is kosher (the function ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) must be defined for the input ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png)), the manipulation we made above is valid and we have obtained the answer ![x=f^{-1}(c)](./images/7891f5214a7c74a6c06bab63ad6527cde39be94e.png).

The above example introduces the notation ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) for denoting the inverse function. This notation is inspired by the notation for reciprocals. Recall that multiplication by the reciprocal number ![a^{-1}](./images/2e16513eec946e9f07947541e30d02e13962e7d4.png) is the inverse operation of multiplication by the number ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png): ![a^{-1}ax=1x=x](./images/7d372240fd106c0c69044aeb324566e8426126e0.png). In the case of functions, however, the negative-one exponent does not refer to “one over-![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png)” as in ![\frac{1}{f(x)}=(f(x))^{-1}](./images/f082cbda0d5d91030f9c8481943fa77ac3ffdcaa.png); rather, it refers to the inverse function. In other words, the number ![f^{-1}(y)](./images/1e4fdd8e948ff1492990e3b3fc66f077e53f73b5.png) is equal to the number ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) such that ![f(x)=y](./images/aad6a42679d823357232d67c11fb325cfb6404be.png). Be careful: sometimes an equation can have multiple solutions. For example, the function ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) maps two input values (![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![-x](./images/665de79093233e3f251ecb3a98ec9fb472a7dbd8.png)) to the same output value ![x^2=f(x)=f(-x)](./images/225df6ea629181b902ee3044228114a20483a683.png). The inverse function of ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) is ![f^{-1}(y)=\sqrt{y}](./images/38cf5359afac7c573bd6a83009ae76bd1d7db530.png), but both ![x=+\sqrt{c}](./images/2348540dcb49df8ee449f852d823e27b44acb84c.png) and ![x=-\sqrt{c}](./images/96abd29a561e622c2714820bf4b333378eafa2b9.png) are solutions to the equation ![x^2=c](./images/a944f657af0162a74ba42176618898d1c76f20df.png). In this case, this equation’s solutions can be indicated in shorthand notation as ![x=\pm \sqrt{c}](./images/d5ab7bdc83043ecf3f43d32a8a2255a81243e1ed.png).

###[Formulas](./Front matter.md)

Here is a list of common functions and their inverses:

![\begin{align*}
\textrm{function } f(x)      	
& \; \; \Leftrightarrow \; \;      \textrm{inverse } f^{-1}(x)           \\
x+2		& \; \; \Leftrightarrow \; \;      x-2			\\
2x		& \; \; \Leftrightarrow \; \;      \tfrac{1}{2}x		\\
-1x		& \; \; \Leftrightarrow \; \;      -1x			\\
x^2		& \; \; \Leftrightarrow \; \;      \pm\sqrt{x}		\\
2^x		& \; \; \Leftrightarrow \; \;      \log_{2}(x)		\\
3x+5		& \; \; \Leftrightarrow \; \;      \tfrac{1}{3}(x-5)	\\ 
a^x		& \; \; \Leftrightarrow \; \;      \log_a(x)		\\
\exp(x)= e^x	& \; \; \Leftrightarrow \; \;      \ln(x)=\log_e(x)	\\
\sin(x)		& \; \; \Leftrightarrow \; \;      \sin^{-1}(x)=\arcsin(x) \\
\cos(x)		& \; \; \Leftrightarrow \; \;      \cos^{-1}(x)=\arccos(x)
\end{align*}](./images/4a3a851947f771e70dd73375dd381272ed087ab5.png)

The function-inverse relationship is _symmetric_—if you see a function on one side of the above table (pick a side, any side), you’ll find its inverse on the opposite side.

Don’t be surprised to see ![-1x \; \Leftrightarrow -1x](./images/f71bbeeb29672fc29d0b50518ee5398b0bcb54d3.png) in the list of function inverses. Indeed, the opposite operation of multiplying by ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png) is to multiply by ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png) once more: (![-(-x) = x](./images/fce866259ae4606aa59bfcbac8c768a7938c6596.png)).

####[Example 1](./Front matter.md)

If you want to solve the equation ![x-4 = 5](./images/16ef851a967f8b58f084bda0e712022be5681984.png), you can apply the inverse function of ![x-4](./images/3a5042937d46ee9115849d3a0237fe8c3f8befaa.png), which is ![x + 4](./images/e8cccb153409b7d77ad56d3b6cb25e361cf93fa5.png). After adding four to both sides of the equation, ![x-4+4  = 5 +4](./images/be6a71c0d32692f8e008590a716b7e8576fba492.png), we obtain the answer ![x = 9](./images/c878748c1929b1a800f3312990f94ed67fc0022e.png).

####[Example 2](./Front matter.md)

Let’s say your teacher doesn’t like you and right away, on the first day of class, he gives you a serious equation and tells you to find ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png):

![\log_5\left(3 + \sqrt{6\sqrt{x}-7}   \right) = 34+\sin(8)-\Psi(1).](./images/cf44064890b6579eeeb9f46eaa76207a9ad8c4ed.png)

See what I mean when I say the teacher doesn’t like you?

First, note that it doesn’t matter what ![\Psi](./images/29f8210903ee30024f88170c0f2698d7c0295852.png) (the Greek letter _psi_) is, since ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is on the other side of the equation. You can keep copying ![\Psi(1)](./images/67f25dab8c9dd4ee20425643fbc3bebc8726072a.png) from line to line, until the end, when you throw the ball back to the teacher. “My answer is in terms of _your_ variables, dude. _You_ go figure out what the hell ![\Psi](./images/29f8210903ee30024f88170c0f2698d7c0295852.png) is since you brought it up in the first place!” By the way, it’s not actually recommended to quote me verbatim should a situation like this arise. The same goes with ![\sin(8)](./images/5b3295ca8083820bf8ce4e7bb7fb4dc3200843ae.png). If you don’t have a calculator handy, don’t worry about it. Keep the expression ![\sin(8)](./images/5b3295ca8083820bf8ce4e7bb7fb4dc3200843ae.png) instead of trying to find its numerical value. In general, try to work with variables as much as possible and leave the numerical computations for the last step.

Okay, enough beating about the bush. Let’s just find ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and get it over with! On the right-hand side of the equation, we have the sum of a bunch of terms with no ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in them, so we’ll leave them as they are. On the left-hand side, the outermost function is a logarithm base ![5](./images/0a99a11a8db1514f59b81b2211782467dd4a2e74.png). Cool. Looking at the table of inverse functions, we find the exponential function is the inverse of the logarithm: ![a^x \Leftrightarrow \log_a(x)](./images/799542c9e4ba38661afa1f8ed73cbf8da92bf374.png). To get rid of ![\log_5](./images/58e8c5b4f0f34821d0cb2576f420c8ea836b42d2.png), we must apply the exponential function base 5 to both sides:

![5^{ \log_5\left(3 + \sqrt{6\sqrt{x}-7}   \right) }  = 5^{ 34+\sin(8)-\Psi(1) },](./images/bb75ef8e81b87a5202a520af0b98361685d70758.png)

which simplifies to

![3 + \sqrt{6\sqrt{x}-7} = 5^{ 34+\sin(8)-\Psi(1) },](./images/0bfe2519fc654259052b379ceece2ab722ab4677.png)

since ![5^x](./images/b0b8d6aa3652f1ba32e48376eaa0592c00a5f7c3.png) cancels ![\log_5 x](./images/3a2975b1cf6422b67db00fb847d0e380e6f0b297.png).

From here on, it is going to be as if Bruce Lee walked into a place with lots of bad guys. Addition of ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) is undone by subtracting ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) on both sides:

![\sqrt{6\sqrt{x}-7} = 5^{ 34+\sin(8)-\Psi(1) } - 3.](./images/b193c01a9cb5cdff1d06412a726301de0bd29cc9.png)

To undo a square root we take the square:

![6\sqrt{x}-7 = \left(5^{ 34+\sin(8)-\Psi(1) } - 3\right)^2.](./images/f2c12111c0866ac5965ecb1edf79b41705e7fa0f.png)

Add ![7](./images/7c8183005b1d0a8999b7a1cc791bffe88aeb450f.png) to both sides,

![6\sqrt{x} = \left(5^{ 34+\sin(8)-\Psi(1) } - 3\right)^2+7,](./images/02770606dda8f1373da7ebf4fa1e912dc79de445.png)

divide by ![6](./images/e8ed0b8c238bb0e8c23f11db175de0a483bfde15.png)

![\sqrt{x} = \frac{1}{6}\left(\left(5^{ 34+\sin(8)-\Psi(1) } - 3\right)^2+7\right),](./images/141b89796806459e4deaac15b65258697942f7ac.png)

and square again to find the final answer:

![\begin{align*}
x 
&= \left[\frac{1}{6}\left(\left(5^{ 34+\sin(8)-\Psi(1) } - 3\right)^2+7\right) \right]^2.
\end{align*}](../Images/260699908a4fde58813cd308ace45dd5426bc5a9.png)

Did you see what I was doing in each step? Next time a function stands in your way, hit it with its inverse so it knows not to challenge you ever again.

###[Discussion](./Front matter.md)

The recipe I have outlined above is not universally applicable. Sometimes ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) isn’t alone on one side. Sometimes ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) appears in several places in the same equation. In these cases, you can’t effortlessly work your way, Bruce Lee-style, clearing bad guys and digging toward ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)—you need other techniques.

The bad news is there’s no general formula for solving complicated equations. The good news is the above technique of “digging toward the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)” is sufficient for 80% of what you are going to be doing. You can get another 15% if you learn how to solve the quadratic equation:

![ax^2 +bx + c = 0.](./images/5b301653663b1a2051533bab284ecc6dac2607a7.png)

We’ll show a formula for solving quadratic equations in[Section 1.6](./Chapter 1_ Math fundamentals.md). Solving cubic equations like ![ax^3+bx^2+cx+d=0](./images/97ca1dc326817f9db62b0fbab519ebc0c1fbbaf3.png) using a formula is also possible, but at this point you might as well start using a computer to solve for the unknowns.

There are all kinds of other equations you can learn how to solve: equations with multiple variables, equations with logarithms, equations with exponentials, and equations with trigonometric functions. The principle of “digging” toward the unknown by applying inverse functions is the key for solving all these types of equations, so be sure to practice using it.

###[Exercises](./Front matter.md)

E1.4 Solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the following equations:

**a)** ![3x=6](./images/9c5d702ed2365ddae9a341fc4fe44d7b1b84ea3e.png) **b)** ![\log_5(x)=2](./images/fbe8b133403ffa091d83e2206bff544732b3c904.png) **c)** ![\log_{10}(\sqrt{x})=1](./images/92b4dcd66ac63013595310784917584d2e2a10e5.png)

E1.5 Find the function inverse and use it to solve the problems.

**a)**-    Solve the equation ![f(x)=4](./images/686fce6efa012532fbd18b05850eb06909b95711.png), where ![f(x)= \sqrt{x}](./images/bc20cca97740e11e58a05c4912bea200fcff083d.png).
**b)**-    Solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the equation ![g(x)=1](./images/a5f26cd1edd4df476771c95f932eb0caed6b0c3e.png), given ![g(x)= e^{-2x}](./images/5de1eb6759d6059f87c782e3b01e65f162c6fe29.png).

##[1.5 Basic rules of algebra](./Chapter 1_ Math fundamentals.md)

It’s important that you know the general rules for manipulating numbers and variables, a process otherwise known as—you guessed it—_algebra_. This little refresher will cover these concepts to make sure you’re comfortable on the algebra front. We’ll also review some important algebraic tricks, like _factoring_ and _completing the square_, which are useful when solving equations.

Let’s define some terminology for referring to different parts of math expressions. When an expression contains multiple things added together, we call those things _terms_. Furthermore, terms are usually composed of many things multiplied together. When a number ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is obtained as the product of other numbers like ![x=abc](./images/8ee871daeb9883f9b3996d00ed3c6ae203d34aa2.png), we say “![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) factors into ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png).” We call ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) the _factors_ of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).

![anatomy_of_an_eqn](./images/anatomy_of_an_eqn.png)

Figure 1.7: Diagram showing the names used to describe the different parts of the equation ![abc+de=0](./images/4629ba07af9413eca7d68bd6619533112acbfd15.png).

Given any three numbers ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png), we can apply the following algebraic properties:

1.  Associative property: ![a+b+c=(a+b)+c=a+(b+c)](./images/50e17ecea831148f1c6e38e8d1e578b63962d5f9.png) and ![abc=(ab)c=a(bc)](./images/a0319968f1b83acfbf5fa43c0543a5cfbcef4836.png)
2.  Commutative property: ![a+b=b+a](./images/a6fd95d4de5838f19e5619f0bcac997b1465436f.png) and ![ab=ba](./images/f3536b76e86db67948a746785d54445f12d5b163.png)
3.  Distributive property: ![a(b+c)=ab+ac](./images/bd95bcfce2970aaa08a89c9d980e3389ae6baf90.png)

We use the distributive property every time we _expand_ brackets. For example ![a(b+c+d)=ab + ac + ad](./images/b0b5456e8b28be7f94a95370ca2c1c0bb68e60bb.png). The brackets, also known as parentheses, indicate the expression ![(b+c+d)](./images/fc5096722f0be5f0e3ea41399f3c2acdeb601e4c.png) must be treated as a whole; as a factor consisting of three terms. Multiplying this expression by ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) is the same as multiplying each term by ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png).

The opposite operation of expanding is called _factoring_, which consists of rewriting the expression with the common parts taken out in front of a bracket: ![ab+ac = a(b+c)](./images/db50122ba29e9b48f698c4455b10196220823317.png). In this section, we’ll discuss all algebra operations and illustrate what they’re capable of.

#####[Example](./Front matter.md)

Suppose we are asked to solve for ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) in the equation

![7(3 + 4t) = 11(6t - 4).](./images/92603f6db6a341e863d4ceaa831c8b2523c7bcbc.png)

Since the unknown ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) appears on both sides of the equation, it is not immediately obvious how to proceed.

To solve for ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png), we can bring all ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) terms to one side and all constant terms to the other side. First, expand the two brackets to obtain

![21 + 28t = 66t - 44.](./images/995a362b165097c1b61b7347b0279768b5f9ceca.png)

Then move things around to relocate all ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png)s to the equation’s right-hand side and all constants to the left-hand side:

![21 + 44 = 66t - 28t.](./images/349016dcbe07c4f7545949910114e2622cb562fa.png)

We see ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) is contained in both terms on the right-hand side, so we can “factor it out” by rewriting the equation as

![21 + 44 = t(66 - 28).](./images/1b421a488dd4d4704dc66c2c469b5d2c8209d97e.png)

The answer is within close reach: ![t = \frac{21 + 44}{66 - 28} = \frac{65}{38}](./images/589c916b8d8a870653447a888840c312348b090c.png).

###[Expanding brackets](./Front matter.md)

To _expand_ a bracket is to multiply each term inside the bracket by the factor outside the bracket. The key thing to remember when expanding brackets is to apply the _distributive_ property: ![a(x+y) = ax + ay](./images/cbd177e45cc5b2e147a0c4e9c5cb972f886bff78.png). For longer expressions, we may need to apply the distributive property several times, until there are no more brackets left:

![\begin{align*}
(a+b)(x+y+z)	&= a(x+y+z) + b(x+y+z)				\\
&= ax + ay + az + bx + by + bz.
\end{align*}](./images/198ddd9d18fe4f02a2a4ae192bd82b1f3e50c1a1.png)

After expanding the brackets in this expression, we end up with six terms—one term for each of the six possible combinations of products between the terms in ![(a+b)](./images/4f281d43d5f059cdfccf39e1638ffadb7bf378f6.png) and the terms in ![(x+y+z)](./images/b21e35f66f0ea4ce911a31cc9bd214638ab38410.png).

The distributive property is often used to manipulate expressions containing different powers of the variable ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). For instance,

![(x+3)(x+2)	=	x(x+2) + 3(x+2)		= 	x^2 +x2 +3x + 6.](./images/8fdcf4e6fd05efa9d1a01686dd513e1d89337475.png)

We can use the commutative property on the second term ![x2=2x](./images/01f2d4bc58166f86f1b3f324539bf7c6fa5b25ff.png), then combine the two ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) terms into a single term to obtain

![(x+3)(x+2)	=	x^2 + 5x + 6.](./images/300b02ce9a3f07e68659f5cc874c7f2bf6531d47.png)

The bracket-expanding and simplification techniques demonstrated above are very common in math, and I recommend you solve some algebra practice problems to get the hang of them. Most math textbooks skip simplification steps and jump straight to the answer, since they assume readers are capable of doing simplifications on their own. It would be too long (and annoying) to show the simplifications for each expression. For example, the sentence “We can rewrite ![(x+3)(x+2)](./images/b559b53c8cbb83679269cfae6d7eeee666f4fbba.png) as ![x^2 + 5x + 6](./images/3adb033a9641a71b1d6ac8acf632caac4bfd9513.png),” is the short version of the longer sentence, “We can apply the distributive property twice on ![(x+3)(x+2)](./images/b559b53c8cbb83679269cfae6d7eeee666f4fbba.png) then combine the terms with the same power of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) to get ![x^2 + 5x + 6](./images/3adb033a9641a71b1d6ac8acf632caac4bfd9513.png).”

It’s not unusual for people to make math mistakes when expanding brackets and manipulating long algebra expressions. To avoid mistakes, use a step-by-step approach and apply only one operation in each step. Write legibly and keep the equations “organized” so it’s easy to check the calculations performed in each step. Consider this slightly-more-complicated algebraic expression and its expansion:

![\begin{align*}
(x+a)(bx^2+cx+d) 
&= x(bx^2+cx+d) + a(bx^2+cx+d)			\\
&= bx^3+cx^2+dx \; + \; abx^2 +acx +ad  	\\
&= bx^3+ (c+ab)x^2+(d+ac)x +ad.
\end{align*}](./images/9f1253163c15d5b899e14b7066ba85ca9fd38379.png)

Note how we sorted the terms in the final expression according to the different powers of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), with the terms containing ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) grouped together, and the terms containing ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) grouped together. This approach helps keep things organized when dealing with expressions containing many terms.

###[Factoring](./Front matter.md)

Factoring involves “taking out” the common parts of a complicated expression in order to make the expression more compact. Suppose we’re given the expression ![6x^2y + 15x](./images/39d4e28acdf4f76258bec01a449f7ee73539b0b7.png). We can simplify this expression by taking out the common factors and moving them in front of a bracket. Let’s see how to do this, step by step.

The expression ![6x^2y + 15x](./images/39d4e28acdf4f76258bec01a449f7ee73539b0b7.png) has two terms. Let’s split each term into its constituent factors:

![6x^2y + 15x =   (3)(2)(x)(x)y + (5)(3)x.](./images/0ae8110321b8e311e1280e76cdefb2f76abffa24.png)

Since factors ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) appear in both terms, we can _factor them out_ like this:

![6x^2y + 15x =  3x(2xy+5).](./images/d04b88e0a85e0b0a4ffa9c0272f64571bd3d1e68.png)

The expression on the right shows ![3x](./images/c9753eead44568fc3c65ddef7c2645aeb7bbb447.png) is common to both terms.

Here’s another example of factoring—notice the common factors are taken out and moved in front of the bracket:

![2x^2y + 2x + 4x = 2x(xy	+1+2) =  2x(xy+3).](./images/6f9fafeb7885b0fed96c5acb86b3887cac149ecc.png)

###[Factoring quadratic expressions](./Front matter.md)

A _quadratic expression_ is an expression of the form ![ax^2 + bx + c](./images/bd3691ef3e230ad04b3025566a0701118b37b8f1.png). The expression contains a _quadratic term_ ![ax^2](./images/c36991840bd7f6240db8de2af0344e08012f2ba2.png), a _linear term_ ![bx](./images/6134b35877a9699dc358121bcb202c6d0fb920d0.png), and a constant term ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png). The numbers ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) are called _coefficients_: the quadratic coefficient is ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), the linear coefficient is ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and the constant coefficient is ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png).

To _factor_ the quadratic expression ![ax^2 + bx + c](./images/bd3691ef3e230ad04b3025566a0701118b37b8f1.png) is to rewrite it as the product of a constant and two factors like ![(x+p)](./images/0ca15563cc5d4b296362341690ad65284fe0ad67.png) and ![(x+q)](./images/b7389f98c0bf1746e426dfc59e99cf3df10f1375.png):

![ax^2 + bx + c = a(x+p)(x+q).](./images/426b8813f70ff53163872a6ec5b3bf94c0f19450.png)

Rewriting quadratic expressions in factored form helps us better understand and describe their properties.

#####[Example](./Front matter.md)

Suppose we’re asked to describe the properties of the function ![f(x)=x^2-5x+6](./images/bfd824fcc4aad2a2461f61aa1d292a1926f3fceb.png). Specifically, we’re asked to find the function’s _roots_, which are the values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) for which the function equals zero.

Factoring the expression ![x^2-5x+6](./images/057c0db3b0ae63d6636d167c769ad0b45e12e04c.png) helps us see its properties more clearly, and makes our job of finding the roots of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) easier. The factored form of this quadratic expression is

![f(x) = x^2-5x+6 = (x-2)(x-3).](./images/de1b4d00924a7eeb579c18390a30e0bb0fa1b40c.png)

Now we can see at a glance that the values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) for which ![f(x)=0](./images/7a99a37639d203a4fd8ea7290e75d7d95997c0c7.png) are ![x=2](./images/e5434555c15a07cfe09b5b352b1965c74365967d.png) and ![x=3](./images/a8613defbaa8652ded80dc153560f6d16cb4448c.png). When ![x=2](./images/e5434555c15a07cfe09b5b352b1965c74365967d.png), the factor ![(x-2)](./images/4f7e64e39c146d383834fa3b1a7eb1f766356795.png) is zero and hence ![f(x)=0](./images/7a99a37639d203a4fd8ea7290e75d7d95997c0c7.png). Similarly, when ![x=3](./images/a8613defbaa8652ded80dc153560f6d16cb4448c.png), the factor ![(x-3)](./images/ed2624a78e23737442bcfb5db366564801747e8e.png) is zero so ![f(x)=0](./images/7a99a37639d203a4fd8ea7290e75d7d95997c0c7.png).

How did we know that the factors of ![x^2-5x+6](./images/057c0db3b0ae63d6636d167c769ad0b45e12e04c.png) are ![(x-2)](./images/4f7e64e39c146d383834fa3b1a7eb1f766356795.png) and ![(x-3)](./images/ed2624a78e23737442bcfb5db366564801747e8e.png) in the above example? For simple quadratics like the one above, we can simply _guess_ the values of ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) in the equation ![x^2-5x+6 = (x+p)(x+q)](./images/b2aa55fd2d2850081fb92e75faa997ad7cb1f04a.png). Before we start guessing, let’s look at the expanded version of the product between ![(x+p)](./images/0ca15563cc5d4b296362341690ad65284fe0ad67.png) and ![(x+q)](./images/b7389f98c0bf1746e426dfc59e99cf3df10f1375.png):

![(x+p)(x+q) = x^2 + (p+q)x + pq.](./images/635a92bb56270562fd565430b095697dc2f591ce.png)

Note the linear term on the right-hand side contains the sum of the unknowns ![(p+q)](./images/65c488191cbabd7b051ac762e9bf0898f24cd313.png), while the constant term contains their product ![pq](./images/039bcc63dfcd3ebcf382f4c8145eb0c0f2068655.png). If we want the equation ![x^2-5x+6 = x^2 + (p+q)x + pq](./images/adc6258aa456ad73872d608b0887265f956f48ba.png) to hold, we must find two numbers ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) whose sum equals ![-5](./images/bd17dd326ba74f3b82e7dff7a32196f5090e1b7b.png) and whose product equals ![6](./images/e8ed0b8c238bb0e8c23f11db175de0a483bfde15.png). After a couple of attempts we find ![p=-2](./images/44e08ac44d0040752e2c6a240d62650f9a156e20.png) and ![q=-3](./images/e668d705c16998f72272f0ac98ceef905cd1da5b.png). This guessing approach is an effective strategy for many of the factoring problems we will likely be asked to solve, since math teachers often choose simple numbers like ![\pm 1](./images/4ddcba029acc1de5f12e7a9c53ea409763d9cb5d.png), ![\pm 2](./images/e77a978dea020a2ae9b7e264be08c8983737c340.png), ![\pm 3](./images/cc94a858fdaed4b7e670ecc66981867a02765807.png), or ![\pm 4](./images/a9eccd62f80d07b05d7c47e83261874a28af6037.png) for the constants ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png). For more complicated quadratic expressions, we’ll need to use the quadratic formula, which we’ll talk about in[Section 1.6](./Chapter 1_ Math fundamentals.md).

####[Common quadratic forms](./Front matter.md)

Let’s look at some common variations of quadratic expressions you might encounter when doing algebra calculations.

The quadratic expression ![x^2 - p^2](./images/e062a7a219ba399ab56da3e3315d6ba68cdb0f03.png) is called a _difference of squares_, and it can be obtained by multiplying the factors ![(x+p)](./images/0ca15563cc5d4b296362341690ad65284fe0ad67.png) and ![(x-p)](./images/108b66eb9b753072e9d1a32e707b3c63cdc8c7c1.png):

![(x+p)(x-p)
= x^2 \; \cancel{- xp} \; \cancel{+px}  \; - p^2
= x^2 - p^2.](./images/9e9101247b0d7708c30a84c4aafd7ed9e17292f1.png)

There’s no linear term because the ![-xp](./images/c4be72b211072b11c99c99e6c75bf73ed1b2b181.png) term cancels the ![+px](./images/c4edf8ae5a31834b69563bf922470a7dedce8cdf.png) term. Any time you see an expression like ![x^2-p^2](./images/e062a7a219ba399ab56da3e3315d6ba68cdb0f03.png), you can know it comes from a product of the form ![(x+p)(x-p)](./images/b3f2a255a660805a54122b443911b566d8f82169.png).

A _perfect square_ is a quadratic expression that can be written as the product of repeated factors ![(x+p)](./images/0ca15563cc5d4b296362341690ad65284fe0ad67.png):

![x^2 + 2px + p^2 = (x+p)(x+p) = (x+p)^2.](./images/99f0223c50bbdbd6bf175b575f4c05774823837f.png)

Note ![x^2 - 2qx + q^2 = (x-q)^2](./images/8118dff09081a15e7f9d9f62faf3dea4ffc017db.png) is also a perfect square.

###[Completing the square](./Front matter.md)

In this section we’ll learn about an ancient algebra technique called _completing the square_, which allows us to rewrite _any_ quadratic expression of the form ![x^2+Bx+C](./images/439f29354da14a0bd451888e3ee75a7dfc2b935e.png) as a perfect square plus some constant correction factor ![(x+p)^2+k](./images/cf0ac5d108cf8b80003d585daaf0eb123926606e.png). This algebra technique was described in one of the first books on _al-jabr_ (algebra), written by Al-Khwarizmi around the year 800 CE. The name “completing the square” comes from the ingenious geometric construction used by this procedure. Yes, we can use geometry to solve algebra problems!

We assume the starting point for the procedure is a quadratic expression whose quadratic coefficient is one, ![1x^2 + Bx + C](./images/8dc114497f0dc6ab2e71d71db5787fd1e7670254.png), and use capital letters ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png) to denote the linear and constant coefficients. The capital letters are to avoid any confusion with the quadratic expression ![ax^2 + bx + c](./images/bd3691ef3e230ad04b3025566a0701118b37b8f1.png), for which ![a\neq 1](./images/e28acd08e71f9722eea33da9e60612262f78e335.png). Note we can always write ![ax^2 + bx + c](./images/bd3691ef3e230ad04b3025566a0701118b37b8f1.png) as ![a(x^2+\frac{b}{a}x + \frac{c}{a})](./images/a47fff324ed899d403fd404fb593aa20d3edc604.png) and apply the procedure to the expression inside the brackets, identifying ![\frac{b}{a}](./images/b8c751140b9c4f6a346f255076ffd52eab0859dd.png) with ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![\frac{c}{a}](./images/106085d6e138fba57eb9fb33b2a54703891e252d.png) with ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png).

First let’s rewrite the quadratic expression ![x^2 + Bx + C](./images/439f29354da14a0bd451888e3ee75a7dfc2b935e.png) by splitting the linear term into two equal parts:

![x^2 + \tfrac{B}{2}x + \tfrac{B}{2}x + C.](./images/846502aa7486f7f81e409cd4f8af77085138641a.png)

We can interpret the first three terms geometrically as follows: the ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) term corresponds to a square with side length ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), while the two ![\frac{B}{2}x](./images/e7938ece26865a3ec3a59247827fb5845fa9d18b.png) terms correspond to rectangles with sides ![\frac{B}{2}](./images/87549d303d9ca68adfc671536ad036f115870fad.png) and ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). See the left side of[Figure 1.8](./Chapter 1_ Math fundamentals.md) for an illustration.

![algebra__completing_the_square](./images/algebra__completing_the_square.png)

Figure 1.8: To complete the square in the expression ![x^2 +Bx + C](./images/df8e6d1240a4bcd9adf98162d36ef5ca6c4f41d1.png), we need to add the quantity ![(\frac{B}{2})^2](./images/3ed91144ea2cb584d0b7b0ef8fbdf59aca10d3de.png), which corresponds to a square (shown in darker colour) with sides equal to half the coefficient of the linear term. We also subtract ![(\frac{B}{2})^2](./images/3ed91144ea2cb584d0b7b0ef8fbdf59aca10d3de.png) so the overall value of the expression remains unchanged.

The square with area ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) and the two rectangles can be positioned to form a larger square with side length ![\big(x + \frac{B}{2}\big)](./images/47f2c86071f4e47588b4e9d264d7d1d487d047bd.png). Note there’s a small piece of sides ![\frac{B}{2}](./images/87549d303d9ca68adfc671536ad036f115870fad.png) by ![\frac{B}{2}](./images/87549d303d9ca68adfc671536ad036f115870fad.png) missing from the corner. To _complete the square_, we can add a term ![\big(\tfrac{B}{2}\big)^2](./images/0c3a9ec3b53cb5d328c450042bb3a610783f225c.png) to this expression. To preserve the equality, we also subtract ![\big(\tfrac{B}{2}\big)^2](./images/0c3a9ec3b53cb5d328c450042bb3a610783f225c.png) from the expression to obtain:

![\begin{align*}
x^2 + \tfrac{B}{2}x + \tfrac{B}{2}x \; + C
&\; = \; 	\underbrace{x^2 + \tfrac{B}{2}x + \tfrac{B}{2}x + \big(\tfrac{B}{2}\big)^2}_{ }  \; \; - \; \big(\tfrac{B}{2}\big)^2 \; \; + \; C   	\\
&\; = \; 	\qquad \quad \big(x+ \tfrac{B}{2}\big)^{\!2}  \qquad \; \; \; - \; \big(\tfrac{B}{2}\big)^2 \; \, + \; C.
\end{align*}](./images/21c620ef5a33fcb7c50df62dec3f384ddf79f5a9.png)

The right-hand side of this equation describes the area of the square with side length ![\big(x + \frac{B}{2}\big)](./images/47f2c86071f4e47588b4e9d264d7d1d487d047bd.png), minus the area of the small square ![\big(\tfrac{B}{2}\big)^2](./images/0c3a9ec3b53cb5d328c450042bb3a610783f225c.png), plus the constant ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png), as illustrated on the right side of[Figure 1.8](./Chapter 1_ Math fundamentals.md).

We can summarize the entire procedure in one equation:

![x^2 + Bx + C
=
\big(x \, \, \underbrace{\!+ \; \tfrac{B}{2} \!}_{(1)}\big)^2 \;  + \;  C \; \;   \underbrace{- \; \big(\tfrac{B}{2}\big)^2}_{(2)}.](./images/5209e08198c48c4105ee62e53465b2ad7202b597.png)

There are two things to remember when you want to apply the complete-the-square trick: (1) choose the constant inside the bracket to be ![\frac{B}{2}](./images/87549d303d9ca68adfc671536ad036f115870fad.png) (half of the linear coefficient), and (2) subtract ![\big(\frac{B}{2}\big)^2](./images/0c3a9ec3b53cb5d328c450042bb3a610783f225c.png) outside the bracket in order to keep the equation balanced.

####[Solving quadratic equations](./Front matter.md)

Suppose we want to solve the quadratic equation ![x^2  + Bx  + C = 0](./images/4ddb0adc8ba4e1e7688456b002282ccaa9ff0fbc.png). It’s not possible to solve this equation with the digging-toward-the-![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) approach from[Section 1.1](./Chapter 1_ Math fundamentals.md) (since ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) appears in both the quadratic term ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) and the linear term ![Bx](./images/78a06970e8d18072242507ec8e043116b0164c5b.png)). Enter the completing-the-square trick!

#####[Example](./Front matter.md)

Let’s find the solutions of the equation ![x^2+5x+6=0](./images/ce8b4160792dab1561782406efddb86ccdac727f.png). The coefficient of the linear term is ![B=5](./images/fbed64e8d17b22333e91ae91ceab6d59adae6edc.png), so we choose ![\frac{B}{2}=\frac{5}{2}](./images/4d4d430c2dee07d26fab49c145b1155c38d4ce71.png) for the constant inside the bracket, and subtract ![\big(\tfrac{B}{2}\big)^2 = \big(\tfrac{5}{2}\big)^2](./images/5e4a48de6f3aeb20ca7a1efef5703e46f09a7bb5.png) outside the bracket to keep the equation balanced. Completing the square gives

![x^2+5x+6  = \left(x+\tfrac{5}{2}\right)^2 + 6 - \big(\tfrac{5}{2}\big)^2 = 0.](./images/a8a09554cb5edbbaeedf52a8a916a62ea79a652c.png)

Next we use fraction arithmetic to simplify the constant terms in the expression: ![6 - \left(\tfrac{5}{2}\right)^{2} = 6\cdot\tfrac{4}{4} - \tfrac{25}{4} = \tfrac{24 - 25}{4} = \tfrac{-1}{4} = -0.25](./images/d4c4135d38764d61ce54acaecdde6178b22c25c5.png).

We’re left with the equation

![\left(x+2.5\right)^2 - 0.25 = 0,](./images/4042f24e014493fd38c1c783bbde1a9f3068f1c0.png)

which we can now solve by digging toward ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). First move ![0.25](./images/3fd7c54c74745045ec032a2da82c32f686242b0b.png) to the right-hand side to get ![\left(x+2.5\right)^2 = 0.25](./images/c5848fc1b0f1b85b6d2bdafb587d109041468379.png). Then take the square root on both sides to obtain ![(x+2.5) = \pm 0.5](./images/2b98eab22a5517c40f9e650f8f6e640d37176682.png), which simplifies to ![x = -2.5 \pm 0.5](./images/b4097e0d53eb274cf09ad24a10be68c145ccf03e.png). The two solutions are ![x=-2.5+0.5=-2](./images/dd134a586144dda461eb5a334d4cd0f0490a5e52.png) and ![x=-2.5-0.5=-3](./images/3dcb8b5d7c090bd43d0204890cab6aea44663846.png). You can verify these solutions by substituting the values in the original equation ![(-2)^2+5(-2)+6=0](./images/3c96383c156388caf70aa8f82b0dd6f3ff6b5d97.png) and similarly ![(-3)^2+5(-3)+6=0](./images/9d2b6f93efc03e0a32b94a565d3d9d53cc142325.png). Congratulations, you just solved a quadratic equation using a 1200-year-old algebra technique!

In the next section, we’ll learn how to leverage the complete-the-square trick to obtain a general-purpose formula for quickly solving quadratic equations.

###[Exercises](./Front matter.md)

E1.6 Factor the following quadratic expressions:

**a)** ![x^2-8x+7](./images/1e0679f8d86eb264def4e1dc256598873978f5b6.png) **b)** ![x^2+4x+4](./images/39a9e7cae0283a2fd291400e0d23bfa8dbfa329a.png) **c)** ![x^2-9](./images/0697a83b96e29cf05f63e371d985008341a151fd.png)

Guess the values ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) in the expression ![(x+p)(x+q)](./images/f0f2a70b0278aa9e9a88854e35b7ff0eb8e5d607.png).

E1.7 Solve the equations by completing the square.

**a)** ![x^2 + 2x - 15=0](./images/000c83fe369b181c84ac6cd84a81d435360d73d5.png) **b)** ![x^2 + 4x + 1=0](./images/9a82b0226a4df1f9d5bb01ee61b6cc4ba946b895.png)

##[1.6 Solving quadratic equations](./Chapter 1_ Math fundamentals.md)

What would you do if asked to solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the quadratic equation ![2x^2 = 4x + 6](./images/e6aaf9bdd35e19d901a9644dcfb420f65062d084.png)? This is called a _quadratic equation_ since it contains the unknown variable ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) squared. The name comes from the Latin _quadratus_, which means square. Quadratic equations appear often, so mathematicians created a general formula for solving them. In this section, we’ll learn about this formula and use it to put some quadratic equations in their place.

Before we can apply the formula, we need to rewrite the equation we are trying to solve in the following form:

![ax^2 + bx + c = 0.](./images/5b301653663b1a2051533bab284ecc6dac2607a7.png)

This is called the _standard form_ of the quadratic equation. We obtain this form by moving all the numbers and ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)s to one side and leaving only ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) on the other side. For example, to transform the quadratic equation ![2x^2 = 4x + 6](./images/e6aaf9bdd35e19d901a9644dcfb420f65062d084.png) into standard form, we subtract ![4x + 6](./images/c5e824bcd58d148c77467de2ab5293e4ef5268e6.png) from both sides of the equation to obtain ![2x^2 - 4x - 6 = 0](./images/812a222fc6a24e870eff5b9fe6006c9aa4c57ec6.png). What are the values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that satisfy this equation?

####[Quadratic formula](./Front matter.md)

The solutions to the equation ![ax^2 + bx + c = 0](./images/fd3cc0bb314c27f07e27c677b7f0f64aa1cef172.png) for ![a\neq0](./images/b468b98e09738362cd9966bda33c3e4eee60e0d1.png) are

![x_1 = \frac{-b + \sqrt{b^2-4ac} }{2a} 
\qquad \textrm{and} \qquad \; \;
x_2 = \frac{-b - \sqrt{b^2-4ac} }{2a} \, .](./images/7b35eddbe49b5ea59e1c36bd2b0e3bfb636e36f0.png)

The quadratic formula is usually abbreviated ![x=\frac{-b \pm \sqrt{b^2 - 4ac}}{2a}](./images/543b33da8c26fe808adfe4c322e90feec576e4a8.png), where the sign “![\pm](./images/545c8dfbc82d1670eaa90f9d9f8c6acd520fca13.png)” stands for both “![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png)” and “![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png).” The notation “![\pm](./images/545c8dfbc82d1670eaa90f9d9f8c6acd520fca13.png)” allows us to express both solutions ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) in one equation, but you should keep in mind there are really two solutions.

Let’s see how the quadratic formula is used to solve the equation ![2x^2 - 4x - 6 = 0](./images/812a222fc6a24e870eff5b9fe6006c9aa4c57ec6.png). Finding the two solutions requires the simple mechanical task of identifying ![a=2](./images/b064db3f557125195851654f973344ac447408eb.png), ![b=-4](./images/341edb26ec032d030664b6006abde67178567453.png), and ![c=-6](./images/e7270eb54c3e403eecb943bd4cdb57089bb89292.png), then plugging these values into the two parts of the formula:

![x_1 = \frac{4 + \sqrt{4^2-4(2)(-6)} }{4} = \frac{4 + \sqrt{16+48} }{4} = \frac{4 + \sqrt{64} }{4} = 3,](./images/9611aea4837dbf9c927ba13e4a8c3c3d91aa2c74.png)

![x_2 = \frac{4 - \sqrt{4^2-4(2)(-6)} }{4} = \frac{4 - \sqrt{16+48} }{4}  = \frac{4 - \sqrt{64} }{4} = -1.](./images/1dc6da4e489f1486710196d3d5bddf5180724f40.png)

We can easily verify that value ![x_1=3](./images/2e017fbf9d19cbc06c1f1cda4de10ca9a7f6bd6e.png) and ![x_2=-1](./images/8d64be4573bfad585a41f423e00f7ab0950ed2ac.png) both satisfy the original equation ![2x^2 = 4x + 6](./images/e6aaf9bdd35e19d901a9644dcfb420f65062d084.png).

####[Proof of the quadratic formula](./Front matter.md)

Every claim made by a mathematician comes with a _proof_, which is a step-by-step argument that shows why the claim is true. It’s easy to see where a proof starts and where a proof ends in mathematical texts. Each proof begins with the heading _Proof_ (usually in italics) and has the symbol “![\qedsymbol](./images/7567a4cc5e5220136c39b86f7c333f2a3c56c071.png)” at its end. The purpose of these demarcations is to give readers the option to skip the proof. It’s not necessary to read and understand the proofs of all math statements, but reading proofs can often lead you to a more solid understanding of the material.

I want you to see the proof of the quadratic formula because it’s an important result that you’ll use very often to solve math problems. Reading the proof will help you understand where the quadratic formula comes from. The proof relies on the completing-the-square technique from the previous section, and some basic algebra operations. You can totally handle this!

We’re starting from the quadratic equation ![ax^2 + bx + c = 0](./images/fd3cc0bb314c27f07e27c677b7f0f64aa1cef172.png), and we’re making the additional assumption that ![a\neq 0](./images/b468b98e09738362cd9966bda33c3e4eee60e0d1.png). We want to find the value or values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that satisfy this equation.

The first thing we want to do is divide by ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) to obtain the equivalent equation

![x^2 + \frac{b}{a}x  + \frac{c}{a} = 0.](./images/3b856d26ae3b842174d689f644fd076971ae8c8c.png)

We are allowed to divide by ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) since we assumed that ![a \neq 0](./images/b468b98e09738362cd9966bda33c3e4eee60e0d1.png).

Next we apply the _complete the square_ trick to the quadratic expression, to obtain an equivalent expression of the form ![(x+?)^2 + ?](./images/ee9793f58d1c3df67ba4b2b745dfcc6770bd158e.png). Recall that the trick for completing the square is to choose the number inside the bracket to be half the coefficient of the linear term of the quadratic expression, which is ![\frac{b}{2a}](./images/5f193accefbb90688d8c5ce47bfb3e03b6830622.png) in this case. We must also subtract the square of this term outside the bracket in order to maintain the equality. After completing the square, we’re left with the following equation:

![\left(x + \frac{b}{2a} \right)^{\!2} + \frac{c}{a} - \frac{b^2}{4a^2}	=	0.](./images/3f8334271bf00b4fc54d3526cf178df3d2599fe2.png)

From here, we use the standard digging-toward-the-![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) procedure. Move all constants to the right-hand side,

![\left(x + \frac{b}{2a}\right)^{\!2} \;  = \;  \frac{b^2}{4a^2} -\frac{c}{a}\,,](./images/52d8769135745dccf0c6962d153feaaaff2e2f86.png)

and take the square root of both sides to undo the square function:

![\; \; \quad \qquad x + \frac{b}{2a}  \; = \; \pm \sqrt{ \frac{b^2}{4a^2} -\frac{c}{a} }\,.](./images/b677ccaeca9194de7694360b26dc977c73827c83.png)

Since any number and its opposite have the same square, taking the square root gives us two possible solutions, which we denote using the “![\pm](./images/545c8dfbc82d1670eaa90f9d9f8c6acd520fca13.png)” symbol.

Next we subtract ![\frac{b}{2a}](./images/5f193accefbb90688d8c5ce47bfb3e03b6830622.png) from both sides of the equation to isolate ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and obtain ![x  = - \frac{b}{2a}  \pm \sqrt{ \frac{b^2}{4a^2} -\frac{c}{a} }](./images/278577afb2cb8c8d97b8e8720cf484159fe65e03.png). We tidy up the mess under the square root, ![\sqrt{ \frac{b^2}{4a^2}  -\frac{c}{a} }
= \sqrt{ \frac{b^2}{4a^2} -\frac{4a\,\cdot\, c}{4a\,\cdot\, a} }
= \sqrt{ \frac{b^2 - 4ac}{4a^2}  }
= \frac{\sqrt{b^2 -4ac}  }{ 2a   }](./images/74f9a2061fe5858740c950e5d31f5fd4ca59cbe1.png), and add the fractions on the right-hand side to obtain ![x = \frac{-b \pm \sqrt{b^2-4ac} }{2a}](./images/543b33da8c26fe808adfe4c322e90feec576e4a8.png). The solutions to the quadratic equation ![ax^2 + bx + c = 0](./images/fd3cc0bb314c27f07e27c677b7f0f64aa1cef172.png) are

![x_1 = \frac{-b + \sqrt{b^2-4ac} }{2a}
\qquad \textrm{and} \qquad
x_2  = \frac{-b - \sqrt{b^2-4ac} }{2a}\,.](./images/fa5ab3f84ea102b49f2a42234927f796b2a271a6.png)

This completes the proof of the quadratic formula.

The expression ![b^2-4ac](./images/b4455eea522be23a674b7842874fb2e3dd69b40b.png) is called the _discriminant_ of the equation. The discriminant tells us important information about the solutions of the equation ![ax^2 + bx + c = 0](./images/fd3cc0bb314c27f07e27c677b7f0f64aa1cef172.png). The solutions ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) correspond to real numbers if the discriminant is positive or zero: ![b^2-4ac \geq 0](./images/9363e2174c64b3b3bd20036dcc70807f46c95fd7.png). When the discriminant is zero (![b^2-4ac = 0](./images/44822f985628bf78e46cd851d62e03c4823051eb.png)), the equation has only one solution since ![x_1= x_2 = \frac{-b}{2a}](./images/38bbb4efb9b89f22d513e6045f02cb34ad4bf671.png). If the discriminant is negative, ![b^2-4ac < 0](./images/9703a2a71b94d359d5f5d83763d7c97871f22406.png), the quadratic formula requires computing the square root of a negative number, which is not allowed for real numbers.

####[Alternative proof](./Front matter.md)

To prove the quadratic formula, we don’t necessarily need to show the algebra steps we followed to obtain the formula as outlined above. The quadratic formula states that ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) are solutions. To prove the formula is correct we can simply plug ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) into the equation ![ax^2 + bx + c = 0](./images/fd3cc0bb314c27f07e27c677b7f0f64aa1cef172.png) to verify that ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) are solutions. Verify this on your own.

###[Applications](./Front matter.md)

####[The golden ratio](./Front matter.md)

The _golden ratio_ is an essential proportion in geometry, art, aesthetics, biology, and mysticism, and is usually denoted as ![\varphi=\frac{1+\sqrt{5}}{2}=1.6180339\ldots](./images/7c516e1590d1e5ae59a5fa6d48f93231146c8f75.png). This ratio is determined as the positive solution to the quadratic equation

![x^2 -x -1 = 0.](./images/063a4595557649c9036fbd7b8d3b96012a01cc76.png)

Applying the quadratic formula to this equation yields two solutions,

![x_1 = \frac{1+\sqrt{5}}{2} = \varphi
\qquad
\textrm{and}
\qquad
x_2 = \frac{1-\sqrt{5}}{2} = - \frac{1}{\varphi} \, .](./images/87c852f4032c581fac75513c4fba01aea8da6a9f.png)

You can learn more about the various contexts in which the golden ratio appears from the[Wikipedia article](./Golden_ratio.md) on the subject.

###[Explanations](./Front matter.md)

####[Multiple solutions](./Front matter.md)

Often, we are interested in only one of the two solutions to the quadratic equation. It will usually be obvious from the context of the problem which of the two solutions should be kept and which should be discarded. For example, the _time of flight_ of a ball thrown in the air from a height of ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) metres with an initial velocity of ![12](./images/54f577f0cef96c9c252a77cc3e94bfff64ec11ad.png) metres per second is obtained by solving the equation ![(-4.9)t^2+12t+3=0](./images/09421ed007be67b900cfe5d9bbc4e15b19f7845a.png). The two solutions of the quadratic equation are ![t_1=-0.229](./images/6bb1e48773f286d4c100ab0647da6139144efede.png) and ![t_2=2.678](./images/efb3678588b5f305c8447aa7faf41a16578e0d5d.png). The first answer ![t_1](./images/a96a16c1768364abb21bf6d3180620d34ab79599.png) corresponds to a time in the past so we reject it as invalid. The correct answer is ![t_2](./images/d80d9d67494503d65144324fc583772b50dabfd1.png). The ball will hit the ground after ![t=2.678](./images/4b7e1a03ccecb43b3ab39d9c8f5076874622a95c.png) seconds.

####[Relation to factoring](./Front matter.md)

In the previous section we discussed the _quadratic factoring_ operation by which we could rewrite a quadratic function as the product of a constant and two factors:

![f(x)=ax^2+bx+c=a(x-x_1)(x-x_2).](./images/ae13173974a48c188883d99f90c37330698f49aa.png)

The two numbers ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) are called the _roots_ of the function: these points are where the function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) touches the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis.

You now have the ability to factor any quadratic equation: use the quadratic formula to find the two solutions, ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), then rewrite the expression as ![a(x-x_1)(x-x_2)](./images/ac7101b53df3c7b6e1b6f07e1d86dc99dd9ca8b1.png).

Some quadratic expressions cannot be factored, however. These “unfactorable” expressions correspond to quadratic functions whose graphs do not touch the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis. They have no real solutions (no roots). There is a quick test you can use to check if a quadratic function ![f(x)=ax^2+bx+c](./images/7b4e833ccdeb0b66165c7a185dc8474b599dd740.png) has roots (touches or crosses the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis) or doesn’t have roots (never touches the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis). If ![b^2-4ac>0](./images/caf6f95b116d7d1980923e4c3aebf0d9ebabbd8a.png) then the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) has two roots. If ![b^2-4ac=0](./images/44822f985628bf78e46cd851d62e03c4823051eb.png), the function has only one root, indicating the special case when the function touches the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis at only one point. If ![b^2-4ac<0](./images/9703a2a71b94d359d5f5d83763d7c97871f22406.png), the function has no roots. In this case, the quadratic formula fails because it requires taking the square root of a negative number, which is not allowed (for now). We’ll come back to the idea of taking square roots of negative numbers in[Section 1.14](./Chapter 1_ Math fundamentals.md) (see page 1.14).

###[Links](./Front matter.md)

\[ Algebra explanation of the quadratic formula \][`https://www.youtube.com/watch?v=r3SEkdtpobo`](./watch_v=r3SEkdtpobo.md)

\[ Visual explanation of the quadratic formula derivation \][`https://www.youtube.com/watch?v=EBbtoFMJvFc`](./watch_v=EBbtoFMJvFc.md)

###[Exercises](./Front matter.md)

E1.8 Solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the quadratic equation ![2x^2-x=3](./images/ab625694f772f27f6054e095e10119a98618ffbd.png).

E1.9 Solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the equation ![x^4-4x^2+4=0](./images/a61875fcc9d9618ddb18012425348840ea870d78.png).

Use the substitution ![y=x^2](./images/830f89201891605011673c09292abc520547457f.png).

##[1.7 The Cartesian plane](./Chapter 1_ Math fundamentals.md)

The Cartesian plane, named after famous philosopher and mathematician René Descartes, is used to visualize pairs of numbers ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png).

Consider first the _number line_ representation for numbers.

![number_line](./images/number_line.png)

Figure 1.9: Every real number ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) corresponds to a point on the number line. The number line extends indefinitely to the left (toward negative infinity) and to the right (toward positive infinity).

The Cartesian plane is the two-dimensional generalization of the number line. Generally, we call the plane’s horizontal axis “the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis” and its vertical axis “the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis.” We put notches at regular intervals on each axis so we can measure distances.

![empty_coordinate_system](./images/empty_coordinate_system.png)

Figure 1.10: Every point in the Cartesian plane corresponds to a pair of real numbers ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png). Points ![P=(P_x,P_y)](./images/a4563a54a3cadb4f75dc6ebf9fce19f9cd4be411.png), vectors ![\vec{v}=(v_x,v_y)](./images/261a887c54e70e24450de2619a47bc054de1a0de.png), and graphs of functions ![(x,f(x))](./images/77a775792b03ee5e29970c57825514fa5637b1ef.png) live here.

[Figure 1.10](./Chapter 1_ Math fundamentals.md) is an example of an empty Cartesian coordinate system. Think of the coordinate system as an empty canvas. What can you draw on this canvas?

###[Vectors and points](./Front matter.md)

A _point_ ![P=(P_x,P_y)](./images/b2b822ec2101ce7777578420162a777f76eeca7c.png) in the Cartesian plane has an ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-coordinate and a ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinate. To find this point, start from the origin—the point (0,0)—and move a distance ![P_x](./images/b1a4d23e560b672f17b435aa4557dbd21f156683.png) on the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis, then move a distance ![P_y](./images/fd52e5b2410dcbb405180accd08125785090de23.png) on the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis.

![vectors_and_point_in_cartesian_plane](./images/vectors_and_point_in_cartesian_plane.png)

Figure 1.11: A Cartesian plane which shows the point ![P=(-3,2)](./images/2fb28fb8590226f087477a39fd85fc7e39850361.png) and the vectors ![\vec{v}_1=(3,1)](./images/4896e8ed8c3cb84f31bce862406b9437a56779a4.png) and ![\vec{v}_2=\vec{v}_3=(-1,-2)](./images/22e609810187ea23b764599ca0c55ab2680ffe37.png).

Similar to a point, a vector ![\vec{v}=(v_x,v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png) is a pair of coordinates. Unlike points, we don’t necessarily start from the plane’s origin when mapping vectors. We draw vectors as arrows that explicitly mark where the vector starts and where it ends.

Note that vectors ![\vec{v}_2](./images/2dbe5e20ac504259a4c3b71592b315011fb78245.png) and ![\vec{v}_3](./images/d63fd9bb74319ed4e2f1dfb7240598e43ac4d302.png) illustrated in[Figure 1.11](./Chapter 1_ Math fundamentals.md) are actually the _same_ vector—the “displace left by ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) and down by ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png)” vector. It doesn’t matter where you draw this vector, it will always be the same whether it begins at the plane’s origin or elsewhere.

###[Graphs of functions](./Front matter.md)

The Cartesian plane is great for visualizing functions. You can think of a function as a set of input-output pairs ![(x,f(x))](./images/ce58134a57443a546d1fccbafa99c55bc06f1e8b.png). You can draw the _graph_ of a function by letting the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinate represent the function’s output value:

![(x,y) = (x,f(x)).](./images/a1ec928cd23e5bddb2a5296fc384a6532f9ccca5.png)

For example, with the function ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png), we can pass a line through the set of points

![(x,y) = (x, x^2),](./images/11fa9b1b67d83552f04b2ee4a11cdcc3854d8fe0.png)

and obtain the graph shown in[Figure 1.12](./Chapter 1_ Math fundamentals.md).

![graph_of_quadratic_func](./images/graph_of_quadratic_func.png)

Figure 1.12: The graph of the function ![f(x)=x^2](./images/6be7c05bf214c3bbc82b53bfb18dcfd9b1ffece6.png) consists of all pairs of points ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png) in the Cartesian plane that satisfy ![y=x^2](./images/7d207c92c39723fcd0475684abb4b5b2cf056302.png).

When plotting functions by setting ![y=f(x)](./images/7b49e4a41f7dceef9f4e593fe8b4f6aa481e96cc.png), we use a special terminology for the two axes. The ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis represents the _independent_ variable (the one that varies freely), and the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis represents the _dependent_ variable ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png), since ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) depends on ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).

To draw the graph of any function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png), use the following procedure. Imagine making a sweep over all of the possible input values for the function. For each input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), put a point at the coordinates ![(x,y)=(x,f(x))](./images/7fee87a968217496824108e5c7ae6320df4e13a9.png) in the Cartesian plane. Using the graph of a function, you can literally _see_ what the function does: the “height” ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) of the graph at a given ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-coordinate tells you the value of the function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png).

###[Dimensions](./Front matter.md)

The number line is one-dimensional. Every number ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) can be visualized as a point on the number line. The Cartesian plane has two dimensions: the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) dimension and the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) dimension. If we need to visualize math concepts in 3D, we can use a three-dimensional coordinate system with ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png) axes (see[Figure 1.55](./Chapter 1_ Math fundamentals.md) on page 1.55).

##[1.8 Functions](./Chapter 1_ Math fundamentals.md)

We need to have a relationship talk. We need to talk about functions. We use functions to describe the relationships between variables. In particular, functions describe how one variable _depends_ on another.

For example, the revenue ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) from a music concert depends on the number of tickets sold ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png). If each ticket costs ![\$25](./images/4af084dd27ad83c313a45046b9d84730669aaee9.png), the revenue from the concert can be written _as a function of_ ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) as follows: ![R(n) = 25n](./images/a73e8345b643a48262a4b31e901f4634f72d8336.png). Solving for ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) in the equation ![R(n)=7000](./images/2e7521c4b4282c21d4f7414703483387547263a7.png) tells us the number of ticket sales needed to generate ![\$7000](./images/d84b4575589d34a4894565ef79e40cdb255053f4.png) in revenue. This is a simple model of a function; as your knowledge of functions builds, you’ll learn how to build more detailed models of reality. For instance, if you need to include a ![5\%](./images/03b961b42c91552d09fa2317147dd96fb7277aac.png) processing charge for issuing the tickets, you can update the revenue model to ![R(n) = 0.95\cdot25\cdot n](./images/4fe2a7cb72c52058ed88c80961ff33a3d200b7d6.png). If the estimated cost of hosting the concert is ![C=\$2000](./images/4ed191857f4656fd69020662b1edbb153a399c81.png), then the profit from the concert ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) can be modelled as

![\begin{align*}
P(n) 	&= R(n) \; - \; C 				\\
&= 0.95\cdot \$25\cdot n \; -  \;  \$2000
\end{align*}](./images/170d49f87726aa31234afe9195ecda040e28bb8c.png)

The function ![P(n)=23.75n-2000](./images/61f2256912be7cc849f9aa72dc73b6cb88d1906c.png) models the profit from the concert as a function of the number of tickets sold. This is a pretty good model already, and you can always update it later as you learn more information.

The more functions you know, the more tools you have for modelling reality. To “know” a function, you must be able to understand and connect several of its aspects. First you need to know the function’s mathematical **definition**, which describes exactly what the function does. Starting from the function’s definition, you can use your existing math skills to find the function’s **properties**. You must also know the **graph** of the function; what the function looks like if you plot ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) versus ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) in the[Cartesian plane](./Chapter 1_ Math fundamentals.md). It’s also a good idea to remember the **values** of the function for some important inputs. Finally—and this is the part that takes time—you must learn about the function’s **relations** to other functions.

###[Definitions](./Front matter.md)

A _function_ is a mathematical object that takes numbers as inputs and produces numbers as outputs. We use the notation

![f \colon A \to B](./images/9d31d7f95f2bc45c29422ad60397cf3ee4d76faa.png)

to denote a function from the input set ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) to the output set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). In this book, we mostly study functions that take real numbers as inputs and give real numbers as outputs: ![f\colon\mathbb{R} \to \mathbb{R}](./images/0f51ba12bb06036fe005cd004bc9e4020e4e7264.png).

![functions-definition](./images/functions-definition.png)

Figure 1.13: An abstract representation of a function ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png) from the set ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) to the set ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png). The function ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png) is the arrow which _maps_ each input ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) in ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) to an output ![f(x)](./images/e991ff22266fdbbf51e9ab850aa72059edbea8de.png) in ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png). The output of the function ![f(x)](./images/e991ff22266fdbbf51e9ab850aa72059edbea8de.png) is also denoted ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png).

A function is not a number; rather, it is a _mapping_ from numbers to numbers. We say “![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) maps ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) to ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png).” For any input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), the output value of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) for that input is denoted ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png), which is read as “![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).”

We’ll now define some fancy technical terms used to describe the input and output sets of functions.

-   ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png): the _source set_ of the function describes the types of numbers that the function takes as inputs.
-   ![\textrm{Dom}(f)](./images/41c456f937a78c9f31fb17aaa1e6d69dfbcc165b.png): the _domain_ of a function is the set of allowed input values for the function.
    
-   ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png): the _target set_ of a function describes the type of outputs the function has. The target set is sometimes called the _codomain_.
-   ![\textrm{Im}(f)](./images/524c3c01145aaf0ec393e3c3261591d24f94001c.png): the _image_ of the function is the set of all possible output values of the function. The image is sometimes called the _range_.

See[Figure 1.14](./Chapter 1_ Math fundamentals.md) for an illustration of these concepts. The purpose of introducing all this math terminology is so we’ll have words to distinguish the general types of inputs and outputs of the function (real numbers, complex numbers, vectors) from the specific properties of the function like its domain and image.

![functions_sets_domain_image](./images/functions_sets_domain_image.png)

Figure 1.14: Illustration of the input and output sets of a function ![f \colon A \to B](./images/eddde5ed4c0380c11549f39010b100c71c6ed8c5.png). The _source set_ is denoted ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) and the _domain_ is denoted ![\textrm{Dom}(f)](./images/84dea59856673db5becc55acb6269e6e72cf619b.png). Note that the function’s domain is a subset of its source set. The _target set_ is denoted ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) and the _image_ is denoted ![\textrm{Im}(f)](./images/4969ff65337d1914d6819702a346326a3b2b001b.png). The image is a subset of the target set.

Let’s look at an example to illustrate the difference between the source set and the domain of a function. Consider the square root function ![f \colon \mathbb{R} \to \mathbb{R}](./images/0f51ba12bb06036fe005cd004bc9e4020e4e7264.png) defined as ![f(x) = \sqrt{x}](./images/bc20cca97740e11e58a05c4912bea200fcff083d.png), which is shown in[Figure 1.15](./Chapter 1_ Math fundamentals.md). The source set of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is the set of real numbers—yet only nonnegative real numbers are allowed as inputs, since ![\sqrt{x}](./images/feb1aa654c5a0153a8a477c91f43fb87e105d2ce.png) is not defined for negative numbers. Therefore, the domain of the square root function is only the nonnegative real numbers: ![\textrm{Dom}(f) = \mathbb{R}_+ = \{x \in \mathbb{R} \; | \; x \geq 0 \}](./images/1394c030caf9f54eb2039a4b411ef216d34e5140.png). Knowing the domain of a function is essential to using the function correctly. In this case, whenever you use the square root function, you need to make sure that the inputs to the function are nonnegative numbers.

The complicated-looking expression between the curly brackets uses _set notation_ to define the set of nonnegative numbers ![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png). In words, the expression ![\mathbb{R}_+ = \{x \in \mathbb{R} \; | \; x \geq 0 \}](./images/819c53df1aa3df4a4895e825dcb97c2069c2d3dc.png) states that “![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png) is defined as the set of all real numbers ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) such that ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is greater than or equal to zero.” We’ll discuss set notation in more detail in[Section 1.16](./Chapter 1_ Math fundamentals.md). For now, you can just remember that ![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png) represents the set of nonnegative real numbers.

![functions_sets_domain_image-sqrt_x](./images/functions_sets_domain_image-sqrt_x.png)

Figure 1.15: The input and output sets of the function ![f(x) = \sqrt{x}](./images/ac69a8bd2fae60c518a4a37ccda55aa47bfe43e8.png). The domain of ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png) is the set of nonnegative real numbers ![\mathbb{R}_+](./images/2a5bafe4716a7945e6b76d693de91269a941aa9a.png) and its image is ![\mathbb{R}_+](./images/2a5bafe4716a7945e6b76d693de91269a941aa9a.png).

To illustrate the difference between the image of a function and its target set, let’s look at the function ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) shown in[Figure 1.16](./Chapter 1_ Math fundamentals.md). The quadratic function is of the form ![f\colon\mathbb{R} \to \mathbb{R}](./images/0f51ba12bb06036fe005cd004bc9e4020e4e7264.png). The function’s source set is ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) (it takes real numbers as inputs) and its target set is ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) (the outputs are real numbers too); however, not all real numbers are possible outputs. The _image_ of the function ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) consists only of the nonnegative real numbers ![\mathbb{R}_+ = \{y \in \mathbb{R} \; | \; y \geq 0 \}](./images/f152661f0b402b694c685b5546be6504200c2f6d.png), since ![f(x)\geq 0](./images/e585931a09c7bd10d250280230b00745a6fb41b4.png) for all ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).

![functions_sets_domain_image-x_squared](./images/functions_sets_domain_image-x_squared.png)

Figure 1.16: The function ![f(x) = x^2](./images/6be7c05bf214c3bbc82b53bfb18dcfd9b1ffece6.png) is defined for all reals: ![\textrm{Dom}(f) = \mathbb{R}](./images/c38913cfdfc1b73908448475716286697f493188.png). The image of the function is the set of nonnegative real numbers: ![\textrm{Im}(f) = \mathbb{R}_+](./images/61bf43cc5fa9144cdf2a000e7216b637b30c1705.png).

###[Function properties](./Front matter.md)

We’ll now introduce some additional terminology for describing three important function properties. Every function is a mapping from a source set to a target set, but what kind of mapping is it?

-   A function is _injective_ if it maps two different inputs to two different outputs. If ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) are two input values that are not equal ![x_1 \neq x_2](./images/305c3b9baef39f2480ed016ebab8a9ca3cb33ba1.png), then the output values of an injective function will also not be equal ![f(x_1) \neq f(x_2)](./images/81181c00da24d6d29ca352671743624d837ac6e5.png).
-   A function is _surjective_ if its image is equal to its target set. For every output ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in the target set of a surjective function, there is at least one input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in its domain such that ![f(x) = y](./images/aad6a42679d823357232d67c11fb325cfb6404be.png).
-   A function is _bijective_ if it is both injective and surjective.

I know this seems like a lot of terminology to get acquainted with, but it’s important to have names for these function properties. We’ll need this terminology to give a precise definition of the _inverse function_ in the next section.

#####[Injective property](./Front matter.md)

We can think of _injective_ functions as pipes that transport fluids between containers. Since fluids cannot be compressed, the “output container” must be at least as large as the “input container.” If there are two distinct points ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) in the input container of an injective function, then there will be two distinct points ![f(x_1)](./images/72b868cf0cb113e7db9fc2aae7490c6e3e6f9a24.png) and ![f(x_2)](./images/0b0bcbf59bbdd1082a2f6fee783748bf40c66188.png) in the output container of the function as well. In other words, injective functions don’t smoosh things together.

In contrast, a function that doesn’t have the injective property can map several different inputs to the same output value. The function ![f(x) = x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) is not injective since it sends inputs ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![-x](./images/665de79093233e3f251ecb3a98ec9fb472a7dbd8.png) to the same output value ![f(x)=f(-x)=x^2](./images/90f6933da7c74b4f70ecf170982ac2d4c81cfe3e.png), as illustrated in[Figure 1.16](./Chapter 1_ Math fundamentals.md).

The maps-distinct-inputs-to-distinct-outputs property of injective functions has an important consequence: given the output of an injective function ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), there is only one input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) such that ![f(x)=y](./images/aad6a42679d823357232d67c11fb325cfb6404be.png). If a second input ![x'](./images/a586d5136004ea7453b41817f14e8cc4a0e27a75.png) existed that also leads to the same output ![f(x)=f(x')=y](./images/f16fe321c279c04c40760dfbd708a36b5fdaf180.png), then the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) wouldn’t be injective. For each of the outputs ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) of an injective function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png), there is a _unique_ input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) such that ![f(x)=y](./images/aad6a42679d823357232d67c11fb325cfb6404be.png). In other words, injective functions have a unique-input-for-each-output property.

#####[Surjective property](./Front matter.md)

A function is _surjective_ if its outputs cover the entire target set: every number in the target set is a possible output of the function for some input. For example, the function ![f \colon \mathbb{R} \to \mathbb{R}](./images/0f51ba12bb06036fe005cd004bc9e4020e4e7264.png) defined by ![f(x) = x^3](./images/93a7014078c09731603e500dd212378e2f714d3d.png) is surjective: for every number ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in the target set ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png), there is an input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), namely ![x=\sqrt[3]{y}](../Images/0d6be0cd2c2fbb8d4b945b6757be26813435b107.png), such that ![f(x)=y](./images/aad6a42679d823357232d67c11fb325cfb6404be.png). The function ![f(x) = x^3](./images/93a7014078c09731603e500dd212378e2f714d3d.png) is surjective since its image is equal to its target set, ![\textrm{Im}(f) = \mathbb{R}](./images/244d43724f3c6fee4d75e45706979a3009f2b881.png), as shown in[Figure 1.17](./Chapter 1_ Math fundamentals.md).

On the other hand, the function ![f \colon \mathbb{R} \to \mathbb{R}](./images/0f51ba12bb06036fe005cd004bc9e4020e4e7264.png) defined by the equation ![f(x) = x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) is not surjective since its image is only the nonnegative numbers ![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png) and not the whole set of real numbers (see[Figure 1.16](./Chapter 1_ Math fundamentals.md)). The outputs of this function do not include the negative numbers of the target set, because there is no real number ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that can be used as an input to obtain a negative output value.

![functions_sets_domain_image-x_cubed](./images/functions_sets_domain_image-x_cubed.png)

Figure 1.17: For the function ![f(x) = x^3](./images/4536efb367d0e266ffeb90f5b9a621fcf4b76a16.png) the image is equal to the target set of the function, ![\textrm{Im}(f) = \mathbb{R}](./images/8f449bb54c783d3258b1fd83f6cffc4a80bfd731.png), therefore the function ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png) is surjective. The function ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png) maps two different inputs ![x_1 \neq x_2](./images/4c521f57955bae352fa7c5dff183ad76a6b3c850.png) to two different outputs ![f(x_1) \neq f(x_2)](./images/17a9e3c4742a8ed656d1e7428767b241cefe5854.png), so ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png) is injective. Since ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png) is both injective and surjective, it is a _bijective_ function.

#####[Bijective property](./Front matter.md)

A function is bijective if it is both injective and surjective. When a function ![f:A \to B](./images/fee1518c22dcddb6d3884996a42cf34180344a9d.png) has both the injective and surjective properties, it defines a _one-to-one correspondence_ between the numbers of the source set ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and the numbers of the target set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). This means for every input value ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), there is exactly one corresponding output value ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and for every output value ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), there is exactly one input value ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) such that ![f(x)=y](./images/aad6a42679d823357232d67c11fb325cfb6404be.png). An example of a bijective function is the function ![f \colon \mathbb{R} \to \mathbb{R}](./images/0f51ba12bb06036fe005cd004bc9e4020e4e7264.png) defined by ![f(x) = x^3](./images/93a7014078c09731603e500dd212378e2f714d3d.png) (see[Figure 1.17](./Chapter 1_ Math fundamentals.md)). For every input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the source set ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png), the corresponding output ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) is given by ![y=f(x)=x^3](./images/7b26088784534f447d47776baa5b00abaadd5f55.png). For every output value ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in the target set ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png), the corresponding input value ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is given by ![x=\sqrt[3]{y}](../Images/0d6be0cd2c2fbb8d4b945b6757be26813435b107.png).

A function is not bijective if it lacks one of the required properties. Examples of non-bijective functions are ![f(x)=\sqrt{x}](./images/bc20cca97740e11e58a05c4912bea200fcff083d.png), which is not surjective and ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png), which is neither injective nor surjective.

#####[Counting solutions](./Front matter.md)

Another way to understand the injective, surjective, and bijective properties of functions is to think about the solutions to the equation ![f(x)=b](./images/2a861eb958347b4a8233c47a8b9223c21095ea76.png), where ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) is a number in the target set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). The function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is injective if the equation ![f(x)=b](./images/2a861eb958347b4a8233c47a8b9223c21095ea76.png) has _at most one_ solution for every number ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png). The function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is surjective if the equation ![f(x)=b](./images/2a861eb958347b4a8233c47a8b9223c21095ea76.png) has _at least one_ solution for every number ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png). If the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is bijective then it is both injective and surjective, which means the equation ![f(x)=b](./images/2a861eb958347b4a8233c47a8b9223c21095ea76.png) has _exactly one_ solution.

###[Inverse function](./Front matter.md)

We used inverse functions repeatedly in previous chapters, each time describing the inverse function informally as an “undo” operation. Now that we have learned about bijective functions, we can give a the precise definition of the inverse function and explain some of the details we glossed over previously.

Recall that a _bijective_ function ![f:A \to B](./images/fee1518c22dcddb6d3884996a42cf34180344a9d.png) is a _one-to-one correspondence_ between the numbers in the source set ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and numbers in the target set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png): for every output ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), there is exactly one corresponding input value ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) such that ![f(x)=y](./images/aad6a42679d823357232d67c11fb325cfb6404be.png). The _inverse function_, denoted ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png), is the function that takes any output value ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in the set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and finds the corresponding input value ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that produced it ![f^{-1}(y) = x](./images/b425fe2af879842b3e5bae3d030e704dd77dc2d7.png).

![functions-inverse](./images/functions-inverse.png)

Figure 1.18: The inverse ![f^{-1}](./images/40657bbd9974ddbac2723bec6cae199f88f156fb.png) undoes the operation of the function ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png).

For every bijective function ![f:A \to B](./images/fee1518c22dcddb6d3884996a42cf34180344a9d.png), there exists an inverse function ![f^{-1}: B \to A](./images/95939cfee8985529ebf48ac57c46ef49a0907d56.png) that performs the _inverse mapping_ of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png). If we start from some ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), apply ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png), and then apply ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png), we’ll arrive—full circle—back to the original input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png):

![f^{-1}\!\big( \; f(x) \; \big) = x.](./images/fe59112a4376e894d6bab08ee5a90c8df9110b7c.png)

In[Figure 1.18](./Chapter 1_ Math fundamentals.md) the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is represented as a forward arrow, and the inverse function ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) is represented as a backward arrow that puts the value ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) back to the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) it came from.

Similarly, we can start from any ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in the set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and apply ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) followed by ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) to get back to the original ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) we started from:

![f\!\big( \; f^{-1}(y) \; \big) = y.](./images/466b209644bb23b5c5ec042f771a9e124f55b203.png)

In words, this equation tells us that ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is the “undo” operation for the function ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png), the same way ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) is the “undo” operation for ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png).

If a function is missing the injective property or the surjective property then it isn’t bijective and it doesn’t have an inverse. Without the injective property, there could be two inputs ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![x'](./images/a586d5136004ea7453b41817f14e8cc4a0e27a75.png) that both produce the same output ![f(x)=f(x')=y](./images/f16fe321c279c04c40760dfbd708a36b5fdaf180.png). In this case, computing ![f^{-1}(y)](./images/1e4fdd8e948ff1492990e3b3fc66f077e53f73b5.png) would be impossible since we don’t know which of the two possible inputs ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) or ![x'](./images/a586d5136004ea7453b41817f14e8cc4a0e27a75.png) was used to produce the output ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png). Without the surjective property, there could be some output ![y'](./images/89a3e5b4e7e5ffa60e5d59b68fdd0b4492ba6ef1.png) in ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) for which the inverse function ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) is not defined, so the equation ![f(f^{-1}(y)) = y](./images/07cd2f10a50c90d4cd0d4f1e57c97aef11b47655.png) would not hold for all ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). The inverse function ![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png) exists only when the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) is bijective.

Wait a minute! We know the function ![f(x) = x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) is not bijective and therefore doesn’t have an inverse, but we’ve repeatedly used the square root function as an inverse function for ![f(x) = x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png). What’s going on here? Are we using a double standard like a politician that espouses one set of rules publicly, but follows a different set of rules in their private dealings? Is mathematics corrupt?

Don’t worry, mathematics is not corrupt—it’s all legit. We can use inverses for non-bijective functions by imposing _restrictions_ on the source and target sets. The function ![f(x) = x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) is not bijective when defined as a function ![f: \mathbb{R} \to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png), but it _is_ bijective if we define it as a function from the set of nonnegative numbers to the set of nonnegative numbers, ![f: \mathbb{R}_+ \to \mathbb{R}_+](./images/bf0cfa0362e4d117d53377630db522b067b01e48.png). Restricting the source set to ![\mathbb{R}_+ = \{x \in \mathbb{R} \; | \; x \geq 0 \}](./images/819c53df1aa3df4a4895e825dcb97c2069c2d3dc.png) makes the function injective, and restricting the target set to ![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png) also makes the function surjective. The function ![f: \mathbb{R}_+ \to \mathbb{R}_+](./images/bf0cfa0362e4d117d53377630db522b067b01e48.png) defined by the equation ![f(x) = x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) is bijective and its inverse is ![f^{-1}(y) = \sqrt{y}](./images/38cf5359afac7c573bd6a83009ae76bd1d7db530.png).

It’s important to keep track the of restrictions on the source set we applied when solving equations. For example, solving the equation ![x^2 = c](./images/a944f657af0162a74ba42176618898d1c76f20df.png) by restricting the solution space to nonnegative numbers will give us only the positive solution ![x = \sqrt{c}](./images/772deeb4a19710cc867b3cfacd63188ca80c3a04.png). We have to manually add the negative solution ![x = -\sqrt{c}](./images/96abd29a561e622c2714820bf4b333378eafa2b9.png) in order to obtain the complete solutions: ![x = \sqrt{c}](./images/772deeb4a19710cc867b3cfacd63188ca80c3a04.png) or ![x = -\sqrt{c}](./images/96abd29a561e622c2714820bf4b333378eafa2b9.png), which is usually written ![x = \pm \sqrt{c}](./images/d5ab7bdc83043ecf3f43d32a8a2255a81243e1ed.png). The possibility of multiple solutions is present whenever we solve equations involving non-injective functions.

###[Function composition](./Front matter.md)

We can combine two simple functions by chaining them together to build a more complicated function. This act of applying one function after another is called _function composition_. Consider for example the composition:

![f\!\circ\!g \, (x) =  f\!\left( \: g(x) \: \right) = z.](./images/f1c1d11c5e65a1c4f69c19307e24dd17d133b8bf.png)

![functions-composition](./images/functions-composition.png)

Figure 1.19: The function composition ![f\!\circ\!g](./images/ed84f770f40be8130720b951f994f4ebc8847ef4.png) describes the combination of first applying the function ![g](./images/02d971083edc95192057f7439c1b92e3df1c2959.png), followed by the function ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png): ![f\circ g\,(x) = f(g(x))](./images/4a93520cc66b2d0e03233952f8a15eeae005774f.png).

[Figure 1.19](./Chapter 1_ Math fundamentals.md) illustrates the concept of function composition. First, the function ![g:A\to B](./images/4fb6fe750b899a355043e72d2a65a050d43252fc.png) acts on some input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) to produce an intermediary value ![y=g(x)](./images/5040150b60b0714402de924a554f6fa3f6328166.png) in the set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). The intermediary value ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) is then passed through the function ![f:B \to C](./images/c05add8bdf649697f843f959bf1afb3878142daa.png) to produce the final output value ![z=f(y) = f(g(x))](./images/97866b06823786a37ab4f29ca180e24e284ceda3.png) in the set ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png). We can think of the _composite function_ ![f \circ g](./images/525b5a0d10c1db2e3036359cd5005c80a885d52d.png) as a function in its own right. The function ![f\circ g: A \to C](./images/11b411768f04b02eb70477aec597b0b76d1c0be9.png) is defined through the formula ![f\circ g\,(x) = f(g(x))](./images/c7063a7f97ef3524fbd8c82e52b3791644c3b23c.png).

Don’t worry too much about the “![\circ](./images/31dc3d9b8d2635e37b421ae65c38d96f6b810085.png)” symbol—it’s just a convenient math notation I wanted you to know about. Writing ![f\circ g](./images/525b5a0d10c1db2e3036359cd5005c80a885d52d.png) is the same as writing ![f(g(x))](./images/d08082c4e6410ab9206c559129008dc063f06872.png). The important takeaway from[Figure 1.19](./Chapter 1_ Math fundamentals.md) is that functions can be combined by using the outputs of one function as the inputs to the next. This is a very useful idea for building math models. You can understand many complicated input-output transformations by describing them as compositions of simple functions.

#####[Example 1](./Front matter.md)

Consider the function ![g \colon \mathbb{R}_+ \to \mathbb{R}_+](./images/495cb39f10f68ad74a5d6e09a5db56f11922349d.png) given by ![g(x) = \sqrt{x}](./images/59dcae40ff87663758474befbc4873684131f5b8.png), and the function ![f \colon \mathbb{R} \to \mathbb{R}_+](./images/2e9cbec266996674c414fe9a9be9d9356e41862c.png) defined by ![f(x) = x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png). The composite function ![f \circ g \, (x) = (\sqrt{x})^2 = x](./images/92db19b0b4c3ec08419f066410c8cc5e4c50b867.png) is defined for all nonnegative reals. The composite function ![g \circ f](./images/00b94fb0e48a7929191b550d158b8db814c42d63.png) is defined for all real numbers, and we have ![g \circ f \, (x) = \sqrt{x^2} = |x|](./images/fe87c5c1362d2885e27898067e9a553ffea5dec4.png).

#####[Example 2](./Front matter.md)

The composite functions ![f \circ g](./images/525b5a0d10c1db2e3036359cd5005c80a885d52d.png) and ![g \circ f](./images/00b94fb0e48a7929191b550d158b8db814c42d63.png) describe different operations. If ![g(x) = \ln(x)](./images/02a2b93c8e9a37845d3730562f3182db82e9c906.png) and ![f(x) = x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png), the functions ![g \circ f \, (x) = \ln(x^2)](./images/1ec14293c94b3599a31c1bca00b7532cf6921598.png) and ![f \circ g \, (x) = (\ln x)^2](./images/3056c945fd969c301c6b6bef0b242c4b661a32db.png) have different domains and produce different outputs, as you can verify using a calculator.

Using the notation “![\circ](./images/31dc3d9b8d2635e37b421ae65c38d96f6b810085.png)” for function composition, we can give a concise description of the properties of a bijective function ![f: A \to B](./images/fee1518c22dcddb6d3884996a42cf34180344a9d.png) and its inverse function ![f^{-1}: B \to A](./images/95939cfee8985529ebf48ac57c46ef49a0907d56.png):

![(f^{-1} \circ  f)(x) = x
\qquad \textrm{and} \qquad
(f  \circ  f^{-1})(y) = y,](./images/76344380a42e6dbcd2f5a68c6ee451aabd7791b4.png)

for all ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and all ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

###[Function names](./Front matter.md)

We use short symbols like ![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png), ![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png), ![\times](./images/6c1ccbe8bb6958fb7f98fce646fdb82946c0ffa3.png), and ![\div](./images/b9b69bdcfb95f9d425f2158ac57705d7211d59aa.png) to denote most of the important functions used in everyday life. We also use the squiggle notation ![\sqrt{\phantom{x}}](./images/0dcc1b1e9d9165a6a9ae812829137ab709f5a778.png) for square roots and superscripts to denote exponents. All other functions are identified and denoted by their _name_. If I want to compute the _cosine_ of the angle ![60^\circ](./images/fa017a0b5a1cfa24a2498c20df91459d36ae3268.png) (a function describing the ratio between the length of one side of a right-angle triangle and the hypotenuse), I write ![\cos(60^\circ)](./images/43cae69ffd3e483b44991148e0f69d1b94c5c945.png), which means I want the value of the ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png) function for the input ![60^\circ](./images/fa017a0b5a1cfa24a2498c20df91459d36ae3268.png).

Incidentally, the function ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png) has a nice output value for that specific angle: ![\cos(60^\circ)=\frac{1}{2}](./images/c079bc44f63f8053fbffddc52620b72b461ff84c.png). Therefore, seeing ![\cos(60^\circ)](./images/43cae69ffd3e483b44991148e0f69d1b94c5c945.png) somewhere in an equation is the same as seeing ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png). To find other values of the function, say ![\cos(33.13^\circ)](./images/5a0eb33c64ae25cc8c18cf92149b384033f0c650.png), you’ll need a calculator. All scientific calculators have a convenient little ![\button{\cos}](./images/bfb8ab75efc60108a6aa4b2aae3c42af044d99fe.png) button for this very purpose.

###[Handles on functions](./Front matter.md)

When you learn about functions you learn about the different “handles” by which you can “grab” these mathematical objects. The main handle for a function is its **definition**: it tells you the precise way to calculate the output when you know the input. The function definition is an important handle, but it is also important to “feel” what the function does intuitively. How does one get a feel for a function?

####[Table of values](./Front matter.md)

One simple way to represent a function is to look at a list of input-output pairs: ![\big\{ \{ \text{in}=x_1, \text{out}=f(x_1) \}](./images/49c8d75b01cd9d3c854bd57571db30a4f45efa9b.png), ![\{ \text{in}~=~x_2,](./images/5d3a8110196d1df358ee7a094a382980948f9561.png) ![\text{out}=f(x_2) \}](./images/48dbf805257b7efea0a79ba7d569dca4f59b11ba.png), ![\{ \text{in}=x_3, \text{out}=f(x_3) \}, \ldots \big\}](./images/252b118e0da6f9bcb48cd8acd407ec4cd27b05b7.png). A more compact notation for the input-output pairs is ![\{ (x_1,f(x_1)),](./images/beb5f2afd03f53e0112e7ef3d727b21401ad41c4.png) ![(x_2,f(x_2)),](./images/fbce49bb77e385c7bd100bd8572e13596bc5326b.png) ![(x_3,f(x_3)), \,  \ldots \}](./images/32f7709032549948305784fac920c7b5647a3b4d.png), where the first number of each pair represents an input value and the second represents the output value given by the function.

We can also build a **table of values** by writing the input values in one column and recording the corresponding output values in a second column. You can choose inputs at random or focus on the important-looking ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) values in the function’s domain.

![\begin{align*}
\textrm{input}=x \qquad &\rightarrow	\qquad f(x)=\textrm{output}					\\
\underline{\hspace{3cm}}	\qquad &\phantom{\rightarrow} \; \qquad	\underline{\hspace{3cm}} \\
0		\qquad 	&\rightarrow	\qquad f(0)   \\
1		\qquad 	&\rightarrow	\qquad f(1)   \\
55		\qquad 	&\rightarrow	\qquad f(55)  \\
x_4		\qquad 	&\rightarrow	\qquad f(x_4)
\end{align*}](./images/28acbffbbdc9283240c978981e040f8922a38399.png)

Table 1.1: Table of input-output values of the function ![f(x)](./images/e991ff22266fdbbf51e9ab850aa72059edbea8de.png). The input values ![x = 0](./images/aa78f6a194098d11a5239ec5d5ad4f0fbff21af8.png), ![x = 1](./images/c05f845e5cc9939507fccda58e08dc7831b8de3a.png) and ![x = 55](./images/5d573ca73f5d93eb0fe3af544ee79ebaf7c3e600.png) are chosen to “test” what the function does.

You can create a table of values for any function you want to study. Follow the example shown in[Table 1.1](./Chapter 1_ Math fundamentals.md). Use the input values that interest you and fill out the right side of the table by calculating the value of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) for each input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).

####[Function graph](./Front matter.md)

One of the best ways to feel a function is to look at its graph. A graph is a line on a piece of paper that passes through all input-output pairs of a function. Imagine you have a piece of paper, and on it you draw a blank _coordinate system_ as in[Figure 1.20](./Chapter 1_ Math fundamentals.md).

![empty_coordinate_system](./images/empty_coordinate_system.png)

Figure 1.20: An empty ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png)\-coordinate system that you can use to draw function graphs. The graph of ![f(x)](./images/e991ff22266fdbbf51e9ab850aa72059edbea8de.png) consists of all the points for which ![(x,y)=(x,f(x))](./images/157c22fe73145ba6248db3fd1598b72054368e18.png). See[Figure 1.12](./Chapter 1_ Math fundamentals.md) on page 1.12 for the graph of ![f(x)=x^2](./images/6be7c05bf214c3bbc82b53bfb18dcfd9b1ffece6.png).

The horizontal axis is used to measure ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). The vertical axis is used to measure ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png). Because writing out ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) every time is long and tedious, we use a short, single-letter alias to denote the output value of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) as follows:

![y = f(x) = \text{output}.](./images/32d31076ddb8d3d7978df3fcd385c9e1b7b5d970.png)

Think of each input-output pair of the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) as a point ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) in the coordinate system. The graph of a function is a representational drawing of everything the function does. If you understand how to interpret this drawing, you can infer everything there is to know about the function.

####[Facts and properties](./Front matter.md)

Another way to feel a function is by knowing the function’s properties. This approach boils down to learning facts about the function and its connections to other functions. An example of a mathematical connection is the equation ![\log_{B}(x)=\frac{\log_b(x)}{\log_b(B)}](./images/b4b9f184bbe18ac12c0f5bfe9f50ec66b8fafbfb.png), which describes a link between the logarithmic function base ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and the logarithmic function base ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png).

The more you know about a function, the more “paths” your brain builds to connect to that function. Real math knowledge is not about memorization; it is about establishing a network of associations between different areas of information in your brain. See the concept maps on page 1 for an illustration of the paths that link math concepts. Mathematical thought is the usage of these associations to carry out calculations and produce mathematical arguments. For example, knowing about the connection between logarithmic functions will allow you compute the value of ![\log_7(e^3)](./images/5944ab12890ead655799f551c99598bd1d8c8d2b.png), even though calculators don’t have a button for logarithms base ![7](./images/7c8183005b1d0a8999b7a1cc791bffe88aeb450f.png). We find ![\log_7(e^3) = \frac{\ln e^3}{\ln 7} = \frac{3}{\ln 7}](./images/a9a5e355b6571ebda6060f1b9e216586ec232845.png), which can be computed using the ![\button{\ln}](./images/aadf9700fb3e763d4de901f702f0ac3d2ecd840e.png) button.

To develop mathematical skills, it is vital to practice path-building between concepts by solving exercises. With this book, I will introduce you to some of the many paths linking math concepts, but it’s on you to reinforce these paths through practice.

#####[Example 3](./Front matter.md)

Consider the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) from the real numbers to the real numbers (![f \colon \mathbb{R} \to \mathbb{R}](./images/0f51ba12bb06036fe005cd004bc9e4020e4e7264.png)) defined as ![f(x)=x^2+2x-3](./images/2326e3e8739dfa9140a18be48c7b6b5788086135.png). The value of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) when ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png) is ![f(1)=1^2+2(1)-3=0](./images/40c11e9e7fc69b4dc277c7c5a7fd81929793a1ea.png). When ![x=2](./images/e5434555c15a07cfe09b5b352b1965c74365967d.png), the output is ![f(2)=2^2+2(2)-3=5](./images/5fa472d9d82ff2c312ab33aa00988e3b51a8a314.png). What is the value of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) when ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png)? You can use algebra to rewrite this function as ![f(x)=(x+3)(x-1)](./images/d391773ac581edcda6f25b3022810a8599746da3.png), which tells you the graph of this function crosses the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis at ![x=-3](./images/699ea87ebc7ddbed03e723cff5e95c316d8c0389.png) and at ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png). The values above will help you plot the graph of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png).

#####[Example 4](./Front matter.md)

Consider the exponential function with base 2 defined by ![f(x) = 2^x](./images/50991cf3d8946e7921d08d7b2143f25f133a2b59.png). This function is crucial to computer systems. For instance, RAM memory chips come in powers of two because the memory space is exponential in the number of “address lines” used on the chip. When ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png), ![f(1)=2^1=2](./images/f8833ce9a35e430dbfc606060c6cb7d4d7d0da36.png). When ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is 2 we have ![f(2)=2^2=4](./images/a9895e6a05635592ffe8e84ee1e761563d91727c.png). The function is therefore described by the following input-output pairs: ![(0,1)](./images/51dc53e490143c62313d23af4c20f5a4e63d4d20.png), ![(1,2)](./images/f733efd97e74ebe8ad97f86e8f959bb6de9fa2a8.png), ![(2,4)](./images/9b1040b6ec7a73f8a1a34cd602344458a427853a.png), ![(3,8)](./images/ec1c5021b6dbf2807a31ec0f4b56e36981179126.png), ![(4,16)](./images/9d5d8514bb7be1eea6abbb173db18152c0a73706.png), ![(5,32)](./images/f4f3659f596800742087da1e020ab5a5c3467dfe.png), ![(6,64)](./images/213b64cd8649cec803f81e9a170e24f351dbf87e.png), ![(7,128)](./images/f015cd2f559d160ce1c881b07d1aeeffda549c8c.png), ![(8,256)](./images/e71e08eaa1e71038a1f1680dec233197d598308d.png), ![(9,512)](./images/694c521205fc0b46d5527f9b603812587ec08868.png), ![(10,1024)](./images/eeff6fc01e31bcd641d8d123b8f6de0f6db615b7.png), ![(11, 2048)](./images/15640ed9282e522ebe7cdcf643cc00a2a11bbcf2.png), ![(12,4096)](./images/f684358b285f55c2d724b865a612ae0bb8c3f85d.png), etc. Recall that any number raised to exponent ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) gives ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png). Thus, the exponential function passes through the point ![(0,1)](./images/51dc53e490143c62313d23af4c20f5a4e63d4d20.png). Recall also that negative exponents lead to fractions, so we have the points ![(-1,\frac{1}{2})](./images/d580756841841f63970d8152de87a48f3020372f.png), ![(-2,\frac{1}{4})](./images/2de84b60e6e33b34c926b054d3fbb1613e72dfbb.png), ![(-3,\frac{1}{8})](./images/203260adbbdec514e6b70b8f88fad959720980aa.png), etc. You can plot these ![(x, f(x))](./images/ce58134a57443a546d1fccbafa99c55bc06f1e8b.png) coordinates in the Cartesian plane to obtain the graph of the function.

###[Discussion](./Front matter.md)

To describe a function we specify its source and target sets ![f \colon A \to B](./images/9d31d7f95f2bc45c29422ad60397cf3ee4d76faa.png), then give an equation of the form ![f(x) = \textrm{``expression involving } x \textrm{''}](./images/a626765f6bc9d1b949956831f358ae2927c0ad04.png) that defines the function. Since functions are defined using equations, does this mean that functions and equations are the same thing? Let’s take a closer look.

In general, any equation containing two variables describes a _relation_ between these variables. For example, the equation ![x-3 = y-4](./images/676a943ca861984fbca902579ee5b0a80fa61b88.png) describes a relation between the variables ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png). We can isolate the variable ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in this equation to obtain ![y = x + 1](./images/7ed5ca6ac587326ea79c407a34662fa391839541.png) and thus find the value of ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) when the value of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is given. We can also isolate ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) to obtain ![x = y-1](./images/17bcff950057b3397ff42923c3e90c8839c7bca2.png) and use this equation to find ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) when the value of ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) is given. In the context of an equation, the relationship between the variables ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) is symmetrical and no special significance is attached to either of the two variables.

We also can describe the same relationship between ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) as a function ![f: \mathbb{R} \to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png). We choose to identify ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) as the input variable and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) as the output variable of the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png). Having identified ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) with the output variable, we can interpret the equation ![y = x + 1](./images/7ed5ca6ac587326ea79c407a34662fa391839541.png) as the definition of the function ![f(x) = x + 1](./images/b7a1ceee742e113d4f02d5f1119e759e824c6f8e.png).

Note that the equation ![x-3 = y-4](./images/676a943ca861984fbca902579ee5b0a80fa61b88.png) and the function ![f(x) = x + 1](./images/b7a1ceee742e113d4f02d5f1119e759e824c6f8e.png) describe the same relationship between the variables ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png). For example, if we set the value ![x = 5](./images/d9641318ca68f3505bcda367bf4e9442b9c94fba.png) we can find the value of ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) by solving the equation ![5-3 = y-4](./images/0b4985fd833733697cb029e3de5892dc013c5c6f.png) to obtain ![y = 6](./images/ad0aa3a3e977a4867f8932add1ff5ba2b01c3037.png), or by computing the output of the function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) for the input ![x=5](./images/d9641318ca68f3505bcda367bf4e9442b9c94fba.png), which gives us the same answer ![f(5)=6](./images/971cd778d976b6ae8243178d19d64178a7853441.png). In both cases we arrive at the same answer, but modelling the relationship between ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) as a function allows us to use the whole functions toolbox, like function composition and function inverses.

In this section we talked a lot about functions in general but we haven’t said much about any function specifically. There are many useful functions out there, and we can’t discuss them all here. In the next section, we’ll introduce ![10](./images/fd39ea446d2046417cbd0fc131073609dd557e3d.png) functions of strategic importance for all of science. If you get a grip on these functions, you’ll be able to understand all of physics and calculus and handle _any_ problem your teacher may throw at you.

##[1.9 Functions reference](./Chapter 1_ Math fundamentals.md)

Your _function vocabulary_ determines how well you can express yourself mathematically in the same way your English vocabulary determines how well you can express yourself in English. The following pages aim to embiggen your function vocabulary, so you’ll know how to handle the situation when a teacher tries to pull some trick on you at the final.

If you’re seeing these functions for the first time, don’t worry about remembering all the facts and properties on the first reading. We’ll use these functions throughout the rest of the book, so you’ll have plenty of time to become familiar with them. Remember to return to this section if you ever get stuck on a function.

To build mathematical intuition, it’s essential you understand functions’ graphs. Memorizing the definitions and properties of functions gets a lot easier with visual accompaniment. Indeed, remembering what the function “looks like” is a great way to train yourself to recognize various types of functions.[Figure 1.21](./Chapter 1_ Math fundamentals.md) shows the graphs of some of the most important functions we’ll use in this book.

![3x3_functions_miniplots](./images/3x3_functions_miniplots.png)

Figure 1.21: We’ll see many types of function graphs in the next pages.

###[Line](./Front matter.md)

The equation of a line describes an input-output relationship where the change in the output is _proportional_ to the change in the input. The equation of a line is

![f(x) = mx+b.](./images/dfec3cad2f6dd0af8e8d0bc68410343dbf69baf1.png)

The constant ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) describes the slope of the line. The constant ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) is called the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-intercept and it is the value of the function when ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png).

Consider what relationship the equation of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) describes for different values of ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png). What happens when ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) is positive? What happens when ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) is negative?

####[Graph](./Front matter.md)

![graph_of_2x_plus_3](./images/graph_of_2x_plus_3.png)

Figure 1.22: The graph of the function ![f(x)=2x-3](./images/018409ec8df3d06b5276e79e46c250a198b58218.png). The slope is ![m=2](./images/1e3403653af8fe9f7ce8286eed82811819bdd0d4.png). The ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png)\-intercept of this line is ![b=-3](./images/340f9c2ffaf5b089f078bf2bb9338d5034939453.png). The ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-intercept is at ![x=\frac{3}{2}](./images/9303ffa73ebf82c6a3660cefd3c3790aa97cbdf3.png).

####[Properties](./Front matter.md)

-   Domain: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). The function ![f(x)=mx+b](./images/34d27cda30de32cc4290f9d5b7b7f1facdbefb8e.png) is defined for all reals.
-   Image: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) if ![m\neq 0](./images/be23e3c9df19ba625ac47e8d865a3a6e08c9a5f4.png). If ![m=0](./images/322b77051593ce29d4613ff7de4fc3caeaa9e458.png) the function is constant ![f(x)=b](./images/2a861eb958347b4a8233c47a8b9223c21095ea76.png), so the image set contains only a single number ![\{ b\}](./images/e3c0f9cb748a14e3ad7b9bb60b118f1133618467.png).
-   ![x=-b/m](./images/47a8c6cd1199ddeefa6a0d1102a4de49b309c26c.png): the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-intercept of ![f(x)=mx+b](./images/34d27cda30de32cc4290f9d5b7b7f1facdbefb8e.png). The ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-intercept is obtained by solving ![f(x)=0](./images/7a99a37639d203a4fd8ea7290e75d7d95997c0c7.png).
-   The inverse to the line ![f(x)=mx+b](./images/34d27cda30de32cc4290f9d5b7b7f1facdbefb8e.png) is ![f^{-1}(x)=\frac{1}{m}(x-b)](./images/7ea67ce7f3c9fd9b4a7041ce6794819b7c73bbf6.png), which is also a line.

####[General equation](./Front matter.md)

A line can also be described in a more symmetric form as a relation:

![Ax + By = C.](./images/72fa640665d5fbdfe87da3dbf300e1dee4eeaff7.png)

This is known as the _general_ equation of a line. The general equation for the line shown in[Figure 1.22](./Chapter 1_ Math fundamentals.md) is ![2x-1y=3](./images/7fe8a4c0b9d4400f10fe8c0081b6840585ebf78b.png).

Given the general equation of a line ![Ax + By = C](./images/45c77cf07a1fed940869cab3e7695414c7431358.png) with ![B\neq 0](./images/7f0a3d93f8ddf8548cb5f688e5f6edcd1c0bcc7d.png), you can convert to the function form ![y=f(x)=mx+b](./images/d8cf5080f5e5e6492b2ef723e5c4cb558ec9d537.png) by computing the slope ![m=\frac{-A}{B}](./images/9516d8f8868f35da48e07d7fe6ea67a4bb12e7ba.png) and the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-intercept ![b=\frac{C}{B}](./images/777fdcf0715f7556e79f7f2c56d2007373df985a.png).

###[Square](./Front matter.md)

The function ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) _squared_, is also called the _quadratic_ function, or _parabola_. The formula for the quadratic function is

![f(x)=x^2.](./images/2da7c295641740e05d42bd1c0134c2d75b2f4fb5.png)

The name “quadratic” comes from the Latin _quadratus_ for square, since the expression for the area of a square with side length ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png).

![quadratic_func](./images/quadratic_func.png)

Figure 1.23: Plot of the quadratic function ![f(x)=x^2](./images/6be7c05bf214c3bbc82b53bfb18dcfd9b1ffece6.png). The graph of the function passes through the following ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png) coordinates: ![(-2,4)](./images/dce0b4adf1a76d0bb605974f6ce5ef88962f44b6.png), ![(-1,1)](./images/dfd4b5827bd43dc20cc705adbfcb62254f061fc5.png), ![(0,0)](./images/88f092814c075b14ae3942f62ed4da42f8321ec0.png), ![(1,1)](./images/2ea5ec79a8e31eeca324b4dd0e638f58cc29173d.png), ![(2,4)](./images/354718cf1435335f9236c62bfcc18b32a276d493.png), ![(3,9)](./images/f0efa4e0cc8c31c1dbb5a8cfc89a5608fb45c359.png), etc.

####[Properties](./Front matter.md)

-   Domain: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). The function ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) is defined for all numbers.
-   Image: ![\mathbb{R}_+ = \{y \in \mathbb{R} \; | \; y \geq 0 \}](./images/f152661f0b402b694c685b5546be6504200c2f6d.png). The outputs are nonnegative numbers since ![x^2 \geq 0](./images/28687ac556857bfe3e605258b28cc25ecb3c6f8d.png), for all real numbers ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).
-   The function ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) is the inverse of the square root function ![\sqrt{x}](./images/feb1aa654c5a0153a8a477c91f43fb87e105d2ce.png).
-   ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) is _two-to-one_: it sends both ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![-x](./images/665de79093233e3f251ecb3a98ec9fb472a7dbd8.png) to the same output value ![x^2=(-x)^2](./images/1eee7cd2844a9df06769bb3c3482a0dfc4df92bb.png).
-   The quadratic function is _convex_, meaning it curves upward.

The set expression ![\{y \in \mathbb{R} \; | \; y \geq 0 \}](./images/cc56f97acf0a83a5e4a5b04ec4c905c649dfaf08.png) that we use to define the nonnegative real numbers (![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png)) is read “the set of real numbers that are greater than or equal to zero.”

###[Square root](./Front matter.md)

The square root function is denoted

![f(x) = \sqrt{x} = x^{\frac{1}{2}} .](./images/965e9145a4dc4e39f712fefd39a2d1b245eb8168.png)

The square root ![\sqrt{x}](./images/feb1aa654c5a0153a8a477c91f43fb87e105d2ce.png) is the inverse function of the square function ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) when the two functions are defined as ![f : \mathbb{R}_+ \to \mathbb{R}_+](./images/bf0cfa0362e4d117d53377630db522b067b01e48.png). The symbol ![\sqrt{c}](./images/e385df4fc333344625a17193859ba82c465bfe93.png) refers to the _positive_ solution of ![x^2=c](./images/a944f657af0162a74ba42176618898d1c76f20df.png). Note that ![-\sqrt{c}](./images/6c3770458255bf887108896051cdae4b6cf61e46.png) is also a solution of ![x^2=c](./images/a944f657af0162a74ba42176618898d1c76f20df.png).

####[Graph](./Front matter.md)

![sqrt_of_x](./images/sqrt_of_x.png)

Figure 1.24: The graph of the function ![f(x)=\sqrt{x}](./images/ac69a8bd2fae60c518a4a37ccda55aa47bfe43e8.png). The domain of the function is ![\mathbb{R}_+](./images/2a5bafe4716a7945e6b76d693de91269a941aa9a.png) because we can’t take the square root of a negative number.

####[Properties](./Front matter.md)

-   Domain: ![\mathbb{R}_+ = \{x \in \mathbb{R} \; | \; x \geq 0 \}](./images/819c53df1aa3df4a4895e825dcb97c2069c2d3dc.png). The function ![f(x)=\sqrt{x}](./images/bc20cca97740e11e58a05c4912bea200fcff083d.png) is only defined for nonnegative inputs. There is no real number ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) such that ![y^2](./images/06e660e934616faae0cfbbeba9c671071ceea99f.png) is negative, hence the function ![f(x)=\sqrt{x}](./images/bc20cca97740e11e58a05c4912bea200fcff083d.png) is not defined for negative inputs ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png).
-   Image: ![\mathbb{R}_+ = \{y \in \mathbb{R} \; | \; y \geq 0 \}](./images/f152661f0b402b694c685b5546be6504200c2f6d.png). The outputs of the function ![f(x)=\sqrt{x}](./images/bc20cca97740e11e58a05c4912bea200fcff083d.png) are nonnegative numbers since ![\sqrt{x} \geq 0](./images/130c07536d7092dcf89c1091a967c4f9593c4831.png).

In addition to _square_ root, there is also _cube_ root ![f(x) = \sqrt[3]{x}  = x^{\frac{1}{3}}](../Images/845442ae1e1277c5e37205fa88ccffb7c0798d98.png), which is the inverse function for the cubic function ![f(x)=x^3](./images/93a7014078c09731603e500dd212378e2f714d3d.png). We have ![\sqrt[3]{8}=2](../Images/d1dfc4711eed70da4902e6b7546430f9cae87e93.png) since ![2\times2\times2=8](./images/a2f2bc1f6af8892877de3009069c17b5e67da131.png). More generally, we can define the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)th\-root function ![\sqrt[n]{x}](../Images/f11caa47e7745cc7aa10ecd3cea7286d0e68a11e.png) as the inverse function of ![x^n](./images/ac040deff83e3e689456a91a060b81b94f94841f.png).

###[Absolute value](./Front matter.md)

The _absolute value_ function tells us the size of numbers without paying attention to whether the number is positive or negative. We can compute a number’s absolute value by _ignoring the sign_ of the number. A number’s absolute value corresponds to its distance from the origin of the number line.

Another way of thinking about the absolute value function is to say it multiplies negative numbers by ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png) to “cancel” their negative sign:

![f(x)=|x|=  \left\{  \begin{array}{rl}  x &\text{ if } x\geq 0, \\  -x &\text{ if } x<0. \end{array} \right.](./images/bc5b4172403da4a558a55f81b3a35644b9a55adf.png)

####[Graph](./Front matter.md)

![absolute_value_of_x](./images/absolute_value_of_x.png)

Figure 1.25: The graph of the absolute value function ![f(x)=|x|](./images/52adf6c8dd2827684be213490cfc1c89d4823178.png).

####[Properties](./Front matter.md)

-   Domain: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). The function ![f(x)=|x|](./images/0ab625374a5346f7c88b6eaaa6685a0d713a0c15.png) is defined for all inputs.
-   Image: ![\mathbb{R}_+ = \{y \in \mathbb{R} \; | \; y \geq 0 \}](./images/f152661f0b402b694c685b5546be6504200c2f6d.png)
-   The combination of squaring followed by square-root is equivalent to the absolute value function:
    
    ![\sqrt{ x^2 }  = |x|,](./images/33d15014a7952b6bc0ba48a0a59399501d658181.png)
    
    since squaring destroys the sign.
    

###[Polynomials](./Front matter.md)

The polynomials are a very useful family of functions. For example, quadratic polynomials of the form ![f(x) = ax^2 + bx +c](./images/7b4e833ccdeb0b66165c7a185dc8474b599dd740.png) often arise when describing physics phenomena.

The general equation for a polynomial function of degree ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is

![f(x)=a_0 + a_1x + a_2x^2 + a_3x^3 + \cdots + a_nx^n.](./images/84cffafd386b49d6087b437ffd5d682060880d04.png)

The constants ![a_i](./images/742468daa9df98467c8672fd641aa4d150e2d2ed.png) are known as the _coefficients_ of the polynomial.

####[Parameters](./Front matter.md)

-   ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png): the variable
-   ![a_0](./images/e5f45f608555f355964666e0369b21e1a495aa85.png): the constant term
-   ![a_1](./images/687e2b6e809c59ef21e9cab2e018a3b291d0bd3e.png): the _linear_ coefficient, or _first-order_ coefficient
-   ![a_2](./images/15e6e46159abbf02dbc681c4e96a0803670acafc.png): the _quadratic_ coefficient
-   ![a_3](./images/2f35f026afd31384bb62a7e3e27f7e142fef5528.png): the _cubic_ coefficient
-   ![a_n](./images/1506cdb80ad5652d9a410c8547f1a72cbd19ce34.png): the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)th order coefficient
-   ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png): the _degree_ of the polynomial. The degree of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) is the largest power of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that appears in the polynomial.

A polynomial of degree ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) has ![n+1](./images/59ddb5062033134e6e2c571f6fdcf91ff1b80567.png) coefficients: ![a_0,a_1,a_2,\ldots, a_n](./images/5d47fdd46ef9539b7cb326a004ff2f667cbbb154.png).

####[Properties](./Front matter.md)

-   Domain: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). Polynomials are defined for all inputs.
-   The roots of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) are the values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) for which ![f(x)=0](./images/7a99a37639d203a4fd8ea7290e75d7d95997c0c7.png).
-   The image of a polynomial function depends on the coefficients.
-   The sum of two polynomials is also a polynomial.

The most general first-degree polynomial is a line ![f(x) = mx + b](./images/34d27cda30de32cc4290f9d5b7b7f1facdbefb8e.png), where ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) are arbitrary constants. The most general second-degree polynomial is ![f(x) = a_2 x^2 + a_1 x + a_0](./images/7a55ac0ee8808c6bb16ec48d76433be4bc9b2472.png), where again ![a_0](./images/e5f45f608555f355964666e0369b21e1a495aa85.png), ![a_1](./images/687e2b6e809c59ef21e9cab2e018a3b291d0bd3e.png), and ![a_2](./images/15e6e46159abbf02dbc681c4e96a0803670acafc.png) are arbitrary constants. We call ![a_k](./images/f9edff0d0e43ac0129579bc7ab8b6dbad3ee277c.png) the _coefficient_ of ![x^k](./images/75b026066799b69aa8fa40bb828bbd3704f4b2c2.png), since this is the number that appears in front of ![x^k](./images/75b026066799b69aa8fa40bb828bbd3704f4b2c2.png). Following the pattern, a third-degree polynomial will look like ![f(x) = a_3 x^3 + a_2 x^2 + a_1 x + a_0](./images/bca2c4d8251f798e68d4f16b4e862e84b4e83e95.png).

In general, a polynomial of degree ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) has the equation

![f(x) = a_n x^n + a_{n-1}x^{n-1} + \cdots + a_2 x^2 + a_1 x + a_0.](./images/2c8adc6c09acae643fbf354b5cfcdae97c8af611.png)

You can add two polynomials by adding together their coefficients:

![\begin{align*}
f(x) + g(x)
&=	(a_n x^n + \cdots + a_1 x + a_0)
\; + \; 
(b_n x^n + \cdots + b_1 x + b_0)\\
&=	(a_n+b_n) x^n + \cdots + (a_1+b_1) x + (a_0+b_0).
\end{align*}](./images/826cde20ae9f57c95f3952735c4da73a0c04dbc9.png)

The subtraction of two polynomials works similarly. We can also multiply polynomials together using the general algebra rules for expanding brackets.

### Solving polynomial equations

Very often in math, you will have to _solve_ polynomial equations of the form

![A(x) = B(x),](./images/6139c84ad505cdf362510ab78259f82dca8868aa.png)

where ![A(x)](./images/3d31c2eebbc56e94daa63d03213f25d65afe2979.png) and ![B(x)](./images/2b2c80a3b69a09772a4d4bc13f1bb0f9c054034d.png) are both polynomials. Recall from earlier that to _solve_, we must find the values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that make the equality true.

Say the revenue of your company is a function of the number of products sold ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), and can be expressed as ![R(x)=2x^2 + 2x](./images/d4387c3c793634e3bed4564668430e6dee8ff421.png). Say also the cost you incur to produce ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) objects is ![C(x)=x^2+5x+10](./images/06feafbf1335dda2e62f5cad606f8629e6683a8d.png). You want to determine the amount of product you need to produce to break even, that is, so that revenue equals cost: ![R(x)=C(x)](./images/3497f012d93f8f5a86cfc6a804cdbece4a456bdb.png). To find the break-even value ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), solve the equation

![2x^2 + 2x = x^2+5x+10.](./images/031f3b771996e1c3d5fd84aecf5640b3ef8d6262.png)

This may seem complicated since there are ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)s all over the place. No worries! We can turn the equation into its “standard form,” and then use the quadratic formula. First, move all the terms to one side until only zero remains on the other side:

![\begin{align*}
2x^2 + 2x \; \; \; -x^2  	&= \cancel{x^2}+5x+10  \; \; \;  - \cancel{x^2} 	\\
x^2 + 2x \; \; \; -5x   	&= \cancel{5x}+10  \; \; \; -\cancel{5x}	\\
x^2 - 3x \; \; \; -10   	&= \cancel{10}  \; \; \; -\cancel{10}		\\
x^2 - 3x -10         	&= 0.		
\end{align*}](./images/e36aa05b177c8eea99fff8e068d5d5021cdc2e1a.png)

Remember, if we perform the same operations on both sides of the equation, the resulting equation has the same solutions. Therefore, the values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that satisfy ![x^2 - 3x -10  = 0](./images/0536d1a9dffbdf53793d297b0e8b353ff343628c.png), namely ![x=-2](./images/5b422a9c8a6c0d82762433062ff9f9b6846f0c90.png) and ![x=5](./images/d9641318ca68f3505bcda367bf4e9442b9c94fba.png), also satisfy ![2x^2 + 2x = x^2+5x+10](./images/43c44ea2bd3004d6e58589a479c4f3ad18b4cb8c.png), which is the original problem we’re trying to solve.

This “shuffling of terms” approach will work for any polynomial equation ![A(x)=B(x)](./images/8f0c878f7eea2fc763ac84070460ee42ce5587e8.png). We can always rewrite it as ![C(x)=0](./images/7b852c0c89d8ee257245d2ea29b7436114040112.png), where ![C(x)](./images/a795301d959880bd31da0018b465cc2450cd8584.png) is a new polynomial with coefficients equal to the difference of the coefficients of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). Don’t worry about which side you move all the coefficients to because ![C(x)=0](./images/7b852c0c89d8ee257245d2ea29b7436114040112.png) and ![0=-C(x)](./images/58af8a9159fcca24802468eb750e2a4064a31974.png) have exactly the same solutions. Furthermore, the degree of the polynomial ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png) can be no greater than that of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) or ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

The form ![C(x)=0](./images/7b852c0c89d8ee257245d2ea29b7436114040112.png) is the _standard form_ of a polynomial, and we’ll explore several formulas you can use to find its solution(s).

####[Formulas](./Front matter.md)

The formula for solving the polynomial equation ![P(x)=0](./images/05f2d4d0b3425d7b71735015356ddf4cb1490de5.png) depends on the _degree_ of the polynomial in question.

For a first-degree polynomial equation, ![P_1(x) = mx + b = 0](./images/402ece60cf4b014f3c03b9d26b705b1d4ee83c7b.png), the solution is ![x=\frac{-b}{m}](./images/80c13ff89b253ec0b0fd7cfdf549ac89929504bd.png): just move ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) to the other side and divide by ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png).

For a second-degree polynomial,

![P_2(x) = ax^2 + bx + c = 0,](./images/afc91e65514a13dd692bd5a18bd203d751cc4d85.png)

the solutions are ![x_1=\frac{-b + \sqrt{ b^2 -4ac}}{2a}](./images/cdee20d8eadb8af0776df3fc4e674af89332f536.png) and ![x_2=\frac{-b - \sqrt{b^2-4ac}}{2a}](./images/004f60cbde0abbc32458a67068b01f574a238e7f.png).

If ![b^2-4ac < 0](./images/9703a2a71b94d359d5f5d83763d7c97871f22406.png), the solutions will involve taking the square root of a negative number. In those cases, we say no real solutions exist.

There is also a formula for polynomials of degree ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) and ![4](./images/d642a42f2cf4e1514233d611b91e5d4646202fc8.png), but they are complicated. For polynomials with order ![\geq 5](./images/20072671b026b6280e7602761b2d97948b40db78.png), there does not exist a general analytical solution.

####[Using a computer](./Front matter.md)

When solving real-world problems, you’ll often run into much more complicated equations. To find the solutions of anything more complicated than the quadratic equation, I recommend using a computer algebra system like `SymPy`: [http://live.sympy.org](./live.sympy.org.md)`.

To make `SymPy` solve the standard-form equation ![C(x)=0](./images/7b852c0c89d8ee257245d2ea29b7436114040112.png), call the function `solve(expr,var)`, where the expression `expr` corresponds to ![C(x)](./images/a795301d959880bd31da0018b465cc2450cd8584.png), and `var` is the variable you want to solve for. For example, to solve ![x^2-3x+2=0](./images/6f36f00cd53d7cf15a9ac228247b1f4c5c798859.png), type in the following:

 >>> solve(x\*\*2 - 3\*x + 2, x)          # usage: solve(expr, var)
 \[1, 2\]		

The function `solve` will find the solutions to any equation of the form `expr = 0`. In this case, we see the solutions are ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png) and ![x=2](./images/e5434555c15a07cfe09b5b352b1965c74365967d.png).

Another way to solve the equation is to factor the polynomial ![C(x)](./images/a795301d959880bd31da0018b465cc2450cd8584.png) using the function `factor` like this:

 >>> factor(x\*\*2 - 3\*x + 2)            # usage: factor(expr)
 (x - 1)\*(x - 2)	

We see that ![x^2-3x+2 = (x-1)(x-2)](./images/85ea225283d5d1dea889c0ff27f64e26d92ca6a9.png), which confirms the two roots are indeed ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png) and ![x=2](./images/e5434555c15a07cfe09b5b352b1965c74365967d.png).

####[Substitution trick](./Front matter.md)

Sometimes you can solve fourth-degree polynomials by using the quadratic formula. Say you’re asked to solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in

![x^4 - 7x^2 + 10  = 0.](./images/38a010067c1d3951eea12d388a9b473643d0720e.png)

Imagine this problem is on your exam, where you are not allowed to use a computer. How does the teacher expect you to solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)? The trick is to substitute ![y=x^2](./images/830f89201891605011673c09292abc520547457f.png) and rewrite the same equation as

![y^2 - 7y + 10  = 0,](./images/d468838e33851f0905bb347bc503dd3d394b948f.png)

which you can solve by applying the quadratic formula. If you obtain the solutions ![y=\alpha](./images/c03546e115b140ddd13480bb0de4b51b1fc82453.png) and ![y=\beta](./images/3652cd034a7ba746fb5ffefd800ef8dddc500e19.png), then the solutions to the original fourth-degree polynomial are ![x=\pm\sqrt{\alpha}](./images/6c05af22675f1460c590017b549ebe44d3562091.png) and ![x=\pm\sqrt{\beta}](./images/c4a907182d7e2979d278ec6525abe8be87fae223.png), since ![y=x^2](./images/830f89201891605011673c09292abc520547457f.png).

Since we’re not taking an exam right now, we are allowed to use the computer to find the roots:

 >>> solve(y\*\*2 - 7\*y + 10, y)
 \[2, 5\]
 >>> solve(x\*\*4 - 7\*x\*\*2 + 10, x)
 \[sqrt(2), -sqrt(2), sqrt(5), -sqrt(5)\]

Note how the second-degree polynomial has two roots, while the fourth-degree polynomial has four roots.

####[Even and odd functions](./Front matter.md)

The polynomials form an entire family of functions. Depending on the choice of degree ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) and coefficients ![a_0](./images/e5f45f608555f355964666e0369b21e1a495aa85.png), ![a_1](./images/687e2b6e809c59ef21e9cab2e018a3b291d0bd3e.png), ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png), ![a_n](./images/1506cdb80ad5652d9a410c8547f1a72cbd19ce34.png), a polynomial function can take on many different shapes. Consider the following observations about the symmetries of polynomials:

-   If a polynomial contains only even powers of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), like ![f(x)=1+x^2-x^4](./images/8b9965b45ac9373926566d8e144d52c1eb537084.png) for example, we call this polynomial _even_. Even polynomials have the property ![f(x)=f(-x)](./images/718aae08f1d3a23d3846884c4026ab3560423850.png). The sign of the input doesn’t matter.
-   If a polynomial contains only odd powers of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), for example ![g(x)=x+x^3-x^9](./images/a522b26fadfde69d9ca8685b944816965aefcc1b.png), we call this polynomial _odd_. Odd polynomials have the property ![g(x)=-g(-x)](./images/a160b819378f90ef90a23c40599f1ef2f0542abd.png).
-   If a polynomial has both even and odd terms then it is neither even nor odd.

The terminology of _odd_ and _even_ applies to functions in general and not just to polynomials. All functions that satisfy ![f(x)=f(-x)](./images/718aae08f1d3a23d3846884c4026ab3560423850.png) are called _even functions_, and all functions that satisfy ![f(x)=-f(-x)](./images/05746c176350e076b7e4ecd70c16a62f42a075f5.png) are called _odd functions_.

###[Sine](./Front matter.md)

The sine function represents a fundamental unit of vibration. The graph of ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) _oscillates_ up and down and crosses the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis multiple times. The shape of the graph of ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) corresponds to the shape of a vibrating string. See[Figure 1.26](./Chapter 1_ Math fundamentals.md).

In the remainder of this book, we’ll meet the function ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) many times. We’ll define the function ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) more formally as a trigonometric ratio in[](./Chapter 1_ Math fundamentals.md)[Section 1.11](./Chapter 1_ Math fundamentals.md). In[Section 1.13](./Chapter 1_ Math fundamentals.md) we’ll use ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) and ![\cos(x)](./images/42eba01bdd88eaeb543a741e31931fb1bcc1f295.png) (another trigonometric ratio) to work out the _components_ of vectors.

At this point in the book, however, we don’t want to go into too much detail about all these applications. Let’s hold off on the discussion about vectors, triangles, angles, and ratios of lengths of sides and instead just focus on the graph of the function ![f(x) = \sin(x)](./images/4183d62596f5df749b6f26da9812b76fb865365f.png).

####[Graph](./Front matter.md)

![sin_of_x](./images/sin_of_x.png)

Figure 1.26: The graph of the function ![y=\sin(x)](./images/4d216f3b958505b2d7c1f87ff213aef986284ca8.png) passes through the following ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png) coordinates: ![(0,0)](./images/88f092814c075b14ae3942f62ed4da42f8321ec0.png), ![(\frac{\pi}{6},\frac{1}{2})](./images/e83266bdce92854abe6f1f6948ecd12b6df7c8ad.png), ![(\frac{\pi}{4},\frac{\sqrt{2}}{2})](./images/91110dc4ab1e0745b837ef4723e34de0079e6c3d.png), ![(\frac{\pi}{3},\frac{\sqrt{3}}{2})](./images/281016ce484f3e4bfbf7bbadb24ef5a24652d17c.png), ![(\frac{\pi}{2},1)](./images/ab9ecb7062cf1c61ae7447b29fde3ae305d79ebc.png), ![(\frac{2\pi}{3},\frac{\sqrt{3}}{2})](./images/b0c3a5746de5e33a8175eaf0d50cf06732a5e97b.png), ![(\frac{3\pi}{4},\frac{\sqrt{2}}{2})](./images/8fe1f0d1054322926beab7dbd4a16c8ffcdfed93.png), ![(\frac{5\pi}{6},\frac{1}{2})](./images/3000de4fdfc25b83d8ae947cbb7043b0ae627bd5.png), and ![(\pi,0)](./images/5d277ed6975b66b77352340672e2f9beed830ea0.png). For ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) between ![\pi](./images/b62e24766fc6854b97c3c7fd6bc08b58daf064cc.png) and ![2\pi](./images/8a22179df7683e15968bcee7cd0eefbd44628c4c.png), the function’s graph has the same shape it has for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) between ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png) and ![\pi](./images/b62e24766fc6854b97c3c7fd6bc08b58daf064cc.png), but with negative values.

![the_numer_pi](./images/the_numer_pi.png)

Figure 1.27: The function ![f(x)=\sin(x)](./images/192eadfe475ce98c71dabfd0582260468e28bba5.png) crosses the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-axis at ![x=\pi](./images/4d7b505cd5d53805ec573b61674e12ee554617b1.png).

Let’s start at ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png) and follow the graph of the function ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) as it goes up and down. The graph starts from ![(0,0)](./images/4467446eac588743b0a225c1f23f0769d34ee1f5.png) and smoothly increases until it reaches the maximum value at ![x=\frac{\pi}{2}](./images/7d4465e3cf7f545ad0d54f546737f67689187a79.png). Afterward, the function comes back down to cross the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis at ![x=\pi](./images/8ec248aef4277195a352c377c2c9ddb01b071a59.png). After ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png), the function drops below the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis and reaches its minimum value of ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png) at ![x=\frac{3\pi}{2}](./images/624326776df3bf1d3ba41596996c3a7b3eecd6a3.png). It then travels up again to cross the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis at ![x=2\pi](./images/29ea489d229c3d5ec114577b099ac10d7947a26c.png). This ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png)\-long cycle repeats after ![x=2\pi](./images/29ea489d229c3d5ec114577b099ac10d7947a26c.png). This is why we call the function _periodic_—the shape of the graph repeats.

![sin_of_x_many_cycles](./images/sin_of_x_many_cycles.png)

Figure 1.28: The graph of ![\sin(x)](./images/45a2d7692173f54b7a5b793e7000d5f8ae16b245.png) from ![x=0](./images/aa78f6a194098d11a5239ec5d5ad4f0fbff21af8.png) to ![x=2\pi](./images/93ff05d03c3884c93ab5c1742517be81ef8e3e00.png) repeats periodically everywhere else on the number line.

####[Properties](./Front matter.md)

-   Domain: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). The function ![f(x)=\sin(x)](./images/4183d62596f5df749b6f26da9812b76fb865365f.png) is defined for all input values.
-   Image: ![\{ y \in \mathbb{R} \; | \;  -1 \leq y \leq 1 \}](./images/bd1c62938c948974edb039364ebe78644d183cdd.png). The outputs of the sine function are always between ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png) and ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png).
-   Roots: ![\{\,\ldots, -3\pi, -2\pi,-\pi,0,\pi,2\pi,3\pi, \ldots\,\}](./images/509a5419f9d885ed882c949ce1f70bae9f712baa.png). The function ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) has roots at all multiples of ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png).
-   The function is periodic, with period ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png): ![\sin(x) = \sin(x+2\pi)](./images/65911f6c1fd4aacc95b2852c92c814ac02013581.png).
-   The ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png) function is _odd_: ![\sin(x)=-\sin(-x)](./images/cd4d052672103ab19e5ec327ba59c18f1c5ab23e.png)
-   Relation to ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png): ![\sin^2 x + \cos^2 x = 1](./images/47ccbd45c5262b7a39e463c4599b609cab1df3f7.png)
-   Relation to ![\csc](./images/61af3e7fb46b95ddc13676e332f7e984269f7417.png): ![\csc(x) = \frac{1}{\sin x}](./images/f3d268f4cff4e952a0be7d99da7b1eaf2c6c273e.png) (![\csc](./images/61af3e7fb46b95ddc13676e332f7e984269f7417.png) is read _cosecant_)
-   The inverse function of ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) is denoted as ![\sin^{-1}(x)](./images/af0ad8f1530f51d51c9ebd50b06010cae3c9f9ac.png) or ![\arcsin(x)](./images/3cc22438fb97a2b4f7dd7bd7ee2e8d8afa837e93.png), not to be confused with ![(\sin(x))^{-1}=\frac{1}{\sin(x)} = \csc(x)](./images/9dda71ff798b0798cbe2edeab222233bef0b50bf.png).
-   The number ![\sin(\theta)](./images/824871e39122c39630d6ad0cd62509c541a95c14.png) is the length-ratio of the vertical side and the hypotenuse in a right-angle triangle with angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) at the base.

####[Links](./Front matter.md)

\[ See the Wikipedia page for nice illustrations \]

[`http://en.wikipedia.org/wiki/Sine`](./Sine.md)

###[Cosine](./Front matter.md)

The cosine function is the same as the sine function _shifted_ by ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png) to the left: ![\cos(x) = \sin(x+\frac{\pi}{2})](./images/0453faaadf337905c195118675b03e40e5ea5b5c.png). Thus everything you know about the sine function also applies to the cosine function.

####[Graph](./Front matter.md)

![cos_of_x](./images/cos_of_x.png)

Figure 1.29: The graph of the function ![y=\cos(x)](./images/c5c540114a8b6ac139a90b62640b2977aa6cfbe6.png) passes through the following ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png) coordinates: ![(0,1)](./images/e69b48bc6687ee74a843dea90543682e53e069e3.png), ![(\frac{\pi}{6},\frac{\sqrt{3}}{2})](./images/10881e0ad84db0e7f710c2289c8ed3e8f8a5bb43.png), ![(\frac{\pi}{4},\frac{\sqrt{2}}{2})](./images/91110dc4ab1e0745b837ef4723e34de0079e6c3d.png), ![(\frac{\pi}{3},\frac{1}{2})](./images/df6b661bb836148a1d3256198e6004de2d09526e.png), ![(\frac{\pi}{2},0)](./images/ec071e3f025ada409c0d8a07d4cbbcf867a43357.png), ![(\frac{2\pi}{3},-\frac{1}{2})](./images/c98d3b69f29ef6e9123168972d5dc42123dca5e2.png), ![(\frac{3\pi}{4}, -\frac{\sqrt{2}}{2})](./images/bf8105e251ea7fc180c35e32ae1d6a8073873fe7.png), ![(\frac{5\pi}{6}, -\frac{\sqrt{3}}{2})](./images/e700381b9b5d9646331bfde6fa33616e61e6410d.png), and ![(\pi,-1)](./images/9e8b4293aad697516f179a905400c2a42546f3f7.png).

The cos function starts at ![\cos(0)=1](./images/f5b3cdc84480abc9dc2dfc7e5baa8d207c69ca46.png), then drops down to cross the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis at ![x=\frac{\pi}{2}](./images/7d4465e3cf7f545ad0d54f546737f67689187a79.png). Cos continues until it reaches its minimum value at ![x=\pi](./images/8ec248aef4277195a352c377c2c9ddb01b071a59.png). The function then moves upward, crossing the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis again at ![x=\frac{3\pi}{2}](./images/624326776df3bf1d3ba41596996c3a7b3eecd6a3.png), and reaching its maximum value again at ![x=2\pi](./images/29ea489d229c3d5ec114577b099ac10d7947a26c.png).

####[Properties](./Front matter.md)

-   Domain: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png)
-   Image: ![\{ y \in \mathbb{R} \; | \;  -1 \leq y \leq 1 \}](./images/bd1c62938c948974edb039364ebe78644d183cdd.png)
-   Roots: ![\{\, \ldots, \, -\frac{3\pi}{2}, \, -\frac{\pi}{2}, \frac{\pi}{2}, \frac{3\pi}{2},  \frac{5\pi}{2}, \, \ldots\,\}](./images/1a0ddbcda41282655f1a633af39ae2884c601244.png)
-   Relation to ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png): ![\sin^2 x + \cos^2 x = 1](./images/47ccbd45c5262b7a39e463c4599b609cab1df3f7.png)
-   Relation to ![\sec](./images/76afc4e27dc20abfc98194cd1d27be8d973d1732.png): ![\sec(x) = \frac{1}{\cos x}](./images/c71cb35933cf6944b520bc076edd3f9e3213e810.png) (![\sec](./images/76afc4e27dc20abfc98194cd1d27be8d973d1732.png) is read _secant_)
-   The inverse function of ![\cos(x)](./images/42eba01bdd88eaeb543a741e31931fb1bcc1f295.png) is denoted ![\cos^{-1}(x)](./images/7ab458a0b32663975fe692af5cdd455280d7facc.png) or ![\arccos(x)](./images/080d41cf122a160773a028e035e8cbe80353e4b5.png).
-   The ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png) function is _even_: ![\cos(x) = \cos(-x)](./images/e8e692ff4501b6a0c6b26bdeb7d1e80f62a57409.png)
-   The number ![\cos(\theta)](./images/c839aa37ae418cebc997feae47acc5c5a2621571.png) is the length-ratio of the horizontal side and the hypotenuse in a right-angle triangle with angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) at the base

###[Tangent](./Front matter.md)

The tangent function is the ratio of the sine and cosine functions:

![f(x)=\tan(x)= \frac{ \sin(x) }{ \cos(x) }.](./images/2d02283863189f63fd93c1fde97f7419cf48f4f8.png)

####[Graph](./Front matter.md)

![tan_of_x](./images/tan_of_x.png)

Figure 1.30: The graph of the function ![f(x)=\tan(x)](./images/b1af0e9ecb1d1fe45571815a947007c1d0e46088.png).

####[Properties](./Front matter.md)

-   Domain: ![\{ x\in \mathbb{R} \;|\; x\neq \frac{(2n+1)\pi}{2} \textrm{ for any } n \in \mathbb{Z} \}](./images/6aed40ea40125807d9feff6b38eab26f94582a74.png)
-   Image: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png)
-   The function ![\tan](./images/23bcb493ab30c7e1982ecdfc718cb114739a236e.png) is periodic with period ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png).
-   The ![\tan](./images/23bcb493ab30c7e1982ecdfc718cb114739a236e.png) function “blows up” at values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) where ![\cos x=0](./images/559d9b82216586dd71a56fd6429111bdcd548873.png). These are called _asymptotes_ of the function and their locations are ![x=\ldots, \frac{-3\pi}{2},\frac{-\pi}{2},\frac{\pi}{2},\frac{3\pi}{2},\ldots](./images/bf52a5a8c65fbc8f6d04d68c78ba52cbbbe25a98.png).
-   Value at ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png): ![\tan(0)=\frac{0}{1}=0](./images/07808368d5b8051460a22eabc29861140eb0f73a.png), because ![\sin(0)=0](./images/1039454e3f7c1dc8621ca1214264b25931e6f4a0.png).
-   Value at ![x=\frac{\pi}{4}](./images/8fba5584b8394e1bc9494d408dee9804de5564dc.png): ![\tan\left(\frac{\pi}{4} \right) 
    = \frac{ \sin(\frac{\pi}{4}) }{ \cos(\frac{\pi}{4}) }
    = \frac{ \frac{\sqrt{2}}{2}  }{ \frac{\sqrt{2}}{2}  }
    = 1](./images/96b5d14a9cb121ac5adb8ab96d256537d03ae297.png).
-   The number ![\tan(\theta)](./images/e56f0f1b7ac206d3c8a8fcded8b8f3dbf8ec52fc.png) is the length-ratio of the vertical and the horizontal sides in a right-angle triangle with angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png).
-   The inverse function of ![\tan(x)](./images/e2e54e690a08842541d1a09bfaaeaf12b183da93.png) is denoted ![\tan^{-1}(x)](./images/be6c4ab3c8c9f848623ca3b6968bdf885f236b6c.png) or ![\arctan(x)](./images/4060a59c36601100322dee60d5342e9ce5cb62d1.png).
-   The inverse tangent function is used to compute the angle at the base in a right-angle triangle with horizontal side length ![\ell_h](./images/2868b08915320a7dd2a6be412b008a5e50909956.png) and vertical side length ![\ell_v](./images/42cd88cfe00f4e2154475854d21d1caaa7e3a9d6.png): ![\theta=\tan^{-1}\!\left(\frac{\ell_v}{\ell_h}\right)](./images/5200ada5242f84731a3e2dd3404588a36d41b414.png).

###[Exponential](./Front matter.md)

The exponential function base ![e=2.7182818\ldots](./images/fb4582d23931e533021afab31d50084c1972c8c0.png) is denoted

![f(x)=e^{x} = \exp(x).](./images/68df781508c6743a0ae06c0a491211cd544be6fa.png)

####[Graph](./Front matter.md)

![exp_x](./images/exp_x.png)

Figure 1.31: The graph of the exponential function ![f(x)=e^x](./images/016e4bba9b7fbc0c498c517a8bc2fbd6a0f2b94f.png) passes through the following points: ![(-2,\frac{1}{e^2})](./images/2e859a27a13f66d4c86fb593d95cf573e24507aa.png), ![(-1,\frac{1}{e})](./images/3f8dfb70d5e9ee3d3dcf8c4fe904f728d51b2e61.png), ![(0,1)](./images/e69b48bc6687ee74a843dea90543682e53e069e3.png), ![(1,e)](./images/f4d0e1b5252b57bab483cc364fdaaeb2bad62279.png), ![(2,e^2)](./images/7db7581fd79f625da150fd7f37996ec200206a24.png), ![(3,e^3)](./images/ae8c0950d37a5679c1e78977e4bf6e954615e95a.png), ![(4,e^4)](./images/dd8c03681e714b7cf7bae8488628c1e0128e0aa4.png), etc.

####[Properties](./Front matter.md)

-   Domain: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png)
-   Image: ![\{ y \in \mathbb{R} \; | \;  y > 0 \}](./images/e2dcc0322be2c5b26c0ff153acbca3c9fde25e2f.png)
-   ![f(a)f(b)=f(a+b)](./images/524a0e3f562df809d2b5cff9a9a497c32d67579e.png) since ![e^ae^b=e^{a+b}](./images/0abafa7181db7b0ce939f64ba5496affcb02764a.png)

A more general exponential function would be ![f(x)=Ae^{\gamma x}](./images/ec29f92d9c4f5c2059ceea17ba5d87f2d9c086c6.png), where ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is the initial value, and ![\gamma](./images/75d69c99b85555a7a707d37e166d67f0b0b33b25.png) (the Greek letter _gamma_) is the _rate_ of the exponential. For ![\gamma > 0](./images/28ace2ec6ef4e217de9d1eacb0d48676c311e368.png), the function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) is increasing, as in[Figure 1.31](./Chapter 1_ Math fundamentals.md). For ![\gamma < 0](./images/2ad80534cc9e64616bb9ab365ad17c9b81736dab.png), the function is decreasing and tends to zero for large values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). The case ![\gamma=0](./images/23420b1a348948c66a85f0ca5a93142860d5f272.png) is special since ![e^{0}=1](./images/8b5c1d6def122509bf2299cc78327efee1481a1f.png), so ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) is a constant of ![f(x)=A1^x=A](./images/3fcc8cba141ee6fde0c9b5fe830aa1fd7575357d.png).

####[Links](./Front matter.md)

[ The exponential function ![2^x](./f48039fdd12997d3d965a32c2cc14c98a9c2b002.png.md) evaluated \]

[`http://www.youtube.com/watch?v=e4MSN6IImpI`](./watch_v=e4MSN6IImpI.md)

###[Natural logarithm](./Front matter.md)

The natural logarithm function is denoted

![f(x)=\ln(x) = \log_e(x).](./images/01c0ddbda7ada9c9af9a9e500d03a9643c39a12e.png)

The function ![\ln(x)](./images/ac737e1e2f55643d55061ce3d81125603dfe30fd.png) is the inverse function of the exponential ![e^x](./images/4f0ced03d137197bad0d134b4967fb961efde701.png).

####[Graph](./Front matter.md)

![ln_of_x](./images/ln_of_x.png)

Figure 1.32: The graph of the function ![\ln(x)](./images/1d948625a0469bc07520393051228d62c38eafaf.png) passes through the following coordinates: ![(\frac{1}{e^2},-2)](./images/71d37cc4497188068e62c516a4f8e50d22510a51.png), ![(\frac{1}{e},-1)](./images/4dad00d2b62462ad298358721647ddd370e2b6b7.png), ![(1,0)](./images/17fa76d96a4d6efa1a8a1bab1ccb6699ef7b2e34.png), ![(e, 1)](./images/ce62ef87bb05b75252e453b387fbf1b349c5b0bf.png), ![(e^2, 2)](./images/bfed24e76606a8398f1b7a319e9b3a31ae5c682a.png), ![(e^3, 3)](./images/7b392eb7514ac95da5569132299653a23a27848b.png), ![(e^4, 4)](./images/328c698de5ff83e4ac87e871cb22085110ca30f5.png), etc.

####[Properties](./Front matter.md)

-   Domain: ![\{ x \in \mathbb{R} \; | \;  x > 0 \}](./images/832bdcda995978642ccb69bc4bfda9a51790fd77.png)
-   Image: ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png)

###[Exercises](./Front matter.md)

E1.10 Find the domain, the image, and the roots of ![f(x)=2\cos(x)](./images/c847e1f83fa814ae3f153f871de4f8992c7bafac.png).

E1.11 What are the degrees of the following polynomials? Are they even, odd, or neither?

**a)** ![p(x)=x^2-5x^4+1](./images/0d1dc983cad8a24e63519c3f1980dda4498d1e48.png) **b)** ![q(x)=x-x^3+x^5-x^7](./images/17a8a2dc310ad4750f4135563c330794d56a7bf9.png)

E1.12 Solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the following polynomial equations.

**a)** ![3x+x^2=x-15+2x^2](./images/4c3fc6f0d099c05cb4b3b1457320c81af86d6375.png) **b)** ![3x^2-4x-4+x^3=x^3+2x+2](./images/62b21803544bc90d49861f7652e7f96aefc79bcf.png)

##[1.10 Geometry](./Chapter 1_ Math fundamentals.md)

The word “geometry” comes from the Greek roots _geo_, which means “earth,” and _metron_, which means “measurement.” This name is linked to one of the early applications of geometry, which was to measure the total amount of land contained within a certain boundary region. Over the years, the study of geometry evolved to be more abstract. Instead of developing formulas for calculating the area of specific regions of land, mathematicians developed general area formulas that apply to _all_ regions that have a particular shape.

In this section we’ll present formulas for calculating the perimeters, areas, and volumes for various shapes (also called “figures’’) commonly encountered in the real world. For two-dimensional figures, the main quantities of interest are the figures’ areas and the figures’ perimeters (the length of the walk around the figure). For three-dimensional figures, the quantities of interest are the surface area (how much paint it would take to cover all sides of the figure), and volume (how much water it would take to fill a container of this shape). The formulas presented are by no means an exhaustive list of everything there is to know about geometry, but they represent a core set of facts that you want to add to your toolbox.

###[Triangles](./Front matter.md)

The area of a triangle is equal to ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png) times the length of its base times its height:

![A = \tfrac{1}{2} a h_a.](./images/54e2e2702cf3579cc3f99c1cbef751e1cde451ca.png)

Note that ![h_a](./images/bbd31396cf7a7a0427255ac580bd61ac0aece2a0.png) is the height of the triangle _relative to_ the side ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png).

![areas-triangle](./images/areas-triangle.png)

Figure 1.33: A triangle with side lengths ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png), ![b](./images/ae769ce22c6289af843e3e66bd3145003e72ccf6.png), and ![c](./images/0da715a1d62623ace880d9c3dde79450f829f124.png). The height of the triangle with respect to the side ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png) is denoted ![h_a](./images/5b692974f08aa0cc9510b2d8ef0df681e742b6ae.png).

The perimeter of a triangle is given by the sum of its side lengths:

![P = a + b + c.](./images/73b49f73e22170665953479539212552d728913b.png)

#####[Interior angles of a triangle rule](./Front matter.md)

The sum of the inner angles in any triangle is equal to ![180^\circ](./images/79177e21de4aca7ef1a1ea67a1e45a189a959c86.png). Consider a triangle with internal angles ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png), ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) and ![\gamma](./images/75d69c99b85555a7a707d37e166d67f0b0b33b25.png) as shown in[Figure 1.34](./Chapter 1_ Math fundamentals.md). We may not know the values of the individual angles ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png), ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png), and ![\gamma](./images/75d69c99b85555a7a707d37e166d67f0b0b33b25.png), but we know their sum is ![\alpha+\beta+\gamma=180^\circ](./images/e142b8f4b0c2df174a493954068c66c68cbb7185.png).

![triangle-sine-and-cosine-law](./images/triangle-sine-and-cosine-law.png)

Figure 1.34: A triangle with inner angles ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png), ![\beta](./images/bc326c959b80d3a24fcdf5fda29ab07ecaf549ba.png), and ![\gamma](./images/1de0711177fbe0b9b05028cb4d2dd5122b1b1ef1.png) and sides ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png), ![b](./images/ae769ce22c6289af843e3e66bd3145003e72ccf6.png), and ![c](./images/0da715a1d62623ace880d9c3dde79450f829f124.png).

#####[Sine rule](./Front matter.md)

The sine rule states the following equation is true:

![\frac{a}{\sin(\alpha)}=\frac{b}{\sin(\beta)}=\frac{c}{\sin(\gamma)},](./images/455730de2ac377250d7ecdece9a3c03353856099.png)

where ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) is the angle opposite to side ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) is the angle opposite to side ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and ![\gamma](./images/75d69c99b85555a7a707d37e166d67f0b0b33b25.png) is the angle opposite to side ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png), as shown in[Figure 1.34](./Chapter 1_ Math fundamentals.md).

#####[Cosine rule](./Front matter.md)

The cosine rules states the following equations are true:

![\begin{align*}
a^2 & =b^2+c^2-2bc\cos(\alpha), \\
b^2 & =a^2+c^2-2ac\cos(\beta), \\
c^2 & =a^2+b^2-2ab\cos(\gamma).
\end{align*}](./images/6769010e45d486579a8a6ebc54d2e56fbcd7928f.png)

These equations are useful when you know two sides of a triangle and the angle between them, and you want to find the third side.

###[Circle](./Front matter.md)

The circle is a beautiful shape. If we take the centre of the circle at the origin ![(0,0)](./images/4467446eac588743b0a225c1f23f0769d34ee1f5.png), the circle of radius ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png) corresponds to the equation

![x^2 + y^2 = r^2.](./images/75b80d8daf9d32c2dcf4711bd50bb2bd63620011.png)

This formula describes the set of points ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) with a distance from the centre equal to ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png).

####[Area](./Front matter.md)

The area enclosed by a circle of radius ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png) is given by ![A = \pi r^2](./images/5a0ae5c752df99e984938906c2483cb9d1305dc1.png). A circle of radius ![r=1](./images/9143b33c23ebbf4230318e18ec539ee3acf20636.png) has area ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png).

####[Circumference and arc length](./Front matter.md)

The circumference of a circle of radius ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png) is

![C = 2 \pi r.](./images/5ba3c25e46d3b2c61687c53681b77cab49ebe463.png)

A circle of radius ![r=1](./images/9143b33c23ebbf4230318e18ec539ee3acf20636.png) has circumference ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png). This is the total length you can measure by following the curve all the way around to trace the outline of the entire circle. For example, the circumference of a circle of radius ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) m is ![C=2\pi(3) =18.85](./images/a2fb6f82c4787d925905761bbaf1e40446aefa79.png) m. This is how far you’ll need to walk to complete a full turn around a circle of radius ![r=3](./images/45683b5e4cb6dfb0637fff9fbeaaa602bd66852c.png) m.

What is the length of a part of the circle? Say you have a piece of the circle, called an _arc_, and that piece corresponds to the angle ![\theta=57^\circ](./images/854e0fb04a83d21589a429588c9ccf7bb966e68f.png) as shown in[Figure 1.35](./Chapter 1_ Math fundamentals.md). What is the arc’s length ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png)? If the circle’s total length ![C=2 \pi r](./images/86473188aa4629373cded3e508e7ad4e9557e157.png) represents a full ![360^\circ](./images/e062f6a280550879a6671cfdd99a1487bbf2ec7a.png) turn around the circle, then the arc length ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) for a portion of the circle corresponding to the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is

![\ell = 2 \pi r \frac{\theta}{360}\,.](./images/d33221f614cab6e56d7f1fe6b4772df0585b0bc7.png)

The arc length ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) depends on ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png), the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png), and a factor of ![\frac{2\pi}{360}](./images/6c91c1712ed39de8ef1fb484182b2f32179258ef.png).

![circle_arc_length_for_angle_57](./images/circle_arc_length_for_angle_57.png)

Figure 1.35: The arc length ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) equals ![\frac{57}{360}](./images/4034d116b3998c78c74fa2ba61ee75cd09e63426.png) of the circle’s circumference ![2\pi r](./images/6825f08c99855b65f3795517999f6a04c7e95041.png).

####[Radians](./Front matter.md)

While scientists and engineers commonly use degrees as a measurement unit for angles, mathematicians prefer to measure angles in _radians_, denoted ![\textrm{rad}](./images/0f12c1b2f6d421d2295cd02355cb27a5bf6d5a66.png).

Measuring an angle in radians is equivalent to measuring the arc length ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) on a circle with radius ![r=1](./images/9143b33c23ebbf4230318e18ec539ee3acf20636.png), as illustrated in[Figure 1.36](./Chapter 1_ Math fundamentals.md).

![circle_arc_length_for_angle_theta](./images/circle_arc_length_for_angle_theta.png)

Figure 1.36: The angle ![\theta](./images/962d17a7e21d58659675e6e02789c85029447dd5.png) measured in radians corresponds to the arc length ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) on a circle with radius ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png). The full circle corresponds to the angle ![2\pi](./images/8a22179df7683e15968bcee7cd0eefbd44628c4c.png) rad.

The conversion ratio between degrees and radians is

![2\pi \; \text{rad} \; = \;   360^\circ.](./images/72671cdf726acdbf81d91ba2131115e860a703c8.png)

When the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is measured in radians, the arc length is given by:

![\ell = r \theta.](./images/eff0c552da39c5f13384dd9ba9ac28889d4f73ff.png)

To find the arc length ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png), we simply multiply the circle radius ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png) times the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) measured in radians.

Note the arc-length formula with ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) measured in radians is simpler than the arc-length formula with ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) measured in degrees, since we don’t need the conversion factor of ![360^\circ](./images/e062f6a280550879a6671cfdd99a1487bbf2ec7a.png).

###[Sphere](./Front matter.md)

A sphere of radius ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png) is described by the equation ![x^2 + y^2 + z^2 = r^2](./images/712474050ff2ab89e0b642d528c9e787a67509fc.png). The surface area of the sphere is ![A = 4\pi r^2](./images/3e61830f3cccedc407bf1906473218ea94b9741b.png), and its volume is given by ![V = \tfrac{4}{3}\pi r^3](./images/504baad1c8e912ede2d76dcfc65bd6d73df08f52.png).

![volume-sphere](./images/volume-sphere.png)

Figure 1.37: A sphere of radius ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) has surface area ![4\pi r^2](./images/3acd05d424d4a510902aece55148455542187975.png) and volume ![\tfrac{4}{3}\pi r^3](./images/abc8ba44b573617cca402d2e61dff273cb737bb4.png).

###[Cylinder](./Front matter.md)

The surface area of a cylinder consists of the top and bottom circular surfaces, plus the area of the side of the cylinder:

![A = 2\!\left( \pi r^2 \right) + (2\pi r) h.](./images/33a3326972b7d560f8786d864dc2219f8561efdd.png)

The volume of a cylinder is the product of the area of the cylinder’s base times its height:

![V = \left(\pi r^2 \right)h.](./images/d09dfe6742a9bbd42007797f736d45e1475af719.png)

![cylinder_h_r](./images/cylinder_h_r.png)

Figure 1.38: A cylinder with radius ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) and height ![h](./images/77e0e4a50e89652b20f69385d6e8957897e96dcf.png) has volume ![\pi r^2h](./images/48ea7ba1ad10540a5f6a364e664d9be19db82def.png).

#####[Example](./Front matter.md)

You open the hood of your car and see 2.0 L written on top of the engine. The 2.0 L refers to the combined volume of the four pistons, which are cylindrical in shape. The owner’s manual tells you the radius of each piston is 43.75 mm, and the height of each piston is 83.1 mm. Verify the total engine volume is 1998789 mm![^3](./images/7b9b50b436322b2a0526474a915ba85eec6b9c72.png) ![\approx 2](./images/65a71df47e56744968e3f132bfe0db069c4d3709.png) L.

###[Cones and pyramids](./Front matter.md)

The volume of a square pyramid with side length ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and height ![h](./images/f1ca3cd6c70e90cc02066e90b194d6633838fd36.png) is given by the formula ![V=\frac{1}{3}a^2h](./images/36646451b5fe8865599d78073ba0729c12e695d8.png). The volume of a cone of radius ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png) and height ![h](./images/f1ca3cd6c70e90cc02066e90b194d6633838fd36.png) is given by the formula ![V = \tfrac{1}{3}\pi r^2h](./images/1a0d7b5ff8d0d9c61091e3eeacfe822a79cbb447.png). Note the factor ![\frac{1}{3}](./images/2e1382258077dc418e81971924dd9f4f09b9215a.png) appears in both formulas. These two formulas are particular cases of the general volume formula that applies to all pyramids:

![V = \tfrac{1}{3}Ah,](./images/94e440b5408e611f6863551ebe1892debbf2fcf8.png)

where ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is the area of the pyramid’s base and ![h](./images/f1ca3cd6c70e90cc02066e90b194d6633838fd36.png) is its height. This formula applies for pyramids with a base that is a triangle (triangular pyramids), a square (square pyramids), a rectangle (rectangular pyramids), a circle (cones), or any other shape.

![geometry_pyramids_and_cone](./images/geometry_pyramids_and_cone.png)

Figure 1.39: The volumes of pyramids and cones are described by the formula ![V=\frac{1}{3}Ah](./images/f99fd6998289587093fc3336c21fd592498d84a0.png), where ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is the area of the base and ![h](./images/77e0e4a50e89652b20f69385d6e8957897e96dcf.png) is the height.

###[Exercises](./Front matter.md)

E1.13 Find the length of side ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the triangle below.

![cosine_rule_exercise](./images/cosine_rule_exercise.png)

Use the cosine rule.

E1.14 Find the volume and the surface area of a sphere with radius ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png).

E1.15 On a rainy day, Laura brings her bike indoors, and the wet bicycle tires leave a track of water on the floor. What is the length of the water track left by the bike’s rear tire (diameter ![73](./images/1ef3361ba7794d107cab1edb4fabf659128ff2e3.png) cm) if the wheel makes five full turns along the floor?

##[1.11 Trigonometry](./Chapter 1_ Math fundamentals.md)

If one of the angles in a triangle is equal to ![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png), we call this triangle a _right-angle triangle_. In this section we’ll discuss right-angle triangles in great detail and get to know their properties. We’ll learn some fancy new terms like _hypotenuse_, _opposite_, and _adjacent_, which are used to refer to the different sides of a triangle. We’ll also use the functions _sine_, _cosine_, and _tangent_ to compute the _ratios of lengths_ in right triangles.

Understanding triangles and their associated trigonometric functions is of fundamental importance: you’ll need this knowledge for your future understanding of mathematical concepts like vectors and complex numbers.

![rightangletriangle](./images/rightangletriangle.jpg)

Figure 1.40: A right-angle triangle. The angle at the base is denoted ![\theta](./images/962d17a7e21d58659675e6e02789c85029447dd5.png) and the names of the sides of the triangle are indicated.

###[Concepts](./Front matter.md)

-   ![A,B,C](./images/9dc72bafb4194efbc4454a2eff6b19caff5a2f32.png): the three _vertices_ of the triangle
-   ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png): the angle at the vertex ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png). Angles can be measured in degrees or radians.
-   ![\text{opp} = AB](./images/a70b1ac60495b811fa5fdf7d449bc0fe68fbbee8.png): the length of the _opposite_ side to ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png)
-   ![\text{adj} = BC](./images/65fb9b466f1348a7fc9c08237aa95c6ab616092d.png): the length of side _adjacent_ to ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png)
-   ![\text{hyp} = AC](./images/13194876f3d2df4a790c6cff07f6f9521ba92142.png): the _hypotenuse_. This is the triangle’s longest side.
-   ![h](./images/f1ca3cd6c70e90cc02066e90b194d6633838fd36.png): the “height” of the triangle (in this case ![h = \text{opp} = AB](./images/1ad6438835220f87f0871b449dfbbf2481780213.png))
-   ![\sin\theta = \frac{\text{opp}}{\text{hyp}}](./images/22664fcaa7e3d94bd8835f58de04fe84d9671143.png): the _sine_ of theta is the ratio of the length of the opposite side and the length of the hypotenuse
-   ![\cos\theta = \frac{\text{adj}}{\text{hyp}}](./images/68c8874f59d13dba35c7ddd333f8167e63b0b509.png): the _cosine_ of theta is the ratio of the adjacent length and the hypotenuse length
-   ![\tan\theta = \frac{\sin\theta}{\cos\theta} = \frac{\text{opp}}{\text{adj}}](./images/f47c3cfc418bd61785fcfa3146e5ce7f7fadca52.png): the _tangent_ is the ratio of the opposite length divided by the adjacent length

###[Pythagoras’ theorem](./Front matter.md)

In a right-angle triangle, the length of the hypotenuse squared is equal to the sum of the squares of the lengths of the other sides:

![\text{adj}^2 \; + \; \text{opp}^2  \; = \;   \text{hyp}^2.](./images/0112e6c9ea3d5a56c6e6ca8d1a715c8d52c5d011.png)

If we divide both sides of the above equation by ![\text{hyp}^2](./images/53e57ab3decc1696582c49af23ef973dc1326016.png), we obtain

![\frac{\text{adj}^2}{ \text{hyp}^2 } \;  + \; \frac{\text{opp}^2}{ \text{hyp}^2 }  \; = \; 1.](./images/b4bc8bd0fff5f08e45edb14d41f016e40d39d3e9.png)

Since ![\frac{\text{adj}}{\text{hyp}}=\cos\theta](./images/5f8d1807b47fb87f7d08d09166fd3879af021799.png) and ![\frac{\text{opp}}{\text{hyp}} = \sin\theta](./images/d8159b110646a639e05d24e87166b84a12b18ccf.png), this equation can be rewritten as

![\cos^2\theta \; + \; \sin^2\theta = 1.](./images/e8fde4d691ec7733a4038d6f9d55e2f4f1712a24.png)

This is a powerful _trigonometric identity_ that describes an important relation between sine and cosine functions. In case you’ve never seen this notation before, the expression ![\cos^2\theta](./images/647533bfa552116ca74d082df1f80fe2971ce5a5.png) is used to denote ![(\cos(\theta))^2](./images/0db6163a40bccb699fe50fcdde77476c2cc5b91a.png).

###[Sin and cos](./Front matter.md)

Meet the trigonometric functions, or trigs for short. These are your new friends. Don’t be shy now, say hello to them.

“Hello.”

“Hi.”

“Soooooo, you are like functions right?”

“Yep,” sin and cos reply in chorus.

“Okay, so what do you do?”

“Who me?” asks cos. “Well I tell the ratio…hmm…Wait, are you asking what I do as a _function_ or specifically what _I_ do?”

“Both I guess?”

“Well, as a function, I take angles as inputs and I give ratios as answers. More specifically, I tell you how ‘wide’ a triangle with that angle will be,” says cos all in one breath.

“What do you mean wide?” you ask.

“Oh yeah, I forgot to say, the triangle must have a hypotenuse of length 1. What happens is there is a point ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) that moves around on a circle of radius 1, and we _imagine_ a triangle formed by the point ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png), the origin, and the point on the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis located directly below the point ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png).”

“I am not sure I get it,” you confess.

“Let me try explaining,” says sin. “Look at[Figure 1.41](./Chapter 1_ Math fundamentals.md) and you’ll see a circle. This is the unit circle because it has a radius of 1. You see it, yes?”

“Yes.”

“Now imagine a point ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) that moves along the circle of radius 1, starting from the point ![P(0)=(1,0)](./images/357fc0e87aabed65cf686732c5e4902e681dfaa7.png). The ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) coordinates of the point ![P(\theta)=(P_x(\theta),\; P_y(\theta))](./images/d7f3f6982bab70f3c29069a6a4910ebefd6ae848.png) as a function of ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) are

![P(\theta)=(P_x(\theta),\; P_y(\theta)) = (\cos\theta, \; \sin\theta ).](./images/8477e47bb54f09491f4450f000464552974a03bc.png)

So, _either_ you can think of us in the context of triangles, or in the context of the unit circle.”

“Cool. I kind of get it. Thanks so much,” you say, but in reality you are weirded out. Talking functions? “Well guys. It was nice to meet you, but I have to get going, to finish the rest of the book.”

“See you later,” says cos.

“Peace out,” says sin.

###[The unit circle](./Front matter.md)

The _unit circle_ is a circle of radius one centred at the origin. The unit circle consists of all points ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that satisfy the equation ![x^2 + y^2 = 1](./images/af4acd6cf99c0acbe03063911aca7f38dbac2fe1.png). A point ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) on the unit circle has coordinates ![(P_x,P_y)=(\cos\theta,\sin\theta)](./images/d447b08887036c8d688118e5560c20e93940b663.png), where ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is the angle ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) makes with the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis.

![trigonometric_functions_as_point_or_as_triangle](./images/trigonometric_functions_as_point_or_as_triangle.png)

Figure 1.41: The unit circle corresponds to the equation ![x^2+y^2=1](./images/950836720d563cfffe789815f321c6bde34e1565.png). The coordinates of the point ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) on the unit circle are ![P_x= \cos\theta](./images/ad7c44e04cfff5c5c9593cda7cd0da9915824dc9.png) and ![P_y=\sin\theta](./images/16e7e26952b4d7016933bce0ab62819bad48edf7.png).

![the_graph_of_sin_theta_as_the_vertical_component_of_P_on_unit_circle](./images/the_graph_of_sin_theta_as_the_vertical_component_of_P_on_unit_circle.png)

Figure 1.42: The function ![f(\theta)=\sin\theta](./images/0c2eb915573dd8bb5bc5f3fd283754b94f1f7375.png) describes the vertical position of a point ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) that travels along the unit circle. The graph shows the values of the function ![f(\theta)=\sin\theta](./images/0c2eb915573dd8bb5bc5f3fd283754b94f1f7375.png) for angles between ![\theta=0](./images/fe080cb3d59fd6ee273544426f89e8f491790085.png) and ![\theta=\pi](./images/da4ecc733f99196b8f72d193e57edb0091409e66.png).

[Figure 1.42](./Chapter 1_ Math fundamentals.md) shows the graph of the function ![f(\theta)=\sin\theta](./images/e3e2f15b41d193422fd0cfcfa32a3bf391076916.png). The values ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) for the angles ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png), ![\frac{\pi}{6}](./images/d808f73eb3b1ee4c2fa9c2494b068e7daf80797b.png) (![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png)), ![\frac{\pi}{3}](./images/f36d70c9f72528bf2a51e2dde96b3d31d318eb66.png) (![60^\circ](./images/fa017a0b5a1cfa24a2498c20df91459d36ae3268.png)), and ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png) (![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png)) are marked. There are three values to remember: ![\sin\theta = 0](./images/bba81004b4a3dc84dff0518499a454524075b70a.png) when ![\theta = 0](./images/2b705e4c8211e7331368d3b370c932d9289ebe9a.png), ![\sin\theta = \frac{1}{2}](./images/32dc202dc5c3db1f91a28549b4c2a4183bef3a88.png) when ![\theta = \frac{\pi}{6}](./images/fd8ea45cdf3f83b6e9c0b15f04b438d9df0e6409.png) (![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png)), and ![\sin\theta = 1](./images/bde330c88b0d574993dfbd18bdaddd4e6c95b046.png) when ![\theta=\frac{\pi}{2}](./images/fecd60e58ea6f0a4bbcbdd95bc3a6fdae935ef6a.png) (![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png)). See[Figure 1.26](./Chapter 1_ Math fundamentals.md) (page 1.26) for a graph of ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) that shows a complete cycle around the circle. Also see[Figure 1.29](./Chapter 1_ Math fundamentals.md) (page 1.29) for the graph of ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png).

Instead of trying to memorize the values of the functions ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) and ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) separately, it’s easier to remember them as a combined “package” ![(\cos\theta, \sin\theta)](./images/a3582a5b7e99b628756ef1371b95ec1431bffa38.png), which describes the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinates of the point ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) for the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png).[Figure 1.43](./Front matter.md) shows the values of ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) and ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) for the angles ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png), ![\frac{\pi}{6}](./images/d808f73eb3b1ee4c2fa9c2494b068e7daf80797b.png) (![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png)), ![\frac{\pi}{4}](./images/83eb36bebaea14b26caf7467fcb663a1882deb23.png) (![45^\circ](./images/bd3d3974358aa0059bc92afb15aa60914b97d2d5.png)), ![\frac{\pi}{3}](./images/f36d70c9f72528bf2a51e2dde96b3d31d318eb66.png) (![60^\circ](./images/fa017a0b5a1cfa24a2498c20df91459d36ae3268.png)), and ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png) (![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png)). These are the most common angles that often show up on homework and exam questions. For each angle, the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-coordinate (the first number in the bracket) is ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png), and the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinate (the second number in the bracket) is ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png).

![trigonometry--unit-circle-with-angles-and-cos-sin-first_quadrant](./images/trigonometry--unit-circle-with-angles-and-cos-sin-first_quadrant.jpg)

Figure 1.43: The combined ![(\cos\theta, \sin\theta)](./images/86dc16bf45417a60bbc414bf304d4389a25aa8b2.png) coordinates for the points on the unit circle at the most common angles: ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png), ![\frac{\pi}{6}](./images/3b5d0f66c30c7d568d256ea0d710e1290fecef1a.png) (![30^\circ](./images/305983de0b217ba62d42b17421a4d2daa9bddfcc.png)), ![\frac{\pi}{4}](./images/baeefa71dccdc5bcb680be1d02cfb40156408352.png) (![45^\circ](./images/21a712deb257850ddb3c03e861d51b65dcdf7325.png)), ![\frac{\pi}{3}](./images/590c0261a4175c0a9d062439132515c23ea11b32.png) (![60^\circ](./images/ca89e63627d449b782f61dbf3d42b1b471e52375.png)), and ![\frac{\pi}{2}](./images/875b844877de8f3ff1fc0e18eee091b18c254300.png) (![90^\circ](./images/684ce1d7bc30223b2bca0253677a7a121af338f6.png)).

Note the values of ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) and ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) for the angles shown in[Figure 1.43](./Front matter.md) are all combinations of the fractions ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png), ![\frac{\sqrt{2}}{2}](./images/75c083857b78189709130b86fcff9f88a8252278.png), and ![\frac{\sqrt{3}}{2}](./images/1fc94afe0ffaed9c3c1e702a6f9678255c1b6505.png). The square roots appear as a consequence of the trigonometric identity ![\cos^2\theta + \sin^2\theta = 1](./images/c72d9c1f692a201bcad239b8c2722470cdb49bb6.png). This identity tells us that the sum of the squared coordinates of each point on the unit circle is equal to one. Let’s look at what this equation tells us for the angle ![\theta = \frac{\pi}{6}](./images/fd8ea45cdf3f83b6e9c0b15f04b438d9df0e6409.png) (![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png)). Remember that ![\sin(30^\circ) = \frac{1}{2}](./images/53628543829e6b3bc70b77c6590ca9fc226858a0.png) (the length of the dashed line in[Figure 1.43](./Front matter.md)). We can plug this value into the equation ![\cos^2(30^\circ) + \sin^2(30^\circ) = 1](./images/7eafdaf5dfd33894cdffc327fee2cd3e5d1df543.png) to find the value: ![\cos(30^\circ) = \sqrt{ 1 - \sin^2(30^\circ)  } = \sqrt{ 1 - \frac{1}{4} } = \sqrt{ \frac{3}{4} } =  \tfrac{\sqrt{3}}{2}](./images/e0a05d80d857e81b29be38aca45d1ee335dc62b7.png).

The coordinates ![\left(\frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2} \right)](./images/3188e596723e8508681d2bf2aca3ea1e2c04a47b.png) for the angle ![\theta = \frac{\pi}{4}](./images/6e3ba6511e53f90b16bc99e7de9c08da73ee83e6.png) (![45^\circ](./images/bd3d3974358aa0059bc92afb15aa60914b97d2d5.png)) are obtained from a similar calculation. We know the values of ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) and ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) must be equal for that angle, so we’re looking for the number ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) that satisfies the equation ![a^2 + a^2 = 1](./images/353446d1b56fce61f81ec77a40d506c45bed7980.png), which is ![a=\frac{1}{\sqrt{2}} = \frac{\sqrt{2}}{2}](./images/f0c26fa9ec5a54d06a2ab4597a284f42e1c559b8.png). The values of ![\cos(60^\circ)](./images/43cae69ffd3e483b44991148e0f69d1b94c5c945.png) and ![\sin(60^\circ)](./images/a3ffc3bdc8ea80b2cf644f9f18940abb1c29e7d6.png) can be obtained from a symmetry argument. Measuring ![60^\circ](./images/fa017a0b5a1cfa24a2498c20df91459d36ae3268.png) from the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis is the same as measuring ![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png) from the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis, so ![\cos(60^\circ)=\sin(30^\circ)=\frac{1}{2}](./images/9222803cfb400a427309b8ff349bfb45718e912e.png) and ![\sin(60^\circ) = \cos(30^\circ) = \frac{\sqrt{3}}{2}](./images/162edb9dfa27df6bb418bf3e2b0c61571d860891.png).

We can extend the calculations described above for all other angles that are multiples of ![\frac{\pi}{6}](./images/d808f73eb3b1ee4c2fa9c2494b068e7daf80797b.png) (![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png)) and ![\frac{\pi}{4}](./images/83eb36bebaea14b26caf7467fcb663a1882deb23.png) (![45^\circ](./images/bd3d3974358aa0059bc92afb15aa60914b97d2d5.png)) to obtain the ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) and ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) values for the whole unit circle, as shown in[Figure 1.44](./Chapter 1_ Math fundamentals.md).

![trigonometry--unit-circle-with-angles-and-cos-sin](./images/trigonometry--unit-circle-with-angles-and-cos-sin.png)

Figure 1.44: The coordinates of the point on the unit circle ![(\cos\theta, \sin\theta)](./images/86dc16bf45417a60bbc414bf304d4389a25aa8b2.png) are indicated for all multiples of ![\frac{\pi}{6}](./images/3b5d0f66c30c7d568d256ea0d710e1290fecef1a.png) (![30^\circ](./images/305983de0b217ba62d42b17421a4d2daa9bddfcc.png)) and ![\frac{\pi}{4}](./images/baeefa71dccdc5bcb680be1d02cfb40156408352.png) (![45^\circ](./images/21a712deb257850ddb3c03e861d51b65dcdf7325.png)). Note the symmetries.

Don’t be intimidated by all the information shown in[Figure 1.44](./Chapter 1_ Math fundamentals.md)! You’re not expected to memorize all these values. The primary reason for including this figure is so you can appreciate the symmetries of the sine and cosine values that we find as we go around the circle. The values of ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) and ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) for all angles are the same as the values for the angles between ![0^\circ](./images/0d7756c7a9232950a519c1caab5b749470e96404.png) and ![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png), but one or more of their coordinates has a negative sign. For example, ![150^\circ](./images/d21864e643c9e80c30c28290c0baf24297296a28.png) is just like ![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png), except its ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-coordinate is negative since the point lies to the left of the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis. Another use for[Figure 1.44](./Chapter 1_ Math fundamentals.md) is to convert between angles measured in degrees and radians, since both units for angles are indicated.

###[Non-unit circles](./Front matter.md)

Consider a point ![Q(\theta)](./images/bb3a639c08214d6d9f3ba88c71a3dcaaac43b786.png) at an angle of ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) on a circle with radius ![r\neq1](./images/70016a74235637d674b338b85a33c6cf4efdc3aa.png). How can we find the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinates of the point ![Q(\theta)](./images/bb3a639c08214d6d9f3ba88c71a3dcaaac43b786.png)?

We saw that the coefficients ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) and ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) correspond to the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinates of a point on the _unit_ circle (![r=1)](./images/7d9559c4b4bb6269c53883dcd80a7ebc25deca9e.png). To obtain the coordinates for a point on a circle of radius ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png), we must _scale_ the coordinates by a factor of ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png):

![Q(\theta) =  (Q_x(\theta), Q_y(\theta) ) =  ( r\cos\theta, r\sin\theta ).](./images/437073dab59be59c92398a80396c49fe0f4d5cf1.png)

![decomposing_vector_r_into_two_parts](./images/decomposing_vector_r_into_two_parts.png)

Figure 1.45: The ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\- and ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png)\-coordinates of a point at the angle ![\theta](./images/962d17a7e21d58659675e6e02789c85029447dd5.png) and distance of ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) from the origin are given by ![x=r\cos\theta](./images/8398e3c9742c15e1f75620a2bd52249cea00f6b7.png) and ![y=r\sin\theta](./images/00567fc74e2e546e1c6dbf32e2885689bf7ef12b.png).

The take-away message is that you can use the functions ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) and ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png) to find the “horizontal” and “vertical” components of any length ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png). From this point on in the book, we’ll always talk about the length of the _adjacent_ side as ![x=r\cos\theta](./images/e38646af349076ae5b057e31ba6c0b235f7c93d5.png), and the length of the _opposite_ side as ![y = r\sin\theta](./images/85f38127fbb2a2113b2ac101fad1cb967d55a65e.png). It is extremely important you get comfortable with this notation.

The reasoning behind the above calculations is as follows:

![\cos\theta
=
\frac{\text{adj}}{\text{hyp}} = \frac{x}{r}
\quad \Rightarrow \quad  
x = r \cos\theta,  \\](./images/b304a5630e54f84087e3c4410e264beefe9efcfa.png)

and

![\sin\theta
=
\frac{\text{opp}}{\text{hyp}}=\frac{y}{r}
\quad \Rightarrow \quad
y = r\sin\theta.](./images/775a9842108ea7f47a99dce7c3dcb977263715c0.png)

###[Calculators](./Front matter.md)

Watch out for the units of angle measures when using calculators and computers. Make sure you know what kind of angle units the functions ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png), ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png), and ![\tan](./images/23bcb493ab30c7e1982ecdfc718cb114739a236e.png) expect as inputs, and what kind of outputs the functions ![\sin^{-1}](./images/f1f15f8a6c1d7b57372601fa0c266d09e48d1022.png), ![\cos^{-1}](./images/6ee3216c73c8efa549ab83ad0faa200c9e50f39a.png), and ![\tan^{-1}](./images/4c7e0e6f32fbf1ec2542303bff7bb0d31040cb87.png) return.

For example, let’s see what we should type into the calculator to compute the sine of 30 degrees. If the calculator is set to degrees, we simply type: ![\button{\texttt{3}}](./images/44ea8e2cd2978a8c88bbf292c09a97ec80d98bd4.png), ![\button{\texttt{0}}](./images/5bfe97fd27beaa001e32524d640278331f187959.png), ![\button{\texttt{sin}}](./images/ef9e30cb23bc0fa5e5e3b74d39b7d23b94736f5d.png), ![\button{\texttt{=}}](./images/8e58896e2f61a42b8457fc121fb48a328fa4503f.png), and obtain the answer ![0.5](./images/68d4957d7f32385c33450fcf78986d1693f0d2b2.png).

If the calculator is set to radians, we have two options:

1.  Change the `mode` of the calculator so it works in degrees.
2.  Convert ![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png) to radians
    
    ![30^\circ \times \frac{ 2\pi \; \text{rad} }{ 360^\circ } = \frac{\pi}{6} \; \text{rad},](./images/f3725fc08114a94179adeda671ec202ae32be081.png)
    
    and type: ![\button{\pi}](./images/eb0edc4fbd6e9a2354d4a3f8aa9a22916e90be02.png), ![\button{\small\texttt{/}}](./images/e2119f0d4666ee439518ba6adb2401d5e75b2ea2.png), ![\button{\texttt{6}}](./images/09adceb6b5ed2985f1d0106a4b5b0ed063ec4fd2.png), ![\button{\texttt{sin}}](./images/ef9e30cb23bc0fa5e5e3b74d39b7d23b94736f5d.png), ![\button{\texttt{=}}](./images/8e58896e2f61a42b8457fc121fb48a328fa4503f.png) on the calculator.
    

Try computing ![\cos(60^\circ)](./images/43cae69ffd3e483b44991148e0f69d1b94c5c945.png), ![\cos\!\big(\frac{\pi}{3}\; \text{rad}\big)](./images/6951213361271032028ae03a1b971b1aa450b75f.png), and ![\cos^{-1}(\frac{1}{2})](./images/6de347d342cdb0adbb400fb9249344ff85d440a4.png) using your calculator to make sure you know how it works.

###[Exercises](./Front matter.md)

E1.16 Given a circle with radius ![r=5](./images/6bcf954f04a8a296832d618b376476047f7d1a2b.png), find the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinates of the point at ![\theta=45^{\circ}](./images/e89633c8872e5a9901f0fde99b6882655acb9156.png). What is the circumference of the circle?

E1.17 Convert the following angles from degrees to radians.

**a)** ![30^\circ](./images/dbafc023e090ac92e968892e2a8c3570fe3ceba2.png) **b)** ![45^\circ](./images/bd3d3974358aa0059bc92afb15aa60914b97d2d5.png) **c)** ![60^\circ](./images/fa017a0b5a1cfa24a2498c20df91459d36ae3268.png) **d)** ![270^\circ](./images/353599644066235caade9d74c725c105caac634b.png)

###[Links](./Front matter.md)

\[ Unit-circle walkthrough and tricks by patrickJMT on YouTube \]

[`http://bit.ly/1mQg9Cj`](./1mQg9Cj.md) and[`http://bit.ly/1hvA702`](./1hvA702.md)

##[1.12 Trigonometric identities](./Chapter 1_ Math fundamentals.md)

There are a number of important relationships between the values of the functions ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png) and ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png). Here are three of these relationships, known as _trigonometric identities_. There about a dozen other identities that are less important, but you should memorize these three.

The three identities to remember are:

####[1. Unit hypotenuse](./Front matter.md)

![\sin^2 \theta + \cos^2 \theta = 1.](./images/6654d9df7639f64437d01dfa136f738a7272cd6c.png)

The unit hypotenuse identity is true by the Pythagoras theorem and the definitions of sin and cos. The sum of the squares of the sides of a triangle is equal to the square of the hypotenuse.

####[2. Sine angle sum](./Front matter.md)

![\sin(a + b)=\sin(a)\cos(b) + \sin(b)\cos(a).](./images/c8721e7c0b87dfaabdbb8a1f57ccd39d620401df.png)

The mnemonic for this identity is “sico + sico.”

####[3. Cosine angle sum](./Front matter.md)

![\cos(a + b)=\cos(a)\cos(b) - \sin(a)\sin(b).](./images/0e3344d5775a16c050785c6d803ad4bbc534728f.png)

The mnemonic for this identity is “coco ![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png) sisi.” The negative sign is there because it’s not good to be a sissy.

###[Derived formulas](./Front matter.md)

If you remember the above three formulas, you can derive pretty much all the other trigonometric identities.

####[Double angle formulas](./Front matter.md)

Starting from the sico + sico identity and setting ![a=b=x](./images/b8a173bed9280d7a9ed664a4be11b166cfb3d88d.png), we can derive the following identity:

![\sin(2x) = 2\sin(x)\cos(x).](./images/b350223f87cf61a991b146c3e2b4a521fcdfb81f.png)

Starting from the coco-sisi identity, we obtain

![\begin{align*}
\cos(2x) 
&\;  = \cos^2(x) - \sin^2(x) \\			  
&\; =\; 2\cos^2(x) - 1 
\; = 2\left(1 - \sin^2(x)\right) - 1 
\; = 1 - 2\sin^2(x).
\end{align*}](./images/aa3406828baeaef0145ac3140cacacfc265046a5.png)

The formulas for expressing ![\sin(2x)](./images/b55e009af2d930e0ff4754e67484350d81a368a3.png) and ![\cos(2x)](./images/d58d6288b93527ada8c3ebfba086f8f479eff895.png) in terms of ![\sin(x)](./images/8fa5e82f1189bb918740e8129de7061161939a9c.png) and ![\cos(x)](./images/42eba01bdd88eaeb543a741e31931fb1bcc1f295.png) are called _double angle formulas_.

If we rewrite the double-angle formula for ![\cos(2x)](./images/d58d6288b93527ada8c3ebfba086f8f479eff895.png) to isolate the ![\sin^2](./images/4844ed3636dbddd28b46e8dca7598c99ed77d78e.png) or the ![\cos^2](./images/67591add05228df6e2a8c974f7b85f1b804088b0.png) term, we obtain the _power-reduction formulas_:

![\cos^2(x) = \frac{1}{2}\left(1+\cos(2x)\right), \qquad
\sin^2(x) = \frac{1}{2}\left(1-\cos(2x)\right).](./images/16c24320510180e2d9419490e17d018a36705495.png)

####[Self-similarity](./Front matter.md)

Sin and cos are periodic functions with period ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png). Adding a multiple of ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png) to the function’s input does not change the function:

![\sin(x + 2\pi)= \sin(x), \qquad  \cos(x+2\pi)=\cos(x).](./images/cee46deed806b367d464e30d89c9e71791bc9b21.png)

This follows because adding a multiple of ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png) brings us back to the same point on the unit circle.

Furthermore, sin and cos have symmetries with respect to zero,

![\sin(-x)=-\sin(x), \qquad   \cos(-x)=\cos(x),](./images/58ef3f671b595d7bf139c10cd248165c77240dbb.png)

within each ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) half-cycle,

![\sin(\pi-x)=\sin(x), \qquad   \cos(\pi-x)=-\cos(x),](./images/cd9408238c7130e7542057d73143bc99a8aff944.png)

and within each full ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png) cycle,

![\sin(2\pi-x)=-\sin(x), \qquad   \cos(2\pi-x)=\cos(x).](./images/623740ce431546c4395426c8925d5f061652eb0e.png)

Take the time to revisit[Figure 1.26](./Chapter 1_ Math fundamentals.md) (page 1.26),[Figure 1.29](./Chapter 1_ Math fundamentals.md) (page 1.29), and[Figure 1.44](./Chapter 1_ Math fundamentals.md) (page 1.44) to visually confirm that all the equations shown above are true. Knowing the points where the functions take on the same values (symmetries) or take on opposite values (anti-symmetries) is very useful in calculations.

####[Sin is cos, cos is sin](./Front matter.md)

It shouldn’t be surprising if I tell you that sin and cos are actually ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png)\-shifted versions of each other:

![\cos(x)=\sin\!\left(x\!+\!\tfrac{\pi}{2}\right)\!,	
\qquad
\sin(x) = \cos\!\left(x\!-\!\tfrac{\pi}{2}\right)\!.](./images/ba2ba25ae5c8625ce6f10c61e2d7040d9cbbeb3d.png)

####[Formulas for sums and products](./Front matter.md)

Here are some formulas for transforming sums into products:

![\sin\!\left(a\right)+\sin\!\left(b\right)=2\sin\!\left(\tfrac{1}{2}(a+b)\right)\cos\!\left(\tfrac{1}{2}(a-b)\right),](./images/64c18d04b14a3204567b53b89993cd5d180557cb.png)

![\sin\!\left(a\right)-\sin\!\left(b\right)=2\sin\!\left(\tfrac{1}{2}(a-b)\right)\cos\!\left(\tfrac{1}{2}(a+b)\right),](./images/d9ec0e88709c9ba5e440ade7c59f3475a1eb507e.png)

![\cos\!\left(a\right)+\cos\!\left(b\right)=2\cos\!\left(\tfrac{1}{2}(a+b)\right)\cos\!\left(\tfrac{1}{2}(a-b)\right),](./images/f28692f8a19bf1c3a0c2855342f21ad829c2faf6.png)

![\cos\!\left(a\right)-\cos\!\left(b\right)=-2\sin\!\left(\tfrac{1}{2}(a+b)\right)\sin\!\left(\tfrac{1}{2}(a-b)\right).](./images/42b4465f16fd8bf07e198a4ed89f2c2b1f2d4506.png)

And here are some formulas for transforming products into sums:

![\sin(a)\cos(b) = \tfrac{1}{2}\Big(\sin(a+b)+\sin(a-b)\Big),](./images/1c0d33fa4e78a4c6f60a5d15e0cb3337375300fe.png)

![\sin(a)\sin(b) = \tfrac{1}{2}\Big(\cos(a-b)-\cos(a+b)\Big),](./images/a4a27418a793ab827f14fddb09caffcb9b4685d1.png)

![\cos(a)\cos(b) = \tfrac{1}{2}\Big(\cos(a-b)+\cos(a+b)\Big).](./images/ee97971c70ce7aa2ccfc1bddd4b93ae914ff7933.png)

###[Discussion](./Front matter.md)

The above formulas will come in handy when you need to find some unknown in an equation, or when you are trying to simplify

###[Exercises](./Front matter.md)

E1.18 Given ![a=\pi](./images/ee0a8302d79ed2c2aefdfe5f3637002bd2040738.png) and ![b=\frac{\pi}{2}](./images/30f6fcfee58ef857a0fd79cbc5754b7211e8d4f0.png), find

**a)** ![\sin(a+b)](./images/fbea16b1033457bacd08bddda6c18bb02e09679e.png) **b)** ![\cos(2a)](./images/6d9fdc72c8a614566568f1fe43b738edaf1aa777.png) **c)** ![\cos(a+b)](./images/7beb089058ea17213ee03ac46f0ad530dc44aeaa.png)

E1.19 Simplify the following expressions and compute their value without using a calculator.

**a)** ![\cos(x)+\cos(\pi-x)](./images/748f5cab22aaf0b126a7f971302f0fe10acf3684.png) **b)** ![2\sin^2(x)+\cos(2x)](./images/6715ecdbe092621df7be23ead21e9b5e4cc67de7.png)

**c)** ![\sin(\frac{5\pi}{4}) \sin(-\frac{\pi}{4})](./images/1690ff085c3c4c4347c08784815fa4528254c200.png) **d)** ![2\cos(\frac{5\pi}{4}) \cos(-\frac{\pi}{4}) \cos(\pi)](./images/35f3fe13eabf5146f0c01d4c525fcfe01ed69666.png)

##[1.13 Vectors](./Chapter 1_ Math fundamentals.md)

In this section we’ll learn how to manipulate multi-dimensional objects called vectors. Vectors are the precise way to describe directions in space. We need vectors in order to describe physical quantities like the velocity of an object, its acceleration, and the net force acting on the object. Vectors are used more broadly in the study of computer graphics, probability theory, machine learning, and other fields of science and mathematics. It’s all about vectors these days, so you better get to know them.

![vector_components](./images/vector_components.png)

Figure 1.46: The vector ![\vec{v}=(3,2)](./images/b1326924dc2e600e1e701dbb1ef93408e479cc3d.png) is an arrow in the Cartesian plane. The horizontal component of ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) is ![v_x=3](./images/2cf77d54a38334b818ba4139156d4898b2a6e138.png) and the vertical component is ![v_y=2](./images/66a3f7a2b2a1c5d950b18504e7085738c9c4ea5a.png).

Vectors are built from _components_, which are ordinary numbers. You can think of a vector as a list of numbers, and _vector algebra_ as operations performed on the numbers in the list. Vectors can also be manipulated as geometric objects, represented by arrows in space. The arrow that corresponds to the vector ![\vec{v}=(v_x,v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png) starts at the origin ![(0,0)](./images/4467446eac588743b0a225c1f23f0769d34ee1f5.png) and ends at the point ![(v_x,v_y)](./images/bf08d8f270c5ace12ee18ba92752c926e1cd6f5b.png). The word vector comes from the Latin _vehere_, which means _to carry_. Indeed, the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) takes the point ![(0,0)](./images/4467446eac588743b0a225c1f23f0769d34ee1f5.png) and carries it to the point ![(v_x,v_y)](./images/bf08d8f270c5ace12ee18ba92752c926e1cd6f5b.png).

![vectors_concept_map](./images/vectors_concept_map.jpg)

Figure 1.47: This figure illustrates the new concepts related to vectors. As you can see, there is quite a bit of new vocabulary to learn, but don’t be fazed—all these terms are just fancy ways of talking about arrows.

Vectors are extremely useful in all areas of life. In physics, for example, we use a vector to describe the velocity of an object. It is not sufficient to say that the speed of a tennis ball is 200 kilometres per hour: we must also specify the direction in which the ball is moving. Both of the two velocities

![\vec{v}_1 = (200,0) 
\qquad \textrm{and}
\qquad \vec{v}_2=(0,200)](./images/6101cd6f2dba035b714249d237221d4d10d05d83.png)

describe motion at the speed of ![200](./images/204dfa22e65a81ae547637327538dcc1cdf447ff.png) kilometres per hour; but since one velocity points along the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis, and the other points along the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis, they are _completely_ different velocities. The velocity vector contains information about the object’s speed _and_ its direction. The direction makes a big difference. If it turns out the tennis ball is hurtling toward you, you’d better get out of the way!

###[Definitions](./Front matter.md)

A two-dimensional vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) corresponds to a _pair of numbers_:

![\vec{v} = (v_x, v_y),](./images/acfde2581536fd9b8bce0e74932206b8c1541c72.png)

where ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) is the _![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-component_ of the vector and ![v_y](./images/6f1ce966448346cbc28c3277a48ccbc1483c0f8c.png) is its _![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-component_. We denote the set of two-dimensional vectors as ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png), since the components of a two-dimensional vector are specified by two real numbers. We’ll use the mathematical shorthand ![\vec{v} \in \mathbb{R}^2](./images/e3178de0f13474a865bbadb33a26cc93ba2230b3.png) to define a two-dimensional vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). Vectors in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png) can be represented as arrows in the Cartesian plane. See the vector ![\vec{v}=(3,2)](./images/fe77600797085587e6baec5f7e6ccc43b1d49b80.png) illustrated in[Figure 1.46](./Chapter 1_ Math fundamentals.md).

We can also define three-dimensional vectors like the vector ![\vec{v} = (v_x, v_y, v_z) \in \mathbb{R}^3](./images/846f4bcc7c0555bef131d5c6c7e0589ae501c104.png), which has three components. Three-dimensional vectors can be represented as arrows in a coordinate system that has three axes, like the one shown in[Figure 1.55](./Chapter 1_ Math fundamentals.md) on page 1.55. A three-dimensional coordinate system is similar to the Cartesian coordinate system you’re familiar with, and includes the additional ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-axis that measures the height above the plane. In fact, there’s no limit to the number of dimensions for vectors. We can define vectors in an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional space: ![\vec{v} = (v_1, v_2, \ldots, v_n) \in \mathbb{R}^n](./images/bc3ba25e4cc7bd8db126bf85e909a7bcb658ed98.png). For the sake of simplicity, we’ll define all the vector operation formulas using two-dimensional vectors. Unless otherwise indicated in the text, all the formulas we give for two-dimensional vectors ![\vec{v} \in \mathbb{R}^2](./images/e3178de0f13474a865bbadb33a26cc93ba2230b3.png) also apply to ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vectors ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png).

####[Vector operations](./Front matter.md)

Consider two vectors, ![\vec{u}=(u_x,u_y)](./images/e3868cb48e118b5925103a15d0f6d0c4f8f78712.png) and ![\vec{v}=(v_x,v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png), and assume that ![\alpha \in \mathbb{R}](./images/291a1b884bfe1bd3bdd9e4811c426bcf4da094c5.png) is an arbitrary constant. The following operations are defined for these vectors:

-   **Addition:** ![\vec{u} + \vec{v} = (u_x+v_x,\, u_y+v_y)](./images/055113a1178af569bd531a6d479d8ee0da9b89e0.png)
-   **Subtraction:** ![\vec{u} - \vec{v} = (u_x-v_x,\, u_y-v_y)](./images/1279d6af1a9a070c2dff5fec8163b42ede322a9d.png)
-   **Scaling:** ![\alpha \vec{u} = (\alpha u_x,\, \alpha u_y)](./images/e94f3989924d6865f7c1fe72ccfe7900b4fed506.png)
-   **Dot product:** ![\vec{u} \cdot \vec{v}  = u_xv_x+u_yv_y](./images/1df07f27b8070a6fa6e9dd9f3362c6f95a376845.png)
-   **Length:** ![\|\vec{u}\| = \sqrt{\vec{u}\cdot\vec{u}} = \sqrt{u_x^2+u_y^2}](./images/ddfd4eb1f617c4294e73a3f30985e026233ddff7.png). The vector’s length is also called the _norm_ of the vector. We sometimes use the letter ![u](./images/82a971ebc8ceb9b9a22bd63d00ce51c1323a931d.png) to denote the length of the vector ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png).

Note there is no vector division operation.

For vectors in a three-dimensional space ![\vec{u}=(u_x,u_y,u_z) \in \mathbb{R}^3](./images/421ff0b542f02b29c43425fb9ca488c7e6fbfbeb.png) and ![\vec{v}=(v_x,v_y,v_z) \in \mathbb{R}^3](./images/846f4bcc7c0555bef131d5c6c7e0589ae501c104.png), we can also define the **cross product** operation ![\vec{u} \times \vec{v} = (u_yv_z-u_zv_y,\; u_zv_x-u_xv_z,\; u_xv_y-u_yv_x)](./images/104e0169bf5dfbd2479945a3cfa2887ec778ed69.png). The dot product and the cross product are new operations that you probably haven’t seen before. We’ll talk more about dot products and the cross products later on. For now let’s start with the basics.

####[Vector representations](./Front matter.md)

We’ll use three equivalent ways to denote vectors in two dimensions:

-   ![\vec{v} =(v_x, v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png): component notation. The vector is written as a pair of numbers called the _components_ or _coordinates_ of the vector.
-   ![\vec{v} =v_x\hat{\imath}+ v_y\hat{\jmath}](./images/cd33df884edcfbe9d040c4d295f459405759d0fb.png): unit vector notation. The vector is expressed as a combination of the unit vectors ![\hat{\imath} = (1,0)](./images/ca117edff5a44d8252c5b0538071c75e20e886c9.png) and ![\hat{\jmath} = (0,1)](./images/f732fb0e5b4bfd2b91753a5a3f7214b5dcebd378.png).
-   ![\vec{v}=\|\vec{v}\|\angle \theta](./images/32e62fd8c275610b10b0d3067c0a65097aa03684.png): length-and-direction notation (also known as _polar coordinates_). The vector is expressed in terms of its _length_ ![\|\vec{v}\|](./images/8f866786ba2376f2849ed080dcb2433d9371ba0f.png) and the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) that the vector makes with the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis.

![vector_components_annotated](./images/vector_components_annotated.png)

Figure 1.48: The vector ![\vec{v}=(v_x,v_y) = v_x\hat{\imath}+ v_y\hat{\jmath} = \|\vec{v}\|\angle \theta](./images/980bcd07a58d9506344f6782fc3b933d69687ea8.png).

We use the component notation for doing vector algebra calculations since it is most compact. The unit vector notation shows explicitly that the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) corresponds to the sum of ![v_x\hat{\imath}](./images/b60a2e8e062ed9b895ef4b53b3966742ca1958e5.png) (a displacement of ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) steps in the direction of the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis) and ![v_y\hat{\jmath}](./images/c8fcad2c0e5bc6dd463b5baf1ec21ba4d4e89c1f.png) (a displacement of ![v_y](./images/6f1ce966448346cbc28c3277a48ccbc1483c0f8c.png) steps in the direction of the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis). The length-and-direction notation describes the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) as a displacement of ![\|\vec{v}\|](./images/8f866786ba2376f2849ed080dcb2433d9371ba0f.png) steps in the direction of the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png). We’ll use all three ways of denoting vectors throughout the rest of the book, and we’ll learn how to convert between them.

###[Vector algebra](./Front matter.md)

#####[Addition and subtraction](./Front matter.md)

Just like numbers, you can add vectors

![\vec{v}+\vec{w} = (v_x, \, v_y) + (w_x, \, w_y) = (v_x+w_x, \, v_y+w_y),](./images/32b353543d5408a660d3a0ebcb56cb8b7469110f.png)

subtract them

![\vec{v}-\vec{w} = (v_x, \, v_y) - (w_x, \, w_y) = (v_x-w_x, \, v_y-w_y),](./images/462a1d26039d5cd41b10ff48f9bd307799cd9dde.png)

and solve all kinds of equations where the unknown variable is a vector. This is not a formidably complicated new development in mathematics. Performing arithmetic calculations on vectors simply requires **carrying out arithmetic operations on their components**. Given two vectors, ![\vec{v}=(4,2)](./images/42f3ee36d1973937e3d0ed79a643610d52f95218.png) and ![\vec{w}=(3,7)](./images/536248f2b253d2ec18175408aed68492b39b17ef.png), their difference is computed as ![\vec{v}-\vec{w} = (4, 2) - (3, 7) = (1,  -5)](./images/17335c3240f454c916f2ad3d1e0a0c988fc5684a.png).

#####[Scaling](./Front matter.md)

We can also _scale_ a vector by any number ![\alpha \in \mathbb{R}](./images/291a1b884bfe1bd3bdd9e4811c426bcf4da094c5.png):

![\alpha \vec{v} = (\alpha v_x, \alpha v_y),](./images/dac828132e1d189652516a4ae1e37d58dde05b27.png)

where each component is multiplied by the scale factor ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png). Scaling changes the length of a vector. If ![\alpha>1](./images/5117d41b3ada605992913a472895044983f62b30.png) the vector will get longer, and if ![0\leq \alpha <1](./images/061eca709136c45c573f1a31dd82affb33d1dcee.png) then the vector will become shorter. If ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) is a negative number, the scaled vector will point in the opposite direction.

#####[Length](./Front matter.md)

A vector’s length is obtained from Pythagoras’ theorem. Imagine a right-angle triangle with one side of length ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) and the other side of length ![v_y](./images/6f1ce966448346cbc28c3277a48ccbc1483c0f8c.png); the length of the vector is equal to the length of the triangle’s hypotenuse:

![\|\vec{v}\|^2  = v_x^2 + v_y^2 
\qquad\Rightarrow\qquad
\|\vec{v}\|  = \sqrt{ v_x^2 + v_y^2 }\,.](./images/b314f68e3e35ee853643c87e043f4d7d342fd4b3.png)

A common technique is to scale a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) by one over its length ![\frac{1}{ \|\vec{v}\|}](./images/da0d3c628f5cbdec2004347eeb2b8157c0b2b1d5.png) to obtain a unit vector that points in the same direction as ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png):

![\hat{v} = \frac{\vec{v}}{ \|\vec{v}\| }=\left( \frac{v_x}{ \|\vec{v}\| }, \frac{v_y}{ \|\vec{v}\| } \right)\!.](./images/03e2b7d0290a99214a183569ae66635803417632.png)

Unit vectors (denoted with a hat instead of an arrow) are useful when you want to describe only a direction in space without any specific length in mind. Verify that ![\|\hat{v}\|=1](./images/4edfed1d4c26632afef6d8630a151e959091144a.png).

###[Vector as arrows](./Front matter.md)

So far, we described how to perform algebraic operations on vectors in terms of their components. Vector operations can also be interpreted geometrically, as operations on arrows in the Cartesian plane.

#####[Vector addition](./Front matter.md)

The sum of two vectors corresponds to the combined displacement of the two vectors.[Figure 1.49](./Chapter 1_ Math fundamentals.md) illustrates the addition of two vectors, ![\vec{v}_1=(3,0)](./images/577348f0e379b008a7e644eaad19713603c94d66.png) and ![\vec{v}_2=(2,2)](./images/32f2cccf97ac5b08a5225abbe7dfd8147707cec0.png). The sum of the two vectors is the vector ![\vec{v}_1+\vec{v}_2=(3,0)+(2,2)=(5,2)](./images/f185486e3095335d542c05734081ec1271e43195.png).

![vector_addition](./images/vector_addition.png)

Figure 1.49: The addition of the vectors ![\vec{v}_1](./images/d33646fb26ad9d3975a25ad3c85c11f594226bce.png) and ![\vec{v}_2](./images/65b10c95bdff2bcc3058df8e5d95333772f5523c.png) produces the vector ![(5,2)](./images/a5bfc02b219e534129968c830e26c3b110132717.png).

#####[Vector subtraction](./Front matter.md)

Before we describe vector subtraction, note that multiplying a vector by a scale factor ![\alpha=-1](./images/c9ea067c78520f1c1bff91c26b14e651b55bf8b9.png) gives a vector of the same length as the original, but pointing in the opposite direction.

This fact is useful if you want to subtract two vectors using the graphical approach. Subtracting a vector is the same as adding the negative of the vector:

![\vec{w} - \vec{v}_1
= \vec{w} + (- \vec{v}_1)
=  \vec{v}_2.](./images/fdf4c756dbc952c95b4acafa16b4b32dc83e633c.png)

![vector_subtraction](./images/vector_subtraction.png)

Figure 1.50: The vector subtraction ![\vec{w} - \vec{v}_1](./images/0f9872cfaa7363d49c6d71aa37f826f08e23a358.png) is equivalent to the vector addition ![\vec{w} + (-\vec{v}_1)](./images/3b2dc88eae5fb0b9a9a0db4006bb3fa2acecaa3b.png), where ![(-\vec{v}_1)](./images/b14efbf4e003b5969b719908bc056c9b12ebd1c9.png) is like ![\vec{v}_1](./images/d33646fb26ad9d3975a25ad3c85c11f594226bce.png) but points in the opposite direction.

[Figure 1.50](./Chapter 1_ Math fundamentals.md) illustrates the graphical procedure for subtracting the vector ![\vec{v}_1=(3,0)](./images/577348f0e379b008a7e644eaad19713603c94d66.png) from the vector ![\vec{w}=(5,2)](./images/753b90a54a9a7a91875d573ca61c470601e96a80.png). Subtraction of ![\vec{v}_1=(3,0)](./images/577348f0e379b008a7e644eaad19713603c94d66.png) is the same as addition of ![-\vec{v}_1=(-3,0)](./images/736443142868b3df4146c959448ba80b213cfe2e.png).

#####[Scaling](./Front matter.md)

The scaling operation acts to change the length of a vector. Suppose we want to obtain a vector in the same direction as the vector ![\vec{v}=(3,2)](./images/fe77600797085587e6baec5f7e6ccc43b1d49b80.png), but half as long. “Half as long” corresponds to a scale factor of ![\alpha = 0.5](./images/460bcf77fe035d2d0a9f2bd923cc9faf42f2b1a9.png). The scaled-down vector is ![\vec{w}=0.5\vec{v}=(1.5,1)](./images/6a2409260e2da03806118c32813f22a1b0502585.png). Conversely, we can think of the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) as being twice as long as the vector ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png).

![vector_scaled_by_point_five](./images/vector_scaled_by_point_five.png)

Figure 1.51: Vectors ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) and ![\vec{w}](./images/8605b88df3c2d74846ee2ea09257899f3d121a33.png) are related by the equation ![\vec{v}=2\vec{w}](./images/e1ba5ebc442e9f8242f119ceaaa105dc235b0a9c.png).

Multiplying a vector by a negative number reverses its direction.

###[Length-and-direction representation](./Front matter.md)

So far, we’ve seen how to represent a vector in terms of its components. There is another way of representing two-dimensional vectors: we can describe the vector ![\vec{v} \in \mathbb{R}^2](./images/e3178de0f13474a865bbadb33a26cc93ba2230b3.png) in terms of its length ![\|\vec{v}\|](./images/8f866786ba2376f2849ed080dcb2433d9371ba0f.png) and its direction ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png)—the angle it makes with the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis. For example, the vector ![(1,1)](./images/87bba4e732e0a9d658e2cbc048e3de70be797554.png) can also be written as ![\sqrt{2}\angle45^{\circ}](./images/eb778a1a7553269e784ef79b8431ce90a59dc663.png) using length-and-direction notation. This length-and-direction notation is useful because it makes it easy to see the “size” of vectors. On the other hand, vector arithmetic operations are much easier to carry out in the component notation. It’s therefore good to know the formulas for converting between the two vector representations.

![polar_coordinates_conversion_for_vector_v](./images/polar_coordinates_conversion_for_vector_v.png)

Figure 1.52: The ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\- and ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png)\-components of a vector with length ![\|\vec{v}\|](./images/5a4f6f609935e5c4003d4907fc1f320a0f25582a.png) in the direction ![\theta](./images/962d17a7e21d58659675e6e02789c85029447dd5.png) are given by ![v_x=\|\vec{v}\|\cos\theta](./images/5a0711e4037c39e091f5b352f0d820364691f4d8.png) and ![v_y=\|\vec{v}\|\sin\theta](./images/8ce1b7bbd43d07bde5b55d6f6fb3fbcfa7381b71.png).

To convert the length-and-direction vector ![\vec{v}=\|\vec{v}\|\angle\theta](./images/32e62fd8c275610b10b0d3067c0a65097aa03684.png) into an ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-component and a ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-component ![(v_x,v_y)](./images/bf08d8f270c5ace12ee18ba92752c926e1cd6f5b.png), use the formulas

![v_x=\|\vec{v}\|\cos\theta  
\quad \textrm{and} \quad 
v_y=\|\vec{v}\|\sin\theta.](./images/a04972078106050cd2abb8bfb587a9110f312bc5.png)

To convert from component notation ![\vec{v}=(v_x,v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png) to length-and-direction ![\|\vec{v}\|\angle\theta](./images/b77607ccac4e718ad4616e60146f7b92ff220142.png), use

![\|\vec{v}\|=\sqrt{v_x^2+v_y^2}\,,
\quad
\theta\! =\!\left\{ \begin{array}{ll}
\!\!\tan^{-1}\!\big(\tfrac{v_y}{v_x}\big)  			&	\textrm{ if } v_x > 0, 					\\
\!\!180^\circ + \tan^{-1}\!\!\big(\tfrac{v_y}{v_x}\big)  	&	\textrm{ if } v_x < 0, 					\\
\!\!90^\circ 					  			&	\textrm{ if } v_x=0 \textrm{ and }  v_y > 0,  	\\
\!\!-90^\circ 					  			&	\textrm{ if } v_x=0 \textrm{ and }  v_y < 0.
\end{array}\right.](./images/4f188403daad4833013205668167dbffa13ce7bb.png)

Finding the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is a little tricky. We must use a different formula for computing ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) depending on the value of ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) and there are four different cases to consider. The basic idea is to use the inverse tangent function ![\tan^{-1}](./images/4c7e0e6f32fbf1ec2542303bff7bb0d31040cb87.png), which is also called ![\arctan](./images/18ad5010bf9adb60b92ef1a2fd9a2fa00fe74a82.png), or `atan` on computer systems. By convention, the function ![\tan^{-1}](./images/4c7e0e6f32fbf1ec2542303bff7bb0d31040cb87.png) returns values between ![-90^\circ](./images/b6d8a62b03bbe8e7b65633536b67c3880ade0254.png) (![-\frac{\pi}{2}](./images/c35b68787b078c66df9a8a6c9796f5e5b3f09fda.png) \[rad\]) and ![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png) (![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png) \[rad\]), which correspond to vectors with a positive ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) component. If the ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) component is negative, we must add ![180^\circ](./images/79177e21de4aca7ef1a1ea67a1e45a189a959c86.png) (![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) \[rad\]) to the output of the inverse-tangent calculation to obtain the correct angle. When ![v_x=0](./images/9273e3024e034bfe9d6630e680680eee0432f79d.png) we can’t compute the fraction ![\frac{v_y}{v_x}](./images/3039e63629ddb1a3fa2baca853f03fd5cfee29dd.png) because we cannot divide by zero, so must handle the cases with ![v_x=0](./images/9273e3024e034bfe9d6630e680680eee0432f79d.png) separately as described above. Computer algebra systems provide the two-input arctangent function `atan2(y,x)` that will correctly compute the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) for any coordinate pair ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png).

###[Unit vector notation](./Front matter.md)

In two dimensions, we can think of a vector ![\vec{v}=(v_x, v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png) as a command to “Go a distance ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) in the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-direction and a distance ![v_y](./images/6f1ce966448346cbc28c3277a48ccbc1483c0f8c.png) in the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-direction.” To write this set of commands more explicitly, we can use multiples of the vectors ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png) and ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png). These are the unit vectors pointing in the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) directions:

![\hat{\imath} = (1,0) \qquad \textrm{and} \qquad \hat{\jmath} = (0,1).](./images/df3e44175c137d2c853251b0f90fa420c98b3f1e.png)

Any number multiplied by ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png) corresponds to a vector with that number in the first coordinate. For example, ![3\hat{\imath}=(3,0)](./images/47a6b7c7bdfdb5a5749cf50d3618181cdb509dbd.png) and ![4\hat{\jmath}=(0,4)](./images/a7e849d2c38bc90bb19018bb2be1a5ef9591c51b.png).

In physics, we tend to perform a lot of numerical calculations with vectors; to make things easier, we often use unit vector notation:

![v_x \hat{\imath} + v_y\hat{\jmath}
\qquad \Leftrightarrow \qquad
(v_x, v_y).](./images/86a4e5e2afaf7e46ca3a496260456e3fc79f4dd6.png)

The addition rule remains the same for the new notation:

![\underbrace{2\hat{\imath}+ 3\hat{\jmath}}_{\vec{v}} \; \; + \; \;  \underbrace{ 5\hat{\imath} - 2\hat{\jmath}}_{\vec{w}}
\; = \;
\underbrace{  7\hat{\imath} + 1\hat{\jmath} }_{\vec{v}+\vec{w}}.](./images/0a4d6c45b5aa56ac0ae03664432ce022e26b3cb8.png)

It’s the same story repeating all over again: we need to add ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png)s with ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png)s, and ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png)s with ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png)s.

###[Examples](./Front matter.md)

####[Simple example](./Front matter.md)

Compute the sum ![\vec{s}=4\hat{\imath}+5\angle 30^\circ](./images/1f4383a12fb0966916b47720c1bdfbf41a0d24eb.png). Express your answer in the length-and-direction notation.

Since we want to carry out an addition, and since addition is performed in terms of components, our first step is to convert ![5\angle 30^\circ](./images/f25d860c83b6b224e025131d85cec5d032e8d231.png) into component notation: ![5\angle 30^\circ 
= 5\cos 30^\circ\hat{\imath} + 5\sin 30^\circ\hat{\jmath}
= \tfrac{5\sqrt{3}}{2}\hat{\imath}+ \tfrac{5}{2}\hat{\jmath}](./images/7d7c0e91e62dc5868ea2c67edc019f6e1a7e5f18.png). We can now compute the sum:

![\vec{s} \; \; = \; \;
4\hat{\imath}  \; +  \; \tfrac{5\sqrt{3}}{2}\hat{\imath} + \tfrac{5}{2}\hat{\jmath}
\; \; = \; \; 
(4+ \tfrac{5\sqrt{3}}{2})\hat{\imath} + (\tfrac{5}{2})\hat{\jmath}\,.](./images/987fa3ae7dfae07523641b75eac030db008509c8.png)

The ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-component of the sum is ![s_x = (4+ \frac{5\sqrt{3}}{2})](./images/73f5d91750d06ff72ef60c6b4c99764f7f69135a.png) and the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-component of the sum is ![s_y = (\frac{5}{2})](./images/4efb3d46b9a815c58d21319f4058d57802063759.png). To express the answer as a length and a direction, we compute the length ![\|\vec{s}\|= \sqrt{s_x^2 + s_y^2} = 8.697](./images/95073975380a580e7f18111f387fb5c41ef81297.png) and the direction ![\tan^{-1}(s_y/s_x)=16.7^\circ](./images/81f2b4e774b64db267eb51f77423f3a6a48f4083.png). The answer is ![\vec{s}= 8.697\angle 16.7^\circ](./images/b095182b47b85eb97c7e5ec8b47b51ec16d9630c.png).

####[Relative motion example](./Front matter.md)

A boat can reach a top speed of 12 knots in calm seas. Instead of cruising through a calm sea, however, the boat’s crew is trying to sail up the St-Laurence river. The speed of the current is 5 knots.

If the boat travels directly upstream at full throttle 12![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png), then the speed of the boat relative to the shore will be

![12\hat{\imath} - 5 \hat{\imath} = 7\hat{\imath},](./images/c59060d0a41b6f2ed677889567f2a03cefe3d2ab.png)

since we must “deduct” the speed of the current from the speed of the boat relative to the water. See the vector diagram in[Figure 1.53](./Chapter 1_ Math fundamentals.md).

![vectors-boat-in-current-upstream](./images/vectors-boat-in-current-upstream.png)

Figure 1.53: A boat travels with speed ![12](./images/dff6d79bc1867e1686a866fa07b2a9e109f577bf.png) knots against a current of ![5](./images/f2fa057f2254981666da1b26f97fb103f09600a3.png) knots.

If the crew wants to cross the river perpendicular to the current flow, they can use some of the boat’s thrust to counterbalance the current, and the remaining thrust to push across. The situation is illustrated in[Figure 1.54](./Chapter 1_ Math fundamentals.md). In what direction should the boat sail to cross the river? We are looking for the direction of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) the boat should take such that, after adding in the velocity of the current, the boat moves in a straight line between the two banks (in the ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png) direction).

![vectors-boat-in-current](./images/vectors-boat-in-current.png)

Figure 1.54: Part of the boat’s thrust cancels the current.

Let’s analyze the vector diagram. The opposite side of the triangle is parallel to the current flow and has length ![5](./images/0a99a11a8db1514f59b81b2211782467dd4a2e74.png). We take the up-the-river component of the velocity ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) to be equal to ![5\hat{\imath}](./images/9eff0bbaa0e3bc1fdc5038af315574df394bd805.png), so that it cancels exactly the ![-5\hat{\imath}](./images/0604564ceb02a40a85c33aee3072418cb9088554.png) flow of the river. The hypotenuse has length ![12](./images/54f577f0cef96c9c252a77cc3e94bfff64ec11ad.png) since this is the speed of the boat relative to the surface of the water.

From all of this we can answer the question like professionals. You want the angle? Well, we have that ![\frac{\text{opp}}{\text{hyp}} = \frac{5}{12}=\sin(\theta)](./images/96180370787700716d55f4e4038d0fb82f0c8a74.png), where ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is the angle of the boat’s course relative to the straight line between the two banks. We can use the inverse-sin function to solve for the angle:

![\theta = \sin^{-1}\!\left(\tfrac{5}{12} \right) = 24.62^\circ.](./images/4f203375561b91ef427ac497504b9751706cbb33.png)

The across-the-river component of the velocity can be calculated using ![v_y = 12\cos(\theta)=10.91](./images/1feb03da6b8c116ac16e2c6e249fceda61f6b517.png), or from Pythagoras’ theorem if you prefer ![v_y = \sqrt{ \|\vec{v}\|^2 - v_x^2 } = \sqrt{ 12^2 - 5^2 }=10.91](./images/4321f56034bb70ec0b755d220855f4442bfee3e9.png).

###[Discussion](./Front matter.md)

We did a lot of hands-on activities with vectors in this section and skipped over some of the theoretical details. Now that you’ve been exposed to the practical side of vector calculations, it’s worth clarifying certain points that we glossed over.

####[Vectors vs. points](./Front matter.md)

We used the notation ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png) to describe two kinds of math objects: the set of points in the Cartesian plane and the set of vectors in a two-dimensional space. The point ![P=(P_x,P_y)](./images/b2b822ec2101ce7777578420162a777f76eeca7c.png) and the vector ![\vec{v}=(v_x,v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png) are both represented by pairs of real numbers, so we use the notation ![P \in \mathbb{R}^2](./images/a237d38a6caa05839fab54a890d4124cb04b086a.png) and ![\vec{v} \in \mathbb{R}^2](./images/e3178de0f13474a865bbadb33a26cc93ba2230b3.png) to describe them. This means that a pair of numbers ![(3,2) \in \mathbb{R}^2](./images/9b3f02678d23f4fa480e5abbe79e5300d760c640.png) could represent the _coordinates_ of a point, or the _components_ of a vector, depending on the context.

Let’s take a moment to review the definitions of points and vectors and clarify the types of operations we can perform on them:

-   **Space of points ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png)** : the set of points ![P=(P_x,P_y)](./images/b2b822ec2101ce7777578420162a777f76eeca7c.png) corresponds to locations in the Cartesian plane. The point ![P=(P_x,P_y)](./images/b2b822ec2101ce7777578420162a777f76eeca7c.png) corresponds to the geometric instructions: “Starting at the origin ![(0,0)](./images/4467446eac588743b0a225c1f23f0769d34ee1f5.png), move ![P_x](./images/b1a4d23e560b672f17b435aa4557dbd21f156683.png) units along the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis and ![P_y](./images/fd52e5b2410dcbb405180accd08125785090de23.png) units along the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis.” The distance between points ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) is denoted ![d(P,Q)](./images/cbf00d11df1e2c17fcf58032fbd755932b743df8.png).
-   **Vector space ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png)** : the set of vectors ![\vec{v}=(v_x, v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png) describes displacements in the Cartesian plane. The vector ![\vec{v}=(v_x, v_y)](./images/394a91f1c184d49eeba365d316d1cfc0ec89211e.png) corresponds to the instructions: “Starting anywhere, move ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) units along the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis and ![v_y](./images/6f1ce966448346cbc28c3277a48ccbc1483c0f8c.png) units along the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis.” Vectors can be combined and manipulated using the vector algebra operations ![\vec{u}+\vec{v}](./images/3c2311f5d52e6932259fd54b71fc2017a077c2ba.png), ![\vec{u}-\vec{v}](./images/564b261b672e79034ab1b4003fc6e6b57eb808ac.png), ![\alpha\vec{u}](./images/5590c48726c42903e5e58859e3dd7c33b0121b2c.png), ![\vec{u}\cdot\vec{v}](./images/c2c14c66057b2918741cbf6c703fc3f8cce131ee.png), and ![\|\vec{v}\|](./images/8f866786ba2376f2849ed080dcb2433d9371ba0f.png).

Note the geometric instructions for points and vectors are very similar; the only difference is the starting point. The coordinates of a point ![(P_x,P_y)](./images/80ea82bedd25cc57d7a052b222d62d89731f4162.png) specify a _fixed position_ relative to the origin ![(0,0)](./images/4467446eac588743b0a225c1f23f0769d34ee1f5.png), while the components of a vector ![(v_x, v_y)](./images/bf08d8f270c5ace12ee18ba92752c926e1cd6f5b.png) describe a _relative displacement_ that can have any starting point.

Let’s look at some examples of calculations that combine points and vectors. Consider the points ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) in the Cartesian plane, and the displacement vector ![\vec{v}_{\tiny PQ}](./images/620f3b3a46053a371289221c9afc08994572eb52.png) between them. The displacement vector ![\vec{v}_{\tiny PQ}](./images/620f3b3a46053a371289221c9afc08994572eb52.png) gives the “move instructions” for getting from point ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) to point ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) and is defined by the equation:

![\vec{v}_{\tiny PQ} \; =  \;  Q - P.](./images/1279c25770ab87ad39ce204b9113ecee915defa7.png)

This equation says that subtracting two points produces a vector, which make sense if you think about it—the “difference” between two points is a displacement vector.

We can use the displacement vector ![\vec{v}_{\tiny PQ}](./images/620f3b3a46053a371289221c9afc08994572eb52.png) in calculations like this:

![P + \vec{v}_{\tiny PQ} \; = \; P +  (Q - P) \; =  \; Q.](./images/7d90cc7a96beefac4773480b247a985642d72594.png)

In words, this calculation shows that “Starting at the point ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and moving by ![\vec{v}_{\tiny PQ}](./images/620f3b3a46053a371289221c9afc08994572eb52.png) brings us to the point ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png).”

The above equations use addition and subtraction operations between a mix of points and vectors. This is rather unusual: normally we only use operations like “+” and “-” between math objects of the same kind. In this case, we’re allowed to mix points and vectors because they both describe “move instructions” of the same kind.

Let’s keep going. What other useful calculations can we do by combining points and vectors? Suppose we wanted to find the midpoint ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) that lies exactly in the middle between points ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png). We can find the midpoint ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) using the displacement vector ![\vec{v}_{\tiny PQ}](./images/620f3b3a46053a371289221c9afc08994572eb52.png) and some basic vector algebra. If starting from ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and moving by ![\vec{v}_{\tiny PQ}](./images/620f3b3a46053a371289221c9afc08994572eb52.png) brings us all the way to the point ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png), then starting from ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and moving by ![\frac{1}{2}\vec{v}_{\tiny PQ}](./images/2c639ead419f07862e4a2731484b7c3a890bbbe0.png) will bring us to the midpoint: ![M =  P + \tfrac{1}{2}\vec{v}_{\tiny PQ}](./images/97d2949ada659e2a5f2ef25183c82f127f1f37a6.png).

The mathematical bridge between points and vectors allows us to use vector techniques to solve geometry problems. By learning to describe geometric objects like points, lines, and circles using vectors, we can do complicated geometry calculations using simple algebraic manipulations like vector operations. This exemplifies a general pattern in mathematics: applying techniques developed in one domain to solve problems in another domain.

#####[Example](./Front matter.md)

You come to class one day and there’s a surprise quiz that asks you to write the formula for the distance ![d(P,Q)](./images/cbf00d11df1e2c17fcf58032fbd755932b743df8.png) between two points ![P=(P_x,P_y)](./images/b2b822ec2101ce7777578420162a777f76eeca7c.png) and ![Q=(Q_x,Q_y)](./images/10c0e794411fbd0e677b3d1edd5fd30ca64dcfae.png). You don’t remember ever learning about such a formula and feel caught off guard. How can the teacher ask for a formula they haven’t covered in class yet? This seems totally unfair!

After a minute of stressing out, you take a deep breath, come back to your senses, and resolve to give this problem a shot. You start by sketching a coordinate system, placing points ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) in it, and drawing the line that connects the two points. What is the formula that describes the length of this line?

The line from ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) to ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) looks like the hypotenuse of a triangle, which makes you think that trigonometry could somehow be used to find the answer. Unfortunately, trying to remember the trigonometry formulas has only the effect of increasing your math anxiety. You take this as a sign that you should look for other options. In math, it’s important to trust your gut instincts.

By a fortunate coincidence, you were recently reading about the connection between points and vectors, and specifically about the displacement vector ![\vec{v}_{\tiny PQ} = Q - P](./images/1248efc232b2301e58d120307a41bd67cc8b4891.png). The line in your sketch represents the vector ![\vec{v}_{\tiny PQ}](./images/620f3b3a46053a371289221c9afc08994572eb52.png). You realize that the distance between the points ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) and ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) is the same as the length of the vector ![\vec{v}_{\tiny PQ}](./images/620f3b3a46053a371289221c9afc08994572eb52.png). You remember the formula for the length of a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is ![\|\vec{v}\| = \sqrt{ v_x^2 + v_y^2}](./images/66fc48a27e391ea9941907087cd4cf2f61279b72.png) and you know the formula for the displacement vector is ![\vec{v}_{\tiny PQ} = (Q_x-P_x, Q_y-P_y)](./images/26c534cdb637fa8bcad4d4f08b4a78db7c4c54d9.png), so you combine these formulas to obtain the answer: ![d(P,Q) = \left\|\vec{v}_{\tiny PQ}\right\| = \sqrt{ (Q_x-P_x)^2 + (Q_y-P_y)^2 }](./images/f89335bffdc54794ac15fa321f2790c9b72fd93f.png). One more win for the “don’t worry and try it” strategy for solving math problems!

####[Vectors in three dimensions](./Front matter.md)

A three-dimensional coordinate system consists of three axes: the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis, the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis, and the ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-axis. The three axes point in perpendicular directions to each other, as illustrated in[Figure 1.55](./Chapter 1_ Math fundamentals.md). Look around you and find a corner of the room you’re in where two walls and the floor meet. The ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis and the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis are the edges where the floor meets the walls. The vertical edge where the two walls meet represents the ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-axis.

![empty_coordinate_system_3D](./images/empty_coordinate_system_3D.png)

Figure 1.55: A three-dimensional coordinate system with ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png), ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png), and ![z](./images/f55c007144affca7e483671451c5e3aebe5c1aa7.png) axes.

The vector ![\vec{v} = (v_x, v_y, v_z) \in \mathbb{R}^3](./images/846f4bcc7c0555bef131d5c6c7e0589ae501c104.png) describes the following displacement instructions: “Move ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) units in the direction of the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis, then move ![v_y](./images/6f1ce966448346cbc28c3277a48ccbc1483c0f8c.png) along the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-axis, and finally move ![v_z](./images/387cd73c8e889d0c77298fe1a209b9151289faae.png) in the direction of the ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-axis.” In three dimensions, there are three unit vectors that describe unit steps in the direction of each of the axes:

![\hat{\imath} = (1, 0, 0), \qquad
\hat{\jmath} = (0, 1, 0) \quad \textrm{and} \quad \;
\hat{k} = (0, 0, 1).](./images/2a29aabe4341b2ad60815914269a9bc9ac14407a.png)

We can therefore describe the vector ![\vec{v} = (v_x, v_y, v_z)](./images/87c95a73f484d93d31b33d580a161c30cea133fe.png) in terms of unit vectors as ![\vec{v} = v_x \hat{\imath} + v_y \hat{\jmath} + v_z \hat{k}](./images/0bec2684a5977179d57de5bb5e4c906d34f74b97.png).

####[High-dimensional vectors](./Front matter.md)

The most common types of vectors you’ll encounter in math and physics are two-dimensional and three-dimensional vectors. In other fields of science like genetics and machine learning, it’s common to see vectors with many more dimensions. For example, in machine learning we often represent “rich data” like images, videos, and text as vectors with thousands of dimensions.

An example of an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector is

![\vec{v} = (v_1, v_2, \ldots, v_n) \in \mathbb{R}^n.](./images/5068f3d4810380e0f824b1482db1954d5e6eff70.png)

The vector algebra operations you learned in this section also apply to these high-dimensional vectors.

####[Vectors and vector coordinates](./Front matter.md)

One final point we need to clarify is the difference between real-world vector quantities like the velocity of a tennis ball ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and its mathematical representation as a coordinate vector ![(v_x,v_y,v_z)](./images/89f872c82996b86c9b7ed306d9d98fea762b6865.png). If you know the coordinate vector ![(v_x,v_y,v_z)](./images/89f872c82996b86c9b7ed306d9d98fea762b6865.png) then you know what the real-world velocity is, right? Not quite.

Let’s say you’re doing a physics research project on tennis serves. You define an ![xyz](./images/c2d9f4e6406cf03da1990bafc0a0e1883881bfe6.png)\-coordinate system for the tennis court, which allows you to represent the ball’s velocity ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) as a triple of components ![(v_x,v_y,v_z)](./images/89f872c82996b86c9b7ed306d9d98fea762b6865.png) interpreted as: “The ball is moving with velocity ![v_x](./images/844016b916ae72a7f94c1e4b07736fb39764a7ff.png) units in the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-direction, ![v_y](./images/6f1ce966448346cbc28c3277a48ccbc1483c0f8c.png) units in the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-direction, and ![v_z](./images/387cd73c8e889d0c77298fe1a209b9151289faae.png) units in the ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)\-direction.”

Suppose you want to describe the velocity vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) to a fellow physicist via text message. Referring to your sheet of calculations, you find the values ![\vec{v}=(60,3,-2)](./images/ef792d323504022891aabfc5761d5334c9e14901.png), which you know were measured in metres per second. You send this message:

    The velocity is (60,3,-2) measured in metres per second. 

A few minutes later the following reply comes back:

    Wait whaaat? What coordinate system are you using? 

Indeed the information you sent is incomplete. Vector components depend on the coordinate system in which the vectors are represented. The triple of numbers ![(60,3,-2)](./images/8f60f47ee187e5ef6c211c1a891c1c15caa2e70b.png) only makes sense once you know the directions of the axes in the ![xyz](./images/c2d9f4e6406cf03da1990bafc0a0e1883881bfe6.png)\-coordinate system. Realizing your mistake, you send a text with all the required information:

    Using the coordinate system centred at the south post of
    the net, with the x-axis pointing east along the court,
    the y-axis pointing north along the net, and the z-axis
    pointing up, the velocity is (60,3,-2) in metres per second. 

A few seconds later, you get the reply:

    OK got it now. Thx! 

This hypothetical situation illustrates the importance of the coordinate systems for describing vectors. If you don’t know what the coordinate system is, knowing the coordinates ![(v_x,v_y,v_z)](./images/89f872c82996b86c9b7ed306d9d98fea762b6865.png) doesn’t tell you much. Only when you know the directions of the unit vectors ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png), ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png), and ![\hat{k}](./images/1427cff1bf4c402fb2a07d3b871082761b7c2102.png) can you interpret the instructions ![\vec{v} = v_x\hat{\imath}+v_y\hat{\jmath}+v_z\hat{k}](./images/0bec2684a5977179d57de5bb5e4c906d34f74b97.png).

It turns out, using the ![xyz](./images/c2d9f4e6406cf03da1990bafc0a0e1883881bfe6.png)\-coordinate system with the three vectors ![\{\hat{\imath},\hat{\jmath},\hat{k}\}](./images/20a783ec4e2fb4e61cdda060b7be04e1c1bd2022.png) is just one of many possible ways we can represent vectors. We can represent a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) as coordinates ![(v_1,v_2,v_3)](./images/d6f9bedeb9a54107047374f785c25741614d6b4c.png) with respect to any _basis_ ![\{ \hat{e}_1, \hat{e}_2, \hat{e}_3 \}](./images/c2bcd6a22c91fbce431e53813ab74cdf932e39ff.png) using the expression ![\vec{v} = v_1\hat{e}_1 + v_2\hat{e}_2 +  v_3\hat{e}_3](./images/cd57d30dc5e6475fb6c68800db6324da0f01071d.png), which corresponds to the instructions: “Move ![v_1](./images/26bb4de90d49b42600706cf2e962fbcf50141c0c.png) units in the direction of ![\hat{e}_1](./images/6918c3bc61ee2edc463842c5b586359c71047541.png), move ![v_2](./images/b8ca706d019569604aca5b0c8b702542f0fd8e6b.png) units in the direction of ![\hat{e}_2](./images/4a63957434b4c53e36baba2d6b8fe95b725bd6e2.png), and move ![v_3](./images/bfc4eadd653f02c4089f3359b55ced531eb69354.png) units in the direction of ![\hat{e}_3](./images/66f4b3ad9a951309553970e4674d8b4e64b5f1aa.png).”

What’s a basis, you ask? I’m glad you asked, because this is the subject of the next section.

###[Basis](./Front matter.md)

One of the most important concepts in the study of vectors is the concept of a _basis_. Consider the three-dimensional vector space ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png). A _basis_ for ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) is a set of vectors ![\{ \hat{e}_1, \hat{e}_2, \hat{e}_3 \}](./images/c2bcd6a22c91fbce431e53813ab74cdf932e39ff.png) that can be used as a coordinate system for ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png). If the set of vectors ![\{ \hat{e}_1, \hat{e}_2, \hat{e}_3 \}](./images/c2bcd6a22c91fbce431e53813ab74cdf932e39ff.png) is a basis, then you can _represent_ any vector ![\vec{v} \in \mathbb{R}^3](./images/7d4d76835dd377bbd6d7248bd9e3aa55aa35fdfa.png) as coordinates ![(v_1,v_2,v_3)](./images/d6f9bedeb9a54107047374f785c25741614d6b4c.png) _with respect to_ that basis:

![\vec{v} =  v_1\hat{e}_1 + v_2\hat{e}_2 + v_3\hat{e}_3.](./images/ac168cc1711533799458e5b61df62c14da44c42d.png)

The vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is obtained by measuring out a distance ![v_1](./images/26bb4de90d49b42600706cf2e962fbcf50141c0c.png) in the ![\hat{e}_1](./images/6918c3bc61ee2edc463842c5b586359c71047541.png) direction, a distance ![v_2](./images/b8ca706d019569604aca5b0c8b702542f0fd8e6b.png) in the ![\hat{e}_2](./images/4a63957434b4c53e36baba2d6b8fe95b725bd6e2.png) direction, and a distance ![v_3](./images/bfc4eadd653f02c4089f3359b55ced531eb69354.png) in the ![\hat{e}_3](./images/66f4b3ad9a951309553970e4674d8b4e64b5f1aa.png) direction.

You are already familiar with the _standard_ basis ![\{ \hat{\imath}, \hat{\jmath}, \hat{k} \}](./images/20a783ec4e2fb4e61cdda060b7be04e1c1bd2022.png), which is associated with the ![xyz](./images/c2d9f4e6406cf03da1990bafc0a0e1883881bfe6.png)\-coordinate system. You know that any vector ![\vec{v} \in \mathbb{R}^3](./images/7d4d76835dd377bbd6d7248bd9e3aa55aa35fdfa.png) can be expressed as a triple ![(v_x,v_y,v_z)](./images/89f872c82996b86c9b7ed306d9d98fea762b6865.png) with respect to the basis ![\{ \hat{\imath}, \hat{\jmath}, \hat{k} \}](./images/20a783ec4e2fb4e61cdda060b7be04e1c1bd2022.png) through the formula ![\vec{v}=v_x\hat{\imath}+v_y\hat{\jmath}+v_z\hat{k}](./images/0bec2684a5977179d57de5bb5e4c906d34f74b97.png). The whole point of this section is to let you know that other bases (coordinate systems) exist, and to get you into the habit of asking, “With respect to which coordinate system?” every time you see a coordinate vector ![(a,b,c)](./images/8d7dd5f859ad481699cbc2ebf240709d1f684f5b.png).

####[An analogy](./Front matter.md)

Let’s start with a simple example of a basis. If you look at the HTML source code behind any web page, you’re sure to find at least one mention of the colour stylesheet directive such as `color:#336699;`. The numbers should be interpreted as a triple of values ![(33,66,99)](./images/934c41d26d508f49acc4f19eec680567e5de903a.png), each value describing the amount of red, green, and blue needed to create a given colour. Let us call the colour described by the triple ![(33,66,99)](./images/934c41d26d508f49acc4f19eec680567e5de903a.png) CoolBlue. This convention for colour representation is called the RGB colour model and we can think of it as the _RGB basis_. A basis is a set of elements that can be combined together to express something more complicated. In our case, the **R**, **G**, and **B** elements are pure colours that can create any colour when mixed appropriately. Schematically, we can write this mixing idea as

![{\rm CoolBlue} = (33,66,99)_{RGB}=33{\mathbf R}+66{\mathbf G}+99{\mathbf B},](./images/826d654f4ffad3b58f5a5f8bf7bd672f95070090.png)

where the _components_ determine the strength of each colour. To create the colour, we combine its components as symbolized by the ![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png) operation.

The cyan, magenta, and yellow (CMY) colour model is another basis for representing colours. To express the “cool blue” colour in the CMY basis, you will need the following components:

![(33,66,99)_{RGB} = {\rm CoolBlue}  = (222,189,156)_{CMY} = 222{\mathbf C}+189{\mathbf M}+156{\mathbf Y}.](./images/368ba39a37df695721c34903ab7b1e9099f30d7a.png)

The _same_ colour CoolBlue is represented by a _different_ set of components when the CMY colour basis is used.

Note that a triple of components by itself doesn’t mean anything unless we know the basis being used. For example, if we were to interpret the triple of components ![(33,66,99)](./images/934c41d26d508f49acc4f19eec680567e5de903a.png) with respect to the CMY basis, we would obtain a completely different colour, which would not be cool at all. A basis is required to convert mathematical objects like the triple ![(a,b,c)](./images/8d7dd5f859ad481699cbc2ebf240709d1f684f5b.png) into real-world ideas like colours. As exemplified above, to avoid any ambiguity we can use a subscript after the bracket to indicate the basis associated with each triple of components. Writing ![(222,189,156)_{CMY}](./images/241155b9b051450a7ee47070f994d535d51c3d24.png) and ![(33,66,99)_{RGB}](./images/513e31e489597a883f7443695fa9473808c45a65.png) clarifies which basis to use for each triple of components.

####[Discussion](./Front matter.md)

It would be hard to over-emphasize the importance of the basis—the coordinate system you use to describe vectors. The choice of coordinate system is the bridge between real-world vector quantities and their mathematical representation in terms of components. Every time you start a new problem that involves vector calculations, the first thing you should do is choose the coordinate system you want to use, and indicate it clearly in the diagram.

Using a non-standard coordinate system can sometimes simplify the equations you have to solve. For example, let’s say we want to study the motion of a block sliding down an incline with velocity ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), as illustrated in[Figure 1.56](./Chapter 1_ Math fundamentals.md). Using the standard ![xy](./images/3133f7b53d3e887d709125d519e1caea5b0c303b.png)\-basis, the velocity vector is represented as ![(v\cos\theta,-v\sin\theta)_{xy}](./images/280999d7041e31370c719d93661f862cb8ea1a89.png), which has components in both the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\- and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-directions and requires using trigonometric functions. If instead you use the non-standard ![x'y'](./images/c22e08ee1aa98623565180ec599ce8719ae234ae.png)\-basis, the components of the velocity will be ![(v,0)_{x'y'}](./images/529f815cc6fb562e855aa41b38e28b7d8c964c52.png). Note the velocity only has a component along the ![x'](./images/a586d5136004ea7453b41817f14e8cc4a0e27a75.png)\-direction, which will simplify all subsequent calculations.

![rotated_coordinate_system](./images/rotated_coordinate_system.png)

Figure 1.56: The vector ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) is described by the coordinates ![(v\cos\theta,-v\sin\theta)_{xy}](./images/047542d77ea48ae8a3f1f8ce36dea6c65f29bb24.png) with respect to the standard basis ![xy](./images/e819445128c475992b46e256b3c37c0307f3d821.png). The same vector ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) is described by the coordinates ![(v,0)_{x'y'}](./images/2a3fedcbed460b54154d164205ee401708734a39.png) with respect to the “tilted” basis ![x'y'](./images/7d60d063038d5fdb7e3f2a7ad08cdeeb0e3ed697.png).

###[Links](./Front matter.md)

\[ Vectors and vector operations explained by 3Blue1Brown \]

[https://www.youtube.com/watch?v=fNkzzaMoSs](./watch_v=fNk_zzaMoSs.md)

\[ More vector illustrations and definitions from Wikipedia \]

[https://en.wikipedia.org/wiki/Euclideanvector](./Euclidean_vector.md)

###[Exercises](./Front matter.md)

E1.20 Given the vectors ![\vec{v}_1=(2,1)](./images/2579a293f1b4c261020c7cfd24d5cb02d30540b4.png), ![\vec{v}_2=(2,-1)](./images/84fe8ac74806a6285b943241ebb7e9f8a184492a.png), and ![\vec{v}_3=(3,3)](./images/47f8fe3302128c21f2211bbb3b761269d9e570e0.png), calculate the following expressions:

**a)** ![\vec{v}_1 + \vec{v}_2](./images/beddba16aa0ca2f0afbdbefc0810e974a59eecc1.png) **b)** ![\vec{v}_2 - 2\vec{v}_1](./images/19662bfefc7c3990321f52f0e23d8319d584b500.png) **c)** ![\vec{v}_1 + \vec{v}_2 + \vec{v}_3](./images/38d3fb87784f331022fb0788025a70cae6d3d35c.png)

E1.21 Express the following vectors as components:

**a)** ![\vec{v}_1 =10\angle30^\circ](./images/a4d628ce9dc0c17f3e0fceb24fa2cf1d6fcb5417.png) **b)** ![\vec{v}_2 = 12\angle\!-\!90^\circ](./images/c755c0d807c1daf8ad4b2bea356904c6a279d501.png) **c)** ![\vec{v}_3 = 3\angle170^\circ](./images/0548d263f60b6c7b7b21ead76d1b7deb70a6be51.png)

E1.22 Express the following vectors in length-and-direction notation:

**a)** ![\vec{u}_1 = (4,0)](./images/c8ddd3724d59a5fbd7b4cdb4407fd95110174b5b.png) **b)** ![\vec{u}_2 = (1,1)](./images/aa79525c2fb7946c671f09020444600469101222.png) **c)** ![\vec{u}_3 = (-1,3)](./images/d47a00d3b35445563fb7b55a44c6faf9c1d52d3c.png)

##[1.14 Complex numbers](./Chapter 1_ Math fundamentals.md)

By now, you’ve heard about complex numbers ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png). The word “complex” is an intimidating word. Surely it must be a complex task to learn about the complex numbers. That may be true in general, but it helps if you know about vectors. Complex numbers are similar to two-dimensional vectors ![\vec{v} \in \mathbb{R}^2](./images/e3178de0f13474a865bbadb33a26cc93ba2230b3.png). We add and subtract complex numbers like vectors. Complex numbers also have components, length, and “direction.” If you understand vectors, you will understand complex numbers at almost no additional mental cost.

We’ll begin with a practical problem.

####[Example](./Front matter.md)

Suppose you’re asked to solve the following quadratic equation:

![x^2 + 1 = 0.](./images/0ad8423907b49ac90579cbdee921836c1cf45c7a.png)

You’re looking for a number ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), such that ![x^2=-1](./images/1727824eaf351623c48db4fa98a83097fe3899af.png). If you are only allowed to give real answers (the set of real numbers is denoted ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png)), then there is no answer to this question. In other words, this equation has no solutions. Graphically speaking, this is because the quadratic function ![f(x)=x^2 + 1](./images/a5f10eaeef61b455f8c6ebdaab32e14349db34ca.png) does not cross the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis.

However, we’re not taking no for an answer! If we insist on solving for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the equation ![x^2 + 1 = 0](./images/4e54898086e08377bc8b88c9429255d0d402493f.png), we can imagine a new number ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) that satisfies ![i^2=-1](./images/8f6a05a5a173cf1a23631e03a53b0a172a46ad47.png). We call ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) the unit imaginary number. The solutions to the equation are therefore ![x_1=i](./images/92334357b74bf83c70f164d8869a74a17fec05a5.png) and ![x_2=-i](./images/41981ca21acbbc06cd20a9cfb97050c2415855df.png). There are two solutions because the equation is quadratic. We can check that ![i^2 + 1 = -1 +1 = 0](./images/ca9a10a35196ac2da26e8fcad0b3bcd95fabe96f.png) and also ![(-i)^2 +1 = (-1)^2i^2 + 1 = i^2 +1 = 0](./images/96898d81ec6fa66296be0344b3485292f21c6f78.png).

Thus, while the equation ![x^2 + 1=0](./images/4e54898086e08377bc8b88c9429255d0d402493f.png) has no real solutions, it _does_ have solutions if we allow the answers to be imaginary numbers.

###[Definitions](./Front matter.md)

Complex numbers have a real part and an imaginary part:

-   ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png): the unit imaginary number ![i = \sqrt{-1}](./images/5ed82d597f14e08c1179a4d111111d566b6f2211.png) or ![i^2 = -1](./images/8f6a05a5a173cf1a23631e03a53b0a172a46ad47.png)
-   ![bi](./images/a257bb31b81ab979092c365a232fe2c4299e077b.png): an imaginary number that is equal to ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) times ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)
-   ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png): the set of real numbers
-   ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png): the set of complex numbers ![\mathbb{C} = \{ a + bi \;  | \;  a,b \in \mathbb{R} \}](./images/bab8ac9a1b7564978e7b048685457da2993909e3.png)
-   ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png): a complex number
    -   ![\textrm{Re}\{ z \}=a](./images/8b547f862cc767345407ed8c9d15d7cfcb040df6.png): the real part of ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)
    -   ![\textrm{Im}\{ z \}=b](./images/f4a43c5803f6b41ac5012e4f5528ec4708e9a5de.png): the imaginary part of ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png)
-   ![\overline{z}](./images/4d0c81dad43b59bde68acab0e73db28d9cd30db1.png): the _complex conjugate_ of ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png). If ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png), then ![\overline{z}=a-bi](./images/5f7e626aa098fb8021f6523d683f1bcf7468ec57.png).

The polar representation of complex numbers:

-   ![z= |z|\angle \varphi_z= |z|\cos\varphi_z + i|z|\sin\varphi_z](./images/6e14735f8756cc694a2cd79b1a2d891e5d879573.png)
-   ![|z|=\sqrt{ \overline{z}z }=\sqrt{a^2+b^2}](./images/afcb5e9b1dbf33e480d82a7090c16166c1557e83.png): the _magnitude_ of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)
-   ![\varphi_z=\tan^{-1}(b/a)](./images/9b52f1f96c094bbbcf3ed3b5754f991e735cf9e2.png): the _phase_ or _argument_ of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)
-   ![\textrm{Re}\{ z \} = |z|\cos \varphi_z](./images/e9128a5c8f59161a2556dd1064a962be4b674d6f.png)
-   ![\textrm{Im}\{ z \} = |z|\sin \varphi_z](./images/c0e98a03a609dc9c92e343e692dc716d5cb34811.png)

###[Formulas](./Front matter.md)

####[Addition and subtraction](./Front matter.md)

Just as we performed the addition of vectors component by component, we perform addition on complex numbers by adding the real parts together and adding the imaginary parts together:

![(a+bi) + (c+di) = (a+c) + (b+d)i.](./images/ef49c3e0a635a846549e32eb4c64edaef62ecd23.png)

####[Polar representation](./Front matter.md)

We can give a geometric interpretation of the complex numbers by extending the real number line into a two-dimensional plane called the _complex plane_. The horizontal axis in the complex plane measures the _real_ part of the number. The vertical axis measures the _imaginary_ part. Complex numbers are points in the complex plane.

![complex_number](./images/complex_number.png)

Figure 1.57: The complex number ![z=a+bi](./images/6726fa2b9973563448763762b7417c468e90cea1.png) corresponds to the point with coordinates ![(a,b)](./images/1c48cd23174e0c88d85ebf6f75fd48baa63f05cf.png) in the complex plane.

It is possible to represent any complex number ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png) in terms of its _magnitude_ and its _phase_:

![z= |z|\angle \varphi_z = \underbrace{|z|\cos\varphi_z}_a + \underbrace{|z|\sin\varphi_z}_bi.](./images/d8af77ecd07012e3af36d5fbc49f3172c89d4890.png)

The _magnitude_ (or _absolute value_) of a complex number ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png) is

![|z|=\sqrt{a^2+b^2}.](./images/710a591731794938e947f5a77a80febc4d54b7e9.png)

This corresponds to the _length_ of the vector that represents the complex number in the complex plane. The formula is obtained by using Pythagoras’ theorem.

The _phase_, also known as the _argument_ of the complex number ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png) is given by the formula

![\varphi_z	= \arg z =  \texttt{atan2(}b\texttt{,}a\texttt{)} = 
\left\{ \begin{array}{ll}
\!\!\tan^{-1}\!\big(\tfrac{b}{a}\big)  		&	\textrm{ if } a > 0, 					\\
\!\! \pi + \tan^{-1}\!\!\big(\tfrac{b}{a}\big)  	&	\textrm{ if } a < 0, 					\\
\!\! \frac{\pi}{2}				  		&	\textrm{ if } a=0 \textrm{ and }  b > 0, 	\\
\!\!-\frac{\pi}{2}				  		&	\textrm{ if } a=0 \textrm{ and }  b < 0.
\end{array}\right.](./images/ffa66d07d3467ee311ef6e2474b26f25a6010ba4.png)

The phase corresponds to the angle that ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png) forms with the real axis.

We previously saw this complicated-looking formula with four cases when we talked about vectors [Section 1.13](./Chapter 1_ Math fundamentals.md)). When a certain formula comes up two times in a math book, this should tell you the author _really_ wants you to know it. Seriously, do me a favour and revisit the exercise [1.13.10](./Chapter 1_ Math fundamentals.md) (page 1.13.10).

Computer algebra systems provide the two-input inverse tangent function `atan2`, which is the easiest way to calculate the phase ![\varphi_z](./images/17d1dc797cc9c260fa1f3b8cc9bf89329cb06ec6.png) for the complex number ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png). The function `atan2` handles all four cases automatically and always computes the correct phase ![\varphi_z](./images/17d1dc797cc9c260fa1f3b8cc9bf89329cb06ec6.png). Try doing some calculations with `atan2` using the computer algebra systems at  [https://live.sympy.org](./live.sympy.org.md).

In addition to the vector-like operations we can perform on complex numbers, like computing their magnitude and phase, we can also perform other operations on complex numbers that are not defined for vectors. The set of complex numbers ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png) is a _field_. This means, in addition to the addition and subtraction operations, we can also perform multiplication and division with complex numbers.

####[Multiplication](./Front matter.md)

The product of two complex numbers is computed using the usual rules of algebra:

![\begin{align*}
(a+bi)(c+di)	&= a(c+di) + bi(c+di)			\\
&= ac+adi + bci + bdi^2		\\
&= (ac - bd) + (ad + bc)i.
\end{align*}](./images/09f96ce4574c2db057371b29777cbc5ed2888ee3.png)

In the polar representation, the product formula is

![(p\angle \phi)(q\angle \psi) = pq \angle (\phi + \psi).](./images/4b5a81fc75ff1d8d2f597858e2336ac65456ed2b.png)

To multiply two complex numbers, multiply their magnitudes and add their phases.

#####[Example](./Front matter.md)

Verify that ![z \,\overline{z} = a^2+b^2 = |z|^2](./images/d35f31972ea031510362c6e8ef953b18da652e67.png).

####[Division](./Front matter.md)

Let’s look at the procedure for dividing complex numbers:

![\frac{(a+bi)}{(c+di)} 
= \frac{(a+bi)}{(c+di)}\frac{(c-di)}{(c-di)} 
= (a+bi)\frac{(c-di)}{(c^2+d^2)} 
= (a+bi)\frac{\overline{c+di}}{|c+di|^2}.](./images/605c8a4064a066abb6add2fb4b0ef609ff236f3d.png)

In other words, to divide the number ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png) by the complex number ![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png), compute ![\overline{s}](./images/7b91fcb627a4d6aff990b09351e61bf517ae5d90.png) and ![|s|^2=s\overline{s}](./images/90c3db44165877f00d2329e8d561947a9a436508.png) and then use

![z/s = z\frac{ \overline{s} }{ |s|^2 }.](./images/19fdb7a39d941784dc76337444fba8bec04852e9.png)

You can think of ![\displaystyle \frac{ \overline{s} }{ |s|^2 }](./images/1cfd4412a5e452c49bb75a776371f2f824ed2b34.png) as being equivalent to ![s^{-1}](./images/81f3d033ef6aba19136a9a910124ec6e34d5e3cc.png).

#####[Cardano’s example](./Front matter.md)

One of the earliest examples of reasoning involving complex numbers was given by Gerolamo Cardano in his 1545 book _Ars Magna_. Cardano wrote, “If someone says to you, divide 10 into two parts, one of which multiplied into the other shall produce 40, it is evident that this case or question is impossible.” We want to find numbers ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) such that ![x_1+x_2=10](./images/543b4f2217715969ad80d94fd5e48bbef32c8184.png) and ![x_1x_2=40](./images/e81094cf3ec9c6cc44885b3c64513eb5842a91d1.png). This sounds kind of impossible. Or is it?

“Nevertheless,” Cardano said, “we shall solve it in this fashion:

![x_1 = 5 + \sqrt{15}i \; \; \text{and} \; \; x_2 = 5 - \sqrt{15}i.\textrm{''}](./images/b56f02647aaa6a88dbac736f89e2dc4f7b7a4a3e.png)

When you add ![x_1 + x_2](./images/2c8c4931c737852498c4d62878f579b343e84e67.png) you obtain 10. When you multiply the two numbers the answer is

![\begin{align*}
x_1x_2  	&=	\left(5 + \sqrt{15}i\right)\!\left(5 - \sqrt{15}i\right) 						\\
&= 	25 -5\sqrt{15}i + 5\sqrt{15}i -  \sqrt{15}^2i^2 = 25 + 15 =  40.
\end{align*}](./images/e267e1787cc069bc6d978d4a2bcbbdf4fde576ef.png)

Hence ![5 + \sqrt{15}i](./images/e9efefef494c6b4febbcf241ec88dd9d68bb6aaa.png) and ![5 - \sqrt{15}i](./images/89738c38aae6e11a83003f0b2eebb3f49c2f25ff.png) are two numbers whose sum is ![10](./images/fd39ea446d2046417cbd0fc131073609dd557e3d.png) and whose product is 40.

#####[Example 2](./Front matter.md)

Let’s compute the product of ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png) and ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png). The answer is obviously ![-i](./images/ee8a6aa063a41618dec99979ad86e0c2da565792.png), but let’s look at this simple calculation geometrically. The polar representation of the number ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) is ![1\angle\frac{\pi}{2}](./images/810df23009bb632a1a1220151dea6917bb92fcf6.png). Multiplication of any complex number ![z=|z|\angle \varphi_z](./images/94ff577ac351643b122bcb29dd725a785517e766.png) by ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) corresponds to adding ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png) to the phase of the number:

![zi	= (|z|\angle \varphi_z)(1\angle\tfrac{\pi}{2})
=  (|z| \cdot 1)\angle(\varphi_z+\tfrac{\pi}{2})
= |z|\angle(\varphi_z+\tfrac{\pi}{2}).](./images/8b54fa0da8024e0a5fb743c425e8e83535599a27.png)

In other words, multiplication by ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) is equivalent to applying a ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png) (![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png)) counterclockwise rotation in the complex plane. We can therefore interpret the answer ![(-1)(i)=-i](./images/a829024d310a2c9c92c655e3a0cfe40916e9060a.png) as the complex number ![-1=1 \angle \pi](./images/5aa895d2facd21f545ce6f8ab8ac2e29a12b2a85.png) experiencing a ![\frac{\pi}{2}](./images/83ff2a16c638fa216946407554cb54e2b80b64d8.png) rotation to arrive at ![1 \angle(\pi + \tfrac{\pi}{2})=1 \angle \tfrac{3\pi}{2}=-i](./images/9fada86cb55c2791363990cbe7d17dc8fd7a6cb4.png).

#####[Example 3](./Front matter.md)

Find the polar representation of ![z=-3-i](./images/d5f6fa0ece89de5c5ef86a40fc042a9611733da7.png) and compute ![z^{6}](./images/ab4b867e916e08c5f82de399834a30218c94a0ea.png). Let’s denote the polar representation of ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png) by ![z = r \angle \varphi](./images/c13f096db8f3adb3bebda0f0f4eb83d44d989808.png) as shown in[Figure 1.58](./Chapter 1_ Math fundamentals.md). We find ![r=\sqrt{3^2 +1^2}=\sqrt{10}](./images/53ad19a2b65ba52620df2680111bb0e035faaa01.png) and ![\varphi=\tan^{-1}(\frac{1}{3})+\pi=0.322+\pi](./images/c55897a09a44ea1490eb8f68de310c005aff80f1.png). Using the polar representation, we can easily compute ![z^{6}](./images/ab4b867e916e08c5f82de399834a30218c94a0ea.png):

![z^{6} 
= r^{6} \angle (6\varphi)
= (\sqrt{10})^{6} \angle \, 6(0.322+\pi)
= 10^{3} \angle 1.932 + 6\pi
= 10^{3} \angle 1.932.](./images/04e178fa529b7aa71924426205021317342ef25d.png)

Note we can ignore multiples of ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png) in the phase. We thus find the value of ![z^6](./images/ab4b867e916e08c5f82de399834a30218c94a0ea.png) is ![1000\cos(1.932) + 1000\sin(1.932)i=-353.4 +935.5i](./images/f7e9bf059853aae2e70fda8db19e8acd0132982f.png).

![complex_number_example1](./images/complex_number_example1.png)

Figure 1.58: The complex number ![z=3-i](./images/0b1b496d3deb6284ed4d9546d0cce1b9c50ed6c1.png) has magnitude ![r=\sqrt{10}](./images/457a836d0acb596d5846a95cc13f05c0f5e529c1.png) and phase ![\varphi=0.322+\pi=3.463](./images/c57974f32dfaa834531a701285001c0bfc202306.png).

####[Fundamental theorem of algebra](./Front matter.md)

The fundamental theorem of algebra states that any polynomial of degree ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png), ![P(x) = a_nx^n + \cdots + a_2x^2 + a_1x + a_0](./images/0c4fbf6b570e5e5b04d1a48c24d607777bf2d278.png), can be written as

![P(x) = a_n (x - z_1)(x - z_2) \cdots (x-z_n),](./images/dd30fdb01f3e475ff00c964462fac5a4eedbb436.png)

where ![z_i \in \mathbb{C}](./images/7078247f4edd7db72a18806aac15e54a7f33ba27.png) are the polynomial’s roots. In other words, the equation ![P(x)=0](./images/05f2d4d0b3425d7b71735015356ddf4cb1490de5.png) has ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) solutions: the complex numbers ![z_1](./images/1444a218cd82124afaaeee40dc89564dfd07ebc2.png), ![z_2](./images/064b779916d840018713acc29484ac15679e02a0.png), …, ![z_n](./images/d8240bc06c8558eaadd21e4c284e4efb482fdf0f.png). Before today, you might have said the equation ![x^2+1=0](./images/4e54898086e08377bc8b88c9429255d0d402493f.png) has no solutions. Now you know its solutions are the complex numbers ![z_1=i](./images/9b967fe379a9e24c5b61c5fa9a3243848983f8e8.png) and ![z_2=-i](./images/e6c18e22e7e7ee7bebd24910cf44017113e2d28f.png).

The theorem is “fundamental” because it tells us we’ll never need to invent numbers “fancier” than the complex numbers to solve polynomial equations. To understand why this is important, recall that each set of numbers is associated with a different class of equations.[Figure 1.2](./Chapter 1_ Math fundamentals.md) on page 1.2 shows the nested containment structure of the number sets ![\mathbb{N}](./images/bafa4736281babd323c41d9dbdcbc6784e7e82e1.png), ![\mathbb{Z}](./images/3636b0a74fb9602986d02bfdab407ba5c85666a6.png), ![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png), ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png), and ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png). The natural numbers ![\mathbb{N}](./images/bafa4736281babd323c41d9dbdcbc6784e7e82e1.png) appear as solutions of the equation ![m+n=x](./images/5d62667186631922ee267fae5fbdbcfc2e146d75.png), where ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) and ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) are natural numbers (denoted ![m,n \in \mathbb{N}](./images/c37d3c2e41f666891fbf0bfff2439844dc029cc4.png)). The integers ![\mathbb{Z}](./images/3636b0a74fb9602986d02bfdab407ba5c85666a6.png) are the solutions to equations of the form ![x+m=n](./images/293bd952c82c3c0e5cdb40928d642d15bf3cd3cb.png), where ![m,n \in \mathbb{N}](./images/c37d3c2e41f666891fbf0bfff2439844dc029cc4.png). The rational numbers ![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png) are necessary to solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in ![mx=n](./images/5b2d0e1fa3e477dc4349466431c38c348a82038a.png), with ![m,n \in \mathbb{Z}](./images/23caea76dcf39df90e0cfe8857650c96ec0045e8.png). To find the solutions of ![x^2=2](./images/6336e0d5708e4906cd885211e420863ab051b0a9.png), we need the real numbers ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png). And in this section, we learned that the solutions to the equation ![x^2 = -1](./images/1727824eaf351623c48db4fa98a83097fe3899af.png) are complex numbers ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png). At this point you might be wondering if you’re attending some sort of math party, where mathematicians write down complicated equations and—just for the fun of it—invent new sets of numbers to describe the solutions to these equations. Can this process continue indefinitely?

Nope. The party ends with ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png). The fundamental theorem of algebra guarantees that any polynomial equation you could come up with—no matter how complicated it is—has solutions that are complex numbers ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png).

####[Euler’s formula](./Front matter.md)

It turns out the exponential function is related to the functions sine and cosine. Lo and behold, we have _Euler’s formula_:

![e^{i\theta} = \cos \theta + i\sin \theta \,.](./images/261da1fabaad8eed1feb10587860dee4cc608090.png)

Inputting an imaginary number to the exponential function outputs a complex number that contains both ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png) and ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png). Euler’s formula gives us an alternate notation for the polar representation of complex numbers: ![z=|z|\angle\varphi_z = |z|e^{i\varphi_z}](./images/20733f9ac6c9a8df3b6ef9b78756f53b1f84f8aa.png).

If you want to impress your friends with your math knowledge, plug ![\theta=\pi](./images/3409aef1cc99acf633e8d1885c6f2e4f11f633ac.png) into the above equation to find

![e^{i\pi} = \cos(\pi) + i\sin(\pi)= -1,](./images/e37cbb14ca8859334488937319369c3d37b732d9.png)

which can be rearranged to obtain the equation ![e^{i\pi} + 1 = 0](./images/0711a0e71f70d1f3b404de9ac589847f348ae94a.png). The equation ![e^{i\pi} + 1 = 0](./images/0711a0e71f70d1f3b404de9ac589847f348ae94a.png) is called _Euler’s identity_, and it shows a relationship between the five most important numbers in all of mathematics: Euler’s number ![e=2.71828\ldots{}](./images/bb80cbcb5a3693210427b4b1e75f66a6b1aca7d4.png), ![\pi=3.14159\ldots](./images/6b8a6be055a1d2029980be6a719b9c4cc08a6e18.png), the imaginary number ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png), 1, and zero. It’s kind of cool to see all these important numbers reunited in one equation, don’t you agree?

One way to understand the equation ![e^{i\pi} + 1 = 0](./images/0711a0e71f70d1f3b404de9ac589847f348ae94a.png), is to think of ![e^{i\pi}](./images/99c2c91392a5a60f670760c4820e8ee3d8c28c5d.png) as the polar representation of the complex number ![z=1e^{i\pi}=1\angle\pi](./images/20f618891b673b821e12debffff674c937719ec4.png), which is the same as ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) rotated counterclockwise by ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) radians (![180^\circ](./images/79177e21de4aca7ef1a1ea67a1e45a189a959c86.png)) in the complex plane. We know ![e^{i\pi} = 1\angle\pi = -1](./images/7867aeafe9cb1204d8e98f7acb77009e8944fd67.png) and so ![e^{i\pi} + 1 = 0](./images/0711a0e71f70d1f3b404de9ac589847f348ae94a.png).

####[De Moivre’s formula](./Front matter.md)

By replacing ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) in Euler’s formula with ![n\theta](./images/04b55983fdca2fa7498f68ed52da03181388c24c.png), we obtain de Moivre’s formula:

![\left( \cos \theta + i \sin \theta \right)^n = \cos n\theta + i \sin n\theta.](./images/cccaf309c89c769f4f324b5b13aeedf19c65ffb3.png)

De Moivre’s formula makes sense if you think of the complex number ![z=e^{i\theta}=\cos\theta+i\sin\theta](./images/26974977b836c07568319268a0cbc7abd8b6d833.png), raised to the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)th power:

![(\cos \theta + i \sin \theta)^n=z^n = (e^{i\theta})^n = e^{in\theta}=\cos n\theta + i \sin n\theta.](./images/556abea6b7a7d225ccb6e7d57b38160a8ce37a49.png)

Setting ![n=2](./images/d971bde3d9feee0a7e7e3c836b72e5b1c4a541cd.png) in de Moivre’s formula, we can derive the double angle formulas (page 1.12.1.1) as the real and imaginary parts of the following equation:

![(\cos^2 \theta - \sin^2 \theta) + (2\sin \theta \cos \theta )i = \cos(2\theta) + \sin(2\theta)i.](./images/6a7cddeb5b2fc0bff8bb49d64783510860a5a2ff.png)

###[Links](./Front matter.md)

\[ Intuitive proof of the fundamental theorem of algebra \]

[`https://www.youtube.com/watch?v=shEk8sz1oOw`](./watch_v=shEk8sz1oOw.md)

##[1.15 Solving systems of linear equations](./Chapter 1_ Math fundamentals.md)

Solving equations with one unknown—like ![2x + 4 = 7x](./images/e9fa861fe93727918a477b09df9a542275594c5f.png), for instance—requires manipulating both sides of the equation until the unknown variable is _isolated_ on one side. For this instance, we can subtract ![2x](./images/a7b59e2b5d6108cb3e2b951758e65620c41d42ad.png) from both sides of the equation to obtain ![4 = 5x](./images/ad837885d39a126807637cdc31e5ec8f97ee5cdc.png), which simplifies to ![x=\frac{4}{5}](./images/79ac26c529fcf97384c15025ec6d8a760c8de3f9.png).

What about the case when you are given _two_ equations and must solve for _two_ unknowns? For example,

![\begin{align*}
x + 2y     & =  5, \\
3x + 9y    & =  21.
\end{align*}](./images/49245d6663d86006cf9963958d0affa2ebc1ddaf.png)

Can you find values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) that satisfy both equations?

###[Concepts](./Front matter.md)

-   ![x,y](./images/442092a8682a99f8214b59ce8ae6a851ea54a734.png): the two unknowns in the equations
-   ![eq1, eq2](./images/7e14f4ada1add158a82a74cf7a382edcaa43ffea.png): a system of two equations that must be solved _simultaneously_. These equations will look like
    
    ![\begin{align*}
    a_1x + b_1y     & =  c_1, \\
    a_2x + b_2y     & =  c_2,
    \end{align*}](./images/8957a9c7b4afa515a25128cd34999341161f74f2.png)
    
    where ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)s, ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)s, and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png)s are given constants.
    

###[Principles](./Front matter.md)

If you have ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) equations and ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) unknowns, you can solve the equations _simultaneously_ and find the values of the unknowns. There are several different approaches for solving equations simultaneously. We’ll show three of these approaches for the case ![n=2](./images/d971bde3d9feee0a7e7e3c836b72e5b1c4a541cd.png).

###[Solution techniques](./Front matter.md)

When solving for two unknowns in two equations, the best approach is to _eliminate_ one of the variables from the equations. By combining the two equations appropriately, we can simplify the problem to the problem of finding one unknown in one equation.

####[Solving by substitution](./Front matter.md)

We want to solve the following system of equations:

![\begin{align*}
x + 2y	& =  5, \\
3x + 9y	& =  21.   
\end{align*}](./images/49245d6663d86006cf9963958d0affa2ebc1ddaf.png)

We can isolate ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the first equation to obtain

![\begin{align*}
x		& =  5 - 2y, \\
3x + 9y	& =  21.  
\end{align*}](./images/71f20e420e5e2626eae90a4223935b699ce6dd97.png)

Now _substitute_ the expression for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) from the top equation into the bottom equation:

![3(5-2y) + 9y = 21.](./images/48c86e05fd8086abe94a58918188dba91126becb.png)

We just eliminated one of the unknowns by substitution. Continuing, we expand the bracket to find

![15 - 6y +9y =  21, \\](./images/d14e4d93439377b2635368329d571aa06737a01b.png)

or

![3y = 6.](./images/2522ecc55adee1864557519eb92dd291fc73b773.png)

We find ![y=2](./images/2d75ac51aced995d1be9b9479c5c67a96ea74f97.png), but what is ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)? Easy. To solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), plug the value ![y=2](./images/2d75ac51aced995d1be9b9479c5c67a96ea74f97.png) into any of the equations we started from. Using the equation ![x = 5-2y](./images/99e955f72af027f47c9a0d08f9529b40e3128114.png), we find ![x = 5-2(2) = 1](./images/6131dede5dbe9e85cb45445264e0a22437aa0efd.png).

####[Solving by subtraction](./Front matter.md)

Let’s now look at another way to solve the same system of equations:

![\begin{align*}
x + 2y	& =  5, \\
3x + 9y	& =  21.   
\end{align*}](./images/49245d6663d86006cf9963958d0affa2ebc1ddaf.png)

Observe that any equation will remain true if we multiply the whole equation by some constant. For example, we can multiply the first equation by ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) to obtain an equivalent set of equations:

![\begin{align*}
3x + 6y     & =  15, \\
3x + 9y    & =  21.
\end{align*}](./images/f6cb732c3bbb17756e2a1643259b921b9ab10f2d.png)

Why did I pick 3 as the multiplier? By choosing this constant, the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) terms in both equations now have the same coefficient.

Subtracting two true equations yields another true equation. Let’s subtract the top equation from the bottom one:

![\cancel{3x} - \cancel{3x} + 9y - 6y = 21 - 15
\quad \Rightarrow \quad
3y = 6.](./images/0051ed110ecdc79ea5495443287aab3c5c2c96ab.png)

The ![3x](./images/c9753eead44568fc3c65ddef7c2645aeb7bbb447.png) terms cancel. This subtraction eliminates the variable ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) because we multiplied the first equation by ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png). We find ![y=2](./images/2d75ac51aced995d1be9b9479c5c67a96ea74f97.png). To find ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), substitute ![y=2](./images/2d75ac51aced995d1be9b9479c5c67a96ea74f97.png) into one of the original equations:

![x + 2(2) = 5,](./images/5f4b46ebbb32f8d33c5f99c4de9ced0d02a4c5c0.png)

from which we deduce that ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png).

####[Solving by equating](./Front matter.md)

There is a third way to solve the system of equations

![\begin{align*}
x + 2y	& =  5, \\
3x + 9y	& =  21.
\end{align*}](./images/49245d6663d86006cf9963958d0affa2ebc1ddaf.png)

We can isolate ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in both equations by moving all other variables and constants to the right-hand sides of the equations:

![\begin{align*}
x	& =  5 -2y, \\
x	& =  \frac{1}{3}(21 - 9y) = 7 - 3y.
\end{align*}](./images/7423b60a4cf49dd972b0ccb8bf0b016fb5b3b970.png)

Though the variable ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is unknown to us, we know two facts about it: ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is equal to ![5 - 2y](./images/44b8e5e06ca16368d8e3871fb969cf2c38d1c631.png) and ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is equal to ![7 - 3y](./images/8956d28ecc3fab7916169f2e2ed009c664c2f1da.png). Therefore, we can eliminate ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) by equating the right-hand sides of the equations:

![5 - 2y = 7 -3y.](./images/0f754e772b0a82c3152bc6759a5bd20742f59d7d.png)

We solve for ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) by adding ![3y](./images/b723b16c080391d3b3ce67f9139b7d58521476d5.png) to both sides and subtracting ![5](./images/0a99a11a8db1514f59b81b2211782467dd4a2e74.png) from both sides. We find ![y = 2](./images/2d75ac51aced995d1be9b9479c5c67a96ea74f97.png) then plug this value into the equation ![x = 5 - 2y](./images/99e955f72af027f47c9a0d08f9529b40e3128114.png) to find ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). The solutions are ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png) and ![y=2](./images/2d75ac51aced995d1be9b9479c5c67a96ea74f97.png).

###[Discussion](./Front matter.md)

The repeated use of the three algebraic techniques presented in this section will allow you to solve any system of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linear equations in ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) unknowns. Each time you eliminate one variable using a substitution, a subtraction, or an elimination by equating, you’re simplifying the problem to a problem of finding ![(n-1)](./images/ec3b44139e3842466ac8f8d102343c62b3683edb.png) unknowns in a system of ![(n-1)](./images/ec3b44139e3842466ac8f8d102343c62b3683edb.png) equations. In[Chapter 3](./Chapter 3_ Computational linear algebra.md) we’ll develop a more advanced, systematic approach for solving systems of linear equations.

###[Geometric solution](./Front matter.md)

Solving a system of two linear equations in two unknowns can be understood geometrically as finding the point of intersection between two lines in the Cartesian plane. In this section we’ll explore this correspondence between algebra and geometry to develop yet another way of solving systems of linear equations.

The algebraic equation ![ax+by=c](./images/42ee2424cdf16a2480ad7b64bff19712203fcb86.png) containing the unknowns ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) can be interpreted as a _constraint_ equation on the set of possible values for the variables ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png). We can visualize this constraint geometrically by considering the coordinate pairs ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that lie in the Cartesian plane. Recall that every point in the Cartesian plane can be represented as a coordinate pair ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png), where ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) are the coordinates of the point.

[Figure 1.59](./Chapter 1_ Math fundamentals.md) shows the geometrical representation of three equations. The line ![\ell_a](./images/d5ea4d81b18367d15c8688c783ff4cf071778ebd.png) corresponds to the set of points ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that satisfy the equation ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png), the line ![\ell_b](./images/f21116d3f470e0fe92d6edf39169841e4b0ebc22.png) is the set of points ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that satisfy the equation ![y=2](./images/2d75ac51aced995d1be9b9479c5c67a96ea74f97.png), and the line ![\ell_c](./images/b144639dfeb73409f7f6e33428b7293ee4d7da23.png) corresponds to the set of points that satisfy ![x+2y=2](./images/b1c1af2702e28fd1e9f3232b01e6d3beb44dfffb.png).

![systems_of_equations__examples](./images/systems_of_equations__examples.png)

Figure 1.59: Graphical representations of three linear equations.

You can convince yourself that the geometric lines shown in[Figure 1.59](./Chapter 1_ Math fundamentals.md) are equivalent to the algebraic equations by considering individual points ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) in the plane. For example, the points ![(1,0)](./images/d8f32e7b923a10bccdaa68e7141d6158e48cdc1f.png), ![(1,1)](./images/87bba4e732e0a9d658e2cbc048e3de70be797554.png), and ![(1,2)](./images/f733efd97e74ebe8ad97f86e8f959bb6de9fa2a8.png) are all part of the line ![\ell_a](./images/d5ea4d81b18367d15c8688c783ff4cf071778ebd.png) since they satisfy the equation ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png). For the line ![\ell_c](./images/b144639dfeb73409f7f6e33428b7293ee4d7da23.png), you can verify that the line’s ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-intercept ![(2,0)](./images/0dddacefeff5e4a5c8501a5b39528bfe02b6fe43.png) and its ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-intercept ![(0,1)](./images/51dc53e490143c62313d23af4c20f5a4e63d4d20.png) both satisfy the equation ![x+2y=2](./images/b1c1af2702e28fd1e9f3232b01e6d3beb44dfffb.png).

The Cartesian plane as a whole corresponds to the set ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png), which describes all possible pairs of coordinates. To understand the equivalence between the algebraic equation ![ax+by=c](./images/42ee2424cdf16a2480ad7b64bff19712203fcb86.png) and the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) in the Cartesian plane, we can use the following precise math notation:

![\ell : \{ (x,y) \in \mathbb{R}^2 \; | \;  ax+by=c \}.](./images/f7ea0f99d9f03a3091f58808df1f10bd74d828a3.png)

In words, this means that the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) is defined as the subset of the pairs of real numbers ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that satisfy the equation ![ax+by=c](./images/42ee2424cdf16a2480ad7b64bff19712203fcb86.png).[Figure 1.60](./Chapter 1_ Math fundamentals.md) shows the graphical representation of the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png).

You don’t have to take my word for it, though! Think about it and convince yourself that all points on the line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) shown in[Figure 1.60](./Chapter 1_ Math fundamentals.md) satisfy the equation ![ax+by=c](./images/42ee2424cdf16a2480ad7b64bff19712203fcb86.png). For example, you can check that the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-intercept ![(\frac{c}{a},0)](./images/20369783f33ded170e28f9799e6c29bb7d5c04b2.png) and the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-intercept ![(0,\frac{c}{b})](./images/a4baa29b096538989767db763a4c95f46ae19485.png) satisfy the equation ![ax+by=c](./images/42ee2424cdf16a2480ad7b64bff19712203fcb86.png).

![systems_of_equations__ax_by_eq_c](./images/systems_of_equations__ax_by_eq_c.png)

Figure 1.60: Graphical representation of the equation ![ax+by=c](./images/2922f60522f50fee2542df1e9ae91055614c209e.png).

Solving the system of two equations

![\begin{align*}
a_1x + b_1y     & =  c_1, \\
a_2x + b_2y     & =  c_2,
\end{align*}](./images/8957a9c7b4afa515a25128cd34999341161f74f2.png)

corresponds to finding the intersection of the lines ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png) that represent each equation. The pair ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that satisfies both algebraic equations simultaneously is equivalent to the point ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that is the intersection of lines ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png), as illustrated in[Figure 1.61](./Chapter 1_ Math fundamentals.md).

![systems_of_equations__intersection_general](./images/systems_of_equations__intersection_general.png)

Figure 1.61: The point ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png) that lies at the intersection of lines ![\ell_1](./images/2700171b346ab6b4bda6d406dd791123fee92c26.png) and ![\ell_2](./images/d044fe34b7d41f4916ccf967c6bb2bc7e088c762.png).

#####[Example](./Front matter.md)

Let’s see how we can use the geometric interpretation to solve the system of equations

![\begin{align*}
x + 2y	& =  5, \\
3x + 9y	& =  21.
\end{align*}](./images/49245d6663d86006cf9963958d0affa2ebc1ddaf.png)

We’ve already seen three different _algebraic_ techniques for finding the solution to this system of equations; now let’s see a _geometric_ approach for finding the solution. I’m not kidding you, we’re going to solve the exact same system of equations a fourth time!

The first step is to draw the lines that correspond to each of the equations using pen and paper or a graphing calculator. The second step is to find the coordinates of the point where the two lines intersect as shown in[Figure 1.62](./Chapter 1_ Math fundamentals.md). The point ![(1,2)](./images/f733efd97e74ebe8ad97f86e8f959bb6de9fa2a8.png) that lies on both lines ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png) corresponds to the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) values that satisfy both equations simultaneously.

![systems_of_equations__intersection_example](./images/systems_of_equations__intersection_example.png)

Figure 1.62: The line ![\ell_1](./images/2700171b346ab6b4bda6d406dd791123fee92c26.png) with equations ![x + 2y = 5](./images/2d0f3f9f9d012b46c8023ffd6cf6a5243df3035d.png) intersects the line ![\ell_2](./images/d044fe34b7d41f4916ccf967c6bb2bc7e088c762.png) with equation ![3x + 9y =  21](./images/e68edea73d5c9d32d520e73006b7b20c3e526e8d.png) at the point ![(1,2)](./images/ff0ebe362ea8060ceecb21ab65cba42156a1fb54.png).

Visit the webpage at[`www.desmos.com/calculator/exikik615f`](./exikik615f.md) to play with an interactive version of the graphs shown in[Figure 1.62](./Chapter 1_ Math fundamentals.md). Try changing the equations and see how the graphs change.

###[Exercises](./Front matter.md)

E1.23 Plot the lines ![\ell_a](./images/d5ea4d81b18367d15c8688c783ff4cf071778ebd.png), ![\ell_b](./images/f21116d3f470e0fe92d6edf39169841e4b0ebc22.png), and ![\ell_c](./images/b144639dfeb73409f7f6e33428b7293ee4d7da23.png) shown in[Figure 1.59](./Chapter 1_ Math fundamentals.md) (page 1.59) using the[Desmos graphing calculator](./calculator.md). Use the graphical representation of these lines to find: **a)** the intersection of lines ![\ell_c](./images/b144639dfeb73409f7f6e33428b7293ee4d7da23.png) and ![\ell_a](./images/d5ea4d81b18367d15c8688c783ff4cf071778ebd.png), **b)** the intersection of ![\ell_a](./images/d5ea4d81b18367d15c8688c783ff4cf071778ebd.png) and ![\ell_b](./images/f21116d3f470e0fe92d6edf39169841e4b0ebc22.png), and **c)** the intersection of lines ![\ell_b](./images/f21116d3f470e0fe92d6edf39169841e4b0ebc22.png) and ![\ell_c](./images/b144639dfeb73409f7f6e33428b7293ee4d7da23.png).

E1.24 Solve the system of equations simultaneously for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png):

![\begin{align*}
2x + 4y 		&= 16, \\
5x \; - \; y     	&= 7.
\end{align*}](./images/913311f06a401e311e2153634677e94c83cfb741.png)

E1.25 Solve the system of equations for the unknowns ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png):

![\begin{align*}
2x+y-4z 		&= 28, 		\\
x \; + y \, + \; z   	&= 8, 		\\
2x-y-6z 		&= 22.
\end{align*}](./images/1a3ac94d3b1f928cec6f877dc7039dc6996b052f.png)

E1.26 Solve for ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) given the equations ![p+q = 10](./images/c1dc6e7a9ea8296f990b9860ec53ac5ec9a7091c.png) and ![p-q=4](./images/77023c936f38c4e47dbef9ee903f8db197877e08.png).

##[1.16 Set notation](./Chapter 1_ Math fundamentals.md)

A _set_ is the mathematically precise notion for describing a group of objects. You don’t need to know about sets to perform simple math; but more advanced topics require an understanding of what sets are and how to denote set membership, set operations, and set containment relations. This section introduces all the relevant concepts.

###[Definitions](./Front matter.md)

-   _set_: a collection of mathematical objects
-   ![S,T](./images/df7d30a5876859b8b2d8a2c369315bd0a05de403.png): the usual variable names for sets
-   ![s \in S](./images/02f420ef6d8d77045e6d12b4b8461fe14149bb48.png): this statement is read “![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png) is an element of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)” or “![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png) is in ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)”
-   ![\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}](./images/a9e1c62cb85bf4b5fe510bc9b2b97035de5ce1d3.png): some important number sets: the naturals, the integers, the rationals, and the real numbers, respectively.
-   ![\emptyset](./images/938eb1d63c1623b9ef1a1893d533b2ddbd150136.png): the _empty set_ is a set that contains no elements
-   ![\{ \textrm{  .....  } \}](./images/fcd0c4fc7ddc3a3d077713638d30bd5c0bd6d85a.png): the curly brackets are used to define sets, and the expression inside the curly brackets describes the set contents.

Set operations:

-   ![S\cup T](./images/91e63cef4fbd2f287c8131f52cd1076803506832.png): the _union_ of two sets. The union of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) and ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) corresponds to the elements in either ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) or ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png).
-   ![S \cap T](./images/bd0b8e5112de34fa4caabed0273013e5a43a508d.png): the _intersection_ of the two sets. The intersection of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) and ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) corresponds to the elements that are in both ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) and ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png).
-   ![S \setminus T](./images/a7d1a54ac39a5095d67083779d95885a475da6f5.png): _set difference_ or _set minus_. The set difference ![S \setminus T](./images/a7d1a54ac39a5095d67083779d95885a475da6f5.png) corresponds to the elements of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) that are not in ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png).

Set relations:

-   ![\subset](./images/7510dd7840f1a976551de242eb1c540756851d87.png): is a strict subset of
-   ![\subseteq](./images/841f77c050e8b8386a24b9a2913fde53e70dc8d1.png): is a subset of or equal to

Here is a list of special mathematical shorthand symbols and their corresponding meanings:

-   ![\in](./images/2e5332d4dce880ee99aa3ddb6391969885e6c153.png): element of
-   ![\notin](./images/28f488db777d43ab7292eb84c492377e84e2ee7f.png): not an element of
-   ![\forall](./images/2454ab24706a8b1ba8fad496a7e8193bf39d07e1.png): for all
-   ![\exists](./images/bdc29e915f5557007aa7097f7629300209d49d2c.png): there exists
-   ![\nexists](./images/5f4a3680ab9c27039b6926b03d4499a0f2fe5449.png): there doesn’t exist
-   ![|\,](./images/067e689b06f066fa184c60124db37a4f60e1ea63.png): such that

These symbols are used in math proofs because they allow us to express complex mathematical arguments succinctly and precisely.

An _interval_ is a subset of the real line. We denote an interval by specifying its endpoints and surrounding them with either square brackets “![[](./images/8388870dcf992f26b51e9b65a9c0ae8257ac86ac.png)” or round brackets “![(](./images/57d561ecf909904e0dc49eff612d8edac73d8bce.png)” to indicate whether or not the corresponding endpoint is included in the interval.

-   ![[a,b]](../Images/0127303c2247a29e7eb054904ab693237ca4075e.png): the _closed_ interval from ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) to ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png). This corresponds to the set of numbers between ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) on the real line, including the endpoints ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png). ![[a,b] = \{ x\in \mathbb{R}\; | \; a \leq x \leq b \}](../Images/5d8da925651b88012743bcd282b7920d9ddb148a.png).
-   ![(a,b)](./images/98a5efa74a3f363e0ebadc4f086212f0b4a1a3de.png): the _open_ interval from ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) to ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png). This corresponds to the set of numbers between ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) on the real line, _not_ including the endpoints ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png). ![(a,b) = \{ x\in \mathbb{R}\; | \; a < x < b \}](./images/3d4314d10f6f50208e89b6b6dea804c56bbce2a3.png).
-   ![[a,b)](./images/09c48b9eeb5df2269ba7b5c7e24d0914a5785d7f.png): the half-open interval that includes the left endpoint ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) but not the right endpoint ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png). ![[a,b) = \{ x\in \mathbb{R}\; | \; a \leq x < b \}](./images/493477fc140ad7b4912a80cf61c8098e1f85a35d.png).

Sometimes we encounter intervals that consist of two disjointed parts. We use the notation ![[a,b] \cup [c,d]](../Images/7318231c0c5580407630f17e90d4e9e374d53cff.png) to denote the union of the two intervals, which is the set of numbers _either_ between ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) (inclusive) _or_ between ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) and ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png) (inclusive).

###[Sets](./Front matter.md)

Much of math’s power comes from _abstraction_: the ability to see the bigger picture and think _meta_ thoughts about the common relationships between math objects. We can think of individual numbers like ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png), ![-5](./images/bd17dd326ba74f3b82e7dff7a32196f5090e1b7b.png), and ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png), or we can talk about the set of _all_ numbers.

It is often useful to restrict our attention to a specific _subset_ of the numbers as in the following examples.

####[Example 1: The nonnegative real numbers](./Front matter.md)

Define ![\mathbb{R}_+ \subset \mathbb{R}](./images/dc8ec24a27e06b81ea768fc405a20369fb9e1f1d.png) (read “![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png) is a subset of ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png)”) to be the set of nonnegative real numbers:

![\mathbb{R}_+  \eqdef  \{ \text{all } x \text{ in } \mathbb{R} \text{ such that } x \geq 0 \},](./images/1794ef30cd7c65c3183ce4c1e921b80d05c8c825.png)

or expressed more compactly,

![\mathbb{R}_+ \eqdef \{ x \in \mathbb{R} \; | \; x \geq 0 \}.](./images/fc00ed24daaa9aae49dd836335c089a69f1d2249.png)

If we were to translate the above expression into plain English, it would read “The set ![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png) is defined as the set of all real numbers ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) such that ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is greater or equal to zero.”

Note we used the “is defined as” symbol “![\eqdef](./images/2cb557e51c5e620a2a873c7db18d9322bc09397e.png)” instead of the basic “![=](./images/b8ca3693499b05d77b159c39cca4f9b6fd74d54e.png)” to give an extra hint that we’re defining a new variable ![\mathbb{R}_+](./images/b7214c758763207ff6e76a58803e0ecc41620bfa.png) that is equal to the set expression on the right. In this book, we’ll sometimes use the symbol “![\eqdef](./images/2cb557e51c5e620a2a873c7db18d9322bc09397e.png)” when defining new variables and math quantities. Some other books use the notation “![:=](./images/6df265601546e1ac2a25d722d6ef318177bf6dad.png)” or “![\equiv](./images/a930ec6c874158916f3d2dd135aedc1fd38dcbdd.png)” for this purpose. The meaning of “![\eqdef](./images/2cb557e51c5e620a2a873c7db18d9322bc09397e.png)” is identical to “![=](./images/b8ca3693499b05d77b159c39cca4f9b6fd74d54e.png)” but it tells us the variable on the left of the equality is new.

####[Example 2: Even and odd integers](./Front matter.md)

Define the set of even integers as

![E \eqdef \{ m \in \mathbb{Z}  \; | \;  m=2n, \; n \in \mathbb{Z} \} =  \{ \ldots, -4, -2, 0, 2, 4, \ldots \}  \quad](./images/7282a954f4189e52d7590ed7024838078d028290.png)

and the set of odd integers as

![O \eqdef \{ m \in \mathbb{Z}   \; | \;  m=2n+1, \; n \in \mathbb{Z} \} =  \{ \ldots, -3, -1, 1, 3, 5, \ldots \}.](./images/bbc88097189254a4b57604e84d4dc3a74ca3cea0.png)

Indeed, every even number is divisible by two, so it can be written in the form ![2n](./images/3bc1b84c8c2b445e2f6ee68eceb6f94508a78e9e.png) for some integer ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png). Odd numbers can be obtained from the “template” ![2n+1](./images/afb9bd8d4b4018091f9eb1e9ed651e05411f5047.png), with ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) varying over all integers.

In both of the above examples, we use the _set-builder_ notation ![\{\, \ldots \; | \;  \ldots \, \}](./images/c04fd0cafd475679dac142c092a8071b53fccf2f.png) to define the sets. Inside the curly braces we first describe the general kind of mathematical objects we are talking about, followed by the symbol “![|](./images/87e0224147ed550dbca19b1b3c52d6b8482983bc.png)” (read “such that”), followed by the conditions that must be satisfied by all elements of the set.

###[Number sets](./Front matter.md)

Recall the fundamental number sets we defined in[Section 1.2](./Chapter 1_ Math fundamentals.md) in the beginning of the book. It is worthwhile to review them briefly.

The _natural_ numbers form the set derived when you start from ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) and add ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) any number of times:

![\mathbb{N} 	\eqdef 	\{ 0, 1, 2, 3, 4, 5, 6, \ldots \}.](./images/87e9e369dba8944d5a2988e5474d1ee0a7248d4c.png)

We use the notation ![\mathbb{N}^*](./images/f86746cb88e07725d440a60ff78a59da681e9033.png) to denote the set of _positive natural numbers_. The set ![\mathbb{N}^*](./images/f86746cb88e07725d440a60ff78a59da681e9033.png) is the same as ![\mathbb{N}](./images/bafa4736281babd323c41d9dbdcbc6784e7e82e1.png) but excludes zero.

The integers are the numbers derived by adding or subtracting 1 some number of times:

![\mathbb{Z} 	\eqdef 	\{ x \:|\: x= \pm n, n \in \mathbb{N} \}.](./images/a13c40e485d5ce2f9de3569d9a394a75e31497c7.png)

If we allow for divisions between integers, we require the set of rational numbers to represent the results:

![\mathbb{Q} \eqdef	\left\{  \frac{m}{n} \; \Big| \; m \in \mathbb{Z}, \; n \in \mathbb{N}^*  \right\},](./images/1de30070755f8fc5d557956f87c6fc9aeefa6163.png)

In words, this expression is telling us that every rational number can be written as a fraction ![\frac{m}{n}](./images/a63eac226ced841a66c7c3ca10b635f7bd6243c3.png), where ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) is an integer (![m \in \mathbb{Z}](./images/e7fd82c9ddc27978ec73a9191edd6895c8cbd36d.png)), and ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is a positive natural number (![n \in \mathbb{N}^*](./images/3f5f26c911241eeb9ef8f3e33eedbc14f6d9f7b8.png)).

The broader class of real numbers also includes all rationals as well as irrational numbers like ![\sqrt{2}](./images/6715b8265ad0d01e2040fdb8d7b64f78ff347978.png) and ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png):

![\mathbb{R} \eqdef \{\pi, e, -1.53929411\ldots,\;  4.99401940129401\ldots, \; \ldots \}.](./images/ae20d75ada39086ce5308ff9b53a0e3f466a1277.png)

Finally, we have the set of complex numbers:

![\mathbb{C} \eqdef \{ 1, i,  1+i, 2+3i,  \ldots \},](./images/38bf273a8917392f6075d1d98f13863a9bc8a5b2.png)

where ![i \eqdef \sqrt{-1}](./images/a150c889c82f67cc0caa0a50fb9bcf627717e926.png) is the unit imaginary number.

Note that the definitions of ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) and ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png) are not very precise. Rather than give a precise definition of each set inside the curly braces as we did for ![\mathbb{Z}](./images/3636b0a74fb9602986d02bfdab407ba5c85666a6.png) and ![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png), we instead stated some examples of the elements in the set. Mathematicians sometimes do this and expect you to guess the general pattern for all the elements in the set.

The following inclusion relationship holds for the fundamental sets of numbers:

![\mathbb{N} \subset 
\mathbb{Z} \subset 
\mathbb{Q} \subset 
\mathbb{R} \subset 
\mathbb{C}.](./images/8c02c496ec33c2339f328afffa093fdde20873b4.png)

This relationship means every natural number is also an integer. Every integer is a rational number. Every rational number is a real. And every real number is also a complex number. See[Figure 1.2](./Chapter 1_ Math fundamentals.md) (page 1.2) for an illustration of the subset relationship between the number sets.

###[Rational numbers and fractions](./Front matter.md)

So far in this book, we’ve used the notions of “fraction” and “rational number” somewhat interchangeably. Now that we’ve learned about sets, we can clarify the differences and equivalencies between these related concepts.

The same rational number ![\frac{2}{3}](./images/7bec526385ee19c07930ca05efa2d4b9de370b2c.png) can be written as a fraction in multiple, equivalent ways. The fractions ![\frac{2}{3}](./images/7bec526385ee19c07930ca05efa2d4b9de370b2c.png), ![\frac{4}{6}](./images/51268d27bfe49f2e15355ffbfc0b8a3f778acfbe.png), ![\frac{6}{9}](./images/23a6548dd098c868f832ee04438a9a498559317b.png), ![\frac{8}{12}](./images/cf054bb2ab18d925762ef91d9aa268c9143c088b.png), and ![\frac{2k}{3k}](./images/40fc1d2dab3e244508c33ccd3bf342da919ac54c.png) all correspond to the same rational number. Keep in mind the existence of these _equivalent fractions_ whenever checking whether two rational numbers are equal. For example, one person could obtain the answer ![\frac{2}{3}](./images/7bec526385ee19c07930ca05efa2d4b9de370b2c.png) to a given problem, while another person obtains the answer ![\frac{4}{6}](./images/51268d27bfe49f2e15355ffbfc0b8a3f778acfbe.png). Since the two fractions look different, we might think these are different answers, when in fact both answers correspond to the same rational number.

A _reduced fraction_ is a fraction of the form ![\frac{m}{n}](./images/a63eac226ced841a66c7c3ca10b635f7bd6243c3.png) such that the numbers ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) and ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) are the smallest possible. We can obtain the reduced fraction by getting rid of any common factors that appear both in the numerator and denominator. For example,

![\frac{4}{6} = \frac{2\cdot 2}{3 \cdot 2} = \frac{2\cdot \cancel{2}}{3 \cdot \cancel{2} } = \frac{2}{3} \,,](./images/c6843ac1513e990c6af2785f25e951e6318ab579.png)

where we cancelled the common factor ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) to obtain the equivalent reduced fraction. Reduced fractions are a useful representation for the set of rational numbers, because each rational number corresponds to a unique reduced fraction. Two rational numbers are equal if and only if they correspond to the same reduced fraction.

###[Subsets of the real line](./Front matter.md)

Recall that the real numbers ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) have a graphical representation as points on the number line. See[Figure 1.9](./Chapter 1_ Math fundamentals.md) on page 1.9 for a reminder. The number line is also useful for representing various subsets of the real numbers, which we call _intervals_. We can graphically represent an interval by setting a section of the number line in **bold**. For example, the set of numbers that are strictly greater than ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) and strictly smaller than ![4](./images/d642a42f2cf4e1514233d611b91e5d4646202fc8.png) is represented mathematically either as “![(2,4)](./images/9b1040b6ec7a73f8a1a34cd602344458a427853a.png),” or more explicitly as

![\{ x \in \mathbb{R} \;|\;    2 < x < 4 \},](./images/c02fa0a34e8c229d40a5a8d605fa2de9470e52c8.png)

or graphically as in[Figure 1.63](./Chapter 1_ Math fundamentals.md).

![interval_2open_to_4open](./images/interval_2open_to_4open.png)

Figure 1.63: The open interval ![(2,4) = \{ x \in \mathbb{R} \;|\;    2 < x < 4 \}](./images/a59349e0bc69a947b40d508def94337622c316ad.png).

Let’s read the mathematical definition of this set carefully, and try to connect it with the graphical representation. Recall that the symbol ![\in](./images/2e5332d4dce880ee99aa3ddb6391969885e6c153.png) denotes set membership and the vertical bar stands for “such that,” so the whole expression “![\{ x \in \mathbb{R} \;|\;    2 < x < 4 \}](./images/98e06f5f684f0d6103a0abc0fdabc61a83427be8.png)” is read “the set of real numbers ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), such that ![2<x<4](./images/ea300aa31f565ad49933152500e57bf1915d1f89.png).” Indeed this is also the region shown in bold in[Figure 1.63](./Chapter 1_ Math fundamentals.md).

Note that this interval is described by _strict_ inequalities, which means the subset contains ![2.000000001](./images/a4402de94c02ba0d26c2977cf27d7bc47260d5b3.png) and ![3.99999999](./images/28089233cffec515d316499bb8a00597fb77c162.png), but doesn’t contain the endpoints ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) and ![4](./images/d642a42f2cf4e1514233d611b91e5d4646202fc8.png). These _open_ endpoints ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) and ![4](./images/d642a42f2cf4e1514233d611b91e5d4646202fc8.png) are denoted on the number line as empty dots. An empty dot indicates that the endpoint is not included in the set.

We use the _union_ symbol (![\cup](./images/91697a2784b0c0c91152aa400907a9286e8d78ac.png)) to denote subsets of the number line that consist of several parts. For example, the set of numbers that lies _either_ between ![-3](./images/5d5e7190d58650b3f220f1b3c1b6b0dd0a9b6e2e.png) and ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) _or_ between ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) and ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) is written as

![\{ x \in \mathbb{R} \; |\;    -3 \leq x \leq 0 \} 
\; \cup \;
\{ x \in \mathbb{R} \;|\;    1 \leq x \leq 2 \}.](./images/da6838398c42f646032c4c104b7c31fa7db35f1b.png)

![interval_-3_to_0_and_1_to_2_all_closed](./images/interval_-3_to_0_and_1_to_2_all_closed.png)

Figure 1.64: The graphical representation of the set ![[-3,0] \cup [1,2]](../Images/4c30a9349c70900ce717ecb528c987b7d0b2465a.png).

This set is defined by less-than-or-equal inequalities, so the intervals contain their endpoints. These _closed_ endpoints are denoted on the number line with filled-in dots.

###[Set relations](./Front matter.md)

We’ll now introduce a useful graphical representation for set relations and set operations. Although sets are purely mathematical constructs and they have no “shape,” we can draw _Venn diagrams_ to visualize relationships between sets and different subsets.

Consider the notion of a set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) that is strictly contained in another set ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). We write ![B \subset A](./images/125d1426fe587d2e4e948205ac41fc47b4f5a677.png) if ![\,\forall b \in B](./images/c0577fdb37c0ff8f00c6932f7d282aad5e84c997.png), ![b \in A](./images/b8ffad98726529555736311b34ecb808b6fd3787.png) as well. Written in words, ![B \subset A](./images/125d1426fe587d2e4e948205ac41fc47b4f5a677.png) tells us every element of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is also an element of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

![b_subset_a_contained](./images/b_subset_a_contained.png)

Figure 1.65: Venn diagram showing an example of the set relation ![B \subset A](./images/6cff5c277bbd1086ef8249d2392b7d75a245b00e.png). The set ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) is strictly contained in the set ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png).

[Figure 1.65](./Chapter 1_ Math fundamentals.md) shows the picture that mathematicians have in mind when they say, “The set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is contained in the set ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).” The picture helps us visualize this abstract mathematical notion.

Mathematicians use two different symbols to describe set containment, in order to specify either a _strict_ containment relation or a _subset-or-equal_ relation. The two types of containment relations between sets are similar to the _less-than_ (![<](./images/447e1b06dc3a3b38f9247e13194807806e178452.png)) and _less-than-or-equal_ (![\leq](./images/55279c624ae5c44513db6e2e0532df4ae9f06ad6.png)) relations between numbers. A strict containment relation is denoted by the symbol ![\subset](./images/7510dd7840f1a976551de242eb1c540756851d87.png). We write ![B \subset A](./images/125d1426fe587d2e4e948205ac41fc47b4f5a677.png) if and only if every element of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is also an element of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), and there exists at least one element of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) that is not an element of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). Using set notation, the previous sentence is expressed as

![B \subset A
\qquad
\Leftrightarrow
\qquad
\forall b \in B, b \in A \textrm{ and }  \exists a \in A  \textrm{ such that } a \notin B.](./images/0bb4b01d3be7b550b407849dae7e3dc53fb6a428.png)

For example, the expression ![E \subset \mathbb{Z}](./images/de0853a9b006f8844d0a805cbfb4907142a22088.png) shows that the even numbers are a strict subset of the integers. Every even number is an integer, but there exist integers that are not even (the odd numbers). Some mathematicians prefer the more descriptive symbol ![\subsetneq](./images/2f9ecda7a5049cd4ef8462af86a532f6ed19b8bc.png) to describe strict containment relations.

A subset-or-equal relation is denoted ![B \subseteq A](./images/d88f26a6419d37d53c3cd3510cd6c624aaa4fc57.png). In writing ![B \subseteq A](./images/d88f26a6419d37d53c3cd3510cd6c624aaa4fc57.png), a mathematician claims, “Every element of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is also an element of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png),” but makes no claim about the existence of elements that are contained in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) but not in ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). The statement ![B \subset A](./images/125d1426fe587d2e4e948205ac41fc47b4f5a677.png) implies ![B \subseteq A](./images/d88f26a6419d37d53c3cd3510cd6c624aaa4fc57.png); however, ![B \subseteq A](./images/d88f26a6419d37d53c3cd3510cd6c624aaa4fc57.png) does not imply ![B \subset A](./images/125d1426fe587d2e4e948205ac41fc47b4f5a677.png). This is analogous to how ![b < a](./images/c4de45045448ad9535b374371f5fbf77ca5ada2c.png) implies ![b \leq a](./images/7ff17317eb6179c2fb49489064e59865ad89d90e.png), but ![b \leq a](./images/7ff17317eb6179c2fb49489064e59865ad89d90e.png) doesn’t imply ![b < a](./images/c4de45045448ad9535b374371f5fbf77ca5ada2c.png), since ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) could be equal.

###[Set operations](./Front matter.md)

Venn diagrams also help us visualize the subsets obtained from set operations.[Figure 1.66](./Chapter 1_ Math fundamentals.md) illustrates the set union ![A \cup B](./images/f848009bdd92b661fabb60ee31b1eedea54ac015.png), the set intersection ![A \cap B](./images/976995a676d6eaa2988678f07924399775fb87e6.png), and the set difference ![A \setminus B](./images/fcc307a8a212c36de9a1423848211451350b9484.png), for two sets ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

The union ![A \cup B](./images/f848009bdd92b661fabb60ee31b1eedea54ac015.png) describes all elements that are in either set ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) or set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), or both. If ![e \in A \cup B](./images/a60db2a7aee51c05f8e7076ffd36962aa3dc0ff9.png), then ![e \in A](./images/f4a4e0ff9b0f275aa9430842e8e1ba9d55934926.png) or ![e \in B](./images/8c31c2960f7839f2451c44336f043fa33895f0da.png).

Recall the set of even numbers ![E \subset \mathbb{Z}](./images/de0853a9b006f8844d0a805cbfb4907142a22088.png) and the set of odd numbers ![O \subset \mathbb{Z}](./images/e6a7a64f2b5da2477c8918c93b118d4dc0d15c30.png) defined above. Since every integer is either an even number or an odd number, we know ![\mathbb{Z} \subseteq E \cup O](./images/b1970e119cab0e72544524306214b4083572cfc7.png). The union of two subsets is always contained within the parent set, so we also know ![E \cup O \subseteq \mathbb{Z}](./images/e01596b219d0ada1adc995c0eda08ac03194096b.png). Combining these facts, we can establish the equality ![E \cup O = \mathbb{Z}](./images/605bb750cb9f6e03a840f15d37c730ea46cc09ad.png), which states the fact, “The combination of all even and odd numbers is the same as all integers.”

![set_operations_union_intersection_difference](./images/set_operations_union_intersection_difference.png)

Figure 1.66: Venn diagrams showing different subsets obtained using the set operations: set union ![A \cup B](./images/1e427cffba53b0be7b316d27081a964d091984a2.png), set intersection ![A \cap B](./images/e0d51c28fb1bef4efab7d443955d4f794dfa8fcb.png), and set difference ![A \setminus B](./images/47754d1dcdd013d8dc48663cd72719fd34e8b8d7.png).

The set intersection ![A \cap B](./images/976995a676d6eaa2988678f07924399775fb87e6.png) and set difference ![A \setminus B](./images/fcc307a8a212c36de9a1423848211451350b9484.png) are also illustrated in[Figure 1.66](./Chapter 1_ Math fundamentals.md). The intersection of two sets contains the elements that are part of both sets. The set difference ![A \setminus B](./images/fcc307a8a212c36de9a1423848211451350b9484.png) contains all the elements that are in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) but not in ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

Note the meaning of the conjunction “or” in English is ambiguous. The expression “in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) or ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)” could be interpreted as either an “inclusive or,” meaning “in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) or ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), or in both”—or as an “exclusive or,” meaning “in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) or ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), but not both.” Mathematicians always use “or” in the inclusive sense, so ![A \cup B](./images/f848009bdd92b661fabb60ee31b1eedea54ac015.png) denotes elements that are in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) or ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), or in both sets. We can obtain an expression that corresponds to the “exclusive or” of two sets by taking the union of the sets and subtracting their intersection: ![(A \cup B) \setminus (A\cap B)](./images/08c28d113bf0b00c7a0496ec01fe7bcc5415edb5.png).

####[Example 3: Set operations](./Front matter.md)

Consider the three sets ![A=\{a,b,c\}](./images/b707332600b6e3d0d0fbeed311989aa13352f2fc.png), ![B=\{b,c,d\}](./images/481164fc2a458a3e58fb3aebf3b26e03aa0de66f.png), and ![C=\{c,d,e\}](./images/c6f1a7d3e68841da1bdf40a1b1d388fa793f9673.png). Using set operations, we can define new sets, such as

![A \cup B = 	\{a,b,c,d\},
\quad 
A \cap B =  	\{b,c\},
\quad
\textrm{and} 
\quad
A \setminus B =  \{a\},](./images/8ab659405e4c678513064213532142a4e7412525.png)

which correspond to elements in either ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) or ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), the set of elements in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), and the set of elements in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) but not in ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), respectively.

We can also construct expressions involving three sets:

![A \cup B \cup C = \{a,b,c,d,e\},
\qquad
\quad
A \cap B \cap C = \{c\}.](./images/9c195bdb0121b03f5e1627daf51bf00655684b9d.png)

And we can write more elaborate set expressions, like

![(A \cup B ) \setminus C = \{a,b\},](./images/ac896b5a322127eb1a5b0701d8893f7edf3efa6a.png)

which is the set of elements that are in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) or ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) but not in ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png).

Another example of a complicated set expression is

![(A \cap B) \cup (B\cap C) = \{b,c,d\},](./images/fcc9939d5fdc36b784099b4d0f4ea9d73a41d91a.png)

which describes the set of elements in both ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) or in both ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png). As you can see, set notation is a compact, precise language for writing complicated set expressions.

####[Example 4: Word problem](./Front matter.md)

A startup is looking to hire student interns for the summer. Define ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png) to be the subset of students who are good with computers, ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) the subset of students who know math, ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png) the students with design skills, and ![L](./images/8344682567e06566040f4cde165f91b06c4ee6f5.png) the students with good language skills.

Using set notation, we can specify different subsets of the students the startup might hire. Let’s say the startup is a math textbook publisher; they want to hire students from the set ![M \cap L](./images/cb214f991dac9da78441b5e437e8dfe97e26353e.png)—the students who are good at math and who also have good language skills. A startup that builds websites needs both designers and coders, and therefore would choose students from the set ![D \cup C](./images/e7911da8d87de93d0e993c46ce43e224d983698b.png).

###[New vocabulary](./Front matter.md)

The specialized notation used by mathematicians can be difficult to get used to. You must learn how to read symbols like ![\exists](./images/bdc29e915f5557007aa7097f7629300209d49d2c.png), ![\subset](./images/7510dd7840f1a976551de242eb1c540756851d87.png), ![|](./images/87e0224147ed550dbca19b1b3c52d6b8482983bc.png), and ![\in](./images/2e5332d4dce880ee99aa3ddb6391969885e6c153.png) and translate their meaning in the sentence. Indeed, learning advanced mathematics notation is akin to learning a new language.

To help you practice the new vocabulary, we’ll look at a simple mathematical proof that makes use of the new symbols.

####[Simple proof example](./Front matter.md)

**Claim:** Given ![J(n)=3n+2-n](./images/6e3f60a405150eedcd2cdbe087115a613337fedf.png), ![J(n) \in E](./images/71123c3bc5b212da41cfe68bbff56c578875ea80.png) for all ![n \in \mathbb{Z}](./images/6a60974b71b73f667371a22a9ac7786140271f1a.png).

The claim is that the function ![J(n)](./images/9a91395424b29391745140adbd9548e4374afa71.png) outputs an even number, whenever the input ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is an integer. To prove this claim, we have to show that the expression ![3n+2-n](./images/f8b63edc8cc8b78ad1419c16430e67ecce3f57d7.png) is even for all numbers ![n \in \mathbb{Z}](./images/6a60974b71b73f667371a22a9ac7786140271f1a.png).

We want to show ![J(n) \in E](./images/71123c3bc5b212da41cfe68bbff56c578875ea80.png) for all ![n \in \mathbb{Z}](./images/6a60974b71b73f667371a22a9ac7786140271f1a.png). Let’s first review the definition of the set of even numbers ![E \eqdef \{ m \in \mathbb{Z} \; | \; m=2n, n \in \mathbb{Z} \}](./images/69b0f940579121365ef4634a21599790e9366b9e.png). A number is even if it is equal to ![2n](./images/3bc1b84c8c2b445e2f6ee68eceb6f94508a78e9e.png) for some integer ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png). Next let’s simplify the expression for ![J(n)](./images/9a91395424b29391745140adbd9548e4374afa71.png) as follows:

![J(n)=3n+2-n = 2n +2 = 2(n+1).](./images/096812d0eb3599114f63c7174ef761008baa4937.png)

Observe that the number ![(n+1)](./images/1a92a7f301b110623ddd5e73b5c32dda5b55476d.png) is always an integer whenever ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is an integer. Since the output of ![J(n)=2(n+1)](./images/078b1925117c84338ade7a9527ab8c2858305ed9.png) is equal to ![2m](./images/689173da4039c4782280337cd8dc812d77ec375a.png) for some integer ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png), we’ve proven that ![J(n) \in E](./images/71123c3bc5b212da41cfe68bbff56c578875ea80.png), for all ![n \in \mathbb{Z}](./images/6a60974b71b73f667371a22a9ac7786140271f1a.png).

###[Sets as solutions to equations](./Front matter.md)

Another context where sets come up is when describing solutions to equations and inequalities. In[Section 1.1](./Chapter 1_ Math fundamentals.md) we learned how to solve for the unknown ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in equations. To solve the equation ![f(x)=c](./images/a456fa7c89e92c4af1874dd44d609a91c7685ef6.png) is to find all the values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that satisfy this equation. For simple equations like ![x-3=6](./images/820d2fcebab63fa36ae175bf70fe8401c980a497.png), the solution is a single number ![x=9](./images/c878748c1929b1a800f3312990f94ed67fc0022e.png), but more complex equations can have multiple solutions. For example, the solution to the equation ![x^2=4](./images/6cb588a648f6edaf65a4aaefb7145b376e453ebe.png) is the set ![\{-2,2\}](./images/909dd890d1bccabcd624319e25c75243cba02a98.png), since both ![x=-2](./images/5b422a9c8a6c0d82762433062ff9f9b6846f0c90.png) and ![x=2](./images/e5434555c15a07cfe09b5b352b1965c74365967d.png) satisfy the equation.

Please update your definition of the math verb “to solve” (an equation) to include the new notion of a _solution set_—the set of values that satisfy the equation. A solution set is the mathematically precise way to describe an equation’s solutions:

-   The solution set to the equation ![x-3=6](./images/820d2fcebab63fa36ae175bf70fe8401c980a497.png) is the set ![\{9\}](./images/b4518ca60b8e13867aa9dc76e62b1b91c5eaf631.png).
-   The solution set for the equation ![x^2=4](./images/6cb588a648f6edaf65a4aaefb7145b376e453ebe.png) is the set ![\{-2,2\}](./images/909dd890d1bccabcd624319e25c75243cba02a98.png).
-   The solution set of ![\sin(x)=0](./images/04b2423dfd7fd3ce43798bf0c87b2e7fd2859c30.png) is the set ![\{x \; | \;  x = \pi n, \forall n \in \mathbb{Z}\}](./images/a471cd9c4a911de70f127d0f93565149b231d048.png).
-   The solution set for the equation ![\sin(x)=2](./images/99d76d936cdddbbd04562bf3ae46948f3e9e1a87.png) is ![\emptyset](./images/938eb1d63c1623b9ef1a1893d533b2ddbd150136.png) (the empty set), since there is no number ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that satisfies the equation.

The `SymPy` function `solve` returns the solutions of equations as a list. To solve the equation ![f(x)=c](./images/a456fa7c89e92c4af1874dd44d609a91c7685ef6.png) using `SymPy`, we first rewrite it as expression that equals zero ![f(x)-c=0](./images/0f7ae773dd5b54f2fcdeff459a9e1d70a53a5df9.png), then call the function `solve`:

 >>> solve(x-3 -6, x)       # usage: solve(expr, var)
 \[9\]
 
 >>> solve(x\*\*2 -4, x)
 \[-2, 2\]
 
 >>> solve(sin(x), x)
 \[0, pi\]                    # found only solutions in \[0,2\*pi) 
 
 >>> solve(sin(x) -2, x)
 \[\]                         # empty list = empty set		

In the next section we’ll learn how the notion of a solution set is used for describing the solutions to systems of equations.

####[Solution sets to systems of equations](./Front matter.md)

Let’s revisit what we learned in[Section 1.15](./Chapter 1_ Math fundamentals.md) about the solutions to systems of linear equations, and define their solution sets more precisely. The solution set for the system of equations

![\begin{align*}
a_1x + b_1y     & =  c_1, \\
a_2x + b_2y     & =  c_2,
\end{align*}](./images/8957a9c7b4afa515a25128cd34999341161f74f2.png)

corresponds to the intersection of two sets:

![\underbrace{
\{ (x,y) \in \mathbb{R}^2 \; | \;  a_1x+b_1y=c_1 \}
}_{\ell_1}
\;  \cap \; 
\underbrace{
\{ (x,y) \in \mathbb{R}^2 \; | \;  a_2x+b_2y=c_2 \}
}_{\ell_2}.](./images/e334a8811b732655d394ae32c2d73a2ce025a6f9.png)

Recall that the lines ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png) are the geometric interpretation of these sets. Each line corresponds to a set of coordinate pairs ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that satisfy the equation of the line. The solution to the system of equations is the set of points at the intersection of the two lines ![\ell_1 \cap \ell_2](./images/7bd3fedc6c4e5ae3396dac968e0ac5969a797dff.png). Note the word _intersection_ is used in two different mathematical contexts: the solution is the _set intersection_ of two sets, and also the _geometric intersection_ of two lines.

Let’s take advantage of this correspondence between set intersections and geometric line intersections to understand the solutions to systems of equations in a little more detail. In the next three sections, we’ll look at three possible cases that can occur when trying to solve a system of two linear equations in two unknowns. So far we’ve only discussed Case A, which occurs when the two lines intersect at a point, as in the example shown in[Figure 1.67](./Chapter 1_ Math fundamentals.md). To fully understand the possible solutions to a system of equations, we need to think about all other cases; like Case B when ![\ell_1 \cap \ell_2 = \emptyset](./images/28806f7264767bdb66e70845de1caee43c342cc1.png) as in[Figure 1.68](./Chapter 1_ Math fundamentals.md), and Case C when ![\ell_1 \cap \ell_2 = \ell_1 = \ell_2](./images/17c606163ed5ca64eee1897bb319cda617d3dbd5.png) as in[Figure 1.69](./Chapter 1_ Math fundamentals.md).

#####[Case A: One solution.](./Front matter.md)

When the lines ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png) are non-parallel, they will intersect at a point as shown in[Figure 1.67](./Chapter 1_ Math fundamentals.md). In this case, the solution set to the system of equations contains a single point:

![\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=2 \}
\;  \cap \; 
\{ (x,y) \in \mathbb{R}^2 \; | \;  x=1 \}
=
\{ (1,\tfrac{1}{2}) \}.](./images/0b6257a0d20f9d2e15509475517475bc976e93a4.png)

![systems_of_equations__solution_sets_case_A](./images/systems_of_equations__solution_sets_case_A.png)

Figure 1.67: Case A: The intersection of the lines with equations ![x+2y=2](./images/9f95c91d3de64363febfd1cbce68c7e59c3cc208.png) and ![x=1](./images/c05f845e5cc9939507fccda58e08dc7831b8de3a.png) is the point ![(1,\frac{1}{2}) \in \mathbb{R}^2](./images/f58859f83f67682abd4430655017bff965a6bfee.png).

#####[Case B: No solution.](./Front matter.md)

If the lines ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png) are parallel then they will never intersect. The intersection of these lines is the empty set:

![\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=2 \}
\;  \cap \; 
\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=4 \}
=
\emptyset.](./images/4f948703ff45d16433e42358768f82d9675d87da.png)

Think about it—there is no point ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that lies on both ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png). Using algebra terminology, we say this system of equations has no solution, since there are no numbers ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) that satisfy both equations.

![systems_of_equations__solution_sets_case_B](./images/systems_of_equations__solution_sets_case_B.png)

Figure 1.68: Case B: The lines with equations ![x+2y=2](./images/9f95c91d3de64363febfd1cbce68c7e59c3cc208.png) and ![x+2y=4](./images/10af2f08189f2611fa52f38b8c446c7ad69a3b23.png) are parallel and do not intersect. Using set notation, we can describe the solution set as ![\emptyset](./images/f9bbe9077d067b510406bdc6443bd0f4f8267a24.png) (the empty set).

#####[Case C: Infinitely many solutions.](./Front matter.md)

If the lines ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png) are parallel and overlapping then they intersect everywhere. This case occurs when one of the equations in a system of equations is a multiple of the other equation, as in the case of equations ![x+2y=2](./images/b1c1af2702e28fd1e9f3232b01e6d3beb44dfffb.png) and ![3x+6y=6](./images/2b7b7974579f0d9c6d06f390b0b2508a6c3af2de.png). The lines ![\ell_1](./images/7ae603910be5831b95669f0801290f5d39126868.png) and ![\ell_2](./images/0b4ca5c61e6fe4ba7a8e9f911940ed01d1593296.png) that correspond to these equations are shown in[Figure 1.69](./Chapter 1_ Math fundamentals.md). Any point ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) that satisfies ![x+2y=2](./images/b1c1af2702e28fd1e9f3232b01e6d3beb44dfffb.png) also satisfies ![3x+6y=6](./images/2b7b7974579f0d9c6d06f390b0b2508a6c3af2de.png). Since both equations describe the same geometric line, the intersection of the two lines is equal to the lines: ![\ell_1 \cap \ell_2 = \ell_1 = \ell_2](./images/17c606163ed5ca64eee1897bb319cda617d3dbd5.png). In this case, the solution to the system of equations is described by the set ![\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=2 \}](./images/e491f6b0bfb8c65c249e08759affa4c67ef0d18c.png).

![systems_of_equations__solution_sets_case_C](./images/systems_of_equations__solution_sets_case_C.png)

Figure 1.69: Case C: the line ![\ell_1](./images/2700171b346ab6b4bda6d406dd791123fee92c26.png) described by equation ![x+2y=2](./images/9f95c91d3de64363febfd1cbce68c7e59c3cc208.png) and the line ![\ell_2](./images/d044fe34b7d41f4916ccf967c6bb2bc7e088c762.png) described by equation ![3x+6y=6](./images/054fee39fffaf3a4b79e3efb596ac73684dc1f16.png) correspond to the same line in the Cartesian plane. The intersection of these lines is the set ![\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=2 \} = \ell_1 = \ell_2](./images/65ff85de9a56cf71e53cc991e0a9780ba256aaa6.png).

We need to consider all three cases when thinking about the solutions to systems of linear equations: the solution set can be a point (Case A), the empty set (Case B), or a line (Case C). Observe that the same mathematical notion (a set) is able to describe the solutions in all three cases even though the solutions correspond to very different geometric objects. In Case A the solution is a set that contains a single point ![\{ (x,y) \}](./images/d9d2ce987b1d8b55f9d061aaa537b25a48bca729.png). In Case B the solution is the empty set ![\emptyset](./images/938eb1d63c1623b9ef1a1893d533b2ddbd150136.png). And in Case C the solution set is described by the infinite set ![\{ (x,y) \in \mathbb{R}^2 \; | \;  ax+by=c \}](./images/72a64917fc78d54da14b97755d1c99ed18b3cb38.png), which corresponds to a line ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) in the Cartesian plane. I hope you’ll agree with me that set notation is useful for describing mathematical concepts precisely and for handling solutions to linear equations.

Sets are also useful for describing the solutions to inequalities, which is what we’ll learn about next.

####[Inequalities](./Front matter.md)

In this section, we’ll learn how to solve inequalities. The solution set to an inequality is an _interval_—a subset of the number line. Consider the inequality ![x^2 \leq 4](./images/8199a85159a2fb812e5ee82448db6dc11d79ab5d.png), which is equivalent to asking the question, “For which values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) less than or equal to ![4](./images/d642a42f2cf4e1514233d611b91e5d4646202fc8.png)?” The answer to this question is the interval ![[-2,2] = \{ x\in \mathbb{R} \; | \; -2 \leq x \leq 2 \, \}](../Images/c12d35ed9589c3e9ced4f8444b8eeb304a73d7cf.png).

Working with inequalities is essentially the same as working with their endpoints. To solve the inequality ![x^2 \leq 4](./images/8199a85159a2fb812e5ee82448db6dc11d79ab5d.png), we first solve ![x^2 = 4](./images/6cb588a648f6edaf65a4aaefb7145b376e453ebe.png) to find the endpoints and then use trial and error to figure out which part of the space to the left and right of the endpoints satisfies the inequality.

It’s important to distinguish the different types of inequality conditions. The four different types of inequalities are

-   ![f(x) <  g(x)](./images/cdb36d43384190e13a2edeb7333154fae7548a07.png): a strict inequality. The function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) is always _strictly less than_ the function ![g(x)](./images/402bc673d4d7429bab611029b1a9d8a42f53931c.png).
-   ![f(x) \leq g(x)](./images/4728f88173533325152b5549c2872fa1ecd720bd.png): the function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) is _less than or equal to_ ![g(x)](./images/402bc673d4d7429bab611029b1a9d8a42f53931c.png).
-   ![f(x) > g(x)](./images/753afa82683e15faff7b69ed138cd0697e05a795.png): ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) is _strictly greater than_ ![g(x)](./images/402bc673d4d7429bab611029b1a9d8a42f53931c.png).
-   ![f(x) \geq g(x)](./images/1a650eb30482796b186cf3b5b3ead9cd4a6c9068.png): ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) is _greater than or equal to_ ![g(x)](./images/402bc673d4d7429bab611029b1a9d8a42f53931c.png).

Depending on the type of inequality, the answer will be either a _open_ or _closed_ interval.

To solve inequalities we use the techniques we learned for solving equations: we perform simplifying steps **on both sides of the inequality** until we obtain the answer. The only new aspect when dealing with inequalities is the following. When multiplying an inequality by a negative number on both sides, we must flip the direction of the inequality:

![f(x) \leq g(x) \qquad \Rightarrow  \qquad -f(x) \geq -g(x).](./images/d98bfdbea58dcc315fcfbe304c0b499fe26b3838.png)

#####[Example 5](./Front matter.md)

To solve the inequality ![7-x \leq 5](./images/70567b45f76fd6451c18957602dee55a26f1c081.png) we must _dig_ toward the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and _undo_ all the operations that stand in our way:

![\begin{align*}
7-x 					&\leq 5,		\\
(-x) + 7				&\leq 5,		\\
(-x) + 7 \; \color{blue}{-7}	&\leq 5 \; \color{blue}{-7},		\\
-x 					&\leq -2,		\\
x 					&\geq 2.
\end{align*}](./images/9795d2dfacef4e32b03390d255d7582a0580b1fc.png)

To obtain the second line we simply rewrote the order of operations on the left side of the inequality. In the third line we subtracted ![7](./images/7c8183005b1d0a8999b7a1cc791bffe88aeb450f.png) from both sides of the inequality to undo the ![+7](./images/f52f94f6008439049c76436231782afd7557ce91.png) operation. In the last step we multiplied both sides of the inequality by ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png), which had the effect of changing the inequality from ![\leq](./images/55279c624ae5c44513db6e2e0532df4ae9f06ad6.png) to ![\geq](./images/227dad476525d8ee25b8b2bfbba5bc95f33cde3d.png). The solution set to the inequality ![7-x \leq 5](./images/70567b45f76fd6451c18957602dee55a26f1c081.png) is the interval ![[2,\infty)](./images/7fde5ab6b47cd5f4c25b927a45c5e1332cdf264d.png).

#####[Example 6](./Front matter.md)

To solve the inequality ![x^2 \leq 4](./images/8199a85159a2fb812e5ee82448db6dc11d79ab5d.png), we must undo the quadratic function by taking the square root of both sides of the inequality. Note the equation ![x^2=4](./images/6cb588a648f6edaf65a4aaefb7145b376e453ebe.png) has two solutions: ![x=-2](./images/5b422a9c8a6c0d82762433062ff9f9b6846f0c90.png) and ![x=2](./images/e5434555c15a07cfe09b5b352b1965c74365967d.png). Similarly, we’ll need to consider two separate cases for the inequality conditions. Simplifying the inequality ![x^2 \leq 4](./images/8199a85159a2fb812e5ee82448db6dc11d79ab5d.png) by taking the square root on both sides results in two inequality conditions

![x \geq -2 	\qquad \textrm{and} \qquad x \leq 2,](./images/542f1f762663ab93d2560f5529692a833701d887.png)

which we can express more concisely as ![-2 \leq x \leq 2](./images/50089cdf7b229413bb471659c524bba4c3056e8d.png). If ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is a negative number, it must be greater than ![-2](./images/fad909888effb4a36881235a6f079a1489f6af7f.png); and if ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is a positive number, it must be less than ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) in order for ![x^2 \leq 4](./images/8199a85159a2fb812e5ee82448db6dc11d79ab5d.png). The solution set for the inequality ![x^2 \leq 4](./images/8199a85159a2fb812e5ee82448db6dc11d79ab5d.png) is the interval ![[-2,2] = \{ x\in \mathbb{R}\; | \; -2 \leq x \leq 2 \}](../Images/b9d0722e8fc54887cbe9dbeee083932e23cf556e.png). Note the solution is a closed interval (square brackets), which means the endpoints are included.

The best way to convince yourself that the above algebraic reasoning is correct is to think about the graph of the function ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png). The inequality ![x^2 \leq 4](./images/8199a85159a2fb812e5ee82448db6dc11d79ab5d.png) corresponds to the condition ![f(x)\leq 4](./images/70a71fdfe1cfe043236e238839b652215a48206a.png). For what values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is the graph of the function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) below the line with equation ![y=4](./images/9629f73ef1f77af7d5f9a0ac17febd2d949ca295.png)?

As you can see, solving inequalities is no more complicated than solving equations. You can think about an inequality in terms of its endpoints, which correspond to the equality conditions. Whenever things get complicated (as in Example 6), you can sketch the function graphs for the different terms in the inequality and visually determine the appropriate directions for the inequality signs.

###[Sets related to functions](./Front matter.md)

A function that takes real variables as inputs and produces real numbers as outputs is denoted ![f : \mathbb{R} \to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png). The _domain_ of a function is the set of all possible inputs to the function that produce an output:

![\textrm{Dom}(f) \eqdef \{ x \in \mathbb{R} \; | \; f(x) \in\mathbb{R} \}.](./images/6bc23da2d20385d09a66dd6d225a7e9ea26a5d3a.png)

Inputs for which the function is undefined are not part of the domain. For instance the function ![f(x)=\sqrt{x}](./images/bc20cca97740e11e58a05c4912bea200fcff083d.png) is not defined for negative inputs, so we have ![\textrm{Dom}(f) = \mathbb{R}_+](./images/2479b8b02f486d05d246b4716b16109871f7a6c1.png).

The _image_ of a function is the set of all possible outputs of the function:

![\textrm{Im}(f) \eqdef \{ y \in \mathbb{R} \; | \; \exists x\in\mathbb{R},\; y=f(x) \}.](./images/96e77b79825ec34da5c4773d140606920591f34c.png)

For example, the function ![f(x)=x^2](./images/8d8f72d34f4a43ceb27640796185b0dbdfa79761.png) has the image set ![\textrm{Im}(f) = \mathbb{R}_+](./images/a2debef8ffc993dd67280634b108927911d47164.png) since the outputs it produces are always nonnegative.

###[Discussion](./Front matter.md)

Knowledge of the precise mathematical jargon introduced in this section is not crucial to understanding basic mathematics. That said, I wanted to expose you to some technical math notation here because this is the language in which mathematicians think and communicate. Most advanced math textbooks will assume you understand technical math notation, so it’s good to be prepared.

###[Exercises](./Front matter.md)

E1.27 Given the three sets ![A=\{1,2,3,4,5,6,7\}](./images/af197f44ac024489741305b4133b72e75aaaaa89.png), ![B=\{1,3,5\}](./images/bb9f1375fa2c62be20ce03188d2ade5a6918520d.png), and ![C=\{2,4,6\}](./images/5b56fbe02c1bcde86cca465e7a2b2c2fb9715cf2.png), compute the following set expressions.

**a)** ![A \setminus B](./images/fcc307a8a212c36de9a1423848211451350b9484.png) **b)** ![B \cup C](./images/0099913aea11e5548bfa06a58eeec24d5920cf7f.png) **c)** ![A \cap B](./images/976995a676d6eaa2988678f07924399775fb87e6.png) **d)** ![B \cap C](./images/1ca4c636112db5eba7adebedecab4328c9900a62.png)

**e)** ![A \!\cup \!B \!\cup \!C](./images/c1179e358cd2d2ff78f093c4a70f6e8d503e8410.png) **f)** ![A  \setminus (B\!\cup\!C)](./images/7ed209350fc5aefdac3d49b1e861f329a9c22a7d.png) **g)** ![(A  \setminus B) \!\cup \!C](./images/862960524007490e2961084dbda386d8f470cfe9.png) **h)** ![A\!\cap\!B\!\cap\!C](./images/e4e0cc0e272aba386d96d988ef8682ba5f8fae27.png)

E1.28 Find the values of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) that satisfy the following inequalities.

**a)** ![2x < 3](./images/08ff2885cdbfba0d3fc26fd3bd5047d57712cf66.png) **b)** ![-4x \geq 20](./images/12eadcf593fed6f785ac644ad23c14424b76cc06.png) **c)** ![|2x-3|<5](./images/9794ccb49e9557c07f3bbc76951acf1766b0314b.png)

**d)** ![3x + 3 < 5x  - 5](./images/eb453ff9859b0aea0616f7ad588447e3d8fd4a7d.png) **e)** ![\frac{1}{2}x-2 \geq \frac{1}{3}](./images/1fda843c8be206eb502fed7f3388bc27238d41ea.png) **f)** ![(x+1)^2 \geq 9](./images/2992c8cee4e52bdc58639994501a3e3b7d5f2e79.png)

Express your answer as an interval with appropriate endpoints.

##[1.17 Math problems](./Chapter 1_ Math fundamentals.md)

We’ve now reached the first section of problems in this book. The purpose of these problems is to give you a way to comprehensively practice your math fundamentals. Knowing how to solve math problems is a very useful skill to develop. At times, honing your math chops might seem like tough mental work, but at the end of each problem, you’ll gain a stronger foothold on all the topics you’ve been learning about. You’ll also experience a small _achievement buzz_ after each problem you vanquish.

Sit down and take a crack at these practice problems today, or another time when you’re properly caffeinated. If you make time for some math practice, you’ll develop long-lasting comprehension and true math fluency.

Without solving any problems, you’re likely to forget most of what you’ve learned in the next few months. You might still remember the big ideas, but the details will be fuzzy and faded. By solving some of the practice problems, you’ll remember a lot more stuff. Don’t break the pace now: with math, it’s very much _use it or lose it_!

Make sure you put your phone away while you’re working on the problems. You don’t need fancy technology to do math; grab a pen and some paper from the printer and you’ll be fine. The great mathematicians like Descartes, Hilbert, Leibniz, and Noether did most of their work with pen and paper and they did well. Spend some time with math the way they did.

P1.1 Solve for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) in the equation ![x^2-9=7](./images/95c6a2d014d6d3b734b241acd02fc5c9eecf1584.png).

P1.2 Solve for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) in the equation ![\cos^{-1}\!\left( \frac{x}{A} \right) - \phi = \omega t](./images/8d85a88fd10f370db1d88afd817198d4a2056b65.png).

P1.3 Solve for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) in the equation ![\frac{1}{x}=\frac{1}{a}+\frac{1}{b}](./images/7cdcffd2c46bf451c7b0520ca9a62e0f4a3b1ef8.png).

P1.4 Use a calculator to find the values of the following expressions:

**a)**  ![\sqrt[4]{3^3}](../Images/f87127449bc98ea0603bf5464ea8f971495d187a.png)**b)**  ![2^{10}](./images/48014af92e148792443d341e9a40b426b20ec7d9.png)**c)**  ![7^{^{\frac{1}{4}}}-10](./images/6b131f91709df93205f31ea400fb91700187f4e5.png)**d)** ![\frac{1}{2}\ln(e^{22})](./images/98488fb6bae087fd3474c7b670e3d30343482a26.png)

P1.5 Compute the following expressions involving fractions:

**a)**  ![\dfrac{1}{2} + \dfrac{1}{4}](./images/59208e9a6a91f57e8be2515a795a08f5602b5e08.png)**b)**  ![\dfrac{4}{7} - \dfrac{23}{5}](./images/02dd6747404463e877b15eed137bf163556a09fb.png)**c)** ![1\frac{3}{4} + 1\frac{31}{32}](./images/a89bc49318298cc6df4d560a6cd0b26d6a027afc.png)

P1.6 Use the basic rules of algebra to simplify the following expressions:

**a)**  ![ab\,\dfrac{1}{a}\,b^2cb^{-3}](./images/d5f34ea469114d15c8fcd05ce37c18702ec660ba.png)**b)**  ![\dfrac{abc}{bca}](./images/1f6f243c77602faf31e636c594b223bdb2269676.png)**c)** ![\dfrac{27a^2}{\sqrt{9abba}}](./images/8711b7eccc950d47f4730149c1c70f2e459be032.png)

**d)**  ![\dfrac{a(b+c) - ca}{b}](./images/9ec2bb800bfd30b12e569af9c40d9986daad769d.png)**e)**  ![\dfrac{a}{c\sqrt[3]{b}}\dfrac{b^{\frac{4}{3}} }{a^2}](../Images/739eeda91ef7d9687e80c352241b91ad4eef69fb.png)**f)** ![(x+a)(x+b)\!-x(a+b)](./images/479b34f3c053e361d0cd9a4b7fe187b742f46eb1.png)

P1.7 Expand the brackets in the following expressions:

**a)**  ![(x+a)(x-b)](./images/3f329801627c3dd6aa820b838c47848adc626bc3.png)**b)**  ![(2x+3)(x-5)](./images/0508308f4d8597226fabd6fd86248154616b81c2.png)**c)** ![(5x-2)(2x+7)](./images/e635c9101e208acdc367a0af93418574df5d94b1.png)

P1.8 Factor the following expressions as a product of linear terms:

**a)**  ![x^2-2x-8](./images/ab884bfd761617a52a4614394cad94f594c0be88.png)**b)**  ![3x^3-27x](./images/271ec44966e9eef91e331ed8b8e5067dfc0b855c.png)**c)** ![6x^2+11x-21](./images/b1e948d4d4f0b8ee269175e2ed758ed794821c9d.png)

P1.9 Complete the square in the following quadratic expressions to obtain expressions of the form ![A(x-h)^2+k](./images/aeab7c76f184315548a815e711c13e137adec7b9.png).

**a)**  ![x^2 -4x +7](./images/0d751cea992f5735872a9d99925ccd1d8ca9fc16.png)**b)**  ![2x^2+12x+22](./images/7dae7053c0bfbf62b544cb3591bf2373731089d6.png)**c)** ![6x^2+11x-21](./images/b1e948d4d4f0b8ee269175e2ed758ed794821c9d.png)

P1.10 A golf club and a golf ball cost $1.10 together. The golf club costs one dollar more than the ball. How much does the ball cost?

P1.11 A father is 35 years old and his son is 5 years old. In how many years will the father’s age be four times the son’s age?

P1.12 A boy and a girl collected 120 nuts. The girl collected twice as many nuts as the boy. How many nuts did each collect?

P1.13 Alice is 5 years older than Bob. The sum of their ages is 25 years. How old is Alice?

P1.14 A publisher needs to bind 4500 books. One print shop can bind these books in 30 days, another shop can do it in 45 days. How many days are necessary to bind all the books if both shops work in parallel?

Find the books-per-day rate of each shop.

P1.15 A plane leaves Vancouver travelling at ![600\,](./images/1487499547a026463a603e409ab495768486b622.png)km/h toward Montreal. One hour later, a second plane leaves Vancouver heading for Montreal at ![900\,](./images/2f2679260e1d95fe1b0f1cad08ecc16026878a5b.png)km/h. How long will it take for the second plane to overtake the first?

Distance travelled is equal to velocity multiplied by time: ![d=vt](./images/aed5a5e524320e69c13bd5943f568c2e5555e1c5.png).

P1.16 The golden ratio, denoted ![\varphi](./images/6f14e9ed0b9ebc16fdc9b26b6156e6d595813474.png), is the positive solution to the quadratic equation ![x^2 - x - 1=0](./images/f0abcc295c9e8b75188a422a56aebd5f17f32808.png). Find the golden ratio.

P1.17 Solve for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) in the equation ![\dfrac{1}{x} + \dfrac{2}{1-x} = \dfrac{4}{x^2}](./images/c82ef7e7cadf5589f9f301197d0afd25d1e33d75.png).

Multiply both sides of the equation by ![x^2(1-x)](./images/adad48438d179cf368cc0f770d09e6a6f873c077.png).

P1.18 Use substitution to solve for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) in the following equations:

**a)**  ![x^6-4x^3+4=0](./images/a0da32fb3028832d7217a55230d1337844a8c651.png)**b)** ![\dfrac{1}{2-\sin x} = \sin x](./images/ccbaa3fd49306b32c56353e9d95a5021b5a7dcff.png)

P1.19 Find the range of values of the parameter ![m](./images/89bd9dbe770020ab4a4b963d537e5e619b5ee2ef.png) for which the equation ![2x^2 - mx + m = 0](./images/d50157fe9e40073effd0dea44002986566540e1d.png) has no real solutions.

Use the quadratic formula.

P1.20 Use the properties of exponents and logarithms to simplify

**a)**  ![e^xe^{-x}e^z](./images/dfd914b4fb33568bee29478b7546598563e4d2a7.png)**b)**  ![\left(\dfrac{xy^{-2}z^{-3}}{x^2y^3z^{-4}}\right)^{\!-3}](./images/d0fb7af8ae096d0fcbfa31a9b98b73772d620423.png)**c)** ![(8x^6)^{-\frac{2}{3}}](./images/07707e801b726a3d17c70fde0721829c0e94ae6f.png)

P1.21 Two algorithms, P and Q, can be used to solve a certain problem. The running time of Algorithm P as a function of the size of the problem ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) is described by the function ![P(n) = 0.002n^2](./images/229fb0885d4a0cea2dcd1e604107d85e8ce2f566.png). The running time of Algorithm Q is described by ![Q(n)=0.5n](./images/ff5e82e959e1bb44d998a0ebf12476fcfcb2f99b.png). For small problems, Algorithm P runs faster. Starting from what ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) will Algorithm Q be faster?

P1.22 Consider a right-angle triangle in which the shorter sides are ![8\,](./images/e8ca64b6b55db234d437a0d5ba7decb7703b6790.png)cm and ![6\,](./images/844bee62df5fb0dc76d0011cbeeea225100b84b4.png)cm. What is the length of the triangle’s longest side?

P1.23 A television screen measures 26 inches on the diagonal. The screen height is 13 inches. How wide is the screen?

P1.24 Given the angle and distance measurements labelled in[Figure 1.70](./Front matter.md), calculate the distance ![d](./images/dd565b0bdaf16b09052be14b28af85a1bdefb913.png) and the height of the mountain peak ![h](./images/77e0e4a50e89652b20f69385d6e8957897e96dcf.png).

![mountain-peak-angles](./images/mountain-peak-angles.png)

Figure 1.70

Use the definition of ![\tan\theta](./images/f7b61ad2b4b39969c831e59912918a9a9ed6d7d1.png) to obtain two equations in two unknowns.

P1.25 Find ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png). Express your answer in terms of ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png), ![b](./images/ae769ce22c6289af843e3e66bd3145003e72ccf6.png), ![c](./images/0da715a1d62623ace880d9c3dde79450f829f124.png) and ![\theta](./images/962d17a7e21d58659675e6e02789c85029447dd5.png).

![two_pythagoras_steps](./images/two_pythagoras_steps.png)

Use Pythagoras’ theorem twice; then use the function ![\tan](./images/d5802baf1158612e5a5391471ea3227fe43b2844.png).

P1.26 Use the power-reduction trigonometric identities (page 1.12.1.1) to express ![\sin^2\theta \cos^2\theta](./images/6f9ef78e1bf565c7924181e4bd1762cb752a4927.png) in terms of ![\cos 4\theta](./images/11de5e9f75b05c3ddc153a53d7d9635f4446acaf.png).

P1.27 Find the length of side ![c](./images/0da715a1d62623ace880d9c3dde79450f829f124.png) in the triangle:

![triangle_sine_rule](./images/triangle_sine_rule.png)

Use the sine rule.

P1.28 Consider the obtuse triangle shown in[Figure 1.71](./Front matter.md).

1.  Express ![h](./images/ff3d7c730fe249f87f25867e29826880166ebd2f.png) in terms of ![a](./images/4cda22d5320f6dff6eb299ee1773423f12d173ea.png) and ![\theta](./images/e54174a8e3ea733d18997611936c61176c6ab2f6.png).
2.  What is the area of this triangle?
3.  Express ![c](./images/f1e11ab49a8c49bd7edfbb4ff83a4e9c8aa85385.png) in terms of the variables ![a](./images/4cda22d5320f6dff6eb299ee1773423f12d173ea.png), ![b](./images/0252df302d58f3c4c7bcd2beba571d0faf9eaab9.png), and ![\theta](./images/e54174a8e3ea733d18997611936c61176c6ab2f6.png).

You can use the cosine rule for part **c)**.

![an-obtuse-triangle](./images/an-obtuse-triangle.png)

Figure 1.71

P1.29 Satoshi likes warm saké. He places 1 litre of water in a sauce pan with diameter ![17\,](./images/df4db213007fc72f9c6a43ddf8650e09dc0ca9ad.png)cm. How much will the height of the water level rise when Satoshi immerses a saké bottle with diameter ![7.5\,](./images/61e3df337af768166d12b0ef7b8eaa5dc8808cd8.png)cm?

You’ll need the volume conversion ratio ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png) litre = ![1000\,](./images/a5887e8cbfd146a5844d2a3cb6a968f0464da45e.png)cm![^3](./images/298e389be45d4deb1ec82fc7825080369c8340d1.png).

P1.30 The length of a rectangle is ![c + 2](./images/fb829bb159f2bf31d86777c014f74647099ecba3.png) and its height is ![5](./images/f2fa057f2254981666da1b26f97fb103f09600a3.png). What is the area of the rectangle?

P1.31 A box of facial tissues has dimensions ![10.5\,](./images/65ef1e3ecd59e49287dec767fbf8a48ed47357b7.png)cm by ![7\,](./images/ab5f9919a3107b9360fade327e25a681813da00d.png)cm by ![22.3\,](./images/45677b874d70cb5a9ebfb9ee6bc25ad2fb4644fa.png)cm. What is the volume of the box in litres?

![1\,](./images/f547f28f2b316249a2aa49d68acb25119ce9970a.png)L = ![1000\,](./images/a5887e8cbfd146a5844d2a3cb6a968f0464da45e.png)cm![^3](./images/298e389be45d4deb1ec82fc7825080369c8340d1.png).

P1.32 A swimming pool has length ![\ell=20\,](./images/4359b26886259acc114d334539341ffcd750a080.png)m, width ![w = 10\,](./images/0dab0f83fb4263fef59d13430bd0155c42944bbc.png)m, and depth ![d=1.5\,](./images/415dcfefe8aac0d1fc9840e230b5f547da358734.png)m. Calculate the volume of water in the swimming pool in litres?

![1\,](./images/f547f28f2b316249a2aa49d68acb25119ce9970a.png)m![^3](./images/298e389be45d4deb1ec82fc7825080369c8340d1.png) = ![1000\,](./images/a5887e8cbfd146a5844d2a3cb6a968f0464da45e.png)L.

P1.33 How many litres of water remain in a tank that is ![15\,](./images/3249c25ead510d5b43bb8b721584cadccaf38669.png)m long, ![6\,](./images/844bee62df5fb0dc76d0011cbeeea225100b84b4.png)m wide, and ![5\,](./images/35157f9bd61f4fa2d78d619f69ec6919974be9fb.png)m high, if 30% of its capacity is spent?

P1.34 A building has two water tanks, each with capacity ![4000\,](./images/a05b33ab2deacd821ebded95450bdfa4dd938171.png)L. One of them is ![\frac{1}{4}](./images/16f97df2aae4eaf5797114583fd4e7d61a7b6cf6.png) full and the other contains three times more water. How many litres of water does the building have in total?

P1.35 A man sells firewood. To make standard portions, he uses a standard length of rope ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) to surround a pack of logs. One day, a customer asks him for a double portion of firewood. What length of rope should he use to measure this order? Assume the packs of logs are circular in shape.

P1.36 How much pure water should be added to 10 litres of a solution that is 60% acid to make a solution that is 20% acid?

P1.37 A tablet screen has a resolution of 768 pixels by 1024 pixels, and the physical dimensions of the screen are 6 inches by 8 inches. One might conclude that the best size of a PDF document for such a screen would be 6 inches by 8 inches. At first I thought so too, but I forgot to account for the status bar, which is 20 pixels tall. The actual usable screen area is only 768 pixels by 1004 pixels. Assuming the width of the PDF is chosen to be 6 inches, what height should the PDF be so that it fits perfectly in the content area of the tablet screen?

P1.38 Find the sum of the natural numbers 1 through 100.

Imagine pairing the biggest number with the smallest number in the sum, the second biggest number with the second smallest number, etc.

P1.39 Solve for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) and ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png) simultaneously in the following system of equations: ![-x - 2y = -2](./images/d1b29f0296de0a69159d87b8045e02d1a6bd3cb0.png) and ![3x + 3y = 0](./images/97d1fd64723539655e51b177d4feb8691c7eb9b6.png).

P1.40 Solve the following system of equations for the three unknowns:

![\begin{align*}
1x + 2y +3 z = 14, \\
2x + 5y +6 z = 30, \\
-1x +2y +3 z = 12.
\end{align*}](./images/9e6c99657bd5627864a18ffec8ea927485f7dc53.png)

P1.41 Express the following vectors in length-and-direction notation:

**a)**  ![\vec{u}_1 = (0,5)](./images/1b6d3f67f37df1845b920919d53e35312bc488be.png)**b)**  ![\vec{u}_2 = (1,2)](./images/a37a6e99267e823c7627bec8b4dbee49f2382392.png)**c)** ![\vec{u}_3 = (-1,-2)](./images/dcf17c5dab725576437ddd87b264a471ebcb3954.png)

P1.42 Express the following vectors as components:

**a)**  ![\vec{v}_1 =20\angle30^\circ](./images/6289ddda4f9f42b8c8c821c302c727d2c3007793.png)**b)**  ![\vec{v}_2 = 10\angle\!-\!90^\circ](./images/490b26e9e3dc6a89a8277723bfa733b078a22936.png)**c)** ![\vec{v}_3 = 5\angle150^\circ](./images/792d91e9873d0d32d05a30f333b22c6451467bf7.png)

P1.43 Express the following vectors in terms of unit vectors ![\hat{\imath}](./images/2d091e90cd2ab3f47cbaf9f2c08ecb87d459f6ba.png), ![\hat{\jmath}](./images/a713505a11318673286b4dcb0b3cf905c0e8f24f.png), and ![\hat{k}](./images/99e682a282b64e2a67cb7fbe8dd1304838c5575c.png):

**a)**  ![\vec{w}_1 = 10\angle25^\circ](./images/fc1a4efddf714a7a7c8c6ebbd5f5e19ef374eb56.png)**b)**  ![\vec{w}_2 = 7\angle\!-\!90^\circ](./images/03c8b25ab53d13c0d5af4a9a6cbd4cc7f4714baa.png)**c)** ![\vec{w}_3 =(3,-2,3)](./images/4667ba15412721e9f401a504c37aed58e839faed.png)

P1.44 Given the vectors ![\vec{v}_1=(1,1)](./images/89e6a59f9660b78bea7c6ad9cc1effd29ff99b00.png), ![\vec{v}_2=(2,3)](./images/93d6bbab5801fc870746e89a2ced1cff321e7245.png), and ![\vec{v}_3=5\angle 30^\circ](./images/83cc0613a0e9e4e4aeb6a72ad5aa886a69c45049.png), calculate the following expressions:

**a)**  ![\vec{v}_1 + \vec{v}_2](./images/9b32b4835c67d130e42b5e0af4c3d54f2e7d0901.png)**b)**  ![\vec{v}_2 - 2\vec{v}_1](./images/cedbc0cee41601baa4a95d28c02d238d2c021f3f.png)**c)** ![\vec{v}_1 + \vec{v}_2 + \vec{v}_3](./images/43f5c8c987d0f90390d65d1a2356560b03bd3b09.png)

P1.45 Starting from the point ![P=(2,6)](./images/743b52bb992c2edf7e1a28210a7f1e8bda9a1a15.png), the three displacement vectors shown in[Figure 1.72](./Front matter.md) are applied to obtain the point ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png). What are the coordinates of the point ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png)?

![vector_addition_problem](./images/vector_addition_problem.png)

Figure 1.72

P1.46 Compute the following expressions:

**a)**  ![\sqrt{-4}](./images/fe4c54334dc0acf13f320c093f0691e5f0688527.png)**b)**  ![\dfrac{2+3i}{2+2i}](./images/e808c2275a1795e5703407f6a2ea979e855fc434.png)**c)** ![e^{3i}(2+i)e^{-3i}](./images/a44f94a2ea8c2e839178acc56b25c981785caaca.png)

P1.47 Solve for ![x \in \mathbb{C}](./images/72d97cefaacc6a9f0db14dbb43a33e8b54913656.png) in the following equations:

**a)**  ![x^2 = -4](./images/b38570ec1362446e3855f6b03ffbb4935ec705fd.png)**b)** ![\sqrt{x} = 4i](./images/b0f594ae8b8233e988ccaa788d66d7531b42f50c.png)

**c)**  ![x^2 +2x + 2=0](./images/0cf699b083fa3bc559c57de2eb721bca50ce6c74.png)**d)** ![x^4 +4x^2 +3 = 0](./images/74317d191635d1483e0c70f80f943df1af6f01cc.png)

To solve **d)**, use the substitution ![u=x^2](./images/a1377ceb53bef4aa6be930c9c0b55b17f42b1980.png).

P1.48 Given the numbers ![z_1 = 2+i](./images/8a75e5b9e63f910af7cc5101e5df382af67d8dbb.png), ![z_2 = 2-i](./images/79194d853f6eb45001d12c56af3367ee0692b35e.png), and ![z_3 = -1 - i](./images/2bc6027bf1a6c8b10b2faee2a82a7d53e231c523.png), compute

**a)**  ![|z_1|](./images/7f399e58176393c1fc7fbd638ec47ffe90ab283f.png)**b)**  ![\dfrac{z_1}{z_3}](./images/e3d0b25b62923ab6929dd7ed74c5f3d888e339e8.png)**c)** ![z_1z_2z_3](./images/7724f81ddb581be01b530cc78b29efa31822f31f.png)

P1.49 Let ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) be the set of people who are bankers and ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) be the set of crooks. Rewrite the math statement ![\exists b \in B \mid b \notin C](./images/93c9ddc4f9758ce81573ed8f85fa4b83c2e8b770.png) in plain English.

P1.50 Let ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) denote the set of people who run Monsanto, and ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png) denote the people who ought to burn in hell for all eternity. Write the math statement ![\forall p \in M,  p \in H](./images/479eb440cd523febd5bc6e500b85210f923b1272.png) in plain English.

P1.51 When starting a business, one sometimes needs to find investors. Define ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) to be the set of investors with money, and ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) to be the set of investors with connections. Describe the following sets in words: **a)** ![M \setminus C](./images/803a6ba3ac3da9531bbbad3ba763d46974a26577.png), **b)** ![C \setminus M](./images/2452dab72930a8c43bacbb77a310c6deff598319.png), and the most desirable set **c)** ![M\cap C](./images/03d7c5d19343ee7fd73733b6bcf45b0d807b6128.png).
