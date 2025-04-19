---
tags:
  - call_option
  - forwards
  - options
  - put_call_parity
  - put_option
  - risk_sharing
  - strike_price
aliases:
  - Forward Synthesis
  - Off-Market Forward
  - Options and Forwards
  - Put-Call Parity
key_concepts:
  - Call and Put Payoffs
  - Cash vs Physical Settlement
  - Cost-of-Carry Equation
  - Long Forward Strategy
  - Put-Call Parity Formula
  - Synthesizing Forwards
---

# 5.4 OPTIONS AND FORWARDS, RISK SHARING AND PUT-CALL PARITY  

Suppose we buy a call and sell a put on the same asset. Suppose that we also search among all possible strike prices and find one strike price, $K$ , such that the premium on the call struck at $K$ that we buy is exactly paid for by the premium on the put struck at $K$ that we sell. Let us examine the payoff of our strategy at expiry for physical-settle options.  

If $S\geq K$ , then the call option is in-the-money and we buy the stock for the amount. $K$ If $S\leq K$ , then the put option is in-the-money. We are exercised against, and we buy the. stock for the amount $K$ . By buying the call and selling the put, we are in effect agreeing to. buy the stock for the amount. $K$ on the expiry date. In a cash settle case, this means that no. matter whether the stock price is above or below the strike price, our payoff is $S-K$ on the. expiry date.  

Our strategy is equivalent to entering a long forward on the stock. Net, we pay nothing today, and on a future date we deliver the sum of money. $K$ for one share of the stock. The. forward is on-market (zero PV up front)..  

If we were slightly less careful in our search for the perfect strike, and instead picked one at random, but made sure that the strike on the long call is the same as the strike on the short put, then we would have in effect entered into an off-market forward with the markto-market value (PV) equal to the difference between the premium on the call and that on the put:  

$$
C a l l-P u t=F o r w a r d
$$  

One can think of the forward value of the stock as the median separating two possibility regions for the future stock price. The long call covers the part of the region to the right of the strike, i.e. with stock values greater than the strike. The short put covers that part of the region to the left of the strike, i.e. with stock values lower than the strike. Traders can synthesize forwards from options, or they can enter into forwards and synthesize options by selling off the undesirable probability regions. For example to synthesize a call, a dealer may enter into a forward and buy a put to offset the short put implicit in the forward. To synthesize a put, a dealer may enter into a short forward and buy a call to offset the short call implicit in the short forward.  

The relationship of call and put prices to the value of the forward is known as put-call parity. It takes the following form for options on non-dividend-paying stocks:.  

# Put-Call Parity  

$$
C-P=S-P V(K)
$$  

The left-hand side is the cost of the long call-short put strategy. $C$ is the price of the call with strike $K;P$ is the price of the put with strike $K$ . The right-hand side is the mark-to-market $(P V)$ of the forward contract. The forward contract to buy the stock for price $K$ can be replicated by borrowing the present value of $K$ and buying the stock now for the price $S$ If $K$ is low, the contract to buy the stock for $K$ at a forward date is valuable and $S-P V(K)>0$ This also means that calls cost more than puts for low strikes. If $K$ is high, the contract to buy the stock for $K$ at a forward date is not desirable and $S-P V(K)<0.$ This also means that calls cost less than puts for high strikes.  

There is a strike at which the prices of calls and puts must be the same, and that strike is given by the equation  

$$
S=P V(K)
$$  

This is the cost-of-carry equation in disguise. If we use the discrete form of discounting over 1 year with annual interest rate. $r$ , then the equation becomes:.  

$$
S=\frac{K^{*}}{1+r}
$$  

The strike at which calls and puts are equally valuable is equal to the forward price of the stock. Someone should be willing to agree today to sell you a stock worth $S=\$100$ today for $K^{*}=\$104$ if the financing rate is. $r=4\%$ . That is because they can borrow $\$100$ at $4\%$ and use the money to buy the stock now; in 1 year they have to repay $\$104$ . The put-call parity states that the long call-short put strategy is another way to replicate a forward at no cost, therefore a call struck at $\$104$ and a put struck at. $\$104$ must cost the same. If you buy the call and sell the put, you guarantee yourself a $\$104$ purchase price for the stock in. 1 year's time.  

The put-call parity reflects an advanced way of risk arbitrage. The prices of calls and puts (for all strikes) have to be in line with on- and off-market forward and futures. The arbitrage is executable by combining futures and options on the same underlying asset and choosing to buy the side that is cheaper relative to the other.  

This is also an advanced way of broader risk sharing. When a stock is bought in an Initial Public Offering (IPO) providing capital to a growing business, the buyer may not think much. of options and forwards. He does, however, appreciate the existence of a secondary market for stocks (stock exchange), so that he can sell the stock when he no longer wants to bear its. risk. The person he sells to may, however, be an option player who wants the stock, but only for a certain amount of time or only in a certain scenario. The fact that he can customize his participation in the stock may be the main reason that he purchases the stock. He does not buy another stock that does not have options trading on it, because that would force him into an all-or-nothing risk.  
