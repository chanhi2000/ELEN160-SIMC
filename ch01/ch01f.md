## 1.6 Chaos in Physical Systems

Chaotic behavior has been observed in a variety of engineering models, ranging from classical Newtonian mechanics to fluid dynamics and electronic circuits. In the following, we will consider two simple physical systems that exhibit this property.

### The Forced Pendulum
As it well known, the motion of a pendulum is governed by Newton’s Second Law. The diagram of forces is shown in __Fig. 1.63__, with $$\theta$$ and $$g$$ denoting the displacement angle and the gravitational acceleration, respectively.

#### Fig. 1.63 The forces acting on the pendulum.
![fig1-63]()

It is usually assumed that the damping force is proportional to the angular velocity, so the overall equation of motion can be expressed as
$$
m\ddot{x}=-\gamma\dot{\theta}-mg\sin{\theta}\tag{1.161}
$$

Recalling that
$$
dx=ld\theta\tag{1.162}
$$

it is easily verified that $$(1.161)$$ can be rewritten as a second order differential equation in $$\theta(t)$$.
$$
ml\ddot{\theta}+\gamma\dot{\theta}=0\tag{1.163}
$$

The dynamics of the pendulum become considerably more interesting if we include an external sinusoidal force
$$
F_e=A\cos{\omega_D{t}}\tag{1.164}
$$

with a *fired frequency* $$\omega_D$$ and a variable amplitude $$A$$. In that case, the model becomes
$$
\ddot{\theta}+\alpha_1\dot{\theta}+\alpha_2\sin{\theta}=p\cos{\omega_D{t}}\tag{1.165}
$$

where $$\alpha_1=\tfrac{\gamma}{ml}$$ and $$\alpha_2=\tfrac{g}{l}$$ are constants, and $$p=\tfrac{A}{ml}$$ is a parameter. Defining $$\omega=\theta$$ and setting $$\alpha_2=1$$ (which can be done by choosing $$l$$ to equal the gravitational acceleration), we can reformulate (1.165) in the form of state eqautions
$$
\begin{align*}
\dot{\theta}&=\omega\\
\dot{\omega}&=\ddot{\theta}=-\alpha_1\omega-\sin{\theta}+p\cos{\omega_D t}
\end{align*}\tag{1.166}
$$

Since this is a *non-autonomous* system, it is useful to define an additional state variable as $$\phi=\omega_D{t}$$. In that case, we obtain a third-order model.
$$
\begin{align*}
\dot{\theta}&=\omega\\
\dot{\omega}&=-\alpha_1\omega-\sin{\theta}+p\cos{\phi}\\\dot{\phi}&=\omega_D
\end{align*}\tag{1.167}
$$

which contains no explicit dependency on time.

To see how chaotic behavior can arise in this system, let us set $$\alpha_1=0.5$$ and $$\omega_D=\tfrac{2}{3}$$, and allow parameter $$p$$ to vary. The system dynamics for two different values of $$p$$ are shown in __Figs. 1.64__-__1.67__, which indicate that both periodic and chaotic motion is possible for a forced pendulum.

#### Fig. 1.64. The periodic motion of a forced pendulum.
![fig1-64]()

#### Fig. 1.65. The limit cycle for the periodic motion.
![fig1-65]()

#### Fig. 1.66 The chaotic motion of a forced pendulum.
![fig1-66]()

#### Fig. 1.67. The strange attractor for the chaotic motion.
![fig1-67]()

### Chua’s Circuit
The circuit shown in __Fig. 1.68__ was first considered by L. O. Chua.

#### Fig. 1.68. Chua's nonlinear circuit.
![fig1-68]()

The nonlinear resistor is defined by the piecewise-linear current-voltage relationship
$$
f(v)=\begin{cases}m_0v+B_p(m_1-m_0),&v\geq{B}_p\\m_1v,&-B_p<v<B_p\\m_0v+B_p(m_1-m_0),&v\leq-B_p\end{cases}\tag{1.168}
$$

whose graphical representation is provided in __Fig. 1.69__.

