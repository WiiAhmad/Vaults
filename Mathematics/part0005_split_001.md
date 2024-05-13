Chapter 5    

##[5.1 Functions](part0005_split_001.md)

We need to have a relationship talk. We need to talk about functions. We use functions to describe the relationships between variables. In particular, functions describe how one variable _depends_ on another.

For example, the revenue ![R](00268.jpeg) from a music concert depends on the number of tickets sold ![n](00054.jpeg). If each ticket costs ![\$25](00657.jpeg), the revenue from the concert can be written _as a function of_ ![n](00054.jpeg) as follows: ![R(n) = 25n](00658.jpeg). Solving for ![n](00054.jpeg) in the equation ![R(n)=7000](00659.jpeg) tells us the number of ticket sales needed to generate ![\$7000](00660.jpeg) in revenue. This is a simple model of a function; as your knowledge of functions builds, you’ll learn how to build more detailed models of reality. For instance, if you need to include a ![5\%](00661.jpeg) processing charge for issuing the tickets, you can update the revenue model to ![R(n) = 0.95\cdot25\cdot n](00662.jpeg). If the estimated cost of hosting the concert is ![C=\$2000](00663.jpeg), then the profit from the concert ![P](00267.jpeg) can be modelled as

![\begin{align*}   P(n)  &= R(n) \; - \; C     \\    &= 0.95\cdot \$25\cdot n \; -  \;  \$2000  \end{align*}](00664.jpeg)

The function ![P(n)=23.75n-2000](00665.jpeg) models the profit from the concert as a function of the number of tickets sold. This is a pretty good model already, and you can always update it later as you learn more information.

The more functions you know, the more tools you have for modelling reality. To “know” a function, you must be able to understand and connect several of its aspects. First you need to know the function’s mathematical **definition**, which describes exactly what the function does. Starting from the function’s definition, you can use your existing math skills to find the function’s **properties**. You must also know the **graph** of the function; what the function looks like if you plot ![x](00015.jpeg) versus ![f(x)](00288.jpeg) in the[Cartesian plane](part0004_split_001.md). It’s also a good idea to remember the **values** of the function for some important inputs. Finally—and this is the part that takes time—you must learn about the function’s **relations** to other functions.

###[Definitions](part0005_split_001.md)

A _function_ is a mathematical object that takes numbers as inputs and produces numbers as outputs. We use the notation

![f \colon A \to B](00666.jpeg)

to denote a function from the input set ![A](00667.jpeg) to the output set ![B](00409.jpeg). In this book, we mostly study functions that take real numbers as inputs and give real numbers as outputs: ![f\colon\mathbb{R} \to \mathbb{R}](00668.jpeg).

![functions-definition](00669.jpeg)

Figure 5.1: An abstract representation of a function ![f](00670.jpeg) from the set ![A](00671.jpeg) to the set ![B](00672.jpeg). The function ![f](00670.jpeg) is the arrow which _maps_ each input ![x](00632.jpeg) in ![A](00671.jpeg) to an output ![f(x)](00673.jpeg) in ![B](00672.jpeg). The output of the function ![f(x)](00673.jpeg) is also denoted ![y](00674.jpeg).

A function is not a number; rather, it is a _mapping_ from numbers to numbers. We say “![f](00287.jpeg) maps ![x](00015.jpeg) to ![f(x)](00288.jpeg).” For any input ![x](00015.jpeg), the output value of ![f](00287.jpeg) for that input is denoted ![f(x)](00288.jpeg), which is read as “![f](00287.jpeg) of ![x](00015.jpeg).”

We’ll now define some fancy technical terms used to describe the input and output sets of functions.

-   ![A](00667.jpeg): the _source set_ of the function describes the types of numbers that the function takes as inputs.
-   ![\textrm{Dom}(f)](00675.jpeg): the _domain_ of a function is the set of allowed input values for the function.
    
-   ![B](00409.jpeg): the _target set_ of a function describes the type of outputs the function has. The target set is sometimes called the _codomain_.
-   ![\textrm{Im}(f)](00676.jpeg): the _image_ of the function is the set of all possible output values of the function. The image is sometimes called the _range_.

See[Figure 5.2](part0005_split_001.md) for an illustration of these concepts. The purpose of introducing all this math terminology is so we’ll have words to distinguish the general types of inputs and outputs of the function (real numbers, complex numbers, vectors) from the specific properties of the function like its domain and image.

