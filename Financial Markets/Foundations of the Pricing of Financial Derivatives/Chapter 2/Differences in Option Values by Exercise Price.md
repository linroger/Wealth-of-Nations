# 2.6 DIFFERENCES IN OPTION VALUES BY EXERCISE PRICE

The results in this section will enable us to understand the effect of exercise price on the pricing of options. That is, of two otherwise identical calls or puts, differing only by exercise price, which option will be priced higher? Our intuition should tell us that the call with the lower exercise price and the put with the higher exercise price should have higher prices. For the call, the exercise price is the hurdle over which the underlying must get to justify exercise. Thus, the lower the hurdle the easier it is to get over it. Moreover, for a given level of the underlying above the exercise price, the more valuable is the call when exercised. Hence, the lower-exercise price call should be worth more before expiration. For a put, the argument is reversed. To exercise the put, the underlying must get under the exercise price. Hence, the higher is the exercise price, the easier it is to get under it, and for a given level of the underlying below the exercise price, the higher is the exercise price, the higher the payoff of the put. Hence, puts with higher exercise prices should be worth more before expiration. Let us first take a formal look at calls.

![](f3a50bf55cc284807139c94966863806c7cbb00a6c19f0a54d5ed7f90a5df8ad.jpg)
FIGURE 2.4  Illustration of Dividend Impact on Put Lower Bound (Expressed as Percentage)

# 2.6.1 Calls Differing by Exercise Price

Consider two European calls differing only by exercise price. The first call has an exercise price of $X_{L}$ and a price of $c_{t L}$ and the second call has an exercise price of. $X_{H}$ and a price of $c_{t H}$ . The subscripts $L$ and $H$ stand for "low" and "high," respectively, but you should. not get in mind that $c_{t L}$ is lower than $c_{t H}$ . In fact, it will not be, as we show here..

So let us construct portfolio G, consisting of a long position in the call with exercise price $X_{L}$ and a short position in the call with exercise price of $X_{H}$ , and portfolio. $H$ consisting of zero-coupon bonds with face value of $X_{H}-X_{L}$ and current value of. $(X_{H}-X_{L})e^{-r_{c}\tau}$ We use these portfolios to establish an upper bound for the difference in the prices of the two calls, as shown in Table 2.5.

The first result to notice is that the payoff to Portfolio G is nonnegative, which means that the initial value of the call portfolio must be nonnegative. Therefore,

$$
c_{t L}\geq c_{t H}.
$$

This result means simply that the call with the lower exercise price must sell for at least. as much as the call with the higher exercise price. If the calls are American, this result still holds if we can prove that the payoff of the calls is never negative. We need not worry.

TABLE 2.5 Establishing an Upper Bound for the Difference in the Prices of Two European Calls Differing Only by Exercise Price.


<html><body><table><tr><td></td><td></td><td colspan="3">Value at Expiration</td></tr><tr><td>Instrument</td><td>CurrentValue</td><td>Sr≤XL</td><td>Hx>s>x</td><td>Sr ≥ XH</td></tr><tr><td>Portfolio G</td><td></td><td></td><td></td><td></td></tr><tr><td>Long European call (X)</td><td>CtL</td><td>0</td><td>ST - XL</td><td>Sr -XL</td></tr><tr><td>Short European call (XH)</td><td>-CtH</td><td>0</td><td>0</td><td>-(Sr -XH)</td></tr><tr><td>Total</td><td>H-</td><td>0</td><td>ST -XL</td><td>XH -XL</td></tr><tr><td>Portfolio H</td><td></td><td></td><td></td><td></td></tr><tr><td>Zero-coupon bond</td><td>(XH - X)e-ret</td><td>XH - XL</td><td>XH -XL</td><td>XH - XL</td></tr></table></body></html>

about the call we hold for we would never exercise it early if it were to our disadvantage.. If the call we are short is exercised early, then it must be the case that $S_{t}>X_{H}$ which means that $S_{t}>X_{L}$ and we could exercise our long call early, capturing a gain of $X_{H}-X_{L}$ , the maximum payoff at expiration in the case of a European call. Thus, early exercise makes no difference and we can state that8

