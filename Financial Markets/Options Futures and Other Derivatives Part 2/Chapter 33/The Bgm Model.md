---
tags:
  - bgm_model
  - caplet_pricing
  - forward_rates
  - interest_rate_derivatives
  - libor_market_model
aliases:
  - BGM Model
  - LIBOR Model
key_concepts:
  - Forward rate
  - Forward rate volatilities
  - HJM model drawbacks
  - LIBOR market model
  - Reset times
  - Rolling risk-neutral world
---

# 33.2 THE BGM MODEL  

One drawback of the HJM model is that it is expressed in terms of instantaneous forward rates and these are not directly observable in the market. Another related drawback is that it is difficult to calibrate the model to prices of actively traded instruments. This has led Brace, Gatarek, and Musiela (BGM), Jamshidian, and Miltersen, Sandmann, and Sondermann to propose an alternative.4 At the time the. model was developed, LIBOR was commonly used for both discounting and defining. payoffs. For this reason it was termed the LIBOR market model. However, the same. approach can be used to model risk-free rates determined from overnight indexed swaps..  

# The Model  

Define $t_{0}=0$ and let $t_{1},t_{2},\ldots$ be the reset times for caps that trade in the market today. In the United States, the most popular caps have quarterly resets, so that it is approximately true that $t_{1}=0.25,t_{2}=0.5,t_{3}=0.75$ , and so on. Define $\delta_{k}=t_{k+1}-t_{k}$ and  

$F_{k}(t)$ : Forward rate for the period between times $t_{k}$ and $t_{k+1}$ as seen at time $t(<t_{k})$ expressed with a compounding period of $\delta_{k}$ and an actual/actual day count   
$m(t)$ : Index for the next reset date at time $t$ ; this means that $m(t)$ is the smallest integer such that $t\leq t_{m(t)}$   
$\zeta_{k}(t)$ : Volatility of $F_{k}(t)$ at time $t$  

Initially, we will assume that there is only one factor.  

As shown in Section 28.4, in a world that is defined by the numeraire $P(t,t_{k+1}),F_{k}(t)$ a martingale and follows the process.  

$$
d F_{k}(t)=\zeta_{k}(t)F_{k}(t){}d z
$$  

where $d z$ is a Wiener process.  

The process for $P(t,t_{k})$ has the form  

$$
{\frac{d P(t,t_{k})}{P(t,t_{k})}}=\cdot\cdot\cdot\cdot+\nu_{k}(t)d z
$$  

where $\nu_{k}(t)$ is negative because bond prices and interest rates are negatively related.  

In practice, it is often most convenient to value interest rate derivatives by working in a world that is always defined by the numeraire equal to a bond maturing at the next reset date. We refer to this as a rolling risk-neutral world because the numeraire changes as we roll forward. In this world we can discount from time $t_{k+1}$ to time $t_{k}$ using the zero rate observed at time $t_{k}$ for a maturity $t_{k+1}$ . We do not have to worry about what happens to interest rates between times $t_{k}$ and $t_{k+1}$  

At time $t$ the rolling risk-neutral world is a world defined by the numeraire $P(t,t_{m(t)})$ Equation (33.7) gives the process followed by. $F_{k}(t)$ in a world defined by the numeraire $P(t,t_{k+1})$ From Section 28.8, it follows that the process followed by $F_{k}(t)$ in the rolling risk-neutral world is  

$$
d F_{k}(t)=\zeta_{k}(t)[\nu_{m(t)}(t)-\nu_{k+1}(t)]F_{k}(t){}d t+\zeta_{k}(t)F_{k}(t){}d z
$$  

The relationship between forward rates and bond prices is  

$$
\frac{P(t,t_{i})}{P(t,t_{i+1})}=1+\delta_{i}F_{i}(t)
$$  

or  

$$
\ln P(t,t_{i})-\ln P(t,t_{i+1})=\ln[1+\delta_{i}F_{i}(t)]
$$  

Ito's lemma can be used to calculate the process followed by both the left-hand side and the right-hand side of this equation. Equating the coefficients of. $d z$ gives6  

$$
\nu_{i}(t)-\nu_{i+1}(t)=\frac{\delta_{i}F_{i}(t)\zeta_{i}(t)}{1+\delta_{i}F_{i}(t)}
$$  

so that from equation (33.8) the process followed by $F_{k}(t)$ in the rolling risk-neutral. world is  

