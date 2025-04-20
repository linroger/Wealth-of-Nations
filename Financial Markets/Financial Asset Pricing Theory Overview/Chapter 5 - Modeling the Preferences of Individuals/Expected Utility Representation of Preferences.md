---
tags:
  - expected_utility
  - preference_representation
  - substitution_axiom
  - utility_function
  - von_neumann_morgenstern
aliases:
  - EUT
  - Utility Theory
key_concepts:
  - Expected utility representation
  - Probability distributions
  - Substitution Axiom
  - Utility indices
  - Von Neumann-Morgenstern function
---

# 5.4 Expected utility representation of preferences  

Utility indices are functions of probability distributions on the set of possible consumption levels. With many states of the world and many assets to trade in, the set of such probability distributions will be very, very large. This will significantly complicate the analysis of optimal choice using  

utility indices to represent preferences. To simplify the analysis financial economists traditionally put more structure on the preferences so that they can be represented in terms of expected utility..  

We say that a preference relation. $\succeq$ on $\mathcal{P}(Z)$ has an expected utility representation if there exists a function $u:Z\to\mathbb{R}$ such that  

$$
\pi_{1}\succeq\pi_{2}\quad\Leftrightarrow\quad\sum_{z\in Z}\pi_{1}(z)u(z)\geq\sum_{z\in Z}\pi_{2}(z)u(z).
$$  

Here $\textstyle\sum_{z\in Z}\pi(z)u(z)$ is the expected utility of end-of-period consumption given the consumption probability distribution $\pi$ . The function $u$ is called a von Neumann-Morgenstern utility function or simply a utility function. Note that $u$ is defined on the set $Z$ of consumption levels, which in general has a simpler structure than the set of probability distributions on $Z$ . Given a utility function $u$ , we can obviously define a utility index by $\begin{array}{r}{\mathcal{U}(\pi)=\sum_{z\in Z}\pi(z)u(z)}\end{array}$  

# 5.4.1 Conditions for expected utility  

When can we use an expected utility representation of a preference relation? The next lemma is a first step.  

Lemma 5.2 A preference relation $\succeq$ has an expected utility representation if and only if it can be represented by a linear utility index. $\mathfrak{U}$ in the sense that.  

$$
\mathcal{U}\left(a\pi_{1}+(1-a)\pi_{2}\right)=a\mathcal{U}(\pi_{1})+(1-a)\mathcal{U}(\pi_{2})
$$  

for any $\pi_{1},\pi_{2}\in\mathcal{P}(Z)$ and any $a\in[0,1]$  

Proof: Suppose that $\succeq$ has an expected utility representation with utility function $u$ .Define $\mathcal{U}:\mathcal{P}(Z)\to\mathbb{R}$ by $\begin{array}{r}{\mathcal{U}(\pi)=\sum_{z\in Z}\pi(z)u(z)}\end{array}$ . Then clearly $\mathrm{\mathcal{U}}$ is a utility index representing $\succeq$ and $\mathrm{\mathcal{U}}$ is linear since.  

$$
\begin{array}{l}{{\displaystyle\mathcal{U}\left(a\pi_{1}+(1-a)\pi_{2}\right)=\sum_{z\in Z}\left(a\pi_{1}(z)+(1-a)\pi_{2}(z)\right)u(z)}}\ {{\displaystyle\qquad=a\sum_{z\in Z}\pi_{1}(z)u(z)+(1-a)\sum_{z\in Z}\pi_{2}(z)u(z)}}\ {{\displaystyle\qquad=a\mathfrak{U}(\pi_{1})+(1-a)\mathfrak{U}(\pi_{2})}.}\end{array}
$$  

Conversely, suppose that $\mathrm{\mathcal{U}}$ is a linear utility index representing $\succeq$ . Define a function $u:Z\to\mathbb{R}$ by $u(z)=\mathcal{U}(\mathbf{1}_{z})$ . For any $\pi\in{\mathcal{P}}(Z)$ we have  

$$
\pi\sim\sum_{z\in Z}\pi(z)\mathbf{1}_{z}.
$$  

Therefore,  

