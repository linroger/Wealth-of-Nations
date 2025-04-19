---
tags:
  - cir_model
  - real_world_process
  - risk_neutral_process
  - vasicek_model
  - zero_coupon_bond
aliases:
  - market price of risk
  - risk premium
key_concepts:
  - Bonds have positive risk
  - Interest rates are negative
  - Real-world process
  - Risk-neutral process
  - Vasicek's model
---

# 31.3 REAL-WORLD VS. RISK-NEUTRAL PROCESSES  

Bonds have a positive market price of risk (i.e., positive systematic risk), so investors require an extra return over the risk-free rate for investing in bonds. Interest rates are negatively related to bond prices and therefore have negative market prices of risk.  

Suppose that $\lambda$ is the (negative) market price of risk of the short rate, $r.$ If the riskneutral process for $r$ is  

$$
d r=m(r)d t+s(r)d z
$$  

the real-world process, from Chapter 28, is  

$$
d r=[m(r)+\lambda s(r)]d t+s(r)d z
$$  

In the case of Vasicek's model, the risk-neutral process is  

$$
d r=a(b-r)d t+\sigma d z
$$  

so that the real-world process is  

$$
d r=[a(b-r)+\lambda\sigma]d t+\sigma d z
$$  

Assuming $\lambda$ is constant, this process is  

$$
d r=\left[a(b^{*}-r)\right]d t+\sigma d z
$$  

where $\boldsymbol{b}^{*}=\boldsymbol{b}+\lambda\boldsymbol{\sigma}/a$ The real-world process is therefore the same as the risk-neutral process except that the reversion level is lower (because $\lambda$ is negative).  

In the case of CIR, the risk-neutral process is  

$$
d r=a(b-r)d t+\sigma{\sqrt{r}}d z
$$  

It is convenient to assume that $\lambda=\kappa\sqrt{r}$ , where $\kappa$ is a (negative) constant, so that the real-world process is  

$$
d r=[a(b-r)+\kappa\sigma r]d t+\sigma{\sqrt{r}}d z
$$  

In this case,  

$$
d r=a^{*}(b^{*}-r)d t+\sigma{\sqrt{r}}d z
$$  

where $\boldsymbol{a}^{*}=\boldsymbol{a}-\kappa\boldsymbol{\sigma}$ and $\boldsymbol{b}^{*}=\boldsymbol{a}\boldsymbol{b}/a^{*}$ The real-world process is therefore the same as the risk-neutral process except that the reversion rate is higher and the reversion level is lower.  

Next, consider bonds. Equation (31.11) gives the risk-neutral process in Vasicek's model for a zero-coupon bond. When the market price of risk of the short rate is $\lambda$ , the real-world process is  

$$
d P(t,T)=\left[r(t)-\lambda\sigma B_{\mathrm{vas}}(t,T)\right]P(t,T)d t-\sigma B_{\mathrm{vas}}(t,T)P(t,T)d z(t)
$$  

Equation (31.12) gives the risk-neutral process in the CIR model for a zero-coupon  

bond. When the market price of risk is $\kappa\sqrt{r}$ , the real-world process is  

$$
d P(t,T)=\left[r(t)-\kappa\sigma B_{\mathrm{sir}}(t,T)r(t)\right]P(t,T)d t-\sigma\sqrt{r(t)}B_{\mathrm{sir}}(t,T)P(t,T)d z(t)
$$  
