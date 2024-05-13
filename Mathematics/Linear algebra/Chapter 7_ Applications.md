Chapter 7      

#[Chapter 7 Applications](./Chapter 7_ Applications.md)

In this chapter, we’ll learn about applications of linear algebra. We’ll cover a wide range of topics from different areas of science, business, and technology to give you an idea of the spectrum of possible calculations based on vector and matrix algebra. Don’t worry if you’re not able to follow all the details in each section—we’re taking a broad approach here, covering many different topics in the hope that some will interest you. Note that most of the material covered in this chapter is not likely to show up on your linear algebra final, so no pressure—this is just for fun.

Before we start, I want to say a few words about scientific ethics. Linear algebra is a powerful tool for solving problems and modelling the real world. But with great power comes great responsibility. I hope you’ll make an effort to think about the ethical implications when you use linear algebra to solve problems. Certain applications of linear algebra, like building weapons, interfering with crops, and building mathematically-complicated financial scams are clearly evil, so you should avoid them. Other areas where linear algebra can be applied are not so clear-cut: perhaps you’re building a satellite localization service to find missing people in emergency situations, but the same technology could be used by governments to spy on and persecute your fellow citizens. Do you want to be the person responsible for bringing about an Orwellian state? All I ask of you is to run a quick “System check” before you set to work on a project: ask yourself “Am I working for the System?” Don’t just say “It’s my job” and proceed without caution. If you find what you’re doing for your employer is unethical, then maybe you should find a different job. There are a lot of jobs out there for people who know math, and if the bad guys can’t hire qualified people like you, their power will decrease—and that’s a good thing.

Our System check is complete. On to the applications!

##[7.1 Balancing chemical equations](./Chapter 7_ Applications.md)

Suppose you’re given the chemical equation ![\textrm{H}_2 + \textrm{O}_2  \to  \textrm{H}_2\textrm{O}](./images/9a7b7c19427647d78f829a3df46dd2802e3668bc.png), which indicates that hydrogen molecules (![\textrm{H}_2](./images/0373ed2c602b525b90de71a654f71b94760557f0.png)) and oxygen molecules (![\textrm{O}_2](./images/e6282f2ebf1c314d4786e9935fd9c052c069fe78.png)) can combine to produce water molecules (![\textrm{H}_2\textrm{O}](./images/373c9e0afe51e8c2c68340ab98530b4f6cf5a877.png)). Chemical equations describe how a set of _reactants_ are transformed into a set of _products_. In this case, the reactants are hydrogen and oxygen molecules and the products are water molecules.

The equation ![\textrm{H}_2 + \textrm{O}_2  \to  \textrm{H}_2\textrm{O}](./images/9a7b7c19427647d78f829a3df46dd2802e3668bc.png) is misleading since it doesn’t tell us the correct _stoichiometric ratios_: how much of each type of molecule is consumed and produced. We say the equation is not _balanced_. To _balance_ the equation, we must add coefficients in front of each reactant and each product, so that the total number of atoms on both sides of the reaction is the same: ![2\textrm{H}_2 + \textrm{O}_2  \to  2\textrm{H}_2\textrm{O}](./images/0d27b126d5065dca2c5cf0216cb59937019d00c1.png). Two hydrogen molecules are required for each oxygen molecule, since water molecules contain one oxygen and two hydrogen atoms.

Let’s look at another example. The combustion of methane gas is described by the following chemical equation:

![\textrm{C}\textrm{H}_4 + \textrm{O}_2  \; \to \;  \textrm{C}\textrm{O}_2 + \textrm{H}_2\textrm{O} \,.](./images/7ec44d525fd535de50af9f7277c6800f1d28f005.png)

We want to answer the following two questions. How many molecules of oxygen will be consumed during the combustion of 1000 molecules of methane? How many ![\textrm{C}\textrm{O}_2](./images/a15efc6685a4197635548174f4cc0ae1eb6f39ef.png) molecules will be produced as a result?

Before we can answer such questions, we must find the coefficients ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png), and ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png) that balance the methane-combustion equation:

![a \textrm{C}\textrm{H}_4 + b \textrm{O}_2  \; \to \;  c\textrm{C}\textrm{O}_2 + d\textrm{H}_2\textrm{O}.](./images/5e5ae9a78bc0214ff70cc610d99ce60af0dc4920.png)

For the equation to be balanced, the same number of atoms of each type must appear on each side of the equation. For the methane combustion reaction to be balanced, the following equations must be satisfied:

![\begin{align*}
a 		&= c 		&&\textrm{for }C\textrm{ atoms to be balanced},\\
4a 		&= 2d 	&&\textrm{for }H\textrm{ atoms to be balanced},\\
2b		&= 2c + d	&&\textrm{for }O\textrm{ atoms to be balanced}.
\end{align*}](./images/8211951bb2ff9327c04e638715b864ad3494d888.png)

We can move the ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) and ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png) terms to the left side of each equation and rewrite the system of equations as a matrix equation:

![\begin{array}{rcl}
a  \; \; \; \; \; \; - c   \; \; \; \; \; \; \; 	&=& 0	\\
4a \; \; \; \; \; \; \; \; \; \;  - 2d 	&=& 0	\\
2b - 2c-d 			&=& 0
\end{array}
\qquad
\Rightarrow
\qquad
\underbrace{
\!
\begin{bmatrix}
1 & 0 & -1 & 0  \\
4 & 0 &  0 & -2 \\
0 & 2 & -2  & -1 
\end{bmatrix}
\!}_A \,
\begin{bmatrix}
a \\ b \\ c \\ d
\end{bmatrix}
=
\begin{bmatrix}
0 \\ 0 \\ 0
\end{bmatrix}\!.](./images/609822f57edcd8a7bd085364006ab5a96a2434c6.png)

We’re looking for the vector of coefficients ![\vec{x}=(a,b,c,d)](./images/f624196a2c9d860116b29505487103cfb6b70c7c.png), which is the solution to the null space problem ![A\vec{x}=\vec{0}](./images/61bcffc45ea2149ebd8e3297c5a775c3b8c8f631.png). See [4.5.6](./Chapter 4_ Geometric aspects of linear algebra.md) on page 4.5.6 for details. The RREF of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) contains three pivots and one free variable. The solution to the null space problem is one-dimensional:

![\{ (a,b,c,d) \} = \textrm{span}( (\tfrac{1}{2}, \, 1\,, \tfrac{1}{2}\,, 1) ).](./images/431c21de24d9854e8e4ce52efd244439e105a9fc.png)

The solution is the span of the vector ![(\tfrac{1}{2}, \, 1\,, \tfrac{1}{2}\,, 1)](./images/9a9aaad5cb789c3b4d2e0a1a704743fbebc835bf.png). The solution space is infinite since any balanced equation will remain balanced if we double or triple the amount of reactants and products. Choosing the coefficients as suggested by the solution to the null space problem gives ![\tfrac{1}{2}\textrm{C}\textrm{H}_4 +  \textrm{O}_2  \to \tfrac{1}{2}\textrm{C}\textrm{O}_2 + \textrm{H}_2\textrm{O}](./images/2475bd49fae6f772773cababb73aedbd404ff24e.png), which is a balanced equation. The convention in chemistry is to choose integer coefficients for reactants and products, so we’ll multiply the equation by two to obtain the final answer:

![\textrm{C}\textrm{H}_4 + 2\textrm{O}_2  \; \to \;  \textrm{C}\textrm{O}_2 + 2\textrm{H}_2\textrm{O}.](./images/e20b99639d35882e4dd8c356b7f9eb4a14ab6a5b.png)

Balancing chemical equations may not seem like the most exciting technique ever, but it’s a useful skill for many chemistry calculations. It’s a good start to know that substances ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) can transform into substances ![C](./images/e104c07e4395e448b71e474fea29a36b6dc2615a.png) and ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png), but it’s better to know _how much_ of each reactant is consumed and how much of each product is produced per “unit of reaction.” Once we’ve identified one “unit of reaction,” we can calculate other quantities in terms of it, such as measuring the energy released per unit of reaction. The combustion of ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png)\[mol\] (![=6.022\times10^{23}](./images/31fd8bf73d686e8347e68cc7ffa5b66a4821e8db.png) molecules) of methane produces ![890](./images/9119357064fc1a6ccde6424c4d5436b602067dbe.png)\[kJ\] of heat:

![\textrm{C}\textrm{H}_4 + 2\textrm{O}_2  
\; \to \;  
\textrm{C}\textrm{O}_2 + 2\textrm{H}_2\textrm{O}  \; \;  + \; 890\,\textrm{[kJ/mol]}.](../Images/3a7e9ff879341d7506ad5ea5dfb0668c52b16f20.png)

Now _this_ is cool. If you’re heating your chalet with methane gas, and you know how many joules of heat you’ll need, then the balancing chemical equation will help you calculate how many litres of methane you need to stock in order to survive this winter.

###[Exercises](./Front matter.md)

The exercises below aren’t difficult, so you should totally try to solve them. Plus, they’ll give you some extra practice with the Gauss–Jordan elimination procedure. It’s been _ages_ since[Chapter 3](./Chapter 3_ Computational linear algebra.md), so a refresher can’t hurt.

Watch out, chemistry is coming at ya! Can you handle it?

E7.1 Balance the chemical equation ![\textrm{Al} + \textrm{O}_2 \;  \to \;  \textrm{Al}_2 \textrm{O}_3](./images/ca89feeaf404dac880f0e037fed5fa9f476a18c3.png).

E7.2 Balance the equation ![\textrm{Fe}(\textrm{OH})_3 + \textrm{HCl} \; \to \; \textrm{FeCl}_3 + \textrm{H}_2\textrm{O}](./images/0f7eba46067cb5453ec46529fa029c7cc650e108.png).

##[7.2 Input–output models in economics](./Chapter 7_ Applications.md)

Suppose you’re the top economic official of a small country and you want to make a production plan for the coming year. For the sake of simplicity, let’s assume your country produces only three commodities: electric power, wood, and aluminum. Your job is to choose the production rates of these commodities: ![x_e](./images/c2a1f5d18e6e87b931548b9096059d2ae03806ee.png), ![x_w](./images/c58f0e81cac8642e7019aa993349244df56cd9e2.png), and ![x_a](./images/cc4541af003aa07ba7a9c30895c8078b7be3e5e3.png). Your country must produce enough to satisfy both the internal demand and the external demand for these commodities. The problem is complicated because the production rates in one industry may affect the production rates of other industries. For instance, it takes some electric power to produce each unit of aluminum, so your production plan must account for both external demand for electric power, as well as _internal demand_ for electric power for aluminum production. When complex interdependences exist between the different internal industries, as is often the case, it makes the process of picking the right production rates more complex.

In reality, most high-ranking government officials make their decisions about which industry to sponsor based on the dollar amounts of the kickbacks and bribes they received during the previous year. Let’s ignore reality for a moment and assume you’re an honest economist interested in using math to do what is right for the country instead of abusing your position of power like a blood-thirsty leech.

Let’s assume the electric production ![x_e](./images/c2a1f5d18e6e87b931548b9096059d2ae03806ee.png) must satisfy an external demand of ![25](./images/a9fb8fa13ef0ef56e4b3065957001b9106982854.png) units, plus an additional ![0.05](./images/e431d9335aa27fde5225d61522f9138ae422e859.png) units for each unit of wood produced (electricity needed for saw mill operations) and an additional ![0.3](./images/c8ae369718852e8f2049b90a7521985b5cd033e4.png) units for each unit of aluminum produced. The wood production must be ![10](./images/fd39ea446d2046417cbd0fc131073609dd557e3d.png) units plus additional small amounts that depend on ![x_e](./images/c2a1f5d18e6e87b931548b9096059d2ae03806ee.png) and ![x_a](./images/cc4541af003aa07ba7a9c30895c8078b7be3e5e3.png) (wood for construction). The production of aluminum must match ![14](./images/6063949b028f99381255d890f2964537ef1c66cb.png) units of external demand plus an additional ![0.1](./images/ebe277b3361085df056c7c3ebf981f9e8397583c.png) units for each unit of electric power (for repairs of electric cables). We can model the interdependence between the industries using the following system of equations:

![\begin{align*}
x_e 	\quad 	&= 		\quad \; \; \; \;  \, 25 		\; \; \; \; \; \qquad +  \quad 			\qquad \; \;  0.05x_w  \; \;  + 	 \; \; \;   	0.3x_a  	\\
x_w	\quad 	&=		\quad \; \; \; \;  \, 10 		\; \; \; \; \; \qquad + \quad 			0.01x_e   \qquad \;  \; \;  \; \; +	 \; \;  0.01x_a	\\
x_a	\quad 	&=		\underbrace{14}_{\textrm{external demand}} \; \; \; \,  + \quad \; \; 
\underbrace{0.1x_e \qquad \qquad \qquad \qquad \;  }_{\textrm{internal demand}}.	
\end{align*}](./images/2688371e519f7878c390ee75ccc4cfae249e65ae.png)

You can use linear algebra to solve this complicated industry interdependence problem and choose appropriate production rates. Express the system of equations as a matrix equation:

![\underbrace{\!\!
\begin{bmatrix} x_e \\ x_w \\ x_a \end{bmatrix}
\!\!}_{\vec{x}}
=
\underbrace{\!\!
\begin{bmatrix} 25 \\ 10 \\ 14 \end{bmatrix}		   
\!\!}_{\vec{d}}
\;    + \; 
\underbrace{\!\!
\begin{bmatrix}
0 		&	0.05		&	0.3		\\
0.01  	&	0		&	0.01		\\
0.1		&	0		&	0		
\end{bmatrix}\!\!}_{A} \;
\underbrace{\!\!\begin{bmatrix} x_e \\ x_w \\ x_a \end{bmatrix}\!\!}_{\vec{x}}.](./images/d9a9e70f9a56785076b76b9fafef42a5e692254c.png)

This is known as a _Leontief input-output model_ in honour of Wassily Leontief, who first applied linear algebra techniques to economics, and was awarded the Nobel prize for this contribution.

To find the appropriate production rates, we must solve for the unknown ![\vec{x}=(x_e,x_w,x_a)](./images/05352895640139b676b9ad2831c91aeee26202cb.png) in the above equation. The equation ![\vec{x} = \vec{d} + A\vec{x}](./images/153f73b761104da2d1f9d276c7189d75ef2404d5.png) is a little unusual, but we can solve it using standard techniques:

![\mathbbm{1}\vec{x} = \vec{d} + A\vec{x}
\quad
\Rightarrow  
\quad
(\mathbbm{1} - A)\vec{x} = \vec{d}
\quad
\Rightarrow  
\quad
\vec{x} = (\mathbbm{1} - A)^{-1}\vec{d}.](./images/7e5c7bff584808afc9af6c7835de14da6bac6eff.png)

The solution to the electricity, wood, and aluminum production scenario is ![\vec{x}=(x_e,x_w,x_a)=(30.64,10.48,17.06)](./images/a1370f48868d6f282cfd5872f0a99c73ace9897e.png). See [3.6](./Chapter 3_ Computational linear algebra.md) for the details of the solution.

Note the electricity production rate is significantly higher than the external demand, in order to account for the internal demand of electricity for the aluminum production.

####[Links](./Front matter.md)

\[ History of the Leontief input-output model in economics \]

[`https://en.wikipedia.org/wiki/Input-output_model`](./Input-output_model.md)

###[Exercises](./Front matter.md)

E7.3 A group of farmers has formed a cooperative that specializes in three crops: arugula (_eruca sativa_), broccoli, and carrots. They need to produce 10 tons of arugula, 200 tons of broccoli, and 300 tons of carrots for sale. The farmers also need some additional production to feed themselves and the work-for-food tourists that come to help them scale up production during the harvest season. To feed the workers needed to grow 100 kg of arugula, they need to produce an extra 10 kg of broccoli and 10 kg of carrots. To produce 100 kg of broccoli, it takes 1 kg of arugula and 15 kilograms of carrots. To produce 100 kg of carrots, it takes 1 kg of arugula and 20 kilograms of broccoli. How much of each vegetable should the farmers produce?

##[7.3 Electric circuits](./Chapter 7_ Applications.md)

We can use Ohm’s law to solve many circuit problems. To _solve_ a circuit is to find the current flowing in each wire in the circuit, and the value of the voltage at every point in the circuit. Ohm’s law, ![V=IR](./images/19b74bf663981eb747db2be5711c9e90e2bdcc0d.png), tells us the voltage ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) required to “push” a current ![I](./images/c0c93262ae3eeffc031389fa783f5dc2a63da57f.png) through a resistor with resistance ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png). This simple equation is all we need to find the currents and voltages of any electric circuit involving wires, batteries, and resistors.

Since we’re in Math Land, the units of the circuit quantities won’t play a direct role in our analysis; but we’ll still introduce them, since units will help us perform dimensional analysis of the equations. Voltages are measured in volts \[V\], currents are measured in Amperes \[A\], and resistance is measured in Ohms [![\Omega](./a89081e357231e56c28ec4682bcbcfdba27b4d8f.png.md)\]. Intuitively, the resistance of a resistor measures how difficult it is to “push” current through it. Indeed, the units for resistance have the dimensions of Volt per Ampere: ![[\Omega]=[\textrm{V}/\textrm{A}]](../Images/f9583bd165d27fdc3d6183f88738808c7a0ad3a6.png). The equation ![V=RI](./images/b1c011acb284e97c1f74c59d11b3636a288f30eb.png) tells us how much current ![I](./images/c0c93262ae3eeffc031389fa783f5dc2a63da57f.png)\[A\] flows through a resistor with resistance ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png)[![\Omega](./a89081e357231e56c28ec4682bcbcfdba27b4d8f.png.md)\] connected to a voltage source with potential ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\[V\]. Alternatively, if we know the current ![I](./images/c0c93262ae3eeffc031389fa783f5dc2a63da57f.png)\[A\] and the resistance ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png)[![\Omega](./a89081e357231e56c28ec4682bcbcfdba27b4d8f.png.md)\], we can find ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), the voltage applied to the resistor. A third way to use the equation ![V=RI](./images/b1c011acb284e97c1f74c59d11b3636a288f30eb.png) is to solve for the resistance ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) in cases when we know both ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) and ![I](./images/c0c93262ae3eeffc031389fa783f5dc2a63da57f.png).

#####[Example](./Front matter.md)

Your friend gives you a 121[![\Omega](./a89081e357231e56c28ec4682bcbcfdba27b4d8f.png.md)\] light bulb (a resistor) and asks you to connect it outdoors on the backyard porch to provide some extra lighting for a summer party. You run to the basement and find three different spools of electric wire: a green wire rated for currents of up to ![0.5](./images/68d4957d7f32385c33450fcf78986d1693f0d2b2.png)\[A\], a blue wire rated for currents of up to ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png)\[A\], and a red wire rated for currents of up to ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png)\[A\]. Knowing that the voltage coming out of the wall socke[1](./Front matter.md) is ![110](./images/bd907740c24f341abfc5af0db07b1c9ce88d4c2c.png)\[V\], what is the lowest-rating wire you can use to connect the light bulb?

A simple calculation using ![V=RI](./images/b1c011acb284e97c1f74c59d11b3636a288f30eb.png) shows us that the current flowing through the lightbulb is ![I = \frac{V}{R} = \frac{110[\textrm{V}]}{121[\Omega]} = 0.909](../Images/3e0c4842d648d05f64923bce730797a46bf69198.png)\[A\]. Thanks to your calculation, you choose the blue wire rated for ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png)\[A\] knowing you won’t have problems with wires overheating and causing a fire.

It can be difficult to solve for all the voltages and currents in electric circuits that contain multiple voltage sources (batteries) and resistors (light bulbs), like the circuit shown in[Figure 7.1](./Chapter 7_ Applications.md). Using the equation ![V=RI](./images/b1c011acb284e97c1f74c59d11b3636a288f30eb.png) for each resistor leads to several equations that must be solved simultaneously to find the unknowns. Did someone say “system of linear equations”? Linear algebra to the rescue!

![applications_circuit_ex_blank](./images/applications_circuit_ex_blank.png)

Figure 7.1: An electric circuit with three batteries and three resistors.

Knowing linear algebra will enable you to solve even the most complicated circuit using row operations (Gauss–Jordan elimination) in one or two minutes. We’ll illustrate this application of linear algebra by solving the example circuit shown on the right, which involves three batteries (the parallel lines labelled ![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png) and ![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png)) and three resistors (the wiggly lines).

###[Background](./Front matter.md)

Before we get started, let me introduce the minimum information you need to know about circuits: _Kirchhoff’s voltage law_ and _Kirchhoff’s current law_.

The voltages in a circuit are related to the electric potential energy of the electrons flowing in the circuit. The electric potential is analogous to the concept of gravitational potential: a battery raises the electric potential of electrons like an elevator raises the gravitational potential of objects by increasing their height. Starting from this heightened potential, electrons flow through the circuit and lose potential when they pass through resistors. _Kirchhoff’s voltage law_ (KVL) states that the sum of the voltage gains and losses along any _loop_ in the circuit must sum to zero. Intuitively, you can think of KVL as a manifestation of the _conservation of energy_ principle: the potential gained by electrons when they pass through batteries is lost in the resistors (in the form of heat). By the time the electrons complete their journey around any loop in the circuit, they must return to their initial potential.

_Kirchhoff’s current law_ states that the total current flowing into a wire junction must equal the total current flowing out of the junction. You can think of this as a manifestation of the _conservation of charge_ principle: the total charge coming into a junction equals the total charge flowing out of the junction, because charges cannot be created or destroyed.

Recall that to solve a circuit is to find the currents that flow in each wire and the voltage across each resistor. We’ll now illustrate how to solve a complicated circuit by introducing current variables, applying Kirchhoff’s laws to obtain systems of linear equations, and solving these equations using linear algebra.

###[Using linear algebra to solve circuits](./Front matter.md)

The first step is to define variables for each of the quantities of interest in the circuit as shown in[Figure 7.2](./Chapter 7_ Applications.md). We’ll call ![I_1](./images/b95faa24096bfbeb1b5fe3c21a9b1719d5177f2b.png) the current that flows down through the middle wire of the circuit, which then splits into the current ![I_2](./images/72293988c0745d97ba47391d548d2d7cbcfe103e.png) in the left branch and the current ![I_3](./images/145b2bac2b7de5f212c1d502a0c74115e83ee6e6.png) going to the right. Next we follow the currents in the circuit and label the terminals of each resistor “![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png)” and “![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png)” to indicate its _polarity_—the direction of the voltage drop across it. The rule to follow is simple: the label “![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png)” goes on the side where the current enters the resistor, and the label “![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png)” goes on the side where the current leaves the resistor. We write the “![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png)” on the side where the current enters because electric potential always _drops_ when passing through a resistor. It’s important to keep track of the polarity of resistors when writing the KVL equations for the circuit.

![applications_circuit_branch_currents](./images/applications_circuit_branch_currents.png)

Figure 7.2: The circuit with branch currents labelled. Each resistor is assigned a _polarity_ relative to the current flowing through it.

We’re now in a position to apply Kirchhoff’s voltage and current laws to this circuit and obtain a set of equations that relate the unknown currents. Let’s first apply Kirchhoff’s voltage law to the loop along the path A-B-C-D-A, computing the total of the voltage gains along this path:

![\begin{align*}
+10  - R_1I_2 + 5  -  R_2I_1  \; &= \;  0.
\end{align*}](./images/785cca0669c3b0a12f14f2a309bff8cc0d660563.png)

\\label{eqn:electric\_circuits\_abcda} Each battery produces a gain in potential for the electrons flowing through it. Each resistor leads to a drop in potential (negative gain) proportional to the current flowing through the resistor (recall $V = RI$). Similarly, we obtain a second KVL equation by following the path A-F-E-D-A in the circuit:

![\begin{align*}
+10  - R_1I_2 + 5  -  R_2I_1  \; &= \;  0.
\end{align*}](./images/8039cad1bff08093a8f56b8ddf16c3550fdddfb9.png)

\\label{eqn:electric\_circuits\_afeda} We're measuring voltage \\emph{gains} along this loop, therefore the contribution of the battery is positive while the contributions of the resistors are negative. We obtain a third equation linking the unknown currents from Kirchhoff's current law applied to junction~A:

![\begin{align*}
+10  - R_1I_2 + 5  -  R_2I_1  \; &= \;  0.
\end{align*}](./images/b4770664e7783c755a9bf001c0acb62135d4c9ae.png)

Combining the three circuit equations, we obtain a system of three linear equations in three unknowns:

![\begin{align*}
+10  - R_1I_2 + 5  -  R_2I_1  \; &= \;  0.
\end{align*}](./images/61839cfdae3745b0fd9567653943370e7be117c9.png)

Do you see where this is going? Perhaps rewriting the equations into the standard form we discussed in[Section 3.1](./Chapter 3_ Computational linear algebra.md) will help you see what is going on:

![\begin{align*}
R_2I_1 \; + R_1I_2   \; \qquad  \quad \; 			\; &=  \; 15,		\\
R_2I_1 \; \qquad \quad \; \; +    R_3 I_3       		\; &= \; 20,		\\			
I_1  \; \; \;  \; \; -   I_2 \; \; \, \; \; -   I_3 				\; &= \; 0.
\end{align*}](./images/e245646dcf2308947e0b45c5e4dcee48b21d494e.png)

Rewriting the system of equations as an augmented matrix, we obtain:

![\left[\begin{array}{ccc|c}
R_2 & R_1 & 0 \; \; & \;  15\\
R_2 & 0 & R_3 \; \; & \;  20\\
1 & -1 & -1 \; \; & \;  0
\end{array}\right]\!.](../Images/ee067717c13d7f2611df025de851a5495de14cf3.png)

Assume the values of the resistors are ![R_1=1](./images/a50c352235e43ac60adaf0a0b735ff742c6f75e9.png)[![\Omega](./a89081e357231e56c28ec4682bcbcfdba27b4d8f.png.md)\], ![R_2=2](./images/197accf71741565b515a39dcf683a76128a14da6.png)[![\Omega](./a89081e357231e56c28ec4682bcbcfdba27b4d8f.png.md)\], and ![R_3=1](./images/1b47085b3f75dceb28577969999772d4d5804af2.png)[![\Omega](./a89081e357231e56c28ec4682bcbcfdba27b4d8f.png.md)\]. We substitute these values into the augmented matrix, and then find its reduced row echelon form:

![\left[\begin{array}{ccc|c}
2 & \; 1 & \; 0 \; \; & 15	\\
2 & \; 0 & \; 1 \; \; & 20	\\
1 & -1 & -1 \; \; & 0
\end{array}\right]
\quad
\textrm{---{\sc rref}}\!\!\rightarrow
\quad
\left[\begin{array}{ccc|c}
1 & 0 & 0 \; \; & 7		\\
0 & 1 & 0 \; \; & 1		\\
0 & 0 & 1 \; \; & 6
\end{array}\right]\!.](../Images/b1ea9a40106fbb4709415c1d9cb5aab1f9363882.png)

The currents are ![I_1=7](./images/2f70a18465a789de7bbdf4f2dddb92f3d8728335.png)\[A\], ![I_2=1](./images/1f525d12ee4694add64a1c5e3a81630d2fdf96aa.png)\[A\], and ![I_3=6](./images/7434492f792f0902294e41c653fdc4e6198ef88b.png)\[A\]. The voltage drop across ![R_1](./images/8b13a1ba012b87b09c6a690a4a68411bf8aca63f.png) is ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png)\[V\] with polarity as indicated in[Figure 7.2](./Chapter 7_ Applications.md). The voltage drops across ![R_2](./images/298c3a8eeb4c54d846817b8f5066042f39bdd3eb.png) and ![R_3](./images/6d065085aa78144e541aecc3280f532e1154cdac.png) are ![14](./images/6063949b028f99381255d890f2964537ef1c66cb.png)\[V\] and ![6](./images/e8ed0b8c238bb0e8c23f11db175de0a483bfde15.png)\[V\] respectively. Verify that these currents and voltages are consistent with the KVL equations we started from.

The combination of Kirchhoff’s laws and linear algebra techniques allows us to solve any electric circuit. Analyzing complicated circuits will require solving large systems of equations; but, by using matrix methods, you should be able to handle even the most complex circuit. And you can always[use `SymPy` to perform a RREF computation](./1kmYLmz.md) if it’s ever too hairy to calculate by hand.

###[Other network flows](./Front matter.md)

The same techniques we used for finding the flow of currents in circuits can also be applied to many other problems involving flow: the flow of cars on city streets, the flow of goods and services between economies, and the flow of information (data packets) through the internet. In each case, a different law governs how the flows travel through the network, yet we can use the same matrix techniques to solve the resulting systems of linear equations.

###[Exercises](./Front matter.md)

E7.4 Obtain a third KVL equation for the path A-B-C-D-E-F-A in the circuit from[Figure 7.2](./Chapter 7_ Applications.md). Combine this third equation with the KVL equations for the paths A-B-C-D-A and A-F-E-D-A given on page eqn:electric\_circuits\_abcda. Are these three equations in three unknowns sufficient to solve the circuit without using the KCL equation?

E7.5 Write the three KVL equations for the three inner loops of the circuit. Obtain the KCL equations for junctions B and C.

![exercise_one](./images/exercise_one.png)

Combine the five equations to form a matrix equation ![R\vec{I} = \vec{V}](./images/d319a30ba25565d3244ca835eb9ed7fc1e6fffbb.png), where ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) is a ![5\times 5](./images/b4b2c17e39d8e0ccd01458171f726f27c9305e39.png) matrix, ![\vec{I} = (I_1,I_2,I_3,I_4,I_5)^\sfT](./images/1c0a5eba6dbe891f90fe10d0e76b14643784b87f.png) is the vector of unknown currents, and ![\vec{V} = (V_1,V_2,V_3,0,0)^\sfT](./images/750dcc3ddb3f10b9e0df0d91ca4b861720849982.png) is a vector of constants.

##[7.4 Graphs](./Chapter 7_ Applications.md)

A _graph_ is an abstract mathematical model that describes connections between a set of nodes. We call the nodes _vertices_ and the connections _edges_. The graph is defined as a pair of sets ![G=(V,E)](./images/410e8bebdc9eff8e5afd77cf5eb121cfcc1921ec.png), where ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png) is the set of vertices and ![E](./images/80475983a19b0a9300f24e29f61de72089cf32a2.png) is the set of edges in the graph. We can also describe the edges by specifying the _adjacency matrix_ of the graph.

Rather than define graphs formally and in detail, we’ll look at a simple graph example to give you an idea of the main concepts and introduce graph notation.[Figure 7.3](./Chapter 7_ Applications.md) shows a small graph with five vertices and seven edges. This abstract link structure could represent many real-world scenarios: five websites and the hyperlinks between them, five Twitter accounts and their “following” relationships, or seven financial transactions between five businesses.

![small_graph_example](./images/small_graph_example.png)

Figure 7.3: A simple graph with five vertices and seven edges.

The graph in[Figure 7.3](./Chapter 7_ Applications.md) is represented mathematically as ![G=(V,E)](./images/410e8bebdc9eff8e5afd77cf5eb121cfcc1921ec.png), where ![V=\{ 1,2,3,4,5 \}](./images/23d5ae3a149db8e5546230366d6e7a40ea28a669.png) is the set of vertices, and ![E = \{ (1,2),](./images/6d84fe2c668480a6c5f02662ca71a86637e2d1ff.png) ![(1,3),](./images/e628f933df8b32653a1840b57e61bc535f27eb22.png) ![(2,3),](./images/aadc82d8a48c7cdc5f7334ebbdd9997efe0dba09.png) ![(3,5),](./images/063809e7fbd9d5643b4513042d499c618ecd29bf.png) ![(4,1),](./images/2f8e7620ca79df747f292dfcb65d326773c490b4.png) ![(4,5),](./images/8820e66c60e6a9f476e8287ee081982027ff00ba.png) ![(5,1) \}](./images/0b7353d955823b3d86c7d020f8e9f6d156dbe47f.png) is the set of edges. Note the edge from vertex ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) to vertex ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) is represented as the pair ![(i,j)](./images/1577818349566033338ba5b9a849604cef4f466a.png).

###[Adjacency matrix](./Front matter.md)

The _adjacency matrix_ representation of the graph in[Figure 7.3](./Chapter 7_ Applications.md) is a ![5\times 5](./images/b4b2c17e39d8e0ccd01458171f726f27c9305e39.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) that contains information about the edges in the graph. Specifically, ![A_{ij}=1](./images/dc39415b7ce23fb418638bba41310a720f30ce72.png) if the edge ![(i,j)](./images/1577818349566033338ba5b9a849604cef4f466a.png) exists, otherwise ![A_{ij}=0](./images/b79a76ef87c2dbb960f9b35449d279cf7e460a22.png) if the edge doesn’t exist:

![A = 
\begin{bmatrix}
0 & 1 & 1 & 0 & 0\\
0 & 0 & 1 & 0 & 0\\
0 & 0 & 0 & 0 & 1\\
1 & 0 & 0 & 0 & 1\\
1 & 0 & 0 & 0 & 0
\end{bmatrix}\!\!.](./images/41183ead3561d1f1cdcd7832eaee8407a4e2009e.png)

Each row contains ones in the positions where edges exist. The adjacency matrix representation works in tandem with the integer labels of the vertices—Vertex 1 corresponds to the first row of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), Vertex 2 to the second row, and so on for the other rows. We don’t need labels for the vertices since the labels can be deduced from their position in the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

###[Applications](./Front matter.md)