![functions_sets_domain_image](00677.jpeg)

Figure 5.2: Illustration of the input and output sets of a function ![f \colon A \to B](00678.jpeg). The _source set_ is denoted ![A](00671.jpeg) and the _domain_ is denoted ![\textrm{Dom}(f)](00679.jpeg). Note that the function’s domain is a subset of its source set. The _target set_ is denoted ![B](00672.jpeg) and the _image_ is denoted ![\textrm{Im}(f)](00680.jpeg). The image is a subset of the target set.

Let’s look at an example to illustrate the difference between the source set and the domain of a function. Consider the square root function ![f \colon \mathbb{R} \to \mathbb{R}](00668.jpeg) defined as ![f(x) = \sqrt{x}](00337.jpeg), which is shown in[Figure 5.3](part0005_split_001.md). The source set of ![f](00287.jpeg) is the set of real numbers—yet only nonnegative real numbers are allowed as inputs, since ![\sqrt{x}](00681.jpeg) is not defined for negative numbers. Therefore, the domain of the square root function is only the nonnegative real numbers: ![\textrm{Dom}(f) = \mathbb{R}_+ = \{x \in \mathbb{R} \; | \; x \geq 0 \}](00682.jpeg). Knowing the domain of a function is essential to using the function correctly. In this case, whenever you use the square root function, you need to make sure that the inputs to the function are nonnegative numbers.

The complicated-looking expression between the curly brackets uses _set notation_ to define the set of nonnegative numbers ![\mathbb{R}_+](00683.jpeg). In words, the expression ![\mathbb{R}_+ = \{x \in \mathbb{R} \; | \; x \geq 0 \}](00684.jpeg) states that “![\mathbb{R}_+](00683.jpeg) is defined as the set of all real numbers ![x](00015.jpeg) such that ![x](00015.jpeg) is greater than or equal to zero.” We’ll discuss set notation in more detail in[Section 8.3](part0008_split_003.md). For now, you can just remember that ![\mathbb{R}_+](00683.jpeg) represents the set of nonnegative real numbers.

![functions_sets_domain_image-sqrt_x](00685.jpeg)

Figure 5.3: The input and output sets of the function ![f(x) = \sqrt{x}](00686.jpeg). The domain of ![f](00670.jpeg) is the set of nonnegative real numbers ![\mathbb{R}_+](00687.jpeg) and its image is ![\mathbb{R}_+](00687.jpeg).

To illustrate the difference between the image of a function and its target set, let’s look at the function ![f(x)=x^2](00298.jpeg) shown in[Figure 5.4](part0005_split_001.md). The quadratic function is of the form ![f\colon\mathbb{R} \to \mathbb{R}](00668.jpeg). The function’s source set is ![\mathbb{R}](00060.jpeg) (it takes real numbers as inputs) and its target set is ![\mathbb{R}](00060.jpeg) (the outputs are real numbers too); however, not all real numbers are possible outputs. The _image_ of the function ![f(x)=x^2](00298.jpeg) consists only of the nonnegative real numbers ![\mathbb{R}_+ = \{y \in \mathbb{R} \; | \; y \geq 0 \}](00688.jpeg), since ![f(x)\geq 0](00689.jpeg) for all ![x](00015.jpeg).

![functions_sets_domain_image-x_squared](00690.jpeg)

Figure 5.4: The function ![f(x) = x^2](00652.jpeg) is defined for all reals: ![\textrm{Dom}(f) = \mathbb{R}](00691.jpeg). The image of the function is the set of nonnegative real numbers: ![\textrm{Im}(f) = \mathbb{R}_+](00692.jpeg).

###[Function properties](part0005_split_001.md)

We’ll now introduce some additional terminology for describing three important function properties. Every function is a mapping from a source set to a target set, but what kind of mapping is it?

-   A function is _injective_ if it maps two different inputs to two different outputs. If ![x_1](00455.jpeg) and ![x_2](00456.jpeg) are two input values that are not equal ![x_1 \neq x_2](00693.jpeg), then the output values of an injective function will also not be equal ![f(x_1) \neq f(x_2)](00694.jpeg).
-   A function is _surjective_ if its image is equal to its target set. For every output ![y](00018.jpeg) in the target set of a surjective function, there is at least one input ![x](00015.jpeg) in its domain such that ![f(x) = y](00297.jpeg).
-   A function is _bijective_ if it is both injective and surjective.

