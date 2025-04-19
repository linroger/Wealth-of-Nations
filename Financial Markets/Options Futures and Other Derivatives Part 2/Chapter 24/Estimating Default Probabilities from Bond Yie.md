---
tags:
  - bond_yield
  - default_probability
  - hazard_rate
  - recovery_rate
  - risk_free_rate
aliases:
  - Default Estimation
  - Yield Spread
key_concepts:
  - Average hazard rate
  - Bond yield spread
  - Matching bond prices
  - Recovery rate
  - Risk-free rate
---

# 24.4  ESTIMATING DEFAULT PROBABILITIES FROM BOND YIELD SPREADS  

Tables such as Table 24.1 provide one way of estimating default probabilities. Another. approach is to look at bond yield spreads. A bond's yield spread is the excess of the promised yield on the bond over the risk-free rate. The usual assumption is that the excess yield is compensation for the possibility of default.3.  

Suppose that the bond yield spread for a $T$ -year bond is $s(T)$ per annum. This means that the average loss rate on the bond between time 0 and time $T$ should be approximately $s(T)$ per annum. Suppose that the average hazard rate during this time is $\overline{{\lambda}}(T)$ Another expression for the average loss rate is $\bar{\lambda}(T)(1-R)$ , where $R$ is the estimated recovery rate. This means that it is approximately true that  

or  

$$
\begin{array}{c}{{\overline{{{\lambda}}}(T)\big(1-R\big)=s(T)}}\ {{{}}}\ {{\overline{{{\lambda}}}(T)=\displaystyle\frac{s(T)}{1-R}}}\end{array}
$$  

The approximation works very well in a wide range of situations.  

# Example 24.1  

Suppose that 1-year, 2-year, and 3-year bonds issued by a corporation yield 150, 180, and 195 basis points more than the risk-free rate, respectively. If the recovery rate is estimated at. $40\%$ , the average hazard rate for year 1 given by equa-. tion (24.2) is $0.0150/(1-0.4)=0.025$ or $2.5\%$ per annum. Similarly, the average hazard rate for years 1 and 2 is. $0.0180/(1-0.4)=0.030$ or $3.0\%$ per annum, and. the average hazard rate for all three years is. $0.0195/(1-0.4)=0.0325$ or $3.25\%$ These results imply that the average hazard rate for the second year is $2\times0.03-1\times0.025=0.035$ or $3.5\%$ and that the average hazard rate for the. third year is. $3\times0.0325-2\times0.03=0.0375$ or $3.75\%$  

# Matching Bond Prices  

For a more precise calculation we can choose hazard rates so that they match bond prices. The approach is similar to the bootstrap method for calculating a zero-coupon. yield curve described in Section 4.7. Suppose that bonds with maturities. $t_{i}$ are used, where $t_{1}<t_{2}<t_{3}\cdots.$ The shortest maturity bond is used to calculate the hazard rate. out to time $t_{1}$ . The next shortest maturity bond is used to calculate the hazard rate. between times $t_{1}$ and $t_{2}$ , and so on.  

# Example 24.2  

Suppose that the risk-free rate is. $5\%$ per annum (continuously compounded) for all maturities and 1-year, 2-year, and 3-year bonds have yields of $6.5\%$ $6.8\%$ , and $6.95\%$ , respectively (also continuously compounded). (This is consistent with the data in Example 24.1.) We suppose that each bond has a face value of $\$100$ and provides semiannual coupons at the rate of. $8\%$ per year (with a coupon having just. been paid). The values of the bonds can be calculated from their yields as $\$101.33$ $\$101.99$ , and $\$102.47$ . If the bonds were risk-free the bond values (obtained by discounting cash flows at $5\%$ ) would be. $\$102.83$ $\$105.52$ , and $\$108.08$ , respectively. This means that the present value of expected default losses on the 1-year bond must be. $\$102.83$ Similarly, the present value of expected. default losses on the 2-year and 3-year bonds must be $\$3.53$ and $\$5.61$ . Suppose that the hazard rate in year $i$ is $\lambda_{i}$ - $1\leq i\leq3$ ) and the recovery rate is $40\%$  

Consider the 1-year bond. The probability of a default in the first 6 months is. $1-e^{-0.5\lambda_{1}}$ and the probability of a default during the following 6 months is $e^{-0.5\lambda_{1}}-e^{-\lambda_{1}}$ . We assume that defaults can happen only at the midpoints of. these 6-month intervals. The possible default times are therefore in 3 months and 9 months. The (forward) risk-free value of the bond at the 3-month point is  

$$
4e^{-0.05\times0.25}+104e^{-0.05\times0.75}=\S104.12
$$  

Given the definition of recovery rate in the previous section, if there is a default the bond will be worth. $\$40$ . The present value of the loss if there is a default at the. 3-month point is therefore.  

$$
(104.12-40)e^{-0.05\times0.25}=\S63.33
$$  

The risk-free value of the bond at the 9-month point is $104e^{-0.05\times0.25}=\$102.71$ If there is a default, the bond will be worth $\$40$ The present value of a loss if there is a default at the 9-month point is therefore  

$$
(102.71-40)e^{-0.05\times0.75}=\S60.40
$$  

The hazard rate $\lambda_{1}$ must therefore satisfy  

$$
(1-e^{-0.5\lambda_{1}})\times63.33+(e^{-0.5\lambda_{1}}-e^{-\lambda_{1}})\times60.40=1.50
$$  

The solution to this (e.g., by using Solver in Excel) is $\lambda_{1}=2.46\%$  

The 2-year bond is considered next. Its default probabilities at times 3 months. and 9 months are known from the analysis of the 1-year bond. The hazard rate for the second year is calculated so that the present value of the expected loss on. the bond is $\$3.53$ . The 3-year bond is treated similarly. The hazard rate for the second and third years prove to be $3.48\%$ and $3.74\%$ . (Note that the three estimated hazard rates are very similar to those calculated in Example 24.1 using. equation (24.2).) A worksheet showing the calculations is on the author's website:. www-2.rotman.utoronto.ca/\~hull/ofod.  

# The Risk-Free Rate  

The methods we have just presented for calculating default probabilities are critically. dependent on the choice of a risk-free rate. The spreads in Example 24.1 are differences between bond yields and risk-free rates. The calculation of the expected losses from default implied by bond prices in Example 24.2 depends on calculating the prices of. risk-free bonds. The benchmark risk-free rate used by bond traders is usually a Treasury rate. For example, a bond trader might quote the yield on a bond as being. a spread of 250 basis points over Treasuries. However, as discussed in Section 4.3, Treasury rates are too low to be useful proxies for risk-free rates..  

Credit default swap (CDS) spreads, which were briefly explained in Section 7.11 and will be discussed in more detail in Chapter 25, provide a credit spread estimate that does not depend on the risk-free rate. A number of researchers have attempted to imply riskfree rates by comparing bond yields to CDS spreads. The implied risk-free rate in normal market conditions seems to be close to the OIS rate.4  
