Chapter 9      

#[Chapter 9 Quantum mechanics](./Chapter 9_ Quantum mechanics.md)

By the end of the 19th century, physicists thought they had figured out most of what there is to know about the laws of nature. Newton’s laws of mechanics described the motion of objects in space, and Maxwell’s equations described electricity and magnetism. Wave phenomena—including the propagation of sound, light, and waves on the surface of liquids—were also well understood. Only a few small inconsistencies between theory and experiments with atoms and radiation remained unsolved.

> “\[ …\] it seems probable that most of the grand underlying principles have now been firmly established and that further advances are to be sought chiefly in the rigorous application of these principles to all the phenomena which come under our notice.” — Albert A. Michelson in 1894

Physicists like Michelson were worried about the future of physics research. It was as if they were wondering, “What are we going to do now that we’ve figured everything out?” Little did they know about the quantum storm that was about to hit physics, and with it, the complete rewrite of our understanding of nature at the smallest scale.

Understanding the structure of atoms—the smallest constituents of matter known at the time—was no trivial task. Describing the absorption of electromagnetic radiation by metals also turned out to be quite complicated. In both cases, the physical theories of the time predicted that the energy of physical systems could take on any value; yet experimental observations showed _discrete_ energy levels. Imagine you throw a (very-very tiny) ball, and the laws of physics force you to choose an initial velocity for the ball from a list of “allowed” values: ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) m/s, ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) m/s, ![2](./images/3912d9ef84ab62f113906709343efc5fe27b608c.png) m/s, ![3](./images/eb50992782ed0e8025a72f499ad64c3f67b484f3.png) m/s, and so forth. That would be weird, no? Weird indeed, and this is the situation physicists were facing in the beginning of the 20th century: their theories described the energy levels of atoms as real numbers ![E \in \mathbb{R}](./images/58ac86cf337825c5c55424e02299a1137e07a28b.png), but experiments showed that only a discrete set of energy levels exist. For example, the energy levels that the electrons of the hydrogen atom can take on are:

![\begin{align*}
E \in \{ \; 
& 	21.8\!\times\!10^{-19}\,\textrm{J},\; 
5.44\!\times\!10^{-19}\,\textrm{J},\; 
2.42\!\times\!10^{-19}\,\textrm{J},\; 			\\
& 
13.6\!\times\!10^{-20}\,\textrm{J},\; 
8.71\!\times\!10^{-20}\,\textrm{J},\; 
6.05\!\times\!10^{-20}\,\textrm{J}, \; \ldots \; \}.
\end{align*}](./images/563c5712ac1d3b4fa035e01fa3a45b4f5e5cbc03.png)

Other experimental observations suggested that electromagnetic radiation is not a continuous wave, but comes in discrete “wave packets,” which we call _photons_ today. The theory of _quantum mechanics_ was born out of a need to explain these observations. The term _quantum_, from the Latin _quantus_ for quantity, was coined to describe the discrete nature of the phenomena that physicists were trying to explain.

During the first half of the 20th century, in experiment after experiment, quantum principles were used to correctly predict many previously-unexplained observations. During the second half of the 20th century, biologists, chemists, engineers, and physicists applied quantum principles to all areas of science. This process of “upgrading” classical models to quantum models led to a better understanding of the laws of nature, and the discovery of useful things like transistors and lasers.

The fundamental principles of quantum mechanics can be explained in the space on the back of an envelope. Understanding quantum mechanics is a matter of combining a little knowledge of linear algebra (vectors, inner products, projections) with some probability theory [Chapter 8](./Chapter 8_ Probability theory.md)). In this chapter, we’ll take a little excursion to the land of physics to learn about the ideas of great scientists like Bohr, Planck, Dirac, Heisenberg, and Pauli. Your linear algebra skills will allow you to learn about some fascinating 20th\-century discoveries. This chapter is totally optional reading, reserved for readers who _insist_ on learning about the quantum world. If you’re not interested in quantum mechanics, it’s okay to skip this chapter, but I recommend you check out[Section 9.1.4](./Chapter 9_ Quantum mechanics.md) on _Dirac notation_ for vectors and matrices. Learning Dirac notation serves as an excellent review of the core concepts of linear algebra.

sec-quantum\_mechanics\_introduction

The principles of quantum mechanics have far-reaching implications for many areas of science: physics, chemistry, biology, engineering, philosophy, and many other fields of study. Each field of study has its own view on quantum mechanics, and has developed a specialized language for describing quantum concepts. We’ll formally introduce the postulates of quantum mechanics in[Section 9.3](./Chapter 9_ Quantum mechanics.md), but before we get there, let’s look at some of the disciplines where quantum principles are used.

#####[Physics](./Front matter.md)

Physicists use the laws of quantum mechanics as a toolbox to understand and predict the outcomes of atomic-scale physics experiments. By “upgrading” classical physics models to reflect the ideas of quantum mechanics, physicists (and chemists) obtain more accurate models that lead to better predictions.

For example, in a _classical_ physics model, the motion of a particle is described by its position ![x(t)](./images/806ead86db9381928f7a352b6d1b96dd68fd53df.png) and velocity ![v(t)](./images/412b88636f53d835235ee79f132529c86bef14d0.png) as functions of time:

![\textrm{classical state} = (x(t), v(t)), \textrm{ for all times } t.](./images/9da38c593bbd2f687c44ae79538f0e96f9338227.png)

At any given time ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png), the particle is at position ![x(t)](./images/806ead86db9381928f7a352b6d1b96dd68fd53df.png) and moving with velocity ![v(t)](./images/412b88636f53d835235ee79f132529c86bef14d0.png). Using Newton’s laws of motion and calculus, we can predict the position and the velocity of a particle at all times.

In a quantum description of the motion of a particle in one dimension, the state of a particle is represented by a _wave function_ ![\ket{\psi(x,t)}](./images/d3c67784e6da5d00a7d7ec9fec78eb620022ce08.png), which is a complex-valued function of position ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) and time ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png):

![\textrm{quantum state}=\ket{\psi(x,t) }, \textrm{ for all times } t. \quad](./images/11649ab79bf291f9cb85809cb9234103a3528c24.png)

At any given time ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png), the state of the particle corresponds to a complex-valued function of a real variable ![\ket{\psi(x)}   \in \{\mathbb{R} \to \mathbb{C}\}](./images/49f07d0b24dcccc375e8f54b35769d3bb6c35e76.png). The wave function ![\ket{\psi(x)}](./images/5a9452e15f5657cb77e94226095a32d7ccf376b4.png) is also called the _probability-amplitude_ function. The probability of finding the particle at position ![x_a](./images/cc4541af003aa07ba7a9c30895c8078b7be3e5e3.png) is proportional to the value of the squared norm of the wave function:

![\textrm{Pr}\!\left(  \{ \textrm{particle position} = x_a \}  \right)
\quad 
\propto
\quad 
\big| \ket{\psi(x_a)} \big|^2.](./images/be67432a6b92ac8be961aef29d102b2d8fa99d37.png)

Instead of having a definite position ![x(t)](./images/806ead86db9381928f7a352b6d1b96dd68fd53df.png) as in the classical model, the position of the particle in a quantum model is described by a probability distribution calculated from its wave function ![\ket{\psi(x)}](./images/5a9452e15f5657cb77e94226095a32d7ccf376b4.png). Instead of having a definite momentum ![p(t)](./images/ddd8457f0ce2ff776fdb7d0c401e88b28a980cd2.png), the momentum of a quantum particle is another function calculated based on its wave function ![\ket{\psi(x)}](./images/5a9452e15f5657cb77e94226095a32d7ccf376b4.png).

Classical models provide accurate predictions for physics problems involving macroscopic objects, but fail to predict the physics of atomic-scale phenomena. Much of 20th\-century physics research efforts were dedicated to the study of quantum concepts like ground states, measurements, spin angular momentum, polarization, uncertainty, entanglement, and non-locality.

#####[Computer science](./Front matter.md)

Computer scientists understand quantum mechanics using principles of information. Quantum principles impose a fundamental change to the “data types” used to represent information. Classical information is represented as _bits_, elements of the finite field of size two ![\mathbb{Z}_2](./images/8309b94e2344e9e2d19570a1d099e55eb33b8e0d.png):

![\textrm{bit: } x = 0 \; \;  \textrm{or} \; \; x=1.](./images/996b208a4a04af28e240f01d58742477ff3a4cc4.png)

In the quantum world, the fundamental unit of information is the _qubit_, which is a two-dimensional unit vector in a complex inner product space:

![\textrm{qubit: } \ket{x} = \alpha\ket{0} +\beta\ket{1}.](./images/03fcce1d5cc68e95f4591a940b6319259f8844c3.png)

This change to the underlying information model requires reconsidering fundamental information processing tasks like computation, data compression, encryption, and communication.

#####[Philosophy](./Front matter.md)

Philosophers have also updated their conceptions of the world to incorporate the laws of quantum mechanics. Observations of physics experiments forced them to reconsider the fundamental question, “What are things made of?” Another interesting question philosophers have considered is whether the quantum state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) of a physical system really exists, or if ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) is a representation of our knowledge about the system.

A third central philosophy concept that quantum mechanics calls into question is _determinism_—the clockwork-model of the universe, where each effect has a cause we can trace, like the connections between gears in a mechanical clock. The laws of physics tell us that the next state of the universe is determined by the current state of the universe, and the state changes according to the equations of physics. However, representing the universe as a quantum state has implications for our understanding of how the universe “ticks.” Clockwork (deterministic) models of the universe are not wrong—they just require a quantum upgrade.

Many scientists are also interested in the philosophical aspects of quantum mechanics. Physicists call these types of questions _foundations_ or _interpretations_. Since different philosophical interpretations of quantum phenomena cannot be tested experimentally, these questions are considered outside the scope of physics research. Nevertheless, these questions are so deep and fascinating that physicists continue to pursue them, and contribute interesting philosophical work.

\[ Philosophical issues in quantum theory \]

[`http://plato.stanford.edu/entries/qt-issues/`](./qt-issues.md)

###[Physical models of the world](./Front matter.md)

We’ll situate our discussion of quantum mechanics within two conceptual worlds:

-   The **real world** is where physical experiments are performed.
-   The **mathematical world** is a purely theoretical construct that aims to model certain aspects of the real world.

The better the mathematical model, the more closely its predictions correspond to the behaviour of real-world systems. Sill, no math or physics model can ever predict real-world outcomes with 100% accuracy. When we say that a certain mathematical model is better than another, we mean it can predict the outcomes of controlled experiments with greater accuracy. Physicists are very open to new theories—anyone can be a physicist! You can start by constructing any crazy mathematical model for describing nature, and if your model correctly predicts the outcomes of experiments, other physicists will start using it.

We can make a further distinction among mathematical models, classifying them into two categories depending on the type of math they use:

-   **Classical models** describe the world in terms of real variables like positions and velocities.
-   **Quantum models** describe systems in terms of vectors in complex vector spaces.

[Table 9.1](./Chapter 9_ Quantum mechanics.md) compares the objects used in the two types of mathematical models of the real world. In physics, classical models describe the motion of particles using trajectories ![\vec{r}(t)](./images/50cbc8f8ef8d9bf619ffab9c69458d45f40e8872.png), whereas quantum models use wave functions ![\ket{\psi(\vec{r},t)}](./images/eca308dc39b3ed0f4d0f6133d811cb4571f708ee.png). In computer science, classical information is stored in bits ![i \in \{0,1\}](./images/5d9968b7ba103a6ea09daa3a81da65628b09001c.png), whereas quantum information is stored in qubits ![\ket{x} \in \mathbb{C}^2](./images/ec8e1cf4159421e09cad9b2025f11c3e43dfadb5.png).

**Real world:**

-   The motion of a ball thrown in the air
-   The motion of an electron through space
-   The paths of light particles moving through optical circuits
-   The electric current flowing though a superconducting loop

**Classical models:**

-   ![x(t) \in \{\mathbb{R} \to \mathbb{R} \}](./images/4813936d669740b58b17af38eef70e3a33f4dff6.png)
-   ![\vec{r}(t) \in \{ \mathbb{R} \to \mathbb{R}^3 \}](./images/8312ee523183c8beb9871f6c07a8321d623902d1.png)
-   ![i \in \mathbb{Z}_2 = \{0,1\}](./images/9d0ec249439fa82162b5630e51c0a51c762bfba3.png) (a bit)
-   ![j \in \mathbb{Z}_d](./images/2ae9e843fc78198f38d00aead7c894fc0afd8031.png)
    

**Quantum models:**

-   ![\ket{\psi(x,t)} \in \{ \mathbb{R} \times \mathbb{R} \to \mathbb{C} \}](./images/7fd4fe4edd59a3cfc473142a76c2a7f4fed9aa00.png)
-   ![\ket{\psi(\vec{r},t)} \in \{ \mathbb{R}^3 \times \mathbb{R} \to \mathbb{C} \}](./images/bb4b0e961c124c90440707f669591567e9248509.png)
-   ![\ket{x} \in \mathbb{C}^2](./images/ec8e1cf4159421e09cad9b2025f11c3e43dfadb5.png) (a qubit)
-   ![\ket{y} \in \mathbb{C}^d](./images/4dffa476f5939a93c2c5298b37a62552a28745bc.png)

Table 9.1: Examples of the math used in classical and quantum models.

#####[Example](./Front matter.md)

Let’s analyze the difference between classical and quantum models of the real world using an example. Consider a photon (a particle of light) going through an optical circuit that consists of several lenses, mirrors, and other optical instruments. A photon detector is placed at position ![x_f](./images/2c2f131c9928c3956cf3809de674dff6247fc9fc.png) at the end of the circuit. The objective of the experiment is to predict if the photon will arrive at the detector and cause it to “click.” The two possible outcomes of the experiment are `click` (photon arrives at detector) or `noclick` (photon doesn’t arrive at detector)[1](./Front matter.md)

A classical model of the motion of the photon calculates the photon’s position at all times ![x(t)](./images/806ead86db9381928f7a352b6d1b96dd68fd53df.png) and leads to the prediction ![i=1](./images/0cdd115824c03900b3a5548ae67f149cf80cea7a.png) (`click`) if ![x_f = x(t)](./images/8b89d88859b8d7c30f5c57c53313905fd8a28f2b.png), for some ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png). On the other hand, if the detector does not lie on the photon’s trajectory, then the classical model will predict ![i=0](./images/2bc58078382ddad0945f1ab62ffe3ba749469da6.png) (`noclick`).

A quantum model would describe the photon’s trajectory through the circuit as a linear combination of two different possible paths:

![\ket{\psi}	 = 	\alpha \ket{0}  + \beta \ket{1} 
\quad \textrm{where} \; \; 
|\alpha|^2 + |\beta|^2 = 1.](./images/f960eb409d5724cad2ca07d72752971db4362747.png)

Here ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png) describes paths that arrive at the detector, and ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) describes paths that don’t. The coefficients ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) describe the relative “weights” of the different paths. Using the quantum model, we can obtain a probabilistic prediction of whether the detector will click or not:

![\textrm{Pr}(\,\texttt{noclick}\; \!)  = |\alpha|^2  				\; \quad \textrm{and} \quad
\textrm{Pr}(\texttt{click}\; \!)    = |\beta|^2.](./images/7a977a4c5827c15f21e7b4423cf0757451149238.png)

For this example, both the classical and the quantum models describe the same real-world phenomenon. We can test the validity of both models by comparing the models’ predictions with what happens in reality.

Note that the two models make very different assumptions about reality. The classical model assumes the photon follows a single path through the circuit, whereas the quantum model assumes the photon can take multiple paths through the circuit. Despite the difference in the mathematical substrate of the models and their fundamentally different views of reality, we can compare the two models’ predictions on the same footing. Note it doesn’t make sense to say one model is more real than the other. The only thing that is real is the photon in the optical circuit, and the photon doesn’t care whether you use classical or quantum models to describe its path.

###[Quantum model peculiarities](./Front matter.md)

We’ll now comment on the relative “intuitiveness” of classical and quantum models and introduce the concept of _quantum measurement_, which is of central importance in quantum mechanics.

Classical models have the advantage of being more intuitively understandable than quantum models. The variables in classical models often correspond to measurable aspects of real-world systems. We can identify the position variable in a classical model with the position of a particle in the real world. Velocity and momentum are harder to understand intuitively, but we have some general intuition about motion and collisions from everyday life. In general, we can understand classical models more readily because it’s easier for us to think about a mechanistic, clockwork-like universe, in which objects push on each other with clearly defined cause and effect, like a clock that goes click, click, click.

In contrast, we do not enjoy such intuitive interpretation of quantum models, since our senses cannot directly perceive movement and interaction at the quantum level. Because quantum models’ states do not directly correspond to observable aspects in the real world, quantum models are often described as mysterious and counterintuitive. Quantum models are harder to understand in part because they use complex vector quantities to represent systems, and complex numbers are more difficult to visualize. For example, visualizing the complex-valued state of a photon ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) is difficult, since you must think about both the real part and the imaginary part of ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png). Even though we can’t see what ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) looks like, we can describe it using an equation, and do math calculations with it. In particular, we can compare the predictions obtained from calculations based on the quantum state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) to measurements performed in the real world.

The process of _quantum measurement_ is how we map the predictions of the quantum model to observable quantities. A quantum measurement acts on a particle’s wave function ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) to produce a classical outcome. **Performing quantum measurements is like asking questions of particles, and the measurement outcomes are the answers to these questions.**

![\begin{align*}
\textrm{What is your position?}
\quad
&\Leftrightarrow
\quad
\textrm{position}(\ket{\psi}) = x \in \mathbb{R}		\\
\textrm{What is your momentum?}
\quad
&\Leftrightarrow
\quad
\textrm{momentum}(\ket{\psi}) = p \in \mathbb{R}	\\				\textrm{What is your spin momentum?}
\quad
&\Leftrightarrow
\quad
\textrm{spin}_{\uparrow\!\downarrow}(\ket{\psi}) = s   \in \{ \uparrow, \downarrow \}
\end{align*}](./images/035aa77eb1e565ebf1776889f4de41c721bec898.png)

Since measurement outcomes correspond to real-world quantities that can be measured, we can judge the merits of quantum models the same way we judge the merits of classical models—in terms of the quality of their predictions.

###[Chapter overview](./Front matter.md)

In the next section, we’ll describe a tabletop experiment involving lasers and polarization lenses, with an outcome that’s difficult to explain using classical physics. The remainder of the chapter will introduce the tools needed to explain the outcome of this experiment in terms of quantum mechanics. We’ll start by introducing a special notation for vectors that is used to describe quantum phenomena [Section 9.1.4](./Chapter 9_ Quantum mechanics.md)).

In[Section 9.3](./Chapter 9_ Quantum mechanics.md), we’ll formally define the “rules” of quantum mechanics, also known as the _postulates_ of quantum mechanics. We’ll learn the “rules of the game” using the simplest possible quantum systems (qubits), and define how quantum systems are prepared, how we manipulate them using _quantum operations_, and how we extract information from them using _quantum measurements_. This part of the chapter is based on the notes from the introductory lectures of a graduate-level quantum information course, so don’t think you’ll be getting some watered-down, hand-wavy version of quantum mechanics. You’ll learn the real stuff, because I know you can handle it.

In[Section 9.4](./Chapter 9_ Quantum mechanics.md) we’ll apply the quantum formalism to the polarizing lenses experiment, showing that a quantum model leads to the correct qualitative and quantitative prediction for the observed outcome. We’ll close the chapter with short explanations of different applications of quantum mechanics with pointers for further exploration about each topic.

Throughout the chapter, we’ll focus on _matrix_ quantum mechanics and use computer science language to describe quantum phenomena. A computer science approach allows us to discuss the fundamental aspects of quantum theory without introducing all the physics required to understand atoms. Finally, I just might throw in a sample calculation using the wave function of the hydrogen atom, to give you an idea of what that’s like.

##[9.1 Polarizing lenses experiment](./Chapter 9_ Quantum mechanics.md)

Let’s run through a simple tabletop experiment that illustrates the limitations of classical, deterministic reasoning. The outcome of the experiment will highlight the need for careful consideration of the measurements used in scientific experiments.

We’ll describe the experiment using words and diagrams, but you can easily reproduce the experiment in your own “lab,” since it requires only simple equipment. I encourage you to try it yourself. You’ll need three polarizing lenses, a laser pointer, a piece of paper, and three binder clips for holding the lenses upright. You can buy polarizing lenses on the cheap from a second-hand camera shop—any polarizing lens will do.

###[Background](./Front matter.md)

In photography, polarizing lenses are used to filter out undesirable light reflections, like reflections that occur from water surfaces or glass windows. To better understand the experiment, we need to introduce some basic notions about the physics of light, specifically the concept of light polarization.

Light consists of photons. Photons are travelling pulses of electromagnetic energy. Electromagnetic energy can travel through space in the form of a wave. Polarization refers to the orientation of the electric field ![\vec{E}](./images/c9248ea1586d3a8d36a423b47a4bfcd8ce70a288.png) of a propagating electromagnetic wave.

Light is normally unpolarized, meaning it corresponds to a mixture of photons that have electric and magnetic components of random orientation. A light beam is _polarized_ if all its photons have the same orientation of their electric field.

![Onde_electromagnetique](./images/Onde_electromagnetique.png)

Figure 9.1: A photon is a pulse of electromagnetic energy. The energy of a photon travels in the form of a wave that has an electric component ![\vec{E}](./images/acf9f6af8938cefc16ce3a9d23d92f565e738b2b.png) and a magnetic component ![\vec{B}](./images/70512258fce933395cc2c31e5980f6c155cf3344.png). The figure shows a photon travelling in the positive ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png)\-direction with its electric component along the ![z](./images/f55c007144affca7e483671451c5e3aebe5c1aa7.png)\-axis.

Light reflected from flat surfaces, like the surface of a lake or a glass window, becomes polarized, which means the electric components of all the reflected photons become aligned.

Photographers use this fact to selectively filter out light with a particular polarization. A _polarizing filter_ or _polarizing lens_ has a special coating which conducts electricity in one direction, but not in the other. You can think of a polarizing lens as a surface covered by tiny conductive bands that interact with the electric component of incoming light particles. Light rays that hit the polarizing lens will either pass through or be reflected depending on their polarization. Light particles with a polarization perpendicular to the conductive bands pass through the lens, while light particles with polarization parallel to the conductive bands are reflected. This is because the surface of the lens has different conductive properties in the parallel and perpendicular directions.

![Wire-grid-polarizer](./images/Wire-grid-polarizer.png)

Figure 9.2: Incoming photons interact with the horizontal conductive bands of a polarizing lens. The horizontal bands of the lens reflect the horizontal component of the photons’s electric field. Vertically-polarized photons pass through the lens because the conductive bands are perpendicular to their electric field. Thus, a vertically polarizing lens denoted ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png) allows only vertically polarized light to pass through.

Consider the illustration in[Figure 9.3](./Chapter 9_ Quantum mechanics.md). The effect of a vertically polarizing lens on a beam of light is to only allow vertically polarized light to pass through.

![polarization-example-vertical-polarization-lens](./images/polarization-example-vertical-polarization-lens.png)

Figure 9.3: A vertically polarizing lens (![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png)) allows only vertically polarized light particles to pass through.

In[Figure 9.4](./Chapter 9_ Quantum mechanics.md) we see another aspect of polarizing lenses. If the light is already vertically polarized, adding a second vertically polarizing lens will not affect the beam. All light that passes through the first lens will also pass through the second.

![polarization-example-vertical-vertical-polarization-combo](./images/polarization-example-vertical-vertical-polarization-combo.png)

Figure 9.4: A second vertically polarizing lens has no further effect since light is already vertically polarized.

Taking a vertically polarizing lens and rotating it by 90 degrees turns it into a horizontally polarizing lens. See[Figure 9.5](./Chapter 9_ Quantum mechanics.md).

![polarization-example-horizontal-polarization-lens](./images/polarization-example-horizontal-polarization-lens.png)

Figure 9.5: A horizontally polarizing lens (![H](./images/a279e0fcb01c790332b789868a755f2255460155.png)) allows only horizontally polarized light particles to pass through.

Note that horizontally polarizing lenses and vertically polarizing lenses are complementary: vertically polarized light will not pass through a horizontally polarizing lens. This situation is illustrated in[Figure 9.6](./Chapter 9_ Quantum mechanics.md).

![polarization-example-vertical-horizontal-polarization-combo](./images/polarization-example-vertical-horizontal-polarization-combo.png)

Figure 9.6: Placing a horizontally polarizing lens after the vertically polarizing lens has the effect of filtering all light. Zero photons make it through both filters, which we indicate with the empty set symbol ![\emptyset](./images/f9bbe9077d067b510406bdc6443bd0f4f8267a24.png).

The previous examples can familiarize you with the properties of polarizing lenses, in case you don’t have actual lenses to play with. If you do have polarizing lenses, you can shine a laser pointer through them, observing when light passes through and when light is filtered out. Use binder clips to position the lenses on a flat surface, and reproduce the setup in[Figure 9.4](./Chapter 9_ Quantum mechanics.md). Don’t worry about finding the exact orientation for “vertical.” Any orientation of the lenses will do, as long as the first and the second polarizing lens have the same orientation. Next, you can rotate the second lens by 90![^\circ](./images/405f5940fc14d77f440f0e55e82ccbd540694152.png) to obtain the setup shown in[Figure 9.6](./Chapter 9_ Quantum mechanics.md), where the second lens has a perpendicular orientation and thus rejects all light.

#####[Example](./Front matter.md)

Polarized sunglasses leverage the properties of light polarization to make outdoor activities more enjoyable. When a beam of light bounces off the surface of a lake, it becomes horizontally polarized. This polarization effect is due to the interaction of light’s electric field at the surface of the water. A person wearing vertically polarizing lenses (polarized sunglasses) cannot see the sun’s reflection off the water surface because the ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lenses filter out the horizontally polarized light reflected from the surface of the lake. This effect is useful for people who are often outdoors in bright sunlight, as it reduces the blinding effect of the sun’s reflection.

###[Classical physics paradigm](./Front matter.md)

Before we describe the outcome of the polarizing lenses experiment, let’s take a moment to describe the assumptions about the world that 19th\-century physicists held. Understanding this classical world view will explain why the outcomes of the polarizing lenses experiment are so surprising.

The classical laws of physics are deterministic, meaning they do not allow randomness. According to the classical school, experimental outcomes depend on _definite_ variables, like the properties of particles. Physicists assume they can predict the outcome of any experiment given they know the properties of the particles involved. If some outcome cannot be predicted, it must be because the value of some property of the particles is unknown. In other words, everything happens for a reason. Another key assumption classical physicists make is that a photon’s properties are immutable, meaning we cannot change them. Classical physicists assume their **experiments correspond to passive observations** that cannot change the system’s properties.

A 19th\-century physicist would expect the outcomes of polarizing lenses experiments to be fully determined by the polarization property of photons. Each photon carries a tag `H` or `V` that describes its polarization. In the setup shown in[Figure 9.3](./Chapter 9_ Quantum mechanics.md), each photon that passes through the lens must have `tag="V"`, because we know by definition that a ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lens only allows vertically polarized photons to pass through. Readers familiar with SQL syntax will recognize the action of the vertically polarizing lens as the following query:

![\texttt{SELECT photon FROM photons WHERE tag="V";}](./images/3ce9e81892755fe8d19283f6ff659af714ee8e86.png)

In other words, out of all the incoming photons, only the vertically polarized photons pass through the lens. Similarly, for the ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png)\-polarizing lens shown in[Figure 9.5](./Chapter 9_ Quantum mechanics.md), the filtering process can be understood as the query:

![\texttt{SELECT photon FROM photons WHERE tag="H";}](./images/ae90e0f81dd760b127c578a775c570ce33726a48.png)

In both cases, classical physicists would assume that whether or not a photon passes through a lens is predetermined, and is dependent only on the photon’s tag.

