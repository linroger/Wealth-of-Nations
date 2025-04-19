---
tags:
  - '#asset_or_nothing_option'
  - '#black_scholes_merton_formula'
  - '#cash_or_nothing_option'
  - '#continuous_time'
  - '#digital_options'
  - '#european_options'
  - '#risk_free_rate'
  - '#state_prices'
  - '#state_pricing'
---
# 29.5 STATE PRICING AND OPTIONS IN CONTINUOUS TIME

In the real world, there are an infinite number of possible states. This makes it difficult, if not impossible, to identify the specific states and derive their prices. It is possible, however, to make some approximations of state prices from the prices of traded options.

As discussed in Chapter 13, a standard European call option on an asset can be decomposed into two components. One is a long position in an asset-or-nothing option, which pays the value of the asset if its price at expiration exceeds the exercise price and nothing otherwise. The other component is a short position in a certain number of cash-or-nothing options, which obligates the seller to pay a certain amount of money if the asset price at expiration exceeds the exercise price and nothing otherwise. The number of such options is the exercise price.

Letting $c$ be the call price, S be the underlying asset price,. $X$ be the exercise price, $r_{c}$ be the continuous risk-free rate,. $\sigma$ be the volatility of the return on the asset price, and $\tau$ be the time to expiration, the value of the European call is well known as the Black-Scholes-Merton formula,

$$
\begin{array}{c}{c=S N(d_{1})-X e^{-r_{c}\tau}N(d_{2})}\ {d_{1}=\cfrac{\ln(S/X)+(r_{c}+\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}},}\end{array}
$$

and

$$
d_{2}=\frac{\ln(S/X)+(r_{c}-\sigma^{2}/2)\tau}{\sigma\sqrt{\tau}}=d_{1}-\sigma\sqrt{\tau}.
$$

As we discussed in Chapter 13, the value of the asset-or-nothing component of a standard European option is $S N(d_{1})$ and the value of the cash-or-nothing component is $X e^{-r_{c}\tau}N(d_{2})$ For our purposes here, we need the value of a more general cash-or-nothing option, one that pays off 1.0 if it expires with the asset value above the exercise price and zero otherwise. And as covered in Chapter 13, such an option is sometimes called a digital or binary option because it pays off zero or 1.0. Let us denote the price of the digital call option as $d c$ , and we see that its value is

$$
d c=e^{-r_{c}\tau}N(d_{2}).
$$

Given the Black-Scholes-Merton put option pricing formula,

$$
\begin{array}{r}{p=X e^{-r_{c}\tau}\left[1-N(d_{2})\right]-S\left[1-N(d_{1})\right],}\end{array}
$$

we can find the price of a digital put, which is an option that pays 1.0 if the asset value at expiration is less than the exercise price. Its formula is.

$$
d p=e^{-r_{c}\tau}\lbrack1-N(d_{2})\rbrack.
$$

These digital option formulas are also the partial derivatives of the Black-ScholesMerton call and put formulas with respect to the exercise price.5.

Now let us divide the uncertain outcomes into three possibilities. Let $S_{T}$ be the value of the asset at a specific future date,. $S_{1}$ be one possible level of the asset, and. $S_{2}$ be another possible level of the asset where. $S_{2}>S_{1}$ . Thus, we know that the asset value must fall within any of a number of ranges, as specified here:.

$$
\begin{array}{c}{{S_{T}\leq S_{1}}}\ {{}}\ {{S_{1}<S_{T}\leq S_{2}}}\ {{}}\ {{S_{T}>S_{2}.}}\end{array}
$$

These ranges are collectively exhaustive. As such, they completely define the state space.. Although this specification oversimplifies the real world, it does allow us to work with three easily identifiable states from which we can determine the three state prices..

We wish to find the prices of the pure assets that span the state space. Our problem, therefore, is as follows:

What is the price of an asset that pays 1.0 if $S_{T}\leq S_{1}$ What is the price of an asset that pays 1.0 if $S_{1}<S_{T}\leq S_{2}$ What is the price of an asset that pays 1.0 if $S_{T}>S_{2}$

It turns out that we can use digital calls and puts to obtain the answer.

A digital put with an exercise price of $S_{1}$ is an asset that pays 1.0 if the first state,. $S_{T}\leq S_{1}$ , occurs and zero otherwise. Thus, its price is the price of the first pure asset. The. second pure asset is identical to a long position in a digital call with an exercise price of $S_{1}$ and a short position in a digital call with an exercise price of. $S_{2}$ . To see this, note that if $S_{T}\leq S_{1}$ , both options expire out-of-the-money so there is no payoff. If $S_{1}<S_{T}\leq S_{2}$ , the long digital call struck at $S_{1}$ pays 1.0 and the short digital call struck at. $S_{2}$ pays nothing for a total payoff of 1.0. If $S_{T}>S_{2}$ the long digital call struck at $S_{1}$ pays 1.0 and the short digital call struck at $S_{2}$ will require a payment of 1.0, thereby offsetting and leaving a zero payoff. The third pure asset, which pays 1.0 if the state. $S_{T}>S_{2}$ occurs, can be replicated with a long digital call with an exercise price of $S_{2}$

Let us put some numbers on these results by deriving the prices of these pure assets from the prices of options on a particular stock index priced at 10,o00, with a volatility of $20\%$ and a yield of. $2\%$ . The continuously compounded risk-free rate is $2.5\%$ . We consider two options that expire in 60 days, so $\tau=60/365=0.1644$ . The first option has an. exercise price of 9,000, and the second an exercise price of 11,000. With this information, we can find the state prices for this index being below 9,000, between 9,000 and 11,000, and above 11,000.

Using the Black-Scholes-Merton option pricing model, we obtain the following values: $e^{-r_{c}\tau}=e^{-0.025(0.1644)}=0.9959$ $N(d_{2}|X=9,000)=0.8978$ and $N(d_{2}|X=11,000)=$ 0.1139. From this, we obtain the following prices for the digital options:

<html><body><table><tr><td>digital call struck at 9,000 digital put struck at 9,000 digital call struck at 11,000</td><td>0.8941 (= 0.9959*0.8978) 0.1018 [= 0.9959*(1 -0.8978)] 0.1135 (= 0.9959*0.1139).</td></tr></table></body></html>

Thus, our state prices are

<html><body><table><tr><td>pure asset1 0.1018 pure asset2 0.7806 (= 0.8941 -0.1135)</td></tr></table></body></html>

We can then obtain the risk-free rate over that period as. $1/(0.1018+0.7806+0.1135)-$ $1=0.004118$ .This result is consistent with the. $2.5\%$ continuously compounded rate because the equivalent discrete compounded rate for 60 days would be $e^{0.02\hat{5}(60/365)}-1=$ 0.004118.