$$
\mathfrak{U}(\pi)=\mathfrak{U}\left(\sum_{z\in Z}\pi(z)\mathbf{1}_{z}\right)=\sum_{z\in Z}\pi(z)\mathfrak{U}(\mathbf{1}_{z})=\sum_{z\in Z}\pi(z)u(z).
$$  

Since $\mathrm{\mathcal{U}}$ is a utility index, we have $\pi_{1}\succeq\pi_{2}\Leftrightarrow\mathcal{U}(\pi_{1})\geq\mathcal{U}(\pi_{2})$ , which the computation above shows is equivalent to $\begin{array}{r}{\sum_{z\in Z}\pi_{1}(z)u(z)\geq\sum_{z\in Z}\pi_{2}(z)u(z)}\end{array}$ .Consequently, $u$ gives an expected utility  

<html><body><table><tr><td>2</td><td>1 2</td><td>3</td><td>4</td></tr><tr><td>T1</td><td>0 0.2</td><td>0.6</td><td>0.2</td></tr><tr><td>T2</td><td>0 0.4</td><td>0.2</td><td>0.4</td></tr><tr><td>T3</td><td>1 0</td><td>0</td><td>0</td></tr><tr><td>T4</td><td>0.5 0.1</td><td>0.3</td><td>0.1</td></tr><tr><td>T5</td><td>0.5 0.2</td><td>0.1</td><td>0.2</td></tr></table></body></html>  

Table 5.3: The probability distributions used in the illustration of the Substitution Axiom.  

representation of $\succeq$  

The question then is under what assumptions the preference relation. $\succeq$ can be represented by a linear utility index. As shown by von Neumann and Morgenstern (1944) we need an additional axiom, the so-called Substitution Axiom..  

Axiom 5.3 (Substitution) For all $\pi_{1},\pi_{2},\pi_{3}\in\mathcal{P}(Z)$ and all $a\in(0,1]$ , we have  

and  

$$
\begin{array}{r l}{\pi_{1}\succ\pi_{2}\quad\Leftrightarrow\quad a\pi_{1}+(1-a)\pi_{3}\succ a\pi_{2}+(1-a)\pi_{3}}\ &{}\ &{}\ {\pi_{1}\sim\pi_{2}\quad\Leftrightarrow\quad a\pi_{1}+(1-a)\pi_{3}\sim a\pi_{2}+(1-a)\pi_{3}.}\end{array}
$$  

The Substitution Axiom is sometimes called the Independence Axiom or the Axiom of the Irrelevance of the Common Alternative. Basically, it says that when the individual is to compare two. probability distributions, she need only consider the parts of the two distributions which are different from each other. As an example, suppose the possible consumption levels are. $Z=\{1,2,3,4\}$ and consider the probability distributions on $Z$ given in Table 5.3. Suppose you want to compare the distributions $\pi_{4}$ and $\pi_{5}$ . They only differ in the probabilities they associate with consumption levels 2, 3, and 4 so it should only be necessary to focus on these parts. More formally observe. that  

$$
\pi_{4}\sim0.5\pi_{1}+0.5\pi_{3}~\mathrm{and}~\pi_{5}\sim0.5\pi_{2}+0.5\pi_{3}.
$$  

$\pi_{1}$ is the conditional distribution of. $\pi_{4}$ given that the consumption level is different from 1 and $\pi_{2}$ is the conditional distribution of. $\pi_{5}$ given that the consumption level is different from 1. The Substitution Axiom then says that.  

$$
\pi_{4}\succ\pi_{5}\quad\Leftrightarrow\quad\pi_{1}\succ\pi_{2}.
$$  

The next lemma shows that the Substitution Axiom is more restrictive than the Monotonicity Axiom.  

Lemma 5.3 If a preference relation. $\succeq$ satisfies the Substitution Axiom, it will also satisfy the Monotonicity Axiom..  

Proof: Given $\pi_{1},\pi_{2}\in\mathcal{P}(Z)$ with $\pi_{1}\succ\pi_{2}$ and numbers $a,b\in[0,1]$ . We have to show that  

