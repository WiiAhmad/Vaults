Chapter 3      

#[Chapter 3 Computational linear algebra](./Chapter 3_ Computational linear algebra.md)

This chapter covers the computational aspects of performing matrix calculations. Understanding matrix computations is important because the rest of the chapters in this book depend on them. Suppose we’re given a huge matrix ![A \in \mathbb{R}^{n\times n}](./images/2f056442410016d3a541715471950849562de0c4.png) with ![n=1000](./images/cc596b6caace4df8560e478ec587dc41aedc4db6.png). Behind the innocent-looking mathematical notation of the matrix inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png), the matrix product ![AA](./images/dfbc1f0037cdee2cd7dac10a1ce7b5ae8f8d6616.png), and the matrix determinant ![\textrm{det}(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png), are hidden monster computations involving all the ![1000\times 1000 = 1](./images/3688af4ee69291cde89a4b6725ca12b5029e5875.png) million entries of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Millions of arithmetic operations must be performed…so I hope you have at least a thousand pencils ready!

Okay, calm down. I won’t _actually_ make you calculate millions of arithmetic operations. In fact, to learn linear algebra, it is sufficient to know how to carry out calculations with ![3\times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) and ![4 \times 4](./images/841e9fa0bb8c2499770ffd8babaaf06f37a4a26f.png) matrices. Yet, even for such moderately sized matrices, computing products, inverses, and determinants by hand are serious computational tasks. If you’re ever required to take a linear algebra final exam, you’ll need to make sure you can do these calculations quickly. And even if no exam looms in your imminent future, it’s still important you practice matrix operations by hand to get a feel for them.

This chapter will introduce you to four important computational tasks involving matrices.

#####[Gauss–Jordan elimination](./Front matter.md)

Suppose we’re trying to solve two equations in two unknowns ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png):

![\begin{align*}
ax + by  &= c, \\
dx + ey  &= f.
\end{align*}](./images/55d2721f79a1fa6d5253502a64555ce38e34e0fc.png)

If we add ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png)\-times the first equation to the second equation, we obtain an equivalent system of equations:

![\begin{align*}
ax \; + \qquad \; \; \, by \; &= \qquad \;  c \\
(d+\alpha a)x + (e+\alpha b)y  &= f+\alpha c. \qquad \qquad
\end{align*}](./images/bf532bea37d5378fa667ce221aa2d78383d794e9.png)

This is called a _row operation_: we added ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png)\-times the first row to the second row. Row operations change the coefficients of the system of equations, but leave the solution unchanged. Gauss–Jordan elimination is a systematic procedure for solving systems of linear equations using row operations.

#####[Matrix multiplication](./Front matter.md)

The product ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png) between matrices ![A \in \mathbb{R}^{m\times \ell}](./images/b0ede296919e4c3a24753989c4314f3fb0de0a48.png) and ![B \in \mathbb{R}^{\ell \times n}](./images/d742164890dd4391e9b9a7e0b490e133edb87633.png) is the matrix ![C \in \mathbb{R}^{m\times n}](./images/d9abe832d13e229ca20be8d418a31f8bf1719743.png) whose entries ![c_{ij}](./images/7ea84843068c73cace02ad6f2a02e61951a9026e.png) are defined by the formula ![c_{ij} = \sum_{k=1}^\ell a_{ik}b_{kj}](./images/1424d92bf4d9af5c3b41fe194c0c6da73bdd1eb4.png) for all ![i \in[1,\ldots,m]](../Images/45e70e4792892aa567503fc88c3c3a95abb0d6ca.png) and ![j \in[1,\ldots,n]](../Images/9d367204a9bd98753a8c90edec37bf9fda56dbc5.png). In[Section 3.3](./Chapter 3_ Computational linear algebra.md), we’ll unpack this formula and learn about its intuitive interpretation: that computing ![C=AB](./images/ba53bead8c57c1cb4b7760ffaf0bde454194c32e.png) is computing all the dot products between the rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and the columns of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

#####[Determinant](./Front matter.md)

The determinant of a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), denoted ![\textrm{det}(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png), is an operation that gives us useful information about the linear independence of the rows of the matrix. The determinant is connected to many notions of linear algebra: linear independence, geometry of vectors, solving systems of equations, and matrix invertibility. We’ll discuss these aspects of determinants in[Section 3.4](./Chapter 3_ Computational linear algebra.md).

#####[Matrix inverse](./Front matter.md)

In[Section 3.5](./Chapter 3_ Computational linear algebra.md), we’ll build upon our knowledge of Gauss–Jordan elimination, matrix products, and determinants to derive three different procedures for computing the matrix inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png).

##[3.1 Reduced row echelon form](./Chapter 3_ Computational linear algebra.md)

In this section we’ll learn to solve systems of linear equations using the _Gauss–Jordan elimination_ procedure. A system of equations can be represented as a matrix of coefficients. The Gauss–Jordan elimination procedure converts any matrix into its _reduced row echelon form_ (RREF). We can use the RREF to easily find the solution (or solutions) of the system of equations.

Heads up: the material covered in this section requires your full-on, caffeinated attention, as the procedures you’ll learn are somewhat tedious. Gauss–Jordan elimination involves many repetitive manipulations of arrays of numbers. It’s important you follow the step-by-step manipulations, as well as verify each step I present _on your own_ with pen and paper. Don’t just take my word for it—always verify the steps!

###[Solving equations](./Front matter.md)

Suppose you’re asked to solve the following system of equations:

![\begin{align*}
1x_1 + 2x_2 & = 5 \\
3x_1 + 9x_2 & = 21.
\end{align*}](./images/d9d1295c3dd1e351acfdf996490b9e9e3f927a70.png)

The standard approach is to use one of the equation-solving tricks we learned in[Section 1.15](./Chapter 1_ Math fundamentals.md) to combine the equations and find the values of the two unknowns ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png).

Observe that the _names_ of the two unknowns are irrelevant to the solution of the system of equations. Indeed, the solution ![(x_1,x_2)](./images/9e628fc8a57668be16d71e16020db1888c235853.png) to the above system of equations is the same as the solution ![(s,t)](./images/dfa51b2dc0a66fb2b46afc9f65fcfec9b111c1d8.png) to the system of equations

![\begin{align*}
1s + 2t & =  5 \\
3s + 9t & =  21.
\end{align*}](./images/39d267bd56edcf1ef1f0a40e2d8992a94a9a0260.png)

The important parts of a system of linear equations are the _coefficients_ in front of the variables, and the constants on the right side of each equation.

###[Augmented matrix](./Front matter.md)

The system of linear equations can be written as an _augmented matrix_:

![\left[ 
\begin{array}{cc|c}
1 & 2  \; \; &  5  \\
3 & 9  \;  \; & 21
\end{array} \right]\!.](../Images/a37d7817b5d6f51865400fd64c52465e370fb4cf.png)

The first column corresponds to the coefficients of the first variable; the second column is for the second variable; and the last column corresponds to the constants on the right side. It is customary to draw a vertical line where the equal signs in the equations would normally appear. This line helps distinguish the coefficients of the equations from the column of constants on the right side.

Once we have the augmented matrix, we can simplify it by using _row operations_ (which we’ll discuss shortly) on its entries. After simplification by row operations, the augmented matrix will be transformed to

![\left[ 
\begin{array}{cc|c}
1 & 0 \; \;  & \; 1  \\
0 & 1 \; \;  & \; 2
\end{array} \right]\!,](../Images/05d86885e525341cb69ee3ee34a5ef82614aee66.png)

which corresponds to the system of equations

![\begin{align*}
x_1 & = 1 \\
x_2 & = 2.
\end{align*}](./images/9960afe78f4b1aa6679fc2aa6e384ac0dc3ee92c.png)

This is a _trivial_ system of equations; there is nothing left to solve and we can see the solutions are ![x_1=1](./images/451b77dc3be16693007f68f5764852db56954d24.png) and ![x_2=2](./images/dbd682fe27848026f5a0fa50f1d07adadad0e61c.png). This example illustrates the general idea of the Gauss–Jordan elimination procedure for solving systems of equations by manipulating an augmented matrix.

###[Row operations](./Front matter.md)

We can manipulate the rows of an augmented matrix without changing its solutions. We’re allowed to perform the following three types of row operations:

-   Add a multiple of one row to another row
-   Swap the position of two rows
-   Multiply a row by a constant

Let’s trace the sequence of row operations needed to solve the system of equations

![\begin{align*}
\qquad
1x_1 + 2x_2 &=  5 \\
3x_1 + 9x_2 &=  21,
\end{align*}](./images/3774ef7b5ce6064d0a2d6a81666b4de39054896d.png)

starting from its augmented matrix:

![\qquad  \; \; 
\left[
\begin{array}{cc|c}
1 & 2 \; \;  & \;  5  \\
3 & 9 \; \;  & \; 21  
\end{array} \right]\!.](../Images/af062780e897fe81ebcedccff019d9edead5a517.png)

1.  As a first step, we eliminate the first variable in the second row by subtracting three times the first row from the second row:
    
    ![\left[\begin{array}{cc|c}1 & 2 \; \; & \; 5\\0 & 3 \; \; & \; 6\end{array}\right]\!.](../Images/0a527bc4fbb3afee4b3427c7b03f8352f8773367.png)
    
    We denote this row operation as ![R_2 \gets R_2 - 3R_1](./images/fb500f7ee9892774999183ff5cc78dff5362cfac.png).
    
2.  To simplify the second row, we divide it by ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) to obtain
    
    ![\left[\begin{array}{cc|c}1 & 2 \; \; & \; 5\\0 & 1 \; \; & \; 2\end{array}\right]\!.](../Images/bca1a886a8d0898b3b95f69a7354fdf66d7a73ae.png)
    
    This row operation is denoted ![R_2 \gets \frac{1}{3}R_2](./images/a4bc8b81a525d2f8e6de557459c7f63acac6314a.png).
    
3.  Finally we eliminate the second variable from the first row by subtracting two times the second row, ![R_1 \gets R_1 - 2R_2](./images/c9fe4f74671bcc370ee5e99a29db8b0e89f9af6c.png):
    
    ![\left[\begin{array}{cc|c}1 & 0 \; \; & \; 1\\0 & 1 \; \; & \; 2\end{array}\right]\!.](../Images/14a28fe45e7866a0fd56e0175c8a57aa56eb77f6.png)
    
    We can now read off the solution: ![x_1 = 1](./images/451b77dc3be16693007f68f5764852db56954d24.png) and ![x_2=2](./images/dbd682fe27848026f5a0fa50f1d07adadad0e61c.png).
    

Note how we simplified the augmented matrix through a specific procedure: we followed the _Gauss–Jordan elimination_ algorithm to bring the matrix into its _reduced row echelon form_.

The _reduced row echelon form_ (RREF) is the simplest form for an augmented matrix. Each row contains a _leading one_ (a numeral 1) also known as a _pivot_. Each column’s pivot is used to eliminate the numbers that lie below and above it in the same column. The end result of this procedure is the reduced row echelon form:

![\left[ \begin{array}{cccc|c}
1 & 0 & *  & 0 \; \; & \; * \\
0 & 1 & *  & 0 \; \; & \; * \\
0 & 0 & 0  & 1 \; \; & \; * 
\end{array} \right]\!.](../Images/fa488389ea9148cc7630db08ad8c44c9972ca340.png)

Note the matrix contains only zero entries below and above the pivots. The asterisks ![*](./images/29afcbe8d161a0b41a70ac8141fd12b208af180b.png) denote arbitrary numbers that cannot be eliminated because no leading one is present in these columns.

###[Definitions](./Front matter.md)

-   The _solution_ to a system of linear equations in the variables ![x_1,x_2,\ldots,x_n](./images/e134cadee1393cbf3dbc898980a1c82c087a4cf9.png) is the set of values ![\{ (x_1,x_2, \ldots, x_n) \}](./images/c24efcdb586016dc816088ff268b35667dbcf0de.png) that satisfy _all_ the equations.
-   The _pivot_ for row ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) of a matrix is the left-most nonzero entry in the row ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png). Any _pivot_ can be converted into a _leading one_ by an appropriate scaling of that row.
-   _Gaussian elimination_ is the process of bringing a matrix into _row echelon form_.
-   A matrix is said to be in _row echelon form_ (REF) if all entries below the leading ones are zero. This form can be obtained by adding or subtracting the row with the leading one from the rows below it.
-   _Gaussian-Jordan elimination_ is the process of bringing a matrix into _reduced row echelon form_.
-   A matrix is said to be in _reduced row echelon form_ (RREF) if all the entries below _and above_ the pivots are zero. Starting from the REF, we obtain the RREF by subtracting the row containing the pivots from the rows above that row.
-   ![\textrm{rank}(A)](./images/ed9af0029991b2f3fe54ea738272a568e5f5880a.png): the _rank_ of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is the number of pivots in the RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

###[Gauss–Jordan elimination algorithm](./Front matter.md)

The Gauss–Jordan elimination algorithm proceeds in two phases: a forward phase in which we move left to right, and a backward phase in which we move right to left.

1.  Forward phase (left to right):
    1.  Obtain a pivot (a leading one) in the leftmost column.
    2.  Subtract the row with the pivot from all rows below it to obtain zeros in the entire column.
    3.  Look for a leading one in the next column and repeat.
2.  Backward phase (right to left):
    1.  Find the rightmost pivot and use it to eliminate all numbers above the pivot in its column.
    2.  Move one column to the left and repeat.

#####[Example](./Front matter.md)

We’re asked to solve the following system of equations:

![\begin{align*}
1x + 2y +3 z &= 14 \; \\
2x + 5y +6 z &= 30 \; \\
-1x +2y +3 z &= 12.  \qquad
\end{align*}](./images/140b9d4027c35311188baab35ca8bbecfa634756.png)

The first step toward the solution is to build the augmented matrix that corresponds to this system of equations:

![\left[\begin{array}{ccc|c}{\color{blue}1} & 2 & 3 \; \; & \;  14\\2 & 5 & 6 \; \; & \;  30\\-1 & 2 & 3 \; \; & \;  12\end{array}\right]\!.](../Images/db4159461b033314cb416d743de9e8b6bdc3e5bb.png)

We can now start the left-to-right phase of the algorithm:

1.  Conveniently, there is a leading one at the top of the leftmost column. If a zero were there instead, a row-swap operation would be necessary to obtain a nonzero entry.
2.  The next step is to clear the entries in the entire column below this pivot. The row operations we’ll use for this purpose are ![R_2 \gets R_2 - 2R_1](./images/ed2d48642732071d5cac4caa3c732eaf8d530c7e.png) and ![R_3 \gets R_3 + R_1](./images/c7200cb74701907003b0b4011e1279a2f7d8d7a7.png):
    
    ![\left[\begin{array}{ccc|c}
    1 & 2 & 3 \; \; & \;  14\\
    0 & {\color{blue}1} & 0 \; \; & \;  2\\
    0 & 4 & 6 \; \; & \;  26
    \end{array}\right]\!.](../Images/f40f4ea3f3ac15dc9afeb1a7bbe4375f96fd9209.png)
    
3.  We now shift our attention to the second column. Using the leading one for the second column, we set the number in the column below it to zero using ![R_3 \gets R_3 - 4R_2](./images/5e3bfebd974670457faaaa19d31e4e0e890d5f2d.png). The result is
    
    ![\left[\begin{array}{ccc|c}1 & 2 & 3 \; \; & \;   14\\0 & 1 & 0 \; \; & \;   2\\0 & 0 & {\color{blue}6} \; \; & \;  18\end{array}\right]\!.](../Images/f9f56ed69cf2e31d5a6d60ff9bfbf7419273487b.png)
    
4.  Next, we move to the third column. Instead of a leading one, we find it contains a “leading six,” which we can convert to a leading one using ![R_3 \gets \frac{1}{6}R_3](./images/7ee3fe9165069363bd226722a35255cd0ffcb1f0.png). We thus obtain
    
    ![\left[\begin{array}{ccc|c} 1 & 2 & 3 \; \; & \; 14\\0 & 1 & 0 \; \; & \; 2\\0 & 0 & {\color{blue}1} \; \; & \; 3\end{array}\right]\!.](../Images/03e855e557ef4493f6991b656767bb33fb1924ff.png)
    

The forward phase of the Gauss–Jordan elimination procedure is now complete. We identified three pivots and used them to systematically set all entries below each pivot to zero. The matrix is now in _row echelon form_.

Next, we perform the backward phase of the Gauss–Jordan elimination procedure, where we’ll work right-to-left to set all numbers above each pivot to zero:

1.  The first row operation is ![R_1 \gets R_1 -3R_3](./images/44222380b1b3582109baffaf2eb5d8f13e836aa8.png), and it leads to
    
    ![\left[\begin{array}{ccc|c}1 & 2 & 0 \; \; & \;  5\\0 & 1 & 0 \; \; & \; 2\\0 & 0 & 1 \; \; & \; 3\end{array}\right]\!.](../Images/52182ec46a5716d9d0db9978490779e1d7a91be0.png)
    
2.  The final step is ![R_1 \gets R_1 -2R_2](./images/c9fe4f74671bcc370ee5e99a29db8b0e89f9af6c.png), which gives
    
    ![\left[\begin{array}{ccc|c}1 & 0 & 0 \; \; & \;  1\\0 & 1 & 0 \; \; & \;  2\\0 & 0 & 1 \; \; & \;  3\end{array}\right]\!.](../Images/f80053975abde3cc0b01cd095cbc84d4cd3163c4.png)
    

The matrix is now in _reduced row echelon form_, and we can see the solution is ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png), ![y=2](./images/2d75ac51aced995d1be9b9479c5c67a96ea74f97.png), and ![z=3](./images/a998cce2e26331a7d4b05dd4bc3c6ea3673302b4.png).

We’ve described the general idea of the Gauss–Jordan elimination and explored some examples where the solutions to the system of equations were _unique_. There are other possibilities for the solutions of a system of linear equations. We’ll describe these other possible scenarios next.

###[Number of solutions](./Front matter.md)

A system of three linear equations in three variables could have:

-   **One solution**. If the RREF of a matrix has a pivot in each row, we can read off the values of the solution by inspection:
    
    ![\left[ \begin{array}{ccc|c}
    1 & 0 & 0  \; \; &  \;  c_1 \\
    0 & 1 & 0  \; \; & \;  c_2 \\
    0 & 0 & 1  \; \;  &\;  c_3
    \end{array}\right]\!.](../Images/a1d9a09c3b229789668918d5633abdbea4a8a981.png)
    
    The _unique_ solution is ![x_1=c_1](./images/e1143b517769633d0550235ccbef46dce836d372.png), ![x_2=c_2](./images/b222653be49ae5eaae76d4dfa1860820a841f8cc.png), and ![x_3=c_3](./images/d81fed2b78f93cca4a1ee6c121a675d363be6dd9.png).
    
