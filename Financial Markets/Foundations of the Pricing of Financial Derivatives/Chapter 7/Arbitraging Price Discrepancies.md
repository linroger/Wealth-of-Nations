# 7.3 ARBITRAGING PRICE DISCREPANCIES

If the actual market price of the option differs from the model price, an arbitrage is possible. Consider the call option case. If the call can be sold for more than the formula value, Equation (7.9), the call is overpriced. Overpriced instruments should be sold. Simply selling the call, however, hardly qualifies as an arbitrage. If the call expires in-the-money, one could incur a significant loss, even though the call was underpriced. Instead, the arbitrage should be completed, and the risk eliminated by holding an offsetting number of units of the asset.

The arbitrageur would, thus, buy $b_{c}$ units of the asset for each call sold. It should be easy to see that the investment required would be less than what is given in Equation (7.2). Equation (7.2) is based on the market price equaling the model price, Equation (7.9). Hence, the amount invested is reduced by the overpricing. Convergence of the option value to its exercise value is ensured one period later because the option is expiring and can clearly be worth only its exercise value. With less money invested and the same payoff as before, the rate of return clearly exceeds the risk-free rate. If the option trades at below the formula price, it would be purchased and $b_{c}$ units of the asset would be sold, creating a net short position. The proceeds would be invested in risk-free bonds to earn the rate $r$ With the option purchased at a lower than fair price, the asset and option would finance. the purchase of the risk-free asset at a lower cost than it should if correctly priced, so the. investor would earn an arbitrage profit.

IABLE 7.1  Arbitrage Cash Flows Within One-Period Binomial Model for Calls


<html><body><table><tr><td>Strategy</td><td>Today</td><td>Down Event at Expiration</td><td>Up Event at Expiration</td></tr><tr><td>Sell call</td><td>0+ =+11.43</td><td>-max(0,dS -X) = 0</td><td>-max(0,uS-X)=-23.75</td></tr><tr><td>Buy b. shares</td><td>-hS =-52.78</td><td>+hSd=+42.22</td><td>+h Su = +65.97</td></tr><tr><td>Borrow</td><td>+B= +41.39</td><td>-B(1 + r) = -42.22</td><td>-B(1 +r) = -42.22</td></tr><tr><td>Net Cash flow</td><td>+0.04*</td><td></td><td>0</td></tr></table></body></html>

\*Note the quoted price is 11.43 and the model price is 11.38, a difference of 0.05. The table reports an arbitrage profit of 0.04. The 0.01 discrepancy is simply a rounding error.

IABLE 7.2  Arbitrage Cash Flows Within One-Period Binomial Model for Puts


<html><body><table><tr><td>Strategy</td><td>Today</td><td>Down Event at Expiration</td><td>Up Event at Expiration</td></tr><tr><td>Buy put</td><td>-pQ = -10.37</td><td>+max(0,X-dS)=+20.80</td><td>+max(0,X -uS)= 0</td></tr><tr><td>Buy hp s shares</td><td></td><td>+h,Sd = +36.98</td><td>+h,Su = +57.78</td></tr><tr><td>Borrow</td><td>+B =+56.65</td><td>-Bp(1 + r) = -57.78</td><td>-Bp(1 +r) = -57.78</td></tr><tr><td>Netcashflow</td><td>+0.06*</td><td></td><td>0</td></tr></table></body></html>

\*Note the quoted price is 10.37 and the model price is 10.42, a difference of 0.05. The table reports an arbitrage profit of 0.06 The 0.01 discrepancy is simply a rounding error..

Based on the information given in the past two examples, suppose we have the following market quotes, $c_{Q}=11.43$ and $p_{\mathscr{Q}}=10.37$ . Recall $S=99$ $X=100$ $r=0.02$ $\tau=1$ $u=1.25$ , and $d=0.8$ . In equilibrium, we found $c=11.38$ and $p=10.42$ , thus, the call price is too high and the put price is too low. Arbitrageurs typically prefer to receive positive cash flow today with no chance of any future liability. Alternative arbitrage transactions result in no cash flow today, but some chance of positive cash flow in the future.

Because the quoted call price is too high, the arbitrageur would sell it and buy the synthetic call option. Buying the synthetic call entails buying the stock with borrowed money. Table 7.1 illustrates cash flows capturing the arbitrage profit available with the call option.

Thus, the arbitrageur receives 0.04 today with no chance of a future liability. Within. this simple one-period binomial world, trading pressure will drive down the quoted call price and drive up the quoted stock price until the net cash flow is zero..

Turning to puts, if the quoted put price is too low, the arbitrageur would buy it and sell the synthetic put. We previously formed a hedge portfolio by buying the stock and the put. Hence, we can turn that around and see that a synthetic put would involve selling the stock and lending at the risk-free rate. Selling the synthetic put would, therefore, entail buying the stock and borrowing. Table 7.2 illustrates the cash flows that capture the arbitrage profit available with the underpriced put option.

Thus, the arbitrageur receives 0.06 today with no chance of a future liability. Within this simple one-period binomial world, trading pressure could simply drive up the quoted put price. Alternatively, buying shares can drive up the quoted stock price with some influence on the put price. Ultimately, the initial net cash flow must be zero.2

Regardless of the direction of the mispricing, the ability to earn an arbitrage profit would force a price alignment until the option price conforms to the model price.
