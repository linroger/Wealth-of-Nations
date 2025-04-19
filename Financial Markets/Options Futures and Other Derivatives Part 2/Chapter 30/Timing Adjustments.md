---
tags:
  - '#correlation'
  - '#derivative_valuation'
  - '#forward_interest_rate'
  - '#forward_price'
  - '#ito_lemma'
  - '#numeraire_ratio'
  - '#stock_index'
  - '#timing_adjustments'
  - '#volatility'
---
# 30.2 TIMING ADJUSTMENTS  

In this section consider the situation where a market variable $V$ is observed at time $T$ and its value is used to calculate a payoff that occurs at a later time $T^{*}$ . Define:  

$V_{T}$ :Value of $V$ at time $T$ $E_{T}(V_{T})$ : Expected value of $V_{T}$ in a world defined by numeraire $\textstyle P(t,T)$ $E_{T^{*}}(V_{T})$ :Expected value of $V_{T}$ in a world defined by numeraire $\boldsymbol{P}(t,\boldsymbol{T}^{*})$  

The numeraire ratio when we move from the $\textstyle P(t,T)$ numeraire to the $\boldsymbol{P}(t,\boldsymbol{T}^{*})$ numeraire (see Section 28.8) is  

$$
W=\frac{P(t,T^{*})}{P(t,T)}
$$  

This is the forward price of a zero-coupon bond lasting between times $T$ and $T^{*}$ . Define:  

$\sigma_{V}$ :Volatility of $V$ $\sigma_{W}$ :Volatility of W Pvw:Correlation between V and W.  

From equation (28.35), the change of numeraire increases the growth rate of $V$ by $\alpha_{V}$ where  

$$
\alpha_{V}=\rho_{V W}\sigma_{V}\sigma_{W}
$$  

This result can be expressed in terms of the forward interest rate between times $T$ and $T^{*}$ Define:  

$R_{F}$ : Forward interest rate for period between $T$ and $T^{*}$ , expressed with a compounding frequency of $m$   
$\sigma_{R}$ :Volatility of $R_{F}$  

The relationship between $W$ and $R_{F}$ is  

$$
W=\frac{1}{(1+R_{F}/m)^{m(T^{*}-T)}}
$$  

The relationship between the volatility of $W$ and the volatility of $R_{F}$ can be calculated from Ito's lemma as  

$$
\sigma_{W}W=\sigma_{R}R_{F}{\frac{\partial W}{\partial R_{F}}}=-{\frac{\sigma_{R}R_{F}(T^{*}-T)}{(1+R_{F}/m)^{m(T^{*}-T)+1}}}
$$  

so that  

$$
\sigma_{W}=-{\frac{\sigma_{R}R_{F}(T^{*}-T)}{1+R_{F}/m}}
$$  

Hence equation (30.2) becomes  

$$
\alpha_{V}=-{\frac{\rho_{V R}\sigma_{V}\sigma_{R}R_{F}(T^{*}-T)}{1+R_{F}/m}}
$$  

where $\rho_{V R}=-\rho_{V W}$ is the instantaneous correlation between. $V$ and $R_{F}$ . As an approximation, it can be assumed that. $R_{F}$ remains constant at its initial value and that the volatilities and correlation in this expression are constant to get, at time zero,  

$$
E_{T^{*}}(V_{T})=E_{T}(V_{T})\mathrm{exp}\Bigg[-{\frac{\rho_{V R}\sigma_{V}\sigma_{R}R_{F}(T^{*}-T)}{1+R_{F}/m}}T\Bigg]
$$  

# Example 30.2  

Consider a derivative that provides a payoff in 6 years equal to the value of a stock index observed in 5 years. Suppose that 1,200 is the forward value of the stock index for a contract maturing in 5 years. Suppose that the volatility of the index is $20\%$ , the volatility of the forward risk-free interest rate between years 5 and 6 is $18\%$ , and the correlation between the two is. $-0.4$ . Suppose further that the risk-. free zero curve is flat at. $8\%$ with annual compounding. The results just produced. can be used with $V$ defined as the value of the index,. $T=5$ $T^{*}={\bar{6}}$ $m=1$ $R_{F}=0.08,\rho_{V R}=-0.4,\sigma_{V}=0.2(\$ , and $\sigma_{R}=0.18$ , so that  

$$
E_{T^{*}}(V_{T})=E_{T}(V_{T})\mathrm{exp}\biggl[-{\frac{-0.4\times0.20\times0.18\times0.08\times1}{1+0.08}}\times5\biggr]
$$  

or $E_{T^{*}}(V_{T})=1.00535E_{T}(V_{T}).$ From the arguments in Chapter 28, $E_{T}(V_{T})$ is the forward price of the index, or 1,200. It follows that $E_{T^{*}}(V_{T})=1,200\times1.00535=$ 1,206.42. Using again the arguments in Chapter 28, it follows from equation (28.20) that the value of the derivative is $1,206.42\times P(0,6)$ . In this case, $P(0,6)=$ $1/1.08^{6}=0.6302$ , so that the value of the derivative is 760.25.  
