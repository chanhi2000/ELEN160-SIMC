## 4.1 Special Relativity

Special relativity is concerned with the way in which physical processes appear to different observers. This problem dates back (at least) to Galileo, who was the first to mathematically connect observations made in reference systems that are in relative motion. The simplest way to introduce Galilean transformation is to consider a moving object which is observed from two different coordinate systems, $$A$$ and $$B$$, as shown in __Fig. 4.1__. One of these systems is assumed to be stationary, while the other moves with a constant velocity $$\vec{V}_R$$.

#### Fig. 4.1. Two coordinate systems in relative motion.
![fig4-01]()

Since
$$
\vec{r}_A(t)=\vec{r}_B(t)+\vec{R}(t)\tag{4.1}
$$

and $$\vec{R}(t)=\vec{V}_Rt$$, we have
$$
\vec{r}_A(t)=\vec{r}_B(t)+\vec{V}_R(t)\tag{4.2}
$$
In the one dimensional case, this simplifies to
$$
x_A(t)=x_B(t)+v_Rt
$$

It is important to recognize that from the Galilean perspective time is *identical* in the two coordinate systems (that is, $$t_A=t_B=t$$). Differentiating both sides of $$(4.3)$$ over time, we obtain
$$
v_A(t)=v_B(t)+v_R\tag{4.4}
$$

which leads to the conclusion that the velocity of the object will generally be *different* for the two observers. However, since
$$
\alpha_A(t)=\frac{dv_A}{dt}=\frac{dv_B}{dt}=\alpha_B(t)\tag{4.5}
$$

the acceleration will remain the same.
One of the most important characteristics of any coordinate transformation is quantities that remain *invariant* to it. It is not difficult to show that for Galilean transformations the distance between two objects exhibits this property. Indeed, if two coordinate systems move with a relative velocity $$v_R$$, the distance between objects $$P$$ and $$Q$$ can be expressed as
$$
\begin{align*}
x_A^{(p)}-x_A^{(q)}&=x_B^{(p)}+v_Rt-\left[x_B^{(q)}+v_Rt\right]\\
&=x_B^{(p)}-x_B^{(q)}
\end{align*}\tag{4.6}
$$

The preservation of distance allows us to introduce a common *metric* for all frames of reference. In three dimensions, this metric can be formulated in terms of the displacement between two nearby points as
$$
ds^2=dx^2+dy^2+dz^2\tag{4.7}
$$

### The Lorentz Transformation
Although the Galilean approach worked very well in the context of Newtonian mechanics, in the late 1800s it was observed that Maxwell's equations are not invariant to such transformations. This posed a conceptual problem, since basic electromagnetic phenomena ought to be unaffected by the relative motion of the observers. Einstein stated this principle explicitly in the form of two postulates:

### Postulate 1.
The laws of physics must be identical for all observers moving at constant velocities.

### Postulate 2.
The speed of light is the same for all observers moving at constant velocities.

In order for these two postulates to hold, it was necessary to introduce a new coordinate transformation under which Maxwell's equations would remain invariant. It turns out that this requirement is satisfied by the so-called *Lorentz transformation*, which is based on the assumption that two observers will record *different times* and *different spatial locations* for the same event. This is quite unlike the Galilean view, where it was assumed that all observers record the *same* time for an event (the difference being only in the spatial coordinates).

In describing the Lorentz transformation, we will consider two observers whose relative speed is $$v_R$$, and whose record of the same event is given in terms of spacetime coordinates $$(t_A,\:x_A)$$ and $$(t_B,\:x_B)$$, respectively (for simplicity, we will consider only one spatial dimension). In matrix form, the relationship between these coordinates is given as
$$
\begin{bmatrix}ct_B\\x_B\end{bmatrix}
=L\begin{bmatrix}ct_A\\x_A\end{bmatrix}\tag{4.8}
$$

where
$$
L=\Gamma
\begin{bmatrix}
1&-\tfrac{v_R}{c}\\
-\tfrac{v_R}{c}&1
\end{bmatrix}\tag{4.9}
$$

and
$$
\Gamma=\frac{1}{\sqrt{1-\tfrac{v_R^2}{c^2}}}\tag{4.10}
$$

We can rewrite $$(4.8)$$ and its inverse in a more explicit form as
$$
\begin{align*}
t_B&=\Gamma\left[t_A-\left(\tfrac{v_R}{c^2}\right)x_A\right]&t_A&=\Gamma\left[t_B-\left(\tfrac{v_R}{c^2}\right)x_B\right]\\
x_B&=\Gamma\left[-v_Rt_A+x_A\right]&x_A&=\Gamma\left[v_Rt_B+x_B\right]
\end{align*}\tag{4.11}
$$