#### Fig. 1.69. The current-voltage characteristic of the nonlinear element.
![fig1-69]()

THe state model for this circuit can be derived from the following four equations, which correspond to Kirchoff’s laws and Ohm’s law
$$
\begin{matrix}
\begin{matrix}\text{KCL}\\
\begin{aligned}&-i_L+i_{C2}+i_R=0\\&-i_R+i_{C1}+i_0=0
\end{aligned}\end{matrix}&&
\begin{matrix}\text{KVL}\\
v_L+v_{C2}=0
\end{matrix}&&
\begin{matrix}\text{Ohm's Law}\\
i_R=G(v_{C2}-v_{C1})
\end{matrix}
\end{matrix}\tag{1.169}
$$

Recalling that $$i_0=f(v_{C1})$$, equations $$(1.169)$$ yield
$$
\begin{align*}
i_{C2}&=C_2\dot{v}_{C2}=i_L-G(v_{C2}-v_{C1})\\
i_{C1}&=C_1\dot{v}_{C1}=G(v_{C2}-v_{C1})-f(v_{C1})\\
v_L&=L\dot{i}_L=-v_{C2}
\end{align*}\tag{1.170}
$$

In order to simplify the analysis, let us additionally assume that $$G=C_2$$ (numerically, not dimensionally!) and define the following scaled variables
$$
\begin{matrix}
x_1=\frac{v_{C1}}{B_p}&&
x_2=\frac{v_{C2}}{B_p}&&
x_3=\frac{1}{B_pG}i_L
\end{matrix}\tag{1.171}
$$

It is easily verified taht the system now be described as
$$
\begin{align*}
\dot{x}_1&=\alpha[-x_1+x_2-h(x_1)]\\
\dot{x}_2&=x_1-x_2+x_3\\
\dot{x}_3&=-\beta x_2
\end{align*}\tag{1.172}
$$

where
$$
\begin{matrix}
\alpha=\frac{G}{C_i}=\frac{C_2}{C_1},&&
\beta=\frac{1}{LG}
\end{matrix}\tag{1.173}
$$

and
$$
h(x_1)=\frac{1}{B_pG}f(v_{C1})=\begin{cases}bx_1+(a-b),&x_1\geq1\\\alpha x_1,&-1<x_1<1\\bx_1-(a-b),&x_1\geq-1\end{cases}\tag{1.174}
$$

with $$a=\tfrac{m_1}{G}$$ and $$b=\\tfrac{m_0}{G}$$.

It should be noted that $$(1.172)$$ resembles the double-scroll model $$(1.114)$$, the only difference being the addition of term $$x_1(t)$$ in the first equation. It is therefore not surprising that this circuit exhibits chaotic behavior for certain parameter values. The dynamics of this system are illustrated in __Figs. 1.70__-__1.73__, which correspond to two different values of parameter $$\alpha$$ (with $$a$$, $$b$$ and $$\beta$$ set to $$a=-\tfrac{8}{7}$$, $$b=–\tfrac{5}{7}$$ and $$\beta=16$$ in both cases).


#### Fig. 1.70. A periodic solution for Chua’s circuit.
![fig1-70]()

#### Fig. 1.71. The limit cycle corresponding to the periodic solution.
![fig1-71]()

#### Fig. 1.72. Chaotic oscillations in CHua’s circuit.
![fig1-72]()

#### Fig. 1.73. THe strange attractor for the chaotic case.
![fig1-73]()

### Attractor Reconstruction
The previous two examples have well defined analytical models, and the corresponding attractors can be constructed quite accurately using numerical simulation. But what if we are dealing with a physical system whose model is not known, and for which we can measure only a single output variable $$y(t)$$? Is it possible to detect chaos in such a system, and perhaps distinguish it from purely random behavior? Amazingly, in some cases it is. It turns out that if the system has an attractor of low dimension, we can approximately “reconstruct” this set.

In order to understand how this can be done, we first need to revisit the problem of estimating fractal dimensions. In the case of chaotic attractors, the capacitive dimension introduced in (__Section 1.3__)[ch01c.md] is usually a rather impractical measure, since it generally requires a great deal of computer time and memory. An alternative definition with better numerical properties is the so-called *correlation dimension*, whose calculation is explained below.

- __STEP 1.__ Generate a large set of points on the attractor (a single solution will do if we run it long enough to eliminate all transients).

- __STEP 2.__ Fix a point $$x$$ on the attractor, and let $$N_x(\epsilon)$$ denote the number of points from this set that are contained in an n-dimensional ball of radius $$\epsilon$$ centered at $$x$$.

- __STEP 3.__ As $$\epsilon$$ increases, $$N_x(\epsilon)$$ is expected to grow as $$N_x(\epsilon)\sim\epsilon^{dx_x}$$. The exponent $$d_x$$ that characterizes this function is referred to as the *pointwise dimension* at $$x$$.

- __STEP 4.__ Since it is an arbitrary point (and can be chosen from a sparser or denser portion of the attractor), repeat the procedure for many different point and average $$N_x(\epsilon)$$ for a fixed $$\epsilon$$. This average, denoted $$C(\epsilon)$$ considered tο be independent of $$x$$, and is assumed to have the form $$C(\epsilon)\sim\epsilon^d$$. The exponent $$d$$ in this expression is referred to as the *correlation dimension*. Typically, the dimension is somewhat smaller than its capacitive counterpart, but the two are usually similar.

In order to determine $$d$$ explicitly, it usually suffices to plot $$\log{(C(\epsilon))}$$ as function of $$\log{(\epsilon)}$$. In estimating the slope, one should bear in mind that the graph is linear only in its "middle" portion. Indeed, for large values of $$\epsilon$$, the n-dimensional ball includes the *entire* attractor, so $$N_x(\epsilon)$$ cannot increase an further (which creates a saturation effect). On the other hand, when $$\epsilon$$ is sufficiently small, $$x$$ will be the only point that is included in $$N_x(\epsilon)$$.

Having defined an appropriate measure of dimensionality, we can now describe the process of attractor reconstruction in terms of the following three step algorithm.

- __STEP 1.__	Fix a delay value $$\Delta$$, and form a $$k+1$$ - dimensional vector
$$
z(t)=\left[\begin{matrix}
z_1(t)\\z_2(t)\\z_3(t)\\\vdots\\z_{k+1}(t)\end{matrix}\right]
=\left[\begin{matrix}y(t)\\y(t-\Delta)\\y(t-2\Delta)\\\vdots\\y(t-k\Delta)
\end{matrix}\right]\tag{1.175}
$$
Then, plot the evolution of $$z$$ in the $$k+1$$ – dimensional state space, and identify the attractor (if one exists).

-__STEP 2.__ Estimate the correlation dimension of the attractor, using procedure described above.

-__STEP 3.__ If the correlation dimension is larger than in the previous step, increment k and repeat the process. If it remains unchanged, stop.[^8]

It has actually been shown that when the system has a low order chaotic attractor, then there exists a delay $$\Delta$$ and an "embedding dimension" $$k$$ which allow for its successful reconstruction.[^9] The problem with this result is that it is not clear how to optimally choose $$\Delta$$, so in most cases the appropriate delay needs to be determined heuristically. Despite this weakness, however, it is fair to say that the possibility of attractor reconstruction remains a truly remarkable result. Edward Lorenz (the scientist, who discovered chaos) actually claimed that this was the most surprising property that he encountered in his study of nonlinear systems.[^10]

[^8]: If the system has a low order chaotic attractor, the correlation dimension computed by this algorithm should converge to a small number. This is quite different from purely random systems, where the dimension increases monotonically with $$k$$.
[^9]: See, for example: Floris Takens, “Detecting strange attractors in turbulence,” in *Dynamic Systems and Turbulence - Warwick 1980*, D. A. Rand and L. S. Young (Eds.), Springer-Verlag, 1981.
[^10]: S. Strogatz, Nonlinear Dynamics and Chaos, Perseus Publishing, 1994.