-   **Infinitely many solutions**. If one of the equations is redundant, a row of zeros will appear when the matrix is brought to the RREF. This happens when one of the original equations is a linear combination of the other two. In such cases, we’re really solving _two_ equations in _three_ variables, so we can’t “pin down” one of the unknown variables. We say the solution contains a _free variable_. For example, consider the following RREF:
    
    ![\left[ \begin{array}{ccc|c}
    1 & 0 & a_1  \; \; & \;  c_1 \\
    0 & 1 & a_2  \; \; & \;  c_2 \\
    0 & 0 & 0      \; \; & \;  0
    \end{array}\right]\!.](../Images/a1b53042a60dced1ea98cee2191f3660d4ded125.png)
    
    The column that doesn’t contain a leading one corresponds to the free variable. To indicate that ![x_3](./images/db23e43963a7727df3e8966c1e818afe37b229d7.png) is a free variable, we give it a special label, ![x_3=t](./images/e8e875310e66bdcf62fe671d14ef304388e4e5ea.png). The variable ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) could be any number ![t \in \mathbb{R}](./images/27da8cc414f17278d49c7116607963991c3cd05f.png). In other words, when we say ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) is free, it means ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) can take on _any_ value from ![-\infty](./images/f721ad0d9976ce8087387d1ef86a879ec6843579.png) to ![+\infty](./images/f5959adec770e45f017adb874bd6041ec0cd63b0.png). The information in the augmented matrix can now be used to express ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png) in terms of the constants and the free variable ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png):
    
    ![\left\{ \!\!
    \begin{array}{rl}
    x_1 \!\!\!\!\! &= c_1 -a_1\:t \\
    x_2 \!\!\!\!\! &= c_2 - a_2\:t \\
    x_3 \!\!\!\!\! &= t
    \end{array}, \; \; 
    \forall t \in \mathbb{R}
    \right\}
    = 
    \left\{
    \begin{bmatrix} c_1 \\ c_2 \\ 0 \end{bmatrix}
    + t \! \begin{bmatrix} -a_1 \\ -a_2 \\ 1 \end{bmatrix},\; \; \; 
    \forall t \in \mathbb{R}
    \right\}\!.](./images/e341f4dcf7fcefcd53f446dd3c0afa3dde65d745.png)
    
    The solution corresponds to the equation of a line passing through the point ![(c_1,c_2,0)](./images/2f47f43d6f2d705190bbd7393ac4113ceb7bd4e0.png) with direction vector ![(-a_1,-a_2,1)](./images/68654d9b6eb63fefa9ad01aa23fd6affeae92059.png). We’ll discuss the geometry of lines in[Chapter 4](./Chapter 4_ Geometric aspects of linear algebra.md). For now, it’s important you understand that a system of equations can have more than one solution; any point on the line ![\ell = \{ (c_1,c_2,0) + t(-a_1,-a_2,1), \; \forall t \in \mathbb{R} \}](./images/165a31b6244a6d390714ccec022394987b2ce49b.png) is a solution to the above system of equations.
    
-   **Infinitely many solutions in two dimensions**. It’s also possible to obtain a two-dimensional solution space. This happens when two of the three equations are redundant. This results in a single leading one, and thus two free variables. For example, in the RREF
    
    ![\left[ \begin{array}{ccc|c}
    0 & 1 & a_2   \; \; & \;  c_2 \\
    0 & 0 & 0    \; \; & \;   0 \\
    0 & 0 & 0    \; \; & \;  0 
    \end{array}\right]\!,](../Images/62c7c4284e9d2b19b8a157e7e55e711122d40e9a.png)
    
    the variables ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png) and ![x_3](./images/db23e43963a7727df3e8966c1e818afe37b229d7.png) are free. As in the previous infinitely-many-solutions case, we define new labels for the free variables ![x_1 = s](./images/d0b6c6cca4f6b4a70ee6dc9957335cd32b7e2a84.png) and ![x_3 = t](./images/e8e875310e66bdcf62fe671d14ef304388e4e5ea.png), where ![s \in \mathbb{R}](./images/014b6412f3d0a4ca03b911b3247bbdc72d0337fe.png) and ![t \in \mathbb{R}](./images/27da8cc414f17278d49c7116607963991c3cd05f.png) are two arbitrary numbers. The solution to this system of equations is
    
    ![\!
    \left\{ \!\!
    \begin{array}{rl}
    x_1 \!\!\!\!\! & = s \\
    x_2 \!\!\!\!\! & = c_2 - a_2t, \\
    x_3 \!\!\!\!\! & = t
    \end{array} \; 
    \forall s,t \in \mathbb{R}\!
    \right\}
    = 
    \left\{ \!\!
    \begin{bmatrix} 0 \\ c_2 \\ 0 \end{bmatrix} \!
    + s\! 
    \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} \!
    + t \!
    \begin{bmatrix} 0 \\ -a_2 \\ 1 \end{bmatrix}\!\!,\; 
    \forall s,t \in \mathbb{R} \!
    \right\}\!.](./images/643a25e1d99d4dee136cb14a494c7b79460d9b13.png)
    
    This solution set corresponds to the _parametric equation_ of a plane that contains the point ![(0,c_2,0)](./images/b0f2317cecc132b9f98dcd8f1c5a7adfd91e6d57.png) and the vectors ![(1,0,0)](./images/9e1166baa708e742a15d8042b9584b63a07fe1d9.png) and ![(0,-a_2,1)](./images/e039bb5efe7174a515ac42dcee32573097d704a2.png).
    
    The _general equation_ for the solution plane is ![0x + 1y + a_2z = c_2](./images/1c84adaf9e603860dbb55deadfb6f7d182b0dc94.png), as we can observe from the first row of the augmented matrix. We’ll learn more about the geometry of planes and how to convert between their general and parametric forms in[Section 4.1](./Chapter 4_ Geometric aspects of linear algebra.md).
    
-   **No solutions**. If there are no numbers ![(x_1,x_2,x_3)](./images/8a4b0f0600dc1c85862eb769a4bc48cc98e12e5c.png) that simultaneously satisfy all three equations, the system of equations has no solution. An example of a system of equations with no solution is the pair ![s+t=4](./images/78146d3c42bd1a219f29636591a0e3419b5974c0.png) and ![s+t=44](./images/cf5a883646a3915a9b6a753c21776c82171edff9.png). There are no numbers ![(s,t)](./images/dfa51b2dc0a66fb2b46afc9f65fcfec9b111c1d8.png) that satisfy both of these equations.
    
    A system of equations has no solution if its reduced row echelon form contains a row of zero coefficients with a nonzero constant in the right side:
    
    ![\left[ \begin{array}{ccc|c}
    1 & 0 & 0   \; \; &  \; c_1 \\
    0 & 1 & 0   \; \; &  \; c_2 \\
    0 & 0 & 0   \; \; & \; c_3 
    \end{array}\right]\!.](../Images/f6401890c4e6f1774d6e17370168631ad795d134.png)
    
    If ![c_3 \neq 0](./images/e5f57bfda95da651c88e3a1435629e58e2ba238a.png), this system of equations is impossible to satisfy. There is no solution because there are no numbers ![(x_1,x_2,x_3)](./images/8a4b0f0600dc1c85862eb769a4bc48cc98e12e5c.png) such that ![0x_1+0x_2+0x_3=c_3](./images/4d1de41977145e23de25e84bd06cbf133998cf34.png).
    

Dear reader, we’ve reached a moment in this book where you’ll need to update your math vocabulary. The solution to an individual equation is a finite set of points. The solution to a _system_ of equations can be an entire space containing infinitely many points, such as a line or a plane. Please update your definition of the term _solution_ to include the new, more specific term _solution set_—the set of points that satisfy the system of equations. The _solution set_ of a system of three linear equations in three unknowns could be either the empty set ![\{ \emptyset \}](./images/93a7420c3b6251d9d1bc523744318a2be533ebaf.png) (no solution), a set with one element ![\{ (x_1,x_2,x_3) \}](./images/49e3d526ae8c7dc5bc78b25d70823b3ffaacd9d5.png), or a set with infinitely many elements like a line ![\{ p_{\textrm{o}}+t\:\vec{v}, t \in \mathbb{R} \}](./images/3aad303bee42d097285e4c3c6dd6803f4a6c3717.png) or a plane ![\{ p_{\textrm{o}}+s\,\vec{v} + t\,\vec{w}, \; s,t \in \mathbb{R} \}](./images/aa9872b0b5a54e3914e068f352908890ea136ce9.png). Another possible solution set is all of ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png), where every vector ![\vec{x} \in \mathbb{R}^3](./images/9cdaa42fcbe5056fd30e5d8cadc73cdc5bcad040.png) is a solution to the equation:

![\begin{bmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0 
\end{bmatrix}\!\!
\begin{bmatrix}
x_1 \\ x_2 \\ x_3
\end{bmatrix}
=					
\begin{bmatrix}
0 \\ 0 \\ 0
\end{bmatrix}\!.](./images/e12344ab01b17cc217aa7eeef0e7b95dd440d3b8.png)

Note the distinction between the three types of infinite solution sets. A line is one-dimensional, a plane is two-dimensional, and ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) is three-dimensional. Describing all points on a line requires one parameter, describing all points on a plane takes two parameters, and describing a point in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) takes three parameters.

###[Geometric interpretation](./Front matter.md)

We can gain some intuition about solution sets by studying the geometry of the intersections of lines in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png) and planes in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png).

####[Lines in two dimensions](./Front matter.md)

Equations of the form ![ax + by = c](./images/42ee2424cdf16a2480ad7b64bff19712203fcb86.png) correspond to lines in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png). Solving systems of equations of the form

![\begin{align*}
a_1 x + b_1 y & = c_1 	\\
a_2 x + b_2 y & = c_2
\end{align*}](./images/6b121a8509feb05d9722a3c406d362af52c4b36d.png)

requires finding the point ![(x,y) \in \mathbb{R}^2](./images/230ae6e306621590c91814a23ea728bae276fe20.png) where these lines intersect. There are three possibilities for the solution set:

-   **One solution** if the two lines intersect at a point
-   **Infinitely many solutions** if the lines are superimposed
-   **No solution** if the two lines are parallel and never intersect

See figures[1.67](./Chapter 1_ Math fundamentals.md),[1.68](./Chapter 1_ Math fundamentals.md), and[1.69](./Chapter 1_ Math fundamentals.md) (pages 1.67–1.69) for an illustration.

####[Planes in three dimensions](./Front matter.md)

Equations of the form ![ax + by + cz = d](./images/9127ff243e829b2850d6ae5b33161fdcb12f666d.png) correspond to planes in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png). When solving three such equations,

![\begin{align*}
a_1 x + b_1 y + c_1 z & = d_1, \\
a_2 x + b_2 y + c_2 z & = d_2, \\
a_3 x + b_3 y + c_3 z & = d_3,
\end{align*}](./images/2b2e86d47619feafca0efd6b9c1b66f50e04972d.png)

we want to find the points ![(x,y,z)](./images/ab8147f25510506ccc5d4d1090c36e74e6becf81.png) that satisfy all three equations simultaneously. There are four possibilities for the solution set:

-   **One solution**. Three non-parallel planes intersect at a point.
-   **Infinitely many solutions**. If one of the plane equations is redundant, the solution corresponds to the intersection of two planes. Two non-parallel planes intersect on a line.
-   **Infinitely many solutions in two dimensions**. If two of the equations are redundant, the solution space is a two-dimensional plane.
-   **No solution**. If no common points exist at the intersection of all three planes, then the system of equations has no solution.

![plane_intersections_solutions](./images/plane_intersections_solutions.png)

Figure 3.1: Three planes can intersect at a unique point, as in figure (a); or along a line, as in figure (b). In the first case, there is a unique point ![(x_{o},y_{o},z_{o})](./images/450ffba8c4255474a9b396a0606d066326aab2a7.png) common to all three planes. In the second case, all points on the line ![\{p_{o} + t \vec{v}, \; \forall t \in \mathbb{R} \}](./images/8ba1fc572ca3f5f60b69dadff073e44f5fabda83.png) are shared by the planes.

![plane_intersections_no_solutions](./images/plane_intersections_no_solutions.png)

Figure 3.2: These illustrations depict systems of three equations in three unknowns that have no solution. No common points of intersection exist.

###[Computer power](./Front matter.md)

The computer algebra system at[`http://live.sympy.org`](./live.sympy.org.md) can be used to compute the reduced row echelon form of any matrix.

Here is an example of how to create a sympy `Matrix` object:

\>>> from sympy.matrices import Matrix
>>> A = Matrix(\[\[1, 2,  5\],      # use SHIFT+ENTER for newline
                \[3, 9, 21\]\]) 

In `Python`, we define lists using the square brackets `[` and `]`. A matrix is defined as a list of lists.

To compute the reduced row echelon form of `A`, call its `rref()` method:

\>>> A.rref()
( \[1, 0, 1\] # RREF of A         # locations of pivots
  \[0, 1, 2\],                    \[0, 1\]               ) 

The `rref()` method returns a tuple containing the RREF of `A` and an array that tells us the 0-based indices of the columns that contain leading ones. Usually, we’ll want to find the RREF of `A` and ignore the pivots; to obtain the RREF without the pivots, select the first (index zero) element in the result of `A.rref()`:

\>>> Arref = A.rref()\[0\]
>>> Arref
\[1, 0, 1\]
\[0, 1, 2\]  

The `rref()` method is the fastest way to obtain the reduced row echelon form of a `SymPy` matrix. The computer will apply the Gauss–Jordan elimination procedure and show you the answer. If you want to see the intermediary steps of the elimination procedure, you can also manually apply row operations to the matrix.

#####[Example](./Front matter.md)

Let’s compute the reduced row echelon form of the same augmented matrix by using row operations in `SymPy`:

\>>> A = Matrix(\[\[1, 2,  5\],
                \[3, 9, 21\]\])

>>> A\[1,:\] = A\[1,:\] - 3\*A\[0,:\]
>>> A
\[1, 2, 5\]
\[0, 3, 6\]

We use the notation `A[i,:]` to refer to entire rows of the matrix. The number `i` specifies the ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png)\-based row index: the first row of `A` is `A[0,:]` and the second row is `A[1,:]`. The code example above implements the row operation ![R_2 \gets R_2 - 3R_1](./images/fb500f7ee9892774999183ff5cc78dff5362cfac.png).

To obtain the reduced row echelon form of the matrix `A`, we carry out two more row operations, ![R_2 \gets \frac{1}{3}R_2](./images/a4bc8b81a525d2f8e6de557459c7f63acac6314a.png) and ![R_1 \gets R_1 - 2R_2](./images/c9fe4f74671bcc370ee5e99a29db8b0e89f9af6c.png), using the following commands:

\>>> A\[1,:\] = S(1)/3\*A\[1,:\]
>>> A\[0,:\] = A\[0,:\] - 2\*A\[1,:\]
>>> A    
\[1, 0, 1\]           # the same result as A.rref()\[0\]
\[0, 1, 2\]   

Note we represent the fraction ![\frac{1}{3}](./images/2e1382258077dc418e81971924dd9f4f09b9215a.png) as `S(1)/3` in order to obtain the exact rational expression `Rational(1,3)`. If we were to input ![\frac{1}{3}](./images/2e1382258077dc418e81971924dd9f4f09b9215a.png) as `1/3`, `SymPy` would interpret this either as integer or floating point division, which is not what we want. The single-letter helper function `S` is an alias for the function `sympify`, which ensures a `SymPy` object is produced. Another way to input the exact fraction ![\frac{1}{3}](./images/2e1382258077dc418e81971924dd9f4f09b9215a.png) is `S(’1/3’)`.

If you need to swap two rows of a matrix, you can use the standard Python tuple assignment syntax. To swap the position of the first and second rows, use

\>>> A\[0,:\], A\[1,:\] = A\[1,:\], A\[0,:\] 
>>> A    
\[0, 1, 2\]
\[1, 0, 1\] 

Using row operations to compute the reduced row echelon form of a matrix allows you to see the intermediary steps of a calculation; which is useful, for instance, when checking the correctness of your homework problems.

There are other applications of matrix methods that use row operations (see[Section 7.6](./Chapter 7_ Applications.md)), so it’s good idea to know how to use `SymPy` for this purpose.

###[Discussion](./Front matter.md)

In this section, we learned the Gauss–Jordan elimination procedure for simplifying matrices, which just so happens to be one of the most important computational tools of linear algebra. Beyond being a procedure for finding solutions to systems of linear equations, the Gauss–Jordan elimination algorithms can be used to solve a broad range of other linear algebra problems. Later in the book, we’ll use the Gauss–Jordan elimination algorithm to compute inverse matrices [Section 3.5](./Chapter 3_ Computational linear algebra.md)) and to “distill” bases for vector spaces [Section 4.5](./Chapter 4_ Geometric aspects of linear algebra.md)).

###[Exercises](./Front matter.md)

You’ve read about linear algebra—now you must apply what you’ve learned. Let’s see if you can solve the exercises in this section. It will probably take you a few hours to complete all of them, but trust me: if you do the work, you’ll reap the rewards.

Imagine you want to join a martial arts school and the master tells you to first practice horse stance for hours before you can learn any moves. Well, this is the math equivalent. You need to know the Gauss–Jordan elimination procedure inside out, since it’s the base on which we’ll build many other linear algebra skills.

E3.1 Consider the system of equations and its augmented matrix representation:

![\begin{array}{rrl}
3x &  + \; \; 		3y 	&	=  \; \; 6	\\
2x &  + \; \, \frac{3}{2}y 	& 	= \; \; 5
\end{array}
\qquad
\Rightarrow
\qquad
\left[\!\!\begin{array}{cc|c} 
3 & 		3  \;  & 6 \\
2 &  \frac{3}{2}    \; & 5 
\end{array}\!\!\right]\!	.](../Images/e5e4aaff03a298f0b8f114b597db83166afa7100.png)

Find the solution to this system of equations by bringing the augmented matrix into reduced row echelon form.

E3.2 Repeat [3.1.10](./Chapter 3_ Computational linear algebra.md) using the calculator at[`http://live.sympy.org`](./live.sympy.org.md). First define the augmented matrix using

\>>> A = Matrix(\[
         \[3,       3,  6\],
         \[2,  S(3)/2,  5\]\])  # note use of S(3)/2 to obtain 3/2

Then perform row operations using `SymPy` to bring the matrix into RREF. Confirm your answer using the direct method `A.rref()`.

E3.3 Find the solutions to the systems of equations that correspond to the following augmented matrices.

1.  ![\left[\!\!\begin{array}{cc|c} 
    3 & 		3  \;  & 6 \\
    1 &  		1   \; & 5 
    \end{array}\!\!\right]\!](../Images/80359efd5ec310a05e979190afdc14e08291eff4.png)          
2.  ![\left[\!\!\begin{array}{cc|c} 
    3 & 		3  \;  & 6 \\
    2 &  \frac{3}{2}   \; & 3 
    \end{array}\!\!\right]\!](../Images/69e7e676ab03de3a12b5b12eb9b93ea064681733.png)          
3.  ![\left[\!\!\begin{array}{cc|c} 
    3 & 		3  \;  & 6 \\
    1 &  		1   \; & 2 
    \end{array}\!\!\right]\!](../Images/abbe01ffe5cf3cce1418f39defc63464b5e1287d.png)

The third system of equations has many solutions.

In this section we learned a practical computational algorithm for solving systems of equations by a using row operations on an augmented matrix. In the next section, we’ll increase the level of abstraction. By “zooming out” one level, we can view the entire system of equations as a matrix equation ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) and solve the problem in one step: ![\vec{x} = A^{-1}\vec{b}](./images/0d62d34451b4b14be91c26e3a018d61ca1d9b6c0.png).

##[3.2 Matrix equations](./Chapter 3_ Computational linear algebra.md)

We can express the problem of solving a system of linear equations as a matrix equation and obtain the solution using the matrix inverse. Consider the following system of linear equations:

![\begin{align*}
x_1 + 2x_2     	& =  5	\\
3x_1 + 9x_2    	& =  21.
\end{align*}](./images/c3b264415e9da169a2c67c36e53818d6da205fe0.png)

We can rewrite this system of equations as a matrix-vector product:

![\begin{bmatrix}
1 & 2 \\
3 & 9 
\end{bmatrix}
\!\!
\begin{bmatrix}
x_1 \\
x_2 
\end{bmatrix}
=
\begin{bmatrix}
5 \\
21
\end{bmatrix}\!,](./images/2a4ddccecfb1df5f239fe1bc605fe108d986a33c.png)

or, more compactly, as ![A\vec{x} = \vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png), where ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is a ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix, ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) is the vector of unknowns (a ![2 \times 1](./images/ff0d917829459a76eae0ac57cc13fac67fe68ba0.png) matrix), and ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png) is a vector of constants (a ![2 \times 1](./images/ff0d917829459a76eae0ac57cc13fac67fe68ba0.png) matrix).

We can solve for ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) in this matrix equation by multiplying both sides of the equation by the inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png):

![A^{-1} A \vec{x} = \mathbbm{1} \vec{x}  = \vec{x} = A^{-1}\vec{b}.](./images/268a248a78855cd4fab22abaa7c390cff4afa56d.png)

Thus, to solve a system of linear equations, we can find the inverse of the matrix of coefficients, then compute the product:

![\vec{x} = \begin{bmatrix}x_1 \\ x_2 \end{bmatrix} =
A^{-1} \vec{b}
= \begin{bmatrix}
3  & -\frac{2}{3}  \\
-1 & \frac{1}{3}  
\end{bmatrix}
\!\!
\begin{bmatrix}5 \\  21 \end{bmatrix}
=
\begin{bmatrix}1 \\  2 \end{bmatrix}.](./images/43380c7803cafdddedc65e8bdfd46ef8c6c7eaec.png)

The amount of effort it takes to find ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) is roughly equivalent to the effort needed to bring an augmented matrix ![[\:A\; | \; \vec{b}\:]](../Images/2d800063df7c3d7f3ce6ef8fb9bdc52d1dca9a26.png) to reduced row echelon form—it’s not like we’re given the solution for free by simply rewriting the system of equations in matrix form. Nevertheless, expressing the system of equations as ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) and its solution as ![\vec{x} = A^{-1}\vec{b}](./images/0d62d34451b4b14be91c26e3a018d61ca1d9b6c0.png) is useful in that it saves us from needing to juggle dozens of individual coefficients. The same symbolic expression ![\vec{x} = A^{-1}\vec{b}](./images/0d62d34451b4b14be91c26e3a018d61ca1d9b6c0.png) applies whether ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is a ![2\times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix or a ![1000 \times 1000](./images/2e94cd41921bbd6d5b3e5fddac439793178448ba.png) matrix.

###[Introduction](./Front matter.md)

It’s time we had an important discussion about matrix equations and how they differ from regular equations with numbers. If ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) are three numbers, and I tell you to _solve_ for ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) in the equation

![ab = c,](./images/b43f1fd2e18f9452989d7f31ad5cedae57b1fe60.png)

you’d know the answer is ![a = c/b = c\frac{1}{b}=\frac{1}{b}c](./images/994d2af20ebf077149e7568cccfb31f947ead5f9.png), and that would be the end of it.

Now suppose ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), and ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png) are matrices and you want to solve for ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) in the matrix equation

![AB = C.](./images/41278c07ddfb80a446adfd1191a0f217877c5c21.png)

The answer ![A=C/B](./images/1ef1a5e0a5a9cddd1ae9aa9395ea02a6a63bbf04.png) is not allowed. So far, we defined matrix _multiplication_ and matrix _inversion_, but not matrix _division_. Instead of dividing by ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), we must multiply by ![B^{-1}](./images/3ce81de543e8cf47a1570a7cb200d40a7c3786c1.png), which has the same effect as a “divide by ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)” operation. The product of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![B^{-1}](./images/3ce81de543e8cf47a1570a7cb200d40a7c3786c1.png) gives the identity matrix,

![BB^{-1} = \mathbbm{1}, \qquad B^{-1}B = \mathbbm{1}.](./images/b8dd38b2850dfb25be1830fcd3357b98c43a9380.png)

When applying the inverse matrix ![B^{-1}](./images/3ce81de543e8cf47a1570a7cb200d40a7c3786c1.png) to the equation, we must specify whether we are multiplying from the left or from the right, because matrix multiplication is not commutative. Can you determine the correct answer for ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) in the above equations? Is it ![A = CB^{-1}](./images/336b778ac60119b48114c634d5e2e150f1fb3b8c.png) or ![A = B^{-1}C](./images/eb80f60a863965a58de99c4c82852747ef658fb5.png)?

To solve matrix equations, we employ the same technique we used to solve equations in[Chapter 1](./Chapter 1_ Math fundamentals.md): undoing the operations that stand in the way of the unknown. Recall that we must always **do the same thing to both sides of an equation** for it to remain true.

With matrix equations, it’s the same story all over again, but there are two new things you need to keep in mind:

-   The order in which matrices are multiplied matters. Matrix multiplication is not a commutative operation, ![AB \neq BA](./images/945c74acf897e385f9922efafe4cbdf20d3443e6.png). The expressions ![ABC](./images/257b9f3d6c7fdfaaba480f0835f7b6ac4670f521.png) and ![BAC](./images/44fa489d6a454cdf31bb5e0d92753fc96d0de865.png) are different despite the fact that they are the product of the same three matrices.
-   When performing operations on matrix equations, you can act either _from the left_ or _from the right_ on the equation.

The best way to familiarize yourself with the peculiarities of matrix equations is to look at example calculations. Don’t worry, there won’t be anything too mathematically demanding in this section; we’ll just look at some pictures.

###[Matrix times vector](./Front matter.md)

Suppose we want to solve the equation ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png), in which an ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) multiplies the vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) to produce a vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png). Recall, we can think of vectors as “tall and skinny” ![n \times 1](./images/3090ba3f3c80de1e80bc520aaec116200eb116f6.png) matrices.

The picture corresponding to the equation ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) is

![linear_algebra--ax_eq_b_step1](./images/linear_algebra--ax_eq_b_step1.png) .

Assuming ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible, we can multiply by the inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) on the left of both sides of the equation:

![linear_algebra--ax_eq_b_step2](./images/linear_algebra--ax_eq_b_step2.png) .

By definition, ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) times its inverse ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is equal to the identity matrix ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png), which is a diagonal matrix with ones on the diagonal and zeros everywhere else:

![linear_algebra--ax_eq_b_step3](./images/linear_algebra--ax_eq_b_step3.png) .

Any vector times the identity matrix remains unchanged, so

![linear_algebra--ax_eq_b_step4](./images/linear_algebra--ax_eq_b_step4.png) ,

which is the final answer.

Note that the question “Solve for ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) in ![A\vec{x} = \vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png)” sometimes arises in situations where the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is not invertible. If the system of equations is under-specified (![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is wider than it is tall), there will be a whole subspace of acceptable solutions ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png). Recall the cases with infinite solutions (lines and planes) we saw in the previous section.

###[Matrix times matrix](./Front matter.md)

Let’s look at some other matrix equations. Suppose we want to solve for ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) in the equation ![AB=C](./images/cd9c4620d57c6bd12d126d0b4d3a212d38e67c67.png):

![linear_algebra--aab_eq_c_step1](./images/linear_algebra--aab_eq_c_step1.png) .

To isolate ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), we multiply by ![B^{-1}](./images/3ce81de543e8cf47a1570a7cb200d40a7c3786c1.png) _from the right_ on both sides:

![linear_algebra--aab_eq_c_step2](./images/linear_algebra--aab_eq_c_step2.png) .

When ![B^{-1}](./images/3ce81de543e8cf47a1570a7cb200d40a7c3786c1.png) hits ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), the matrices cancel (![BB^{-1}=\mathbbm{1}](./images/5bf2d1e26c74ce5db228bc9901ee70d888b4fc32.png)) and we obtain

![linear_algebra--aab_eq_c_step3](./images/linear_algebra--aab_eq_c_step3.png) .

###[Matrix times matrix variation](./Front matter.md)

What if we want to solve for ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) in the same equation ![AB=C](./images/cd9c4620d57c6bd12d126d0b4d3a212d38e67c67.png)?

![linear_algebra--abb_eq_c_step1](./images/linear_algebra--abb_eq_c_step1.png) .

Again, we must _do the same_ to both sides of the equation. To cancel ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), we need to multiply by ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) from the left:

![linear_algebra--abb_eq_c_step2](./images/linear_algebra--abb_eq_c_step2.png) .

When ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) cancels with ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), we obtain the final result

![\qquad \qquad \qquad \qquad](./images/6c29e9512c5d582f62cf8cb53108444b9aa09554.png) ![linear_algebra--abb_eq_c_step3](./images/linear_algebra--abb_eq_c_step3.png) .

This completes our lightning tour of matrix equations. There is really nothing new to learn here; just make sure you’re aware that the _order_ in which matrices are multiplied matters, and remember the general principle of “doing the same thing to both sides of the equation.” Acting according to this principle is essential in all of math, and particularly important when manipulating noncommutative operations as in matrix equations.

In the next section, we’ll “zoom in” on matrix equations by examining the arithmetic operations performed on matrix entries during multiplication.

###[Exercises](./Front matter.md)

E3.4 Solve for ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) in the following matrix equations: **a)** ![XA=B](./images/4f60bda8fb7d2f2893dc41807c9168c68d6b11b3.png), **b)** ![ABCXD = E](./images/4fe93f2055b5fe27d1fb91b395ccfae6a4e5c356.png), and **c)** ![AC = XDC](./images/1276baa27a7a07b9a4431b098f3f892493e37ae4.png). You can assume the matrices ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png), ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png), and ![E](./images/80475983a19b0a9300f24e29f61de72089cf32a2.png) are all invertible.

##[3.3 Matrix multiplication](./Chapter 3_ Computational linear algebra.md)

Suppose we’re given the matrices

![A = 
\left[
\begin{array}{cc}
a&b \\
c&d
\end{array}
\right]\! 
\qquad 
\textrm{and}
\qquad
B = 
\left[
\begin{array}{cc}
e&f \\
g&h
\end{array}
\right]\!,](../Images/bc276e1dbe02d47ef101da84eb81d782fd222c5e.png)

and we want to compute the _matrix product_ ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png).

Unlike matrix addition and subtraction, matrix multiplication is _not_ performed entry-wise:

![\left[
\begin{array}{cc}
a&b \\
c&d
\end{array}
\right] \!
\left[
\begin{array}{cc}
e&f \\
g&h
\end{array}
\right] 
\; 
\neq
\; 
\left[
\begin{array}{cc}
ae&bf \\
cg&dh
\end{array}
\right]\!.](../Images/40c0982a4969535981004f8e6754ca70a5e56e5c.png)

Instead, the matrix product is computed by taking the dot product between each row of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and each column of the matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![\begin{align*}
\begin{array}{c}
\begin{array}{c} 
\vec{r}_1 \rightarrow \\
\vec{r}_2 \rightarrow 
\end{array}
\!\!
\left[
\begin{array}{cc}
a & b \\
c & d
\end{array}
\right] \\
\; \\
\; 
\end{array}
\!\!\!\!\!\!
\begin{array}{c}
\left[
\begin{array}{cc}
e&f \\
g&h
\end{array}
\right] \\
\uparrow \; \; \; \,  \uparrow  \\
{\vec{c}_1} \; \; \;  {\vec{c}_2}
\end{array} 
&
\begin{array}{c} 
= \\
\;  \\
\; 
\end{array}
\begin{array}{c} 
\left[
\begin{array}{cc}
\vec{r}_1 \cdot \vec{c}_1  & 	\; \; \vec{r}_1 \cdot \vec{c}_2   \\
\vec{r}_2 \cdot \vec{c}_1  & 	\; \; \vec{r}_2 \cdot \vec{c}_2 
\end{array}
\right] \\
\;  \\
\; 
\end{array} \\
& \; =
\; \;  \left[
\begin{array}{cc}
ae+ bg  & af + bh  \\
ce + dg & cf + dh
\end{array}
\right]\!.
\end{align*}](../Images/23fae57614e45d0ef82402dd328d7e81a363b235.png)

Recall the dot product between two vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) is computed using the formula ![\vec{v}\cdot \vec{w} = \sum_i v_iw_i](./images/88ad82490170be00d0c4ac7b5621f5d80b710cbd.png).

Now, let’s look at a picture that shows how to compute the product of a matrix with four rows and another matrix with five columns. To compute the top left entry of the result, take the dot product of the first row of the first matrix and the first column of the second matrix.

![linear_algebra--matrix_multiplication_ex1](./images/linear_algebra--matrix_multiplication_ex1.png)

Figure 3.3: Matrix multiplication is performed rows-times-columns. The first-row, first-column entry of the product is the dot product of ![r_1](./images/1307ba0bcc6f70f864872f9c199fd787e6b1587b.png) and ![c_1](./images/58893cd9da407062010d0f38a6bd6c0cf8bfa5a7.png).

Similarly, the entry on the third row and fourth column of the product is computed by taking the dot product of the third row of the first matrix and the fourth column of the second matrix. See[Figure 3.4](./Front matter.md).

![linear_algebra--matrix_multiplication_ex2](./images/linear_algebra--matrix_multiplication_ex2.png)

Figure 3.4: The third-row, fourth-column entry of the product is computed by taking the dot product of ![r_3](./images/e446f60136c16ee1f13d39a7766b0704927941bd.png) and ![c_4](./images/12cafcc65cd3f8d230d65bfc0a9a6c668eac4490.png).

For the matrix product to work, the rows of the first matrix must have the same length as the columns of the second matrix.

###[Matrix multiplication rules](./Front matter.md)

-   Matrix multiplication is associative:
    
    ![(AB)C = A(BC) = ABC.](./images/ca48a32c8ac69cadaf2a1273964bb70bf83c8e4d.png)
    
-   The touching dimensions of the matrices must be the same. For the triple product ![ABC](./images/257b9f3d6c7fdfaaba480f0835f7b6ac4670f521.png) to exist, the rows of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) must have the same dimension as the columns of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), and the rows of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) must have the same dimension as the columns of ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png).
-   Given two matrices ![A \in \mathbb{R}^{m\times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) and ![B \in \mathbb{R}^{n\times k}](./images/cc11e436ad85114a36eb0f2ac1df3d03b0dca491.png), the product ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png) is an ![m \times k](./images/fc506368e86cc5f653bbf7cd0f886ed528808e6a.png) matrix.
-   Matrix multiplication is not a commutative operation.

![linear_algebra--matrix_multiplication_not_commutative](./images/linear_algebra--matrix_multiplication_not_commutative.png)

Figure 3.5: The order of multiplication matters for matrices: the product ![AB](./images/ba90019888e8cb9ef51160a7cd7cb8ec3c63edda.png) does not equal the product ![BA](./images/963b816e55c8e1a8ee9f5511d1fc2f015eb274b3.png).

#####[Example](./Front matter.md)

Consider the matrices ![A \in \mathbb{R}^{2 \times 3}](./images/653aa08f677af5e703182c7bbb59d44441f404b4.png) and ![B \in \mathbb{R}^{3 \times 2}](./images/199bf9c74e882a24fc419bb4bce6bd9f6b84e793.png). The product ![AB=C \in \mathbb{R}^{2 \times 2}](./images/1e8e46c53c7d9e38a752918ec24bbc139483213a.png) is computed as

![\underbrace{\!\!
\begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 &6 \end{bmatrix} \!\!}_A
\:
\underbrace{ \!\!
\begin{bmatrix} 1 & 2 \\ 3 & 4 \\  5 & 6 \end{bmatrix} \!\!}_B
\; =
\begin{bmatrix} 1+6+15 & 2 +8 +18  \\ 4 + 15+ 30 & 8 + 20 + 36 \end{bmatrix}
=
\; 
\underbrace{\!\!
\begin{bmatrix} 22 & 28 \\ 49 & 64 \end{bmatrix} \!\!}_{C}.](./images/76c3a89344a2f01b054e7c2075e218f92df4faa2.png)

We can also compute the product ![BA=D \in \mathbb{R}^{3 \times 3}](./images/b98b217d2f5322758d42b3154995307276cbc97f.png):

![\underbrace{ \!\!
\begin{bmatrix} 1 & 2 \\ 3 & 4 \\  5 & 6 \end{bmatrix} \!\!}_B
\:
\underbrace{\!\!
\begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 &6 \end{bmatrix} \!\!}_A
\; =
\begin{bmatrix} 1+8 &  2+10 & 3+12 \\ 3+16 & 6+20 & 9+24 \\ 5+24 & 10+30 & 15+36 \end{bmatrix}
=
\; 
\underbrace{\!\!
\begin{bmatrix}  9 & 12 & 15 \\ 19 & 26 & 33 \\ 29 & 40 & 51 \end{bmatrix} \!\!}_{D}.](./images/c420caf7364d445b8e9ec86b2f2c3f7bea5357a3.png)

In each case, the touching dimensions of the two matrices in the product are the same. Note that ![C=AB \neq BA = D](./images/31559ab7e7cd051df69280ae32662a817544556d.png), and in fact, the products ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png) and ![BA](./images/58910eb14ca75c4168a6f7410c0420693ae4e4f0.png) are matrices with different dimensions.

###[Applications](./Front matter.md)

Why is matrix multiplication defined the way it is defined?

####[Composition of linear transformations](./Front matter.md)

The long answer to this question will be covered in depth when we reach the chapter on linear transformations [Section 5](./Chapter 5_ Linear transformations.md), page 5). Since I don’t want you to live in suspense, I’ll give you the short answer now. We can think of multiplying a column vector ![\vec{x} \in \mathbb{R}^n](./images/4671e225c1d3d806bc3ce99567ead571061ea9b1.png) by a matrix ![A \in \mathbb{R}^{m\times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) as analogous to applying a _linear transformation_ ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) of the form:

![T_A: \mathbb{R}^n \to \mathbb{R}^m.](./images/9d2bfe26c3c1490c77f342d9e1942c5d5690a06d.png)

Applying the linear transformation ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) to the input ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) is the same as computing the matrix-vector product ![A\vec{x}](./images/1013646b0165a8b1f4e2bcaca5e29639cc92eae1.png):

![\textrm{for all } \vec{x} \in \mathbb{R}^n, \quad  T_A\!\left(\vec{x}\right) = A\vec{x}.](./images/41be738d65df1f473aa9f4d70f1f35f2633d49a8.png)

Every linear transformation from ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) to ![\mathbb{R}^m](./images/4d4f5acbadc1b9a3febf3642dbe25d99a4704061.png) can be described as a multiplication by some matrix ![A \in \mathbb{R}^{m\times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png).

What happens when we apply two linear transformations in succession? When we do this to ordinary functions, we call it _function composition_, and denote it with a little circle:

![g\circ\!f\:(x) = g(f(x)),](./images/406a23ff2b1c30765bfad9fbeac40a7dd448d73a.png)

where ![g\circ f\;(x)](./images/5fff8e52575b8a7e7cd90a73621e02460f1ad944.png) indicates we should first apply ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) to ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), then apply ![g](./images/1946b9850ac13de564c7e979735a85b5419ff434.png) to the output of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png). The composition of two linear transformations ![T_B\circ T_A](./images/4ea971586a02456bac60d6e61f57181fe2e2b716.png) (applying ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) then ![T_B](./images/3eb6f9b23c111571cd293fd118b9b082bddfa6bd.png)) corresponds to multiplication by matrices ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png):

![T_B\circ T_A (\vec{x})
= T_B\!\left( T_A(\vec{x}) \right)
= B(A \vec{x})
= (BA) \vec{x}.](./images/e5379188ac05af31f35db47346fb9da64cc25d0b.png)

Note we can describe the composite transformation ![T_B\circ T_A](./images/4ea971586a02456bac60d6e61f57181fe2e2b716.png) by the matrix ![BA](./images/58910eb14ca75c4168a6f7410c0420693ae4e4f0.png), which is the product of matrices ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). **Matrix products enable us to easily compose linear transformations.**

Understanding the connection between matrices and linear transformations helps explain why matrix multiplication is not commutative. In general, ![BA \neq AB](./images/1e8a826c68e3979c98e7ec9cce335794d5c48b80.png): there’s no reason to expect ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png) will equal ![BA](./images/58910eb14ca75c4168a6f7410c0420693ae4e4f0.png), just as there’s no reason to expect that ![f \circ g](./images/525b5a0d10c1db2e3036359cd5005c80a885d52d.png) will equal ![g \circ f](./images/00b94fb0e48a7929191b550d158b8db814c42d63.png) for two arbitrary functions.

Matrix multiplication is an extremely useful computational tool. At the moment, your feelings about matrix multiplication might not be so warm and fuzzy, given it can be tedious and repetitive. Be patient and stick with it. Solve some exercises to make sure you understand. Afterward, you can let computers multiply matrices for you—because computers are good at repetitive tasks.

####[Row operations as matrix products](./Front matter.md)

There is an important connection between row operations and matrix multiplication. Performing the row operation ![\mathcal{R}](./images/292f5e6542a43a174b008b49eaff3627381bc3d0.png) on a matrix is equivalent to a left multiplication by an _elementary matrix_ ![E_{\mathcal{R}}](./images/1dcf3505688a7912c896e9126ae744b2aef2a194.png):

