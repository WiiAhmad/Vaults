Chapter 8      

#[Chapter 8 Probability theory](./Chapter 8_ Probability theory.md)

In this chapter, we’ll use linear algebra concepts to explore the world of probability theory. Think of this as bonus material because the topics we’ll discuss are not normally part of a linear algebra course. Given the general usefulness of probabilistic reasoning and the fact that you have already covered all the prerequisites, it would be a shame _not_ to learn a bit about probability theory and its applications.

The chapter is structured as follows. In[Section 8.1](./Chapter 8_ Probability theory.md), we’ll discuss probability distributions, which are mathematical models for describing random events.[Section 8.1.10](./Chapter 8_ Probability theory.md) introduces the concept of a _Markov chain_, which can be used to characterize the random transitions between different states of a system. Of the myriad of topics in probability theory, we’ve chosen to discuss probability distributions and Markov chains because they correspond one-to-one with vectors and matrices. This means you should feel right at home. In[Section 8.1.15](./Chapter 8_ Probability theory.md), we’ll describe Google’s PageRank algorithm for ranking webpages, which is an interesting application of Markov chains.

##[8.1 Probability distributions](./Chapter 8_ Probability theory.md)

Many phenomena in the world are inherently unpredictable. When you throw a six-sided die, one of the outcomes ![\{ 1, 2, 3, 4, 5, 6\}](./images/95e76504e6d6c90f7220b23f295a144e380a386f.png) will result, but you don’t know which one. Similarly, when you toss a coin, you know the outcome will be either `heads` or `tails` but you can’t predict which outcome will result. Probabilities are used to describe events where uncertainty plays a role. We can assign probabilities to the different outcomes of a dice roll, the outcomes of a coin toss, and also to many real-world systems. For example, we can build a probabilistic model of hard drive failures using past observations. We can then calculate the probability that your family photo albums will survive the next 10 or 20 years. Backups my friends, backups.

Probabilistic models can help us better understand random events. The fundamental concept in probability theory is that of a _probability distribution_, which describes the likelihood of different outcomes of a random event. For example, the probability distribution for the roll of a fair die is ![\psub{X} = (\frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6})^\sfT](./images/590e73a1c1e950b03dea72b136d6a215e4885be0.png), and the probability distribution for a coin toss is ![\psub Y = (\frac{1}{2}, \frac{1}{2})^\sfT](./images/577101ca387828b42a56f22b31919d9c363a4ceb.png). Each entry of a probability distribution corresponds to the _probability mass_ of a given outcome. This terminology borrows from the concept of mass distribution used in physics. The entries of a probability distribution satisfy the following conditions: each entry is a nonnegative number, and the sum of the entries is one. These two conditions are known as the _Kolmogorov axioms_ of probability.

Strictly speaking, understanding linear algebra is not required for understanding probability theory. However, vector notation is very effective for describing probability distributions. Your existing knowledge of vectors and the rules for matrix multiplication will allow you to quickly understand many concepts in probability theory. Probabilistic reasoning is highly useful, so it’s totally worth taking the time to learn about it.

###[Random variables](./Front matter.md)

A random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is described by a probability distribution ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png). Before we formally define the notion of a probability distribution, we must introduce some formalism. We denote by ![\mathcal{X}](./images/32a4c19efc930fae17f63aa5e07a8fe5b73def06.png) (calligraphic ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png)) the _sample space_ of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png), which is the set of all possible outcomes of the random variable. A _discrete_ random variable has a finite sample space. For example, we can describe the outcome of rolling a six-sided die using the random variable ![X \in \mathcal{X}](./images/7ec79ad4ea8c1a7b641f4e81ea74a56ec640d997.png), where the sample space is ![\mathcal{X}=\{1, 2, 3, 4, 5, 6 \}](./images/d2f04d0401951d55fedd637431da4be49c85ee63.png). The number of possible outcomes is six: ![|\mathcal{X}|=6](./images/c881349bab92b6e5de10c6fe16aabc6874525c00.png).

We can describe the random outcome of a coin toss as a random variable ![Y \in \{\texttt{heads}, \texttt{tails} \}](./images/beecbd5c8e48b9510cfbfb5f4fc003967de1aabd.png). The possible outcomes of the coin toss are ![\mathcal{Y}=\{\texttt{heads}, \texttt{tails} \}](./images/b19fa8b3985dcfbfcbc1858ecd5615e3ed5bebd4.png). The number of possible outcomes is two: ![|\mathcal{Y}|=2](./images/5ae08af78cd0d062d6a9c69bfaf5e540e0e336b3.png).

In the case of the hard drive failure model, we can define the random variable ![L \in \mathbb{N}](./images/77190cc78604bc615493cd81a8ee9ac41fefcff2.png) as the years of a hard drive’s lifetime before it fails. Using the random variable ![L](./images/8344682567e06566040f4cde165f91b06c4ee6f5.png) we can describe interesting scenarios using probabilistic reasoning. For example, the condition that a hard drive will function correctly for at least eight years can be described as ![L \geq 8](./images/85a3c820b7a7302aff56a7880fcb6f67d51547f5.png).

###[Probability distributions](./Front matter.md)

The probability distribution of a discrete random variable ![X \in \mathcal{X}](./images/7ec79ad4ea8c1a7b641f4e81ea74a56ec640d997.png) is a vector of ![|\mathcal{X}|](./images/d45c64a23b4c427a9b2557e222b7173f028c543f.png) nonnegative numbers that sum to one. Using mathematically precise notation, we write the definition of ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) as follows:

![\psub X \in \mathbb{R}^{|\mathcal{X}|} 
\quad \textrm{such that} \quad 
\psub X(x) \geq 0,  \forall x \in \mathcal{X} 
\;  \; \textrm{and} \;   \; 
\sum_{x \in \mathcal{X}} \psub X(x) = 1.](./images/8e78acb9f1d84098db3f2e79b3cc289c2798ca98.png)

A probability distribution is a vector in ![\mathbb{R}^{|\mathcal{X}|}](./images/9644e41d931e9a4757d8dac1b7662a380e9d08c0.png) that satisfies two special requirements: its entries must be nonnegative and the sum of the entries must be one.

###[Events](./Front matter.md)

In addition to the individual outcomes of a random variable, we can define _events_ that consist of compositions of individual outcomes. Events correspond to different subsets of the sample space and are usually defined using words like “![\{ \textrm{event description} \}](./images/fb0184129531c95778c10f3ca5a7023ee213d788.png),” which is the standard curly-bracket notation used to denote sets and subsets.

Recall the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) that describes the outcome of rolling a six-sided die. The sample space for this random variable is ![\mathcal{X} = \{1,2,3,4,5,6\}](./images/d2f04d0401951d55fedd637431da4be49c85ee63.png). We can define various events that involve the six-sided die and describe them as subsets of the sample space. For example, the event ![\{ X \textrm{ is odd} \}](./images/dfcb66844c94840e752d784d36e682503338b243.png) corresponds to the subset ![\{1,3,5\} \subset \mathcal{X}](./images/ba25649376c3d6ba004eb6e0e42846784ca04f87.png).

Events are useful because they allow us to describe specific combinations of outcomes that are of practical interest. We can use the logical operators `OR` and `AND` to define composite events. The logical `OR` operator for events corresponds to the union operation for sets. For example, ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) resulting in an odd number,

![\{ X \textrm{ is odd} \} \; = \;  \{ X = 1 \} \texttt{ OR } \{ X = 3 \} \texttt{ OR } \{ X = 5 \},](./images/caeaf693bb6d62fce9161b001c5db0ed2d923a76.png)

corresponds to the union of sets ![\{1\} \cup \{3\} \cup \{5\} = \{1,3,5\} \subset \mathcal{X}](./images/5e18e20371e6d788e8010028914e86284e4215d5.png).

The logical `AND` operator corresponds to the intersection of sets, and is often used to describe composite events that involve multiple random variables.

With these simple principles for describing probabilistic phenomena, we can build rich combinations of random events, expectations, and statistics—and develop methods for predicting the likelihood of future events. In the remainder of this section, we’ll explore concepts of probabilistic reasoning through a series of examples.

#####[Example 1](./Front matter.md)

Consider again the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) that describes the outcome of rolling a six-sided die. Assuming the die is fair, the probability distribution of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is

![\psub X = \colvec{\tfrac{1}{6} \\ \tfrac{1}{6} \\ \tfrac{1}{6} \\ \tfrac{1}{6} \\ \tfrac{1}{6} \\ \tfrac{1}{6}  }
\begin{array}{l}
\leftarrow \psub X(1) \\
\leftarrow \psub X(2) \\
\leftarrow \psub X(3) \\			
\leftarrow \psub X(4) \\
\leftarrow \psub X(5) \\
\leftarrow \psub X(6)						
\end{array}.](./images/12e9901c3e99698f9d6c14857479f07fe589686c.png)

The probability distribution ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) is a six-dimensional vector and the probability of each outcome is ![\frac{1}{6}](./images/93229e067d9c29b3c8434f4f0debca56efb90322.png). The sum of the entries is one.

Let’s take a moment to discuss the different notations for referring to the entries of the distribution ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png). The ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)th element of the vector ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) can be written in three equivalent ways:

![\psub{Xx}
\quad
=
\quad
\psub X(x)
\quad
=
\quad
\textrm{Pr}(\{ X=x \}).](./images/d3dc420cbdda219162967f8940d349dd57f1839f.png)

These three different ways of denoting the probability mass associated with outcome ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) in the distribution ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) represent three different ways of thinking about probability distributions. We can use the normal vector notation based on subscripts, ![\psub{Xx}](./images/d843ed92478f9fb991d03fba35aa1ef65e1c6eb0.png), but the appearance of two subscripts tends to be confusing. When the meaning of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is clearly apparent from the context, we can use the simpler notation ![p_x](./images/b76bbeaa1d9ea54fb5ad939d552eb15a08dff833.png). The notation ![\psub X(x)](./images/268458ae534f3934b69fa4fe23a10019d3607d1d.png) emphasizes the idea that a probability distribution can be understood as a _probability mass function_ that assigns probability mass for each of the possible outcomes. We can think of ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) as a function of the form ![\psub X : \{1,2,3,4,5,6\} \to \mathbb{R}](./images/b747b2227a42946aa6dba9d1d37af3a6cf47d049.png). The most precise notation for probabilities is ![\textrm{Pr}(\{ X=x \})](./images/eff8daf322b9a5e251e0c2eb233795f8e0a6db78.png), which describes the probability, denoted ![\textrm{Pr}](./images/080eb0a9c78c2b046978f3b2eebfe500692c8dc5.png), of the event that a random draw from ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) results in the outcome ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png), denoted ![\{X=x\}](./images/f9b2bc89775a5534e6c854e38f2e03239e69d1a7.png). Note we use the capital letter ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) when referring to the random variable, and the lowercase letter ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) to refer to particular outcomes of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png). In the standard terminology for probability theory, we refer to the particular outcome ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) as a _realization_ of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png).

