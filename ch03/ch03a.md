## 3.1 Quantum Operators

The state of a quantum particle is described by a complex-valued *wave function*, which is usually denoted by $$psi(x,\:t)$$. The evolution of this function over time is governed by Schrödinger's equation
$$
i\hbar\frac{\partial\psi}{\partial t}=\hat{H}\psi\tag{3.1}
$$
where $$\hat{H}$$ represents a linear operator, and $$\hbar$$ is Planck's constant divided by $$2\pi$$. For a single particle of mass $$m$$ in an external field $$V(x,\:y,\:z)$$, $$\hat{H}$$ has the form
$$
\hat{H}=-\frac{\hbar^2}{2m}\nabla^2+V(x,\:y,\:z)\tag{3.2}
$$

where
$$
\nabla^2=\frac{\partial^2}{\partial{x}^2}+\frac{\partial^2}{\partial{y}^2}+\frac{\partial^2}{\partial{z}^2}\tag{3.3}
$$

There is an interesting connection between operator H and the total energy of a classical particle. In the classical case, the sum of the kinetic and potential energy can be expressed as
$$
E=\frac{1}{2}m(v_x^2+v_y^2+v_z^2)+V(x,y,z)\tag{3.4}
$$

or equivalently (in terms of momentum) as
$$
E=\frac{1}{2m}(p_x^2+p_y^2+p_z^2)+V(x,y,z)\tag{3.5}
$$
If the momentum components in $$(3.5)$$ are now substituted by *operators*
$$
\begin{matrix}
\hat{p}_x=i\hbar\frac{\partial}{\partial{x}};&
\hat{p}_y=i\hbar\frac{\partial}{\partial{y}};&
\hat{p}_z=i\hbar\frac{\partial}{\partial{z}};
\end{matrix}\tag{3.6}
$$

we obtain
$$
\frac{1}{2m}\left(\hat{p}_x^2+\hat{p}_y^2+\hat{p}_z^2\right)=-\frac{\hbar}{2m}\nabla^2\tag{3.7}
$$

In other words, replacing $$p_x$$, $$p_y$$, and $$p_z$$, in $$(3.5)$$ with their operator counterparts directly produces $$\hat{H}$$.

What does the wave function $$\psi(x,\:t)$$ actually tell us? That depends to some tent on what it is that we want to measure. Suppose, for example, that we are interested in an observable quantity $$q$$. With any such quantity, we can associate an operator $$\hat{Q}$$, much like we did with the momentum operator in $$(3.6)$$. If we consider only stationary states, the eigenfunctions[^1] of $$\hat{Q}$$ will depend on $$x$$ only, satisfying
$$
\hat{Q}\phi_i(x)=q_i\phi_i(x)\tag{3.8}
$$

In equation $$(3.8)$$, real numbers $$q_i\:(i=1,\:2,\:\cdots)$$ represent the *eigenvalues* that correspond to functions $$\phi_i(x)\:(i=1,\:2,\:\cdots)$$. The quantum mechanical interpretation of this equation is that the particle is in a *definite* state of $$q$$ only when $$\psi(x)\in\{\phi_1(x),\:\phi_2(x),\:\cdots\}$$. In other words, if $$\psi(x)=\phi_i(x)$$, a measurement will certainly produce $$q=q_i$$.

What can we say about quantum states that do not correspond to eigenfunctions? Before answering this question, we should first note that operator $$\hat{Q}$$ is always chosen so that it satisfies the following three properties:
- __Property 1.__ All eigenvalues of $$\hat{Q}$$ must be *real numbers*. This is important because it allows us to identify measurable physical quantities with eigenvalues.
- __Property 2.__ The eigenfunctions of $$\hat{Q}$$ form a basis in the function space. This means that any function $$f(x)$$ can be expressed in terms of $$\{\phi_1(x),\:\phi_2(x),\:\cdots\}$$ as
$$
f(x)=\sum_i\beta_i\phi_i(x)\tag{3.9}
$$
where $$\beta_i\:(i=1,\:2,\:\cdots)$$ are constant coefficients.
- __Property 3.__ The *scalar product*[^2] of two eigenfunctions, which is defined as
$$
\left<\phi_i(x),\:\phi_j(x)\right>=\int{\phi_i^*(\rho)\phi_j(\rho)d\rho}\tag{3.10}
$$
satisfies
$$
\left<\phi_i(x),\:\phi_j(x)\right>=\begin{cases}1,&i=j\\0,&i\neq j\end{cases}\tag{3.11}
$$
When this property holds, the basis $$\{\phi_1(x),\:\phi_2(x),\:\cdots\}$$ is said to be *orthonormal*.