The adjacency matrix of a graph can be used to answer certain questions about the graph’s properties. For example, powers of the adjacency matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) tell us information about the connectivity in the graph. The number of ways to get from vertex ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) to vertex ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) in two steps is ![(A^2)_{ij}](./images/a101e5a32419fccdf584b9169c43e7952b0cc360.png), which is the ![ij](./images/cd7b298e9868bc16139f9c4cedd1ec9ec5e48d33.png)th entry of ![A^2](./images/a0d61abbc27f436fbb804c112345805d7ce3a569.png):

![A^2 = 
\begin{bmatrix}
0 & 0 & 1 & 0 & 1\\
0 & 0 & 0 & 0 & 1\\
1 & 0 & 0 & 0 & 0\\
1 & 1 & 1 & 0 & 0\\
0 & 1 & 1 & 0 & 0
\end{bmatrix}\!\!.](./images/48a9b4fe2ac04b78d2f760ffa1e7865cda239ed4.png)

The number of ways to get from vertex ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) to vertex ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png) in zero, one, or two steps is ![\mathbbm{1} + A + A^2](./images/682f986cf0c9d0b116be80839fcd7d6487440f41.png):

![\mathbbm{1} + A + A^2
= 
\begin{bmatrix}
1 & 1 & 2 & 0 & 1\\
0 & 1 & 1 & 0 & 1\\
1 & 0 & 1 & 0 & 1\\
2 & 1 & 1 & 1 & 1\\
1 & 1 & 1 & 0 & 1
\end{bmatrix}\!\!.](./images/920be5ecec53295630b8feef05c3062b72e6e380.png)

Observe that most of the graph ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) is well connected, except for Vertex 4, which has no inbound edges. The only way to get to Vertex 4 is if we start there.

The fact that we can discuss graph connectivity by doing matrix algebra is amazing when you think about it. The entry ![(\mathbbm{1} + A + A^2 )_{41}=2](./images/269855fcc4a7c49702049d1602a0837447a29166.png) tells us there are two ways to get from Vertex 4 to Vertex 1 in two steps or less. Indeed, we can either transition directly through the edge ![(4,1)](./images/b072fec43cf4b2762c9f392a7911923b5a16c31d.png) in one step, or indirectly via Node 5 in two steps by passing through the edges ![(4,5)](./images/6a4147c619fec1ec8cc3850f30eba9d39ac0aaca.png) and ![(5,1)](./images/93b19dc524d07745d6872406d5716ad48a8acb6a.png). Rather than manually counting all possible paths between vertices, we can compute all possible paths at once using matrix algebra on the adjacency matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

###[Discussion](./Front matter.md)

The analysis of connectivity between vertices is useful in many domains. Graphs are used to describe network flows, matching problems, social networks, webpages, and many other applications. In all these domains, the adjacency matrix plays a key role in graph representation. In[Section 8.1.15](./Chapter 8_ Probability theory.md), we’ll study the graph of all webpages on the web, and we’ll discuss Google’s PageRank algorithm, which uses information in the adjacency matrix of the web to compute an “importance” rank for each webpage.

###[Links](./Front matter.md)

\[ Graph theory and its applications \]

[`https://en.wikipedia.org/wiki/Graph_theory`](./Graph_theory.md)

\[ More details about adjacency matrices with examples \]

[`https://en.wikipedia.org/wiki/Adjacency_matrix`](./Adjacency_matrix.md)

###[Exercises](./Front matter.md)

E7.6 Find the adjacency matrix representation of the following graphs:

1.  ![graph_exercise_a](./images/graph_exercise_a.png)    
2.  ![graph_exercise_b](./images/graph_exercise_b.png)    
3.  ![graph_exercise_c](./images/graph_exercise_c.png)

E7.7 For each of the graphs in [7.4.5](./Chapter 7_ Applications.md), find the number of ways to get from vertex ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) to vertex ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) in two steps or less.

You can obtain the answer by computing the matrix ![\mathbbm{1} + A + A^2](./images/682f986cf0c9d0b116be80839fcd7d6487440f41.png).

##[7.5 Fibonacci sequence](./Chapter 7_ Applications.md)

We’ll now look at a neat trick for computing the ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png)th term in the Fibonacci sequence ![(0,1,1,2,3,5,8,13,21,34,55,89,144,\ldots)](./images/c2063a0db8e4c3d9a4082cb47e091882b255e815.png). The terms in the Fibonacci sequence ![(a_0, a_1, a_2, \ldots)](./images/9bf54722c486d2c86407299ac77234a534d6f779.png) start with ![a_0=0](./images/cb35c9fd78ae9096396f7bd43fd17aeb09b45bd1.png), ![a_1=1](./images/731070e0e18e1eeca23379f1a247c2c25383561e.png), and then each subsequent term is computed as the sum of the two terms preceding it:

![a_0 = 0, \quad a_1=1, \quad a_{n} = a_{n-1} + a_{n-2}, \; \textrm{for all} \; n \geq 2.](./images/04a3e22295fc0d1adfffb8cd65a61b98879e26e4.png)

The technical term for this type of formula is a _recurrence relation_. To compute the ![1000](./images/b5c26d560b3abf8ac16c16d37ec4812726e3d5be.png)th term in the sequence using the formula, you’ll need to perform ![1000](./images/b5c26d560b3abf8ac16c16d37ec4812726e3d5be.png) steps of arithmetic. But do we really need ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) steps to compute ![a_N](./images/ce152bdeb5463163bb914d0144985c7ef1e71278.png)? In this section we’ll learn an eigenvalue trick that allows us to compute ![a_N](./images/ce152bdeb5463163bb914d0144985c7ef1e71278.png) in just five steps of symbolic computation, no matter how big ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) is.

First we express the recurrence relation as a matrix product:

![\begin{array}{rcl}
a_{n+1} &=& a_{n} + a_{n-1}	\\
a_{n} &=& a_{n}	\\
\end{array}
\qquad
\Rightarrow
\qquad
\underbrace{
\!
\begin{bmatrix}
a_{n+1} \\
a_{n}
\end{bmatrix}
\!
}_{\vec{a}_n}
=
\underbrace{
\!
\begin{bmatrix}
1 & 1 \\
1 & 0
\end{bmatrix}
\!}_A \,
\underbrace{ \!
\begin{bmatrix}
a_{n} \\
a_{n-1}
\end{bmatrix}
\!
}_{\vec{a}_{n-1}}.](./images/148dba93345c2e59b5d1bf6586890cba7cf4acbb.png)

We can compute the ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png)th term in the Fibonacci sequence by starting from the initial column vector ![\vec{a}_0 = (a_1, a_0)^\sfT](./images/bfc5009fcb91019535fa7897b5032e74cabb285c.png), and repeatedly multiplying by the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):

![\begin{bmatrix}
a_{n+1} \\
a_{n}
\end{bmatrix}
=
A^N
\begin{bmatrix}
a_1 \\
a_{0}
\end{bmatrix}.](./images/c4b4aba98ae406a41f3ff60a0fbf90791afcf9bb.png)

We can “extract” ![a_N](./images/ce152bdeb5463163bb914d0144985c7ef1e71278.png) from the vector ![\vec{a}_N](./images/4f0810f7a5621a463766fc00f5d346fc7d847f12.png) by computing the dot product of ![\vec{a}_N](./images/4f0810f7a5621a463766fc00f5d346fc7d847f12.png) with the vector ![(0,1)](./images/51dc53e490143c62313d23af4c20f5a4e63d4d20.png). This dot product operation has the effect of “selecting” the second component of the vector ![\vec{a}_N](./images/4f0810f7a5621a463766fc00f5d346fc7d847f12.png).

Thus, we obtain the following compact formula for computing the ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png)th term in the Fibonacci sequence in terms of the ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png)th power of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):

![a_N = (0,1) A^{N}(1,0)^\sfT.](./images/365101fa8b05f217c3efd818aa34d36299aaafdb.png)

Do you remember the eigendecomposition trick for computing powers of matrices by only computing powers of their eigenvalues? We can use the eigendecomposition trick to compute ![A^N](./images/ffdd3fa5cf19da7296682a5548d5bfe298a541e4.png) very efficiently. The first step is to find the eigendecomposition of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png):

![\begin{align*}
\begin{bmatrix}
1 & 1 \\
1 & 0
\end{bmatrix}
& \; = \; \; 
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
\frac{5 + \sqrt{5}}{10}		&	\frac{ \sqrt{5} }{5}	\\
\frac{5 - \sqrt{5}}{10}		& 	-\frac{ \sqrt{5} }{5}	
\end{bmatrix}\!
}_{Q^{-1}}.
\end{align*}](./images/c711c74cfd5d236eefc878f06584ee65bfc79da9.png)

The two eigenvalues of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) are ![\lambda_1 = \varphi=\frac{1+\sqrt{5}}{2} \approx 1.618\ldots](./images/344013c7d78ac4b56a401e8ec8a9d996c2ff99d8.png) (the golden ratio), and ![\lambda_2 = \frac{-1}{\varphi} = \frac{1-\sqrt{5}}{2} \approx -0.618\ldots](./images/8889264efb6348024d066999039f5816416bc32f.png) (the negative inverse of the golden ratio). The columns of ![Q](./images/2c68144abb2caa43f10c6b4ec52940fd34c1c633.png) contain the corresponding eigenvectors of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png).

We can compute ![A^{N}](./images/ffdd3fa5cf19da7296682a5548d5bfe298a541e4.png) using the following formula:

![A^N\! 
=  \underbrace{A A \cdots A}_{N \textrm{ times}}
=  \underbrace{Q\Lambda Q^{-1} \;  Q\Lambda Q^{-1}  \cdots Q\Lambda Q^{-1} }_{N \textrm{ times}}
= Q\Lambda^N Q^{-1}.](./images/b335df9de2539c180885604f182c7a64dee58786.png)

To compute ![A^N](./images/ffdd3fa5cf19da7296682a5548d5bfe298a541e4.png) it is sufficient to compute the ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png)th powers of the eigenvalues ![\lambda_1 = \varphi](./images/2f2f21d0df53c0ae6e15d137c17f0c8fc64ba90d.png) and ![\lambda_2 = \frac{-1}{\varphi}](./images/599cb02289918f6dde2dceefb74473068e353df8.png). For example, to compute ![a_5](./images/1e477155f168094ada02ea43b316409421b1c3d3.png), the fifth element in the Fibonacci sequence, we compute ![A^{5}](./images/57dde55c8312eab653657459933597b6a8f48524.png) using ![Q\Lambda^5 Q^{-1}](./images/4f65767d2e635a6d3f617868f7cfb62b30a623c1.png), then use the formula ![a_5 = (0,1) A^{5}(1,0)^\sfT](./images/dfa0fed8a7f8a7ffadc15e0ceaeabcc0000f2e4a.png):

![\begin{align*}
a_5 
& =
\begin{bmatrix} 0 & 1 \end{bmatrix}\!\!
\begin{bmatrix}
1   &  1 \\
1   & 0
\end{bmatrix}^{\!5} \!
\begin{bmatrix} 1 \\ 0 \end{bmatrix}								\\
& =
\begin{bmatrix} 0 & 1 \end{bmatrix}
\!
Q
\begin{bmatrix}
\varphi^5 		& 0 					\\
0			& \frac{-1}{\varphi^5}
\end{bmatrix}
\!
Q^{-1}
\begin{bmatrix} 1 \\ 0 \end{bmatrix}								\\
& =
\begin{bmatrix} 0 & 1 \end{bmatrix}
\!\!
\begin{bmatrix}
8   &  5 \\
5   & 3
\end{bmatrix}
\!\!
\begin{bmatrix}1 \\ 0 \end{bmatrix}
=
\begin{bmatrix} 0 & 1 \end{bmatrix}
\!\!
\begin{bmatrix}8 \\ 5 \end{bmatrix}
=
5.
\end{align*}](./images/9fafb718c2eeaeac0d61364daf94592edaf4bccf.png)

We can similarly compute ![A^{55}](./images/cb63ed50e56f2f2f9b5fb818747ae991151adb7c.png):

![A^{55} = Q\Lambda^{55} Q^{-1}
=
\begin{bmatrix}
225851433717    &  139583862445 \\
139583862445    & 86267571272
\end{bmatrix},](./images/0a0b4f5dc7d6d5c4a26994daab3ca0ed052b9104.png)

then compute ![a_{55}](./images/7f89d5ee929db2a9dca46abc36b49b86a0e76880.png) using the formula,

![a_{55} = (0,1)A^{55}(1,0)^\sfT = 139583862445.](./images/019554cd4f6db9bc9857915923151f01962cb481.png)

The eigendecomposition trick allows us to take a mathematical shortcut by obtaining the answer ![a_N](./images/ce152bdeb5463163bb914d0144985c7ef1e71278.png) using a constant number of math operations—regardless of the size of ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png):

![a_N = (0,1) Q\Lambda^N Q^{-1} (1,0)^\sfT.](./images/8b8dcddfde6965bd661470c240f4b7ce28cbd7eb.png)

First compute the ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png)th power of ![\Lambda](./images/e31ea04fc05409ecc232f6fb468f35f4ebebd4fa.png). Then multiply ![\Lambda^N](./images/e750b57ed99aea4302b4183300f41b9a6953dfc2.png) by ![(0,1)Q](./images/3ee0b7f5142cb5f03cff92f21b1c2cab694dd54f.png) on the left, and by ![Q^{-1}(1,0)^\sfT](./images/b6d6f814e75b70f208ed1e0b5205090d6f33b319.png) on the right. This is interesting since other algorithms for computing the Fibonacci numbers usually require a number of steps proportional to the size of ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png).

There are some caveats to the approach outlined above. We assumed computing ![\varphi^N](./images/5aeb7977aa0e831235aae73b6931b1bedce8a1ec.png) and ![(-1/\varphi )^N](./images/98ec28a31fd7106744f06438d47a1226050f742d.png) could be done in a single operation, which is not a realistic assumption on any computer. Computing the power of a number usually takes several multiplication steps, so we’re kind of cheating when we count computing ![\Lambda^N](./images/e750b57ed99aea4302b4183300f41b9a6953dfc2.png) as a single step. Also, infinite-precision (symbolic) manipulations are not realistic either since computers work with finite-precision approximations to real numbers, so the eigenvalue trick will not work for large values of ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png). Basically, the eigenvalue trick is only a theoretical result and can’t be used in practical programs.

####[Links](./Front matter.md)

\[ See the Wikipedia page for more on the Fibonacci numbers \]

[`https://en.wikipedia.org/wiki/Fibonacci_number`](./Fibonacci_number.md)

###[Exercises](./Front matter.md)

E7.8 Recall the Fibonacci sequence ![a_n \! = \!(0,1,1,2,3,5,8,13,21,34,\ldots)](./images/981060a4c4bea3f80fe4bdfaf39791e4570c49c8.png). Describe what happens to the ratio ![\frac{a_{n+1}}{a_{n}}](./images/6786346302bec567c56f59184923c33f5a0e067e.png) as ![n\to \infty](./images/c56002afec0e22ba13376c0540e8ebd2704a69a6.png).

Compare the size of ![(\lambda_1)^n](./images/4500c237d2c0953b1585f99aca7d4034c0753bdf.png) and ![(\lambda_2)^n](./images/1c812250e93ad7a75567bece004a7b0c8a83d200.png) for large values of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png).

E7.9 Compute the matrix products in the expression ![(0,1) Q\Lambda^N Q^{-1}(1,0)^\sfT](./images/1ad5125bea6294993d86a0ce8ba2ccf98a1a790a.png) to obtain a closed-form expression for ![a_N](./images/ce152bdeb5463163bb914d0144985c7ef1e71278.png).

You can simplify expressions that contain square roots in the denominator as follows: ![\frac{1}{a+b\sqrt{5}}=\frac{1}{a+b\sqrt{5}}\cdot 1 = \frac{1}{a+b\sqrt{5}}\frac{a-b\sqrt{5}}{a-b\sqrt{5}}=\frac{a-b\sqrt{5}}{a^2-5b^2}](./images/136dd460273278cc3fd84be899fbc67e5554cdcf.png).

##[7.6 Linear programming](./Chapter 7_ Applications.md)

In the early days of computing, computers were primarily used to solve optimization problems, so the term “programming” is often used to describe optimization problems. _Linear programming_ is the study of linear optimization problems that involve linear constraints. These types of optimization problems play an important role in business: the whole point of corporations is to constantly optimize profits subject to time, energy, and legal constraints.

Many optimization problems can be expressed as _linear programs_. To solve an optimization problem is to find the optimal value, which is either the maximum or the minimum of some function, called the _objective function_. In a linear program, the objective function is a multivariable linear function ![g(x_1,x_2,\ldots,x_n)](./images/a4cb1fca85cea6609375c1a08e8c617b48d211cc.png) and the constraints on the variables of the problem are also linear. A linear program with ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) variables and ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) constraints is expressed as a maximization problem,

![\begin{align*}
\max_{x_1,x_2, \ldots, x_n} 	g(x_1,x_2, \ldots, x_n) 		\; &=\;  		c_1x_1  + c_2x_2 + \cdots + c_nx_n,
\end{align*}](./images/088c3657b0bb30245e06a5d8372827d9d6d15602.png)

subject to ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) linear constraints,

![\begin{align*}
a_{11}x_1	+ a_{12}x_2 + \cdots +  a_{1n}x_n 		&\leq \; 	b_1,	\\
a_{21}x_1	+ a_{22}x_2 + \cdots + a_{2n}x_n 		&\leq \; 	b_2,	\\
& \; \; \vdots 		\\
a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n 		&\leq \; 	b_m.
\end{align*}](./images/e7a6a19c8a5ee5667b003aa875a0a9e6b838f376.png)

The solution to this linear program is the vector ![(x_1,x_2,\ldots,x_n)](./images/e4ecec2dce3f43dc23c09120fcd980355a422437.png) that makes ![g(x_1,x_2, \ldots, x_n)](./images/a4cb1fca85cea6609375c1a08e8c617b48d211cc.png) as large as possible, and also satisfies all the constraints. For example, the variables ![x_1, x_2, \ldots, x_n](./images/e134cadee1393cbf3dbc898980a1c82c087a4cf9.png) could represent the production rates of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) different products made by a company. If the coefficients ![c_1, c_2, \ldots, c_n](./images/ee2d713d39c7a00541a0b1fad17446bfd010f302.png) represent the selling price for each of the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) products, then ![c_ix_i](./images/8e72a7c0efd45d7da70ad5848bed9e8f4f10f07d.png) represents the revenue generated by selling ![x_i](./images/95d233a0d2bf3ac8b54cc52b4da9bcc248fb5855.png) units of product ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png), and ![g(x_1,x_2, \ldots, x_n)=c_1x_1  + c_2x_2 + \cdots + c_nx_n](./images/41a17548ef465a0b869954455a1f56dfddc1b518.png) represents the total revenue for a given choice of production rates. The ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) inequalities could represent various limitations of human resources, production capacity, or logistics constraints. To solve the linear program is to find the production rates ![x_1, x_2, \ldots, x_n](./images/e134cadee1393cbf3dbc898980a1c82c087a4cf9.png) that maximize revenue, subject to the constraints.

The _simplex algorithm_ is a systematic procedure for finding solutions to linear programming problems. The simplex algorithm is somewhat similar to the Gauss–Jordan elimination procedure since it uses row operations on a matrix-like structure called a _tableau_. For this reason, linear programming and the simplex algorithm are often forced upon students taking a linear algebra course, especially business students. I’m not going to lie to you and tell you the simplex algorithm is very exciting, but it is very powerful. For this reason, you should know it exists, and develop a general intuition about how it works. And, as with all things corporate-related, it’s worth learning about so you’ll know the techniques of the enemy.

Since the details of the simplex algorithm might not be of interest to all readers of the book, I split the topic of linear programming into a separate tutorial, which you can read online at the link below.

\[ Linear programming tutorial \]

[`https://minireference.github.io/linear_programming/tutorial.pdf`](./tutorial.pdf.md)

##[7.7 Least squares approximate solutions](./Chapter 7_ Applications.md)

An equation of the form ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) could have exactly one solution (if ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is invertible), infinitely many solutions (if ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has a null space), or no solution at all (if ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png) is not in the column space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png)). In this section, we’ll discuss the case with no solution, and describe an approach for computing an _approximate_ solution ![\vec{x}^*](./images/941010006fa5230edc4e604149c930dfe8ccde45.png) such that the vector ![A\vec{x}^*](./images/053d0ed3a42e5efeb8d177d131106355110f6c30.png) is as close as possible to ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png).

We could jump right away to the formula for the least squares approximate solution (![\vec{x}^* = (A^\sfT A)^{-1} A^\sfT \vec{b}](./images/15f4048d8d73ba95cc10b8dbbf22b49c318eed94.png)), but this would hardly be enlightening or useful for your understanding. Instead, let’s learn about the least squares approximate solution in the context of a machine learning problem in which we’ll try to predict some unknown quantities based on a linear model learned from past observations. This is called _linear regression_ and it’s one of the most useful applications of linear algebra.

Your company’s database of current clients contains all the information about the frequency of purchases ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png), value of purchases ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), promptness of payment ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png), and other useful information. You know what is _really_ useful information, though? Knowing the customer lifetime value (CLV)—the total revenue this customer will generate during their entire relationship with your company. You have data on the CLVs of existing customers and you want to leverage this data to predict the CLVs of new customers.

Suppose you have data for ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) existing customers in the form of vectors, expressed as ![\vec{a}_i = (f_i, V_i, P_i, \ldots)](./images/973346456886dc0f58e4c57c6faeed450eeca401.png), and you calculate a customer lifetime value (CLV) for each existing customer, ![b_i = CLV_i](./images/b87748a010a19fc8a33c7fbb51ef7b95c0d2c52f.png). The resulting dataset consists of observations ![\vec{a}_i](./images/526e48cc32df10feb0b33714ad3cd65cf4c405ca.png) and outcomes ![b_i](./images/13294bd22e12bd7ece755875322827e8e82562b2.png):

![D =  \left\{
\begin{bmatrix}
\textrm{ ---} & \vec{a}_1 & \textrm{--- } \\
\textrm{ ---} & \vec{a}_2 & \textrm{--- } \\
\textrm{ ---} & \vec{a}_3 & \textrm{--- } \\
&   \vdots  &     \\
\textrm{ ---} & \vec{a}_N & \textrm{--- }
\end{bmatrix},
\begin{bmatrix}
b_1 		\\
b_2 		\\
b_3		\\
\vdots 	\\
b_N	
\end{bmatrix}	
\right\}
\!
= \{ A, \vec{b} \}.](./images/59f4be8db23dfdef0096dc7aa54509ac6ffcf71f.png)

The clients’ observational data is stored in an ![N \times n](./images/aa75bfd21b4b87ee22cf42ec9624a7f5c96dbd52.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), and the corresponding CLVs are stored as an ![N \times 1](./images/b01e98eeec38a771f699fa4b853c2725ae9e6747.png) column vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png).

#####[Statement of the problem](./Front matter.md)

Given the ![\vec{a}_{k}](./images/b543eb2850e2744444abdd73e8a71d21a3eef80b.png) of a new customer, predict the customer’s ![b_k](./images/0e18e1a01321e3b0478e6e5fc644c73fa9b64f60.png), based on the information in the dataset ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png).

###[Linear model](./Front matter.md)

A simple way to model the dependence of the label ![b_i](./images/13294bd22e12bd7ece755875322827e8e82562b2.png) on the observational data ![\vec{a}_i =  (a_{i1}, a_{i2}, \ldots, a_{in})](./images/3de216b16d408bb716e665d8b337a9e2057e8fda.png) is to use a linear model with ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) parameters ![m_1,m_2,\ldots,m_n](./images/69cc88f036417696e27169eee41b7f7f3ecf481a.png):

![y_{\vec{m}}(x_1,x_2,\ldots,x_n) 
=  m_1x_1 + m_2x_2 + \cdots + m_nx_n  
=  \vec{m} \cdot \vec{x}.](./images/2657bfc206c48fd4775a05852449010f4cd917ca.png)

If your model is accurate, then ![y_{\vec{m}}(\vec{a}_i)](./images/499ebe3ea4f373b5d3f73b930f8776804d3aeaab.png) will closely approximate ![b_i](./images/13294bd22e12bd7ece755875322827e8e82562b2.png). But how can we measure the accuracy of the approximation?

Let’s define _error terms_ that measure how the model’s predictions ![y_{\vec{m}}(\vec{a}_i)](./images/499ebe3ea4f373b5d3f73b930f8776804d3aeaab.png) differ from the observed values ![b_i](./images/13294bd22e12bd7ece755875322827e8e82562b2.png). The error term for the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th customer is

![e_i(\vec{m}) = | y_{\vec{m}}(\vec{a}_i)   - b_i |^2.](./images/319efacf84ea2005eac1bfae543cd0e970ad3ba8.png)

The expression ![e_i(\vec{m})](./images/3f0dbe6eac244390a53e39cbd9537ed70f919328.png) measures the _squared error_ between the model’s prediction and the known value. Our goal is to choose a model that makes the sum of all the error terms as small as possible:

![S(\vec{m})
= \sum_{i=1}^{N} e_i(\vec{m})
= \sum_{i=1}^{N} \left| y_{\vec{m}}(\vec{a}_i)   - b_i \right|^2.](./images/a8a776840bb8d8c2b0fac1daa377bde809f13d6b.png)

We’ll refer to the function ![S(\vec{m})](./images/d889e66ae1d7d7fb8a5fadc50316eb5b56928cb8.png) as the _objective function_, which is the usual terminology for optimization problems. Our goal is to choose the value of ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) that minimizes ![S(\vec{m})](./images/d889e66ae1d7d7fb8a5fadc50316eb5b56928cb8.png), the _sum of squared errors_ of the model’s predictions.

Intuitively, it makes sense to minimize the objective function ![S(\vec{m})](./images/d889e66ae1d7d7fb8a5fadc50316eb5b56928cb8.png) because it captures how the predictions of the model ![y_{\vec{m}}(\vec{a}_i)](./images/499ebe3ea4f373b5d3f73b930f8776804d3aeaab.png) differ from the values ![b_i](./images/13294bd22e12bd7ece755875322827e8e82562b2.png). The objective function will be zero (![S(\vec{m})=0](./images/e63fc4220e31b781cf17344ac7bf1ebffa48e34e.png)) if the model _perfectly_ predicts the data. On the other hand, any model prediction ![y_{\vec{m}}(\vec{a}_i)](./images/499ebe3ea4f373b5d3f73b930f8776804d3aeaab.png) that overshoots or undershoots the correct ![b_i](./images/13294bd22e12bd7ece755875322827e8e82562b2.png) value will lead to a large error term: ![\left| y_{\vec{m}}(\vec{a}_i) - b_i \right|^2](./images/f5310b4487086548c4ab47d30a4b9db590ea90be.png). Observe that the objective function ![S(\vec{m})](./images/d889e66ae1d7d7fb8a5fadc50316eb5b56928cb8.png) is a quadratic function: the error terms grow quadratically with the size of the discrepancy between the model and the actual values.

###[Linear algebra formulation](./Front matter.md)

When faced with an unfamiliar problem (such as finding the approximate solution to a system of equations ![A\vec{x}=\vec{b}](./images/8b222185a7f703f0bc259d216dfd737f68524fbf.png) using a quadratic error model) don’t become alarmed. Stand your ground and try relating the problem to something you’re more familiar with. Thinking about problems in terms of linear algebra can often unlock your geometric intuition and show you a path toward the solution.

Using a matrix-vector product, we can express the “vector prediction” of the model ![\vec{y}_{\vec{m}}](./images/15256079015d35af60a893b10fe05d6653d8e760.png) for the whole dataset in one shot: ![\vec{y}_{\vec{m}} = A\vec{m}](./images/213763cc8b13027efc6e44e8d03aae37e2c94812.png). The total squared error function for the model ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) on the dataset ![D = \{ A, \vec{b} \}](./images/50600077c30f00843d70fa83ab0fecfcf1bf8ac5.png) can be written as the following expression:

![\begin{align*}
S(\vec{m}) 	& = 		\sum_{i=1}^{N}  \left| y_{\vec{m}}(\vec{a}_i)   - b_i \right|^2 	\\
& = 		\|  \vec{y}_{\vec{m}}  -\vec{b} \|^2 						\\
& =  		 \| A\vec{m} - \vec{b} \|^2.
\end{align*}](./images/457d4aed1b0d733f5ec71131c5bfbdc9b89bcc3a.png)

The total squared error for the model ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) on the dataset ![\{ A, \vec{b} \}](./images/efff9aacb87efc0df95b559c18fdc7050b5fcf23.png) is the squared length of the vector ![A\vec{m} - \vec{b}](./images/e5ccdbaac7f3f08fbf9642b20a2e7abea3a4ca17.png).

In the ideal case, if the model were to perfectly match the observations, the total squared error would be zero, and the equation ![A\vec{m} =  \vec{b}](./images/2c88121ed59108377626f334a9a225b2239c793c.png) would have a solution:

![A\vec{m} - \vec{b} = 0
\qquad 
\Rightarrow	
\qquad
A\vec{m} =  \vec{b}.](./images/52b71d06647fb26b06b00a48d2fc2299b8870e6b.png)

In practice, however, the model predictions ![A\vec{m}](./images/b1668eb70eab2be80c458aca19819568a299dfa9.png) will never perfectly match the data ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png), so we must be content with the approximate solution ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png):

![A\vec{m} \approx \vec{b}.](./images/a446117cc19049bb9e948e860193dd073a40ac7a.png)

The _least squares approximate solution_ to this equation is chosen so as to minimize the total squared error function:

![\min_{\vec{m}}	 S(\vec{m}) 
\quad = \quad
\min_{\vec{m}}	\left\|A\vec{m} - \vec{b}\, \right\|^2.](./images/c1a78d5d88deac93499f8b851482411e58267b38.png)

In other words, of all the possible approximate solutions ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png), we must pick the one that makes the length of the vector ![A\vec{m} - \vec{b}](./images/e5ccdbaac7f3f08fbf9642b20a2e7abea3a4ca17.png) the smallest.

###[Finding the least squares approximate solution](./Front matter.md)

There are two possible approaches for finding the least squares solution, denoted ![\vec{m}^*](./images/69fe90c14f82da9351bec8f951e65e373c0b4761.png). We can either use calculus techniques to minimize the total squared error ![S(\vec{m})](./images/d889e66ae1d7d7fb8a5fadc50316eb5b56928cb8.png), or geometry techniques to find the shortest vector ![(A\vec{m} - \vec{b})](./images/bfd4660ce72cd5279c2a16df5afe5caa6f3643f2.png).

Regardless of the approach chosen, the trick to finding the least squares approximate solution to ![A\vec{m} \approx \vec{b}](./images/387640413e5992841834f2aac4182d7953ac098a.png) is to multiply the equation by ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png) to obtain

![A^\sfT \!A \, \vec{m}   = A^\sfT \, \vec{b}.](./images/fa9fa82ef1a09816032427727fc9f0cf25d26b48.png)

The matrix ![A^\sfT\! A](./images/d5ea84f3e435617427dcf6e8309c287b9de3ad16.png) will be invertible if the columns of A are linearly independent, which is the case for most tall-and-skinny matrices. We can therefore solve for ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) by multiplying both sides of the above equation by the matrix ![(A^\sfT \!A)^{-1}](./images/1520eed16266e94268fdb3f45179963ca98f86c1.png):

![\vec{m}  =  (A^\sfT \!A)^{-1}A^\sfT \vec{b}.](./images/a4f9c40dbc804c86ef3bfd3d0b04f1b72ed419e2.png)

Indeed, this expression is the _least squares solution_ to the optimization problem we set out to solve in the beginning of this section:

![\vec{m}^*
=
\mathop{\textrm{argmin}}_{\vec{m}} 	S(\vec{m}) 
=
\mathop{\textrm{argmin}}_{\vec{m}}	\left\|A\vec{m} - \vec{b}\, \right\|^2
=
(A^\sfT \!A)^{-1}A^\sfT \vec{b}.](./images/8eb792081dc6c895ec195eeceac6e6abdfc20185.png)

We can refer to the linear model ![y_{\vec{m}^*}](./images/3e604853f6524294e4e8098fa2bb6e71fd0c0df7.png) as the _best fit_ for the dataset ![\{ A, \vec{b} \}](./images/efff9aacb87efc0df95b559c18fdc7050b5fcf23.png) since it minimizes the sum of the prediction errors.

#####[Moore–Penrose inverse](./Front matter.md)

When we combine the particular combination of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), its transpose ![A^\sfT](./images/748c8c2373cc795eb0cc83b1f21191f24b04d31d.png), and the inverse operation that we used to find the approximate solution ![\vec{m}^*](./images/69fe90c14f82da9351bec8f951e65e373c0b4761.png), we get what’s called the _Moore–Penrose inverse_ or _pseudoinverse_ of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). We use the shorthand notation ![A^+](./images/b95a6e4080e50dd79fac3707f22a0cff41de50f1.png) (not to be confused with ![A^\dagger](./images/3763a4fed4d19a6bb65a04d027dc9aa010a3ee60.png)), for the entire expression:

![A^+ 	\,\eqdef\, (A^\sfT A)^{-1}A^\sfT.](./images/6997bdd0e26fb6eba8d3494ea166ff9bb3f49b6d.png)

