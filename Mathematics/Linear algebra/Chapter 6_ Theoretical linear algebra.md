Chapter 6      

#[Chapter 6 Theoretical linear algebra](./Chapter 6_ Theoretical linear algebra.md)

Let’s take a trip down memory lane: 170 pages ago, we embarked on a mind-expanding journey through the land of linear algebra. We encountered vector and matrix operations. We studied systems of linear equations, solving them with row operations. We covered miles of linear transformations and their matrix representations. With the skills you’ve acquired to reach this point, you’re ready to delve into the abstract, theoretical aspects of linear algebra—that is, since you know all the useful stuff, you can officially move on to the cool stuff.

In math, we often use abstraction to find the commonalities between different mathematical objects. These parallels give us a deeper understanding of the mathematical structures we compare. This chapter extends what we know about the vector space ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) to the realm of abstract vector spaces of vector-like mathematical objects [Section 6.3](./Chapter 6_ Theoretical linear algebra.md)). We’ll discuss linear independence, find bases, and count dimensions for these abstract vector spaces. We’ll define abstract inner product operations and use them to generalize the concept of orthogonality for abstract vectors [Section 6.4](./Chapter 6_ Theoretical linear algebra.md)). We’ll explore the Gram–Schmidt orthogonalization procedure for distilling orthonormal bases from non-orthonormal bases [Section 6.5](./Chapter 6_ Theoretical linear algebra.md)). Finally, we’ll introduce vectors and matrices with complex entries [Section 6.7](./Chapter 6_ Theoretical linear algebra.md)).[Section 6.7](./Chapter 6_ Theoretical linear algebra.md) also reviews everything we’ve learned in this book, so be sure to read it even if complex numbers are not required for your course. Along the way, we’ll develop a taxonomy for the different types of matrices according to their properties and applications [Section 6.2](./Chapter 6_ Theoretical linear algebra.md)). We’ll also investigate matrix decompositions—techniques for splitting matrices into products of simpler matrices [Section 6.6](./Chapter 6_ Theoretical linear algebra.md)). The chapter begins by discussing the most important decomposition technique of them all: the _eigendecomposition_, which is a way to uncover the “natural basis” for any matrix.

##[6.1 Eigenvalues and eigenvectors](./Chapter 6_ Theoretical linear algebra.md)

The set of eigenvectors of a matrix is a special set of input vectors for which the action of the matrix is described as a simple _scaling_. In[Section 5.2](./Chapter 5_ Linear transformations.md), we observed how linear transformations act differently on different input spaces. We also observed the special case of the “zero eigenspace,” called the _null space_ of a matrix. The action of a matrix on the vectors in its null space is equivalent to a multiplication by zero. We’ll now put these eigenvalues and eigenvectors under the microscope and see what more there is to see.

Decomposing a matrix in terms of its eigenvalues and its eigenvectors gives valuable insights into the properties of the matrix. Certain matrix calculations, like computing the power of the matrix, become much easier when we use the _eigendecomposition_ of the matrix. For example, suppose we’re given a square matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png),

![A =
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}\!,](./images/92b17968364189abf6c24fb3791551e8b93f45d0.png)

and we want to compute ![A^7](./images/3c623179c4e0f4064b793c363f29ba2bd5cd94f7.png). In other words, we want to compute

![A^7 = \!
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}
\!\!
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}
\!\!
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}
\!\!
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}
\!\!
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}
\!\!
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}
\!\!
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}\!\!.](./images/ba860da27322f0674959fe7cd0ee54879b44354b.png)

That’s an awful lot of matrix multiplications! Now imagine how many times we’d need to multiply the matrix if we wanted to find ![A^{17}](./images/e12699888524c5ed5d86f44bbc1de81be3bd2c11.png) or ![A^{77}](./images/0fe65358d742dc70ca37552a3a8976c2b7da2a57.png). Too many times, that’s how many. Let’s be smart about this. Every matrix corresponds to some linear operation. This means it’s legit to ask, “What does the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) do?” Once we figure that out, we can compute ![A^{77}](./images/0fe65358d742dc70ca37552a3a8976c2b7da2a57.png) by simply doing what ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) does ![77](./images/22c0892c80142902b896bb2b2dd5aa3b27a600c1.png) times.

The best way to see what a matrix does is to look inside it and see what it’s made of (you may need to gradually gain the matrix’s trust before it lets you do this). To understand the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), you must find its _eigenvectors_ and its _eigenvalues_. The word _eigen_ is the German word for “self.” The eigenvectors of a matrix are its “self vectors,” and correspond to a natural choice of basis for describing the action of the matrix. The _eigendecomposition_ is a change-of-basis operation that expresses the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) with respect to its _eigenbasis_ (“self-basis”). The eigendecomposition of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is a product of three matrices:

![\begin{align*}
A=
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}
& =
\; 
\underbrace{\!\begin{bmatrix}
1	&	2	\\
2	&	\!\!-1	
\end{bmatrix}\!
}_Q \; 
\underbrace{\!
\begin{bmatrix}
5 	&  	0 	\\
0	& 	10
\end{bmatrix}\!
}_{\Lambda} 
\; 
\underbrace{\!\!
\begin{bmatrix}
\frac{1}{5} 		& 	\frac{2}{5} 		\\
\frac{2}{5} 		& 	\!-\frac{1}{5}	
\end{bmatrix}\!
}_{Q^{-1}}
=
Q\Lambda Q^{-1}.
\end{align*}](./images/d683fb310f9ba8e8660a551be8b8ee8bec3f1525.png)

You can multiply the three matrices ![Q\Lambda Q^{-1}](./images/a1aca4e6f98100bcc6653f3d8d21e225c4e6c3a4.png) to obtain ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Note that the middle matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) (the capital Greek letter _lambda_) has entries only on the diagonal. The diagonal matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) is sandwiched between the matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) on the left and ![Q^{-1}](./images/18207310aecab4dfab85bf9abeceb6a172ff2f3e.png) (the inverse of ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png)) on the right.

The eigendecomposition of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) allows us to compute ![A^7](./images/3c623179c4e0f4064b793c363f29ba2bd5cd94f7.png) in a civilized manner:

![\begin{align*}
A^7\! & =  A A A A A A A \\
& =  	Q\Lambda 
\underbrace{Q^{-1}Q}_{\mathbbm{1}}\Lambda 
\underbrace{Q^{-1}Q}_{\mathbbm{1}}\Lambda 
\underbrace{Q^{-1}Q}_{\mathbbm{1}}\Lambda 
\underbrace{Q^{-1}Q}_{\mathbbm{1}}\Lambda 
\underbrace{Q^{-1}Q}_{\mathbbm{1}}\Lambda 
\underbrace{Q^{-1}Q}_{\mathbbm{1}}\Lambda Q^{-1}  \\
& =  	Q\Lambda \mathbbm{1} 
\Lambda \mathbbm{1} 
\Lambda \mathbbm{1}
\Lambda \mathbbm{1} 
\Lambda \mathbbm{1} 
\Lambda \mathbbm{1}
\Lambda Q^{-1}  \\
& =  	Q\Lambda \Lambda \Lambda  \Lambda  \Lambda  \Lambda  \Lambda Q^{-1}  \\
& =  	Q\Lambda^7 Q^{-1}.
\end{align*}](./images/1de159682927438827693d0b37a4f4f42ce2c1dc.png)

All the inner ![Q^{-1}](./images/18207310aecab4dfab85bf9abeceb6a172ff2f3e.png)s cancel with the adjacent ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png)s. How convenient! Since the matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) is diagonal, it’s easy to compute its seventh power:

![\Lambda^7=
\begin{bmatrix}
5 	&  	0 	\\
0	& 	10 
\end{bmatrix}^7
=
\begin{bmatrix}
5^7 		&  	0 	\\
0		&	10^7
\end{bmatrix}
=
\begin{bmatrix}
78125 	&  	0 \\
0		& 	10\,000\,000
\end{bmatrix}\!.](./images/d013c5d8c7a0663bd32d4a28597d7d011bd91a05.png)

Thus we can express our calculation of ![A^7](./images/3c623179c4e0f4064b793c363f29ba2bd5cd94f7.png) as

![A^7 = 
\begin{bmatrix}
9 & \!\!\!-2 \\
-2 & 6 
\end{bmatrix}^7
\!
= 
\; 
\underbrace{\!\!\begin{bmatrix}
1	&	2	\\
2	&	\!\!-1	
\end{bmatrix}\!\!
}_Q
\begin{bmatrix}
78125\!	&  0 \\
0	 \!	& 10\,000\,000
\end{bmatrix}
\underbrace{\!\!
\begin{bmatrix}
\frac{1}{5} 		& 	\frac{2}{5} 		\\
\frac{2}{5} 		& 	\!\!-\frac{1}{5}	
\end{bmatrix}\!\!
}_{Q^{-1}}.](./images/3e3e7029259a5187c99ff235b9133428998ed96f.png)

We still need to multiply these three matrices together, but we’ve cut the work from six matrix multiplications to two. The answer is

![A^7
= Q\Lambda^7 Q^{-1}
=
\begin{bmatrix}
8015625 		& 	\!\! -3968750		\\
-3968750 	& 	2062500
\end{bmatrix}\!.](./images/7d6571e4d38a4b46ae704ce9163c4b96526519ac.png)

With this technique, we can compute ![A^{17}](./images/e12699888524c5ed5d86f44bbc1de81be3bd2c11.png) just as easily:

![A^{17}
= Q\Lambda^{17} Q^{-1}
=
\begin{bmatrix}
80000152587890625 	& \!-39999694824218750\\
-39999694824218750 	& 20000610351562500
\end{bmatrix}\!.](./images/ef62e34ecb04cd659e069ab279dd6f9febef74d1.png)

We could even compute ![A^{777}= Q\Lambda^{777} Q^{-1}](./images/92a508b7841165ea0329b98f42c344558a6051ff.png) if we wanted to. I hope by now you get the point: once you express ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) in its _eigenbasis_, computing the powers of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) requires computing the powers of its _eigenvalues_, which is much simpler than carrying out matrix multiplications.

###[Definitions](./Front matter.md)

-   ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png): an ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) square matrix. The entries of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are denoted as ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png).
-   ![\textrm{eig}(A) = (\lambda_1, \lambda_2, \ldots, \lambda_n )](./images/b8f9cb49427a2882100e4fb093f7b3e0dd703fb6.png): the list of _eigenvalues_ of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Eigenvalues are usually denoted by the Greek letter _lambda_. Note that some eigenvalues could be repeated in the list.
-   ![p(\lambda)\!=\det(A - \lambda \mathbbm{1})](./images/ec892f3e70128ef0cc1d28eee8f3f92595174a8c.png): the _characteristic polynomial_ of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). The eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are the roots of the characteristic polynomial.
-   ![\{ \vec{e}_{\lambda_1}, \vec{e}_{\lambda_2}, \ldots, \vec{e}_{\lambda_n} \}](./images/dc56ee6d6fc483ee6f15dd938663b5a77b328ee1.png): the set of _eigenvectors_ of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Each eigenvector is associated with a corresponding eigenvalue.
-   ![\Lambda  \eqdef  \textrm{diag}(\lambda_1, \lambda_2, \ldots, \lambda_n)](./images/665062a7b280766ba1fd8956e098d09320c98829.png): the diagonalized version of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). The matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) contains the eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) on the diagonal:
    
    ![\Lambda = 
    \begin{bmatrix}
    \lambda_1	&  \cdots  	&  0 			\\
    \vdots 		&  \ddots  	&  0  			\\
    0  			&   0      	&  \lambda_n
    \end{bmatrix}.](./images/96b6c9e23255d99b372508a74adbfca51dba37d0.png)
    
    The matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) is the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) expressed in its eigenbasis.
    
-   ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png): a matrix whose columns are eigenvectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):
    
    ![Q 
    \eqdef
    \begin{bmatrix}
    \vert  &  & \vert \\
    \vec{e}_{\lambda_1}  &  \cdots &  \vec{e}_{\lambda_n} \\
    \vert  &  & \vert 
    \end{bmatrix}
    =  
    \tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_\lambda}}.](../Images/587cea6ded6ad6bd2f30e9a2d2bde8106d69cb35.png)
    
    The matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) corresponds to the _change-of-basis_ matrix from the eigenbasis ![B_\lambda = \{ \vec{e}_{\lambda_1}, \vec{e}_{\lambda_2}, \vec{e}_{\lambda_3}, \ldots \}](./images/d4f91e0122ea928fac1e7b05f8bf879bee556dbc.png) to the standard basis ![B_s = \{\hat{\imath}, \hat{\jmath}, \hat{k}, \ldots \}](./images/f8abf09820d3bfb8190f59f8599ff83fce5ec8e0.png).
    
-   ![A=Q\Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png): the _eigendecomposition_ of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)
-   ![\Lambda = Q^{-1}AQ](./images/6e15890f7fe31e3ed4f82b2a15d7a6db60786f70.png): the _diagonalization_ of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

###[Eigenvalues](./Front matter.md)

The fundamental eigenvalue equation is

![A\vec{e}_\lambda = \lambda\vec{e}_\lambda,](./images/0179774dc80879a95c6970ccf2d04b2191d0dc6f.png)

where ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png) is an eigenvalue and ![\vec{e}_\lambda](./images/75eb683d215d8a51d7d8530263bae9361734ca92.png) is an eigenvector of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Multiply ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by one of its eigenvectors ![\vec{e}_\lambda](./images/75eb683d215d8a51d7d8530263bae9361734ca92.png), and the result is the same vector scaled by the constant ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png).

To find the eigenvalues of a matrix, start from the eigenvalue equation ![A\vec{e}_\lambda =\lambda\vec{e}_\lambda](./images/cfe8c47b5c3a090a9c8a01b061c9978c66ea6c32.png), insert the identity ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png), and rewrite the equation as a null-space problem:

![A\vec{e}_\lambda =\lambda\mathbbm{1}\vec{e}_\lambda
\qquad
\Rightarrow
\qquad
\left(A - \lambda\mathbbm{1}\right)\vec{e}_\lambda = \vec{0}.](./images/c01de98b99bc6742a99f2c833ba887f523ffed4d.png)

This equation has a solution whenever ![|A - \lambda\mathbbm{1}|=0](./images/bdd4f63be3d98329f31538d06f03db940d58bd2f.png). The eigenvalues of ![A \in \mathbb{R}^{n \times n}](./images/2f056442410016d3a541715471950849562de0c4.png), denoted ![(\lambda_1, \lambda_2, \ldots, \lambda_n )](./images/54345aafb30ff145fadde40cf4355a25f4b5235a.png), are the roots of the _characteristic polynomial_:

![p(\lambda) 	\eqdef 	\det(A-\lambda \mathbbm{1})		=	0.](./images/e2f302f57ff40adba773837917500ca1256cfb38.png)

Calculate this determinant and we obtain an expression involving the entries ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png) and the variable ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png). If ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix, the characteristic polynomial is a polynomial of degree ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) in ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png).

We denote the list of eigenvalues as ![\textrm{eig}(A)=( \lambda_1, \lambda_2, \ldots, \lambda_n )](./images/b8f9cb49427a2882100e4fb093f7b3e0dd703fb6.png). If ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png) is a repeated root of the characteristic polynomial ![p(\lambda)](./images/30766a7f24f986f8adb53268e60241ea8bb8a4c3.png), it’s called a _degenerate_ eigenvalue. For example, the identity matrix ![\mathbbm{1} \in \mathbb{R}^{2\times 2}](./images/d3d9d51f99c1dbbcd98817871ba416422b620009.png) has the characteristic polynomial ![p_\mathbbm{1}(\lambda)=(\lambda-1)^2](./images/d80d06a87f46a681d3a0163bd8429462f55c8da0.png), which has a repeated root at ![\lambda=1](./images/80fc8bed47c96f557f144e0985441a990951940c.png). We say the eigenvalue ![\lambda=1](./images/80fc8bed47c96f557f144e0985441a990951940c.png) is _degenerate_ and has _algebraic multiplicity_ ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png). It’s important to keep track of degenerate eigenvalues, so we specify the multiplicity of an eigenvalue by repeatedly including it in the list of eigenvalues: ![\textrm{eig}(\mathbbm{1})=(\lambda_1, \lambda_2) = (1,1)](./images/ae71994119e8c75d4ce503b869b7cf4589f139ef.png).

###[Eigenvectors](./Front matter.md)

The _eigenvectors_ associated with eigenvalue ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png) of matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are the vectors in the _null space_ of the matrix ![(A-\lambda_i \mathbbm{1} )](./images/61443e2485045d893da3968378561c84f65ea9dc.png).

To find the eigenvectors associated with the eigenvalue ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png), you need to solve for the components ![e_{\lambda,x}](./images/1a7b42fd96a02efa338de6d35e8da96a96ad5736.png) and ![e_{\lambda,y}](./images/65881d5b5258c250bc50b971c1ed7cb0618b5bb6.png) of the vector ![\vec{e}_\lambda=(e_{\lambda,x},e_{\lambda,y})](./images/db11b98753c83796a558c6e28a0486cf13c551f8.png) that satisfies the equation

![A\vec{e}_\lambda =\lambda\vec{e}_\lambda,](./images/0179774dc80879a95c6970ccf2d04b2191d0dc6f.png)

or equivalently,

![(A-\lambda \mathbbm{1} ) \vec{e}_\lambda = 0
\qquad \Leftrightarrow \qquad
\begin{bmatrix}
a_{11}-\lambda & a_{12} \\
a_{21} & a_{22}-\lambda
\end{bmatrix}
\begin{bmatrix}
e_{\lambda,x} \\
e_{\lambda,y}
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0
\end{bmatrix}.](./images/c815788e933ff196f093e69888b670f26ddc0ae1.png)

You previously solved this type of problem when you learned how to compute the null space of a matrix.

If ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png) is a repeated root (_degenerate_ eigenvalue), the null space of ![(A-\lambda_i \mathbbm{1} )](./images/61443e2485045d893da3968378561c84f65ea9dc.png) could contain multiple eigenvectors. The dimension of the null space of ![(A-\lambda_i \mathbbm{1} )](./images/61443e2485045d893da3968378561c84f65ea9dc.png) is called the _geometric multiplicity_ of the eigenvalue ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png).

###[Eigendecomposition](./Front matter.md)

If an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is _diagonalizable_ (I promise I didn’t make that word up) this means we can find ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) eigenvectors for that matrix. The eigenvectors that come from different eigenspaces are guaranteed to be linearly independent (see exercise [6.1.10](./Chapter 6_ Theoretical linear algebra.md)). We can also pick a set of linearly independent vectors _within_ each of the degenerate eigenspaces. Combining the eigenvectors from all the eigenspaces gives us a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent eigenvectors, which form a _basis_ for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png). This is the _eigenbasis_.

Let’s place the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) eigenvectors side by side as the columns of a matrix:

![Q =
\begin{bmatrix}
\vert  &  & \vert \\
\vec{e}_{\lambda_1}  &  \cdots &  \vec{e}_{\lambda_n} \\
\vert  &  & \vert 
\end{bmatrix}\!.](./images/df244fc4cd2d81a23b6f631097946c37e4eb57df.png)

We can decompose ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) in terms of its eigenvalues and its eigenvectors:

![A = Q \Lambda Q^{-1} =
\begin{bmatrix}
\vert  &  & \vert \\
\vec{e}_{\lambda_1}  &  \cdots &  \vec{e}_{\lambda_n} \\
\vert  &  & \vert 
\end{bmatrix}
\!\!
\begin{bmatrix}
\lambda_1	&  \cdots  &  0 \\
\vdots 	&  \ddots  &  0  \\
0  	&   0      &  \lambda_n
\end{bmatrix}
\!\!
\begin{bmatrix}
\; \\
\; \; \; \; \; \; Q^{-1} \; \; \; \; \; \;  \\
\; 
\end{bmatrix}\!.](./images/c6d976d0e829d96aef585460757c4adf22fd229c.png)

The matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) is a diagonal matrix of eigenvalues, and the matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) is the change-of-basis matrix that contains the corresponding eigenvectors as columns.

Note that only the _direction_ of each eigenvector is important and not the length. Indeed, if ![\vec{e}_\lambda](./images/75eb683d215d8a51d7d8530263bae9361734ca92.png) is an eigenvector (with eigenvalue ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png)), so is any ![\alpha \vec{e}_\lambda](./images/0cb20dd53a146dbb25a082d7766b2076feb97733.png) for all ![\alpha \in \mathbb{R}](./images/291a1b884bfe1bd3bdd9e4811c426bcf4da094c5.png). Thus we’re free to use any multiple of the vectors ![\vec{e}_{\lambda_i}](./images/93c5fcf398fb33ead2faff86020d9fefdfdcb678.png) as the columns of the matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png).

#####[Example](./Front matter.md)

Find the eigendecomposition of the matrix:

![A=\begin{bmatrix}
1 & 2  & 0 \\
0 & 3  & 0 \\
2 & -4 & 2 \end{bmatrix}\!.](./images/fcace8d8f9bf93808d58ffb5d62494948027d895.png)

In decreasing order, the eigenvalues of the matrix are:

![\lambda_1 = 3, \qquad \lambda_2 = 2, \qquad \lambda_3= 1.](./images/0d07f3c7fcc0da3a209b7fdf97a2e5dbab8b1aa9.png)

The eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are the values that appear on the diagonal of ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png).

When a ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix has three distinct eigenvalues, it is diagonalizable, since it has the same number of linearly independent eigenvectors as eigenvalues. We know the eigenvectors are linearly independent by the following reasoning. The matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has three different eigenvalues. Each eigenvalue is associated with at least one eigenvector, and these eigenvectors are linearly independent (see [6.1.10](./Chapter 6_ Theoretical linear algebra.md) on page 6.1.10). Recall that any set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors in ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) forms a basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png). Since the three eigenvectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are linearly independent, we have enough columns to construct a change-of-basis matrix of eigenvectors ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) and use it to write ![A=Q\Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png).

To find the eigenvectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), solve for the null space of the matrices ![(A-3\mathbbm{1})](./images/249dc0d77f8f16316b66c79b1b32eb86eff8a1de.png), ![(A-2\mathbbm{1})](./images/fa95cfeba44c71129e6d41c8e3dea50e92e58ecd.png), and ![(A-\mathbbm{1})](./images/467ede3e5a8a0b0323a970904eae25e49381d336.png) respectively:

![\vec{e}_{\lambda_1} = 
\begin{bmatrix} -1 \\ -1 \\ 2 \end{bmatrix}\!, 
\qquad 
\vec{e}_{\lambda_2} = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}\!, 
\qquad 
\vec{e}_{\lambda_3} = \begin{bmatrix} -1 \\ 0 \\ 2 \end{bmatrix}\!.](./images/174ebe472018237342fc0160fa2664093d0e6705.png)

Check that ![A \vec{e}_{\lambda_k} = \lambda_k \vec{e}_{\lambda_k}](./images/39f275abc876a3a948962131c1746798f40deca7.png) for each of the vectors above. Let ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) be the matrix constructed with the eigenvectors as its columns:

![Q=
\begin{bmatrix}
-1 & 0 & -1 \\
-1 & 0  & 0 \\
2 & 1 & 2 \end{bmatrix},
\qquad \textrm{then compute} \qquad 
Q^{-1} = 
\begin{bmatrix}
0 & -1 & 0 \\
2 & 0  & 1 \\
-1 & 1 & 0 \end{bmatrix}\!.](./images/8745afd22b63fcd3b94bdc60dc660b4b935140b7.png)

Together with the matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png), these matrices form the eigendecomposition of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):

![A = Q\Lambda Q^{-1} =\!
\begin{bmatrix}
1 & 2  & 0 \\
0 & 3  & 0 \\
2 & \!\!-4 & 2 \end{bmatrix}
\!=\!
\begin{bmatrix}
-1 & 0 & \!\!-1 \\
-1 & 0  & 0 \\
2 & 1 & 2 \end{bmatrix} 
\!\!\!
\begin{bmatrix}
3 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 1\end{bmatrix}
\!\!\!
\begin{bmatrix}
0 & \!\!-1 & 0 \\
2 & 0  & 1 \\
-1 & 1 & 0 \end{bmatrix}\!\!.](./images/66ec392f11d28f9c9400257d392c54074725d241.png)

To find the diagonalization of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), move ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) and ![Q^{-1}](./images/18207310aecab4dfab85bf9abeceb6a172ff2f3e.png) to the other side of the equation. More specifically, multiply the equation ![A=Q\Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png) by ![Q^{-1}](./images/18207310aecab4dfab85bf9abeceb6a172ff2f3e.png) on the left and by ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) on the right to obtain the diagonal matrix:

![\Lambda = Q^{-1}AQ = \!
\begin{bmatrix}
0 & \!\!-1 & 0 \\
2 & 0  & 1 \\
-1 & 1 & 0 \end{bmatrix}
\!\!\!
\begin{bmatrix}
1 & 2  & 0 \\
0 & 3  & 0 \\
2 & \!\!-4 & 2 \end{bmatrix}
\!\!\!
\begin{bmatrix}
-1 & 0 & \!\!-1 \\
-1 & 0  & 0 \\
2 & 1 & 2 \end{bmatrix} \!=\!
\begin{bmatrix}
3 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 1\end{bmatrix}\!\!.](./images/757baa39a78317a3cd8353dfc2d5fd6fc260523d.png)

Have you noticed how time consuming it is to compute the eigendecomposition of a matrix? It’s really incredible. Though we skipped some details of the calculation (including finding the solution of the characteristic polynomial and the three null space calculations), finding the eigendecomposition of a ![3\times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix took more than a page of work. Don’t be surprised if it takes hours to compute eigendecompositions on homework problems; you’re not doing anything wrong. Eigendecompositions simply take a lot of work. We’re dealing with a seven-syllable word here—did you really expect the process to be easy?

Actually, computing eigenvectors and eigenvalues _will_ become easier with practice. After eigendecomposing a dozen matrices or so using only pen and paper, you’ll be able to whip through the steps for a ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix in about 20 minutes. That’s a really good thing for your GPA, because the probability of seeing an eigenvalue question on your linear algebra final exam is about 80%. It pays to have a mathematical edge with this stuff.

For readers learning linear algebra without the added motivational bonus of exam stress, I recommend you eigendecompose at least one matrix using only pen and paper to prove to yourself you can do it. In all other circumstances, you’re better off using `SymPy` to create a `Matrix` object; then calling its `eigenvals()` method to find the eigenvalues, or its `eigenvects()` method to find both its eigenvalues and eigenvectors.

###[Explanations](./Front matter.md)

Yes, we’ve got some explaining to do.

####[Eigenspaces](./Front matter.md)

Recall the definition of the _null space_ of a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):

![\mathcal{N}(A) \,\eqdef\, \{ \vec{v} \in \mathbb{R}^n  \; | \;  A\vec{v} = 0 \}.](./images/739cb87eb4f09099b274b40621f68000817dd7b0.png)

The _dimension_ of the null space is the number of linearly independent vectors in the null space.

#####[Example](./Front matter.md)

If the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) sends exactly two linearly independent vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) to the zero vector, ![A\vec{v} = 0, \; A\vec{w} = 0](./images/6a12e5c9296dcab9b6cc12f6a2ae8bd0dfb30aa2.png), then its null space is two-dimensional. We can always choose the vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) to be orthogonal (![\vec{v}\cdot\vec{w}=0](./images/903092627363cf2a56160060b0d0ca857d39ca79.png)) and thus obtain an _orthogonal basis_ for the null space.

Each eigenvalue ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png) is associated with an _eigenspace_. The eigenspace ![E_{\lambda_i}](./images/fcfe5115070f67bd3d38df5bd07df22ef7d4937c.png) is the null space of the matrix ![(A-\lambda_i \mathbbm{1})](./images/61443e2485045d893da3968378561c84f65ea9dc.png):

![E_{\lambda_i}
\,\eqdef\, \mathcal{N}\left( A-\lambda_i \mathbbm{1} \right)
= \{  \vec{v} \in \mathbb{R}^n \; | \;   \left( A-\lambda_i \mathbbm{1} \right)\vec{v} = \vec{0} \, \}.](./images/2ce796aaa0ec2521ab64c2d66f65ec2613dcb1d6.png)

Every eigenspace contains at least one nonzero eigenvector. For degenerate eigenvalues (repeated roots of the characteristic polynomial), the null space of ![\left( A-\lambda_i \mathbbm{1} \right)](./images/ad94e1d443b4acd5a6e75541bf00df13c992f4dd.png) can contain multiple eigenvectors.

####[Change-of-basis matrix](./Front matter.md)

The matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) is a _change-of-basis_ matrix. Given a vector expressed in the eigenbasis ![\tensor{[\vec{v}]}{_{B_{\lambda}}}=(v^\prime_1,v^\prime_2,v^\prime_3)^\sfT_{B_{\lambda}}
= v^\prime_1\vec{e}_{\lambda_1}+ v^\prime_3\vec{e}_{\lambda_3}+v^\prime_3\vec{e}_{\lambda_3}](../Images/e1ff007c9ccfe657e462ee31278d2ac5949eb0ee.png), we can use the matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) to convert it to coordinates in the standard basis ![[\vec{v}]_{B_{s}} = (v_1, v_2,v_3)^\sfT_{B_s} = v_1\hat{\imath} + v_2\hat{\jmath}+v_3\hat{k}](../Images/0abde0bc45fe185b110483e33c4025985eefd6f4.png) as follows:

![\tensor{[\vec{v}]}{_{B_{s}}} 
= 	Q 
\tensor{[\vec{v}]}{_{B_{\lambda}}} 
=  	\tensor[_{B_{s}}]{[\mathbbm{1}]}{_{B_{\lambda}}} 
\tensor{[\vec{v}]}{_{B_{\lambda}}}.](../Images/9fb9cc15a7cf3b5264f3fec6a4f95d704f00d6b6.png)

The change of basis in the other direction is given by the inverse matrix:

![\quad \; 
\tensor{[\vec{v}]}{_{B_{\lambda}}} 
=  	\; Q^{-1} 
\tensor{[\vec{v}]}{_{B_{s}}}
= 	\tensor[_{B_{\lambda}}]{[\mathbbm{1}]}{_{B_{s}}} 
\tensor{[\vec{v}]}{_{B_{s}}}.](../Images/c1f4bdb4b9649a9250297794b39091b905c3ed97.png)

####[Interpretation](./Front matter.md)

The eigendecomposition ![A = Q \Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png) allows us to interpret the action of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) on an arbitrary input vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) as the following three steps:

![\tensor{[\vec{w}]}{_{B_{s}}} 
=   	\tensor[_{B_{s}}]{[A]}{_{B_{s}}} 
\tensor{[\vec{v}]}{_{B_{s}}}
= 	Q
\Lambda 
Q^{-1} 
\tensor{[\vec{v}]}{_{B_{s}}}
= 	\underbrace{\!\!\; \tensor[_{B_{s}}]{[\mathbbm{1}]}{_{B_{\lambda}}} 
\underbrace{\!\!\; \tensor[_{B_{\lambda}}]{[\Lambda]}{_{B_{\lambda}}}
\underbrace{\; \tensor[_{B_{\lambda}}]{[\mathbbm{1}]}{_{B_{s}}} 
\tensor{[\vec{v}]}{_{B_{s}}} 
}_1 
}_2 
}_3\!.](../Images/178b57f0a10ce7545d8c813a5949e38266ba096e.png)

1.  In the first step, we convert the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) from the standard basis to the eigenbasis of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).
2.  In the second step, the action of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) on vectors expressed with respect to its eigenbasis corresponds to a multiplication by the diagonal matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png).
3.  In the third step, we convert the output ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) from the eigenbasis back to the standard basis.

Another way to interpret these three steps is to say that, deep down inside, the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is actually the diagonal matrix ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png). To see the diagonal form of the matrix, we must express the input vectors with respect to the _eigenbasis_:

![[\vec{w}]_{B_{\lambda}} 
=  	\tensor[_{B_{\lambda}}]{[\Lambda]}{_{B_{\lambda}}}
\tensor{[\vec{v}]}{_{B_{\lambda}}}.](../Images/0f1d1b99c0b5950f18585f08c39152afc430f1f7.png)

It’s extremely important you understand the meaning of the equation ![A=Q\Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png) intuitively in terms of the three-step procedure. To help understand the three-step procedure, we’ll analyze in detail what happens when we multiply ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by one of its eigenvectors. Let’s pick ![\vec{e}_{\lambda_1}](./images/c6a7a4f75c1f6532ddf53ed57afe53a9b6f12351.png) and verify the equation ![A\vec{e}_{\lambda_1} 
= Q\Lambda Q^{-1}\vec{e}_{\lambda_1} 
= \lambda_1\vec{e}_{\lambda_1}](./images/8c0772d02f8d9a2d02e31053d525d97f38ced04c.png) by following the vector through the three steps:

