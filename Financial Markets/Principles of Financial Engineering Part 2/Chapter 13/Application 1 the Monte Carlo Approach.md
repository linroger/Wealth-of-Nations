---
tags:
  - '#digital_options'
  - '#discretization_bias'
  - '#european_options'
  - '#fx_options'
  - '#monte_carlo_method'
  - '#option_pricing'
  - '#path_dependency'
  - '#risk_neutral_dynamics'
---
# 13.2 APPLICATION 1: THE MONTE CARLO APPROACH  

Consider again the expectation involving a function $C\left(S_{t},t\right)$ of the underlying risk. $S_{t}$ under a working Martingale measure, $\bar{\tilde{P}}$  

$$
\frac{C(S_{t},t)}{Z_{t}}=E_{t}^{\tilde{P}}\left[\frac{C(S_{T},T)}{Z_{T}}\right]
$$  

where $S_{t}$ and $Z_{t}$ are two arbitrage-free asset prices at time t. $Z_{t}$ is used as the normalizing asset and is instrumental in defining $\tilde{P}.\cal{C}(S_{t},t)$ may represent a European option premium or any other derivative that depends on $S_{t}$ with expiration $T$  

This equation can be used as a vehicle to calculate a numerical value for $C(S_{t},t)$ , if we are given the probability measure $\tilde{P}$ and if we know $Z_{t}$ There are two ways of doing this. First, we can. try to solve analytically for the expectation and obtain the resulting. $C(S_{t},\textit{t})$ as a closed-form formula. When the current value of the normalizing asset, $Z_{t}$ is known, this would amount to taking the integral:  

$$
C(S_{t},t)=Z_{t}\left[\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}\frac{C(S_{T},T)}{Z_{T}}\tilde{f}(S_{T},Z_{T})\mathrm{d}S_{T}\mathrm{d}Z_{T}\right]
$$  

where $\tilde{f}(.)$ is the joint conditional probability density function of. $S_{T},Z_{T}$ in terms of the $\tilde{P}$ probability.2 $Z_{T}$ on the right-hand side is considered to be random and possibly correlated with $S_{T}.$ As a result, the probability $\tilde{P}$ would apply to both random variables,. $S_{T}$ and $Z_{T}$  

With judicious choices of. $Z_{t}$ , we can however make $Z_{T}$ a constant. For example, if we choose. $Z_{t}$ as the default-free discount bond that matures at time $T$  

$$
Z_{T}=1
$$  

It is clear that such normalization greatly simplifies the pricing exercise, since $\tilde{f}(.)$ is then a univariate conditional density.  

But, even with this there is a problem with the analytical method. Often, there are no closedform solutions for the integrals, and a nice formula tying $S_{t}$ to $Z_{t}$ and other parameters of the distribution function $\tilde{P}$ may not exist. The value of the integral can still be calculated, although not through a closed-form formula. It has to be evaluated numerically.  

One way of doing this is the Monte Carlo method.? This section briefly summarizes the procedure. We begin with a simple example. Suppose a random variable, $^{4}X$ with a known normal distribution denoted by $P$ , is given:5  

$$
X\sim N(\mu,\sigma)
$$  

Suppose we have a known function $g(X)$ of $X$ How would we calculate the expectation $E^{P}$ $[g(X)]$ , knowing that $E^{P}[g(X)]<\infty\stackrel{.}{.}$ ? One way, of course, is by using the analytical approach mentioned earlier. Take the integral  

$$
E^{P}[g(X)]=\int_{-\infty}^{\infty}g(x)\biggl(\frac{1}{\sqrt{2\pi\sigma^{2}}}e^{-(1/2\sigma^{2})(x-\mu)^{2}}\biggr)\mathrm{d}x
$$  

if a closed-form solution exists.  

But there is a second, easier way. We can invoke the law of large numbers and realize that given a large sample of realizations of $X$ denoted by $x_{i},$ the sample mean of any function of the $x_{i}$ say $g(x_{i})$ , will be close to the true expected value $E^{P}\left[g(X)\right]$ . So, the task of calculating an arbitrarily good approximation of $E^{P}[g(X)]$ reduces to drawing a very large sample of $x_{i}$ from the right. distribution. Using random number generators, and the known distribution function of $X$ we can obtain $N$ replicas of $x_{i}$ . These would be generated independently, and the law of large numbers would apply:  