I know this seems like a lot of terminology to get acquainted with, but it’s important to have names for these function properties. We’ll need this terminology to give a precise definition of the _inverse function_ in the next section.

#####[Injective property](part0005_split_001.md)

We can think of _injective_ functions as pipes that transport fluids between containers. Since fluids cannot be compressed, the “output container” must be at least as large as the “input container.” If there are two distinct points ![x_1](00455.jpeg) and ![x_2](00456.jpeg) in the input container of an injective function, then there will be two distinct points ![f(x_1)](00695.jpeg) and ![f(x_2)](00696.jpeg) in the output container of the function as well. In other words, injective functions don’t smoosh things together.

In contrast, a function that doesn’t have the injective property can map several different inputs to the same output value. The function ![f(x) = x^2](00298.jpeg) is not injective since it sends inputs ![x](00015.jpeg) and ![-x](00299.jpeg) to the same output value ![f(x)=f(-x)=x^2](00697.jpeg), as illustrated in[Figure 5.4](part0005_split_001.md).

The maps-distinct-inputs-to-distinct-outputs property of injective functions has an important consequence: given the output of an injective function ![y](00018.jpeg), there is only one input ![x](00015.jpeg) such that ![f(x)=y](00297.jpeg). If a second input ![x'](00698.jpeg) existed that also leads to the same output ![f(x)=f(x')=y](00699.jpeg), then the function ![f](00287.jpeg) wouldn’t be injective. For each of the outputs ![y](00018.jpeg) of an injective function ![f](00287.jpeg), there is a _unique_ input ![x](00015.jpeg) such that ![f(x)=y](00297.jpeg). In other words, injective functions have a unique-input-for-each-output property.

#####[Surjective property](part0005_split_001.md)

A function is _surjective_ if its outputs cover the entire target set: every number in the target set is a possible output of the function for some input. For example, the function ![f \colon \mathbb{R} \to \mathbb{R}](00668.jpeg) defined by ![f(x) = x^3](00700.jpeg) is surjective: for every number ![y](00018.jpeg) in the target set ![\mathbb{R}](00060.jpeg), there is an input ![x](00015.jpeg), namely ![x=\sqrt[3]{y}](00701.jpeg), such that ![f(x)=y](00297.jpeg). The function ![f(x) = x^3](00700.jpeg) is surjective since its image is equal to its target set, ![\textrm{Im}(f) = \mathbb{R}](00702.jpeg), as shown in[Figure 5.5](part0005_split_001.md).

On the other hand, the function ![f \colon \mathbb{R} \to \mathbb{R}](00668.jpeg) defined by the equation ![f(x) = x^2](00298.jpeg) is not surjective since its image is only the nonnegative numbers ![\mathbb{R}_+](00683.jpeg) and not the whole set of real numbers (see[Figure 5.4](part0005_split_001.md)). The outputs of this function do not include the negative numbers of the target set, because there is no real number ![x](00015.jpeg) that can be used as an input to obtain a negative output value.

![functions_sets_domain_image-x_cubed](00703.jpeg)

Figure 5.5: For the function ![f(x) = x^3](00704.jpeg) the image is equal to the target set of the function, ![\textrm{Im}(f) = \mathbb{R}](00705.jpeg), therefore the function ![f](00670.jpeg) is surjective. The function ![f](00670.jpeg) maps two different inputs ![x_1 \neq x_2](00706.jpeg) to two different outputs ![f(x_1) \neq f(x_2)](00707.jpeg), so ![f](00670.jpeg) is injective. Since ![f](00670.jpeg) is both injective and surjective, it is a _bijective_ function.

#####[Bijective property](part0005_split_001.md)

A function is bijective if it is both injective and surjective. When a function ![f:A \to B](00708.jpeg) has both the injective and surjective properties, it defines a _one-to-one correspondence_ between the numbers of the source set ![A](00667.jpeg) and the numbers of the target set ![B](00409.jpeg). This means for every input value ![x](00015.jpeg), there is exactly one corresponding output value ![y](00018.jpeg), and for every output value ![y](00018.jpeg), there is exactly one input value ![x](00015.jpeg) such that ![f(x)=y](00297.jpeg). An example of a bijective function is the function ![f \colon \mathbb{R} \to \mathbb{R}](00668.jpeg) defined by ![f(x) = x^3](00700.jpeg) (see[Figure 5.5](part0005_split_001.md)). For every input ![x](00015.jpeg) in the source set ![\mathbb{R}](00060.jpeg), the corresponding output ![y](00018.jpeg) is given by ![y=f(x)=x^3](00709.jpeg). For every output value ![y](00018.jpeg) in the target set ![\mathbb{R}](00060.jpeg), the corresponding input value ![x](00015.jpeg) is given by ![x=\sqrt[3]{y}](00701.jpeg).

