---
tags:
  - analytic_solutions
  - binomial_tree
  - fixed_income_securities
  - forward_rate
  - mean_reversion
  - risk_premium
  - short_term_rate
  - spot_rate
  - term_structure_models
  - vasicek_model
aliases:
  - Mean Reversion
  - Risk Neutrality
  - Short Rate Model
  - Term Structure
  - Vasicek
key_concepts:
  - Analytical solutions
  - Drift and shock
  - Mean reversion of rates
  - Risk premium impact
  - Risk-neutral dynamics
---

# 9.1 THE VASICEK MODEL  

The Vasicek model assumes mean reversion to set the expected path of the short-term rate. When below its long-term value, the short-term rate is expected to increase; when above its long-term value, the short-term rate is expected to decrease. Mathematically, the risk-neutral dynamics for the short-term rate, $r$ , are given by,  

$$
d r=k(\theta-r)d t+\sigma d w
$$  

In words, the instantaneous change in the short-term rate, $d r$ is determined by a trend or drift plus a random fluctuation or shock. The drift is equal to the parameter of mean reversion,. $k$ , times the distance. between the long-run value of the short-term rate,. $\theta$ , and its current value.. Because all variables are expressed in annualized terms, the. $d t$ factor adjusts for the actual passage of time. Say, for example, that. $r=2\%$ $k=0.0165$ and $\theta=11\%$ . Then the drift of the short-term rate in Equation (9.1) is. $0.0165(11\%-2\%)$ or $0.1485\%$ or 14.85 basis points per year. The drift over a month, therefore, with. $d t=1/12$ , would be $14.85/12$ or about 1.2 basis points per month. The shock around the drift in Equation (9.1) is sdw, where. $d w$ is a normally distributed random variable with mean equal to zero and.  

standard deviation equal to $\sqrt{d t}$ .The shock, therefore, is normally distributed with mean zero and standard deviation. $\sigma{\sqrt{d t}}$ . For example, if $\sigma$ is $0.95\%$ , or 95 basis points per year, then the volatility of the shock over a month is $95\times{\sqrt{1/12}}=27.4$ basis points.  

As explained in the previous chapter, fixed income security prices may incorporate a risk premium that is indistinguishable from a drift in the evolution of the short-term rate. Along these lines, Equation (9.1) can be viewed. as containing a drift due to a risk premium. Assume for the purposes of. this section that the risk premium is a known constant of $\lambda$ basis points per year, and that the long-run value of the short-term rate under the true or real-world probabilities is $r_{\infty}$ . In that case, the true process of the short-term rate with the addition of a drift due to the risk premium is,  

$$
\begin{array}{l}{d r=k(r_{\infty}-r)d t+\lambda d t+\sigma d w}\ {\quad=k\left(\left[r_{\infty}+\displaystyle\frac{\lambda}{k}\right]-r\right)d t+\sigma d w}\ {\quad\theta\equiv r_{\infty}+\displaystyle\frac{\lambda}{k}}\end{array}
$$  

Equation (9.3) neatly emphasizes the inability to distinguish expectations from risk premium by observing security prices: an infinite number of combinations of $r_{\infty}$ and $\lambda$ give the same $\theta$ and, therefore, the same risk-neutral price process in Equation (9.1).  

One reason that the Vasicek model is useful, both for learning about. term structure models and for some simple pricing and hedging applications,. is that most rates and prices from the model can be expressed through simple formulae. For the most complex securities, numerical methods, like binomial. trees, are needed, and Appendix A9.1 explains how the model's dynamics might be captured in a binomial tree. The text, however, continues by presenting analytic solutions of the model, of which some of the most useful are,  

$$
\begin{array}{l}{{E[r_{t}]=r_{0}e^{-k t}+\theta(1-e^{-k t})}}\ {{{}}}\ {{V[r_{t}]=\sigma^{2}{\frac{1-e^{-2k t}}{2k}}}}\ {{{}}}\ {{f(t)=\theta+e^{-k t}(r_{0}-\theta)-{\frac{\sigma^{2}}{2k^{2}}}(1+e^{-2k t}-2e^{-k t})}}\ {{{}}}\ {{\hat{r}(t)=\theta+{\frac{1-e^{-k t}}{k t}}(r_{0}-\theta)-{\frac{\sigma^{2}}{2k^{2}}}\left(1+{\frac{1-e^{-2k t}}{2k t}}-2{\frac{1-e^{-k t}}{k t}}\right)}}\end{array}
$$  

