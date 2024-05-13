Chapter 10      

#[End matter](./End matter.md)

##[Conclusion](./Front matter.md)

By tackling the linear algebra concepts in this book, you’ve proven you can handle computational complexity, develop geometric intuition, and understand abstract math ideas. These are precisely the types of skills you’ll need in order to understand more advanced math concepts, build scientific models, and develop useful applications. Congratulations on taking this important step toward your mathematical development. Throughout this book, we learned about vectors, linear transformations, matrices, abstract vector spaces, and many other math concepts that are useful for building math models.

Mathematical models serve as a highly useful common core for all sciences, and the techniques of linear algebra are some of the most versatile modelling tools that exist. Every time you use an equation to characterize a real-world phenomenon, you’re using your math modelling skills. Whether you’re applying some well-known scientific model to describe a phenomenon or developing a new model specifically tailored to a particular application, the deeper your math knowledge, the better the math models you’ll be able to leverage. Let’s review and catalogue some of the math modelling tools we’ve learned about, and see how linear algebra fits into a wider context.

To learn math modelling, you must first understand basic math concepts such as numbers, equations, and functions ![f:\mathbb{R}\to\mathbb{R}](./images/963a00a0185b80fbefbf7e83e2d0d4189476138d.png). Once you know about functions, you can use different formulas ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) to represent, model, and predict the values of real-world quantities. Working with functions is the first modelling superpower conferred on people who become knowledgeable in math. For example, understanding the properties of the function ![f(x)=Ae^{-x/B}](./images/28e38048c2e95fd17a6e72d6ed51c83bb6d53534.png) in the abstract enables you to describe the expected number of atoms remaining in a radioactive reaction ![N(t)=N_{\!o}\,e^{-\gamma t}](./images/9452fa5729087579f8f66aee195db1ac17f5ff61.png), predict the voltage of a discharging capacitor over time ![v(t) = V_{\!o}\,e^{-\frac{t}{RC}}](./images/95dab95878d121462a95e39e2d6b85f389834f27.png), and understand the exponential probability distribution ![\psub{X}(x)=\lambda e^{-\lambda x}](./images/9feeb66e4695a86a8d54199f770a2515af3ad340.png).

To further develop your math modelling skills, the next step is to generalize the concepts of inputs ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), outputs ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and functions ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) to other input-output relationships. In linear algebra, we studied functions of the form ![T:\mathbb{R}^n \to \mathbb{R}^m](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png) that obey the linear property:

![T(\alpha\vec{x}_1+\beta \vec{x}_2)  =   \alpha T(\vec{x}_1) + \beta T(\vec{x}_2).](./images/786618a8829698dbcaeeb6f86539376b0de4843f.png)

This linear structure enables us to study the properties of many functions, solve equations involving linear transformations, and build useful models for many applications (some of which we discussed in[Chapter 7](./Chapter 7_ Applications.md)). The mathematical structure of a linear transformation ![T:\mathbb{R}^n \to \mathbb{R}^m](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png) can be _represented_ as multiplication by a matrix ![M_T \in \mathbb{R}^{m \times n}](./images/941601a4ecd9670b4e8d5963fcb6365be4ae7908.png). The notion of matrix representations (![T \Leftrightarrow M_T](./images/3fcd7db1223c291ed0a4eb0e7a55e5d74d2ea8ad.png)) was central throughout this book. Even if you forget the computational procedures we learned, the idea of representations should stick with you, and you should be able to recognize representations in many contexts. That’s a big deal, because most advanced math topics involve studying the parallels between different abstract notions. Understanding linear transformations and their representations is an important first step toward advanced math topics.

The computational skills you learned in[Chapter 3](./Chapter 3_ Computational linear algebra.md) are also useful; though you probably won’t be solving any problems by hand using row operations from this point forward, since computers outclass humans on matrix arithmetic tasks. Good riddance. Until now, you did all the work and used `SymPy` to check your answers. From now on, you can let `SymPy` do all the calculations and your job will be to chill.

If you didn’t skip the sections on abstract vector spaces, you know about the parallels between the vector space ![\mathbb{R}^4](./images/63147fde7ca40efcdbf48e4b0a82e082577ebd3b.png) and the abstract vector spaces of third-degree polynomials ![a_0 + a_1x + a_2x^2 + a_3x^3](./images/bdeb20ff48d1c0b4c9dff50a407da2d4eedba70a.png) and ![2\times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) matrices ![\begin{bmatrix}a & b \\ c & d \end{bmatrix}](./images/dc1aba57db2aa420523b6dcb2f1e140253da2093.png). This is another step up the ladder of abstraction, as it deepens your understanding of all math objects with vector-like structure.

It was my great pleasure to be your guide through the subject of linear algebra. I hope you walk away from this book with a solid understanding of how the concepts of linear algebra fit together. In the book’s introduction, I likened linear algebra to playing with legos. Indeed, if you feel comfortable manipulating vectors and matrices, performing change-of-basis operations, and using the matrix decomposition techniques to see inside matrices, you’ll be able to “play” with all kinds of complex systems and problems. For example, consider the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) that you want to apply to an input vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png). Suppose the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is most easily described in the basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png), but the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is expressed with respect to the basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png). “No problem,” you can say, and proceed to build the following chain of matrices that compute the output vector ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png):

![[\vec{w}]_{B} = 
\!\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}
\!\tensor[_{B^\prime}]{\left[A_T\right]}{_{B^\prime}}
\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}} \! 
[\vec{v}]_{B}.](../Images/06c1b4289d13a137648e606ce487831a751c9d2d.png)

Do you see how matrices and vectors fit together neatly like legos?

I can’t tell you what the next step on your journey will be. With your new linear algebra modelling skills, a thousand doors have opened for you; now you must explore and choose. Will you learn how to code and start a software company? Maybe you’ll use your analytical skills to go to Wall Street and destroy the System from the inside. Or perhaps you’ll apply your modelling skills to revolutionize energy generation, thus making human progress sustainable. Regardless of your choice of career, I hope you’ll stay on good terms with math and continue learning whenever you have the chance. Good luck with your studies!

##[Social stuff](./Front matter.md)

Be sure to contact me if you have any feedback about this book. It helps to hear which parts of the book readers like, hate, or don’t understand. I consider all feedback in updating and improving future editions of this book. This is how the book got good in the first place—lots of useful feedback from readers. You can reach me by email at [`ivan@minireference.com`](./mailto_ivan@minireference.com.md).

Another thing you can do to help us is to review the book on Amazon.com, Goodreads, Google Books, or otherwise spread the word about the **No Bullshit Guide** textbook series. Talk to your friends and let them in on the knowledge buzz.

If you want to know what Minireference Co. has been up to, check out our blog at[`minireference.com/blog/`](./blog.md). The blog is a mix of 30% publishing technology talk, 50% startup business talk, and 20% announcements. Checking the blog is the easiest way to follow the progress of our revolution in the textbook industry. For real; we’re totally serious about making education accessible through affordable textbooks. You can also connect via Twitter[`@minireference`](./minireference.md) and Facebook[`fb.me/noBSguide`](./noBSguide.md).

##[Acknowledgements](./Front matter.md)

This book would not have been possible without the support of my parents, and my teachers: Claude Crépeau, Patrick Hayden, Paul Kenton, Benoit Larose, and Ioannis Psaromiligkos. It’s by listening to them that I gained the confidence to learn and later teach advanced math topics. Patrick Hayden deserves a particular mention in this regard since his ability to explain concepts clearly inspired me to tackle complicated problems using a steady, methodical approach. Patrick also showed me that it’s possible to trick students into learning even the most advanced topics by presenting the material in a logical and structured manner. Many thanks also to David Avis, Arlo Breault, Michael Hilke, Igor Khavkine, Felix Kwok, Juan Pablo Di Lelle, Ivo Panayotov, and Mark M. Wilde for their support with the book.

The errorlessness and consistency of the text would not have been possible without the help of my editor Sandy Gordon, who did a great job at polishing the text until it flowed. Truly no bullshit is allowed into the book when Sandy’s on watch. Many thanks to Polina Anis’kina who helped me to create the problem sets for the book.

##[General linear algebra links](./Front matter.md)

Below are some useful links to resources where you can learn more about linear algebra. We covered a lot of ground, but linear algebra is endless. Don’t sit on your laurels and think you’re the boss now that you’ve completed this book and its problem sets. You have the tools, but you need to practice using them. Try reading about the same topics from some other sources. See if you can do the problem sets in another linear algebra textbook. Try to use linear algebra in the coming year and further solidify your understanding of the material.

\[ Video lectures of Gilbert Strang’s linear algebra class at MIT \]

[`http://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010`](./18-06-linear-algebra-spring-2010.md)

\[ The essence of linear algebra video playlist by 3Blue1Brown \]

[`http://bit.ly/essence_of_LA`](./essence_of_LA.md)

\[ A free online textbook with amazing interactive visualizations \]

[`http://immersivemath.com/ila/index.html`](./index.md)

\[ Lecture notes by Terrence Tao \]

[`http://www.math.ucla.edu/~tao/resource/general/115a.3.02f/`](./115a.3.02f.md)

\[ Wikipedia overview on matrices \]

[`https://en.wikipedia.org/wiki/Matrix_(mathematics)`](./Matrix_(mathematics.md))

\[ Linear algebra wikibook (with solved problems) \]

[`https://en.wikibooks.org/wiki/Linear_Algebra`](./Linear_Algebra.md)

\[ Proofs involving linear algebra \]

[`http://proofwiki.org/wiki/Category:Linear_Algebra`](./Category_Linear_Algebra.md)

\[ Linear algebra from first principles using diagrams only \]

[`https://graphicallinearalgebra.net/`](./graphicallinearalgebra.net.md)

#[Answers and solutions](./End matter.md)

##[Chapter 1 solutions](./Front matter.md)

### Answers to exercises

**E1.1** **a)** ![x=3](./images/9e76ed599947813e60c697e3d4fc1d56c2e1f315.png); **b)** ![x=30](./images/76d6986a1cc9aabb90e0853e9ffa83b87ec88bdc.png); **c)** ![x=2](./images/911a43661a5c85ab3ce3e2df51bb4d02f99f18f8.png); **d)** ![x=-3](./images/17aea68f8a9479a258bcba8e0c9f485589b4424a.png). **E1.2** **a)** ![\mathbb{Z}, \mathbb{Q}, \mathbb{R},\mathbb{C}](./images/8e7f3bee666b2b6c218d5821736ead26e9930835.png); **b)** ![\mathbb{C}](./images/f7f5609cb32f4e04e28d43f486b0bc96ea8e235c.png); **c)** ![\mathbb{N},\mathbb{Z}, \mathbb{Q}, \mathbb{R},\mathbb{C}](./images/832b87840de349738506a0ae49a0cb189f7ca70a.png); **d)** ![\mathbb{Q}, \mathbb{R},\mathbb{C}](./images/ff3dad16e0737ec6c4cc4ec89dc0b0a598a09573.png); **e)** ![\mathbb{R},\mathbb{C}](./images/87ec55854f297788688d565d8e7a35fde6cd4f92.png). **E1.3** **a)** ![21](./images/6253c9ba0abdb5460c2a3c6fea8de8b2e9db6af5.png); **b)** ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png); **c)** ![\frac{2}{27}](./images/e7a37fbfa367b8ad327c7b7c63fc62a2061beaef.png). **E1.4** **a)** ![x=2](./images/911a43661a5c85ab3ce3e2df51bb4d02f99f18f8.png); **b)** ![x=25](./images/09c6940f4e40851ab395fef1c91bad4102160939.png); **c)** ![x=100](./images/50d4515a56f07b68012394287c86b3cc3241efd8.png). **E1.5** **a)** ![f^{-1}(x)=x^2](./images/997efc41d4641dce9a19f5ae1403c6bbe2b9ebcf.png), ![x=16](./images/7988d278565f52b6eeb829ccb802e919524ad97a.png). **b)** ![g^{-1}(x)=-\frac{1}{2}\ln(x)](./images/936e76ee631264cc8a26575df94272fe0f343a43.png), ![x=0](./images/aa78f6a194098d11a5239ec5d5ad4f0fbff21af8.png). **E1.6** **a)** ![(x-1)(x-7)](./images/eedbf12ef16e2bcf1371173c1a44114579eda1e3.png); **b)** ![(x+2)^2](./images/7f03ae0044580d8ac5d0e3d5d1a31623ebdaa547.png); **c)** ![(x+3)(x-3)](./images/8ac0436c6e8c1f3cef5115511cdde5988e65e4de.png). **E1.7** **a)** ![x^2+2x-15=(x+1)^2-16=0](./images/7e0b7d0e016407302fdb7c81eb04f76c9cb5d30e.png), which has solutions ![x=3](./images/9e76ed599947813e60c697e3d4fc1d56c2e1f315.png) and ![x=-5](./images/7cc9fa19b510043647514f7df53a962cf076987b.png); **b)** ![x^2 + 4x + 1=(x + 2)^2-3=0](./images/98bdb35347294c5e237758cf1db0720052775dac.png), with solutions ![x=-2+\sqrt{3}](./images/908bd46c02dbbb99cb3316d6b709c72a0ed48db7.png) and ![x=-2-\sqrt{3}](./images/dfb73eb4e68e990527b37e8381a6ad1b92e4addf.png). **E1.8**  ![x_{1}=\frac{3}{2}](./images/95644c0f0e586c37d92dfc46067aefa83f6460b6.png) and ![x_{2}=-1](./images/01458725f517faebdd373a9970a9587ca7bd9159.png). **E1.9** ![x=\pm \sqrt{2}](./images/362fe74f75decfcb9758fe8a3cc9a6b834391b1d.png). **E1.10** Domain: ![\mathbb{R}](./images/6d542e40d2c729cb1658d7def8a88065c05e6a73.png). Image: ![[-2,2]](../Images/579d94b806913e6c392575bc88bfc671ea7ce287.png). Roots: ![\{\ldots, -\frac{\pi}{2}, \frac{\pi}{2}, \frac{3\pi}{2}, \frac{5\pi}{2}, \ldots\}](./images/26f20e8867d5cc826f8225baf6dccf258c92fac3.png). **E1.11** **a)**  ![p(x)](./images/5f059c6777903c2fb291453bf05fca5ffd7e1e28.png) is even and has degree ![4](./images/052f98fd6b37228ecd75b2b373f9a31bb8f6a7a1.png). **b)**  ![q(x)](./images/6efeae8e74c414f73475eed433a0a226e3d23292.png) is odd and has degree ![7](./images/9dae2aeb6d96ce448b7d241f9bd2a689ff2c409a.png). **E1.12** **a)**  ![x=5](./images/8a73d292a04d77f02c700b5757b2691c054bf273.png) and ![x=-3](./images/17aea68f8a9479a258bcba8e0c9f485589b4424a.png); **b)**  ![x=1 + \sqrt{3}](./images/ad7d0434c7815456e061a724f207e1fa9fba98a9.png) and ![x=1- \sqrt{3}](./images/22fcd891ec2f11b0e1c3777512387fd793cbe5bb.png). **E1.13** ![x=\sqrt{21}](./images/65c441bfb5dd99909a1e599d182b9be700699394.png). **E1.14**  ![V=33.51](./images/2a09f0156c0d451b04550d5df61f090fe69167f2.png) and ![A=50.26](./images/808e7e204467fa96b2d9a7f8f54a09d19ffa9829.png). **E1.15** Length of track ![= 5C=5\pi d=11.47](./images/ac23f6f5526d755b6fb62a1c59e40962f96cdd1b.png) m. **E1.16** ![x=5\cos(45^{\circ})=3.54](./images/f88f79a013c3519f3d2ea728d966329f2e6877cc.png), ![y=5\sin(45^{\circ})=3.54](./images/a2703cfa89ea54e99265b86e2747e315c6d17017.png); ![C=10\pi](./images/dcdd4101f4fed24c2aa1b12ea5d9db4c67723201.png). **E1.17** **a)**  ![\frac{\pi}{6}](./images/3b5d0f66c30c7d568d256ea0d710e1290fecef1a.png) rad; **b)**  ![\frac{\pi}{4}](./images/baeefa71dccdc5bcb680be1d02cfb40156408352.png) rad; **c)**  ![\frac{\pi}{3}](./images/590c0261a4175c0a9d062439132515c23ea11b32.png) rad; **d)**  ![\frac{3\pi}{2}](./images/9d5068f3b6e62da8db5557cecca324744e506e0e.png) rad. **E1.18** **a)** ![-1](./images/4bc0e9293b68d85818e6a2261dcd8da0284b4084.png); **b)** ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png); **c)** ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png). **E1.19** **a)** ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png); **b)** ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png); **c)** ![\frac{1}{2}](./images/54ae72be4ad2a7c6696d4f792b4e571f46aa8216.png); **d)** ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png). **E1.20** **a)** ![(4,0)](./images/5b1eb26ea8c83699022971f3b1566d6d5379143a.png). **b)** ![(-2,-3)](./images/0a9687ab33333989401fda9cbc70e64ce7294e1b.png). **c)** ![(7,3)](./images/cef351f259e67dc77b3d89244833c4e50b932283.png). **E1.21** **a)** ![\vec{v}_1=(5\sqrt{3},5)=(8.66,5)](./images/c0152cc1135c8a732db217d33cc7bf10f61b5039.png). **b)** ![\vec{v}_2=(0,-12)](./images/50e1925abef8800c1c3ea5422afa6d28f5d25a11.png). **c)** ![\vec{v}_3=(-2.95,0.52)](./images/dfefdb33aadfdfcddf002bceabff5827b0233605.png). **E1.22** **a)** ![\vec{u}_1=4\angle 0^\circ](./images/85a2c3186678927538440974be47262ae044191f.png). **b)** ![\vec{u}_2=\sqrt{2}\angle 45^\circ](./images/5e86447dd4ee800969c2ca1eeb953655581ac39c.png). **c)** ![\vec{u}_3=\sqrt{10}\angle108.43^\circ](./images/f22d8811a3c1abd332d3a9e1ff88e7f20e6c7313.png). **E1.23** **a)** ![(1,\frac{1}{2})](./images/1f3e8266b4d4d16705124013369d7c5e1c492a6b.png). **b)** ![(1,2)](./images/ff0ebe362ea8060ceecb21ab65cba42156a1fb54.png). **c)** ![(-2,2)](./images/7fe0c047138a16e94540a84f8f2a9069c8397ab3.png). **E1.24** ![x=2](./images/911a43661a5c85ab3ce3e2df51bb4d02f99f18f8.png), ![y=3](./images/3919dc65bc2a8ac61e72bdbbc22f6a26a0fb062c.png). **E1.25** ![x=5](./images/8a73d292a04d77f02c700b5757b2691c054bf273.png), ![y=6](./images/4e5ddaae853201b43c63967044bb36277a81a412.png), and ![z=-3](./images/01e0818f2918dc44df52153c808e605911b00c4e.png). **E1.26**  ![p=7](./images/282a05163414bd1acaf5bba6d350d122e8f53fc2.png) and ![q=3](./images/b04331b5d3954da42eb04556a29df85cbb5fc189.png). **E1.27** **a)** ![\{2,4,6,7\}](./images/ce94ba4e4e0b5e49595930a3e2d261f16fb6dfc3.png); **b)** ![\{1,2,3,4,5,6\}](./images/62378da0ce9740b54abb367bb6304285d5eef59a.png); **c)** ![\{1,3,5\}](./images/f084440c1274365cac209fd138e99a886429c3b6.png); **d)** ![\emptyset](./images/f9bbe9077d067b510406bdc6443bd0f4f8267a24.png); **e)** ![\{1,2,3,4,5,6,7\}](./images/bcc879eaa8c77a873b297405e11ebe12138fe0f9.png); **f)** ![\{7\}](./images/8b4701e6052ae612835efbf5fe5319e9f98779a6.png); **g)** ![\{2,4,6,7\}](./images/ce94ba4e4e0b5e49595930a3e2d261f16fb6dfc3.png); **h)** ![\emptyset](./images/f9bbe9077d067b510406bdc6443bd0f4f8267a24.png). **E1.28** **a)** ![(-\infty,\frac{3}{2})](./images/6ba89a1455e9982e6987621b5f55e0c1413a9855.png); **b)** ![(-\infty,-5]](../Images/3ff1a43e308f991134fbe7a2dd9ec7beb48386f0.png); **c)** ![(-1,4)](./images/7a0405e2a36fd86db2ed7fef031808b972bfb5fd.png); **d)** ![(4, \infty)](./images/8c237a39864c0e9cacceff7bf224dc017ccb1c50.png); **e)** ![[\frac{14}{3}, \infty)](./images/12cd364456b6513e58d5ed441f55b2fccdc7abf3.png); **f)**   ![(-\infty,-4]](../Images/a499e3bbe750738a497f7759ac78de251f2e32c3.png) ![\cup](./images/f328d926bc330fe3cfae05128f39eec5b2535365.png) ![[2,\infty)](./images/5d9d1b52eae47f544d83d355bf6f906dbe371465.png).

### Solutions to selected exercises

**E1.12** **a)** Rewrite the equation putting all terms on the right-hand side: ![0=x^2 -2x -15](./images/97764a23df56facef564f3592114e27614e843a5.png). We can factor this quadratic by inspection. Are there numbers ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png) and ![b](./images/ae769ce22c6289af843e3e66bd3145003e72ccf6.png) such that ![a+b=-2](./images/fd2e71380201451284a13941e4ed6dae66b4f019.png) and ![ab=-15](./images/0591926d9a22d542512e6227ace3994eac5266a1.png)? Yes, ![a=-5](./images/ccd0c1e00cb64c9bdd0d5ad5aed92fee5bff059c.png) and ![b=3](./images/5df0b1e4698d8c8a0e37f84b4bc0effe0c77c46d.png), so ![0=(x-5)(x+3)](./images/b31420af49f402ee5aa192100efa10a8e4f053a3.png). **b)** Rewrite the equation so all terms are on the left-hand side: ![3x^2-6x-6 =0](./images/cc46186186cdc115c69fe2d784c38c55baa5685a.png). Nice, the cubic terms cancel! We’ll use the quadratic formula to solve this equation ![x=\frac{6 \pm \sqrt{(-6)^2-4(3)(-6)}}{6}=\frac{6 \pm 6\sqrt{3}}{6}=1 \pm \sqrt{3}](./images/9d0d95c241b87e74d8cf36ba13bd238c22e84318.png).

**E1.13** The cosine rule tells us ![x^2 = 4^2 + 5^2 - 2(4)(5)\cos(60^\circ)=21](./images/b9bd129fd040b1e1f83d28e78e573e84a1e48a47.png). Therefore ![x=\sqrt{21}](./images/65c441bfb5dd99909a1e599d182b9be700699394.png).

**E1.14** The volume of the sphere with radius ![r=2](./images/5a2ca487d43721882a076a78c300f6902837b052.png) is ![V=\frac{4}{3}\pi 2^3=33.51](./images/6c95eb6529483a4bbaf0d89a1f9f9e05a56ee634.png). Its surface area is ![A=4\pi 2^2=50.26](./images/2eac1626fb59b32f5c299535fb8ca06c31a1f085.png).

**E1.17** To convert an angle measure from degrees to radians we must multiply it by the conversion ratio ![\frac{\pi}{180}](./images/2741baa6b1e1fb01302e5923301041bd8640603e.png).

**E1.23** See[https://www.desmos.com/calculator/ocedywekcl](./ocedywekcl.md) for plots.

**E1.28** **a)** Dividing both sides of the inequality by two gives ![x < \frac{3}{2}](./images/32db3de897bf742cd05c632b87abbf8bc3c6d758.png). **b)** Divide both sides by negative four to obtain ![x \leq -5](./images/d663aef28506b98e5460acc6c771c9f9241abfce.png). Note the “![\geq](./images/fa1c5807c442a64d1142bb26a4ebfd8f923cff9f.png)” changed to “![\leq](./images/a8767a437950cf57f82eff7c35518960293525da.png)” since we divided by a negative number. **c)** If the absolute value of ![(2x-3)](./images/357e8f3b5a83782564d70920b2997647be646be9.png) is less than five, then ![(2x-3)](./images/357e8f3b5a83782564d70920b2997647be646be9.png) must lie in the interval ![(-5,5)](./images/c4616c3cf01dc7f2acc7e3d426d45ff5e34e704b.png). We can therefore rewrite the inequality as ![-5 < 2x-3 < 5](./images/a0ad61f6b45662ded8d20fc33bce4cdcc3d10262.png), then add three to both sides to obtain ![-2 < 2x < 8](./images/1beb3a6298180587891e3cb60f7105da869ead3d.png), and divide by two to obtain the final answer ![-1 < x < 4](./images/5631090166a61c4ec324a70abfc716710c905bc2.png). **d)** Let’s collect all the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-terms on the right and all the constants on the left: ![8 < 2x](./images/0f206f491e567d1e78b57c2958c85e9023a7a8e2.png), which leads to ![4 < x](./images/4f0cd9c58863ee5359e53f6edb1a9f50e1c23473.png). **e)** To simplify, add two to both sides of the inequality to obtain ![\frac{1}{2}x \geq \frac{1}{3} +2](./images/006952266994cb97a326adf93a7f0d912ff25b95.png). You remember how to add fractions right? We have ![\frac{1}{3} +2 = \frac{1}{3} + \frac{6}{3} = \frac{7}{3}](./images/91c6045ff5a50f9231519b24774849ea1c06c978.png), and therefore ![\frac{1}{2}x \geq \frac{7}{3}](./images/510d7af0923d614f9f0e7701047ddfaebf4e8171.png). Multiply both sides by two to obtain ![x \geq \frac{14}{3}](./images/f8a36372f7be936df33d2ced7f43071bdb234482.png). **f)** The first step is to get rid of the square by taking the square root operation on both sides: ![\sqrt{ (x+1)^2} \geq \sqrt{9}](./images/1c0e5a3bc842877cecc4afabd1d2416d4c415116.png). Recall that ![\sqrt{x^2} = |x|](./images/d30d4771353c3123bad6eadd354592a167f6fd47.png), so we have ![|x+1| \geq 3](./images/0618fd8bf5156ef52c402ba51893a72d46c46ba4.png). There are two ways for the absolute value of ![(x+1)](./images/658f31767c97e31fc728cfa6de962022fb4b1d70.png) to be greater than three. Either ![x+1 \geq 3](./images/c3003a33fad7a4d65857c5080e2233c2fba17ee0.png) or ![x+1 \leq -3](./images/b748568e3eb215afc105c01da69ca1410b7e2a1d.png). We subtract one in each of these inequalities to find ![x \geq 2](./images/b1e6cefa0bc59b3a7146dbae82a26abd6c391c07.png) or ![x\leq -4](./images/48a280d851cc637bcaf2c564986aa174d25ac91e.png). The solution to this inequality is the union of these two intervals.

### Answers to problems

**P1.1** ![x=\pm 4](./images/3c7dadac4fb6743cf00767df6844f6bfb7146228.png). **P1.2** ![x=A\cos(\omega t+\phi)](./images/598febfd89515d2d103b98c981e21269cd3d7627.png). **P1.3** ![x=\frac{ab}{a+b}](./images/d9362fc02ee4a296d0047d4dbb6198dab57b636c.png). **P1.4** **a)** ![2.2795](./images/f83d054a03a450d99bfe706ba51d600319f8860c.png). **b)** ![1024](./images/aacae08b13a2caefe91b8a4d36ebaaa4a8dc3d85.png). **c)** ![-8.373](./images/a371e077fd67e52e54a8e893892d4879ce54bbea.png). **d)** ![11](./images/06e9e340f49db965f008cbc1ab1c98681948d6fe.png). **P1.5** **a)** ![\frac{3}{4}](./images/40f093176024660c5500bd5225871a1d6d598731.png). **b)** ![\frac{-141}{35}](./images/2a71fd0e1203c4fdbfca2bb4f88dcdbc9e2e1abb.png). **c)** ![3\frac{23}{32}](./images/348a54f9df740c099ea7ea8daceb3bed635181c1.png). **P1.6** **a)** ![c](./images/0da715a1d62623ace880d9c3dde79450f829f124.png). **b)** ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png). **c)** ![\frac{9|a|}{|b|}](./images/9d07cfb46d3cc1275bef54b61bacdc479d101e99.png). **d)** ![a](./images/da88f0593681387e3bfb35e93a58aa55d7c9f10f.png). **e)** ![\frac{b}{ac}](./images/05fd0d8645186faf2c5b7f01e53f46608c91a419.png). **f)** ![x^2+ab](./images/fec55f1ae55e0b9d753eb02b3669a82c0ee3d1c9.png). **P1.7** **a)** ![x^2 + (a-b)x -ab](./images/fe596a724b650638ce19af134111693e0c6c3d60.png). **b)** ![2x^2 -7x -15](./images/4a535aec1fc54416be0fd12f13765f66feddc013.png). **c)** ![10x^2 + 31x - 14](./images/d77b70cac77048c93d63eb565e79df4e30fee97b.png). **P1.8** **a)** ![(x-4)(x+2)](./images/3b4f17f263bd4265eaa1fa3325bcd4d6b3f85a4a.png). **b)** ![3x(x-3)(x+3)](./images/4fb6afd19412d497c55d294fe34232cefbe834c2.png). **c)** ![(x+3)(6x-7)](./images/52d2c6690287e44f6e142ba82949f02b9fab0a84.png). **P1.9** **a)** ![(x-2)^2 +3](./images/47f794c854f0ec18706776309ffaccb18d43f278.png). **b)** ![2(x+3)^2+4](./images/38a82912af572149e10782a44fc7eb0097e05571.png). **c)** ![6\big(x + \frac{11}{12}\big)^2 - \frac{625}{24}](./images/a0bd4c247e0d7f81e282f255768120ef37196b37.png). **P1.10** ![\$0.05](./images/e77edaced2171b7d3bdec211d1666f1bff9a8a2f.png). **P1.11** 5 years later. **P1.12** girl = 80 nuts, boy = 40 nuts. **P1.13** Alice is 15. **P1.14** 18 days. **P1.15** After 2 hours. **P1.16** ![\varphi = \frac{ 1+ \sqrt{5} }{2}](./images/daead138c0e7e69f4c959d360ea0ede1738227ba.png). **P1.17** ![x= \frac{-5 \pm \sqrt{41} }{2}](./images/d3877dce5d198e6be3aa1a85dfc3931c3e76b779.png). **P1.18** **a)** ![x=\sqrt[3]{2}](../Images/b7a83a9edefcc6003dec4505324fb364a15c1c0f.png). **b)**  ![x=(\frac{\pi}{2}+2\pi n)](./images/221124d110093856eb94f50bb28fb743a10c30e2.png) for ![n\in \mathbb{Z}](./images/8a72e0c3a0966d6ca1b8fff7bec4474b6adf19f0.png). **P1.19** No real solutions if ![0<m<8](./images/b6792b9eb495001714b658cc4021c5b74184381e.png). **P1.20** **a)** ![e^{z}](./images/9725ed75f473eac37b77c528713e8e55fe0a0297.png). **b)** ![\frac{x^3y^{15}}{z^3}](./images/6c0a08e255e063e491615fec2c759b124ee94a3f.png). **c)** ![\frac{1}{4x^4}](./images/05c28634244dd69f9182472b5dda5e3846db6f6d.png). **P1.21** For ![n>250](./images/441e64cd6fce66aba954bd0f72b17a6774fea2f8.png), Algorithm Q is faster. **P1.22** ![10\,](./images/026341202bbdf32d7566ca9bb51b0a037035d11d.png)cm. **P1.23** ![22.52\,](./images/8334869ebf07d8a4e40106a732b58abf88f613bd.png)in. **P1.24** ![d=\frac{1800\tan20^\circ-800\tan25^\circ}{\tan 25^\circ - \tan 20^\circ}](./images/93fb54714e1c64efd9551197477aa61c5b8bff5c.png), ![h=1658.46\,](./images/f91c7d934517df4da6f83df4975035434ae49e3d.png)m. **P1.25** ![x=\tan\theta\sqrt{a^2+b^2+c^2}](./images/8a92687e85df2e685aff7a594b95ef8567c27f0e.png). **P1.26** ![\sin^2\theta \cos^2\theta = \frac{1 - \cos 4\theta}{8}](./images/e2b0a8ee26c286617559d6719cee0a83e747878b.png). **P1.27** ![c=\frac{a\sin 75^\circ}{\sin 41^\circ}\approx 14.7](./images/8d3de1ec498833b5b0532227e07df5e487aeefb8.png). **P1.28** **a)** ![h=a\sin\theta](./images/c66ec6e8a6a6e88ae92d686236e029ea16fd5981.png). **b)** ![A=\frac{1}{2}ba\sin\theta](./images/09c56dd3bdc88bb06be242410979c46eaaba3873.png). **c)** ![c=\sqrt{a^2 + b^2 -2ab\cos(180^{^{\circ}}-\theta)}](./images/6bd61be904bd559b93b3d8224a89b0945c16f0ff.png). **P1.29** ![1.06\,](./images/d17da130953774f7a8dec98fbf71ee892cf984f5.png)cm. **P1.30** ![A_{\textrm{rect}}=5c + 10](./images/8cc90e4e03dce468e4a7c11ffb75195ac32f8197.png). **P1.31** ![V_{\textrm{box}}=1.639\,](./images/548420c3f7666158c47bd159c9759f882b9e20ba.png)L. **P1.32** ![V=300\,000\,](./images/566557cf40cbf50d466591ba47a7040f2bb9d34a.png)L. **P1.33** ![315\,000\,](./images/40ae36313fd32b048204cf1dbd41799370e0b9c7.png)L. **P1.34** ![4000\,](./images/a05b33ab2deacd821ebded95450bdfa4dd938171.png)L. **P1.35** A rope of length ![\sqrt{2}\ell](./images/092fcda5f3f7fa655dcf16413e6ee21568178a48.png). **P1.36** ![20\,](./images/5372a12fa2e1d5d1765e415b0a160a1c98436376.png)L of water. **P1.37**  ![h=7.84](./images/ecfa4efa6e499562eed60b05ee38a5a581c52095.png) inches. **P1.38** ![1+2+\cdots + 100=50\times101=5050](./images/9bb56b690f4086680a423823bb5460574347c53c.png). **P1.39**  ![x=-2](./images/41835b72b9ddbed1be69ca909cebc2785c3e67f6.png) and ![y=2](./images/cc6e2caf510e8ab2df5cb330b62b88df743e132e.png). **P1.40** ![x=1](./images/c05f845e5cc9939507fccda58e08dc7831b8de3a.png), ![y=2](./images/cc6e2caf510e8ab2df5cb330b62b88df743e132e.png), and ![z=3](./images/c3b403b56f69f4a56f67957ebd240c93b0d5d881.png). **P1.41** **a)** ![\vec{u}_1=5\angle 90^\circ](./images/9b4afe46e664f4aa11c1fa588fa93e4c0d1b2fa2.png). **b)** ![\vec{u}_2=\sqrt{5}\angle 63.4^\circ](./images/bfc5eb19c4c6957bd2b8768a6025f405bbf419b4.png). **c)**  ![\vec{u}_3=\sqrt{5}\angle 243.4^\circ](./images/14d9a573eeec3df06fc1b9b21a93121250906a8b.png) or ![\sqrt{5}\angle\!-\!116.6^\circ](./images/c60ba03f95ff2e6ca06af7793153664738428f05.png). **P1.42** **a)** ![\vec{v}_1=(17.32,10)](./images/7280bfe0cad982dedd21fbd837a8949e92efd3d9.png). **b)** ![\vec{v}_2=(0,-10)](./images/bf309ee03bde0f568deb010ccfd5b2848200d40a.png). **c)** ![\vec{v}_3=(-4.33,2.5)](./images/f60fec22be9a80755c31a8cea31340941a5c1f88.png). **P1.43** **a)** ![\vec{w}_1=9.06\hat{\imath}  + 4.23\hat{\jmath}](./images/78d367d9f93f73b33d85e298cea38c188a706c5f.png). **b)** ![\vec{w}_2=-7\hat{\jmath}](./images/1c47f37fe1627263e2fe9dd4437ccb06905a7258.png). **c)** ![\vec{w}_3=3\hat{\imath}  -2\hat{\jmath} +3\hat{k}](./images/37d6bd76c37df1c6bfed7983d6889b396074a10a.png). **P1.44** **a)** ![(3,4)](./images/87ce0e4ac7717043f4a753048b6c6c4fed0db3e8.png). **b)** ![(0,1)](./images/e69b48bc6687ee74a843dea90543682e53e069e3.png). **c)** ![(7.33,6.5)](./images/a1fd52fc4c3da44fb5b3cf2e7a66843de021d5d1.png). **P1.45** ![Q=(5.73,4)](./images/7d54bc2a81f1d122a738f029cc5fe6e22a8b8c79.png). **P1.46** **a)** ![2i](./images/9489846ad682230dec3f5d71d462c3191e9fef22.png). **b)** ![\frac{1}{4}(5+i)](./images/ead272fc5e7c11185df959685ceddc9fca45e53b.png). **c)** ![2+i](./images/d418a516cfa8960904f2524e715347fae8a3610b.png). **P1.47** **a)** ![x=\pm 2i](./images/4782d99556a034332ee890123a6817f50d7b54fc.png). **b)** ![x=-16](./images/222c77b22300f216a5a3f867a6c3c5430c3812a9.png). **c)**  ![x=-1-i](./images/2b44d96c56d9baa0906ed0b761299ebabe4be0c0.png) and ![x=-1+i](./images/d177e39ebb8a691b4533f73a8034112528752a78.png). **d)** ![x=i](./images/1a42deab85ced7ab393e09f3df830d31df42d359.png), ![x=-i](./images/956c7ad25978042cd1289845fe6cbeb36ad3a533.png), ![x=\sqrt{3}i](./images/dd03dc30ece94bad35e73eaf684057e0f4793d39.png), and ![x=-\sqrt{3}i](./images/4a36e21d3be5ab09b43b821e0d221daedf0c8084.png). **P1.48** **a)** ![\sqrt{5}](./images/681cca0ee5a6067f3a493be3afa8717738938688.png). **b)** ![\frac{1}{2}(-3+i)](./images/33d979e4b12ee563600af39265aece2c04999672.png). **c)** ![-5 - 5i](./images/a3c1f37f348f953d26380c0e501b2f4704c4fea9.png).

### Solutions to selected problems

**P1.5** For **c)**, ![1\frac{3}{4} + 1\frac{31}{32}
= \frac{7}{4} + \frac{63}{32}
= \frac{56}{32} + \frac{63}{32} = \frac{119}{32}=3\frac{23}{32}](./images/6ff2115a189dd6076aaaf66a126132495b09ac1b.png).

**P1.9** The solutions for **a)** and **b)** are fairly straightforward. To solve **c)**, we first factor out ![6](./images/160a910df642692dd50f0862138b3bc151d89988.png) from the first two terms to obtain ![6(x^2 + \frac{11}{6}x)-21](./images/c51c60e3b48bd96dde56784932023eeeca149833.png). Next we choose half of the coefficient of the linear term to go inside the square and add the appropriate correction to maintain equality: ![6[x^2 + \frac{11}{6}x]-21   =     6[ (x + \frac{11}{12})^2 - (\frac{11}{12})^2 ]-21](../Images/44a1cc7a0bb32e5597227d2db1bf952b3f50f05a.png). After expanding the rectangular brackets and simplifying, we obtain the final expression: ![6(x + \frac{11}{12})^2 - \frac{625}{24}](./images/c85fb892a2ed5e87786ccda8a81c6ff141478ff7.png).

**P1.11** We must solve for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) in ![35+x = 4(5+x)](./images/3409338c27fbedf9254dae22edc9ab065899cac2.png). We obtain ![35 + x = 20 + 4x](./images/d51731d20771e8c64eb3d168037dec6ed3a79a14.png), then ![15 = 3x](./images/ed9f0079855b42ed735cb6c51a31a4ac7d3e7e4f.png), so ![x=5](./images/8a73d292a04d77f02c700b5757b2691c054bf273.png).

**P1.13** Let ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) be Alice’s age and ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) be Bob’s age. We’re told ![A=B+5](./images/71520fbad75970248375cd32cc00c2834c9add70.png) and ![A+B=25](./images/489b568b7abdf37914ef72e780537c8e69a26599.png). Substituting the first equation into the second we find ![(B+5)+B=25](./images/34d95db8742a497ad875d050152b15f542e890f1.png), which is the same as ![2B=20](./images/4da6be3bf44f58dfe3f59a43be95834d69ddec37.png), so Bob is 10 years old. Alice is 15 years old.

**P1.14** The first shop can bind ![4500/30 = 150](./images/5e1d9af87b67297ee8ef78e930a0b3b67db24a3e.png) books per day. The second shop can bind ![4500/45 = 100](./images/f283c9b97123a335a03a625be2acbbfe4af50906.png) books per day. The combined production capacity rate is ![150+100=250](./images/d74ff663a08d0ebcfb2baa78211d780311794490.png) books per day. It will take ![4500/250=18](./images/c3d19426d8f8037a075adf10712d24defa778e14.png) days to bind the books when the two shops work in parallel.

**P1.15** Let ![t_{\textrm{m}}](./images/ce9a1e9df32892cad4d7179e808bd83b4c7d65a4.png) denote the time when the two planes meet, as measured from the moment the second plane departs. Since it left one hour earlier, the slower plane will have travelled a distance ![600(t_{\textrm{m}}+1)](./images/eb4e1179aa7f32362cfbe41557594c20f28a3223.png) km when they meet. The faster plane will have travelled the distance ![900t_{\textrm{m}}](./images/dd98e694bd8bf7ad1ac39d4e529311b8eda7c0a6.png) km when they meet. Combining the two expressions we find ![600(t_{\textrm{m}}+1) = 900t_{\textrm{m}}](./images/5d1894867d7122b276366626b2e4ec5e03c7ee57.png). The time when the planes meet is ![t_{\textrm{m}} = 2](./images/9dc6e321c4f0ee5d900f2ab318fe3f3240dc29ab.png) hours after the departure of the second plane.

**P1.19** Using the quadratic formula, we find ![x = \frac{ m \pm \sqrt{m^2 - 8m} }{ 4}](./images/594f01f0b38a581608317f918ab6d12d2f1d7c64.png). If ![m^2 - 8m \geq 0](./images/e406f756f1a0967d945072c184423d8ff31b3e92.png), the solutions are real. If ![m^2 - 8m < 0](./images/e217160f44c303718c67f6323760d214175bf1bf.png), the solutions will be complex numbers. Factoring the expressions and plugging in some numbers, we observe that ![m^2 - 8m = m(m-8) < 0](./images/a7013bc4b3c2871a3d407c30b41080198f8800d5.png) for all ![m \in (0,8)](./images/a945a2a78abbb0f277c1c36212a6e53d1b18235a.png).

**P1.21** The running time of Algorithm Q grows linearly with the size of the problem, whereas Algorithm P’s running time grows quadratically. To find the size of the problem when the algorithms take the same time, we solve ![P(n)=Q(n)](./images/6e718d5b7d3a504316f584c83cff5822399a9c7f.png), which is ![0.002n^2=0.5n](./images/b123f774953ba931fef805db3b13caae5f7cbac2.png). The solution is ![n=250](./images/2de975ab815f2d7ecf1a6341c5febc7ca6ac3793.png). For ![n>250](./images/441e64cd6fce66aba954bd0f72b17a6774fea2f8.png), the linear-time algorithm (Algorithm Q) will take less time.

**P1.24** Observe the two right-angle triangles drawn in[Figure 1.70](./Front matter.md). From the triangle with angle ![25^\circ](./images/85224c662e0b60db48651b4b83f37a13462793d2.png) we know ![\tan 25^\circ = \frac{h}{800+d}](./images/4e22c89b40c2b0a14d5c76789e19e7d9ae2c682d.png). From the triangle with angle ![20^\circ](./images/99cd00abf4ce9774bb15dbec556dea4204eee832.png) we know ![\tan 20^\circ = \frac{h}{1800+d}](./images/40e398b8c14d19b53a0e675af29037fc464fa466.png). We isolate ![h](./images/77e0e4a50e89652b20f69385d6e8957897e96dcf.png) in both equations and eliminate ![h](./images/77e0e4a50e89652b20f69385d6e8957897e96dcf.png) by equating ![(1800+d)\tan25^\circ = \tan 20^\circ (800+d)](./images/f389180b3f3ca9d5faece85350b151e36b597a0e.png). Solving for ![d](./images/dd565b0bdaf16b09052be14b28af85a1bdefb913.png) we find ![d=\frac{1800\tan20^\circ-800\tan25^\circ}{\tan 25^\circ - \tan 20^\circ}=2756.57\,](./images/2bec13c31cfd0fb2fd0a309b3933550a5b3b8623.png)m. Finally we use ![\tan 25^\circ = \frac{h}{800+d}](./images/4e22c89b40c2b0a14d5c76789e19e7d9ae2c682d.png) again to obtain ![h=\tan 25^\circ(800+d)=1658.46\,](./images/68e8b69558c09be5602ac70e6a36134ecb3e0055.png)m.

**P1.26** We know ![\sin^2(\theta) = \frac{1}{2}\left(1-\cos(2\theta)\right)](./images/32c359d2976ee56934bb82cff5ca655999e77feb.png) and ![\cos^2(\theta) = \frac{1}{2}\left(1+\cos(2\theta)\right)](./images/3798941929031ad55018ba5c6f64965ceef634a4.png), so their product is ![\frac{1}{4}\left(1-\cos(2\theta)\cos(2\theta)\right)](./images/3272e87b30b5dffba5823a403650878814a4ca30.png), and ![\cos(2\theta)\cos(2\theta)=\cos^2(2\theta)](./images/17e23e8ac0e8bee99c328b8a1ecc2564823ff287.png). Using the power-reduction formula on the term ![\cos^2(2\theta)](./images/1ffde7cdc2c7edcd64779670431e9b05a357c3de.png) gives ![\sin^2\theta \cos^2\theta = \frac{1}{4}\left(1-\frac{1}{2}(1+\cos(4\theta))\right)](./images/61381520f8e5bafe6d57e88fa17b9f0ef388aeea.png).

**P1.29** The volume of the water stays constant and is equal to ![1000\,](./images/a5887e8cbfd146a5844d2a3cb6a968f0464da45e.png)cm![^3](./images/298e389be45d4deb1ec82fc7825080369c8340d1.png). Initially the height of the water ![h_1](./images/fc1ce50aae1205adbf888676fcd808725397c230.png) can be obtained from the formula for the volume of a cylinder ![1000\,\textrm{cm}^3 = h_1\pi(8.5\,\textrm{cm})^2](./images/f8f12c346ffe4c4d187b3600027098e28bdcd18a.png), so ![h_1=4.41\,](./images/d36bb555c43e4b94ab350b3cdf4c10da0167af2a.png)cm. After the bottle is inserted, the water has the shape of a cylinder with a cylindrical part missing. The volume of water is ![1000\,\textrm{cm}^3 = h_2\left( \pi(8.5\,\textrm{cm})^2 - \pi(3.75\,\textrm{cm})^2\right)](./images/217854bd29512d52c1d08d0dd7d16f0d36d7d876.png). We find ![h_2=5.47\,](./images/7b7cd101f68d80ed95d22515b844952b3e6853a4.png)cm. The change in height is ![h_2-h_1=5.47-4.41=1.06\,](./images/35a382641d885cd62b0ce8b4d7d795100236d4a5.png)cm.

**P1.30** The rectangle’s area is equal to its length times its height ![A_{\textrm{rect}}=\ell h](./images/8eddad61cfdaca9cd1c8a13425231832240fa9e9.png).

**P1.31** The box’s volume is ![V=w\times h \times \ell = 10.5\times 7 \times 22.3=1639\,](./images/6f1e97cfc1f1c7838cc52ecfbd98ec25401db8c0.png)cm![^3](./images/298e389be45d4deb1ec82fc7825080369c8340d1.png)\=![1.639\,](./images/60f01b4b3098aebc013327e8a03e6d02816b4fbc.png)L.

**P1.33** The tank’s total capacity is ![15 \times 6  \times  5 = 450\,](./images/ae5ded36c771eac33189d522479c9e5e7296dbee.png)m![^3](./images/298e389be45d4deb1ec82fc7825080369c8340d1.png). If 30% of its capacity is spent, then 70% of the capacity remains: ![315\,](./images/9a7d2369423aca623885b2206a12cdb695056121.png)m![^3](./images/298e389be45d4deb1ec82fc7825080369c8340d1.png). Knowing that ![1\,](./images/f547f28f2b316249a2aa49d68acb25119ce9970a.png)m![^3 = 1000\,](./images/232d2efd7c24b54573162ea4026de17929ee2d76.png)L, we find there are ![315\,000\,](./images/40ae36313fd32b048204cf1dbd41799370e0b9c7.png)L in the tank.

**P1.34** The first tank contains ![\frac{1}{4}\times 4000= 1000\,](./images/2c019ba411f1a6273cef123c883ce94111a03bdc.png)L. The second tank contains three times more water, so ![3000\,](./images/dbfa1355ad78464f1a93ac4e21cbff05220fdde8.png)L. The total is ![4000\,](./images/a05b33ab2deacd821ebded95450bdfa4dd938171.png)L.

**P1.35** The amount of wood in a pack of wood is proportional to the area of a circle ![A=\pi r^2](./images/77d4c6c1d19667066326e6fb834857f8f41cf5f5.png). The circumference of this circle is equal to the length of the rope ![C=\ell](./images/663e672a6f93cc290996e0b6335ca5272789005b.png). Note the circumference is proportional to the radius ![C=2\pi r](./images/02c2f06658385004d46ed15043a8cc0093f8aa9e.png). If we want double the area, we need the circle to have radius ![\sqrt{2}r](./images/654f6e3b77878c75ea5ec9482619665768e239d4.png), which means the circumference needs to be ![\sqrt{2}](./images/634aa665aee4ddb43342219e2d5b1b6e93385c08.png) times larger. If we want a pack with double the wood, we need to use a rope of length ![\sqrt{2}\ell](./images/092fcda5f3f7fa655dcf16413e6ee21568178a48.png).

**P1.36** In ![10\,](./images/026341202bbdf32d7566ca9bb51b0a037035d11d.png)L of a 60% acid solution there are ![6\,](./images/844bee62df5fb0dc76d0011cbeeea225100b84b4.png)L of acid and ![4\,](./images/ee78f03fb04c05867b2731ee4d1dc386aec40b91.png)L of water. A 20% acid solution will contain four times as much water as it contains acid, so ![6\,](./images/844bee62df5fb0dc76d0011cbeeea225100b84b4.png)L acid and ![24\,](./images/d35ad58010d42390c3fc56807b66a1d1fb16d069.png)L water. Since the ![10\,](./images/026341202bbdf32d7566ca9bb51b0a037035d11d.png)L we start from already contains ![4\,](./images/ee78f03fb04c05867b2731ee4d1dc386aec40b91.png)L of water, we must add ![20\,](./images/5372a12fa2e1d5d1765e415b0a160a1c98436376.png)L.

**P1.37** The document must have a ![768/1004](./images/6748c91c29620c26f93ea87054585c538c29834b.png) aspect ratio, so its height must be ![6 \times \frac{1004}{768} = 7.84375](./images/37d530d3e8647c39a9e763ab10d7069dce1aac41.png) inches.

**P1.38** If we rewrite ![1+2+3+ \cdots + 98+ 99+100](./images/27f3f3c5459b3fc20ee2c2cd382fff0cdfe171f3.png) by pairing numbers, we obtain the sum ![(1+100) + (2+99) + (3+98) + \cdots](./images/90dfefee09d0faef9162b8d1daa2c1ba25ec46e8.png). This list has ![50](./images/35cd44d8b8f5bd544d81c293bb4c65f7aa93181d.png) terms and each term has the value ![101](./images/026d9309d4010c2cdd40630156ba7f0b52f95ead.png). Therefore ![1+2+3+ \cdots + 100 = 50\times101=5050](./images/6d471b5ed2e3cce5074a0df32d1c36480a5a30df.png).

**P1.49** There exists at least one banker who is not a crook. Another way of saying the same thing is “not all bankers are crooks”—just _most_ of them.

**P1.50** Everyone steering the ship at Monsanto ought to burn in hell, forever.

**P1.51** **a)** Investors with money but without connections. **b)** Investors with connections but no money. **c)** Investors with both money and connections.

##[Chapter 2 solutions](./Front matter.md)

### Answers to exercises

**E2.1** ![A^{-1} = \begin{bmatrix}\frac{1}{7} & 0 \\ 0 & \frac{1}{2}\end{bmatrix}](./images/72560fca8a50f8f73ac1a58f014e87e5e6f4f40c.png). **E2.2**

1.  ![A\vec{v}=\begin{bmatrix}7\\ 14\end{bmatrix}](./images/c5389d2b0027659297a3e5387d08516744f8afbf.png);
2.  ![B\vec{v}=\begin{bmatrix}-1\\ 9\end{bmatrix}](./images/4e23c4d2b2fcf38b71d25568d572d292d4bc2733.png);
3.  ![A(B\vec{v})=\begin{bmatrix}26\\ 41\end{bmatrix}](./images/fcad028e002c5183d2ec763c96471c57fe3b85c2.png);
4.  ![B(A\vec{v})=\begin{bmatrix}-7\\ 63\end{bmatrix}](./images/cbd34f98ae53a94b5bc61a1eb1fec0c743ee4777.png);
5.  ![A\vec{w}=\begin{bmatrix}-15\\ -32\end{bmatrix}](./images/2f7e3cc14cf5cae60fcfe13a5c5a70c0d315a16a.png);
6.  ![B\vec{w}=\begin{bmatrix}3\\ -21\end{bmatrix}](./images/19fde7d26764f9d07d815b1c1d69b8fa4ed1be63.png).

**E2.3** ![v_1=-2](./images/01900e303a954742e6de2af1669f56cd2e717c8c.png), ![v_2=3](./images/ee81cf361f13d5dd78a8e23cdc574737ef2a2e0f.png). **E2.4** **a)** ![(1,1,3)](./images/e294a33e8bb304a6c5e6fd7214bdcb7a2415a222.png); **b)** ![(1,1,-3)](./images/9d187314bee6b2c729f1fcd042ec358db5e3a874.png); **c)** ![(3,3,3)](./images/06cb1f7a8b0479ee43241ebe95483e35eebb0da0.png); **d)** ![\sqrt{2}](./images/634aa665aee4ddb43342219e2d5b1b6e93385c08.png). **E2.5** **a)** ![5](./images/f2fa057f2254981666da1b26f97fb103f09600a3.png); **b)** ![(-1, -1, 1)](./images/ef70ad44a79586d170e5899de9f0ed5af3bf624e.png); **c)** ![(1,1,-1)](./images/de9f082b79826cd59620c4a5a6b26da016dd47aa.png); **d)** ![(0, 0, 0)](./images/b9ea26d6179acf575343bff96f0677c7583b7bd6.png). **E2.6**

1.  This part has been omitted for brevity.
2.  ![\vec{v}_1 = (9.848, 1.736)](./images/e6410ab870559bdc5d13d272921c5040dfdc07de.png); ![\vec{v}_2 = (8.66, 5)](./images/fa9ce01974f462e3c48f70384b7759a2e587136f.png); ![\vec{v}_3 = (5, 8.66)](./images/01fc8d3094c4fad2e5be96aee2c8e7b0ca6f6d68.png); ![\vec{v}_4 = (-5, 8.66)](./images/efeb1b7e230f825b9d690d030ebce29864915988.png).
3.  ![\Pi_{\hat{\imath}}(\vec{v}_1) = 9.848](./images/c9a53a1114fbf7664a5588b8c946c9e3553bbb2a.png); ![\Pi_{\hat{\imath}}(\vec{v}_2) = 8.66](./images/2288193e7c4a6c070ea885158368ca82384a160b.png); ![\Pi_{\hat{\imath}}(\vec{v}_3) = 5](./images/e3c90dbb71ed56126bee3011cf669d04c82a1f7e.png); ![\Pi_{\hat{\imath}}(\vec{v}_4) = -5](./images/0d4ea60cf615356f5af238e18b08e5d28368743d.png).
4.  ![\Pi_{\hat{\jmath}}(\vec{v}_1) = 1.736](./images/3a119c9ae9e06423497f6eed1ecedd708c6a4f80.png); ![\Pi_{\hat{\jmath}}(\vec{v}_2) = 5](./images/c5d8da8731f4942935f6a712cc68ab7cebfcad3f.png); ![\Pi_{\hat{\jmath}}(\vec{v}_3) = 8.66](./images/0dc668a923b048389cdcde673ac87bbd406a99d3.png); ![\Pi_{\hat{\jmath}}(\vec{v}_4) = 8.66](./images/edfc9dacb4f83528d7ae4625d51c90dc72c22266.png).
5.   ![\Pi_{\vec{d}}(\vec{v}_1) = (5.79, 5.79)](./images/0794c23527371b073eb4172e3e2677ecd9367a9b.png) and ![\| \Pi_{\vec{d}}(\vec{v}_1) \| = 8.19](./images/866c0ee5805400fdafd858683e0612a79447b162.png); ![\Pi_{\vec{d}}(\vec{v}_2) = (6.83,6.83)](./images/8ccca85de95fc0df07410f0e47a5b67473d54aeb.png) and ![\| \Pi_{\vec{d}}(\vec{v}_2) \| = 9.66](./images/2f4eeb3e63ee634d23141fb7787ea9995c12fb2b.png); ![\Pi_{\vec{d}}(\vec{v}_3) = (6.83,6.83)](./images/b27c1eb744b8245e84264f4ccba943df748caa3d.png) and ![\| \Pi_{\vec{d}}(\vec{v}_3) \| = 9.66](./images/4833246d5c5fd5019fe4bca80924921725c5a0c0.png); ![\Pi_{\vec{d}}(\vec{v}_4) = (1.83,1.83)](./images/6d03985227f0cf2896e9f216b81326e6a4de4b8d.png) and ![\| \Pi_{\vec{d}}(\vec{v}_4) \| = 2.59](./images/2092b5e4a86244a743c459559045ff08a445a9dd.png).

**E2.7**

1.  ![\begin{bmatrix}3 & 2\\ 4 & 1\end{bmatrix}](./images/c318b7b747ea8d90e4309a8c4d9b0dfd2a62ce0e.png);
2.  ![\begin{bmatrix}-2 & 2\\3 & -2\\0 & 1\end{bmatrix}](./images/83348159ae16952a8e9fd79f3095aa10268c5579.png);
3.  ![\begin{bmatrix}17 & 16\\8 & 9\end{bmatrix}](./images/cf9b557bc8b131cafd622e8185e0889424aa2150.png);
4.  ![\begin{bmatrix}13 & 12 & 11 & 10\\2 & 3 & 4 & 5\end{bmatrix}](./images/e73498a6a1217d228e4609734b17e31c8150e73b.png);
5.  ![\begin{bmatrix}2 & 1 & 4\\-2 & 4 & 1\end{bmatrix}](./images/6cbb7267431ba3615db3d4be4143a96d76e3c405.png);
6.  Doesn’t exist;
7.  ![\begin{bmatrix}-2 & -6\\5 & 10\\2 & 1\end{bmatrix}](./images/472c2fbee55dad48315fd1ea0ae52cf06f13b090.png);
8.  ![-5](./images/c022472a0124cfa19d9a34beed2081ce3db04b55.png);
9.  Doesn’t exist;
10.  Doesn’t exist;
11.  ![-5](./images/c022472a0124cfa19d9a34beed2081ce3db04b55.png);
12.  ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png);
13.  ![4](./images/052f98fd6b37228ecd75b2b373f9a31bb8f6a7a1.png);
14.  ![4](./images/052f98fd6b37228ecd75b2b373f9a31bb8f6a7a1.png).

**E2.8**

1.  ![14](./images/b0edc2bf75b619110ab76f7086b4c9a26b6988ba.png);
2.  ![5](./images/f2fa057f2254981666da1b26f97fb103f09600a3.png);
3.  ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png);
4.  ![\begin{bmatrix}1 & 2 & 3\\2 & 4 & 6\\3 & 6 & 9\end{bmatrix}](./images/364c124dd2a586389a7cdd855313d08a07cad892.png);
5.  ![\begin{bmatrix}4 & -2 & 0\\-2 & 1 & 0\\0 & 0 & 0\end{bmatrix}](./images/bca317839afc57f9f21eeee2f0d872236db33134.png);
6.  ![\begin{bmatrix}2 & -1 & 0\\4 & -2 & 0\\6 & -3 & 0\end{bmatrix}](./images/bfc38ed2e4a8bbe234dc4e417d95b3aeb5d597d0.png).

**E2.9**  ![\alpha=-\frac{1}{2}](./images/cf4273d9ca7c632444c2d3f1a36c40454ce3967a.png) and ![\beta = 12](./images/0ddd024b7fcf4fa0e9286cb621bbc296221c5776.png). **E2.10**

1.  Yes;
2.  No;
3.  Yes.

### Solutions to selected exercises

**E2.1** To find ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png) we must consider the action of ![A=\begin{bmatrix}7 & 0 \\ 0 & 2\end{bmatrix}](./images/753816ed79710c268e50912a515105b34fd67c6c.png) on an arbitrary vector ![\vec{v}=\begin{bmatrix}v_1 \\ v_2\end{bmatrix}](./images/da231759c16a35b6d0dcf91c14a1316e5c1e1564.png), and perform the inverse action. Since ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) multiplies the first component by ![7](./images/9dae2aeb6d96ce448b7d241f9bd2a689ff2c409a.png), ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png) must divide the first component by ![7](./images/9dae2aeb6d96ce448b7d241f9bd2a689ff2c409a.png). Since ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) multiplies the second component by ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png), ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png) must divide the second component by ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png). Thus ![A^{-1} = \begin{bmatrix}\frac{1}{7} & 0 \\ 0 & \frac{1}{2}\end{bmatrix}](./images/72560fca8a50f8f73ac1a58f014e87e5e6f4f40c.png).

**E2.10** An expression is linear in the variable ![v](./images/14593f3784642e49a79b179a9f00f7f98ec4f6e3.png) if it contains ![v](./images/14593f3784642e49a79b179a9f00f7f98ec4f6e3.png) raised only to the first power. This is the case for the first and third expressions but not the second, since it contains ![\sqrt{x} = x^{\frac{1}{2}}](./images/872989b538b506c1e9c77466152f508d66abbcfc.png).

### Answers to problems

**P2.1**

1.   ![q(x)](./images/6efeae8e74c414f73475eed433a0a226e3d23292.png) is nonlinear;
2.  ![f(x)](./images/e991ff22266fdbbf51e9ab850aa72059edbea8de.png), ![g(x)](./images/ca1163900e1dfcd5ebd78751df0c1df474872bb9.png), and ![h(x)](./images/0405de510835a85e4f87d8997b77ec463d581e4f.png) are all linear;
3.   ![i(x)](./images/906974744ae9459d0ee6aff3d3dbb5af6270f0e3.png) is nonlinear;
4.   ![j(x)](./images/0c000c757e02477b36bf14ec04fb96f8018f5c5a.png) is nonlinear.

**P2.2** ![(1,2,3)](./images/3464a91f2b8b725144a7b77e5eef7bb9733b88f1.png). **P2.3** ![\ket{a}+\ket{b} = 5\ket{0} +2\ket{1}](./images/8b07153a245083300ba90ed06b11239cc52774b0.png). **P2.4** **a)** 0; **b)** ![(0,0,1)](./images/ab463cdeea40b18339c2010619c8b3ff716061bb.png); **c)** ![(0,1,-1)](./images/268bf582ea4e1e6733c8f2ace2350c46461116a2.png); **d)** ![(0,0,-1)](./images/5389f896622ca7a3cd42ad7f767c121a30a1d760.png). **P2.5** **a)** ![5](./images/f2fa057f2254981666da1b26f97fb103f09600a3.png); **b)** ![(-1, 1, 1)](./images/e8396e15486f87fd0f26233ae3ff860ca3fab81f.png); **c)** ![(0, 0, 0)](./images/b9ea26d6179acf575343bff96f0677c7583b7bd6.png); **d)** ![(0, 0, 0)](./images/b9ea26d6179acf575343bff96f0677c7583b7bd6.png). **P2.6** **a)** ![6](./images/160a910df642692dd50f0862138b3bc151d89988.png). **b)** ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png). **c)** ![-3](./images/90c76b79a3ab345cb1b4c158ecd5457a570bc393.png). **d)** ![(-2, 1, 1)](./images/578b43959657cd12deb1932ad07c6cc46e4404fa.png). **e)** ![(3, -3, 0)](./images/55c52c821f2ef604a7f4dc9a4e9a985300a6e806.png). **f)** ![(7, -5, 1)](./images/c4ba414825f89447bb6362a84343f25876cb4ad1.png). **P2.7** **a)** ![(2,3,3,7,8)](./images/9e98a8623a75ab2adec923dc2ccf7fe5d4a86204.png). **b)** ![(0,-1,-3,-1,-2)](./images/ce8e9a138c18734edc41cd504be8ee238b701a77.png). **c)** ![30](./images/d31688897adee961e35ff339d4f8367fd0ebe922.png). **P2.8**  ![(-\frac{2}{3}, \frac{1}{3}, \frac{2}{3})](./images/f117a9f15c714bdc96dedf31da9e74111460e261.png) or ![(\frac{2}{3}, -\frac{1}{3}, -\frac{2}{3})](./images/d3440460527dd78a504d79d6e276e02d21e581f2.png). **P2.9** ![(12, -4, -12)](./images/69cd40469a20244f7068f721ecaa4537d32ddfdd.png). **P2.10** The tractor’s trajectory is a half-circle. The total distance travelled is ![3.14](./images/b9965aab5a029f38e19efb03746175726ba43fef.png) km. **P2.12** ![M\vec{v} = \begin{bmatrix} \alpha z_1 + \beta z_2 \\ \gamma z_1 + \delta z_2 \end{bmatrix}](./images/4f9292309a67e81e91d1a7f207aaaed2bd3b148b.png). **P2.13** ![A=\begin{bmatrix}3 & 0 \\ 0 & 1\end{bmatrix}](./images/38bca1d8e9323ca5d20f5fb0a6aed137d6b8091b.png); ![B=\begin{bmatrix}1 & 1 \\ 0 & 1\end{bmatrix}](./images/3de083df7be1d0c2ac78958f6858f804ac5d1b42.png); ![C=\begin{bmatrix}3 & 1 \\ 0 & 1\end{bmatrix}](./images/374733c130eaa46f2e3f2238a00124cf1a75be98.png). ![AB=\begin{bmatrix}3 & 3 \\ 0 & 1\end{bmatrix}](./images/d78a87fd71a0423d665fff1724c459f99b897825.png); ![BA=\begin{bmatrix}3 & 1 \\ 0 & 1\end{bmatrix}=C](./images/9971857d199895b477b048578357ee34785e15c7.png). **P2.14**

1.  ![\begin{bmatrix}-5 & -5\\4 & 2\end{bmatrix}](./images/1a3af6904911f39e52405292ed0595101eca89f1.png);
2.  ![\begin{bmatrix}-5 & 10 & -5\\20 & 5 & 10\end{bmatrix}](./images/33571bf8e3bf956c61b1fcb9605ee8170c429477.png);
3.  ![\begin{bmatrix}17 & 28\\41 & 64\end{bmatrix}](./images/ae5c8027b308bcc37b94f16b935842d4954ed62c.png);
4.  Doesn’t exist;
5.  ![\begin{bmatrix}18 & 21\\9 & 12\\8 & 9\end{bmatrix}](./images/7a668766222e16e1a8801a4237530d6667ec4ae3.png);
6.  ![\begin{bmatrix}9 & 12\end{bmatrix}](./images/6bfb81b5fc691676119c3b60dadc8ec148aee4b3.png);
7.  ![\begin{bmatrix}-4 \\ -7 \end{bmatrix}](./images/7d9e18217e6e97b65f5984a4fc6f303ab093f230.png);
8.  ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png);
9.  ![\begin{bmatrix}2 & 1\\-4 & -2\end{bmatrix}](./images/c278e79edf4cf7f225d9d24c7f0b139d88251bfa.png);
10.  ![8](./images/50c8b4df6905af6190f7d236bc17391db40df469.png);
11.  ![11](./images/06e9e340f49db965f008cbc1ab1c98681948d6fe.png);
12.  ![-3](./images/90c76b79a3ab345cb1b4c158ecd5457a570bc393.png);
13.  ![20](./images/2c31b5640cc4b45a9728a4879f35d0339017ef22.png).

**P2.15**

1.  ![\det(B)](./images/84e3b5af457901ea7e48e4584b30eedbedd626e1.png);
2.  ![\det{A}](./images/399a8dd3ddb9868f7eafb5a36012a1fa55dd4202.png);
3.  ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png).

**P2.16**

1.  ![6](./images/160a910df642692dd50f0862138b3bc151d89988.png);
2.  ![\frac{3}{2}](./images/73ed5270656d2a2441766fc8c06c10c08465190b.png);
3.  ![15](./images/381913d2ae1bbde5835eb40cbcd3a0dec6013ceb.png);
4.  ![30](./images/d31688897adee961e35ff339d4f8367fd0ebe922.png).

### Solutions to selected problems

**P2.1** A function is linear in ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) if it contains ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) raised only to the first power. Basically, ![f(x)=mx](./images/e5e278f41f122b0ff9f92b80c92f455fe6e96938.png) (for some constant ![m](./images/89bd9dbe770020ab4a4b963d537e5e619b5ee2ef.png)) is the only possible linear function of one variable.

**P2.8** See[`bit.ly/1cOa8yo`](./1cOa8yo.md) for calculations.

**P2.9** Any multiple of the vector ![\vec{u}_1 \times \vec{u}_2 = (-3,1,3)](./images/c534de7c8cf50c0b6f1fe8c097e0948e54b7d9ec.png) is perpendicular to both ![\vec{u}_1](./images/9132905adb136b3def7253541a01ea011c15ddb4.png) and ![\vec{u}_2](./images/572c45ec2091843fffe32379c62653300bf21b2d.png). We must find a multiplier ![t \in \mathbb{R}](./images/e6250d87e22942b35ab92c53add74e23867cc87a.png) such that ![t(-3,1,3) \cdot (1, 1, 0) = 8](./images/eec1f7d12d35be340420b9c87da44d2c7cb5da48.png). Computing the dot product we find ![-3t + t = 8](./images/2404229b4598caeba0b24bdec8ecdb36e162fbfb.png), so ![t=-4](./images/fdc11c90b7aa1c9bdd4d33b397f258dcb3a1419f.png). The vector we’re looking for is ![(12, -4, -12)](./images/69cd40469a20244f7068f721ecaa4537d32ddfdd.png). See[`bit.ly/1nmYH8T`](./1nmYH8T.md) for calculations.

**P2.10** The direction of the tractor changes constantly throughout the day, and the overall trajectory has the shape of a half-circle. The total distance travelled by the tractor is equal to half the circumference of a circle of radius ![R](./images/71ce7fefa53db4a14c0017370cefd764e17150d5.png). Since it took the tractor six hours of movement at ![v=0.524](./images/e780c938577bc2f7734209377d43c2893a5dedd4.png) km/h to travel half the circumference of the circle, we have ![\frac{1}{2}C = \pi R = v(t_f-t_i) = 0.524(6)](./images/6fbddc78f052015578cac1a066cc3c32a0f68d62.png), from which we find ![R=1](./images/a185b4091bae2a9c1741b341e02300a13b81eccc.png) km. The total distance travelled by the tractor is ![\pi R = 3.14](./images/56158d6bffcf655fb3ecc4165d9ce347f727b7f6.png) km.

**P2.11** Using algebra we find ![\| \vec{u}-\vec{v} \|^2 = \| \vec{u} \|^2  + \| \vec{v} \|^2 - 2 \vec{u} \cdot \vec{v}](./images/3823c0a5b977827d597a721731703dbc9e4caf21.png). Using the cosine rule we find ![\| \vec{u}-\vec{v} \|^2 = \| \vec{u} \|^2  + \| \vec{v} \|^2 - 2\|\vec{u}\|\|\vec{v}\|\cos(\varphi)](./images/8b5110bec87ffc960afcbcab3bca79a7440e10a5.png). Equating these two expressions, we can obtain the geometric formula for the cosine product.

**P2.13** Using the definition of the matrix vector product, we can imitate the action of each linear transformation ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) by choosing appropriate entries in the matrix. The top row corresponds to the first component of the output; the bottom row corresponds to the second component of the output. Observe that ![BA=C](./images/7d95ff49501e88639db0aad808398d5f896ebaaa.png). The composite transformation of applying ![T_A](./images/4572faefffc69b8739c22f15ee38b8bd432eaddd.png) followed by ![T_B](./images/6a8762f8f1dc0f5953ad880229ce3ac4cdd5d0c8.png) (denoted ![T_B \circ T_A](./images/7bc5b90360c148aa8e3c4ba4e0160c8d47f6e94d.png)), is equivalent to the transformation ![T_C](./images/c394317ccc160c06d0f15d5807c441495ff8cc26.png). Note ![AB \neq BA](./images/abeba309f663275c0ee0fbbd488d4820dabf5c5a.png): the matrix product ![AB](./images/ba90019888e8cb9ef51160a7cd7cb8ec3c63edda.png) corresponds to compositing the composition of the linear transformations in the opposite order ![T_A \circ T_B](./images/50b95f5a252c67c3481c05ab6d50b253fcf91776.png).

##[Chapter 3 solutions](./Front matter.md)

### Answers to exercises

**E3.1** ![x=4](./images/36d0b58300a983e0f07427c9f5678dd357dc4e7a.png), ![y=-2](./images/b90f3e0bce2932d09765ce62a3c09a394d83815c.png). **E3.3**

1.  No solution;
2.  ![(0,2)](./images/01a81606440a03d4a10e95c4cbe7b3800e87ebcd.png);
3.  ![\{ (2,0) + s(-1,1), \forall s \in \mathbb{R}\}](./images/2950ba0c30490c9bc2ccda220d0de9c83d689cc8.png).

**E3.4** **a)** ![X = BA^{-1}](./images/806cfea0b45552eb331951564ddf5e1f937717e1.png); **b)** ![X = C^{-1}B^{-1}A^{-1}E D^{-1}](./images/fd349165a84295c0b87e1e30cf8f22f3500186ff.png); **c)** ![X=AD^{-1}](./images/c059288e9cc8e57f298b36005ba4d91ed9f227d1.png). **E3.5** ![P=\begin{bmatrix} 19 & 22 \\  43 & 50  \end{bmatrix}](./images/c8489ddf6497bb8e37a313e2b658e06e856657e4.png); ![Q=\begin{bmatrix} -5 & 9 \\  \; 8& 6  \end{bmatrix}](./images/7d09e84d5f46d69f704a480143fb5e310ac0ddd5.png). **E3.6**

1.  ![\begin{bmatrix}19 & 24\\40 & 51\end{bmatrix}](./images/3041b0dcde6db19bea691c40ca44405d5c101fee.png);
2.  ![\begin{bmatrix}57 & 88\\11 & 24\end{bmatrix}](./images/eb1d6f848f9e54859af4b1772588edd33b30a7da.png);
3.  ![\begin{bmatrix}17 & 28\\41 & 64\end{bmatrix}](./images/ae5c8027b308bcc37b94f16b935842d4954ed62c.png);
4.  ![\begin{bmatrix}54 & 69\\22 & 27\end{bmatrix}](./images/b1ab690c080212fb48ded7dad782a36cffd86bc4.png);
5.  Doesn’t exist;
6.  ![\begin{bmatrix}18 & 21\\9 & 12\\8 & 9\end{bmatrix}](./images/7a668766222e16e1a8801a4237530d6667ec4ae3.png);
7.  ![-165](./images/ff7bc22f60989599cd37358289b9f93afc66e0c0.png).

**E3.7**

1.  ![-2](./images/8f479dcb6ed2867a0aed7ffa9c0d19f060cb5b5e.png);
2.  ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png);
3.  ![4](./images/052f98fd6b37228ecd75b2b373f9a31bb8f6a7a1.png);
4.  ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png).

**E3.8** ![V=2](./images/6a54c8b87b168d777fb6b7632dbe4cb3c11f0e41.png). **E3.9** Linearly independent. **E3.10**  ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png) exists for all ![\alpha\neq6](./images/d0a974bb0bb06c6cc2ef80cd89db1d843d8e6ada.png). **E3.11** ![A^{-1} = \begin{bmatrix} 2  &  -1 \\ -1  & 1 \end{bmatrix}](./images/4bc3dd980defd2eb0f04773361b62ad03e9b9130.png). **E3.12**  ![x=-8](./images/782bf103464fb3ff9980745754ac6b2ad8aad23c.png) and ![y=3](./images/3919dc65bc2a8ac61e72bdbbc22f6a26a0fb062c.png).

### Solutions to selected exercises

**E3.2** The row operations required to bring `A` to reduced row echelon form are: ![R_1 \gets \frac{1}{3}R_1](./images/8bed9da2f194c72ca884a4a422e7aeb69052c5d6.png), ![R_2 \gets R_2 -2R_1](./images/11cb0c8e23ed206b7d8ff7afdfab489ec0fa14d8.png), ![R_2 \gets -2R_2](./images/8e280ffd6097330f24deb290ce97e8471323e19b.png), ![R_1 \gets R_1 - R_2](./images/ab66855edb341245eb61d47b836fa50eff57f12a.png). Using `SymPy` these operations are implemented as follows:

\>>> A\[0,:\] = A\[0,:\]/3
>>> A\[1,:\] = A\[1,:\] - 2\*A\[0,:\]
>>> A\[1,:\] = -2\*A\[1,:\]
>>> A\[0,:\] = A\[0,:\] - A\[1,:\]

Try displaying the matrix `A` after each operation to watch the progress.

**E3.8** See[`bit.ly/181ugMm`](./181ugMm.md) for the calculations.

**E3.9** We can determine if the vectors are linearly independent by constructing a ![3 \times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) matrix from them and computing the determinant. In this case, we have ![\det\!\left( \begin{bmatrix}1 & 4 & 3\\2 & 1 & 1\\0 & -2 & -1\end{bmatrix} \right) = -3 \neq 0](./images/f2debe63da7ea8c45ffabdfe7ef2fd383c464112.png) so the vectors are linearly independent.

**E3.12** We can solve the equation ![A\begin{bmatrix}x \\ y\end{bmatrix}\! = \vec{b}](./images/bbf78ce2429f62666fe80c3ab817e0238ae5d2f9.png) by multiplying the equation by the inverse ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png). We find ![A^{-1} = \!\begin{bmatrix}-2 & -3\\1 & 1\end{bmatrix}](./images/830c38c312c68f2a54d7c9e1e8c5ad8b56b1d89c.png) and ![\begin{bmatrix}x \\ y\end{bmatrix} \! = A^{-1}\vec{b} = \! \begin{bmatrix}-8 \\ 3\end{bmatrix}](./images/51cc86e0f78241a392b3f044a637986da4251c98.png).

### Answers to problems

**P3.1**  ![x=15](./images/6e9c6712fae489b8b6e9a5d21906293743544abe.png) and ![y=2](./images/cc6e2caf510e8ab2df5cb330b62b88df743e132e.png). **P3.2**

1.  Alice: ![R_2 \gets R_2 -2R_1](./images/11cb0c8e23ed206b7d8ff7afdfab489ec0fa14d8.png), ![R_2 \gets -2R_2](./images/8e280ffd6097330f24deb290ce97e8471323e19b.png), ![R_1 \gets R_1 - R_2](./images/ab66855edb341245eb61d47b836fa50eff57f12a.png);
2.  Bob: ![R_2 \gets R_2 - 2R_1](./images/11cb0c8e23ed206b7d8ff7afdfab489ec0fa14d8.png), ![R_2 \gets \frac{-2}{3}R_2](./images/ebaeb07cd9c3ae589cf2883d10a44afad5c34933.png), ![R_1 \gets R_1 - \frac{3}{2}R_2](./images/acd470eed1af13a841441a99529a2a768b3bd877.png);
3.  Charlotte: ![R_1 \gets \frac{1}{2}R_1](./images/a721390a041e541a37fc242fe7bd9f9d672c9d90.png), ![R_2 \gets R_2 -3R_1](./images/5c63cbc85af5dd7f22961cd9e336d4170e6db49a.png), ![R_2 \gets \frac{4}{3}R_2](./images/512c146cd618eb42091bee5214393a184de32f2c.png), ![R_1 \gets R_1 - \frac{3}{4}R_2](./images/a69541ba951fd3818ba6bf880625d29f3b41ed4a.png).

**P3.3**

1.  ![(-2,2)](./images/7fe0c047138a16e94540a84f8f2a9069c8397ab3.png);
2.  ![(-4, -1,-2)](./images/264677547d50a300c4a39107dd306443f26db34e.png);
3.  ![(\frac{-2}{5}, \frac{-1}{2}, \frac{3}{5})](./images/32717cadaba29c3d8068980463fcceaf7d5fa61c.png).

**P3.4**

1.  ![\{ (2,0) + s(-2,1), \; \forall s \in \mathbb{R}\}](./images/4126b2dbba9ed38fcf9ea715744eb1fd60458959.png);
2.  ![\{ (2,1,0) + s(3,1,1), \; \forall s \in \mathbb{R}\}](./images/29bbf00a1e05f486733478cc0c5e510288f48f62.png);
3.  ![\{ (\frac{1}{10},0,\frac{3}{5}) + \alpha(1,1,0), \forall \alpha \in \mathbb{R}\}](./images/517656306a1420fa8cd76576fe10d26954efbc94.png).

**P3.5**

1.  ![\{ (1,0,0) + s(1,1,0) + t(2,0,1), \forall s,t \in \mathbb{R}\}](./images/39351d2203f298f16453659e801c531f0d11bb1f.png);
2.    ![\{ (\frac{1}{10}, 0, \frac{3}{5}, 0)](./images/f2b5d2c1516ed40b4a2ba60644b2b66606e4d8a3.png) ![+\;\alpha(1, 1, 0, 0)](./images/36b06c630866086d9b399b121441acf022341a4f.png) ![+\;\beta(-\frac{1}{10}, 0, -\frac{3}{5}, 1)](./images/1635d149ab80f5deee744eca3cd7718132fec811.png), ![\forall \alpha, \beta \in \mathbb{R}\}](./images/e28df2655f7da328858112ba0642704a0cb511f2.png).

**P3.6**

1.   ![\begin{bmatrix}
    x_1\\
    x_2\\
    x_3
    \end{bmatrix}
    \in](./images/9da01c46a3ca66fe4063fff3772bfc8333d5148e.png) ![\left\{
    \begin{bmatrix}
    0\\
    0\\
    0
    \end{bmatrix}		
    +
    t\begin{bmatrix}
    1\\
    -1\\
    1
    \end{bmatrix},
    \; \forall t \in \mathbb{R} \right\}](./images/438451e59e3e3f3b543f0d86a9a13805ec263508.png).
2.   ![\begin{bmatrix}
    x_1\\
    x_2\\
    x_3
    \end{bmatrix}](./images/225e4db8e5a97ccce7432d9cd6b1b2f52b9e36c1.png) = ![\begin{bmatrix}
    0\\
    -2\\
    5
    \end{bmatrix}](./images/7583121e13e21198cff39080fea2fca8045bce05.png).
3.   ![\begin{bmatrix}
    x_1\\
    x_2\\
    x_3
    \end{bmatrix}](./images/225e4db8e5a97ccce7432d9cd6b1b2f52b9e36c1.png) = ![\Big\{
    \begin{bmatrix}
    \frac{3}{2}\\
    \frac{1}{2}\\
    0
    \end{bmatrix}](./images/2182dcec2a3b76b6767c00a87bf9b3cb4257f33c.png) ![+\;
    t\begin{bmatrix}
    0\\
    -2\\
    1
    \end{bmatrix},
    \; \forall t \in \mathbb{R} \Big\}](./images/24e3a4accbcb599184516cf49f2deb0ac97547a9.png).

**P3.7** ![\textrm{rank}(A) \leq 4](./images/141d3134aa38d7303c00cf3f4944c1dd75d32cdb.png). **P3.8** ![C=B^{-1}](./images/2b9d0b26c17b7ef03aca613ed177911e42d3f8a2.png). **P3.9**

1.  ![M^{-1}L^{-1}MK^2](./images/aa38e821c09bc9326b156c6d231f16de27360c9b.png);
2.  ![J^{-3}K^{-1}J^{2}](./images/05f98339db3bd9a2682a29e4505cfd182e4095f7.png);
3.  ![A=\frac{1}{2}\mathbbm{1}](./images/6997957149317f1155530e0ae36d8cff5716fa3f.png);
4.  ![Y=N^{-1}](./images/ec1a55e03b3f6b53ee986cf5b1da963cb7dc5dc6.png).

**P3.10** ![\vec{x}=(-7, -19,-3)^\sfT](./images/cff47d04a3f008288eea1cab37797172d50bbb2a.png). **P3.11** ![\vec{x}=(30.64,10.48,17.06)](./images/80332b5e435e21a831aef0304c643b0c91af0cb6.png). **P3.12** **a)** ![AB=\begin{bmatrix}
6 & 2\\
10 & 2\\
11 & 3
\end{bmatrix}](./images/c37cac760e1fc749b48eba896418fc84551be9e9.png). **b)** ![AA=\begin{bmatrix}
4 & 6 & 3 \\
6 & 18 & 8\\
3 & 7 & 5
\end{bmatrix}](./images/0c1679d186a6cd52afaf6f590359d306b596c8b6.png). **c)**  ![BA](./images/963b816e55c8e1a8ee9f5511d1fc2f015eb274b3.png) doesn’t exist. **d)**  ![BB](./images/b74d50f33ae1ab12edd49b4d9a64d2fad8a8871a.png) doesn’t exist. **P3.13** ![\begin{bmatrix}
-2 & -2\\
-15 & -15
\end{bmatrix}](./images/def64dcdef851ad1b89c62102b0987b230b7f860.png). **P3.15**

1.  ![\begin{bmatrix}13 & 5 & 3\\6 & 9 & 12\\6 & 5 & 16\end{bmatrix}](./images/ef5d67f4b04746475e02a94f7c90d0563f1bec81.png);
2.  ![\begin{bmatrix}-6 & 7 & 5 & -5\\-9 & 15 & 18 & -3\\-7 & 19 & 10 & 5\end{bmatrix}](./images/afe9a4cac4a63fd23b5a15708c035d50746d72b9.png);
3.  ![\begin{bmatrix}4 & -4\\24 & 3\\18 & 17\end{bmatrix}](./images/762d6fc5bf6674d53128c0d3f69a8263a6c66688.png);
4.  ![\begin{bmatrix}-8 & -5 & -8\\15 & 7 & 23\\3 & 9 & 9\\-1 & -3 & 7\end{bmatrix}](./images/70dbd2b54a5541e4e658e0b9841023389c2390cd.png);
5.  ![\begin{bmatrix}4 & 11 & 18\\6 & -1 & 22\end{bmatrix}](./images/b8e529285d0d35abf9fb077a401e8fdd3e306545.png);
6.  ![\begin{bmatrix}-51 & 92 & 55 & -10\\-49 & 58 & 85 & -40\end{bmatrix}](./images/ae1988621e36364f4b97db36b11a915c5de5d10f.png).

**P3.16** **a)** ![\begin{bmatrix}
0 						& \; \cos(\alpha)-\sin(\alpha)		\\
\sin(\alpha)-\cos(\alpha)		& \; -\cos(2\alpha)
\end{bmatrix}](./images/cb91fa14136d3515ca04c72b7ae8c52ea48d2669.png); **b)** ![\begin{bmatrix}
\cos^{2}(\alpha) 			& \; - \sin(\alpha)			\\
2 \sin(\alpha) - \cos(\alpha) 	& \; \sin^{2}(\alpha)
\end{bmatrix}](./images/d7e06d398232eeefce1c15d775b23b104acc3695.png); **c)** ![\begin{bmatrix}
\cos(2 \alpha) 				& - \sin(\alpha)			\\
2 \sin(\alpha) - \cos(\alpha) 	& \; 0
\end{bmatrix}](./images/861c51579491c970bf3e20ef449c951a6a4338be.png). **P3.17** **a)** ![-3](./images/90c76b79a3ab345cb1b4c158ecd5457a570bc393.png); **b)** ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png); **c)** ![10](./images/504b25330f8f8570d3f0375f31b97ec9d4a99a91.png). **P3.18** ![\det(A) = -48](./images/1166ec2c9d976c1ba7b9c76881cb4953a24d0077.png); ![\det(B)=13](./images/d0600058cd46efa3a38a233ccd57f04b8b78fd6b.png). **P3.19**

1.  Independent;
2.  Dependent;
3.  Dependent.

**P3.20** Area ![=2](./images/c795c3ede7836d4b4e512d448216c1f3ef90bbf3.png). **P3.21** Volume ![= 8](./images/bc1736f4054d5f0b77db05de2171e145a3277429.png). **P3.22**

1.  ![-2](./images/8f479dcb6ed2867a0aed7ffa9c0d19f060cb5b5e.png);
2.  ![-162](./images/f5b8d2b8a9f325dd331b4a25dafe0acbed9794bd.png);
3.  ![-8](./images/0c1e9fa0a2f8e832c9e611bb330604c0d3f8a8e2.png);
4.  ![-14](./images/e4e86013562edf2d017c6fa07e6648759bcde82a.png);
5.  ![28](./images/9a13dabdab4bcaf5898b7dc025bfa2a48f3711e0.png).

**P3.23** **a)** ![86](./images/ccedf8b59eb3e9316956fd3816d0a671d64b3a9e.png); **b)** ![-86](./images/59237658f4091e5ce174281b30a9da156292998a.png); **c)** ![-172](./images/a2f3683ab178de1cef46d526097f2c2ba945ba5f.png). **P3.24** For both rows and columns: ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png): not independent; ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png): independent; ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png): not independent; ![D](./images/5eadde85cc4d11e6f52f4e09b6059250e60a2ea9.png): not independent. **P3.25** ![\det(J)=r](./images/d423fa1193e13ac66399d39a07438d58d7d94156.png). **P3.26** ![|\det(J_s)|=\rho^2\sin\phi](./images/3f40f69490c18d56cce9487f4936d3e7c2cf47ee.png). **P3.27** **a)** The inverse doesn’t exist; **b)** ![\begin{bmatrix}
5 & -2\\
-2 & 1
\end{bmatrix}](./images/e51fd63da7eaf78bb173c98cad10dac55fd6ad6d.png); **c)** ![\begin{bmatrix}
2 & -\frac{3}{2}\\
-1 & 1
\end{bmatrix}](./images/91756becff83c279f9ac09e7262ab3d448a0c5b4.png). **P3.28** ![B=\begin{bmatrix}
-17 & -30\\
5 & 8
\end{bmatrix}](./images/7a5f58871aeb6d908d903c05b6dfa12b6d2a0b1d.png). **P3.29**  ![A^{-1} = \begin{bmatrix}
- \frac{1}{3} & \frac{2}{3} & - \frac{1}{3}\\
- \frac{2}{3} & \frac{1}{3} & - \frac{5}{3}\\
\frac{4}{3} & - \frac{2}{3} & \frac{7}{3}		\end{bmatrix}](./images/6cb60fb8fe96e7104b0caad6703b2ef74efd51db.png) and ![B^{-1} = \frac{1}{21}\begin{bmatrix}
-3 & -5 & \frac{-21}{6} & 11\\
3 & -2 & 7 & -4\\
9 & 15 & \frac{21}{2} & -12\\
3 & -9 & 0 & 3
\end{bmatrix}](./images/9af041c86b7f787ffab272d2e29bdf8b8fa0adf2.png). **P3.31** ![C_A=\begin{bmatrix}
1 & 2 & -4\\
-2 & -1 & 2\\
1 & 5 & -7
\end{bmatrix}](./images/3939109882b1c90a1d2a8d4f13eb1dc4a1ae0751.png); ![C_B=\begin{bmatrix}
-10 & 6 & -12\\
-4 & -10 & 20\\
1 & 18 & -5
\end{bmatrix}](./images/1abd113759b868fe30c2febd823b789fccca85c1.png); ![C_C=\begin{bmatrix}
0 & 0 & 0 & 0\\
2 & -2 & 2 & -2\\
-4 & 4 & -4 & 4\\
-8 & 8 & -8 & 8
\end{bmatrix}](./images/e01c6d9c50b92993d25d32a9fde3222e639aaf2a.png). **P3.32** ![A^{-1} = \begin{bmatrix}-1 & 1 & -2\\-1 & \frac{1}{2} & - \frac{5}{2}\\2 & -1 & 4\end{bmatrix}](./images/660ddbc5e47ae3fbcb2dcbf7b0c91a35d33ffe08.png). **P3.33** ![a=-3](./images/6d36602b669cb8edd979705d9411fbbdf42ebec8.png), ![b=1](./images/c7dc76ed6d7e379f0c8c71145046853a7dc95332.png), ![c=2](./images/add9738294ab73ea45e091cccb1c5d6aa2a30941.png), ![d=-2](./images/a80d333ea7d105c330e9772f1ea6d188df72d661.png). **P3.34**  ![\begin{bmatrix}
1 & -1\\
2 & 2
\end{bmatrix}
\begin{bmatrix}
-1 & -1\\
1 & 2
\end{bmatrix}
=
\begin{bmatrix}
-2 & -3\\
0 & 2
\end{bmatrix}](./images/065daf192973ad408ff443de05284769ba325882.png). **P3.35**  ![B=SA](./images/f1abf8a718f580cd9e8533905aa47330d49d8c5b.png) and ![C=AS](./images/44f25c33172ed5d29fa18a69899fb2c02db515af.png), where ![S= \begin{bmatrix}\alpha & 0 \\ 0 & \beta\end{bmatrix}](./images/fedb1fa5e9865a9836fc9af12c58eb0480cf343b.png).

### Solutions to selected problems

**P3.7** Since the system of equations ![A\vec{x} = \vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) has an infinite number of solutions, the RREF of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) must contain at least one row of zeros. Therefore, the rank of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) can be at most ![5-1=4](./images/b414eeba35c58b75086e098a5d4a0914d1bdd09b.png).

**P3.8** First simplify the equation by multiplying with ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png) from the left, and with ![D^{-1}](./images/1b9a30d84e0eccf458fdc37721fe5941ee2e9a98.png) from the right, to obtain ![BC=\mathbbm{1}](./images/d4ae7f580d3a1fe93d6e1d3e8db4d19ce994c95d.png). Now we can isolate ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) by multiplying with ![B^{-1}](./images/f930552c0ccebcac8f983e8b777e8dd2b1f6a4e7.png) from the left. We obtain ![B^{-1} = C](./images/d7ddd2f6ab5e17be81805a8e6f45199d40389050.png).

**P3.11** Start by rewriting the matrix equations as ![(\mathbbm{1} - A)\vec{x} = \vec{d}](./images/75875260be86eed4e1d16c388163b536f5d548c4.png), then solve for ![\vec{x}](./images/d253d396ee7731d3b565bf2ff5bf610db05cf3eb.png) by hitting the equation with the appropriate inverse: ![\vec{x} = (\mathbbm{1} - A)^{-1}\vec{d}](./images/86e3edd641db0598245dc40ac1f6da19d670f894.png). See[`bit.ly/1hg44Ys`](./1hg44Ys.md) for the details of the calculation.

**P3.14** First rewrite ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png) as ![\frac{1}{\sqrt{2}}\begin{bmatrix}1 & 1\\1 & -1\end{bmatrix}](./images/83a82140ea2f48e89e028d89bb0f6888a7a4d2f8.png) to simplify calculations. Then computing ![HXH](./images/e9339d4b30b85ee65c6b6e87557a3efbc01d8246.png) gives us ![HXH =
\frac{1}{2}\!\left( \begin{bmatrix}1 & 1\\1 & -1\end{bmatrix}
\begin{bmatrix}0 & 1\\1 & 0\end{bmatrix} \right)\!
\begin{bmatrix}1 & 1\\1 & -1\end{bmatrix}
=	\frac{1}{2}	\begin{bmatrix}1 & 1\\-1 & 1\end{bmatrix}
\begin{bmatrix}1 & 1\\1 & -1\end{bmatrix}
=	\frac{1}{2}	\begin{bmatrix}2 & 0\\0 & -2\end{bmatrix}
= Z](./images/4b6b876ddfc5c5652a3088f69f3ee6ace301e1f7.png). The calculation for ![HZH](./images/6c436e9caaba2003aaaf55c72ff87222cb07566f.png) is similar and it leads to ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png).

**P3.19** We can determine if the sets of vectors are linearly independent by combining them to form a matrix then computing this matrix’s determinant. If the determinant of the matrix is nonzero, the vectors are linearly independent.

**P3.23** The answers in **a)** and **b)** have different signs because interchanging rows in a matrix changes the sign of the determinant. For part **c)**, we use the fact that multiplying one row of a matrix by a constant has the effect of multiplying the determinant by the same constant.

**P3.24** We can calculate the determinant of the matrix to check if its rows are independent. If the determinant is not zero then vectors are independent, otherwise vectors are dependent. The columns of a square matrix are linearly independent if and only if the rows of the matrix are linearly independent.

**P3.25** The determinant of ![J](./images/7053e93a03d11c5be84f3a4f2126b24ee27efd4d.png) is

![\begin{vmatrix}
\cos\theta		&		-r\sin\theta		\\
\sin\theta		&		r\cos\theta
\end{vmatrix}
=
r\cos^2\theta + r\sin^2 \theta
=
r.](./images/cb9bae7d0cb6f7b3b60a4de0b48bb420b4cd9fd1.png)

**P3.26** The determinant of ![J_s](./images/2fcb519205af68d200e416c303e95a720804f52f.png) is

![\begin{align*}
\det(J_s)
&=
\begin{vmatrix}
\sin\phi\cos\theta		&		-\rho\sin\phi\sin\theta	&	\rho\cos\phi\cos\theta	\\
\sin\phi\sin\theta		&		\rho\sin\phi\cos\theta	&	\rho\cos\phi\sin\theta		\\
\cos\phi				& 		0				&	-\rho\sin\phi
\end{vmatrix}																\\
&=
\rho^2\left(
\cos^2\phi  \sin\phi
(-1)
\; - \;
\sin^3\phi (1)
\right)																			\\
&=
-\rho^2\sin\phi\left(\cos^2\phi  + \sin^2\phi\right)
= -\rho^2\sin\phi.
\end{align*}](./images/83cc100569f2a96d186401a8e0dcc0d4e465092c.png)

Since we’re only interested in finding the _volume factor_ we can ignore the sign of the Jacobian’s determinant: ![|\det(J_s)|=\rho^2\sin\phi](./images/3f40f69490c18d56cce9487f4936d3e7c2cf47ee.png).

**P3.28** To solve for the matrix ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) in the equation ![AB=C](./images/7de256cf406312440b51cdc5e3a31e5d747b8e0c.png), we must get rid of the matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) on the left side. We do this by multiplying the equation ![AB=C](./images/7de256cf406312440b51cdc5e3a31e5d747b8e0c.png) by the inverse ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png). We find the inverse of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) by starting from the array ![[\;A\; | \; \mathbbm{1}\:\; ]](../Images/0646aa44a0a4dd7e995be55738aa651310726ed7.png), and performing the row operations ![\mathcal{R}_1: R_2 \gets R_2 -2R_1](./images/64e8323853af68e48e46e76b58903d86a7dc93e9.png), ![\mathcal{R}_2: R_2 \gets -R_2](./images/a59e0543d7d214b8aecda883bd87d517b237bdfb.png), and ![\mathcal{R}_3: R_1 \gets R_1 -4R_2](./images/6c002fdfb9a5a7359d3047859b3b0dcd045f7351.png), to find the matrix ![A^{-1} = \begin{bmatrix}-7 & 4\\2 & -1\end{bmatrix}](./images/ba4cbcc276cb096cc76505aeddc62075eff9fddd.png). Applying ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png) to both sides of the equation, we find ![B=A^{-1}C=\begin{bmatrix}-17 & -30\\5 & 8\end{bmatrix}](./images/98fc53da72f349e31a2d8164ee7bbf8d1654cad5.png).

**P3.30** Zero matrix has the ![\det(A)=0](./images/8987bfff498c8be808f1f460dff9e047194709bc.png). We have ![A^{-1} = \frac{1}{\det(A)}\textrm{adj}(A)](./images/3989d1ae91f55118127698b355486ecf72f705d3.png). We cannot divide by zero, so the zero matrix has no inverse.

**P3.32** See[`bit.ly/matinvxls`](./matinvxls.md) for the solution.

**P3.33** Find the inverse of ![\begin{bmatrix}1 & 3\\-2 & -1\end{bmatrix}](./images/f88805686e43b957c88b0d6c511493865d46e464.png), then multiply both sides of the equation by the inverse to isolate the matrix of unknowns ![\begin{bmatrix}a & b\\c & d\end{bmatrix}](./images/56c558202b5f37c0cd8edc0b4c9a79e216b9f81f.png).

**P3.34** First we calculate ![\begin{bmatrix}
a & b\\
c & d
\end{bmatrix}
\begin{bmatrix}
e & f\\
g & h
\end{bmatrix}
=
\begin{bmatrix}
ae+bg & af+bh\\
ce+dg & df+dh
\end{bmatrix}
=
\begin{bmatrix}
2ae & ae+ec\\
ce+ca & c^2+ec
\end{bmatrix}](./images/b88883e25c6f30d15aa6c6a567d13dba2e32e970.png). We proceed by comparing the two matrices entry by entry. Observe ![2ae=-2](./images/a9de0bb61eba1c69027ded0134c2945520eb4fee.png), which implies ![ae=-1](./images/366e28c974fd0e13121bb56c825ad81408fdd8cc.png), which allows us to simplify ![ae+ec=-3](./images/00181bdbce7671eff538af1e4a97fc50cb469904.png) to ![ec=-2](./images/7122cb622b3ba83d2d60d17749495076c1cc4ae0.png). The equation ![ec+ca=0](./images/2b7afd8885a0ce9ce26510d6987c0c27c6e1012c.png) implies ![ca=2](./images/0e23e61949ad461c35a15c8c34e383ebc711d358.png). Finally, using ![ce+c^2=2](./images/8e0271b2d815f2894d137d42bd14f847232298f7.png) and ![ec=-2](./images/7122cb622b3ba83d2d60d17749495076c1cc4ae0.png), we find ![c=2](./images/add9738294ab73ea45e091cccb1c5d6aa2a30941.png). Therefore ![c=d=h=2](./images/afce8f227f2051b23b4c04913cf2da0b7a48664e.png), ![a=g=1](./images/6cb027ee169411ec889bf4af985c12c390e040bc.png), and ![e=b=f=-1](./images/4117011337c0232cab31d21ac3d1f13fb32ab531.png).

##[Chapter 4 solutions](./Front matter.md)

### Answers to exercises

**E4.1** ![d(\ell,O)=\frac{3\sqrt{2}}{2} \approx 2.121](./images/bc8942a60b35af75652f2604ed868350360fbd3d.png). **E4.2** ![d(\ell,O)=3](./images/33c9b173adec8cb7a6f7126521e3a0154d9efbf6.png). **E4.3** ![d(P,O)=5\sqrt{3} \approx 8.66](./images/a28de92a6aba897f37e5a9ef5f5f61cc95c3d39e.png). **E4.4** ![2x+y=5](./images/fbd6b784f1ef09fd96e4d4c4f8cad7666ef3dc21.png). **E4.5**

1.  ![\sqrt{10}](./images/cab18ad47b895d2406cd093549b6a5d7fc31b572.png);
2.  ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png);
3.  ![\frac{\sqrt{3}}{3}](./images/56c8a40ab099c8223b2eb8929e05c36b2f179c26.png);
4.  ![2\sqrt{3}](./images/7201d10649969c6bcdf08a90dac468cc19a24fd0.png);
5.  ![\sqrt{3}](./images/476ea09afd766595f1e572344507ef3ce56bbcdc.png);
6.  ![\frac{\sqrt{3}}{3}](./images/56c8a40ab099c8223b2eb8929e05c36b2f179c26.png).

**E4.6**

1.  ![(\frac{4}{3},\frac{4}{3},\frac{4}{3})](./images/ed66837dc8fc2144f7d341820d158eb777b3793d.png);
2.  ![(-\frac{1}{3},\frac{5}{3},-\frac{4}{3})](./images/4ec0706263a30f126da62cf9fc070edaa2c6a77f.png);
3.  ![(\frac{5}{3},-\frac{1}{3},-\frac{4}{3})](./images/4040594b5a1d9fcc5bc3cca18bbb8c4254aac4cd.png);
4.  ![(\frac{5}{3},\frac{5}{3},\frac{5}{3})](./images/63e24cbf8126881fd7a3f2cd05830144b510fce3.png);
5.  ![(-\frac{5}{3},-\frac{5}{3},\frac{10}{3})](./images/6a17b206cf440029eb07fa24ea9b7d42fdf35e86.png).

**E4.7**

1.  ![(\frac{2}{5}, \frac{26}{5},5)](./images/1ec0dc05d9b57a071874871702f8339ec974d77d.png);
2.  ![11.841](./images/043296eec9cd8eaae16776cd6aa4e60b52c6de73.png);
3.  ![(\frac{14}{5},\frac{32}{5},0)](./images/6834ef3ad076ac65160407e4f3dcf489de0fd286.png);
4.  ![12.837](./images/9dd8ec776f2fa95fc6e79145faebc83a1263d2d3.png);
5.  ![5.6745](./images/deda17136e5500dc30fa8687cd20c9a326fb1d36.png).

The point ![p](./images/b11f2617243b9603c98df21c26f4fc4d87ffa1fb.png) is closer to ![\ell_1](./images/2700171b346ab6b4bda6d406dd791123fee92c26.png) than to ![\ell_2](./images/d044fe34b7d41f4916ccf967c6bb2bc7e088c762.png). **E4.8** ![(\frac{30}{53},\frac{5}{53}, \frac{-20}{53})](./images/c3dfc9234157933a6df59441eea94f13a01a85c5.png). **E4.9** ![\vec{v}=(4,3,2)_{W}](./images/b92b239132b1776b1823f79c3869abab9e442880.png). **E4.10** ![\tensor[_{B_m}]{\left[\mathbbm{1}\right]}{_{B_s}}=\begin{bmatrix}
\frac{1}{2} & \frac{1}{2} & 0\\
\frac{1}{2} & - \frac{1}{2} & 0\\
0 & 0 & \frac{1}{2}\end{bmatrix}](../Images/40c2edf8d3d7e9a52b5d2b876cabab4b0634db48.png). **E4.11** There must be four vectors in the set and the vectors must be linearly independent. **E4.12**

1.  Yes;
2.  Yes;
3.  Yes;
4.  No;
5.  Yes.

**E4.13** ![\mathrm{rank}(A)=\dim(\mathcal{R}(A))=\dim(\mathcal{C}(A))=3](./images/359152d63bab1f3399f4d048ed59f69c92339b1e.png), ![\dim(\mathcal{N}(A))=1](./images/80cbeac50e27a81f9e68a62b868239424e0598d3.png), and ![\dim(\mathcal{N}(A^\sfT))=0](./images/b276743ba0f3f190951b2ca6b5dca488408ad752.png). ![\mathrm{rank}(B)=\dim(\mathcal{R}(B))=\dim(\mathcal{C}(B))=3](./images/c4770fe7b0c49491c472951ee25f0846427c5c95.png), ![\dim(\mathcal{N}(B))=2](./images/a4f52a49e8c1ff7190e126abed156a0c18bd5678.png), and ![\dim(\mathcal{N}(B^\sfT))=1](./images/1596ffcd5a008c1f472a55a1d3887f69df9e770e.png). ![\mathrm{rank}(C)=\dim(\mathcal{R}(C))=\dim(\mathcal{C}(C))=0](./images/b1d5155945f49c132bcf9e53ea1b885362af0e58.png), ![\dim(\mathcal{N}(C))=4](./images/c15b83b43e93eee900f5e42c5949a4f709f5f1ca.png), and ![\dim(\mathcal{N}(C^\sfT))=3](./images/0b76001099fd67e5d0750ea585c468cfaee2e733.png). **E4.14** ![\mathcal{R}(A) = \textrm{span}( (1,0,0,0)](./images/1cdf5b23b7e9053aec4db1ab0f9e852a655996c4.png), ![(0,1,-1,0) )](./images/061110b12342abcbcf1fe80e62f26952feee25d9.png), ![\mathcal{C}(A) = \textrm{span}( (1,0,0)^\sfT](./images/0d2663a78cf2cd3aad90b8efbf935957067d4d35.png), ![(0,1,0)^\sfT )](./images/b6ecd08476f90f6f7288e783c82443a47fad2324.png), and ![\mathcal{N}(A)=\textrm{span}( (0,1,1,0)^\sfT](./images/78bd2e060b5ec002df40cade42995c04934d4629.png), ![(0,0,0,1)^\sfT )](./images/913768a94fc1b215eae7ac107f2fdfa99703b231.png). **E4.15** Yes. **E4.16** ![\mathcal{N}(A) = \textrm{span}( (\tfrac{1}{2}, \, 1\,, \tfrac{1}{2}\,, 1) )](./images/0178991676aa7807311e619ed75868fd4c3437d0.png); ![\mathcal{N}(B) = \textrm{span}( (1,1,0), (2,0,1) )](./images/20f01fa19ab197d834421cf9e735fce986304ca9.png). **E4.17** ![\mathcal{R}(A) = \textrm{span}( (1,3,0,0)](./images/64f1b8c04e7417b440f97ecfd65cbc969769b2c7.png), ![(0,0,1,0)](./images/5fb19a62be9cb20330a2c2a0b5fd26f961d4196d.png), ![(0,0,0,1) )](./images/91b16e34c194c1e88c06486062bf9b852c8c857f.png), ![\mathcal{C}(A) = \textrm{span}( (1,2,3)^\sfT](./images/cdb4db7bb2a04bf4777133d3fb62c76ee0780f90.png), ![(3,7,9)^\sfT](./images/e5a3bd5555923ce354502a8a05f29f2420f11e5a.png), ![(3,6,10)^\sfT )](./images/1793bb0f9ad2e5fd5fa3e1fae17fd3a2bb329de0.png), and ![\mathcal{N}(A)=\textrm{span}( (-3,1,0,0)^\sfT )](./images/e8f9f949caa1aef69c52fc409c2985e987244c4f.png).

### Solutions to selected exercises

**E4.1** Using the formula from page 4.1.5.2, we find

![\begin{align*}
d(\ell,O)
&= 	\left\| (0,3) - \tfrac{  (0,3) \cdot (1,-1)  }{ 1^2 +(-1)^2 } (1,-1) \right\|	\\
&= 	\left\| (0,3) - \tfrac{  -3  }{ 2 } (1,-1) \right\|						\\
&=	\left\| \left( \tfrac{3}{2}, \tfrac{3}{2} \right) \right\|
= 	\tfrac{3\sqrt{2}}{2}.
\end{align*}](./images/a8e64c5cc9090c6c88f33070fb05772bfbccdcb3.png)

**E4.2** Using the formula from page 4.1.5.2, we find

![d(\ell,O)
=
\left\| (0,0,3) - \frac{  (0,0,3) \cdot (1,1,0)  }{ 1^2+1^2+0^2 } (1,1,0) \right\|
=
3.](./images/1260afa55b91a35017a241a5f65f372d1b69bfe5.png)

**E4.5**

1.  This is the norm of ![\|r\|](./images/8aa5377f59aaf4a1d9a840575487c7d632afcee8.png).
2.  To find a vector from the origin to the closest point on the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png), find a vector to any point on the line and subtract the part of the vector that is parallel to the line. The length of this perpendicular-only vector is the closest distance ![d(\ell,O)](./images/709deed432f37b4d3187c96585ebb71b8e8c1f33.png).
3.  Start with an arbitrary point in the plane, say ![p_P = (1,0,0)](./images/8adb1d2858a43e5caf5693b302292eddff2e0418.png). Then compute the length of the projection of ![p_P](./images/46694f649cb3ff11e5b9d4ecdf35582d88e3fedd.png) in the normal direction to obtain a vector to the point closest to the origin in the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png). The length of this vector is equal to ![d(P,O)](./images/a189345d7e48662c427c328fed0b93bca269291a.png).
4.  The procedure is analogous to part (b), but we’ll use a vector ![\vec{u} = (0,0,2) - (1,3,0)](./images/0ad6247caaa56a75d33706a3f2be0669f1c3f2cd.png), which starts at ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) and ends on a point on the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png). The part of the vector ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png) that is perpendicular to the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) is computed as ![\Pi_{\ell^\perp}(\vec{u}) = \vec{u} - \Pi_{\ell}(\vec{u})](./images/ca2e20ee8844a5c54ecc4012e14b9587d53b7011.png). The closest distance between ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) and ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) is the length of this vector, ![\|\Pi_{\ell^\perp}(\vec{u})\|](./images/17886d6fb24b81aa8fd440db583c033ca61af1af.png).
5.  The procedure is analogous to part (c), but we start with the vector ![\vec{v} = (1,0,0) - (1,3,0)](./images/e32ce0de273b62d63725850734383ba3675b1960.png), which starts at ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) and ends on a point in the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png). The closest distance between ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) and ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) is ![\|\Pi_{\vec{n}_P}(\vec{v})\|](./images/341ec269025d617d061f1593b7f02dc5b336e741.png).
6.  The line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) is parallel to the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png). Define a vector that starts at some point on the line and ends at some point in the plane ![\vec{w} = (1,0,0) - (0,0,2)](./images/fdb4efdd848300c44a9ef128185d076dcbf78e0f.png); then compute ![\|\Pi_{\vec{n}_P}(\vec{w})\|](./images/c3f5ae9c000ce7ccd0252f93454473b30aae5db1.png).

**E4.6** See[`bit.ly/projxrcis`](./projxrcis.md) for the solution using `SymPy`.

**E4.7** See [`bit.ly/dist_lines_exrcis`](./dist_lines_exrcis.md) for the solution.

**E4.8** The vectors ![(2,-4,2)](./images/60290c4bece1568c8256f743aae24266fba7b0c4.png) and ![(6,1,-4)](./images/edc6bc4910b165c30606922dd929c926c12217a8.png) define a plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png). We’re looking for the projection of ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) onto ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png). First, use the cross product to find a normal vector to the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png): ![\vec{n} = (2,-4,2) \times (6,1,-4) = (14,20,26)](./images/7339bef1b03b75ad6027534b694e3fd9daed7725.png). Then, compute the projection using the formula ![\Pi_P(\vec{v})=\vec{v}-\Pi_{\vec{n}}(\vec{v}) = (\frac{30}{53},\frac{5}{53}, \frac{-20}{53})](./images/911d7e2f54ccccf0de33994066883b531e179ae5.png).

**E4.10** Find the inverse change of basis matrix ![\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_m}} = \begin{bmatrix}1 & 1 & 0 \\ 1 & -1 & 0 \\ 0 & 0 & 2\end{bmatrix}](../Images/4fb281a2a909b264f1f6036b3e5c28f733d58863.png), whose columns are the vectors of the basis ![B_m](./images/7679bd26c003a3b533e2a9055349508293e38050.png). Then compute ![\tensor[_{B_m}]{\left[\mathbbm{1}\right]}{_{B_s}}
= \left(\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_m}}\right)^{-1}
=\frac{1}{2}\begin{bmatrix}1 & 1 & 0\\1 & -1 & 0\\0 & 0 & 1\end{bmatrix}](../Images/8c64d04b2eb739420defa46f93046d7a8c33a100.png).

**E4.12** All the given subsets are subspaces of ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png) except for **d)** because the plane ![2x+y+z=3](./images/744215c26e3d380ca4cd08b7806fbaa69ee6ce3b.png) does not contain the zero vector ![(0,0,0)](./images/b9ea26d6179acf575343bff96f0677c7583b7bd6.png).

**E4.15** The null space of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) and ![-A](./images/c65d02d1b34e019474545c3171b84928a31ad1c6.png) are identical since ![A\vec{v}=\vec{0}](./images/3da4e340c5aadfb7e0a53a44887c9db5e749c59e.png) if and only if ![-A\vec{v}=\vec{0}](./images/bcfc503d986815b933c2346c791acc51dec9a1e4.png). The same goes for the left null spaces. The column spaces are the same since any vector ![\vec{w} \in \mathcal{C}(A)](./images/9561f4df9b3cc7c196ffd56cafcf38d623a174c8.png) corresponds to some choice of coefficients ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) such that ![\vec{w}=A\vec{v}](./images/d7b01c0d33b812950ed483ca00defceda1ec399f.png), and since using ![-A](./images/c65d02d1b34e019474545c3171b84928a31ad1c6.png) and ![-\vec{v}](./images/77edd111096989f77b6743546ceb9de34f13b802.png) gives the same vector ![(-A)(-\vec{v})=\vec{w}](./images/56dd0d6e64e724b9eaf8d03d077e6daea061ea03.png). The same goes for the row spaces.

**E4.16** The null space of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) consists of all vectors ![\vec{x}=(x_1,x_2,x_3,x_4)^\sfT](./images/71b76e68a0715fadc311b0bba4fc966fd1584a65.png) that satisfy ![A\vec{x}=\vec{0}](./images/2364c48fe18dbfa6d867d8b3ba4b7c329d64a97e.png). To solve this equation we first compute the RREF of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png):

![\textrm{rref}(A) =
\begin{bmatrix}
1 & 0 & 0 & - \frac{1}{2}	\\
0 & 1 & 0 & -1			\\
0 & 0 & 1 & - \frac{1}{2}			
\end{bmatrix},](./images/8c1942096683eef663bd0089853d0acefe85afa2.png)

and observe it pivots in the first three columns, while ![x_4=s](./images/eb459f8d11833286dcc116021a4b3a80d6e5e924.png) is a free variable. The null space of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is

![\begin{bmatrix}
1 & 0 & 0 & - \frac{1}{2}	\\
0 & 1 & 0 & -1			\\
0 & 0 & 1 & - \frac{1}{2}			
\end{bmatrix}
\!\!
\left[\begin{array}{c}x_1\\x_2\\x_3\\s \end{array}\right]
=
\left[\begin{array}{c}0\\0\\0 \end{array}\right]
\qquad
\Rightarrow
\qquad
\begin{array}{rcl}
1x_1  - \frac{1}{2}s	&=&0 \\
1x_2  - s			&=&0 \\
x_3 - \frac{1}{2}s  	&=&0
\end{array}](../Images/e4b94af70c33cd8f86b97f1923030e0b9685487f.png)

The null space is ![\mathcal{N}(A) = \textrm{span}( (\tfrac{1}{2}, \, 1\,, \tfrac{1}{2}\,, 1) )](./images/0178991676aa7807311e619ed75868fd4c3437d0.png).

### Answers to problems

**P4.1** **a)** ![(1,2)](./images/ff0ebe362ea8060ceecb21ab65cba42156a1fb54.png). **b)** Lines overlap so every point on the lines is an intersection point. **c)** ![(1,1)](./images/2ea5ec79a8e31eeca324b4dd0e638f58cc29173d.png). **P4.2** **a)** ![\{ (1,-\frac{1}{2},0) + s(0,-\frac{1}{2},1), \forall s \in \mathbb{R}\}](./images/93634568a82089aa0b99dde58c0e884257d6c54b.png); **b)** ![\{ (-1,2,0) + t(1,-1,1), \forall t \in \mathbb{R}\}](./images/2bb338f021367de7d47cfde95e4c87907e748291.png). **P4.3** **a)** parallel; **b)** neither; **c)** perpendicular. **P4.4** ![d(r,P)=1](./images/113ee4268954fd586e524cba509fb2bbe91d6e3e.png). **P4.5** ![d(p,Q)=\frac{2}{3}](./images/806f2b2bdcd37c5d68b0da6a70188065cf329541.png). **P4.6** **a)** ![d(p,q)=7](./images/975ef07e14f99dd14a58f2d0dcba9caaf760b582.png); **b)** ![d(m,n)=5](./images/0dc9ac78cf5f4403ed834d00ab8a00521fe5879b.png); **c)** ![d(r,s)=3](./images/f75baede0ad898c68caa10a74f761b67e5a91f91.png); **d)** ![d(i,j)=\sqrt{19}](./images/11f19996a4403cba34c6a4bfe2cab6a0bfb99a91.png). **P4.7** ![x+y+2z=4](./images/44685cae8065aa85f0dc3c760be6d038204fa95c.png). **P4.8** ![\ell: \left\{\frac{x+3}{2}=\frac{y-1}{-4}=\frac{z}{-1}\right\}](./images/016f12de4105587f09ecd7340ba06df0dbbe93c0.png). **P4.9** ![2x -11y - 7z =2](./images/96a3b41edfe82a9790507c3351bf2337360b30b9.png). **P4.10** ![\Pi_{\vec{u}}(\vec{v})
=\frac{\vec{v}\cdot\vec{u}}{\|\vec{u}\|^2}\vec{u}
=\frac{(1,1,1)\cdot(2,1,-1)}{2^2+1^2+(-1)^2}(2,1,-1)
=\frac{1}{3}(2,1,-1)](./images/f7c2badafb26df16618c6616e79afeab77c59676.png); ![\Pi_{\vec{v}}(\vec{u})
=\frac{\vec{v}\cdot\vec{u}}{\|\vec{v}\|^2}\vec{v}
=\frac{(1,1,1)\cdot(2,1,-1)}{1^2+1^2+1^2}(1,1,1)
=\frac{2}{3}(1,1,1)](./images/802fe3c630ffdd386f000fabd9b1f706f6527d59.png). **P4.11** ![\Pi_P(\vec{v})=\frac{1}{7}(17,30,-1)](./images/fe8aadd68ee96b1d9e8235856b612bcc58905d47.png). **P4.12** ![\Pi_{P^{\perp}\!}(\vec{u})=(-\frac{6}{25},0,-\frac{8}{25})](./images/8851f5e25bb2f32d2077d1087e15958301fb3693.png). **P4.13** ![d(\ell, P)=\frac{7}{3}](./images/cc46c22f2a5b1ffa555557d0f4c229adf8e95612.png). **P4.14** ![\vec{v}=(2,1,3)_{W}](./images/eaf736fea9d793941c61be13dc7d9af1d95084aa.png). **P4.15** ![\tensor[_{V}]{\left[\mathbbm{1}\right]}{_{U}}
=\begin{bmatrix}
-1 & 2 & 0\\
1 & -1 & 1\\
1 & -1 & -1
\end{bmatrix}](../Images/23d670ffb6428f41dc69f5f357e71cbf068ab7bb.png). **P4.17**

1.  Yes;
2.  No;
3.  Yes;
4.  No;
5.  No.

**P4.18**

1.  ![A=\begin{bmatrix}1 & 2 & 3 \\ 2 & 4 & 6\end{bmatrix}](./images/f8b401b3ecffe777e3c7c067ba5ecc59fa352b27.png);
2.  ![B=\begin{bmatrix}1 & -1 & 0 \\ 1 & 0 & -1\end{bmatrix}](./images/112c18ee25377b9b92957a94e056b0d7561b8b56.png);
3.  ![C=\begin{bmatrix}3 & 6 & 9 \\ -1 & -2 & -3\end{bmatrix}](./images/5d30a72f577c180f332a1dd3e51cd04f6caf7462.png).

Other answers are possible. **P4.19** ![d=\frac{bc}{a}](./images/da8151c865049d07ff3649ce6a1eb08f3c9a5011.png). **P4.20**

1.  The ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-axis;
2.  The ![xy](./images/e819445128c475992b46e256b3c37c0307f3d821.png)\-plane;
3.  The ![xy](./images/e819445128c475992b46e256b3c37c0307f3d821.png)\-plane;
4.  All of ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png);
5.  The ![yz](./images/020ce2f2825bf4a1a52bec7954f769ecd008a4f4.png)\-plane.

**P4.22** No, but you can conclude that ![\dim V \leq m](./images/2a1064a43e2b885f2352ad617f9a751e2e9e52c1.png). **P4.29** ![\vec{v}_3=(0,1,0)](./images/20b9e0ba04dc7c455102c9eabe1c0bae02e39f25.png), ![\vec{v}_3^\prime=(2,4,7)](./images/342f93ce9594a87ba78b3d3d24815ef1cc75e8ef.png). **P4.30** ![\vec{v}_4=(5,2,-3,1)](./images/b0b5c23cbc81630ea8b5b59b24d597027e5d7510.png).

### Solutions to selected problems

**P4.1** To find the intersection point, solve the two equations simultaneously.

**P4.3** We can solve this problem by comparing the plane normals. **a)** The normals to the planes are ![\vec{n}_1=(1,-1,-1)](./images/0b2f60ca1b508a7b4d3037cb6d58238de074e006.png) and ![\vec{n}_2=(2,-2,-2)=2\vec{n}_1](./images/4df03ea14b66ba1d14f4328396c44fe63291498c.png). The normals are multiples of each other so the planes are parallel. **b)** ![\vec{n}_1=(3,2,0)](./images/bddf570caeaf7f05fde380d29100e45ff4ccb5b0.png), ![\vec{n}_2=(0,1,-1)](./images/796ed70c5c1c9a61fffd24306ac36aa52f2cda6a.png), and ![\vec{n}_1\cdot \vec{n}_2=2 \neq 0](./images/4c9f8586a26e7f31265a03912b471de949aac973.png). The planes are neither parallel nor perpendicular. **c)** ![\vec{n}_1=(1,-2,1)](./images/bc4014cb2cb69c306e7b24bc94bf654c97275782.png), ![\vec{n}_2=(1,1,1)](./images/71814ddf039f1578392b50bec8d958ee5cd7bcf4.png), and ![\vec{n}_1\cdot \vec{n}_2=0](./images/8d259c344b45b70ed40c4deb494119a1682e7a99.png); therefore the planes are perpendicular.

**P4.4** Use the formula ![d(r,P)=\frac{| \vec{n} \cdot r  |}{ \| \vec{n} \| }=\frac{|2(2)+1(3)-2(5)|}{ \sqrt{2^2+1^2+(-2)^2}}=\frac{3}{3}=1](./images/3a0f2b745edd4be34c06475ee175d0b9cb99495a.png).

**P4.5** Construct the vector ![\vec{v} = p - q =  (5,3,5) - (0,1,0)=(5,2,5)](./images/017020048879330fee198c90656129bbf88187dd.png), which starts at ![q](./images/8352363828e0228195580ba48c9cde386d9f6849.png) (an arbitrary point in the plane ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png)) and ends at the point ![p](./images/b11f2617243b9603c98df21c26f4fc4d87ffa1fb.png). The shortest distance between the point ![p](./images/b11f2617243b9603c98df21c26f4fc4d87ffa1fb.png) and the plane ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png) is equal to the length of the projection of the vector ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) in the direction of the plane’s normal vector ![\vec{n}](./images/7da6b307d5458666fc055f8a1f35f4dc2c7b11d7.png), which is given by the formula ![\|\Pi_{\vec{n}}(\vec{v})\|](./images/40f0140a5d1ce0542c3ec4496425d78a805eb527.png). We find ![d(p,Q)=\big\| \frac{\vec{v} \cdot \vec{n}}{ \| \vec{n} \|^2 }\vec{n} \big\|
= \big\| \frac{10 + 2 - 10}{ 2^2+1^2+(-2)^2}(2,1,-2) \big\|
= \big\|\frac{2}{9}(2,1,-2)\big\|=\frac{2}{3}](./images/f39abac5e4bfe6314854031e3d466bce56dc015d.png).

**P4.7** First we find two vectors in the plane; for example ![\vec{u} = r-q = (-1,-1,1)](./images/5f8cf460eb99a864545b98053e40b473c245ac3d.png) and ![\vec{v} = s-q = (0,-2,1)](./images/a3249bbb4d83c27bbe80fb6b7af657fac32c2abc.png). Then we must find the normal vector ![\vec{n}](./images/7da6b307d5458666fc055f8a1f35f4dc2c7b11d7.png), ![\vec{n}=\vec{u} \times \vec{v}=(-1,-1,1)\times(0,-2,1)=(1,1,2)](./images/d0dd18cc8a1144f89653a2f1afe5edf3c3d38da1.png). We can use any of the three points as the point ![p_o](./images/99626cfb842666284982d8053417782f3f4c5dfe.png) in the geometric equation of the plane ![\vec{n} \cdot[ (x,y,z) - p_o]=0](../Images/b4a8b9ec671b128a176068174d9447b89fb080c4.png). Using ![q=(1,3,0)](./images/f323b2ad2d03c463efdb1be8174a0cb5a8e4af2e.png), we obtain the equation ![(1,1,2) \cdot[ (x,y,z) - (1,3,0) ]=1(x-1)+1(y-3)+2z=0](../Images/df4ba8fd6d533570dd5647089d90a63737df15e6.png). Computing the expression gives ![x-1+y-3+2z=0](./images/1653bdef7d8ddc39a10b3ae9a96073660b2c777d.png), which simplifies to ![x+y+2z=4](./images/44685cae8065aa85f0dc3c760be6d038204fa95c.png).

**P4.9** We use the Gauss–Jordan elimination procedure to find the intersection of the two planes. The line of intersection is ![\ell_1: \{ (1,0,0) + (1,-3,5)t \,|\, \forall t \in \mathbb{R} \}](./images/40aec4ba9c70811321e320e097066068c6a82dd3.png), where ![(1,0,0)](./images/593ea2bff8593eab66c6e688b53cf5ebe7274cd4.png) is a point on the line of intersection and ![\vec{v}_1=(1,-3,5)](./images/d46f956864f56fbc4970062c9aed8eb239099d00.png) is its direction vector. The direction vector of ![\ell_2](./images/d044fe34b7d41f4916ccf967c6bb2bc7e088c762.png) is ![\vec{v}_2 = (2,1,-1)](./images/3c28e1320c12b86bfe38edbc1b57bf2ad7739f8b.png). We want to find the equation of a plane ![\vec{n}\cdot[ (x,y,z) - p_{\textrm{o}} ]=0](../Images/37ddf2ae88d480bcfb05cc84dddec7adcb102412.png) that has a normal perpendicular to both ![\vec{v}_1=(1,-3,5)](./images/d46f956864f56fbc4970062c9aed8eb239099d00.png) and ![\vec{v}_2=(2,1,-1)](./images/3c28e1320c12b86bfe38edbc1b57bf2ad7739f8b.png). Using ![\vec{n} = \vec{v}_1 \times \vec{v}_2=(-2, 11, 7)](./images/99da9c7bb6e44e1ec74f614183f2215f959cb593.png), and choosing the point ![p_{\textrm{o}}=(1,0,0)](./images/ef96ef3c3c2c4f1bdec76e73861a248554b0d2bd.png) from the line ![\ell_1](./images/2700171b346ab6b4bda6d406dd791123fee92c26.png), we obtain ![(-2, 11, 7)\cdot[ (x,y,z) - (1,0,0) ]=0](../Images/711b90b5ac140eca34bb511297669c2bc23af23b.png).

**P4.11** Let’s first find ![\Pi_{P^{\perp}}(\vec{v})
=\frac{\vec{v}\cdot\vec{n}}{\|\vec{n}\|^2}\vec{n}
=\frac{(3,4,1)\cdot(2,-1,4)}{2^2+(-1)^2+4^2}(2,-1,4)
=\frac{2}{7}(2,-1,4)](./images/627522d6da10fde83395156b90a23db8326c8d72.png). Then ![\Pi_P(\vec{v})=\vec{v}-\Pi_{P^{\perp}}(\vec{v})=(3,4,1)-\frac{2}{7}(2,-1,4)=\frac{1}{7}(17,30,-1)](./images/10fdd2e75686002eb8e045307455e3618f0e9e8f.png). We can verify ![\Pi_P(\vec{v})+\Pi_{P^{\perp}}(\vec{v})=\frac{1}{7}(17,30,-1)+\frac{2}{7}(2,-1,4)=(3,4,1)=\vec{v}](./images/514aaab6cbf59b02d01ad7d9a8204a4ace7f47a9.png). This shows that the projection we found is correct.

**P4.12** First we find the normal ![\vec{n}](./images/7da6b307d5458666fc055f8a1f35f4dc2c7b11d7.png) of the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) using the cross-product trick, ![\vec{n}=(s-m) \times (r-m)](./images/27e727e5fd6d18b82e0be7b09f84a4910c238a19.png). Since ![s-m=(4,0,-3)](./images/ba1037b861c40eecc7a5414115cc1e912c3b4f7e.png) and ![r-m=(4,1,-3)](./images/1ee46efb99e07f3afd634fa2a274abf070dfbf43.png), we find ![\vec{n}=(4,0,-3)\times(4,1,-3)=(3,0,4)](./images/965ed9a1363cb5577f4aba3bbe6628d1a3e81684.png). Now we want to find the projection of ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png) onto the space perpendicular to ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png), which is given by the formula ![\Pi_{P^{\perp}}(\vec{u})
=\frac{\vec{v}\cdot\vec{n}}{\|\vec{n}\|^2}\vec{n}
=\frac{(-2,1,1)\cdot(3,0,4)}{3^2+4^2}(3,0,4)
=\frac{-2}{25}(3,0,4)
=(-\frac{6}{25},0,-\frac{8}{25})](./images/ef241a7bf0e1dcbc93e978fbc4d982470eb674e3.png).

**P4.13** We’ll compute the distance by first finding a vector ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) that connects an arbitrary point in the plane ![P](./images/67ca4b3231b6b7a7b8043e709f968f1b99fbbc4e.png) with an arbitrary point on the line ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png), and then computing the component of ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) that is perpendicular to the plane. The point that lies on the line is ![p_\ell=(1,-3,2)](./images/8a219ecf6bcc4a7852558c4526266ad253715d19.png), and the point in the plane is ![p_P=(0,1,1)](./images/0c374042dba6f22e1bdd589d03d737116424180c.png). The vector between them is ![\vec{v}=p_P - p_\ell =(1,-4,1)](./images/99afc7a87c6cba5c7471b6696fcfc1e9959687d6.png). To compute ![d(\ell, P)](./images/23abb28217d4177f2a30cff23d1ab689d54b7b32.png) we must find the length of the projection of ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) in the direction of ![\vec{n}](./images/7da6b307d5458666fc055f8a1f35f4dc2c7b11d7.png): ![d(\ell, P)=\big\| \frac{\vec{v} \cdot \vec{n}}{ \| \vec{n} \|^2 }\vec{n} \big\|
=\frac{|\vec{n}\cdot \vec{v}|}{\|\vec{n}\|}
=\frac{(1,-4,1)\cdot(-1,2,2)}{\sqrt{(-1)^2+2^2+2^2}}=\frac{7}{3}](./images/1e2c875d8100e9fc4bd00eb9c9811acdfd811a82.png).

**P4.15** First we find the change-of-basis transformations to the standard basis ![\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{U}} = \begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 1\\
0 & 1 & -1
\end{bmatrix}](../Images/a8505264ccaf39174e784b3aa50b95305034f342.png) and ![\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{V}} = \begin{bmatrix}
1 & 1 & 1\\
1 & 1 & 0\\
1 & 0 & 1
\end{bmatrix}](../Images/00d93dd71879f66fdd9c051023388c849cf8b7d5.png). Next we compute ![\tensor[_{V}]{\left[\mathbbm{1}\right]}{_{B_s}}
=\big(\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{V}}\big)^{-1}
=\begin{bmatrix}
-1 & 1 & 1\\
1 & 0 & -1\\
1 & -1 & 0
\end{bmatrix}](../Images/e7f253a6c4e39f25943f7e5e3b1a5b3f4bb7531e.png). Finally, we compute ![\tensor[_{V}]{\left[\mathbbm{1}\right]}{_{U}}
= \tensor[_{V}]{\left[\mathbbm{1}\right]}{_{B_s}} \tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{U}}](../Images/fca7434211259cff99ee298f327a2220473b5641.png).

**P4.16** We can check that the sum of two upper triangular matrices results in an upper triangular matrix. Scaling an upper triangular matrix also preserves its nature. The zero matrix is upper triangular. Since all three subspace conditions are satisfied, the upper triangular matrices form a subspace.

**P4.17** In each case, we must either recognize the set as being a subspace or explain which of the three subset conditions fails.

1.   ![W_1](./images/053ca6352d4185c887a84f1f12995cb3c1bf2648.png) corresponds to the plane ![x + y = 0](./images/d5634a72ab87aa7f3b104fab78b5d5812f53264b.png) which is a subspace of ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png).
2.  Consider the vectors ![(0,1,0) \in W_2](./images/d8351bd89412abb2da602db489f6f85ba8b148bb.png) and ![(0,0,1) \in W_2](./images/84cd135e0d85a95fa0f029fdffe5e2da23ab5fc8.png). The sum ![(0,1,0) + (0,0,1) = (0,1,1) \notin W_2](./images/adafbf4f9bd1c2afcc9a0a19d0aa5109007f0804.png), so ![W_2](./images/88de53ad3126ed77c9fbb1785caf047c77abefc8.png) is not closed under addition.
3.   ![W_3](./images/704ac88c14b5b7788ffd73d5d15d5007f1c411c2.png) is equivalent to the line ![\{ (0,0,0) + t(1,1,1), \forall t \in \mathbb{R} \}](./images/b3701b14502087aa9ce715732e373a0b45611885.png), which is a subspace of ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png).
4.  Consider the vector ![(1,0,0) \in W_4](./images/7cfa9d8cf1b6fc4d208da77d57de572ee4cc5381.png). Multiplying this vector by ![-3](./images/90c76b79a3ab345cb1b4c158ecd5457a570bc393.png) results in ![(-3,0,0) \notin W_4](./images/34b793aeb15e4e068cd9036149ffcef3e9bc4bd1.png), so the set ![W_4](./images/2e6b9529457506cb077f4955dd2943d07810db84.png) is not closed under scalar multiplication.
5.  The set ![W_5](./images/f736f107c98620fe77c98a1a25098d215d38f389.png) does not contain the zero element ![(0,0,0)](./images/b9ea26d6179acf575343bff96f0677c7583b7bd6.png).

**P4.19** Imagine performing the first step in the Gauss–Jordan elimination procedure. Subtracting ![\frac{c}{a}](./images/4532d01c2b8521a228eaa50d9cae27aebe6f3aef.png) times the first row from the second row results in ![\begin{bmatrix}a & b \\ 0 & \; d-\frac{c}{a}b \end{bmatrix}](./images/b79464046a573739fea8a490a97185781568d049.png). If ![d=\frac{bc}{a}](./images/da8151c865049d07ff3649ce6a1eb08f3c9a5011.png), the matrix will have rank one.

**P4.21** Define ![W = \textrm{span}(\vec{v}_1, \vec{v}_2-\vec{v}_1, \vec{v}_3-\vec{v}_2, \vec{v}_4-\vec{v}_3)](./images/be7c7376c2d5808adfa7a318ef0ccb11a1a88cc3.png). Every vector ![\vec{w} \in W](./images/5d599cdfde3efa0f028f483572a70206d5a15c3c.png) can be written in the following two equivalent ways:

![\begin{align*}
\vec{w} 	&= \alpha_1 \vec{v}_1
+ \alpha_2(\vec{v}_2-\vec{v}_1)
+ \alpha_3(\vec{v}_3-\vec{v}_2)
+ \alpha_4(\vec{v}_4-\vec{v}_3)		\\
& = (\alpha_1-\alpha_2) \vec{v}_1
+ \alpha_2\vec{v}_2
+ \alpha_3(\vec{v}_3-\vec{v}_2)
+ \alpha_4(\vec{v}_4-\vec{v}_3)	.
\end{align*}](./images/9d51fc0d366aaf431b103378aabe234802d4f176.png)

This implies ![W =  \textrm{span}(\vec{v}_1, \vec{v}_2, \vec{v}_3-\vec{v}_2, \vec{v}_4-\vec{v}_3)](./images/35ee96aa4c5084f3f9cbf1702587074dca990029.png). Using this approach we can show ![W =  \textrm{span}(\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4-\vec{v}_3)](./images/d5596b469e023824276f9dcbacfdd8cfce5161b1.png), and then ![W =  \textrm{span}(\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4) = V](./images/f35e2ffe64e500bb31c3494970f19f61d82d8fdf.png).

**P4.22** Recall that the dimension of a vector space is equal to the number of vectors in a basis for the vector space. For a set of vectors to be a basis, the vectors must span the space _and_ be linearly independent. Since the problem does not specify whether the set of vectors are linearly independent, we cannot conclude that ![\dim V = m](./images/db9dfc3f80d5abb5371f1ae2d0ad6daf40f4e418.png).

**P4.23** Define ![W = \textrm{span}(\vec{w}_1, \vec{w}_2)](./images/420d7403374b3616c27cd288bc44c2a11b981f41.png), which means any vector ![\vec{w} \in W](./images/5d599cdfde3efa0f028f483572a70206d5a15c3c.png) can be written in the form ![\vec{w} = \alpha_1 \vec{w}_1 + \alpha_2 \vec{w}_2](./images/5a646bebb500cb4f34cae74d182ced37b2ca431a.png). To show ![W](./images/cf83ddf97823b88ae25eb70438f249f159f02fbf.png) is a subspace, we must show it is closed under addition and scalar multiplication, and that it contains the zero element. Consider two arbitrary vectors chosen from ![W](./images/cf83ddf97823b88ae25eb70438f249f159f02fbf.png), ![\vec{w}_a = \alpha_1 \vec{w}_1 + \alpha_2 \vec{w}_2](./images/0068de99818bbad9c3704ba38380636cceafb117.png) and ![\vec{w}_b = \beta_1 \vec{w}_1 + \beta_2 \vec{w}_2](./images/eec461e1998d8e89064fd1286c8eaceac65f8f7d.png). The sum of these two vectors is ![\vec{w}_a  + \vec{w}_b = (\alpha_1+\beta_1) \vec{w}_1 + (\alpha_2+\beta_2) \vec{w}_2](./images/f80dd29e69527bf72a57eabe470d25c0b3e1c856.png), which is also a vector in ![W](./images/cf83ddf97823b88ae25eb70438f249f159f02fbf.png). Similarly, scaling ![\vec{w}_a](./images/21e66479d15eb2459d76b8b9568c31b7c3e2bb79.png) by a constant produces a vector in ![W](./images/cf83ddf97823b88ae25eb70438f249f159f02fbf.png), and choosing the coefficients ![\alpha_1=\alpha_2=0](./images/02ce9676b10ec32855365ac1137881f7ecf534f3.png) gives the zero vector. Therefore ![W \subseteq V](./images/adcb4996061ecd9b9d85f92dc73bf2ce7b2d6687.png).

**P4.24** We are told the set ![S = \{\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/096cfbfce53afd267b69d7547925ca930ffadfe7.png) is linearly independent, which implies ![\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \cdots + \alpha_n\vec{v}_n \; = \; \vec{0}](./images/f0214557e4ed8ddb6a1da1efdab10811d43c9f37.png) has only trivial solution ![(\alpha_1,\alpha_2,\alpha_3,\alpha_4)=(0,0,0,0)](./images/0e3fdd1e93bdc562d4e1a09a20218aece4b748f4.png). Define the set ![S^\prime = \{\vec{v}_1, \vec{v}_2-\vec{v}_1, \vec{v}_3-\vec{v}_2, \vec{v}_4-\vec{v}_3\}](./images/829a603465c7c6535d43fac320b7cf69a30f9d35.png). To find whether ![S^\prime](./images/c830bcf468da1129b3bf83177f89d049d989f301.png) is a linearly independent set, consider the following equation:

![\beta_1 \vec{v}_1
+ \beta_2(\vec{v}_2-\vec{v}_1)
+ \beta_3(\vec{v}_3-\vec{v}_2)
+ \beta_4(\vec{v}_4-\vec{v}_3)
= 0.](./images/dd18d8db0dff10456c997cab58d787ac90c8608d.png)

Rearranging the terms, we obtain the equivalent expression

![\underbrace{(\beta_1 - \beta_2 - \beta_3 - \beta_4)}_{\alpha_1}\vec{v}_1
+ \underbrace{(\beta_2 - \beta_3)}_{\alpha_2} \vec{v}_2
+ \underbrace{(\beta_3 - \beta_4)}_{\alpha_3} \vec{v}_3
+ \underbrace{\beta_4}_{\alpha_4} \vec{v}_4
= 0.](./images/9cd11ca88f095c72ff6dd35e6f959fb10ea1fd6e.png)

We recognize this form of equation from the definition of linear independence. Since we’re told ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/09e5ed76d3621c6d585d8c4b3b884ae4c93434fc.png) is a linearly independent set, we know the only solution to the above equation is ![(\alpha_1,\alpha_2,\alpha_3,\alpha_4)=(0,0,0,0)](./images/0e3fdd1e93bdc562d4e1a09a20218aece4b748f4.png), or

![0 = \beta_1 - \beta_2 - \beta_3 - \beta_4, \; \;
0 = \beta_2 - \beta_3 - \beta_4, \; \;
0 = \beta_3 - \beta_4, \; \;
0 = \beta_4.](./images/5282b92a2b805b590c6aed34711e7dce789fa4a3.png)

Solving for the unknowns in the order ![\beta_4](./images/c567f7bb43f3c3ad3a37636d9e096d85c8334502.png), ![\beta_3](./images/c00fd84cebcc8655cb81c92b5587aa42d5f58023.png), ![\beta_2](./images/1c0631b7135e632aefdb52465ff0b18bbda07963.png), ![\beta_1](./images/0298e7c9f09ccd88a9179a7ee8b16c5840e1647a.png), we find the only solution is ![(\beta_1,\beta_2,\beta_3,\beta_4)=(0,0,0,0)](./images/04fcf3a039a54f1bb8ccaa92f9e93f250e095074.png); therefore, ![\{\vec{v}_1, \vec{v}_2-\vec{v}_1, \vec{v}_3-\vec{v}_2, \vec{v}_4-\vec{v}_3\}](./images/98fff543039ecf6fbcba59397a9a2399fc321a82.png) is a linearly independent set.

**P4.25** We’ll use a proof by contradiction. If ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3\}](./images/3ab621063eeab3da100e803cd5b1524a970e87eb.png) is not a linearly independent set then there must be some ![(\beta_1, \beta_2, \beta_3) \neq (0,0,0)](./images/21c19493351da044dc73064a3afcea3e5a8e73da.png) such that ![\beta_1\vec{v}_1 + \beta_2\vec{v}_2 + \beta_3\vec{v}_3 = 0](./images/e965d6dc219e710661ab2318d9fb65abe12f68ff.png). If this is true, then the equation ![\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \alpha_3\vec{v}_3 + \alpha_4\vec{v}_4 = 0](./images/af317c97f0be32d621b778f0c2df216aca67646a.png) will have a non-trivial solution ![(\alpha_1, \alpha_2, \alpha_3, \alpha_4) \neq (0,0,0,0)](./images/96433e151029099e3b399dc8a384fa9a055f6556.png): ![\alpha_1 = \beta_1](./images/06bbcf322d95c69c4018fb425933402d99569d52.png), ![\alpha_2 = \beta_2](./images/d0cf1543da7951e830d31abc498382ae92dda9d1.png), ![\alpha_3 = \beta_3](./images/2e2c26e2d4d808b3b1741c3b41f0f2edce75701f.png), and ![\alpha_4 = 0](./images/e9493f3d62094456bd738d79f9e71f6d8811ad38.png). However, this contradicts the fact that ![\{ \vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/09e5ed76d3621c6d585d8c4b3b884ae4c93434fc.png) is a linearly independent set. Since we’ve arrived at a contradiction, it must be true that ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3\}](./images/3ab621063eeab3da100e803cd5b1524a970e87eb.png) is a linearly independent set.

**P4.26** We know ![\vec{v}_1](./images/d33646fb26ad9d3975a25ad3c85c11f594226bce.png), ![\vec{v}_2](./images/65b10c95bdff2bcc3058df8e5d95333772f5523c.png), ![\vec{v}_3](./images/6fb023e89213b68ba9ff281a50c3bf2d42b8e701.png) are linearly independent, and ![\vec{v}_4 \notin \textrm{span}(\vec{v}_1, \vec{v}_2, \vec{v}_3)](./images/2e95a35edc4751501f35495b9f6859c67035a4d9.png). To set up the proof by contradiction, assume ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/09e5ed76d3621c6d585d8c4b3b884ae4c93434fc.png) is a linearly dependent set. This implies the equation ![\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \alpha_3\vec{v}_3 + \alpha_4\vec{v}_4 = 0](./images/af317c97f0be32d621b778f0c2df216aca67646a.png) has a nontrivial solution: ![(\alpha_1, \alpha_2, \alpha_3, \alpha_4) \neq (0,0,0,0)](./images/96433e151029099e3b399dc8a384fa9a055f6556.png). We’ll analyze the case ![\alpha_4=0](./images/e9493f3d62094456bd738d79f9e71f6d8811ad38.png) separately from the case ![\alpha_4\neq0](./images/d2a016433d94f7ff74952e9a312eda26369e19db.png). In the case ![\alpha_4 = 0](./images/e9493f3d62094456bd738d79f9e71f6d8811ad38.png), at least one of the coefficients ![\alpha_1](./images/16381899d902084ae5c1157682c413dfcb4b4c4a.png), ![\alpha_2](./images/1993456dfea15bd780d137a3df5fc9a324186764.png), ![\alpha_3](./images/ab073f01d278eea0dcf443202306336b30c4a01e.png) must be nonzero, which means ![\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \alpha_3\vec{v}_3 = 0](./images/c7a5c983aad2177d37ce7524a73d689b00a94e31.png) has a non-trivial solution; but this is a contradiction since ![\vec{v}_1](./images/d33646fb26ad9d3975a25ad3c85c11f594226bce.png), ![\vec{v}_2](./images/65b10c95bdff2bcc3058df8e5d95333772f5523c.png), ![\vec{v}_3](./images/6fb023e89213b68ba9ff281a50c3bf2d42b8e701.png) are linearly independent. In the case of ![\alpha_4 \neq 0](./images/d2a016433d94f7ff74952e9a312eda26369e19db.png), we can rewrite the equation as follows:

![\alpha_1\vec{v}_1 + \alpha_2\vec{v}_2 + \alpha_3\vec{v}_3 + \alpha_4\vec{v}_4 = 0
\quad
\Rightarrow
\quad
\vec{v}_4 = \tfrac{-\alpha_1}{\alpha_4}\vec{v}_1
+ \tfrac{-\alpha_2}{\alpha_4}\vec{v}_2
+ \tfrac{-\alpha_3}{\alpha_4}\vec{v}_3,](./images/59c5c49f4e6acd2219922891cc7038d226fc20e2.png)

which shows that ![\vec{v}_4 \in \textrm{span}(\vec{v}_1, \vec{v}_2, \vec{v}_3)](./images/716ad81439f205c86b50e85419b2505b9112667b.png) and contradicts ![\vec{v}_4 \notin \textrm{span}(\vec{v}_1, \vec{v}_2, \vec{v}_3)](./images/2e95a35edc4751501f35495b9f6859c67035a4d9.png). Since we’ve arrived at a contradiction in both cases, we conclude that ![\{\vec{v}_1, \vec{v}_2, \vec{v}_3, \vec{v}_4\}](./images/09e5ed76d3621c6d585d8c4b3b884ae4c93434fc.png) must be a linearly independent set.

**P4.27** To check whether ![\{\vec{v}_3,\vec{v}_2 +\vec{v}_3,\vec{v}_1 +\vec{v}_2 +\vec{v}_3\}](./images/813cfae71a48543417782484a31dbd458de25ade.png) is a linearly independent set, we must consider the solutions to the equation ![c_1\vec{v}_3 + c_2(\vec{v}_2 +\vec{v}_3) + c_3(\vec{v}_1 +\vec{v}_2 +\vec{v}_3) = 0](./images/28d30f532440125f98a3170ae46e5431fbca813f.png). We can rewrite this equation as follows:

![\begin{align*}
0 	&= c_1\vec{v}_3 + c_2(\vec{v}_2 +\vec{v}_3) + c_3(\vec{v}_1 +\vec{v}_2 +\vec{v}_3) 			\\
&= \underbrace{c_3}_{\alpha_1} \vec{v}_1
+ \underbrace{(c_2 + c_3)}_{\alpha_2} \vec{v}_2
+ \underbrace{(c_1 + c_2 + c_3)}_{\alpha_3} \vec{v}_3.
\end{align*}](./images/a6453583d6578758a03e600ca5e110579ba09906.png)

This latter equation has the same form as the definition of linear independence; and since ![\{\vec{v}_1,\vec{v}_2,\vec{v}_3\}](./images/3ab621063eeab3da100e803cd5b1524a970e87eb.png) is a linearly dependent set, we know the only solution to this equation is ![(\alpha_1, \alpha_2, \alpha_3) = (0,0,0)](./images/de28915fa6d89abbdf48fe44231384c652d5d172.png), which implies

![c_3 =  0, \quad
c_2 + c_3 =  0, \quad
\textrm{and} \quad
c_1 + c_2 + c_3 =  0.](./images/4894e150dede765bd2e71c002e03b9f21b170bc7.png)

Solving these equations, we obtain the trivial solution ![(c_1, c_2, c_3) = (0,0,0)](./images/090b780efe431f96f741107e0e278d1edf7cc929.png) and conclude that the set ![\{\vec{v}_3,\vec{v}_2 +\vec{v}_3,\vec{v}_1 +\vec{v}_2 +\vec{v}_3\}](./images/813cfae71a48543417782484a31dbd458de25ade.png) is linearly independent.

**P4.28** Since the set ![\{\vec{u},\vec{v}\}](./images/330eafccc48633cc20ba2911e630ca55de8a71df.png) is a basis for ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png), the dimension of ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png) is two. The set ![\{\vec{u} + \vec{v}, a\vec{u}\}](./images/151a37f62f9c24c6ecdd82ff27ab415932ffce49.png) contains two vectors so it is sufficient to check whether the vectors in the set are linearly independent. Consider the following equation:

![\beta_1(\vec{u} + \vec{v}) + \beta_2a\vec{u}
= 0
= \underbrace{(\beta_1 + \beta_2a)}_{\alpha_1}\vec{u} + \underbrace{\beta_1}_{\alpha_2}\vec{v}.](./images/74628bb1d81963dd10caa22e4b1fb2e34f7a83af.png)

Given ![\{\vec{u},\vec{v}\}](./images/330eafccc48633cc20ba2911e630ca55de8a71df.png) is a linearly independent set, the only solution to ![\alpha_1 \vec{u} + \alpha_2 \vec{v} =0](./images/c7d4f5e59ab901817e54e8715db1b56323b9e8c2.png) is ![(\alpha_1,\alpha_2)=(0,0)](./images/eac6149b5c0f3c9a2babd11007638feb0fb549a7.png); therefore ![\beta_1 + \beta_2a = \beta_1 = 0](./images/a794a60447ab94c06a477522dd88cf928b68cdee.png) and ![\beta_1 = \beta_2 = 0](./images/c3c8173fec5455da56e7971d4b16995833abd0b8.png). This implies ![\{\vec{u} + \vec{v}, a\vec{u}\}](./images/151a37f62f9c24c6ecdd82ff27ab415932ffce49.png) is a basis for ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png). The proof for ![\{a\vec{u}, b\vec{v}\}](./images/f06a3fbabd6dafe4de22fb3e300c3fbdf86a9e7d.png) is analogous.

**P4.29** To extend the set ![\{\vec{v}_1,\vec{v}_2\}](./images/bef4ce5d9df5c6ce308b18824ebb7c04b515613e.png) to a basis for ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png) we must pick a vector that is linearly independent from ![\vec{v}_1](./images/d33646fb26ad9d3975a25ad3c85c11f594226bce.png) and ![\vec{v}_2](./images/65b10c95bdff2bcc3058df8e5d95333772f5523c.png). We can see the structure of ![\textrm{span}(\vec{v}_1,\vec{v}_2)](./images/434ff2a3fe5f6494ff493d42e877e7cd61dabc79.png) more clearly if we construct the matrix ![V\!=\!\begin{bmatrix}
\textrm{---} \vec{v}_1 \textrm{---} \\
\textrm{---} \vec{v}_2 \textrm{---}\end{bmatrix}](./images/e6724c1db019c6bbf47e2b03546fae1120c5fcc5.png) and transform it to its reduced row echelon form ![\sim \begin{bmatrix}1 & 2 & 0 \\ 0 & 0 & 1\end{bmatrix}](./images/d8ca94cbeb7da066d258b9809f44f2b6dda8a5a6.png). We can add the vector ![\vec{v}_3=(0,1,0)](./images/20b9e0ba04dc7c455102c9eabe1c0bae02e39f25.png) to make this matrix full rank. On the other hand, if we want to add a third vector ![\vec{v}_4](./images/497b24787340775ee919702626cee362c519cef7.png) that is not linearly independent, we can pick any linear combination of ![\vec{v}_1](./images/d33646fb26ad9d3975a25ad3c85c11f594226bce.png) and ![\vec{v}_2](./images/65b10c95bdff2bcc3058df8e5d95333772f5523c.png), like ![\vec{v}_4 = \vec{v}_1 + \vec{v}_2](./images/400b03f3d9dff71dc4df979382a92b3e64bbbefb.png), for example.

**P4.30** Construct the matrix ![V\!=\!\begin{bmatrix}
\textrm{---} \vec{v}_1 \textrm{---} \\
\textrm{---} \vec{v}_2 \textrm{---} \\
\textrm{---} \vec{v}_3 \textrm{---} \end{bmatrix}](./images/cc859bff45e77b89da115182f00728672d3a952d.png) and find a vector in its null space.

##[Chapter 5 solutions](./Front matter.md)

### Answers to exercises

**E5.1**

1.   ![T_1](./images/0c939d1d782c2f141809d390824e095cab4cf007.png) is linear, ![M_{T_1} = \begin{bmatrix}1 & 2 & 3\end{bmatrix}](./images/9f319220d03a6316815e0abf96a6efcf82965149.png);
2.   ![T_2](./images/d6ac5c698528f2a098c74de07d2794fbebbced94.png) is not linear, ![T_2(2,0) \neq 2T_2(1,0)](./images/13b2f06b7539ce7269a05a964f7b3b1ffab7727b.png);
3.   ![T_3](./images/f105829d657e89a5289e6ddf5acde806823951f8.png) is not linear, ![T_3(2,0) \neq 2T_3(1,0)](./images/07c75352476ac4d43a3416210d8c7659b0da805a.png);
4.   ![T_4](./images/a3a901e8254ff306501263c9ced13e4f304d2b07.png) is linear, ![M_{T_4} = \begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ 1 & 0 & 0\end{bmatrix}](./images/434290227a639edd47353fe479cf580e005e19dc.png).

**E5.2** ![T : \mathbb{R}^3 \to \mathbb{R}^3](./images/b1753d4f064554d4a5ee943f67074d042a32dede.png), ![\textrm{Ker}(T)=\{ \vec{0} \}](./images/4a3cca6e9b9df5077e2d38d9f43c0c7ee917a0bb.png), ![\textrm{Im}(T)=\mathbb{R}^3](./images/309a8c4c30a7b8529f4e1880120375ad64a61314.png). ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is injective and surjective; therefore it is bijective. **E5.3** ![T_M : \mathbb{R}^3 \to \mathbb{R}^2](./images/592d6393e1b70eedd05c7aff69623f17d28a342c.png), ![\textrm{Ker}(T_M)=\textrm{span}( (0,1,0) )](./images/f0e508e2045ee28e1bd6ed8d2977dd6fe2bee49d.png), ![\textrm{Im}(T_M)=\mathbb{R}^2](./images/fd1648bddec2e3910f94d443d1b81366a555dff1.png). ![T_{M^\sfT} : \mathbb{R}^2 \to \mathbb{R}^3](./images/7afea532920c784ed232691344fe6aad32640db3.png), ![\textrm{Ker}(T_{M^\sfT})=\{ \vec{0} \}](./images/3b8adae31d84989a8625285415df7c373692220e.png), ![\textrm{Im}(T_{M^\sfT})=\textrm{span}( (1,0,0), (0,0,1) )](./images/3759be7f9dae1d74fe1164fc783512adcbe63e2e.png). **E5.4**  ![T(x,y) = (x+4y, 2x + 5y, 3x + 6y)](./images/158ecf009a1c2bdca9fafe66220877fedaef82a7.png) and ![M_T = \begin{bmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6\end{bmatrix}](./images/e15f0a716da37ae8af1a805d7ea16f2b8a53a994.png). **E5.5** ![M_{R_{\frac{\pi}{4}}} = \begin{bmatrix}
\frac{\sqrt{2}}{2} & - \frac{\sqrt{2}}{2}\\\frac{\sqrt{2}}{2} & \frac{\sqrt{2}}{2}
\end{bmatrix}](./images/9e1a6ca678d92b0ea1a739e7cee48a4f9cd9aecc.png), ![M_{R_{\frac{\pi}{2}}} = \begin{bmatrix}
0 & -1 \\ 1 & 0
\end{bmatrix}](./images/6a26f91ab2e7d0b4116cacf3114f25fae00561b9.png). **E5.6** ![M_{\Pi_{\vec{d}}}=\hat{d}\hat{d}^\sfT=\begin{bmatrix}
\frac{1}{10} & \frac{3}{10}\\\frac{3}{10} & \frac{9}{10}\end{bmatrix}](./images/db67fb7f4aa0baeb98434a8662af27feaf7133a6.png). **E5.7** ![\!\tensor[_{B}]{\left[M_T\right]}{_{B}} =
\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}} \!
\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}} \!
\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/760e625d0626d74aa0a2ab5bcc16db40b9b1f431.png). **E5.8**

1.  ![\!\tensor[_{B_s}]{\left[M_T\right]}{_{B_s}} = \begin{bmatrix}3 & 0\\0 & 1\end{bmatrix}](../Images/f14c34d6c925eb6e821f9d0e4a118285a15c36ca.png);
2.  ![\!\tensor[_{B_{\!f}}]{\left[M_T\right]}{_{B_{\!f}}} = \begin{bmatrix}1 & 0\\0 & 3\end{bmatrix}](../Images/65e2733066392ce7c5a1409849c844d03b6f1f2c.png);
3.  ![\!\tensor[_{B_d}]{\left[M_T\right]}{_{B_d}} = \begin{bmatrix}2 & 1\\1 & 2\end{bmatrix}](../Images/e45bfa4d1c1af6036ac6aae61cdcffae932c0305.png).

**E5.9** ![\tensor{\left[\vec{x}_i\right]}{_{B}}
= \!\tensor[_{B^\prime}]{\left[M^{-1}_T\right]}{_{B^\prime}}
\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}}](../Images/e3a51ecc6cf5d77f2836e77a1134599095408b7b.png), ![\tensor{\left[\vec{y}_i\right]}{_{B}}
= \!
\tensor[_{B}]{\left[M_T\right]}{_{B}} \!
\tensor[_{B^\prime}]{\left[M^{-1}_T\right]}{_{B^\prime}}
\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}}](../Images/d453784f7a7909fe9129394573357df8cc5928dc.png).

### Solutions to selected exercises

**E5.5** The general formula for the rotation matrix is ![R_{\theta} = \begin{bmatrix}
\cos\theta	&-\sin\theta \\
\sin\theta	&\cos\theta \end{bmatrix}](./images/a8a87cf2c57b646036186cd7b3b9e1e2582fdf86.png). Substitute the values ![\theta = \frac{\pi}{4}](./images/6da292d11915b10603e7710037f146016f6b4e54.png) and ![\theta = \frac{\pi}{2}](./images/e20734f1f9c8ffe2b35bd53fb724d6457ade4da9.png) in the general formula to obtain the matrix representations of ![R_{\frac{\pi}{4}}](./images/6767cd60a10d4ef16ac383e22ba97cd002216119.png) and ![R_{\frac{\pi}{2}}](./images/321e976c94b1b66f83c9c7de88a2491ba795190a.png).

**E5.6** A unit vector in the direction ![\vec{d}](./images/b9be750f633ce5bec55379e5fee742e8c39401d8.png) is given by ![\hat{d} = \frac{\vec{d}}{\| \vec{d} \|} = (\frac{\sqrt{10}}{10},\frac{3 \sqrt{10}}{10})^\sfT](./images/f36a1b75c789a8499188ac5ff273bc33728d2dd2.png). To find the projection matrix, compute the outer product ![\hat{d}\hat{d}^\sfT](./images/aadacd0bfd35922a93cc4b275c107c26a1ac8447.png).

**E5.7** Start with the formula for ![\!\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}](../Images/466c61726ff088465d23e3727bfafbbf2e940dfd.png) and multiply it by ![\!\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/6eba5736aaeac39bfab97bb1914be2d01a992628.png) from the left and by ![\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/4a4ecfdfc9c5054e751269d1546d09a63ba094ae.png) from the right.

**E5.8** Find the answers to parts **a)** and **b)** by inspection. For part **c)**, obtain ![\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_d}}
= \begin{bmatrix}\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}}\\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\end{bmatrix}](../Images/0e4834ead3a0be40aed4ac3156e6816fe2f20164.png) and find its inverse: ![\tensor[_{B_d}]{\left[\mathbbm{1}\right]}{_{B_s}}
= \begin{bmatrix}\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}}\\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\end{bmatrix}](../Images/02a8125c9a2a5cabf161fb90e10486cddaa3fe19.png). Next, calculate ![\!\tensor[_{B_d}]{\left[M_T\right]}{_{B_d}}](../Images/eec6993269471c02f7ab0bbbaad95b4e0b6d4fe9.png) by computing ![\tensor[_{B_d}]{\left[\mathbbm{1}\right]}{_{B_s}}
\!\tensor[_{B_s}]{\left[M_T\right]}{_{B_s}}  \!
\tensor[_{B_s}]{\left[\mathbbm{1}\right]}{_{B_d}}](../Images/16e9b6baf5712032d998d9ddab91a9993c2c11b5.png).

**E5.9** Since ![\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}} = \!
\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}
\tensor{\left[\vec{x}_i\right]}{_{B}}](../Images/a77422ae7d123e5b9a73014efd99650078dea50d.png), you can recover ![\tensor{\left[\vec{x}_i\right]}{_{B}}](../Images/ce4fa5da69547ffb37673828e939d099c0181265.png) by hitting ![\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}}](../Images/30b565ff98003848e44016653e8096ec4499da50.png) with the inverse of ![M_T](./images/dbfb444ef018689f1a816771da259ccbe5b9fb51.png) in the basis ![B^\prime](./images/13d9d9ed978ead3b244fe13d0e6f6269b46a3024.png): ![\tensor{\left[\vec{x}_i\right]}{_{B}}
= \!\tensor[_{B^\prime}]{\left[M^{-1}_T\right]}{_{B^\prime}} \!
\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}}](../Images/6c96960cb4f1fa50847063008b03cc51b9e9dadd.png). To find the correct output, compute ![\tensor{\left[\vec{y}_i\right]}{_{B}}
= \!
\tensor[_{B}]{\left[M_T\right]}{_{B}}\!
\tensor[_{B^\prime}]{\left[M^{-1}_T\right]}{_{B^\prime}}
\tensor{\left[ \vec{y}^{\textrm{w}}_i \right]}{_{*}}](../Images/d453784f7a7909fe9129394573357df8cc5928dc.png).

**E5.10** Let ![\vec{c}_1, \vec{c}_2, \ldots, \vec{c}_n](./images/0f4b8841955ca80b7528ba2540c0d26f92fa1545.png) be the ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) columns of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png). Since the columns of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) form a basis for ![\mathbb{R}^n](./images/c13a42cda23a1ca066cf166c10710815dbf2b946.png), any vector ![\vec{b} \in \mathbb{R}^n](./images/c4f8d857842c460f7e942c5ae7be33288f4e630a.png) can be written as a unique linear combination of the columns of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png): ![\vec{b} = x_1\vec{c}_1 + x_2\vec{c}_2 + \cdots + x_n\vec{c}_n](./images/dae7e2be37b5392131324bd1ba29581fb83d5a64.png) for some coefficients ![x_1, x_2, \ldots, x_n](./images/1cb52bce0f5fcd3ebc3c24d354af93d62ac20500.png). Reinterpreting the last equation as a matrix product in the column picture, we conclude ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) has a unique solution ![\vec{x}](./images/d253d396ee7731d3b565bf2ff5bf610db05cf3eb.png).

**E5.11** The rank–nullity theorem tells us ![\textrm{rank}(A) + \textrm{nullity}(A) = n](./images/0c5ee797692a57e6d7fce497288c550bca8bf620.png) for any ![n\times n](./images/08e2c13b8fef8a136e869818aa0544678444207a.png) matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png). Given ![\mathcal{N}(A) =\{ \vec{0} \}](./images/2eef75841099680988f7ccd54136e65ec6231824.png), this means ![\textrm{nullity}(A)=0](./images/e2e260c97e2baa652f937d858d6437b0a8b5fb6e.png) and therefore ![\textrm{rank}(A)=n](./images/92c3eff508101a27048e5ba26f0606c90d368522.png).

### Answers to problems

**P5.1**

1.   ![T_1](./images/0c939d1d782c2f141809d390824e095cab4cf007.png) is linear, ![M_{T_1} = \begin{bmatrix} 0 &  1\\ 1 & 1\end{bmatrix}](./images/9b7c596847a122c61f52ab3758bb237a3ebdbe1e.png);
2.   ![T_2](./images/d6ac5c698528f2a098c74de07d2794fbebbced94.png) is not linear, ![T_2(2,2) \neq 2T_2(1,1)](./images/2007e8f492d8336727906d59edd612ea8fc10912.png);
3.   ![T_3](./images/f105829d657e89a5289e6ddf5acde806823951f8.png) is not linear, ![T_3(-1,-1) + T_3(1,1) \neq T_2(0,0)](./images/b7590e18d3d5804190ba0f0364f3af8121f63aa0.png);
4.   ![T_4](./images/a3a901e8254ff306501263c9ced13e4f304d2b07.png) is linear, ![M_{T_4} = \begin{bmatrix} 3 & -2 & 1\\ 2 & 1 & -4\end{bmatrix}](./images/caeb205a71419965ff883aea7d0551908b3c5cb2.png);
5.   ![T_5](./images/13ef7d217ea788b0056c4e83086dfde39911a321.png) is linear, ![M_{T_5} = \begin{bmatrix} 1 \\2 \\ 3 \end{bmatrix}](./images/497b748ca958ea87cc519372b86e4fbafef37d4a.png);
6.   ![T_6](./images/9386514dec3c10aba518c05341321b727491d22b.png) is not linear, ![T_6(2,0,0,0) \neq 2T_6(1,0,0,0)](./images/70a57d74789afb390f684120bd090422fb6db2a3.png).

**P5.2** ![\textrm{Im}(T)=\textrm{span}\!\left((1,1,0),(0,-1,2)\right)](./images/6da9f4b16dea5fd4336289116ffeebf05a3a29e9.png). **P5.3** ![M_T=\begin{bmatrix}
0 	& - a_{z} 	& a_{y}\\
a_{z} & 0 		& - a_{x}\\
-a_{y} & a_{x} 	& 0\end{bmatrix}](./images/c6ff51a92181224073fa837bf697b0aba2588025.png); ![\textrm{Ker}(T) = \textrm{span}(  (a_x,a_y,a_z)^\sfT )](./images/7f06af7eb51c7a70b12dfad227f4d85423e0774f.png). **P5.4** ![M_T=\begin{bmatrix}-1 & 3\\-7 & 4\end{bmatrix}](./images/e0d35920a57f35616987939c2f5bacd6d07c2c0d.png), with respect to the standard basis. **P5.5**

1.  ![\!\tensor[_{B}]{\left[M_T\right]}{_{B}} = \begin{bmatrix}
    1& 0 &0 \\1 & 1 &0 \\ 1 & 1 & 1\end{bmatrix}](../Images/32a28d0d1f155a7972e42ee36f1a62b5b137dca5.png);
2.  ![\!\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}} = \begin{bmatrix}
    1 & 0 & 0\\1 & \frac{3}{2} & \frac{1}{2}\\0 & - \frac{1}{2} & \frac{1}{2}\end{bmatrix}](../Images/68663a20d87d586a8ae8b9db785d667cfdcd51ac.png);
3.  ![\!\tensor[_{B}]{\left[M_T\right]}{_{B^\prime}} = \begin{bmatrix}
    1 & 0 & 0\\1 & 1 & 1\\1 & 2 & 0\end{bmatrix}](../Images/1f7b18696c44dfab503631035c073eaf908a0241.png).

**P5.6** ![\!\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}
= \begin{bmatrix}2 & 0 & 0\\0 & 2 & 0\\0 & 0 & -3\end{bmatrix}](../Images/4aca386a1c8cffcf28c5d615b54e031af04b505a.png). **P5.7**

1.  ![\mathbbm{1}](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png), which is the identity transformation;
2.  ![M_1 = \begin{bmatrix}0 & 1\\ 1 & 0  \end{bmatrix}](./images/53e690a2bda08014688e3d2c9cf0cdaf0d43fe07.png);
3.  ![M_2 = \begin{bmatrix}1 & 0\\ 0 & -1 \end{bmatrix}](./images/c9bd3177c64f23f3b449fd4c7bcb9a8be6b40d3a.png);
4.  ![M_3 = \begin{bmatrix}	\cos(\frac{\pi}{3}) 	&\; -\sin(\frac{\pi}{3})	\\
    \sin(\frac{\pi}{3}) 	&\;  \cos(\frac{\pi}{3})	\end{bmatrix}](./images/11e913d0450f6b6c68e08b01f446dd04cf481c28.png);
5.  ![M_4 = \begin{bmatrix}	\cos(-\frac{\pi}{6}) 	&\; -\sin(-\frac{\pi}{6})	\\
    \sin(-\frac{\pi}{6}) 	&\;  \cos(-\frac{\pi}{6}) 	\end{bmatrix}](./images/34cf19db66230e51de8c76cabddaf2bdf1720547.png);
6.  ![M_5 = \begin{bmatrix}1 & \frac{1}{2}\\ 0 & 1\end{bmatrix}](./images/f32faa4860678072006e1c67aad39195dac12050.png).

### Solutions to selected problems

**P5.2** Applying ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) to the input vector ![(1,0)](./images/17fa76d96a4d6efa1a8a1bab1ccb6699ef7b2e34.png) produces ![(1, 1-0, 2\cdot 0)=(1,1,0)](./images/55510bf768f98aa23f231d089b465cf4d2a37878.png), and the input vector ![(0,1)](./images/e69b48bc6687ee74a843dea90543682e53e069e3.png) produces the output ![(0, 0-1, 2\cdot 1)=(0,-1,2)](./images/180cd29410d4ee901735b2fd830d429075dee4ad.png). Thus, ![\textrm{Im}(T)=\textrm{span}\!\left((1,1,0),(0,-1,2)\right) \subseteq\mathbb{R}^3](./images/35b2b3de341f142a788e592f07fe1dcd5dd14195.png).

**P5.3** Use the standard probing-with-the-standard-basis approach to obtain the matrix representation. See[`youtu.be/BaM7OCEm3G0`](./BaM7OCEm3G0.md) for an interesting discussion about the cross product viewed as a linear transformation.

**P5.5** The change-of-basis transformation from ![B^\prime](./images/13d9d9ed978ead3b244fe13d0e6f6269b46a3024.png) to the standard basis is ![\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}} = \begin{bmatrix}1 & 0 & 0\\0 & 1 & 1\\0 & 1 & -1\end{bmatrix}](../Images/6583352023105cc282abd61c8d24355e5af9985e.png). We find ![\!\tensor[_{B}]{\left[M_T\right]}{_{B}} = \begin{bmatrix}1& 0 &0 \\1 & 1 &0 \\ 1 & 1 & 1\end{bmatrix}](../Images/32a28d0d1f155a7972e42ee36f1a62b5b137dca5.png) directly by observing the formula for ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png). Next we compute ![\!\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}](../Images/466c61726ff088465d23e3727bfafbbf2e940dfd.png) using the “sandwich” formula ![\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}
\!\tensor[_{B}]{\left[M_T\right]}{_{B}}
\!\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/e870a1ceb45123ad29c2271a2ca15dd491c08fdf.png). Finally, we compute ![\!\tensor[_{B}]{\left[M_T\right]}{_{B^\prime}}](../Images/f424452a0c517dabe6122acf2d4c83db0870e677.png) by changing only the right basis of the transformation: ![\!\tensor[_{B}]{\left[M_T\right]}{_{B^\prime}}  = 	\!\tensor[_{B}]{\left[M_T\right]}{_{B}} \!\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/1bc6f5a88d597c9e58c84b96dec3c2a6f32c4e1a.png).

**P5.6** The change-of-basis matrix from the basis ![B^\prime](./images/13d9d9ed978ead3b244fe13d0e6f6269b46a3024.png) to the standard basis ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) is ![\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}} = \begin{bmatrix}1 & 0 & 1\\0 & 1 & 0\\0 & 0 & 1\end{bmatrix}](../Images/59fc1637d881ea576ce233ed3f0059b55b1d0576.png). We then compute ![\!\tensor[_{B^\prime}]{\left[M_T\right]}{_{B^\prime}}=
\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}
\!\tensor[_{B}]{\left[M_T\right]}{_{B}}
\!\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/d275ec3132a5f7cbce7e48494badc6ad0ac2467c.png).

**P5.7** First, you must visually recognize the type of transformation that is acting in each case; then, use the appropriate matrix formula. Transformations 1 and 2 are reflections. Transformations 3 and 4 are rotations. Transformation 5 is a _shear_ that maps ![T_5(\hat{\imath})=\hat{\imath}](./images/994444b67a2a1d172832ba981a3fade9831df274.png) and ![T_5(\hat{\jmath})=(\frac{1}{2}, 1)^\sfT](./images/161a58591cf91e7cdc826496c354eb419f4756f2.png). You can obtain the matrix representation from these two observations.

**P5.8** Let ![B_s = \{ \hat{e}_1, \hat{e}_2, \ldots, \hat{e}_n \}](./images/eb5aa6ab3220bf9c00911ae912fc0f2bc9be3cba.png) be the standard basis for ![\mathbb{R}^n](./images/c13a42cda23a1ca066cf166c10710815dbf2b946.png). Since ![A\vec{x} = \vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) has a solution ![\vec{x}](./images/d253d396ee7731d3b565bf2ff5bf610db05cf3eb.png) for every possible ![\vec{b}](./images/9de6fd92ad217df8b49690b95fe00acb5956bf59.png), it is possible to find the solutions ![\vec{x}_i](./images/9c62a70853e0ee7831a1e915db39a61f9c0058a9.png) in ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) equations of the form ![A\vec{x}_i= \hat{e}_i](./images/fcfbf01950966f645c4ce7b6fe93b9569ec41b50.png), for ![i \in \{1,2,\ldots, n\}](./images/5c3f9d6aa08545f1a61189dc9bfd5a13abaa7a5d.png). Now construct the matrix ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) that contains the solutions ![\vec{x}_i](./images/9c62a70853e0ee7831a1e915db39a61f9c0058a9.png) as columns: ![B=[\vec{x}_1, \ldots, \vec{x}_n]](../Images/8a49f895f88f4e0ea5c8d1b7cf1fa944f1fe4c85.png). Observe that ![A B = A [\vec{x}_1, \ldots, \vec{x}_n]](../Images/adbe80633a2aca0f056bc2f39106d1a0a2d8c1c3.png) ![=[A\vec{x}_1, \ldots, A \vec{x}_n]](../Images/aae6dce2cb624b9aa3e71d2e7be79e136fe7f50e.png) ![=[\hat{e}_1,  \ldots, \hat{e}_n] = \mathbbm{1}_n](../Images/7b990fedc5dd0fc343cc9c3daff878b605b702c5.png). The equation ![BA=\mathbbm{1}_n](./images/60545b7313d6c17750f8bc1ece39792436b4d1a9.png) implies ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is invertible.

**P5.9** We want to show there is a unique solution to ![A\vec{x} =\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) if and only if ![A\vec{y} =\vec{0}](./images/32a613d295ef80379534f5b12c90de06d0124df6.png) has only the trivial solution ![\vec{y}=\vec{0}](./images/8f983ea66c2e283c7a22ba145a494f9345440b09.png). To show **(2)**![\Rightarrow](./images/574ec67e273e0b826ab15d9302589550a2de1145.png)**(4)**, let’s assume the opposite of ![\mathbf{(4)}](./images/07d1bf71f51c47c635997579a9368a2e3673d127.png) is true: that ![A\vec{x} =\vec{0}](./images/2364c48fe18dbfa6d867d8b3ba4b7c329d64a97e.png) has a nontrivial solution ![\vec{y} \neq \vec{0}](./images/630ea8212948af2cd227f3ebc192d310df7f24b1.png). If this is true, then ![\vec{x}^\prime = \vec{x}+\vec{y}](./images/0b6f628eb36c5c016d487b5f3ecf791c95435851.png) is a solution to ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) since ![A\vec{x}^\prime = A(\vec{x}+\vec{y})=A\vec{x}+\cancelto{0}{A\vec{y}}=A\vec{x}=\vec{b}](./images/6c1d229221e13a7d0be931148c50b556f44a7bff.png). Since ![\vec{y} \neq 0](./images/05ac776007a59abb9fae71717781f9701d5571f6.png), ![\vec{x}^\prime \neq \vec{x}](./images/93ef10ed622eae61f5dfe6a9f1bb6d5ceebdc237.png), and therefore ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) does not have a unique solution. If we want ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) to have a unique solution, ![A\vec{y}=\vec{0}](./images/32a613d295ef80379534f5b12c90de06d0124df6.png) must have only the trivial solution ![\vec{y}=\vec{0}](./images/8f983ea66c2e283c7a22ba145a494f9345440b09.png).

We can use similar reasoning to show **(4)**![\Rightarrow](./images/574ec67e273e0b826ab15d9302589550a2de1145.png)**(2)**. Assume ![A\vec{x}_1 = \vec{b}](./images/813571076e6cb8ac180d998d84059aacca434ac0.png) and ![A\vec{x}_2 = \vec{b}](./images/e9fdf66ca19c2ce17b2470c8ae04ccba36c9dc2c.png) are two solutions, and assume ![\vec{x}_1 \neq \vec{x}_2](./images/34ac353ac1de720aaafd4a99239512fe6c20d7e7.png). Then ![A(\vec{x}_1-\vec{x}_2) = \vec{0}](./images/d835098f89250802f171c8c3aa554c6701741714.png); and, since ![\vec{x}_1 - \vec{x}_2 \neq \vec{0}](./images/dc1e4c22785273159c18ac94fd72410919450ae9.png), we’ve shown that ![A\vec{x}=\vec{0}](./images/2364c48fe18dbfa6d867d8b3ba4b7c329d64a97e.png) has a nontrivial solution. If we want ![A\vec{y}=\vec{0}](./images/32a613d295ef80379534f5b12c90de06d0124df6.png) to have only the trivial solution ![\vec{y}=\vec{0}](./images/8f983ea66c2e283c7a22ba145a494f9345440b09.png), then ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png) must have a unique solution.

**P5.10** If ![A\vec{x} = \vec{0}](./images/2364c48fe18dbfa6d867d8b3ba4b7c329d64a97e.png) has only the trivial solution ![\vec{x}=0](./images/a9df2ac9c080d3d5dd5d2532a5c6bbd775340d75.png), then the reduced row echelon form of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) contains no free parameters and ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) has full rank.

**P5.11** To solve the system of equations ![A\vec{x} = \vec{0}](./images/2364c48fe18dbfa6d867d8b3ba4b7c329d64a97e.png), we build the augmented matrix ![[\;A\; | \; \vec{0}\:\;  ]](../Images/4bf150937cdde827ead19b8a2e7ec3787a8afcab.png) and compute its RREF. Since ![A\vec{x} = \vec{0}](./images/2364c48fe18dbfa6d867d8b3ba4b7c329d64a97e.png) has a unique solution, the RREF of ![[\;A\; | \; \vec{0}\:\;  ]](../Images/4bf150937cdde827ead19b8a2e7ec3787a8afcab.png) doesn’t contain any free variables, so the reduced echelon form of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) must be ![\mathbbm{1}_n](./images/80172280ff371cf29109741e0ea9a3f77229c0c1.png).

**P5.12** Assume the matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is invertible. Consider the procedure for obtaining the matrix inverse that starts from the extended array ![[\;A\; | \; \mathbbm{1}\:\;  ]](../Images/0646aa44a0a4dd7e995be55738aa651310726ed7.png). The sequence of row operations ![\mathcal{R}_1, \mathcal{R}_2, \ldots, \mathcal{R}_k](./images/08f740f415eb9dff50037738409941c42f28fa43.png) is used to obtain the RREF of the extended array:

![[\;A\; | \; \mathbbm{1}\:\;  ]
\quad
- \mathcal{R}_1, \mathcal{R}_2, \ldots, \mathcal{R}_k \to
\quad[ \; \:\mathbbm{1}\;  | \; A^{-1} \;].](../Images/67c8cc5bbb97e1b880a80ff8f8c1427c5c966906.png)

Thus, ![\textrm{rref}(A)=\mathbbm{1}](./images/00b6cffd0f336fd924883d9ab2fc363b441d8ebd.png). Note the determinant of the final step is nonzero; ![|\mathbbm{1}| \neq 0](./images/ebe15c6d82a8e66f5e5755c3b1ea87f2873c252b.png). Since the row operations ![\mathcal{R}_i](./images/f5e010bee539414a7b86e7e040bab0c416726cc8.png) only act to change the sign or the size of the determinant, the overall sequence of row operations doesn’t change the zero vs. nonzero nature of the determinant. This implies the determinant of the original matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is also nonzero; ![|A| \neq 0](./images/3cfd7d76b93460d52f6d534d973093fdc2711fb8.png).

**P5.13** If ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is injective, then its kernel contains only the zero vector ![\textrm{Ker}(T) = \{ \vec{0} \}](./images/4a3cca6e9b9df5077e2d38d9f43c0c7ee917a0bb.png). Since we’re interested in determining the linear independence of the set ![\{T(\vec{v}_1), \ldots, T(\vec{v}_n)\}](./images/97b7563321663b43fbe1e63311cd428174c56a0f.png), we must consider the solutions to the equation

![\alpha_1T(\vec{v}_1) + \cdots + \alpha_nT(\vec{v}_n) = \vec{0}.](./images/6275867ca9b39c46d8db34aadc0ea5fd76b6db85.png)

Knowing ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is linear, we can rewrite this as ![T(\alpha_1 \vec{v}_1 +  \cdots + \alpha_n\vec{v}_n)= \vec{0}](./images/56670209d7472bd615e6031843bdf64cdb738953.png). Since ![\textrm{Ker}(T) = \{ \vec{0} \}](./images/4a3cca6e9b9df5077e2d38d9f43c0c7ee917a0bb.png), the equation we started with is equivalent to the equation ![\alpha_1 \vec{v}_1 +  \cdots + \alpha_n\vec{v}_n = \vec{0}](./images/a8d873841a8e63117888c9f617aceffb7cd48541.png). But we’re told ![\{\vec{v}_1, \ldots, \vec{v}_n\}](./images/74bb0f6d123899dd1a1696a3a856fd92d4694ec6.png) is a linearly independent set, so the only solution to this equation is the trivial solution ![\alpha_i=0](./images/4768b74ed594132de56328481fa56679694f4996.png). Therefore ![\{T(\vec{v}_1), \ldots, T(\vec{v}_n)\}](./images/97b7563321663b43fbe1e63311cd428174c56a0f.png) is a linearly independent set.

**P5.14** Consider an arbitrary vector ![\vec{w} \in W](./images/5d599cdfde3efa0f028f483572a70206d5a15c3c.png). Since ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is surjective, there must exist a vector ![\vec{v} \in V](./images/29866f8b2ddb39d0672c000364e6c3550e02dace.png) such that ![T(\vec{v}) = \vec{w}](./images/eec2f844626e69749d75a6cd299785caf609ab66.png). We know ![\{\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n\}](./images/c347f2a61041e38870318e22c3cab109a9aa03c0.png) is a spanning set for ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png), so it must be that ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) can be written as a linear combination of this set of vectors:

![\vec{v} = \alpha_1 \vec{v}_1 +  \alpha_2\vec{v}_2 + \cdots + \alpha_n\vec{v}_n.
\quad](./images/78fd6e14067b3f07fa6452941370de7b319d3abe.png)

Now apply the linear transformation ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) to both sides of this equation:

![\vec{w} = T(\vec{v}) = \alpha_1T(\vec{v}_1) +  \alpha_2 T(\vec{v}_2) + \cdots + \alpha_nT(\vec{v}_n).](./images/cef3bd15e68c7a1b074433831680d6b65911e0c3.png)

We’ve shown that an arbitrary vector ![\vec{w} \in W](./images/5d599cdfde3efa0f028f483572a70206d5a15c3c.png) can be written as a linear combination of the vectors ![T(\vec{v}_1)](./images/9c168b3b412c5226c26fd18ed69f5d90aaf9ee8f.png), ![T(\vec{v}_2)](./images/1629dbc54f34c2ad336c0f83addd5d08959ee23b.png), …, ![T(\vec{v}_n)](./images/a154fcd81f8b2ae1aeb648484272882c26a66e56.png); therefore, the vector space ![W](./images/cf83ddf97823b88ae25eb70438f249f159f02fbf.png) is spanned by ![\{T(\vec{v}_1), T(\vec{v}_2), \ldots, T(\vec{v}_n)\}](./images/0299674f8a1e7e0ddbaccfaefef0412e91e93d50.png).

**P5.15** Assume ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) doesn’t have full rank. Then there must exist a nonzero vector ![\vec{y}](./images/c85a8e41439136335598a45b5d6c94c03ccce093.png) such that ![B\vec{y}=0](./images/8b64ceca8663465b079dd7f29f8dfdd27014c4e2.png). Now multiply both sides of the equation ![AB=\mathbbm{1}](./images/c5106705d43e103f4d2d94bedca4c03370087085.png) by the vector ![\vec{y}](./images/c85a8e41439136335598a45b5d6c94c03ccce093.png) to obtain ![AB\vec{y} = \mathbbm{1}\vec{y} = \vec{y}](./images/090e9da32508ae2cf741ed0b71f7098513f77b62.png). The left side of this equation is ![AB\vec{y}=A\vec{0} = \vec{0}](./images/61032a495d410376c36927ffa3f40a3f21dc511a.png), but the right side is ![\mathbbm{1}\vec{y} = \vec{y} \neq \vec{0}](./images/f3225732bc349ee05fbe315dd8a9c6693d2c91eb.png), so we’ve arrived at a contradiction and ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) must have full rank.

For the second part of the question, we start from the equation ![AB= \mathbbm{1}](./images/c5106705d43e103f4d2d94bedca4c03370087085.png) and multiply both sides by ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) to obtain ![BAB = B](./images/42e8adb0f2402c3f6aa485a284d46f5b0315e166.png), which simplifies to ![(BA - \mathbbm{1})B = 0](./images/7f1fdaf2a678d16ad15661a71895b355c0f52f7b.png). We can multiply this equation by any nonzero vector ![\vec{x} \in \mathbb{R}^n](./images/5c1b3670be91e1e0aaf2bb066be8c19f8b3e8575.png) and obtain ![(BA - \mathbbm{1})B\vec{x} = \vec{0}](./images/a75bdc1bb7cbc016ffc04ce9bac75ef37e3dbf92.png). Since we know ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) has full rank ![B\vec{x} \neq 0](./images/00ad771e27a4432394a4eef43aa67b7548e6da82.png), it must be that ![(BA - \mathbbm{1})](./images/840c251533c8dbcd5fe49501639769933726f065.png) is the zero matrix. Therefore ![BA = \mathbbm{1}](./images/043298d6b292f59cd4f0270a30f06b54b4e7f966.png).

##[Chapter 6 solutions](./Front matter.md)

### Answers to exercises

**E6.1**

1.  ![p(\lambda)=(\lambda-4)^2](./images/b2bc0241d7e44eaecef15872c8b1ac8bd22b95f9.png); ![\lambda_1=4](./images/48a462f22915a9157b8b7ea11d5eddb46338aa74.png) (repeated).
2.  ![p(\lambda)=\lambda^2-4\lambda-5](./images/2adb63e34cf369ddc82499f4e1d7bab7c26fecc6.png); ![\lambda_1=5](./images/5856d0b77ca309a7484b70cd890f83d0beaa47f7.png) and ![\lambda_2=-1](./images/cef3f79b03d4a080c911cd1bdbb2d9306404498d.png).
3.  ![p(\lambda)=\lambda^2-21](./images/4fea220cc514a587c0a680e0898d03434a41d7f7.png); ![\lambda_1=\sqrt{21}](./images/3bc26022241acf530fd34a0c1b972d0d4feb5011.png), ![\lambda_2=-\sqrt{21}](./images/76c6076c00f1d132c7469faf1c4d3635f6ed4681.png).
4.  ![p(\lambda)=\lambda^2](./images/bc7ae432b8bd64ff419b219692ab7767fb68b005.png); ![\lambda_1=0](./images/447dc65e04e5d33e042aff25cf9556bf7a8f8ddd.png) (repeated).
5.  ![p(\lambda)=\lambda^2-2\lambda+1](./images/f3981c44ad15a9c7d87a3c7ee26acacd563aa700.png); ![\lambda_1=1](./images/c21ae39b78a77a312730247b3e13b40200f75e7e.png) (repeated).

**E6.2**  ![\lambda_1=1](./images/c21ae39b78a77a312730247b3e13b40200f75e7e.png) with eigenvector ![\vec{e}_1 = (1,1,0)^\sfT](./images/980e3f1db3aedd4fe59bb6e3c2742b883afd0d3d.png) and ![\lambda_2=5](./images/3b9f6b44209da572639a600ee5cc0a06c18bf4cc.png) with eigenvectors ![\vec{e}_2 = (-1,1,0)^\sfT](./images/41dc8312a02e96a913b5f9a062ab3a2b2d4b440f.png) and ![\vec{e}_3 = (0, 0, 1)^\sfT](./images/6ced4a63f72c257b01264f2a6617315848ccc775.png). **E6.6**  ![\alpha=-3](./images/811c1f9eee8acc06d92eb26f7c2a34943081f573.png) and ![\beta= 4](./images/06398a323156f9fcbb65e172be4ac294eacc14e6.png). **E6.7**  ![(1,1)^\sfT](./images/e4581efa87bd5df766af244071ec6ebd01ecc565.png) and ![(1,-2)^\sfT](./images/3f6415983ff4128e379cfa69df14c35735db5ca7.png) are eigenvectors of ![L](./images/767c126073d24e4524f0b90b80e9579b9c16b1db.png). **E6.8** ![\det(A)=15](./images/5014ab8d4918cfe0bf9afceebfee244dc539a045.png), ![A^{-1}= \begin{bmatrix} 1 & - \frac{4}{5} & - \frac{11}{3}\\0 & \frac{1}{5} & - \frac{1}{3}\\0 & 0 & \frac{1}{3} \end{bmatrix}](./images/617de4ee1379715e22738a8552cfeb465b70439a.png); ![\det(B)=xz](./images/85ea056346d00a7630978d34e54996972fa6a70d.png), ![B^{-1}=\begin{bmatrix}\frac{1}{x} & 0\\- \frac{y}{x z} & \frac{1}{z}\end{bmatrix}](./images/2c5a952c119fec420ab2e1c858601281c281170f.png); ![\det(C)=1](./images/3aa4c105092f3c30a64fbc4e28f26eb333dec320.png), ![C^{-1}=\begin{bmatrix} 5 & 0 \\ 0 & \frac{1}{5}\end{bmatrix}](./images/c4bcdaed4486fc71ee749125295bfb014001518e.png). **E6.9** No. **E6.10**

1.   ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is upper triangular and positive definite.
2.   ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) is orthogonal and normal. Specifically, ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) is a rotation.
3.   ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) is symmetric, orthogonal, and normal. Also, ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) is a reflection and a permutation.

**E6.11** ![\big\{ 	\mathbf{e}_1 = \begin{bmatrix} 1 & 0  \\  0 & 0 \end{bmatrix},
\mathbf{e}_2 = \begin{bmatrix} 0 & 1  \\  0 & 0 \end{bmatrix},
\mathbf{e}_3 = \begin{bmatrix} 0 & 0  \\  0 & 1 \end{bmatrix} \big\}](./images/74f99e1e648f983e3d7f2f72b32252845af47476.png). **E6.12** Yes. **E6.14** ![\|P_0\| = \sqrt{2}](./images/0f339eaa31199873db8577daaf804bf82ac12076.png), ![\|P_1\| = \frac{\sqrt{6}}{3}](./images/02ba12d91b6987c4f7deebe53fe25c16be8fdc3d.png), and ![d(P_0,P_1)=\frac{2 \sqrt{6}}{3}](./images/8d3f1dab6af1ae7fbff8c8b9c8616120b0726f18.png). **E6.15** ![\vec{e}_1=(4,2)](./images/5ec190f1c4e0b1c09e610a0bc01163aeda7dd4f5.png), ![\vec{e}_2=(-1,2)](./images/174514515fa55ea63cbea2d79f2e3699336a6d2c.png). **E6.16** ![\hat{e}_1=(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}},0)](./images/329e65bbac3b35655c6d87873dd8cf1d90f4b336.png), ![\hat{e}_2=(\frac{1}{\sqrt{6}}, - \frac{1}{\sqrt{6}}, \frac{2}{\sqrt{6}})](./images/215ab7c55cd1a1ac39e273e3f35f2c48f4ab67f9.png), and ![\hat{e}_3=(-\frac{1}{\sqrt{3}}, \frac{1}{\sqrt{3}}, \frac{1}{\sqrt{3}})](./images/c61373a6e1bc710b38cc49f9594706726c55b205.png). **E6.17** ![\hat{\mathbf{e}}_1=1](./images/ffa4d654b13802b99dd7eadeaf795e31f9b0d3fb.png), ![\hat{\mathbf{e}}_2 = \sqrt{12}(x-\frac{1}{2})](./images/b80bf678afdc17f3e29f2ee2e355306643a492b2.png), and ![\hat{\mathbf{e}}_3=6\sqrt{5}(x^2-x+\frac{1}{6})](./images/72c9c0894baa647d3959318116ce2d14211bca74.png). **E6.18** ![Q =\begin{bmatrix} \frac{1}{\sqrt{2}}	& \frac{1}{\sqrt{6}}	& 	-\frac{1}{\sqrt{3}} 	\\
\frac{1}{\sqrt{2}}		& - \frac{1}{\sqrt{6}}	&	\frac{1}{\sqrt{3}}		\\
0				& \frac{2}{\sqrt{6}} 	& 	\frac{1}{\sqrt{3}} \end{bmatrix}](./images/933f6e73fe6dcfbb4cfcab5c887e9725fc4aad8b.png), and ![R =\begin{bmatrix} \sqrt{2}		& \frac{1}{\sqrt{2}}	& 	\frac{1}{\sqrt{2}} 	\\
0			& \frac{3}{\sqrt{6}}	&	\frac{1}{\sqrt{6}}		\\
0			& 0 				& 	\frac{2}{\sqrt{3}} \end{bmatrix}](./images/3719e6d7d5f44b3a5a54476cee3c587d558e133e.png). **E6.19** **a)** ![-1 + i](./images/f2cd930b2dca129c65f9ea5cdccd9ce320fa4989.png); **b)** ![-14 + 23i](./images/6878b2b0d9a5191516ba043a5e428ec02b6c4ad1.png); **c)** ![\frac{1}{25}(26 + 7i)](./images/cd98825f0441088a7894c38e988903f52ac2f063.png). **E6.20**  ![\lambda_1=i](./images/9d8b416307c94303fd92c0afa0dcc30d8d167157.png) with ![\vec{e}_1 = (-\frac{1}{2+i}, 1)^\sfT](./images/deae1211d1d85227d168aac6f49f750dae31bb13.png) and ![\lambda_2=-i](./images/e493517c151442eac24e4a6c30b46b1568f8d3ab.png) with ![\vec{e}_2 = (-\frac{1}{2-i}, 1)^\sfT](./images/6f47fd274d57cfca8e2e9b646d3d552ce6e3a43a.png). **E6.21** ![\tensor[_{F}]{\left[\mathbbm{1}\right]}{_{B}}=\frac{1}{4}\begin{bmatrix}
1 & 1 & 1 & 1\\1 & i & -1 & - i\\1 & -1 & 1 & -1\\1 & - i & -1 & i
\end{bmatrix}](../Images/05b2e3971ad9075790f81c3038ee01b0863943b0.png). **E6.22** No.

### Solutions to selected exercises

**E6.2** The characteristic polynomial is ![p_A(\lambda) = \lambda^3-11\lambda^2+35\lambda-25=(\lambda-1)(\lambda-5)^2](./images/5639206f7dab21c5adbac1ea3542eb3ea8865ce8.png). The eigenvalues of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) are ![\lambda_1=1](./images/c21ae39b78a77a312730247b3e13b40200f75e7e.png) and the repeated eigenvalue ![\lambda_2=5](./images/3b9f6b44209da572639a600ee5cc0a06c18bf4cc.png). To find eigenvectors that correspond to ![\lambda_1](./images/f35b707e7ea2f140dc8864eee509396242b7c977.png), we must find the null space of the matrix ![(A-\mathbbm{1})](./images/28aa678611091e3eee00e3d311523552468a0e55.png). We find the eigenvector ![\vec{e}_1 = (1,1,0)^\sfT](./images/980e3f1db3aedd4fe59bb6e3c2742b883afd0d3d.png). For ![\lambda_2=5](./images/3b9f6b44209da572639a600ee5cc0a06c18bf4cc.png) we find ![\vec{e}_2 = (-1,1,0)^\sfT](./images/41dc8312a02e96a913b5f9a062ab3a2b2d4b440f.png) and ![\vec{e}_3 = (0, 0, 1)^\sfT](./images/6ced4a63f72c257b01264f2a6617315848ccc775.png).

**E6.3** Let ![\vec{e}_1](./images/9b972dff65be429ce1c6b2af34b363348b06a70f.png) be the eigenvector associated with ![\lambda_1](./images/f35b707e7ea2f140dc8864eee509396242b7c977.png) and ![\vec{e}_2](./images/264af0eea6be5b6ec5e7421ad813f442548174a0.png) be the ![\lambda_2](./images/9ede4a5f2e6e4ed32db0d9e911d1309bffce61e1.png) eigenvector. We want to show that the linear independence equation ![\alpha_1\vec{e}_1+\alpha_2\vec{e}_2 = \vec{0}](./images/5245aa77d9a39d8783ca5435bb1b920e3697dede.png) has only the trivial solution; ![(\alpha_1,\alpha_2)=(0,0)](./images/eac6149b5c0f3c9a2babd11007638feb0fb549a7.png). Multiplying the linear independence equation by ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) gives us

![A(\alpha_1\vec{e}_1+\alpha_2\vec{e}_2)
= \alpha_1\lambda_1\vec{e}_1 + \alpha_2\lambda_2\vec{e}_2
= \vec{0}.](./images/852785fab6d7a6fe1306f61023bea217bc543abd.png)

Separately, multiply the linear independence equation by ![\lambda_1](./images/f35b707e7ea2f140dc8864eee509396242b7c977.png) to obtain

![\lambda_1(\alpha_1\vec{e}_1+\alpha_2\vec{e}_2)
= \lambda_1\alpha_1\vec{e}_1 + \lambda_1\alpha_2\vec{e}_2
= \vec{0}.](./images/941dcd3cd51f60b1f4b7921931f73cfa916d7af5.png)

Subtracting the latter two equations, we find

![0\vec{e}_1 + \alpha_2(\lambda_2-\lambda_1)\vec{e}_2
= \alpha_2(\lambda_2-\lambda_1)\vec{e}_2
= \vec{0}.](./images/7a0c29e680ae464678c0323658a7268039e73be9.png)

Since ![\lambda_2-\lambda_1\neq 0](./images/581b2be321e44ca9a363f7978339fd9369a55a31.png) and ![\vec{e}_2\neq\vec{0}](./images/643f40edb16bb965573a9b5124dcee7bff7b6334.png), it must be that ![\alpha_2=0](./images/10e92bb91de58b4bb42427842298707a34ee58b2.png). But if ![\alpha_2=0](./images/10e92bb91de58b4bb42427842298707a34ee58b2.png), then the equation ![\alpha_1\vec{e}_1 + \cancelto{0}{\alpha_2}\vec{e}_2 = \vec{0}](./images/302fd25bc954374a77eebb79ec740a9bc50a1046.png) and ![\vec{e}_1\neq\vec{0}](./images/bd36c15e42fbf1d57180a9832d72214f39d0b44a.png) implies ![\alpha_1=0](./images/9995fcb302a4b9c1e691cbc9d0aaea5980eba5d5.png); thus we’ve shown ![(\alpha_1,\alpha_2)=(0,0)](./images/eac6149b5c0f3c9a2babd11007638feb0fb549a7.png) is the only solution. Therefore, ![\{ \vec{e}_1, \vec{e}_2\}](./images/598ab33d333293ed21fa7ca302a27c776f3d96e4.png) is a linearly independent set.

**E6.4** Multiply both sides of the eigenvalue equation ![A\vec{e}_\lambda=\lambda \vec{e}_\lambda](./images/7d833c282665cf3cf1b4482d1f6d33c5257efb2e.png) by ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) to obtain ![AA\vec{e}_\lambda=\lambda A\vec{e}_\lambda = \lambda^2 \vec{e}_\lambda](./images/10c005fb1ed5dfdee4993f4d86864bc97557824a.png). Thus ![\lambda^2](./images/9b71eb57df95842da13d259787ae8c624d57bac0.png) is an eigenvalue of ![A^2](./images/42fa492c11a9b8c0880228cc9499138f0f81c9ed.png).

**E6.5** Multiply both sides of the eigenvalue equation ![A\vec{e}_\lambda=\lambda \vec{e}_\lambda](./images/7d833c282665cf3cf1b4482d1f6d33c5257efb2e.png) by ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png) to obtain ![A^{-1}A\vec{e}_\lambda=\lambda A^{-1}\vec{e}_\lambda](./images/50545a9f7f26b1fac69c2224eba2ccb0b7612ed3.png). After ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png) cancels with ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png), we’re left with the equation ![\vec{e}_\lambda=\lambda A^{-1}\vec{e}_\lambda](./images/7395641c6ab2b98e68bfc60058a656f16e85dfe8.png). Dividing both sides of the equation by ![\lambda](./images/5024e92226f2b135df8c3d6a84c7cb3f3943c5e1.png) we obtain ![\frac{1}{\lambda}\vec{e}_\lambda=A^{-1}\vec{e}_\lambda](./images/4023b9feeac31992aea0a342af07f214345d2617.png), which shows that ![\lambda^{-1}](./images/6439f609888427d78737c6d69979d5ddec18e1de.png) is an eigenvalue of ![A^{-1}](./images/5e9eb810c674a94eff543456cb2ac0b98f226f5b.png).

**E6.6** The characteristic polynomial of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is ![p_A(\lambda)= x^2 -\beta x -\alpha](./images/7ebc4b4ba979961304b31e50420b9a96e8ed6a5c.png). If we want the eigenvalues of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) to be ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png) and ![3](./images/b6031d121f1b4a4b138ae89b9919d5b4c8ebf35b.png), we must choose ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png) and ![\beta](./images/bc326c959b80d3a24fcdf5fda29ab07ecaf549ba.png) so that ![p_A(\lambda)=(\lambda-1)(\lambda-3)](./images/df250f98b33ea16dea8d6a75b742b065b5e3e399.png). Expanding the factored expression, we find ![(\lambda-1)(\lambda-3)=\lambda^2 -4\lambda +3](./images/9db266b86c9d0a41da44695f36ce70bbde930515.png), so ![\alpha=-3](./images/811c1f9eee8acc06d92eb26f7c2a34943081f573.png) and ![\beta= 4](./images/06398a323156f9fcbb65e172be4ac294eacc14e6.png).

**E6.7** First we compute ![L(1,1)^\sfT = (5,5)^\sfT = 5(1,1)^\sfT](./images/c8e6e70a27a750ded14ab56319936a9cb52ca3f5.png) so ![(1,1)^\sfT](./images/e4581efa87bd5df766af244071ec6ebd01ecc565.png) is an eigenvector, with eigenvalue ![\lambda=5](./images/3b523063efc0e67818bfdf8a5db1ff486ce7f1d7.png). Next we compute ![L(1,-1)^\sfT = (1,3)^\sfT \neq \alpha(1,-1)^\sfT](./images/e0c66ef10ede365c1a7f70e0559b5a16f7a848c1.png) so ![(1,-1)^\sfT](./images/601c9bb1ecebed73b623d787a7dd70a9fb60d288.png) is not an eigenvector. We can also compute ![L(1,-2)^\sfT = (-1,2)^\sfT = -1(1,-2)^\sfT](./images/54b25bfc7e1c6e0d88a622726eff26a6cb5ca1a3.png), which implies ![(1,-2)^\sfT](./images/3f6415983ff4128e379cfa69df14c35735db5ca7.png) is an eigenvector with eigenvalue ![-1](./images/4bc0e9293b68d85818e6a2261dcd8da0284b4084.png). Since a ![2\times 2](./images/8d9f69fe9ab543dc19bd60e8ea565644efbcebb4.png) matrix can have at most two eigenvectors, we don’t need to check ![(2,-1)^\sfT](./images/a4f8546f27abbb2c5c7242cc7435d85015481b19.png) since we know it’s not an eigenvector.

**E6.9** A matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is symmetic if it satisfies ![A^\sfT = A](./images/2ac9cf58fe6395984402ca59537161b3783c70f3.png), which is not the case for the given matrix.

**E6.11** First of all we must determine dimensionality of the vector space in question. The general vector space of ![2\times 2](./images/8d9f69fe9ab543dc19bd60e8ea565644efbcebb4.png) matrices has four dimensions, but an upper triangular matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) satisfies ![a_{ij}=0](./images/be5d162d2a9bc6d77f36078d02baccecee3e40f0.png) for all ![i > j](./images/c2fe2b7516ddfa7c04aedc89002a81e3f1cebc99.png), which corresponds to the constraint ![a_{21}=0](./images/f7748b8b51bf5922222b6178d388c4c66e74c251.png). The space of ![2 \times 2](./images/8d9f69fe9ab543dc19bd60e8ea565644efbcebb4.png) upper triangular matrices is a subspace of a four-dimensional vector space defined by one constraint; therefore it is three-dimensional. Any matrix ![\begin{bmatrix}a & b \\  0 & c \end{bmatrix}](./images/6d0a8d7668769fa43edda9960af904ad043cffe9.png) can be written as ![a\mathbf{e}_1 + b\mathbf{e}_2+c\mathbf{e}_3](./images/73135863420c54f93fb714c1a22961577a2f3396.png).

**E6.12** Consider an arbitrary second-degree polynomial ![p(x)=a_0+a_1x+a_2x^2](./images/5133486d3d1c43fa04982355db156ac74799b044.png). We can rewrite it as

![\begin{align*}
p(x) 	&= a_0+a_1[(x-1)+1]+a_2[(x-1)+1]^2				\\
&= a_0+a_1(x-1)+a_1+a_2[(x-1)^2+2(x-1)+1]		\\
&= (a_0+a_1+a_2)1+(a_1+2a_2)(x-1)+a_2(x-1)^2.
\end{align*}](../Images/e24c8f9df6142537eafbacf0bdc535e71aa29325.png)

Since we’ve expressed an arbitrary polynomial of degree two in the desired form, the answer is yes. In other words, ![\{ 1, x-1, (x-1)^2\}](./images/c9769f0c019d694a47fec453e3a1913ee03da294.png) is a basis for the vector space of polynomials of degree at most two.

**E6.13** First we compute ![\langle \mathbf{e}_1, \mathbf{e}_2 \rangle = 0](./images/b292f55a773bf3aae5c8bc75ae9ec00731c13480.png), ![\langle \mathbf{e}_1, \mathbf{e}_3 \rangle = 0](./images/3cb976c3118233fb83921a38810401d324ba79c8.png), and ![\langle \mathbf{e}_2, \mathbf{e}_3 \rangle = 0](./images/e3ccfbe763f0720987d488a3d565fc89f83948e1.png) to show the vectors of the basis are orthogonal. Then compute ![\langle \mathbf{e}_1, \mathbf{e}_1 \rangle = 1](./images/1fe630abebce74922798c1226e04098d9a35ef6e.png), ![\langle \mathbf{e}_2, \mathbf{e}_2 \rangle = 1](./images/d4db72967c6577b771966939b447f55f5ee42529.png), and ![\langle \mathbf{e}_3, \mathbf{e}_3 \rangle = 1](./images/31c63fb6c53d8ca987d9504b484b6b2ecdf5df5f.png) to show the vectors have norm one. The set ![\big\{ \mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3\big\}](./images/e32d83c35985761919c7e8676a4becb23a2e606e.png) is orthonormal.

**E6.15** The exercise does not require us to normalize the vectors, so we can leave the first vector as-is: ![\vec{v}_1=\vec{e}_1=(4,2)](./images/288b12690c3e0444ce7fbdbd7dc831cf3037e2fd.png). Next, we calculate ![\vec{e}_2](./images/264af0eea6be5b6ec5e7421ad813f442548174a0.png) using the formula ![\vec{e}_2 = \vec{v}_2 - \Pi_{\vec{e}_1}\!(\vec{v}_2)](./images/f72bd90c2d59cf0b38fe94494a769470223c2e79.png), which corresponds to removing the component of ![\vec{v}_2](./images/65b10c95bdff2bcc3058df8e5d95333772f5523c.png) that lies in the direction of ![\vec{e}_1](./images/9b972dff65be429ce1c6b2af34b363348b06a70f.png). Using the projection formula we obtain ![\Pi_{\vec{e}_1}\!(\vec{v}_2) = \frac{ (4,2) \cdot (1,3) }{ \| (4,2) \|^2 }(4,2) = \frac{4+6}{16 + 4}(4,2) =\frac{1}{2}(4,2)=(2,1)](./images/7599f09d8467e07a973ffd2b5bdace8ec1ff06e8.png). Thus ![\vec{e}_2 = \vec{v}_2 - \Pi_{\vec{e}_1}\!(\vec{v}_2) =  (1,3) - (2,1) = (-1,2)](./images/515cff20c9a4c52fbdb67b2e3ea49693ac6adb93.png). Verify that ![\vec{e}_1 \cdot \vec{e}_2 = 0](./images/40868f44a88cae0974b55424ddfe5d384a179e0d.png).

**E6.17** We’re given the functions ![\mathbf{f}_1=1](./images/60debaf4f15cc79a6168559ddc3db8b419be4af4.png), ![\mathbf{f}_2=x](./images/9616927529e2219594ad28b70c26c2a9289483b2.png), and ![\mathbf{f}_3=x^2](./images/e8e6fea220c58b6332fa9aaf7105b09df0bd58ec.png) and we want to transform them into an orthonormal set ![\{\hat{\mathbf{e}}_1, \hat{\mathbf{e}}_2, \hat{\mathbf{e}}_3\}](./images/36e2cf3c9ac8fbb9f4ec10fa28b1703d7ea88311.png). Since ![\|\mathbf{f}_1\|=1](./images/e797b449eac6adae8c23e58b63aadefbe605c8e6.png), we set ![\hat{\mathbf{e}}_1=\mathbf{f}_1](./images/4343cb03c20744d7c3d3e55238eaaf18a5b696ac.png). Next we find ![\mathbf{e}_2=\mathbf{f}_2 - \langle \mathbf{f}_2, \hat{\mathbf{e}}_1 \rangle \hat{\mathbf{e}}_1 = x-\frac{1}{2}](./images/ea41f8eb3bd083c2cc0cffa8c3bbdfeba202d252.png). After normalization we obtain ![\hat{\mathbf{e}}_2 = \sqrt{12}(x-\frac{1}{2})](./images/b80bf678afdc17f3e29f2ee2e355306643a492b2.png). Continuing with the Gram–Schmidt procedure, we compute ![\mathbf{e}_3
=\mathbf{f}_3
- \langle \mathbf{f}_3, \hat{\mathbf{e}}_1 \rangle \hat{\mathbf{e}}_1
- \langle \mathbf{f}_3, \hat{\mathbf{e}}_2 \rangle \hat{\mathbf{e}}_2
= x^2-\frac{1}{3}-\frac{\sqrt{3}}{6}\sqrt{12}(x-\frac{1}{2})](./images/3257469b64d8b82546838a17877c2dadef7e8aa1.png) and find ![\hat{\mathbf{e}}_3=6\sqrt{5}(x^2-x+\frac{1}{6})](./images/72c9c0894baa647d3959318116ce2d14211bca74.png).

**E6.20** The characteristic polynomial is ![p_B(\lambda)=
\begin{vmatrix}
-2-\lambda  &-1  \\
5     &2-\lambda
\end{vmatrix}=\lambda^2+1](./images/6e1da0c923316f8a71c386667adbbfe355475013.png). The roots of the characteristic polynomial are ![\lambda_1=i](./images/9d8b416307c94303fd92c0afa0dcc30d8d167157.png) and ![\lambda_2=-i](./images/e493517c151442eac24e4a6c30b46b1568f8d3ab.png). To find the eigenvector associated with the eigenvalue ![\lambda_1=i](./images/9d8b416307c94303fd92c0afa0dcc30d8d167157.png), we calculate ![\mathcal{N}(B-i\mathbbm{1})](./images/3000878caa10f8170acd05041a4cfa9d2e4b4168.png). We obtain the eigenvector ![\vec{e}_1 = (-\frac{1}{2+i}, 1)^\sfT](./images/deae1211d1d85227d168aac6f49f750dae31bb13.png). Similarly we calculate ![\mathcal{N}(B+i\mathbbm{1})](./images/2ef9bf9d9c6389bbdd2f61f29de2f2f4491b8a8a.png) and find ![\vec{e}_2 = (-\frac{1}{2-i}, 1)^\sfT](./images/6f47fd274d57cfca8e2e9b646d3d552ce6e3a43a.png), which is the eigenvector associated with ![\lambda_2=-i](./images/e493517c151442eac24e4a6c30b46b1568f8d3ab.png).

**E6.21** First we find the inverse change of basis ![\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{F}}](../Images/0c7e1f43343a5eb3b4f8bc2d5d70c7cc7178e723.png) with columns that are the vectors of the Fourier basis ![F](./images/dc25194d69d5c268f6302992b9c956308163dc79.png). We then compute its inverse to find ![\tensor[_{F}]{\left[\mathbbm{1}\right]}{_{B}}
= \left(\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{F}}\right)^{-1}
=\frac{1}{4}\begin{bmatrix}1 & 1 & 1 & 1\\1 & i & -1 & - i\\1 & -1 & 1 & -1\\1 & - i & -1 & i\end{bmatrix}](../Images/f80d167b86a616ca751cd49887c254e7668133bb.png).

**E6.22** A matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is Hermitian if it satisfies ![A^\dagger = A](./images/7928596eb63dee0bd4b24728c876e1238d80cd0a.png), which is not the case for the given matrix.

### Answers to problems

**P6.1**

1.  ![\lambda_1 = 6](./images/8f66536e08389859205c46fb12158c517c574236.png), ![\lambda_2 = -1](./images/cef3f79b03d4a080c911cd1bdbb2d9306404498d.png);
2.  ![\lambda_1 = -2](./images/ee6860e64676031a57a73a06384526914da75243.png), ![\lambda_2 = 2](./images/e000d904c6e9d84257acd9db72e7700357d58296.png), ![\lambda_3 = 0](./images/703ecd68fbeab6a915bdc5c0bdefc9acf6596550.png).

**P6.2**

1.  ![\lambda_1=5](./images/5856d0b77ca309a7484b70cd890f83d0beaa47f7.png), ![\lambda_2=4](./images/e03f663ee22c6a85a753b05fbc70de70c5237aa7.png);
2.  ![\lambda_1=\frac{1}{2}(5+\sqrt(5))](./images/a70765e1a6a24fcc487c92c2030ea757143e688b.png), ![\lambda_2=\frac{1}{2}(5-\sqrt(5))](./images/e075d7ceaed510ead7797b696c81e28e1fe0ccfc.png);
3.  ![\lambda_1=3](./images/da9a0b785e295e436aa5902219c81fabb371ac7e.png), ![\lambda_2=0](./images/1911d5522079a624378e590a7784ca187e55383a.png), ![\lambda_3=0](./images/703ecd68fbeab6a915bdc5c0bdefc9acf6596550.png);
4.  ![\lambda_1=-3](./images/90491a0780e580a62a43d350b58ccec2945d6fce.png), ![\lambda_2=-1](./images/cef3f79b03d4a080c911cd1bdbb2d9306404498d.png), ![\lambda_3=1](./images/f4ca089b58d99183d93d6e14bcb5d7b27d44e039.png).

**P6.3** ![\lambda_1 = \varphi = \frac{1+\sqrt{5}}{2}=1.6180339\ldots](./images/57a3473de9f51c6c101803382d127cce14319b5d.png); ![\lambda_2 = - \frac{1}{\varphi} = \frac{1-\sqrt{5}}{2} =-0.6180339\ldots](./images/7b1c7fe0080f0faf0e18825a60a3e374024b625a.png). **P6.4**  ![\lambda_1 = \varphi](./images/cce5dff548a5ac3f19e9aaf5b87d6e0cb097cc42.png) and ![\lambda_2 = - \frac{1}{\varphi}](./images/78915854c32113de0287d46718febaeeb6227323.png). **P6.5** ![X = Q^{-1} = \begin{bmatrix}
\frac{5 + \sqrt{5}}{10}		&	\frac{ \sqrt{5} }{5}	\\
\frac{5 - \sqrt{5}}{10}		& 	-\frac{ \sqrt{5} }{5}	
\end{bmatrix}](./images/548aed429f7c8f21c300933a4bfa64485682452b.png). **P6.6**

1.  ![\lambda_1=1](./images/c21ae39b78a77a312730247b3e13b40200f75e7e.png), ![\vec{e}_{\lambda_1} = (1,1)^\sfT](./images/b3b24b7b1f1cc62c8ac11b234ab30d13c744090f.png), ![\lambda_2=-1](./images/cef3f79b03d4a080c911cd1bdbb2d9306404498d.png), ![\vec{e}_{\lambda_2} = (1,-1)^\sfT](./images/7551e13a6befd32852847cdf19221dbb5355ecef.png);
2.  ![\lambda_1=3](./images/da9a0b785e295e436aa5902219c81fabb371ac7e.png), ![\vec{e}_{\lambda_1} = (1,3,9)^\sfT](./images/37bd7050fe51548f8a539123ece89644ed585311.png), ![\lambda_2=2](./images/e000d904c6e9d84257acd9db72e7700357d58296.png), ![\vec{e}_{\lambda_2} = (1,2,4)^\sfT](./images/81a87cf38843f82d40741797300ce56b637d1dc7.png), ![\lambda_3=-1](./images/31137a3a674e1cecef8f310ba6122705e67f099c.png), ![\vec{e}_{\lambda_3} = (1,-1,1)^\sfT](./images/61c1833351706d4a40474fed137481ef98528c95.png).

**P6.7** ![A^{10}=\begin{bmatrix}
2 &	2	\\
5 & \, -1	
\end{bmatrix}^{10}
=
\begin{bmatrix}
765854 & \, 282722 \\
706805 & \, 341771
\end{bmatrix}](./images/b793126d7debf43cc9e9624f5e58ab08b7731110.png). **P6.8** ![(x_{\infty},y_{\infty},z_{\infty})^\sfT=\frac{1}{6}(x_0+4y_0+z_0,x_0+4y_0+z_0,x_0+4y_0+z_0)^\sfT](./images/6fbca308e6e6e3390ee8871e158b3d14090b17de.png). **P6.11**

1.  ![-240](./images/c6cb0fc57669ebce661c224fdac30453128ea438.png);
2.  ![900](./images/2400e3bab9ef2de905c50b5c65f59063221dcbb0.png);
3.  ![\frac{-1}{30}](./images/7074bb90e29f84d74f5042387f631fce8389d6a1.png);
4.  ![\frac{27}{2}](./images/201b30114438c807e8131bdfe60ab9157cabceff.png).

**P6.13**

1.  Yes;
2.  No;
3.  Yes.

**P6.16** Both are right. **P6.17** ![(2O)^{-1} = \frac{1}{2}O^\sfT](./images/f70c8ca91f69ca895bc7178b1dc296ad0043b17e.png). **P6.18** Yes, ![\left(P_2(t), \mathbb{R},+,\cdot\right)](./images/ec5c09f9799e9a8dfe9c1d11848359e6516dfd50.png) is a vector space. **P6.19** No. **P6.20** No. **P6.21**

1.  No;
2.  Yes;
3.  Yes.

**P6.22** ![\vec{v}=(1,0,0,1)](./images/96901de1db86eb8ebc2d583d88f28ac6de01053a.png). **P6.23** ![V=[1,0,0,1]](../Images/f1eacd481937ffa7b9b2df1ecec32dbea415f83b.png). **P6.25** The subset of ![\mathbb{R}^2](./images/95400ab39ca45e382fe8897a6d187c7836ff8db6.png) that consists of the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\- and ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png)\-axes. **P6.26** The subset of the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-axis that corresponds to the integers ![\mathbb{Z}](./images/e999cb5ac9183f0446091d02434bd37ae6e9b3bf.png). **P6.27** ![M_T = \begin{bmatrix}
0 & 0	 & 0 \\
0 & 0	 & 0 \\
0 & 0	 & 1
\end{bmatrix}](./images/fbf22c54f6ed204e55233820d270f5385f2235c9.png). Eigenvalues: ![\lambda=1](./images/e0147e4a5a8d2795eee85499d5ee1e7ae34d8f2f.png) with multiplicity one, and ![\lambda=0](./images/09add4b68320db3ffa62586834ad00abaf1ad70e.png) with multiplicity two. **P6.28** The solution space is one-dimensional and spanned by the function ![e^{-t}](./images/ce7072d032abdc2d0827c7850d45bd4254e0d189.png). **P6.29** ![\begin{bmatrix}
3 & 1 \\
-1 & 3
\end{bmatrix}](./images/987087713c95177e3e0ae156d0e353ee3323b5f9.png). **P6.30** ![D = \begin{bmatrix}
0 & 1 & 0 & 0 \\
0 & 0 & 2 & 0 \\
0 & 0 & 0 & 3 \\
0 & 0 & 0 & 0
\end{bmatrix}](./images/7bbf05bfb2d39505acba91b8b169bda2617ba79b.png). **P6.31** ![\left\{ \mathbf{e}_1 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix},
\mathbf{e}_2 = \begin{bmatrix} 0 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{bmatrix},
\mathbf{e}_3 = \begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{bmatrix} \right\}](./images/e1ab376d89d6d387eda7a03b01fcee6ce148be53.png). **P6.32** ![d=6](./images/779dfaa0de206345185720b29711883d1244679d.png). **P6.33** ![d=9](./images/086b9d651a2b24c662e6f6fc06c1689d8c09e677.png). **P6.34** ![\lambda_1=-2](./images/ee6860e64676031a57a73a06384526914da75243.png); ![\textbf{e}_1=\begin{bmatrix}-1  &0  \\1  &0\end{bmatrix}](./images/15b155475db53de0b848e9abaec543cfe0fbe448.png). ![\lambda_2=-1](./images/cef3f79b03d4a080c911cd1bdbb2d9306404498d.png); ![\textbf{e}_2=\begin{bmatrix}-2  &1  \\1  &0\end{bmatrix}](./images/096e2af40fea15530c99e635f6de0582be3e3d19.png). ![\lambda_3=1](./images/f4ca089b58d99183d93d6e14bcb5d7b27d44e039.png) (repeated); ![\textbf{e}_3=\begin{bmatrix}0  &0  \\0  &1\end{bmatrix}](./images/22e39029af351d93e9e31b0e9cb8f75d0142c749.png) and ![\textbf{e}_4= \begin{bmatrix}2  &3  \\1  &0\end{bmatrix}](./images/b800233186a5e11a544d349bbf4d08f9054531b1.png). **P6.35** ![\langle L_0(x), L_1(x) \rangle =0](./images/e0d5c916e620d0829a8487f6d7be5dbbc2db881d.png), ![\langle L_0(x), L_2(x) \rangle =0](./images/c80bac73f165b6e33e6dc5dd9bc77b3506615ae4.png), and ![\langle L_1(x), L_2(x) \rangle =0](./images/1b99d3cd0e23376ac374229e4bd4310e7930ac2c.png). **P6.36**

1.  ![9](./images/4de481be2efe2721dc600f3cf2d036cac3551beb.png);
2.  ![3](./images/b6031d121f1b4a4b138ae89b9919d5b4c8ebf35b.png);
3.  ![\sqrt{10}](./images/cab18ad47b895d2406cd093549b6a5d7fc31b572.png).

**P6.39** ![\hat{e}_1=(0,1)](./images/bf1926641ffd90024196ad3a141cbcaf401e7847.png), ![\hat{e}_2=(-1,0)](./images/e22968344489230314525d310b99c655f861d9b2.png). **P6.40** ![\hat{e}_1=(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}})](./images/98ed5a3420a404a41b6959d8d53aae1f0ebbb1b6.png), ![\hat{e}_2=(-\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}})](./images/6b7c503d5add83b0a11bb5b7c52c4dc7e67122b1.png). **P6.41** ![\hat{e}_1=(\frac{3}{\sqrt{10}},\frac{1}{\sqrt{10}})](./images/61dc22c0052bef9f7982210887e8a63b5472aba6.png), ![\hat{e}_2=(\frac{-1}{\sqrt{10}},\frac{3}{\sqrt{10}})](./images/fc486b0c0c10c42b503aea230be937c151cea569.png). **P6.42** ![\hat{\mathbf{e}}_1 = \frac{1}{\sqrt{2}}](./images/2c6334876b0db595b5c04048e56d9278e3d61ea2.png), ![\hat{\mathbf{e}}_2 = \sqrt{\frac{3}{2}}x](./images/c0a002a881e9ef18fadfaa5a9d9427ab73e35c0c.png), and ![\hat{\mathbf{e}}_3= \sqrt{\frac{5}{8}}(3x^2-1)](./images/1696c2554ef71f9b48d757729d387520cf228ecd.png). **P6.43** ![A=Q\Lambda Q^{-1}=\left[\begin{smallmatrix}
2 & 0 & -5 \\
0 & 2 & 0 \\
0 & 0 & -3
\end{smallmatrix}\right]=
\left[\begin{smallmatrix}
1 & 0 & 1 \\
0 & 1 & 0 \\
1 & 0 & 0
\end{smallmatrix}\right]
\left[\begin{smallmatrix}
-3 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 2
\end{smallmatrix}\right]
\left[\begin{smallmatrix}
0 & 0 & 1 \\
0 & 1 & 0 \\
1 & 0 & -1
\end{smallmatrix}\right]](../Images/8286f2cb308756b3ec1c1cbcad4b0bd82c4a948e.png). **P6.44**

1.  ![5](./images/f2fa057f2254981666da1b26f97fb103f09600a3.png);
2.  ![2+3i](./images/f8e8255337c2fc6f2615ac59fe4045fef5a5ef6f.png);
3.  ![2+5i](./images/9a9395b68611697494bc5175acce1d85357df575.png);
4.  ![\sqrt{26}](./images/e1c7b39d4131cef42dd68bca8c337b56b3b2f737.png).

**P6.45** ![A+B=\left[\begin{smallmatrix}
4 	& \; 2\\
8+3i 	& \; -5+3i
\end{smallmatrix}\right]](../Images/6ceaa873b697903af2f341ea7be9e02cd79361ae.png); ![CB=\left[\begin{smallmatrix}
3+8i 		& \; 2-i			\\
45+3i 	& \; -33+31i 		\\
16-4i 	& \; 16+8i
\end{smallmatrix}\right]](../Images/8958d84eef5b8765d8b35dc85862a6acb0d8214b.png); ![(2+i)B=\left[\begin{smallmatrix}
5 	& 8-i\\
9+7i & -15+5i
\end{smallmatrix}\right]](../Images/791f455e1fe5ed4ccf19d920d2fd6d43685aaa6b.png). **P6.46**

1.   ![\lambda_1=2+i](./images/0ea19d90b87785d466a5cbbaef024d3d053f85f6.png) and ![\lambda_2=2-i](./images/981fb325f53262d211d30ba6b855c5dc3a061ab9.png);
2.   ![\lambda_1=3\sqrt{3}i](./images/3bbc534c92e7e242ab1cead50b57e2439d5e91da.png) and ![\lambda_2=3\sqrt{3}i](./images/5053dc9f0e7c6d2b1bf317f354465c38c180d3f4.png);
3.   ![\lambda_1=2+8i](./images/8fea4afb5339301a39b79050b98c91b619e28fed.png) and ![\lambda_2=2-8i](./images/27c7eb76f3249c2707308295541efc6927d628d8.png).

**P6.47** ![Q=\begin{bmatrix}
-1+i 	& \; 1+i	\\
2 	& 	2
\end{bmatrix}](./images/56fe7ac32d23cb10365536175d5279e6e5f92552.png), ![\Lambda=\begin{bmatrix}
0 & 0\\
0 & 2
\end{bmatrix}](./images/8a35869ba59e6e235f1502e07d28a60daf98788b.png). **P6.53**

1.  Yes;
2.  No;
3.  Yes;
4.  No;
5.  Yes;
6.  Yes.

### Solutions to selected problems

**P6.3** To find the eigenvalues of the matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) we must find the roots of its characteristic polynomial:

![p(\lambda)
= \det(A - \lambda \mathbbm{1})
= \det\left(
\begin{bmatrix}
1 & 1 \\
1 & 0
\end{bmatrix}
-
\begin{bmatrix}
\lambda & 0 \\
0 & \lambda
\end{bmatrix}
\right)
= \det\left(
\begin{bmatrix}
1 - \lambda & 1 \\
1 & -\lambda
\end{bmatrix}
\right).](./images/c4779effcfa8b1422d7f1ee5e1296cd45f2cff3f.png)

Using the determinant formula ![\det\left(\begin{bmatrix} a & b \\ c & d \end{bmatrix}\right)=ad-bc](./images/bbf247be48e3f3100b181383467126d5165ac7fa.png), we find the characteristic polynomial of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is ![p(\lambda)  =\lambda^2 -\lambda -1](./images/ee5c6b47c136f6fa1d01dbf372179b849d81ea59.png). The eigenvalues of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) are the roots ![\lambda_1](./images/f35b707e7ea2f140dc8864eee509396242b7c977.png) and ![\lambda_2](./images/9ede4a5f2e6e4ed32db0d9e911d1309bffce61e1.png) of this equation, which we can find using the formula for solving quadratic equations we saw in[Section 1.6](./Chapter 1_ Math fundamentals.md) (see page 1.6.1).

**P6.4** The vector ![\vec{e}_1](./images/9b972dff65be429ce1c6b2af34b363348b06a70f.png) is an eigenvector of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) because ![A\vec{e}_1 =
\begin{bmatrix}
1 & 1 		\\
1 & 0
\end{bmatrix}
\begin{bmatrix}
1  			\\
\frac{1}{\varphi}
\end{bmatrix}			
=
\begin{bmatrix}
1 + 	\frac{1}{\varphi}	\\
1
\end{bmatrix}](./images/9ea1f07030d2844ebed7af97880c3cf58f1d34f5.png). Now observe the following interesting fact: ![\frac{1}{\varphi}(1 + 	\frac{1}{\varphi}) = \frac{1}{\varphi} + \frac{1}{\varphi^2} = \frac{\varphi + 1}{\varphi^2}=1](./images/a1b035cf55033f51368b9b92ae738a745da46e65.png). This means we can write ![A\vec{e}_1 =
\begin{bmatrix}
1 & 1 		\\
1 & 0
\end{bmatrix}
\begin{bmatrix}
1  			\\
\frac{1}{\varphi}
\end{bmatrix}			
=
\varphi
\begin{bmatrix}
1	\\
\frac{1}{\varphi}
\end{bmatrix}](./images/0a05b0debd7c197ba41113e92b4e6ad47c999a01.png), which shows that ![\vec{e}_1](./images/9b972dff65be429ce1c6b2af34b363348b06a70f.png) is an eigenvector of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) and it corresponds to eigenvalue ![\lambda_1 = \varphi](./images/cce5dff548a5ac3f19e9aaf5b87d6e0cb097cc42.png). Similar reasoning shows ![A\vec{e}_2 = - \frac{1}{\varphi} \vec{e}_2](./images/5b894828b8aba5af1576da75bf41254f327e4a73.png) so ![\vec{e}_2](./images/264af0eea6be5b6ec5e7421ad813f442548174a0.png) is an eigenvector of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) that corresponds to eigenvalue ![\lambda_2 = - \frac{1}{\varphi}](./images/78915854c32113de0287d46718febaeeb6227323.png).

**P6.5** The eigendecomposition of matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is ![A=Q\Lambda Q^{-1}](./images/ee5d6e83ebf09408beffeecb5fefe26f016470fd.png). The unknown matrix ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png) is the inverse matrix of the matrix ![Q=\begin{bmatrix}
1 				& 	1 \\
\frac{1}{\varphi} 	& 	-\varphi
\end{bmatrix}
=\begin{bmatrix}
1 				&  \, 1 \\
\frac{2}{1+\sqrt{5}} 	&  \,	-\frac{1+\sqrt{5}}{2}
\end{bmatrix}](./images/0fd81f1e84b6fb27b655311ca77ea3aa22ecfd72.png). To find ![Q^{-1}](./images/4fc0a1dfa3850f833c942fd6c651e964bd121f1d.png) we can start from the array ![[\;Q\; | \; \mathbbm{1}\:\; ]](../Images/e8ee30adc83aaf01abe68e7f1f1c14c210c30b11.png) and perform row operations until we obtain ![[\; \mathbbm{1}\:\; | \;Q^{-1}\; ]](../Images/d1183cc2c57e5741cfc9f579a11a875207b084e8.png).

**P6.6** First we obtain the characteristic polynomial ![p_A(\lambda)=\begin{vmatrix}-\lambda 	& 1 \\ 1 & -\lambda \end{vmatrix}=\lambda^2-1](./images/261b63119762ecaa90a67ed45cb4af823be45ead.png). The eigenvalues of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) are ![\lambda_1=1](./images/c21ae39b78a77a312730247b3e13b40200f75e7e.png) and ![\lambda_2=-1](./images/cef3f79b03d4a080c911cd1bdbb2d9306404498d.png). To find the eigenvector that corresponds to ![\lambda_1=1](./images/c21ae39b78a77a312730247b3e13b40200f75e7e.png), we must solve the null space problem ![(A-\mathbbm{1})\vec{v} = \vec{0}](./images/af0afa66cce2b718ed99cabef75f36952dc9d413.png). We start from ![(A-\mathbbm{1}) = \begin{bmatrix} -1 & 1 \\ 1 & -1 \end{bmatrix}](./images/295f8aacdfac431815bc089b1c7912ad04940b91.png) and after two row operations find the reduced row echelon form ![\begin{bmatrix} 1 & -1 \\ 0 & 0 \end{bmatrix}](./images/b83196d7de42f916a30f899d39fbac755836f0ab.png). The second column is a free variable, which we’ll call ![s](./images/b2ed2336a0f1bedf9435fa07a7b1b918cc6f4a91.png), and we find the solution to the null space problem is ![\begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} s \\ s \end{bmatrix}](./images/efa78c8bfffe0fb8a5227b87c8b1332446efd57f.png). The ![\lambda=1](./images/e0147e4a5a8d2795eee85499d5ee1e7ae34d8f2f.png) eigenspace is spanned by the eigenvector ![\vec{e}_{\lambda_1}=(1,1)^\sfT](./images/b3b24b7b1f1cc62c8ac11b234ab30d13c744090f.png). The procedure for finding the ![\lambda_2](./images/9ede4a5f2e6e4ed32db0d9e911d1309bffce61e1.png) eigenvector is similar.

**P6.7** First we decompose ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) as the product of three matrices ![A=Q\Lambda Q^{-1}](./images/ee5d6e83ebf09408beffeecb5fefe26f016470fd.png), where ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png) is a matrix of eigenvectors, and ![\Lambda](./images/c82ec11bd6d5d07101c37fc87040104e616ef994.png) contains the eigenvalues of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png). ![A=\begin{bmatrix}
2 &	2	\\
5 & -1	
\end{bmatrix}
\; = \; \;
\begin{bmatrix}
-2 & 1\\
5 & 1
\end{bmatrix}
\begin{bmatrix}
-3 & 0	\\
0 & 4
\end{bmatrix}
\begin{bmatrix}
-1/7 	& 	1/7 \\
5/7		& 	2/7
\end{bmatrix}](./images/6e028a5fdd47a011e103d716c1cb8f4436b90da2.png). Since the matrix ![\Lambda](./images/c82ec11bd6d5d07101c37fc87040104e616ef994.png) is diagonal, we can compute its 10th power: ![\Lambda^{10}=\begin{bmatrix}
59049 & 0\\
0 & 1048576
\end{bmatrix}](./images/61ee26fb9f220d014568fb8481acb615edf8a19a.png). Thus the calculation of ![A^{10}](./images/e86c2ecd416ff89b516a396fb90cc5e30e89a61f.png) is

![A^{10}
=
\begin{bmatrix}
-2 & 1\\
5 & 1
\end{bmatrix}
\begin{bmatrix}
59049 & 0\\
0 & 1048576
\end{bmatrix}
\begin{bmatrix}
\frac{-1}{7} & \frac{1}{7} \\
\frac{5}{7} & \frac{2}{7}
\end{bmatrix}
=
\begin{bmatrix}
765854 & 282722 \\
706805 & 341771
\end{bmatrix}\!.](./images/e9e9e699f05cb002ed1ddae04136fff031fdc9b8.png)

**P6.8** The eigenvalues of ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) are ![\frac{1}{4}](./images/16f97df2aae4eaf5797114583fd4e7d61a7b6cf6.png), ![\frac{1}{2}](./images/54ae72be4ad2a7c6696d4f792b4e571f46aa8216.png), and 1, and its eigendecomposition is ![M=Q\Lambda Q^{-1}](./images/de51b778c95e966f411c687692c5d7f6edbaa6c2.png). We can compute ![(x_{\infty},y_{\infty},z_{\infty})^\sfT](./images/c0ea3110fce16fcfa2feb43e8092ee93cf2f15a5.png) using ![M^\infty(x_0,y_0,z_0)^\sfT](./images/53212bd81d0e4f82d9609129fe0c30fc91495019.png). To compute ![M^\infty](./images/16237e0fcec6182658181488bc7c52e4b43399bf.png), we can compute ![\Lambda^\infty](./images/7c8c12cd50a89db2bfbe68a29eb0f58ac78ee7e6.png). The ![\frac{1}{4}](./images/16f97df2aae4eaf5797114583fd4e7d61a7b6cf6.png) and ![\frac{1}{2}](./images/54ae72be4ad2a7c6696d4f792b4e571f46aa8216.png) eigenspaces will disappear, leaving us only with the subspace of the eigenvalue 1. ![M^\infty =  Q \Lambda^\infty Q^{-1}](./images/c2d8f68e57a92195219be966149b9dd16a2f9080.png), and each row of this matrix has the form ![[\frac{1}{6},\frac{4}{6},\frac{1}{6}]](../Images/8008c6ed5a82195592547d082bd7ce4c0fb4fee9.png). See[`bit.ly/eigenex001`](./eigenex001.md) for the details.

**P6.9** The characteristic polynomial of the matrix has degree ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png), and an ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png)th\-degree polynomial has at most ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) distinct roots.

**P6.10** If ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is invertible, then ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is bijective and there is a one-to-one correspondence between every input vector ![\vec{v}](./images/51f6f8125b4ea5afb3c3c28d1fbfda9b6c44e954.png) in the domain of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) and some vector ![\vec{w}](./images/8605b88df3c2d74846ee2ea09257899f3d121a33.png) in the image space of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png). Since ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is invertible, the equation ![T(\vec{v})=\vec{0}](./images/4e4f21d9b638070d56d5c5cc553e4f1a47178305.png) is satisfied by the unique vector ![\vec{v}=\vec{0}](./images/28c39f296eeaea24a3c9b5b893d28452c948002f.png) so ![\lambda=0](./images/09add4b68320db3ffa62586834ad00abaf1ad70e.png) is not an eigenvalue of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png). To show the other direction, observe that if ![\lambda=0](./images/09add4b68320db3ffa62586834ad00abaf1ad70e.png) is an eigenvalue of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) there must exist a vector ![\vec{e} \neq 0](./images/40b67ff1a9cde19eb9d56e5168e4b77792740c04.png) such that ![T(\vec{e})=0\vec{e}=\vec{0}](./images/c391235836f1e6359124a1813bbd1b78cad68c6d.png). Since ![S(\vec{0})=\vec{0}](./images/926b83250c387f78e5ed7968d1e70f941daee1e2.png) for all linear maps, it is impossible to construct a map ![S](./images/8436a085cdcd39ca21b9cf6890036abf2ac6ac09.png) that can take ![\vec{0}](./images/3c2017d0fa03308a6cac648f9d227f12ece75450.png) to ![\vec{e}](./images/d9a2db1574f78504eeeeac0c899806b2deffc5be.png) as required for the inverse of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png). Therefore ![T^{-1}](./images/9fd7beaf91b46b9ffd91dc8143ddda2350d6c878.png) doesn’t exist.

**P6.11** Use the facts that ![\textrm{Tr}(A)=\lambda_1+\lambda_2+\lambda_3](./images/ca240d752eaa073aa09bd6084b8e9d8b1ff1bbe3.png) and ![\det(A)=\lambda_1\lambda_2\lambda_3](./images/a206952dbc75351999639da42cdc041642e4af02.png), and the properties of trace and determinant (page 2.3.9) to compute the expressions.

**P6.12** If ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is a diagonal matrix, we have ![A_{ij} =0=A_{ji}](./images/53c753bc258c72eaed072eb8523abb1b6c74758d.png) when ![i\ne j](./images/dbdc7c186307fc994a844ca98936145c90a87291.png). Therefore diagonal matrices are symmetric.

**P6.13** To check whether the matrix is orthogonal, check whether the transpose of the matrix is its inverse so that ![O^\sfT O=\mathbbm{1}](./images/a0c4044087734be6c5f842f55f29ee4c8cfa7c35.png).

**P6.14** If ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) is normal, we can write it as ![M=O\Lambda O^\sfT](./images/d6afa19b3817c0641631d68cfa08a3ff416eddb1.png), where ![O](./images/1740c06abfeb9f9ff2f4f2956420de0c4ad2963a.png) is orthogonal and ![\Lambda](./images/c82ec11bd6d5d07101c37fc87040104e616ef994.png) is diagonal. Compute ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) raised to the power ![k](./images/bd8c78013f1a4c5cfa999dd9c4c7a09100df8aab.png) as follows: ![M^k=
O\Lambda O^\sfT
O\Lambda O^\sfT
\cdots
O\Lambda O^\sfT
=
O\Lambda^k O^\sfT](./images/ea2d5496e9ba5f227b0b9de1a0f00df9fc88b637.png), since the inner ![O](./images/1740c06abfeb9f9ff2f4f2956420de0c4ad2963a.png)s cancel with the ![O^\sfT](./images/2e9fff8e985671d4bf4c7ec3266cd7bd2cc19504.png)s. We see ![\mathcal{C}(M) = \mathcal{C}(O)=\mathcal{C}(M^k)](./images/e7c3f8588a90849aeb0c1309d5771ed5e8c075fa.png) and ![\mathcal{N}(M) = \mathcal{N}(O^\sfT)=\mathcal{N}(M^k)](./images/fc63eea0d87fd25af4b1a4333b767fffa734e006.png).

**P6.15** Show this directly: ![\vec{u}^\sfT(A + B)\vec{u}=\vec{u}^\sfT A\vec{u} + \vec{u}^\sfT B\vec{u} \geq 0](./images/fc757af434d5d8be39de837e0b75fd1a78d9ec26.png), for all ![\vec{u}](./images/48518337ac6cf70bf0d29c426f5f9fdea5fcc299.png).

**P6.16** An orthogonal matrix ![O](./images/1740c06abfeb9f9ff2f4f2956420de0c4ad2963a.png) satisfies both ![O^\sfT\! O=\mathbbm{1}](./images/c22e0e0ad9e988216ee7268fdd2c2f32bb43ee5a.png) and ![OO^\sfT=\mathbbm{1}](./images/758a16f45f9f3705e87e2789e710b30bde755fbd.png).

**P6.17** We’re looking for a matrix ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) such that ![B2O=\mathbbm{1}](./images/e6378ae2eda657b424566350ce80e42e0f5081fd.png). Since ![O](./images/1740c06abfeb9f9ff2f4f2956420de0c4ad2963a.png) is orthogonal, we know ![OO^\sfT = O^\sfT O = \mathbbm{1}](./images/b8ed64fc09d2fc7ade35a8a8dedc3a10a7bb6dca.png), so the inverse matrix ![B](./images/e161e68c276672f9f727b5d5488a9687092484cb.png) is ![\frac{1}{2}O^\sfT](./images/f0836d9dcb02cadb1c8ca27d274d8690d0cc9e1a.png).

**P6.18** This isn’t a difficult question; you just need to go through the motions.

**P6.19** A vector space would obey ![0 \cdot (a_1, a_2) = (0,0)](./images/4ed30c54e9b98459b85030e84a4f02f93b0668df.png) (the zero vector), but we have ![0 \cdot (a_1, a_2)=(0, a_2) \neq (0,0)](./images/c5e50f76aba1dfc0f49b3e688f56c6c83cba6544.png), so ![(V,\mathbb{R},+,\cdot)](./images/1a6e1948647b730c9437cf77c7c4305cbc0bce66.png) is not a vector space.

**P6.20** The vector addition operation is not associative: we have ![((a_1,a_2)+(b_1,b_2))+(c_1,c_2)=(a_1 +2b_1 +2c_1,a_2 +3b_2 +3c_2)](./images/300328c0ef2b3a22c87d9e882b3cfee078908c31.png) but ![(a_1,a_2)+((b_1,b_2)+(c_1,c_2))=(a_1 +2b_1 +4c_1,a_2 +3b_2 +9c_2)](./images/5eee95ca87223623add16d0cd69b3c5e6d6a738c.png).

**P6.21** A subspace of ![\mathbb{R}^3](./images/6047322f301984173459071b7901f02d92091539.png) must be closed under addition and scalar multiplication, and must contain the zero element.

**P6.24** Start with two arbitrary elements of ![P_2(t)](./images/a3a24fcb05393985cc24f6fc43e0b7c8cfe6c93a.png)—like ![\mathbf{p} = a_0 + a_1t + a_2t^2](./images/f01a35543e96607788ebcdf928e58b778a3880e6.png) and ![\mathbf{q}=b_0 + b_1t + b_2t^2](./images/6181fc2514d5476ccb73d42395f595a74abeee64.png)— and show that ![P_2(t)](./images/a3a24fcb05393985cc24f6fc43e0b7c8cfe6c93a.png) is closed under addition and scalar multiplication.

**P6.25** Consider the union of the points of the ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-axis and the ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png)\-axis. Computing the sum of vectors taken from different axes results in a vector between the axes, which exists outside the subset. Therefore, the subset is not closed under addition, and is therefore not a vector subspace.

**P6.26** The integers are closed under addition: ![m+n \in \mathbb{Z}](./images/69d65593cd87e229b8c62bc58b562b62aa7bbb35.png) for all ![m,n  \in \mathbb{Z}](./images/641b8ab38788d160ebf07d73acfdf0e7aca4d2d8.png). However, choosing a non-integer scale factor ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png) will result in ![\alpha m \notin \mathbb{Z}](./images/dbc3574cf312ac043dc25d38febc0b7626f4d3ce.png).

**P6.27** Given an arbitrary input ![\vec{v} = v_0 + v_1x + v_2x^2](./images/13bc3c8ec78584504d375a7ed82b4603d4abff4c.png), the effect of ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png) is to select the quadratic term, so it corresponds to a projection matrix onto the third dimension. The eigenvalue ![\lambda=1](./images/e0147e4a5a8d2795eee85499d5ee1e7ae34d8f2f.png) corresponds to the subspace spanned by ![(0,0,1)](./images/ab463cdeea40b18339c2010619c8b3ff716061bb.png). The eigenvalue ![\lambda=0](./images/09add4b68320db3ffa62586834ad00abaf1ad70e.png) corresponds to the two-dimensional subspace spanned by ![(1,0,0)](./images/593ea2bff8593eab66c6e688b53cf5ebe7274cd4.png) and ![(0,1,0)](./images/c49791f7b0488ef341f16647ca53a7a3a097fd81.png).

**P6.28** The solutions to the differential equation ![f'(t) +f(t)=0](./images/31c2a6e93f91c7b53068192f025ec0c28f264e38.png) are of the form ![f(t)=Ce^{-t}](./images/264115484bf049a38dbfe1d677e238742e65e21d.png), where ![C](./images/065ab9cd044c1baf86d3f71f315ae372c8c50a0b.png) is an arbitrary constant. Since any solution in the _solution space_ can be written as a multiple of the function ![e^{-t}](./images/ce7072d032abdc2d0827c7850d45bd4254e0d189.png), we say the solution space is _spanned_ by ![e^{-t}](./images/ce7072d032abdc2d0827c7850d45bd4254e0d189.png). Since one function is sufficient to span the solution space, the solution space is one-dimensional.

**P6.29** We apply ![L](./images/767c126073d24e4524f0b90b80e9579b9c16b1db.png) to both ![e^{2x}\cos x](./images/47d62406b6221238822589eb62c20c6c5328674e.png) and ![e^{2x}\sin x](./images/f94194857ad1051a2de89f4cdd0ebf27ab96fd73.png) to obtain

![\begin{align*}
L(e^{2x}\cos x)  &= 2e^{2x}\cos x-e^{2x}\sin x+e^{2x}\cos x = 3e^{2x}\cos x-e^{2x}\sin x	\\
L(e^{2x}\sin x) 	&= 2e^{2x}\sin x+e^{2x}\cos x+e^{2x}\sin x = e^{2x}\cos x+3e^{2x}\sin x.
\end{align*}](./images/2f1902933c2ee63c937d6ab427259fb59f8dc4a7.png)

When the input is ![e^{2x}\cos x](./images/47d62406b6221238822589eb62c20c6c5328674e.png), the output of ![L](./images/767c126073d24e4524f0b90b80e9579b9c16b1db.png) corresponds to the vector ![(3,-1)^\sfT](./images/7f44cdab67ca093038602d1a9646ae807b7023ac.png) with respect to the basis ![\{ e^{2x}\cos x, e^{2x}\sin x \}](./images/ebbefa53af2b331e81cbe7b781c5d493a98636b6.png). The second output corresponds to the vector ![(1,3)^\sfT](./images/7cc8bb709b073bbe59304f22eafeac1e99ee4a53.png) with respect to this basis. These vectors are columns of the matrix representing ![L](./images/767c126073d24e4524f0b90b80e9579b9c16b1db.png). Thus, the matrix representing ![L](./images/767c126073d24e4524f0b90b80e9579b9c16b1db.png) with respect to the given basis is ![\begin{bmatrix} 3 & 1 \\ -1 & 3\end{bmatrix}](./images/987087713c95177e3e0ae156d0e353ee3323b5f9.png).

**P6.31** First of all we must determine dimensionality of the vector space in question. The general vector space of ![3\times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) matrices has nine dimensions, but a diagonal matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) satisfies ![a_{ij}=0](./images/be5d162d2a9bc6d77f36078d02baccecee3e40f0.png) for all ![i\neq j](./images/dbdc7c186307fc994a844ca98936145c90a87291.png), which corresponds to the following six constraints: ![\{ a_{12}=0, a_{13}=0, a_{21}=0, a_{23}=0,  a_{31}=0, a_{32}=0 \}](./images/bff687fbd985a811082ab3c16c2f6b1b5fcff113.png). The space of diagonal matrices is a subspace of a nine-dimensional vector space defined by six constraints; therefore it is three-dimensional. The answer given is the standard basis. Other answers are possible: any set of three vectors that span the same space would do.

**P6.32** A matrix ![A \in \mathbb{R}^{3 \times 3}](./images/65184f899cef39087f5c49284116eee34f292105.png) is symmetric if and only if ![A^\sfT = A](./images/2ac9cf58fe6395984402ca59537161b3783c70f3.png). This means we can pick the entries on the diagonal arbitrarily, but the symmetry requirement leads to the constraints ![a_{12}=a_{21}](./images/84f904cf903e0a981ce2749332b01c2a09c44ea5.png), ![a_{13}=a_{31}](./images/6e16a758287f9557e3fe1f49ee72cd43b2ec8b0a.png), and ![a_{23}=a_{32}](./images/d337fef4718c28d01b82c98be96211abbebbcf19.png). Thus the space of ![3 \times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) symmetric matrices is six-dimensional.

**P6.33** A Hermitian matrix ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png) is a matrix with complex entries that satisfies ![H = H^\dagger](./images/566c711097bbd2c77e969e0172efecd335760713.png), or equivalently ![h_{ij} = \overline{ h_{ji}}](./images/04f40565d20b8203af87b1903ad663b704ee2082.png), for all ![i,j](./images/a3c32d69b2977957a787cf394c522482c2a3f105.png). A priori the space of ![3 \times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) matrices with complex entries is ![18](./images/a1d8e08677476ef22fc989a85d8d18f863542c95.png)\-dimensional, for the real and imaginary parts of each of the nine entries. The Hermitian property imposes the following constraints. First, diagonal entries must be real if we want ![h_{ii} = \overline{h_{ii}}](./images/70fbbf9e5818069f4621b0cda2bcc13d8d938d23.png) to be true, which introduces three constraints. Second, once we pick the real and imaginary parts of an off-diagonal entry ![a_{ij}](./images/c5ec51389709ae009371bf5faf6a13cd4f2e453e.png), we’re forced to choose ![a_{ji} = \overline{ a_{ij} }](./images/45e14f7a2274de30fbb8161f2eac9191e660aca6.png), leading to six more constraints. Thus, the vector space of ![3 \times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) Hermitian matrices is ![18-3-6=9](./images/d8e7f20ade88eec631af258adce7ff9b7b9ca2f6.png)\-dimensional.

**P6.36** **a)** Using linearity: ![\langle\vec{v}_1, 2\vec{v}_2+ 3\vec{v}_3\rangle
=2\langle\vec{v}_1,\vec{v}_2\rangle +3\langle\vec{v}_1,\vec{v}_3\rangle
=6+3=9](./images/731e9128ba97be236ed373e32b83e7dc01dd03c1.png).

**b)** Using linearity in both entries: ![\langle 2\vec{v}_1-\vec{v}_2,\vec{v}_1+\vec{v}_3\rangle
=2\langle\vec{v}_1,\vec{v}_1\rangle +2\langle\vec{v}_1,\vec{v}_3\rangle -\langle\vec{v}_2,\vec{v}_1\rangle -\langle\vec{v}_2,\vec{v}_3\rangle
=2\langle\vec{v}_1,\vec{v}_1\rangle +2\langle\vec{v}_1,\vec{v}_3\rangle -\langle\vec{v}_1,\vec{v}_2\rangle -\langle\vec{v}_2,\vec{v}_3\rangle
=2+2-3+2=3](./images/88c4e6b001b7ec028695dc0a2978be766bc2bf76.png).

**c)** We start with ![13=\langle\vec{v}_2,\vec{v}_1+\vec{v}_2\rangle=\langle\vec{v}_2,\vec{v}_1\rangle +\langle\vec{v}_2,\vec{v}_2\rangle](./images/e1db5268048ac93b18bcd836f3105dd825a62eb0.png), and since we know ![\langle\vec{v}_1,\vec{v}_2\rangle=3](./images/1d1e3be5626e9092f107170cb3e199bf86df0538.png), we obtain ![3+\Vert\vec{v}_2\Vert^2 =13](./images/1e0bf0fa3e81daf9fe4ccb193d4fa44b8542f62a.png), so ![\Vert\vec{v}_2\Vert^2=10](./images/3fe949fd55bf51481dcc641bec13ced7f5c23c5d.png) and ![\Vert\vec{v}_2\Vert=\sqrt{10}](./images/fcf7adfb41e4b3c4f02ec9e2f7b7a50e9e43e939.png).

**P6.37** If ![\mathbf{v}=\mathbf{0}](./images/4890a1dd0707b7258c6abeef6a1fcb1e69d8f4c5.png), then the inequality holds trivially. If ![\mathbf{v}\ne0](./images/1233fc6c35d02abf7a74de7a5c93610228db9751.png), we can start from the following, which holds for any ![c \in \mathbb{C}](./images/d9f87cd1b0ae55e7390669bcb6c502a37f44a45e.png):

![\begin{align*}
0 	&\le 	\langle \mathbf{u}-c\mathbf{v},\mathbf{u}-c\mathbf{v}\rangle	\\
&=	\langle \mathbf{u},\mathbf{u}-c\mathbf{v}\rangle -c\langle \mathbf{v},\mathbf{u}-c\mathbf{v}\rangle	\\
&=	\langle \mathbf{u},\mathbf{u}\rangle
-\overline{c}\langle \mathbf{u},\mathbf{v}\rangle
-c\langle \mathbf{v},\mathbf{u}\rangle
+|c|^2\langle \mathbf{v},\mathbf{v}\rangle.
\end{align*}](./images/36da46b0b3b6ae7b53c1b910b18906558f42270c.png)

This is true in particular when ![c=\frac{\langle \mathbf{u},\mathbf{v}\rangle }{\langle \mathbf{v},\mathbf{v}\rangle }](./images/9072c1d2ee9e32e20dabfc0928cae53e700558a2.png), so we continue:

![\begin{align*}
0	&\le	\langle \mathbf{u},\mathbf{u}\rangle
-\frac{\overline{\langle \mathbf{u},\mathbf{v}\rangle }\langle \mathbf{u},\mathbf{v}\rangle }{\langle \mathbf{v},\mathbf{v}\rangle }
-\frac{\langle \mathbf{u},\mathbf{v}\rangle \langle \mathbf{u},\mathbf{v}\rangle }{\langle \mathbf{v},\mathbf{v}\rangle }
+\frac{|\langle \mathbf{u},\mathbf{v}\rangle |^2\langle \mathbf{v},\mathbf{v}\rangle }{\langle \mathbf{v},\mathbf{v}\rangle ^2}	\\
0	&\le	\langle \mathbf{u},\mathbf{u}\rangle
-\frac{|\langle \mathbf{u},\mathbf{v}\rangle |^2}{\langle \mathbf{v},\mathbf{v}\rangle }
- \cancel{\frac{|\langle \mathbf{u},\mathbf{v}\rangle |^2}{\langle \mathbf{v},\mathbf{v}\rangle} }							+\cancel{\frac{|\langle \mathbf{u},\mathbf{v}\rangle |^2}{\langle \mathbf{v},\mathbf{v}\rangle} }		\\
0	&\le	\langle \mathbf{u},\mathbf{u}\rangle
-\frac{|\langle \mathbf{u},\mathbf{v}\rangle |^2}{\langle \mathbf{v},\mathbf{v}\rangle }	\\
0	&\le	\langle \mathbf{u},\mathbf{u}\rangle \langle \mathbf{v},\mathbf{v}\rangle
- |\langle \mathbf{u},\mathbf{v}\rangle |^2,
\end{align*}](./images/9a0665acb222616989e1c977c0ae5d6c4f68fe67.png)

from which we conclude ![|\langle \mathbf{u}, \mathbf{v}\rangle |^2 \leq \lVert \mathbf{u}\rVert^2 \lVert \mathbf{v}\rVert^2](./images/e229d7e3e1f51116cee8f766cdf4ec5409fb7ade.png). Taking the square root on both sides of this inequality, we obtain the statement of the Cauchy–Schwarz inequality, ![|\langle \mathbf{u}, \mathbf{v}\rangle | \leq \lVert \mathbf{u}\rVert \lVert \mathbf{v}\rVert](./images/207a8c13fa98932d40365885a1ea2f97ba3c9f7c.png).

**P6.38** We proceed using the following chain of inequalities:

![\begin{align*}
\lVert\mathbf{u}+\mathbf{v}\rVert^2
&=	\langle\mathbf{u}+\mathbf{v},\mathbf{u}+\mathbf{v}\rangle 								\\
&=	\langle \mathbf{u},\mathbf{u}\rangle +\langle \mathbf{u},\mathbf{v}\rangle
+\langle \mathbf{v},\mathbf{u}\rangle +\langle \mathbf{v},\mathbf{v}\rangle 				\\
&\le 	\lVert \mathbf{u}\rVert^2+2\langle \mathbf{u},\mathbf{v}\rangle+\lVert \mathbf{v}\rVert^2			\\
&\le 	\lVert \mathbf{u}\rVert^2+2\lVert \mathbf{u}\rVert \lVert \mathbf{v}\rVert +\lVert \mathbf{v}\rVert^2	\\
&= 	(\lVert \mathbf{u}\rVert +\lVert \mathbf{v}\rVert)^2.
\end{align*}](./images/03280cbb9c9a8b3c3ff846def7bcf26237865150.png)

Therefore we obtain the equation ![\lVert \mathbf{u}+\mathbf{v}\rVert^2  \le (\lVert \mathbf{u}\rVert +\lVert \mathbf{v}\rVert )^2](./images/778002349ae0ac4fbd51af5d6f28f917a47757eb.png), and since ![\lVert \mathbf{u}\rVert](./images/2d857e979e36bc5809b228f0d27a84d42d8b3a40.png) and ![\lVert \mathbf{v}\rVert](./images/758abc57084f9c8164b04536caf31869b42bd56e.png) are nonnegative numbers, we can take the square root on both sides of the inequality to obtain ![\lVert \mathbf{u}+\mathbf{v}\rVert  \le \lVert \mathbf{u}\rVert +\lVert \mathbf{v}\rVert](./images/44235bac22eb9ade1090777fc749b5bb4f9e6808.png).

**P6.39** This is a trick question: we don’t really need to perform the Gram–Schmidt procedure since ![\vec{v}_2](./images/65b10c95bdff2bcc3058df8e5d95333772f5523c.png) is already perpendicular to ![\vec{v}_1](./images/d33646fb26ad9d3975a25ad3c85c11f594226bce.png) and both vectors have length one.

**P6.40** We’re given the vectors ![\vec{v}_1=(1,1)](./images/89e6a59f9660b78bea7c6ad9cc1effd29ff99b00.png) and ![\vec{v}_2=(0,1)](./images/bfb936af6d3d866ae913b0a491c9b03927049072.png) and want to perform the Gram–Schmidt procedure. We pick ![\vec{e}_1=\vec{v}_1=(1,1)](./images/813f1cd06a7b6abdc2f7189b6c22d4399fb600c2.png), and after normalization we have ![\hat{e}_1=(\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}})](./images/98ed5a3420a404a41b6959d8d53aae1f0ebbb1b6.png). Next we compute ![\vec{e}_2=\vec{v}_2 - \Pi_{\hat{e}_1}(\vec{v}_2)=\vec{v}_2- (\hat{e}_1 \cdot \vec{v}_2)\hat{e}_1=(\frac{-1}{2},\frac{1}{2})](./images/da134b37efe9d1da84081720d11760f1097616b7.png). Normalizing ![\vec{e}_2](./images/264af0eea6be5b6ec5e7421ad813f442548174a0.png) we obtain ![\hat{e}_2=(-\frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}})](./images/6b7c503d5add83b0a11bb5b7c52c4dc7e67122b1.png).

**P6.41** Let ![\vec{v}_1=(3,1)](./images/4896e8ed8c3cb84f31bce862406b9437a56779a4.png) and ![\vec{v}_2=(-1,1)](./images/798d72d8aa6fc97c354d7a33bb810ab089cfb51f.png). We start by identifying ![\vec{e}_1=\vec{v}_1](./images/9ad78eb22db0a17eaa170cb686ad52d8292bdf43.png), then perform Gram–Schmidt process to find ![\vec{e}_2](./images/264af0eea6be5b6ec5e7421ad813f442548174a0.png) from ![\vec{v}_2](./images/65b10c95bdff2bcc3058df8e5d95333772f5523c.png):

![\vec{e}_2
=\vec{v}_2-\Pi_{\hat{e}_1}\!(\vec{v}_2)\hat{e}_1
=\vec{v}_2- \left( \frac{\vec{e}_1}{\|\vec{e}_1\|} \cdot \vec{v}_2\right)\!\frac{\vec{e}_1}{\|\vec{e}_1\|}
=\left(\frac{-2}{5},\frac{6}{5} \right).](./images/a48b3503cd30fe724d58adac83fd88efee1ff337.png)

Now we have two orthogonal vectors and we can normalize them to make them unit vectors. We obtain the vectors ![(\frac{3}{\sqrt{10}},\frac{1}{\sqrt{10}})](./images/8eb17a2d58892d200ffa5cc511323ffb8a91926b.png) and ![(\frac{-1}{\sqrt{10}},\frac{3}{\sqrt{10}})](./images/4175079e948fb8bd9ef3aef44900ecfe3b2752a5.png), which form an orthogonal basis.

**P6.43** First find the eigenvalues of the matrix. Then find an eigenvector for each eigenvalue and construct a matrix ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png) composed of the three eigenvectors. Compute ![Q^{-1}](./images/4fc0a1dfa3850f833c942fd6c651e964bd121f1d.png) and write the eigendecomposition as ![A=Q\Lambda Q^{-1}](./images/ee5d6e83ebf09408beffeecb5fefe26f016470fd.png).

**P6.44**

1.  ![\sqrt{3^2+4^2}=5](./images/5a7a5027d45cbcc4b4b4337e47b417715ee626cb.png).
2.  Complex conjugation changes the sign of the imaginary part: ![\overline{2-3i}=2+3i](./images/b8653fb4020182ed9dd0dcf640eb41813fddf635.png).
3.  ![3i-1+3+2i=2+5i](./images/0d9f9d51aa8b06ff01c531e2269cc52ae5684b62.png).
4.  ![|3i-4i-5|=|-5-i|=\sqrt{26}](./images/ee16fb7eaa3115590591182a2e124f9d5856facf.png).

**P6.47** The characteristic polynomial of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is ![p_A(\lambda) = \lambda^2 -2\lambda = \lambda(\lambda-2)](./images/10019e9dcdc7403cc1fdbbb19c382a3654801bb6.png), so the eigenvalues are ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png) and ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png). The eigenvector for ![\lambda=0](./images/09add4b68320db3ffa62586834ad00abaf1ad70e.png) is ![\vec{e}_{0} = (-1+i, 2)^\sfT](./images/ebbdf92fee0e64b486158ab639c485623f365d32.png). The eigenvector for ![\lambda=2](./images/16f643e689416a97fffc6d6f96ab76aec64f18c9.png) is ![\vec{e}_{2} = (1+i, 2)^\sfT](./images/78bf0425ed96e22139c716ec9bcfb1ef24383a51.png). As ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) has two one-dimensional eigenspaces, an eigenbasis is given by ![\{(-1+i, 2)^\sfT, (1+i, 2)^\sfT\}](./images/4e5c7e5564e89336903fbe764b2b2d00c73d66be.png). So ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is diagonalizable with ![Q=\begin{bmatrix}
-1+i & 1+i \\
2 & 2
\end{bmatrix}](./images/5c4bbfb217dad94f5416c6169fd8dcd0f7ec5d15.png) and ![\Lambda=\begin{bmatrix}
0 & 0\\
0 & 2
\end{bmatrix}](./images/8a35869ba59e6e235f1502e07d28a60daf98788b.png).

**P6.48** Observe ![P_2(x)](./images/b5ae3364ef8aabcbba48b6d08261711e4aeaf3c0.png) is three-dimensional; therefore, if ![B_a](./images/add37d6a9a46ad5529b6ae7b703e3cee1cd1a838.png) is a linearly independent set, then it is a basis as it has three elements. If ![a(1 +ix) +b(1 +x+ix^2) +c(1 + 2ix) = 0](./images/cf65c29cfb608bf565d43182c576d8269cfc7cc1.png) then ![(a+b+c)1 + (ia+b+ 2ic)x+ibx^2 = 0](./images/2b26d53eddfaf88e04639e55447ed6cfa7a3193f.png). But the standard basis of ![P_2(x)](./images/b5ae3364ef8aabcbba48b6d08261711e4aeaf3c0.png) is linearly independent, so we must have ![a + b + c = 0](./images/c99c723cfa2ad6bd9706e1f40394b5f94884cfab.png), ![ia + b + 2ic = 0](./images/e05ac364def5c50658fe765d2fa5413fd9708074.png), and ![ib = 0](./images/0d97cf755e8f1ad1039cf04ba135bfa5c5bd38a7.png). The last equation implies ![b = 0](./images/eafc4318049c90486bb9c0868e4c7ff280fbdcc2.png), and the first two imply both a and c are zero. As the only linear combination of distinct elements of ![B_a](./images/add37d6a9a46ad5529b6ae7b703e3cee1cd1a838.png) which sums to zero is the trivial sum, ![B_a](./images/add37d6a9a46ad5529b6ae7b703e3cee1cd1a838.png) is linearly independent.

**P6.49** Computing the determinant of ![A - \lambda \mathbbm{1}](./images/ec901271f5bd54b3e966701c248ffc7de1328c69.png), we obtain ![p_A(\lambda)=\lambda^2 - \lambda \left(a+d\right) + ad - b c](./images/1e471cf647f010db12748fe17b33abd914bb65cf.png). We obtain the condition by computing the discriminant of this quadratic equation.

**P6.50** Since ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) is normal, we can write it as ![M=U\Lambda U^\dagger](./images/bd71242a72c07bdc0ab1107e82179f97cde35115.png), where ![U](./images/af637a41bea3ed020af83373059b7121337850ba.png) is a unitary matrix and ![\Lambda](./images/c82ec11bd6d5d07101c37fc87040104e616ef994.png) is diagonal. Taking the transpose of this equation we find ![M^\dagger=(U\Lambda U^\dagger)^\dagger = U\Lambda^\dagger U^\dagger](./images/688956767721197317b0bfd11fcf55baef152dca.png). Thus, ![\mathcal{C}(M) = \mathcal{C}(U)=\mathcal{C}(M^\dagger)](./images/462a5a4b1cb256390b8fa6b7edc2f151e7c5ffd7.png).

**P6.51** If ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is Hermitian, we know ![A^\dagger = A](./images/7928596eb63dee0bd4b24728c876e1238d80cd0a.png). Now suppose ![\vec{e}](./images/d9a2db1574f78504eeeeac0c899806b2deffc5be.png) is an eigenvector of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) associated with a nonzero eigenvalue ![\lambda](./images/5024e92226f2b135df8c3d6a84c7cb3f3943c5e1.png). The eigenvalue equation is ![A\vec{e}=\lambda \vec{e}](./images/3f94e8a94c028197dabdc691c746972fdb37bf4b.png). Taking the Hermitian transpose of both sides of the eigenvalue equation, we obtain ![(A\vec{e})^\dagger = \vec{e}^{\,\dagger}\!A^\dagger = \vec{e}^{\,\dagger}\!A =\overline{\lambda}\vec{e}^{\,\dagger}](./images/7c0e599226a7bbb1e6baa78f9890632d2eadcd08.png). Now suppose we multiply the eigenvalue equation by ![\vec{e}^{\,\dagger}](./images/510c05c4bc27d42a2c8ac7175de0c218c3ae3c52.png) from the left. We obtain ![\vec{e}^{\,\dagger}\!A\vec{e}=\lambda \vec{e}^{\,\dagger}\vec{e} = \lambda \| \vec{e} \|^2](./images/1e948364015499e1251c27bcd69571398bfe4df1.png). We can also interpret the triple product ![\vec{e}^{\,\dagger}\!A\vec{e}](./images/178ce753c23429b79246c4661ef60c0c4b6b032e.png) as ![(\vec{e}^{\,\dagger}\!A)\vec{e}](./images/76481cc5284cfbc7f4b226d2af53076cb1071ed5.png). We know the expression in the brackets equals ![\overline{\lambda}\vec{e}^{\,\dagger}](./images/3bb1fa96a488959690623beb7489a3d5a0af13e8.png), and overall we have ![(\vec{e}^{\,\dagger}\!A)\vec{e} = \overline{\lambda}\vec{e}^{\,\dagger}\vec{e} = \overline{\lambda}\| \vec{e} \|^2](./images/5b76ea5ca4545afa3ff553be2b631a025dbd061f.png). We’ve thus obtained the equation ![\overline{\lambda}\| \vec{e} \|^2 = \lambda \| \vec{e} \|^2](./images/991210a0881f0ca881ad57a744f371ef075818c9.png). Since ![\| \vec{e} \|^2 \neq 0](./images/0248474f57da2a9eb44fb2e4dbf0fae3e0cb742e.png), it must be that ![\lambda = \overline{\lambda}](./images/08fd4938a2e79652289cacf54793da737f61de37.png), which means ![\lambda](./images/5024e92226f2b135df8c3d6a84c7cb3f3943c5e1.png) is real. The realness of Hermitian eigenvalues is a useful property used in quantum physics. To ensure the energy of a physical system can be expressed as a real number, physicists require that energy operators be Hermitian matrices.

**P6.52** Assume ![\vec{e}](./images/d9a2db1574f78504eeeeac0c899806b2deffc5be.png) is an eigenvector associated with a nonzero eigenvalue ![\lambda](./images/5024e92226f2b135df8c3d6a84c7cb3f3943c5e1.png) of a unitary matrix ![U](./images/af637a41bea3ed020af83373059b7121337850ba.png). The eigenvalue equation tells us ![U\vec{e}=\lambda \vec{e}](./images/60130cdc163fe54cc1de165683a7d7498ac4618e.png). Computing the squared length of both sides of this equation, we find ![\| U\vec{e} \|^2 = \vec{e}^{\,\dagger}U^\dagger U \vec{e}  = \vec{e}^{\,\dagger}\mathbbm{1}\vec{e}
= \vec{e}^{\,\dagger} \vec{e} = \|\vec{e}\|^2](./images/2b57d4b54643cd506d0d63a5b85a542c4a05adf8.png) for the left side, and ![\|\lambda \vec{e}\|^2 = \vec{e}^{\,\dagger} \overline{\lambda} \lambda \vec{e} = |\lambda|^2  \|\vec{e}\|^2](./images/cbde6caed4f00f8c819d039216f6cfa279a44489.png) for the right side. Combining these results leads us to the equation ![\|\vec{e}\|^2 = |\lambda|^2  \|\vec{e}\|^2](./images/9571fa349f2cb3e3e8a8eac09dff525d202d961f.png); and since ![\|\vec{e}\|^2 \neq 0](./images/0248474f57da2a9eb44fb2e4dbf0fae3e0cb742e.png), this means ![|\lambda|^2=1](./images/c1da75a09b67e91625ebab42a7500bffa853f388.png), which implies ![|\lambda| = 1](./images/ff381e3a0aeb6bed1cb268050e0f11579ef1c9c6.png).

**P6.53** To prove a matrix is nilpotent, you can compute its powers ![A^2](./images/42fa492c11a9b8c0880228cc9499138f0f81c9ed.png), ![A^3](./images/ac6ef51041988f3871e7bdf84c241cb53dc552b6.png), ![A^4](./images/305ce46aabeb04d63aeac588bd7d0e3f3ef76e94.png), …to see if you obtain the zero matrix. To prove a matrix is not nilpotent, you can show it has a nonzero eigenvalue.

**a)** This matrix is nilpotent because its square is the zero matrix.

**b)** The matrix is not nilpotent because its characteristic polynomial ![p(\lambda)=\lambda^{2} - 6 \lambda + 8](./images/84e28b0aaecdbdc7c93d735d970ed327c0051199.png) has a nonzero root.

**c)** This matrix is nilpotent because it squares to the zero matrix.

**d)** The matrix is not nilpotent because it has nonzero eigenvalues.

**e)** Yes; the cube of this matrix is the zero matrix.

**f)** Yes; the square of this matrix is the zero matrix.

**P6.54** The key fact we need to remember is that the eigenvectors of normal matrices form a full basis. Since ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png) is normal, it can be diagonalized: ![M=Q\Lambda Q^{-1}](./images/de51b778c95e966f411c687692c5d7f6edbaa6c2.png). The “square-root of ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png)” operator is obtained by taking the square root of the eigenvalues matrix: ![\sqrt{M}=Q\sqrt{\Lambda}Q^{-1}](./images/5056144de4c7c446dc3a94ac158670303b9b1fb4.png).

##[Chapter 7 solutions](./Front matter.md)

### Answers to exercises

**E7.1** ![4 \textrm{Al} + 3 \textrm{O}_2 \; \to\;  2 \textrm{Al}_2 \textrm{O}_3](./images/f98f077422f3523fe1936976e77355a0232b0a2f.png). **E7.2** ![\textrm{Fe}(\textrm{OH})_3 + 3 \textrm{HCl} \; \to \; \textrm{FeCl}_3 + 3 \textrm{H}_2\textrm{O}](./images/0bd3065bdc4d287a0182be6503869139f61dfb7c.png). **E7.3**  ![x_a=106.3](./images/7c65aedbec429aebaabde20196ad6c9b09d2bbae.png) tons, ![x_b = 281.2](./images/2016f589d28deedb891bff10d0807a3fb73708fe.png) tons, and ![x_c=352.8](./images/f570b92cfca28b65c74d63ea348ada220babc2a5.png) tons. **E7.4** ![+10 -R_1I_2 + 5 - R_3I_3 - 20 = 0](./images/ae3f871bcda26ad9d1ba77b49bc375cbbc769b1a.png). No, because the three KVL equations are not linearly independent. **E7.5** See solution. **E7.6**

1.  ![A = \begin{bmatrix}0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 1 & 0\end{bmatrix}](./images/5a27bdbe1a365b09cfc5023a2a1d2349d39122ba.png);
2.  ![A = \begin{bmatrix}0 & 1 & 0 \\ 0 & 1 & 1 \\ 0 & 0 & 0\end{bmatrix}](./images/413bccdb157078d22392f218b2067321263f751f.png);
3.  ![A = \begin{bmatrix}0 & 1 & 1 \\ 1 & 0 & 1 \\ 1 & 1 & 0\end{bmatrix}](./images/9d363e400b48f2b507459bb61a72a0940f5124fc.png).

**E7.7**

1.  ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png);
2.  ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png);
3.  ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png).

**E7.8** ![\lim_{n\to \infty} \frac{a_{n+1}}{a_{n}} = \lambda_1 = \varphi =\frac{1+\sqrt{5}}{2}](./images/30cc8e889ad05da5394895c4d88e950478963c14.png). **E7.9**  ![a_{N} = \frac{1}{\sqrt{5}}  	\left(	\frac{1+\sqrt{5}}{2}	\right)^N
- 	\frac{1}{\sqrt{5}}		\left(	\frac{1-\sqrt{5}}{2}	\right)^N.](./images/a177bf308c7432f6a2b9d17222aa111c333d5593.png)**E7.10** ![h(x)=0.52x](./images/2807ecb7165211ab0f00b8c052aeb0182b156855.png). **E7.11** ![y=4-x](./images/119850f7748722cf47bc6daa0103df25603ebdd1.png). **E7.12** ![S(m^*)=4704.63](./images/98d5ed6a85d68bfd1ff32bd84c34bacc0c9458f2.png). **E7.13** ![S(\vec{m}^{\prime*})=433.54](./images/96e78c8cca46c1019afe9d3d60fc8a98c4df601e.png). **E7.14** ![\vec{c} = 1100\;1111\;0100\;1110](./images/b24aa787b33c9ca7943bae21ef056766218954f5.png). **E7.15** ![\vec{c}=\vec{x}G=(1,0,1,0,1,0,1)](./images/3eb24e690029a939dbe68344e26084bb08fe43b0.png). **E7.16** ![G=\begin{bmatrix}
1 & 0 & 0 & 0 & 1\\0 & 1 & 0 & 0 & 1\\0 & 0 & 1 & 0 & 1\\0 & 0 & 0 & 1 & 1
\end{bmatrix}](./images/cf7abfdf504d55431a041393d05cd2c3556c6899.png).

### Solutions to selected exercises

**E7.3** See[`http://bit.ly/vegonomics`](./vegonomics.md) for the calculation steps.

**E7.4** This exercise shows how the abstract notion of linear independence applies to electric circuits. We must choose the KVL equations that describe the current flowing in linearly independent loops. There are three loops in the circuit from which we can obtain KVL equations: the left inner loop, the right inner loop, and the perimeter of the circuit as a whole. The KVM equation for the outer loop is a linear combination of the KVL equations of the two inner loops.

**E7.5** The KVL equation for the clockwise loop starting at junction A is ![V_1 - R_2I_2 - R_1I_1=0](./images/0c1dcdc93986a92f0887839e926bc4fe84466087.png). The KVL equation starting at B is ![-R_3I_3 + V_2 -R_4I_4+R_2I_2=0](./images/c6bbcf75f6e957cd195ed3e69218632365d84561.png). The equation for the loop starting at C is ![V_3-R_5I_5 + R_4I_4=0](./images/5e8d33e7767c8a9bc821d5e3013076c41822b4d2.png). Observe the voltage drop across ![R_2](./images/ce8ba73ef56f94f0d635c6e8f75ccf8a22cf2147.png) and ![R_4](./images/b408cd217b61bc7966539303cd8a589c04f90cf4.png) appears as gains and drops in the KVL equations. The KCL equation for junction B is ![I_1=I_2+I_3](./images/4807ff47727d3d99b9d1e61b70de16b93d921e0a.png) and that for C is ![I_3=I_4+I_5](./images/0d98b80cae06026e690cad42915796d4309f088c.png). After combining the equations and performing some simplifications, we obtain the matrix equation ![R\vec{I} = \vec{V}](./images/6f177144d57c080768d9b4e77f31486a9c5d3e34.png), where ![R=
\begin{bmatrix}
R_{1} & R_{2} & 0 & 0 & 0\\
0 & - R_{2} & R_{3} & R_{4} & 0\\
0 & 0 & 0 & - R_{4} & R_{5}\\
1 & -1 & -1 & 0 & 0\\
0 & 0 & 1 & -1 & -1
\end{bmatrix}](./images/14bcc18d00b96e518ae98943330c79aa085dae53.png).

**E7.6** The ![i](./images/48b353d891e57e944c38b22a253327079ba56c85.png)th row of the adjacency matrix contains the information about the outgoing edges for vertex ![i](./images/48b353d891e57e944c38b22a253327079ba56c85.png) in the graph. If the edge ![(i,j)](./images/c04f5423659b0636ef9b6e34200c7af58104b427.png) exists, then ![A_{ij}=1](./images/ca7306a30bedfd21aef1d2b00f9adb1d77949738.png), otherwise ![A_{ij}=0](./images/da19b0e5f4cba6dd69463e07d0877a81351ee716.png).

**E7.8** Since ![|\lambda_2| < 1](./images/d8e9bafbe33d146571d35a8e3ccea8792cbd301a.png), as ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png) increases the number ![\lambda_2^2](./images/7c549622ff979329b7516d7bd77d1dc6947f6d22.png) tends to zero, and only the effects of ![\lambda_1^n](./images/079dfc87566cbf17211afc4929959e6170633912.png) remain. The ratio ![\frac{a_{n+1}}{a_{n}}](./images/4cf8bbfda582f1375aeef3a7693fc1399d72e9e6.png) approaches ![\lambda_1](./images/f35b707e7ea2f140dc8864eee509396242b7c977.png) as ![n\to \infty](./images/e612569eeb8b103bc7a67b34e63f51de23157424.png).

**E7.9** Compute the product ![Q\Lambda^NQ^{-1}](./images/b6739d60b7b84ac144ce1919f56069306e4ef668.png) in the order ![(Q\Lambda^N)Q^{-1}](./images/d490104e244f36c08b33ba3aa2b294d8cf952a6d.png). To find ![a_N](./images/81d9d73258b0820ca10c2518190d0f90c755af53.png), we’re only interested in computing the bottom left entry of this matrix. We obtain the formula ![a_N = \frac{5 + \sqrt{5}}{10}\!\left(\frac{1+\sqrt{5}}{2}\right)^{N-1}
+ \; \frac{5 - \sqrt{5}}{10}\!\left(\frac{1-\sqrt{5}}{2}\right)^{N-1}](./images/114ecf749f6648d6c5d1c002ff7cfa4c8a7adb99.png), which simplifies to ![a_N = \frac{\varphi^N-(-\varphi)^{-N}}{\sqrt{5}}](./images/4d36c59172ac051ee49a08e650212f4554ed3da9.png).

**E7.10** The data you’re given consists of pairs ![(a_i,b_i)](./images/974245b578696f4ee8b0cd872753c1d70afa078e.png), where ![a_i](./images/c2c7a8fa49815a3dbd09a55ac0b0b91a4c1312f1.png) is the total number of flips in the trial and ![b_i](./images/a51f62ee57fdbe27169dd91cf7bbc29cdb330897.png) is the number of heads. We represent the data as a matrix of flip counts ![A \in \mathbb{R}^{5 \times 1}](./images/264b190b077acc4a9c017dd8005112e33ef95165.png) and a vector of heads counts ![\vec{b} \in \mathbb{R}^{5}](./images/50ea677d3b96e6f2d5c22e17eda27f5e79cbef1f.png). Applying the standard approach for finding the Moore–Penrose inverse, we find ![(A^{\prime\sfT} \!A^\prime)^{-1} = [\frac{1}{3520}]](../Images/732262f5798d3bef8836bb81b1b58e68f218354b.png). Next we find the least squares approximate solution to ![A\vec{m} =\vec{b}](./images/364da8876020c6a145be4d59df9585be1345a0d3.png) by computing ![\vec{m} = (A^{\prime\sfT} \!A^\prime)^{-1} A^\sfT \vec{b} = [0.52]](../Images/7b40752c3248dd74882389878d0dd714e186e184.png). The slope of the line of best fit is ![0.52](./images/09e5f9747fd803aeb5ecf269dd557816e72ac62e.png).

**E7.11** The dataset consists of a matrix of inputs ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png), ![A=(0,1,2)^\sfT](./images/b068280f76e54d3272d3ad5332d734dba9eaed94.png), and a vector of outputs ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png), ![\vec{b}=(3.9,3.2,1.9)^\sfT](./images/d66ae5e7f8f130ca40cceea7da4470d49c4e908b.png). Since we’re interested in fitting an affine model ![y=b + mx](./images/389d6078ad148f4059e8ce6cc51728f135db1de1.png), we must augment the matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) with a column of ones to obtain ![A^\prime](./images/31dd30922c41f5695d509d9ddffcea83d982a147.png), and then compute ![A^{\prime\sfT} \!A^\prime](./images/8af7b483e8a27df1782163322ba835d1e0a73133.png) and its inverse:

![A^\prime =
\begin{bmatrix}
1	&	0	\\
1	&	1	\\
1	&	2
\end{bmatrix},
\quad
A^{\prime\sfT} \!A^\prime
=
\begin{bmatrix}
3	&	3	\\
3	&	5
\end{bmatrix}
\quad
\Rightarrow
\quad
(A^{\prime\sfT} \!A^\prime)^{-1}
=
\begin{bmatrix}
\frac{5}{6} 		& - \frac{1}{2}		\\
-\frac{1}{2} 	& \frac{1}{2}
\end{bmatrix}.](./images/9ab26c4d5256a4dd4bd96b3942a2efd584343a87.png)

We can now compute the Moore–Penrose inverse ![{A^{\prime}}^+](./images/9595dec4e44f2700aada3b02f0e94288cc8a6ab6.png) and obtain the approximate solution as follows:

![{A^{\prime}}^+
=
(A^{\prime\sfT} \!A^\prime)^{-1}A^{\prime\sfT}
=
\begin{bmatrix}
\frac{5}{6} 		& \frac{1}{3} 	& - \frac{1}{6}	\\
-\frac{1}{2} 	& 0 			& \frac{1}{2}
\end{bmatrix}
\quad
\Rightarrow
\quad{A^{\prime}}^+ \vec{b}
=
\begin{bmatrix}
4		\\
-1
\end{bmatrix}.](./images/6c91a3e5851a913112b7ea03ec14766eeb09b48c.png)

Thus the best-fitting affine model for the dataset is ![y=4-x](./images/119850f7748722cf47bc6daa0103df25603ebdd1.png).

**E7.16** The procedure for encoding each four-bit message ![\vec{x}=x_1x_2x_3x_4](./images/be0bc7c20a83c58acc32ca9e2078dfcbfb4dec7e.png) into a five-bit codeword ![\vec{c}=c_1c_2c_3c_4c_5](./images/000a14550a78e95600ecf8dbbf79c05caa9bea9d.png) is as follows: set ![c_i = x_i](./images/2f59908a6b4a74324f58fbc048a1f4a7c19ee285.png) for the first four bits, and set the fifth bit to ![c_5= x_1 + x_2 + x_3 + x_4](./images/0db829a232961ae7af40d5e118cd1ba07d3319f1.png).

**E7.17** To find ![\langle \mathbf{e}_1(x), \mathbf{e}_2(x) \rangle](./images/ea62face3c1a5a3924cf0bd453a3c8cd5df0edc6.png), we must compute the integral ![\int_0^L \sin(\tfrac{\pi}{L}x) \sin(\tfrac{2\pi}{L}x) \, dx](./images/2d0bd3c394f22b8aecd92ea67b387487fb9b56d7.png). Change variables to ![y=\tfrac{\pi}{L}x](./images/adc4e7858228e33e618cdc914b122ecb910925a3.png) to simplify. The integral becomes ![\langle \mathbf{e}_1(x), \mathbf{e}_2(x) \rangle = k\int_0^\pi \sin(y)\sin(2y)\,dy](./images/3fd944dda32f8a8a021cf51bc065e3a1dd27fa0d.png), where ![k=\tfrac{L}{\pi}](./images/0b123bf9413ca3a992a70827d07e229d70da2be8.png). Using the double-angle formula, we find ![\sin(y)\sin(2y)=\sin(y)2\sin(y)\cos(y)=2\sin^2(y)\cos(y)](./images/1eba89a2b883fb3467ca460a5668af557382609f.png). Next, use the substitution ![u=\sin(y)](./images/bfa54b2092e240f98147629c46ada813e0dcbd23.png), ![du=\cos(y)dy](./images/b188a33679546501e92733c91062f6724c46b0c3.png) to obtain ![2k \int \sin^2(y)\cos(y)\,dy=2k \int u^2 du](./images/50760642475d15da065a42b3cb577ff63c8a86ad.png) ![=\frac{2k}{3}\left[ u^3 \right]=\frac{2k}{3}\sin^3(y)](../Images/12e8c519055b4293fa48a31e5b01aa96b3ad31ec.png). Finally, evaluating the expression at the endpoints, we find ![\langle \mathbf{e}_1(x), \mathbf{e}_2(x) \rangle = \frac{2k}{3}\left[\sin^3(\pi) - \sin^3(0)\right]=0](../Images/d7a1e9e4041e6fb22f54581b03b97fd2d60c7cd5.png). This confirms that ![\mathbf{e}_1(x)](./images/8b9a6b2e65c82ed544571d928fb2a39d71764af0.png) and ![\mathbf{e}_2(x)](./images/b4dc7d56011e04861b0245f4bd59c1fac1fa081a.png) are orthogonal.

**E7.18** The coefficient ![b_0](./images/2fdb35fc8b233bff2cb9a2654ca06f3e7b014074.png) corresponds to the basis function ![\sin(\tfrac{0\pi}{T}t)](./images/d345d350e5ec4e0f7c36d65d3fd3f12672da57a3.png), which is zero everywhere. Thus, the integral ![b_0 = \frac{1}{T} \int_0^T f(t) \sin(\tfrac{2\pi0}{T}t) \,dt](./images/e2a3197fa38c3825367ba5fd57b440542a8c5028.png), always produces a zero result ![b_0=0](./images/3f7147af44220994a0ccdbc661ca89a50bd2abfa.png). On the other hand, the zero-frequency ![\cos](./images/4d9047d23dbc26d89201938eb349b15300ee1647.png) function is constant—![\cos(\tfrac{2\pi0}{T}t) = 1](./images/d70bddd471dc36ba144a31853a2790524b88e9eb.png)—and the coefficient ![a_0 = \frac{1}{T} \int_0^T f(t) 1 \,dt](./images/7b3a7992863db04ee835eadcb4c4a580296584df.png) corresponds to the average value of the function ![f(t)](./images/5efd00e5bf3a607572430909c72c6a99d7761528.png) on the interval ![[0,T]](../Images/9abb3190e93dc12108b6548f31cdedda5acd924e.png).

### Answers to problems

**P7.1** ![\textrm{C}_{55}\textrm{H}_{104}\textrm{O}_6 + 78\textrm{O}_2
\; \to \;
55\textrm{C}\textrm{O}_2 + 52\textrm{H}_2\textrm{O}](./images/fc1968314c02923f59551df082023cf9e4dfe2b3.png). **P7.2** ![I_1=\frac{85}{11}\approx7.7](./images/129854c7f074ac5e1ab804f51b1cb82cd372a839.png)\[A\] and ![I_5=\frac{25}{11}\approx 2.27](./images/41f0d5864278bf2a248d818bfd04fc7c82f78c01.png)\[A\]. **P7.3** ![y=1+\frac{1}{2}x](./images/c688463c0b35d976ef9eb77cfab4251ab14f0144.png). **P7.4** ![p(x)=334 + 1.001x](./images/1bca5db7811ac27e4556ddbcf1d804ffd5ae2e80.png); ![p(700) =\$1035](./images/d202df575cf536e22f97a1366c2eaf4b7376dce0.png). **P7.5** ![q(x) = 174 + 1.69x - 0.000558x^2](./images/280076d544ff451628901e9e1364b9e07c4cd4f4.png); ![q(700)=\$1084](./images/358427533d3706d130efa0fae12f1d0ef898c95e.png). **P7.7**

1.  ![A = \begin{bmatrix}
    0 & 1 & 0 & 0 & 1 \\
    1 & 0 & 1 & 1 & 0 \\
    0 & 1 & 0 & 1 & 0 \\
    0 & 0 & 1 & 0 & 1 \\
    1 & 0 & 0 & 1 & 0
    \end{bmatrix}](./images/613533890252f227a4e002f2f475c8836731e761.png);
2.  ![A = \begin{bmatrix}
    0 & 1 & 0 & 0 & 1 \\
    0 & 0 & 1 & 0 & 1 \\
    0 & 0 & 0 & 1 & 1 \\
    1 & 0 & 0 & 0 & 1 \\
    0 & 0 & 0 & 0 & 0
    \end{bmatrix}](./images/60ed2feb3d703be69cfb29d17689920e2400e18d.png);
3.  ![A = \begin{bmatrix}
    0 & 1 & 1 & 1 & 1 \\
    1 & 0 & 1 & 0 & 0 \\
    0 & 1 & 0 & 1 & 0 \\
    0 & 0 & 1 & 0 & 1 \\
    1 & 0 & 0 & 1 & 0
    \end{bmatrix}](./images/9ada3bab91694cbb971ad76e49228e171e005572.png).

**P7.8**

1.  ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png);
2.  ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png);
3.  ![3](./images/b6031d121f1b4a4b138ae89b9919d5b4c8ebf35b.png).

**P7.9**

1.  ![graph_inverse_problem_a](./images/graph_inverse_problem_a.png);
2.  ![graph_inverse_problem_b](./images/graph_inverse_problem_b.png).

**P7.10**

1.  ![\begin{bmatrix}1 & 0 & 0\\  0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}](./images/6a28995be0784635796057967103aa7b0193937c.png);
2.  ![M_1 = \begin{bmatrix}0 & 1 & 0\\  1 & 0 & 0 \\ 0 & 0 & 1\end{bmatrix}](./images/ce4fefd997a2201211ec3041e17d5ba5c276d9c4.png);
3.  ![M_2 = \begin{bmatrix}1 & 0 & 0\\  0 & -1 & 0 \\ 0 & 0 & 1\end{bmatrix}](./images/0b3e84da8e217cc57f4d3685da0b1aaa1e120e4b.png);
4.  ![M_3 = \begin{bmatrix}	\cos(\frac{\pi}{3}) 	& -\sin(\frac{\pi}{3}) 	& 0\\
    \sin(\frac{\pi}{3}) 	& \cos(\frac{\pi}{3}) 	& 0 \\
    0 				& 0 				& 1\end{bmatrix}](./images/7512addd41f07b781380d9b80c18cc160be8289a.png);
5.  ![M_4 = \begin{bmatrix}	\cos(-\frac{\pi}{6}) 	& -\sin(-\frac{\pi}{6}) 	& 0\\
    \sin(-\frac{\pi}{6}) 	& \cos(-\frac{\pi}{6}) 	& 0 \\
    0 				& 0 				& 1\end{bmatrix}](./images/b9edae324eb37bec183ab66efd83a5c31bf52f81.png);
6.  ![M_5 = \begin{bmatrix}1 & \frac{1}{2} & 0\\  0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}](./images/59e105e018468467c489e825744a043ceb4eb0a9.png).

**P7.11**

1.  ![M_6 = \begin{bmatrix}1 & 0 & 1\\  0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}](./images/e57e83fb0ba4edd285e43e57c40bd50093f70664.png);
2.  ![M_7 = \begin{bmatrix}1 & 0 & 0\\  0 & 1 & 2 \\ 0 & 0 & 1\end{bmatrix}](./images/4ff94001fdd12ea87dddbd4d2a63d28b42d08717.png);
3.  ![M_8 = \begin{bmatrix}1 & 0 & 1\\  0 & 1 & 2 \\ 0 & 0 & 1\end{bmatrix}](./images/6dd61a87a9c1573b3b0ce115fcb9285950977617.png);
4.  ![M_4 = \begin{bmatrix}	\cos(-\frac{\pi}{6}) 	& -\sin(-\frac{\pi}{6}) 	& 0\\
    \sin(-\frac{\pi}{6}) 	& \cos(-\frac{\pi}{6}) 	& 0 \\
    0 				& 0 				& 1\end{bmatrix}](./images/b9edae324eb37bec183ab66efd83a5c31bf52f81.png), ![30^\circ](./images/305983de0b217ba62d42b17421a4d2daa9bddfcc.png) counter-clockwise rotation;
5.  ![M_9 = \begin{bmatrix}	\cos(-\frac{\pi}{6}) 	& -\sin(-\frac{\pi}{6}) 	& 0\\
    \sin(-\frac{\pi}{6}) 	& \cos(-\frac{\pi}{6}) 	& 2 \\
    0 				& 0 				& 1\end{bmatrix}](./images/e8894cf60955e29603ca2cff020d527ca8f15f26.png);
6.  ![M_{10} = \begin{bmatrix}	\cos(-\frac{\pi}{6}) 	&\;  -\sin(-\frac{\pi}{6})		& \; -2\sin(-\frac{\pi}{6})\\
    \sin(-\frac{\pi}{6}) 	&\;  \cos(-\frac{\pi}{6})		& \; 2\cos(-\frac{\pi}{6})\\
    0 				&\;  0 					& \; 1\end{bmatrix}](./images/1923152c68c4ef1092fdbce555767ef41e65f495.png).

**P7.12** ![P=\begin{bmatrix}1 & 0 & 0\\ 0 & 1 & 0\\1 & \frac{1}{2} & 0\end{bmatrix}](./images/ebf263cba1a2161255b5db5804db82552e20ea30.png); ![p^\prime=(\frac{2}{5},\frac{6}{5})](./images/85bac78c8030779999f7995e20decf8b8ac44596.png) and ![q^\prime=(\frac{3}{4}, \frac{1}{2})](./images/abc8c98fb5a38a89b6dce47b139371dd2758ce0a.png). **P7.13** Alice sent ![\vec{m} = 01110011\;](./images/81edd344116d6507be5c993b2eaf3ea018e4c171.png) ![01110101\;](./images/1cb1c7c49b38dbbd09e8fb03baef04290c1e99dc.png) ![01110000](./images/c0bbe72887a62e77746fb4633538dd0fae8d0b61.png). After ASCII decoding each byte of this binary string, we find it corresponds to the message “sup.” **P7.15** ![f(\omega)=\sigma e^{-\frac{\sigma^2\omega^2}{2}}](./images/fc8dc289071832d95e7ca4e911e93896d32c1bdc.png). **P7.16** ![f(\omega) = \frac{1}{\sqrt{2\pi}} \frac{  2|a| }{   |a|^2 + \omega^2}](./images/c8cc7e1c24c860caa8c7b0866f3a60d97640135d.png). **P7.17** Fourier transform of ![f'(t)](./images/9b58e0c2a2e96cc20acf4fe72be8827b47f716af.png) is ![(i\omega)f(\omega)](./images/5c67cc556861c974183462d80134eb7d09f8bf0b.png).

### Solutions to selected problems

**P7.1** The reaction we’re studying is the burning of triglycerides. Read more about that here:[`http://bmj.com/content/349/bmj.g7257`](./bmj.g7257.md).

**P7.2**

The KVL equation for the clockwise loop starting at junction A is ![V_1 - R_1I_1 - R_2I_2 = 0](./images/b3d569016422a1a1e20d822d3332e14dd03589a6.png). The equation for the loop starting at C is ![-R_3I_3 -R_4I_4+R_2I_2=0](./images/7687ba91506113f65a4ede79a4df395dd6d34aac.png). The equation starting at ![D](./images/5eadde85cc4d11e6f52f4e09b6059250e60a2ea9.png) is ![+R_5I_5 - V_2 + R_4I_4=0](./images/5604debefdc2e7d14e64a6bf03587c83b7c59bb8.png). The KCL equation for junction C is ![I_1=I_2+I_3](./images/4807ff47727d3d99b9d1e61b70de16b93d921e0a.png) and that for D is ![I_3 + I_5=I_4](./images/27177208310004cbfad439f1030a5b89045f4198.png). After combining the equations, we obtain the matrix equation ![R\vec{I} = \vec{V}](./images/6f177144d57c080768d9b4e77f31486a9c5d3e34.png), where ![\vec{V}=\begin{bmatrix}
15 \\ 0 \\ 10 \\ 0 \\ 0
\end{bmatrix}](./images/3b4ce949ca8a0137427b5f2d1c3951bcd6cc557a.png) and ![R=
\begin{bmatrix}
R_{1} & R_{2} 	& 0 		& 0 		& 0\\
0 	& -R_{2} 	& R_{3} 	& R_{4} 	& 0\\
0 	& 0 		& 0 		& R_{4} 	& R_{5}\\
1 	& -1 		& -1 		& 0 		& 0\\
0 	& 0 		& 1 		& -1 		& 1
\end{bmatrix}](./images/9bb6c0f9124b94b9f7adf013ad74a4c695456cf8.png), which becomes ![R=
\begin{bmatrix}
1 & 1 & 0 & 0 & 0\\
0 & -1 & 4 & 2 & 0\\
0 & 0 & 0 & 2 & 2\\
1 & -1 & -1 & 0 & 0\\
0 & 0 & 1 & -1 & 1
\end{bmatrix}](./images/957bc16f34c934d45203b2ea65b56d323af5b0a0.png). We compute ![\vec{I} = R^{-1}\vec{V}](./images/a3dc2c19de4b1ec8da34991b8b382f9963901b16.png) and the answer is ![I_1=\frac{85}{11}\approx7.7](./images/129854c7f074ac5e1ab804f51b1cb82cd372a839.png) and ![I_5=\frac{25}{11}\approx 2.27](./images/41f0d5864278bf2a248d818bfd04fc7c82f78c01.png).

**P7.3** The dataset consists of a matrix of inputs ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png), ![A = (0,1,2,3)^\sfT](./images/1598e3b5896a826340d9690f4856c5433091e4dd.png), and a vector of outputs ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png), ![\vec{b}=(0.9,1.6, 2.1, 2.4)^\sfT](./images/5564fa53c766537830476b5f01a74add1b08c306.png). Since we’re interested in fitting an affine model ![y=b + mx](./images/389d6078ad148f4059e8ce6cc51728f135db1de1.png), we must augment the matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) with a column of ones to obtain ![A^\prime](./images/31dd30922c41f5695d509d9ddffcea83d982a147.png), and then compute ![A^{\prime\sfT} \!A^\prime](./images/8af7b483e8a27df1782163322ba835d1e0a73133.png) and its inverse:

![A^\prime =
\begin{bmatrix}
1	&	0	\\
1	&	1	\\
1	&	2	\\
1	&	3
\end{bmatrix},
\quad
A^{\prime\sfT} \!A^\prime
=
\begin{bmatrix}
4	&	\; 6	\\
6	&	\, 14
\end{bmatrix}
\quad
\Rightarrow
\quad
(A^{\prime\sfT} \!A^\prime)^{-1}
=
\begin{bmatrix}
\frac{7}{10} 	& -\frac{3}{10}	\\
-\frac{3}{10} 	& \frac{1}{5}
\end{bmatrix}.](./images/9241caa2742399ac21aaeb0ca22eb8ad882a2dfa.png)

We can now compute the Moore–Penrose inverse ![{A^{\prime}}^+](./images/9595dec4e44f2700aada3b02f0e94288cc8a6ab6.png) and obtain the approximate solution as follows:

![{A^{\prime}}^+
=
(A^{\prime\sfT} \!A^\prime)^{-1}A^{\prime\sfT}
=
\begin{bmatrix}
\frac{7}{10} 	& \frac{2}{5} 	& \frac{1}{10} 	& -\frac{1}{5}	\\
-\frac{3}{10} 	& -\frac{1}{10} 	& \frac{1}{10} 	& \frac{3}{10}
\end{bmatrix}
\quad
\Rightarrow
\quad{A^{\prime}}^+ \vec{b}
=
\begin{bmatrix}
1		\\
\frac{1}{2}
\end{bmatrix}.](./images/614ee29f03485ab2321fc21c9485bb0ca80470a8.png)

Thus the best-fitting affine model for the dataset is ![y=1+\frac{1}{2}x](./images/c688463c0b35d976ef9eb77cfab4251ab14f0144.png).

**P7.4** This is a standard least squares problem with an affine model. Visit this link to see the calculations,[`bit.ly/apt_rent_affine`](./apt_rent_affine.md); and this link to see the graph of the best-fitting affine model,[`bit.ly/apt_rent_fits`](./apt_rent_fits.md).

**P7.5** This is a least squares problem with a quadratic model. For the solution obtained using `SymPy`, see[`bit.ly/apt_rent_quadratic`](./apt_rent_quadratic.md). See[`bit.ly/apt_rent_fits`](./apt_rent_fits.md) for the graph of the best-fitting model.

**P7.6** The matrix equation can be either consistent (![\exists\vec{x}](./images/20ca28c1e85c6ab2b55242f0c5b0102d57c93ad0.png) such that ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png)), or inconsistent (![\nexists\vec{x}](./images/1d7927841a5e6fb640b885783f9824b1637fc52e.png) such that ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png)). If the matrix equation is consistent, then it either has a unique solution ![\vec{x}=\vec{x}_p](./images/32d1ae63485c8ec99cd5d44a8f9d48ba67b1be76.png) if ![\mathcal{N}(A) = \{ \vec{0} \}](./images/2eef75841099680988f7ccd54136e65ec6231824.png), or an infinite solutions set ![\vec{x}=\vec{x}_p + \mathcal{N}(A)](./images/70b35d7624afabaeebd8bd76aa709480b87a4dc9.png) if ![\mathcal{N}(A)](./images/2f174c7f34e074737143988a381616177bbe75be.png) is non-empty. If the matrix equation is inconsistent, we can still find a least squares approximate solution.

**P7.7** The ![i](./images/48b353d891e57e944c38b22a253327079ba56c85.png)th row of the adjacency matrix contains the information of the outgoing edges for vertex ![i](./images/48b353d891e57e944c38b22a253327079ba56c85.png) in the graph. If the edge ![(i,j)](./images/c04f5423659b0636ef9b6e34200c7af58104b427.png) exists, then ![A_{ij}=1](./images/ca7306a30bedfd21aef1d2b00f9adb1d77949738.png), otherwise ![A_{ij}=0](./images/da19b0e5f4cba6dd69463e07d0877a81351ee716.png).

**P7.9** The number of rows (columns) of the adjacency matrix tells us how many vertices the graph contains. The ![i](./images/48b353d891e57e944c38b22a253327079ba56c85.png)th row of the adjacency matrix contains the information of the outgoing edges for vertex ![i](./images/48b353d891e57e944c38b22a253327079ba56c85.png) in the graph. If you see ![A_{ij}=1](./images/ca7306a30bedfd21aef1d2b00f9adb1d77949738.png) then you must draw the edge ![(i,j)](./images/c04f5423659b0636ef9b6e34200c7af58104b427.png) in the graph.

**P7.10** Your job is to recognize visually what type of transformation is acting in each case, and then use the appropriate matrix formula from[Chapter 5](./Chapter 5_ Linear transformations.md).

**P7.11** Recall that the third column of homogeneous coordinates matrix representations serves to perform translations. Use the matrix product ![M_7M_4](./images/ed822f86ac520b86074f2f1aad9c6c402484ee7b.png) (first rotate then translate) to obtain the answer to part (e). Use the matrix product ![M_4M_7](./images/affef2d8a8d3fa606aa92a21932cb32dfa3e1b17.png) (first translate then rotate) to obtain the answer to part (f).

**P7.12** See [`bit.ly/persp_proj_prob`](./persp_proj_prob.md) for the calculations.

**P7.14** Decompose the formula for ![c_n](./images/05e590752bb6df58b74984eb3f7340a3b4db8f4d.png) into a its real part and imaginary parts:

![\begin{align*}
c_n	& = \frac{1}{T}\int_0^T f(t)e^{-i\frac{2\pi n}{T}t}\,dt					\\
& = \textrm{Re}\left\{
\tfrac{1}{T} \!\!
\int_0^T f(t)e^{-i\frac{2\pi n}{T}t}\,dt
\right\}
+
\textrm{Im}\left\{
\tfrac{1}{T} \!\!
\int_0^T f(t)e^{-i\frac{2\pi n}{T}t}\,dt
\right\}i												\\
& = \tfrac{1}{T} \!\!
\int_0^T f(t)
\textrm{Re}\left\{
e^{-i\frac{2\pi n}{T}t}
\right\}
dt
+
\tfrac{1}{T} \!\!
\int_0^T f(t)
\textrm{Im}\left\{
e^{-i\frac{2\pi n}{T}t}
\right\}
i\,dt												\\					
& = \tfrac{1}{T} \!\!
\int_0^T f(t)
\cos\left({\tfrac{2\pi n}{T}t}\right)
\,dt
-
\tfrac{1}{T} \!\!
\int_0^T f(t)
\sin\left({\tfrac{2\pi n}{T} t}\right)
i\,dt.
\end{align*}](./images/d783b3980b1cd3866eff1f7e2f655cd2b93f3b80.png)

We recognize the real part of ![c_n](./images/05e590752bb6df58b74984eb3f7340a3b4db8f4d.png) as the cosine coefficients ![a_n](./images/af7b3d3ed5dbdda80e11d68e014374fad67aa4b5.png) of the Fourier series, and the imaginary part of ![c_n](./images/05e590752bb6df58b74984eb3f7340a3b4db8f4d.png) as the negative of the sine coefficients ![b_n](./images/15d33d27d1a8b0f1ca293314ec8bf1336bc5a59e.png) of the Fourier series:

![\begin{align*}
\textrm{Re}\left\{  c_n \right\}
& =
\textrm{Re}\left\{
\tfrac{1}{T} \!\!
\int_0^T f(t)e^{-i\frac{2\pi n}{T}t}\,dt
\right\}
= \tfrac{1}{T} \!\! \int_0^T \!\! f(t) \cos\left({\tfrac{2\pi n}{T}t}\right)dt
= a_n,															\\
\textrm{Im}\left\{  c_n \right\}
& =
\textrm{Im}\left\{
\tfrac{1}{T} \!\!
\int_0^T f(t)e^{-i\frac{2\pi n}{T}t}\,dt
\right\}
= \tfrac{1}{T} \!\! \int_0^T \!\! f(t) \sin\left({-\tfrac{2\pi n}{T} t}\right)dt
= - b_n.
\end{align*}](./images/e1407ba9567fe57e0ca69ca76a9706d1a89964f4.png)

Thus we have shown ![c_n = a_n - ib_n](./images/3d68dd8e2e2d74586729a6291342d44385958b7a.png).

Using the simple definition of the coefficients ![c_n](./images/05e590752bb6df58b74984eb3f7340a3b4db8f4d.png) above, the synthesis equation for the complex Fourier transform is the somewhat awkward expression ![f(t) = c_0
+ \frac{1}{2}\sum_{n=1}^{\infty} e^{-i\frac{2\pi n}{T}t} c_n
+ \frac{1}{2}\sum_{n=-\infty}^{-1}  e^{-i\frac{2\pi n}{T}t} \overline{c_n}](./images/5313671b889a2a1460c5f15de50d7cdb536e77fc.png). Many textbooks describe complex Fourier series in terms of the two-sided coefficients ![c_n^\prime, n \in \mathbb{Z}](./images/89eb29d464d162f9676ed857011e0cdde27d69d4.png) defined as

![\begin{align*}
c_0^\prime &= c_0,	\\
c_n^\prime &= \tfrac{1}{2}c_n = \tfrac{1}{2}(a_n - i b_n)					& & \textrm{ for } n \geq 1,	\\
c_{n}^\prime &= \tfrac{1}{2}\overline{c_{-n}} = \tfrac{1}{2}(a_{-n} + i b_{-n})		& & \textrm{ for } n \leq -1.
\end{align*}](./images/ed4e3fc1ab7ba6b8ebc85b8ec77025811a5f728d.png)

Using the coefficients ![c^\prime_n](./images/2c2935f7631ebb1279535ede63309498eae48ca9.png), the synthesis equation for the complex Fourier series is the simpler expression ![f(t) = \sum_{n=-\infty}^{\infty} e^{-i\frac{2\pi n}{T}t} c^\prime_n](./images/b5cc169dbf9d2fa8dc29f2b0df778f0fb8f646dd.png).

**P7.15** This is a long calculation but straightforward if you write things clearly. The key idea is to rewrite ![t^2 + 2 \sigma^2 i \omega t](./images/a651f0781bb2089b36951790bef5bab162a9a429.png) in the form ![(t+h)^2 +k](./images/90a90c533d1b955241fda41487ba26b87c37a5ba.png) so that the constant term ![k=\sigma^4 \omega^2](./images/59f4d80b75651e27cab439d6e170bca877d73a55.png) can be removed from the integral.

![\begin{align*}
f(\omega)
&= 	\tfrac{1}{\sqrt{2\pi}} \!\!
\int_{-\infty}^{\infty}
\!\!
e^{-i\omega t}
e^{-\frac{t^2}{2\sigma^2}}
\, dt
= \tfrac{1}{\sqrt{2\pi}} \!\!
\int_{-\infty}^{\infty}
\!\!
e^{-\frac{1}{2\sigma^2}\left(
t^2 + 2 \sigma^2 i \omega t
\right)}
\, dt										\\
&= \tfrac{1}{\sqrt{2\pi}}\!\!
\int_{-\infty}^{\infty}
\!\!
e^{-\frac{1}{2\sigma^2}\left([t+\sigma^2 i \omega]^2 + \sigma^4 \omega^2
\right)}
dt
= \tfrac{1}{\sqrt{2\pi}}
e^{-\frac{\sigma^2\omega^2}{2}}
\!\!\!
\int_{-\infty}^{\infty}
\!\!
e^{-\frac{1}{2\sigma^2}\left([t+\sigma^2 i \omega]^2
\right)}
dt										\\
&= \tfrac{1}{\sqrt{2\pi}}									e^{-\frac{\sigma^2\omega^2}{2}}
\int_{-\infty}^{\infty}
e^{-\frac{1}{2\sigma^2}\left( t^\prime \right)^2}
\, dt^\prime, \qquad \textrm{letting } t^\prime = t+\sigma^2 i \omega 							\\
&= \tfrac{1}{\sqrt{2\pi}}
e^{-\frac{\sigma^2\omega^2}{2}}
\sqrt{2\pi}{\sigma} = \sigma e^{-\frac{\sigma^2\omega^2}{2}}.
\end{align*}](../Images/de85f9c40766bdc05060dffe7835e70aa51b706c.png)

**P7.16** We start from the definition ![f(\omega) = 	\tfrac{1}{\sqrt{2\pi}} \!
\int_{-\infty}^{\infty}
\!
e^{-i\omega t}
e^{-|at|}
\, dt](./images/0418b7f4a709c1def3e7768fde51506719434c8e.png). Next we rewrite ![e^{-i\omega t}](./images/5e63ab292c0b780cd448acce035ec67277839a4b.png) as ![(\cos(\omega t) - i\sin(\omega t))](./images/ab9a566893835f434e8000fd1296708ceca5160d.png) and observe that sine is an odd function so this term vanishes. The integral becomes ![f(\omega) = \tfrac{2}{\sqrt{2\pi}}
\int_{0}^{\infty}
\!
\cos(\omega t)
e^{-|at|}
\, dt](./images/1efdf002bb3d3d678f340fef96f59dd4f33ad9ab.png), which we can tackle using integration by parts.

**P7.17** Starting from the formula ![f(t)=\tfrac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}
e^{i\omega t}
f(\omega)
\, d\omega](./images/43f73e31fc5b8ff6015de65fdaba1b4f071057c1.png), take the derivative with respect to ![t](./images/e393328f63600775ab7376c9b4fc411c9b60340a.png) to obtain ![f'(t) = \frac{d}{dt}\!\left(\!
\int_{-\infty}^{\infty}
e^{i\omega t} 	f(\omega)	\, d\omega \!
\right)\!
= \int_{-\infty}^{\infty} \!\!
e^{i\omega t} 	(i\omega)	f(\omega)	\, d\omega](./images/50a0c1ada90e54e5d9ab3f42a070fe27f45fbd32.png) ![= (i\omega) \int_{-\infty}^{\infty} \!\!
e^{i\omega t} 	f(\omega)	\, d\omega](./images/185466eee1361a76937d86d05f5297a36e31cf69.png). This means the Fourier transform of ![f'(t)](./images/9b58e0c2a2e96cc20acf4fe72be8827b47f716af.png) is ![(i\omega)f(\omega)](./images/5c67cc556861c974183462d80134eb7d09f8bf0b.png).

The Fourier transform converts differential equations involving ![f(t)](./images/5efd00e5bf3a607572430909c72c6a99d7761528.png) into algebraic equations involving ![f(\omega)](./images/c80b9e827d00011fc8ea63776be98c78925cb7df.png). For example, the Fourier transform of the second-order differential equation ![\alpha f^{\prime\prime}(t) + \beta f^{\prime}(t) + \gamma f(t)= 0](./images/f998866293f472d7f763bcb1284ff27438991e1f.png) is a second-order (quadratic) algebraic equation: ![\alpha (i\omega)^2 f(\omega) + \beta (i\omega) f(\omega) + \gamma f(\omega) = 0](./images/4cab1ef15f9e780aa58c5a6eb7e48b5c4942723f.png). I encourage you to learn more about differential equations from the web, or email me if you think I should write a book on this topic.

##[Chapter 8 solutions](./Front matter.md)

### Answers to exercises

**E8.1**

1.  No; weights don’t add to one.
2.  Yes.
3.  No; contains a negative number.

**E8.2** ![\mu_X=3.5](./images/d6ce1723aedb621bbd278d2a41dfb26260251581.png), ![\sigma_X^2 = \tfrac{35}{12} \approx 2.92](./images/dea2ece648c70233533e750920e7331ea9923ec8.png). **E8.3** ![B=M^{\sfT}](./images/d7a5ff45d341a51fbe768040ae3b028c3db6e090.png). **E8.4** ![\psub{X_\infty} = \left(\frac{5}{31}, \frac{20}{31}, \frac{6}{31} \right)](./images/60abe069530aadc392c82da7389781b1070a61e4.png). **E8.5** ![\psub{X_\infty} = \left(\frac{34}{61}, \frac{14}{61}, \frac{13}{61} \right)](./images/b8f17bbd65cff9826e919b9352086d28aecb4dac.png). **E8.6** ![\psub{X_\infty} = (0.2793, 0.1457, 0.2768, 0.02,0.2781)^\sfT](./images/9488e10809226913d63a2d7396914445a2535e48.png).

### Solutions to selected exercises

**E8.4** You can either use `evec = M.eigenvects()[0][2][0]` to extract the first eigenvector, or `evec = (M-eye(3)).nullspace()[0]`, which is more efficient. To obtain a probability distribution, normalize the eigenvector by dividing it by its ![\ell^1](./images/e943825a9a6d29ed0f8c4109d35fd0dcecc4a468.png)\-norm `pinf = evec/evec.norm(1)`.

**E8.5** Use `evec = (C-eye(3)).nullspace()[0]` to extract the eigenvector for ![\lambda=1](./images/e0147e4a5a8d2795eee85499d5ee1e7ae34d8f2f.png), then normalize the vector by its ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png)\-norm to make it a probability distribution `pinf = evec/evec.norm(1) =` ![\left(\frac{34}{61}, \frac{14}{61}, \frac{13}{61} \right)](./images/7106e64f02049d091fa96170c516c8db2e3898e8.png).

**E8.6** You can see the solution at this URL:[`bit.ly/21GOUCe`](./21GOUCe.md).

### Answers to problems

**P8.2** ![\textrm{Pr}(\{ \texttt{heads}, \texttt{heads}, \texttt{heads}, \texttt{heads}\}) = \frac{1}{16}](./images/144b1616486a55ddb607a39db79181827aadc993.png). **P8.4** ![\mathbb{E}_X[X]=\frac{1}{p}](../Images/21246793ffb33aeaeecfe6f8fa9794b1cbd9a63f.png). **P8.5** ![\mathbb{E}_X[W]=\$\frac{100}{101} < \$1](../Images/a5b317370423ceb2f78bde759ffdbf2341af1868.png). Not worth it. **P8.6**  ![\mathbb{E}_X[f(X)] = \tfrac{\$7}{6} > \$1](../Images/65ac84a2c5c649eb8107c71cd4a7dc11fcce9924.png) so it’s worth playing this game. **P8.8** ![\psub{X_1} = (\frac{1}{2},\frac{1}{2})^\sfT](./images/1d7e139e5ac5fb79e30d0856aee36a9b9048bf4d.png), ![\psub{X_2} = (\frac{3}{8},\frac{5}{8})^\sfT](./images/f1d3bdec0dc71d5b84cca88057ad829b2d2a3793.png), ![\psub{X_\infty} = (\frac{1}{3},\frac{2}{3})^\sfT](./images/55d19ae369dbe5117a4847dda9966ae3104a2ed5.png). **P8.9** ![\psub{X_{\infty}}=(0.1721, 0.169, 0.245, 0.245,0.169)^\sfT](./images/2c64a60376447476b206b2889aa09c4db55bd26e.png).

### Solutions to selected problems

**P8.1** Assume, for a contradiction, that ![p_1 >1](./images/707e6c00ecf038982a126075566e371909d8307f.png). We know from Kolmogorov’s axioms that ![p_i \geq 0](./images/9192bca3b2b85c97037dab5bf6b618241419a7c5.png) for all ![i](./images/48b353d891e57e944c38b22a253327079ba56c85.png). Observe that ![\sum_i p_i = p_1 + p_2 + p_3  \geq p_1 >1](./images/413ba8e4e962c43a29a2f3cd65732d2656133948.png), which means the vector ![(p_1,p_2,p_3)](./images/42a80008417203f97348fc83e9b81387d55cbe71.png) is not a valid probability distribution. Therefore, it must be that ![p_1 > 1](./images/707e6c00ecf038982a126075566e371909d8307f.png) is false, and ![p_1 \leq 1](./images/fe5d00725923f0f48b59e3b5c83c66103f7dc375.png) is true.

**P8.2** Substitute ![p=\frac{1}{2}](./images/ac588ffd8b6ed171e22586ef6d7a28a39b9ea429.png) and ![n=4](./images/b9d924e89ce23cbd94b74a231e4298f9aac8c34b.png) into the expression ![p^n](./images/d74a6c95a2f90c16103bb250fa5a6d1393384596.png).

**P8.3** The biased coin flip is modelled by a random variable ![Y](./images/af40f50353f77406a09c621b7bba6537bc9c6750.png), and different coin flips correspond to random variables ![Y_1](./images/6c6639818d4993256b0079c44f93e2577196fc11.png), ![Y_2](./images/527d8270998a6d2a527086a4d9af917db961b9b8.png), ![Y_3](./images/e870a51399efafcfc0d8c17852630958eec549c4.png), …which are independent copies of ![Y](./images/af40f50353f77406a09c621b7bba6537bc9c6750.png). The probability of getting `heads` on the first flip is ![P_N(1)=\textrm{Pr}\!\left( \{ Y_1=\texttt{heads} \} \right)\! =p](./images/f6c15cad996fef133f1d99b45fb510046edb96c6.png). The probability of getting `heads` on the second flip corresponds to the event ![\{Y_1=\texttt{tails}\} \; \texttt{AND} \; \{Y_2=\texttt{heads} \}](./images/a174da41a8df374efd14a1ee6fdec10f4518c73e.png). We assumed the coin flips are independent, so ![P_N(2)=(1-p)p](./images/c918a9a6019f99126305e1c41c08bd97915760de.png). Similarly ![P_N(3) = (1-p)^2p](./images/ff32c60cdf9b693732237bf123b83e6a164e07b1.png). The general formula is ![P_N(n) = (1-p)^{n-1}p](./images/7900d61eb338c6bbd056f19d25ab957d93ed9ace.png).

**P8.4** Starting from the definition, we write ![\mathbb{E}_X[X] = \sum_{x = 0}^\infty x  (1-p)^{x-1}p](../Images/457e0dd04f801b694ff147914731b3157b61b363.png). Using the formula from the hint to compute the infinite summation, we obtain the answer ![\mathbb{E}_X[X] = p\sum_{x = 0}^\infty x  (1-p)^{x-1} = p\frac{1}{(1-(1-p))^2} =  \frac{p}{p^2} =\frac{1}{p}](../Images/fda7ea22120df8206e30d5c7b003eff8a5beb6e6.png).

**P8.5** We’ll model each spin of the roulette wheel as a random variable ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png) with sample space ![\{ \textrm{red}, \textrm{black}, \textrm{green}\}](./images/35c5409a8e897f6ba15b85d3abe0e54040b8f406.png) and probability distribution ![\psub{X} = (\frac{50}{101},\frac{50}{101},\frac{1}{101})](./images/8925f5a25e98144bee52aba393fe586475b35734.png). When placing a bet on black, the payout is ![W=\$2](./images/4efa7392940da834162614a1d5efcf57280c7e28.png) if the outcome is black, and zero for other outcomes. The expected value of the payout is ![\mathbb{E}_X[W]=0\cdot \frac{50}{101} + \$2 \cdot \frac{50}{101} + 0\cdot \frac{1}{101}=\$\frac{100}{101}](../Images/7050d5f71ea22e34121427d517f409cc6875610b.png). Since ![\frac{100}{101} < 1](./images/5010495c9a7010202cbef42331ea5ef4fe19f081.png), the house has an advantage, so the mathematician shouldn’t play.

**P8.6** The payout function for this game is defined as follows:

![f(\myepsdice{1}) = f(\myepsdice{2}) = f(\myepsdice{3}) = \$0,
\quad
f(\myepsdice{4}) = f(\myepsdice{5}) = \$1,
\quad
f(\myepsdice{6}) = \$5.](./images/ead01d740ed9824bb95975b859b944c9791d4afb.png)

The die is described by the distribution ![\psub{X} = (\frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6})^\sfT](./images/f36e02c528aa35e5df843328f4a66a9b1bf7c168.png). The expected payout is ![\mathbb{E}_X[f(X)]
=  \textstyle \sum_x f(x)\, \psub{X}(x)
= \tfrac{\$1+\$1+\$5}{6}  \; = \;  \tfrac{\$7}{6} \; = \; \$1.1\overline{6}](../Images/8f9c9607a939259d7b8a94eb86b7afbb9ff3f920.png). The expected payout is greater than the cost to play, so you’ll win on average.

**P8.7** Starting from ![\textrm{var}(X) = \sum_x (x-\musub{X})^2 \, \psub{X}(x)](./images/9eb494d8e4082c31f2e4c2ffcead4caaabb753ed.png) and expanding the bracket, we obtain ![\sum_x \big( x^2  \, \psub{X}(x)  - 2x\musub{X}\, \psub{X}(x) + \musub{X}^2\,\psub{X}(x) \big)](./images/99919fb7513fa7280283ccbbf3a79f30cd1ca432.png). Since ![\sum_x x\,\psub{X}(x) = \musub{X}](./images/36d6a0d42a6c89619e262a9026bba36a8d4299f1.png) and ![\sum_x \psub{X}(x) = 1](./images/dbab9ceaba217afb85a834ec9f56c89fa20bdf66.png), this variance expression simplifies to ![\sum_x x^2\,\psub{X}(x)  - \musub{X}^2](./images/407115e6fd26cd4944b69a7bb6c762c666938678.png). An analogous equations relating the moments of inertia of solids exists in physics: ![I_\mathrm{cm} = I - md^2](./images/7895af0fbc63750fcc23cd1dd0e514cbd5348680.png). This is known as the parallel axis theorem and states that the moment of inertia of a solid around its centre of mass is equal to its moment of inertia around a different parallel axis, minus a factor ![md^2](./images/b34d471fe2c25fa087ae4f6b00b64295628791a0.png) proportional to the mass of the object and the squared distance of the axis to the centre of mass.

**P8.8** Define ![X_i](./images/924d898c73ae19ed8cc880c0aab15f1d2a0a2680.png) to be the probability distribution of the weather in Year ![i](./images/48b353d891e57e944c38b22a253327079ba56c85.png). The transition matrix for the weather Markov chain is ![M=\left[\begin{smallmatrix}
\frac{1}{2} & \frac{1}{4} \\
\frac{1}{2} & \frac{3}{4}
\end{smallmatrix}\right]](../Images/71ebe43cd98a0e85acdf65a7762d0a1ed0788b6e.png). We obtain the weather in Year 1 using ![\psub{X_1}=M(1,0)^\sfT=(\frac{1}{2},\frac{1}{2})^\sfT](./images/543c0d0613b47d7cfae725e42cd967ad6853943c.png). The weather in Year 2 is ![\psub{X_2}=M^2(1,0)^\sfT = (\frac{3}{8},\frac{5}{8})^\sfT](./images/eadd8bb89346239571e561dbae489179a048bf14.png). The long term (stationary) distribution is ![\psub{X_\infty}=M^\infty(1,0)^\sfT = (\frac{1}{3},\frac{2}{3})^\sfT](./images/2e68c9cac6c108ccb471f5c71f0fc724c179b529.png).

**P8.9** Construct ![M_1](./images/2fbe7f3d090b8150a5bb7678a07a7525b79caad9.png) by counting the outbound links for each webpage, then mix in ![0.9](./images/044a412bf8946ddbded266ecc308d3b4c30c9f1d.png) of it with ![0.1](./images/dbcc8f43553d35ed6c6af144ccabffae77b6dbb5.png) of ![\frac{1}{5}\mathbb{J}](./images/0510679bacefc672de271333d41bdab242a5797a.png) to obtain the Markov chain matrix ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png):

![M_1  = \begin{bmatrix}
0 & \frac{1}{2} & 0 & 0 & \frac{1}{2}\\
\frac{1}{4} & 0 & \frac{1}{2} & 0 & 0\\
\frac{1}{4} & \frac{1}{2} & 0 & \frac{1}{2} & 0\\
\frac{1}{4} & 0 & \frac{1}{2} & 0 & \frac{1}{2}\\
\frac{1}{4} & 0 & 0 & \frac{1}{2} & 0
\end{bmatrix},
\quad
M_2 = \frac{1}{5}\,\mathbb{J}_{5},
\quad
M = \begin{bmatrix}
\frac{1}{50} & \frac{47}{100} & \frac{1}{50} & \frac{1}{50} & \frac{47}{100}\\
\frac{49}{200} & \frac{1}{50} & \frac{47}{100} & \frac{1}{50} & \frac{1}{50}\\
\frac{49}{200} & \frac{47}{100} & \frac{1}{50} & \frac{47}{100} & \frac{1}{50}\\
\frac{49}{200} & \frac{1}{50} & \frac{47}{100} & \frac{1}{50} & \frac{47}{100}\\
\frac{49}{200} & \frac{1}{50} & \frac{1}{50} & \frac{47}{100} & \frac{1}{50}
\end{bmatrix}\!.](./images/4ca5647991616fcd650ecd9cd0fe9e149454b544.png)

Solving ![\left( M- \mathbbm{1} \right)\vec{e}= \vec{0}](./images/49907ec3e19eb3201fff8bd874fc82d706ce73df.png), we find ![\psub{X_{\infty}}= \frac{\vec{e}}{\|\vec{e}\|_1}=(0.1721, 0.169, 0.245, 0.245,0.169)^\sfT](./images/e8cd3992edee2910549bcb3daeacb57a5519155d.png).

##[Chapter 9 solutions](./Front matter.md)

### Answers to exercises

**E9.1**  ![\vec{u}=(\alpha,0,0,\beta)^\sfT](./images/a5a1d3f61a8d51e32d4558af784b6719b9495ea3.png) (a column vector); ![\overline{\vec{v}^\sfT}=(0,\overline{a},\overline{b},0)](./images/d028ffbc07b1cbaed9b599dbd5434bfacc869bab.png) (a row vector). **E9.2** ![\ket{w}=1\ket{0} + i\ket{1} - \ket{2}](./images/6037a38acd61a55bd3aa4dcfe9f536954340e952.png); ![\bra{w} = 1\bra{0} -i \bra{1} - \bra{2}](./images/c5d80cacec6f72fe74ca63e9a24717ceec018167.png); ![\| \vec{w} \|=\sqrt{3}](./images/a22acb59056ee5e109dd9e3203a895789c61179f.png). **E9.3** ![\det(A)=-2](./images/dc6bb3716e104b0e3d74871789f1e2d3e977d389.png). **E9.4**

1.  ![(1+\frac{1}{\sqrt{2}})\ket{0} + \frac{i}{\sqrt{2}}\ket{1}](./images/6a4630b29bad86b34af9d9c936e0709abf69a446.png);
2.  ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png);
3.  ![\frac{\sqrt{2}}{2}](./images/299f67eddaec166439802eb1190394edfd0b43be.png);
4.  ![\frac{\sqrt{10}}{10} + \frac{\sqrt{10} i}{5}](./images/e2aff5fa130bf1cb66378c5166203ff32274c862.png);
5.  ![\frac{\sqrt{10}}{10} - \frac{\sqrt{10} i}{5}](./images/d94ed48f072e043392b1e302d06d692e88428282.png);
6.  ![\begin{bmatrix}1 & 0\\0 & 0\end{bmatrix}](./images/0512ade1dc21239a9525a15042f57f2b8f034bf2.png);
7.  ![\frac{\sqrt{2}}{2}\ket{0}](./images/22a9c286c7971553286810b5567d564657e337df.png);
8.  ![\begin{bmatrix}\frac{1}{2} & - \frac{i}{2}\\\frac{i}{2} & \frac{1}{2}\end{bmatrix}](./images/852c8ea09127b29b1d3daa6f52cbbc0219ee583d.png);
9.  ![\frac{1}{2}\ket{0} + \frac{i}{2}\ket{1}](./images/18201de9dd131c1daefabbdd7b7dfa242303c25c.png);
10.  ![(\frac{\sqrt{5}}{10} + \frac{\sqrt{5} i}{5})\ket{0} - (\frac{\sqrt{5}}{5} - \frac{\sqrt{5} i}{10})\ket{1}](./images/f624dd6759969d1f0a439377ca59a419c2db8bc0.png).

**E9.5**

1.  ![A\ket{v}=10\ket{0}+19\ket{1}](./images/90b37a70721d1b971b83aa8c720bc7f945ff584c.png);
2.   ![\bra{v}A =](./images/5ccdfc6f0ed2c2a2637d92acd8ae5773b174c12b.png) ![13\bra{0} + 18\bra{1}](./images/98b67482a3d61555a3b9237338c95eb3e71d02c4.png);
3.    ![A\ket{w} =](./images/455398d35227fd473697d2a6ed750979b2264fbf.png) ![(-3 - 6i)\ket{0}](./images/5cfad0b48a6372af23ffaf3d0d5b9526d5d5fbbc.png) ![- (12 + 10i)\ket{1}](./images/290027fcaca86cad087445593fd9917257a153a6.png);
4.  ![\bra{v}A\ket{v} = 67](./images/55908052c3fe7663f1a59d432275d73a4f69641a.png);
5.   ![\bra{w}A =](./images/7c6137d106db1eb2273442adb7e4148978c71be5.png) ![(-3 + 8i)\bra{0} + (-9 + 10 i)\bra{1}](./images/12a0c75d442df49cc8f193b7c93f4fd6e4986125.png);
6.   ![\bra{w}A\ket{w}](./images/96faaff9789c3506e05e7f02d2e1e352cda1d2da.png) ![= 29 - 6i](./images/f8094750800b7f3caf11db92c45bad1f0f4806fb.png).

**E9.6** ![M_T= 2\ketbra{0}{0} + 1\ketbra{0}{1} -3\ketbra{1}{1}](./images/2b7f3d280979c0f611585c819bafbd98ec24a77e.png). **E9.7**  ![HH\ket{0}=\ket{0}](./images/66ea79e8eb58f68c6322df7fd951556d82607007.png) and ![HH\ket{1}=\ket{1}](./images/e54e5589461220a1a4dc0c2994d2f03980537693.png). **E9.8** ![XX= \begin{bmatrix}1 & 0\\0 & 1\end{bmatrix}](./images/dc22b9dab5a9c928312bc23b81d5639641f09269.png), ![XZ= \begin{bmatrix}0 & -1\\1 & 0\end{bmatrix}](./images/ba9622700596f428091788d39cb43bb66cf6765b.png), ![ZX= \begin{bmatrix}0 & 1\\-1 & 0\end{bmatrix}](./images/66c2f8022de181b976649d69631737f2aeb5a462.png). **E9.9** See solution. **E9.10**  ![M_{\Pi_+} = \begin{bmatrix}\frac{1}{2} & \frac{1}{2}\\\frac{1}{2} & \frac{1}{2}\end{bmatrix}](./images/373cbb95922ac3c97864986c08fa8d84e89e50a8.png) and ![M_{\Pi_-} = \begin{bmatrix}\frac{1}{2} & -\frac{1}{2}\\ -\frac{1}{2} & \frac{1}{2}\end{bmatrix}](./images/4f859e5683068d717e4a6f22faeaebfa66c0723c.png). **E9.11** ![\textrm{Pr}( \{ - \} | \psi)=\frac{|\alpha  - \beta|^2}{2}](./images/57b44473cc7e2d148075d4ba8ade740d280c365d.png). **E9.12** ![\ket{\theta^\perp}=(\frac{1}{\sqrt{2}}, \frac{e^{- i (\pi-\theta)}}{\sqrt{2}})^\sfT](./images/ecf0ec02c23f4f27ec6e9ce07d37e7b94b5b9c32.png). ![M_{\Pi_\theta} = \begin{bmatrix}\frac{1}{2} & \frac{e^{- i \theta}}{2} \\ \frac{e^{i \theta}}{2} & \frac{1}{2}\end{bmatrix}](./images/69f6de6335cfd31956556ac00c88afff66a23e7e.png) and ![M_{\Pi_{\theta^\perp}} = \begin{bmatrix}\frac{1}{2} & \frac{1}{2} e^{i (\pi-\theta)}\\\frac{1}{2} e^{- i (\pi-\theta)} & \frac{1}{2}\end{bmatrix}](./images/9eb8db15a76e02eb81c03d9555d3fdf62128b87e.png). ![\textrm{Pr}( \{ - \} | \psi)=\sqrt{\left|{\frac{\alpha}{2} + \frac{\beta}{2} e^{- i \theta}}\right|^{2} + \left|{\frac{\alpha}{2} e^{i \theta} + \frac{\beta}{2}}\right|^{2}}](./images/766dd3b672bdf0ca79c5c7703a594bf65cb7e473.png). **E9.13** ![\ket{\psi}\!\otimes\!\ket{\phi} =
\alpha \gamma\ket{00}
+ \alpha \delta \ket{01}
+ \beta \gamma\ket{10}
+ \beta \delta\ket{11}](./images/3a5cf12b9eb0599fae3efb8e15030bd7aec9ae45.png).

### Solutions to selected exercises

**E9.7** Let’s first see what happens to ![\ket{0}](./images/f5eede2beac6072a276e8d8abe4fc0cf90522335.png) when we apply the operator ![HH](./images/311ae1f449f8ddd29011bb358937740a4c459472.png). The result of the first ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png) applied to ![\ket{0}](./images/f5eede2beac6072a276e8d8abe4fc0cf90522335.png) is ![H\ket{0}=\ket{+}=\tfrac{1}{\sqrt{2}}\!\left( \ket{0} + \ket{1} \right)](./images/ebc5ca39f2636a68cede900d0b299de172726863.png). Applying the second ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png) operator, we get ![HH\ket{0}=H\ket{+}=\tfrac{1}{\sqrt{2}}\!\left( H\ket{0} + H\ket{1} \right)](./images/9083ff684477e1a52f4065f738a861e98d87b65a.png). Applying the ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png) operation gives ![\tfrac{1}{\sqrt{2}}\big(
\tfrac{1}{\sqrt{2}}\!\left( \ket{0} + \ket{1} \right)
+ \tfrac{1}{\sqrt{2}}\!\left( \ket{0} - \ket{1} \right)
\big)](./images/584081624edb5193f4e07afd5bed303491ab9695.png), which simplifies to ![\tfrac{1}{\sqrt{2}}\!\big(  \tfrac{2}{\sqrt{2}} \ket{0} \big) = \ket{0}](./images/f44027e8b26050ce26c2d5d18a1a34ba77a729c1.png). So ![HH\ket{0}=\ket{0}](./images/66ea79e8eb58f68c6322df7fd951556d82607007.png). A similar calculation shows that ![HH\ket{1}=\ket{1}](./images/e54e5589461220a1a4dc0c2994d2f03980537693.png).

**E9.8** Use matrix multiplication. Note ![XZ](./images/5d1c703df3fb15ad38f69a3a8343c5c7733a412d.png) is not the same as ![ZX](./images/f27104fdb1898eb0974a15b9bda6a10a7a94db34.png).

**E9.9** Using the definition of ![\ket{+}](./images/0c4bdc263050bc6a06d91cd01c1b9d1f600daee6.png) and ![\ket{-}](./images/fdbe98762b7672f51923df5d1a1614e0708ccd7c.png), we obtain expressions for the vectors of the standard basis written in terms of the Hadamard basis: ![\ket{0}=\tfrac{1}{\sqrt{2}}\ket{+} + \tfrac{1}{\sqrt{2}}\ket{-}](./images/ae99c6b22a60042ca885bb79b5455b2e9994332f.png), and ![\ket{1} = \tfrac{1}{\sqrt{2}}\ket{+} - \tfrac{1}{\sqrt{2}}\ket{-}](./images/78368012adc71327b3766533fe776f441f866422.png). The remainder of the calculations require arithmetic and simplifications:

![\begin{align*}
\ket{01} & -  \ket{10}
=	\ket{0}\otimes\ket{1} - \ket{1}\otimes\ket{0}		\\
&=	\left(\! \tfrac{1}{\sqrt{2}}\ket{+} + \tfrac{1}{\sqrt{2}}\ket{-} \!\right)\!
\left(\! \tfrac{1}{\sqrt{2}}\ket{+} - \tfrac{1}{\sqrt{2}}\ket{-} \!\right)
-
\left(\! \tfrac{1}{\sqrt{2}}\ket{+} - \tfrac{1}{\sqrt{2}}\ket{-} \!\right)\!
\left(\! \tfrac{1}{\sqrt{2}}\ket{+} + \tfrac{1}{\sqrt{2}}\ket{-} \!\right)		\\
&=	\tfrac{1}{2}
\Big(
\cancel{\ket{+}\!\ket{+}} -  \ket{+}\ket{-} + \ket{-}\ket{+} - \cancel{\ket{-}\!\ket{-}}
- \cancel{\ket{+}\!\ket{+}} - \ket{+}\ket{-}  + \ket{-}\ket{+}  + \cancel{\ket{-}\!\ket{-}} 	\Big) 		\\
&=	\tfrac{1}{2}	\Big(	 -2\ket{+}\ket{-} + 2\ket{-}\ket{+} 	\Big)
\; = \; -( \ket{+}\ket{-} - \ket{-}\ket{+})
\; = \; \ket{+}\ket{-} - \ket{-}\ket{+}.
\end{align*}](./images/f39a0f7f56ce038919325c280745f004930acab2.png)

The last equality holds since the state’s global phase can be ignored.

### Answers to problems

**P9.1** No, since ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png) is not unitary. **P9.2**  ![YY\ket{0}=\ket{0}](./images/b8ee974ece876a20d711663b2dbab3724d91cc8b.png) and ![YY\ket{1}=\ket{1}](./images/a3a2ae255a58f378987d6eb1ad2e9cb02dfa5dd5.png). **P9.3** ![i \alpha\ket{0} - i \beta\ket{1}](./images/1edbcee853c6a5aa312e006327145ee890d23be2.png). **P9.4** Two parameters. **P9.5**  ![\alpha \in[0,1]](../Images/59da019f286f320ad559d5c049d96619546d65b2.png) and ![\varphi \in[0,2\pi]](../Images/7f1b4e75055e169a749c061b7da3f666a431be5e.png). **P9.6**  ![\theta \in[0,\pi]](../Images/d6804bb479ce8422ef3b243f532e1a53944c5fad.png) and ![\varphi \in[0,2\pi]](../Images/7f1b4e75055e169a749c061b7da3f666a431be5e.png). **P9.7**  ![HXH = Z](./images/af404e8600c608c4b3aad8ee35746874b29f1e00.png) and ![HZH = X](./images/d2ebfb101ee279c2e5c61967d67107449126ec0a.png). **P9.8** ![\textrm{Pr}( \{ v \} | \psi)=|\alpha \overline{a} + \beta \overline{b}|^2](./images/8596590d349c74131ba4e1043807eb60b4d47a7a.png). **P9.9** ![\Pr(\{0\} | \psi )=|\beta|^2](./images/702f12daa975f741485ce54da3b6dc50d2076a76.png); ![\Pr(\{+\} | \psi )=\tfrac{1}{2}|\alpha+\beta|^2](./images/61829c217c22b5b4d4bfa12f1db6aa04e65c7c64.png); ![\Pr(\{-\} | \psi )=\tfrac{1}{2}|\alpha-\beta|^2](./images/6a977287447296b34bbff170a39aec3fc3132e7a.png). **P9.11** ![\mathbb{E}_R[R]=\frac{3}{2}a](../Images/dd24830e2815b597622254c5ff60b2a0c112570b.png). **P9.12** ![\braket{\psi_1 ,\psi_2} = 0](./images/e187438b4feb72f46716ee5f6a06baf837c9753a.png). **P9.13** ![\Pr(\{0 \leq x \leq \frac{1}{4} \} | \psi_a ) = \frac{7}{16}](./images/be6c33ef68b934bc0d3b46a4fa80806e6158f721.png); ![\Pr(\{0 \leq x \leq \frac{1}{4} \} | \psi_b ) = \frac{79}{256}](./images/b1b8a6e58aef11f0686db7b46f7bcdb0ec5db880.png); ![\Pr(\{0 \leq x \leq \frac{1}{4} \} | \psi_c ) = \frac{1}{4}](./images/d33105e289752a0006d486028e07224777004ecb.png).

### Solutions to selected problems

**P9.1** Quantum gates correspond to unitary operators. Since ![Q^\dagger Q \neq \mathbbm{1}](./images/702d49e978acf24c3626c720a43e404929255d9f.png), ![Q](./images/5c03f27acad44aee6afe854fa4850f2fc833dea9.png) is not unitary and it cannot be implemented by any physical device. The boss is _not_ always right!

**P9.2** Let’s first see what happens to ![\ket{0}](./images/f5eede2beac6072a276e8d8abe4fc0cf90522335.png) when we apply the operator ![YY](./images/ffeb1bbc6506847a88bc4470e65619cf33ac6278.png). The result of the first ![Y](./images/af40f50353f77406a09c621b7bba6537bc9c6750.png) applied to ![\ket{0}](./images/f5eede2beac6072a276e8d8abe4fc0cf90522335.png) is ![Y\ket{0}=i\ket{1}](./images/ea4808d82266478cd4330ca7f0008ffc7016724a.png). Then, applying the second ![Y](./images/af40f50353f77406a09c621b7bba6537bc9c6750.png) operator, we get ![YY\ket{0}=Y(i\ket{1})=iY\ket{1}=i(-i)\ket{0}=\ket{0}](./images/0d98a568ba3d7fb3661bed3358b2ecf01f7f3a59.png). So ![YY\ket{0}=\ket{0}](./images/b8ee974ece876a20d711663b2dbab3724d91cc8b.png). A similar calculation shows that ![YY\ket{1}=\ket{1}](./images/a3a2ae255a58f378987d6eb1ad2e9cb02dfa5dd5.png).

**P9.3** Since ![HH=\mathbbm{1}](./images/b0ce354474e4fa26748451b5b4bbf181d69c12a0.png), we obtain ![XHHY=XY= \begin{bmatrix}i & 0\\0 & - i\end{bmatrix}](./images/bbe09275a3e4a9f5d5e0bb7e152345f0ead3c6ce.png), then multiply this operator by ![\alpha\ket{0} + \beta\ket{1}](./images/5f959a0ca3473d59a1ac6b0a13025fe658407ce6.png) to obtain the answer.

**P9.4** Starting from the four degrees of freedom for general two-dimensional complex vectors, we must subtract one degree of freedom for each of the constraints: one because we’re ignoring global phase, and one because we require ![|\alpha|^2 + |\beta|^2 =1](./images/1a7e3ef8cac9af9b678e83d5e1d9365ee5a5f335.png):

![4 \textrm{ d.f.} \; - \; \alpha \textrm{ real} \; - \;  \{ \| \ket{\psi} \| = 1 \} \; \; = \; \; 2 \textrm{ d.f.}](./images/d5046e70a1777fc2dd2038825e3536bcb75fecd1.png)

A qubit ![\ket{\psi}](./images/8c189fe864f4bb7cfce344e362bf45afabb8a37e.png) has only two degrees of freedom. In other words, two parameters are sufficient to describe any qubit.

**P9.5** Since the squared-magnitudes of the components of ![\ket{\psi}](./images/8c189fe864f4bb7cfce344e362bf45afabb8a37e.png) must be a probability distribution, ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png) is restricted in the range ![[0,1]](../Images/be774047ea995e7d95970f92bc878233711b924c.png). The phase of the second component can be chosen arbitrarily; ![\varphi \in[0,2\pi]](../Images/7f1b4e75055e169a749c061b7da3f666a431be5e.png).

**P9.6** These are the angles of the[_Bloch sphere_](./Bloch_sphere.md), which is a useful way to visualize qubit quantum states.

**P9.9** All three calculations require computing the product of the appropriate projection matrix with the density matrix ![\rho = \begin{bmatrix} |\alpha|^2 & \overline{\beta}\alpha \\  \overline{\alpha}\beta &|\beta|^2 \end{bmatrix}](./images/45801069d0e58a19e2db03d2eea482ca453be622.png), then taking the trace. The[density matrix](./Density_matrix.md) representation is used in many domains of physics, as well as in quantum information theory.

**P9.10**

1.  Expand the expressions for ![\ket{\psi}_1](./images/57b29cc250fc0732da55c9dfcc38c82076561f25.png) and ![\ket{\Phi_+}_{23}](./images/1d847e66995a186330da65e4385f7a060ec73ce6.png) and compute the tensor product.
2.  Using the definitions of the Bell states ![\ket{\Phi_{+}}](./images/eca44bad06b944ced15a2d66ab9732bba53cf30a.png), ![\ket{\Phi_{-}}](./images/e671778c055eefffbe69a6789d0b97721a4742af.png), ![\ket{\Psi_{+}}](./images/8cf9e6e78020f4aa32be528f6aae73ad16fd8d32.png), ![\ket{\Psi_{-}}](./images/5fec45523900ae3af4af6c49874b4053cdefee57.png), and the ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png) and ![Z](./images/f5847940aa9276e4b67acfea096b0baa533528c9.png) operators, we expand the expression on the right side of the equation and show it equals the expression on the left side, which in turn equals ![\ket{\psi}_1 \otimes \ket{\Phi_+}_{23}](./images/455fca0b7e67b8b0fe819ebc46df0211cad74370.png).
3.  Applying the CNOT gate to the state ![\ket{\Phi_{+}} = \tfrac{1}{\sqrt{2}}\!\left( \ket{00} + \ket{11} \right)](./images/1fbafd352dbde3bfd528e3f484161ae6f3987082.png) results in ![\tfrac{1}{\sqrt{2}}\!\left( \ket{00} + \ket{10} \right) =](./images/add538e64e7c96dbd53747416328e4674ba4982c.png) ![\tfrac{1}{\sqrt{2}}\!\left( \ket{0} + \ket{1} \right)\otimes \ket{0}](./images/f198ecee3d7d2b4ede4d00f6880f4df98f940d35.png). Next, applying the Hadamard gate on the first qubit leaves us with the state ![\ket{00}](./images/2510e8c9b00c031639a488f529518955481dfea8.png), which leads to the measurement outcome ![00](./images/38630fc5dbe9613b017f493e6ba81983b5ecd849.png) when both qubits are measured in the standard basis. The analysis for the other bell states is similar.
4.  The recovery operation that Bob must perform is determined by the measurement outcome. Since the ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png) and ![Z](./images/f5847940aa9276e4b67acfea096b0baa533528c9.png) gates are self-inverse, the recovery operations that Bob must perform are described by the following mapping: ![00 \to \mathbbm{1}](./images/c932c62cf2d6598e519a8c90229a030e3ed92898.png), ![10 \to Z](./images/cef2136d4e0fe4d1d864a556eb08aef6e588dfd1.png), ![01 \to X](./images/7400564435d31d40f3e3f060fbf92662934deec3.png), ![11 \to ZX](./images/d0b5239496c68c073a86c66b365af23e7571f487.png).

See this video for more details about the quantum teleportation protocol:[`youtu.be/3wZ35c3oYUE`](./3wZ35c3oYUE_list=PL1826E60FD05B44E4.md).

**P9.11** Using integration by parts with ![u=r^3](./images/38e3ed717e92d730dbf3f08fd5725554aa4505b0.png) and ![dv=\exp(-2r/a)r^2\,dr](./images/c45eed62dbc2e3b1de3eac3ed2cb23c80cbd53cf.png) simplifies the integral to the form ![\frac{3a}{2}(\frac{4}{a^3} \int_0^\infty \exp(\frac{-2 r}{a}) r^2\,dr)](./images/2490e91bfce6e460ee41d527f2e8e986d9c3d1de.png). Instead of continuing with two more steps of integration by parts, we can recognize the expression inside the brackets to be equal to one, since ![\psub{R}(r)=\frac{4}{a^3}\exp(-2r/a)r^2](./images/990cd4f653b104090787668b36921558f85ea817.png) is a probability distribution. This calculation supports the classical chemical viewpoint, which describes electrons as living in an “electron cloud” or “orbital” of radius roughly ![\frac{3}{2}a](./images/7973aa74730cb28dbcaa18955ef74bd9823c32f7.png). Note this is somewhat misleading since the actual wave function ![\psi(\vec{r})](./images/adc055de0081d3eab68849bc6c74cb27b2fc9e88.png) drops off as ![\exp(-r)](./images/43753a7f85238b07496a0f1ff6fe8a8453814ff1.png).

**P9.12** The inner product ![\braket{\psi_1 ,\psi_2} = \int_0^1 \overline{\psi_1(x)} \psi_2(x)\,dx](./images/e7dd2983ec72e8f15f6e63f417b8115aa0ef4c48.png) corresponds to the integral ![\int_0^1 (2x-1)(6x^2-6x+1)\,dx=\int_0^1 (12x^3 - 18x^2 + 8x -1)\,dx](./images/bb824ae63187af5c75a97eb4fba15e4d68b3c2bd.png). Using the formula ![\int x^n\,dx= \frac{x^{n+1}}{n+1}](./images/f454aef0b3f71b3c7e2181d38285b3432c719c85.png), we find ![\braket{\psi_1 ,\psi_2} = \left[ \frac{12}{4}x^4 - \frac{18}{3}x^3 + \frac{8}{2}x^2 - x\right]^1_0 = 0](../Images/62889747da78a06fef1366308d0b27553e3bc056.png). The functions ![\psi_1(x)](./images/827d59d72e790f3b715a1d4f828dd19e9b860ba5.png) and ![\psi_2(x)](./images/00546c8521e6b6ea025ac166dfc159cf081ecdf8.png) are called the[_Shifted Legendre polynomials_](./Legendre_polynomials.md).

**P9.13** You can perform the required integrals by hand or use the[`SymPy`](./live.sympy.org.md) command `integrate((sqrt(3)*(2*x-1))**2,(x,0,1/4))` for part **a)**. For part **b)**, use the command `integrate((sqrt(5)*(6*x**2-6*x+1))**2,(x,0,1/4))`. For part **c)**, the constant wave function is ![\psi_c(x)=1](./images/edba62e304764616a83b3d80c9c57cbaf3ae3ed0.png), and the interval ![[0,\frac{1}{4}]](../Images/b02ac5665aeb2a8aa27fd2fdabe534ce8233bcf7.png) contains exactly ![\frac{1}{4}](./images/16f97df2aae4eaf5797114583fd4e7d61a7b6cf6.png) of its probability mass.

#[Notation](./End matter.md)

This appendix contains a summary of the notation used in this book.

##[Math notation](./Front matter.md)

Expression

Read as

Used to denote

![a,b,x,y](./images/60d71b480be26072fd109b324566bbbe8de2036d.png)

variables

![=](./images/b8ca3693499b05d77b159c39cca4f9b6fd74d54e.png)

is equal to

expressions that have the same value

![\eqdef](./images/2cb557e51c5e620a2a873c7db18d9322bc09397e.png)

is defined as

new variable definitions

![a+b](./images/1f747de8510cd5c6b556549a7eb6b39fef3d16ed.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) plus ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)

the combined lengths of ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)

![a-b](./images/e9396bae98fa3009be2d2e8fd76ee7defaa7a68f.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) minus ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)

the difference in lengths between ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) and ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)

![a\times b = ab](./images/99a9c76beb474803a3d84aab5704b5ad6bd750d9.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) times ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)

the area of a rectangle

![a^2 \eqdef aa](./images/34bd0c4024dc0241c2fde9620f0e4a1d9789ff52.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) squared

the area of a square of side length ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

![a^3 \eqdef aaa](./images/9bbf217411abb3a8d5091b86b9d67c22c5c653d3.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) cubed

the volume of a cube of side length ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

![a^n](./images/66446eb2bd89fe989ffb3bc5e8f3c6bdd67033cf.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) exponent ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) multiplied by itself ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) times

![\sqrt{a} \eqdef a^{\frac{1}{2}}](./images/bce2fc6b1e87d8253b1b1dcd677c813a5cf2df59.png)

square root of ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

the side length of a square of area ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

![\sqrt[3]{a}\eqdef a^{\frac{1}{3}}](../Images/2251fb50bc884e918670622557e119b26ef148db.png)

cube root of ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

the side length of a cube with volume ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

![a/b = \frac{a}{b}](./images/cce71517796f2bca157643e75af9312ed97c2465.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) divided by ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) parts of a whole split into ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) parts

![a^{-1}\eqdef \frac{1}{a}](./images/6c605d37c0864a3654551bfc4ae65d1343ba9975.png)

one over ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

division by ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png)

![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

the function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) applied to input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

![f^{-1}](./images/2231561c3a0470d90648725ab4379015da33fe37.png)

![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) inverse

the inverse function of ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png)

![f \circ g](./images/525b5a0d10c1db2e3036359cd5005c80a885d52d.png)

![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) compose ![g](./images/1946b9850ac13de564c7e979735a85b5419ff434.png)

function composition; ![f \circ g(x) \eqdef f(g(x))](./images/733acda9b8b71feabd984e7567db9cdfdfb46b0e.png)

![e^x](./images/4f0ced03d137197bad0d134b4967fb961efde701.png)

![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png) to the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

the exponential function base ![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png)

![\ln(x)](./images/ac737e1e2f55643d55061ce3d81125603dfe30fd.png)

natural log of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

the logarithm base ![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png)

![a^x](./images/e640997799d5c4a655ce63088bcea1533d150c1d.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) to the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

the exponential function base ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

![\log_a(x)](./images/a862f6d95048c38d65b388c19507123e0a74322e.png)

log base ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

the logarithm base ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png)

![\theta,\phi](./images/11a0ea3dddaa709a62c5fdc36900073f3b874ebf.png)

_theta_, _phi_

angles

![\sin,\cos,\tan](./images/7360318bcc03ae052a3092ed971f572e4327a1aa.png)

sin, cos, tan

trigonometric ratios

![\%](./images/82ea2be5161407eac522175669b465b7e9d6e4c4.png)

percent

proportions of a total; ![a\% \eqdef \frac{a}{100}](./images/8c5d2aeb6857c96392cf70df026ac818d264f3f9.png)

##[Set notation](./Front matter.md)

You don’t need a lot of fancy notation to do math, but it really helps if you know a little bit of set notation.

Symbol

Read as

Denotes

![\{ \; \ldots \;  \}](./images/05c1e2baef54f8458c557289116154cd12c69a04.png)

the set ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png)

definition of a set

![|](./images/87e0224147ed550dbca19b1b3c52d6b8482983bc.png)

such that

describe or restrict the elements of a set

![\mathbb{N}](./images/bafa4736281babd323c41d9dbdcbc6784e7e82e1.png)

the naturals

the set ![\mathbb{N} \eqdef \{0,1,2,\ldots\}](./images/6d6c538cfd310bf29b7cffa01b0507339f6d10dc.png). Also ![\mathbb{N}_+\!\! \eqdef \mathbb{N}\! \setminus \! \!\{ 0\}](./images/1c9c9f3f21b10531bd795924af3d3ed816f6efa9.png).

![\mathbb{Z}](./images/3636b0a74fb9602986d02bfdab407ba5c85666a6.png)

the integers

the set ![\mathbb{Z} \eqdef\{\ldots,-2,-1,0,1,2,3,\ldots\}](./images/810b3d1d710dbedbd1b8f1f53f917bf0f0466a03.png)

![\mathbb{Q}](./images/6cb1ea57b10c031e15759835fc2b40301a8f534d.png)

the rationals

the set of fractions of integers

![\mathbb{R}](./images/83d725a6c70734dbd28878885a1518dc28ba0c3d.png)

the reals

the set of real numbers

![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png)

the set of complex numbers

![\mathbb{F}_q](./images/d8fd0f1eff28d9e6d2783aadef13a973c284ce38.png)

finite field

the set ![\{0,1,2,3,\ldots,q-1\}](./images/847c6f1e2fddb9b0cc9ec985c9daa76e91e03ede.png)

![\subset](./images/7510dd7840f1a976551de242eb1c540756851d87.png)

subset

one set strictly contained in another

![\subseteq](./images/841f77c050e8b8386a24b9a2913fde53e70dc8d1.png)

subset or equal

containment or equality

![\cup](./images/91697a2784b0c0c91152aa400907a9286e8d78ac.png)

union

the combined elements from two sets

![\cap](./images/6653e0186c1b6c0cfb5f14fca0ad426ed37d46e6.png)

intersection

the elements two sets have in common

![S\setminus T](./images/a7d1a54ac39a5095d67083779d95885a475da6f5.png)

![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) set minus ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png)

the elements of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png) that are not in ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png)

![a\in S](./images/444c81c894d21e059d4112c3a72fc73140a8e0ae.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) in ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) is an element of set ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)

![a\notin S](./images/b3f648a10eee36f8012c674a1e4f60e98c5013b0.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) not in ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)

![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) is not an element of set ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)

![\forall x](./images/5f7ffcd46cda3820e3c703c0c3c8a5725ea1bf77.png)

for all ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

a statement that holds for all ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

![\exists x](./images/19fc01e6f48c1911c709156a2044efab5ae01b25.png)

there exists ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

an existence statement

![\nexists x](./images/639e12a4873f6781eda5fbc0af5733292f74bcc3.png)

there doesn’t exist ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)

a non-existence statement

![S \times T](./images/cff3b72a1926d7e35ed8437e3daf77061de20997.png)

Cartesian product

all pairs ![(s,t)](./images/dfa51b2dc0a66fb2b46afc9f65fcfec9b111c1d8.png) where ![s \in S](./images/02f420ef6d8d77045e6d12b4b8461fe14149bb48.png) and ![t \in T](./images/bb8d13cde9e4084c9f0c98c07e3320f2a95112de.png)

An example of a condensed math statement that uses set notation is “![\nexists m, n \in \mathbb{Z}](./images/9dc26bfbc8217c0da7f60c77b89dde6db92c7df0.png) such that ![\frac{m}{n}=\sqrt{2}](./images/e84d5edac2b557e0be7ce33a1ce29553cbb16a90.png),” which reads “there don’t exist integers ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) and ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) whose fraction equals ![\sqrt{2}](./images/6715b8265ad0d01e2040fdb8d7b64f78ff347978.png).” Since we identify the set of fractions of integers with the rationals, this statement is equivalent to the shorter “![\sqrt{2} \notin \mathbb{Q}](./images/02d257cd493cfa6991e76da165957cf4277b28aa.png),” which reads “![\sqrt{2}](./images/6715b8265ad0d01e2040fdb8d7b64f78ff347978.png) is irrational.”

##[Vectors notation](./Front matter.md)

Expression

Denotes

![\mathbb{R}^{n}](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png)

the set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional real vectors

![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png)

a vector

![(v_x,v_y)](./images/bf08d8f270c5ace12ee18ba92752c926e1cd6f5b.png)

vector in component notation

![v_x\hat{\imath}+v_y\hat{\jmath}](./images/f0036010de1060a23c2de008f95980b962ca7681.png)

vector in unit vector notation

![\|\vec{v}\|\angle \theta](./images/b77607ccac4e718ad4616e60146f7b92ff220142.png)

vector in length-and-direction notation

![\|\vec{v}\|](./images/8f866786ba2376f2849ed080dcb2433d9371ba0f.png)

length of the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png)

![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png)

angle the vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) makes with the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis

![\hat{v} \eqdef \frac{\vec{v}}{ \| \vec{v} \|}](./images/99d70f51fad4c8629640e1aa40edcdc11db7ec00.png)

unit vector in the same direction as ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png)

![\vec{u} \cdot \vec{v}](./images/c2c14c66057b2918741cbf6c703fc3f8cce131ee.png)

dot product of the vectors ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png)

![\vec{u} \times \vec{v}](./images/463be6a293fa8d06d54e2b035e190791aabbaa4c.png)

cross product of the vectors ![\vec{u}](./images/0a6a0dc6c48a541e8c9ef0851ba4744ea6e79c36.png) and ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png)

##[Complex numbers notation](./Front matter.md)

Expression

Denotes

![\mathbb{C}](./images/f71db6f61019f5429691529e568fd48b01b6079c.png)

the set of complex numbers ![\mathbb{C} \eqdef \{ a + bi \;  | \;  a,b \in \mathbb{R} \}](./images/5869118a48ac96c707d8089e031c90809c84b33f.png)

![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)

the unit imaginary number ![i \eqdef \sqrt{-1}](./images/a150c889c82f67cc0caa0a50fb9bcf627717e926.png) and ![i^2 = -1](./images/8f6a05a5a173cf1a23631e03a53b0a172a46ad47.png)

![\textrm{Re}\{ z \}=a](./images/8b547f862cc767345407ed8c9d15d7cfcb040df6.png)

real part of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)

![\textrm{Im}\{ z \}=b](./images/f4a43c5803f6b41ac5012e4f5528ec4708e9a5de.png)

imaginary part of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)

![|z|\angle \varphi_z](./images/c7f2f949a2c7dca299140bbe5be3b37e4bdc16d4.png)

polar representation of ![z = |z|\cos\varphi_z + i|z|\sin\varphi_z](./images/dd57e88abe2a200c7b5461f1d643860b204a7914.png)

![|z|=\sqrt{a^2+b^2}](./images/3cd2af1870435b4ef2aa2866580cf4ad4e68258f.png)

magnitude of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)

![\varphi_z=\tan^{-1}(b/a)](./images/9b52f1f96c094bbbcf3ed3b5754f991e735cf9e2.png)

phase or argument of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)

![\overline{z}=a-bi](./images/5f7e626aa098fb8021f6523d683f1bcf7468ec57.png)

complex conjugate of ![z=a+bi](./images/17b41d0e4a44d73efe73a4657992f9f7d35734b2.png)

![\mathbb{C}^{n}](./images/5e85dd74e099e5e8c750c0e9a5e0cdadfd1feba8.png)

the set of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional complex vectors

##[Vector space notation](./Front matter.md)

Expression

Denotes

![U,V,W](./images/afa0f3fb4e8f9c4c6cb3a4c19c81bff8b15b5183.png)

vector spaces

![W \subseteq V](./images/fe3c4c0997eb9a8f0f62a9774b91a1b0a2e5aaf2.png)

vector space ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png) subspace of vector space ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)

![\{\vec{v} \in V \, | \, \, \langle\texttt{cond}\rangle \, \}](./images/6e553afd6133b1f1b2c950f11ef3a4005fe4225a.png)

subspace of vectors in ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) satisfying condition ![\langle\texttt{cond}\rangle](./images/e8b6dd30bdfbee1f1dc0c526848ecb3e0b863fd4.png)

![\textrm{span}(\vec{v}_1,\ldots, \vec{v}_n)](./images/6280cb7f7917fa486093e922002e6a0c3e0581ed.png)

span of vectors ![\vec{v}_1, \ldots, \vec{v}_n](./images/e10bcecbde645bcf1016f8ce4d6e32e2d014df5f.png)

![\textrm{dim}(U)](./images/39429e204b5a7b77f2a7c92527c8a409cebed629.png)

dimension of vector space ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png)

![\mathcal{R}(M)](./images/61a4071689dae6b91184f94760c9ed7e9c6d88d1.png)

row space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png)

![\mathcal{N}(M)](./images/b2b278a718926bbd8fe6fd73a60a504f938642b4.png)

null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png)

![\mathcal{C}(M)](./images/041f2eb567ff07b61707a135e5034908da7356fb.png)

column space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png)

![\mathcal{N}(M^\sfT)](./images/0363059816fea5757210b13c001a730e237cbead.png)

left null space of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png)

![\textrm{rank}(M)](./images/30d29f723fc33a519f304d9e6bd11a33b5a7a33b.png)

rank of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png); ![\textrm{rank}(M)\eqdef\textrm{dim}(\mathcal{R}(M))=\textrm{dim}(\mathcal{C}(M))](./images/2831fe535ab9e0c0691990a5eceb7bbd7adbfcb8.png)

![\textrm{nullity}(M)](./images/36e1608e1027b0638e46a221e5d77c7b6de57155.png)

nullity of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png); ![\textrm{nullity}(M)\eqdef\textrm{dim}(\mathcal{N}(M))](./images/3a52b8e4fc9d2906954d44c6f415093402b1ca7e.png)

![B_s](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png)

the standard basis

![\{\vec{e}_1, \ldots, \vec{e}_n\}](./images/96eb34b2dcd7da1e692a4d29f5e5d2abb271dfd1.png)

an orthogonal basis

![\{\hat{e}_1, \ldots, \hat{e}_n\}](./images/dfbb3d78dc546c5d414bcbe75d3c0237e1122d0e.png)

an orthonormal basis

![\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/029b9a61176cd5f29400e699e84a44a9f08e60cd.png)

the change-of-basis matrix from basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) to basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png)

![\Pi_S](./images/bb92730a68612a6546559230103e501cfe6e21a7.png)

projection onto subspace ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)

![\Pi_{S^\perp}](./images/11fcfc12e8198c56be561ee9aa01f7cd43367253.png)

projection onto the orthogonal complement of ![S](./images/1d085e5a07142ece188179070ee0a5330609c549.png)

##[Abstract vector spaces notation](./Front matter.md)

Expression

Denotes

![(V, F, +, \cdot)](./images/3f96d7df630be29a65d98b3dbcdb12830f78c147.png)

abstract vector space of vectors from the set ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), whose coefficients are from the field ![F](./images/fde085937972221cc351ca105835c8b5a11aa591.png), addition operation “![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png)” and scalar-multiplication operation “![\cdot\,](./images/4ec995749ae8ac4da25df2280a67757c0f5df1f2.png)”

![\mathbf{u},\mathbf{v},\mathbf{w}](./images/10dc55742b341d5c28693c9c2477794883297407.png)

abstract vectors

![\langle \mathbf{u},\mathbf{v} \rangle](./images/3b9ee96b30fdf71f77bac471145faa2692f7d7b1.png)

inner product of vectors ![\mathbf{u}](./images/fdef05356517f4e74d2a56deccef430681ee4bfa.png) and ![\mathbf{v}](./images/633b84ab115cc79e0751cfddae6cfadae6fca32b.png)

![\| \mathbf{u} \|](./images/7687a07feabdd3baac20c0ca1979ebad7a3d9099.png)

norm of ![\mathbf{u}](./images/fdef05356517f4e74d2a56deccef430681ee4bfa.png)

![d(\mathbf{u},\mathbf{v})](./images/d0a0982e39869b4701fbc79ed8b74ed0588d92b6.png)

distance between ![\mathbf{u}](./images/fdef05356517f4e74d2a56deccef430681ee4bfa.png) and ![\mathbf{v}](./images/633b84ab115cc79e0751cfddae6cfadae6fca32b.png)

##[Notation for matrices and matrix operations](./Front matter.md)

Expression

Denotes

![\mathbb{R}^{m \times n}](./images/e0107482dfd257822ffe0115cf94429a3196e6c5.png)

the set of ![m \times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrices with real entries

![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

a matrix

![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png)

entry in the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th row and ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th column of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

![|A|](./images/f395085915c0b82f3f55aa5551b1676f28378881.png)

determinant of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), also denoted ![\det(A)](./images/15858c058152cc1c34d1695876240fa759d3ff0a.png)

![A^{-1}](./images/470721386b3ed37ecad20851d6614bec164aa877.png)

matrix inverse

![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png)

matrix transpose

![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png)

identity matrix; ![\mathbbm{1}A=A\mathbbm{1}=A](./images/2ea7a72d8d40155bfd804b0b7763bb4f9ee9c14e.png) and ![\mathbbm{1}\vec{v}=\vec{v}](./images/51c805cb90f920dcdb1371614e5b3eb0770dfdec.png)

![AB](./images/5f4c229ac7bb206619ccb6b37f3f4869b2632cba.png)

matrix-matrix product

![A\vec{v}](./images/7f9f917ef64cac1364cf488fd6017afa872a4ef3.png)

matrix-vector product

![\vec{w}^\sfT \!A](./images/b3c37e23de728a3775e07245dd292758a138788e.png)

vector-matrix product

![\vec{u}^\sfT \!\vec{v}](./images/bb85036a1f627ef3799ee6d631de067d0793fbce.png)

vector-vector inner product; ![\vec{u}^\sfT \!\vec{v} \eqdef \vec{u} \cdot \vec{v}](./images/ec8e281bd51251f208d23fd26d12f7688c973e49.png)

![\vec{u}\vec{v}^\sfT](./images/e9e2698be3fbcd275db30173393a484b3894974e.png)

vector-vector outer product

![\textrm{ref}(A)](./images/c57cc149dba89c48c553392e3243eaadf4591c39.png)

row echelon form of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

![\textrm{rref}(A)](./images/bd243681e4ed2b131e5732052a4caccd4b17cd11.png)

reduced row echelon form of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

![\textrm{rank}(A)](./images/ed9af0029991b2f3fe54ea738272a568e5f5880a.png)

rank of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) ![\eqdef](./images/2cb557e51c5e620a2a873c7db18d9322bc09397e.png) number of pivots in ![\textrm{rref}(A)](./images/bd243681e4ed2b131e5732052a4caccd4b17cd11.png)

![A \sim A'](./images/616d29aece8be6d229234989cae5e506ff67c17f.png)

matrix ![A'](./images/159d093543a2410fe352596d95c1c568f45cab01.png) obtained from matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by row operations

![\mathcal{R}_1, \mathcal{R}_2, \ldots](./images/d5a2874f8699726c4f91710d86dd3a3599f22637.png)

row operations, of which there are three types:

![\quad\rightarrow](./images/2dded950f0442206fea6d9e6d274c5f43fd57ec4.png) ![R_i \gets R_i + k R_j](./images/594e507ec2195588028ae723c9dd11dea98de1d0.png): add ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png)\-times row ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) to row ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)

![\quad\rightarrow](./images/2dded950f0442206fea6d9e6d274c5f43fd57ec4.png) ![R_i \leftrightarrow R_j](./images/ce9758117ca43592e749c375bdef2dc382d1b566.png): swap rows ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) and ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)

![\quad\rightarrow](./images/2dded950f0442206fea6d9e6d274c5f43fd57ec4.png) ![R_i \gets m R_i](./images/40718d9d90d94ec6f0e1e18788ac91f74d237f16.png): multiply row ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) by constant ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png)

![E_{\mathcal{R}}](./images/1dcf3505688a7912c896e9126ae744b2aef2a194.png)

elementary matrix for row operation ![\mathcal{R}](./images/292f5e6542a43a174b008b49eaff3627381bc3d0.png); ![\mathcal{R}(M) \!\eqdef\! E_{\mathcal{R}}M](./images/8db178643e04a056bb5f2edccd9a543b3de941eb.png)

![[\, A \; |\; \vec{b} \; ]](../Images/ca80087adfe2155c69bab4b33bd5585e0ce2954a.png)

augmented matrix containing matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png)

![[\, A \; |\; B \; ]](../Images/ce25cee85a5c33ccf756e1887c53ca9581a27c41.png)

augmented matrix array containing matrices ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)

![M_{ij}](./images/443e3b60ab8c4d4c944621decdf87e8d95310edd.png)

minor associated with entry ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png). See page 3.5.2.

![\textrm{adj}(A)](./images/b5ba597b443e849b8a4e8c8f28702579f95df26d.png)

adjugate matrix of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). See page 3.5.2.

![(A^\sfT \! A)^{-1}\!A^\sfT](./images/f0c922131c7c75664685c20db107793eba57a798.png)

Moore–Penrose inverse of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). See page 7.7.

![\mathbb{C}^{m \times n}](./images/44abc05b131ab500106dd687c35de58b42d4c30e.png)

the set of ![m \times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrices with complex entries

![A^\dagger](./images/3763a4fed4d19a6bb65a04d027dc9aa010a3ee60.png)

Hermitian transpose; ![A^\dagger \eqdef (\overline{A})^\sfT](./images/1172491c96e01ef926b1efbccb88ab76f0ed54f8.png)

##[Notation for linear transformations](./Front matter.md)

Expression

Denotes

![T:\mathbb{R}^{n} \to \mathbb{R}^{m}](./images/b2b29081b967253c6ee350a713a0102cf22ec526.png)

linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) from the input space ![\mathbb{R}^{n}](./images/12c50013ba8e70391907f05b9e8eedb455818a81.png)

to the output space ![\mathbb{R}^{m}](./images/4d4f5acbadc1b9a3febf3642dbe25d99a4704061.png)

![M_T \in \mathbb{R}^{m \times n}](./images/941601a4ecd9670b4e8d5963fcb6365be4ae7908.png)

matrix representation of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png)

![\textrm{Im}(T)= \mathcal{C}(M_T)](./images/5be1a484e15e9828647cb1f451c932882193e6dc.png)

the image space of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) ![=](./images/b8ca3693499b05d77b159c39cca4f9b6fd74d54e.png) column space of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png)

![\textrm{Ker}(T)= \mathcal{N}(M_T)](./images/5039b1220a13b0f9d12b4d69737f99c015aa0ea7.png)

the kernel of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) ![=](./images/b8ca3693499b05d77b159c39cca4f9b6fd74d54e.png) null space of ![M_T](./images/a864c858f377715775bb9941686e85c5eea67167.png)

![S \circ T(\vec{x})](./images/5644e0bcf8fc739a9975d3aac9a47c7632be6132.png)

composition of linear transformations;

![S \circ T(\vec{x}) \eqdef S(T(\vec{x})) = M_SM_T\vec{x}](./images/b8b47eb5390ccff0b73cefd0aea6b67989aa8b4f.png)

![M \in \mathbb{R}^{m \times n}](./images/d14b5d2cce3a462cb51f112b439784a9e31a6ba4.png)

an ![m \times n](./images/296adf1031dd46f28e7427f071b56e413b60279b.png) matrix

![T_M:\mathbb{R}^{n} \to \mathbb{R}^{m}](./images/d614512014c4b2224d731e9951a540c501bead6e.png)

the linear transformation defined as ![T_M(\vec{v})\eqdef M\vec{v}](./images/0b854a0b761eb20ce0bbc24e20c4d1a691d3eb91.png)

![T_{M^\sfT}:\mathbb{R}^{m} \to \mathbb{R}^{n}](./images/f509e202c6732b5058f67e19e88c6ccd0518e300.png)

the adjoint linear transformation ![T_{M^\sfT}(\vec{a}) \eqdef \vec{a}^\sfT \!M](./images/17f831ee2368e645e65d6b35311d2dbfc14888df.png)

##[Matrix decompositions](./Front matter.md)

Expression

Denotes

![A \in \mathbb{R}^{n \times n}](./images/2f056442410016d3a541715471950849562de0c4.png)

a matrix (assume diagonalizable)

![p_A(\lambda)\!\eqdef \!|A-\lambda\mathbbm{1}|](./images/405a02a1a9bffdfd459987afb8513e4363268935.png)

characteristic polynomial of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

![\lambda_1, \ldots, \lambda_n](./images/8523eb6c9411775bee87d3b022bcf14223c04172.png)

eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) = roots of ![p_A(\lambda)](./images/4bc02a515f32b8569dffa981fc40e6800c99ee51.png)

![\Lambda \in \mathbb{R}^{n \times n}](./images/338ef8f2a4602b872aab7444e887067447c53894.png)

diagonal matrix of eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

![\vec{e}_{\lambda_1}, \ldots, \vec{e}_{\lambda_n}](./images/ef01f6992795100e7c5fae7a9bdbb4e0d8d26fb7.png)

eigenvectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

![Q \in \mathbb{R}^{n \times n}](./images/2b7c682842a2b24a9f5b9fb74a7e8aae82c5c482.png)

matrix whose columns are eigenvectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

![A=Q\Lambda Q^{-1}](./images/f466d5b0107bfb4fbe7ccf5d545d612f49234648.png)

eigendecomposition of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)

![A=O\Lambda O^\sfT](./images/5fb620b0c1b0c45951af03774a36b6c5267fb2f9.png)

eigendecomposition of a normal matrix

![B \in \mathbb{R}^{m \times n}](./images/3c88c8becc49bd444f9d20d7192dc667616c9608.png)

a generic matrix

![\sigma_1, \sigma_2, \ldots](./images/e76a1b375182a10eb9c8a682cd0c04642168c05c.png)

singular values of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)

![\Sigma \in \mathbb{R}^{m \times n}](./images/5f44d2dc6782c9cde2ff37c3101636ab4048920a.png)

matrix of singular values of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)

![\vec{u}_{1}, \ldots, \vec{u}_m](./images/a1a565074aed95a21b1022636000eef6735b061c.png)

left singular vectors of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)

![U \in \mathbb{R}^{m \times m}](./images/0201d9e6913d30f1592835f54a1d24ca8146db61.png)

matrix of left singular vectors of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)

![\vec{v}_{1}, \ldots, \vec{v}_n](./images/e10bcecbde645bcf1016f8ce4d6e32e2d014df5f.png)

right singular vectors of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)

![V \in \mathbb{R}^{n \times n}](./images/228673f875d9da32f2f49a595d1bf0ae079a0d8e.png)

matrix of right singular vectors of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)

![B=U\Sigma V^\sfT](./images/0f24a43a2653c4175e48f22fad3e588386d49391.png)

singular value decomposition of ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png)

[1.](./Front matter.md) We’re assuming the detector has 100% efficiency (detects every photon that arrives at it) and generates zero noise (no false-positive clicks).

[2.](./Front matter.md) This is where the name _wave function_ comes from.
