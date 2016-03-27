## 1.2 Nonlinear Systems

A nonlinear dynamic system is generally described by a set of first order differential equations
$$
\dot{x}=f(x,t)\tag{1.62}
$$

where $$f(x,t)$$ is a vector-valued nonlinear function. Models of this type arise in a wide variety of applications, ranging from engineering to economics and ecology. From a theoretical standpoint, it is important to distinguish between *autonomous* and *non-autonomous* dynamical systems.  An example of a non-autonomous system would be
$$
\begin{align*}
\dot{x}_1&=-x_1+2x_1x_2+x_2^2\\
\dot{x}_2&=x_1+x_2+x_1^2x_2+2\cos{(3t)}
\end{align*}\tag{1.63}
$$

where time shows up *explicitly* through the cosine term. In such cases it is appropriate to use the general description $$(1.62)$$, since $$f$$ is a function of both $$x$$ and $$t$$. In contrast, an autonomous system has no explicit time dependency, and can be described simply as
$$
\dot{x}=f(x)\tag{1.64}
$$

The second order system
$$
\begin{align*}
\dot{x}_1&=x_1-x_2^2\\
\dot{x}_2&=x_1\sin{(x_{2})}-x_2
\end{align*}\tag{1.65}
$$

is a typical example.

To see how nonlinear systems differ from their linear counterparts, let us consider a simple scalar system
$$
\dot{x}=x^{2}+2x\tag{1.66}
$$

with a quadratic nonlinearity. The first thing that we notice about it is that it has *multiple equilibria*, corresponding to $$x^e=0$$ and $$x^e=-2$$. This is quite unlike linear systems, where the coordinate origin was always the unique equilibrium, regardless of the size of the model (assuming, of course, that matrix $$A$$ is nonsingular). In dealing with multiple equilibria, two questions arise naturally:
1. How can we compute all the equilibria of a general dynamic system?
2. Is it possible to determine whether a particular equilibrium is an attractor or a repeller?

In the following, we will address these issues in some detail.

### *Computation of Equilibria*
The system equilibria can be viewed as solutions of the algebraic equation
$$
f(x)=0\tag{1.67}
$$

Computing the solutions of $$(1.67)$$ can be a very difficult task in general, and there are no guarantees that all of them will be found. One of the most effective solution techniques for nonlinear equations is the so-called Newton iterative method. The following simple example illustrates the basic ideas of this approach

### Example 1.6.
Consider the scalar equation
$$
f(x)=x^2+4x+3=0\tag{1.68}
$$

which we propose to solve iteratively. In order to do that, we will form the following sequence
$$
x(k+1)=x(k)-\left|f'(x(k))\right|^{-1}f(x(k))\tag{1.69}
$$

##### Table 1.1. Iterative sequences for two different initial guesses.
| $$x(0)=0$$ | $$x(0)-5$$ |
| :--------: | :--------: |
| $$x(1)=-0.7500$$ | $$x(1)=-3.6700$$ |
| $$x(2)=-0.9750$$ | $$x(2)=-3.1330$$ |
| $$x(3)=-0.9969$$ | $$x(3)=-3.0078$$ |
| $$x(4)=-0.9999$$ | $$x(1)=-3.0000$$ |

##### Fig. 1.3. An illustration of Newton's method.
![fig1-03]()

starting from some initial guess $$x(0)$$. Two possible scenarios are shown in __Table 1.1__, suggesting that different choices of $$x(0)$$ can lead to very different solutions.

Before extending Newton's method to larger systems, it is useful to consider its geometric interpretation in the scalar case. To that effect, in __Fig. 1.3__ we show the plot of function $$(1.68)$$ in a region that contains the solution $$x^*=-1$$.

