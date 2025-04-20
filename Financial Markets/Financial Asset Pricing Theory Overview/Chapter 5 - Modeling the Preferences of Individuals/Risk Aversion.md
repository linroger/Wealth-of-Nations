---
tags:
  - concave_function
  - fair_gamble
  - risk_aversion
  - risk_premium
  - utility_function
aliases:
  - Certainty Equivalent
  - Risk Attitudes
key_concepts:
  - Attitudes towards risk
  - Fair gamble definition
  - Quantitative risk aversion
  - Risk-averse individual
  - Utility function preferences
---

# 5.5 Risk aversion  

In this section we focus on the attitudes towards risk reflected by the preferences of an individual. We assume that the preferences can be represented by a utility function. $u$ and that $u$ is strictly increasing so that the individual is "greedy,' i.e. prefers high consumption to low consumption.. We assume that the utility function is defined on some interval $Z$ of $\mathbb{R}$ , e.g. $Z=\mathbb{R}_{+}\equiv[0,\infty)$  

# 5.5.1 Risk attitudes  

Fix a consumption level $c\in Z$ . Consider a random variable $\varepsilon$ with $\operatorname{E}[\varepsilon]=0$ .We can think of $c+\varepsilon$ as a random variable representing a consumption plan with consumption $c+\varepsilon(\omega)$ if state $\omega$ is realized. Note that $\operatorname{E}[c+\varepsilon]=c$ . Such a random variable $\varepsilon$ is called a fair gamble or a zero-mean risk.  

An individual is said to be (strictly) risk-averse if she for all. $c\in Z$ and all fair gambles. $\varepsilon$ (strictly) prefers the sure consumption level. $c$ to $c+\varepsilon$ . In other words, a risk-averse individual rejects all fair gambles. Similarly, an individual is said to be (strictly) risk-loving if she for all $c\in Z$ (strictly) prefers $c+\varepsilon$ to $c$ , and said to be risk-neutral if she for all $c\in Z$ is indifferent between accepting any fair gamble or not. Of course, individuals may be neither risk-averse, riskneutral, or risk-loving, for example if they reject fair gambles around some values of $c$ and accept fair gambles around other values of. $c$ . Individuals may be locally risk-averse, locally risk-neutral,. and locally risk-loving. Since it is generally believed that individuals are risk-averse, we focus on preferences exhibiting that feature..  

We can think of any consumption plan. $c$ as the sum of its expected value. $\operatorname{E}[c]$ and a fair gamble $\varepsilon=c-\operatorname{E}[c]$ . It follows that an individual is risk-averse if she prefers the sure consumption $\operatorname{E}[c]$ to the random consumption $c$ , i.e. if $u(\mathrm{E}[c])\geq\mathrm{E}[u(c)]$ . By Jensen's Inequality, this is true exactly when $u$ is a concave function and the strict inequality holds if $u$ is strictly concave and. $c$ is a non-degenerate random variable, i.e. it does not have the same value in all states. Recall that $u:Z\to\mathbb{R}$ concave means that for all $z_{1},z_{2}\in Z$ and all $a\in(0,1)$ we have  

$$
u\left(a z_{1}+(1-a)z_{2}\right)\geq a u(z_{1})+(1-a)u(z_{2}).
$$  

If the strict inequality holds in all cases, the function is said to be strictly concave. By the above argument, we have the following theorem:  

Theorem 5.4 An individual with a utility function u is (strictly) risk-averse if and only if u is (strictly) concave.  

Similarly, an individual is (strictly) risk-loving if and only if the utility function is (strictly) convex. An individual is risk-neutral if and only if the utility function is affine.  

# 5.5.2 Quantitative measures of risk aversion  

We will focus on utility functions that are continuous and twice differentiable on the interior of $Z$ By our assumption of greedy individuals, we then have $u^{\prime}>0$ , and the concavity of the utility function for risk-averse investors is then equivalent to $u^{\prime\prime}\leq0$  

The certainty equivalent of the random consumption plan $c$ is defined as the $c^{*}\in Z$ such that  

$$
u(c^{*})=\mathrm{E}[u(c)],
$$  

i.e. the individual is just as satisfied getting the consumption level. $c^{*}$ for sure as getting the random. consumption $c$ . With $Z\subseteq\mathbb{R}$ $c^{*}$ uniquely exists due to our assumptions that $u$ is continuous and strictly increasing. From the definition of the certainty equivalent it is clear that an individual will rank consumption plans according to their certainty equivalents..  

For a risk-averse individual we have the certainty equivalent. $c^{*}$ of a consumption plan is smaller than the expected consumption level E[c]. The risk premium associated with the consumption plan $c$ is defined as $\lambda(c)=\operatorname{E}[c]-c^{*}$ so that  

$$
\operatorname{E}[u(c)]=u(c^{*})=u(\operatorname{E}[c]-\lambda(c)).
$$  

The risk premium is the consumption the individual is willing to give up in order to eliminate the uncertainty.  

