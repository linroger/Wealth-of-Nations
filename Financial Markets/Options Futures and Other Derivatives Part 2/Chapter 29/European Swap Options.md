# 29.3 EUROPEAN SWAP OPTIONS  

Swap options, or swaptions, are options on interest rate swaps and are another popular. type of interest rate option. They give the holder the right to enter into a certain interest rate swap at a certain time in the future. (The holder does not, of course, have to exercise this right.) Many large financial institutions that offer interest rate swap. contracts to their corporate clients are also prepared to sell them swaptions or buy swaptions from them. As shown in Business Snapshot 29.2, a swaption can be viewed as a type of bond option.  

To give an example of how a swaption might be used, consider a company that knows that in 6 months it will enter into a 5-year floating-rate loan agreement and knows that it will wish to swap the floating interest payments for fixed interest payments to convert the loan into a fixed-rate loan (see Chapter 7 for a discussion of how swaps can be used in this way). At a cost, the company could enter into a swaption giving it the right to receive the 6-month floating rate and pay a certain fixed rate of interest, say $3\%$ per annum, for a 5-year period starting in 6 months. If the fixed rate exchanged for floating on a regular 5-year swap in 6 months turns out to be less than $3\%$ per annum, the company will choose not to exercise the swaption and will enter into a swap agreement in the usual way. However, if it turns out to be greater than $3\%$ per annum, the company will choose to exercise the swaption and will obtain a swap at more favorable terms than those available in the market.  

Swaptions, when used in the way just described, provide companies with a guarantee that the fixed rate of interest they will pay on a loan at some future time will not exceed. some level. They are an alternative to forward swaps (sometimes called deferred swaps). Forward swaps involve no up-front cost but have the disadvantage of obligating the company to enter into a swap agreement. With a swaption, the company is able to benefit from favorable interest rate movements while acquiring protection from unfavorable. interest rate movements. The difference between a swaption and a forward swap is analogous to the difference between an option on a foreign currency and a forward contract on the currency.  

# Valuation of European Swaptions  

As explained in Chapter 7, the swap rate for a particular maturity at a particular time is the (mid-market) fixed rate that would be exchanged for the floating rate in a newly issued swap with that maturity. The model usually used to value a European option on a swap assumes that the underlying swap rate at the maturity of the option is lognormal. Consider a swaption where the holder has the right to pay a rate $s_{K}$ and receive the floating rate on a swap that will last. $n$ years starting in $T$ years. We suppose that there are m payments per year under the swap and that the notional principal is $L$  

# Business Snapshot 29.2 Swaptions and Bond Options  

As explained in Chapter 7, an interest rate swap can be regarded as an agreement to exchange a fixed-rate bond for a floating-rate bond. At the start of a swap, the value of the floating-rate bond always equals the principal amount of the swap. A swaption can therefore be regarded as an option to exchange a fixed-rate bond for the principal amount of the swap-that is, a type of bond option.  

If a swaption gives the holder the right to pay fixed and receive floating, it is a put option on the fixed-rate bond with strike price equal to the principal. If a swaption gives the holder the right to pay floating and receive fixed, it is a call option on the fixed-rate bond with a strike price equal to the principal.  

Chapter 7 showed that day count conventions may lead to the fixed payments under a swap being slightly different on each payment date. For now we will ignore the effect of day count conventions and assume that each fixed payment on the swap is the fixed rate times $L/m$ . The impact of day count conventions is considered at the end of this. section.  

Suppose that the swap rate for an $n$ -year swap starting at time $T$ proves to be $s_{T}$ . By comparing the cash flows on a swap where the fixed rate is $s_{T}$ to the cash flows on a swap where the fixed rate is $s_{K}$ , it can be seen that the payoff from the swaption consists of a series of cash flows equal to  

$$
\frac{L}{m}\operatorname*{max}(s_{T}-s_{K},0)
$$  

The cash flows are received $m$ times per year for the $n$ years of the life of the swap. Suppose that the swap payment dates are $T_{1},T_{2},\ldots,T_{m n}$ measured in years from today. (It is approximately true that $T_{i}=T+i/m$ ) Each cash flow is the payoff from a call option on $s_{T}$ with strike price $s_{K}$  

Whereas a cap is a portfolio of options on interest rates, a swaption is a single option. on the swap rate with repeated payoffs. The standard market model gives the value of a swaption where the holder has the right to pay. $s_{K}$ as  

where  

$$
\begin{array}{l}{{\displaystyle\sum_{i=1}^{m n}\frac{L}{m}P(0,T_{i})[s_{F}N(d_{1})-s_{K}N(d_{2})]}}\ {{\displaystyle}}\ {{d_{1}=\frac{\ln(s_{F}/s_{K})+\sigma^{2}T/2}{\sigma\sqrt{T}}}}\ {{d_{2}=\frac{\ln(s_{F}/s_{K})-\sigma^{2}T/2}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}}\end{array}
$$  

