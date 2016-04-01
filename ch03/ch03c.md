## 3.3 The EPR Paradox and Quantum Entanglement

In the 1930s, Einstein and his two graduate students, Podolski and Rosen, produced what they thought was a decisive argument against the so-called Copenhagen interpretation of quantum mechanics, which maintains that the microscopic world is inherently uncertain. This argument, which became known as the EPR paradox, was the subject of heated debates for nearly five decades. When the question was finally resolved in the early 1980s, it became clear that Einstein's premise was wrong, and that the behavior of quantum particles cannot be explained by deterministic laws and “hidden variables”.

In order to understand the nature of this paradox, we first need to briefly describe what is meant by the “spin” of a particle. The notion of spin arises when relativistic effects are incorporated into quantum mechanics. In ಂrde gain an intuitive grasp of this concept, it is helpful to imagine a ball with a unit radius that spins around its own axis. All points that belong to such a ball obviously experience circular motion (except, of course, those that are on the axis itself). Given the angular velocity of this object, classical physics allows us to uniquely determine the corresponding angular momentum.

The problem with extending this concept to quantum mechanics stems from the fact that particles cannot be viewed as microscopic “balls.” Instead, they are formally represented as *point-like* entities which have no physical dimensions. Such objects clearly cannot rotate around their own axis in any conventional sense, and it is hard to see how one could associate an angular momentum with them. And yet, that is precisely what quantum mechanics does when it talks about the “spin” of a particle.
In dealing with quantum spin, it is important to keep in mind that this property has no counterpart in the world of our everyday experience. We can perhaps interpret it as something that is mathematically similar to conventional rotation, but is ultimately different in kind. The nature of this difference is clearly illustrated by the fact that spin is an *intrinsic* characteristic the particle, just like its mass or charge. This is quite unlike classical physics, where the angular momentum explicitly depends on the velocity of the object.

Spin can be characterized by two pieces of information:
1. The *amount of spin*, which is fixed for a given particle. Particles whose spin is an odd multiple of $$\tfrac{\hbar}{2}$$ are referred to as *fermions*, while those whose spin is an integer multiple of ℏ (including zero) are known as *bosons*.
2. The *direction of the spin*, which can be clockwise or counterclockwise. These two possibilities correspond to “spin up” and “spin down” states, respectively.

To get a sense for how quantum spin is treated mathematically, let us consider an isolated electron, which has the smallest possible amount of spin for a fermion (that is, $$\tfrac{\hbar}{2}$$). What we don't know about the electron's spin is its *direction*, and this is something that we can measure. Since there are only two possible outcomes, the states of *definite spin* can be described by wave functions $$\psi_1$$ and $$\psi_2.$$ If the electron is *not* in one of these two states, its wave function can be expressed as their superposition
$$
\psi=\alpha_1\psi_1+\alpha_2\psi_2\tag{3.61}
$$

where $$|\alpha_1|^2$$ and $$|\alpha_2|^2$$ represent the probabilities of measuring spin up’ and ‘spin down', respectively.

This brief (and admittedly superficial) discussion of quantum spin is all that we really need in order to understand the EPR paradox. The essence of this paradox is perhaps best described in terms of an experiment in which an atom with spin zero disintegrates into two smaller particles (say A and B) that fly off in different directions. According to quantum mechanics, prior to a measurement the state of each particle ought to be a superposition of “up” and “down” spins. Note, however, that if we happen to measure spin “up” for particle A, it is guaranteed that we will subsequently measure spin “down” for B, regardless of the distance between them. This is due to the conservation of angular momentum, which holds both in classical and quantum physics (keep in mind that in this case the spin of the “parent” atom was zero).

The EPR paradox relates to the fact that measuring the spin of particle A somehow places particle B in a state of definite spin as well, although B itself has not yet been “disturbed” (B could actually be very far from A when the measurement occurs). There is no physical mechanism that would allow information about measurements made on particle A to be “instantaneously transmitted” to particle B, given that no signal can propagate faster than light. Based on this apparent contradiction, Einstein argued that quantum mechanics is, in fact, an incomplete theory. He suggested that particles A and B were really subject to “hidden” deterministic laws, and are both in a state of *definite spin* which is decided at their “birth.” He further hypothesized that we may not be able to predict exactly what this state will be, but we can always assign a “classical” probability to each outcome.