$$
a>b\quad\Leftrightarrow\quad a\pi_{1}+(1-a)\pi_{2}\succ b\pi_{1}+(1-b)\pi_{2}.
$$  

Note that if $a=0$ , we cannot have $a>b$ , and if $a\pi_{1}+(1-a)\pi_{2}\succ b\pi_{1}+(1-b)\pi_{2}$ we cannot have $a=0$ . We can therefore safely assume that $a>0$  

First assume that $a>b$ . Observe that it follows from the Substitution Axiom that  

$$
a\pi_{1}+(1-a)\pi_{2}\succ a\pi_{2}+(1-a)\pi_{2}
$$  

and hence that $a\pi_{1}+(1-a)\pi_{2}\succ\pi_{2}$ . Also from the Substitution Axiom we have that for any $\pi_{3}\succ\pi_{2}$ , we have  

$$
\pi_{3}\sim\left(1-\frac{b}{a}\right)\pi_{3}+\frac{b}{a}\pi_{3}\succ\left(1-\frac{b}{a}\right)\pi_{2}+\frac{b}{a}\pi_{3}.
$$  

Due to our observation above, we can use this with $\pi_{3}=a\pi_{1}+(1-a)\pi_{2}$ . Then we get  

$$
\begin{array}{c}{{a\pi_{1}+(1-a)\pi_{2}\succ\displaystyle\frac{b}{a}\{a\pi_{1}+(1-a)\pi_{2}\}+\left(1-\displaystyle\frac{b}{a}\right)\pi_{2}}}\ {{\mathrm{}}}\ {{\sim b\pi_{1}+(1-b)\pi_{2},}}\end{array}
$$  

as was to be shown.  

Conversely, assuming that  

$$
a\pi_{1}+(1-a)\pi_{2}\succ b\pi_{1}+(1-b)\pi_{2},
$$  

we must argue that $a>b$ . The above inequality cannot be true if $a=b$ since the two combined distributions are then identical. If $b$ was greater than $a$ , we could follow the steps above with $a$ and $b$ swapped and end up concluding that $b\pi_{1}+(1-b)\pi_{2}\succ a\pi_{1}+(1-a)\pi_{2}$ , which would contradict our assumption. Hence, we cannot have neither $a=b$ nor $a<b$ but must have $a>b$ $\sqcup$  

Next we state the main result:  

Theorem 5.2 Assume that $Z$ is finite and that $\succeq$ is a preference relation on $\mathcal{P}(Z)$ . Then  can be represented by a linear utility index if and only $i f\succeq$ satisfies the Archimedean Axiom and the Substitution Axiom.  

Proof: First suppose the preference relation. $\succeq$ satisfies the Archimedean Axiom and the Substitution Axiom. Define a utility index. $\mathcal{U}:\mathcal{P}(Z)\to\mathbb{R}$ exactly as in the proof of Theorem 5.1, i.e.. $\mathcal{U}(\pi)=\alpha_{\pi}$ , where $\alpha_{\pi}\in[0,1]$ is the unique number such that.  

$$
\boldsymbol{\pi}\sim\alpha_{\pi}\mathbf{1}_{z^{u}}+(1-\alpha_{\pi})\mathbf{1}_{z^{l}}.
$$  

We want to show that, as a consequence of the Substitution Axiom, $\mathrm{\mathcal{U}}$ is indeed linear. For that purpose, pick any two probability distributions $\pi_{1},\pi_{2}\in\mathcal{P}(Z)$ and any number $a\in[0,1]$ . We want to show that $\mathcal{U}\left(a\pi_{1}+(1-a)\pi_{2}\right)=a\mathcal{U}(\pi_{1})+(1-a)\mathcal{U}(\pi_{2})$ . We can do that by showing that  

$$
a\pi_{1}+(1-a)\pi_{2}\sim(a\mathcal{U}(\pi_{1})+(1-a)\mathcal{U}(\pi_{2}))\mathbf{1}_{z^{u}}+\left(1-\{a\mathcal{U}(\pi_{1})+(1-a)\mathcal{U}(\pi_{2})\}\right)\mathbf{1}_{z^{l}}.
$$  

