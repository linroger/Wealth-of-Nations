---
tags:
  - arbitrage_pricing
  - bond_prices
  - call_option
  - interest_rate_derivatives
  - law_of_one_price
  - replicating_portfolio
aliases:
  - Arbitrage
  - Derivatives
  - Pricing
key_concepts:
  - Arbitrage opportunity
  - Bond price dependence
  - Call option pricing
  - Interest rate contingent claim
  - Replicating portfolio value
---

# 7.2 ARBITRAGE PRICING OF DERIVATIVES  

This section prices an interest rate contingent claim or derivative, in particular, a call option that expires in six months to purchase $\$1,000$ face value of a then six-month zero at $\$990$ . Figure 7.2 starts the price tree for this call option based on the rates and prices in Figure 7.1. If on date 1 the six-month rate is $2.50\%$ , and a six-month zero sells for $\$987.654$ , the right to buy that zero at $\$990$ is worthless. On the other hand, if the six-month rate is $1.50\%$ , and the price of a six-month zero is $\$992.556$ , then the right to buy the zero at $\$990$ is worth $\$992.556-\$9990$ , or $\$2.556$ . This description of the option's terminal payoffs emphasizes the contingent claim nature of the option: its value depends on interest rates through the value of an underlying bond.  

![](a43fa1d520f560d699698b4262b58beb1da668723a80f9a323382bdfc3c4fab2.jpg)  
FIGURE 7.2 Pricing a 990 Six-Month Call Option on a Six-Month Zero Coupon Bond.  

Chapter 1 showed that a security is priced by arbitrage by finding and. pricing its replicating portfolio. In that context, because all bond cash flows are fixed or constant, the construction of the replicating portfolio is rela-. tively simple. The present context is more difficult, because cash flows do. depend on the level of rates, and the replicating portfolio must replicate the. contingent claim for any possible interest rate scenario..  

To price the call option of this section by arbitrage, construct a portfolio on date 0 of underlying securities, namely six-month and one-year zero coupon bonds, such that the portfolio is worth $\$0$ in the upstate on date 1. and $\$2.556$ in the downstate. Let. $F^{.5}$ and $F^{1}$ be the face values of six-month. and one-year zeros in this replicating portfolio, respectively, and recall that the possible values of these bonds on date 1 are shown in Figure 7.1. These face amounts, therefore, must satisfy the following two equations,  

$$
\begin{array}{l}{{F^{.5}+.987654F^{1}=\S0}}\ {{}}\ {{F^{.5}+.992556F^{1}=\S2.558}}\end{array}
$$  

Equation (7.3) may be interpreted as follows. In the upstate, the value of the replicating portfolio's now maturing six-month zero is its face value.. The value of the once one-year zeros, now six-month zeros, is .987654 per dollar face value. Hence, the left-hand side of Equation (7.3) denotes the value of the replicating portfolio in the upstate. This value must equal. $\$0$ the value of the option in the upstate. Similarly, Equation (7.4) sets the value of the replicating portfolio in the downstate equal to the value of the option in the downstate.  

Solving Equations (7.3) and (7.4) gives $F^{.5}=-\$515.0000$ and $F^{1}=\$521.4375$ . In words, the option can be replicated by buying $\$521.4375$ face value of one-year zeros and shorting $\$515.0000$ face amount of six-month zeros on date O. Therefore, by the law of one price, the price of the option equals the price of the replicating portfolio, which, using the bond prices given earlier, is equal to,  

$$
\begin{array}{r l r}{990099F^{5}+.978842F^{1}=-.990099\times\S515.0000+.978842\times\S521.4375}&{{}}&{}\ {=\S0.504}&{{}}&{}&{{}(7.5)}\end{array}
$$  

Recall that pricing based on the law of one price is enforced by arbitrage. If the price of the option were less than. $\$0.504$ , arbitrageurs could buy the option, short the replicating portfolio, keep the difference, and have no future liabilities. Similarly, if the price of the option were greater than $\$0.504$ , arbitrageurs could short the option, buy the replicating portfolio,. keep the difference, and, once again, have no future liabilities. Thus, ruling out profits from riskless arbitrage implies an option price of. $\$0.504$  

It is important to emphasize that the option cannot be priced by expected discounted value, which gives an option price of,  

$$
{\frac{.5\times\S0+.5\times\S2.555831}{1+{\frac{.02}{2}}}}=\S1.2653
$$  

The true option price is lower, because investors dislike the risk of the call option and, as a result, will not pay as much as its expected discounted value. Put another way, the risk penalty implicit in the call option price is. inherited from the risk penalty of the one-year zero, that is, from the property. that the price of the one-year zero is less than its expected discounted value.. Once again, the pricing of risk is discussed in the next two chapters. While. this section illustrates arbitrage pricing with a call option, it should be clear. that the framework can be used to price any security with cash flows that ultimately depend on the six-month rate. For example, because the price of. a five-year bond over time depends on the evolution of the six-month rate,. an option on that five-year bond can be priced in this framework as well.  

A remarkable feature of arbitrage pricing is that the probabilities of upand down-moves never enter into the calculation of the arbitrage price. See. Equations (7.3) through (7.5). The explanation for this somewhat surprising. result follows from the principles of arbitrage. Arbitrage pricing requires. that the value of the replicating portfolio be the same as the value of the option in both the up- and the down-states. Therefore, the composition of the replicating portfolio is the same whether the probability of the upstate is $20\%$ $50\%$ , or $80\%$ . But if the composition of the portfolio does not. depend directly on the probabilities, and if the prices of the securities in the portfolio are given, then the price of the replicating portfolio and the price of the option cannot depend directly on the probabilities either..  

Despite the fact that the option price does not depend directly on the probabilities, these probabilities must have some impact on the option price. After all, as it becomes more and more likely that rates will rise to $2.50\%$ and that bond prices will be low, the value of options to purchase bonds must fall. The resolution of this apparent paradox is that the option price depends indirectly on the probabilities through the price of the one-year zero. Were the probability of an up move to increase suddenly, the current value of a one-year zero would decline. And since the replicating portfolio is long one-year zeros, the value of the option would decline as well. In summary, a. derivative like an option depends on the probabilities only through current bond prices. Given bond prices, however, probabilities are not needed to. derive prices determined by arbitrage.  
