# SOME APPLICATIONS OF THE 13 FUNDAMENTAL THEOREM  

# CHAPTER OUTLINE  

# 13.1 Introduction .. 428  

13.2 Application 1: The Monte Carlo Approach... 429   
13.2.1 Pricing with Monte Carlo ... 430   
13.2.1.1 Pricing a call with constant spot rate . 431   
13.2.2 Pricing Binary FX Options... 433   
13.2.2.1 Obtaining the risk-neutral dynamics . 433   
13.2.2.2 Monte Carlo process.. 435   
13.2.3 Path Dependency .. 436   
13.2.4 Discretization Bias and Closed Forms... 438   
13.2.5 Real-Life Complications . 438   
.3 Application 2: Calibration .... . 438   
13.3.1 Calibrating a Tree .. 439   
13.3.2 Extracting a LIBOR Tree. 439   
13.3.2.1 Pricing functions . 439   
13.3.3 Obtaining the BDT Tree. 441   
13.3.3.1 Specifying the dynamics . 441   
13.3.3.2 The variance of Li . 441   
13.3.4 Calibrating the Tree .. 443   
13.3.5 Uses of the Tree 445   
13.3.5.1 Application: pricing a cap . 445   
13.3.5.2 Some assumptions of the model .. 447   
13.3.5.3 Remarks .. 447   
13.3.6 Real-World Complications .. 448   
13.4 Application 3: Quantos .. 448   
13.4.1 Pricing Quantos... 448   
13.4.2 The PDE Approach . 451   
13.4.2.1 A PDE for quantos. 452   
13.4.3 Quanto Forward.. 453   
13.4.4 Quanto Option.. 453   
13.4.4.1 Black Scholes and dividends.. 454   
13.4.5 How to Hedge Quantos.. 454   
13.4.6 Real-Life Considerations . 454   
13.5 Conclusions. 455   
Suggested Reading .. . 455   
Exercises . 455   
EXCEL Exercises . 456   
MATLAB Exercises. 457  

# 13.1 INTRODUCTION  

The theorem discussed in the previous chapter establishes important no-arbitrage conditions that permit pricing and risk management using Martingale methods. According to these conditions, given unique arbitrage-free state prices, we can obtain a synthetic probability measure, $\tilde{P}$ , under which all asset prices normalized by a particular $Z_{t}$ become Martingales. Letting $C(S_{t},t)$ represent a security whose price depends on an underlying risk $S_{t}.$ , we can write,  

$$
\frac{C(S_{t},t)}{Z_{t}}=E_{t}^{\tilde{P}}\left[\frac{C(S_{T},T)}{Z_{T}}\right]
$$  

As long as positive state prices exist, many such probabilities can be found and each will be associated with a particular normalization. The choice of the right working probability then becomes a matter of convenience and data availability.  

The equality in Eq. (13.1) can be evaluated numerically using various methods. The arbitragefree price $S_{t}$ can be calculated by evaluating the expectation and then multiplying by $Z_{t}.$ . But to evaluate the expectation, we would need the probability $\tilde{P}$ , hence, this must be obtained first. A further desirable characteristic is that the future value, $Z_{T}$ , be constant, as it would be in the case of a default-free bond that matures at time $T.$ Hence, $T$ maturity bonds are good candidates for normalization.  

In this chapter, we show three applications of the fundamental theorem. The first application is the Monte Carlo procedure which can be interpreted as a general method to calculate the expectation in Eq. (13.1). This method can be applied straightforwardly when instruments under consideration are of European type. The procedure uses the tools supplied by the fundamental theorem together with the law of large numbers.1  

The second application of the fundamental theorem involves calibration. Calibration is the selection of model parameters using observed arbitrage-free prices from liquid markets. The chapter discusses simple examples of how to calibrate stochastic differential equations and tree models to market data using the fundamental theorem. This is done within the context of the Black Derman Toy (BDT) model.  

The third application of the fundamental theorem introduced in Chapter 12 is more conceptual in nature. We use quanto assets to show how the theorem can be exploited in modeling. Quanto assets provide an excellent vehicle for this, since their pricing involves switches between domestic and foreign risk-neutral measures. Techniques for switching between measures are an integral part of financial engineering and will be discussed further in the next chapter. The application to quantos provides the first step.  

Before we discuss these issues, a note of caution is in order. The discussion in this chapter should be regarded as an overview that presents examples for when to use the fundamental theorem, instead of being a source of how to implement such numerical techniques. Calculations using Monte Carlo or calibration are complex numerical procedures, and a straightforward application may not give satisfactory results. Interested readers can consult the sources provided at the end of the chapter.  

# 13.2 APPLICATION 1: THE MONTE CARLO APPROACH  

Consider again the expectation involving a function $C\left(S_{t},t\right)$ of the underlying risk $S_{t}$ under a working Martingale measure, $\bar{\tilde{P}}$ :  

$$
\frac{C(S_{t},t)}{Z_{t}}=E_{t}^{\tilde{P}}\left[\frac{C(S_{T},T)}{Z_{T}}\right]
$$  

where $S_{t}$ and $Z_{t}$ are two arbitrage-free asset prices at time t. $Z_{t}$ is used as the normalizing asset and is instrumental in defining $\tilde{P}.~C(S_{t},t)$ may represent a European option premium or any other derivative that depends on $S_{t}$ with expiration $T$ .  

This equation can be used as a vehicle to calculate a numerical value for $C(S_{t},\ t)$ , if we are given the probability measure $\tilde{P}$ and if we know $Z_{t}$ . There are two ways of doing this. First, we can try to solve analytically for the expectation and obtain the resulting $C(S_{t},\ t)$ as a closed-form formula. When the current value of the normalizing asset, $Z_{t}$ , is known, this would amount to taking the integral:  

$$
C(S_{t},t)=Z_{t}\left[\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}\frac{C(S_{T},T)}{Z_{T}}\tilde{f}(S_{T},Z_{T})\mathrm{d}S_{T}\mathrm{d}Z_{T}\right]
$$  

where $\tilde{f}(.)$ is the joint conditional probability density function of $S_{T},Z_{T}$ in terms of the $\tilde{P}$ probability.2 $Z_{T}$ on the right-hand side is considered to be random and possibly correlated with $S_{T}$ As a result, the probability $\tilde{P}$ would apply to both random variables, $S_{T}$ and $Z_{T}$ .  

With judicious choices of $Z_{t}$ , we can however make $Z_{T}$ a constant. For example, if we choose $Z_{t}$ as the default-free discount bond that matures at time $T_{\mathbf{\delta}}$ ,  

$$
Z_{T}=1
$$  

It is clear that such normalization greatly simplifies the pricing exercise, since $\tilde{f}(.)$ is then a univariate conditional density.  

But, even with this there is a problem with the analytical method. Often, there are no closedform solutions for the integrals, and a nice formula tying $S_{t}$ to $Z_{t}$ and other parameters of the distribution function $\Tilde{P}$ may not exist. The value of the integral can still be calculated, although not through a closed-form formula. It has to be evaluated numerically.  

One way of doing this is the Monte Carlo method.3 This section briefly summarizes the procedure. We begin with a simple example. Suppose a random variable, $^4X$ , with a known normal distribution denoted by $P$ , is given:5  

$$
X\sim N(\mu,\sigma)
$$  

Suppose we have a known function $g(X)$ of $X$ . How would we calculate the expectation $E^{P}$ $[g(X)]$ , knowing that $E^{P}[g(X)]<\infty^{\prime}$ ? One way, of course, is by using the analytical approach mentioned earlier. Take the integral  

$$
E^{P}[g(X)]=\int_{-\infty}^{\infty}g(x)\biggl(\frac{1}{\sqrt{2\pi\sigma^{2}}}e^{-(1/2\sigma^{2})(x-\mu)^{2}}\biggr)\mathrm{d}x
$$  

if a closed-form solution exists.  

But there is a second, easier way. We can invoke the law of large numbers and realize that given a large sample of realizations of $X$ , denoted by $x_{i},$ the sample mean of any function of the $x_{i}$ , say $g(x_{i})$ , will be close to the true expected value $E^{P}\left[g(X)\right]$ . So, the task of calculating an arbitrarily good approximation of $\boldsymbol{E}^{P}\left[g(\boldsymbol{X})\right]$ reduces to drawing a very large sample of $x_{i}$ from the right distribution. Using random number generators, and the known distribution function of $X$ , we can obtain $N$ replicas of $x_{i}$ . These would be generated independently, and the law of large numbers would apply:  

$$
{\frac{1}{N}}\sum_{i=1}^{N}g(x_{i})\to E^{p}[g(X)]
$$  

The condition $\boldsymbol{E}^{P}\left[\boldsymbol{g}(\boldsymbol{X})\right]<\infty$ is sufficient for this convergence to hold. We now put this discussion in the context of asset pricing.  

# 13.2.1 PRICING WITH MONTE CARLO  

With the Monte Carlo method, an expectation is evaluated by first generating a sequence of replicas of the random variable of interest from a prespecified model, and then calculating the sample mean. The application of this method to pricing equations is immediate. In fact, the fundamental theorem provides the risk-neutral probability, $\tilde{P}$ , such that for any arbitrage-free asset price $S_{t},$  

$$
\frac{S_{t}}{B_{t}}=E_{t}^{\tilde{P}}\left[\frac{S_{T}}{B_{T}}\right]
$$  

Here, the normalizing variable denoted earlier by $Z_{t}$ is taken to be a savings account and is now denoted by $B_{t}$ . This asset is defined as  

$$
B_{t}=e^{\int_{0}^{t}r_{u}\mathrm{d}u}
$$  

$r_{u}$ being the continuously compounded instantaneous spot rate. It represents the time $t$ value of an investment that was one dollar at time $t=0$ . The integral in the exponent means that $r_{u}$ is not constant during $u\in[t,~T]$ . If $\boldsymbol{r}_{t}$ is a random variable, then we will need joint conditional distribution functions in order to select replicas of $S_{T}$ and $B_{T}$ . We have to postulate a model that describes the joint dynamics of $S_{T},B_{T}$ and that ties the information at time $t$ to the random numbers generated for time $T.$ . We begin with a simple case where $\boldsymbol{r}_{t}$ is constant at $r$ .  

