## 1.4 Bifurcation

Chaos is not a universal phenomenon, and occurs only under certain comditions. To understand what this means, let us consider a variant of the double-scroll equation
$$
\begin{align*}
\dot{x}_1&=a\left[x_2-h(x_1)\right]\\
\dot{x}_2&=x_1-x_2+x_3\\
\dot{x}_3&=-bx_2
\end{align*}\tag{1.137}
$$

where $$a$$ and $$b$$ are parameters than can change (parameter variations are very common in engineering models). In the following, we will look at three different scenarios.
- __CASE 1__. For $$a=8.8$$ and $$b=16$$ the system has a periodic solution with a *single* amplitude. This property is illustrated in __Fig. 1.37__, where we show the evolution of state $$x_i(t)$$.

#### Fig. 1.37. Periodic solution with a single amplitude.
![fig1-37]()

- __CASE 2__. When $$a=9.1$$ and $$b=16$$, the solution is still periodic, but with two different amplitudes. This type of change is known as *period doubling*, and is shown in __Fig. 1.38__.

#### Fig. 1.38. Periodic solution with two amplitudes.
![fig1-38]()

- __CASE 3__. If parameter $$a$$ is further increased to $$a=9.3$$ (with $$b$$ still fixed at $$16$$), the system exhibits chaotic behavior. The corresponding trajectory for $$x_i(t)$$ is shown in __Fig. 1.39__, and the attractor is provided in __Fig. 1.40__.

#### Fig. 1.39. A chaotic solution.
![fig1-39]()

#### Fig. 1.40. The strange attractor.
![fig1-40]()

Our analysis of the double-scroll equation suggests that the emergence of chaos should be studied in the context of system parameters. This basically means that a dynamic system should be described as
$$
\dot{x}=f(x,p,t)\tag{1.138}
$$

where $$p$$ is a vector of parameters (for the model in $$(1.137)$$, this vector would be $$p=\left[\begin{matrix}a&b\end{matrix}\right]^T$$). Given such a description, our objective will be to analyze the system dynamics as vector $$p$$ varies. In this analysis, values of $$p$$ for which the system behavior changes qualitatively will prove to be particularly important, and we will refer to them as bifurcation points. The following examples illustrate different types of bifurcations that can occur in simple nonlinear systems.


### Example 1.21.
(Saddle-node bifurcation). Consider the system
$$
\dot{x}=p-x^2\tag{1.139}
$$

where $$p$$ is a scalar parameter. For values $$p<0$$, this system has no equilibrium, since equation
$$
p-x^2=0\tag{1.140}
$$

has no real solutions. For $$p=0$$, there is a unique equilibrium at $$x=0$$, and for $$p>0$$ there are two equilibria corresponding to $$\pm\sqrt{p}$$. Note that the linearized system at $$x^e=\sqrt{p}$$ is
$$
\dot{y}=-2\sqrt{p}y\tag{1.141}
$$

which which indicates that this is a *stable* equilibrium. On the other hand, the linearization at $$x^e=-\sqrt{p}$$ produces
$$
\dot{y}=2\sqrt{p}y\tag{1.142}
$$

which is clearly *unstable*.

The analysis outlined above is best summarized by plotting the system equilibria as a function of $$p$$. Such a plot is known as a *bifurcation diagram*, and is very useful in analyzing chaos. The bifurcation diagram for the system $$(1.139)$$ is shown in __Fig. 1.41__, in which unstable equilibria are indicated by dashed lines.

From __Fig. 1.41__ it is quite obvious that this system undergoes a qualitative change for $$p=0$$, when two new equilibria emerge. As a result, $$p=0$$ represents a bifurcation point for this system. Since one of the new equilibria is always stable and the other one unstable, this type of bifurcation is known as a *saddle-node*.

#### Fig. 1.41. A saddle node bifurcation.
![fig1-41]()

### Example 1.22.
(Pitchfork bifurcation). Consier the system
$$
\dot{x}=x(p-x^2)\tag{1.143}
$$

For $$p<0$$, the only equilibrium is $$x=0$$, while for $$p>0$$ there are two more, corresponding to $$\pm\sqrt{p}$$. Te jacobian associated with $$(1.143)$$ has the form
$$
J(x)=p-3x^2\tag{1.144}
$$

