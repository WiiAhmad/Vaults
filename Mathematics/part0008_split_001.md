Chapter 8    

##[8.1 Solving systems of linear equations](part0008_split_001.md)

Solving equations with one unknown—like ![2x + 4 = 7x](01867.jpeg), for instance—requires manipulating both sides of the equation until the unknown variable is _isolated_ on one side. For this instance, we can subtract ![2x](01868.jpeg) from both sides of the equation to obtain ![4 = 5x](01869.jpeg), which simplifies to ![x=\frac{4}{5}](01870.jpeg).

What about the case when you are given _two_ equations and must solve for _two_ unknowns? For example,

![\begin{align*}   x + 2y     & =  5, \\   3x + 9y    & =  21.  \end{align*}](01871.jpeg)

Can you find values of ![x](00015.jpeg) and ![y](00018.jpeg) that satisfy both equations?

###[Concepts](part0008_split_001.md)

-   ![x,y](01872.jpeg): the two unknowns in the equations
-   ![eq1, eq2](01873.jpeg): a system of two equations that must be solved _simultaneously_. These equations will look like
    
    ![\begin{align*}          a_1x + b_1y     & =  c_1, \\          a_2x + b_2y     & =  c_2,     \end{align*}](01874.jpeg)
    
    where ![a](00014.jpeg)s, ![b](00074.jpeg)s, and ![c](00256.jpeg)s are given constants.
    

###[Principles](part0008_split_001.md)

If you have ![n](00054.jpeg) equations and ![n](00054.jpeg) unknowns, you can solve the equations _simultaneously_ and find the values of the unknowns. There are several different approaches for solving equations simultaneously. We’ll show three of these approaches for the case ![n=2](01857.jpeg).

###[Solution techniques](part0008_split_001.md)

When solving for two unknowns in two equations, the best approach is to _eliminate_ one of the variables from the equations. By combining the two equations appropriately, we can simplify the problem to the problem of finding one unknown in one equation.

####[Solving by substitution](part0008_split_001.md)

We want to solve the following system of equations:

![\begin{align*}     x + 2y & =  5, \\     3x + 9y & =  21.       \end{align*}](01871.jpeg)

We can isolate ![x](00015.jpeg) in the first equation to obtain

![\begin{align*}                        x  & =  5 - 2y, \\                    3x + 9y & =  21.      \end{align*}](01875.jpeg)

Now _substitute_ the expression for ![x](00015.jpeg) from the top equation into the bottom equation:

![3(5-2y) + 9y = 21.](01876.jpeg)

We just eliminated one of the unknowns by substitution. Continuing, we expand the bracket to find

![15 - 6y +9y =  21, \\](01877.jpeg)

or

![3y = 6.](01878.jpeg)

We find ![y=2](01879.jpeg), but what is ![x](00015.jpeg)? Easy. To solve for ![x](00015.jpeg), plug the value ![y=2](01879.jpeg) into any of the equations we started from. Using the equation ![x = 5-2y](01880.jpeg), we find ![x = 5-2(2) = 1](01881.jpeg).

####[Solving by subtraction](part0008_split_001.md)

Let’s now look at another way to solve the same system of equations:

![\begin{align*}     x + 2y & =  5, \\     3x + 9y & =  21.       \end{align*}](01871.jpeg)

Observe that any equation will remain true if we multiply the whole equation by some constant. For example, we can multiply the first equation by ![3](00106.jpeg) to obtain an equivalent set of equations:

![\begin{align*}     3x + 6y     & =  15, \\     3x + 9y    & =  21.    \end{align*}](01882.jpeg)

Why did I pick 3 as the multiplier? By choosing this constant, the ![x](00015.jpeg) terms in both equations now have the same coefficient.

Subtracting two true equations yields another true equation. Let’s subtract the top equation from the bottom one:

![\cancel{3x} - \cancel{3x} + 9y - 6y = 21 - 15     \quad \Rightarrow \quad      3y = 6.](01883.jpeg)

The ![3x](00368.jpeg) terms cancel. This subtraction eliminates the variable ![x](00015.jpeg) because we multiplied the first equation by ![3](00106.jpeg). We find ![y=2](01879.jpeg). To find ![x](00015.jpeg), substitute ![y=2](01879.jpeg) into one of the original equations:

![x + 2(2) = 5,](01884.jpeg)

from which we deduce that ![x=1](00773.jpeg).

####[Solving by equating](part0008_split_001.md)

There is a third way to solve the system of equations

![\begin{align*}     x + 2y & =  5, \\     3x + 9y & =  21.    \end{align*}](01871.jpeg)

