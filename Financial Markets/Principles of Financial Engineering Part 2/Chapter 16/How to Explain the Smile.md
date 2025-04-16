---
tags:
  - '#black_scholes_formula'
  - '#equity_markets'
  - '#gamma'
  - '#implied_volatility'
  - '#jump_diffusion_model'
  - '#market_conventions'
  - '#option_pricing'
  - '#out_of_the_money_options'
  - '#stochastic_volatility'
  - '#volatility_smile'
---
# 16.13 HOW TO EXPLAIN THE SMILE  

The volatility smile is an empirical phenomenon that violates the assumptions of the. Black-Scholes world. At the same time, the volatility smile is related to the implied volatilities. obtained from the Black-Scholes formula. This may give rise to confusion. The smile suggests. that the Black-Scholes formula is not valid, while at the same time, the trader obtains the smile using the very same Black-Scholes formula. Is there an internal inconsistency?  

The answer is no. To clarify the point, we use an analogy that is unrelated to the present discus-. sion, but illustrates what market conventions are. Consider the 3-month LIBOR rate $L_{t}$ What is the present value of, say, $\$100$ that will be received in 3 months' time? We saw in Chapter 3 that all. we need to do is calculate the ratio:.  

$$
\frac{100}{(1+L_{t}\frac{1}{4})}
$$  

An economist who is used to a different decompounding may disagree and use the following present value formula:  

$$
\frac{100}{(1+L_{t})_{4}^{1}}
$$  

Who is right? The answer depends on the market convention. If $L_{t}$ is quoted under the condition that formula (16.64) be used, then formula (16.65) would be wrong if used with the same $L_{t}$ However, we can always calculate a new $L_{t}^{*}$ using the equivalence:  

$$
{\frac{100}{(1+L_{t}{\frac{1}{4}})}}={\frac{100}{(1+L_{t}^{*})_{4}^{\perp}}}
$$  

Then, the formula  

$$
\frac{100}{(1+L_{t}^{*})_{4}^{1}}
$$  

used with $L_{t}^{*}$ would also yield the correct present value. The point is, the market is quoting an interest rate $L_{t}$ with the condition that it is used with formula (16.64). If for some odd reason a client wants to use formula (16.65), then the market would quote $L_{t}^{*}$ instead of $L_{t}$ . The result would. be the same since, whether we use formula (16.64) with $L_{t}$ , as the market does, or formula (16.65) with $L_{t}^{*}$ , we would obtain the same present value. In other words, the question of which formula is correct depends on how the market quotes the variable of interest.  

This goes for options also. The Black-Scholes formula may be the wrong formula if we substitute one particular volatility, but may give the right answer if we use another volatility. And the. latter may be different than the real-world volatility at that instant. But traders can still use a. particular volatility to obtain the right option price from this "wrong' formula, just as in the earlier. present value example. This particular volatility, when associated with the Black-Scholes formula, may give the correct value for the option even though the assumptions leading to the formula are. not satisfied.  

Thus, suppose the arbitrage-free option price obtained under the "correct"' assumptions is given by  

$$
C(S_{t},t,T,K,\sigma_{t}^{*},\theta_{t})
$$  

where $K$ is the strike price,. $T$ is the expiration date, and $S_{t}$ is the underlying asset price. The (vec-. tor) variable. $\theta_{t}$ represents all the other parameters that enter the "correct' formula and that may not. be taken into account by the Black-Scholes world. For example, the volatility may be stochastic, and some parameters that influence the volatility dynamics may indirectly enter the formula and be part of $\theta_{t}$ 13 The critical point here is the meaning that is attached to. $\boldsymbol{\sigma}_{t}^{*}$ . We assume for now that it is the correct instantaneous volatility as of time. $t.$  