$$
{\frac{1}{N}}\sum_{i=1}^{N}g(x_{i})\to E^{p}[g(X)]
$$  

The condition $E^{P}\left[g(X)\right]<\infty$ is sufficient for this convergence to hold. We now put this discus. sion in the context of asset pricing.  

# 13.2.1 PRICING WITH MONTE CARLO  

With the Monte Carlo method, an expectation is evaluated by first generating a sequence of replicas of the random variable of interest from a prespecified model, and then calculating the sample mean. The application of this method to pricing equations is immediate. In fact, the fundamental. theorem provides the risk-neutral probability, $\tilde{P}$ , such that for any arbitrage-free asset price $S_{t},$  

$$
{\frac{S_{t}}{B_{t}}}=E_{t}^{\tilde{P}}\left[{\frac{S_{T}}{B_{T}}}\right]
$$  

Here, the normalizing variable denoted earlier by $Z_{t}$ is taken to be a savings account and is now. denoted by $B_{t}$ . This asset is defined as.  

$$
B_{t}=e^{\int_{0}^{t}r_{u}\mathrm{d}u}
$$  

$r_{u}$ being the continuously compounded instantaneous spot rate. It represents the time $t$ value of an investment that was one dollar at time $t=0$ . The integral in the exponent means that $r_{u}$ is not constant during $u\in[t,T]$ . If $r_{t}$ is a random variable, then we will need joint conditional distribution functions in order to select replicas of $S_{T}$ and $B_{T}.$ We have to postulate a model that describes the joint dynamics of $S_{T},B_{T}$ and that ties the information at time $t$ to the random numbers generated for time $T.$ We begin with a simple case where $r_{t}$ is constant at $r.$  

# 13.2.1.1 Pricing a call with constant spot rate  

Consider the calculation of the price of a European call option with strike $K$ and expiration $T$ written on $S_{t}$ in a world where all Black-Scholes assumptions are satisfied. Using $B_{t}$ in Eq. (13.9) as the normalizing asset, Eq. (13.8) becomes  

$$
\frac{C(t)}{e^{r t}}=E_{t}^{\tilde{P}}\left[\frac{C T}{e^{r T}}\right]
$$  

where $C(t)$ denotes the call premium that depends on $S_{t}t,K,r$ and $\sigma$ . After simplifying and rearranging  

$$
C(t)=e^{-r(T-t)}E_{t}^{\tilde{P}}[C(T)]
$$  

where  

$$
C(T)=\operatorname*{max}[S_{T}-K,0]
$$  

The Monte Carlo method can easily be applied to the right-hand side of Eq. (1. to obtain $C(t)$  

Using the savings account normalization, we can write down the discretized risk-neutral dynamics for $S_{t}$ for discrete intervals of size $0<\Delta$  

$$
S_{t+\Delta}=(1+r\Delta)S_{t}+\sigma S_{t}(\Delta W_{t})
$$  

where it is assumed that the percentage volatility. $\sigma$ is constant and that the disturbance term,. $\Delta W_{t}$ is a normally distributed random variable with mean zero and variance $\Delta$  

$$
\Delta W_{t}\sim N(0,\Delta)
$$  

The $r$ enters the SDE due to the use of the risk-neutral measure $\tilde{P}$ We can easily calculate replicas of $S_{T}$ using these dynamics:  

1. Select the size of $\Delta$ , and then use a proper pseudo-random number generator, to generate the random variable $\Delta W_{t}$ from a normal distribution.   
2. Use the current value $S_{t}$ , the parameter values $r,\sigma$ , and the dynamics in Eq. (13.13) to obtain the $N$ terminal values ${S_{T}^{j},j}=\mathbf{\bar{1}},2,...,N.$ Here $j$ will denote a random path generated by the Monte Carlo exercise.  

3. Substitute these into the payoff function,  

$$
C(T)^{j}=\operatorname*{max}[S_{T}^{j}-K,0]
$$  

and obtain $N$ replicas of $C(T)^{j}$  

4. Finally, calculate the sample mean and discount it properly to get $C(t)$  

$$
C(t)=e^{-r(T-t)}\frac{1}{N}\sum_{j=1}^{N}C(T)^{j}
$$  

This procedure gives the arbitrage-free price of the call option. We now consider a simple example.  

# EXAMPLE  

Consider pricing the following European vanilla call written on $S_{t}$ the EUR/USD exchange rate, which follows the discretized (approximate) SDE:  

$$
S_{t_{i}}^{j}=S_{t_{i-1}}^{j}+(r-r^{f})S_{t_{i-1}}^{j}\Delta+\sigma S_{t_{i-1}}^{j}\sqrt{\Delta}\in\d S_{i}^{j}
$$  

where the drift is the differential between the domestic and foreign interest rates.  

We are given the following data on a call with strike $K=1.0950$  

$$
r=2\%r^{f}=3\%t_{0}=0,T=5\mathrm{days}=1.09\sigma=0.10
$$  

A financial engineer decides to select. $N=3$ trajectories to price this call. The discrete nterval is selected as $\Delta=1$ day.  

The software Mathematica provides the following standard normal random numbers:  

$$
\{0.763,0.669,0.477,0.287,1.81,-0.425\}
$$$$
\begin{array}{c}{{\{\cup./0>,\cup.\cup\cup>,\cup.+\prime}~/~,\cup..20~,\cup.\cup1,-\cup.+\angle{\mathcal{I}}\}}}\ {{\{1.178,-0.109,-0.310,-2.130,-0.013,0.421141\}}}\ {{\{-0.922,0.474,-0.556,0.400,-0.890,-2.736\}}}\end{array}
$$  

