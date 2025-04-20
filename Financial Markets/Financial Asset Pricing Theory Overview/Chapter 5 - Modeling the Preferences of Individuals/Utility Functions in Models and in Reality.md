---
tags:
  - absolute_risk_aversion
  - crra_utility
  - hara_utility
  - logarithmic_utility
  - power_utility
  - relative_risk_aversion
  - risk_aversion
  - utility_functions
aliases:
  - extended power utility
  - isoelastic utility
key_concepts:
  - Absolute risk aversion
  - CRRA utility definition
  - HARA utility function
  - Logarithmic utility function
  - Negative exponential utility
  - Relative risk aversion
  - Satiation HARA utility
---

# 5.6 Utility functions in models and in reality  

# 5.6.1 Frequently applied utility functions  

CRRA utility.(Also known as power utility or isoelastic utility.) Utility functions $u(c)$ in this class are defined for $c\geq0$  

$$
u(c)={\frac{c^{1-\gamma}}{1-\gamma}},
$$  

where $\gamma>0$ and $\gamma\neq1$ . Since  

$$
u^{\prime}(c)=c^{-\gamma}\quad\mathrm{~and~}\quad u^{\prime\prime}(c)=-\gamma c^{-\gamma-1},
$$  

the absolute and relative risk aversions are given by  

$$
\mathrm{ARA}(c)=-\frac{u^{\prime\prime}(c)}{u^{\prime}(c)}=\frac{\gamma}{c},\qquad\mathrm{RRA}(c)=c\mathrm{ARA}(c)=\gamma.
$$  

The relative risk aversion is constant across consumption levels. $c$ , hence the name CRRA (Constant Relative Risk Aversion) utility. Note that $\begin{array}{r}{u^{\prime}(0+)\equiv\operatorname*{lim}_{c\rightarrow0}u^{\prime}(c)=\infty}\end{array}$ with the consequence that an optimal solution will have the property that consumption/wealth. $c$ will be strictly above 0 with probability one. Hence, we can ignore the very appropriate non-negativity constraint on consumption since the constraint will never be binding. Furthermore, $u^{\prime}(\infty)\equiv\mathrm{lim}_{c\rightarrow\infty}u^{\prime}(c)=0$  

Some authors assume a utility function of the form. $u(c)=c^{1-\gamma}$ , which only makes sense for. $\gamma\in(0,1)$ . However, empirical studies indicate that most investors have a relative risk aversion above 1, cf. the discussion below. The absolute risk tolerance is linear in $c$  

$$
\mathrm{ART}(c)={\frac{1}{\mathrm{ARA}(c)}}={\frac{c}{\gamma}}.
$$  

![](57c5a0ba7d267d50d8ac101b6f5a736c3b27c3d3d7a7998c447ca71b64817d84.jpg)  
Figure 5.1: Some CRRA utility functions.  

Except for a constant, the utility function  

$$
u(c)={\frac{c^{1-\gamma}-1}{1-\gamma}}
$$  

is identical to the utility function specified in (5.6). The two utility functions are therefore equivalent in the sense that they generate the same optimal choices. The advantage in using the latter definition is that this function has a well-defined limit as $\gamma\to1$ . From l'Hospital's rule we have that  

$$
\operatorname*{lim}_{\gamma\rightarrow1}{\frac{c^{1-\gamma}-1}{1-\gamma}}=\operatorname*{lim}_{\gamma\rightarrow1}{\frac{-c^{1-\gamma}\ln c}{-1}}=\ln c,
$$  

which is the important special case of logarithmic utility. When we consider CRRA utility,. we will assume the simpler version (5.6), but we will use the fact that we can obtain the optimal strategies of a log-utility investor as the limit of the optimal strategies of the general CRRA investor. as $\gamma\to1$  

Some CRRA utility functions are illustrated in Figure 5.1.  

HARA utility. (Also known as extended power utility.) The absolute risk aversion for CRRA utility is hyperbolic in $c$ . More generally a utility function is said to be a HARA (Hyperbolic Absolute Risk Aversion) utility function if  

$$
\operatorname{ARA}(c)=-{\frac{u^{\prime\prime}(c)}{u^{\prime}(c)}}={\frac{1}{\alpha c+\beta}}
$$  

for some constants $\alpha,\beta$ such that $\alpha c+\beta>0$ for all relevant $c$ .HARA utility functions are sometimes referred to as affine (or linear) risk tolerance utility functions since the absolute risk tolerance is  

