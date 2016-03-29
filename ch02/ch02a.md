## 2.1 An Introduction to Formal Systems

A formal system can be fully defined by a set of axioms and two types of rules:
- __RULES OF FORMATION__, which determine whether or not a string of symbol is a legitimate member of the system.
- __RULES OF INFERENCE__, which provide the basis for generating new theorems from axioms and already existing theorems.

To illustrate the main properties of such systems, let us once again consider so-called $$\text{PQ}$$ system[^1], which consists of three types of symbols — letters $$\text{P},\:\text{Q}$$, and strings of hyphens. The rules and axioms of this system can be described in the following manner.
### *Rule of Formation.*

Any string of the type
$$
x\:P\:y\:Q\:z\tag{2.1}
$$

where $$x$$, $$y$$ and $$z$$ represent sequences of one or more hyphens is a member of this system (we will refer to it as a *well-formed string*).

### *Axioms.*
Every string of the type
$$
x\:P-Q\:x-\tag{2.2}
$$

where $$x$$ is a sequence of hyphens is an axiom.

### *Rules of Inference.*
If
$$
x\:P\:y\:Q\:z\tag{2.3}
$$

is a theorem, then
$$
x\:P\:y-Q\:z-\tag{2.4}
$$

is also a theorem.

Two remarks are in order before we proceed.

### Remark 2.1.
The rule of formation implies that not every combination $$P$$, $$Q$$ and hyphens is a member of this system. For example,
$$
---P--Q---\tag{2.5}
$$

is a well-formed string, but
$$
---P\:Q---\tag{2.6}
$$

or
$$
-P-Q-P\tag{2.7}
$$

are not.

### Remark 2.2.
The $$\text{PQ}$$ system has infinitely many axioms, since $$x$$ can any sequence of hyphens.

The theorems of the $$\text{PQ}$$ system can be automatically generated from the axioms, by applying the rule of inference. For instance, starting with axiom
$$
--P-Q---\tag{2.8}
$$

we can generate the following theorem
$$
--P--Q----\tag{2.9}
$$
Applying the rule of inference again, we get
$$
--P---Q-----\tag{2.10}
$$

and so on. It would be rather straightforward to program a computer to generate theorems in this manner. Note, however, that such a program would obviously never terminate, since there are infinitely many axioms and boundless possibities to produce theorems from them.

In the following, we will use this simple example to introduce two fundamental properties that characterize any formal system—*internal consistency* and *completeness*. These properties will now be described in greater detail, as will some of their most important implications, Such an analysis will provide the necessary background for understanding Gödel's Incompleteness Theorem and its consequences.

### Internal Consistency
A key problem facing any formal system is the verification of *internal consistency*. The main issue that arises in this context is summarized by the following question: How can one be sure that the rules of inference don’t produce two theorems that contradict each other? Answering such a question can be a formidable task, even in simple cases. The problem is compounded by the fact that consistency can be defined in a number of different ways (which are equivalent for most reasonable systems, but are not identical in general).

We begin with a definition that assumes that the system has some form of *negation* built into its structure.

### Definition 2.1.
A formal system is said to be internally consistent if there is no well formed string $$P$$ such that both $$P$$ and its negation, $$\sim{P}$$, are theorems.

Proofs of consistency in the sense of __Definition 2.1__ can be very difficult. If we attempted to do this *within* the formal system, our only option would be to generate theorems until we find two that stand in logical opposition. In this way, we might be able to establish *inconsistency* in a finite number of steps (if we are very, very fortunate). Consistency, however, can never be verified in this manner, since infinitely many theorems need to be examined. It follows, therefore, that a proof of consistency requires reasoning that *transcends* the formal system.

One possible approach to this problem would be to consider an alternative definition of consistency, which is based on the notion of an *interpretation*. An interpretation can be viewed as a mapping that “translates” all the statements about a particular formal system $$S$$ into statements about some other (preferably more manageable) system $$M$$.

### Definition 2.2.
A formal system is said to be internally consistent if there exists an interpretation in which every one of its theorems translates into a true statement