where $E[r_{t}]$ gives today's expectation of the short-term rate at time $t$ $V[r_{t}]$ gives the variance of the short-term rate at time $t,f(t)$ is the continuously compounded forward rate of term $t$ ; and $\hat{\boldsymbol{r}}(t)$ is the continuously compounded spot rate of term $t$  

Figures 9.1 through 9.3 illustrate these formulae with the parameter val-. ues given earlier. The expected short-term rate, according to Equation (9.4) and the solid line in Figure 9.1, moves gradually from $r_{0}$ today $(t=0)$ to $\theta$ in the very distant future $(t=\infty)$ . The mean reversion parameter governing. the speed of that adjustment, $k=0.0165$ , is sometimes quoted instead as a. half-life. From Equation (9.4), a shock to. $r_{0}$ decays according to the factor $e^{-k t}$ . And half of such a shock decays away after time. $b$ , such that,  

$$
\begin{array}{c}{{e^{-k b}=\displaystyle\frac{1}{2}}}\ {{b=l n(2)/k}}\end{array}
$$  

For the relatively small mean reverting parameter, $k=0.0165$ $b$ is over 42 years, which means that any shock to $r$ affects rate expectations over a very long period of time. Equivalently, the expected rate takes a very long time to revert from the current rate to $\theta$  

The standard deviation of the short-term rate around its expectations is given by the square root of (9.5) and shown by the dashed lines in Figure 9.1. With a volatility parameter of 95 basis points per year and a very slow mean reversion, the standard deviation around expectations is quite wide. The figure does show, however, that mean reversion narrows this standard deviation. Without mean reversion, the standard deviation of the short-term rate is greater, at $\sigma{\sqrt{t}}$ . Put another way, the pull of the short-term rate to the constant value $\theta$ reduces the standard deviation of the short-term rate as of any future date.  

![](e743777a47f9698620fd03c06159e945d2da04c75ed755330ae6824863335d76.jpg)  
FIGURE 9.1  Expectations of the Continuously Compounded Short-Term Rate in the Vasicek Model, with One-Standard-Deviation Bands. Light Dotted Lines Give Bands Without Any Mean Reversion. Model Parameters Are $r_{0}=2\%$ $\theta=11\%$ $k=0.0165$ , and $\sigma=0.95\%$  

Equations (9.6) and (9.7), illustrated in Figure 9.2, give the continuously. compounded forward and spot rates in the model. The shape of the forward curve is discussed presently. Recall, however, as discussed in Chapter 2, so long as the forward curve is above the spot curve, spot rates are increasing..  

Figure 9.3 shows the term structure of forward rate volatility in the.. model, that is, the instantaneous volatility of forward rates of different terms. Because the only volatility in the model is the volatility of changes in the short-term rate, the volatility of $f(t)$ from Equation (9.6) - is just $\sigma e^{-k t}$ . The mean reversion feature of the model, therefore, captures the empirical regularity that, for longer terms, the term structure of volatility is downward sloping. Empirical volatilities of short-term rates are much. lower than indicated in this figure, however, because the central bank pegs short-term rates. The Gauss $^{\ast}$ model, discussed next, has the flexibility to capture both a low short-term rate volatility and an ultimately declining term structure of volatilities. In any case, note from Equation (9.6) that the sensitivity of each forward rate to changes in the short-term rate is $e^{-k t}$ Hence, these sensitivities across terms have the same shape as in Figure 9.3..  