$$
\operatorname{ART}(c)={\frac{1}{\operatorname{ARA}(c)}}=\alpha c+\beta.
$$  

The risk cautiousness is $\mathrm{ART}^{\prime}(c)=\alpha$  

How do the HARA utility functions look like? First, let us take the case $\alpha=0$ , which implies that the absolute risk aversion is constant (so-called CARA utility) and $\beta$ must be positive.  

$$
{\frac{d(\ln u^{\prime}(c))}{d c}}={\frac{u^{\prime\prime}(c)}{u^{\prime}(c)}}=-{\frac{1}{\beta}}
$$  

implies that  

$$
\ln u^{\prime}(c)=-{\frac{c}{\beta}}+k_{1}\quad\Rightarrow\quad u^{\prime}(c)=e^{k_{1}}e^{-c/\beta}
$$  

for some constant $k_{1}$ . Hence,  

$$
u(c)=-\frac{1}{\beta}e^{k_{1}}e^{-c/\beta}+k_{2}
$$  

for some other constant $k_{2}$ . Applying the fact that increasing affine transformations do not change. decisions, the basic representative of this class of utility functions is the negative exponential utility function  

$$
u(c)=-e^{-a c},\quad c\in\mathbb{R},
$$  

where the parameter $a=1/\beta$ is the absolute risk aversion. Constant absolute risk aversion is certainly not very reasonable. Nevertheless, the negative exponential utility function is sometimes used for computational purposes in connection with normally distributed returns, e.g. in one-period models.  

Next, consider the case $\alpha\neq0$ . Applying the same procedure as above we find  

$$
{\frac{d(\ln u^{\prime}(c))}{d c}}={\frac{u^{\prime\prime}(c)}{u^{\prime}(c)}}=-{\frac{1}{c+\beta}}\quad\Rightarrow\quad\ln u^{\prime}(c)=-{\frac{1}{\alpha}}\ln(\alpha c+\beta)+k_{1}
$$  

so that  

$$
u^{\prime}(c)=e^{k_{1}}\exp\left\{-\frac{1}{\alpha}\ln(\alpha c+\beta)\right\}=e^{k_{1}}\left(\alpha c+\beta\right)^{-1/\alpha}.
$$  

For $\alpha=1$ this implies that  

$$
u(c)=e^{k_{1}}\ln(c+\beta)+k_{2}.
$$  

The basic representative of such utility functions is the extended log utility function  

$$
u(c)=\ln\left(c-{\bar{c}}\right),\quad c>{\bar{c}},
$$  

where we have replaced. $\beta$ by $-c$ . For $\alpha\neq1$ , Equation (5.8) implies that  

$$
u(c)=\frac{1}{\alpha}e^{k_{1}}\frac{1}{1-\frac{1}{\alpha}}\left(\alpha c+\beta\right)^{1-1/\alpha}+k_{2}.
$$  

For $\alpha<0$ , we can write the basic representative is  

$$
u(c)=-\left(\bar{c}-c\right)^{1-\gamma},\quad c<\bar{c},
$$  

where $\gamma=1/\alpha<0$ . We can think of $\bar{c}$ as a satiation level and call this subclass satiation HARA utility functions. The absolute risk aversion is  

$$
\mathrm{ARA}(c)={\frac{-\gamma}{{\bar{c}}-c}},
$$  

which is increasing in. $c$ , conflicting with intuition and empirical studies. Some older financial models used the quadratic utility function, which is the special case with $\gamma=-1$ so that $u(c)=$ $-\left(\bar{c}-c\right)^{2}$ . An equivalent utility function is. $u(c)=c-a c^{2}$  

For $\alpha>0$ (and $\alpha\neq1$ ), the basic representative is  

$$
u(c)={\frac{(c-{\bar{c}})^{1-\gamma}}{1-\gamma}},\quad c>{\bar{c}},
$$  

where $\gamma=1/\alpha>0$ . The limit as $\gamma\to1$ Of the equivalent utility function $\frac{(c-\bar{c})^{1-\gamma}-1}{1-\gamma}$ is equal to thee extended log utility function $u(c)=\ln(c-\bar{c})$ . We can think of $c$ as a subsistence level of wealth or consumption (which makes sense only if $\bar{c}\geq0$ ) and refer to this subclass as subsistence HARA utility functions. The absolute and relative risk aversions are  

$$
\mathrm{ARA}(c)={\frac{\gamma}{c-{\bar{c}}}},\quad\mathrm{RRA}(c)={\frac{\gamma c}{c-{\bar{c}}}}={\frac{\gamma}{1-({\bar{c}}/c)}},
$$  

