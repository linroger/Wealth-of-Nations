---
tags:
  - '#base_correlation'
  - '#breakeven_spread'
  - '#compound_correlation'
  - '#deriva_gem'
  - '#gaussian_copula_model'
  - '#implied_correlation'
  - '#kth_to_default_cds'
  - '#synthetic_cdo_valuation'
  - '#tranche_valuation'
---
# 25.10 VALUATION OF A SYNTHETIC CDO  

Synthetic CDOs can be valued using the DerivaGem software. To explain the calculations, suppose that the payment dates on a synthetic CDO tranche are at times $\tau_{1},\tau_{2},\ldots,\tau_{m}$ and $\tau_{0}=0$ . Define $E_{j}$ as the expected tranche principal at time. $\tau_{j}$ and $\nu(\tau)$ as the present value of. $\$1$ received at time $\tau$ . Suppose that the spread on a. particular tranche (i.e., the number of basis points paid for protection) is $s$ per year. This spread is paid on the remaining tranche principal. The present value of the expected regular spread payments on the CDO is therefore given by. $s A$ , where  

$$
A=\sum_{j=1}^{m}(\tau_{j}-\tau_{j-1})E_{j}\nu(\tau_{j})
$$  

The expected loss between times $\tau_{j-1}$ and $\tau_{j}$ .5 $E_{j-1}-E_{j}.$ Assume that the loss occurs at the midpoint of the time interval (i.e., at time $0.5\tau_{j-1}+0.5\tau_{j})$ . The present value of the  

expected payoffs on the CDO tranche is  

$$
C=\sum_{j=1}^{m}(E_{j-1}-E_{j})\nu(0.5\tau_{j-1}+0.5\tau_{j})
$$  

The accrual payment due on the losses is given by $s B$ , where  

$$
B=\sum_{j=1}^{m}0.5(\tau_{j}-\tau_{j-1})(E_{j-1}-E_{j})\nu(0.5\tau_{j-1}+0.5\tau_{j})
$$  

The value of the tranche to the protection buyer is. $C-s A-s B.$ The breakeven spread on the tranche occurs when the present value of the payments equals the present value of the payoffs or  

$$
{\cal{C}}=s{\cal{A}}+s{\cal{B}}
$$  

The breakeven spread is therefore  

$$
s={\frac{C}{A+B}}
$$  

Equations (25.1) to (25.3) show the key role played by the expected tranche principal in. calculating the breakeven spread for a tranche. If we know the expected principal for a tranche on all payment dates and we also know the zero-coupon yield curve, the. breakeven tranche spread can be calculated from equation (25.4).  

If there is an upfront payment and a fixed spread of $s^{*}$ (as is the case in Table 25.6 for) the $0{-}3\%$ tranche where $s^{*}$ is 500 basis points), the upfront payment as a percent of the principal is $C-s^{*}(A+B)$  

# Using the Gaussian Copula Model of Time to Default  

The one-factor Gaussian copula model of time to default was introduced in Section 24.8. This is the standard market model for valuing synthetic CDOs. All companies are assumed to have the same probability $Q(t)$ of defaulting by time $t$ Equation (24.9) converts this unconditional probability of default by time $t$ to the probability of default by time $t$ conditional on the factor $F$  

$$
Q(t\mid F)=N\Bigg({\frac{N^{-1}[Q(t)]-\sqrt{\rho}F}{\sqrt{1-\rho}}}\Bigg)
$$  

Here $\rho$ is the copula correlation, assumed to be the same for any pair of companies.  

In the calculation of $Q(t)$ , it is usually assumed that the hazard rate for a company is constant and consistent with the index spread. The hazard rate that is assumed can be calculated by using the CDS valuation approach in Section 25.2 and searching for the hazard rate that gives the index spread. Suppose that this hazard rate is $\lambda$ . Then, from equation (24.1),  

$$
Q(t)=1-e^{-\lambda t}
$$  

From the properties of the binomial distribution, the standard market model gives the probability of exactly $k$ defaults by time $t$ , conditional on $F$ as  

$$
P(k,t|F)={\frac{n!}{(n-k)!k!}}Q(t|F)^{k}[1-Q(t|F)]^{n-k}
$$  

