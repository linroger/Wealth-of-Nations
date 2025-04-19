---
tags:
  - cds_pricing
  - discount_rates
  - protection_leg
  - single_name_cds
  - survival_probabilities
aliases:
  - CDS Valuation
  - Credit Default Swap Pricing
key_concepts:
  - CDS valuation example
  - Discount rates
  - Protection buyer payments
  - Protection seller payments
  - Survival probabilities
---

# 18.7 PRICING SINGLE-NAME CDS  

The basic approach to pricing CDS is relatively simple, but there are real-world market conventions that have to be taken into account in practice. We first present a simplified CDS pricing example before reviewing market conventions and how they affect pricing.  

# 18.7.1 A SIMPLIFIED CDS VALUATION EXAMPLE  

We can use some of the tools reviewed above to value a CDS. Essentially the approach is to choose the CDS spread cds in such a way as to set the PV of the expected payments by the protection seller (the protection leg) to the PV of the payments made by the protection buyer (the premium leg). This was captured by Eq. (18.35). The two main inputs in this calculation are the survival probabilities and the discount rates. The survival probabilities should be risk-neutral probabilities and they can be obtained from bond prices or asset swaps discussed in Section 18.3. Of course, once market prices or CDS spreads are given, the survival probabilities can also be backed out from CDS markets, similar to how implied volatilities are backed out from option prices.  

Let's consider the following example of a 5-year CDS with a notional amount $N=\$1$ We assume that default can occur in the middle of each year. The riskless rate is assumed to be $4\%$ and the yield curve is flat. If one uses the default intensity approach outlined in Section 18.6 with a hazard rate of $\lambda=5\%$ , then one can calculate the probability of survival for each year from Eq. (18.22). The default intensity approach is also referred to as a reduced form approach to modeling default. We distinguish it from the structural approach to default modeling discussed in Chapter 19.  

For the end of the first year, the equation leads to a probability of default (PD) of $P(\tau<T)=$ $1-e^{-\lambda T}=1-e^{-5\%\times1}=0.0488$ Therefore the probability of survival is $1-0.0488=0.9512$ We can similarly calculate the probability of survival (PS) until the end of years 1, 2, 3, 4, and 5. This is shown in column 2 of Table 18.1. The second column shows the expected premium payment times the CDS spread cds. It is calculated as $P S\times c d s\times\mathrm{N}$ otional amount.  

The discount factor in this example is based on continuous discounting. The discount factor for year 1 is $e^{-0.04\times1}=0.9608$ The present value of the expected premium payment at the end of thee first year in Table 18.1 is. $0.9512\times0.9608\times c d s\times1=0.9139\times c d s$ Note that this present value. does not take into account the accrual payments (Eq. (18.32)).  

We also need to add the accrued premiums in the event of a default. Table 18.2 shows their calculation in the first five columns. The probability of default during year. $T+I$ is calculated as the probability of survival until the end of year $T$ minus the probability of survival until the end of year $T+I$ For example of date $T=I.5$ we calculate the probability of survival until year. $T=l.5$ to be $0.9512-0.9048=0.0464$ . Since we expect to receive the CDS premium cds at date $T=l.5$ the expected accrual payment is $0.464\times{\bf0.5}\times{c d s}$ . If we multiply the expected accrual payments. times the discount factor we obtain a present value of all expected accrual payments of $0.1006\times c d s$  

<html><body><table><tr><td colspan="4">Table18.1S Simplified CDS Valuation Example (PV of Premium Leg)</td></tr><tr><td>Time (Years)</td><td>Probability of Survival (PS)</td><td>Expected Payment</td><td>Discount Factor</td><td>PVofExpected Payment</td></tr><tr><td>1</td><td>0.9512</td><td>0.9512×cds</td><td>0.9608</td><td>0.9139×cds</td></tr><tr><td>2</td><td>0.9048</td><td>0.9048×cds</td><td>0.9231</td><td>0.8353Xcds</td></tr><tr><td>3</td><td>0.8607</td><td>0.8607× cds</td><td>0.8869</td><td>0.7634×cds</td></tr><tr><td>4</td><td>0.8187</td><td>0.8187×cds</td><td>0.8521</td><td>0.6977× cds</td></tr><tr><td>5</td><td>0.7788</td><td>0.7788×cds</td><td>0.8187</td><td>0.6376×cds</td></tr><tr><td>Total</td><td></td><td></td><td></td><td>3.8479X cds</td></tr></table></body></html>  

Table 18.2 Simplified CDS Valuation Example (PV of Protection Leg and Accrued Payments)   


