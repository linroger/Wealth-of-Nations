---
tags:
  - counterparty_risk
  - credit_risk
  - cva_dva
  - default_risk
  - derivative_valuation
  - risk_management
aliases:
  - CVA and DVA
  - Credit Valuation Adjustment
  - Debit Valuation Adjustment
key_concepts:
  - Counterparty default
  - Credit valuation adjustment
  - Early termination
  - Expected loss calculation
  - No-default value
---

# 9.1 CVA AND DVA  

Most of this book is concerned with determining the no-default value of derivatives, that is, the value assuming that neither of the two sides will default. CVA and DVA are adjustments to the no-default value reflecting the possibility of a default by one of the two sides. Here we provide an overview of them. More details on their calculation are in Chapter 24.  

Suppose that a bank and a counterparty have entered into a portfolio of derivative. transactions that are cleared bilaterally. The master agreement between the bank and the counterparty will almost certainly state that netting applies. This means that all outstanding derivatives between the two sides are considered as a single derivative in the. event of a default. When one party declares bankruptcy, fails to post collateral as required, or fails to perform as promised in some other way, the other party will declare. an event of default. This leads to an early termination of the outstanding derivatives between the bank and the counterparty a few days later and a settlement amount is calculated. The settlement amount reflects the value of the derivatives and is adjusted to allow for the fact that the nondefaulting party will incur costs equal to half the. applicable bid-ask spreads when replacing the transactions in the portfolio..  

Suppose that it is the bank's counterparty that defaults and neither side posts. collateral. (Later we explain the impact of collateral.) If the early termination happens. when the outstanding derivatives portfolio has a positive value to the bank and a. negative value to the counterparty, the bank will be an unsecured creditor for the settlement amount and is likely to incur a loss because it will fail to receive it in full. In the opposite situation, where the portfolio has a negative value to the bank and a. positive value to the counterparty, the settlement amount is owed by the bank to the counterparty (or to the counterparty's liquidators) and will be paid in full so that there is no loss.  

The credit valuation adjustment (CVA) is the bank's estimate of the present value of the expected cost to the bank of a counterparty default. Suppose that the life of the. longest outstanding derivatives transaction between the bank and the counterparty is $T$ years. To calculate CVA, the bank divides the next. $T$ years into a number of intervals. For each interval, it calculates:  

1. The probability of an early termination during the interval arising from a counterparty default; and   
2. The present value of the expected loss from the derivatives portfolio if there is an early termination at the midpoint of the interval.  

Suppose that there are $N$ intervals, $q_{i}$ is the probability of default by the counterparty. during the ith interval, and. $\nu_{i}$ is the present value of the expected loss if there is a default at the midpoint of the ith interval. CVA is calculated as:  

$$
\mathrm{CVA}=\sum_{i=1}^{N}q_{i}\nu_{i}
$$  

This formula is deceptively simple but the procedure for implementing it is quite complicated and computationally very time-consuming. It will be explained in Chapter 24.  

Define $f_{\mathrm{nd}}$ as the no-default value of the derivatives portfolio to the bank. As explained earlier, this is the value of the portfolio assuming that neither side will default. When the possibility of a counterparty default is taken into account, the value of the portfolio to the bank becomes  

$$
f_{\mathrm{nd}}\mathrm{~-~}\mathrm{CVA}
$$  

But this is not the end of the story. The bank itself might default. This is liable to lead to a loss to the counterparty and an equal and opposite gain to the bank. The debit (or. debt) valuation adjustment (DVA) is the present value of the expected gain to the bank. from the possibility that it might itself default. It is calculated similarly to CVA:.  

$$
\mathrm{{DVA}}=\sum_{i=1}^{N}q_{i}^{*}\nu_{i}^{*}
$$  

where $q_{i}^{*}$ is the probability of a default by the bank during the ith interval and. $\nu_{i}^{*}$ is the present value of the bank's gain (and the counterparty's loss) if the bank defaults at the. midpoint of the interval. Taking both CVA and DVA into account, the value of the portfolio to the bank is.  

$$
f_{\mathrm{nd}}-\mathrm{CVA}+\mathrm{DVA}
$$  

The idea that a bank will gain from its own default seems strange to many people. How can there be a gain from a default? One way of thinking about this is as follows. Derivatives are what are referred to as "zero-sum games." The gain to one side always equals the loss to the other side. If the bank's counterparty is worse off because of the possibility that the bank will default on the outstanding derivatives, the bank (or the bank's creditors) must be better off. The reason why this is so is that, in circumstances where it defaults, a bank avoids having to honor its contracts when the no-default value of those contracts to the bank is negative.  

Without DVA, it is liable to be difficult for derivatives transactions to be agreed to. Consider two market participants, $\boldsymbol{\mathrm X}$ and Y, who are negotiating a bilaterally cleared. interest rate swap where X will be paying a fixed rate of interest and receiving LIBOR with no collateral being posted. For the purposes of our example we assume that there are no other trades between these two parties.' The two sides agree that, if there is no default risk, the fixed rate should be $2.2\%$ . We suppose that, when X takes Y's default risk into account, it determines it should pay $2.1\%$ rather than $2.2\%$ . (The $0.1\%$ per annum reduction is compensation to X for possibility that Y might default.) But when Y takes X's default risk into account, it determines that it should receive. $2.35\%$ rather than $2.2\%$ . (The extra $0.15\%$ is compensation to $\mathrm{Y}$ for the possibility that X might default.) It is easy to see that the two sides are unlikely do a deal if each side considers only the possibility of the other side defaulting. But if each side calculates a DVA (recognizing that it might itself default), the two sides will have a better chance of doing. a deal because they will value the expected cash flows from the swap similarly..  

DVA has a counterintuitive effect. As the bank's creditworthiness declines,. $q_{i}^{*}$ in equation (9.2) increases and DVA increases. This makes the derivatives portfolio more valuable to the bank. As the bank's creditworthiness improves,. $q_{i}^{*}$ decreases and DVA decreases so that the portfolio is less valuable. Why should the bank gain from a worsening of its credit quality? The reason is that as the bank becomes more likely to default it is more likely that it will not have to honor its derivatives obligations..  

# Collateral  

When the agreement between the two parties requires collateral to be posted, the situation is more complicated. A credit support annex (CSA) to the master agreement specifies how the required amount of collateral is calculated and what form the collateral can take. Interest is normally paid on cash collateral at close to the fed funds rate or similar overnight rate. When the collateral takes the form of securities, a haircut is usually applied to the market value of the securities.  

If a bank's counterparty defaults, the bank is entitled to keep any collateral that has been posted by the counterparty if it is less than any settlement amount it is owed. Similarly, if the bank defaults, the counterparty can use any collateral posted by the bank to cover any settlement amount it is owed. Any collateral in excess of the settlement amount must be returned.  

Equations (9.1) and (9.2) are still correct when collateral is posted, but the calculation of $\nu_{i}$ and $\nu_{i}^{*}$ is more complicated. The calculation must take into account the collateral that would be provided by the bank to the counterparty or by the counterparty to the bank at the time of an early termination. Usually the calculation involves an assumption that the defaulting party will stop posting collateral, and will stop returning excess collateral, several days before the early termination. The number of days assumed here is known as the cure period or margin period of risk. For example, if the cure period is 10. days, the collateral at the time of the early termination would be assumed to be that specified in the CSA 10 days earlier..  