Let’s use the distribution ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) to compute the probability of rolling a number five or greater, which corresponds to the event ![\{ X \geq 5\}](./images/f4b63f2f4f3b71f6743dbea5b9bf1e8cbd2adfb4.png). Note the outcome “greater than or equal to five” occurs when we roll a five _or_ a six. Thus, the complex event ![\{X \geq 5\}](./images/f4b63f2f4f3b71f6743dbea5b9bf1e8cbd2adfb4.png) is the logical `OR` of these two basic events:

![\{ X \geq 5 \}
\; = \; 
\{ X = 5 \} \texttt{ OR } \{ X = 6 \}.](./images/4b3068382216b92e912c9c2cfc2bd7299c00a9ac.png)

The probability of the event ![\{ X \geq 5 \}](./images/f4b63f2f4f3b71f6743dbea5b9bf1e8cbd2adfb4.png) is

![\begin{align*}
\textrm{Pr}(\{ X \geq 5\})
&= \textrm{Pr}(\{ X = 5\} \texttt{ OR } \{ X = 6\})		\\
&= \quad \psub{X}(5) \quad + \quad \psub{X}(6) \quad
= \tfrac{1}{6} + \tfrac{1}{6}
= \tfrac{1}{3}.
\end{align*}](./images/e7e93ffe5cdc35fa98e16be9dbfc8ea75464003f.png)

Since the outcomes five and six are mutually exclusive, the logical `OR` of these events corresponds to the sum of the probabilities of the outcomes.

#####[Example 2](./Front matter.md)

The probability distribution of the random variable ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png) that describes the outcome of a coin toss is

![\psub{\,Y} = \colvec{\tfrac{1}{2} \\ \tfrac{1}{2} }
\begin{array}{l}
\leftarrow \psub{\,Y}(\texttt{heads}) \\
\leftarrow \psub{\,Y}(\texttt{tails}).
\end{array}](./images/fe8a1269d866764003bedb94b19b2f568ce3b75b.png)

The probability distribution ![\psub{\,Y}](./images/0d5a6a8e6929a762e469666735d3f0ca561a3d94.png) corresponds to a function of the form ![\psub{\,Y}:  \{\texttt{heads}, \texttt{tails} \} \to \mathbb{R}](./images/3fad17a0fbd6b50b3e4f32f7ac03d86f5e5b037e.png), but for the sake of notational convenience, we associate the probability of `heads` and `tails` with the first and second entries of a two-dimensional vector ![\psub{\,Y}](./images/0d5a6a8e6929a762e469666735d3f0ca561a3d94.png). After all, this is a book about linear algebra, so everything must be turned into a vector!

What is the probability of getting `heads` three times in a row? We need three variables, ![Y_1](./images/a89d405cf024648a95f88fdf74862d86253630f3.png), ![Y_2](./images/6c24b793f87d46bc1418ce18c54e002daa4183fd.png), and ![Y_3](./images/877366c220e3f82253ebbdb56bfae7e89316d056.png), to represent the outcomes of the three coin tosses. Each random variable ![Y_i](./images/b9aa27c534a44423fb57e8eba11d88a239625097.png) is an independent copy of the random variable ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png). The probability of the outcome “three `heads` in a row” corresponds to the outcome where all three coin tosses come out `heads`: the first coin toss results in `heads` (![\{Y_1 = \texttt{heads} \}](./images/76b6ac95be86d2c364ac8ca3a00de22e113deccf.png)), the second coin toss results in `heads` (![\{Y_2 = \texttt{heads} \}](./images/327da122192d4c9385ef7cbf45ec7e686cee48a1.png)), and the third coin toss also results in `heads` (![\{Y_3 = \texttt{heads} \}](./images/83940ccaf49143021efb360e9a104bde6f86ee0f.png)). The probability of throwing three `heads` in a row is given by:

![\begin{align*}	
\textrm{Pr}(\{  & \textrm{three } \texttt{heads} \textrm{ in a row} \})			\\
&= \textrm{Pr}(
\{Y_1 = \texttt{heads} \}
\texttt{ AND }
\{Y_2 = \texttt{heads} \}
\texttt{ AND }
\{Y_3 = \texttt{heads} \} )		\\
& = \psub{\,Y}(\texttt{heads}) \cdot \psub{\,Y}(\texttt{heads}) \cdot \psub{\,Y}(\texttt{heads})
= \tfrac{1}{2}\cdot \tfrac{1}{2} \cdot \tfrac{1}{2}
= \tfrac{1}{8}.
\end{align*}](./images/d677e6013362a87e314a7fcd99fb19477bda938c.png)

Since each coin toss is an _independent_ random event, the probability of the logical `AND` of the three events is the product of the probabilities of the three events.

The examples above only scratch the surface of possibilities for modelling real-world situations in terms of random events, and for reasoning mathematically about the probabilities of different outcomes. I encourage you to research the topic of probability theory further on your own.

###[Expectations](./Front matter.md)

Consider a function ![f:\mathcal{X} \to \mathbb{R}](./images/be53e95af05505b333fb143ac90e8fd986eddcbf.png) that assigns values to each of the possible outcomes of a random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png). You can think of ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) as the payout function in a game of chance based on the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png). You obtain ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) dollars when the outcome of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). Using the usual notation for functions, we can write ![f(X)](./images/fe5ca1665f14af0d5300324e2db49b4a1955f3eb.png) to describe the payout of this game. Since the input ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is a random variable, the output value ![f(X)](./images/fe5ca1665f14af0d5300324e2db49b4a1955f3eb.png) is also a random variable. We can obtain the _expected payout_ of this game if we multiply each of the possible payouts by its probability of occurrence:

![\mathbb{E}_X\!\big[f(X) \big]
\; \eqdef \; 
\sum_{x \in \mathcal{X}}  f(x) \psub{X}(x).](../Images/170e78155579bc54a511d2a5aa3c2d1382c9211a.png)

The above equation introduces the _expectation operator_ ![\mathbb{E}_X](./images/4cfeeb9fc9d290571ae630b448cdc24cb7cb1ed8.png), which computes the weighted sum of the payouts for all possible outcomes. The payout amount for each outcome is multiplied by the probability of the outcome. The expected amount you’ll take home after playing the game of chance ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) times is ![n\mathbb{E}_X\!\big[f(X) \big]](../Images/1894f2dd86afb8c0dc5ca24743ff51b303fa9214.png). Sometimes you win big, sometimes you win less—by weighting each payout by its probability, we obtain the correct estimate of your expected winnings or losses.

#####[Example 3](./Front matter.md)

Consider the following game involving a six-sided die. You pay $1 to roll the die and the payout for the game is as follows. If you roll a ![\myepsdice{1}](./images/e300ded3bc3c862af38ecdb23923dd9313728ad0.png), a ![\myepsdice{2}](./images/f230e518128ec997fbbf53fe8c6ed27bc7ad49a3.png), a ![\myepsdice{3}](./images/72643b1848de343ed13862ea2b96804fb3691529.png), or a ![\myepsdice{4}](./images/cdffefddaed85e5ed85351236c4508f1eb3c4034.png), you win nothing. If you roll a ![\myepsdice{5}](./images/6205adb5cdcbd981cdc8d67300752fb092a14afa.png), you win $1. If you roll a ![\myepsdice{6}](./images/bb4d0b6cfb683299c08dc237339f3f470625bf3e.png), you win $4. Should you play this game?

The payout function for this game is defined as follows:

![f(\myepsdice{1}) = f(\myepsdice{2}) = f(\myepsdice{3}) = f(\myepsdice{4}) = \$0,
\quad
f(\myepsdice{5}) = \$1,
\quad
f(\myepsdice{6}) = \$4.](./images/511a3fbdabd999d194da393e4c35686e926ae021.png)

We’ll model the die roll as a random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) with distribution ![\psub{X} = (\frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6})^\sfT](./images/590e73a1c1e950b03dea72b136d6a215e4885be0.png). The expected payout for this game is

![\begin{align*}
\mathbb{E}_X[f(X)]  
&=  \textstyle \sum_x f(x)\, \psub{X}(x)																	\\
&= f(\myepsdice{1})\tfrac{1}{6} + f(\myepsdice{2})\tfrac{1}{6} + f(\myepsdice{3})\tfrac{1}{6}
+ f(\myepsdice{4})\tfrac{1}{6} + f(\myepsdice{5})\tfrac{1}{6} + f(\myepsdice{6})\tfrac{1}{6}  		\\
&= (\$0)\tfrac{1}{6} + (\$0)\tfrac{1}{6} + (\$0)\tfrac{1}{6} + (\$0)\tfrac{1}{6} + (\$1)\tfrac{1}{6} +  (\$4)\tfrac{1}{6}  				\\
&= \tfrac{\$1+\$4}{6}  \; = \;  \tfrac{\$5}{6} \; \approx \; 83 \textrm{ cents}.
\end{align*}](../Images/6c63ec83eb45dd9aa33767dc44da7c30d43cd879.png)

The expected payout of this game is less than the cost of playing, so it doesn’t make sense to play. Computing the expected value for any casino game will quickly convince you not to play—the expected payout is always less then what you must pay to play.

###[Expected value and variance of random variables](./Front matter.md)

We can use the expectation operator to compute certain characteristic properties of the random variable. The _expected value_ and the _variance_ are two properties of any random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) that capture important aspects of its behaviour.

The _expected value_ of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is computed using the formula

![\musub{X}
\eqdef \mathbb{E}_X[X]
= \sum_x x\, \psub{X}(x).](../Images/d47b99be2d3617fca8d9ff5702d5208b68553f86.png)

The expected value is a single number that tells us what value of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) we can expect to obtain on average from the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png). The expected value is also called the _average_ or the _mean_ of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png).

The _variance_ of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is defined as follows:

![\sigma^2_X
\eqdef	\mathbb{E}_X\!\big[(X-\musub{X})^2\big]
= 		\sum_x (x-\musub{X})^2 \, \psub{X}(x).](../Images/f2fae43fbf14cf2c3df63d9892a6309c8b101630.png)

The variance formula computes the expectation of the squared distance of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) from its expected value. The variance ![\sigma^2_X](./images/8d57732ec79993396eaff0623304ac149d6c4bee.png), also denoted ![\textrm{var}(X)](./images/4bf53ebbeab35915ad8e18be52f97388fc10a271.png), gives us an indication of how clustered or spread the values of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) are. A small variance indicates the outcomes of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) are tightly clustered near the expected value ![\musub{X}](./images/5b4b476e7247013a09b69de63e6ebbc9db94653b.png), while a large variance indicates the outcomes of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) are widely spread.

