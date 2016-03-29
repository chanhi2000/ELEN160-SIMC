## 2.4 Incompleteness in Modern Mathematics

In this section we will consider several areas of modern mathematics whose development was greatly influenced by Gödel's work. Some of the results obtained in these fields challenge our basic intuitive concepts, and extend them in ways that open up exciting new possibilities. We will begin with an example from computer science, and then move on to a discussion of non-Cantorian set theory and non-standard analysis.[^10]

### The Elusive Number Omega
In many ways, a formal system is very much like a computer program. Indeed, one can easily envision the axioms and rules of inference as an *algorith$$M^*$$, whose output are the resulting theorems. With that in mind, it is not very surprising that a form of Gödelian incompleteness is encountered in the domain of computer science. In this section, we will concentrate on one such case, which involves the number Omega introduced by Gregory Chaitin.[^11]
In order to understand what makes Omega so interesting, we first need to establish some basic facts about computer programs. We will begin by considering the following simple code, whose purpose is to compute the smallest number for which the sum
$$
s_n=\sum_{k=0}^n\frac{1}{2^k}\tag{2.50}
$$

exceeds some prescribed value $$m$$.

### Algorithm 2.1.
The sum described in $$(2.50)$$ can be encoded as a Matlab m-file in the following way:
```m
function [n,s] = program1(m)
s=0; k=0;
while(s<m)
	s=s+2(-k);
	k=k+1;
end
n=k
```

As the program repeatedly executes this loop, the variable s takes on values $$1$$, $$1.5$$, $$1.75$$, $$1.875$$ etc. Consequently, if we set $$m=1.6$$ in this program, it will halt after passing through the loop three times, and will return $$n=3$$ and $$s=1.75$$ as its output. If, on the other hand, we were to set $$m=2.6$$, the program would *never halt*. This follows directly from the fact that $$s_n$$ increases monotonically, with $$2$$ as its upper limit.

The distinction between programs that halt and those that do not is at the heart of one of the most profound results in computer science. This result relates to the so-called Halting Problem, which was posed (and solved) by Alan Turing in the 1930s, when computers were no more than a thought experiment. Turing’s question can be paraphrased as follows: “Is there a program that can decide in a finite amount of time whether any other program will halt?” In showing that such a program does *not* exist, Turing discovered a kind of incompleteness akin to the one established by Gödel. Indeed, one of the immediate consequences of this result is that there will always be a program for which we cannot formally establish whether or not it will halt.

To get a better sense for why the Halting Problem cannot be resolved by a computer program, it is useful to consider a simple formal system of the kind introduced in [__Section 2.1__](ch02a.md). Such a system consists of axioms and rules of inference, which produce strings of characters as theorems. Let us now assume that we are given a particular string, and are asked whether or not it is a theorem. How could we tell? If we attempt to find an answer within the formal system itself, the only way to proceed would be to generate the theorems one by one, and hope that one of them will ultimately match the given string. However, if this does not happen, the process could go on forever. In other words, such a formal system cannot establish the “theoremhood” of any given string in a finite amount of time. A similar (although much more subtle) kind of reasoning lies behind Turing's result as well.

The number Omega is intimately related to the Halting Problem. In order to define it, let us consider how one could *randomly* generate a program. A simple way to do this would be to flip a coin whenever the computer requests the next bit of the program. This bit will be a $$1$$ if the outcome of the toss is “heads,” and $$0$$ if it is “tails.” The process continues until the program halts, at which point the computer stops asking for additional bits. Programs with this property are called *self-delimiting*, due to the fact that they implicitly control their own length.

Let us now denote the set of all self-delimiting programs that halt by H, and form the sum
$$
\Omega=\sum_{p\in H}2^{-|p|}\tag{2.51}
$$

where $$|p|$$ represents the length of program $$p$$ measured in bits. The constant $$\Omega$$ defined in this way corresponds to the probability that a randomly chosen program will halt. To justify this interpretation, suppose that among all possible self-delimiting programs only $$111$$ and $$0101$$ actually halt. If we adopt the coin flipping model for generating random programs, then the halting probability is the sum of the probability that the first three tosses produce $$111$$ (which is $$2^{-3}$$) and the probability that the first four tosses produce $$0101$$ (which is $$2^{-4}$$). Note that this is precisely the way in which $$\Omega$$ is constructed.[^12]