Applying ![A^+](./images/b95a6e4080e50dd79fac3707f22a0cff41de50f1.png) to both sides of the approximate equation ![A\vec{m}\approx\vec{b}](./images/387640413e5992841834f2aac4182d7953ac098a.png) is analogous to solving the equation by applying the inverse,

![\begin{align*}
A^+\!A\vec{m}		& =		A^+\vec{b},		\\
\vec{m}			& =		A^+\vec{b}.
\end{align*}](./images/5a2c7fc554a0f14d75f51cf011db0852ed62e3ca.png)

However, the solution is approximate, since ![A\vec{m} \neq \vec{b}](./images/3f22aca0efc3be20bc42aab449f158a4be4a5ef4.png). The solution ![A^+\vec{b}](./images/6f376c182ad1b800efff88ee169efa515536c8f6.png) is optimal according to the sum of squared errors criterion ![S(\vec{m})](./images/d889e66ae1d7d7fb8a5fadc50316eb5b56928cb8.png).

#####[Example 1](./Front matter.md)

Given the dataset with six samples ![(x_i,b_i)](./images/be3af904e2f5b861d4ed58d8d49bcd7d198acd94.png): ![(105, 45)](./images/8f240ff729cd8e8a4f2a4aa47b9643d091d7a3a2.png), ![(113,63)](./images/c6f10c73c657e5f631cf275b15a11c4d647a674c.png), ![(125,86)](./images/b5acaa393af30231fc261af68b924f1f9bc09f4c.png), ![(137,118)](./images/327c646079fc80a6746f4785ed38fd35da6d792c.png), ![(141,112)](./images/5744535cc0d8a0661b9c97b403281915abe0e2d9.png), ![(153,169)](./images/368f61a9b0664b1960e8453bf6066cb168ad2e36.png), what is the best linear model ![y_m(x)=mx](./images/96c2b280dd6d80fdfafa4a5dbc7539e92a3dbb78.png) for predicting ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png) given ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)? The first step is to express the given samples in the standard form ![\{A,\vec{b}\}](./images/efff9aacb87efc0df95b559c18fdc7050b5fcf23.png), where ![A \in \mathbb{R}^{6\times 1}](./images/737f5b94d78bc67a924da6e33bbc5731124a8968.png) and ![\vec{b} \in \mathbb{R}^{6\times 1}](./images/40cadb4faa5b3566993069749ccd3cc1ad88b460.png). We then calculate the best parameter ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) using the Moore–Penrose inverse formula:

![\{A,\vec{b}\} 
=
\left\{ 
\begin{bmatrix}
105 \\ 113 \\ 125 \\ 137 \\ 141 \\ 153
\end{bmatrix},
\begin{bmatrix}
45 \\ 63 \\ 86 \\ 118 \\ 112 \\ 169
\end{bmatrix}
\right\}
\quad
\Rightarrow
\quad
m^* =  (A^\sfT A)^{-1}A^\sfT \vec{b} = 0.792.](./images/50771cae8b6483107548161f2289e9db4b9b7977.png)

The best-fitting linear model for the data is ![y(x)=0.792x](./images/5221e021cba13bf4a93a080cacec6900ad91253a.png). For the details of the calculation, see[`http://bit.ly/leastsq_ex1`](./leastsq_ex1.md).[Figure 7.4](./Chapter 7_ Applications.md) shows a scatter plot of the dataset ![\{(x_i,b_i)\}](./images/ee0c17c80f0869a1fe22a71e8338383962217104.png) and the graph of the linear model that best fits the data.

![linear_regression_plot](./images/linear_regression_plot.jpg)

Figure 7.4: The line of the form ![y_m(x)=mx](./images/9be63703d35362eaf8b41ef92bc4c28308124729.png) that best fits the set of data points ![(x_i,b_i) \in \mathbb{R}^2](./images/a3ac3a0fd465448bf339806c9d21f5ef4d537c7a.png). The plot shows a scatter plot of the data points, and the line of best fit ![y(x) = 0.792x](./images/f77a4eb7076accf59929ba6e305a1b1cdc26893f.png). The line passes through the middle of the dataset and minimizes the sum of the squared vertical differences between the model output ![y_m(x_i)](./images/754c3e414d04b24f34b762300f54d2fea37cf46e.png) and the true value ![b_i](./images/a51f62ee57fdbe27169dd91cf7bbc29cdb330897.png).

###[Geometric interpretation](./Front matter.md)

The solution to the least squares optimization problem,

![\vec{m}^*
\; = \; 
\mathop{\textrm{argmin}}_{\vec{m}} \| A\vec{m} - \vec{b} \|^2,](./images/261ec5c2b110513983fbd4b53077623592b3ad31.png)

can be understood geometrically as the search for the vector in the column space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) that is _closest_ to the vector ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png), as illustrated in[Figure 7.5](./Chapter 7_ Applications.md). As we vary the parameter vector ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png), we obtain different vectors ![A\vec{m} \in \mathcal{C}(A)](./images/c09ecf17cc0909b18afa1375898288e9c570e74f.png). Of all the points ![A\vec{m}](./images/b1668eb70eab2be80c458aca19819568a299dfa9.png) in the column space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), the point ![A\vec{m}^*](./images/6723ebf0fe936ec623854a4dfe11d22f3cb79104.png) is the closest to the point ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png).

Let’s define the _error vector_ that corresponds to the difference between the model prediction ![A\vec{m}](./images/b1668eb70eab2be80c458aca19819568a299dfa9.png) and the actual value ![\vec{b}](./images/2d8a7fa461c00df55bf5d15ac78501f81226775e.png):

![\vec{e}	\; \; \eqdef  \; \; 	A\vec{m} - \vec{b}.](./images/e86633adb612155fecc141ac60c60a23a4932e9f.png)

Using the geometric intuition and looking at[Figure 7.5](./Chapter 7_ Applications.md), we see that the optimal solution ![A\vec{m}^*](./images/6723ebf0fe936ec623854a4dfe11d22f3cb79104.png) occurs when the error vector is perpendicular to the column space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png). Recall the left fundamental subspaces of the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png): its column space ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png) and its orthogonal complement, the left null space ![\mathcal{N}(A^\sfT)](./images/c000bec6891375191f8d0e221f13c6ae42ca6c7e.png). Thus, if we want an error vector that is perpendicular to ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png), we must find an error vector that lies in the left null space of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png): ![\vec{e}^{\,*} \in \mathcal{N}(A^\sfT)](./images/24391b4b13414eacfa8d0e3f082bbf044aa6be1c.png). Using the definition of the left null space,

![\mathcal{N}(A^\sfT) = \{ \vec{w} \in \mathbb{R}^N \;|\; \vec{w}^\sfT M = \vec{0}^\sfT \},](./images/766046fa43d29e46a57233e182df4768db3d573f.png)

we obtain the following equation that defines ![\vec{m}^*](./images/69fe90c14f82da9351bec8f951e65e373c0b4761.png):

![(\vec{e}^{\,*})^\sfT A = 0
\qquad
\Rightarrow
\qquad
(A\vec{m}^* - \vec{b})^\sfT A = 0.](./images/547a82cc8fa362bb8c360d9b0b8499dbfd2c5158.png)

Taking the transpose of the last equation, we obtain ![A^\sfT(A\vec{m}^* - \vec{b})=0](./images/feb05a94ec8bf78eda1a90c6ad9731df7ad4277f.png), which is equivalent to condition ![A^\sfT\!A\vec{m}^* = A^\sfT\vec{b}](./images/9523290ad05d902e6df03cfeefff1b95bbbeb940.png) used to find ![\vec{m}^*](./images/69fe90c14f82da9351bec8f951e65e373c0b4761.png).

![geometric_interpretation_of_linear_least_squares_labels](./images/geometric_interpretation_of_linear_least_squares_labels.png)

Figure 7.5: Linear regression can be seen as a “search” problem restricted to the column space of the data matrix ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png). The least squares approximate solution ![\vec{m}^* = A^+\vec{b}](./images/31f0e57efcec2bd02382a1ef4713e183620f0ad7.png) corresponds to the point in ![\mathcal{C}(A)](./images/0e83764e60daef6d8fc51e1a7ff512574364155e.png) that is closest to ![\vec{b}](./images/9de6fd92ad217df8b49690b95fe00acb5956bf59.png). For this ![\vec{m}^*](./images/934c44863c6e54f95141c41ed2e37d7537045dbb.png), the error vector ![\vec{e}^{\,*}](./images/0e423af03cd9f84fb659276ad31fb0fad51ec722.png) is perpendicular to the column space of ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png).

Using geometric intuition about vector spaces and orthogonality proves helpful in solving this complex optimization problem. Choosing ![\vec{e}^{\,*}](./images/43311e28ced9e305889d8761f4dea97be147eea3.png) orthogonal to ![\mathcal{C}(A)](./images/b739ee05523d03f9314ea6e1a6886171dee0ffa7.png) leads to the shortest vector, ![A\vec{m}^* - \vec{b}](./images/05f4ae9f0998ff6a280ca1fd973634d4ea9c23f3.png), and produces the smallest total squared error, ![S(\vec{m}^*)= \| A\vec{m}^* - \vec{b} \|^2](./images/4348a2844f36881b42d5be8e2881e3e3d49db3e3.png).

###[Affine models](./Front matter.md)

We can also apply the Moore–Penrose inverse formula to more complicated models. A simple extension of a linear model is the _affine model_ ![y_{\vec{m},c}(\vec{x})=  \vec{m} \cdot \vec{x} + c](./images/0b9c085d812812e9552bf20bbc4677f7b587ff50.png), which adds a constant term ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) to the output of a linear model. The model parameters correspond to an ![(n+1)](./images/1a92a7f301b110623ddd5e73b5c32dda5b55476d.png)\-vector ![\vec{m}^\prime = (c,m_1,m_2,\ldots,m_n)](./images/d36ba58ee512ff9098bd4dae214b6f3f532e565d.png):

![y_{\vec{m}^\prime}(x_1,x_2,\ldots,x_n) 
=  m_0 + m_1x_1 + m_2x_2 + \cdots + m_nx_n  
=  \vec{m}^\prime \cdot (1,\vec{x}).](./images/0a9f131d41cc288766a504e27e2d79985ce3e73e.png)

For uniformity of notation, we’ll refer to the constant term as ![m_0](./images/1ca8d4bb8d2de1f7bc618b0a0d1d88b508bff3c2.png) instead of ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png). You can think of the parameter ![m_0](./images/1ca8d4bb8d2de1f7bc618b0a0d1d88b508bff3c2.png) as the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-intercept of the model.

To accommodate this change in the model, we must preprocess the dataset ![D = \{ A, \vec{b} \}](./images/50600077c30f00843d70fa83ab0fecfcf1bf8ac5.png) by adding a column of ones to the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), turning it into ![N \times (n+1)](./images/0af3bf39a7e411b42993142dcf4e02cd3d5cde79.png) matrix ![A^\prime](./images/159d093543a2410fe352596d95c1c568f45cab01.png). The new dataset looks like this:

![D^\prime =  \left\{
\begin{bmatrix}
1 & \textrm{ ---} & \vec{a}_1 & \textrm{--- } \\
1 & \textrm{ ---} & \vec{a}_2 & \textrm{--- } \\
1 & \textrm{ ---} & \vec{a}_3 & \textrm{--- } \\
\vdots   & &   \vdots  &     \\
1 & \textrm{ ---} & \vec{a}_N & \textrm{--- }
\end{bmatrix},
\begin{bmatrix}
b_0 		\\
b_1 		\\
b_2		\\
\vdots 	\\
b_N	
\end{bmatrix}	
\right\}
\!
= \{ A^\prime, \vec{b} \}.](./images/ba1164d36e90e418ab51f146df3314fabad2d56b.png)

Except for the preprocessing step, which is commonly called “data-massaging,” the remainder of the steps for finding a least squares solution are the same as in the case of linear regression. We find the optimal parameter vector ![\vec{m}^{\prime *}](./images/bdcbbb077aca9eb638dcb0a369e28a5d68885a82.png) by applying the Moore–Penrose inverse formula:

![\vec{m}^{\prime *}  = (A^{\prime\sfT} A^\prime)^{-1}A^{\prime\sfT} \vec{b}.](./images/212f505f9361299a4aff63853bd388e4f88e2434.png)

#####[Example 2](./Front matter.md)

Find the affine model ![y_{\vec{m}^{\prime}}(x)=m_0 + m_1x](./images/a358bc2e1c26b825c8ea765548dbdee7a37f5a5c.png) that best fits the data points from Example 1 (page ). To find the best parameter vector ![\vec{m}^{\prime}=(m_0,m_1)^\sfT](./images/1378891969d51f7f4f96e08f4115e405e1f4ffd8.png), we first preprocess the dataset by adding a column of ones to the data matrix. We then apply the inverse formula:

![\!\!\!
\{A^\prime,\vec{b}\} 
=
\left\{ 
\begin{bmatrix}
1 & 105 \\		1 &  113 \\ 	1 & 125 \\ 		1 & 137 \\ 		1 & 141 \\ 	1 & 153
\end{bmatrix},
\begin{bmatrix}
45 \\ 63 \\ 86 \\ 118 \\ 112 \\ 169
\end{bmatrix}
\right\}
\quad
\Rightarrow
\quad
\vec{m}^{\prime *}  
=
{A^{\prime}}^+ \vec{b} 
= 
\begin{bmatrix}
-210.4 \\ \; \; 2.397
\end{bmatrix}\!.](./images/5d7bc697bc3515f4199dfb01983838e485912710.png)

The affine model ![y(x)= -210.4 +2.397x](./images/5a0480fc13a27ea43ffc3184ba33d315bb9de371.png) is the best fit. I’ve omitted the details of the matrix calculation for brevity, but you can verify everything is legit here:[`http://bit.ly/leastsq_ex2`](./leastsq_ex2.md). See[Figure 7.6](./Chapter 7_ Applications.md) for the graph of the best fitting affine model.

![affine_regression_plot](./images/affine_regression_plot.jpg)

Figure 7.6: The affine model (![y_{\vec{m}^\prime}(x)=m_0 + m_1x](./images/029a62117176df7c65344584478c096101bdf076.png)) that best fits the data points is the line ![y(x)= -210.4 +2.397x](./images/da1852f3bab63501cbeabf2db69fcb7b13e50cc0.png). Allowing for one extra parameter, ![m_0](./images/e024a071a1b9008f0a4490b546e89d8cb23e2788.png) (the ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png)\-intercept), results in a model that fits the data much better, as compared to the fit in[Figure 7.4](./Chapter 7_ Applications.md).

Note the terms _linear regression_ and _linear least squares_ apply to fitting both linear models ![\vec{y}_{\vec{m}} = \vec{m}\cdot\vec{x}](./images/63245d510290b0368545b3830726ab1067b268a4.png), and affine models ![\vec{y}_{\vec{m}^{\,\prime}} = \vec{m}^\prime \cdot (1,\vec{x})](./images/b53fa7c7fef3b8f335b668702e58ebfabb4365d6.png). After all, an affine model is just a linear model with a ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-intercept, so it makes sense to refer to them by the same name.

###[Quadratic models](./Front matter.md)

The mathematical approach based on the Moore–Penrose inverse we used in linear regression can also be used to find approximate solutions for nonlinear models. For the sake of simplicity, let’s assume there are only two observed quantities in the dataset (![n=2](./images/d971bde3d9feee0a7e7e3c836b72e5b1c4a541cd.png)). The most general quadratic model for two variables is:

![y_{\vec{m}}(x,y) 
=  m_0 + m_1x + m_2y  \; \; + \; \;       m_3 xy + m_4x^2 + m_5y^2.](./images/2d5719b57824baffe5b7b89c41b3d18ae5b3c605.png)

The terms with coefficients ![m_0](./images/1ca8d4bb8d2de1f7bc618b0a0d1d88b508bff3c2.png), ![m_1](./images/9747323f90595beb9839f458f53ccdd924d69803.png), and ![m_2](./images/f05a6d25c78357311af1315bdb40ab4ab2c94bbb.png) describe an affine model for the variables ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and we add additional terms with parameters ![m_3](./images/f62e51e4a5d6fc33f6aea6d7466ae8cfd2f1c65c.png), ![m_4](./images/d9faebb94c8582a2a976fd56f8587e9bce6b7fb4.png), and ![m_5](./images/2aa1f174b38c6f6d73e83f990e85918719e1bbab.png) to describe quadratic components in ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png). The parameter vector for the most general quadratic model of two variables is six-dimensional: ![\vec{m} = (m_0,m_1,m_2,m_3,m_4,m_5)](./images/29c0b9e167dad9cdf769c77189bce19e85fcf766.png).

Assume we start from the following dataset:

![D =  \left\{
\begin{bmatrix}
x_1		& y_1		\\
x_2		& y_2		\\
\vdots   	& \vdots     	 \\
x_N		& y_N
\end{bmatrix},
\begin{bmatrix}
b_1 		\\
b_2 		\\
\vdots 	\\
b_N	
\end{bmatrix}	
\right\}
\!
= \{ A, \vec{b} \}.](./images/a5f010ebabe7063ead2697191fed3caecdcc4ab1.png)

To use the Moore–Penrose inverse formula, we must preprocess ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by adding several new columns:

![D^\prime =  \left\{
\begin{bmatrix}
1	& 	x_1	& y_1	& x_1y_1		& x_1^2 	& y_1^2	\\
1	& 	x_2	& y_2	& x_2y_2		& x_2^2 	& y_2^2	\\
\vdots &  \vdots & \vdots	& \vdots	& \vdots	& \vdots     	 \\
1	& 	x_N	& y_N	& x_Ny_N		& x_N^2 	& y_N^2	\\
\end{bmatrix}\!,
\begin{bmatrix}
b_1 		\\
b_2 		\\
\vdots 	\\
b_N	
\end{bmatrix}	
\right\}
\!
= 
\{ A^\prime, \vec{b} \}.](./images/c362bb2fabf53825a39eab2ef5bf71320a7a2589.png)

This preprocessing step allows us to compute a vector prediction of the model with parameters ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) applied to the entire dataset: ![\vec{y}_{\vec{m}} = A^\prime \vec{m}](./images/1808658d4a365a4a0c7413e2317dde9cf0ca0ffa.png). The total squared error for this model is ![S(\vec{m}) = \|  \vec{y}_{\vec{m}}  -\vec{b} \|^2](./images/21e7a1f36c6519eba91c7171a248cb1dc6454080.png). The least squares approximate solution ![\vec{m}^*](./images/69fe90c14f82da9351bec8f951e65e373c0b4761.png) is obtained as usual: ![\vec{m}^{*}  = (A^{\prime\sfT} A^\prime)^{-1}A^{\prime\sfT} \vec{b}](./images/0707c8b612c1804d6c5d4a51d76315d3004a47ec.png).

Note the number of parameters in a quadratic model grows—surprise, surprise—quadratically. There were ![n=2](./images/d971bde3d9feee0a7e7e3c836b72e5b1c4a541cd.png) variables in the above example, and the parameters vector ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) is six-dimensional. The number of parameters of a general quadratic model in ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) variables is ![\frac{1}{2}(n+1)(n+2)=\frac{1}{2}(n^2+3n+2)](./images/a3e59ba73e77a7e8295818e16cf6f2ba9076ded9.png). The number of model parameters is an important consideration to take into account when fitting models to large datasets.

#####[Example 3](./Front matter.md)

Imagine you’re a data-friendly business person and you want to pick which model to fit to a dataset ![\{A,b\}](./images/8cac066ba6edcc5cfcd4496139c95868122aa36f.png) with ![n=1000](./images/cc596b6caace4df8560e478ec587dc41aedc4db6.png) features. The observational data matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) has ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) rows and ![1000](./images/b5c26d560b3abf8ac16c16d37ec4812726e3d5be.png) columns. You have the option of choosing either an affine model, ![y_a(\vec{x})=m_0 + m_1x_1 + \cdots + m_{n}x_{n}](./images/0111eec3d35df823816658f110d279aeb07ce428.png), or a quadratic model, ![y_q(\vec{x})=m_0 + m_1x_1 + \cdots + m_nx_n + m_{n+1}x_1x_1 + m_{n+2}x_1x_2 + \cdots](./images/00684db9b5b39e89918f0088188b446a765bfb74.png), for the dataset.

To fit an affine model, you’ll need to preprocess ![A \in \mathbb{R}^{N\times 1000}](./images/f4ff97c7c59052435730e952af860fbbd42d745d.png) into ![A^\prime \in \mathbb{R}^{N\times 1001}](./images/13e5d8929f7176cd380469939ad63a28d1981bec.png), and then find the inverse of ![(A^{\prime\sfT}\!A^\prime) \in \mathbb{R}^{1001 \times 1001}](./images/b7781caba665d488735f44be8621c20f976dc201.png). That’s totally doable.

In contrast, the number of parameters in a quadratic model with ![n=1000](./images/cc596b6caace4df8560e478ec587dc41aedc4db6.png) dimensions is ![\frac{1}{2}(1000+1)(1000+2)= 501501](./images/09101192c5e7a897eb61273929b5f87e6def0373.png). To fit a quadratic model, you’ll need to preprocess the data matrix to obtain ![A^\prime \in \mathbb{R}^{N\times 501501}](./images/774a132de3fac3c631bfdb31f5e4190c865b3fa4.png), and then find the inverse of ![(A^{\prime\sfT}\!A^\prime) \in \mathbb{R}^{501501 \times 501501}](./images/635f0bf5f19c50907d9bca6c69bc7f53f07040e4.png). That’s a big matrix. You’ll need one terabyte of memory just to store all the entries of the matrix ![A^{\prime\sfT}\!A^\prime](./images/5c98f2f342aec0988c349c1a60f7e9e98e397793.png), and computing its inverse will take a _really_ long time.

So the choice is made; affine model it is. The affine model may be less accurate than a quadratic model, but if it works and provides value, you can use it. This is the reason why scientists, engineers, statisticians, and business folk are so crazy about building linear models, even though more advanced models are available. Linear models are a _sweet spot_ for prediction applications: they have great modelling power, they’re easy to implement, and they lead to computational problems that are easy to solve.

###[Links](./Front matter.md)

\[ Further discussion about least squares problems on Wikipedia \]

[`https://en.wikipedia.org/wiki/Linear_regression`](./Linear_regression.md)

[`https://en.wikipedia.org/wiki/Linear_least_squares_(mathematics)`](./Linear_least_squares_(mathematics.md))

\[ More about the Moore–Penrose inverse \]

[`https://en.wikipedia.org/wiki/Moore-Penrose_inverse`](./Moore-Penrose_inverse.md)

###[Exercises](./Front matter.md)

E7.10 You want to determine whether a coin is fair, so you toss it repeatedly and record the number of times it lands heads. On the first trial, you flip the coin eight times and obtain four heads, which is a heads-to-flips ratio of ![\frac{4}{8}](./images/34fc7ba078032439df9f5996999ba59066b36abf.png). On subsequent trials you obtain heads-to-flips ratios of ![\frac{9}{16}](./images/6b9b2b7267495c07820633b2c8b8d38f511ed6d6.png), ![\frac{13}{24}](./images/bab42e1bb00712c444b0189bdbc510c3bbb14076.png), ![\frac{17}{32}](./images/2bc90a5008dd87b18f793f6e8aeb40e114cffbcc.png), and ![\frac{20}{40}](./images/50416585e1ab9af36f512bbb62e572cdf51fe108.png). Find the best-fitting linear model ![h(x) = mx](./images/57694459c992c066ef17f70bf8c536ebbd9bbdaf.png) to describe the number of heads in a trial with ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) flips.

E7.11 Find the best-fitting affine model ![y = b + mx](./images/d484de126f7bd270645faa62fb2540d1a0ccdfdc.png) to the ![(x,y)](./images/58d6a47248c48257d2fcc374393dc19c64cfcc6b.png) data points ![(0,3.9)](./images/dbd6d2a4dced3fb846a088d9c8dddbbf8d08e4e4.png), ![(1,3.2)](./images/f3e003d2460fb42cebec83f850cd2e3d33d3e49d.png), and ![(2,1.9)](./images/7f32961f530660510599d788a9cded9b54fbc0df.png). Perform all the calculations by hand.

Find the Moore–Penrose inverse.

E7.12 Calculate the total squared error ![S(m^*) = \|Am^* - \vec{b}\|^2](./images/514fc038ac597f83d97ad00676c8b26f018b5694.png) of the best-fit linear model obtained in Example 1 (page ). Use the `SymPy` calculation at[`bit.ly/leastsq_ex1`](./leastsq_ex1.md) as your starting point.

The `Matrix` method `.norm()` might come in handy.

E7.13 Revisit Example 2 (page ) and find the total squared error of the best-fit affine model ![S(\vec{m}^{\prime*}) = \|A\vec{m}^{\prime*} - \vec{b}\|^2](./images/b270fba8e0f401d1954a141a58556e0f04ea7eb9.png). You can start from the calculation provided here[`bit.ly/leastsq_ex2`](./leastsq_ex2.md) and extend it.

##[7.8 Computer graphics](./Chapter 7_ Applications.md)

Linear algebra is the mathematical language of computer graphics. Whether you’re building a simple two-dimensional game with stick figures, or a fancy three-dimensional visualization, knowing linear algebra will help you understand the graphics operations that draw pixels on the screen.

In this section, we’ll discuss some basic computer graphics concepts. In particular, we’ll introduce _homogeneous coordinates_, a representation for vectors and matrices that uses an extra dimension. Instead of representing a three-dimensional vector as a triple of Cartesian coordinates ![(x,y,z)_c](./images/ca8195a9891d0dfcfed559dad97e5846655c1a49.png), we’ll use a four-dimensional homogeneous coordinates vector ![(x,y,z,1)_h](./images/d113bbbbc7db269b23f0884ba2f4f87335199e16.png). Homogeneous coordinates allow us to represent any computer graphics transformation as a matrix-vector product. We’ve already seen that scalings, rotations, reflections, and orthogonal projections can be represented as matrix-vector products. With homogeneous coordinates, we can represent translations and perspective projections as matrix products, too. That’s very convenient, since it enables us to understand all computer graphics operations in terms of matrix multiplications.

Computer graphics is a vast subject, far more extensive than the pages allotted in this book. To keep things simple, we’ll focus on two-dimensional graphics, and only briefly touch upon three-dimensional graphics. The goal is not to teach you the commands of computer graphics APIs like OpenGL and WebGL, but to give you the basic math tools for understanding what’s happening under the hood.

###[Affine transformations](./Front matter.md)

In[Chapter 5](./Chapter 5_ Linear transformations.md) we studied various linear transformations and their representations as matrices. We also briefly discussed the class of _affine transformations_, which consist of a linear transformation followed by a translation:

![\vec{w} 	=  T(\vec{v}) + \vec{d}.](./images/8cb6d5c6e8ee1fcaa1607166613e6aa3073b5b82.png)

In the above equation, the input vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is first acted upon by a linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png), and then the output of ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is translated by the displacement vector ![\vec{d}](./images/7905c6edce4836df7858602b11fd751a55b4b8f0.png) to produce the output vector ![\vec{w}](./images/e9b92e1d9d8797d4022a17266b33c894f4f538d4.png).

In this section, we’ll use _homogeneous coordinates_ for vectors and transformations, which allow us to express affine transformations as matrix-vector products in a larger vector space:

![\vec{w}  =  T(\vec{v}) + \vec{d}
\qquad
\Leftrightarrow
\qquad
\vec{W} 	=  A\vec{V}.](./images/8b5647bebf0da2d6f8aa17c4850fca972f2f0805.png)

If ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) is an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector, then its representation in homogeneous coordinates ![\vec{V}](./images/56a7f95f8db267bda5a093c972ea7f3e3d4098bb.png) is an ![(n+1)](./images/1a92a7f301b110623ddd5e73b5c32dda5b55476d.png)\-dimensional vector. The ![(n+1)\times(n+1)](./images/a412c769f10091f3afd0860b84a0e8d3363292e1.png) matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) contains the combined information about both the linear transformation ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) and the translation ![\vec{d}](./images/7905c6edce4836df7858602b11fd751a55b4b8f0.png).

###[Homogeneous coordinates](./Front matter.md)

Instead of using a triple of Cartesian coordinates to represent points ![p=(x,y,z)_c \in \mathbb{R}^3](./images/ecf79597bae10a1ce003a2b60008d6ff7b3b0d58.png), we’ll use the quadruple ![P=(x,y,z,1)_h \in \mathbb{R}^4](./images/0a121d037f9f2df0aa182dfe7ef2cd26a18f2267.png), which is a representation of the same point in _homogeneous coordinates_. Similarly, the vector ![\vec{v}=(v_x,v_y,v_z)_c \in \mathbb{R}^3](./images/71a4e1b35aeacadc686cbd4e34d20a3dd812a1de.png) in Cartesian coordinates corresponds to the vector ![\vec{V}=(v_x,v_y,v_z,1)_h \in \mathbb{R}^4](./images/54e58670ab6e914f521830d578e0c36363677efc.png) in homogeneous coordinates. Though there is no mathematical difference between points and vectors, we’ll stick to the language of points as it is more natural for graphics problems.

An interesting property of homogeneous coordinates is that they’re not unique: the vector ![\vec{v}=(v_x,v_y,v_z)_c](./images/568bc6a404fd3d10afe8c307c4adc319a3737b3c.png) corresponds to a whole _set of points_ in homogeneous coordinates, ![\vec{V}= \{ (\alpha v_x,\alpha v_y,\alpha v_z,\alpha)_h \}](./images/f7ce0d7d6146bb04816c44d6c97610eb716dd312.png), for ![\alpha\in \mathbb{R}](./images/291a1b884bfe1bd3bdd9e4811c426bcf4da094c5.png). This makes homogeneous coordinates invariant to scaling:

![\colvec{ a \\ b \\c }_{\!c}
\qquad
\Leftrightarrow
\qquad
\colvec{ a \\ b \\c \\1 }_{\!h}
=
\colvec{ 5a \\5b \\ 5c \\5}_{\!h}
=
\colvec{ 500a \\500b \\ 500c \\500}_{\!h}\!\!\!.](./images/13f409eb4fda7b4ea9e9065f72e5ebee46e6b8d1.png)

This is kind of weird, but this extra freedom to rescale vectors arbitrarily leads to many useful applications.

To convert from homogeneous coordinates ![(X,Y,Z,W)_h=(a,b,c,d)_h](./images/726039bf51fca77b69e965bdfc373a54f40955f6.png) to Cartesian coordinates, we divide each component by the ![W](./images/ff912058d501cbd876dd9285aaf90305b12e22bf.png)\-component to obtain the equivalent vector ![(X,Y,Z,W)_h=(\tfrac{a}{d},\tfrac{b}{d},\tfrac{c}{d},1)_h](./images/eabb91a2271df2d30dd18a5ba427fbef5f417c6f.png), which corresponds to the point ![(x,y,z)_c=\left(\tfrac{a}{d},\tfrac{b}{d},\tfrac{c}{d}\right)_{\!c} \in \mathbb{R}^3](./images/b2227281c620308c61c06766ef2ce8311849b494.png).

In the case when the underlying Cartesian space is two-dimensional, the point ![p=(x,y)_c \in \mathbb{R}^2](./images/ddd915621868869fcd7d05e8021a191413f1bd23.png) is written as ![P=(X,Y,W)_h=(x,y,1)_h](./images/f57761a839946839a1532477a20940c20ab08e1d.png) in homogeneous coordinates. The homogeneous coordinates ![(X,Y,W)_h=(a,b,d)_h](./images/48d6d614531165bb7ab7036e7169e5a19e6ec6bf.png) (where ![d\neq0](./images/7b1855a7bf3070a35119797a2ba5646d9c8edc6b.png)) represent the point ![(x,y)_c=\left(\tfrac{a}{d},\tfrac{b}{d}\right)_{\!c} \in \mathbb{R}^2](./images/615d0dd444932c1fbecf99c627d6ee6e673b12f0.png).

This conversion between homogeneous coordinates and Cartesian coordinates can also be understood geometrically, as illustrated in[Figure 7.7](./Chapter 7_ Applications.md). The point ![(X,Y,W)_h](./images/f4aaaf91cec7e19a5936c0662deb7a83fabf3c66.png) in homogeneous coordinates corresponds to an infinite line in the three-dimensional ![XYW](./images/41014cb920c8b7dd868de8587a74f1423d2cc5e4.png)\-coordinate space. To obtain the Cartesian coordinates for this point, find the intersection of the infinite line with the plane ![W=1](./images/75c9be7cc8826241eaf3cbfdc6a28236f2776232.png).

![homogeneous_plane_w1](./images/homogeneous_plane_w1.png)

Figure 7.7: A two-dimensional Cartesian point ![(x,y)_c](./images/681be0b217a56f26cb5f1e834657f4efc005d8d5.png) corresponds to an infinite line in a three-dimensional homogeneous coordinates space ![\{ (\alpha x,\alpha y,\alpha)_h, \; \alpha\in \mathbb{R} \}](./images/846b603e675b74fb28666601d0a5b5b04a8d9d4f.png). To convert a point from homogeneous coordinates to Cartesian coordinates, we must find where the infinite line intersects the plane ![W=1](./images/905257d0c4784eb3e0a5950411b9615321a3dbe0.png). The homogeneous coordinates of the intersection point will have the form ![(x,y,1)_h](./images/52d6da9f0bf89664c42ef9ed7bc086b0ec4ed8e3.png). The first two components of this point are the Cartesian coordinates ![(x,y)_c](./images/681be0b217a56f26cb5f1e834657f4efc005d8d5.png).