# 13.2.1.1 Pricing a call with constant spot rate  

Consider the calculation of the price of a European call option with strike $K$ and expiration $T$ written on $S_{t}$ , in a world where all Black Scholes assumptions are satisfied. Using $B_{t}$ in Eq. (13.9) as the normalizing asset, Eq. (13.8) becomes  

$$
{\frac{C(t)}{e^{r t}}}=E_{t}^{\tilde{P}}\left[{\frac{C T}{e^{r T}}}\right]
$$  

where $C(t)$ denotes the call premium that depends on $S_{t}~t,~K,~r.$ , and $\sigma$ . After simplifying and rearranging  

$$
C(t)=e^{-r(T-t)}E_{t}^{\tilde{P}}[C(T)]
$$  

where  

$$
C(T)=\operatorname*{max}[S_{T}-K,0]
$$  

The Monte Carlo method can easily be applied to the right-hand side of Eq. ( to obtain $C(t)$ .  

Using the savings account normalization, we can write down the discretized risk-neutral dynamics for $S_{t}$ for discrete intervals of size $0<\Delta$ :  

$$
S_{t+\Delta}=(1+r\Delta)S_{t}+\sigma S_{t}(\Delta W_{t})
$$  

where it is assumed that the percentage volatility $\sigma$ is constant and that the disturbance term, $\Delta W_{t}$ , is a normally distributed random variable with mean zero and variance $\Delta$ :  

$$
\Delta W_{t}\sim N(0,\Delta)
$$  

The $r$ enters the SDE due to the use of the risk-neutral measure $\tilde{P}$ . We can easily calculate replicas of $S_{T}$ using these dynamics:  

1. Select the size of $\Delta$ , and then use a proper pseudo-random number generator, to generate the random variable $\Delta W_{t}$ from a normal distribution.   
2. Use the current value $S_{t}$ , the parameter values $r,\sigma$ , and the dynamics in Eq. (13.13) to obtain the $N$ terminal values $S_{T}^{j},j=\bar{1},2,...,N.$ . Here $j$ will denote a random path generated by the Monte Carlo exercise.  

3. Substitute these into the payoff function,  

$$
C(T)^{j}=\operatorname*{max}[S_{T}^{j}-K,0]
$$  

and obtain $N$ replicas of $C(T)^{j}$ .  

4. Finally, calculate the sample mean and discount it properly to get $C(t)$ :  

$$
C(t)=e^{-r(T-t)}\frac{1}{N}{\sum_{j=1}^{N}}C(T)^{j}
$$  

This procedure gives the arbitrage-free price of the call option. We now consider a simple example.  

# EXAMPLE  

Consider pricing the following European vanilla call written on $S_{t}$ , the EUR/USD exchange rate, which follows the discretized (approximate) SDE:  

$$
S_{t_{i}}^{j}=S_{t_{i-1}}^{j}+(r-r^{f})S_{t_{i-1}}^{j}\Delta+\sigma S_{t_{i-1}}^{j}\sqrt{\Delta}\in_{i}^{j}
$$  

where the drift is the differential between the domestic and foreign interest rates.  

We are given the following data on a call with strike $K=1.0950$ :  

$$
r=2\%r^{f}=3\%t_{0}=0,T=5{\mathrm{days}}=1.09\sigma=0.10
$$  

A financial engineer decides to select $N=3$ trajectories to price this call. The discrete interval is selected as $\Delta=1$ day.  

The software Mathematica provides the following standard normal random numbers:  

$$
\{0.763,0.669,0.477,0.287,1.81,-0.425\}
$$$$
\begin{array}{c}{{10.10,0.00>,0.+1/\ ,0.20>,1.01,-0.42>\mathrm{{J}}}}\\ {{\ }}\\ {{\{1.178,-0.109,-0.310,-2.130,-0.013,0.421141\}}}\\ {{\ }}\\ {{\{-0.922,0.474,-0.556,0.400,-0.890,-2.736\}}}\end{array}
$$  

Using these in the discretized SDE,  

$$
S_{i}^{j}=\left(1+(0.02-0.03)\frac{1}{365}\right)S_{i-1}^{j}+0.10S_{i-1}^{j}\sqrt{\frac{1}{365}}\in_{i}^{j}
$$  

we get the trajectories:  

<html><body><table><tr><td>Path</td><td>Day 1</td><td>Day 2</td><td>Day 3</td><td>Day 4</td><td>Day 5</td></tr><tr><td>1</td><td>1.0937</td><td>1.0965</td><td>1.0981</td><td>1.1085</td><td>1.1060</td></tr><tr><td>2</td><td>1.0893</td><td>1.0875</td><td>1.0754</td><td>1.0753</td><td>1.0776</td></tr><tr><td>3</td><td>1.0927</td><td>1.08946</td><td>1.0917</td><td>1.086</td><td>1.0710</td></tr></table></body></html>  

For the case of a plain vanilla euro call, with strike $K=1.095$ , only the first trajectory ends in-the-money, so that  

$$
C(T)^{1}=0.011,\quad C(T)^{2}=0,\quad C(T)^{3}=0
$$  

Using continuous compounding the call premium becomes  

$$
C(t)=\mathrm{Exp}\bigg(-0.02\frac{5}{365}\bigg)\frac{1}{3}[0.011+0+0]
$$  

$$
C(t)=0.0037
$$  

Obviously, the parameters of this model are selected to illustrate the application of the Monte Carlo procedure, and no real-life application would price securities with such a small number of trajectories. However, one important wrinkle has to be noted. The drift of this SDE was given by $(r-r^{f})S_{t}\Delta$ and not by $r S_{t}\Delta$ , which was the case of stock price dynamics. This modification will be dealt with below. Foreign currencies pay foreign interest rates and the risk-free interest rate differentials should be used. We discuss this in more detail in the following section.  

# 13.2.2 PRICING BINARY FX OPTIONS  

This section applies the Monte Carlo technique to pricing digital or binary options in foreign exchange markets. We consider the following elementary instrument:  

If the price of a foreign currency, denoted by $S_{t}$ , exceeds the level $K$ at expiration, the option holder will receive the payoff $R$ denoted in domestic currency. Otherwise the option holder receives nothing. The option is of European style and has expiration date $T.$ . The option will be sold for $C(t)$ .  

We would like to price this binary FX option using Monte Carlo. However, because the underlying is an exchange rate, some additional structure needs to be imposed on the environment and we discuss this first. This is a good example of the use of the fundamental theorem. It also provides a good occasion to introduce some elementary aspects of option pricing in FX markets.  

# 13.2.2.1 Obtaining the risk-neutral dynamics  

In the case of vanilla options written on stock prices, we assumed that the underlying stock pays no dividends and that the stock price follows a geometric continuous time process such as  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}
$$  

with $\mu$ being an unknown drift coefficient representing the market’s expected percentage appreciation of the stock and $\sigma$ being a constant percentage volatility parameter whose value has to be obtained. $W_{t},$ finally, represents a Wiener process.  

Invoking the fundamental theorem of asset pricing, we then replaced the unknown drift term $\mu$ by the risk-free interest rate $r$ assumed to be constant. In the case of options written on foreign exchange rates, some of these assumptions need to be modified. We can preserve the overall geometric structure of the $S_{t}$ process, but we have to change the assumption concerning dividends. A foreign currency is, by definition, some interbank deposit and will earn foreign (overnight) interest. According to the fundamental theorem, we can replace the real-world drift $\mu$ by the interest rate differential, $r_{t}-r_{t}^{f}$ , where $r_{t}^{f}$ is the foreign instantaneous spot rate and $\boldsymbol{r}_{t}$ is, as usual, the domestic rate. Thus, if spot rates are constant,  

$$
r_{t}=r,r_{t}^{f}=r^{f}\quad\forall t
$$  

This gives the arbitrage-free dynamics:6  

$$
\mathrm{d}S_{t}=(r-r^{f})S_{t}\mathrm{d}t+\sigma S_{t}W_{t}\quad t\in[0,\infty)
$$  

The rationale behind using the interest rate differential, instead of the spot rate $r$ , as the riskneutral drift is a direct consequence of the fundamental theorem when the asset considered is a foreign currency. Since this chapter is devoted to applications of the fundamental theorem, we prefer to discuss this briefly.  

Using the notation presented in Chapter 12, we take $S_{t}$ as being the number of dollars paid for one unit of foreign currency. The fundamental theorem of asset pricing introduced in Chapter 12 implies that we can use the state prices $\{Q^{i}\}$ for states $i=1,...,n$ , and write  

$$
S_{t}=\sum_{i=1}^{n}(1+r^{f}\Delta)S_{T}^{i}Q^{i}
$$  

According to this, one unit of foreign currency will be worth $S_{T}^{i}$ dollars in state $i$ of time $T.$ , and it will also earn $\boldsymbol{r}^{f}$ per annum in interest during the period $\Delta=T-t.$ . Normalizing with the domestic savings account, this becomes  

$$
S_{t}=\sum_{i=1}^{n}\frac{(1+r^{f}\Delta)}{(1+r\Delta)}S_{T}^{i}(1+r\Delta)Q^{i}
$$  

We now choose the risk-neutral probabilities as  

$$
\tilde{p}_{i}=(1+r\Delta)Q^{i}
$$  

and rearrange Eq. (13.30) to obtain the expected gross return of $S_{t}$ during $\Delta$  

$$
\frac{(1+r\Delta)}{(1+r^{f}\Delta)}=E_{t}^{\tilde{P}}\left[\frac{S_{T}}{S_{t}}\right]
$$  

Here, the left-hand side can be approximated as7  

$$
(1+r\Delta-r^{f}\Delta)
$$  

which means that $S_{t}$ is expected to change at an annual rate of $(r-r^{f})$ under the risk-neutral probability $\tilde{P}$ . This justifies the continuous time risk-neutral drift of the dynamics:  

$$
\mathrm{d}S_{t}=(r-r^{f})S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}
$$  

Now that the dynamics are specified, the next step is selecting the Monte Carlo trajectories.  

# 13.2.2.2 Monte Carlo process  