This follows from the Substitution Axiom:  

$$
\begin{array}{r l}&{a\pi_{1}+(1-a)\pi_{2}\sim a\{\mathcal{U}(\pi_{1})\mathbf{1}_{z^{u}}+\left(1-\mathcal{U}(\pi_{1})\right)\mathbf{1}_{z^{l}}\}+\left(1-a\right)\{\mathcal{U}(\pi_{2})\mathbf{1}_{z^{u}}+\left(1-\mathcal{U}(\pi_{2})\right)\mathbf{1}_{z^{l}}\}}\ &{\qquad\sim\left(a\mathcal{U}(\pi_{1})+(1-a)\mathcal{U}(\pi_{2})\right)\mathbf{1}_{z^{u}}+\left(1-\left\{a\mathcal{U}(\pi_{1})+(1-a)\mathcal{U}(\pi_{2})\right\}\right)\mathbf{1}_{z^{l}}.}\end{array}
$$  

Now let us show the converse, i.e. if $\succeq$ can be represented by a linear utility index $\mathrm{\mathcal{U}}$ , then it must satisfy the Archimedean Axiom and the Substitution Axiom. In order to show the Archimedean Axiom, we pick $\pi_{1}\succ\pi_{2}\succ\pi_{3}$ , which means that $\mathcal{U}(\pi_{1})>\mathcal{U}(\pi_{2})>\mathcal{U}(\pi_{3})$ , and must find numbers $a,b\in(0,1)$ such that  

$$
a\pi_{1}+(1-a)\pi_{3}\succ\pi_{2}\succ b\pi_{1}+(1-b)\pi_{3},
$$  

i.e. that  

$$
\mathcal{U}\left(a\pi_{1}+(1-a)\pi_{3}\right)>\mathcal{U}(\pi_{2})>\mathcal{U}\left(b\pi_{1}+(1-b)\pi_{3}\right).
$$  

Define the number $a$ by  

$$
a=1-\frac{1}{2}\frac{\mathcal{U}(\pi_{1})-\mathcal{U}(\pi_{2})}{\mathcal{U}(\pi_{1})-\mathcal{U}(\pi_{3})}.
$$  

Then $a\in(0,1)$ and by linearity of $\mathrm{\mathcal{U}}$ we get  

$$
\begin{array}{l}{{\displaystyle\mathcal{U}\left(a\pi_{1}+(1-a)\pi_{3}\right)=a\mathcal{U}(\pi_{1})+(1-a)\mathcal{U}(\pi_{3})}}\ {{\displaystyle=\mathcal{U}(\pi_{1})+(1-a)\left(\mathcal{U}(\pi_{3})-\mathcal{U}(\pi_{1})\right)}}\ {{\displaystyle=\mathcal{U}(\pi_{1})-\frac{1}{2}\left(\mathcal{U}(\pi_{1})-\mathcal{U}(\pi_{2})\right)}}\ {{\displaystyle=\frac{1}{2}\left(\mathcal{U}(\pi_{1})+\mathcal{U}(\pi_{2})\right)}}\ {{\displaystyle>\mathcal{U}(\pi_{2})}.}\end{array}
$$  

Similarly for $b$  

In order to show the Substitution Axiom, we take $\pi_{1},\pi_{2},\pi_{3}\in\mathcal{P}(Z)$ and any number $a\in(0,1]$ We must show that $\pi_{1}\succ\pi_{2}$ if and only if $a\pi_{1}+(1-a)\pi_{3}\succ a\pi_{2}+(1-a)\pi_{3}$ , i.e.  

$$
\mathcal{U}(\pi_{1})>\mathcal{U}(\pi_{2})\quad\Leftrightarrow\quad\mathcal{U}\left(a\pi_{1}+(1-a)\pi_{3}\right)>\mathcal{U}\left(a\pi_{2}+(1-a)\pi_{3}\right).
$$  

This follows immediately by linearity of $\mathrm{\mathcal{U}}$  

