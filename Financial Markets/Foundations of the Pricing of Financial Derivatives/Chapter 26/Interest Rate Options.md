---
tags:
  - arbitrage_free_model
  - black_model
  - heath_jarrow_morton
  - interest_rate_options
  - interest_rate_swaps
aliases:
  - IRO
  - Interest Rate Option
  - Option on Interest Rates
key_concepts:
  - Arbitrage-free term structure model
  - Black model application
  - Fixed payment, floating payment
  - Interest rate options
  - Option valuation challenges
---

# 26.3 INTEREST RATE OPTIONS

As with interest rate forwards and swaps, there are also options on interest rates. An interest rate option gives the right but not the obligation to make or receive a fixed payment at an upcoming date. An interest rate call is the right to make a fixed payment and receive a floating payment. An interest rate put is the right to receive a fixed payment and make a floating payment. As with swaps, the rate is determined on the settlement date, but the payment is made on the next settlement date, at which time the rate is reset.

# 26.3.1 Interest Rate Option Values

Using the same notation as with interest rate swaps, on day $J_{:}$ the value at $J$ of the payoff of a call with strike rate. $X$ is

$$
V I R C_{J}(J,q)=\operatorname*{max}\left[0,\frac{L_{J}(q)-X}{1+L_{J}(q)\left(\frac{q}{360}\right)}\right].
$$

Of course, this amount is paid at $j+q$ , hence the discounting to obtain the value at $J.$ The payoff of an interest rate put is

$$
V I R P_{J}(J,q)=\operatorname*{max}\left[0,\frac{X-L_{J}(q)}{1+L_{J}(q)\left(\frac{q}{360}\right)}\right].
$$

Valuing interest rate options prior to expiration, however, is much more difficult than. valuing swaps or FRAs. As we have previously noted, options depend on the distribution of the underlying, in particular the volatility. Moreover, although we can typically value an option on an asset in isolation from the options on other assets, we cannot value an interest rate option in isolation from the other interest rate options on the same underlying. interest rate but with different maturities and strikes. If we try to do so, we might admit arbitrage. Nonetheless, this procedure is commonly done in practice. For example, many. practitioners use the Black model for pricing options on forwards and futures that we. previously covered. The reasoning is that an option on an interest rate is really an option. on a forward rate. So, to use the Black model one simply plugs in the forward rate as the underlying and the forward rate volatility as the volatility as required in the model. The. problem with doing this, however, is that if other options on the same underlying are also offered for trading, these prices could admit arbitrage, because there is no linkage between. prices from the Black model for options on the same underlying. That is, applying the Black model to two options on the same interest rate does not guarantee that one cannot. arbitrage the one against the other. There is no binding force that connects the option prices, because the model is applied independently to the two options..

The best method of dealing with this concern is to develop an arbitrage-free model of the term structure. There are many such models, and we shall cover one, the Heath-Jarrow-Morton model, in Chapter 27. In Chapter 28 we shall show how to derive prices using a binomial version of that model.

# 26.3.2 Interest Rate Option Parity Relationships

There are some important parity relationships between interest rate options and interest rate swaps and forwards. Consider an interest rate call and an interest rate put both with an exercise rate of $X$ For notational simplicity, let us disregard the adjustment $(q/360)$ and state the payoffs at time $j$ of a long call and short put as

$$
\operatorname*{max}\bigl[0,L_{j}(q)-X\bigr]-\operatorname*{max}\bigl[0,X-L_{j}(q)\bigr].
$$

Now, consider the various possible outcomes:

If $L_{j}(q)>X$
Call pays $L_{j}(q)-X$
Put pays nothing.
If $L_{j}(q)<X$
Call pays nothing.
Put pays $-{\bigl(}X-L_{j}(q){\bigr)}=L_{j}(q)-X.$

We can see that in all circumstances, the combination pays. $L_{j}(q)-X$ . This makes this combination similar to a long FRA. There is, however, a more precise specification that makes this combination identical to an FRA: that the strike. $X$ is the same as the FRA rate. In other words, if. $X$ is not the FRA rate, then the call and put would not have the same prices, so going long a call and short a put would result in either the call costing more than the put or the put costing more than the call. There would, therefore, be either a net cash outflow or inflow at the start. Hence, this synthetic FRA would be off-market. An FRA priced at the appropriate arbitrage-free rate that is based on zero value at the start would have no initial cash inflow or outflow. So, if the exercise rate of the interest rate call and put is set at the FRA rate, there would be no net cash inflow or outflow. Then the put and the call have the same price, so buying a call and selling a put would cost nothing on net.

# 26.3.3 Interest Rate Caps, Floors, and Collars

A combination of interest rate calls expiring at different dates is called a $c a p$ , because it is often used by a borrower to cap the interest rate on a floating-rate loan. The borrower takes out the loan and buys a cap, which consists of interest rate call options that expire on the dates on which the loan rates are reset. The component call options are called caplets. When the underlying rate is above the cap exercise rate, the caplet pays off and effectively compensates the borrower for the increase in interest rates. When the loan rate is reset below the cap exercise rate, the caplet expires unexercised, and the borrower benefits from the lower rate. The total cost of the component caplets that make up the cap does effectively raise the loan rate, but it serves as insurance that limits the overall rate paid to a maximum, hence, a cap.

A combination of interest rate puts is called a floor because it is often used by a lender. to put a floor on the rate on a floating-rate loan. The individual put options are called. floorlets. A lender in a floating-rate loan might buy a floor to put a minimum on the effective rate on a loan. Each floorlet would expire on the day on which the loan rate is reset..

When the rate resets below the exercise rate, the floorlet pays off and the lender is compensated for the lower rate. The overall cost of the floor lowers the rate of return on the loan but effectively sets a minimum rate.

A combination of long cap and short floor is called a collar because it is used by bor-. rowers to contain the effective interest rate on a floating-rate loan within a range. The cap strike is chosen at a rate that effectively limits the loan rate to a maximum value. The. borrower then sells a floor at a lower strike, which results in giving up gains when the rate falls below the lower exercise rate. The two rates are set such that the price of the cap is precisely offset by the price of the floor.' The effective rate on the loan will vary between the cap exercise rate and the floor exercise rate. If the call and put exercise rates are both set to the swap rate, the call premium will also equal the put premium and there will be no. net cash outflow or inflow at the start. Moreover, the combination will produce the same results as an interest rate swap.

It is also possible to have forward contracts on swaps, which are called forward swaps,. and options on swaps, which are called swaptions. We shall illustrate swaptions when we show how to use a binomial tree to price interest rate derivatives in Chapter 28..
