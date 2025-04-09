# 7.5 AMERICAN OPTIONS AND EARLY EXERCISE IN THE BINOMIAL FRAMEWORK

If the options are American style, they can be exercised early. It is well known that American call options will not be exercised early unless there is a dividend or some other cash. amount paid by the asset, in which case early exercise could be justified immediately before. the cash is paid.7 To accommodate the possibility of early exercise, there are a variety of methods that can be used in the binomial model. One extremely useful, but somewhat oversimplified method, is to assume the dividend is a constant rate of the value of the asset.8. This approach, however, would imply a dividend at every time step. There are some limited. situations in which that might be appropriate, such as for an option on a stock index where dividends are paid by the constituent stocks at different times. An alternative approach, however, is to subtract the present value of all dividends over the life of the option from. the current value of the underlying--often called the escrow method. Then we let the net of the stock price minus the present value of dividends evolve through the binomial tree according to the factors $\boldsymbol{\mathscr{u}}$ and $d.$ At a given node at which the dividend is paid, we decide. if the option is worth exercising just before the stock goes ex-dividend. If so, the exercise value replaces the value obtained using the formula. We explore the escrow method in detail in the next section..

To illustrate the early exercise decision for calls, suppose at a point in the tree, we have. a value of the stock price minus the present value of all remaining dividends over the life of the option of 42.' Suppose that using the binomial formula, we compute the value of the. call at that point as 2.25. Assume there is a 3.0 dividend being paid at this time point; then, the stock price with the dividend is 45.10 with the exercise price at 42, we could exercise. it and collect a value of 3.0, which is more than its unexercised value of 2.25. Thus, we would replace 2.25 with 3.0. This early exercise check would be done at all points in the tree in which the option is in-the-money..

If the option is a put, it is well known that early exercise could occur regardless of a. dividend. In that case, at every in-the-money point in the binomial tree, we would need to. check to see if the put is worth more exercised or not. If it is worth more exercised, we insert the exercise value at that point into the tree as the option value. If not, we use the. computed value obtained by the formula. If there is a dividend, it will reduce the frequency of early exercise because dividends drive the stock price down, which makes puts worth more. Exercising early throws away this benefit. If early exercise is justified when there are dividends, it would occur just after a dividend. That is, if we are going to exercise the put,. we might as well wait until the stock falls..

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>100</td></tr><tr><td>Put</td><td>15.49</td></tr><tr><td>Hedge Ratio</td><td>0.47</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>125</td></tr><tr><td>Put</td><td>4.33</td></tr><tr><td>Hedge Ratio</td><td>0.15</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>156.25</td></tr><tr><td>Put</td><td></td></tr></table></body></html>

FIGURE 7.9 Two-Period Binomial Model for European Put Option Illustrated


<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>77</td></tr><tr><td>Put</td><td>26.96</td></tr><tr><td>Hedge Ratio</td><td>1</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>96.25</td></tr><tr><td>Put</td><td>8.75</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>59.29</td></tr><tr><td>Put</td><td>45.71</td></tr></table></body></html>

Now to illustrate this early exercise feature, we consider a two-period binomial model when there are no dividends with the following parameters, $S=100$ $X=105$ $r=1.0\%$ $u=1.25$ $d=0.77$ , and two years to expiration. Figure 7.9 illustrates the underlying stock price, put price, and hedge ratio for a European put option.11 Note that at time step 1, the hedge ratio is 1 because both subsequent up and down moves at time 2 are in-the-money.

If the put option is American, then we need to check at each time step whether it is more valuable to exercise the option early. At time 1, when a down move has occurred, the exercise value is $28[=\operatorname*{max}(0,X-S d)=\operatorname*{max}(0,105-77)]$ . Thus, the European put. price of 26.96 is replaced with 28 as the put buyer would prefer to receive 28 from early exercise rather than 26.96 from just holding the put option. This 1.04 increase in value results in the initial put price rising 0.52 to. $16.01$ as well as the hedge ratio rising to 0.49. The early exercise feature is illustrated in Figure 7.10..

We now further explore the role of dividends on both European and American options.
