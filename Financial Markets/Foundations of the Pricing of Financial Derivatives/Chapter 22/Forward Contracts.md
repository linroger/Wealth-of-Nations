---
tags:
  - expiration
  - forward_contracts
  - over_the_counter
  - pricing
  - valuation
aliases:
  - Forward Contract
  - Long Position
  - Short Position
key_concepts:
  - agreed forward price
  - agreement between two parties
  - buyer purchases asset
  - customizable agreements
  - firm commitment
---

# 22.1 FORWARD CONTRACTS

A forward contract is an agreement between two parties in which the buyer, or long, agrees. that at a future date, called the expiration, the buyer will purchase an asset from the seller, or short, at a price they agree on today. This price they agree on is called the forward. price. A forward contract is a firm commitment, which distinguishes it from an option. An option is a right, but not an obligation. The holder of the option can exercise it, but they. will not do so if market conditions are not favorable. In a forward contract, the future transaction that the two parties agree on will be executed for certain.1 No money changes. hands between the two parties when the contract is initiated. Thus, the contract is neither an asset nor a liability, and in fact, it has zero value at the start. When time elapses and the value of the underlying moves, value is created for one party and destroyed for the other.

Forward contracts are completely customizable agreements that are typically created in a dealer or over-the-counter market.2 That is, a financial institution acting as a dealer offers to take either a long or short position. As such, it quotes the price at which it would buy, called the bid, and the price at which it would sell, called the ask. Another company, called an end user, has a need for a forward contract, such as to lock in the purchase price of an asset it intends to buy in the future, and enters into the contract with the dealer. The end user specifies exactly what terms it wants, such as the identity of the underlying and the expiration date.

Many homes are purchased with forward contracts although typically not referenced. in this way. Usually a potential buyer will sign a contract to purchase a home and also. make a nonrefundable deposit. Assuming the seller meets all the contractual conditions, the buyer will purchase the home some time later at a closing meeting. The purchase terms. are given in the forward contract..

We now move into the heart of the analysis: the pricing and valuation of forward contracts.

# 22.1.1 Pricing and Valuing Forward Contracts

Note that the title of this section uses the words pricing and valuing. When talking about.
most assets, including options, we use the terms somewhat interchangeably, acknowledg-.
ing, however, that value is what something is worth and price is what someone pays. When markets are efficient and, therefore, process all relevant information, price equals value. In.
the world of forwards, futures, and swaps, however, price and value are entirely different.
concepts.

We start by assuming we are at time 0, at which time the underlying is at. $S_{0}$ . Two parties enter into a forward contract in which the buyer agrees that at the expiration, time. $T$ , it will pay an amount of money,. $F_{0}(T)$ , to the seller and receive the underlying asset. The. contract expires at time $T$ , and the time to expiration in years is. $\tau$ . The parameter $F_{0}(T)$ is called the forward price. It is the price that will be paid by the buyer to the seller at the expiration. Because by now you understand options reasonably well, it might be useful to think of $F_{0}(T)$ as the analog of the option exercise price. Hence, the forward price will be. on a similar order of magnitude to the value of the underlying, $S_{0}$ . But even though $F_{0}(T)$ is the forward price, it is not the value of the contract. You should think of value as the amount that would be paid by one party so that this party acquires the contract from the other. Let us denote the value of a forward contract as. $V_{t}\big[F_{0}(\bar{T})\big]$ , which means the value of the forward contract at an arbitrary time $t$ with the contract expiring at time $T$ in which the forward price is $F_{0}(T)$ . Let us first establish the principle that the value of the contract. at time zero is zero:

$$
V_{0}\big[F_{0}(T)\big]=0.
$$

This result is intuitive in that neither party pays the other any money at the start. We said that value is what one party pays to acquire something from another. With forward contracts, the two parties engage in the agreement, but neither pays any money to the other. Later we shall demonstrate a nonstandard circumstance in which value is not zero at time zero.