To better understand some of the key properties of $$\Omega$$, we need to introduce the notion of *algorithmic complexity*, which can be traced back to the 17th century and the great German mathematician and philosopher Gottfried Wilhelm von Leibniz. In his *Discourse on Metaphysics*, Leibniz pondered how one could differentiate observations that conform to a law from those that are random. To gain some insight into this question, consider $$a$$ set of $$n$$ randomly selected points in a plane. It is well known that one can always construct an interpolation polynomial of order $$n$$ or higher that passes through all these points. The difficulty, however, is that such a polynomial is no simpler than the data that it is trying to “explain.” As a result, this mathematical function tells us nothing new or useful. In view of this problem, Leibniz proposed that we should use *simplicity* as a criterion for distinguishing between phenomena that are lawful and those that are not.

In the context of algorithmic information theory, the criterion proposed by Leibniz can be reformulated in terms of *program length*. To see how that works, suppose that we are given the first $$N$$ decimal digits of a real number, and are asked to find the *smallest* self-delimiting program that will produce this data as its output. If we succeed, the size of this program (measured in bits) corresponds to the *complexity* of the output. The following example is designed to illustrate this idea more clearly.

### Example 2.1.
Let us consider the first $$N$$ digits in the decimal expansion of $$\pi$$ (where $$N$$ is a large, fixed number). How complicated does the program have to be in order to produce such a output? It turns out that the required program is actually quite simple. One possibility is based on the following formula established by David and Gregory Chudnovsky:
$$
\frac{1}{\pi}=12\sum_{k=0}^{\infty}\frac{(-1)^k(6k!)(13,591,409+545,140,134\cdot k)}{(3k!)(k!)^640,320^{3k+1.5}}\tag{2.52}
$$

The formula looks rather messy, but it can be coded in just a few lines.

It can be shown that each term in the sum $$(2.52)$$ produces an additional 14 digits of $$\pi$$. More importantly, the length of the code is completely independent of $$N$$ (the execution time is a different matter, but that has nothing to do with our definition of complexity). With that in mind, we can conclude that the enormous amount of raw data contained in the digits of $$\pi$$ carries little in the way of algorithmic information. All this information can actually be *compressed* into a very simple code, since the decimals of $$\pi$$ obey a certain pattern that captured by $$(2.52)$$.[^13]

In the case of $$\Omega$$, the situation is very different from the one in __Example 2.1__. It turns out, for instance, that in order to compute the first $$N$$ bits in its binary expansion, we need a program whose size is close to $$N$$ bits. This means that the algorithmic information contained in the bits of $$\Omega$$ *cannot* be compressed into a program that is substantially smaller than the data itself. Things actually even worse than that. For real numbers such as $$\pi$$ (which are described by explicit formulas) we can increase the number of computed digits indefinitely. We cannot do this for $$\Omega$$, although it is a well defined number with a definite binary expansion. As Chaitin pointed out, each of the unknowable bits of $$\Omega$$ represents a concrete example of Gödel's incompleteness.

> “Gödel's incompleteness theorem tells us that within mathematics there are statements that are unknowable, or undecidable. Omega tells us that there are in fact infinitely many such statements: whether any one of the infinitely many bits of Omega is a $$0$$ or a $$1$$ is something that we cannot deduce from any mathematical theory. More precisely, any maths theory enables us to determine at most finitely many bits of Omega.” *Gregory Chaitin*[^14]

What makes $$\Omega$$ particularly interesting is the fact that it is *not* an abstract creation like Gödel's unprovable proposition. Omega is an actual number, about which we know quite a bit and can precisely specify how it can be constructed. It seems that we are tantalizingly close to computing it, and yet we know that it will remain eternally elusive.

> “I wouldn't say that we can touch it, but we can certainly point straight at it.... That's much more frustrating and much more interesting than being told that we can't have something or do something that never seemed concrete enough or down to earth.” *Gregory Chaitin*[^15]

### Non-Cantorian Set Theory
The concept of a set is one of the oldest and most basic in all of mathematics. For a very long time, this notion was accepted intuitively. Cantor's definition proposed in the 19th century is a typical illustration of this approach:

### Definition 2.5.
A set is any collection into a whole of definite and separate objects of our intuition or thought.

It turns out, however, that Cantor's idea of a set leaves some fundamental questions unanswered. In the following, we will focus on two propositions that have been particularly troublesome in that respect—the Axiom of Choice and the Continuum Hypothesis.

To properly understand what these propositions claim, we must first recognize that there are different kinds of infinite sets, and that the sizes of these sets can be compared in a meaningful way. It can be shown, for example, that the set of all real numbers is in some sense “larger” than the set of all integers. In technical terms, the two sets are said to have cardinality $$c$$ and $$\aleph_0$$ (pronounced aleph zero), respectively, with $$c>\aleph_0$$. Another way to make this distinction is to say that the set of integers is countable, while the set of real numbers is *not*.

We now turn to the Axiom of Choice, which can be formulated as follows:
- __P1__: *The Axiom of Choice.* Let $$\alpha$$ be a collection of sets $$\{A,\:B,\:\cdots\}$$, and assume that none of these sets is empty. The axiom of choice states that there exists a set $$Z$$ consisting of precisely one element each from $$A$$, $$B$$, etc.
This proposition has been viewed as problematic by many mathematicians, much like Euclid's 5th axiom. To see why this is so, let us consider the simple set $$A=\{1,\:2,\:3\}$$, and form a set $$B=\left\{\{\},\:\{1\},\:\{2\},\:\{3\},\:\{1,\:2\},\:\{1,\:3\},\:\{2,\:3\},\:\{1,\:2,\:3\}\right\}$$ which consists of all its subsets. Set $$B$$ is referred to as the *power set* of $$A$$, and usually denoted by $$B=2^{A}$$. This notation reflects the fact that any finite set $$A$$ with m elements has exactly $$2^m$$ subsets (a property that is easily verified for our sets $$A$$ and $$B$$). It is obvious that proposition __P1__ holds true in all such cases, but it remains unclear whether this conclusion can be extended to infinite sets as well. In order to appreciate the complexity of the question, it suffices to observe that the set of integers (whose cardinality is $$\aleph_0$$) contains *uncountably many* subsets. This property was proved by Georg Cantor, and is formally expressed as $$c= 2^{\aleph_0}$$. Under such circumstances, it is difficult to see how proposition __P1__ could be verified in a systematic manner.
The second proposition that we will be concerned with addresses the question of whether there are infinite sets whose cardinality lies between $$\aleph_0$$ and $$c$$. Cantor assumed that such sets do *not* exist, and this conjecture is referred to as the “continuum hypothesis”. Determining whether or not this hypothesis is correct proved to be a very difficult task—so difficult, in fact, that it became one of the most celebrated unsolved problems in mathematics (it was the first one on Hilbert’s famous list, which was compiled around 1900).