For the purpose of our discussion, we’ll restrict our attention to photons with either horizontal (`tag="H"`) or vertical (`tag="V"`) polarization. There are other possible polarization directions, but we’ll focus on the tags `H` and `V` because they’re mutually exclusive—if a photon is horizontally polarized, we know a vertically polarizing lens will reject it. We can assert that photons that pass through an ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png)\-polarizing lens are not vertically polarized; if they were, these photons would reflect off the lens instead of passing through.

###[Polarizing lenses experiment](./Front matter.md)

The physics experiment we’ll describe consists of sending photons through an optical circuit made of polarizing lenses and observing how many photons pass through the circuit. We describe the number of photons that reach any point in the circuit in qualitative terms, by referring to the _optical power_ reaching that point, denoted ![P](./images/007b6f42853e2d6a7e8c32c2cf94304c5425e066.png). We choose the light intensity of the beam after it passes through the first polarizing lens as our reference, and call it ![P=1](./images/56559d650864322f649b9c29da7ef3b40702420b.png) (full brightness). You can think of optical power as brightness. If you were to insert a piece of paper somewhere in the optical circuit, the optical power would measure the brightness of the spot of light on the paper at that particular location in the circuit. When power ![P=1](./images/56559d650864322f649b9c29da7ef3b40702420b.png), the spot of light is fully bright. If ![P=0.5](./images/283233a7d178b2b216c868190fd5a8c0183b6aed.png) the spot is half as bright as when ![P=1](./images/56559d650864322f649b9c29da7ef3b40702420b.png). The case ![P=0](./images/67c139803f2357a85c9f7bff365a717d7c73598f.png) corresponds to zero brightness and occurs when no photons hit the piece of paper.

The initial setup for the experiment consists of an ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png)\-polarizing lens followed by a ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lens, as shown in[Figure 9.7](./Chapter 9_ Quantum mechanics.md).

![two-lenses-expriment](./images/two-lenses-expriment.png)

Figure 9.7: The initial setup for the polarizing lenses experiment consists of an ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png)\-polarizing lens followed by a ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png)\-polarizing lens. Only photons with `tag="H"` can pass through the first lens, so no photons with `tag="V"` pass through the first lens. No photons can pass through both lenses since the ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png)\-polarizing lens accepts only photons with `tag="V"`.

We know the photons that pass through the first lens are horizontally polarized. It’s no surprise that when this light hits the second lens, none of the photons make it through, since a ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lens rejects ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png)\-polarized photons.

#####[Adding a third lens](./Front matter.md)

We now introduce a third lens between the first two lenses, and we orient the middle lens differently from the other two—in the diagonal direction, for example. The result is shown in[Figure 9.8](./Chapter 9_ Quantum mechanics.md). Suddenly, light appears at the end of the circuit! How does this make sense? You tell me if this is crazy or not. Intuitively, adding more filtering only reduces the amount of light passing through the circuit; yet the amount of light that passes through the circuit increases when we add the middle filter. How can adding more filtering increase light intensity? What is going on?

![three-lenses-expriment](./images/three-lenses-expriment.png)

Figure 9.8: Adding an additional polarizing lens in the middle of the circuit causes light to appear at the end of the optical circuit.

We pick the middle lens to be a diagonally polarizing lens ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png). A diagonally polarizing lens is obtained by rotating any polarizing lens by 45![^\circ](./images/405f5940fc14d77f440f0e55e82ccbd540694152.png). The exact choice for the middle lens is not crucial for the experiment to work; so long as its polarization is different from the ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png)\- and ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lenses that surround it.

For a demonstration of the three-polarizing lenses experiment, see this Youtube video:[`https://youtu.be/PJHCADY-Bio?t=6m14s`](./PJHCADY-Bio_t=6m14s.md).

###[Classical analysis](./Front matter.md)

The experimental observations illustrated in[Figure 9.8](./Chapter 9_ Quantum mechanics.md) are difficult to explain using the classical way of thinking, in which particle properties are immutable tags, and experiments are passive observations.

We have evidence that a particle’s state can change during the process of measurement. Let’s examine this more closely. We’ll trace the path of the photons through the optical circuit in[Figure 9.8](./Chapter 9_ Quantum mechanics.md), keeping track of what we know about the photons at each stage. First, all photons that pass through the first ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png)\-polarizing lens are known to be horizontally polarized (`tag="H"`). We’re sure no ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarized photons pass through the first lens, because an ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png)\-polarizing lens is guaranteed to reject all ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarized photons. Yet, after passing through the second lens (the ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png) lens), these same photons appear to be vertically polarized since they pass through the third lens. Is something wrong with the tagging system? It seems the photons’ tag states are affected by the measurements performed on them. This fact is difficult to explain for classical physicists since they assume measurements correspond to passive observations. In the classical paradigm, measuring a photon’s ![D](./images/ec2cf42d15fc217ec1e0c76c5c24971db252cffa.png)\-polarization using the middle lens should not affect its `H` and `V` tags.

In[Section 9.3](./Chapter 9_ Quantum mechanics.md) we’ll revisit the polarizing lenses experiment after we have learned the postulates of quantum mechanics. We’ll see we can explain the outcome of the experiment by describing the photon’s polarization in terms of vector-like states; and that our understanding of vectors can even predict the final light intensity of ![P=0.25](./images/8f123c0f34f027bcfd2fd4f0aaa203e310b51663.png) we observed during the experiment. Before we discuss the postulates of quantum mechanics [Section 9.3](./Chapter 9_ Quantum mechanics.md)), we’ll need to introduce some new notation for describing quantum states.

This section is a quick primer on Dirac notation, which is a precise and concise language for talking about vectors and matrices. The Dirac notation for vectors ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png) is an alternative to the usual notations for vectors like ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) or ![\mathbf{v}](./images/633b84ab115cc79e0751cfddae6cfadae6fca32b.png).

This new notation will look weird initially, but once you get the hang of it, I guarantee you’ll like it. Learning Dirac notation is an excellent way to review essential linear algebra concepts like bases, vectors, inner products, and matrices. Understanding Dirac notation is essential if you’re interested in learning quantum mechanics, but it’s also worth learning “just because”—it’s _that_ cool.

We’ll now discuss several vector topics you’re familiar with, and compare standard vector notation ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) with the equivalent Dirac notation ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png).

####[The standard basis](./Front matter.md)

Consider a ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png)\-dimensional complex vector space ![\mathbb{C}^d](./images/8686e292eac775a5afb303d0a06aa39018168f97.png). We refer to complex vector spaces as Hilbert spaces, in honour of David Hilbert, who contributed prolific developments to math and physics.

To understand any vector space, it is essential to construct a basis for the space. A natural choice for a basis is the standard basis, which we’ll denote ![\{ \ket{0}, \ket{1}, \ket{2}, \ldots, \ket{d-1} \}](./images/5e8c50f3842ef9dbe5fee81aff5df8e870f23d63.png). The basis vectors are defined as:

![\ket{0} =	\colvec{ 1 \\ 0 \\ \vdots \\ 0}\!,
\quad
\ket{1} =	\colvec{ 0 \\ 1 \\ \vdots \\ 0}\!,
\qquad
\ldots,
\quad
\ket{d-1} =	\colvec{ 0 \\  \vdots \\ 0  \\ 1}\!.](./images/76a8aaaba6640f4ad05e4eb2d5983e2f745b1b2c.png)

Note the indices are shifted by one so the first basis vector has index ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png), not index ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png). This zero-based indexing is chosen to make certain links between quantum theory and computer science more apparent.

One benefit of Dirac notation is that it doesn’t require writing subscripts. To refer to a vector associated with properties ![a](./images/43cec1a1714075e03ef71c50ba6cd20d9e641606.png), ![b](./images/9412ff45fe40f01c2717d32e74faa8f2e2284abd.png), and ![c](./images/178c2ec82ef3e356dcd1141f277934c3f139f5df.png), we can write ![\ket{a,b,c}](./images/57c1af0c3b659cd039bb6ba5fc48ccc8dad523ce.png), instead of the more convoluted expression ![\vec{v}_{a,b,c}](./images/7b329dbaf4e22201954fb55d9f55c4b481233d54.png).

We’ll now focus solely on the two-dimensional complex vector space ![\mathbb{C}^2](./images/a3872a4fb8e558e4f3ec519b05d7eb9f7b7b7d12.png); however, the results and definitions presented below also apply to vectors of any dimension.

####[Vectors](./Front matter.md)

In Dirac notation, a vector in ![\mathbb{C}^2](./images/a3872a4fb8e558e4f3ec519b05d7eb9f7b7b7d12.png) is denoted as a _ket_:

![\ket{v} 	=	\alpha\ket{0} + \beta\ket{1} 
\qquad \Leftrightarrow \qquad
\colvec{ \alpha \\ \beta } = 	\alpha\colvec{ 1 \\ 0} + \beta\colvec{ 0 \\ 1 }\!,](./images/ceb02af6034bf3ecf63f76a3fdb03821b1fba32e.png)

where ![\alpha\in\mathbb{C}](./images/4d578e1908f19ad0ca352a10985ff54c99aa7147.png) and ![\beta\in\mathbb{C}](./images/d11ec58959e8dab2b0a3fe7c7b27820967f74b7a.png) are the _components_ of ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png) and ![\{ \ket{0}, \ket{1}\}](./images/0433fdf95be980a035da81addd049f24c61576cb.png) is the standard basis for ![\mathbb{C}^2](./images/a3872a4fb8e558e4f3ec519b05d7eb9f7b7b7d12.png):

![\ket{0} = \colvec{ 1 \\  0}\!,
\qquad 
\ket{1} = \colvec{ 0\\  1}\!.](./images/80c121e90f8fc35544d66e9ecae3caea59032849.png)

Why do we call the angle-bracket thing a “ket,” you ask? Let me tell you about the _bra_ part, and then it will start to make sense.

The Hermitian transpose of the ket-vector ![\ket{v} = \alpha\ket{0} + \beta\ket{1}](./images/0a9e0e2ac990d302a2995c713a37121a24f6e022.png) is the _bra_\-vector ![\bra{v}](./images/ae259a2300d0c51f8549370594c407aca58d4777.png):

![\bra{v} 	= 	\overline{\alpha}\bra{0} + \overline{\beta}\bra{1} 
\qquad
\Leftrightarrow
\qquad[\overline{\alpha},  \overline{\beta} ]			
= 		\overline{\alpha}[1,0] + \overline{\beta}[0,1].
\qquad](../Images/0637782ac9a2e9904c1e2ca348606211d288f364.png)

Recall that the Hermitian transpose, also called the complex transpose, is the combination of the regular transpose (![\vec{v} \to \vec{v}^\sfT](./images/3b6039de83fb48e7c6090cebca2e5e9a090d0363.png)) and the complex conjugation of each component of the vector (![v_{i} \to \overline{v_{i}}](./images/723961516b1dc59df8ef1f2d30a6ea369a5fd537.png)), and is denoted as the dagger operator “![\,\dagger\,](./images/71dbff3b04ea524cd57b4171cc8ad310c3525f8b.png)” (see page 6.7.1.3 for a refresher on the dagger operator). Now observe how much simpler the _bra_ notation for the Hermitian transpose of a vector is compared to the other notations we’ve seen so far:

![\bra{v} 
\qquad 
\Leftrightarrow
\qquad
\vec{v}^\dagger   = \overline{(\vec{v}^\sfT)} =  (\overline{\vec{v}})^\sfT.](./images/9a1a3dabf29ba90af54a27ddb3e0163c0636b243.png)

When you put a bra ![\bra{v}](./images/ae259a2300d0c51f8549370594c407aca58d4777.png) next to a ket ![\ket{w}](./images/d06a6f6b801d000cdbb9977fe35d1a298a334ddd.png), they become a bra-ket ![\braket{v|w}](./images/ae6819c5526066501e2b721c7daf8d16d3e5e1ec.png), which looks very similar to the brackets used to denote the inner product between two vectors. Observe the relative notational simplicity of calculating the inner product between the vectors ![\ket{v} = v_0\ket{0}+v_1\ket{1}](./images/0b25e0876daeffb4040a90c4cfde48f41a581c6d.png) and ![\ket{w} = w_0\ket{0}+w_1\ket{1}](./images/be63346fa46b2fe4d6d1e3562f8020d117ca1d14.png) in Dirac notation:

![\braket{v|w} = \overline{v_0} w_0 + \overline{v_1} w_1
\qquad 
\Leftrightarrow
\qquad		
\vec{v}^\dagger \vec{w}    =	\overline{\vec{v}} \cdot \vec{w}.](./images/c0a330732856301730691e04489989bec4df96a9.png)

Complex conjugation was already applied to the coordinates of ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png) when transforming it into a bra-vector ![\bra{v}](./images/ae259a2300d0c51f8549370594c407aca58d4777.png), thus we can simply “put together” the bra and the ket to compute the inner product. Because the bra notation ![\bra{v}](./images/ae259a2300d0c51f8549370594c407aca58d4777.png) contains the Hermitian transpose, it removes the need for the dagger symbol. For instance, the inner product of ![\ket{v}= \alpha\ket{0} + \beta\ket{1}](./images/0a9e0e2ac990d302a2995c713a37121a24f6e022.png) with itself is

![\begin{align*}
\braket{v|v} 	&=	\left( \overline{\alpha}\bra{0} + \overline{\beta}\bra{1},
\alpha\ket{0} + \beta\ket{1} \right)	\\
&=	\overline{\alpha}\alpha \braket{0|0}
+ \overline{\alpha}\beta \,\underbrace{\!\braket{0|1}\!}_0 \,
+ \overline{\beta}\alpha \,\underbrace{\!\braket{1|0}\!}_0 \,
+ \overline{\beta}\beta \braket{1|1}	\\
&= 	|\alpha|^2 + |\beta|^2.
\end{align*}](./images/8c052bb7d3137592d993a7c575d8f629299dda69.png)

This small simplification of the notation for inner products is quite useful, since inner products are the workhorse for calculating vector coordinates, finding projections, and performing change-of-basis transformations. The concise notation enables us to dig deeper into these aspects of linear algebra without getting overwhelmed by notational complexity. Moreover, Dirac’s bra-ket notation is sufficiently simple to use in equations without needing to define new variables ![v_i](./images/abb23a5428dd91d81a0e764b6e1f2924c3cfae81.png) for vector coordinates. We’ll look at this more closely in the next section.

####[Vector coordinates](./Front matter.md)

The _coordinates_ ![v_i](./images/abb23a5428dd91d81a0e764b6e1f2924c3cfae81.png) of a vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) with respect to an orthonormal basis ![\{ \hat{e}_i \}](./images/eef194e84589e60d53ce9919410e93eb3417c776.png) are computed using the inner product ![v_i = \hat{e}_i^\dagger \vec{v}](./images/cf8a77cc3a5d2336bcb65a763ff5d043fa172d90.png). In Dirac notation, the coordinates of ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png) with respect to the standard basis ![\{ \ket{0}, \ket{1} \}](./images/0433fdf95be980a035da81addd049f24c61576cb.png) can be written as ![\braket{i|v}](./images/d61e76356f74be6d36f3f6a6e3bd2118cbef32f5.png). We can write any vector ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png) as a linear combination of kets, with bra-kets as coefficients:

![\ket{v} = \underbrace{\braket{0|v}}_{v_0}\ket{0}  +  \underbrace{\braket{1|v}}_{v_1}\ket{1}.](./images/1ad972011a872a0aadfd7830021f63f2a8cd4a34.png)

The expression ![\braket{i|v}](./images/d61e76356f74be6d36f3f6a6e3bd2118cbef32f5.png) explicitly defines the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th coordinate of ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png); therefore, we don’t need to define the variable ![v_i](./images/abb23a5428dd91d81a0e764b6e1f2924c3cfae81.png).

Another basis for the vector space ![\mathbb{C}^2](./images/a3872a4fb8e558e4f3ec519b05d7eb9f7b7b7d12.png) is the _Hadamard basis_, which corresponds to the standard basis rotated by ![45^\circ](./images/bd3d3974358aa0059bc92afb15aa60914b97d2d5.png) in the counter-clockwise direction:

![\begin{align*}
\ket{+} 	& =   \tfrac{1}{\sqrt{2}}\ket{0} + \tfrac{1}{\sqrt{2}}\ket{1},   \\
\ket{-} 	& =    \tfrac{1}{\sqrt{2}}\ket{0} - \tfrac{1}{\sqrt{2}}\ket{1}.
\end{align*}](./images/f83149f9225cc16eac7127f864e17eb1ac6c86e2.png)

The Hadamard basis, henceforth denoted ![B_h = \{ \ket{+}, \ket{-} \}](./images/c3ab72d711e250dff1d87c6d7bd23e8a3b8a95c1.png), is an orthonormal basis:

![\braket{+|+} = 1,
\quad
\braket{+|-} = 0,
\quad
\braket{-|+} = 0,
\quad
\braket{-|-} = 1.](./images/11459d20c3b758d6e587adbf4ea2090d6511c3af.png)

Since the Hadamard basis ![B_h](./images/ed806363e7593bfb85745e769a27899ad2058cd7.png) is an orthonormal basis, we can express any vector ![\ket{v} \in \mathbb{C}^2](./images/8133e818ea2470b536df0956b2b3548922dd7022.png) as a linear combination of kets:

![\ket{v}	= 	\underbrace{\braket{+|v}}_{v_+}\ket{+} + \underbrace{\braket{-|v}}_{v_-}\ket{-}.](./images/b416a1610f74f1019584a25a384d0dc7ef18c2a8.png)

Note that the coefficients of the linear combination are computed using the inner product with the corresponding basis vector ![\braket{+|v}](./images/dfb0887e6044529c3b38594b03302d77c1f3f986.png) and ![\braket{-|v}](./images/db79af426247d0f1efe4eb952b5ebc5f366c6d97.png). The bra-ket notation allows us to refer to the coordinates of ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png) with respect to ![\{ \ket{+}, \ket{-} \}](./images/5e1996145b5be00fb9a3058418c66a821d664108.png), without the need to define variables ![v_+](./images/52fc51a23dca5d6e30f0a27063fe9bfe7ae11103.png) and ![v_-](./images/741dfc2296bacd1c3d183a2507e08734d87b0b50.png).

It’s not uncommon to see vector coordinates with respect to different bases used in calculations. With the usual vector notation, we must specify which basis we’re using as a subscript. For example, the same vector ![\vec{v}](./images/e50e841f819bb6df0b1a86a6661f572a50de8276.png) can be expressed as a coordinate vector ![\vec{v} = (v_0, v_1)_{B_s}^\sfT](./images/7100d22c2612a8376b7c2d8faa13ed464eb6a7b8.png) with respect to the standard basis ![B_s](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png), or as a coordinate vector ![\vec{v} = (v_+, v_- )_{B_h}^\sfT](./images/be9a542a3678cb7c17bcc8d9a87f136509021fe7.png) with respect to the Hadamard basis. In the bra-ket notation, the coordinates with respect to ![B_s](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png) are ![\braket{0|v}](./images/82a43622d145038bf15262751c1853b3b80e3746.png) and ![\braket{1|v}](./images/9c7da4fd22431d28434e6749719625370bbeb2b5.png), and the coordinate with respect to ![B_h](./images/ed806363e7593bfb85745e769a27899ad2058cd7.png) are ![\braket{+|v}](./images/dfb0887e6044529c3b38594b03302d77c1f3f986.png) and ![\braket{-|v}](./images/db79af426247d0f1efe4eb952b5ebc5f366c6d97.png), making the choice of basis evident.

####[Change of basis](./Front matter.md)

Consider the task of finding the _change-of-basis_ matrix ![\!\tensor[_{B_h}]{\left[\mathbbm{1}\right]}{_{B_s}}](../Images/9cfa8e1d041179b0d30b22038d5dd2fc0116c10c.png) that converts vectors from the standard basis ![B_s = \{ (1,0), (0,1) \}](./images/7ed3895543be801cd2110c68ecb0ae599ec8326a.png) to the Hadamard basis ![B_h = \{ (\tfrac{1}{\sqrt{2}},\tfrac{1}{\sqrt{2}}), (\tfrac{1}{\sqrt{2}},-\tfrac{1}{\sqrt{2}}) \}](./images/e5e4b9a161b23229056d864ee359162874f05dff.png).

Using the standard approach for finding change-of-basis matrices discussed in[Section 4.3.7](./Chapter 4_ Geometric aspects of linear algebra.md) (page 4.3.7), we know the columns of ![\!\tensor[_{B_h}]{\left[\mathbbm{1}\right]}{_{B_s}}](../Images/9cfa8e1d041179b0d30b22038d5dd2fc0116c10c.png) contain the coordinates of ![(1,0)](./images/d8f32e7b923a10bccdaa68e7141d6158e48cdc1f.png) and ![(0,1)](./images/51dc53e490143c62313d23af4c20f5a4e63d4d20.png) as expressed with respect the basis ![B_h](./images/ed806363e7593bfb85745e769a27899ad2058cd7.png):

![\!\tensor[_{B_h}]{\left[\mathbbm{1}\right]}{_{B_s}}
\; = \; 
\tensor[_{B_h\!}]{
\begin{bmatrix}
\braket{+|0} \!	&	\! \braket{+|1}	\\
\braket{-|0}  \!	&	\! \braket{-|1}
\end{bmatrix}
}{_{\!B_s}}
\; = \; 		
\tensor[_{B_h\!}]{
\begin{bmatrix}
\tfrac{1}{\sqrt{2}}	&	\tfrac{1}{\sqrt{2}}	\\
\tfrac{1}{\sqrt{2}}	&	-\tfrac{1}{\sqrt{2}} 
\end{bmatrix}
}{_{\!B_s}}\!.](../Images/6855a9e3a640ce849a81001801875ec74a7edfc8.png)

We can now compute the coordinates of any vector ![\vec{v} = (v_0, v_1)_{B_s}^\sfT](./images/7100d22c2612a8376b7c2d8faa13ed464eb6a7b8.png) with respect to the Hadamard basis, by multiplying ![(v_0, v_1)_{B_s}^\sfT](./images/aad3f6a0309ea00ddb5555ed38b38c1ff72d097d.png) by the change-of-basis matrix:

![\begin{align*}
\colvec{ v_+\\ v_- }_{\!B_h}
&=  \!\tensor[_{B_h}]{\left[\mathbbm{1}\right]}{_{B_s}} \colvec{ v_0 \\ v_1 }_{\!B_s}			\\
&=
\tensor[_{B_h\!}]{
\begin{bmatrix}
\tfrac{1}{\sqrt{2}}	&	\tfrac{1}{\sqrt{2}}	\\
\tfrac{1}{\sqrt{2}}	&	-\tfrac{1}{\sqrt{2}}
\end{bmatrix}
}{_{\!B_s}}\!
\colvec{ v_0 \\ v_1 }_{\!B_s}					\\
&=	\colvec{  \tfrac{1}{\sqrt{2}}\big( v_0 + v_1\big) 		\\
\tfrac{1}{\sqrt{2}}\big( v_0 - v_1 \big)
}_{\!B_h}.
\end{align*}](../Images/2bce151d39c9f5ab1c40ee302624e516d0c5de10.png)

This is the usual approach for computing the coordinates of a vector in one basis in terms of the coordinates of another basis using matrix notation.

Consider now the same change-of-basis operation, but with calculations carried out in Dirac notation. Given the vector ![\vec{v}=(v_0,v_1)_{B_s} = v_0 \ket{0} + v_1\ket{1}](./images/e0bede6f256232276fbb8bbb7b0104b9446c2819.png) expressed as coordinates with respect to the standard basis ![B_s](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png), we want to find ![\vec{v}=(v_+,v_-)_{B_h} = v_+\ket{+} + v_-\ket{-}](./images/126fb113df08773f19d9f316ebe5c07729c242d8.png). Starting from the definition of ![v_+](./images/52fc51a23dca5d6e30f0a27063fe9bfe7ae11103.png) and ![v_-](./images/741dfc2296bacd1c3d183a2507e08734d87b0b50.png), we obtain

![\begin{align*}
\vec{v} & = (v_+, v_- )_{B_h}^\sfT		 \\
& = \braket{+|v}\ket{+} + \braket{-|v}\ket{-}  \\
& = 	\bra{+}\big( v_0\ket{0} + v_1\ket{1} \big) \ket{+} + \bra{-}\big( v_0\ket{0} + v_1\ket{1} \big) \ket{-}  \\
& = 	\big( v_0\braket{+|0} + v_1\braket{+|1} \big) \ket{+} + \big( v_0\braket{-|0} + v_1\braket{-|1} \big) \ket{-}  \\
& = 	\underbrace{\tfrac{1}{\sqrt{2}}\big( v_0 + v_1\big)}_{v_+} \ket{+} + 
\underbrace{\tfrac{1}{\sqrt{2}}\big( v_0 - v_1 \big)}_{v_-} \ket{-}.
\end{align*}](./images/f858c8c5d7aada2272485b27012c6e14cae112aa.png)

Working from the definitions of vectors and their coordinates, and using only basic algebra rules, we can perform the change-of-basis operation without explicitly constructing the change-of-basis matrix.

####[Outer products](./Front matter.md)

Recall the _outer product_ operation for vectors that we introduced in[Section 5.2](./Chapter 5_ Linear transformations.md) (see page 5.2.3.5). The expression ![\ketbra{0}{0}](./images/356788f009d51147f4f2fe15d4e9b53d5e57bec3.png) is equivalent to the _projection_ onto the subspace spanned by the vector ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png):

![\ketbra{0}{0}		
\qquad
\Leftrightarrow
\qquad
\begin{bmatrix}
1 \\
0 
\end{bmatrix}
\!
\begin{bmatrix}
1 & \!\! 0	
\end{bmatrix}
=
\begin{bmatrix}
1 & 0  \\
0 & 0 
\end{bmatrix}.](./images/5d05d9705f4c91845f9d06a80db0627caa17969b.png)

We can verify this by considering the product of ![\ketbra{0}{0}](./images/356788f009d51147f4f2fe15d4e9b53d5e57bec3.png) and an arbitrary vector ![\ket{v}=\alpha\ket{0} + \beta\ket{1}](./images/0a9e0e2ac990d302a2995c713a37121a24f6e022.png):

![\ketbra{0}{0} \left(\alpha\ket{0} + \beta\ket{1}\right)
=  \alpha \ket{0} \underbrace{\braket{0|0}}_1 + \beta\ket{0} \underbrace{\braket{0|1}}_0
= \alpha \ket{0}.](./images/82eb48c12286b4506491a77da5594f0675d095aa.png)

The ability to easily express outer products is another win for Dirac notation. For example, the projection onto the ![\ket{+}](./images/65a36f521741d9cd1a45efa30255d0b8241c30d9.png)\-subspace is ![\ketbra{+}{+}](./images/62b718dffbf75863dd919107e767576a7aae1882.png).

####[Matrices](./Front matter.md)

Now get ready for some crazy stuff. It turns out outer-product expressions are useful not only for projections, but can in fact represent any matrix. Consider the linear operator ![A : \mathbb{C}^2 \to \mathbb{C}^2](./images/2a7909f9573ec6ff8a67ddea027c882a5ee6cb67.png) and its matrix representation with respect to the standard basis:

![\begin{align*}
\tensor[_{B_s}]{\left[A\right]}{_{B_s}}  
&=
\tensor[_{B_s}]{
\begin{bmatrix}
a_{00}	&	a_{01}	\\
a_{10}	&	a_{11}	\\
\end{bmatrix}
}{_{B_s}}\!.
\end{align*}](../Images/0f7e2bc5722bdb0cd41d783aab687560ea660a3b.png)

Instead of positioning the entries in an array, we can represent ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as a linear combination of outer products:

![\begin{align*}
A \; 
& =  \; 
a_{00} \ketbra{0}{0} + a_{01}\ketbra{0}{1} +
a_{10} \ketbra{1}{0} + a_{11}\ketbra{1}{1}.
\end{align*}](./images/edda3f232bafc501851ad6be8887cf6eed204841.png)