![\begin{align*}
\tensor[_{B_{s}}]{[A]}{_{B_{s}}} 
\tensor{[\vec{e}_{\lambda_1}]}{_{B_{s}}}
&= 	Q
\Lambda 
Q^{-1} 
\tensor{[\vec{e}_{\lambda_1}]}{_{B_{s}}}											\\
&= 	\underbrace{\! \tensor[_{B_{s}}]{[\mathbbm{1}]}{_{B_{\lambda}}} \; 
\underbrace{\! \tensor[_{B_{\lambda}}]{[\Lambda]}{_{B_{\lambda}}} 
\underbrace{    \tensor[_{B_{\lambda}}]{[\mathbbm{1}]}{_{B_{s}}} 
\tensor{[\vec{e}_{\lambda_1}]}{_{B_{s}}} 
}_{ (1,0,\ldots)^\sfT_{B_\lambda}    		} 
}_{ (\lambda_1,0,\ldots)^\sfT_{B_\lambda}	} 
}_{ \lambda_1 \tensor{[\vec{e}_{\lambda_1}]}{_{B_{s}}} }
= 	\lambda_1 
\tensor{[\vec{e}_{\lambda_1}]}{_{B_{s}}}.
\end{align*}](../Images/684b68c4fcc2669c326993497ebcb0881b4b97af.png)

In the first step, we convert the vector ![\tensor{[\vec{e}_{\lambda_1}]}{_{B_{s}}}](../Images/4691dd74123cf3b09ce44313987663f6e80eb398.png) to the eigenbasis and obtain ![(1,0,\ldots,0)^\sfT_{B_\lambda}](./images/ee426736b9558037bce346c30273737fe54c8485.png). The second step results in ![(\lambda_1,0,\ldots,0)^\sfT_{B_\lambda}](./images/8da3e17eeb81c99dd76d2a3cdb258611644d1059.png), because multiplying ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) by the vector ![(1,0,\ldots,0)^\sfT_{B_\lambda}](./images/ee426736b9558037bce346c30273737fe54c8485.png) selects the value in the first column of ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png). For the third step, we convert ![(\lambda_1,0,\ldots,0)^\sfT_{B_\lambda}=\lambda_1(1,0,\ldots,0)^\sfT_{B_\lambda}](./images/e5d18a21abbb7f88b56cf5b756456d42b343a3c7.png) back to the standard basis to obtain ![\lambda_1\tensor{[\vec{e}_{\lambda_1}]}{_{B_{s}}}](../Images/788d13bf732e6dd446b0e4659836bab4a00ea092.png). Boom!

####[Invariant properties of matrices](./Front matter.md)

The determinant and the trace of a matrix are strictly functions of the eigenvalues. The determinant of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is the product of its eigenvalues:

![\det(A) = |A| =\prod_i \lambda_i = \lambda_1\lambda_2\cdots\lambda_n,](./images/06d6fb94300c4cae2b85a188a5067f4884578652.png)

and the trace is the sum of the eigenvalues:

![\textrm{Tr}(A)=\sum_i a_{ii}=\sum_i \lambda_i = \lambda_1 + \lambda_2 + \cdots \lambda_n.](./images/2ea8a7927e6853d4992f9a9557cdf3b72eb530b1.png)

The above equations are true because

![|A|=|Q\Lambda Q^{-1}|
=|Q| |\Lambda| |Q^{-1}|
=|Q| |Q^{-1}| |\Lambda|
= \frac{|Q|}{|Q|} |\Lambda|
=|\Lambda| 
=\prod_i \lambda_i,](./images/e4ee256713eec4a517ba4b74cb1d2bd83c23b5f7.png)

and

![\textrm{Tr}(A)=\textrm{Tr}(Q\Lambda Q^{-1})
=\textrm{Tr}(\Lambda Q^{-1}Q)
=\textrm{Tr}(\Lambda \mathbbm{1})
=\textrm{Tr}(\Lambda)
=\sum_i \lambda_i.](./images/67b585ed5222860c5e7a143816683abf4d915d44.png)

The first equation follows from the properties of determinants: ![|AB|=|A| |B|](./images/45d53e7cf41c0b3d6d0ca8049a2a209b4e1dc8d5.png) and ![|A^{-1}|=\frac{1}{|A|}](./images/372094416196de1d2449c56b0a10e14a227dd9a5.png) (see page 2.3.9). The second equation follows from the cyclic property of the trace operator ![\textrm{Tr}(ABC)=\textrm{Tr}(BCA)](./images/823437bf44dec88c6e7d46b5e7cdeb2a23253586.png) (see page 2.3.8).

In fact, the above calculations are true for any _similarity transformation_. Recall that a similarity transformation is a change-of-basis calculation in which a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) gets multiplied by an invertible matrix ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) from the left and by the inverse ![P^{-1}](./images/673110cb74e9c6dd7ef57248c5d46cbb35f61993.png) from the right: ![A^\prime = PA P^{-1}](./images/44ca6de5b33b7128b8853d7396c90098aac048b3.png). The determinant and the trace of a matrix are _invariant_ properties under similarity transformations—they don’t depend on the choice of basis.

####[Relation to invertibility](./Front matter.md)

Let’s briefly revisit three of the equivalent conditions we stated in the invertible matrix theorem. For a matrix ![A \in \mathbb{R}^{n \times n}](./images/2f056442410016d3a541715471950849562de0c4.png), the following statements are equivalent:

-   ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible
-   ![|A|\neq 0](./images/f615db9f7bc3b65e2d42c40b7785e7f55ff65dc1.png)
-   The null space contains only the zero vector ![\mathcal{N}(A)=\{\vec{0}\}](./images/4a0f833076b6035d08158e9dc8d1c755007e1973.png)

The formula ![|A|=\lambda_1 \lambda_2 \cdots \lambda_n](./images/e3ff7bdef46171aa267427a690af9ef091bba800.png) reveals why the last two statements are equivalent. If ![|A|\neq 0](./images/f615db9f7bc3b65e2d42c40b7785e7f55ff65dc1.png), none of the ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png)s are zero (if one of the eigenvalues is zero, the whole product is zero). We know ![\lambda=0](./images/10934b7194187c81748d1850a1ebd06584c5a07b.png) is _not_ an eigenvalue of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), which means there exists no vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) such that ![A\vec{v} = 0\vec{v}=\vec{0}](./images/a0430e871adeb30ec189a6ea1dd8abc906707041.png). Therefore, there are no vectors in the null space ![\mathcal{N}(A)](./images/f44c532970139aa43f2c4a46e02783f940db0cab.png). We can also follow this reasoning in the other direction. If the null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is empty, then there is no nonzero vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) such that ![A\vec{v} = 0\vec{v}=\vec{0}](./images/a0430e871adeb30ec189a6ea1dd8abc906707041.png), which means ![\lambda=0](./images/10934b7194187c81748d1850a1ebd06584c5a07b.png) is not an eigenvalue of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png); hence the product ![\lambda_1\lambda_2\cdots \lambda_n \neq 0](./images/6704dc68bb76517ab1aa48ad06ee88fd0ca426b6.png).

However, if there exists a nonzero vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) such that ![A\vec{v} = \vec{0}](./images/dd0654eddf8afc1a3d57a47b36dc528c6fea569a.png), then ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has a non-empty null space and ![\lambda=0](./images/10934b7194187c81748d1850a1ebd06584c5a07b.png) is an eigenvalue of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png); thus ![|A|=\lambda_1 \lambda_2 \cdots \lambda_n=0](./images/3c383ab33323cba76a062a9c4ad25fe618d3955c.png).

###[Eigendecomposition for normal matrices](./Front matter.md)

A matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is _normal_ if it satisfies the equation ![A^\sfT A = A A^\sfT](./images/063f9caebb88f2bc873e9efb8620bf9229fc6b63.png). All normal matrices are diagonalizable, and the change-of-basis matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) can be chosen to be an _orthogonal_ matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png).

The eigenvectors corresponding to different eigenvalues of a normal matrix are _orthogonal_. Furthermore, we can choose the eigenvectors within the same eigenspace to be orthogonal. By collecting the eigenvectors from all eigenspaces of the matrix ![A \in \mathbb{R}^{n \times n}](./images/2f056442410016d3a541715471950849562de0c4.png), it is possible to obtain a basis ![\{\vec{e}_1,\vec{e}_2,\ldots, \vec{e}_n\}](./images/40e82a98662683434a2486f48aa02e49c558b7aa.png) of orthogonal eigenvectors:

![\vec{e}_{i} \cdot \vec{e}_{j} = 
\left\{ \begin{array}{ll} 
\|\vec{e}_i\|^2 	& \text{ if } i =j, \\
0 		& \text{ if } i \neq j.
\end{array}\right.](./images/35b7ea2d4e7a9e30904cdad8c2df3b5f3d1c1432.png)

Normalizing these vectors gives a set of _orthonormal_ eigenvectors ![\{\hat{e}_1,\hat{e}_2,\ldots, \hat{e}_n \}](./images/0bfc670a2906a6a127fa62f32efbfdb9754d60e2.png) that form a basis for the space ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png):

![\hat{e}_{i} \cdot \hat{e}_{j} = 
\left\{ \begin{array}{ll} 
1 	& \text{ if } i =j, \\
0	& \text{ if } i \neq j.
\end{array}\right.](./images/0e25ba6aa839a0f36e12b497048c955ccfcd7148.png)

Consider now the matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) constructed by using these orthonormal vectors as the columns:

![O=
\begin{bmatrix}
\vert  &  & \vert \\
\hat{e}_{1}  &  \cdots &  \hat{e}_{n} \\
\vert  &  & \vert 
\end{bmatrix}\!.](./images/62e38a818da5d1638aa778aa5b324a78e4dc4c9d.png)

The matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is an _orthogonal_ matrix, meaning it satisfies ![OO^\sfT=I=O^\sfT O](./images/a45f8726698c60d5c89cbe59122dd5792903bf8a.png). In other words, the inverse of ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is obtained by taking the transpose ![O^\sfT](./images/d3a821cd413a76e0c61febeb666dd1b6730512fa.png). To see how this works, consider the following product:

![O^\sfT O 
=
\begin{bmatrix}
\textrm{ ---}\!\! & \hat{e}_{1}  &  \!\!\textrm{--- } \\
& \vdots &  \\
\textrm{ ---}\!\! & \hat{e}_{n} & \!\!\textrm{--- } 
\end{bmatrix}
\!\!
\begin{bmatrix}
\vert  &  & \vert \\
\hat{e}_{1}  &  \cdots &  \hat{e}_{n} \\
\vert  &  & \vert 
\end{bmatrix}
=
\begin{bmatrix}
1  & 0 & 0 \\
0  & \!\ddots & 0 \\
0  & 0 & 1 
\end{bmatrix}
=\mathbbm{1}.](./images/d278f8f354f04e1df80cfe437c2386c29bdd8c2b.png)

Each of the ones on the diagonal arises from taking the dot product of a unit-length eigenvector with itself. The off-diagonal entries are zero because the vectors are orthogonal. By definition, the inverse ![O^{-1}](./images/64d39fc80e7bf6ffb032c24f15a805f24a4490e0.png) is the matrix, which gives ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) when multiplied by ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png), so we have ![O^{-1} = O^\sfT](./images/cddecdde9c2896ba5abef768162e08bbc73b3542.png).

Using the orthogonal matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) and its inverse ![O^\sfT](./images/d3a821cd413a76e0c61febeb666dd1b6730512fa.png), we can write the eigendecomposition of a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as

![A 
= O \Lambda O^{-1} 
= O \Lambda O^\sfT =
\begin{bmatrix}
\vert  &  & \vert \\
\hat{e}_{1}  &  \!\cdots\! &  \hat{e}_{n} \\
\vert  &  & \vert 
\end{bmatrix}
\!\!
\begin{bmatrix}
\lambda_1	&  \cdots  &  0 \\
\vdots 	&  \ddots  &  0  \\
0  	&   0      &  \lambda_n
\end{bmatrix}
\!\!
\begin{bmatrix}
\textrm{ ---}\!\! & \hat{e}_{1}  &  \!\!\textrm{--- } \\
& \vdots &  \\
\textrm{ ---}\!\! & \hat{e}_{n} & \!\!\textrm{--- } 
\end{bmatrix}\!\!.](./images/80b52bfb58c0354a3430f77aa01b0a33d52ebfe6.png)

The key advantage of using an orthogonal matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) in the diagonalization procedure is that computing its inverse becomes a trivial task: ![O^{-1}=O^\sfT](./images/cddecdde9c2896ba5abef768162e08bbc73b3542.png). The class of normal matrices enjoys a special status by virtue of being diagonalizable by orthogonal matrices.

###[Discussion](./Front matter.md)

####[Non-diagonalizable matrices](./Front matter.md)

Not all matrices are diagonalizable. For example, the matrix

![B=
\begin{bmatrix}
3 & 1 \\
0 & 3
\end{bmatrix}\!](./images/4f97013aa8fcf73d48f5d9c20169f47c750ce957.png)

has ![\lambda = 3](./images/39fd32df799322fb70d18944ebfb72296088b911.png) as a repeated eigenvalue, but the null space of the matrix ![(B-3\mathbbm{1})](./images/dcb93ee880165501e6f794bc22eecab273c2053a.png) contains only one eigenvector: ![(1,0)^\sfT](./images/739d3ab405159af8f10bf884a0fc5b87f1ac69a1.png). The matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) has a single eigenvector in the eigenspace ![\lambda=3](./images/39fd32df799322fb70d18944ebfb72296088b911.png). To describe this situation using precise mathematical terminology, we say the _algebraic multiplicity_ of the eigenvalue ![\lambda=3](./images/39fd32df799322fb70d18944ebfb72296088b911.png) is two, but the _geometric multiplicity_ of the eigenvalue is one.

The matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is a ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix with a single eigenvector. Since we’re one eigenvector short, we can’t construct the diagonalizing change-of-basis matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png). We say the matrix has _deficient_ geometric multiplicity, meaning it doesn’t have a full set of eigenvectors. Therefore, ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) is not diagonalizable.

####[Matrix power series](./Front matter.md)

One of the most useful concepts of calculus is the idea that functions can be represented as Taylor series. The Taylor series of the exponential function ![f(x) =e^x](./images/3704a9cf958891c36dac3de35e7f355a1e45465a.png) is

![e^x 		\; = \; 	\sum_{k=0}^\infty \frac{x^k}{k!} 
\; = \; 	1 + x + \frac{x^2}{2} + \frac{x^3}{3!} + \frac{x^4}{4!} + \frac{x^5}{5!} + \cdots.](./images/d8cafc93d9c5bac9bf1f019b28e29545c2b497e6.png)

Nothing stops us from using the same Taylor series expression to define the exponential function of a matrix:

![e^A   	\; = \; 	\sum_{k=0}^\infty \frac{A^k}{k!}  
\; = \;  	1 + A + \frac{A^2}{2} + \frac{A^3}{3!} + \frac{A^4}{4!} + \frac{A^5}{5!} + \cdots .](./images/6fb7fbbc2a0b4d3bc6c16928a3c50ae14f607088.png)

Okay, there _is_ one thing stopping us—we need to compute an infinite sum of progressively larger matrix powers. Remember how we used the diagonalization of ![A=Q\Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png) to write ![A^{77}](./images/0fe65358d742dc70ca37552a3a8976c2b7da2a57.png) as ![Q\Lambda^{77} Q^{-1}](./images/259bf2cfc0aee0dcbedaf0564f7ee6e7b23b9cd5.png)? We can apply that trick here to obtain the exponential of a matrix in a much simpler form:

![\begin{align*}
e^A  
& 	= \sum_{k=0}^\infty \frac{A^k}{k!}  
= \sum_{k=0}^\infty \frac{(Q\Lambda Q^{-1})^k}{k!} 			\\
& 	= \sum_{k=0}^\infty \frac{Q\:\Lambda^k\:Q^{-1} }{k!}  			\\
&  	=  Q\left[ \sum_{k=0}^\infty \frac{ \Lambda^k }{k!}\right]Q^{-1}  	\\
& 	= Q\left( 1 + \Lambda 
+ \frac{\Lambda^2}{2} + \frac{\Lambda^3}{3!} 
+ \frac{\Lambda^4}{4!} + \ldots \right)Q^{-1} 			\\
& 	= Qe^\Lambda Q^{-1} 								\\
&	= 
\begin{bmatrix}
\; \\
\; \; \; \; \; \; Q \;  \; \; \; \; \; \;  \\
\; 
\end{bmatrix}
\!\!\!
\begin{bmatrix}
e^{\lambda_1}	&  \cdots  &  0 \\
\vdots 	&  \ddots  &  0  \\
0  	&   0      &  e^{\lambda_n}
\end{bmatrix}
\!\!\!
\begin{bmatrix}
\; \\
\; \; \; \; \; \; Q^{-1} \; \; \; \; \; \;  \\
\; 
\end{bmatrix}\!.
\end{align*}](../Images/10103bdc2c3ab27bea296a8ac53c5828f35aae10.png)

We can use this approach to define “matrix functions” of the form

![F: \mathbb{R}^{n \times n} \; \to \; \mathbb{R}^{n \times n}](./images/45ad85721ef4aa0f015d86ae1976e06fb51e5d19.png)

as Taylor series of matrices. Computing the matrix function ![F(A)](./images/d8ba28920866dace58e91b2efbf0cd49ee49975a.png) on an input matrix ![A=Q\Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png) is equivalent to computing the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) of each of the eigenvalues of the matrix: ![F(A)=Q\:f(\Lambda)\:Q^{-1}](./images/a2d20bb4070402edd50838c52f2e9f6c61c6d370.png).

####[Review](./Front matter.md)

We learned how to decompose matrices in terms of their eigenvalues and eigenvectors. The fundamental equation is ![A\vec{e}_{\lambda} = \lambda\vec{e}_{\lambda}](./images/cfe8c47b5c3a090a9c8a01b061c9978c66ea6c32.png), where the vector ![\vec{e}_{\lambda}](./images/75eb683d215d8a51d7d8530263bae9361734ca92.png) is an _eigenvector_ of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), and the number ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png) is an _eigenvalue_ of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

The characteristic polynomial is derived from a simple manipulation of the eigenvalue equation:

![\begin{align*}
A\vec{e}_{\lambda} 							& = \lambda\vec{e}_{\lambda} \\
A\vec{e}_{\lambda} - \lambda \vec{e}_{\lambda} 	& = 0 \\
(A-{\lambda} \mathbbm{1})\vec{e}_{\lambda} 		& = 0.
\end{align*}](./images/d00e2ca2a0e9b76d4a20d9955993b8db362a378f.png)

For this equation to be satisfied, the vector ![\vec{e}_\lambda](./images/75eb683d215d8a51d7d8530263bae9361734ca92.png) must be in the _null space_ of ![(A-\lambda \mathbbm{1})](./images/fb1c5c0f10461cd049357a5fec23697aee17b493.png). The problem of finding the eigenvalues reduces to finding the values of ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png) for which the matrix ![(A-\lambda \mathbbm{1})](./images/fb1c5c0f10461cd049357a5fec23697aee17b493.png) has a non-empty null space. Recall that a matrix has a non-empty null space if and only if it is not invertible. The easiest way to check if a matrix is invertible is to compute the determinant: ![|A-\lambda \mathbbm{1}| = 0](./images/bdd4f63be3d98329f31538d06f03db940d58bd2f.png).

Because multiple eigenvalues and eigenvectors may satisfy this equation, we keep a list of eigenvalues ![(\lambda_1, \lambda_2, \ldots, \lambda_n )](./images/54345aafb30ff145fadde40cf4355a25f4b5235a.png) and corresponding eigenvectors ![\{ \vec{e}_{\lambda_1}, \vec{e}_{\lambda_2}, \ldots \}](./images/08de2c699bce3b6c023ea6253325b365a588ea8d.png). The eigendecomposition of the matrix is ![A=Q\Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png), where ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) is the matrix with eigenvectors as columns, and ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) contains the eigenvalues on the diagonal.

###[Applications](./Front matter.md)

Many scientific methods use the eigendecomposition of a matrix as a building block. For instance:

-   In statistics, the _principal component analysis_ technique aims to uncover the dominant cause of the variation in datasets by eigendecomposing the _covariance matrix_—a matrix computed from the dataset.
-   Google’s original PageRank algorithm for ranking webpages by “importance” can be explained as the search for an eigenvector of a matrix. The matrix contains information about all the hyperlinks that exist between webpages (see[Section 8.1.15](./Chapter 8_ Probability theory.md)).
-   In quantum mechanics, the energy of a system is described by the Hamiltonian operator. The eigenvalues of the Hamiltonian are the possible energy levels the system can have.

Analyzing a matrix in terms of its eigenvalues and its eigenvectors is a powerful technique to “see inside” a matrix and understand what the matrix does. In the next section, we’ll analyze several different types of matrices and discuss their properties in terms of their eigenvalues.

###[Links](./Front matter.md)

\[ Good visual examples of eigenvectors from Wikipedia \]

[`http://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors`](./Eigenvalues_and_eigenvectors.md)