- __P2__: *The Continuum Hypothesis*. In an infinite set, all infinite subsets either cardinality $$\aleph_0$$ or $$c$$.
As a first step in addressing these difficult issues, it is necessary to recast the notion of a set in more formal terms.  The appropriate axiomatic framework was introduced in the 1920s by the Norwegian logician Thoralf Skolem, based on earlier work by Ernst Zermelo and Abraham Fraenkel. This system (without __P1__ and __P2__) is commonly referred to as Restricted Set Theory, which we will demote in the following as RST. In the 1960s it was established that __P1__ and __P2__ are actually *unprovable propositions* within RST. As a result, we can either add __P1__ and __P2__ as axioms (thus obtaining a “standard” version of set theory or we could add their negations, which results in the so-called non-Cantorian set theory. Although both of these possibilities produce logically consistent systems, the latter one is clearly more exotic and counterintuitive (much like non-Euclidean geometry).
To see why propositions __P1__ and __P2__ are unprovable in the framework of restricted set theory, we need to refer to some of Gödel's later work. Based on his classic results on the consistency and completeness of formal systems, Gödel  introduced the class of *constructible sets* as a model for RST (in the foll we will denote this class by $$M$$). By definition, constructible sets are those that can be formed from simpler sets by a well defined sequence of steps. In this way, every statement of restricted set theory becomes “translatable” into a statement about $$M$$. Using such a model, Gödel was able to show that both __P1__ and __P2__ turn out to be *theorems* in $$M$$. As a result, he could legitimately claim that adding __P1__ and/or __P2__ as axioms in restricted set theory will not create consistency problems. If any such problems were to arise, their cause would necessarily be in restricted set theory. In this sense, Gödel's consistency proof was relative – he basically established that RST with __P1__ and __P2__ added as axioms is consistent if and only if RST itself is consistent.

The schematic diagram in __Fig. 2.3__ provides a further illustration of this point. Namely, if we were to assume that $$\Phi(T_S)\subset{T}_M$$ (where $$T_S$$ and $$T_M$$ denote the theorems of RST and $$M$$, respectively), this would obviously imply that RST is consistent. This property would remain unchanged if we were to add $$p_1$$ and $$p_2$$ to $$T_S$$, since both of these propositions map into $$T_M$$. Note, however, that $$\Phi(T_S)\subset{T_M}$$ is only an *assumption*, whose validity ultimately determines the truth of the overall statement. In that sense, the consistency proof is relative.

#### Fig. 2.3. An illustration of the relative consistency of standard set theory.
![fig2-03]()

It can also be shown that adding the *negation* of __P1__ and __P2__ as axioms will result in relative consistency. In order to establish this fact, it is necessary (among other things) to use a different model for restricted set theory. The details of the proof are quite complicated and will not be considered here.[^16] For our purposes, it suffices to recognize that this result (combined with Gödel's Conclusions) implies that __P1__ and __P2__ are *unprovable propositions* in the framework of RST. This provides yet another illustration of the incompleteness of formal mathematics, and of the interesting possibilities that can arise from this fact.

### Non-Standard Analysis
We begin our brief description of this field with a sequence of straightforward propositions from standard mathematical analysis.
$$
\begin{align*}
p_1:&&\text{There exists a number } c\text{ such that } 0<c<1.\\
p_2:&&\text{There exists a number } c\text{ such that } 0<c<\tfrac{1}{2}.\\\vdots\\
p_n:&&\text{There exists a number } c\text{ such that } 0<c<\tfrac{1}{n}.\\\vdots
\end{align*}\tag{2.53}
$$

Clearly, any *finite* collection of these statements can be true simultaneously. wever, the *whole set* cannot, since in standard analysis for any number $$c$$ we can always find a sufficiently large $$n_0$$ such that $$c\geq\tfrac{1}{n_0}$$. In other words, the proposition
$$
\begin{align*}
p_\infty:&&\text{For any } n \text{ there exists a number } c\text{ such that } 0<c<\tfrac{1}{n}
\end{align*}
$$

is *false* in conventional mathematics.

The above result may perhaps be mildly counterintuitive, but there seems to be nothing particularly unusual about it. What is surprising, however, is the fact that there exists an “alternative” mathematical system in which $$p_\infty$$ is actually *true*. To gain a better understanding of the properties of such a non-standard system, let us denote the set of all statements in standard mathematical
analysis by $$M$$, and let $$L$$ be a formal system into which we can “translate these statements as appropriate strings of symbols. In this ease, $$M$$ obviously represents a model for $$L$$, in the sense proposed by Gödel. It is important to recognize in this context that not all statements of $$M$$ can be properly formalize. In that respect, mathematics is surprisingly similar to human languages.

Every individual statement $$p_i$$ in $$(2.53)$$ can easily be “translated” into a string of symbols $$\sigma_i$$ in $$L$$. The same holds true for any *finite subset* of statements $$p_i$$ well. It can be shown that under these conditions there exists another model for $$L$$, denoted $$M^*$$, in which the translations of $$\sigma_i$$, are true both *individually* and as *a whole*. This result follows from the so-called Compactness Theorem, which is closely related to Gödel's work on completeness.

There is no doubt that $$M^*$$ must contain some very strange objects in order for all $$\sigma_i$$ to be true simultaneously. Among these objects are the elusive “infinitesimals”, which are greater than zero and yet smaller than any ordinary positive number. Nothing like this exists in standard mathematics, as witnessed by the falsity of statement $$p_\infty$$. An interesting question in this context is whether we can somehow relate $$M^*$$ to $$M$$. It turns out that we can, since both are models for the same formal system $$L$$. Systems $$M$$ and $$M^*$$ are said to be *formally*, equivalent, in the sense that there is a correspondence between those statement that are “translatable” into the formal system $$L$$. Of course, statements of $$M$$ and $$M^*$$ that are *not* translatable needn't be connected in any way. This situation is illustrated in __Fig. 2.4__, in which the shaded areas denote the formally equivalent parts of $$M$$ and $$M^*$$.

#### Fig. 2.4. The formally equivalent parts of $$M$$ and $$M^*$$.
![fig2-04]()

What does this equivalence really mean? Basically, it implies that what is true in $$M^*$$  “translates“ into what is true in $$M$$, via the common formal language $$L$$. As a result, it becomes possible to construct proofs in $$M^*$$, and then convert the result into statements about M. Most mathematicians require no more than that. They are usually not particularly interested in the “objective existence” of infinitesimals and related philosophical issues. Their primary concern is whether objects such as infinitesimals can be legitimately used in proofs, and the Compactness Theorem permits them to do so. This is very similar to the way in which complex numbers are used in electrical engineering. No one seriously ponders whether such numbers truly exist in the real world — all that matters is the fact that they greatly simplify the analysis of circuits with sinusoidal inputs.

Formal equivalence allows for some fascinating generalizations. For example, the true statement $$s_i:$$ “10 is a positive number” in $$M$$ can be mapped into $$L$$, and therefore has an equivalent statement $$s_i^*$$ in $$M^*$$. This possibility (which is schematically illustrated in __Fig. 2.5__) leads to the conclusion that all standard numbers have a representation in $$M^*$$.

#### Fig. 2.5. Mapping of $$s_i$$, into $$s_i^*$$ via $$\sigma_i$$.
![fig2-05]()

It is important to recognize that $$M^*$$ also contains a variety of other objects such as infinitesimals and infinitely large numbers, which have no counterpart in $$M$$. Along these lines, we can think of any number $$r\in{M}$$ as having a “pseudo-real” equivalent $$r^*\in{M}^*$$, which is surrounded by a vast set of other pseudo-real objects. The entire infinitesimal “neighborhood” of $$r^*$$ is sometimes referred to as a monad, following the philosophical terminology of Leibniz. For any number $$\hat{r}^*=r^*+dr$$ in such a monad, we say that $$r^*$$ is its *standard part*.

Most mathematicians agree that these unusual generalizations of real numbers opened up a new and exciting line of research. However, there is no consensus as to where such an approach may ultimately lead. Whatever its future may be, it is important to remember that some key elements of this theory (such as the Compactness Theorem) directly relate to Gödel's results in the area of formal systems. One could therefore reasonably claim that Gödel paved the way for Abraham Robinson's pioneering work on infinitesimals, and provided the necessary conditions for the emergence of nonstandard analysis.[^17]

[^10]: An excellent introductory exposition of the last two topics can be found in Davis and Hersh, The *Mathematical Experience*, Birkhauser, 1981.
[^11]: Gregory Chaitin, Meta-Math: *The Quest for Omega*, Pantheon Books, 2005.
[^12]: The fact that we are summing over self-delimiting programs is an important prerequisite for convergence. To see why this is so, suppose that the program represented by bits $$1001$$ halts, and contributes $$2^{-4}$$ to the sum. In that case, we don't need to consider any other programs of the form $$1001xxxxx$$, because a self-delimiting program will not ask for more bits after halting. In this way we can eliminate a large number of redundant terms from the sum $$(2,51)$$, and ensure that $$0\leq\Omega\leq{1}$$.
[^13]: There are many other formulas for calculating $$\pi$$, some of which converge much faster than $$(2,52)$$. A nice survey of these results can be found in: Borwein and Bailey, *Mathematics by Experiment*, A. K. Peters, 2004.
[^14]: Gregory Chaitin, “Omega and why maths has no TOEs,” Plus Magazine, 37, December 2005
[^15]: Gregory Chaitin, *Meta-Math: The Quest for Omega*.
[^16]: For further information, see: Paul Cohen, *Set Theory and the Continuum Hypothesis*, Addison-Wesley, 1966.
[^17]: A classic text on this subject is: Abraham Robinson, *Nonstandard Analysis*, Princeton University Press, 1996.
