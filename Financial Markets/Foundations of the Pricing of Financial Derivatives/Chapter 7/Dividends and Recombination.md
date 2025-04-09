# 7.6 DIVIDENDS AND RECOMBINATION

Dividends pose a significant problem with the multiplicative binomial model presented here. Figure 7.11 illustrates the loss of the recombining property in the presence of a cash. dividend at time 1. Recall that the stock price falls by the dollar dividend amount on the. ex-dividend date. As discussed in Chapter 2, optimal early exercise may occur either right before the ex-dividend date for calls or right after the ex-dividend date for puts.. Note that mathematically,

$$
\left(S u-D_{1}\right)d=\left(S d-D_{1}\right)u\mathrm{only}\mathrm{if}D_{1}=0.
$$

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>100</td></tr><tr><td>Put</td><td>15.49 16.01</td></tr><tr><td>Hedge Ratio</td><td>0.47 0.49</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>125</td></tr><tr><td>Put</td><td>4.33</td></tr><tr><td>Hedge Ratio</td><td>0.15</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>156.25</td></tr><tr><td>Put</td><td></td></tr></table></body></html>

FIGURE 7.10 Two-Period Binomial Model for American Put Option Illustrated


<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>77</td></tr><tr><td>Put</td><td>26.96 28.00</td></tr><tr><td>Hedge Ratio</td><td>1.00</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>96.25</td></tr><tr><td>Put</td><td>8.75</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>59.29</td></tr><tr><td>Put</td><td>45.71</td></tr></table></body></html>

![](37ecf09da98f621c3ebcdebc5a295434ce8796de07c179737a0f7613c056f7e7.jpg)
FIGURE 7.11 Two-Period Binomial Model with Discrete Dividends

Thus, the presence of discrete dividends poses a significant computational problem. The binomial tree fails to recombine and is known as a bushy tree. When a binomial tree does recombine, the number of nodes after $N$ time steps is. $N+1$ . Unfortunately, when. a binomial tree fails to recombine the node count explodes with more time steps.12 That is, the number of nodes after $N$ time steps is $2^{N}$ . There are numerous potential ways to address this challenge.

One efficient method is what is known as the escrow method. Suppose the firm places in escrow the present value of the dividend payments over the life of the option. That is, the present value of the dividends is set aside, and the remaining stock value is modeled. within the binomial framework. We define a new variable commonly known as the stock price without dividends denoted. $S^{\prime}$ . Therefore, the actual stock, S, can be decomposed. into two components, the present value of the dividend payments,. $P V(D)$ , and the rest of. the stock price, which excludes the dividends over the life of the option, $S^{\prime}$ 13 Figure 7.12 illustrates the escrow method..

We illustrate the incorporation of dividends with the escrow method in a two-period binomial example. Suppose the current stock price is 105, the exercise price is 100, the annual, discretely compounded, risk-free rate is $1\%$ , the time to expiration is two years, $u=1.25$ , and $d=0.77$ . Assume a dividend after one year of 2.0. Thus, the present value of the dividend is

$$
P V(D)=\frac{D_{1}}{(1+r)^{\Delta t}}=\frac{2}{(1+0.01)^{1}}=1.98.
$$

Therefore, the stock price without dividends is

$$
\begin{array}{r}{S^{\prime}=S-P V(D)=105-1.98=103.02.}\end{array}
$$

Based on the escrow method and corresponding single-period binomial model, we produce the results for European options provided in Figure 7.13..

The values for American options are different. At each node, we appraise whether the exercise value exceeds the binomial model value. At time 1, we have value adjustments as the call should be exercised right before going ex-dividend and the put should be exercised right after going ex-dividend. Based on this approach, Figure 7.14 illustrates the American option prices.

Thus, at time 1 after an up move has occurred, the call buyer will exercise the option right before the ex-dividend event, buy the stock at 100, and sell the stock at 130.77, netting 30.77. At time 1, when a down move has occurred, the put buyer will exercise the option right after the ex-dividend event, buy the stock at 77.33. $(=79.33-2)$ , and sell the stock via the put at 100, netting 22.67. Therefore, both the call and put prices are higher. for the American options when compared to the European options..

![](c9879426e49049879568e03176d0b4410c7b1559704c11bff460f610474d4f76.jpg)
FIGURE 7.12 Two-Period Binomial Model with Dividends Based on Escrow Method

![](b6f1bb719cc86b677f0806141069ffb4f99dc798cc46f3d2b6f2fd0b97b166ae.jpg)
HGuRe7.13 Numerical Example of Two-Period Binomial Model with Dividends for European Options

![](1dee67a26e27d3893b06d422de71d3aecbccb69bb54ee5ef59c66737fbdf3e72.jpg)
FGURE 7.14 Numerical Example of Two-Period Binomial Model with Dividends for American Options

We now examine cases where the binomial framework is difficult at best to apply.