![A' = \mathcal{R}(A)
\qquad
\Leftrightarrow
\qquad 
A' = E_{\mathcal{R}}A.](./images/8ee7fda527f314d57746d55cddadab1058ff3c8d.png)

There are three types of elementary matrices that correspond to the three types of row operations. Let’s look at an example.

#####[Example](./Front matter.md)

The row operation of adding ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) times the second row to the first row (![\mathcal{R} : R_1 \gets R_1 + mR_2](./images/fa227e354e287bdbd4b316e7dcfb55bda1d78df8.png)) corresponds to the elementary matrix

![\begin{align*}
E_{\mathcal{R}} = 
\begin{bmatrix}
1 & m \\
0 & 1 
\end{bmatrix}\!,
\; \; 
\textrm{which acts as}
\; \; 
\begin{bmatrix}
1 & m \\
0 & 1 
\end{bmatrix}\!\!
\begin{bmatrix}
a & b \\
c & d 
\end{bmatrix}
= 
\begin{bmatrix}
a+mc & \!b+md \\
c & d 
\end{bmatrix}\!. 
\end{align*}](./images/15a63fab55aab96094e45a69c8d4f30bd394f6c8.png)

We’ll discuss elementary matrices in more detail in[Section 3.5.4](./Chapter 3_ Computational linear algebra.md).

We can also perform column operations on matrices if we multiply them by elementary matrices from the right.

###[Exercises](./Front matter.md)

E3.5 Compute the following matrix products:

![P = 
\begin{bmatrix} 	1&2 \\   3&4  \end{bmatrix}
\!\!
\begin{bmatrix} 	5&6 \\   7&8  \end{bmatrix}
\quad
\textrm{and}
\quad
Q = 
\begin{bmatrix}	
3& 1 &  2&  2 \\ 0 & 2 & -2 & 1
\end{bmatrix}\!\!				\begin{bmatrix}
-2 &  3 \\  
\; \; 1 &  0 \\  
-2 & \!\!-2 \\  
\; \; 2 &  2 
\end{bmatrix}\!.](./images/329e994ff0de4f55d629880ba07d072e17ca7426.png)

E3.6 Consider the following matrices of different dimensions:

![A \!=\!
\begin{bmatrix}
2	& 	3	\\
5 	&	6
\end{bmatrix}	\!,
\; 
B \!= \!
\begin{bmatrix}
7	& 	8	\\
1 	&	4
\end{bmatrix}	\!,
\; 
C \!=\! 
\begin{bmatrix}
-1	& 	4	\\
2 	&	1	\\
-1	&	2
\end{bmatrix}	\!,
\; 
U \!=\!
\begin{bmatrix}
2 & 1
\end{bmatrix}	\!,
\; 
\textrm{and}
\; 
V \! = \!
\begin{bmatrix}
1		\\
-2
\end{bmatrix}	\!.](./images/73a3c80c3f9007f605bad2c51695c55edd3c8760.png)

Compute the following matrix expressions.

1.  ![A^2](./images/a0d61abbc27f436fbb804c112345805d7ce3a569.png)
2.  ![B^2](./images/38db21f980b92e2cfac8c484f3d7a8cf55fa1772.png)
3.  ![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png)
4.  ![BA](./images/58910eb14ca75c4168a6f7410c0420693ae4e4f0.png)
5.  ![AC](./images/aa7d723b084d934250963427b8540e10d4c7e0e9.png)
6.  ![CA](./images/55dc0313568474c622c19ff006faac5e3c0bf127.png)
7.  ![UABV](./images/88039f52963e11a15a043425633b99a1e681e45e.png)

##[3.4 Determinants](./Chapter 3_ Computational linear algebra.md)

What is the volume of a rectangular box of length ![1\,](./images/3e0ee12bfaeac49dd6eb9bf5770ac6996a80fd2f.png)m, width ![2\,](./images/272e1b0f0122f01bdc769366c2acc82330e2b7ab.png)m, and height ![3\,](./images/d0599a0161293d62f72f247921f2c123629b3238.png)m? It’s easy to compute the volume of this box because its shape is a _right rectangular prism_. The volume of this rectangular prism is ![V=\ell \times w \times h = 6\,](./images/8869cdfa9c18933d74885fd19ee0e47ff3433b2a.png)m![^3](./images/7b9b50b436322b2a0526474a915ba85eec6b9c72.png). What if the shape of the box was a _parallelepiped_ instead? A parallelepiped is a box whose opposite faces are parallel but whose sides are slanted, as shown in[Figure 3.9](./Chapter 3_ Computational linear algebra.md) on page 3.9. How do we compute the volume of a parallelepiped? The determinant operation, specifically the ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) determinant, is the perfect tool for this purpose.

The determinant operation takes square matrices as inputs and produces numbers as outputs:

![\textrm{det}: \mathbb{R}^{n \times n} \to \mathbb{R}.](./images/6d65229e81525580b5b55f3303224675789b4685.png)

The determinant of a matrix, denoted ![\det(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png) or ![|A|](./images/f395085915c0b82f3f55aa5551b1676f28378881.png), is a particular way to multiply the entries of the matrix to produce a single number. We use determinants for all kinds of tasks: to compute areas and volumes, to solve systems of equations, to check whether a matrix is invertible or not, etc.

We can intuitively interpret the determinant of a matrix as a geometric calculation. The determinant is the “volume” of the geometric shape whose “sides” are the rows of the matrix. For ![2\times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrices, the determinant corresponds to the area of a parallelogram. For ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrices, the determinant corresponds to the volume of a parallelepiped. For dimensions ![d>3](./images/b3acb52ba401d5842a4a6dbe093105104d4103d9.png), we say the determinant measures a ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png)\-dimensional hyper-volume.

Consider the linear transformation ![T:\mathbb{R}^2 \to \mathbb{R}^2](./images/5983a52066d18e5338bbb02e92cb094cfbdd0957.png) defined through the matrix-vector product with a matrix ![A_T](./images/81f26977f2fbdfae28b4e545d3db4507c37524b8.png): ![T(\vec{x}) = A_T\vec{x}](./images/9d82d2680ba1adef54f1198552c7aa3e1bce15f5.png). The determinant of the matrix ![A_T](./images/81f26977f2fbdfae28b4e545d3db4507c37524b8.png) is the _scale factor_ associated with the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). The scale factor of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) describes how the area of a unit square in the input space (a square with dimensions ![1\times 1](./images/f0c3d747f547beb566ee37904af637e54f75fa08.png)) is transformed by ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png). After passing through ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png), the unit square is transformed to a parallelogram with area ![\det(A_T)](./images/02c6d74dbfaeb4eb76a9dba8231493736233cd3e.png). Linear transformations that “shrink” areas have ![\det(A_T) < 1](./images/87958c84a29577000505bd944a98065e3e1f4bad.png), while linear transformations that “enlarge” areas have ![\det(A_T) > 1](./images/b6762ad691ecdcb0076eb4327014ea3149052506.png). A linear transformation that is _area preserving_ has ![\det(A_T)=1](./images/b0eb1a7ddccd2c9c044456458ec8fc7b41eb39e5.png).

![determinant_as_scale_factor_unit_square_tmp](./images/determinant_as_scale_factor_unit_square_tmp.png)

Figure 3.6: A square with side length ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png) in the input space of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is transformed to a parallelogram with area ![\textrm{det}(A_T)](./images/32e5be4e6f22797e35375bda1efe13dcba9883ed.png) in the output space of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png). The determinant measures the _scale factor_ by which the area changes.

The determinant is also used to check linear independence for a given set of vectors. We construct a matrix using the vectors as the matrix rows, and compute its determinant. If the determinant is nonzero, the vectors are linearly independent.

The determinant of a matrix tells us whether or not the matrix is invertible. If ![\det(A)\neq 0](./images/69633a1b936d0299a2d93cf1e2aada740f28d697.png), then ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible; if ![\det(A)=0](./images/4c192db42d3bd89cf462441ca977988e7069d97b.png), ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is not invertible.

The determinant shares a connection with the vector cross product, and is also used in the definition of the eigenvalue equation.

In this section, we’ll discuss all the applications of determinants. As you read along, I encourage you to actively draw connections between the geometric, algebraic, and computational aspects of determinants. Don’t worry if it doesn’t all click right away—you can always review this section once you’ve learned more about linear transformations, the geometry of cross products, and eigenvalues.

###[Formulas](./Front matter.md)

The determinant of a ![2\times2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix is

![\det
\!\left(
\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} 
\end{bmatrix}
\right)
=
\begin{vmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} 
\end{vmatrix}
=a_{11}a_{22}-a_{12}a_{21}.](./images/1b69fbaa6bb5158ce74ce188c50a1cd12bfe0efa.png)

The formulas for the determinants of larger matrices are defined recursively. For example, the determinant of a ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix is defined in terms of ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) determinants:

![\begin{align*}
\; 
&\!\!\!\!\!\!\!\!
\begin{vmatrix}
a_{11} & a_{12} & a_{13} \\ 
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{vmatrix} = 														\\
&=
a_{11}
\begin{vmatrix}
a_{22} & a_{23} \\
a_{32} & a_{33}
\end{vmatrix}
-
a_{12}
\begin{vmatrix}
a_{21} & a_{23} \\
a_{31} & a_{33}
\end{vmatrix}
+
a_{13}
\begin{vmatrix}
a_{21} & a_{22} \\
a_{31} & a_{32}
\end{vmatrix}														\\
&=
a_{11}(a_{22}a_{33}-a_{23}a_{32})
-
a_{12}(a_{21}a_{33} - a_{23}a_{31})
+
a_{13}(a_{21}a_{32} - a_{22}a_{31})									\\
&=
a_{11}a_{22}a_{33}   \qquad - a_{12}a_{21}a_{33} \qquad  + a_{13}a_{21}a_{32}  				\\
& \qquad 
- a_{11}a_{23}a_{32} \qquad  + a_{12}a_{23}a_{31}  \qquad - a_{13}a_{22}a_{31}.
\end{align*}](./images/1c78f6a93d8d863a8499b61c027da4b591c301d3.png)

There’s a neat computational trick for computing ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) determinants by hand. The trick consists of extending the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) into a ![3\times 5](./images/019023ae4d9c1cbf0449d0d82d53d6c6a496847c.png) array that contains copies of the columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png): the first column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is copied to the fourth column of the extended array, and the second column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is copied to the fifth column. The determinant is then computed by summing the products of the entries on the three positive diagonals and subtracting the products of the entries on the three negative diagonals, as illustrated in[Figure 3.7](./Chapter 3_ Computational linear algebra.md).

![determinant_computational_trick-0](./images/determinant_computational_trick-0.png)

Figure 3.7: Computing the determinant using the extended array trick. The solid lines indicate the positive terms while the dashed lines indicate the negative terms in the determinant calculation.

The general formula for the determinant of an ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix is

![\det(A) = \sum_{j=1}^n  \;  (-1)^{1+j}a_{1j}M_{1j},](./images/e77f73b39fe4e9c248703b383a95a7ce7533e02e.png)

where ![M_{ij}](./images/443e3b60ab8c4d4c944621decdf87e8d95310edd.png) is called the _minor_ associated with the entry ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png). The minor ![M_{ij}](./images/443e3b60ab8c4d4c944621decdf87e8d95310edd.png) is the determinant of the submatrix obtained by removing the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th row and the ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th column of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Note the factor ![(-1)^{i+j}](./images/0c6f86dcd2ac79915e3102330991a05a9ab6047b.png) that alternates between the values ![+1](./images/c03be1cb22b5ad56e68076ad4186197cc876c717.png) and ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png) for different terms in the formula.

In the case of ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrices, applying the determinant formula gives the correct formula,

![\begin{align*}
\det(A)  
&= (+1)a_{11}M_{11} + (-1)a_{12}M_{12} + (+1)a_{13}M_{13} \\
&= 
a_{11}
\begin{vmatrix}
a_{22} & a_{23} \\
a_{32} & a_{33}
\end{vmatrix}
-
a_{12}
\begin{vmatrix}
a_{21} & a_{23} \\
a_{31} & a_{33}
\end{vmatrix}
+
a_{13}
\begin{vmatrix}
a_{21} & a_{22} \\
a_{31} & a_{32}
\end{vmatrix}\!.				
\end{align*}](./images/c3ce188c3bfbfadf8edc25eb8f8fb4c433d47ccd.png)

The determinant of a ![4 \times 4](./images/841e9fa0bb8c2499770ffd8babaaf06f37a4a26f.png) matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is

![\det(B)  
= b_{11}M_{11} - b_{12}M_{12} + b_{13}M_{13}  - b_{14}M_{14}.](./images/65de1748956463e114f877959ed8ddd421011843.png)

The determinant formula, ![\det(A) = \sum_{j=1}^n  \;  (-1)^{1+j}a_{1j}M_{1j}](./images/f08cab7fa23da80ad4885b1ec263c8e94e6bfa19.png), assumes we _expand_ the determinant along the first row of the matrix. In fact, a determinant formula can be obtained by expanding the determinant along _any_ row or column of the matrix. For example, expanding the determinant of a ![3\times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix along the second column produces the determinant formula

![\det(A) = \sum_{i=1}^3  (-1)^{i+2}a_{i2}M_{i2}=(-1)a_{12}M_{12} + (1)a_{22}M_{22} + (-1)a_{32}M_{32}.](./images/bb5f96f9f2877592ff86894aaf398bd470857685.png)

The expand-along-any-row-or-column nature of determinants can be very handy: if you need to calculate the determinant of a matrix with one row (or column) containing many zero entries, it makes sense to expand along that row since many of the terms in the formula will be zero. If a matrix contains a row (or column) consisting entirely of zeros, we can immediately tell its determinant is zero.

###[Geometric interpretation](./Front matter.md)

####[Area of a parallelogram](./Front matter.md)

Suppose we’re given vectors ![\vec{v} = (v_1, v_2)](./images/6a397785cb41b9155e6c8bcaa271e1a634a1ea50.png) and ![\vec{w} = (w_1, w_2)](./images/3fb2949284ba0abf3f00ebf98bf355c9ac3f5cb9.png) in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png) and we construct a parallelogram with corner points ![(0,0)](./images/4467446eac588743b0a225c1f23f0769d34ee1f5.png), ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png), and ![\vec{v}+\vec{w}](./images/7ebf2bb27cbe4285ac278ac8c737fbd780107121.png).

The area of this parallelogram is equal to the determinant of the matrix that contains ![(v_1, v_2)](./images/b5bd7b70fbe7a7ecb4cad3e228c4464683186c83.png) and ![(w_1, w_2)](./images/a6ba5731539278aaa2564b6b1b9b769f646df7e5.png) as rows:

![\textrm{area} 
= \begin{vmatrix}
\; v_1 & v_2  \\
w_1 & w_2  \;
\end{vmatrix}
= v_1w_2 - v_2w_1.](./images/6e39855ffdfb3dfe048b47f2a899ad686f86a2bf.png)

![determinant_2d_parallelogram_area](./images/determinant_2d_parallelogram_area.png)

Figure 3.8: The determinant of a ![2\times2](./images/8d9f69fe9ab543dc19bd60e8ea565644efbcebb4.png) matrix corresponds to the area of the parallelogram constructed from the rows of the matrix.

####[Volume of a parallelepiped](./Front matter.md)

Suppose we’re given three vectors: ![\vec{u} = (u_1, u_2, u_3)](./images/e0deb694534bdbb091b1e1bd24e2d5e6ed336ba3.png), ![\vec{v} = (v_1, v_2, v_3)](./images/b5dec8d3fc9b621a78642f27092aa0374f269070.png), and ![\vec{w} = (w_1, w_2,w_3)](./images/ff091c9be1a83544f5b1c892e6a88f6222dddafe.png) in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png). Then suppose we construct the parallelepiped with corner points ![(0,0,0)](./images/6504b17477eb02040594d433af4d4485562e2960.png), ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png), ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png), ![\vec{v}+\vec{w}](./images/7ebf2bb27cbe4285ac278ac8c737fbd780107121.png), ![\vec{u}+\vec{w}](./images/c9f2a74d3916141447348973aa572d7102913bb9.png), ![\vec{u}+\vec{v}](./images/3c2311f5d52e6932259fd54b71fc2017a077c2ba.png), and ![\vec{u}+\vec{v}+\vec{w}](./images/650568ec050565d62567b02aeb7f620921f15883.png), as illustrated in[Figure 3.9](./Chapter 3_ Computational linear algebra.md).

The volume of this parallelepiped is equal to the determinant of the matrix containing the vectors ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png), ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) as rows:

![\begin{align*}
\textrm{volume} &= 
\left|\begin{array}{ccc}
u_1 & u_2 & u_3 \\
v_1 & v_2 & v_3 \\
w_1 & w_2 & w_3 
\end{array}\right| 	\\
&=
u_{1}(v_{2}w_{3} - v_{3}w_{2})
-
u_{2}(v_{1}w_{3} - v_{3}w_{1})
+
u_{3}(v_{1}w_{2} - v_{2}w_{1}).
\end{align*}](./images/4ea350798856581b94d760700429307f27ad6fce.png)

![parallelepiped_uvw](./images/parallelepiped_uvw.png)

Figure 3.9: The determinant of a ![3\times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) matrix corresponds to the volume of the parallelepiped constructed from the rows of the matrix.

####[Sign and absolute value of the determinant](./Front matter.md)

Calculating determinants can produce positive or negative numbers. Consider the vectors ![\vec{v}=(v_1,v_2) \in \mathbb{R}^2](./images/67a303c1c5d84636f067d6bc0aecffa3a89d9473.png) and ![\vec{w}=(w_1,w_2) \in \mathbb{R}^2](./images/25e9c8886890018881b46e9203b8f4b0eadc3585.png) and the determinant

![D =
\det\!\left(
\begin{bmatrix}
\; v_{1} & v_{2} \\
w_{1} & w_{2}
\end{bmatrix}
\right)
=
v_1w_2 - v_2w_1.](./images/454979b5da0254f5780c628ebb0ae315e4922306.png)

Let’s denote the value of the determinant by the variable ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png). The absolute value of the determinant is equal to the area of the parallelogram constructed by the vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png). The sign of the determinant (positive, negative, or zero) tells us information about the relative orientation of the vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png). If we let ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) be the measure of the angle from ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) toward ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png), then the following possibilities exist.

-   If ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is between ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) and ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) (![180^\circ](./images/79177e21de4aca7ef1a1ea67a1e45a189a959c86.png)), the determinant is positive ![D>0](./images/331bd25028048501747b6ca835aaa06eaedaabd2.png). This is the case illustrated in[Figure 3.8](./Chapter 3_ Computational linear algebra.md).
-   If ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is between ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) (![180^\circ](./images/79177e21de4aca7ef1a1ea67a1e45a189a959c86.png)) and ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png) (![360^\circ](./images/e062f6a280550879a6671cfdd99a1487bbf2ec7a.png)), the determinant is negative ![D<0](./images/ae7b0a1b268e780ce06d0e531bd1ed10dfc6ca46.png).
-   When ![\theta=0](./images/2b705e4c8211e7331368d3b370c932d9289ebe9a.png) (the vectors point in the same direction), or when ![\theta=\pi](./images/3409aef1cc99acf633e8d1885c6f2e4f11f633ac.png) (the vectors point in opposite directions), the determinant is zero, ![D=0](./images/91be966e1b08dbd447fd2920ad8d479f5540d43d.png).

The formula for the area of a parallelogram is ![A=b\times h](./images/d0032828eb523fb68ba8c2c13f5974e217ed23b5.png), where ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) is the length of the parallelogram’s base, and ![h](./images/f1ca3cd6c70e90cc02066e90b194d6633838fd36.png) is the parallelogram’s height. In the case of the parallelogram in[Figure 3.8](./Chapter 3_ Computational linear algebra.md), the length of the base is ![\|\vec{v}\|](./images/8f866786ba2376f2849ed080dcb2433d9371ba0f.png) and the height is ![\|\vec{w}\|\sin\theta](./images/547989e8bf1ae0ce3fe4a0d6920915ad4b66f296.png), where ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is the angle measure between ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png). The geometric interpretation of the ![2\times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) determinant is described by the formula,