\[ Eigenvectors and eigenvalues explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=PFDu9oVAE-g`](./watch_v=PFDu9oVAE-g.md)

###[Exercises](./Front matter.md)

E6.1 Find the characteristic polynomial and the eigenvalues of each of the following matrices:

1.  ![\begin{bmatrix}
    10	&	-9 \\
    4	&	-2
    \end{bmatrix}](./images/8356d8c962b16e53361dec5dc8aba1c71e03c750.png)
2.  ![\begin{bmatrix}
    1  &2  \\
    4  &3
    \end{bmatrix}](./images/4147636748e360563b788d685a78bec507bb03b7.png)
3.  ![\begin{bmatrix}
    0  &3  \\
    7 &0
    \end{bmatrix}](./images/0bd00563a2c111ada8518963934e03c78efc33f3.png)
4.  ![\begin{bmatrix}
    0  &0  \\
    0  &0
    \end{bmatrix}](./images/1a69f68503ef9398455a6334e99284a54e820c57.png)
5.  ![\begin{bmatrix}
    1  &0  \\
    0  &1
    \end{bmatrix}](./images/90d8ae2f9fdd385dedd57bb509fc2d96d82e7955.png)

E6.2 Find the characteristic polynomial, the eigenvalues, and the eigenvectors of the matrix:

![A =
\begin{bmatrix}
3	&-2 	&0  \\
-2	&3  	&0  \\
0	&0  	&5
\end{bmatrix}.](./images/9ebc6dd0a5af7aa08632a82614d17a244f122fe2.png)

E6.3 Suppose ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is a ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix with two distinct eigenvalues, ![\lambda_1](./images/8c8067d72e5c67f01fd0e636d444f0dd5010b26f.png) and ![\lambda_2](./images/513506b4f306a5400f9b870a2a4241599b77a126.png). Prove that the eigenvectors that correspond to the different eigenvalues are linearly independent.

E6.4 Let ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png) be an eigenvalue of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and let ![\vec{e}_\lambda](./images/75eb683d215d8a51d7d8530263bae9361734ca92.png) be the corresponding eigenvector. Show that ![\lambda^2](./images/13069c0552a0905844cbbe0fbf721a7be806c9eb.png) is an eigenvalue of ![A^2](./images/a0d61abbc27f436fbb804c112345805d7ce3a569.png).

E6.5 Suppose ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png) is an eigenvalue of the invertible matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) with corresponding eigenvector ![\vec{e}_\lambda](./images/75eb683d215d8a51d7d8530263bae9361734ca92.png). Show that ![\lambda^{-1}](./images/4b9268941a2cf49a945d5c83b0c7b48b94c022e0.png) is an eigenvalue of the inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png).

E6.6 Find the values of ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) so the matrix ![A = \begin{bmatrix} 0 & \alpha \\ 1 & \beta \end{bmatrix}](./images/77d2618766f05b93be07999f1970331e733eb344.png) will have eigenvalues ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) and ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png).

E6.7 Consider the matrix ![L=\begin{bmatrix} 3 & 2 \\ 4 & 1 \end{bmatrix}](./images/9d5d9ae0b860fc73153cad690309dc4d64908915.png). Which of the following vectors are eigenvectors of ![L](./images/8344682567e06566040f4cde165f91b06c4ee6f5.png)?

![\colvec{1 \\	1}, \qquad
\colvec{1 \\ 	-1}, \qquad
\colvec{1 \\	-2}, \qquad
\colvec{2 \\ 	-1}.](./images/b8e52ae73aa19700fb65483ae7c8614d6b1421a8.png)

##[6.2 Special types of matrices](./Chapter 6_ Theoretical linear algebra.md)

Mathematicians just love to categorize things. Conveniently for us, they’ve categorized certain types of matrices. Rather than embarking on a verbose explanation of the properties of a matrix, such as

  I have this matrix A whose rows are perpendicular vectors and 
  when you multiply any vector by this matrix it doesn't change 
  the length of the vector but just kind of rotates it---
	

it’s much simpler to refer to the categorization by saying,

   Let A be an orthogonal matrix.
	

Most advanced science textbooks and research papers routinely use terminology like “diagonal matrix,” “symmetric matrix,” and “orthogonal matrix,” so make sure you’re familiar with these concepts.

This section will also review and reinforce what we learned about linear transformations. Recall that we can think of the matrix-vector product ![A\vec{x}](./images/1013646b0165a8b1f4e2bcaca5e29639cc92eae1.png) as applying a linear transformation ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png) to an input vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png). Therefore, each of the special matrices discussed here also corresponds to a special type of linear transformation. Keep this dual correspondence in mind because we’ll use the same terminology to describe matrices _and_ linear transformations.

###[Notation](./Front matter.md)

-   ![\mathbb{R}^{m \times n}](./images/e0107482dfd257822ffe0115cf94429a3196e6c5.png): the set of ![m \times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrices
-   ![A,B,C,O,P,Q,\ldots](./images/e74d72ce173f41a7ab8904f2e4c90c5dcab8f58b.png): typical names for matrices
-   ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png): the entry in the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th row and ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th column of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)
-   ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png): the transpose of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)
-   ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png): the inverse of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)
-   ![\lambda_1, \lambda_2, \ldots](./images/c806e5477a0e117da6d104c717e82e9b2a4971c2.png): the _eigenvalues_ of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). For each eigenvalue ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png) there is at least one associated _eigenvector_ ![\vec{e}_{\lambda_i}](./images/93c5fcf398fb33ead2faff86020d9fefdfdcb678.png) that obeys the equation ![A\vec{e}_{\lambda_i} = \lambda_i \vec{e}_{\lambda_i}](./images/135b9fb0084d224519e9eba97275b2d764b9edae.png). Multiplying the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by its eigenvectors ![\vec{e}_{\lambda_i}](./images/93c5fcf398fb33ead2faff86020d9fefdfdcb678.png) is the same as scaling ![\vec{e}_{\lambda_i}](./images/93c5fcf398fb33ead2faff86020d9fefdfdcb678.png) by ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png).

###[Diagonal matrices](./Front matter.md)

Diagonal matrices contain entries on the diagonal and zeros everywhere else. For example:

![A = 
\begin{bmatrix}
a_{11}	& 	0		& 0 		\\
0		& 	a_{22}	& 0 		\\
0		& 	0 		& a_{33}
\end{bmatrix}\!.](./images/f1b2410c0ee7c7d3595211902407fc829706213d.png)

A diagonal matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) satisfies ![a_{ij}=0, \text{if } i\neq j](./images/dd5c8b68d201a02b8769267aba6ce41ccf3af4bd.png). The eigenvalues of a diagonal matrix are ![\lambda_i = a_{ii}](./images/73361205e005bba8a8996365bba8186788e272b2.png).

###[Symmetric matrices](./Front matter.md)

A matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is symmetric if and only if

![A^\sfT = A, \quad \textrm{or equivalently if} \quad a_{ij} = a_{ji}, \text{ for all } i,j.](./images/d9f916e2ea4c910d7da26ca1ae66fcc1145b5abf.png)

The eigenvalues of symmetric matrices are real numbers, and the eigenvectors can be chosen to be mutually orthogonal.

Given any matrix ![B\in\mathbb{R}^{m \times n}](./images/3c88c8becc49bd444f9d20d7192dc667616c9608.png), the product of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) with its transpose ![B^\sfT B](./images/653ecc1386ea585efeab2bff352a44e121356ce5.png) is always a symmetric matrix.

###[Upper triangular matrices](./Front matter.md)

Upper triangular matrices have zero entries below the main diagonal:

![\begin{bmatrix}
a_{11}	& a_{12}	& a_{13} \\
0		& a_{22}	& a_{23} \\
0		& 0 		& a_{33}
\end{bmatrix},
\qquad
a_{ij}=0, \quad \text{if } i > j.](./images/468dfe17f383b46f6984cb43875d970ccf35f8e6.png)

For a _lower_ triangular matrix, all the entries _above_ the diagonal are zeros: ![a_{ij}=0, \text{if } i < j](./images/29e69657aac4dd9f7e0b9a8fccc3cfbf888cbbb3.png).

###[Identity matrix](./Front matter.md)

The identity matrix is denoted ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) or ![\mathbbm{1}_n \in \mathbb{R}^{n \times n}](./images/931d0f291e361772341367d23afa7be360dd21ca.png) and plays the role of multiplication by the number ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) for matrices: ![\mathbbm{1}A=A\mathbbm{1}=A](./images/2ea7a72d8d40155bfd804b0b7763bb4f9ee9c14e.png). The identity matrix is diagonal with ones on the diagonal:

![\mathbbm{1}_3 = 
\begin{bmatrix}
1	& 0	& 0 \\
0	& 1 	& 0 \\
0	& 0 	& 1
\end{bmatrix}\!.](./images/899f18e6622abc9b8d2f5a32bb2e5fd5f5a284ef.png)

Any vector ![\vec{v} \in \mathbb{R}^3](./images/7d4d76835dd377bbd6d7248bd9e3aa55aa35fdfa.png) is an eigenvector of the identity matrix with eigenvalue ![\lambda = 1](./images/80fc8bed47c96f557f144e0985441a990951940c.png).

###[Orthogonal matrices](./Front matter.md)

A matrix ![O \in \mathbb{R}^{n \times n}](./images/20d43cef44f07c3047e03eedc348663ed9955f8d.png) is _orthogonal_ if it satisfies ![OO^\sfT=\mathbbm{1}=O^\sfT O](./images/460b71739ec3bee2e81eba7bd0052320e6eeb181.png). In other words, the inverse of an orthogonal matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is obtained by taking its transpose: ![O^{-1} =  O^\sfT](./images/cddecdde9c2896ba5abef768162e08bbc73b3542.png).

**Multiplication by an orthogonal matrix preserves lengths**. Consider the matrix-vector product ![O\vec{v}=\vec{w}](./images/464ae26b5ecb5912f9f357d391ed5d2692b12638.png). The length of a vector before the multiplication is ![\|\vec{v}\|=\sqrt{ \vec{v} \cdot \vec{v} }](./images/0d134125afc497e97a27eba5d9c67c6208984818.png). The length of a vector after the multiplication is

![\|\vec{w}\|
= \sqrt{ \vec{w} \cdot \vec{w} }
= \sqrt{ (O\vec{v})^\sfT(O\vec{v}) }
= \sqrt{ \vec{v}^\sfT O^\sfT O\vec{v} }.](./images/be731d8d1d8f7fb5a6b7f1502f643a667abc5c70.png)

The second equality follows from the interpretation of the dot product as a matrix product ![\vec{u} \cdot \vec{v} = \vec{u}^\sfT\vec{v}](./images/0706e38fb1eecc10212ced24a34cf3862121f82c.png). The third equality follows from the properties of matrix transpose ![(AB)^\sfT = B^\sfT A^\sfT](./images/c898f120bdbcebcebf1f51640d922b0861c7191e.png).

When ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is an orthogonal matrix, we can substitute ![O^\sfT O=\mathbbm{1}](./images/4f6851492efed417c5e16f7e04619f1289b89914.png) in the above expression to establish ![\|\vec{w}\|= \sqrt{ \vec{v}^\sfT \mathbbm{1} \vec{v} } =\|\vec{v}\|](./images/534da22a57c4d0a66b70baa46d68b2bd2495e007.png), which shows that multiplication by an orthogonal matrix is a _length preserving_ operation.

The eigenvalues of an orthogonal matrix have _unit_ length, but can in general be complex numbers ![\lambda=e^{i\theta} \in \mathbb{C}](./images/95bd607affd81843fe5c097b6313a9583be1c945.png). The determinant of an orthogonal matrix is either one or negative one ![|O|\in\{-1,1\}](./images/26a1fed0ff7fa2f37f566a25cf9396f4a9fafd9e.png).

You can visualize orthogonal matrices by thinking of their columns as a set of vectors that form an orthonormal basis for ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png):

![O =
\begin{bmatrix}
\vert  &  & \vert \\
\hat{e}_{1}  &  \cdots &  \hat{e}_{n} \\
\vert  &  & \vert 
\end{bmatrix}
\quad
\textrm{such that}
\quad
\hat{e}_{i} \cdot \hat{e}_{j} = 
\left\{ \begin{array}{ll} 
1 	& \text{ if } i =j, \\
0	& \text{ if } i \neq j.
\end{array}\right.](./images/66d5c6136fa1ddf83896dbd0f63e23b7142a9a6e.png)

You can verify the matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is orthogonal by computing ![O^\sfT O=\mathbbm{1}](./images/4f6851492efed417c5e16f7e04619f1289b89914.png). The orthogonal matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is a change-of-basis matrix from the standard basis to the column basis ![\{ \hat{e}_1,\hat{e}_2,\ldots, \hat{e}_n \}](./images/0bfc670a2906a6a127fa62f32efbfdb9754d60e2.png).

Everything stated above about multiplication by an orthogonal matrix also applies to orthogonal transformations ![T_O:\mathbb{R}^n\to\mathbb{R}^n](./images/6b79b6dcda069ba9b02b2d36f43fa29e66b7692c.png) because of the equivalence ![O\vec{v}=\vec{w} \; \Leftrightarrow \; T_O(\vec{v})=\vec{w}](./images/e1695cb0b7f65c2c32ab71ec0744df276e05a957.png).

The set of orthogonal matrices contains three special cases: _rotations_ matrices, _reflection_ matrices, and _permutation_ matrices.

####[Rotation matrices](./Front matter.md)

A rotation matrix takes the standard basis ![\{ \hat{\imath}, \hat{\jmath}, \hat{k} \}](./images/20a783ec4e2fb4e61cdda060b7be04e1c1bd2022.png) to a rotated basis ![\{ \hat{e}_1,\hat{e}_2,\hat{e}_3 \}](./images/c2bcd6a22c91fbce431e53813ab74cdf932e39ff.png). Consider an example in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png). The counterclockwise rotation by the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is given by the matrix

![R_\theta =
\begin{bmatrix}
\cos\theta	&-\sin\theta \\
\sin\theta	&\cos\theta
\end{bmatrix}\!.](./images/dacc0b48a965a1de7c0db3aaff840f90d58ef581.png)

The matrix ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) takes ![\hat{\imath}=(1,0)^\sfT](./images/7abf849dcb1ea1d0519e31988c8b8eb72c0d72e9.png) to ![(\cos\theta,\sin\theta)^\sfT](./images/dc60052f0a36696052134bc356484af0e2f70e7d.png), and ![\hat{\jmath}=(0,1)^\sfT](./images/ad9b1ca61ac6bd26422a4aeb788f6d2075638bdf.png) to ![(-\sin\theta,\cos\theta)^\sfT](./images/4425fbffb395a2f18340b711f749494102e4eb54.png).

As another example, consider the rotation by the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) around the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png):

![\begin{bmatrix}
1&0&0\\
0&\cos\theta&-\sin\theta\\
0&\sin\theta&\cos\theta
\end{bmatrix}\!.](./images/883056311b601f81130f11158cc9b8f7c945e509.png)

This rotation is entirely in the ![yz](./images/3b2d62155811a68db2e68ec06f60c29d76a6e177.png)\-plane, so the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-component of a vector multiplying this matrix remains unchanged.

The determinant of a rotation matrix is equal to one. The eigenvalues of rotation matrices are complex numbers with unit magnitude.

####[Reflections](./Front matter.md)

If the determinant of an orthogonal matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is equal to negative one, we say it is _mirrored orthogonal_. For example, the reflection through the line with direction vector ![(\cos\theta, \sin\theta)](./images/a3582a5b7e99b628756ef1371b95ec1431bffa38.png) is given by:

![R=
\begin{bmatrix}
\cos(2\theta) &\sin(2\theta)\\
\sin(2\theta) &-\cos(2\theta)
\end{bmatrix}.](./images/4ae186239058f5f3802f0699e7e83813700c81c6.png)

A reflection matrix always has at least one eigenvalue equal to negative one, which corresponds to the direction perpendicular to the axis of reflection.

####[Permutation matrices](./Front matter.md)

Permutation matrices are another important class of orthogonal matrices. The action of a permutation matrix is simply to change the _order_ of the vector components. For example, the permutation ![\pi: \hat{e}_1 \to \hat{e}^\prime_1](./images/61753dc6701723e162001d7ef97306c271b37f9a.png), ![\hat{e}_2 \to \hat{e}^\prime_3](./images/e028c27e965773972bf0419200576045e3e12389.png), ![\hat{e}_3 \to \hat{e}^\prime_2](./images/8bb13e6b013149ab83c4c38107e82f7863048c67.png) can be represented as the matrix

![M_\pi
=
\begin{bmatrix}
1 & 0 & 0 \\
0 & 0 & 1 \\
0 & 1 & 0
\end{bmatrix}.](./images/4cd97816799d02377405f69f65f98681ae9acfdc.png)

An ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) permutation matrix contains ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) ones in ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) different columns and zeros everywhere else.

The _sign_ of a permutation corresponds to the determinant ![\det(M_\pi)](./images/7e6d271703b3149efe5406f28a869b301025be47.png). We say that permutation ![\pi](./images/656d98b0b8757268a556f19292f717b6532a03d0.png) is _even_ if ![\det(M_\pi) = +1](./images/de75851a6d42a3be8d67af8c34c5108c80c02aed.png) and _odd_ if ![\det(M_\pi) = -1](./images/d61e098a3fe1fe3fcf03a1923b03f593b886adec.png).

###[Positive matrices](./Front matter.md)

A matrix ![P \in \mathbb{R}^{n \times n}](./images/1c8dec7a187408a4d3c91ae46a70e337c083f406.png) is _positive semidefinite_ if

![\vec{v}^\sfT P \vec{v} \geq 0
\quad
\textrm{for all } \vec{v} \in \mathbb{R}^n.](./images/936d38f56be9d6ec9b0d314b8324d921d8975bbc.png)

The eigenvalues of a positive semidefinite matrix are all nonnegative ![\lambda_i \geq 0](./images/0425de4c0a18ea0a98d3c7889fc9034e3f696b0b.png).

If instead the matrix ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) obeys the strict inequality ![\vec{v}^\sfT P \vec{v} > 0](./images/b09ea38c9dfefcdebb6855dceccd8068a9a10c36.png) for all ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png), we say the matrix ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) is _positive definite_. The eigenvalues of positive definite matrices are strictly greater than zero ![\lambda_i >  0](./images/391b7372bcd58800408b954ceb96d87e73a2ec07.png).

###[Projection matrices](./Front matter.md)

The defining property of a projection matrix is that it can be applied multiple times without changing the result:

![\Pi = \Pi^2= \Pi^3= \Pi^4= \Pi^5 = \cdots.](./images/d20e1dffd607b14abd14c92566287332275aca29.png)

A projection has two eigenvalues: one and zero. The space ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) that is left invariant by the projection ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png) corresponds to the eigenvalue ![\lambda=1](./images/80fc8bed47c96f557f144e0985441a990951940c.png). The orthogonal complement ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) corresponds to the eigenvalue ![\lambda=0](./images/10934b7194187c81748d1850a1ebd06584c5a07b.png) and consists of vectors that get annihilated by ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png). The space ![S^\perp](./images/a799731c8a7e2ccc968ffd6c820166b8c4fb1576.png) is the null space of ![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png).

###[Normal matrices](./Front matter.md)

The matrix ![A = \mathbb{R}^{n \times n}](./images/29d267d4d3bcafb13a9311643120587d38daabbb.png) is _normal_ if it obeys ![A^\sfT A=AA^\sfT](./images/063f9caebb88f2bc873e9efb8620bf9229fc6b63.png). If ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is normal, it has the following properties:

-   ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is an eigenvector of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) if and only if ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is an eigenvector of ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png).
-   For all vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) and ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png) and a normal transformation ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), we have
    
    ![(A\vec{v}) \!\cdot\! (A\vec{w})
    = (A\vec{v})^{\!\sfT} \!(A\vec{w})
    = \vec{v}^\sfT \! A^{\!\sfT} \!A\vec{w}
    = \vec{v}^\sfT \!A A^{\!\sfT} \vec{w}
    = (A^{\!\sfT} \vec{v}) \!\cdot\! (A^{\!\sfT} \vec{w}).](./images/b9cf33a7c8f5483a49162a4de3c0576f6e78cc7b.png)
    
-   The matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has a full set of linearly independent eigenvectors. Eigenvectors corresponding to distinct eigenvalues are orthogonal, and eigenvectors from the same eigenspace can be chosen to be mutually orthogonal.

Every normal matrix is diagonalizable by an orthogonal matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png). The eigendecomposition of a normal matrix is written as ![A = O\Lambda O^\sfT](./images/5fb620b0c1b0c45951af03774a36b6c5267fb2f9.png), where ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) is orthogonal and ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) is diagonal.

Orthogonal (![O^\sfT O=\mathbbm{1}](./images/4f6851492efed417c5e16f7e04619f1289b89914.png)) and symmetric (![A^\sfT=A](./images/4fb1743063e84bb6a2e3112affa915367e3e1d54.png)) matrices are normal matrices, since ![O^\sfT O=\mathbbm{1}=OO^\sfT](./images/e8a84cd920784516a673ffbfb29571100af47b22.png) and ![A^\sfT A=A^2=AA^\sfT](./images/e8d950a934e9ad41d056d9e0cbaa0ecd8a7868b7.png).

![special_types_of_matrices](./images/special_types_of_matrices.jpg)

Figure 6.1: This concept map illustrates the connections and relations between special types of matrices. We can understand matrices through the constraint imposed on their eigenvalues or their determinants. This diagram shows only a subset of the many connections between the different types of matrices. We’ll discuss matrices with complex entries in[Section 6.7](./Chapter 6_ Theoretical linear algebra.md).

###[Discussion](./Front matter.md)

We’ve defined several special categories of matrices and described their properties. You’re now equipped with some very precise terminology for describing different types of matrices. Each of these special matrices plays a role in certain applications.

This section also highlighted the importance of the eigenvalue description of matrices. Indeed, we can understand all special matrices in terms of the constraints imposed on their eigenvalues. The concept map in[Figure 6.1](./Chapter 6_ Theoretical linear algebra.md) summarizes the relationships between the different special types of matrices. The map also refers to _unitary_ and _Hermitian_ matrices, which extend the concepts of _orthogonal_ and _symmetric_ matrices to describe matrices with complex entries.

###[Exercises](./Front matter.md)

E6.8 Find the determinants and inverses of these triangular matrices:

![A = 
\begin{bmatrix}
1 & 4 & 15 \\
0 & 5 & 5 \\
0 & 0 & 3
\end{bmatrix},
\qquad
B = 
\begin{bmatrix}
x & 0		\\ 
y & z
\end{bmatrix},
\qquad
C = 
\begin{bmatrix}
\frac{1}{5} & 0	\\
0		& 5 
\end{bmatrix}.](./images/74273e6c6552a14ffad4b4fadfb8bd7009c85ea5.png)

E6.9 Is the matrix ![\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}](./images/dff55c55c70ca6cc3146fa1cf038c38272c102c3.png) symmetric?

E6.10 In this section we learned about different types of matrices: diagonal, triangular, positive (semi)definite, symmetric, and orthogonal matrices. What types of matrices are these?

1.  ![A\!=\!\!\begin{bmatrix} 1 & 2 & 3\\ 0 & 4 & 1\\ 0 & 0 & 7 \end{bmatrix}](./images/1c86a8e3235798582d1f9093543f5cceab9682b4.png)
2.  ![B\!=\!\!\begin{bmatrix}\frac{1}{\sqrt{2}}	& \frac{1}{\sqrt{6}}	& 	\frac{1}{\sqrt{3}} 	\\
    \frac{1}{\sqrt{2}}		& - \frac{1}{\sqrt{6}}	&	-\frac{1}{\sqrt{3}}		\\
    0				& \frac{2}{\sqrt{6}} 	& 	-\frac{1}{\sqrt{3}}\end{bmatrix}](./images/13a91c94f4f3e16031ea769cf68635e1910050dc.png)
3.  ![C\!=\!\!\begin{bmatrix}0 & 1 & 0\\ 1 & 0 & 0\\ 0 & 0 & 1\end{bmatrix}](./images/e0eb562199938c054eb82792e9c7f1a9954348fc.png)

Compute the matrices’ eigenvalues to analyse their properties.

##[6.3 Abstract vector spaces](./Chapter 6_ Theoretical linear algebra.md)

You can apply your knowledge of vectors more generally to other vector-like mathematical objects. For example, polynomials behave similarly to vectors. To add two polynomials ![P(x)](./images/d97a3842ab56856ea412215e0ec0b5abca6c623d.png) and ![Q(x)](./images/131d3837ee1bd364fb9ace90534cde3dbf796a79.png), we add together the coefficients of each power of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)—the same way vectors are added component by component.

In this section, we’ll learn how to use the terminology and concepts associated with vectors to study other mathematical objects. In particular, we’ll see that notions such as _linear independence_, _basis_, and _dimension_ can be applied to mathematical objects like matrices, polynomials, and functions. We’ll use the notation ![\mathbf{v}](./images/633b84ab115cc79e0751cfddae6cfadae6fca32b.png) for describing abstract vectors as opposed to the usual ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) used for ordinary vectors.

###[Definitions](./Front matter.md)

An abstract vector space ![(V,F,+,\cdot)](./images/3f96d7df630be29a65d98b3dbcdb12830f78c147.png) consists of four things:

-   A set of vector-like objects ![V=\{\mathbf{u},\mathbf{v},\ldots \}](./images/c0835ccf6e9e3d4a5162f1ef9bd33c349639f6c4.png)
-   A field ![F](./images/fde085937972221cc351ca105835c8b5a11aa591.png) of scalar numbers, usually ![F=\mathbb{R}](./images/4e8ba7f01a2537adb250f8002113eb4d4e9b6a3d.png)
-   An addition operation “![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png)” for elements of ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) that dictates how to add vectors: ![\mathbf{u} + \mathbf{v}](./images/158b3240274a7e53eef419ebc2a96e65a7621de6.png)
-   A scalar multiplication operation “![\cdot](./images/02ca492c3fc32f2bb808f25d16aec9e93a911586.png)” for scaling a vector by an element of the field. Scalar multiplication is usually denoted implicitly ![\alpha \mathbf{u}](./images/407bc14020a58933a01f60ff226584eb33c93fb1.png) (without the dot).

A vector space satisfies the following eight axioms, for all scalars ![\alpha, \beta \in F](./images/cb99a7e9a65a615e0d305c59a92afcf794e30a12.png) and all vectors ![\mathbf{u}, \mathbf{v}, \mathbf{w} \in V](./images/8fd62c8c0ca6fe347979718e661d171cfc6dadf3.png):

1.  ![\mathbf{u} +  (\mathbf{v}+ \mathbf{w}) = (\mathbf{u}+ \mathbf{v}) + \mathbf{w}](./images/379b6bddf287e28d0988acca09be54335ac51cd4.png) (associativity of addition)
2.  ![\mathbf{u} +  \mathbf{v}  = \mathbf{v} +  \mathbf{u}](./images/185701a379539636b6037d2f640344f740ec156b.png) (commutativity of addition)
3.  There exists a zero vector ![\mathbf{0} \in V](./images/a5d0e68776a5a92aec072c27b655777001edde5b.png), such that ![\mathbf{u} +  \mathbf{0} = \mathbf{0} +\mathbf{u} = \mathbf{u}](./images/47f9fc9310d1eb43f9536221dd56a0cf7e728a81.png) for all ![\mathbf{u} \in V](./images/4a869665b21aa2f6eaf354a4c85abc940ed30a7f.png).
4.  For every ![\mathbf{u} \in V](./images/4a869665b21aa2f6eaf354a4c85abc940ed30a7f.png), there exists an inverse element ![-\mathbf{u}](./images/02e66d1d2637e22f8b4107e4aa96fdd27e235ebe.png) such that ![\mathbf{u} +  (-\mathbf{u}) = \mathbf{u} -\mathbf{u} = \mathbf{0}](./images/eab6e98570c7b257bf019dd7b0a8c01cc93541c1.png).
5.  ![\alpha   (\mathbf{u} +  \mathbf{v}) = \alpha  \mathbf{u} +  \alpha \mathbf{v}](./images/12a1f97f7b07f3911a720f738d7c85a7d451008e.png) (distributivity I)
6.  ![(\alpha + \beta)\mathbf{u}= \alpha\mathbf{u} +  \beta\mathbf{u}](./images/e3905e101729190918697a19b7e1e1944793dbbf.png) (distributivity II)
7.  ![\alpha   (\beta  \mathbf{u})= (\alpha\beta) \mathbf{u}](./images/a1817c4e8c862072cebc0d4a1fdc43da43e8d855.png) (associativity of scalar multiplication)
8.  There exists a unit scalar ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) such that ![1 \mathbf{u}= \mathbf{u}](./images/4f605190979d39c9989097cca7e02d5b5e3acfae.png).

If you know anything about vectors, the above properties should be familiar. Indeed, these are the standard properties for the vector space ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png), where the field ![F](./images/fde085937972221cc351ca105835c8b5a11aa591.png) is ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png), and for which standard vector addition and scalar multiplication operations apply.

###[Theory](./Front matter.md)

Believe it or not, we’re actually done with all the theory for this section. Move along folks, there’s nothing more to see here aside from the definitions above—which are restatements of the properties of vector addition and vector scaling that you’ve already seen before.

The only thing left to do is illustrate these concepts through some examples.

###[Examples](./Front matter.md)

Matrices, polynomials, and functions are vector-like math objects. The following examples demonstrate how we can treat these math objects as abstract vector spaces ![(V,F,+,\cdot)](./images/3f96d7df630be29a65d98b3dbcdb12830f78c147.png).

####[Matrices](./Front matter.md)

Consider the vector space of ![m\times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrices over the real numbers ![\mathbb{R}^{m \times n}](./images/e0107482dfd257822ffe0115cf94429a3196e6c5.png). The addition operation for two matrices ![A,B \in \mathbb{R}^{m \times n}](./images/c9d9369f7645d8c79198c0ae0b3f1356a3736057.png) is the usual rule of matrix addition: ![(A+B)_{ij} = a_{ij}+b_{ij}](./images/4d61bcfd39c8d1efe436878e47aae7aa2c25eec9.png).

This vector space is ![mn](./images/c54ad625c4a9152821f885961a53152893c34288.png)\-dimensional, which can be seen by constructing a basis for the space. The standard basis for ![\mathbb{R}^{m \times n}](./images/e0107482dfd257822ffe0115cf94429a3196e6c5.png) consists of ![mn](./images/c54ad625c4a9152821f885961a53152893c34288.png) matrices with zero entries everywhere except for a single ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) in the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th row and the ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th column. Any matrix ![A \in \mathbb{R}^{m \times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png) can be written as a linear combination of the matrices in the standard basis.

#####[Example](./Front matter.md)

The standard basis ![B_{s}](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png) for the vector space ![\mathbb{R}^{2 \times 2}](./images/193cdcbfa6e97118f8f5a662a11df76e2ccb299a.png) is

![\mathbf{e}_1 = 
\begin{bmatrix}
1 & 0 \\
0 & 0 
\end{bmatrix}, \; \; 
\mathbf{e}_2 = 
\begin{bmatrix}
0 & 1 \\
0 & 0 
\end{bmatrix}, \; \; 
\mathbf{e}_3 = 
\begin{bmatrix}
0 & 0 \\
1 & 0 
\end{bmatrix}, \; \; 
\mathbf{e}_4 = 
\begin{bmatrix}
0 & 0 \\
0 & 1 
\end{bmatrix}\!.](./images/3a9e644f01ee04742425bba0e67c459b010058f5.png)

Any matrix ![A \in \mathbb{R}^{2 \times 2}](./images/e953836548ba75da04b70f5d325dd36170f4786b.png) can be written as a linear combination of the vectors in ![B_{s}](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png):

![\begin{align*}
A  = 
\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} 
\end{bmatrix}		
& = 
a_{11}\!
\begin{bmatrix}
1 & 0 \\
0 & 0 
\end{bmatrix}
+
a_{12}\!
\begin{bmatrix}
0 & 1 \\
0 & 0 
\end{bmatrix}
+
a_{21}\!
\begin{bmatrix}
0 & 0 \\
1 & 0 
\end{bmatrix}
+
a_{22}\!
\begin{bmatrix}
0 & 0 \\
0 & 1 
\end{bmatrix}					\\
& = a_{11}\mathbf{e}_1  + a_{12}\mathbf{e}_2 + a_{21}\mathbf{e}_3 + a_{22}\mathbf{e}_4.      
\end{align*}](./images/158fc6713fce1a45efec85c11e0c783a2037dd67.png)

In other words, ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) can be expressed as a vector of coordinates with respect to the basis ![B_{s}](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png): ![A=(a_{11}, a_{12}, a_{21}, a_{22})_{B_{s}}](./images/e8f34fab5330bb9686992f69b06c1c41fb3a14b4.png).

The abstract concept of a matrix ![A \in \mathbb{R}^{2 \times 2}](./images/e953836548ba75da04b70f5d325dd36170f4786b.png) can be expressed as two equivalent representations. We can think of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) either as an array of numbers with two columns and two rows, or as a four-dimensional vector of coordinates with respect to the basis ![B_{s}](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png):

![A
\; = \; 
\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} 
\end{bmatrix}	
\; = \; 
(a_{11}, a_{12}, a_{21}, a_{22})_{\!B_s}.](./images/4a7a47a7868effffd29595a8e8ec7f36c819f7fa.png)

We’ve arrived at a major _knowledge buzz_ milestone: **matrices are vectors!** In precise mathematical terms, we just demonstrated the existence of an _isomorphism_ between the set of ![2\times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrices and the set of four-dimensional vectors. We can add, subtract, and scale ![2\times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrices in their ![\mathbb{R}^4](./images/63147fde7ca40efcdbf48e4b0a82e082577ebd3b.png) representations. In the following exercises, we’ll see how to compute the matrix trace operation ![\textrm{Tr}(A)](./images/5cac703e5885c95d0781a32376aa9d456b4dbeb2.png) in terms of the vector representation.

####[Symmetric 2x2 matrices](./Front matter.md)

Define the vector space consisting of ![2\times2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) symmetric matrices

![\mathbb{S}(2,2) \,\eqdef\, \{ A \in \mathbb{R}^{2 \times 2} \; | \; A = A^\sfT \, \}](./images/fa614c7ce034f18333882e71871c3b99221716f4.png)

in combination with the usual matrix addition and scalar multiplication operations. We obtain an explicit basis for this space as follows:

![\mathbf{v}_1 = 
\begin{bmatrix}
1 & 0 \\
0 & 0 
\end{bmatrix}, \; \; 
\mathbf{v}_2 = 
\begin{bmatrix}
0 & 1 \\
1 & 0 
\end{bmatrix}, \; \; 
\mathbf{v}_3 = 
\begin{bmatrix}
0 & 0 \\
0 & 1 
\end{bmatrix}\!.](./images/66f1bebaaf190ee917a9e2f5292071a916fb6b35.png)

Any element of the vector space ![S \in \mathbb{S}(2,2)](./images/497e6d0cf810484f60d48e7a357f307475a9d7a9.png) can be written as a linear combination of the basis vectors:

![\begin{align*}
S 	\; = \; 
\begin{bmatrix}
a & b \\
b & c 
\end{bmatrix}
\; &= \; 
a
\begin{bmatrix}
1 & 0 \\
0 & 0 
\end{bmatrix}
+
b
\begin{bmatrix}
0 & 1 \\
1 & 0 
\end{bmatrix}
+
c
\begin{bmatrix}
0 & 0 \\
0 & 1 
\end{bmatrix} 						\\
\; &= \; a\mathbf{v}_1 + b\mathbf{v}_2 + c\mathbf{v}_3.
\end{align*}](./images/13709d960df854e57cac97b5c3491f399eccfcac.png)

Since there are three vectors in a basis for ![\mathbb{S}(2,2)](./images/ef308dd930953b3854ec0d47bd900f3309fd725e.png), the vector space ![\mathbb{S}(2,2)](./images/ef308dd930953b3854ec0d47bd900f3309fd725e.png) is three-dimensional.

Note how we count the dimensions in this case. The space of ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrices is four-dimensional in general, but imposing the symmetry constraint ![a_{12}=a_{21}](./images/e2006a5c95a00ced51b64cb6439b944bf4a9af0e.png) eliminates one parameter, so we’re left with a three-dimensional space.

####[Polynomials of degree n](./Front matter.md)

Define the vector space ![P_n(t)](./images/e74d2c6c9aba8411ca9b3f4877b6c8edcfd358d8.png) of polynomials with real coefficients and degree less than or equal to ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png). The “vectors” in this space are polynomials of the form

![\mathbf{p} = a_0 + a_1x + a_2x^2 + \cdots + a_n x^n.](./images/4ebaa4e88c26c4e21255c9bce516d7c7f5623d47.png)

The coefficients of the polynomial ![a_0,a_1,a_2,\ldots,a_n](./images/5d47fdd46ef9539b7cb326a004ff2f667cbbb154.png) are the components of the vector ![\mathbf{p}](./images/8d5c5e9c7c93ad77d3e7eb5a4467d10aeba61dad.png).

The addition of vectors ![\mathbf{p}, \mathbf{q} \in P_n(t)](./images/8659e3778b8ecc24231214cb5b1e6b03f415fb74.png) is performed component-wise:

![\begin{align*}
\mathbf{p} + \mathbf{q}
& =	(a_0+a_1x+\cdots+a_nx^n)+(b_0+b_1x+\cdots+b_nx^n) \\
& =	(a_0+b_0)+(a_1+b_1)x+\cdots +(a_n+b_n)x^n.
\end{align*}](./images/e8d73b57ca4b21d9e95391837e887b6000acbf93.png)

Similarly, scalar multiplication acts as you’d expect:

![\alpha \mathbf{p}
= \alpha\cdot (a_0+a_1x+\ldots a_nx^n)=(\alpha a_0)+(\alpha a_1)x+\ldots (\alpha a_n)x^n.](./images/b8ab79b262416a3cb2b8fc8be7154738fce1fea6.png)

The space ![P_n(x)](./images/064ff86501dba020964c53718619fda009a33f0f.png) is ![(n+1)](./images/1a92a7f301b110623ddd5e73b5c32dda5b55476d.png)\-dimensional since each “vector” in this space has ![n+1](./images/59ddb5062033134e6e2c571f6fdcf91ff1b80567.png) components.

####[Functions](./Front matter.md)

Another interesting vector space is the set of functions ![f:\mathbb{R} \to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png) in combination with the point-wise addition and scalar multiplication operations:

![\mathbf{f}+\mathbf{g} =(f+g)(x) = f(x) + g(x),
\qquad
\alpha\mathbf{f} = (\alpha f)(x) = \alpha f(x).](./images/75f0ba374eeb2a1544b1fa4a1d8a4a276e127511.png)

The space of functions is _infinite_\-dimensional.

###[Discussion](./Front matter.md)

We’ve talked about bases, components, and dimensions of _abstract_ vector spaces. Indeed, these notions are well-defined for any vector-like object. Though this section only discussed vector spaces with real components, we can apply the same techniques to vectors with components from any _field_. The notion of a _field_ describes any number-like object for which the operations of addition, subtraction, multiplication, and division are defined. An example of another field is the set of complex numbers ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png). We’ll discuss the linear algebra of vectors with complex components in[Section 6.7](./Chapter 6_ Theoretical linear algebra.md).

In the next section, we’ll define an _abstract inner product_ operation and use this definition to discuss concepts like orthogonality, length, and distance in abstract vector spaces.

###[Links](./Front matter.md)

\[ Further discussion and examples on Wikipedia \]

[`http://en.wikipedia.org/wiki/Vector_space`](./Vector_space.md)

\[ Examples of vector spaces \]

[`http://wikibooks.org/wiki/Linear_Algebra/Definition_and_Examples_of_Vector_Spaces`](./Definition_and_Examples_of_Vector_Spaces.md)

\[ Abstract vector spaces explained by 3Blue1Brown \]

[`https://youtube.com/watch?v=TgKwz5Ikpc8`](./watch_v=TgKwz5Ikpc8.md)

###[Exercises](./Front matter.md)

E6.11 Find a basis for the space of ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) upper triangular matrices.

E6.12 Can every polynomial of degree at most two be written in the form ![\alpha + \beta (x-1) + \gamma (x-1)^2](./images/2c68a05a943df4d8c7f6d2414014cb598e8b3ec4.png)?

Try to express an arbitrary polynomial in this form.

##[6.4 Abstract inner product spaces](./Chapter 6_ Theoretical linear algebra.md)

An inner product space is an abstract vector space ![(V,\mathbb{R},+,\cdot)](./images/313330e93218147f3e2906b573cc90e81ca0ef18.png) for which we define an _abstract inner product_ operation that takes pairs of vectors as inputs and produces numbers as outputs:

![\langle \cdot, \cdot \rangle : V \times V \to \mathbb{R}.](./images/25c36d68f8c4f71f423296c7934108895a415e5f.png)

We can use any inner product operation, as long as it satisfies the following criteria for all ![\mathbf{u}, \mathbf{v}, \mathbf{v}_1,\mathbf{v}_2\in V](./images/f4d27939cc9841954ef9af00ec12715497bb35d9.png) and ![\alpha,\beta \in \mathbb{R}](./images/d3db62d29b143a5aceb076e151fa6666f7ffaeaa.png). The inner product operation must be:

-   Symmetric: ![\langle \mathbf{u},\mathbf{v}\rangle =\langle \mathbf{v},\mathbf{u}\rangle](./images/886a2a574e4c04b3d4ccd726e7098c778e30fc53.png)
-   Linear: ![\langle \mathbf{u},\alpha\mathbf{v}_1+\beta\mathbf{v}_2\rangle 
    =\alpha\langle \mathbf{u},\mathbf{v}_1\rangle +\beta\langle \mathbf{u},\mathbf{v}_2\rangle](./images/0adc800ef7f5b95fdc1029811440681c02b604fd.png)
-   Positive semidefinite: ![\langle \mathbf{u},\mathbf{u}\rangle \geq0](./images/707648c85a9c6015f87ff0170869c03c7c9415c7.png) for all ![\mathbf{u}\in V](./images/4a869665b21aa2f6eaf354a4c85abc940ed30a7f.png) with ![\langle \mathbf{u},\mathbf{u}\rangle =0](./images/321add528a9e6b050992a9633f9447d7150a6fee.png) if and only if ![\mathbf{u}=\mathbf{0}](./images/eb1e1fb3fa4e081fcea8eb478d7b220840dd23f5.png)

These criteria are inspired by the properties of the standard inner product (dot product) for vectors in ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png):

![\langle \vec{u}, \vec{v}\rangle = \vec{u} \cdot \vec{v} = \sum_{i=1}^n u_i v_i = \vec{u}^\sfT \vec{v}.](./images/8bea611aa997c58093bc1083997b83ec8191567c.png)

In this section, we’ll extend the idea of the dot product by defining inner product operations ![\langle \mathbf{u},\mathbf{v}\rangle](./images/3b9ee96b30fdf71f77bac471145faa2692f7d7b1.png) for abstract vectors ![\mathbf{u}, \mathbf{v} \in V](./images/7e2d606a73df0ffc2e4651df1b948859003708ee.png). We’ll define inner product operations for matrices ![\langle A,B\rangle](./images/457530a9e2a6d437577aa0cb5189d8b8d9bb5463.png), polynomials ![\langle \mathbf{p},\mathbf{q}\rangle](./images/06fb518ea8c99ade962e7e1054b7083a0d0b0bf6.png), and functions ![\langle f,g \rangle](./images/3931bc4690e40d6b756d56407acf683f3491af9d.png). These inner product operations will allow us to talk about _orthogonality_ between abstract vectors,

![\mathbf{u} \textrm{ and } \mathbf{v} \textrm{ are orthogonal } 
\qquad
\Leftrightarrow
\qquad
\langle \mathbf{u},\mathbf{v}\rangle = 0,](./images/1d12cbf42d5c0bbcc956210fd28807103b9a20ad.png)

the _length_ of an abstract vector,

![\| \mathbf{u} \| =  \sqrt{ \langle \mathbf{u},\mathbf{u}\rangle },](./images/91674bbd913414d0f664d4d12d8c81169d298f27.png)

and the _distance_ between two abstract vectors,

![d(\mathbf{u},\mathbf{v}) 
= \| \mathbf{u}-\mathbf{v} \|
= \sqrt{ \langle (\mathbf{u}-\mathbf{v}),(\mathbf{u}-\mathbf{v})\rangle }.](./images/0b593a10457af27e2709400df5124fc49bf19f81.png)

Let’s get started.

###[Definitions](./Front matter.md)

We’ll work with vectors from an abstract vector space ![(V,\mathbb{R},+,\cdot)](./images/313330e93218147f3e2906b573cc90e81ca0ef18.png) where:

-   ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is the set of vectors in the vector space.
-   ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) is the _field_ of real numbers. The components of the abstract vectors are taken from this field.
-   ![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png) is the addition operation defined for elements of ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png).
-   ![\cdot](./images/02ca492c3fc32f2bb808f25d16aec9e93a911586.png) is the scalar multiplication operation between an element of the field ![\alpha \in \mathbb{R}](./images/291a1b884bfe1bd3bdd9e4811c426bcf4da094c5.png) and a vector ![\mathbf{u} \in V](./images/4a869665b21aa2f6eaf354a4c85abc940ed30a7f.png).

We define a new operation called _abstract inner product_ for that space:

![\langle \cdot, \cdot \rangle : V \times V \to \mathbb{R}.](./images/25c36d68f8c4f71f423296c7934108895a415e5f.png)

The abstract inner product takes as inputs two vectors ![\mathbf{u}, \mathbf{v} \in V](./images/7e2d606a73df0ffc2e4651df1b948859003708ee.png) and produces real numbers as outputs: ![\langle \mathbf{u},\mathbf{v}\rangle \in \mathbb{R}](./images/cf3a60506b752fdf96dc05446484feea2650080b.png).

We define the following related quantities in terms of the inner product operation:

-   ![\| \mathbf{u} \|  \,\eqdef\,  \sqrt{ \langle \mathbf{u},\mathbf{u}\rangle }](./images/e1fd713b60962280e574ce2b181d021d52d3cc51.png): the _norm_ or _length_ of an abstract vector
-   ![d(\mathbf{u},\mathbf{v}) \,\eqdef\,  \| \mathbf{u}-\mathbf{v} \|](./images/1b384e9e34486bf0d15510525113fbe80d6cd9cc.png): the _distance_ between two vectors

###[Orthogonality](./Front matter.md)

Recall that two vectors ![\vec{u}, \vec{v} \in \mathbb{R}^n](./images/07862d1e19e84ed614920b490c86af5f7f625961.png) are said to be orthogonal if their dot product is zero. This follows from the geometric interpretation of the dot product:

![\vec{u}\cdot \vec{v} = \|\vec{u}\| \|\vec{v}\| \cos\theta,](./images/c33276311a4db2ab1e592510377dd9ec204ce161.png)

where ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) is the _angle_ between ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). Orthogonal means “at right angle with.” Indeed, if ![\vec{u}\cdot \vec{v}=0](./images/e2e787c6c697f4ddd1546c151b26e517b03fa497.png), the angle between ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) must be ![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png) or ![270^\circ](./images/353599644066235caade9d74c725c105caac634b.png), since ![\cos\theta=0](./images/4831038ce54cc77e64c9140169c4010cbcadb25a.png) only for these two angles.

In analogy with the regular dot product, we define the notion of _orthogonality_ between abstract vectors in terms of the abstract inner product:

![\mathbf{u} \textrm{ and } \mathbf{v} \textrm{ are orthogonal } 
\qquad
\Leftrightarrow
\qquad
\langle \mathbf{u},\mathbf{v}\rangle = 0.](./images/feddbddbcdac522ad71d970a8d592b830d4d033a.png)

Translating the geometric intuition of “at ![90^\circ](./images/6018f803990b41827c623eef586d1b3c4887c1b3.png) angle with” might not be possible for certain abstract vector spaces. For instance, what is the angle between two polynomials? Nevertheless, the fundamental notion of “perpendicular to” exists in all abstract inner product vector spaces.

###[Norm](./Front matter.md)

Every definition of an inner product for an abstract vector space ![(V,\mathbb{R},+,\cdot)](./images/313330e93218147f3e2906b573cc90e81ca0ef18.png) induces a _norm_ for that vector space:

![\| . \| : V  \to \mathbb{R}.](./images/600c9fbb5c5189adf0e368d346b21ea427cd6741.png)

The norm is defined in terms of the inner product. The norm of a vector is the square root of the inner product of the vector with itself:

![\|\mathbf{u}\|	\,\eqdef\,	\sqrt{\langle \mathbf{u},\mathbf{u}\rangle }.](./images/29a0a56517f0c4fec03a3f05080ea8925a1b60d4.png)

The norm corresponds to the abstract notion of length for vectors. All norms must satisfy the following criteria:

-   ![\|\mathbf{v}\| \geq 0](./images/7945d5f90f549d7bb804e2aa2faaf6763a921646.png) with equality if and only if ![\mathbf{v} = \mathbf{0}](./images/5d163cb831867bc427f50addfbb17c8781a648bb.png)
-   ![\| k\mathbf{v} \| = k \|\mathbf{v}\|](./images/d023b24b8c187f571bac3ed2e50a66f7c8804eab.png)
-   The triangle inequality:
    
    ![\|\mathbf{u}+\mathbf{v}\|\leq\|\mathbf{u}\|+\|\mathbf{v}\|](./images/fac148298c8d8fafb98395a7bae54b00cd23a2fb.png)
    
-   Cauchy–Schwarz inequality:
    
    ![| \langle \mathbf{x} , \mathbf{y}  \rangle | \leq \|\mathbf{x} \|\: \| \mathbf{y} \|,](./images/b781d56a06036924f8786608ec0a327615561ddd.png)
    
    with equality if and only if ![\mathbf{x}](./images/d60a4bf2e8fcbf0ce5fee05d510dd41968862eb6.png) and ![\mathbf{y}](./images/c1805a85da42208958fa1cba09bd64a54c8944e8.png) are linearly dependent
    

Norms defined in terms of a valid inner product automatically satisfy these criteria.

###[Distance](./Front matter.md)

The distance between two points ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) and ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) in ![\mathbb{R}^n](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png) is equal to the norm of the vector that goes from ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) to ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png): ![d(p,q)=\| q - p \|](./images/fc0f86cff8e4472a41b015ce7dabfd2dee2e9644.png). We can similarly define a _distance_ function between pairs of vectors in an abstract vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png):

![d : V  \times V \to \mathbb{R}.](./images/0e9c4ff4fb4b016b14511bf2b3f16f8bfd891253.png)

The distance between two abstract vectors is equal to the norm of their difference:

![d(\mathbf{u},\mathbf{v}) 
\,\eqdef\, \| \mathbf{u}-\mathbf{v} \|
=\sqrt{ \langle (\mathbf{u}-\mathbf{v}),(\mathbf{u}-\mathbf{v})\rangle }.](./images/e28b31097db274bbe1e142ff8ab5810dbcb86d3a.png)

Distances defined in terms of a valid norm obey the following criteria:

-   ![d(\mathbf{u},\mathbf{v}) = d(\mathbf{v},\mathbf{u})](./images/22259ac7a1ff9b909a328ffbfde141daa7b48864.png)
-   ![d(\mathbf{u},\mathbf{v}) \geq 0](./images/84ad590cf69bb7780347d7e7e6c4706ac297d792.png) with equality if and only if ![\mathbf{u}=\mathbf{v}](./images/a11d815ade7fa942f400ff4ad64ad6ec87f1859e.png)

###[Examples](./Front matter.md)

Let’s define some inner product functions for the aforementioned abstract vector spaces.

####[Matrix inner product](./Front matter.md)

The Hilbert–Schmidt inner product for real matrices is defined in terms of the matrix transpose, matrix multiplication, and matrix trace operations:

![\langle A, B \rangle_{\textrm{HS}} = \textrm{Tr}\!\left( A^\sfT B \right).](./images/217f79bdc9d685a882cd3df29fcf963acbab73c5.png)

We can use this inner product to talk about _orthogonality_ properties of matrices. In the last section, we defined the set of ![2\times2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) symmetric matrices

![\mathbb{S}(2,2) = \{ A \in \mathbb{R}^{2\times 2} \; | \; A = A^\sfT \, \},](./images/b8dd9fa5a77a830ecaf74e1f2ad06598bd09fc8c.png)

and gave an explicit basis for this space:

![\mathbf{v}_1 = 
\begin{bmatrix}
1 & 0 \\
0 & 0 
\end{bmatrix}\!, 
\qquad
\mathbf{v}_2 = 
\begin{bmatrix}
0 & 1 \\
1 & 0 
\end{bmatrix}\!, 
\qquad
\mathbf{v}_3 = 
\begin{bmatrix}
0 & 0 \\
0 & 1 
\end{bmatrix}\!.](./images/3a296d3296af657d3052711c5c8ddae0fc687e59.png)

It’s easy to show that these vectors are all _mutually orthogonal_ with respect to the Hilbert–Schmidt inner product ![\langle \cdot , \cdot \rangle_{\textrm{HS}}](./images/929a9c90efee991750c9f51e13a6550a084209e3.png):

![\langle \mathbf{v}_1 , \mathbf{v}_2 \rangle_{\textrm{HS}}=0, \qquad
\langle \mathbf{v}_1 , \mathbf{v}_3 \rangle_{\textrm{HS}}=0, \qquad
\langle \mathbf{v}_2 , \mathbf{v}_3 \rangle_{\textrm{HS}}=0.](./images/296113dcdc59edd63f34cc611d78ec19b2edffde.png)

Verify these three equations by computing each inner product. Try this by hand on a piece of paper … like right now.

The three inner product calculations of the last equation indicate that the set ![\{ \mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3 \}](./images/5dd0f2f887c144f1cb3b41d830e7e9a16571018b.png) forms an orthogonal basis for the vector space ![\mathbb{S}(2,2)](./images/ef308dd930953b3854ec0d47bd900f3309fd725e.png) with respect to the inner product ![\langle \cdot, \cdot \rangle_{\textrm{HS}}](./images/929a9c90efee991750c9f51e13a6550a084209e3.png).

####[Hilbert–Schmidt norm](./Front matter.md)

The Hilbert–Schmidt inner product induces the Hilbert–Schmidt norm:

![\|A\|_{\textrm{HS}}
\,\eqdef\, \sqrt{ \langle A, A \rangle_{\textrm{HS}} }
= \sqrt{ \textrm{Tr}\!\left( A^\sfT A \right) }
= \left[ \sum_{i,j=1}^{n} |a_{ij}|^2 \right]^{\frac{1}{2}}.](../Images/20997666b40eb04597c4fa3c113498dacb322969.png)

We can use this norm to define an abstract notion of length for matrices. Continuing with the above example, we can obtain an ortho**normal** basis ![\{ \hat{\mathbf{v}}_1, \hat{\mathbf{v}}_2, \hat{\mathbf{v}}_3 \}](./images/ebd7eb68f3dc8a9441f2b8c3999fad4bdd7634c9.png) for ![\mathbb{S}(2,2)](./images/ef308dd930953b3854ec0d47bd900f3309fd725e.png) as follows:

![\hat{\mathbf{v}}_1 =  \mathbf{v}_1,
\qquad
\hat{\mathbf{v}}_2 = \frac{ \mathbf{v}_2 }{ \|\mathbf{v}_2\|_{\textrm{HS}} } = \frac{1}{\sqrt{2}}\mathbf{v}_2,
\qquad
\hat{\mathbf{v}}_3 = \mathbf{v}_3.](./images/ffcc8e5c7ec393055285079382c12f5e5dac66b5.png)

Verify that ![\|\hat{\mathbf{v}}_2\|_{\textrm{HS}}=1](./images/7064be37462b6788e2b6fcd934ad0e2ae39a4db2.png).

####[Function inner product](./Front matter.md)

Consider two functions, ![\mathbf{f}=f(t)](./images/cfc923390ecbce5c3fe5c5b118f22238875c5e7c.png) and ![\mathbf{g}=g(t)](./images/e59d1d9d7e6f590b5d6341772dc65267557d287e.png), and define their inner product as follows:

![\langle \mathbf{f},\mathbf{g}\rangle \,\eqdef\, \int_{-\infty}^\infty f(t)g(t)\; dt.](./images/5c4c5e0f9086ce4401702a1dfcfeea657aea7fb1.png)

This formula is the continuous-variable version of the inner product formula for vectors ![\vec{u}\cdot\vec{v}=\sum_i u_i v_i](./images/f728d5256f19b5b03e7cb1d2bac2fc3292e2748f.png). Instead of a summation, we have an integral; otherwise the idea is the same since we’re measuring the _overlap_ between ![\mathbf{f}](./images/31b9206f2adc2cbc346f440c9cb0c5f78a16538d.png) and ![\mathbf{g}](./images/42e1be0a285d1f23118253cb5ae98cd9c4c86c4a.png). The integral passes along the real line from ![-\infty](./images/f721ad0d9976ce8087387d1ef86a879ec6843579.png) until ![\infty](./images/18001a4cf7963f0eea21f6c4aeab5fb1cd8c6a5c.png) like a zipper that brings together ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) times ![g(t)](./images/1a95936639329f7b8df93c8a0a607ac715e76b5f.png) at each point.

#####[Example](./Front matter.md)

Consider the function inner product on the interval ![[-1,1]](../Images/b072cebfd75fdf83cba4813cb0cd96d340e840ab.png) as defined by the formula:

![\langle \mathbf{f}, \mathbf{g}\rangle =\int_{-1}^1 f(t)g(t)\; dt.](./images/bc5aaa9f140edde271769b3d9bfe93b07efac0e5.png)

Verify that the following polynomials, known as the Legendre polynomials ![P_n(x)](./images/064ff86501dba020964c53718619fda009a33f0f.png), are mutually orthogonal with respect to the above inner product:

![\; \; \; \; \; P_0(x)=1, \qquad \; 
P_1(x)=x, \qquad \;  \\](./images/a0aa2d5178445241b338fe0968b5c6c2d9515c4e.png)

![P_2(x)=\frac{1}{2}(3x^2-1), \qquad 
P_3(x)=\frac{1}{2}(5x^3-3x).](./images/0f6daa08cfdee63b0ccdad8d8ca1ceb84dea44e1.png)

####[Generalized dot product](./Front matter.md)

We can think of the regular dot product for vectors as the following vector-matrix-vector product:

![\vec{u} \cdot \vec{v} = \vec{u}^\sfT \vec{v}= \vec{u}^\sfT \mathbbm{1} \vec{v}.](./images/7a5b97b173d504f155f6cead57e56a3612cad33b.png)

More generally, we can insert any _symmetric_, _positive semidefinite_ matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) between the vectors and obtain a valid inner product:

![\langle \vec{x}, \vec{y} \rangle_M \,\eqdef\, \vec{x}^\sfT M \vec{y}.](./images/664a2332fc94d56bd2c466911630832d65854d69.png)

The matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is called the _metric_ for this inner product, and it encodes the relative contributions of the different components of the vectors to the inner product.

The requirement that ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) be symmetric stems from the symmetric requirement for inner products: ![\langle \mathbf{u},\mathbf{v}\rangle =\langle \mathbf{v},\mathbf{u}\rangle](./images/886a2a574e4c04b3d4ccd726e7098c778e30fc53.png). The requirement that the matrix be positive semidefinite comes from the positive semidefinite requirement for inner products: ![\langle \mathbf{u},\mathbf{u}\rangle = \vec{u}^\sfT M \vec{u} \geq 0](./images/1af699bcb608fec5e9132b1fb2cc6576cae5d9b2.png), for all ![\mathbf{u}\in V](./images/4a869665b21aa2f6eaf354a4c85abc940ed30a7f.png).

We can always obtain a symmetric and positive semidefinite matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) by setting ![M = A^\sfT A](./images/d6cb0fafcb192ab64d368ca6a749c827495bd9bd.png) for some matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). To understand why we might want to construct ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) in this way, recall that each matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) implements some linear transformation ![T_A(\vec{u})=A\vec{u}](./images/ffdb40a3a13383a2ebe7cf60f3492fad27ff0f25.png). An inner product ![\langle \vec{u},\vec{v}\rangle_M](./images/cbc6cdca4564cbedd7932c8188101ecc4927fb16.png) can be interpreted as the regular dot product in the output space of ![T_A](./images/487ea635c2ec263593f64b7212fe91f7c365a5d2.png):

![\langle \vec{u}, \vec{v} \rangle_M = 
\vec{u}^\sfT M \vec{v}=
\vec{u}^\sfT A^\sfT A \vec{v}=
(A\vec{u})^\sfT (A \vec{v})=
T_A(\vec{u}) \cdot T_A(\vec{v}).](./images/6449e2da286ed4daf7878cdb4fc8167b5702382d.png)

The notion of a generalized inner product with metric matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is a powerful idea with applications in advanced math areas like analysis and differential geometry. The concept of a metric also shows up in physics: when Einstein talks about masses causing space to become “curved,” he’s talking about the curvature of the metric of space-time.

####[Valid and invalid inner product spaces](./Front matter.md)

A standard question profs like to ask on exams is to check whether a given vector space and some weird definition of an inner product operation form a valid inner product space. Recall that _any_ operation can be used as the inner product, as long as it satisfies the _symmetry_, _linearity_, and _positive semidefinite_ criteria. To prove an inner product operations is valid, you must show it satisfies the three criteria.

Alternatively, you can prove the vector space ![(V,\mathbb{R},+,\cdot)](./images/313330e93218147f3e2906b573cc90e81ca0ef18.png) with inner product ![\langle \mathbf{u}, \mathbf{v} \rangle](./images/3b9ee96b30fdf71f77bac471145faa2692f7d7b1.png) is _not_ a valid inner product space if you find an example of one or more ![\mathbf{u},\mathbf{v} \in V](./images/7e2d606a73df0ffc2e4651df1b948859003708ee.png) that don’t satisfy the axioms.

###[Discussion](./Front matter.md)

This has been another one of those sections where we learn no new linear algebra, but simply generalize notions we already know about standard vectors ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png) to abstract vector-like objects ![\textbf{v} \in V](./images/87d4b85826a24ee735720c9bb71dbcb1a4820ea0.png). You can now talk about orthogonality and norms for matrices, polynomials, and functions.

###[Exercises](./Front matter.md)

E6.13 Prove the set of matrices ![\big\{ 	\mathbf{e}_1 = \begin{bmatrix} 1 & 0  \\  0 & 0 \end{bmatrix},
\mathbf{e}_2 = \begin{bmatrix} 0 & 1  \\  0 & 0 \end{bmatrix},
\mathbf{e}_3 = \begin{bmatrix} 0 & 0  \\  0 & 1 \end{bmatrix} \big\}](./images/09b9ee158f743765258e0990d450b0d3d7ba44ca.png) is an orthonormal set under the inner product ![\langle A, B \rangle_{\textrm{HS}} = \textrm{Tr}\!\left( A^\sfT B \right)](./images/2b3b00646e99622c275b3baead9356d113c9af07.png).

E6.14 Compute the norm of the functions ![P_0(x)=1](./images/c0aa5a7ed79ad1bfae85d54817498101d4d15ebf.png) and ![P_1(x)=x](./images/19aedb8816ee618d4a2d8c4225837373f3fdd6a4.png) with respect to the function inner product ![\langle \mathbf{f}, \mathbf{g}\rangle =\int_{-1}^1 f(x)g(x)\; dt](./images/cb67a5497230183caf5d8104fad391a09c77c729.png) defined on the interval ![[-1,1]](../Images/b072cebfd75fdf83cba4813cb0cd96d340e840ab.png). Also compute the distance ![d(P_0,P_1)](./images/b4aad70015a7eccbbf2d5210c5a0e0660a6b63d6.png).

Recall that a vector’s norm is defined as ![\|\mathbf{u}\|=\sqrt{\langle \mathbf{u},\mathbf{u}\rangle }](./images/dc1d914751fbc250786c0b2710d8caf4770b06dc.png).

##[6.5 Gram–Schmidt orthogonalization](./Chapter 6_ Theoretical linear algebra.md)

Recall what we learned in[Section 4.3](./Chapter 4_ Geometric aspects of linear algebra.md) about the three “quality grades” for bases: orthonormal, orthogonal, and generic, with orthonormal bases being the easiest to work with. In this section, we’ll learn how to take a generic basis for an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)—that is, a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors ![\{ \mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n \}](./images/0fa691abe98bb510ff4c1d046f5c4e1f2f75fa7c.png)—and transform it into an orthonormal basis ![\{\hat{\mathbf{e}}_1,\hat{\mathbf{e}}_2,\ldots,\hat{\mathbf{e}}_n \}](./images/54ed11896b9cfd154fc451faf1467d89abed1d31.png) that satisfies the conditions

![\langle \hat{\mathbf{e}}_i, \hat{\mathbf{e}}_j \rangle 
=\left\{ \begin{array}{ll} 1 & \textrm{ if } i = j, \\ 0 & \textrm{ if } i \neq j. \end{array}\right.](./images/f980a0b87bd10674b95304854c95de29105b5551.png)

This procedure is known as _Gram–Schmidt orthogonalization_ and is based on a sequence of projection and subtraction operations.

The discussion and procedures in this section are described in terms of vectors in an abstract inner product space. Thus, the Gram–Schmidt algorithm applies to ordinary vectors ![\vec{v} \in \mathbb{R}^n](./images/12c88838db1ff85d9675a27147b2252248da56ee.png), matrices ![A \in \mathbb{R}^{m\times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png), and polynomials ![\mathbf{p} \in P_n(x)](./images/f79e5a5b1624ceafa9228d96518669a99ffd241e.png). Indeed, we can talk about orthogonality for any set of mathematical objects for which we’ve defined an inner product operation.

###[Definitions](./Front matter.md)

-   ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png): an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space
-   ![\{ \mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n \}](./images/0fa691abe98bb510ff4c1d046f5c4e1f2f75fa7c.png): a generic basis for the space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)
-   ![\{ \mathbf{e}_1, \mathbf{e}_2, \ldots, \mathbf{e}_n \}](./images/f2f270a6f0578aa7d55d152840a3a64114757b89.png): an _orthogonal basis_ for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). Each vector ![\mathbf{e}_i](./images/c58e8abecd10a774c4a891ac3aeb1a379ef3d676.png) is orthogonal to all other vectors: ![\mathbf{e}_i \cdot \mathbf{e}_j=0](./images/cc8ff96535606d76d099e046302dd172cfdf17ca.png), for ![i\neq j](./images/fe4bf09b19814755a6c9a589b2e1aad7707242e8.png).
-   ![\{ \hat{\mathbf{e}}_1, \hat{\mathbf{e}}_2, \ldots, \hat{\mathbf{e}}_n \}](./images/54ed11896b9cfd154fc451faf1467d89abed1d31.png): an _orthonormal_ basis for ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). An orthonormal basis is an orthogonal basis of unit vectors.

We assume the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is equipped with an inner product operation:

![\langle \cdot, \cdot \rangle : V \times V \to \mathbb{R}.](./images/25c36d68f8c4f71f423296c7934108895a415e5f.png)

The following operations are defined in terms of the inner product:

-   The _length_ of a vector ![\|\mathbf{v}\| = \langle \mathbf{v}, \mathbf{v} \rangle](./images/68985dff916d25131fd78ff05f05b6d2a38140a2.png)
-   The _projection_ operation. The projection of the vector ![\mathbf{u}](./images/fdef05356517f4e74d2a56deccef430681ee4bfa.png) onto the subspace spanned by the vector ![\mathbf{e}](./images/f72907ea3606b6de6f1fe6ad4f0d731715c43387.png) is denoted ![\Pi_{\mathbf{e}}(\mathbf{u})](./images/ca79d1a955b08ec4658123cde701354014ad45b3.png) and is computed using
    
    ![\Pi_{\mathbf{e}}(\mathbf{u}) 
    =  \frac{  \langle \mathbf{u}, \mathbf{e} \rangle }{ \|\mathbf{e}\|^2 } \mathbf{e}.](./images/c2859b3063fdc17deaffc38af6fa3a9c17a7ebc6.png)
    
-   The _projection complement_ of the projection ![\Pi_{\mathbf{e}}(\mathbf{u})](./images/ca79d1a955b08ec4658123cde701354014ad45b3.png) is the vector ![\mathbf{w}](./images/9856678a8965d0e82dcf3757697d1a918fba542f.png) that we must add to ![\Pi_{\mathbf{e}}(\mathbf{u})](./images/ca79d1a955b08ec4658123cde701354014ad45b3.png) to recover the original vector ![\mathbf{u}](./images/fdef05356517f4e74d2a56deccef430681ee4bfa.png):
    
    ![\mathbf{u} = \Pi_{\mathbf{e}}(\mathbf{u}) + \mathbf{w}
    \qquad \; \; 
    \Rightarrow
    \qquad \; \; 
    \mathbf{w} = \mathbf{u} - \Pi_{\mathbf{e}}(\mathbf{u}).](./images/029787bad7dc3e16b9a753e2a88478ff3c85ed16.png)
    
    The vector ![\mathbf{w}](./images/9856678a8965d0e82dcf3757697d1a918fba542f.png) is orthogonal to the vector ![\mathbf{e}](./images/f72907ea3606b6de6f1fe6ad4f0d731715c43387.png), ![\langle \mathbf{w}, \mathbf{e} \rangle = 0](./images/04559ead4158512ffebb3e6d3f5e838f94b04d2a.png).
    

###[Orthonormal bases are nice](./Front matter.md)

Recall that a _basis_ for an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is any set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). The choice of basis is a big deal because we express the coordinates of vectors and matrices with respect to the basis. From a theoretical standpoint, all bases are equally good; but from a practical standpoint, orthogonal and orthonormal bases are much easier to work with.

An orthonormal basis ![B=\{ \hat{\mathbf{e}}_1, \hat{\mathbf{e}}_2, \hat{\mathbf{e}}_3 \}](./images/2c6be4541b609236a1feec7a7825e933bf799ff6.png) is the most useful kind of basis because the coordinates ![c_1](./images/e36d3237a39ff5553e766cf40b8f6802aa0c00ab.png), ![c_2](./images/0d5930fc118c2ea1b71c5a4c404f5dcb28633f6d.png), and ![c_3](./images/eb78bb692e455e2e67f6084b3f5403526b3491c7.png) of a vector ![\mathbf{c}=(c_1,c_2,c_3)_B](./images/ca20187c1cda0473fc5cbb5c4a03d230460b54a3.png) with respect to ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) are obtained using three independent inner product calculations:

![c_1 = \langle \mathbf{c}, \hat{\mathbf{e}}_1 \rangle,
\qquad
c_2 = \langle \mathbf{c}, \hat{\mathbf{e}}_2 \rangle,
\qquad 
c_3 = \langle \mathbf{c}, \hat{\mathbf{e}}_3 \rangle.](./images/faf135024d314f45ab4d311f302d05726e95f467.png)

We can express any vector ![\mathbf{v}](./images/633b84ab115cc79e0751cfddae6cfadae6fca32b.png) as

![\mathbf{v} =  
\langle \mathbf{v}, \hat{\mathbf{e}}_1 \rangle \hat{\mathbf{e}}_1
+ 
\langle \mathbf{v}, \hat{\mathbf{e}}_2 \rangle \hat{\mathbf{e}}_2
+
\langle \mathbf{v}, \hat{\mathbf{e}}_3 \rangle \hat{\mathbf{e}}_3.](./images/8d8790bfec3e96206dc03a46282cba27735bcfb4.png)

This formula is a generalization of the usual formula for coordinates with respect to the standard basis ![\{ \hat{\imath}, \hat{\jmath},\hat{k} \}](./images/20a783ec4e2fb4e61cdda060b7be04e1c1bd2022.png): ![\vec{v} = (\vec{v}\cdot\hat{\imath})\hat{\imath} + (\vec{v}\cdot\hat{\jmath})\hat{\jmath} + (\vec{v}\cdot\hat{k}) \hat{k}](./images/5fbbc48747a0a71a6f4bd91952f10b004441e08a.png).

###[Orthogonalization](./Front matter.md)

The “best” kind of basis for computational purposes is an orthonormal basis like ![\{ \hat{\mathbf{e}}_1, \hat{\mathbf{e}}_2, \ldots, \hat{\mathbf{e}}_n \}](./images/54ed11896b9cfd154fc451faf1467d89abed1d31.png). How can we _upgrade_ some general set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors ![\{ \mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n \}](./images/0fa691abe98bb510ff4c1d046f5c4e1f2f75fa7c.png) into an orthonormal basis ![\{ \hat{\mathbf{e}}_1, \hat{\mathbf{e}}_2, \ldots, \hat{\mathbf{e}}_n \}](./images/54ed11896b9cfd154fc451faf1467d89abed1d31.png)? The vectors ![\{\hat{\mathbf{e}}_i\}](./images/28d5ef89278e743b8083219d8054b16d2aad6c13.png) must be linear combinations of the vectors ![\{\mathbf{v}_i\}](./images/643ae22a3de092925d041f75c5f995ba8aaa0888.png), but which linear combinations should we choose?

Note the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) remains the same:

![\textrm{span}(\mathbf{v}_1,\mathbf{v}_2,\ldots,\mathbf{v}_n )
=
V
= \textrm{span}( \hat{\mathbf{e}}_1,\hat{\mathbf{e}}_2,\ldots,\hat{\mathbf{e}}_n ).](./images/02dd1254fb9786b2686a09217bd7828bf2dfef6f.png)

However, the basis ![\{\hat{\mathbf{e}}_1,\hat{\mathbf{e}}_2,\ldots,\hat{\mathbf{e}}_m \}](./images/d8224852c23716d1fbdaec86e7fd64a0c27599f8.png) is easier to work with.

The technical term for distilling a high-quality orthonormal basis from a low-quality basis of arbitrary vectors is called _orthogonalization_. Most of the work lies in obtaining the set of vectors ![\{ \mathbf{e}_i\}](./images/015263c630e1eea63e56ddc8c39b30637f07a45c.png) that are _orthogonal_ to each other:

![\langle \mathbf{e}_i, \mathbf{e}_j \rangle =0, \quad \textrm{ for all } i \neq j.](./images/63029da22cf0abad521e8150941b5de67f7a873d.png)

To convert an orthogonal basis into an orthonormal basis, divide each vector by its length: ![\hat{\mathbf{e}}_i = \frac{\mathbf{e}_i}{ \| \mathbf{e}_i \| }](./images/02114c3437569559e93566323527ef06991b883a.png).

It’s now time to see how orthogonalization works; get ready for some Gram–Schmidting.

###[Gram–Schmidt orthogonalization procedure](./Front matter.md)

The Gram–Schmidt orthogonalization procedure converts a basis of arbitrary vectors ![\{ \mathbf{v}_1, 		\ldots, \mathbf{v}_n \}](./images/a9ee3f2376fc183a1366d08ab2e8f50d080fbf07.png) into an orthonormal basis ![\{ \hat{\mathbf{e}}_1, 		\ldots, \hat{\mathbf{e}}_n \}](./images/cf0e7bb21f90d6ef2684dd810c42a758a62a3cc0.png). The main idea is to take the vectors ![\mathbf{v}_i](./images/924a3cc0654caeefafd4fb9940452b3099f8b9a0.png) one at a time, each time defining a new vector ![\mathbf{e}_i](./images/c58e8abecd10a774c4a891ac3aeb1a379ef3d676.png) as the _orthogonal complement_ of ![\mathbf{v}_i](./images/924a3cc0654caeefafd4fb9940452b3099f8b9a0.png) to all the previously chosen vectors ![\mathbf{e}_1](./images/ee544d1c6687b1376419cae8cf6c54725b115287.png), ![\mathbf{e}_2](./images/3f19515af410075149edca2cdeb2b8e67e37b10f.png), ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png), ![\mathbf{e}_{i-1}](./images/65ea7b96624de4103057b52b0ba626132cf3cb8c.png). Recall we can use the projection formula ![\Pi_{\hat{\mathbf{e}}}(\mathbf{v}) = \langle \hat{\mathbf{e}}, \mathbf{v}\rangle\hat{\mathbf{e}}](./images/1fbf36499d55dc6ce1f027b01b2e5121c253f03f.png) to compute the component of any vector ![\mathbf{v}](./images/633b84ab115cc79e0751cfddae6cfadae6fca32b.png) in the direction ![\hat{\mathbf{e}}](./images/998067730fde20ccf0dafa38a9618400fdc07a28.png).

The orthogonalization algorithm consists of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) steps:

![\begin{align*}
\mathbf{e}_1 &= \mathbf{v}_1  
& \hat{\mathbf{e}}_1 &= {\mathbf{v}_1 \over \|\mathbf{v}_1\|},  \\
\mathbf{e}_2 &= \mathbf{v}_2-\Pi_{\hat{\mathbf{e}}_1}\!(\mathbf{v}_2), 
& \hat{\mathbf{e}}_2 &= {\mathbf{e}_2 \over \|\mathbf{e}_2\|}, \\
\mathbf{e}_3 &= \mathbf{v}_3-\Pi_{\hat{\mathbf{e}}_1}\!(\mathbf{v}_3)-\Pi_{\hat{\mathbf{e}}_2}\!(\mathbf{v}_3), 
& \hat{\mathbf{e}}_3 &= {\mathbf{e}_3 \over \|\mathbf{e}_3\|}, \\
\mathbf{e}_4 &= \mathbf{v}_4-\Pi_{\hat{\mathbf{e}}_1}\!(\mathbf{v}_4)-\Pi_{\hat{\mathbf{e}}_2}\!(\mathbf{v}_4),
-\Pi_{\hat{\mathbf{e}}_3}\!(\mathbf{v}_4), 
& \hat{\mathbf{e}}_4 &= {\mathbf{e}_4 \over \|\mathbf{e}_4\|}, \\
& \vdots &&\vdots \\
\mathbf{e}_n &= \mathbf{v}_n-\sum_{i=1}^{n-1}\Pi_{\hat{\mathbf{e}}_i}\!(\mathbf{v}_n),
&\hat{\mathbf{e}}_n &= {\mathbf{e}_n\over\|\mathbf{e}_n\|}.
\end{align*}](./images/9eab988fd402555b95c240f5864463419961b372.png)