Next, let us establish the value of the contract at expiration, which is as follows:

$$
\begin{array}{r}{V_{T}\big[F_{0}(T)\big]=S_{T}-F_{0}(T).}\end{array}
$$

This result is determined by precisely what happens at expiration, at which time the buyer of the contract pays the price,. $F_{0}(T)$ , to the seller and receives the asset valued at $S_{T}$ Therefore, the value to the buyer is. $S_{T}-F_{0}(T)$ . Conversely, the value to the seller is. $-\left[S_{T}-F_{0}(T)\right]$ . Note that the payoff here is linear in the underlying, whereas with options, the payoff is nonlinear in the underlying.3 This linearity will make a huge difference in how we construct a risk-free hedge that will provide the option value. Linearity will, in fact, make the risk-free hedge for a forward contract be static, rather than dynamic, as it is for options.

Thus, forward pricing is a relatively simple matter, especially in comparison to option pricing. Suppose we sell a forward contract at price. $F_{0}(T)$ and simultaneously buy one unit. of the asset at price $S_{0}$ . At expiration, the short forward contract obligates us to deliver the asset and be paid $F_{0}(T)$ . So what will happen at expiration is simple. We will deliver the.

asset and be paid. $F_{0}(T)$ . Note how the value of the asset at expiration, $S_{T}$ , is irrelevant to. the payoff of the overall position of long the asset and short the forward contract. In fact, there is no risk to the overall position. The value at expiration of the position is $F_{0}(T)$ and being risk free, this value should be discounted to the present at the risk-free rate to equal the value of the initial position. The value of the initial position is the value of the asset, $S_{0}$ , minus the value of the forward contract, but the value of the forward contract is zero by Equation (22.1). Thus, the value of the asset at time 0, $S_{0}$ , must equal the forward. price discounted at the risk-free rate. Rearranging and solving for the forward price gives our forward pricing equation,

$$
F_{0}(T)=S_{0}(1+r)^{\tau},
$$

where $\tau$ is the time to expiration expressed as a fraction of a year. For forward contracts, this is the analog of the Black-Scholes-Merton equation. As you can see, it is much simpler. Now, let us consider the special case in which we create a forward contract an instant. before expiration. Then $\tau\rightarrow0$ , and the new forward price would be the spot price,

$$
F_{T}(T)=S_{T}(1+r)^{0}=S_{T}.
$$

Forward contracts are often written on assets that have costs associated with holding them, and these assets can also yield cash flows, such as dividends, or other benefits. Let $\gamma(0,T)$ be the value at time $T$ of any accumulated costs minus any accumulated benefits. Then Equation (22.3) becomes

$$
F_{0}(T)=S_{0}(1+r)^{\tau}+\gamma(0,T).
$$

Note that $\gamma(0,T)$ can be either positive or negative depending on whether the costs exceed the benefits or vice versa. Further, there are numerous ways to incorporate asset-related cash flows. We chose here to introduce them as simply an addition.

We have established the value of a forward contract at time O and the value at time $T.$ the expiration. What we now need is the value at some arbitrary evaluation time $t$ , sometime between times 0 and. $T.$ This result is only slightly more difficult to establish. Thus, now consider that we are at the evaluation time $t_{:}$ $0<t<T$ The forward contract price. was established at time 0 and set at $F_{0}(T)$ and is fixed. The spot price is $S_{t}$ The remaining time to expiration will be denoted. $\tau_{t}$ To determine the value of this forward contract, let us sell a new forward contract expiring at $T.$ This contract will have a new price,. $F_{t}(T)$ and a time to expiration of $\tau_{t}$ . Being long the original forward contract obligates us to buy the asset at time $T$ at price $F_{0}(T)$ , and being short a new forward contract obligates us to sell the asset at time. $T$ at price $F_{t}(T)$ . The overall position is risk-free in that the value of the underlying at time. $T$ will have no relevance to us. We will buy the asset at $F_{0}(T)$ and sell it at $F_{t}(T)$ . Thus, we are guaranteed that at time $T$ we will have a cash flow of $F_{t}(T)-F_{0}(T)$ , an amount that is known at time. $t.$ The present value from $T$ to $t$ equals the value of our overall position at time $t$ Our overall position at time $t$ is the value of the long position in the original forward contract minus the value of the new forward contract that we are short. But the value of the new forward contract at $t$ is zero, because it is a newly established contract and, therefore, has a value of zero. Thus, the value of the original contract at. $t$ is