![D = 
\det\!\left(
\begin{bmatrix}
\; v_{1} & v_{2} \\
w_{1} & w_{2}
\end{bmatrix}
\right)
= \;  \underbrace{\!\!\|\vec{v}\|\!\!}_b\;\underbrace{\!\|\vec{w}\|\sin\theta\!}_h.](./images/506f3084fa3973ac1c865ed6a3d63b803085fdfe.png)

Observe the “height” of the parallelogram is negative when ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is between ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) and ![2\pi](./images/768c9563e9c402ed3cba8fb8a7435edb30634cbc.png).

###[Properties](./Front matter.md)

Let ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) be two square matrices of the same dimension. The determinant operation has the following properties:

-   ![\det(AB) = \det(A)\det(B) = \det(B)\det(A) = \det(BA)](./images/67377113129dfd0135a2c821fde0b793971dadcc.png)
-   If ![\det(A)\neq 0](./images/69633a1b936d0299a2d93cf1e2aada740f28d697.png), the matrix is invertible and ![\det(A^{-1}) = \frac{1}{\det(A)}](./images/c01009f7df3222008c1969462f80d041354c99e7.png)
-   ![\det\!\left( A^\sfT \right)  =  \det\!\left( A \right)](./images/69549d7d0ff673286a07580b398ee8ce0890ac1f.png)
-   ![\det(\alpha A) = \alpha^n \det(A)](./images/5e3db729d582e7a5cf743a03e3ca17e99df7b692.png), for an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)
-   ![\textrm{det}\!\left( A \right) =  \prod_{i=1}^{n} \lambda_i](./images/051ab4a08ad5831b53aec4d68f296e6e5a8b5ac5.png), where ![\{\lambda_i\} = \textrm{eig}(A)](./images/77829d9522085d25e2ce4b1a538342e910229674.png) are the eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

###[The effects of row operations on determinants](./Front matter.md)

Recall the three row operations we used for the Gauss–Jordan elimination procedure:

-   Add a multiple of one row to another row
-   Swap two rows
-   Multiply a row by a constant

We’ll now describe the effects of these row operations on the value of the matrix determinant. In each case, we’ll connect the effects of the row operation to the geometric interpretation of the determinant operation.

####[Add a multiple of one row to another row](./Front matter.md)

Adding a multiple of one row of a matrix to another row does not change the determinant of the matrix.

![determinant_properties_r1eqr1plsalphar2](./images/determinant_properties_r1eqr1plsalphar2.png)

Figure 3.10: Row operations of the form ![\mathcal{R}_\alpha: R_i \gets R_i + \alpha R_j](./images/5cade1dd79cb949c79f895b6082769ef49812f2f.png) do not change the value of the matrix determinant.

This property follows from the fact that parallelepipeds with equal base enclosed between two parallel planes have the same volume even if they have different slants. This is called _Cavalieri’s principle_.

It is easier to visualize Cavalieri’s principle in two dimensions by considering two parallelograms with base ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) and different slants, enclosed between two parallel lines. The area of both parallelograms is the same: ![A = b \times h](./images/d0032828eb523fb68ba8c2c13f5974e217ed23b5.png), where ![h](./images/f1ca3cd6c70e90cc02066e90b194d6633838fd36.png) is the distance between the parallel lines.

####[Swapping rows](./Front matter.md)

Swapping two rows of a matrix changes the sign of its determinant.

![determinant_properties_swap_two_rows](./images/determinant_properties_swap_two_rows.png)

Figure 3.11: Swapping any two rows, ![\mathcal{R}_\beta: R_i \leftrightarrow R_j](./images/6c07d92105f443add4527572ac4e965e9fd242c2.png), flips the sign of the determinant.

This property is a consequence of measuring _signed volumes_. Swapping two rows changes the relative orientation of the vectors, and hence changes the sign of the volume from positive to negative or vice versa.

####[Multiply a row by a constant](./Front matter.md)

Multiplying a row by a constant is equivalent to multiplying the determinant by the constant.

![determinant_properties_multbyconstant](./images/determinant_properties_multbyconstant.png)

Figure 3.12: Row operations of the form ![\mathcal{R}_\gamma: R_i \gets \alpha R_i](./images/bd9a51627106c0c92633da27774879c820e3d084.png) scale the value of the determinant by the factor ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png).

This property follows from the fact that making one side of the parallelepiped ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) times longer increases the volume of the parallelepiped by a factor of ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png).

When each entry of an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix is multiplied by the constant ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png), each of the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) rows is multiplied by ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png), and so the determinant changes by a factor of ![\alpha^n](./images/b8307c2e9f2f2d0c3eefa2eb00725337a0f9f257.png): ![\det(\alpha A) = \alpha^n \det(A)](./images/5e3db729d582e7a5cf743a03e3ca17e99df7b692.png).

####[Zero-vs-nonzero determinant property](./Front matter.md)

There is an important distinction between matrices with zero determinant and matrices with nonzero determinant. We can understand this distinction geometrically by considering the ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) determinant calculation. Recall, the volume of the parallelepiped with sides ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png), ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) is equal to the determinant of the matrix containing the vectors ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png), ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png), and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) as rows. If the determinant is zero, it means at least one of the rows of the matrix is a linear combination of the other rows. The volume associated with this determinant is zero because the geometric shape it corresponds to is a flattened, two-dimensional parallelepiped; in other words, a parallelogram. We say the matrix is “deficient” if its determinant is zero.

On the other hand, if the determinant of a matrix is nonzero, the rows of the matrix are linearly independent. In this case, the determinant calculation corresponds to the volume of a real parallelepiped. We say the matrix is “full” if its determinant is nonzero.

The zero-vs-nonzero determinant property of a matrix does not change when we perform row operations on the matrix. If a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has a nonzero determinant, we know its reduced row echelon form will also have nonzero determinant. The number of nonzero rows in the reduced row echelon form of the matrix is called the _rank_ of the matrix. We say a matrix ![A \in \mathbb{R}^{n \times n}](./images/2f056442410016d3a541715471950849562de0c4.png) has _full rank_ if its RREF contains ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) pivots. If the RREF of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) contains a row of zeros, then ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is not full rank and ![\det(A)=0](./images/4c192db42d3bd89cf462441ca977988e7069d97b.png). On the other hand, if ![\det(A)\neq 0](./images/69633a1b936d0299a2d93cf1e2aada740f28d697.png), we know that ![\textrm{rref}(A)=\mathbbm{1}](./images/a49e791f88aa14cccd0118a99f8dcdb1fcb16e28.png).

###[Applications](./Front matter.md)

Apart from the geometric and invertibility-testing applications of determinants described above, determinants are related to many other topics in linear algebra. We’ll briefly cover some of these in this section.

####[Cross product as a determinant](./Front matter.md)

We can compute the cross product of the vectors ![\vec{v} = (v_1, v_2, v_3)](./images/b5dec8d3fc9b621a78642f27092aa0374f269070.png) and ![\vec{w} = (w_1, w_2,w_3)](./images/ff091c9be1a83544f5b1c892e6a88f6222dddafe.png) by computing the determinant of a special matrix. We place the symbols ![\hat{\imath}](./images/4ba8062d7b57b600758e66cbfcfaefdfb3b80293.png), ![\hat{\jmath}](./images/7246aa5987e2db7d54b98378fc615d1f3b06e985.png), and ![\hat{k}](./images/1427cff1bf4c402fb2a07d3b871082761b7c2102.png) in the first row of the matrix then write the components of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) in the second and third rows. After expanding the determinant along the first row, we obtain the cross product:

![\begin{align*}
\vec{v}\times\vec{w} 
& =
\left|\begin{array}{ccc}
\hat{\imath} & \hat{\jmath} & \hat{k} \\
v_1 & v_2 & v_3 \\
w_1 & w_2 & w_3
\end{array}\right|  					\\
& =
\hat{\imath}
\left|\begin{array}{cc}
v_{2}  & v_{3} \\
w_{2} &  w_{3}
\end{array}\right|
\; -
\hat{\jmath}
\left|\begin{array}{cc}
v_{1} & v_{3} \\
w_{1} & w_{3}
\end{array}\right|
\; +
\hat{k}
\left|\begin{array}{cc}
v_{1} & v_{2} \\
w_{1} & w_{2}
\end{array}\right| 					\\
&= (v_2w_3-v_3w_2)\hat{\imath}   
-(v_1w_3 - v_3w_1)\hat{\jmath} 
+(v_1w_2-v_2w_1)\hat{k} 				\\
& = (v_2w_3-v_3w_2,\; v_3w_1 - v_1w_3,\; v_1w_2-v_2w_1).
\end{align*}](./images/2a8e16ef51a6614acd107f696a73f3b94794e5e5.png)

Observe that the anticommutative property of the vector cross product, ![\vec{v}\times\vec{w} = - \vec{w}\times\vec{v}](./images/d58a458c8117cdbd6e5b3ad281b14288a93490f1.png), corresponds to the swapping-rows-changes-the-sign property of determinants.

The extended array trick for computing ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) determinants (see[Figure 3.7](./Chapter 3_ Computational linear algebra.md)) doubles as a trick for computing cross products:

![cross_product_computational_trick-0](./images/cross_product_computational_trick-0.png)

Figure 3.13: We can quickly compute the cross product of two vectors using the extended array trick.

Using the correspondence between the cross product and the determinant, we can write the determinant of a ![3\times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix in terms of the dot product and cross product:

![\left|\begin{array}{ccc}
u_1 & u_2 & u_3 \\
v_1 & v_2 & v_3 \\
w_1 & w_2 & w_3 \\
\end{array}\right|
=
\vec{u}\cdot(\vec{v}\times\vec{w}).](./images/0e888187b68b1f83e4314446cf06517458daea4c.png)

####[Cramer’s rule](./Front matter.md)

Cramer’s rule is an approach for solving systems of linear equations using determinants. Consider the following system of equations and its representation as a matrix equation:

![\begin{align*}
a_{11}x_1 + a_{12}x_2 + a_{13}x_3 	& \; = \;  b_1 \\
a_{21}x_1 + a_{22}x_2 + a_{23}x_3 	& \; = \;  b_2 	\quad \qquad \Leftrightarrow \quad \qquad A\vec{x} = \vec{b}. \\
a_{31}x_1 + a_{32}x_2 + a_{33}x_3 	& \; = \;  b_3
\end{align*}](./images/2ac08d2ec5f6df2a493c56974c4353988bc7304b.png)

We’re looking for the vector ![\vec{x}=(x_1,x_2,x_3)](./images/1e7a3130b9d50c14192a7dba0d40d9f77bde56ee.png) that satisfies this system of equations.

Begin by writing the system of equations as an augmented matrix:

![\left[\begin{array}{ccc|c}
a_{11} & a_{12} & a_{13} \; \; &  \; b_1 \\
a_{21} & a_{22} & a_{23} \; \; &  \; b_2 \\
a_{31} & a_{32} & a_{33} \; \; &  \; b_3
\end{array}\right]
\; = \; 
\left[\begin{array}{ccc|c}
\vert & \vert & \vert  \; \; & \; \vert \\
\vec{a}_1 \; & \vec{a}_2 \; & \vec{a}_3 \; \;  & \; \vec{b} \\
\vert & \vert & \vert \; \; & \; \vert 
\end{array}\right].](../Images/9d8178aae3fcd00a95303a1439b15577544c7800.png)

We use the notation ![\vec{a}_j](./images/55da5b8cbd4e2fb359dfdcf8e5913a332e78fda9.png) to denote the ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th column of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), and ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png) to denote the column of constants.

Cramer’s rule requires computing ratios of determinants. To find ![x_1](./images/1ed4d16d182d3ec24604e05240bb4a63f49e29b9.png), the first component of the solution vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png), we compute the following ratio of determinants:

![x_1=
\frac{
\left|\begin{array}{ccc}
\vert & \vert & \vert \\
\vec{b} & \vec{a}_2 & \vec{a}_3  \\
\vert & \vert & \vert 
\end{array}\right|
}{
\left|\begin{array}{ccc}
\vert & \vert & \vert \\
\vec{a}_1 & \vec{a}_2 & \vec{a}_3  \\
\vert & \vert & \vert 
\end{array}\right|
} 
= 
\frac{ 
\left|\begin{array}{ccc}
b_1 & a_{12} & a_{13}  \\
b_2 & a_{22} & a_{23}  \\
b_3 & a_{32} & a_{33}
\end{array}\right|
}{
\left|\begin{array}{ccc}
a_{11} & a_{12} & a_{13}  \\
a_{21} & a_{22} & a_{23}  \\
a_{31} & a_{32} & a_{33}
\end{array}\right|
}\;.](./images/9f58b8791e320df537c3f0c240bee144ca95a5e8.png)

Basically, we replace the column that corresponds to the unknown we want to solve for (in this case the first column) with the vector of constants ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png), and compute the determinant before dividing by ![\textrm{det}(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png). To find ![x_2](./images/96a98def8f51117b329e4cc7e2ac4c1a9f55e4ae.png), we’ll need to compute the determinant of a matrix where ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png) replaces the second column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Similarly, to find ![x_3](./images/db23e43963a7727df3e8966c1e818afe37b229d7.png), we replace the third column with ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png).

Cramer’s rule is a neat computational trick that might come in handy if you ever want to solve for one particular component of the unknown vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png), without solving for the other components.

####[Linear independence test](./Front matter.md)

Suppose you’re given a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png), ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vectors ![\{ \vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n \}](./images/abdaeb0dbcba5c098940107f852a5b9fc0c2de80.png) and asked to check whether the vectors are linearly independent.

You could use the Gauss–Jordan elimination procedure to accomplish this task. Write the vectors ![\vec{v}_i](./images/11553a8d864ca512231bf7ef8cb860c8ad8271ac.png) as the rows of a matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). Next, use row operations to find the reduced row echelon form (RREF) of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). Row operations do not change the linear independence between the rows of a matrix, so you can tell whether the rows are independent from the reduced row echelon form of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png).

Alternatively, you can use the _determinant test_ as a shortcut to check whether the vectors are linearly independent. If ![\det(M)](./images/92cd684e2dc045de6fdcbd142bd391ab3924c3d4.png) is zero, the vectors that form the rows of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) are not linearly independent. On the other hand, if ![\det(M)\neq 0](./images/0782b71849b0e8c637032f3a659ee661591e3797.png), then the rows of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) are linearly independent.

####[Eigenvalues](./Front matter.md)

The determinant operation is used to define the _characteristic polynomial_ of a matrix. The characteristic polynomial of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is denoted ![p_A(\lambda)](./images/4bc02a515f32b8569dffa981fc40e6800c99ee51.png), and is defined as the determinant of the expression ![(A-\lambda\mathbbm{1})](./images/fb1c5c0f10461cd049357a5fec23697aee17b493.png):

![\begin{align*}
p_A(\lambda) 
& \eqdef \det( A - \lambda\mathbbm{1} ) \\
& = 
\begin{vmatrix}
a_{11}-\lambda & a_{12} \\
a_{21} & a_{22}-\lambda  
\end{vmatrix}  \\
& =    (a_{11}-\lambda)(a_{22}-\lambda) - a_{12}a_{21} \\
& = \lambda^2 - \underbrace{(a_{11}+a_{22})}_{\textrm{Tr}(A)}\lambda  +  \underbrace{(a_{11}a_{22} - a_{12}a_{21})}_{\det(A)}.
\end{align*}](./images/844d042d37f6a8daf8b33427ee7d649cd1d3b4d4.png)