which are both decreasing in $c$ . The relative risk aversion approaches $\infty$ for $c\to\bar{c}$ and decreases to the constant $\gamma$ for $c\to\infty$ . Clearly, for $\bar{c}=0$ , we are back to the CRRA utility functions so that these also belong to the HARA family.  

Mean-variance preferences. For some problems it is convenient to assume that the expected utility associated with an uncertain consumption plan only depends on the expected value and the variance of the consumption plan. This is certainly true if the consumption plan is a normally distributed random variable since its probability distribution is fully characterized by the mean and variance. However, it is generally not appropriate to use a normal distribution for consumption (or wealth or asset returns).  

For a quadratic utility function, $u(c)=c-a c^{2}$ , the expected utility is.  

$$
\operatorname{E}[u(c)]=\operatorname{E}\left[c-a c^{2}\right]=\operatorname{E}[c]-a\operatorname{E}\left[c^{2}\right]=\operatorname{E}[c]-a\left(\operatorname{Var}[c]+\operatorname{E}[c]^{2}\right),
$$  

which is indeed a function of the expected value and the variance of the consumption plan. Alas, the quadratic utility function is inappropriate for several reasons. Most importantly, it exhibits increasing absolute risk aversion.  

For a general utility function the expected utility of a consumption plan will depend on all moments. This can be seen by the Taylor expansion of. $u(c)$ around the expected consumption, $\operatorname{E}[c]$  

$$
u(c)=u(\mathrm{E}[c])+u^{\prime}(\mathrm{E}[c])(c-\mathrm{E}[c])+\frac{1}{2}u^{\prime\prime}(\mathrm{E}[c])(c-\mathrm{E}[c])^{2}+\sum_{n=3}^{\infty}\frac{1}{n!}u^{(n)}(\mathrm{E}[c])(c-\mathrm{E}[c])^{n},
$$  

where $u^{(n)}$ is the $n$ 'th order derivative of $u$ . Taking expectations, we get  

$$
\operatorname{E}[u(c)]=u(\operatorname{E}[c])+{\frac{1}{2}}u^{\prime\prime}(\operatorname{E}[c])\operatorname{Var}[c]+\sum_{n=3}^{\infty}{\frac{1}{n!}}u^{(n)}(\operatorname{E}[c])\operatorname{E}\left[(c-\operatorname{E}[c])^{n}\right].
$$  

Here $\mathrm{E}\left[(c-\mathrm{E}[c])^{n}\right]$ is the central moment of order $n$ . The variance is the central moment of order 2.. Obviously, a greedy investor (which just means that. $u$ is increasing) will prefer higher expected consumption to lower for fixed central moments of order 2 and higher. Moreover, a risk-averse investor (so that $u^{\prime\prime}<0$ ) will prefer lower variance of consumption to higher for fixed expected. consumption and fixed central moments of order 3 and higher. But when the central moments of order 3 and higher are not the same for all alternatives, we cannot just evaluate them on the basis of their expectation and variance. With quadratic utility, the derivatives of. $u$ of order 3 and higher are zero so there it works. In general, mean-variance preferences can only serve as an approximation of the true utility function.  

# 5.6.2 What do we know about individuals' risk aversion?  

From our discussion of risk aversion and various utility functions we expect that individuals are risk averse and exhibit decreasing absolute risk aversion. But can this be supported by empirical evidence? Do individuals have constant relative risk aversion? And what is a reasonable level of risk aversion for individuals?  

You can get an idea of the risk attitudes of an individual by observing how they choose between. risky alternatives. Some researchers have studied this by setting up "laboratory experiments" in which they present some risky alternatives to a group of individuals and simply see what they. prefer. Some of these experiments suggest that expected utility theory is frequently violated,. see e.g. Grether and Plott (1979). However, laboratory experiments are problematic for several. reasons. You cannot be sure that individuals will make the same choice in what they know is an experiment as they would in real life. It is also hard to formulate alternatives that resemble the rather complex real-life decisions. It seems more fruitful to study actual data on how individuals have acted confronted with real-life decision problems under uncertainty. A number of studies do that.  

Friend and Blume (1975) analyze data on household asset holdings. They conclude that the data is consistent with individuals having roughly constant relative risk aversion and that the coefficients of relative risk aversion are "on average well in excess of one and probably in excess of two' (quote from page 900 in their paper). Pindyck (1988) finds support of a relative risk aversion between 3 and 4 in a structural model of the reaction of stock prices to fundamental variables.  

