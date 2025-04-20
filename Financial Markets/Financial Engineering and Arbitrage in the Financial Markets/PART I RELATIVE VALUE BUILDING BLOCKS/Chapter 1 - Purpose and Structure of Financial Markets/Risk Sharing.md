---
tags:
  - american_option
  - financial_contracts
  - insurance_contract
  - risk_sharing
  - state_contingent_claims
aliases:
  - Insurance Contracts
  - Risk Sharing
  - State-contingent claims
key_concepts:
  - Call option as subset
  - Financial contracts as bundles
  - Forward contract example
  - Insurance contract illustration
  - State-contingent claims defined
  - Stock as claims package
---

# 1.2 RISK SHARING  

All financial contracts, whether in the form of securities or not, can be viewed as bundles, or packages of unit payoff claims (mini-contracts), each for a specific date in the future and a specific set of outcomes. In financial economics, these are called state-contingent claims.  

Let us start with the simplest illustration: an insurance contract. A 1-year life insurance. policy promising to pay $\$1,000,000$ in the event of the insured's death can be viewed as a package of 12 monthly claims (lottery tickets), each paying $\$1,000,000$ if the holder dies during that month. The value of the policy up front (the premium) is equal to the sum of. the values of all the individual tickets. As the holder of the policy goes through the year, he can discard tickets that did not pay off, and the value of the policy to him diminishes until it reaches zero at the end of the coverage period.  

Let us apply the concept of state-contingent claims to known securities. Suppose you buy. one share of XYZ SA stock currently trading at. $\notin45$ per share and pays no dividends. You intend to hold the share for 2 years. To simplify things, we assume that the stock trades once a. month and in increments of $\displaystyle\varepsilon_{1}$ . The minimum price is $\in0$ (a limited liability company cannot have a negative value) and the maximum price is $\epsilon_{199}$ . The share of XYZ SA can be viewed as a package of claims. Each claim represents a contingent cash flow from selling the share for a particular price in a particular month in the future. Only one of those claims will ever pay, say when we sell the stock for. $\mathsf{\varepsilon}{}^{78}$ in month 16. We can arrange the potential price levels from $\in0$ to $\epsilon_{199}$ in increments of $\displaystyle\varepsilon_{1}$ to have overall 200 possible price levels. We arrange the dates from today to 24 months from today (our holding horizon). The stock is equivalent to 200 times 24, or 480 claims. The easiest way to imagine this set of claims is as a rectangle with time on the horizontal axis and potential stock prices (states of nature) on the vertical axis. The price of the stock today is equal to the sum of the values of all the claims, i.e. all the state- and time-indexed squares of the rectangle.  

![](e6ae1aa48ec4f0f2e893ad3d0b8a8a023fc1b38598df2bf729eadd09f0071b05.jpg)  
Figure 1.1 Stock and forward as packages of state-contingent claims  

Figure 1.1 shows the stock as a rectangle of 480 state-contingent claims. It also shows a forward contract on XYZ SA's stock viewed as a subset of this rectangle. Suppose we enter into a contract today to purchase the stock 13 months from today for $\yen60$ . The forward can be viewed as a 200-by-24 rectangle with the first 12 months' worth of claims taken out (equal to zero, as no action can be taken). If, in month 13, the stock trades above $\yen60$ , we have a gain; if the stock trades below $\yen60$ , we have a loss equal to the difference between the actual stock. price and the precontracted forward price.  

Figure 1.2 shows a long American call option contract to buy XYZ SA's shares for. $\notin60$ with an expiry 2 years from today as a. $139\times24$ subset of our original rectangle, the rest zeroed. out. The squares corresponding to the stock prices of $\yen60$ or below are eliminated, because they have no value. The payoff of each claim is equal to the intrinsic (exercise) value of the call. Figure 1.2 also shows a short American put struck at. $\yen60$ with an expiry in 12 months..  

The fundamental tenet of the option valuation methodology which applies to all securities is that if we can value each claim (one square of the rectangle) or small sets of claims (sections of the rectangle) in the package, then we can value the package as a whole sum of its parts.  

![](b5f6a50e0062eccaffbde36f89f587c91ee140b89212cc55ad815422c2cefc84.jpg)  
Figure 1.2 Long American call and short American put as packages of state-contingent claims.aims  