A function is not bijective if it lacks one of the required properties. Examples of non-bijective functions are ![f(x)=\sqrt{x}](00337.jpeg), which is not surjective and ![f(x)=x^2](00298.jpeg), which is neither injective nor surjective.

#####[Counting solutions](part0005_split_001.md)

Another way to understand the injective, surjective, and bijective properties of functions is to think about the solutions to the equation ![f(x)=b](00710.jpeg), where ![b](00074.jpeg) is a number in the target set ![B](00409.jpeg). The function ![f](00287.jpeg) is injective if the equation ![f(x)=b](00710.jpeg) has _at most one_ solution for every number ![b](00074.jpeg). The function ![f](00287.jpeg) is surjective if the equation ![f(x)=b](00710.jpeg) has _at least one_ solution for every number ![b](00074.jpeg). If the function ![f](00287.jpeg) is bijective then it is both injective and surjective, which means the equation ![f(x)=b](00710.jpeg) has _exactly one_ solution.

###[Inverse function](part0005_split_001.md)

We used inverse functions repeatedly in previous chapters, each time describing the inverse function informally as an “undo” operation. Now that we have learned about bijective functions, we can give a the precise definition of the inverse function and explain some of the details we glossed over previously.

Recall that a _bijective_ function ![f:A \to B](00708.jpeg) is a _one-to-one correspondence_ between the numbers in the source set ![A](00667.jpeg) and numbers in the target set ![B](00409.jpeg): for every output ![y](00018.jpeg), there is exactly one corresponding input value ![x](00015.jpeg) such that ![f(x)=y](00297.jpeg). The _inverse function_, denoted ![f^{-1}](00289.jpeg), is the function that takes any output value ![y](00018.jpeg) in the set ![B](00409.jpeg) and finds the corresponding input value ![x](00015.jpeg) that produced it ![f^{-1}(y) = x](00711.jpeg).

![functions-inverse](00712.jpeg)

Figure 5.6: The inverse ![f^{-1}](00713.jpeg) undoes the operation of the function ![f](00670.jpeg).

For every bijective function ![f:A \to B](00708.jpeg), there exists an inverse function ![f^{-1}: B \to A](00714.jpeg) that performs the _inverse mapping_ of ![f](00287.jpeg). If we start from some ![x](00015.jpeg), apply ![f](00287.jpeg), and then apply ![f^{-1}](00289.jpeg), we’ll arrive—full circle—back to the original input ![x](00015.jpeg):

![f^{-1}\!\big( \; f(x) \; \big) = x.](00715.jpeg)

In[Figure 5.6](part0005_split_001.md) the function ![f](00287.jpeg) is represented as a forward arrow, and the inverse function ![f^{-1}](00289.jpeg) is represented as a backward arrow that puts the value ![f(x)](00288.jpeg) back to the ![x](00015.jpeg) it came from.

Similarly, we can start from any ![y](00018.jpeg) in the set ![B](00409.jpeg) and apply ![f^{-1}](00289.jpeg) followed by ![f](00287.jpeg) to get back to the original ![y](00018.jpeg) we started from:

![f\!\big( \; f^{-1}(y) \; \big) = y.](00716.jpeg)

In words, this equation tells us that ![f](00287.jpeg) is the “undo” operation for the function ![f^{-1}](00289.jpeg), the same way ![f^{-1}](00289.jpeg) is the “undo” operation for ![f](00287.jpeg).

If a function is missing the injective property or the surjective property then it isn’t bijective and it doesn’t have an inverse. Without the injective property, there could be two inputs ![x](00015.jpeg) and ![x'](00698.jpeg) that both produce the same output ![f(x)=f(x')=y](00699.jpeg). In this case, computing ![f^{-1}(y)](00296.jpeg) would be impossible since we don’t know which of the two possible inputs ![x](00015.jpeg) or ![x'](00698.jpeg) was used to produce the output ![y](00018.jpeg). Without the surjective property, there could be some output ![y'](00717.jpeg) in ![B](00409.jpeg) for which the inverse function ![f^{-1}](00289.jpeg) is not defined, so the equation ![f(f^{-1}(y)) = y](00718.jpeg) would not hold for all ![y](00018.jpeg) in ![B](00409.jpeg). The inverse function ![f^{-1}](00289.jpeg) exists only when the function ![f](00287.jpeg) is bijective.