Other studies are based on insurance data. Using U.S. data on so-called property/liability. insurance, Szpiro (1986) finds support of CRRA utility with a relative risk aversion coefficient. between 1.2 and 1.8.  Cicchetti and Dubin (1994) work with data from the U.S. on whether. individuals purchased an insurance against the risk of trouble with their home telephone line. They conclude that the data is consistent with expected utility theory and that a subsistence HARA utility function performs better than log utility or negative exponential utility..  

Ogaki and Zhang (2001) study data on individual food consumption from Pakistan and India. and conclude that relative risk aversion is decreasing for poor individuals, which is consistent with a subsistence HARA utility function..  

It is an empirical fact that even though consumption and wealth have increased tremendously over the years, the magnitude of real rates of return has not changed dramatically. As indicated by (5.5) relative risk premia are approximately proportional to the relative risk aversion. As we. shall see in later chapters, basic asset pricing theory implies that relative risk premia on financial assets (in terms of expected real return in excess of the real risk-free return) will be proportional to the "average" relative risk aversion in the economy. If the "average' relative risk aversion was. significantly decreasing (increasing) in the level of consumption or wealth, we should have seen. decreasing (increasing) real returns on risky assets in the past. The data seems to be consistent. with individuals having "on average" close to CRRA utility..  

To get a feeling of what a given risk aversion really means, suppose you are confronted with two consumption plans. One plan is a sure consumption of $c$ , the other plan gives you $(1-\alpha)\bar{c}$ with probability 0.5 and $(1+\alpha)\bar{c}$ with probability 0.5. If you have a CRRA utility function  

<html><body><table><tr><td>=RRA</td><td>α = 1%</td><td>Q = 10% Q = 50%</td></tr><tr><td>0.5</td><td>0.00%</td><td>0.25% 6.70%</td></tr><tr><td>1</td><td>0.01%</td><td>0.50% 13.40%</td></tr><tr><td>2</td><td>0.01%</td><td>1.00% 25.00%</td></tr><tr><td>5</td><td>0.02%</td><td>2.43% 40.72%</td></tr><tr><td>10</td><td>0.05%</td><td>4.42% 46.00%</td></tr><tr><td>20</td><td>0.10%</td><td>6.76% 48.14%</td></tr><tr><td>50</td><td>0.24%</td><td>8.72% 49.29%</td></tr><tr><td>100</td><td>0.43%</td><td>9.37% 49.65%</td></tr></table></body></html>  

Table 5.5: Relative risk premia for a fair gamble of the fraction $\alpha$ of your consumption.  

$u(c)=c^{1-\gamma}/(1-\gamma)$ , the certainty equivalent $c^{*}$ of the risky plan is determined by  

$$
\frac{1}{1-\gamma}\left(c^{*}\right)^{1-\gamma}=\frac{1}{2}\frac{1}{1-\gamma}\left((1-\alpha)\bar{c}\right)^{1-\gamma}+\frac{1}{2}\frac{1}{1-\gamma}\left((1+\alpha)\bar{c}\right)^{1-\gamma},
$$  

which implies that  

$$
c^{*}=\left(\frac{1}{2}\right)^{1/(1-\gamma)}\left[(1-\alpha)^{1-\gamma}+(1+\alpha)^{1-\gamma}\right]^{1/(1-\gamma)}\bar{c}.
$$  

The risk premium $\lambda({\bar{c}},\alpha)$ is  

$$
\lambda(\bar{c},\alpha)=\bar{c}-c^{*}=\left(1-\left(\frac{1}{2}\right)^{1/(1-\gamma)}\left[(1-\alpha)^{1-\gamma}+(1+\alpha)^{1-\gamma}\right]^{1/(1-\gamma)}\right)\bar{c}.
$$  

Both the certainty equivalent and the risk premium are thus proportional to the consumption level $c$ . The relative risk premium. $\lambda(\bar{c},\alpha)/\bar{c}$ is simply one minus the relative certainty equivalent $c^{*}/\bar{c}$ . These equations assume $\gamma\neq1$ . In Exercise 5.5 you are asked to find the certainty equivalent and risk premium for log-utility corresponding to $\gamma=1$  