where $n$ is the number of reference entities in the portfolio. Suppose that the tranche under consideration covers losses on the portfolio between $\alpha_{L}$ and $\alpha_{H}$ . The parameter $\alpha_{L}$ is known as the attachment point and the parameter $\alpha_{H}$ is known as the detachment point. Define  

$$
n_{L}=\frac{\alpha_{L}n}{1-R}\quad\mathrm{and}\quad n_{H}=\frac{\alpha_{H}n}{1-R}
$$  

where $R$ is the recovery rate. Also, define $m(x)$ as the smallest integer greater than $x$ Without loss of generality, we assume that the initial tranche principal is 1. The tranche principal stays 1 while the number of defaults, $k$ , is less than $m(n_{L})$ . It is zero when the. number of defaults is greater than or equal to $m(n_{H})$ . Otherwise, the tranche principal is  

$$
\frac{\alpha_{H}-k(1-R)/n}{\alpha_{H}-\alpha_{L}}
$$  

Define $E_{j}(F)$ as the expected tranche principal at time $\tau_{j}$ conditional on the value of the.   
factor $F$ It follows that.  

$$
E_{j}(F)=\sum_{k=0}^{m(n_{L})-1}P(k,\tau_{j}|F)+\sum_{k=m(n_{L})}^{m(n_{H})-1}P(k,\tau_{j}|F)\frac{\alpha_{H}-k(1-R)/n}{\alpha_{H}-\alpha_{L}}
$$  

Define $A(F),B(F)$ , and $C(F)$ as the values of $A,B$ , and $C$ conditional on $F$ Similarly to equations (25.1) to (25.3),  

$$
\begin{array}{l}{{\displaystyle{A(F)=\sum_{j=1}^{m}(\tau_{j}-\tau_{j-1})E_{j}(F)\nu(\tau_{j})}}}\ {{\displaystyle{B(F)=\sum_{j=1}^{m}0.5(\tau_{j}-\tau_{j-1})(E_{j-1}(F)-E_{j}(F))\nu(0.5\tau_{j-1}+0.5\tau_{j})}}}\ {{\displaystyle{C(F)=\sum_{j=1}^{m}(E_{j-1}(F)-E_{j}(F))\nu(0.5\tau_{j-1}+0.5\tau_{j})}}}\end{array}
$$  

The variable $F$ has a standard normal distribution. To calculate the unconditional values of $A,B$ , and $C$ , it is necessary to integrate $A(F),B(F)$ , and $C(F)$ over a standard normal distribution. Once the unconditional values have been calculated, the breakeven spread on the tranche can be calculated as $C/(A+B)$ or the upfront payment can be calculated as $C-s^{*}(A+B)$  

The integration is best accomplished with a procedure known as Gaussian quadrature. It involves the following approximation:  

$$
\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}}e^{-F^{2}/2}g(F)d F\approx\sum_{k=1}^{M}w_{k}g(F_{k})
$$  

As $M$ increases, accuracy increases. The values of $w_{k}$ and $F_{k}$ for different values of. $M$ are given on the author's website. The value of $M$ is twice the "number of integration  

points" variable in DerivaGem. Setting the number of integration points equal to 20 usually gives good results.  

# Example 25.2  

Consider the mezzanine tranche of iTraxx Europe (5-year maturity) when the copula correlation is 0.15 and the recovery rate is $40\%$ . In this case, $\alpha_{L}=0.03$ $\alpha_{H}=0.06$ $n=125$ $n_{L}=6.25$ , and $n_{H}=12.5$ . We suppose that the term structure of interest rates is flat at $3.5\%$ , payments are made quarterly, and the CDS spread. on the index is 50 basis points. A calculation similar to that in Section 25.2 shows that the constant hazard rate corresponding to the CDS spread is $0.83\%$ (with continuous compounding). An extract from the remaining calculations is shown in Table 25.7. A value of $M=60$ is used in equation (25.12). The factor values,. $F_{k}$ and their weights, $w_{k}$ , are shown in the first segment of the table. The expected.  

