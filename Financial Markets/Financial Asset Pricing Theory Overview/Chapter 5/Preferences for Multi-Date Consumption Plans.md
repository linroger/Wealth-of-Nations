---
tags:
  - consumption_plans
  - expected_utility
  - multi_date
  - time_additivity
  - time_preference
aliases:
  - Additively separable utility
  - Multi-period consumption
key_concepts:
  - Expected utility representation
  - Intertemporal substitution
  - Multi-date consumption plans
  - Subjective time preference rate
  - Time-separable utility
---

# 5.7 Preferences for multi-date consumption plans  

Above we implicitly considered preferences for consumption at one given future point in time. We need to generalize the ideas and results to settings with consumption at several dates. In one-period models individuals can consume both at time 0 (beginning-of-period) and at time 1 (end-of-period). In multi-period models individuals can consume either at each date in the discrete time set ${\mathcal{T}}=\{0,1,2,\ldots,T\}$ or at each date in the continuous time set $\mathcal{T}=[0,T]$ . In any case a consumption plan is a stochastic process $c=(c_{t})_{t\in\mathcal{T}}$ where each $c_{t}$ is a random variable representing the state-dependent level of consumption at time $t$  

Consider the discrete-time case and, for each $t$ , let $Z_{t}\subseteq\mathbb{R}$ denote the set of all possible consumption levels at date $t$ and define $Z=Z_{0}\times Z_{1}\times\cdot\cdot\cdot\times Z_{T}\subseteq\mathbb{R}^{T+1}$ , then any consumption plan $c$ can again be represented by a probability distribution $\pi$ on the set $Z$ . For finite $Z$ , we can again apply Theorem 5.1 so that under the relevant axioms, we can represent preferences by a utility index $\mathrm{\mathcal{U}}$ which to each consumption plan. $(c_{t})_{t\in\mathbb{T}}=(c_{0},c_{1},...,c_{T})$ attaches a real number $\mathcal{U}(c_{0},c_{1},\dots,c_{T})$ with higher numbers to the more preferred consumption plans. If we further impose the Substitution Axiom, Theorem 5.2 ensures an expected utility representation, i.e. the existence of a utility function $U:Z\rightarrow\mathbb{R}$ so that consumption plans are ranked according to their expected utility, i.e..  

$$
\mathcal{U}(c_{0},c_{1},\dots,c_{T})=\mathrm{E}\left[U(c_{0},c_{1},\dots,c_{T})\right]\equiv\sum_{\omega\in\Omega}p_{\omega}U\left(c_{0},c_{1}(\omega),\dots,c_{T}(\omega)\right).
$$  

We can call $U$ a multi-date utility function since it depends on the consumption levels at all dates. Again this result can be extended to the case of an infinite. $Z$ , e.g. $Z=\mathbb{R}_{+}^{7^{\prime}+1}$ , but also to continuous-time settings where. $U$ will then be a function of the entire consumption process c = (ct)tE[0,T]:  

# 5.7.1 Additively time-separable expected utility  

Often time-additivity is assumed so that the utility the individual gets from consumption in one period does not directly depend on what she consumed in earlier periods or what she plans to consume in later periods. For the discrete-time case, this means that.  

$$
U(c_{0},c_{1},\dots,c_{T})=\sum_{t=0}^{T}u_{t}(c_{t})
$$  

where each $u_{t}$ is a valid "single-date' utility function. Still, when the individual has to choose her. current consumption rate, she will take her prospects for future consumption into account. The continuous-time analogue is  

$$
U((c_{t})_{t\in[0,T]})=\int_{0}^{T}u_{t}(c_{t})d t.
$$  

In addition it is typically assumed that. $u_{t}(c_{t})=e^{-\partial t}u(c_{t})$ for all $t$ . This is to say that the direct. utility the individual gets from a given consumption level is basically the same for all dates, but the individual prefers to consume any given number of goods sooner than later. This is modeled by the subjective time preference rate $\delta$ , which we assume to be constant over time and independent. of the consumption level. More impatient individuals have higher. $\delta$ 's. In sum, the life-time utility. is typically assumed to be given by.  

$$
U(c_{0},c_{1},\dots,c_{T})=\sum_{t=0}^{T}e^{-\delta t}u(c_{t})
$$  

in discrete-time models and  

$$
U((c_{t})_{t\in[0,T]})=\int_{0}^{T}e^{-\delta t}u(c_{t})d t
$$  

in continuous-time models. In both cases, $u$ is a "single-date' utility function such as those discussed in Section 5.6.  

