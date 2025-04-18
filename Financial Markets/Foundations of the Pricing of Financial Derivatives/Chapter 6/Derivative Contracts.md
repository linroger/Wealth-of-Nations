---
tags:
  - '#arbitrage'
  - '#derivative_contracts'
  - '#forward_contract'
  - '#option_pricing'
  - '#risk_free_rate'
  - '#risk_neutrality'
  - '#spot_price'
  - '#underlying_asset'
---
# 6.4 DERIVATIVE CONTRACTS

Our ultimate interest is in one type of derivative, the option. Understanding option pricing is key to understanding the pricing of numerous other financial instruments. Before we get to options, however, let us take a look at a simpler type of derivative: the forward contract. Suppose we create a side bet on the outcome of the first asset. Let Trader A offer to pay Trader $\mathrm{~B~}26.50\$ if the good economy occurs, provided that Trader B will pay Trader A 23.50 if the bad economy occurs. Suppose that Trader A borrows 70 at the risk-free rate of $5\%$ and uses the funds to purchase the asset. They then enter into this side bet to pay Trader $\mathrm{~B~}26.50\$ if the good economy occurs with the condition that they receive 23.50 from Trader B if the bad economy occurs. The 70 Trader B borrows will have to be paid back, thereby requiring a payment of $70(1.05)=73.50$ one period later. Trader B's overall payoff will be as follows:.

A good economy occurs: He holds an asset worth 100, owes 26.50, and pays back the loan value of 73.50 for a net cash flow of zero..

A bad economy occurs: He holds an asset worth 50, receives 23.50, and pays back the loan value of 73.50 for a net cash flow of zero..

Of course, there is no particular reason this investor should do this. They committed. none of their own funds at the start and end up with no money regardless of the outcome. But this example illustrates that the side bet should pay 26.50 to one party if a good. economy occurs and 23.50 to the other party if the bad economy occurs. These are fair equilibrium terms for the side bet..

What if the side bet pays 26.50 if the good economy occurs and 25 if the bad one occurs? Then it should be apparent that if the bad economy occurs, Trader A will end up with $50+25-73.50=1.50.$ If the good economy occurs, Trader A will end up with zero. So, without investing any of their own money, Trader A takes a gamble in which they either end up with no money or 1.50. Trader A will certainly do it, as will other arbitrageurs. Their collective actions force the terms of the side bet to change until the bet is a fair one for both parties. That naturally occurs if the payoff in the bad economy is 23.50.

The two payoffs to Trader A, 26.50 in the good economy and $-23.50$ in the bad economy, can be derived as follows:

If the good economy occurs: $100-x=26.50$ If the bad economy occurs: $50-x=-23.50$

Clearly $x=73.50$ . This number is a special value and is the key to finding the equilibrium payoffs of the side bet. We could, however, have obtained that value in another and much easier way. We simply take the price of the asset, 70, and compound it at the risk-free rate, $5\%$

$$
70(1.05)=73.50.
$$

This side bet illustrates a type of derivative transaction known as a forward contract.. Embedded in a forward contract is the notion of a forward price. We can think of the forward price, 73.50 in this example, as the price that one party agrees to pay for the asset when the contract expires. Thus, here a party going long the forward contract agrees to pay. 73.50 one period later. If the good economy occurs, the party pays 73.50 and receives the asset worth 100 for a net gain of 26.50. If the bad economy occurs, the party pays 73.50 and receives the asset worth only 50 for a net loss of 23.50. Thus, a forward contract is. an agreement for one party to pay the forward price and receive the asset at a later date. The other party agrees to deliver the asset and receive the forward price..

In this example, we assumed that the asset price was 70, which was the price appropriate for the highly risk-averse investor. Suppose we have a less risk-averse investor who considers the asset worth 80. In that case, the forward price would be 80(1.05)84. The forward contract would need to pay 16 to one party if the good economy occurs and 34 to the other party if the bad economy occurs. In this way, if someone did the transaction just described, that is, borrowed 80 at. $5\%$ and offered the forward contract as a seller, they. would end up with. $100-16-84=0$ if the good economy occurs and. $50-34-84=0$ if the bad economy occurs. This result is what it should be. The person committed no personal funds and took no risk. Therefore, the gain should be zero for certain.

The point is that the forward price, whether 73.50 or 84, depends on the spot price of the underlying asset and the risk-free rate. It will also depend on how long the contract is and for some assets and some derivatives, it will depend on other factors.6 The most important point is that we take the asset price as given. We do not care whether the investors who priced the asset are highly risk averse, slightly risk averse, or risk neutral. We assume that how investors feel about risk is fully incorporated into the price of the asset. Once the asset price is determined, we do not care what factors investors consider in obtaining that price.

With that in mind, we can treat our process of valuing derivatives as though investors are risk neutral. Consider the case where investors are highly risk averse and price the asset at 70. We noted that at a risk-free rate of $5\%$ , these investors are pricing the asset with a risk premium of $9.29\%$ , because the expected value of the asset is 80, which is $14.29\%$ higher than 70, but a portion of the $14.29\%$ is the risk-free return $(5.0\%)$ . For our forward contract, however, the forward price was found to be 73.50, which is only $5\%$ higher than the spot price of 70. Thus, the forward contract can be viewed as being priced by risk-neutral investors. That does not mean that investors are actually risk neutral. In fact, we just said they are highly risk averse in this example. But the forward price is found by taking the spot price of 70 and factoring it up to reflect only a risk-free return of $5\%$ thereby obtaining 73.50 as the forward price. The principle that derivative instruments are priced to prohibit the opportunity to earn an arbitrage profit turns out to be the same as the notion that we can treat participants in derivative markets as though they are risk neutral. This simply means that derivatives are priced as though investors are risk neutral. In fact, they are not risk neutral but are risk averse. Their risk aversion is embedded into the price of the underlying asset. Given the price of the underlying asset, it is easy to price the derivative, using, of course, the condition of risk neutrality..

Yet another way to look at it is that if we did not treat investors as though they were risk neutral when pricing derivatives, we would be double counting the risk. The risk is. incorporated into the price of the asset. The price of the asset is then incorporated into the derivative price, which takes care of handling any adjustment for risk. We cannot treat. the derivatives investor as though they require a premium as compensation for the risk.. That premium is already there-in the price of the asset. We will return to this point in the last section of this chapter, where we introduce a world of risk-averse and risk-neutral investors.