To distinguish Cartesian vectors from homogeneous vectors, we’ll use capital letters like ![P,\vec{A},\vec{B},\ldots](./images/b715ae1e109c14f56246044d3778d0430f6ef5c2.png) for points and vectors in homogeneous coordinates, and lowercase letters like ![p,\vec{a},\vec{b},\ldots](./images/f4dbce0fc9bfe27adc1b51ada9a930c1c077a5db.png) when referring to points and vectors in Cartesian coordinates.

####[Affine transformations in homogeneous coordinates](./Front matter.md)

Consider the affine transformation that consists of the transformation ![T:\mathbb{R}^2 \to \mathbb{R}^2](./images/5983a52066d18e5338bbb02e92cb094cfbdd0957.png) followed by a translation by ![\vec{d} = (d_1,d_2)](./images/76e14ac258a1809a00a9dfad8cbc1b2800359556.png). If ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png) is represented by the matrix ![M_T = \begin{bmatrix}
m_{11}	& m_{12}  \\
m_{21}	& m_{22}
\end{bmatrix}](./images/f8c9fea01dddf862dae887b3a3dd4736cb1c605d.png), then the affine transformation as a whole can be represented as follows:

![\begin{bmatrix}
x'	\\
y'	
\end{bmatrix}
=
\begin{bmatrix}
m_{11}	& \!m_{12}	\\
m_{21}	& \!m_{22}
\end{bmatrix}
\!\!
\begin{bmatrix}
x	\\
y	
\end{bmatrix}
+
\begin{bmatrix}
d_1	\\
d_2
\end{bmatrix}
\quad \Leftrightarrow \quad
\begin{bmatrix}
x'	\\
y'	\\
1
\end{bmatrix}
=
\begin{bmatrix}
m_{11}	& \!m_{12}	& \!d_1	\\
m_{21}	& \!m_{22}	& \!d_2	\\
0		& 0		& 1
\end{bmatrix}
\!\!
\begin{bmatrix}
x	\\
y	\\
1
\end{bmatrix}\!\!.](./images/36cf014fcb683cb19e3e9f57ae339246c27c5ec5.png)

In the homogeneous coordinates representation, the input has an additional component that contains the constant value one, and the matrix has an additional column that operates on this constant component. The result of the matrix-vector product is to add the constants ![d_1](./images/7af199fd88872b768590a90f0bfa8bcbae54d2da.png) and ![d_2](./images/428495dbe3412f5eb5b9b2071f1d0cd4bbb55412.png) to the first and second coordinates:

![x' = m_{11}x	+	m_{12}y	+	d_1,
\qquad
y' = m_{21}x	+	m_{22}y	+	d_2,](./images/5fb959526ebc177c2aca9450a6f223fe5f0c5fc7.png)

which is exactly what translation by ![\vec{d}](./images/7905c6edce4836df7858602b11fd751a55b4b8f0.png) is all about. As you can see, there’s nothing fancy about homogeneous coordinates. Make sure you understand the above matrix-vector products and that you’re convinced there is no new math here—just the good old matrix-vector product you’re familiar with.

###[Graphics transformations in 2D](./Front matter.md)

When points and vectors are represented in homogeneous coordinates, we can express most useful geometric transformations of the form ![T:\mathbb{R}^2 \to \mathbb{R}^2](./images/5983a52066d18e5338bbb02e92cb094cfbdd0957.png) as ![3\times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrices in homogeneous coordinates. In addition to affine transformations we discussed above, homogeneous coordinates also allow us to perform _perspective transformations_, which are of central importance in computer graphics. The most general transformation we can perform using homogeneous coordinates is

![\begin{bmatrix}
x^\prime	\\
y^\prime	\\
w^\prime
\end{bmatrix}
=
\begin{bmatrix}
m_{11}	& m_{12}	& d_1	\\
m_{21}	& m_{22}	& d_2	\\
p_1		& p_2	& 1
\end{bmatrix}
\!\!
\begin{bmatrix}
x	\\
y	\\
w
\end{bmatrix},](./images/366aee935a0ebdc49a30334feb6a5cf7f9c72b04.png)

where ![M = \begin{bmatrix}
m_{11}	& m_{12}  \\
m_{21}	& m_{22}
\end{bmatrix}](./images/c619906bcc9da31af201a992cfcd7121e7a168ef.png) corresponds to any linear transformation, ![\vec{d}=(d_1,d_2)](./images/76e14ac258a1809a00a9dfad8cbc1b2800359556.png) corresponds to a translation, and ![(p_1,p_2)](./images/0bdad1ae6b3d2f1c0a607d121c322d4d4d42061f.png) is a perspective transformation.

####[Linear transformations](./Front matter.md)

Let ![R_\theta](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png) be the clockwise rotation by the angle ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) of all points in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png). In homogeneous coordinates, this rotation is represented as

![p^\prime  =  R_\theta(p)
\quad
\Leftrightarrow
\quad
P^\prime = M_{R_\theta}P,](./images/32822ea3daa71028b8f891c54fc64e3704a76a55.png)

where ![M_{R_\theta}](./images/60dc1481c43df67b678450528f649658a2ec45a6.png) is the following ![3\times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrix:

![\begin{bmatrix}
\cos \theta		& \sin \theta		& 0	\\
-\sin \theta		& \cos \theta		& 0	\\
0			& 0				& 1
\end{bmatrix}\!.](./images/ec3ed07500f1093dee9246e98e44c0c7e1a270c0.png)

The ![2\times 2](./images/a45549bed0620dd87777e8a82a74d8aa8011bfa4.png) submatrix in the top-left corner of matrices in homogeneous coordinates can represent any linear transformation: projections, reflections, scalings, and shear transformations. The following equation shows the homogeneous-coordinates matrix representations of three linear transformations: the reflection through the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis ![M_{R_x}](./images/610b50976d1bc14a1d91b572c0dc56c97b8209c6.png), an arbitrary scaling ![M_{S}](./images/47f74708f99cb23182fd7597b3f6f09a1b4478d8.png), and a shear along the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis ![M_{SH_x}](./images/162721667ef2d1fb305d0aa7ac133ed4089208be.png).

![M_{R_x}
=
\begin{bmatrix}
1		& 0		& 0	\\
0		& -1		& 0	\\
0		& 0		& 1
\end{bmatrix}
\quad
M_{S}
=
\begin{bmatrix}
s_x		& 0		& 0	\\
0		& s_y	& 0	\\
0		& 0		& 1
\end{bmatrix}
\quad				
M_{SH_x}
=
\begin{bmatrix}
1		& a		& 0	\\
0		& 1		& 0	\\
0		& 0		& 1
\end{bmatrix}\!](./images/a06d02dd590c9b883abe016a1f13804be501ce39.png)

####[Orthogonal projections](./Front matter.md)

Projections can also be represented as ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrices. The projection onto the ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png)\-axis corresponds to the following representation in homogeneous coordinates:

![p^\prime = \Pi_x(p)
\qquad
\Leftrightarrow
\qquad
\begin{bmatrix}
x^\prime 	\\
0	 	\\
1
\end{bmatrix}
=
\begin{bmatrix}
1		& 0		& 0	\\
0		& 0		& 0	\\
0		& 0		& 1
\end{bmatrix}
\!\!
\begin{bmatrix}
x	\\
y	\\
1
\end{bmatrix}\!.](./images/3a5cbfd522440f6c93ae9b9febb70ef66dd2ba1c.png)

####[Translation](./Front matter.md)

The translation by the displacement vector ![\vec{d} = (d_x,d_y)](./images/3eeec930602bc2c1df55439d8a50a6f0ad2c58c5.png) corresponds to the matrix

![M_{T_{\vec{d}}}
=
\begin{bmatrix}
1		& 0		& d_x	\\
0		& 1		& d_y	\\
0		& 0		& 1
\end{bmatrix}\!.](./images/9bdd96bb41c54257ad19141f5d6fd38752ed32a8.png)

Note the top-left submatrix of ![M_{T_{\vec{d}}}](./images/83f1817c92988ed3e31c68789fc6716f41ae08d8.png) contains the identity matrix; we perform the identity linear transformation and a translation by ![\vec{d}](./images/7905c6edce4836df7858602b11fd751a55b4b8f0.png).

![homogeneous_coodinates_2d_transformations](./images/homogeneous_coodinates_2d_transformations.png)

Figure 7.8: Illustration of the different transformations on a sample shape. Source:[`wikipedia File:2D_affine_transformation_matrix.svg`](./Transformation_matrix.md)

Rotations, reflections, shear transformations, and translations can all be represented as multiplications by ![3 \times 3](./images/425200d1749f405fcad6aee4562f98df5876a3ff.png) matrices.[Figure 7.8](./Chapter 7_ Applications.md) shows examples of transformations we can perform using the matrix-vector product in homogeneous coordinates. I hope by now you’re convinced that this idea of adding an extra “constant” dimension to vectors is useful. But wait, there’s more! We haven’t yet seen what happens when we put coefficients in the last row of the matrix.

####[Perspective projections](./Front matter.md)

The notion of perspective is very important in the world of visual art. For a painting to look realistic, the relative size of the objects pictured must convey their relative distance from the viewer. Distant objects in the scene are painted smaller than objects in the foreground. To transform a three-dimensional scene into a realistic two-dimensional painting, we need to apply a _perspective transformation_. Rather than give you the general formula for perspective transformations, we’ll derive the matrix representation for perspective transformations from scratch. Trust me, it will be a lot more interesting.

We can understand perspective transformations by tracing imaginary light rays that originate from each corner of an object and travel to the eye of an observer ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) in a straight line (see[Figure 7.9](./Chapter 7_ Applications.md)). The image of the perspective projections is created along the path of the light ray, where the ray intersects the _projective plane_, which represents the screen where the image will form. Since we’re working in ![\mathbb{R}^2](./images/f635d8678256add2c13bd993e376c50a9ee406a9.png), we can draw a picture of what’s going on.

![homogeneous_coordinates_perspective_square](./images/homogeneous_coordinates_perspective_square.png)

Figure 7.9: The perspective projection of a square onto a screen. Note how the side of the square that is closer to the observer appears longer than the farther side.

Let’s assume the observer is placed at the origin, ![O=(0,0)](./images/e274d94922d4bd9ef8535f331f00c05ca8e961ea.png), and let’s compute the _perspective transformation_ that projects points onto the line with equation ![y=d](./images/81249f1185c524b7cf3c2b59520e5e9abcbd8d4d.png). Under this perspective projection, every point ![p=(x,y)](./images/adb59d0a48194b970f0198add2666a214e358042.png) in the plane maps to a point ![p^\prime = (x^\prime,y^\prime)](./images/2925d86f725b2584a8f8d242ada6532557cc838a.png) on the line ![y=d](./images/81249f1185c524b7cf3c2b59520e5e9abcbd8d4d.png).[Figure 7.10](./Chapter 7_ Applications.md) illustrates the situation.

![projection_onto_yeqd](./images/projection_onto_yeqd.png)

Figure 7.10: The point ![p^\prime=(x^\prime,y^\prime)](./images/fc30e9b5421388bc93c8c05dd4903ed2cfa6f676.png) is the projection of the point ![p=(x,y)](./images/c34d9cc57757900edd714e946c3f2ef0308f6fd4.png) onto the line with equation ![y=d](./images/85199f661484fd4c572e2ecb3032c61467a7a51c.png). The ratio of lengths ![d/y](./images/d0a03703da3e666fe4b18adc6037478da7dd98ad.png) must equal the ratio of lengths ![x^\prime/x](./images/e382fb30b04dfe762382f0c6b81d42163cad689a.png).

The only math prerequisite you need to remember is the general principle for _similar_ triangles: if a triangle with sides ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png) is similar to a triangle with sides ![a^\prime](./images/676842a6745c6489627eaeaccb15ae3767ac03d8.png), ![b^\prime](./images/0bf4dd6406df7bd2bd7dd22386442f99f58c9362.png), ![c^\prime](./images/c1acd52b1a1b3b8b20761393b89b20eae69950c8.png), then the ratios of the lengths of the triangles’ sides will be equal:

![\frac{a^\prime}{a}
\; \; 
=
\; \; 
\frac{b^\prime}{b}
\; \; 
=
\; \; 
\frac{c^\prime}{c}.](./images/92e5cfae53146602e19f408df98abc612e5cf5f2.png)

Since the two triangles in[Figure 7.10](./Chapter 7_ Applications.md) are similar, we know ![\frac{x^\prime}{x} = \frac{d}{y}](./images/12edebed13d96c650c6d1a4ba20741f925cd8ba7.png), and therefore we directly obtain the expression for ![(x^\prime, y^\prime)](./images/166638c9c02e2d319f6ab270b80439f1110b4847.png) as follows:

![\begin{align*}				
x^\prime 	&= 	\frac{d}{y}x,		\\
y^\prime 	&= 	\frac{d}{y}y = d.
\end{align*}](./images/08bf4887db0042d7f6ed263d088090e57dd4397a.png)

This doesn’t look very promising, however, since the expression for ![x^\prime](./images/a586d5136004ea7453b41817f14e8cc4a0e27a75.png) contains a division by ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png). The set of equations is not linear in ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), and therefore cannot be expressed as a matrix-product. If only there were some way to represent vectors and transformations that also allowed division by coefficients too.

Let’s analyze the _perspective transformation_ in terms of homogeneous coordinates, and see if we find anything useful:

![\colvec{
x^\prime	\\
y^\prime	\\
1
}
=
\colvec{
\frac{d}{y}x	\\
d			\\
1
}
=
\colvec{
x	\\
y	\\
\frac{y}{d}
}\!\!.](./images/81cbb536802b8d751cce233167c41159371b59c2.png)

The second equality holds because vectors in homogeneous coordinates are invariant to scalings: ![(a,b,c)_h=\alpha(a,b,c)_h](./images/e03923de4db3f394a0d25dda977ed070e83d6faf.png) for all ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png). We can shift the factor ![\frac{d}{y}](./images/fc7eec87707e5af398b31cebdedf65eb06ed141a.png) as we please: ![(\tfrac{d}{y}x,d,1) = \tfrac{d}{y}(x,y,\tfrac{y}{d}) = (x,y,\tfrac{y}{d})](./images/263de914d903513e96511c456ab89cf0664606d0.png). In the alternate homogeneous coordinates expression, we’re no longer dividing by ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png). This means we can represent the perspective transformation as a matrix-vector product:

![\colvec{
x^\prime	\\
y^\prime	\\
1
}
=
\colvec{
x	\\
y	\\
\frac{y}{d}
}
=
\begin{bmatrix}
1		& 0			& 0	\\
0		& 1			& 0	\\
0		& \frac{1}{d}	& 0
\end{bmatrix}
\!\!
\begin{bmatrix}
x	\\
y	\\
1
\end{bmatrix}\!.](./images/f47ae4b70319ecc9f8807ff943dd4aba794ab3ab.png)

Now that’s interesting. By preparing the vector ![(X^\prime,Y^\prime,W^\prime)](./images/e124618049be457a1d8d33fb06ca64eaa49ee4a7.png) with a third component ![W^\prime\neq1](./images/537d4350fe6c970d864b895699b7e78967dd9e53.png), we can force each coefficient to be scaled by ![\tfrac{1}{W^\prime}](./images/3fcd397386d28d4d1effbb3646dfd65903013933.png), which is exactly what we need for perspective transformations. Depending on how the coefficient ![W^\prime](./images/8410a7f23d52b15b69c94dfa6e11e2ea4fd0de14.png) is constructed, different perspective transformations can be obtained.

A _perspective projection_ transformation is a perspective transformation followed by an orthogonal projection that removes some of the vector’s components. The perspective projection onto the line with equation ![y=d](./images/81249f1185c524b7cf3c2b59520e5e9abcbd8d4d.png) is the composition of a _perspective transformation_ ![P:\mathbb{R}^3 \to \mathbb{R}^3](./images/42c2be7e2e6644fde27d7266862298cd0f0e42c7.png) followed by an orthogonal projection ![\Pi_x:\mathbb{R}^3 \to \mathbb{R}^2](./images/02145b2e10ae75789aa230029bb49af19273d250.png) which simply discards the ![y^\prime](./images/89a3e5b4e7e5ffa60e5d59b68fdd0b4492ba6ef1.png) coordinate:

![\begin{bmatrix}
x^\prime 	\\
1
\end{bmatrix}
\!
=
\!				
\begin{bmatrix}
1		& 0			& 0	\\
0		& 0			& 1
\end{bmatrix}
\!\!
\begin{bmatrix}
1		& 0			& 0	\\
0		& 1			& 0 	\\
0		& \frac{1}{d}	& 0
\end{bmatrix}
\!\!
\begin{bmatrix}
x	\\
y	\\
1
\end{bmatrix}
\quad
\Rightarrow
\quad
\begin{bmatrix}
x^\prime 	\\
1
\end{bmatrix}
\!
=
\underbrace{\!\!
\begin{bmatrix}
1		& 0			& 0	\\
0		& \frac{1}{d}	& 0
\end{bmatrix}
\!\!}_{\Pi_x P}
\begin{bmatrix}
x	\\
y	\\
1
\end{bmatrix}\!\!.](./images/83c406a64a4f590a9fa140988d028f63d0b5ede7.png)

Note that only the ![x^\prime](./images/a586d5136004ea7453b41817f14e8cc4a0e27a75.png) coordinate remains after the projection. This is the desired result since we want only the “local” coordinates of the projection plane ![y=d](./images/81249f1185c524b7cf3c2b59520e5e9abcbd8d4d.png) to remain after the projection.

Certain textbooks on computer graphics discuss only the combined perspective-plus-projection transformation ![\Pi_x P](./images/5db4838132016baf69e86140d3de565d719ca460.png), as described on the right side of the above equation. I prefer to treat the perspective transformation separately from the projection, since it makes the math easier to understand. Also, by including the “depth information” (the ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png)\-coordinates) of the objects we’re projecting we can determine which objects appear in front of others.

####[General perspective transformation](./Front matter.md)

Let’s now look at the general case of a perspective transformation that projects arbitrary points ![p=(x,y)](./images/adb59d0a48194b970f0198add2666a214e358042.png) onto the line ![ax + by = d](./images/eb78f39e9f6b2e99c11f2cca920631ae4effe5e7.png). Again, we assume the observer is located at the origin ![O=(0,0)](./images/e274d94922d4bd9ef8535f331f00c05ca8e961ea.png). We want to calculate the coordinates of the projected point ![p^\prime=(x^\prime,y^\prime)](./images/2925d86f725b2584a8f8d242ada6532557cc838a.png), as illustrated in[Figure 7.11](./Chapter 7_ Applications.md).

![projection_onto_axbyeqd](./images/projection_onto_axbyeqd.png)

Figure 7.11: The point ![p^\prime=(x^\prime,y^\prime)](./images/fc30e9b5421388bc93c8c05dd4903ed2cfa6f676.png) is the projection of the point ![p=(x,y)](./images/c34d9cc57757900edd714e946c3f2ef0308f6fd4.png) onto the line with equation ![ax+by=d](./images/a736875c6179c12b21df900813a847c9e349acf4.png). We define points ![\alpha^\prime](./images/04d54d5533e67b1fd831847295dd445ca58536e9.png) and ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png) in the direction of line’s normal vector ![\vec{n} = (a,b)](./images/fb5fbda9462886dd7946f286c7b9fb388e527772.png). The distances from the origin to these points are ![\ell^\prime](./images/dd431117b890a5ce886fcab2bb839b339e442733.png) and ![\ell](./images/a8b77e4128d434d2124f2dffd6c021866d5228a5.png) respectively. We have ![\ell^\prime/\ell=x^\prime/x=y^\prime/y](./images/3fa4d930acf4d5ad1147796771de302179bbe7b7.png).

To obtain the general perspective transformation, we’ll follow a logical reasoning similar to the special case we considered above based on the properties of similar triangles. Define ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) to be the projection of the point ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) onto the line with direction vector ![\vec{n}=(a,b)](./images/17def10ea92fde2142938ca612daf924745dfac7.png) passing through the origin. Using the general formula for distances (see[Section 4.1.5.3](./Chapter 4_ Geometric aspects of linear algebra.md)), we can obtain the length ![\ell](./images/bb962abb90510299183b434b954b75dbb99553a8.png) from ![O](./images/077930d34c865fd61442fa46de1bbb8cba255440.png) to ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png):

![\ell \; 
= 		d(O,\alpha)
= 		\frac{ \vec{n} \cdot p }{ \| \vec{n} \| }
=		\frac{ ax + by }{ \| \vec{n} \|  }.](./images/0671df2b4b4337753c371787e982906bfbcd520b.png)

Similarly, we define ![\ell^\prime](./images/78073bb033f111c66422eff196455eee0b277c86.png) to be the length of the projection of ![p^\prime](./images/8f19b83653e94bd936262825262d569d5aa55981.png) onto ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png):

![\ell^\prime \; 
=		d(O,\alpha^\prime)
= 		\frac{ \vec{n} \cdot p^\prime }{ \| \vec{n} \| }
= 		\frac{ ax^\prime + by^\prime }{ \| \vec{n} \|  }
= 		\frac{ d }{ \| \vec{n} \|  }.](./images/23e59fe8eba8a7ab6df1d132bd22f5e4a298d2cf.png)

The last equation holds true because the point ![p^\prime](./images/8f19b83653e94bd936262825262d569d5aa55981.png) is located on the line with equation ![ax+by=d](./images/eb78f39e9f6b2e99c11f2cca920631ae4effe5e7.png).

By the similarity of triangles, we know the ratio of lengths ![x^\prime/x](./images/464f0a79de90e8635f7cbe24d20afd446445f105.png) and ![y^\prime/y](./images/3a48d78e649ee00069cd91e53616b6d270a144c9.png) must equal the ratio of orthogonal distances ![\ell^\prime/\ell](./images/e8e0b11567bdb7965c289889aeb839ce395ce40e.png):

![\frac{x^\prime}{x} 
= \frac{y^\prime}{y} 
= \frac{\ell^\prime}{\ell}
= \frac{ d }{  ax + by }.](./images/cc77d5cc817b644e79e4edcc6524519ebe778027.png)

We can use this fact to express the coordinates ![x^\prime](./images/a586d5136004ea7453b41817f14e8cc4a0e27a75.png) and ![y^\prime](./images/89a3e5b4e7e5ffa60e5d59b68fdd0b4492ba6ef1.png) in terms of the original ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png) coordinates. As in the previous case, expressing points in homogeneous coordinates allows us to arbitrarily shift scale factors:

![\colvec{
x^\prime	\\
y^\prime	\\
1
}
=
\colvec{
\frac{\ell^\prime}{\ell}x	\\
\frac{\ell^\prime}{\ell}y	\\
1
}
=
\colvec{
x	\\
y	\\
\frac{\ell}{\ell^\prime}
}
=
\colvec{
x		\\
y		\\
\!\!\frac{ax+by}{d}\!\!
}\!\!.](./images/f72238205f48c659f67fcbef2cbf1f77a6cd16f0.png)

The last expression is linear in the variables ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and ![y](./images/32b4f839fd5a7c4051bbc31f343b40bfdb30bc3b.png), therefore it has a matrix representation:

![\colvec{
x^\prime	\\
y^\prime	\\
1
}
=
\colvec{
X^\prime	\\
Y^\prime	\\
W^\prime
}
=
\begin{bmatrix}
1		& 0			& 0	\\
0		& 1			& 0	\\
\frac{a}{d}	& \frac{b}{d}	& 0
\end{bmatrix}
\!\!
\colvec{
x	\\
y	\\
1
}\!\!.](./images/ec04b8a64a1a7eb2eae880272eca9e140687c540.png)

This is the most general example of a perspective transformation. The “scale factor” ![W^\prime](./images/8410a7f23d52b15b69c94dfa6e11e2ea4fd0de14.png) is a linear combination of the input coordinates: ![W^\prime=\tfrac{a}{d}x + \tfrac{b}{d}y](./images/3508894b546f2e2f33b225dbb8b24aa5660d9db9.png). Observe that by setting ![a=0](./images/897fa831f1648f14cf78f8b3b30c40fa5350e225.png) and ![b=1](./images/b63ea28293bc91e6a576131d50af49bff1d79bf5.png), we recover the perspective transformation for the projection onto the line ![y=d](./images/81249f1185c524b7cf3c2b59520e5e9abcbd8d4d.png).

###[Graphics transformations in 3D](./Front matter.md)

Everything we saw in the previous section about two-dimensional transformations also applies to three-dimensional transformations. A three-dimensional Cartesian coordinate triple ![(x,y,z)_c \in \mathbb{R}^3](./images/938081648ec573ec460fd3b15036e0a80ac3a3e3.png) is represented as ![(x,y,z,1)_h \in \mathbb{R}^4](./images/d7b611c7bcd4b49717995492a614f7beab6ed77d.png) in homogeneous coordinates. Transformations in homogeneous coordinates are represented by ![4 \times 4](./images/841e9fa0bb8c2499770ffd8babaaf06f37a4a26f.png) matrices. An affine transformation is represented by the matrix

![A
=
\begin{bmatrix}
m_{11}	& m_{12}	& m_{13}	& d_1	\\
m_{21}	& m_{22}	& m_{23}	& d_2	\\
m_{31}	& m_{32}	& m_{33}	& d_3	\\
0		& 0		& 0		& 1
\end{bmatrix}\!\!,](./images/6dcf9932ba793e00cd01041f25c37a9304588b2c.png)

and the perspective transformation onto the line ![ax+by+cz=d](./images/9127ff243e829b2850d6ae5b33161fdcb12f666d.png) with the observer at the origin is expressed as the matrix

![P
=
\begin{bmatrix}
1			& 0			& 0			& 0		\\
0			& 1			& 0			& 0		\\
0			& 0			& 1			& 0		\\
\frac{a}{d}		& \frac{b}{d}	& \frac{c}{d}	& 0
\end{bmatrix}\!\!.](./images/c7395f0dffe98a031b045cd6e5962dd6e227ae46.png)

These should look somewhat familiar to you. Affine transformations, projections, and perspective transformations are the same in 3D as in 2D, except we’re now working in a four-dimensional homogeneous coordinates space.

The best part about being able to apply the homogeneous coordinates representation to all transformations is that we can _compose_ transformations together, in a way that’s similar to building with LEGOs. We’ll learn about this in the next section.

###[3D graphics programming](./Front matter.md)

Inside every modern computer is a special-purpose processor, called the _graphics processing unit_ (GPU), which is dedicated to computer graphics operations. Modern GPUs can have thousands of individual graphics processing units called _shaders_, and each shader can perform millions of linear algebra operations per second. Think about it; thousands of processors working in parallel to calculate matrix-vector products for you—that’s a lot of linear algebra calculating power!

The reason we need so much processing power is because 3D models are made of thousands of little polygons. Drawing a 3D scene (also known as _rendering_) involves performing linear algebra manipulations on all these polygons. This is where the GPU comes in. The job of the GPU is to translate, rotate, and scale the polygons of the 3D models by placing them into the scene, and then computing what the scene looks like when projected to the two-dimensional window (the screen) through which you’re observing the virtual world. This transformation—from the model coordinates to world coordinates, and then to screen coordinates (pixels)—is carried out in a _graphics processing pipeline_.

![graphics-processing-pipeline](./images/graphics-processing-pipeline.png)

Figure 7.12: A graphics processing pipeline for drawing 3D objects on the screen. A 3D model is composed of polygons expressed with respect to a coordinate system centred on the object. The model matrix positions the object in the scene, the view matrix positions the camera in the scene, and finally the projection matrix computes what should appear on the screen.

We can understand the graphics processing pipeline as a sequence of matrix transformations: the model matrix ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png), the view matrix ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), and the projection matrix ![\Pi_s](./images/d6e82adef938894acc54844ac38a136f168d9d34.png). The GPU applies this sequence of operations to each of the object’s vertices, ![(x,y,z,1)_o](./images/b3cc7a64e7f91a28fe6c356cb584460f2d7c6a41.png), to obtain the pixel coordinates, ![(x^\prime,y^\prime)_s](./images/e0c8d36af6bc409b975980354e963ee6aeef15f0.png), of the vertices on the screen:

![\colvec{
\!x^\prime\!\!		\\
\!y^\prime\!\!
}_{\!s}
\!
= 
\Pi_s V M
\!
\colvec{
\!x\!\!	\\
\!y\!\!	\\
\!z\!\!	\\
\!1\!\!
}_{\!m}
\quad
\Rightarrow
\quad
(x,y,z,1)_m M^\sfT V^\sfT \Pi_s^\sfT  = (x^\prime,y^\prime)_s.](./images/b06c9e60a26dfc1a268752a962d2b80aee85ff2e.png)

In the context of computer graphics, it is customary to represent the graphics processing pipeline in the “transpose picture,” so that vertex data flows from left to right as in[Figure 7.12](./Chapter 7_ Applications.md). Instead of representing vertices as column vectors multiplied by matrices ![M](./images/c059431ac94a828618aad52f8e0dbab3dc37b1fc.png), ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png), and ![\Pi_s](./images/d6e82adef938894acc54844ac38a136f168d9d34.png) from the left, we represent vertices as row vectors multiplied by matrices ![M^\sfT](./images/351e3c059c9c1ab7f9c3644694084f639f6fd2eb.png), ![V^\sfT](./images/87478ea0be889391f8791e5603b7495e8704d3ff.png), and ![\Pi_s^\sfT](./images/e2c2d0bb888c054e7a6e4c9003d7bec31a04aef3.png) from the right. All the reasoning remains the same, and all the transformation matrices described above still work; you just might need to transpose them if you’re using them in a program.

Finally, a comment on efficiency. It is not necessary to compute the matrix-vector products with ![M^\sfT](./images/351e3c059c9c1ab7f9c3644694084f639f6fd2eb.png), ![V^\sfT](./images/87478ea0be889391f8791e5603b7495e8704d3ff.png), and ![\Pi_s^\sfT](./images/e2c2d0bb888c054e7a6e4c9003d7bec31a04aef3.png) for each vertex. It’s much more efficient to pre-compute a combined transformation matrix, ![C^\sfT=M^\sfT V^\sfT \Pi_s^\sfT](./images/93287f2fb90f3ffb7cabeb87646b66c9d7ee7e21.png), and apply ![C^\sfT](./images/a51a010fe4f60d87127d354d3b147e44ac0cf91b.png) to each of the coordinates of the 3D objects. Similarly, when adding another object to the scene, only the model matrix needs to be modified, while the view and projection matrices remain the same.

####[Practical considerations](./Front matter.md)

We discussed homogeneous coordinates and the linear algebra transformations used for computer graphics. This is the essential theory you’ll need in order to get started with computer graphics programming. The graphics pipelines used in modern 3D software involve a few more steps than the simplified version shown in[Figure 7.12](./Chapter 7_ Applications.md). We’ll now discuss some points and practical considerations for programming computer graphics on real GPUs:

-   There are actually _two_ graphics pipelines at work in the GPU. The _geometry pipeline_ handles the transformation of polygons that form the 3D objects. A separate _texture pipeline_ controls the graphics patterns that fill the polygons. The final step in the rendering process combines the outputs of the two pipelines.
-   The model and view matrices can be combined to form a single model-view matrix that converts object coordinates to camera coordinates.
-   Not all objects in the scene need to be rendered. We don’t need to render objects that fall outside the camera’s viewing angle. We can also skip objects that are closer than the _near plane_ or farther than the _far plane_ of the camera. Though the scene could extend infinitely, we’re only interested in rendering the subset of the scene that we want displayed on the screen, which we call the _view frustum_. See the illustration in[Figure 7.13](./Chapter 7_ Applications.md).

![homogeneous_perspectie_proj](./images/homogeneous_perspectie_proj.jpg)

Figure 7.13: The perspective transformation that projects a three-dimensional model onto a two-dimensional screen surface. Note only a subset of the scene (the _view frustum_) is drawn, which lies between the _near plane_ and the _far plane_ within the field of view.

I encourage you to pursue the subject of computer graphics on your own. There are excellent free resources for learning OpenGL and WebGL on the web.

###[Discussion](./Front matter.md)

Homogeneous coordinates and projective geometry are powerful mathematical techniques with deep connections to many advanced math subjects. For the purpose of this section, we explored the subject from an engineering perspective—as a handy trick for working with computer graphics using matrix-vector products. Homogeneous coordinates have many other applications that we did not have time to discuss. We’ll briefly mention some of these additional applications here, with the hope of inspiring you to research the subject further.

Homogeneous coordinates are convenient for representing planes in ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png). The plane with general equation ![ax + by + cz = d](./images/9127ff243e829b2850d6ae5b33161fdcb12f666d.png) is represented by the vector ![\vec{N}=(a,b,c,-d)](./images/01c348dc77445f3830d4df62d575a62867fab5e2.png) in homogeneous coordinates. This is a natural way to express planes. Instead of describing the plane’s normal vector ![\vec{n}](./images/73fa40109cf90703e887257086fe879fea458953.png) separately from the constant ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png), we can represent the plane by an “enhanced” normal vector ![\vec{N} \in \mathbb{R}^4](./images/ad97cbb2d8dad7c5fcb6fa9a78ec38ad807fceb8.png):

![\textrm{Plane with } \vec{n} = (a,b,c) \textrm{ and constant } d
\quad
\Leftrightarrow
\quad
\vec{N} = (a,b,c,-d).](./images/c17cce675c043e5d7954002bb6f1d33f5b12f27a.png)

