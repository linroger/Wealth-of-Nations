---
tags:
  - '#collateral_agreements'
  - '#counterparty_default'
  - '#credit_risk_derivatives'
  - '#cva_dva'
  - '#downgrade_triggers'
  - '#exposure_calculation'
  - '#isda_master_agreement'
  - '#monte_carlo_simulation'
  - '#wrong_way_risk'
---
# 24.7 CREDIT RISK IN DERIVATIVES TRANSACTIONS  

In this section we consider how credit risk is quantified for bilaterally cleared derivatives. transactions. This topic was introduced in Chapter 9. Typically, bilaterally cleared derivatives between two companies are governed by an International Swaps and Derivatives Association (ISDA) Master Agreement. For transactions between financial institutions, regulations require that variation margin be exchanged and initial margin be posted with third parties. Initial margin is calculated so that it covers losses over a 10-day period with $99\%$ confidence.  

The Master Agreement defines the circumstances when an event of default occurs. For example, when one side fails to make payments on outstanding derivatives transactions as required or fails to post margin (i.e., collateral) as required or declares bankruptcy, there is an event of default. The other side then has the right to terminate all outstanding transactions. There are two circumstances when this is likely to lead to a loss for the nondefaulting party:  

1. The total value of the transactions to the nondefaulting party is positive and greater than the collateral (if any) posted by the defaulting party. The nondefaulting party is then an unsecured creditor for the value of the transactions minus the value of the collateral.  

2. The total value of the transactions is positive to the defaulting party and the collateral posted by the nondefaulting party is greater than this value. The nondefaulting party is then an unsecured creditor for the return of the excess collateral it has posted.  

For the purposes of our discussion, we ignore the bid-ask spread costs incurred by the nondefaulting party when it replaces the transactions it had with the defaulting party.  

# CVA and DVA  

CVA and DVA were introduced in Chapter 9. A bank's credit valuation adjustment (CVA) for a counterparty is the present value of the expected cost to the bank of a default by the counterparty. Its debit (or debt) valuation adjustment (DVA) is the present value of the expected cost to the counterparty of a default by the bank. The possibility of the bank defaulting is a benefit to the bank because it means that there is some possibility that the bank will not have to make payments as required on its derivatives. DVA, a cost to the counterparty, therefore increases the value of its derivatives portfolio to the bank.  

The no-default value of outstanding transactions is their value assuming neither side. will default. (Derivatives pricing models such as Black-Scholes-Merton provide no-. default values.) If $f_{\mathrm{nd}}$ is the no-default value to the bank of its outstanding derivatives. transactions with the counterparty, the value the outstanding transactions when possible defaults are taken into account is.  

$$
f_{\mathrm{nd}}-\mathrm{CVA}+\mathrm{DVA}
$$  

Suppose that the life of the longest outstanding derivative between the bank and the counterparty is $T$ years. As explained in Chapter 9, the interval between time 0 and. time $T$ is divided into $N$ subintervals and CVA and DVA are estimated as  

$$
\mathrm{{CVA}}=\sum_{i=1}^{N}q_{i}\nu_{i},\mathrm{{DVA}}=\sum_{i=1}^{N}q_{i}^{*}\nu_{i}^{*}
$$  

Here $q_{i}$ is the risk-neutral probability of the counterparty defaulting during the ith interval, $\nu_{i}$ is the present value of the expected loss to the bank if the counterparty defaults at the midpoint of the ith interval, $q_{i}^{*}$ is the risk-neutral probability of the bank defaulting during the ith interval, and $\nu_{i}^{*}$ is the present value of the expected loss to the counterparty (gain to the bank) if the bank defaults at the midpoint of the ith interval.  

Consider first the calculation of $q_{i}$ Note that $q_{i}$ should be a risk-neutral default probability because we are valuing future cash flows and (implicitly) using risk-neutral valuation (see Section 24.5). Suppose that $t_{i}$ is the end point of the ith interval, so that $q_{i}$ is the risk-neutral probability of a counterparty default between times. $t_{i-1}$ and $t_{i}$ We first estimate credit spreads for the counterparty for a number of different maturities. Using interpolation, we then obtain an estimate,. $s(t_{i})$ , of the counterparty's credit spread for maturity $t_{i}$ $1\leq i\leq N.$ ). From equation (24.2), an estimate of the counter-. party's average hazard rate between times O and. $t_{i}$ is $s(t_{i})/(1-R)$ , where $R$ is the recovery rate expected in the event of a counterparty default. From equation (24.1), the.  

probability that the counterparty will not default by time $t_{i}$ is  

