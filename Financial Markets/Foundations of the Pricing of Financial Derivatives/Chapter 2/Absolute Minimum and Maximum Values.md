---
tags:
  - '#absolute_maximum_value'
  - '#absolute_minimum_value'
  - '#american_call_option'
  - '#american_put_option'
  - '#arbitrage_profit'
  - '#european_call_option'
  - '#european_put_option'
  - '#option_pricing'
  - '#upper_boundary_condition'
---
# 2.2 ABSOLUTE MINIMUM AND MAXIMUM VALUES

By absolute minimum and maximum values, we wish to define bounds within which the option prices must lie. We do not rule out the possibility that the actual option prices might. have a higher minimum or lower maximum value that we can establish later.

The first absolute minimum value that we can easily specify is that an option cannot. have a negative value. One can never be forced to exercise an option. Hence, it can never. be worth less than zero. This result is true for both calls and puts as well as for American and European options,

$$
\begin{array}{r}{c_{t}\geq0\mathrm{~and~}C_{t}\geq0}\ {\mathrm{~}p_{t}\geq0\mathrm{~and~}P_{t}\geq0.}\end{array}
$$

Now, let us think about the maximum values. Both the European call and the American call cannot cost more than the value of the underlying asset. Either call option allows the. holder the right to buy the asset so the holder of the option would not pay more than the. cost of the asset to acquire the right to buy the asset. A weaker statement might place this. upper bound at infinity, because that is the upper bound on the asset price, but there is no. reason to impose such an extreme upper bound as the current value of the asset is more precise.

A put reaches its maximum value when the asset is worthless. A European put then is worth the present value of the exercise price as its holder has the right to exercise the option at expiration and claim $X$ dollars at that time. Thus, its current worth is the present value. of X.4 For an American put, however, there is no reason to wait as it can be immediately. exercised for a cash flow of. $X$

The maximum values of calls and puts are stated formally as

$$
\begin{array}{r l}{c_{t}\leq S_{t}\quad\mathrm{and}\quad C_{t}\leq S_{t}}&{}\ {p_{t}\leq X e^{-r_{c}\tau}\quad\mathrm{and}\quad P_{t}\leq X_{t}.}\end{array}
$$

Suppose you call your broker for a quote on a one-year, at-the-money. $(S_{t}=X=100$ European call and to your surprise the broker quotes you 101 per share. As this is a clear violation of the upper boundary condition, there is an arbitrage profit available. The quoted call price is too high; hence, you would sell the call and buy the stock for a net cash flow of 1 $(=101-100)$ . If the option expires out-of-the-money, sell the stock and receive. nonnegative proceeds $\left(S_{t}\geq0\right)$ . If the option expires in-the-money, then when the option. is exercised by the buyer, you receive the exercise price $\mathit{\Omega}^{\prime}X=100\mathit{\check{\Psi}}.$ and deliver the stock you previously purchased. Thus, in all future states of the world, there is no possibility of having to pay money. This is clearly an attractive transaction that will rarely, if ever, be available.

<html><body><table><tr><td>Instrument</td><td>Now Time (t)</td><td>Expiration n (time T, out-of-the-money S (X>LS</td><td>Expiration n (time T, in-the-money X < ST )</td></tr><tr><td>Short the call</td><td>101</td><td>0</td><td>X+Is-</td></tr><tr><td>Long the stock</td><td>-100</td><td>ST</td><td>ST</td></tr><tr><td>Net proceeds</td><td>1</td><td>ST</td><td>X</td></tr></table></body></html>
