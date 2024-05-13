Chapter 1    

## [1.3 Number representations](part0001_split_003.md)

We use the letters “a, b, c, …” to write words. In a similar fashion, we use the digits ![0,1,2,3,4,5,6,7,8](00133.jpeg), and ![9](00134.jpeg) to write numbers in the language of math. You can think of the digits ![0](00101.jpeg) through ![9](00134.jpeg) as the “letters” used to write numbers. For example, the number ![334](00135.jpeg) consists of the digits ![3](00106.jpeg), ![3](00106.jpeg), and ![4](00136.jpeg). Note that the same digit ![3](00106.jpeg) denotes two different quantities depending on its position within the number. The first digit ![3](00106.jpeg) corresponds to the value three hundred, while the second digit ![3](00106.jpeg) corresponds to the value thirty.

### [Concepts](part0001_split_003.md)

In this section, we’ll review three important number representations:

-   The _decimal notation_ for integers, rationals, and real numbers consists of an integer part and a fractional part separated by a _decimal point_. For example, the decimal ![32.17](00137.jpeg) consists of the integer ![32](00138.jpeg) and the fractional part ![0.17](00139.jpeg).
-   The _fraction notation_ for integers and rational numbers consists of a numerator divided by a denominator. Here are some sample math expressions with fractions: ![\frac{1}{2}](00050.jpeg), ![\frac{3}{4}](00140.jpeg), ![\frac{3}{2}=1\frac{1}{2}](00141.jpeg), and ![\frac{17}{100}](00142.jpeg).
-   The _number line_ is a graphical representation for numbers that allows us to visualize numbers as geometric points on a line.

The same number ![a](00014.jpeg) can be represented in multiple equivalent ways. It is often convenient to convert from one representation to another depending on the calculations we need to perform. For example, the number three can be expressed as the numeral ![3](00106.jpeg), the decimal ![3.0](00143.jpeg), the fraction ![\frac{3}{1}](00144.jpeg), or as the point that lies three units to the right of the origin on the number line. All these representations refer to the same quantity, but each representation is useful in different contexts. The goal of this section is to get you comfortable working with all the number representations.

### [Positional notation for numbers](part0001_split_003.md)

The Hindu–Arabic numeral system is the most widely used system for writing numbers today. It is a _decimal_ _positional_ system. The term _decimal_ refers to the fact that it uses 10 unique symbols (the digits ![0](00101.jpeg) through ![9](00134.jpeg)) to represent numbers. The system is _positional_ because the value of each digit depends on its position within the number. Positional number systems are also called _place-value_ systems.

![number_repr_numeral](00145.jpeg)

Figure 1.6: The place-value representation of the number ![a = a_3a_2a_1a_0](00146.jpeg).

Note the terminology used to refer to the individual digits of the numeral: we call ![a_3](00147.jpeg) the thousands, ![a_2](00148.jpeg) the hundreds, ![a_1](00149.jpeg) the tens, and ![a_0](00150.jpeg) the units.

Any natural number ![a \in \mathbb{N}](00151.jpeg), no matter how large, can be written as a sequence of digits:

![\begin{align*}    a & =    a_{n}\cdots a_{2}a_{1}a_{0}                                        \\     & =         a_n \cdot 10^n     +  \cdots + a_2 \cdot 10^2 + a_1 \cdot 10 + a_0 \cdot 1,   \end{align*}](00152.jpeg)

where the digits ![a_0](00150.jpeg), ![a_1](00149.jpeg), …come from the set ![\{0,1,2,3,4,5,6,7,8,9\}](00153.jpeg).

For example, the numeral ![4235](00154.jpeg) corresponds to this calculation:

![\begin{align*}     4235     & =         4 \cdot 10^3     \, \, \; +    2 \cdot 10^2  +   3 \cdot 10     +  5 \cdot 1    \\     & =         4 \cdot 1000     +   2 \cdot 100     +  3 \cdot 10     + 5 \cdot 1    \\     & =         4000         +   200         +  30         + 5.   \end{align*}](00155.jpeg)

