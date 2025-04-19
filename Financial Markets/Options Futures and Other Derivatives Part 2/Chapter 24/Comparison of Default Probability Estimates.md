---
tags:
  - bond_yields
  - credit_spreads
  - default_probability
  - hazard_rates
  - risk_neutral
aliases:
  - Bond Yields vs. Default
  - Default Probability Comparison
  - Hazard Rate Estimates
key_concepts:
  - Credit spread impact
  - Expected excess return
  - Flight to quality
  - Historical vs. implied rates
  - Risk-neutral valuation
---

# 24.5 COMPARISON OF DEFAULT PROBABILITY ESTIMATES  

The default probabilities estimated from historical data are usually much less than those. derived from bond yield spreads. The difference between the two was particularly large. during the financial crisis which started in mid-2007. This is because there was what is termed a "flight to quality" during the crisis, where all investors wanted to hold safe securities such as Treasury bonds. The prices of corporate bonds declined, thereby increasing their yields. The credit spread on these bonds increased and calculations such as the one in equation (24.2) gave very high hazard rate estimates..  

Table 24.2 is taken from research published in 2005 which used Moody's data. It compares historical hazard rates with those implied by bond yields for bonds with. different ratings and shows that the latter are much greater than the former. The historical hazard rate was calculated using data similar to that in Table 24.1. The. hazard rate implied by bond yields was calculated using equation (24.2) with a recovery. rate of $40\%$ . The bond yield spreads used were averages over a number of years. The. risk-free rate was estimated from the credit default swap market to be 43 basis points. higher than Treasuries. It can be seen that the ratio of the hazard rate calculated from bonds to the historical hazard rate tends to decline as a bond becomes less creditworthy, whereas the difference between the two tends to increase. (The B-rated bonds. do not quite conform to this pattern.)  

More recent data gives a similar result to that in Table 24.2. Consider, for example, Baa-rated (or BBB-rated) bonds. The cumulative probability of default during a seven-. year period, taken from Table 24.1, is. $2.33\%$ . Equation (24.10) gives  

$$
\begin{array}{r}{\overline{{\lambda}}(7)=-\frac{1}{7}\ln\left[1-Q(7)\right]}\end{array}
$$  

where $\overline{{\lambda}}(t)$ is the average hazard rate during $t$ years and $Q(t)$ is the cumulative probability of default by time $t$ years. Setting $Q(7)=0.0233$ , we obtain $ \overline{{\lambda}}(7)=0.0034$ (i.e., $0.34\%$ or 34 basis points). The spread of the Baa (or BBB) corporate bond yield over the riskfree rate was about $1.8\%$ for the years preceding 2019. Equation (24.2) gives an estimate for the hazard rate implied by bond yields as $0.018/(1-0.4)=0.03$ , or $3\%$ (about nine times the estimate from Table 24.1).  

Table 24.2 Seven-year average hazard rates ( $\%$ per annum)   


<html><body><table><tr><td>Rating</td><td>Historical hazardrate</td><td>Hazardrate frombonds</td><td>Ratio</td><td>Difference</td></tr><tr><td>Aaa</td><td>0.04</td><td>0.67</td><td>16.8</td><td>0.63</td></tr><tr><td>Aa</td><td>0.06</td><td>0.78</td><td>13.0</td><td>0.72</td></tr><tr><td>A</td><td>0.13</td><td>1.28</td><td>9.8</td><td>1.15</td></tr><tr><td>Baa</td><td>0.47</td><td>2.38</td><td>5.1</td><td>1.91</td></tr><tr><td>Ba</td><td>2.40</td><td>5.07</td><td>2.1</td><td>2.67</td></tr><tr><td>B</td><td>7.49</td><td>9.02</td><td>1.2</td><td>1.53</td></tr><tr><td>Caaandlower</td><td>16.90</td><td>21.30</td><td>1.3</td><td>4.40</td></tr></table></body></html>  

Table 24.3 Expected excess return on bonds (basis points).   


<html><body><table><tr><td>Rating</td><td>Bondyieldspread overrisk-freerate</td><td>Spreadfor historicaldefaults</td><td>Excess return</td></tr><tr><td>Aaa</td><td>40</td><td>2</td><td>38</td></tr><tr><td>Aa</td><td>47</td><td>4</td><td>43</td></tr><tr><td>A</td><td>77</td><td>8</td><td>69</td></tr><tr><td>Baa</td><td>143</td><td>28</td><td>115</td></tr><tr><td>Ba</td><td>304</td><td>144</td><td>160</td></tr><tr><td>B</td><td>542</td><td>449</td><td>93</td></tr><tr><td>Caa</td><td>1278</td><td>1014</td><td>264</td></tr></table></body></html>  