The degree of risk aversion is associated with. $u^{\prime\prime}$ , but a good measure of risk aversion should be invariant to strictly positive, affine transformations. This is satisfied by the Arrow-Pratt measures of risk aversion defined as follows. The Absolute Risk Aversion is given by.  

$$
\mathrm{ARA}(c)=-{\frac{u^{\prime\prime}(c)}{u^{\prime}(c)}}.
$$  

The Relative Risk Aversion is given by  

$$
\mathrm{RRA}(c)=-\frac{c u^{\prime\prime}(c)}{u^{\prime}(c)}=c\mathrm{ARA}(c).
$$  

We can link the Arrow-Pratt measures to the risk premium in the following way. Let $\bar{c}\in Z$ denote some fixed consumption level and let $\varepsilon$ be a fair gamble. The resulting consumption plan is then $c=c+\varepsilon$ . Denote the corresponding risk premium by $\lambda(\bar{c},\varepsilon)$ so that  

$$
\operatorname{E}[u({\bar{c}}+\varepsilon)]=u(c^{*})=u\left({\bar{c}}-\lambda({\bar{c}},\varepsilon)\right).
$$  

We can approximate the left-hand side of (5.4) by  

$$
\operatorname{E}[u({\bar{c}}+\varepsilon)]\approx\operatorname{E}\left[u({\bar{c}})+\varepsilon u^{\prime}({\bar{c}})+{\frac{1}{2}}\varepsilon^{2}u^{\prime\prime}({\bar{c}})\right]=u({\bar{c}})+{\frac{1}{2}}\operatorname{Var}[\varepsilon]u^{\prime\prime}({\bar{c}}),
$$  

using $\operatorname{E}[\varepsilon]=0$ and $\operatorname{Var}[\varepsilon]=\operatorname{E}[\varepsilon^{2}]-\operatorname{E}[\varepsilon]^{2}=\operatorname{E}[\varepsilon^{2}]$ , and we can approximate the right-hand side of (5.4) by  

$$
u\left(\bar{c}-\lambda(\bar{c},\varepsilon)\right)\approx u(\bar{c})-\lambda(\bar{c},\varepsilon)u^{\prime}(\bar{c}).
$$  

Hence we can write the risk premium as  

$$
\lambda(\bar{c},\varepsilon)\approx-\frac{1}{2}\operatorname{Var}[\varepsilon]\frac{u^{\prime\prime}(\bar{c})}{u^{\prime}(\bar{c})}=\frac{1}{2}\operatorname{Var}[\varepsilon]\mathrm{ARA}(\bar{c}).
$$  

Of course, the approximation is more accurate for "small' gambles. Thus the risk premium for a small fair gamble around $c$ is roughly proportional to the absolute risk aversion at. $c$ . We see that. the absolute risk aversion $\mathrm{ARA}(\bar{c})$ is constant if and only if $\lambda(\bar{c},\varepsilon)$ is independent of. $\bar{c}$  

Loosely speaking, the absolute risk aversion ARA. $(c)$ measures the aversion to a fair gamble of. a given dollar amount around $c$ , such as a gamble where there is an equal probability of winning. or loosing 1000 dollars. Since we expect that a wealthy investor will be less averse to that gamble than a poor investor, the absolute risk aversion is expected to be a decreasing function of wealth. Note that  

$$
\mathrm{ARA}^{\prime}(c)=-\frac{u^{\prime\prime\prime}(c)u^{\prime}(c)-u^{\prime\prime}(c)^{2}}{u^{\prime}(c)^{2}}=\left(\frac{u^{\prime\prime}(c)}{u^{\prime}(c)}\right)^{2}-\frac{u^{\prime\prime\prime}(c)}{u^{\prime}(c)}<0\quad\Rightarrow\quad u^{\prime\prime\prime}(c)>0,
$$  

that is, a positive third-order derivative of $u$ is necessary for the utility function. $u$ to exhibit decreasing absolute risk aversion..  

Now consider a "multiplicative" fair gamble around $c$ in the sense that the resulting consumption plan is $c=\bar{c}\left(1+\varepsilon\right)=\bar{c}+\bar{c}\varepsilon$ , where $\operatorname{E}[\varepsilon]=0$ . The risk premium is then  

$$
\lambda(\bar{c},\bar{c}\varepsilon)\approx\frac{1}{2}\mathrm{Var}[\bar{c}\varepsilon]\mathrm{ARA}(\bar{c})=\frac{1}{2}\bar{c}^{2}\mathrm{Var}[\varepsilon]\mathrm{ARA}(\bar{c})=\frac{1}{2}\bar{c}\mathrm{Var}[\varepsilon]\mathrm{RRA}(\bar{c})
$$  

implying that  

$$
\frac{\lambda(\bar{c},\bar{c}\varepsilon)}{\bar{c}}\approx\frac{1}{2}\operatorname{Var}[\varepsilon]\mathrm{RRA}(\bar{c}).
$$  