$$
V_{t}\big[F_{0}(T)\big]=\frac{F_{t}(T)-F_{0}(T)}{(1+r)^{\tau_{t}}}.
$$

IABLE 22.1 Cash Flows for Long Forward Valuation


<html><body><table><tr><td>Strategy</td><td>Cash Flow at Time 0</td><td>Value at Time t</td><td>Cash Flow at Time T</td></tr><tr><td>Buy forward Fo(T)</td><td></td><td>V,(T)</td><td>Vr[Fo(T)] = ST -Fo(T)</td></tr><tr><td>Sell forward F(T)</td><td>NA</td><td>0</td><td>V[F,(T)] = F,(T) - ST</td></tr><tr><td>NetCashFlow/Value</td><td></td><td>V,(T)</td><td>F,(T) -Fo(T)</td></tr></table></body></html>

Note: NA indicates sell forward at time $t$ does not exist.

Table 22.1 illustrates the cash flows at the three relevant times: the initial trade date, $(\tau=0)$ , the evaluation date, $t.$ and the expiration date, $T.$ Adapting Equation (22.5) for the condition at time $t$ instead of time 0, we have the price of the new forward contract as

$$
F_{t}(T)=S_{t}(1+r)^{\tau_{t}}.
$$

Using this result in Equation (22.6), we can then restate the value equation as

$$
V_{t}\big[F_{0}(T)\big]=S_{t}-\frac{F_{0}(T)}{(1+r)^{\tau_{t}}}.
$$

Or essentially, the current spot price minus the present value of the original forward price. Note that if we set $t=0$ or $t=T$ in Equation (22.7), we obtain Equations (22.1) and (22.2):

$$
\begin{array}{r l}&{t=0:V_{0}\big[F_{0}(T)\big]=S_{0}-F_{0}(T)\big/(1+r)^{\tau}=S_{0}-S_{0}=0}\ &{t=T:V_{T}\big[F_{0}(T)\big]=S_{T}-F_{0}(T)\big/(1+r)^{0}=S_{T}-F_{0}(T).}\end{array}
$$

For example, assume at time O a one-year forward contract was entered at $\$25$ You have been tasked with determining the fair value of this contract after nine months. (time $t$ ). At time $t$ , we know the underlying instrument priced is $\$26$ and the interest rate is $3.902\%$ (annual compounding). In this case we know the price of a new forward contract is

$$
F_{t}(T)=S_{t}(1+r)^{\tau_{t}}=26(1+0.03902)^{0.25}=26.25.
$$

Further, the value of the initial long forward contract at time $t$ is

$$
V_{t}\big[F_{0}(T)\big]=\frac{F_{t}(T)-F_{0}(T)}{(1+r)^{\tau_{t}}}=\frac{26.25-25}{(1+0.03902)^{0.25}}=\S1.238.
$$

Note that the contract, which had a zero value nine months earlier, is now worth a positive. value. Intuitively, its value has increased because it is the obligation to buy an asset that has since increased in value..

# 22.1.2 Forward Contracts and Options

Now, let us tie forward contracts back to options. First, note that because a long position in the asset, hedged with a short forward contract, can create a riskless position or essentially a risk-free bond, it follows that a position in the asset can be replicated by a long position in a forward contract and a long position in a risk-free bond. Recall that put-call parity states that

