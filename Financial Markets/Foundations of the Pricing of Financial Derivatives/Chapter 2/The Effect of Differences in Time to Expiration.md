# 2.7 THE EFFECT OF DIFFERENCES IN TIME TO EXPIRATION

Consider two European calls differing only by time to expiration. One option expires at time $T_{1}$ and has a time to expiration of. $T_{1}-t=\tau_{1}$ and the other expires at $T_{2}$ and has a time to expiration of $T_{2}-t=\tau_{2}$ , and where $\tau_{2}>\tau_{1}$ . Their respective prices will be. $c_{t1}$ and $c_{t2}$ with similar notation for American calls as well as for European and American puts..

For a European call, it is simple to demonstrate that in the absence of dividends, the longer-term call must sell for at least as much as the shorter-term call. Suppose we are at the expiration date of the shorter-term call and the asset price is $S_{T_{1}}$ . Its value is $\operatorname*{max}(0,S_{T_{1}}-X)$ . The longer-term option, however, has time remaining of $\tau_{2}-\tau_{1}$ , so its minimum value is $\mathrm{max}[0,S_{T_{1}}-X e^{-r_{c}(\tau_{2}-\tau_{1})}].$ which is at least as great as the value of the shorter-term expiring option. Consequently,

$$
c_{t2}\geq c_{t1},
$$

with the LHS being the current price of the longer term call, and the RHS being the current price of the shorter-term call. Thus, the longer-term call cannot be worth less than the. shorter-term call. In the absence of dividends, there would be no early exercise, so the previous statement would apply for American options..

$$
\mathrm{C}_{t2}\geq\mathrm{C}_{t1}.
$$

If there are dividends, then the longer term European call has a minimum value of. $\operatorname*{max}[0,S_{T_{1}}-D-X e^{-r_{c}(\tau_{2}-\tau_{1})}]$ , which might make it seem as if that option has a mini-. mum less than the exercise value of the expiring option. If that is the case, however, the longer-term American option would sell for at least the exercise value. Consequently, Equation (2.24) is still valid.

For a European put, we obtain a somewhat counterintuitive result. First assume no dividends. Then the expiring, shorter-term option is worth. $\operatorname*{max}(0,X-S_{T_{1}})$ . The second option, which still has time remaining, is worth at least. $\mathrm{max}[0,X e^{-r_{c}(\tau_{2}-\tau_{1})}-S_{T_{1}}]$ Thus, it might be the case that the shorter-term option is worth more. This somewhat strange. result that a longer-term European put can be worth less than a shorter-term European put. arises because there are conflicting sources of value arising from the time to expiration in. an option. A longer time to expiration generally helps an option, whether a put or a call,. in that it gives it greater time for a favorable asset price move to occur. The longer time to expiration also has an effect arising from the present value of the potential payoff at expiration. For a put, the better outcome at expiration is to exercise it, which will result in a. cash inflow from the sale of the asset. A longer time to expiration reduces the present value of this inflow, however, rendering the put potentially less valuable. This disadvantage of. a longer expiration can be partially, perhaps wholly, offset by the advantage of the longer time for a favorable asset price move. Puts that are deep in-the-money will tend to have this disadvantage weigh more than the advantage because their potential for exercise is greater and their potential for gains from further asset price moves is limited. All other puts will tend to have the advantage greater than the disadvantage. With the LHS being the current price of the longer-term put and the RHS being the current price of the shorter-term put, the overall result is

$$
\begin{array}{r}{p_{t2}\geq\leq p_{t1}.}\end{array}
$$

In other words, we cannot definitely make a statement about the relationship of a longerterm European put price to the shorter-term put price..

If the put is American, however, there is no requirement to wait to receive the exercise price at expiration. It can always be claimed now. Thus,

$$
P_{t2}\ge P_{t1}.
$$

If there are dividends on the asset and the puts are European, the expiring option. is worth $\operatorname*{max}(0,S_{T_{1}}-X)$ . The other option is still alive and worth at least max. $[0,X e^{-r_{c}(\tau_{2}-\tau_{1})}-D_{1}\stackrel{.}{-}S_{T_{1}}]$ Again, it may be the case that the longer-term put is worth. less, which would, of course, all depend on the various factors that affect the option price. Consequently, our previous statement for European puts for the no-dividend case holds as well if there are dividends. If the puts are American, the remaining option will always sell for at least its exercise value, which makes it worth at least as much as the expiring option. Consequently, our statement for American puts without dividends holds when dividends are introduced.