The fraction of consumption you require to engage in the multiplicative risk is thus (roughly) pro-.   
portional to the relative risk aversion at. $c$ . Note that utility functions with constant or decreasing.   
(or even modestly increasing) relative risk aversion will display decreasing absolute risk aversion.  

Some authors use terms like risk tolerance and risk cautiousness. The absolute risk tolerance at $c$ is simply the reciprocal of the absolute risk aversion, i.e..  

$$
\mathrm{ART}(c)={\frac{1}{\mathrm{ARA}(c)}}=-{\frac{u^{\prime}(c)}{u^{\prime\prime}(c)}}.
$$  

Similarly, the relative risk tolerance is the reciprocal of the relative risk aversion. The risk cautiousness at $c$ is defined as the rate of change in the absolute risk tolerance, i.e. $\mathrm{ART}^{\prime}(c)$  

# 5.5.3 Comparison of risk aversion between individuals  

An individual with utility function. $u$ is said to be more risk-averse than an individual with utility. function $\boldsymbol{v}$ if for any consumption plan. $c$ and any fixed. $\bar{c}\in\mathrm{~\it~Z~}$ with $\operatorname{E}[u(c)]\geq u({\bar{c}})$ , we have $\mathrm{E}[v(c)]\geq v(\bar{c})$ . So the $\boldsymbol{v}$ -individual will accept all gambles that the. $u$ -individual will accept - and possibly some more. Pratt (1964) has shown the following theorem:  

Theorem 5.5 Suppose u and v are twice continuously differentiable and strictly increasing. Then the following conditions are equivalent:  

(a) u is more risk-averse than $v$   
(b) $\mathrm{ARA}_{u}(c)\geq\mathrm{ARA}_{v}(c)$ for all $c\in Z$   
(c) a strictly increasing and concave function $f$ exists such that $u=f\circ v$  

Proof: First let us show $(\mathrm{a})\Rightarrow(\mathrm{b})$ : Suppose $u$ is more risk-averse than $\upsilon$ , but that $\mathrm{ARA}_{u}(\hat{c})<$ $\mathrm{ARA}_{v}(\hat{c})$ for some ${\hat{c}}\in Z$ .Since $\mathrm{ARA}_{u}$ and $\mathrm{ARA}_{v}$ are continuous, we must then have that $\mathrm{ARA}_{u}(c)<\mathrm{ARA}_{v}(c)$ for all $c$ in an interval around $\hat{c}$ . Then we can surely find a small gamble around $\hat{c}$ , which the. $u$ -individual will accept, but the $\upsilon$ -individual will reject. This contradicts the assumption in (a).  

Next, we show. $\mathrm{(b)\Rightarrow(c)}$ : Since $\boldsymbol{v}$ is strictly increasing, it has an inverse $v^{-1}$ and we can define. a function $f$ by $f(x)=u\left(v^{-1}(x)\right)$ . Then clearly. $f(v(c))=u(c)$ so that $u=f\circ v$ . The first-order derivative of $f$ is  

$$
f^{\prime}(x)=\frac{u^{\prime}\left(v^{-1}(x)\right)}{v^{\prime}\left(v^{-1}(x)\right)},
$$  

which is positive since. $u$ and $\upsilon$ are strictly increasing. Hence,. $f$ is strictly increasing. The secondorder derivative is.  

$$
\begin{array}{r l r}&{}&{f^{\prime\prime}(x)=\frac{u^{\prime\prime}\left(v^{-1}(x)\right)-\left\{v^{\prime\prime}\left(v^{-1}(x)\right)u^{\prime}\left(v^{-1}(x)\right)\right\}/v^{\prime}\left(v^{-1}(x)\right)}{v^{\prime}\left(v^{-1}(x)\right)^{2}}}\ &{}&{\qquad=\frac{u^{\prime}\left(v^{-1}(x)\right)}{v^{\prime}\left(v^{-1}(x)\right)^{2}}\left(\mathrm{ARA}_{v}\left(v^{-1}(x)\right)-\mathrm{ARA}_{u}\left(v^{-1}(x)\right)\right).}\end{array}
$$  

From (b), it follows that $f^{\prime\prime}(x)<0$ , hence $f$ is concave.  

Finally, we show that $\mathrm{(c)}\Rightarrow\mathrm{(a)}$ : assume that for some consumption plan $c$ and some $\bar{c}\in Z$ , we have $\operatorname{E}[u(c)]\geq u({\bar{c}})$ but $\mathrm{E}[v(c)]<v(\bar{c})$ . We want to arrive at a contradiction.  

$$
\begin{array}{r l}&{f\left(v(\bar{c})\right)=u(\bar{c})\leq\mathrm{E}[u(c)]=\mathrm{E}[f(v(c))]}\ &{\qquad<f\left(\mathrm{E}[v(c)]\right)}\ &{\qquad<f\left(v(\bar{c})\right),}\end{array}
$$  

where we use the concavity of $f$ and Jensen's Inequality to go from the first to the second line, and we use that $f$ is strictly increasing to go from the second to the third line. Now the contradiction is clear.  