Suppose we would like to price our digital option in such a framework. How could we do this using the Monte Carlo approach? Given that the arbitrage-free dynamics for $S_{t}$ are obtained, we can simply apply the steps outlined earlier.  

In particular, we need to generate random paths starting from the known current value for $S_{t}$ . This can be done in two ways. We can first solve the SDE in Eq. (13.34) and then select random replicas from the resulting closed-form formula, if any. The second way is to discretize the dynamics in Eq. (13.34), and proceed as discussed in the previous section. Suppose we decided to proceed by first choosing a discrete interval $\Delta$ , and then discretizing the dynamics:8  

$$
{S_{t+\Delta}}={S_{t}}+({r-{r^{f}}}){S_{t}}\Delta+\sigma{S_{t}}\Delta{W_{t}}
$$  

The next step would be to use a random number generator to obtain $N$ sequences of standard normal random variables $\{\in_{i}^{j},i=1,...,k,j=1,...,\bar{N}\}$ and then calculate the $N$ simulated trajectories using the discretized SDE:  

$$
S_{t_{i}}^{j}=S_{t_{i-1}}^{j}+(r-r^{f})S_{t_{i-1}}^{j}\Delta+\sigma S_{t_{i-1}}^{j}\sqrt{\Delta}\in_{i}^{j}
$$  

where the superscript $j$ denotes the jth simulated trajectory and where $\Delta=t_{i}-t_{i-1}$  

Once the paths $\left\{S_{t_{i}}^{j}\right\}$ are obtained, the arbitrage-free value of the digital call option premium $C$ $\mathbf{\rho}(t)$ that pays $R$ at expiration can be found by using the equality  

$$
C(t)=\mathrm{Re}^{-r(T-t)}E_{t}^{\tilde{P}}\left[I_{\{S_{T}>K\}}\right]
$$  

where the symbol $I_{\{S_{T}>K\}}$ is the indicator function that determines whether at time $T.$ , the $S_{T}$ exceeds $K$ or not:  

$$
I_{\{S_{T}>K\}}=\left\{\begin{array}{c l}{{1}}&{{\mathrm{IF}S_{T}>K}}\\ {{0}}&{{\mathrm{Otherwise}}}\end{array}\right.
$$  

This means that $I_{\{S_{T}>K\}}$ equals 1 if the option expires in-the-money; otherwise it is 0. According to the expected payoff in Eq. (13.37), the arbitrage-free $C(t)$ depends on the value of $E_{t}^{\tilde{P}}\big[I_{\{S_{T}>K\}}\big]$ . The latter can be written as  

$$
E_{t}^{\tilde{P}}\big[I_{\{S_{T}>K\}}\big]=\mathrm{Prob}(S_{T}>K)
$$  

Thus  

$$
C(t)=\mathrm{Re}^{-r(T-t)}\operatorname{Prob}(S_{T}>K)
$$  

This equation is easy to interpret. The value of the digital option is equal to the risk-neutral probability that $S_{T}$ will exceed $K$ times the present value of the constant payoff $R$ .9  

Under these conditions, the role played by the Monte Carlo method is simple. We generate $N$ paths for the exchange rate starting from the current observation $S_{t},$ and then calculate the proportion of paths that would end up above the level $K.$ . Once this tally is made, denoting this number by $m$ , the arbitrage-free value of the option will be  

$$
\begin{array}{c}{{\displaystyle C(t)=e^{-r(T-t)}R~\mathrm{(Prob(}S_{T}>K))}}\\ {{\displaystyle\cong e^{-r(T-t)}R\Big(\frac{\mathfrak m}{\mathrm{N}}\Big)}}\end{array}
$$  

Thus, in this case the Monte Carlo method is used to calculate a special expected value, which is the risk-neutral probability of the event $\{S_{T}>K\}$ . The following section discusses two examples.  

# 13.2.3 PATH DEPENDENCY  

In the examples discussed thus far, we used the Monte Carlo method to generate trajectories for an underlying risk $S_{t}$ , yet considered only the time $T$ values of these trajectories in calculating the desired quantity $C(S_{t},\ t)$ . The other elements of the trajectory were not directly used in pricing.  

This changes if the asset under consideration makes interim payouts or is subject to some other restrictions as in the case of barrier options. When $C\left(S_{t},t\right)$ denotes the price of a barrier call option with barrier $H$ , the option may knock in or out depending on the event $S_{u}<H$ during the period $u\in[t,~T]$ . Consider the case of a down-and-out call. In pricing this instrument, once a Monte Carlo trajectory is obtained, the whole trajectory needs to be used to determine if the condition $S_{u}<H$ is satisfied by $S_{u}^{j}$ during the entire trajectory. This is one example of the class of assets that are path dependent and hence require direct use of entire Monte Carlo trajectories.  

We now provide two more examples of the application of the Monte Carlo procedure. In the first case, the procedure is applied to a vanilla digital option, and in the second example, we show what happens when the option is a down-and-out call.  

# EXAMPLE  

Consider pricing a digital option written on $S_{t}$ , the EUR/USD exchange rate with the same structure as in the first example. The digital euro call has strike $K=1.091$ and pays $\$100$ if it expires in-the-money. The parameters are the same as before:  

$$
r=2\mathcal{U},\quad r^{f}=3\mathcal{V},\quad t_{0}=0,\quad t=5\mathrm{days},\quad S_{t_{0}}=1.09,\quad\sigma=0.10
$$  

The paths for $S_{t}$ are given by  

<html><body><table><tr><td>Path</td><td>Day 1</td><td>Day 2</td><td>Day 3</td><td> Day 4</td><td>Day 5</td></tr><tr><td>1</td><td>1.0937</td><td>1.0965</td><td>1.0981</td><td>1.1085</td><td>1.1060</td></tr><tr><td>2</td><td>1.0893</td><td>1.0875</td><td>1.0780</td><td>1.0850</td><td>1.092</td></tr><tr><td>3</td><td>1.0927</td><td>1.08946</td><td>1.0917</td><td>1.086</td><td>1.0710</td></tr></table></body></html>  

The digital call expires in-the-money if $1.091<S_{T}^{j}$ . There are two incidences of this event in the previous case, and the estimated risk-neutral probability that the option expires in-themoney is 2/3. The option value is calculated as  

$$
C(t)=\mathrm{Exp}\left(-0.02{\frac{5}{365}}\right){\frac{2}{3}}[100]
$$  

$$
C(t)=\mathbb{\S}66.6
$$  

Now, consider what happens if we add a knock-out barrier $H=1.08$ . The digital call knocks out if $S_{t}$ falls below this barrier before expiration.  

# EXAMPLE  

All parameters are the same as in the first example, and the paths are given by  

<html><body><table><tr><td>Path</td><td>Day 1</td><td>Day 2</td><td>Day 3</td><td> Day 4</td><td> Day 5</td></tr><tr><td>1</td><td>1.0937</td><td>1.0965</td><td>1.0981</td><td>1.1085</td><td>1.1060</td></tr><tr><td>2</td><td>1.0893</td><td>1.0875</td><td>1.0780</td><td>1.0850</td><td>1.092</td></tr><tr><td>3</td><td>1.0927</td><td>1.08946</td><td>1.0917</td><td>1.086</td><td>1.0710</td></tr></table></body></html>  

The digital knock-out call requires that $1.091<S_{T}^{j}$ and that the trajectory never falls below 1.08. Thus, there is only one incidence of this in this case and the value of the option is calculated as  

$$
C(t)=\exp\left(-0.02{\frac{5}{365}}\right){\frac{1}{3}}[100]
$$  

$$
C(t)=\$33.3
$$  

Hence, the digital option is cheaper. Also, note that in the case of vanilla call, only the terminal values were used to calculate the option value, whereas in the case of the knock-out call, the entire trajectory was needed to check the condition $H<S_{t}$ .  

# 13.2.4 DISCRETIZATION BIAS AND CLOSED FORMS  

The examples on the Monte Carlo used discrete approximations of SDEs. Assuming that the arbitrage-free dynamics of an asset price $S_{t}$ can be described by a geometric SDE,  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{d}t+\sigma S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

we selected an appropriate time interval $\Delta$ , and ignoring continuous compounding, discretized the SDE  

$$
S_{t+\Delta}=(1+r\Delta)S_{t}+\sigma S_{t}(\Delta W_{t})
$$  

Equation (13.49) is only an approximation of the true continuous time dynamics given by Eq. (13.48).  

For some special SDEs, we can sample the exact $S_{t}$ . In such special cases, the stochastic differential equation for $S_{t}$ can be “solved” for a closed form. The geometric process shown in Eq. (13.48) is one such case. We can directly obtain the value of $S_{T}$ using the closed-form formula:  

$$
S_{T}=S_{t_{0}}e^{r(T-t_{0})-(1/2)\sigma^{2}(T-t_{0})+\sigma\left(W_{T}-W_{t_{0}}\right)}
$$  

The term $\left(W_{T}-W_{t_{0}}\right)$ will be normally distributed with mean zero and variance $T-t_{0}$ . Hence, by drawing replicas of this random variable, we can obtain exact replicas for $S_{T}$ at any $T_{:}$ , $t_{0}<T$ It turns out that even in the case of a mean-reverting model, such closed-form formulas are available and lend themselves to Monte Carlo pricing. However, in general, we may have to use discretized SDEs that may contain a discretization bias.10  

# 13.2.5 REAL-LIFE COMPLICATIONS  

Obviously, Monte Carlo becomes a complex approach once we go beyond simple examples. Difficulties arise, yet significant improvements can be made in regard to (i) how to select random numbers with computers, (ii) how to trick the system, such that the greatest accuracy can be obtained in the shortest time, and (iii) how to reduce the variance of the calculated prices with a given number of random selections. For these questions, other sources should be considered; we will not discuss them given our focus on financial engineering.11  

# 13.3 APPLICATION 2: CALIBRATION  

Calibrating a model means selecting the model parameters such that the observed arbitrage-free benchmark prices are duplicated by the use of this model. In this section we give two examples for this procedure. Since we already discussed several examples of how the fundamental theorem can be applied to SDEs, in this section we concentrate instead on tree models. As the last section has shown, calibration can be done using Monte Carlo and the SDEs as well.  

# 13.3.1 CALIBRATING A TREE  

The BDT model is a good example for procedures that extract information from market prices. The model calibrates future trajectories of the spot rate $\boldsymbol{r}_{t}$ . The BDT model illustrates the way arbitragefree dynamics can be extracted from liquid and arbitrage-free asset prices.12  

The basic idea of the BDT model is that of any other calibration methodology. Let it be implicit binomial trees, estimation of state prices implicit in asset prices, or estimation of risk-neutral probabilities. The model assumes that we are given a number of benchmark arbitrage-free zero-coupon bond prices and a number of relevant volatility quotes in these markets. These volatility quotes can come from liquid caps and floors or from swaptions that are discussed in Chapters 16 and 17, respectively. The procedure evolves in three steps. First, arbitrage-free benchmark securities’ prices and the relevant volatilities are obtained. Second, from these data the arbitrage-free dynamics of the relevant variable are extracted. Finally, other interest-sensitive securities are priced using these arbitrage-free dynamics.  

This section illustrates the procedure using a three-period binomial tree. To simplify the notation and concentrate on understanding the main ideas, this section assumes that the time intervals $\Delta$ in the tree equal 1 year, and that the day-count parameter $\delta$ in a LIBOR setting equals 1 as well. The reader can easily generalize this simple example.  

# 13.3.2 EXTRACTING A LIBOR TREE  

Suppose we have arbitrage-free prices of three default-free benchmark zero-coupon bonds $\{B(t_{0},t_{1})$ , $B(t_{0},\ t_{2}),\ B(t_{0},\ t_{3})\}$ . Also suppose we observe reliable volatility quotes $\sigma_{i}\ i=0$ , 1, 2 for the LIBOR rates $L_{t_{0}},L_{t_{1}},L_{t_{2}}$ .  

First note that $\sigma_{0}$ is by definition equal to 0, because time $t_{0}$ variables have already been observed at time $t_{0}$ . Next, assume that we have the following data:  

$$
\begin{array}{c}{{\sigma_{1}=15\%}}\\ {{\sigma_{2}=20\%}}\\ {{B(t_{0},t_{1})=0.95}}\\ {{B(t_{0},t_{2})=0.87}}\\ {{B(t_{0},t_{3})=0.79}}\end{array}
$$  

From these data, we extract information concerning the future arbitrage-free behavior of the LIBOR rates $L_{t_{i}}$ . We first need some pricing functions that tie the arbitrage-free bond prices to the dynamics of the LIBOR rates. These pricing functions are readily available from the fundamental theorem.  

# 13.3.2.1 Pricing functions  

Consider the fundamental theorem written for times $t_{0}$ and $t_{3}$ . Suppose there are $k$ states of the world at time $t_{3}$ and consider the matrix equation discussed in Chapter 11:  

$$
S_{k x1}=D_{k x k}Q_{k x1}
$$  

Here, $s$ is a $(k x1)$ vector of arbitrage-free asset prices at time $t_{0},D$ is the payoff matrix at time $t_{3}$ , and $\boldsymbol{Q}$ is the $(k x1)$ vector of positive state prices at time $t_{3}$ .  

Suppose the first asset is a 1-year LIBOR-based deposit and the second asset is the bond $B(t_{0},$ $t_{3})$ , which matures and pays 1 dollar at $t_{3}$ . Then, the first two rows of the matrix equation in Eq. (13.56) will be as follows:  

$$
\begin{array}{r l}{\binom{1}{B(t_{0},t_{3})}=}&{\left(\begin{array}{l l l l}{\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{1}}&{\cdots}&{\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{k}}\end{array}\right)}\\ &{\times\left(\begin{array}{l}{Q^{1}}\\ {\cdots}\\ {\cdots}\\ {Q^{k}}\end{array}\right)}\end{array}
$$  

where $\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}$ represents the return to the savings account investment in the ith state of time $t_{3}$ . We can write the second row as  