Although Einstein and his collaborators were not aware of this at the time, there is actually a way to explicitly test the validity of their conjecture. This test is based on certain properties of classical probabilities which were discovered by physicist John Bell in 1964. To get a sense for what Bell’s result means, suppose that particles A and B have *definite* spins, and consider all possible combinations in the three spatial directions. In __Table 3.1__, these states are summarized as triplets $$(s_x,\:s_y,\:s_z)$$ , which are necessarily complementary for the two particles along each axis, due to the conservation of momentum.

As an illustration, let us consider the probability that particle A has spin 'up' in the $$x$$-direction (*i.e.* $$x\uparrow$$) and that B has spin 'up' in the $$y$$-direction (i.e. $$y\uparrow$$). Out of the eight possible scenarios in the table, only combinations 3 and 4 correspond to this particular outcome. Consequently, the overall probability $$P(x\uparrow,\:y\uparrow)$$ can be expressed as
$$
P(x\uparrow,\:y\uparrow)=\frac{n_3+n_4}{N}\tag{3.62}
$$

#### Table 3.1. Possible spin combinations.
|     | Particle A | Particle B |
| :-: | :--------: | :--------: |
| 1 | $$\left(x\uparrow,\:y\uparrow,\:z\uparrow\right)$$ | $$\left(x\downarrow,\:y\downarrow,\:z\downarrow\right)$$
| 2 | $$\left(x\uparrow,\:y\uparrow,\:z\downarrow\right)$$ | $$\left(x\downarrow,\:y\downarrow,\:z\uparrow\right)$$
| 3 | $$\left(x\uparrow,\:y\downarrow,\:z\uparrow\right)$$ | $$\left(x\downarrow,\:y\uparrow,\:z\downarrow\right)$$
| 4 | $$\left(x\uparrow,\:y\downarrow,\:z\downarrow\right)$$ | $$\left(x\downarrow,\:y\uparrow,\:z\uparrow\right)$$
| 5 | $$\left(x\downarrow,\:y\uparrow,\:z\uparrow\right)$$ | $$\left(x\uparrow,\:y\downarrow,\:z\downarrow\right)$$
| 6 | $$\left(x\downarrow,\:y\uparrow,\:z\downarrow\right)$$ | $$\left(x\uparrow,\:y\downarrow,\:z\uparrow\right)$$
| 7 | $$\left(x\downarrow,\:y\downarrow,\:z\uparrow\right)$$ | $$\left(x\uparrow,\:y\uparrow,\:z\downarrow\right)$$
| 8 | $$\left(x\downarrow,\:y\downarrow,\:z\downarrow\right)$$ | $$\left(x\uparrow,\:y\uparrow,\:z\uparrow\right)$$

where $$n_3$$ and $$n_4$$ represent the number of generated particles with combinations 3 and 4, respectively, while $$N$$ denotes the total number of particles. Following the same procedure, probabilities $$P(x\uparrow,\:z\uparrow)$$ and $$P(z\uparrow,\:y\uparrow)$$ can be computed as
$$
P(x\uparrow,\:z\uparrow)=\frac{n_2+n_4}{N}\tag{3.63}
$$

and
$$
P(z\uparrow,\:y\uparrow)=\frac{n_3+n_7}{N}\tag{3.64}
$$

Observing that
$$
\frac{n_3+n_4}{N}<\frac{n_2+n_4}{N}<\frac{n_3+n_7}{N}\tag{3.65}
$$

we now have that
$$
P(x\uparrow,\:y\uparrow)<P(x\uparrow,\:z\uparrow)<P(z\uparrow,\:y\uparrow)\tag{3.66}
$$

which is one of several possible formulations of *Bell’s inequality*.

This sample result proved to be crucial for verifying the validity of “hidden variable” theories, since it provided a condition that the particles must satisfy if their behavior is truly classical. The definitive experiment along these lines was conducted by Alain Aspect and his collaborators in 1981. Their measurements conclusively established that Bell’s inequality was *violated* in this case, which confirmed that quantum phenomena do not lend themselves to strictly deterministic descriptions.

Given such a result, the only consistent explanation of the EPR paradox is that no matter how far apart A and B are, their common “parentage” prevents us from treating them as separate entities. In technical terms, this means that the two particles shouldn't be described by separate wave functions, but rather by a single one (even if they end up in different galaxies). When particle A is observed, the *joint* wave function collapses, causing particle B to assume a definite spin value as well. According to this interpretation quantum mechanics must be viewed as a *non-local* theory, and all microscopic phenomena are somehow connected into a non-decomposable whole.