Table 24.3 shows another way of looking at the results in Table 24.2. The second. column shows the bond yield spread. The spread required to compensate for the. historical default rate is shown in the third column. (For example, in the case of the Baa bond it is $0.47\%\times0.6=0.28\%$ , or 28 basis points.) The expected excess return is. shown in the final column of the table..  

A large percentage difference between the two hazard rate estimates in Table 24.2 translates into a small expected excess return on the bond. For Aaa-rated bonds, the ratio of the two hazard rates is 16.8, but the expected excess return is only 38 basis points. The expected excess return tends to increase as credit quality declines.  

# Real-World vs. Risk-Neutral Probabilities  

The default probabilities or hazard rates implied from credit spreads are risk-neutral.   
estimates. They can be used to calculate expected cash flows in a risk-neutral world.   
when there is credit risk. The value of the cash flows is obtained using risk-neutral valuation by discounting the expected cash flows at a risk-free rate. Example 24.2 shows.   
an application of this to the calculation of the cost of defaults. We will see more.   
applications in the next chapter.  

Default probabilities or hazard rates calculated from historical data are real-world. (sometimes termed physical) default probabilities. Table 24.2 shows that risk-neutral default probabilities are much higher than real-world default probabilities. The expected. excess return in Table 24.3 arises directly from the difference between real-world and. risk-neutral default probabilities. If there were no expected excess return, then the real-. world and risk-neutral default probabilities would be the same, and vice versa..  

Why do we see such big differences between real-world and risk-neutral default probabilities? As we have just argued, this is the same as asking why corporate bond traders earn more than the risk-free rate on average.  

One reason often advanced for the results is that corporate bonds are relatively illiquid and the returns on bonds are higher than they would otherwise be to compensate for this. This is true, but research shows that it does not fully explain the results in Table 24.3.' Another possible reason for the results is that the subjective default probabilities of bond traders may be much higher than the those given in Table 24.1. Bond traders may be allowing for depression scenarios much worse than anything seen during the period covered by historical data. However, it is difficult to see how this can explain a large part of the excess return that is observed.  

By far the most important reason for the results in Tables 24.2 and 24.3 is that bonds do not default independently of each other. There are periods of time when default rates are very low and periods of time when they are very high. Evidence for this can be obtained by looking at the default rates in different years. S&P statistics show that since 1981 the default rate per year in the U.S. for non-investment-grade. rated companies has ranged from a low of. $0.63\%$ in 1981 to a high of $11.81\%$ in 2009, respectively. The year-to-year variation in default rates gives rise to systematic risk (i.e., risk that cannot be diversified away) and bond traders earn an excess expected return for bearing the risk. (This is similar to the excess expected return earned by equity. holders that is calculated by the capital asset pricing model-see the appendix to. Chapter 3.) The variation in default rates from year to year may be because of overall. economic conditions and it may be because a default by one company has a ripple effect resulting in defaults by other companies. (The latter is referred to by researchers as credit contagion.)  

In addition to the systematic risk we have just talked about, there is nonsystematic (or idiosyncratic) risk associated with each bond. If we were talking about stocks, we would argue that investors can to a large extent diversify away the nonsystematic risk by choosing a portfolio of, say, 30 stocks. They should not therefore demand a risk premium for bearing nonsystematic risk. For bonds, the arguments are not so clear-cut. Bond returns are highly skewed with limited upside. (For example, on an individual bond, there might be a $99.75\%$ chance of a $4\%$ return in a year, and a. $0.25\%$ chance of a $-60\%$ return in the year, the first outcome corresponding to no default and the second to default.) This type of risk is difficult to "diversify away".8 It would require tens of. thousands of different bonds. In practice, many bond portfolios are far from fully. diversified. As a result, bond traders may earn an extra return for bearing nonsystematic. risk as well as for bearing the systematic risk mentioned in the previous paragraph.  

# Which Default Probability Estimate Should Be Used?  

At this stage it is natural to ask whether we should use real-world or risk-neutral default. probabilities in the analysis of credit risk. The answer depends on the purpose of the. analysis. When valuing credit derivatives or estimating the impact of default risk on the. pricing of instruments, risk-neutral default probabilities should be used. This is because the analysis calculates the present value of expected future cash flows and almost invariably (implicitly or explicitly) involves using risk-neutral valuation. When carrying. out scenario analyses to calculate potential future losses from defaults, real-world default probabilities should be used..  
