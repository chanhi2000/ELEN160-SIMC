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

- __CASE 2__. When $$a=9.1$$ and $$b=16$$, the solution is still periodic, but with two different amplitudes. This type of change is known as *period doubling*, and is shown in __Fig. 1.38__.

- __CASE 3__. If parameter $$a$$ is further increased to $$a=9.3$$ (with $$b$$ still fixed at $$16$$), the system exhibits chaotic behavior. The corresponding trajectory for $$x_i(t)$$ is shown in __Fig. 1.39__, and the attractor is provided in __Fig. 1.40__.

Our analysis of the double-scroll equation suggests that the emergence of chaos should be studied in the context of system parameters. This basically means that a dynamic system should be described as
$$
\dot{x}=f(x,p,t)\tag{1.138}
$$

where $$p$$ is a vector of parameters (for the model in $$(1.137)$$, this vector would be p = [a     b]T). Given such a description, our objective will be to analyze the system dynamics as vector p varies. In this analysis, values of p for which the system behavior changes qualitatively will prove to be particularly important, and we will refer to them as bifurcation points. The following examples illustrate different types of bifurcations that can occur in simple nonlinear systems.
