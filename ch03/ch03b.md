## 3.2 Heisenberg's Uncertainty Principle

Heisenberg's Uncertainty Principle is one of the best known results of quantum mechanics. In simple terms, this principle maintains that we cannot simultaneously detect the position and momentum of a quantum particle without an error. The problem that we are dealing with here is not unlike measuring the distance between two cities. If cities were points, this distance could be determined with arbitrary precision. However, since they actually have finite dimensions, it is impossible to reduce the measurement error below a certain threshold.

In order to provide a more formal interpretation of this principle, we must first establish several preliminary results. We begin with the following definition.

### Definition 3.1.
We will say that operators $$\hat{A}$$ and $$\hat{B}$$ *commute* if they satisfy
$$
\hat{A}\hat{B}\psi=\hat{B}\hat{A}\psi\tag{3.35}
$$
for any function $$\psi(x)$$. This property is formally expresssed as
$$
\left[\hat{A},\:\hat{B}\right]\equiv\hat{A}\hat{B}-\hat{B}\hat{A}=0\tag{3.36}
$$

### Proposition 3.1.
Any two operators that commute have a common set of eigenfunctions.
*Proof*.  Suppose that $$\hat{A}$$ and $$\hat{B}$$ commute, and let $$\psi_n$$ be an eigenfunction of $$\hat{B}$$. Then, there exists a number bn such that
$$
\hat{B}\psi_n=b_n\psi_n\tag{3.37}
$$

It is not difficult to show that $$\varphi_n\equiv\hat{A}\psi_n$$ is also an eigenfunction of $$\hat{B}. Indeed, since $$\hat{A}\hat{B}=\hat{B}\hat{A}$$, we have
$$
\begin{align*}
\hat{B}\phi_n&=\hat{B}\hat{A}\psi_n=\hat{A}\hat{B}\psi_n\\
&=b_n\hat{A}\psi_n=b_n\phi_n\tag{3.38}
\end{align*}
$$

Observing that $$\varphi_n$$, and $$\psi_n$$, are eigenfunctions of $$\hat{B}$$ that correspond to the *same* eigenvalue $$b_n$$, it follows that they can differ at most by a constant factor $$\alpha_n$$ (*i.e.* $$\varphi_n=\alpha_n\psi_n$$). Consequently,
$$
\hat{A}\psi_n\equiv\varphi_n=\alpha_n\psi_n\tag{3.39}
$$

which means that $$\psi_n$$ is an eigenfunction of $$\hat{Α}$$ as well

### Remark 3.2.
Since eigenfunctions are associated with observable states __Proposition 3.1__ tells us that we can *simultaneously* measure quantities $$A$$ and $$B$$ whenever the corresponding Operators Commute. It is important to recognize, however, that commutation is not a universal property in quantum mechanics. Operators such as $$\hat{x}$$ and $$\hat{p}$$, for example, satisfy
$$
\left[x,p\right]=i\hbar\tag{3.40}
$$
which means that the states of definite momentum and position are *mutually exclusive*.

### Proposition 3.2
Let us assume that $$\hat{A}$$ is an operator that corresponds to some observable quantity $$A$$. The *expected value* of A (denoted $$\left<A\right>$$), and its *dispersion* $$\Delta{A}$$ can then be expressed as
$$
\left<A\right>=\left<\psi,\hat{A}\psi\right>\tag{3.41}
$$

and
$$
\left<\Delta A\right>^2\equiv\left<A^2\right>-\left<A\right>^2=\left<\psi,\:\left(\Delta\hat{A}\right)^2\psi\right>\tag{3.42}
$$

where operator $$\Delta\hat{A}$$ is defined as
$$
\Delta\hat{A}\equiv\hat{A}-\left<A\right>\tag{3.43}
$$