The expected value ![\mu](./images/9fb8ef778ea0c7c46d412558b51cb6522aef6c8c.png) and the variance ![\sigma^2](./images/a850e7973f3c89f2d4a27ad7de8e20210fc6c51b.png) are two central concepts in probability theory and statistics because they allow us to characterize any random variable. The expected value is a measure of the _central tendency_ of the random variable, while the variance ![\sigma^2](./images/a850e7973f3c89f2d4a27ad7de8e20210fc6c51b.png) measures its _dispersion_. Readers familiar with concepts from physics can think of the expected value as the _centre of mass_ of the distribution, and the variance as the _moment of inertia_ of the distribution.

Computing expected values and variances allows us to compare different random variables. Suppose you want to compare two random variables, ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) and ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png). It can be difficult to compare their probability distributions ![\psub{X}](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) and ![\psub{Y}](./images/8902bccd573fed956d4b706ed3c6dad023ac7ba6.png) directly, but we can compute their expected values and their variances and use these properties as the basis for the comparison. If we find ![\musub{X} > \musub{Y}](./images/2947c5838a9c2b9d222c80f04f70375bf47811fa.png), then we know ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) takes on larger values than ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png) on average. If ![\sigma^2_X > \sigma^2_Y](./images/0d7e5c8648699148548926c5f03f4863b2fbf0b5.png), then we know the probability mass function of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is more spread out than that of ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png).

###[Conditional probability distributions](./Front matter.md)

Probability theory also allows us to model dependencies between random variables. We use _conditional probability distributions_ to describe situations where one random variable depends on another. Consider the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) whose random outcomes depend on another variable ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png). To describe this probability dependence, we must specify the probability distributions of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) for each of the possible values of ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png). This information is expressed as a conditional probability distribution:

![\psub{X|Y} (x|y) 	\eqdef	\textrm{Pr}(\{ X=x \} \textrm{ given } \{ Y=y \}).](./images/964d216fcaa2753ed097fe7a0163b445a49e052c.png)

The vertical bar is pronounced “given,” and it separates the unknown random variable from the random variable whose value is known. The distribution ![\psub{X|Y}](./images/63e58b80a472808335da388999e3bb0cae7989fe.png) satisfies the conditions for a probability distribution for all ![y \in \mathcal{Y}](./images/f8dc31efefb41e77ce74123fef62cd00a37ad94a.png):

![\psub{X|Y} \in \mathbb{R}^{|\mathcal{X}| \times |\mathcal{Y}|} 
\textrm{ s.t. } 
\psub{X|Y}(x|y) \geq 0
\textrm{ and }
\sum_{x \in \mathcal{X}} \psub{X|Y}(x|y) = 1,
\forall y \in \mathcal{Y}.](./images/1ac3287049a728758817e17bad1aa5fd37dfc070.png)

It is natural to represent ![\psub{X|Y}](./images/63e58b80a472808335da388999e3bb0cae7989fe.png) as a ![|\mathcal{X}| \times |\mathcal{Y}|](./images/56d1036f567e80ddfaa59019c8e6c306afda03ce.png) matrix, with each column representing the probability of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) for a given value of ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png).

#####[Example 4](./Front matter.md)

Consider a probability distribution with six possible outcomes obtained by rolling one of two different dice—one fair and one biased. The probability distribution when rolling the fair die is ![\psub{X_{\!f}}= (\tfrac{1}{6},  \tfrac{1}{6},  \tfrac{1}{6},  \tfrac{1}{6},  \tfrac{1}{6},  \tfrac{1}{6})^\sfT](./images/59046d390c3d0031590eb24d5fc184b0f5c1da57.png). The probability distribution when rolling the biased die is ![\psub{X_b} = (\tfrac{1}{4},  \tfrac{1}{4},  \tfrac{1}{4},  \tfrac{1}{4}, 0, 0 )^\sfT](./images/8175ecc435ea6dab3ce7048e6598ea297383d5f1.png). Introducing the conditioning variable ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png) that describes which die is rolled, we can express the situation with the two dice as the following conditional probability distribution:

![\psub{X|Y}
\; = \begin{bmatrix}
\; \tfrac{1}{6} & \; \; \tfrac{1}{4} \; \\
\; \tfrac{1}{6} & \; \; \tfrac{1}{4} \; \\
\; \tfrac{1}{6} & \; \; \tfrac{1}{4} \; \\
\; \tfrac{1}{6} & \; \; \tfrac{1}{4} \;  \\
\; \tfrac{1}{6} & \; \; 0 \;   \\
\; \tfrac{1}{6} & \; \; 0 \;  \; 
\end{bmatrix}\!.](./images/c33f797197b83201e0e6a7c61964d66503ec6ff0.png)

The first column corresponds to the fair die ![Y=f](./images/df1b9788e1a9bc2c1c1454118e8e61f25b5d53c3.png), and the second column corresponds to the biased die ![Y=b](./images/12624a9066fb2d98ee2d40ddf0c94ce246d3b3e7.png).

Combining the probability distributions for the two dice, ![\psub{X_{\!f}}](./images/dcd30cc05ab33b712e658f157ef36ce91341c1ca.png) and ![\psub{X_b}](./images/630cfe6c838e3598e1cd07c1faebad3aece49888.png), into a single conditional distribution, ![\psub{X|Y}](./images/63e58b80a472808335da388999e3bb0cae7989fe.png), allows us to construct more complex probabilistic structures, as illustrated in the next example.

#####[Example 5](./Front matter.md)

Consider an experiment in which the outcome of a coin toss ![Y](./images/11f8f9453fe0e764209e0f36fa530073cb66d757.png) decides which die we throw—the fair die or the biased die. Suppose the coin is biased with ![\psub{Y} = (\frac{3}{4},\frac{1}{4})^\sfT](./images/36a132b6ce69951b43e5833ef9ea48901231c6ed.png). If the outcome of the coin toss is `heads`, we roll the fair die. If the coin toss gives `tails`, we roll the biased die. We’re interested in describing the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png), which corresponds to die rolls in which the fair die is used ![\frac{3}{4}](./images/6448a6b510b35da556b1c86649971794b11a9619.png) of the time and the biased die is used ![\frac{1}{4}](./images/474eb89340545d05a238efb3cf39c9bb239e1816.png) of the time. What is the probability distribution ![\psub{X}](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) for ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png)?

To model this situation, we combine the “which die” probability distribution ![\psub{Y} = (\tfrac{3}{4}, \tfrac{1}{4})^\sfT](./images/4aec903478f55fc5d44d05e0dad2203bd73627ae.png) with the conditional probability distribution ![\psub{X|Y}](./images/63e58b80a472808335da388999e3bb0cae7989fe.png) obtained in the previous example:

![\begin{align*}
\psub X(x) 
& =		\sum_{y \in \mathcal{Y}} \psub{X|Y}(x|y) \psub Y (y)			\\
& =		\psub{X|Y}(x|f) \psub Y (\texttt{heads})   + \psub{X|Y}(x|b) \psub Y (\texttt{tails})		\\
& = 		\psub{X|Y}(x|f) \tfrac{3}{4}  \; \;  \quad \qquad + \psub{X|Y}(x|b) \tfrac{1}{4}					\\
& = 		\tfrac{3}{4} (\tfrac{1}{6},\tfrac{1}{6},\tfrac{1}{6},\tfrac{1}{6},\tfrac{1}{6},\tfrac{1}{6})^\sfT
+ \tfrac{1}{4} (\tfrac{1}{4},\tfrac{1}{4},\tfrac{1}{4},\tfrac{1}{4},0,0)^\sfT	\\
& = 		(\tfrac{3}{16},\tfrac{3}{16},\tfrac{3}{16},\tfrac{3}{16},\tfrac{1}{8},\tfrac{1}{8})^\sfT.
\end{align*}](./images/08bed187c68cd4175ba94ce664c18cd5cb835ef1.png)

The probabilistic mixture of two random events corresponds to a linear combination—and when you think “linear combination,” you immediately think “matrix-vector product representation,” right? Indeed, we can also express ![\psub X](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) as a matrix-vector product between the conditional probability distribution of the matrix ![\psub{X|Y}](./images/63e58b80a472808335da388999e3bb0cae7989fe.png) and the vector ![\psub{Y}](./images/8902bccd573fed956d4b706ed3c6dad023ac7ba6.png):

![\psub X \; 
= \begin{bmatrix} 
\; \tfrac{1}{6} & \; \; \tfrac{1}{4} \; 	\\ 
\; \tfrac{1}{6} & \; \; \tfrac{1}{4} \; 	\\ 
\; \tfrac{1}{6} & \; \; \tfrac{1}{4} \; 	\\ 
\; \tfrac{1}{6} & \; \; \tfrac{1}{4} \;  	\\ 
\; \tfrac{1}{6} & \; \; 0 \;   		\\ 
\; \tfrac{1}{6} & \; \; 0 \;  \; 
\end{bmatrix}
\!\!
\begin{bmatrix}
\; \tfrac{3}{4} \; 	\\
\; \tfrac{1}{4} \; \; 
\end{bmatrix}
=
\begin{bmatrix} 
\; \tfrac{3}{16}  \; 		\\
\; \tfrac{3}{16}  \;  	\\
\; \tfrac{3}{16}  \;  	\\
\; \tfrac{3}{16}  \;  	\\
\; \tfrac{1}{8}  \;     	\\
\; \tfrac{1}{8}  \; \; 
\end{bmatrix}\!.](./images/b8c440b11e0ade218afa1b8242a227aca6a9c0ab.png)

You can verify that ![\sum_{x} \psub{X}(x)=1](./images/4118782a469d9de893fd8bd49a3b9828f852a32c.png) as expected for all probability distributions.

Note we were able to use conditional probability distributions to describe complicated random events in terms of the matrix-vector product. The notion of a conditional probability distribution is a fundamental building block of probability theory. Many modern machine learning techniques use probabilistic models constructed from conditional probability distributions.

###[Interpretations of probability theory](./Front matter.md)

One approach to understanding probability theory is to think about probabilities as describing relative frequencies of occurrence for different possible outcomes. The quantity ![\psub{X}(a)](./images/41f2193261b28a8cbb64ec1a8a548efa5ded7e88.png) represents the proportion of outcomes of the event ![\{ X = a \}](./images/fee90d6bf8fa84521a373cee31c938231f49a711.png) among all possible outcomes of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png).

This suggests an approach for estimating the probability mass of each of the possible outcomes. To characterize some real-world phenomenon as the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png), we estimate the probability distribution of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) by repeating the real-world phenomenon ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) times, where ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) grows to infinity. The probability mass of each outcome ![a \in \mathcal{X}](./images/f27a74648ca8515ac3cff7c1b40c59949d0c6a5c.png) is defined as the following limit:

![\psub{X}(a)  \eqdef  \frac{ N(\{X=a\},n) }{  n },  \quad n \to \infty,](./images/4bbe42f5ff51dd7db09b501cc5d6fde21cb4b321.png)

where ![N(\{X=a\},n)](./images/b5fa5f7a45e5818693971caf36fbae4f59e2e2e7.png) is the number of times the outcome ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png) occurs during ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) repetitions. If I tell you the probability mass of outcome ![\{ X = a \}](./images/fee90d6bf8fa84521a373cee31c938231f49a711.png) is ![0.3](./images/c8ae369718852e8f2049b90a7521985b5cd033e4.png), it means that if you take ![1000](./images/b5c26d560b3abf8ac16c16d37ec4812726e3d5be.png) draws from the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png), you can expect approximately ![300](./images/c9386f888a462e6c4b32245bfc53b32c78a867bb.png) of those draws to result in the outcome ![\{ X = a \}](./images/fee90d6bf8fa84521a373cee31c938231f49a711.png). Defining probabilities by counting the occurrences of different outcomes is called the _frequentist_ approach to probability theory. In practice, we don’t have time to actually repeat events an infinite number of times in order to obtain their exact probabilities; so think of this frequentist approach as a thought experiment, rather than applicable in practice.

Another conceptual interpretation of probability theory is to consider probability distributions as representations of our state of _knowledge_ or _beliefs_ about reality. Instead of describing some objective reality, the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) and its probability distribution ![\psub{X}](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) can represent our state of knowledge about the real-world phenomenon that ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) describes. Since ![\psub{X}](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) represents our state of knowledge about the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png), it makes sense to update the distribution ![\psub{X}](./images/54bb08dab67f6fe6bc47b1c817cbede7f903fc6c.png) as we learn new facts. This is called the _Bayesian_ approach to probability theory, named after Thomas Bayes who was an 18th century statistician. Consider the following example of Bayesian-style reasoning.

You’re given a coin and asked to come up with a probability distribution that describes its chances of landing `heads` or `tails`. Initially you have no information about whether the coin is biased in favour of heads or tails, so it makes sense to start with the initial belief that the coin is fair. This is called the _prior belief_, or simply _prior_—it’s the belief you hold prior to gathering data. If you toss the coin several times and observe significantly more `heads` than `tails`, you can update your belief about the coin’s probability distribution to account for your observations of the data. The specific technique for updating a prior belief in light of new observations is called _Bayes’ rule_.

Both the frequentist and Bayesian perspectives lead to useful techniques for modelling random events. Frequentist methods are concerned with drawing principled conclusions given a set of empirical observations. Bayesian models are generally more flexible and allow us to combine empirical observations with priors that encode the domain knowledge provided by experts. The frequentist approach is useful when you want to analyze data, prepare reports, and come up with hard numbers about the data. The Bayesian approach is more useful for building machine learning applications like voice recognition.

###[Discussion](./Front matter.md)

We described the basic notions in probability theory, such as random variables, probability distributions, and conditional probability distributions. These concepts are the bread-and-butter of probabilistic reasoning. Let’s take a minute to recap and summarize this new material, linking it back to vectors and linear transformations—the main subjects of this book. The probability distribution of a discrete random variable is a vector of real numbers. For instance, the probability distribution describing the outcome of rolling a six-sided die is a six-dimensional vector, ![\psub{X} \in \mathbb{R}^6](./images/1864a17fa0f960cc39c58180dfaeeccb16b4f938.png). Probability distributions are vectors that obey some extra constraints: each entry must be a nonnegative number, and the sum of the entries in the vector must equal one.

Conditional probability distributions are mappings that describe how a set of random “given” variables influence the probabilities of a set of random “outcome” variables. Conditional probability distributions can be represented as matrices, where each column of the matrix contains the outcome distribution for one of the values of the given variable. A conditional probability distribution with five possible outcomes, conditioned on a given variable with 10 possible states, is represented as a ![5 \times 10](./images/7f271f649294bed1fcabc95d8d87fea5be49ae81.png) matrix that contains probability distributions in each of its columns.

Conditional probability distributions are powerful tools for modelling real-world scenarios. Many machine learning algorithms involve the characterization, estimation, and exploitation of conditional probability distributions. We can also describe a noisy communication channel as a conditional probability distribution of the channel’s outputs given each of the channel’s possible inputs.

In the next section, we’ll learn about an application of conditional probability distributions that describes the state of a system undergoing random transitions between a number of possible states. This is a special case of a conditional probability distribution for which the random conditioning variable and random outcome variable are of the same dimension. Indeed, the outcome variable and the conditional space both represent states of the same system at different times.

###[Links](./Front matter.md)

\[ Discussion on the Bayesian way of thinking about probabilities \]

[`https://en.wikipedia.org/wiki/Bayesian_probability`](./Bayesian_probability.md)

\[ Detailed discussion about Bayes rule \]

[`http://yudkowsky.net/rational/bayes`](./bayes.md)

[`http://yudkowsky.net/rational/technical`](./technical.md)

###[Exercises](./Front matter.md)

E8.1 Do the following vectors represent probability distributions?

1.  ![\left(\tfrac{1}{2}, \tfrac{1}{2}, \tfrac{1}{2} \right)^\sfT](./images/0299bcbcd2ec253b5ad0e5e1a5da3add89a92ebe.png)
2.  ![\left(\tfrac{1}{4}, \tfrac{1}{4}, \tfrac{1}{4}, \tfrac{1}{4} \right)^\sfT](./images/13f20279ef52a84ee54d4c2ad943114a249d88bb.png)
3.  ![\left(0.3, 0.3, -0.1, 0.5  \right)^\sfT](./images/ad3d4a6d2ce243fc74bc90e6603e88998cb43214.png)

E8.2 Compute the expected value ![\mu_X](./images/a6ea9e6d31e09f152a097056574268a205c75aff.png) and the variance ![\sigma_X^2](./images/8d57732ec79993396eaff0623304ac149d6c4bee.png) of the random variable ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) that describes the outcome of rolling a six-sided die. The probability distribution of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) is ![\psub X = (\frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6}, \frac{1}{6})^\sfT](./images/590e73a1c1e950b03dea72b136d6a215e4885be0.png).

So far, we’ve talked about random events without any reference to the flow of time. In this section we’ll combine the idea of random variables with the notion of time. A _random process_ is a model of a system that undergoes transitions between states over time. The state of the system at time ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) is described by a random variable ![X_t](./images/8533bcabf4a02432de904a011308187022b3cc0e.png). We obtain the next state of the system ![X_{t+1}](./images/6ef3346f48002c003664c8378ae109770ec017fd.png) from the following conditional probability distribution:

![\psub{X_{t+1}|X_{t}X_{t-1}\cdots X_0}(x_{t+1}|x_{t}x_{t-1}\cdots x_0).](./images/942852140bac711b9e2d8ee8f41f44199d184ab0.png)

The random variable ![X_{t+1}](./images/6ef3346f48002c003664c8378ae109770ec017fd.png) depends on the previous states of the system: ![X_t](./images/8533bcabf4a02432de904a011308187022b3cc0e.png), ![X_{t-1}](./images/8e6f4eb6bba0a684d54b5ec3f68bb8b6f98351fc.png), ![X_{t-2}](./images/1b911324ac1f1bfd87a10a7c4605b41fbb2d7276.png), ![\cdots](./images/f3f653b876dacd0339b3fd194cb67f5a330d6a30.png), ![X_0](./images/1707e47e59e74901cdd275ed8c8cc2be8df2b4aa.png). Studying such history-dependent processes is a formidable task due to the myriad of possible influences from past states. Faced with this complexity, we can make a useful simplifying assumption by considering _memoryless_ random processes.

A _Markov process_ or _Markov chain_ is a random process for which the transition probabilities for the system’s next state depend only on its current state, regardless of previous states:

![\psub{X_{t+1}|X_{t}X_{t-1}\cdots X_0}(x_{t+1}|x_{t}x_{t-1}\cdots x_0)
=
\psub{X_{t+1}|X_{t}}(x_{t+1}|x_{t}).](./images/f2ffaa24ad467f68b89eb65b69739003fb6d3db6.png)

The system’s next state ![X_{t+1}](./images/6ef3346f48002c003664c8378ae109770ec017fd.png) depends only on its current state ![X_t](./images/8533bcabf4a02432de904a011308187022b3cc0e.png), and not on its prior history: ![X_{t-1}](./images/8e6f4eb6bba0a684d54b5ec3f68bb8b6f98351fc.png), ![X_{t-2}](./images/1b911324ac1f1bfd87a10a7c4605b41fbb2d7276.png), ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png), ![X_0](./images/1707e47e59e74901cdd275ed8c8cc2be8df2b4aa.png). Markov chains forget everything that happened in the past, which is why we refer to them as _memoryless_ random processes. A Markov chain is fully described by the conditional probability distribution ![\psub{X_{t+1}|X_{t}}(x_{t+1}|x_{t})](./images/920bdd52ea3e2ca5315574a6b27fc3938e0c7c0c.png), which describes the probability of the system’s next state, given its current state. We also refer to ![\psub{X_{t+1}|X_{t}}](./images/5812a92b562718bad00ac593f51b0ff9f8e37e58.png) as the _transition matrix_, since it describes the probabilities that the system will transition from one state to another.

Markov chains are extremely versatile models for analyzing many real-world systems. We don’t have the space to cover the topic in full, but I’ll introduce the basic notions for your general knowledge. First, we’ll look at the connection between Markov chains and matrix multiplication. Then, we’ll see how your eigenvalue-finding skills can help compute an important property of Markov chains. Understanding Markov chains is also necessary background material for understanding Google’s PageRank algorithm, which we’ll discuss in[Section 8.1.15](./Chapter 8_ Probability theory.md).

###[Example](./Front matter.md)

Three friends are kicking a football in the park: Alice, Bob, and Charlie. Whenever Alice gets the ball, she passes it to Bob 40% of the time, passes it to Charlie 40% of the time, or holds onto the ball 20% of the time. Bob is kind of a greedy dude: when he gets the ball, he holds onto it 80% of the time, and is equally likely to pass it to Alice or Charlie 20% of the time. When Charlie gets the ball, he’s equally likely to pass the ball to Alice or Bob, or keep it for himself. Assume these friends kick the ball around for a very long time (hundreds of passes), and you observe them at some point. What is the probability that each player will be in possession of the ball at the instant you observe them?