Using these in the discretized SDE,  

$$
S_{i}^{j}=\left(1+(0.02-0.03)\frac{1}{365}\right)S_{i-1}^{j}+0.10S_{i-1}^{j}\sqrt{\frac{1}{365}}\epsilon_{i}^{j}
$$  

we get the trajectories:  

<html><body><table><tr><td>Path</td><td>Day 1</td><td>Day 2</td><td>Day 3</td><td>Day 4</td><td>Day 5</td></tr><tr><td>1</td><td>1.0937</td><td>1.0965</td><td>1.0981</td><td>1.1085</td><td>1.1060</td></tr><tr><td>2</td><td>1.0893</td><td>1.0875</td><td>1.0754</td><td>1.0753</td><td>1.0776</td></tr><tr><td>3</td><td>1.0927</td><td>1.08946</td><td>1.0917</td><td>1.086</td><td>1.0710</td></tr></table></body></html>  

For the case of a plain vanilla euro call, with strike $K=1.095$ , only the first trajectory. ends in-the-money, so that.  

$$
C(T)^{1}=0.011,\quad C(T)^{2}=0,\quad C(T)^{3}=0
$$  

Using continuous compounding the call premium becomes  

$$
C(t)=\mathrm{Exp}\left(-0.02\frac{5}{365}\right)\frac{1}{3}[0.011+0+0]
$$  

$$
C(t)=0.0037
$$  

Obviously, the parameters of this model are selected to illustrate the application of the Monte Carlo procedure, and no real-life application would price securities with such a small number of trajectories. However, one important wrinkle has to be noted. The drift of this SDE was given by $(\boldsymbol{r}-\boldsymbol{r}^{f})S_{t}\Delta$ and not by $r S_{t}\Delta$ , which was the case of stock price dynamics. This modification will be dealt with below. Foreign currencies pay foreign interest rates and the risk-free interest rate differentials should be used. We discuss this in more detail in the following section.  

# 13.2.2 PRICING BINARY FX OPTIONS  

This section applies the Monte Carlo technique to pricing digital or binary options in foreign exchange markets. We consider the following elementary instrument:  

If the price of a foreign currency, denoted by. $S_{t}$ exceeds the level $K$ at expiration, the option holder will receive the payoff $R$ denoted in domestic currency. Otherwise the option holder. receives nothing. The option is of European style and has expiration date $T.$ The option will be sold for $C(t)$  

We would like to price this binary FX option using Monte Carlo. However, because the underlying is an exchange rate, some additional structure needs to be imposed on the environment and we discuss this first. This is a good example of the use of the fundamental theorem. It also provides a good occasion to introduce some elementary aspects of option pricing in FX markets.  

# 13.2.2.1 Obtaining the risk-neutral dynamics  

In the case of vanilla options written on stock prices, we assumed that the underlying stock pays no dividends and that the stock price follows a geometric continuous time process such as.  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}
$$  

with $\mu$ being an unknown drift coefficient representing the market's expected percentage appreciation of the stock and $\sigma$ being a constant percentage volatility parameter whose value has to be. obtained. $W_{t},$ finally, represents a Wiener process..  