The existence of an orthonormal basis for $$\hat{Q}$$ allows us to express the wave function $$\psi(x)$$ as
$$
\psi(x)=\sum_i\alpha_i(q_i)\phi_i(x)\tag{3.12}
$$

In such a case, the particle is not in any definite state of $$q$$, but is rather a *superposition* of all observable states. What this means is that a measurement could produce *any* of the possible values for $$q$$, but we cannot tell in advance which one. What we do know, however, is the probability of measuring a particular value $$q_i$$. THis probability is directly related to the coefficients $$\alpha_i(q_i)$$, and can be expressed as
$$
P(q_i)=\left|\alpha_i(q_i)\right|^2\tag{3.13}
$$

To see how $$P(q_i)$$ can be computed, we could recall that the scalar product defined in $$(3.10)$$ satisfies[^3]
$$
\left<\sum_i\alpha_if_i(x),\:g(x)\right>=\sum_i\alpha_i^*\left<f_i(x),\:g(x)\right>\tag{3.14}
$$

where $$f_i(x)$$ and $$g(x)$$ are arbitrary complex-valued functions. We can then use $$(3.11)$$ and $$(3.12)$$ to obtain
$$
\left<\psi(x),\:\phi_i(x)\right>=\sum_j\alpha_j^*(q_j)\left<\phi_j(x),\:\phi_i(x)\right>=\alpha_i^*(q_i)\tag{3.15}
$$

which allows us to express the probability as
$$
P(q_i)=\left|\alpha_i(q_i)\right|^2=\left|\left<\psi(x),\:\phi_i(x)\right>\right|^2\tag{3.16}
$$

### Remark 3.1
In order to treat the terms $$|\alpha_i(q_i)|^2$$ as probabilities, we must ensure that
$$
\sum_i\left|\alpha_i(q_i)\right|^2=1\tag{3.17}
$$

We can do this by using *normalized* wave functions, which must satisfy the constraint $$<\psi(x),\:\psi(y)>=1$$. To see why this is so, it suffices to observe that
$$
\begin{align*}
\left<\psi(x),\:\psi(x)\right>&=\left<\sum_i\alpha_i\phi_i(x),\sum_j\alpha_j\phi_j(x) \right>\\
&=\sum_{i,\:j}\alpha_i^*\alpha_j\left<\phi_i(x),\:\phi_j(x)\right>\\
&=\sum_i\left|\alpha_i(q_i)\right|^2
\end{align*}\tag{3.18}
$$

What happens when we perform an actual measurement? In that case, the wave function *collapses* into exactly one of the eigenfunctions $$\phi_i(x)$$, and automatically moves moves into a state that corresponds to eigenvalue $$q_i$$. It is important to recognize that all subsequent measurements will produce the same result. Indeed, since the system is in state $$\psi(x)=\phi_i(x)$$ after the initial measurement, the probability of detecting some $$q_j\neq{q}_i$$ is
$$
P(q_j)=\left|\left<\phi_i(x),\:\phi_j(x)\right>\right|^2=0\tag{3.19}
$$

Without this property (which follows from the orthogonality condition $$(3.11)$$), our predictions about quantum phenomena would be completely unreliable.

### The Continuous Spectrum
In the preceding discussion, we assumed that operator $$\hat{Q}$$ has a *discrete* set of eigenfunctions and eigenvalues. But what happens if the possible outcomes represent a *continuum*? In such cases, the expansion $$(3.12)$$ turns into an integral
$$
\psi(x)=\int{\alpha(q)\phi(x,\:q)dq}\tag{3.20}
$$

much like Fourier series turn into Fourier transforms when the function is ареriodic. The quantity $$|\alpha(q)|^2$$ can be interpreted as the *probability density*, where
$$
dP=\left|\alpha(q)\right|^2dq\tag{3.21}
$$

represents the infinitesimal probability that the outcome will fall in the interval $$[p,\:p+dp]$$. It is not difficult to show that
$$
\alpha^*(q)=\left<\psi(x),\:\phi(x,q)\right>=\int{\psi^*(x)\phi(x,\:q)dx}\tag{3.22}
$$

which is a continuous version of expression $$(3.15)$$.

### Example 3.1.
In the one-dimensional case, the quantum *momentum operator* takes the form
$$
\hat{p}=i\hbar\frac{\partial}{\partial{x}}\tag{3.23}
$$

States of definite momentum correspond to the eigenfunctions $$\phi(x,\:p)$$ of this operator, which must satisfy
$$
i\hbar\frac{\partial\phi(x,\:p)}{\partial{x}}=p\phi(x,\:p)\tag{3.24}
$$