$$
B(t_{0},t_{3})=\sum_{i=1}^{k}Q^{i}
$$  

Normalizing by the savings account, this becomes  

$$
B(t_{0},t_{3})=\sum_{i=1}^{k}\frac{\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}}{\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}}Q^{i}
$$  

Relabeling the risk-neutral probabilities  

$$
\tilde{p}_{i}=\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}Q^{i}
$$  

gives  

$$
B(t_{0},t_{3})=\sum_{i=1}^{k}\frac{1}{\left[\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)\right]^{i}}\tilde{p}_{i}
$$  

Thus, we obtain the pricing equation for the $t_{3}$ maturity bond as:  

$$
B(t_{0},t_{3})=E_{t_{0}}^{\tilde{P}}\left[\frac{1}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)}\right]
$$  

Proceeding in a similar way, we can obtain the pricing equations for the two remaining bonds:  

$$
\begin{array}{c}{{\displaystyle B(t_{0},t_{1})=E_{t_{0}}^{\tilde{P}}\Bigg[\frac1{\big(1+L_{t_{0}}\big)}\Bigg]}}\\ {{\displaystyle B(t_{0},t_{2})=E_{t_{0}}^{\tilde{P}}\Bigg[\frac1{\big(1+L_{t_{0}}\big)\big(1+L_{t_{1}}\big)}\Bigg]}}\end{array}
$$  

The first equation is trivially true, since $L_{t_{0}}$ is known at time $t_{0}$ .  

# 13.3.3 OBTAINING THE BDT TREE  

In this particular example, we have three benchmark prices and two volatilities. This gives five equations:  

$$
B(t_{0},t_{1})=E_{t_{0}}^{\tilde{P}}\left[\frac{1}{\left(1+L_{t_{0}}\right)}\right]
$$  

$$
B(t_{0},t_{2})=E_{t_{0}}^{\tilde{P}}\left[\frac{1}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)}\right]
$$  

$$
B(t_{0},t_{3})=E_{t_{0}}^{\tilde{P}}\left[\frac{1}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)}\right]
$$  

$$
\mathrm{Vol}\left(L_{t_{1}}\right)=\sigma_{1}
$$  

$$
\mathrm{Vol}\left(L_{t_{2}}\right)=\sigma_{2}
$$  

Once we specify a model for the dynamics of $L_{t_{i}}$ , we can solve these equations to obtain the arbitrage-free paths for $L_{t_{i}}$ .  

# 13.3.3.1 Specifying the dynamics  

We now obtain this arbitrage-free dynamics. Following the tradition in tree models, we simplify the notation and use the index $i=0,1,2,3$ to denote “time,” and the letters $u$ and $d$ to represent the up and down states at each node. First note that we have five equations and, hence, we can at most, get five pieces of independent information from these equations. In other words, the specified dynamic must have at most five unknowns in it. Consider the following three-period binomial tree:  

$$
L_{0}\bigsqcup_{L_{1}^{d}\bigsqcup_{1}^{d}L_{2}^{d u}}^{L_{1}^{u}\bigsqcup^{d}L_{2}^{u}}
$$  

The dynamic has seven unknowns, namely $\{L_{0},L_{1}^{u},L_{1}^{d},L_{2}^{u d},L_{2}^{d u},L_{2}^{d d},L_{2}^{u u}\}$ . That is two more than the number of equations we have. At least two unknowns must be eliminated by imposing additional restrictions on the model. These will come from the specification of variances, as we will now see.  

# 13.3.3.2 The variance of Li  

The spot LIBOR rate $L_{i},i=0,1,2$ has a binomial specification. This means that at any node, the spot rate can take one of only two possible values. Thus, the percentage variance of $L_{i}.$ , conditional on state $j$ at “time” $i$ , is given by13  

$$
V a r(L_{i}|j)=E\tilde{P}[\ln(L_{i})-\ln(\overline{{L}}_{i})^{2}|j]
$$  

where  

$$
\ln\ \overline{{L}}_{i}=E\tilde{P}[\ln(L_{i})|j]
$$  

is the conditional expected value of $L_{i}.$ .  

We now make two additional assumptions. The first assumption is for notational purposes only. We let $j=u$ , and hence assume that we are in an “up” state. The outcome for $j=d$ will be similar.  

Second, we let  

$$
\begin{array}{r c l}{\displaystyle p_{i}^{u}=\frac{1}{2}}&{\forall i}&{}\\ {\displaystyle p_{i}^{d}=\frac{1}{2}}&{\forall i}&{}\end{array}
$$  

That is to say, we assume that the up-and-down risk-neutral probabilities are constant over the life of the tree and that they are equal. We will see that this assumption, which at first may look fairly strong, is actually not a restriction. Using these assumptions and the binomial nature of the LIBOR rate, we can immediately calculate the following:14  

$$
\begin{array}{c}{{E\tilde{P}[\ln(L_{i})\mid j=u]=p^{u}\mathrm{ln}(L_{i}^{u u})+(1-p^{u})\mathrm{ln}(L_{i}^{u d})}}\\ {{{}}}\\ {{{}={\displaystyle{\frac{1}{2}}\left[\mathrm{ln}(L_{i}^{u u})+\mathrm{ln}(L_{i}^{u d})\right]}}}\end{array}
$$  

Replacing this in Eq. (13.71) gives  

$$
V a r(L_{i}\mid j=u)=E\tilde{P}\left[\left(\ln(L_{i})-\frac{1}{2}\left[\ln(L_{i}^{u u})+\ln(L_{i}^{u d})\right]\right)^{2}|j=u\right]
$$  

Simplifying and regrouping, we obtain  

$$
V a r(L_{i}\mid j=u)=\left(\frac{1}{2}\left[-\ln(L_{i}^{u u})+\ln(L_{i}^{u d})\right]\right)^{2}
$$  

This means that the volatility at time $i$ , in state $u$ , is given by  

$$
\sigma_{i}^{u}=\frac{1}{2}\ln\left[\frac{L_{i}^{u u}}{L_{i}^{u d}}\right]
$$  

The result for the down state will be similar:  

$$
\sigma_{i}^{d}=\frac{1}{2}\ln\bigg[\frac{L_{i}^{d u}}{L_{i}^{d d}}\bigg]
$$  

These volatility estimates are functions of the possible values that the LIBOR rate can take during the subsequent period. Hence, given the market quotes on LIBOR volatilities, these formulas can be solved backward to obtain $L_{i}^{u u},L_{i}^{u d}$ . We will do this next.  