The variable ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png) (the Greek letter _lambda_) is customarily used in this definition. The roots of the characteristic polynomial are the _eigenvalues_ of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Observe the coefficient of the linear term in ![p_A(\lambda)](./images/4bc02a515f32b8569dffa981fc40e6800c99ee51.png) is equal to ![-\textrm{Tr}(A)](./images/fb78adda836c3753e0a65eac07a10722d200b22f.png) and the constant term equals ![\det(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png). The name _characteristic polynomial_ is indeed appropriate since ![p_A(\lambda)](./images/4bc02a515f32b8569dffa981fc40e6800c99ee51.png) encodes the information about three important properties of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png): its eigenvalues ![(\lambda_1,\lambda_2)](./images/beb6950ee131f6ab859305d001d0312f09b99a4e.png), its trace ![\textrm{Tr}(A)](./images/5cac703e5885c95d0781a32376aa9d456b4dbeb2.png), and its determinant ![\det(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png).

We’ll continue to discuss characteristic polynomials and eigenvalues in[Section 6.1](./Chapter 6_ Theoretical linear algebra.md).

###[Exercises](./Front matter.md)

E3.7 Find the determinants of the following matrices.

1.  ![\begin{bmatrix}
    1&2\\ 
    3&4			
    \end{bmatrix}](./images/dff55c55c70ca6cc3146fa1cf038c38272c102c3.png)
2.  ![\begin{bmatrix}
    3&4\\ 
    1&2 				
    \end{bmatrix}](./images/388ed7956b229b44403c7d2a166c32b16b4a5e02.png)
3.  ![\begin{bmatrix}
    1 	& 1 	& 1	\\
    1 	& 2 	& 3	\\
    1	& 2	& 7					
    \end{bmatrix}](./images/3c10f960f387573890fcccbe23a944b5663a0ad4.png)
4.  ![\begin{bmatrix}
    1 	& 2 	& 3	\\
    0 	& 0 	& 0	\\
    1	& 3	& 4					
    \end{bmatrix}](./images/3ee3e8a2da258810e5532fde0b9046e334e4fc61.png)

E3.8 Find the volume of the parallelepiped whose sides are the vectors ![\vec{u}=(1, 2, 3)](./images/ab56c7987603c79fb83187ed7e9fa5c347d5b44c.png), ![\vec{v}= (2,-2,4)](./images/32c84ab8ad45954f585f9609acdc8cf1064e32e1.png), and ![\vec{w}=(2,2,5)](./images/26fb06f0881c4710ba8597ea0616923615931759.png).

E3.9 Determine whether the set of vectors ![\{ (1,4,3),\;  (2,1,1),\; (0,-2,-1)\}](./images/455a37a5ef146a94935dc453d7cb141e8aacd2b9.png) is linearly dependent or linearly independent.

###[Links](./Front matter.md)

\[ More information about determinants from Wikipedia \]

[`http://en.wikipedia.org/wiki/Determinant`](./Determinant.md)

[`http://en.wikipedia.org/wiki/Minor_(linear_algebra)`](./Minor_(linear_algebra.md))

\[ The determinant explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=Ip3X9LOh2dk`](./watch_v=Ip3X9LOh2dk.md)

##[3.5 Matrix inverse](./Chapter 3_ Computational linear algebra.md)

In this section, we’ll learn four different approaches for computing the inverse of a matrix. Since knowing how to compute matrix inverses is a pretty useful skill, learning several approaches is hardly overkill. Note that the matrix inverse is _unique_, so no matter which method you use to find the inverse, you’ll always obtain the same answer. You can verify your calculations by computing the inverse in different ways and checking that the answers agree.

###[Existence of an inverse](./Front matter.md)

Not all matrices are invertible. Given a matrix ![A \in \mathbb{R}^{n \times n }](./images/2f056442410016d3a541715471950849562de0c4.png), we can check whether it is invertible by computing its determinant:

![A^{-1} \; \textrm{exists} 
\qquad \textrm{if and only if} \qquad 
\textrm{det}(A) \neq 0.](./images/c14fe635a98c3ebd9a24222312edb642a15d855a.png)

Calculating the determinant of a matrix serves as an _invertibility test_. The exact value of the determinant is not important; it could be big or small, positive or negative; as long as the determinant is nonzero, the matrix passes the invertibility test.

###[Adjugate matrix approach](./Front matter.md)

The inverse of a ![2\times2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix can be computed as follows:

![\begin{bmatrix}
a&b\\ 
c&d
\end{bmatrix}^{-1}
=
\frac{1}{ad-bc}
\begin{bmatrix}
\; d&-b\\ 
-c& \; a
\end{bmatrix}\!.](./images/15797cabe14aea37ef0b73c2e4a6852b4fa3158d.png)

The above formula is the ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) version of a general formula for obtaining the inverse based on the _adjugate matrix_:

![A^{-1} = \frac{1}{ \textrm{det}(A) } \textrm{adj}(A).](./images/982f69ac82ab20ab57ff7f22de5d2a9262e1b458.png)

What is the adjugate matrix, you ask? The adjugate matrix is kind of complicated, so let’s proceed step by step. We’ll first define a few prerequisite concepts.

In this section, we’ll work on a matrix ![A \in \mathbb{R}^{3 \times 3}](./images/56a95b574a11fbe3404951e06d60f40095de817b.png) and refer to its entries as ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png), where ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) is the row index and ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) is the column index:

![A =
\begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{bmatrix}\!.](./images/65fcc85be14de31257cb53dcb3c81694b36cbb7d.png)

First we’ll define three concepts associated with determinants:

1.  For each entry ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png), the _minor_ ![M_{ij}](./images/443e3b60ab8c4d4c944621decdf87e8d95310edd.png) is the determinant of the matrix that remains after we remove the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th row and the ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). For example, the minor that corresponds to the entry ![a_{12}](./images/6a900889a0b7e32191a6331ff9b241d3cb748f17.png) is given by:
    
    ![M_{12}
    =
    \begin{vmatrix}
    \times  & \color{blue}{\times}  & \times \\
    a_{21} & \times & a_{23} \\
    a_{31} & \times & a_{33}
    \end{vmatrix}
    = \left| \begin{matrix} a_{21} & a_{23} \\ a_{31} & a_{33}  \end{matrix} \right|
    = a_{21}a_{33} - a_{23}a_{31}.](./images/2ecb78fc0d9b5768c859d3c63729564df9c6f6a6.png)
    
2.  The _sign_ of each entry ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png) is defined as ![\textrm{sign}(a_{ij}) \eqdef (-1)^{i+j}](./images/a87032cac8febdbd443ef828b4fd0a11aa8e1018.png). For example, the signs of the different entries in a ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix are
    
    ![\begin{pmatrix}
    +	& 	-	&	+	\\
    -	&	+ 	&	-	\\
    +	&	-	&	+
    \end{pmatrix}.](./images/b508df71374a8bb9279a50f33354fe85d8c5af00.png)
    
3.  The _cofactor_ ![c_{ij}](./images/7ea84843068c73cace02ad6f2a02e61951a9026e.png) for the entry ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png) is the product of this entry’s sign and its minor:
    
    ![c_{ij}  \eqdef \textrm{sign}(a_{ij})M_{ij} = (-1)^{i+j}M_{ij}.](./images/3cd471f5902bc5407560d8dc899c4fa2d189ca53.png)
    

The above concepts should look somewhat familiar, since they previously appeared in the formula for computing determinants. If we expand the determinant along the first row of the matrix, we obtain the formula

![\textrm{det}(A) 
= \sum_{j=1}^n a_{1j} \textrm{sign}(a_{1j}) M_{1j}
= \sum_{j=1}^n a_{1j} c_{1j}.](./images/32f027b76eb4aa29cfd96941865821c89eb69cf9.png)

Here we can see where the name _cofactor_ comes from: the cofactor ![c_{ij}](./images/7ea84843068c73cace02ad6f2a02e61951a9026e.png) is what multiplies the _factor_ ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png) in the determinant formula.

Okay, now we’re ready to describe the adjugate matrix. The adjugate matrix is defined as the transpose of the _matrix of cofactors_ ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png). The matrix of cofactors is a matrix of the same dimensions as the original matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) that is constructed by replacing each entry ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png) by its cofactor ![c_{ij}](./images/7ea84843068c73cace02ad6f2a02e61951a9026e.png). The matrix of cofactors for ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is

![C = 
\begin{bmatrix}
c_{11} & c_{12} & c_{13} \\
c_{21} & c_{22} & c_{23} \\
c_{31} & c_{32} & c_{33}
\end{bmatrix}
=
\begin{bmatrix} 
+\left| \begin{matrix} a_{22} & a_{23} \\  a_{32} & a_{33} \end{matrix} \right| &
-\left| \begin{matrix} a_{21} & a_{23} \\  a_{31} & a_{33}  \end{matrix} \right| &
+\left| \begin{matrix} a_{21} & a_{22} \\  a_{31} & a_{32} \end{matrix} \right| \\ 
& & \\ 
-\left| \begin{matrix} a_{12} & a_{13} \\  a_{32} & a_{33} \end{matrix} \right| &
+\left| \begin{matrix} a_{11} & a_{13} \\  a_{31} & a_{33} \end{matrix} \right| &
-\left| \begin{matrix} a_{11} & a_{12} \\  a_{31} & a_{32} \end{matrix} \right| \\ 
& & \\ 
+\left| \begin{matrix} a_{12} & a_{13} \\  a_{22} & a_{23} \end{matrix} \right| &
-\left| \begin{matrix} a_{11} & a_{13} \\  a_{21} & a_{23} \end{matrix} \right| &
+\left| \begin{matrix} a_{11} & a_{12} \\  a_{21} & a_{22} \end{matrix} \right|
\end{bmatrix}\!\!.](./images/8283c342b58ac9e9cdd7f0704ea718961d58cd69.png)

The adjugate matrix ![\textrm{adj}(A)](./images/b5ba597b443e849b8a4e8c8f28702579f95df26d.png) is the transpose of the matrix of cofactors: page-adjA\_definitions

![\textrm{adj}(A)  \eqdef C^\sfT.](./images/17e719770158e5c08e0cc05c6305ea38eeceb943.png)

The formula for the inverse matrix is ![A^{-1} = \frac{1}{ \textrm{det}(A) } \textrm{adj}(A)](./images/ee106f014cb26e147dc01e4ea20ad8c81b90077f.png). In the ![3\times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) case, the matrix inverse formula is

![A^{-1}
=
\frac{1}{
\left|\begin{matrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{matrix}
\right|}
\begin{bmatrix} 
+\left| \begin{matrix} a_{22} & a_{23} \\  a_{32} & a_{33} \end{matrix} \right| &
-\left| \begin{matrix} a_{12} & a_{13} \\  a_{32} & a_{33}  \end{matrix} \right| &
+\left| \begin{matrix} a_{12} & a_{13} \\  a_{22} & a_{23} \end{matrix} \right| \\ 
& & \\ 
-\left| \begin{matrix} a_{21} & a_{23} \\  a_{31} & a_{33} \end{matrix} \right| &
+\left| \begin{matrix} a_{11} & a_{13} \\  a_{31} & a_{33} \end{matrix} \right| &
-\left| \begin{matrix} a_{11} & a_{13} \\  a_{21} & a_{23}  \end{matrix} \right| \\ 
& & \\ 
+\left| \begin{matrix} a_{21} & a_{22} \\  a_{31} & a_{32} \end{matrix} \right| &
-\left| \begin{matrix} a_{11} & a_{12} \\  a_{31} & a_{32} \end{matrix} \right| &
+\left| \begin{matrix} a_{11} & a_{12} \\  a_{21} & a_{22} \end{matrix} \right|
\end{bmatrix}\!\!.](./images/cb715edaf9e293a8d9545997141f888c830dfdeb.png)

I know this looks complicated, but I wanted you to know about the adjugate matrix approach for computing the inverse. In practice, you’ll rarely have to compute inverses using this approach; nevertheless, the adjugate matrix formula represents an important theoretical concept. Note the formula fails if ![\textrm{det}(A)=0](./images/4c192db42d3bd89cf462441ca977988e7069d97b.png), due to a divide-by-zero error.

###[Using row operations](./Front matter.md)

Another way to obtain the inverse of a matrix is to record all the _row operations_ ![\mathcal{R}_1,\mathcal{R}_2,\ldots](./images/d5a2874f8699726c4f91710d86dd3a3599f22637.png) needed to transform ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) into the identity matrix:

![\mathcal{R}_k(\ldots \mathcal{R}_2( \mathcal{R}_1( A ) )\ldots) 
= \mathbbm{1}.](./images/c180a6b5e2ce34d10e0b52a8327a12b68eaef142.png)

Recall that we can think of the action of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as a vector transformation, ![\vec{w}=A\vec{v}](./images/ac490d0583ac5681d84038eddce044b27e731392.png). By definition, the inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) is the operation that undoes the effect of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png): ![A^{-1}\vec{w} = \vec{v}](./images/f68dca1f4fee882df97042dee505edc8b163838b.png). The combination of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) followed by ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) is the identity transformation, ![A^{-1}A\vec{v}=\mathbbm{1}\vec{v} = \vec{v}](./images/f8de462de98b68e41c0dd109eb81b363d50dbb0d.png).

The cumulative effect of the row operations required to transform ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) to the identity matrix is equivalent to the “undo” action of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Applying the sequence of row operations ![\mathcal{R}_1, \mathcal{R}_2, \ldots, \mathcal{R}_k](./images/5090f932d13d1a13a32ba8b3ed3b0730909f86d3.png) has the same effect as multiplying by ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png):

![A^{-1}\vec{w}
\; = \; 
\mathcal{R}_k(\ldots \mathcal{R}_2( \mathcal{R}_1( \vec{w} ) )\ldots).](./images/db271166147b73661ba1ef0134f79d9546a716e4.png)

If you think this method of finding the inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) seems more complicated than useful, you’re right—if it weren’t for the existence of a neat procedure for recording the row operations ![\mathcal{R}_1](./images/4c4c707337b2729d8ba24da3015cbe93a3f35001.png), ![\mathcal{R}_2](./images/03cd03c8cafdd141d645b2723d2f810248628ab2.png),![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png),![\mathcal{R}_k](./images/6dbf2e1d14bebd25ef96cd89010b6b35b1565a10.png) that makes everything simpler. We’ll discuss this procedure next.

Begin by initializing an ![n \times 2n](./images/967b96d26bc4156bfd511d0857164490b2d24fcc.png) array with the entries of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) on the left side and the identity matrix on the right side: ![[\;A\; | \; \mathbbm{1}\:\; ]](../Images/4f6834d8f136f7578b884eca2edded481eea1b8d.png). If we perform the Gauss–Jordan elimination procedure on this array, we’ll end up with the inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) in the right side of the array:

![[\;A\; | \; \mathbbm{1}\:\;  ] 
\; 
\xrightarrow{  \; \textrm{Gauss--Jordan elimination} \; }
\; 
[ \; \:\mathbbm{1}\;  | \; A^{-1} \;].](../Images/1b8d2d8132e1302da3a5259fd293a54e2953d272.png)

#####[Example](./Front matter.md)

Let’s illustrate the procedure by computing the inverse of the following matrix:

![A = 
\begin{bmatrix}
1 & 2 \\
3 & 9 
\end{bmatrix}.](./images/6a2e7f59308ac08d4697806ff134fb65b95859cf.png)

We start by writing the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) next to the identity matrix ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png):

![\qquad 
\left[ 
\begin{array}{cc|cc}
1 & 2  \; \; & \; \;  1 & 0  \\
3 & 9  \; \; & \; \;  0 & 1  
\end{array} \right]\!.](../Images/afcf046d9190915b770df2d621dfafbd3a7c7088.png)

Next, we perform the Gauss–Jordan elimination procedure on the resulting ![2 \times 4](./images/5b3afde6284d094412117437aa0250ab2d440496.png) array:

1.  Subtract three times the first row from the second row, written compactly as ![\mathcal{R}_1: R_2 \gets R_2 -3R_1](./images/c286be6a1c422618ed06b1938e9d05d6a3f39099.png), to obtain
    
    ![\left[ 
    \begin{array}{cc|cc}
    1 & 2  \; \; & \; \;  1  & 0  \\
    0 & 3  \; \; & \; \;  -3 & 1  
    \end{array} \right]\!.](../Images/d80b90ee4e98a207db248d8a2b52a0c2491cd885.png)
    
2.  Perform another row operation ![\mathcal{R}_2: R_2 \gets \frac{1}{3}R_2](./images/dd401edd0780c1d3afd3d3df138a642486dfdb7e.png) to obtain a leading one in the second column:
    
    ![\left[ 
    \begin{array}{cc|cc}
    1 & 2  \; \; & \; \;  1  & 0  \\
    0 & 1  \; \; & \; \;  -1 & \frac{1}{3}  
    \end{array} \right]\!.](../Images/107429088b6e129f224947d57c9191dc5969821b.png)
    
3.  Finally, perform ![\mathcal{R}_3:  R_1 \gets R_1 - 2R_2](./images/b02a701406afd93ac0d37c5ae27ce357bcae51e1.png) to clear the entry above the leading one in the second column:
    
    ![\; \; 
    \left[ 
    \begin{array}{cc|cc}
    1 & 0  \; \; & \; \;  3  & -\frac{2}{3}  \\
    0 & 1  \; \; & \; \;  -1 & \frac{1}{3}  
    \end{array} \right]\!.](../Images/8ce3977e641bf3cc8fda227fee77ee9205b6dacd.png)
    

The inverse of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) now appears in the right side of the above array,

![\qquad \qquad
A^{-1} = 
\begin{bmatrix}
3  & -\frac{2}{3}  \\
-1 & \frac{1}{3}  
\end{bmatrix}\!.](./images/2cbbb84e2466949e3e92f70cca56656c185f5854.png)

This algorithm works because we identify the sequence of row operations ![\mathcal{R}_3(\mathcal{R}_2( \mathcal{R}_1( \; . \; ) ))](./images/e2c69dd3f37ab77f270a49df264f14436d93ea79.png) with the action of the inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png):

![\mathcal{R}_3(\mathcal{R}_2( \mathcal{R}_1( A ) )) = \mathbbm{1}
\qquad \Rightarrow \qquad
\mathcal{R}_3(\mathcal{R}_2( \mathcal{R}_1( \mathbbm{1} ) ))  = A^{-1}.](./images/c75ace7bddbe2d2e08e4d812007b64bbc204224f.png)

The combined effect of the three row operations is to “undo” the action of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png); therefore this sequence of row operations has the same effect as the inverse operation ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png). The right side of the ![2 \times 4](./images/5b3afde6284d094412117437aa0250ab2d440496.png) array serves as a record of the cumulative effect of this sequence of row operations performed. Because the right side starts from the identity matrix, it will contain ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) by the end of the procedure.

###[Using elementary matrices](./Front matter.md)

Every row operation ![\mathcal{R}](./images/292f5e6542a43a174b008b49eaff3627381bc3d0.png) performed on a matrix is equivalent to an operation of left multiplication by an _elementary matrix_ ![E_{\mathcal{R}}](./images/1dcf3505688a7912c896e9126ae744b2aef2a194.png):

![A' = \mathcal{R}(A) 
\qquad
\Leftrightarrow
\qquad 
A' = E_{\mathcal{R}}A.](./images/8ee7fda527f314d57746d55cddadab1058ff3c8d.png)

There are three types of elementary matrices that correspond to the three types of row operations. We’ll illustrate the three types of elementary matrices with examples from the ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) case:

-   Adding ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) times the second row to the first row corresponds to
    
    ![\begin{align*}
    \mathcal{R}_\alpha:R_1 \gets R_1 +m R_2  
    & \qquad \Leftrightarrow \qquad 
    E_\alpha = 
    \begin{bmatrix}
    1 & m \\
    0 & 1 
    \end{bmatrix}\!.
    \end{align*}](./images/30abc780824bdbaf7026095f8ff43f61085dc3f2.png)
    
-   Swapping the first and second rows corresponds to
    
    ![\begin{align*}
    \qquad \; \; 
    \mathcal{R}_\beta:R_1 \leftrightarrow R_2	
    & \qquad  \Leftrightarrow \qquad 
    E_\beta = 
    \begin{bmatrix}
    0 & 1 \\
    1 & 0 
    \end{bmatrix}\!.
    \end{align*}](./images/0131c68f6d8fb20de809f900c294b59392c35f4e.png)
    
-   Multiplying the first row by the constant ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png) corresponds to
    
    ![\begin{align*}			
    \qquad \:
    \mathcal{R}_\gamma:R_1 \gets k R_1
    & \qquad  \Leftrightarrow \qquad 
    E_\gamma = 
    \begin{bmatrix}
    k & 0 \\
    0 & 1 
    \end{bmatrix}\!.
    \end{align*}](./images/f8c697f1d86d39b8d86aa1109853989782a82579.png)
    

The general rule is simple: to find the elementary matrix that corresponds to a given row operation, apply that row operation to the identity matrix ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png).

Recall the procedure we used to find the inverse in the previous section. We applied the sequence of row operations ![\mathcal{R}_1,\mathcal{R}_2,\ldots](./images/d5a2874f8699726c4f91710d86dd3a3599f22637.png) to transform the array ![[\;A\; | \; \mathbbm{1}\:\;  ]](../Images/4f6834d8f136f7578b884eca2edded481eea1b8d.png) into the reduced row echelon form:

![\mathcal{R}_k(\ldots  \mathcal{R}_2( \mathcal{R}_1( [\;A\; | \; \mathbbm{1}\:\;  ] ) )\ldots)
\; \; =  \; \; [ \; \:\mathbbm{1}\;  | \; A^{-1} \;].](../Images/980b3694cb286b6a763a9d2b2ae68b6e12960936.png)

If we represent each row operation as a multiplication by an elementary matrix, we obtain the equation

![\qquad \quad \; \; 
E_{k}\cdots E_{2}E_{1} [\;A\; | \; \mathbbm{1}\:\;  ] 
\; \; =  \; \; [ \; \:\mathbbm{1}\;  | \; A^{-1} \;].](../Images/f99857016ba80b22cd68b8fe466402da76f71f6f.png)

Observe that ![E_{k}\cdots E_{2}E_{1}A = \mathbbm{1}](./images/5bec1a20dca38120bd26219de62a09a17bc563f6.png), so we’ve obtained an expression for the inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) as a product of elementary matrices:

![A^{-1}	 = 	E_{k}\cdots E_{2}E_{1}.](./images/f5297808132f52912ccbd6bd6f4ba66504bad90b.png)

We’ll now illustrate how the formula ![A^{-1}=E_{k}\cdots E_{2}E_{1}](./images/9e0b34fe241fd87c2cfa6db93f75ddb06be6e908.png) applies in the case of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) discussed above

![A = 
\begin{bmatrix}
1 & 2 \\
3 & 9 
\end{bmatrix}\!.](./images/fac116ae88e8580afd8cc454c1b5b9a79cfc565f.png)

Recall the row operations we applied in order to transform ![[\;A\; | \; \mathbbm{1}\:\;  ]](../Images/4f6834d8f136f7578b884eca2edded481eea1b8d.png) into ![[ \; \:\mathbbm{1}\;  | \; A^{-1} \;]](../Images/af44c284ed275a175ca2dba299c72990584a9529.png):

1.  ![\mathcal{R}_1](./images/4c4c707337b2729d8ba24da3015cbe93a3f35001.png): ![R_2 \gets R_2 -3R_1](./images/fb500f7ee9892774999183ff5cc78dff5362cfac.png)
2.  ![\mathcal{R}_2](./images/03cd03c8cafdd141d645b2723d2f810248628ab2.png): ![R_2 \gets \frac{1}{3}R_2](./images/a4bc8b81a525d2f8e6de557459c7f63acac6314a.png)
3.  ![\mathcal{R}_3](./images/87748d3569599ba129b8b2e06436d1382e5bbaac.png): ![R_1 \gets R_1 - 2R_2](./images/c9fe4f74671bcc370ee5e99a29db8b0e89f9af6c.png)

Let’s revisit these row operations, representing each of them as a multiplication by an elementary matrix:

1.  The first row operation, ![\mathcal{R}_1: R_2 \gets R_2 -3R_1](./images/c286be6a1c422618ed06b1938e9d05d6a3f39099.png), corresponds to a multiplication by the elementary matrix ![E_1](./images/dba171c31bb7a8963f510873c5949f261638d4bf.png):
    
    ![E_1 =
    \begin{bmatrix}
    1 & 0 \\
    -3 & 1 
    \end{bmatrix}\!,
    \qquad 			    
    E_1 A = 
    \begin{bmatrix}
    1 & 0 \\
    -3 & 1 
    \end{bmatrix}\!
    \begin{bmatrix}
    1 & 2 \\
    3 & 9 
    \end{bmatrix}
    = 
    \begin{bmatrix}
    1 & 2 \\
    0 & 3 
    \end{bmatrix}\!. \; \;](./images/22b3c56f9f086eea5ef845256a23eb93559fe666.png)
    
2.  The second row operation, ![\mathcal{R}_2: R_2 \gets \frac{1}{3}R_2](./images/dd401edd0780c1d3afd3d3df138a642486dfdb7e.png), corresponds to a matrix ![E_2](./images/ed27b3364f410f54c28b7089bcaf3dc9e6031444.png):
    
    ![E_2 = 
    \begin{bmatrix}
    1 & 0 \\
    0 & \frac{1}{3} 
    \end{bmatrix}\!,			    
    \qquad 
    E_2 (E_1 A) = 
    \begin{bmatrix}
    1 & 0 \\
    0 & \frac{1}{3} 
    \end{bmatrix}\!
    \begin{bmatrix}
    1 & 2 \\
    0 & 3 
    \end{bmatrix}
    = 
    \begin{bmatrix}
    1 & 2  \\
    0 & 1  
    \end{bmatrix}\!.](./images/0c34d4b0d819bb5752fcb66f06f84e2aaeb04665.png)
    
3.  The third row operation, ![\mathcal{R}_3: R_1 \gets R_1 - 2R_2](./images/b02a701406afd93ac0d37c5ae27ce357bcae51e1.png), corresponds to the elementary matrix ![E_3](./images/890f91c0088914a3805efcbec29b668287384a53.png):
    
    ![\quad \; \; 
    E_3 = 
    \begin{bmatrix}
    1 & \!\!-2  \\
    0 & 1  
    \end{bmatrix}\!, 
    \quad 
    E_3(E_2E_1 A) = 
    \begin{bmatrix}
    1 & \!\!-2  \\
    0 & 1  
    \end{bmatrix}\!
    \begin{bmatrix}
    1 & 2  \\
    0 & 1  
    \end{bmatrix}
    =
    \begin{bmatrix}
    1 & 0  \\
    0 & 1  
    \end{bmatrix}\!. \; \;](./images/bfa19c58b3fd1dbbed00eea80555bdb41b60bc78.png)
    

Note that ![E_3E_2E_1A=\mathbbm{1}](./images/7c5e87c1a6cff41ac321e48fe2f752908e35d111.png), so the expression ![E_3E_2E_1](./images/686424e2afef44324b4fcdafec10b92075e773fb.png) must equal ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png):

![A^{-1}\!=E_3E_2E_1 =  \!
\begin{bmatrix}
1 & -2  \\
0 & 1  
\end{bmatrix}\!
\begin{bmatrix}
1 & \!0 \\
0 & \!\tfrac{1}{3} 
\end{bmatrix}\!
\begin{bmatrix}
1 & 0 \\
-3 & 1 
\end{bmatrix}
=
\begin{bmatrix}
3  & -\frac{2}{3}  \\
-1 & \frac{1}{3}  
\end{bmatrix}\!.](./images/f0b4e41aed283a2c1e575284c78ac54e363d1f14.png)

Verify the last equation by computing the product of the three elementary matrices.

Since we know ![A^{-1}\!=E_3E_2E_1](./images/c206c588c35b2e4ccaee291c7909b13c26ca6aae.png), then ![A=(A^{-1})^{-1}=(E_3E_2E_1)^{-1}=E_1^{-1}E_2^{-1}E_3^{-1}](./images/a46ffbbec4729a45961d16cba50d9b4d0cba6f80.png). We can write ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as a product of elementary matrices:

![A = E_1^{-1}E_2^{-1}E_3^{-1}
= 
\begin{bmatrix}
1 & 0 \\
3 & 1 
\end{bmatrix}\!
\begin{bmatrix}
1 & 0 \\
0 & 3
\end{bmatrix}\!
\begin{bmatrix}
1 & 2  \\
0 & 1  
\end{bmatrix}\!.](./images/c3a7216dfca95e1166ca468c9f97760329d9548b.png)

The inverses of the elementary matrices are easy to compute; they correspond to the elementary “undo” operations of ![E_1](./images/dba171c31bb7a8963f510873c5949f261638d4bf.png), ![E_2](./images/ed27b3364f410f54c28b7089bcaf3dc9e6031444.png), and ![E_3](./images/890f91c0088914a3805efcbec29b668287384a53.png). For example, ![E_1](./images/dba171c31bb7a8963f510873c5949f261638d4bf.png) performs the row operation ![R_2 \gets R_2 -3R_1](./images/fb500f7ee9892774999183ff5cc78dff5362cfac.png), so its “undo” operation is ![R_2 \gets R_2 + 3R_1](./images/f59fd4627cf96bf88f4a1f7c05dee548a2cc410a.png), which corresponds to ![E_1^{-1}= \begin{bmatrix}1 & 0 \\3 & 1 \end{bmatrix}](./images/e370e807366f32130a01c7efaddcdfa616026167.png).

The elementary matrix approach teaches us that every invertible matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) can be decomposed as the product of elementary matrices. The inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) consists of the product of the inverses of the elementary matrices that make up ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) (in the reverse order).

###[Using a computer algebra system](./Front matter.md)

You can use a computer algebra system to specify matrices and compute their inverses. Let’s illustrate how to find the matrix inverse using the computer algebra system at[`http://live.sympy.org`](./_evaluate=A%20%3D%20Matrix(%20%5B%20%5B1%2C2%5D%2C%20%5B3%2C4%5D%20%5D%20.md)%0A%23--%0AA.inv()%0A%23--%0A).

\>>> from sympy.matrices import Matrix
>>> A = Matrix( \[ \[1,2\],\[3,9\] \] )   # define a Matrix object    
>>> A.inv()                         # call the inv method on A
\[ 3, -2/3\]
\[-1,  1/3\]

Note `SymPy` returns an answer in terms of exact rational numbers. This is in contrast with numerical computer algebra systems like[`Octave`](./octave.md) and `MATLAB`, which are based on floating point arithmetic.

###[Discussion](./Front matter.md)

We’ve explored several ways to compute matrix inverses. If you need to find the inverse of a matrix using only pen and paper, on a final exam for example, I recommend using the Gauss–Jordan elimination procedure on the extended array:

![[\;A\; | \; \mathbbm{1}\:\;  ]   \; 
- \textrm{G--J elimination} \rightarrow \; 
[ \; \:\mathbbm{1}\;  | \; A^{-1} \;],](../Images/9140923f394793f6195dcc4185ee96219c019728.png)

since it is fairly easy to perform even for large matrices and it leverages your experience with the Gauss–Jordan elimination procedure.

For ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrices, the formula ![\begin{bmatrix} a&\!\!b\\   c&\!\!d  \end{bmatrix}^{-1}  =\frac{1}{ad-bc}
\begin{bmatrix}  \; d&\!\!-b\\   -c& \; a  \end{bmatrix}](./images/3e8d13b227782b7c5e0c93c55045c34c6cac80cd.png) is faster.

####[Invertibility](./Front matter.md)

Not all matrices are invertible. Keep this in mind, since teachers might try to trick you by asking you to find the inverse of a non-invertible matrix. Let’s analyze how each procedure for computing the inverse fails when applied to a non-invertible matrix ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png). The inverse formula based on the determinant and the adjugate matrix is ![D^{-1} = \frac{1}{ \textrm{det}(D) } \textrm{adj}(D)](./images/d9c915bdbeaa8eccd203f8e1143382f583be626f.png). However, if the matrix ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png) is not invertible, then ![\textrm{det}(D)=0](./images/b3ea91a5792593fdcf1813e1a9a980e6b4a0c52f.png) and the formula fails due to a divide-by-zero error. The row operations approach to computing the inverse will also fail. Starting from the extended array ![[\;D\; | \; \mathbbm{1}\:\;  ]](../Images/2375031b452faa85f537067e843d067b19454103.png), you can apply all the row operations you want, but you’ll never be able to obtain the identity matrix in the left half of the extended array. This is because the reduced row echelon form of a non-invertible matrix ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png) has at least one row of zeros: ![\textrm{rref}(D) \neq \mathbbm{1}](./images/f02c52fe136510264af8633df14fc3d7d67962a0.png). We’ll discuss invertible matrices and their properties in[Section 5.4](./Chapter 5_ Linear transformations.md). For now, be sure to remember the determinant _invertibility test_: if ![\textrm{det}(A)=0](./images/4c192db42d3bd89cf462441ca977988e7069d97b.png), then ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is non-invertible, and if ![\textrm{det}(A)\neq 0](./images/69633a1b936d0299a2d93cf1e2aada740f28d697.png), then ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible.