In the ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th step of the procedure, we compute a vector ![\mathbf{e}_j](./images/18dccfe1c9c58b37e563f00e030fe269a59b7adf.png) by starting from ![\mathbf{v}_j](./images/4ea89a14ee0dbd2d60eb8889f915b5a07c7cb87b.png) and subtracting all the projections of ![\mathbf{v}_j](./images/4ea89a14ee0dbd2d60eb8889f915b5a07c7cb87b.png) onto the previous vectors ![\mathbf{e}_i](./images/c58e8abecd10a774c4a891ac3aeb1a379ef3d676.png) for all ![i<j](./images/a43afa9f3a386ccf7eb367790d46a491ad9aba80.png). In other words, ![\mathbf{e}_j](./images/18dccfe1c9c58b37e563f00e030fe269a59b7adf.png) is the part of ![\mathbf{v}_j](./images/4ea89a14ee0dbd2d60eb8889f915b5a07c7cb87b.png) that is orthogonal to all the vectors ![\mathbf{e}_1, \mathbf{e}_2, \ldots, \mathbf{e}_{j-1}](./images/1b8f5d14e3a66ce7cff6cf85d81d78417e8db5f4.png).

This procedure is known as orthogonalization because it splits the vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) into orthogonal subspaces ![V_1, V_2, \ldots, V_n](./images/78395a6fd33129d033c4a1db0dcbc77417227481.png):

![V_j = 
\textrm{span}\bigg( \mathbf{v} \in V \; \bigg| \; \mathbf{v}= \sum_{i=1}^j \alpha_i \mathbf{v}_i \bigg)
\; \; \setminus  \; \; 
\textrm{span}\bigg( \mathbf{v} \in V \; \bigg| \; \mathbf{v}= \sum_{i=1}^{j-1} \alpha_i \mathbf{v}_i \bigg).](./images/d61f7ededce86d97a95f6c2eed365de342633f18.png)

Recall that the symbol ![\setminus](./images/bbc99930f192783ed45cf262df5c52e215540221.png) denotes the _set difference_ operation. The set ![A \setminus B](./images/fcc307a8a212c36de9a1423848211451350b9484.png) consists of all elements that are in set ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) but not in set ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png).

Observe that the subspaces ![V_1, V_2, \ldots, V_n](./images/78395a6fd33129d033c4a1db0dcbc77417227481.png) are, by construction, mutually orthogonal. Given any vector ![\mathbf{u} \in V_i](./images/00f8eb76a80b498584c6d0c419cf14548c9b3ec5.png) and another vector ![\mathbf{v} \in V_j, j\neq i](./images/9c6053f62bcf1b765c4dd5ffb8d7d7d06be8d73d.png), then ![\mathbf{u} \cdot \mathbf{v} = 0](./images/b65694ba65bcd30abdc913abc26e0b5a89273e00.png).

The vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is the sum of these subspaces:

![V = V_1 \oplus V_2 \oplus V_3 \oplus \cdots \oplus V_n.](./images/97fdc892bbd33da83d3a4efad654378d0bd51a58.png)

The notation ![\oplus](./images/6a61dca4d2971f0ac55df48a1ea4eefb5483aeb0.png) means _orthogonal sum_. Each space ![V_j](./images/a1971718a5fc8d2326bfe582e1ee3d016b0bddaa.png) is spanned by a vector ![\mathbf{e}_j](./images/18dccfe1c9c58b37e563f00e030fe269a59b7adf.png) which is orthogonal to all the ![V_i](./images/b443203da1c115accef3e47eeb16d0360a0f9f71.png)s, for ![i < j](./images/a43afa9f3a386ccf7eb367790d46a491ad9aba80.png).

###[Discussion](./Front matter.md)

The main point you must remember about orthogonalization is simply that it can be done. Any “low-quality” basis (a set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) linearly independent vectors ![\{ \mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n \}](./images/0fa691abe98bb510ff4c1d046f5c4e1f2f75fa7c.png) in an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional space) can be converted into a “high quality” orthonormal basis ![\{ \hat{\mathbf{e}}_1, \hat{\mathbf{e}}_2, \ldots, \hat{\mathbf{e}}_n \}](./images/54ed11896b9cfd154fc451faf1467d89abed1d31.png) using the Gram–Schmidt procedure.

You can also perceive the Gram–Schmidt procedure as a technique for creating structure in an arbitrary vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png). The initial description ![V=\textrm{span}(\mathbf{v}_1,\mathbf{v}_2,\ldots,\mathbf{v}_n)](./images/aec8e8f73b0c812530ac909fadd07e63ddaf31ef.png) lacks structure. It’s just some amorphous vector space spanned by an arbitrary set of vectors. After the orthogonalization procedure, we obtain the equivalent description ![V = V_1 \oplus V_2 \oplus V_3 \oplus \cdots \oplus V_n](./images/77fe8eabc345eca4a9e87943975c787e50bed273.png) that shows ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is the direct sum of orthogonal subspaces.

In the next section, we’ll continue on our mathematical quest for structure by discussing procedures that uncover hidden structure in matrices. For example, when phrased in terms of matrices, the Gram–Schmidt orthogonalization procedure is called _![QR](./images/1aedd31dee0f0d59e9beeb4a637c1a45974f3ffd.png) decomposition_—stay tuned! And meanwhile, try the following exercises.

###[Exercises](./Front matter.md)

E6.15 Convert the vectors ![\vec{v}_1 = (4,2)](./images/6eb70326a89085a6644929e95b908f9c4f077d61.png) and ![\vec{v}_2 = (1,3)](./images/31cbba10757bb9bc322b79301565353ba404cb9c.png) into an orthogonal basis for ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png).

E6.16 Perform the Gram–Schmidt orthogonalization procedure on the vectors ![\vec{v}_1=(1,1,0)](./images/9153a12309b5ebc415523cd1afbcd8fbe23952ae.png), ![\vec{v}_2=(1,0,1)](./images/f1883df4731a67a5c444b5a9b8807c044deae614.png), and ![\vec{v}_3=(0,1,1)](./images/d6ff862a1b41d77c88c187f8613bf469b66f3e4c.png) to obtain an orthonormal basis ![\{\hat{e}_1, \hat{e}_2, \hat{e}_3 \}](./images/c2bcd6a22c91fbce431e53813ab74cdf932e39ff.png).

E6.17 Consider the vector space of polynomials of degree at most two ![P_2(x)](./images/470e4e253d68b222e3f3b163490bc01e944484f7.png), and consider the inner product ![\langle \mathbf{p}, \mathbf{q}\rangle = \int_0^1 p(x)q(x)\,dx](./images/a0a13ea5587c416ec751ce4dea37c11caadab3b8.png). Perform the Gram–Schmidt orthogonalization procedure on the polynomials ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png), ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), and ![x^2](./images/08fe6a3dad1cc8eca8f316557c5ac7205c5a3e85.png) to obtain an orthonormal basis for ![P_2(x)](./images/470e4e253d68b222e3f3b163490bc01e944484f7.png).

##[6.6 Matrix decompositions](./Chapter 6_ Theoretical linear algebra.md)

It’s often useful to express a given matrix as the product of other, simpler matrices. These matrix decompositions (also known as factorizations) can help us understand the structure of matrices by revealing their constituents. In this section, we’ll discuss various matrix factorizations and specify the types of matrices they apply to.

Most of the material covered here is not usually included in a first-year linear algebra course. Nevertheless, knowing about the different matrix decompositions is quite helpful, as many linear algebra applications depend on these decompositions. Got that? Good. Onward!

###[Eigendecomposition](./Front matter.md)

The eigendecomposition breaks a matrix into its eigenvalues and eigenvectors. The eigenbasis, when it exists, is the most “natural” basis for looking at a matrix. A diagonalizable matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) can be written as

![A = Q \Lambda Q^{-1},](./images/2cbfc34469e390e961306834402301c0544a6c13.png)

where ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) is a matrix whose columns are eigenvectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), and ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png) is a diagonal matrix containing the eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

The eigendecomposition of a matrix is a similarity transformation (a change of basis) where the new basis matrix consists of eigenvectors of the matrix.

If ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is positive semidefinite then its eigenvalues are nonnegative. If the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is symmetric then its eigenvalues are real numbers.

When the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is _normal_, meaning it satisfies ![AA^\sfT = A^\sfT A](./images/ed2a0e0284ecaeeb8eaeb349c8d2a298d8b029a4.png), we can choose ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) to be an orthogonal matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) that satisfies ![O^\sfT O = \mathbbm{1}](./images/4f6851492efed417c5e16f7e04619f1289b89914.png). Calculating the inverse of an orthogonal matrix is easy: ![O^{-1}=O^\sfT](./images/cddecdde9c2896ba5abef768162e08bbc73b3542.png). The eigendecomposition for normal matrices is ![A = O \Lambda O^\sfT](./images/5fb620b0c1b0c45951af03774a36b6c5267fb2f9.png).

###[Singular value decomposition](./Front matter.md)

We can generalize the concepts of eigenvalues and eigenvectors to non-square matrices. Consider a matrix ![A \in \mathbb{R}^{m \times n}](./images/9b75a79d1ec9d3319f7ee4dc22498831c17415e5.png). Since the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is not a square matrix, we can’t use the standard eigendecomposition. However, there is a trick for turning a non-square matrix into a square matrix while preserving some of its properties: multiply the matrix by its transpose. The matrix ![A A^\sfT \in \mathbb{R}^{n \times n}](./images/4246adb39a0f2ae8a1f3d7deb74acbf1d6515327.png) has the same column space as the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Similarly, ![A^\sfT A \in \mathbb{R}^{m \times m}](./images/22b9046f98cabf90194fd9a1cce6eced170afeae.png) has the same row space as the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

The _singular value decomposition_ breaks a matrix into the product of three matrices: an ![m\times m](./images/2322ada5aede7496c64841e769698afafffbb942.png) orthogonal matrix ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) which consists of _left singular vectors_, an ![m \times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrix ![\Sigma](./images/d39a5eaeec3a326b9cea2deac91a6b9083fdc4dc.png) with the _singular values_ ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png) on the diagonal, and an ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) orthogonal matrix ![V^\sfT](./images/87478ea0be889391f8791e5603b7495e8704d3ff.png) of _right singular vectors_:

![A \; = \; 
\underbrace{ \!\!
\begin{bmatrix}
\vert  &  & \vert \\
\hat{u}_1  &  \!\cdots \! &  \hat{u}_m \\
\vert  &  & \vert 
\end{bmatrix}\!\!
}_U
\; 
\underbrace{\!\!
\begin{bmatrix}
\sigma_1 & 0 		& \cdots \; \;  \\
0	  & \sigma_2	& \cdots \; \;  \\
0 	  & 0			& \cdots \; \; 
\end{bmatrix}\!\!
}_\Sigma
\; 
\underbrace{\!\!
\begin{bmatrix}
\textrm{ ---} & \hat{v}_{1}  & \textrm{--- }  \\
& \vdots &  \\
\textrm{ ---} & \hat{v}_{n} & \textrm{--- } 
\end{bmatrix}\!\!
}_{V^\sfT}
\; = \; U\Sigma V^\sfT.](./images/32d7b88dce50d0b384e297e668e458086b7414d2.png)

To find the matrices ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png), ![\Sigma](./images/d39a5eaeec3a326b9cea2deac91a6b9083fdc4dc.png), and ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), perform eigendecomposition on the matrix products ![AA^\sfT](./images/c0e4c506d0a9d20e0630f3bdcd2e4cfa6953f244.png) and ![A^\sfT\! A](./images/d5ea84f3e435617427dcf6e8309c287b9de3ad16.png).

Consider first the matrix ![AA^\sfT](./images/c0e4c506d0a9d20e0630f3bdcd2e4cfa6953f244.png). Since ![AA^\sfT](./images/c0e4c506d0a9d20e0630f3bdcd2e4cfa6953f244.png) is a square matrix, we can compute its eigendecomposition ![AA^\sfT = U \Lambda_\ell U^\sfT](./images/374b6f33271f79d0330d3e32d40422acb99ea5af.png). The eigenvectors of ![AA^\sfT](./images/c0e4c506d0a9d20e0630f3bdcd2e4cfa6953f244.png) span the same space as the column space of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). We call these vectors the _left singular vectors_ of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

The left singular vectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) (the columns of ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png)) are the eigenvectors of the matrix ![A A^\sfT](./images/c0e4c506d0a9d20e0630f3bdcd2e4cfa6953f244.png):

![U=     
\begin{bmatrix}
\vert  &  & \vert \\
\hat{u}_1  &  \cdots &  \hat{u}_m \\
\vert  &  & \vert 
\end{bmatrix}\!, 
\; \; \; 
\textrm{ where } 
\{ (\lambda_i,\hat{u}_i) \} 
= \textrm{eigenvects}(AA^\sfT).](./images/949da6aabd0988ca6ce8a10b27b6054f0cc91abc.png)

To find the right singular vectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) (the rows of ![V^\sfT](./images/87478ea0be889391f8791e5603b7495e8704d3ff.png)), perform the eigendecomposition on the matrix ![A^\sfT \!A](./images/d5ea84f3e435617427dcf6e8309c287b9de3ad16.png), denoted ![A^\sfT \!A = V \Lambda_r V^\sfT](./images/b6bfa25ed24f9701955069c6b4577f8d30789471.png). Build the orthogonal matrix ![V^\sfT](./images/87478ea0be889391f8791e5603b7495e8704d3ff.png) by stacking the eigenvectors of ![A^\sfT \!A](./images/d5ea84f3e435617427dcf6e8309c287b9de3ad16.png) as rows:

![V^\sfT =
\begin{bmatrix}
\textrm{ ---} & \!\hat{v}_{1}\!  &  \textrm{--- } \\
& \vdots &  \\
\textrm{ ---} & \!\hat{v}_{n}\! & \textrm{--- }
\end{bmatrix}\!,
\; \; \; 
\textrm{ where } 
\{ (\lambda_i,\hat{v}_i) \} 
= \textrm{eigenvects}(A^\sfT A).](./images/375c0a868600164fef7207fdd2d7f634e684bb26.png)

The eigenvalues of the matrix ![A^\sfT \!A](./images/d5ea84f3e435617427dcf6e8309c287b9de3ad16.png) are the same as the eigenvalues of the matrix ![AA^\sfT](./images/c0e4c506d0a9d20e0630f3bdcd2e4cfa6953f244.png). In both cases, the eigenvalues ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png) correspond to the squares of the singular values of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

On its diagonal, the matrix of singular values ![\Sigma \in \mathbb{R}^{m\times n}](./images/5f44d2dc6782c9cde2ff37c3101636ab4048920a.png) contains the singular values ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png), which are the positive square roots of the eigenvalues ![\lambda_i](./images/c899545dcb352ceed3bd5758ec0d3aa996f1d6dc.png) of the matrix ![AA^\sfT](./images/c0e4c506d0a9d20e0630f3bdcd2e4cfa6953f244.png) (or the matrix ![A^\sfT A](./images/c9c50a5ffab5c448763dde9a00195e1462369257.png)):

![\sigma_i = \sqrt{ \lambda_i }\;, \; \; \; 
\textrm{ where } \{ \lambda_i \} = \textrm{eigenvals}(AA^\sfT) = \textrm{eigenvals}(A^\sfT A).](./images/be12d2b3998734d065f6ed8df8e563db3eb1d265.png)

The singular value decomposition shows the inner structure of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). We can interpret the operation ![\vec{y} = A\vec{x} = U\Sigma V^\sfT\vec{x}](./images/db228d083b77e61003435b2fd47b64b6f8905174.png) as a three-step process:

1.  Convert the input ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) to the basis of right singular vectors ![\{ \vec{v}_i \}](./images/4c01a1c142d7c154921cdcea613fb106ac85604a.png).
2.  Scale each component by the corresponding singular value ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png).
3.  Convert the output from the ![\{ \vec{u}_i \}](./images/2adbc52c86419269a6e06fabc3c2e5554fb44135.png) basis to the standard basis.

This three-step procedure is analogous to the three-step procedure we used to understand the eigendecomposition of square matrices in[Section 6.1](./Chapter 6_ Theoretical linear algebra.md) (see page 6.1.5.3).

The singular value decomposition (SVD) has numerous applications in statistics, machine learning, and computer science. Applying the SVD to a matrix is like looking inside it with X-ray vision, since you can see its ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png)s. The action of ![A=U\Sigma V^\sfT](./images/a4afc5c0534e90b7196af8c88e6abb9d87256029.png) occurs in ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) parallel streams: the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th stream consists of multiplying the input vector by the right singular vector ![\vec{v}_i^\sfT](./images/8a649978a1c072fa654ecbf50a18fe08d43a2df9.png), scaling by the weight ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png), and finally multiplying by the left singular vector ![\vec{u}_i](./images/6bab6bec1fed9b6fe08b826863602a20207bb02f.png). Each singular value ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png) corresponds to the “strength” of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) on the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th subspace—the subspace spanned by its ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th left and right singular vectors.

#####[Example](./Front matter.md)

Suppose you need to calculate the product ![M\vec{v}](./images/a2233aa21d00d349c36f1a56f7976108fb9d00ba.png) where ![M \in \mathbb{R}^{1000\times2000}](./images/8ccb3c6ca240df8ad2f13e57cda2b8b4b27bac42.png) and ![\vec{v} \in \mathbb{R}^{2000}](./images/3645062a40f5913cd2eb85cd053ccdcbeca9423c.png). Suppose furthermore the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) has only three large singular values, ![\sigma_1=6](./images/b06bfc964f66a99bca0201db57303c80cdfcd930.png), ![\sigma_2=5](./images/919ba0b0643d4594cecaf566c2ccaf5f1b43cdfc.png), ![\sigma_3=4](./images/253cf1f5b4d79881cc6d1a9d0600ed4bd518a6cb.png), and many small singular values, ![\sigma_4=0.0002, \sigma_5=0.0001, \ldots, \sigma_{1000}=1.1\times10^{-13}](./images/964f5c261b58391a1f1cffc406b9405feb8aaabe.png). Observe that most of the “weight” of the matrix ![\Sigma](./images/d39a5eaeec3a326b9cea2deac91a6b9083fdc4dc.png) is concentrated in the first three singular values, ![\sigma_1](./images/19681a860e60cceaafdb213984eeb086776d1484.png), ![\sigma_2](./images/c1024ed108bb5223f54ddb6e127918b325310b78.png), and ![\sigma_3](./images/ec25a173cdfd417517c6f4dd44f7e93f1b953e6b.png). We can obtain a _low-rank approximation_ to the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) by keeping only the large singular values and their associated singular vectors. Construct the matrix ![\tilde{\Sigma} \in \mathbb{R}^{3\times 3}](./images/ad413db5e64a96e18b6c909936766dec7bae301b.png) which contains only the first three singular values, and surround ![\tilde{\Sigma}](./images/a338ccb0dc5f632951c8334cc88b2d8597f1beec.png) with matrices ![\tilde{U} \in \mathbb{R}^{1000\times 3}](./images/70f3cdb9d2760da6eb991d5c93e842ed2096510d.png) and ![\tilde{V}^\sfT \in  \mathbb{R}^{3\times 2000}](./images/badaf7845684d1c1814e737c768554e74347ad35.png) which contain the singular vectors associated with the first three singular values. Despite the significant reduction in the size of the matrices used in the decomposition, the matrix ![\tilde{M} = \tilde{U} \tilde{\Sigma} \tilde{V}^\sfT \in \mathbb{R}^{1000\times 2000}](./images/e99b6016546a80d11dfa8977fd628476c7fe4f1e.png) represents a good approximation to the original matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). We cut some small, insignificant singular values, which doesn’t change the matrix too much. We can quantify the difference between the original ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) and its low-rank approximation ![\tilde{M}](./images/0e40833043886b05a728d81fcbb15f92024c1260.png) using the Hilbert–Schmidt norm: ![\|M-\tilde{M}\|_{\textrm{HS}} = \sqrt{ \sum_{i=4}^{1000} \sigma_i^2 }](./images/d4e1166c5fad8259fc626cee9a2f9396b8c09c71.png). Since ![\sigma_4, \sigma_5, \ldots, \sigma_{1000}](./images/2b8049ef3e843c59c0641d1db8d083dd0a8eca26.png) are tiny numbers, we can say ![\tilde{M} \approx M](./images/881816b2b2825a67447874797435aa30d8f57fed.png).

####[Links](./Front matter.md)

\[ Singular value decomposition on Wikipedia \]

[`http://en.wikipedia.org/wiki/Singular_value_decomposition`](./Singular_value_decomposition.md)

\[ Excellent blog post series that explains the SVD intuitively \]

Part 1, motivation:[`https://jeremykun.com/?p=5946`](./_p=5946.md)

Part 2, computations:[`https://jeremykun.com/?p=8329`](./_p=8329.md)

\[ Understanding the SVD and its applications \]

[`http://www.math.umn.edu/~lerman/math5467/svd.pdf`](./svd.pdf.md)

\[ Principal component analysis in statistics is based on SVD \]

[`http://en.wikipedia.org/wiki/Principal_component_analysis`](./Principal_component_analysis.md)

###[LU decomposition](./Front matter.md)

Computing the inverse of a triangular matrix is far easier than computing the inverse of a general matrix. Thus, for computational purposes, it’s sometimes useful to write a matrix as the product of two triangular matrices. We call this factorization the ![LU](./images/d700b3024ab22b765ed99f5e4830ddb32d926aab.png) decomposition:

![A = LU,](./images/f825d1f2371793b5b6550e27d3116740fed60b17.png)

where ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) is an _upper triangular_ matrix and ![L](./images/8344682567e06566040f4cde165f91b06c4ee6f5.png) is a _lower triangular_ matrix.

The main application of this decomposition is to obtain more efficient solutions to equations of the form ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png). Because ![A=LU](./images/b2bbd8b7c12096fd98d716d2d4d62238de9d9e67.png), we can solve this equation in two steps. Starting from ![LU\vec{x}=\vec{b}](./images/fe5dfa2ee43a50691aae34fefecd8f3c838377c6.png), first multiply by ![L^{-1}](./images/aae09ce5706767bfeba978562e5dfd53d3e73d18.png) and then by ![U^{-1}](./images/ef208fedcd0049f5b093064a688e8a4436646e6a.png):

![LU\vec{x} = \vec{b}
\quad
\Rightarrow 
\quad
L^{-1}LU\vec{x}=U\vec{x}=L^{-1}\vec{b}
\quad
\Rightarrow 
\quad
\vec{x}=U^{-1}L^{-1}\vec{b}.](./images/c742f6be15fd2935badb91bac761c2c7839e946b.png)

We’ve split the work of finding the inverse ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png) into two simpler subtasks: finding ![L^{-1}](./images/aae09ce5706767bfeba978562e5dfd53d3e73d18.png) and ![U^{-1}](./images/ef208fedcd0049f5b093064a688e8a4436646e6a.png), which are easier to compute.

The ![LU](./images/d700b3024ab22b765ed99f5e4830ddb32d926aab.png) decomposition is mainly used for linear algebra calculations on computers, but it’s also possible to find the ![LU](./images/d700b3024ab22b765ed99f5e4830ddb32d926aab.png) decomposition of a matrix by hand. Recall the algorithm for finding the inverse of a matrix, in which we start from the array ![[\,A\,|\;\mathbbm{1}\;]](../Images/99316346f44937a2a7d39e935c178b73ef2813c0.png) and perform row operations to bring the array into reduced row echelon form ![[\;\mathbbm{1}\; |\,A^{-1}\,]](../Images/ef35a70727afaf732412a1dcbcf669e0998c6b3c.png). Consider the midpoint of the algorithm when the left side of the array is the row echelon form (REF). Since the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) in its REF is upper triangular, the array will contain ![[\; U\;|\,L^{-1}\,]](../Images/1bc827518360cda2d300cd03c00789cbda7002d2.png). The ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) part of the decomposition is on the left side, and the ![L](./images/8344682567e06566040f4cde165f91b06c4ee6f5.png) part is obtained by finding the inverse of the right side of the array.

Note the ![LU](./images/d700b3024ab22b765ed99f5e4830ddb32d926aab.png) decomposition exists only for matrices that can be brought to RREF without using row-swap operations. If a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) requires row-swap operations to be transformed to RREF, we can decompose it as ![A=PLU](./images/17ddf30d96e21e94c5b132235ee161e27ad1438d.png), where ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png) is a permutation matrix. The ![PLU](./images/b51d42fbf7d129793fd6d0da2bbc1148a39d8eb2.png) decomposition has the same computational advantages of splitting the inverse computation into three simpler subtasks: ![A^{-1} = U^{-1}L^{-1}P^{-1}](./images/a5c1b71b6cf62bba1017fd72b4031e0e1fb3c495.png).

###[Cholesky decomposition](./Front matter.md)

For a _symmetric_, _positive semidefinite_ matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), the ![LU](./images/d700b3024ab22b765ed99f5e4830ddb32d926aab.png) decomposition can take on a simpler form. Such matrices can be written as the product of a triangular matrix and its transpose:

![A = LL^\sfT \quad \textrm{or} \quad   A=U^\sfT U,](./images/781a535b08faed55cbc0cd0495cf1ae59d491689.png)

where ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) is an _upper triangular_ matrix and ![L](./images/8344682567e06566040f4cde165f91b06c4ee6f5.png) is a _lower triangular_ matrix. This is called the _Cholesky decomposition_ of a matrix, and like the ![LU](./images/d700b3024ab22b765ed99f5e4830ddb32d926aab.png) decomposition, it has applications for faster numerical linear algebra calculations, nonlinear optimization, and machine learning.

###[QR decomposition](./Front matter.md)

Any real square matrix ![A \in \mathbb{R}^{n\times n}](./images/2f056442410016d3a541715471950849562de0c4.png) can be decomposed as a product of an orthogonal matrix ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) and an upper triangular matrix ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png):

![A = OU.](./images/5e3197e23a5fed6b676231bddb3d9f5c240df6fd.png)

For historical reasons, the orthogonal matrix is denoted ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) instead of ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png), and the upper triangular matrix is denoted ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) (think “right-triangular” since it contains entries only to the _right_ of the main diagonal). Using the conventional names, the decomposition becomes

![A = QR,](./images/3c2d6b24332d716dc802ab38bde697cd4aaad13f.png)

which is why it’s known as the ![QR](./images/1aedd31dee0f0d59e9beeb4a637c1a45974f3ffd.png) decomposition.

The ![QR](./images/1aedd31dee0f0d59e9beeb4a637c1a45974f3ffd.png) decomposition is equivalent to the Gram–Schmidt orthogonalization procedure applied to the columns of the matrix. The matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) records the orthonormal basis while the matrix ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) contains the coefficients required to express the columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as linear combinations of the columns of ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png).

#####[Example](./Front matter.md)

Consider the decomposition

![A = 
\begin{bmatrix}
12 & -51 & 4 \\
6 & 167 & -68 \\
-4 & 24 & -41 
\end{bmatrix}
= QR.](./images/6a4d47cdec28759634cd69ffad68935c694b1d04.png)

We’re looking for an orthogonal matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) and an upper triangular matrix ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) such that ![A=QR](./images/1cfd8e741adc996641195d3847f8fc81b491d1cc.png). We can obtain the orthogonal matrix ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) by performing the Gram–Schmidt procedure on the columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

Let’s illustrate the procedure by computing the factorization ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Begin by changing the second column in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) so it becomes orthogonal to the first (by subtracting a multiple of the first column). Next, change the third column in ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) so it is orthogonal to both of the first columns (by subtracting multiples of the first two columns). We obtain a matrix with the same column space as ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), but which has orthogonal columns:

![\begin{bmatrix}
\vert & \vert & \vert \\
\mathbf u_1 & \mathbf u_2 & \mathbf u_3 \\
\vert & \vert & \vert 
\end{bmatrix}
=
\begin{bmatrix}
12 & -69 & -\frac{58}{5} \\
6  & 158 & \frac{6}{5} \\
-4 &  30 & -33 
\end{bmatrix}\!.](./images/5a2c86ba0f0ed7973d5e64b33fc16ba3ac8f95a2.png)

To obtain an orthogonal matrix, we must normalize each column to have length one:

![Q = 
\begin{bmatrix}
\vert & \vert & \vert \\
\frac{\mathbf u_1}{\|\mathbf u_1\|} & 
\frac{\mathbf u_2}{\|\mathbf u_2\|} & 
\frac{\mathbf u_3}{\|\mathbf u_3\|} \\
\vert & \vert & \vert 
\end{bmatrix}
=
\begin{bmatrix}
\frac{6}{7}    &    -\frac{69}{175}   &   -\frac{58}{175}   \\
\frac{3}{7}    &    \frac{158}{175}   &     \frac{6}{175}   \\
-\frac{2}{7}    &      \frac{6}{35}    &   -\frac{33}{35}    
\end{bmatrix}\!.](./images/678c03317d35337c87cb2e0d4cda6267fd3f1bf3.png)

We can obtain the matrix ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) from ![Q^\sfT](./images/713a7f6ecce45601420769acfead0a2067d6091e.png) and ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):

![Q^\sfT  A = \; \underbrace{\!Q^\sfT Q\!}_{\mathbbm{1}}\,R = R
\qquad  \Rightarrow \qquad 
\begin{matrix}
R = Q^\sfT A =
\end{matrix}
\begin{bmatrix}
14  &  21          &            -14 \\
0  & 175          &           -70 \\
0  &   0          &          35
\end{bmatrix}\!.](./images/782d3e120452730abd300a29024adb0d7ba4c774.png)

The columns of ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) contain the mixture of coefficients required to obtain the columns of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) from the columns of ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png). For example, the second column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is equal to ![21\frac{\mathbf u_1}{\|\mathbf u_1\|}+175\frac{\mathbf u_2}{\|\mathbf u_2\|}](./images/672b80f20d1721652de179133cdb96024c8722ca.png).[Verify that ![QR](./1aedd31dee0f0d59e9beeb4a637c1a45974f3ffd.png.md) equals ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).](http://bit.ly/1c2Wjxk)

###[Discussion](./Front matter.md)

The last several pages have only scratched the surface of matrix decompositions. There are countless applications for matrix methods, and matrix factorizations play key roles in many of them.

Machine learning techniques often use matrix decompositions to uncover useful structure within data matrices. Two examples include _nonnegative matrix factorization_ (used for recommender systems) and _latent Dirichlet allocation_ (used for document classification). I encourage you to research this subject further on your own—it’s quite an interesting wormhole to get sucked into.

###[Links](./Front matter.md)

\[ Cool retro video showing the steps of the SVD procedure \]

[`http://www.youtube.com/watch?v=R9UoFyqJca8`](./watch_v=R9UoFyqJca8.md)

\[ More info and examples on Wikipedia \]

[`http://en.wikipedia.org/wiki/Matrix_decomposition`](./Matrix_decomposition.md)

[`http://en.wikipedia.org/wiki/Cholesky_decomposition`](./Cholesky_decomposition.md)

\[ A detailed example of the QR factorization of a matrix \]

[`http://www.math.ucla.edu/~yanovsky/Teaching/Math151B/handouts/GramSchmidt.pdf`](./GramSchmidt.pdf.md)

###[Exercises](./Front matter.md)

E6.18 Compute the ![QR](./images/1aedd31dee0f0d59e9beeb4a637c1a45974f3ffd.png) factorization of the matrix ![A=\begin{bmatrix}1 & 1 & 0 \\ 1 & 0 & 1 \\ 0 & 1 & 1 \end{bmatrix}](./images/b5a418569c16eef6afdddf028b3789f649cca48b.png).

##[6.7 Linear algebra with complex numbers](./Chapter 6_ Theoretical linear algebra.md)

So far we’ve discussed the math of vectors and matrices with real components. In fact, the linear algebra techniques you’ve learned apply to any _field_ ![F](./images/fde085937972221cc351ca105835c8b5a11aa591.png). The term _field_ applies to any mathematical object for which the operations of addition, subtraction, multiplication, and division are defined.

Since the complex numbers ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png) are a field, we can perform linear algebra over the field of complex numbers. In this section, we’ll define vectors and matrices with complex components, and discover that they behave similarly to their real counterparts. You’ll see that complex linear algebra is no more complex than real linear algebra. It’s the same, in fact, except for one small difference: instead of matrix transpose ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png), we use the Hermitian transpose ![A^\dagger](./images/3763a4fed4d19a6bb65a04d027dc9aa010a3ee60.png), which is the combination of the transpose and an entry-wise complex conjugate operation.

Complex vectors are not just an esoteric mathematical concept intended for specialists. Complex vectors can arise as answers for problems involving ordinary real matrices. For example, the rotation matrix

![R_\theta = 
\begin{bmatrix}
\cos\theta	&-\sin\theta \\
\sin\theta	&\cos\theta
\end{bmatrix}](./images/bdea29cc42f0caf9550c2589f8df5add5cae225c.png)

