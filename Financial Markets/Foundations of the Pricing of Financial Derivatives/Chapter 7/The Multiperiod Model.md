# 7.4 THE MULTIPERIOD MODEL

The case we have covered until now spans only one period. We can easily extend the model. to multiple periods and thereby accommodate options with longer lives.3 The layout is illustrated in Figure 7.6. We let the asset move from $S u$ to $S u^{2}$ or Sud, and from. $S d$ to $S d u$ or $S d^{2}$ . Note that $S u d=S d u$ , so over two periods, there are three possible outcomes. The asset can go up twice to $S u^{2}$ , up and then down or down and then up to. $S u d_{;}$ or down twice to $S d^{2}$ . The call and put option payoffs in those states are4.

$$
\begin{array}{l l}{{c_{u^{2}}=\operatorname*{max}(0,S u^{2}-X)~}}&{{\displaystyle p_{u^{2}}=\operatorname*{max}(0,X-S u^{2})}}\ {{c_{u d}=\operatorname*{max}(0,S u d-X)~\mathrm{and}~p_{u d}=\operatorname*{max}(0,X-S u d).}}&{{}}\ {{c_{d^{2}}=\operatorname*{max}(0,S d^{2}-X)~}}&{{\displaystyle p_{d^{2}}=\operatorname*{max}(0,X-S d^{2})}}\end{array}
$$

The illustration is looking more like a branching tree or lattice. Two key features of the binomial model are the recombining nature of the tree and that the growth of the stock price is multiplicative. The tree is recombining because the stock price is assumed to grow multiplicatively such that. $S u d=S d u$ . Clearly, the order of multiplication does not matter.. The multiplicative approach presented here facilitates the convergence of the stock price. to the lognormal distribution--a point we will explore in Chapter 9.5.

Let us position ourselves in the time 1 up state, where the asset price is $S u$ .  At this point, we are now back in a one-period world. There are two possible outcomes in the next period, which is the expiration. It should be easy to see that the value of the call and put at this point would be

![](images/ff60534e24e860b2fe4469b728753f618cf87d654b28287db14451e243d57697.jpg)
FIGURE 7.6 Two-Period Binomial Model

$$
c_{u}=\frac{\phi c_{u^{2}}+(1-\phi)c_{u d}}{1+r}\mathrm{~and~}p_{u}=\frac{\phi p_{u^{2}}+(1-\phi)p_{u d}}{1+r}.
$$

Likewise, in the time 1 down state, the option value would be

$$
c_{d}=\frac{\phi c_{u d}+(1-\phi)c_{d^{2}}}{1+r}\mathrm{~and~}p_{d}=\frac{\phi p_{u d}+(1-\phi)p_{d^{2}}}{1+r}.
$$

Stepping back to time 0, the values of the call and put options are again found with Equation (7.9), where the values of $c_{u}$ and $\boldsymbol{p}_{u}$ are given in Equation (7.20) and $c_{d}$ and $\mathbf{\nabla}p_{d}$ are given in Equation (7.21). Thus, to price options in the binomial framework in a multiperiod model, we start at the end-the exercise date-and work backwards to the present.

The special case for two-period options does lend itself to a simple formula that relates the initial option value to the value two periods later, essentially skipping over the first period:

$$
=\frac{\phi^{2}c_{u^{2}}+2\phi(1-\phi)c_{u d}+(1-\phi)^{2}c_{d^{2}}}{(1+r)^{2}}\mathrm{~and~}p=\frac{\phi^{2}p_{u^{2}}+2\phi(1-\phi)p_{u d}+(1-\phi)^{2}p_{d^{2}}}{(1+r)^{2}}.
$$

Note that the three option payoffs two periods later are each weighted by the risk-neutral probabilities, $\phi^{2}$ $2\phi(1-\phi)$ , and $ (1-\bar{\phi})^{2}$ . These are the binomial probabilities for two trials, and they add up to 1. The coefficients on the probabilities are 1, 2, and 1. These numbers are the coefficients of the two-period binomial expansion commonly expressed as $(a+b)^{2}$ , which equals $a^{2}+2a b+b^{2}$ . Note the binomial coefficients 1, 2, 1. This pattern would continue through additional periods, a result that will help us when we use the binomial model with a very large number of periods to approximate a continuous time world.6

The seemingly simplifying assumptions of a binomial world, whereby an asset can go to only one of two values, can send a false signal that the model is unrealistic. We shall see in Chapter 9 that the model can be made highly realistic. We will divide the finite life of an option into a very large number of periods, ultimately leading to an extremely large number of possible outcomes.