Conversely, if we can value the package, then we are able to value subsets of claims through a subtraction of the whole minus a complement subset. Also, we may be able to combine disparate (dependent on different state variables) sets of claims (stocks on equity prices and bonds on interest rates) to form complex securities (a convertible bond). By subtracting one part (option) from the value of the combination (convertible bond), we can infer the value of a subset (straight bullet bond).  

In general, the value of a contingent claim does not stay constant over time. If the holder of the life insurance becomes sick during the year and the likelihood of his death increases, then the value of all claims increases. In our stock example, the prices of the claims change as information about the company's earnings reaches the market. Not all the claims in the package have to change in value by the same amount, however. An improvement in the earnings may be only short term. The policyholder's likelihood of death may increase for the days immediately following his illness, but be less for more distant dates. As the prices of the individual claims fluctuate over time, so does the value of the entire bundle. However, at any given moment of time, the sum of the values of the claims must be equal to the value of the package, the insurance policy, or the stock. The valuation effort is restricted to here and now, and we have to repeat the exercise an instant later.  

A good valuation model strives to make the claims in a package independent of each other. In our example, the payoff of the life insurance policy depends on the person dying during the month, not on whether the person is dead or alive. In that set-up, at most one claim of the whole set will pay. If we modeled the payoff to depend on being dead and not dying, all the claims after the morbid event would have positive prices and be contingent on each other. Sometimes, even with the best of efforts, it may be impossible to model the claims in a package as independent. If a payoff at a later date depends on whether the stock reached some level at an earlier date, the later claim's value depends on the prior one. A mortgage. bond's payoff at a later date depends on whether the mortgage has not already prepaid. This. is referred to as a survival or path-dependence problem. As our imaginary two-dimensional rectangles cannot handle path dependence; we ignore this dimension of risk throughout the book as it adds very little to our discussion and can usually be handled by models..  

Let us turn to the definition of risk sharing.  

Definition Risk sharing is a purchase or a sale, explicit or through a side contract, of all or some of the state-contingent claims in the package to another party.  

In real life, risk sharing takes many forms. The owner of the XYZ share may decide to sell a covered call on the stock (see Chapter 5). If he sells a 2-year American call struck at $\yen60$ , and gives the buyer the right to purchase the share at $\yen60$ from him even if XYZ trades higher in the market, the covered call seller is capping his stock-cum-option payoff at $\yen60$ in exchange for an up-front option premium that he receives. This corresponds to exchanging the squares corresponding to price levels above $\yen60$ for squares with a flat payoff of $\yen60$ , or to subtracting, one-by-one, the payoffs in the American call package in Figure 1.2 from all the state-contingent claim payoffs in the stock package in Figure 1.1. This illustrates the important risk-sharing role of options in financial markets. Stockholders can buy or sell off parts of their holdings, and others can acquire subsets of the entire stock risk.  

Another example of risk sharing is the hedge of a corporate bond with a risk-free government bond. A hedge is a sale of a package of state-contingent claims against a primary position, which eliminates all the risk of that position coming from one state variable. The sale of. a security that is identical to the primary position is the only transaction that can eliminate. all the risk. A hedge always leaves some risk unhedged! When a trader purchases a 10-year $5\%$ coupon bond issued by XYZ Corp. and, in an effort to eliminate interest rate risk he simultaneously shorts a 10-year $4.5\%$ coupon government bond -- duration-matching the size of the short -- he guarantees that for small parallel movements in the interest rates, the changes in the values of the two bonds are identical, but opposite in sign. If interest rates rise, the loss on the corporate bond holding will be offset by the gain on the short government bond. If interest. rates decline, the gain on the corporate bond will be offset by the loss on the government bond. However, as explained in Chapters 2 and 7, the second state variable credit spread is completely unhedged. In fact, the trader speculates that the credit spread on the corporate bond declines. Irrespective of whether interest rates rise or fall, the trader gains if ever the. XYZ credit spread declines since the corporate bond's price will go up more, or go down less, than that of the government bond. It is only when the credit standing of XYZ worsens and the spread rises, that the trader will suffer a loss. The corporate bond is exposed over time to two dimensions of risk: interest rates and corporate spread. In the state-contingent claim sense, the corporate bond would be represented by a large rectangular cube with time, interest rate, and credit spread as dimensions. The government bond hedge eliminates all potential payoffs along the interest rate axis, reducing the cube to a plane, with only time and credit spread as dimensions.  

Almost any hedge or relative value arbitrage position discussed in this book can be thought of in the context of a multidimensional cube defined by time and risk state-variable axes. The hedge eliminates a dimension or a subspace from the cube.  
