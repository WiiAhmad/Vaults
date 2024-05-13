Chapter 8    

##[8.3 Set notation](part0008_split_003.md)

A _set_ is the mathematically precise notion for describing a group of objects. You don’t need to know about sets to perform simple math; but more advanced topics require an understanding of what sets are and how to denote set membership, set operations, and set containment relations. This section introduces all the relevant concepts.

###[Definitions](part0008_split_003.md)

-   _set_: a collection of mathematical objects
-   ![S,T](01944.jpeg): the usual variable names for sets
-   ![s \in S](01945.jpeg): this statement is read “![s](01799.jpeg) is an element of ![S](00595.jpeg)” or “![s](01799.jpeg) is in ![S](00595.jpeg)”
-   ![\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}](01946.jpeg): some important number sets: the naturals, the integers, the rationals, and the real numbers, respectively.
-   ![\emptyset](01947.jpeg): the _empty set_ is a set that contains no elements
-   ![\{ \textrm{  .....  } \}](01948.jpeg): the curly brackets are used to define sets, and the expression inside the curly brackets describes the set contents.

Set operations:

-   ![S\cup T](01949.jpeg): the _union_ of two sets. The union of ![S](00595.jpeg) and ![T](01950.jpeg) corresponds to the elements in either ![S](00595.jpeg) or ![T](01950.jpeg).
-   ![S \cap T](01951.jpeg): the _intersection_ of the two sets. The intersection of ![S](00595.jpeg) and ![T](01950.jpeg) corresponds to the elements that are in both ![S](00595.jpeg) and ![T](01950.jpeg).
-   ![S \setminus T](01952.jpeg): _set difference_ or _set minus_. The set difference ![S \setminus T](01952.jpeg) corresponds to the elements of ![S](00595.jpeg) that are not in ![T](01950.jpeg).

Set relations:

-   ![\subset](01864.jpeg): is a strict subset of
-   ![\subseteq](01953.jpeg): is a subset of or equal to

Here is a list of special mathematical shorthand symbols and their corresponding meanings:

-   ![\in](01863.jpeg): element of
-   ![\notin](01954.jpeg): not an element of
-   ![\forall](01865.jpeg): for all
-   ![\exists](01866.jpeg): there exists
-   ![\nexists](01955.jpeg): there doesn’t exist
-   ![|\,](01956.jpeg): such that

These symbols are used in math proofs because they allow us to express complex mathematical arguments succinctly and precisely.

