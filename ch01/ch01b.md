## 1.2 Nonlinear Systems

A nonlinear dynamic system is generally described by a set of first order differential equations
> ######(1.62)
$$
\dot{x}=f(x,t)
$$

where $$f(x,t)$$ is a vector-valued nonlinear function. Models of this type arise in a wide variety of applications, ranging from engineering to economics and ecology. From a theoretical standpoint, it is important to distinguish between *autonomous* and *non-autonomous* dynamical systems.  An example of a non-autonomous system would be
> ######(1.63)
$$
\begin{align*}
\dot{x}_1&=-x_1+2x_1x_2+x_2^2\\
\dot{x}_2&=x_1+x_2+x_1^2x_2+2\cos{(3t)}
\end{align*}
$$

where time shows up *explicitly* through the cosine term. In such cases it is appropriate to use the general description (1.62), since $$f$$ is a function of both $$x$$ and $$t$$. In contrast, an autonomous system has no explicit time dependency, and can be described simply as
> ######(1.64)
$$
\begin{align*}
\dot{x}=f(x)
\end{align*}
$$

The second order system
> ######(1.65)
$$
\begin{align*}
\dot{x}_1&=x_1-x_2^2\\\dot{x}_2&=x_1\sin{(x_{2})}-x_2
\end{align*}
$$

is a typical example.
To see how nonlinear systems differ from their linear counterparts, let us consider a simple scalar system
> ######(1.66)
$$
\begin{align*}
\dot{x}=x^{2}+2x
\end{align*}
$$

with a quadratic nonlinearity. The first thing that we notice about it is that it has multiple equilibria, corresponding to $$x^e=0$$ and $$x^e=-2$$. This is quite unlike linear systems, where the coordinate origin was always the unique equilibrium, regardless of the size of the model (assuming, of course, that matrix $$A$$ is nonsingular). In dealing with multiple equilibria, two questions arise naturally:
1. How can we compute all the equilibria of a general dynamic system?
2. Is it possible to determine whether a particular equilibrium is an attractor or a repeller?

In the following, we will address these issues in some detail.

#### Computation of Equilibria
The system equilibria can be viewed as solutions of the algebraic equation
> ######(1.67)
$$
\begin{align*}
f(x)=0
\end{align*}
$$

Computing the solutions of (1.67) can be a very difficult task in general, and there are no guarantees that all of them will be found. One of the most effective solution techniques for nonlinear equations is the so-called Newton iterative method. The following simple example illustrates the basic ideas of this approach

**Example 1.6.** Consider the scalar equation
> ######(1.68)
$$
\begin{align*}
f(x)=x^2+4x+3=0
\end{align*}
$$

which we propose to solve iteratively. In order to do that, we will form the following sequence
> ######(1.69)
$$
\begin{align*}
x(k+1)=x(k)-\left|f'(x(k))\right|^{-1}f(x(k))
\end{align*}
$$

| $$x(0)=0$$ | $$x(0)-5$$ |
| :--------: | :--------: |
| $$x(1)=-0.7500$$ | $$x(1)=-3.6700$$ |
| $$x(2)=-0.9750$$ | $$x(2)=-3.1330$$ |
| $$x(3)=-0.9969$$ | $$x(3)=-3.0078$$ |
| $$x(4)=-0.9999$$ | $$x(1)=-3.0000$$ |

##### Table 1.1. Iterative sequences for two different initial guesses.

##### Fig. 1.3. An illustration of Newton's method.

starting from some initial guess x(0). Two possible scenarios are shown in Table 1.1, suggesting that different choices of x(0) can lead to very different solutions.

Before extending Newton's method to larger systems, it is useful to consider its geometric interpretation in the scalar case. To that effect, in Fig. 1.3 we show the plot of function (1.68) in a region that contains the solution $$x^*=-1$$.

The point labeled $$x(1)$$ represents the intersection of slope $$f'(x(0))$$ with the x-axis. As a result, we can write