<html><body><table><tr><td>Time</td><td>Probability of Default</td><td>Expected Accrual</td><td>Discount Factor</td><td>PV of Expected Accrual Payment</td><td>R</td><td>Expected</td><td>PV of Expected</td></tr><tr><td>(Years)</td><td>(PD) 0.0488</td><td>Payment 0.0244Xcds</td><td>0.9802</td><td>0.0239×cds</td><td>0.4</td><td>Payoff 0.0293</td><td>Payoff 0.0287</td></tr><tr><td>0.5 1.5</td><td>0.0464</td><td>0.0232×cds</td><td>0.9418</td><td>0.0218Xcds</td><td>0.4</td><td>0.0278</td><td>0.0262</td></tr><tr><td>2.5</td><td>0.0441</td><td>0.0221×cds</td><td>0.9048</td><td>0.0200×cds</td><td>0.4</td><td>0.0265</td><td>0.0240</td></tr><tr><td>3.5</td><td>0.0420</td><td>0.0210Xcds</td><td>0.8694</td><td>0.0182Xcds</td><td>0.4</td><td>0.0252</td><td>0.0219</td></tr><tr><td>4.5</td><td>0.0399</td><td>0.0200×cds</td><td>0.8353</td><td>0.0167×cds</td><td>0.4</td><td>0.0240</td><td>0.0200</td></tr><tr><td></td><td></td><td></td><td></td><td>0.1006×cds</td><td></td><td></td><td>0.1208</td></tr></table></body></html>  

If we add the expected accrual payments and the expected premium payments, we obtain a value of $3.8479\times c d s+0.1006\times c d s=3.9585\times c d s$  

Finally, lets consider the protection leg payments. The last three columns of Table 18.2 show the calculations. We assume a standard recovery rate of $R=40\%$ . The expected payoff for date $T=0.5$ e.g., $(1-R)\times N\times0.0488=\mathbf{0.6}\times\mathbf{1}\times\mathbf{0.0488}\times\mathbf{0.9802}=\mathbf{0.0287}$ One can use programs such as Matlab or VBA to calculate the spread cds that sets the present value of the premium leg and the protection leg equal to each other so that $3.9585\times c d s=0.1208$ If we do that we find a value of $c d s=0.0306$ or 306 basis points. In other words, given the parameters in this example a CDS spread of 306 basis points would set the present value of the premium leg payments equal to the protection leg payments.  

# 18.7.2 REAL-WORLD COMPLICATIONS  

The above example is very much a simplified and unrealistic treatment of CDS valuation. It ignores many real-world complications such as coupon, day-count conventions, interest rate curves, and upfront payments. CDS premiums are paid typically on a quarterly basis and since the "CDS big bang", CDS include upfront payments. The choice of the benchmark yield curve and riskless rate is important in practice. The swap yield curve or the LIBOR curve could be used as the basis for the discount factors, but as we will discuss in Chapter 24 the LIBOR curve has some issues due to counterparty risk. White (2013) provides detailed CDS pricing formulae that take into account the ISDA model and real-world conventions.25 Since the CDS market has moved from the spread convention for single-name contracts to a fixed coupon and upfront payments, following standardization it is important for market participants to be able to match the upfront payment amounts and be able to translate upfront quotations to spread quotations and vice versa in a standardized manner. Therefore, ISDA created the CDS Standard model and made the underlying source code for CDS calculations freely available at http://www.cdsmodel.com/cdsmodel/.  

# 18.7.3 LESSONS FROM THE GFC FOR CDS PRICING  

Historically financial innovation has played an important role in economic growth, funding economic activity and risk sharing, but occasionally it also turns sour. Derivatives are one example of financial innovation and derivatives debacles occur with an disturbingly high frequency.6 Such debacles have led to unexpected losses on the part of unsophisticated or misinformed counterparties such as corporates, municipalities, or banks, but sometimes they lead to systemic risk. The insurance company AIG was nearly brought down by losses on CDS positions during the GFC. AIG had a AAA credit rating and was therefore considered a safe counterparty to sell CDS protection. However, the size of its portfolio grew disproportionately large and reached around $\$500$ billion dollars in notional value in 2008. AIG also provided insurance against the default of Lehman. Brothers which famously went under in September of 2008. One of the mistakes that AIG made. was that, in contrast to the reserves it held for its traditional insurance business, it never correctly reserved for the CDS that it was selling. The irony was that CDS were first developed within a unit of AIG Financial Products which was started in 1987.  
