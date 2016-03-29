## 2.3 Gödel's Incompleteness Theorem

Based on the discussion in [__Sections 2.1__](ch02a.md) and [__2.2__](ch02b.md), we can now consider Gödel’s famous Incompleteness Theorem and provide an outline of its proof. Given the complexity of this proof, in the following we will focus only on its main ideas[^6].

We begin with a description of Gödel's main result, which can be summarized in the following way.

### Theorem 2.1.
(The First Incompleteness Theorem) In every sufficient complex formal system there are unprovable propositions. Even if such a system were augmented by an indefinite number of new axioms and rules, there would always be number theoretic truths that are not formally derivable.

__Theorem 2.1__ has two important corollaries, which pertain to consistency and completeness.

### Corollary 2.1.
It is impossible to prove the consistency of the formal system proposed in Principia Mathematica, or any similarly complex formal system within the system  itself.

### Corollary 2.2.
Given any consistent formalization of number theory (including the one in Principia Mathematica), there are true number theoretic statements (whose truth can be established by external means) that are expressible as well-formed strings, but are *not* theorems. In other words, no sufficiently complex formal system is complete with respect to the “standard” interpretation (which assumes number theory as its model).

To get a sense for how the Incompleteness Theorem was proved, we first need to breifly describe a formal system known as Typographical Number Theory (TNT), which was designed to represent statements about non-negative integers.[^7] This system uses a limited number of standard arithmetical and logic symbols, which are listed in __Table 2.1.__ Note that all positive integers can be described by combining prefix $$S$$ and number zero in the manner indicate __Table 2.2.__

#### Table 2.1. Representation of numbers in TNT.
| Number | TNT Symbol |
| :----: | :--------: |
| $$0$$ | $$0$$ |
| $$1$$ | $$\text{S}0$$ |
| $$2$$ | $$\text{SS}0$$ |
| $$3$$ | $$\text{SSS}0$$ |
| $$\vdots$$ | $$\vdots$$ |

#### Table 2.2. Integer representation of TNT symbols.
| Number | TNT Symbol |
| :----: | :--------: |
| $$0$$ | $$666$$ |
| $$\text{S}$$| $$123$$ |
| $$+$$ | $$112$$ |
| $$.$$ | $$236$$ |
| $$($$ | $$362$$ |
| $$)$$ | $$323$$ |
| $$<$$ | $$212$$ |
| $$>$$ | $$213$$ |
| $$[$$ | $$312$$ |
| $$]$$ | $$313$$ |
| $$a$$ | $$262$$ |
| $$'$$ | $$163$$ |
| $$\wedge$$ | $$161$$ |
| $$\vee$$ | $$616$$ |
| $$\supset$$ | $$633$$ |
| $$\sim$$ | $$223$$ |
| $$\exists$$ | $$333$$ |
| $$\forall$$ | $$626$$ |
| $$:$$ | $$636$$ |
| $$\text{end of line}$$ | $$611$$ |

As noted earlier, one of the key elements of Gödel's proof is the construction of a mapping that associates a specific integer with every TNT symbol. A possible way to do this is shown in __Table 2.1__, where each symbol is matched to a triplet of digits from the set $$\{1,\:2,\:3,\:6\}$$.[^8]

Using this mapping, we can *uniquely* express any TNT string as an integer (usually, a very large one). For example, the string
$$
S0+0=S0\tag{2.43}
$$

correspond to the 21 digit number $$\alpha=123,666,112,666,111,123,666$$, which will be referred to in the following as the *Gödel number* of $$(2.43)$$.[^9]

Before proceeding, it is important to add that TNT statements can include one or more variables (which are denoted $$a$$, $$a^{\prime}$$, $$a^{\prime\prime}$$, etc.). Such statements fall into two general categories, which are known as *open* and *closed* formulas. An example of an open formula would be the string
$$
S0+a=S0\tag{2.44}
$$
where $$a$$ is a *free variable*. In cases like this, we cannot determine whether the statement is true or false, since $$a$$ is unspecified.

Closed formulas are characterized by the fact that each variable has an associated *quantifier*. This requirement ensures that the truth of the statement can always be decided. As an illustration of this property, consider a modification of $$(2.44)$$ where the quantifier $$\exists{a}:$$ is added at the beginning of the string. It is easily verified taht the resulting formula
$$
\exists{a}:S0+a=S0\tag{2.45}
$$

represents a true statement, whose interpretation is: “There exists a non-negative number $$a$$ such that $$1+a=a$$.”

The Gödel numbering defined in __Table 2.1__ allows us to represent an entire proof as a single integer. Indeed, since formal proofs proceed as sequences of individual statements, all we need to do is find the Gödel number for each of them, and separate consecutive lines by inserting the triplet $$611$$. Note that the line of such a derivation always corresponds to the actual theorem that we set out to prove. This information is easily extracted from the Gödel number of the proof by identifying all digits that follow the last appearance of $$611$$. For Example, if a proof were represented by Gödel number
$$
\beta=626,262,636,\cdots,611,333,262,636,123,666,112,262,111,123,666\tag{2.46}
$$

