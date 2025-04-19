---
tags:
  - delivery_price
  - forward_contracts
  - marking_to_market
  - risk_free_rate
  - valuation
aliases:
  - Forward Contract Valuation
  - Valuation of Forwards
key_concepts:
  - Delivery price
  - Forward contract value
  - Long forward contract
  - Marking to market
  - Risk-free interest rate
---

# 5.7 VALUING FORWARD CONTRACTS  

The value of a forward contract at the time it is first entered into is close to zero. At a later stage, it may prove to have a positive or negative value. It is important for banks and other financial institutions to value the contract each day. (This is referred to as marking to market the contract.) Using the notation introduced earlier, we suppose $K$ is the delivery price for a contract that was negotiated some time ago, the delivery date is $T$ years from today, and. $r$ is the $T$ -year risk-free interest rate. The variable $F_{0}$ is the forward price that would be applicable if we negotiated the contract today. In addition, we define $f$ to be the value of forward contract today.  

It is important to be clear about the meaning of the variables. $F_{0},K$ , and $f.$ At the beginning of the life of the forward contract, the delivery price,. $K$ , is set equal to the. forward price at that time and the value of the contract, $f,$ is 0. As time passes, $K$ stays the same (because it is part of the definition of the contract), but the forward price changes and the value of the contract becomes either positive or negative..  

A general result, applicable to all long forward contracts (both those on investment assets and those on consumption assets), is.  

$$
f=(F_{0}-K)e^{-r T}
$$  

To see why equation (5.4) is correct, we form a portfolio today consisting of (a) a. forward contract to buy the underlying asset for $K$ at time $T$ and (b) a forward contract to sell the asset for. $F_{0}$ at time $T$ The payoff from the portfolio at time $T$ is $S_{T}-K$ from the first contract and. $F_{0}-S_{T}$ from the second contract. The total payoff is $F_{0}-K$ and is known for certain today. The portfolio is therefore a risk-free investment and its value. today is the payoff at time $T$ discounted at the risk-free rate or $(F_{0}-K)e^{-r T}.$ The value of the forward contract to sell the asset for $F_{0}$ is worth zero because $F_{0}$ is the forward. price that applies to a forward contract entered into today. It follows that the value of a (long) forward contract to buy an asset for $K$ at time $T$ must be $(F_{0}-K)e^{-r T}.$ Similarly, the value of a (short) forward contract to sell the asset for. $K$ at time $T$ is $(K-\mathfrak{F}_{0})e^{-r\bar{T}}$  

# Example 5.4  

A long forward contract on a non-dividend-paying stock was entered into some time ago. It currently has 6 months to maturity. The risk-free rate of interest (with continuous compounding) is $10\%$ per annum, the stock price is $\$25$ , and the delivery price is $\$24$ In this case, $S_{0}=25,r=0.10,T=0.5$ , and $K=24.$ From equation (5.1), the 6-month forward price, $F_{0}$ , is given by  

$$
F_{0}=25e^{0.1\times0.5}=\S26.28
$$  

From equation (5.4), the value of the forward contract is  

$$
f=(26.28-24)e^{-0.1\times0.5}=\S2.17
$$  

Equation (5.4) shows that we can value a long forward contract on an asset by making. the assumption that the price of the asset at the maturity of the forward contract equals the forward price. $F_{0}$ . To see this, note that when we make that assumption, a long. forward contract provides a payoff at time $T$ of $F_{0}-K$ . This has a present value of. $(F_{0}-K)e^{-r T}$ , which is the value of. $f$ in equation (5.4). Similarly, we can value a short. forward contract on the asset by assuming that the current forward price of the asset is  

# Business Snapshot 5.2 A Systems Error?  

A foreign exchange trader working for a bank enters into a long forward contract to buy 1 million pounds sterling at an exchange rate of 1.5000 in 3 months. At the same. time, another trader on the next desk takes a long position in 16 contracts for. 3-month futures on sterling. The futures price is 1.5000 and each contract is on. 62,500 pounds. The positions taken by the forward and futures traders are therefore the same. Within minutes of the positions being taken, the forward and the futures prices both increase to 1.5040. The bank's systems show that the futures trader has. made a profit of $\$4,000$ , while the forward trader has made a profit of only $\$3,900$ --- The forward trader immediately calls the bank's systems department to complain.. Does the forward trader have a valid complaint?  

The answer is no! The daily settlement of futures contracts ensures that the futures trader realizes an almost immediate profit corresponding to the increase in the futures price. If the forward trader closed out the position by entering into a short contract at 1.5040, the forward trader would have contracted to buy 1 million pounds at 1.5000 in 3 months and sell 1 million pounds at 1.5040 in 3 months. This would lead to a $\$4,000$ profit-- but in 3 months, not today. The forward trader's profit is the present value of $\$4,000$ . This is consistent with equation (5.4).  

The forward trader can gain some consolation from the fact that gains and losses are treated symmetrically. If the forward/futures prices dropped to 1.4960 instead of rising to 1.5040, then the futures trader would take a loss of $\$4,000$ while the forward trader would take a loss of only $\$3,900$  

realized. These results are analogous to the result in Section 4.9 that we can value a forward rate agreement on the assumption that forward rates are realized.  

Using equation (5.4) in conjunction with equation (5.1) gives the following expression for the value of a forward contract on an investment asset that provides no income  

$$
f=S_{0}-K e^{-r T}
$$  

Similarly, using equation (5.4) in conjunction with equation (5.2) gives the following expression for the value of a long forward contract on an investment asset that provides a known income with present value $I$  

$$
f=S_{0}-I-K e^{-r T}
$$  

Finally, using equation (5.4) in conjunction with equation (5.3) gives the following. expression for the value of a long forward contract on an investment asset that provides a known yield at rate $q$  

$$
f=S_{0}e^{-q T}-K e^{-r T}
$$  

When a futures price changes, the gain or loss on a futures contract is calculated as. the change in the futures price multiplied by the size of the position. This gain is. realized almost immediately because futures contracts are settled daily. Equation (5.4) shows that, when a forward price changes, the gain or loss is the present value of the change in the forward price multiplied by the size of the position. The difference between the gain/loss on forward and futures contracts can cause confusion on a. foreign exchange trading desk (see Business Snapshot 5.2).  
