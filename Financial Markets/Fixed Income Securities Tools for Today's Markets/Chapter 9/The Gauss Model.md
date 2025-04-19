---
tags:
  - business_cycles
  - gauss_model
  - interest_rates
  - mean_reversion
  - monetary_policy
  - term_structure
aliases:
  - G+ Model
  - Gauss Plus Model
key_concepts:
  - Gauss model introduction
  - Long-term expectations
  - Mean reversion parameters
  - Short-term interest rate
  - Term structure dynamics
---

# 9.2 THE GAUSS+ MODEL  

The Gauss $^{\ast+}$ model is well-known among practitioners as a tool for proprietary trading and hedging. The assumptions of the model are intuitively appealing, and they reasonably balance the goals of tractability and of capturing the empirical complexity of term structure dynamics. The goal of the text is to introduce the model, both in theory -- through its equations and. solution -- and in application - through a full estimation of its parameters using recent data. Introducing a detailed estimation procedure here is noteworthy, because methodologies across the industry vary widely. The goal of the extensive appendix to this section is to enable a determined reader to estimate and implement the model independently..  

The dynamics of the cascade form of the model are given in. Equations (9.9) through (9.12). The factors $r,m$ , and $l$ denote the shortterm rate of interest, a medium-term factor, and a long-term factor, respectively. The parameters $\mu$ and $\rho$ are discussed presently. The mean reversion parameters of the factors are, $\alpha_{r}$ $\alpha_{m}$ , and $\alpha_{l}$ respectively, and the volatility parameters for the medium- and long-term factors are $\sigma_{m}$ and $\sigma_{l}$ respectively. The two random variables in the model are. $d\mathbb{W}^{1}$ and $d\mathbb{W}^{2}$ The subscript $t$ denotes time- $\cdot t$ observations of the factors, of changes in the factors, and of the random variables. Finally, then, the equations are,.  

$$
\begin{array}{r l}&{~d\boldsymbol{r}_{t}=-\alpha_{r}(\boldsymbol{m}_{t}-\boldsymbol{r}_{t})d t}\ &{~d\boldsymbol{m}_{t}=-\alpha_{m}(l_{t}-m_{t})d t+\sigma_{m}(\rho d W_{t}^{1}+\sqrt{1-\rho^{2}}d W_{t}^{2})}\ &{~d l_{t}=-\alpha_{l}(\mu-l_{t})d t+\sigma_{l}d W_{t}^{1}}\ &{E[d W_{t}^{1}d W_{t}^{2}]=0}\end{array}
$$  

Given the structure of the model, it turns out that the medium- and long-term factors can be thought of as rates. The short-term rate mean reverts to the medium-term factor, which is meant to reflect business cycles and monetary policy factors. The medium-term factor reverts to the long-term factor, which is meant to reflect long-term expectations of inflation and the real interest rate, which ultimately depend on long-term trends in demographics, production technology, and so forth. And the long-term factor reverts to a constant, $\mu$ , which, as in the Vasicek model, can be thought of as including both a long-term expectation of the short-term rate and a risk premium. The mean reversion parameters are expected to be consistent with these economic interpretations; that is, the short-term rate reverts quickly to the medium-term factor; the medium-term factor reverts more slowly to the long-term factor; and the long-term factor reverts slowest of all to its target.  

While the medium- and long-term factors trend as described in the previous paragraph, they also fluctuate around these trends. With respect to the evolution of the long-term factor in Equation (9.11), the fluctuation over a short time. $d t$ is $\sigma_{l}d\mathbb{W}_{t}^{1}$ . Because $d\mathbb{W}_{t}^{1}$ is normally distributed with. mean zero and standard deviation $\sqrt{d t}$ the instantaneous fluctuation of the long-term factor around its trend has mean zero and volatility $\sigma_{l}\sqrt{d t}$ The random terms in Equation (9.10) look complicated, but they simply ensure that the instantaneous fluctuation of the medium-term factor around its trend has a volatility of. $\sigma_{m}{\sqrt{d t}}$ and a correlation of $\rho$ with the fluctuation of the long-term factor around its trend. To see this, note that $d\mathbb{W}_{t}^{2}$ also has mean zero and standard deviation $\sqrt{d t}$ , and, from Equation (9.12), zero correlation with. $d\mathbb{W}_{t}^{1}$ . It then follows from Equation (9.10) that the standard. deviation of $d m_{t}$ is,  

$$
\sqrt{\sigma_{m}^{2}(\rho^{2}d t+[1-\rho^{2}]d t)}=\sigma_{m}\sqrt{d t}
$$  

that the covariance of dm and $d l$ is,  

$$
\mathrm{Co}\nu[\sigma_{m}(\rho d\mathrm{W}^{1}+\sqrt{1-\rho^{2}}d\mathrm{W}^{2}),\sigma_{l}d\mathrm{W}^{1}]=\rho\sigma_{m}\sigma_{l}d t
$$  