> ######(1.70)
$$
\begin{align*}
f('x(0))=\frac{f(x(0))}{x(0)-x(1)}
\end{align*}
$$

which directly impliess
> ######(1.71)
$$
\begin{align*}
x(1)=x(0)-\left|f'(x(k))\right|^{-1}f(x(0))
\end{align*}
$$

Equation (1.71) allows us to conclude that point $$x(1)$$ on the graph corresponds to the first iterate obtaining using Newton's method. It is not difficult to see $$x(2)$$, $$x(3)$$, etc. have the same interpretation, and that this sequence converges to $$x^*=-1$$.

In the multivariable case, Newton's method takes the form
> ######(1.72)
$$
\begin{align*}
x(k+1)=x(k)-\left|J(x(k))\right|^{-1}f(x(k))
\end{align*}
$$

where
> ######(1.73)
$$
\begin{align*}
f(x)=\left[\begin{matrix}f_1(x_1,x_2,\cdots,x_n)\\\vdots\\f_n(x_1,x_2,\cdots,x_n)\end{matrix}\right]
\end{align*}
$$

is a vector-valued nonlinear function, and
> ######(1.74)
$$
\begin{align*}
J(x)=\left[\begin{matrix}\tfrac{\partial{f}_1}{\partial{x}_1}&\cdots&\tfrac{\partial{f}_1}{\partial x_n}\\\vdots&\ddots&\vdots\\\tfrac{\partial{f}_n}{\partial x_1}&\cdots&\tfrac{\partial{f}_n}{\partial x_n}\end{matrix}\right]
\end{align*}
$$

represents its Jacobian. The following example illustrates how the iterative process works in this case.

**Example 1.7.** Consider the pair of nonlinear equations
> ######(1.75)
$$
\begin{align*}
f(x)-\left[\begin{matrix}3x_1x_2-x_2^{-2}-e^{x_1}\\x_1^2x_2-\cos{(x_1)}-x_2\end{matrix}\right]=0
\end{align*}
$$

whose solutions we wish to compute. It is easily verified that the Jacobian of this system has the form
> ######(1.76)
$$
\begin{align*}
J(x)=\left[\begin{matrix}3x_2-e^{x_1}&3x_1+2x_2^{-3}\\2x_1x_2+\sin{(x_1)}&x_1^2-1\end{matrix}\right]
\end{align*}
$$

In Table 1.2, we show Newton's iterates for two different initial guesses.

| x | x |
| :---: | :---: |
| $$x(0)=\left[\begin{matrix}1&1\end{matrix}\right]$$ | $$x(0)=\left[\begin{matrix}-1&-1\end{matrix}\right]$$ |
| $$x(1)=\left[\begin{matrix}1.1901&1.1329\end{matrix}\right]$$ | $$x(1)=\left[\begin{matrix}-0.5336&-0.9877\end{matrix}\right]$$ |
| $$x(2)=\left[\begin{matrix}1.1619&1.1379\end{matrix}\right]$$ | $$x(2)=\left[\begin{matrix}-0.4134&–1.1120\end{matrix}\right]$$ |
| $$x(3)=\left[\begin{matrix}1.1617&1.1383\end{matrix}\right]$$ | $$x(3)=\left[\begin{matrix}-0.4330&-1.1167\end{matrix}\right]$$ |
| $$x(4)=\left[\begin{matrix}1.1617&1.1383\end{matrix}\right]$$ | $$x(4)=\left[\begin{matrix}-0.4328&-1.1170\end{matrix}\right]$$ |
##### Table 1.2. Iterative sequences for two different initial guesses.

As in Example 1.6, it is apparent that different initial guesses produce different solutions of (1.75).  In this case, however, it is very difficult to tell whether additional solutions exist (and what initial guesses would lead to them).  The same can be said for a broad class of similar problems where analytical solutions are not available.

**Remark 1.2.** In general, there is no guarantee that Newton's method will converge. Whether or not that will happen depends to a large extent on the choice of initial approximation.  This can be a major problem, particularly when the system is large.

#### Stability

A simple way to determine whether a given equilibrium $$x^e$$ is attractive or not is to linearize the system using the Taylor series expansion. For the system shown in (1.66), linearization around $$x^e=0$$ yields
> ######(1.77)
$$
\begin{align*}
\dot{x}=2x
\end{align*}
$$

which indicates that this equilibrium is a repeller. Similarly, linearization around $$x^e=-2$$ yields

> ######(1.78)
$$
\begin{align*}
\dot{y}=-2y
\end{align*}
$$

where $$y=x-x^e$$. This implies that $$x^e=-2$$ is an *attractor*

It is important to recognize that linearization provides only *local* information about an equilibrium. As a result, we can claim that the trajectories originating close to xe = –2 will be attracted by this equilibrium, but we can really say anything about other solutions of the system. This is another fundamental difference with respect to linear system, where an asymptotically stable equilibrium was a global attractor

To further illustrate the local properties of equilibria, let us consider the systems
> ######(1.79)
$$
\begin{align*}
\dot{x}_1&=-3x_{1}+4x_{1}^2-0.5x_1x_2-x_1^3\\
\dot{x}_2&=-2.1x_2+x_1x_2
\end{align*}
$$

which represents a variant of the classical predator-prey model in ecology ($$x_1$$ and $$x_2$$ are the populations of the prey and predator, respectively)

##### A. The Equilibria
Our first step will be to determine the equilibria of this system, which implies solving the following pair of equations
> ######(1.80)
$$
\begin{align*}
&-3x_{1}+4x_{1}^2-0.5x_1x_2-x_1^3=0\\
&-2.1x_2+x_1x_2=0
\end{align*}
$$

In a typical nonlinear system we would have to do this numerically, with no guarantee of finding all possible solutions. In this case, however, the problem can be solved analytically, by observing that condition
> ######(1.81)
$$
\begin{align*}
x_2(x_1-2.1)=0
\end{align*}
$$

allows for two possible cases:

**CASE 1.** $$x_2\neq0$$, which implies that $$x_1=2.1$$ and $$x_2=1.98$$ is the unique solution

**CASE 2.** $$x_2=0$$, which implies that $$x_1$$ can be determined by solving equation

> ######(1.82)
$$
\begin{align*}
-3x_1+4x_1^2-x_1^3=0
\end{align*}
$$

This is a simple third order polynomial with roots $$0$$, $$1$$, and $$3$$.
Based on the above analysis, we can conclude that the predator-prey model has exactly four equilibria
> ######(1.83)
$$
\begin{matrix}
x^{e}=\left[\begin{matrix}0\\0\end{matrix}\right];&
x^e=\left[\begin{matrix}1\\0\end{matrix}\right];&
x^e=\left[\begin{matrix}3\\0\end{matrix}\right];&
x^e=\left[\begin{matrix}2.10\\1.98\end{matrix}\right];
\end{matrix}
$$


##### B. stability
Turning now to the question of stability, we first need to linearize the system around each equilibrium. The Jacobian of (1.80) has the general form

> ######(1.84)
$$
\begin{align*}
J(x)=\left[\begin{matrix}(-3+8x_1-0.5x_2-3x_1^2)&-0.5x_1\\x_2&-2.1+x_1\end{matrix}\right]
\end{align*}
$$

which leads to the following scenarios:
1. For $$x^e=\left[\begin{matrix}0&0\end{matrix}\right]^T$$, we have
> ######(1.85)
$$
\begin{align*}
J(x^e)=\left[\begin{matrix}-3&0\\0&-2.1\end{matrix}\right]
\end{align*}
$$

The linearized system is therefore
> ######(1.86)
$$
\begin{align*}
\dot{y}=J(x^e)y
\end{align*}
$$

where $$y=x-x^e$$. Since this is now a system of the form (1.15), its stability properties can be determined by checking the eigenvalues. In this case, $$\lambda_1=-3$$ and $$\lambda_2=-2.1$$, indicating that $$x^e=\left[\begin{matrix}0&0\end{matrix}\right]^T$$ is a *stable* equilibrium.

2. For $$x^e=\left[\begin{matrix}1&0\end{matrix}\right]^T$$, we have
> ######(1.87)
$$
\begin{align*}
J(x^e)=\left[\begin{matrix}2&-0.5\\0&-1.1\end{matrix}\right]
\end{align*}
$$

and the eigenvalues of the linearized system are $$\lambda_1=2$$ and $$\lambda_2=-1.1$$. This indicates that $$x^e=\left[\begin{matrix}1&0\end{matrix}\right]^T is an *unstable* equilibrium.

3. For $$x^e=\left[\begin{matrix}3&0\end{matrix}\right]^T$$, we have
> ######(1.88)
$$
\begin{align*}
J(x^e)=\left[\begin{matrix}-6&-1.5\\0&0.9\end{matrix}\right]
\end{align*}
$$

and the eigenvalues of the linearized system are $$\lambda_1=-6$$ and $$\lambda_2=-0.9$$. This indicates that $$x^e=\left[\begin{matrix}3&0\end{matrix}\right]^T$$ is an *unstable* equilibrium.

4. For $$x^e=\left[\begin{matrix}2.1&1.98\end{matrix}\right]^T$$, we have
> ######(1.89)
$$
\begin{align*}
J(x^e)=\left[\begin{matrix}-0.42&-1.05\\1.98&0\end{matrix}\right]
\end{align*}
$$

and the eigenvalues of the linearized system are $$\lambda_{1,2}=-0.21\pm{j}1.43$$. This indicates that $$x^e=\left[\begin{matrix}2.1&1.98\end{matrix}\right]^T$$ is a *stable* equilibrium.

At this point, we know that two of the four equilibria are locally attractive. However, we still don't know what happens to solutions that don’t originate in the immediate neighborhood of these equilibria. This is actually a very hard question to answer analytically, even for relatively simple systems. One way to approach the problem is to perform multiple simulations, and then plot each trajectory in the $$x_1$$-$$x_2$$ plane. A collection of these trajectories referred to as the *phase portrait* of the system, and is shown in Fig. 1.4 (the Solid dots indicate the initial conditions).

##### Fig. 1.4. Regions of attraction for different equilibria.

Fig. 1.4 suggests that there are entire regions in the phase space from which solutions are attracted to particular equilibria. Such regions are known as regions of attraction. In this context we should note that there may also be regions from which solutions are not attracted to any of the equilibria (an example of such a region is the lower right-hand quadrant of Fig. 1.4).

#### Types of Attractors in Nonlinear Systems
In all the examples that we considered so far, the trajectories were attracted to (or repelled by) the system equilibria. It turns out, however, that nonlinear systems trajectories can also be attracted by other objects in the phase space. In the following, we will identify three such objects, in increasing degree of complexity.

##### *Limit Cycles*
Let us consider the following system (also known as the van der Pol oscillator)

> ######(1.90)
$$
\begin{align*}
\dot{x}_1&=x_2\\
\dot{x}_2&=(1-x_1^2)x_2-x_1
\end{align*}
$$

which has a unique equilibrium at the origin. Observing that the Jacobian has the form
> ######(1.91)
$$
\begin{align*}
\end{align*}
$$

> ######(1.92)
$$
\begin{align*}
\end{align*}
$$

> ######(1.93)
$$
\begin{align*}
\end{align*}
$$

> ######(1.94)
$$
\begin{align*}
\end{align*}
$$

> ######(1.95)
$$
\begin{align*}
\end{align*}
$$

> ######(1.96)
$$
\begin{align*}
\end{align*}
$$

> ######(1.97)
$$
\begin{align*}
\end{align*}
$$

> ######(1.98)
$$
\begin{align*}
\end{align*}
$$

> ######(1.99)
$$
\begin{align*}
\end{align*}
$$

> ######(1.100)
$$
\begin{align*}
\end{align*}
$$

> ######(1.101)
$$
\begin{align*}
\end{align*}
$$

> ######(1.102)
$$
\begin{align*}
\end{align*}
$$

> ######(1.103)
$$
\begin{align*}
\end{align*}
$$

> ######(1.104)
$$
\begin{align*}
\end{align*}
$$

> ######(1.105)
$$
\begin{align*}
\end{align*}
$$

> ######(1.106)
$$
\begin{align*}
\end{align*}
$$

> ######(1.107)
$$
\begin{align*}
\end{align*}
$$

> ######(1.108)
$$
\begin{align*}
\end{align*}
$$

> ######(1.109)
$$
\begin{align*}
\end{align*}
$$

> ######(1.110)
$$
\begin{align*}
\end{align*}
$$

> ######(1.111)
$$
\begin{align*}
\end{align*}
$$

> ######(1.112)
$$
\begin{align*}
\end{align*}
$$

> ######(1.113)
$$
\begin{align*}
\end{align*}
$$

> ######(1.114)
$$
\begin{align*}
\end{align*}
$$

> ######(1.115)
$$
\begin{align*}
\end{align*}
$$

> ######(1.116)
$$
\begin{align*}
\end{align*}
$$