An _interval_ is a subset of the real line. We denote an interval by specifying its endpoints and surrounding them with either square brackets “![[](01957.jpeg)” or round brackets “![(](01958.jpeg)” to indicate whether or not the corresponding endpoint is included in the interval.

-   ![[a,b]](../images/01959.jpeg): the _closed_ interval from ![a](00014.jpeg) to ![b](00074.jpeg). This corresponds to the set of numbers between ![a](00014.jpeg) and ![b](00074.jpeg) on the real line, including the endpoints ![a](00014.jpeg) and ![b](00074.jpeg). ![[a,b] = \{ x\in \mathbb{R}\; | \; a \leq x \leq b \}](01960.jpeg).
-   ![(a,b)](01961.jpeg): the _open_ interval from ![a](00014.jpeg) to ![b](00074.jpeg). This corresponds to the set of numbers between ![a](00014.jpeg) and ![b](00074.jpeg) on the real line, _not_ including the endpoints ![a](00014.jpeg) and ![b](00074.jpeg). ![(a,b) = \{ x\in \mathbb{R}\; | \; a < x < b \}](01962.jpeg).
-   ![[a,b)](01963.jpeg): the half-open interval that includes the left endpoint ![a](00014.jpeg) but not the right endpoint ![b](00074.jpeg). ![[a,b) = \{ x\in \mathbb{R}\; | \; a \leq x < b \}](01964.jpeg).

Sometimes we encounter intervals that consist of two disjointed parts. We use the notation ![[a,b] \cup [c,d]](../images/01965.jpeg) to denote the union of the two intervals, which is the set of numbers _either_ between ![a](00014.jpeg) and ![b](00074.jpeg) (inclusive) _or_ between ![c](00256.jpeg) and ![d](01966.jpeg) (inclusive).

###[Sets](part0008_split_003.md)

Much of math’s power comes from _abstraction_: the ability to see the bigger picture and think _meta_ thoughts about the common relationships between math objects. We can think of individual numbers like ![3](00106.jpeg), ![-5](00391.jpeg), and ![\pi](00057.jpeg), or we can talk about the set of _all_ numbers.

It is often useful to restrict our attention to a specific _subset_ of the numbers as in the following examples.

####[Example 1: The nonnegative real numbers](part0008_split_003.md)

Define ![\mathbb{R}_+ \subset \mathbb{R}](01967.jpeg) (read “![\mathbb{R}_+](00683.jpeg) is a subset of ![\mathbb{R}](00060.jpeg)”) to be the set of nonnegative real numbers:

![\mathbb{R}_+  \eqdef  \{ \text{all } x \text{ in } \mathbb{R} \text{ such that } x \geq 0 \},](01968.jpeg)

or expressed more compactly,

![\mathbb{R}_+ \eqdef \{ x \in \mathbb{R} \; | \; x \geq 0 \}.](01969.jpeg)

If we were to translate the above expression into plain English, it would read “The set ![\mathbb{R}_+](00683.jpeg) is defined as the set of all real numbers ![x](00015.jpeg) such that ![x](00015.jpeg) is greater or equal to zero.”

Note we used the “is defined as” symbol “![\eqdef](01970.jpeg)” instead of the basic “![=](00022.jpeg)” to give an extra hint that we’re defining a new variable ![\mathbb{R}_+](00683.jpeg) that is equal to the set expression on the right. In this book, we’ll sometimes use the symbol “![\eqdef](01970.jpeg)” when defining new variables and math quantities. Some other books use the notation “![:=](01971.jpeg)” or “![\equiv](01972.jpeg)” for this purpose. The meaning of “![\eqdef](01970.jpeg)” is identical to “![=](00022.jpeg)” but it tells us the variable on the left of the equality is new.

####[Example 2: Even and odd integers](part0008_split_003.md)

Define the set of even integers as

![E \eqdef \{ m \in \mathbb{Z}  \; | \;  m=2n, \; n \in \mathbb{Z} \} =  \{ \ldots, -4, -2, 0, 2, 4, \ldots \}  \quad](01973.jpeg)

and the set of odd integers as

![O \eqdef \{ m \in \mathbb{Z}   \; | \;  m=2n+1, \; n \in \mathbb{Z} \} =  \{ \ldots, -3, -1, 1, 3, 5, \ldots \}.](01974.jpeg)

Indeed, every even number is divisible by two, so it can be written in the form ![2n](01975.jpeg) for some integer ![n](00054.jpeg). Odd numbers can be obtained from the “template” ![2n+1](01976.jpeg), with ![n](00054.jpeg) varying over all integers.

In both of the above examples, we use the _set-builder_ notation ![\{\, \ldots \; | \;  \ldots \, \}](01977.jpeg) to define the sets. Inside the curly braces we first describe the general kind of mathematical objects we are talking about, followed by the symbol “![|](01978.jpeg)” (read “such that”), followed by the conditions that must be satisfied by all elements of the set.

###[Number sets](part0008_split_003.md)

Recall the fundamental number sets we defined in[Section 1.2](part0001_split_002.md) in the beginning of the book. It is worthwhile to review them briefly.

The _natural_ numbers form the set derived when you start from ![0](00101.jpeg) and add ![1](00211.jpeg) any number of times:

![\mathbb{N}  \eqdef  \{ 0, 1, 2, 3, 4, 5, 6, \ldots \}.](01979.jpeg)

We use the notation ![\mathbb{N}^*](01980.jpeg) to denote the set of _positive natural numbers_. The set ![\mathbb{N}^*](01980.jpeg) is the same as ![\mathbb{N}](00048.jpeg) but excludes zero.

The integers are the numbers derived by adding or subtracting 1 some number of times:

![\mathbb{Z}  \eqdef  \{ x \:|\: x= \pm n, n \in \mathbb{N} \}.](01981.jpeg)

If we allow for divisions between integers, we require the set of rational numbers to represent the results:

![\mathbb{Q} \eqdef \left\{  \frac{m}{n} \; \Big| \; m \in \mathbb{Z}, \; n \in \mathbb{N}^*  \right\},](01982.jpeg)

In words, this expression is telling us that every rational number can be written as a fraction ![\frac{m}{n}](00052.jpeg), where ![m](00053.jpeg) is an integer (![m \in \mathbb{Z}](01983.jpeg)), and ![n](00054.jpeg) is a positive natural number (![n \in \mathbb{N}^*](01984.jpeg)).

The broader class of real numbers also includes all rationals as well as irrational numbers like ![\sqrt{2}](00056.jpeg) and ![\pi](00057.jpeg):

![\mathbb{R} \eqdef \{\pi, e, -1.53929411\ldots,\;  4.99401940129401\ldots, \; \ldots \}.](01985.jpeg)

Finally, we have the set of complex numbers:

![\mathbb{C} \eqdef \{ 1, i,  1+i, 2+3i,  \ldots \},](01986.jpeg)

where ![i \eqdef \sqrt{-1}](01987.jpeg) is the unit imaginary number.

Note that the definitions of ![\mathbb{R}](00060.jpeg) and ![\mathbb{C}](00062.jpeg) are not very precise. Rather than give a precise definition of each set inside the curly braces as we did for ![\mathbb{Z}](00225.jpeg) and ![\mathbb{Q}](00051.jpeg), we instead stated some examples of the elements in the set. Mathematicians sometimes do this and expect you to guess the general pattern for all the elements in the set.

The following inclusion relationship holds for the fundamental sets of numbers:

![\mathbb{N} \subset       \mathbb{Z} \subset       \mathbb{Q} \subset       \mathbb{R} \subset       \mathbb{C}.](01988.jpeg)

This relationship means every natural number is also an integer. Every integer is a rational number. Every rational number is a real. And every real number is also a complex number. See[Figure 1.1](part0001_split_002.md) (page 1.1) for an illustration of the subset relationship between the number sets.

###[Rational numbers and fractions](part0008_split_003.md)

So far in this book, we’ve used the notions of “fraction” and “rational number” somewhat interchangeably. Now that we’ve learned about sets, we can clarify the differences and equivalencies between these related concepts.

The same rational number ![\frac{2}{3}](01989.jpeg) can be written as a fraction in multiple, equivalent ways. The fractions ![\frac{2}{3}](01989.jpeg), ![\frac{4}{6}](01990.jpeg), ![\frac{6}{9}](01991.jpeg), ![\frac{8}{12}](01992.jpeg), and ![\frac{2k}{3k}](01993.jpeg) all correspond to the same rational number. Keep in mind the existence of these _equivalent fractions_ whenever checking whether two rational numbers are equal. For example, one person could obtain the answer ![\frac{2}{3}](01989.jpeg) to a given problem, while another person obtains the answer ![\frac{4}{6}](01990.jpeg). Since the two fractions look different, we might think these are different answers, when in fact both answers correspond to the same rational number.

A _reduced fraction_ is a fraction of the form ![\frac{m}{n}](00052.jpeg) such that the numbers ![m](00053.jpeg) and ![n](00054.jpeg) are the smallest possible. We can obtain the reduced fraction by getting rid of any common factors that appear both in the numerator and denominator. For example,

![\frac{4}{6} = \frac{2\cdot 2}{3 \cdot 2} = \frac{2\cdot \cancel{2}}{3 \cdot \cancel{2} } = \frac{2}{3} \,,](01994.jpeg)

where we cancelled the common factor ![2](00103.jpeg) to obtain the equivalent reduced fraction. Reduced fractions are a useful representation for the set of rational numbers, because each rational number corresponds to a unique reduced fraction. Two rational numbers are equal if and only if they correspond to the same reduced fraction.

###[Subsets of the real line](part0008_split_003.md)

Recall that the real numbers ![\mathbb{R}](00060.jpeg) have a graphical representation as points on the number line. See[Figure 1.12](part0001_split_003.md) on page 1.12 for a reminder. The number line is also useful for representing various subsets of the real numbers, which we call _intervals_. We can graphically represent an interval by setting a section of the number line in **bold**. For example, the set of numbers that are strictly greater than ![2](00103.jpeg) and strictly smaller than ![4](00136.jpeg) is represented mathematically either as “![(2,4)](00784.jpeg),” or more explicitly as

![\{ x \in \mathbb{R} \;|\;    2 < x < 4 \},](01995.jpeg)

or graphically as in[Figure 8.5](part0008_split_003.md).

![interval_2open_to_4open](01996.jpeg)

Figure 8.5: The open interval ![(2,4) = \{ x \in \mathbb{R} \;|\;    2 < x < 4 \}](01997.jpeg).

Let’s read the mathematical definition of this set carefully, and try to connect it with the graphical representation. Recall that the symbol ![\in](01863.jpeg) denotes set membership and the vertical bar stands for “such that,” so the whole expression “![\{ x \in \mathbb{R} \;|\;    2 < x < 4 \}](01998.jpeg)” is read “the set of real numbers ![x](00015.jpeg), such that ![2<x<4](01999.jpeg).” Indeed this is also the region shown in bold in[Figure 8.5](part0008_split_003.md).

Note that this interval is described by _strict_ inequalities, which means the subset contains ![2.000000001](02000.jpeg) and ![3.99999999](02001.jpeg), but doesn’t contain the endpoints ![2](00103.jpeg) and ![4](00136.jpeg). These _open_ endpoints ![2](00103.jpeg) and ![4](00136.jpeg) are denoted on the number line as empty dots. An empty dot indicates that the endpoint is not included in the set.

We use the _union_ symbol (![\cup](02002.jpeg)) to denote subsets of the number line that consist of several parts. For example, the set of numbers that lies _either_ between ![-3](02003.jpeg) and ![0](00101.jpeg) _or_ between ![1](00211.jpeg) and ![2](00103.jpeg) is written as

![\{ x \in \mathbb{R} \; |\;    -3 \leq x \leq 0 \}     \; \cup \;    \{ x \in \mathbb{R} \;|\;    1 \leq x \leq 2 \}.](02004.jpeg)

![interval_-3_to_0_and_1_to_2_all_closed](02005.jpeg)

Figure 8.6: The graphical representation of the set ![[-3,0] \cup [1,2]](../images/02006.jpeg).

This set is defined by less-than-or-equal inequalities, so the intervals contain their endpoints. These _closed_ endpoints are denoted on the number line with filled-in dots.

###[Set relations](part0008_split_003.md)

We’ll now introduce a useful graphical representation for set relations and set operations. Although sets are purely mathematical constructs and they have no “shape,” we can draw _Venn diagrams_ to visualize relationships between sets and different subsets.

Consider the notion of a set ![B](00409.jpeg) that is strictly contained in another set ![A](00667.jpeg). We write ![B \subset A](02007.jpeg) if ![\,\forall b \in B](02008.jpeg), ![b \in A](02009.jpeg) as well. Written in words, ![B \subset A](02007.jpeg) tells us every element of ![B](00409.jpeg) is also an element of ![A](00667.jpeg).

![b_subset_a_contained](02010.jpeg)

Figure 8.7: Venn diagram showing an example of the set relation ![B \subset A](02011.jpeg). The set ![B](00672.jpeg) is strictly contained in the set ![A](00671.jpeg).

[Figure 8.7](part0008_split_003.md) shows the picture that mathematicians have in mind when they say, “The set ![B](00409.jpeg) is contained in the set ![A](00667.jpeg).” The picture helps us visualize this abstract mathematical notion.

Mathematicians use two different symbols to describe set containment, in order to specify either a _strict_ containment relation or a _subset-or-equal_ relation. The two types of containment relations between sets are similar to the _less-than_ (![<](02012.jpeg)) and _less-than-or-equal_ (![\leq](02013.jpeg)) relations between numbers. A strict containment relation is denoted by the symbol ![\subset](01864.jpeg). We write ![B \subset A](02007.jpeg) if and only if every element of ![B](00409.jpeg) is also an element of ![A](00667.jpeg), and there exists at least one element of ![A](00667.jpeg) that is not an element of ![B](00409.jpeg). Using set notation, the previous sentence is expressed as

![B \subset A    \qquad    \Leftrightarrow    \qquad    \forall b \in B, b \in A \textrm{ and }  \exists a \in A  \textrm{ such that } a \notin B.](02014.jpeg)

For example, the expression ![E \subset \mathbb{Z}](02015.jpeg) shows that the even numbers are a strict subset of the integers. Every even number is an integer, but there exist integers that are not even (the odd numbers). Some mathematicians prefer the more descriptive symbol ![\subsetneq](02016.jpeg) to describe strict containment relations.

A subset-or-equal relation is denoted ![B \subseteq A](02017.jpeg). In writing ![B \subseteq A](02017.jpeg), a mathematician claims, “Every element of ![B](00409.jpeg) is also an element of ![A](00667.jpeg),” but makes no claim about the existence of elements that are contained in ![A](00667.jpeg) but not in ![B](00409.jpeg). The statement ![B \subset A](02007.jpeg) implies ![B \subseteq A](02017.jpeg); however, ![B \subseteq A](02017.jpeg) does not imply ![B \subset A](02007.jpeg). This is analogous to how ![b < a](02018.jpeg) implies ![b \leq a](02019.jpeg), but ![b \leq a](02019.jpeg) doesn’t imply ![b < a](02018.jpeg), since ![a](00014.jpeg) and ![b](00074.jpeg) could be equal.

###[Set operations](part0008_split_003.md)

Venn diagrams also help us visualize the subsets obtained from set operations.[Figure 8.8](part0008_split_003.md) illustrates the set union ![A \cup B](02020.jpeg), the set intersection ![A \cap B](02021.jpeg), and the set difference ![A \setminus B](02022.jpeg), for two sets ![A](00667.jpeg) and ![B](00409.jpeg).

The union ![A \cup B](02020.jpeg) describes all elements that are in either set ![A](00667.jpeg) or set ![B](00409.jpeg), or both. If ![e \in A \cup B](02023.jpeg), then ![e \in A](02024.jpeg) or ![e \in B](02025.jpeg).

Recall the set of even numbers ![E \subset \mathbb{Z}](02015.jpeg) and the set of odd numbers ![O \subset \mathbb{Z}](02026.jpeg) defined above. Since every integer is either an even number or an odd number, we know ![\mathbb{Z} \subseteq E \cup O](02027.jpeg). The union of two subsets is always contained within the parent set, so we also know ![E \cup O \subseteq \mathbb{Z}](02028.jpeg). Combining these facts, we can establish the equality ![E \cup O = \mathbb{Z}](02029.jpeg), which states the fact, “The combination of all even and odd numbers is the same as all integers.”

![set_operations_union_intersection_difference](02030.jpeg)

Figure 8.8: Venn diagrams showing different subsets obtained using the set operations: set union ![A \cup B](02031.jpeg), set intersection ![A \cap B](02032.jpeg), and set difference ![A \setminus B](02033.jpeg).

The set intersection ![A \cap B](02021.jpeg) and set difference ![A \setminus B](02022.jpeg) are also illustrated in[Figure 8.8](part0008_split_003.md). The intersection of two sets contains the elements that are part of both sets. The set difference ![A \setminus B](02022.jpeg) contains all the elements that are in ![A](00667.jpeg) but not in ![B](00409.jpeg).

Note the meaning of the conjunction “or” in English is ambiguous. The expression “in ![A](00667.jpeg) or ![B](00409.jpeg)” could be interpreted as either an “inclusive or,” meaning “in ![A](00667.jpeg) or ![B](00409.jpeg), or in both”—or as an “exclusive or,” meaning “in ![A](00667.jpeg) or ![B](00409.jpeg), but not both.” Mathematicians always use “or” in the inclusive sense, so ![A \cup B](02020.jpeg) denotes elements that are in ![A](00667.jpeg) or ![B](00409.jpeg), or in both sets. We can obtain an expression that corresponds to the “exclusive or” of two sets by taking the union of the sets and subtracting their intersection: ![(A \cup B) \setminus (A\cap B)](02034.jpeg).

####[Example 3: Set operations](part0008_split_003.md)

Consider the three sets ![A=\{a,b,c\}](02035.jpeg), ![B=\{b,c,d\}](02036.jpeg), and ![C=\{c,d,e\}](02037.jpeg). Using set operations, we can define new sets, such as

![A \cup B =  \{a,b,c,d\},     \quad      A \cap B =   \{b,c\},     \quad     \textrm{and}      \quad     A \setminus B =  \{a\},](02038.jpeg)

which correspond to elements in either ![A](00667.jpeg) or ![B](00409.jpeg), the set of elements in ![A](00667.jpeg) and ![B](00409.jpeg), and the set of elements in ![A](00667.jpeg) but not in ![B](00409.jpeg), respectively.

We can also construct expressions involving three sets:

![A \cup B \cup C = \{a,b,c,d,e\},     \qquad     \quad     A \cap B \cap C = \{c\}.](02039.jpeg)

And we can write more elaborate set expressions, like

![(A \cup B ) \setminus C = \{a,b\},](02040.jpeg)

which is the set of elements that are in ![A](00667.jpeg) or ![B](00409.jpeg) but not in ![C](00266.jpeg).

Another example of a complicated set expression is

![(A \cap B) \cup (B\cap C) = \{b,c,d\},](02041.jpeg)

which describes the set of elements in both ![A](00667.jpeg) and ![B](00409.jpeg) or in both ![B](00409.jpeg) and ![C](00266.jpeg). As you can see, set notation is a compact, precise language for writing complicated set expressions.

####[Example 4: Word problem](part0008_split_003.md)

A startup is looking to hire student interns for the summer. Define ![C](00266.jpeg) to be the subset of students who are good with computers, ![M](01424.jpeg) the subset of students who know math, ![D](01443.jpeg) the students with design skills, and ![L](02042.jpeg) the students with good language skills.

Using set notation, we can specify different subsets of the students the startup might hire. Let’s say the startup is a math textbook publisher; they want to hire students from the set ![M \cap L](02043.jpeg)—the students who are good at math and who also have good language skills. A startup that builds websites needs both designers and coders, and therefore would choose students from the set ![D \cup C](02044.jpeg).

###[New vocabulary](part0008_split_003.md)

The specialized notation used by mathematicians can be difficult to get used to. You must learn how to read symbols like ![\exists](01866.jpeg), ![\subset](01864.jpeg), ![|](01978.jpeg), and ![\in](01863.jpeg) and translate their meaning in the sentence. Indeed, learning advanced mathematics notation is akin to learning a new language.

To help you practice the new vocabulary, we’ll look at a simple mathematical proof that makes use of the new symbols.

####[Simple proof example](part0008_split_003.md)

**Claim:** Given ![J(n)=3n+2-n](02045.jpeg), ![J(n) \in E](02046.jpeg) for all ![n \in \mathbb{Z}](02047.jpeg).

The claim is that the function ![J(n)](02048.jpeg) outputs an even number, whenever the input ![n](00054.jpeg) is an integer. To prove this claim, we have to show that the expression ![3n+2-n](02049.jpeg) is even for all numbers ![n \in \mathbb{Z}](02047.jpeg).

We want to show ![J(n) \in E](02046.jpeg) for all ![n \in \mathbb{Z}](02047.jpeg). Let’s first review the definition of the set of even numbers ![E \eqdef \{ m \in \mathbb{Z} \; | \; m=2n, n \in \mathbb{Z} \}](02050.jpeg). A number is even if it is equal to ![2n](01975.jpeg) for some integer ![n](00054.jpeg). Next let’s simplify the expression for ![J(n)](02048.jpeg) as follows:

![J(n)=3n+2-n = 2n +2 = 2(n+1).](02051.jpeg)

Observe that the number ![(n+1)](02052.jpeg) is always an integer whenever ![n](00054.jpeg) is an integer. Since the output of ![J(n)=2(n+1)](02053.jpeg) is equal to ![2m](02054.jpeg) for some integer ![m](00053.jpeg), we’ve proven that ![J(n) \in E](02046.jpeg), for all ![n \in \mathbb{Z}](02047.jpeg).

###[Sets as solutions to equations](part0008_split_003.md)

Another context where sets come up is when describing solutions to equations and inequalities. In[Section 1.1](part0001_split_001.md) we learned how to solve for the unknown ![x](00015.jpeg) in equations. To solve the equation ![f(x)=c](02055.jpeg) is to find all the values of ![x](00015.jpeg) that satisfy this equation. For simple equations like ![x-3=6](02056.jpeg), the solution is a single number ![x=9](00314.jpeg), but more complex equations can have multiple solutions. For example, the solution to the equation ![x^2=4](02057.jpeg) is the set ![\{-2,2\}](02058.jpeg), since both ![x=-2](00878.jpeg) and ![x=2](00380.jpeg) satisfy the equation.

Please update your definition of the math verb “to solve” (an equation) to include the new notion of a _solution set_—the set of values that satisfy the equation. A solution set is the mathematically precise way to describe an equation’s solutions:

-   The solution set to the equation ![x-3=6](02056.jpeg) is the set ![\{9\}](02059.jpeg).
-   The solution set for the equation ![x^2=4](02057.jpeg) is the set ![\{-2,2\}](02058.jpeg).
-   The solution set of ![\sin(x)=0](02060.jpeg) is the set ![\{x \; | \;  x = \pi n, \forall n \in \mathbb{Z}\}](02061.jpeg).
-   The solution set for the equation ![\sin(x)=2](02062.jpeg) is ![\emptyset](01947.jpeg) (the empty set), since there is no number ![x](00015.jpeg) that satisfies the equation.

The `SymPy` function `solve` returns the solutions of equations as a list. To solve the equation ![f(x)=c](02055.jpeg) using `SymPy`, we first rewrite it as expression that equals zero ![f(x)-c=0](02063.jpeg), then call the function `solve`:

 >>> solve(x-3 -6, x)       # usage: solve(expr, var)
 \[9\]
 
 >>> solve(x\*\*2 -4, x)
 \[-2, 2\]
 
 >>> solve(sin(x), x)
 \[0, pi\]                    # found only solutions in \[0,2\*pi) 
 
 >>> solve(sin(x) -2, x)
 \[\]                         # empty list = empty set		

In the next section we’ll learn how the notion of a solution set is used for describing the solutions to systems of equations.

####[Solution sets to systems of equations](part0008_split_003.md)

Let’s revisit what we learned in[Section 8.1](part0008_split_001.md) about the solutions to systems of linear equations, and define their solution sets more precisely. The solution set for the system of equations

![\begin{align*}         a_1x + b_1y     & =  c_1, \\         a_2x + b_2y     & =  c_2,    \end{align*}](01874.jpeg)

corresponds to the intersection of two sets:

![\underbrace{      \{ (x,y) \in \mathbb{R}^2 \; | \;  a_1x+b_1y=c_1 \}     }_{\ell_1}     \;  \cap \;      \underbrace{      \{ (x,y) \in \mathbb{R}^2 \; | \;  a_2x+b_2y=c_2 \}     }_{\ell_2}.](02064.jpeg)

Recall that the lines ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg) are the geometric interpretation of these sets. Each line corresponds to a set of coordinate pairs ![(x,y)](00630.jpeg) that satisfy the equation of the line. The solution to the system of equations is the set of points at the intersection of the two lines ![\ell_1 \cap \ell_2](02065.jpeg). Note the word _intersection_ is used in two different mathematical contexts: the solution is the _set intersection_ of two sets, and also the _geometric intersection_ of two lines.

Let’s take advantage of this correspondence between set intersections and geometric line intersections to understand the solutions to systems of equations in a little more detail. In the next three sections, we’ll look at three possible cases that can occur when trying to solve a system of two linear equations in two unknowns. So far we’ve only discussed Case A, which occurs when the two lines intersect at a point, as in the example shown in[Figure 8.9](part0008_split_003.md). To fully understand the possible solutions to a system of equations, we need to think about all other cases; like Case B when ![\ell_1 \cap \ell_2 = \emptyset](02066.jpeg) as in[Figure 8.10](part0008_split_003.md), and Case C when ![\ell_1 \cap \ell_2 = \ell_1 = \ell_2](02067.jpeg) as in[Figure 8.11](part0008_split_003.md).

#####[Case A: One solution.](part0008_split_003.md)

When the lines ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg) are non-parallel, they will intersect at a point as shown in[Figure 8.9](part0008_split_003.md). In this case, the solution set to the system of equations contains a single point:

![\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=2 \}      \;  \cap \;       \{ (x,y) \in \mathbb{R}^2 \; | \;  x=1 \}      =      \{ (1,\tfrac{1}{2}) \}.](02068.jpeg)

![systems_of_equations__solution_sets_case_A](02069.jpeg)

Figure 8.9: Case A: The intersection of the lines with equations ![x+2y=2](02070.jpeg) and ![x=1](00764.jpeg) is the point ![(1,\frac{1}{2}) \in \mathbb{R}^2](02071.jpeg).

#####[Case B: No solution.](part0008_split_003.md)

If the lines ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg) are parallel then they will never intersect. The intersection of these lines is the empty set:

![\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=2 \}      \;  \cap \;       \{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=4 \}      =      \emptyset.](02072.jpeg)

Think about it—there is no point ![(x,y)](00630.jpeg) that lies on both ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg). Using algebra terminology, we say this system of equations has no solution, since there are no numbers ![x](00015.jpeg) and ![y](00018.jpeg) that satisfy both equations.

![systems_of_equations__solution_sets_case_B](02073.jpeg)

Figure 8.10: Case B: The lines with equations ![x+2y=2](02070.jpeg) and ![x+2y=4](02074.jpeg) are parallel and do not intersect. Using set notation, we can describe the solution set as ![\emptyset](02075.jpeg) (the empty set).