# 13.3.4 CALIBRATING THE TREE  

The elements of the tree can now be calibrated to the observed prices. Using the assumptions concerning (i) the binomial nature for the process $L_{i}.$ , (ii) that $p^{u}={p^{d}}=1/2$ , and (iii) that the tree is recombining, we get the following five equations:  

$$
B(t_{0},t_{1})=\frac{1}{(1+L_{0})}
$$  

$$
B(t_{0},t_{2})=\frac{1}{2}\frac{1}{(1+L_{0})(1+L_{1}^{u})}+\frac{1}{2}\frac{1}{(1+L_{0})(1+L_{1}^{d})}
$$  

$$
\begin{array}{r l}{B(t_{0},t_{3})=}&{\displaystyle\frac{1}{4}\left[\frac{1}{(1+L_{0})(1+L_{1}^{u})(1+L_{2}^{u u})}\right]+\frac{1}{4}\left[\frac{1}{(1+L_{0})(1+L_{1}^{u})(1+L_{2}^{u d})}\right]}\\ &{\displaystyle+\frac{1}{4}\left[\frac{1}{(1+L_{0})(1+L_{1}^{d})(1+L_{2}^{d u})}\right]+\frac{1}{4}\left[\frac{1}{(1+L_{0})(1+L_{1}^{d})(1+L_{2}^{d d})}\right]}\end{array}
$$  

$$
\begin{array}{c}{{\frac{1}{2}\mathrm{ln}\left[\frac{L_{1}^{u}}{L_{1}^{d}}\right]=0.15}}\\ {{{}}}\\ {{\frac{1}{2}\mathrm{ln}\left[\frac{L_{2}^{u u}}{L_{2}^{u d}}\right]=0.20}}\end{array}
$$  

Of these equations, the first and second are straightforward. We just applied the risk-neutral measures to price the benchmark bonds. When weighted by these probabilities, the values of future payoffs discounted by the LIBOR rates become Martingales and hence, equal the current price of the appropriate bond, see Figure 13.1.  

![](554737f4522529b0b9f319ab272024378ede67d89fdc1d25861ee485383bc818.jpg)  

# FIGURE 13.1  

LIBOR rates and present value of future payoffs.  

The third equation represents the pricing function for the bond that matures at time $t=3$ . It is interesting to see what it does. According to the tree used here, there are four possible paths the LIBOR rate can take during $t=0$ , 1, 2. These are  

$$
\begin{array}{r l}&{\{L_{0},L_{1}^{u},L_{2}^{u u}\}}\\ &{\{L_{0},L_{1}^{u},L_{2}^{u d}\}}\\ &{\{L_{0},L_{1}^{d},L_{2}^{d u}\}}\\ &{\{L_{0},L_{1}^{d},L_{2}^{d d}\}}\end{array}
$$  

Due to the way probabilities, $p^{u}$ and $p^{d}$ , are picked in this model, each path is equally likely to occur. This gives the third equation.  

The last two equations are simply the volatilities at each node. We see that as the volatilities depend only on the time index $i$ ,  

$$
\begin{array}{c}{{\displaystyle{\frac{1}{2}}\mathrm{ln}\bigg[\frac{L_{2}^{u u}}{L_{2}^{u d}}\bigg]=0.20}}\\ {{\displaystyle{\frac{1}{2}}\mathrm{ln}\bigg[\frac{L_{2}^{d u}}{L_{2}^{d d}}\bigg]=0.20}}\end{array}
$$  

which means that  

$$
L_{2}^{u u}L_{2}^{d d}=L_{2}^{u d}L_{2}^{d u}
$$  

This adds another equation to the five listed earlier and makes the number of unknowns equal to the number of equations. Under the further assumption that the tree is recombining, we have  

$$
L_{2}^{u u}L_{2}^{d d}=(L_{2}^{u d})^{2}
$$  

Now Eqs. $(13.81)-(13.85)$ and (13.92) (13.93) can be solved for the seven unknowns $\{L_{0},L_{1}^{u},L_{1}^{d},L_{2}^{u u},L_{2}^{d u},L_{2}^{u d},L_{2}^{d d}\}$ .  

The simplest way to solve these equations is to start from $i=0$ and work forward, since the system is recursive. It is trivial to obtain $L_{0}$ from the first equation. The second and fourth equations give $L_{1}^{u},L_{1}^{d}$ , and the remaining three equations give the last three unknowns. There is one caveat. The system of equations $(13.81){-}(13.85)$ is not linear. Hence, a nonlinear hill-climbing solution procedure must be used to determine the unknowns.  

# EXAMPLE  

The situation is shown in the figure below. There are three periods. Hence, we have three discounts given by the corresponding zero-coupon bond prices and three volatilities. The first volatility is zero, since we do know the value of $L_{0}$ .  

The system in Eqs. (13.81) (13.85) can be solved recursively. First, we solve for $L_{0}$ , then for $L_{1}^{u}$ and $L_{1}^{d}$ , and last for the time $t=2$ LIBOR rates. The nonlinear equations solved using Mathematica yield the following results:  

$$
\begin{array}{r l}&{L_{0}=5.26\%\gtrsim\lfloor\frac{L_{1}^{u}}{1}=6.39\%\lesssim\lfloor\frac{u\i}{12}=L_{2}^{d u}=9.7\%}\\ &{\qquad\quad\vdash L_{1}^{d}=4.73\%\lesssim\lfloor\frac{u\ i}{12}=5.3\%=5.3\%}\end{array}
$$  

We now discuss how BDT trees that give arbitrage-free paths for LIBOR rates or other spot rates can be used.  

# 13.3.5 USES OF THE TREE  

Arbitrage-free trees have many uses. (i) We can price baskets of options written on the LIBOR rates $L_{i}$ . These are called caps and floors and are very liquid. (ii) We can use the tree to price swaps and related derivatives. (iii) Finally, we can use the tree to price forward caps, floors, and swaps. We discuss one example below.  

# 13.3.5.1 Application: pricing a cap  

A caplet is an option written on a particular LIBOR rate $L_{t_{i}}$ . A cap rate, $L_{K},$ is selected as a strike price, and the buyer of the caplet is compensated if the LIBOR rate moves above $L_{K}$ , see Figures 13.2 and 13.3. The expiration date is $t_{i},$ , and the settlement date is $t_{i+1}$ . A caplet then “caps” the interest cost of the buyer. A sequence of consecutive caplets written on $L_{t_{i}},L_{t_{i+1}},...,L_{t_{i+\tau}}$ forms a $\intercal$ period cap. Similarly, a sequence of consecutive floorlets forms a floor. An interest rate floor is a derivative contract in which the buyer receives payments at the end of each period in which the interest rate is below the agreed strike price.  

Suppose we have the following caplet to price:  

• The $t_{i}$ are such that $t_{i}-t_{i-1}=12$ months. At time $t_{2}$ , the LIBOR rate $L_{t_{2}}$ will be observed. A notional amount $N$ is selected at time $t_{0}$ . Let it be given by  

$$
N=\mathbb{S}1\mathrm{million}
$$  

![](5f9c8c133d608cae2a74a9ddef7b961fd7544d2613548f3b9df0b96d441e71a5.jpg)  

# FIGURE 13.2  

Caplet payoff.  

![](1db08b4257684998b5fdec3732f39746c567729a1f3ec14d76ee0141be0e7d5e.jpg)  

# FIGURE 13.3  

Floorlet payoff.  

• If the LIBOR rate $L_{t_{2}}$ is in excess of the cap rate $L_{K}=6.5\%$ , the client will receive payoff:  

$$
C(t_{3})=\frac{N\big(L_{t_{2}}-L_{K}\big)}{100}
$$  

at time $t_{3}$ . Otherwise the client is paid nothing.  

For this “insurance,” the client pays a premium equal to $C(t_{0})$ .  

The question is how to determine an arbitrage-free value of the caplet premium $C(t_{0})$ . The fundamental theorem says that the expected value of the expiration date payoff, discounted by the risk-free rate, will equal $C(t_{0})$ if we evaluate the expectation using the risk-neutral probability. That is to say, remembering that we have $\delta=1$ ,  

$$
C(t_{0})=E_{t_{0}}^{\tilde{P}}\left[\frac{C(t_{3})}{\left(1+L_{t_{0}}\right)\left(1+L_{t_{1}}\right)\left(1+L_{t_{2}}\right)}\right]
$$  

with expiration payoff  

$$
C(t_{3})=N\operatorname*{max}\left[\frac{\left(L_{t_{2}}-L_{K}\right)}{100},0\right]
$$  

The pricing of the caplet is done with the BDT tree determined previously. In the example, the tree had four possible trajectories, each occuring with probability 1/4. Using these we can calculate the caplet price.  

According to the BDT tree, the caplet ends in-the-money in three of the four trajectories. Calculating the possible payoffs in each case and then dividing by the discount factors, we get the numerical equivalent of the expectation in Eq. (13.98).  

$$
C_{0}=0.25\left[\begin{array}{l}{{{\frac{53000}{(1.0526)(1.0639)(1.118)}}+{\frac{144400}{(1.0526)(1.0473)(1.0793)}}}}\\ {{}}\\ {{+{\frac{14400}{(1.0526)(1.0639)(1.0793)}}}}\end{array}\right]
$$  

$$
=\$16,587
$$  

We should emphasize that under these circumstances the discount factors are random variables. They cannot be taken out of the expectation operator. Also, the center node, which is recombining and, hence, leads to the same value for $L_{2}^{u d}$ and $L_{2}^{d u}$ , still requires different discount factors since the average interest rate is different across the two middle trajectories.  

# 13.3.5.2 Some assumptions of the model  

It may be worthwhile to summarize some of the assumptions that were used in the previous discussion.  

The BDT approach is an example of a one-factor model, since the short rate, here represented by the LIBOR rate $L_{i},$ is assumed to be the only variable determining bond prices. This means that bond prices are perfectly correlated.   
The distribution of interest rates is lognormal in the limit.   
We made several simplifying assumptions concerning the framework. There were neither taxes, nor any trading costs.  

Needless to say, the procedure also rests on the premise that the original data are arbitrage-free.  