$$
\frac{d F_{k}(t)}{F_{k}(t)}=\sum_{i=m(t)}^{k}\frac{\delta_{i}F_{i}(t)\zeta_{i}(t)\zeta_{k}(t)}{1+\delta_{i}F_{i}(t)}d t+\zeta_{k}(t)d z
$$  

The HJM result in equation (33.4) is the limiting case of this as the $\delta_{i}$ tend to zero (see Problem 33.7).  

# Forward Rate Volatilities  

The BGM model can be simplified by assuming that. $\zeta_{k}(t)$ is a function only of the number of whole accrual periods between the next reset date and time $t_{k}$ . Define $\Lambda_{i}$ as the value of. $\zeta_{k}(t)$ when there are. $i$ such accrual periods. This means that. $\zeta_{k}(t)=\Lambda_{k-m(t)}$ is a step function.  

The $\Lambda_{i}$ are related to the volatilities used to price caplets in Black's model. They can be thought of as forward values of those volatilities.' Suppose that $\sigma_{k}$ is the Black volatility for the caplet that corresponds to the period between times $t_{k}$ and $t_{k+1}$ and that the rate for this period is determined at time $t_{k}$ Equating variances, we must have  

$$
\sigma_{k}^{2}t_{k}=\sum_{i=1}^{k}\Lambda_{k-i}^{2}\delta_{i-1}
$$  

This equation can be used to obtain the $\Lambda$ 's iteratively.8  

# Example 33.1  

Assume that the $\delta_{i}$ are all equal and the Black caplet spot volatilities for the first three caplets are $24\%$ $22\%$ , and $20\%$ . This means that $\Lambda_{0}=24\%$ . Since  

$$
\Lambda_{0}^{2}+\Lambda_{1}^{2}=2\times0.22^{2}
$$  

$\Lambda_{1}$ is $19.80\%$ . Also, since  

$$
\Lambda_{0}^{2}+\Lambda_{1}^{2}+\Lambda_{2}^{2}=3\times0.20^{2}
$$  

$\Lambda_{2}$ is $15.23\%$  

# Example 33.2  

Consider the data in Table 33.1 on caplet volatilities $\sigma_{k}$ . These exhibit a hump. The $\Lambda$ s are shown in the second row. Notice that the hump in the $\Lambda$ 's is more pronounced than the hump in the $\sigma$ 's.  

Table 33.1 Volatility data; accrual period $=1$ year.   


<html><body><table><tr><td>Year, k:</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>0k (%):</td><td>15.50</td><td>18.25</td><td>17.91</td><td>17.74</td><td>17.27</td><td>16.79</td><td>16.30</td><td>16.01</td><td>15.76</td><td>15.54</td></tr><tr><td>Ak-1 (%):</td><td>15.50</td><td>20.64</td><td>17.21</td><td>17.22</td><td>15.25</td><td>14.15</td><td>12.98</td><td>13.81</td><td>13.60</td><td>13.40</td></tr></table></body></html>  

# Implementation of the Model  

The BGM model can be implemented using Monte Carlo simulation. Expressed in terms of the $\Lambda_{i}$ s, equation (33.10) is  

$$
\frac{d F_{k}(t)}{F_{k}(t)}=\sum_{i=m(t)}^{k}\frac{\delta_{i}F_{i}(t)\Lambda_{i-m(t)}\Lambda_{k-m(t)}}{1+\delta_{i}F_{i}(t)}d t+\Lambda_{k-m(t)}d z
$$  

so that from Ito's lemma  

$$
d\ln F_{k}(t)=\bigg[\sum_{i=m(t)}^{k}\frac{\delta_{i}F_{i}(t)\Lambda_{i-m(t)}\Lambda_{k-m(t)}}{1+\delta_{i}F_{i}(t)}-\frac{\big(\Lambda_{k-m(t)}\big)^{2}}{2}\bigg]d t+\Lambda_{k-m(t)}d z
$$  

If, as an approximation, we assume in the calculation of the drift of $\ln F_{k}(t)$ that $F_{i}(t)=F_{i}(t_{j})$ for $t_{j}<t<t_{j+1}$ , then  