For the three equilibria, we have the following scenarios:

**(i)** For $$x^e=0$$, the linearized system is
$$
\dot{x}=pz\tag{1.145}
$$

Consequently, this equilibrium is stable when $$p<0$$, and unstable when $$p>0$$.

**(ii)** For $$x^e=\sqrt{p}$$, the linearized system is
$$
\dot{y}=-2py\tag{1.146}
$$
where $$y=x-x^e$$. Since this equilibrium exists only for $$p>0$$, it is always stable.

**(iii)**  For $$x^e=-\sqrt{p}$$, the linearized system is exactly the same as $$(1.146)$$, and the same analysis applies. As a result, this equilibrium is stable for all $$p>0$$.

The above analysis is summarized in the bifurcation diagram shown in __Fig. 1.42__.

It is clear that $$p=0$$ represents a bifurcation point for this system. This type of bifurcation where two *stable* equilibria emerge is known as a *pitchfork* (the reason for this name is obvious from __Fig. 1.42__).

#### Fig. 1.42. A pitchfork bifurcation.
![fig1-42]()

### Example 1.23.
(Transcritical bifurcation). The system
$$
\dot{x}=x(p-x)\tag{1.147}
$$

has two equilibria for all values of $$p$$, located at $$x^e=0$$ and $$x^e=p$$, respectively. Linearization around these equilibria gives rise to the following two cases:

**(i)** For $$x^e=0$$, the linearized system is
$$
\dot{x}=px\tag{1.148}
$$

Consequently, this equilibrium is stable when $$p<0$$, and unstable when $$p>0$$.

**(ii)** For $$x^e=p$$, the linearized system is
$$
\dot{y}=-py\tag{1.149}
$$
where $$y=x-x^e$$. This equilibrium is stable when $$p>0$$, and unstable when $$p<0$$

The bifurcation diagram for this system is shown in __Fig. 1.43__. It indicates that $$p=0$$ is once again a bifurcation point, but the nature of the qualitative change is different from the previous two examples. In this case no new equilibria are created following the bifurcation, but there is an exchange of stability between the two equilibria. Such a bifurcation is referred to as *transcritical*.

#### Fig. 1.43. A transcritical bifurcation.
![fig1-43]()

Bifurcations are by no means limited to equilibria. The following example describes the so-called Hopf bifurcation, in which a limit cycle is born for a particular parameter value.

### Example 1.24.
(Hopf bifurcation). Consider the system
$$
\begin{align*}
\dot{x}_1&=p_1x_1-p_2x_2-(x_1^2+x_2^2)x_1\\
\dot{x}_2&=p_2x_1+p_1x_2-(x_1^2+x_2^2)x_2
\end{align*}\tag{1.150}
$$

which contains two parameters, $$p_1$$ and $$p_2$$. It is easily verified that this system has an equilibrium at the origin, and the corresponding Jacobian is
$$
J(x^e)=\left[\begin{matrix}p_1&-p_2\\p_2&p_1\end{matrix}\right]\tag{1.151}
$$

The eigenvalues of $$J(x^e)$$ are $$\lambda_{1,2}=p_1\pm{j}p_2$$, which means that this equilibrium is stable for $$p_1<0$$ and unstable for $$p_1>0$$.

It is important to recognize that the stability of the equilibrium is not the only thing that changes when $$p_1$$ passes through zero. To see this more clearly, let us introduce new variables $$r$$ and $$\theta$$ such that
$$
\begin{align*}
x_1&=r\cos{\theta}\\
x_2&=r\sin{\theta}
\end{align*}\tag{1.152}
$$

In that case, the derivatives $$\dot{x}_1$$ and $$\dot{x}_2$$ become
$$
\begin{align*}
\dot{x}_1&=\dot{r}\cos{\theta}-(r\sin{\theta})\dot{\theta}\\
\dot{r}_2&=\dot{r}\sin{\theta}+(r\cos{\theta})\dot{\theta}
\end{align*}\tag{1.153}
$$