Note how the English pronunciation of the number, “four thousand, two hundred and thirty-five,” literally walks you through the calculation.

### [Decimal representation](part0001_split_003.md)

Any number ![a](00014.jpeg) less than one can be written as a _decimal point_ followed by a sequence of digits, as illustrated in[Figure 1.7](part0001_split_003.md).

![\begin{align*}    a    & = 0\,\mathbf{.}\,a_{-1}a_{-2}a_{-3}\cdots        \\    & = 0 + \frac{a_{-1}}{10^1} + \frac{a_{-2}}{10^2}  + \frac{a_{-3}}{10^3}  + \cdots        \; .   \end{align*}](00156.jpeg)

The decimal point indicates the beginning of the fractional part of a number. The place values of the digits to the right of the decimal point correspond to different decimal fractions. For example, the digit ![7](00157.jpeg) corresponds to three different decimal fractions depending on its position within the number:

![0.7=\frac{7}{10}   \; \;  ,  \qquad    0.07=\frac{7}{100}   \; \;  ,  \qquad    \textrm{and}    \qquad    0.007=\frac{7}{1000}  \; \;  .](00158.jpeg)

![number_repr_decimal_leq_one](00159.jpeg)

Figure 1.7: The decimal representation of a number smaller than one.

The first digit to the right of the decimal point ![a_{-1}](00160.jpeg) represents the _tenths_, the second digit ![a_{-2}](00161.jpeg) represents the _hundredths_, the third the _thousandths_, and so on.

In general, a number written in decimal notation has both an integer part and a fractional part:

![\begin{align*}    a    & =    a_{n}\cdots a_{2}a_{1}a_{0}\,\mathbf{.}\,a_{-1}a_{-2}a_{-3}\cdots        \\       & = a_n \cdot 10^n     +  \cdots + a_2 \cdot 10^2 + a_1 \cdot 10 + a_0      + \frac{a_{-1}}{10^1} + \frac{a_{-2}}{10^2} + \frac{a_{-3}}{10^3}  + \cdots               \end{align*}](00162.jpeg)

The decimal point appears in the middle of the digits and acts as a separator. The digits to the left of the decimal point, ![a_{n}\cdots a_{2}a_{1}a_{0}](00163.jpeg), correspond to the integer part of the number, while the digits to the right of the decimal, ![0.a_{-1}a_{-2}a_{-3}\cdots](00164.jpeg), correspond to the fractional part of the number.

![number_repr_decimal](00165.jpeg)

Figure 1.8: The decimal number ![a](00110.jpeg) consists of an integer part ![a_3a_2a_1a_0](00166.jpeg) and a fractional part ![0.a_{-1}a_{-2}\cdots](00167.jpeg) separated by the decimal point.

Note the names for the different digits in the fractional part of the decimal in[Figure 1.8](part0001_split_003.md). These names are used when we describe the fractional part of a decimal in words:

-   “![1.4](00168.jpeg)” is read “one and four tenths,” or you could informally describe the decimal as you see it written: “one point four.”
-   “![45.37](00169.jpeg)” is read “forty-five and thirty-seven hundredths,” or sometimes “forty-five point three seven.”
-   A length measurement like “![0.345](00170.jpeg) in” is read “three-hundred forty-five thousandths of an inch.”

We can use decimal notation to represent rational numbers like one-half (![0.5](00171.jpeg)), one-quarter (![0.25](00172.jpeg)), and three-quarters (![0.75](00173.jpeg)). We can also use decimal notation to write approximations to irrational numbers. For example, the irrational number ![\sqrt{2}](00056.jpeg) (the diagonal of a square with length one) is approximately equal to ![1.41421](00174.jpeg). We say the approximation ![1.41421](00174.jpeg) is “accurate to five decimals,” because this is how many digits there are in its fractional part.

So far we reviewed the decimal representation for numbers, which is very familiar to us from everyday life. Perhaps you’re starting to think that math isn’t so bad after all? Some of you must be saying, “Wonderful, I’m becoming friends with numbers while avoiding uncomfortable topics like fractions.” Sorry, but you’re not getting off so easily because this is exactly what’s coming up next. That’s right, we’re about to make friends with fractions, too.