and, therefore, that the correlation of dm and $d l$ is,  

$$
\frac{\rho\sigma_{m}\sigma_{l}d t}{\sigma_{m}\sqrt{d t}\times\sigma_{l}\sqrt{d t}}=\rho
$$  

The evolution of the short-term rate in the model, Equation (9.9), is meant to reflect how central banks conduct rate policy. The Fed, for example, keeps the short-term policy rate pegged or fixed at a target, but moves that target over time in a manner deemed appropriate for the state of the business cycle and monetary conditions. Mathematically, in Equation (9.9), the short-term rate is fixed over the very short time interval, $d t$ , in the sense that there is no random variable shocking the dynamics of $r$ . The rate, $r$ is pushed gradually, however, toward the medium-term factor, $^m$ , which in turn reverts to the long factor, l.  

The medium- and long-term factors move expectations of the short-term rate as of future dates. Because these expectations move smoothly over time,. the medium- and long-term factors are assumed to move in a continuous. fashion. The short-term rate, by contrast, changes in the real world by dis-. crete amounts, on a set of fixed dates, according to central bank policy decisions. The model approximates the future outcomes of this process, however, by a continuous process starting at today's short-term rate..  

The lack of a volatility term in Equation (9.9) is an important feature of the Gauss $^{+}$ model. As pointed out in the discussion of the Vasicek model, mean-reverting factors generate a downward-sloping term structure of volatility. Largely because of central banks, however, empirical and implied term structures of volatility tend to have a hump; that is, volatility is low for very short-term rates before increasing to a peak at intermediate-term or longer rates. In the Gauss $^{+}$ model, the lack of a random shock in the dynamics of $r$ keeps short-term rate volatility low. In this way, the Gauss+ model can match empirically observed hump-shaped term structures of volatility.  

In passing, the $\mathtt{G a u s s+}$ model gets its name from the lack of a volatility term in Equation (9.9). The "Gauss" part of the name indicates that interest rates have a normal or Gaussian distribution. But while most one-, two-, or three-factor normal models have a corresponding number of sources of risk, the Gauss+ model, strictly speaking, has three factors, but only two sources of risk. The model has three state variables in the sense that describing the state of the world in the model requires knowing the three factors, $r,m$ and $l.$ There are only two sources of risk, however, namely, $d\mathbb{W}^{1}$ and $d\mathbb{W}^{2}$ The $^{\circ\circ}+{}^{\mathfrak{s}}$ in the name, therefore, indicates the somewhat unusual presence of a factor or state variable that is not also a source of risk.  

As a final comment on the structure of the model, Equations (9.9) through (9.12) are the risk-neutral dynamics of the model. Additional assumptions allow for the identification of an implicit risk premium. An application of the model developed next shows how this may be done, assuming that only the long-term factor earns a risk premium.2  

Appendix A9.2 gives a detailed account of how the parameters of the. Gauss $^{\ast}$ model might be estimated from bond or swap data. A simplified overview is presented here, using daily data from January 2014 to January 2022 on the fed funds target rate (see Chapter 12) and on zero coupon bond prices of various maturities, which are derived from the prices of US Treasury bonds. The time series of zero coupon bond prices are published by the Federal Reserve Bank of New York and are publicly available.3  

Consistent with the interpretation of the model, the short-term rate,. $r_{\mathrm{{i}}}$ is taken each day as equal to the fed funds target rate on that day. While a gen-. eral collateral repo rate is theoretically more consistent with a term structure of Treasury interest rates, repo rates exhibit occasional idiosyncratic jumps. that complicate the estimation without significant offsetting advantages.  

Once estimated, the model factors are chosen to "fit" or match, each day,. the one-year rates, two and 10 years forward, and the fed funds target rate. Furthermore, as discussed presently, with these two- and 10-year forward rates fair by construction, the model becomes a tool for trading value in other parts of the curve relative to these fitted points. For ease of exposition, by the way, all forward rates mentioned from this point denote one-year rates some number of years forward..  

Although the model ultimately fits the two- and 10-year forward rates, note that the factors $^m$ and $l$ are in no way those forward rates themselves, in the way that. $r$ equals the fed funds rate. The relationships of all forward. rates to $^m$ and $l$ depend on the estimated model parameters and, in particular,. on the mean reversion parameters. More specifically, the larger. $\alpha_{r}$ , the faster changes to the factors $^m$ and l make their way into the term structure of rates. The larger $\alpha_{m}$ , the faster m converges to $l$ , and the less m affects longer-term yields. And the smaller $\alpha_{l}$ , the slower $l$ converges to $\mu$ , and the more similar or parallel is the effect of $l$ on all longer-term yields.  
