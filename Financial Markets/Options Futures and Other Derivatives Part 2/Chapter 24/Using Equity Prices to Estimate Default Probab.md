# 24.6  USING EQUITY PRICES TO ESTIMATE DEFAULT PROBABILITIES  

When we use a table such as Table 24.1 to estimate a company's real-world probability of default, we are relying on the company's credit rating. Unfortunately, credit ratings. are revised relatively infrequently. This has led some analysts to argue that equity prices can provide more up-to-date information for estimating default probabilities..  

In 1974, Merton proposed a model where a company's equity is an option on the. assets of the company.' Suppose, for simplicity, that a firm has one zero-coupon bond outstanding and that the bond matures at time. $T.$ Define:  

$V_{0}$ : Value of company's assets today $V_{T}$ : Value of company's assets at time $T$ $E_{0}$ : Value of company's equity today $E_{T}$ : Value of company's equity at time $T$ $D$ : Debt repayment due at time $T$ $\sigma_{V}$ : Volatility of assets (assumed constant) $\sigma_{E}$ : Instantaneous volatility of equity.  

If $V_{T}<D$ , it is (at least in theory) rational for the company to default on the debt at time $T.$ The value of the equity is then zero. If $V_{T}>D$ , the company should make the debt repayment at time. $T$ and the value of the equity at this time is $V_{T}-D$ . Merton's. model, therefore, gives the value of the firm's equity at time $T$ as  

$$
E_{T}=\operatorname*{max}(V_{T}-D,0)
$$  

This shows that the equity is a call option on the value of the assets with a strike price equal to the repayment required on the debt. The Black-Scholes-Merton formula gives the value of the equity today as  

$$
E_{0}=V_{0}N(d_{1})-D e^{-r T}N(d_{2})
$$  

where  

$$
d_{1}=\frac{\ln(V_{0}/D)+(r+\sigma_{V}^{2}/2)T}{\sigma_{V}\sqrt{T}}\quad\mathrm{and}\quad d_{2}=d_{1}-\sigma_{V}\sqrt{T}
$$  

The value of the debt today is $V_{0}\mathrm{~-~}E_{0}$  

The risk-neutral probability that the company will default on the debt is $N(-d_{2})$ . To calculate this, we require $V_{0}$ and $\sigma_{V}$ Neither of these are directly observable. However, if the company is publicly traded, we can observe $E_{0}$ . This means that equation (24.3) provides one condition that must be satisfied by $V_{0}$ and $\sigma_{V}$ . We can also estimate $\sigma_{E}$ from historical data or options. From Ito's lemma,  

$$
\sigma_{E}E_{0}={\frac{\partial E}{\partial V}}\sigma_{V}V_{0}=N(d_{1})\sigma_{V}V_{0}
$$  

This provides another equation that must be satisfied by $V_{0}$ and $\sigma_{V}$ . Equations (24.3) and (24.4) provide a pair of simultaneous equations that can be solved for $V_{0}$ and $\sigma_{V}$ 10  

# Example 24.3  

The value of a company's equity is $\$3$ million and the volatility of the equity is $80\%$ . The debt that will have to be paid in 1 year is $\$10$ million. The risk-free rate is $5\%$ per annum. In this case $E_{0}=3$ $\sigma_{E}=0.80$ $r=0.05$ $T=1$ , and $D=10$ Solving equations (24.3) and (24.4) as indicated in footnote 10 yields $V_{0}=12.40$ and $\sigma_{V}=0.2123$ The parameter $d_{2}$ is 1.1408, so that the probability of default is $N(-d_{2})=0.127$ , or $12.7\%$ . The market value of the debt is $V_{0}\mathrm{~-~}E_{0}$ , or 9.40. The present value of the promised payment on the debt is $10e^{-0.05\times1}=9.51$ The expected loss on the debt is therefore $(9.51-9.40)/9.51$ , or about $1.2\%$ of its no-default value.  

The basic Merton model we have just presented has been extended in a number of ways.. For example, one version of the model assumes that a default occurs whenever the value of the assets falls below a barrier level. Another allows payments on debt. instruments to be required at more than one time..  

How well do the default probabilities produced by Merton's model and its extensions correspond to actual default experience? The answer is that Merton's model and its. extensions produce a good ranking of default probabilities (risk-neutral or real-world). This means that a monotonic transformation can be used to convert the probability of. default output from Merton's model into a good estimate of either the real-world or. risk-neutral default probability.11 It may seem strange to take a default probability. $N(-d_{2})$ that is in theory a risk-neutral default probability (because it is calculated from an option-pricing model) and use it to estimate a real-world default probability. Given the nature of the calibration process we have just described, the underlying assumption. is that the ranking of the risk-neutral default probabilities of different companies is the. same as the ranking of their real-world default probabilities..  
