Chapter 1    

## [1.2 Numbers](part0001_split_002.md)

In the beginning, we must define the main players in the world of math: numbers.

### [Definitions](part0001_split_002.md)

Numbers are the basic objects we use to count, measure, quantify, and calculate things. Mathematicians like to classify the different kinds of number-like objects into categories called _sets_:

-   The natural numbers: ![\mathbb{N} = \{0,1,2,3,4,5,6,7, \ldots \, \}](00042.jpeg)
-   The integers: ![\mathbb{Z} = \{\ldots, -3,-2,-1,0,1,2,3 , \ldots  \, \}](00043.jpeg)
-   The rational numbers: ![\mathbb{Q} = \{\frac{5}{3}, \frac{22}{7}, 1.5, 0.125,  -7, \, \ldots \, \}](00044.jpeg)
-   The real numbers: ![\mathbb{R} = \{-1,0,1, \sqrt{2}, e,\pi, \;  4.94\ldots, \; \ldots \, \}](00045.jpeg)
-   The complex numbers: ![\mathbb{C} = \{ -1, 0, 1, i,  1+i, 2+3i,  \ldots \, \}](00046.jpeg)

These categories of numbers should be somewhat familiar to you. Think of them as neat classification labels for everything that you would normally call a number. Each group in the above list is a _set_. A set is a collection of items of the same kind. Each collection has a name and a precise definition for which items belong in that collection. Note also that each of the sets in the list contains all the sets above it, as illustrated in[Figure 1.1](part0001_split_002.md). For now, we don’t need to go into the details of[sets and set notation](part0008_split_003.md), but we do need to be aware of the different sets of numbers.

![nested_sets](00047.gif)

Figure 1.1: An illustration of the nested containment structure of the different number sets. The set of natural numbers is contained in the set of integers, which in turn is contained in the set of rational numbers. The set of rational numbers is contained in the set of real numbers, which is contained in the set of complex numbers.

Why do we need so many different sets of numbers? Each set of numbers is associated with more and more advanced mathematical problems.

The simplest numbers are the natural numbers ![\mathbb{N}](00048.jpeg), which are sufficient for all your math needs if all you’re going to do is _count_ things. How many goats? Five goats here and six goats there so the total is 11 goats. The sum of any two natural numbers is also a natural number.

As soon as you start using _subtraction_ (the inverse operation of addition), you start running into negative numbers, which are numbers outside the set of natural numbers. If the only mathematical operations you will ever use are _addition_ and _subtraction_, then the set of integers ![\mathbb{Z} = \{ \ldots, -2, -1, 0, 1, 2, \ldots \}](00049.jpeg) will be sufficient. Think about it. Any integer plus or minus any other integer is still an integer.

You can do a lot of interesting math with integers. There is an entire field in math called _number theory_ that deals with integers. However, to restrict yourself solely to integers is somewhat limiting—a rotisserie menu that offers ![\frac{1}{2}](00050.jpeg) of a chicken would be totally confusing.

If you want to use division in your mathematical calculations, you’ll need the rationals ![\mathbb{Q}](00051.jpeg). The set of rational numbers corresponds to all numbers that can be expressed as _fractions_ of the form ![\frac{m}{n}](00052.jpeg) where ![m](00053.jpeg) and ![n](00054.jpeg) are integers, and ![n \neq 0](00055.jpeg). You can add, subtract, multiply, and divide rational numbers, and the result will always be a rational number. However, even the rationals are not enough for all of math!

In geometry, we can obtain _irrational_ quantities like ![\sqrt{2}](00056.jpeg) (the diagonal of a square with side 1) and ![\pi](00057.jpeg) (the ratio between a circle’s circumference and its diameter). There are no integers ![x](00015.jpeg) and ![y](00018.jpeg) such that ![\sqrt{2}=\frac{x}{y}](00058.jpeg), therefore we say that ![\sqrt{2}](00056.jpeg) is _irrational_ (not in the set ![\mathbb{Q}](00051.jpeg)). An irrational number has an infinitely long decimal expansion that doesn’t repeat. For example, ![\pi = 3.141592653589793\ldots](00059.jpeg) where the dots indicate that the decimal expansion of ![\pi](00057.jpeg) continues all the way to infinity.

Combining the irrational numbers with the rationals gives us all the useful numbers, which we call the set of real numbers ![\mathbb{R}](00060.jpeg). The set ![\mathbb{R}](00060.jpeg) contains the integers, the rational numbers ![\mathbb{Q}](00051.jpeg), as well as irrational numbers like ![\sqrt{2}=1.4142135\ldots](00061.jpeg). By using the reals you can compute pretty much anything you want. From here on in the text, when I say _number_, I mean an element of the set of real numbers ![\mathbb{R}](00060.jpeg).