$$
\exp\left(-\frac{s(t_{i})t_{i}}{1-R}\right)
$$  

This means that  

$$
q_{i}=\exp\left(-\frac{s(t_{i-1})t_{i-1}}{1-R}\right)-\exp\left(-\frac{s(t_{i})t_{i}}{1-R}\right)
$$  

is the probability of the counterparty defaulting during the ith interval. The probability $q_{i}^{*}$ is similarly calculated from the bank's credit spreads.  

Consider next the calculation of the. $\nu_{i}$ assuming that no collateral is posted. This usually requires a computationally very time consuming Monte Carlo simulation. The market variables determining the no-default value of the outstanding transactions between the bank and the counterparty are simulated in a risk-neutral world between time 0 and time T. On each simulation trial, the exposure of the bank to the counterparty. at the midpoint of each interval is calculated. The exposure is equal to. $\operatorname*{max}(V,0)$ , where $V$ is the total value of the transactions to the bank. (If the transactions in total have a. negative value to the bank, there is no exposure; if they have a positive value, the exposure is equal to this positive value.) The variable $\nu_{i}$ is set equal to the present value of the. average exposure across all simulation trials multiplied by one minus the recovery rate. The variable $\nu_{i}^{*}$ is calculated similarly from the counterparty's exposure to the bank..  

When there is a collateral agreement between the bank and the counterparty, the calculation of $\nu_{i}$ is more complicated. It is necessary to estimate on each simulation trial the amount of collateral held by each side at the midpoint of the ith interval in the event of a default. In this calculation, it is usually assumed that the counterparty stops posting collateral and stops returning any excess collateral held $c$ days before a default. The parameter $c$ , which is typically 10 or 20 days, is referred to as the cure period or margin period of risk. In order to know what collateral is held at the midpoint of an interval in the event of a default, it is necessary to calculate the value of transactions $c$ days earlier. The way exposure is calculated is illustrated with the following example. The present value of the expected loss $\nu_{i}$ is calculated from the average exposure across all simulation trials as in the no-collateral case. A similar analysis of the average exposure of the counterparty to the bank leads to $\nu_{i}^{*}$  

# Example 24.4  

There is a two-way zero-threshold collateral agreement between a bank and its (nonfinancial) counterparty. This means that each side is required to post collateral worth $\operatorname*{max}(V,0)$ with the other side, where $V$ is the value of the outstanding transactions to the other side. The cure period is 20 days. Suppose that time $\tau$ is the midpoint of one of the intervals used in the bank's CVA calculation.  

1. On a particular simulation trial, the value of outstanding transactions to the bank at time $\tau$ is 50 and their value 20 days earlier is 45. In this case, the. calculation assumes that the bank has collateral worth 45 in the event of a default at time $\tau$ . The bank's exposure is the uncollateralized value it has in the derivatives transactions, or 5.   
2. On a particular simulation trial the value of outstanding transactions to the bank at time $\tau$ is 50 and their value 20 days earlier is 55. In this case, it is assumed that the bank will have adequate collateral and its exposure is zero.   
3. On a particular simulation trial the value of outstanding transactions to the bank at time $\tau$ is $-50$ and the value 20 days earlier is $-45$ . In this case, the bank is assumed to have posted less than 50 of collateral in the event of a default at time $\tau$ and its exposure is zero.   
4. On a particular simulation trial the value of outstanding transactions to the bank at time $\tau$ is $-50$ and the value 20 days earlier is $-55$ . In this case, it is assumed that 55 of collateral is held by the counterparty 20 days before time $\tau$ and, in the event of a default at time $\tau$ , none of it is returned. The bank's exposure is therefore 5, the excess collateral it has posted.  

In addition to calculating CVA, banks usually calculate peak exposure at the midpoint of each interval. This is a high percentile of the exposures given by the Monte Carlo simulation trials. For example, if the percentile is $97.5\%$ and there are 10,000 Monte Carlo trials, the peak exposure at a particular midpoint is the 250th highest exposure at that point. The maximum peak exposure is the maximum of the peak exposures at all midpoints.12  

Banks usually store all the paths sampled for all market variables and all the valuations calculated on each path. This enables the impact of a new transaction on CVA and DVA to be calculated relatively quickly. Only the value of the new transaction for each sample path needs to be calculated in order to determine its incremental effect on CVA and DVA. If the value of the new transaction is positively correlated to existing transactions, it is likely to increase CVA and DVA. If it is negatively correlated to existing transactions (e.g., because it is wholly or partially unwinding those transactions), it is likely to decrease CVA and DVA.  