$$
C_{t L}\geq C_{t H}.
$$

So, the lower exercise price American call is worth at least as much as the higher exercise price American call.

The second result we notice is that Portfolio $\mathrm{H}$ dominates Portfolio G. Consequently, we have

$$
c_{t L}-c_{t H}\leq(X_{H}-X_{L})e^{-r_{c}\tau}.
$$

This statement establishes an upper bound on the spread between the call prices. It says that the spread between the prices of the two call options differing only by exercise price is no more than the present value of the difference in the exercise prices..

If the calls are American, then we are required to modify Portfolio $\mathrm{H}$ such that its. current value is. $X_{H}-X_{L}$ and its face value is $(X_{H}-X_{L})e^{r_{c}\tau}$ . If our short call is exercised early, we simply exercise our long call, which is even deeper in-the-money, and capture a value of. $X_{H}-X_{L}$ . This money is then invested at the risk-free rate. Without adjusting Portfolio H, we might have Portfolio G dominating Portfolio $_\mathrm{H}$ due to the interest earned on the reinvestment of $X_{H}-X_{L}$ if early exercise occurs. With Portfolio $_\mathrm{H}$ worth $X_{H}-X_{L}$ today, however, it will grow to a value that is at least as great as that of Portfolio $\mathrm{G}$ in the. event of early exercise. Consequently, for American calls the rule becomes

$$
C_{t L}-C_{t H}\leq X_{H}-X_{L}.
$$

If there is no possibility of early exercise, as is the case when the asset makes no payments, the upper bound on the American spread comes down to the upper bound on the European spread, which is a smaller number.