$$
F_{k}(t_{j+1})=F_{k}(t_{j})\mathrm{exp}\Bigg[\Big(\sum_{i=j+1}^{k}{\frac{\delta_{i}F_{i}(t_{j})\Lambda_{i-j-1}\Lambda_{k-j-1}}{1+\delta_{i}F_{i}(t_{j})}}-{\frac{\Lambda_{k-j-1}^{2}}{2}}\Big)\delta_{j}+\Lambda_{k-j-1}\epsilon\sqrt{\delta_{j}}\Bigg]
$$  

where $\epsilon$ is a random sample from a normal distribution with mean equal to zero and. standard deviation equal to one. In the Monte Carlo simulation, this equation is used to calculate forward rates at time $t_{1}$ from those at time zero; it is then used to calculate forward rates at time $t_{2}$ from those at time $t_{1}$ ; and so on.  

# Extension to Several Factors  

The BGM model can be extended to incorporate several independent factors. Suppose that there are $p$ factors and $\zeta_{k,q}$ is the component of the volatility of $F_{k}(t)$ attributable to the $q$ th factor. Equation (33.10) becomes (see Problem 33.11)  

$$
\frac{d F_{k}(t)}{F_{k}(t)}=\sum_{i=m(t)}^{k}\frac{\delta_{i}F_{i}(t)\sum_{q=1}^{p}\zeta_{i,q}(t)\zeta_{k,q}(t)}{1+\delta_{i}F_{i}(t)}d t+\sum_{q=1}^{p}\zeta_{k,q}(t)d z_{q}
$$  

Define $\lambda_{i,q}$ as the $q$ th component of the volatility when there are. $i$ accrual periods between the next reset date and the maturity of the forward contract. Equation (33.14)  

then becomes  

$$
\begin{array}{r l}&{\mathbf{\Phi}_{k_{k}}(t_{j+1})=F_{k}(t_{j})}\ &{\times\exp\biggl[\biggl(\underset{i=j+1}{\overset{k}{\sum}}\frac{\delta_{i}F_{i}(t_{j})\sum_{q=1}^{p}\lambda_{i-j-1,q}\lambda_{k-j-1,q}}{1+\delta_{i}F_{i}(t_{j})}-\frac{\sum_{q=1}^{p}\lambda_{k-j-1,q}^{2}}{2}\biggr)\delta_{j}+\underset{q=1}{\overset{p}{\sum}}\lambda_{k-j-1,q}\epsilon_{q}\sqrt{\delta_{j}}\biggr]}\end{array}
$$  

where the $\epsilon_{q}$ are random samples from a normal distribution with mean equal to zero and standard deviation equal to one.  

The approximation that the drift of a forward rate remains constant within each accrual period allows us to jump from one reset date to the next in the simulation. This is convenient because as already mentioned the rolling risk-neutral world allows us to discount from one reset date to the next. Suppose that we wish to simulate a zero curve for. $N$ accrual periods. On each trial we start with the forward rates at time zero. These are $F_{0}(0),F_{1}(0),\ldots,F_{N-1}(0)$ and are calculated from the initial zero curve. Equation (33.16) is used to calculate $F_{1}(t_{1}),F_{2}(t_{1}),\ldots,F_{N-1}(t_{1})$ . Equation (33.16) is then used again to calculate $F_{2}(t_{2}),F_{3}(t_{2}),\ldots,F_{N-1}(t_{2})$ , and so on, until. $F_{N-1}\big(t_{N-1}\big)$ is obtained. Note that as we move through time the zero curve gets shorter and shorter. For example, suppose each accrual period is 3 months and $N=40$ . We start with a. 10-year zero curve. At the 6-year point (at time $t_{24}$ ), the simulation gives us information on a 4-year zero curve.  

The drift approximation that we have used (i.e., $F_{i}(t)=F_{i}(t_{j})$ for $t_{j}<t<t_{j+1,}$ ) can be tested by valuing caplets using equation (33.16) and comparing the prices to those given by Black's model. The value of $F_{k}(t_{k})$ is the realized rate for the time period between $t_{k}$ and $t_{k+1}$ and enables the caplet payoff at time $t_{k+1}$ to be calculated. This. payoff is discounted back to time zero, one accrual period at a time. The caplet value is. the average of the discounted payoffs. The results of this type of analysis show that the cap values from Monte Carlo simulation are not significantly different from those given by Black's model. This is true even when the accrual periods are 1 year in length and a. very large number of trials is used.' This suggests that the drift approximation is innocuous in most situations.  