This is really cool because we can now use the same representation for both vectors and planes, and perform vector operations between them. Yet again, we find a continuation of the “everything is a vector” theme we’ve encountered throughout this book.

What good is representing planes in homogeneous coordinates? For starters, it allows us to verify whether any point ![\vec{P}](./images/2f4fac0d6109451fefcd2871426afbf5b9b44a34.png) lies in the plane ![\vec{N}](./images/d2a6628408b9379dd8ca8e75d89185e979d096ce.png) by computing the dot product ![\vec{N} \cdot \vec{P}](./images/1d266dc50476dbedc9bd27625cc44b3f61d6344a.png). The point ![\vec{P}](./images/2f4fac0d6109451fefcd2871426afbf5b9b44a34.png) lies inside the plane with normal vector ![\vec{N}](./images/d2a6628408b9379dd8ca8e75d89185e979d096ce.png) if and only if ![\vec{N} \cdot \vec{P}=0](./images/ab4a2b5a454b347ab690c3b4d03799b4167d9c66.png). Consider the point ![\vec{P}_1=(0,0,\frac{d}{c},1)](./images/1cb9f9995a4b2d817ba1bb5746c0bb2ef2d3402a.png) that lies in the plane ![ax + by + cz = d](./images/9127ff243e829b2850d6ae5b33161fdcb12f666d.png); we can verify that

![\vec{N} \cdot \vec{P}_1
=
(a,b,c,-d) \cdot (0,0,\tfrac{d}{c},1)
= 
0.](./images/c5b1a60a0d22daa4f5534aecd31aec6d11727230.png)

It’s also possible to easily obtain the homogeneous coordinates of the plane ![\vec{N}](./images/d2a6628408b9379dd8ca8e75d89185e979d096ce.png) that passes through any three points, ![\vec{P}](./images/2f4fac0d6109451fefcd2871426afbf5b9b44a34.png), ![\vec{Q}](./images/43485e5aa84a3a33f2723ec38a96f44cdd093d29.png), and ![\vec{R}](./images/96df7bed823f9c8cc89078e90d263188a6b3c59d.png). We’re looking for a vector ![\vec{N}](./images/d2a6628408b9379dd8ca8e75d89185e979d096ce.png) that is perpendicular to all three points. We can obtain ![\vec{N}](./images/d2a6628408b9379dd8ca8e75d89185e979d096ce.png) using a generalization of the cross product, computed using a four-dimensional determinant:

![\vec{N}
=
\begin{vmatrix}
\hat{e}_1 &  \hat{e}_2 	& \hat{e}_3 & \hat{e}_4  		\\
p_{x} 	& p_y		& p_z 	  & p_w			\\
q_{x} 	& q_y		& q_z 	  & q_w			\\
r_{x} 	& r_y			& r_z 	  & r_w
\end{vmatrix}\!,](./images/815044c6910dcfcaea76402fddff417ab5586001.png)

where ![\{ \hat{e}_1,  \hat{e}_2, \hat{e}_3, \hat{e}_4 \}](./images/977a7db48dd8c98f571d93712b157f2712857493.png) is the standard basis for ![\mathbb{R}^4](./images/63147fde7ca40efcdbf48e4b0a82e082577ebd3b.png). I bet you haven’t seen a four-dimensional cross product before—this stuff is wild! See the links below if you want to learn more about homogeneous coordinates, projective spaces, or computer graphics.

###[Links](./Front matter.md)

\[ A detailed tutorial series on WebGL \]

[`https://github.com/greggman/webgl-fundamentals/`](./webgl-fundamentals.md)

\[ Visualization of polygon drawing in a 3D scene \]

[`http://orbides.org/apps/superslow.html`](./superslow.md)

##[7.9 Cryptography](./Chapter 7_ Applications.md)

Cryptography is the study of secure communication. The two main tasks that cryptographers aim to achieve are private communication (no eavesdroppers) and authenticated communication (no impersonators). Using algebraic operations over finite fields ![\mathbb{F}_q](./images/d8fd0f1eff28d9e6d2783aadef13a973c284ce38.png), it’s possible to achieve both of these goals. Math is the weapon for privacy!

The need for private communication between people has existed long before the development of modern mathematics. Thanks to modern mathematical techniques, we can now perform cryptographic operations with greater ease, and build cryptosystems with security guaranteed by mathematical proofs. In this section, we’ll discuss the famous _one-time pad_ encryption technique invented by Gilbert Vernam. One-time pad encryption is important because Claude Shannon proved it is _absolutely secure_. In order to understand what that means precisely, we’ll first need some context about the concepts studied in the field of cryptography.

###[Context](./Front matter.md)

The secure communication scenarios we’ll discuss in this section involve three parties:

-   Alice is the message sender
-   Bob is the message receiver
-   Eve is the eavesdropper

Alice wants to send a private message to Bob, but Eve has the ability to see all communication between Alice and Bob. You can think of Eve as a Facebook administrator, or an employee of the Orwellian, privacy-invading web application _du jour_. To defend against Eve, Alice will _encrypt_ her messages before sending them to Bob, using a secret key only Alice and Bob have access to. Eve will be able to capture the encrypted messages (called _ciphertexts_) but they will be unintelligible to her because of the encryption. Assuming Bob receives the messages from Alice, he’ll be able to _decrypt_ them using his copy of the secret key. Encryption allows Alice and Bob to have _private_ communication despite Eve’s eavesdropping.

Cryptography is an interesting subject that is very pertinent in the modern age of pervasive network surveillance. Learning cryptography is a bit like learning kung fu for self defence. You don’t need to go around beating people up, but you should know how to defend yourself in case something happens. I encourage you to learn more about practical cryptography for your communications. Knowing some basics about passwords, secret keys, digital signatures, and certificates will help you keep pace with the forces out there.

The material in this section only scratches the surface of all there is to learn about cryptography; it serves to illustrate the main concepts through a simple example: the _one-time pad_ encryption protocol. This simple encryption scheme is provably unconditionally secure, given some assumptions about the secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png).

###[Definitions](./Front matter.md)

A cryptographic protocol consists of an encryption function, a decryption function, and a procedure for generating the secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png). For simplicity we assume messages and keys are all binary strings:

-   ![\vec{m} \in \{0,1\}^n](./images/d89ab3db16752bb60a9567feaadd226980b0bf73.png): the _message_ or _plaintext_ is a bitstring of length ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)
-   ![\vec{k}  \in \{0,1\}^n](./images/375acb55f12052d61aefccf5106a9c4e192f7c1f.png): the _key_ is a shared secret between Alice and Bob
-   ![\vec{c} \in \{0,1\}^n](./images/5c636ca74717d76a6749909b2297e853cb10c2c9.png): the _ciphertext_ is the encrypted message
-   ![\textrm{Enc}(\vec{m},\vec{k})](./images/3bd4e217d328053f0200ffd083a5e53b1c9d3524.png): the encryption function that takes as input a message ![\vec{m}  \in \{0,1\}^n](./images/d89ab3db16752bb60a9567feaadd226980b0bf73.png) and the key ![\vec{k} \in \{0,1\}^n](./images/375acb55f12052d61aefccf5106a9c4e192f7c1f.png) and produces a ciphertext ![\vec{c} \in \{0,1\}^n](./images/5c636ca74717d76a6749909b2297e853cb10c2c9.png) as output
-   ![\textrm{Dec}(\vec{c},\vec{k})](./images/afbd16de58f50ac4ea92d18365617555f3451607.png): the decryption function that takes as input a ciphertext ![\vec{c}  \in \{0,1\}^n](./images/5c636ca74717d76a6749909b2297e853cb10c2c9.png) and the key ![\vec{k} \in \{0,1\}^n](./images/375acb55f12052d61aefccf5106a9c4e192f7c1f.png) and produces the decrypted message ![\vec{m} \in \{0,1\}^n](./images/d89ab3db16752bb60a9567feaadd226980b0bf73.png) as output

We consider the protocol to be secure if Eve cannot gain any information about the messages ![\vec{m}_1,\vec{m}_2,\ldots](./images/71f2f328da1a148542f3d62473ab5c5646b4e9ba.png) from the ciphertexts ![\vec{c}_1,\vec{c}_2,\ldots](./images/47a1af79e91453baeb72d08f1d7b303a91839c10.png) she intercepts.

Before we describe the one-time pad encryption protocol and discuss its security, we must introduce some background about binary numbers.

###[Binary](./Front matter.md)

The cryptographic operations we’ll discuss in this section apply to information encoded _in binary_. A _bit_ is an element of the binary field, a finite field with two elements ![\mathbb{F}_2 \eqdef \{0,1\}](./images/cd1876175e8537de7c0e354082e0dcf4c52c59cc.png). A _bitstring_ of size ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector of bits ![\vec{v} \in \{0,1\}^n](./images/4f9d36a7781014dea25d4fc659be24e944585a34.png). For notational simplicity, we denote bitstrings as ![v_1v_2\cdots v_n](./images/325fb545b85a6d99213751fe75e5ca7962a4dff6.png) instead of using the usual vector notation ![(v_1,v_2, \ldots, v_n)](./images/a8412d31821f825d4716112d3bc8da172d6c37df.png). For example, ![0010](./images/fac31ffb1217d907919b28a1d19fd592346f8feb.png) is a bitstring of length ![4](./images/d642a42f2cf4e1514233d611b91e5d4646202fc8.png).

All information in modern digital systems is encoded in binary. Every file on your computer consists of long sequences of bits that are copied between disk memory, RAM, caches, and CPU registers. For example, using the ASCII encoding convention, the character `a` is encoded as the bitstring ![01100001](./images/9a5b4e9f96a6354fa0981feff5058e6821213ced.png), and the character `b` is encoded as ![01100010](./images/6301b82e2e32d636a61271c29104495acb4772af.png). We can express a message that consists of several characters by concatenating the bitstrings that correspond to each character, like so:

![\textrm{``baba''} 	\quad	\Leftrightarrow 	\quad 01100010\; 01100001\; 01100010 \; 01100001.](./images/f1e1182e2a0147bdd869b6b8ef3a8f316c816a99.png)

For example, if the secret message ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) is the text `beer@18h`, we’ll represent it as a sequence of eight chunks of eight bits each, making for a bitstring of total length ![64](./images/042c14256d54cdb7d5baad03acd63fdd3c83da81.png):

![\vec{m} 
= 
\underbrace{01100010}_{\textrm{b}}\; 
\underbrace{01100101}_{\textrm{e}}\; 
\ldots \;  \ldots \;  \ldots \;  \ldots \; \ldots \; 
\underbrace{01101000}_{\textrm{h}}
\; \; \in \; \; \{0,1\}^{64}.](./images/a5c57805e949b32a215c12da32a4235df9acaa92.png)

Representing the text `beer@18h` as a ![64](./images/042c14256d54cdb7d5baad03acd63fdd3c83da81.png)\-dimensional binary vector allows us to manipulate it using linear algebra operations. This may sound like a little thing—a convenience at best—but it’s actually a big deal since it opens the door to many applications.

In this section we’ll describe how basic vector operations on bitstrings can be used for cryptography. In the next section, we’ll learn about _error-correcting codes_, which apply matrix operations on binary information vectors to protect them from noise.

###[The XOR operation](./Front matter.md)

The XOR operation, usually denoted ![\oplus](./images/6a61dca4d2971f0ac55df48a1ea4eefb5483aeb0.png), corresponds to addition in the finite field ![\mathbb{F}_2](./images/435aef1d0a822b1d260e1b6619312c55b17d8252.png):

![c = a \oplus b
\quad
\Leftrightarrow 
\quad
c = (a + b) \mod 2.](./images/e968c76c4702028c1941c03546ef187c09c16069.png)

[Table 7.1](./Chapter 7_ Applications.md) shows the results of the XOR operation on all possible combinations of inputs.

![\oplus](./images/6a61dca4d2971f0ac55df48a1ea4eefb5483aeb0.png)

0

1

0

0

1

1

1

0

Table 7.1: The XOR operation ![\oplus](./images/1c07f3cca070c6c28f16c4d597d0f448f68357cc.png) applied to all possible binary inputs.

The XOR operation acting on two bitstrings of the same length is the XOR operation applied to each of their elements:

![\vec{c} = \vec{a} \oplus \vec{b} 	
\quad
\Leftrightarrow 
\quad
c_i = (a_{i} + b_{i}) \mod 2.](./images/a9eeb44ed49973e175ac01a38bf0fb579a5dd20b.png)

The XOR operation isn’t anything new—it’s just the normal vector addition operation for vectors with components in the finite field ![\mathbb{F}_2](./images/435aef1d0a822b1d260e1b6619312c55b17d8252.png).

Intuitively, you can think of XOR as a “conditional toggle” operation. Computing the XOR of a bit ![a \in \mathbb{F}_2](./images/85d0c1b395ab9feb52306bd565bdc7421e74671d.png) with ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) leaves the bit unchanged, while computing the XOR with ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) toggles the bit, changing ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) to ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) or ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) to ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png). To illustrate this “toggle” effect, consider the bitstring ![\vec{v} = 0010](./images/58d8fce70b223f6bde554d5c0c53d87dd6e91eda.png) and the results of XOR-ing it with the all-zeros bitstring ![0000](./images/820ce1cc4d5ed2a007d213987c223039cde5ebf5.png), the all-ones bitstring ![1111](./images/78b95600ad7cacd8c3015a58656a6eed1330055c.png), and a random-looking bitstring ![0101](./images/7257a3856f838cf166265e79859dbc4fdf972822.png):

![0010 \oplus 0000            	=  0010,
\quad
0010 \oplus 1111             	=  1101,
\quad
0010 \oplus 0101            	=  0111.](./images/fc6776b2bde7caa9ecdd369acbc1b783e5372e22.png)

In the first case, none of the bits are flipped; in the second case all the bits are flipped; and in the third case only the second and fourth bits are flipped.

An important property of the XOR operation is that it is its own inverse: ![\vec{z} \oplus \vec{z} = \vec{0}](./images/f310167c933e7f7960929386be101a5ced40fc52.png), for all ![\vec{z}](./images/690dd011e497f9df247023ad063801b30627b1c7.png). In particular, if XOR-ing the bitstring ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png) with some bitstring ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png) produces ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png), then XOR-ing ![\vec{y}](./images/8acc0176bd9e975362bfa7c3d0431879596f54c0.png) with ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png) recovers the original vector ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png):

![\textrm{if  } \;   \vec{x} \oplus \vec{k} = \vec{y},
\quad
\textrm{ then  } \;  \vec{y} \oplus \vec{k}  = \vec{x}.](./images/354a9f2a0aae290c262e13b69e7ddbf113c75a4d.png)

This statement follows from the self-inverse property of the XOR operation and the associative law for vector addition:

![\begin{align*}
\vec{y} \oplus \vec{k}	
&=	(\vec{x} \oplus \vec{k}) \oplus \vec{k} 	\\
&=  	\vec{x} \, \oplus ( \vec{k} \oplus \vec{k} )	\\
&=	\vec{x} \, \oplus \, \vec{0} 				\\
&=	\vec{x}.
\end{align*}](./images/c60a749120b60976124f956a3c0a6373a8baf222.png)

The self-inverse property of the XOR operation is the basis for the one-time pad encryption and decryption operations.

###[One-time pad cryptosystem](./Front matter.md)

The one-time pad encryption scheme is based on computing the XOR of the message ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) and the secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png), which has the same length as the message. The security of the protocol depends crucially on how the secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png) is generated, and on how the key is used:

-   The key must be kept secret. Only Alice and Bob know ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png).
-   The key must be random: the value of each bit of the key ![k_i \in \vec{k}](./images/c21797a9a126a297c41bb721b0c7e6923fe9aedc.png) is random; ![k_i=1](./images/6ab0cf013dbe7a3101977ffbe8b81a952fa6cc0e.png) with probability 50%, and ![k_i=0](./images/aa2e954302aecb1247c7a74c45e5124c9d9c6819.png) with probability 50%.
-   Alice and Bob must _never reuse_ the secret key.

####[One-time pad encryption](./Front matter.md)

To obtain the ciphertext ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) for the message ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png), Alice computes the XOR of ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) and the secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png):

![\textrm{Enc}(\vec{m},\vec{k})
\,\eqdef\,
\vec{m} \oplus \vec{k}
=
\vec{c}.](./images/42c7bee95adb7d91d6c8b7e3c78c6ed975520e37.png)

####[One-time pad decryption](./Front matter.md)

Upon receiving the ciphertext ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png), Bob decrypts it by computing the XOR with the secret key:

![\textrm{Dec}(\vec{c},\vec{k})
\,\eqdef\,
\vec{c} \oplus \vec{k}
=
\vec{m}.](./images/3189acdb919b607c03058dfb3a83ae703b131d54.png)

From the self-inverse property of the XOR operation, we know XOR-ing any bitstring with the secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png) twice acts like the identity operation: ![\vec{m} \oplus \vec{k} \oplus \vec{k} = \vec{m}](./images/8923fd7836ac1b9137cc15f82af1fa939ea93e99.png).

####[Discussion](./Front matter.md)

Observe that using this encryption method to send an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-bit message requires ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) bits of secret key. Since bits of the secret key cannot be reused, we say that sending ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) bits securely “consumes” ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) bits of secret key. This notion of secret keys as a “consumable resource” is an important general theme in cryptography. Indeed, coming up with encryption and decryption functions is considered the easy part of cryptography, and the hard parts of cryptography are _key management_ and _key distribution_.

Consider a practical use of the one-time pad encryption scheme. Sending multiple messages ![m_1](./images/9747323f90595beb9839f458f53ccdd924d69803.png), ![m_2](./images/f05a6d25c78357311af1315bdb40ab4ab2c94bbb.png), ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png) requires multiple secret keys ![\vec{k}_1, \vec{k}_2](./images/898bdce37ea94fbef25a2a7156a023b54979a833.png), ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png) that Alice uses when she wants to communicate with Bob. Imagine a pad of paper; each page of the pad contains one secret key ![\vec{k}_i](./images/54ea71b30a93ed10a3353471e6065863f2d31867.png). Since keys cannot be reused, Alice must keep flipping through the pad, using the key from each page only once. This is where the name “one-time pad” comes from.

###[One-time pad security](./Front matter.md)

Security definitions in cryptography are based on different assumptions about the powers of the eavesdropper Eve. We need to formally define what _secure_ means, before we can evaluate the security of any cryptosystem. Modern cryptography is a subfield of mathematics, so we shouldn’t be surprised if the definition of security is stated in mathematical terms.

#####[Definition: Indistinguishability under chosen-plaintext attack (IND-CPA)](./Front matter.md)

A cryptosystem is considered secure in terms of indistinguishability if no eavesdropper can distinguish the ciphertexts of two messages ![\vec{m}_a](./images/79b2871f3b9ad242f2d50f503aeef44d4a80272e.png) and ![\vec{m}_b](./images/ea74012927e8a308478952d870309bf7075f664f.png) chosen by the eavesdropper, with a probability greater than guessing randomly.

This is one of the strongest security standards we can expect from a cryptosystem. It is also the simplest to understand. This definition of security can be understood as a game played between Alice and Eve. Suppose Eve can force Alice to send only one of two possible messages ![\vec{m}_a](./images/79b2871f3b9ad242f2d50f503aeef44d4a80272e.png) or ![\vec{m}_b](./images/ea74012927e8a308478952d870309bf7075f664f.png). Every time Eve sees a ciphertext ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png), she must guess whether Alice sent ![\vec{m}_a](./images/79b2871f3b9ad242f2d50f503aeef44d4a80272e.png) or ![\vec{m}_b](./images/ea74012927e8a308478952d870309bf7075f664f.png). We want to compare an Eve that has access to ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png), with a “control Eve” that only has access to a random string ![\vec{r}](./images/f922589ce2457f489bd34c34e47c1be9566640cd.png) that is completely uncorrelated with the message or the ciphertext. A cryptosystem is secure, according to the _indistinguishability under chosen-plaintext_ security definition, if the Eve with access to ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) is no better at distinguishing between messages ![\vec{m}_a](./images/79b2871f3b9ad242f2d50f503aeef44d4a80272e.png) and ![\vec{m}_b](./images/ea74012927e8a308478952d870309bf7075f664f.png) than she is at guessing randomly (which is the best that “control Eve” can do).

We won’t go into the formal details of the math, but we need to specify exactly what we mean by “with a probability greater than guessing randomly.” Control Eve has a completely random string ![\vec{r}](./images/f922589ce2457f489bd34c34e47c1be9566640cd.png), which contains no information about the message ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png), so control Eve must guess randomly and her probability of success is ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png). An Eve that can distinguish the ciphertext ![\vec{c}_a = \textrm{Enc}(\vec{m}_a)](./images/ce28acc163bcf25c8324e5abf107bfacdc48d53a.png) from the ciphertext ![\vec{c}_b = \textrm{Enc}(\vec{m}_b)](./images/9a9ed48bf9757bb85a612d1ee120bfe705ac38e9.png) with a probability significantly greater than ![\frac{1}{2}](./images/72c873ba6e56356329d322adfdd922f01517fe0d.png) is considered to have an advantage in distinguishing the ciphertext. Any such scheme is not considered secure in terms of IND-CPA. Intuitively, the IND-CPA definition of security captures the notion that Eve should learn no information about the message ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) after seeing its ciphertext ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png).

#####[Sketch of security proof](./Front matter.md)

The one-time pad encryption system is secure according to IND-CPA because of the assumption we make about the shared, secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png)—namely that it is generated randomly. Each bit ![k_i \in \vec{k}](./images/c21797a9a126a297c41bb721b0c7e6923fe9aedc.png) takes on the binary value ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) with probability 50%, and the value ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) with probability 50%.

Eve knows the plaintext of the two possible messages ![m_a](./images/fc83d7d417e6ff69c955408ca76e516771f186b5.png) and ![m_b](./images/35b1a3117a4224b532afd65cd3ec3ac95d8a5c8a.png), but she can’t tell which message was sent from the ciphertext ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) since she can’t distinguish between two equally likely alternative scenarios. In Scenario 1, Alice sent ![\vec{m}_a](./images/79b2871f3b9ad242f2d50f503aeef44d4a80272e.png), and the secret key is ![\vec{k}_a](./images/dfaa6b772d2a82205616112f2466dcd0492cba41.png), where ![\vec{c}=\vec{m}_a \oplus \vec{k}_a](./images/a1db75fb7a4178ba34a716dd87f1310122de6a09.png). In Scenario 2, Alice sent ![\vec{m}_b](./images/ea74012927e8a308478952d870309bf7075f664f.png), and the secret key is ![\vec{k}_b](./images/a8fd1dd6352c191f753a809276a9bf7b23dd121c.png), where ![\vec{c}=\vec{m}_b \oplus \vec{k}_b](./images/31d1169e1f3f62c4efd3903dccda7af156d21ead.png). The XOR operation combines the randomness of ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png) with the randomness in the secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png), so trying to distinguish whether ![\vec{m}_a](./images/79b2871f3b9ad242f2d50f503aeef44d4a80272e.png) or ![\vec{m}_b](./images/ea74012927e8a308478952d870309bf7075f664f.png) was sent is just as difficult as distinguishing ![\vec{k}_a](./images/dfaa6b772d2a82205616112f2466dcd0492cba41.png) and ![\vec{k}_b](./images/a8fd1dd6352c191f753a809276a9bf7b23dd121c.png). Since ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png) is completely random, Eve is forced to guess randomly. Thus the probability of determining the correct message is no better than guessing, which is precisely the requirement for the definition of security.

The randomness of the shared secret key is crucial to the security of the one-time pad encryption scheme. In general, we can think of _shared randomness_ (shared secret key) as a communication resource that allows for mathematically-secure private communication between two parties. But what if Alice and Bob don’t have access to shared randomness (that is, to some shared secret)? In the next section, we’ll introduce a different type of cryptosystem that doesn’t depend on a shared secret between Alice and Bob.

###[Public key cryptography](./Front matter.md)

Assume Alice and Bob are dissidents in two neighbouring countries who want to communicate with each other, but they can’t trust the network that connects them. If the dissidents cannot meet in person, obtaining a shared secret key to use for encryption will be difficult. They can’t send the secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png) over the network because the eavesdropper will see it, and thus be able to decrypt all subsequent encrypted communications between the dissidents. This is a major limitation of all cryptosystems in which the same secret is used to encrypt and decrypt.

Do not despair dear readers, the System hasn’t won yet: the dissidents can use _public-key_ cryptography techniques to share a secret key over the untrusted network, in plain view of all state and non-state sponsored eavesdroppers. The security of public-key cryptosystems comes from some clever math operations (which are performed in a finite field), and the computational difficulty of “reversing” these mathematical operations for very large numbers. For example, the security of the _Rivest–Shamir–Adleman_ (RSA) cryptosystem depends on the difficulty of factoring integers. It’s easy to compute the product of two integers ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png) and ![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png); but given only the product ![de](./images/54693ae4d78d139e51c7dd356b91933e547d0183.png), it is computationally difficult to find the factors ![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png) and ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png). For very large prime numbers ![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png) and ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png), even the letter agencies will have a difficult time finding the factors of ![de](./images/54693ae4d78d139e51c7dd356b91933e547d0183.png). This means ordinary citizens can use the power of math and cryptography to defend against corporate spying and the police state. Understanding cryptography will become increasingly important in the 21st century.

####[Definitions](./Front matter.md)

In a public-key cryptosystem, the secret key is actually a pair of keys, ![\vec{k} = \{ e_{\vec{k}}, d_{\vec{k}} \}](./images/f49b338435378c97bab8a9f04839810421cf77d6.png), where ![e_{\vec{k}}](./images/ab6c481c3ab5d3f11c5b52d3a6dd96c6c2c4f5da.png) is the public encryption key and ![d_{\vec{k}}](./images/aa875d3b25a1f33a5e90674bbe6637366a0d8c0b.png) is the private decryption key. The same encryption function, called ![\textrm{Enc}](./images/615b19846c388c8dae0d0c1594c0106d0009636d.png), is used for both encryption and decryption, but with different keys.

To use public-key cryptography, each communicating party must generate their own public-private key pairs. We’ll focus on Alice, and assume Bob performs analogous steps. Alice generates a public-private key pair ![\{ e_{\vec{k}}, d_{\vec{k}} \}](./images/ea01c9d3fb1d612275f8190fb9ac7578225b8a9e.png), and then shares the public part of the key with Bob. Note the public key can be shared openly, in plain sight, and it’s not a problem if Eve intercepts it—this is why it’s called a public key—everyone is allowed to know it.

####[Encryption](./Front matter.md)

Bob uses Alice’s public encryption key whenever he wants to send Alice a secret message. To encrypt message ![\vec{m}](./images/6859f0329835ce2e8653977eca3cd786a0415c54.png), Bob uses the function ![\textrm{Enc}](./images/615b19846c388c8dae0d0c1594c0106d0009636d.png) and Alice’s public encryption key ![e_{\vec{k}}](./images/ab6c481c3ab5d3f11c5b52d3a6dd96c6c2c4f5da.png) as follows:

![\vec{c} = \textrm{Enc}(\vec{m},e_{\vec{k}}).](./images/bba9d1e7356b596fc1c194e931818be43700d856.png)

When Alice receives the ciphertext ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png), she uses her private key ![d_{\vec{k}}](./images/aa875d3b25a1f33a5e90674bbe6637366a0d8c0b.png) (that only she knows) to decrypt the message:

![\vec{m} = \textrm{Dec}(\vec{c},d_{\vec{k}}).](./images/dce085a0aad5769ef62bcbd270ba0c6b909e771f.png)

Observe that public-key cryptosystems are inherently many-to-one: anyone who knows Alice’s public key ![e_{\vec{k}}](./images/ab6c481c3ab5d3f11c5b52d3a6dd96c6c2c4f5da.png) can create encrypted messages that only she can decode.

####[Digital signatures](./Front matter.md)

Alice can also use her public-private key pair to broadcast one-to-many _authenticated_ statements ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png), meaning receivers can be sure the statements they receive were sent by Alice. The math is the same; we just use the keys in the opposite order. Alice encrypts the statement ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png) to produce a ciphertext,

![\vec{c} = \textrm{Enc}(\vec{s},d_{\vec{k}}),](./images/638a5e524502b7faabd6d69cc2e406ab869cc0d2.png)

then publishes the encrypted post ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) to her blog or a public forum. Everyone who knows Alice’s public key ![e_{\vec{k}}](./images/ab6c481c3ab5d3f11c5b52d3a6dd96c6c2c4f5da.png) can decrypt the post ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) to obtain the statement ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png):

![\vec{s} = \textrm{Dec}( \vec{c} , e_{\vec{k}}).](./images/8fbcf78b676f10462a08c71e50496b485f7680bc.png)

The interesting property here is that we can be sure the statement ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png) was sent by Alice, since only she controls the private key ![d_{\vec{k}}](./images/aa875d3b25a1f33a5e90674bbe6637366a0d8c0b.png). This digital signature scheme makes it difficult for any third parties to impersonate Alice, since they don’t know Alice’s private key ![d_{\vec{k}}](./images/aa875d3b25a1f33a5e90674bbe6637366a0d8c0b.png). This is the principle behind _digital signatures_ used in the delivery of software updates.

We don’t have space in this section to delve deeper into public-key cryptography, but we’ll illustrate the main ideas through an example.

####[Example: ssh keys for remote logins](./Front matter.md)

The secure shell protocol allows users to login to remote hosts. To login as `user` on the server `remotehost.com`, run the command `ssh user@remotehost.com` on the command prompt. The remote host will usually ask you for a password before it lets you login.

Passwords are the weakest form of authentication. Given enough effort, it’s always possible for an attacker to guess your password. Furthermore, people tend to use the same password for multiple accounts, meaning that if one account is compromised then all accounts will be compromised. In this section, we’ll describe a more secure approach for `ssh` logins based on public key authentication.

Setting up key-based authentication for `ssh` requires that steps are performed on your machine and on the remote server. Commands prefixed with `laptop>` should be typed on your local machine, while commands that start with `remotehost>` are to be executed on the remote server. Note these commands assume a UNIX environment. If you’re using a Windows machine, I recommend you install[`cygwin`](./www.cygwin.com.md) to obtain the same functionality.

The first step is to generate an `ssh` private-public key pair in the subdirectory called `.ssh` inside your home directory:

laptop> cd ~                           # go to you home dir ~
laptop> mkdir .ssh                     # create a .ssh subdir
laptop> ssh-keygen -t rsa -b 4096      # generate an RSA key pair

Accept the defaults for the questions you’re asked, and be sure to set a password to protect your `ssh` private key. A new public key pair will be created in the directory `~/.ssh/`. The private key is contained in the file `~/.ssh/id_rsa`, and the corresponding public key is in the file `~/.ssh/id_rsa.pub`. You can confirm that these files exist by running the command `ls .ssh`. Additionally, you can ensure that these files have restrictive access permissions by issuing the command,

laptop> chmod -R go-rwx .ssh 

This command has the effect of recursively (`-R`) changing permissions for users in the same group (`g`) as you and other (`o`) users, by removing (`-`), read (`r`), write (`w`), and execute (`x`) permissions. Basically, nobody other than you should be allowed to touch these files.

Another useful command to know involves adding the private key to a “key chain,” which is a temporary store of credentials tied to your current login session on your laptop:

laptop> ssh-add -K ~/.ssh/id\_rsa    # add priv. key to keychain 

This command will prompt you to enter the password you used when generating the `ssh` key pair. Now that the private key is on your keychain, you won’t be prompted for a password for a little while.

Next, copy the public key `~/.ssh/id_rsa.pub` from your laptop to the remote server. You can do this via the command `scp` as follows:

laptop> scp id\_rsa.pub user@remotehost:~/key\_from\_laptop.pub 

You’ll need to substitute `user` and `remotehost` with the actual username and hostname (or IP address) of the remote server for which you want to set up the ssh-key login.

The final step is to place the public key information in a special file called `~/.ssh/authorized_keys`, located on the remote host. You can do this using the following commands:

laptop> ssh user@remotehost
remotehost> cd ~
remotehost> mkdir .ssh
remotehost> cat key\_from\_laptop.pub >> .ssh/authorized\_keys 
remotehost> chmod -R go-rwx .ssh 

Inspect the resulting file and you’ll see it contains a copy of the public key from your laptop. Now, if you log out of the remote host and try reconnecting to it using `ssh user@remotehost.com`, you’ll be logged in automatically without needing to enter a password.

Once you’ve set up your login using `ssh` keys for your server, it’s a good idea to completely disable password logins. In general, this is the best approach for ensuring security, and many hosting services only support logins using `ssh` keys.

###[Discussion](./Front matter.md)

We’ll conclude with some basic advice for programmers who want to use cryptography in their software. Rather than trying to roll your own crypto functions, keep in mind it’s best to use established libraries. Libraries are good for you—there are many ways cryptosystems can fail, and experts have thought about defending against many potential attacks. Don’t be a cowboy programmer—use the libraries.

###[Links](./Front matter.md)

\[ Signal is a secure messaging app for mobile \][`https://whispersystems.org/`](./whispersystems.org.md)

\[ Public-key cryptography general concepts \][`https://en.wikipedia.org/wiki/Public-key_cryptography`](./Public-key_cryptography.md)

###[Exercises](./Front matter.md)