# 13.3.5.3 Remarks  

The BDT approach may be considered simplistic. Yet, until the advent of the Forward LIBOR Model that we will introduce in the next chapter, market professionals preferred to stay with the BDT approach given the more sophisticated alternatives. A simple model may not fit reality exactly, but may have three important advantages.  

1. If the model depends on few parameters, then few parameters have to be determined and the chance of error is less.   
2. If the model is simple, a trader or risk manager will accumulate some personal experience in how to adjust for weaknesses of the model.   
3. Simple models whose weaknesses are well known and well tried may be better than more sophisticated models with no track record.  

We will see that another model with known weaknesses, namely the Black Scholes model, is preferred by traders for similar reasons.  

# 13.3.6 REAL-WORLD COMPLICATIONS  

The BDT model as used in the previous example is, of course, based on symbolic parameters, such as two states, readily available pure discount bond prices, and so on. And as mentioned earlier, it rests on several restrictive assumptions.  

In a real-world application, the following additions to the example discussed above need to be made. (i) Day-count conventions need to be checked and corrected for, (ii) settlement may be done at time $t=2$ , then further discounting may be needed from $t=3$ to $t=2$ , and (iii) in market applications, caps consisting of several caplets instead of a single caplet are priced.  

# 13.4 APPLICATION 3: QUANTOS  

The first two examples of the application of the fundamental theorem shown thus far were essentially numerical. The pricing of quanto contracts constitutes another application of the fundamental theorem. This requires a conceptual discussion. It is a good example of how the techniques introduced in Chapter 12 can be used in modeling. The section is also intended to complete the discussion of the financial engineering aspects of quantoed assets that we started in Chapter 10.  

A quantoed foreign asset makes future payoffs in the domestic currency at a known exchange rate. An exchange rate, $x_{t},$ is chosen at initiation, to settle the contract at time T. For example, using quantos, a dollar-based investor could benefit from the potential upside of a foreign stock market, while eliminating the implicit currency exposure to exchange rate movements.  

# 13.4.1 PRICING QUANTOS  

The following application of the fundamental theorem starts with pricing a quanto forward. Let $S_{t}^{*}$ be a foreign stock denominated in the foreign currency. Let $x_{t}$ be the exchange rate defined as the number of domestic currency, per 1 unit of foreign currency. The fundamental theorem can be used with the domestic risk-neutral measure $\tilde{P}$ to obtain the time $t_{0}$ value of the forward contract:  

$$
V(t_{0})=e^{-r(T-t_{0})}E_{t_{0}}^{\tilde{P}}x_{t_{0}}\big[S_{T}^{*}-F_{t_{0}}\big]
$$  

$F_{t_{0}}$ is the time $T$ forward value of the foreign stock. It is measured in foreign currency. Setting the $V(t_{0})$ equal to zero gives the forward value $F_{t_{0}}$ :  

$$
F_{t_{0}}=E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]
$$  

Thus, in order to calculate $F_{t_{0}}$ we need to evaluate the expectation of the foreign currency denominated $S_{T}^{*}$ under the domestic risk-neutral measure $\tilde{P}$ :  

$$
E_{t_{0}}^{\tilde{P}}[S_{T}^{*}].
$$  

The fact that the state prices, $\boldsymbol{Q}^{i}$ , in the fundamental theorem are denominated in the domestic currency, whereas $S_{t}^{*}$ is denominated in the foreign currency, makes this a nontrivial exercise.  

But, if used judiciously, the fundamental theorem can still be exploited for obtaining the expectation in Eq. (13.101). To maintain continuity, we use the simple framework developed in Chapter 12. In particular, we assume that there are only two periods, $t_{0}$ and $T_{\cdot}$ , with $n$ states of the world at time $T.$ . The notation remains the same.  

Consider the matrix equation of the fundamental theorem for three assets. The first is the domestic savings account $B_{t}$ which starts at 1 dollar and earns the domestic annual rate $r.$ The second is a foreign savings account, $B_{t}^{*}$ which starts with 1 unit of the foreign currency and earns the foreign interest rate $r^{*}$ . These interest rates are assumed to be constant. The foreign currency has dollar value $x_{t0}$ at time $t_{0}$ . Finally, we have the foreign stock, $S_{t_{0}}^{*}$ .  

Putting these into the matrix equation implied by the fundamental theorem we get  

$$
\left(\begin{array}{c}{{1}}\\ {{x_{t_{0}}}}\\ {{x_{t_{0}}S_{t_{0}}^{*}}}\end{array}\right)=\left(\begin{array}{c c c}{{1+r(T-t_{0})}}&{{\ldots}}&{{1+r(T-t_{0})}}\\ {{x_{T}^{1}[1+r^{*}(T-t_{0})]}}&{{\ldots}}&{{x_{T}^{n}[1+r^{*}(T-t_{0})]}}\\ {{x_{T}^{1}S_{T}^{*1}}}&{{\ldots}}&{{x_{T}^{n}S_{T}^{*n}}}\end{array}\right)\left(\begin{array}{c}{{Q^{1}}}\\ {{\ldots}}\\ {{\ldots}}\\ {{\ldots}}\\ {{Q^{k}}}\end{array}\right)
$$  

Here, $x_{T}^{i}$ and $S_{T}^{*i}$ have $i$ superscripts because their time $T$ value depends on the state that is realized at that time. This system involves domestic state prices, and therefore the value of the foreign stock $S_{t_{0}}^{*}$ is converted into domestic currency by multiplying with $x_{t_{0}}.\ Q^{i},i=1,\ ...,n$ are the state prices assumed to be known and positive.  

We start with two results that are obtained by the following methods shown in Chapter 12. Define the domestic risk-neutral measure $\tilde{P}$ as  

$$
\tilde{p}_{i}=(1+r(T-t_{0}))Q^{i}
$$  

Then, from the third row of Eq. (13.102) we obtain the equality,  

$$
x_{t_{0}}S_{t_{0}}^{*}=\frac{1}{1+r(T-t_{0})}{\sum_{i=1}^{n}}x_{T}^{i}S_{T}^{*i}{\tilde{p}}_{i}
$$  

This means that  

$$
x_{t_{0}}S_{t_{0}}^{*}=\frac{1}{1+r(T-t_{0})}E_{t_{0}}^{\tilde{P}}\big[x_{T}S_{T}^{*}\big]
$$  

Using the second row of the system in Eq. (13.102), we obtain a similar equality for the exchange rate. After switching from $\boldsymbol{Q}^{i}$ to the risk-neutral probabilities $\tilde{P}$ ,  

$$
x_{t_{0}}=\frac{1+r^{*}(T-t_{0})}{1+r(T-t_{0})}E_{t_{0}}^{\tilde{P}}[x_{T}]
$$  

We use Eqs. (13.105) and (13.106) in calculating the desired quantity, $E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]$ . We know from elementary statistics that  

$$
\mathrm{Cov}(S_{T}^{*},x_{T})=E_{t_{0}}^{\tilde{P}}[S_{T}^{*}x_{T}]-E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]E_{t_{0}}^{\tilde{P}}[x_{T}]
$$  

Rearranging, we can write:  

$$
E_{t_{0}}^{\tilde{P}}\big[S_{T}^{*}\big]=\frac{E_{t_{0}}^{\tilde{P}}[S_{T}^{*}x_{T}]-\operatorname{Cov}(S_{T}^{*},x_{T})}{E_{t_{0}}^{\tilde{P}}[x_{T}]}
$$  

We substitute in the numerator from Eq. (13.105) and in the denominator from Eq. (13.106) to obtain  

$$
E_{t_{0}}^{\tilde{P}}\big[S_{T}^{*}\big]=\frac{[1+r(T-t_{0})]x_{t_{0}}S_{t_{0}}^{*}-\mathrm{Cov}(S_{T}^{*},x_{T})}{x_{t_{0}}[(1+r(T-t_{0}))/(1+r*(T-t_{0}))]}
$$  

We prefer to write this in a different form using the correlation coefficient denoted by $\rho$ , and the percentage annual volatilities of $x_{t}$ and $S_{t}^{*}$ denoted by $\sigma_{x},\sigma_{s},$ respectively. Let  

$$
\operatorname{Cov}(S_{T}^{*},x_{T})=\rho\sigma_{x}\sigma_{s}(x_{t_{0}}S_{t_{0}}^{*})(T-t_{0})
$$  

The expression in Eq. (13.109) becomes  

$$
E_{t_{0}}^{\tilde{P}}\big[S_{T}^{*}\big]=\frac{1+r^{*}(T-t_{0})}{1+r(T-t_{0})}[1+(r-\rho\sigma_{x}\sigma_{s})(T-t_{0})]S_{t_{0}}^{*}
$$  

We can approximate this as15  

$$
E_{t_{0}}^{\tilde{P}}[S_{T}^{*}]\cong[1+(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t_{0})]S_{t_{0}}^{*}
$$  

This gives the foreign currency denominated price of the quanto forward in the domestic currency:  

$$
F_{t_{0}}\cong[1+(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t_{0})]S_{t_{0}}^{*}
$$  

The present value of this in domestic currency will be the spot value of the quanto:  

$$
V_{t_{0}}=x_{t_{0}}\frac{1}{1+r(T-t_{0})}[1+(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t_{0})]S_{t_{0}}^{*}
$$  

We can also write this relationship by reinterpreting the interest rates as continuously compounded rates:  

$$
V_{t_{0}}=e^{-r(T-t_{0})}e^{(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t_{0})}x_{t_{0}}S_{t_{0}}^{*}
$$  

According to this expression, the value of the quanto feature depends on the sign of the correlation between exchange rate movements and the value of the foreign stock. If this correlation is positive, then the quanto feature is negatively priced. If the correlation is negative, the quanto feature has positive value.16 If the correlation is zero, the quanto feature has zero value.  

$$
{\frac{1}{1+z}}=1-z
$$  

for small z. In the approximation, we ignore all terms of order $\left(T-t_{0}\right)^{2}$ and higher.   
16Suppose the correlation is positive. Then, when foreign stock’s value goes up, in general, the foreign currency will also go up. The quanto eliminates this opportunity from the point of view of a stockholder, and hence, has a negative value and the quantoed asset is cheaper.  

