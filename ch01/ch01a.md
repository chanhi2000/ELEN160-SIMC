## 1.1	Linear Systems: An Overview

The dynamic behavior of physical systems can often be described by a set of n first order differential equations of the form

$$
\dot{x}=Ax+Bu\tag{1.1}
$$

In $$(1.1)$$
$$
x(t)=\left[\begin{matrix}x_1\\\vdots\\x_n\end{matrix}\right]\tag{1.2}
$$

represents the *state vector*
$$
u(t)=\left[\begin{matrix}u_1\\\vdots\\u_m\end{matrix}\right]\tag{1.3}
$$

denotes the *input*, and $$A$$ and $$B$$ are constant matrices of dimension $$n\times{n}$$ and $$n\times{m}$$, respectively. The following two examples illustrate how models of this type arise naturally in engineering problems.

### Example 1.1.
Let us consider a body with mass m which is connected to a spring and moves along a friction-producing surface. A schematic diagram of this system is provided in __Fig. 1.1.__, where $$F(t)$$ represents an external force (which can be time-varying in general.)

#### Fig. 1.1. A simple mechanical system.
![fig1-01]()

It is normally assumed that friction is proportional to the velocity of the body, and that the restoring force of the spring has the form
$$
F_s=-kx\tag{1.4}
$$

In that case, Newton’s Second Law produces the following equation of motion.
$$
m\ddot{x}=-\gamma\dot{x}-kx+F(t)\tag{1.5}
$$

In order to obtain a state-space model, let us introduce state variable $$x_1(t)$$ and $$x_2(t)$$ as
$$
\begin{align*}
x_1(t)&=x(t)\\
x_2(t)&=\dot{x}(t)
\end{align*}\tag{1.6}
$$

Observing that $$\ddot{x}(t)=\dot{x}_2(t)$$, $$(1.5)$$ can then be replaced by two first-order differential equations
$$
\begin{align*}
\dot{x}_1&=x_2\\
\dot{x}_2&=-\left(\frac{k}{m}\right)x_1-\left(\frac{\gamma}{m}\right)x_2+\left(\frac{1}{m}\right)F(t)
\end{align*}\tag{1.7}
$$

This representation clearly conforms to $$(1.1)$$ with
$$
\begin{matrix}
A=\left[\begin{matrix}0&1\\-k/m&-\gamma/m\end{matrix}\right],\\
B=\left[\begin{matrix}0\\1/m\end{matrix}\right],\\
u(t)=F(t)
\end{matrix}\tag{1.8}
$$

### Example 1.2.
Consider the circuit in Fig. 1.2, where $$v_g(t)$$ is assumed to be a time-varying voltage source.

#### Fig. 1.2. A second order circuit.
![fig1-02]()

Kirchoff's current and voltage laws for this circuit produce the following two equations
$$
\begin{aligned}
&i_C-i_L&=0\\
&-v_g(t)+Ri_L+v_L+v_C&=0
\end{aligned}\tag{1.9}
$$

Recalling that
$$
\begin{matrix}v_L=L\frac{di_L}{dt}&&\text{and}&&i_C=C\frac{dv_C}{dt}\end{matrix}\tag{1.10}
$$

.$$(1.9)$$ becomes
$$
\begin{align*}
C\dot{v}_C&=iL\\
L\dot{i}_L&=-v_C-Ri_L+v_g(t)
\end{align*}\tag{1.11}
$$

If we now define new variables $$x_1(t)$$ and $$x_2(t)$$ as
$$
\begin{align*}
x_{1}(t)&=v_C(t)\\
x_{2}(t)&=i_L(t)
\end{align*}\tag{1.12}
$$

We obtain a pair of first-order differential equations
$$
\begin{align*}
\dot{x}_{1}&=(1/C)x_2\\
\dot{x}_{2}&=-(1/L)x_1-(R/L)x_2+(1/L)v_g(t)
\end{align*}\tag{1.13}
$$