We can isolate ![x](00015.jpeg) in both equations by moving all other variables and constants to the right-hand sides of the equations:

![\begin{align*}     x & =  5 -2y, \\     x & =  \frac{1}{3}(21 - 9y) = 7 - 3y.    \end{align*}](01885.jpeg)

Though the variable ![x](00015.jpeg) is unknown to us, we know two facts about it: ![x](00015.jpeg) is equal to ![5 - 2y](01886.jpeg) and ![x](00015.jpeg) is equal to ![7 - 3y](01887.jpeg). Therefore, we can eliminate ![x](00015.jpeg) by equating the right-hand sides of the equations:

![5 - 2y = 7 -3y.](01888.jpeg)

We solve for ![y](00018.jpeg) by adding ![3y](01889.jpeg) to both sides and subtracting ![5](00117.jpeg) from both sides. We find ![y = 2](01879.jpeg) then plug this value into the equation ![x = 5 - 2y](01880.jpeg) to find ![x](00015.jpeg). The solutions are ![x=1](00773.jpeg) and ![y=2](01879.jpeg).

###[Discussion](part0008_split_001.md)

The repeated use of the three algebraic techniques presented in this section will allow you to solve any system of ![n](00054.jpeg) linear equations in ![n](00054.jpeg) unknowns. Each time you eliminate one variable using a substitution, a subtraction, or an elimination by equating, you’re simplifying the problem to a problem of finding ![(n-1)](01890.jpeg) unknowns in a system of ![(n-1)](01890.jpeg) equations. There is an entire math course called[linear algebra](./noBSLA.md), in which you’ll develop a systematic approach for solving systems of linear equations.

###[Geometric solution](part0008_split_001.md)

Solving a system of two linear equations in two unknowns can be understood geometrically as finding the point of intersection between two lines in the Cartesian plane. In this section we’ll explore this correspondence between algebra and geometry to develop yet another way of solving systems of linear equations.

The algebraic equation ![ax+by=c](01891.jpeg) containing the unknowns ![x](00015.jpeg) and ![y](00018.jpeg) can be interpreted as a _constraint_ equation on the set of possible values for the variables ![x](00015.jpeg) and ![y](00018.jpeg). We can visualize this constraint geometrically by considering the coordinate pairs ![(x,y)](00630.jpeg) that lie in the Cartesian plane. Recall that every point in the Cartesian plane can be represented as a coordinate pair ![(x,y)](00630.jpeg), where ![x](00015.jpeg) and ![y](00018.jpeg) are the coordinates of the point.

[Figure 8.1](part0008_split_001.md) shows the geometrical representation of three equations. The line ![\ell_a](01892.jpeg) corresponds to the set of points ![(x,y)](00630.jpeg) that satisfy the equation ![x=1](00773.jpeg), the line ![\ell_b](01893.jpeg) is the set of points ![(x,y)](00630.jpeg) that satisfy the equation ![y=2](01879.jpeg), and the line ![\ell_c](01894.jpeg) corresponds to the set of points that satisfy ![x+2y=2](01895.jpeg).

![systems_of_equations__examples](01896.jpeg)

Figure 8.1: Graphical representations of three linear equations.

You can convince yourself that the geometric lines shown in[Figure 8.1](part0008_split_001.md) are equivalent to the algebraic equations by considering individual points ![(x,y)](00630.jpeg) in the plane. For example, the points ![(1,0)](01897.jpeg), ![(1,1)](01607.jpeg), and ![(1,2)](00783.jpeg) are all part of the line ![\ell_a](01892.jpeg) since they satisfy the equation ![x=1](00773.jpeg). For the line ![\ell_c](01894.jpeg), you can verify that the line’s ![x](00015.jpeg)\-intercept ![(2,0)](01898.jpeg) and its ![y](00018.jpeg)\-intercept ![(0,1)](00782.jpeg) both satisfy the equation ![x+2y=2](01895.jpeg).

The Cartesian plane as a whole corresponds to the set ![\mathbb{R}^2](01549.jpeg), which describes all possible pairs of coordinates. To understand the equivalence between the algebraic equation ![ax+by=c](01891.jpeg) and the line ![\ell](01143.jpeg) in the Cartesian plane, we can use the following precise math notation:

![\ell : \{ (x,y) \in \mathbb{R}^2 \; | \;  ax+by=c \}.](01899.jpeg)

