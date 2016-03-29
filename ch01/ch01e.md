## 1.5 Routes to Chaos

In this section we will consider three different mechanisms through which chaos can arise. In all cases, we will observe how the system behavior changes as one more parameters are varied. Bifurcation diagrams will prove to be a very useful tool for this purpose.

### The Period-Doubling Route
Consider a system with a stable limit cycle of period $$T$$. For a given parameter value $$p$$, the amplitude of the periodic solution can be represented as the uniform uence shown in __Fig. 1.46__. In the bifurcation diagram, this sequence would obviously correspond to a single point, since all maxima are equal to $$1$$.

As the parameter is increased beyond some value $$p_1$$, the situation shown in __Fig. 1.47__ can arise. The new waveform is still periodic, but its period is now $$2T$$, due to the variations in amplitude. Since the steady state solution now has two different peak values, the bifurcation diagram “splits' in the manner shown in __Fig. 1.48__.

#### Fig. 1.46. Peak values for a limit cycle with a single amplitude.
![fig1-46]()

#### Fig. 1.47. Peak values for a limit cycle with two amplitudes.
![fig1-47]()

#### Fig. 1.48. Splitting of the bifurcation diagram.
![fig1-48]()


The ‘period-doubling’ bifurcation described above can occur again for some $$p=p_2$$, at which point the peak values in the system have the form shown in __Fig. 1.49__. The period becomes $$4T$$, and the bifurcation diagram splits into four branches, as in __Fig. 1.50__.
__Fig. 1.49__. Peak values for a limit cycle with four amplitudes.

#### Fig. 1.49. Peak values for a limit cycle with four amplitudes.
![fig1-47]()

#### Fig. 1.50, Bifurcation diagram with two splits.
![fig1-50]()

It is well known that a cascade of period-doubling bifurcations can ultimately lead to chaos. This phenomenon has been observed in a wide variety of models, including several that we already considered. A typical example of this phenomenon is shown in __Fig 1.51__.

#### Fig. 1.51. The bifurcation diagram for a chaotic system.
![fig1-51]()

A rigorous examination of conditions under which period-doubling occurs is not possible at this time, since the underlying math is far too complicated. Nevertheless, a simple (and admittedly crude) one dimensional model can provide considerable insight into what is really going on. To that effect, let us assume that any two successive maxima of our trajectory are related as
$$
x_{k+1}=f(x_k)=px_k(1-x_k)\tag{1.159}
$$

How one can come up with such an equation in general remains something of a mystery. What is important, however, is that this is a simple scalar *difference equation* which accounts for parameter variations, and allows us to easily plot the maxima as a function of $$p$$. To illustrate this point, let us set $$p=2$$ and pick $$x_1=0.2$$ as the initial point. Following $$(1.159)$$, we easily obtain the sequence shown in __Fig. 1.52__, which clearly indicates that there is a single steady state amplitude $$x^e=0.5$$.

#### Fig. 1.52. The sequence for $$x_1=0.2$$.
![fig1-52]()

A more intuitive way of looking at equation $$(1.159)$$ would be to generate the sequence $$\{x_k\}$$ in the manner shown in __Fig. 1.53__. In this figure we plotted two separate functions: $$x_{k+1}=px_k(1-x_k)$$ and $$x_{k+1}=x_k$$. The intersection points represent the equilibria of system $$(1.159)$$, since they satisfy the condition
$$
x^*=f(x^*)\tag{1.160}
$$

#### Fig. 1.53. A schematic approach for generating the sequence.
![fig1-53]()

It is not difficult to show that equilibrium $$x^*=0$$ is unstable, while the one corresponding to $$x^*=0.5$$ is stable. Indeed, a simple inspection of __Figs. 1.54__ and __1.55__ shows that the stability of the equilibrium depends exclusively on the slope of $$f$$ at the intersection point. If the magnitude of slope is $$<1$$ (as in __Fig. 1,54__), the equilibrium is stable; if not, the intersection point is a repeller.

#### Fig. 1.54. The sequence for a slope $$<1$$.
![fig1-54]()

#### Fig. 1.55. The sequence for a slope $$>1$$.
![fig1-55]()

Let us now see what happens when $$p$$ is increased to $$p=3.3$$. In this case, the graphical method gives rise to the situation shown in __Fig. 1.56__, which suggests at there are two alternating maxima in the steady state. This is consistent with the amplitude splitting model shown in __Fig. 1.48__, and indicates that a period-doubling bifurcation has occurred.

#### Fig. 1.56. A schematic representation of the two-amplitude case.
![fig1-56]()