Wait a minute! We know the function ![f(x) = x^2](00298.jpeg) is not bijective and therefore doesn’t have an inverse, but we’ve repeatedly used the square root function as an inverse function for ![f(x) = x^2](00298.jpeg). What’s going on here? Are we using a double standard like a politician that espouses one set of rules publicly, but follows a different set of rules in their private dealings? Is mathematics corrupt?

Don’t worry, mathematics is not corrupt—it’s all legit. We can use inverses for non-bijective functions by imposing _restrictions_ on the source and target sets. The function ![f(x) = x^2](00298.jpeg) is not bijective when defined as a function ![f: \mathbb{R} \to \mathbb{R}](00719.jpeg), but it _is_ bijective if we define it as a function from the set of nonnegative numbers to the set of nonnegative numbers, ![f: \mathbb{R}_+ \to \mathbb{R}_+](00720.jpeg). Restricting the source set to ![\mathbb{R}_+ = \{x \in \mathbb{R} \; | \; x \geq 0 \}](00684.jpeg) makes the function injective, and restricting the target set to ![\mathbb{R}_+](00683.jpeg) also makes the function surjective. The function ![f: \mathbb{R}_+ \to \mathbb{R}_+](00720.jpeg) defined by the equation ![f(x) = x^2](00298.jpeg) is bijective and its inverse is ![f^{-1}(y) = \sqrt{y}](00301.jpeg).

It’s important to keep track the of restrictions on the source set we applied when solving equations. For example, solving the equation ![x^2 = c](00304.jpeg) by restricting the solution space to nonnegative numbers will give us only the positive solution ![x = \sqrt{c}](00721.jpeg). We have to manually add the negative solution ![x = -\sqrt{c}](00303.jpeg) in order to obtain the complete solutions: ![x = \sqrt{c}](00721.jpeg) or ![x = -\sqrt{c}](00303.jpeg), which is usually written ![x = \pm \sqrt{c}](00305.jpeg). The possibility of multiple solutions is present whenever we solve equations involving non-injective functions.

###[Function composition](part0005_split_001.md)

We can combine two simple functions by chaining them together to build a more complicated function. This act of applying one function after another is called _function composition_. Consider for example the composition:

![f\!\circ\!g \, (x) =  f\!\left( \: g(x) \: \right) = z.](00722.jpeg)

![functions-composition](00723.jpeg)

Figure 5.7: The function composition ![f\!\circ\!g](00724.jpeg) describes the combination of first applying the function ![g](00725.jpeg), followed by the function ![f](00670.jpeg): ![f\circ g\,(x) = f(g(x))](00726.jpeg).

[Figure 5.7](part0005_split_001.md) illustrates the concept of function composition. First, the function ![g:A\to B](00727.jpeg) acts on some input ![x](00015.jpeg) to produce an intermediary value ![y=g(x)](00728.jpeg) in the set ![B](00409.jpeg). The intermediary value ![y](00018.jpeg) is then passed through the function ![f:B \to C](00729.jpeg) to produce the final output value ![z=f(y) = f(g(x))](00730.jpeg) in the set ![C](00266.jpeg). We can think of the _composite function_ ![f \circ g](00731.jpeg) as a function in its own right. The function ![f\circ g: A \to C](00732.jpeg) is defined through the formula ![f\circ g\,(x) = f(g(x))](00733.jpeg).

Don’t worry too much about the “![\circ](00734.jpeg)” symbol—it’s just a convenient math notation I wanted you to know about. Writing ![f\circ g](00731.jpeg) is the same as writing ![f(g(x))](00735.jpeg). The important takeaway from[Figure 5.7](part0005_split_001.md) is that functions can be combined by using the outputs of one function as the inputs to the next. This is a very useful idea for building math models. You can understand many complicated input-output transformations by describing them as compositions of simple functions.

#####[Example 1](part0005_split_001.md)