### Quantum Entanglement
The process that produces a “joint” wave function for a collection of interacting particles is known as *quantum entanglement*. In order to understand what this means, let us first consider a classical system $$S$$, which consists of two subsystems $$S_1$$ and $$S_2$$. If the possible states of $$S_1$$ and $$S_2$$ are $$\{x_1,\:x_2,\:x_3,\:\cdots\}$$ and $$\{y_1,\:y_2,\:y_3,\:\cdots\}$$, respectively, the overall state of the system can always be uniquely associated with a pair of “microstates” $$(x_i,\:y_i)$$. In this way, the behavior of the “whole” can always be reduced to the behavior of its constituent parts.

In quantum mechanics, the situation is considerably more complicated. To see why this is so, suppose that subsystem $$S_1$$ is initially in state $$\psi_i$$, which corresponds to a definite value of some physical quantity $$A$$. We will make a similar assumption for System $$S_2$$ as well, the only difference being that its state $$\phi_j$$ corresponds to a definite value of physical quantity $$B$$. When these two subsystems *interact*, the state of the resulting composite system $$S$$ can be described as
$$
\chi=\sum_{i,j}\alpha_{ij}(\psi_i\otimes\phi_j)\tag{3.67}
$$

where $$\otimes$$ denotes a mathematical operation that combines functions $$\psi_i$$, and $$\phi_j$$ in a special way.

An important property of this operation it that the state $$\chi$$ of the overall system isn't always reducible to the states of $$S_1$$ and $$S_2$$. As a result, the two subsystems must be viewed as elements of a greater “whole” whose dynamics *include* and *transcend* the dynamics of its parts. The following example illustrates how such “entangled” states can arise in a simple hypothetical model.
### Example 3.5.
Let us consider two subsystems $$S_1$$ and $$S_2$$ whose individual states are described in terms of vectors
$$
x=
\left[\begin{matrix}
x_1\\x_2\\x_3\\x_4
\end{matrix}\right]\tag{3.68}
$$

and
$$
y=\left[\begin{matrix}
y_1\\y_2\\y_3
\end{matrix}\right]\tag{3.69}
$$

respectively. It is easily verified that any state of  $$S_1$$ can be expressed as
$$
x=x_1\psi_1+x_2\psi_2+x_3\psi_3+x_4\psi_4\tag{3.70}
$$

where vectors
$$
\begin{matrix}
\psi_1=\left[\begin{matrix}1\\0\\0\\0\end{matrix}\right];&&
\psi_2=\left[\begin{matrix}0\\1\\0\\0\end{matrix}\right];&&
\psi_3=\left[\begin{matrix}0\\0\\1\\0\end{matrix}\right];&&
\psi_4=\left[\begin{matrix}0\\0\\0\\1\end{matrix}\right]
\end{matrix}\tag{3.71}
$$

represent an orthonormal basis in $$R^4$$. The same holds true for subsystem $$S_2$$, whose states can be expanded as
$$
y=y_1\phi_1+y_2\phi_2+y_3\phi_3\tag{3.72}
$$

using
$$
\begin{matrix}
\phi_1=\left[\begin{matrix}1\\0\\0\end{matrix}\right];&&
\phi_2=\left[\begin{matrix}0\\1\\0\end{matrix}\right];&&
\phi_3=\left[\begin{matrix}0\\0\\1\end{matrix}\right]
\end{matrix}\tag{3.73}
$$

as the basis.

Suppose now that the two subsystems interact in a way that gives rise to composite functions of the form
$$
\chi=\sum_{i=1}^{4}\sum_{j=1}^{3}\alpha_{ij}\left(\psi_i\otimes\phi_j\right)\tag{3.74}
$$
where operator $$\otimes$$ denotes the Kronecker product. Given a pair of vectors $$a\in{R}^4$$ and $$b\in{R}^3$$, this product can be defined as
$$
\begin{align*}
a\otimes{b}&=a\cdot b^T\\
&=\left[\begin{matrix}
a_1b_1&a_1b_2&a_1b_3\\
a_2b_1&a_2b_2&a_2b_3\\
a_3b_1&a_3b_2&a_3b_3\\
a_4b_1&a_4b_2&a_4b_3
\end{matrix}\right]
\end{align*}\tag{3.75}
$$