<html><body><table><tr><td colspan="7">Table 25.7 Valuation of CDO in Example 25.2: principal = 1; payments are per unit of spread.</td></tr><tr><td colspan="7">Weights and values for factors</td></tr><tr><td>Wk</td><td></td><td>0.1579</td><td>0.1579</td><td>0.1342</td><td>0.0969</td><td></td></tr><tr><td>Fk</td><td></td><td>0.2020</td><td>-0.2020</td><td>-0.6060</td><td>-1.0104</td><td></td></tr><tr><td colspan="7">Expected principal, E,(Fk)</td></tr><tr><td>Time</td><td></td><td></td><td>1.0000</td><td>1.0000</td><td></td><td></td></tr><tr><td>i=1</td><td></td><td>1.0000</td><td></td><td></td><td>1.0000</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>j=19</td><td></td><td>0.9953</td><td>0.9687</td><td>0.8636</td><td>0.6134</td><td></td></tr><tr><td>j= 20</td><td></td><td>0.9936</td><td>0.9600</td><td>0.8364</td><td>0.5648</td><td></td></tr><tr><td colspan="7">PV expected payment, A(Fk)</td></tr><tr><td>i= 1</td><td></td><td>0.2478</td><td>0.2478</td><td>0.2478</td><td>0.2478</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>j=19</td><td></td><td>0.2107</td><td>0.2051</td><td>0.1828</td><td>0.1299</td><td></td></tr><tr><td>j= 20</td><td></td><td>0.2085</td><td>0.2015</td><td>0.1755</td><td>0.1185</td><td></td></tr><tr><td>Total</td><td></td><td>4.5624</td><td>4.5345</td><td>4.4080</td><td>4.0361</td><td></td></tr><tr><td colspan="7">PV expected accrual payment, B(Fk)</td></tr><tr><td>j=1</td><td></td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>j=19</td><td></td><td>0.0001</td><td>0.0008</td><td>0.0026</td><td>0.0051</td><td></td></tr><tr><td>j= 20</td><td></td><td>0.0002</td><td>0.0009</td><td>0.0029</td><td>0.0051</td><td></td></tr><tr><td>Total</td><td></td><td>0.0007</td><td>0.0043</td><td>0.0178</td><td>0.0478</td><td></td></tr><tr><td colspan="7">PV expected payoff, C(Fk)</td></tr><tr><td>j=1</td><td></td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>j= 19</td><td></td><td>0.0011</td><td>0.0062</td><td>0.0211</td><td>0.0412</td><td></td></tr><tr><td>j= 20</td><td></td><td>0.0014</td><td>0.0074</td><td>0.0230</td><td>0.0410</td><td></td></tr><tr><td>Total</td><td></td><td>0.0055</td><td>0.0346</td><td>0.1423</td><td>0.3823</td><td></td></tr></table></body></html>  

tranche principals on payment dates conditional on the factor values are calculated from equations (25.5) to (25.8) and shown in the second segment of the table. The. values of $A,B$ , and $C$ conditional on the factor values are calculated in the last three. segments of the table using equations (25.9) to (25.11). The unconditional values of $A,B$ , and $C$ are calculated by integrating $A(F)$ $B(F)$ , and $C(F)$ over the probability. distribution of. $F.$ This is done by setting. $g(F)$ equal in turn to $A(F)$ $B(F)$ , and $C(F)$ in equation (25.12). The result is.  

$$
A=4.2846,B=0.0187,C=0.1496
$$  

The breakeven tranche spread is $0.1496/(4.2846+0.0187)=0.0348$ or 348 basis points.  

This result can be obtained from DerivaGem. The CDS worksheet is used to convert the 50-basis-point spread to a hazard rate of. $0.83\%$ . The CDO worksheet is then used with this hazard rate and 30 integration points..  

# Valuation of kth-to-Default CDS  

A kth-to-default CDS (see Section 25.6) can also be valued using the standard market model by conditioning on the factor. $F.$ The conditional probability that the. $k$ th default happens between times $\tau_{j-1}$ and $\tau_{j}$ is the conditional probability that there are. $k$ or more defaults by time $\tau_{j}$ minus the conditional probability that there are. $k$ or more defaults by time. $\tau_{j-1}$ . This can be calculated from equations (25.5) to (25.7) as  

$$
\sum_{q=k}^{n}P(q,\tau_{j}|F)-\sum_{q=k}^{n}P(q,\tau_{j-1}|F)
$$  

