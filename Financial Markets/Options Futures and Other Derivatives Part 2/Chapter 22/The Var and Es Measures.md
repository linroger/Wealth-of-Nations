# 22.1 THE VaR AND ES MEASURES  

When using the value-at-risk measure, an analyst is interested in making a statement of the following form: "I am. $X$ percent certain there will not be a loss of more than $V$ dollars in the next $N$ days." The variable $V$ is the VaR of the portfolio. It is a function of two parameters: the time horizon (. $N$ days) and the confidence level. $(X\%)$ . It is the loss level over $N$ days that has a probability of only. $(100-X)\%$ of being exceeded.  

Bank regulators have traditionally required banks to calculate VaR for market risk with $N=10$ and $X=99$ (see the discussion in Business Snapshot 22.1). If VaR with these parameters is $\$20$ million for a bank, it is $99\%$ certain that it will not lose more thane $\$20$ million over the next 10 days. The 99th percentile of the 10-day loss distribution is $\$20$ million. Alternatively we can say that the first percentile of the gain distribution is. $-\$20$ million. VaR is illustrated in Figures 22.1 and 22.2.  

# Business Snapshot 22.1 How Bank Regulators Use VaR  

The Basel Committee on Bank Supervision is a committee of the world's bank regulators that meets regularly in Basel, Switzerland. In 1988 it published what has become known as Basel I. This is an agreement between the regulators on how the capital a bank is required to hold for credit risk should be calculated. Later the Basel Committee published The 1996 Amendment which was implemented in 1998 and required banks to hold capital for market risk as well as credit risk. The Amendment distinguishes between a bank's trading book and its banking book. The banking book consists primarily of loans and is not usually revalued on a regular basis for managerial and accounting purposes. The trading book consists of the myriad of different instruments that are traded by the bank (stocks, bonds, swaps, forward contracts, options, etc.) and is normally revalued daily.  

The 1996 Amendment calculates capital for the trading book using the VaR. measure with $N=10$ and $X=99$ This means that it focuses on the revaluation loss over a 10-day period that is expected to be exceeded only. $1\%$ of the time. The capital the bank is required to hold is $k$ times this $\mathrm{VaR}$ measure (with an adjustment for what are termed specific risks). The multiplier $k$ is chosen on a bank-by-bank basis by the regulators and must be at least 3.0. For a bank with excellent well-tested VaR estimation procedures, it is likely that $k$ will be set equal to the minimum value of 3.0. For other banks it may be higher.  

Basel I has been followed by Basel II, Basel II.5, Basel III, and Basel IV. Basel II (which was implemented in most parts of the world in about 2007) uses VaR with a one-year time horizon and a $99.9\%$ confidence level for calculating capital for credit risk and operational risk. Basel II.5 (which was implemented in 2012) revised the way. market risk capital is calculated. One of the changes involves what is known as stressed VaR. This is a VaR measure based on how market variables have moved during a particularly adverse time period. Basel III increased the amount of capital. that banks are required to hold and the proportion of that capital that must be equity. BaselIVincludesthe Fundamental Review ofthe Trading Book, whichinvolves. basing the capital for market risk on expected shortfall with a $97.5\%$ confidence level rather than VaR with a $99\%$ confidence level. Basel IV also limits the extent to which banks can use internal models for calculating required capital..  

VaR is an attractive measure because it is easy to understand. In essence, it asks the simple question "How bad can things get? This is the question all senior managers want answered. They are very comfortable with the idea of compressing all the Greek letters for all the market variables underlying a portfolio into a single number.  

If we accept that it is useful to have a single number to describe the risk of a portfolio, an interesting question is whether VaR is the best alternative. Some researchers have argued that VaR may tempt traders to choose a portfolio with a return distribution similar to that in Figure 22.2. The portfolios in Figures 22.1 and 22.2 have the same VaR, but the portfolio in Figure 22.2 is much riskier because big losses are more likely.  

![](images/1789fcf8b5e9d2395b8b09d9a17d12b4c3ff17680f20fba1680cb39414b1c23d.jpg)  
Figure 22.1 Calculation of VaR from the probability distribution of the change in the portfolio value; confidence level is $X\%$ . Gains in portfolio value are positive; losses are negative.  

![](images/7d61fad544484a2b68c1d3c7aad8121c25081f3abe32c7f18bee11ecf9be5f17.jpg)  
Figure 22.2 Alternative situation to Figure 22.1. VaR is the same, but the potential loss is larger.  

A measure that deals with the problem we have just mentioned is expected shortfall (ES).1 VaR asks the question: "How bad can things get?" ES asks: "If things do get bad, how much can the company expect to lose?" ES is the expected loss during an $N$ day period conditional on the loss being worse than the VaR loss. For example, with $X=99$ and $N=10$ , the expected shortfall is the average amount the company loses over a 10-day period when the loss is worse than the 10-day $99\%$ VaR. As mentioned in Business Snapshot 22.1, bank regulation is changing so that the capital for market risk is based on ES, not VaR. The confidence level is changing from $99\%$ to $97.5\%$  

# The Time Horizon  

VaR and ES each have two parameters: the time horizon $N$ , measured in days, and the confidence level $X.$ In practice, analysts often set $N=1$ in the first instance when VaR or ES is estimated for market risk. This is because there is not usually enough data  

available to estimate directly the behavior of market variables over periods of time longer than 1 day. The usual assumptions are.  

$$
\begin{array}{c}{N\mathrm{-}\mathrm{day}\mathrm{VaR}=1\mathrm{-}\mathrm{day}\mathrm{VaR}\times\sqrt{N}}\ {N\mathrm{-}\mathrm{day}\mathrm{ES}=1\mathrm{-}\mathrm{day}\mathrm{ES}\times\sqrt{N}}\end{array}
$$  

These formulas are exactly true when the changes in the value of the portfolio on successive days have independent identical normal distributions with mean zero. In other cases they are approximations.  
