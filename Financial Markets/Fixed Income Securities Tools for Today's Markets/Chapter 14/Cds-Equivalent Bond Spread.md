---
tags:
  - bond_spread
  - cds_equivalent
  - credit_risk
  - default_risk
  - hazard_rate
aliases:
  - CDS spread
  - Genworth bond
  - credit spread
key_concepts:
  - CDS-equivalent spread
  - bond market price
  - default and recovery
  - discounted cash flows
  - hazard rate calculation
---

# 14.7 CDS-EQUIVALENT BOND SPREAD  

The credit spreads defined earlier in the chapter are all measures of bond return assuming no default. An alternative approach, the CDS-equivalent bond spread, accounts for default and recovery and is computed along the lines of the previous section. The basic idea is to find the hazard rate such that the market price of the bond equals the expected discounted value of its cash flows. Then, the bond's CDS-equivalent spread is the CDS spread corresponding to that hazard rate. To illustrate, say that the market price of a five-year, $5\%$ (annual pay) bond on Genworth is 94.561 as of August 16, 2021. It is shown next that the expected discounted value of that bond's cash flows equals that market price if the hazard rate is $9.322\%$ . Furthermore, from Table 14.10, the five-year CDS spread at a hazard rate of $9.322\%$ is 558.92 basis points. Therefore, the CDS-equivalent spread of this five-year, $5\%$ bond is 558.92 basis points. In other words, the credit risk implied by the bond's market price is the same as that implied by a five-year CDS at a spread of 558.92 basis points. This spread depends on the restrictive assumption that the hazard rate is constant. The calculation of expected discounted values, while seeming to imply risk neutrality, is not as restrictive as it seems: the hazard rate can be considered "risk-neutral" so that it prices fixed income securities without necessarily reflecting real-world probabilities. (This distinction is discussed in Chapter 7.)  

Appendix A14.4 gives the algebra for calculating the expected discount value of a bond's cash flows given a hazard rate. The text, however, continues with pricing 100 face amount of an annual pay, five-year,. $5\%$ Genworth bond as of August 16, 2021, and the results are summarized in Table 14.11.. Because the bond's assumed market price is consistent with a hazard rate of $9.332\%$ , which is the hazard rate in Table 14.10, the cumulative survival. and default probabilities from that table can be used here. Also, because the pricing dates are the same, the discount factors from that table can be used here as well.  

Along the lines of the previous section, the expected value of a bond's. coupon in a given year is half of its value times the probability of default over the year plus its value times the probability of no default over the year. The discounted expected value of the first coupon of the. $5\%$ Genworth bond, for example, is as in Equation (14.6), but with the bond coupon of 5.00 replacing the CDS spread payment of 5.5892,  

$$
\begin{array}{c}{\mathrm{dPV}=0.998462[8.901\%\times2.50+91.099\%\times5.00]}\ {=0.222+4.548=4.770}\end{array}
$$  

The two components of this coupon's expected discounted value are given in the second and third columns of the first row of Table 14.11. The next rows of the table repeat this calculation for subsequent coupon payments, using the appropriate discount factors, cumulative survival probabilities, and cumulative default probabilities from Table 14.10. Summing the results, the total discounted expected value of the bond's coupons is $0.916+18.760=19.676$  

TABLE 14.11 Calculating the Expected Discounted Value of 100 Face Amount of an Annual Pay Five-Year $5\%$ Genworth Bond as of August 16, 2021, at a Hazard Rate of $9.322\%$ and a Recovery Rate of $40\%$   