Defaults between time $\tau_{j-1}$ and $\tau_{j}$ can be assumed to happen at time $0.5\tau_{j-1}+0.5\tau_{j}.$ This allows the present value of payments and of payoffs, conditional on. $F$ to be calculated in the same way as for regular CDS payoffs (see Section 25.2). By integrating over $F$ the unconditional present values of payments and payoffs can be calculated..  

# Example 25.3  

Consider a portfolio consisting of 10 bonds each with a hazard rate of $2\%$ per annum. Suppose we are interested in valuing a third-to-default CDS where payments are made annually in arrears. Assume that the copula correlation is 0.3, the recovery rate is $40\%$ , and all risk-free rates are. $5\%$ . As in Table 25.7, we consider $M=60$ different factor values. The unconditional cumulative probabil-. ity of each bond defaulting by years 1, 2, 3, 4, 5 is 0.0198, 0.0392, 0.0582, 0.0769, 0.0952, respectively. Equation (25.5) shows that, conditional on. $F=-1.0104$ these default probabilities are 0.0361, 0.0746, 0.1122, 0.1484, 0.1830, respectively. From the binomial distribution, the conditional probability of three or more defaults by times 1, 2, 3, 4, 5 years is 0.0047, 0.0335, 0.0928, 0.1757, 0.2717, respectively. The conditional probability of the third default happening during years 1, 2, 3, 4, 5 is therefore 0.0047, 0.0289, 0.0593, 0.0829, 0.0960, respectively. An analysis similar to that in Section 25.2 shows that the present values of payoffs, regular payments, and accrual payments conditional on $F=-1.0104$ are 0.1379, 3.8443s, and 0.1149s, where $s$ is the spread. Similar calculations are. carried out for the other 59 factor values and equation (25.12) is used to integrate over $F$ The unconditional present values of payoffs, regular payments, and accrual payments are 0.0629, 4.0580s, and 0.0524s. The breakeven CDS spread is therefore 0 $.0629/(4.0580+0.0524)=0.0153$ , or 153 basis points.  

# Implied Correlation  

In the standard market model, the recovery rate $R$ is usually assumed to be $40\%$ . This leaves the copula correlation $\rho$ as the only unknown parameter. This makes the model similar to Black-Scholes-Merton, where there is only one unknown parameter, the volatility. Market participants like to imply a correlation from the market quotes for tranches in the same way that they imply a volatility from the market prices of options.  

Suppose that the values of $\{\alpha_{L},\alpha_{H}\}$ for successively more senior tranches are $\{\alpha_{0},\alpha_{1}\}$ $\left\{\alpha_{1},\alpha_{2}\right\}$ $\{\alpha_{2},\alpha_{3}\},\ldots,\mathrm{with}\alpha_{0}=0.$ (For example, in the case of iTraxx Europe, $\alpha_{0}=0$ $\alpha_{1}=0.03$ $\alpha_{2}=0.06$ $\alpha_{3}=0.09$ $\alpha_{4}=0.12$ $\alpha_{5}=0.22$ $\alpha_{6}=1.00.$ ) There are. two alternative implied correlation measures. One is compound correlation or tranche correlation. For a tranche $\{\alpha_{q-1},\alpha_{q}\}$ , this is the value of the correlation, $\rho$ , that leads to. the spread calculated from the model being the same as the spread in the market. It is found using an iterative search. The other is base correlation. For a particular value of $\alpha_{q}\left(q\right)\geq1)$ , this is the value of $\rho$ that leads to the $\{0,\alpha_{q}\}$ tranche being priced consistently with the market. It is obtained using the following steps:  

1. Calculate the compound correlation for each tranche.   
2. Use the compound correlation to calculate the present value of the expected loss on each tranche during the life of the CDO as a percent of the initial tranche principal. This is the variable we have defined as $C$ above. Suppose that the value of $C$ for the $\{\alpha_{q-1},\alpha_{q}\}$ tranche is $C_{q}$   
3. Calculate the present value of the expected loss on the $\{0,\alpha_{q}\}$ tranche as a percent of the total principal of the underlying portfolio. This is ${\textstyle\sum_{p=1}^{q}C_{p}(\alpha_{p}-\alpha_{p-1})}$  