Invoking the fundamental theorem of asset pricing, we then replaced the unknown drift term $\mu$ by the risk-free interest rate $r$ assumed to be constant. In the case of options written on foreign exchange rates, some of these assumptions need to be modified. We can preserve the overall geo-. metric structure of the $S_{t}$ process, but we have to change the assumption concerning dividends. A foreign currency is, by definition, some interbank deposit and will earn foreign (overnight) interest. According to the fundamental theorem, we can replace the real-world drift $\mu$ by the interest. rate differential,. $r_{t}-r_{t}^{f}$ , where $r_{t}^{f}$ is the foreign instantaneous spot rate and $r_{t}$ is, as usual, the. domestic rate. Thus, if spot rates are constant,  

$$
r_{t}=r,r_{t}^{f}=r^{f}\quad\forall t
$$  

This gives the arbitrage-free dynamics:6  

$$
\mathrm{d}S_{t}=(r-r^{f})S_{t}\mathrm{d}t+\sigma S_{t}W_{t}\quad t\in[0,\infty)
$$  

The rationale behind using the interest rate differential, instead of the spot rate $r$ as the riskneutral drift is a direct consequence of the fundamental theorem when the asset considered is a foreign currency. Since this chapter is devoted to applications of the fundamental theorem, we prefer to discuss this briefly.  

Using the notation presented in Chapter 12, we take $S_{t}$ as being the number of dollars paid for one unit of foreign currency. The fundamental theorem of asset pricing introduced in Chapter 12 implies that we can use the state prices $\{Q^{i}\}$ for states $i=1,...,n$ , and write  

$$
S_{t}=\sum_{i=1}^{n}(1+r^{f}\Delta)S_{T}^{i}Q^{i}
$$  

According to this, one unit of foreign currency will be worth $S_{T}^{i}$ dollars in state $i$ of time $T.$ and it will also earn. $r^{f}$ per annum in interest during the period $\Delta=T-t.$ Normalizing with the domes-. tic savings account, this becomes  

$$
S_{t}=\sum_{i=1}^{n}{\frac{(1+r^{f}\Delta)}{(1+r\Delta)}}S_{T}^{i}(1+r\Delta)Q^{i}
$$  

We now choose the risk-neutral probabilities as  

$$
\tilde{p}_{i}=(1+r\Delta)Q^{i}
$$  

and rearrange Eq. (13.30) to obtain the expected gross return of $S_{t}$ during $\Delta$  

$$
\frac{\left(1+r\Delta\right)}{\left(1+r^{f}\Delta\right)}=E_{t}^{\tilde{P}}\left[\frac{S_{T}}{S_{t}}\right]
$$  

Here, the left-hand side can be approximated as'  

$$
(1+r\Delta-r^{f}\Delta)
$$  

which means that $S_{t}$ is expected to change at an annual rate of $(r-r^{f})$ under the risk-neutral probability $\tilde{P}$ This justifies the continuous time risk-neutral drift of the dynamics:  

$$
\mathrm{d}S_{t}=(r-r^{f})S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}
$$  

Now that the dynamics are specified, the next step is selecting the Monte Carlo trajectories.  

# 13.2.2.2 Monte Carlo process  

Suppose we would like to price our digital option in such a framework. How could we do this using the Monte Carlo approach? Given that the arbitrage-free dynamics for $S_{t}$ are obtained, we can simply apply the steps outlined earlier.  

In particular, we need to generate random paths starting from the known current value for. $S_{t}$ This can be done in two ways. We can first solve the SDE in Eq. (13.34) and then select random replicas from the resulting closed-form formula, if any. The second way is to discretize the dynamics in Eq. (13.34), and proceed as discussed in the previous section. Suppose we decided to proceed by first choosing a discrete interval $\Delta$ , and then discretizing the dynamics:  

$$
\boldsymbol{S_{t+\Delta}}=\boldsymbol{S_{t}}+(\boldsymbol{r}-\boldsymbol{r^{f}})\boldsymbol{S_{t}}\boldsymbol{\Delta}+\sigma\boldsymbol{S_{t}}\boldsymbol{\Delta W_{t}}
$$  

The next step would be to use a random number generator to obtain $N$ sequences of standard normal random variables $\{\in_{i}^{j},i=1,...,k,j=1,...,\bar{N}\}$ and then calculate the $N$ simulated trajectories using the discretized SDE:  