In order to frame __Definition 2.2__ in slightly more technical terms, let $$\Phi$$ denote the mapping from $$S$$ into a model system $$M$$, and assume that $$\Phi(S)=W\subset{M}$$. This is equivalent to saying that all the statements of $$S$$ map into a *subset* of statements about $$M$$. If we now demote all the theorems contained in $$S$$ and $$W$$. by $$T_S$$ and $$T_M$$, respectively, then consistency requires
$$
\Phi(T_s)\subset{T_M}\tag{2.11}
$$

Condition $$(2.11)$$ is illustrated in __Fig. 2.1__, which schematically shows how every theorem of $$S$$ must “translate” into a theorem of $$M$$ in order for $$S$$ to be a consistent system.[^2]

#### Fig. 2.1. A schematic illustration of consistency.
![fig2-01]()

To see the practical value of __Definition 2.2__, let us assume that $$P$$, $$Q$$ and sequences of hyphens are interpreted in the following way:
$$
\begin{matrix}
\text{Symbol}&\text{Interpretation}\\
P&+\\Q&=\\-&1\\--&2\\---&3\\\vdots&\vdots
\end{matrix}\tag{2.12}
$$

According to $$(2.12)$$, every one of our axioms can now be translated into a statement of the form
$$
N+1=N+1\tag{2.13}
$$

which is clearly a truth about integers. Furthermore, under this interpretation the rule of inference preserves the truth of the statement. To see this more clearly, recall that if $$x\:P\:y\:Q\:z$$ is a theorem, then a $$x\:P\:y-Q\:z-$$ must be a theorem as well. This property obviously extends to the translations of these statements, since the truth of a $$x+y=z$$ implies the truth of $$x+y+1=z+1$$. Since all theorems are derived using this rule of inference, we can claim that the $$\text{PQ}$$ system is internally consistent.

Although the consistency proof proposed above is very simple, it is important to recognize that its logical validity *does not* follow exclusively from the properties of the $$\text{PQ}$$ system. Instead, it requires a certain amount of *external* reasoning as well, which relies on verifiable facts from elementary number theory. This is a pattern that we will encounter in all subsequent application of __Definition 2.2__.

### Completeness
A related (and equally important) problem associated with a formal system amounts to establishing whether or not it is *complete*. As in the case of consistency, here too there are a number of possible definitions, two of which we provide below.

### Definition 2.3.
A formal system is said to be complete if for any well formed string $$P$$, either $$P$$ or its negation, $$\sim{P}$$, is a theorem.

According to this definition, a system is *incomplete* if neither $$P$$ nor $$\sim{P}$$ are theorems. If such a proposition $$P$$ exists, it is said to be *undecidable* (this is a notion that Gödel used extensively in establishing his results).

An alternative definition of completeness is a *relative* one, and is provided with respect to a given interpretation.

### Definition 2.4.
A formal system $$S$$ is complete with respect to a given terpretation if every truth that is expressible in $$S$$ is also a theorem.

In terms of our previous notation, the completeness of $$S$$ with respect to a model system $$M$$ entails
$$
\Phi(T_S)=T_M\tag{2.14}
$$

which is a stronger condition than $$(2.11)$$. What $$(2.14)$$ requires is that every theorem (*i.e.* true statement) in $$M$$ that can be translated into a statement in $$S$$ corresponds to a theorem in $$S$$. To better understand what this means, consider the scenario where there exists a theorem $$t_0$$ in $$T_M$$ that maps into some $$p\notin{T}_S$$. In that case, system $$S$$ would be *incomplete* with respect to this interpretation (a schematic illustration of such a situation is provided in __Fig. 2.2__).[^3]

#### Fig. 2.2. A schematic illustration of incompleteness.
![fig2-02]()

In the case of the $$\text{PQ}$$ system and the interpretation proposed in $$(2.12)$$, the problem of completeness reduces to the following question: Is every expressible truth about adding two integers also a theorem? It turns out that this is indeed the case. To see that, consider three arbitrary integers $$a$$, $$b$$ and $$c$$ that satisfy
$$
a+b=c\tag{2.15}
$$