Consider the matrix vector product ![A\ket{x} = \ket{y}](./images/17bfb2873635d918013994dc5407228151e8d731.png). The matrix entry ![a_{10}](./images/4ecff65c3b4759c9b59d046a9c5b70060b2d4c38.png) describes the multiplication factor that connects the ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png)\-component in the input ![\ket{x}](./images/162d2cc27b77bb4e18cb745b46de98ae47f2e529.png) to the ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png)\-component of the output vector ![\ket{y}](./images/92529f5c2ec85f225f4ffce32a3a3f5e1984b281.png). The expression ![a_{10} \ketbra{1}{0}](./images/ba49e469890f6e19e304ae811c7dfade629e9d16.png) is a concise description of the same story. The ![\bra{0}](./images/30c1ef8253bdc50ae825b2f868857e4fb412049a.png) in this expression will “select” only the ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) component of the input, and the ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png) indicates that this term contributes to the ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png) component of the output.

The entries of the matrix representation ![\tensor[_{B_s}]{\left[A\right]}{_{B_s}}](../Images/97bfbaf85a8e24b39f5472fcb7edb2dedb8983cd.png) depend on the choice of bases for the input and output spaces. The value of the entry ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png) in the matrix representation is computed by “probing” the matrix with the ![j](./images/3314c02090bd49936a6087274b61e7c78cf46298.png)th basis vector of the input basis, and observing the value of the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th component in the resulting output. We can express the entire “probing procedure” easily in Dirac notation: ![a_{ij} = \braket{i|A|j}](./images/d408fe771723fa7ac161d11d35e129d9dfd90b6e.png). Thus, we can write the matrix entries as follows:

![\begin{align*}
\tensor[_{B_s}]{
\begin{bmatrix}
a_{00}	&	a_{01}	\\
a_{10}	&	a_{11}	\\
\end{bmatrix}
}{_{B_s}}							
&=
\tensor[_{B_s}]{
\begin{bmatrix}
\bra{0}A\ket{0}	&	\bra{0}A\ket{1}	\\
\bra{1}A\ket{0}	&	\bra{1}A\ket{1}	\\
\end{bmatrix}
}{_{B_s}}.
\end{align*}](../Images/c26cbb6c0b6e47592170f9aa2ffaf78679197620.png)

In fact, we don’t need matrix notation or the entries ![a_{ij}](./images/6b32e49045d77d882822aac4b4dde215e230a9f0.png) at all. Instead, we can express ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) as a linear combination of outer products, with appropriately chosen coefficients:

![\begin{align*}
A \; \; 
& = \; 
\bra{0}A\ket{0}\ketbra{0}{0}
+  \bra{0}A\ket{1}\ketbra{0}{1} 
+  \bra{1}A\ket{0}\ketbra{1}{0} 
+  \bra{1}A\ket{1}\ketbra{1}{1}.
\end{align*}](./images/d246920e12f667ffa9cec7c9283222992a216267.png)

Let’s verify the formula for the ![a_{10} = \bra{1}A\ket{0}](./images/39fdbfc892251583ef6c3911bbd1d6088f1f653f.png)\-entry of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png), to see how this linear combination of outer products thing works. We start from the definition ![A = 	a_{00} \ketbra{0}{0} + a_{01}\ketbra{0}{1} + a_{10} \ketbra{1}{0} + a_{11}\ketbra{1}{1}](./images/4df1524c7603760c200fa6364151a750f148222f.png), and multiply ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) by ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) from the right and ![\bra{1}](./images/c0005a67191cd0b83fe57931c6db30189ca00842.png) from the left:

![\begin{align*}
\bra{1}A\ket{0}
&=
\bra{1}
\Big(
a_{00} \ketbra{0}{0} + a_{01}\ketbra{0}{1} +  a_{10} \ketbra{1}{0} + a_{11}\ketbra{1}{1}
\Big)
\ket{0}		\\
&= 
\bra{1}
\Big(
a_{00} \ket{0} \!\underbrace{\!\!\braket{0|0}\!\!}_1
+ a_{01}\ket{0} \!\underbrace{\!\!\braket{1|0}\!\!}_0 
+  a_{10} \ket{1} \!\underbrace{\!\!\braket{0|0}\!\!}_1
+ a_{11}\ket{1} \!\underbrace{\!\!\braket{1|0}\!\!}_0 
\!\Big)														\\
&=
\bra{1}
\Big(
a_{00} \ket{0} 
+  a_{10} \ket{1} 
\Big)														\\
&= 	    a_{00} \,\underbrace{\!\braket{1|0}\!}_0 \, 
+  a_{10} \,\underbrace{\!\braket{1|1}\!}_1 \,	= a_{10}.
\end{align*}](./images/a8c805aae4df62a383936011f5e9d3f64a8b6948.png)

Indeed, ![\bra{1}A\ket{0}](./images/04af53cf4e94aa505c09b0b08a5fcc82b30b7b1d.png) is the same as ![a_{10}](./images/4ecff65c3b4759c9b59d046a9c5b70060b2d4c38.png). In fact, we’ll rarely use the notation ![a_{10}](./images/4ecff65c3b4759c9b59d046a9c5b70060b2d4c38.png), since ![\bra{1}A\ket{0}](./images/04af53cf4e94aa505c09b0b08a5fcc82b30b7b1d.png) is just as easy to write, and much more intuitive: the ![a_{10}](./images/4ecff65c3b4759c9b59d046a9c5b70060b2d4c38.png)\-entry of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) is what you obtain when you “sandwich” the matrix ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) between the vectors ![\bra{1}](./images/c0005a67191cd0b83fe57931c6db30189ca00842.png) on the left and ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) on the right.

In Dirac notation, the basis appears explicitly in expressions for entries of a matrix. We can define the entries of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) in any other basis easily and precisely. The representation of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) with respect to the Hadamard basis ![B_h = \{ \ket{+}, \ket{-} \}](./images/c3ab72d711e250dff1d87c6d7bd23e8a3b8a95c1.png) is

![\begin{align*}
\tensor[_{B_h}]{\left[A\right]}{_{B_h}}  
&=
\tensor[_{B_h}]{
\begin{bmatrix}
\bra{+}A\ket{+}	&	\bra{+}A\ket{-}	\\
\bra{-}A\ket{+}	&	\bra{-}A\ket{-}	\\
\end{bmatrix}
}{_{B_h}}\!,
\end{align*}](../Images/8e82d1de18ab6b32b3b6242807809b26510d44a3.png)

or equivalently,

![A=\bra{+}A\ket{+} \ketbra{+}{+}
\,+\, \bra{+}A\ket{-} \ketbra{+}{-} 
\,+\, \bra{-}A\ket{+}  \ketbra{-}{+}
\,+\, \bra{-}A\ket{-}	 \ketbra{-}{-}.](./images/3982f9bb13448351280677733d07c466eb8d0ed7.png)

The coefficient ![\bra{+}A\ket{+}](./images/683d98384f89e7d001efb7b79e8256acf717bfe8.png) is the ![a_{++}](./images/393e85e950663883b647ba40e74dd3adbe19f7ef.png)\-entry of the matrix representation of ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) with respect to the Hadamard basis ![B_h](./images/ed806363e7593bfb85745e769a27899ad2058cd7.png).

#####[Summary](./Front matter.md)

Dirac notation is a convenient way to represent linear algebra concepts: vectors ![\ket{v}](./images/98612f57381fc1b72beffe8b815efab8ec63ebe6.png) and their Hermitian transposes ![\bra{v}](./images/ae259a2300d0c51f8549370594c407aca58d4777.png), vector coordinates ![\braket{i|v}](./images/d61e76356f74be6d36f3f6a6e3bd2118cbef32f5.png), inner products ![\braket{v|w}](./images/ae6819c5526066501e2b721c7daf8d16d3e5e1ec.png), outer products ![\ketbra{v}{w}](./images/5082636bdc72f57fb46a30a98ffcb81cb9616ee1.png), and matrix entries ![\braket{i|A|j}](./images/36dad597c7b91af91e4a0c052c2b2c385ee4a1cb.png). Because of this expressiveness, Dirac notation is widely used when discussing quantum mechanical topics in modern chemistry, physics, and computer science. In particular, Dirac notation is a core component in the study of quantum mechanics. In fact, we could say that if you understand Dirac notation, you already understand half of quantum mechanics.

###[Exercises](./Front matter.md)

E9.1 Consider the vectors ![\ket{u}=\alpha\ket{0} + \beta\ket{3}](./images/afafb6cc978cbe571c61975067c4f4713871ce74.png) and ![\ket{v}=a\ket{1} + b\ket{2}](./images/8f0f9efb0bec6b80b141969b8a815e027e935313.png), which are elements of ![\mathbb{C}^4](./images/6afc61c3a2c1b3e91bb5f3492fb8c914e49bf19f.png). Express the ket ![\ket{u}](./images/48271bb60580a7878b9dd81944f861dee6c2af5e.png) and the bra ![\bra{v}](./images/ae259a2300d0c51f8549370594c407aca58d4777.png) as four-dimensional coordinate vectors. Indicate whether your answers correspond to row vectors or column vectors.

E9.2 Express the vector ![\vec{w}=(1,i,-1)^\sfT_{B_s} \in \mathbb{C}^3](./images/c21120e7f296239725b767b56a7f6e7ffe0ed66d.png) as a ket ![\ket{w}](./images/d06a6f6b801d000cdbb9977fe35d1a298a334ddd.png) and as a bra ![\bra{w}](./images/3370b2f6555cd46240ff6d259f093cb7c44ca934.png). Compute its length ![\| \vec{w} \| =  \sqrt{ \braket{w|w} }](./images/0a01a72a3dab462003739399009ab86fa910f8d3.png).

E9.3 Find the determinant of the following matrix:

![A = 1 \ketbra{0}{0} + 2 \ketbra{0}{1} + 3 \ketbra{1}{0} + 4\ketbra{1}{1}.](./images/c494896d0e9992d6fddef4da6b04907362424898.png)

E9.4 Consider the vectors ![\ket{u} = \ket{0}](./images/adeaedf54b8377cd3546d90d9a3dc4ae52137ed9.png), ![\ket{v}=\frac{1}{\sqrt{2}}\ket{0} + \frac{i}{\sqrt{2}}\ket{1}](./images/4c94c9f909a52f8e62857c0fc8feb69ee5b07fb1.png), and ![\ket{w}=\frac{1}{\sqrt{5}}\ket{0} - \frac{2}{\sqrt{5}}\ket{1}](./images/f7f8430bd59c70900f473ff53d6f1f8900e1e05d.png). Compute the following expressions:

1.  ![\ket{u}\!+\!\ket{v}](./images/63284d2d25785fa82b3e9c68be64102341359687.png)
2.  ![\|\ket{v}\| \!+\! \|\ket{w}\|](./images/0fa110700940a405884048d7df0801416d1c21b6.png)
3.  ![\braket{u|v}](./images/221f60448c0fe843a023572acb23c60952068096.png)
4.  ![\braket{v|w}](./images/ae6819c5526066501e2b721c7daf8d16d3e5e1ec.png)
5.  ![\braket{w|v}](./images/44c759d38cd4016f56380d0dcd38b8d10d74dbf1.png)
6.  ![\ketbra{u}{u}](./images/6a1ae3011f826038813cb2a2b0320a919973f891.png)
7.  ![\Pi_{\ket{u}\!}(\ket{v})](./images/45c748e83dcffff0da81af21c07591ba4774f9e9.png)
8.  ![\ketbra{v}{v}](./images/6c0faf5d8a1dbac2522019d56fb051fa9706a1a5.png)
9.  ![\Pi_{\ket{v}\!}(\ket{u})](./images/8e506c846199c0460afe8cd4ad4484826ed1e281.png)
10.  ![\Pi_{\ket{v}\!}(\ket{w})](./images/5f9f8cb69db919484ed74e9007eac61e3aee0876.png)

The projection matrix onto a unit vector ![\hat{a}](./images/0fb2a22a7052a151cb3fbfc5b473e61e8ccfeb10.png) is equal to ![\hat{a}\hat{a}^\dagger](./images/a070eca362e06cd48457db396a87ae3917f94224.png).

E9.5 Given the matrix ![A = 1\ketbra{0}{0} + 3\ketbra{0}{1} +4\ketbra{1}{0} +5\ketbra{1}{1}](./images/fe31a95b5a1b7ce8bb12bcb450e8130a736cc7b8.png) and the vectors ![\ket{v}=1\ket{0} + 3\ket{1}](./images/34aafc825a468d3c65bba92fd0a535ab76129105.png) and ![\ket{w}=-3\ket{0} -2i\ket{1}](./images/86add8188ef735d334822ba333b540dd0d285f6c.png), compute:

1.  ![A\ket{v}](./images/c1ebff6214161b7bb13c0e2d15541ee1e8be936c.png)
2.  ![\bra{v}A](./images/50195fd09d25daf7d143b54716d396725dd83fe8.png)
3.  ![A\ket{w}](./images/bcf758cfcbfcf5bad39c0e2420a43731b0ea3c94.png)
4.  ![\bra{v}A\ket{v}](./images/f7d2a6f865363c9666891c0426bb4264b9558267.png)
5.  ![\bra{w}A](./images/bb919fc14232c0cda00d3974c8e28ca087898654.png)
6.  ![\bra{w}A\ket{w}](./images/d9000c387abcdfc478ab1d223a9b2e6240054d34.png)

E9.6 Express the linear transformation ![T(x,y) = (2x+y, -3y)](./images/5b842e5a85b2cc2ef76e22bf89f9048ab6f2b5a1.png) as a matrix that acts on an input vector of the form ![x\ket{0} + y\ket{1}](./images/f2b106cc9fd7018d47e5548e27226a5fb4abd141.png).

##[9.2 Quantum information processing](./Chapter 9_ Quantum mechanics.md)

Digital technology is sought after because of the computational, storage, and communication advantages of manipulating digital information instead of continuous-time signals. Similarly, quantum technology enables certain new advances for computational and communication tasks. This section will equip you with a mental model for thinking about quantum information processing tasks in analogy to a digital information processing pipeline you’re already familiar with: the digitization, compression, and playback of sound recording that we discussed in[Section 7.11.6](./Chapter 7_ Applications.md) (page 7.11.6).

The use of quantum technology for information processing tasks is no more mysterious than the use of digital technology for information processing tasks. Playing a digital recording on your `mp3` player involves a number of processing, conversion, and signal amplification steps. Similarly, using a quantum computer involves several conversion, processing, and measurement steps. In both cases you input some data into a machine, and wait for the machine to process the data and output the answer.

We can think of both digital and quantum technology as black box processes, with internal workings that we can’t access directly. In both cases, the intermediate representation of data is in a format that is unintelligible: we can’t understand what is encoded in quantum states any more than we can understand what is encoded in digital data. For instance, an `mp3` file contains ones and zeros; but, unless we’re unusually gifted, it’s impossible to tell which artist plays the song ![010100101010101000111\ldots](./images/5cdbfadf862b3a5431897ff9a0d705248de39007.png) just by looking at the raw, digital data. To understand information processing in the digital and quantum worlds, we must study the “adaptors”—the processes used to convert the internal data representation into signals we can intelligibly perceive.

To further highlight the parallel structure between digital information processing and quantum information processing, we’ll now review the `mp3` compression task as an example of a digital information processing pipeline.

###[Digital signal processing](./Front matter.md)

A _sound card_ is a computer component that converts between analog signals that we can hear and digital signals that computers understand. The sound card digitizes sound using an analog-to-digital converter (ADC). For music playback, the sound card uses a digital-to-analog converter (DAC), which transforms digital sounds into analog sound vibrations to be played through speakers. The ADC receives signal via the sound card’s line-in and microphone jacks; the DAC outputs sound via the sound card’s line-out and headphone jacks.

![digital-information-processing-pipeline](./images/digital-information-processing-pipeline.png)

Figure 9.9: A digital information processing pipeline for sound recording and playback. Sound vibrations are captured by a microphone and converted to digital form using an analog-to-digital converter (ADC). Next the digital `wav` file is converted to the more compact `mp3` format using digital processing. In the last step, sound is converted back into analog sound vibrations by a digital-to-analog converter (DAC).

[Figure 9.9](./Chapter 9_ Quantum mechanics.md) illustrates a full digital information processing pipeline for sound. We use an _analog-to-digital converter_ (ADC) to transform the analog sound into digital form; the sound’s digital representation is then processed, and finally a _digital-to-analog converter_ (DAC) transforms the digital signal into analog form. If the music encoding, processing, and playback steps are successful, the final output will sound like the original sound recorded.

The grey-shaded region in[Figure 9.9](./Chapter 9_ Quantum mechanics.md) corresponds to digital data. The example of `mp3` compression is just one of many uses of digital processing that become possible once we convert analog information into digital form. Information stored in digital form allows for countless other affordances: the long-term storage of the `mp3` file, the file’s transmission over the internet, or the computation of a digital fingerprint of the song. Mathematically speaking, we can describe any digital information processing task as a function, ![f:\mathbb{Z}_2^n \to \mathbb{Z}_2^k](./images/8c8569bc47f0161eeb1b12a2ca741fb0e9adced5.png), that takes ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-dimensional binary vectors as inputs and produces ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png)\-dimensional binary vectors as outputs.

###[Quantum information processing](./Front matter.md)

In order to understand the context where quantum information processing has applications, we’ll describe a hypothetical scenario. Suppose you’re trying to calculate the output of some mathematical function ![f(x)](./images/9d5dad90bcaf7b324071babae52f24c17f1b7b24.png) for the input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png). Your first approach is to express the math function ![f](./images/8fa270612071570e083551c3f0a79098b082da97.png) as a function in code ![\texttt{f}](./images/d90d0b7e12cf53f7a9cbed99c0d3f6e0c507f8de.png), but you quickly notice that running the code of the function ![\texttt{f}](./images/d90d0b7e12cf53f7a9cbed99c0d3f6e0c507f8de.png) takes too long for the types of inputs you’re interested in. Computing `f(x)` would take a century on your laptop, and even if you ran your code on a powerful cluster of computers, it might still take years to compute the output. Normally people quit at this point.

You’re not a quitter though, so instead of waiting for the classical computer to finish computing ![\texttt{f(x)}](./images/5ebcb45704a875d05af86b3c03ed77c448520534.png), you decide to use a quantum computer.[Figure 9.10](./Chapter 9_ Quantum mechanics.md) shows the sequence of steps needed to operate a quantum computer. Starting from the input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) expressed as a classical bitstring ![x \in \mathbb{Z}_2^k](./images/ee99fb831c2ddc22bea0749e4a357a47ee88be64.png), you use state preparation to encode the input into a quantum vector ![\ket{x} \in \mathbb{C}^m](./images/80076370815358fe6a98106c3a8c557eb55c56ee.png) inside the quantum computer. You can then perform quantum operations on the input state to transform it to an output state ![\ket{y} \in \mathbb{C}^n](./images/e7fc7538dfb1fca275f3996c63a8621bb2a4bd89.png). Finally, you perform a measurement on the output state ![\ket{y}](./images/92529f5c2ec85f225f4ffce32a3a3f5e1984b281.png) to obtain a classical bitstring ![y \in \mathbb{Z}_2^\ell](./images/b2a1801edbc573b1992d53c557100f63c8b05f68.png), which is hopefully the answer you’re looking for.

The main difference between classical and quantum computation is the underlying data types used in the computation. Instead of working with _bits_ and using digital functions ![\texttt{f}:\mathbb{Z}_2^k \to \mathbb{Z}_2^\ell](./images/7c9878e7c474234ca101a4658d4890fa4d407ce1.png), quantum computers work with _qubits_ and use _quantum operations_ ![T:\mathbb{C}^m \to \mathbb{C}^n](./images/4bac4a08b7f026640f26bc04dcd934e4d791a259.png) to perform computations. Quantum computation is more general than classical computation since quantum computers can make use of quantum effects like constructive interference.

The other big difference between classical and quantum computation is that the quantum computer outputs the state ![\ket{y}](./images/92529f5c2ec85f225f4ffce32a3a3f5e1984b281.png) only once. You can think of **quantum measurement as asking a question** about the state ![\ket{y}](./images/92529f5c2ec85f225f4ffce32a3a3f5e1984b281.png). You’re free to perform any measurement, but **you can ask only one question**, since quantum measurements disrupt the state of a system.

![quantum-information-processing-pipeline](./images/quantum-information-processing-pipeline.png)

Figure 9.10: A quantum information processing pipeline. A classical bitstring ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) of length ![k](./images/bd8c78013f1a4c5cfa999dd9c4c7a09100df8aab.png) is used as instructions for preparing an ![m](./images/89bd9dbe770020ab4a4b963d537e5e619b5ee2ef.png)\-dimensional quantum state ![\ket{x}](./images/2a7a5443c8fd91133c20b32ff8f62916ef7ae998.png). Next, quantum operations are performed on the state ![\ket{x}](./images/2a7a5443c8fd91133c20b32ff8f62916ef7ae998.png) to convert it to the output state ![\ket{y}](./images/eba6c309daf45b135386cf577ec7a28af9b7cd20.png). Finally, the state ![\ket{y}](./images/eba6c309daf45b135386cf577ec7a28af9b7cd20.png) is _measured_ to obtain the classical bitstring ![y](./images/863c5d360491e23bb59644eb7d2d7ac1abf65fa1.png) as output.

Quantum processing pipelines are analogous to digital information processing pipelines. The process of _state preparation_ in quantum processing is analogous to the analog-to-digital conversion step in digital processing. In both cases we convert the input to the format required for the processing step. Similarly, quantum _measurements_ correspond to the digital-to-analog conversion step. In both cases we must convert the output to a format we can understand.

In the next section, we’ll discuss the components of the quantum information processing pipeline in more detail. We’ll introduce the four _postulates_ of quantum mechanics, which specify how quantum systems are represented and what we can do with them. The postulates of quantum mechanics roughly correspond to the conversion steps illustrated in[Figure 9.10](./Chapter 9_ Quantum mechanics.md). One postulate defines how quantum states are prepared, another postulate describe the types of operations we can perform on quantum states, and a third postulate formally defines the process of quantum measurement. The next section is the “quantum mechanics explained in the space on the back of an envelope” part alluded to in the introduction of this chapter. We’ve set the scene, introduced Dirac notation, and now we can finally discuss the details of the quantum formalism.

##[9.3 Postulates of quantum mechanics](./Chapter 9_ Quantum mechanics.md)

The _postulates_ of quantum mechanics dictate the rules for working within the “quantum world.” The four postulates define:

-   What quantum states are
-   Which quantum operations can be performed on quantum states
-   How to extract information from quantum systems by measuring them
-   How to represent composite quantum systems

These postulates specify the structure that all quantum theories must have. Together, the four postulates are known as the _quantum formalism_, and describe the math structure common to all fields that use quantum mechanics: physics, chemistry, engineering, and quantum information. Note the postulates are not provable or derivable from a more basic theory: scientists simply take the postulates as facts and make sure their theories embody these principles.

###[Quantum states](./Front matter.md)

Quantum states are modelled as special types of vectors. The _state_ of a ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png)\-dimensional quantum system is a unit vector ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png), in a ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png)\-dimensional complex inner product vector space ![\mathbb{C}^d](./images/8686e292eac775a5afb303d0a06aa39018168f97.png), which we call the Hilbert space. This is the first postulate that belongs on the back of the envelope.

To every isolated quantum system is associated a complex inner product space (Hilbert space) called the _state space_. A state is described by a unit vector in state space.

The following comments apply to the description of quantum systems:

-   The requirement that state vectors must have length one will become important when we discuss the probabilistic nature of quantum measurements.
-   The _global phase_ of a quantum state vector doesn’t matter, which means ![\ket{\psi} = e^{i \theta} \ket{\psi}, \forall \theta \in \mathbb{R}](./images/c60b8c761533861bf8397160d5752cda09f09350.png). The vectors ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png), ![-\ket{\psi}](./images/c2c9d8df2c2d41ac8932a6c139246f9fa6881acf.png), and ![i\ket{\psi}](./images/cf5fedf414389d6f3cbf04cba7f3da36f5818887.png) all represent the same quantum state.
-   Each physical system corresponds to its own Hilbert space, usually denoted with the same label as the system, ![\ket{\psi}_1 \in V_1](./images/81d8637cd5c4a5f0ec9df6b0f279cfab664500e1.png) and ![\ket{\psi}_2 \in V_2](./images/445d81e7c4fcefb29d9e91f6d20037620837f50b.png).

In general, the quantum states of physical systems are represented as vectors in ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png)\-dimensional or sometimes even infinite-dimensional Hilbert spaces. To keep things simple, we’ll focus on two-dimensional quantum systems.

#####[The qubit](./Front matter.md)

In analogy with two-state classical bits ![\in \{0,1\}](./images/9c7e1797d94003415dc9c3bbc9e2654341651841.png) we call two-dimensional quantum systems _qubits_ ![\in \mathbb{C}^2](./images/a8d31162747ea3590130ee96462b52865f5a955d.png), which is short for _quantum bit_. Many physical systems, like the polarization of a photon or the spin of an electron, can be represented as qubits. A qubit is a unit vector in a two-dimensional Hilbert space ![\mathbb{C}^2](./images/a3872a4fb8e558e4f3ec519b05d7eb9f7b7b7d12.png):

![\ket{\psi} =  \alpha\ket{0} +\beta\ket{1},](./images/c0d44579e1dc6c22ae6b22150969c8badaa8f1c4.png)

where

![\begin{align*}
&		\alpha \in  \mathbb{R},  \qquad \qquad \qquad  \text{ (global phase doesn't matter) }  \\
&		\beta \in \mathbb{C},  \\ 
&		|\alpha|^2 + |\beta|^2 =1.
\end{align*}](./images/37f5f51b466352c0fa8378c87680183eda1ae3bc.png)

Recall that ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) and ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png) are the vectors of the standard basis for ![\mathbb{C}^2](./images/a3872a4fb8e558e4f3ec519b05d7eb9f7b7b7d12.png):

![\ket{0} = \colvec{ 1 \\  0}\!,
\qquad
\ket{1} = \colvec{ 0\\  1}\!.](./images/80c121e90f8fc35544d66e9ecae3caea59032849.png)

The restriction that ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) must be a real number follows from the fact that the global phase of a quantum state can be ignored. The condition that a quantum state must have length one is equivalent to the constraint ![|\alpha|^2 + |\beta|^2 =1](./images/48823d1a0eea4c757f6cb8878e9c99b513acea1b.png).

![quantum_state](./images/quantum_state.png)

Figure 9.11: A photon encounters a half-silvered mirror, which is also known as a beam splitter. The photon can take one of the two possible paths, so we describe it as the superposition ![\ket{\gamma} = \tfrac{1}{\sqrt{2}}\ket{0} +\tfrac{1}{\sqrt{2}}\ket{1}](./images/dff7f6603c916d300620188d7633b1f2c2d36d6d.png), where ![\ket{0}](./images/f5eede2beac6072a276e8d8abe4fc0cf90522335.png) describes the photon passing through the mirror, and ![\ket{1}](./images/d3a8693180879df266a7fdaa1ddb0ac5c4a6d190.png) describes the photon being reflected.

Though the notion of a qubit is an abstract concept, many physical systems can embody it. In[Figure 9.11](./Chapter 9_ Quantum mechanics.md), the information of a qubit is encoded in the path a photon takes after it encounters a half-silvered mirror. Qubits are a device-independent representation of quantum information, similar to how classical bits are device-independent representations for classical information. A bit is a bit, regardless of whether it is transmitted over the network, stored in RAM, or stored on a hard drive. Similarly, a qubit is a qubit, regardless of whether it’s encoded in the polarization of a photon, an electron’s spin, or in the direction of magnetic flux of a superconducting loop.

#####[Quantum state preparation](./Front matter.md)