Consider the following situation for two American calls: Suppose the lower 100 strike $(X_{L})$ call price is $C_{t L}=17$ and the higher 110 strike $(X_{H})$ call price is $C_{t H}=6.9$ . Based solely on this data, how would an arbitrageur exploit this data? Again, the first step. is to assess whether there is a boundary condition violation. Because these options are American, the boundary can be assessed based on Equation (2.18) as $C_{t L}-C_{t H}=17.0-$ $6.9=10.1>X_{H}-X_{L}=110-100=10.$ Thus, these quoted call prices suggest a 0.1 arbi-. trage opportunity. The arbitrageur seeks to pocket this O.1 through a series of current trades. Note in this case $C_{t L}-C_{t H}-(X_{H}-X_{L})=0.1$ and the trading strategy is embedded in this expression. Notice that you can generate this result by executing transactions that generate these specific cash flows, namely, sell the low strike call (. $C_{t L}=17\$ , buy the high strike call $\cdot{\cal C}_{t H}=6.9\mathrm{,}$ , and lend the difference in strike prices. $(X_{H}-X_{L}=10)_{,}$ . If the buyer of the $X_{L}$ call decides to exercise their right to buy the asset at some presently unknown point in time, $t^{\prime}$ , then the arbitrageur will exercise their right to buy the asset at. $X_{H}$ as well as sell bonds. Table 2.6 clearly demonstrates that these transactions result in arbitrage profits today with no subsequent chance for future negative cash flows.

As interest will be earned on buying bonds, we indicate this future value as. $F V.$ Note in Table 2.6 that the net cash flow today is 0.1. Buying pressure will drive up the high. strike call and selling pressure will drive down the low strike call. For every future possible outcome, the net cash flow is positive assuming interest rates are positive. Further note that trading pressure will drive the option prices in such a way that the positive net cash flow will no longer exist. Again, in well-functioning markets, we expect the net cash flow today to quickly move so as to be nonpositive..

# 2.6.2  Puts Differing by Exercise Price

Now consider two European puts differing only by exercise price. The first put has an exercise price of $X_{L}$ and a price of $p_{t L}$ and the second put has an exercise price of $X_{H}$ and a price of $\boldsymbol{p}_{t H}$ . Construct Portfolio I, consisting of a short position in the put with exercise price $X_{L}$ and a long position in the put with exercise price of $X_{H}.$ and Portfolio J consisting of zero-coupon bonds with face value of $X_{H}-X_{L}$ and current value of. $(X_{H}-X_{L})e^{-r_{c}\tau}$ We use these portfolios to set an upper bound for the difference in the prices of the two puts as shown Table 2.7..

TABLE 2.6 Numerical Illustration Establishing an Upper Bound for the Difference in the Prices of Two American Calls Differing Only by Exercise Price


<html><body><table><tr><td rowspan="2">Instrument</td><td rowspan="2">Cash Flow Today</td><td rowspan="2">Early Exercise (t)</td><td colspan="3">Cash Flow at Expiration</td></tr><tr><td>Sr ≤ XL</td><td>Hxs> x</td><td>ST > XH</td></tr><tr><td>Sell X, call</td><td>CtL = 17.0</td><td>-(S, - XL) = 100 -St</td><td>0</td><td>-(Sr - XL) = 100 -Sr</td><td>-(Sr - XL) = 100 -ST</td></tr><tr><td>Buy XH call</td><td>-Cth = -6.9</td><td>(Hx -"s)+ =St-110*</td><td>0</td><td>0</td><td>+(Sr - XH) = Sr -110</td></tr><tr><td>Buy XH - XL bond</td><td>-(XH-XL) = 10</td><td>FV,(XH - XL) >10</td><td>FVT(XH -XL) >10</td><td>FVT(XH - XL) >10</td><td>FVT(XH -XL) >10</td></tr><tr><td>Net</td><td>CuL - CtH -(XH - XL) = 0.1</td><td>>o</td><td>>10</td><td>>0</td><td>Interest > 0</td></tr></table></body></html>

Note: The arbitrageur will exercise early the high strike call only if it is in-the-money and trading for less than its exercise value; otherwise, they will just sell it. If $S_{t^{\prime}}$ is less than 110, then the net column for some early exercise date $\left(t^{\prime}\right)$ will be positive, even if $X_{H}$ call is worthless.

The first result we should notice is that the payoff to Portfolio I is nonnegative, which means that the initial value of the put portfolio must be nonnegative. In other words,

$$
\begin{array}{r}{p_{t H}\ge p_{t L}.}\end{array}
$$

This statement means that the put with the higher exercise price must sell for at least as much as the put with the lower exercise price. If the puts are American, this result still holds if we can prove that the payoff of the put portfolio is never negative. We need not worry about the put we hold for we would never exercise it early if it were to our disadvantage. If the put we are short in is exercised early, then it must be the case that $S_{t}<X_{L}$ which means that we could exercise our long put early, capturing a gain of $X_{H}-X_{L}$ earlier than expiration. This is the maximum payoff at expiration in the case of a European put. Thus, early exercise makes no difference, and we can state that

$$
\begin{array}{r}{P_{t H}\ge P_{t L}.}\end{array}
$$

The second result we notice is that Portfolio $\mathrm{J}$ dominates Portfolio I. Consequently,. we have

$$
\begin{array}{r}{p_{H}-p_{L}\le(X_{H}-X_{L})e^{-r_{c}\tau}.}\end{array}
$$

This statement establishes an upper bound on the spread between the European put prices.
The spread is no more than the present value of the difference in the exercise prices.

If the puts are American, then we are required to modify Portfolio J such that its. current value is. $(X_{H}-X_{L})e^{-r_{c}\tau}$ and its face value is $X_{H}-X_{L}$ . If our short put is exercised early, we simply exercise our long put, which is even deeper in-the-money, and capture. a value of $X_{H}-X_{L}$ . This amount is then invested at the risk-free rate. Without adjusting. Portfolio J, we might have Portfolio I dominating Portfolio J due to the interest earned on the reinvestment of $X_{H}-X_{L}$ . With Portfolio J worth $X_{H}-X_{L}$ today, however, it will grow to a value that is at least as great as that of Portfolio I in the event of early exercise. Consequently, for American puts the rule becomes

TABLE 2.7 Establishing an Upper Bound for the Difference in the Prices of Two European Puts Differing Only by Exercise Price


<html><body><table><tr><td></td><td></td><td colspan="3">ValueatExpiration</td></tr><tr><td>Instrument</td><td>CurrentValue</td><td>ST ≤XL</td><td>Hx>s>x</td><td>Sr ≥ XH</td></tr><tr><td>Portfolio I</td><td></td><td></td><td></td><td></td></tr><tr><td>Long European put (XH)</td><td>PtH</td><td>S -HX</td><td>Ls -Hx</td><td>0</td></tr><tr><td>Short European put (X,)</td><td>-PtL</td><td>-(XL -ST)</td><td>0</td><td>0</td></tr><tr><td>Total</td><td>PtH-PtL</td><td>XH -XL</td><td>XH -ST</td><td>0</td></tr><tr><td>Portfolio J</td><td></td><td></td><td></td><td></td></tr><tr><td>Zero-coupon bond</td><td>(XH - XL)e-rct</td><td>x -Hx</td><td>XH - XL</td><td>XH -XL</td></tr></table></body></html>

$$
P_{t H}-P_{t L}\leq X_{H}-X_{L}.
$$

Thus, the spread between the American put prices is no more than the spread between the exercise prices.

Consider the following situation for two three-month European puts: Suppose the. lower 100-strike $(X_{L})$ put price is $p_{L}=6.05$ and the higher 110-strike $(X_{H})$ put price is $p_{H}=16$ . Assume the continuously compounded risk-free rate is. $5\%$ . Based solely on this data, how would an arbitrageur exploit this situation? As before, the first step is to assess whether there is a boundary condition violation. Because these options are European puts,. the boundary can be assessed based on Equation (2.21) as.

$$
_H-\_p_{t L}=16.0-6.05=9.95>(X_{H}-X_{L})e^{-r_{c}\tau}=(110-100)e^{-0.05(3/12)}=9.875778.
$$

Thus, these quoted call prices suggest an approximately 0.07 arbitrage opportunity. The arbitrageur seeks to pocket this O.07 through a series of current trades. Note in this case the boundary is violated and again the trading strategy is embedded in this expression. Rearranging we have

$$
p_{t H}-p_{t L}-(X_{H}-X_{L})e^{-r_{c}\tau}=9.95-9.88=0.07.
$$

Notice that you can generate this result by executing transactions that generate these specific cash flows, namely, selling the high strike put. $(p_{H}=16)$ , buying the low strike put.
$(p_{L}=6.05)$ , and lending the difference in the present value of the strike prices (. $(X_{H}-$
$X_{L})e^{-r_{c}\tau}\cong9.88$ ). Table 2.8 clearly demonstrates that these transactions result in arbitrage.
profits today with no subsequent chance for future negative cash flows.

Because interest will be earned on buying bonds, we buy bonds valued at the present value of the difference in strike prices. Note in Table 2.8 that the net cash flow today is 0.07. Further, buying pressure will drive up the low strike put and selling pressure will drive down the high strike put. For every future possible outcome, the net cash flow is nonnegative assuming interest rates are positive. Further note that trading pressure will drive the option prices in such a way that the positive net cash flow will no longer exist. Again, in well-functioning markets, we expect the net cash flow today to quickly move so as to be nonpositive.

TABLE 2.8 Numerical Illustration Establishing an Upper Bound for the Difference in the Prices of Two European Puts Differing Only by Exercise Price.


<html><body><table><tr><td colspan="2"></td><td colspan="3">Cash Flow at Expiration</td></tr><tr><td>Instrument</td><td>Cash Flow Today</td><td>x≥s</td><td>Hxs>x</td><td>Sr > XH</td></tr><tr><td>Sell XH put</td><td>+PH = 16.0</td><td>(s - Hx)- = ST - 100</td><td>(s - Hx)- = Sr -100</td><td>0</td></tr><tr><td>Buy X, put</td><td>-PL =-6.05</td><td>(s - x)+ = 100-ST</td><td>0</td><td>0</td></tr><tr><td>Buy PV(XH -X,) bond</td><td>-PV(XH -XL) = 9.88</td><td>(x - Hx)+ = 10</td><td>+(XH - XL) = 10</td><td>(x - Hx)+ = 10</td></tr><tr><td>Net</td><td>PH-PL +PV(XH - XL)</td><td>0</td><td>Sr - 100 > 0</td><td>10</td></tr></table></body></html>