Time-additivity is mostly assumed for tractability. However, it is important to realize that the time-additive specification does not follow from the basic axioms of choice under uncertainty, but. is in fact a strong assumption, which most economists agree is not very realistic. One problem is that time-additive preferences induce a close link between the reluctance to substitute consumption across different states of the economy (which is measured by risk aversion) and the willingness to substitute consumption over time (which can be measured by the so-called elasticity of intertemporal substitution). Solving intertemporal utility maximization problems of individuals. with time-additive CRRA utility, it turns out that an individual with a high relative risk aversion will also choose a very smooth consumption process, i.e. she will have a low elasticity of intertemporal substitution. There is nothing in the basic theory of choice that links the risk aversion and the elasticity of intertemporal substitution together. For one thing, risk aversion makes sense even in an atemporal (i.e. one-date) setting where intertemporal substitution is meaningless and, conversely, intertemporal substitution makes sense in a multi-period setting without uncertainty in which risk aversion is meaningless. The close link between the two concepts in the multi-period model with uncertainty is an unfortunate consequence of the assumption of time-additive expected utility.  

According to Browning (1991), non-additive preferences were already discussed in the 1890 book. "Principles of Economics" by Alfred Marshall. See Browning's paper for further references to the. critique on intertemporally separable preferences. Let us consider some alternatives that are more general and still tractable.  

# 5.7.2 Habit formation and state-dependent utility  

The key idea of habit formation is to let the utility associated with the choice of consumption at a given date depend on past choices of consumption. In a discrete-time setting the utility index of a given consumption process $c$ is now given as $\begin{array}{r}{\operatorname{E}[\sum_{t=0}^{T}e^{-\delta t}u(c_{t},h_{t})]}\end{array}$ , where $h_{t}$ is a measure of the standard of living or the habit level of consumption, e.g. a weighted average of past consumption rates such as  

$$
h_{t}=h_{0}e^{-\beta t}+\alpha\sum_{s=1}^{t-1}e^{-\beta(t-s)}c_{s},
$$  

where $h_{0}$ $\alpha$ , and $\beta$ are non-negative constants. It is assumed that $u$ is decreasing in $h$ so that high past consumption generates a desire for high current consumption, i.e. preferences display intertemporal complementarity. In particular, models where $u(c,h)$ is assumed to be of the powerlinear form,  

$$
u(c,h)={\frac{1}{1-\gamma}}(c-h)^{1-\gamma},\quad\gamma>0,c\geq h,
$$  

turn out to be computationally tractable. This is closely related to the subsistence HARA utility, but with habit formation the "subsistence level" $h$ is endogenously determined by past consumption. The corresponding absolute and relative risk aversions are  

$$
\mathrm{ARA}(c,h)\equiv-\frac{u_{c c}(c,h)}{u_{c}(c,h)}=\frac{\gamma}{c-h},\quad\mathrm{RRA}(c,h)\equiv-c\frac{u_{c c}(c,h)}{u_{c}(c,h)}=\frac{\gamma c}{c-h},
$$  

where $u_{c}$ and $u_{c c}$ are the first- and second-order derivatives of $u$ with respect to $c$ . In particular, the relative risk aversion is decreasing in $c$ . Note that the habit formation preferences are still consistent with expected utility.  

A related line of extension of the basic preferences is to allow the preferences of an individual. to depend on some external factors, i.e. factors that are not fully determined by choices made by the individual. One example that has received some attention is where the utility which some individual attaches to her consumption plan depends on the consumption plans of other individuals or maybe the aggregate consumption in the economy. This is often referred to as "keeping up with the Jones'es."' If you see your neighbors consume at high rates, you want to consume at a high rate too. Utility is state-dependent. Models of this type are sometimes said to have an external habit, whereas the habit formation discussed above is then referred to as internal habit.. If we denote the external factor by $X_{t}$ , a time-additive life-time expected utility representation is $\operatorname{E}[\sum_{t=0}^{T}e^{-\delta t}u(c_{t},X_{t})]$ , and a tractable version is $\begin{array}{r}{u(c,X)=\frac{1}{1-\gamma}\left(c-X\right)^{1-\gamma}}\end{array}$ very similar to the subsistence CRRA or the specific habit formation utility given above. In this case, however, the "subsistence" level is determined by external factors. Another tractable specification is $u(c,X)=$ $\frac{1}{1-\gamma}(c/X)^{1-\gamma}$  

# 5.7.3 Recursive utility  