Figure 9.4, the last presented on the Vasicek model, decomposes the forward rate curve into expectations, risk premium, and convexity using the values $\lambda=0.125\%$ , which - given $\theta=11\%$ and Equation (9.3) - means that $r_{\infty}=3.424\%$ . In this decomposition, expectations are mildly increasing. over the coming years. Forward rates out to 10 year or so increase much more rapidly than expectations, however, due to the risk premium of 12.5 basis points per year. For longer terms, however, the (negative) convexity term grows rapidly, not only moderating the impacts of expectations and convexity but also actually causing forward rates to decline with term.  

![](80c3a67e3d3b4b9fa64bbee1d53ccdbcfa1a9bc83641fe055d8253aa1bc7a973.jpg)  
FIGurE 9.2  Continuously Compounded Forward and Spot Rates in the Vasicek Model. Model Parameters Are $r_{0}=2\%$ $\theta=11\%$ $k=0.0165$ , and $\sigma=0.95\%$  

![](eb58567ac3a8892fcd3c7e8b692abd8ab804044aaf896e4292f1995f8fe20024.jpg)  
FIGUre 9.3 Term Structure of Forward Rate Volatilities in the Vasicek Model. Parameters Are $r_{0}=2\%$ $\theta=11\%$ $k=0.0165$ , and $\sigma=0.95\%$  

![](c10126115bf9b1ea66dfdd5a2d4749709288cf0cd77c85c5c4dd584eb870f09f.jpg)  
FIGURe 9.4 Decomposition of the Forward Rates in the Vasicek Model into Expectations, Risk Premium, and Convexity. Model Parameters Are $r_{0}=2\%$ $\lambda=0.125\%$ $r_{\infty}=3.424\%$ $k=0.0165$ , and $\sigma=0.95\%$  

The Vasicek model has some limited uses for practitioners. It is a rela-. tively simple model, which is a great advantage. Furthermore, as explained in Chapter 6, a single factor can explain a large fraction of term structure variability, particular across longer maturities. The parameters. $r_{0},k$ and $\theta$ can be jointly calibrated to approximate both the shape of the term structure and the shape of rate sensitivities to the factor (i.e., Figure 9.3). The parameter $\sigma$ can be used to approximate an implied option volatility at one point of the term structure. With these considerations in mind, the model. can reasonably be used, for example, to price, compare values, and hedge. long-term bonds that are first callable after some intermediate number of years. The model is flexible enough to match the prices of noncallable bonds from 10 to 30 years, and also to match the most relevant volatility, namely,. the volatility of 10-year rates. Bond sensitivities to changes in interest rates, defined in the model as changes in $r$ , can be computed by shifting $r_{0}$ , recomputing prices, and computing DV01s or durations. To the extent that bonds of one maturity are hedged with bonds of another maturity, the effectiveness of the resulting hedges depend on the reliability of the shape in Figure 9.3..  

The model might also be used for trading and hedging relatively. long-term bonds. The value of. $r_{0}$ might be set each day so that the model. 10-year rate matches the market 10-year rate. Deviations of calculated prices of longer-term bonds from model predictions might then be taken as signals of relative value, with hedge ratios calculated as described in the previous paragraph. The success of relative value trading along these lines depends on the extent to which the model captures the equilibrium or steady state of the shape of the term structure. Also, as before, hedging effectiveness depends on the reliability of the term structure of sensitivities to the factor.  

The Vasicek model is not very widely used, however, because it is. too simple for most applications. First, the model is not flexible enough to approximate the wide variety of observed market term structures. Or,. put another way, calibrating the model to match one point on the term structure relies too heavily on the model to approximate all other points on the term structure. Second, while one factor does explain a lot of. term structure variability, a second factor can capture significantly more variability. In terms of the discussion in Chapter 6, more than one factor is needed to hedge intermediate- and shorter-term bonds. Third, the Vasicek model cannot capture the empirical regularity, mentioned already, that the. term structure of volatilities and, therefore, the term structure of factor. sensitivities, typically rises quickly with term and then flattens or declines. This limitation means that the model cannot simultaneously handle options. or other volatility-sensitive products that are spread out across the term. structure, nor can it reliably hedge bonds most sensitive to one segment of the term structure with bonds most sensitive to another segment. With these caveats, the text turns to a much more flexible term structure model..  