Consider the function ![g \colon \mathbb{R}_+ \to \mathbb{R}_+](00736.jpeg) given by ![g(x) = \sqrt{x}](00737.jpeg), and the function ![f \colon \mathbb{R} \to \mathbb{R}_+](00738.jpeg) defined by ![f(x) = x^2](00298.jpeg). The composite function ![f \circ g \, (x) = (\sqrt{x})^2 = x](00739.jpeg) is defined for all nonnegative reals. The composite function ![g \circ f](00740.jpeg) is defined for all real numbers, and we have ![g \circ f \, (x) = \sqrt{x^2} = |x|](00741.jpeg).

#####[Example 2](part0005_split_001.md)

The composite functions ![f \circ g](00731.jpeg) and ![g \circ f](00740.jpeg) describe different operations. If ![g(x) = \ln(x)](00742.jpeg) and ![f(x) = x^2](00298.jpeg), the functions ![g \circ f \, (x) = \ln(x^2)](00743.jpeg) and ![f \circ g \, (x) = (\ln x)^2](00744.jpeg) have different domains and produce different outputs, as you can verify using a calculator.

Using the notation “![\circ](00734.jpeg)” for function composition, we can give a concise description of the properties of a bijective function ![f: A \to B](00708.jpeg) and its inverse function ![f^{-1}: B \to A](00714.jpeg):

![(f^{-1} \circ  f)(x) = x    \qquad \textrm{and} \qquad    (f  \circ  f^{-1})(y) = y,](00745.jpeg)

for all ![x](00015.jpeg) in ![A](00667.jpeg) and all ![y](00018.jpeg) in ![B](00409.jpeg).

###[Function names](part0005_split_001.md)

We use short symbols like ![+](00453.jpeg), ![-](00454.jpeg), ![\times](00746.jpeg), and ![\div](00747.jpeg) to denote most of the important functions used in everyday life. We also use the squiggle notation ![\sqrt{\phantom{x}}](00748.jpeg) for square roots and superscripts to denote exponents. All other functions are identified and denoted by their _name_. If I want to compute the _cosine_ of the angle ![60^\circ](00749.jpeg) (a function describing the ratio between the length of one side of a right-angle triangle and the hypotenuse), I write ![\cos(60^\circ)](00750.jpeg), which means I want the value of the ![\cos](00751.jpeg) function for the input ![60^\circ](00749.jpeg).

Incidentally, the function ![\cos](00751.jpeg) has a nice output value for that specific angle: ![\cos(60^\circ)=\frac{1}{2}](00752.jpeg). Therefore, seeing ![\cos(60^\circ)](00750.jpeg) somewhere in an equation is the same as seeing ![\frac{1}{2}](00050.jpeg). To find other values of the function, say ![\cos(33.13^\circ)](00753.jpeg), you’ll need a calculator. All scientific calculators have a convenient little ![\button{\cos}](00754.jpeg) button for this very purpose.

###[Handles on functions](part0005_split_001.md)

When you learn about functions you learn about the different “handles” by which you can “grab” these mathematical objects. The main handle for a function is its **definition**: it tells you the precise way to calculate the output when you know the input. The function definition is an important handle, but it is also important to “feel” what the function does intuitively. How does one get a feel for a function?

####[Table of values](part0005_split_001.md)

One simple way to represent a function is to look at a list of input-output pairs: ![\big\{ \{ \text{in}=x_1, \text{out}=f(x_1) \}](00755.jpeg), ![\{ \text{in}~=~x_2,](00756.jpeg) ![\text{out}=f(x_2) \}](00757.jpeg), ![\{ \text{in}=x_3, \text{out}=f(x_3) \}, \ldots \big\}](00758.jpeg). A more compact notation for the input-output pairs is ![\{ (x_1,f(x_1)),](00759.jpeg) ![(x_2,f(x_2)),](00760.jpeg) ![(x_3,f(x_3)), \,  \ldots \}](00761.jpeg), where the first number of each pair represents an input value and the second represents the output value given by the function.

We can also build a **table of values** by writing the input values in one column and recording the corresponding output values in a second column. You can choose inputs at random or focus on the important-looking ![x](00015.jpeg) values in the function’s domain.