has complex eigenvalues ![\lambda_1 = e^{i\theta}](./images/dd6f8dc317ae804f00b8af018105d38770281f42.png) and ![\lambda_2 = e^{-i\theta}](./images/facf36a15ee90959c80b071bab0fb7d31c1ed72d.png) and its eigenvectors have complex components. If you want to know how to calculate the eigenvalues and eigenvectors of rotation matrices, you need to understand how to do linear algebra calculations with complex numbers. This section serves as a review of all the important linear algebra concepts we’ve learned in this book. I recommend you read this section, even if you’re not required to know about complex matrices for your course. As your guide through the land of linear algebra, it’s my duty to make sure you understand linear algebra in the complex field. It’s good stuff; I guarantee there’s _knowledge buzz_ to be had in this section.

###[Definitions](./Front matter.md)

Recall the basic notions of complex numbers introduced in[Section 1.14](./Chapter 1_ Math fundamentals.md):

-   ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png): the unit imaginary number; ![i = \sqrt{-1}](./images/5ed82d597f14e08c1179a4d111111d566b6f2211.png) and ![i^2 = -1](./images/8f6a05a5a173cf1a23631e03a53b0a172a46ad47.png)
-   ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png): a complex number ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png) whose real part is ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and whose imaginary part is ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)
-   ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png): the set of complex numbers ![\mathbb{C} = \{ a + bi \;  | \;  a,b \in \mathbb{R} \}](./images/bab8ac9a1b7564978e7b048685457da2993909e3.png)
-   ![\textrm{Re}\{ z \}=a](./images/8b547f862cc767345407ed8c9d15d7cfcb040df6.png): the _real_ part of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)
-   ![\textrm{Im}\{ z \}=b](./images/f4a43c5803f6b41ac5012e4f5528ec4708e9a5de.png): the _imaginary_ part of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)
-   ![\overline{z}](./images/4d0c81dad43b59bde68acab0e73db28d9cd30db1.png): the _complex conjugate_ of ![z](./images/dff32fac745617b7679cd31834f9c8040825f652.png). If ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png) then ![\overline{z}=a-bi](./images/5f7e626aa098fb8021f6523d683f1bcf7468ec57.png)
-   ![|z|=\sqrt{ \overline{z}z }=\sqrt{a^2+b^2}](./images/afcb5e9b1dbf33e480d82a7090c16166c1557e83.png): the _magnitude_ or _length_ of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)
-   ![\arg(z)=\tan^{-1}(\frac{b}{a})](./images/6d17e44c040d42c5aeb757f7b141f9b97e96491d.png): the _phase_ or _argument_ of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png). Note that ![\tan^{-1}(\frac{b}{a})](./images/da171425ddc94e63b47a17266c88d53222d4bcc6.png) and ![\arg(z)](./images/0408560d31031681ca5015dd3da5569a71e1c908.png) coincide only if ![a\geq 0](./images/fb42b8500d8af2d509e0f54265e3b928e1bc6de8.png). A correction is necessary to the output of ![\tan^{-1}(\frac{b}{a})](./images/da171425ddc94e63b47a17266c88d53222d4bcc6.png) when ![a<0](./images/afe4de135c31514e0ca9cb0381b047fa3758386e.png). The computer function `atan2(b,a)` returns the correct phase for all ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png).

####[Complex vectors](./Front matter.md)

A complex vector ![\vec{v} \in \mathbb{C}^n](./images/b98e3b08cb0c46724f3a01a80b36e86792eed6ec.png) is an array of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) complex numbers:

![\vec{v} = (v_1,v_2, \ldots, v_n) \;  \;  \in \;  \;  \mathbb{C}^n.](./images/3311ef243cce53b00f70cc979ee7a2ae965a78ea.png)

####[Complex matrices](./Front matter.md)

A complex matrix ![A \in \mathbb{C}^{m\times n}](./images/a50a3038b1dc969c86e3656550abc0374c7bc238.png) is a table of numbers with ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) rows and ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) columns. An example of a ![3\times 2](./images/3247cd7695abad3cf4c4a69c536cd715d34202d1.png) matrix with complex entries is

![A = \begin{bmatrix}
a_{11} & a_{12}	\\
a_{21} & a_{22} 	\\
a_{31} & a_{32} 
\end{bmatrix}
\; \; 
\in
\; \; 
\mathbb{C}^{3\times 2}.](./images/16e615dccbad2dc2d7df9234af4ae953794c377e.png)

####[Hermitian transpose](./Front matter.md)

The _Hermitian transpose_ operation, denoted ![^\dagger](./images/2361096691b9ceb31e69175e5eaef6c35445c863.png), consists of the combination of the regular transpose (![A \to A^\sfT](./images/def8a4c136ab174427487e7d1447cb30e3a48a2c.png)) and the complex conjugation of each entry in the matrix (![a_{ij} \to \overline{a_{ij}}](./images/734b41d16fd774d6575d8adb95be38844b04bdd2.png)):

![A^\dagger 	\,\eqdef\, \overline{(A^\sfT)}=(\overline{A})^\sfT.](./images/0b673e839e460e2d4b09314cfd9663d40cb7bf78.png)

Expressed in terms of the entries of the matrix ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png), the Hermitian transpose corresponds to the transformation ![a_{ij} \to \overline{ a_{ji} }](./images/6a0988ec9bc124b4578e07159f8534399cbbf674.png). There are _many_ mathematical terms that refer to this operation, including _Hermitian conjugate_, _complex transpose_, “dagger” operation, _conjugate transpose_, and _adjoint_.

The term _adjoint_ is preferred by mathematicians and the notation ![A^*](./images/cddb391b7cce85df91837db748837519d9f630e5.png) is used consistently in mathematics research papers. The dagger notation ![^\dagger](./images/2361096691b9ceb31e69175e5eaef6c35445c863.png) is preferred by physicists and engineers, but shunned by mathematicians. Mathematicians prefer to stick with the star superscript because they feel they invented the concept. We use the notation ![^\dagger](./images/2361096691b9ceb31e69175e5eaef6c35445c863.png) in this book because at some point the author had to make an allegiance with one of the two camps, and because the symbol ![^\dagger](./images/2361096691b9ceb31e69175e5eaef6c35445c863.png) looks a bit like the transpose symbol ![^\sfT](./images/a462348fa44a14519bb7f3a98207adcc6cb061da.png).

The Hermitian transpose applied to a ![3\times2](./images/3247cd7695abad3cf4c4a69c536cd715d34202d1.png) matrix acts as follows:

![\textrm{if }
A = 
\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
a_{31} & a_{32}
\end{bmatrix}
\quad
\textrm{ then }
\quad
A^\dagger = 
\begin{bmatrix}
\overline{a_{11}} & \overline{a_{21}} & \overline{a_{31}} \\
\overline{a_{12}} & \overline{a_{22}} &  \overline{a_{32}} 
\end{bmatrix}.](./images/1250ac92f4c368e6e18470294e04a8aa9792c613.png)

Recall that vectors are special types of matrices. We can identify a vector ![\vec{v} \in \mathbb{C}^n](./images/b98e3b08cb0c46724f3a01a80b36e86792eed6ec.png) with a column matrix ![\vec{v} \in \mathbb{C}^{n \times 1}](./images/608f970a25a7e5a86d6b99213fe555a037277468.png) or with a row matrix ![\vec{v} \in \mathbb{C}^{1 \times n}](./images/711d2ef712dded92c28c9d19b0a49c32ec110fe7.png). We apply the complex conjugation operation to transform column vectors into conjugate row vectors:

![\vec{v}^\dagger 	\,\eqdef\,	\overline{(\vec{v}^\sfT)}=(\overline{\vec{v}})^\sfT.](./images/e768fa8fe8033cd2524f44f5360e64abb03b3885.png)

The Hermitian transpose of a column vector is a row vector in which each component has been complex-conjugated:

![\textrm{if }			
\vec{v} = 
\begin{bmatrix}
\alpha \\
\beta  \\
\gamma
\end{bmatrix}
\quad
\textrm{ then }
\quad			
\vec{v}^\dagger
=
\begin{bmatrix}
\alpha \\
\beta  \\
\gamma
\end{bmatrix}^\dagger
= 
\begin{bmatrix}
\overline{\alpha}	& \overline{\beta} 	& \overline{\gamma}
\end{bmatrix}\!.](./images/6d9d8951bf353f8132106f5c61368323ea905c32.png)

The Hermitian transpose for vectors is important because it’s related to the definition of the inner product for complex vectors.

####[Complex inner product](./Front matter.md)

The inner product for vectors with complex components ![\vec{u}, \vec{v} \in \mathbb{C}^n](./images/b69b9975d1c18c4f1f20f489bb797ae4f4347e3b.png) is defined as the following operation:

![\langle \vec{u}, \vec{v} \rangle 
\,\eqdef\, \sum_{i=1}^n \overline{u_i} v_i
= \vec{u}^\dagger \vec{v}.](./images/49c2add56b1abc834ec535312a00e9a5fcb331ed.png)

In this expression, complex conjugation is applied to the components of the first vector. This corresponds to the notion of applying the Hermitian transpose to the first vector to turn it into a row vector of complex conjugates, then using the matrix multiplication rule for a ![1 \times n](./images/d470d6249220dd5f738c22ef1592c3a0bc5bd50e.png) matrix ![\vec{u}^\dagger](./images/5610f659e870b33fcbb6111c4f22d8d956a92f01.png) times an ![n \times 1](./images/3090ba3f3c80de1e80bc520aaec116200eb116f6.png) matrix ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png).

For real vectors ![\vec{u}, \vec{v} \in \mathbb{R}^n](./images/07862d1e19e84ed614920b490c86af5f7f625961.png), the complex inner product formula reduces to the inner product formula we used previously: ![\vec{u} \cdot \vec{v} = \vec{u}^\sfT \vec{v}](./images/0706e38fb1eecc10212ced24a34cf3862121f82c.png). Rather than thinking of the inner product for complex vectors as a new operation, we can say the inner product has always been defined as ![\langle \vec{u}, \vec{v} \rangle = \vec{u}^\dagger \vec{v}](./images/738e0d835a682bceae59f7bae6a7e19e8cc27d50.png)—we just never noticed until now because complex conjugation has no effect on vectors with real components. Specifically, ![\vec{u}^\dagger = \vec{u}^\sfT](./images/2519c236ab4f4573a01a41ae336f55c230c85afc.png) if all the ![u_i](./images/591118fba36dc2f9dc391498e04c7f38ef7032c7.png)s are real numbers.

###[Linear algebra over the complex field](./Front matter.md)

One of the fundamental linear algebra ideas we’ve learned is how to use _linear transformations_ to model input-output phenomena in which input vectors ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) are linearly transformed to output vectors: ![\vec{w}=T(\vec{v})](./images/6aa95b3a44d6864e1530428c8e2c4f63bd5023f4.png). Linear transformations are functions of the form ![T:\mathbb{R}^m \to \mathbb{R}^n](./images/7d5634bf6f463494b224a3f14177a00cb0801d15.png). We can _represent_ these linear transformations as ![m\times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrices _with respect to_ some choice of input and output bases.

These linear algebra ideas also apply to complex vectors and complex matrices. For example, a linear transformation from ![T: \mathbb{C}^2 \to \mathbb{C}^2](./images/3807b0209e1fa030e56a51d010827556d441a575.png) can be represented as the matrix multiplication

![\begin{bmatrix}
w_1 \\
w_2  
\end{bmatrix}
=
\begin{bmatrix}
\alpha 		&	\beta	\\
\gamma		& 	\delta	
\end{bmatrix}
\!\!
\begin{bmatrix}
v_1 \\
v_2  
\end{bmatrix}\!.](./images/3863773b3aa0752282ec72956ea48c62736328cd.png)

Each linear transformation ![T: \mathbb{C}^2 \to \mathbb{C}^2](./images/3807b0209e1fa030e56a51d010827556d441a575.png) corresponds to some ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix ![{\scriptscriptstyle \begin{bmatrix}
\alpha 		&	\beta	\\
\gamma		& 	\delta
\end{bmatrix}}](./images/20165cebc6e2d1c22ab3f1f0c3109eb1d785ebe4.png) with entries ![\alpha,\beta, \gamma,\delta \in \mathbb{C}](./images/fa9c66f5f9d98d4735dc4335613fefe55c5d4a7e.png).

The change from real entires to complex entires has the effect of doubling the number of parameters required to describe the transformation. A ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) complex matrix has eight parameters, not four. Where are those eight parameters, you ask? Here:

![\begin{bmatrix}
\alpha 		&	\beta	\\
\gamma		& 	\delta	
\end{bmatrix}
\; = \; 
\begin{bmatrix}
\textrm{Re}\{\alpha\} 	&	\!\!\textrm{Re}\{\beta\}	\\
\textrm{Re}\{\gamma\}	& 	\!\!\textrm{Re}\{\delta\}	
\end{bmatrix}
\; 
+
\; 
\begin{bmatrix}
\textrm{Im}\{\alpha\} 		&\!\!		\textrm{Im}\{\beta\}	\\
\textrm{Im}\{\gamma\}	&\!\! 		\textrm{Im}\{\delta\}	
\end{bmatrix}\!i.](./images/349baf887050bbc049f5d3461183deedf0c536a1.png)

Each of the four entries of the matrix has a real part and an imaginary part, making for a total of eight parameters to pick when specifying the matrix.

Similarly, to specify a vector ![\vec{v}=\mathbb{C}^2](./images/be356477fbf972b8aace77e177c07893d267df39.png) you need to specify four parameters:

![\begin{bmatrix}
v_1 \\
v_2  
\end{bmatrix}
=
\begin{bmatrix}
\textrm{Re}\{v_1\} \\
\textrm{Re}\{v_2\}  
\end{bmatrix}
+
\begin{bmatrix}
\textrm{Im}\{v_1\} \\
\textrm{Im}\{v_2\}  
\end{bmatrix}\!i.](./images/6df1dd9d542a825599c8f36ecc314161283b7727.png)

In practice, this doubling of dimensions doesn’t play a role in calculations because we usually perform algebra steps with the complex entries and rarely split the matrices into their real and imaginary parts.

All the linear algebra techniques you’ve learned also work with complex numbers, as you’ll see in the following examples.

#####[Example 1: Solving systems of equations](./Front matter.md)

Suppose you’re solving a problem that involves complex numbers and a system of two linear equations in two unknowns:

![\begin{align*}
z_1 + 2z_2     		& =  3+i \\
3z_1 + (9+i)z_2    	& =  6+2i.
\end{align*}](./images/7f51515234c6e93731ae1e6d35ba337bd4fd6e3e.png)

You’re asked to find the values of the unknowns ![z_1](./images/1444a218cd82124afaaeee40dc89564dfd07ebc2.png) and ![z_2](./images/064b779916d840018713acc29484ac15679e02a0.png).

The solutions ![z_1](./images/1444a218cd82124afaaeee40dc89564dfd07ebc2.png) and ![z_2](./images/064b779916d840018713acc29484ac15679e02a0.png) will be complex numbers, but apart from that, there’s nothing special about this problem—keep in mind, linear algebra with complex numbers is the same as linear algebra with real numbers, so the techniques you learned for real numbers work just as well for complex numbers. Now let’s solve this system of equations.

First observe that the system of equations can be written as a matrix-vector product:

![\underbrace{\!\!
\begin{bmatrix}
1 & 2 \\
3 & 9+i 
\end{bmatrix}\!\!}_{A}
\; 
\underbrace{\!\! 
\begin{bmatrix}
\, z_1\, \\
\, z_2 \,
\end{bmatrix}\!\!
}_{\vec{z}}
\; 
=
\; 
\underbrace{\!\!
\begin{bmatrix}
3+i \\
6+2i
\end{bmatrix}\!\!
}_{\vec{b}}\,.](./images/04b25108b161445f383980ea038ec4a54a04d98f.png)

We’ve expressed the system as a ![2 \times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) multiplying the vector of unknowns ![\vec{z}](./images/690dd011e497f9df247023ad063801b30627b1c7.png) (a ![2 \times 1](./images/ff0d917829459a76eae0ac57cc13fac67fe68ba0.png) matrix) to produce a vector of constants ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png) (another ![2 \times 1](./images/ff0d917829459a76eae0ac57cc13fac67fe68ba0.png) matrix). We can solve for ![\vec{z}](./images/690dd011e497f9df247023ad063801b30627b1c7.png) by multiplying both sides of the equation by the inverse matrix ![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png). The inverse matrix of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is

![A^{-1} =
\begin{bmatrix}
1 + \frac{6}{3 + i} & - \frac{2}{3 + i}\\
- \frac{3}{3 + i} & \frac{1}{3 + i}
\end{bmatrix} \!.](./images/f196aa888be38ca760c9ba420359a58152a6e4fa.png)

We can now compute the answer ![\vec{z}](./images/690dd011e497f9df247023ad063801b30627b1c7.png) using the equation ![\vec{z}=A^{-1}\vec{b}](./images/5f74c1632091419c1e7de2e1d1b36f7f2964c3fd.png):

![\begin{bmatrix}
z_1   \\
z_2
\end{bmatrix}
=
\begin{bmatrix}
1 + \frac{6}{3 + i} & - \frac{2}{3 + i}\\
- \frac{3}{3 + i} & \frac{1}{3 + i}
\end{bmatrix}
\!\!
\begin{bmatrix}
3+i\\
6 + 2i
\end{bmatrix}
=
\begin{bmatrix}
3+i + 6 - 4  \\
-3 + 2 
\end{bmatrix}
=
\begin{bmatrix}
5+i   \\
-1
\end{bmatrix}\!.](./images/c985582a1ce91f8320657b408e492f769cfaac46.png)

#####[Example 2: Finding the inverse](./Front matter.md)

We learned several approaches for computing matrix inverses in[Section 3.5](./Chapter 3_ Computational linear algebra.md). Here we’ll review the procedure for computing the inverse using row operations.

Given the matrix

![A = 
\begin{bmatrix}
1 & 2 \\
3 & 9+i 
\end{bmatrix}\!,](./images/ea964014b116917b16d8f323975b421c3a9f9460.png)

first build a ![2 \times 4](./images/5b3afde6284d094412117437aa0250ab2d440496.png) array that contains ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) on the left side and the identity matrix ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) on the right side:

![\quad \; \; 
\left[ 
\begin{array}{cc|cc}
1 & 2  	\,&\,  1 & 0  \\
3 & 9+i  	\,&\,  0 & 1  
\end{array}\right]\!.](../Images/2222dde6bf34ed792faf9beed8ab832497e4732b.png)

Now perform the Gauss–Jordan elimination procedure on the resulting ![2 \times 4](./images/5b3afde6284d094412117437aa0250ab2d440496.png) array.

1.  Subtract three times the first row from the second row (![R_2 \gets R_2 -3R_1](./images/fb500f7ee9892774999183ff5cc78dff5362cfac.png)) to obtain
    
    ![\left[ 
    \begin{array}{cc|cc}
    1 & 2  	\,&\,   1  & 0  \\
    0 & 3+i  	\,&\,   -3 & 1  
    \end{array} \right]\!.](../Images/99277ca82243cb1c6a0f45890d44b5fa127249d8.png)
    
2.  Perform ![R_2 \gets \frac{1}{3+i}R_2](./images/a42e9c8b305f1f8252ef73d9e421f140606b7c88.png) to create a pivot in the second row:
    
    ![\qquad \quad
    \left[ 
    \begin{array}{cc|cc}
    1 & 2  \,&\,   1  & 0  \\
    0 & 1  \,&\,   \frac{-3}{3+i} & \frac{1}{3+i} 
    \end{array} \right]\!.](../Images/1fd4040f3cd39e48d8eb5cc408052656551ab1db.png)
    
3.  Finally, perform ![R_1 \gets R_1 - 2R_2](./images/c9fe4f74671bcc370ee5e99a29db8b0e89f9af6c.png) to obtain the RREF:
    
    ![\qquad \qquad \quad \; 
    \left[ 
    \begin{array}{cc|cc}
    1 & 0  \,&\,   1 + \frac{6}{3+i}  & - \frac{2}{3+i}   \\
    0 & 1  \,&\,   \frac{-3}{3+i} & \frac{1}{3+i} 
    \end{array} \right]\!.](../Images/0a5d0ce067997f05e2a30525937f2706a7db64d0.png)
    

The inverse of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) appears on the right side of the array,

![A^{-1} =
\begin{bmatrix}
1 + \frac{6}{3 + i} & - \frac{2}{3 + i}\\
- \frac{3}{3 + i} & \frac{1}{3 + i}
\end{bmatrix}\!.](./images/f196aa888be38ca760c9ba420359a58152a6e4fa.png)

#####[Example 3: Linear transformations as matrices](./Front matter.md)

The effect of multiplying a vector ![\vec{v} \in \mathbb{C}^n](./images/b98e3b08cb0c46724f3a01a80b36e86792eed6ec.png) by a matrix ![M \in \mathbb{C}^{m\times n}](./images/35c34693eb3ade5a9457a89353f151f4932ee798.png) is the same as applying a linear transformation ![T_M:\mathbb{C}^n \to \mathbb{C}^m](./images/42b4394f74b290d93596aeeb94bfedf6e53146a0.png) to the vector:

![\quad
\vec{w} = M \vec{v} \qquad \quad \Leftrightarrow \qquad  \quad\vec{w} = T_M(\vec{v}).](./images/7745ecd9eb03404ea30ff98f94c33701f4abd6ec.png)

The opposite is also true—any linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) can be _represented_ as a multiplication by some matrix ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png):

![\vec{w} = T(\vec{v})  \qquad \quad \Leftrightarrow \qquad \quad \vec{w} = M_T \vec{v}.](./images/23207bad0f1b6ee2df95ee964cf83be7e6db4cbf.png)

We’ll use a simple example to review the procedure for finding the matrix representation of a linear transformation.

Consider the linear transformation ![T:\mathbb{C}^2 \to \mathbb{C}^2](./images/3807b0209e1fa030e56a51d010827556d441a575.png), which produces the input-output pairs

![T\!\left(
\begin{bmatrix}
1 \\ 0 
\end{bmatrix}
\right)
=
\begin{bmatrix}
3 \\ 2i 
\end{bmatrix}
\qquad
\textrm{and}
\qquad
T\!\left(
\begin{bmatrix}
0 \\ 2 
\end{bmatrix}
\right)
=
\begin{bmatrix}
2 \\ 4+4i 
\end{bmatrix}\!.](./images/7d3560be1ed12aa6457520a3dc5f8757fe336979.png)

How can we use the information provided above to find the matrix representation of the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png)?

To obtain the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) with respect to a given basis, we need to combine, as columns, the outputs of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) for the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) vectors of that basis:

![M_T = 
\begin{bmatrix} 
\vert & \vert &  & \vert \\
T(\vec{e}_1)  \!&\! T(\vec{e}_2) \!& \cdots &\! T(\vec{e}_n) \\
\vert & \vert &  & \vert 
\end{bmatrix}\!,](./images/3d3fc2e30dd6771d18cbe9d113d04c03e25e26a8.png)

where the set ![\{ \hat{e}_1,\hat{e}_2,\ldots, \hat{e}_n\}](./images/0bfc670a2906a6a127fa62f32efbfdb9754d60e2.png) is a basis for the input space.

The problem statement gives us the information needed for the first column of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png), but we’re not given the output of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) for ![\hat{e}_2](./images/4a63957434b4c53e36baba2d6b8fe95b725bd6e2.png). However, we can work around this limitation since we know ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is _linear_. The property ![T(\alpha \vec{v}) = \alpha T(\vec{v})](./images/da3a2477b59474d6c3b36af0ece80dd53ee2563e.png) implies

![T\!\left(
2
\begin{bmatrix}
0 \\ 1
\end{bmatrix}
\right)
=
2
\begin{bmatrix}
1 \\ 2+2i 
\end{bmatrix}
\qquad
\Rightarrow
\qquad
T\!\left(
\begin{bmatrix}
0 \\ 1
\end{bmatrix}
\right)
=
\begin{bmatrix}
1 \\ 2+2i 
\end{bmatrix}\!.](./images/f2e985ee8abc4f467977a27bc604095f2862b756.png)

Combining the information for ![T(\hat{e}_1)](./images/35befe18e88516bc4c9b366cc6323f0da982f42b.png) and ![T(\hat{e}_2)](./images/426daef9c8aa6af38b0e9b5b11f040c2451e6d36.png), we obtain the matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png):

![M_T=
\begin{bmatrix}
3 	&	1 	\\ 
2i	&	2+2i 
\end{bmatrix}\!.](./images/730ed23156ebe995b17cffdea1fbad6a8d7922f6.png)

###[Complex eigenvalues](./Front matter.md)

I want you to learn about linear algebra with complex vectors so that we can complete the classification of linear transformations in terms of their eigenvalues. Recall that projections obey ![\Pi=\Pi^2](./images/b8f331a00c096eb6b69429bd991b3fede5f6a0b0.png) and have eigenvalues zero or one, and reflections have at least one eigenvalue equal to ![-1](./images/092d11154a9fa6921a0a36a3dbbe143fde3c37d8.png).

What are the eigenvalues of rotation matrices? The eigenvalues of a matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are the roots of its characteristic polynomial ![p_A(\lambda)=\textrm{det}(A - \lambda \mathbbm{1})](./images/5d2706093fcd7fc76a4b2f04121350a3f2ccfc36.png). To find the eigenvalues of the rotation matrix ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) we defined in[Section 5.2.5](./Chapter 5_ Linear transformations.md) (page 5.2.5), we must find the solutions of the equation ![p_{R_\theta}(\lambda) =0](./images/838825192ea2ee2950e060c793c735a2628e5baa.png):

![\begin{align*}
0	&= p_{R_\theta}(\lambda) 							\\
&= \textrm{det}(R_\theta - \lambda \mathbbm{1})			\\
&= \textrm{det}\left( 
\begin{bmatrix}
\cos\theta -\lambda 	&-\sin\theta \\
\sin\theta	&\cos\theta -\lambda 
\end{bmatrix}
\right)										\\
&= (\cos\theta - \lambda)^2+\sin^2\theta.							 
\end{align*}](./images/9ecbb1dbeddce2d09be670765fa6ea2ea885b20f.png)

To solve for ![\lambda](./images/2b483570460a442eca4244e381d083d92497420a.png), first move ![\sin^2\theta](./images/ad94593eea4f98e5a855014f2b0cccf1c1162501.png) to the other side of the equation,

![-\sin^2\theta = (\cos\theta - \lambda)^2, \qquad \qquad \qquad \qquad \qquad](./images/22432850b4c7a9a7e93ce4af671872ed148032fc.png)

then take the square root on both sides:

![\cos\theta-\lambda = \pm \sqrt{ -  \sin^2 \theta } = \pm \sqrt{ - 1} \sin \theta =  \pm i\sin\theta.](./images/11c07a8bef05d439a31d195cfd08857524657cf2.png)

The eigenvalues of ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) are ![\lambda_1 = \cos\theta + i \sin\theta](./images/60463765a40d388ac428dd7117878de0f5ba0ae7.png) and ![\lambda_2 = \cos\theta - i \sin\theta](./images/f1e23899a5eb0bdb636b52e6f186a6c28301cacd.png). Using Euler’s formula (see page 1.14.2.6) we can express the eigenvalues more compactly as ![\lambda_1 = e^{i\theta}](./images/dd6f8dc317ae804f00b8af018105d38770281f42.png) and ![\lambda_2 =e^{-i\theta}](./images/facf36a15ee90959c80b071bab0fb7d31c1ed72d.png). What’s interesting here is that complex numbers emerge as answers to a matrix problem that was originally stated in terms of real variables.

This is not a coincidence: complex exponentials are in many ways the natural way to talk about rotations, periodic motion, and waves. If you pursue a career in math, physics, or engineering, you’ll use complex numbers and Euler’s formula on a daily basis.

###[Special types of matrices](./Front matter.md)

We’ll now define a few special types of matrices with complex entries. These matrices are analogous to the special matrices we defined in[Section 6.2](./Chapter 6_ Theoretical linear algebra.md), but their definitions are adapted to use the Hermitian transpose operation ![^\dagger](./images/2361096691b9ceb31e69175e5eaef6c35445c863.png).

####[Unitary matrices](./Front matter.md)

A matrix ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) is _unitary_ if it obeys ![U^\dagger U=\mathbbm{1}](./images/a108d1163e9673d490d22e7ec552da23b04a31b8.png). The norm of the determinant of a unitary matrix is ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png), ![|\det(U)|=1](./images/371bdb13a7d32715b10a616f791764c0c7de430c.png). For an ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png), the following statements are equivalent:

-   ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) is unitary.
-   The columns of ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) form an orthonormal basis.
-   The rows of ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) form an orthonormal basis.
-   The inverse of ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) is ![U^\dagger](./images/cb3040cc51784e00774ac863467bd00a54d5005a.png).

Unitary matrices are the complex analogues of orthogonal matrices. Indeed, if a unitary matrix ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) has real entries, then ![U^\dagger = U^\sfT](./images/b216fa2f7651aecb857d13bd7b30e58fb526cf74.png) and we have ![U^\sfT U=\mathbbm{1}](./images/d40f2d9180a706813e55223bed252f2bbb688b50.png), which is the definition of an orthogonal matrix.

####[Hermitian matrices](./Front matter.md)

A Hermitian matrix ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) is equal to its own Hermitian transpose:

![H^\dagger = H  \qquad \quad \Leftrightarrow \qquad \quad  h_{ij} = \overline{ h_{ji}}, \; \; \text{ for all } i,j.](./images/59a72c44b189b0930150748d848bcd4c1b258372.png)

Hermitian matrices are complex-number analogues of symmetric matrices.

A Hermitian matrix ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) can be freely moved from one side to the other in a complex inner product:

![\langle H\vec{x},\vec{y}\rangle
=(H\vec{x})^\dagger\vec{y}
=\vec{x}^\dagger H^\dagger \vec{y}
=\vec{x}^\dagger \: (H\vec{y}) 
=\langle\vec{x},H\vec{y}\rangle.](./images/0cd1bd9c6ba9fe0a9c767d78ccfddc570bcf7d61.png)

The eigenvalues of Hermitian matrices are real numbers.

####[Normal matrices](./Front matter.md)

Previously, we defined the set of real normal matrices to be matrices that satisfy ![A^\sfT \!A=AA^\sfT](./images/7e995d6cd4022f95753d9f03d02e295a41aef2b5.png). For matrices with complex entries, the definition of a normal matrix uses the dagger: ![A^\dagger A = AA^\dagger](./images/5a12cc35733326c5908e2bcca2d286af1779965d.png).

Consulting the concept map in[Figure 6.1](./Chapter 6_ Theoretical linear algebra.md) on page 6.1 will help you see the parallels between the different types of special matrices. I realize there’s a lot of new terminology to absorb all at once, so don’t worry about remembering everything. The main idea is to know that these special types of matrices exist—not to know _everything_ about them.

###[Inner product for complex vectors](./Front matter.md)

The complex inner product is an operation of the form

![\langle \cdot, \cdot \rangle :
\mathbb{C}^n \times \mathbb{C}^n \to \mathbb{C}.](./images/1c3889573e50dd0b020e25824055298617792aa5.png)

The inner product ![\langle \vec{u},\vec{v}\rangle](./images/22e8d82be3029958c4dbfa4a9944a3aa2eaa3543.png) for real vectors is equivalent to the matrix multiplication between the row vector ![\vec{u}^\sfT](./images/4ea2ec2fd2a9143fcc3e4910831ec0a0e1f86ee6.png) and the column vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). Extending the notion of inner product to work with complex vectors requires a modification to the inner product formula. The inner product for vectors ![\vec{u},\vec{v} \in \mathbb{C}^n](./images/b69b9975d1c18c4f1f20f489bb797ae4f4347e3b.png) is defined as

![\langle \vec{u},\vec{v}\rangle 
\,\eqdef\, \sum_{i=1}^n \overline{u_i} v_i
= \vec{u}^\dagger \vec{v}.](./images/49c2add56b1abc834ec535312a00e9a5fcb331ed.png)

The formula is similar to the inner product formula for real vectors, but uses the Hermitian transpose ![^\dagger](./images/2361096691b9ceb31e69175e5eaef6c35445c863.png) instead of the regular transpose ![^\sfT](./images/a462348fa44a14519bb7f3a98207adcc6cb061da.png). The inner product of two vectors ![\vec{u}, \vec{v} \in \mathbb{C}^3](./images/dbf7faa7b55d75382d6141743d3e48b582d8783e.png) is

![\langle \vec{u},\vec{v}\rangle
=
\overline{u}_1v_1 + \overline{u}_2v_2 + \overline{u}_3v_3 
=
\begin{bmatrix}
\overline{u}_{1}     &   \!\overline{u}_{2} &\!  \overline{u}_{3} \\
\end{bmatrix}
\!\!
\begin{bmatrix}
v_1 \\
v_2 \\
v_3 
\end{bmatrix}
= 
\vec{u}^\dagger\vec{v}.](./images/568f050534b5d7731b3338ead6ff08f6dc942dca.png)

This dagger thing is very important. Using the definition of the inner product with a dagger on the first input ensures the complex inner product will obey the positive semidefinite criterion (see page 6.4). The inner product of a vector ![\vec{v} \in \mathbb{C}^3](./images/183af4e1bd28c8486703cf79d26fc907d9c1943c.png) with itself is

