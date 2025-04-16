---
tags:
  - '#binomial_tree'
  - '#equilibrium_swap_rate'
  - '#interest_rate_swaps'
  - '#one_period_rate'
  - '#present_value'
  - '#swap_payments'
  - '#swap_valuation'
  - '#zero_coupon_bonds'
---
# 28.7 INTEREST RATE SWAPS

Let us price and value a swap that expires at time 2 in which the underlying is the one-period rate. We shall now need to create the tree of one-period add-on rates. In the previous section covering FRAs, we showed how the one-period continuously compounded rate converts to the add-on rate, but FRAs have only one payment so we did not need the entire tree. Swaps have multiple payments, so we do need the full tree. Following the conversion procedure as we did in the previous section, we obtain Figure 28.8.

In Chapter 26, we covered how to obtain the equilibrium swap rate. For a swap that expires at time 3, the rate will be given from the prices of one- and two-period zero-coupon bonds.

$$
{\frac{1-0.8694}{0.9343+0.8694}}=0.072433.
$$

We know that the first swap payment, which occurs at time 1, is based on the starting spot rate of $7.0365\%$ . That payment will be

$$
0.070365-0.072433=-0.002068.
$$

Note that the rate, 0.070365, is the continuous equivalent of the discrete rate 0.068 (i.e., $e^{0.068}-1=0.070365;$ . This payment will occur in each of the next two states. Interest rates go up to where the one-period rate is $9.6584\%$ . The swap payment of -0.002068 is made and the swap payment in the next period will be

$$
0.096584-0.072433=0.024151.
$$

This payment will occur regardless of which of the next two outcomes occurs. Now, stepping back to time 1 with the one-period rate at $5.3586\%$ , the next swap payment will be.

$$
0.053586-0.072433=-0.018847.
$$

Now, let us step back and value the swap at time 1. We can do that by taking a discounted weighted average of the next two swap values. Except we know that the next two values. are 0.024151 for certain, because they were determined at the last period, meaning that. we do not have to take a weighted average. We simply discount that value back to the present and add the current payment:

$$
\begin{array}{l}{{V I R S(2,0.072433)^{+}=0.024151(0.9119)-0.002068=0.019956}}\ {{{}}}\ {{V I R S(2,0.072433)^{-}=-0.018847(0.9491)-0.002068=-0.019956}}\end{array}
$$

The symmetry of these two values guarantees that the value at time zero will be zero, as it should for a swap priced at the equilibrium rate. The tree of swap values is shown in Figure 28.9.

You will note that here we valued the swap a bit differently from the way we did. in Chapter 26, where we added the notional to the fixed and floating sides. That was a necessary trick that helped us avoid having to value specific outcomes. But with a binomial tree, we can value specific outcomes. Just to show you that we obtain the same results, let us verify the value of 0.019956 that appears in the top state at time 1 in Figure 28.9.. Remember that in Chapter 26 we showed that the present value of the remaining floating. payments plus the notional is 1. The present value of the remaining fixed payment plus. notional of 1 is easily found by discounting 1 plus the upcoming fixed payment at the one-period rate, which would be done by multiplying by the one-period zero-coupon bond price of 0.9119. Subtracting the present value of the fixed payments plus notional from the present value of the floating payments plus notional, which is equal to 1, gives the value. of the swap:

![](images/cb59043ce3f425900ca0820f80db0fd87eea20173ccd93fbb658e6de92de3fab.jpg)

$$
1.0-1.072433(0.9119)-0.002068=0.019956.
$$

And this is the same value we obtained by discounting the values as in the tree.