# 13.4.2 THE PDE APPROACH  

Our next example shows how the fundamental theorem can be used to obtain partial differential equations (PDE) for quanto instruments. The treatment will be in continuous time and is essentially heuristic. Consider the same two-currency environment. The domestic and foreign savings deposits are denoted by $B_{t}$ and $B_{t}^{*}$ , respectively. The corresponding continuously compounded rates are assumed to be constant, for simplicity, at $r$ and $r^{*}$ . This means that the savings account values increase incrementally according to the following (ordinary) differential equations:  

$$
\begin{array}{c}{\mathrm{d}B_{t}=r B_{t}\mathrm{d}t\quad t\in[0,\infty)}\\ {\mathrm{d}B_{t}^{*}=r^{*}B_{t}^{*}\mathrm{d}t\quad t\in[0,\infty)}\end{array}
$$  

Let $x_{t}$ be the exchange rate expressed as the domestic currency price of 1 unit of foreign currency. $x_{t}$ satisfies the SDE:  

$$
\mathrm{d}x_{t}=\upmu_{x}x_{t}\mathrm{d}t+\sigma_{x}x_{t}\mathrm{d}W_{1t}\quad t\in[0,\infty)
$$  

under the appropriate Martingale measure.  

First we obtain the exchange rate dynamics under the $B_{t}$ normalization. Note that $B_{t}^{*}$ is a traded asset and its price in domestic currency is $x_{t}B_{t}^{*}$ . According to the results obtained in Chapter 12, with $B_{t}$ normalization, and the corresponding risk-neutral measure $\tilde{P}$ , the ratio  

$$
\frac{x_{t}B_{t}^{*}}{B_{t}}
$$  

should behave as a Martingale. This means that the drift of the implied dynamics should be zero. Taking total derivatives,17  

$$
E_{t}^{\tilde{P}}\left[\mathrm{d}\frac{x_{t}B_{t}^{*}}{B_{t}}\right]=E_{t}^{\tilde{P}}\left[\frac{B_{t}^{*}}{B_{t}}\mathrm{d}x_{t}+\frac{x_{t}}{B_{t}}\mathrm{d}B_{t}^{*}-\frac{x_{t}B_{t}^{*}}{B_{t}^{2}}\mathrm{d}B_{t}\right]=0
$$  

Replacing from Eqs. (13.116), (13.117), and (13.118), we obtain18  

$$
\frac{B_{t}^{*}}{B_{t}}\upmu_{x}x_{t}\mathrm{d}t+\frac{x_{t}}{B_{t}}r^{*}B_{t}^{*}\mathrm{d}t-\frac{x_{t}B_{t}^{*}}{B_{t}^{2}}r B_{t}\mathrm{d}t=\frac{x_{t}B_{t}^{*}}{B_{t}}\left[\upmu_{x}+r^{*}-r\right]\mathrm{d}t
$$  

In order for this drift to be zero, we must have, under $\tilde{P}$ , at all times:  

$$
\mu_{x}+r^{*}-r=0
$$  

Replacing this drift in Eq. (13.118) gives the exchange rate dynamics under the $\tilde{P}$ :  

$$
\mathrm{d}x_{t}=(r-r^{*})x_{t}\mathrm{d}t+\sigma_{x}x_{t}\mathrm{d}W_{1t}\quad t\in[0,\infty)
$$  

Next, consider the $\tilde{P}$ dynamics of the foreign stock $S_{t}^{*}$ .  

$$
\mathrm{d}S_{t}^{*}=\upmu_{s}S_{t}^{*}\mathrm{d}t+\sigma_{x}S_{t}^{*}\mathrm{d}W_{2t}\quad t\in[0,\infty)
$$  

Under the $B_{t}$ normalization, the domestic currency value of the foreign stock should behave as a Martingale. Applying Ito’s Lemma:  

$$
E_{t}^{\tilde{P}}\left[\mathrm{d}\frac{x_{t}S_{t}^{*}}{B_{t}}\right]=E_{t}^{\tilde{P}}\left[\frac{S_{t}^{*}}{B_{t}}\mathrm{d}x_{t}+\frac{x_{t}}{B_{t}}\mathrm{d}S_{t}^{*}-\frac{x_{t}S_{t}^{*}}{B_{t}^{2}}\mathrm{d}B_{t}+\frac{\mathrm{d}x_{t}\mathrm{d}S_{t}^{*}}{B_{t}}\right]=0
$$  

Replacing the differentials and simplifying, we obtain  

$$
\begin{array}{l}{\displaystyle\frac{S_{t}^{*}}{B_{t}}(r-r^{*})\boldsymbol{x}_{t}+\frac{x_{t}}{B_{t}}\upmu_{s}S_{t}^{*}-\frac{x_{t}S_{t}^{*}}{B_{t}^{2}}r B_{t}+\frac{\rho\sigma_{x}\sigma_{s}x_{t}S_{t}^{*}}{B_{t}}}\\ {=\frac{x_{t}S_{t}^{*}}{B_{t}}\left[(r-r^{*})+\upmu_{s}-r+\rho\sigma_{x}\sigma_{s}\right]=0}\end{array}
$$  

In order for this drift to be zero we must have, under $\tilde{P}$ , at all times:  

$$
\upmu_{S}={r}^{*}-\rho\sigma_{x}\sigma_{s}
$$  

This gives the arbitrage-free stock price dynamics:  

$$
\mathrm{d}S_{t}^{*}=(r^{*}-\rho\sigma_{x}\sigma_{s})S_{t}^{*}\mathrm{d}t+\sigma_{x}S_{t}^{*}\mathrm{d}W_{2t}\quad t\in[0,\infty)
$$  

These dynamics imply that:  

$$
E_{t}^{\tilde{P}}[S_{T}^{*}]=e^{(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t)}S_{t}^{*}
$$  

as derived in the previous section. Here the interest rates $r$ and $r^{*}$ should be interpreted as continuously compounded rates. In the previous section, they were actuarial rates for the period $T-t_{0}$ .  

# 13.4.2.1 A PDE for quantos  

Finally, using these results we can obtain a PDE for an arbitrary quanto asset written on a risk associated with a foreign economy. Let this foreign currency denominated asset be denoted by $S_{t}^{*}$ . Let $V_{t}$ denote the time $t$ value of the quanto,  

$$
V(t)=x_{t}V(S_{t}^{*},\ t)
$$  

$V(.)$ , being a pricing function of the asset, needs to be determined. $x_{t}$ is the initial exchange rate written in the quanto contract and, hence, $V(t)$ is expressed in domestic currency terms. Under $B_{t}$ normalization, $V(t)$ should behave as a Martingale. Applying Ito’s Lemma we obtain:19  

$$
E_{t}^{\tilde{P}}\bigg[\mathrm{d}\frac{V(t)}{B_{t}}\bigg]=E_{t}^{\tilde{P}}\bigg[\frac{V_{t}}{B_{t}}\mathrm{d}t+\frac{V_{s}}{B_{t}}\mathrm{d}S_{t}^{*}-\frac{V}{B_{t}^{2}}\mathrm{d}B_{t}+\frac{1}{2}\frac{V_{s s}\sigma_{s}^{2}(S_{t}^{*})^{2}}{B_{t}}\mathrm{d}t\bigg]=0
$$  

Replacing the stochastic differentials and simplifying yields the implied PDE,  

$$
V_{t}+(r^{*}-\rho\sigma_{x}\sigma_{s})S_{t}^{*}V_{s}+\frac{1}{2}V_{S S}\sigma_{s}^{2}(S_{t}^{*})^{2}-r V=0
$$  

with the terminal condition:  

$$
V(T)=x_{t}V(S_{T}^{*},T)
$$  

We apply this PDE to two special cases.  

# 13.4.3 QUANTO FORWARD  

Suppose we know that a quanto forward has the value,  

$$
V(t)=q(t)S_{t}^{*}
$$  

but that the time-dependent function $q(t)$ is unknown. The PDE derived in the previous section can be used to solve for $q(t)$ . Differentiating Eq. (13.134), we get the partial derivatives:  

$$
V_{t}=\frac{\partial q(t)}{\partial t}S_{t}^{*}=\dot{q}S_{t}^{*}
$$  

$$
V_{s}=q(t)
$$  

$$
V_{s s}=0
$$  

We replace these in the PDE for the quanto,  

$$
\dot{q}S_{t}^{*}+(r^{*}-\rho\sigma_{x}\sigma_{s})q(t)S_{t}^{*}-r q(t)S_{t}^{*}=0
$$  

with the terminal condition,  

$$
V(T)=x_{t}S_{T}^{*}
$$  

Eliminating the common $S_{t}^{*}$ terms, this ordinary differential equation can be solved for $q(t)$ :  

$$
q(t)=x_{t}e^{(r^{*}-\rho\sigma_{x}\sigma_{s})(T-t)}
$$  

This is the same result as obtained earlier.  

# 13.4.4 QUANTO OPTION  

Suppose the payoff $V(T)$ of a quanto asset relates to the payoff of a European call on a foreign stock $S_{t}^{*}$ :  

$$
V_{T}=x_{t}\operatorname*{max}[S_{T}^{*}-K^{*},0]
$$  

Here $K^{*}$ is a foreign currency denominated strike price and $T$ is the expiration date. Then the PDE derived in Eq. (13.132) can be solved using the equivalence with the Black Scholes formula to obtain the pricing equation for a European quanto call:  

$$
C(t)=x_{t}\left[S_{t}^{*}e^{(r^{*}-r-\rho\sigma_{x}\sigma_{s})(T-t)}N(b_{1})-K^{*}e^{-r(T-t)}N(b_{2})\right]
$$  

where  

$$
b_{1}=\frac{(\ln S_{t}^{*}/K^{*})+(r^{*}-\rho\sigma_{x}\sigma_{s}+0.5\sigma_{s}^{2})(T-t)}{\sigma_{s}\sqrt{T-t}}
$$  

$$
b_{2}=b_{1}-\sigma_{s}{\sqrt{T-t}}
$$  

The value of the call will be measured in domestic currency.  

# 13.4.4.1 Black Scholes and dividends  