It is easily verified that functions of the form
$$
\phi(x,\:p)=e^{-ipx/\hbar}\tag{3.25}
$$

are solutions of $$(3.24)$$ for any choice of $$p$$, This indicates that the momentum operator has a *continuous* set of eigenvalues.[^4]

Following $$(3.20)$$, we can express the quantum state $$\psi(x)$$ in terms of momentum components as
$$
\psi(x)=\int{\alpha(p)\phi(x,\:p)dp}=\int{\alpha(p)e^{-ipx/\hbar}dp}\tag{3.26}
$$

As noted earlier, in such a representation $$|\alpha(q)|^2dp$$ corresponds to the probability that the measurement will produce a momentum value in the interval $$[p,\:p+dp]$$.

### Example 3.2.
The one-dimensional *position operator* is simply a multiplication by $$x$$, whose eigenfunctions must satisfy.
$$
\hat{X}\varphi(x,\:\rho)=x\varphi(x,\:\rho)=\rho\varphi(x,\:\rho)\tag{3.27}
$$

In $$(3.27)$$, $$\varphi(x,\:\rho)$$ represents a state of definite position, in which $$x=\rho$$. It is not difficult to verify that $$\varphi(x,\:\rho)=\delta(x-\rho)$$, since Dirac's delta function has the property
$$
(x-\rho)\delta(x-\rho)=0\tag{3.28}
$$

With that in mind, we can express $$\psi(x)$$ in terms of states with definite position as
$$
\psi(x)=\int{\alpha(\rho)\delta(x-\rho)d\rho}\tag{3.29}
$$

where $$|\alpha(\rho)|^2$$ represents the probability density for measuring $$x=\rho$$.

This result has an interesting interpretation if we recall that Dirac's delta functions satisfies
$$
\int{\alpha(\rho)\delta(x-\rho)d\rho}=\alpha(x)\tag{3.30}
$$

by definition. Comparing $$(3.29)$$ and $$(3.30)$$, it follows that $$\psi(x)=\alpha(x)$$, which allows us to view $$|\psi(x)|^2$$ as the probability density that a measurement will find the particle in position $$x$$.

In cases when a continuum of outcomes is possible, the probability of observing a particular value $$q\in[q_0,\:q_0+dq]$$ is an infinitely small number. As a result, it often makes more sense to ask whether quantity $$q$$ falls in a certain interval $$W=[q_a,\:q_b]$$. In order to make such an evaluation, we can rewrite $$(3.20)$$ as
$$
\begin{align*}
\psi(x)&=\int_{q\in W}{\alpha(q)\phi(x,q)dq}+\int_{q\notin W}{\alpha(q)\phi(x,q)dq}\\
&=\psi_A(x)+\psi_B(x)
\end{align*}\tag{3.31}
$$

It is important to note that although functions $$\psi_A(x)$$ and $$\psi_B(x)$$ are guaranteed to be orthogonal (that is, $$\left<\psi_Α(x),\:\psi_B(x)\right>=0$$), they are *not normalized*. Indeed, since
$$
\begin{align*}
\left<\psi(x),\psi(y)\right>&=\left<\psi_A(x)+\psi_B(x),\psi_A(x)+\psi_B(x)\right>\\
&=\left<\psi_A(x)+\psi_B(x)\right>+\left<\psi_A(x)+\psi_B(x)\right>=1
\end{align*}\tag{3.32}
$$

we have that $$\left<\psi_Α(x),\:\psi_A(x)\right>=a^2$$ and $$\left<\psi_B(x),\:\psi_B(x)\right>=b^2$$, with $$a^2+b^2=1$$. We can eliminate this problem by normalizing $$\psi_A(x)$$ and $$\psi_B(x)$$ as
$$
\begin{matrix}
\bar{\psi}_A(x)=\frac{1}{a}\psi_A(x);&&
\bar{\psi}_B(x)=\frac{1}{b}\psi_B(x)
\end{matrix}\tag{3.33}
$$

and rewriting $$\psi(x)$$ as
$$
\psi(x)=a\alpha\bar{\psi}_A(x)+b\bar{\psi}_B(x)\tag{3.34}
$$
In this representation, $$a^2$$ is the probability that $$\psi(x)$$ will collapse into state $$\bar{\psi}_A(x)$$, which corresponds to $$q_a\leq{q}\leq{q}_b$$. Note that $$\bar{\psi}_A(x)$$ is *not* a stat with a definite value of $$q$$, but rather corresponds to a *fixed range* of possible values.