The (correct) pricing function in Eq. (16.68) may be more complex and may not even have a closed-form solution in contrast to the BlackScholes formula, $F(S_{t},t,\sigma)$ . Suppose traders ignore Eq. (16.68) but prefer to use the formula $F(S_{t},t,\sigma)$ , even though the latter is "wrong." Does this mean traders will calculate the wrong price?  

Not necessarily. The "wrong' formula. $F(S_{t},t,\sigma)$ can very well yield the same option price as $C$ $(S_{t},t,K,\sigma_{t}^{*},\theta_{t})$ if the trader uses in. $F(S_{t},t,\sigma)$ , another volatility, $\sigma$ , such that the two formulas give. the same correct price:  

$$
C(S_{t},t,K,\sigma_{t}^{*},\theta_{t})=F(S_{t},t,\sigma)
$$  

Thus, we may be able to get the correct option price from the "unrealistic' Black-Scholes formula if we proceed as follows:  

1. We quote the $K_{i}$ strike option volatilities $\sigma_{i}$ directly at every instant $t$ under the condition that the Black-Scholes formula be used to obtain the option value. Then, liquid and arbitrage-free markets will supply "correct" observations of the ATM volatility $\sigma_{0}$   
2. For out-of-the-money options, we use the Black-Scholes formula with a new volatility denoted by $\sigma((S/K_{i}),S)$ , and  

$$
\sigma\left({\frac{S}{K_{i}}},S\right)=\sigma_{0}+f\left({\frac{S}{K_{i}}},S\right)
$$  

where $f(.)$ is, in general, positive and implies a smile effect. The adjustment made to the ATM volatility, $\sigma_{0}.$ is such that when. $\sigma((S/K_{i}),S)$ is used in the Black-Scholes formula, it gives the correct value for $K_{i}$ strike option:  

$$
F{\Bigg(}S_{t},t,K_{i},\sigma_{0}+f{\Bigg(}{\frac{S}{K_{i}}},S{\Bigg)}{\Bigg)}=C(S_{t},t,K_{i},\sigma_{t}^{*},\theta_{t})
$$  

The adjustment factor $f((S/K_{i}),S)$ is determined by the trader's experience, knowledge, and the trading environment at that instant. The relationships between risk reversal, butterfly, and ATM volatilities discussed in the previous section can also be used here.15  

The trader, thus, adjusts the volatility of the non-ATM options so that the wrong formula gives the correct answer, even though what is used in the Black-Scholes formula may not be the "correct" instantaneous realized volatility of the $S_{t}$ process.  

The $f((S/K_{i}),S)$ is, therefore, an adjustment required by the imperfections of the Black-Scholes formula in adequately representing the real-world environment. The upshot is that when we plot $\sigma((S/K_{i}),S)$ against $K_{i}/S$ 0r $K_{i}$ we get a smile, or a skew curve, depending on the time and the sec-. tor we are working with.  

For what types of situations should the volatilities be adjusted? At least three inconsistencies of the Black-Scholes assumptions with the real world can be corrected for by adjusting the volatilities across the strike $K_{i}$ The first is the lognormal process assumption. The second is the fact that if asset prices fall dramatically during a relatively short period of time, this could increase the "fear factor" and volatility would increase. The third involves the organizational and regulatory assumptions concerning financial markets. We discuss these in more detail next.  

# 16.13.1 CASE 1: NONGEOMETRIC PRICE PROCESSES  

Suppose the underlying obeys the true risk-neutral dynamics described by the SDE:  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{~d}t+\sigma S_{t}^{\alpha}\mathrm{~d}W_{t}\quad t\in[0,\infty)
$$  

With $\alpha=1,~S_{t}$ would be lognormal. Everything else being conformable to the Black-Scholes world, there would be no smile in the implied volatilities.  

The caseof $\alpha<1$ would require an adjustment to the volatility coefficient used in the Black-Scholes formula as the strike changes. This is true, since, unlike in the case of $\alpha=1$ , now the percentage volatility is dependent on the level of. $S_{t}$ We divide by $S_{t}$ to obtain  