E7.14 Alice wants to send the message ![\vec{m} = 0110\;1000\;0110\;1001](./images/e2e3b29c3114e0570c352e565ebe95cbb92565ad.png) to Bob. They have pre-shared the secret key ![\vec{k}=1010\;0111\;0010\;0111](./images/c3d9b6ec35a659c8b9bf5bcc585bee1ca69421fd.png). Compute the ciphertext ![\vec{c} = \textrm{Enc}(\vec{m},\vec{k}) =\vec{m} \oplus \vec{k}](./images/fd14eef66d7faae826e1748df4cd0df3ccecd3e3.png) that Alice will send to Bob. Verify that Bob will obtain the correct message after decrypting.

##[7.10 Error-correcting codes](./Chapter 7_ Applications.md)

The raw information-carrying capacity of a DVD is roughly 5.64GB; which is about 20% more than the 4.7GB of data that your computer will let you write to it. Why this overhead? Are DVD manufacturers trying to cheat you? Actually, they’re looking out for you; the extra space is required for the _error-correcting code_ that is applied to your data before writing it to the disk. Without the error-correcting code, even the tiniest scratch on the surface of the disk would make the disk unreadable, destroying your precious data. In this section, we’ll learn how error-correcting codes work.

Error-correcting codes play an essential part in the storage, the transmission, and the processing of digital information. Even the slightest change to a computer program will make it crash—computer programs simply don’t like it when you fiddle with their bits. Crashing was the norm back in the 1940s as illustrated by this quote:

> “Two weekends in a row I came in and found that all my stuff had been dumped and nothing was done. I was really annoyed because I wanted those answers and two weekends had been lost. And so I said, Dammit, **if the machine can detect an error, why can’t it locate the position of the error and correct it?**”
> 
> — Richard Hamming

Richard Hamming was a researcher at Bell in the 1940s. He ran into the problem of digital data corruption, and decided to do something to fix it. As a solution, he figured out a clever way to encode ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png) bits of information into ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) bits of storage, such that it’s possible to recover the information even if some errors occurred on the storage medium. An _error-correcting code_ is a mathematical strategy for defending against erasures and errors. Hamming’s invention of error-correcting codes became a prerequisite for the modern age of computing—after all, reliable computation is much more useful than unreliable computation.

###[Definitions](./Front matter.md)

An _error-correcting code_ is a prescription for encoding _binary_ information. Recall that bits are elements of the binary field, ![\mathbb{F}_2 = \{0,1\}](./images/11de25d76e6a10da48d513fbf1f4f71840562df2.png). A bitstring of length ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) is an ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional vector of bits ![\vec{v} \in \{0,1\}^n](./images/4f9d36a7781014dea25d4fc659be24e944585a34.png). For example, ![0010](./images/fac31ffb1217d907919b28a1d19fd592346f8feb.png) is a bitstring of length ![4](./images/d642a42f2cf4e1514233d611b91e5d4646202fc8.png).

We use several parameters to characterize error-correcting codes:

-   ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png): the size, or length, of the messages for the code.
-   ![\vec{x}_i \in \{0,1\}^k](./images/100d1c2b261904623848689b9d46777c03e48623.png): a _message_. Any bitstring of length ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png) is a valid message.
-   ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png): the size of the codewords in the code.
-   ![\vec{c}_i \in \{0,1\}^n](./images/a1ace299b770e921423a73216fca67dc460b7beb.png): the _codeword_ that corresponds to message ![\vec{x}_i](./images/bc3acdc5b7336eb352b49cea75260879bfc271e1.png).
-   A _code_ consists of ![2^k](./images/9b7ae832d168a38950a140a1260e665d2bca5eba.png) codewords ![\{\vec{c}_1,\vec{c}_2,\ldots\}](./images/1bbd9fcc454008a8f0df5d1df6c9600a04e8fb42.png), one for each of the possible messages ![\{\vec{x}_1,\vec{x}_2,\ldots\}](./images/080b7f4d185c4c47b842a0392107a123b0b4528d.png).
-   ![d(\vec{c}_i,\vec{c}_j)](./images/6d21bb832bf7e5f9b9302aa7cacc9810505a1115.png): the _Hamming distance_ between codewords ![\vec{c}_i](./images/4c9fb9ff782ce7f9e89a437f0b72e6f41bb2595b.png) and ![\vec{c}_j](./images/b14ff89f92a1115fcf1f8e72ab6fa7156f5478c0.png).
-   An ![(n,k,d)](./images/621db18662a6e5972f342f045a6ae4888a7cce5d.png) code is a procedure for encoding messages into codewords; ![\textrm{Enc}: \{0,1\}^k \to \{0,1\}^n](./images/0f57aa81f052141026e14bcd5ca3120b79cb9381.png), which guarantees the _minimum distance_ between any two codewords is at least ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png).

The _Hamming distance_ between two bitstrings ![\vec{x}, \vec{y} \in \{0,1\}^n](./images/e3f03a40d6e26aaf6f87ee54d1d65fd352ccad92.png) counts the number of bits where the two bitstrings differ:

![d(\vec{x}, \vec{y}) \,\eqdef\, \sum_{i=1}^n \delta(x_i,y_i),
\quad \textrm{where }
\delta(x_i,y_i) = \left\{ 
\begin{array}{ll}
0 & \textrm{if } x_i = y_i, \\
1 & \textrm{if } x_i \neq y_i.
\end{array} \right.](./images/cf74f65fc681a7b887f2ee0e6db95140abd6a84f.png)

Intuitively, the Hamming distance between two bitstrings measures the minimum number of substitutions required to transform one bitstring into the other. For example, the Hamming distance between codewords ![\vec{c}_1=0010](./images/9e42473e5dba8f1d4feee3b3cba6763832212e43.png) and ![\vec{c}_2=0101](./images/56480fe62abafa3d4b8d5ca5d15222fbc29d8775.png) is ![d(\vec{c}_1, \vec{c}_2)=3](./images/47fdb1fcd915eeebba7d122483eb72349e9f00b3.png), because it takes three substitutions (also called _bit flips_) to convert ![\vec{c}_1](./images/56ee1cc6f0f1764f4ab0809107eb219c79f33c8d.png) to ![\vec{c}_2](./images/c0783c48eca35a66209759ad8f7156607b8c16a7.png) or vice versa.

An ![(n,k,d)](./images/621db18662a6e5972f342f045a6ae4888a7cce5d.png) code is defined by a function ![\textrm{Enc}: \{0,1\}^k \to \{0,1\}^n](./images/0f57aa81f052141026e14bcd5ca3120b79cb9381.png) that encodes messages ![\vec{x}_i \in \{0,1\}^k](./images/100d1c2b261904623848689b9d46777c03e48623.png) into codewords ![\vec{c}_i \in \{0,1\}^n](./images/a1ace299b770e921423a73216fca67dc460b7beb.png). Usually the encoding procedure ![\textrm{Enc}](./images/615b19846c388c8dae0d0c1594c0106d0009636d.png) is paired with a decoding procedure, ![\textrm{Dec}: \{0,1\}^n \to \{0,1\}^k](./images/a8ed4c8dca12a74cbf54140b733829f78e8c8e47.png), which recovers messages from (possibly corrupted) codewords.

![channel-coding](./images/channel-coding.png)

Figure 7.14: An error-correcting scheme using the encoding function ![\textrm{Enc}](./images/8fbc619efdd8bb12fdefcbe7565c108ecfadfaef.png) and the decoding function ![\textrm{Dec}](./images/2c62f57770051e14f7e7fafd9bba8d6f333cbaa4.png) to protect against the effect of noise (denoted ![\lightning](./images/e38d4003a8d2c77762833334ab0cdd3568a78491.png)). Each message ![\vec{x}](./images/d253d396ee7731d3b565bf2ff5bf610db05cf3eb.png) is encoded into a codeword ![\vec{c}](./images/b033bf19166a94278ffc5fd6b507b42bc30b1317.png). The codeword ![\vec{c}](./images/b033bf19166a94278ffc5fd6b507b42bc30b1317.png) is transmitted through a _noisy channel_ that can corrupt the codeword by transforming it into another bitstring ![\vec{c}^{\,\prime}](./images/d5ea17edf91486a703ce79df2f3ac15abf38fa09.png). The decoding function ![\textrm{Dec}](./images/2c62f57770051e14f7e7fafd9bba8d6f333cbaa4.png) looks for a valid codeword ![\vec{c}](./images/b033bf19166a94278ffc5fd6b507b42bc30b1317.png) that is close in Hamming distance to ![\vec{c}^{\,\prime}](./images/d5ea17edf91486a703ce79df2f3ac15abf38fa09.png). If the protocol is successful, the decoded message will match the transmitted message ![\vec{x}^{\,\prime} = \vec{x}](./images/9303306d62d17d3ffde03fd0cd638d25695fbdd1.png), despite the noise (![\lightning](./images/e38d4003a8d2c77762833334ab0cdd3568a78491.png)).

###[Linear codes](./Front matter.md)

A code is _linear_ if its encoding function ![\textrm{Enc}](./images/615b19846c388c8dae0d0c1594c0106d0009636d.png) is a linear transformation:

![\textrm{Enc}(\vec{x}_i + \vec{x}_j) = \textrm{Enc}(\vec{x}_i) + \textrm{Enc}(\vec{x}_j),	\textrm{ for all messages } \vec{x}_i, \vec{x}_j.](./images/191d8f807e00a1d08aa832fcd6d3b2ed134735b1.png)

An ![(n,k,d)](./images/621db18662a6e5972f342f045a6ae4888a7cce5d.png) linear code encodes ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png)\-bit messages into ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-bit codewords with minimum inter-codeword distance ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png). Linear codes are interesting because their encoding function ![\textrm{Enc}](./images/615b19846c388c8dae0d0c1594c0106d0009636d.png) can be implemented as a matrix multiplication. We use the following terms when defining linear codes as matrices:

-   ![G \in \mathbb{F}_2^{k \times n}](./images/e0eafe2eb86917c96ce188ffe287917e53057c33.png): the _generating matrix_ of the code. Each codeword ![\vec{c}_i](./images/4c9fb9ff782ce7f9e89a437f0b72e6f41bb2595b.png) is produced by multiplying the message ![\vec{x}_i](./images/bc3acdc5b7336eb352b49cea75260879bfc271e1.png) by ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) from the right:
    
    ![\textrm{Enc}(\vec{x}_i) = \vec{c}_i = \vec{x}_i G.](./images/c59a1790e1e0952db5f3c0c342f87f7252b05f44.png)
    
-   ![\mathcal{R}(G)](./images/81c4d6fe69b118a415e82573b48337d399648a4d.png): the row space of the generator matrix is called the _code space_. We say a codeword ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) is valid if ![\vec{c}\in\mathcal{R}(G)](./images/07b4fb5fb4571b183566b6515e97188c03bd0b32.png), which means there exists some message ![\vec{x} \in \{0,1\}^k](./images/505311f13abdbe117b61e99df4eb75abf100cd89.png) such that ![\vec{x}G = \vec{c}](./images/a31b33f48f33241c4fb385bd1a03621d0b89e30c.png).
-   ![H \in \mathbb{F}_2^{(n-k) \times n}](./images/2a6e327a5742014c4066faa76620876703168c4a.png): the _parity check matrix_ of the code. The _syndrome_ vector ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png) of any bitstring ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png) is obtained by multiplying ![\vec{c}^{\,\prime \sfT}](./images/88261cc9591a3c87724f19996d406a3c265e527a.png) by ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) from the left:
    
    ![\vec{s} = H\vec{c}^{\,\prime \sfT}.](./images/f4ca7ef9c7ffdb90ecc250a896ce0a416e9fbd0a.png)
    
    If ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png) is a valid codeword (no error occurred), then ![\vec{s} = \vec{0}](./images/190e63b2dd4dfd874a5bdd3bcd5507a4c5797667.png). If ![\vec{s}\neq \vec{0}](./images/11c555d78f529a0f28e2c41c3a975862ef30e66a.png), we know an error has occurred. The syndrome information helps us correct the error.
    

We can understand linear codes in terms of the input and output spaces of the encoding function ![\textrm{Enc}(\vec{x}) = \vec{x}G](./images/d5bb1cd8ff6e268740389212b9a8c7d03d2d1764.png). Left multiplication of ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) by a ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png)\-dimensional row vector produces a linear combination of the rows of ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png). Thus, the set of all possible codewords (called the _code space_) corresponds to the row space of ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png).

Every vector in the null space of ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) is orthogonal to every codeword ![\vec{c}_i](./images/4c9fb9ff782ce7f9e89a437f0b72e6f41bb2595b.png). We can construct a parity-check matrix ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) by choosing any basis for the null space for ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png). We call ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) the orthogonal complement of ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png), which means ![\mathcal{N}(G) = \mathcal{R}(H)](./images/d7bb011dd9b8c4e63b1a3d7025904391f7f47289.png). Alternately, we can say the space of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional bitstrings decomposes into orthogonal subspaces of valid and invalid codewords: ![\mathbb{F}_2^n = \mathcal{R}(G) \oplus \mathcal{R}(H)](./images/a199b843d2c1826220fed8a84060d05e5f080848.png). We know ![H\vec{c}^\sfT=\vec{0}](./images/4533217359659570d11f97df5ebf00a054c68e7f.png) for all valid codewords ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png). Furthermore, the _syndrome_ obtained by multiplying an invalid codeword ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png) with the parity check matrix ![\vec{s} = H\vec{c}^{\,\prime \sfT}](./images/527e891f29c0d72748bae4e2014a3dced76c041e.png) can help us characterize the error that occurred, and correct it.

###[Coding theory](./Front matter.md)

The general idea behind error-correcting codes is to choose the ![2^k](./images/9b7ae832d168a38950a140a1260e665d2bca5eba.png) codewords so they are placed far apart from each other in the space ![\{0,1\}^n](./images/d028adfa8cff67630fc52694a7c2c59893f8f999.png). If a code has minimum distance ![d\geq 2](./images/f3d2f245b7f23fcf281b83e48cdefd6352b9f060.png) between codewords, then this code is robust to one-bit errors. To understand why, imagine a bubble of radius one (in Hamming distance) around each codeword. When a one-bit error occurs, a codeword will be displaced from its position, but it will remain within the bubble of radius one. In other words, if a one-bit error occurs, we can still find the correct codeword by looking for the closest valid codeword. See[Figure 7.15](./Chapter 7_ Applications.md) for an illustration of a set of codewords that are ![d>2](./images/90dd1eee5ed0e9e80b555293f11f36a56cf6fca9.png) distance apart. Any bitstring that falls within one of the bubbles will be decoded as the codeword at the centre of the bubble. We cannot guarantee this decoding procedure will succeed if more than one errors occur.

![error_correcting_code_bubbles_flat](./images/error_correcting_code_bubbles_flat.png)

Figure 7.15: The rectangular region represents the space of binary strings of length ![n](./images/e847edf1efb9fe4ea5c92430259b6e6f92de2be9.png). Each codeword ![c_i](./images/0d0d399e832decc7a59bb0833bb72ad2b3fa8b15.png) is denoted with a black dot. A “bubble” of Hamming distance one around each codeword is shown. Observe that the distance between any two codewords is greater than two (![d>2](./images/092fee9b67e66c6f0d42765fbd24e0e29477c5ba.png)). By Observation 1, we know this code can correct any one-bit error (![\lfloor \frac{d}{2} \rfloor \geq 1](./images/fd5615a86e9780f4f25de131ba28e75ed63b6077.png)).

#####[Observation 1](./Front matter.md)

An ![(n,k,d)](./images/621db18662a6e5972f342f045a6ae4888a7cce5d.png)\-code can correct up to ![\lfloor{\frac{d}{2}\rfloor}](./images/efb92b17ff555410ccecb1dcdfba4fbf3c34fb95.png) errors.

The notation ![\lfloor x\rfloor](./images/4c23b8badaf845cf0b150ccd27ace4644a11bb59.png) describes the _floor_ function, which computes the closest integer value smaller than ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). For example, ![\lfloor 2 \rfloor = 2](./images/c6c76b652e9c98b8ad783cf20e951e1c22fa8b53.png) and ![\lfloor \frac{3}{2}\rfloor = \lfloor 1.5\rfloor = 1](./images/8f8b32235b75c5f1c257a1b2d7c45c016448c86e.png). We can visualize Observation 1 using[Figure 7.15](./Chapter 7_ Applications.md) by imagining the radius of each bubble is ![\lfloor{\frac{d}{2}\rfloor}](./images/efb92b17ff555410ccecb1dcdfba4fbf3c34fb95.png) instead of ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png).

###[Repetition code](./Front matter.md)

The simplest possible error-correcting code is the _repetition code_, which protects information by recoding multiple copies of each message bit. For instance, we can construct a ![(3,1,3)](./images/d65c7dad7e3bb13b6d7fa56c22786f4aa88fc380.png) code by repeating each message bit three times. The encoding procedure ![\textrm{Enc}](./images/615b19846c388c8dae0d0c1594c0106d0009636d.png) is defined as follows:

![\textrm{Enc}(0) = 000 = \vec{c}_0,		\qquad  \textrm{Enc}(1) = 111 = \vec{c}_1.](./images/bf276d847e438941addc465d1d75ba91276f0e73.png)

Three bit flips are required to change the codeword ![\vec{c}_0](./images/0682cd8cd3d2198cc0daf34b41c02c0fc2aaf184.png) into the codeword ![\vec{c}_1](./images/56ee1cc6f0f1764f4ab0809107eb219c79f33c8d.png), and vice versa. The Hamming distance between the codewords of this repetition code is ![d=3](./images/8292ebebf77eaab13ddc140e111c85c08c61b5c1.png).

Encoding a string of messages ![x_1x_2x_3 = 010](./images/9202563d6fe593cdac90a030c3fc7cafd4dbec09.png) results in a string of codewords ![000111000](./images/d7bc7f0a161c438352b9de8fc18b065703979bc2.png). We can apply the “majority vote” decoding strategy using the following decoding function ![\textrm{Dec}](./images/e15402f8ff22a1d9030d544af152acc1f25543a1.png), defined by

![\begin{align*}
& \textrm{Dec}(000) = 0, \; \textrm{Dec}(100) = 0, \; \textrm{Dec}(010) = 0, \; \textrm{Dec}(001) = 0, \\
& \textrm{Dec}(111) = 1, \; \textrm{Dec}(011) = 1, \; \textrm{Dec}(101) = 1, \; \textrm{Dec}(110) = 1.
\end{align*}](./images/ea525c7bb9b5104ed7470a2def9695d878e0042a.png)

Observe that any one-bit error is corrected. For example, the message ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png) is encoded as the codeword ![\vec{c}=000](./images/2052d1816676cd3e2d918c4e882ad35fc7a98fa8.png). If an error occurs on the first bit during transmission, the received codeword will be ![\vec{c}^{\,\prime} = 100](./images/2325a743b1c88cbc60a5a8d8d3ae6d5df1467c5d.png), and majority-vote decoding will correctly output ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png). Since ![d>2](./images/90dd1eee5ed0e9e80b555293f11f36a56cf6fca9.png) for this repetition code, the code can correct all one-bit errors.

###[The Hamming code](./Front matter.md)

The ![(7,4,3)](./images/7fa3141228a852a5b6fc51ea8c96dae312e91b05.png) _Hamming code_ is a linear code that encodes four-bit messages into seven-bit codewords with minimum Hamming distance of ![d=3](./images/8292ebebf77eaab13ddc140e111c85c08c61b5c1.png) between any two codewords. The generator matrix for the Hamming code is

![G \,
= 
\begin{bmatrix}
1 & 0 & 0 & 1 & 0 & 1 & 1\\
0 & 1 & 0 & 1 & 0 & 1 & 0\\
0 & 0 & 1 & 1 & 0 & 0 & 1\\
0 & 0 & 0 & 0 & 1 & 1 & 1
\end{bmatrix}\!\!.					\label{eqn:hamming_code_generator_matrix}](./images/c0416f69698f47669625c71434f82946a600d7f6.png)

Note that other possibilities for the matrix ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) exist. Any permutation of the columns and rows of the matrix will be a generator matrix for a ![(7,4,3)](./images/7fa3141228a852a5b6fc51ea8c96dae312e91b05.png) Hamming code. We have chosen this particular ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) because of the useful structure in its parity-check matrix ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png), which we’ll discuss shortly.

####[Encoding](./Front matter.md)

We’ll now look at how the generating matrix is used to encode four-bit messages into seven-bit codewords. Recall that all arithmetic operations are performed in the finite field ![\mathbb{F}_2](./images/435aef1d0a822b1d260e1b6619312c55b17d8252.png). The message ![(0,0,0,1)](./images/fa51da5a0a6c30f1a42fd16e02f2c6e4339b61b4.png) is encoded as the codeword

![(0,0,0,1)G = (0,0,0,0,1,1,1),](./images/00cde87bc05561df2fb7d058df4456705a04d79f.png)

similarly ![(0,0,1,0)](./images/8e7d94266cb7639f95962fd129cc2393e88cbc75.png) is encoded into ![(0,0,1,0)G = (0,0,1,1,0,0,1)](./images/529b7e41e8afc53ee617b114b9e5bb645d774902.png). Now consider the message ![(0,0,1,1)](./images/137ab5cfc77de55e5b3822854de6ff5304d5900e.png), which is a linear combination of the messages ![(0,0,1,0)](./images/8e7d94266cb7639f95962fd129cc2393e88cbc75.png) and ![(0,0,0,1)](./images/fa51da5a0a6c30f1a42fd16e02f2c6e4339b61b4.png). To obtain the codeword for this message, we can multiply it with ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) as usual to find ![(0,0,1,1)G = (0,0,1,1,1,1,0)](./images/9a5a32deccfde27c085a69439f007905191f7b84.png). Another approach is to use the linearity of the code and add the codewords for the messages ![(0,0,1,0)](./images/8e7d94266cb7639f95962fd129cc2393e88cbc75.png) and ![(0,0,0,1)](./images/fa51da5a0a6c30f1a42fd16e02f2c6e4339b61b4.png): ![(0,0,1,1,0,0,1) + (0,0,0,0,1,1,1) = (0,0,1,1,1,1,0)](./images/2665bc7a568ce4f5267191bf17464b90b211b396.png).

####[Decoding with error correction](./Front matter.md)

The minimum distance for this Hamming code is ![d=3](./images/8292ebebf77eaab13ddc140e111c85c08c61b5c1.png), which means it can correct one-bit errors. In this section, we’ll look at some examples of bit-flip errors that can occur, and discuss the decoding procedure we can follow to extract messages—even from a corrupted codeword ![\vec{c}^\prime](./images/c2425becb570ba960024ff52c8a782571cf36d94.png).

The _parity-check matrix_ for the ![(7,4,3)](./images/7fa3141228a852a5b6fc51ea8c96dae312e91b05.png) Hamming code is

![H 
= 
\begin{bmatrix}
1 & 1 & 1 & 1 & 0 & 0 & 0\\
1 & 1 & 0 & 0 & 1 & 1 & 0\\
1 & 0 & 1 & 0 & 1 & 0 & 1 
\end{bmatrix}\!\!.](./images/91b2016953d1988f6587efb1d85cdab80bcda5b1.png)

This matrix is the orthogonal complement of the generating matrix ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png). Every valid codeword ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) is in the row space of ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png), since ![\vec{c} = \vec{x}G](./images/2a50356424275c08362713d5b5aa0461f04bde7f.png) for some message ![\vec{x}](./images/9fb3be08798d4143b1df06c9c828ea04131574c7.png). Since the rows of ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) are orthogonal to ![\mathcal{R}(G)](./images/81c4d6fe69b118a415e82573b48337d399648a4d.png), the product of ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) with any valid codeword will be zero: ![H\vec{c}^\sfT=0](./images/51ba65ec686a29deb9c88995d607737ace607daa.png).

On the other hand, if the codeword ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png) contains an error, then multiplying it with ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) will produce a nonzero _syndrome_ vector ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png):

![H\vec{c}^{\,\prime \sfT} = \vec{s} \neq 0.](./images/a4bd438500435776758e1495c620ee6c3c44d7fe.png)

The decoding procedure ![\textrm{Dec}](./images/e15402f8ff22a1d9030d544af152acc1f25543a1.png) uses the information in the syndrome vector ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png) to correct the error. In general, the decoding function can be a complex procedure that involves ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png) and ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png). In the case of the Hamming code, the decoding procedure is very simple because the syndrome vector ![\vec{s} \in \{0,1\}^3](./images/23eceb7c95400e987e96e66683f954cb4087d92c.png) contains the binary representation of the location where the bit-flip error occurred. Let’s look at an example to illustrate how error correction works.

#####[Example](./Front matter.md)

Suppose we send the message ![\vec{x} = (0,0,1,1)](./images/d3054f074b04b8a878af8e14d6fd551a293590b8.png) encoded as the codeword ![\vec{c} = (0,0,1,1,1,1,0)](./images/187e828c6b0ea7d466fea5f23489b366f300656b.png). If an error on the last bit occurs in transit, the received codeword will be ![\vec{c}^{\,\prime} = (0,0,1,1,1,1,1)](./images/56d3d1cdc64c8589978186f964e954a7977ecb72.png). Computing the syndrome for ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png), we obtain

![\vec{s}
=
H\vec{c}^{\,\prime \sfT} 
= 
\begin{bmatrix}
1 & 1 & 1 & 1 & 0 & 0 & 0\\
1 & 1 & 0 & 0 & 1 & 1 & 0\\
1 & 0 & 1 & 0 & 1 & 0 & 1 
\end{bmatrix}
\!\!
\begin{bmatrix}
0 \\ 0 \\ 1 \\ 1 \\ 1 \\ 1 \\ 1
\end{bmatrix}
=					
\begin{bmatrix}
0 \\ 0 \\ 1
\end{bmatrix}\!\!.](./images/cb54bfbe978c846d4b81597e8f5ae86b90397f82.png)

The syndrome vector ![\vec{s} = (0,0,1)](./images/1eb7a2abde6bff268a41d5891e88b2d76bc4c142.png) corresponds to the binary string ![001](./images/233dbff6fc49177e05de1ea8d8ccbf03248e0949.png), which is the number one. Note we count bits from right to left when interpreting the syndrome of an error: bit one is the rightmost bit of the codeword, bit two is the second to last, and so on. This syndrome ![001](./images/233dbff6fc49177e05de1ea8d8ccbf03248e0949.png) tells us the location of the error is on bit one of the codeword, which is the rightmost bit. After correcting the error by flipping the rightmost bit, we obtain the correct codeword ![\vec{c} = (0,0,1,1,1,1,0)](./images/187e828c6b0ea7d466fea5f23489b366f300656b.png), which decodes to the message ![\vec{x} = (0,0,1,1)](./images/d3054f074b04b8a878af8e14d6fd551a293590b8.png) that was sent.

Let’s check the error-correcting ability of the Hamming code with another single-bit error. If a bit-flip error occurs on bit four (counting from the right), the received codeword will be ![\vec{c}^{\,\prime\prime} = (0,0,1,0,1,1,0)](./images/77dd88b28e436763e1bb27cb1ac3f6513c40367e.png). The syndrome for ![\vec{c}^{\,\prime\prime}](./images/894c152cd4e52162130adccce17ce424fac22c91.png) is ![H\vec{c}^{\,\prime\prime \sfT}  = (1,0,0)](./images/8744aa721b7fb60f27329bf66fac3d6778efaedd.png), which corresponds to the number four when interpreted in binary. Again, we’re able to obtain the position where the error has occurred from the syndrome.

The fact that the syndrome tells us where the error has occurred is not a coincidence, but a consequence of deliberate construction of the matrices ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) and ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) of the Hamming code. Let’s analyze the possible received codewords ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png), when the transmitted codeword is ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png):

![\vec{c}^{\prime} = 
\left\{ \begin{array}{ll} 
\vec{c} 			& \textrm{if no error occurs}						\\
\vec{c} + \vec{e}_i	& \textrm{if bit-flip error occurs in position } i,
\end{array} \right.](./images/caf08bea8095fcc957ecdcfe7b464d6b5569ebc5.png)

where ![\vec{e}_i](./images/8e3efa1e871aeea4f937dc13aa99a36dbde1386c.png) is a vector that contains a single one in position ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png). Indeed a bit flip in the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th position is the same as adding one in that position, since we’re working in the finite field ![\mathbb{F}_2](./images/435aef1d0a822b1d260e1b6619312c55b17d8252.png).

In the case when no error occurs, the syndrome will be zero ![H\vec{c} = \vec{0}](./images/0cc0f7bf201d1792758cfd04636a0ad3b38353fd.png), because ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) is defined as the orthogonal complement of the code space (the row space of ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png)). In the case when a single error occurs, the syndrome calculation only depends on the error:

![\vec{s}
=
H\vec{c}^{\prime \sfT}
=
H(\vec{c} + \vec{e}_i)^\sfT
=
\cancel{H\vec{c}} + H\vec{e}_i
=
H\vec{e}_i.](./images/4978708fb30decfcc466aa78c50214b19bc48176.png)

If you look carefully at the structure in the parity-check matrix ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png), you’ll see its columns contain the binary encoding of the numbers between seven and one. With this clever construction of the matrix ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png), we’re able to obtain a syndrome that tells us the binary representation of where an error has occurred.

####[Discussion](./Front matter.md)

Throughout this section, we referred to “the” ![(7,4,3)](./images/7fa3141228a852a5b6fc51ea8c96dae312e91b05.png) _Hamming code_, but in fact there exists much freedom when defining a Hamming code with these dimensions. For example, we’re free to perform any permutation of the columns of the generator matrix ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) and the parity check matrix ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png), and the resulting code will have the same properties as the ![(7,4,3)](./images/7fa3141228a852a5b6fc51ea8c96dae312e91b05.png) Hamming code discussed in this section.

The term _Hamming code_ actually applies to a whole family of linear codes. For any ![r >2](./images/ccc60621fb0feac82fa5d2dddc9fe4e9875afe67.png), there exists a ![(2^r-1,2^{r}-r-1,3)](./images/71bd60ed94f300d824707e3ba3b39bea88a68402.png) Hamming code that has similar structure and properties as the _Hamming ![(7,4,3)](./images/7fa3141228a852a5b6fc51ea8c96dae312e91b05.png) code_. The ability to “read” the location of the error directly from the syndrome is truly a marvellous mathematical construction particular to the Hamming code. Other types of error-correcting codes that infer the error from the syndrome vector ![\vec{s}](./images/9950fe35f2b707d21bfde2e9981b9711e527f62a.png) may require more complicated procedures.

Note that all Hamming codes have minimum distance ![d=3](./images/8292ebebf77eaab13ddc140e111c85c08c61b5c1.png), which means they allow us to correct ![\lfloor \frac{3}{2}\rfloor = 1](./images/ede65e5443592c3f2dea3baa1186dfb6ee089296.png) bit errors. Hamming codes are therefore not appropriate for use with communication channels on which multi-bit errors are likely to occur. There exist other code families, like the _Reed–Muller codes_ and _Reed–Solomon codes_, which can be used in noisier scenarios. For example, Reed–Solomon codes are used by NASA for deep-space communications and for error correction on DVDs.

###[Error-detecting codes](./Front matter.md)

Another approach for dealing with errors is to focus on _detecting_ the errors, rather than trying to correct them. Error-detecting codes, like the _parity-check code_, are used in scenarios where it is possible to retransmit messages. If the receiver detects a transmission error has occurred, she can ask the sender to retransmit the corrupted message. The receiver will be like, “Yo, Sender, I got your message, but its _parity_ was _odd_, so I know there was an error and I want you to send that message again.” Error detection and retransmission is how internet protocols work (TCP/IP).

The _parity-check code_ is a simple example of an error-detecting code. The _parity_ of a bitstring describes whether the number of 1s in the string is odd or even. The bitstring ![0010](./images/fac31ffb1217d907919b28a1d19fd592346f8feb.png) has odd parity, while the bitstring ![1100](./images/01cc65dca51fd5f7c3f9be9394936bd0bbbf11ab.png) has even parity. We can compute the parity of any bitstring by taking the sum of its bits—the sum being performed in the finite field ![\mathbb{F}_2](./images/435aef1d0a822b1d260e1b6619312c55b17d8252.png).

A simple ![(k+1,k,2)](./images/796343c88ce362f5542fd2929983856ae4863442.png) parity-check code is created by appending a single bit ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) (the parity bit) to the end of every message to indicate the parity of the message bitstring ![x_1x_2\cdots x_k](./images/13a0d313fcb96f1d056873317a8dbde12f739e89.png). We append ![p=1](./images/76cb3f3d712fe3ac79024ba82ce3457d398525a3.png) if the message has odd parity, and ![p=0](./images/5dd01cd0b4adb112a6e7d73b40441ef0181c6d8a.png) if the message has even parity. The resultant message-plus-parity-check bitstring ![\vec{c}=x_1x_2\cdots x_kp](./images/68f18fae9900cef209f4e1c7fea0c60c4445361e.png) will always have even parity.

If a single bit-flip error occurs during transmission, the received codeword ![\vec{c}^{\,\prime}](./images/08aec95cd7db718f801e6b15e86c6bcb4c302ad2.png) will have odd parity, which tells us the message data has been affected by noise. More advanced error-detecting schemes can detect multiple errors, at the cost of appending more parity-check bits at the end of messages.

###[Links](./Front matter.md)

\[ The Hamming distance between bitstrings \][`https://en.wikipedia.org/wiki/Hamming_distance`](./Hamming_distance.md)

\[ More examples of linear codes on Wikipedia \][`https://en.wikipedia.org/wiki/Linear_code`](./Linear_code.md)[`https://en.wikipedia.org/wiki/Hamming_code`](./Hamming_code.md)[`https://en.wikipedia.org/wiki/Reed-Muller_code`](./Reed-Muller_code.md)