#####[Case C: Infinitely many solutions.](part0008_split_003.md)

If the lines ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg) are parallel and overlapping then they intersect everywhere. This case occurs when one of the equations in a system of equations is a multiple of the other equation, as in the case of equations ![x+2y=2](01895.jpeg) and ![3x+6y=6](02076.jpeg). The lines ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg) that correspond to these equations are shown in[Figure 8.11](part0008_split_003.md). Any point ![(x,y)](00630.jpeg) that satisfies ![x+2y=2](01895.jpeg) also satisfies ![3x+6y=6](02076.jpeg). Since both equations describe the same geometric line, the intersection of the two lines is equal to the lines: ![\ell_1 \cap \ell_2 = \ell_1 = \ell_2](02067.jpeg). In this case, the solution to the system of equations is described by the set ![\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=2 \}](02077.jpeg).

![systems_of_equations__solution_sets_case_C](02078.jpeg)

Figure 8.11: Case C: the line ![\ell_1](01907.jpeg) described by equation ![x+2y=2](02070.jpeg) and the line ![\ell_2](01908.jpeg) described by equation ![3x+6y=6](02079.jpeg) correspond to the same line in the Cartesian plane. The intersection of these lines is the set ![\{ (x,y) \in \mathbb{R}^2 \; | \;  x+2y=2 \} = \ell_1 = \ell_2](02080.jpeg).