The only thing you can’t do with the reals is to take the square root of a negative number—you need the complex numbers ![\mathbb{C}](00062.jpeg) for that. We defer the discussion on ![\mathbb{C}](00062.jpeg) until the end of[Chapter 7](Vectors.md).

### [Operations on numbers](part0001_split_002.md)

#### [Addition](part0001_split_002.md)

You can add numbers. I’ll assume you’re familiar with this stuff:

![2 + 3 = 5,\; \; \; 45+56=101,\; \; \; 9\,999 + 1 = 10\,000.](00063.jpeg)

You can visualize numbers as sticks of different length. Adding numbers is like adding sticks together: the resulting stick has a length equal to the sum of the lengths of the constituent sticks, as illustrated in[Figure 1.2](part0001_split_002.md).

![number_line_addition](00064.gif)

Figure 1.2: The addition of numbers corresponds to adding lengths.

Addition is _commutative_, which means that ![a+b=b+a](00065.jpeg). In other words, the order of the numbers in a summation doesn’t matter. It is also _associative_, which means that if you have a long summation like ![a+b+c](00066.jpeg) you can compute it in any order ![(a+b)+c](00067.jpeg) or ![a+(b+c)](00068.jpeg), and you’ll get the same answer.

#### [Subtraction](part0001_split_002.md)

Subtraction is the inverse operation of addition:

![2 - 3 = -1, \quad 45-56 = -11, \quad 999 - 1 = 998.](00069.jpeg)

Unlike addition, subtraction is not a commutative operation. The expression ![a-b](00070.jpeg) is not equal to the expression ![b-a](00071.jpeg), or written mathematically:

![a-b \neq b-a.](00072.jpeg)

Instead we have ![b-a=-(a-b)](00073.jpeg), which shows that changing the order of ![a](00014.jpeg) and ![b](00074.jpeg) in the expression changes its sign.

Subtraction is not associative either:

![(a-b) - c \neq  a - (b-c).](00075.jpeg)

For example ![(7- 2) -3 = 2](00076.jpeg) while ![7- (2-3) = 8](00077.jpeg).

#### [Multiplication](part0001_split_002.md)

You can also multiply numbers together:

![ab = \underbrace{a+a+\cdots+a}_{b \; \textrm{times}}=\underbrace{b+b+\cdots+b}_{a \; \textrm{times}}.](00078.jpeg)

Note that multiplication can be defined in terms of repeated addition.

The visual way to think about multiplication is as an area calculation. The area of a rectangle of width ![a](00014.jpeg) and height ![b](00074.jpeg) is equal to ![ab](00079.jpeg). A rectangle with a height equal to its width is a square, and this is why we call ![aa=a^2](00080.jpeg) “![a](00014.jpeg) squared.”

![number_line_multiplication](00081.gif)

Figure 1.3: The area of a rectangle with width ![3](00082.jpeg) m and height ![2](00083.jpeg) m is equal to ![6](00084.jpeg)m![^2](00085.jpeg), which is equivalent to six squares with area ![1](00086.jpeg)m![^2](00085.jpeg) each.

Multiplication of numbers is also commutative, ![ab=ba](00087.jpeg), and associative, ![abc=(ab)c=a(bc)](00088.jpeg). In modern math notation, no special symbol is required to denote multiplication; we simply put the two factors next to each other and say the multiplication is _implicit_. Some other ways to denote multiplication are ![a\cdot b](00089.jpeg), ![a\times b](00090.jpeg), and, on computer systems, ![a*b](00091.jpeg).

#### [Division](part0001_split_002.md)

Division is the inverse operation of multiplication.

![a/b \; = \;  \frac{a}{b}  \; = a\div b = \text{ one } b^{\scriptsize \text{th}} \text{ of } a.](00092.jpeg)

Whatever ![a](00014.jpeg) is, you need to divide it into ![b](00074.jpeg) equal parts and take one such part.

Division is not a commutative operation since ![a/b](00093.jpeg) is not equal to ![b/a](00094.jpeg). Division is not associative either: ![(a \div b) \div c   \neq   a \div (b \div c)](00095.jpeg). For example, when ![a=6](00096.jpeg), ![b=3](00097.jpeg), and ![c=2](00098.jpeg), we get ![(6/3)/2=1](00099.jpeg) while ![6/(3/2)=4](00100.jpeg).

Note that you cannot divide by ![0](00101.jpeg). Try it on your calculator or computer. It will say “`error divide by zero`” because this action simply doesn’t make sense. After all, what would it mean to divide something into zero equal parts?

#### [Exponentiation](part0001_split_002.md)