### [Fractions](part0001_split_003.md)

Fractions describe what happens when a _whole_ is cut into ![n](00054.jpeg) equal parts and we are given ![m](00053.jpeg) of those parts. For example, the fraction ![\frac{3}{8}](00175.jpeg) describes having three parts out of a whole cut into eight parts, hence the name “three-eighths.”

![fractions_3_8_pie_chart](00176.jpeg)

Figure 1.9: The fraction ![\frac{3}{8}](00177.jpeg) can be visualized as three slices from a pizza that has been cut into eight equal slices.

It’s important to understand fractions because many math concepts like rational numbers (![\mathbb{Q}](00051.jpeg)), ratios, percents, and probabilities are best described in the language of fractions.

#### [Definitions](part0001_split_003.md)

The fraction “![a](00014.jpeg) over ![b](00074.jpeg)” can be written three different ways:

![a/b = a \div b = \frac{a}{b}\,.](00178.jpeg)

The top and bottom parts of the fraction ![\dfrac{a}{b}](00179.jpeg) have special names:

-   ![b](00074.jpeg) is called the _denominator_ of the fraction. It tells us how many parts make up the whole.
-   ![a](00014.jpeg) is called the _numerator_. It tells us the number of parts we have.

Fractions are the most natural way to represent rational numbers. Why natural? Check out these simple fractions:

![\begin{align*}    \tfrac{1}{1}    &= 1.0 \\    \tfrac{1}{2}    &= 0.5 \\    \tfrac{1}{3}    &= 0.33333\ldots = 0.\overline{3} \\    \tfrac{1}{4}    &= 0.25 \\    \tfrac{1}{5}    &= 0.2 \\    \tfrac{1}{6}    &= 0.166666\ldots = 0.1\overline{6} \\    \tfrac{1}{7}    &= 0.14285714285714285\ldots = 0.\overline{142857}    \end{align*}](00180.jpeg)

The fractional notation on the left is preferable because it shows the underlying _structure_ of the number while avoiding the need to write complicated decimals.

When written as decimal numbers, certain fractions have infinitely long decimal expansions. We use the overline notation to indicate the digit(s) that repeat infinitely in the decimal, as in the case of ![0.\overline{3}](00181.jpeg), ![0.1\overline{6}](00182.jpeg), and ![0.\overline{142857}](00183.jpeg) shown above.

Fractions allow us to carry out precise mathematical calculations easily with pen and paper, without the need for a calculator.

##### [Example](part0001_split_003.md)

Calculate the sum of ![\frac{1}{7}](00184.jpeg) and ![\frac{1}{3}](00185.jpeg).

Let’s say we decide, for reasons unknown, that it’s a great day for decimal notation—we’d have to write our calculation as

![\begin{align*}     \textrm{ans}          &= 0.\overline{142857} \; + \; 0.\overline{3} \\      &= 0.142\,857\,142\,857\ldots \; +  \;  0.333\,333\,333\,333\ldots \\      &= 0.476\,190\,476\,190\,476\ldots \\      & = 0.\overline{476190}.     \end{align*}](00186.jpeg)

Wow that was complicated! This calculation is much simpler if we use fractions:

![\frac{1}{7}+\frac{1}{3}        \; = \; \frac{1}{7}\!\times\!\frac{3}{3} \; + \; \frac{1}{3}\!\times\!\frac{7}{7}       \; = \; \frac{3}{21}+\frac{7}{21}        \; = \; \frac{3+7}{21}        \; = \; \frac{10}{21}.](00187.jpeg)

Want to know how we did that? We multiplied the first term by ![\frac{3}{3}=1](00188.jpeg) and the second term by ![\frac{7}{7}=1](00189.jpeg) in order to obtain two equivalent fractions with the same denominator. This is one of the standard strategies when performing fraction operations: rewriting them as equivalent fractions that have the same denominator.

#### [Equivalent fractions](part0001_split_003.md)