Substituting into $$(1.150)$$, we can rewrite this equation as
$$
\begin{align*}
\dot{r}\cos{\theta}-(r\sin{\theta})\dot{\theta}&=p_1r\cos{\theta}-p_2r\sin{\theta}-r^3\cos{\theta}\\\dot{r}\sin{\theta}+(r\cos{\theta})\dot{\theta}&=p_2r\cos{\theta}+p_1r\sin{\theta}-r^3\sin{\theta}
\end{align*}\tag{1.154}
$$

Sorting out the terms, we obtain
$$
\begin{align*}
\cos{\theta}(\dot{r}-p_1r+r^3)-\sin{\theta}(r\dot{\theta}-p_2r)&=0\\
\sin{\theta}(\dot{r}-p_1r+r^3)+\cos{\theta}(r\dot{\theta}-p_2r)&=0
\end{align*}\tag{1.155}
$$

Since $$(1.155)$$ must equal zero for all $$\theta$$, the following two conditions must hold
$$
\begin{matrix}\begin{aligned}&\dot{r}-p_1r+r^3=0\\&r\dot{\theta}-p_2r=0\end{aligned}&&\Rightarrow&&\begin{align*}&\dot{r}=r(p_1-r^2)\\&r(\dot{\theta}-p_2)=0\end{align*}
\end{matrix}\tag{1.156}
$$

Both equations are obviously satisfied for $$r=0$$ (which corresponds to the equilibrium at the origin). However, when $$p_1>0$$, there is also a solution of the form
$$
\begin{align*}
r(t)&=\sqrt{p_1}\\
\theta(t)&=p_2t
\end{align*}\tag{1.157}
$$

In the original coordinates, this solution can be expressed as
$$
\begin{align*}
x_1(t)&=\sqrt{p_1}\cos{(p_2t)}\\
x_2(t)&=\sqrt{p_1}\sin{(p_2t)}
\end{align*}\tag{1.158}
$$

This is clearly a limit cycle, which corresponds to a circle of radius $$\sqrt{p_1}$$ in the phase plane.

What can we conclude in this case?

1. .$$p=0$$ is a bifurcation point, at which a limit cycle of amplitude $$\sqrt{p_1}$$ is born. In general, it can be shown that the amplitude of any limit cycle born through a Hopf bifurcation is always proportional to $$(p-p_0)^{\tfrac{1}{2}}$$, where $$p_0$$ is the bifurcation point.

2. It can be shown that the limit cycle in this example is an attractor for *all* values of $$p_1>0$$. An illustration of this fact is provided in __Fig. 1.44__, for $$p_1=1$$ and $$p_2=1$$.
#### Fig. 1.44. The limit cycle for a Hopf bifurcation.
![fig1-44]()

3. A Hopf bifurcation which gives rise to an attractive limit cycle is called *supercritical*. If the limit cycle turns out to be unstable (and it can!), we refer to the bifurcation as *subcritical*.

4. The notion of a Hopf bifurcation can be generalized to the scenario where an originally stable limit cycle loses this property, and in the process gives birth to a second limit cycle with a different frequency. In the following, we will refer to this process as a *generalized Hopf bifurcation*.

In systems of higher order, there are a number of other possibilities for bifurcations. Since a rigorous analysis of these phenomena is very complicated, in the following we will tend to describe them in terms of bifurcation diagrams. Before we apply this method, however, we need to address a conceptual problem that arises in this context. All our bifurcation diagrams up to this point involved plots of the equilibria as a function of the parameter, However, this approach doesn't work in the case of Hopf bifurcations, where we have to deal with a limit cycle that consists of infinitely many points. The problem is likely to get even worse for quasi-periodic and chaotic attractors. How can we incorporate different types of attractors into the bifurcations diagram without significantly complicating it? A simple way would be to plot only the local *maxima* of a trajectory that belongs to the attractor, and add them to the equilibrium points that are already in the diagram. In our еxample, all the local maxima of the limit cycle are equal to $$\sqrt{p_1}$$, so its contribution for a given value of $$p_1$$ would be a single point on the bifurcation diagram. The plot for system $$(1.150)$$ obtained using this method is shown in Fig. 1.45.
__Fig. 1.45__. The bifurcation diagram.