Another preference specification gaining popularity is the so-called recursive preferences or Epstein-Zin preferences, suggested and discussed by, e.g., Kreps and Porteus (1978), Epstein and Zin (1989, 1991), and Weil (1989). The original motivation of this representation of preferences is that it allows individuals to have preferences for the timing of resolution of uncertainty, which is not consistent with the standard multi-date expected utility theory and violates the set of behavioral axioms.  

In a discrete-time framework Epstein and Zin (1989, 1991) assumed that life-time utility from time $t$ on is captured by a utility index $\mathcal{U}_{t}$ (in this literature sometimes called the "felicity") satisfying the recursive relation  

$$
\mathcal{U}_{t}=f(c_{t},z_{t}),
$$  

where $z_{t}=C E_{t}(\mathcal{U}_{t+1})$ is the certainty equivalent of. $\mathcal{U}_{t+1}$ given information available at time $t$ and $f$ is an aggregator on the form.  

$$
f(c,z)=(a c^{\alpha}+b z^{\alpha})^{1/\alpha}.
$$  

The aggregator is identical to the two-good CES utility specification (5.13) and, since $z_{t}$ here refers to future consumption or utility, $\psi=1/(1-\alpha)$ is called the elasticity of intertemporal substitution..  

An investor's willingness to substitute risk between states is modeled through $z_{t}$ as the certainty equivalent of a constant relative risk aversion utility function. Recall that the certainty equivalent for an atemporal utility function $u$ is defined as  

$$
C E=u^{-1}\left(\operatorname{E}[u(x)]\right).
$$  

In particular for CRRA utility $u(x)=x^{1-\gamma}/(1-\gamma)$ we obtain  

$$
C E=\left(\mathrm{E}[x^{1-\gamma}]\right)^{\frac{1}{1-\gamma}},
$$  

where $\gamma>0$ is the relative risk aversion.  

To sum up, Epstein-Zin preferences are specified recursively as  

$$
\mathcal{U}_{t}=\left(a c_{t}^{\alpha}+b\left(\mathrm{E}_{t}[\mathcal{U}_{t+1}^{1-\gamma}]\right)^{\frac{\alpha}{1-\gamma}}\right)^{1/\alpha}.
$$  

Using the fact that $\begin{array}{r}{\alpha=1-\frac{1}{\psi}}\end{array}$ , we can rewrite $\mathcal{U}_{t}$ as  

$$
\mathcal{U}_{t}=\left(a c_{t}^{1-\frac{1}{\psi}}+b\left(\mathrm{E}_{t}[\mathcal{U}_{t+1}^{1-\gamma}]\right)^{\frac{1-\frac{1}{\psi}}{1-\gamma}}\right)^{\frac{1}{1-\frac{1}{\psi}}}.
$$  

Introducing $\begin{array}{r}{\theta=(1-\gamma)/(1-\frac{1}{\psi})}\end{array}$ , we have  

$$
\begin{array}{r}{\mathcal{U}_{t}=\left(a c_{t}^{\frac{1-\gamma}{\theta}}+b\left(\operatorname{E}_{t}[\mathcal{U}_{t+1}^{1-\gamma}]\right)^{\frac{1}{\theta}}\right)^{\frac{\theta}{1-\gamma}}.}\end{array}
$$  

The constant $a$ is unimportant. Bansal (2007) and other authors put $a=1-\delta$ and $b=\delta$ However, the value of. $a$ does not affect optimal decisions and therefore no interpretation can be given to $a$ . In order to see this, first note that we can rewrite (5.15) as  

$$
\begin{array}{r l}&{\mathcal{U}_{t}=a^{1/\alpha}\left(c_{t}^{\alpha}+b a^{-1}\left(\mathrm{E}_{t}\left[\mathcal{U}_{t+1}^{1-\gamma}\right]\right)^{\frac{\alpha}{1-\gamma}}\right)^{1/\alpha}}\ &{=a^{1/\alpha}\left(c_{t}^{\alpha}+b\left(\mathrm{E}_{t}\left[\left\{a^{-1/\alpha}\mathcal{U}_{t+1}\right\}^{1-\gamma}\right]\right)^{\frac{\alpha}{1-\gamma}}\right)^{1/\alpha},}\end{array}
$$  

which implies that  

$$
a^{-1/\alpha}\mathcal{U}_{t}=\left(c_{t}^{\alpha}+b\left(\mathrm{E}_{t}\left[\left\{a^{-1/\alpha}\mathcal{U}_{t+1}\right\}^{1-\gamma}\right]\right)^{\frac{\alpha}{1-\gamma}}\right)^{1/\alpha}.
$$  