The operation of encoding some classical information into a quantum system is called _state preparation_. Imagine an apparatus that prepares quantum systems in one of several possible quantum states, depending on the position of the “control switch” ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) of the machine.

![quantum-state-preparation](./images/quantum-state-preparation.png)

Figure 9.12: The classical input ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) is used to prepare a quantum system. The quantum state ![\ket{x}](./images/2a7a5443c8fd91133c20b32ff8f62916ef7ae998.png) is produced when the classical input is ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png).

An example of quantum state preparation is a machine that can produce photons in two different polarizations ![\ket{H}](./images/0cbef79e16a72127bd567b54dd2a83ded941ecee.png) and ![\ket{V}](./images/9097d28a02a1d14f8bcedc25919c58a58a63d879.png). If the input ![x=0](./images/c17138fe008c3faa236a74c435e137be4f5aa951.png) is specified, the machine will produce the state ![\ket{H}](./images/0cbef79e16a72127bd567b54dd2a83ded941ecee.png), and if ![x=1](./images/fea10811d28f936dba151b3ac42b4301e3894119.png) is specified as the input, the machine will produce ![\ket{V}](./images/9097d28a02a1d14f8bcedc25919c58a58a63d879.png).

The quantum state preparation step is analogous to the analog-to-digital conversion step; it’s how we get classical information into a quantum computer. Once we have converted the input ![x](./images/59f89ea6383d6a43ea38a038a1484f5ce8cf2526.png) into a quantum state ![\ket{x}](./images/162d2cc27b77bb4e18cb745b46de98ae47f2e529.png), the natural next question to ask is what we can _do_ with ![\ket{x}](./images/162d2cc27b77bb4e18cb745b46de98ae47f2e529.png). What quantum operations are we allowed to perform on quantum states?

###[Quantum operations](./Front matter.md)

The second definition we can write on the back of the envelope is about identifying _quantum operations_ with unitary transformations acting on quantum states. Every quantum operation can be represented as a unitary operation ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) applied to the input state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) to produce the output state ![\ket{\psi^\prime}](./images/177f51fd790c559fc25662980b3d38811e247f3f.png).

![\ket{\psi} 
\longrightarrow 
\boxed{  \! \! \! \begin{array}{c} \text{ U } \end{array} \! \! \!  } 
\longrightarrow
\ket{\psi^\prime}](./images/4f6684d1f048e3995e0ccd0e364e183becbc77ec.png)

The requirement that all quantum operations be unitary is codified in the second postulate of quantum mechanics. Time evolution of an isolated quantum system is unitary. If the state at time ![t](./images/3c7f497fcfa37569f864ab2b1acb531985ae9eb3.png) is ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) and at time ![t^\prime](./images/9b9606b3e1588b3de962d56ea54fc1f92e028cf6.png) is ![\ket{\psi^\prime}](./images/177f51fd790c559fc25662980b3d38811e247f3f.png), then there exists a unitary operator ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) such that ![\ket{\psi^\prime} = U \ket{\psi}](./images/6770b91f1243a6bc90cdadc7ad6a02e3cc4e717a.png). This is a major piece of the quantum puzzle, so let’s analyze what it means: mathematically, physically, and computationally.

First let’s get the math out of the way. Recall that a unitary matrix ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) obeys ![U^{\dagger} U = U U^{\dagger} = \mathbbm{1}](./images/3deaa5a94fca17f1955f1ceab73d1f3aa4481bd2.png). Postulate 2 ensures that quantum states will maintain their unit-length property after quantum operations are performed on them. Assume the quantum system starts from a state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) that has length one, ![\| \ket{\psi} \|^2 = \braket{ \psi | \psi } =~1](./images/d2a89af24d8311c77c3360a7a77b32089e64d665.png). After the unitary ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) is applied, the state after evolution will be ![\ket{\psi^\prime}=U\ket{\psi}](./images/6770b91f1243a6bc90cdadc7ad6a02e3cc4e717a.png) and its squared length will be ![\|\ket{\psi^\prime} \|^2
=  \| U\ket{\psi} \|^2 
= \braket{\psi | U^\dagger U | \psi} 
= \braket{\psi | \mathbbm{1} | \psi}  
=  \braket{\psi | \psi} = 1](./images/7d6ac3bc1fc39986fd72f101470553de40b83f8a.png). In other words, **quantum operations are length-preserving**.

The second postulate refers explicitly to a time variable and the state of the system at different times, which is the physics way of thinking about quantum operations. For example, applying a quantum operation to a real physical system could correspond to applying a certain magnetic field to that system. If applying the magnetic field for one second applies the rotation operation ![R_{\theta}](./images/a9e25f4c67edd30a17ea475457076029ac847e00.png), then applying the magnetic field for two seconds performs the rotation ![R_{2\theta}](./images/6e6585bc6b8c6deeb138c2a7359cf31438032b48.png); therefore the time variable is of central importance to the experiment.

The computer science perspective on the second postulate is more abstract. Instead of counting seconds, computer scientists model quantum operations as discrete “gates” that can be applied to quantum states. Computer scientists describe their quantum algorithms in terms of unitary operators ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png), and they assume there exists a specific physical operation that performs the quantum operation ![U](./images/8b1e3d50bbc03610613bf4d368244eda19c539ba.png) on a real physical qubit system.

In this chapter, we’ll take the computer science approach and think of quantum information processing tasks in terms of applying different gates to quantum states. We’ll now define several quantum gates that perform useful unitary operations on qubits.

#####[Example 1: phase gate](./Front matter.md)

The ![Z](./images/53f6f5c482e34c26d20fc819d706dba659b581dd.png) operator is defined by its action on the vectors of the standard basis.

![Z\ket{0} = \ket{0}, 
\qquad
Z\ket{1} = -1 \ket{1}.](./images/e032a67bec2d1e9b23c6c7c6ff735d78f8bc4234.png)

The ![Z](./images/53f6f5c482e34c26d20fc819d706dba659b581dd.png) operator leaves the ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) unchanged but flips the phase of ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png).

Given knowledge of the actions of the ![Z](./images/53f6f5c482e34c26d20fc819d706dba659b581dd.png) operator on the vectors of the standard basis, we can construct its matrix representations:

![Z 
= 
\tensor[_{B_s}]{
\begin{bmatrix}
1	&	0	\\
0	&	-1	\\
\end{bmatrix}
}{_{B_s}}
=
\ketbra{0}{0}  - \ketbra{1}{1}.](../Images/0212d50513ed0c8b6452a877d3e58633ba9aa0de.png)

#####[Example 2: NOT gate](./Front matter.md)

The ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) operator is defined by the following actions on the vectors of the standard basis:

![X\ket{0} = \ket{1}, 
\qquad
X\ket{1} = \ket{0}.](./images/00198b7a70dd63fb366ce3850d3946790cf14960.png)

The ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) operator acts as a “quantum NOT gate,” changing ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png)s into ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png)s, and ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png)s into ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png)s. The matrix representation of the ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) operator is:

![X 
= 
\tensor[_{B_s}]{
\begin{bmatrix}
0	&	1	\\
1	&	0	\\
\end{bmatrix}
}{_{B_s}}
=
\ket{0}\bra{1}  + \ket{1}\bra{0}.](../Images/266791e5c620bfdfb06b19c75ee858fa75d736b2.png)

#####[Example 3: Hadamard gate](./Front matter.md)

The Hadamard operator takes the vectors of the standard basis to the vectors of the Hadamard basis ![\ket{+} = \frac{1}{\sqrt{2}} (\ket{0} + \ket{1})](./images/a6104af3c18d22ab841cf501713e06c91aafcbb8.png) and ![\ket{-} =  \frac{1}{\sqrt{2}} (\ket{0} - \ket{1})](./images/d997cc0d679b66c6e7d682ceab1e2ed8d3351c8b.png):

![H \ket{0} = \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) = \ket{+}, 
\qquad
H \ket{1} = \frac{1}{\sqrt{2}} (\ket{0} - \ket{1}) = \ket{-}.](./images/8ee0585f85261086e7430a7eddc5e7188d197d7a.png)

You can also think of the ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) operator as a ![45^\circ](./images/bd3d3974358aa0059bc92afb15aa60914b97d2d5.png) counter-clockwise rotation. The matrix representation of the Hadamard gate is

![H 
= 
\tensor[_{B_s}]{	
\left[ \begin{array}{cc}
\frac{1}{\sqrt{2}} 	& \frac{1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}} 	& -\frac{1}{\sqrt{2}}
\end{array} \right]
}{_{B_s}}.](../Images/64c75c65546c9a6e43ca92b918f9cccd105242df.png)

By linearity, we can deduce the effects of the operators ![Z](./images/53f6f5c482e34c26d20fc819d706dba659b581dd.png), ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png), and ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) on an arbitrary qubit ![\alpha\ket{0} +\beta\ket{1}](./images/b4bb13b050275c14ead837c6b0f0f5bebda25cbc.png):

![\begin{align*}
Z ( \alpha\ket{0} +\beta\ket{1} ) 
&= \alpha\ket{0} - \beta\ket{1},						\\
X ( \alpha\ket{0} +\beta\ket{1} ) 
&= \beta\ket{0} + \alpha \ket{1},						\\
H ( \alpha\ket{0} +\beta\ket{1} ) 
&= \tfrac{\alpha+\beta}{\sqrt{2}}\ket{0} \, +  \, \tfrac{\alpha-\beta}{\sqrt{2}}\ket{1}.
\end{align*}](./images/953911f6054687a038032e492b58eb17d209adab.png)

#####[Example 4](./Front matter.md)

The effect of the operator ![XZ](./images/d1f515dda36d8fd406a79a82bf10900c22c8167c.png) corresponds to the combination of the effects of the ![Z](./images/53f6f5c482e34c26d20fc819d706dba659b581dd.png) and ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) operators. We can understand the action of ![XZ](./images/d1f515dda36d8fd406a79a82bf10900c22c8167c.png) either by applying it to an arbitrary qubit ![\alpha\ket{0} +\beta\ket{1}](./images/b4bb13b050275c14ead837c6b0f0f5bebda25cbc.png):

![XZ ( \alpha\ket{0} +\beta\ket{1} ) 		= 		- \beta\ket{0} + \alpha\ket{1},](./images/9b0429b408e102766653b14f67043d817b620102.png)

or by multiplying together the operator’s matrix representations:

![XZ=
\tensor[_{B_s}]{
\begin{bmatrix}
0	&	1	\\
1	&	0	\\
\end{bmatrix}
}{_{B_s}}
\tensor[_{B_s}]{
\begin{bmatrix}
1	&	0	\\
0	&	-1	\\
\end{bmatrix}
}{_{B_s}}
=
\tensor[_{B_s}]{
\begin{bmatrix}
0	&	-1	\\
1	&	0	\\
\end{bmatrix}
}{_{B_s}}.](../Images/ad5d223d419878166a6809e600cb9306d85dde15.png)

In general, it is possible to perform many quantum operations and combinations of operations when working with quantum states. The examples presented above represent the most commonly used operations. Note that unitary time evolution is invertible: for every quantum gate ![G](./images/3c639e0c43a4a7d5f6c91083c88c6bb9184f59da.png) there exists an inverse gate ![G^{-1}](./images/2124fabe0ea6512e6171b1a4901ad49fe7ae902a.png) such that ![G^{-1}G = \mathbbm{1}](./images/45473845204ae8e37407ad0815f73484252a1002.png).

####[Links](./Front matter.md)

\[ Wikipedia article on quantum gates \]

[`https://en.wikipedia.org/wiki/Quantum_gate`](./Quantum_gate.md)

####[Exercises](./Front matter.md)

E9.7 The Hadamard gate is defined as ![H=\tfrac{1}{\sqrt{2}}
\begin{bmatrix}
1		& 1	\\
1		& -1
\end{bmatrix}](./images/5c7b71e281efb77ce0386aecde2ecb3d4149ab12.png). Compute the effect of the operator ![HH](./images/cba43778ee4f8615e85da75c85b26aba1d086733.png) on the vectors of the standard basis ![\{ \ket{0}, \ket{1} \}](./images/0433fdf95be980a035da81addd049f24c61576cb.png).

E9.8 Compute ![XX](./images/1764197ec6baf99f3d69b051d98b797979e38423.png), ![XZ](./images/d1f515dda36d8fd406a79a82bf10900c22c8167c.png), and ![ZX](./images/037f2edb2a4df8e5a79d4fa1781f051643e72293.png).

So far, we’ve filled half the space on the back of the envelope. It’s time to talk about the third fundamental idea in quantum mechanics: quantum measurements.

###[Quantum measurements](./Front matter.md)

A quantum measurement performed on a quantum system corresponds to a collection of projection operators ![\{ \Pi_i \}](./images/7a54549e80fc0c3b4f9cebad376bdf462d60260b.png) that act on the Hilbert space. A measurement with ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) possible outcomes is represented by ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) projection operators ![\{\Pi_1, \Pi_2, \ldots, \Pi_n\}](./images/09e18de030a112bd715ce861e37ffefe5412959f.png). The projection operators form a _decomposition of the identity_, meaning their sum is equal to the identity matrix:

![\sum_{i=1}^n \Pi_i = \mathbbm{1}.](./images/1500f4e3fcca84af3d30536b5bc24655701641ea.png)

Intuitively, the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) different projection operators correspond to ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) different alternatives for the evolution of the quantum system. Performing the measurement is like asking “which way is it going to be?” and letting the system decide which path it wants to take. _Born’s rule_ is used to assign probabilities to different measurement outcomes.

A quantum measurement is modelled by a collection of projection operators ![\{\Pi_i \}](./images/7a54549e80fc0c3b4f9cebad376bdf462d60260b.png) that act on the state space of the system being measured and satisfy ![\sum_i \Pi_i = \mathbbm{1}](./images/2d1b3689bc2064fb3ae9413e0465e2186b7d4a82.png). The index ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) labels the different measurement outcomes.

The probability of outcome ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) when performing measurement ![\{\Pi_i \}](./images/7a54549e80fc0c3b4f9cebad376bdf462d60260b.png) on a quantum system in the state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) is given by the squared length of the state after applying the ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png)th projection operator:

![\textrm{Pr}\!\left(\{ \textrm{outcome } i \textrm{ given state } \ket{\psi} \} \right)
\; \eqdef \; 		\Big\| \Pi_i \ket{\psi} \Big\|^2
\qquad \; \; 					\textrm{(Born's rule).}](./images/a6ae743b036516158d44c3c1be7d2aed83c9dc5f.png)

When outcome ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) occurs, the post-measurement state of the system is

![\ket{\psi^\prime_i}
\; \eqdef \; 
\frac{	\Pi_i \ket{\psi}
}{
\| \Pi_i \ket{\psi} \|
}.](./images/195856608f042d7634b0e997043ce251a9277b41.png)

Let’s unpack this definition to see what is going on.

#####[Born’s rule](./Front matter.md)

For the measurement defined by the projection operators ![\{\Pi_1, \Pi_2, \ldots, \Pi_n\}](./images/09e18de030a112bd715ce861e37ffefe5412959f.png), Born’s rule states that the probability of outcome ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) is ![\braket{\psi | \Pi_i  | \psi}](./images/9b7ca68e8fe7e82269d7d4348b8075a0f2dcd4c8.png).

This expression for the squared norm of the overlap between ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) and ![\Pi_i](./images/cc4312dcc34f2c08bf9fec4f70595143d3dc5ec7.png) can be written in several equivalent ways:

![\Big\| \Pi_i \ket{\psi}  \Big\|^2
= \left( \Pi_i \ket{\psi},  \Pi_i \ket{\psi} \right) 
= \braket{ \psi | \Pi_i  \Pi_i   | \psi }
= \braket{ \psi | \Pi_i   | \psi },](./images/bcb22b6663d9457fd267805e1364123688d82929.png)

where the last equality follows from the idempotence property of projectors ![\Pi_i = \Pi_i^2](./images/9824347c8662e5a3a6fa6276fb09faf8893a4d92.png). The last expression, where the projection operator is “sandwiched” by two copies of the quantum state, is the physicist’s usual way of expressing Born’s rule by defining ![\textrm{Pr}\!\left(\{ \textrm{outcome } i \} \right) \eqdef \braket{ \psi | \Pi_i   | \psi }](./images/472cfaad005fdaef9b4ceb8ad67171764fb6a648.png). For the class of projective measurements we’re discussing here, the two definitions are equivalent.

The set of projection operators ![\{\Pi_1, \Pi_2, \ldots, \Pi_n\}](./images/09e18de030a112bd715ce861e37ffefe5412959f.png) forms a decomposition of the identity ![\mathbbm{1} = \sum_i \Pi_i](./images/f6c4406091235840dcc770fc1aca180cbce4b08a.png). This guarantees that the probability distribution of the different outcomes is normalized:

![\begin{align*}			
1 = \| \mathbbm{1} \ket{\psi} \|^2
&= \left\| ( \Pi_1 + \cdots + \Pi_n  ) \ket{\psi} \right\|^2 					\\
&\overset{\scriptscriptstyle \textrm{py}}{=}  \left\| \Pi_1 \ket{\psi} \right\|^2  + \cdots + \left\| \Pi_n  \ket{\psi} \right\|^2	\\
&= \textrm{Pr}\!\left(\{ \textrm{outcome } 1 \} \right)
+ \cdots +
\textrm{Pr}\!\left(\{ \textrm{outcome } n \} \right).
\end{align*}](./images/ced1f0bcd27f09ec4687ebcb9184a3b1417dd718.png)

That’s good to check; otherwise Kolmogorov would be angry with us. Note the equality labelled ![\overset{\scriptscriptstyle \textrm{py}}{=}](./images/f02b55f4648c6ba50e63e6467efdfaa010281424.png) follows from Pythagoras’ theorem; we’re using the fact that the operators ![\{\Pi_i\}](./images/7a54549e80fc0c3b4f9cebad376bdf462d60260b.png) are mutually orthogonal.

#####[Post-measurement state](./Front matter.md)

When outcome ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) occurs, Postulate 3 tells us that the state of the quantum system becomes ![\ket{\psi^\prime_i} = \frac{ \Pi_i \ket{\psi} }{ \| \Pi_i \ket{\psi} \|}](./images/b89b8b6d496d4c63f439334b61e4eebc6ea3b8df.png), which is the result of applying the projection ![\Pi_i](./images/cc4312dcc34f2c08bf9fec4f70595143d3dc5ec7.png) to obtain ![\Pi_i \ket{\psi}](./images/4d14927e7dcd040efdcbfae85ab435cded348263.png), and then normalizing the state so that ![\|\ket{\psi^\prime_i}\| = 1](./images/e4484c263537ffa69c37d0713bb7c53343dc6071.png).

Measurements are not passive observations! Quantum measurement is an invasive procedure that typically changes the state of the system being measured. In general, the quantum state after the measurement will not be the same as the state before the measurement:

![\ket{\psi^\prime_i} \; \neq \;  \ket{\psi},](./images/bd24e2b8ae7f2ac23bf4ef2eedf610a05ca64d2f.png)

and we say the state is _disturbed_ by the measurement, (though it’s possible that ![\ket{\psi^\prime_i} =\ket{\psi}](./images/9b83d9e11a88b7d47cb5809a3bc1c38a2440449c.png) when the input state lives entirely within the image space of one of the projection operators ![\ket{\psi^\prime_i} =\Pi_i\ket{\psi}=\ket{\psi}](./images/55e9de8c3db9e4711855abce24b3318fe0360345.png)).

A quantum measurement is an interaction that creates classical information and destroys quantum information. By measuring, we obtain the classical information ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) that tells us which outcome occurred, but we disturb the initial state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png), forcing the quantum state into the “aligned with ![\Pi_i](./images/cc4312dcc34f2c08bf9fec4f70595143d3dc5ec7.png)”-state ![\ket{\psi^\prime_i}](./images/07afba28bc257b87f9ff22063883df85586994a0.png). We can still carry out further experiments with the post-measurement state ![\ket{\psi^\prime_i}](./images/07afba28bc257b87f9ff22063883df85586994a0.png), but it’s not the same as the initial state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png). Specifically, we’ve lost all the information about ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) that used to exist in the subspace ![(\mathbbm{1} - \Pi_i)](./images/b5f3ef543bccefbf942262ad17b29e63dcad9857.png).

Another way to describe what happens during a quantum measurement is to say the state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) _collapses_ into the state ![\ket{\psi^\prime_i}](./images/07afba28bc257b87f9ff22063883df85586994a0.png). This is the terminology used by physicists to describe the effects of the projection that occurs during a measurement. Before the measurement, the quantum state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) could be any vector, but after we observe the outcome ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png), we know the state has “collapsed” and is now confined to the image subspace of the projection operator ![\Pi_i](./images/cc4312dcc34f2c08bf9fec4f70595143d3dc5ec7.png). We won’t use the terminology of state collapse in this chapter, because the term “projection” more accurately describes what’s happening.

Historically, the founders of quantum mechanics chose some rather poor terminology to describe quantum measurements. In addition to “collapse,” they also used the term “observer” to describe whomever observes the outcome ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) of a quantum measurement experiment. Trying to understand quantum mechanics using this terminology often leads to magical thinking and anthropomorphizing of the underlying physical events. Proponents of pop-psychology ideas have latched onto the term “observer” to suggest that the collapse of quantum states that occurs during quantum measurements is caused by the presence of human consciousness. Watch out for that fluff.

A more grounded way to think about quantum measurement is in terms of _interaction_ between the quantum state of a particle and a classical measurement apparatus that can be in one of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) possible states. Due to the relative size of the two interacting systems (tiny quantum system and large measurement apparatus), the state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) is forced to “align” with one of the ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) possible states of the measurement apparatus.

#####[Example 4](./Front matter.md)

In Figure ![\ref{fig:MirrorWDets}](./images/435770780a968ea31912a1c1e942412e26579649.png) a state vector ![\ket{\psi} = \alpha \ket{0} + \beta \ket{1}](./images/5793fb1477cd6223587ef6ff0ef9f6d39fb7403f.png) is measured with photo detectors modelled as projectors given by

![\begin{array}{lccr}
\Pi_0 = \ketbra{0}{0}& \quad & \quad & \sum_j \Pi_j = \mathbbm{1} \\
\Pi_1 = \ketbra{1}{1}&
\end{array}](./images/85bb2872410430f9cd610edb8957d02589269338.png)

![\begin{align*}
\textrm{Pr}( \{0 \} | \psi) 
&= 	\textrm{Pr}\!\left(\{ \textrm{outcome } 0 \textrm{ given state } \ket{\psi} \} \right)				\\
&= 	\bra{\psi} \; \; \quad \Pi_0 \quad \; \,  \ket{\psi} 										\\
&=   		\bra{\psi} \quad \ketbra{0}{0} \quad \ket{\psi} 										\\
&=  		( \overline{\alpha} \bra{0}+ \overline{\beta} \bra{1})  \, \ketbra{0}{0} \, ( \alpha \ket{0} + \beta \ket{1} )  	\\
&= 		\overline{\alpha} \alpha 															\\
&= 		| \alpha |^2.
\end{align*}](./images/4a6b96385e1471d815c032656839436dee7678ea.png)

The probability of outcome ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) is ![\textrm{Pr}( \{1 \} | \psi)  = \bra{\psi} \Pi_1 \ket{\psi} =   | \beta |^2](./images/43efbf18d0ae78e6aa2ad993811d7fb80e9c5ff6.png). After the measurement, the quantum system exists in one of two possible states: ![\ket{\psi^\prime_0}= \ket{0}](./images/be91ea2945314b465a6e1009b118128ac62fe4bd.png) or ![\ket{\psi^\prime_1}=\ket{1}](./images/63a73c8ababcc7cd588cf1c8ca4ea52226e1469b.png).

#####[Example 5](./Front matter.md)

Consider the measurement ![\{ \Pi_+, \Pi_- \}](./images/bf3150dea76b004aeab6757253812a74cd7e26ba.png) that consists of the projectors onto the Hadamard basis:

![\begin{array}{lccr}
\Pi_+ = \ketbra{+}{+} & \quad & \quad & \Pi_+ + \Pi_-  = \mathbbm{1} \\
\Pi_- = \ketbra{-}{-} &
\end{array}](./images/fc578e99caa8415c2bf02349c215b007241b6003.png)

Given the quantum state ![\ket{\psi} =  \alpha \ket{0} + \beta \ket{1}](./images/5793fb1477cd6223587ef6ff0ef9f6d39fb7403f.png), the probability of outcome “![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png)” is given by

![\begin{align*}
\textrm{Pr}( \{ + \} | \psi) 
&= \left\|  \Pi_+  \ket{\psi}	\right\|^2 								\\
&= \left\|  \ketbra{+}{+} 	\ket{\psi} \right\|^2							\\
&= \left\|  \ketbra{+}{+} 	( \alpha \ket{0} + \beta \ket{1} ) \right\|^2			\\
&= \left\| \ket{+} 		( \alpha \braket{+|0} + \beta \braket{+|1} )\right\|^2	\\
&= \left\| \ket{+} 		\left( \alpha \tfrac{1}{\sqrt{2}}  \; \,  +  \beta\tfrac{1}{\sqrt{2}} \right) \right\|^2	\\
&= \frac{|\alpha  + \beta|^2}{2} \left\| \ket{+} \right\|^2						\\
&= \frac{|\alpha  + \beta|^2}{2}.
\end{align*}](./images/955c89e121d8f416d7767145860a2f8951b0e003.png)

The probability of outcome “![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png)” is ![\textrm{Pr}( \{ - \} | \psi)  = \frac{|\alpha  - \beta|^2}{2}](./images/0c8d7023d1afdb5c2f9e858c73bfa23d0eddabbc.png). After the measurement, the quantum system is in one of two possible states: ![\ket{\psi^\prime_+}= \ket{+}](./images/0b817859a5cb54c3e80384bdb5d080b04e729822.png) or ![\ket{\psi^\prime_-}=\ket{-}](./images/c67cf3ae1763baa6e83eab39da9bcac0f3e2ba95.png).

![quantum_state_measured](./images/quantum_state_measured.png)

Figure 9.13: The state of a photon after encountering a ![(1-\alpha)](./images/d566f5af866ee03cdef3d46a3ac7db92213c7470.png)\-silvered mirror is ![\ket{\gamma} = \alpha\ket{0} + \beta\ket{1}](./images/8344257f00c3a648221b19d03fcc634f0917c549.png). The probability that the horizontal photodetector “clicks” is ![|\alpha|^2](./images/530dc6a8c190e76fb182a50fa6aa4135c8cb6f05.png), and is obtained by projecting ![\ket{\gamma}](./images/c164185d0f0c061c3244572da95b2661c430a4dd.png) on the subspace ![\ketbra{0}{0}](./images/cbe4d8dc6bcbd4cfc6eff892d535896980af8317.png). The probability that the top photodetector clicks is equal to ![|\beta|^2](./images/92e77b300bcc97f19c74805096a6e089622e06e6.png), and is obtained by projecting ![\ket{\gamma}](./images/c164185d0f0c061c3244572da95b2661c430a4dd.png) on the subspace ![\ketbra{1}{1}](./images/7283eb4c05865538827bd9fddd78583e756042cc.png).

The measurement process is a fundamental aspect of quantum models. You’ll need to acclimate to the idea that measurements change systems’ states. It’s not magic; it’s a phenomenon that occurs due to the relative size of the systems (tiny quantum particles and huge measurement apparatus), and the fact that measurements force quantum and classical systems to interact.

###[Composite quantum systems](./Front matter.md)

So far we discussed state preparation, quantum operations, and quantum measurements of individual qubits. There’s just enough room on the back of our envelope to discuss quantum models for systems made of multiple qubits.