This form obviously corresponds to $$(1.1)$$, with
$$
\begin{matrix}
A=\left[\begin{matrix}0&1/C\\-1/L&-R/L\end{matrix}\right],\\
B=\left[\begin{matrix}0\\1/L\end{matrix}\right],\\
u(t)=v_g(t)
\end{matrix}\tag{1.14}
$$

#### *Eigenvalues and Eigenvectors*
ln the remainder of this section, we will consider systems оf the form
$$
\dot{x}=Ax\tag{1.15}
$$

in which there are no external inputs (that іs, $$u=0$$). Since the dynamics of such systems depend primarily on $$A$$, the properties of this matrix need to be studied in some detail. We begin with the following definition.

### Definition 1.1,
A number $$\lambda_i$$, (which can be real or complex) is said to be all *eigenvalue* of $$A$$ if there is a nonzero vector $$y_i$$), such that
$$
Ay_{i}=\lambda_i{y}_i\tag{1.16}
$$

A vector $$y$$, that satisfies $$(1,16)$$ is referred to as an *eigenvector* that corresponds to $$\lambda_i$$

The computation of eigenvalues and eigenvectors is illustrated by the following example.

### Example 1.3.
Consider the linear system $$(1.15)$$ where
$$
\begin{align*}
A=\left[\begin{matrix}0&1\\-6&-5\end{matrix}\right]
\end{align*}\tag{1.17}
$$

If $$\lambda$$ is an eigenvalue of $$A$$, then equation
$$
\begin{align*}
(A-\lambda{I})y=0
\end{align*}\tag{1.18}
$$

must be satisfied for some nonzero vector $$y$$ (here I denotes the identity matrix).  Since system $$(1.18)$$ has a nontrivial solution if and only if
$$
\begin{align*}
\Delta(\lambda)=\det{\left(A-\lambda I\right)}=0
\end{align*}\tag{1.19}
$$

it follows that the eigenvalues of $$A$$ are actually the roots of polynomial $$\Delta(\lambda)$$. In our example, this polynomial has the form
$$
\begin{align*}
\Delta(\lambda)&=\lambda^2+5\lambda+6\\
&=(\lambda+2)(\lambda+3)
\end{align*}\tag{1.20}
$$

which implies that the eigenvalues are $$\lambda_1=-2$$ and $$\lambda_2=-3$$.

How can we determine the eigenvectors that correspond to $$\lambda_1$$ and $$\lambda_2$$? For $$\lambda_1=-2$$, $$(1.18)$$ becomes
$$
\begin{align*}
\left[\begin{matrix}2&1\\-6&-3\end{matrix}\right]\left[\begin{matrix}y_{11}\\y_{12}\end{matrix}\right]=\left[\begin{matrix}0\\0\end{matrix}\right]
\end{align*}\tag{1.21}
$$

which is a singular system of equations. This property becomes obvious after applying Gaussian elimination, which produces
$$
\begin{align*}
\left[\begin{matrix}2&1\\0&0\end{matrix}\right]\left[\begin{matrix}y_{11}\\y_{12}\end{matrix}\right]=\left[\begin{matrix}0\\0 \end{matrix}\right]
\end{align*}\tag{1.22}
$$

Observing that the second equation is satisfied for any choice of $$y_{11}$$ and $$y_{12}$$, we can set  $$y_{12}=t$$ (where $$t$$ is an arbitrary real number). Component $$y_{11}$$ can then be uniquely determined as
$$
y_{11}=-\frac{t}{2}\tag{1.23}
$$

The solution of $$(1.22)$$ has the general form
$$
y_{1}=t\left[\begin{matrix}-\tfrac{2}{2}\\1\end{matrix}\right]\tag{1.24}
$$

which suggests that there are actually *infinitely many* eigenvectors corresponding to $$\lambda_1$$ However, all of these eigenvectors are proportional to vector
$$
\overline{y}_{1}=\left[\begin{matrix}-\tfrac{1}{2}\\1\end{matrix}\right]\tag{1.25}
$$