The fractions ![\frac{3}{8}](00175.jpeg), ![\frac{6}{16}](00190.jpeg), and ![\frac{12}{32}](00191.jpeg) all correspond to the same number. Think about it—if you cut a pizza in 8 pieces and take 3 of them (see[Figure 1.9](part0001_split_003.md)), or you cut a pizza in 16 equal pieces and take 6 of them, you’ll get the same amount of pizza in the end. All fractions of the form ![\frac{3k}{8k}](00192.jpeg) are _equivalent_ to the fraction ![\frac{3}{8}](00175.jpeg), meaning they correspond to the same number.

#### [Multiplying fractions](part0001_split_003.md)

Fraction multiplication involves multiplying the numerators together and multiplying the denominators together:

![\frac{a}{b} \times \frac{c}{d}      = \frac{a\times c}{b \times d}      = \frac{ac}{bd} \,.](00193.jpeg)

For example, the product of the fractions ![\frac{1}{3}](00185.jpeg) and ![\frac{1}{2}](00050.jpeg) gives ![\frac{1}{3} \times \frac{1}{2} = \frac{1 \times 1}{3 \times 2} = \frac{1}{6}](00194.jpeg). This calculation shows that taking “one third of one half of some thing” is the same as taking one sixth of that thing.

#### [Dividing fractions](part0001_split_003.md)

To divide two fractions, compute the product of the first fraction times the second fraction “flipped” upside down:

![\frac{ a/b }{ c/d }     \; \; = \; \; \frac{a}{b} \div \frac{c}{d}     \; \; = \; \; \frac{a}{b} \times \frac{d}{c}      \; \; = \; \;  \frac{a\times d}{b \times c}      \; \; = \; \; \frac{ad}{bc} \,.](00195.jpeg)

In other words, division by the fraction ![\frac{c}{d}](00196.jpeg) is the same as multiplication by the fraction ![\frac{d}{c}](00197.jpeg). This is called the “flip and multiply” rule for dividing fractions. For example, to divide the fraction ![\frac{1}{3}](00185.jpeg) by the fraction ![\frac{1}{2}](00050.jpeg), we do the following calculation: ![\frac{1}{3} / \frac{1}{2} = \frac{1}{3} \times \frac{2}{1} = \frac{2}{3}](00198.jpeg).

#### [Reciprocals](part0001_split_003.md)

The mathematical term _reciprocal_ is used to describe the notion of “flipping” a number. The reciprocal of ![y](00018.jpeg) is ![\frac{1}{y}](00199.jpeg), which is read “one over ![y](00018.jpeg).” Multiplication by the reciprocal ![\frac{1}{y}](00199.jpeg) is the same as division by ![y](00018.jpeg). The product of any number and its reciprocal equals one: ![y \times \frac{1}{y} = \frac{y}{y} = 1](00200.jpeg). The reciprocal of the fraction ![\frac{m}{n}](00052.jpeg) is the “flipped” fraction ![\frac{n}{m}](00201.jpeg). The product of ![\frac{m}{n}](00052.jpeg) and its reciprocal equals one: ![\frac{m}{n} \times \frac{n}{m} = \frac{mn}{nm} = 1](00202.jpeg).

Another way to denote the notion of “flipping” a number is to use the exponent negative one. The reciprocal of the number ![y](00018.jpeg) is denoted ![y^{-1}](00203.jpeg) and equals ![\frac{1}{y}](00199.jpeg). The reciprocal of the fraction ![\frac{m}{n}](00052.jpeg) is denoted ![(\frac{m}{n})^{-1}](00204.jpeg) and equals ![\frac{n}{m}](00201.jpeg). Using the negative exponent notation for reciprocals, we can write the “flip and multiply” rule for dividing fractions as ![\frac{a}{b} \div \frac{c}{d} = \frac{a}{b} \times \big(\frac{c}{d}\big)^{-1} = \frac{a}{b} \times \frac{d}{c}  = \frac{ad}{bc}](00205.jpeg). We’ll discuss negative exponents more generally in[Section 3.1](part0003_split_001.md).