Hence, it is clear that the utility index $\tilde{\mathcal{U}}$ defined for any $t$ by $\dot{\mathcal{U}}_{t}=a^{-1/\alpha}\mathcal{U}_{t}$ is equivalent to the utility index $\mathrm{\mathcal{U}}$ , since it is just a scaling. Without loss of generality we could put $a=1$  

Time-additive power utility as a special case. The special case $\gamma=1/\psi$ corresponds to time-additive expected CRRA utility. In order to see this, first note that with $\gamma=1/\psi$ , we have $\theta=1$ and thus  

$$
\mathcal{U}_{t}=\left(a c_{t}^{1-\gamma}+b\mathrm{E}_{t}[\mathcal{U}_{t+1}^{1-\gamma}]\right)^{\frac{1}{1-\gamma}}
$$  

or  

$$
\begin{array}{r}{\mathcal{U}_{t}^{1-\gamma}=a c_{t}^{1-\gamma}+b\mathrm{E}_{t}[\mathcal{U}_{t+1}^{1-\gamma}].}\end{array}
$$  

If we start unwinding the recursions, we get  

$$
\begin{array}{r l}&{\mathcal{U}_{t}^{1-\gamma}=a c_{t}^{1-\gamma}+b\operatorname{E}_{t}\left[a c_{t+1}^{1-\gamma}+b\operatorname{E}_{t+1}[\mathcal{U}_{t+2}^{1-\gamma}]\right]=a\operatorname{E}_{t}\left[c_{t}^{1-\gamma}+b c_{t+1}^{1-\gamma}\right]+b^{2}\operatorname{E}_{t}\left[\mathcal{U}_{t+2}^{1-\gamma}\right]}\ &{\quad\quad=\dots}\ &{\quad\quad=a\displaystyle{\sum_{s=0}^{\infty}}\operatorname{E}_{t}\left[b^{s}c_{t+s}^{1-\gamma}\right].}\end{array}
$$  

Any strictly increasing function of a utility index will represent the same preferences. In particular,  

$$
\mathcal{V}_{t}=\frac{1}{a(1-\gamma)}\mathcal{U}_{t}^{1-\gamma}=\sum_{s=0}^{\infty}\mathrm{E}_{t}\left[b^{s}\frac{1}{1-\gamma}c_{t+s}^{1-\gamma}\right]
$$  

represents the same preferences and is clearly equivalent to time-additive expected utility. Note that $b$ plays the role of the subjective discount factor..  

The Epstein-Zin preferences are characterized by three parameters: the relative risk aversion $\gamma$ , the elasticity of intertemporal substitution $\psi$ , and the subjective discount factor $b$ . Relative to the standard time-additive power utility, the Epstein-Zin specification allows the relative risk aversion (attitudes towards atemporal risks) to be disentangled form the elasticity of intertemporal substitution (attitudes towards shifts in consumption over time). Moreover, Epstein and Zin (1989) shows that when $\gamma>1/\psi$ , the individual will prefer early resolution of uncertainty. If $\gamma<1/\psi$ late resolution of uncertainty is preferred. For the standard utility case $\gamma=1/\psi$ , the individual is indifferent about the timing of the resolution of uncertainty. Note that in the relevant case of $\gamma>1$ , the auxiliary parameter $\theta$ will be negative if and only if $\psi>1$ . Empirical studies disagree about reasonable values of $\psi$ . Some studies find $\psi$ smaller than one (e.g. Campbell 1999), other studies find $\psi$ greater than one (e.g. Vissing-Jorgensen and Attanasio 2003).  

The continuous-time equivalent of recursive utility is called stochastic differential utility and. studied by, e.g., Duffie and Epstein (1992b). Note that generally recursive preferences are not consistent with expected utility since. $\mathcal{U}_{t}$ depends non-linearly on the probabilities of future con-. sumption levels.  

# 5.7.4 Two-good, multi-period utility  

For studying some problems it is useful or even necessary to distinguish between different consumption goods. Until now we have implicitly assumed a single consumption good which is perishable in the sense that it cannot be stored. However, individuals spend large amounts on durable goods such as houses and cars. These goods provide utility to the individual beyond the period of purchase and can potentially be resold at a later date so that it also acts as an investment. Another important good is leisure. Individuals have preferences both for consumption of physical goods and for leisure. A tractable two-good utility function is the Cobb-Douglas function:  

$$
u(c_{1},c_{2})=\frac{1}{1-\gamma}\left(c_{1}^{\psi}c_{2}^{1-\psi}\right)^{1-\gamma},
$$  

where $\psi\in[0,1]$ determines the relative weighting of the two goods.  
