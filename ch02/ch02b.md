## 2.2 Absolute Proofs

Establishing the consistency and completeness of complicated formal systems can be an extraordinarily difficult task. Even if one could find an interpretation that works, proving completeness requires showing that all expressible truths are also theorems. In most cases, this would entail an infinite number of demonstrations, which is obviously impossible in practice (remember that although any finite number of tests may be positive, this doesn't allow us to conclude that there won’t be be unpleasant surprises down the line). In this section, we will consider a rather elaborate formal system for which it is actually possible to show both consistency and completeness without interpreting all the symbols. This system (often referred to as Sentential Calculus) is interesting because it represents a subset of the formal system that inspired Gödel's theorems. It will also illustrate the flavor (if not the details) of Gödel's proof, and show that establishing properties such as consistency requires *metamathematical* (that is, reasoning ‘outside’ the formal system).

### Sentential Calculus
Sentential Calculus consists of two distinct types of symbols, which are referred to as variables and connectives. A brief description of each type is provided below.[^4]

### *Variables*
are simply letters of the alphabet, with no interpretation associated with them.

### *Connectives*
are additional symbols that have a specific interpretation, and are used to link variables (and/or strings). They are defined as follows:
$$
\begin{matrix}
\text{Symbol}&\text{Interpretation}\\\sim&\text{not}\\\vee&\text{or}\\supset&\text{if-then}\\\wedge&\text{and}
\end{matrix}\tag{2.29}
$$

### *Rules of Formation.*
There are three rules of formation:
1. Each letter of the alphabet is a well formed string.
2. If $$S$$ is a well-formed string, them so is $$\sim{S}$$.
3. If $$S_1$$ and $$S_2$$ are well formed strings, then so are:
$$
\begin{matrix}
S_1\vee S_2\\S_1\supset{S}_2\\S_1\wedge{S}_2
\end{matrix}\tag{2.30}
$$

Based on these rules, it is easy to verify whether a string is well-formed For example, strings
$$
\begin{matrix}
p\\\sim{p}\\p\vee q\\(p\vee{q})\supset(q\vee{p})
\end{matrix}\tag{2.31}
$$

are all well formed, while
$$
\begin{matrix}
p\sim q\\qp\vee\\p\wedge
\end{matrix}\tag{2.32}
$$

are not.

### *Axioms.*
Sentential calculus has four axioms:
$$
\begin{align*}\text{Axiom }1\:\:\:\:&(p\vee q)\supset p\\\text{Axiom }2\:\:\:\:&p\supset(p\vee q)\\\text{Axiom }3\:\:\:\:&(p\vee q)\supset(q\vee p)\\\text{Axiom }4\:\:\:\:&(p\supset q)\supset[(r\vee p)\supset(r\vee q)]
\end{align*}
$$
Note that since the variables have no interpretation, these axioms have no specific meaning.

### *Rules of Inference.*
The rules of inference determine how new theorems are obtained tained from existing ones. In this system, there are two such rules: the Rule of Substitution and the Rule of Detachment.

1. *Rule of Substitution.* Suppose that string $$S_1$$ is a theorem, and that we substitute every occurrence of a certain variable with some well-formed string $$S_2$$. Then, the resulting string is itself a theorem. As an illustration, consider the string
$$
(p\vee{q})\supset(q\vee{p})\tag{2.34}
$$
(which is actually an axiom). If we were to replace $$p$$ with some arbitrary well-formed string $$S$$, the resulting statement)
$$
(S\vee{q})\supset(q\vee{S})\tag{2.35}
$$
would be a theorem (although $$S$$ itself needn't be).

2. *Rule of Detachment.* Suppose that $$S_1$$ and $$S_1\supset{S}_2$$ are both theorems. Then, the $$S_2$$ is a theorem as well.
Now that we have introduced all the ingredients of the formal system, our objective will be to prove that it is internally consistent. The proof involves a sequence of steps, and does not require an interpretation of the variables.
    - __STEP 1.__ As a first step, let us consider what would happen if two strings $$S_1$$ and $$\sim{S}_1$$ both turned out to be theorems. In that case, a statement and its negation would be provable simultaneously, which clearly implies inconsistency the sense of __Definition 2.1__). We will now show that if Sentential Calculus were indeed inconsistent in this way, then *any* well-formed string would necessarily a theorem. In order to do this, we will assume that both $$S_1$$ and $$\sim{S}_1$$ are theorems, and make use of the fact that