Classically, if we have two bits ![b_1\in \{0,1\}](./images/0276b106256e664ce7081a8e02e84fe4d493e7bf.png) and ![b_2\in \{0,1\}](./images/9642cc0ee96b7ec49af11601cd285b8661359881.png), we can concatenate them to obtain a bit string ![b_1b_2 \in \{0,1\}^2](./images/680b1f3028a34347ec15320a013a654fc36dc088.png), which can have one of four possible values: ![00](./images/d737fc1eb1e6358db3d3491d32ff01428830802f.png), ![01](./images/269addefdc26046581e330cf5538e0e5bc5c5997.png), ![10](./images/fd39ea446d2046417cbd0fc131073609dd557e3d.png), and ![11](./images/8081ad598b8cb7c04afb5db089c6a193f900a516.png). The combined state of two qubits ![\ket{\varphi_1} \in \mathbb{C}^2](./images/0b85f5515dd3a217592ff42b2aa818eba2be4ca9.png) and ![\ket{\varphi_2} \in \mathbb{C}^2](./images/30ba228d09f77272f6eeee67931ba7954c69ce3a.png) is the _tensor product state_ ![\ket{\varphi_1} \otimes \ket{\varphi_2}](./images/a23791ce613c0690d7ace665de6a82b2f6a658b6.png) in the four-dimensional _tensor product space_ ![\mathbb{C}^2 \otimes \mathbb{C}^2 = \mathbb{C}^4](./images/054ea94a0cacaab0b271826ceff78bc69ea8a7a1.png). A basis for the tensor product space can be obtained by taking all possible combinations of the basis vectors for the individual qubits: ![\{ \ket{0}\otimes\ket{0}, \, \ket{0}\otimes\ket{1}, \, \ket{1}\otimes\ket{0},  \, \ket{1}\otimes\ket{1} \}](./images/dd79d691218d87b4c2535feda223a9dfd074686b.png).

The state space of a composite quantum system is equal to the tensor product of the state spaces of the individual systems. If systems ![1,2,\ldots,n](./images/7a02bfdfa6f2ce155403fbffa860cfb10171bc17.png) exist in states ![\ket{\varphi_1}, \ket{\varphi_2},\cdots,\ket{\varphi_n}](./images/6f5eaa7758cf6c651b98ff92043a64865cf5da93.png), then the state of the composite system is ![\ket{\varphi_1} \otimes
\ket{\varphi_2} \otimes \cdots \otimes \ket{\varphi_n}](./images/42293170eab216ee8c96a295d851a23230085250.png).

Postulate 4 tells us how we can combine the state spaces of different quantum systems to describe a composite system. Many interesting quantum applications involve operations on multiple qubits and are described by vectors in a tensor product space, so let’s look more closely at this “![\otimes](./images/60b5df432c9aa653a66fb2cddc4f588b4b119172.png)”-thing.

#####[Tensor product space](./Front matter.md)

If you’d never heard of _tensor products_ before, don’t worry—the only scary part is the tensor product symbol “![\otimes](./images/60b5df432c9aa653a66fb2cddc4f588b4b119172.png),” which we’ll explain in this section. A _tensor product space_ consists of all possible combinations of the basis vectors for the two subspaces. For example, consider two qubits ![\ket{\varphi_1} \in V_1 = \mathbb{C}^2](./images/bf2a84f72d1318dde7cf6cb8b735e00ff86ad75a.png) and ![\ket{\varphi_2} \in V_2 = \mathbb{C}^2](./images/e88ca7e0e1db9eca8f75368a95e4c78f8782f018.png). We’ll denote the standard basis for ![V_1](./images/d5c2ea480bc621ea9e17c050369ce2500b7dbac0.png) as ![B_1 = \{ \ket{0}_1, \ket{1}_1 \}](./images/1e70a184ae0218212660fe74c66c6e06cca03e1c.png) and the standard basis for ![V_2](./images/2afb7677b53adc5b4a76fcb7be639aed65b1bc2a.png) as ![B_2 = \{ \ket{0}_2, \ket{1}_2 \}](./images/bf9d207d06b18bc95644fb74af30b02c869afe3b.png). The tensor product space ![B_{12} = V_1 \otimes V_2](./images/4c6f34391d1514365d4d2658a5f1e6b7836b1114.png) is four-dimensional and has the following basis:

![B_{12} =
\big\{ 
\ket{0}_1\!\otimes\!\ket{0}_2,  \; 
\ket{0}_1\!\otimes\!\ket{1}_2, \; 
\ket{1}_1\!\otimes\!\ket{0}_2, \; 
\ket{1}_1\!\otimes\!\ket{1}_2 
\big\}.](./images/f7fb86f011dfa7785658e0037a8d28abd4a7816d.png)

This level of subscripts and the explicit use of the symbol ![\otimes](./images/60b5df432c9aa653a66fb2cddc4f588b4b119172.png) hurts the eyes (and the hand if you must use this notation to solve problems). It’s therefore customary to drop the subscripts, omit the tensor product symbol, and draw a single ket that contains a “string” of indices:

![\ket{a}_1\!\otimes\!\ket{b}_2
=
\ket{a}\!\otimes\!\ket{b}
=
\ket{a}\ket{b}
=
\ket{ab}.](./images/5d6bb1e3b3fec037f45811284f983a2f80da2dee.png)

The basis for the tensor product space ![B_{12} = V_1 \otimes V_2](./images/4c6f34391d1514365d4d2658a5f1e6b7836b1114.png) looks much nicer in the simplified notation:

![B_{12} =
\big\{ 
\ket{00}, \; 
\ket{01}, \; 
\ket{10}, \; 
\ket{11}
\big\}.](./images/608b73554f6c842ab6301f66995731e1d950f038.png)

#####[Tensor product of two vectors](./Front matter.md)

Suppose we’re given two qubits with states described by the following vectors:

![\ket{\varphi_a}_1 = \alpha_1 \ket{0}_1 + \beta_1\ket{1}_1,
\qquad 
\ket{\varphi_b}_2 = \alpha_2 \ket{0}_2 + \beta_2\ket{1}_2.](./images/b871b34b81129f7ae848ae09fa9fd27ff9e3af58.png)

Note the subscripts indicate which system we’re describing: ![\ket{0}_1](./images/d004f24a3984b121a2a29541429795f7a8f3fec0.png) is the state ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) for the first qubit, while ![\ket{0}_2](./images/8276b826bb724099bd4a82ff1f14350a4bd09d85.png) is the state ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) of the second qubit.

The state of the combined system is the tensor product state ![\ket{\varphi_{ab}}_{12} = \ket{\varphi_a}_1 \otimes \ket{\varphi_b}_2](./images/15e6ae1fc4a71b5e397b6ebc5ade00bed7edbe29.png), which is computed by combining all possible combinations of the components of ![\ket{\varphi_a}_1](./images/bd2a85e99d7d38f49e812da6069ba3d14e4993da.png) and the components of ![\ket{\varphi_b}_2](./images/7c7463076cc40fb83a3470b8d602a03cb3ee1a2f.png):

![(\alpha_1, \;  \beta_1)_{B_1}
\otimes
( \alpha_2, \; \beta_2)_{B_2}
=
\left( \alpha_1\alpha_2,  \; 
\alpha_1\beta_2, \; 
\beta_1\alpha_2,  \; 
\beta_1\beta_2\right)_{B_{12}}.](./images/6f5ac1fc67ae67a8dc21083f1d50b9012d86cc88.png)

The notion of “all possible combinations” is easier to see by considering the tensor product operation in terms of the basis vectors:

![\begin{align*}
\ket{\varphi_{ab}}_{12} 	&= \ket{\varphi_a}_1 \otimes \ket{\varphi_b}_2			\\
&= (\alpha_1 \ket{0}_1 + \beta_1\ket{1}_1) 
\otimes (\alpha_2 \ket{0}_2 + \beta_2\ket{1}_2) 		\\
&= \alpha_1\alpha_2 \ket{0}_1\ket{0}_2 
+ \alpha_1\beta_2 \ket{0}_1\ket{1}_2 
+ \beta_1\alpha_2  \ket{1}_1\ket{0}_2 
+ \beta_1\beta_2\ket{1}_1\ket{1}_2 		\\
&= \alpha_1\alpha_2 \ket{00}
+  \alpha_1\beta_2 \ket{01}
+ \beta_1\alpha_2  \ket{10}
+ \beta_1\beta_2\ket{11}				\\
&= \left( \alpha_1\alpha_2,  \; 
\alpha_1\beta_2, \; 
\beta_1\alpha_2,  \; 										
\beta_1\beta_2\right)_{B_{12}},
\end{align*}](./images/74c520eefc5b184552df2e9d5a35da903fd3644d.png)

where ![B_{12} = \{ \ket{00}, \ket{01}, \ket{10}, \ket{11} \}](./images/395935aa4260c38a6a8824d7a18cbccb4e61b313.png) is the standard basis for the tensor product space.

#####[State spaces and dimension counting](./Front matter.md)

A quantum state that consists of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) qubits can represent any unit vector in ![\mathbb{C}^{2^n}](./images/b06ee14dcf8bb42b7e7dc9a9dc8d09682f399a34.png). That’s an insanely big state space—a huge ![2^n](./images/83a434c6b4b6e3fe6ea82f7a52dddf16f2446ee7.png)\-dimensional playground. In comparison, a classical bitstring of length ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) can take on one of ![2^n](./images/83a434c6b4b6e3fe6ea82f7a52dddf16f2446ee7.png) values. Let’s compare the state space of a two-bit classical register ![R](./images/c58f33ef2152adc5d14064267ac226f58f430242.png) with the state space of a two-qubit quantum register ![\ket{R}](./images/34310ed41afb29588e9886a7eb8477847a919dde.png). The classical register can take on one of four possible values:

![R \in \{ 00, 01, 10, 11 \},](./images/56bbe65bc95a70293544af703f9df83963f76471.png)

whereas the quantum register ![\ket{R}](./images/34310ed41afb29588e9886a7eb8477847a919dde.png) can be any unit vector in ![\mathbb{C}^4](./images/6afc61c3a2c1b3e91bb5f3492fb8c914e49bf19f.png). Similar to a classical registers, the standard basis for the state space of a two-qubit quantum register also consists of four basis vectors:

![\ket{00}\!=\! (1,0,0,0), \; 
\ket{01}\!=\! (0,1,0,0), \; 
\ket{10}\!=\! (0,0,1,0), \; 
\ket{11}\!=\! (0,0,0,1),](./images/24c5d9076f71876c65c739812efc8c727b6585dd.png)

but the quantum register can also represent superpositions of the basis states like ![\ket{R} = (\tfrac{1}{\sqrt{2}}, \tfrac{1}{\sqrt{2}}, 0, 0)](./images/777a762f7af035a9c8aa49c02a582403c47aaf03.png) or ![\ket{R} = (\tfrac{1}{\sqrt{3}}, \tfrac{1}{\sqrt{3}}, \tfrac{1}{\sqrt{3}}, 0)](./images/8685a581d8b0ca8053d0b23ae6f6bd090aec4a5f.png).

Using a very large vector space to represent states does not necessarily make a model more powerful, but the large dimension of the tensor product space suggests many new possibilities. Much of the recent excitement in the area of quantum computing is based on the promise of using the qubits of a quantum computer to perform computations in very large quantum state spaces. We shouldn’t get carried away with enthusiasm, because with great state space comes great noise. It’s easy to imagine ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) qubits in a row in a mathematical model, but building a physical system that can store ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) qubits and protect them from noise is a much more difficult task. Another bottleneck in quantum computing is the difficulty of extracting information from quantum systems. The quantum state space of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) qubits is ![\mathbb{C}^{2^n}](./images/b06ee14dcf8bb42b7e7dc9a9dc8d09682f399a34.png), but projective measurements of the form ![\{\Pi_1,\Pi_2,\ldots,\Pi_m\}](./images/e923b21b54223b04891a3b38ddbbe84a9ca78d5c.png) can only obtain _one_ answer to a question with ![m](./images/a5650ddf125db11e575747a6ea31f2fd574c5803.png) possible classical outcomes (![m \leq 2^n](./images/6b0f36eb5a9de86da3b37f229680093d7c91ff11.png)). We’ll learn more about theoretical and practical considerations for quantum computing in[Section 9.6](./Chapter 9_ Quantum mechanics.md).

###[Exercises](./Front matter.md)

E9.9 Show that the quantum state ![\ket{0}\ket{1} - \ket{1}\ket{0}](./images/b45d988423007a174cb64210d5a79189c74efd31.png) is equal to the quantum state ![\ket{+}\ket{-} - \ket{-}\ket{+}](./images/15d509794a5e2b8959572a5673c99d5a80e132f0.png).

Express ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) and ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png) in the basis ![\{ \ket{+}, \ket{-} \}](./images/5e1996145b5be00fb9a3058418c66a821d664108.png).

###[Quantum entanglement](./Front matter.md)

At the risk of veering further off-topic for a linear algebra book, we’ll now briefly describe _entangled_ quantum states. In particular, we’ll discuss the properties of the _entangled state_ ![\ket{\Psi_-} = \frac{1}{\sqrt{2}}(\ket{01} - \ket{10})](./images/db57c8961a0d9969fc6d6a5f36f476149fcb3def.png). Entanglement is some really crazy stuff, and some of the most fascinating results in quantum information science make use of pre-shared entangled states.

In[Section 7.9](./Chapter 7_ Applications.md) we discussed how a secret key shared between two parties, Alice and Bob, can function as a _communication resource_ used to achieve private communication (via the one-time pad cryptosystem). You can think of entanglement as another type of communication resource: a stronger-than-classical correlation between two parts of a quantum system. One half of the system is controlled by Alice, the other half is controlled by Bob. When the collective state of a two-qubit quantum system is in the entangled state ![\frac{1}{\sqrt{2}}(\ket{01} - \ket{10})](./images/ec86101acb0d7e41db3c786078cb0024b7078979.png), measuring the individual qubits will produce anti-correlated results _in any basis_.

#####[Example 7](./Front matter.md)

The Einstein-Podolsky-Rosen (EPR) state is a two-qubit quantum state with interesting _nonlocal_ properties. We assume Alice controls one half of the quantum state, and Bob controls the other half of the following state:

![\ket{\Psi_-}^{AB}
= \tfrac{1}{\sqrt{2}}\ket{0}^{A}\ket{1}^{B}   -   \tfrac{1}{\sqrt{2}}\ket{1}^{A}\ket{0}^{B}.](./images/3f3271cf4a95eb8d13067c2f336ac1db8bd7ab26.png)

Note the use of superscripts to denote which party controls each part of the system.

Let’s analyze the different measurements Alice and Bob can perform on this state. If Alice measures her system in the basis ![\{ \ket{0}, \ket{1}\}](./images/0433fdf95be980a035da81addd049f24c61576cb.png), the projection operators that correspond to the two outcomes are

![\Pi^{AB}_0 	= \ketbra{0}{0}^{A} \otimes \mathbbm{1}^{B}
\qquad
\textrm{and}
\qquad
\Pi^{AB}_1 	= \ketbra{1}{1}^{A} \otimes \mathbbm{1}^{B}.](./images/aacaaace61759f06ad13216597537fcdb2861740.png)

Since only Alice’s half of the state is measured, the measurement acts like the identity operator on Bob’s half of the state. There’s a ![50](./images/2b10670a50c0a575208a1161c74c474f9d35032c.png)\-![50](./images/2b10670a50c0a575208a1161c74c474f9d35032c.png) chance of outcomes ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) and ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png):

![\textrm{Pr}(0| \Psi_-)
=
\bra{\Psi_-} \Pi^{AB}_0 \ket{\Psi_-} = \tfrac{1}{2},
\quad
\textrm{Pr}(1| \Psi_-)
=		
\bra{\Psi_-} \Pi^{AB}_1 \ket{\Psi_-} = \tfrac{1}{2}.](./images/a932d5bb84a84a7f625fb8e7c4d2dbf38391e2ad.png)

Depending on the outcome, the post-measurement state of the system will be either ![\ket{0}^{A}\ket{1}^{B}](./images/32a2194ab9d20e6116e88777e0b3658f3f53c7f2.png) or ![\ket{1}^{A}\ket{0}^{B}](./images/6e2ee5db385a7ca9d74e5cba0d3f22df3848c907.png). If Bob then measures his half of the system, he’ll obtain the outcome opposite Alice’s. In other words, the measurement outcomes that Alice and Bob obtain are perfectly anti-correlated.

What if Alice and Bob choose to measure their respective halves of the EPR state ![\ket{\Psi_-}^{AB}](./images/91ab6f8fc88f9efcf0f07744de271505017e17b4.png) in the basis ![\{\ket{+},\ket{-} \}](./images/5e1996145b5be00fb9a3058418c66a821d664108.png)? Using some basic calculations (see Exercise [9.3.5](./Chapter 9_ Quantum mechanics.md)), we can express the EPR state ![\ket{\Psi_-}^{AB}](./images/91ab6f8fc88f9efcf0f07744de271505017e17b4.png) in terms of the basis ![\{\ket{+},\ket{-} \}](./images/5e1996145b5be00fb9a3058418c66a821d664108.png) as follows:

![\tfrac{1}{\sqrt{2}}\ket{0}^{A}\ket{1}^{B} - \tfrac{1}{\sqrt{2}}\ket{1}^{A}\ket{0}^{B}
=
\ket{\Psi_-}^{AB}
= 
\tfrac{1}{\sqrt{2}}\ket{+}^{A}\ket{-}^{B} - \tfrac{1}{\sqrt{2}}\ket{-}^{A}\ket{+}^{B}.](./images/047660f35dc8aac0e219cff3633742e60cfbde24.png)

Observe that the state ![\ket{\Psi_-}^{AB}](./images/91ab6f8fc88f9efcf0f07744de271505017e17b4.png) has the same structure in the Hadamard basis as in the standard basis. Thus, Alice and Bob’s measurement outcomes will also be perfectly anti-correlated when measuring in the Hadamard basis.

A state ![\ket{\psi}^{AB}](./images/a099cde01394606173a6337e196b2b01c8a11b7a.png) is called _entangled_ if it cannot be written as a tensor product of quantum states ![\ket{\phi}^{A} \otimes \ket{\varphi}^{B}](./images/b4e83b416b817525ab53bcb448215d18bad637ce.png), where ![\ket{\phi}^{A}](./images/bd387f929a7d9ff0e21f0fdeb1a45e835c31cd31.png) describes the state held by Alice and ![\ket{\varphi}^{B}](./images/05468928a63a0c861333b59698782ed9d5e2992b.png) the state held by Bob. The EPR state ![\ket{\Psi_-}^{AB}](./images/91ab6f8fc88f9efcf0f07744de271505017e17b4.png) is _entangled_, which means it cannot be written as a tensor product of the quantum states of individual qubits:

![\ket{0} \otimes \ket{1} - \ket{1} \otimes \ket{0} 
\; 
\neq
\; 
(a\ket{0}+ b\ket{1}) \otimes (c\ket{0}+ d\ket{1}),](./images/1bc9cce2e5ee44ad5c185ad2cc933caf22017355.png)

for any ![a,b,c,d \in \mathbb{C}](./images/d63b76a1db7aad7a6f186af31a4cbafbb9b34eb8.png). Since we cannot describe the EPR state ![\ket{\Psi_-}^{AB}](./images/91ab6f8fc88f9efcf0f07744de271505017e17b4.png) as the tensor product of two local states ![\ket{\phi}^{A}](./images/bd387f929a7d9ff0e21f0fdeb1a45e835c31cd31.png) and ![\ket{\varphi}^{B}](./images/05468928a63a0c861333b59698782ed9d5e2992b.png), we say it requires a _nonlocal_ description, which is another way of saying ![\ket{\Psi_-}^{AB}](./images/91ab6f8fc88f9efcf0f07744de271505017e17b4.png) is entangled.

There is something strange about the EPR state. If Alice measures her half of the state and finds ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png), then we know immediately that Bob’s state will be ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png). The collapse in the superposition on Alice’s side immediately causes a collapse of the superposition on Bob’s side. Note that Bob’s collapse will occur _immediately_, no matter how distant Bob’s system is from Alice’s. This is what the authors Einstein, Podolsky, and Rosen called “spooky action at a distance.” How could Bob’s system “know” to always produce the opposite outcome even at the other end of the universe?

Now imagine you have a whole bunch of physical systems prepared in the EPR state. Alice controls one half of each of the EPR pairs, while Bob controls the other half. This is a communication resource called _shared entanglement_. Many of the quantum information protocols make use of shared entanglement between Alice and Bob, to achieve novel communication tasks.

A useful perspective for thinking about quantum entanglement is to consider the information encoded in the quantum state. This is called the _information theory_ perspective on quantum mechanics. From the point of view of information, we can say a system is entangled whenever we know more about the system as a whole than about its parts. We have complete certainty about the state of the composite system ![\ket{\Psi_-}^{AB}](./images/91ab6f8fc88f9efcf0f07744de271505017e17b4.png), and complete uncertainty about the states of the individual subsystems controlled by Alice and Bob. When Alice measures her half of the entangled state, the two outcomes of the measurement are equally likely. Her measurement outcome essentially corresponds to a completely random bit, which encodes zero information. I would like to tell you more about quantum information theory, but let’s not go further off course.

Instead of discussing theory, let’s describe a practical scenario in which it is possible to know more about a whole system than about its constituent parts.

#####[Physics example](./Front matter.md)

We’ll now describe a physical process that leads to the creation of an entangled quantum state. Consider a quantum particle ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) that _decays_ into two quantum subparticles, ![p_a](./images/204f5379603a3ef2f81d0d9bdc8b0e260cf8ac36.png) and ![p_b](./images/9a0d0d1ed57a2f6d8964ed2fe6d33c2ea345421d.png). The decay process obeys various physics conservation laws; in particular, the total spin angular momentum before and after the decay must be conserved. Supposing the particle ![p](./images/336c1ec6d8dcd29d4f71e50907c6d25921225842.png) has zero spin angular momentum before the decay, then the law of conservation of angular momentum dictates the subparticles ![p_a](./images/204f5379603a3ef2f81d0d9bdc8b0e260cf8ac36.png) and ![p_b](./images/9a0d0d1ed57a2f6d8964ed2fe6d33c2ea345421d.png) must have opposite spin. The spin angular momentum of each particle is in an unknown direction (up, down, left, right, in, or out), but whichever spin direction we measure for ![p_a](./images/204f5379603a3ef2f81d0d9bdc8b0e260cf8ac36.png), the spin angular momentum of ![p_b](./images/9a0d0d1ed57a2f6d8964ed2fe6d33c2ea345421d.png) immediately takes on the opposite direction. This way, regardless of the direction of their individual spins, their combined spin angular momentum will be zero, as required by the law of conservation of angular momentum.

The general scenario discussed above describes what would happen if a Helium atom were to explode, the two electrons in its ground state flying off to distant sides of the universe. The two electrons have opposite spins, but we don’t know the directions of the individual spins. The only thing we know is that their total spin equals zero, since the ground state of the Helium atom has spin zero. This is how the “anti-correlation in _any_ basis” aspect of quantum entanglement arises.

###[Summary](./Front matter.md)

We can summarize the concepts of quantum mechanics we learned in this chapter, and relate them to the concepts of linear algebra:

![\begin{align*}
\textrm{quantum state} 		& \; \Leftrightarrow \;   \textrm{vector }   \ket{v} \in \mathbb{C}^d 	\\
\textrm{evolution} 			& \; \Leftrightarrow \;   \textrm{unitary operations}  \\
\textrm{measurement} 		& \; \Leftrightarrow \;   \textrm{projections}		\\
\textrm{composite system} 	& \; \Leftrightarrow \;   \textrm{tensor product}
\end{align*}](./images/d382fc15d2f0d56b5c47924ee88bdde466fac379.png)

The quantum formalism embodied in the four postulates of quantum mechanics has been applied in describing many physical phenomena. Using complex vectors to represent quantum states leads to useful models and predictions for experimental outcomes. In the next section, we’ll use the quantum formalism to analyze the outcomes of the polarizing lenses experiment.

In addition to the applications of quantum principles, studying the structure of quantum states and operations is an interesting field on its own. An example of a quantum idea that is fundamentally new is the existence of _entangled_ quantum states. Later in this chapter, we’ll discuss an interesting application of quantum entanglement as part of the _quantum teleportation_ protocol, illustrated in[Figure 9.23](./Chapter 9_ Quantum mechanics.md) (page 9.23).

###[Exercises](./Front matter.md)

E9.10 Find the matrix representation of the projection matrices ![\Pi_+ = \ket{+} \bra{+}](./images/33ac5a650047745369feb1a51575b570210031df.png) and ![\Pi_- =  \ket{-} \bra{-}](./images/0cdef424a7f1eb6272695c6701a348e5437a9719.png). Show that ![\Pi_+ + \Pi_- = \mathbbm{1}](./images/ad3da1f3576324ecdb92cb24925e874a819b7425.png).

E9.11 Compute the probability of outcome “![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png)” for the measurement ![\{ \Pi_+, \Pi_- \} = \{ \ket{+} \bra{+},  \ket{-} \bra{-} \}](./images/5d461d9ac3d9e2e8f99e65d716bc150d9ae74761.png) performed on the quantum state ![\ket{\psi} =  \alpha \ket{0} + \beta \ket{1}](./images/5793fb1477cd6223587ef6ff0ef9f6d39fb7403f.png).

E9.12 Given the state ![\ket{\theta} = (\frac{1}{\sqrt{2}},  \frac{e^{i \theta}}{\sqrt{2}} )^\sfT](./images/3f112213a8a87c62b13298f528f25dd3cfc2c2a6.png), find a quantum state ![\ket{\theta^\perp}](./images/519933c3e3119610e02fdd8097a43a503dd9a447.png) that is orthogonal to ![\ket{\theta}](./images/cf78a6cf98a2c86fa00942b1be68f7347cfaa639.png). Find the projection operators ![\Pi_\theta](./images/fe517b3a97fdc68308ec8d45359b5c00b5c9b0fa.png) and ![\Pi_{\theta^\perp}](./images/b2b187d9e341ce3c455dfb851ba1ddaa9eae59e6.png) that correspond to the measurements in the basis ![\{ \ket{\theta}, \ket{\theta^\perp} \}](./images/c810a289c1bbb897650a1e103b8446fdc2d291d2.png). Verify that ![\Pi_\theta + \Pi_{\theta^\perp} = \mathbbm{1}](./images/6776d768fce1a8694f285b2d74367ca7055257fe.png). Compute the probability of outcome ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png) when performing the measurement ![\{ \Pi_\theta, \Pi_{\theta^\perp}\}](./images/25cd54ae6d6b551f71f8f6c876f93841524e63ff.png) on the state ![\ket{\psi} =  \alpha \ket{0} + \beta \ket{1}](./images/5793fb1477cd6223587ef6ff0ef9f6d39fb7403f.png).

The state ![\ket{\theta^\perp}](./images/519933c3e3119610e02fdd8097a43a503dd9a447.png) satisfies ![\braket{\theta^\perp | \theta}=0](./images/5513f704f78f853cc4c7b859e07dc926d02aa999.png).

E9.13 Given the two qubits ![\ket{\psi} = \alpha\ket{0} +\beta\ket{1}](./images/5793fb1477cd6223587ef6ff0ef9f6d39fb7403f.png) and ![\ket{\phi} = \gamma\ket{0} +\delta\ket{1}](./images/ffbb85a96c96251b5199f0ee4ee2cd1cc909f624.png), compute the tensor product state ![\ket{\psi} \otimes \ket{\phi}](./images/9c85f2a09570104b3a2a8757c3d217a4623c5400.png).

###[Links](./Front matter.md)

\[ Compact set of notes on QM written by a physicist \]

[`http://graybits.biz/notes/quantum_mechanics/preface`](./preface.md)

\[ Lecture series on QM written by a computer scientist \]

[`http://scottaaronson.com/democritus/lec9.html`](./lec9.md)

\[ Quantum mechanics summary written by a philosopher \]

[`http://plato.stanford.edu/entries/qm/`](./qm.md)

##[9.4 Polarizing lenses experiment revisited](./Chapter 9_ Quantum mechanics.md)