*Proof*.  We will demonstrate this property for the case when $$\hat{A}$$ has discrete eigenvalues $$\{a_1,\:a_2,\:\cdots\}$$, with corresponding eigenfunctions $$\{\phi_1,\:\phi_2,\:\cdots\}$$ (the proof for the continuous case is similar). We begin by observing that expansion $$(3.12)$$ and property $$(3.8)$$ allow us to write.
$$
\begin{align*}
\left<\psi(x),\hat{A}\psi(x)\right>&=\left<\sum_i\sum_i\alpha_i\phi_i(x),\sum_j\alpha_j\phi_j(x)\right>\\
&=\sum_{i,j}\alpha_i^*\alpha_j\left<\phi_i(x),\phi_j(x)\right>\\
&=\sum_i\left|\alpha_i(\alpha_i)\right|^2
\end{align*}\tag{3.44}
$$
Since $$|\alpha_i(a_i)|^2$$ is the probability of observing $$a_i$$, $$(3.44)$$ can be interpreted as the *expected value* of $$A$$.

Regarding the dispersion, it suffices to recall the definition of operator $$\Delta\hat{A}$$, which implies that
$$
\left(\Delta\hat{A}\right)^2 =\hat{A}^2-2\hat{A}\left<A\right>+\left<A\right>^2\tag{3.45}
$$

From this expression, we directly obtain
$$
\begin{align*}
\left<\psi,\left(\Delta\hat{A}\right)^2\psi\right>&=\left<\psi,\hat{A}^2\psi\right>-2\left<A\right>\left<\psi,\hat{A}\psi\right>+\left<A\right>^2\\
&=\left<A^2\right>-\left<A\right>^2
\end{align*}\tag{3.46}
$$

### Remark 3.3.
Note that the dispersion $$\Delta{A}$$ is in fact the quantum equivalent of the standard deviation. This allows us to interpret $$\Delta{A}$$ as the predicted statistical spread of results when repeated measurement of $$A$$ are made.

Heisenberg’s Principle is usually formulated in terms of the dispersions of the position and momentum, as
$$
\Delta{x}\Delta{p}\geq\frac{\hbar}{2}\tag{3.47}
$$

In order to derive this relationship, let us assume that operators $$\Delta\hat{A}=\hat{A}-\left<A\right>$$ and $$\Delta\hat{B}=\hat{B}-\left<B\right>$$ correspond to the dispersions of some arbitrary quantities $$A$$ and $$B$$. It is not difficult to see that inequality
$$
J(\eta)=\int{\left|\eta\Delta\hat{A}-i\Delta\hat{B}\right|^2dx\geq0}\tag{3.48}
$$

holds for any real number $$\eta$$. Using the fact that $$[\Delta\hat{A},\:\Delta\hat{B}]=[\hat{A},\:\hat{B}]$$, this integral can be expressed as
$$
J(\eta)=\eta^2\int{\psi^*\left(\Delta\hat{A}\right)^2\psi dx}-i\eta\int{\psi^*\left[\hat{A},\hat{B}\right]\psi dx}+\int{\psi^*\left(\Delta\hat{B}\right)^2\psi{d}x}\tag{3.49}
$$

In this special case where $$\hat{A}=\hat{x}$$ and $$\hat{B}=\hat{p}$$, the term $$[\hat{A},\:\hat{B}]$$ in the second integral becomes $$[\hat{A},\:\hat{B}]=[\hat{x},\:\hat{p}]=i\hbar$$. Recalling $$(3.42)$$, $$J(\eta)$$ now takes the form
$$
J(\eta)=\eta^2(\Delta{x})^2+\eta\hbar+\left(\Delta{p}\right)^2\geq0\tag{3.50}
$$

Since this is a quadratic inequality in $$\eta$$, it is easily verified that $$(3.50)$$ is satisfied if and only if $$(3.47)$$ holds.

### Example 3.3.
As an illustration of Heisenberg's Principle, let us consider the case when $$\psi(x)$$ has the form of a wave packet
$$
\psi(x)=\frac{1}{(2\pi)^{1/4}\sqrt{\Delta x}}\exp{\left[\frac{i\left<p\right>x}{\hbar}-\frac{x^2}{4\left(\Delta{x}\right)^2}\right]}\tag{3.51}
$$