We can model the ball possession as a Markov process with three possible states, ![\mathcal{X} = \{ A, B, C \}](./images/1a59121202353335d9324c1f57727d6f8fe7a0c4.png), where each state describes moments when Alice, Bob, or Charlie has the ball. The transition probabilities ![\psub{X_{t+1}|X_{t}}(x_{t+1}|x_{t})](./images/920bdd52ea3e2ca5315574a6b27fc3938e0c7c0c.png) describe how the next state of the ball’s possession ![x_{t+1}](./images/4494650d91bffba64b8d8f6c3c871f386a33dc4b.png) depends on the previous state of the ball’s possession ![x_{t}](./images/e8be50e40ff6816347e98c7cae392daa411677c1.png). The transition matrix of the Markov chain in our current example is

![\psub{X_{t+1}|X_{t}} \; 
=
\begin{bmatrix} 
\; 0.2 & \; \; 0.1 & \; \; 0.\overline{3}		\; \\ 
\; 0.4 & \; \; 0.8 & \; \; 0.\overline{3}      	\; \\ 
\; 0.4 & \; \; 0.1 & \; \; 0.\overline{3}		\;  \; 
\end{bmatrix}
=
M.](./images/4484d534353d33ef812967a98a000a1b8b4943b0.png)

To maintain consistency with the notation for conditional probability distributions, we refer to the entries of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) as ![\psub{X_{t+1}|X_{t}}(x_{t+1}|x_{t})](./images/920bdd52ea3e2ca5315574a6b27fc3938e0c7c0c.png). The “given” variable ![x_t](./images/e8be50e40ff6816347e98c7cae392daa411677c1.png) selects the column of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png), and the different entries in this column represent the transition probabilities for that state. Using the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) and some basic linear algebra techniques, we can calculate the probability of finding the ball in any given player’s possession after many iterations of the “pass the ball” Markov process.

![markov_chain_ABC](./images/markov_chain_ABC.png)

Figure 8.1: Graphical representation of the transition probabilities between three states: “Alice has the ball,” “Bob has the ball,” and “Charlie has the ball.”

Let’s walk through an example calculation in which we assume the ball starts in Alice’s possession. Since we know that Alice has the ball at ![t=0](./images/93b87617c4082c719b320b97d0fce8c1c72438a2.png), we can describe the initial state of the system by the probability distribution ![\psub{X_0} = (1,0,0)^\sfT](./images/34daa009355f79c787c13734d2b9b4ec3e833dff.png), with 100% of the probability on Alice. We obtain the probability of finding the ball in each player’s possession after one time step, or unit of time, by multiplying the initial probability vector ![\psub{X_0}](./images/bffcd9b50c097f53f8f0370db213d5a48011c133.png) by the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png):

![\begin{align*}
\psub{X_1} 
& = 
M \psub{X_0}		\\
&=
\begin{bmatrix} 
\; 0.2 & \; \; 0.1 & \; \; 0.\overline{3}		\; \\ 
\; 0.4 & \; \; 0.8 & \; \; 0.\overline{3}      	\; \\ 
\; 0.4 & \; \; 0.1 & \; \; 0.\overline{3}		\;  \; 
\end{bmatrix}
\!
\begin{bmatrix} 
\; 1		\; \\ 
\; 0      	\; \\ 
\; 0		\;  \; 
\end{bmatrix}
= 
\begin{bmatrix} 
\; 0.2		\; \\ 
\; 0.4      	\; \\ 
\; 0.4		\;  \; 
\end{bmatrix}\!\!.
\end{align*}](./images/b68d86dd23f22a68633338617fc7b53c873dd20a.png)

All of the “where is the ball” probability starts with Alice, but after one time step it spreads to Bob and Charlie, according to Alice’s expected passing behaviour (the first column in the transition matrix).

We can continue this process to obtain the probability of ball possession after two time steps. We simply multiply the probability vector ![\psub{X_1}](./images/1655b46fbbbafb074379872b402fff43b40e8386.png) by the transition matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png), which is the same as multiplying the initial state ![\psub{X_0}](./images/bffcd9b50c097f53f8f0370db213d5a48011c133.png) by ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) twice:

![\begin{align*}
\psub{X_2} 
&= MM\psub{X_0} = M\psub{X_1}	\\
&= 
\begin{bmatrix} 
\; 0.2 & \; \; 0.1 & \; \; 0.\overline{3}		\; \\ 
\; 0.4 & \; \; 0.8 & \; \; 0.\overline{3}      	\; \\ 
\; 0.4 & \; \; 0.1 & \; \; 0.\overline{3}		\;  \; 
\end{bmatrix}
\!\!\!
\begin{bmatrix} 
\; 0.2 & \; \; 0.1 & \; \; 0.\overline{3}		\; \\ 
\; 0.4 & \; \; 0.8 & \; \; 0.\overline{3}      	\; \\ 
\; 0.4 & \; \; 0.1 & \; \; 0.\overline{3}		\;  \; 
\end{bmatrix}
\!\!\!
\begin{bmatrix} 
\; 1		\; \\ 
\; 0      	\; \\ 
\; 0		\;  \; 
\end{bmatrix}
= 		
\begin{bmatrix} 
0.21\overline{3}\; \\
0.5\overline{3} \; \; \\
0.25\overline{3} \, \,
\end{bmatrix}\!\!.			   
\end{align*}](./images/f5866ce96ec0ff4c2057480bfdd0c1b78ac5fe53.png)

Let’s focus on the first entry of this vector. The probability that Alice is holding the ball after two time steps is ![0.21\overline{3}](./images/b7b6c89f755949c60bbf6449d6ad4706df3ceb01.png). This number represents the combination of three different “paths” of starting from the state ![x_0=A](./images/de007f319484d53f930ae8b37dacb0c7f1bd6392.png) and coming to the state ![x_2 = A](./images/137926c52a12ce8d8cd474118a74dccf1afc4872.png) at ![t=2](./images/3eebee037779a6e49d9616a9135ccb072a6f2749.png). Either Alice kept the ball for two time steps (![x_1=A](./images/ed6a8a1c732f62b03d9e8fc240a9b454a1f59765.png)); or Alice passed the ball to Bob (![x_1=B](./images/e31b4044a4196b657921401fadb31be05a54c908.png)) and then he passed it back to her; or Alice passed the ball to Charlie (![x_1=C](./images/531c3edad36c964c0efabbb9206f989a76d0a5df.png)) and Charlie passed it back to her. By computing the sum of the products of the probabilities of the events on each path, we arrive at the value

![\begin{align*}
\psub{X_2|X_0}(A|A)
&= 
\psub{X_2|X_1}(A|A)\; \psub{X_1|X_0}(A|A) 	\\
& \qquad \qquad \quad +
\psub{X_2|X_1}(A|B) \; \psub{X_1|X_0}(B|A)	\\
& \qquad \qquad \qquad \qquad \qquad \, +
\psub{X_2|X_1}(A|C) \; \psub{X_1|X_0}(C|A)	\\
&=
0.2 \times 0.2   
+ 0.1 \times 0.4
\; + 0.\overline{3} \times  0.4					\\
&=
0.21\overline{3}.
\end{align*}](./images/079ef840eaf18364ee53cb7e72d0f7ddcf2f5a14.png)

This is a lot of work to do manually. Compare the above calculation with the multiplication-by-the-transition-matrix approach, and the compact expression ![\psub{X_2} = MM\psub{X_0}](./images/54f6cc8f4f15103043effdf90144a56de96cb3a6.png) which “takes care” of these three different paths automatically: there’s no need to manually consider all possible paths—instead, just multiply the state by the transition matrix to obtain the state probabilities in the next time step.

Thanks to the power of the Markov chain construction, we can carry the ball possession probabilities vector forward through time as far as we want to. To calculate the random state ![\psub{X_{t+1}}](./images/989b0ebda9c4fcd2c44166b852961c2abcb3fa45.png), multiply the previous state vector ![\psub{X_{t}}](./images/994f630cba4dff51da252dd34eae6673a1d0e61e.png) by the Markov transition probabilities matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). The probability distribution of ball possession after three time steps is

![\psub{X_3}
=
M \psub{X_2}
= M M \psub{X_1} 
= M M M \psub{X_0}
= M^3 \psub{X_0}
= 		
\begin{bmatrix} 
0.180\overline{4}	\\
0.596\overline{4}	\\
0.223\overline{1}
\end{bmatrix}\!.](./images/6418c2c9d62e39dcf708927f5e79a921d96e97d3.png)

Continuing this process, we can obtain the probability state vector after 10 and 20 time steps of the Markov chain:

![\psub{X_{10}} \!\!	
= M^{10} \psub{X_0} \!
= \!
\begin{bmatrix} 
0.161\ldots	\\
0.645\ldots	\\
0.193\ldots
\end{bmatrix}			   
\quad
\textrm{and}
\quad
\psub{X_{20}}  \!\!
= M^{20} \psub{X_0} \!
= \!
\begin{bmatrix} 
0.1612903\ldots		\\
0.6451612\ldots		\\
0.193548\ldots \; 	
\end{bmatrix}\!.](./images/d4f06ff99f9673f1b9d9c5e7b06bae27640a9ff4.png)

Observe how the weights of the probability distribution seem to change less and less as the Markov chain advances. Recall we originally set out to calculate the probability that each player will be in possession of the ball after a very long time. We seem to be on the right track to find this long-term probability of ball possession.

###[Stationary distribution](./Front matter.md)

If the evolution of a Markov chain continues for long enough, the probability vector will converge to a stable distribution ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) that remains unchanged when multiplied by ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png):

![M \psub{X_{\infty}} = \psub{X_{\infty}}.](./images/73def388e6dfd162ae0aef45e7b686c0c5364a18.png)

This is called the _stationary distribution_ of the Markov chain. Observe that ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) is an eigenvector of the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) with eigenvalue ![\lambda=1](./images/80fc8bed47c96f557f144e0985441a990951940c.png).

The convergence to a unique stationary distribution is a fundamental property of Markov chains. Assuming the Markov chain represented by ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) satisfies some technical conditions (which we won’t go into), it will converge to a stationary distribution ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png). Thus, if we want to find ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png), we just need to keep repeatedly multiplying by ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) until the distribution stabilizes:

![\psub{X_{\infty}} = 		
\begin{bmatrix} 
0.161290322580645\ldots		\\
0.645161290322581\ldots		\\
0.193548387096774\ldots
\end{bmatrix}					
= M^{\infty} \psub{X_0}.](./images/69754aa23224798c96cc5f1dcd349305d015f248.png)

The Markov chain will converge to the same stationary distribution ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) regardless of the starting point ![\psub{X_0}](./images/bffcd9b50c097f53f8f0370db213d5a48011c133.png). The ball could start with Bob ![\psub{X_0}=(0,1,0)^\sfT](./images/527540dca14853115dfed89afb75f68ea8fdb8a3.png) or with Charlie ![\psub{X_0}=(0,0,1)^\sfT](./images/59ae432afa9f15672cbf6195e692e1039a8d606e.png); and after running the Markov chain for long enough, we’d still arrive at the stationary distribution ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png).