#### [Adding fractions](part0001_split_003.md)

Suppose we are asked to find the sum of the two fractions ![\frac{a}{b}](00206.jpeg) and ![\frac{c}{d}](00196.jpeg). If the denominators are the same, then we can add just the top parts: ![\frac{1}{5} + \frac{2}{5} = \frac{3}{5}](00207.jpeg). It makes sense to add the numerators since they refer to parts of the _same_ whole.

However, if the denominators are different, we cannot add the numerators directly since they refer to parts of different wholes. Before we can add the numerators, we must rewrite the fractions so they have the same denominator, called a _common denominator_. We can obtain a common denominator by multiplying the first fraction by ![\frac{d}{d}=1](00208.jpeg) and the second fraction by ![\frac{b}{b}=1](00209.jpeg) in order to make the denominator of both fractions the same:

![\frac{a}{b} + \frac{c}{d}      \; \; \; = \; \; \;        \frac{a}{b}\!\left(\frac{d}{d}\right) + \frac{c}{d}\!\left(\frac{b}{b}\right)     \; \; \; = \; \; \;       \frac{ad}{bd} + \frac{bc}{bd}.](00210.jpeg)

Now that we have fractions with the same denominator, we can add their numerators. Note it’s okay to change the denominator of a fraction as long as we also change the numerator in the same way. Multiplying the top and the bottom of a fraction by the same number is the same as multiplying by ![1](00211.jpeg). So while the numbers of the fractions change, their equivalency is preserved:

![\frac{a}{b} + \frac{c}{d}     \; \; \; = \; \; \;        \frac{ad}{bd} + \frac{bc}{bd}     \; \; \; = \; \; \;         \frac{ ad + bc }{bd}.](00212.jpeg)

##### [Example](part0001_split_003.md)

To add ![\frac{1}{6}](00213.jpeg) and ![\frac{1}{15}](00214.jpeg), we can use the product of the two denominators as the common denominator, ![6 \times 15 = 90](00215.jpeg), and perform the fraction addition as follows:

![\frac{1}{6} + \frac{1}{15}       \; = \;  \frac{1}{6}\!\times\!\frac{15}{15} \; + \; \frac{1}{15}\!\times\!\frac{6}{6}      \; = \;  \frac{15}{90} + \frac{6}{90}       \; = \; \frac{21}{90}      \; = \;  \frac{7\times \cancel{3}}{30 \times \cancel{3}}      \; = \; \frac{7}{30}\,.](00216.jpeg)

Note how we simplified the fraction by removing the factor ![3](00106.jpeg) that is common to both the numerator and the denominator. The final answer ![\frac{7}{30}](00217.jpeg) is a reduced fraction equal to ![\frac{21}{90}](00218.jpeg).

The rules for subtracting fractions are the same as for adding fractions: computing the subtraction ![\frac{a}{b} - \frac{c}{d}](00219.jpeg) is the same as computing the addition ![\frac{a}{b} + \frac{-c}{d}](00220.jpeg).

#### [Whole-and-fraction notation](part0001_split_003.md)

A fraction greater than ![1](00211.jpeg) like ![\frac{5}{3}](00128.jpeg) can also be denoted ![1\frac{2}{3}](00221.jpeg), which is read as “one and two-thirds.” Similarly, ![\frac{22}{7}=3\frac{1}{7}](00222.jpeg). We write the integer part of the number first, followed by the fractional part.

There is nothing wrong with writing fractions like ![\frac{5}{3}](00128.jpeg) and ![\frac{22}{7}](00223.jpeg). However, some teachers call these fractions _improper_ and demand that all fractions are written in the whole-and-fraction way, as in ![1\frac{2}{3}](00221.jpeg) and ![3\frac{1}{7}](00224.jpeg). At the end of the day, both notations are correct.

### Number line](part0001_split_003.md)

The _number line_ is a very useful visual representation for numbers. Every number from the sets ![\mathbb{N}](00048.jpeg), ![\mathbb{Z}](00225.jpeg), ![\mathbb{Q}](00051.jpeg), and ![\mathbb{R}](00060.jpeg) corresponds to some point on the number line. Developing a visual representation for numbers allows us to instantly compare the numbers’ sizes based on their positions on the number line.