which we will choose as the 'representative' for this set.

We can proceed in a similar way to obtain the eigenvector corresponding to $$\lambda_2=-3$$. In that case we have
$$
\begin{align*}
\left[\begin{matrix}3&1\\-6&-2\end{matrix}\right]\left[\begin{matrix}y_{21}\\y_{22}\end{matrix}\right]=\left[\begin{matrix}0\\0 \end{matrix}\right]
\end{align*}\tag{1.26}
$$

which becomes
$$
\begin{align*}
\left[\begin{matrix}3&1\\0&0\end{matrix}\right]\left[\begin{matrix}y_{21}\\y_{22}\end{matrix}\right]=\left[\begin{matrix}0\\0 \end{matrix}\right]
\end{align*}\tag{1.27}
$$

after Gaussian elimination. It is not difficult to verify that all the solutions of $$(1.27)$$ have the form
$$
y_{2}=t\left[\begin{matrix}-\tfrac{1}{3}\\1\end{matrix}\right]\tag{1.28}
$$

and that
$$
\overline{y}_{2}=\left[\begin{matrix}-\tfrac{1}{3}\\1\end{matrix}\right]\tag{1.29}
$$

can be taken as the representative eigenvector.

### *Linear Transformations and Jordan Canonical Forms*
A linear transformation represents a change of the coordinate system in which we view our model. To see what that means, let us introduce a new state vector
$$
z(t)=T^{-1}x(t)\tag{1.30}
$$

where $$T$$ is a given *transformation matrix*. Since
$$
x(t)=Tz(t)\tag{1.31}
$$

the original system $$(1.1)$$ can now be expressed as
$$
T\dot{z}=ATz+Bu\tag{1.32}
$$

Multiplying both sides on the left by $$T^{–1}$$, we obtain
$$
\dot{z}=\tilde{A}z+\tilde{B}u\tag{1.33}
$$

where
$$
\begin{matrix}
\tilde{A}=T^{-1}AT&&\text{and}&&\tilde{B}=T^{-1}BT
\end{matrix}\tag{1.34}
$$

A particularly useful coordinate transformation corresponds to the case when $$T$$ is formed from the eigenvectors of matrix $$A$$. To see why this is so, consider a $$2\times2$$ matrix $$A$$ with a pair of real, distinct eigenvalues $$\lambda_1$$ and $$\lambda_2$$. If $$y_1$$ abd $$y_2$$ are the associated eigenvectors, we have
$$
\begin{align*}
Ay_{1}&=\lambda_1y_1\\
Ay_{2}&=\lambda_2y_2
\end{align*}\tag{1.35}
$$

by definition. Forming matrix $$T$$ as
$$
\begin{align*}
T=\left[\begin{matrix}y_1&y_2\end{matrix}\right]
\end{align*}\tag{1.36}
$$

we obtain
$$
\begin{align*}
AT&=\left[\begin{matrix}Ay_1&Ay_2\end{matrix}\right]\\
&=\left[\begin{matrix}\lambda_1y_1&\lambda_2y_2\end{matrix}\right]\\
&=T\Lambda
\end{align*}\tag{1.37}
$$

where
$$
\begin{align*}
\Lambda=\left[\begin{matrix}\lambda_1&0\\0&\lambda_2\end{matrix}\right]
\end{align*}\tag{1.38}
$$

Since
$$
\tilde{A}=T^{-1}AT=\Lambda\tag{1.39}
$$

it follows that this transformation *diagonalizes* $$A$$. The elements of $$\Lambda$$ are the eigenvalues of $$A$$, and this matrix is referred to as the *Jordan canonical form* of $$A$$.

### Remark 1.1.
When the eigenvalues are complex or multiple, the Jordan canonical form becomes more complicated. It should be noted, however, that the main ideas developed in the following are easily extended to this case.