# Ratchet Caps, Sticky Caps, and Flexi Caps  

The BGM model can be used to value some types of nonstandard caps. Consider. ratchet caps and sticky caps. These incorporate rules for determining how the cap rate for each caplet is set. In a ratchet cap it equals the rate at the previous reset date plus a. spread. In a sticky cap it equals the previous capped rate plus a spread. Suppose that the cap rate at time $t_{j}$ is $K_{j},$ the rate at time $t_{j}$ is $R_{j},$ and the spread is $s$ . In a ratchet cap, $K_{j+1}=R_{j}+s.$ In a sticky cap, $K_{j+1}=\operatorname*{min}(R_{j},K_{j})+s$  

Tables 33.2 and 33.3 provide valuations of a ratchet cap and sticky cap using the BGM model with one, two, and three factors. The principal is. $\$100$ . The term structure (for both discounting and determining payoffs) is assumed to be flat at $5\%$ per annum continuously compounded, or $5.127\%$ annually compounded, and the caplet volatilities.  

Table 33.2 Valuation of ratchet caplets.   


<html><body><table><tr><td>Capletstart time (years)</td><td>One factor</td><td>Two factors</td><td>Three factors</td></tr><tr><td>1</td><td>0.196</td><td>0.194</td><td>0.195</td></tr><tr><td>2</td><td>0.207</td><td>0.207</td><td>0.209</td></tr><tr><td>3</td><td>0.201</td><td>0.205</td><td>0.210</td></tr><tr><td>4</td><td>0.194</td><td>0.198</td><td>0.205</td></tr><tr><td>5</td><td>0.187</td><td>0.193</td><td>0.201</td></tr><tr><td>6</td><td>0.180</td><td>0.189</td><td>0.193</td></tr><tr><td>7</td><td>0.172</td><td>0.180</td><td>0.188</td></tr><tr><td>8</td><td>0.167</td><td>0.174</td><td>0.182</td></tr><tr><td>9</td><td>0.160</td><td>0.168</td><td>0.175</td></tr><tr><td>10</td><td>0.153</td><td>0.162</td><td>0.169</td></tr></table></body></html>  

are as in Table 33.1. The interest rate is reset annually. The spread is 25 basis points. applied to the annually compounded rate. Tables 33.4 and 33.5 show how the volatility. was split into components when two- and three-factor models were used. The results are based on 100,o00 Monte Carlo simulations incorporating the antithetic variable technique described in Section 21.7. The standard error of each price is about 0.001..  

A third type of nonstandard cap is a flexi cap. This is like a regular cap except that there is a limit on the total number of caplets that can be exercised. Consider an annualpay flexi cap when the principal is. $\$100$ , the term structure is flat at $5\%$ , and the cap volatilities are as in Tables 33.1, 33.4, and 33.5. Suppose that all in-the-money caplets are exercised up to a maximum of five. With one, two, and three factors, the BGM model gives the price of the instrument as 3.43, 3.58, and 3.61, respectively (see Problem 33.14 for other types of flexi caps)..  

Table 33.3 Valuation of sticky caplets.   


<html><body><table><tr><td>Capletstart time (years)</td><td>One factor</td><td>Two factors</td><td>Three factors</td></tr><tr><td>1</td><td>0.196</td><td>0.194</td><td>0.195</td></tr><tr><td>2</td><td>0.336</td><td>0.334</td><td>0.336</td></tr><tr><td>3</td><td>0.412</td><td>0.413</td><td>0.418</td></tr><tr><td>4</td><td>0.458</td><td>0.462</td><td>0.472</td></tr><tr><td>5</td><td>0.484</td><td>0.492</td><td>0.506</td></tr><tr><td>6</td><td>0.498</td><td>0.512</td><td>0.524</td></tr><tr><td>7</td><td>0.502</td><td>0.520</td><td>0.533</td></tr><tr><td>8</td><td>0.501</td><td>0.523</td><td>0.537</td></tr><tr><td>9</td><td>0.497</td><td>0.523</td><td>0.537</td></tr><tr><td>10</td><td>0.488</td><td>0.519</td><td>0.534</td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>  

Table 33.4 Volatility components in two-factor model.   


