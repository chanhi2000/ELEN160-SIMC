## 3.4 Group Theory and Supersymmetry

The final section of this chapter is devoted to the motion of symmetry, which plays a vital role in quantum mechanics (as well as in particle physics and string theory). The principal tool for studying this property is *group theory*, whose main ideas will be outlined in the following. Although this outline is very limited and simplified, it should hopefully provide the reader with a sense of H, symmetry is formally incorporated into modern physics.[^5]

### Symmetry Groups
To gain a basic understanding of what is meant by a *symmetry group*, consider the square shown in __Fig. 3.3__. What types of transformations will leave this object unchanged?

#### Fig. 3.3. The Square and its axes of symmetry.
![fig3-03]()

The square will obviously remain invariant to rotations around the origin by $$0^\circ$$, $$90^\circ$$, $$180^\circ$$ and $$270^\circ$$. It is also unchanged when reflected (or “flipped”) around the four axes indicated in __Fig. 3.3__.

A convenient way of representing these eight ‘symmetry preserving' oper tions is to view vertices $$\{a,\:b,\:c,\:d\}$$ as points in the complex plain. The original configuration can then be represented as a complex vector
$$
z=\left[\begin{matrix}a\\b\\c\\d\end{matrix}\right]
=\left[\begin{matrix}1\\i\\-1\\-i\end{matrix}\right]\tag{3.84}
$$

It is not difficult to see that a rotation of the square by $$90^\circ$$ is equivalent to multiplying $$z$$ by the imaginary unit. Indeed, the new vector
$$
w=iz=\left[\begin{matrix}a\\b\\c\\d\end{matrix}\right]=\left[\begin{matrix}i\\-1\\-i\\1\end{matrix}\right]\tag{3.85}
$$

corresponds to the reordering of vertices shown in __Fig. 3.4__. In a similar way, it can be shown that rotations by $$180^\circ$$ and $$270^\circ$$ correspond to $$w=-z$$ and $$w=-iz$$, respectively.

#### Fig. 3.4. The square after rotation.
![fig3-04]()

Reflections around the horizontal and vertical axes can be represented in terms of the complex conjugate of $$z$$ (in the following, we will use the symbol $$C$$ to denote this operation). For the horizontal axis, we have
$$
w=Cz=\left[\begin{matrix}1\\-i\\-1\\i\end{matrix}\right]\tag{3.86}
$$

which produces the ordering of vertices shown in __Fig. 3.5__ (note that the operation $$-Cz$$ corresponds to a reflection around the vertical axis).

### Fig. 3.5. The square after reflection around the horizontal axis.
![fig3-05]()

Reflections around the remaining two axes are somewhat more complicat and require a *composite* operation. This operation consists of multiplication by $$i$$, followed by complex conjugation:
$$
w=C(iz)
=C\left[\begin{matrix}i\\-1\\-i\\1\end{matrix}\right]
=\left[\begin{matrix}-i\\-1\\i\\1\end{matrix}\right]\tag{3.87}
$$

The resulting arrangement is shown in __Fig. 3.6__. Following the same procedure, it is easily verified that the operation
$$
w=-C(iz)
=C\left[\begin{matrix}i\\1\\-i\\-1\end{matrix}\right]\tag{3.88}
$$

corresponds to the reflection shown in __Fig. 3.7.__

#### Fig. 3.6. Reflection around one of the diagonal axes.
![fig3-06]()

#### Fig. 3.7. Reflection around the other diagonal axis.
![fig3-07]()

### The Formal Definition of a Group
The collection of eight transformations
$$
G=\{g_1,\:\cdots,\:g_8\}=\left\{1,\:i,\:-1,\:-i,\:C,\:-C,\:Ci,\:-Ci\right\}\tag{3.89}
$$

represents what is known as a *group*. Since these operation leave the original object unchanged, they are usually referred to as a *symmetry group*.

From a formal standpoint, a group can be viewed as a collection of mathematical operations with the following properties.

### Property 1.
The successive application of two group members, $$g_i$$ and $$g_j$$, defines the operation of *multiplication* in the group. The resulting element $$g=g_ig_j$$, must also be a member of the group.

### Example 3.6.
Consider the successive application of $$g_2=i$$ and $$g_7=Ci$$, both of which belong to group $$G$$. The resulting operation is
$$
w=g_2g_7z=g_2\left[\begin{matrix}-i\\-1\\i\\1\end{matrix}\right]
=\left[\begin{matrix}1\\-i\\-1\\i\end{matrix}\right]\tag{3.90}
$$

It is easily verified that the same w can be obtained by applying $$g_4=C$$
$$
w=g_4z=\left[\begin{matrix}1\\-i\\-1\\i\end{matrix}\right]\tag{3.91}
$$
In other words, we have that $$g_2g_7=g_4$$, and $$g_4\in{G}$$.