Table 5.5 shows the relative risk premium for various values of the relative risk aversion coefficient. $\gamma$ and various values of. $\alpha$ , the "size' of the risk. For example, an individual with $\gamma=5$ is willing to sacrifice 2.43% of the safe consumption in order to avoid a fair gamble of. $10\%$ of that consumption. level. Of course, even extremely risk averse individuals will not sacrifice more than they can loose but in some cases it is pretty close. Looking at these numbers, it is hard to believe in. $\gamma$ -values outside, say, [1, 10]. In Exercise 5.6 you are asked to compare the exact relative risk premia shown in the table with the approximate risk premia given by (5.5)..  

# 5.6.3 Two-good utility functions and the elasticity of substitution  

Consider an atemporal utility function $f(c,z)$ of the consumption of two different goods at the same time. An indifference curve in the. $(c,z)$ -space is characterized by $f(c,z)=k$ for some constant $k$ Changes in $c$ and $z$ along an indifference curve are linked by.  

$$
\frac{\partial f}{\partial c}d c+\frac{\partial f}{\partial z}d z=0
$$  

so that the slope of the indifference curve (also known as the marginal rate of substitution) is  

$$
{\frac{d z}{d c}}=-{\frac{\frac{\partial f}{\partial z}}{\frac{\partial f}{\partial c}}}.
$$  

Unless the indifference curve is linear, its slope will change along the curve. Indifference curves are generally assumed to be convex. The elasticity of substitution tells you by which percentage you need to change $z/c$ in order to obtain a one percent change in the slope of the indifference curve. It is a measure of the curvature or convexity of the indifference curve. If the indifference curve is very curved, you only have to move a little along the curve before its slope has changed by one percent. Hence, the elasticity of substitution is low. If the indifference curve is almost linear, you have to move far away to change the slope by one percent. In that case the elasticity of substitution is. very high. Formally, the elasticity of substitution is defined as  

$$
\psi=-\frac{d\left(\frac{z}{c}\right)/\frac{z}{c}}{d\left(\frac{\frac{\partial f}{\partial z}}{\frac{\partial f}{\partial z}}\right)/\frac{\frac{\partial f}{\partial z}}{\frac{\partial f}{\partial z}}}=-\frac{\frac{\partial f}{\partial z}/\frac{\partial f}{\partial c}}{z/c}\frac{d\left(z/c\right)}{d\left(\frac{\partial f}{\partial z}/\frac{\partial f}{\partial c}\right)},
$$  

which is equivalent to  

$$
\psi=-\frac{d\ln{(z/c)}}{d\ln{\left(\frac{\partial f}{\partial z}/\frac{\partial f}{\partial c}\right)}}.
$$  

Assume now that  

$$
f(c,z)=(a c^{\alpha}+b z^{\alpha})^{1/\alpha},
$$  

where $\alpha<1$ and $\alpha\neq0$ . Then  

$$
\frac{\partial f}{\partial c}=a c^{\alpha-1}\left(a c^{\alpha}+b z^{\alpha}\right)^{\frac{1}{\alpha}-1},\qquad\frac{\partial f}{\partial z}=b z^{\alpha-1}\left(a c^{\alpha}+b z^{\alpha}\right)^{\frac{1}{\alpha}-1},
$$  

and thus  

$$
{\frac{\frac{\partial f}{\partial z}}{\frac{\partial f}{\partial c}}}={\frac{b}{a}}\left({\frac{z}{c}}\right)^{\alpha-1}.
$$  

Computing the derivative with respect to $z/c$ , we get  

$$
\frac{d\left(\frac{\frac{\partial f}{\partial z}}{\frac{\partial f}{\partial c}}\right)}{d\left(\frac{z}{c}\right)}=\frac{b}{a}(\alpha-1)\left(\frac{z}{c}\right)^{\alpha-2}
$$  

and thus  

$$
\psi=-\frac{\frac{b}{a}\left(\frac{z}{c}\right)^{\alpha-1}}{\frac{z}{c}}\frac{1}{\frac{b}{a}(\alpha-1)\left(\frac{z}{c}\right)^{\alpha-2}}=-\frac{1}{\alpha-1}=\frac{1}{1-\alpha},
$$  

which is independent of. $(c,z)$ . Therefore the utility function (5.13) is referred to as CES (Constant Elasticity of Substitution) utility..  

For the Cobb-Douglas utility function  

$$
f(c,z)=c^{a}z^{1-a},\quad0<a<1,
$$  

the intertemporal elasticity of substitution equals 1. In fact, the Cobb-Douglas utility func tion (5.14) can be seen as the limit of the utility function (5.13) assuming $b=1-a$ aS $\alpha\rightarrow0$  