$s_{F}$ is the forward swap rate at time zero, and $\sigma$ is the volatility of the forward swap rate (so that $\sigma\sqrt{T}$ is the standard deviation of. $\ln{s_{T}}$  

This is a natural extension of Black's model. The volatility $\sigma$ is multiplied by $\sqrt{T}$ The $\textstyle\sum_{i=1}^{m n}P(0,T_{i})$ term is the discount factor for the mn payoffs. Defininge $A$ as the value of a contract that pays $1/m$ at times $T_{i}\left(1\leq i\leq m n\right)$ , the value of the swaption becomes.  

$$
L A[s_{F}N(d_{1})-s_{K}N(d_{2})]
$$  

where  

$$
A=\frac{1}{m}\sum_{i=1}^{m n}P(0,T_{i})
$$  

If the swaption gives the holder the right to receive a fixed rate of $s_{K}$ instead of paying it, the payoff from the swaption is  

$$
\frac{L}{m}\operatorname*{max}(s_{K}-s_{T},0)
$$  

This is a put option on $s_{T}$ . As before, the payoffs are received at times $T_{i}\left(1\leq i\leq m n\right)$ The standard market model gives the value of the swaption as  

$$
L A[s_{K}N(-d_{2})-s_{F}N(-d_{1})]
$$  

DerivaGem can be used to value swaptions using Black's model. In the Cap_and_. Swap_Options worksheet, select Swap Options as the Underlying Type and Black-. European as the pricing model. Inputs are similar to those for caps. Forward rates are used to determine the forward swap rate. If this forward swap rate is known, the forward rates can be input as flat and equal to the known value..  

# Example 29.4  

Suppose that the risk-free zero curve is flat at $6\%$ per annum with continuous compounding. Consider a swaption that gives the holder the right to pay $6.2\%$ in a 3-year swap starting in 5 years. Payments are made semiannually and the principal is $\$100$ million. The forward swap rate is $6.1\%$ with continuous compounding, which translates as $6.194\%$ with semiannual compounding. The volatility of the forward swap rate is $20\%$ . In this case,  

$$
A={\frac{1}{2}}{\big(}e^{-0.06\times5.5}+e^{-0.06\times6}+e^{-0.06\times6.5}+e^{-0.06\times7}+e^{-0.06\times7.5}+e^{-0.06\times8}{\big)}=2.0035
$$  

Als $0,s_{F}=0.06194,s_{K}=0.062,T=5$ , and $\sigma=0.2$ , so that  

$$
\begin{array}{c}{{d_{1}=\displaystyle\frac{\ln(0.06194/0.062)+0.2^{2}\times5/2}{0.2\sqrt{5}}=0.2214}}\ {{d_{2}=d_{1}-0.2\sqrt{5}=-0.2258}}\end{array}
$$  

From equation (29.10), the value of the swaption (in $\$1$ millions) is  

$$
100\times2.0035\times[0.06194\times N(0.2214)-0.062\times N(-0.2258)]=2.19
$$  

(This is in agreement with the price given by DerivaGem.)  

# Theoretical Justification for the Swaption Model  

The extension of Black's model used for swaptions can be shown to be internally consistent by considering a world defined by a numeraire equal to the annuity. $A$ . The analysis in Section 28.4 shows that:.  

1. The current value of any security is the current value of the annuity multiplied by the expected value of  

in this world (see equation (28.25))  

2. The expected value of the swap rate at time $T$ in this world equals the forward swap rate (see equation (28.24)).  

The first result shows that the value of the swaption is  

$$
L A E_{A}[\operatorname*{max}(s_{T}-s_{K},0)]
$$  

From equation (15A.1), this is  

where  

$$
\begin{array}{c}{{L A[E_{A}(s_{T})N(d_{1})-s_{K}N(d_{2})]}}\ {{{}}}\ {{d_{1}=\displaystyle\frac{\ln[E_{A}(s_{T})/s_{K}]+\sigma^{2}T/2}{\sigma\sqrt{T}}}}\ {{d_{2}=\displaystyle\frac{\ln[E_{A}(s_{T})/s_{K}]-\sigma^{2}T/2}{\sigma\sqrt{T}}=d_{1}-\sigma\sqrt{T}}}\end{array}
$$  

The second result shows that $E_{A}(s_{T})$ equals $s_{F}$ . The results lead to the swap option pricing. formula in equation (29.10). They show that interest rates can be treated as constant for the purposes of discounting provided that the expected swap rate is set equal to the forward swap rate. Note that the results in Section 28.4 show that this theoretical result is valid when the floating rate in the underlying swap is not the same as the risk-free rate.  

# The Impact of Day Count Conventions  

The above formulas can be made more precise by considering day count conventions.. The fixed rate for the swap underlying the swap option is expressed with a day count. convention such as actual/365 or $30/360$ . Suppose that $T_{0}=T$ and that, for the applicable day count convention, the accrual fraction corresponding to the time period between $T_{i-1}$ and $T_{i}$ is $a_{i}$ (For example, if $T_{i-1}$ corresponds to March 1 and $T_{i}$ corresponds to September 1 and the day count is actual/365, $a_{i}=184/365=0.5041.)$ The formulas that have been presented are then correct with the annuity factor $A$ being defined as  

$$
A=\sum_{i=1}^{m n}a_{i}P(0,T_{i})
$$  

# Negative Rates  

The shifted lognormal model can be used to handle the possibility of negative interest rates when swaptions are valued. Equations (29.10) and (29.11) are used with with $s_{F}$ replaced by $s_{F}+\alpha$ and $s_{K}$ replaced by $s_{K}+\alpha$ . The shift, $\alpha$ , in practice often depends on both the life of the option and the life of the underlying swap. The Bachelier normal model can also be used. When the holder has the right to pay $s_{K}$ equation (29.10) becomes  

$$
L A[(s_{F}-s_{K})N(d)+\sigma^{*}\sqrt{T}N^{\prime}(d)]
$$  

and when the holder has the right to receive $s_{K}$ , equation (29.11) becomes  

$$
L A[(s_{K}-s_{F})N(-d)+\sigma^{*}\sqrt{T}N^{\prime}(d)]
$$  

where $\sigma^{*}\sqrt[]{T}$ is the standard deviation of $s_{T}$ and  

$$
d={\frac{s_{F}-s_{K}}{\sigma^{*}{\sqrt{T}}}}
$$  