(this is the only type of algebraic formula that can be represented in the $$\text{PQ}$$ system using our interpretation). If we start with axiom
$$
x\:P-Q\:x-\tag{2.16}
$$

where $$x$$ is a string of a hyphens and apply the rules of inference $$b-1$$ times, we will obtain
$$
x\:P\:y\:Q\:z\tag{2.17}
$$

Theorem $$(2.17)$$ obviously corresponds to expression $$(2.15)$$, since $$x$$, $$y$$ and $$z$$ are strings consisting of $$a$$, $$b$$ and $$c=a+b$$ hyphens, respectively. The proposed interpretation of the symbols thus allows us to prove both the completeness and the internal consistency of the $$\text{PQ}$$ system.

### The Modified PQ System
The fact that the consistency and completeness of a formal system (in the sense of __Definitions 2.2__ and __2.4__) can be established using an interpretation of the symbols suggests that these properties needn't be absolute. To get an idea of some of the issues that arise in this context, let us consider a modified version of the $$\text{PQ}$$ system, in which we introduce a second set of axioms:

### AXIOM SCHEME 2.
Every string of the type
$$
x\:P-Q\:x\tag{2.18}
$$

is also an axiom.

Under the old interpretation of the symbols, the axiom
$$
-P-Q-\tag{2.19}
$$

would be interpreted as
$$
1+1=1\tag{2.20}
$$
which is clearly false. Does this mean that the modified system is actually inconsistent? Not necessarily, if we can suitably *reinterpret* the symbols. To that effect, let us consider the following translation:
$$
\begin{matrix}
\text{Symbol}&\text{Interpretation}\\
P&+\\Q&\geq\\-&1\\--&2\\---&3\\\vdots&\vdots
\end{matrix}\tag{2.21}
$$

The general statement
$$
x\:P-Q\:x\tag{2.21}
$$

would now correspond to
$$
N+q\geq{N}\tag{2.22}
$$

which is obviously correct. Since __Definition 2.2__ requires that $$\Phi(T_S)\subset{T_M}$$ in *at least* one interpretation, it follows that the $$\text{PQ}$$ system remains consistent after adding __Axiom Scheme 2__.

What about completeness? The true arithmetical statement
$$
2+3\geq1\tag{2.24}
$$

can obviously be expressed as
$$
--P---Q-\tag{2.25}
$$

which is a well-formed string, but is not a theorem in the $$\text{PQ}$$ system. Indeed, if we wanted to ‘backtrack’ toward an axiom of the form
$$
x\:P-Q\:x\tag{2.26}
$$

or
$$
x\:P-Q\:x-\tag{2.27}
$$

we would need to reduce the number of hyphens between $$P$$ and $$Q$$ to one. The rule of inference requires that we reduce the number of hyphens on both sides of $$Q$$ by $$1$$ in each step, so after one step $$(2.25)$$ would become
$$
--P--Q\tag{2.28}
$$

Note, however, that this is not a well formed string any more.

The above discussion suggests that the modified $$\text{PQ}$$ system is consistent, but is incomplete with respect to the interpretation proposed in $$(2.21)$$. This follows directly from the fact that there are truths about integers that can be expressed as well formed strings, but are not theorems. However, it is entirely possible that we could come up with a different interpretation of the symbols which would guarantee *both* consistency and completeness. For the modified $$\text{PQ}$$ system, it turns out that there is such an interpretation. The only necessary modification would be to reinterpret $$Q$$ as “equal or greater by one” (you are welcome to try this!)


[^1]: This system was considered in: Douglas Hofstadter, *Gödel, Escher, Bach: An Eternal Golden Braid*, Basic Books, 1999.
[^2]: Note that there could be many other theorems in the model system $$M$$ which are not part of set $$W$$. We could think of these theorems as truths that can not be “translated” into statements (*i.e.* well-formed strings) in S. In that respect, it is fair to say that the model M is “richer” than the original system.
[^3]: A stronger version of __Definition 2.4__ is that $$\Phi(T_S)=T_M$$ for all possible interpretations (not just a particular model $$M$$). Such a definition of completeness is sometimes referred to as *adequacy*, or completeness *with respect to truth*.