In words, this means that the line ![\ell](01143.jpeg) is defined as the subset of the pairs of real numbers ![(x,y)](00630.jpeg) that satisfy the equation ![ax+by=c](01891.jpeg).[Figure 8.2](part0008_split_001.md) shows the graphical representation of the line ![\ell](01143.jpeg).

You don’t have to take my word for it, though! Think about it and convince yourself that all points on the line ![\ell](01143.jpeg) shown in[Figure 8.2](part0008_split_001.md) satisfy the equation ![ax+by=c](01891.jpeg). For example, you can check that the ![x](00015.jpeg)\-intercept ![(\frac{c}{a},0)](01900.jpeg) and the ![y](00018.jpeg)\-intercept ![(0,\frac{c}{b})](01901.jpeg) satisfy the equation ![ax+by=c](01891.jpeg).

![systems_of_equations__ax_by_eq_c](01902.jpeg)

Figure 8.2: Graphical representation of the equation ![ax+by=c](01903.jpeg).

Solving the system of two equations

![\begin{align*}        a_1x + b_1y     & =  c_1, \\        a_2x + b_2y     & =  c_2,   \end{align*}](01874.jpeg)

corresponds to finding the intersection of the lines ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg) that represent each equation. The pair ![(x,y)](00630.jpeg) that satisfies both algebraic equations simultaneously is equivalent to the point ![(x,y)](00630.jpeg) that is the intersection of lines ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg), as illustrated in[Figure 8.3](part0008_split_001.md).

![systems_of_equations__intersection_general](01906.jpeg)

Figure 8.3: The point ![(x,y)](00634.jpeg) that lies at the intersection of lines ![\ell_1](01907.jpeg) and ![\ell_2](01908.jpeg).

#####[Example](part0008_split_001.md)

Let’s see how we can use the geometric interpretation to solve the system of equations

![\begin{align*}     x + 2y & =  5, \\     3x + 9y & =  21.    \end{align*}](01871.jpeg)

We’ve already seen three different _algebraic_ techniques for finding the solution to this system of equations; now let’s see a _geometric_ approach for finding the solution. I’m not kidding you, we’re going to solve the exact same system of equations a fourth time!

The first step is to draw the lines that correspond to each of the equations using pen and paper or a graphing calculator. The second step is to find the coordinates of the point where the two lines intersect as shown in[Figure 8.4](part0008_split_001.md). The point ![(1,2)](00783.jpeg) that lies on both lines ![\ell_1](01904.jpeg) and ![\ell_2](01905.jpeg) corresponds to the ![x](00015.jpeg) and ![y](00018.jpeg) values that satisfy both equations simultaneously.

![systems_of_equations__intersection_example](01909.jpeg)

Figure 8.4: The line ![\ell_1](01907.jpeg) with equations ![x + 2y = 5](01910.jpeg) intersects the line ![\ell_2](01908.jpeg) with equation ![3x + 9y =  21](01911.jpeg) at the point ![(1,2)](01912.jpeg).

Visit the webpage at[`www.desmos.com/calculator/exikik615f`](./exikik615f.md) to play with an interactive version of the graphs shown in[Figure 8.4](part0008_split_001.md). Try changing the equations and see how the graphs change.

###[Exercises](part0008_split_001.md)

E8.1 Plot the lines ![\ell_a](01892.jpeg), ![\ell_b](01893.jpeg), and ![\ell_c](01894.jpeg) shown in[Figure 8.1](part0008_split_001.md) (page 8.1) using the[Desmos graphing calculator](./calculator.md). Use the graphical representation of these lines to find: **a)** the intersection of lines ![\ell_c](01894.jpeg) and ![\ell_a](01892.jpeg), **b)** the intersection of ![\ell_a](01892.jpeg) and ![\ell_b](01893.jpeg), and **c)** the intersection of lines ![\ell_b](01893.jpeg) and ![\ell_c](01894.jpeg).

E8.2 Solve the system of equations simultaneously for ![x](00015.jpeg) and ![y](00018.jpeg):

![\begin{align*}    2x + 4y   &= 16, \\    5x \; - \; y      &= 7.   \end{align*}](01913.jpeg)

E8.3 Solve the system of equations for the unknowns ![x](00015.jpeg), ![y](00018.jpeg), and ![z](00656.jpeg):

![\begin{align*}    2x+y-4z   &= 28,   \\    x \; + y \, + \; z    &= 8,   \\    2x-y-6z   &= 22.   \end{align*}](01914.jpeg)

E8.4 Solve for ![p](00384.jpeg) and ![q](00385.jpeg) given the equations ![p+q = 10](01915.jpeg) and ![p-q=4](01916.jpeg).