[Figure 1.10](part0001_split_003.md) shows the natural numbers ![\mathbb{N} = \{\, 0,1,2,3,4,5, \, \ldots \, \}](00226.jpeg) represented as equally spaced points on the number line. We can construct the entire set of natural numbers by starting from ![0](00101.jpeg) and taking steps of length one to the right on the number line. That’s what counting is—we just keep adding one.

Note that natural numbers never end. We can always keep adding one to every number and obtain a larger number. The number line therefore extends to the right to infinity.

![number_line_naturals](00227.gif)

Figure 1.10: The natural numbers ![\mathbb{N}](00228.jpeg).

The integers ![\mathbb{Z} = \{\ldots, -5, -4, -3,-2,-1,0,1,2,3,4,5, \ldots  \, \}](00229.jpeg) are similar to the naturals, but they also extend to the left of zero. Numbers to the left of zero are negative, while numbers to the right of zero are positive. The number line extends indefinitely on both sides, going to negative infinity on the left and positive infinity on the right.

![number_line_integers](00230.gif)

Figure 1.11: The integers ![\mathbb{Z}](00231.jpeg).

The set of integers corresponds to a set of equally-spaced points on the number line with gaps of empty space between each integer. We need the real numbers ![\mathbb{R}](00060.jpeg) to fill these gaps.

The set of real numbers ![\mathbb{R}](00060.jpeg) is the complete representation of all possible points on the number line: every real number corresponds to some point on the number line, and every point on the number line corresponds to some real number. Visually, the set of real numbers fills the entire number line in **bold**, as shown in[Figure 1.12](part0001_split_003.md). In other words, there are real numbers everywhere!

![number_line_rationals_and_reals](00232.gif)

Figure 1.12: The real numbers ![\mathbb{R}](00233.jpeg) cover the entire number line.

Recall that the set of real numbers includes all the rational numbers like ![-\frac{3}{2}](00234.jpeg), ![\frac{1}{2}](00050.jpeg), and ![\frac{9}{2}](00235.jpeg), as well as irrational numbers like ![\sqrt{2}](00056.jpeg), ![e](00236.jpeg), and ![\pi](00057.jpeg). This means any number you are likely to run into when solving math problems can be visualized as a point on the number line. The number line can also be used to represent subsets of the real numbers. We’ll talk about that in[Section 8.3](part0008_split_003.md). For example, the subset of real numbers that are greater than two and smaller than four is shown in[Figure 8.5](part0008_split_003.md) (page 8.5).

###[Discussion](part0001_split_003.md)

Since we’re still on the topic of number representations, I want to add some footnotes with “bonus material” related to the ideas we’ve covered in this section. Feel free to skip to the next section if you’re in a hurry, because this is definitely not going to be on the exam!

####[Elementary arithmetic procedures](part0001_split_003.md)

The four basic arithmetic operations are addition, subtraction, multiplication, and division. We can perform these operations for numerals ![a](00014.jpeg) and ![b](00074.jpeg) of any size using only pen and paper. It is sufficient to follow one of the well-defined procedures (called algorithms) for manipulating the individual digits that make up the numbers. The Wikipedia articles on elementary arithmetic and long division offer an excellent discussion of these procedures.

\[ Algorithms for performing elementary arithmetic \][`https://en.wikipedia.org/wiki/Elementary_arithmetic`](./Elementary_arithmetic.md)[`https://en.wikipedia.org/wiki/Long_division`](./Long_division.md)

####[Computer representations](part0001_split_003.md)