$$
S_{t_{i}}^{j}=S_{t_{i-1}}^{j}+(r-r^{f})S_{t_{i-1}}^{j}\Delta+\sigma S_{t_{i-1}}^{j}\sqrt{\Delta}\in\d_{i}^{j}
$$  

where the superscripte $j$ denotes the jth simulated trajectory and where $\Delta=t_{i}-t_{i-1}$  

Once the paths $\left\{S_{t_{i}}^{j}\right\}$ are obtained, the arbitrage-free value of the digital call option premium $C$ $(t)$ that pays $R$ at expiration can be found by using the equality  

$$
C(t)=\mathrm{Re}^{-r(T-t)}E_{t}^{\tilde{P}}\left[I_{\{S_{T}>K\}}\right]
$$  

where the symbol $I_{\{S_{T}>K\}}$ is the indicator function that determines whether at time $T.$ the $S_{T}$ exceeds $K$ or not:  

$$
I_{\{S_{T}>K\}}=\left\{{1\atop{0}}\quad{\mathrm{IF}}S_{T}>K\right.
$$  

This means that $I_{\{S_{T}>K\}}$ equals 1 if the option expires in-the-money; otherwise it is 0. According to the expected payoff in Eq. (13.37), the arbitrage-free $C(t)$ depends on the value of $E_{t}^{\tilde{P}}\big[I_{\{S_{T}>K\}}\big]$ . The latter can be written as  

$$
E_{t}^{\tilde{P}}\big[I_{\{S_{T}>K\}}\big]=\operatorname{Prob}(S_{T}>K)
$$  

Thus  

$$
C(t)=\mathrm{Re}^{-r(T-t)}\mathrm{Prob}(S_{T}>K)
$$  

This equation is easy to interpret. The value of the digital option is equal to the risk-neutral probability that $S_{T}$ will exceed $K$ times the present value of the constant payoff $R$  

Under these conditions, the role played by the Monte Carlo method is simple. We generate $N$ paths for the exchange rate starting from the current observation $S_{t},$ and then calculate the proportion of paths that would end up above the level $K.$ Once this tally is made, denoting this number by $m$ , the arbitrage-free value of the option will be  

$$
\begin{array}{c}{{C(t)=e^{-r(T-t)}R~\mathrm{(Prob}(S_{T}>K))}}\ {{\cong e^{-r(T-t)}R\Big(\frac{\mathrm{m}}{\mathrm{N}}\Big)}}\end{array}
$$  

Thus, in this case the Monte Carlo method is used to calculate a special expected value, which is the risk-neutral probability of the event $\{S_{T}>K\}$ . The following section discusses two examples.  

# 13.2.3 PATH DEPENDENCY  

In the examples discussed thus far, we used the Monte Carlo method to generate trajectories for an underlying risk $S_{t}$ yet considered only the time $T$ values of these trajectories in calculating the desired quantity $C(S_{t},t)$ . The other elements of the trajectory were not directly used in pricing.  

This changes if the asset under consideration makes interim payouts or is subject to some other restrictions as in the case of barrier options. When. $C\left({{S}_{t}},t\right)$ denotes the price of a barrier call option with barrier $H$ , the option may knock in or out depending on the event. $S_{u}<H$ during the period $u\in[t,T]$ . Consider the case of a down-and-out call. In pricing this instrument, once a Monte Carlo. trajectory is obtained, the whole trajectory needs to be used to determine if the condition $S_{u}<H$ is satisfied by $S_{u}^{j}$ during the entire trajectory. This is one example of the class of assets that are path dependent and hence require direct use of entire Monte Carlo trajectories..  

We now provide two more examples of the application of the Monte Carlo procedure. In the first case, the procedure is applied to a vanilla digital option, and in the second example, we show. what happens when the option is a down-and-out call..  

# EXAMPLE  

Consider pricing a digital option written on. $S_{t}$ the EUR/USD exchange rate with the same structure as in the first example. The digital euro call has strike. $K=1.091$ and pays $\$100$ if it expires in-the-money. The parameters are the same as before:  

$$
r=2\mathcal{A},\quad r^{f}=3\mathcal{H},\quad t_{0}=0,\quad t=5\mathrm{days},\quad S_{t_{0}}=1.09,\quad\sigma=0.10
$$  

The paths for $S_{t}$ are given by  

<html><body><table><tr><td>Path</td><td>Day 1</td><td>Day 2</td><td>Day 3</td><td>Day 4 Day 5</td><td></td></tr><tr><td>1</td><td>1.0937</td><td>1.0965</td><td>1.0981</td><td>1.1085</td><td>1.1060</td></tr><tr><td>2</td><td>1.0893</td><td>1.0875</td><td>1.0780</td><td>1.0850</td><td>1.092</td></tr><tr><td>3</td><td>1.0927</td><td>1.08946</td><td>1.0917</td><td>1.086</td><td>1.0710</td></tr></table></body></html>  

The digital call expires in-the-money if $1.091<S_{T}^{j}$ . There are two incidences of this event in the previous case, and the estimated risk-neutral probability that the option expires in-themoney is 2/3. The option value is calculated as  

$$
C(t)=\mathrm{Exp}\left(-0.02\frac{5}{365}\right)\frac{2}{3}[100]
$$  

$$
C(t)=\S66.6
$$  

Now, consider what happens if we add a knock-out barrier $H=1.08$ . The digital call knocks out if $S_{t}$ falls below this barrier before expiration.  

# EXAMPLE  

All parameters are the same as in the first example, and the paths are given by  

<html><body><table><tr><td>Path</td><td>Day 1</td><td>Day 2</td><td>Day 3</td><td>Day 4</td><td>Day 5</td></tr><tr><td>1</td><td>1.0937</td><td>1.0965</td><td>1.0981</td><td>1.1085</td><td>1.1060</td></tr><tr><td>2</td><td>1.0893</td><td>1.0875</td><td>1.0780</td><td>1.0850</td><td>1.092</td></tr><tr><td>3</td><td>1.0927</td><td>1.08946</td><td>1.0917</td><td>1.086</td><td>1.0710</td></tr></table></body></html>  

The digital knock-out call requires that $1.091<S_{T}^{j}$ and that the trajectory never falls below 1.08. Thus, there is only one incidence of this in this case and the value of the option is calculated as  

$$
C(t)=\mathrm{Exp}\left(-0.02\frac{5}{365}\right)\frac{1}{3}[100]
$$  

$$
C(t)=\$33.3
$$  

Hence, the digital option is cheaper. Also, note that in the case of vanilla call, only the terminal. values were used to calculate the option value, whereas in the case of the knock-out call, the entire trajectory was needed to check the condition. $H<S_{t}$  

# 13.2.4 DISCRETIZATION BIAS AND CLOSED FORMS  

The examples on the Monte Carlo used discrete approximations of SDEs. Assuming that the arbitrage-free dynamics of an asset price. $S_{t}$ can be described by a geometric SDE,  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

we selected an appropriate time interval. $\Delta$ , and ignoring continuous compounding, discretized the SDE  

$$
S_{t+\Delta}=(1+r\Delta)S_{t}+\sigma S_{t}(\Delta W_{t})
$$  

Equation (13.49) is only an approximation of the true continuous time dynamics given by Eq. (13.48).  

For some special SDEs, we can sample the exact. $S_{t}$ . In such special cases, the stochastic differ-. ential equation for. $S_{t}$ can be "solved' for a closed form. The geometric process shown in Eq. (13.48) is one such case. We can directly obtain the value of $S_{T}$ using the closed-form formula:.  

$$
S_{T}=S_{t_{0}}e^{r(T-t_{0})-(1/2)\sigma^{2}(T-t_{0})+\sigma\left(W_{T}-W_{t_{0}}\right)}
$$  

The term $\left(W_{T}-W_{t_{0}}\right)$ will be normally distributed with mean zero and variance. $T-t_{0}$ .Hence, by drawing replicas of this random variable, we can obtain exact replicas for. $S_{T}$ at any $T_{:}$ $t_{0}<T.$ It turns out that even in the case of a mean-reverting model, such closed-form formulas are available. and lend themselves to Monte Carlo pricing. However, in general, we may have to use discretized SDEs that may contain a discretization bias.10  

# 13.2.5 REAL-LIFE COMPLICATIONS  

Obviously, Monte Carlo becomes a complex approach once we go beyond simple examples.. Difficulties arise, yet significant improvements can be made in regard to (i) how to select random numbers with computers, (ii) how to trick the system, such that the greatest accuracy can be. obtained in the shortest time, and (iii) how to reduce the variance of the calculated prices with a. given number of random selections. For these questions, other sources should be considered; we will not discuss them given our focus on financial engineering.11  