![](f7f66ea650e889736cbc22fcbfe3c92f125e64a3c8f5b2c93865456d5eb3b44c.jpg)  
Figure 25.3 Vertical axis gives present value of expected loss on 0 to $X\%$ tranche as a percent of total underlying principal for iTraxx Europe on January 31, 2007.  

Table 25.8  Implied correlations for 5-year iTraxx Europe tranches on January 31, 2007.   
Compound correlations   


<html><body><table><tr><td>Tranche</td><td>0-3%</td><td>3-6%</td><td>6-9%</td><td>9-12%</td><td>12-22%</td></tr><tr><td>Implied correlation</td><td>17.7%</td><td>7.8%</td><td>14.0%</td><td>18.2%</td><td>23.3%</td></tr><tr><td>Base correlations</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Tranche</td><td>0-3%</td><td>0-6%</td><td>0-9%</td><td>0-12%</td><td>0-22%</td></tr><tr><td>Implied correlation</td><td>17.7%</td><td>28.4%</td><td>36.5%</td><td>43.2%</td><td>60.5%</td></tr></table></body></html>  

4. The $C$ value for the $\{0,\alpha_{q}\}$ tranche is the value calculated in Step 3 divided by $\alpha_{q}$ The base correlation is the value of the correlation parameter, $\rho$ , that is consistent with this $C$ -value. It is found using an iterative search.  

The present value of the loss as a percent of underlying portfolio that would be calculated in Step 3 for the iTraxx Europe quotes for January 31, 2007, given in Table 25.6 are shown in Figure 25.3. The implied correlations for these quotes are shown in Table 25.8. The calculations were carried out using DerivaGem assuming that the term structure of interest rates is flat at $3\%$ and the recovery rate is $40\%$ . The CDSs worksheet shows that the 23-basis-point spread implies a hazard rate of $0.382\%$ . The implied correlations are calculated using the CDOs worksheet. The values underlying Figure 25.3 can also be calculated with this worksheet using the expression in Step 3 above.  

The correlation patterns in Table 25.8 exhibit a "correlation smile". As the tranche becomes more senior, the implied correlation first decreases and then increases. The base correlations exhibit a correlation skew where the implied correlation is an increasing function of the tranche detachment point..  

If market prices were consistent with the one-factor Gaussian copula model, then the implied correlations (both compound and base) would be the same for all tranches. From the pronounced smiles and skews that are observed in practice, we can infer that market prices are not consistent with this model.  

# Valuing Nonstandard Tranches  

We do not need a model to value the standard tranches of a standard portfolio such as iTraxx Europe because the spreads for these tranches can be observed in the market. Sometimes quotes need to be produced for nonstandard tranches of a standard portfolio. Suppose that you need a quote for the. $4\mathrm{-}8\%$ iTraxx Europe tranche. One approach is to interpolate base correlations so as to estimate the base correlation for the $0{-}4\%$ tranche and the $0{-}8\%$ tranche. These two base correlations. allow the present value of expected loss (as a percent of the underlying portfolio principal) to be estimated for these tranches. The present value of the expected loss for the $4\mathrm{-}8\%$ tranche (as a percent of the underlying principal) can be estimated as the. difference between the present value of expected losses for the. $0{-}8\%$ and $0{-}4\%$ tranches. This can be used to imply a compound correlation and a breakeven spread for the tranche.  

It is now recognized that this is not the best way to proceed. A better approach is to calculate expected losses for each of the standard tranches and produce a chart such as  

Figure 25.3 showing the variation of expected loss for the. $0{-}X\%$ tranche with $X$ Values on this chart can be interpolated to give the expected loss for the. $0{-}4\%$ and the $0{-}8\%$ tranches. The difference between these expected losses is a better estimate of the expected loss on the $4\mathrm{-}8\%$ tranche than that obtained from the base correlation. approach.  

It can be shown that for no arbitrage the expected losses when calculated as in Figure 25.3 must increase with $X$ at a decreasing rate. If base correlations are interpolated and then used to calculate expected losses, this no-arbitrage condition is often not satisfied. (The problem here is that the base correlation for the. $0{-}X\%$ tranche is a nonlinear function of the expected loss on the $0{-}X\%$ tranche.) The direct approach of interpolating expected losses is therefore much better than the indirect approach of. interpolating base correlations. What is more, it can be done so as to ensure that the no-arbitrage condition just mentioned is satisfied.  