Whenever you want to store a number on a computer, you must choose an appropriate computer representation for this number. The two most commonly used types of numbers in the computer world are integers (`int`) and floating point numbers (`float`). Computer integers can accurately describe the set of mathematical integers ![\mathbb{Z}](00225.jpeg), but there are limitations on the maximum size of numbers that computers can store. We can use floating point numbers to store decimals with up to 15 digits of precision. The `int` and `float` numbers that computers provide are sufficient for most practical computations, and you probably shouldn’t worry about the limited precision of computer number representations. Still, I want you to be aware of the distinction between the abstract mathematical concept of a number and its computer representation. The real number ![\sqrt{2}](00056.jpeg) is irrational and has an infinite number of digits in its decimal expansion. On a computer, ![\sqrt{2}](00056.jpeg) is represented as the approximation ![1.41421356237310](00237.jpeg) (a `float`). For most purposes the approximation is okay, but sometimes the limited precision can show up in calculations. For example, `float(sqrt(2))*float(sqrt(2)) = 2.0000000000000004` ![\neq 2](00238.jpeg) and `float(0.1)+float(0.2) = 0.30000000000000004` ![\neq 0.3](00239.jpeg). The result of the computer’s calculation is only accurate up to the 15th digit. That’s pretty good if you ask me.

####[Scientific notation](part0001_split_003.md)

In science we often work with very large numbers like _the speed of light_ (![299\,792\,458](00240.jpeg)), and very small numbers like _the permeability of free space_ (![0.000001256637](00241.jpeg)). It can be difficult to judge the magnitude of such numbers and to carry out calculations on them using the usual decimal notation.

Dealing with such numbers is much easier if we use _scientific notation_. The speed of light can be written as ![2.99792458\times 10^{8}](00242.jpeg), and the permeability of free space is denoted as ![1.256637\times 10^{-6}](00243.jpeg). In both cases, we express the number as a decimal number between ![1.0](00244.jpeg) and ![9.9999\ldots](00245.jpeg) followed by the number ![10](00246.jpeg) raised to some exponent. The effect of multiplying by ![10^8](00247.jpeg) is to move the decimal point eight steps to the right, making the number bigger. Multiplying by ![10^{-6}](00248.jpeg) has the opposite effect, moving the decimal point to the left by six steps and making the number smaller. Scientific notation is useful because it allows us to clearly see the _size_ of numbers: ![1.23\times 10^{6}](00249.jpeg) is ![1\,230\,000](00250.jpeg) whereas ![1.23\times 10^{-10}](00251.jpeg) is ![0.000\,000\,000\,123](00252.jpeg). With scientific notation you don’t need to count the zeros!

The number of decimal places we use when specifying a certain physical quantity is usually an indicator of the _precision_ with which we are able to measure this quantity. Taking into account the precision of the measurements we make is an important aspect of all quantitative research. Since elaborating further would be a digression, we won’t go into a full discussion about the topic of _significant figures_ here. Feel free to read the Wikipedia article on the subject to learn more.

Computer systems represent numbers using scientific notation, too. When entering a floating point number into the computer, separate the decimal part from the exponent by the character `e`, which stands for “exponent.” For example, the speed of light is written as `2.99792458e8` and the permeability of free space is `1.256637e-6`.

###[Exercises](part0001_split_003.md)

E1.4 Compute the value of the following expressions:

**a)** ![\frac{1}{2} + \frac{1}{3}](00253.jpeg) **b)** ![\frac{1}{2} + \frac{1}{3} + \frac{1}{4}](00254.jpeg) **c)** ![3\frac{1}{2} + 2 - \frac{1}{3}](00255.jpeg)

###[Links](part0001_split_003.md)

I encourage you to check the links provided below to learn more about numbers and number representations.

\[ History of the Hindu–Arabic system for representing numbers \][`https://en.wikipedia.org/wiki/Hindu–Arabic_numeral_system`](./Hindu%E2%80%93Arabic_numeral_system.md)

\[ Positional number representation systems \][`https://en.wikipedia.org/wiki/Positional_notation`](./Positional_notation.md)

\[ Decimal representation \][`https://en.wikipedia.org/wiki/Decimal_representation`](./Decimal_representation.md)

\[ More details on scientific notation \][`https://en.wikipedia.org/wiki/Scientific_notation`](./Scientific_notation.md)

\[ Info about significant figures calculations \][`https://en.wikipedia.org/wiki/Significant_figures`](./Significant_figures.md)