$$
\begin{array}{r l}&{\mathcal{U}\left(a\pi_{1}+(1-a)\pi_{3}\right)=a\mathcal{U}(\pi_{1})+\mathcal{U}\left((1-a)\pi_{3}\right)}\ &{\qquad>a\mathcal{U}(\pi_{2})+\mathcal{U}\left((1-a)\pi_{3}\right)}\ &{\qquad=\mathcal{U}\left(a\pi_{2}+(1-a)\pi_{3}\right)}\end{array}
$$  

with the inequality holding if and only if $\mathcal{U}(\pi_{1})>\mathcal{U}(\pi_{2})$ . Similarly, we can show that $\pi_{1}\sim\pi_{2}$ if and only if. $a\pi_{1}+(1-a)\pi_{3}\sim a\pi_{2}+(1-a)\pi_{3}$  

The next theorem shows which utility functions that represent the same preference relation. The proof is left for the reader as Exercise 5.1..  

Theorem 5.3 A utility function for a given preference relation is only determined up to a strictly increasing affine transformation, i.e. if $u$ is a utility function for $\succeq$ , then v will be so if and only if there exist constants $a>0$ and b such that $v(z)=a u(z)+b$ for all $z\in Z$  

If one utility function is an affine function of another, we will say that they are equivalent. Note that an easy consequence of this theorem is that it does not really matter whether the utility is positive or negative. At first, you might find negative utility strange but we can always add a sufficiently large positive constant without affecting the ranking of different consumption plans..  

Suppose $\mathrm{\mathcal{U}}$ is a utility index with an associated utility function $u$ . If $f$ is any strictly increasing transformation, then $V=f\circ\mathcal{U}$ is also a utility index for the same preferences, but $f\circ u$ is only the utility function for $V$ if $f$ is affine.  

The expected utility associated with a probability distribution $\pi$ on $Z$ is $\textstyle\sum_{z\in Z}\pi(z)u(z)$ . Recall that the probability distributions we consider correspond to consumption plans. Given a consumption plan, i.e. a random variable. $c$ , the associated probability distribution is defined by the probabilities  

$$
\pi(\boldsymbol{z})=\mathbb{P}\left(\left\{\boldsymbol{\omega}\in\Omega|\boldsymbol{c}(\boldsymbol{\omega})=\boldsymbol{z}\right\}\right)=\sum_{\boldsymbol{\omega}\in\Omega:\boldsymbol{c}(\boldsymbol{\omega})=\boldsymbol{z}}p_{\omega}.
$$  

The expected utility associated with the consumption plan $c$ is therefore  

$$
\operatorname{E}[u(c)]=\sum_{\omega\in\Omega}p_{\omega}u(c(\omega))=\sum_{z\in Z}\sum_{\omega\in\Omega:c(\omega)=z}p_{\omega}u(z)=\sum_{z\in Z}\pi(z)u(z).
$$  

Of course, if $c$ is a risk-free consumption plan in the sense that a. $z$ exists such that $c(\omega)=z$ for all $\omega$ , then the expected utility is $\operatorname{E}[u(c)]=u(z)$ . With a slight abuse of notation we will just write this as $u(c)$  

# 5.4.2 Some technical issues  

Infinite $Z$ .What if $Z$ is infinite, e.g. $Z=\mathbb{R}_{+}\equiv\left\lvert0,\infty\right\rvert$ ? It can be shown that in this case a preference relation has an expected utility representation if the Archimedean Axiom, the Substitution Axiom, an additional axiom ("the sure thing principle"), and "some technical conditions" are satisfied. Fishburn (1970) gives the details.  

Expected utility in this case:. $\begin{array}{r}{\operatorname{E}[u(c)]=\int_{Z}u(z)\pi(z)d z}\end{array}$ , where $\pi$ is a probability density function. derived from the consumption plan $c$  

Boundedness of expected utility.Suppose $u$ is unbounded from above and $\mathbb{R}_{+}\subseteq Z$ . Then there exists $(z_{n})_{n=1}^{\infty}\subseteq Z$ with $z_{n}\to\infty$ and $u(z_{n})\geq2^{n}$ . Expected utility of consumption plan $\pi_{1}$ with $\pi_{1}(z_{n})=1/2^{n}$  