![\langle \vec{v},\vec{v}\rangle  
= \vec{v}^\dagger\vec{v}
=  \begin{bmatrix}
\overline{v}_{1}     &   \!\overline{v}_{2} &\!  \overline{v}_{3} \\
\end{bmatrix}
\!\!
\begin{bmatrix}
v_1 \\
v_2 \\
v_3 
\end{bmatrix}
= |v_1|^2 + |v_2|^2 + |v_3|^2,](./images/aeb7867b16176f7a8262c727df9765fe4d639020.png)

where ![|v_i|^2 = \overline{v}_iv_i](./images/375a22e558a753344d1030114634a86deef7b37a.png) is the magnitude-squared of the component ![v_i \in~\!\mathbb{C}](./images/faec2f393a60e733eb443f314e2f043b46e78b4b.png). The magnitudes of the complex components are nonnegative real numbers, so the sum of their squares is also a nonnegative real number. Therefore, the complex inner product satisfies the positive semidefinite requirement ![\langle \vec{v},\vec{v}\rangle \geq 0](./images/8f56d997ba7a2a93ac0feb35f6880638a9a78442.png) for inner products.

###[Length of a complex vector](./Front matter.md)

The complex inner product induces the following complex norm:

![\|\vec{v}\| 
\,\eqdef\, 	\sqrt{  \langle \vec{v},\vec{v}\rangle  }
= 		\sqrt{ \vec{v}^\dagger\vec{v} } 
= 		\sqrt{ |v_1|^2 + |v_2|^2 +  \cdots + |v_n|^2 }\,.](./images/2bc1add7ac8edd73deb91f96c7dfeae540adad92.png)

The norm for complex vectors satisfies the positive semidefinite requirement ![\|\vec{v}\| \geq 0](./images/4c32a8e7469476c0f1989d0b121178df5ed1d281.png) for norms (see page 6.4.3).

#####[Example](./Front matter.md)

Calculate the norm of the vector ![\vec{v}=(2+i, 3, 5i)](./images/b2d1c85f0b03f0f5381603a4563843aeafab93d8.png).

The Hermitian transpose of the row vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is the column vector ![\vec{v}^\dagger = (2-i,3,-5i)^\sfT](./images/a7cb7c0ad6453c211606171644e75b1b6ffe9964.png). The norm of ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is equal to the square root of ![\langle \vec{v},\vec{v}\rangle](./images/afce3e7bd3559d2b1d2331c4c3993140b6066a9a.png) so ![\|\vec{v}\| = \sqrt{  \langle \vec{v},\vec{v}\rangle  } = \sqrt{ (2-i)(2+i) + 3^2 + (-5i)(5i) }=\sqrt{4+1 + 9 + 25}=\sqrt{39}](./images/18bb7de9bf3006207533da1d64d585de6b74fb24.png).

###[Complex inner product spaces](./Front matter.md)

A real inner product space is an abstract vector space ![(V,\mathbb{R},+,\cdot)](./images/313330e93218147f3e2906b573cc90e81ca0ef18.png) for which we’ve defined an inner product operation ![\langle \mathbf{u} , \mathbf{v} \rangle](./images/3b9ee96b30fdf71f77bac471145faa2692f7d7b1.png) which obeys (1) the symmetric property, (2) the linearity property, and (3) the positive semidefinite property.

Similarly, a complex inner product space is an abstract vector space ![(V,\mathbb{C},+,\cdot)](./images/a5e67e5c424edb34d195b2ec00cbf3c8406804d0.png) with an inner product operation ![\langle \mathbf{u} , \mathbf{v} \rangle](./images/3b9ee96b30fdf71f77bac471145faa2692f7d7b1.png) that satisfies the following criteria for all ![\mathbf{u}, \mathbf{v}, \mathbf{v}_1,\mathbf{v}_2\in V](./images/f4d27939cc9841954ef9af00ec12715497bb35d9.png) and ![\alpha,\beta \in\mathbb{C}](./images/7b005f5966f912def1587fb5d827e63f5b24bcd8.png):

-   Conjugate symmetric: ![\langle \mathbf{u},\mathbf{v}\rangle =\overline{\langle \mathbf{v},\mathbf{u}\rangle }](./images/6c1b39b0b62b58d85003e68befe2e79d98679703.png)
-   Linear: ![\langle \mathbf{u},\alpha\mathbf{v}_1+\beta\mathbf{v}_2\rangle
    =\alpha\langle \mathbf{u},\mathbf{v}_1\rangle +\beta\langle \mathbf{u},\mathbf{v}_2\rangle](./images/0adc800ef7f5b95fdc1029811440681c02b604fd.png)
-   Positive semidefinite: ![\langle \mathbf{u},\mathbf{u}\rangle \geq0](./images/707648c85a9c6015f87ff0170869c03c7c9415c7.png) for all ![\mathbf{u}\in V](./images/4a869665b21aa2f6eaf354a4c85abc940ed30a7f.png) with ![\langle \mathbf{u},\mathbf{u}\rangle =0](./images/321add528a9e6b050992a9633f9447d7150a6fee.png) if and only if ![\mathbf{u}=\mathbf{0}](./images/eb1e1fb3fa4e081fcea8eb478d7b220840dd23f5.png)

The conjugate symmetry property ![\langle \mathbf{u},\mathbf{v}\rangle =\overline{\langle \mathbf{v},\mathbf{u}\rangle }](./images/6c1b39b0b62b58d85003e68befe2e79d98679703.png) ensures the inner product of a vector with itself is a real number: ![\langle \mathbf{u},\mathbf{u}\rangle = \overline{\langle \mathbf{u},\mathbf{u}\rangle } \in\mathbb{R}](./images/73f7b6585bfddfab8f2963eb53098b5c94a8e615.png).

#####[Example](./Front matter.md)

The Hilbert–Schmidt inner product for matrices ![A, B \in \mathbb{C}^{m \times n}](./images/3dcc45c0d2d237158e39318e58992e1f19ab6ddc.png) is defined as

![\langle A, B \rangle_{\textrm{HS}}
\,\eqdef\, \textrm{Tr}\!\left( A^\dagger B \right)
= \sum_{i=1}^n \langle  A\vec{e}_i, B\vec{e}_i \rangle.](./images/c6cb9e613b771ad74798cd65dda233a2d5e14681.png)

The product ![A\vec{e}_i](./images/1f898693e221c1883442920b67bccb230013cde2.png) has the effect of “selecting” the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th column of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png); we can consider the Hilbert–Schmidt inner product of matrices ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) as the sum of the vector inner products of the columns of the two matrices.

We can also define the Hilbert–Schmidt norm for matrices:

![\|A\|_{\textrm{HS}}
\,\eqdef\, 	\sqrt{ \langle A, A \rangle_{\textrm{HS}} }
= 		\sqrt{ \textrm{Tr}\!\left( A^\dagger A \right) }
= 		\!\left[ \sum_{i=1}^m \sum_{j=1}^{n} |a_{ij}|^2 \right]^{\!\frac{1}{2}}\!.](../Images/71f60cb249fdfa5010e312136331e6f39a6ac048.png)

The Hilbert–Schmidt norm is the square root of the sum of the squared magnitudes of the entries of the matrix.

The Hilbert–Schmidt inner product and norm are sometimes called _Frobenius inner product_ and _Frobenius norm_, respectively.

###[Singular value decomposition](./Front matter.md)

The singular value decomposition we introduced for real matrices in[Section 6.6.2](./Chapter 6_ Theoretical linear algebra.md) also applies to matrices with complex entries.

The singular value decomposition of a matrix ![A \in \mathbb{C}^{m \times n}](./images/a50a3038b1dc969c86e3656550abc0374c7bc238.png) is a way to express ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as the product of three matrices:

![A = U\Sigma V^\dagger.](./images/279f71e8a7925fdc34eb765d7da0c86de023815b.png)

The ![m\times m](./images/2322ada5aede7496c64841e769698afafffbb942.png) unitary matrix ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) consists of _left singular vectors_ of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). The ![m \times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrix ![\Sigma](./images/d39a5eaeec3a326b9cea2deac91a6b9083fdc4dc.png) contains the _singular values_ ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png) on the diagonal. The ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) unitary matrix ![V^\dagger](./images/912b12a4a4d830031c85d7c5fe0abe8bc48633aa.png) consists of _right singular vectors_.

The singular values ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png) of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are the positive square roots of the eigenvalues of the matrix ![AA^\dagger](./images/77aa5059c3dc7239c3547c2ef4b7ccddba946260.png). To find the matrix of left singular vectors ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png), calculate the eigenvectors of ![AA^\dagger](./images/77aa5059c3dc7239c3547c2ef4b7ccddba946260.png) and pack them as columns. To find the matrix of right singular vectors ![V^\dagger](./images/912b12a4a4d830031c85d7c5fe0abe8bc48633aa.png), calculate the eigenvectors ![A^\dagger A](./images/e72de992e72a455f001407b14b64730576b0cca0.png), pack them as columns in a matrix ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), then take the Hermitian transpose of this matrix.

The Hilbert–Schmidt norm of a matrix ![A \in \mathbb{C}^{m \times n}](./images/a50a3038b1dc969c86e3656550abc0374c7bc238.png) is equal to the square root of the sum of the squares of its singular values:

![\|A\|_{\textrm{HS}}
= \sqrt{ \textrm{Tr}\!\left( A^\dagger A \right) }
= \sqrt{ \sum_{i=1}^n \sigma_i^2 }.](./images/deb33b49df5a11c0ac4381bc6eea9891da8349f4.png)

This equation shows an important connection between the matrix’s norm and the size of its singular values. The singular value ![\sigma_i](./images/7515dfa03c2b37995897f0be2ec5b59991396271.png) corresponds to the multiplier that ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) applies between the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th left singular vector and the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th right singular vector.

The singular value decomposition is used in many algorithms and procedures to uncover the inner structure of matrices. The machine learning technique called _principal component analysis_ (PCA) corresponds to applying the SVD to a data matrix. Alternatively, you can think of the PCA as applying an eigendecomposition of the _covariance matrix_ of the data.

###[Explanations](./Front matter.md)

####[Complex eigenvectors](./Front matter.md)

The characteristic polynomial of the rotation matrix ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) is ![p(\lambda)=(\cos\theta - \lambda)^2+\sin^2\theta=0](./images/1c8a82e2513ff92c13f24669217a2add175e6ba9.png). The eigenvalues of ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) are ![\lambda_1 = \cos\theta + i \sin\theta = e^{i\theta}](./images/d2501ebd89aef156828ca2342aafa017feaa4d4c.png) and ![\lambda_2 = \cos\theta - i \sin\theta=e^{-i\theta}](./images/41a1bcf3c7ba35cf69d0d477443a1182cead80fc.png). What are its eigenvectors?

Before we get into the eigenvector calculation, I want to show you a useful trick for rewriting ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png) and ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png) expressions in terms of complex exponential functions. Recall Euler’s formula, ![e^{i\theta} = \cos\theta + i \sin\theta](./images/e121a20685ffac97d746ced075400d22165d332d.png). Using this equation and the analogous expression for ![e^{-i\theta}](./images/04bd00f775414f3a6f33447437eafc7113d4cda7.png), we can obtain the following expressions for ![\cos\theta](./images/7d55b4ade5701f0ed4db96d3683ce5e6526d9c97.png) and ![\sin\theta](./images/ca98049bc95af8edff203c0490c1fe76851a1b3a.png):

![\cos\theta = \frac{1}{2}\left( e^{i\theta} + e^{-i\theta} \right),
\qquad 
\sin\theta = \frac{1}{2i}\left( e^{i\theta} - e^{-i\theta} \right).](./images/342486904d4f4c3b1c8e9f34374e5b11da4c0ca0.png)

Try calculating the right side in each case to verify the accuracy of each expression. These formulas are useful because they allow us to rewrite expressions of the form ![e^{i\theta}\cos\phi](./images/1c1af7e18effe9904f7ebef6fd75bb22eac33229.png) as ![e^{i\theta}\frac{1}{2}\!\left( e^{i\phi} + e^{-i\phi} \right) 
= \frac{1}{2}\!\Big( e^{i(\theta+\phi)}](./images/e8d45d97346b8217bbc8a4f87ad4b1df9c855a54.png) ![+ e^{i(\theta-\phi)} \big)](./images/1161e714403f2cec3a9d40014c80178d6708f2da.png), which is simpler.

Let’s now see how to find the eigenvector ![\vec{e}_{\lambda_1} = (\alpha,\beta)^\sfT](./images/1290aab23db5d2acac5beeaf8e9fe4526bf08a58.png) associated with the eigenvalue ![\lambda_1 = e^{i\theta}](./images/dd6f8dc317ae804f00b8af018105d38770281f42.png). The eigenvalue equation for the eigenvalue ![\lambda_1 = e^{i\theta}](./images/dd6f8dc317ae804f00b8af018105d38770281f42.png) is

![R_\theta \vec{e}_{\lambda_1}
= e^{i\theta} \vec{e}_{\lambda_1}
\qquad \Leftrightarrow \qquad
\begin{bmatrix}
\cos\theta	&-\sin\theta \\
\sin\theta	&\cos\theta
\end{bmatrix}
\!\!
\begin{bmatrix}
\alpha \\ \beta
\end{bmatrix}
=
e^{i\theta}
\begin{bmatrix}
\alpha \\ \beta
\end{bmatrix}\!.](./images/7b8000d5205eab4fa96cb9c940cbe94dfcbfc23d.png)

We’re looking for the components ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png). Do you remember how to find eigenvectors? Don’t worry if you’ve forgotten—this is why we have this review chapter! We’ll go through the problem in detail. Brace yourself though, because the calculation is quite long.

The “finding the eigenvector(s) of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) for the eigenvalue ![\lambda_1](./images/8c8067d72e5c67f01fd0e636d444f0dd5010b26f.png)” task is carried out by finding the _null space_ of the matrix ![(A-\lambda_1 \mathbbm{1})](./images/604eecc64220716991da148fca0ab94e75bb2c0d.png). We rewrite the eigenvalue equation stated above as

![(R_\theta - e^{i\theta}\mathbbm{1}) \vec{e}_{\lambda_1} = 0
\quad \Leftrightarrow \quad
\begin{bmatrix}
\cos\theta - e^{i\theta}	&-\sin\theta \\
\sin\theta			&\cos\theta  - e^{i\theta}
\end{bmatrix}
\!\!
\begin{bmatrix}
\alpha \\ \beta
\end{bmatrix}
=
\begin{bmatrix}
0 \\ 0
\end{bmatrix}\!.](./images/3ab3a4842706afdc4dfb6219f4889c1a48ee2355.png)

It’s now clear that the finding-the-eigenvectors procedure corresponds to a null space calculation.

Let’s use the ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png)\-rewriting trick to simplify ![\cos\theta  - e^{i\theta}](./images/afe54a17bdee29357e9cfd543c36ecd041232937.png):

![\begin{align*}
\cos\theta  - e^{i\theta} 
&= 
\tfrac{1}{2}\left(e^{i\theta} + e^{-i\theta} \right) \; - e^{i\theta}  	\\
& = 
\tfrac{1}{2}e^{i\theta} + \tfrac{1}{2}e^{-i\theta} - e^{i\theta} 
= \tfrac{-1}{2}e^{i\theta} + \tfrac{1}{2}e^{-i\theta} 
= \tfrac{-1}{2}\!\left(e^{i\theta} - e^{-i\theta} \right) 				\\
&= 	-i \tfrac{1}{2i}\!\left(e^{i\theta} - e^{-i\theta} \right) 				\\
&=  -i\sin\theta.
\end{align*}](./images/9d08177d85e1b2cfeef3a18c35b2456cb8604fdc.png)

We substitute this simplified expression in the two places where it appears, and do some row operations to simplify the matrix:

![\begin{bmatrix}
-i\sin\theta		&	-\sin\theta 					\\
\sin\theta		& 	\!\!-i\sin\theta
\end{bmatrix}
\sim   
\begin{bmatrix}
\sin\theta		&	\!\!-i\sin\theta 				\\
\sin\theta		& 	\!\!-i\sin\theta
\end{bmatrix}
\sim  
\begin{bmatrix}
\sin\theta		&	\!\!-i\sin\theta 				\\
0			& 	0
\end{bmatrix}
\sim 
\begin{bmatrix}
1			&	-i		 				\\
0			& 	0
\end{bmatrix}\!.](./images/bb38e2dadf33e2de7f578893927f97f4035c9d58.png)

We can now solve the null space problem. Observe that the second column of the matrix does not contain a pivot, so ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) is a free variable, which we’ll denote ![s \in \mathbb{R}](./images/014b6412f3d0a4ca03b911b3247bbdc72d0337fe.png). We thus obtain the equations:

![\begin{bmatrix}
1			&	-i		 				\\
0			& 	0
\end{bmatrix}			
\!\!
\begin{bmatrix}
\alpha \\ s
\end{bmatrix}
=
\begin{bmatrix}
0 \\ 0
\end{bmatrix}
\qquad
\Rightarrow
\qquad
\begin{array}{rcl}
1\alpha + (-is)			&=&0, \\
0					&=&0.
\end{array}](./images/805f110d26f617cad668351cd4cea94a310c6643.png)

Solving for ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) in terms of ![s](./images/01c32b2913a168e905e5986c66085c7f0d87d487.png), we find ![\alpha = is](./images/e60b9493fda876c7b84172186d3649e777e1e9af.png), and therefore the solution is ![(\alpha,\beta)^\sfT = (is, s)](./images/b520b65a4c1ff62f257aadc5f52cf051ceaea77a.png). The eigenspace that corresponds to the eigenvalue ![\lambda_1 = e^{i\theta}](./images/dd6f8dc317ae804f00b8af018105d38770281f42.png) is the null space of the matrix ![(R_\theta - e^{i\theta}\mathbbm{1})](./images/840d778de256c0ec9c8e66e5ac7efc1e72b0c618.png):

![\mathcal{N}(R_\theta - e^{i\theta}\mathbbm{1}) 
\; = \; \left\{ \begin{bmatrix}is \\ s \end{bmatrix}\!\!, \; \; \forall s\in \mathbb{R} \right\}
\; =  \; \textrm{span}\!\left( \begin{bmatrix}i \\ 1 \end{bmatrix} \right).](./images/d93ff1f8856ba3b9b98eefe9b71a91bc758048e7.png)

After all this work, we’ve finally obtained an eigenvector ![\vec{e}_{\lambda_1}=(i,1)^\sfT](./images/e754f1bc789fa16f984c1424ccd406ac6db727fe.png) that corresponds to the eigenvalue ![\lambda_1 = e^{i\theta}](./images/dd6f8dc317ae804f00b8af018105d38770281f42.png). Let’s verify that the vector we obtained satisfies the eigenvalue equation ![R_\theta \vec{e}_{\lambda_1} = e^{i\theta}\vec{e}_{\lambda_1}](./images/0a602408536feb8821b055564a5de3e09485eb31.png):

![\begin{bmatrix}
\cos\theta 		&-\sin\theta 		\\
\sin\theta		&\cos\theta  
\end{bmatrix}		
\!\!
\begin{bmatrix}
i \\ 
1 
\end{bmatrix}		
=
\begin{bmatrix}
i\cos\theta -\sin\theta 		\\
i\sin\theta	 + \cos\theta  
\end{bmatrix}		
=
\begin{bmatrix}
i(\cos\theta +i \sin\theta) 		\\
\cos\theta + i\sin\theta
\end{bmatrix}	
=
e^{i\theta}\!
\begin{bmatrix}
i \\ 
1 
\end{bmatrix}\!.](./images/b45a1a28deb18ba8690d074f40fec5f1ca3c7ca4.png)

The eigenvector for the eigenvalue ![\lambda_2 = e^{-i\theta}](./images/facf36a15ee90959c80b071bab0fb7d31c1ed72d.png) is ![\vec{e}_{\lambda_2}=(i,-1)^\sfT](./images/50de58d9bbe9cf8a1ee12e769ba3421b7f07ad1c.png). Verify that it satisfies the eigenvalue equation ![R_\theta \vec{e}_{\lambda_2} = e^{-i\theta}\vec{e}_{\lambda_2}](./images/aad318aeca4139ca0d9052d556e1d8de05f3625c.png).

I know it was quite a struggle to find the eigenvectors of this rotation matrix, but this is the case in general when finding eigenvectors. You must complete the null space calculation steps for each eigenspace, and this takes a long time. Be sure to practice finding eigenvectors by hand—I can pretty much guarantee you’ll need this skill on your linear algebra final. And don’t forget to give yourself a pat on the back when you’re done!

####[Properties of the Hermitian transpose operation](./Front matter.md)

The Hermitian transpose obeys the following properties:

-   ![(A+B)^\dagger     = A^\dagger + B^\dagger](./images/0c96765b16eda57fc888163c54f98cd1e6d0eccd.png)
-   ![(AB)^\dagger       = B^\dagger A^\dagger](./images/59df0cebdc81444e3566d02aad4ad421f0ad8d4e.png)
-   ![(ABC)^\dagger    = C^\dagger B^\dagger A^\dagger](./images/b7c01f9181102c4af10e722ef06e2b13c69fe81b.png)
-   ![(A^\dagger)^{-1} = (A^{-1})^\dagger](./images/e156ee1f3180763b35288ea53b150b902db2eb2e.png)

Note these are the same properties as the regular transpose operation from[Section 2.3.5](./Chapter 2_ Intro to linear algebra.md) (see page 2.3.5).

####[Conjugate linearity in the first input](./Front matter.md)

The complex inner product we defined is linear in the second input and _conjugate-linear_ in the first input:

![\begin{align*}
\langle\vec{v}, \alpha\vec{a}+ \beta\vec{b} \rangle
&= \alpha\langle\vec{v},\vec{a}\rangle+ \beta\langle\vec{v}, \vec{b}\rangle, \\
\langle\alpha\vec{a}+\beta\vec{b}, \vec{w} \rangle
&= \overline{\alpha}\langle\vec{a}, \vec{w}\rangle 
+ \overline{\beta}\langle\vec{b}, \vec{w}\rangle.
\end{align*}](./images/734048be04370844ab34803cdccb00dfafd8680b.png)

Keep this in mind every time you deal with complex inner products. The complex inner product is not symmetric since it requires that the complex conjugation be performed on the first input. Remember, instead of ![\langle\vec{v}, \vec{w} \rangle \neq \langle \vec{w}, \vec{v}\rangle](./images/0dd399743d4cefc1bc239b4c1505cab3b2ca89f3.png), we have ![\langle\vec{v}, \vec{w} \rangle = \overline{ \langle \vec{w}, \vec{v}\rangle}](./images/f30eb3ba0a18a8081f4681c951715faac2d7b40d.png).

The choice of complex conjugation in the first input is a matter of convention. In this text, we _defined_ the inner product ![\langle \cdot, \cdot \rangle](./images/84f6c2ce19236cff4d2df48b7b4594aebbd1e27b.png) with the ![^\dagger](./images/2361096691b9ceb31e69175e5eaef6c35445c863.png) operation on the first input, which is known as the _physics convention_. Some old mathematics texts define the inner product of complex vectors using the complex conjugation on the second input, which makes the inner product linear in the first input and conjugate-linear in the second input. This convention is fine, too. The choice of convention doesn’t matter, as long as one of the inputs is conjugated to ensure the inner product obeys the positive semidefinite requirement ![\langle \vec{u}, \vec{u} \rangle \geq 0](./images/91d14e4130dae6d8f467896a45fc371095c2cfc5.png).

####[Function inner product](./Front matter.md)

In the section on inner product spaces, we discussed the notion of the vector space of all real-valued functions of a real variable ![f:\mathbb{R} \to \mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png), and defined an inner product between functions:

![\langle f,g\rangle =\int_{-\infty}^\infty f(x) g(x)\; dx.](./images/c7c758d0026d7b41e42b4650907f1a4ed9cdd30a.png)

Suppose we have two complex-valued functions ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) and ![g(x)](./images/402bc673d4d7429bab611029b1a9d8a42f53931c.png):

![f\colon \mathbb{R} \to \mathbb{C}, \qquad
g\colon \mathbb{R} \to \mathbb{C}.](./images/8ad773bfe77c9ad9ac488e9cc618823f79fac20e.png)

We define the inner product for complex-valued functions as

![\langle f, g \rangle =\int_{-\infty}^\infty \overline{f(x)} g(x)\; dx.](./images/a5ed47e8a43fa9454c2cc34a52069abf7ee74517.png)

The complex conjugation of one of these functions ensures that the inner product of a function with itself results in a real number. The function inner product measures the _overlap_ between ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) and ![g(x)](./images/402bc673d4d7429bab611029b1a9d8a42f53931c.png).

###[Linear algebra over other fields](./Front matter.md)

We can carry out linear algebra calculations over any _field_. A field is a set of numbers for which an addition, subtraction, multiplication, and division operations are defined. The addition and multiplication operations we define must be associative and commutative, and multiplication must distribute over addition. Furthermore, a field must contain an additive identity element (denoted ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png)) and a multiplicative identity element (denoted ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png)). The properties of a field are essentially all the properties of the numbers you’re familiar with: ![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png), ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png), and ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png).

The focus of our discussion in this section was to show that the linear algebra techniques we learned for manipulating real numbers work equally well with complex numbers. This shouldn’t be too surprising since, after all, linear algebra manipulations boil down to arithmetic manipulations of the components of vectors and matrices. Since both real numbers and complex numbers can be added, subtracted, multiplied, and divided, we can study linear algebra over both ![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png) and ![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png).

We can also perform linear algebra over _finite fields_. A _finite field_ is a set ![\mathbb{F}_q \eqdef \{ 0,1,2, \ldots, q-1\}](./images/2ab4fe5c0764e60f0bd314052fcc89bfffcb6b36.png), where ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) is a prime number or the power of a prime number. All the arithmetic operations in this field are performed _modulo_ the number ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png), which means all arithmetic operations must result in answers in the set ![\{ 0,1,2, \ldots, q-1\}](./images/cb9cae3b4261401219d324e8c2e88fbdff02cda5.png). If the result of an operation falls outside this set, we either add or subtract ![q](./images/6df82b8eda0c8681029019699cf8c157e46ca550.png) until the number falls in the set ![\mathbb{F}_q](./images/d8fd0f1eff28d9e6d2783aadef13a973c284ce38.png). Consider the finite field ![\mathbb{F}_5 \eqdef \{0,1,2,3,4\}](./images/58c7d059dfa2cb5f5d062d447302dd20bc28c99e.png). To add two numbers in ![\mathbb{F}_5](./images/3c26de7642a7a7886b338cc40a294fc494b562e3.png), proceed as follows:

![\begin{align*}
\; \; \; \; \; (3 + 3) \bmod 5 	&\; = \;  6 \; \bmod 5  		&\; \; \; \; (\textrm{too big, so subtract } 5) 	\\
&\; = \; 1\; \bmod 5.
\end{align*}](./images/189b667877ebe7a53cbe0b3e3e03e2b6e1da58dc.png)

Similarly, for subtraction,

![\begin{align*}
\; \; (1-4) \bmod 5  		&\; = \; (-3) \bmod 5  		&(\textrm{too small, so add } 5)			 \\
&\; = \; 2 \bmod  5.
\end{align*}](./images/6e7346aa23a3fff545c5412849d765d1964ffc2f.png)

The field of binary numbers ![\mathbb{F}_2 \eqdef \{ 0,1 \}](./images/cd1876175e8537de7c0e354082e0dcf4c52c59cc.png) is an important finite field used in many areas of communications, engineering, and cryptography. In the next chapter we’ll discuss the one-time cryptosystem, which allows for secure communication of messages encoded in binary [Section 7.9](./Chapter 7_ Applications.md)). We’ll also discuss error-correcting codes that enable the reliable transmission of information over noisy communication channels [Section 7.10](./Chapter 7_ Applications.md)). For example, the data packets that your cell phone sends via radio waves are first linearly encoded using a matrix-vector product operation carried out over the finite field ![\mathbb{F}_2](./images/435aef1d0a822b1d260e1b6619312c55b17d8252.png).

At first, thinking of linear algebra over the finite field ![\mathbb{F}_q](./images/d8fd0f1eff28d9e6d2783aadef13a973c284ce38.png) may seem complicated, but don’t worry about it. It’s the same stuff we’ve been practicing—you just need to apply “![\!\bmod \, q](./images/f1e140b32999a08c82329e4b293bf769d99fe698.png)” after every arithmetic calculation. All of your intuition about dimensions and orthogonality, and all the computational procedures you know, are still applicable.

The field of rational numbers ![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png) is another example of a field that’s often used in practice. Solving systems of equations using rational numbers on computers is interesting because the answers obtained are exact—using rational numbers allows us to avoid many of the numerical accuracy problems associated with floating point numbers.

###[Discussion](./Front matter.md)

####[The adjoint operator](./Front matter.md)

Though we used the term _Hermitian transpose_ and the notation ![A^\dagger](./images/3763a4fed4d19a6bb65a04d027dc9aa010a3ee60.png) throughout this section, it’s worth commenting that mathematicians prefer the term _adjoint_ for the same operation, and denote it ![A^*](./images/cddb391b7cce85df91837db748837519d9f630e5.png). Recall we previously discussed the concept of an _adjoint linear transformation_ ![T_{M^\sfT}:\mathbb{R}^m \to \mathbb{R}^n](./images/f509e202c6732b5058f67e19e88c6ccd0518e300.png), which corresponds to the multiplication of a matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) by a row vector from the left ![T_{M^\sfT}(\vec{a}) \eqdef \vec{a}^\sfT M](./images/5c62809ebdfc39b9f3461ee83e8772ab1ab5e486.png) (see page 4.4.10.1). We didn’t use the term “transpose” then because transposing is something you do to matrices. Instead, we used the math term _adjoint_, which precisely describes the notion of the “transpose of a linear transformation.” Since we’re on the topic of math terminology, it should be noted that some mathematicians use the term _adjoint operator_ instead of _adjoint linear transformation_, since they call _operators_ what we call _linear transformations_.

####[Matrix quantum mechanics](./Front matter.md)

Guess what? Understanding linear algebra over the complex field means you understand quantum mechanics! Quantum mechanics unfolds in a complex inner product space (called a Hilbert space). If you understood the material in this section, you should be able to understand the axioms of quantum mechanics at no additional mental cost. If you’re interested in this kind of stuff you should read[Chapter 9](./Chapter 9_ Quantum mechanics.md).

###[Exercises](./Front matter.md)

E6.19 Calculate **a)** ![(2+5i)-(3+4i)](./images/535b95b1f81321eb2a5ed128588217d3358417c9.png), **b)** ![(2+5i)(3+4i)](./images/2c1e56558515864cb7d42928f78eaf708309f566.png), and **c)** ![(2+5i)/(3+4i)](./images/9ffb529ea668d6d74e8245b8114a9136ddef2a39.png).

E6.20 Find the characteristic polynomial, the eigenvalues and their associated eigenvectors for the matrix ![B = \begin{bmatrix}-2  &-1 \\5  &2\end{bmatrix}](./images/f452a720bb4176891766aac9aaf8084ae0f8910c.png).

E6.21 Find the change-of-basis matrix ![\tensor[_{F}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/8319c38f54f68673d5178c62d31ad46b0ebd502f.png) that transforms vectors expressed in the standard basis ![B = \{(1,0,0,0),](./images/de487df864c5b664a44d1169da628aed6674c596.png) ![(0,1,0,0),](./images/b38b28440154ab5cd97515651faf683ed6fed284.png) ![(0,0,1,0),](./images/00934ccd3ce5b05953ffcb7cdc97dfdff801225e.png) ![(0,0,0,1) \}](./images/a978e2865879010b30140e405bd89fe94d2eb0c1.png) to vectors in the _Fourier basis_ ![F = \{ (1,1,1,1),](./images/e131197074d1970303b69125cf0c42bc15af6d62.png) ![(1,-i,-1,i),](./images/177edef5df540bb2d0413a272ac717b2a008aaed.png) ![(1,-1,1,-1),](./images/ba96475058b261eac113fb4782d70c016426699b.png) ![(1,i,-1,-i) \}](./images/928c6f99793875bb5254862b347aad54a81c7204.png).

Find the change-of-basis matrix ![\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{F}}](../Images/016b885767d5a0bb22b0aae4a7d61cf55f8caece.png) first.

E6.22 Is the matrix ![\begin{bmatrix} 1 & 2+i \\ 3-i & 4 \end{bmatrix}](./images/041a1c175505b5bab8fb8e9d62716d76f125f4d4.png) Hermitian?

##[6.8 Theory problems](./Chapter 6_ Theoretical linear algebra.md)

It’s now time to test your understanding of the theoretical concepts we discussed in this chapter. The eigenvector equation ![A\vec{e}_\lambda = \lambda \vec{e}_\lambda](./images/cfe8c47b5c3a090a9c8a01b061c9978c66ea6c32.png) is one of the deepest ideas in linear algebra. I’ve prepared several problems so you can challenge yourself and test your understanding of eigenvalues and eigenvectors. The problems will test your theoretical understanding as well as your stamina, because computing eigenvectors requires many steps of arithmetic and takes a long time. The first eigenvector problem you’ll solve might take you up to an hour. Don’t be alarmed by this—that’s totally normal. After solving a few eigenvector problems, your problem-solving time will drop to 30 minutes; and quickly after that you’ll able to solve eigenvalue problems easily in 15 minutes.