###[Exercises](./Front matter.md)

E7.15 Find the codeword ![\vec{c}](./images/69a3d602f0d106707ffef54b132972e1705b04cf.png) that corresponds to the message ![\vec{x}=(1,0,1,1)](./images/a578b3151e0cc26119159aa9595c0b797db5d0dc.png) for the ![(7,4,3)](./images/7fa3141228a852a5b6fc51ea8c96dae312e91b05.png) Hamming code, which has the generator matrix ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) as given on page eqn:hamming\_code\_generator\_matrix.

E7.16 Construct the ![(5,4,2)](./images/c8fef68fcaa7402f4d9415dfdc848bc3a850dec4.png) parity check code’s encoding matrix ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png).

##[7.11 Fourier analysis](./Chapter 7_ Applications.md)

Way back in the 17th century, Isaac Newton carried out a famous experiment using light beams and glass prisms. He showed that when a beam of white light passes through a prism, it splits into a rainbow of colours: the rainbow is red at one end, followed by orange, yellow, green, blue, and finally violet at the other end. This experiment showed that white light is made of _components_ with different colours. Using the language of linear algebra, we can say that white light is a “linear combination” of different colours.

Today we know that different colours of light correspond to electromagnetic waves with different frequencies: red light has a frequency around ![450](./images/a5cfcf8d05b287f4dbe0d38ce9697a3ee250768b.png) THz, while violet light has a frequency around ![730](./images/60a6cb8d44209aef91837fadf70a02655a8961c2.png) THz. We can therefore say that white light is made of components with different frequencies. The notion of describing complex phenomena in terms of components with different frequencies is the main idea behind _Fourier analysis_.

Fourier analysis is used to describe sounds, vibrations, electric signals, radio signals, light signals, and many other phenomena. The Fourier transform allows us to represent all these “signals” in terms of components with different frequencies. Indeed, the Fourier transform can be understood as a change-of-basis operation that converts a signal from a time basis to a frequency basis:

![[\mathbf{v}]_t  
\qquad 
\Leftrightarrow 
\qquad[\mathbf{v}]_f.](../Images/0ef23ff05b427c5b9320da0f8db1c56e49c5bd6e.png)

For example, if ![\mathbf{v}](./images/633b84ab115cc79e0751cfddae6cfadae6fca32b.png) represents a musical vibration, then ![[\mathbf{v}]_t](../Images/32978e6e76d951d5e1da2e96c034eeda1c66da45.png) corresponds to the vibration as a function of time, while ![[\mathbf{v}]_f](../Images/2e4ec0302884d1c59de7a403cd8fb39d04d42d3b.png) corresponds to the frequency content of the vibration. Depending on the properties of the signal in the time domain and the choice of basis for the frequency domain, different Fourier transformations are possible.

We’ll study three different bases for the frequency domain based on orthonormal sets of sinusoidal and complex exponential functions. The _Fourier series_ is a representation for continuous periodic functions ![f(t) \in \{ \mathbb{R} \to \mathbb{R} \}](./images/c34022052bf9e738213aabadad246eab468794d2.png); that is, functions that satisfy ![f(T+t) = f(t)](./images/d7d0dcbbbfcd42dcc380702cfaee609c70d3395e.png). The Fourier basis used in the Fourier series is the set of sines and cosines of the form ![\sin(\tfrac{2\pi n}{T}t)](./images/3cf77e10c335ab46f401c67fbe0810aa4160da15.png) and ![\cos(\tfrac{2\pi n}{T}t)](./images/c3d1a2369fa04ff9040acdd97211be5a6aed804e.png), which form an orthogonal set. The _Fourier transform_ is the continuous version of the Fourier series. Instead of a countable set of frequency components, the frequency representation of the signal is described by a complex-valued continuous function ![f(\omega) \in \{ \mathbb{R} \to \mathbb{C} \}](./images/f5f80a162e52a5eea7ad2d7fc0ee2e8114dcb090.png). Instead of a continuous time parameter ![t\in \mathbb{R}](./images/27da8cc414f17278d49c7116607963991c3cd05f.png), certain signals are described in terms of ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) _samples_ from the time signal: ![\{ f[t] \}_{t\in[0,1,\ldots, N-1]}](../Images/450da87035ae3248d72ae1ee135cd2539e4eb949.png). The _discrete Fourier transform_ is a version of the Fourier transform for signals defined at discrete time samples.[Table 7.2](./Chapter 7_ Applications.md) shows a summary of these three Fourier-type transformations. The table indicates the class of functions for which the transform applies, the Fourier basis for the transform, and the frequency-domain representation used.

**Fourier transformations**

Name

Time domain

Fourier basis

Frequency domain

**FS**

![f(t) \in \{ \mathbb{R} \to \mathbb{R} \}](./images/c34022052bf9e738213aabadad246eab468794d2.png)

![1, \{\cos\!\left(\frac{2\pi n}{T}\!\right)\! \}_{n \in \mathbb{N}_+},](./images/0e9dfc6efb143b883a3c5c785efe507d4a377980.png)

![(a_0,a_1,b_1, \ldots)](./images/45685698d05ba2e5eb1fe742e21b1f31ac4761d8.png)

s.t. ![f(t)=f(t+T)](./images/87370cdfe2cfe0f29c4353f701ce531e83c46ec1.png)

![\qquad \{\sin\!\left(\frac{2\pi n}{T}\!\right)\}_{n \in \mathbb{N}_+}](./images/32c80755350b7db269ded28317c8094f1d888a7e.png)

**FT**

![f(t) \in \{ \mathbb{R} \to \mathbb{R} \}](./images/c34022052bf9e738213aabadad246eab468794d2.png)

![\{e^{i\omega t} \}_{\omega \in \mathbb{R}}](./images/2c46c18919f8829b99cd6e78f22f96a127ab8368.png)

![f(\omega) \in \{ \mathbb{R} \to \mathbb{C} \}](./images/f5f80a162e52a5eea7ad2d7fc0ee2e8114dcb090.png)

s.t. ![\displaystyle\int_{-\infty}^\infty \!\!|f(t)|^2\,dt < \infty](./images/5113eaba126ed43f3588bf49d8fe009f8e6c5c7a.png)

**DFT**

![f[t] \in \{ [N] \to \mathbb{R}\}](../Images/981bc6ca11cfedf0373e60d7a98257339b1c8b98.png)

![\{e^{\frac{i w t}{N}} \}_{w \in[N]}](../Images/755bb993a491c8930515cf46223827378ee3f3bc.png)

![f[w]\in \{ [N] \to\mathbb{C}\}](../Images/f35c8bb68a9aa370ccb6c513a140b3b2d723081d.png)

Table 7.2: This table shows the time domains, Fourier bases, and frequency domains for the three Fourier transformations that we’ll discuss. The _Fourier series_ (**FS**) converts periodic continuous time signals into Fourier coefficients. The _Fourier transform_ (**FT**) converts finite-power continuous signal into continuous functions of frequency. The _discrete Fourier transform_ (**DFT**) is the discretized version of the Fourier transform.

Fourier transforms are normally studied by physics and electrical engineering students during their second or third year at university. You, dear readers, thanks to your understanding of linear algebra, are ready for a 10-page sneak-peek of the Fourier transformations course right now. In this section, we’ll study the mathematics behind the Fourier transforms and discuss how they’re used in practical signal-processing applications. Before we jump into signal processing, let’s look at something much simpler: the vibration of a guitar string.

###[Example 1: Describing the vibrations of a string](./Front matter.md)

Imagine a string of length ![L](./images/8344682567e06566040f4cde165f91b06c4ee6f5.png) that is stretched between two attachment points, like a guitar string. If you pluck this string it will vibrate. As it vibrates, we can describe the displacement of the string from its resting (straight, or non-vibrating) position as a function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png), where ![x \in[0, L]](../Images/45b607204ada714caed9d60404d327f6bbf32c62.png). The longest vibration along the string’s length is called the _fundamental_, while other, shorter vibrations are called _overtones_. See[Figure 7.16](./Chapter 7_ Applications.md) for an illustration. When you pluck the guitar string, your ears perceive the fundamental and the overtones combined as a single tone. The relative prominence of the fundamental vs. overtone frequencies varies among instruments.

When strings vibrate, only certain _modes_ of vibration continue to vibrate over time, while others decay (fade out and stop) more quickly. Once the string is plucked and the initial vibration begins, the energy in the string “bounces around,” reflecting from the fixed attachments at both ends, and many vibrations cancel out. After some time, the only vibrations remaining on the string are the following sine-like vibrations:

![\mathbf{e}_1(x) = \sin(\tfrac{\pi}{L}x),
\; \; 
\mathbf{e}_2(x) = \sin(\tfrac{2\pi}{L}x),
\; \; 
\mathbf{e}_3(x) = \sin(\tfrac{3\pi}{L}x),
\; \; 
\ldots \; .](./images/e3556bcde7ade0983fc4f12396e3f74478865693.png)

Vibrations of the form ![\mathbf{e}_n(x) = \sin(\tfrac{n\pi}{L}x)](./images/bf2c8c332f87c075e2d53811204a69234464132e.png) persist because they are stable, which means they satisfy the physics constraints imposed on the string[2](./Front matter.md) One constraint is that the string’s endpoints are clamped down: ![\mathbf{e}_n(0)=0](./images/91caa1e1f014528e2a5bf0ae5e2611b2e4bb43d4.png) and ![\mathbf{e}_n(L)=0](./images/7230566d2252e452df02b7e0d4062c0dd36166cc.png). Another constraint requires that the vibration of the string ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) must satisfy the equation ![f(x)=f(L-x)](./images/d8142a62ac8120476c2f123795b9a6da41735ceb.png).

![standing_waves_on_a_string](./images/standing_waves_on_a_string.png)

Figure 7.16: Standing waves on a string with length ![L=1](./images/08ac672d0cec5bfca53a42870c80578246b6e562.png). The longest vibration is called the _fundamental_. Other vibrations are called _overtones_.

The functions ![\{\mathbf{e}_n(x)\}_{n\in \mathbb{N}^+}](./images/7fab5bf3a78c4cc1edaac9985bbc2ac95cd53737.png) form a basis for the set of vibrations that satisfy ![f(0)=0](./images/53bf5ef7d1d9a20e980e1d84f3a35e338c86ea86.png), ![f(L)=0](./images/6e04c6240da84db635e57ad7069b68b8aaba6c54.png), and ![f(x)=f(L-x)](./images/d8142a62ac8120476c2f123795b9a6da41735ceb.png) on ![[0,L]](../Images/39ec3fdc51f265bbabe7152214c3b5ac77f73582.png). Any vibration on the string can be described in terms of a sequence of coefficients ![(a_1, a_2, a_3, \ldots )](./images/fbe993a8fb39c6ced7648869d329e667e9d4c0ce.png):

![f(x) \, \textrm{ s.t. } f(x) = f(L-x) 
\qquad
\Leftrightarrow
\qquad
(a_1, a_2, a_3, a_4, \ldots ). \qquad](./images/1704cdbe165f8643b354086036b1a19b741208f1.png)

The coefficient ![a_i](./images/742468daa9df98467c8672fd641aa4d150e2d2ed.png) represents how much of the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th vibration exists on the string.

Depending how you pluck the string, the shape of the vibrating string ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) will be some linear combination of the vibrations ![\mathbf{e}_n(x)](./images/8cf3dc8de95d53b4a8e06964643bb237e9f2563e.png):

![\begin{align*}
f(x)   	&= 	a_1\sin(\tfrac{\pi}{L}x) + a_2 \sin(\tfrac{2\pi}{L}x) + a_3\sin(\tfrac{3\pi}{L}x) + \; \cdots 				\\
&=  	a_1\,\mathbf{e}_1(x)  \quad  + a_2\,\mathbf{e}_2(x)  \quad  \;\, +  a_3\,\mathbf{e}_3(x)  \quad \; + \;  \cdots
\end{align*}](./images/6b219b53d35b2d063a2611ffca23f0c7ab43607d.png)

That’s quite crazy if you think about it: rather than describing the exact shape of the vibrating string ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png), it’s sufficient to specify a list of coefficients to describe the vibration. The coefficient ![a_1](./images/687e2b6e809c59ef21e9cab2e018a3b291d0bd3e.png) tells us the prominence of the fundamental vibration, and the other coefficients tell us the prominence of the overtones. Since the laws of physics restrict the possible vibrations to linear combinations of the basis vibrations ![\{\mathbf{e}_n(x)\}_{n\in \mathbb{N}^+}](./images/7fab5bf3a78c4cc1edaac9985bbc2ac95cd53737.png), we can represent any vibration on the string through its sequence of coefficients ![(a_1, a_2, a_3, \ldots )](./images/fbe993a8fb39c6ced7648869d329e667e9d4c0ce.png).

###[The main idea](./Front matter.md)

The guitar string example shows it’s possible to understand a complex real-world system in terms of a succinct description—the coefficients ![(a_1, a_2, a_3, \ldots)](./images/fbe993a8fb39c6ced7648869d329e667e9d4c0ce.png). This general pattern occurs when solving many science problems stated in terms of differential equations. Often, the solutions can be expressed as linear combinations of an orthonormal basis of functions. Using this example, we’re now positioned to explain the main idea behind Fourier transformations and their connection to the concept of inner product space, which we studied in[Section 6.4](./Chapter 6_ Theoretical linear algebra.md).

The fundamental starting point of all Fourier-type reasoning is to define the inner product space for the solution space, and a basis of orthonormal functions for that space. In the case of the vibrating string, the space of string vibrations consists of functions ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) on the interval ![[0,L]](../Images/39ec3fdc51f265bbabe7152214c3b5ac77f73582.png) that satisfy ![f(0)=0](./images/53bf5ef7d1d9a20e980e1d84f3a35e338c86ea86.png), ![f(L)=0](./images/6e04c6240da84db635e57ad7069b68b8aaba6c54.png), and ![f(x) = f(L-x)](./images/d8142a62ac8120476c2f123795b9a6da41735ceb.png). The inner product operation we’ll use for this space is

![\langle f(x), g(x) \rangle \,\eqdef\, \int_{x=0}^{x=L} f(x)g(x) \, dx,](./images/ebf1ff571e7ca72bf05839258153a341a1539385.png)

and the functions ![\{\mathbf{e}_n(x)\}_{n\in \mathbb{N}^+}](./images/7fab5bf3a78c4cc1edaac9985bbc2ac95cd53737.png) form an orthogonal basis for this space. We can verify that ![\langle \mathbf{e}_m(x), \mathbf{e}_n(x) \rangle = 0](./images/1469ce3f3b32c5fcb45668940362825fff7c9533.png) for all ![m \neq n](./images/4a4117397ea95e1696eec3b02135d02a158d0dff.png). See Exercise [7.11.9](./Chapter 7_ Applications.md) for a hands-on experience.

Since ![\{\mathbf{e}_n(x)\}_{n\in \mathbb{N}^+}](./images/7fab5bf3a78c4cc1edaac9985bbc2ac95cd53737.png) forms a basis, we can express any function as a linear combination of the basis functions. The complicated-looking Fourier transform formulas that we’ll discuss shortly can therefore be understood as applications of the general change-of-basis formula.

#####[Change-of-basis review](./Front matter.md)

Let’s quickly review the change-of-basis formula. You recall the change-of-basis operation, right? Given two orthonormal bases, ![B=\{ \hat{e}_1, \hat{e}_2, \hat{e}_3 \}](./images/085e29361ca11de1ae1bb3f1912df98da41a610e.png) and ![B^\prime=\{ \hat{e}^\prime_1, \hat{e}^\prime_2, \hat{e}^\prime_3 \}](./images/5fb8f867d1fb32eb70d533f6e96ec771e3b416ea.png), you should know how to convert a vector ![[\vec{v}]_{B}](../Images/a9c18efe9118dbe0258614d5a0b292f46ff3e3ce.png) expressed with respect to basis ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png), into coordinates with respect to basis ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png). In case you’ve forgotten, look back to page 4.3.7, where we define the change-of-basis matrix ![\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}](../Images/029b9a61176cd5f29400e699e84a44a9f08e60cd.png) that converts from ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) coordinates to ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) coordinates, and its inverse ![\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}](../Images/1a734635c91bfad2c510fd7637a4502e2ac1ea24.png) that converts from ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) coordinates to ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) coordinates:

![[\vec{v}]_{B^\prime} = 
\!\tensor[_{B^\prime}]{\left[\mathbbm{1}\right]}{_{B}}\! 
[\vec{v}]_{B}
\qquad
\Leftrightarrow
\qquad[\vec{v}]_{B} = 
\!\tensor[_{B}]{\left[\mathbbm{1}\right]}{_{B^\prime}}\! 
[\vec{v}]_{B^\prime}.](../Images/fb9aac065bd8d61571c1109910c28102b271ddb4.png)

When the bases are orthonormal, the change-of-basis operation depends only on the inner product between the vectors of the two bases:

![\vec{v}^{\,\prime}_i
= 
\sum_{j=1}^3  \langle \hat{e}^\prime_i,  \hat{e}_j \rangle v_j
\qquad
\Leftrightarrow
\qquad
\vec{v}^{}_i
= 
\sum_{j=1}^3  \langle \hat{e}_i,  \hat{e}_j^\prime \rangle v^{\,\prime}_j	.](./images/6b309c7e9f70befdd6bc2686bf40b59c1209e812.png)

Orthonormal bases are nice like that—if you know how to compute inner products, you can perform the change of basis.

To apply the general formulas for change of basis to the case of the vibrating string, we must first define the two bases and compute the inner product between them. We can think of the function ![f(x) \in \{ [0,L] \to \mathbb{R} \}](../Images/40fc2fd02aea67816f4e4239909a551ef83c418b.png) as described in the “default basis” ![\mathbf{e}_x](./images/602e0b511775e6d4586743db41160a34e3a3161c.png), which is equal to one at ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and zero everywhere else. The Fourier basis for the problem consists of the functions ![\mathbf{e}_n = \sin(\tfrac{n\pi}{L}x)](./images/2f00d0101b432af4d5259f134e9b4d8e007e4efe.png) for ![n \in \mathbb{N}^+](./images/dea1d1ce93c7247b2208261e5943df6b0ea8d29a.png). The inner product between ![\mathbf{e}_x](./images/602e0b511775e6d4586743db41160a34e3a3161c.png) and ![\mathbf{e}_n](./images/7a28813469305b79b0fd3981c465e132bf19c310.png) is

![\langle
\mathbf{e}_x,
\mathbf{e}_n
\rangle
=
\int_0^L 
\mathbf{e}_x(y)
\sin(\tfrac{n\pi}{L}y)
\,dy
=
\sin(\tfrac{n\pi}{L}x),](./images/25105b36babab88ca1bf414efd4fb42cf44b6c25.png)

since the function ![\mathbf{e}_x(y)](./images/d1fadc125cbbd7d1175a6b3f3460c642c693ddbf.png) is equal to zero everywhere except at ![y=x](./images/f11b12456873127040f5e21fe0be791e0421166c.png).

We can obtain the change-of-basis transformations by extending the notion of a matrix-vector appropriately. We use the integral on the interval ![[0,L]](../Images/39ec3fdc51f265bbabe7152214c3b5ac77f73582.png) for the change of basis to the Fourier coefficients, and the infinite sum over coefficients to change from the space of Fourier coefficients to functions:

![a_n
= 
\!
\int_0^L 
\!\!\sin(\tfrac{n\pi}{L}x) f(x) \, dx
\qquad
\Leftrightarrow
\qquad
f(x)
= 
\!\sum_{n=1}^\infty  
\sin(\tfrac{n\pi}{L}x)
a_n.](./images/e48e22736fc8061175995e4e858fdaaca54700fd.png)

Compare these formulas with the basic change-of-basis formula between bases ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png).

![fourier_series_sin_only_change_of_basis_matrix](./images/fourier_series_sin_only_change_of_basis_matrix.png)

Figure 7.17: Any string vibration ![f(x)](./images/e991ff22266fdbbf51e9ab850aa72059edbea8de.png) can be represented as coefficients ![(a_1, a_2, a_3, a_4, \ldots)](./images/a05835d57e4dca17675475ec873af1999350eb34.png) with respect to the basis of functions ![\mathbf{e}_n(x) = \sin(\tfrac{n\pi}{L}x)](./images/d6dfe4f9b24d989b0e600d6cd35102bbf24d0218.png).

[Figure 7.17](./Chapter 7_ Applications.md) illustrates the right side of the change-of-basis formula. A vibration expressed in the Fourier basis ![(a_1,a_2,a_3,a_4,\ldots)](./images/b803351b1732547c17fe6a5e8a3193b72207376c.png) is transformed to a function ![f(x) \in \{ [0,L] \to \mathbb{R} \}](../Images/40fc2fd02aea67816f4e4239909a551ef83c418b.png) in the default basis.

####[Analysis and synthesis](./Front matter.md)

The terminology for describing Fourier transformations borrows from the world of music. A _frequency analyzer_ is a device used to measure the sonic frequencies contained in audio signals. A _synthesizer_ is an instrument that generates combinations of electronic signals to produce various musical sounds.

Similarly, in the jargon of Fourier transformations, we refer to the change of basis from the default basis to the Fourier basis (![\!\tensor[_{f}]{\left[\mathbbm{1}\right]}{_{x}}](../Images/07ad44e8c9769aa95446e773fead7912fa195206.png)) as _Fourier analysis_, and the transformation from the Fourier basis to the default basis (![\!\tensor[_{x}]{\left[\mathbbm{1}\right]}{_{f}}](../Images/38ab62344d03d7f4a083c95315cd6750218b5b07.png)) as _Fourier synthesis_. This terminology, in addition to sounding extra fancy, gives us some useful intuition about the purpose of the Fourier transform. Given a vibration on the string, we use the Fourier transform to analyze the vibration, decomposing it into its constituent vibrations. The _Fourier analysis equations_ describe how to calculate the Fourier coefficients of the different frequencies.

The opposite process of the Fourier transformation—starting with the Fourier coefficients and combining them to obtain a vibration in the default basis—is called _synthesis_, in analogy with a synthesizer that can generate myriad sounds. The synthesis of a vibration as a function of ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) is expressed mathematically as a linear combination of vibrations with different frequencies multiplied by frequency-domain coefficients. For example, you can pick any set of coefficients ![(a_1, a_2, a_3, a_4, \ldots)](./images/b803351b1732547c17fe6a5e8a3193b72207376c.png), and form the linear combination ![\sum_{n=1}^N a_n\sin(\tfrac{2\pi n}{L}x)](./images/0c271716762ec98c951e0e439b6100269847a8f1.png); then you can check to hear what that vibration sounds like. This is how synthesizers work: they can mimic the sounds of various musical instruments and natural phenomena, as well as create totally new sounds, by producing different linear combinations of a basis of vibrations.

###[Fourier series](./Front matter.md)

When discussing Fourier transformations, it is natural to work with functions of time ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png), which we call _signals_. A signal in the “time basis” is specified by its values ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) for all times ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png). This is the “time domain” representation for signals. The _Fourier series_ corresponds to the following change-of-basis operation:

![f(t) \, \textrm{ s.t. } f(t) = f(T+t) 
\qquad
\Leftrightarrow
\qquad
(a_0, a_1, b_1, a_2, b_2,  \ldots ).](./images/7f7bbaf578f3a57940fc54a184ff29ff6edf986d.png)

The coefficients ![(a_0, a_1, b_1, a_2, b_2,  \ldots)](./images/852c120e01e3f475ccda8bda8566c862a27c423d.png) are called the _Fourier coefficients_ of ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png). The _Fourier series_ applies to all signals ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) that satisfy the constraint ![f(t)=f(t+T)](./images/87370cdfe2cfe0f29c4353f701ce531e83c46ec1.png) for all ![t \in[0,T)](./images/d2261e3687a73c213a6112e759752fe4ea06e526.png). We say such signals are _periodic_ with period ![T](./images/033cb66d601734240c89b124c013cea4024cbf13.png).

The basis used for the Fourier series consists of the set of cosine and sine functions with frequencies that are multiples of ![\tfrac{2\pi}{T}](./images/025c5e643d00a3f28335a8a75e0cdda3588a0947.png):

![\left\{
\sin\!\left(\frac{2\pi n}{T}t\!\right)
\right\}_{n \in \mathbb{N}_+}
\; \textrm{ and } 
\quad
\left\{
\cos\!\left(\frac{2\pi n}{T}t\!\right)
\right\}_{n \in \mathbb{N}}.](./images/af541830ccb30da3e8f9425eb72d614bf7cd779f.png)

This family of functions forms an orthogonal set with respect to the standard inner product:

![\langle f(t), g(t) \rangle = \frac{1}{T}\int_{t=0}^{t=T} f(t)g(t) \, dt.](./images/9b66b939af52bb66cb380dccb50a8a92e94a2ee0.png)

Every periodic signal ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) can be represented as a _Fourier series_ of the form:

![\begin{equation}
f(t) 
=
a_0 + \sum_{n=1}^\infty a_n\cos(\tfrac{2\pi n}{T}t) 
\; + \; 
\sum_{n=1}^\infty b_n\sin(\tfrac{2\pi n}{T}t).
\tag{FSS}
\label{eqn:FSS}
\end{equation}](./images/34a5d19ced74b0fcc39e28118981a1aca3a0fcea.png)

This is the Fourier series _synthesis_ equation, hence the label[(7.15)](./Chapter 7_ Applications.md). The coefficient ![a_i](./images/742468daa9df98467c8672fd641aa4d150e2d2ed.png) represents how much of the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th cosine-like vibration is contained in ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png), and the coefficient ![b_i](./images/13294bd22e12bd7ece755875322827e8e82562b2.png) represents how much of the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th sine-like vibration is contained in ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png). See the illustration in[Figure 7.18](./Chapter 7_ Applications.md) for a visual representation of the synthesis equation. This representation of a periodic signal is directly analogous to the analysis we performed for the vibrating string, but this time we use both sines and cosines.

![fourier_series_change_of_basis_matrix](./images/fourier_series_change_of_basis_matrix.png)

Figure 7.18: The Fourier series synthesis[equation (7.15)](./Chapter 7_ Applications.md) represented as a matrix-vector product. A periodic signal ![f(t)](./images/5efd00e5bf3a607572430909c72c6a99d7761528.png) is represented as a series of Fourier coefficients ![(a_0,  a_1, b_1, a_2, b_2, a_3, b_3, \ldots)](./images/d28867c021b369ba35d6e5702cb46cba54a63e71.png). The first column of the change-of-basis matrix corresponds to the constant component ![1=\cos(0)](./images/f3e56479d23aa0d6be7ddea1bfa6f34d04195246.png). The remaining columns correspond to cosines and sines with different frequencies.

We compute the Fourier coefficients using the following formulas:

![\begin{equation}
a_n \! = \frac{1}{T} \!\int_0^T  \!\! f(t) \cos(\tfrac{2\pi n}{T}t) \,dt,
\quad
\; \; \; 
b_n \! = \frac{1}{T} \!\int_0^T  \!\! f(t) \sin(\tfrac{2\pi n}{T}t) \,dt.
\tag{FSA}
\label{eqn:FSA}
\end{equation}](./images/54746365f3002dd253e86470d9c45e95758ff888.png)

These are the Fourier series _analysis_ equations, hence the label[(7.16)](./Chapter 7_ Applications.md). These transformations correspond to the standard change of basis for the function ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) in the time domain to the Fourier basis of cosines and sines.

For the Fourier series representation of a periodic time signal to be exact, we must compute an infinite number of coefficients in the Fourier series ![(a_0, a_1, b_1, a_2, b_2,  \ldots)](./images/852c120e01e3f475ccda8bda8566c862a27c423d.png). However, we’re often interested in obtaining an approximation to a ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) using only a finite set of Fourier coefficients:

![f(t) 	
\approx 
a_0 + \sum_{n=1}^N a_n\cos(\tfrac{2\pi n}{T}t)  + \sum_{n=1}^N b_n\sin(\tfrac{2\pi n}{T}t).](./images/6389d6829a425886f2af267b0e13c7c752ed5325.png)

This is called a _Fourier series approximation_ since the frequency representation does not contain the components with frequencies ![\frac{N+1}{T}](./images/0d0bf7bb5725f63e1bae197e2cfdaf8fd4d067ad.png), ![\frac{N+2}{T}](./images/6eba66e1bfa3bc6c9933b681b329963d06c551e7.png), and higher. Nevertheless, these finite-series approximations of signals are used in many practical scenarios; it’s much easier to compute a finite number of Fourier coefficients instead of an infinite number.

#####[Example](./Front matter.md)

For an example calculation of the Fourier coefficients of the _square wave_ signal, see[`bit.ly/fourier_series_square_wave`](./fourier_series_square_wave.md) by Joshua Vaughan. Note the square wave analyzed is an _odd_ function, so its coefficients ![a_n](./images/1506cdb80ad5652d9a410c8547f1a72cbd19ce34.png) are all zero.

![fourier_series_square_wave](./images/fourier_series_square_wave.png)

Figure 7.19: The square-wave signal can be approximated by a linear combination of sine functions with different frequencies.

In the next section, we’ll describe the Fourier transform, which is a continuous-frequency version of the Fourier series.

###[Fourier transform](./Front matter.md)

The Fourier series representation applies only to periodic functions ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png), but not every function of interest in signal processing is periodic. The _Fourier transform_ applies to all signals ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) (periodic or not) that obey the _finite-power_ constraint:

![\int_{t=-\infty}^{t=+\infty} |f(t)|^2 \, dt  \; \leq  \;  \infty.](./images/942805363921ecfe2d07525f81ec5bf6d01a1af4.png)

This class of functions includes most signals of practical importance in communication scenarios.

The result of the _Fourier transform_ is a complex-valued continuous function in the frequency domain:

![f(t) \in \{ \mathbb{R} \to \mathbb{R} \}
\qquad
\Leftrightarrow
\qquad
f(\omega) \in \{ \mathbb{R} \to \mathbb{C} \}.](./images/dd18287721faf8f050754cbcbb659a2dd2057664.png)

The basis used in the Fourier transforms is

![\mathbf{e}_\omega 	\; = \; e^{i\omega t},
\textrm{ for } \omega \in \mathbb{R},](./images/154e0643b4bc8f850ba3c9c0eba241676c7e9589.png)

parametrized by the continuous parameters ![\omega \in \mathbb{R}](./images/d3e30595ea5a88865c5fd6c2ccbae116916999af.png). The functions ![\{\mathbf{e}_\omega\}](./images/df90af1e4879995961e5902dcac4e8ae43addab8.png) form an orthogonal basis with respect to the standard inner product for functions:

![\langle f(t), g(t) \rangle
= 
\frac{1}{\sqrt{2\pi}} 
\int_{-\infty}^{\infty} 
\overline{ f(t) }
g(t) 
\, dt.
\label{eqn:fourier_transform_innner_product}](./images/f0d6fdf493f582013aafacfc0f234104d864c3a9.png)

The change-of-basis from the time domain to the frequency domain is performed using the integral:

![\begin{equation}
f(\omega)
= \!\!
\int 
\langle \mathbf{e}_\omega, \mathbf{e}_t  \rangle
f(t)
\, dt
=
\tfrac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty}
e^{-i\omega t}
f(t)
\, dt.
\tag{FTA}
\label{eqn:FTA}
\end{equation}](./images/3bdbd03613f9c54a89b6f42526c612470f1a657f.png)

This is the Fourier transform _analysis_ equation. We can understand this formula as an instance of the general change-of-basis formula from the “default basis” for the time domain ![\{\mathbf{e}_t \}_{t \in \mathbb{R}}](./images/d9b7406394eba44b225292335780a13411534081.png) to the basis ![\{\mathbf{e}_\omega \}_{\omega \in \mathbb{R}}](./images/774b8d57b848c7b8df5503a240c5abfa1ed16e83.png). The function ![f(\omega)](./images/2aeb0e1e8fcde8c3b93976b5977d10143d779006.png) is called the _spectrum_ or _Fourier transform_ of ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png); it tells us all the information about the frequency content of the signal ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png). Note _Fourier transform_ can be used as a verb when referring to the change-of-basis transformation, or as a noun when referring to the function ![f(\omega)](./images/2aeb0e1e8fcde8c3b93976b5977d10143d779006.png), which is the result of the Fourier transform.

The _Inverse Fourier transform_ is the change of basis from the frequency domain back to the time domain. Given the frequency representation of a function ![f(\omega)](./images/2aeb0e1e8fcde8c3b93976b5977d10143d779006.png), we can reconstruct the time representation of the signal using the Fourier transform _synthesis_ integral:

![\begin{equation}
f(t) = \!\!			
\int
\langle \mathbf{e}_t, \mathbf{e}_\omega  \rangle
f(\omega)
\, d\omega
=
\tfrac{1}{\sqrt{2\pi}}
\int_{-\infty}^{\infty} 
e^{i\omega t}
f(\omega)
\, d\omega.
\tag{FTS}
\label{eqn:FTS}
\end{equation}](./images/2607b11a8a3339b34188efbcd767453944ddf024.png)