$$
p_{0}+S_{0}=c_{0}+\frac{X}{\left(1+r\right)^{\tau}}.
$$

Given Equation (22.3), we can substitute into put-call parity for $S_{0}$ and obtain

$$
p_{0}+\frac{F_{0}(T)}{\left(1+r\right)^{\tau}}=c_{0}+\frac{X}{\left(1+r\right)^{\tau}}.
$$

As such, Equation (22.10) expresses the relationships among the put price, the call. price, the option exercise price, and the forward price. Note that because we are free to choose the exercise price of the options, we could set the exercise price to the forward price. Then $F_{0}(T)=X$ , and from Equation (22.10), we would have the put and call prices. equal to each other.

# 22.1.3 Some Additional Facts on Forward Contracts

Finally, let us learn a few more important facts about forward contract pricing. We have. said that a forward contract does not involve any exchange of money between buyer. and seller at the start; hence, the value of the contract is zero at the start. This is the standard case, but it is not absolutely mandatory. The buyer and seller of a forward contract can set the price at whatever forward price they want. These types of contracts are called off-market forward contracts. First, take another look at Equation (22.3), which is repeated here:

$$
F_{0}(T)=S_{0}(1+r)^{\tau}.
$$

Suppose the parties set $F_{0}(T)$ to a value higher than the RHs. Now, let us see what happens. We first restate the value Equation, (22.7), with $t=0$

$$
V_{0}\left[F_{0}\left(T\right)\right]=S_{0}-\frac{F_{0}(T)}{\left(1+r\right)^{\tau}}.
$$

If the forward price is set to the formula price, Equation (22.3), this value goes to zero, as we have shown. But if the forward price is set higher than the formula price, then the. value becomes negative. A negative value contract means that the seller must pay the buyer. the value at the start. Let us think about this. If the forward price is too high, the buyer has agreed to pay too much at time. $T$ for the asset. Hence, the seller has the advantage. and must compensate the buyer for this additional value at time 0. If the forward price is. set lower than the formula price, then the value in the above equation becomes positive.. A positive value contract means that the buyer must pay the seller the contract value at the start. In this case, the buyer will be paying too little at time. $T$ and must compensate the seller for this additional value at time 0..

Finally, let us note several additional characteristics of forward contracts. Typical. forward contracts contain provisions that allow either party to request a settlement of the other. That is, the contract can be terminated early. Suppose the long holds a. position that has a value, as calculated in the manner shown in Equation (22.7), of $\$1.5$ million. The long and the short could, thus, terminate the contract before expiration by having the short pay the long $\$1.5$ million. If the value were negative, the long would pay the short. Either party can request an early termination, but typically one party is a dealer and dealers do not usually request early termination, because they exist to serve the needs of their clients and not to impose their own needs on their clients. The counterparty, who. is usually an end user, would ordinarily be the one to request an early termination..

Forward contracts can also be written to specify that at expiration the contract calls for physical delivery of the asset or an alternative procedure called cash settlement. Suppose, for example, that the buyer holds a forward contract on two million barrels of crude oil with a forward price of $\$70$ a barrel. Now, let us say we are at expiration and the price of crude oil is. $\$75$ a barrel. A physical delivery contract would result in the short delivering two million barrels of oil to the long, who would pay the short $\$70$ a barrel. So the long benefits by acquiring two million barrels at $\$5$ per barrel below the market price. Alternatively, a cash-settled contract would result in the short simply paying the long $\$10$ million. By settling in cash, the two parties can avoid the high transaction costs of handling the oil..

Forward contracts are subject to default. Technically the dealer or the end user could default. In deriving these pricing formulas, we have not taken default into account, because. that is a subset of the subject of credit risk. Some forward contracts are processed through. a clearinghouse and are subject to margin requirements and periodic settlements, which is the standard process used in futures contracts, as we explain next..