$$
\sum_{n=1}^{\infty}u(z_{n})\pi_{1}(z_{n})\geq\sum_{n=1}^{\infty}2^{n}{\frac{1}{2^{n}}}=\infty.
$$  

If $\pi_{2},\pi_{3}$ are such that $\pi_{1}\succ\pi_{2}\succ\pi_{3}$ , then the expected utility of $\pi_{2}$ and $\pi_{3}$ must be finite. But for no $b\in(0,1)$ do we have  

$$
\pi_{2}\succ b\pi_{1}+(1-b)\pi_{3}\qquad[\mathrm{expected~utility}=\infty].
$$  

. no problem if $Z$ is finite.  

no problem if $\mathbb{R}_{+}\subseteq Z$ $u$ is concave, and consumption plans have finite expectations: $u$ concave $\Rightarrow u$ is differentiable in some point $b$ and  

$$
u(z)\leq u(b)+u^{\prime}(b)(z-b),\quad\forall z\in Z.
$$  

If the consumption plan $c$ has finite expectations, then  

$$
\operatorname{E}[u(c)]\leq\operatorname{E}[u(b)+u^{\prime}(b)(c-b)]=u(b)+u^{\prime}(b)\left(\operatorname{E}[c]-b\right)<\infty.
$$  

Table 5.4: The probability distributions used in the illustration of the Allais Paradox.   


<html><body><table><tr><td>2</td><td>0</td><td>1 5</td></tr><tr><td>T1</td><td>0 1</td><td>0</td></tr><tr><td>T2</td><td>0.01</td><td>0.89 0.1</td></tr><tr><td></td><td>0.9</td><td>0 0.1</td></tr><tr><td>T4</td><td>0.89</td><td>0.11 0</td></tr></table></body></html>  

Subjective probability. We have taken the probabilities of the states of nature as exogenously given, i.e. as objective probabilities. However, in real life individuals often have to form their own probabilities about many events, i.e. they form subjective probabilities. Although the analysis is a bit more complicated, Savage (1954) and Anscombe and Aumann (1963) show that the results we developed above carry over to the case of subjective probabilities. For an introduction to this analysis, see Kreps (1990, Ch. 3).  

# 5.4.3 Are the axioms reasonable?  

The validity of the Substitution Axiom, which is necessary for obtaining the expected utility representation, has been intensively discussed in the literature. Some researchers have conducted experiments in which the decisions made by the participating individuals conflict with the Substitution Axiom.  

The most famous challenge is the so-called Allais Paradox named after Allais (1953). Here is one example of the paradox. Suppose $Z=\{0,1,5\}$ . Consider the consumption plans in Table 5.4.. The Substitution Axiom implies that. $\pi_{1}\succ\pi_{2}\Rightarrow\pi_{4}\succ\pi_{3}$ . This can be seen from the following:.  

$$
\begin{array}{r l}&{\quad0.11\big(\S1\big)+0.89\bigg[\big(\S1\big)\bigg]\sim\pi_{1}\succ\pi_{2}\sim0.11\left(\frac{1}{11}\big(\S0\big)+\frac{10}{11}\big(\S5\big)\right)+0.89\bigg[\big(\S1\big)\bigg]\quad\Rightarrow}\ &{\underbrace{0.11\big(\S1\big)+0.89\bigg[\big(\S0\big)\bigg]}_{\pi_{4}\sim}\sim0.11\left(\frac{1}{11}\big(\S0\big)+\frac{10}{11}\big(\S5\big)\right)+0.89\bigg[\big(\S0\big)\bigg]\sim\underbrace{0.9\big(\S0\big)+0.1\big(\S5\big)}_{\pi_{3}\sim}}\end{array}
$$  

Nevertheless individuals preferring $\pi_{1}$ to $\pi_{2}$ often choose $\pi_{3}$ over $\pi_{4}$ . Apparently people tend to over-weight small probability events, e.g. (\$0) in $\pi_{2}$  

Other "problems":  

. the "framing" of possible choices, i.e. the way you get the alternatives presented, seem to affect decisions   
models assume individuals have unlimited rationality  