Let’s revisit the polarizing lenses experiment, this time modelling photons’ polarization states as two-dimensional complex vectors. We define the state of a horizontally polarized photon as ![\ket{H} \eqdef \ket{0} = (1,0)^\sfT](./images/42570f48650f37b1da4e3f30d1d33cf37c2a3a66.png), and the state of a vertically polarized photon as ![\ket{V} \eqdef \ket{1} = (0,1)^\sfT](./images/7b7d947edacfa9c4792ac792aa4301daea97babb.png). This choice corresponds to the observation that horizontal and vertical polarizations are complementary. We shall interpret the polarizing lenses in the optical circuit both as state preparation and measurement steps. The measurement outcome we observe is whether photons pass through the complete optical circuit.

[Figure 9.14](./Chapter 9_ Quantum mechanics.md) illustrates the state preparation step we can use in experiments with photons. We can prepare photons in the states ![\ket{H}](./images/0cbef79e16a72127bd567b54dd2a83ded941ecee.png) or ![\ket{V}](./images/9097d28a02a1d14f8bcedc25919c58a58a63d879.png) by starting from unpolarized photons, and passing them through either an ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png)\-polarizing lens or a ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lens.

![polarization-example-with-quantum-state](./images/polarization-example-with-quantum-state.png)

Figure 9.14: State preparation procedure for photons with horizontal or vertical polarization. Depending on our choice of ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png)\- or ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png)\-polarizing lens, we can prepare different quantum states.

Placing a polarizing lens in the path of a photon performs the measurement ![\{\Pi_\leftarrow, \Pi_\rightarrow\}](./images/add015bbf93f399e44002d6326da45753c7e4294.png) of the photon’s polarization state. Using the lens to measure a photon’s polarization state yields two possible outcomes: “photon passes through lens” or “photon is reflected by lens.” The polarizing lens is the measurement apparatus, and the measurement corresponds to whether each photon that hits the lens is horizontally or vertically polarized.

[Figure 9.15](./Chapter 9_ Quantum mechanics.md) shows the projection operators that correspond to a measurement using a horizontally polarizing lens. The outcome “passes through” corresponds to the projection operator ![\Pi_\rightarrow = \ket{H}\!\bra{H} =
\begin{bmatrix}
1	&	0	\\
0	&	0	\\
\end{bmatrix}](./images/6ee4fef3b4de727d8682b96247b5d3ffa353e480.png). The outcome “is reflected” corresponds to the projection matrix ![\Pi_\leftarrow = \ket{V}\!\bra{V} =
\begin{bmatrix}
0	&	0	\\
0	&	1	\\
\end{bmatrix}](./images/85efe361a9296ca0e5cd3a0431387b2f7f72d99e.png).

![define-H-measurement](./images/define-H-measurement.png)

Figure 9.15: A horizontally polarizing lens corresponds to the quantum measurement ![\{\Pi_\leftarrow , \Pi_\rightarrow\}](./images/67ee2f59f2dfb1beae53e61601a7460085446e83.png). An incoming photon in the state ![\ket{\gamma}](./images/c164185d0f0c061c3244572da95b2661c430a4dd.png) is asked to choose one of the two alternative paths. With probability ![\| \Pi_\rightarrow\ket{\gamma}\|^2](./images/df69cc1e3b648e67f7089ccbc6fbf03835296678.png), the photon passes through the ![H](./images/a279e0fcb01c790332b789868a755f2255460155.png)\-polarizing lens and becomes horizontally polarized ![\ket{\gamma^\prime} = (1,0)^\sfT](./images/b94e50664e4639b7bd485e6f26b971278a3af8e6.png). With probability ![\| \Pi_\leftarrow\ket{\gamma}\|^2](./images/7fb8d16e8ee662764bf566aab27c17b3c9c78f50.png), the photon is reflected.

Recall that the probability of outcome ![i](./images/5f9dc13e64b07921d5938d4947f75b96b06a6ae6.png) in a quantum measurement ![\{\Pi_i\}](./images/7a54549e80fc0c3b4f9cebad376bdf462d60260b.png) is given by the expression ![\|\Pi_i \ket{\gamma}\|^2](./images/04ecf222be6b3502caf6d24071ea8f4d24cb2f38.png), where ![\ket{\gamma}](./images/6a5e0c591eb889f19cb67f3e3169b8989c5b2eaf.png) is the state of the incoming photon. Knowing the projection operators that correspond to the “passes through” and “is reflected” outcomes allows us to predict the probability that photons with a given state will pass through the lens.[Figure 9.16](./Chapter 9_ Quantum mechanics.md) illustrates a two-step experiment in which photons prepared in the horizontally polarized state ![\ket{H} = (1,0)^\sfT](./images/0726ff091aaa7e3a79aaab5e5f8e354bfd10e973.png) arrive at a ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lens. The probability that photons pass through the ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lens is

![\begin{align*}
\textrm{Pr}\!\left(\{ \textrm{pass through } V \textrm{ lens given state } \ket{H} \} \right)
&=
\left\| 
\ket{V}\!\bra{V}
\ket{H}
\right\|^2 	\\
&=
\left\| 
\begin{bmatrix}
0	&	0	\\
0	&	1
\end{bmatrix}		
\begin{bmatrix}
1 \\ 0
\end{bmatrix}
\right\|^2 \\
&=
\left\|
\begin{bmatrix}
0 \\ 0
\end{bmatrix}
\right\|^2 = 0.
\end{align*}](./images/e416bc02e26cfea234a319e73b8496034df0d475.png)

Indeed, we observe the same result in the lab—all ![\ket{H}](./images/0cbef79e16a72127bd567b54dd2a83ded941ecee.png) photons are rejected by the ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lens.

![two-lenses-experiment-bis](./images/two-lenses-experiment-bis.png)

Figure 9.16: Photons prepared in the state ![\ket{H}=(1,0)^\sfT](./images/e1dc72940ef8bc7f8dfce69b62dc28100057e678.png) are rejected by the ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png)\-polarizing lens because the horizontally polarized state has zero overlap with the projector ![\Pi_\rightarrow = \ket{V}\!\bra{V}](./images/983dd5cc7f440071642ae3b23d18965bbd05a29b.png).

Let’s now use the quantum formalism to analyze the results of the three-lenses experiment we discussed earlier in the chapter.[Figure 9.17](./Chapter 9_ Quantum mechanics.md) shows the optical circuit that consists of a state preparation step and two measurement steps. The diagonally polarizing lens placed in the middle of the circuit only allows photons with ![45^\circ](./images/bd3d3974358aa0059bc92afb15aa60914b97d2d5.png)\-diagonal polarization to pass through: ![\ket{D} = \big(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\big)^{\!\sfT}](./images/99c61795dea0c78bcc6856824e46c985fee1d5b4.png). The projection operator associated with the “passes through” outcome of the diagonal polarization measurement is

![\Pi_\rightarrow
= 
\ket{D}\!\bra{D}
=
\begin{bmatrix}\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} \end{bmatrix}
\begin{bmatrix}\frac{1}{\sqrt{2}}  & \frac{1}{\sqrt{2}} \end{bmatrix}
=
\begin{bmatrix}
\frac{1}{2}	&	\frac{1}{2}	\\
\frac{1}{2}	&	\frac{1}{2}
\end{bmatrix}.](./images/8b13c713088d915662a2db946f744e62b71f9f35.png)

The probability of ![\ket{H}](./images/0cbef79e16a72127bd567b54dd2a83ded941ecee.png) photons passing through the diagonal lens is

![\begin{align*}
\textrm{Pr}\!\left(\{ \textrm{pass through } D \textrm{ lens given state } \ket{H} \} \right)
&=
\left\| 
\ket{D}\!\bra{D}
\ket{H}
\right\|^2 									\\
&=
\left\|
\begin{bmatrix}
\frac{1}{2}	&	\frac{1}{2}	\\
\frac{1}{2}	&	\frac{1}{2}
\end{bmatrix}
\begin{bmatrix} 
1 \\
0
\end{bmatrix}
\right\|^2 									\\
&=
\left\|
\begin{bmatrix}
\frac{1}{2} \\ \frac{1}{2}
\end{bmatrix}
\right\|^2 									\\
&= \left(\tfrac{1}{2}\right)^2 + \left(\tfrac{1}{2}\right)^2	= \frac{1}{2}.
\end{align*}](./images/c4cd62bea73d51f7ce93f257fa33def2518804b0.png)

The post-measurement state of photons that make it through the diagonally polarizing lens is ![\ket{D} = \big(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}}\big)^{\!\sfT}](./images/99c61795dea0c78bcc6856824e46c985fee1d5b4.png).

![three-lenses-experiment-bis](./images/three-lenses-experiment-bis.png)

Figure 9.17: Photons prepared in the state ![\ket{H}](./images/f3c8b5d8d081b68a038bf381c7fecf689ba8fd36.png) are subjected to two sequential measurements: a diagonal polarizing measurement ![D](./images/5eadde85cc4d11e6f52f4e09b6059250e60a2ea9.png) followed by a vertical polarizing measurement ![V](./images/829d384e7a4c55c2e8a18945262e493586f1d2c0.png). The projection operators for the “is reflected” and “passes though” outcomes are indicated in each step.

Photons that pass through the middle lens are in the state ![\ket{D}](./images/06ddacb1a338b2c1d04e834448cc1c9d104d3326.png). The probability of these photons passing through the ![V](./images/151c3ba3af0584dde5a361b2266af8757396e5f8.png)\-polarizing lens is

![\begin{align*}
\textrm{Pr}\!\left(\{ \textrm{pass through } V \textrm{ lens given state } \ket{D} \} \right)
&=
\left\| 
\ket{V}\!\bra{V}
\ket{D}
\right\|^2 									\\
&=
\left\| 
\begin{bmatrix}
0	&	0	\\
0	&	1
\end{bmatrix}		
\begin{bmatrix}
\tfrac{1}{\sqrt{2}} \\
\tfrac{1}{\sqrt{2}}
\end{bmatrix}
\right\|^2 									\\
&=
\left\|
\begin{bmatrix}
0 \\ \tfrac{1}{\sqrt{2}}
\end{bmatrix}
\right\|^2 									\\
&= 0^2 + \left(\tfrac{1}{\sqrt{2}}\right)^2 			=  \frac{1}{2}.
\end{align*}](./images/9a49ec937d37900bf7f00f57daac5221e4cda963.png)

The overall probability of a photon passing through both measurement lenses is ![\frac{1}{4}](./images/474eb89340545d05a238efb3cf39c9bb239e1816.png).

This probability is consistent with the light intensity observations we see in[Figure 9.8](./Chapter 9_ Quantum mechanics.md) (page 9.8). Note the new interpretation that quantum mechanics provides for the same observations. We previously referred to the optical power ![P=0.5](./images/283233a7d178b2b216c868190fd5a8c0183b6aed.png) after the first measurement and optical power ![P=0.25](./images/8f123c0f34f027bcfd2fd4f0aaa203e310b51663.png) after the second measurement. The quantum formalism predicts the probability ![p=0.5](./images/8ddab888a082e9f6f8a2a360f1517c69b7dcfbea.png) for photons to pass through the first lens and the probability ![p=0.25](./images/b9b71790255ef310c20b5bf1b8169090085a12c7.png) for the photons to reach the end of the circuit.

####[Discussion](./Front matter.md)

The polarizing lenses experiment illustrates some key aspects of the quantum formalism: the modelling of quantum states as vectors, the process of state preparation, and the effects of measurements on systems. Mainly, the experiment shows how a probabilistic approach for describing the light intensity in the circuit successfully predicts the experiment’s outcome.

Let’s compare the quantum interpretation of this experiment with a classical interpretation. It’s possible to explain all the observations of the polarizing lenses experiment using the classical theory of electromagnetic waves. Modelling the light beam as a classical wave allows us to understand the projections to the “passes through” orientation of the polarizing lenses. Because the light beam consists of many photons, it behaves like a continuous quantity that can be split: part of the wave passes through the lens while another part is reflected. Classical wave theory correctly predicts the qualitative aspects of the experiment shown in[Figure 9.17](./Chapter 9_ Quantum mechanics.md), but the light intensity is described in terms of optical power ![P=\frac{1}{4}](./images/e899b4da06181677cd63bcb408290c74976652d6.png), which is the average squared amplitude of an electromagnetic wave. In contrast, quantum theory models photons as discrete packets of energy, and explains the outcome of the polarizing lenses experiment as the probability ![p=\frac{1}{4}](./images/f14ede9d645257e31dae864e07c2855adedd0b23.png) that a photon will pass through the circuit. For this tabletop experiment, both the classical model of light (as a wave that can be infinitely subdivided) and the quantum model of light (as discrete particles) predict the same outcome. Therefore, the polarizing lenses experiment performed with a laser pointer does not serve as proof for the necessity of a quantum mechanical description of reality.

As we discussed in the introduction to this chapter, to really reveal quantum effects, we need to look at the very small-scale or very low-power regimes. It’s possible to reproduce the polarizing lenses experiment using a _single photon source_. A single photon source behaves like a super-weak laser pointer that emits only one photon at a time. When discussing the single photon regime, the classical theory of electromagnetic waves hits a wall, since a single photon cannot subdivide into parts—it is a quantum of light; a small, indivisible bundle of energy. Classical wave theory can correctly predict average optical power, but it can’t provide a clear picture of what exactly happens when individual photons hit a polarizing lens.

The polarizing lenses experiment is inspired by the famous _Stern–Gerlach experiment_, which is performed with the magnetic spin of silver atoms, and which involves a similar demonstration, comparable observed outcomes, and analogous reasoning. I encourage you to learn more about the original Stern–Gerlach experiment.

\[ The Stern–Gerlach experiment \]

[`https://en.wikipedia.org/wiki/Stern-Gerlach_experiment`](./Stern-Gerlach_experiment.md)

[`https://youtube.com/watch?v=rg4Fnag4V-E`](./watch_v=rg4Fnag4V-E.md)

##[9.5 Quantum mechanics is not that weird](./Chapter 9_ Quantum mechanics.md)

Without a doubt, you’ve heard that quantum mechanics is weird, mysterious, and generally “magical.” Well, unless vector operations count as magic, it’s not _that_ magical. In this section, we’ll single out three so-called “weird” aspects of quantum mechanics: superposition, interference, and the fact that quantum measurements affect the states of systems being measured.

###[Quantum superposition](./Front matter.md)

Classical binary variables (bits) can have one of two possible values: ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) or ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png). Examples of physical systems that behave like bits are electric switches that can be either open or closed, digital transistors that either conduct or don’t conduct electricity, and capacitors that are either charged or discharged.

A quantum bit (qubit), can be both ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) and ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) _at the same time_. Wow! Said this way, it surely sounds impressive and mystical, no? But if we use the term _linear combination_ instead of “at the same time,” the quantum reality doesn’t seem so foreign. A quantum state is a linear combination of the basis states. This isn’t so crazy. The _superposition principle_ is a general notion in physics that is not specific to quantum phenomena, but applies to all systems described by differential equations. Indeed, superpositions exist in many classical physics problems, too.

#####[Example](./Front matter.md)

Consider a mass attached to a spring that undergoes simple harmonic motion. The differential equation that governs the motion of the mass is ![x''(t) + \omega^2 x(t) = 0](./images/e19a78756ace132df54319f2bfe17527c68d9486.png). This equation has two solutions: ![x_0(t)=\sin(\omega t)](./images/9c793e55bfad8bf6270697b3b354f8cbec20e1a6.png) and ![x_1(t) =\cos(\omega t)](./images/6ad7171fd958c117e63ea53020130653171112eb.png), corresponding to two different starting points of the oscillation. Since both ![x_0(t)](./images/bb60b898ab2e6b873ed6bf6d207d167949ce57a1.png) and ![x_1(t)](./images/1834c1d13dfb2c16984a6d72f655c8ded0691ed2.png) satisfy the equation ![x''(t) + \omega^2 x(t) = 0](./images/e19a78756ace132df54319f2bfe17527c68d9486.png), any linear combination of ![x_0(t)](./images/bb60b898ab2e6b873ed6bf6d207d167949ce57a1.png) and ![x_1(t)](./images/1834c1d13dfb2c16984a6d72f655c8ded0691ed2.png) is also a solution. Thus, the most general solution to the differential equation is of the form:

![x(t) 	= \alpha x_0(t) + \beta x_1(t)
= \alpha \sin(\omega t) + \beta \cos(\omega t).](./images/b900ef1624fa33e32b3f02d97f237a54ac125d45.png)

Usually we combine the ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png) and ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png) terms and describe the equation of motion for the mass-spring system in the equivalent form ![x(t) = A \cos(\omega t + \phi)](./images/59b17785dee31d1991c551cdaa1d46aab7868a6d.png), where ![A](./images/a7ebd3de1e7c66767d8b53415ef903d9b496a427.png) and ![\phi](./images/be6641cf3fbb04421551096640a00124667cb922.png) are computed from ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png). The mass-spring system might be described as undergoing both ![\sin](./images/f90387bef63751351a717a26b3f7dafad28fa601.png) motion and ![\cos](./images/f52108a391c4845ef8912955d2ca9d3ed7d771bc.png) motion “at the same time,” but do you see how ridiculous and incomplete this sounds?

The notion of _quantum superposition_ is simply a consequence of the general superposition principle for differential equations. If the quantum states ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) and ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png) both represent valid solutions to a quantum differential equation, then the state of the system can be described as a linear combination of these two solutions:

![\ket{\psi} =  \alpha\ket{0} + \beta\ket{1}.](./images/266868be458206647642caa8b68d61674d5a0f05.png)

The observation that “![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) is both ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) and ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png) at the same time” is not wrong; it’s just not very useful. It’s much more precise to describe the quantum state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) as a linear combination.

###[Interference](./Front matter.md)

Unlike particles that bounce off each other, waves can co-exist in the same place. The resulting wave pattern is the sum of the constituent waves. Quantum particles behave similarly to waves in certain experiments, and this can lead to _interference_ between quantum systems.

The prototypical example of interference is Young’s double-slit experiment, in which particles passing through two thin slits interact with each other, causing an interference pattern of alternating bright and dark spots on a screen. Classical physics models assume particles behave like tiny point-like balls that bounce off each other whenever they come in contact. A classical model predicts that particles will appear on the screen in two bright peaks, directly facing the two slits.

In contrast, the quantum model of a particle describes it as a travelling energy pulse that exhibits wave-like properties[2](./Front matter.md) In a quantum model, the particles passing through the slits behave like waves and can combine constructively or destructively, depending on the relative distances travelled by the particles. Similar interference patterns occur whenever waves combine, as in the example of waves on the surface of a liquid, or sound waves.

![interference_pattern](./images/interference_pattern.jpg)

Figure 9.18: The waves emitted by two synchronized sources form an interference pattern. Observe the stripes of destructive interference where the waves meet “out of sync” (peak to trough) and cancel each other out.

Performing Young’s double-slit experiment reveals a pattern of bright and dark stripes (called fringes) on the screen in support of the quantum model. The locations of the dark fringes correspond exactly to the places where particles passing through the two slits arrive “out of sync,” and combine destructively:

![\ket{\psi} - \ket{\psi} =  0.](./images/f3657bec51c21d93f24b89e3193c6e8424d465e4.png)

The locations where destructive interference occurs correspond to the dark fringes on the screen, where no particles arrive.

The idea that one wave can cancel another wave is not new. What _is_ new is the observation that particles behave like waves that can interfere with each other. That’s definitely new. Indeed, interference was one of the first puzzling effects of quantum systems that was observed. Observations from interference experiments forced physicists to attribute wave-like properties to particles.

\[ Video demonstration of Young’s double-slit experiment \]

[`https://youtube.com/watch?v=qCmtegdqOOA`](./watch_v=qCmtegdqOOA.md)

###[Measurement of a system affects the system’s state](./Front matter.md)

Another seemingly weird aspect of quantum mechanics is the notion that quantum measurements can affect the states of the systems being measured. This phenomenon is not attributable to some sort of quantum magic, but is rather due to the energy scale and the size of systems where quantum physics comes into play. Let’s see why.

When we think about physical systems on the scale of individual atoms, we can no longer consider ourselves (and our physical measurement apparatuses) as passive observers of these systems. Instead, we need to account for the _interactions_ between quantum systems and the measurement apparatuses used to observe them. The fact that measurements affect the state of the very systems they measure is not some magical process, but rather a consequence of the natural properties of the particles themselves. The particles we observe are affected by our measurement methods.

###[Wave functions](./Front matter.md)

The quantum mechanics techniques we discussed in this chapter are useful for modelling physical systems that have discrete sets of states. In _matrix quantum mechanics_, quantum states are described by vectors in finite-dimensional, complex inner product spaces. Other physics problems require the use of _wave function quantum mechanics_, in which quantum states are represented as complex-valued functions of space coordinates ![\vec{r}=(x,y,z)](./images/682376f372abb93e3fd66308aedd1506820c6df8.png). Instead of the dot product between vectors, the inner product for wave functions is ![\langle f(\vec{r}), g(\vec{r}) \rangle = \int\!\int\!\int_{\mathbb{R}^3} \overline{ f(\vec{r}) } g(\vec{r}) \, d^3\vec{r}](./images/8c765050167f4cfdc6bf9d63eaef93986250aa0d.png). This may seem like a totally new ball game, but actually calculations using wave functions are not too different from the inner product calculations we used to compute Fourier transformations in[Section 7.11](./Chapter 7_ Applications.md).

It’s beyond the scope of the current presentation to discuss _wave functions_ in detail, but I want to show you an example of a calculation with wave functions, so you won’t say I didn’t show you some proper physics stuff. The ground state of the hydrogen atom is described by the wave function ![\psi(\vec{r}) =\frac{1}{\sqrt{\pi a^3}}\exp(-r/a)](./images/00419257c859fb1674e7607ce6f49dd451810238.png), where ![r=\|\vec{r}\|](./images/1d22808c2ad9d6ac438fba6a3b3c01b92a46fcd9.png). The probability of finding the electron at position ![\vec{r}](./images/f922589ce2457f489bd34c34e47c1be9566640cd.png) from the proton is described by the inner product ![\overline{\psi(\vec{r})}\psi(\vec{r}) = |\psi(\vec{r})|^2](./images/19995c09e906d364af08ca378f4db2848ed6dab7.png):

![\Pr\!\left(\{ \text{finding electron at} \; \vec{r} \; \} \right) =  |\psi(\vec{r})|^2.](./images/03e4530db256b87c46cd11064852ab641a667287.png)

Since ![\psi(\vec{r})](./images/81d38c020cfcc2cba68327b5839a0deddc169550.png) depends only on the distance ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png), we know the wave function has a spherically symmetric shape, as illustrated in[Figure 9.19](./Chapter 9_ Quantum mechanics.md).

![electron_s_orbital](./images/electron_s_orbital.png)

Figure 9.19: The ![s](./images/b2ed2336a0f1bedf9435fa07a7b1b918cc6f4a91.png) orbital of an electron is spherically symmetric.

We’ll now check whether ![|\psi(\vec{r})|^2](./images/1a819b57d18753340c4d6e6363e0e569c0305003.png) is a properly normalized probability density function. Integrating the probability density function ![|\psi(\vec{r})|^2](./images/1a819b57d18753340c4d6e6363e0e569c0305003.png) over all of ![\mathbb{R}^3](./images/ba8e36c1bc5d4e52785e4de888b32c4583b24d61.png) should give a total probability of one. Instead of Cartesian coordinates ![(x,y,z)](./images/ab8147f25510506ccc5d4d1090c36e74e6becf81.png), we’ll use spherical coordinates ![(r, \phi, \theta)](./images/58e44750c2a5c15e1b47de872836e3f5b69f8dc9.png) to solve this problem. In spherical coordinates, the volume of a thin slice from the surface of a sphere of width ![d\theta](./images/c183f5df875526ccd36361f64d8a99373667188e.png), height ![d\phi](./images/1d1a1590831bea812257185215e9980300bc5fd8.png), and thickness ![dr](./images/b885a068702b8a28a08acac08a9753b49bf0e165.png) is given by ![r^2 \sin \phi \; d\phi \, d\theta \, dr](./images/84d4f1f9a71b9f912f92be2c59ee0fdfec45ab49.png). If you haven’t seen spherical coordinates before, don’t worry about this expression too much. The conversion factor ![r^2 \sin \phi](./images/79bac6fbabb57143f371f2b2ebbfd669bff77a50.png) is a trick for converting the “small piece of volume” ![d^3\vec{r}=dx\;dy\;dz](./images/1be93b4c1a940675924e0acacb352ca4e568b958.png) to an equivalent small piece of volume in spherical coordinates ![d^3\vec{r}=r^2 \sin \phi \; d\phi \, d\theta \, dr](./images/c4fedaca9a600ae881bad63175fa3d4af65a551b.png). See [3.6](./Chapter 3_ Computational linear algebra.md) for the derivation.

We split the triple integral into two parts: an integral that depends only on the radius ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png), and double integral over the angles ![\phi](./images/be6641cf3fbb04421551096640a00124667cb922.png) and ![\theta](./images/532c6c6219bd603742487e15d9eb7057a6c1a036.png). The total probability of finding the electron somewhere in space is

![\begin{align*}
p_{\textrm{total}} 
&= \int\!\!\!\int\!\!\!\int_{\mathbb{R}^3} |\psi(\vec{r})|^2  \; d^3\vec{r}  \\
&= 
\int_0^\infty \!\!\! \int_0^{2\pi} \!\!\! \int_0^\pi  
|\psi(r)|^2  \; r^2 \sin \phi \; d\phi \, d\theta \, dr   					\\
&= 
\left(\int_0^\infty \!\! \frac{1}{\pi a^3}\exp(-2r/a)  \; r^2 \,   dr   \right)
\left(\int_0^{2\pi}\!\!\!\int_0^\pi \!\! \sin \phi \, d\phi \, d\theta  \right)		\\				    &= 
\left(\int_0^\infty  \frac{1}{\pi a^3}\exp(-2r/a)  \; r^2 \,   dr \right)
\left( 4\pi \right)												\\
&= 
\int_0^\infty \!\! \underbrace{\frac{4}{a^3} \exp\left(-\frac{2 r}{a}\right) r^2}_{p(r)} \, dr.
\end{align*}](./images/9bd75e430da8691cd411725dd5e108cdf694e1f0.png)

The expression ![p(r)=\frac{4}{a^3}\exp(-2r/a) r^2](./images/963231c5617e4515ee03b0b8e19d0ce44338df45.png) describes the probability of finding the electron at a distance ![r](./images/fbb99f2a65a23be18fae775eb9f9dd3d870db27f.png) from the centre of the nucleus. We can complete the calculation of total probability by taking the integral of ![p(r)](./images/eae490d8b85d250e2cf5f1943c97003a31bd1218.png) from ![r=0](./images/f1b54e2b3ed99244a4389ff74ff18da87a3f01f1.png) to ![r=\infty](./images/c5446f7ae8cda97b8e1faf893a09552662650274.png):

![\begin{align*}
p_{\textrm{total}} 		
&=	\int_0^\infty \!\! p(r) \, dr										\\
&=    \frac{4}{a^3} \int_0^\infty \!\! \exp\left(\frac{2 r}{a}\right) r^2 \, dr  			 \\
&= 	1.
\end{align*}](./images/17e41728146ee4abf5bdad5ea25a9d13991384d2.png)

The purpose of working through this wave function calculation is to give you an idea of the complex calculations physicists regularly perform using the wave function formalism. In comparison, the matrix formalism for quantum mechanics is much simpler, involving only basic linear algebra calculations.

##[9.6 Quantum mechanics applications](./Chapter 9_ Quantum mechanics.md)

What can we accomplish using quantum physics that we can’t do using classical physics? What can we compute with qubits that we can’t compute with bits? You’ve learned about the quantum formalism; but how useful is it? In this section, we’ll explore some areas of physics and computer science that wouldn’t exist without the laws of quantum mechanics.