We need to consider all three cases when thinking about the solutions to systems of linear equations: the solution set can be a point (Case A), the empty set (Case B), or a line (Case C). Observe that the same mathematical notion (a set) is able to describe the solutions in all three cases even though the solutions correspond to very different geometric objects. In Case A the solution is a set that contains a single point ![\{ (x,y) \}](02081.jpeg). In Case B the solution is the empty set ![\emptyset](01947.jpeg). And in Case C the solution set is described by the infinite set ![\{ (x,y) \in \mathbb{R}^2 \; | \;  ax+by=c \}](02082.jpeg), which corresponds to a line ![\ell](01143.jpeg) in the Cartesian plane. I hope you’ll agree with me that set notation is useful for describing mathematical concepts precisely and for handling solutions to linear equations.

Sets are also useful for describing the solutions to inequalities, which is what we’ll learn about next.

####[Inequalities](part0008_split_003.md)

In this section, we’ll learn how to solve inequalities. The solution set to an inequality is an _interval_—a subset of the number line. Consider the inequality ![x^2 \leq 4](02083.jpeg), which is equivalent to asking the question, “For which values of ![x](00015.jpeg) is ![x^2](00026.jpeg) less than or equal to ![4](00136.jpeg)?” The answer to this question is the interval ![[-2,2] = \{ x\in \mathbb{R} \; | \; -2 \leq x \leq 2 \, \}](02084.jpeg).