### Property 2.
The operation of multiplication is *associative*:
$$
(g_i,g_j)g_k=g_i(g_jg_k)\tag{3.92}
$$

### Property 3.
The group must have an *identity element*, $$I$$, such that
$$
gI=g\tag{3.93}
$$

for all $$g\in{G}$$. In our group $$g_1=1$$ is obviously such an element.

### Property 4.
Each element in the group must have an *inverse element*, $$g_i^{-1}\in{G}$$, which satisfies
$$
g_ig_i^{-1}=I\tag{3.94}
$$

As an illustration, consider element $$g_4=-i$$ of group G. Since $$g_4i=1$$, it obviously follows that $$g_4^{-1}=i=g_2$$, which is also an element of the group.

### Subgroups and the Abelian Property
Subgroups play a significant role in particle physics and unification theories. A subgroup is simply a subset of the original group, which constitutes a group in its own right. In the case of group $$G$$ defined in $$(3.89)$$, typical examples would be
$$
S_1=\left\{1,i,-1,-i\right\}\tag{3.95}
$$

or
$$
S_2=\left\{1,-1,C,-C\right\}\tag{3.96}
$$

It is easily verified that the elements of $$S_1$$ and $$S_2$$ satisfy __Properties 1-4__.

Subgroups often have special properties that the whole group does not. For example, not all elements of group $$G$$ satisfy
$$
g_ig_j=g_jg_i\tag{3.97}
$$

Indeed, if we were to test this property on elements $$g_5=C$$ and $$g_2=i$$, we would obtain
$$
g_5g_2=Ci=-iC=-g_2g_5\tag{3.98}
$$

which is a violation of $$(3.97)$$. However, if we focus on subgroup $$S_1$$ only, $$(3.97)$$ does hold for all $$g_i$$, $$g_j\in{S}_1$$. We refer to subgroups with such a property as *Abelian groups* (after the Norwegian mathematician Niels Abel).

### Representation of a Finite Group
When dealing with simple objects such as the square in __Fig. 3.3__, the symmetry preserving transformations can be represented by elementary mathematical operations such as multiplication by a complex number or conjugation. However, for more complicated and abstract objects, such a representation is usually inadequate. A possible way to describe a general finite group is to associate matrices $$T(g_1),\:T(g_2),\:\cdots{T}(g_n)$$ with each of its members. For this to be a legitimate representation, the matrices have to preserve the multiplication law of the original group. In other words, for any two elements $$g_i,\:g_j\in{G}$$, we must have
$$
T(g_i)T(g_j)=T(g_ig_j)\tag{3.99}
$$

How can we construct matrices that conform to $$(3.99)$$? A simple way to do this is to label the rows and columns of $$T(g_k)$$ as
$$
T(g_k)=
\begin{matrix}
\begin{array}{cccc}
&\phantom{2}g_1&\phantom{2}g_2&\cdots&\phantom{2}g_n
\end{array}\\
\begin{matrix}
g_1\\g_2\\\vdots\\g_n
\end{matrix}
\begin{bmatrix}
t_{11}&t_{12}&\cdots&t_{1n}\\
t_{21}&t_{22}&\cdots&t_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
t_{n1}&t_{n2}&\cdots&t_{nn}
\end{bmatrix}
\end{matrix}\tag{3.100}
$$


and define its elements as
$$
t_{ij}=
\begin{cases}
1,&\text{if  }g_ig_j^{-1}=g_k\\
0,&\text{otherwise}
\end{cases}\tag{3.101}
$$

It is not difficult to verify that this construction secures the validity of $$(3.99)$$.

### Example 3.7.
In the following, we will show that $$(3.99)$$ holds for the representation of subgroup $$S_1\{1,\:i,\:-1,\:–i\}$$. In order to do this, let us (arbitrarily) pick $$g_2=i$$ and $$g_3=-1$$, and form matrices
$$
T(g_2)=
\begin{matrix}
\begin{array}{cccc}
\phantom{6}&\:\:1&\phantom{8}\:\:i&\:\:-1&\:\:-i\phantom{6}
\end{array}\\
\begin{matrix}
1\\i\\-1\\-i
\end{matrix}
\begin{bmatrix}
\phantom{4}0\phantom{4}&\phantom{4}0\phantom{4}&\phantom{4}0\phantom{4}&\phantom{4}1\phantom{4}\\
1&0&0&0\\
0&1&0&0\\
0&0&1&0
\end{bmatrix}
\end{matrix}\tag{3.102}
$$