![\begin{align*}     \textrm{input}=x \qquad &\rightarrow \qquad f(x)=\textrm{output}     \\     \underline{\hspace{3cm}} \qquad &\phantom{\rightarrow} \; \qquad \underline{\hspace{3cm}} \\     0  \qquad  &\rightarrow \qquad f(0)   \\     1  \qquad  &\rightarrow \qquad f(1)   \\     55  \qquad  &\rightarrow \qquad f(55)  \\     x_4  \qquad  &\rightarrow \qquad f(x_4)     \end{align*}](00762.jpeg)

Table 5.1: Table of input-output values of the function ![f(x)](00673.jpeg). The input values ![x = 0](00763.jpeg), ![x = 1](00764.jpeg) and ![x = 55](00765.jpeg) are chosen to “test” what the function does.

You can create a table of values for any function you want to study. Follow the example shown in[Table 5.1](part0005_split_001.md). Use the input values that interest you and fill out the right side of the table by calculating the value of ![f(x)](00288.jpeg) for each input ![x](00015.jpeg).

####[Function graph](part0005_split_001.md)

One of the best ways to feel a function is to look at its graph. A graph is a line on a piece of paper that passes through all input-output pairs of a function. Imagine you have a piece of paper, and on it you draw a blank _coordinate system_ as in[Figure 5.8](part0005_split_001.md).

![empty_coordinate_system](00633.gif)

Figure 5.8: An empty ![(x,y)](00634.jpeg)\-coordinate system that you can use to draw function graphs. The graph of ![f(x)](00673.jpeg) consists of all the points for which ![(x,y)=(x,f(x))](00766.jpeg). See[Figure 4.4](part0004_split_001.md) on page 4.4 for the graph of ![f(x)=x^2](00652.jpeg).

The horizontal axis is used to measure ![x](00015.jpeg). The vertical axis is used to measure ![f(x)](00288.jpeg). Because writing out ![f(x)](00288.jpeg) every time is long and tedious, we use a short, single-letter alias to denote the output value of ![f](00287.jpeg) as follows:

![y = f(x) = \text{output}.](00767.jpeg)

Think of each input-output pair of the function ![f](00287.jpeg) as a point ![(x,y)](00630.jpeg) in the coordinate system. The graph of a function is a representational drawing of everything the function does. If you understand how to interpret this drawing, you can infer everything there is to know about the function.

####[Facts and properties](part0005_split_001.md)

Another way to feel a function is by knowing the function’s properties. This approach boils down to learning facts about the function and its connections to other functions. An example of a mathematical connection is the equation ![\log_{B}(x)=\frac{\log_b(x)}{\log_b(B)}](00768.jpeg), which describes a link between the logarithmic function base ![B](00409.jpeg) and the logarithmic function base ![b](00074.jpeg).

The more you know about a function, the more “paths” your brain builds to connect to that function. Real math knowledge is not about memorization; it is about establishing a network of associations between different areas of information in your brain. See the concept maps on page 1 for an illustration of the paths that link math concepts. Mathematical thought is the usage of these associations to carry out calculations and produce mathematical arguments. For example, knowing about the connection between logarithmic functions will allow you compute the value of ![\log_7(e^3)](00769.jpeg), even though calculators don’t have a button for logarithms base ![7](00157.jpeg). We find ![\log_7(e^3) = \frac{\ln e^3}{\ln 7} = \frac{3}{\ln 7}](00770.jpeg), which can be computed using the ![\button{\ln}](00771.jpeg) button.

To develop mathematical skills, it is vital to practice path-building between concepts by solving exercises. With this book, I will introduce you to some of the many paths linking math concepts, but it’s on you to reinforce these paths through practice.

#####[Example 3](part0005_split_001.md)

Consider the function ![f](00287.jpeg) from the real numbers to the real numbers (![f \colon \mathbb{R} \to \mathbb{R}](00668.jpeg)) defined as ![f(x)=x^2+2x-3](00772.jpeg). The value of ![f](00287.jpeg) when ![x=1](00773.jpeg) is ![f(1)=1^2+2(1)-3=0](00774.jpeg). When ![x=2](00380.jpeg), the output is ![f(2)=2^2+2(2)-3=5](00775.jpeg). What is the value of ![f](00287.jpeg) when ![x=0](00776.jpeg)? You can use algebra to rewrite this function as ![f(x)=(x+3)(x-1)](00777.jpeg), which tells you the graph of this function crosses the ![x](00015.jpeg)\-axis at ![x=-3](00778.jpeg) and at ![x=1](00773.jpeg). The values above will help you plot the graph of ![f(x)](00288.jpeg).