The point labeled $$x(1)$$ represents the intersection of slope $$f'(x(0))$$ with the x-axis. As a result, we can write
$$
f('x(0))=\frac{f(x(0))}{x(0)-x(1)}\tag{1.70}
$$

which directly impliess
$$
x(1)=x(0)-\left|f'(x(k))\right|^{-1}f(x(0))\tag{1.71}
$$

Equation $$(1.71)$$ allows us to conclude that point $$x(1)$$ on the graph corresponds to the first iterate obtaining using Newton's method. It is not difficult to see $$x(2)$$, $$x(3)$$, etc. have the same interpretation, and that this sequence converges to $$x^*=-1$$.

In the multivariable case, Newton's method takes the form
$$
x(k+1)=x(k)-\left|J(x(k))\right|^{-1}f(x(k))\tag{1.72}
$$

where
$$
f(x)=\left[\begin{matrix}f_1(x_1,x_2,\cdots,x_n)\\\vdots\\f_n(x_1,x_2,\cdots,x_n)\end{matrix}\right]\tag{1.73}
$$

is a vector-valued nonlinear function, and
$$
\begin{align*}
J(x)=\left[\begin{matrix}\tfrac{\partial{f}_1}{\partial{x}_1}&\cdots&\tfrac{\partial{f}_1}{\partial x_n}\\\vdots&\ddots&\vdots\\\tfrac{\partial{f}_n}{\partial x_1}&\cdots&\tfrac{\partial{f}_n}{\partial x_n}\end{matrix}\right]
\end{align*}\tag{1.74}
$$

represents its Jacobian. The following example illustrates how the iterative process works in this case.

### Example 1.7.
Consider the pair of nonlinear equations
$$
f(x)-\left[\begin{matrix}3x_1x_2-x_2^{-2}-e^{x_1}\\x_1^2x_2-\cos{(x_1)}-x_2\end{matrix}\right]=0\tag{1.75}
$$

whose solutions we wish to compute. It is easily verified that the Jacobian of this system has the form
$$
\begin{align*}
J(x)=\left[\begin{matrix}3x_2-e^{x_1}&3x_1+2x_2^{-3}\\2x_1x_2+\sin{(x_1)}&x_1^2-1\end{matrix}\right]
\end{align*}\tag{1.76}
$$

In __Table 1.2__, we show Newton's iterates for two different initial guesses.

#### Table 1.2. Iterative sequences for two different initial guesses.
| x | x |
| :---: | :---: |
| $$x(0)=\left[\begin{matrix}1&1\end{matrix}\right]$$ | $$x(0)=\left[\begin{matrix}-1&-1\end{matrix}\right]$$ |
| $$x(1)=\left[\begin{matrix}1.1901&1.1329\end{matrix}\right]$$ | $$x(1)=\left[\begin{matrix}-0.5336&-0.9877\end{matrix}\right]$$ |
| $$x(2)=\left[\begin{matrix}1.1619&1.1379\end{matrix}\right]$$ | $$x(2)=\left[\begin{matrix}-0.4134&–1.1120\end{matrix}\right]$$ |
| $$x(3)=\left[\begin{matrix}1.1617&1.1383\end{matrix}\right]$$ | $$x(3)=\left[\begin{matrix}-0.4330&-1.1167\end{matrix}\right]$$ |
| $$x(4)=\left[\begin{matrix}1.1617&1.1383\end{matrix}\right]$$ | $$x(4)=\left[\begin{matrix}-0.4328&-1.1170\end{matrix}\right]$$ |

As in __Example 1.6__, it is apparent that different initial guesses produce different solutions of $$(1.75)$$.  In this case, however, it is very difficult to tell whether additional solutions exist (and what initial guesses would lead to them).  The same can be said for a broad class of similar problems where analytical solutions are not available.

### Remark 1.2.
In general, there is no guarantee that Newton's method will converge. Whether or not that will happen depends to a large extent on the choice of initial approximation.  This can be a major problem, particularly when the system is large.

### *Stability*
A simple way to determine whether a given equilibrium $$x^e$$ is attractive or not is to linearize the system using the Taylor series expansion. For the system shown in $$(1.66)$$, linearization around $$x^e=0$$ yields
$$
\dot{x}=2x\tag{1.77}
$$

which indicates that this equilibrium is a *repeller*. Similarly, linearization around $$x^e=-2$$ yields
$$
\dot{y}=-2y\tag{1.78}
$$

where $$y=x-x^e$$. This implies that $$x^e=-2$$ is an *attractor*

It is important to recognize that linearization provides only *local* information about an equilibrium. As a result, we can claim that the trajectories originating close to $$x^e=-2$$ will be attracted by this equilibrium, but we can really say anything about other solutions of the system. This is another fundamental difference with respect to linear system, where an asymptotically stable equilibrium was a *global attractor*.

To further illustrate the local properties of equilibria, let us consider the systems
$$
\begin{align*}
\dot{x}_1&=-3x_{1}+4x_{1}^2-0.5x_1x_2-x_1^3\\
\dot{x}_2&=-2.1x_2+x_1x_2
\end{align*}\tag{1.79}
$$

which represents a variant of the classical predator-prey model in ecology ($$x_1$$ and $$x_2$$ are the populations of the prey and predator, respectively)

##### *A. The Equilibria*
Our first step will be to determine the equilibria of this system, which implies solving the following pair of equations
$$
\begin{aligned}
-3x_{1}+4x_{1}^2-0.5x_1x_2-x_1^3&=0\\
-2.1x_2+x_1x_2&=0
\end{aligned}\tag{1.80}
$$

In a typical nonlinear system we would have to do this numerically, with no guarantee of finding all possible solutions. In this case, however, the problem can be solved analytically, by observing that condition
$$
x_2(x_1-2.1)=0\tag{1.81}
$$

allows for two possible cases:

- **CASE 1.** $$x_2\neq0$$, which implies that $$x_1=2.1$$ and $$x_2=1.98$$ is the unique solution
- **CASE 2.** $$x_2=0$$, which implies that $$x_1$$ can be determined by solving equation
$$
-3x_1+4x_1^2-x_1^3=0\tag{1.82}
$$

This is a simple third order polynomial with roots $$0$$, $$1$$, and $$3$$.
Based on the above analysis, we can conclude that the predator-prey model has *exactly* four equilibria
$$
\begin{matrix}
x^{e}=\left[\begin{matrix}0\\0\end{matrix}\right];&
x^e=\left[\begin{matrix}1\\0\end{matrix}\right];\\
x^e=\left[\begin{matrix}3\\0\end{matrix}\right];&
x^e=\left[\begin{matrix}2.10\\1.98\end{matrix}\right];
\end{matrix}\tag{1.83}
$$


##### *B. stability*
Turning now to the question of stability, we first need to linearize the system around each equilibrium. The Jacobian of $$(1.80)$$ has the general form
$$
\begin{align*}
J(x)=\left[\begin{matrix}(-3+8x_1-0.5x_2-3x_1^2)&-0.5x_1\\x_2&-2.1+x_1\end{matrix}\right]
\end{align*}\tag{1.84}
$$

which leads to the following scenarios:
**(i)** For $$x^e=\left[\begin{matrix}0&0\end{matrix}\right]^T$$, we have
$$
J(x^e)=\left[\begin{matrix}-3&0\\0&-2.1\end{matrix}\right]\tag{1.85}
$$

The linearized system is therefore
$$
\dot{y}=J(x^e)y\tag{1.86}
$$

where $$y=x-x^e$$. Since this is now a system of the form $$(1.15)$$, its stability properties can be determined by checking the eigenvalues. In this case, $$\lambda_1=-3$$ and $$\lambda_2=-2.1$$, indicating that $$x^e=\left[\begin{matrix}0&0\end{matrix}\right]^T$$ is a *stable* equilibrium.

**(ii)** For $$x^e=\left[\begin{matrix}1&0\end{matrix}\right]^T$$, we have
$$
J(x^e)=\left[\begin{matrix}2&-0.5\\0&-1.1\end{matrix}\right]\tag{1.87}
$$

and the eigenvalues of the linearized system are $$\lambda_1=2$$ and $$\lambda_2=-1.1$$. This indicates that $$x^e=\left[\begin{matrix}1&0\end{matrix}\right]^T$$ is an *unstable* equilibrium.

**(iii)** For $$x^e=\left[\begin{matrix}3&0\end{matrix}\right]^T$$, we have
$$
J(x^e)=\left[\begin{matrix}-6&-1.5\\0&0.9\end{matrix}\right]\tag{1.88}
$$

and the eigenvalues of the linearized system are $$\lambda_1=-6$$ and $$\lambda_2=-0.9$$. This indicates that $$x^e=\left[\begin{matrix}3&0\end{matrix}\right]^T$$ is an *unstable* equilibrium.

**(iv)** For $$x^e=\left[\begin{matrix}2.1&1.98\end{matrix}\right]^T$$, we have
$$
J(x^e)=\left[\begin{matrix}-0.42&-1.05\\1.98&0\end{matrix}\right]\tag{1.89}
$$

and the eigenvalues of the linearized system are $$\lambda_{1,2}=-0.21\pm{j}1.43$$. This indicates that $$x^e=\left[\begin{matrix}2.1&1.98\end{matrix}\right]^T$$ is a *stable* equilibrium.

At this point, we know that two of the four equilibria are locally attractive. However, we still don't know what happens to solutions that don’t originate in the immediate neighborhood of these equilibria. This is actually a very hard question to answer analytically, even for relatively simple systems. One way to approach the problem is to perform multiple simulations, and then plot each trajectory in the $$x_1$$-$$x_2$$ plane. A collection of these trajectories referred to as the *phase portrait* of the system, and is shown in __Fig. 1.4__ (the Solid dots indicate the initial conditions).

#### Fig. 1.4. Regions of attraction for different equilibria.
![fig1-04]()

__Fig. 1.4__ suggests that there are entire regions in the phase space from which solutions are attracted to particular equilibria. Such regions are known as regions of attraction. In this context we should note that there may also be regions from which solutions are not attracted to any of the equilibria (an example of such a region is the lower right-hand quadrant of __Fig. 1.4__).

### *Types of Attractors in Nonlinear Systems*
In all the examples that we considered so far, the trajectories were attracted to (or repelled by) the system equilibria. It turns out, however, that nonlinear systems trajectories can also be attracted by other objects in the phase space. In the following, we will identify three such objects, in increasing degree of complexity.

#### *Limit Cycles*
Let us consider the following system (also known as the van der Pol oscillator)
$$
\begin{align*}
\dot{x}_1&=x_2\\
\dot{x}_2&=(1-x_1^2)x_2-x_1
\end{align*}\tag{1.90}
$$

which has a unique equilibrium at the origin. Observing that the Jacobian has the form
$$
J(x)=\left[\begin{matrix}0&1\\-(2x_1x_2+1)&1-x_1^2\end{matrix}\right]\tag{1.91}
$$

it follows that
$$
J(x^e)=\left[\begin{matrix}0&1\\-1&1\end{matrix}\right]\tag{1.92}
$$

with eigenvalues $$\lambda_{1,2}=0.5\pm{j}0.866$$. This indicates that $$x^e=\left[\begin{matrix}0&0\end{matrix}\right]^T$$ is a *repeller*, and that solutions originating in the neighborhood of this point diverge from it. It is important to recall, however, that this linearization is valid only near the origin, so we can’t tell what happens to these solutions as $$t\to\infty$$, The easiest way to evaluate the long term behavior of the trajectories is to numerically solve the differential equation for several different initial conditions (some near the equilibrium, and some further away). The typical responses for $$x_1(t)$$ and $$x_2(t)$$ are shown in __Figs. 1.5__ and __1.6__, indicating that solutions seem to settle into a periodic steady state as $$t\to\infty$$. Such a trajectory is referred to as a *limit cycle*, and it represents a legitimate attractor for this system.

#### Fig. 1.5. Evolution of state $$x_1$$.
![fig1-05]()

#### Fig. 1.6. Evolution of state $$x_2$$.
![fig1-06]()

To see the attractive nature of the limit cycle more clearly, in __Fig. 1.7__ we provide a phase portrait of the system (making sure that the simulation time was long enough to allow solutions to reach their steady state). This portrait indicates that the limit cycle is represented by a closed curve in the phase space, and that all of our trajectories are attracted to it.

#### Fig. 1.7. The limit cycle in the phase space.
![fig1-07]()

#### *Quasi-Periodic Attractors*
Before we begin our discussion of quasi-periodic attractors, it is first necessary to define what we mean by quasi-periodic behavior. The simplest example would be the function
$$
f(t)=\cos{\omega_1t}+\cos{\omega_2t}\tag{1.93}
$$

which is a sum of two sinusoids with different frequencies. Is such a function periodic? Well, that depends... The necessary condition for periodicity is that
$$
f(t+T)=f(t)\tag{1.94}
$$

holds for some $$T$$. It is easily verified that this will be the case when
$$
\begin{align*}
\omega_1T&=2p\pi\\
\omega_2T&=2q\pi
\end{align*}\tag{1.95}
$$


For some integers $$p$$ and $$q$$, or equivalently if
$$
\frac{\omega_1}{\omega_2}=\frac{p}{q}\tag{1.96}
$$

When $$(1.96)$$ holds, we say that frequencies $$\omega_1$$ and $$\omega_2$$ are *commensurate*, and $$f(t)$$ is periodic with
$$
\omega_{eq}=\frac{2\pi}{T}=\frac{\omega_1}{p}=\frac{\omega_2}{q}\tag{1.97}
$$

This scenario is often referred as frequency locking, since $$ω_\text{eq}$$ ‘locks’ onto some fraction of the original frequencies  $$\omega_1$$ and $$\omega_2$$.
What happens if  $$\omega_1$$ and $$\omega_2$$ are not commensurate (for instance, when  $$\omega_1=\sqrt{3}\omega_2$$)? In that case, $$f(t)$$ is clearly not periodic, but it can nevertheless be represented as a sum of two independent periodic functions. Since $$f(t)$$ still exhibits some regularity in its behavior, we say that it is *quasi-periodic*.

The following simple example provides an illustration of both frequency locking and quasi-periodic behavior in a physical system.

### Example 1.8.
The circuit in __Fig. 1.8__ is driven by a sinusoidal source of the form $$v_g(t)=\cos{(\omega_0t)}$$. Since this is a linear system, its response can be obtained analytically using Laplace transforms. After some algebra, the expressions for the capacitor voltage and the inductor current are found to be
$$
\begin{align*}
x_1(t)&=v_C(t)\\
&=\frac{\omega_C^2}{\omega_C^2-\omega_0^2}\left[\cos{\omega_0t}-\cos{\omega_Ct}\right]
\end{align*}\tag{1.98}
$$

#### Fig. 1.8. An LC circuit.
![fig1-08]()

and
$$
\begin{align*}
x_x(t)&=i_L(t)\\
&=\frac{1}{L\left(\omega_C^2-\omega_0^2\right)}\left[\omega_C\sin{\omega_Ct}-\omega_0\sin{\omega_0t}\right]
\end{align*}\tag{1.99}
$$

where
$$
\omega_C=\frac{1}{\sqrt{LC}}\tag{1.100}
$$

From $$(1.98)$$ and $$(1.99)$$ it is clear that the dynamics of this system involves two different frequencies, $$\omega_0$$ and $$\omega_C$$. Depending on how $$\omega_0$$, $$L$$ and $$C$$ are chosen, the following scenarios can arise.
- **CASE 1.** For $$L=1$$, $$C=1$$ and $$\omega_0=1.5$$ we have
$$
\frac{\omega_0}{\omega_C}=\frac{3}{2}\tag{1.101}
$$

which means that the frequencies are commensurate. As a result, $$x_1(t)$$ and $$x_2(t)$$ have the periodic form shown in __Fig. 1.9__ and __1.10__. The attractor for this system is the closed curve shown in __Fig. 1.11__.

#### Fig. 1.9. Evolution of state $$x_1$$.
![fig1-09]()

#### Fig. 1.10. Evolution of state $$x_2$$.
![fig1-10]()

#### Fig. 1.11. The attractor.
![fig1-11]()

- **CASE 2.** For $$L=2$$, $$C=1$$ and $$\omega_0=1.5$$ the ratio
$$
\frac{\omega_0}{\omega_C}=\frac{3\sqrt{2}}{2}\tag{1.102}
$$

is *not* a rational number. In this case, states $$x_1(t)$$ and $$x_2(t)$$ exhibit quasi-periodic behavior, as indicated in __Figs. 1.12__ and __1.13__. The attractor is now the rather complicated set shown in __Fig. 1.14__.

#### Fig. 1.12. Evolution of state $$x_1$$.
![fig1-12]()

#### Fig. 1.13. Evolution of state $$x_2$$.
![fig1-13]()

#### Fig. 1.14. The attractor.
![fig1-14]()

### Example 1.9.
Let us now consider a slightly more general scenario, where $$f(t)$$ is a product of two sinusoids
$$
f(t)=\cos{\omega_1t}\cdot\cos{\omega_2t}\tag{1.103}
$$

As in __Example 1.8__, $$f(t)$$ will be periodic when condition $$(1.96)$$ holds. It is also easily verified that $$f(t)$$ is quasi-periodic when wand we are incommensurate, since
$$
f(t)=\frac{1}{2}\cos{\left[\left(\omega_1-\omega_2\right)t\right]}+\frac{1}{2}\cos{\left[\left(\omega_1+\omega_2\right)t\right]}\tag{1.104}
$$

Before proceeding to more general cases, we need to observe that the solutions of nonlinear differential equations are rarely available in analytic form, and are usually obtained numerically. This raises the following question: If we only have a plot of $$f(t)$$, how can we tell whether it is quasi-periodic? One way to do this is based on the fact that a quasi-periodic function can always be expressed as
$$
f(t)=\sum_{i=1}^{N}h_i(t)\tag{1.105}
$$

where $$h_i(t)$$ are independent periodic functions with frequencies $$\omega_i\:(i=1,\:2\:,\cdots,\:N)$$. The Fourier spectrum of such a function is always *discrete*, as opposed to an arbitrary aperiodic function which has a continuous spectrum.

#### Example 1.10
Let us now consider a further generalization, in which $$f(t)$$ is given as
$$
f(t)=a(t)\cdot{b}(t)\tag{1.106}
$$

Functions $$a(t)$$ and $$b(t)$$ are assumed to be periodic (but not sinusoidal), with frequencies $$\omega_1$$ and $$\omega_2$$, respectively. In this case, we can perform our analysis by expanding $$a(t)$$ and $$b(t)$$ in terms of their Fourier series as
$$
a(t)=\sum_{n=0}^{\infty}{A_n\cos{(n\omega_1t)}}\tag{1.107}
$$

and
$$
b(t)=\sum_{n=0}^{\infty}{B_n\cos{(n\omega_2t)}}\tag{1.108}
$$

(for simplicity we assumed that the functions were even, so only cosine terms. appear).
The expansions in $$(1.107)$$ and $$(1.108)$$ allow us to express $$f(t)$$ as
$$
f(t)=\sum_{n,k}{A_nB_k\cos{(n\omega_1t)}\cdot\cos{(k\omega_2t)}}\tag{1.109}
$$

and therefore
$$
\begin{align*}
f(t)&=\frac{1}{2}\sum_{n,k}{A_nB_k\cos{\left[(n\omega_1+k\omega_2)t\right]}}\\
&+\frac{1}{2}\sum_{n,k}{A_nB_k\cos{\left[(n\omega_1-k\omega_2)t\right]}}\\
\end{align*}\tag{1.110}
$$

It is not difficult to show that $$f(t)$$ will once again be periodic if $$(1.96)$$ holds, since this implies $$n\omega_1T=2np\pi$$ and $$k\omega_2T=2kp\pi$$ for all integers $$n$$ and $$k$$ as well. In the incommensurate case, $$f(t)$$ is guaranteed to be quasiperiodic since $$(1.110)$$ is an infinite sum of periodic functions. The frequency spectrum is obviously discrete, with nonzero values at $$n\omega_1\pm{k}\omega_2\:(n,k=0,\:1,\cdots)$$.

An example of a nonlinear System with a quasi-periodic attractor is the force van der Pol oscillator
$$
\begin{align*}
\dot{x}_1&=x_2\\
\dot{x}_2&=(1-x_1^2)x_2-x_1+0.5\cos{(1.1t)}
\end{align*}\tag{1.111}
$$

This is a *non-autonomous* system, which differs from $$(1.90)$$ in the sinusoidal forcing term. The time domain responses of $$x_1(t)$$ and $$x_2(t)$$ are shown in __Figs. 1.15__ and __1.16__, suggesting that the steady state Solutions are *not* periodic.

The phase portrait for this system is provided in __Fig. 1.17__, which indicates that the quasi-periodic solution is an attractor for this system. It is important to recognize that a quasi-periodic attractor has a more complicated structure than a limit cycle, which corresponds to a single closed curve in the phase space

#### Fig. 1.15. Evolution of state $$x_1$$.
![fig1-15]()

#### Fig. 1.16. Evolution of state $$x_2$$.
![fig1-16]()

#### Fig. 1.17. The attractor.
![fig1-17]()

#### *Chaotic (Strange) Attractor*
Strange attractors represent the most complicated type of attractor in a nonlinear system. The solutions associated with it appear to be random, and yet they are generated by a well defined deterministic equation. This was a very unexpected (and rather recent) discovery in nonlinear system theory.

We will begin our study of strange attractors with several simple illustrative examples. Most of them are third order systems, since chaos cannot occur in autonomous systems of order $$<3$$ (or non-autonomous systems of order $$<2$$).

### Example 1.11
The Lorenz equation
$$
\begin{align*}
\dot{x}_1&=-10x_1+10x_2\\
\dot{x}_2&=-x_1x_3+28x_1-x_2\\
\dot{x}_3&=x_1x_2-\tfrac{8}{3}x_3
\end{align*}\tag{1.112}
$$

is the first mathematical model in which chaotic behavior was observed. was introduced in 1963 by Edward Lorenz, as a highly simplified framework, for studying atmospheric phenomena.[^1] The strange attractor and its projection onto the all $$x_1-x_3$$ axis are shown in __Figs. 1.18__ and __1.19__, and the evolution state $$x_1(t)$$ is provided in __Fig. 1.20__.

#### Fig. 1.18. The strange attractor for the Lorenz equation.
![fig1-18]()

#### Fig. 1.19. Projection of the attractor onto the $$x_1-x_2$$ plane.
![fig1-19]()

#### Fig, 1.20. Evolution of state $$x_1$$.
![fig1-20]()

### Example 1.12.
The Rossler equation
$$
\begin{align*}
\dot{x}_1&=-x_2-x_3\\
\dot{x}_2&=x_1+0.2x_2\\
\dot{x}_3&=0.2+x_1x_3-5.7x_3
\end{align*}\tag{1.113}
$$

arises in the modeling of fluid flows and chemical reactions, and contains only one nonlinear term.[^2] Nevertheless, it has all the characteristics of chaos, as illustrated in __Figs. 1.21__, __1.22__ and __1.23__

#### Fig. 1.21. The attractor for the Rössler equation.
![fig1-21]()

#### Fig. 1.22. Projection of the attractor onto the $$x_1-x_2$$ plane.
![fig1-22]()

#### Fig. 1.23. Evolution of state $$x_1$$.
![fig1-23]()


### Example 1.13.
The double-scroll equation
$$
\begin{align*}
\dot{x}_1&=9x_2-9h(x_1)\\
\dot{x}_2&=x_1-x_2+x_3\\
\dot{x}_3&=-\left(\tfrac{100}{7}\right)x_2
\end{align*}\tag{1.114}
$$

is associated with a class of nonlinear electronic circuits developed by L. O. Chua.[^3] The nonlinear term $$h(x_1)$$ is piecewise-continuous, and is defined as
$$
h(x_1)=\begin{cases}
\left(\tfrac{2}{7}\right)x_1-\tfrac{3}{7},&x_1\geq1\\
-\left(\tfrac{1}{7}\right)x_1,&-1<x_1<1\\
\left(\tfrac{2}{7}\right)x_1+\tfrac{3}{7},&x_1\leq-1
\end{cases}\tag{1.115}
$$

The attractor and its projection are shown in __Figs. 1.24__ and __1.25__, and the evolution of state $$x_1(t)$$ is provided in __Fig. 1.26__.

#### Fig. 1.24. The attractor for the double scroll equation.
![fig1-24]()

#### Fig. 1.25. Projection of the attractor onto the $$x_1-x_3$$ plane.
![fig1-25]()

### Example 1.14.
The forced Duffing equation
$$
\begin{align*}
\dot{x}_1&=x_2\\
\dot{x}_2&=x_1-x_1^3-0.25x_2+0.3\cos{(t)}
\end{align*}\tag{1.116}
$$

provides an example of chaotic behavior in non-autonomous systems.[^4] The attractor and state $$x_1(t)$$ are shown in __Figs. 1.27__ and __1.28__.

#### Fig. 1.27. The attractor for forced Duffing equation.
![fig1-27]()

#### Fig. 1.28. Evolution of state x1.
![fig1-28]()

[^1]: E. N. Lorenz, “Deterministic nonperiodic flow,” Journal of Atmospheric Science 20, pp. 130-144. 1963.
[^2]: O. E. Rössler, “An equation for continuous chaos,” Physics Letters A, 57, pp. 397-398, 1976.
[^3]: T. Matsumoto, “A chaotic attractor from Chua's circuit,” IEEE Transactions on Circuits and Systems, CAS-31, pp. 1055-1058, 1984.
[^4]: Y. Ueda, “Survey of regular and chaotic phenomena in the forced Duffing oscillator,” Chaos, Solitons and Fractals, 1, pp. 199-231, 1991.