###[Particle physics](./Front matter.md)

The basic quantum mechanics formalism we learned in this chapter is not appropriate for describing the behaviour of high energy particles. The best current model for describing high energy physics is called _quantum field theory_. Quantum field theory is a generalization of basic quantum mechanics that models fundamental particles as disturbances in various _particle fields_. Recall that photons, the quanta of light, are described as disturbances of the electromagnetic field. The equations of quantum field theory describe how elementary particles and antiparticles are created and destroyed, and the various interactions between different particle fields. Quantum field theory is a bit like chemistry, where different combinations of atoms are transformed into other combinations of atoms—only instead of atoms, we have elementary particles like quarks and leptons. In the same way _Mendeleev’s periodic table_ is a catalogue of all available atoms, the _Standard Model_ of particle physics is a catalogue of all available elementary particles. These elementary particles combine to form other, more complex particles, like protons and neutrons. The transformations of these particles are only observed in high energy physics experiments performed in particle accelerators.

High energy physics becomes important at the extreme end of an energy continuum, where quantum field theory is most applicable. In contrast, the rules of chemistry dominate the low-energy end of the energy continuum. Chemical reactions describe how molecules transform into other molecules; and molecules essentially represent the various ways electrons are shared between groups of atoms. At higher energies, atoms are “stripped” of their electrons; the atoms have so much energy, they’re no longer bound to the nucleus. At this point, the laws of chemistry are no longer relevant, since electrons and molecules move freely. Enter nuclear physics, which studies the combinations of protons and neutrons that form the nuclei of different atoms. A nuclear reaction is like a chemical reaction, but instead of chemical molecules, the reactant and products are various types of nuclei. An example of nuclear reaction is the fusion of two heavy hydrogen nuclei to form a helium nucleus. At higher energy still, even protons and neutrons can break apart, and the analysis shifts to interactions between elementary particles like leptons, bosons, neutrinos, quarks, and photons. This is the domain of high energy physics.

The basic postulates of quantum mechanics still apply in quantum field theory, but the models become more complicated since we assume even the interactions between particles are quantized. You can think of the basic quantum mechanics described in this chapter as learning the alphabet, and quantum field theory as studying Shakespeare, including the invention of new words. Studying quantum field theory requires new math tools like path integrals, new intuitions like symmetry observations, and new computational tricks like _renormalization_.

The essential way of thinking about photons, electrons, and the interactions between them can be obtained by reading Richard Feynman’s short book titled _QED_, which stands for _quantum electrodynamics_. In this tiny book, Feynman uses the analogy of a “tiny clock” attached to each particle to explain the phase ![e^{i\theta}](./images/2d9f5a485cb54e65a1fc26cf9c9f01b8ba80d7d3.png) of a wave function. From this simple analogy, the author builds to explain complex concepts (path integrals, for instance) at the graduate level of quantum field theory. I highly recommended this book; it’s a wonderful chance to learn from one of the great scientists in the field and one of the best physics teachers of all times.

\[ The Standard Model of particle physics \]

[`https://en.wikipedia.org/wiki/Standard_Model`](./Standard_Model.md)

\[BOOK\] Richard P. Feynman. _QED: The strange theory of light and matter_. Princeton University Press, 2006, ISBN 0691125759.

###[Solid state physics](./Front matter.md)

Physicists have sought to understand the inner structure of materials since the first days of physics. As they’ve learned, they’ve developed numerous applications, from semiconductors to lasers, photovoltaic batteries (solar panels), light emitting diodes (LEDs). These applications all depend on materials with specially engineered conductivity properties. Indeed, working with the conductivity of materials gives us insight into their other properties. We can classify materials into the following general conductivity-type groups: insulators, metals, and semi-conductors. These categories correspond to materials with different _energy band structures_.

Insulators are the most boring type of material, because their energy band structure doesn’t permit any interesting chemical interactions. Take glass, for instance—just a clump of silica (![\textrm{Si}\textrm{O}_2](./images/40b2de81755c329a3eda6ea960f31c565970e68f.png)). The term _glass_ is used in physics to describe any material made of randomly oriented molecules that lack a specific crystal structure.

Conductors are more interesting. A hand-wavy explanation of conductivity would be to say the electrons in conductors like aluminum and copper are “free to move around.” Solid state physics allows for a more precise understanding of the phenomenon. Using quantum mechanical models, we can determine the energy levels that electrons can occupy, and predict how many electrons will be available to conduct electricity.

Semiconductors are the most interesting type of material since they can switch between conductive and non-conductive states. The _transistor_, the invention that makes all electronics possible, consists of a sandwich of three different types of semiconductors. The voltage applied to the middle section of a transistor is called the _gate voltage_, and it controls the amount of current that can flow through the transistor. If the gate voltage is set to `ON` (think ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) in binary), then semiconducting material is biased; free electrons are available in its conduction band, and current can flow through. If the gate voltage is set to `OFF` (think ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) in binary), then the conduction band is depleted and the transistor won’t conduct electricity. The improvements in semiconductor technologies—specifically the ability to pack billions of transistors into a tiny microprocessor chip—have been fuelling the ongoing computer revolution pretty much since transistors were first commercialized. In summary, no solid state physics = no mobile phones.

Quantum mechanics is used so much in solid state physics that we could suitably nickname the field “applied quantum physics.”

\[ Simple explanation of energy band structure and conductivity \]

[`https://wikipedia.org/wiki/Electrical_resistivity_and_conductivity`](./Electrical_resistivity_and_conductivity.md)

###[Superconductors](./Front matter.md)

Certain materials exhibit surprising physical properties at very low temperatures. By low temperatures, I mean _really low_, like ![-272^\circ](./images/041d3bdde52cbb8d181c2335b987d1ef0385b955.png)C; a temperature close to _absolute zero_, the temperature at which all molecules stop. You’d exhibit surprising properties too if your were placed in an environment this cold! Take for example the properties of different metals, which are generally considered to have low electric resistance. There are regular conductors like aluminum that have low resistance, and high-end conductors like silver that have even lower resistance, and then there are _superconductors_ which have zero resistance. Superconductors are an example of a purely quantum phenomenon that cannot be explained by classical physics.

Some of the most iconic landmarks of modern scientific progress, like magnetic resonance imaging (MRI) machines and magnetically levitating bullet trains, are made possible by superconductor technology. Superconductors offer zero resistance to electric current, which means they can support much stronger currents than regular conductors like aluminum and silver. All these applications require extensive refrigeration equipment to keep the materials at a temperature where they behave like superconductors.

\[ Superconductivity \]

[`https://en.wikipedia.org/wiki/Superconductivity`](./Superconductivity.md)

###[Quantum optics](./Front matter.md)

Classical optics deals with beams of light that contain quintillions of photons. A _quintillion_ is ![10^{18}](./images/2d12c30c8b349695ba661dea1d8330b8858cf128.png), which is more than a lot. When working with this many photons, it’s possible to model light beams as continuous electromagnetic waves, and use classical electromagnetic theory and optics to understand experiments. Quantum optics comes into play when we perform optics experiments that involve far fewer photons, including experiments with single photons. When a single photon travels through an optical circuit, it cannot “split” like a continuous wave. For example, when a beam of light hits a half-silvered mirror, we say the beam is partially reflected. However, we can’t say the same for a single photon, since the photon cannot be split. Instead, the state of the photon after it has encountered a half-silvered mirror is best described as a superposition of the “passed through” and “reflected” states, as shown in[Figure 9.11](./Chapter 9_ Quantum mechanics.md) (page 9.11).

An example of a quantum optics effect is the _spontaneous downconversion effect_, in which a single photon is absorbed by a material and then reemitted as two photons with an entangled polarization state:

![\ket{\Psi_-}  = \tfrac{1}{\sqrt{2}}\ket{H}\ket{V} - \tfrac{1}{\sqrt{2}}\ket{V}\ket{H}.](./images/ba5aaf0f2baf9c9d27b219e25b4ee86e2c712b4e.png)

By the crystal’s properties, we know one of the two emitted photons has horizontal polarization and the other has vertical polarization, but we don’t know which is which. Such entangled photons can be used as starting points for other experiments that involve entanglement. Another interesting aspect of quantum optics are the so-called _squeezed states_ that can be detected more accurately than regular (unsqueezed) photons.

Quantum optics is a field of active research. Scientists in academia and industry study exotic photon generation, advanced photon detection schemes, and generally explore how photons can most efficiently carry information.

\[ Basic principles in physics of light \]

[`https://materialford.wordpress.com/introduction-to-research-light/`](./introduction-to-research-light.md)

###[Quantum cryptography](./Front matter.md)

Performing a quantum measurement on the state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) tends to disturb the state. From the perspective of experimental physics, this disturbance is an obstacle since it gives us limited, one-time access to the quantum state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png), making the study of quantum states more difficult. From the perspective of cryptography however, the state-disturbing aspect of quantum measurement is an interesting and potentially valuable property. If Alice transmits a secret message to Bob encoded in the state of a quantum system, it would be impossible for an eavesdropper Eve to “listen in” on the state unnoticed because Eve’s measurement would disturb the state. The _BB84 protocol_, named after its inventors Charles Bennett and Gilles Brassard, is based on this principle.

The standard basis ![B_s = \{\ket{0},\ket{1}\}](./images/db884c87097451c08e5ec4356f27cc5b3c011b12.png) and the Hadamard basis ![B_h = \{\ket{+},\ket{-}\}](./images/c3ab72d711e250dff1d87c6d7bd23e8a3b8a95c1.png) are _mutually unbiased bases_, which means that a basis vector from one basis lies exactly halfway between the vectors from the other basis. If we measure the state ![\ket{+}](./images/65a36f521741d9cd1a45efa30255d0b8241c30d9.png) (or ![\ket{-}](./images/aa1c13b985a0ee85d6a681ee94319e06c10da81d.png)) in the basis ![B_s](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png), the outcomes ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png) and ![1](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png) are equally unlikely. Similarly, measuring ![\ket{0}](./images/b658c2c2dcfb08c16c088c71916395df7a3f70eb.png) (or ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png)) in the basis ![B_h](./images/ed806363e7593bfb85745e769a27899ad2058cd7.png) produces outcomes “![+](./images/1e72f4760b740fbfe3355aad239f77500e5edc20.png)” and “![-](./images/5c250198f8e67179c7d787c2c49d01249b138cbc.png)” with equal probability. The use of mutually unbiased bases is central to the security of the BB84 protocol, which we’ll describe step by step:

1.  Alice starts with ![2n](./images/3bc1b84c8c2b445e2f6ee68eceb6f94508a78e9e.png) random candidate bits which she sends to Bob. Roughly half of the candidate bits will live on to become the final shared secret key, while the other half will be discarded. She chooses one of the bases ![B_s](./images/a5270a45c11e4ac4a605d2309227b938d5b63a96.png) or ![B_h](./images/ed806363e7593bfb85745e769a27899ad2058cd7.png) at random when encoding each bit of information she wants to send. Bob chooses to perform his measurement randomly, either in the standard basis or in the Hadamard basis. The information is transmitted correctly whenever Bob happens to pick the same basis as Alice, which happens about half the time. Whenever Bob’s basis for measurement is different from the basis Alice uses for encoding, Bob’s output is completely random.
2.  Alice and Bob publicly announce the basis they used for each transmission and discard the bits where different bases were used. This leaves Alice and Bob with roughly ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) candidate bits of secret key.
3.  Alice and Bob then publicly reveal ![\alpha n](./images/f88c8c75a06ba58eeca31702b39d46acdcffa32f.png) of the candidate bits, which we’ll call the check bits. Assuming the quantum communication channel between Alice and Bob does not introduce any noise, Alice and Bob’s copies of the check bits should be identical, since they used the same basis. If they observe many check bits that disagree, Alice and Bob will immediately abort the protocol.
4.  If the ![\alpha n](./images/f88c8c75a06ba58eeca31702b39d46acdcffa32f.png) check bits agree, then Alice and Bob can be sure the remaining ![(1-\alpha)n](./images/f7120344ec70790fbd204a479d96656aae5583eb.png) bits they share are known only to them.

Consider what happens if the eavesdropper Eve tries to intercept the messages between Alice and Bob. Eve can measure the quantum state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) sent by Alice, then forward to Bob the post measurement state ![\ket{\psi^\prime}](./images/177f51fd790c559fc25662980b3d38811e247f3f.png). Eve is forced to choose a basis for the measurement she performs, and her measurement disturbs the state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) whenever she picks a basis different from the one used by Alice. Since it’s not possible to measure quantum systems without disturbing them, the eavesdropper Eve reveals her presence by introducing errors in the transmitted data. Some of the _check bits_ Alice and Bob compare in Step 3 will disagree, and thus Alice and Bob will know that someone is eavesdropping on them. Though quantum mechanics does not prevent eavesdropping, it does give Alice and Bob the ability to detect when an eavesdropper is present.

The BB84 protocol established the beginning of a new field at the intersection of computer science and physics that studies _quantum key distribution_ protocols. The field has developed rapidly from theory to research, and today there are even commercial quantum cryptography systems. It’s interesting to compare quantum cryptography with the public key cryptography systems discussed in[Section 7.9](./Chapter 7_ Applications.md). The security of the RSA public-key encryption is based on the computational difficulty of factoring large numbers. The security of quantum cryptography is guaranteed by the laws of quantum mechanics.

\[ Bennett–Brassard quantum cryptography protocol from 1984 \]

[`https://en.wikipedia.org/wiki/BB84`](./BB84.md)

\[ Using quantum phenomena to distribute secret keys \]

[`https://en.wikipedia.org/wiki/Quantum_key_distribution`](./Quantum_key_distribution.md)

###[Quantum computing](./Front matter.md)

The idea of quantum computing has existed since the early days of quantum mechanics. Richard Feynman originally proposed the idea of a _quantum simulator_ in 1982, which is a quantum apparatus that can simulate the quantum behaviour of another physical system. Imagine a device that can simulate the behaviour of physical systems that would otherwise be too difficult and expensive to build. The quantum simulator would be much better at simulating quantum phenomena than any simulation of quantum mechanics on a classical computer.

Another possible application of a quantum simulator could be to encode classical mathematical optimization problems as constraints in a quantum system, then let the quantum evolution of the system “search” for good solutions. Using a quantum simulator in this way, it might be possible to find solutions to optimization problems much faster than any classical optimization algorithm could.

Once computer scientists started thinking about quantum computing, they weren’t satisfied with studying optimization problems alone, and they set out to qualify and quantify all the computational tasks that are possible with qubits. A quantum computer stores and manipulates information that is encoded as quantum states. It’s possible to perform certain computational tasks on a quantum computer much faster than on any classical computer. We’ll discuss _Grover’s search algorithm_ and _Shor’s factoring algorithm_ below, but first let’s introduce the basic notions of quantum computing.

#####[Quantum circuits](./Front matter.md)

Computer scientists like to think of quantum computing tasks as series of “quantum gates,” in analogy with the logic gates used to construct classical computers.[Figure 9.20](./Chapter 9_ Quantum mechanics.md) shows an example of a quantum circuit that takes two qubits as inputs and produces two qubits as outputs.

![quantumcircuit_make_EPR](./images/quantumcircuit_make_EPR.png)

Figure 9.20: A quantum circuit that applies the Hadamard gate to the first qubit, then applies the controlled-NOT gate from the first qubit to the second qubit.

This circuit in[Figure 9.20](./Chapter 9_ Quantum mechanics.md) is the combination of two quantum gates. The first operation is to apply the Hadamard gate ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) on the first qubit, leaving the second qubit untouched. This operation is equivalent to multiplying the input state by the matrix ![H \otimes \mathbbm{1}](./images/668ae67f418bb10440cdc247eb6116132b86c911.png). The second operation is called the _controlled-NOT_ (or controlled-![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png)) gate, definition-CNOT which applies the ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) operator (also known as the NOT gate) to the second qubit whenever the first qubit is ![\ket{1}](./images/99b52329621ddf0314b460051f95a100390a3b04.png), and does nothing otherwise:

![\textrm{CNOT}(\ket{0}\otimes\ket{\varphi})=\ket{0}\otimes\ket{\varphi},
\qquad
\textrm{CNOT}(\ket{1}\otimes\ket{\varphi})= \ket{1}\otimes X\ket{\varphi}.](./images/68adc3f12cbe644e2f2878964ec3ed4b382bd2e1.png)

The circuit illustrated in[Figure 9.20](./Chapter 9_ Quantum mechanics.md) can be used to create entangled quantum states. If we input the quantum state ![\ket{00} = \ket{0}\!\otimes\!\ket{0}](./images/ba223c27f36e5aa41d8f5be24f8818c9932db285.png) into the circuit, we obtain the maximally entangled state ![\ket{\Phi_+} = \tfrac{1}{\sqrt{2}}\left(\ket{00} + \ket{11}\right)](./images/f3432319fe4c0bf2ed02fd47629538bceb35a159.png) as output, as depicted in[Figure 9.21](./Chapter 9_ Quantum mechanics.md).

![circuit_make_EPR_states](./images/circuit_make_EPR_states.jpg)

Figure 9.21: Inputting ![\ket{0}\!\otimes\!\ket{0}](./images/f8b3d766ee7af7b7605789c4d186e5865f1b3083.png) into the circuit produces an EPR state ![\ket{\Phi_+} = \tfrac{1}{\sqrt{2}}\left(\ket{00} + \ket{11}\right)](./images/ad50f04f007e746970fd81eece24bf5d3d12de2e.png) on the two output wires of the circuit.

Quantum circuits can also represent quantum measurements.[Figure 9.22](./Chapter 9_ Quantum mechanics.md) shows how a quantum measurement in the standard basis is represented.

![circuit_measure_in_Bs](./images/circuit_measure_in_Bs.jpg)

Figure 9.22: Measurement in the standard basis ![B_s = \{\ket{0},\ket{1}\}](./images/3c4d943f2188b14f714cd7fbb291f118e8f691c5.png). The projectors of this measurement are ![\Pi_0 = \ketbra{0}{0}](./images/d93f0a71ecfe9cc49dbc687f77134559d63b13a4.png) and ![\Pi_1 = \ketbra{1}{1}](./images/fbca922c1daff45c7f462d5ef1c4ebe2f0c66055.png).

We use double lines to represent the flow of classical information in the circuit.

#####[Quantum registers](./Front matter.md)

Consider a quantum computer with a single register ![\ket{R}](./images/34310ed41afb29588e9886a7eb8477847a919dde.png) that consists of three qubits. The quantum state of this quantum register is a vector in ![\mathbb{C}^2\otimes \mathbb{C}^2 \otimes \mathbb{C}^2](./images/49acfadff3b95fc3fd1d561cb0120b8132b2704f.png):

![\ket{R}
=
\; \; 
\left(
\alpha_1\ket{0} + \beta_1\ket{1}
\right)
\; \otimes \; 
\left(
\alpha_2\ket{0} + \beta_2\ket{1}
\right)
\; \otimes \; 
\left(
\alpha_3\ket{0} + \beta_3\ket{1}
\right),](./images/941cee80864cb82c1c32c252a41e92c7e2f4138b.png)

where the tensor product ![\otimes](./images/60b5df432c9aa653a66fb2cddc4f588b4b119172.png) is used to combine the quantum states of the individual qubits. We’ll call this the “physical representation” of the register and use ![0](./images/ed78710f64c241b4a45fdd6d2cfe456060dd90fc.png)\-based indexing for the qubits. Borrowing language from classical computing, we’ll call the rightmost qubit the _least significant_ qubit, and the leftmost qubit the _most significant_ qubit.

The tensor product of three vectors with dimension two is a vector with dimension eight. The quantum register ![\ket{R}](./images/34310ed41afb29588e9886a7eb8477847a919dde.png) is thus a vector in an eight-dimensional vector space. The quantum state of a three-qubit register can be written as:

![\ket{R}
=
a_0\ket{0} + a_1\ket{1} + a_2\ket{2} + a_3\ket{3} + a_4\ket{4} + a_5\ket{5} + a_6\ket{6} + a_{7}\ket{7},](./images/5122a5e758ba247e8043d401a034187f8d6866ff.png)

where ![a_i](./images/742468daa9df98467c8672fd641aa4d150e2d2ed.png) are complex components. We’ll call this eight-dimensional vector space the “logical representation” of the quantum register. Part of the excitement about quantum computing is the huge size of the “logical space” where quantum computations take place. The logical space of a ![10](./images/fd39ea446d2046417cbd0fc131073609dd557e3d.png)\-qubit quantum register has dimension ![2^{10}=1024](./images/3729a835a23609590ae40b7f2564c935d5150f3f.png). That’s ![1024](./images/e4e38d6140556ae9147eb75eb16e182614712f81.png) complex components we’re talking about. That’s a big state space for just a 10-qubit quantum register. Compare this with a 10-bit classical register, which can store one of ![2^{10}=1024](./images/3729a835a23609590ae40b7f2564c935d5150f3f.png) discrete values.

We won’t discuss quantum computing further here, but I still want to show you some examples of single-qubit quantum operations and their effect on the tensor product space, so you’ll have an idea of the craziness that is possible.

#####[Quantum gates](./Front matter.md)

Let’s say you’ve managed to construct a quantum register; what can you do with it? Recall the single-qubit quantum operations ![Z](./images/53f6f5c482e34c26d20fc819d706dba659b581dd.png), ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png), and ![H](./images/d73b3f224add0df7b4a6810731221dfc7014ead5.png) we described earlier. We can apply any of these operations on individual qubits in the quantum register. For example, applying the ![X= \begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}](./images/576c42d0bc7ce42667c968559fd644da650eb7f9.png) gate to the first (most significant) qubit of the quantum register corresponds to the following quantum operation:

![circuit_operator_X11_equation](./images/circuit_operator_X11_equation.png)

The operator ![X\!\otimes\!\mathbbm{1}\!\otimes\!\mathbbm{1}](./images/f28b064badeac9ee9ec1f1a381780811f3d48bdc.png) “toggles” the first qubit in the register while leaving all other qubits unchanged.

Yes, I know the tensor product operation is a bit crazy, but that’s the representation of composite quantum systems and operations so please get used to it. What if we apply the ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) operator to the middle qubit?

![circuit_operator_1X1_equation](./images/circuit_operator_1X1_equation.png)

Compare the structure of the operators ![X\!\otimes\!\mathbbm{1}\!\otimes\!\mathbbm{1}](./images/f28b064badeac9ee9ec1f1a381780811f3d48bdc.png) and ![\mathbbm{1}\!\otimes\!X\!\otimes\!\mathbbm{1}](./images/2371387b408ab6e63e321c60266822f5fc1383de.png). See how the action of ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png)s affects different parts of the tensor product space ![\mathbb{C}^8](./images/80aab69852a3f61875470a8a9ddd1a8efb3c558d.png)?

To complete the picture, let’s also see the effects of applying the ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png) gate to the third (least significant) qubit in the register:

![circuit_operator_11X_equation](./images/circuit_operator_11X_equation.png)

Crazy stuff, right? Don’t worry, in time you’ll get used to the space-within-a-space structure concept.

####[Okay, so what?](./Front matter.md)

Quantum computers give us access to a very large state space. The fundamental promise of quantum computing is that a small set of simple quantum operations (quantum gates) can be used to perform interesting computational tasks. Sure it’s difficult to interact with and manipulate quantum systems, but the space is so damn big that it’s worth checking out what kind of computing you can do in there. It turns out there are already several useful things you can do using a quantum computer. The two flagship applications for quantum computing are Grover’s search algorithm and Shor’s factoring algorithm.

#####[Grover’s search algorithm](./Front matter.md)

Suppose you’re given an unsorted list of ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) items and you want to find a particular item in that list. This is called an _unstructured search problem_. This is a hard problem to solve for a classical computer since the algorithm must parse through the entire list, which takes roughly ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png) steps. In contrast, the unstructured problem can be solved in roughly ![\sqrt{n}](./images/c86ab926ce6c72a01450c7c95191f884f786f33e.png) steps on a quantum computer using _Grover’s search algorithm_.

The quantum speed for the unstructured search problem sure is nice, but it’s really nothing to get excited about. The real money-maker for the field of quantum computing has been Shor’s factoring algorithm for factoring products of prime numbers.

#####[Shor’s factoring algorithm](./Front matter.md)

The security of the RSA cryptosystem we discussed in[Section 7.9](./Chapter 7_ Applications.md) is based on the assumption that factoring products of large prime numbers is computationally intractable. Given the product ![de](./images/54693ae4d78d139e51c7dd356b91933e547d0183.png) of two unknown prime numbers ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png) and ![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png), it is computationally difficult to find the factors ![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png) and ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png). No classical algorithm is known that can factor large numbers; even the letter agencies will have a hard time finding the factors of ![de](./images/54693ae4d78d139e51c7dd356b91933e547d0183.png) when ![d](./images/4fd85ab618590fbfafc2c84f0ce55a727a10205c.png) and ![e](./images/b8d218c7d309ebacc998b568fbc541c8f7e0c424.png) are chosen to be sufficiently large prime numbers. Thus, if an algorithm that could quickly factor large numbers existed, attackers would be able to break many of the current security systems. _Shor’s factoring algorithm_ fits the bill, theoretically speaking.

Shor’s algorithm reduces the factoring problem to the problem of _period finding_, which can be solved efficiently using the quantum Fourier transform. Shor’s algorithm can factor large numbers efficiently (in polynomial time). This means RSA encryption would be easily hackable by running Shor’s algorithm on a sufficiently large, and sufficiently reliable quantum computer. The letter agencies are excited about this development since they’d love to be able to hack all present-day cryptography. Can you imagine not being able to log in securely to any website because Eve is listening in, hacking your crypto using her quantum computer?

Currently, Shor’s algorithm is only a _theoretical_ concern. Despite considerable effort, no quantum computers exist today that can manipulate quantum registers with thousands of qubits.

###[Discussion](./Front matter.md)

Quantum computing certainly presents interesting possibilities, but it’s a little early to imagine a quantum computing revolution in tomorrow’s newspaper. As with startup ventures, it’s the implementation that counts—not the idea. The current status of quantum computing as a technology is mixed. On one hand, certain quantum algorithms performed in logical space are very powerful; on the other hand, the difficulty of building a quantum computer is not to be underestimated.

It’s also important to keep in mind that quantum computers are not better at solving arbitrary computational problems than the computers we already use. The problems that may benefit from a quantum speedup have a particular structure, which can be tackled with a choreographed pattern of constructive and destructive interference in quantum registers. Yet not all computationally hard problems have this structure. Quantum computing technology is at a crossroad: it could become a revolutionary development, or it could turn out that building a large-scale quantum computer is not worth the engineering challenge. So although it’s cool we can execute certain tasks faster on a quantum computer, don’t throw out your classical computer just yet.

Even if the quest to build a quantum computer doesn’t pan out, we’re certain to learn many interesting things about fundamental physics along the way. Besides, learning about the fundamental nature of quantum information is more scientifically valuable than trying to hack people’s email. In the next section, we’ll give an example of a new communication task that was discovered through the study of quantum information science.

#####[Quantum teleportation](./Front matter.md)

[Figure 9.23](./Chapter 9_ Quantum mechanics.md) illustrates a surprising aspect of quantum information: we can “teleport” a quantum state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) from one lab to another. The quantum state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) starts in the first qubit of the register, which is held by Alice, and ends in the third qubit, which is in Bob’s lab, but there is no quantum communication channel between the two labs. This is why the term “quantum teleportation” was coined to describe this communication task, since the state ![\ket{\psi}](./images/683adc68524b1fe588a06ca68ac6fe1855881f53.png) seems to materialize in Bob’s lab like the teleportation machines used in Star Trek.

The communication resources required for the quantum teleportation protocol are one maximally entangled state shared between Alice’s and Bob’s labs, and two bits of classical communication from Alice to Bob. We can express the quantum teleportation protocol as a quantum circuit.

![quantum_teleportation_wEPR](./images/quantum_teleportation_wEPR.jpg)