and
$$
T(g_3)=
\begin{matrix}
\begin{array}{cccc}
\phantom{6}&\:\:1&\phantom{8}\:\:i&\:\:-1&\:\:-i\phantom{6}
\end{array}\\
\begin{matrix}
1\\i\\-1\\-i
\end{matrix}
\begin{bmatrix}
\phantom{4}0\phantom{4}&\phantom{4}0\phantom{4}&\phantom{4}1\phantom{4}&\phantom{4}0\phantom{4}\\
0&0&0&1\\
1&0&0&0\\
0&1&0&0
\end{bmatrix}
\end{matrix}\tag{3.103}
$$

Since $$g_2g_3=-i=g_4$$, and
$$
T(g_4)=
\begin{matrix}
\begin{array}{cccc}
\phantom{6}&\:\:1&\phantom{8}\:\:i&\:\:-1&\:\:-i\phantom{6}
\end{array}\\
\begin{matrix}
1\\i\\-1\\-i
\end{matrix}
\begin{bmatrix}
\phantom{4}0\phantom{4}&\phantom{4}1\phantom{4}&\phantom{4}0\phantom{4}&\phantom{4}0\phantom{4}\\
0&0&1&0\\
0&0&0&1\\
1&0&0&0
\end{bmatrix}
\end{matrix}\tag{3.104}
$$

it is easily verified that
$$
T(g_2)T(g_3)=T(g_2g_3)=T(g_4)\tag{3.105}
$$

holds.

It is important to recognize that symmetry groups can be finite or *continuous*. Group $$G$$ described in (3.89) is obviously finite, since it contains only eight elements. An example of a continuous group would be the rotation of a circle around its center. In this case, rotation by *any* angle α leaves the object unchanged. Furthermore, since successive rotations by angles $$\alpha$$ and $$\beta$$ are equivalent to a single rotation by angle $$\alpha+\beta$$, it is not difficult to show that this set constitutes a group. Continuous groups are very common in quantum mechanics, particularly in quantum field theory. The mathematical framework that provides a description for such groups is known as *Lie algebra*, after Norwegian mathematician Sophus Lie.

### Supersymmetry
A proper examination of group theory and its role in modern physics clearly lies beyond the scope of this book, since it requires a much more advanced mathematical background than the one we have provided. Nevertheless, I feel it is instructive to close this chapter with an example which illustrates how group theory is used in quantum mechanics. Although our discussion will be brief and informal, it should nevertheless provide the reader with some important insights on this subject.

Our focus in the following will be on quantum field theory, which provides the necessary conceptual framework for particle physics. This theory make extensive use of symmetry groups, which allow us (among other things) to mathematically transform one set of particles into another. One of the main difficulties that is encountered in this context stems from the fact that conventional symmetry groups (of the sort that we discussed) do *not* allow us to transform bosons into fermions, and vice versa. This restriction poses a major theoretical challenge, since it often leads to results that make no physical sense (such as infinite probabilities, for example).

A possible way to circumvent this problem is to modify the standard properties of a group, and expand the rules of Lie algebra so that they satisfy both anticommutation and commutation laws. Such extensions have led to generalized concepts such as *supergroups* and *supersymmetry*, which allow us to eliminate the troublesome infinities. This becomes possible once each fermion is assigned a bosonic *superpartner*[^6] (and vice versa), whose presence largely neutralizes the underlying mathematical difficulties. The idea that all known particles have “superpartners” may perhaps sound strange, but it is widely accepted by physicists (although the existence of such entities has yet to be confirmed experimentally).[^7]

Perhaps the most striking consequence of supersymmetry is the possibility that the electromagnetic, strong nuclear and weak nuclear forces could be indistinguishable at very high energies. Models that do not incorporate supersymmetry lack such unifying power, and predict instead that the strengths of the three forces would be similar, but not *identical*. This is clearly a prospect that most theoretical physicists find thoroughly unappealing (both aesthetically and philosophically). We should add in this context that aesthetic considerations are taken very seriously in Science, since they are often our best criterion for evaluating hypotheses that cannot be verified experimentally. Unification theories certainly fall into that category, since the energy levels required to test them are impossible to reproduce (it is believed that such extreme physical conditions existed only in the immediate aftermath of the Big Bang).

[^5]: There are a number of excellent introductory texts on group theory. Some suggestions for further reading are provided below:
1. Morton Hammermesh, *Group Theory and Its Applications to Physical Problems*, Dover Publications, 1990.
2. Derek Robinson, *A Course in the Theory of Groups*, Springer-Verlag, 1996.
3. Roy McWeeny, Symmetry: *An Introduction to Group Theory and Its Applications*, Dover Publications, 2002.

[^6]: Some examples of Superpartner pairs are: *electron-selectron*, *photon-photino*, and *neutrino-sneutrino*.
[^7]: Scientists hope that the Large Hadron Collider (LHC) may be a resolve some of these issues. As the world’s largest particle accelera the LHC could potentially provide the energy levels needed to confirm the existence of superpartners.