Now we provide an example of how the binomial model works when extending to two periods. Suppose the current stock price is 40, the exercise price is 40, the annual, discretely compounded, risk-free rate is $2\%$ , the time to expiration is two years, $u=1.25$ and $d=0.8$ . Now assume a two-period binomial model. Based on Equation (7.22), we can compute the call and put prices. First, we compute the terminal payoffs for both calls and puts as

$$
\begin{array}{r l}&{c_{u^{2}}=\operatorname*{max}\left(0,S u^{2}-X\right)=\operatorname*{max}\left[0,40(1.25)^{2}-40\right]=22.5}\ &{c_{u d}=\operatorname*{max}\left(0,S u d-X\right)=\operatorname*{max}\left[0,40(1.25)0.8-40\right]=0\mathrm{~and}}\ &{c_{d^{2}}=\operatorname*{max}\left(0,S d^{2}-X\right)=\operatorname*{max}\left[0,40(0.8)^{2}-40\right]=0}\end{array}
$$

$$
\begin{array}{r}{p_{u^{2}}=\operatorname*{max}\left(0,X-S u^{2}\right)=\operatorname*{max}\left[0,40-40(1.25)^{2}\right]=0}\end{array}
$$

$$
\begin{array}{r}{\phi_{u d}=\operatorname*{max}\left(0,X-S u d\right)=\operatorname*{max}\left[0,40-40(1.25)0.8\right]=0}\end{array}
$$

$$
\begin{array}{r}{p_{d^{2}}=\operatorname*{max}\left(0,X-S d^{2}\right)=\operatorname*{max}\left[0,40-40(0.8)^{2}\right]=14.4.}\end{array}
$$

The binomial probability of an up move over a single period is $\phi=(1+0.02-$ $0.8)/(1.25-0.8)=48.8889\%$ . Therefore, based on Equation (7.22), we find.

$$
\begin{array}{l}{c=\cfrac{\phi^{2}c_{u^{2}}+2\phi(1-\phi)c_{u d}+(1-\phi)^{2}c_{d^{2}}}{(1+r)^{2}}}\ {=\cfrac{(0.4889)^{2}22.5+2(0.4889)(1-0.4889)0+(1-0.4889)^{2}0}{(1+0.02)^{2}}=5.17}\end{array}
$$

and

$$
\begin{array}{l}{\displaystyle{p=\frac{\phi^{2}p_{u^{2}}+2\phi(1-\phi)p_{u d}+(1-\phi)^{2}p_{d^{2}}}{(1+r)^{2}}}}\ {\displaystyle{~=\frac{(0.4889)^{2}0+2(0.4889)(1-0.4889)0+(1-0.4889)^{2}14.4}{(1+0.02)^{2}}=3.62.}}\end{array}
$$

Alternatively, the two-period binomial model can be viewed as three one-period binomial models that apply the no-arbitrage condition. The call results are illustrated in Figure 7.7 and the put results are illustrated in Figure 7.8..

We turn now to address American options where early exercise can enhance the worth of an option.

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>50</td></tr><tr><td>Call</td><td>10.78431</td></tr><tr><td>Hedge Ratio</td><td>1</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>32</td></tr><tr><td>Call</td><td>0</td></tr><tr><td>Hedge Ratio</td><td></td></tr></table></body></html>

FIGURE 7.7 Two-Period Binomial Model for Calls Illustrated


<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>40</td></tr><tr><td>Call</td><td>5.16895</td></tr><tr><td>Hedge Ratio</td><td>0.59913</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>62.5</td></tr><tr><td>Call</td><td>22.5</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>40</td></tr><tr><td>Call</td><td>0</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>25.6</td></tr><tr><td>Call</td><td>0</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>50</td></tr><tr><td>Put</td><td>0</td></tr><tr><td>Hedge Ratio</td><td>0</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>32</td></tr><tr><td>Put</td><td>7.21569</td></tr><tr><td>Hedge Ratio</td><td>1</td></tr></table></body></html>

FIGURE 7.8 Two-Period Binomial Model for Puts Illustrated


<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>40</td></tr><tr><td>Put</td><td>3.61570</td></tr><tr><td>Hedge Ratio</td><td>0.40087</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>62.5</td></tr><tr><td>Put</td><td></td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>40</td></tr><tr><td>Put</td><td>0</td></tr></table></body></html>

<html><body><table><tr><td>Item</td><td>Value</td></tr><tr><td>Underlying</td><td>25.6</td></tr><tr><td>Put</td><td>14.4</td></tr></table></body></html>
