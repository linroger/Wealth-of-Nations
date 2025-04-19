---
tags:
  - american_futures_options
  - bond_futures
  - bond_futures_options
  - bsm_model
  - term_structure_model
aliases:
  - Bond Futures Options
  - Futures Options
key_concepts:
  - BSM approach
  - Bond futures options
  - Early exercise
  - European option
  - Term structure models
---

# 16.3 BOND FUTURES OPTIONS  

Bond futures in the United States are discussed in Chapter 11. Options on these futures contracts are traditional or equity-style options, which means that, like options on stocks, purchasers of options pay a premium at the time of purchase and, if exercised, realize their intrinsic values.  

Options on bond futures can be valued with term structure models. In a one-factor model, for example, after creating a risk-neutral tree for the futures price, the value of a futures option can be computed by starting from the maturity date of the option and working backwards, using the rule that. the value of the option at each node is the maximum of the value of holding. the option and of exercising it immediately. Of course, because the delivery options embedded in bond futures may not be modeled adequately by a. one-factor model, multi-factor approaches might be preferred..  

While simple conceptually, it is apparent from Chapter 11 that build-. ing a futures model takes a good deal of effort. Therefore, practitioners who do not otherwise need such a model tend to use a BSM approach for bond futures options. The required assumptions are that: the option is European; the discount factor to option expiration is uncorrelated with the underlying futures price; and the futures price is lognormal with constant volatility. The assumption that the option is European, that is, that early exercise is not optimal, is reasonable in practice. Early exercise of an equitystyle futures option may be optimal if interest earned on the realized intrinsic value exceeds the time value of the option, but this is rarely the case. For some intuition on this point, note that early exercise of a put on a stock may be optimal, because of the potential of earning interest on the entire strike price, not just on its intrinsic value. The assumption that the discount factor is uncorrelated with the bond futures price is not bad in practice. Bond futures options typically mature in a few months or less, while the bond underlying the futures contract typically matures in many years. Hence, the correlation is typically weak between the discount factor, which depends on very short-term rates, and the bond futures price, which depends on longer-term rates. The assumption of constant price volatility, however, essentially assumes away the delivery options of bond futures: as rates change and the cheapest-to-deliver bond changes, the Dv01 and, therefore, the price volatility of the futures changes as well. (See Chapter 11.) While perhaps acceptable when interest rates are low relative to the contract's notional coupon, ignoring the delivery option seems to undercut one of the main motivations for using BSM in the first place, namely, to obtain accurate deltas. Nevertheless, BSM is used in practice in this context.  

Under the assumptions listed in the previous paragraph, Appendix. A16.3 shows that calls and puts on US Treasury note and bond futures contracts are given by, respectively,.  

$$
\begin{array}{c}{{\S N\times d_{0}(T)\times\xi^{L N}(S_{0},T,K,\sigma)/100}}\ {{\S N\times d_{0}(T)\times\pi^{L N}(S_{0},T,K,\sigma)/100}}\end{array}
$$  

TABLE 16.4 A Call Option on the June 10-Year. Treasury Note Futures Contract, as of February 28, 2022. The Futures Contract and Option Mature on. June 21, 2022.   


<html><body><table><tr><td>Quantity Value</td></tr><tr><td>So 126.3438</td></tr><tr><td>113 =0.3096</td></tr><tr><td>T 365</td></tr><tr><td>K 126.5 5.655%</td></tr><tr><td>d(T) 0.9979%</td></tr><tr><td>gLN(So, T, K,α) 1.50996</td></tr><tr><td>V。 = $100,000 × do(T)× gLN/100 $1,509.96</td></tr></table></body></html>  

where $N$ is the face amount of bonds per contract;. $S_{0}$ is the futures price; $T$ is the time to option expiration; $K$ is the strike price; $\sigma$ is the lognormal or percentage price volatility; and. $d_{0}(T)$ is the discount factor to option expiration. Table 16.4 applies Equation (16.6) to a call option on the June 10-year US Treasury note futures contract as of the end of February 2022, where both the futures and option contracts expire on June 21, 2022. Note that there are 113 days from February 28, 2022, to June 21, 2022.  
