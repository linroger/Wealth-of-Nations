---
tags:
  - '#annuity'
  - '#binomial_model'
  - '#interest_rate_swaptions'
  - '#payer_swaption'
  - '#receiver_swaption'
  - '#strike_rate'
  - '#swap_rates'
  - '#swaptions'
  - '#zero_coupon_bonds'
---
# 28.9 INTEREST RATE SWAPTIONS

Swaptions, which we briefly mentioned in Chapter 26, are options to enter into a swap.. If the underlying swap is a pay-fixed swap, then the swaption is called a payer swaption. If it is a receive-fixed swap, then the swaption is called a receiver swaption. In either case,. the swaption has a designated fixed or strike rate that plays the role of an exercise price. The underlying swap has a specific set of terms that are specified in the swaption contract. Say the strike rate is $7\%$ , and the underlying swap is a five-year swap with semiannual payments on January 30 and July 30. Let us assume that at expiration of the swaption, the equilibrium rate on the underlying swap is more than $7\%$ . Then a payer swaption is in-the-money, because it allows the holder to enter into the underlying swap and pay $7\%$ fixed to receive floating, while that same swap in the market would require paying more than $7\%$ fixed to receive floating. The swaption holder can either maintain the. $7\%$ swap or can offset it by going into the market and entering into the opposite swap with the same counterparty, thereby paying floating and receiving more than. $7\%$ fixed. The floating sides. effectively cancel and what remains is an annuity of the difference between the market rate and $7\%$ . If that swaption were structured to settle in cash, the seller of the swap would. pay the buyer the present value of that annuity. Letting the market rate at expiration of the swaption be less than. $7\%$ would result in a receiver swaption being in the money, and. a similar process would apply.

Using our binomial model, let us create a swaption with a. $7\%$ strike and expiration of time 1 with the underlying swap being a three-period swap with payments made at each time step. In order to price this swap, we shall need to know the possible rates on three-year swaps at time 1. We have already covered how swap rates are determined. Now, consider the top state at time 1 where the prices of one-, two-, and three-year zero-coupon bonds were shown in Figure 28.2 as 0.9119, 0.8289, and 0.7558. Thus, the rate on a three-year swap at that point in the tree would be.

$$
S R(3)^{+}=\frac{1-0.7558}{0.9119+0.8289+0.7558}=0.097822.
$$

In the bottom state at time 1, the three zero-coupon bond prices are 0.9491, 0.8890, and 0.8269. Thus, the swap rate would be.

$$
S R(3)^{-}=\frac{1-0.8269}{0.9491+0.8890+0.8269}=0.064932.
$$

So, assuming we are in the top state at time 1, the rate on three-year swaps would be $9.7822\%$ , which is above the strike rate, so the payer swaption would be exercised and the receiver swaption would expire unexercised. Now, let us determine the value of the payer swaption on exercise. We are creating a swap to pay $7\%$ and receive the floating rate, but we can offset that swap by entering into a swap in the market to pay the floating rate and receive $9.7822\%$ . This process creates a three-year annuity of $0.097822-0.07=$ 0.027822. The value of this payer swap is easily derived by finding the present value of this annuity:

$$
V p S W(1,0.07,3)^{+}=(0.097822-0.07)(0.9119+0.8289+0.7558)=0.0695.
$$

The receiver swaption is worth nothing, because it is out-of-the-money. That is, $V r S W(1,0.07,3)^{+}=0.0000$ . In the bottom state, it should be apparent that the payer. swaption is worth nothing,. $V p S W(1,0.07,3)^{-}=0.0000$ , and the receiver swaption is. worth

$$
V r S W(1,0.07,3)^{-}=(0.07-0.064932)(0.9491+0.8890+0.8269)=0.0135.
$$

Now we roll back to time 0 and discount the weighted-average of the next two possible swaption values:

$$
\begin{array}{r}{V p S W(1,0.07,3)=\left[0.5(0.0695)+0.5(0.0000)\right]0.9343=0.0324}\ {V r S W(1,0.07,3)=\left[0.5(0.0000)+0.5(0.0135)\right]0.9343=0.0063.}\end{array}
$$

This information is summarized in Figure 28.12.

![](images/87e459da041f32dbd0e7b7e561c6239acc638a85a25f485b65e99dabedeee440.jpg)
FIGURE 28.12 Binomial Tree of Swaption Values