Although the Kronecker product is considerably simpler than the operator introduced in $$(3.67)$$, there are a number of important similarities between them. Perhaps the most prominent one is that both operations produce aggregate states whose structure is considerably more complex than the structure of the subsystem states This property is apparent from equation $$(3.74)$$, which indicates that the states of the overall system must be described by $$4\times3$$ matrices, while those of $$S_1$$ and $$S_2$$ are adequately represented by vectors of dimension $$4\times1$$ and $$3\times1$$, respectively.

Another property is that is common to both operators is the “irreducibility” of the composite states. In our example, this is due to the fact that a $$4\times3$$ matrix $$\chi$$ can have rank as high as 3, while the rank of $$x\cdot{y}^{T}$$ is always equal to 1. As a result, $$\chi$$ can be expressed in the form
$$
\chi=x\otimes{y}\tag{3.76}
$$

only in very special cases. This clearly indicates that the overall system typically has properties that cannot be associated with the behavior of the subsystems. The “whole”, in other words, is greater than the sum of its parts.

In addition to its explanatory role in the EPR paradox, the phenomenon quantum entanglement also plays an important part in the so-called “measurement problem,” which remains one of the most hotly debated issues in m physics. A fundamental question that arises in this context is how measurement devices should be incorporated into the overall model. Some scientists believe that they should be viewed as quantum systems which interact with the particles whose properties they are designed to measure. Others have claimed that the behavior of the measurement apparatus is essentially classical, and that its description lies outside of quantum theory.

To see the relationship between quantum entanglement and measurements, suppose that we wish to determine the spin of an electron using an appropriate instrument. For the sake of argument, let us assume that the measurement device is a quantum system in its own right, with three eigenstates:
$$
\begin{matrix}
\psi_0&\leftrightarrow&\text{Instrument is idle}\\
\psi_1&\leftrightarrow&\text{Instrument shows }\uparrow\\
\psi_2&\leftrightarrow&\text{Instrument shows }\downarrow
\end{matrix}\tag{3.77}
$$

Since the electron can have two definite states of spin along the $$z$$-axis, we can describe it in terms of two eigenfunctions:
$$
\begin{matrix}
\phi_1&\leftrightarrow&\text{Spin-up}\\
\phi_2&\leftrightarrow&\text{Spin-down}
\end{matrix}\tag{3.78}
$$

If we now decide to treat the measurement process as an interaction between the electron and the apparatus, what will be the outcome? In order to answer this question, let us first consider the simple case when the initial composite state of the system is
$$
\chi_0=\psi_0\otimes\phi_1\tag{3.79}
$$

This corresponds to a situation where the device is idle prior to the interaction, and the electron is in a definite “spin-up” state. During the interaction, the wave function χ(t) evolves according to Schrödinger's equation, ultimately reaching the final state
$$
\chi_1=\psi_1\otimes\phi_1\tag{3.80}
$$

Such a state can obviously be related to the individual subsystems – the meter shows a definite reading $$\uparrow$$, which matches the definite spin-up state of the electron. This is very much what one would expect to see in a classical system.

Things become considerably more interesting, however, when the electron does *not* have a definite spin prior to the interaction. In that case, it is in a state of superposition, which can be described as
$$
\phi=\alpha_1\phi_1+\alpha_2\phi_2\tag{3.81}
$$

What will a measurement produce in this case? The state of the composite system will have the initial form
$$
\chi_0=\psi_0\otimes\left(\alpha_1\phi_1+\alpha_2\phi_2\right)\tag{3.82}
$$

which can be meaningfully associated with subsystem states $$\psi_0$$ and $$phi=α\alpha_1\phi_1+\alpha_2\phi_2$$, respectively. However, once the interaction is complete, the system will evolve into state
$$
\chi_f=\alpha_1(\psi_1\otimes\phi_1)+\alpha_2(\psi_2\otimes\phi_2)\tag{3.83}
$$
State  $$\chi_f$$ is now *entangled*, and can *not* be meaningfully associated with the subsystem states. The electron and the measurement device are in a “joint” state of superposition, in which $$|\alpha_1|^2$$ and $$|\alpha_2|^2$$ represent the probabilities that we will record states $$\chi_1=\psi_1\otimes\phi_1$$ and $$\chi_2=\psi_2\otimes\phi_2$$, respectively, when the wave function $$\chi_f$$ collapses. Then (and only then) can we give an interpretation of the measurement that is consistent with our everyday experience.
