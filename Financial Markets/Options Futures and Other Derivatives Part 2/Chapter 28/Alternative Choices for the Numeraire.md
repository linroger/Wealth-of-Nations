# 28.4  ALTERNATIVE CHOICES FOR THE NUMERAIRE  

We now present a number of examples of the equivalent martingale measure result. The first example shows that it is consistent with the traditional risk-neutral valuation result used in earlier chapters. The other examples prepare the way for the valuation of bond options, interest rate caps, and swap options in Chapter 29.  

# Money Market Account as the Numeraire  

The dollar money market account is a security that is worth $\$1$ at time zero and earns. the instantaneous risk-free rate $r$ at any given time. The variable $r$ may be stochastic. If. we set $g$ equal to the money market account, it grows at rate $r$ so that  

$$
d g=r g d t
$$  

The drift of $g$ is stochastic, but the volatility of $g$ is zero. It follows from the results in Section 28.3 that $f/g$ is a martingale in a world where the market price of risk is zero. This is the world we defined earlier as the traditional risk-neutral world. From equation (28.15),  

$$
f_{0}=g_{0}\hat{E}\bigg(\frac{f_{T}}{g_{T}}\bigg)
$$  

where $\hat{E}$ denotes expectations in the traditional risk-neutral world.  

In this case, $g_{0}=1$ and  

$$
g_{T}=e^{\int_{0}^{T}r d t}
$$  

so that equation (28.17) reduces to  

$$
f_{0}=\hat{E}(e^{-\int_{0}^{T}r d t}f_{T})
$$  

or  

$$
f_{0}=\hat{E}(e^{-\bar{r}T}f_{T})
$$  

where $\bar{r}$ is the average value of $r$ between time 0 and time $T.$ This equation shows that one way of valuing an interest rate derivative is to simulate the short-term interest rate $r$ in the traditional risk-neutral world. On each trial the payoff is calculated and discounted at the average value of the short rate on the sampled path.  

When the short-term interest rate. $r$ is assumed to be constant, equation (28.19 reduces to  

$$
f_{0}=e^{-r T}\hat{E}(f_{T})
$$  

or the risk-neutral valuation relationship used in earlier chapters.  

# Zero-Coupon Bond Price as the Numeraire  

Define $\textstyle P(t,T)$ as the price at time $t$ of a risk-free zero-coupon bond that pays off $\$1$ at time $T.$ We now explore the implications of setting the numeraire $g$ equal to $\textstyle P(t,T)$ . Let $E_{T}$ denote expectations in a world defined by this numeraire. Because $g_{T}=P(T,T)=1$ and $g_{0}=P(0,T)$ , equation (28.15) gives  

$$
f_{0}=P(0,T)E_{T}(f_{T})
$$  

Notice the difference between equations (28.20) and (28.19). In equation (28.19), the discounting is inside the expectations operator. In equation (28.20), the discounting, as  

represented by the $\textstyle P(0,T)$ term, is outside the expectations operator. The use of. $\textstyle P(t,T)$ as the numeraire therefore considerably simplifies things for a security that provides a payoff solely at time $T$  

Consider any variable $\theta$ that is not an interest rate.6 A forward contract on $\theta$ with maturity $T$ is defined as a contract that pays off $\theta_{T}-K$ at time $T$ where $\theta_{T}$ is the value $\theta$ at time $T.$ Define $f$ as the value of this forward contract. From equation (28.20),  

$$
f_{0}=P(0,T)[E_{T}(\theta_{T})-K]
$$  

The forward price, $F$ of $\theta$ is the value of $K$ for which $f_{0}$ equals zero. It therefore follows that  

$$
P(0,T)[E_{T}(\theta_{T})-F]=0
$$  

or  

$$
F=E_{T}(\theta_{T})
$$  

Equation (28.21) shows that the forward price of any variable (except an interest rate) is its expected future spot price in a world defined by the numeraire $\textstyle P(t,T)$ . Note the difference here between forward prices and futures prices. The argument in Section 18.6 shows that the futures price of a variable is the expected future spot price in the traditional risk-neutral world.  

To summarize, equation (28.20) shows that any security that provides a payoff at time $T$ can be valued by calculating its expected payoff in a world defined by the. numeraire that is a bond maturing at time. $T$ and discounting at the current risk-free rate. for maturity $T.$ Equation (28.21) shows that it is correct to assume that the expected value of the underlying variables equal their forward values when computing the. expected payoff.  

# Forward Interest Rates  

For the next result, define. $F(t)$ as the forward interest rate as seen at time $t$ for the period between $T$ and $T^{*}$ expressed with a compounding period of. $T^{*}-T$ .(For example, if $\boldsymbol{T}^{*}-\boldsymbol{T}=0.5$ , the interest rate is expressed with semiannual compounding; $T^{*}~{-}~T=0.25$ , it is expressed with quarterly compounding; and so on.)  

Define $R$ as the realized rate between $T$ and $T^{*}$ expressed with the same compounding frequency. From the definition of a forward interest rate, a forward rate agreement paying off $F(t)\mathrm{~-~}R$ at time $T^{*}$ is worth zero at time $t.$ From the result in equation (28.21), it follows that  

$$
P(0,T^{*})E_{T^{*}}(F(t)-R)=0
$$  

so that  

$$
E_{T^{*}}(R)=F(t)
$$  

Note that in this result $F(t)$ and $R$ can be calculated from any yield curve. In the case of the risk-free yield curve calculated from overnight interest rates, $R$ is not known until time $T^{*}$ . For other yield curves, $R$ is known at time $T.$ Equation (28.22) applies in both cases. The results we just have produced will be useful in explaining the valuation of interest rate caps and floors in the next chapter.  

# Annuity Factor as the Numeraire  

For the next application of equivalent martingale measure arguments, consider a floating-for-fixed swap starting at a future time $T$ with payment dates at times. $T_{1}$ $T_{2}$ ..., $T_{N}$ In the swap, a fixed rate of interest is exchanged for the floating rate. Define $T_{0}=T$ . Assume that the notional principal is $\$1$ . Suppose that the forward swap rate (i.e., the interest rate on the fixed side that makes the forward swap have a value of zero) is $s(t)$ at time $t\left(t\leq T\right)$ . The value of the fixed side of the swap is  

$$
s(t)A(t)
$$  

where  

$$
A(t)=\sum_{i=0}^{N-1}(T_{i+1}-T_{i})P(t,T_{i+1})
$$  

Define the value of the floating side as. $V(t)$ . Equating the values of the fixed and floating sides gives  

$$
s(t)A(t)=V(t)
$$  

or  

$$
s(t)=\frac{V(t)}{A(t)}
$$  

The equivalent martingale measure result can be applied by setting $f$ equal to $V(t)$ and $g$ equal to $A(t)$ . This leads to  

$$
s(t)=E_{A}[s(T)]
$$  

where $E_{A}$ denotes expectations in a world that is defined by the numeraire $A(t)$ . Therefore, in a world defined by this numeraire, the expected future swap rate is the current forward swap rate.  

The result in equation (28.15) shows that  

$$
V(0)=A(0)E_{A}{\Bigg[}{\frac{V(T)}{A(T)}}{\Bigg]}
$$  

This result, when combined with the result in equation (28.24), will be critical to an understanding of the standard market model for European swap options in the next. chapter. Note that in this result. $V(t)$ can be calculated from any yield curve, whereas. $A(t)$ is calculated from the risk-free zero curve. For example, the swap can be a LIBORfor-fixed swap, while the risk-free rate is calculated from the OIS zero curve..  
