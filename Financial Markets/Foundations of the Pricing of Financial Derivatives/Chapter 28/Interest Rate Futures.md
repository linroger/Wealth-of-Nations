---
tags:
  - add_on_interest_rates
  - binomial_framework
  - eurodollar_futures
  - futures_pricing
  - interest_rate_futures
  - mark_to_market
aliases:
  - Futures Pricing
  - Interest Rate Futures Pricing
key_concepts:
  - Binomial futures pricing
  - Futures expected gain
  - Futures on add-on rates
  - Mark-to-market value
  - Weighted average settlement
---

# 28.10 INTEREST RATE FUTURES

We could price a futures on any underlying that we have already covered, such as add-on interest rates, continuously compounded rates, zero-coupon bonds, and coupon bonds. We shall illustrate how futures pricing works in a binomial framework by pricing a futures on the one-period add-on interest rate. This process will be very similar to how Eurodollar futures, the most widely traded futures contract, work in practice.

Let us specify that we are interested in a two-period futures on the add-on rate. At. expiration, the futures price will automatically settle to the one-period add-on spot rate. The tree of one-period add-on spot rates was given in Figure 28.8. Hence, the futures will settle at either $11.6864\%$ $8.3856\%$ , or $5.1823\%$ . The final mark-to-market or settlement. will be the difference between that price and the previous price..

Recall that a futures is marked-to-market, and that mark-to-market value is the value. of the futures. Once the mark-to-market value is paid from one party to the other, the. contract resets itself to the current futures price so that its value is pulled back to zero. At that point, the expected gain from the futures must be zero, because there is no money. invested. Because a futures contract must have zero expected gain, the following conditions. must hold to determine the futures price at time 1:.

$$
\begin{array}{r l}&{0.5\left[0.116864-f(2)^{+}\right]+0.5\left[0.083856-f(2)^{+}\right]=0.0000}\ &{0.5\left[0.083856-f(2)^{-}\right]+0.5\left[0.051823-f(2)^{-}\right]=0.0000.}\end{array}
$$

Notice that we do no discounting of the weighted average settlement, because it would have no effect. The terms on the left-hand sides must equal zero without discounting. It is also easy to see that the futures price at time 1 in either state will be the average of the next two possible futures prices. Thus,

$$
\begin{array}{r}{f(2)^{+}=0.5(0.116864)+0.5(0.083856)=0.10036}\ {f(2)^{-}=0.5(0.083856)+0.5(0.051823)=0.06784.}\end{array}
$$

And the futures price at time 0 will be the weighted average of these two prices:

$$
0.5(0.10036)+0.5(0.06784)=0.0841.
$$

Now let us determine the mark-to-market value of the futures as it evolves through the tree. We use an asterisk $({}^{\ast})$ in the exponent to indicate that this is the value before the. settlement:

$$
\begin{array}{l}{{\nu f(2)^{++*}=0.116864-0.10036=0.016504}}\ {{\nu f(2)^{+-*}=0.083856-0.10036=-0.016504}}\ {{\nu f(2)^{-+*}=0.083856-0.06784=0.016016}}\ {{\nu f(2)^{--*}=0.051823-0.06784=-0.016016.}}\end{array}
$$

Note in particular that the outcome in which rates go up then down is not the same. as when rates go down first and then up. These four amounts are the payouts from the settlement at expiration. Now, let us back up to time 1 and compute the value before the. settlement:

$$
\begin{array}{l}{{\nu f(2)^{+*}=0.10036-0.0841=0.01626}}\ {{\nu f(2)^{-*}=0.067840-0.0841=-0.01626.}}\end{array}
$$

Now, let us verify that all of these values are correct by determining the expectation of the next-period values through the tree:

$$
\begin{array}{r l}&{\nu f(2)^{+}=0.5(0.016504)+0.5(-0.016504)=0.0000}\ &{\nu f(2)^{-}=0.5(0.016016)+0.5(-0.016016)=0.0000}\ &{\nu f(2)=0.5(0.01626)+0.5(-0.01626)=0.0000.}\end{array}
$$

Technically these values should be discounted, but clearly that is unnecessary. These results are summarized in Figure 28.13.

With the methodology learned here, we would be able to price virtually any futures following the same procedure.

![](506fd2ae5889801bf63dfd36a6635f1efa71129520a30ca80fa9a93481443675.jpg)
FIGURE 28.13 Binomial Tree of Futures Prices and Values
