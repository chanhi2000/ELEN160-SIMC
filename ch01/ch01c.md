## 1.3 Trademarks of Chaos

In addition to the strange and complicated shape of the attractor, there are a number of other features that are unique to chaotic behavior. In this section, we will focus on the three most prominent ones.

### Νοn-Ρeriodic Behavior
Chaotic trajectories are not periodic, but are bounded for all $$t$$. Several solutions with this property were shown in __Figs. 1.20__, __1.23__ and __1.26__ of the previous section. A natural question that arises in this context is how one can be sure that a trajectory is chaotic and not quasi-periodic (or perhaps periodic with a very long period). A plot of the state variables as a function of time is not particularly reliable in that respect. Instead, it is better to observe the frequency spectrum of the trajectory. In the periodic and quasi-periodic cases the spectrum is necessarily *discrete*, while the chaotic one is *continuous*.

### Sensitivity to Initial Conditions
Perhaps the most important characteristic of chaotic trajectories is their sensitivity to initial conditions. For all ‘normal’ attractors, trajectories that start from similar initial conditions remain close together at all times. The following three examples clearly illustrate this point.

### Example 1.15.
The predator-prey model $$(1.79)$$ is an example of a system in which the attractors are equilibria. In __Fig. 1.29__, we show two trajectories whose initial conditions differ by 2%. It is clear from the graph that the two solutions remain close at all times, and ultimately merge as they approach the equilibrium.

#### Fig. 1.29: Two initially close trajectories for the predatory-prey (the attractor for this system is an equilibrium)
![fig1-29]()

### Example 1.16.
For the van der Pol oscillator $$(1.90)$$, the attractor is a limit cycle. A pair of trajectories whose initial conditions differ by 20% are shown in __Fig. 1.30__. It is readily observed that the difference between the two solutions is small, and becomes negligible in the steady state.

#### Fig. 1.30: Two initially close trajectories for the van der Pol oscillator (the attractor for this system is a limit cycle).
![fig1-30]()

### Example 1.17.
The forced van der Pol oscillator $$(1.111)$$ has a quasi-periodic attractor. In __Fig. 1.31__ we show two of its solutions with initial conditions that differ by 10%. As in the previous examples, the trajectories remain close at all times, although in this case they never become completely indistinguishable.

#### Fig. 1.31: Two initially close trajectories for the forced van der Pol oscillator (this system has a quasi-periodic attractor).
![fig1-31]()

In contrast to __Examples 1.15-1.17__, chaotic solutions exhibit exponential sensitivity with respect to initial conditions. To see this, let us consider two solutions of system $$(1.114)$$, whose initial conditions differ by only 0.01%. The evolution of the two trajectories is shown in __Fig. 1.32__, indicating that after a sufficiently long time there is no resemblance between them. It is important to recognize, however, that this type of system exhibits only eventual unpredictability—the trajectories are actually very similar in the short term.

#### Fig. 1.32. Two initially close trajectories for the double scroll model (this system has a strange attractor).
![fig1-32]()

### Lyapunov Exponents
Suppose that we have two trajectories $$x(t;\:t_0,x_0)$$ and $$\tilde{x}(t;\:t_0,x_0+\delta{x}_0)$$, whose initial conditions differ by some small $$\delta{x}_0$$. In the following, we will be interested in estimating how the difference
$$
\delta{x}(t)=\tilde{x}(t;\:t_0,x_0+\delta{x}_0)-x(t;\:t_0,x_0)\tag{1.117}
$$

evolves over time. Since $$\delta{x}_0$$ is small, we can assume that $$\delta{x}(t)$$ has the general form
$$
\delta{x}(t)=\Phi(t;\:t_0,x_0)\delta{x}_0\tag{1.118}
$$

where $$\Phi(t;\:t_0,x_0)$$ is a time-varying matrix that needs to be determined.  In order to compute this matrix, we should first observe that differentiation of $$(1.118)$$ yields
$$
\delta{\dot{x}}(t)=\dot{\Phi}(t;\:t_0,x_0)\delta{x}_0\tag{1.119}
$$

Furthermore, since
$$
\dot{x}(t)=f(x,t)\delta{1.120}
$$

and
$$
\dot{\tilde{x}}(t)=f(\tilde{x},t)\delta{1.121}
$$

we also know that
$$
\begin{align*}
\delta{\dot{x}}(t)&=f(\tilde{x},t)-f(x,t)\\
&\approx{J}\left(x(t),t\right)\delta{x}(t)
\end{align*}\tag{1.122}
$$

where $$J(x(t),t)$$ is the Jacobian of $$f(x,t)$$ evaluated at $$x(t;\:t_0,x_0)$$. This linearization is appropriate for as long as $$\delta{x}(t)$$ remains small. [^5]