<html><body><table><tr><td></td><td colspan="2">Expected PV Coupon</td><td colspan="2">Expected PV Principal</td></tr><tr><td>Year</td><td>Default</td><td>No Default</td><td>Default</td><td>No Default</td></tr><tr><td>1</td><td>0.222</td><td>4.548</td><td>3.555</td><td></td></tr><tr><td>2</td><td>0.202</td><td>4.126</td><td>3.225</td><td></td></tr><tr><td>3</td><td>0.182</td><td>3.724</td><td>2.911</td><td></td></tr><tr><td>4</td><td>0.164</td><td>3.351</td><td>2.620</td><td></td></tr><tr><td>5</td><td>0.147</td><td>3.011</td><td>2.354</td><td>60.222</td></tr><tr><td>Total</td><td>0.916</td><td>18.760</td><td>14.663</td><td>60.222</td></tr><tr><td>Bond Price</td><td></td><td></td><td></td><td>94.561</td></tr></table></body></html>  

With respect to principal, if there is a default in any year, then the prin-. cipal received is the face amount times the recovery rate. The discounted expected value of principal received in the third year, for example, is the. three-year discount factor times the probability of default in year three times the recovery on 100 face amount,  

$$
0.985062\times7.3787\%\times40=2.911
$$  

which is the value given in the fourth column, third row, of Table 14.11. (Note that, in Equation (14.9), the bondholder receives 40, while in Equation (14.7), the buyer of protection receives a default compensation of 60.) The table uses the equivalents of Equation (14.9) to calculate the rest of the fourth column.  

If there is no default up to and including maturity, the bond pays its full principal amount. The expected discounted value of this cash flow is,  

$$
0.959797\times62.744\%\times100=60.222
$$  

and is given in the year five row and in the rightmost column of Table 14.11.  

Finally, adding together the four components of the bond's expected discounted value from the table, the bond's price is 94.561. Hence, because the bond is fairly priced using a hazard rate of. $9.322\%$ , and because that hazard rate corresponds to a CDS spread of 558.92 basis points (from the previous section), this bond's CDS equivalent spread is 558.92 basis points.  

This section now compares the CDS-equivalent bond spread just explained with the bond spread discussed already. First, Appendix A14.3 shows that the CDS spread is approximately equal to the hazard rate times one minus the recovery rate. Mathematically, letting $s^{C D S}$ denote the CDS spread; letting $\lambda$ denote the hazard rate, as before; and letting $R$ denote the recovery rate,  

$$
s^{C D S}\approx\lambda(1-R)
$$  

In the context of Table 14.10, for example, the approximation predicts a CDS spread of $9.322\%$ times $(1-40\%)$ , or 559.32 basis points, while the. actual spread is a very close 558.92 basis points..  

Second, Appendix A14.5 shows that,  

$$
s^{B o n d}\approx\lambda(1-R^{m})
$$  

where $s$ is the bond spread, and $R^{m}$ is the recovery rate as a percentage of market value. To this point the chapter has assumed par recovery, that is, bond recovery rates are best modeled as a fixed percentage of face amount. Market recovery, by contrast, which is used to derive Equation (14.12), assumes that recovery is a fixed percentage of market value. Say that two bonds were sold by the same issuer with the same seniority, but one of the bonds has a much longer maturity and trades at a larger price discount or premium, depending on the level of rates and spreads. In the event of default, will the two bonds recover the same amount - as assumed by par recovery - or will the longer-term bond's recovery reflect its greater discount or premium - as assumed by market recovery? Par recovery is the more common assumption and is better supported by empirical evidence.17  

In short, CDS and bond spreads are not equivalent, and the consensus in favor of the par recovery assumptions argues in favor of preferring the CDS spread. Furthermore, at high hazard rates and low bond prices, the CDS spread is significantly greater than the bond spread. To illustrate, recall from Tables 14.10 and 14.11 that the five-year. $5\%$ Genworth bond, at a hazard. rate of $9.322\%$ and a price of 94.561, has a CDS spread of 559 basis points. From the data in these tables, it can also be computed that its bond spread is a similar 551 basis points.18 However, if the hazard rate is a much higher  

$16.70\%$ , then the bond price is 80.688; the CDS spread is 1,000 basis points; and the bond spread is a much lower 932 basis points. (These computations are also left as an exercise for the reader.) Intuitively, by assuming too low a recovery for discount bonds, bond spreads have to be lower to reproduce seemingly high market prices.  
