---
tags:
  - asset_exchange
  - correlation
  - derivative_valuation
  - option_pricing
  - volatility
aliases:
  - Asset Exchange Option
  - Exchange Option
key_concepts:
  - Asset volatilities and correlation
  - Income at rate
  - Numeraire security
  - Option to exchange assets
  - Option value formula
---

# 28.7 OPTION TO EXCHANGE ONE ASSET FOR ANOTHER  

Consider next an option to exchange an investment asset worth $U$ for an investment asset worth $V$ . This has already been discussed in Section 26.14. Suppose that the volatilities of $U$ and $V$ are $\sigma_{U}$ and $\sigma_{V}$ and the coefficient of correlation between them is $\rho$  

Assume first that the assets provide no income and choose the numeraire security to be $U$ Setting $f=V$ in equation (28.15) gives  

$$
V_{0}=U_{0}E_{U}\bigg(\frac{V_{T}}{U_{T}}\bigg)
$$  

where $E_{U}$ denotes expectations in a world defined by the numeraire $U$ (We are here using the multifactor extension of equation (28.15) because $V$ and $U$ may depend on different Wiener processes.)  

The variable $f$ in equation (28.15) can be set equal to the value of the option under consideration, so that $f_{T}=\operatorname*{max}(V_{T}-U_{T},0)$ . It follows that  

$$
f_{0}=U_{0}E_{U}\bigg[\frac{\mathrm{max}(V_{T}-U_{T},0)}{U_{T}}\bigg]
$$  

or  

$$
f_{0}={U_{0}E_{U}}\Big[\mathrm{max}\Big(\frac{V_{T}}{U_{T}}-1,0\Big)\Big]
$$  

The volatility of. $V/U$ is $\hat{\sigma}$ (see Problem 28.13), where  

$$
\hat{\sigma}^{2}=\sigma_{U}^{2}+\sigma_{V}^{2}-2\rho\sigma_{U}\sigma_{V}
$$  

From equation (15A.1), equation (28.31) becomes  

$$
f_{0}={\cal U}_{0}\biggl[E_{U}\biggl(\frac{V_{T}}{U_{T}}\biggr)N(d_{1})-N(d_{2})\biggr]
$$  

where  

$$
d_{1}=\frac{\ln(V_{0}/U_{0})+\hat{\sigma}^{2}T/2}{\hat{\sigma}\sqrt{T}}\mathrm{and}d_{2}=d_{1}-\hat{\sigma}\sqrt{T}
$$  

Substituting from equation (28.30) gives  

$$
f_{0}=V_{0}N(d_{1})-U_{0}N(d_{2})
$$  

This is the value of an option to exchange one asset for another when the assets provide no income.  

Problem 28.8 shows that, when $f$ and $g$ provide income at rate. $q_{f}$ and $q_{g}$ , equation (28.15) becomes  

$$
f_{0}=g_{0}e^{(q_{f}-q_{g})T}E_{g}{\bigg(}{\frac{f_{T}}{g_{T}}}{\bigg)}
$$  

This means that equations (28.30) and (28.31) become  

$$
E_{U}\bigg({\frac{V_{T}}{U_{T}}}\bigg)=e^{(q_{U}-q_{V})T}{\frac{V_{0}}{U_{0}}}
$$  

and  

$$
f_{0}=e^{-q_{U}T}U_{0}E_{U}\bigg[\operatorname*{max}\bigg(\frac{V_{T}}{U_{T}}-1,0\bigg)\bigg]
$$  

and equation (28.32) becomes  

$$
f_{0}=e^{-q_{V}T}V_{0}N(d_{1})-e^{-q_{U}T}U_{0}N(d_{2})
$$  

with $d_{1}$ and $d_{2}$ being redefined as  

$$
d_{1}=\frac{\ln(V_{0}/U_{0})+(q_{U}-q_{V}+\hat{\sigma}^{2}/2)T}{\hat{\sigma}\sqrt{T}}\mathrm{and}d_{2}=d_{1}-\hat{\sigma}\sqrt{T}
$$  

This is the result given in equation (26.5) for the value of an option to exchange one asset for another.  