It’s up to you how fluent you want to become. Certainly if you have a linear algebra exam coming up, it would be good to solve all the problems and maybe even solve problems in other books, too. If you’re just reading about linear algebra for fun, you probably don’t need to suffer through the steps of finding eigenvalues using only pen and paper. Solve the problems using `SymPy` instead—you can’t say no to that!

In this chapter we also learned about abstract vector spaces, another important theoretical idea in linear algebra. All the techniques you’ve learned about vectors can be applied to polynomials, matrices, functions, and other vector-like objects. That’s all nice in theory, but we’re going to move beyond passive appreciation and get into the nitty gritty by solving problems that involve bases, linear independence, dimensions, and orthogonality in abstract vector spaces. It might seem like crazy stuff, but if you trust the idea of equivalent representations and the abstract notion of a linear transformation, you’ll see it’s all good and that you can work with abstract vectors.

Finally, the problems that involve linear algebra over the complex field will serve as the final review of what you’ve learned in this book. This is the final boss. You’ll be asked to review and combine your computational, geometric, and theoretical linear algebra skills, applying them to vectors and matrices with complex coefficients. Are you ready for this?

I’m not going to lie to you and say the problems are easy, but this is the final push, so hang in there and you’ll be done with all the linear algebra theory in just a few hours. After finishing the problems in this chapter, the rest of the book winds down with three chapters of cool applications, which are much lighter reading. So grab a pen, pull out some paper and kick some problem ass!

P6.1 Yuna wants to cheat on her exam and she needs your help. Please help her compute the eigenvalues of the following matrices, and slip her the piece of paper carefully so the teacher doesn’t notice. Yuna will give you a chocolate bar to thank you.

1.  ![\begin{bmatrix}
    3 & 1\\
    12 & 2
    \end{bmatrix}](./images/a16c35ecfe4224a238da7e466716cce9f8a6d182.png)
2.  ![\begin{bmatrix}
    0 & 1 & 0\\
    2 & 0 & 2\\
    0 & 1 & 0
    \end{bmatrix}](./images/85512f23bb80ba9424ecb558e4e7178718637e9e.png)

P6.2 Find the eigenvalues of the following matrices.

1.  ![\begin{bmatrix}
    4 & 2\\
    0 & 5
    \end{bmatrix}](./images/7d0d94d38e1659a04e4ff11304b1f68cdf0f9b51.png)
2.  ![\begin{bmatrix}
    3 & 1\\
    1 & 2
    \end{bmatrix}](./images/283c2a9b5c00e3b772be7c8ed49f904904f94988.png)
3.  ![\begin{bmatrix}
    2 & 0 & 1\\
    1 & 2 & 0\\
    0 & 4 & -1
    \end{bmatrix}](./images/51ffd8dcd25b00a84314d415bc31ba464409b98f.png)
4.  ![\begin{bmatrix}
    -3 & 0 & 0\\
    4 & 1 & 0\\
    2 & 1 & -1
    \end{bmatrix}](./images/1e22613a45ef7b2ad76686db05dccf1c0eab4c67.png)

P6.3 Compute the eigenvalues of the matrix ![A = 
\begin{bmatrix}
1 & 1 \\
1 & 0
\end{bmatrix}](./images/5c97dde7ef800e3aa1d1c7082f7b81ee9eaaca70.png).

P6.4 Show that the vectors ![\vec{e}_1 = (1, \frac{1}{\varphi})^\sfT](./images/e4907b2c588a2f4be624007e3e092ad44d3836bd.png) and ![\vec{e}_2 = (1, -\varphi)^\sfT](./images/ffa883c86033a36537503b43945670d44640d8f3.png) are eigenvectors of the matrix ![A = 
\begin{bmatrix}
1 & 1 \\
1 & 0
\end{bmatrix}](./images/5c97dde7ef800e3aa1d1c7082f7b81ee9eaaca70.png). What are the eigenvalues associated with these eigenvectors?

Compute ![A\vec{e}_1](./images/e6f9044b055dbd4b312c3e57bd5ee4ce98741520.png) and ![A\vec{e}_2](./images/fcef1da13f60c5c6d3e18bf4a16a849de61d7333.png) to see what happens. Use the fact that ![\varphi](./images/6f14e9ed0b9ebc16fdc9b26b6156e6d595813474.png) satisfies the equation ![\varphi^2 -\varphi -1=0](./images/3eb145add7c04775aee44711b1d12b7b4f85ee94.png) to simplify expressions.

P6.5 We can write the matrix ![A = 
\begin{bmatrix}
1 & 1 \\
1 & 0
\end{bmatrix}](./images/5c97dde7ef800e3aa1d1c7082f7b81ee9eaaca70.png) as the product of three matrices ![Q\Lambda X](./images/dc3dfbc3bc92697f7616882da01c173e488e8aac.png), where ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png) contains the eigenvectors of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png), and ![\Lambda](./images/c82ec11bd6d5d07101c37fc87040104e616ef994.png) contains its eigenvalues:

![\begin{bmatrix}
1 & 1 \\
1 & 0
\end{bmatrix}
\; = \; \;
\underbrace{\!
\begin{bmatrix}
1 				& 	1 \\
\frac{1}{\varphi} 	& 	-\varphi
\end{bmatrix}
}_Q \; \, 
\underbrace{\!	
\begin{bmatrix}
\varphi 		& 0 				\\
0			& \frac{-1}{\varphi}
\end{bmatrix}\!
}_{\Lambda}
\; \;
\underbrace{\!
\begin{bmatrix}
\, ?		&	? \, 	\\
\, ?		& 	? \, 
\end{bmatrix}\!
}_{X}.](./images/b5db5c22ceeb8f8193eb1eb416cb116d2b872af3.png)

Find the matrix ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png).

P6.6 Compute the eigenvalues and eigenvectors of these matrices:

1.  ![A=\begin{bmatrix}
    0 & 1 \\
    1 & 0
    \end{bmatrix}](./images/a3d6abc1be50ebb18a1104aad57678b857d201a0.png)
2.  ![B=\begin{bmatrix}
    0 & 1 & 0 		\\
    0 & 0 & 1 		\\
    -6 & -1 & 4
    \end{bmatrix}](./images/624c6a9b8ef7d8f540553976930b7a82e024fbce.png)

P6.7 Given ![A=\begin{bmatrix}
2 &	2	\\
5 & -1	
\end{bmatrix}](./images/8e574d2e73fc50d1fb85433289e305d7aed27931.png), find ![A^{10}](./images/e86c2ecd416ff89b516a396fb90cc5e30e89a61f.png).

P6.8 Consider the sequence of triples ![\{ (x_n,y_n,z_n) \}_{n = 0,1,2, \ldots}](./images/0331bb17002f06250295aa34da17f37a4d2d231f.png) produced according to the formula:

![\underbrace{\begin{bmatrix}
\frac{1}{2} & \frac{1}{2} & 0\\
\frac{1}{8} & \frac{3}{4} & \frac{1}{8}\\
0 & \frac{1}{2} & \frac{1}{2}
\end{bmatrix}}_M
\begin{bmatrix}
x_n \\ y_n \\ z_n
\end{bmatrix}
=
\begin{bmatrix}
x_{n+1} \\ y_{n+1} \\ z_{n+1}
\end{bmatrix}\!.](./images/5f2157309bfcf495b41632b036dd44b7db3156e2.png)

Give a formula for ![(x_{\infty},y_{\infty},z_{\infty})](./images/d4d6b5c52823800fd520d3bfa746fcacca8e168b.png) in terms of ![(x_0,y_0,z_0)](./images/9bcec5964ab4676f0afc2ab03f015c48ea490c91.png). This recurrence relation is related to “surface smoothing” algorithms used in 3D graphics; see[`https://youtu.be/mX0NB9IyYpU`](./mX0NB9IyYpU.md) for more explanations.

Compute the eigenvalues ![\lambda_1](./images/f35b707e7ea2f140dc8864eee509396242b7c977.png), ![\lambda_2](./images/9ede4a5f2e6e4ed32db0d9e911d1309bffce61e1.png), and ![\lambda_3](./images/d46c2c71619e7c274bf93342d0bcdb2fc15fa825.png) of the matrix ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png). What will happen to the eigenvalues if you raise them to the power ![\infty](./images/42c777f473b0c5e98bd06929c747d966458a44be.png)?

P6.9 Explain why an ![n \times n](./images/08e2c13b8fef8a136e869818aa0544678444207a.png) matrix can have at most ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) different eigenvalues.

P6.10 Prove that ![T:V \to V](./images/a42010b83a00782cd01d495866fad4dbd3d73f8c.png) is an invertible linear transformation if and only if ![\lambda=0](./images/09add4b68320db3ffa62586834ad00abaf1ad70e.png) is not an eigenvalue of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png).

P6.11 An unknown matrix ![A \in \mathbb{R}^{3\times 3}](./images/65184f899cef39087f5c49284116eee34f292105.png) has eigenvalues ![\lambda_1 = 2](./images/05dac464eef00016e310e39326be66b480a31e4a.png), ![\lambda_2 = -3](./images/68bec4570941375ec71f2119dff07df3787cbd8f.png), and ![\lambda_3 = 5](./images/a49199a7a129b1636b087d204f301bd07f368d33.png). Calculate the value of the following expressions:

1.  ![\det(2A)](./images/7ace9c0394fbafa43e4deaabb69d162b596ecbf2.png)
2.  ![\det(A^2)](./images/fa5ef437f94ca174903e69eb5bd66489568da7e6.png)
3.  ![\det(A^{-1})](./images/d980e2816c50ac580b172569beacaf128991469d.png)
4.  ![\textrm{Tr}(A + 15A^{-1}+A^\sfT)](./images/ff3655972aff0652982387a32d1d303bc2affbac.png)

P6.12 Prove that diagonal matrices are symmetric matrices.

P6.13 Check whether the following matrices are orthogonal or not:

1.  ![\begin{bmatrix}
    -1 & 0 & 1 \\
    0 & 1 & 0 \\
    0 & 0 & -1
    \end{bmatrix}](./images/370119480c5bb0113485c0b22c538372221c1ed2.png)
2.  ![\begin{bmatrix}
    1 & -1 & 1 \\
    1 & -1 & -1 \\
    0 & 1 & 0
    \end{bmatrix}](./images/db3f503dcf480c0560582883e5121b2a194f73a3.png)
3.  ![\begin{bmatrix}
    0 & 0 & 0 & 1 \\
    0 & 0 & 1 & 0 \\
    1 & 0 & 0 & 0 \\
    0 & 1 & 0 & 0								
    \end{bmatrix}](./images/8a9cd5234e05f9208f530312f6dde226b4a54cb3.png)

P6.14 Given a normal matrix ![M \in \mathbb{R}^{n\times n}](./images/a8f5396feb3fa59387d3c4434806f79c4ee44091.png) (![M^\sfT \!M = M M^\sfT](./images/fdaaad43efa72aa6ae35f1126a788a230b5dc704.png)), show that ![\mathcal{C}(M) = \mathcal{C}(M^k)](./images/2af6087c2cb68459cd44715c4f05a216477d6ac1.png) and ![\mathcal{N}(M) = \mathcal{N}(M^k)](./images/b6492846746e31f26737ef2948ca7e8218951282.png) for all ![k](./images/bd8c78013f1a4c5cfa999dd9c4c7a09100df8aab.png).

Think of the eigendecomposition for normal matrices.

P6.15 Given ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) and ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) are two positive semidefinite matrices, show that the sum ![A+B](./images/dee1488badad431f7e240c6451b2a9a8ffd703e7.png) is also a positive semidefinite matrix.

P6.16 Two friends are arguing over a matrix question. Jane claims that a matrix is orthogonal if and only if its columns are an orthonormal basis. John says that a matrix is orthogonal if and only if its rows are an orthonormal basis. Use the rows-times-columns interpretation of the matrix product to figure out who is right.

P6.17 Given that ![O](./images/1740c06abfeb9f9ff2f4f2956420de0c4ad2963a.png) is an orthogonal matrix, find the inverse of ![2O](./images/9fda0ac3b22aeb306d40f52c63b10f86f3b9772c.png).

P6.18 Prove that the set of polynomials of degree two ![P_2(t)](./images/a3a24fcb05393985cc24f6fc43e0b7c8cfe6c93a.png) is a vector space. Consider arbitrary elements ![\mathbf{p} = a_0 + a_1t + a_2t^2](./images/f01a35543e96607788ebcdf928e58b778a3880e6.png) and ![\mathbf{q}=b_0 + b_1t + b_2t^2](./images/6181fc2514d5476ccb73d42395f595a74abeee64.png), arbitrary constants ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png) and ![\beta](./images/bc326c959b80d3a24fcdf5fda29ab07ecaf549ba.png), and verify that all eight axioms stated in[Section 6.3](./Chapter 6_ Theoretical linear algebra.md) hold.

P6.19 Let ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png) be the set of two-dimensional vectors of real numbers, with addition defined as ![(a_1, a_2) + (b_1,b_2) = (a_1 + b_1, a_2b_2)](./images/1c2aae0a7b68084f2112903249d8a8ab2494ca0a.png) and scalar multiplication defined as ![c \cdot (a_1, a_2) = (ca_1, a_2)](./images/28f23f64fc70cea8af059ffe877c7d33f58b131b.png). Is ![(V,\mathbb{R},+,\cdot)](./images/1a6e1948647b730c9437cf77c7c4305cbc0bce66.png) a vector space? Justify your answer.

Check whether scaling by zero obeys the vector space axioms.

P6.20 Let ![V = \{(a_1,a_2)\}](./images/7acaa3d04c6a85fb2d7984e6c3848e6d39cb6ab9.png), with ![a_1,a_2 \in \mathbb{R}](./images/bc6b9029a207fff37e96a40fa6da32a2553f5290.png). Define vector addition as ![(a_1,a_2) + (b_1,b_2) = (a_1 + 2b_1,a_2 + 3b_2)](./images/41e238e03c5c0c25f550306a74859764bce57bac.png) and scalar multiplication as ![c \cdot (a_1,a_2) = (ca_1,ca_2)](./images/2e5eafffd72efe1a9d5be8faffdd5bd7d312e861.png). Is ![(V,\mathbb{R},+,\cdot)](./images/1a6e1948647b730c9437cf77c7c4305cbc0bce66.png) a vector space? Justify your answer.

Check that the associative property holds.

P6.21 Determine whether the following subsets of ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png) are subspaces:

1.  ![\{ (x,y,z) \in \mathbb{R} \; | \; x + y + z = 3 \}](./images/893ed3f86aedca5fb252d9fe766965a04e699ff2.png)
2.  ![\{ (x,y,z) \in \mathbb{R} \; | \; x + y + z = 0 \}](./images/4b365d0683e1b36796a75ecd551b6c473a9bbafb.png)
3.  ![\{ (x,y,z) \in \mathbb{R} \; | \; x = 2y = 3z\}](./images/86b2b280f80183e582704dfd7b8b19941f448eac.png)

P6.22 Consider an arbitrary matrix ![A \in \mathbb{R}^{2 \times 2}](./images/5204fa1e900e21aa235c6147ce9e46d7171d9b96.png) and its representation as a vector of coordinates with respect to ![B_{s}](./images/e13026aed2c1d1e2f31b33188dc66164e47898d0.png): ![\vec{A}=(a_{11}, a_{12}, a_{21}, a_{22})_{\!B_{s}}](./images/99534ddf1bb86bd84c2b17da1c4f4e89f11be56c.png). Suppose we want to compute the matrix trace operation in terms of the vector dot product. What vector ![\vec{v} \in \mathbb{R}^4](./images/12a64bfd04691e62071d3cd7bb30856731f5ad8f.png) makes this equation true ![\textrm{Tr}(A) = \vec{v} \cdot \vec{A}](./images/9a67dcb4a8edc027ac3707ffa6c9e1e50986059e.png)?

P6.23 Repeat the previous question, but now think of ![\vec{A}](./images/962e9ec43b0d0ebfaa0eaf63437a5d266e07b466.png) as a ![4 \times 1](./images/6a302a0116e7b876fbac37fbe55651608842eb3c.png) matrix. Find the matrix ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png) that implements the trace operation: ![\textrm{Tr}(A)=V \vec{A}](./images/a329d51dfc6845798128d7689ff06b419cbcc529.png). Assume the standard matrix-matrix product is used.

P6.24 Prove that the set of polynomials of degree two ![P_2(t)](./images/a3a24fcb05393985cc24f6fc43e0b7c8cfe6c93a.png) is a vector subspace of the vector space ![P_3(t)](./images/693083b379ca72200bd35bb9f189c4a6d9a0b402.png).

A subspace of ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png) must be closed under addition and scalar multiplication, and contain the zero element.

P6.25 Give an example of a subset of ![\mathbb{R}^2](./images/95400ab39ca45e382fe8897a6d187c7836ff8db6.png) that is closed under scalar multiplication, but is not a subspace.

P6.26 Give an example of a subset of ![\mathbb{R}^2](./images/95400ab39ca45e382fe8897a6d187c7836ff8db6.png) that is closed under addition, but is not a subspace.

P6.27 Consider the linear transformation ![T : P_2(x) \to P_2(x)](./images/cd61f3a2fbdc5a5b57c8e6909c54089887b4152d.png) defined as ![T(a_0 + a_1x + a_2x)=a_2x^2](./images/8d783ddac1a775dc4aba9ee1535a4e0814771231.png). Find the matrix representation of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) with respect to the basis ![\{ 1, x, x^2 \}](./images/31b2ffeaf6021abc2814f90b403abb9d8606cacd.png), and compute the eigenvalues of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png).

P6.28 Find the dimension of the vector space of functions that satisfy the differential equation ![f'(t) +f(t)= 0](./images/31c2a6e93f91c7b53068192f025ec0c28f264e38.png).

Which function is equal to a multiple of its own derivative?

P6.29 Let ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png) be the vector space consisting of all functions of the form ![\alpha e^{2x}\cos x + \beta e^{2x}\sin x](./images/669183d3ffc7c4b12a61c3d566f78324441b6747.png). Consider the linear transformation ![L: V \to V](./images/c7e39d7bcc557a8f1f2981e482df3625c32fd479.png), ![L(f) = f' + f](./images/97aa85e2fea5c04e9ca5c6f67d5ce80ba05458db.png). Find the matrix representing ![L](./images/767c126073d24e4524f0b90b80e9579b9c16b1db.png) with respect to the basis ![\{ e^{2x}\cos x, e^{2x}\sin x \}](./images/ebbefa53af2b331e81cbe7b781c5d493a98636b6.png).

P6.30 Find the matrix representation of the derivative operator ![Dp(x) = \frac{d}{dx}p(x)](./images/fbb930406c3fb434bdefa8cd04a787acd8209412.png) for the vector space of polynomials of degree three ![p(x) = a_0 + a_1x + a_2x^2 + a_3x^3](./images/4c08a22ae176caed7258a550b90487f0ede0b6fe.png), represented as coordinates ![(a_0,a_1,a_2,a_3)^\sfT](./images/fe5f90ea29b2b12ee0f025e3aa0be92152afa8b3.png).

P6.31 Give a basis for the vector space of ![3 \times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) diagonal matrices.

P6.32 What is the dimension of the vector space of ![3 \times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) symmetric matrices?

See page 6.2.3 for definition.

P6.33 How many matrices are there in a basis for the vector space of ![3 \times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) Hermitian matrices?

See page 6.7.4 for definition.

P6.34 The linear operator ![T:\mathbb{R}^{2 \times 2} \to \mathbb{R}^{2 \times 2}](./images/74f6749bb2ba4fed5d96cd857757f54641562fb4.png) is defined by the equation

![T\left(
\begin{bmatrix}
a	&	b  \\
c	&	d
\end{bmatrix}
\right)
=
\begin{bmatrix}
2c	&	a+c  \\
b-2c	&	d
\end{bmatrix}.](./images/aa3587f2931322f73f91c740ffb61ef69aac1194.png)

Find the eigenvalues and eigenvectors of this linear operator.

The eigenvectors of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) are ![2\times 2](./images/8d9f69fe9ab543dc19bd60e8ea565644efbcebb4.png) matrices.

P6.35 Show that the following functions, called Laguerre polynomials, are orthogonal with respect to the inner product ![\langle f(x),\!g(x) \rangle\!=\!\!\int_0^\infty \!f(x) g(x)e^{-x}dx](./images/a77417f55108b14792d6c06b6011b532bd287995.png).

![L_0(x) = 1,
\qquad
L_1(x) = 1-x,
\qquad
L_2(x) = \tfrac{1}{2}(x^2-4x+2).](./images/20b9b5e6638b55af07ffd1c602f94df238ab6abc.png)

Use the formula ![\int_0^\infty f(x) g'(x)\,dx = f(x) g(x) \big\vert_0^\infty -  \int_0^\infty f'(x)g(x) \, dx](./images/a43d775158d2329c0faaf67319ff904370e0f1ab.png).

P6.36 Let ![\vec{v}_1, \vec{v}_2, \vec{v}_3](./images/137523f0285754d667d4ae5866f5f89cc753d644.png) be vectors from a vector space ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png). Given ![\langle\vec{v}_1,\vec{v}_2\rangle = 3](./images/1d1e3be5626e9092f107170cb3e199bf86df0538.png), ![\langle\vec{v}_2,\vec{v}_3\rangle =2](./images/aca45d284cb8a30fa0402dcdd006585f742764d6.png), ![\langle\vec{v}_1, \vec{v}_3\rangle = 1](./images/5dd0de26c6005ec2728bd36c2e9073122bd49171.png), ![\langle\vec{v}_1,\vec{v}_1\rangle = 1](./images/b3b4da441961203f1b1fef22ed5b3028056ba859.png), and ![\langle\vec{v}_2,\vec{v}_1+\vec{v}_2\rangle =13](./images/8fbde3ff8f41e59d587b4e615293c5543431244d.png), find:

1.         ![\langle\vec{v}_1, 2\vec{v}_2+ 3\vec{v}_3\rangle](./images/8b8dab05016ca20e5e3a929ea3e531a04cbd266c.png)
2.         ![\langle2\vec{v}_1-\vec{v}_2,\vec{v}_1+\vec{v}_3\rangle](./images/872e4694f0d700267518d4511adf27302e3a74de.png)
3.  ![\Vert\vec{v}_2\Vert](./images/d56f4c5393591e2d57f45015f64ccf9ecb8aca36.png)

P6.37 Prove the Cauchy–Schwarz inequality ![|\langle \mathbf{u},\mathbf{v}\rangle| \leq \lVert \mathbf{u}\rVert \lVert \mathbf{v}\rVert](./images/207a8c13fa98932d40365885a1ea2f97ba3c9f7c.png).

It is true that ![\lVert \mathbf{a} \rVert >0](./images/9cc112fdd7f186ace7f0a7b1c7ef9399f3a6098e.png) for any vector ![\mathbf{a}](./images/149c239c03e9cb47a1cec7ea99ec909dfc377a34.png). Use this fact to expand the expression ![\lVert\mathbf{u}-c\mathbf{v}\rVert > 0](./images/363a748e81ac992fa2644170d8e71abdb4c80a8c.png), choosing ![c=\frac{\langle \mathbf{u},\mathbf{v}\rangle }{\langle \mathbf{v},\mathbf{v}\rangle }](./images/9072c1d2ee9e32e20dabfc0928cae53e700558a2.png).

P6.38 Prove the triangle inequality ![\lVert \mathbf{u}+\mathbf{v}\rVert  \le \lVert \mathbf{u}\rVert +\lVert \mathbf{v}\rVert](./images/44235bac22eb9ade1090777fc749b5bb4f9e6808.png).

Compute ![\lVert\mathbf{u}+\mathbf{v}\rVert](./images/2c783031cd05967fc26e72ddee1ea9970cc2e31f.png) as an inner product and simplify the expression using the fact ![\langle \mathbf{a}, \mathbf{b} \rangle \leq \lVert \mathbf{a} \rVert \lVert \mathbf{b} \rVert](./images/01b10610548874ecc205b74d0f22374d88b62994.png) for all vectors ![\mathbf{a}](./images/149c239c03e9cb47a1cec7ea99ec909dfc377a34.png) and ![\mathbf{b}](./images/3c74e27c296567ffd74caeb36d6012335dfa12d6.png).

P6.39 Perform the Gram–Schmidt orthogonalization procedure on the following basis for ![\mathbb{R}^2](./images/95400ab39ca45e382fe8897a6d187c7836ff8db6.png): ![\{ (0,1),(-1,0)\}](./images/5e8da16960fd1718d9b547894efd3024198613ae.png).

P6.40 Perform Gram–Schmidt orthogonalization on vectors ![\vec{v}_1=(1,1)](./images/89e6a59f9660b78bea7c6ad9cc1effd29ff99b00.png) and ![\vec{v}_2=(0,1)](./images/bfb936af6d3d866ae913b0a491c9b03927049072.png) to obtain an orthonormal basis.

P6.41 Convert the vectors ![(3,1)](./images/716b21898cf7b2b0d118dbe8b886629f7ea53887.png) and ![(-1,1)](./images/dfd4b5827bd43dc20cc705adbfcb62254f061fc5.png) into an orthonormal basis.

P6.42 Consider the vector space ![P_2(x)](./images/b5ae3364ef8aabcbba48b6d08261711e4aeaf3c0.png) of polynomials of degree two in combination with the inner product ![\langle \mathbf{f}, \mathbf{g} \rangle = \int_{-1}^{1} f(x) g(x)\,dx](./images/166cf664e077201e8cfacc79ba95740b4bb8096a.png). The functions ![\mathbf{f}_1(x)=1](./images/1785cae78cc2302259904a59131c62d50820c1de.png), ![\mathbf{f}_2(x)=x](./images/3f97ee6d834f635e48b5404aab13500951aa8ff1.png), and ![\mathbf{f}_3(x)=x^2](./images/4dbfd5c2b8436c1dd11446118d782de83bac4932.png) are linearly independent and form a basis for ![P_2(x)](./images/b5ae3364ef8aabcbba48b6d08261711e4aeaf3c0.png). Transform ![\{ \mathbf{f}_1, \mathbf{f}_2, \mathbf{f}_3 \}](./images/46d5a160251d1e64ff58c1b5d564e21cf1166085.png) into an orthonormal basis for ![P_2(x)](./images/b5ae3364ef8aabcbba48b6d08261711e4aeaf3c0.png).

P6.43 Find the eigendecomposition of the matrix ![A=\begin{bmatrix}
2 & \; 0 & -5	\\
0 & \; 2 & \; 0	\\
0 & \; 0 & -3
\end{bmatrix}](./images/a658ce71b5be7a4fcd57736ab2eb0399aac035c6.png).

P6.44 Compute the following expressions:

1.  ![|3i-4|](./images/f9b17cc8872ddab8aeb22998863b6ff8bc2326cd.png)
2.  ![\overline{2-3i}](./images/50b91f4017037d3a005c0456ee9b709260ac5451.png)
3.  ![(3i-1)+\overline{3-2i}](./images/2dc4d9f6b5fc1f204f0b9a1a4fd025442df2bd6b.png)
4.  ![|\overline{-3i}-\overline{-4i+5}|](./images/cf9a933681e16a731e746878e0bede306f93c2ab.png)

P6.45 Given complex matrices ![A=\begin{bmatrix}
2+i & -1+2i \\
3+2i & -2i
\end{bmatrix}](./images/02c06127d4d70395fdc470880c77d08e924c4671.png), ![B=\begin{bmatrix}
2-i & \; 3-2i \\
5+i & \; -5+5i
\end{bmatrix}](./images/dde4c547e5b89efa00126554abb24494d63f78e2.png), and ![C=\begin{bmatrix}
1+2i & i \\
3-i & 8 \\
4+2i & 1-i								
\end{bmatrix}](./images/7a79a1ca1bea82ef863ab8ef37b076163a9257fd.png), find ![A+B](./images/dee1488badad431f7e240c6451b2a9a8ffd703e7.png), ![CB](./images/2b7d76eeb25afe771c813fed63665897fb5ec909.png), and ![(2+i)B](./images/6254d3b7aef317596850e014fcc242b9c04ef3e1.png).

P6.46 Find the eigenvalues of the following matrices:

1.               ![\begin{bmatrix}
    3  & -2\\
    1 & 1
    \end{bmatrix}](./images/9b0f13741c6cf6be9cd2ab67f682e8903e2c8952.png)
2.               ![\begin{bmatrix}
    3 & -9 \\
    4 & -3
    \end{bmatrix}](./images/92fdc16faeec60edc62a9ec1413abc0434f119ec.png)
3.  ![\begin{bmatrix}
    3 & -13 \\
    5 & 1\\								
    \end{bmatrix}](./images/36b04c52e8819e196f61fbe205e10045362d9f20.png)

P6.47 Determine all the eigenvalues of ![A=\begin{bmatrix}
1+i & 1 \\
2 & 1-i
\end{bmatrix}](./images/d2ff3e5c5ee4e87afe68a1c306f2440a3179d39a.png). For each eigenvalue ![\lambda](./images/5024e92226f2b135df8c3d6a84c7cb3f3943c5e1.png) of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png), find the set of eigenvectors corresponding to ![\lambda](./images/5024e92226f2b135df8c3d6a84c7cb3f3943c5e1.png). Determine whether or not ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is diagonalizable; if so, find an invertible matrix ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png) and a diagonal matrix ![\Lambda](./images/c82ec11bd6d5d07101c37fc87040104e616ef994.png) such that ![Q^{-1}AQ = \Lambda](./images/8da3e273eba09db9fb73e22f2ba2965a3830218d.png).

P6.48 Show that the set ![B_a=\{1+ix, 1+x+ix^2, 1+2ix\}](./images/5743ee0f0802eb5fcc8c98c5a9161f1444470c62.png) is a basis for the space of polynomials with complex coefficients of degree at most two.

P6.49 Given the matrix ![A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}](./images/c7aa3b5024c8452b2e0b3ad7c63dc71d5146961b.png), show that ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) has a real eigenvalue if and only if ![(a-d)^2 + 4bc \geq 0](./images/e22320d8e6b31e33b4727706a81e47bdb5ed53ab.png).

P6.50 Given a normal matrix ![M \in \mathbb{C}^{n\times n}](./images/b88ce62a7975012b1aa65dfa105a084a7a08d9c0.png), prove that ![\mathcal{C}(M) = \mathcal{C}(M^\dagger)](./images/05abe5b042fe894ee2a7a877fa22f57d739b8eba.png).

Think of the eigendecomposition for normal matrices.

P6.51 Prove that the eigenvalues of Hermitian matrices are real.

Consider the equation ![A\vec{e}=\lambda \vec{e}](./images/3f94e8a94c028197dabdc691c746972fdb37bf4b.png) and the expression ![\vec{e}^{\,\dagger}\!A\vec{e}](./images/178ce753c23429b79246c4661ef60c0c4b6b032e.png).

P6.52 Show that eigenvalues of unitary matrices have magnitude one.

Use the fact that unitary matrices are length preserving.

P6.53 A matrix is _nilpotent_ if it becomes the zero matrix when repeatedly multiplied by itself. We say ![A](./images/b8ea154608b63c4e8d479d61a6aebd1d90803164.png) is nilpotent if ![A^k = 0](./images/80b14b83ba28040bcac189c889024981f9344edb.png) for some power ![k](./images/494383672902d4819c2d91723ecdb09455c85878.png). A nilpotent matrix has only the eigenvalue zero, hence its trace and determinant are zero. Are the following matrices nilpotent?

1.  ![\begin{bmatrix}
    -2  &4  \\
    -1  &2
    \end{bmatrix}](./images/de5a59370455af980c175b1c2af1488f71bda267.png)
2.  ![\begin{bmatrix}
    3  &1  \\
    1  &3
    \end{bmatrix}](./images/9f1bea10f541d7f8fe2d3cf1992c536a17a19a28.png)
3.  ![\begin{bmatrix}
    -3  &2  &1  \\
    -3  &2  &1  \\
    -3  &2  &1
    \end{bmatrix}](./images/37bf404e91c9a3a7128dace2e1ff0d2ccaa9296d.png)
4.  ![\begin{bmatrix}
    1  &1  &4  \\
    3  &0  &-1 \\
    5  &2  &7
    \end{bmatrix}](./images/13935725a4e07625119f43179a18a7685d83cc98.png)
5.  ![\begin{bmatrix}
    45  &-22  &-19  \\
    33  &-16  &-14  \\
    69  &-34  &-29
    \end{bmatrix}](./images/94a7381e64b5015c869549c5e1fcc347519769d3.png)
6.  ![\begin{bmatrix}
    5 & -3 & 2\\
    15 & -9 & 6\\
    10 & -6 & 4
    \end{bmatrix}](./images/b93f5c0457d82d389cc415081a13a7eb4be86ce1.png)

P6.54 Given ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) is a normal matrix, show that the matrix ![\sqrt{M}](./images/1afb429ebb99966936d925ea7135deedbb2bab65.png) exists.

Does an eigendecomposition of ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) exist?