$$
\frac{\mathrm{d}S_{t}}{S_{t}}=r\mathrm{d}t+\sigma S_{t}^{\alpha-1}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

The percentage volatility is given by the term. $\sigma S_{t}^{\alpha-1}$ . This percentage volatility will be a. decreasing function of. $S_{t}$ if $\alpha<1.$ As $S_{t}$ declines, the percentage volatility increases. Thus, the trader needs to use higher implied volatility parameters in the Black-Scholes formula for put options with lower and lower strike prices. This means that the more out-of-the-money the put option is, the higher the volatility used in the Black-Scholes formula must be.  

This illustrates the idea that although the trader knows that the Black-Scholes world is far from reality, the volatility is adjusted so that the original Black-Scholes framework is preserved and that a "wrong" formula can still give the correct option value.  

# 16.13.2 CASE 2: POSSIBILITY 0F CRASH  

Suppose a put option series has an expiration of 2 months. All options are identical except for their strike. They run from ATM to deep out-of-the-money. Suppose also that the current level of $S_{t}$ is 100. The liquid put options have strikes 90, 80, 70, and 60.  

Here is what the 90-strike option implies. If the option expires in-the-money, then the market would have fallen by at least $10\%$ in 2 months. This is a big fall, perhaps, but not a disaster. In contrast, if the 60-strike put expires in-the-money, this would imply a $40\%$ drop in 2 months. This is clearly an unusual event, and unusual events lead to sudden spikes in volatility. Thus, the 60-strike option is relatively more associated with events that are labeled as crises and, everything else the same, this option would, in all likelihood, be in-the-money when the volatility is very high. But when this option becomes in-the-money, its gamma, which originally is close to zero, will also be higher. Thus, the trader who sells this option would have higher cash payouts due to delta hedge adjustments. So, to compensate for these potentially higher cash payments, the trader would use higher and higher vol parameters in put options that are more and more out-of-the-money, and, hence, are more and more likely to be associated with a crisis situation.  

This explanation is consistent with the smiley shapes observed in reality. Note that in FX mar-. kets, sudden drops and sudden increases would mean higher volatility because in each case one of the observed currencies could be falling dramatically. So the smile will be more or less.  

symmetric. But in the case of equity markets, a sudden increase in equity prices may be an important event, but not a crisis at all. For traders (excluding the shorts) this is a happy" outcome, and the volatility may not increase much. In contrast, when asset prices suddenly crash, this increases the fear factor and the volatilities may spike. Thus, in equity markets the smile is expected to be mostly one-sided if this explanation is correct. It turns out that empirical data support this contention. Out-of-the-money equity puts have a smile, but out-of-the-money equity calls exhibit almost no smile.  

# EXAMPLE  

Consider Table 16.2 which displays the prices of options with June 2002 expiry, on January 10, 2002, and ignore issues related to Americanness or any possible payouts. These data are collected at the same time as those discussed in the earlier example. In this case, the options are longer dated and expire in about 6 months. First, we obtain the volatility smile for these data.  

The data are collected at the same instant, and since the current value of the underlying index is the same in each case, the division by. $S_{t_{0}}$ is not a major issue, but we still prefer to. graph the volatility smile against the $K/S$  

We extract ask prices for the 8 out-of-the-money puts and consider the 600-put as being in-the-money. This way we can calculate nine implied vols. The price data that we use are shown in Table 16.2. We consider first the out-of-the-money put asking prices listed in the sixth column of this table. This will give nine prices.  