Replacing $$\delta{x}(t)$$ with the expression $$(1.118)$$, we obtain
$$
\delta{\dot{x}}(t)=J\left(x(t),t\right)\Phi(t;t_0,x_0)\delta{x}_0\tag{1.123}
$$

Equating $$(1.119)$$ and $$(1.123)$$ now produces the so-called variational equation
$$
\dot{\Phi}(t;\:t_0,x_0)=J\left(x(t),t\right)\Phi(t;t_0,x_0)\tag{1.124}
$$

Note that the initial condition for this equation is
$$
\Phi(t;t_0,x_0)=I\tag{1.125}
$$

since $$\delta{x}(t_0)=\delta{x}_0$$.

Once $$x(t;\:t_0,x_0)$$ is known, we can compute $$J(x(t), t)$$ and solve $$(1,124)$$ numerically to obtain $$\Phi(t;\:t_0,x_0)$$. The eigenvalues of this matrix (denoted $$m_i(t)$$) are functions of time, and are used to define Lyapunov exponents as
$$
\lambda_i=\lim_{t\to\infty}\frac{1}{t}\ln{\left|m_i(t)\right|}\tag{1.126}
$$

### Remark 1.3. 
In cases when  $$J(x(t),\:t)$$ has eigenvalues in the right half-plane. (which is typical for chaotic behavior), the solution of $$(1.124)$$ can pose serious numerical problems, since $$\Phi(t;\:t_0,x_0)\to\infty$$ when $$t\to\infty$$. As a result, Lyapunov exponents are usually not computed by direct integration.

#### Table 1.3. A characterization of attractors based on Lyapunov exponents.
| ATTRACTOR | LYAPUNOV EXPONENTS |
| :-------: | :----------------: |
| Equilbrium point | $$0>\lambda_1\geq\cdots\geq\lambda_n$$ |
| Limit Cycle | $$\begin{matrix}\lambda_1=0\\0\geq\lambda_2\geq\cdots\geq\lambda_n\end{matrix}$$ | 
| Quasi-Periodic (2 frequencies) | $$\begin{matrix}\lambda_1=\lambda_2=0\\0\geq\lambda_{3}\geq\cdots\geq\lambda_n\end{matrix}$$ |
| Quasi-Periodic ($$k$$ frequencies) | $$\begin{matrix}\lambda_1=\cdots=\lambda_k=0\\0\geq\lambda_{k+1}\geq\cdots\geq\lambda_n\end{matrix}$$ |
| Chaotic | $$\begin{matrix}\lambda_1>0\\\sum_{i=1}^{n}{\lambda_i}<0\end{matrix}$$ |