Working with inequalities is essentially the same as working with their endpoints. To solve the inequality ![x^2 \leq 4](02083.jpeg), we first solve ![x^2 = 4](02057.jpeg) to find the endpoints and then use trial and error to figure out which part of the space to the left and right of the endpoints satisfies the inequality.

It’s important to distinguish the different types of inequality conditions. The four different types of inequalities are

-   ![f(x) <  g(x)](02085.jpeg): a strict inequality. The function ![f(x)](00288.jpeg) is always _strictly less than_ the function ![g(x)](01031.jpeg).
-   ![f(x) \leq g(x)](02086.jpeg): the function ![f(x)](00288.jpeg) is _less than or equal to_ ![g(x)](01031.jpeg).
-   ![f(x) > g(x)](02087.jpeg): ![f(x)](00288.jpeg) is _strictly greater than_ ![g(x)](01031.jpeg).
-   ![f(x) \geq g(x)](02088.jpeg): ![f(x)](00288.jpeg) is _greater than or equal to_ ![g(x)](01031.jpeg).

Depending on the type of inequality, the answer will be either a _open_ or _closed_ interval.

To solve inequalities we use the techniques we learned for solving equations: we perform simplifying steps **on both sides of the inequality** until we obtain the answer. The only new aspect when dealing with inequalities is the following. When multiplying an inequality by a negative number on both sides, we must flip the direction of the inequality:

![f(x) \leq g(x) \qquad \Rightarrow  \qquad -f(x) \geq -g(x).](02089.jpeg)

#####[Example 5](part0008_split_003.md)

To solve the inequality ![7-x \leq 5](02090.jpeg) we must _dig_ toward the ![x](00015.jpeg) and _undo_ all the operations that stand in our way:

![\begin{align*}      7-x      &\leq 5,  \\      (-x) + 7    &\leq 5,  \\      (-x) + 7 \; \color{blue}{-7} &\leq 5 \; \color{blue}{-7},  \\      -x      &\leq -2,  \\      x      &\geq 2.     \end{align*}](02091.jpeg)

To obtain the second line we simply rewrote the order of operations on the left side of the inequality. In the third line we subtracted ![7](00157.jpeg) from both sides of the inequality to undo the ![+7](02092.jpeg) operation. In the last step we multiplied both sides of the inequality by ![-1](00308.jpeg), which had the effect of changing the inequality from ![\leq](02013.jpeg) to ![\geq](02093.jpeg). The solution set to the inequality ![7-x \leq 5](02090.jpeg) is the interval ![[2,\infty)](02094.jpeg).

#####[Example 6](part0008_split_003.md)

To solve the inequality ![x^2 \leq 4](02083.jpeg), we must undo the quadratic function by taking the square root of both sides of the inequality. Note the equation ![x^2=4](02057.jpeg) has two solutions: ![x=-2](00878.jpeg) and ![x=2](00380.jpeg). Similarly, we’ll need to consider two separate cases for the inequality conditions. Simplifying the inequality ![x^2 \leq 4](02083.jpeg) by taking the square root on both sides results in two inequality conditions