<html><body><table><tr><td colspan="6">Table 16.2 OEX Options with June 21, 2002, Expiry (Collected 9:46 CBOT on January 10,2002)</td></tr><tr><td>Calls</td><td>Bid</td><td>Ask</td><td>Puts</td><td>Bid</td><td>Ask</td></tr><tr><td>Jun 440 Jun 460</td><td>153.4 134.8</td><td>156.4 137.8</td><td>Jun 440 Jun 460</td><td>4.2 5.6</td><td>4.8 6.3</td></tr><tr><td>Jun 480</td><td>116.7</td><td>119.7</td><td>Jun 480</td><td>7.4</td><td>8.1</td></tr><tr><td>Jun 500</td><td>99.2 82.6</td><td>102.2 85.6</td><td>Jun 500</td><td>9.9</td><td>10.6</td></tr><tr><td>Jun 520</td><td>67.2</td><td>69.7</td><td>Jun 520 Jun 540</td><td>12.9</td><td>14.4</td></tr><tr><td>Jun 540</td><td>52.7</td><td>55.2</td><td>Jun 560</td><td>17.2 22.7</td><td>18.7</td></tr><tr><td>Jun 560</td><td>39.8</td><td>41.8</td><td>Jun 580</td><td></td><td>24.2</td></tr><tr><td>Jun 580</td><td>28.6</td><td></td><td></td><td>29.3</td><td>31.3</td></tr><tr><td>Jun 600</td><td>19.9</td><td>30.6</td><td>Jun 600</td><td>38.3</td><td>40.3</td></tr><tr><td>Jun 620</td><td>12.8</td><td>21.4</td><td>Jun 620</td><td>49.5</td><td>51.5</td></tr><tr><td>Jun 640</td><td>8</td><td>14.3</td><td>Jun 640 Jun 660</td><td>62.2</td><td>64.7</td></tr><tr><td>Jun 660</td><td>4.7</td><td>8.7</td><td>Jun 680</td><td>76.9</td><td>79.9</td></tr><tr><td>Jun 680</td><td></td><td>5.4</td><td></td><td>93.7</td><td>96.7</td></tr><tr><td>Jun 700</td><td>2.55</td><td>3.2</td><td>Jun 700</td><td>111.6</td><td>114.6</td></tr></table></body></html>  

Ignoring other complications that may exist in reality, we use the Black-Scholes formula straightforwardly with  

$$
S_{t_{0}}=589.15,r=1.90\%,t={\frac{152}{365}}=0.416
$$  

We solve the equations  

$$
P(589.15,K_{i},1.90,\sigma_{K_{i}},0.416)=P_{K_{i}}\quad i=1,...,9
$$  

and obtain the nine implied volatilities $\sigma_{K_{i}}$ . Using Mathematica, we obtain the following result, which shows the value of $K_{i}/S$ and the corresponding implied vols for out-of-the-money puts:  

<html><body><table><tr><td>KSI</td><td>Vol</td></tr><tr><td>0.74</td><td>0.26</td></tr><tr><td>0.78</td><td>0.26</td></tr><tr><td>0.81</td><td>0.26</td></tr><tr><td>0.84</td><td>0.25</td></tr><tr><td>0.88</td><td>0.25</td></tr><tr><td>0.91</td><td>0.24</td></tr><tr><td>0.95</td><td>0.23</td></tr><tr><td>0.98</td><td>0.22</td></tr><tr><td>1.01</td><td>0.21</td></tr></table></body></html>  

This is shown in Figure 16.15. Clearly, as the moneyness of the puts decreases, the volatility increases. Option market makers will conclude that, if in 6 months, US equity markets  

![](images/128b2bc82bd9652346b89a15b457ff65d1ec3bbf939fd8aa7f4b18d53755fc26.jpg)  

# FIGURE 16.15  

Implied volatility of OEX options against moneyness.  

were to drop by $25\%$ , then the fear factor would increase volatility from. $21\%$ to $26\%$ . By selecting the seven out-of-the-money call prices, we get the implied vols for out-of-themoney calls.  

<html><body><table><tr><td>K-SI</td><td>Vol</td></tr><tr><td>0.98</td><td>0.23</td></tr><tr><td>1.01</td><td>0.22</td></tr><tr><td>1.05</td><td>0.21</td></tr><tr><td>1.08</td><td>0.20</td></tr><tr><td>1.12</td><td>0.19</td></tr><tr><td>1.15</td><td>0.19</td></tr><tr><td>1 18</td><td>0.18</td></tr></table></body></html>  