Note the similarity between the forward (analysis) and the inverse (synthesis) Fourier transform formulas. Indeed, these are representations of the general change-of-basis formula using the inner product for functions. Compare the Fourier transform change-of-basis formulas and the basic change-of-basis formulas between bases ![B](./images/db67b719c7a4518c7017f4eb519bb595c2baa02a.png) and ![B^\prime](./images/43ecbf29e1aa8f9a38b234b0f1103d2f6fe2adf1.png) discussed on page . The conjugate-symmetric property of the inner product ![\langle \mathbf{e}_t, \mathbf{e}_\omega  \rangle = \overline{ \langle \mathbf{e}_\omega, \mathbf{e}_t  \rangle  }](./images/41ff562d0bdf2a7e5aa70ab05ecce47ac5e2d8bc.png) explains the change from ![e^{-i\omega t}](./images/588d3694ae8c25c4d8e2de9bfb27cdfc8790774c.png) to ![e^{i\omega t}](./images/86361ad2c78fb3405a65fdad79513e67dae80d4c.png).

Further discussion about the Fourier transform and its many applications is beyond the scope of the current section. If you take a signal-processing course (the _best_ course in the electrical engineering curriculum), you’ll learn all about the Fourier transform.

###[Discrete Fourier transform](./Front matter.md)

Continuous-time signals are important in sound engineering, radio communications, and other communication scenarios. Signals can also be digitized and represented as discrete samples rather than continuous functions. A continuous-time signal ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) can be approximated by taking a finite set of ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) _samples_ from the signal. This sampling results in a discrete-time signal ![f[t] \in \{ [N] \to \mathbb{R} \}](../Images/981bc6ca11cfedf0373e60d7a98257339b1c8b98.png), where the shorthand ![[N]](../Images/91b08290a667f9d50dd342f06055023c8a9e339c.png) denotes the sequence ![[0,1,\ldots,N-1]](../Images/6021fa72f457ae2f3cc1eba0874ab226541f7585.png). We’ll use square brackets around the function input to distinguish the discrete-time signal ![f[t]](../Images/cb4e46bdb39df946b82871daf7862013a89d6b2e.png) from its continuous-time counterpart ![f(t) \in \{ \mathbb{R} \to \mathbb{R} \}](./images/c34022052bf9e738213aabadad246eab468794d2.png).

The _discrete Fourier transform_ converts ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) samples of a discrete-time signal into a frequency representation with ![N](./images/5edacfb9230d9454fe52051e2dbd4f429c151d90.png) frequency components:

![f[t] \in \mathbb{R}, \textrm{ for } t \in[N]
\qquad
\Leftrightarrow
\qquad
f[w] \in \mathbb{C}, \textrm{ for } w \in[N].](../Images/5b8b8359541da349bef85223fb3a5f498f171838.png)

The basis for the frequency domain consists of complex exponentials:

![\mathbf{e}_w
\; = \; 
e^{i\frac{2\pi w}{N} t}, \textrm{ for } t \in[N] \textrm{ and } w \in[N].](../Images/cb1bf163b9e6665396796953900ec05a28326dfa.png)

These functions form an orthonormal set with respect to the inner product ![\langle f[n], g[n] \rangle \,\eqdef\, \tfrac{1}{\sqrt{N}} \sum_{n=0}^{N-1} \overline{f[n]}g[n]](../Images/bb2d2ec7c16ed745adf47589214cc7e401e2f3d7.png). You can understand this inner product and this basis as a discrete version of the inner product and basis used for the Fourier transform; hence the name.

To convert from the time domain to the frequency domain, we use the discrete Fourier transform analysis equation:

![\begin{equation}
f[w]
=
\sum_{t=0}^{N-1}
\langle \mathbf{e}_w, \mathbf{e}_t  \rangle 
f[t]			
=
\tfrac{1}{\sqrt{N}}
\sum_{t=0}^{N-1}
f[t]
e^{ -i\frac{2\pi w}{N}t }.
\tag{DFTA}
\label{eqn:DFTA}
\end{equation}](../Images/772a7f86fac0a01ea90e29ebdced1b5606d976f0.png)

This is the usual change-of-basis formula from the standard basis in the time domain ![\{ \mathbf{e}_t \}](./images/4df191fc5dd18fa86a73b37aec720db99c859f19.png) to the discrete Fourier basis ![\{ \mathbf{e}_w \}](./images/1306ad2eb3e33fc576317875e48a6bd0d2e406e9.png).

To convert a signal from the frequency domain back to the time domain, we use the discrete Fourier transform synthesis equation:

![\begin{equation}
f[t]
=
\sum_{w=0}^{N-1}
\langle \mathbf{e}_t, \mathbf{e}_w  \rangle 
f[w]
=
\tfrac{1}{\sqrt{N}}
\sum_{w=0}^{N-1}			
f[w]
e^{i\frac{2\pi w}{N} t}.
\tag{DFTS}
\label{eqn:DFTS}
\end{equation}](../Images/a277158d939eff13a2e2776bc2b76877da36d3d9.png)

Again, this inverse change-of-basis transformation can be understood as a special case of the standard change-of-basis formula we learned in[Section 4.3.7](./Chapter 4_ Geometric aspects of linear algebra.md) (see page 4.3.7).

#####[Sampling signals](./Front matter.md)

The _sample rate_ is an important practical consideration to take into account when converting analog signals to digital form. Usually the samples of the continuous signal ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) are taken at uniform time intervals spaced by time ![\Delta t](./images/0a0f8aa8527890975f5c3268b39d5d0ad71cf2a9.png). The _sample rate_ or _sampling frequency_ ![f_s](./images/ef979fcb180ea980396e8ed10609bb7a15157e9f.png) is defined as the inverse of the time between samples: ![f_s= \frac{1}{\Delta t}](./images/f0df34cf558a841f6ceb5ee95b1b66a5c0f1ca27.png). For good performance, we must choose the sampling frequency ![f_s](./images/ef979fcb180ea980396e8ed10609bb7a15157e9f.png) to be at least double that of the highest frequency of interest in the signal we’re sampling.

For example, the upper limit of the range of human hearing is ![20](./images/2d4614bb6964ec25d6422867b67c402a22f13125.png) kHz; therefore CD digital audio recordings are sampled at ![f_s = 44.1](./images/ae8ee2d50725ba79af25c5ef0be8c6181c3bb0aa.png) kHz. This means one second of audio recording corresponds to ![44\,100](./images/8ae79c8ed46317aae54e64fd383433442ad87853.png) discrete audio samples, which we’ll denote as a sequence ![f[0]](../Images/938db20156753904dd73ff8450ff87f8316977a9.png), ![f[1]](../Images/b5768b62952d715dac1ad7940b7b88387d739a22.png), ![f[2]](../Images/32796664c6758378493776a4835ada9b4b8c7ecd.png), ![\ldots](./images/4fdc0a35fde7a506fe489f70906cc1931ecac197.png), ![f[44099]](../Images/45e753f6120e9a7c5a68be9d87b51f902248cf11.png). The sample ![f[0]](../Images/938db20156753904dd73ff8450ff87f8316977a9.png) corresponds to the value of the signal at ![t=0](./images/93b87617c4082c719b320b97d0fce8c1c72438a2.png), ![f[1]](../Images/b5768b62952d715dac1ad7940b7b88387d739a22.png), which corresponds to the value of ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) at the next sampling time ![t=\frac{1}{f_s}](./images/19d213d981ef9a2aeb229872ac66df6b2332de2c.png), and so on for the rest of the samples ![f[t] = f(t \frac{1}{f_s})](../Images/ce9466a4587264db266816749b793f75653b5c63.png).

###[Digital signal processing](./Front matter.md)

Fourier transforms play a central role in digital signal processing. Many image compression and sound compression algorithms depend on the discrete Fourier transform. For example, `mp3` compression works by cutting an audio file into short time segments, transforming these segments to the frequency domain using the discrete Fourier transform, and then omitting the high-frequency components. Below, we give a high-level overview of the pipeline of transformations used for `mp3` encoding and playback. We’ll assume we start from a song recorded in the digital audio `wav` format. A `wav` file describes the song’s sound intensity as a function of time; in other words, the song is represented in the time basis ![[\texttt{song}]_{t}](../Images/1b5d5fff3715b19321abdd6939e46c61afed05eb.png).

The idea behind `mp3` encoding is to leave out certain “non-essential” aspects of audio recordings. The field of psychoacoustics develops models of human hearing that tell us which aspects of audio signals can and cannot be detected by humans. For example, we can delete the sound frequencies that are beyond the range of human hearing without noticeably degrading a recording’s playback quality. Let’s consider a simplified model of `mp3` encoding that consists of a projection in the frequency domain ![\!\tensor[_{f}]{\left[\Pi\right]}{_{f}}](../Images/9a2d7b08ed81ad58f1c456cf14fa768c78c45e3e.png). The overall `mp3` encoding and playback pipeline can be described as a sequence of transformations:

![\underbrace{ \!
[\texttt{song}^\prime]_{t} = 
\!\tensor[_{t}]{\left[\mathbbm{1}\right]}{_{f}}
\!\!}_{\texttt{mp3} \textrm{ playback}}
\; 
\underbrace{ \!
\!\tensor[_{f}]{\left[\Pi\right]}{_{f}}
\!\tensor[_{f}]{\left[\mathbbm{1}\right]}{_{t}} \! 
[\texttt{song}]_{t}.
\!\!}_{\texttt{mp3} \textrm{ encoding}}](../Images/84e802328911a116e64558cfc3cade9af1b2f914.png)

Note we’re modelling the `mp3` pipeline using standard matrix-vector products, so the sound information flows from right to left in the above equation. First we use the Fourier transform, denoted ![\!\tensor[_{f}]{\left[\mathbbm{1}\right]}{_{t}}](../Images/e4d82bc868d55dd9206a11e8f9e32e02f851d7d8.png), to transform the song from the time-basis to the frequency-basis, where the psychoacoustic projection ![\!\tensor[_{f}]{\left[\Pi\right]}{_{f}}](../Images/9a2d7b08ed81ad58f1c456cf14fa768c78c45e3e.png) is applied. An `mp3` file is the frequency-domain representation of the song after applying the projection: ![[\texttt{song}^\prime]_{f} = \!\tensor[_{f}]{\left[\Pi\right]}{_{f}}
\!\tensor[_{f}]{\left[\mathbbm{1}\right]}{_{t}} \! 
[\texttt{song}]_{t}](../Images/9aa8bf7283c9a994b0d5aa22b39a9e070dc3e0fa.png). Compression ratios up to a factor of 10 can be achieved using this approach: a ![50](./images/2b10670a50c0a575208a1161c74c474f9d35032c.png) MB `wav` file can be compressed to a ![5](./images/0a99a11a8db1514f59b81b2211782467dd4a2e74.png) MB `mp3` file. During playback, the inverse change of basis, ![\!\tensor[_{t}]{\left[\mathbbm{1}\right]}{_{f}}](../Images/8eec38660e8e098f3f9ee02a35bd2f4e45274666.png), transforms the song from the frequency-basis back to the time-basis.

Obviously some level of sound degradation occurs in this process, and the song you hear during playback ![[\texttt{song}^\prime]_{t}](../Images/5848a5d655f569548e1bc176acb95da089257951.png) sounds different from the original ![[\texttt{song}]_{t}](../Images/1b5d5fff3715b19321abdd6939e46c61afed05eb.png). If good models of human hearing are used, the differences should be mostly imperceptible. Crucial to the `mp3` encoding process, the psychoacoustic models are applied in the frequency domain. This is an example of the Fourier transform acting as a building block for a more complex procedure.

###[Discussion](./Front matter.md)

In this section we learned about three different Fourier transformations: the Fourier series, the Fourier transform, and the discrete Fourier transform. All the scary-looking formulas we saw can be understood as special cases of the same idea: Fourier transformations are change-of-basis operations between a time basis and a frequency basis, which consists of orthogonal functions of the form ![e^{i\omega t}](./images/86361ad2c78fb3405a65fdad79513e67dae80d4c.png).

It may seem like the Fourier series, with its sine and cosine terms, is a different kind of beast; but it only looks different until you recall Euler’s formula, ![e^{i\theta} = \cos\theta + i \sin \theta](./images/e121a20685ffac97d746ced075400d22165d332d.png) (see page 1.14.2.6). Using Euler’s formula, we can express the Fourier series of a function as a sequence of complex coefficients ![c_n \in \mathbb{C}](./images/068a8e6c1b7738afd2427dc154e874afcb41b347.png) that contain the combined information of both cosine- and sine-like components of a periodic signal ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png). The complex Fourier coefficients ![c_n](./images/ff1f41a02a2323e2f2e0e7fc04893e07d826df08.png) are obtained using the formula

![c_n
= \int_0^T 
\left\langle e^{i\frac{2\pi n}{T}t}, \mathbf{e}_t \right\rangle
f(t)
\,dt
= \frac{1}{T}\int_0^T
e^{-i\frac{2\pi n}{T}t}
f(t)
\,dt.](./images/2a0dd798ad9201a631a1ff04631cad9296341615.png)

Problem [7.12](./Chapter 7_ Applications.md) will ask you to verify the connection between the Fourier series of complex exponentials and the Fourier series of sines and cosines.

The Fourier change of basis is a general principle that can be applied in many contexts. All the transforms we discussed in this section use the family of orthogonal functions ![e^{i\omega t}](./images/86361ad2c78fb3405a65fdad79513e67dae80d4c.png), but there are other sets of orthogonal functions that can serve as alternate bases for different applications. To mention a few, we have the Bessel functions ![J_\lambda](./images/3d3860ba4b43576356cdc454d776bc242dfb3d62.png), the spherical harmonics ![Y_{mn}(\theta,\psi)](./images/377da6ed7b306f344aff20fcaa5fb869254f787c.png), the Legendre polynomials ![P_n(x)](./images/064ff86501dba020964c53718619fda009a33f0f.png), the Hermite polynomials ![H_n(x)](./images/e5ea9083a600a3df2484ada87ba27dc5a07e8a36.png), and the Laguerre polynomials ![L_n(x)](./images/30c4f0de6432458382dd766029e78203dd4a581b.png). All these families of functions form orthogonal sets on different intervals with respect to different inner products.

###[Links](./Front matter.md)

\[ Visualizations of Fourier synthesis of a square wave signal \]

[`http://codepen.io/anon/pen/jPGJMK/`](./jPGJMK.md)

[`http://bgrawi.com/Fourier-Visualizations/`](./Fourier-Visualizations.md)

\[ Excellent video tutorial about digital audio processing \]

[`http://xiph.org/video/vid2.shtml`](./vid2.shtml.md)

\[ Website with animations that explain signal processing concepts \]

[`http://jackschaedler.github.io/circles-sines-signals/`](./circles-sines-signals.md)

\[ A nice discussion on math.stackexchange.com \]

[`https://math.stackexchange.com/questions/1002/`](./fourier-transform-for-dummies.md)

\[ Wikipedia pages of the three Fourier transforms we described \]

[`https://en.wikipedia.org/wiki/Fourier_series`](./Fourier_series.md)

[`https://en.wikipedia.org/wiki/Fourier_transform`](./Fourier_transform.md)

[`https://en.wikipedia.org/wiki/Discrete_Fourier_transform`](./Discrete_Fourier_transform.md)

\[ Orthogonal polynomials and generalized Fourier series \]

[`http://math24.net/orthogonal-polynomials.html`](./orthogonal-polynomials.md)

###[Exercises](./Front matter.md)

E7.17 Recall the functions ![\mathbf{e}_n(x) = \sin(\tfrac{n\pi}{L}x)](./images/bf2c8c332f87c075e2d53811204a69234464132e.png) that can be used to describe all vibrations of a guitar string of length ![L](./images/8344682567e06566040f4cde165f91b06c4ee6f5.png). Verify that ![\mathbf{e}_1(x)](./images/c834efe57f7221eda70b7cbf75bb92ca08ee0e3f.png) and ![\mathbf{e}_2(x)](./images/4676a5867d9308a1ce1898a6b3155bf504567c5d.png) are orthogonal functions by computing the inner product ![\langle \mathbf{e}_1(x), \mathbf{e}_2(x) \rangle](./images/34d772e74d9732f1b9d431698032a795d8a30c7d.png). Use the inner product definition from page 7.11.2.

You might find the double-angle formula from page 1.12.1.1 useful.

E7.18 Explain why the Fourier series ![(a_0, a_1, b_1, a_2, b_2, \ldots)](./images/852c120e01e3f475ccda8bda8566c862a27c423d.png) of a periodic function ![f(t)](./images/01d9a833a72a1a0c3ed234817373e8e92a8223b4.png) contains a coefficient ![a_0](./images/e5f45f608555f355964666e0369b21e1a495aa85.png) but not a coefficient ![b_0](./images/93e61cd3c2eeea8ea1cc21aa36c388dc06f0d705.png).

##[Discussion](./Front matter.md)

We’ve only scratched the surface of all the possible problem domains that can be modelled using linear algebra. The topics covered in this chapter are a small sample of the range of scientific, computing, and business activities that benefit from the use of matrix methods and understanding of vector spaces. Linear algebra allows you to perform complex numerical procedures using a high level of abstraction.

Normally, a linear algebra class should end here. We’ve covered all the information you need to know about vectors, matrices, linear transformations, and vector spaces; and also discussed several applications. Feel free to close this book now, content that your valiant effort to learn linear algebra is done. But perhaps you’d like to learn some further topics and make use of your linear algebra skills? If this sounds interesting, I encourage you to keep reading, as there are two more chapters of cool “optional material” ahead.

[Chapter 8](./Chapter 8_ Probability theory.md) covers the basics of probability theory, Markov chains, and the idea behind Google’s PageRank algorithm for classifying web pages. Probability theory is not directly related to linear algebra, but the applications we’ll discuss make heavy use of linear algebra concepts.

The laws of quantum mechanics govern physics phenomena at the femto-scale—think individual atoms. It’s a common misconception to assume quantum laws are somehow mysterious or counterintuitive, and that perhaps they can only be understood by people with a solid math background.[Chapter 9](./Chapter 9_ Quantum mechanics.md) contains a concise introduction to the principles of quantum mechanics specifically tailored to people who know linear algebra. The material is adapted from lectures the author prepared for a graduate-level introductory course, so there will be no dumbing down or oversimplification. With your background in linear algebra, you can handle the real stuff.

##[More linear algebra applications](./Front matter.md)

You’ll find the following resources useful if you want to learn more about linear algebra applications.

\[ Three compilations of linear algebra applications \]

[`http://aix1.uottawa.ca/~jkhoury/app.htm`](./Chapter 7_ Applications.md)

[`https://medium.com/@jeremyjkun/633383d4153f`](./here-s-just-a-fraction-of-what-you-can-do-with-linear-algebra-633383d4153f.md)

[`http://people.math.harvard.edu/~knill/teaching/math21b2018/handouts/use.pdf`](./use.pdf.md)

\[ A document that describes many applications in detail \]

[`http://www.geverstine.com/reprints/Everstine_linearalgebra.pdf`](./Everstine_linearalgebra.pdf.md)

\[ 33 miniatures: algorithmic applications of linear algebra \]

[`http://kam.mff.cuni.cz/~matousek/stml-53-matousek-1.pdf`](./stml-53-matousek-1.pdf.md)

\[ A book about linear algebra applications to data science \]

[`http://amazon.com/Data-Science-from-Scratch/dp/149190142X`](./149190142X.md)

##[7.12 Applications problems](./Chapter 7_ Applications.md)

It would be easy to think of all the applications of linear algebra presented in this chapter as a TV program, designed to entertain rather than teach. Certainly you can continue to the next chapter without solving any problems, but do you really want to do that to yourself?

Presented next are a number of practice problems that will test your understanding of the new concepts and give you a great opportunity to practice your linear algebra skills. The linear algebra techniques we learned in previous chapters are key building blocks for applications. So don’t sit on your laurels thinking, “Yay, I’m in[Chapter 7](./Chapter 7_ Applications.md) and I know linear algebra now, I’m so good.” Prove it.

P7.1 Consider the following chemical equation that describes how your body burns fat molecules: ![\textrm{C}_{55}\textrm{H}_{104}\textrm{O}_6 + \textrm{O}_2 \; \to \; \textrm{C}\textrm{O}_2 + \textrm{H}_2\textrm{O}](./images/12ee4075d69a66c50984ff13c16bf812bc18cfc7.png). Balance this chemical equation.

P7.2 Check out this circuit containing two batteries and five resistors:

![problem_one](./images/problem_one.png)

1.  Label the polarity of each resistor in the circuit.
2.  Write three KVL equations and two KCL equations.
3.  Rewrite the equations in the form ![R\vec{I} = \vec{V}](./images/8c847f6f5c06d41932c186de1ee082bc0480bca1.png), where ![R](./images/7b4484a7475e142eef700c7c304d9eb49269263e.png) is a ![5\times 5](./images/24160aefb8daffd776f0a21c6fa2e33301711b68.png) matrix, ![\vec{I} = (I_1,I_2,I_3,I_4,I_5)^\sfT](./images/7d5b9f4de6eae06542a6b7b424eb9f9f02478fdb.png), and ![\vec{V}](./images/e6df6f3bfa361e4dca3985c320cd7a54a2ce2f76.png) is a vector of constants.
4.  Find the value of the currents ![I_1](./images/92b15d8292cfa5116e8f3eb166bcedcc5e91c000.png) and ![I_5](./images/c1aacc7e99ec9abf09b9a74d9acf9629859916d2.png) given ![V_1=15](./images/3d9947ba584c6d96841d309849785187e5a006ae.png)\[V\], ![V_2=10](./images/e3cb8625ef05f981b70d8da218a005fb7828edc9.png)\[V\], ![R_1=1](./images/7c5aac914c6e6b85d607af8ae70bf95b1a66d886.png)[![\Omega](./d5866e1c589aab7c68e0f7b1fab3b2274cf5d5a0.png.md)\], ![R_2=1](./images/293548521c4a3f14394555269df425640ff52488.png)[![\Omega](./d5866e1c589aab7c68e0f7b1fab3b2274cf5d5a0.png.md)\], ![R_3=4](./images/53f0f0f05cf2c87a715700e2aff91c0099c6023b.png)[![\Omega](./d5866e1c589aab7c68e0f7b1fab3b2274cf5d5a0.png.md)\], ![R_4=2](./images/a2015a554df0715eb75704db97be963aac92f456.png)[![\Omega](./d5866e1c589aab7c68e0f7b1fab3b2274cf5d5a0.png.md)\], ![R_5=2](./images/19e42069aeb4f1073532d3c7810d37889badc6cb.png)[![\Omega](./d5866e1c589aab7c68e0f7b1fab3b2274cf5d5a0.png.md)\].

The direction of the voltage drop across a resistor depends on the direction of the current flowing through it.

P7.3 Given the ![(x,y)](./images/324023387152cfd89accc75830ebc0a994eed8aa.png) pairs ![(0,0.9)](./images/25fa1ca6a48cd582235122670e62dd13980ad0ab.png), ![(1,1.6)](./images/8fd93f8bd814a49ee6693591a24e1d9bb957ca5d.png), ![(2,2.1)](./images/8b6d6441b3a39f24f49dea145b375bcd8269e97f.png), and ![(3,2.4)](./images/4c383ac1068d7593a7c4506e33a56400aef0c735.png), find the best-fitting affine model ![y = b + mx](./images/389d6078ad148f4059e8ce6cc51728f135db1de1.png) for this data.

Find the Moore–Penrose inverse.

P7.4 You just moved to a new city and you’re looking for a new place to live. To get an idea of the rent prices per square foot, you check out the classifieds and find the following offers: a 200 sq ft mini-studio for $500, a 300 sq ft studio for $620, a 400 sq ft small apartment for $750, a 500 sq ft one bedroom condo for $890, a 900 sq ft two bedroom aparment for $1250, and a 1000 sq ft apartment for $1300. Find the best-fitting curve ![p(x) = b+ mx](./images/299c51657a05df5ae2d3b210bbbbf4d55efddb5b.png) to the above data, where ![p(x)](./images/5f059c6777903c2fb291453bf05fca5ffd7e1e28.png) represents the price for ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) square feet. What is the estimated price for a 700 sq ft apartment?

Use a computer algebra system like `SymPy` for the calculations. To get you started, I set up the problem data here:[`bit.ly/apt_rent_data`](./apt_rent_data.md).

P7.5 Redo [7.12](./Chapter 7_ Applications.md), but this time find the best-fitting quadratic model ![q(x) = c + bx + ax^2](./images/e4cd6a08b75d74b3193b1967690624269d58cc33.png) for the price per square foot. What is the estimated price for a 700 sq ft apartment predicted by the quadratic model?

After preprocessing, the data matrix must have three columns.

P7.6 Describe the possible types of solutions to the equation ![A\vec{x}=\vec{b}](./images/95849f99b4d26d5bf968a0354ed239c51f5fb9aa.png), where ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is an ![m\times n](./images/db64f3a4b45f481733f89912bcb47c0179ce9042.png) matrix. Discuss the following three cases: when ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is wide (![m < n](./images/d2a302f0cce8c1ddf0f917ae19b2eb33bc4f93db.png)), when ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is square (![m=n](./images/eee7c3eb817438e5e82f7b6201ff7d82f4e43306.png)), and when ![A](./images/01826656709ba3d8fa0e488ce874b9fc14b5964d.png) is tall (![m >n](./images/2d07c7bc0a3d85fd2a9f187450303ee2091adf7e.png)).

Describe the column space, row space, and null space of the matrix.

P7.7 Find the adjacency matrix representation of the following graphs:

1.  ![graph_problem_a](./images/graph_problem_a.png)
2.  ![graph_problem_b](./images/graph_problem_b.png)
3.  ![graph_problem_c](./images/graph_problem_c.png)

P7.8 For each of the graphs in [7.12](./Chapter 7_ Applications.md), find the number of ways to get from vertex ![1](./images/2afc353cf06912c08c45250ec61b4dba1bf1263a.png) to vertex ![3](./images/b6031d121f1b4a4b138ae89b9919d5b4c8ebf35b.png) in two steps or less.

Obtain the answer by inspection or by looking at the appropriate entry of the matrix ![\mathbbm{1} + A + A^2](./images/33ac83443d2224813b3a363a948f52dfb7c06734.png).

P7.9 Draw the graphs that correspond to these adjacency matrices:

      1.                     ![A = \begin{bmatrix}
    0 & 1 & 1 & 0 \\ 
    1 & 0 & 0 & 0 \\
    0 & 1 & 0 & 1 \\
    1 & 0 & 1 & 0
    \end{bmatrix}](./images/af843f51017a9972e04ff5e18c206783da2c41b4.png)
2.  ![A = \begin{bmatrix}
    1 & 1 & 0 & 0 & 1 & 0 \\
    0 & 0 & 1 & 0 & 0 & 0 \\
    0 & 1 & 0 & 0 & 0 & 1 \\
    1 & 1 & 0 & 0 & 0 & 0 \\
    0 & 0 & 0 & 1 & 0 & 0 \\
    0 & 0 & 0 & 0 & 1 & 0
    \end{bmatrix}](./images/34345a6e66f73c689a4c7351de265ccf5af77a56.png)

P7.10 Find the homogeneous coordinates representations of each of the transformations shown in[Figure 7.20](./Front matter.md). The input to each transformation is the triangle with vertices ![(0,0)](./images/88f092814c075b14ae3942f62ed4da42f8321ec0.png), ![(2,0)](./images/40b6f6b8547473b2b37962617c356013005335ce.png), ![(0,1)](./images/e69b48bc6687ee74a843dea90543682e53e069e3.png) shown in[Figure 7.20](./Front matter.md) (a).

Your answers should be ![3\times 3](./images/6b8fffad37df383e49f7fa3e644f60b34c970097.png) matrices. Recall that ![\sin(\frac{\pi}{6})=\frac{1}{2}](./images/a46e9aad99287dfa646e0c3e59a931d5d27c691e.png).

![transformations_problem_linear](./images/transformations_problem_linear.png)

Figure 7.20

P7.11 Find the homogeneous coordinates representations of each of the transformations shown in[Figure 7.21](./Front matter.md). The input to each transformation is the triangle with vertices ![(0,0)](./images/88f092814c075b14ae3942f62ed4da42f8321ec0.png), ![(2,1)](./images/6c3526e46dd1ffcf346c0da3c6c817d44737c250.png), ![(0,1)](./images/e69b48bc6687ee74a843dea90543682e53e069e3.png) shown in[Figure 7.20](./Front matter.md) (a).

Use your answers from parts (b) and (d) to answer parts (e) and (f).

![transformations_problem_affine](./images/transformations_problem_affine.png)

Figure 7.21

P7.12 Find the homogeneous coordinates representation of the perspective transformation illustrated in the following figure. The observer is located at the origin ![(0,0)](./images/88f092814c075b14ae3942f62ed4da42f8321ec0.png) and the projection line is given by the equation ![2x+y=2](./images/408a31ada77c8f3a838b26206e0277c1d1232969.png).

         ![projection_question_2d](./images/projection_question_2d.png)

Use the matrix to find the coordinates of the projected points ![p^\prime](./images/ffbfef6e0b5dc6ec30fa1b757ed6217e89e689d1.png) and ![q^\prime](./images/81493b4c4ce833e3b6b0e702935a37b6b528aa41.png).

P7.13 Alice and Bob share the key ![\vec{k}=10010111\;01010011\;10011110](./images/d2da7f585ddeab2fff986cc49688cdd72737e941.png). Bob receives the ciphertext ![\vec{c} = 11100100\;00100110\;11101110](./images/142cc9f3520236d962b0fedc1ab852a11fa9ef88.png) sent by Alice. What is the message sent by Alice? Find an[ASCII lookup table](./binary-to-ascii-text-converter.md) on the web and use it to convert the binary message into characters.

P7.14 Consider the signal ![f(t)](./images/5efd00e5bf3a607572430909c72c6a99d7761528.png) that is periodic with period ![T](./images/40f04b10ffbd1510173e7d6ad51829f2b04ff884.png). The coefficients of the Fourier series with complex coefficients are defined using the formula

![c_n
=
\int_0^T	\left\langle e^{i\frac{2\pi n}{T}t}, \mathbf{e}_t \right\rangle f(t) \,dt
=
\frac{1}{T}\int_0^T f(t)e^{-i\frac{2\pi n}{T}t}\,dt.](./images/f8e1c49ebc6a9289881a5e7d15afeba458051d68.png)

Show that ![c_n = a_n - ib_n](./images/3d68dd8e2e2d74586729a6291342d44385958b7a.png), where ![a_n](./images/af7b3d3ed5dbdda80e11d68e014374fad67aa4b5.png) and ![b_n](./images/15d33d27d1a8b0f1ca293314ec8bf1336bc5a59e.png) are the coefficients of the regular Fourier series for ![f(t)](./images/5efd00e5bf3a607572430909c72c6a99d7761528.png) defined in terms of cosines and sines.

Obtain the real and imaginary parts of ![c_n](./images/05e590752bb6df58b74984eb3f7340a3b4db8f4d.png) using Euler’s formula.

P7.15 Find the Fourier transform of the function ![f(t)=e^{-\frac{t^2}{2\sigma^2}}](./images/0d3a8545f11a2536eb57124d1038fc2d909adc67.png).

Use the complete-the-square technique from page 1.5.4, and remove from the exponent a factor that does not contain ![t](./images/e393328f63600775ab7376c9b4fc411c9b60340a.png). The change of variable ![t^\prime = t+\sigma^2 i \omega](./images/0a2dcc60863fe7362bebb1d224f9c03722b926f7.png) might also come in handy. Recall ![\int_{-\infty}^{\infty} e^{-\frac{x^2}{2\sigma^2}}\,dx=\sqrt{2\pi}\sigma](./images/e17fde0744205b5339bbb5f3a66e532bbc72a6ef.png).

P7.16 Find the Fourier transform of the function ![f(t)=e^{-|at|}](./images/e55fdc142f465094af98fdc365bddd20671a3fb7.png).

Split ![e^{-i\omega t}](./images/5e63ab292c0b780cd448acce035ec67277839a4b.png) into sine and cosine terms and use symmetry to convert the two-sided integral ![\int_{-\infty}^{\infty} \cdots dt](./images/760171124bae13bcb67e7344528b9f746d2c050c.png) into a one-sided integral ![\int_{0}^{\infty}\cdots dt](./images/5a5dddcda282234060027d0a7b7e6363bb06027f.png).

P7.17 Consider the function ![f(t)](./images/5efd00e5bf3a607572430909c72c6a99d7761528.png), which has Fourier transform ![f(\omega)](./images/c80b9e827d00011fc8ea63776be98c78925cb7df.png). Find the Fourier transform of the function’s derivative ![f'(t)](./images/9b58e0c2a2e96cc20acf4fe72be8827b47f716af.png), and express your answer in terms of ![f(\omega)](./images/c80b9e827d00011fc8ea63776be98c78925cb7df.png).

Start from the formula for ![f(t)](./images/5efd00e5bf3a607572430909c72c6a99d7761528.png) in[equation 7.18](./Chapter 7_ Applications.md) on page 7.18.

[1.](./Front matter.md) The voltage coming out of wall outlets is actually not a constant 110\[V\] but a sine-wave oscillating between ![+155](./images/e615a11684d888a783d9c5243be810c0ca4c7590.png)\[V\] and ![-155](./images/40fe8b9214cbf60473bcb3716c808671cf93b81c.png)\[V\], but in this example we’ll treat the socket’s output as a constant voltage of ![110](./images/bd907740c24f341abfc5af0db07b1c9ce88d4c2c.png)\[V\].

[2.](./Front matter.md) You can learn more about the physics of standing waves from this tutorial:[`http://www.phy.duke.edu/~rgb/Class/phy51/phy51/node34.html`](./node34.md).