<html><body><table><tr><td>Year, k:</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>入k-1,1 (% ):</td><td>14.10</td><td>19.52</td><td>16.78</td><td>17.11</td><td>15.25</td><td>14.06</td><td>12.65</td><td>13.06</td><td>12.36</td><td>11.63</td></tr><tr><td>入k-1,2 (% ):</td><td></td><td></td><td>-6.45 -6.70 -3.84 -1.96</td><td></td><td>0.00</td><td>1.61</td><td>2.89</td><td>4.48</td><td>5.65</td><td>6.65</td></tr><tr><td>Total</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>volatility (%): 15.50</td><td></td><td>20.64</td><td>17.21</td><td>17.22</td><td>15.25</td><td>14.15</td><td>12.98</td><td>13.81</td><td>13.60</td><td>13.40</td></tr></table></body></html>  

The pricing of a plain vanilla cap depends only on the total volatility and is independent of the number of factors. This is because the price of a plain vanilla caplet depends on the behavior of only one forward rate. The prices of caplets in the nonstandard instruments we have looked at are different in that they depend on the joint probability distribution of several different forward rates. As a result they do depend on the number of factors.  

# Valuing European Swap Options  

There is an analytic approximation for valuing European swap options in the BGM model.10 Assume that the swap cash flows are based on risk-free rates (i.e., the rates used. for discounting). Let $T_{0}$ be the maturity of the swap option and assume that the payment. dates for the swap are $T_{1}$ $T_{2}$ ...,. $T_{N}$ Define $\tau_{i}=T_{i+1}-T_{i}.$ From equation (28.23), the swap rate at time $t$ is given by.  

$$
s(t)=\frac{P(t,T_{0})-P(t,T_{N})}{\sum_{i=0}^{N-1}\tau_{i}P(t,T_{i+1})}
$$  

It is also true that  

$$
\frac{P(t,T_{i})}{P(t,T_{0})}=\prod_{j=0}^{i-1}\frac{1}{1+\tau_{j}G_{j}(t)}
$$  

Table 33.5  Volatility components in a three-factor model.   


<html><body><table><tr><td>Year, k:</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>入k-1,1 (%):</td><td>13.65</td><td>19.28</td><td>16.72</td><td>16.98</td><td>14.85</td><td>13.95</td><td>12.61</td><td>12.90</td><td>11.97</td><td>10.97</td></tr><tr><td>入k-1,2 (%):</td><td></td><td>-6.62 -7.02</td><td>2-4.06 -2.06</td><td></td><td>0.00</td><td>1.69</td><td>3.06</td><td>4.70</td><td>5.81</td><td>6.66</td></tr><tr><td>入k-1, 3 (% ):</td><td>3.19</td><td>2.25</td><td></td><td></td><td>0.00 -1.98 -3.47 -1.63</td><td></td><td>0.00</td><td>1.51</td><td>2.80</td><td>3.84</td></tr><tr><td>Total</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>volatility (%): 15.50</td><td></td><td>20.64</td><td>17.21</td><td>17.22</td><td>15.25</td><td>14.15 12.98</td><td></td><td>13.81</td><td>13.60</td><td>13.40</td></tr></table></body></html>

10 See J. C. Hull and A. White, "Forward Rate Volatilities, Swap Rate Volatilities and the Implementation of the LIBOR Market Model," Journal of Fixed Income, 10, 2 (September 2000): 46-62. Other analytic approximations have been suggested by A. Brace, D. Gatarek, and M. Musiela "The Market Model of Interest Rate Dynamics," Mathematical Finance, 7, 2 (1997): 127-55 and L. B. G. Andersen and J. Andreasen, "Volatility Skews and Extensions of the LIBOR Market Model," Applied Mathematical Finance, 7, 1 (March 2000), 1-32.  

for $1\leq i\leq N$ , where $G_{j}(t)$ is the forward rate at time. $t$ for the period between $T_{j}$ and $T_{j+1}$ . These two equations together define a relationship between $s(t)$ and the $G_{j}(t)$ Applying Ito's lemma (see Problem 33.12), the variance $V(t)$ of the swap rate $s(t)$ is given by  

$$
V(t)=\sum_{q=1}^{p}\biggl[\sum_{k=0}^{N-1}\frac{\tau_{k}\beta_{k,q}(t)G_{k}(t)\gamma_{k}(t)}{1+\tau_{k}G_{k}(t)}\biggr]^{2}
$$  

where  