The method for calculating CVA that we have presented assumes that the probability of default by the counterparty is independent of the bank's exposure. This is a reasonable assumption in many situations. Traders use the term wrong-way risk to describe the situation where the probability of default is positively correlated with exposure and the term right-way risk to describe the situation where the probability of default is negatively correlated with exposure. More complicated models than those we describe have been developed to describe dependence between default probability and exposure.  

A bank has one CVA and one DVA for each of its counterparties. The CVAs and. DVAs can be regarded as derivatives which change in value as market variables change,. counterparty credit spreads change, and bank credit spreads change. The risks in CVA (and occasionally DVA) are managed in the same way as the risks in other derivatives. using Greek letter calculations, scenario analyses, etc.  

# Credit Risk Mitigation  

There are a number of ways banks try to reduce credit risk in bilaterally cleared transactions. One, which we have already mentioned, is netting. Suppose a bank has three uncollateralized transactions with a counterparty worth $+\$10$ million, $+\$30$ million, and $-\$25$ million. If they are regarded as independent transactions, the bank's exposure on the transactions is $\$10$ million, $\$30$ million, and $\$0$ for a total exposure of. $\$40$ million. With netting, the transactions are regarded as a single transaction worth $\$15$ million and the exposure is reduced from. $\$40$ million to $\$15$ million.  

# Business Snapshot 24.1 Downgrade Triggers and AIG  

AIG provides an example of the operation of downgrade triggers. By 2008,AIG had. entered into many derivatives transactions where it guaranteed the performance of the AAA-rated tranches of ABS CDOs. (See Chapter 8 for a description of ABS CDOs.) Many of AIG's transactions had downgrade triggers stating that AIG did. not have to post collateral provided its credit rating remained above AA. On September 15, 2008, it was downgraded below AA by Moody's, S&P, and Fitch. The tranches it had guaranteed were performing badly and it immediately received. collateral calls from many counterparties. It was unable to meet the collateral calls. and bankruptcy was avoided only by a massive government bailout..  

Collateral agreements are an important way of reducing credit risk. Collateral can be either cash (which usually earns interest) or marketable securities. (The latter may be subject to a haircut to calculate their cash equivalent for collateral purposes.) Collateral agreements between financial institutions are now determined by regulation. Derivatives transactions receive favorable treatment in the event of a default. The nondefaulting. party is entitled to keep any collateral posted by the other side. Expensive and timeconsuming legal proceedings are not usually necessary.  

Another credit risk mitigation technique used by financial institutions is known as a. downgrade trigger. This is a clause in the Master Agreement between a bank and a. nonfinancial counterparty stating that if the credit rating of the counterparty falls below a certain level, say BBB, the bank has the option to require collateral or close out all. outstanding derivatives transactions at market value. Downgrade triggers do not provide protection against a relatively big jump in a counterparty's credit rating (e.g., from A to. default). Moreover, they work well only if relatively little use is made of them. If the. counterparty has many downgrade triggers with different derivatives dealers, they are likely to provide little protection to those dealers (see Business Snapshot 24.1)..  

# Special Cases  

In this section we consider two special cases where CVA can be calculated without Monte Carlo simulation.  

The first special case is where the portfolio between the bank and the counterparty. consists of a single uncollateralized derivative that provides a payoff to the bank at. time $T.$ (The bank could for instance have bought a European option with remaining life $T$ from the counterparty.) The bank's exposure at a future time is the no-default value of the derivative at that time. The present value of the exposure is therefore the present value of the derivative's future value. This is the no-default value of the. derivative today. Hence  

$$
\nu_{i}=f_{\mathrm{nd}}(1-R)
$$  

for all $i$ where $f_{\mathrm{nd}}$ is the no-default value of the derivative today and $R$ is the recovery rate. This implies.  

$$
\mathrm{CVA}=(1-R)f_{\mathrm{nd}}\sum_{i=1}^{N}q_{i}
$$  

In this case $\mathrm{{DVA}=0}$ , so that the value. $f$ of the derivative today after allowing for credit risk is  

$$
f=f_{\mathrm{nd}}-(1-R)f_{\mathrm{nd}}\sum_{i=1}^{N}q_{i}
$$  

One particular derivative of the type we are considering is a. $T$ -year zero-coupon bond issued by the counterparty. Assuming recoveries on the bond and the derivative are the same, the value of the bond,. $B$ , is  

$$
B=B_{\mathrm{nd}}-(1-R)B_{\mathrm{nd}}\sum_{i=1}^{N}q_{i}
$$  

where $B_{\mathrm{nd}}$ is the no-default value of the bond. From equations (24.5) and (24.6),  