The Jordan canonical form can greatly simplify the solution of the state equations. Indeed, suppose that we are given a system like $$(1.15)$$ where $$A$$ is an $$n\times{n}$$ matrix with real, distinct eigenvalues. If we transform this system into the Jordan form
$$
\dot{z}=\Lambda{z}\tag{1.40}
$$

it is easily verified that $$(1.40)$$ now consists of $$n$$ decoupled scalar equations
$$
\begin{matrix}
\dot{z}_1=\lambda_1z_1\\\vdots\\
\dot{z}_n=\lambda_nz_n
\end{matrix}\tag{1.41}
$$

whose solutions are
$$
\begin{align*}
\begin{matrix}z_1(t)=z_1(0)e^{\lambda_{1}t}\\\vdots\\z_n(t)=z_n(0)e^{\lambda_{n}t}\end{matrix}
\end{align*}\tag{1.42}
$$

The overall solution vector can be represented in compact form as
$$
\begin{align*}
z(t)=\left[\begin{matrix}e^{\lambda_1t}&&\\&\ddots&\\&&&e^{\lambda_nt}\end{matrix}\right]z(0)
\end{align*}\tag{1.43}
$$

where $$z(0)=T^{-1}x(0)$$.

To see how $$(1.43)$$ appears in the original coordinates, we should recall that
$$
\begin{align*}
x(t)&=Tz(t)\\
&=\left[\begin{matrix}y_1&\cdots &y_{n}\end{matrix}\right]\left[\begin{matrix}e^{\lambda_1t}&&\\&\ddots&\\&&&e^{\lambda_nt}\end{matrix}\right]z(0)
\end{align*}\tag{1.44}
$$

which becomes
$$
\begin{align*}
x(t)=z_{1}(0)e^{\lambda_1t}y_{1}+\:\cdots\:+z_{n}(0)e^{\lambda_nt}y_{n}
\end{align*}\tag{1.45}
$$

after multiplication. A solution expressed in this form is often referred to *modal decomposition*. It has the advantage of explicitly showing how the system dynamics depend on the eigenvalues and eigenvectors of $$A$$.

### Example 1.4.
Let us determine the modal decomposition of System $$(1.15)$$ whose eigenvalues and eigenvectors were computed in **Example 1.3.** Using $$(1.25)$$ and $$(1.29)$$, we directly obtain
$$
\begin{align*}
x(t)&=Tz(t)\\
&=z_{1}(0)e^{-2t}\left[\begin{matrix}-1/2\\1\end{matrix}\right]+z_{2}(0)e^{-3t}\left[\begin{matrix}-1/3\\1\end{matrix}\right]
\end{align*}\tag{1.46}
$$

The initial conditions $$z_1(0)$$ and $$z_2(0)$$ can be related to $$x(0)$$ by observing that $$z(0)=T^{-1}x(0)$$, where
$$
T=\left[\begin{matrix}-1/2&-1/3\\1&1\end{matrix}\right]\tag{1.47}
$$

Since
$$
T^{-1}=\left[\begin{matrix}-6&-2\\6&3\end{matrix}\right]\tag{1.48}
$$

it follows that
$$
\begin{align*}
z_{1}(0)&=-6x_{1}(0)-2x_2(0)\\
z_{2}(0)&=6x_{1}(0)+3x_2(0)
\end{align*}\tag{1.49}
$$

### *Equilibria and Stability*
Any constant solution of $$(1.15)$$ is referred to as an *equilibrium* of the system. Since such a solution must satisfy
$$
Ax^e=0\tag{1.50}
$$

by definition, it follows that $$x^e=0$$ is a unique equilibrium whenever $$A$$ is a nonsingular matrix

### Definition 1.2.
Equilibrium $$x^e$$ is a global attractor if the solution satisfies
$$
\begin{matrix}
x(t)\to{x}^e&(t\rightarrow\infty)
\end{matrix}\tag{1.51}
$$