$$
\gamma_{k}(t)=\frac{\prod_{j=0}^{N-1}[1+\tau_{j}G_{j}(t)]}{\prod_{j=0}^{N-1}[1+\tau_{j}G_{j}(t)]-1}-\frac{\sum_{i=0}^{k-1}\tau_{i}\prod_{j=i+1}^{N-1}[1+\tau_{j}G_{j}(t)]}{\sum_{i=0}^{N-1}\tau_{i}\prod_{j=i+1}^{N}[1+\tau_{j}G_{j}(t)]}
$$  

and $\beta_{j,q}(t)$ is the $q$ th component of the volatility of $G_{j}(t)$ . We approximate $V(t)$ by setting $G_{j}(t)=G_{j}(0)$ for all $j$ and $t.$ The swap volatility that is substituted into the standard market model for valuing a swaption is then  

$$
{\sqrt{\frac{1}{T_{0}}}}{\int_{t=0}^{T_{0}}}V(t)d t
$$  

or  

$$
\sqrt{\frac{1}{T_{0}}}{\int_{t=0}^{T_{0}}\sum_{q=1}^{p}}\Biggl[\sum_{k=0}^{N-1}\frac{\tau_{k}\beta_{k,q}(t)G_{k}(0)\gamma_{k}(0)}{1+\tau_{k}G_{k}(0)}\Biggr]^{2}d t
$$  

In the situation where the length of the accrual period for the swap underlying the swaption is the same as the length of the accrual period for a cap, $\beta_{k,q}(t)$ is the $q$ th component of volatility of a cap forward rate when the time to maturity is $T_{k}-t.$ This can be looked up in a table such as Table 33.5.  

This valuation result for European swap options can be extended to the situation where each swap accrual period includes $M$ subperiods that could be accrual periods in a typical cap. Define $\tau_{j,m}$ as the length of the mth subperiod in the. $j$ th accrual period so that  

$$
\tau_{j}=\sum_{m=1}^{M}\tau_{j,m}
$$  

Define $G_{j,m}(t)$ as the forward rate observed at time $t$ for the $\tau_{j,m}$ accrual period. Because  

$$
1+\tau_{j}G_{j}(t)=\prod_{m=1}^{M}[1+\tau_{j,m}G_{j,m}(t)]
$$  

the analysis leading to equation (33.18) can be modified so that the volatility of $s(t)$ is obtained in terms of the volatilities of the $G_{j,m}(t)$ rather than the volatilities of the $G_{j}(t)$ The swap volatility to be substituted into the standard market model for valuing a swap option proves to be (see Problem 33.13)  

$$
\sqrt{\frac{1}{T_{0}}\int_{t=0}^{T_{0}}\sum_{q=1}^{p}\biggl[\sum_{k=n}^{N-1}\sum_{m=1}^{M}\frac{\tau_{k,m}\beta_{k,m,q}(t)G_{k,m}(0)\gamma_{k}(0)}{1+\tau_{k,m}G_{k,m}(0)}\biggr]^{2}d t}
$$  

Here $\beta_{j,m,q}(t)$ is the $q$ th component of the volatility of $G_{j,m}(t)$ . It is the $q$ th component of the volatility of a cap forward rate when the time to maturity is from $t$ to the beginning of the mth subperiod in the $(T_{j},T_{j+1})$ swap accrual period.  

The expressions (33.18) and (33.19) for the swap volatility do involve the approximations that $G_{j}(t)=G_{j}(0)$ and $G_{j,m}(t)=G_{j,m}(0)$ Hull and White compared the prices of. European swap options calculated using (33.18) and (33.19) with the prices calculated. from a Monte Carlo simulation and found the two to be very close. Once the BGM model has been calibrated, (33.18) and (33.19) therefore provide a quick way of valuing. European swap options. Analysts can determine whether European swap options are. overpriced or underpriced relative to caps. As we shall see shortly, they can also use the results to calibrate the model to the market prices of swap options..  

# Calibrating the Model  

The variable $\Lambda_{j}$ is the volatility at time $t$ of the forward rate. $F_{j}$ for the period between $t_{k}$ and $t_{k+1}$ when there are. $j$ whole accrual periods between $t$ and $t_{k}$ . To calibrate the BGM model, it is necessary to determine the $\Lambda_{j}$ and how they are split into $\lambda_{j,q}$ The $\Lambda$ 's are usually determined from current market data, whereas the split into $\lambda$ s is determined. from historical data.  

