# 25.2 VALUATION OF CREDIT DEFAULT SWAPS  

The CDS spread for a particular reference entity can be calculated from default probability estimates. We will illustrate how this is done for a 5-year CDS..  

Suppose that the hazard rate of the reference entity is. $2\%$ per annum for the whole of. the 5-year life of the CDS. Table 25.1 shows survival probabilities and unconditional probabilities of default. From equation (24.1), the probability of survival to time $t$ is $e^{-0.02t}$ The probability of default during a year is the probability of survival to the beginning of the year minus the probability of survival to the end of the year. For example, the probability of survival to time 2 years is $e^{-0.02\times2}=0.9608$ and the. probability of survival to time 3 years is $e^{-0.02\times3}=0.9418$ The probability of default during the third year is $0.9608-0.9418=0.0190.$  

Table 25.1 Unconditional default probabilities and survival probabilities.   


<html><body><table><tr><td>Year</td><td>Probabilityof survivingtoyearend</td><td>Probability of defaultduringyear</td></tr><tr><td>1</td><td>0.9802</td><td>0.0198</td></tr><tr><td>2</td><td>0.9608</td><td>0.0194</td></tr><tr><td>3</td><td>0.9418</td><td>0.0190</td></tr><tr><td>4</td><td>0.9231</td><td>0.0186</td></tr><tr><td>5</td><td>0.9048</td><td>0.0183</td></tr></table></body></html>  

We will assume that defaults always happen halfway through a year and that payments on the credit default swap are made once a year, at the end of each year. We also assume that the risk-free interest rate is. $5\%$ per annum with continuous compounding and the. recovery rate is $40\%$ . There are three parts to the calculation. These are shown in. Tables 25.2, 25.3, and 25.4.  

Table 25.2 shows the calculation of the present value of the expected payments made on the CDS assuming that payments are made at the rate of $s$ per year and the notional principal is $\$1$ . For example, there is a 0.9418 probability that the third payment of. $s$ is made. The expected payment is therefore 0.9418s and its present value is $0.9418s e^{-0.05\times3}\stackrel{\cdot}{=}0.8106\stackrel{\cdot}{s}$ The total present value of the expected payments is $4.0728s$  

Table 25.3 shows the calculation of the present value of the expected payoff assuming a notional principal of $\$1$ . As mentioned earlier, we are assuming that defaults always happen halfway through a year. For example, there is a 0.0190 probability of a payoff halfway through the third year. Given that the recovery rate is $40\%$ , the expected payoff at this time is $0.0190\times0.6\times1=0.0114$ The present value of the expected payoff is $0.0114e^{-0.05\times2.5}=0.0101$ The total present value of the expected payoffs is $\$0.0506$  

Table 25.2 Calculation of the present value of expected payments. Payment $=s$ per annum.   


<html><body><table><tr><td>Time (years)</td><td>Probability ofsurvival</td><td>Expected payment</td><td>Discount factor</td><td>PV ofexpected payment</td></tr><tr><td>1</td><td>0.9802</td><td>0.9802s</td><td>0.9512</td><td>0.9324s</td></tr><tr><td>2</td><td>0.9608</td><td>0.9608s</td><td>0.9048</td><td>0.8694s</td></tr><tr><td>3</td><td>0.9418</td><td>0.9418s</td><td>0.8607</td><td>0.8106s</td></tr><tr><td>4</td><td>0.9231</td><td>0.9231s</td><td>0.8187</td><td>0.7558s</td></tr><tr><td>5</td><td>0.9048</td><td>0.9048s</td><td>0.7788</td><td>0.7047s</td></tr><tr><td>Total</td><td></td><td></td><td></td><td>4.0728s</td></tr></table></body></html>  

Table 25.3 Calculation of the present value of expected payoff. Notional principal $ \mathit{\Omega}=\$1$   


<html><body><table><tr><td>Time (years)</td><td>Probability ofdefault</td><td>Recovery rate</td><td>Expected payoff ($)</td><td>Discount factor</td><td>PVofexpected payoff ($)</td></tr><tr><td>0.5</td><td>0.0198</td><td>0.4</td><td>0.0119</td><td>0.9753</td><td>0.0116</td></tr><tr><td>1.5</td><td>0.0194</td><td>0.4</td><td>0.0116</td><td>0.9277</td><td>0.0108</td></tr><tr><td>2.5</td><td>0.0190</td><td>0.4</td><td>0.0114</td><td>0.8825</td><td>0.0101</td></tr><tr><td>3.5</td><td>0.0186</td><td>0.4</td><td>0.0112</td><td>0.8395</td><td>0.0094</td></tr><tr><td>4.5</td><td>0.0183</td><td>0.4</td><td>0.0110</td><td>0.7985</td><td>0.0088</td></tr><tr><td>Total</td><td></td><td></td><td></td><td></td><td>0.0506</td></tr></table></body></html>  

As a final step, Table 25.4 considers the accrual payment made in the event of a default. For example, there is a 0.0190 probability that there will be a final accrual payment halfway through the third year. The accrual payment is. $0.5s$ . The expected accrual payment at this time is therefore $0.0190\times0.5s=0.0095s$ Its present value is $\dot{0}.0095s e^{-0.05\times2.5}=0.0084s$ The total present value of the expected accrual payments is 0.0422s.  

From Tables 25.2 and 25.4, the present value of the expected payments is  

$$
4.0728s+0.0422s=4.1150s
$$  