![x \geq -2  \qquad \textrm{and} \qquad x \leq 2,](02095.jpeg)

which we can express more concisely as ![-2 \leq x \leq 2](02096.jpeg). If ![x](00015.jpeg) is a negative number, it must be greater than ![-2](00125.jpeg); and if ![x](00015.jpeg) is a positive number, it must be less than ![2](00103.jpeg) in order for ![x^2 \leq 4](02083.jpeg). The solution set for the inequality ![x^2 \leq 4](02083.jpeg) is the interval ![[-2,2] = \{ x\in \mathbb{R}\; | \; -2 \leq x \leq 2 \}](02097.jpeg). Note the solution is a closed interval (square brackets), which means the endpoints are included.

The best way to convince yourself that the above algebraic reasoning is correct is to think about the graph of the function ![f(x)=x^2](00298.jpeg). The inequality ![x^2 \leq 4](02083.jpeg) corresponds to the condition ![f(x)\leq 4](02098.jpeg). For what values of ![x](00015.jpeg) is the graph of the function ![f(x)](00288.jpeg) below the line with equation ![y=4](02099.jpeg)?

As you can see, solving inequalities is no more complicated than solving equations. You can think about an inequality in terms of its endpoints, which correspond to the equality conditions. Whenever things get complicated (as in Example 6), you can sketch the function graphs for the different terms in the inequality and visually determine the appropriate directions for the inequality signs.

###[Sets related to functions](part0008_split_003.md)

A function that takes real variables as inputs and produces real numbers as outputs is denoted ![f : \mathbb{R} \to \mathbb{R}](00719.jpeg). The _domain_ of a function is the set of all possible inputs to the function that produce an output:

![\textrm{Dom}(f) \eqdef \{ x \in \mathbb{R} \; | \; f(x) \in\mathbb{R} \}.](02100.jpeg)

Inputs for which the function is undefined are not part of the domain. For instance the function ![f(x)=\sqrt{x}](00337.jpeg) is not defined for negative inputs, so we have ![\textrm{Dom}(f) = \mathbb{R}_+](02101.jpeg).

The _image_ of a function is the set of all possible outputs of the function:

![\textrm{Im}(f) \eqdef \{ y \in \mathbb{R} \; | \; \exists x\in\mathbb{R},\; y=f(x) \}.](02102.jpeg)

For example, the function ![f(x)=x^2](00298.jpeg) has the image set ![\textrm{Im}(f) = \mathbb{R}_+](02103.jpeg) since the outputs it produces are always nonnegative.

###[Discussion](part0008_split_003.md)

Knowledge of the precise mathematical jargon introduced in this section is not crucial to understanding basic mathematics. That said, I wanted to expose you to some technical math notation here because this is the language in which mathematicians think and communicate. Most advanced math textbooks will assume you understand technical math notation, so it’s good to be prepared.

###[Exercises](part0008_split_003.md)

E8.7 Given the three sets ![A=\{1,2,3,4,5,6,7\}](02104.jpeg), ![B=\{1,3,5\}](02105.jpeg), and ![C=\{2,4,6\}](02106.jpeg), compute the following set expressions.

**a)** ![A \setminus B](02022.jpeg) **b)** ![B \cup C](02107.jpeg) **c)** ![A \cap B](02021.jpeg) **d)** ![B \cap C](02108.jpeg)

**e)** ![A \!\cup \!B \!\cup \!C](02109.jpeg) **f)** ![A  \setminus (B\!\cup\!C)](02110.jpeg) **g)** ![(A  \setminus B) \!\cup \!C](02111.jpeg) **h)** ![A\!\cap\!B\!\cap\!C](02112.jpeg)

E8.8 Find the values of ![x](00015.jpeg) that satisfy the following inequalities.

**a)** ![2x < 3](02113.jpeg) **b)** ![-4x \geq 20](02114.jpeg) **c)** ![|2x-3|<5](02115.jpeg)

**d)** ![3x + 3 < 5x  - 5](02116.jpeg) **e)** ![\frac{1}{2}x-2 \geq \frac{1}{3}](02117.jpeg) **f)** ![(x+1)^2 \geq 9](02118.jpeg)

Express your answer as an interval with appropriate endpoints.