where $$\left<p\right>$$ denotes the expected value of the momentum ($$\left<x\right>$$ is assumed to be zero for simplicity). It is easily recognized that in this case
$$
\left|\psi(x)\right|^2=\frac{1}{\sqrt{2\pi}\Delta x}\exp{\left[-\frac{x^2}{2(\Delta{x})^2}\right]}\tag{3.52}
$$

represents a Gaussian distribution, whose standard deviation $$\Delta{x}$$ corresponds to the dispersion of the position. The effect of $$\Delta{x}$$ on the wave function is illustrated in __Figs. 3.1__ and __3.2__, which were obtained for $$\Delta{x}=1$$ and $$\Delta{x}=0.01$$, respectively (with $$\left<p\right>=7\hbar$$ in both cases). __Fig. 3.2__ indicates that when $$\Delta{x}\to0$$ the probability density $$|\psi(x)|^2$$ approaches $$\delta(x)$$, which corresponds to a state of *definite position*.

Using the fact that
$$
\alpha^*(p)=\int{\psi^*(x)\phi(x,\:p)dx}\tag{3.53}
$$

and recalling $$(3.25)$$, we can express the probability density of the momentum as
$$
\left|\alpha(p)\right|^2=A\exp{\left[-\frac{2(\Delta{x})^2(p-\left<p\right>)^2)}{\hbar^2}\right]}\tag{3.54}
$$

where $$A$$ is a constant. This is a Gaussian distribution as well, with a standard deviation
$$
\Delta{p}=\frac{\hbar}{2(\Delta{x})}\tag{3.55}
$$

#### Fig. 3.1. The real part of $$\psi(x)$$ for $$\Delta{x}=1$$.
![fig3-01]()

#### Fig. 3.2. The real part of $$\psi(x)$$ for $$\Delta{x}=0.01$$.
![fig3-02]()

since $$\Delta{p}$$ represents the dispersion of the momentum, it is now easily verified that
$$
\Delta{x}\Delta{p}=\frac{\hbar}{2}\tag{3.56}
$$

which is actually the limiting case of Heisenberg’s result.
### Example 3.4.
What would happen if we were to know the *exact* location of the particle (let us denote this location by $$x_0$$)? For this to be possible, the particle must be in a state of *definite position*, which implies
$$
\psi(x)=\delta(x-x_0)\tag{3.57}
$$

Substituting this into $$(3.53)$$, we obtain
$$
\begin{align*}
\alpha^*(p)&=\int{\delta(x-x_0)\phi(x,p)dx}\\
&=\int{\delta(x-x_0)e^{-ipx/\hbar}dx}\\
&=e^{-ipx_0/\hbar}
\end{align*}\tag{3.58}
$$

Since
$$
\left|\alpha(p)\right|^2=\left|e^{-ipx_0/\hbar}\right|=1\tag{3.59}
$$

it follows that the probability density is *exactly the same* for all $$p$$. In other words, if the *precise* position of the particle is known, its momentum turns out to be *completely uncertain*.

Heisenberg's principle has been viewed by many as a theoretical proof that certain properties of quantum particles are inherently unknowable to us. We should bear in mind, however, that this is not just a matter of our inability to simultaneously observe the exact position and velocity of a particle. What Heisenberg's principle really tells us is that states of definite position and momentum *cannot* coexist. Thus, if we determine the position precisely, there is *no definite momentum to be measured*.

It is also important to recognize that the uncertainty principle is not limited to momentum and position. One of its most important variants can be formulated as
$$
\Delta{E}\Delta{t}\geq\frac{\hbar}{2}\tag{3.60}
$$

here $$\Delta{E}$$ represents the most likely change in energy, and $$\Delta{t}$$ is the time over which this change takes place. Inequality $$(3.60)$$ suggests that over very short periods of time energy can fluctuate dramatically, even to the point of producing a short lived particle-antiparticle pair in empty space (according to special relativity, pure energy can be converted into matter and vice versa). One of the consequences of this fact is that “vacuum” is actually teeming with microscopic activity, and should be thought of as empty only *on the average*. The existence of this microscopic “quantum frenzy” has far reaching implications, and is one of the main obstacles to the development of a consistent theory of quantum gravity.