#####[Example 4](part0005_split_001.md)

Consider the exponential function with base 2 defined by ![f(x) = 2^x](00779.jpeg). This function is crucial to computer systems. For instance, RAM memory chips come in powers of two because the memory space is exponential in the number of “address lines” used on the chip. When ![x=1](00773.jpeg), ![f(1)=2^1=2](00780.jpeg). When ![x](00015.jpeg) is 2 we have ![f(2)=2^2=4](00781.jpeg). The function is therefore described by the following input-output pairs: ![(0,1)](00782.jpeg), ![(1,2)](00783.jpeg), ![(2,4)](00784.jpeg), ![(3,8)](00785.jpeg), ![(4,16)](00786.jpeg), ![(5,32)](00787.jpeg), ![(6,64)](00788.jpeg), ![(7,128)](00789.jpeg), ![(8,256)](00790.jpeg), ![(9,512)](00791.jpeg), ![(10,1024)](00792.jpeg), ![(11, 2048)](00793.jpeg), ![(12,4096)](00794.jpeg), etc. Recall that any number raised to exponent ![0](00101.jpeg) gives ![1](00211.jpeg). Thus, the exponential function passes through the point ![(0,1)](00782.jpeg). Recall also that negative exponents lead to fractions, so we have the points ![(-1,\frac{1}{2})](00795.jpeg), ![(-2,\frac{1}{4})](00796.jpeg), ![(-3,\frac{1}{8})](00797.jpeg), etc. You can plot these ![(x, f(x))](00648.jpeg) coordinates in the Cartesian plane to obtain the graph of the function.

###[Discussion](part0005_split_001.md)

To describe a function we specify its source and target sets ![f \colon A \to B](00666.jpeg), then give an equation of the form ![f(x) = \textrm{``expression involving } x \textrm{''}](00798.jpeg) that defines the function. Since functions are defined using equations, does this mean that functions and equations are the same thing? Let’s take a closer look.

In general, any equation containing two variables describes a _relation_ between these variables. For example, the equation ![x-3 = y-4](00799.jpeg) describes a relation between the variables ![x](00015.jpeg) and ![y](00018.jpeg). We can isolate the variable ![y](00018.jpeg) in this equation to obtain ![y = x + 1](00800.jpeg) and thus find the value of ![y](00018.jpeg) when the value of ![x](00015.jpeg) is given. We can also isolate ![x](00015.jpeg) to obtain ![x = y-1](00801.jpeg) and use this equation to find ![x](00015.jpeg) when the value of ![y](00018.jpeg) is given. In the context of an equation, the relationship between the variables ![x](00015.jpeg) and ![y](00018.jpeg) is symmetrical and no special significance is attached to either of the two variables.

We also can describe the same relationship between ![x](00015.jpeg) and ![y](00018.jpeg) as a function ![f: \mathbb{R} \to \mathbb{R}](00719.jpeg). We choose to identify ![x](00015.jpeg) as the input variable and ![y](00018.jpeg) as the output variable of the function ![f](00287.jpeg). Having identified ![y](00018.jpeg) with the output variable, we can interpret the equation ![y = x + 1](00800.jpeg) as the definition of the function ![f(x) = x + 1](00802.jpeg).

Note that the equation ![x-3 = y-4](00799.jpeg) and the function ![f(x) = x + 1](00802.jpeg) describe the same relationship between the variables ![x](00015.jpeg) and ![y](00018.jpeg). For example, if we set the value ![x = 5](00803.jpeg) we can find the value of ![y](00018.jpeg) by solving the equation ![5-3 = y-4](00804.jpeg) to obtain ![y = 6](00805.jpeg), or by computing the output of the function ![f(x)](00288.jpeg) for the input ![x=5](00803.jpeg), which gives us the same answer ![f(5)=6](00806.jpeg). In both cases we arrive at the same answer, but modelling the relationship between ![x](00015.jpeg) and ![y](00018.jpeg) as a function allows us to use the whole functions toolbox, like function composition and function inverses.

In this section we talked a lot about functions in general but we haven’t said much about any function specifically. There are many useful functions out there, and we can’t discuss them all here. In the next section, we’ll introduce ![10](00246.jpeg) functions of strategic importance for all of science. If you get a grip on these functions, you’ll be able to understand all of physics and calculus and handle _any_ problem your teacher may throw at you.