the theorem itself would have the Gödel number
$$
\gamma=333,262,636,123,666,112,262,111,123,666\tag{2.47}
$$

A number like $$\gamma$$ which corresponds to a TNT theorem will be referred to in the following as a *TNT number*.

In order to provide a compact description of Gödel's proof, we need to induce two special number theoretic functions, both of which are can be represented as TNT strings. The first one, denoted $$F_1(a,\:a^{\prime})$$, takes $$a$$ (which is the Gödel number of an entire proof) and checks if $$a^{\prime}$$ is the Gödel number of its last line. In view of our previous discussion, it follows that $$a^{\prime}$$ is a TNT number whenever $$F_1(a,\:a^{\prime})$$ is true for some $$a$$.

The second function, denoted $$F_2(a^{\prime\prime},\:\:a^{\prime})$$, is slightly more complicated. Its first argument, $$a^{\prime\prime}$$, is assumed to be the Gödel number of a known TNT string with a single free variable. This function replaces every occurrence of the free variable with $$a^{\prime\prime}$$, and then checks whether $$a^{\prime}$$ is the Gödel number of the resulting string.

Given these two definitions, let us now consider the string $$H$$:
$$
\sim\exists{a}:\exists{a}^{\prime}:\left<S_1(a,\:a^{\prime})\wedge{S}_2(a^{\prime\prime},\:a^{\prime})\right>\tag{2.48}
$$

where $$S_1(a,\:a^{\prime})$$ and $$S_2(a^{\prime\prime},\:a^{\prime})$$ are TNT representations of functions $$F_1(a,\:a^{\prime})$$ and $$F_2(a^{\prime\prime},\:a^{\prime})$$, respectively. Note that $$a^{\prime\prime}$$ is a free variable in $$H$$,x since it has no quantifier associated with it. Assuming that the Gödel number of $$(2.48)$$ is $$u$$, we will now form a new string $$G$$ by replacing every occurrence of $$a^{\prime\prime}$$ in $$H$$ by $$u$$.
$$
\sim\exists{a}:\exists{a}^{\prime}:\left<S_1(a,\:a^{\prime})\wedge{S}_2(u,\:a^{\prime})\right>\tag{2.49}
$$

The Gödel number for string $$G$$ will be denoted in the following by $$g$$ (which implies that $$F_2(u,\:g)$$ is true by definition).

The number theoretic interpretation of $$G$$ is: “There do *not* exist numbers $$a$$ and $$a^{\prime}$$ such that $$F_1(a,\:a^{\prime})$$ and F_2(u,\:a^{\prime})$$ are simultaneously true.” This interpretation gives rise to two possible scenarios.

- __CASE 1.__ Suppose that the number theoretic interpretation of $$G$$ is a *false* statement. Then, there exist $$a$$ and $$a^{\prime}$$ such that both $$F_1(a,\:a^{\prime})$$ and $$F_2(u,\:a^{\prime})$$ are true. By definition, $$F_2(u,\:a^{\prime})$$ is true only when $$a^{\prime}=g$$. Therefore, $$F_1(a,\:g)$$ must true for some $$a$$. This means that $$g$$ is a TNT number, which is equivalent to saying that $$G$$ is a TNT theorem. Such a result represents a contradiction, since the interpretation of a TNT theorem cannot be a false statement (bear in mind at every TNT theorem must map into a number theoretic truth).

- __CASE 2.__	Suppose that the number theoretic interpretation of $$G$$ is a true statement. This means that there is no pair of numbers $$a$$, and $$a^{\prime}$$ such that $$F_1(a,\:a^{\prime})$$ and $$F_2(u,\:a^{\prime})$$ are simultaneously true. Let us now consider the special case when $$a^{\prime}=g$$. Since $$F_2(u,\:g)$$ is true by definition, then $$F_1(a,\:g)$$ must be false for *all* $$a$$. This means that $$g$$ is *not* the last line of a TNT proof, and therefore cannot be a TNT number. In other words, $$G$$ is not a TNT theorem.

There are no contradictions in __Case 2__, but the implication is that $$G$$ corresponds to a number theoretic truth although it is *not* a TNT theorem. This represents incompleteness as we defined it in [__Section 2.1__](ch02a.md). It is interesting to serve that the interpretation of $$G$$ actually tells us something about the string itself (specifically, that $$G$$ is not a TNT theorem). This suggests that the incompleteness of TNT has its roots in the possibility of self-reference.

[^6]: A rigorous proof can be found in: Kurt Gödel, *On Formally Undecidable Propositions of Principia Mathematica and Related Systems*, Dover Publication, 1992.
[^7]: A considerable amount of literature has been devoted to Gödel's theorem and its proof. In this section, we will follow the approach proposed in Douglas Hofstadter’s book: *Gödel, Escher Bach: An Eternal Golden Braid* where this difficult topic is presented with remarkable clarity. The more ambitious reader can refer to Gödel's original paper for further details.
[^8]: This table represents an abridged version of the one provided on page 268 of *Gödel, Escher Bach: An Eternal Golden Braid*.
[^9]: The number theoretic interpretation of string $$(2.43)$$ is $$1+0=1$$