A further illustration of this phenomenon is provided in __Fig. 1.57__, for $$p=3.53$$. In this case, the solution has period $$4T$$, with *four* distinct maxima.

#### Fig. 1.57. A schematic representation of the four-amplitude case.
![fig1-57]()

To verify that this mechanism leads to chaos, let us consider system $$(1.159)$$ when $$p$$ is increased to $$p=3.9$$. The situation that corresponds to this case is shown in __Fig. 1.58__, which has all the characteristics of chaotic behavior (no periodicity or convergence, bounded maxima).

#### Fig. 1.58. A schematic representation of the chaotic case.
![fig1-58]()

### *The Quasi-Periodic Route*
Suppose that the system has a stable limit cycle of period T for parameter value satisfying $$p\leq{p}_0$$. As noted earlier, a *generalized* Hopf bifurcation associated with this cycle can give birth to a *second* limit cycle, whose frequency is $$\omega_2\neq\omega_1$$.

If the two frequencies turn out to be incommensurate, the attractor becomes quasi-periodic with two independent frequencies. This type of Hopf bifurcation can reoccur for some $$p=p_1$$, giving rise to a third limit cycle of period $$\omega_3$$. If $$\omega_3$$ is incommensurate with $$\omega_2$$ and $$\omega_1$$,we ultimately arrive at a quasi-periodic attractor consisting of three frequencies.

It turns out that the stability of such a system can be very fragile, and that chaotic behavior can be triggered by a small perturbation. This sequence of events was theoretically predicted by Ruelle and Takens in 1971,[^6] and was subsequently observed experimentally both in fluid dynamics and in electronic circuits.[^7]

### *The Intermittent Route*
The third route to chaos is rather direct, and doesn't require multiple bifurcations. To see why this route is associated with 'intermittency', let us assume that there is a limit cycle of period $$T$$ for parameter values $$p\leq{p}_1$$. As we pass $$p_1$$, there will be sudden short bursts of aperiodic behavior followed by relatively long periods of regular oscillations (the oscillations are not strictly periodic, but are very close). This type of behavior is illustrated in __Fig. 1.59__. Note that as $$p$$ moves further away from $$p_1$$, the intermittent chaotic bursts become longer and longer, until all traces of periodic behavior vanish.

#### Fig. 1.59. An illustration of intermittent behavior.
![fig1-59]()

The intermittent route to chaos has a nice interpretation in terms of discrete one dimensional models. To see that, let us assume once again that successive maxima of the trajectory satisfy equation $$(1,159)$$. However, this time we will not plot $$x_{k+1}$$ versus $$x_k$$, but rather $$x_{k+3}$$ (that is, every *third* maximum). Such a plot is easily generated from $$(1.159)$$, and is shown in __Fig. 1.60__ for $$p=3.87$$.

#### Fig, 1.60. The schematic representation for $$p=3.87$$.
![fig1-60]()

The plot in __Fig. 1.60__ indicates six points of intersection, three of which have slopes $$<1$$ in magnitude (and are therefore attractors). Since we are plotting $$x_{k+3}$$ versus $$x_k$$, each of the three fixed points corresponds to a different amplitude (the values are $$x^*=0.16$$, $$x^*=0.51$$, and $$x^*=0.95$$, respectively).

Let us now consider a slightly smaller value of $$p$$, such as $$p=3.82$$. The plot that corresponds to this case is shown in __Fig. 1.61__, and a closer inspection reveal that there are no more stable fixed points (the only remaining intersections have slopes $$>1$$).

#### Fig. 1.61. The schematic representation for $$p=3.82$$.
![fig1-62]()

This obviously means that no periodic solutions exist. However, if we magnify the section of the curve close to the straight line (as shown in __Fig. 1.62__), we notice that $$x_k$$ can spend a considerable amount of time in the 'gap' where $$x_{k+3}\approx{x}_k$$. During such intervals, the solution is almost periodic. Once trajectory leaves the gap, it roams around freely until it becomes trapped in the gap again. Based on this model, it is natural to associate the ‘free roaming‘ intervals with the short aperiodic bursts, and the intervals corresponding to the gap with almost periodic behavior. Of course, as the curve moves away from the line, $$x_k$$ spends less and less time in the gap, until the solution becomes completely aperiodic.

#### Fig. 1.62. A schematic explanation for intermittent aperiodic behavior.
![fig1-62]()

[^6]: D. Ruelle and T. Takens, “On the nature of turbulence,” *Communications in Mathematical Physics*, 20, pp. 167-192, 1971.
[^7]: P. Linsay and A. Cumming, “Three-frequency quasiperiodicity, phase locking and the onset of chaos,” *Physica D*, 40, pp. 196-217, 1989.