Note that in the limiting case when $$v_R\ll{c}$$ (which is typical for Newtonia mechanics) we have $$\Gamma\approx1$$, which means that $$(4.11)$$ reduces to Galilean transformations. This is of fundamental importance, since it preserves the validity of results established by classical mechanics for low velocities.

The Lorentz transformation has an invariance property which has far reaching consequences. To see this, let us consider two events that are described by an observer A in terms of spacetime coordinates $$(t_A,\:x_A)$$ and $$(t_A+dt_A,\:x_A+dx_A$$ In the framework of observer B, the same two events have coordinates $$(t_B,\:x_B)$$ and $$(t_B+dt_B,\:x_B+dx_B)$$. From $$(4.8)$$ we directly obtain
$$
\begin{bmatrix}
cdt_B\\dx_B
\end{bmatrix}=
L\begin{bmatrix}
cdt_A\\dx_A
\end{bmatrix}\tag{4.12}
$$

?????ying that
$$
c^2dt^2_B-dx^2_B=
\begin{bmatrix}
cdt_B&dx_B
\end{bmatrix}
\begin{bmatrix}
1&0\\0&-1
\end{bmatrix}
\begin{bmatrix}
cdt_B\\dx_B
\end{bmatrix}\tag{4.13}
$$

?????at
$$
L^T\begin{bmatrix}
1&0\\0&-1
\end{bmatrix}L=
\begin{bmatrix}
1&0\\0&-1
\end{bmatrix}\tag{4.14}
$$

?We have
$$
c^2dt^2_B-dx^2_B=c^2dt^2_A-dx^2_A\equiv{d}s^2\tag{4.15}
$$

The quantity $$ds$$ is known as the *interval*, and is invariant under Lorentz tranformations.

Equation $$(4.15)$$ is of fundamental importance for special relativity. It points the fact that $$ds^2$$ represents a kind of distance measure (or metric) in spacetime ?? is *identical* in all reference frames. The four dimensional extension of
$$
ds^2=c^2dt^2-dx^2-dy^2-dz^2\tag{4.16}
$$

??? ents a metric that defines so-called *Minkowski spacetime*. In such a ???? the vector $$\begin{bmatrix}ct&x&y&z\end{bmatrix}^T$$ provides a natural representation for any given ???? the superscript $$T$$ dentoes the transpose of a matrix.

???? is important to recognize that the interval $$ds$$ depends on *local* cooordinates ???? and is independent of the relative motion of the two reference frames. This ???? us to introduce the notion of *proper time* as
$$
d\tau=\frac{ds}{c}\tag{4.17}
$$

???? time defined in this way is a quantity that is common to *all* observers, ???? can be computed directly from $$(4.16)$$ as
$$
d\tau^2=dt^2-\frac{1}{c^2}\left(dx^2+dy^2+dz^2\right)\tag{4.18}
$$

???? arbitrary frame of reference. This definition also allows us to express the ???? Minowski metric in a slightly more convenient way, as
$$
c^2d\tau^2=c^2dt^2-dx^2-dy^2-dz^2\tag{4.19}
$$

It should be noted that the spacetime metric defined in $$(4.16)$$ is rather unusual, since it allows for the possibility that $$ds^2<0$$ (which would correspond to something like a “complex distance”). In a typical three dimensional Euclidean space this is mot possible, since the metric has the form
$$
ds^2=dx^2+dy^2+dz^2\tag{4.20}
$$

where all signs are *positive*. The space described in $$(4.20)$$ is said to have *signature* $$(+,\:+,\:+)$$, which is quite unlike the Minkowski space whose signature is $$(+,\:-,\:-,\:-)$$. This is an important property, which defines the scalar product of vectors $$x=\begin{bmatrix}x_1&x_2&x_3&x_4\end{bmatrix}^T$$ and $$y=\begin{bmatrix}y_1&y_2&y_3&y_4\end{bmatrix}^T$$ in sapcetime as
$$
x\cdot{y}=x_1y_1-x_2y_2-x_3y_3-x_4y_4\tag{4.21}
$$

The Minkowski spacetime is said to be *flat*, since the metric $$(4.16)$$ has constant coeffcients $$(c^2,\:-1,\:-1,\:-1)$$ next to the differential terms. In an $$n$$-dimensional *curved* space, $$ds^2$$ would have a more general from
$$
ds^2=\sum_{i,\:j}{g_{i,j}(x)dx_idx_j}\tag{4.22}
$$

where the coefficients in the metric vary from point to point (there is also the possibility of cross product terms $$dx_i$$, $$dx_j$$). One of the immediate conseqeunces of the "flatness" of Minkowski spacetime is the fact that the shortest distance between two points is a straight line. This is not the case with curved spaces, as will become apparent in __Section 4.2__

The following two examples illustrate the profound way in which Loretnz transformation alter our conventional ideas about time and space.

### Example 4.1.