The act of multiplying a number by itself many times is called _exponentiation_. We denote “![a](00014.jpeg) exponent ![n](00054.jpeg)” using a superscript, where ![n](00054.jpeg) is the number of times the base ![a](00014.jpeg) is multiplied by itself:

![a^n = \underbrace{aaa\cdots a}_{n\; \text{times}}.](00102.jpeg)

In words, we say “![a](00014.jpeg) raised to the power of ![n](00054.jpeg).”

To visualize how exponents work, we can draw a connection between the value of exponents and the dimensions of geometric objects.[Figure 1.4](part0001_split_002.md) illustrates how the same length ![2](00103.jpeg) corresponds to different geometric objects when raised to different exponents. The number ![2](00103.jpeg) corresponds to a line segment of length two, which is a geometric object in a one-dimensional space. If we add a line segment of length two in a second dimension, we obtain a square with area ![2^2](00104.jpeg) in a two-dimensional space. Adding a third dimension, we obtain a cube with volume ![2^3](00105.jpeg) in a three-dimensional space. Indeed, raising a base ![a](00014.jpeg) to the exponent ![2](00103.jpeg) is commonly called “![a](00014.jpeg) squared,” and raising ![a](00014.jpeg) to the power of ![3](00106.jpeg) is called “![a](00014.jpeg) cubed.”

The geometrical analogy about one-dimensional quantities as lengths, two-dimensional quantities as areas, and three-dimensional quantities as volumes is good to keep in mind.

![number_line_exponentiation](00107.gif)

Figure 1.4: Geometric interpretation for exponents ![1](00086.jpeg), ![2](00083.jpeg), and ![3](00082.jpeg). A length raised to exponent ![2](00083.jpeg) corresponds to the area of a square. The same length raised to exponent ![3](00082.jpeg) corresponds to the volume of a cube.

Our visual intuition works very well up to three dimensions, but we can use other means of visualizing higher exponents, as demonstrated in[Figure 1.5](part0001_split_002.md).

![exponents_prime_factorizations](00108.jpeg)

Figure 1.5: Visualization of numbers raised to different exponents. Each box in this grid contains ![a^n](00109.jpeg) dots, where the base ![a](00110.jpeg) varies from one through five, and the exponent ![n](00111.jpeg) varies from one through five. In the first row we see that the number ![a=1](00112.jpeg) raised to any exponent is equal to itself. The second row corresponds to the base ![a=2](00113.jpeg) so the number of dots doubles each time we increase the exponent by one. Starting from ![2^1=2](00114.jpeg) in the first column, we end up with ![2^5=32](00115.jpeg) in the last column. The rest of the rows show how exponentiation works for different bases.

### [Operator precedence](part0001_split_002.md)

There is a standard convention for the order in which mathematical operations must be performed. The basic algebra operations have the following precedence:

1.  Parentheses
2.  Exponents
3.  Multiplication and Division
4.  Addition and Subtraction

If you’re seeing this list for the first time, the acronym PEMDAS and the associated mnemonic “Please Excuse My Dear Aunt Sally,” might help you remember the order of operations.

For instance, the expression ![5\cdot 3^2+13](00116.jpeg) is interpreted as “First find the square of ![3](00106.jpeg), then multiply it by ![5](00117.jpeg), and then add ![13](00118.jpeg).” Parentheses are needed to carry out the operations in a different order: to multiply ![5](00117.jpeg) times ![3](00106.jpeg) first and _then_ take the square, the equation should read ![(5\cdot 3)^2 + 13](00119.jpeg), where parentheses indicate that the square acts on ![(5 \cdot 3)](00120.jpeg) as a whole and not on ![3](00106.jpeg) alone.

### [Exercises](part0001_split_002.md)

E1.1 Solve for the unknown ![x](00015.jpeg) in the following equations:

**a)** ![3x+2-5=4+2](00121.jpeg) **b)** ![\frac{1}{2}x-3=\sqrt{3}+12-\sqrt{3}](00122.jpeg)

**c)** ![\frac{7x-4}{2} +1 = 8-2](00123.jpeg) **d)** ![5x-2+3=3x-5](00124.jpeg)

E1.2 Indicate all the number sets the following numbers belong to.

**a)** ![-2](00125.jpeg) **b)** ![\sqrt{-3}](00126.jpeg) **c)** ![8 \div 4](00127.jpeg) **d)** ![\frac{5}{3}](00128.jpeg) **e)** ![\frac{\pi}{2}](00129.jpeg)

E1.3 Calculate the values of the following expressions:

**a)** ![2^33-3](00130.jpeg) **b)** ![2^3(3-3)](00131.jpeg) **c)** ![\frac{4-2}{3^3}(6\cdot 7- 41)](00132.jpeg)