From Table 25.3, the present value of the expected payoff is 0.0506. Equating the two gives  

$$
4.1150s=0.0506
$$  

or $s=0.0123$ . The mid-market CDS spread for the 5-year deal we have considered should be 0.0123 times the principal or 123 basis points per year. This result can also be produced using the DerivaGem CDS worksheet..  

The calculations assume that defaults happen only at points midway between payment dates. This simple assumption usually gives good results, but can easily be relaxed so that more default times are considered.  

Table 25.4 Calculation of the present value of accrual payment.   


<html><body><table><tr><td>Time (years)</td><td>Probability ofdefault</td><td>Expected accrualpayment</td><td>Discount factor</td><td>PVofexpected accrualpayment</td></tr><tr><td>0.5</td><td>0.0198</td><td>0.0099s</td><td>0.9753</td><td>0.0097s</td></tr><tr><td>1.5</td><td>0.0194</td><td>0.0097s</td><td>0.9277</td><td>0.0090s</td></tr><tr><td>2.5</td><td>0.0190</td><td>0.0095s</td><td>0.8825</td><td>0.0084s</td></tr><tr><td>3.5</td><td>0.0186</td><td>0.0093s</td><td>0.8395</td><td>0.0078s</td></tr><tr><td>4.5</td><td>0.0183</td><td>0.0091s</td><td>0.7985</td><td>0.0073s</td></tr><tr><td>Total</td><td colspan="3"></td><td>0.0422s</td></tr></table></body></html>  

# Marking to Market a CDS  

A CDS, like most other derivatives, is revalued (i.e., marked to market) daily. It may have a positive or negative value. Suppose, for example the credit default swap in our example had been negotiated some time ago for a spread of 150 basis points, the present value of the payments by the buyer would be $4.1150\times0.0150=0.0617$ and the present value of the payoff would be 0.0506 as above. The value of swap to the seller would therefore be $0.0617\mathrm{~-~}0.0506$ , or 0.0111 times the principal. Similarly the marked-to-market value of the swap to the buyer of protection would be $-0.0111$ times the principal.  

# Estimating Default Probabilities  

The default probabilities used to value a CDS should be risk-neutral default prob-. abilities, not real-world default probabilities (see Section 24.5 for the difference between the two). Risk-neutral default probabilities can be estimated from bond prices as explained in Chapter 24. An alternative is to imply them from CDS quotes. The latter approach is similar to the practice in options markets of implying volatilities from the prices of actively traded options and using them to value other options..  

Suppose we change the example in Tables 25.2, 25.3, and 25.4 so that we do not know. the default probabilities. Instead we know that the mid-market CDS spread for a newly. issued 5-year CDS is 100 basis points per year. We can reverse-engineer our calculations (using Excel in conjunction with Solver) to conclude that the implied hazard rate is $1.63\%$ per year.  

The DerivaGem software can be used to calculate a term structure of hazard rates from a term structure of CDS spreads or vice versa.  

# Binary Credit Default Swaps  

A binary credit default swap is structured similarly to a regular credit default swap. except that the payoff is a fixed dollar amount. Suppose that, in the example we considered in Tables 25.1 to 25.4, the payoff is. $\$1$ instead of. $1-R$ dollars and the. swap spread is $s$ Tables 25.1, 25.2 and 25.4 are the same, but Table 25.3 is replaced by. Table 25.5. The CDS spread for a new binary CDS is given by. $4.1150s=0.0844$ , so that the CDS spread $s$ is 0.0205, or 205 basis points.  

<html><body><table><tr><td colspan="5">Table25.5 Calculation of the present value of expected payoff from a binary credit default swap. Principal = $1.</td></tr><tr><td>Time (years)</td><td>Probability of default</td><td>Expected payoff ($)</td><td>Discount factor</td><td>PVofexpected payoff ($)</td></tr><tr><td>0.5</td><td>0.0198</td><td>0.0198</td><td>0.9753</td><td>0.0193</td></tr><tr><td>1.5</td><td>0.0194</td><td>0.0194</td><td>0.9277</td><td>0.0180</td></tr><tr><td>2.5</td><td>0.0190</td><td>0.0190</td><td>0.8825</td><td>0.0168</td></tr><tr><td>3.5</td><td>0.0186</td><td>0.0186</td><td>0.8395</td><td>0.0157</td></tr><tr><td>4.5</td><td>0.0183</td><td>0.0183</td><td>0.7985</td><td>0.0146</td></tr><tr><td>Total</td><td></td><td></td><td></td><td>0.0844</td></tr></table></body></html>  

# How Important Is the Recovery Rate?  

Whether we use CDS spreads or bond prices to estimate default probabilities we need. an estimate of the recovery rate. However, provided that we use the same recovery rate for (a) estimating risk-neutral default probabilities and (b) valuing a CDS, the value of the CDS (or the estimate of the CDS spread) is not very sensitive to the recovery rate. This is because the implied probabilities of default are approximately proportional to $1/(1-R)$ and the payoffs from a CDS are proportional to. $1-R$  

This argument does not apply to the valuation of binary CDS. Implied probabilities of default are still approximatelyproportionalto $1/(1-R)$ .However,for abinary CDS,the payoffs from the CDS are independent of. $R$ . If we have a CDS spread for both a plain. vanilla CDS and a binary CDS, we can estimate both the recovery rate and the default probability (see Problem 25.25).  