Since we know the stationary distribution is an eigenvector of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) with eigenvalue ![\lambda=1](./images/80fc8bed47c96f557f144e0985441a990951940c.png), we can use the usual eigenvector-finding techniques to obtain ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) directly: just solve for ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) in ![(M-\mathbbm{1})\vec{v}=\vec{0}](./images/2608701e3c461a03b064bb06020726836b647617.png). This approach gives us an exact analytic expression for the answer. Note we must normalize the eigenvector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) so the sum of its components equals one. The final answer is ![\psub{X_{\infty}} = \frac{\vec{v}}{\|\vec{v}\|_1}=(\tfrac{5}{31}, \tfrac{20}{31}, \tfrac{6}{31})^\sfT](./images/5c51b1090e54fe7f54d40301232f29b8103def79.png), where ![\|\vec{v}\|_1  = |v_1| + |v_2| + |v_3|](./images/08a6c31dc25bd2d6a7f6287747b7559ee2b8e2bd.png) is the ![\ell^1](./images/87ac7ba1355548834748c0d239e0108624d87b76.png)\-norm of the eigenvector.

###[Discussion](./Front matter.md)

Markov chains have countless applications in physics, speech recognition, information processing, machine learning, and many other areas. Their simple, memoryless structure and their intuitive representation as matrices make them easy to understand and easy to fit to many situations.

In the next section, we’ll describe a Markov chain model for people’s web browsing behaviour. The stationary distribution of this Markov chain serves to quantify the relative importance of webpages.

###[Links](./Front matter.md)

\[ Awesome visual representation of states and transitions \]

[`http://setosa.io/blog/2014/07/26/markov-chains/index.html`](./index.md)

\[ More details about Markov chain applications from Wikipedia \]

[`https://en.wikipedia.org/wiki/Markov_chain`](./Markov_chain.md)

###[Exercises](./Front matter.md)

E8.3 After reading the section on Markov chains, you decide to research the subject further by checking out a book on Markov chains from the library. In the book’s notation, Markov chains are represented using _right_\-multiplication of the state vector: ![\vec{v}^{\,\prime} = \vec{v} B](./images/5d504f414aac86762fd1e192f31cca53c460a074.png), where ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is the state of the system at time ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png), ![\vec{v}^{\,\prime}](./images/a27b748fe9e3a90614c66225a1be984a70282901.png) is the state at time ![t+1](./images/4dc46612c91c2a872474a1b1400c59687dc0f113.png), and the matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) represents the Markov chain transition probabilities. Find the matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) that corresponds to the transition probabilities discussed in the Markov chain example on page 8.1.11. How is this matrix ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) related to the matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) that we used in the Markov chain example?

E8.4 Go to[`https://live.sympy.org`](./live.sympy.org.md) and create a `Matrix` object describing the passing-the-ball Markov chain transition probabilities. Use the `Matrix` methods `.eigenvects()` and `.nullspace()` to confirm the stationary distribution of the Markov chain is ![\left(\frac{5}{31}, \frac{20}{31}, \frac{6}{31} \right)](./images/7825d5c629d37b9c56ac7429b3d282a3e07c8fac.png).

You can create a `Matrix` object using

\>>> M = Matrix(\[\[ 2/10, 1/10, 1/3 \],
                \[ 4/10, 8/10, 1/3 \],
                \[ 4/10, 1/10, 1/3 \]\])

If you start from a matrix with exact rational entries, you’ll obtain the exact answer in terms of rational numbers. You can also use the function `S` (short for `sympify`) to create rationals: `S(1/3)` = ![\frac{1}{3}](./images/2e1382258077dc418e81971924dd9f4f09b9215a.png).

The eigenspace that corresponds to the eigenvalue ![\lambda=1](./images/80fc8bed47c96f557f144e0985441a990951940c.png) is the null space of the matrix ![(M-\mathbbm{1}_3)](./images/f62eec13d233c566e78191bc216dcb73e4a843f6.png). Use the `SymPy` command `eye(3)` to create a ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) identity matrix ![\mathbbm{1}_3](./images/36e7da6435d280542cb41b830690e89182b42665.png), then apply the `nullspace` method.

Use `vec.norm(1)` to compute the ![\ell^1](./images/87ac7ba1355548834748c0d239e0108624d87b76.png)\-norm of the vector `vec`.

E8.5 Find the stationary distribution of the following Markov chain:

![C = 
\begin{bmatrix} 
\; 0.8	&	0.3 	&	0.2 \; 		\\ 
\; 0.1 	&	0.2 	& 	0.6 \; 		\\ 
\; 0.1 	& 	0.5	&	0.2 \;  \; 
\end{bmatrix}\!\!.](./images/f7839b4558362c43034c7af84e9ebbaec57b32ca.png)

Consider the information contained in the **links between webpages**. Each link from Page A to Page B can be interpreted as a recommendation by Page A’s author for the contents of Page B. In web-speak we say links from Page A to Page B are “sending eyeballs” to Page B, presumably because there is something interesting to see on Page B. These observations about “eyeball worthiness” are the inspiration behind Google’s PageRank algorithm. We find a good summary of the idea behind PageRank in Google’s 2001 patent application:

> A method assigns importance ranks to nodes in \[...\] the world wide web or any other hypermedia database. The rank assigned to a document is calculated from the ranks of documents citing it. In addition, the rank of a document is calculated from a constant representing the probability that a browser through the database will randomly jump to the document. — Patent[`US6285999`](./US6285999.md)

You may notice there is a weird self-referential thing going on in that definition. The rank of a document depends on the ranks of documents that link to it, but how do you discover the ranks of these documents? By calculating the ranks of documents that link to them, and so on and so forth. Don’t worry if this sounds confusing, it will all start to make sense very soon.

###[The random surfer model](./Front matter.md)

Imagine someone who browses the web by randomly clicking on links. We’ll call this person Randy. Every time Randy opens his web browser he follows the following two strategies:

1.  When visiting a webpage, he’ll make a list of all the outbound links on that page and click on one of the links at random.
2.  Randy randomly selects a page on the web and goes to it.

Randy follows Strategy 1 90% of the time and Strategy 2 the remaining 10% of the time. In the unlikely event that he reaches a page with no outbound links, he’ll follow Strategy 2 and jump to a random page.

You have to agree that Randy’s behaviour is pretty random! This is a simple model for the behaviour of users on the web that assumes people either follow links blindly, or randomly jump to webpages. Simple as it is, this model allows us to capture an important aspect of web browsing behaviour: it allows us to measure the relative importance of different webpages. In the next section, we’ll describe the random surfer model using the machinery of Markov chains.

###[The PageRank Markov chain](./Front matter.md)

We want to construct a Markov chain that models the behaviour of Randy, the random web surfer. The _state_ in the Markov chain corresponds to the webpage Randy is currently viewing, and the transition matrix describes Randy’s link-clicking behaviour. Modelling Randy’s behaviour as a Markov chain will help us calculate the PageRank vector, which describes the “importance” of each webpage on the web.

We’ll now revisit the two random strategies Randy uses to browse the web, and construct the appropriate Markov chain matrices to describe them. Note the dimension of the matrices is ![n \times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png), where ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is the number of webpages on the web.

1.  Suppose Randy visits webpage ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png), which has ![N_j](./images/6278f77cd935d78c06ff11fbca7898abd0b0304c.png) outbound links. The probability he’ll click on one of these links is ![\tfrac{1}{N_j}](./images/e42b806658c971abdbbf6fb145fd1e2527846b4b.png). Thus, the column for Page ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) should contain entries ![\tfrac{1}{N_j}](./images/e42b806658c971abdbbf6fb145fd1e2527846b4b.png) in the rows that correspond to the pages that Page ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) links to. In the special case that Page ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) has zero outbound links, we’ll fill column ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) with the uniform distribution ![(\tfrac{1}{n},\tfrac{1}{n},\ldots,\tfrac{1}{n})^\sfT](./images/923dc3f5fef751d0176e7c546cd9cd22bd71a0b3.png). Thus, we can describe the ![ij](./images/cd7b298e9868bc16139f9c4cedd1ec9ec5e48d33.png)th entry of the transition matrix for Strategy 1 as follows:
    
    ![(M_1)_{ij} = \left\{ 
    \begin{array}{ll}
    \frac{1}{N_j} 	& 	\textrm{if there's a link from Page } j \textrm{ to Page } i 	\\
    \frac{1}{n}		&	\textrm{if Page } j \textrm{ has no outbound links}		\\
    0 			& 	\textrm{otherwise} 
    \end{array} \right.](./images/94da9163a798d258682025ae32801b0bb74d1b9e.png)
    
2.  The transition matrix for Strategy 2 is much simpler. No matter which page Randy visited previously, we want him to jump to a random page on the web; thus each column of the transition matrix ![M_2](./images/e093522e483473c095757cacebdd580f5671af5a.png) will contain the uniform distribution over all pages ![(\tfrac{1}{n},\tfrac{1}{n},\ldots,\tfrac{1}{n})^\sfT](./images/923dc3f5fef751d0176e7c546cd9cd22bd71a0b3.png). We can express this succinctly as:
    
    ![M_2 = \frac{1}{n}\,\mathbb{J},](./images/7eb631ef544e91f7993020aefdc1b1823df377b4.png)
    
    where ![\mathbb{J}](./images/2a2a6f51f5c2c18dd653d6d7055d9e39f8ab1643.png) is a matrix with ones in all its entries.
    

Recall that Randy uses Strategy 1 90% of the time and Strategy 2 10% of the time. The Markov chain ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) that describes his behaviour is a linear combination of the Markov chains for the two strategies:

![M  	= (1-\alpha)M_1 + \alpha M_2
= (1-\alpha)M_1 + \frac{\alpha}{n}\,\mathbb{J},](./images/e8f6533d776830700dfcd506271bd26d487fd36f.png)

where in this instance, ![\alpha=0.1](./images/051fee72bd22ff5f7e13fb95ea647e56de21d811.png) gives us a 90-10 mix of strategies. Note that in general, ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) is a parameter we can adjust for different applications.

The PageRank vector is the stationary distribution of the Markov chain ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png), which is defined through the equation ![M\psub{X_{\infty}} = \psub{X_{\infty}}](./images/08bfcbf6c83d4a4ffcd6afb3d36a682f7a6f0cc0.png). We can obtain ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) by finding the eigenvector of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) in the eigenspace ![\lambda_1=1](./images/059d866c639cc9ccb539a1be16c52dc3413a9956.png), which is equivalent to solving the null space problem ![(M - 1\mathbbm{1})\vec{e} = \vec{0}](./images/5e09a7d074ad34f91bea45c854f09f0fbfc6d6be.png). We can also obtain the stationary distribution ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) by running the Markov chain for many iterations, until we see the probability distribution converge:

![\{ \; \psub{X_{\infty}} \; \}
=
\mathcal{N}\!\left(  M - \mathbbm{1} \right)
\qquad
\Leftrightarrow
\qquad
\psub{X_{\infty}} 
= M^{\infty} \psub{X_0}. 
\qquad](./images/2292aa02dd76c5ef549ca363660f6e64400ab8aa.png)

Both approaches for finding ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) are useful in different contexts. Solving the null space problem gives us the answer directly, whereas the second approach of iterating the Markov chain is more scalable for large graphs.

The PageRank value of a webpage is the probability that Randy will navigate to a given page after running the Markov chain for a sufficiently long time. The PageRank vector ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) captures an important aspect of the well-connectedness or importance of webpages. Let’s illustrate the entire procedure for calculating the PageRank vector for the simple network shown in[Figure 8.2](./Chapter 8_ Probability theory.md).

####[Example: micro-web](./Front matter.md)

We’ll now study the micro-web illustrated in[Figure 8.2](./Chapter 8_ Probability theory.md). This is a _vastly_ simplified version of the link structure between webpages on the web. Rather than include billions of webpages, the micro-web contains only eight webpages ![\{1,2,3,4,5,6,7,8\}](./images/779c87737ceab76a8d1a79923be54883cf36eb28.png). Instead of trillions of links between webpages, the micro-web contains only fourteen links ![\{(1,2),](./images/57dbbff01bde8d32c2c1177963427a98524fa1cb.png) ![(1,5),](./images/84c8f1cb411d33390aae25a3647781ed20129912.png) ![(2,3),](./images/aadc82d8a48c7cdc5f7334ebbdd9997efe0dba09.png) ![(2,5),](./images/aed581e104e231326c3c159aab474e60e165622d.png) ![(3,1),](./images/819026392d6b2e13119c20fe84021039bca74b6c.png) ![(3,5),](./images/063809e7fbd9d5643b4513042d499c618ecd29bf.png) ![(4,5),](./images/8820e66c60e6a9f476e8287ee081982027ff00ba.png) ![(5,6),](./images/101db9636a376011ba62bdfeb00176f46eca79ce.png) ![(5,7),](./images/0dfd2d4315d9c9e10a769093c566bb06047c252a.png) ![(6,3),](./images/ca19dbd66fce272ab2f25d1755dc03aefc9dfc27.png) ![(6,7),](./images/19f18552f826501b59f11a4042083804a3f92633.png) ![(7,5),](./images/f74887935adb47bdd2ce776b3f648e201fc3265a.png) ![(7,6),](./images/6a6ed2a651fa25bb41dbc4dd9ec718b39f5bb9d6.png) ![(7,8)\}](./images/57895643a9e450d9a7277d68351aa2edd38b5074.png). Simple as it may be, this example is sufficient to illustrate the main idea of the PageRank algorithm. Scaling the solution from the case ![n=8](./images/d878bfdcc119d6863d4385a1eb1ea3fded510772.png) to the case ![n=1\,000\,000\,000](./images/157b701cffb36fe33f214d5c696b978f4e1839e8.png) is left as an exercise for the reader.

![micro_internet_example](./images/micro_internet_example.png)

Figure 8.2: A graph showing the links between the pages on the micro-web. Page 5 seems to be an important page because many pages link to it. Since Page 5 links to pages 6 and 7, these pages will probably get a lot of eyeballs, too. Page 4 is the least important, since no links lead to it. Page 8 is an example of the unlikely case of a webpage with no outbound links.

We’ll first construct the transition matrix ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) that corresponds to Strategy 1 (follow a random outbound link), and the matrix ![M_2](./images/e093522e483473c095757cacebdd580f5671af5a.png) for Strategy 2 (teleport to a random page), then construct a 90-10 weighted linear combination of ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) and ![M_2](./images/e093522e483473c095757cacebdd580f5671af5a.png), which is the PageRank Markov chain matrix.

The state of the Markov chain we want to construct corresponds to the probability distribution of Randy visiting one of the eight pages. Let’s say he is currently on Page 1, so the state of the Markov chain is ![(1,0,0,0, 0,0,0,0)^\sfT](./images/64a7a80b1df56b2e471d318283acafb1f526a910.png). Following Strategy 1, Randy will next go to either Page 2 or Page 5. Since there are two possible outbound links, the probability mass of choosing one of them is ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png). Recall that Page 1 corresponds to the first column of the matrix ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png). The first column of ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) must therefore contain the value ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png) in its second and fifth rows. Similarly, the entries in the second column of ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) correspond to the probabilities of Randy following links randomly starting at Page 2. Since Page 2 links to Page 3 and Page 5, the second column of ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) must contain ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png) in its third and fifth rows.

Continuing with this approach, we find the rest of the entries in the transition matrix for Strategy 1:

![M_1
=
\begin{bmatrix}
0 & 0 & \frac{1}{2} & 0 & 0 & 0 & 0 & \frac{1}{8}\\
\frac{1}{2} & 0 & 0 & 0 & 0 & 0 & 0 & \frac{1}{8}\\
0 & \frac{1}{2} & 0 & 0 & 0 & \frac{1}{2} & 0 & \frac{1}{8}\\
0 & 0 & 0 & 0 & 0 & 0 & 0 & \frac{1}{8}\\
\frac{1}{2} & \frac{1}{2} & \frac{1}{2} & 1 & 0 & 0 & \frac{1}{3} & \frac{1}{8}\\
0 & 0 & 0 & 0 & \frac{1}{2} & 0 & \frac{1}{3} & \frac{1}{8}\\
0 & 0 & 0 & 0 & \frac{1}{2} & \frac{1}{2} & 0 & \frac{1}{8}\\
0 & 0 & 0 & 0 & 0 & 0 & \frac{1}{3} & \frac{1}{8}				
\end{bmatrix}\!\!.](./images/0f6afa0b2f5a5a56a64add55a642b8fd11034309.png)

To convince yourself that ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) has the correct entries, compare the rest of the columns with the link structure in[Figure 8.2](./Chapter 8_ Probability theory.md). Recall that Strategy 1 handles the exceptional case of a page with no outbound links by jumping to a random page. Since the micro-web contains eight pages, the uniform distribution over all pages is ![(\frac{1}{8},\frac{1}{8},\frac{1}{8},\frac{1}{8},\frac{1}{8},\frac{1}{8},\frac{1}{8},\frac{1}{8})^\sfT](./images/76321a2fd964f6c0a39155e847e94fb52d391348.png).

Do you recall the _adjacency matrix_ representation for graphs we discussed in[Section 7.4](./Chapter 7_ Applications.md)? You can obtain ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) by taking the transpose of the adjacency matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), and then normalizing the columns so they become probability distributions.

The Markov chain for Strategy 2 is to jump to a random page on the micro-web:

![M_2
=
\frac{1}{8}\,
\mathbb{J}_{8}
=
\begin{bmatrix}
\frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}\\
\frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}\\	
\frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}\\
\frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}\\	
\frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}\\
\frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}\\	
\frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}\\
\frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}& \frac{1}{8}	
\end{bmatrix}\!\!.					\qquad  \; \;](./images/f899b6eedaa437ca4d37a26ca939f00f5ab30f38.png)

Note the new notation ![\mathbb{J}_{n}](./images/c457a4cdf87af29eeab3209aaa09abd077f7144e.png), which corresponds to an ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix with ones in all its entries.

The PageRank Markov chain ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png) is defined in terms of the matrices ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) and ![M_2](./images/e093522e483473c095757cacebdd580f5671af5a.png) and a mixture parameter, which we denote ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png). Choosing ![\alpha=0.1](./images/051fee72bd22ff5f7e13fb95ea647e56de21d811.png) models a Randy who uses Strategy 1 90% of the time and Strategy 2 10% of the time:

![\begin{align*}
M  	&= (1-\alpha)M_1+ \frac{\alpha}{8}\,\mathbb{J}_8		\\
&= \frac{9}{10}\,M_1 + \frac{1}{80}\,\mathbb{J}_8.
\end{align*}](./images/27b415cc3568f3becebe75859448127f75d9dabb.png)

Or, written out in full detail:

![M
=
\begin{bmatrix}
\frac{1}{80} & \frac{1}{80} & \frac{37}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{8}\\
\frac{37}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{8}\\
\frac{1}{80} & \frac{37}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{37}{80} & \frac{1}{80} & \frac{1}{8}\\
\frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{8}\\
\frac{37}{80} & \frac{37}{80} & \frac{37}{80} & \frac{73}{80} & \frac{1}{80} & \frac{1}{80} & \frac{5}{16} & \frac{1}{8}\\
\frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{37}{80} & \frac{1}{80} & \frac{5}{16} & \frac{1}{8}\\
\frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{37}{80} & \frac{37}{80} & \frac{1}{80} & \frac{1}{8}\\
\frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{1}{80} & \frac{5}{16} & \frac{1}{8}
\end{bmatrix}\!\!.](./images/652e46b53dd4d01c67d5be4816425b35831466a7.png)

Notice the sprinkling of ![\frac{1}{80}](./images/7048f23fcaf9be5c2a7ce2ee10cc7a62683d3462.png)s that fill the regions which had only zeros in ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png). The addition of these weights is important for technical reasons. The _mixing time_ of a Markov chain is how long it takes for it to reach its steady state distribution. If we were to use just the matrix ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) for the Markov chain, the probability distribution that describes Randy’s state might get stuck in one part of the graph, and not explore all the nodes. Adding a bit of ![\mathbb{J}_{n}](./images/c457a4cdf87af29eeab3209aaa09abd077f7144e.png) creates connections between all the nodes, and this guarantees the Markov chain will quickly converge to its stationary distribution.

Since we built the Markov chain for the micro-web, we can now find its stationary distribution ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png), which is the PageRank vector:

![\psub{X_{\infty}}
=( 0.08152, 0.05868, 0.1323, 0.02199, 0.2268, 0.1864, 0.2079, 0.08437)^\sfT.](./images/ccd46c4bc20b3edaac914b4334996cdbc3b49634.png)

We obtain ![\psub{X_{\infty}}](./images/329f395cacdbd089bd6a4668b9f1d11a6d7a8069.png) by finding the vector in the ![\lambda_1=1](./images/059d866c639cc9ccb539a1be16c52dc3413a9956.png) eigenspace of ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png). Use[`SymPy`](./live.sympy.org.md) to check this result. See[`bit.ly/microWebPR`](./microWebPR.md) for the commands required to solve the null space problem ![\left( M- \mathbbm{1} \right)\vec{e}= \vec{0}](./images/f084e1dc566d5ab8cb8a76276e0e9789144e5f33.png).