Here, the situation is different. We see that as moneyness of the calls decreases, the vola tility also decreases.  

Option market makers may now think that if, in 6 months, US equity markets were to increase by $20\%$ , then the fear factor would decrease and so would volatility.  

The fear of a crash that leads to a smile phenomenon can, under some conditions, be represented analytically using the so-called jump processes. We discuss this modeling approach next.  

# 16.13.2.1 Modeling crashes  

Consider again the standard geometric Brownian motion case:  

$$
\mathrm{d}S_{t}=r S_{t}\mathrm{~d}t+\sigma S_{t}\mathrm{~d}W_{t}\quad t\in[0,\infty)
$$  

$W_{t}$ is a Wiener process under the risk-neutral probability $\tilde{P}$ Now, keep the volatility parameterization the same, but instead, add a jump component as discussed in Lipton (2002). For example, let  

$$
 \mathrm{d}S_{t}=r S_{t}\mathrm{d}t-\sigma S_{t}\mathrm{d}W_{t}+S_{t}[(e^{j}-1)\mathrm{d}J_{t}-\lambda m\mathrm{d}t]\quad t\in[0,\infty)
$$  

Some definitions are needed regarding the term. $(e^{j}-1)\mathrm{d}J_{t}-\lambda m\mathrm{d}$ t. Thee $j$ is the size of a random. logarithmic jump. The size of the jump is not related to the occurrence of the jump, which is represented by the term. $\mathrm{d}J_{t}$ If the jump is of size zero, then $(e^{j}-1)=0$ and the jump term does not. matter.  

The term $\mathrm{d}J_{t}$ is a Poisson-type process. In general, at time $t$ it equals zero. But, with "small" probability, it can equal one. The probability of this happening depends on the length of the interval we are looking at, and on the size of the intensity coefficient $\lambda$ . The jump can heuristically be modeled as follows:  