Consider first the determination of the $\lambda$ 's from the $\Lambda$ 's. A principal components analysis (see Section 22.9) on forward rate data can be used. The model is  

$$
\Delta F_{j}=\sum_{q=1}^{M}\alpha_{j,q}x_{q}
$$  

where $M$ is the total number of factors (which equals the number of different forward rates), $\Delta F_{j}$ is the change in the jth forward rate $F_{j},\alpha_{j,q}$ is the factor loading for the jth forward rate and the qth factor, $x_{q}$ is the factor score for the $q$ th factor. Define $s_{q}$ as the standard deviation of the $q$ th factor score. If the number of factors used in the BGM model, $p$ , is equal to the total number of factors, $M$ , it is correct to set  

$$
\lambda_{j,q}=\alpha_{j,q}s_{q}
$$  

for $1\leq j,q\leq M.$ When, as is usual, $p<M$ the $\lambda_{j,q}$ must be scaled so that  

$$
\Lambda_{j}=\sqrt{\sum_{q=1}^{p}\lambda_{j,q}^{2}}
$$  

This involves setting  

$$
\lambda_{j,q}=\frac{\Lambda_{j}s_{q}\alpha_{j,q}}{\sqrt{\sum_{q=1}^{p}s_{q}^{2}\alpha_{j,q}^{2}}}
$$  

Consider next the estimation of the $\Lambda$ 's. Equation (33.11) provides one way that they. can be theoretically determined so that they are consistent with caplet prices. In. practice, this is not usually used because it often leads to wild swings in the $\Lambda$ 's and sometimes there is no set of. $\Lambda$ 's exactly consistent with cap quotes. A commonly used calibration procedure is similar to that described in Section 32.6. Suppose that. $U_{i}$ is the market price of the ith calibrating instrument (typically a cap or European swaption) and $V_{i}$ is the model price. The $\Lambda$ s are chosen to minimize  

$$
\sum_{i}(U_{i}-V_{i})^{2}+P
$$  

where $P$ is a penalty function chosen to ensure that the $\Lambda$ 's are "well behaved.".   
Similarly to Section 32.6,. $P$ might have the form.  

$$
P=\sum_{i}w_{1,i}(\Lambda_{i+1}-\Lambda_{i})^{2}+\sum_{i}w_{2,i}(\Lambda_{i+1}+\Lambda_{i-1}-2\Lambda_{i})^{2}
$$  

When the calibrating instrument is a European swaption, formulas (33.18) and (33.19) make the minimization feasible using the Levenberg-Marquardt procedure. Equation (33.20) is used to determine the $\lambda$ 's from the $\Lambda$ 'S.  

# Volatility Skews  

Brokers provide quotes on caps that are not at the money as well as on caps that are at the money. In some markets a volatility skew is observed, that is, the quoted (Black) volatility for a cap or a floor is a declining function of the strike price. This can be handled using the CEV model. (See Section 27.1 for the application of the CEV model to equities.) The model is.  

$$
d F_{i}(t)=\cdots+\sum_{q=1}^{p}\zeta_{i,q}(t)F_{i}(t)^{\alpha}d z_{q}
$$  

where $\alpha$ is a constant ( $0<\alpha<1$ ). It turns out that this model can be handled very. similarly to the lognormal model. Caps and floors can be valued analytically using the cumulative noncentral $\chi^{2}$ distribution. There are similar analytic approximations to those given above for the prices of European swap options.11  

# Bermudan Swap Options  

A popular interest rate derivative is a Bermudan swap option. This is a swap option that can be exercised on some or all of the payment dates of the underlying swap. Bermudan swap options are difficult to value using the BGM model because the BGM model relies on Monte Carlo simulation and it is difficult to evaluate early exercise decisions when Monte Carlo simulation is used. Fortunately, the procedures described in Section 27.8 can be used. Longstaff and Schwartz apply the least-squares approach when there are a large number of factors. The value of not exercising on a particular payment date is assumed to be a polynomial function of the values of the factors.12 Andersen shows that the optimal early exercise boundary approach can be used. He experiments with a number of ways of parameterizing the early exercise boundary and finds that good results are obtained when the early exercise decision is assumed to depend only on the intrinsic value of the option.13 Most traders value Bermudan. options using one of the one-factor no-arbitrage models discussed in Chapter 32. However, the accuracy of one-factor models for pricing Bermudan swap options has. been a controversial issue.14  