Figure 9.23: The first two qubits are in Alice’s lab. The state of the first qubit ![\ket{\psi}_1](./images/57b29cc250fc0732da55c9dfcc38c82076561f25.png) is transferred into the third qubit ![\ket{\psi}_3](./images/c5cb8f3d7f8054504a6afe6cffc2b82e70a79ecd.png), which Bob controls. We say ![\psi](./images/765f660e3046950453d2bb9111def6187c51d42c.png) is “teleported” from Alice’s lab to Bob’s lab because the quantum state ends up in Bob’s lab, but there is no quantum communication channel connecting the labs. The state teleportation happens thanks to the pre-shared entanglement and the two bits of classical information.

The quantum teleportation protocol requires that Alice and Bob pre-share a maximally-entangled state ![\ket{\Phi_+}](./images/4f5963c7727acd0f42ac284f2be2e9ed836488b0.png). By meeting in a central location, Alice and Bob can produce an entangled state using the circuit shown in[Figure 9.21](./Chapter 9_ Quantum mechanics.md) (page 9.21). Alice and Bob then bring their respective halves of the entangled state to their labs. Note Bob’s lab could be very far from Alice’s lab; in another building, another city, or even on the other side of the world.

The initial state for the quantum teleportation protocol is

![\ket{\psi}_1 \otimes \ket{\Phi_+}_{23}
=
\Big( \alpha \ket{0}_1 + \beta \ket{1}_1 \Big) \otimes \Big(\tfrac{1}{\sqrt{2}} \ket{00}_{23}+ \tfrac{1}{\sqrt{2}} \ket{11}_{23}\Big).](./images/79ed0b3237df4ffcb7b7b6bd2d9b283f0e7dbb66.png)

Alice has two qubits in her lab, the state ![\ket{\psi}_1=\alpha \ket{0}_1 + \beta \ket{1}_1](./images/549d4f58ffc689097b8d472c9f509cef05a562cf.png) and half of the entangled state, and Bob has the third qubit, which is the other half of the entangled state. At the end of the teleportation protocol, information about the state ![\psi](./images/440347364b0dc1c934358fc53b9274442f0d5218.png) appears in Bob’s lab: ![\ket{\psi}_3 = \alpha \ket{0}_3 + \beta \ket{1}_3](./images/f758712a94899d930e2704079591881591d3918b.png).

Without quantum communication, it seems impossible for Alice to communicate the components ![\alpha](./images/b9dfc3328aa36a7f1982470015d2e3e2072a2471.png) and ![\beta](./images/74ceb4673da4e180432c7530d8e9675dc2a174b2.png) to Bob. The pre-shared entanglement between Alice and Bob somehow enables this feat. The quantum information about the state ![\psi](./images/440347364b0dc1c934358fc53b9274442f0d5218.png) becomes available in Bob’s lab as soon as Alice performs the measurement of her two qubits. But before Bob obtains the state information, he must apply a _recovery operation_, which is one of ![\mathbbm{1}](./images/279a0132a1d3e9d1823b0bd6519a11d368b79e21.png), ![X](./images/8e81540b01d8fe9252e62af8bd4daee9ff01b2aa.png), ![Z](./images/53f6f5c482e34c26d20fc819d706dba659b581dd.png), or ![ZX](./images/037f2edb2a4df8e5a79d4fa1781f051643e72293.png). The state information will remain unknown until Bob learns which of the four recovery operations he must perform on the state. The information about which operation Bob should perform can be transmitted by classical means: Alice can shout the result to Bob if he’s next door, tell him the results by phone, or send him a text message. After applying the needed recovery operation, Bob obtains the state ![\ket{\psi}_3=\alpha \ket{0}_3 + \beta \ket{1}_3](./images/f758712a94899d930e2704079591881591d3918b.png), which is the state that originated in the first qubit controlled by Alice.

The need for pre-shared entanglement ![\ket{\Phi_+}](./images/4f5963c7727acd0f42ac284f2be2e9ed836488b0.png) between Alice and Bob is analogous to how Alice and Bob needed to pre-share a secret key ![\vec{k}](./images/0e9caa4a126a21a0dec6f75d21915c5ab819e473.png) in order to use the one-time pad encryption protocol. Indeed, pre-shared entangled states are a prime resource in quantum information science. The _superdense coding protocol_ is another surprising application of quantum entanglement. With this protocol, Alice can communicate two bits of classical information to Bob by sending him a single qubit and consuming one pre-shared entangled state.

####[Links](./Front matter.md)

\[ Quantum simulators and practical implementations \]

[`https://en.wikipedia.org/wiki/Quantum_simulator`](./Quantum_simulator.md)

\[ Some data about the difficulty of RSA factoring \]

[`https://en.wikipedia.org/wiki/RSA_numbers`](./RSA_numbers.md)

\[ Video tutorials on quantum computing by Michael Nielsen \]

[`http://michaelnielsen.org/blog/quantum-computing-for-the-determined/`](./quantum-computing-for-the-determined.md)

\[ Grover’s algorithm for unstructured search \]

[`https://en.wikipedia.org/wiki/Grover’s_algorithm`](./Grover's_algorithm.md)

\[ Shor’s algorithm for factoring products of prime integers \]

[`https://en.wikipedia.org/wiki/Shor’s_algorithm`](./Shor's_algorithm.md)

\[ Emerging insights on limitations of quantum computing \]

[`https://archive.siam.org/pdf/news/100.pdf`](./100.pdf.md)

###[Quantum error-correcting codes](./Front matter.md)

Quantum states are finicky things. Every interaction of a qubit with its environment corrupts the quantum information the qubit stores. In the previous section we talked about quantum computing in the abstract, assuming the existence of an ideal noiseless quantum computer. Since the real world is a noisy place, constructing a practical quantum computer is a much greater challenge.

Recall that errors caused by noise are also a problem for classical computers. If classical computers can be made robust to errors using error-correcting codes, can we use error-correcting codes on quantum computers too? Indeed it’s possible to use _quantum error-correcting codes_ to defend against the effects of quantum noise. Keep in mind, quantum error-correcting codes are more complicated to build than their classical counterparts, so it’s not an obvious thing to do, but it can be done.

We won’t go into too much detail, but it’s worth pointing out the following interesting fact about quantum error correction. Building quantum error-correcting codes that can defend against a finite set of errors is sufficient to defend against all possible types of errors. The use of quantum error-correcting schemes is analogous to the classical error-correcting schemes we saw in[Section 7.10](./Chapter 7_ Applications.md). We encode ![k](./images/c60d09aea335984ef7ab564ee287c738da4c41e3.png) qubits of data that we want to protect from noise into a larger ![n](./images/f46231b1dbfc82e7ce67d8d34e269315d70fecb8.png)\-qubit state. The encoded state can support some number of errors before losing the data. The error-correcting procedure involves a syndrome measurement on a portion of the state, and “correction” operators applied to the remaining portion. I encourage you to follow the links below to learn more about this topic.

Building reliable quantum gates is a formidably complicated task due to the difficulty of protecting qubits from noise while simultaneously enabling quantum operations and strong interactions between qubits. It is the author’s opinion that Feynman’s original idea of building quantum simulators for physical systems will be the first useful applications in quantum computing.

\[ More on quantum error-correcting codes \]

[`https://en.wikipedia.org/wiki/Quantum_error_correction`](./Quantum_error_correction.md)

###[Quantum information theory](./Front matter.md)

Classical information theory studies problems like the compression of information and the transmission of information through noisy communication channels. Quantum information theory studies the analogous problems of compression of quantum information and communication over noisy quantum channels.

The appearance of the word “theory” in “quantum information theory” should indicate that this is a mostly theoretical area of research that studies problems in the abstract. The main results of information theory are abstract theorems that may not have direct bearing on practical communication scenarios. For now, applications of quantum information theory remain in the far-off future, but that’s how it is with theory subjects in general. The classical information theorems proven in the 1970s probably looked a bit useless, too; but these theorems serve as the basis of all modern wireless communications. Perhaps the purely theoretical quantum information theorems of today will solve the practical communication problems of the future.

Current efforts in quantum information theory aim to establish capacity results for quantum channels. Some of the existing results are directly analogous to classical capacity results. Other problems in quantum information theory, like the use of entanglement-assisted codes, have no classical counterparts and require a completely new way of thinking about communication problems. The book _From Classical to Quantum Shannon Theory_ by Mark M. Wilde is an excellent guide to the field.

Recently, quantum theory has been applied to novel communication systems, and there is a growing interest from the communications industry to develop applications that push optical communication channels to the bounds of their theoretical efficiency. Essentially, quantum networks are being invented in parallel with quantum computers, so that when we finally build quantum computers, we’ll be able to connect them together, presumably so they can share funny cat videos. What else would we use them for?

\[BOOK\] Mark M. Wilde. _From Classical to Quantum Shannon Theory_, Cambridge University Press, Second edition, ISBN 1107176166,[`http://arxiv.org/abs/1106.1445`](./1106.1445.md).

###[Conclusion](./Front matter.md)

With this chapter, I wanted to bring you closer to the fascinating subject of quantum mechanics. I hope the material helped you understand the basic principles of quantum mechanics and clarified some of the sensational mythology surrounding the “mysteries” of the quantum world. While there’s still much to discover, there’s nothing too counterintuitive about quantum mechanics; it’s just linear algebra, right?

One hundred years ago, quantum mechanics was seen as a foreign subject not to be trusted. In time, physicists developed good models, found better ways to explain experiments, wrote good books, and even started teaching the subject to undergraduate students. This gives me hope for humanity that we can handle even the most complex and uncertain topics when we put our minds to it.

Today we face many complex problems: consolidated corporate control of innovation, cartels, corruption, eroding democratic government systems, the militarization of everything, and conflicting ideologies. We have Sunni and Shia brothers shooting at each other and red gang versus blue gang brothers shooting at each other, and all of this for no good reason. We have all kinds of other bullshit divisions between us.

Let’s hope that one hundred years from now, we’ll have learned to limit the violent and corrupt aspects of human nature, so that we can realize the potential of every child born anywhere in the world. Right now it seems like it won’t be an easy change, but this is how it seemed when people were trying to figure out quantum mechanics, too. All it takes is a critical mass of people who realize and truly internalize the fact we’re all on the same team, and all the divisions we see between us are pure bullshit. If we make sure that two generations of kids grow up without economic strife or bullets flying by their heads, then—I guarantee you—they will be able to figure out the rest. Together, an educated citizenry armed with the knowledge of math, history, science, and technology is more powerful than a dozen Systems combined. All the System has is an outdated hierarchical power structure and capital to pay people and make them do as they’re told. We’ve got six billion people, the internet, and printing presses on our side. Who do you think will win?

##[9.7 Quantum mechanics problems](./Chapter 9_ Quantum mechanics.md)

Let’s recap what just happened here. Did we really cover all the topics of an introductory quantum mechanics course? Yes, we did! Thanks to your solid knowledge of linear algebra, learning the postulates of quantum mechanics took only a few dozen pages. Sure we went quickly and skipped the more physics-y topics, but we covered all the core ideas of quantum theory.

But surely it’s impossible to learn quantum mechanics in such a short time? Well, you tell me. You’re here. The problems are here. Prove to me you’ve really learned quantum mechanics by tackling the practice problems presented in this section like a boss. It’s the end of the book, so don’t be saving your energy. Solve these problems and then you’re done.

P9.1 You work in a quantum computing startup and your boss asks you to implement the quantum gate ![Q = 
\tfrac{1}{\sqrt{2}}
\begin{bmatrix}
1		& 1	\\
1		& 1	
\end{bmatrix}](./images/e3f5d33e9155ed54ed78b80268e0ca57b852fcd4.png). Can you do it?

Recall the requirements for quantum gates.

P9.2 The ![Y](./images/af40f50353f77406a09c621b7bba6537bc9c6750.png) gate is defined as ![Y=\begin{bmatrix}0	& \; -i \\ i & \; 0\end{bmatrix}](./images/a7c0e46d00a88f6969d93a20f89cdccb640100c3.png). Compute the effect of the operator ![YY](./images/ffeb1bbc6506847a88bc4470e65619cf33ac6278.png) on the vectors of the standard basis ![\{ \ket{0}, \ket{1} \}](./images/0a9e65abda6005204b5349de4c1c0a076ba6d238.png).

P9.3 Compute ![XHHY(\alpha\ket{0} + \beta\ket{1})](./images/a600e80ea7c1209d5df53d46b0d9e1830f4641e9.png).

Use the Hadamard gate’s properties to simplify the calculation.

P9.4 Specifying an arbitrary vector ![\alpha\ket{0}+\beta\ket{1} \in \mathbb{C}^2](./images/ed196ab56da6a42dc98984a0a94eeb52fded3cf2.png) requires four parameters: the real and imaginary parts of ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png) and ![\beta](./images/bc326c959b80d3a24fcdf5fda29ab07ecaf549ba.png). Thus one might think that qubits have four _degrees of freedom_. However, the unit-length requirement and the fact that we can ignore the global phase of a qubit correspond to additional constraints that reduce the number of degrees of freedom. How many parameters are required to specify a general quantum state ![\ket{\psi} \in \mathbb{C}^2](./images/06f2f629f6e67e8e08a7f78c6618099630d01ec4.png)?

P9.5 We can write any qubit using only two real parameters:

![\ket{\psi} 	= \alpha\ket{0} + \sqrt{1-\alpha^2}e^{i\varphi}\ket{1},](./images/1e051723b4227296cc4da17400ffe9e5f42f7ec6.png)

where ![\alpha \in \mathbb{R}](./images/69bd52ea0910ca7e80a86efe3ae4c0a8bc2fe403.png) and ![\varphi \in  \mathbb{R}](./images/a8573971a52ef6654095a1ae04cf9019e599ccdd.png). What are the ranges of values for ![\alpha](./images/d2a763c0a51c2a9f47548a9572c0d0a0e38dc44f.png) and ![\varphi](./images/6f14e9ed0b9ebc16fdc9b26b6156e6d595813474.png) such that all qubits can be represented?

P9.6 Consider the parametrization for qubits using two angles ![\theta](./images/962d17a7e21d58659675e6e02789c85029447dd5.png) and ![\varphi](./images/6f14e9ed0b9ebc16fdc9b26b6156e6d595813474.png):

![\ket{\psi} 	= 
\cos\!\left( \theta/2\right) \ket{0} +\sin\!\left( \theta/2\right) e^{i\varphi}\ket{1}.](./images/8750e1fb739d6d1b70c2d0a3e1e2964ddf9fda9e.png)

What values should ![\theta](./images/962d17a7e21d58659675e6e02789c85029447dd5.png) and ![\varphi](./images/6f14e9ed0b9ebc16fdc9b26b6156e6d595813474.png) have for all qubits to be represented?

P9.7 Compute the products of the quantum gates ![HXH](./images/e9339d4b30b85ee65c6b6e87557a3efbc01d8246.png) and ![HZH](./images/6c436e9caaba2003aaaf55c72ff87222cb07566f.png).

P9.8 Consider the state ![\ket{v} = (a,b)^\sfT](./images/9c884ec28230e3f3cb911929a8acd300afd712cd.png) and its orthogonal complement ![\ket{v^\perp}=(\overline{b}, -\overline{a})^\sfT](./images/b7a022d9115160e3164dc5f15f2119ee98b6c758.png). The projection operators ![\Pi_v](./images/8d3b5aa47817b0d8f619d8e52e92c995ebde0400.png) and ![\Pi_{v^\perp}](./images/192cfa114ee30105d775c8102cc7404eef840d4e.png) correspond to the measurements in the basis ![\{ \ket{v}, \ket{v^\perp} \}](./images/211d3c9393e1b96917806da1c3a851c288cb7115.png). Compute the probability of outcome ![v](./images/14593f3784642e49a79b179a9f00f7f98ec4f6e3.png) in the measurement ![\{ \Pi_v, \Pi_{v^\perp}\}](./images/ba3ffe04d325f296e804c71c07a955b92a1bb208.png) on the state ![\ket{\psi} =  \alpha \ket{0} + \beta \ket{1}](./images/6a09bd69c925c0d631bddbc9c440b2c4b4335689.png).

P9.9 When we measure a quantum system ![\ket{\psi}=\alpha\ket{0} +\beta\ket{1}](./images/6a09bd69c925c0d631bddbc9c440b2c4b4335689.png) in the basis ![\{ \ket{0}, \ket{1} \}](./images/0a9e65abda6005204b5349de4c1c0a076ba6d238.png), the Born rule tells us the probability of outcome ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png) is equal to ![\bra{\psi}\Pi_0\ket{\psi}](./images/c0ce8fc003e50801759018cf3d2056ab7628af5b.png). Consider this calculation that involves the trace operation:

![\begin{align*}
\Pr(\{0\} | \psi )
&=	\bra{\psi}\Pi_0\ket{\psi}
=
\bra{\psi}
\begin{bmatrix} 1&0 \\  0 &0 \end{bmatrix}
\ket{\psi}
=
\Tr \left\{
\bra{\psi}
\begin{bmatrix} 1&0 \\  0 &0 \end{bmatrix}
\ket{\psi}
\right\}														\\
&\stackrel{(c)}{=} 	\Tr \left\{
\begin{bmatrix} 1&0 \\  0 &0 \end{bmatrix}
\ketbra{\psi}{\psi}
\right\}
=  \Tr \bigg\{
\begin{bmatrix} 1&0 \\  0 &0 \end{bmatrix}
\underbrace{
\begin{bmatrix} |\alpha|^2 & \overline{\beta}\alpha \\  \overline{\alpha}\beta &|\beta|^2 \end{bmatrix}
}_{\text{density matrix}}
\bigg\}															\\
&=	\Tr \bigg\{
\begin{bmatrix}|\alpha|^2 & \overline{\beta}\alpha \\  0 & 0 \end{bmatrix}
\bigg\} = |\alpha|^2.
\end{align*}](./images/0d59d283597e778bb88e28a332d8fa1c488586b6.png)

The equality labelled ![(c)](./images/310cae1017f953b6d39d04da72e570ac217c37fb.png) follows from the cyclic property of the trace operation ![\Tr\{ABC\} = \Tr\{BCA\}](./images/3f68defbb19df0376f626568705bd21146fe2ad7.png). The above calculation suggests an alternative approach for computing the probabilities of different outcomes of quantum measurements, ![\Pr(\{x\} | \psi ) = \Tr\{ \Pi_x \rho \}](./images/55863c0a022a5602869d4a73be9389be1a39bb4d.png), where ![\rho](./images/5381546665bb83189091e520c5dfc0a46fabbd0a.png) is the[_density matrix_](./Density_matrix.md) representation of the quantum state. The density matrix of the quantum state ![\ket{\psi}=\alpha\ket{0} +\beta\ket{1}](./images/6a09bd69c925c0d631bddbc9c440b2c4b4335689.png) corresponds to the outer product ![\rho = \ketbra{\psi}{\psi}](./images/542558c3edf8901ed5dfd1feed44adb3664f5d4e.png). Calculate the probability of outcome ![\{1\}](./images/c89e3ba6e4ea07716a317a8f32dbddbf8913a83d.png) using ![\Pr(\{1\} | \psi ) = \Tr\{ \Pi_1 \rho \}](./images/2944aba66dc6ebae9919adba86155f97868d48ac.png). Calculate the probabilities of the two outcomes of a measurement in the Hadamard basis ![\Pr(\{+\} | \psi )= \Tr\{ \Pi_+ \rho \}](./images/f42099c847b32c13f7404ffe56b9685554799daa.png) and ![\Pr(\{-\} | \psi )= \Tr\{ \Pi_- \rho \}](./images/232081a1d71169dc623812fc5a2875cd2f7a5193.png).

P9.10 This problem explores the operation of the quantum teleportation circuit shown in[Figure 9.23](./Chapter 9_ Quantum mechanics.md) (see page 9.23). The initial state of the three-qubits register is ![\ket{\psi}_1 \otimes \ket{\Phi_+}_{23}](./images/455fca0b7e67b8b0fe819ebc46df0211cad74370.png), where ![\ket{\psi} =  \alpha\ket{0}+\beta\ket{1}](./images/6a09bd69c925c0d631bddbc9c440b2c4b4335689.png) is a quantum state Alice wants to send to Bob, and where ![\ket{\Phi_{+}} = \tfrac{1}{\sqrt{2}}\!\left( \ket{00} + \ket{11} \right)](./images/1fbafd352dbde3bfd528e3f484161ae6f3987082.png) is a maximally entangled state shared between Alice and Bob.

1.  Show the following equation holds by expanding the tensor product:
    
    ![\ket{\psi}_1 \otimes \ket{\Phi_+}_{23}
    =
    \tfrac{1}{\sqrt{2}}\left[  \alpha\ket{000}_{123}+\beta\ket{100}_{123}+\alpha\ket{011}_{123}+\beta\ket{111}_{123}\right].](../Images/db4ba18b37bf3061c1748732cc78cba659fa6841.png)
    
2.  The expression from part **a)** can be written as a linear combination of the four Bell states: ![\ket{\Phi_{+}} 	= \tfrac{1}{\sqrt{2}}\!\left( \ket{00} + \ket{11} \right)](./images/ad48221bb1ebe176cf63cac1089edf7f2f5c7c00.png), ![\ket{\Phi_{-}} 	= \tfrac{1}{\sqrt{2}}\!\left( \ket{00} - \ket{11} \right)](./images/37ab0e53bc25029792e67226bb702cee284b77ab.png), ![\ket{\Psi_{+}}\!=\!\tfrac{1}{\sqrt{2}}\!\left( \ket{01} + \ket{10} \right)](./images/14c269d6e43e3563a35e9673e87d6697c6905fc7.png), and ![\ket{\Psi_{-}}\!=\!\tfrac{1}{\sqrt{2}}\!\left( \ket{01}\!-\!\ket{10} \right)](./images/a14b057de7638bab0c4352813d3471ea36f15102.png). Verify the equation
    
    ![\begin{align*}
    &\!\! \tfrac{1}{\sqrt{2}}\!\left[  \alpha\ket{000}_{123}+\beta\ket{100}_{123}+\alpha\ket{011}_{123}+\beta\ket{111}_{123}\right]	\\
    & \quad \;  =  \tfrac{1}{2}\Big[
    \ket{\Phi_{+}}_{12} \ket{\psi}_{3}
    +\ket{\Phi_{-}}_{12}Z\ket{\psi}_{3}
    +\ket{\Psi_{+}}_{12}X\ket{\psi}_{3}
    +\ket{\Psi_{-}}_{12}XZ\ket{\psi}_{3}
    \Big].
    \end{align*}](../Images/addd0d6c85d7cd2d111409260ee94a1168ac4185.png)
    
3.  A _Bell measurement_ consists of the combination of a controlled-NOT gate and a Hadamard gate on the first qubit, followed by measurements of both qubits in the standard basis, as illustrated in the circuit below.
    
    ![circuit_pre_Bell_measurement](./images/circuit_pre_Bell_measurement.png)
    
    Using the definition of the controlled-NOT gate (page ) and the Hadamard gate (page ), show that the Bell measurement performed on the state ![\ket{\Phi_{+}}](./images/f70235fb6e6c9ae7575118af22fea7d04ee70110.png) produces the classical measurement outcome ![00](./images/9efeef878cb05606553cca4d5e110de9e3689e69.png). Similarly, show that measuring ![\ket{\Phi_{-}}](./images/4fce6fb678edfd4ee0b413796bb79f6e3ba1079d.png) produces ![10](./images/ceb58fb9d90adb932791148d57ec74a538794a04.png), measuring ![\ket{\Psi_{+}}](./images/37ca516879737a3172efee6e298c84a28deb0c32.png) produces ![01](./images/cbe0d00c20fb1b7c5c41c300823187aa604fb8fb.png), and measuring ![\ket{\Psi_{-}}_{12}](./images/0defc488dceacbec60c04feb97bbe90a81e9a402.png) produces ![11](./images/3d11b18c51ef46f064895fe5a60eacc16cc7efc9.png).
4.  After Alice performs the Bell measurement on the two qubits under her control, the state of Bob’s qubit will be one of the following: ![\ket{\psi}_{3}](./images/cd62179244f1b72e4c319f426c63cc8d2250a249.png) if the measurement outcome is ![00](./images/9efeef878cb05606553cca4d5e110de9e3689e69.png), ![Z\ket{\psi}_{3}](./images/5832a890a57b7da37a060debb5c40d683c64db1f.png) if outcome is ![10](./images/ceb58fb9d90adb932791148d57ec74a538794a04.png), ![X\ket{\psi}_{3}](./images/4109824114bd75d0b8b9b370c56b131b7c743f72.png) if outcome is ![01](./images/cbe0d00c20fb1b7c5c41c300823187aa604fb8fb.png), or ![XZ\ket{\psi}_{3}](./images/409997a08485c766d565a77e8f1b42b86ab66fa8.png) if outcome is ![11](./images/3d11b18c51ef46f064895fe5a60eacc16cc7efc9.png). Indicate the _recovery operation_ Bob must apply in order to recover the state ![\ket{\psi}_{3}](./images/cd62179244f1b72e4c319f426c63cc8d2250a249.png) in each case.

P9.11 The wave function of the electron of the hydrogen atom is ![\psi(\vec{r}) =\frac{1}{\sqrt{\pi a^3}}\exp(-r/a)](./images/e1c68b371944b8f15066a3fbdfd072788c1820fe.png). The electron’s distance from the centre is described by the random variable ![R](./images/71ce7fefa53db4a14c0017370cefd764e17150d5.png) with probability distribution ![\psub{R}(r)=\frac{4}{a^3}\exp(-2r/a)r^2](./images/990cd4f653b104090787668b36921558f85ea817.png). Calculate the expected distance of the electron ![\mathbb{E}_R[R]=\int_{r=0}^{r=\infty}  r \psub{R}(r)\,dr](../Images/f7d24939aa7a8b70af36c7cdecc14642aaa38005.png).

You can solve this problem using integration by parts once.

P9.12 Show that the functions ![\psi_1(x)=2x-1](./images/1d66763ec90e25906caeeb0922fffc7d21ad2aac.png) and ![\psi_2(x)=6x^2-6x+1](./images/d3ed46146e9580d6129974a381c4a1c713f0f8e2.png) are orthogonal with respect to the inner product ![\braket{ f, g } = \int_0^1 \overline{f(x)}g(x) \,dx](./images/35514123aaf94a3dd4d31a5de9df6f981b6a92bb.png).

P9.13 Consider a model of a particle in a one-dimensional box of width one. The state of the particle is described by the wave function ![\psi(x)](./images/bce0ab47f4ec1fd58ff460a981a613b3765b04da.png), where ![x \in[0,1]](../Images/65a2d9d879fac5ae093905ee17598d3528954e49.png). Find the probability of observing ![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) in the first quarter of the box (![x](./images/64e6b171732f9866946e263c64f235cf56f6e538.png) between ![0](./images/a166ece4ed89628d1b35b1da928f948437d520a5.png) and ![\frac{1}{4}](./images/16f97df2aae4eaf5797114583fd4e7d61a7b6cf6.png)) for the following wave functions: **a)** ![\psi_a(x) = \sqrt{3}(2x-1)](./images/48dc027ff9b5c51d8cbf89305ba12e568816249b.png), **b)** ![\psi_b(x) = \sqrt{5}(6x^2-6x+1)](./images/97d3f571a29d0a6182ed792e4386eb7fb73dd28b.png), **c)** a constant wave function ![\psi_c](./images/b4ed27e08bb3969989de5f1c07f9f20f60852cc7.png).

The probability of finding the particle somewhere in the interval ![[a,b]](../Images/3ec6e408e98e8d96932dfe13e4692577e912d0aa.png) is computed using the integral ![\Pr(\{a \leq x \leq b \} | \psi ) = \int_a^b |\psi(x)|^2 \, dx](./images/ae9f3b65850ca52152915f658d2cdd92079eb729.png).