$$
p\supset(\sim{p}\supset{q})\tag{2.36}
$$
is a theorem in our system (we will not prove this). Applying the Rule of while __Axiom 2__ corresponds to Substitution twice, we obtain
$$
S_1\supset(\sim{S}_1\supset{S})\tag{2.37}
$$
which is a theorem for *any* well-formed string $$S$$. The rule of Detachment further implies that
$$
\sim S_1\supset{S}\tag{2.38}
$$
is a theorem as well. We now have a rather interesting situation, in which both $$\sim{S}_1$$ and $$\sim{S}_1\supset{S}$$ are theorems. Applying the Rule of Detachment to these two statements, we conclude that S is itself a theorem, although it was an arbitrarily chose string. In other words, if Sentential Calculus were an inconsistent system, then any well-formed string in it would be a theorem.

    - __STEP 2.__ In view of the result obtained in Step 1, we can now claim that Sentential Calculus is consistent if there exists at least one well-formed string that is not a theorem. The trick, of course, is to find such a statement, and this is by no means easy. A necessary step in this process is to identify a property that is common to all axioms and theorems in the system. In order to do that, let us group all the letters of the alphabet into two classes, denoted $$K_1$$ and $$K_2$$. The compound strings will them be classified according to the following rules:
		- __Rule 1.__ A string of the form $$S_1\vee{S}_2$$ is placed in class $$K_2$$, if *both* $$S_1$$ and $$S_2$$ are in $$K_2$$. Otherwise, it is placed in $$K_1$$.
		- __Rule 2.__ A string of the form $$S_1\supset{S}_2$$ So is placed in class $$K_2$$ if $$S_1$$ is in $$K_1$$ and $$S_2$$ is in $$K_2$$. Otherwise, it is placed in $$K_1$$.
		- __Rule 3.__ A string of the form $$S_1\wedge{S}_2$$ is placed in class $$K_1$$ if *both* $$S_1$$ and $$S_2$$ are in $$K_1$$. Otherwise, it is placed in $$K_2$$.
		- __Rule 4.__ A string of the form to $$S$$ is placed in class $$K_2$$ if $$S$$ is in $$K_1$$ Otherwise, it is placed in $$K_1$$.

	Based on this classification, we will say that a string $$S$$ is a tautology if it is a member of class $$K_1$$ regardless of where its constitutive elements belong.

	- __STEP 3.__ In this step we will show that all the axioms of Sentential Calculus are tautologies. We will demonstrate this property explicitly for __Axioms 1__ and __2__ (the proof is similar for __Axioms 3__ and __4__). The easiest way to do this is to tabulate all the possible combinations. For __Axiom 1__, we have
	$$
	\begin{matrix}
	p&(p\vee q)&(p\vee q)\supset p\\
	K_1&K_1&K_1\\
	K_2&K_2&K_1
	\end{matrix}\tag{2.39}
	$$
	
	while __Axiom 2__ coresponds to
	$$
	\begin{matrix}
	p&q&(p\vee q)&p\supset(p\vee q)\\
	K_1&K_1&K_1&K_1\\
	K_1&K_2&K_1&K_1\\
	K_2&K_1&K_1&K_1\\
	K_2&K_2&K_2&K_1
	\end{matrix}\tag{2.40}
	$$
	
	Ιt is obvious that both axioms always belong to class $$K_1$$, regardless of how we classify letters $$p$$ and $$q$$.

	- __STEP 4.__ Having established that all axioms are tautologies, we now proceed to show that this is true of all theorems as well. Since theorems are derived from axioms by the two rules of inference, it suffices to prove that these rules preserve the ‘tautology’ property. In the following, we will demonstrate this only for the Rule of Detachment (the proof for Rule of Substitution is similar).

	Suppose that $$S_1$$ and $$S_1\supset{S}_2$$ are *both* theorems *and* tautologies. This means that $$S_1\in{K}_1$$ and $$S_1\supset{S}_2\in{K}_1$$ no matter where their constitutive elements belong. The Rule of Detachment implies that $$S_2$$ must be a theorem as well, but it is unclear at this point whether or not it is a tautology.

	What follows is an example of a proof by contradiction. Namely, let us assume that $$S_2$$ is not a tautology. In that case, there exists a possible combination of constitutive elements for which $$S_2\in{K}_2$$. For that particular combination, we have $$S_1\in{K}_1$$ and $$S_2\in{K}_2$$, and __Rule 2__ implies that $$S_1\supset{S}_2\in{K}_2$$ as well. This a contradiction, since we assumed that $$S_1\supset{S}_2$$ is a tautology. As a result, our original assumption must be wrong, and $$S_2$$ must be a tautology whenever $$S_1$$ and $$S_1\supset{S}_2$$ have this property.

	- __STEP 5.__ Since all axioms and theorems were shown to be tautologies, our tasks now reduces to finding a well-formed string that is not. This is actually quite simple. An obvious example would be the string
	$$
	p\vee{q}\tag{2.41}
	$$
	which is clearly well-formed, but is not a tautology. Why this is so is clear from the table below, in which all possible combinations are examined.
	$$
	\begin{matrix}
	p&q&(p\vee q)\\
	K_1&K_1&K_1\\
	K_1&K_2&K_1\\
	K_2&K_1&K_1\\
	K_2&K_2&K_2
	\end{matrix}\tag{2.42}
	$$

### *Conclusions*
The results of this section suggest that consistency can sometimes be established without resorting to specific interpretations. When such a proof can found, it is referred to as *absolute*. It is important to note in this context that our methodology once again relied on reasoning ‘outside’ the formal system.[^5] The only tools available within the Sentential Calculus are the two Rules of Inference, and these were clearly not sufficient to establish consistency. Proofs of this type are called *metaproofs*, since they transcend the limits set by the formal system.

### Remark 2.3.
An absolute proof of completeness is also possible for Sentential Calculus, but we will not consider it here.

[^4]: More details on this system can be found in E. Nagel and J. R. Newman, *Gödel's Proof*, New York University Press, 2001.
[^5]: The concept of a tautology, for example, does not arise within Sentential Calculus.