We now explain how to trick the PDE in Eq. (13.132) in order to arrive at the Black Scholes type formula for the simple quantoed equity option shown above. To do this, we need the equivalent of the Black Scholes formula in the case of a constant rate of dividends paid by the underlying stock during the life of the option.  

Standard derivations in the Black Scholes world will give the European call premium on a stock, $S_{t}.$ that pays dividends at a constant rate $\boldsymbol{Q}$ as,  

$$
C(t)=e^{-Q(T-t)}S_{t}N(\tilde{d}_{1})-K e^{-(r)(T-t)}N(\tilde{d}_{2})
$$  

with  

$$
\tilde{d}_{1}=\frac{(\ln S_{t}/K)+(r-Q+0.5\sigma_{s}^{2})(T-t)}{\sigma_{s}\sqrt{T-t}}
$$  

$$
\tilde{d}_{s}=\tilde{d}_{1}-\sigma_{s}\sqrt{T-t}
$$  

where $S_{t}$ is the dividend paying stock.  

Now, note that we can write the PDE in Eq. (13.138) as  

$$
V_{t}+(r-Q)S_{t}^{*}V_{s}+\frac{1}{2}V_{s s}\sigma_{s}^{2}(S_{t}^{*})^{2}-r V=0
$$  

where $\boldsymbol{Q}$ is treated as a dividend yield, and is given by  

$$
Q=r-r^{*}+\rho\sigma_{x}\sigma_{s}
$$  

We can then use this $\boldsymbol{Q}$ in the standard Black Scholes formula with a known dividend yield to get the quantoed call premium.  

# 13.4.5 HOW TO HEDGE QUANTOS  

Quanto contracts require dynamic hedging. The dealer would form a portfolio made of the underlying foreign asset, the foreign currency (or, better, an FX-forward), and the domestic lending and borrowing. The weights of this portfolio would be adjusted dynamically, so that the portfolio replicates the changes in value of the quanto contract. The trading gains (losses) realized from these hedge adjustments form the basis for the quanto premium or discount.  

# 13.4.6 REAL-LIFE CONSIDERATIONS  

The discussion of quantoed assets in this section has been in a simple, abstract, and unrealistic world. We used the following assumptions, among others: (i) the underlying processes were assumed to be lognormal, so that the implied SDEs were geometric. (ii) The correlation coefficient and the volatility parameters were assumed to be constant during the life of the option. (iii) Similarly, interest rates were assumed to be constant, although the corresponding exchange rate was stochastic.  

These assumptions are not satisfied in most real-world applications. Especially important for quantos, the correlation coefficients between exchange rates and various risk factors are known to be quite unstable. The models discussed in this section therefore need to be regarded as a conceptual application of the fundamental theorem. They do not provide an algorithm for pricing real-world quantos.  

# 13.5 CONCLUSIONS  

This chapter dealt with three applications of the fundamental theorem of asset pricing. In general, a financial engineer needs to use such approaches when static replication of the assets is not possible. Mark-to-market requirements or construction of new products often requires calculating arbitrage-free prices internally without having recourse to synthetics that can be put together using liquid prices observed in the markets. The methods outlined in this chapter show some standard ways of doing this.  

# SUGGESTED READING  

There are several sources the reader may consult to learn more on the methods introduced in this chapter via some simple examples. One of our preferred sources is Clewlow and Strickland (1998), which provides some generic codes for computer applications as well. A recent book that deals with the topic of Monte Carlo in finance is Jackel (2002). The series of articles referenced in Avellaneda et al. (2001) provides an in-depth discussion of calibration issues. Finally, the original Black et al. (1990) model is always an illuminating reading on the BDT model. For quanto assets, and related discussion, consider Hull (2014). Wilmott (2006) is very useful for learning further application of the techniques presented here.  

# EXERCISES  

1. (Black Derman Toy model.) You observe the following default-free discount bond prices $B$ $(t,T_{\mathrm{i}})$ , where time is measured in years:  

$$
B(0,1)=95,B(0,2)=93,B(0,3)=91,B(0,4)=89
$$  

These prices are assumed to be arbitrage-free. In addition, you are given the following cap-floor volatilities:  

$$
\sigma(0,1)=0.20,\sigma(0,2)=0.25,\sigma(0,3)=0.20,\sigma(0,4)=0.18
$$  

where $\sigma(t,T_{i})$ is the (constant) volatility of the LIBOR rate $L_{T_{i}}$ that will be observed at $T_{i}$ with tenor of 1 year.  

a. Using the Black Derman Toy model, calibrate a binomial tree to these data.   
b. Suppose you are given a bond call option with the following characteristics. The underlying, $B(2,4)$ , is a two-period bond, expiration $T=2$ , strike $K_{B}=93$ . You know that the BDT tree is a good approximation to arbitrage-free LIBOR dynamics. What is the forward price of $B$ (2, 4)?   
c. Calculate the arbitrage-free value of this call option using the BDT approach.  

2. (Exchange rates and LIBOR rates.) You know that the euro/dollar exchange rate $\boldsymbol{e}_{t}$ follows the real-world dynamics:  

$$
\mathrm{d}e_{t}=\mu\mathrm{d}t+0.15e_{t}\mathrm{d}W_{t}
$$  

The current value of the exchange rate is $e_{o}=1.1015$ . You also know that the price of a 1-year USD discount bond is given by  

$$
B(t,t+1)^{\mathrm{US}}=98.93\
$$  

while the corresponding euro-denominated bond is priced as  

$$
B(t,t+1)^{\mathrm{EU}}=98.73
$$  

Both of these prices are arbitrage-free and there is no credit risk.  

a. What are the 1-year LIBOR rates in these two currencies at time $t?$ b. What are the continuously compounded interest rates $r_{t}^{\mathrm{US}},r_{t}^{\mathrm{EUR}.}$ ? c. Obtain the arbitrage-free dynamics of the $\boldsymbol{e}_{t}$ . In particular, state clearly whether we need to use continuously compounded rates or LIBOR rates to do this. d. Is there a continuous time dynamic that can be written using the LIBOR rates?  

3. (European option.) Consider again the data given in the previous question.  

a. Use $\Delta=1$ year to discretize the system.   
b. Generate five sets of standard normal random numbers with five random numbers in each set. How do you know that these five trajectories are arbitrage-free?   
c. Calculate the value of the following option using these trajectories. The strike is 0.95, the expiration is 3 years, and the European style applies.  

4. (European FX option.) Suppose you know that the current value of the peso dollar exchange rate is 3.75 pesos per dollar. The yearly volatility of the Mexican peso is $20\%$ .  

The Mexican interest rate is $8\%$ , whereas the US rate is $3\%$ . You will price a dollar option written on the Mexican peso. The option is of European style and has a maturity of 270 days. All processes under consideration are known to be geometric.  

a. Price this option using a standard Monte Carlo model. You will select the number of series, the size of the approximating time intervals, and other parameters of the Monte Carlo exercise.   
b. Now assume that Mexico’s foreign currency reserves follow a geometric SDE with a volatility of $10\%$ and a drift coefficient of $5\%$ a year. The current value of reserves is USD7 billion. If reserves fall below USD6 billion, there will be a one-shot devaluation of $100\%$ . Is this information important for pricing the option? Explain.   
c. Use importance sampling to reprice the option. Your pricing is supposed to incorporate the risk of devaluation.  

# EXCEL EXERCISES  

5. (European Option.)  

Write a VBA program to simulate $M=100$ stock prices using a Monte Carlo technique to calculate the prices of European Call and Put options based on the following data: $S(O)=100\$ ; $K=105$ ; $T=1$ ; $r=8\%$ ; $\sigma=50\%$  

Gradually increase the value of $M$ and report the observed resulting price of the options.  

6. (Digital Currency Options.) Write a VBA program to simulate $M=100$ stock prices using a Monte Carlo technique to calculate the prices of digital call and put options FX options as discussed in the text. Use the following parameters: $S(0)=\S1.54$ ; $K=\$1.58$ ; $T=1$ ; $r=8\%$ ; $r_{f}=6\%$ ; $\sigma=30\%$ ; payoff $R=\$10$ Gradually increase the value of $M$ and report the observed price of the options.  

7. (Barrier Option.) Write a VBA program to simulate $M=100$ stock prices using a Monte Carlo technique to calculate the price of Barrier down-and-out and down-and-in call options based on the following data: $S(O)=100\$ ; $K=110$ ; $T=1$ ; $r=8\%$ ; $\sigma=50\%$ ; $H=90$ Gradually increase the value of $M$ and report the observed price of the options.  

# MATLAB EXERCISES  

8. (European Options.) Write a MATLAB program to document the efficiency of a Monte Carlo approach to the estimation of European Call and Put option prices based on the following data:  

$S(O)=100\$ ; $K=105$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$   
Plot a graph of estimated prices as a function of the number of stock price simulations.  

9. (Barrier Option.) Write a MATLAB program to document the efficiency of a Monte Carlo approach to the estimation of the price of Down-and-Out and Down-and-In Call options based on the following data: • $S(0)=100$ ; $K=110$ ; $T=1$ ; $r=8\%$ ; $\sigma=30\%$ ; $H=90$ • Plot a graph of estimated prices as a function of the number of stock price simulations.  

10. (Digital Currency Option.) Write a MATLAB program to observe the efficiency of Monte Carlo technique to estimate the price of Digital Call and Put price with the following data: $S(0)=\S1.54$ ; $K=\$1.58$ ; $T=1$ ; $r=8\%$ ; $r_{f}=6\%$ ; $\sigma=30\%$ ; $R=\$10$ Plot the graph of estimated price v/s the no. of stock price simulation.  

11. (BDT Model Calibration.) Write a MATLAB program to calibrate the BDT model based on the following data on bond prices and implied volatilities $B(t_{0},t_{1})=0.95$ ; $B(t_{0},t_{2})=0.93$ ; $B(t_{0},t_{3})=0.91$ ; $B(t_{0},t_{4})=0.89$ $\sigma(0,1)=20\%$ ; $\sigma(0,2)=25\%$ ; $\sigma(0,3)=20\%$ ; $\sigma(0,4)=18\%$ Draw the LIBOR tree based on the output results.  

This page intentionally left blank  