What is the benefit of Lyapunov exponents? For one thing, they allow us to neatly classify attractors in the manner shown in __Table 1.3__, Lyapunov exponents also provide an intuitive explanation for the sensitivity of chaotic trajectories with respect to initial conditions. Namely, since $$\lambda_1>0$$, equation $$(1,118)$$ implies that any two nearby trajectories will diverge at an average rate of $$e^{\lambda_1t$$. It should be noted, however, that the distance between the trajectories is ultimately bounded by the dimensions of the attractor (which are finite). Since strange attractors typically exhibit spatial folding (see __Fig. 1.21__ for a typical illustration), initially divergent trajectories can in fact get relatively close together after a certain amount of time, only to drift apart again.

### Fractal Dimension
Another unique characteristic of chaotic attractors is related to their dimensionality. Our intuitive understanding of this property is usually Euclidean. We tend to think of a line as 1-dimensional, a surface as 2-dimensional, a volume as 3-dimensional, etc. In this context, dimensionality serves as a measure of the complexity of a geometric object (for example, we can legitimately claim that a surface is more complex than a line).

Since strange attractors are generally very complicated geometrical structures, it would clearly be interesting to establish their dimension. This would enable us to categorize a particular strange attractor as a line, surface, volume, or perhaps none of the above... In order to do this, we first need a definition of dimension which is broader than the traditional Euclidean one, and can be applied to arbitrary sets of points. While there are a number of such definitions, in the following we will focus on one which is known as *capacitive dimension*. 

To understand this concept, imagine that the entire state space is divided into “cubes' with sides of length $$\epsilon$$. If $$N(\epsilon)$$ denotes the number of cubes that it follows that contain points from the set that we are examining, we can introduce the quantity $$C(\epsilon)$$, defined as
$$
C(\epsilon)=\frac{\ln{N(\epsilon)}}{\ln{\tfrac{1}{\epsilon}}}\tag{1.127}
$$

The limit
$$
d_C=\lim_{\epsilon\to0}C(\epsilon)\tag{1.128}
$$

is known as the capacitive dimension of this set. The following three example show that the definition of capacitive dimension is consistent with the Euclidean one.

### Example 1.18. 
Let us begin by considering a single point, since this is the simplest possible geometrical object. As shown in __Fig. 1.33__, a single box is sufficient to cover the point for any choice of $$\epsilon$$. This implies that $$N(\epsilon)=1$$ an therefore $$C(\epsilon)=0$$ as well, which is consistent with the Euclidean dimension.

#### Fig. 1.33. The dimensionality of a point.
![fig1-33]()

### Example 1.19. 
Consider the straight line of length $$L$$, shown in __Fig. 1.34__.

#### Fig. 1.34. The dimensionality of a line.
![fig1-34]()

The number of ‘boxes’ needed to cover this surface is
$$
N(\epsilon)=\frac{L}{\epsilon}\tag{1.129}
$$

and therefore
$$
\begin{align*}
C(\epsilon)&=\frac{\ln{N(\epsilon)}}{\ln{(1/\epsilon)}}\\
&=\frac{\ln{L}}{\ln{1/\epsilon}}+\frac{\ln{(1/\epsilon)}}{\ln{(1/\epsilon)}}\\
&=1+\frac{\ln{L}}{\ln{(1/\epsilon)}}
\end{align*}\tag{1.130}
$$

Since
$$
\begin{matrix}
\ln{(1/\epsilon)}\to\infty&\text{when }\epsilon\to0
\end{matrix}\tag{1.131}
$$

it follows that
$$
d_C=\lim_{\epsilon\to0}C(\epsilon)=1\tag{1.132}
$$

which obviously matches the Euclidean dimension.

### Example 1.20. 
Consider a square surface with sides of length $$L$$.
#### Fig. 1.35. The dimensionality of a square.
![fig1-35]()

The number of boxes needed to cover this surface is
$$
N(\epsilon)=\frac{L^2}{\epsilon^2}\tag{1.133}
$

which means that
$$
\begin{align*}
C(\epsilon)&=\frac{\ln{L^2}}{\ln{1/\epsilon}}+\frac{\ln{(1/\epsilon)^2}}{\ln{(1/\epsilon)}}\\
&=2+\frac{\ln{L^2}}{\ln{(1/\epsilon)}}
\end{align*}\tag{1.134}
$$

and therefore
$$
d_C=\lim_{\epsilon\to0}C(\epsilon)=2\tag{1.135}
$$
Once again we observe consistency with the Euclidean definition.

To see how the definition of capacitive dimension extends to some less conventional sets, let us consider a line of unit length, which we will transform through an infinite sequence of steps. The transformation consists of removing the middle third of each existing segment, until we arrive at a disconnected set of points (when $$n\to\infty$$). This procedure is illustrated in __Fig. 1.36.__, and the resulting set is known as the Cantor set.

#### Fig. 1.36. THe construction of the *Cantor* set.
![fig1-36]()

To figure out the capacitive dimension of the Cantor set, let us observe that we need a single box of size $$\epsilon=1$$ to cover the set in Step 0, 2 boxes of size $$\epsilon=\tfrac{1}{3}$$ to do this in Step 1, 4 boxes of size $$\epsilon=\tfrac{1}{9}$$ Step 2, etc. Obviously, in Step $$n$$, we will need $$2^n$$ boxes of size $$\epsilon=\left(\tfrac{1}{3}\right)^n$$. Since $$\begin{matrix}\epsilon\to0&\text{when }n\to\infty\end{matrix}$$, we have
$$
\begin{align*}
d_C&=\lim_{\epsilon\to0}\left[\frac{\ln{N(\epsilon)}}{\ln{(1/\epsilon)}}\right]\\
&=\lim_{n\to\infty}\left[\frac{\ln{2^n}}{\ln{3^n}}\right]\\
&=0.63
\end{align*}\tag{1.136}
$$
This is a somewhat surprising result, which suggests that there are certain sets with non-integer dimensionality. Sets of this type are known as *fractals*.

How does this apply to strange attractors? well, it turns out that they too are fractals, unlike all other types of attractors (which have integer dimension). In view of that, what would it mean if we established that a single attractor has $$d_C=2.4$$? This  number would indicate that the attractor is more complex than a surface, but less complex than a volume. Apart from dimensionality, fractals have a number of other interesting properties. Perhaps the most striking one is the fact that they possess both a macroscopic and microscopic structure. The ‘pattern’ exhibited by the attractor in the state space is replicated on *all* scales of magnitude.

[^5]: It should be noted that the difference $$\delta{x}(t)$$ starts out as very small, and remains that way for a certain amount of time by virtue of $$(1.118)$$