###[Exercises](./Front matter.md)

E3.10 For what values of ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) is the matrix ![A =  \begin{bmatrix} 2 & 3 \\ 4 & \alpha \end{bmatrix}](./images/b71f459922da52bd71e2181cd7c424c14f71a801.png) invertible?

E3.11 Compute ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) where ![A =  \begin{bmatrix} 1 & 1 \\ 1 & 2 \end{bmatrix}](./images/b0eea58030688fef8cf3b559fde5ca4b578451d6.png).

E3.12 Solve for ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) in the equation ![\begin{bmatrix}1 & 3\\ -1 & -2\end{bmatrix}
\begin{bmatrix}x \\ y\end{bmatrix} = \begin{bmatrix}1 \\ 2\end{bmatrix}](./images/168026f2ac2df11d42612f58c8db1389116f82d8.png).

E3.13 Show that for an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) invertible matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), the determinant of the adjugate matrix is ![\left| \textrm{adj}(A) \right| = \left(\left| A \right|\right)^{n-1}](./images/1a1372678ed7e0cd7faff26682dcd2418028dfb2.png).

Recall that ![|A^{-1}|=\frac{1}{|A|}](./images/372094416196de1d2449c56b0a10e14a227dd9a5.png) and ![\left| \alpha A \right|=\alpha^n \left| A \right|](./images/d5356650bbdd12e81646bc54d0ed338df89bf5ff.png).

##[3.6 Computational problems](./Chapter 3_ Computational linear algebra.md)

We’ve reached the problem section where you’re supposed to practice all the computational techniques of linear algebra. This is not going to be the most exciting three hours of your life, but you’ll get through it. You need to know how to solve computational problems by hand and apply the Gauss–Jordan elimination procedure; and you need to know how to multiply matrices, calculate determinants, and find matrix inverses. These computational techniques enable all the advanced procedures we’ll develop later in the book. If you skip these practice problems, you’ll have trouble later when it comes to mastering more advanced topics that rely on these basic matrix operations as building blocks. Do this important work now, and you’ll be on your way to becoming fluent in linear algebra computations... plus, the rest of the book will be much more pleasant.

P3.1 Mitchell is on a new diet. His target is to eat exactly ![25](./images/f38b3411a7b45f6e9eca83f0712fff36a61d4b53.png) grams of fat and ![32](./images/b6d268fd2bd0ed2ab3b68d6fd09fb77f20fdaa67.png) grams of protein for lunch today. There are two types of food in the fridge, ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) and ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png). One serving of food ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) contains one gram of fat and two grams of protein, while a serving of food ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png) contains five grams of fat and one gram of protein. To figure out how many servings of each type of food he should eat, Mitchell writes the following system of equations:

![\begin{array}{rll}
x &   +  \; \;    	5y 	&	= \; 25	\\
2x &  +  \; \;    \; y 		& 	= \; 32
\end{array}
\qquad
\Rightarrow
\qquad		
\left[\begin{array}{cc|c}
1& 5 		& 25  \! \\
2 & 1 	& 32  \!
\end{array}\right]\!.](../Images/ed3fcadb77be1838503a18299f732cf541166a2b.png)

Help Mitchell find how many servings of ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) and ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png) he should eat.

Find the reduced row echelon form of the augmented matrix.

P3.2 Alice, Bob, and Charlotte are solving this system of equations:

![\begin{array}{rrl}
3x &  + 		3y 	&	= 6	\\
2x &  + \frac{3}{2}y 	& 	= 5
\end{array}
\qquad
\Rightarrow
\qquad
\left[\!\!\begin{array}{cc|c} 
3 & 		3  \;  & 6 \\
2 &  \frac{3}{2}    \; & 5 
\end{array}\!\!\right]\!	.](../Images/0ce5495cde37f935354a8ce7c70d39e1270a3476.png)

Alice follows the standard procedure to obtain a leading one by performing the row operation ![R_1 \gets \frac{1}{3}R_1](./images/8bed9da2f194c72ca884a4a422e7aeb69052c5d6.png). Bob starts with a different row operation, applying ![R_1 \gets R_1 - R_2](./images/ab66855edb341245eb61d47b836fa50eff57f12a.png) to obtain a leading one. Charlotte takes a third approach by swapping the first and second rows: ![R_1 \leftrightarrow R_2](./images/77c39108f94d72452572c9f36dac38fad60868fe.png). Their respective versions of the augmented matrix are shown below.

1.            ![\left[\!\!\begin{array}{cc|c} 
    1 & 		1  \;  & 2 \\
    2 &  \frac{3}{2}    \; & 5 
    \end{array}\!\!\right]\!](../Images/a35dd2297dbf8f147479c8104cb236b3c036348f.png)
2.            ![\left[\!\!\begin{array}{cc|c} 
    1 & \frac{3}{2}    \;  & 1 \\
    2 &  \frac{3}{2}    \; & 5 
    \end{array}\!\!\right]](../Images/2030501e70c111e64c260fc52a94077b091036fb.png)
3.  ![\left[\!\!\begin{array}{cc|c} 
    2 &  \frac{3}{2}    \; & 5 \\	
    3 & 		3  \;  & 6 
    \end{array}\!\!\right]](../Images/0d425e64083f4b081edd5b458df5324990e5d6b6.png)

Help Alice, Bob, and Charlotte finish solving the system of equations by writing the remaining row operations each of them must perform to bring their version of the augmented matrix into reduced row echelon form.

P3.3 Find the solutions to the systems of equations that correspond to the following augmented matrices.

1.  ![\left[\!\!\begin{array}{cc|c}
    -1 & -2 \;  & -2  \\
    3 &  3  \; & 0 
    \end{array}\!\!\right]\!](../Images/6b894059c84bfd124a525ae9bf5bf844b3c5a90e.png)
2.  ![\left[\!\!\begin{array}{ccc|c}
    1 & -1 & -2  &   1 \\
    -2 &  3 &  3  &  -1 \\
    -1 &  0 &  1  &   2
    \end{array}\!\!\right]](../Images/e96d33fddf48a78d49f163a970fe51d85eb0b49a.png)
3.  ![\left[\!\!\begin{array}{ccc|c} 
    2 & \!-2 &  3  &  2 \\
    1 & \!-2 & -1  &  0 \\
    -2 &  2 &  2  &  1
    \end{array}\!\!\right]](../Images/ca829bf3de7dadcd4a5aac29a69d578e222404d8.png)

P3.4 Find the solution sets for the systems of equations described by the following augmented matrices.

1.  ![\left[\!\!\begin{array}{cc|c}
    -1 & -2 & -2\\
    3 & 6 & 6
    \end{array}\!\!\right]\!](../Images/535822df0c99b152bda1a0eba64fc6a49c7e592d.png)
2.  ![\left[\!\!\begin{array}{ccc|c}
    1 & -1 & -2 & 1\\
    -2 & 3 & 3 & -1\\
    -1 & 2 & 1 & 0
    \end{array}\!\!\right]](../Images/744bcf9c73b9de2322881584404c3e82204e687b.png)
3.  ![\left[\!\!\begin{array}{ccc|c}
    2 & -2 & 3 & 2\\
    0 & 0 & 5 & 3\\
    -2 & 2 & 2 & 1
    \end{array}\!\!\right]](../Images/19faf5110cb247ff8641f440205015b02c01c397.png)

P3.5 Find the solution sets for the augmented matrices.

1.         ![\left[\!\!\begin{array}{ccc|c}
    1 & -1 & -2 & 1\\
    -2 & 2 & 4 & -2\\
    3 & -3 & -6 & 3
    \end{array}\!\!\right]](../Images/45ea31e7c81576824e338c298e151f7fac03d529.png)
2.  ![\left[\!\!\begin{array}{cccc|c}
    2 & -2 & 3 & 2 & 2\\
    0 & 0 & 5 & 3 & 3\\
    6 & -6 & -1 & 0 & 0\\
    6 & -6 & 9 & 6 & 6
    \end{array}\!\!\right]](../Images/aa91aa62d9393fb54c808f928d8c1d9e88b81c5d.png)

P3.6 Find the solutions to the systems of equations.

1.  ![\left[\begin{array}{ccc|c}
    2 & 1 & -1 & 0\\
    0 & 1 & 1 & 0\\
    4 & 2 & -2 & 0
    \end{array}\right]](../Images/8851dbd22d844c7dd63b82a4ac658b396e2aaada.png)
2.  ![\left[\begin{array}{ccc|c}
    2 & 0 & 1 & 5\\
    1 & 4 & 2 & 2\\
    0 & 2 & 1 & 1
    \end{array}\right]](../Images/899172544f3029238070c32e29a037bd872ab8c9.png)
3.  ![\left[\begin{array}{ccc|c}
    1 & 1 & 2 & 2\\
    4 & -2 & -4 & 5\\
    3 & -3 & -6 & 3
    \end{array}\right]](../Images/bf7e75941b3c805ef6e2effe0c407eefea47b057.png)

P3.7 Consider an unknown matrix ![A \in \mathbb{R}^{5 \times 5}](./images/ad878d1ee8562c92bc7c7b9bd7c57915cfffe6e4.png). You’re told the system of linear equations ![A\vec{x} = \vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) has an infinite number of solutions. What is the maximum rank of the matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png)?

P3.8 Solve for ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) in the matrix equation ![ABCD=AD](./images/d33638b15fa7d5b969daf1c605fcc27be0ca9cbe.png).

P3.9 Solve for the following matrix equations problems:

1.  Simplify the expression ![MNB^{-1}BK^{-1}KN^{-1}M^{-2}L^{-1}S^{-1}SMK^2](./images/fa4c7210cfe17e5dd16e51b4bc9b1082303ed49c.png).
2.  Simplify ![J^{-3}K^{2}G^{-1}GK^{-3}J^2](./images/3d01603f76f5b8f584725da102f04585c94c2c27.png).
3.  Solve for ![A](./images/b8ea154608b63c4e8d479d61a6aebd1d90803164.png) in the equation ![A^{-1}BNK=2B^{2}B^{-1}NK](./images/77dd33ae8dabfa591ee440e35dbde32fdcd7d878.png).
4.  Solve for ![Y](./images/7c269bd77f359a43013d04c75910fa1ff14ddc8c.png) in ![SUNNY=SUN](./images/a452f5cfa94d7f9ec3b958470c99e48661476c30.png).

You can assume all matrices are invertible.

P3.10 Solve for ![\vec{x}](./images/d253d396ee7731d3b565bf2ff5bf610db05cf3eb.png) in ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png), where ![A=\begin{bmatrix}
1 & 0 & -3\\
2 & -1 & 1\\
0 & 0 & -1
\end{bmatrix}](./images/e168c0f0aadc6b1affba96de76d81cf3efd5e651.png) and ![\vec{b} = (2, 2, 3)^\sfT](./images/cbad656ba376273fd0577ae75d8b2866d2081b36.png).

Express the equation ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) as an augmented matrix.

P3.11 Solve for ![\vec{x}](./images/d253d396ee7731d3b565bf2ff5bf610db05cf3eb.png) in the equation ![\vec{x} = \vec{d} + A\vec{x}](./images/99d2e347ba896257f5cd25dc13c1a2c80ad506c0.png), where ![A=\begin{bmatrix}
0 		&	0.05		&	0.3		\\
0.01  	&	0		&	0.01		\\
0.1		&	0		&	0		
\end{bmatrix}](./images/081b1cab8c21e5622cc39519458700708c6705d0.png), and ![\vec{d} = (25, 10, 14)^\sfT](./images/3731b2576093faae63a631786d6b8227d0bc0c5f.png). Use[`live.sympy.org`](./live.sympy.org.md) to perform the calculations.

Rewrite as ![\mathbbm{1}\vec{x} = \vec{d} + A\vec{x}](./images/11e45c2a33e142e0110f27f4bb743aaa6885d828.png), then bring all the ![\vec{x}](./images/d253d396ee7731d3b565bf2ff5bf610db05cf3eb.png)s to one side.