We can now use the entries of the PageRank vector to sort the pages of the micro-web by their relative importance, as shown in[Table 8.1](./Chapter 8_ Probability theory.md).

Page ID

PageRank

Page 5

0.22678

Page 7

0.20793

Page 6

0.18642

Page 3

0.13229

Page 8

0.08437

Page 1

0.08152

Page 2

0.05868

Page 4

0.02199

Table 8.1: The PageRanks of the pages from the graph in[Figure 8.2](./Chapter 8_ Probability theory.md).

According to their PageRank score, the top two pages in the micro-web are Page 5 with PageRank ![0.22678](./images/7dc22291320d89ec88233b812fff8122d7142bbe.png) and Page 7 with PageRank ![0.20793](./images/afb9e7df73a0be15f093e7b1e7cb23683dfe36b1.png). Page 6 is not far behind with PageRank ![0.18642](./images/ab82db3e92983790c2788bb5be01ea68408f3e3f.png). Looking at[Figure 8.2](./Chapter 8_ Probability theory.md), we can confirm this ranking makes sense, since Page 5 has the most links pointing to it, and since Page 5 links to Page 6 and Page 7. As expected, Page 4 ranks as the least important page on the micro-web since no pages link to it.

###[Discussion](./Front matter.md)

The example we discussed above involved only eight webpages and an ![8\times 8](./images/2bab62e6428f207b79dab521589717216dfe7cfb.png) Markov chain matrix. Imagine the size of the matrix needed to represent all the links between webpages on the web. The web has upward of a billion webpages and contains trillions of hyperlinks. Imagine an ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) Markov chain matrix, where ![n=1\,000\,000\,000](./images/157b701cffb36fe33f214d5c696b978f4e1839e8.png). You’d need a ridiculous amount of memory to store this matrix, and a huge amount of computing power to work with it.

The computation of the PageRank vector for the entire web can be performed using the _power iteration_ method, which finds the eigenvector for the largest eigenvalue of the matrix. Additionally, careful analysis of the data required to perform the algorithm can avoid the need to construct the impossibly-large ![n\times n](./images/c9b784228a7bac3be0b4d9bdf65f60001c204d96.png) matrix. Thus the contributions of PageRank inventors Larry Page and Sergey Brin go beyond basic linear algebra, since they offer a clever approach for splitting the computation among a cluster of computers. This is a lesson to keep in mind when you use your linear algebra knowledge to build stuff. You need to cultivate a healthy mix of intuition, mathematical tools, _and_ engineering prowess to get things done. Go find the right linear combination of these resources and build your own $300B company. I’m betting on you.

###[Links](./Front matter.md)

\[ The original PageRank paper \]

[`http://ilpubs.stanford.edu/422/1/1999-66.pdf`](./1999-66.pdf.md)

\[ Further discussion about the PageRank algorithm \]

[`https://en.wikipedia.org/wiki/PageRank`](./PageRank.md)

\[ The _power iteration_ method for finding the PageRank eigenvector \]

[`https://en.wikipedia.org/wiki/Power_iteration`](./Power_iteration.md)

###[Exercises](./Front matter.md)

E8.6 Compute the PageRank vector for the network of webpages shown in[Figure 7.3](./Chapter 7_ Applications.md) on page 7.3.

Use[`https://live.sympy.org`](./live.sympy.org.md) and define the matrix ![M_1](./images/e5d9b44b2ef8561fedbf588a3700f4682dda2a40.png) using the syntax `Matrix([[...], ...])`, then mix it with an all-ones matrix `ones(n,n)`. Use the `nullspace` method from [8.1.15](./Chapter 8_ Probability theory.md) to obtain the eigenvector in the ![\lambda=1](./images/80fc8bed47c96f557f144e0985441a990951940c.png) eigenspace.

##[8.2 Probability problems](./Chapter 8_ Probability theory.md)

To better understand random variables and probability distributions, you need to practice using these concepts to solve real-world problems. It just so happens there are some practice problems on this very topic in this section—how convenient is that? Don’t skip them!

Solving practice problems will help you understand probability theory and Markov chains. If you haven’t played with `SymPy` yet, now is a great chance to get to know this powerful computer algebra system because Markov chain calculations are difficult to do by hand.

P8.1 Given a random variable ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png) with three possible outcomes ![\{1,2,3\}](./images/ae5074cd9fec33411fe9798dddc8e48258e85e93.png) and probability distribution ![\psub{X} = (p_1,p_2,p_3)](./images/3ca398eea117ba297c170f800c000b6b237071fe.png), prove that ![p_1 \leq 1](./images/fe5d00725923f0f48b59e3b5c83c66103f7dc375.png).

Use the Kolmogorov’s axioms and build a proof by contradiction.

P8.2 The probability of `heads` for a fair coin is ![p=\frac{1}{2}](./images/05911103a5cf34c4909612eb042f7c88229c11fe.png). The probability of getting `heads`  ![n](./images/e4b68e8c3ac79ddb60832042f0e1d46dc15ad35e.png) times in a row is given by the expression ![p^n](./images/cc73a4ecd022e9d81a40de78e0d14321f2c7b9e1.png). What is the probability of getting `heads` four times in a row?

P8.3 You have a biased coin that lands on `heads` with probability ![p](./images/db026ecd1c353059006f172113faa1deaf037629.png), and consequently lands on `tails` with probability ![(1-p)](./images/68e9809f5c670c03b60d4e59e7b8e1fb34e7cc89.png). Suppose you want to flip the coin until you get `heads`. Define the random variable ![N](./images/53090024c9f918501451c0c8e574166b9e5d0778.png) as the number of tosses required until the first `heads` outcome. What is the probability mass function ![P_N(n)](./images/18831e5bc6a3bb12d3fd8d8e95dd0edf62c3b519.png) for success on the ![n](./images/e4b68e8c3ac79ddb60832042f0e1d46dc15ad35e.png)th toss? Confirm that the formula is a valid probability distribution by showing ![\sum_{n=1}^\infty P_N(n) = 1](./images/d4f6f340dfbcfe2031f7ad9c2f5eebcd4ef5f5c7.png).

Find the probabilities for cases ![n=1,2,3,\ldots](./images/184a72bb2764e00a4f758b050bb7395fd455547e.png) and look for a pattern.

P8.4 The probability mass function for the geometric distribution with success probability ![p](./images/b11f2617243b9603c98df21c26f4fc4d87ffa1fb.png) is ![\psub{X}(x) = (1-p)^{x-1}p](./images/67f9898b53dcc39ef4993df5eb1d958b87c79384.png), where ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png) describes the number of trials until the first success. Compute the expected value ![\mathbb{E}_X[X]](../Images/43baf940f69bd9bce38298d9c5dc6cfec379f3fa.png).

The formula for the sum of the geometric series is ![\sum_{k=0}^\infty r^k = \frac{1}{1-r}](./images/78eb7f3782461d232b9cff351d1ea471c7dcbe96.png), and taking its derivative with respect to ![r](./images/c0d523b6e154a03a4fea7f48c97c54646dac0bb4.png) gives ![\sum_{k=0}^\infty k r^{k-1} = \frac{1}{(1-r)^2}](./images/9374f807fe9b02d906759237e7b2b7dc8c29f264.png).

P8.5 A mathematician walks over to a roulette table in a casino. The roulette wheel has 101 numbers: 50 are black, 50 are red, and the number zero is green. If the mathematician bets $1 on black and the roulette ball stops on a black number, the payout is $2, otherwise the bet is lost. Calculate the expected payout for playing this game, and determine whether it’s worth playing.

P8.6 Consider the following variation of the six-sided die game. You pay $1 to play one round of the game and the payout for the game is as follows. If you roll a ![\myepsdice{1}](./images/8dab3a5f68cd83cc0ece6b5ed542d50eeec73d75.png), a ![\myepsdice{2}](./images/019b7255f65e114bb055e885e282d49ca79fc318.png), or a ![\myepsdice{3}](./images/a690834e890cd8aea1092900e4b112d39a3d6719.png), you win nothing. If you roll a ![\myepsdice{4}](./images/635ed3afda35fd410085965fd0813e5d1369e859.png) or a ![\myepsdice{5}](./images/87df43a8332618667e61b3563ba0396a40ae9d37.png), you win $1. If you roll a ![\myepsdice{6}](./images/c079c53caa33986b5a7ed2a5edeb7f489fbe9fea.png), you win $5. Should you play this game?

P8.7 Show that variance of a random variable ![X](./images/a7f54b569058d4f7f4288861e14c026e6294ac12.png) with distribution ![\psub{X}](./images/1f39c18af6243b9b8f237fe7f9829254d951fad7.png) is given by the formula ![\,\textrm{var}(X) = \sum_{x\in \mathcal{X}} x^2\,\psub{X}(x)  \; - \; \musub{X}^2](./images/01d91aa7d6f62cc385d42f5ff02c17288b53d8a5.png).

Start from the definition ![\textrm{var}(X) \eqdef \mathbb{E}_X\!\big[(X-\musub{X})^2\big]](../Images/82ceb728ddc30e69127a795f9bf7444ab7c8852a.png) and simplify it.

P8.8 Consider the weather in a city which has “good” and “bad” years. Suppose the weather conditions over the years form a Markov chain where a good year is equally likely to be followed by a good or a bad year, while a bad year is three times as likely to be followed by a bad year as by a good year. Given that last year, call it Year ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png), was a good weather year, find the probability distribution that describes the weather in Year ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png), Year ![2](./images/c3c9d3b985832f49aefa0fdc55fd8c1785a9d2aa.png), and Year ![\infty](./images/42c777f473b0c5e98bd06929c747d966458a44be.png).

P8.9 Consider the network of webpages shown in[Figure 8.3](./Front matter.md). Find the Markov chain transition matrices ![M_1](./images/2fbe7f3d090b8150a5bb7678a07a7525b79caad9.png) and ![M_2](./images/0fbea30986f64c383cc4b5128097dbe355dfc621.png) for Randy’s two browsing strategies; then combine the strategies using ![\alpha=0.1](./images/c134b5e5a302793a75a31bce91989968089a0e35.png) to obtain the PageRank matrix ![M](./images/44e67a884615810a50ecabbd2868844c89bc909f.png). Compute the PageRank vector. Which pages are the most important?

![graph_problem_c](./images/graph_problem_c.png)

Figure 8.3

Use[`SymPy`](./live.sympy.org.md) for the calculation. Consult the micro-web calculation example [`bit.ly/microWebPR`](./microWebPR.md)) for the `SymPy` commands you’ll need.