$$
{\frac{f}{f_{\mathrm{nd}}}}={\frac{B}{B_{\mathrm{nd}}}}
$$  

$y$ is the yield on the $T$ -year bond issued by the counterparty and $y_{\mathrm{nd}}$ is the yield on a. similar riskless bond,. $B=e^{-y T}$ and $B_{\mathrm{nd}}=e^{-y_{\mathrm{nd}}T}$ so that this equation gives  

$$
f=f_{\mathrm{nd}}e^{-(y-y_{\mathrm{nd}})T}
$$  

This shows that the derivative can be valued by increasing the discount rate that is applied to the expected payoff in a risk-neutral world by the counterparty's $T$ year credit spread.  

# Example 24.5  

The Black-Scholes-Merton price of a 2-year uncollateralized option is $\$3$ . Twoyear zero-coupon bonds issued by the company selling the option have a yield $1.5\%$ greater than the risk-free rate. The value of the option after default risk is considered is $3e^{-0.015\times2}=\$2.91$ (This assumes that the option stands alone and is not netted with other derivatives in the event of default.)  

For the second special case, we consider a bank that has entered into an uncollateralized forward transaction with a counterparty where it has agreed to buy an asset for. price $K$ at time $T.$ The bank has no other transactions with the counterparty. Define. $F_{t}$ as the forward price at time $t$ for delivery of the asset at time. $T.$ The value of the transaction at time $t$ is, from Section 5.7,  

$$
(F_{t}-K)e^{-r(T-t)}
$$  

where $r$ is the risk-free interest rate (assumed constant).  

The bank's exposure at time $t$ is therefore  

$$
\mathrm{max}[(F_{t}-K)e^{-r(T-t)},0]=e^{-r(T-t)}\mathrm{max}[F_{t}-K,0]
$$  

The expected value of. $F_{t}$ in a risk-neutral world is. $F_{0}$ . The standard deviation of ln. $F_{t}$ is $\sigma\sqrt{t}$ where $\sigma$ is the volatility of $F_{t}.$ From equation (15A.1) the expected exposure at time $t$ is therefore  

$$
w(t)=e^{-r(T-t)}[F_{0}N(d_{1}(t))-K N(d_{2}(t))]
$$  

where  

$$
d_{1}(t)=\frac{\ln(F_{0}/K)+\sigma^{2}t/2}{\sigma\sqrt{t}},d_{2}(t)=d_{1}(t)-\sigma\sqrt{t}
$$  

It follows that  

$$
\nu_{i}=w(t_{i})e^{-r t_{i}}(1-R)=e^{-r T}(1-R)[F_{0}N(d_{1}(t_{i}))-K N(d_{2}(t_{i}))]
$$  

# Example 24.6  

A bank has entered into a forward contract to buy 1 million ounces of gold from a mining company in 2 years for $\$1,500$ per ounce. The current 2-year forward price. is $\$1,600$ per ounce. We suppose that only two intervals each 1-year long are. considered in the calculation of CVA. The probability of the company defaulting during the first year is. $2\%$ and the probability that it will default during the. second year is. $3\%$ . The risk-free rate is $5\%$ per annum. A. $30\%$ recovery in the. event of default is anticipated. The volatility of the forward price of gold is $20\%$  

In this case, $q_{1}=0.02,q_{2}=0.03,F_{0}=1,600,K=1,500,\sigma=0.2,r=0.05,$ $R=0.3,t_{1}=0.5$ , and $t_{2}=1.5$  

$$
d_{1}(t_{1})=\frac{\ln(1600/1500)+0.2^{2}\times0.5/2}{0.2\sqrt{0.5}}=0.5271
$$  

$$
d_{2}(t_{1})=d_{1}-0.2{\sqrt{0.5}}=0.3856
$$  

so that  

$$
\nu_{1}=e^{-0.05\times2.0}\times(1-0.3)[1600N(0.5271)-1500N(0.3856)]=92.67
$$  

Similarly $\nu_{2}=130.65$  

The expected cost of defaults is  

$$
q_{1}\nu_{1}+q_{2}\nu_{2}=0.02\times92.67+0.03\times130.65=5.77
$$  

The no-default value of the forward contract is $(1600-1500)e^{-0.05\times2}=90.48$ When counterparty defaults are considered, the value drops to. $90.48-5.77=$ 84.71. The calculation can be extended to allow the times when the mining. company can default to be more frequent (see Problem 24.28). DVA, which increases the value of the derivative, can be calculated in a similar way to CVA (see Problem 24.29).  