P3.12 Given the following two matrices,

![A =\begin{bmatrix}
1 & 1 & 1\\
0 & 4 & 2\\
3 & 1 & 0
\end{bmatrix}
\quad
\textrm{and}
\quad
B=\begin{bmatrix}
3 & 1\\
2 & 0\\
1 &1
\end{bmatrix}\!,](./images/93a7d18a9e38c3a527464ca5b69e55a51ca995c4.png)

compute the matrix products **a)** ![AB](./images/8a07ac9281e4ab08a6c913813d2381639a19055f.png), **b)** ![AA](./images/f939a2b00aa67057ff50f224646155a4ad3777db.png), **c)** ![BA](./images/eca7b56ba1666a204b05846d630b7f939e262f52.png), and **d)** ![BB](./images/a82c78bda037bb096aeca653ece10cecdeaa24f5.png).

P3.13 Compute the product of three matrices:

![\begin{bmatrix}
2 & 10 & -5 & 0\\
0 & 0 & 1 & 3
\end{bmatrix}
\begin{bmatrix}
1 & 3\\
0 & 2\\
5 &1\\
-3 & -4
\end{bmatrix}
\begin{bmatrix}
1 & 1\\
1 & 1
\end{bmatrix}.](./images/030a06717f012d4b67ada5b08ec3e60f2e06604f.png)

P3.14 Consider the following three matrices:

![X = \begin{bmatrix}0	&	1	\\	1	&	0\end{bmatrix}\!,
\quad
Z = \begin{bmatrix}1	&	0	\\ 	0	&	-1\end{bmatrix}\!,
\quad
\textrm{and}
\quad
H = \begin{bmatrix}\frac{1}{\sqrt{2}} 	& \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} 	& -\frac{1}{\sqrt{2}}\end{bmatrix}\!.](./images/4fd1c0cd23287a40aad07f8ff671edcc0a7c23ed.png)

Show that ![HXH = Z](./images/af404e8600c608c4b3aad8ee35746874b29f1e00.png) and that ![HZH = X](./images/d2ebfb101ee279c2e5c61967d67107449126ec0a.png).

P3.15 Given the matrices

![L = \begin{bmatrix}-1 & 1 & 3\\3 & 0 & 3\\3 & 2 & 1\end{bmatrix},
\quad
M = \begin{bmatrix}-1 & 3 & 3 & 1\\-1 & 4 & -1 & 2\\-2 & 2 & 3 & -2\end{bmatrix},
\quad
\textrm{and}
\quad
N = \begin{bmatrix}5 & 3\\0 & 5\\3 & -2\end{bmatrix}\!,](./images/5e4979871bfdb926efc136aa42de54f345e642db.png)

compute the value of the following matrix products:

1.  ![L^2](./images/28b353ebff777b12d626920e9d0ff0cbaac363d5.png)
2.  ![LM](./images/7ed2c882939d28eca5ffb8766c3bf106b4beb407.png)
3.  ![LN](./images/592d59d6791c7b6429bcd8d9dbfd7f785e9a1785.png)
4.  ![M^\sfT \!L](./images/1046617663b6d271c0a1d58c5e78fd0b215b0a27.png)
5.  ![N^\sfT \!L](./images/ba9aa98b9be1480bf48224a331e7d0ba8cacd41c.png)
6.  ![N^\sfT \!L M](./images/3e58a59fbf2998eaa463e014527704161130ce18.png)

P3.16 Given an unknown variable ![\alpha\in\mathbb{R}](./images/69bd52ea0910ca7e80a86efe3ae4c0a8bc2fe403.png) and the matrices

![A\!=\!\begin{bmatrix}
\cos(\alpha) & 1\\
-1 & -\sin(\alpha)
\end{bmatrix};
\quad
B\!=\!\begin{bmatrix}
\sin(\alpha) & 0\\
0 & -\sin(\alpha)
\end{bmatrix};
\quad
C\!=\!\begin{bmatrix}
1 & -\cos(\alpha)\\
\sin(\alpha) & 1
\end{bmatrix},](./images/1fa14b282502eefe470663a53710819eff8ec3d2.png)

compute the value of **a)** ![A^2+B^2](./images/07624be360ade8e405aa2ab8f5d8c7f5a5e937d5.png), **b)** ![A^2+C](./images/67227cde072043c9ae4c81d083dfa90eabcec834.png), and **c)** ![A^2+C-B^2](./images/42cd823a21466e7d6b3ee2c4d17f2719d5f328e5.png). Give your answer in terms of ![\alpha](./images/9e93fbac894e6dd19e79fd9a0b673c5c70f5c7e4.png) and use the double-angle formulas as needed.

P3.17 Find the determinants of the following matrices.

**a)**  ![\begin{bmatrix}
2 & 1\\
3 & 0
\end{bmatrix}](./images/621b13a375c6d4ef3b3bb3763d83939bd33b2dca.png)**b)**  ![\begin{bmatrix}
0 & 5 & 3\\
0 & 1 & 1\\
0 & 1 & 0
\end{bmatrix}](./images/9ec5931119e874c783ec8f22ae4bc77d34ca311b.png)**c)** ![\begin{bmatrix}
1 & 2 & 0\\
3 & 1 & 1\\
4 & -2 & 0
\end{bmatrix}](./images/9c0b618befc1d95943c9e439c4351f617cb26382.png)

P3.18 Find the determinants of the matrices.

![A = 
\begin{bmatrix}
3 & -1 & 5 & 2\\
0 & 2 & 2 & -3\\
0 & 0 & 4 & 0\\
0 & 0 & 0 & -2
\end{bmatrix}](./images/c14f99923f434f83859bc6d9e16ed63cbe291599.png) ![B=\begin{bmatrix}
2 & -1 & 0 & -3 & 2\\
0 & 1 & 1 & 3 & 0\\
1 & 4 & 0 & 0 & -1\\
3 & -2 & 3 & 1 & 0\\
-1 & 0 & -1 & 0 & 2
\end{bmatrix}](./images/180a2a62d2bff39ee03ecb060bce29c43d679d67.png)

P3.19 Determine if the following sets of vectors are linearly dependent or linearly independent.

1.  ![\{ (1,1,0), (1,0,1), (0,1,1) \}](./images/ac5f0cab6b5d3188169002056d21b26438ded8ff.png)
2.  ![\{ (1,1,0), (1,0,1), (1,3,-2) \}](./images/8ba74138efe1b51cbbe13c1593265dc852d0022d.png)
3.  ![\{ (1,2,3,4), (-1,-2,1,0), (0,0,1,1),(1,0,0,1) \}](./images/c2b75979d0153a03d8dd29b91c8796ddea0f976b.png)

P3.20 Find the area of a parallelogram that has vectors ![\vec{v} = (3, -5)](./images/e11ffb819c80b2fbf1acb4d25c1faa04359068cc.png) and ![\vec{w} = (1, -1)](./images/8f31a80c3e8176e6d16d1455c27411a234494702.png) as its sides.

Use the formula from[Section 3.4.2](./Chapter 3_ Computational linear algebra.md) (page 3.4.2).

P3.21 Find the volume of the parallelepiped that has the vectors ![\vec{u}= (2, 0, 1)](./images/cd79af95f1eb1bfb70138be0538003e22693aa54.png), ![\vec{v}= (1, -1, 1)](./images/d36fbbc31776d8dad02fd6b77a994815b80a2ba6.png), and ![\vec{w}= (0, 2, 3)](./images/21ea0de3ebd711d084068ed7d2ec698c2dfd69d9.png) as sides. See[Figure 3.9](./Chapter 3_ Computational linear algebra.md) for an illustration.

P3.22 Suppose ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) and ![N](./images/6db7ee50944856889e5ae6312383d0890612bec3.png) are unknown ![4 \times 4](./images/32625d296aa8c1162b98bc4fcdde00c4c17c8606.png) matrices with ![|M|=-2](./images/2d0f4bfa8d8251b99b2ce26ed5d472f5c7c4f798.png) and ![|N|=7](./images/6acdcd17d3973aaf4fd5ab64aa091c45d8db1b86.png). Compute the values of these determinant expressions:

1.      ![|M^\sfT|](./images/d74c83800af3dd8cd0e9475d75f584dd14f5c40b.png)
2.      ![|3M|](./images/fd07455ab11c8a82dbb7c84af344b4809d24cf31.png)
3.      ![|M^3|](./images/282a20a5ab299b1ed11cd180fb8106809e169b24.png)
4.      ![|MN|](./images/06b0f450eeb71edc59b65f1b2133bf2052bdafed.png)
5.  ![|M^\sfT \! N M|](./images/bf80daf4e1f1b12244f0edced7a214b2185a4a65.png)

Use the properties of the determinant operation.

P3.23 Given the matrix

![A=\begin{bmatrix}
3 & -2 & 0 & 1\\
0 & 1 & 3 & -1\\
5 & 0 & 1 & 4\\
0 & 3 & -4 & 2
\end{bmatrix},](./images/79bcd9cccecb54fec564d117f52cabac955cd933.png)

**a)**-   Find the determinant of ![A](./images/b8ea154608b63c4e8d479d61a6aebd1d90803164.png).
**b)**-   Find the determinant when you interchange the first and third rows.
**c)**-   Find the determinant after multiplying the second row by ![-2](./images/69ec4e71f810dd2c28c617a1a497ae2efb012d30.png).

P3.24 Check whether the rows of the following matrices are linearly independent:

 ![A=\begin{bmatrix}
1 & 3\\
2 & 6
\end{bmatrix}](./images/ebc41cfa7c83307ece43294228b97eae4fb1a512.png)  ![B=\begin{bmatrix}
1 & 4 & 3\\
2 & 1 & 1\\
0 & -2 & -1
\end{bmatrix}](./images/22420e27af560cf674f31d30e39898fc4396a2c8.png)

 ![C=\begin{bmatrix}
0 & 0 & 0 & 0\\
2 & -2 & 2 & -2\\
-4 & 4 & -4 & 4\\
-8 & 8 & -8 & 8
\end{bmatrix}](./images/7c3bdee41c877994ff923e97335a0fc33bad57dd.png)  ![D=\begin{bmatrix}
1 & 1 & 1 & 1\\
2 & 0 & -2 & 0\\
-1 & 2 & 1 & -2\\
1 & -1 & -1 & 1
\end{bmatrix}](./images/73982b35228a2db4ca600dd5e42af790a5d4bbaf.png)

Are the _columns_ of these matrices linearly independent?

P3.25 The transformation from _polar coordinates_  ![(r,\theta)](./images/e56f3ecc188384fd10dba62d219eee4542774cbf.png) to Cartesian coordinates ![(x,y)](./images/3f9958c361f91abc047c8efa598684fe4cff082e.png) is given by the equations ![x(r,\theta) = r \cos\theta](./images/7922f9856cc4e1db8241b483613fb48dfbe724c2.png) and ![y(r,\theta) = r \sin\theta](./images/e897ec3ba5a7ad3596ec4319ae47a8a5af583d2d.png). Under this transformation, “a little piece of area” ![dxdy](./images/6b84744cbc04ed1cdc0193d64dbda9fd9db7f354.png) is transformed to “a little piece of area” ![\det(J) drd\theta](./images/d8b00bf6b837dbb0403c4a297645a9a421d74fb2.png), where ![\det(J)](./images/85f5dd0ddd43bb3106869118120dd28f70f92809.png) is the _area scale factor_ of the transformation from polar coordinates to Cartesian coordinates. The matrix ![J](./images/9f95116d9b689ab3ff63f0ffca7a95ae54f69e6d.png) contains the partial derivates of ![x(r,\theta)](./images/c799f4aba824d05d8bdb5041a61ac0c22feb1637.png) and ![y(r,\theta)](./images/bc09ae0565d0fc44c5dc55eb7c4ff71277091463.png), and is called the _Jacobian matrix_ of the transformation:

![J 
=
\begin{bmatrix}
\frac{\partial x}{\partial r}		&		\frac{\partial x}{\partial \theta}		\\
\frac{\partial y}{\partial r}		&		\frac{\partial y}{\partial \theta}		
\end{bmatrix}\!.](./images/3b374912adf866e2d20ebd8d8f9392e686605221.png)

Compute the value of ![\det(J)](./images/eff2ca63f8678eee7c25e44d27a2888aeba4459b.png).

P3.26 Spherical coordinates ![(\rho,\theta,\phi)](./images/735dfc634dc7aafa7b1f7deb25f7afbff125e8e0.png) are described by

![\begin{align*}
x &= \rho \sin\phi \cos\theta,		\\
y &= \rho \sin\phi \sin\theta,		\\
z &= \rho \cos\phi.
\end{align*}](./images/acf5b4c172234d2730e1185e8f8fbe8c742a2203.png)

Small “volume chunks” transform according to ![dxdydz =  \det(J_s) d\phi d\theta d\rho](./images/6bfcff6b284c0549a6a58b5308504baa47157bab.png), where ![\det(J_s)](./images/d045522ea0f34b26de15aeb77b7ccb56cf2dac76.png) is the _volume scale factor_, computed as the determinant of the Jacobian matrix of the change-of-coordinates transformation:

![J_s 
=
\begin{bmatrix}
\frac{\partial x}{\partial \rho}		&		\frac{\partial x}{\partial \theta}		& 	\frac{\partial x}{\partial \phi}		\\
\frac{\partial y}{\partial \rho}		&		\frac{\partial y}{\partial \theta}		& 	\frac{\partial y}{\partial \phi}		\\
\frac{\partial z}{\partial \rho}		&		\frac{\partial z}{\partial \theta}		& 	\frac{\partial z}{\partial \phi}
\end{bmatrix}\!.](./images/31f8504cf52e5e95b8f09279f7190a660ad7c620.png)

Compute the absolute value of ![\det(J_s)](./images/d045522ea0f34b26de15aeb77b7ccb56cf2dac76.png).

P3.27 Find the inverses of the following matrices:

**a)**  ![\begin{bmatrix}
0 & 1\\
0 & 0
\end{bmatrix}](./images/07715f8839f705b02adfeb8aee6e80a2df2a214c.png)**b)**  ![\begin{bmatrix}
1 & 2\\
2 & 5
\end{bmatrix}](./images/ec4d3440aa6f5565828ce303912a315e95e0afbc.png)**c)** ![\begin{bmatrix}
2 & 3\\
2 & 4
\end{bmatrix}](./images/45684681112a8286ded4f8eb4fba3ea6325549a7.png)

P3.28 Given the matrix equation ![AB=C](./images/7de256cf406312440b51cdc5e3a31e5d747b8e0c.png), where ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) and ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) are ![2 \times 2](./images/8d9f69fe9ab543dc19bd60e8ea565644efbcebb4.png) matrices, find the matrix ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png).

 ![A=\begin{bmatrix}
1 & 4\\
2 & 7
\end{bmatrix}](./images/7b4aa044776bec438e9da34d2c960a4402b6b47c.png)  ![C=\begin{bmatrix}
3 & 2\\
1 & -4
\end{bmatrix}](./images/34b59e56e05c937d2c6e24668401a717a607b499.png)

P3.29 Find the inverses of the matrices ![A=\!\begin{bmatrix}
1 & 4 & 3\\
2 & 1 & 1\\
0 & -2 & -1
\end{bmatrix}](./images/8e834fad025a2170a7f1af9699404baa23ba97df.png) and ![B=\!\begin{bmatrix}
0 & -3 & 2 & 4\\
1 & -1 & 1 & -1\\
2 & 4 & 0 & -2\\
3 & 0 & 1 & 0
\end{bmatrix}](./images/1a9a66290528498e6adaad61b894e7659a222ca1.png).

P3.30 Prove that the zero matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) has no inverse.

P3.31 Obtain the matrices of cofactors for the following matrices.

![A \! =\!\begin{bmatrix}
1 & 4 & 3\\
2 & 1 & 1\\
0 & -2 & -1
\end{bmatrix}](./images/a6836cdad339dd67826e426c495b8f17cc7faf73.png) ![B=\begin{bmatrix}
5 & 0 & 1\\
3 & -1 & -3\\
0 & -4 & -2
\end{bmatrix}](./images/5d0d548a8a9550747ae636d195e8e06d1d97e712.png) ![C\!=\!\begin{bmatrix}
1 & 1 & 1 & 1\\
2 & 0 & -2 & 0\\
-1 & 2 & 1 & -2\\
1 & -1 & -1 & 1
\end{bmatrix}](./images/ceb88c3c9ffe5e4011c7773eb34b8b07270c432b.png)

P3.32 Implement the formula ![A^{-1} = \frac{1}{ \textrm{det}(A) } \textrm{adj}(A)](./images/3989d1ae91f55118127698b355486ecf72f705d3.png) for the case of ![3 \times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) matrices using a spreadsheet application like LibreOffice, OpenOffice, Excel, or Google Sheets. Assume the entries of the matrix are specified in the top right corner of the spreadsheet: `A1:C3`. Start by writing the formula for computing the determinant and the matrix of cofactors, then combine these partial calculations to obtain the nine entries of the matrix inverse. Test that your formula is correct by finding the inverse of ![A = \begin{bmatrix}1 & 4 & 3\\2 & 0 & 1\\0 & -2 & -1\end{bmatrix}](./images/19e95cebb89d40d8c86f14bbf1dd1e9506970030.png). Compare your formula’s output with the built-in function `=MINVERSE(A1:C3)`.

P3.33 Find the values ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png), ![b](./images/ae769ce22c6289af843e3e66bd3145003e72ccf6.png), ![c](./images/0da715a1d62623ace880d9c3dde79450f829f124.png), and ![d](./images/dd565b0bdaf16b09052be14b28af85a1bdefb913.png) that satisfy the equation

![\begin{bmatrix}
1 & 3\\
-2 & -1
\end{bmatrix}
\begin{bmatrix}
a & b\\
c & d
\end{bmatrix}
=
\begin{bmatrix}
3 & -5\\
4 & 0
\end{bmatrix}\!.](./images/201936dac35daa56e0b6ecce0ea5d754abb831c7.png)

P3.34 Given the constraints ![a=g](./images/5483943a9f7b0009acaa6042ec168b6d5db35b9d.png), ![e=b=f](./images/82618df3a74c744d318b04773319a1b65378ae9f.png), and ![c=d=h](./images/7dd706cb2ac6de9312ddea9bee4e3d380272ada2.png), find a choice of the variables ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png), ![b](./images/ae769ce22c6289af843e3e66bd3145003e72ccf6.png), ![c](./images/0da715a1d62623ace880d9c3dde79450f829f124.png), ![d](./images/dd565b0bdaf16b09052be14b28af85a1bdefb913.png), ![e](./images/73e1641932f0f0a0b96287cc57cb23c7f8ed319b.png), ![f](./images/b1f500d1f1960fa9fb85aa0984ab261beb28c746.png), ![g](./images/02d971083edc95192057f7439c1b92e3df1c2959.png), ![h](./images/77e0e4a50e89652b20f69385d6e8957897e96dcf.png) that satisfies the matrix equation:

![\begin{bmatrix}
a & b\\
c & d
\end{bmatrix}\begin{bmatrix}
e & f\\
g & h
\end{bmatrix}
=
\begin{bmatrix}
-2 & -3\\
0 & 2
\end{bmatrix}\!.](./images/058f3e46eadd19247b5706496b31498e55af42da.png)

P3.35 Given the matrix ![A = \begin{bmatrix}a_{11} & a_{12} \\ a_{21} & a_{22}\end{bmatrix}](./images/8a159838978407aef5b3373a96041d0730ba2a01.png), explain how you can obtain the matrices ![B = \begin{bmatrix}\alpha a_{11} & \alpha a_{12} \\ \beta a_{21} & \beta a_{22}\end{bmatrix}](./images/fb4080372c241f5e323cddcfbc3b9ae70eec3e42.png) and ![C = \begin{bmatrix}\alpha a_{11} & \beta a_{12} \\ \alpha a_{21} & \beta  a_{22}\end{bmatrix}](./images/18d203bd767ea33ddd7fdfaef936fdc80001f6e0.png).

Use matrix multiplication (from the left and from the right).