$$
\mathrm{d}J_{t}={\left\{\begin{array}{l l}{0}&{{\mathrm{with~probability}}(1-\lambda\mathrm{{d}}t)}\ {1}&{{\mathrm{with~probability}}\lambda\mathrm{{d}}t}\end{array}\right.}
$$  

where $0<\mathrm{d}t$ is an infinitesimally short interval. Finally, $m$ is the expected value of. $(e^{j}-1)$  

$$
E_{t}^{\tilde{P}}[(e^{j}-1)]=m
$$  

Thus, we see that, for an infinitesimal interval we can heuristically write  

$$
\begin{array}{r l}&{E_{t}^{\tilde{P}}[(e^{j}-1)\mathrm{d}J_{t}]=E_{t}^{\tilde{P}}[(e^{j}-1)]E_{t}^{\tilde{P}}[\mathrm{d}J_{t}]}\ &{\qquad=m[0.(1-\uplambda\mathrm{d}t)+1.\uplambda\mathrm{d}t]}\ &{\qquad=m\uplambda\mathrm{d}t}\end{array}
$$  

According to this, the expected value of the term $(e^{j}-1)\mathrm{d}J_{t}-\lambda m\mathrm{d}t$ is zero.  

This jump-diffusion model captures some crash phenomena. Stock market crashes, major. defaults, 9/11-type events, and currency devaluations can be modeled as rare but discrete events that lead to jumps in prices.  

The way these types of jumps create a smile can be heuristically explained as follows. In a world where the Black-Scholes assumptions hold, with a geometric. $S_{t}$ process, a constant volatility parameter $\tilde{\sigma}$ , and no jumps, the volatility trade yields the arbitrage relation:.  

$$
\frac{1}{2}C_{s s}\tilde{\sigma}^{2}S^{2}+C_{t}+r C_{s}S-r C=0
$$  

With a jump term added to the geometric process as in Eq. (16.77), the corresponding arbitrage relation becomes  

$$
\frac{1}{2}C_{s s}^{*}\sigma^{2}S^{2}+C_{t}^{*}+(r-\uplambda m)C_{s}^{*}S-r C^{*}+\uplambda E_{t}^{\tilde{P}}\big[C^{*}(S e^{j},t)-C^{*}(S,t)\big]=0
$$  

where $\tilde{P}$ is the risk-neutral probability. Suppose we decide to use, as a convention, the. Black-Scholes formula, but believe that the true PDE is the one in Eq. (16.83). Then, we would select $\tilde{\sigma}$ such that the Black-Scholes formula yields the same option value as the other PDE. would yield.  

For example, out-of-the-money options will have much smaller gammas, $C_{s s}$ . If the expected jump is negative, then $\tilde{\sigma}$ will be bigger, and the more out-of-the-money the options are. As the expiration date $T$ increases, $C_{s s}$ will increase and the smile will be less pronounced..  

# 16.13.3 OTHER EXPLANATIONS  

Many other effects can cause a volatility smile. One is stochastic volatility. Consider a local volatility specification using  

$$
\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma S_{t}^{\alpha}\mathrm{d}W_{t}\quad t\in[0,\infty)
$$  

with, say,. $\alpha<1$ . In this specification, percentage volatility will be stochastic since it depends on the random variable $S_{t}$ But often this specification does not express what is meant by models of stochastic volatility. What is captured by stochastic volatility is a situation where an additional Wiener process $\mathrm{d}B_{t}$ possibly correlated with $\mathrm{d}W_{t}$ affects the dynamics of percentage volatility. For example, we can write  

$$
\begin{array}{r}{\begin{array}{c}{\mathrm{d}S_{t}=\mu S_{t}\mathrm{d}t+\sigma_{t}S_{t}\mathrm{d}W_{t}\quad t\in[0,\infty)}\ {\mathrm{d}\sigma_{t}=a(\sigma_{t},S_{t})\mathrm{d}t+\kappa\sigma_{t}\mathrm{d}B_{t}\quad t\in[0,\infty)}\end{array}}\end{array}
$$  

where $\kappa$ is the parameter representing the (constant) percentage volatility of the volatility of $S_{t}$ In this model, the volatility itself is driven by some random increments that originate in the volatility market only. These shocks are only partially correlated with the innovation terms $\mathrm{d}W_{t}$ affecting the price data.  

It can be shown that stochastic volatility generates a volatility smile. In fact, with stochastic volatility, we can perform an analysis similar to the PDE with a jump process (Lipton, 2002). The result will essentially be similar. However, it is important to emphasize that, everything else being the same, this model may be incomplete in the sense that there may not be enough instruments to hedge the risks associated with $\mathrm{d}W_{t}$ and $\mathrm{d}B_{t}$ completely, and form a risk-free, self-financing portfolio. The jump-diffusion model discussed in the previous section may entail the same problem. To the extent that the jump part and the diffusion part are affected by different processes, the model may not be complete.  

# 16.13.3.1 Structural and regulatory explanations  

Tax effects (Merton, 1976) and the capital requirements associated with carrying out-of-the-money. options in options books may also lead to a smile in implied volatility. We briefly touch on the second point.  

The argument involves the concept of gamma. A negative gamma position is considered to be more risky, the more out-of-the-money the option is. Essentially, negative gamma means that the market maker has sold options and delta hedged them, and that he or she is paying the gamma through the rebalancing of this hedge. If the option is deep out-of-the-money, gamma would be close to zero. Yet, if the option suddenly becomes in-the-money, the gamma could spike, especially if the option is about to expire. This may cause significant losses. Out-of-the-money options, therefore, involve substantial risk and require more capital. Due to such costs, the market maker may want to sell the out-of-the-money option at a higher price than warranted by the ATM volatility.  