for any initial condition $$x(0)$$. Such an equilibrium is also said to be globally *asymptotically stable*.

Attractivity is a very important characteristic of any equilibrium. Recalling $$(1.45)$$, we can conclude that $$x^e=0$$ will have this property when all eigenvalues satisfy $$\lambda_i<0$$. It can be shown that a similar condition holds even if the eigenvalues are complex, in which case the requirement becomes $$\begin{matrix}\Re{(\lambda_i)}<0,&(i=1,\:2,\:\cdots,\:n)\end{matrix}$$.

If one or more eigenvalues satisfy $$\Re(\lambda_i)>0$$, $$x^e=0$$ does not attract the solutions any more. In that case, the equilibrium is said to be *unstable* (it can also be referred to as a *repeller*). The following example illustrates such a situation.

### Example 1.5.
Consider a system of the form $$(1.15)$$, in which
$$
A=\left[\begin{matrix}0.5&1.5\\1.5&0.5\end{matrix}\right]\tag{1.52}
$$

The eigenvalues of $$A$$ are $$\lambda_1=-1$$ and $$\lambda_2=2$$, and the corresponding eigenvectors are
$$
\begin{matrix}
y_{1}=\left[\begin{matrix}-1\\1\end{matrix}\right]&\text{and}&y_{2}=\left[\begin{matrix}1\\1\end{matrix}\right]
\end{matrix}\tag{1.53}
$$

Introducing $$z(t)=T^{-1}x(t)$$ where
$$
T=\left[\begin{matrix}-1&1\\1&1\end{matrix}\right]\tag{1.54}
$$

we obtain two decoupled equations
$$
\begin{align*}
\dot{z}_{1}&=-z_{1}\\
\dot{z}_{2}&=2z_2
\end{align*}\tag{1.55}
$$

with solution
$$
\begin{align*}
z_{1}(t)&=z_{1}(0)e^{-t}\\
z_{2}(t)&=z_2(0)e^{2t}
\end{align*}\tag{1.56}
$$

The model decomposition will therefore have the form
$$
x(t)=z_1(0)e^{-t}\left[\begin{matrix}-1\\1\end{matrix}\right]+z_2(0)e^{2t}\left[\begin{matrix}1\\1\end{matrix}\right]\tag{1.57}
$$

Since one of the exponents is positive, we can conclude that $$x(t)\to\infty&(t\to\infty)\end{matrix}$$ for almost all initial conditions.  What do we mean by 'almost all'?  To see this, it suffices to observe that there are some special initials conditions for which $$x(t)$$ still tends to $$x^e=0$$ when $$t\to\infty$$.  These initial conditions correspond to $$z_2(0)=0$$, since in that case
$$
x(t)=z_1(0)e^{-t}\left[\begin{matrix}-1\\1\end{matrix}\right]\tag{1.58}
$$

We can identify the set of all such initial conditions explicitly, by recalling that
$$
\begin{align*}
\left[\begin{matrix}z_1(0)\\z_2(0)\end{matrix}\right]&=T^{-1}\left[\begin{matrix}x_1(0)\\x_2(0)\end{matrix}\right]\\
&=\left[\begin{matrix}-0.5&0.5\\0.5&0.5\end{matrix}\right]\left[\begin{matrix}x_1(0)\\x_2(0)\end{matrix}\right]
\end{align*}\tag{1.59}
$$

The requirement then becomes
$$
z_2(0)=0.5x_{1}(0)+0.5x_2(0)=0\tag{1.60}
$$

which means that $$x(t)\to0$$ iff
$$
x_1(0)=-x_2(0)\tag{1.61}
$$

Condition $$(1.61)$$ defines a line in the $$x_1-x_2$$ space which is known as a *stable manifold*. All solutions starting on the manifold approach the equilibrium when $$t\to\infty$$, while solutions originating outside it increase unboundedly.
